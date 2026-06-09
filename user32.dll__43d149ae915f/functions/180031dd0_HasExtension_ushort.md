# HasExtension(ushort *)

- ea: `0x180031dd0`
- end: `0x180031fd1`
- name: `?HasExtension@@YAKPEAG@Z`
- size: `513`
- prototype: `unsigned int __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180031a30`

## callees

- `0x180031dd0`
- `0x180031fd8`
- `0x180096e00`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031e82`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031ead`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031ed8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031f03`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031f2e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031f55`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031f7c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031e82`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031ead`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031ed8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031f03`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031f2e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031f55`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031f7c`

## pseudocode

```c
__int64 __fastcall HasExtension(unsigned __int16 *a1)
{
  unsigned __int16 *Extension; // rax
  __int64 v3; // rcx
  WCHAR *v4; // rdx
  __int64 v5; // r8
  WCHAR *v6; // rcx
  WCHAR String1[8]; // [rsp+30h] [rbp-28h] BYREF

  Extension = PathFindExtension(a1);
  if ( *Extension != 46 )
    return 0;
  v3 = 4;
  v4 = String1;
  v5 = 5;
  do
  {
    if ( !v3 )
      break;
    if ( !*Extension )
      break;
    *v4++ = *Extension++;
    --v3;
    --v5;
  }
  while ( v5 );
  v6 = v4 - 1;
  if ( v5 )
    v6 = v4;
  *v6 = 0;
  if ( CompareStringW(0x7Fu, 1u, String1, -1, L".com", -1) == 2 )
    return 1836016430;
  if ( CompareStringW(0x7Fu, 1u, String1, -1, L".bat", -1) == 2 )
    return 1952539182;
  if ( CompareStringW(0x7Fu, 1u, String1, -1, L".cmd", -1) == 2 )
    return 1684890414;
  if ( CompareStringW(0x7Fu, 1u, String1, -1, L".pif", -1) == 2 )
    return 1718186030;
  if ( CompareStringW(0x7Fu, 1u, String1, -1, L".lnk", -1) == 2 )
    return 1802398766;
  if ( CompareStringW(0x7Fu, 1u, String1, -1, L".ico", -1) == 2 )
    return 1868785966;
  if ( CompareStringW(0x7Fu, 1u, String1, -1, L".exe", -1) != 2 )
    return 0;
  return 1702389038;
}

