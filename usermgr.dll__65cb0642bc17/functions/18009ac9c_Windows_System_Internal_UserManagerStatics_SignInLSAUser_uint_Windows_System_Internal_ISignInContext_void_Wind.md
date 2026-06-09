# Windows::System::Internal::UserManagerStatics::SignInLSAUser(uint,Windows::System::Internal::ISignInContext *,void *,Windows::System::IUser * *,Windows::System::Internal::ISignInResult * *)

- ea: `0x18009ac9c`
- end: `0x18009e474`
- name: `?SignInLSAUser@UserManagerStatics@Internal@System@Windows@@AEAAJIPEAUISignInContext@234@PEAXPEAPEAUIUser@34@PEAPEAUISignInResult@234@@Z`
- size: `14296`
- prototype: `__int64 __usercall@<rax>(Windows::System::Internal::UserManagerStatics *__hidden this@<rcx>, unsigned int@<edx>, struct Windows::System::Internal::ISignInContext *@<r8>, void *@<r9>, struct Windows::System::IUser **, struct Windows::System::Internal::ISignInResult **)`
- caller_count: `1`
- callee_count: `56`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18009a4ec`

## callees

- `0x180002c18`
- `0x180006130`
- `0x180007920`
- `0x1800088e8`
- `0x18000acdc`
- `0x18000ce48`
- `0x18000ed00`
- `0x180012890`
- `0x1800179c0`
- `0x1800181f0`
- `0x180024828`
- `0x18002618c`
- `0x180026d04`
- `0x18003329c`
- `0x1800332e8`
- `0x18003561c`
- `0x180037e98`
- `0x180037ee4`
- `0x18003fdb4`
- `0x180041bb0`
- `0x180044f08`
- `0x18004b3d0`
- `0x18004ba28`
- `0x18004e58c`
- `0x18004e77c`
- `0x18004fb70`
- `0x18004fc2c`
- `0x180050c38`
- `0x1800513d0`
- `0x1800547e0`
- `0x180060700`
- `0x1800610f8`
- `0x1800624bc`
- `0x1800653a8`
- `0x18006f1c9`
- `0x180084f0c`
- `0x180084fac`
- `0x180086bcc`
- `0x180089ec8`
- `0x18008a478`
- `0x18008c534`
- `0x18008cb8c`
- `0x180094ff4`
- `0x180096a9c`
- `0x18009ac9c`
- `0x1800a3bf8`
- `0x1800a3e0c`
- `0x1800a6828`
- `0x1800a6e38`
- `0x1800a6ec0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18009b7e7`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009b814`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009bb34`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009bb61`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009bdd1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009bdfe`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009c628`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009c655`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009c9b3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009c9e0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009cc6b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009cc98`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009d652`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009d67f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009dacd`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009dafa`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009ded6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009defd`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009b7e7`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009b814`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009bb34`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009bb61`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009bdd1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009bdfe`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009c628`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009c655`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009c9b3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009c9e0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009cc6b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009cc98`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009d652`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009d67f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009dacd`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009dafa`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009ded6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009defd`
- `msvcrt!_wcsicmp` at `0x18009b339`
- `msvcrt!_wcsicmp` at `0x18009b339`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009b666`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009b666`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18009ba5d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18009bd1d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18009ba5d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18009bd1d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18009d3c2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18009d3c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009b31a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009b32d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009b6ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009bccb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009c236`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009d9ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009da37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009b31a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009b32d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009b6ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009bccb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009c236`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009d9ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009da37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b0cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b136`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b1a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b35d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b3e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b4ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b550`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b563`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b852`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b8d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b8eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b99e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009baf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009bb9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009bc25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009bc38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009bd95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009be3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009bec2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009bed5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009bff5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c099`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c13c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c14c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c316`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c35d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c534`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c54a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c560`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c576`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c58c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c59f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c5b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c5ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c693`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c719`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c72c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c846`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c8bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c8d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c8eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c901`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c917`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c92a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c93d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c977`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ca1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009caa4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cab7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cb05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cb77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cb8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cba3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cbb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cbcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cbe2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cbf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cc2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ccd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cd5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cd6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ce73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cf61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d04f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d129`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d1e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d29e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d2b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d2ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d2e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d2f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d309`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d31c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d6bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d743`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d756`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009db38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009dbbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009dbd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009df28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009dfae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009dfc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b0cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b136`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b1a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b35d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b3e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b4ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b550`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b563`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b852`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b8d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b8eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b99e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009baf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009bb9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009bc25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009bc38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009bd95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009be3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009bec2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009bed5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009bff5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c099`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c13c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c14c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c316`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c35d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c534`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c54a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c560`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c576`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c58c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c59f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c5b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c5ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c693`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c719`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c72c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c846`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c8bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c8d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c8eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c901`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c917`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c92a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c93d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c977`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ca1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009caa4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cab7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cb05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cb77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cb8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cba3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cbb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cbcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cbe2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cbf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cc2f`

## string_xrefs

- `0x18009e02d`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e041`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e055`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e069`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e07d`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e091`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e0a5`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e0b9`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e0cd`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e0e1`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e0f5`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e109`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e11d`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e131`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e148`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e15c`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e170`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e184`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e198`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e1ac`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e1c1`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e1d2`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e1e6`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e1fa`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e20b`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e21f`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e234`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e249`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e25e`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e272`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e286`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e29b`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e2b0`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e2c5`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e2da`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e2ef`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e304`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e319`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e32e`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e343`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e358`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e36d`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e382`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e397`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e3ab`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e3bf`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e3d4`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e3e8`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e3fc`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e410`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e425`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e439`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e44d`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009e461`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009c081`: `onecore\ds\security\umstartup\usermgr\lib\signinresult.cpp`
- `0x18009c125`: `onecore\ds\security\umstartup\usermgr\lib\signinresult.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=49 #try_helpers=1
__int64 __fastcall Windows::System::Internal::UserManagerStatics::SignInLSAUser(
        Windows::System::Internal::UserManagerStatics *this,
        unsigned int a2,
        struct Windows::System::Internal::ISignInContext *a3,
        void *a4,
        struct Windows::System::IUser **a5,
        struct Windows::System::Internal::ISignInResult **a6)
{
  Windows::System::Internal::UserManagerStatics *v7; // rsi
  struct Windows::System::Internal::ISignInResult **v8; // rax
  char v9; // r13
  void (__fastcall *v10)(void *, __int64 *); // rbx
  void (__fastcall *v11)(void *, __int64 *); // rbx
  void (__fastcall *v12)(void *, __int64 *); // rbx
  int v13; // r8d
  int v14; // r9d
  char v15; // r12
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, _QWORD, struct Windows::System::Internal::IUserProfile **); // rbx
  int v19; // eax
  struct Windows::System::Internal::IUserProfile *v20; // rdi
  __int64 (__fastcall *v21)(struct Windows::System::Internal::IUserProfile *, HSTRING *); // rbx
  int v22; // eax
  int v23; // eax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, HSTRING *); // rbx
  int v26; // eax
  int v27; // eax
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, HSTRING *); // rbx
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *UserStaticsInternal; // rcx
  int v35; // eax
  int v36; // eax
  const wchar_t *StringRawBuffer; // rbx
  const wchar_t *v38; // rax
  __int64 v39; // rdi
  int (__fastcall *v40)(__int64, HSTRING *); // rbx
  int v41; // eax
  int v42; // eax
  __int64 v43; // rdi
  int (__fastcall *v44)(__int64, HSTRING, HSTRING *); // rbx
  void (__fastcall *v45)(struct Windows::System::Internal::ISignInContext *, __int64 *); // rbx
  bool v47; // bl
  const struct _tlgProvider_t *v48; // rax
  int v49; // r8d
  int v50; // r9d
  HSTRING *v51; // rdi
  HSTRING *v52; // r12
  void *v53; // r13
  __int64 v54; // rbx
  unsigned int v55; // ebx
  const unsigned __int16 *v56; // rax
  int v57; // eax
  Windows::System::Internal::UserManagerStatics *v58; // rcx
  int v59; // eax
  int v60; // eax
  int v61; // eax
  Windows::System::Internal::UserManagerStatics *v62; // rcx
  __int64 v63; // rcx
  void *v64; // rbx
  __int64 (__fastcall ****j)(_QWORD, GUID *, __int64); // rbx
  int v66; // eax
  Windows::System::Internal::UserManagerStatics *v67; // rcx
  __int64 v68; // rsi
  int (__fastcall *v69)(__int64, HANDLE, HSTRING *); // rbx
  HSTRING v70; // r8
  int v71; // eax
  const char *v72; // r9
  int v73; // eax
  __int64 v74; // rcx
  const unsigned __int16 *v75; // rax
  int v76; // eax
  const char *v77; // r9
  int v78; // eax
  HSTRING *v79; // rsi
  int v80; // eax
  int v81; // eax
  int v82; // eax
  int v83; // eax
  int v84; // eax
  HSTRING *v85; // rbx
  __int64 v86; // r8
  const unsigned __int16 *v87; // r8
  int v88; // eax
  int v89; // r8d
  int v90; // ecx
  unsigned __int8 v91; // al
  int v92; // edx
  int v93; // esi
  int v94; // eax
  struct Windows::System::Internal::IUserProfile *v95; // rsi
  __int64 (__fastcall *v96)(struct Windows::System::Internal::IUserProfile *, HSTRING *); // rbx
  int v97; // eax
  int v98; // eax
  int v99; // eax
  int v100; // eax
  HSTRING v101; // rbx
  int v102; // eax
  HSTRING v103; // rbx
  int v104; // eax
  int v105; // eax
  HSTRING v106; // rbx
  int v107; // eax
  int v108; // eax
  HSTRING v109; // rbx
  int v110; // eax
  int v111; // eax
  HSTRING v112; // rbx
  int v113; // eax
  HSTRING v114; // rbx
  int v115; // eax
  HSTRING v116; // rbx
  int v117; // eax
  int v118; // eax
  unsigned int v119; // esi
  int v120; // eax
  int v121; // edx
  Windows::System::Internal::UserManagerStatics *v122; // rcx
  int v123; // eax
  int v124; // eax
  int v125; // edx
  int v126; // eax
  unsigned int v127; // ebx
  int v128; // eax
  Windows::System::Internal::UserManagerStatics *v129; // r14
  char v130; // si
  int v131; // eax
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *v132; // rax
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *v133; // rax
  __int64 v134; // r8
  int v135; // eax
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *v136; // rax
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *v137; // rax
  int v138; // eax
  int v139; // eax
  int v140; // eax
  void *v141; // r14
  __int64 (__fastcall *v142)(void *, PCWSTR, HSTRING); // rsi
  HSTRING v143; // rbx
  PCWSTR v144; // rax
  int v145; // eax
  const struct _tlgProvider_t *v146; // rbx
  int v147; // r8d
  int v148; // r9d
  int v149; // r9d
  HSTRING v150; // r13
  __int64 (__fastcall *v151)(HSTRING, struct Windows::System::Internal::ISignInContext *, HSTRING *); // rsi
  int v152; // eax
  __int64 v153; // r8
  int v154; // esi
  __int64 v155; // rsi
  HSTRING *v156; // rcx
  __int64 i; // rax
  unsigned int v158; // eax
  int TokenType; // [rsp+20h] [rbp-768h]
  int TokenTypea; // [rsp+20h] [rbp-768h]
  int TokenTypeb; // [rsp+20h] [rbp-768h]
  _BYTE *TokenTypec; // [rsp+20h] [rbp-768h]
  int TokenTyped; // [rsp+20h] [rbp-768h]
  unsigned __int8 v164; // [rsp+50h] [rbp-738h] BYREF
  char v165; // [rsp+51h] [rbp-737h] BYREF
  HSTRING string; // [rsp+58h] [rbp-730h] BYREF
  HSTRING phNewToken; // [rsp+60h] [rbp-728h] BYREF
  unsigned int v168; // [rsp+68h] [rbp-720h] BYREF
  HSTRING v169; // [rsp+70h] [rbp-718h] BYREF
  HSTRING v170; // [rsp+78h] [rbp-710h] BYREF
  bool v171; // [rsp+80h] [rbp-708h]
  char v172; // [rsp+81h] [rbp-707h] BYREF
  bool IsConnectedToXboxLive; // [rsp+82h] [rbp-706h]
  HSTRING v174; // [rsp+88h] [rbp-700h] BYREF
  HSTRING newString; // [rsp+90h] [rbp-6F8h] BYREF
  int v176[2]; // [rsp+98h] [rbp-6F0h] BYREF
  HSTRING v177; // [rsp+A0h] [rbp-6E8h] BYREF
  HSTRING v178; // [rsp+A8h] [rbp-6E0h] BYREF
  char v179; // [rsp+B0h] [rbp-6D8h] BYREF
  char v180; // [rsp+B1h] [rbp-6D7h] BYREF
  char v181; // [rsp+B2h] [rbp-6D6h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v182; // [rsp+B8h] [rbp-6D0h] BYREF
  Windows::System::Internal::SignInResult *v183; // [rsp+C0h] [rbp-6C8h] BYREF
  HSTRING v184; // [rsp+C8h] [rbp-6C0h] BYREF
  HSTRING v185; // [rsp+D0h] [rbp-6B8h] BYREF
  int v186; // [rsp+D8h] [rbp-6B0h] BYREF
  int v187; // [rsp+DCh] [rbp-6ACh] BYREF
  HSTRING v188; // [rsp+E0h] [rbp-6A8h] BYREF
  struct Windows::System::Internal::IUserProfile *v189; // [rsp+E8h] [rbp-6A0h] BYREF
  HSTRING v190; // [rsp+F0h] [rbp-698h] BYREF
  __int64 v191; // [rsp+F8h] [rbp-690h] BYREF
  unsigned int v192; // [rsp+100h] [rbp-688h] BYREF
  __int64 v193; // [rsp+108h] [rbp-680h] BYREF
  struct Windows::System::Internal::SignInResult *v194; // [rsp+110h] [rbp-678h] BYREF
  __int64 v195; // [rsp+118h] [rbp-670h] BYREF
  int v196; // [rsp+120h] [rbp-668h] BYREF
  __int64 v197; // [rsp+128h] [rbp-660h] BYREF
  __int64 (__fastcall ***v198)(_QWORD, GUID *, __int64); // [rsp+130h] [rbp-658h] BYREF
  __int64 v199; // [rsp+138h] [rbp-650h] BYREF
  __int64 v200; // [rsp+140h] [rbp-648h] BYREF
  HSTRING v201; // [rsp+148h] [rbp-640h] BYREF
  HSTRING v202; // [rsp+150h] [rbp-638h] BYREF
  __int64 v203; // [rsp+158h] [rbp-630h] BYREF
  __int64 v204; // [rsp+160h] [rbp-628h] BYREF
  __int128 v205; // [rsp+168h] [rbp-620h] BYREF
  HSTRING *v206; // [rsp+178h] [rbp-610h]
  __int128 v207; // [rsp+180h] [rbp-608h] BYREF
  __int64 v208; // [rsp+190h] [rbp-5F8h]
  HANDLE hExistingToken; // [rsp+198h] [rbp-5F0h] BYREF
  Windows::System::Internal::UserManagerStatics *v210; // [rsp+1A0h] [rbp-5E8h]
  void *v211; // [rsp+1A8h] [rbp-5E0h] BYREF
  int v212; // [rsp+1B0h] [rbp-5D8h] BYREF
  int v213; // [rsp+1B4h] [rbp-5D4h] BYREF
  HSTRING v214; // [rsp+1B8h] [rbp-5D0h] BYREF
  HSTRING v215; // [rsp+1C0h] [rbp-5C8h] BYREF
  DWORD TickCount; // [rsp+1C8h] [rbp-5C0h] BYREF
  struct Windows::System::Internal::ISignInResult **v217; // [rsp+1D0h] [rbp-5B8h] BYREF
  void *v218; // [rsp+1D8h] [rbp-5B0h] BYREF
  WCHAR *v219; // [rsp+1E0h] [rbp-5A8h] BYREF
  _QWORD v220[13]; // [rsp+1F0h] [rbp-598h] BYREF
  char v221; // [rsp+258h] [rbp-530h]
  struct Windows::System::Internal::ISignInContext *v222; // [rsp+260h] [rbp-528h]
  _OWORD v223[3]; // [rsp+268h] [rbp-520h] BYREF
  __int64 v224; // [rsp+298h] [rbp-4F0h]
  HSTRING_HEADER hstringHeader; // [rsp+2A0h] [rbp-4E8h] BYREF
  __int64 v226; // [rsp+2B8h] [rbp-4D0h]
  HSTRING *v227; // [rsp+2C0h] [rbp-4C8h]
  __int64 v228; // [rsp+2C8h] [rbp-4C0h]
  HSTRING *v229; // [rsp+2D0h] [rbp-4B8h]
  __int64 v230; // [rsp+2D8h] [rbp-4B0h]
  _BYTE v231[16]; // [rsp+2E0h] [rbp-4A8h] BYREF
  HSTRING *v232; // [rsp+2F0h] [rbp-498h]
  __int64 v233; // [rsp+2F8h] [rbp-490h]
  HSTRING *v234; // [rsp+300h] [rbp-488h]
  __int64 v235; // [rsp+308h] [rbp-480h]
  HSTRING *v236; // [rsp+310h] [rbp-478h]
  __int64 v237; // [rsp+318h] [rbp-470h]
  HSTRING *v238; // [rsp+320h] [rbp-468h]
  __int64 v239; // [rsp+328h] [rbp-460h]
  unsigned __int16 v240[520]; // [rsp+330h] [rbp-458h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+788h] [rbp+0h]

  v211 = a4;
  v7 = this;
  v210 = this;
  v168 = a2;
  v222 = a3;
  v219 = (WCHAR *)a5;
  v8 = a6;
  v217 = a6;
  if ( !a5 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v8 = v217;
  }
  if ( !v8 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v186 = 0;
  LODWORD(v184) = 0;
  *(_QWORD *)v176 = 0;
  v172 = 0;
  v191 = 0;
  v183 = 0;
  v194 = 0;
  string = 0;
  v178 = 0;
  v200 = 0;
  v195 = 0;
  v199 = 0;
  v189 = 0;
  v193 = 0;
  v198 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))a3;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v198);
  v204 = 0;
  v203 = 0;
  v174 = 0;
  v212 = 0;
  v213 = 0;
  v182 = 0;
  v218 = (void *)-1LL;
  memset_0(v240, 0, 0x402u);
  hExistingToken = (HANDLE)-1LL;
  memset(v223, 0, sizeof(v223));
  v224 = 0;
  v9 = 0;
  v165 = 0;
  v192 = 0;
  TickCount = GetTickCount();
  v179 = 0;
  v197 = 0;
  v181 = 0;
  v205 = 0;
  v206 = 0;
  v207 = 0;
  v208 = 0;
  v10 = *(void (__fastcall **)(void *, __int64 *))(Windows::System::Internal::Adapters::g_AdapterCollection + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v200);
  v10(&Windows::System::Internal::Adapters::g_AdapterCollection, &v200);
  v11 = *(void (__fastcall **)(void *, __int64 *))(Windows::System::Internal::Adapters::g_AdapterCollection + 24LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v195);
  v11(&Windows::System::Internal::Adapters::g_AdapterCollection, &v195);
  v12 = *(void (__fastcall **)(void *, __int64 *))(Windows::System::Internal::Adapters::g_AdapterCollection + 88LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v199);
  v12(&Windows::System::Internal::Adapters::g_AdapterCollection, &v199);
  v196 = 0;
  if ( a3 )
    (*(void (__fastcall **)(struct Windows::System::Internal::ISignInContext *, int *))(*(_QWORD *)a3 + 64LL))(
      a3,
      &v196);
  if ( (unsigned int)dword_180146228 > 4 )
  {
    LODWORD(v170) = v196;
    LODWORD(v177) = v168;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180146228,
      (unsigned int)byte_1801261D3,
      v13,
      v14,
      (__int64)&v177,
      (__int64)&v170);
  }
  v220[0] = &v165;
  v220[1] = &hExistingToken;
  v220[2] = &v183;
  v220[3] = &v186;
  v220[4] = &v217;
  v220[5] = &TickCount;
  v220[6] = &v178;
  v220[7] = &v168;
  v220[8] = &v181;
  v220[9] = v7;
  v220[10] = v223;
  v220[11] = &v195;
  v220[12] = &v218;
  v15 = 1;
  v221 = 1;
  *a5 = 0;
  *v217 = 0;
  v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v7 + 67) + 120LL))(*((_QWORD *)v7 + 67), v168);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC9A,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v16,
      TokenTypea);
  v17 = *((_QWORD *)v7 + 67);
  v18 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::System::Internal::IUserProfile **))(*(_QWORD *)v17 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v189);
  v19 = v18(v17, v168, &v189);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC9B,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v19,
      TokenTypea);
  v20 = v189;
  v21 = *(__int64 (__fastcall **)(struct Windows::System::Internal::IUserProfile *, HSTRING *))(*(_QWORD *)v189 + 64LL);
  WindowsDeleteString(string);
  string = 0;
  v22 = v21(v20, &string);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC9C,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v22,
      TokenTypea);
  v23 = Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>::As<Windows::System::Internal::Implementation::IUserProfileInternal>(
          (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v189,
          (__int64)&v193);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC9D,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v23,
      TokenTypea);
  v24 = v193;
  v25 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v193 + 48LL);
  WindowsDeleteString(v174);
  v174 = 0;
  v26 = v25(v24, &v174);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC9E,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v26,
      TokenTypea);
  v27 = Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInContext>::As<Windows::System::Internal::ISignInContext2>(
          &v198,
          (__int64)&v204);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCA2,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v27,
      TokenTypea);
  v28 = v204;
  v29 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v204 + 48LL);
  WindowsDeleteString(v178);
  v178 = 0;
  v30 = v29(v28, &v178);
  if ( v30 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCA3,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v30,
      TokenTypea);
  v169 = v178;
  phNewToken = v174;
  v31 = Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::SignInResult,Windows::System::Internal::SignInResult,unsigned int &,HSTRING__ *,enum Windows::System::Internal::SignInCaller &,HSTRING__ *>(
          (unsigned int)&v183,
          (unsigned int)&v168,
          (unsigned int)&phNewToken,
          (unsigned int)&v196,
          (__int64)&v169);
  if ( v31 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCA6,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v31,
      TokenTypeb);
  v32 = Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInContext>::As<Windows::System::Internal::Implementation::ISignInContextPrivate>(
          &v198,
          (__int64)&v203);
  if ( v32 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCAA,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v32,
      TokenTypeb);
  v33 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v203 + 48LL))(v203, &v192);
  if ( v33 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCAB,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v33,
      TokenTypeb);
  UserStaticsInternal = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(v7);
  TokenTypec = v176;
  v35 = (*(__int64 (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, _QWORD, char *))(*(_QWORD *)UserStaticsInternal + 136LL))(
          UserStaticsInternal,
          v168,
          v192,
          &v172);
  if ( v35 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCAE,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v35,
      (int)v176);
  if ( *(_QWORD *)v176 )
  {
    LODWORD(newString) = 0;
    v36 = (*(__int64 (__fastcall **)(_QWORD, HSTRING *))(**(_QWORD **)v176 + 56LL))(*(_QWORD *)v176, &newString);
    if ( v36 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCB6,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v36,
        (int)v176);
    if ( (_DWORD)newString == 1 )
    {
      if ( string )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v38 = WindowsGetStringRawBuffer(v174, 0);
        if ( !_wcsicmp(v38, StringRawBuffer) )
          goto LABEL_31;
        goto LABEL_30;
      }
      v39 = v193;
      v40 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v193 + 96LL);
      WindowsDeleteString(0);
      string = 0;
      if ( v40(v39, &string) >= 0 )
        goto LABEL_30;
      v169 = 0;
      v41 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
              (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v176,
              &v191);
      if ( v41 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xCC1,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v41,
          (int)v176);
      v42 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v191 + 80LL))(v191, &v169);
      if ( v42 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xCC2,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v42,
          (int)v176);
      v43 = v193;
      v44 = *(int (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)v193 + 104LL);
      WindowsDeleteString(string);
      string = 0;
      if ( v44(v43, v169, &string) >= 0 )
