# LdapChaseReferral(ldap_request *,ldapmsg *,ushort *,ushort *,ushort,uchar,uchar)

- ea: `0x18002e6d4`
- end: `0x1800308f2`
- name: `?LdapChaseReferral@@YAKPEAUldap_request@@PEAUldapmsg@@PEAG2GEE@Z`
- size: `8734`
- prototype: `unsigned int __usercall@<eax>(struct ldap_request *@<rcx>, struct ldapmsg *@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned __int16, unsigned __int8, unsigned __int8)`
- caller_count: `1`
- callee_count: `32`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180046038`

## callees

- `0x1800037a8`
- `0x18000a280`
- `0x18000adb0`
- `0x18000b440`
- `0x18000cda0`
- `0x18000ce40`
- `0x180015bd8`
- `0x1800164a0`
- `0x18001ce90`
- `0x18001ef10`
- `0x180020228`
- `0x1800207ec`
- `0x180020910`
- `0x180020970`
- `0x180022e80`
- `0x1800230a0`
- `0x1800236f0`
- `0x1800245ec`
- `0x180026b50`
- `0x18002cf6c`
- `0x18002d760`
- `0x18002d8d8`
- `0x18002e6d4`
- `0x180030df0`
- `0x180032968`
- `0x180032bd8`
- `0x180032fd8`
- `0x180033048`
- `0x18003b448`
- `0x18004c2d0`
- `0x18004c3d8`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e9aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002eb6e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ebac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ed27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ee0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ee19`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002eedd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ef7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002efdb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f0bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f0f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f1f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f38e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f523`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f5b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f639`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f66f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f775`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f7f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fa18`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fa4a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fb26`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fbee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fc3b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ffa4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030008`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030018`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030102`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030112`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003021a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800302be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030534`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003058e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030696`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030704`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030727`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800307e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e9aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002eb6e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ebac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ed27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ee0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ee19`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002eedd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ef7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002efdb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f0bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f0f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f1f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f38e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f523`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f5b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f639`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f66f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f775`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f7f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fa18`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fa4a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fb26`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fbee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fc3b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ffa4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030008`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030018`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030102`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030112`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003021a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800302be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030534`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003058e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030696`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030704`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030727`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800307e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002eb1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ec35`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ec48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ec72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002edd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002edf4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ee45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ee67`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ef29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ef94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002efa3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002efcc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f023`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f03e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f1a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f1bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f36f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f3a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f3c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f42b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f4d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f547`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f600`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f61b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f71d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f735`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f7bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f7da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f9f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fa3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fa92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002faad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002face`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fb6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fb87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fbdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fcc2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fcd9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fd76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ff87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ffda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030044`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030057`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003013e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030151`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030232`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030512`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030573`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800305d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800305f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800306a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800306e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030783`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003079d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800307c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030825`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030840`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002eb1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ec35`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ec48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ec72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002edd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002edf4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ee45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ee67`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ef29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ef94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002efa3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002efcc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f023`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f03e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f1a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f1bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f36f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f3a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f3c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f42b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f4d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f547`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f600`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f61b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f71d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f735`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f7bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f7da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f9f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fa3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fa92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002faad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002face`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fb6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fb87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fbdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fcc2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fcd9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fd76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ff87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ffda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030044`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030057`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003013e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030151`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030232`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030512`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030573`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800305d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800305f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800306a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800306e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030783`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003079d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800307c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030825`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030840`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f47d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f47d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e77a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e77a`
- `WS2_32!__imp_htons` at `0x18002f0a4`
- `WS2_32!__imp_htons` at `0x18002f0a4`

## string_xrefs

- `0x18002ea50`: `HandleReferral referral number 0x%x is outside of the referralTableSize range for 0x%x\n`
- `0x18002eecc`: `Couldn't autoreconnect given cached connection 0x%x\n`
- `0x18002f06c`: `Rejecting given cached connection 0x%x\n`
- `0x18002ef6a`: `Successfully autoreconnected given cached connection 0x%x\n`

## pseudocode

