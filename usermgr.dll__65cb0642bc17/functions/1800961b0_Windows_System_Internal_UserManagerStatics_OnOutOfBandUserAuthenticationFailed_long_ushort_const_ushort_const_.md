# Windows::System::Internal::UserManagerStatics::OnOutOfBandUserAuthenticationFailed(long,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x1800961b0`
- end: `0x1800963e1`
- name: `?OnOutOfBandUserAuthenticationFailed@UserManagerStatics@Internal@System@Windows@@AEAAJJPEBG0000@Z`
- size: `561`
- prototype: `__int64 __usercall@<rax>(Windows::System::Internal::UserManagerStatics *__hidden this@<rcx>, int@<edx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800cba40`

## callees

- `0x1800088e8`
- `0x18000ce48`
- `0x1800179c0`
- `0x18003e290`
- `0x180051470`
- `0x180086db4`
- `0x180094884`
- `0x180094f2c`
- `0x1800961b0`
- `0x1800a2fec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18009630a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18009630a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009621c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180096268`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800962d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009621c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180096268`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800962d2`

## string_xrefs

- `0x1800961f4`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180096396`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`

## pseudocode

```c

```