LABEL_30:
        v165 = 1;
    }
LABEL_31:
    if ( (_DWORD)newString == 2 || !v165 )
    {
      v45 = *(void (__fastcall **)(struct Windows::System::Internal::ISignInContext *, __int64 *))(*(_QWORD *)a3 + 112LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v197);
      v45(a3, &v197);
      (*(void (__fastcall **)(struct Windows::System::Internal::IUserProfile *, char *))(*(_QWORD *)v189 + 80LL))(
        v189,
        &v179);
      if ( !v179 || v197 )
        v15 = 0;
      if ( !v15 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xCD7,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)0x80A20303LL,
          (int)v176);
      v221 = 0;
      lambda_a3b0c7a60547604949e16553c62274b5_::operator()(v220);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v197);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v182);
      WindowsDeleteString(v174);
      v174 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v203);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v204);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v198);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v193);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v189);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v199);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v195);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v200);
      WindowsDeleteString(v178);
      v178 = 0;
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v194);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v183);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v191);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v176);
      return 0;
    }
    goto LABEL_40;
  }
  v9 = 1;
  if ( v165 )
  {
LABEL_40:
    v47 = 1;
    goto LABEL_41;
  }
  v47 = string != 0;
LABEL_41:
  v171 = v47;
  IsConnectedToXboxLive = Windows::System::Internal::UserManagerStatics::IsConnectedToXboxLive(v7);
  if ( !v9 && !v47 )
  {
    v48 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v48 > 4u )
    {
      LODWORD(v170) = 0;
      LODWORD(v177) = v196;
      v187 = v168;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v48,
        (unsigned int)word_180126142,
        v49,
        v50,
        (__int64)&v187,
        (__int64)&v177,
        (__int64)&v170);
    }
    v51 = (HSTRING *)*((_QWORD *)&v205 + 1);
    v52 = (HSTRING *)v205;
    v53 = (void *)v207;
    goto LABEL_231;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)v7 + 15);
  phNewToken = (HSTRING)((char *)v7 + 600);
  v54 = **((_QWORD **)v7 + 80);
  v51 = (HSTRING *)*((_QWORD *)&v205 + 1);
  v52 = (HSTRING *)v205;
  while ( v54 != *((_QWORD *)v7 + 80) )
  {
    v215 = *(HSTRING *)(v54 + 40);
    v150 = v215;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v215);
    v169 = 0;
    v151 = *(__int64 (__fastcall **)(HSTRING, struct Windows::System::Internal::ISignInContext *, HSTRING *))(*(_QWORD *)v150 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v169);
    v152 = v151(v150, a3, &v169);
    v154 = v152;
    if ( (byte_180147C81 & 1) != 0 )
    {
      v190 = v169;
      v185 = *(HSTRING *)(v54 + 40);
      v214 = *(HSTRING *)(v54 + 32);
      LODWORD(v170) = v152;
      v232 = &v214;
      v233 = 8;
      v234 = &v185;
      v235 = 8;
      v236 = &v190;
      v237 = 8;
      v238 = &v170;
      v239 = 4;
      TokenTypec = v231;
      McGenEventWrite_EventWriteTransfer(v214, "E", v153, 5);
    }
    if ( (int)(v154 + 0x80000000) < 0 || v154 == -2147467263 )
    {
      try
      {
        if ( &v215 >= v51 || v52 > &v215 )
        {
          if ( v51 == v206 )
          {
            std::vector<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInArbiter>>::_Reserve(&v205);
            v51 = (HSTRING *)*((_QWORD *)&v205 + 1);
            v52 = (HSTRING *)v205;
          }
          *v51 = v150;
        }
        else
        {
          v155 = (char *)&v215 - (char *)v52;
          if ( v51 == v206 )
          {
            std::vector<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInArbiter>>::_Reserve(&v205);
            v51 = (HSTRING *)*((_QWORD *)&v205 + 1);
            v52 = (HSTRING *)v205;
          }
          *v51 = v52[v155 >> 3];
        }
        v156 = v51++;
        *((_QWORD *)&v205 + 1) = v51;
        Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v156);
        if ( v169 )
          std::vector<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>>::push_back(&v207, &v169);
      }
      catch ( std::bad_alloc )
      {
        v158 = wil::verify_hresult<long>(2147942414LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD0F,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)v158,
          TokenType);
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v169);
    if ( v150 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v150 + 16LL))(v150);
    v7 = v210;
    if ( !*(_BYTE *)(v54 + 25) )
    {
      if ( *(_BYTE *)(*(_QWORD *)(v54 + 16) + 25LL) )
      {
        for ( i = *(_QWORD *)(v54 + 8); !*(_BYTE *)(i + 25) && v54 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
          v54 = i;
      }
      else
      {
        i = std::_Tree_val<std::_Tree_simple_types<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>>::_Min();
      }
      v54 = i;
    }
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&phNewToken);
  if ( v165 )
  {
    if ( !*(_QWORD *)v176 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v59 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v176,
            &v191);
    if ( v59 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD27,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v59,
        (int)TokenTypec);
    v60 = (*(__int64 (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v191 + 80LL))(v191, &hExistingToken);
    v58 = retaddr;
    if ( v60 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD28,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v60,
        (int)TokenTypec);
  }
  else
  {
    v55 = v192;
    v56 = WindowsGetStringRawBuffer(v174, 0);
    v57 = Windows::System::Internal::UserManagerStatics::LsaLogonUserWrapper(
            v7,
            v168,
            a3,
            v56,
            v55,
            &hExistingToken,
            &v212,
            &v213);
    v58 = retaddr;
    if ( v57 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD21,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v57,
        (int)TokenTypec);
  }
  v61 = Windows::System::Internal::UserManagerStatics::CheckCancelEvent(v58, v211);
  v62 = retaddr;
  if ( v61 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD2C,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v61,
      (int)TokenTypec);
  if ( v212 )
  {
    Windows::System::Internal::SignInResult::SetResultAndUserLogonStatus(v183, v212, v213);
    v221 = 0;
    lambda_a3b0c7a60547604949e16553c62274b5_::operator()(v220);
    v64 = (void *)v207;
    if ( (_QWORD)v207 )
    {
      std::vector<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>>::_Destroy(
        v63,
        v207,
        *((_QWORD *)&v207 + 1));
      operator delete(v64);
      v207 = 0;
      v208 = 0;
    }
    if ( v52 )
    {
      std::vector<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInArbiter>>::_Destroy(v63, v52, v51);
      operator delete(v52);
      v205 = 0;
      v206 = 0;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v197);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v182);
    WindowsDeleteString(v174);
    v174 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v203);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v204);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v198);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v193);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v189);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v199);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v195);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v200);
    WindowsDeleteString(v178);
    v178 = 0;
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v194);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v183);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v191);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v176);
    return 0;
  }
  v53 = (void *)v207;
  for ( j = (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))v207;
        j != *((__int64 (__fastcall *****)(_QWORD, GUID *, __int64))&v207 + 1);
        ++j )
  {
    v169 = 0;
    LODWORD(v177) = 0;
    v118 = Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>::As<IAsyncInfo>(j, (__int64)&v169);
    if ( v118 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD38,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v118,
        (int)TokenTypec);
    v119 = 0;
    while ( 1 )
    {
      v120 = (*(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)v169 + 56LL))(v169, &v177);
      LODWORD(v170) = v120;
      if ( v120 < 0 )
        break;
      v123 = Windows::System::Internal::UserManagerStatics::CheckCancelEvent(v122, v211);
      if ( v123 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD44,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v123,
          (int)TokenTypec);
      Sleep(0xAu);
      if ( ++v119 > 0x3E8 || (_DWORD)v177 )
      {
        v120 = (int)v170;
        break;
      }
    }
    LODWORD(newString) = 0;
    if ( v119 >= 0x3E8 || v120 < 0 )
    {
      if ( (byte_180147C81 & 1) != 0 )
      {
        v149 = -2147023436;
        if ( v120 < 0 )
          v149 = v120;
        McTemplateU0pdx_EventWriteTransfer((_DWORD)v122, v121, (unsigned int)*j, v149, 10 * v119);
      }
    }
    else
    {
      v124 = (*(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)v169 + 64LL))(v169, &newString);
      if ( v124 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD50,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v124,
          (int)TokenTypec);
      if ( (byte_180147C81 & 1) != 0 )
        McTemplateU0pdx_EventWriteTransfer((_DWORD)retaddr, v125, (unsigned int)*j, (_DWORD)newString, 10 * v119);
      if ( (int)((_DWORD)newString + 0x80000000) >= 0 && (_DWORD)newString != -2147467263 )
      {
        Windows::System::Internal::SignInResult::SetResultAndUserLogonStatus(v183, (int)newString);
        v93 = (int)newString;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v169);
        goto LABEL_187;
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v169);
    v7 = v210;
  }
