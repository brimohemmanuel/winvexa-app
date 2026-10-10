# Winvexa Android — Live Withdrawal Ticker (RPC-backed)

This version keeps the supplied Winvexa HTML and changes the live public withdrawal ticker to read from the secure Supabase RPC `public.get_public_withdrawals()` instead of trying to read the protected `withdrawals` table directly.

Run `get_public_withdrawals.sql` in the Supabase SQL Editor before testing. The function returns only masked/public withdrawal data, including old and new pending/verified withdrawals.

The ticker continuously moves right-to-left and refreshes in the background.


Latest live withdrawal ticker update: shown only on Home, positioned around the Winvexa crown, glass/translucent cards, bank accounts masked as ****1234, and PayPal cards use a PayPal-style P icon.


Latest live withdrawal UI update: ticker moved to the crown area; bank public account masking uses the available last four digits (including public destination fallback); PayPal shows Winvexa player name before masked email.


Latest UI update: the white crown icon is removed from the Home brand area and the live withdrawal ticker occupies the crown slot.


## AdMob integration status (development only)
- Google Mobile Ads SDK is included in the Android project.
- AdMob App ID is configured for Winvexa Spin.
- The app currently uses Google's official TEST rewarded-ad unit ID so ads can be tested safely.
- Do not replace the test ad unit with the live unit for development.
- Important: this is the SDK/bridge integration stage only. Reward callbacks are not yet secured with AdMob Server-Side Verification (SSV) and a Supabase verification endpoint. Do not publish or grant production rewards until that server-side verification step is implemented and tested.
- The HTML's existing ad bridge returns false when opened outside the Android app or when an ad is not ready.
