# _RNvMs4_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE8pop_wallCs7vXzV21FY6F_8gdi_rust

- ea: `0x14000fab0`
- end: `0x14000fb1d`
- name: `_RNvMs4_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE8pop_wallCs7vXzV21FY6F_8gdi_rust`
- size: `109`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1400101f0`

## callees

- `0x14000fab0`
- `0x14000fdc0`
- `0x1400184d7`
- `0x140018630`

## pseudocode

```c
__int64 __fastcall RNvMs4_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE8pop_wallCs7vXzV21FY6F_8gdi_rust(
        __int64 *a1)
{
  __int64 result; // rax
  unsigned __int64 v2; // rcx
  unsigned __int64 v3; // rdx
  __int64 v4; // rdx
  int v5; // r8d
  __int64 v6; // rcx
  __int64 v7; // rcx

  result = *a1;
  v2 = a1[2];
  v3 = *(_QWORD *)(result + 16);
  if ( v2 >= v3 )
    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
      v2,
      v3,
      &anon_01189c164b0c425bf67614ee34d1a89c_28_llvm_7541658972310832757);
  v4 = *(_QWORD *)(result + 8);
  v5 = *(_DWORD *)(v4 + 4 * v2);
  if ( v5 <= 0 )
    RNvNtCs9MWeMO1rkJG_4core9panicking5panic(
      &anon_01189c164b0c425bf67614ee34d1a89c_29_llvm_7541658972310832757,
      33,
      &anon_01189c164b0c425bf67614ee34d1a89c_30_llvm_7541658972310832757);
  *(_DWORD *)(v4 + 4 * v2) = v5 - 1;
  v6 = *(_QWORD *)(result + 16);
  if ( !v6 )
    return RNvNtCsdwtLm5uWta6_10gdi_region3ffi27RustOnZeroSizedScanCallback();
  v7 = v6 - 1;
  *(_QWORD *)(result + 16) = v7;
  if ( !v7 )
    return RNvNtCsdwtLm5uWta6_10gdi_region3ffi27RustOnZeroSizedScanCallback();
  return result;
}

```

## disassembly

```asm
0x14000fab0  sub     rsp, 28h
0x14000fab4  mov     rax, [rcx]
0x14000fab7  mov     rcx, [rcx+10h]
0x14000fabb  mov     rdx, [rax+10h]
0x14000fabf  cmp     rcx, rdx
0x14000fac2  jnb     short loc_14000FB10
0x14000fac4  mov     rdx, [rax+8]
0x14000fac8  mov     r8d, [rdx+rcx*4]
0x14000facc  test    r8d, r8d
0x14000facf  jle     short loc_14000FAF8
0x14000fad1  dec     r8d
0x14000fad4  mov     [rdx+rcx*4], r8d
0x14000fad8  mov     rcx, [rax+10h]
0x14000fadc  test    rcx, rcx
0x14000fadf  jz      short loc_14000FAEF
0x14000fae1  dec     rcx
0x14000fae4  mov     [rax+10h], rcx
0x14000fae8  jz      short loc_14000FAEF
0x14000faea  add     rsp, 28h
0x14000faee  retn
0x14000faef  add     rsp, 28h
0x14000faf3  jmp     _RNvNtCsdwtLm5uWta6_10gdi_region3ffi27RustOnZeroSizedScanCallback
0x14000faf8  lea     rcx, anon_01189c164b0c425bf67614ee34d1a89c_29_llvm_7541658972310832757
0x14000faff  lea     r8, anon_01189c164b0c425bf67614ee34d1a89c_30_llvm_7541658972310832757
0x14000fb06  mov     edx, 21h ; '!'
0x14000fb0b  call    _RNvNtCs9MWeMO1rkJG_4core9panicking5panic
0x14000fb10  lea     r8, anon_01189c164b0c425bf67614ee34d1a89c_28_llvm_7541658972310832757
0x14000fb17  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
```