LABEL_64:
  v66 = Windows::System::Internal::UserManagerStatics::CheckCancelEvent(v62, v211);
  v67 = retaddr;
  if ( v66 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD6E,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v66,
      (int)TokenTypec);
  if ( !v171 )
  {
    v93 = (int)v184;
    goto LABEL_187;
  }
  v188 = 0;
  if ( *((_DWORD *)v7 + 251) == 5 )
  {
    v68 = v193;
    v69 = *(int (__fastcall **)(__int64, HANDLE, HSTRING *))(*(_QWORD *)v193 + 104LL);
    WindowsDeleteString(0);
    v188 = 0;
    if ( v69(v68, hExistingToken, &v188) >= 0 )
    {
      if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                           (Microsoft::WRL::Wrappers::Details *)v188,
                           string,
                           v70) )
      {
        phNewToken = v188;
        v71 = Microsoft::WRL::Wrappers::HString::Set(&string, &phNewToken);
        if ( v71 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xD7E,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v71,
            (int)TokenTypec);
      }
    }
    v7 = v210;
  }
  if ( !v165 && !*(_QWORD *)v176 )
  {
    phNewToken = (HSTRING)-1LL;
    if ( !DuplicateTokenEx(hExistingToken, 0xF01FFu, 0, SecurityImpersonation, TokenImpersonation, (PHANDLE)&phNewToken) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xD87,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        v72);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v176);
    LODWORD(TokenTypec) = (_DWORD)phNewToken;
    v73 = Windows::System::Internal::UserManagerStatics::AddLoggedOnUserFromProfile(v7, v168, string, v192);
    v186 = v73;
    if ( v73 == -2136862970 )
    {
      Windows::System::Internal::SignInResult::OverrideResultAndUserLogonStatus(v183, -2136862970);
      v186 = 0;
      WindowsDeleteString(v188);
      v188 = 0;
      v221 = 0;
      lambda_a3b0c7a60547604949e16553c62274b5_::operator()(v220);
      if ( v53 )
      {
        std::vector<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>>::_Destroy(
          v74,
          v53,
          *((_QWORD *)&v207 + 1));
        operator delete(v53);
        v207 = 0;
        v208 = 0;
      }
      if ( v52 )
        goto LABEL_234;
      goto LABEL_235;
    }
    if ( v73 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD93,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v73,
        (int)TokenTypec);
    v172 = 1;
  }
  if ( !IsConnectedToXboxLive )
  {
    if ( *((_QWORD *)v7 + 113) )
    {
      v169 = 0;
      phNewToken = 0;
      v185 = 0;
      v190 = 0;
      v170 = 0;
      newString = 0;
      v184 = 0;
      v177 = 0;
      v202 = 0;
      v201 = 0;
      v164 = 0;
      v180 = 0;
      v94 = (*(__int64 (__fastcall **)(struct Windows::System::Internal::IUserProfile *, char *))(*(_QWORD *)v189 + 80LL))(
              v189,
              &v180);
      if ( v94 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE0C,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v94,
          (int)TokenTypec);
      if ( v180 )
      {
        v95 = v189;
        v96 = *(__int64 (__fastcall **)(struct Windows::System::Internal::IUserProfile *, HSTRING *))(*(_QWORD *)v189 + 88LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v169);
        v97 = v96(v95, &v169);
        if ( v97 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xE13,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v97,
            (int)TokenTypec);
        v98 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
                (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v169,
                (__int64)&phNewToken);
        if ( v98 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xE14,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v98,
            (int)TokenTypec);
        v226 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Foundation.Collections.PropertySet",
          0x2Bu,
          0x2Au);
        v99 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
                v226,
                &v182);
        if ( v99 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xE18,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v99,
            (int)TokenTypec);
        v100 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
                 (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v182,
                 (__int64)&v185);
        if ( v100 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xE1A,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v100,
            (int)TokenTypec);
        WindowsDeleteString(v190);
        v190 = 0;
        v226 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"XboxUserId", 0xBu, 0xAu);
        if ( (int)Windows::System::Internal::Implementation::ComUtils::FromPropertyMap<HSTRING__ *>(
                    (__int64)phNewToken,
                    v226,
                    (__int64)&v190) >= 0 )
        {
          WindowsDeleteString(v170);
          v170 = 0;
          v226 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Gamertag", 9u, 8u);
          if ( (int)Windows::System::Internal::Implementation::ComUtils::FromPropertyMap<HSTRING__ *>(
                      (__int64)phNewToken,
                      v226,
                      (__int64)&v170) >= 0 )
          {
            v101 = v190;
            v226 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"XboxUserId", 0xBu, 0xAu);
            v102 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
                     (__int64)v185,
                     v226,
                     (__int64)v101,
                     (__int64)&v164);
            if ( v102 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xE2A,
                (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
                (const char *)(unsigned int)v102,
                (int)TokenTypec);
            v103 = v170;
            v226 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Gamertag", 9u, 8u);
            v104 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
                     (__int64)v185,
                     v226,
                     (__int64)v103,
                     (__int64)&v164);
            if ( v104 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xE2B,
                (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
                (const char *)(unsigned int)v104,
                (int)TokenTypec);
            WindowsDeleteString(newString);
            newString = 0;
            v226 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ModernGamertag", 0xFu, 0xEu);
            if ( (int)Windows::System::Internal::Implementation::ComUtils::FromPropertyMap<HSTRING__ *>(
                        (__int64)phNewToken,
                        v226,
                        (__int64)&newString) < 0 )
            {
              v214 = v170;
              v105 = Microsoft::WRL::Wrappers::HString::Set(&newString, &v214);
              if ( v105 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xE30,
                  (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
                  (const char *)(unsigned int)v105,
                  (int)TokenTypec);
            }
            v106 = newString;
            v226 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ModernGamertag", 0xFu, 0xEu);
            v107 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
                     (__int64)v185,
                     v226,
                     (__int64)v106,
                     (__int64)&v164);
            if ( v107 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xE32,
                (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
                (const char *)(unsigned int)v107,
                (int)TokenTypec);
            WindowsDeleteString(v177);
            v177 = 0;
            v226 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(
              &hstringHeader,
              L"UniqueModernGamertag",
              0x15u,
              0x14u);
            if ( (int)Windows::System::Internal::Implementation::ComUtils::FromPropertyMap<HSTRING__ *>(
                        (__int64)phNewToken,
                        v226,
                        (__int64)&v177) < 0 )
            {
              v214 = v170;
              v108 = Microsoft::WRL::Wrappers::HString::Set(&v177, &v214);
              if ( v108 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xE36,
                  (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
                  (const char *)(unsigned int)v108,
                  (int)TokenTypec);
            }
            v109 = v177;
            v226 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(
              &hstringHeader,
              L"UniqueModernGamertag",
              0x15u,
              0x14u);
            v110 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
                     (__int64)v185,
                     v226,
                     (__int64)v109,
                     (__int64)&v164);
            if ( v110 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xE38,
                (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
                (const char *)(unsigned int)v110,
                (int)TokenTypec);
            WindowsDeleteString(v184);
            v184 = 0;
            v226 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(
              &hstringHeader,
              L"ModernGamertagSuffix",
              0x15u,
              0x14u);
            if ( (int)Windows::System::Internal::Implementation::ComUtils::FromPropertyMap<HSTRING__ *>(
                        (__int64)phNewToken,
                        v226,
                        (__int64)&v184) < 0 )
            {
              v111 = Microsoft::WRL::Wrappers::HString::Set(
                       (Microsoft::WRL::Wrappers::HString *)&v184,
                       &cchOriginalDestLength,
                       0);
              if ( v111 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xE3D,
                  (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
                  (const char *)(unsigned int)v111,
                  (int)TokenTypec);
            }
            v112 = v184;
            v226 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(
              &hstringHeader,
              L"ModernGamertagSuffix",
              0x15u,
              0x14u);
            v113 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
                     (__int64)v185,
                     v226,
                     (__int64)v112,
                     (__int64)&v164);
            if ( v113 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xE3F,
                (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
                (const char *)(unsigned int)v113,
                (int)TokenTypec);
            WindowsDeleteString(v202);
            v202 = 0;
            v226 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"AgeGroup", 9u, 8u);
            if ( (int)Windows::System::Internal::Implementation::ComUtils::FromPropertyMap<HSTRING__ *>(
                        (__int64)phNewToken,
                        v226,
                        (__int64)&v202) >= 0 )
            {
              v114 = v202;
              v226 = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"AgeGroup", 9u, 8u);
              v115 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
                       (__int64)v185,
                       v226,
                       (__int64)v114,
                       (__int64)&v164);
              if ( v115 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xE44,
                  (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
                  (const char *)(unsigned int)v115,
                  (int)TokenTypec);
            }
            WindowsDeleteString(v201);
            v201 = 0;
            v226 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UserData", 9u, 8u);
            if ( (int)Windows::System::Internal::Implementation::ComUtils::FromPropertyMap<HSTRING__ *>(
                        (__int64)phNewToken,
                        v226,
                        (__int64)&v201) >= 0 )
            {
              v116 = v201;
              v226 = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UserData", 9u, 8u);
              v117 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
                       (__int64)v185,
                       v226,
                       (__int64)v116,
                       (__int64)&v164);
              if ( v117 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xE49,
                  (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
                  (const char *)(unsigned int)v117,
                  (int)TokenTypec);
            }
            v93 = -2015559654;
            WindowsDeleteString(v201);
            v201 = 0;
            WindowsDeleteString(v202);
            v202 = 0;
            WindowsDeleteString(v177);
            v177 = 0;
            WindowsDeleteString(v184);
            v184 = 0;
            WindowsDeleteString(newString);
            newString = 0;
            WindowsDeleteString(v170);
            v170 = 0;
            WindowsDeleteString(v190);
            v190 = 0;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v185);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&phNewToken);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v169);
            goto LABEL_116;
          }
          Windows::System::Internal::SignInResult::SetResultAndUserLogonStatus(v183, -2136866043);
          WindowsDeleteString(v201);
          v201 = 0;
          WindowsDeleteString(v202);
          v202 = 0;
          WindowsDeleteString(v177);
          v177 = 0;
          WindowsDeleteString(v184);
          v184 = 0;
          WindowsDeleteString(newString);
          newString = 0;
          WindowsDeleteString(v170);
          v170 = 0;
          WindowsDeleteString(v190);
          v190 = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v185);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&phNewToken);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v169);
          WindowsDeleteString(v188);
          v188 = 0;
          v221 = 0;
          lambda_a3b0c7a60547604949e16553c62274b5_::operator()(v220);
          if ( v53 )
          {
            std::vector<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>>::_Destroy(
              v74,
              v53,
              *((_QWORD *)&v207 + 1));
            operator delete(v53);
            v207 = 0;
            v208 = 0;
          }
          if ( !v52 )
            goto LABEL_235;
        }
        else
        {
          Windows::System::Internal::SignInResult::SetResultAndUserLogonStatus(v183, -2136866043);
          WindowsDeleteString(v201);
          v201 = 0;
          WindowsDeleteString(v202);
          v202 = 0;
          WindowsDeleteString(v177);
          v177 = 0;
          WindowsDeleteString(v184);
          v184 = 0;
          WindowsDeleteString(newString);
          newString = 0;
          WindowsDeleteString(v170);
          v170 = 0;
          WindowsDeleteString(v190);
          v190 = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v185);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&phNewToken);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v169);
          WindowsDeleteString(v188);
          v188 = 0;
          v221 = 0;
          lambda_a3b0c7a60547604949e16553c62274b5_::operator()(v220);
          if ( v53 )
          {
            std::vector<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>>::_Destroy(
              v74,
              v53,
              *((_QWORD *)&v207 + 1));
            operator delete(v53);
            v207 = 0;
            v208 = 0;
          }
          if ( !v52 )
            goto LABEL_235;
        }
      }
      else
      {
        Windows::System::Internal::SignInResult::SetResultAndUserLogonStatus(v183, -2136866043);
        v186 = 0;
        WindowsDeleteString(v201);
        v201 = 0;
        WindowsDeleteString(v202);
        v202 = 0;
        WindowsDeleteString(v177);
        v177 = 0;
        WindowsDeleteString(v184);
        v184 = 0;
        WindowsDeleteString(newString);
        newString = 0;
        WindowsDeleteString(v170);
        v170 = 0;
        WindowsDeleteString(v190);
        v190 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v185);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&phNewToken);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v169);
        WindowsDeleteString(v188);
        v188 = 0;
        v221 = 0;
        lambda_a3b0c7a60547604949e16553c62274b5_::operator()(v220);
        if ( v53 )
        {
          std::vector<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>>::_Destroy(
            v74,
            v53,
            *((_QWORD *)&v207 + 1));
          operator delete(v53);
          v207 = 0;
          v208 = 0;
        }
        if ( !v52 )
          goto LABEL_235;
      }