```c
__int64 __fastcall LdapChaseReferral(
        struct ldap_request *a1,
        struct ldapmsg *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 a5,
        unsigned __int8 a6,
        unsigned __int8 a7)
{
  struct ldap_request *v7; // r13
  struct ldapmsg *v10; // r15
  __int64 *ConnectionPointer; // rdi
  __int64 v12; // rsi
  __int64 v13; // rdx
  const WCHAR *v14; // r8
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  int v18; // eax
  int v19; // r9d
  unsigned int v20; // r12d
  unsigned __int16 *v21; // rbx
  int v22; // r8d
  unsigned __int16 *v23; // r10
  unsigned __int16 v24; // cx
  unsigned __int16 v25; // r9
  unsigned __int8 v26; // dl
  __int64 v27; // r15
  char v28; // bl
  __int64 lm_referral; // rax
  unsigned __int16 **v30; // rax
  bool v31; // zf
  unsigned __int16 *v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // rax
  unsigned __int16 **v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r8
  void (__fastcall *v38)(_QWORD, __int64); // rax
  __int64 v39; // rbx
  _DWORD *v40; // rcx
  __int64 v41; // r8
  int CredsWide; // eax
  __int64 v43; // r8
  int v44; // ebx
  __int64 v45; // rbx
  __int64 v46; // rdx
  __int64 v47; // rcx
  const char *v48; // rbx
  __int64 v49; // rdx
  __int64 v50; // r8
  unsigned __int16 *v51; // r12
  struct _RTL_CRITICAL_SECTION *v52; // rbx
  char v53; // r8
  char v54; // al
  int v55; // r15d
  int v56; // edx
  int v57; // eax
  struct _RTL_CRITICAL_SECTION *v58; // rcx
  struct _RTL_CRITICAL_SECTION *v59; // rcx
  int v60; // r14d
  unsigned int v61; // r13d
  char v62; // bl
  unsigned __int16 *v63; // r15
  __int64 *v64; // rdi
  __int64 *v65; // r8
  __int64 *i; // rbx
  char v67; // al
  unsigned __int8 v68; // al
  char v69; // al
  int v70; // ecx
  int v71; // eax
  struct ldap_connection *Connection; // rax
  DWORD LastError; // eax
  struct _RTL_CRITICAL_SECTION *v74; // r14
  int v75; // eax
  struct _RTL_CRITICAL_SECTION *v76; // rcx
  unsigned int v77; // r13d
  char v78; // bl
  unsigned __int16 *v79; // r15
  struct _RTL_CRITICAL_SECTION *v80; // rcx
  __int64 *v81; // r14
  __int64 *v82; // r9
  __int64 *v83; // r8
  __int64 *v84; // rbx
  char v85; // al
  unsigned __int8 v86; // al
  unsigned int v87; // eax
  struct _SOCKET_ADDRESS *const *v88; // rdx
  struct sockaddr_storage *v89; // r8
  int v90; // ecx
  bool v91; // al
  __int64 v92; // rax
  int v93; // ecx
  int v94; // eax
  __int64 v95; // rbx
  struct _RTL_CRITICAL_SECTION *v96; // rcx
  struct _RTL_CRITICAL_SECTION *v97; // rcx
  __int64 v98; // r9
  int v99; // r14d
  int v100; // r15d
  __int64 v101; // rbx
  _DWORD *v102; // rcx
  __int64 v103; // r8
  int EXCredsWide; // eax
  __int64 v105; // r8
  int v106; // ebx
  __int64 v107; // rbx
  const char *v108; // rdx
  _QWORD *v109; // rax
  __int64 v110; // r9
  char v111; // al
  char v112; // bl
  void *v113; // rdx
  unsigned int v114; // eax
  unsigned __int8 (__fastcall *v115)(_QWORD, _QWORD, unsigned __int16 *, const char *, __int64, _DWORD, __int64, __int64 *, _DWORD); // r10
  unsigned int (__fastcall *v116)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD); // rax
  const char *v117; // r15
  int v118; // eax
  unsigned __int16 *v119; // r15
  __int64 v120; // rbx
  __int64 v121; // rax
  unsigned __int16 v122; // ax
  unsigned __int16 v123; // r14
  __int64 v124; // rax
  int v125; // eax
  __int64 v126; // rax
  __int64 v127; // rax
  char v128; // al
  struct _RTL_CRITICAL_SECTION *v129; // rcx
  char *v130; // r14
  int v131; // eax
  __int64 *v132; // rbx
  __int64 v133; // rcx
  __int64 **v134; // rsi
  struct _RTL_CRITICAL_SECTION *v135; // rcx
  struct _RTL_CRITICAL_SECTION *v136; // rcx
  unsigned int j; // ebx
  int cchCount2[2]; // [rsp+30h] [rbp-B9h]
  __int16 v140; // [rsp+58h] [rbp-91h]
  __int64 v141; // [rsp+60h] [rbp-89h]
  int v142; // [rsp+68h] [rbp-81h] BYREF
  __int64 v143; // [rsp+70h] [rbp-79h]
  int cchCount1; // [rsp+78h] [rbp-71h] BYREF
  __int64 v145; // [rsp+80h] [rbp-69h] BYREF
  BOOL v146; // [rsp+88h] [rbp-61h]
  PCNZWCH lpString1; // [rsp+90h] [rbp-59h]
  const char *v148; // [rsp+98h] [rbp-51h]
  unsigned __int16 *v149; // [rsp+A0h] [rbp-49h]
  void (__fastcall *v150)(_QWORD, __int64); // [rsp+A8h] [rbp-41h]
  unsigned int v151; // [rsp+B0h] [rbp-39h]
  __int64 v152; // [rsp+B8h] [rbp-31h] BYREF
  __int64 v153; // [rsp+C0h] [rbp-29h]
  struct _SecHandle v154; // [rsp+C8h] [rbp-21h] BYREF
  unsigned int (__fastcall *v155)(__int64, __int64, unsigned __int16 *, const char *, _DWORD, _QWORD, __int64 *, struct _SecHandle *); // [rsp+D8h] [rbp-11h]
  struct _SecHandle v156; // [rsp+E0h] [rbp-9h] BYREF
  char v158; // [rsp+148h] [rbp+5Fh]

  v7 = a1;
  v148 = 0;
  v143 = 0;
  v145 = 0;
  v10 = a2;
  v158 = 0;
  ConnectionPointer = 0;
  v150 = 0;
  v12 = 0;
  v141 = 0;
  v140 = 0;
  if ( (unsigned int)strlenW(a3, a2, a3) <= 0xA )
    v15 = strlenW(a3, v13, v14);
  else
    v15 = 10;
  if ( a3 && CompareStringW(0x400u, 1u, v14, v15, L"gc._msdcs.", -1) == 2 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
      LDAPClientPrint(0x800000, "Preprocessing GC referral to '%S'\n", a3);
    v18 = strlenW(a3, v16, v17);
    ldap_MoveMemory(a3, a3 + 10, (unsigned int)(2 * v18 - 18));
    if ( v19 && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
      LDAPClientPrint(0x800000, "Chasing GC referral to '%S' instead\n", a3);
  }
  v20 = FromUnicodeWithAlloc(a3);
  lpString1 = (PCNZWCH)ldap_dup_stringW(a3);
  if ( !lpString1 || v20 )
  {
    v27 = 0;
    v28 = 0;
    goto LABEL_204;
  }
  v21 = a4;
  if ( a4 )
  {
    LOWORD(v22) = *a4;
    v23 = a4;
    if ( *a4 )
    {
      while ( 1 )
      {
        ++v21;
        if ( (_WORD)v22 != 37 )
          goto LABEL_43;
        v24 = *v21;
        if ( !*v21 || (v25 = v21[1]) == 0 )
        {
LABEL_45:
          v7 = a1;
          break;
        }
        if ( HIBYTE(v24)
          || HIBYTE(v25)
          || (unsigned __int8)(v24 - 48) > 9u && (unsigned __int8)(v24 - 65) > 5u && (unsigned __int8)(v24 - 97) > 5u )
        {
          goto LABEL_43;
        }
        v26 = v25 - 48;
        if ( (unsigned __int8)(v25 - 48) > 9u && (unsigned __int8)(v25 - 65) > 5u && (unsigned __int8)(v25 - 97) > 5u )
          goto LABEL_43;
        if ( (unsigned __int8)(v24 - 48) > 9u )
        {
          if ( (unsigned __int8)(v24 - 65) > 5u )
          {
            if ( (unsigned __int8)(v24 - 97) > 5u )
              LOBYTE(v24) = 0;
            else
              LOBYTE(v24) = v24 - 87;
          }
          else
          {
            LOBYTE(v24) = v24 - 55;
          }
        }
        if ( v26 > 9u )
        {
          if ( (unsigned __int8)(v25 - 65) > 5u )
          {
            if ( (unsigned __int8)(v25 - 97) > 5u )
              v26 = 0;
            else
              v26 = v25 - 87;
          }
          else
          {
            v26 = v25 - 55;
          }
        }
        v21 += 2;
        v22 = (unsigned __int8)(v26 | (16 * v24));
        if ( v22 != 63 )
        {
LABEL_43:
          *v23 = v22;
        }
        else
        {
          *(_DWORD *)v23 = 3342428;
          v23 += 2;
          *v23 = 70;
        }
        LOWORD(v22) = *v21;
        ++v23;
        if ( !*v21 )
          goto LABEL_45;
      }
    }
    *v23 = 0;
    if ( *a4 )
    {
      v141 = LdapParseReferralDN(a4);
      v21 = a4;
      if ( !v141 )
      {
        v27 = 0;
        v28 = 0;
        goto LABEL_204;
      }
    }
    else
    {
      v21 = 0;
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 48));
  v12 = *((_QWORD *)v7 + 4);
  HIBYTE(v140) = 1;
  if ( *((_WORD *)v7 + 89) <= *((_WORD *)v7 + 90) )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
      LDAPClientPrint(0x800000, "HandleReferral hit hop count limit of 0x%x while handling 0x%x\n", 0, v7);
LABEL_54:
    v20 = 70;
LABEL_55:
    v27 = v141;
    v28 = 0;
    goto LABEL_204;
  }
  lm_referral = v10->lm_referral;
  if ( (unsigned __int16)lm_referral > *((_WORD *)v7 + 88) )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
      LDAPClientPrint(
        0x800000,
        "HandleReferral referral number 0x%x is outside of the referralTableSize range for 0x%x\n",
        v10->lm_referral,
        v7);
    goto LABEL_54;
  }
  LOBYTE(v10) = 0;
  v146 = (int)v10;
  if ( (_WORD)lm_referral )
  {
    v33 = *((_QWORD *)v7 + 21);
    v34 = lm_referral << 6;
    if ( v21 )
      v35 = (unsigned __int16 **)v141;
    else
      v35 = (unsigned __int16 **)(v33 + v34 - 56);
    v31 = *((_BYTE *)v7 + 186) == 99;
    v32 = *v35;
    v36 = *(_QWORD *)(v34 + v33 - 64);
    v149 = v32;
    v153 = v36;
    if ( v31 && *(_BYTE *)(v34 + v33 - 10) == 1 && *((_DWORD *)v7 + 58) == 1 )
      LOBYTE(v146) = 1;
    else
      v149 = v32;
  }
  else
  {
    v153 = v12;
    v30 = (unsigned __int16 **)((char *)v7 + 192);
    if ( v21 )
      v30 = (unsigned __int16 **)v141;
    v31 = *((_BYTE *)v7 + 186) == 99;
    v32 = *v30;
    v149 = *v30;
    if ( v31 )
      v146 = *((_DWORD *)v7 + 58) == 1;
  }
  v151 = CheckForExistingReferral(v7, (unsigned __int16 *)lpString1, a5, v32);
  v20 = v151;
  if ( v151 )
    goto LABEL_55;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 48));
  v38 = *(void (__fastcall **)(_QWORD, __int64))(v12 + 768);
  HIBYTE(v140) = 0;
  v155 = *(unsigned int (__fastcall **)(__int64, __int64, unsigned __int16 *, const char *, _DWORD, _QWORD, __int64 *, struct _SecHandle *))(v12 + 752);
  v150 = v38;
  if ( !v155 || *((_QWORD *)v7 + 27) )
  {
    v51 = 0;
    if ( *((_QWORD *)v7 + 27) )
      goto LABEL_195;
    cchCount1 = strlenW(lpString1, 0, v37);
    LOWORD(v142) = htons(a5);
    v60 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)(v12 + 512));
    v61 = *(_DWORD *)(v12 + 156);
    v154 = *(struct _SecHandle *)(v12 + 176);
    if ( v61 == 128 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v12 + 88));
      v62 = 0;
      if ( *(_BYTE *)(v12 + 152) && *(_QWORD *)(v12 + 128) )
      {
        DecodeUnicodeString(v12 + 136);
        *(_BYTE *)(v12 + 152) = 0;
        v62 = 1;
      }
      v51 = (unsigned __int16 *)ldap_dup_stringW(*(void **)(v12 + 80));
      v63 = (unsigned __int16 *)ldap_dup_stringW(*(void **)(v12 + 128));
      if ( !v51 && *(_QWORD *)(v12 + 80) || !v63 && *(_QWORD *)(v12 + 128) )
        v60 = 90;
      if ( v62 && !*(_BYTE *)(v12 + 152) && *(_QWORD *)(v12 + 128) )
      {
        EncodeUnicodeString(v12 + 136);
        *(_BYTE *)(v12 + 152) = 1;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 88));
    }
    else
    {
      v63 = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 512));
    if ( v60 )
    {
      ldapSecureFree(v63, 1768838476);
      ldapFree(v51, 1768838476);
LABEL_162:
      v7 = a1;
      v20 = v60;
      goto LABEL_55;
    }
    EnterCriticalSection(&ConnectionListLock);
    v64 = (__int64 *)GlobalListActiveConnections;
    v65 = 0;
    for ( i = 0; v64 != &GlobalListActiveConnections; i = v65 )
    {
      i = v64 - 1;
      if ( *((_BYTE *)v64 + 544) != 2
        && *((_BYTE *)i + 553) == 8
        && (*((_DWORD *)i + 17) > (unsigned int)v65 || *((_DWORD *)i + 18) > (unsigned int)v65)
        && *((_BYTE *)i + 554) == (_BYTE)v65
        && *((_WORD *)i + 117) == (_WORD)v142 )
      {
        if ( DoSigningOptionsMatch((struct ldap_connection *)v12, (struct ldap_connection *)(v64 - 1)) )
        {
          if ( *((_BYTE *)i + 193) == *(_BYTE *)(v12 + 193) )
          {
            v67 = *((_BYTE *)i + 646);
            if ( v67 == *(_BYTE *)(v12 + 646) && (a7 == (_BYTE)v65 || v67) )
            {
              v68 = DoCredentialsMatch((struct ldap_connection *)(v64 - 1), v61, &v154, v51, v63);
              v65 = 0;
              if ( v68 )
              {
                if ( *((_DWORD *)i + 250) >= *(_DWORD *)(v12 + 1000) )
                {
                  v69 = ldapWStringsIdentical(lpString1, cchCount1, (PCNZWCH)i[54], -1);
                  v65 = 0;
                  if ( v69 )
                  {
                    v70 = *(_DWORD *)(v12 + 168);
                    if ( v70 == *((_DWORD *)i + 42) )
                    {
                      v71 = *(_DWORD *)(v12 + 172);
                      if ( v71 == *((_DWORD *)i + 43) && (v71 || v70) )
                        break;
                    }
                  }
                }
              }
            }
          }
        }
      }
      v64 = (__int64 *)*v64;
    }
    ldapSecureFree(v63, 1768838476);
    ldapFree(v51, 1768838476);
    v51 = 0;
    if ( !i )
    {
      v58 = &ConnectionListLock;
LABEL_194:
      LeaveCriticalSection(v58);
      goto LABEL_195;
    }
    ConnectionPointer = (__int64 *)ReferenceLdapConnection(i);
    LeaveCriticalSection(&ConnectionListLock);
    if ( !ConnectionPointer )
      goto LABEL_195;
    v52 = (struct _RTL_CRITICAL_SECTION *)(ConnectionPointer + 64);
    EnterCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 64));
    if ( !*((_DWORD *)ConnectionPointer + 17) && !*((_DWORD *)ConnectionPointer + 18) )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 64));
      goto LABEL_120;
    }
    ++*((_DWORD *)ConnectionPointer + 18);
    LeaveCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 64));
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
      LDAPClientPrint(0x800000, "HandleReferral: Found existing connection to '%S'\n", lpString1);
LABEL_411:
    v7 = a1;
LABEL_412:
    v28 = 1;
    v158 = 1;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 48));
    v118 = *((unsigned __int16 *)v7 + 90);
    HIBYTE(v140) = 1;
    if ( *((_WORD *)v7 + 89) <= (unsigned __int16)v118 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
        LDAPClientPrint(0x800000, "HandleReferral hit hop count limit of 0x%x while handling 0x%x\n", v118, (_DWORD)v7);
      v20 = 70;
      goto LABEL_399;
    }
    v119 = v149;
    v20 = CheckForExistingReferral(
            v7,
            (unsigned __int16 *)ConnectionPointer[54],
            *((_WORD *)ConnectionPointer + 253),
            v149);
    if ( v20 )
    {
LABEL_399:
      v27 = v141;
      goto LABEL_204;
    }
    v120 = *((_QWORD *)v7 + 21);
    if ( !v120 )
    {
      v121 = ldapMalloc(*((unsigned __int16 *)v7 + 89) << 6, 1632916044);
      v120 = v121;
      if ( !v121 )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
          LDAPClientPrint(0x800000, "HandleReferral could not allocate ref table while handling 0x%x\n", v7);
        goto LABEL_425;
      }
      *((_QWORD *)v7 + 21) = v121;
      *((_WORD *)v7 + 88) = *((_WORD *)v7 + 89);
    }
    v122 = *((_WORD *)v7 + 88);
    v123 = 1;
    if ( !v122 )
      goto LABEL_430;
    while ( *(_QWORD *)v120 )
    {
      ++v123;
      v120 += 64;
      if ( v123 > v122 )
        goto LABEL_430;
    }
    if ( v123 > v122 )
    {
LABEL_430:
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
        LDAPClientPrint(0x800000, "HandleReferral ref table full(0x%x) while handling 0x%x\n", v123, (_DWORD)v7);
      v20 = 70;
      goto LABEL_202;
    }
    v124 = ldap_dup_stringW(v119);
    if ( v124 || !v119 )
    {
      v27 = v141;
      *(_QWORD *)v120 = ConnectionPointer;
      *(_WORD *)(v120 + 52) = v123;
      *(_QWORD *)(v120 + 8) = v124;
      if ( v141 )
        v125 = *(_DWORD *)(v141 + 20);
      else
        v125 = 3;
      *(_DWORD *)(v120 + 16) = v125;
      if ( v141 )
        v126 = *(_QWORD *)(v141 + 24);
      else
        v126 = 0;
      *(_QWORD *)(v120 + 24) = v126;
      if ( v141 )
        v127 = *(_QWORD *)(v141 + 8);
      else
        v127 = 0;
      *(_QWORD *)(v120 + 32) = v127;
      *(_BYTE *)(v120 + 55) = v140;
      LOBYTE(v140) = 0;
      if ( !v146 || (v128 = 0, !a6) )
        v128 = 1;
      *(_BYTE *)(v120 + 54) = v128;
      ++*((_WORD *)v7 + 90);
      ConnectionPointer = (__int64 *)ReferenceLdapConnection(ConnectionPointer);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 48));
      v20 = LdapSendCommand((struct ldap_connection *)ConnectionPointer, v7);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 48));
      if ( v20 )
      {
        *(_QWORD *)v120 = 0;
        ldapFree(*(_QWORD *)(v120 + 8), 1313100364);
        *(_QWORD *)(v120 + 8) = 0;
        --*((_WORD *)v7 + 90);
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 48));
        HIBYTE(v140) = 0;
        EnterCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 64));
        --*(_DWORD *)ConnectionPointer;
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
          LDAPClientPrint(
            4,
            "LDAP deref conn 0x%x, new count = 0x%x\n",
            (_DWORD)ConnectionPointer,
            *(_DWORD *)ConnectionPointer);
        v129 = (struct _RTL_CRITICAL_SECTION *)(ConnectionPointer + 64);
        if ( *(_DWORD *)ConnectionPointer )
        {
          LeaveCriticalSection(v129);
        }
        else
        {
          LeaveCriticalSection(v129);
          DereferenceLdapConnection2((__int64)ConnectionPointer, 1);
        }
      }
      else
      {
        v130 = (char *)v7 + 216;
        HIBYTE(v140) = 1;
        if ( *((_QWORD *)v7 + 27) )
        {
          v131 = g_fTracingOn;
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x8000) != 0 )
          {
            LDAPClientTraceEvent(0x8000, "The parent search was a paged request\n");
            v131 = g_fTracingOn;
            v130 = (char *)v7 + 216;
          }
          if ( ConnectionPointer )
          {
            if ( v131 && g_fProviderEnabled && (g_ulTraceFlags & 0x8000) != 0 )
              LDAPClientPrint(
                0x8000,
                "Hooking up new connection 0x%x to request 0x%x\n",
                (_DWORD)ConnectionPointer,
                *((_QWORD *)v7 + 27));
            EnterCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 64));
            ++*((_DWORD *)ConnectionPointer + 18);
            LeaveCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 64));
            ConnectionPointer = (__int64 *)ReferenceLdapConnection(ConnectionPointer);
            *(_QWORD *)(*(_QWORD *)v130 + 40LL) = ConnectionPointer;
          }
        }
      }
      goto LABEL_203;
    }
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
      LDAPClientPrint(0x800000, "HandleReferral could not allocate dn while handling 0x%x\n", v7);
LABEL_425:
    v20 = 90;
    goto LABEL_202;
  }
  v152 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(v12 + 512));
  v152 = *(_QWORD *)(v12 + 168);
  if ( *(_DWORD *)(v12 + 156) == 128 || (v39 = *(_QWORD *)(v12 + 128)) == 0 )
  {
    v45 = v143;
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v12 + 88));
    if ( *(_BYTE *)(v12 + 152) )
    {
      DecodeUnicodeString(v12 + 136);
      *(_BYTE *)(v12 + 152) = 0;
    }
    v40 = *(_DWORD **)(v12 + 128);
    if ( (unsigned int)(*v40 - 1) > 0xFFFE )
    {
      v43 = *(_DWORD *)(v39 + 44) >> 1;
      LOBYTE(v43) = (*(_DWORD *)(v39 + 44) & 2) != 0;
      CredsWide = LdapMakeCredsWide(v40, &v145, v43);
    }
    else
    {
      v41 = v40[13] >> 1;
      LOBYTE(v41) = (v40[13] & 2) != 0;
      CredsWide = LdapMakeEXCredsWide(v40, &v145, v41);
    }
    v44 = CredsWide;
    if ( !*(_BYTE *)(v12 + 152) )
    {
      EncodeUnicodeString(v12 + 136);
      *(_BYTE *)(v12 + 152) = 1;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 88));
    if ( v44 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 512));
      v143 = v145;
      goto LABEL_55;
    }
    v45 = v145;
    v143 = v145;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 512));
  v46 = *(_QWORD *)(v153 + 448);
  v47 = *(_QWORD *)(v12 + 448);
  *(_QWORD *)cchCount2 = v45;
  v48 = v148;
  v154.dwLower = 0;
  if ( v155(v47, v46, a4, v148, a5, *(_QWORD *)cchCount2, &v152, &v154) )
    goto LABEL_55;
  v51 = 0;
  ConnectionPointer = (__int64 *)GetConnectionPointer(v154.dwLower, v49, v50);
  if ( !ConnectionPointer )
    goto LABEL_195;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
    LDAPClientPrint(0x800000, "HandleReferral: Given existing connection to '%s'\n", v48);
  v52 = (struct _RTL_CRITICAL_SECTION *)(ConnectionPointer + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 64));
  if ( !*((_DWORD *)ConnectionPointer + 17) && !*((_DWORD *)ConnectionPointer + 18)
    || *((_BYTE *)ConnectionPointer + 553) != 8 && !*((_BYTE *)ConnectionPointer + 555)
    || !DoSigningOptionsMatch((struct ldap_connection *)v12, (struct ldap_connection *)ConnectionPointer)
    || *((_BYTE *)ConnectionPointer + 193) != *(_BYTE *)(v12 + 193)
    || (v54 = *((_BYTE *)ConnectionPointer + 646), v54 != *(_BYTE *)(v12 + 646))
    || a7 && !v54
    || *((_DWORD *)ConnectionPointer + 250) < *(_DWORD *)(v12 + 1000) )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 64));
    EnterCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 64));
    --*(_DWORD *)ConnectionPointer;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
      LDAPClientPrint(
        4,
        "LDAP deref conn 0x%x, new count = 0x%x\n",
        (_DWORD)ConnectionPointer,
        *(_DWORD *)ConnectionPointer);
    v59 = (struct _RTL_CRITICAL_SECTION *)(ConnectionPointer + 64);
    if ( *(_DWORD *)ConnectionPointer )
    {
      LeaveCriticalSection(v59);
    }
    else
    {
      LeaveCriticalSection(v59);
      DereferenceLdapConnection2((__int64)ConnectionPointer, 1);
    }
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
      LDAPClientPrint(0x800000, "Rejecting given cached connection 0x%x\n", (_DWORD)ConnectionPointer);
    goto LABEL_195;
  }
  if ( v53 != 16 && !*((_BYTE *)ConnectionPointer + 554) )
  {
    ++*((_DWORD *)ConnectionPointer + 18);
    LeaveCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 64));
    LOBYTE(v140) = 1;
    v150 = (void (__fastcall *)(_QWORD, __int64))ConnectionPointer[96];
    goto LABEL_412;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 64));
  EnterCriticalSection((LPCRITICAL_SECTION)ConnectionPointer + 14);
  EnterCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 64));
  if ( *((_BYTE *)ConnectionPointer + 553) != 16 && !*((_BYTE *)ConnectionPointer + 554) )
  {
LABEL_131:
    ++*((_DWORD *)ConnectionPointer + 18);
    LeaveCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 64));
    LeaveCriticalSection((LPCRITICAL_SECTION)ConnectionPointer + 14);
    LOBYTE(v140) = 1;
    v150 = (void (__fastcall *)(_QWORD, __int64))ConnectionPointer[96];
    goto LABEL_412;
  }
  *((_BYTE *)ConnectionPointer + 553) = 4;
  LeaveCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 64));
  v55 = LdapAutoReconnect((struct ldap_connection *)ConnectionPointer);
  if ( !v55 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
      LDAPClientPrint(
        0x800000,
        "Successfully autoreconnected given cached connection 0x%x\n",
        (_DWORD)ConnectionPointer);
    EnterCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 64));
    goto LABEL_131;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)ConnectionPointer + 14);
  v56 = g_fTracingOn;
  if ( g_fTracingOn )
  {
    v57 = g_fProviderEnabled;
    if ( g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
    {
      LDAPClientPrint(
        0x100000,
        "LdapWaitForResponseFromServer: reconnect returned 0x%x for 0x%x\n",
        v55,
        (_DWORD)ConnectionPointer);
      v56 = g_fTracingOn;
      v57 = g_fProviderEnabled;
    }
    if ( v56 && v57 && (g_ulTraceFlags & 0x800000) != 0 )
      LDAPClientPrint(0x800000, "Couldn't autoreconnect given cached connection 0x%x\n", (_DWORD)ConnectionPointer);
  }
LABEL_120:
  EnterCriticalSection(v52);
  --*(_DWORD *)ConnectionPointer;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
    LDAPClientPrint(
      4,
      "LDAP deref conn 0x%x, new count = 0x%x\n",
      (_DWORD)ConnectionPointer,
      *(_DWORD *)ConnectionPointer);
  v58 = v52;
  if ( *(_DWORD *)ConnectionPointer )
    goto LABEL_194;
  LeaveCriticalSection(v52);
  DereferenceLdapConnection2((__int64)ConnectionPointer, 1);
LABEL_195:
  Connection = (struct ldap_connection *)LdapAllocateConnection((void *)lpString1, a5, a7, 0);
  ConnectionPointer = (__int64 *)Connection;
  if ( !Connection )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
    {
      LastError = GetLastError();
      LDAPClientPrint(0x2000000, "HandleReferral failed to allocate, error 0x%x.\n", LastError);
    }
LABEL_200:
    v20 = 52;
    goto LABEL_201;
  }
  v75 = LdapConnect(Connection, 0, 0);
  if ( v75 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
      LDAPClientPrint(0x2000000, "HandleReferral failed to connect, error 0x%x.\n", v75);
    CloseLdapConnection((struct ldap_connection *)ConnectionPointer);
    EnterCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 64));
    --*(_DWORD *)ConnectionPointer;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
      LDAPClientPrint(
        4,
        "LDAP deref conn 0x%x, new count = 0x%x\n",
        (_DWORD)ConnectionPointer,
        *(_DWORD *)ConnectionPointer);
    v76 = (struct _RTL_CRITICAL_SECTION *)(ConnectionPointer + 64);
    if ( *(_DWORD *)ConnectionPointer )
    {
      LeaveCriticalSection(v76);
    }
    else
    {
      LeaveCriticalSection(v76);
      DereferenceLdapConnection2((__int64)ConnectionPointer, 1);
    }
    ConnectionPointer = 0;
    goto LABEL_200;
  }
  v60 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(v12 + 512));
  v77 = *(_DWORD *)(v12 + 156);
  v156 = *(struct _SecHandle *)(v12 + 176);
  if ( v77 == 128 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v12 + 88));
    v78 = 0;
    if ( *(_BYTE *)(v12 + 152) && *(_QWORD *)(v12 + 128) )
    {
      DecodeUnicodeString(v12 + 136);
      *(_BYTE *)(v12 + 152) = 0;
      v78 = 1;
    }
    v51 = (unsigned __int16 *)ldap_dup_stringW(*(void **)(v12 + 80));
    v79 = (unsigned __int16 *)ldap_dup_stringW(*(void **)(v12 + 128));
    if ( !v51 && *(_QWORD *)(v12 + 80) || !v79 && *(_QWORD *)(v12 + 128) )
      v60 = 90;
    if ( v78 && !*(_BYTE *)(v12 + 152) && *(_QWORD *)(v12 + 128) )
    {
      EncodeUnicodeString(v12 + 136);
      *(_BYTE *)(v12 + 152) = 1;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 88));
  }
  else
  {
    v79 = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 512));
  if ( v60 )
  {
    ldapSecureFree(v79, 1768838476);
    ldapFree(v51, 1768838476);
    CloseLdapConnection((struct ldap_connection *)ConnectionPointer);
    EnterCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 64));
    --*(_DWORD *)ConnectionPointer;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
      LDAPClientPrint(
        4,
        "LDAP deref conn 0x%x, new count = 0x%x\n",
        (_DWORD)ConnectionPointer,
        *(_DWORD *)ConnectionPointer);
    v80 = (struct _RTL_CRITICAL_SECTION *)(ConnectionPointer + 64);
    if ( *(_DWORD *)ConnectionPointer )
    {
      LeaveCriticalSection(v80);
    }
    else
    {
      LeaveCriticalSection(v80);
      DereferenceLdapConnection2((__int64)ConnectionPointer, 1);
    }
    ConnectionPointer = 0;
    goto LABEL_162;
  }
  EnterCriticalSection(&ConnectionListLock);
  v81 = (__int64 *)GlobalListActiveConnections;
  v82 = &GlobalListActiveConnections;
  v83 = 0;
  while ( 1 )
  {
    v84 = v83;
    if ( v81 == v82 )
      break;
    v84 = v81 - 1;
    if ( v81 - 1 != ConnectionPointer && *((_BYTE *)v84 + 552) != 2 && *((_BYTE *)v84 + 640) == (_BYTE)v83 )
    {
      if ( DoSigningOptionsMatch((struct ldap_connection *)v12, (struct ldap_connection *)(v81 - 1)) )
      {
        if ( *((_BYTE *)v84 + 193) == *(_BYTE *)(v12 + 193) )
        {
          v85 = *((_BYTE *)v84 + 646);
          if ( v85 == *(_BYTE *)(v12 + 646) && (a7 == (_BYTE)v83 || v85) )
          {
            v86 = DoCredentialsMatch((struct ldap_connection *)(v81 - 1), v77, &v156, v51, v79);
            v83 = 0;
            if ( !v86
              || *((_DWORD *)v84 + 250) < *(_DWORD *)(v12 + 1000)
              || *((_BYTE *)v84 + 553) != 8
              || *((_BYTE *)v84 + 554)
              || !*((_DWORD *)v84 + 17) && !*((_DWORD *)v84 + 18) )
            {
              goto LABEL_284;
            }
            v87 = *((_DWORD *)v84 + 93);
            if ( v87 )
            {
              v88 = (struct _SOCKET_ADDRESS *const *)v84[47];
              v89 = (struct sockaddr_storage *)(ConnectionPointer + 29);
              v90 = *((_DWORD *)ConnectionPointer + 92);
              goto LABEL_270;
            }
            v87 = *((_DWORD *)ConnectionPointer + 93);
            v90 = *((_DWORD *)v84 + 92);
            if ( v87 )
            {
              v88 = (struct _SOCKET_ADDRESS *const *)ConnectionPointer[47];
              v89 = (struct sockaddr_storage *)(v84 + 29);
LABEL_270:
              v91 = IsSocketAddressExists(v87, v88, v89, v90);
              v83 = 0;
              if ( !v91 )
              {
LABEL_284:
                v82 = &GlobalListActiveConnections;
                goto LABEL_285;
              }
            }
            else
            {
              if ( *((_DWORD *)ConnectionPointer + 92) != v90
                || *((_WORD *)ConnectionPointer + 117) != *((_WORD *)v84 + 117) )
              {
                goto LABEL_284;
              }
              if ( v90 != 2 || *((_DWORD *)ConnectionPointer + 59) != *((_DWORD *)v84 + 59) )
              {
                if ( v90 != 23 )
                  goto LABEL_284;
                v92 = ConnectionPointer[30] - v84[30];
                if ( !v92 )
                  v92 = ConnectionPointer[31] - v84[31];
                if ( v92 )
                  goto LABEL_284;
              }
            }
            v93 = *(_DWORD *)(v12 + 168);
            if ( v93 == *((_DWORD *)v84 + 42) )
            {
              v94 = *(_DWORD *)(v12 + 172);
              if ( v94 == *((_DWORD *)v84 + 43) && (v94 || v93) )
                break;
            }
            goto LABEL_284;
          }
        }
      }
    }
LABEL_285:
    v81 = (__int64 *)*v81;
  }
  ldapSecureFree(v79, 1768838476);
  ldapFree(v51, 1768838476);
  if ( v84 )
  {
    v95 = ReferenceLdapConnection(v84);
    LeaveCriticalSection(&ConnectionListLock);
    if ( v95 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v95 + 512));
      if ( *(_DWORD *)(v95 + 68) || *(_DWORD *)(v95 + 72) )
      {
        ++*(_DWORD *)(v95 + 72);
        LeaveCriticalSection((LPCRITICAL_SECTION)(v95 + 512));
        if ( !*(_DWORD *)(v95 + 372) && *((_DWORD *)ConnectionPointer + 93) )
        {
          *(_QWORD *)(v95 + 376) = ConnectionPointer[47];
          *(_DWORD *)(v95 + 372) = *((_DWORD *)ConnectionPointer + 93);
          ConnectionPointer[47] = 0;
          *((_DWORD *)ConnectionPointer + 93) = 0;
        }
        CloseLdapConnection((struct ldap_connection *)ConnectionPointer);
        EnterCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 64));
        --*(_DWORD *)ConnectionPointer;
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
          LDAPClientPrint(
            4,
            "LDAP deref conn 0x%x, new count = 0x%x\n",
            (_DWORD)ConnectionPointer,
            *(_DWORD *)ConnectionPointer);
        v97 = (struct _RTL_CRITICAL_SECTION *)(ConnectionPointer + 64);
        if ( *(_DWORD *)ConnectionPointer )
        {
          LeaveCriticalSection(v97);
        }
        else
        {
          LeaveCriticalSection(v97);
          DereferenceLdapConnection2((__int64)ConnectionPointer, 1);
        }
        ConnectionPointer = (__int64 *)v95;
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
          LDAPClientPrint(0x800000, "HandleReferral: Found existing connection to '%S'\n", lpString1);
      }
      else
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)(v95 + 512));
        EnterCriticalSection((LPCRITICAL_SECTION)(v95 + 512));
        --*(_DWORD *)v95;
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
          LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", v95, *(_DWORD *)v95);
        v96 = (struct _RTL_CRITICAL_SECTION *)(v95 + 512);
        if ( *(_DWORD *)v95 )
        {
          LeaveCriticalSection(v96);
        }
        else
        {
          LeaveCriticalSection(v96);
          DereferenceLdapConnection2(v95, 1);
        }
        v95 = 0;
      }
      if ( v95 )
        goto LABEL_411;
    }
  }
  else
  {
    LeaveCriticalSection(&ConnectionListLock);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(v12 + 512));
  v99 = *(_DWORD *)(v12 + 156);
  v100 = 128;
  if ( v99 == 128 || (v101 = *(_QWORD *)(v12 + 128)) == 0 )
  {
    v107 = v143;
  }
  else
  {
    if ( v143 )
    {
      ldapSecureFree(v143, 1667593036);
      v145 = 0;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(v12 + 88));
    if ( *(_BYTE *)(v12 + 152) )
    {
      DecodeUnicodeString(v12 + 136);
      *(_BYTE *)(v12 + 152) = 0;
    }
    v102 = *(_DWORD **)(v12 + 128);
    if ( (unsigned int)(*v102 - 1) > 0xFFFE )
    {
      v105 = *(_DWORD *)(v101 + 44) >> 1;
      LOBYTE(v105) = (*(_DWORD *)(v101 + 44) & 2) != 0;
      EXCredsWide = LdapMakeCredsWide(v102, &v145, v105);
    }
    else
    {
      v103 = v102[13] >> 1;
      LOBYTE(v103) = (v102[13] & 2) != 0;
      EXCredsWide = LdapMakeEXCredsWide(v102, &v145, v103);
    }
    v106 = EXCredsWide;
    if ( !*(_BYTE *)(v12 + 152) )
    {
      EncodeUnicodeString(v12 + 136);
      *(_BYTE *)(v12 + 152) = 1;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 88));
    if ( v106 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 512));
      CloseLdapConnection((struct ldap_connection *)ConnectionPointer);
      v20 = v151;
      v143 = v145;
      goto LABEL_201;
    }
    v107 = v145;
    v143 = v145;
  }
  v142 = 1;
  if ( !*(_BYTE *)(v12 + 646) )
  {
LABEL_343:
    if ( *(_BYTE *)(v12 + 192) )
    {
      LOBYTE(v98) = 1;
      v20 = LdapSetConnectionOption(ConnectionPointer, 149, &v142, v98);
      if ( v20 )
      {
        if ( !g_fTracingOn || !g_fProviderEnabled || (g_ulTraceFlags & 0x800000) == 0 )
          goto LABEL_338;
        v108 = "Unable to setup Signing on referral connection\n";
        goto LABEL_337;
      }
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
        LDAPClientTraceEvent(0x800000, "Successfully setup Signing on referral connection\n");
    }
    if ( *(_BYTE *)(v12 + 193) )
    {
      LOBYTE(v98) = 1;
      v20 = LdapSetConnectionOption(ConnectionPointer, 150, &v142, v98);
      if ( v20 )
      {
        if ( !g_fTracingOn || !g_fProviderEnabled || (g_ulTraceFlags & 0x800000) == 0 )
          goto LABEL_338;
        v108 = "Unable to setup Sealing on referral connection\n";
        goto LABEL_337;
      }
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
        LDAPClientTraceEvent(0x800000, "Successfully setup Sealing on referral connection\n");
    }
    LOBYTE(v98) = 1;
    cchCount1 = *(_DWORD *)(v12 + 1000);
    v20 = LdapSetConnectionOption(ConnectionPointer, 17, &cchCount1, v98);
    if ( v20 )
    {
      if ( !g_fTracingOn || !g_fProviderEnabled || (g_ulTraceFlags & 0x800000) == 0 )
        goto LABEL_338;
      v108 = "Unable to set version on referral connection\n";
LABEL_337:
      LDAPClientTraceEvent(0x800000, v108);
      goto LABEL_338;
    }
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
      LDAPClientPrint(0x800000, "Successfully set version=%ul on referral connection\n", cchCount1);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 512));
    ++*((_DWORD *)ConnectionPointer + 18);
    EnterCriticalSection(&ConnectionListLock);
    v109 = (_QWORD *)qword_180065830;
    ConnectionPointer[2] = qword_180065830;
    ConnectionPointer[1] = (__int64)&GlobalListActiveConnections;
    *v109 = ConnectionPointer + 1;
    qword_180065830 = (__int64)(ConnectionPointer + 1);
    LeaveCriticalSection(&ConnectionListLock);
    if ( !GlobalParallelRecvMode )
      LdapWakeupSelect();
    v110 = v107;
    if ( v107 || !v99 )
    {
      v111 = 0;
      v112 = 0;
      if ( !v99 )
      {
        v110 = 0;
LABEL_386:
        if ( v111 )
          v113 = *(void **)(v12 + 80);
        else
          v113 = 0;
        v114 = LdapBind((struct ldap_connection *)ConnectionPointer, v113, v100, v110, 1u);
        v20 = v114;
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
          LDAPClientPrint(0x800000, "HandleReferral: Bind to host '%S' returned 0x%x\n", lpString1, v114);
        if ( v112 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)(v12 + 512));
          EnterCriticalSection((LPCRITICAL_SECTION)(v12 + 88));
          if ( !*(_BYTE *)(v12 + 152) )
          {
            EncodeUnicodeString(v12 + 136);
            *(_BYTE *)(v12 + 152) = 1;
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 88));
          LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 512));
        }
        if ( !v20 )
        {
          *((_DWORD *)ConnectionPointer + 42) = *(_DWORD *)(v12 + 168);
          *((_DWORD *)ConnectionPointer + 43) = *(_DWORD *)(v12 + 172);
          v115 = *(unsigned __int8 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, const char *, __int64, _DWORD, __int64, __int64 *, _DWORD))(v12 + 760);
          v116 = (unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD))v155;
          ConnectionPointer[95] = (__int64)v115;
          ConnectionPointer[94] = (__int64)v116;
          ConnectionPointer[96] = *(_QWORD *)(v12 + 768);
          if ( v115 )
          {
            v117 = v148;
            if ( v115(
                   *(_QWORD *)(v12 + 448),
                   *(_QWORD *)(v153 + 448),
                   a4,
                   v148,
                   ConnectionPointer[56],
                   a5,
                   v143,
                   ConnectionPointer + 21,
                   0) )
            {
              EnterCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 64));
              ++*((_DWORD *)ConnectionPointer + 17);
              LeaveCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 64));
              if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
                LDAPClientPrint(
                  0x800000,
                  "HandleReferral: Handle was given to callee for host '%s', 0x%x\n",
                  v117,
                  (_DWORD)ConnectionPointer);
              LOBYTE(v140) = 1;
            }
            else if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
            {
              LDAPClientPrint(
                0x800000,
                "HandleReferral: Handle was not given to callee for host '%s', 0x%x\n",
                v117,
                (_DWORD)ConnectionPointer);
            }
          }
          goto LABEL_411;
        }
        v7 = a1;
        v28 = 1;
        goto LABEL_399;
      }
    }
    else
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v12 + 512));
      EnterCriticalSection((LPCRITICAL_SECTION)(v12 + 88));
      if ( *(_BYTE *)(v12 + 152) )
      {
        DecodeUnicodeString(v12 + 136);
        *(_BYTE *)(v12 + 152) = 0;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 88));
      LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 512));
      v110 = *(_QWORD *)(v12 + 128);
      v111 = 0;
      v112 = 1;
    }
    if ( v99 == 128 && !*((_BYTE *)ConnectionPointer + 646) )
      v110 = 0;
    else
      v111 = 1;
    v100 = v99;
    goto LABEL_386;
  }
  LOBYTE(v98) = 1;
  v20 = LdapSetConnectionOption(ConnectionPointer, 10, &v142, v98);
  if ( !v20 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
      LDAPClientTraceEvent(0x800000, "Successfully setup SSL session on referral connection\n");
    goto LABEL_343;
  }
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
  {
    v108 = "Unable to setup SSL session on referral connection\n";
    goto LABEL_337;
  }
LABEL_338:
  LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 512));
  CloseLdapConnection((struct ldap_connection *)ConnectionPointer);
LABEL_201:
  v7 = a1;
LABEL_202:
  v27 = v141;
LABEL_203:
  v28 = v158;
LABEL_204:
  ldapFree(v148, 1936605516);
  ldapFree(lpString1, 1768838476);
  v74 = (struct _RTL_CRITICAL_SECTION *)((char *)v7 + 48);
  if ( HIBYTE(v140) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 48));
  if ( (_BYTE)v140 && v150 )
    v150(*(_QWORD *)(v12 + 448), ConnectionPointer[56]);
  if ( v20 )
  {
    if ( v28 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 64));
      --*((_DWORD *)ConnectionPointer + 18);
      if ( *((_DWORD *)ConnectionPointer + 17) || *((_DWORD *)ConnectionPointer + 18) )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 64));
      }
      else
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 64));
        CloseLdapConnection((struct ldap_connection *)ConnectionPointer);
      }
    }
  }
  else if ( !*((_QWORD *)v7 + 27) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 48));
    v132 = (__int64 *)((char *)v7 + 40);
    v133 = *((_QWORD *)v7 + 5);
    if ( v133 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v133 + 512));
      --*(_DWORD *)*v132;
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
      {
        LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", *v132, *(_DWORD *)*v132);
        v134 = (__int64 **)((char *)v7 + 40);
      }
      else
      {
        v134 = (__int64 **)((char *)v7 + 40);
      }
      v135 = (struct _RTL_CRITICAL_SECTION *)(*v132 + 512);
      if ( *(_DWORD *)*v132 )
      {
        LeaveCriticalSection(v135);
      }
      else
      {
        LeaveCriticalSection(v135);
        DereferenceLdapConnection2(*v132, 1);
      }
      *v134 = 0;
      v74 = (struct _RTL_CRITICAL_SECTION *)((char *)v7 + 48);
    }
    else
    {
      v134 = (__int64 **)((char *)v7 + 40);
    }
    ReferenceLdapConnection(ConnectionPointer);
    *v134 = ConnectionPointer;
    LeaveCriticalSection(v74);
  }
  if ( ConnectionPointer )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 64));
    --*(_DWORD *)ConnectionPointer;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
      LDAPClientPrint(
        4,
        "LDAP deref conn 0x%x, new count = 0x%x\n",
        (_DWORD)ConnectionPointer,
        *(_DWORD *)ConnectionPointer);
    v136 = (struct _RTL_CRITICAL_SECTION *)(ConnectionPointer + 64);
    if ( *(_DWORD *)ConnectionPointer )
    {
      LeaveCriticalSection(v136);
    }
    else
    {
      LeaveCriticalSection(v136);
      DereferenceLdapConnection2((__int64)ConnectionPointer, 1);
    }
  }
  if ( v143 )
    ldapSecureFree(v143, 1667593036);
  if ( v27 )
  {
    ldapFree(*(_QWORD *)v27, 1819432268);
    ldapFree(*(_QWORD *)(v27 + 24), 1819432268);
    ldapFree(*(_QWORD *)(v27 + 32), 1819432268);
    ldapFree(*(_QWORD *)(v27 + 40), 1819432268);
    if ( *(_QWORD *)(v27 + 8) )
    {
      for ( j = 0; j < *(_DWORD *)(v27 + 16); ++j )
        ldapFree(*(_QWORD *)(*(_QWORD *)(v27 + 8) + 8LL * j), 1819432268);
    }
    ldapFree(*(_QWORD *)(v27 + 8), 1819432268);
    ldapFree(v27, 1819432268);
  }
  return v20;
}

```

