# GetTokenSilentlyHelper(bool,ulong,uchar *,unsigned __int64,Windows::Security::Credentials::IWebAccountProvider *,bool *,_GUID *,ulong *,ulong *,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult * *,IUnknown *)

- ea: `0x18005aa84`
- end: `0x18005cf60`
- name: `?GetTokenSilentlyHelper@@YAJ_NKPEAE_KPEAUIWebAccountProvider@Credentials@Security@Windows@@PEA_NPEAU_GUID@@PEAK6PEAPEAUIWebTokenRequestResult@Core@Web@Authentication@34@PEAUIUnknown@@@Z`
- size: `9436`
- prototype: `__int64 __fastcall(char, unsigned int, unsigned __int8 *, __int64, struct Windows::Security::Credentials::IWebAccountProvider *, bool *, struct _GUID *, unsigned int *, unsigned int *, struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult **, struct IUnknown *)`
- caller_count: `4`
- callee_count: `47`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005aa00`
- `0x1800aad70`
- `0x1800aae70`
- `0x1800aaf70`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x18000bd70`
- `0x18000d250`
- `0x180010a70`
- `0x180023a80`
- `0x180024000`
- `0x1800247e4`
- `0x180024ae4`
- `0x1800256d8`
- `0x180025bd8`
- `0x1800262f0`
- `0x1800266b0`
- `0x180026728`
- `0x180026a5c`
- `0x180027a50`
- `0x18002ea84`
- `0x18002fbf0`
- `0x180031270`
- `0x1800344b8`
- `0x18003ea90`
- `0x1800439d0`
- `0x1800455a4`
- `0x1800490c0`
- `0x18004a4fc`
- `0x18004a75c`
- `0x18004b848`
- `0x18004dc68`
- `0x18004fdbc`
- `0x180053cfc`
- `0x18005aa84`
- `0x18005ea74`
- `0x18006072c`
- `0x1800637b4`
- `0x180066608`
- `0x1800682e4`
- `0x180068734`
- `0x18006f778`
- `0x180070660`
- `0x18007f6e0`
- `0x18008e690`
- `0x18009942c`
- `0x1800a3754`
- `0x1800a5688`
- `0x1800b33f0`
- `0x1800ef7fc`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005acd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ace1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005acf2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ad8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ad9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005adae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ae61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ae72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ae83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005af2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005af3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005af50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005affa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b00b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b01c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b108`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b119`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b12a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b278`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b289`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b29a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b38b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b39c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b3ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b488`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b499`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b4aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b59e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b5af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b5c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b695`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b6a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b6b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b837`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b848`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b859`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b94f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b960`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b971`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b9a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ba96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005baa7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005bab8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005bbfe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005bc0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005bc20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005bd97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005bda8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005bdb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005be9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005beae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005bebf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c01c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c02d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c03e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c11f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c130`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c141`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c224`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c235`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c246`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c3cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c3dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c3ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c5e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c5f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c60a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c74d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c75e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c76f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c8f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c90a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c91b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ca9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005caac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cabd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cdad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cdbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cdcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cef4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cf05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cf16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005acd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ace1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005acf2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ad8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ad9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005adae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ae61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ae72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ae83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005af2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005af3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005af50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005affa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b00b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b01c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b108`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b119`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b12a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b278`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b289`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b29a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b38b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b39c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b3ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b488`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b499`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b4aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b59e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b5af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b5c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b695`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b6a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b6b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b837`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b848`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b859`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b94f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b960`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b971`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b9a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ba96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005baa7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005bab8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005bbfe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005bc0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005bc20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005bd97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005bda8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005bdb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005be9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005beae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005bebf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c01c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c02d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c03e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c11f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c130`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c141`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c224`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c235`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c246`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c3cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c3dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c3ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c5e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c5f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c60a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c74d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c75e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c76f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c8f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c90a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c91b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ca9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005caac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cabd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cdad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cdbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cdcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cef4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cf05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cf16`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005ab49`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005ab49`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005c4a7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005c4a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005cbd4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005cbd4`

## string_xrefs