LABEL_234:
      std::vector<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInArbiter>>::_Destroy(v74, v52, v51);
      operator delete(v52);
      v205 = 0;
      v206 = 0;
      goto LABEL_235;
    }
LABEL_133:
    v93 = (int)v184;
    goto LABEL_116;
  }
  if ( *((_DWORD *)v7 + 251) == 5 && !v224 )
  {
    v75 = WindowsGetStringRawBuffer(v174, 0);
    v76 = StringCchCopyW(v240, 0x201u, v75);
    if ( v76 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD9E,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v76,
        (int)TokenTypec);
    if ( !DuplicateTokenEx(hExistingToken, 0xCu, 0, SecurityImpersonation, TokenImpersonation, &v218) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xDA1,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        v77);
    LODWORD(v223[0]) = 56;
    *((_QWORD *)&v223[0] + 1) = v240;
    if ( !(*(unsigned int (__fastcall **)(__int64, void *, _OWORD *))(*(_QWORD *)v195 + 24LL))(v195, v218, v223) )
    {
      Windows::System::Internal::SignInResult::SetResultAndUserLogonStatus(v183, -2136862970);
      WindowsDeleteString(v188);
      v188 = 0;
      v221 = 0;
      lambda_a3b0c7a60547604949e16553c62274b5_::operator()(v220);
      if ( v53 )
      {
        std::vector<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>>::_Destroy(
          v74,
          v53,
          *((_QWORD *)&v207 + 1));
        operator delete(v53);
        v207 = 0;
        v208 = 0;
      }
      if ( v52 )
        goto LABEL_234;
      goto LABEL_235;
    }
  }
  phNewToken = v178;
  v185 = string;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v194);
  v78 = Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::SignInResult,Windows::System::Internal::SignInResult,unsigned int &,HSTRING__ *,enum Windows::System::Internal::SignInCaller &,HSTRING__ *>(
          (unsigned int)&v194,
          (unsigned int)&v168,
          (unsigned int)&v185,
          (unsigned int)&v196,
          (__int64)&phNewToken);
  if ( v78 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xDAE,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v78,
      TokenTyped);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v182);
  v79 = (HSTRING *)v194;
  v80 = Windows::System::Internal::UserManagerStatics::PerformAuthorizationCheck(
          v210,
          hExistingToken,
          v168,
          v174,
          string,
          v194,
          &v182);
  LODWORD(v184) = v80;
  if ( v80 >= 0 )
  {
    phNewToken = 0;
    WindowsDeleteString(0);
    phNewToken = 0;
    v226 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UserData", 9u, 8u);
    v81 = Windows::System::Internal::Implementation::ComUtils::FromPropertySet<HSTRING__ *>(
            (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))v182,
            v226,
            (__int64)&phNewToken);
    if ( v81 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDB8,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v81,
        (int)TokenTypec);
    v185 = phNewToken;
    v82 = Microsoft::WRL::Wrappers::HString::Set(v79 + 23, &v185);
    if ( v82 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13F,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\signinresult.cpp",
        (const char *)(unsigned int)v82,
        (int)TokenTypec);
    v169 = 0;
    WindowsDeleteString(0);
    v169 = 0;
    v226 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"XboxUserId", 0xBu, 0xAu);
    v83 = Windows::System::Internal::Implementation::ComUtils::FromPropertySet<HSTRING__ *>(
            (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))v182,
            v226,
            (__int64)&v169);
    if ( v83 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDBC,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v83,
        (int)TokenTypec);
    v185 = v169;
    v84 = Microsoft::WRL::Wrappers::HString::Set(v79 + 24, &v185);
    if ( v84 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x147,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\signinresult.cpp",
        (const char *)(unsigned int)v84,
        (int)TokenTypec);
    WindowsDeleteString(v169);
    v169 = 0;
    WindowsDeleteString(phNewToken);
  }
  else
  {
    Windows::System::Internal::SignInResult::SetResultAndUserLogonStatus(
      (Windows::System::Internal::SignInResult *)v79,
      v80);
  }
  if ( !(v51 - v52) )
  {
    Microsoft::WRL::ComPtr<Windows::System::Internal::SignInResult>::operator=(&v183, &v194);
    goto LABEL_133;
  }
  v85 = v52;
  while ( 1 )
  {
    while ( 1 )
    {
      if ( v85 == v51 )
        goto LABEL_133;
      phNewToken = *v85;
      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&phNewToken);
      LODWORD(newString) = 0;
      v164 = 0;
      if ( (byte_180147C81 & 1) != 0 )
      {
        LODWORD(v170) = (_DWORD)v184;
        v190 = phNewToken;
        v185 = 0;
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = &v185;
        v226 = 8;
        v227 = &v190;
        v228 = 8;
        v229 = &v170;
        v230 = 4;
        McGenEventWrite_EventWriteTransfer(4, SignedInArbitration_Start, v86, 4);
      }
      v87 = WindowsGetStringRawBuffer(v174, 0);
      Windows::System::Internal::Implementation::AutoUserContext::AutoUserContext(
        (Windows::System::Internal::Implementation::AutoUserContext *)v231,
        hExistingToken,
        v87);
      TokenTypec = &newString;
      v88 = (*(__int64 (__fastcall **)(HSTRING, struct Windows::System::Internal::ISignInContext *, unsigned __int64, unsigned __int8 *))(*(_QWORD *)phNewToken + 56LL))(
              phNewToken,
              a3,
              (unsigned __int64)(v79 + 3) & -(__int64)(v79 != 0),
              &v164);
      v90 = v88;
      LODWORD(v177) = v88;
      if ( (byte_180147C81 & 1) != 0 )
      {
        McTemplateU0xptdd_EventWriteTransfer(
          (_DWORD)newString,
          v164,
          v89,
          (_DWORD)phNewToken,
          v164,
          (char)newString,
          v88);
        v90 = (int)v177;
      }
      if ( v90 >= 0 )
        break;
      if ( v90 != -2147467263 )
      {
        v92 = (int)newString;
        v91 = v164;
        goto LABEL_119;
      }
      Windows::System::Internal::Implementation::AutoUserContext::Revoke((Windows::System::Internal::Implementation::AutoUserContext *)v231);
      if ( phNewToken )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)phNewToken + 16LL))(phNewToken);
      ++v85;
    }
    v91 = v164;
    v92 = (int)newString;
    if ( v164 )
    {
      Windows::System::Internal::SignInResult::SetResultAndUserLogonStatus(
        (Windows::System::Internal::SignInResult *)v79,
        (int)newString);
      Windows::System::Internal::Implementation::AutoUserContext::Revoke((Windows::System::Internal::Implementation::AutoUserContext *)v231);
      if ( phNewToken )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)phNewToken + 16LL))(phNewToken);
      WindowsDeleteString(v188);
      v7 = v210;
      goto LABEL_64;
    }
    if ( (int)newString >= 0 )
    {
      v93 = 0;
      Windows::System::Internal::Implementation::AutoUserContext::Revoke((Windows::System::Internal::Implementation::AutoUserContext *)v231);
      if ( !phNewToken )
        goto LABEL_116;
      goto LABEL_115;
    }
