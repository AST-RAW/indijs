INDIjs
===

INDIjs is a nodejs binding of the INDI library. INDI Library is an Open Source Architecture for Control & Automation of Astronomical Devices. It only binds the client part of the library but device part will be added.

Install
---

You'll need INDI library and headers to be able to compile.

```bash
npm install @astraw/indijs
```

Usage
---

```js
import { Client } from "@astraw/indijs";

const client = new Client("localhost");

client
  .on("connected", () => { /* code */ })
  .on("disconnected", (reason_code) => { /* code */ })
  .on("newDevice", (device) => { /* code */ })
  .on("removeDevice", (devname) => { /* code */ })
  .on("newProperty", (property) => { /* code */ })
  .on("updateProperty", (property) => { /* code */ })
  .on("removeProperty", (propname, devname) => { /* code */ })
  .on("newMessage", (device, messageID) => { /* code */ })

client.connect().then(() => {
  console.log("connected...");
});
```