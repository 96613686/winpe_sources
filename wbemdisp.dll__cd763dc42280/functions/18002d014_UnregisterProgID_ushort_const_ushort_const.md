# UnregisterProgID(ushort const *,ushort const *)

- ea: `0x18002d014`
- end: `0x18002d1ad`
- name: `?UnregisterProgID@@YAXPEBG0@Z`
- size: `409`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002ce6c`

## callees

- `0x18000d2c0`
- `0x180018460`
- `0x18002d014`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d11f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d16f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d11f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d16f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002d05c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002d08f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002d05c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002d08f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002d0a0`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002d185`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002d18f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002d0a0`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002d185`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002d18f`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18002d0fe`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18002d13c`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18002d0fe`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18002d13c`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002d114`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002d12b`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002d152`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002d164`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002d17b`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002d114`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002d12b`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002d152`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002d164`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002d17b`

## string_xrefs

- `0x18002d108`: `CLSID`
- `0x18002d146`: `CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall UnregisterProgID(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  __int64 v4; // rax
  unsigned __int64 v5; // r15
  unsigned __int16 *v6; // rbx
  __int64 v7; // rcx
  unsigned __int64 v8; // r14
  unsigned __int16 *v9; // rdi
  HKEY phkResult; // [rsp+60h] [rbp+18h] BYREF

  phkResult = 0;
  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  v5 = (unsigned int)(v4 + 18);
  v6 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v5, 2u));
  if ( v6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
    v8 = (unsigned int)(v7 + 18);
    v9 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v8, 2u));
    if ( v9 )
    {
      StringCchCopyW(v6, v5, L"SOFTWARE\\CLASSES\\");
      StringCchCatW(v6, v5, a1);
      StringCchCopyW(v9, v8, L"SOFTWARE\\CLASSES\\");
      StringCchCatW(v9, v8, a2);
      if ( !RegOpenKeyW(HKEY_LOCAL_MACHINE, v9, &phkResult) )
      {
        RegDeleteKeyW(phkResult, L"CLSID");
        RegCloseKey(phkResult);
      }
      RegDeleteKeyW(HKEY_LOCAL_MACHINE, v9);
      if ( !RegOpenKeyW(HKEY_LOCAL_MACHINE, v6, &phkResult) )
      {
        RegDeleteKeyW(phkResult, L"CLSID");
        RegDeleteKeyW(phkResult, L"CurVer");
        RegCloseKey(phkResult);
      }
      RegDeleteKeyW(HKEY_LOCAL_MACHINE, v6);
      CWin32DefaultArena::WbemMemFree(v6);
      CWin32DefaultArena::WbemMemFree(v9);
    }
    else
    {
      CWin32DefaultArena::WbemMemFree(v6);
    }
  }
}

```

## disassembly