LABEL_119:
    if ( v91 )
      break;
    if ( (unsigned __int64)(v51 - v52) <= 1 )
      break;
    if ( ++v85 == v51 )
      break;
    Windows::System::Internal::Implementation::AutoUserContext::Revoke((Windows::System::Internal::Implementation::AutoUserContext *)v231);
    if ( phNewToken )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)phNewToken + 16LL))(phNewToken);
  }
  if ( v90 < 0 )
  {
    Windows::System::Internal::SignInResult::SetResultAndUserLogonStatus(
      (Windows::System::Internal::SignInResult *)v79,
      v90);
    v93 = (int)v177;
  }
  else
  {
    Windows::System::Internal::SignInResult::SetResultAndUserLogonStatus(
      (Windows::System::Internal::SignInResult *)v79,
      v92);
    v93 = (int)newString;
  }
  Microsoft::WRL::ComPtr<Windows::System::Internal::SignInResult>::operator=(&v183, &v194);
  Windows::System::Internal::Implementation::AutoUserContext::Revoke((Windows::System::Internal::Implementation::AutoUserContext *)v231);
  if ( phNewToken )
LABEL_115:
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)phNewToken + 16LL))(phNewToken);
LABEL_116:
  WindowsDeleteString(v188);
LABEL_187:
  v126 = Windows::System::Internal::UserManagerStatics::CheckCancelEvent(v67, v211);
  if ( v126 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE4F,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v126,
      (int)TokenTypec);
  if ( v93 >= 0 )
  {
    v127 = 0;
    if ( v171 )
      v127 = 2;
  }
  else
  {
    v127 = 1;
  }
  v187 = 0;
  v128 = (*(__int64 (__fastcall **)(char *, int *))(*((_QWORD *)v183 + 3) + 64LL))((char *)v183 + 24, &v187);
  if ( v128 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE62,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v128,
      (int)TokenTypec);
  v129 = v210;
  Windows::System::Internal::UserManagerStatics::UpdateLastSigninResult(v210, v168, v187);
  v181 = 1;
  v130 = 1;
  if ( *((_DWORD *)v129 + 251) == 5 && v127 != 2 && (!string || v186 < 0 || v187 < 0) )
    v130 = 0;
  if ( IsConnectedToXboxLive )
    Windows::System::Internal::UserManagerStatics::UpdateOfflineProfileFromAuthZ(v129, v189, v182);
  if ( v165 )
  {
    if ( v172 )
    {
      v136 = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(v129);
      if ( v130 )
      {
        LODWORD(TokenTypec) = (_DWORD)v182;
        (*(void (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v136 + 256LL))(
          v136,
          v168,
          v192,
          v127);
      }
      else
      {
        (*(void (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, _QWORD, struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v136 + 272LL))(
          v136,
          *(_QWORD *)v176,
          v127,
          v182);
      }
    }
    else
    {
      v137 = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(v129);
      (*(void (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, _QWORD, struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v137 + 120LL))(
        v137,
        *(_QWORD *)v176,
        v127,
        v182);
    }
LABEL_220:
    if ( IsConnectedToXboxLive )
    {
      if ( v127 == 2 )
      {
        v211 = 0;
        v169 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v211);
        v138 = Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Localize(
                 (char *)v129 + 552,
                 &GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5,
                 &v211);
        if ( v138 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xEBD,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v138,
            (int)TokenTypec);
        v139 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
                 (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v176,
                 &v191);
        if ( v139 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xEBF,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v139,
            (int)TokenTypec);
        v140 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v191 + 88LL))(v191, &v169);
        if ( v140 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xEC0,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v140,
            (int)TokenTypec);
        v141 = v211;
        v142 = *(__int64 (__fastcall **)(void *, PCWSTR, HSTRING))(*(_QWORD *)v211 + 432LL);
        v143 = v169;
        v144 = WindowsGetStringRawBuffer(string, 0);
        v145 = v142(v141, v144, v143);
        if ( v145 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xEC1,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v145,
            (int)TokenTypec);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v211);
      }
    }
    else if ( Windows::System::Internal::UserManagerStatics::IsConnectedToXboxLive(v129) )
    {
      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v176);
      *(_QWORD *)v219 = *(_QWORD *)v176;
    }
    v146 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v146 > 4u )
    {
      LODWORD(v170) = 0;
      v219 = (WCHAR *)WindowsGetStringRawBuffer(string, 0);
      LODWORD(v177) = v196;
      v187 = v168;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v146,
        (unsigned int)&dword_180126184,
        v147,
        v148,
        (__int64)&v187,
        (__int64)&v177,
        (__int64)&v219,
        (__int64)&v170);
    }
