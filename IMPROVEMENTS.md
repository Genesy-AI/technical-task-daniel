# Improvements

## Backend country code validation on bulk import

CSV parsing now rejects invalid ISO 3166-1 alpha-2 country codes on the frontend, but `POST /leads/bulk` still accepts any string for `countryCode` after a trim. Add the same validation on the backend so invalid values cannot be persisted via API clients that bypass the CSV UI.

# startToCloseTimeout on workflows

Currently we have have the startToCloseTimeout in our workflows to 10 s before considering a user stuck. Is this the best time to consider a user stuck, or should we increase it?