```

## disassembly

```asm
0x180031dd0  mov     [rsp+arg_8], rbx
0x180031dd5  mov     [rsp+arg_10], rsi
0x180031dda  push    rdi
0x180031ddb  sub     rsp, 50h
0x180031ddf  mov     rax, cs:__security_cookie
0x180031de6  xor     rax, rsp
0x180031de9  mov     [rsp+58h+var_18], rax
0x180031dee  call    ?PathFindExtension@@YAPEAGPEAG@Z; PathFindExtension(ushort *)
0x180031df3  cmp     word ptr [rax], 2Eh ; '.'
0x180031df7  jz      short loc_180031E18
0x180031df9  xor     eax, eax
0x180031dfb  mov     rcx, [rsp+58h+var_18]
0x180031e00  xor     rcx, rsp; StackCookie
0x180031e03  call    __security_check_cookie
0x180031e08  mov     rbx, [rsp+58h+arg_8]
0x180031e0d  mov     rsi, [rsp+58h+arg_10]
0x180031e12  add     rsp, 50h
0x180031e16  pop     rdi
0x180031e17  retn
0x180031e18  mov     ecx, 4
0x180031e1d  lea     rdx, [rsp+58h+String1]
0x180031e22  xor     r10d, r10d
0x180031e25  lea     r8d, [rcx+1]
0x180031e29  lea     edi, [rcx-3]
0x180031e2c  test    rcx, rcx
0x180031e2f  jz      short loc_180031E4F
0x180031e31  movzx   r9d, word ptr [rax]
0x180031e35  test    r9w, r9w
0x180031e39  jz      short loc_180031E4F
0x180031e3b  mov     [rdx], r9w
0x180031e3f  add     rax, 2
0x180031e43  add     rdx, 2
0x180031e47  sub     rcx, rdi
0x180031e4a  sub     r8, rdi
0x180031e4d  jnz     short loc_180031E2C
0x180031e4f  test    r8, r8
0x180031e52  lea     rcx, [rdx-2]
0x180031e56  lea     rax, aCom; ".com"
0x180031e5d  mov     esi, 7Fh
0x180031e62  cmovnz  rcx, rdx
0x180031e66  lea     r8, [rsp+58h+String1]; lpString1
0x180031e6b  or      ebx, 0FFFFFFFFh
0x180031e6e  mov     edx, edi; dwCmpFlags
0x180031e70  mov     [rsp+58h+cchCount2], ebx; cchCount2
0x180031e74  mov     r9d, ebx; cchCount1
0x180031e77  mov     [rsp+58h+lpString2], rax; lpString2
0x180031e7c  mov     [rcx], r10w
0x180031e80  mov     ecx, esi; Locale
0x180031e82  call    cs:__imp_CompareStringW
0x180031e88  cmp     eax, 2
0x180031e8b  jz      loc_180031F95
0x180031e91  lea     rax, aBat; ".bat"
0x180031e98  mov     [rsp+58h+cchCount2], ebx; cchCount2
0x180031e9c  mov     r9d, ebx; cchCount1
0x180031e9f  mov     [rsp+58h+lpString2], rax; lpString2
0x180031ea4  lea     r8, [rsp+58h+String1]; lpString1
0x180031ea9  mov     edx, edi; dwCmpFlags
0x180031eab  mov     ecx, esi; Locale
0x180031ead  call    cs:__imp_CompareStringW
0x180031eb3  cmp     eax, 2
0x180031eb6  jz      loc_180031FBD
0x180031ebc  lea     rax, aCmd; ".cmd"
0x180031ec3  mov     [rsp+58h+cchCount2], ebx; cchCount2
0x180031ec7  mov     r9d, ebx; cchCount1
0x180031eca  mov     [rsp+58h+lpString2], rax; lpString2
0x180031ecf  lea     r8, [rsp+58h+String1]; lpString1
0x180031ed4  mov     edx, edi; dwCmpFlags
0x180031ed6  mov     ecx, esi; Locale
0x180031ed8  call    cs:__imp_CompareStringW
0x180031ede  cmp     eax, 2
0x180031ee1  jz      loc_180031FA9
0x180031ee7  lea     rax, aPif; ".pif"
0x180031eee  mov     [rsp+58h+cchCount2], ebx; cchCount2
0x180031ef2  mov     r9d, ebx; cchCount1
0x180031ef5  mov     [rsp+58h+lpString2], rax; lpString2
0x180031efa  lea     r8, [rsp+58h+String1]; lpString1
0x180031eff  mov     edx, edi; dwCmpFlags
0x180031f01  mov     ecx, esi; Locale
0x180031f03  call    cs:__imp_CompareStringW
0x180031f09  cmp     eax, 2
0x180031f0c  jz      loc_180031FC7
0x180031f12  lea     rax, aLnk; ".lnk"
0x180031f19  mov     [rsp+58h+cchCount2], ebx; cchCount2
0x180031f1d  mov     r9d, ebx; cchCount1
0x180031f20  mov     [rsp+58h+lpString2], rax; lpString2
0x180031f25  lea     r8, [rsp+58h+String1]; lpString1
0x180031f2a  mov     edx, edi; dwCmpFlags
0x180031f2c  mov     ecx, esi; Locale
0x180031f2e  call    cs:__imp_CompareStringW
0x180031f34  cmp     eax, 2
0x180031f37  jz      short loc_180031FB3
0x180031f39  lea     rax, aIco; ".ico"
0x180031f40  mov     [rsp+58h+cchCount2], ebx; cchCount2
0x180031f44  mov     r9d, ebx; cchCount1
0x180031f47  mov     [rsp+58h+lpString2], rax; lpString2
0x180031f4c  lea     r8, [rsp+58h+String1]; lpString1
0x180031f51  mov     edx, edi; dwCmpFlags
0x180031f53  mov     ecx, esi; Locale
0x180031f55  call    cs:__imp_CompareStringW
0x180031f5b  cmp     eax, 2
0x180031f5e  jz      short loc_180031F9F
0x180031f60  lea     rax, aExe; ".exe"
0x180031f67  mov     [rsp+58h+cchCount2], ebx; cchCount2
0x180031f6b  mov     r9d, ebx; cchCount1
0x180031f6e  mov     [rsp+58h+lpString2], rax; lpString2
0x180031f73  lea     r8, [rsp+58h+String1]; lpString1
0x180031f78  mov     edx, edi; dwCmpFlags
0x180031f7a  mov     ecx, esi; Locale
0x180031f7c  call    cs:__imp_CompareStringW
0x180031f82  cmp     eax, 2
0x180031f85  jnz     loc_180031DF9
0x180031f8b  mov     eax, 6578652Eh
0x180031f90  jmp     loc_180031DFB
0x180031f95  mov     eax, 6D6F632Eh
0x180031f9a  jmp     loc_180031DFB
0x180031f9f  mov     eax, 6F63692Eh
0x180031fa4  jmp     loc_180031DFB
0x180031fa9  mov     eax, 646D632Eh
0x180031fae  jmp     loc_180031DFB
0x180031fb3  mov     eax, 6B6E6C2Eh
0x180031fb8  jmp     loc_180031DFB
0x180031fbd  mov     eax, 7461622Eh
0x180031fc2  jmp     loc_180031DFB
0x180031fc7  mov     eax, 6669702Eh
0x180031fcc  jmp     loc_180031DFB
```