LABEL_231:
    v221 = 0;
    lambda_a3b0c7a60547604949e16553c62274b5_::operator()(v220);
    if ( v53 )
    {
      std::vector<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>>::_Destroy(v74, v53, *((_QWORD *)&v207 + 1));
      operator delete(v53);
      v207 = 0;
      v208 = 0;
    }
    if ( v52 )
      goto LABEL_234;
    goto LABEL_235;
  }
  if ( *(_QWORD *)v176 )
  {
    v132 = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(v129);
    if ( v130 )
    {
      LODWORD(TokenTypec) = (_DWORD)v182;
      (*(void (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v132 + 256LL))(
        v132,
        v168,
        v192,
        v127);
    }
    else
    {
      (*(void (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, _QWORD, struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v132 + 272LL))(
        v132,
        *(_QWORD *)v176,
        v127,
        v182);
    }
LABEL_213:
    v133 = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(v129);
    LOBYTE(v134) = v130 ^ 1;
    v135 = (*(__int64 (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, __int64))(*(_QWORD *)v133 + 208LL))(
             v133,
             *(_QWORD *)v176,
             v134);
    if ( v135 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xEA3,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v135,
        (int)TokenTypec);
    goto LABEL_220;
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v176);
  LODWORD(TokenTypec) = (_DWORD)hExistingToken;
  v131 = Windows::System::Internal::UserManagerStatics::AddLoggedOnUserFromProfile(v129, v168, string, v192);
  v186 = v131;
  hExistingToken = 0;
  if ( v131 != -2136862970 )
  {
    if ( v131 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE97,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v131,
        (int)TokenTypec);
    goto LABEL_213;
  }
  Windows::System::Internal::SignInResult::OverrideResultAndUserLogonStatus(v183, -2136862970);
  v186 = 0;
  v221 = 0;
  lambda_a3b0c7a60547604949e16553c62274b5_::operator()(v220);
  if ( v53 )
  {
    std::vector<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>>::_Destroy(v74, v53, *((_QWORD *)&v207 + 1));
    operator delete(v53);
    v207 = 0;
    v208 = 0;
  }
  if ( v52 )
    goto LABEL_234;
LABEL_235:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v197);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v182);
  WindowsDeleteString(v174);
  v174 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v203);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v204);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v198);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v193);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v189);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v199);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v195);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v200);
  WindowsDeleteString(v178);
  v178 = 0;
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v194);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v183);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v191);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v176);
  return 0;
}

