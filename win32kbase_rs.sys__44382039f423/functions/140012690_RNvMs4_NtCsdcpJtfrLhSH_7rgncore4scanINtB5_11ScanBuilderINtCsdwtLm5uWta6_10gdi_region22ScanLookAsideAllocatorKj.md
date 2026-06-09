# _RNvMs4_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE12remove_wallsB7_

- ea: `0x140012690`
- end: `0x140012767`
- name: `_RNvMs4_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE12remove_wallsB7_`
- size: `215`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14000cc10`

## callees

- `0x140012690`
- `0x140017b00`
- `0x1400184d7`
- `0x140018630`
- `0x140018690`

## pseudocode

```c
char *__fastcall RNvMs4_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE12remove_wallsB7_(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rdi
  unsigned __int64 v5; // rcx
  unsigned __int64 v6; // rdx
  __int64 v7; // rax
  int v8; // edx
  unsigned __int64 v9; // rdx
  char *result; // rax
  char *v11; // rbx
  unsigned __int64 v12; // rsi

  v4 = *a1;
  v5 = a1[2];
  v6 = *(_QWORD *)(v4 + 16);
  if ( v5 >= v6 )
    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
      v5,
      v6,
      &anon_22b06d26984f22b1c5b0f9b994440758_39_llvm_8899961222222301143);
  v7 = *(_QWORD *)(v4 + 8);
  v8 = *(_DWORD *)(v7 + 4 * v5) - a3;
  if ( v8 < 0 )
    RNvNtCs9MWeMO1rkJG_4core9panicking5panic(
      anon_22b06d26984f22b1c5b0f9b994440758_40_llvm_8899961222222301143,
      49,
      &anon_22b06d26984f22b1c5b0f9b994440758_41_llvm_8899961222222301143);
  *(_DWORD *)(v7 + 4 * v5) = v8;
  v9 = a3 + a2 + v5 + 3;
  result = *(char **)(v4 + 16);
  v11 = &result[-v9];
  if ( (unsigned __int64)result < v9 )
    RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail(
      0,
      v9,
      *(_QWORD *)(v4 + 16),
      &anon_c9360f58bbc394745aa7882ed1343abe_1_llvm_18110786352924170244);
  v12 = a2 + v5 + 3;
  if ( v12 > v9 )
    RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail(
      v12,
      v9,
      *(_QWORD *)(v4 + 16),
      &anon_c9360f58bbc394745aa7882ed1343abe_2_llvm_18110786352924170244);
  *(_QWORD *)(v4 + 16) = v12;
  if ( a3 )
  {
    if ( result == (char *)v9 )
      return result;
    result = (char *)memmove(
                       (void *)(*(_QWORD *)(v4 + 8) + 4 * v12),
                       (const void *)(*(_QWORD *)(v4 + 8) + 4 * v9),
                       4LL * (_QWORD)v11);
  }
  else if ( result == (char *)v9 )
  {
    return result;
  }
  *(_QWORD *)(v4 + 16) = &v11[v12];
  return result;
}

```

## disassembly

```asm
0x140012690  push    rsi
0x140012691  push    rdi
0x140012692  push    rbx
0x140012693  sub     rsp, 20h
0x140012697  mov     r9, rdx
0x14001269a  mov     rdi, [rcx]
0x14001269d  mov     rcx, [rcx+10h]
0x1400126a1  mov     rdx, [rdi+10h]
0x1400126a5  cmp     rcx, rdx
0x1400126a8  jnb     loc_14001275A
0x1400126ae  mov     rax, [rdi+8]
0x1400126b2  mov     edx, [rax+rcx*4]
0x1400126b5  sub     edx, r8d
0x1400126b8  js      short loc_14001271F
0x1400126ba  mov     [rax+rcx*4], edx
0x1400126bd  lea     rax, [r9+rcx]
0x1400126c1  lea     rdx, [r8+rax]
0x1400126c5  add     rdx, 3
0x1400126c9  mov     rax, [rdi+10h]
0x1400126cd  mov     rbx, rax
0x1400126d0  sub     rbx, rdx
0x1400126d3  jb      short loc_140012737
0x1400126d5  lea     rsi, [r9+rcx]
0x1400126d9  add     rsi, 3
0x1400126dd  cmp     rsi, rdx
0x1400126e0  ja      short loc_140012748
0x1400126e2  mov     [rdi+10h], rsi
0x1400126e6  test    r8, r8
0x1400126e9  jz      short loc_14001270B
0x1400126eb  cmp     rax, rdx
0x1400126ee  jz      short loc_140012717
0x1400126f0  mov     rax, [rdi+8]
0x1400126f4  lea     rcx, [rax+rsi*4]; void *
0x1400126f8  lea     rdx, [rax+rdx*4]; Src
0x1400126fc  lea     r8, ds:0[rbx*4]; Size
0x140012704  call    memmove
0x140012709  jmp     short loc_140012710
0x14001270b  cmp     rax, rdx
0x14001270e  jz      short loc_140012717
0x140012710  add     rbx, rsi
0x140012713  mov     [rdi+10h], rbx
0x140012717  add     rsp, 20h
0x14001271b  pop     rbx
0x14001271c  pop     rdi
0x14001271d  pop     rsi
0x14001271e  retn
0x14001271f  lea     rcx, anon_22b06d26984f22b1c5b0f9b994440758_40_llvm_8899961222222301143
0x140012726  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_41_llvm_8899961222222301143
0x14001272d  mov     edx, 31h ; '1'
0x140012732  call    _RNvNtCs9MWeMO1rkJG_4core9panicking5panic
0x140012737  lea     r9, anon_c9360f58bbc394745aa7882ed1343abe_1_llvm_18110786352924170244
0x14001273e  xor     ecx, ecx
0x140012740  mov     r8, rax
0x140012743  call    _RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail
0x140012748  lea     r9, anon_c9360f58bbc394745aa7882ed1343abe_2_llvm_18110786352924170244
0x14001274f  mov     rcx, rsi
0x140012752  mov     r8, rax
0x140012755  call    _RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail
0x14001275a  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_39_llvm_8899961222222301143
0x140012761  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
```
