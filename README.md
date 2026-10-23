# Málaga Price Check — Moneyball for Airbnb

**Can data find the bargains the market misses?**

An interactive tool built for the EDHEC *Advanced Data Analysis* project (Prof. Etienne Denis).
It predicts the fair nightly price of an Airbnb listing in Málaga and flags listings that are
priced well below or above what the model expects.

## The two pages

| Page | What it does |
|------|--------------|
| **Map** (`#map`) | 6,268 Málaga listings as dots: 🟢 underpriced, 🔴 overpriced, ⚪ fairly priced. Filter by season, rental type, guests and neighbourhood. Listing cards on the side show advertised price vs model price. |
| **Valuer** (`#value`) | Enter a property (guests, bedrooms, distance to the beach, rating, amenities, booking rules…) and get its model value, a ±30% "fair zone", and what drives the price up or down. |

## How the model works

- Data: 6,612 listings × 3 snapshots (March, June, September 2026), Inside Airbnb.
- PCA on 19 standardised variables → 4 factors, the "4 S's": **Space** (property capacity), **Spot** (location remoteness), **Stars** (guest-perceived quality), **Stuff** (amenities).
- Multiple regression on ln(price) with a 70/30 train/test split by listing (R² ≈ 0.61).
- A listing is **under/overpriced** when its advertised price is more than 30% away from the predicted price (≈ 1 standard deviation of the residuals).

## Run it

It is a single self-contained file: open `index.html` in any browser, or view it on GitHub Pages.

## Team

Thibauld · Minh · Amélie · Anugraha · Giorgia · Jeanne
