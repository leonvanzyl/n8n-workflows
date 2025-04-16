# WhatsApp AI Agent with n8n

A project based on the n8n tutorial for integrating AI agents with WhatsApp.

## Overview

This project demonstrates how to set up an AI-powered WhatsApp bot using n8n. With this implementation, you can create automated responses and intelligent interactions through WhatsApp messaging.

## Tutorial

This implementation follows the tutorial available on YouTube:
[Adding AI Agents to WhatsApp using n8n](https://youtu.be/dZe6dKMS-vY)

## Fix mime type

```javascript
// Loop over input items and change the MIME type of binary data
for (const item of $input.all()) {
  // Check if the item has binary data
  if (item.binary) {
    // Find the binary property name (assuming there's at least one)
    const binaryPropertyNames = Object.keys(item.binary);

    for (const propName of binaryPropertyNames) {
      // If the MIME type is 'audio/mp3', change it to 'audio/mpeg'
      if (item.binary[propName].mimeType === "audio/mp3") {
        item.binary[propName].mimeType = "audio/mpeg";
      }
    }
  }
}

return $input.all();
```