- `0x18005ac85`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18005ad41`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18005ae08`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18005aed5`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18005afa1`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18005b093`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18005b1ea`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18005b2fd`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18005b3fa`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18005b510`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18005b620`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18005b78a`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18005b8a2`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18005b9e9`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18005bb51`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18005bcdf`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18005c064`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18005c303`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18005c511`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18005c676`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18005c7fb`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18005c98f`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18005cb4e`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18005cbad`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18005ccba`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18005b4d8`: `delegatedTokenRequests`

## pseudocode

```c
// Hidden C++ exception states: #wind=55
__int64 __fastcall GetTokenSilentlyHelper(
        char a1,
        unsigned int a2,
        unsigned __int8 *a3,
        __int64 a4,
        struct Windows::Security::Credentials::IWebAccountProvider *a5,
        bool *a6,
        struct _GUID *a7,
        unsigned int *a8,
        unsigned int *a9,
        struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult **a10,
        struct IUnknown *a11)
{
  unsigned __int64 *v15; // r8
  int UserContextFromProvider; // eax
  unsigned int v17; // ebx
  int v18; // eax
  int v19; // eax
  unsigned int v20; // edx
  int BuiltInProviderType; // eax
  int v23; // eax
  struct Windows::Security::Authentication::Web::Core::IWebTokenRequest **v24; // r8
  int v25; // eax
  unsigned __int8 *v26; // rbx
  __int64 (__fastcall *v27)(unsigned __int8 *, GUID *, __int64 *); // rdi
  int v28; // eax
  int v29; // eax
  Windows::Internal::Security::Authentication::Web::CallerContext *v30; // rbx
  HSTRING *v31; // rax
  int v32; // eax
  int v33; // eax
  int (__fastcall *v34)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *); // rbx
  __int64 v35; // rcx
  int v36; // eax
  int v37; // eax
  int PluginPFN; // eax
  const struct _tlgProvider_t *v39; // rax
  __int64 v40; // rdi
  __int64 (__fastcall *v41)(__int64, __int64 *); // rbx
  int v42; // eax
  int v43; // eax
  __int64 v44; // rax
  int Buffer; // eax
  HSTRING CallingAppName; // rax
  int v47; // eax
  const struct _tlgProvider_t *v48; // rax
  int v49; // r9d
  int v50; // ebx
  struct Windows::Storage::Streams::IBuffer **v51; // r8
  int v52; // eax
  __int64 v53; // rbx
  __int64 (__fastcall *v54)(__int64, __int64 *); // rdi
  int v55; // eax
  int v56; // eax
  int v57; // r8d
  int v58; // edx
  __int64 v59; // rbx
  __int64 (__fastcall *v60)(__int64, int *); // rdi
  int v61; // eax
  int RequestHash; // eax
  int v63; // ebx
  struct Windows::Storage::Streams::IBuffer **v64; // r9
  int BufferFromByteArray; // eax
  void *v66; // rcx
  int v67; // eax
  struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *v68; // rax
  int v69; // [rsp+20h] [rbp-398h]
  int v70; // [rsp+20h] [rbp-398h]
  int v71; // [rsp+20h] [rbp-398h]
  int v72; // [rsp+20h] [rbp-398h]
  int v73; // [rsp+20h] [rbp-398h]
  int v74; // [rsp+20h] [rbp-398h]
  int v75; // [rsp+20h] [rbp-398h]
  int v76; // [rsp+50h] [rbp-368h] BYREF
  Windows::Internal::Security::Authentication::Web::CallerContext *v77; // [rsp+58h] [rbp-360h] BYREF
  HSTRING string; // [rsp+60h] [rbp-358h] BYREF
  HSTRING v79; // [rsp+68h] [rbp-350h] BYREF
  HSTRING v80; // [rsp+70h] [rbp-348h] BYREF
  __int64 v81; // [rsp+78h] [rbp-340h] BYREF
  Windows::Internal::Security::Authentication::TokenBroker *v82; // [rsp+80h] [rbp-338h] BYREF
  __int64 v83; // [rsp+88h] [rbp-330h] BYREF
  __int64 v84; // [rsp+90h] [rbp-328h] BYREF
  __int64 v85; // [rsp+98h] [rbp-320h] BYREF
  __int64 v86; // [rsp+A0h] [rbp-318h] BYREF
  __int64 v87; // [rsp+A8h] [rbp-310h] BYREF
  unsigned __int8 *v88; // [rsp+B0h] [rbp-308h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B8h] [rbp-300h] BYREF
  void *TokenHandle; // [rsp+C0h] [rbp-2F8h] BYREF
  char v91; // [rsp+C8h] [rbp-2F0h]
  __int64 v92; // [rsp+D0h] [rbp-2E8h] BYREF
  __int64 v93; // [rsp+D8h] [rbp-2E0h] BYREF
  __int64 v94; // [rsp+E0h] [rbp-2D8h] BYREF
  __int64 v95; // [rsp+E8h] [rbp-2D0h] BYREF
  int v96[2]; // [rsp+F0h] [rbp-2C8h] BYREF
  __int64 v97; // [rsp+F8h] [rbp-2C0h] BYREF
  __int64 v98; // [rsp+100h] [rbp-2B8h] BYREF
  unsigned int v99[2]; // [rsp+108h] [rbp-2B0h] BYREF
  struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *v100; // [rsp+110h] [rbp-2A8h] BYREF
  int v101; // [rsp+118h] [rbp-2A0h] BYREF
  _OWORD v102[2]; // [rsp+120h] [rbp-298h] BYREF
  int v103; // [rsp+140h] [rbp-278h]
  char v104; // [rsp+144h] [rbp-274h]
  _QWORD v105[12]; // [rsp+150h] [rbp-268h] BYREF
  char v106; // [rsp+1B0h] [rbp-208h]
  bool *v107; // [rsp+1C0h] [rbp-1F8h] BYREF
  unsigned int *v108; // [rsp+1C8h] [rbp-1F0h] BYREF
  unsigned int *v109; // [rsp+1D0h] [rbp-1E8h] BYREF
  struct _GUID *v110; // [rsp+1D8h] [rbp-1E0h] BYREF
  unsigned __int64 v111; // [rsp+1E0h] [rbp-1D8h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v112; // [rsp+1E8h] [rbp-1D0h] BYREF
  struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult **v113; // [rsp+1F0h] [rbp-1C8h]
  __int64 v114; // [rsp+1F8h] [rbp-1C0h] BYREF
  ULONGLONG TickCount64; // [rsp+200h] [rbp-1B8h] BYREF
  HSTRING p_SystemTimeAsFileTime; // [rsp+208h] [rbp-1B0h] BYREF
  __int64 v117; // [rsp+210h] [rbp-1A8h] BYREF
  char v118; // [rsp+218h] [rbp-1A0h]
  _BYTE v119[272]; // [rsp+230h] [rbp-188h] BYREF
  __int64 v120; // [rsp+340h] [rbp-78h]
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+0h]

  v112 = a5;
  v107 = a6;
  v110 = a7;
  v109 = a8;
  v108 = a9;
  v113 = a10;
  TbLogProvider::TokenBrokerInternalGetTokenSilentlyHelper::TokenBrokerInternalGetTokenSilentlyHelper((TbLogProvider::TokenBrokerInternalGetTokenSilentlyHelper *)v119);
  v80 = 0;
  v79 = 0;
  string = 0;
  std::make_unique<Windows::Internal::Security::Authentication::Web::CallerContext,,0>(&v77);
  TickCount64 = GetTickCount64();
  v114 = 0;
  v76 = 0;
  *v107 = 0;
  *v110 = 0;
  *v109 = -1;
  *v108 = -1;
  v105[0] = &string;
  v105[1] = &v114;
  v105[2] = v119;
  v105[3] = &v76;
  v105[4] = &v80;
  v105[5] = &v79;
  v105[6] = &v77;
  v105[7] = &TickCount64;
  v105[8] = &v110;
  v105[9] = &v107;
  v105[10] = &v109;
  v105[11] = &v108;
  v106 = 1;
  v83 = a4;
  v111 = 0;
  UserContextFromProvider = Windows::Internal::Security::Authentication::TokenBroker::GetUserContextFromProvider(
                              a5,
                              (struct Windows::Security::Credentials::IWebAccountProvider *)&v111,
                              v15);
  v17 = UserContextFromProvider;
  v76 = UserContextFromProvider;
  if ( UserContextFromProvider < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3FC,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)UserContextFromProvider,
      v69);
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&v83);
    v106 = 0;
    lambda_5bb326b50822b30315723074c6697d89_::operator()(v105);
    std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v77);
    if ( string )
      WindowsDeleteString(string);
    if ( v79 )
      WindowsDeleteString(v79);
    if ( v80 )
      WindowsDeleteString(v80);