```asm
0x18002d014  mov     [rsp+arg_0], rbx
0x18002d019  mov     [rsp+arg_8], rbp
0x18002d01e  push    rsi
0x18002d01f  push    rdi
0x18002d020  push    r12
0x18002d022  push    r14
0x18002d024  push    r15
0x18002d026  sub     rsp, 20h
0x18002d02a  mov     rbp, rdx
0x18002d02d  mov     rsi, rcx
0x18002d030  xor     r12d, r12d
0x18002d033  mov     [rsp+48h+phkResult], r12
0x18002d038  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002d03c  mov     rax, rdi
0x18002d03f  inc     rax
0x18002d042  cmp     [rcx+rax*2], r12w
0x18002d047  jnz     short loc_18002D03F
0x18002d049  lea     r15d, [rax+12h]
0x18002d04d  mov     eax, 2
0x18002d052  mul     r15
0x18002d055  cmovb   rax, rdi
0x18002d059  mov     rcx, rax
0x18002d05c  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002d062  mov     rbx, rax
0x18002d065  test    rax, rax
0x18002d068  jz      loc_18002D196
0x18002d06e  mov     rcx, rdi
0x18002d071  inc     rcx
0x18002d074  cmp     [rbp+rcx*2+0], r12w
0x18002d07a  jnz     short loc_18002D071
0x18002d07c  lea     r14d, [rcx+12h]
0x18002d080  mov     eax, 2
0x18002d085  mul     r14
0x18002d088  cmovb   rax, rdi
0x18002d08c  mov     rcx, rax
0x18002d08f  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002d095  mov     rdi, rax
0x18002d098  test    rax, rax
0x18002d09b  jnz     short loc_18002D0AC
0x18002d09d  mov     rcx, rbx
0x18002d0a0  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002d0a6  nop
0x18002d0a7  jmp     loc_18002D196
0x18002d0ac  lea     r8, aSoftwareClasse_0; "SOFTWARE\\CLASSES\\"
0x18002d0b3  mov     rdx, r15; unsigned __int64
0x18002d0b6  mov     rcx, rbx; unsigned __int16 *
0x18002d0b9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002d0be  mov     r8, rsi; unsigned __int16 *
0x18002d0c1  mov     rdx, r15; unsigned __int64
0x18002d0c4  mov     rcx, rbx; unsigned __int16 *
0x18002d0c7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002d0cc  lea     r8, aSoftwareClasse_0; "SOFTWARE\\CLASSES\\"
0x18002d0d3  mov     rdx, r14; unsigned __int64
0x18002d0d6  mov     rcx, rdi; unsigned __int16 *
0x18002d0d9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002d0de  mov     r8, rbp; unsigned __int16 *
0x18002d0e1  mov     rdx, r14; unsigned __int64
0x18002d0e4  mov     rcx, rdi; unsigned __int16 *
0x18002d0e7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002d0ec  lea     r8, [rsp+48h+phkResult]; phkResult
0x18002d0f1  mov     rdx, rdi; lpSubKey
0x18002d0f4  mov     rsi, 0FFFFFFFF80000002h
0x18002d0fb  mov     rcx, rsi; hKey
0x18002d0fe  call    cs:__imp_RegOpenKeyW
0x18002d104  test    eax, eax
0x18002d106  jnz     short loc_18002D125
0x18002d108  lea     rdx, aClsid; "CLSID"
0x18002d10f  mov     rcx, [rsp+48h+phkResult]; hKey
0x18002d114  call    cs:__imp_RegDeleteKeyW
0x18002d11a  mov     rcx, [rsp+48h+phkResult]; hKey
0x18002d11f  call    cs:__imp_RegCloseKey
0x18002d125  mov     rdx, rdi; lpSubKey
0x18002d128  mov     rcx, rsi; hKey
0x18002d12b  call    cs:__imp_RegDeleteKeyW
0x18002d131  lea     r8, [rsp+48h+phkResult]; phkResult
0x18002d136  mov     rdx, rbx; lpSubKey
0x18002d139  mov     rcx, rsi; hKey
0x18002d13c  call    cs:__imp_RegOpenKeyW
0x18002d142  test    eax, eax
0x18002d144  jnz     short loc_18002D175
0x18002d146  lea     rdx, aClsid; "CLSID"
0x18002d14d  mov     rcx, [rsp+48h+phkResult]; hKey
0x18002d152  call    cs:__imp_RegDeleteKeyW
0x18002d158  lea     rdx, aCurver; "CurVer"
0x18002d15f  mov     rcx, [rsp+48h+phkResult]; hKey
0x18002d164  call    cs:__imp_RegDeleteKeyW
0x18002d16a  mov     rcx, [rsp+48h+phkResult]; hKey
0x18002d16f  call    cs:__imp_RegCloseKey
0x18002d175  mov     rdx, rbx; lpSubKey
0x18002d178  mov     rcx, rsi; hKey
0x18002d17b  call    cs:__imp_RegDeleteKeyW
0x18002d181  nop
0x18002d182  mov     rcx, rbx
0x18002d185  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002d18b  nop
0x18002d18c  mov     rcx, rdi
0x18002d18f  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002d195  nop
0x18002d196  mov     rbx, [rsp+48h+arg_0]
0x18002d19b  mov     rbp, [rsp+48h+arg_8]
0x18002d1a0  add     rsp, 20h
0x18002d1a4  pop     r15
0x18002d1a6  pop     r14
0x18002d1a8  pop     r12
0x18002d1aa  pop     rdi
0x18002d1ab  pop     rsi
0x18002d1ac  retn
```
