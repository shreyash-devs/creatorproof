# CreatorProof

CreatorProof is a cross-platform Flutter application that helps creators publish content with verifiable proof metadata.  
It combines content publishing, identity signals, and blockchain-backed proof anchoring into one user experience.

## Overview

The platform is designed for creators who want stronger attribution and trust around their digital work.  
Each content item can be paired with proof details, on-chain transaction references, and a certificate-style view for verification workflows.

## Core Capabilities

- Creator authentication with Firebase and Google Sign-In
- Global feed with creator profiles, engagement, and comments
- Media upload flow with Cloudinary integration
- Proof record creation and storage in Firestore
- Blockchain anchoring workflow using Polygon Amoy (via `web3dart`)
- Verification-focused views including proof and certificate screens
- Notifications and creator dashboard surfaces

## Product Architecture

CreatorProof follows a feature-first Flutter structure with clear separation between UI, state, and data services:

- **UI layer** in `lib/features/`: screens and widgets by feature domain
- **State layer** with `provider`: app-level theme and auth state
- **Data layer** in `lib/data/`:
  - repositories for Firestore-backed entities (users, posts, proofs, comments, notifications)
  - services for Cloudinary uploads, wallet/key handling, and blockchain transactions
- **Core layer** in `lib/core/`: routes, theme system, constants, and shared app foundations
- **Shared layer** in `lib/shared/`: reusable widgets and models used across features

## Key User Flows

### Creator Journey

1. Authenticate (email/password or Google)
2. Upload media content
3. Generate and attach proof metadata
4. Anchor proof reference through blockchain transaction
5. Publish and share content with verification context

### Trust and Verification Journey

1. Open a creator post or proof detail
2. Review proof metadata and transaction references
3. Access certificate-style representation for validation
4. Use verification views to inspect authenticity signals

## Tech Stack

- **Framework:** Flutter (Dart)
- **State Management:** `provider`
- **Routing:** `go_router`
- **Backend:** Firebase (`firebase_auth`, `cloud_firestore`, `firebase_core`)
- **Media Storage:** Cloudinary (`http` multipart upload)
- **Blockchain:** `web3dart`, `crypto`, wallet utilities
- **Local Secure Storage:** `flutter_secure_storage`
- **UI/UX Libraries:** `google_fonts`, `flutter_animate`, `shimmer`, `cached_network_image`, and media playback packages

## Project Structure

```text
lib/
  app.dart
  main.dart
  core/
    routes/
    theme/
    constants/
    utils/
  data/
    providers/
    repositories/
    services/
  features/
    auth/
    main/
    home/
    upload/
    portfolio/
    profile/
    proof/
    verify/
    notifications/
    dashboard/
    settings/
  shared/
    models/
    widgets/
```

## Platform Support

CreatorProof includes Flutter runners for:

- Android
- iOS
- Web
- Windows
- macOS
- Linux

## Vision

CreatorProof is built to make digital authorship more transparent, trackable, and trustworthy for modern creators.