LABEL_237:
    TbLogProvider::TokenBrokerInternalGetTokenSilentlyHelper::~TokenBrokerInternalGetTokenSilentlyHelper((TbLogProvider::TokenBrokerInternalGetTokenSilentlyHelper *)v119);
    return v17;
  }
  v18 = Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(v77, a11, v111, 1);
  v17 = v18;
  v76 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3FD,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)v18,
      v69);
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&v83);
    v106 = 0;
    lambda_5bb326b50822b30315723074c6697d89_::operator()(v105);
    std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v77);
    if ( string )
      WindowsDeleteString(string);
    if ( v79 )
      WindowsDeleteString(v79);
    if ( v80 )
      WindowsDeleteString(v80);
    goto LABEL_237;
  }
  TokenHandle = 0;
  v91 = 0;
  v19 = Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(
          &TokenHandle,
          *((_QWORD *)v77 + 2));
  v17 = v19;
  v76 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x400,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)v19,
      v69);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&v83);
    v106 = 0;
    lambda_5bb326b50822b30315723074c6697d89_::operator()(v105);
    std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v77);
    if ( string )
      WindowsDeleteString(string);
    if ( v79 )
      WindowsDeleteString(v79);
    if ( v80 )
      WindowsDeleteString(v80);
    goto LABEL_237;
  }
  if ( a1 )
    Windows::Internal::Security::Authentication::Web::PrimeTokenBrokerOnFirstInvocation(
      (Windows::Internal::Security::Authentication::Web *)*((unsigned int *)v77 + 6),
      v20);
  BuiltInProviderType = Windows::Internal::Security::Authentication::TokenBroker::PluginManager::GetBuiltInProviderType(a5);
  if ( BuiltInProviderType == 4 )
  {
    v76 = -2147024891;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x408,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)0x80070005LL,
      v69);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&v83);
    v106 = 0;
    lambda_5bb326b50822b30315723074c6697d89_::operator()(v105);
    std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v77);
    if ( string )
      WindowsDeleteString(string);
    if ( v79 )
      WindowsDeleteString(v79);
    if ( v80 )
      WindowsDeleteString(v80);
    TbLogProvider::TokenBrokerInternalGetTokenSilentlyHelper::~TokenBrokerInternalGetTokenSilentlyHelper((TbLogProvider::TokenBrokerInternalGetTokenSilentlyHelper *)v119);
    return 2147942405LL;
  }
  if ( BuiltInProviderType == 2 && (unsigned int)EnforceEdpForAad(*((void **)v77 + 39)) == -2147024540 )
  {
    v76 = -2147024540;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40B,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)0x80070164LL,
      v69);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&v83);
    v106 = 0;
    lambda_5bb326b50822b30315723074c6697d89_::operator()(v105);
    std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v77);
    if ( string )
      WindowsDeleteString(string);
    if ( v79 )
      WindowsDeleteString(v79);
    if ( v80 )
      WindowsDeleteString(v80);
    TbLogProvider::TokenBrokerInternalGetTokenSilentlyHelper::~TokenBrokerInternalGetTokenSilentlyHelper((TbLogProvider::TokenBrokerInternalGetTokenSilentlyHelper *)v119);
    return 2147942756LL;
  }
  memset(v102, 0, sizeof(v102));
  v103 = 0;
  v104 = 1;
  v82 = 0;
  v23 = Windows::Internal::Security::CPropertiesSerializer::InitializeFromBytes(
          (Windows::Internal::Security::CPropertiesSerializer *)v102,
          a3,
          a2);
  v17 = v23;
  v76 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40F,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)v23,
      v69);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
    Windows::Internal::Security::CPropertiesSerializer::~CPropertiesSerializer((Windows::Internal::Security::CPropertiesSerializer *)v102);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&v83);
    v106 = 0;
    lambda_5bb326b50822b30315723074c6697d89_::operator()(v105);
    std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v77);
    if ( string )
      WindowsDeleteString(string);
    if ( v79 )
      WindowsDeleteString(v79);
    if ( v80 )
      WindowsDeleteString(v80);
    goto LABEL_237;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v102);
  v82 = *(Windows::Internal::Security::Authentication::TokenBroker **)&v102[0];
  v76 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DelegatedTokenRequests>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DelegatedTokenRequests>::GetImpl'::`2'::impl)
    && Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer(v77) )
  {
    SystemTimeAsFileTime = 0;
    v88 = 0;
    v81 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v88);
    v25 = Windows::Internal::Security::Authentication::TokenBroker::DeSerializeWebTokenRequestFromValueSet(
            v82,
            (struct Windows::Foundation::Collections::IPropertySet *)&v88,
            v24);
    v17 = v25;
    v76 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41C,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
        (const char *)(unsigned int)v25,
        v69);
      _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v81);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v88);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
      Windows::Internal::Security::CPropertiesSerializer::~CPropertiesSerializer((Windows::Internal::Security::CPropertiesSerializer *)v102);
      Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
      Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&v83);
      v106 = 0;
      lambda_5bb326b50822b30315723074c6697d89_::operator()(v105);
      std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v77);
      if ( string )
        WindowsDeleteString(string);
      if ( v79 )
        WindowsDeleteString(v79);
      if ( v80 )
        WindowsDeleteString(v80);
      goto LABEL_237;
    }
    v26 = v88;
    v27 = **(__int64 (__fastcall ***)(unsigned __int8 *, GUID *, __int64 *))v88;
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v81);
    v28 = v27(v26, &GUID_c8423c1d_aa94_48ea_86e5_4502f998ab78, &v81);
    v17 = v28;
    v76 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41D,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
        (const char *)(unsigned int)v28,
        v69);
      _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v81);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v88);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
      Windows::Internal::Security::CPropertiesSerializer::~CPropertiesSerializer((Windows::Internal::Security::CPropertiesSerializer *)v102);
      Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
      Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&v83);
      v106 = 0;
      lambda_5bb326b50822b30315723074c6697d89_::operator()(v105);
      std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v77);
      if ( string )
        WindowsDeleteString(string);
      if ( v79 )
        WindowsDeleteString(v79);
      if ( v80 )
        WindowsDeleteString(v80);
      goto LABEL_237;
    }
    v29 = (*(__int64 (__fastcall **)(__int64, struct _FILETIME *))(*(_QWORD *)v81 + 48LL))(v81, &SystemTimeAsFileTime);
    v17 = v29;
    v76 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41E,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
        (const char *)(unsigned int)v29,
        v69);
      _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v81);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v88);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
      Windows::Internal::Security::CPropertiesSerializer::~CPropertiesSerializer((Windows::Internal::Security::CPropertiesSerializer *)v102);
      Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
      Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&v83);
      v106 = 0;
      lambda_5bb326b50822b30315723074c6697d89_::operator()(v105);
      std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v77);
      if ( string )
        WindowsDeleteString(string);
      if ( v79 )
        WindowsDeleteString(v79);
      if ( v80 )
        WindowsDeleteString(v80);
      goto LABEL_237;
    }
    if ( SystemTimeAsFileTime )
    {
      v30 = v77;
      v31 = (HSTRING *)Windows::Internal::StringReference::StringReference(
                         &p_SystemTimeAsFileTime,
                         L"delegatedTokenRequests");
      v32 = Windows::Internal::Security::Authentication::Web::CallerContext::VerifyCapability(v30, *v31);
      v17 = v32;
      v76 = v32;
      if ( v32 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x422,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
          (const char *)(unsigned int)v32,
          v69);
        _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v81);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v88);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
        Windows::Internal::Security::CPropertiesSerializer::~CPropertiesSerializer((Windows::Internal::Security::CPropertiesSerializer *)v102);
        Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
        Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&v83);
        v106 = 0;
        lambda_5bb326b50822b30315723074c6697d89_::operator()(v105);
        std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v77);
        if ( string )
          WindowsDeleteString(string);
        if ( v79 )
          WindowsDeleteString(v79);
        if ( v80 )
          WindowsDeleteString(v80);
        goto LABEL_237;
      }
    }
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v81);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v88);
  }
  v33 = (*(__int64 (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *, HSTRING *))(*(_QWORD *)a5 + 48LL))(
          a5,
          &v80);
  v17 = v33;
  v76 = v33;
  if ( v33 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x427,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)v33,
      v69);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
    Windows::Internal::Security::CPropertiesSerializer::~CPropertiesSerializer((Windows::Internal::Security::CPropertiesSerializer *)v102);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&v83);
    v106 = 0;
    lambda_5bb326b50822b30315723074c6697d89_::operator()(v105);
    std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v77);
    if ( string )
      WindowsDeleteString(string);
    if ( v79 )
      WindowsDeleteString(v79);
    if ( v80 )
      WindowsDeleteString(v80);
    goto LABEL_237;
  }
  v87 = 0;
  v34 = **(int (__fastcall ***)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *))a5;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
  if ( v34(a5, &GUID_4a01eb05_4e42_41d4_b518_e008a5163614, &v87) < 0
    || (*(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v87 + 56LL))(v87, &v79) < 0 )
  {
    Windows::Internal::String::Initialize((Windows::Internal::String *)&v79, L"NULL", 4u);
  }
  v86 = 0;
  v85 = 0;
  v84 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
  v36 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Authentication::Web::Core::WebTokenResponse,Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Authentication::Web::Core::WebTokenResponse *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::Web::Core::WebTokenResponse *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::Web::Core::WebTokenResponse *>,0>>(
          v35,
          &v86);
  v17 = v36;
  v76 = v36;
  if ( v36 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x436,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)v36,
      v69);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
    Windows::Internal::Security::CPropertiesSerializer::~CPropertiesSerializer((Windows::Internal::Security::CPropertiesSerializer *)v102);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&v83);
    v106 = 0;
    lambda_5bb326b50822b30315723074c6697d89_::operator()(v105);
    std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v77);
    if ( string )
      WindowsDeleteString(string);
    if ( v79 )
      WindowsDeleteString(v79);
    if ( v80 )
      WindowsDeleteString(v80);
    goto LABEL_237;
  }
  v37 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Authentication::Web::Core::WebTokenResponse *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::Web::Core::WebTokenResponse *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::Web::Core::WebTokenResponse *>,0>>::As<Windows::Foundation::Collections::IVector<Windows::Security::Authentication::Web::Core::WebTokenResponse *>>(
          &v86,
          &v85);
  v17 = v37;
  v76 = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x437,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)v37,
      v69);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
    Windows::Internal::Security::CPropertiesSerializer::~CPropertiesSerializer((Windows::Internal::Security::CPropertiesSerializer *)v102);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&v83);
    v106 = 0;
    lambda_5bb326b50822b30315723074c6697d89_::operator()(v105);
    std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v77);
    if ( string )
      WindowsDeleteString(string);
    if ( v79 )
      WindowsDeleteString(v79);
    if ( v80 )
      WindowsDeleteString(v80);
    goto LABEL_237;
  }
  Windows::Internal::String::Initialize((Windows::Internal::String *)&string, L"NULL", 4u);
  WindowsDeleteString(string);
  string = 0;
  PluginPFN = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetPluginPFN(
                v77,
                a5,
                &string);
  v17 = PluginPFN;
  if ( PluginPFN < 0 )
  {
    if ( PluginPFN != -2146893805 )
    {
      v76 = PluginPFN;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x43C,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
        (const char *)(unsigned int)PluginPFN,
        v69);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
      Windows::Internal::Security::CPropertiesSerializer::~CPropertiesSerializer((Windows::Internal::Security::CPropertiesSerializer *)v102);
      Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
      Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&v83);
      v106 = 0;
      lambda_5bb326b50822b30315723074c6697d89_::operator()(v105);
      std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v77);
      if ( string )
        WindowsDeleteString(string);
      if ( v79 )
        WindowsDeleteString(v79);
      if ( v80 )
        WindowsDeleteString(v80);
      goto LABEL_237;
    }
    v39 = TbLogProvider::Provider();
    if ( *(_DWORD *)v39 > 5u )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v39,
        word_180149C0A,
        v120 + 8,
        0);
    v40 = v85;
    v41 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v85 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
    v42 = v41(v40, &v84);
    v17 = v42;
    v76 = v42;
    if ( v42 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x447,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
        (const char *)(unsigned int)v42,
        v69);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
      Windows::Internal::Security::CPropertiesSerializer::~CPropertiesSerializer((Windows::Internal::Security::CPropertiesSerializer *)v102);
      Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
      Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&v83);
      v106 = 0;
      lambda_5bb326b50822b30315723074c6697d89_::operator()(v105);
      std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v77);
      if ( string )
        WindowsDeleteString(string);
      if ( v79 )
        WindowsDeleteString(v79);
      if ( v80 )
        WindowsDeleteString(v80);
      goto LABEL_237;
    }
    v81 = 0;
    SystemTimeAsFileTime = 0;
    v98 = 0;
    *(_QWORD *)v96 = 0;
    LODWORD(v88) = 4;
    v94 = v84;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
    v43 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Authentication::Web::Core::CWebTokenRequestResult,Windows::Security::Authentication::Web::Core::CWebTokenRequestResult,Windows::Foundation::Collections::IVectorView<Windows::Security::Authentication::Web::Core::WebTokenResponse *> *,enum Windows::Security::Authentication::Web::Core::WebTokenRequestStatus,std::nullptr_t,std::nullptr_t,std::nullptr_t,Windows::Security::Credentials::IWebAccountProvider * &>(
            (unsigned int)&v81,
            (unsigned int)&v94,
            (unsigned int)&v88,
            (unsigned int)v96,
            (__int64)&v98,
            (__int64)&SystemTimeAsFileTime,
            (__int64)&v112);
    v17 = v43;
    v76 = v43;
    if ( v43 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x451,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
        (const char *)(unsigned int)v43,
        v70);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
      Windows::Internal::Security::CPropertiesSerializer::~CPropertiesSerializer((Windows::Internal::Security::CPropertiesSerializer *)v102);
      Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
      Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&v83);
      v106 = 0;
      lambda_5bb326b50822b30315723074c6697d89_::operator()(v105);
      std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v77);
      if ( string )
        WindowsDeleteString(string);
      if ( v79 )
        WindowsDeleteString(v79);
      if ( v80 )
        WindowsDeleteString(v80);
      goto LABEL_237;
    }
    v44 = v81;
    v81 = 0;
    *v113 = (struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *)v44;
    wil::ActivityBase<TbLogProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v119);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
    Windows::Internal::Security::CPropertiesSerializer::~CPropertiesSerializer((Windows::Internal::Security::CPropertiesSerializer *)v102);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&v83);
    v106 = 0;
    lambda_5bb326b50822b30315723074c6697d89_::operator()(v105);
    std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v77);
    if ( string )
      WindowsDeleteString(string);
    if ( v79 )
      WindowsDeleteString(v79);
    if ( v80 )
      WindowsDeleteString(v80);
    goto LABEL_244;
  }
  v92 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v92);
  v71 = (int)v77;
  Buffer = Windows::Internal::Security::Authentication::TokenBroker::ActivateSilentlyAndGetBuffer(v82, a4, string, 1);
  v17 = Buffer;
  v76 = Buffer;
  if ( Buffer >= 0 )
  {
    if ( *v107 )
    {
      wil::ActivityBase<TbLogProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v119);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v92);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
      Windows::Internal::Security::CPropertiesSerializer::~CPropertiesSerializer((Windows::Internal::Security::CPropertiesSerializer *)v102);
      Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
      Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&v83);
      v106 = 0;
      lambda_5bb326b50822b30315723074c6697d89_::operator()(v105);
      std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v77);
      if ( string )
        WindowsDeleteString(string);
      if ( v79 )
        WindowsDeleteString(v79);
      if ( v80 )
        WindowsDeleteString(v80);
    }
    else
    {
      LODWORD(v95) = 0;
      v93 = 0;
      v98 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v93);
      CallingAppName = Windows::Internal::Security::Authentication::Web::CallerContext::GetCallingAppName(v77);
      v47 = Windows::Internal::Security::Authentication::TokenBroker::DeSerializeWebTokenResponsesWithStatus(
              CallingAppName,
              (__int64)&v95,
              (__int64)&v98,
              (__int64)&v93,
              (__int64)&v85);
      v17 = v47;
      v76 = v47;
      if ( v47 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x478,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
          (const char *)(unsigned int)v47,
          v72);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v93);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v92);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
        Windows::Internal::Security::CPropertiesSerializer::~CPropertiesSerializer((Windows::Internal::Security::CPropertiesSerializer *)v102);
        Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
        Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&v83);
        v106 = 0;
        lambda_5bb326b50822b30315723074c6697d89_::operator()(v105);
        std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v77);
        if ( string )
          WindowsDeleteString(string);
        if ( v79 )
          WindowsDeleteString(v79);
        if ( v80 )
          WindowsDeleteString(v80);
        goto LABEL_237;
      }
      v101 = 0;
      if ( v93 )
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v93 + 48LL))(v93, &v101);
      v48 = TbLogProvider::Provider();
      if ( *(_DWORD *)v48 <= 5u )
      {
        v50 = v95;
      }
      else
      {
        LODWORD(v88) = v101;
        v50 = v95;
        LODWORD(v81) = v95;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v48,
          (unsigned int)&dword_180149B64,
          v120 + 8,
          v49,
          (__int64)&v81,
          (__int64)&v88);
      }
      if ( v50 == 3 )
      {
        SystemTimeAsFileTime = 0;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        RoFileTimeToDateTime(SystemTimeAsFileTime, (struct Windows::Foundation::DateTime *)&v98);
        v98 += 1200000000;
      }
      v97 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v97);
      v52 = Windows::Internal::Security::Authentication::TokenBroker::SerializePropertySet(
              v82,
              (struct Windows::Foundation::Collections::IPropertySet *)&v97,
              v51);
      v17 = v52;
      v76 = v52;
      if ( v52 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x499,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
          (const char *)(unsigned int)v52,
          v72);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v97);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v93);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v92);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
        Windows::Internal::Security::CPropertiesSerializer::~CPropertiesSerializer((Windows::Internal::Security::CPropertiesSerializer *)v102);
        Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
        Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&v83);
        v106 = 0;
        lambda_5bb326b50822b30315723074c6697d89_::operator()(v105);
        std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v77);
        if ( string )
          WindowsDeleteString(string);
        if ( v79 )
          WindowsDeleteString(v79);
        if ( v80 )
          WindowsDeleteString(v80);
        goto LABEL_237;
      }
      v53 = v85;
      if ( v85 )
      {
        v54 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v85 + 64LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
        v55 = v54(v53, &v84);
        v17 = v55;
        v76 = v55;
        if ( v55 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x49E,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
            (const char *)(unsigned int)v55,
            v72);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v97);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v93);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v92);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
          Windows::Internal::Security::CPropertiesSerializer::~CPropertiesSerializer((Windows::Internal::Security::CPropertiesSerializer *)v102);
          Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
          Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&v83);
          v106 = 0;
          lambda_5bb326b50822b30315723074c6697d89_::operator()(v105);
          std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v77);
          if ( string )
            WindowsDeleteString(string);
          if ( v79 )
            WindowsDeleteString(v79);
          if ( v80 )
            WindowsDeleteString(v80);
          goto LABEL_237;
        }
      }
      *(_QWORD *)v99 = 0;
      v94 = 0;
      v81 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v94);
      Windows::Internal::Security::Authentication::Web::CallerContext::GetCallingAppName(v77);
      v56 = Windows::Internal::Security::Authentication::TokenBroker::DeSerializeWebTokenRequestResultOperationParamsFromValueSet(
              v82,
              (__int64)&v81);
      v17 = v56;
      v76 = v56;
      if ( v56 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4AA,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
          (const char *)(unsigned int)v56,
          v73);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v94);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v99);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v97);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v93);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v92);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
        Windows::Internal::Security::CPropertiesSerializer::~CPropertiesSerializer((Windows::Internal::Security::CPropertiesSerializer *)v102);
        Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
        Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&v83);
        v106 = 0;
        lambda_5bb326b50822b30315723074c6697d89_::operator()(v105);
        std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v77);
        if ( string )
          WindowsDeleteString(string);
        if ( v79 )
          WindowsDeleteString(v79);
        if ( v80 )
          WindowsDeleteString(v80);
        goto LABEL_237;
      }
      v58 = 0;
      *(_QWORD *)v96 = 0;
      v59 = v81;
      if ( v81 )
      {
        v60 = *(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v81 + 64LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v96);
        v61 = v60(v59, v96);
        v17 = v61;
        v76 = v61;
        if ( v61 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4AF,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
            (const char *)(unsigned int)v61,
            v73);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v96);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v94);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v99);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v97);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v93);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v92);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
          Windows::Internal::Security::CPropertiesSerializer::~CPropertiesSerializer((Windows::Internal::Security::CPropertiesSerializer *)v102);
          Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
          Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&v83);
          v106 = 0;
          lambda_5bb326b50822b30315723074c6697d89_::operator()(v105);
          std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v77);
          if ( string )
            WindowsDeleteString(string);
          if ( v79 )
            WindowsDeleteString(v79);
          if ( v80 )
            WindowsDeleteString(v80);
          goto LABEL_237;
        }
        v58 = v96[0];
      }
      SystemTimeAsFileTime = 0;
      LODWORD(v88) = 0;
      p_SystemTimeAsFileTime = (HSTRING)&SystemTimeAsFileTime;
      v117 = 0;
      v118 = 1;
      LOBYTE(v57) = 1;
      RequestHash = CreateRequestHash(v94, v58, v57, 0, (__int64)&v88, (__int64)&v117);
      v63 = RequestHash;
      if ( RequestHash < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4BB,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
          (const char *)(unsigned int)RequestHash,
          v74);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_SystemTimeAsFileTime);
      if ( v63 >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v99);
        BufferFromByteArray = Windows::Internal::Security::Authentication::TokenBroker::GetBufferFromByteArray(
                                *(Windows::Internal::Security::Authentication::TokenBroker **)&SystemTimeAsFileTime,
                                (unsigned __int8 *)(unsigned int)v88,
                                (unsigned int)v99,
                                v64);
        if ( BufferFromByteArray < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x4BF,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
            (const char *)(unsigned int)BufferFromByteArray,
            v74);
      }
      v66 = (void *)SystemTimeAsFileTime;
      SystemTimeAsFileTime = 0;
      if ( v66 )
        LocalFree(v66);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v96);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v94);
      v100 = 0;
      SystemTimeAsFileTime = 0;
      *(_QWORD *)v96 = v93;
      v94 = *(_QWORD *)v99;
      v81 = v84;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v100);
      v67 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Authentication::Web::Core::CWebTokenRequestResult,Windows::Security::Authentication::Web::Core::CWebTokenRequestResult,Windows::Foundation::Collections::IVectorView<Windows::Security::Authentication::Web::Core::WebTokenResponse *> *,enum Windows::Security::Authentication::Web::Core::WebTokenRequestStatus &,Windows::Storage::Streams::IBuffer *,Windows::Security::Authentication::Web::Core::IWebProviderError *,std::nullptr_t,Windows::Security::Credentials::IWebAccountProvider * &,Windows::Foundation::DateTime &>(
              (unsigned int)&v100,
              (unsigned int)&v81,
              (unsigned int)&v95,
              (unsigned int)&v94,
              (__int64)v96,
              (__int64)&SystemTimeAsFileTime,
              (__int64)&v112,
              (__int64)&v98);
      v17 = v67;
      v76 = v67;
      if ( v67 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4CB,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
          (const char *)(unsigned int)v67,
          v75);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v100);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v99);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v97);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v93);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v92);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
        Windows::Internal::Security::CPropertiesSerializer::~CPropertiesSerializer((Windows::Internal::Security::CPropertiesSerializer *)v102);
        Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
        Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&v83);
        v106 = 0;
        lambda_5bb326b50822b30315723074c6697d89_::operator()(v105);
        std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v77);
        if ( string )
          WindowsDeleteString(string);
        if ( v79 )
          WindowsDeleteString(v79);
        if ( v80 )
          WindowsDeleteString(v80);
        goto LABEL_237;
      }
      v68 = v100;
      v100 = 0;
      *v113 = v68;
      wil::ActivityBase<TbLogProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v119);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v100);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v99);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v97);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v93);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v92);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
      Windows::Internal::Security::CPropertiesSerializer::~CPropertiesSerializer((Windows::Internal::Security::CPropertiesSerializer *)v102);
      Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
      Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&v83);
      v106 = 0;
      lambda_5bb326b50822b30315723074c6697d89_::operator()(v105);
      std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v77);
      if ( string )
        WindowsDeleteString(string);
      if ( v79 )
        WindowsDeleteString(v79);
      if ( v80 )
        WindowsDeleteString(v80);
    }
