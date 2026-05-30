# Adwings Chat Platform Widget

**Embeddable live chat widget for customer support, powered by the Adwings Chat Platform service.**

## Features

* 🚀 One-click install — paste your site key and you're live
* 💬 Real-time messaging powered by Socket.IO
* 🎨 Shadow DOM–isolated UI so theme styles can't break the widget
* ⚙️ Configurable accent color and corner placement
* 🔌 Zero PHP-side socket logic — everything runs in the visitor's browser

---

## Requirements

| Requirement  | Version |
| ------------ | ------- |
| WordPress    | 6.0+    |
| Tested up to | 6.7     |
| PHP          | 7.4+    |

---

## Overview

Adwings Chat Platform Widget adds a real-time chat bubble to every front-end page of your WordPress site, allowing visitors to communicate with your support team without leaving the page.

To use this plugin, you'll need an Adwings Chat Platform account to obtain:

* A **Site Key**
* A **Server URL**

---

## Installation

### Option 1: Install via WordPress Admin

1. Navigate to **Plugins → Add New**.
2. Upload the plugin ZIP file.
3. Activate the plugin.

### Option 2: Manual Installation

1. Upload the plugin files to:

   ```text
   /wp-content/plugins/adwings-chat-platform-widget/
   ```

2. Activate the plugin from the **Plugins** menu in WordPress.

### Configuration

1. Go to **Settings → Adwings Chat Platform Widget**
2. Enter your:

   * Site Key
   * Server URL
3. Optionally customize:

   * Widget color
   * Widget position
4. Click **Save Changes**

The chat widget will automatically appear on all front-end pages.

---

## How It Works

The plugin injects a single JavaScript widget into your site's front end.

All chat functionality runs directly in the visitor's browser:

* Loads the widget script from your configured server
* Establishes secure HTTPS/WebSocket connections
* Sends and receives chat messages in real time
* Requires no socket handling or message processing on your WordPress server

---

## External Services

This plugin connects to the Adwings Chat Platform service that you configure via the **Server URL** setting.

### Data Transmitted

#### On Every Front-End Page Load

The visitor's browser downloads the widget JavaScript from:

* Configured **Server URL**
* Optional **Widget Script URL** override

#### When a Visitor Uses Chat

The following data may be transmitted directly from the visitor's browser to the configured service:

* Chat message content
* Auto-generated session identifier
* IP address
* User-Agent information

Communication occurs over:

* HTTPS
* WebSocket

#### Site Identification

The configured Site Key is rendered as a:

```html
<script data-key="YOUR_SITE_KEY"></script>
```

attribute so the service can identify your website.

### Important Notes

* No chat data is transmitted by the WordPress server itself.
* The plugin does not send information to third parties on its own.
* Data handling policies are determined by the service configured in your Server URL.

Please review your service provider's Privacy Policy and Terms of Service.

---

## Frequently Asked Questions

### Where do I get a Site Key?

Sign in to your Adwings Chat Platform dashboard and create a site. The generated Site Key will be available in the site's settings.

### Can I pin a specific widget version?

Yes.

Set a versioned URL in **Widget Script URL**, for example:

```text
https://cdn.example.com/widget-v1.2.3.js
```

Leave the field blank to always load the latest version.

### Does this work with caching plugins?

Yes.

Because the widget is loaded directly from the configured CDN or service endpoint, page caching plugins do not interfere with widget updates.

### Does the widget call back to my WordPress server?

No.

All traffic flows directly between the visitor's browser and the Adwings Chat Platform service.

WordPress only outputs a single script tag.

### Will the widget appear before I configure it?

No.

The widget is only loaded when both:

* Site Key
* Server URL

have been configured.

---

## Screenshots

1. Settings page in WordPress Admin
2. Chat bubble displayed on the website
3. Open chat conversation window

---

## Changelog

### 1.0.0

* Initial public release

---

## Upgrade Notice

### 1.0.0

First public release.
