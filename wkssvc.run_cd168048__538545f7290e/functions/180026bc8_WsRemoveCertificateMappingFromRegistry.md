# WsRemoveCertificateMappingFromRegistry

- ea: `0x180026bc8`
- end: `0x180026c76`
- name: `WsRemoveCertificateMappingFromRegistry`
- size: `174`
- prototype: `__int64 __fastcall(PCWSTR ValueName)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180021ea8`
- `0x180022510`
- `0x180023930`

## callees

- `0x180009010`
- `0x180009090`
- `0x1800245ec`
- `0x180026bc8`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180026c44`
- `ntdll!RtlNtStatusToDosError` at `0x180026c44`
- `ntdll!RtlDeleteRegistryValue` at `0x180026bfd`
- `ntdll!RtlDeleteRegistryValue` at `0x180026bfd`

## string_xrefs

- `0x180026bdf`: `WsRemoveCertificateMappingFromRegistry`
- `0x180026c57`: `WsRemoveCertificateMappingFromRegistry`

## pseudocode

```c
__int64 __fastcall WsRemoveCertificateMappingFromRegistry(PCWSTR ValueName)
{
  ULONG v2; // ebx
  int v3; // edi
  int v4; // r8d

  v2 = WsImpersonateClient2("WsRemoveCertificateMappingFromRegistry", 233);
  if ( !v2 )
  {
    v3 = RtlDeleteRegistryValue(0, &Path, ValueName);
    if ( v3 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v4, v3, (__int64)ValueName);
      }
      v2 = RtlNtStatusToDosError(v3);
    }
    WsRevertToSelf2("WsRemoveCertificateMappingFromRegistry", 261);
  }
  return v2;
}

```

## disassembly

```asm
0x180026bc8  mov     [rsp+arg_0], rbx
0x180026bcd  mov     [rsp+arg_8], rsi
0x180026bd2  push    rdi
0x180026bd3  sub     rsp, 30h
0x180026bd7  mov     rsi, rcx
0x180026bda  mov     edx, 0E9h
0x180026bdf  lea     rcx, aWsremovecertif; "WsRemoveCertificateMappingFromRegistry"
0x180026be6  call    WsImpersonateClient2
0x180026beb  mov     ebx, eax
0x180026bed  test    eax, eax
0x180026bef  jnz     short loc_180026C63
0x180026bf1  mov     r8, rsi; ValueName
0x180026bf4  lea     rdx, Path; Path
0x180026bfb  xor     ecx, ecx; RelativeTo
0x180026bfd  call    cs:__imp_RtlDeleteRegistryValue
0x180026c04  nop     dword ptr [rax+rax+00h]
0x180026c09  mov     edi, eax
0x180026c0b  test    eax, eax
0x180026c0d  jns     short loc_180026C52
0x180026c0f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180026c16  lea     rax, WPP_GLOBAL_Control
0x180026c1d  cmp     rcx, rax
0x180026c20  jz      short loc_180026C42
0x180026c22  test    byte ptr [rcx+1Ch], 2
0x180026c26  jz      short loc_180026C42
0x180026c28  cmp     byte ptr [rcx+19h], 1
0x180026c2c  jb      short loc_180026C42
0x180026c2e  mov     rcx, [rcx+10h]
0x180026c32  lea     edx, [rbx+0Ah]
0x180026c35  mov     r9d, edi
0x180026c38  mov     [rsp+38h+var_18], rsi
0x180026c3d  call    WPP_SF_LS
0x180026c42  mov     ecx, edi; Status
0x180026c44  call    cs:__imp_RtlNtStatusToDosError
0x180026c4b  nop     dword ptr [rax+rax+00h]
0x180026c50  mov     ebx, eax
0x180026c52  mov     edx, 105h
0x180026c57  lea     rcx, aWsremovecertif; "WsRemoveCertificateMappingFromRegistry"
0x180026c5e  call    WsRevertToSelf2
0x180026c63  mov     rsi, [rsp+38h+arg_8]
0x180026c68  mov     eax, ebx
0x180026c6a  mov     rbx, [rsp+38h+arg_0]
0x180026c6f  add     rsp, 30h
0x180026c73  pop     rdi
0x180026c74  retn
```