LABEL_244:
    TbLogProvider::TokenBrokerInternalGetTokenSilentlyHelper::~TokenBrokerInternalGetTokenSilentlyHelper((TbLogProvider::TokenBrokerInternalGetTokenSilentlyHelper *)v119);
    return 0;
  }
  if ( Buffer != -805306268 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x465,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)Buffer,
      v71);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v92);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
    Windows::Internal::Security::CPropertiesSerializer::~CPropertiesSerializer((Windows::Internal::Security::CPropertiesSerializer *)v102);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&v83);
    v106 = 0;
    lambda_5bb326b50822b30315723074c6697d89_::operator()(v105);
    std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v77);
    if ( string )
      WindowsDeleteString(string);
    if ( v79 )
      WindowsDeleteString(v79);
    if ( v80 )
      WindowsDeleteString(v80);
    goto LABEL_237;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v92);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
  Windows::Internal::Security::CPropertiesSerializer::~CPropertiesSerializer((Windows::Internal::Security::CPropertiesSerializer *)v102);
  Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
  Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&v83);
  v106 = 0;
  lambda_5bb326b50822b30315723074c6697d89_::operator()(v105);
  std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v77);
  if ( string )
    WindowsDeleteString(string);
  if ( v79 )
    WindowsDeleteString(v79);
  if ( v80 )
    WindowsDeleteString(v80);
  TbLogProvider::TokenBrokerInternalGetTokenSilentlyHelper::~TokenBrokerInternalGetTokenSilentlyHelper((TbLogProvider::TokenBrokerInternalGetTokenSilentlyHelper *)v119);
  return 3489661028LL;
}

