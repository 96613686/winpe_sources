# CUwfConfiguration::commitBcdValue(_GUID const &,ulong)

- ea: `0x18000a824`
- end: `0x18000a8c2`
- name: `?commitBcdValue@CUwfConfiguration@@AEAAJAEBU_GUID@@K@Z`
- size: `158`
- prototype: `__int64 __fastcall(CUwfConfiguration *this, const struct _GUID *, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bdf4`
- `0x18000cf40`
- `0x18000d18c`

## callees

- `0x18000a0b8`
- `0x18000a824`
- `0x18000a8c8`
- `0x18001b020`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000a850`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000a850`

## pseudocode

```c
__int64 __fastcall CUwfConfiguration::commitBcdValue(CUwfConfiguration *this, const struct _GUID *a2, int a3)
{
  CUwfConfiguration *v4; // rcx
  int v5; // eax
  unsigned int v6; // ecx
  int v8; // [rsp+20h] [rbp-878h]
  OLECHAR sz[40]; // [rsp+30h] [rbp-868h] BYREF
  unsigned __int16 v10[1024]; // [rsp+80h] [rbp-818h] BYREF

  if ( !StringFromGUID2(a2, sz, 39) )
    return 2147500037LL;
  v8 = a3;
  if ( (int)StringCbPrintfW(v10, 0x800u, L"HKLM\\BCD00000000\\Objects\\%s\\Elements\\%08lx", sz, v8) < 0 )
    return 2147500037LL;
  v5 = CUwfConfiguration::commitRegKeyValue(v4, v10, L"Element");
  v6 = 0;
  if ( v5 < 0 )
    return (unsigned int)-2147467259;
  return v6;
}

```

## disassembly

```asm
0x18000a824  push    rbx
0x18000a826  sub     rsp, 890h
0x18000a82d  mov     rax, cs:__security_cookie
0x18000a834  xor     rax, rsp
0x18000a837  mov     [rsp+898h+var_18], rax
0x18000a83f  mov     ebx, r8d
0x18000a842  mov     rcx, rdx; rguid
0x18000a845  mov     r8d, 27h ; '''; cchMax
0x18000a84b  lea     rdx, [rsp+898h+sz]; lpsz
0x18000a850  call    cs:__imp_StringFromGUID2
0x18000a856  test    eax, eax
0x18000a858  jz      short loc_18000A8A4
0x18000a85a  lea     r9, [rsp+898h+sz]
0x18000a85f  mov     [rsp+898h+var_878], ebx
0x18000a863  lea     r8, aHklmBcd0000000; "HKLM\\BCD00000000\\Objects\\%s\\Element"...
0x18000a86a  mov     edx, 800h; unsigned __int64
0x18000a86f  lea     rcx, [rsp+898h+var_818]; unsigned __int16 *
0x18000a877  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a87c  test    eax, eax
0x18000a87e  js      short loc_18000A8A4
0x18000a880  lea     r8, aElement; "Element"
0x18000a887  lea     rdx, [rsp+898h+var_818]; unsigned __int16 *
0x18000a88f  call    ?commitRegKeyValue@CUwfConfiguration@@AEAAJPEBG0@Z; CUwfConfiguration::commitRegKeyValue(ushort const *,ushort const *)
0x18000a894  xor     ecx, ecx
0x18000a896  mov     edx, 80004005h
0x18000a89b  test    eax, eax
0x18000a89d  cmovs   ecx, edx
0x18000a8a0  mov     eax, ecx
0x18000a8a2  jmp     short loc_18000A8A9
0x18000a8a4  mov     eax, 80004005h
0x18000a8a9  mov     rcx, [rsp+898h+var_18]
0x18000a8b1  xor     rcx, rsp; StackCookie
0x18000a8b4  call    __security_check_cookie
0x18000a8b9  add     rsp, 890h
0x18000a8c0  pop     rbx
0x18000a8c1  retn
```
