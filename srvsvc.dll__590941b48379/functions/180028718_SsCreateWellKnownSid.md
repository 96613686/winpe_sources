# SsCreateWellKnownSid

- ea: `0x180028718`
- end: `0x1800287bc`
- name: `SsCreateWellKnownSid`
- size: `164`
- prototype: `__int64 __fastcall(WELL_KNOWN_SID_TYPE WellKnownSidType)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a5d4`

## callees

- `0x180028718`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180028744`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002878b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180028744`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002878b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002874e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028759`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002874e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028759`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002876a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002876a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028798`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028798`

## pseudocode

```c
DWORD __fastcall SsCreateWellKnownSid(WELL_KNOWN_SID_TYPE WellKnownSidType, _QWORD *a2)
{
  HLOCAL v5; // rax
  void *v6; // rbx
  SIZE_T uBytes; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  LODWORD(uBytes) = 0;
  if ( CreateWellKnownSid(WellKnownSidType, 0, 0, (DWORD *)&uBytes) )
    return 31;
  if ( GetLastError() != 122 )
    return GetLastError();
  v5 = LocalAlloc(0x40u, (unsigned int)uBytes);
  v6 = v5;
  if ( !v5 )
    return 1450;
  if ( !CreateWellKnownSid(WellKnownSidType, 0, v5, (DWORD *)&uBytes) )
  {
    LocalFree(v6);
    return GetLastError();
  }
  *a2 = v6;
  return 0;
}

```

## disassembly

```asm
0x180028718  mov     rax, rsp
0x18002871b  mov     [rax+8], rbx
0x18002871f  mov     [rax+18h], rsi
0x180028723  push    rdi
0x180028724  sub     rsp, 20h
0x180028728  mov     rdi, rdx
0x18002872b  mov     qword ptr [rdx], 0
0x180028732  xor     edx, edx; DomainSid
0x180028734  mov     dword ptr [rax+10h], 0
0x18002873b  lea     r9, [rax+10h]; cbSid
0x18002873f  xor     r8d, r8d; pSid
0x180028742  mov     esi, ecx
0x180028744  call    cs:__imp_CreateWellKnownSid
0x18002874a  test    eax, eax
0x18002874c  jnz     short loc_1800287A7
0x18002874e  call    cs:__imp_GetLastError
0x180028754  cmp     eax, 7Ah ; 'z'
0x180028757  jz      short loc_180028761
0x180028759  call    cs:__imp_GetLastError
0x18002875f  jmp     short loc_1800287AC
0x180028761  mov     edx, dword ptr [rsp+28h+uBytes]; uBytes
0x180028765  mov     ecx, 40h ; '@'; uFlags
0x18002876a  call    cs:__imp_LocalAlloc
0x180028770  mov     rbx, rax
0x180028773  test    rax, rax
0x180028776  jnz     short loc_18002877F
0x180028778  mov     eax, 5AAh
0x18002877d  jmp     short loc_1800287AC
0x18002877f  lea     r9, [rsp+28h+uBytes]; cbSid
0x180028784  mov     r8, rbx; pSid
0x180028787  xor     edx, edx; DomainSid
0x180028789  mov     ecx, esi; WellKnownSidType
0x18002878b  call    cs:__imp_CreateWellKnownSid
0x180028791  test    eax, eax
0x180028793  jnz     short loc_1800287A0
0x180028795  mov     rcx, rbx; hMem
0x180028798  call    cs:__imp_LocalFree
0x18002879e  jmp     short loc_180028759
0x1800287a0  mov     [rdi], rbx
0x1800287a3  xor     eax, eax
0x1800287a5  jmp     short loc_1800287AC
0x1800287a7  mov     eax, 1Fh
0x1800287ac  mov     rbx, [rsp+28h+arg_0]
0x1800287b1  mov     rsi, [rsp+28h+arg_10]
0x1800287b6  add     rsp, 20h
0x1800287ba  pop     rdi
0x1800287bb  retn
```