```

## disassembly

```asm
0x18005aa84  mov     r11, rsp
0x18005aa87  mov     [r11+8], rbx
0x18005aa8b  mov     [r11+20h], rsi
0x18005aa8f  push    rdi
0x18005aa90  push    r12
0x18005aa92  push    r13
0x18005aa94  push    r14
0x18005aa96  push    r15
0x18005aa98  sub     rsp, 390h
0x18005aa9f  mov     rax, cs:__security_cookie
0x18005aaa6  xor     rax, rsp
0x18005aaa9  mov     [rsp+3B8h+var_38], rax
0x18005aab1  mov     r13, r9
0x18005aab4  mov     r12, r8
0x18005aab7  mov     r15d, edx
0x18005aaba  mov     dil, cl
0x18005aabd  mov     rsi, [rsp+3B8h+arg_20]
0x18005aac5  mov     [r11-1D0h], rsi
0x18005aacc  mov     rax, [rsp+3B8h+arg_28]
0x18005aad4  mov     [r11-1F8h], rax
0x18005aadb  mov     rax, [rsp+3B8h+arg_30]
0x18005aae3  mov     [r11-1E0h], rax
0x18005aaea  mov     rax, [rsp+3B8h+arg_38]
0x18005aaf2  mov     [r11-1E8h], rax
0x18005aaf9  mov     rax, [rsp+3B8h+arg_40]
0x18005ab01  mov     [r11-1F0h], rax
0x18005ab08  mov     rax, [rsp+3B8h+arg_48]
0x18005ab10  mov     [rsp+3B8h+var_1C8], rax
0x18005ab18  mov     r14, [rsp+3B8h+arg_50]
0x18005ab20  lea     rcx, [r11-188h]; this
0x18005ab27  call    ??$?0$$V@TokenBrokerInternalGetTokenSilentlyHelper@TbLogProvider@@AEAA@U?$integral_constant@D$0A@@wistd@@@Z; TbLogProvider::TokenBrokerInternalGetTokenSilentlyHelper::TokenBrokerInternalGetTokenSilentlyHelper(wistd::integral_constant<char,0>)
0x18005ab2c  nop
0x18005ab2d  xor     ebx, ebx
0x18005ab2f  mov     [rsp+3B8h+var_348], rbx
0x18005ab34  mov     [rsp+3B8h+var_350], rbx
0x18005ab39  mov     [rsp+3B8h+string], rbx
0x18005ab3e  lea     rcx, [rsp+3B8h+var_360]
0x18005ab43  call    ??$make_unique@VCallerContext@Web@Authentication@Security@Internal@Windows@@$$V$0A@@std@@YA?AV?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@std@@@0@XZ; std::make_unique<Windows::Internal::Security::Authentication::Web::CallerContext,,0>(void)
0x18005ab48  nop
0x18005ab49  call    cs:__imp_GetTickCount64
0x18005ab4f  mov     [rsp+3B8h+var_1B8], rax
0x18005ab57  mov     [rsp+3B8h+var_1C0], rbx
0x18005ab5f  mov     [rsp+3B8h+var_368], ebx
0x18005ab63  mov     rax, [rsp+3B8h+var_1F8]
0x18005ab6b  mov     [rax], bl
0x18005ab6d  xorps   xmm0, xmm0
0x18005ab70  mov     rax, [rsp+3B8h+var_1E0]
0x18005ab78  movdqu  xmmword ptr [rax], xmm0
0x18005ab7c  or      ecx, 0FFFFFFFFh
0x18005ab7f  mov     rax, [rsp+3B8h+var_1E8]
0x18005ab87  mov     [rax], ecx
0x18005ab89  mov     rax, [rsp+3B8h+var_1F0]
0x18005ab91  mov     [rax], ecx
0x18005ab93  lea     rax, [rsp+3B8h+string]
0x18005ab98  mov     [rsp+3B8h+var_268], rax
0x18005aba0  lea     rax, [rsp+3B8h+var_1C0]
0x18005aba8  mov     [rsp+3B8h+var_260], rax
0x18005abb0  lea     rax, [rsp+3B8h+var_188]
0x18005abb8  mov     [rsp+3B8h+var_258], rax
0x18005abc0  lea     rax, [rsp+3B8h+var_368]
0x18005abc5  mov     [rsp+3B8h+var_250], rax
0x18005abcd  lea     rax, [rsp+3B8h+var_348]
0x18005abd2  mov     [rsp+3B8h+var_248], rax
0x18005abda  lea     rax, [rsp+3B8h+var_350]
0x18005abdf  mov     [rsp+3B8h+var_240], rax
0x18005abe7  lea     rax, [rsp+3B8h+var_360]
0x18005abec  mov     [rsp+3B8h+var_238], rax
0x18005abf4  lea     rax, [rsp+3B8h+var_1B8]
0x18005abfc  mov     [rsp+3B8h+var_230], rax
0x18005ac04  lea     rax, [rsp+3B8h+var_1E0]
0x18005ac0c  mov     [rsp+3B8h+var_228], rax
0x18005ac14  lea     rax, [rsp+3B8h+var_1F8]
0x18005ac1c  mov     [rsp+3B8h+var_220], rax
0x18005ac24  lea     rax, [rsp+3B8h+var_1E8]
0x18005ac2c  mov     [rsp+3B8h+var_218], rax
0x18005ac34  lea     rax, [rsp+3B8h+var_1F0]
0x18005ac3c  mov     [rsp+3B8h+var_210], rax
0x18005ac44  mov     [rsp+3B8h+var_208], 1
0x18005ac4c  mov     [rsp+3B8h+var_330], r13
0x18005ac54  mov     [rsp+3B8h+var_1D8], rbx
0x18005ac5c  lea     rdx, [rsp+3B8h+var_1D8]; struct Windows::Security::Credentials::IWebAccountProvider *
0x18005ac64  mov     rcx, rsi; this
0x18005ac67  call    ?GetUserContextFromProvider@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIWebAccountProvider@Credentials@35@AEA_K@Z; Windows::Internal::Security::Authentication::TokenBroker::GetUserContextFromProvider(Windows::Security::Credentials::IWebAccountProvider *,unsigned __int64 &)
0x18005ac6c  mov     ebx, eax
0x18005ac6e  mov     [rsp+3B8h+var_368], eax
0x18005ac72  test    eax, eax
0x18005ac74  jns     loc_18005AD0D
0x18005ac7a  mov     rcx, [rsp+3B8h]; this
0x18005ac82  mov     r9d, eax; char *
0x18005ac85  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18005ac8c  mov     edx, 3FCh; void *
0x18005ac91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ac96  nop
0x18005ac97  lea     rcx, [rsp+3B8h+var_330]; this
0x18005ac9f  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x18005aca4  nop
0x18005aca5  mov     [rsp+3B8h+var_208], 0
0x18005acad  lea     rcx, [rsp+3B8h+var_268]
0x18005acb5  call    _lambda_5bb326b50822b30315723074c6697d89___operator__
0x18005acba  nop
0x18005acbb  lea     rcx, [rsp+3B8h+var_360]
0x18005acc0  call    ??1?$_Temporary_owner@VCallerContext@Web@Authentication@Security@Internal@Windows@@@std@@QEAA@XZ; std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(void)
0x18005acc5  nop
0x18005acc6  mov     rcx, [rsp+3B8h+string]; string
0x18005accb  test    rcx, rcx
0x18005acce  jz      short loc_18005ACD7
0x18005acd0  call    cs:__imp_WindowsDeleteString
0x18005acd6  nop
0x18005acd7  mov     rcx, [rsp+3B8h+var_350]; string
0x18005acdc  test    rcx, rcx
0x18005acdf  jz      short loc_18005ACE8
0x18005ace1  call    cs:__imp_WindowsDeleteString
0x18005ace7  nop
0x18005ace8  mov     rcx, [rsp+3B8h+var_348]; string
0x18005aced  test    rcx, rcx
0x18005acf0  jz      short loc_18005ACF9
0x18005acf2  call    cs:__imp_WindowsDeleteString
0x18005acf8  nop
0x18005acf9  lea     rcx, [rsp+3B8h+var_188]; this
0x18005ad01  call    ??1TokenBrokerInternalGetTokenSilentlyHelper@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalGetTokenSilentlyHelper::~TokenBrokerInternalGetTokenSilentlyHelper(void)
0x18005ad06  mov     eax, ebx
0x18005ad08  jmp     loc_18005CF32
0x18005ad0d  mov     r9b, 1; bool
0x18005ad10  mov     r8, [rsp+3B8h+var_1D8]; unsigned __int64
0x18005ad18  mov     rdx, r14; struct IUnknown *
0x18005ad1b  mov     rcx, [rsp+3B8h+var_360]; this
0x18005ad20  call    ?Initialize@CallerContext@Web@Authentication@Security@Internal@Windows@@QEAAJPEAUIUnknown@@_K_N@Z; Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(IUnknown *,unsigned __int64,bool)
0x18005ad25  mov     ebx, eax
0x18005ad27  mov     [rsp+3B8h+var_368], eax
0x18005ad2b  xor     r14d, r14d
0x18005ad2e  test    eax, eax
0x18005ad30  jns     loc_18005ADC9
0x18005ad36  mov     rcx, [rsp+3B8h]; this
0x18005ad3e  mov     r9d, eax; char *
0x18005ad41  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18005ad48  mov     edx, 3FDh; void *
0x18005ad4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ad52  nop
0x18005ad53  lea     rcx, [rsp+3B8h+var_330]; this
0x18005ad5b  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x18005ad60  nop
0x18005ad61  mov     [rsp+3B8h+var_208], r14b
0x18005ad69  lea     rcx, [rsp+3B8h+var_268]
0x18005ad71  call    _lambda_5bb326b50822b30315723074c6697d89___operator__
0x18005ad76  nop
0x18005ad77  lea     rcx, [rsp+3B8h+var_360]
0x18005ad7c  call    ??1?$_Temporary_owner@VCallerContext@Web@Authentication@Security@Internal@Windows@@@std@@QEAA@XZ; std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(void)
0x18005ad81  nop
0x18005ad82  mov     rcx, [rsp+3B8h+string]; string
0x18005ad87  test    rcx, rcx
0x18005ad8a  jz      short loc_18005AD93
0x18005ad8c  call    cs:__imp_WindowsDeleteString
0x18005ad92  nop
0x18005ad93  mov     rcx, [rsp+3B8h+var_350]; string
0x18005ad98  test    rcx, rcx
0x18005ad9b  jz      short loc_18005ADA4
0x18005ad9d  call    cs:__imp_WindowsDeleteString
0x18005ada3  nop
0x18005ada4  mov     rcx, [rsp+3B8h+var_348]; string
0x18005ada9  test    rcx, rcx
0x18005adac  jz      short loc_18005ADB5
0x18005adae  call    cs:__imp_WindowsDeleteString
0x18005adb4  nop
0x18005adb5  lea     rcx, [rsp+3B8h+var_188]; this
0x18005adbd  call    ??1TokenBrokerInternalGetTokenSilentlyHelper@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalGetTokenSilentlyHelper::~TokenBrokerInternalGetTokenSilentlyHelper(void)
0x18005adc2  mov     eax, ebx
0x18005adc4  jmp     loc_18005CF32
0x18005adc9  mov     [rsp+3B8h+TokenHandle], r14
0x18005add1  mov     [rsp+3B8h+var_2F0], r14b
0x18005add9  mov     rdx, [rsp+3B8h+var_360]
0x18005adde  mov     rdx, [rdx+10h]; unsigned __int64
0x18005ade2  lea     rcx, [rsp+3B8h+TokenHandle]; TokenHandle
0x18005adea  call    ?Impersonate@ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAAJ_K@Z; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(unsigned __int64)
0x18005adef  mov     ebx, eax
0x18005adf1  mov     [rsp+3B8h+var_368], eax
0x18005adf5  test    eax, eax
0x18005adf7  jns     loc_18005AE9E
0x18005adfd  mov     rcx, [rsp+3B8h]; this
0x18005ae05  mov     r9d, eax; char *
0x18005ae08  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18005ae0f  mov     edx, 400h; void *
0x18005ae14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ae19  nop
0x18005ae1a  lea     rcx, [rsp+3B8h+TokenHandle]; this
0x18005ae22  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x18005ae27  nop
0x18005ae28  lea     rcx, [rsp+3B8h+var_330]; this
0x18005ae30  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x18005ae35  nop
0x18005ae36  mov     [rsp+3B8h+var_208], r14b
0x18005ae3e  lea     rcx, [rsp+3B8h+var_268]
0x18005ae46  call    _lambda_5bb326b50822b30315723074c6697d89___operator__
0x18005ae4b  nop
0x18005ae4c  lea     rcx, [rsp+3B8h+var_360]
0x18005ae51  call    ??1?$_Temporary_owner@VCallerContext@Web@Authentication@Security@Internal@Windows@@@std@@QEAA@XZ; std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(void)
0x18005ae56  nop
0x18005ae57  mov     rcx, [rsp+3B8h+string]; string
0x18005ae5c  test    rcx, rcx
0x18005ae5f  jz      short loc_18005AE68
0x18005ae61  call    cs:__imp_WindowsDeleteString
0x18005ae67  nop
0x18005ae68  mov     rcx, [rsp+3B8h+var_350]; string
0x18005ae6d  test    rcx, rcx
0x18005ae70  jz      short loc_18005AE79
0x18005ae72  call    cs:__imp_WindowsDeleteString
0x18005ae78  nop
0x18005ae79  mov     rcx, [rsp+3B8h+var_348]; string
0x18005ae7e  test    rcx, rcx
0x18005ae81  jz      short loc_18005AE8A
0x18005ae83  call    cs:__imp_WindowsDeleteString
0x18005ae89  nop
0x18005ae8a  lea     rcx, [rsp+3B8h+var_188]; this
0x18005ae92  call    ??1TokenBrokerInternalGetTokenSilentlyHelper@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalGetTokenSilentlyHelper::~TokenBrokerInternalGetTokenSilentlyHelper(void)
0x18005ae97  mov     eax, ebx
0x18005ae99  jmp     loc_18005CF32
0x18005ae9e  test    dil, dil
0x18005aea1  jz      short loc_18005AEB0
0x18005aea3  mov     rcx, [rsp+3B8h+var_360]
0x18005aea8  mov     ecx, [rcx+18h]; this
0x18005aeab  call    ?PrimeTokenBrokerOnFirstInvocation@Web@Authentication@Security@Internal@Windows@@YAXK@Z; Windows::Internal::Security::Authentication::Web::PrimeTokenBrokerOnFirstInvocation(ulong)
0x18005aeb0  mov     rcx, rsi
0x18005aeb3  call    ?GetBuiltInProviderType@PluginManager@TokenBroker@Authentication@Security@Internal@Windows@@SA?AW4BuiltInProviderType@23456@PEAUIWebAccountProvider@Credentials@46@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginManager::GetBuiltInProviderType(Windows::Security::Credentials::IWebAccountProvider *)
0x18005aeb8  cmp     eax, 4
0x18005aebb  jnz     loc_18005AF6B
0x18005aec1  mov     ebx, 80070005h
0x18005aec6  mov     [rsp+3B8h+var_368], ebx
0x18005aeca  mov     rcx, [rsp+3B8h]; this
0x18005aed2  mov     r9d, ebx; char *
0x18005aed5  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18005aedc  mov     edx, 408h; void *
0x18005aee1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005aee6  nop
0x18005aee7  lea     rcx, [rsp+3B8h+TokenHandle]; this
0x18005aeef  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x18005aef4  nop
0x18005aef5  lea     rcx, [rsp+3B8h+var_330]; this
0x18005aefd  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x18005af02  nop
0x18005af03  mov     [rsp+3B8h+var_208], r14b
0x18005af0b  lea     rcx, [rsp+3B8h+var_268]
0x18005af13  call    _lambda_5bb326b50822b30315723074c6697d89___operator__
0x18005af18  nop
0x18005af19  lea     rcx, [rsp+3B8h+var_360]
0x18005af1e  call    ??1?$_Temporary_owner@VCallerContext@Web@Authentication@Security@Internal@Windows@@@std@@QEAA@XZ; std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(void)
0x18005af23  nop
0x18005af24  mov     rcx, [rsp+3B8h+string]; string
0x18005af29  test    rcx, rcx
0x18005af2c  jz      short loc_18005AF35
0x18005af2e  call    cs:__imp_WindowsDeleteString
0x18005af34  nop
0x18005af35  mov     rcx, [rsp+3B8h+var_350]; string
0x18005af3a  test    rcx, rcx
0x18005af3d  jz      short loc_18005AF46
0x18005af3f  call    cs:__imp_WindowsDeleteString
0x18005af45  nop
0x18005af46  mov     rcx, [rsp+3B8h+var_348]; string
0x18005af4b  test    rcx, rcx
0x18005af4e  jz      short loc_18005AF57
0x18005af50  call    cs:__imp_WindowsDeleteString
0x18005af56  nop
0x18005af57  lea     rcx, [rsp+3B8h+var_188]; this
0x18005af5f  call    ??1TokenBrokerInternalGetTokenSilentlyHelper@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalGetTokenSilentlyHelper::~TokenBrokerInternalGetTokenSilentlyHelper(void)
0x18005af64  mov     eax, ebx
0x18005af66  jmp     loc_18005CF32
0x18005af6b  cmp     eax, 2
0x18005af6e  jnz     loc_18005B037
0x18005af74  mov     rcx, [rsp+3B8h+var_360]
0x18005af79  mov     rcx, [rcx+138h]; void *
0x18005af80  call    ?EnforceEdpForAad@@YAJPEAX@Z; EnforceEdpForAad(void *)
0x18005af85  mov     ebx, 80070164h
0x18005af8a  cmp     eax, ebx
0x18005af8c  jnz     loc_18005B037
0x18005af92  mov     [rsp+3B8h+var_368], ebx
0x18005af96  mov     rcx, [rsp+3B8h]; this
0x18005af9e  mov     r9d, ebx; char *
0x18005afa1  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18005afa8  mov     edx, 40Bh; void *
0x18005afad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005afb2  nop
0x18005afb3  lea     rcx, [rsp+3B8h+TokenHandle]; this
0x18005afbb  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x18005afc0  nop
0x18005afc1  lea     rcx, [rsp+3B8h+var_330]; this
0x18005afc9  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x18005afce  nop
0x18005afcf  mov     [rsp+3B8h+var_208], r14b
0x18005afd7  lea     rcx, [rsp+3B8h+var_268]
0x18005afdf  call    _lambda_5bb326b50822b30315723074c6697d89___operator__
0x18005afe4  nop
0x18005afe5  lea     rcx, [rsp+3B8h+var_360]
0x18005afea  call    ??1?$_Temporary_owner@VCallerContext@Web@Authentication@Security@Internal@Windows@@@std@@QEAA@XZ; std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(void)
0x18005afef  nop
0x18005aff0  mov     rcx, [rsp+3B8h+string]; string
0x18005aff5  test    rcx, rcx
0x18005aff8  jz      short loc_18005B001
0x18005affa  call    cs:__imp_WindowsDeleteString
0x18005b000  nop
0x18005b001  mov     rcx, [rsp+3B8h+var_350]; string
0x18005b006  test    rcx, rcx
0x18005b009  jz      short loc_18005B012
  ... truncated ...
```
