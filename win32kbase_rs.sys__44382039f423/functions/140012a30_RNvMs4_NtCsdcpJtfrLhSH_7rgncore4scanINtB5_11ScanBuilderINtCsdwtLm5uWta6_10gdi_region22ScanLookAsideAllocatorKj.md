# _RNvMs4_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE6commitB7_

- ea: `0x140012a30`
- end: `0x140012b50`
- name: `_RNvMs4_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE6commitB7_`
- size: `288`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000c640`

## callees

- `0x14000fdc0`
- `0x140012a30`
- `0x140017a10`
- `0x1400184d7`
- `0x140018630`
- `0x1400193b0`

## pseudocode

```c
__int64 __fastcall RNvMs4_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE6commitB7_(
        __int64 a1)
{
  unsigned __int64 *v1; // r14
  unsigned __int64 v2; // rdi
  unsigned __int64 v3; // rsi
  _DWORD *v4; // r8
  int v5; // ebp
  __int64 result; // rax
  __int64 v7; // r15
  unsigned __int64 v8; // rbx
  __int64 v9; // [rsp+0h] [rbp-88h] BYREF
  __int64 v10; // [rsp+38h] [rbp-50h] BYREF
  _DWORD *v11; // [rsp+40h] [rbp-48h]
  __int64 v12; // [rsp+50h] [rbp-38h]

  v1 = *(unsigned __int64 **)a1;
  v2 = *(_QWORD *)(a1 + 16);
  v3 = *(_QWORD *)(*(_QWORD *)a1 + 16LL);
  if ( v2 >= v3 )
    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
      *(_QWORD *)(a1 + 16),
      v3,
      &anon_22b06d26984f22b1c5b0f9b994440758_42_llvm_8899961222222301143);
  v4 = (_DWORD *)v1[1];
  v5 = v4[v2];
  if ( *v1 != v3 )
    goto LABEL_3;
  v7 = a1;
  v8 = 4;
  if ( 2 * v3 >= 5 )
    v8 = 2 * v3;
  RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
    &v10,
    v3,
    v4,
    v8,
    4u,
    4u);
  if ( (_DWORD)v10 != 1 )
  {
    v4 = v11;
    v1[1] = (unsigned __int64)v11;
    *v1 = v8;
    a1 = v7;
LABEL_3:
    v4[v3] = v5;
    v1[2] = v3 + 1;
    ++**(_DWORD **)(a1 + 8);
    result = 0;
    goto LABEL_4;
  }
  if ( v2 > v1[2] )
    RNvNtCs9MWeMO1rkJG_4core9panicking5panic(
      "assertion failed: index <= scan_data.len()assertion failed: ScanInternal::is_valid_scan(&&*self.scan_data, previou"
      "s_index)TryFromIntErrorseh_unwind\\src\\lib.rs",
      42,
      &anon_22b06d26984f22b1c5b0f9b994440758_44_llvm_8899961222222301143);
  v1[2] = v2;
  result = 14;
  if ( !v2 )
  {
    RNvNtCsdwtLm5uWta6_10gdi_region3ffi27RustOnZeroSizedScanCallback();
    result = 14;
  }
LABEL_4:
  if ( _security_cookie != ((unsigned __int64)&v9 ^ v12) )
    JUMPOUT(0x140012B4FLL);
  return result;
}

```

## disassembly

```asm
0x140012a30  push    r15
0x140012a32  push    r14
0x140012a34  push    rsi
0x140012a35  push    rdi
0x140012a36  push    rbp
0x140012a37  push    rbx
0x140012a38  sub     rsp, 58h
0x140012a3c  mov     rax, cs:__security_cookie
0x140012a43  xor     rax, rsp
0x140012a46  mov     [rsp+88h+var_38], rax
0x140012a4b  mov     r14, [rcx]
0x140012a4e  mov     rdi, [rcx+10h]
0x140012a52  mov     rsi, [r14+10h]
0x140012a56  cmp     rdi, rsi
0x140012a59  jnb     loc_140012B30
0x140012a5f  mov     r8, [r14+8]
0x140012a63  mov     ebp, [r8+rdi*4]
0x140012a67  cmp     [r14], rsi
0x140012a6a  jz      short loc_140012AA4
0x140012a6c  mov     [r8+rsi*4], ebp
0x140012a70  inc     rsi
0x140012a73  mov     [r14+10h], rsi
0x140012a77  mov     rax, [rcx+8]
0x140012a7b  inc     dword ptr [rax]
0x140012a7d  xor     eax, eax
0x140012a7f  mov     rcx, [rsp+88h+var_38]
0x140012a84  xor     rcx, rsp
0x140012a87  mov     rdx, cs:__security_cookie
0x140012a8e  cmp     rdx, rcx
0x140012a91  jnz     loc_140012B42
0x140012a97  add     rsp, 58h
0x140012a9b  pop     rbx
0x140012a9c  pop     rbp
0x140012a9d  pop     rdi
0x140012a9e  pop     rsi
0x140012a9f  pop     r14
0x140012aa1  pop     r15
0x140012aa3  retn
0x140012aa4  mov     r15, rcx
0x140012aa7  lea     rax, [rsi+rsi]
0x140012aab  cmp     rax, 5
0x140012aaf  mov     ebx, 4
0x140012ab4  cmovnb  rbx, rax
0x140012ab8  mov     [rsp+88h+var_60], 4
0x140012ac1  mov     [rsp+88h+var_68], 4
0x140012aca  lea     rcx, [rsp+88h+var_50]
0x140012acf  mov     rdx, rsi
0x140012ad2  mov     r9, rbx
0x140012ad5  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244
0x140012ada  cmp     dword ptr [rsp+88h+var_50], 1
0x140012adf  jnz     short loc_140012B04
0x140012ae1  cmp     rdi, [r14+10h]
0x140012ae5  ja      short loc_140012B18
0x140012ae7  mov     [r14+10h], rdi
0x140012aeb  mov     eax, 0Eh
0x140012af0  test    rdi, rdi
0x140012af3  jnz     short loc_140012A7F
0x140012af5  call    _RNvNtCsdwtLm5uWta6_10gdi_region3ffi27RustOnZeroSizedScanCallback
0x140012afa  mov     eax, 0Eh
0x140012aff  jmp     loc_140012A7F
0x140012b04  mov     r8, [rsp+88h+var_48]
0x140012b09  mov     [r14+8], r8
0x140012b0d  mov     [r14], rbx
0x140012b10  mov     rcx, r15
0x140012b13  jmp     loc_140012A6C
0x140012b18  lea     rcx, anon_22b06d26984f22b1c5b0f9b994440758_43_llvm_8899961222222301143; "assertion failed: index <= scan_data.le"...
0x140012b1f  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_44_llvm_8899961222222301143
0x140012b26  mov     edx, 2Ah ; '*'
0x140012b2b  call    _RNvNtCs9MWeMO1rkJG_4core9panicking5panic
0x140012b30  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_42_llvm_8899961222222301143
0x140012b37  mov     rcx, rdi
0x140012b3a  mov     rdx, rsi
0x140012b3d  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x140012b42  mov     rcx, [rsp+88h+var_38]
0x140012b47  xor     rcx, rsp; StackCookie
0x140012b4a  call    __security_check_cookie
```
