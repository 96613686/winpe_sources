# Windows::System::Internal::UserManagerStatics::OnUserPropertiesChanged(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180096548`
- end: `0x180096a95`
- name: `?OnUserPropertiesChanged@UserManagerStatics@Internal@System@Windows@@AEAAJPEBG00000000@Z`
- size: `1357`
- prototype: `__int64 __usercall@<rax>(Windows::System::Internal::UserManagerStatics *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800cbc20`

## callees

- `0x180007920`
- `0x1800088e8`
- `0x18000ce48`
- `0x180015540`
- `0x1800179c0`
- `0x1800181f0`
- `0x1800332e8`
- `0x18003e290`
- `0x18004ba28`
- `0x180050c38`
- `0x1800513d0`
- `0x180051470`
- `0x180094f2c`
- `0x180096548`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180096609`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009665c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180096609`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009665c`
- `ntdll!RtlIsMultiSessionSku` at `0x1800965ac`
- `ntdll!RtlIsMultiSessionSku` at `0x1800965ac`

## string_xrefs

- `0x1800965c0`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180096701`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180096a23`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180096961`: `Privileges`

## pseudocode

```c

```
