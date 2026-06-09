# _RNvXs6_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EENtNtNtCs9MWeMO1rkJG_4core3ops4drop4Drop4dropB7_

- ea: `0x140013270`
- end: `0x1400132b1`
- name: `_RNvXs6_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EENtNtNtCs9MWeMO1rkJG_4core3ops4drop4Drop4dropB7_`
- size: `65`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14000cc10`

## callees

- `0x14000fdc0`
- `0x140013270`
- `0x140018630`

## pseudocode

```c
__int64 __fastcall RNvXs6_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EENtNtNtCs9MWeMO1rkJG_4core3ops4drop4Drop4dropB7_(
        __int64 *a1)
{
  __int64 result; // rax
  unsigned __int64 v2; // rcx

  result = *a1;
  v2 = a1[2];
  if ( v2 > *(_QWORD *)(result + 16) )
    RNvNtCs9MWeMO1rkJG_4core9panicking5panic(
      "assertion failed: index <= scan_data.len()assertion failed: ScanInternal::is_valid_scan(&&*self.scan_data, previou"
      "s_index)TryFromIntErrorseh_unwind\\src\\lib.rs",
      42,
      &anon_22b06d26984f22b1c5b0f9b994440758_44_llvm_8899961222222301143);
  *(_QWORD *)(result + 16) = v2;
  if ( !v2 )
    return RNvNtCsdwtLm5uWta6_10gdi_region3ffi27RustOnZeroSizedScanCallback();
  return result;
}

```

## disassembly

```asm
0x140013270  sub     rsp, 28h
0x140013274  mov     rax, [rcx]
0x140013277  mov     rcx, [rcx+10h]
0x14001327b  cmp     rcx, [rax+10h]
0x14001327f  ja      short loc_140013298
0x140013281  mov     [rax+10h], rcx
0x140013285  test    rcx, rcx
0x140013288  jz      short loc_14001328F
0x14001328a  add     rsp, 28h
0x14001328e  retn
0x14001328f  add     rsp, 28h
0x140013293  jmp     _RNvNtCsdwtLm5uWta6_10gdi_region3ffi27RustOnZeroSizedScanCallback
0x140013298  lea     rcx, anon_22b06d26984f22b1c5b0f9b994440758_43_llvm_8899961222222301143; "assertion failed: index <= scan_data.le"...
0x14001329f  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_44_llvm_8899961222222301143
0x1400132a6  mov     edx, 2Ah ; '*'
0x1400132ab  call    _RNvNtCs9MWeMO1rkJG_4core9panicking5panic
```
