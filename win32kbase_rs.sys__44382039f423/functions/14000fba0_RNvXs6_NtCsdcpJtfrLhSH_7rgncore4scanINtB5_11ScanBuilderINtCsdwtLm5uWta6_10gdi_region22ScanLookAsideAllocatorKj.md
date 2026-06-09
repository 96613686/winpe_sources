# _RNvXs6_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EENtNtNtCs9MWeMO1rkJG_4core3ops4drop4Drop4dropCs7vXzV21FY6F_8gdi_rust

- ea: `0x14000fba0`
- end: `0x14000fbe1`
- name: `_RNvXs6_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EENtNtNtCs9MWeMO1rkJG_4core3ops4drop4Drop4dropCs7vXzV21FY6F_8gdi_rust`
- size: `65`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400101f0`

## callees

- `0x14000fba0`
- `0x14000fdc0`
- `0x140018630`

## pseudocode

```c
__int64 __fastcall RNvXs6_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EENtNtNtCs9MWeMO1rkJG_4core3ops4drop4Drop4dropCs7vXzV21FY6F_8gdi_rust(
        __int64 *a1)
{
  __int64 result; // rax
  unsigned __int64 v2; // rcx

  result = *a1;
  v2 = a1[2];
  if ( v2 > *(_QWORD *)(result + 16) )
    RNvNtCs9MWeMO1rkJG_4core9panicking5panic(
      anon_01189c164b0c425bf67614ee34d1a89c_19_llvm_7541658972310832757,
      42,
      &anon_01189c164b0c425bf67614ee34d1a89c_20_llvm_7541658972310832757);
  *(_QWORD *)(result + 16) = v2;
  if ( !v2 )
    return RNvNtCsdwtLm5uWta6_10gdi_region3ffi27RustOnZeroSizedScanCallback();
  return result;
}

```

## disassembly

```asm
0x14000fba0  sub     rsp, 28h
0x14000fba4  mov     rax, [rcx]
0x14000fba7  mov     rcx, [rcx+10h]
0x14000fbab  cmp     rcx, [rax+10h]
0x14000fbaf  ja      short loc_14000FBC8
0x14000fbb1  mov     [rax+10h], rcx
0x14000fbb5  test    rcx, rcx
0x14000fbb8  jz      short loc_14000FBBF
0x14000fbba  add     rsp, 28h
0x14000fbbe  retn
0x14000fbbf  add     rsp, 28h
0x14000fbc3  jmp     _RNvNtCsdwtLm5uWta6_10gdi_region3ffi27RustOnZeroSizedScanCallback
0x14000fbc8  lea     rcx, anon_01189c164b0c425bf67614ee34d1a89c_19_llvm_7541658972310832757
0x14000fbcf  lea     r8, anon_01189c164b0c425bf67614ee34d1a89c_20_llvm_7541658972310832757
0x14000fbd6  mov     edx, 2Ah ; '*'
0x14000fbdb  call    _RNvNtCs9MWeMO1rkJG_4core9panicking5panic
```
