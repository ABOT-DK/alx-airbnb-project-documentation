# Airbnb Clone - Booking System Core Flow

## Overview
This document outlines the primary sequential flow for property bookings in the Airbnb clone backend system. The process handles availability verification, payment processing, and booking confirmation.

## Linear Main Flow

```mermaid
flowchart LR
    A([Start]) --> B[Check Availability]
    B --> C[Calculate Total]
    C --> D[Create Temporary Hold]
    D --> E[Process Payment]
    E --> F[Confirm Booking]
    F --> G[Send Notifications]
    G --> H([End])