```

## disassembly

```asm
0x18009ac9c  push    rbx
0x18009ac9e  push    rsi
0x18009ac9f  push    rdi
0x18009aca0  push    r12
0x18009aca2  push    r13
0x18009aca4  push    r14
0x18009aca6  push    r15
0x18009aca8  sub     rsp, 750h
0x18009acaf  mov     rax, cs:__security_cookie
0x18009acb6  xor     rax, rsp
0x18009acb9  mov     [rsp+788h+var_48], rax
0x18009acc1  mov     [rsp+788h+var_5E0], r9
0x18009acc9  mov     r14, r8
0x18009accc  mov     rsi, rcx
0x18009accf  mov     [rsp+788h+var_5E8], rcx
0x18009acd7  mov     [rsp+788h+var_720], edx
0x18009acdb  mov     [rsp+788h+var_528], r8
0x18009ace3  mov     rdi, [rsp+788h+arg_20]
0x18009aceb  mov     [rsp+788h+var_5A8], rdi
0x18009acf3  mov     rax, [rsp+788h+arg_28]
0x18009acfb  mov     [rsp+788h+var_5B8], rax
0x18009ad03  xor     r15d, r15d
0x18009ad06  test    rdi, rdi
0x18009ad09  jnz     short loc_18009AD18
0x18009ad0b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009ad10  mov     rax, [rsp+788h+var_5B8]
0x18009ad18  test    rax, rax
0x18009ad1b  jnz     short loc_18009AD22
0x18009ad1d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009ad22  mov     [rsp+788h+var_6B0], r15d
0x18009ad2a  mov     dword ptr [rsp+788h+var_6C0], r15d
0x18009ad32  mov     qword ptr [rsp+788h+var_6F0], r15
0x18009ad3a  mov     [rsp+788h+var_707], r15b
0x18009ad42  mov     [rsp+788h+var_690], r15
0x18009ad4a  mov     [rsp+788h+var_6C8], r15
0x18009ad52  mov     [rsp+788h+var_678], r15
0x18009ad5a  mov     [rsp+788h+string], r15
0x18009ad5f  mov     [rsp+788h+var_6E0], r15
0x18009ad67  mov     [rsp+788h+var_648], r15
0x18009ad6f  mov     [rsp+788h+var_670], r15
0x18009ad77  mov     [rsp+788h+var_650], r15
0x18009ad7f  mov     [rsp+788h+var_6A0], r15
0x18009ad87  mov     [rsp+788h+var_680], r15
0x18009ad8f  mov     [rsp+788h+var_658], r14
0x18009ad97  lea     rcx, [rsp+788h+var_658]
0x18009ad9f  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18009ada4  nop
0x18009ada5  mov     [rsp+788h+var_628], r15
0x18009adad  mov     [rsp+788h+var_630], r15
0x18009adb5  mov     [rsp+788h+var_700], r15
0x18009adbd  mov     [rsp+788h+var_5D8], r15d
0x18009adc5  mov     [rsp+788h+var_5D4], r15d
0x18009adcd  mov     [rsp+788h+var_6D0], r15
0x18009add5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18009add9  mov     [rsp+788h+var_5B0], rbx
0x18009ade1  xor     edx, edx; Val
0x18009ade3  mov     r8d, 402h; Size
0x18009ade9  lea     rcx, [rsp+788h+var_458]; void *
0x18009adf1  call    memset_0
0x18009adf6  mov     [rsp+788h+hExistingToken], rbx
0x18009adfe  xorps   xmm0, xmm0
0x18009ae01  xor     eax, eax
0x18009ae03  movups  [rsp+788h+var_520], xmm0
0x18009ae0b  movups  [rsp+788h+var_510], xmm0
0x18009ae13  movups  [rsp+788h+var_500], xmm0
0x18009ae1b  mov     [rsp+788h+var_4F0], rax
0x18009ae23  mov     r13b, r15b
0x18009ae26  mov     [rsp+788h+var_737], r15b
0x18009ae2b  mov     [rsp+788h+var_688], r15d
0x18009ae33  call    cs:__imp_GetTickCount
0x18009ae39  mov     [rsp+788h+var_5C0], eax
0x18009ae40  mov     [rsp+788h+var_6D8], r15b
0x18009ae48  mov     [rsp+788h+var_660], r15
0x18009ae50  mov     [rsp+788h+var_6D6], r15b
0x18009ae58  xorps   xmm0, xmm0
0x18009ae5b  movdqu  [rsp+788h+var_620], xmm0
0x18009ae64  mov     [rsp+788h+var_610], r15
0x18009ae6c  movdqu  [rsp+788h+var_608], xmm0
0x18009ae75  mov     [rsp+788h+var_5F8], r15
0x18009ae7d  mov     rax, cs:?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x18009ae84  mov     rbx, [rax+38h]
0x18009ae88  lea     rcx, [rsp+788h+var_648]
0x18009ae90  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009ae95  lea     rdx, [rsp+788h+var_648]
0x18009ae9d  lea     r12, ?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x18009aea4  mov     rcx, r12
0x18009aea7  mov     rax, rbx
0x18009aeaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aeaf  mov     rax, cs:?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x18009aeb6  mov     rbx, [rax+18h]
0x18009aeba  lea     rcx, [rsp+788h+var_670]
0x18009aec2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009aec7  lea     rdx, [rsp+788h+var_670]
0x18009aecf  mov     rcx, r12
0x18009aed2  mov     rax, rbx
0x18009aed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aeda  mov     rax, cs:?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x18009aee1  mov     rbx, [rax+58h]
0x18009aee5  lea     rcx, [rsp+788h+var_650]
0x18009aeed  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009aef2  lea     rdx, [rsp+788h+var_650]
0x18009aefa  mov     rcx, r12
0x18009aefd  mov     rax, rbx
0x18009af00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009af05  mov     [rsp+788h+var_668], r15d
0x18009af0d  test    r14, r14
0x18009af10  jz      short loc_18009AF29
0x18009af12  mov     rax, [r14]
0x18009af15  lea     rdx, [rsp+788h+var_668]
0x18009af1d  mov     rcx, r14
0x18009af20  mov     rax, [rax+40h]
0x18009af24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009af29  mov     eax, cs:dword_180146228
0x18009af2f  cmp     eax, 4
0x18009af32  jbe     short loc_18009AF74
0x18009af34  mov     eax, [rsp+788h+var_668]
0x18009af3b  mov     dword ptr [rsp+788h+var_710], eax
0x18009af3f  mov     eax, [rsp+788h+var_720]
0x18009af43  mov     dword ptr [rsp+788h+var_6E8], eax
0x18009af4a  lea     rax, [rsp+788h+var_710]
0x18009af4f  mov     [rsp+788h+phNewToken], rax
0x18009af54  lea     rax, [rsp+788h+var_6E8]
0x18009af5c  mov     qword ptr [rsp+788h+TokenType], rax; int
0x18009af61  lea     rdx, byte_1801261D3
0x18009af68  lea     rcx, dword_180146228
0x18009af6f  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18009af74  lea     rax, [rsp+788h+var_737]
0x18009af79  mov     [rsp+788h+var_598], rax
0x18009af81  lea     rax, [rsp+788h+hExistingToken]
0x18009af89  mov     [rsp+788h+var_590], rax
0x18009af91  lea     rax, [rsp+788h+var_6C8]
0x18009af99  mov     [rsp+788h+var_588], rax
0x18009afa1  lea     rax, [rsp+788h+var_6B0]
0x18009afa9  mov     [rsp+788h+var_580], rax
0x18009afb1  lea     rax, [rsp+788h+var_5B8]
0x18009afb9  mov     [rsp+788h+var_578], rax
0x18009afc1  lea     rax, [rsp+788h+var_5C0]
0x18009afc9  mov     [rsp+788h+var_570], rax
0x18009afd1  lea     rax, [rsp+788h+var_6E0]
0x18009afd9  mov     [rsp+788h+var_568], rax
0x18009afe1  lea     rax, [rsp+788h+var_720]
0x18009afe6  mov     [rsp+788h+var_560], rax
0x18009afee  lea     rax, [rsp+788h+var_6D6]
0x18009aff6  mov     [rsp+788h+var_558], rax
0x18009affe  mov     [rsp+788h+var_550], rsi
0x18009b006  lea     rax, [rsp+788h+var_520]
0x18009b00e  mov     [rsp+788h+var_548], rax
0x18009b016  lea     rax, [rsp+788h+var_670]
0x18009b01e  mov     [rsp+788h+var_540], rax
0x18009b026  lea     rax, [rsp+788h+var_5B0]
0x18009b02e  mov     [rsp+788h+var_538], rax
0x18009b036  mov     r12d, 1
0x18009b03c  mov     [rsp+788h+var_530], r12b
0x18009b044  mov     [rdi], r15
0x18009b047  mov     rax, [rsp+788h+var_5B8]
0x18009b04f  mov     [rax], r15
0x18009b052  mov     rcx, [rsi+218h]
0x18009b059  mov     rax, [rcx]
0x18009b05c  mov     edx, [rsp+788h+var_720]
0x18009b060  mov     rax, [rax+78h]
0x18009b064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b069  mov     rcx, [rsp+788h]; this
0x18009b071  test    eax, eax
0x18009b073  js      loc_18009E02A
0x18009b079  mov     rdi, [rsi+218h]
0x18009b080  mov     rax, [rdi]
0x18009b083  mov     rbx, [rax+60h]
0x18009b087  lea     rcx, [rsp+788h+var_6A0]
0x18009b08f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009b094  lea     r8, [rsp+788h+var_6A0]
0x18009b09c  mov     edx, [rsp+788h+var_720]
0x18009b0a0  mov     rcx, rdi
0x18009b0a3  mov     rax, rbx
0x18009b0a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b0ab  mov     rcx, [rsp+788h]; this
0x18009b0b3  test    eax, eax
0x18009b0b5  js      loc_18009E03E
0x18009b0bb  mov     rdi, [rsp+788h+var_6A0]
0x18009b0c3  mov     rax, [rdi]
0x18009b0c6  mov     rbx, [rax+40h]
0x18009b0ca  mov     rcx, [rsp+788h+string]; string
0x18009b0cf  call    cs:__imp_WindowsDeleteString
0x18009b0d5  mov     [rsp+788h+string], r15
0x18009b0da  lea     rdx, [rsp+788h+string]
0x18009b0df  mov     rcx, rdi
0x18009b0e2  mov     rax, rbx
0x18009b0e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b0ea  mov     rcx, [rsp+788h]; this
0x18009b0f2  test    eax, eax
0x18009b0f4  js      loc_18009E052
0x18009b0fa  lea     rdx, [rsp+788h+var_680]
0x18009b102  lea     rcx, [rsp+788h+var_6A0]
0x18009b10a  call    ??$As@UIUserProfileInternal@Implementation@Internal@System@Windows@@@?$ComPtr@UIUserProfile@Internal@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserProfileInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>::As<Windows::System::Internal::Implementation::IUserProfileInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserProfileInternal>>)
0x18009b10f  mov     rcx, [rsp+788h]; this
0x18009b117  test    eax, eax
0x18009b119  js      loc_18009E066
0x18009b11f  mov     rdi, [rsp+788h+var_680]
0x18009b127  mov     rax, [rdi]
0x18009b12a  mov     rbx, [rax+30h]
0x18009b12e  mov     rcx, [rsp+788h+var_700]; string
0x18009b136  call    cs:__imp_WindowsDeleteString
0x18009b13c  mov     [rsp+788h+var_700], r15
0x18009b144  lea     rdx, [rsp+788h+var_700]
0x18009b14c  mov     rcx, rdi
0x18009b14f  mov     rax, rbx
0x18009b152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b157  mov     rcx, [rsp+788h]; this
0x18009b15f  test    eax, eax
0x18009b161  js      loc_18009E07A
0x18009b167  lea     rdx, [rsp+788h+var_628]
0x18009b16f  lea     rcx, [rsp+788h+var_658]
0x18009b177  call    ??$As@UISignInContext2@Internal@System@Windows@@@?$ComPtr@UISignInContext@Internal@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISignInContext2@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInContext>::As<Windows::System::Internal::ISignInContext2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInContext2>>)
0x18009b17c  mov     rcx, [rsp+788h]; this
0x18009b184  test    eax, eax
0x18009b186  js      loc_18009E08E
0x18009b18c  mov     rdi, [rsp+788h+var_628]
0x18009b194  mov     rax, [rdi]
0x18009b197  mov     rbx, [rax+30h]
0x18009b19b  mov     rcx, [rsp+788h+var_6E0]; string
0x18009b1a3  call    cs:__imp_WindowsDeleteString
0x18009b1a9  mov     [rsp+788h+var_6E0], r15
0x18009b1b1  lea     rdx, [rsp+788h+var_6E0]
0x18009b1b9  mov     rcx, rdi
0x18009b1bc  mov     rax, rbx
0x18009b1bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b1c4  mov     rcx, [rsp+788h]; this
0x18009b1cc  test    eax, eax
0x18009b1ce  js      loc_18009E0A2
0x18009b1d4  mov     rax, [rsp+788h+var_6E0]
0x18009b1dc  mov     [rsp+788h+var_718], rax
0x18009b1e1  mov     rax, [rsp+788h+var_700]
0x18009b1e9  mov     [rsp+788h+var_728], rax
0x18009b1ee  lea     rax, [rsp+788h+var_718]
0x18009b1f3  mov     qword ptr [rsp+788h+TokenType], rax; int
0x18009b1f8  lea     r9, [rsp+788h+var_668]
0x18009b200  lea     r8, [rsp+788h+var_728]
0x18009b205  lea     rdx, [rsp+788h+var_720]
0x18009b20a  lea     rcx, [rsp+788h+var_6C8]
0x18009b212  call    ??$MakeAndInitialize@VSignInResult@Internal@System@Windows@@V1234@AEAIPEAUHSTRING__@@AEAW4SignInCaller@234@PEAU5@@Details@WRL@Microsoft@@YAJPEAPEAVSignInResult@Internal@System@Windows@@AEAI$$QEAPEAUHSTRING__@@AEAW4SignInCaller@456@2@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::SignInResult,Windows::System::Internal::SignInResult,uint &,HSTRING__ *,Windows::System::Internal::SignInCaller &,HSTRING__ *>(Windows::System::Internal::SignInResult * *,uint &,HSTRING__ * &&,Windows::System::Internal::SignInCaller &,HSTRING__ * &&)
0x18009b217  mov     rcx, [rsp+788h]; this
0x18009b21f  test    eax, eax
0x18009b221  js      loc_18009E0B6
0x18009b227  lea     rdx, [rsp+788h+var_630]
0x18009b22f  lea     rcx, [rsp+788h+var_658]
0x18009b237  call    ??$As@UISignInContextPrivate@Implementation@Internal@System@Windows@@@?$ComPtr@UISignInContext@Internal@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISignInContextPrivate@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInContext>::As<Windows::System::Internal::Implementation::ISignInContextPrivate>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::ISignInContextPrivate>>)
0x18009b23c  mov     rcx, [rsp+788h]; this
0x18009b244  test    eax, eax
0x18009b246  js      loc_18009E0CA
0x18009b24c  mov     rcx, [rsp+788h+var_630]
0x18009b254  mov     rax, [rcx]
0x18009b257  lea     rdx, [rsp+788h+var_688]
0x18009b25f  mov     rax, [rax+30h]
0x18009b263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b268  mov     rcx, [rsp+788h]; this
0x18009b270  test    eax, eax
0x18009b272  js      loc_18009E0DE
0x18009b278  mov     rcx, rsi; this
0x18009b27b  call    ?GetUserStaticsInternal@UserManagerStatics@Internal@System@Windows@@AEAAPEAUIUserStaticsInternal@Implementation@234@XZ; Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(void)
0x18009b280  mov     rcx, rax
0x18009b283  mov     rax, [rax]
0x18009b286  lea     rdx, [rsp+788h+var_6F0]
0x18009b28e  mov     qword ptr [rsp+788h+TokenType], rdx; int
0x18009b293  lea     r9, [rsp+788h+var_707]
0x18009b29b  mov     r8d, [rsp+788h+var_688]
0x18009b2a3  mov     edx, [rsp+788h+var_720]
0x18009b2a7  mov     rax, [rax+88h]
0x18009b2ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b2b3  mov     rcx, [rsp+788h]; this
0x18009b2bb  test    eax, eax
0x18009b2bd  js      loc_18009E0F2
0x18009b2c3  mov     rcx, qword ptr [rsp+788h+var_6F0]
0x18009b2cb  test    rcx, rcx
0x18009b2ce  jz      loc_18009B5AC
0x18009b2d4  mov     dword ptr [rsp+788h+newString], r15d
0x18009b2dc  mov     rax, [rcx]
0x18009b2df  lea     rdx, [rsp+788h+newString]
0x18009b2e7  mov     rax, [rax+38h]
0x18009b2eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b2f0  mov     rcx, [rsp+788h]; this
0x18009b2f8  test    eax, eax
0x18009b2fa  js      loc_18009E106
0x18009b300  cmp     dword ptr [rsp+788h+newString], r12d
0x18009b308  jnz     loc_18009B410
0x18009b30e  mov     rcx, [rsp+788h+string]; string
0x18009b313  test    rcx, rcx
0x18009b316  jz      short loc_18009B34C
0x18009b318  xor     edx, edx; length
0x18009b31a  call    cs:__imp_WindowsGetStringRawBuffer
0x18009b320  mov     rbx, rax
0x18009b323  xor     edx, edx; length
0x18009b325  mov     rcx, [rsp+788h+var_700]; string
0x18009b32d  call    cs:__imp_WindowsGetStringRawBuffer
0x18009b333  mov     rdx, rbx; String2
0x18009b336  mov     rcx, rax; String1
0x18009b339  call    cs:__imp__wcsicmp
0x18009b33f  test    eax, eax
0x18009b341  jnz     loc_18009B40B
0x18009b347  jmp     loc_18009B410
0x18009b34c  mov     rdi, [rsp+788h+var_680]
0x18009b354  mov     rax, [rdi]
  ... truncated ...
```
