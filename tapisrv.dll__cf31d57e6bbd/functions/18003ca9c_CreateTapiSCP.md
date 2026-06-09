# CreateTapiSCP

- ea: `0x18003ca9c`
- end: `0x18003cb85`
- name: `CreateTapiSCP`
- size: `233`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180032ad0`
- `0x18003d4ec`

## callees

- `0x180001600`
- `0x18001c8a4`
- `0x180037344`
- `0x18003ca9c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18003cb64`
- `KERNEL32!LeaveCriticalSection` at `0x18003cb64`
- `KERNEL32!EnterCriticalSection` at `0x18003cabe`
- `KERNEL32!EnterCriticalSection` at `0x18003cabe`

## string_xrefs

- `0x18003cb43`: `Telephony Service`
- `0x18003cb4f`: `CN=Telephony Service`

## pseudocode

```c
__int64 CreateTapiSCP()
{
  HRESULT SCP; // ebx
  _WORD v2[40]; // [rsp+40h] [rbp-1B8h] BYREF
  _WORD v3[40]; // [rsp+90h] [rbp-168h] BYREF
  wchar_t pszDest[128]; // [rsp+E0h] [rbp-118h] BYREF

  EnterCriticalSection(&gSCPCritSec);
  v3[0] = 0;
  v2[0] = 0;
  SCP = StringCbPrintfW(
          pszDest,
          0x100u,
          L"E{\\pipe\\tapsrv}P{ncacn_np}C{%s}A{%s}S{%s}TTL{%s}",
          v3,
          v2,
          L"Inactive",
          &Format);
  if ( SCP >= 0 )
    SCP = CreateSCP(
            L"CN=Telephony Service",
            L"Telephony Service",
            L"B1A37774-E3F7-488E-ADBFD4DB8A4AB2E5",
            0,
            pszDest,
            L"TAPISRVSCPGUID",
            0);
  LeaveCriticalSection(&gSCPCritSec);
  return (unsigned int)SCP;
}

```

## disassembly

```asm
0x18003ca9c  push    rbx
0x18003ca9e  sub     rsp, 1F0h
0x18003caa5  mov     rax, cs:__security_cookie
0x18003caac  xor     rax, rsp
0x18003caaf  mov     [rsp+1F8h+var_18], rax
0x18003cab7  lea     rcx, gSCPCritSec; lpCriticalSection
0x18003cabe  call    cs:__imp_EnterCriticalSection
0x18003cac4  xor     eax, eax
0x18003cac6  lea     r9, [rsp+1F8h+var_168]
0x18003cace  mov     [rsp+1F8h+var_168], ax
0x18003cad6  lea     r8, aEPipeTapsrvPNc; "E{\\pipe\\tapsrv}P{ncacn_np}C{%s}A{%s}S"...
0x18003cadd  mov     [rsp+1F8h+var_1B8], ax
0x18003cae2  lea     rcx, [rsp+1F8h+pszDest]; pszDest
0x18003caea  lea     rax, Format
0x18003caf1  mov     edx, 100h; cbDest
0x18003caf6  mov     [rsp+1F8h+var_1C8], rax
0x18003cafb  lea     rax, aInactive; "Inactive"
0x18003cb02  mov     [rsp+1F8h+lpValueName], rax
0x18003cb07  lea     rax, [rsp+1F8h+var_1B8]
0x18003cb0c  mov     [rsp+1F8h+var_1D8], rax
0x18003cb11  call    StringCbPrintfW
0x18003cb16  mov     ebx, eax
0x18003cb18  test    eax, eax
0x18003cb1a  js      short loc_18003CB5D
0x18003cb1c  lea     rax, gszRegTapisrvSCPGuid; "TAPISRVSCPGUID"
0x18003cb23  mov     [rsp+1F8h+var_1C8], 0; unsigned __int16 **
0x18003cb2c  mov     [rsp+1F8h+lpValueName], rax; lpValueName
0x18003cb31  lea     r8, aB1a37774E3f748; "B1A37774-E3F7-488E-ADBFD4DB8A4AB2E5"
0x18003cb38  lea     rax, [rsp+1F8h+pszDest]
0x18003cb40  xor     r9d, r9d; unsigned __int16 *
0x18003cb43  lea     rdx, aTelephonyServi; "Telephony Service"
0x18003cb4a  mov     [rsp+1F8h+var_1D8], rax; unsigned __int16 *
0x18003cb4f  lea     rcx, aCnTelephonySer; "CN=Telephony Service"
0x18003cb56  call    ?CreateSCP@@YAJPEAG0PEBG001PEAPEAG@Z; CreateSCP(ushort *,ushort *,ushort const *,ushort *,ushort *,ushort const *,ushort * *)
0x18003cb5b  mov     ebx, eax
0x18003cb5d  lea     rcx, gSCPCritSec; lpCriticalSection
0x18003cb64  call    cs:__imp_LeaveCriticalSection
0x18003cb6a  mov     eax, ebx
0x18003cb6c  mov     rcx, [rsp+1F8h+var_18]
0x18003cb74  xor     rcx, rsp; StackCookie
0x18003cb77  call    __security_check_cookie
0x18003cb7c  add     rsp, 1F0h
0x18003cb83  pop     rbx
0x18003cb84  retn
```