## disassembly

```asm
0x18002e6d4  mov     rax, rsp
0x18002e6d7  mov     [rax+10h], rbx
0x18002e6db  mov     [rax+20h], r9
0x18002e6df  mov     [rax+8], rcx
0x18002e6e3  push    rbp
0x18002e6e4  push    rsi
0x18002e6e5  push    rdi
0x18002e6e6  push    r12
0x18002e6e8  push    r13
0x18002e6ea  push    r14
0x18002e6ec  push    r15
0x18002e6ee  lea     rbp, [rax-47h]
0x18002e6f2  sub     rsp, 0F0h
0x18002e6f9  xor     r12d, r12d
0x18002e6fc  mov     r13, rcx
0x18002e6ff  mov     eax, r12d
0x18002e702  mov     [rbp+3Fh+var_90], r12
0x18002e706  mov     rcx, r8
0x18002e709  mov     [rbp+3Fh+var_B8], rax
0x18002e70d  mov     [rbp+3Fh+var_A8], rax
0x18002e711  mov     r14, r9
0x18002e714  mov     rbx, r8
0x18002e717  mov     byte ptr [rsp+120h+var_D0+1], r12b
0x18002e71c  mov     r15, rdx
0x18002e71f  mov     [rbp+3Fh+arg_10], r12b
0x18002e723  mov     edi, r12d
0x18002e726  mov     [rbp+3Fh+var_80], r12
0x18002e72a  mov     esi, r12d
0x18002e72d  mov     [rsp+120h+var_C8], r12
0x18002e732  mov     byte ptr [rsp+120h+var_D0], r12b
0x18002e737  call    strlenW
0x18002e73c  cmp     eax, 0Ah
0x18002e73f  jbe     short loc_18002E748
0x18002e741  lea     eax, [r12+0Ah]
0x18002e746  jmp     short loc_18002E750
0x18002e748  mov     rcx, rbx
0x18002e74b  call    strlenW
0x18002e750  test    rbx, rbx
0x18002e753  jz      loc_18002E817
0x18002e759  lea     rcx, aGcMsdcs; "gc._msdcs."
0x18002e760  mov     [rsp+120h+cchCount2], 0FFFFFFFFh; cchCount2
0x18002e768  mov     [rsp+120h+lpString2], rcx; lpString2
0x18002e76d  mov     r9d, eax; cchCount1
0x18002e770  mov     ecx, 400h; Locale
0x18002e775  mov     edx, 1; dwCmpFlags
0x18002e77a  call    cs:__imp_CompareStringW
0x18002e781  nop     dword ptr [rax+rax+00h]
0x18002e786  cmp     eax, 2
0x18002e789  jnz     loc_18002E817
0x18002e78f  mov     r9d, cs:g_fTracingOn
0x18002e796  test    r9d, r9d
0x18002e799  jz      short loc_18002E7CC
0x18002e79b  cmp     cs:g_fProviderEnabled, r12d
0x18002e7a2  jz      short loc_18002E7CC
0x18002e7a4  test    cs:g_ulTraceFlags, 800000h
0x18002e7af  jz      short loc_18002E7CC
0x18002e7b1  mov     r8, rbx
0x18002e7b4  lea     rdx, aPreprocessingG; "Preprocessing GC referral to '%S'\n"
0x18002e7bb  mov     ecx, 800000h
0x18002e7c0  call    LDAPClientPrint
0x18002e7c5  mov     r9d, cs:g_fTracingOn
0x18002e7cc  mov     rcx, rbx
0x18002e7cf  call    strlenW
0x18002e7d4  lea     rdx, [rbx+14h]
0x18002e7d8  mov     rcx, rbx
0x18002e7db  lea     r8d, ds:0FFFFFFFFFFFFFFEEh[rax*2]
0x18002e7e3  call    ldap_MoveMemory
0x18002e7e8  test    r9d, r9d
0x18002e7eb  jz      short loc_18002E817
0x18002e7ed  cmp     cs:g_fProviderEnabled, r12d
0x18002e7f4  jz      short loc_18002E817
0x18002e7f6  test    cs:g_ulTraceFlags, 800000h
0x18002e801  jz      short loc_18002E817
0x18002e803  mov     r8, rbx
0x18002e806  lea     rdx, aChasingGcRefer; "Chasing GC referral to '%S' instead\n"
0x18002e80d  mov     ecx, 800000h
0x18002e812  call    LDAPClientPrint
0x18002e817  mov     r8d, 736E414Ch
0x18002e81d  lea     rdx, [rbp+3Fh+var_90]
0x18002e821  mov     rcx, rbx; lpWideCharStr
0x18002e824  call    FromUnicodeWithAlloc
0x18002e829  xor     edx, edx
0x18002e82b  mov     r8d, 696E554Ch
0x18002e831  mov     rcx, rbx; Src
0x18002e834  mov     r12d, eax
0x18002e837  call    ldap_dup_stringW
0x18002e83c  mov     rdx, [rbp+3Fh+var_90]
0x18002e840  mov     [rbp+3Fh+var_90], rdx
0x18002e844  xor     edx, edx
0x18002e846  mov     [rbp+3Fh+lpString1], rax
0x18002e84a  test    rax, rax
0x18002e84d  jz      loc_1800306CB
0x18002e853  test    r12d, r12d
0x18002e856  jnz     loc_1800306CB
0x18002e85c  mov     rbx, r14
0x18002e85f  test    r14, r14
0x18002e862  jz      loc_18002E9A6
0x18002e868  movzx   r8d, word ptr [r14]
0x18002e86c  mov     r10, r14
0x18002e86f  test    r8w, r8w
0x18002e873  jz      loc_18002E97E
0x18002e879  add     rbx, 2
0x18002e87d  cmp     r8w, 25h ; '%'
0x18002e882  jnz     loc_18002E964
0x18002e888  movzx   ecx, word ptr [rbx]
0x18002e88b  test    cx, cx
0x18002e88e  jz      loc_18002E97A
0x18002e894  movzx   r9d, word ptr [rbx+2]
0x18002e899  test    r9w, r9w
0x18002e89d  jz      loc_18002E97A
0x18002e8a3  movzx   eax, cx
0x18002e8a6  shr     ax, 8
0x18002e8aa  test    al, al
0x18002e8ac  jnz     loc_18002E964
0x18002e8b2  movzx   eax, r9w
0x18002e8b6  shr     ax, 8
0x18002e8ba  test    al, al
0x18002e8bc  jnz     loc_18002E964
0x18002e8c2  lea     r11d, [rcx-30h]
0x18002e8c6  cmp     r11b, 9
0x18002e8ca  jbe     short loc_18002E8DE
0x18002e8cc  lea     eax, [rcx-41h]
0x18002e8cf  cmp     al, 5
0x18002e8d1  jbe     short loc_18002E8DE
0x18002e8d3  lea     eax, [rcx-61h]
0x18002e8d6  cmp     al, 5
0x18002e8d8  ja      loc_18002E964
0x18002e8de  lea     edx, [r9-30h]
0x18002e8e2  cmp     dl, 9
0x18002e8e5  jbe     short loc_18002E8F7
0x18002e8e7  lea     eax, [r9-41h]
0x18002e8eb  cmp     al, 5
0x18002e8ed  jbe     short loc_18002E8F7
0x18002e8ef  lea     eax, [r9-61h]
0x18002e8f3  cmp     al, 5
0x18002e8f5  ja      short loc_18002E962
0x18002e8f7  cmp     r11b, 9
0x18002e8fb  jbe     short loc_18002E917
0x18002e8fd  lea     eax, [rcx-41h]
0x18002e900  cmp     al, 5
0x18002e902  ja      short loc_18002E909
0x18002e904  sub     cl, 37h ; '7'
0x18002e907  jmp     short loc_18002E917
0x18002e909  lea     eax, [rcx-61h]
0x18002e90c  cmp     al, 5
0x18002e90e  ja      short loc_18002E915
0x18002e910  sub     cl, 57h ; 'W'
0x18002e913  jmp     short loc_18002E917
0x18002e915  xor     cl, cl
0x18002e917  cmp     dl, 9
0x18002e91a  jbe     short loc_18002E93A
0x18002e91c  lea     eax, [r9-41h]
0x18002e920  cmp     al, 5
0x18002e922  ja      short loc_18002E92A
0x18002e924  lea     edx, [r9-37h]
0x18002e928  jmp     short loc_18002E93A
0x18002e92a  lea     eax, [r9-61h]
0x18002e92e  cmp     al, 5
0x18002e930  ja      short loc_18002E938
0x18002e932  lea     edx, [r9-57h]
0x18002e936  jmp     short loc_18002E93A
0x18002e938  xor     dl, dl
0x18002e93a  shl     cl, 4
0x18002e93d  add     rbx, 4
0x18002e941  or      cl, dl
0x18002e943  movzx   r8d, cl
0x18002e947  cmp     r8d, 3Fh ; '?'
0x18002e94b  jnz     short loc_18002E962
0x18002e94d  mov     dword ptr [r10], 33005Ch
0x18002e954  add     r10, 4
0x18002e958  xor     edx, edx
0x18002e95a  mov     word ptr [r10], 46h ; 'F'
0x18002e960  jmp     short loc_18002E968
0x18002e962  xor     edx, edx
0x18002e964  mov     [r10], r8w
0x18002e968  movzx   r8d, word ptr [rbx]
0x18002e96c  add     r10, 2
0x18002e970  test    r8w, r8w
0x18002e974  jnz     loc_18002E879
0x18002e97a  mov     r13, [rbp+3Fh+arg_0]
0x18002e97e  mov     [r10], dx
0x18002e982  cmp     [r14], dx
0x18002e986  jnz     short loc_18002E98D
0x18002e988  mov     rbx, rdx
0x18002e98b  jmp     short loc_18002E9A6
0x18002e98d  mov     rcx, r14; Src
0x18002e990  call    LdapParseReferralDN
0x18002e995  mov     [rsp+120h+var_C8], rax
0x18002e99a  mov     rbx, r14
0x18002e99d  test    rax, rax
0x18002e9a0  jz      loc_1800306D5
0x18002e9a6  lea     rcx, [r13+30h]; lpCriticalSection
0x18002e9aa  call    cs:__imp_EnterCriticalSection
0x18002e9b1  nop     dword ptr [rax+rax+00h]
0x18002e9b6  movzx   eax, word ptr [r13+0B4h]
0x18002e9be  mov     r9d, 1
0x18002e9c4  mov     rsi, [r13+20h]
0x18002e9c8  mov     byte ptr [rsp+120h+var_D0+1], r9b
0x18002e9cd  cmp     [r13+0B2h], ax
0x18002e9d5  ja      short loc_18002EA1E
0x18002e9d7  xor     eax, eax
0x18002e9d9  cmp     cs:g_fTracingOn, eax
0x18002e9df  jz      short loc_18002EA0B
0x18002e9e1  cmp     cs:g_fProviderEnabled, eax
0x18002e9e7  jz      short loc_18002EA0B
0x18002e9e9  mov     eax, 800000h
0x18002e9ee  test    cs:g_ulTraceFlags, rax
0x18002e9f5  jz      short loc_18002EA0B
0x18002e9f7  xor     r8d, r8d
0x18002e9fa  lea     rdx, aHandlereferral_6; "HandleReferral hit hop count limit of 0"...
0x18002ea01  mov     ecx, eax
0x18002ea03  mov     r9, r13
0x18002ea06  call    LDAPClientPrint
0x18002ea0b  mov     r12d, 46h ; 'F'
0x18002ea11  mov     r15, [rsp+120h+var_C8]
0x18002ea16  mov     bl, dil
0x18002ea19  jmp     loc_18002F4AC
0x18002ea1e  movzx   eax, word ptr [r15+3Ch]
0x18002ea23  cmp     ax, [r13+0B0h]
0x18002ea2b  jbe     short loc_18002EA59
0x18002ea2d  xor     ecx, ecx
0x18002ea2f  cmp     cs:g_fTracingOn, ecx
0x18002ea35  jz      short loc_18002EA0B
0x18002ea37  cmp     cs:g_fProviderEnabled, ecx
0x18002ea3d  jz      short loc_18002EA0B
0x18002ea3f  mov     ecx, 800000h
0x18002ea44  test    cs:g_ulTraceFlags, rcx
0x18002ea4b  jz      short loc_18002EA0B
0x18002ea4d  mov     r8d, eax
0x18002ea50  lea     rdx, aHandlereferral_0; "HandleReferral referral number 0x%x is "...
0x18002ea57  jmp     short loc_18002EA03
0x18002ea59  xor     edx, edx
0x18002ea5b  mov     r15b, dl
0x18002ea5e  mov     [rbp+3Fh+var_A0], r15d
0x18002ea62  test    ax, ax
0x18002ea65  jnz     short loc_18002EAA2
0x18002ea67  mov     [rbp+3Fh+var_68], rsi
0x18002ea6b  lea     rax, [r13+0C0h]
0x18002ea72  test    rbx, rbx
0x18002ea75  jz      short loc_18002EA7C
0x18002ea77  mov     rax, [rsp+120h+var_C8]
0x18002ea7c  cmp     byte ptr [r13+0BAh], 63h ; 'c'
0x18002ea84  mov     rdx, [rax]
0x18002ea87  mov     [rbp+3Fh+var_88], rdx
0x18002ea8b  jnz     short loc_18002EAF4
0x18002ea8d  cmp     [r13+0E8h], r9d
0x18002ea94  movzx   r15d, r15b
0x18002ea98  cmovz   r15d, r9d
0x18002ea9c  mov     [rbp+3Fh+var_A0], r15d
0x18002eaa0  jmp     short loc_18002EAF4
0x18002eaa2  mov     rcx, [r13+0A8h]
0x18002eaa9  shl     rax, 6
0x18002eaad  test    rbx, rbx
0x18002eab0  jnz     short loc_18002EABB
0x18002eab2  lea     rdx, [rax-38h]
0x18002eab6  add     rdx, rcx
0x18002eab9  jmp     short loc_18002EAC0
0x18002eabb  mov     rdx, [rsp+120h+var_C8]
0x18002eac0  cmp     byte ptr [r13+0BAh], 63h ; 'c'
0x18002eac8  mov     rdx, [rdx]
0x18002eacb  mov     r8, [rax+rcx-40h]
0x18002ead0  mov     [rbp+3Fh+var_88], rdx
0x18002ead4  mov     [rbp+3Fh+var_68], r8
0x18002ead8  jnz     short loc_18002EAF0
0x18002eada  cmp     [rax+rcx-0Ah], r9b
0x18002eadf  jnz     short loc_18002EAF0
0x18002eae1  cmp     [r13+0E8h], r9d
0x18002eae8  jnz     short loc_18002EAF0
0x18002eaea  mov     byte ptr [rbp+3Fh+var_A0], r9b
0x18002eaee  jmp     short loc_18002EAF4
0x18002eaf0  mov     [rbp+3Fh+var_88], rdx
0x18002eaf4  mov     r15, [rbp+3Fh+lpString1]
0x18002eaf8  mov     r9, rdx; unsigned __int16 *
0x18002eafb  movzx   r8d, [rbp+3Fh+arg_20]; unsigned __int16
0x18002eb00  mov     rdx, r15; unsigned __int16 *
0x18002eb03  mov     rcx, r13; struct ldap_request *
0x18002eb06  call    ?CheckForExistingReferral@@YAKPEAUldap_request@@PEAGG1@Z; CheckForExistingReferral(ldap_request *,ushort *,ushort,ushort *)
0x18002eb0b  mov     [rbp+3Fh+var_78], eax
0x18002eb0e  mov     r12d, eax
0x18002eb11  test    eax, eax
0x18002eb13  jnz     loc_18002EA11
0x18002eb19  lea     rcx, [r13+30h]; lpCriticalSection
0x18002eb1d  call    cs:__imp_LeaveCriticalSection
0x18002eb24  nop     dword ptr [rax+rax+00h]
0x18002eb29  mov     rcx, [rsi+2F0h]
0x18002eb30  xor     edx, edx
0x18002eb32  mov     rax, [rsi+300h]
0x18002eb39  mov     ebx, 80h
0x18002eb3e  mov     byte ptr [rsp+120h+var_D0+1], dl
0x18002eb42  mov     [rbp+3Fh+var_50], rcx
0x18002eb46  mov     [rbp+3Fh+var_80], rax
0x18002eb4a  test    rcx, rcx
0x18002eb4d  jz      loc_18002F085
0x18002eb53  cmp     [r13+0D8h], rdx
0x18002eb5a  jnz     loc_18002F085
0x18002eb60  lea     r14, [rsi+200h]
0x18002eb67  mov     [rbp+3Fh+var_70], rdx
0x18002eb6b  mov     rcx, r14; lpCriticalSection
0x18002eb6e  call    cs:__imp_EnterCriticalSection
0x18002eb75  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
