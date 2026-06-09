# _RNvMs4_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11append_wallCs7vXzV21FY6F_8gdi_rust

- ea: `0x14000f720`
- end: `0x14000f7f2`
- name: `_RNvMs4_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11append_wallCs7vXzV21FY6F_8gdi_rust`
- size: `210`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400101f0`

## callees

- `0x14000f720`
- `0x140017a10`
- `0x1400184d7`
- `0x140018ab0`

## pseudocode

```c
__int64 __fastcall RNvMs4_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11append_wallCs7vXzV21FY6F_8gdi_rust(
        __int64 a1,
        int a2)
{
  __int64 *v2; // rsi
  unsigned __int64 v3; // rcx
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 result; // rax
  int v7; // ebp
  unsigned __int64 v8; // rdi
  __int64 v9; // [rsp+0h] [rbp-68h] BYREF
  __int64 v10; // [rsp+28h] [rbp-40h] BYREF
  __int64 v11; // [rsp+30h] [rbp-38h]
  __int64 v12; // [rsp+40h] [rbp-28h]

  v2 = *(__int64 **)a1;
  v3 = *(_QWORD *)(a1 + 16);
  if ( v3 >= v2[2] )
    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
      v3,
      v2[2],
      &anon_01189c164b0c425bf67614ee34d1a89c_17_llvm_7541658972310832757);
  ++*(_DWORD *)(v2[1] + 4 * v3);
  v4 = v2[2];
  if ( *v2 != v4 )
  {
    v5 = v2[1];
LABEL_4:
    *(_DWORD *)(v5 + 4 * v4) = a2;
    ++v2[2];
    result = 0;
    goto LABEL_5;
  }
  v7 = a2;
  v8 = 4;
  if ( (unsigned __int64)(2 * v4) >= 5 )
    v8 = 2 * v4;
  RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCs7vXzV21FY6F_8gdi_rust_llvm_1180095224807683263(
    &v10,
    v2,
    v8,
    4u,
    4u);
  if ( (_DWORD)v10 != 1 )
  {
    v5 = v11;
    v2[1] = v11;
    *v2 = v8;
    a2 = v7;
    goto LABEL_4;
  }
  result = 14;
LABEL_5:
  if ( _security_cookie != ((unsigned __int64)&v9 ^ v12) )
    JUMPOUT(0x14000F7F1LL);
  return result;
}

```

## disassembly

```asm
0x14000f720  push    rsi
0x14000f721  push    rdi
0x14000f722  push    rbp
0x14000f723  push    rbx
0x14000f724  sub     rsp, 48h
0x14000f728  mov     rax, cs:__security_cookie
0x14000f72f  xor     rax, rsp
0x14000f732  mov     [rsp+68h+var_28], rax
0x14000f737  mov     rsi, [rcx]
0x14000f73a  mov     rcx, [rcx+10h]
0x14000f73e  mov     rax, [rsi+10h]
0x14000f742  cmp     rcx, rax
0x14000f745  jnb     loc_14000F7D5
0x14000f74b  mov     rax, [rsi+8]
0x14000f74f  inc     dword ptr [rax+rcx*4]
0x14000f752  mov     rbx, [rsi+10h]
0x14000f756  cmp     [rsi], rbx
0x14000f759  jz      short loc_14000F785
0x14000f75b  mov     rax, [rsi+8]
0x14000f75f  mov     [rax+rbx*4], edx
0x14000f762  inc     qword ptr [rsi+10h]
0x14000f766  xor     eax, eax
0x14000f768  mov     rcx, [rsp+68h+var_28]
0x14000f76d  xor     rcx, rsp
0x14000f770  mov     rdx, cs:__security_cookie
0x14000f777  cmp     rdx, rcx
0x14000f77a  jnz     short loc_14000F7E4
0x14000f77c  add     rsp, 48h
0x14000f780  pop     rbx
0x14000f781  pop     rbp
0x14000f782  pop     rdi
0x14000f783  pop     rsi
0x14000f784  retn
0x14000f785  mov     ebp, edx
0x14000f787  lea     rax, [rbx+rbx]
0x14000f78b  cmp     rax, 5
0x14000f78f  mov     edi, 4
0x14000f794  cmovnb  rdi, rax
0x14000f798  mov     [rsp+68h+var_48], 4
0x14000f7a1  lea     rcx, [rsp+68h+var_40]
0x14000f7a6  mov     r9d, 4
0x14000f7ac  mov     rdx, rsi
0x14000f7af  mov     r8, rdi
0x14000f7b2  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCs7vXzV21FY6F_8gdi_rust_llvm_1180095224807683263
0x14000f7b7  cmp     dword ptr [rsp+68h+var_40], 1
0x14000f7bc  jnz     short loc_14000F7C5
0x14000f7be  mov     eax, 0Eh
0x14000f7c3  jmp     short loc_14000F768
0x14000f7c5  mov     rax, [rsp+68h+var_38]
0x14000f7ca  mov     [rsi+8], rax
0x14000f7ce  mov     [rsi], rdi
0x14000f7d1  mov     edx, ebp
0x14000f7d3  jmp     short loc_14000F75F
0x14000f7d5  lea     r8, anon_01189c164b0c425bf67614ee34d1a89c_17_llvm_7541658972310832757
0x14000f7dc  mov     rdx, rax
0x14000f7df  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x14000f7e4  mov     rcx, [rsp+68h+var_28]
0x14000f7e9  xor     rcx, rsp; StackCookie
0x14000f7ec  call    __security_check_cookie
```
