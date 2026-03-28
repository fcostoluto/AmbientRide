# AmbientRide Privacy Policy

**Last updated:** March 25, 2026

## Overview

AmbientRide is an ambient commute intelligence platform that uses on-device AI to match riders with drivers sharing similar routes. **Privacy is a core architectural principle** — all AI inference runs locally on your device.

## Data We Collect

### Account Data
- Email address and display name (for authentication)
- Stored in Supabase with row-level security

### Location Data
- **GPS coordinates** are collected only while actively sharing a route (Driver mode)
- Location data is used for real-time ride matching and route display
- Driver location is stored as a **single row** (atomic upsert) — no location history is kept on the server
- Location tracking stops immediately when you stop sharing your route

### Ride Data
- Ride requests (pickup/dropoff coordinates and labels)
- Match records (compatibility scores, rendezvous points)
- CO2 savings ledger entries

### Device Data
- FCM push notification token (for match notifications)
- Device contacts are **hashed locally** (SHA-256) for social trust scoring — **raw contacts are never transmitted**
- Calendar events are processed **entirely on-device** — no calendar data leaves your phone

## Data We Do NOT Collect

- No GPS history or trajectory logs
- No raw contact names, numbers, or email addresses
- No calendar event content
- No clipboard data
- No notification content
- No browsing history
- No advertising identifiers

## On-Device AI Processing

AmbientRide uses on-device AI models that run entirely on your phone:

- **Route intent classifier** — infers your destination from GPS movement patterns
- **Embedding encoder** — scores ride compatibility
- **Small language model** — parses destinations, generates match explanations

All AI inference happens locally. No prompts, GPS data, or personal context is sent to any cloud AI service.

## Federated Learning

Our models improve over time using **federated learning with differential privacy**:

- Your device computes gradient updates from your trip outcomes locally
- **Calibrated noise** is added before transmission (differential privacy)
- Only gradient vectors (not raw data) are sent to the aggregation server
- No GPS coordinates, routes, or personal identifiers are included in gradient updates

## Data Sharing

We do not sell, rent, or share your personal data with third parties.

Data is shared only:
- Between matched riders and drivers (limited to: rendezvous point, compatibility score, display name)
- With Supabase (database hosting) under their data processing agreement
- With Firebase (push notifications only — FCM token and notification content)

## Data Retention

- **Driver location:** Overwritten on each update, deleted when tracking stops
- **Ride requests:** Retained until completed or cancelled
- **Match records:** Retained for CO2 ledger and ride history
- **Account data:** Retained until you delete your account

## Your Rights

You can:
- **View** all your data in the app (Matches, CO2 Impact, Settings)
- **Delete** ride requests and matches
- **Export** your CO2 savings data
- **Delete your account** and all associated data
- **Revoke permissions** at any time in device Settings

## Permissions Explained

| Permission | Purpose | When Used |
|-----------|---------|-----------|
| Location (Fine) | GPS for route sharing and pickup | Driver mode, "Use current location" |
| Notifications | Match alerts | When a compatible ride is found |
| Bluetooth | Nearby rider discovery | Offline matching (optional) |
| Calendar | Trip suggestions from events | Calendar integration (optional) |
| Contacts | Social trust scoring | Social matching (optional, hashed locally) |

All optional permissions can be disabled in Settings without affecting core functionality.

## Contact

For privacy questions or data deletion requests:
- Email: privacy@ambientride.app

## Changes

We will notify you of material changes to this policy via in-app notification.
