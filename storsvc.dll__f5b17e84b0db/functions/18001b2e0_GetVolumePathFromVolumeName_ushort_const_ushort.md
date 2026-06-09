# GetVolumePathFromVolumeName(ushort const *,ushort *)

- ea: `0x18001b2e0`
- end: `0x18001b3a8`
- name: `?GetVolumePathFromVolumeName@@YAJPEBGPEAG@Z`
- size: `200`
- prototype: `__int64 __fastcall(LPCWSTR lpszVolumeName, wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180025bf8`

## callees

- `0x18000d400`
- `0x18000d5a4`
- `0x180012c9c`
- `0x18001b2e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b30c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b30c`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x18001b306`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x18001b364`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x18001b306`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x18001b364`

## pseudocode

```c
__int64 __fastcall GetVolumePathFromVolumeName(LPCWSTR lpszVolumeName, wchar_t *a2)
{
  unsigned __int64 v4; // rax
  WCHAR *v5; // rax
  wchar_t *v6; // rdi
  unsigned int v7; // ebx
  const struct std::nothrow_t *v8; // rdx
  DWORD cchReturnLength; // [rsp+40h] [rbp+18h] BYREF

  cchReturnLength = 0;
  GetVolumePathNamesForVolumeNameW(lpszVolumeName, 0, 0, &cchReturnLength);
  if ( GetLastError() == 234 && cchReturnLength )
  {
    v4 = 2LL * cchReturnLength;
    if ( !is_mul_ok(cchReturnLength, 2u) )
      v4 = -1;
    v5 = (WCHAR *)operator new[](v4, (const struct std::nothrow_t *)std::nothrow);
    v6 = v5;
    if ( v5 )
    {
      if ( GetVolumePathNamesForVolumeNameW(lpszVolumeName, v5, cchReturnLength, &cchReturnLength) )
        v7 = StringCchCopyW(a2, 0x104u, v6);
      else
        v7 = -2147467259;
      operator delete(v6, v8);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return v7;
}

```

## disassembly

```asm
0x18001b2e0  mov     rax, rsp
0x18001b2e3  mov     [rax+8], rbx
0x18001b2e7  mov     [rax+10h], rsi
0x18001b2eb  push    rdi
0x18001b2ec  sub     rsp, 20h
0x18001b2f0  mov     rsi, rdx
0x18001b2f3  mov     dword ptr [rax+18h], 0
0x18001b2fa  xor     edx, edx; lpszVolumePathNames
0x18001b2fc  lea     r9, [rax+18h]; lpcchReturnLength
0x18001b300  xor     r8d, r8d; cchBufferLength
0x18001b303  mov     rbx, rcx
0x18001b306  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18001b30c  call    cs:__imp_GetLastError
0x18001b312  cmp     eax, 0EAh
0x18001b317  jnz     short loc_18001B391
0x18001b319  mov     eax, [rsp+28h+cchReturnLength]
0x18001b31d  test    eax, eax
0x18001b31f  jz      short loc_18001B391
0x18001b321  mov     ecx, eax
0x18001b323  mov     eax, 2
0x18001b328  mul     rcx
0x18001b32b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001b332  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b339  cmovb   rax, rcx
0x18001b33d  mov     rcx, rax; unsigned __int64
0x18001b340  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001b345  mov     rdi, rax
0x18001b348  test    rax, rax
0x18001b34b  jnz     short loc_18001B354
0x18001b34d  mov     ebx, 8007000Eh
0x18001b352  jmp     short loc_18001B396
0x18001b354  mov     r8d, [rsp+28h+cchReturnLength]; cchBufferLength
0x18001b359  lea     r9, [rsp+28h+cchReturnLength]; lpcchReturnLength
0x18001b35e  mov     rdx, rdi; lpszVolumePathNames
0x18001b361  mov     rcx, rbx; lpszVolumeName
0x18001b364  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18001b36a  test    eax, eax
0x18001b36c  jnz     short loc_18001B375
0x18001b36e  mov     ebx, 80004005h
0x18001b373  jmp     short loc_18001B387
0x18001b375  mov     r8, rdi; wchar_t *
0x18001b378  mov     edx, 104h; unsigned __int64
0x18001b37d  mov     rcx, rsi; wchar_t *
0x18001b380  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18001b385  mov     ebx, eax
0x18001b387  mov     rcx, rdi; void *
0x18001b38a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001b38f  jmp     short loc_18001B396
0x18001b391  mov     ebx, 80004005h
0x18001b396  mov     rsi, [rsp+28h+arg_8]
0x18001b39b  mov     eax, ebx
0x18001b39d  mov     rbx, [rsp+28h+arg_0]
0x18001b3a2  add     rsp, 20h
0x18001b3a6  pop     rdi
0x18001b3a7  retn
```
