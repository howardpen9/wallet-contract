# Wallet v5r2
Wallet v5 is custom version of wallet for use instead of v4.

There are three main differences from previous versions:
1. execute arbitrary code onchain. User can pass a continuation to be executed -- this is useful for predicting unsafe random.
2. plugin functionality: plugins are continuations, like small inlined contracts. They may be executed upon getting an incoming message.
   Actual plugin's code is stored in masterchain, so that plugins are just masterchain libraries.
3. secp256r1 keys are supported in addition to Ed25519 ones.

All plugin functions must be inlined, as otherwise call will go out of plugin control so the function won't be found.
