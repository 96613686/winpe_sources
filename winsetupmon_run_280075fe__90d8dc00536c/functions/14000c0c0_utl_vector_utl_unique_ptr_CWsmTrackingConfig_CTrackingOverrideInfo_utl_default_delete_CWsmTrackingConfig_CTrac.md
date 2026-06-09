# utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>>>::_GrowMinimum(unsigned __int64)

- ea: `0x14000c0c0`
- end: `0x14000c1d1`
- name: `?_GrowMinimum@?$vector@V?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@@2@@utl@@AEAA_N_K@Z`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000d174`

## callees

- `0x14000888c`
- `0x140009368`
- `0x14000c0c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000c1a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c1a6`

## pseudocode

```c
char __fastcall utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>>>::_GrowMinimum(
        __int64 *a1,
        const struct std::nothrow_t *a2)
{
  unsigned __int64 v3; // rax
  __int64 v4; // rsi
  _QWORD *v5; // rbx
  __int64 v6; // r8
  char *v7; // r14
  __int64 v8; // rcx
  __int64 v9; // rdx
  char v10; // si
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r8
  char *v15; // rbp

  v3 = 7 * ((unsigned __int64)((a1[2] - *a1) >> 3) >> 2) + 8;
  if ( v3 < (unsigned __int64)a2 )
    v3 = (unsigned __int64)a2;
  if ( v3 > 0xFFFFFFFFFFFFFFFLL )
    v3 = 0xFFFFFFFFFFFFFFFLL;
  if ( (unsigned __int64)a2 > v3 )
    return 0;
  v4 = v3;
  v5 = operator new(8 * v3, a2);
  if ( (unsigned __int64)v5 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    return 0;
  v6 = *a1;
  v7 = (char *)&v5[v4];
  v8 = 0;
  v9 = (a1[1] - *a1) >> 3;
  v10 = 1;
  if ( v9 )
  {
    do
    {
      v11 = *(_QWORD *)(v6 + 8 * v8);
      *(_QWORD *)(v6 + 8 * v8) = 0;
      v5[v8++] = v11;
    }
    while ( v8 != v9 );
  }
  utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>>>(
    v8,
    (__int64)v5,
    0);
  v13 = *a1;
  v14 = (a1[1] - *a1) >> 3;
  v15 = (char *)&v5[v14];
  if ( *a1 != -1 )
  {
    a1[1] = v13;
    utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>>>(
      v12,
      v13,
      v14);
    if ( *a1 )
      ExFreePoolWithTag((PVOID)*a1, 0x6E6D7377u);
  }
  *a1 = (__int64)v5;
  a1[1] = (__int64)v15;
  a1[2] = (__int64)v7;
  return v10;
}

```

## disassembly

```asm
0x14000c0c0  push    rbx
0x14000c0c2  push    rbp
0x14000c0c3  push    rsi
0x14000c0c4  push    rdi
0x14000c0c5  push    r14
0x14000c0c7  sub     rsp, 20h
0x14000c0cb  mov     r8, [rcx+10h]
0x14000c0cf  mov     rdi, rcx
0x14000c0d2  sub     r8, [rcx]
0x14000c0d5  mov     rcx, 0FFFFFFFFFFFFFFFh
0x14000c0df  sar     r8, 3
0x14000c0e3  shr     r8, 2
0x14000c0e7  imul    rax, r8, 7
0x14000c0eb  add     rax, 8
0x14000c0ef  cmp     rax, rdx
0x14000c0f2  cmovb   rax, rdx
0x14000c0f6  cmp     rax, rcx
0x14000c0f9  cmova   rax, rcx
0x14000c0fd  cmp     rdx, rax
0x14000c100  ja      loc_14000C1BF
0x14000c106  mov     rcx, 1FFFFFFFFFFFFFFFh
0x14000c110  cmp     rax, rcx
0x14000c113  ja      loc_14000C1BF
0x14000c119  lea     rsi, ds:0[rax*8]
0x14000c121  mov     rcx, rsi; NumberOfBytes
0x14000c124  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000c129  mov     rbx, rax
0x14000c12c  dec     rax
0x14000c12f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000c133  ja      loc_14000C1BF
0x14000c139  mov     r8, [rdi]
0x14000c13c  lea     r14, [rsi+rbx]
0x14000c140  mov     rdx, [rdi+8]
0x14000c144  xor     ecx, ecx
0x14000c146  sub     rdx, r8
0x14000c149  sar     rdx, 3
0x14000c14d  lea     esi, [rcx+1]
0x14000c150  test    rdx, rdx
0x14000c153  jz      short loc_14000C16D
0x14000c155  mov     rax, [r8+rcx*8]
0x14000c159  mov     qword ptr [r8+rcx*8], 0
0x14000c161  mov     [rbx+rcx*8], rax
0x14000c165  add     rcx, rsi
0x14000c168  cmp     rcx, rdx
0x14000c16b  jnz     short loc_14000C155
0x14000c16d  xor     r8d, r8d
0x14000c170  mov     rdx, rbx
0x14000c173  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@@0@PEAV?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>>>(utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>> &,utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>> *,unsigned __int64)
0x14000c178  mov     rdx, [rdi]
0x14000c17b  mov     r8, [rdi+8]
0x14000c17f  sub     r8, rdx
0x14000c182  sar     r8, 3
0x14000c186  lea     rbp, [rbx+r8*8]
0x14000c18a  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x14000c18e  jz      short loc_14000C1B2
0x14000c190  mov     [rdi+8], rdx
0x14000c194  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@@0@PEAV?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>>>(utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>> &,utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>> *,unsigned __int64)
0x14000c199  mov     rcx, [rdi]; P
0x14000c19c  test    rcx, rcx
0x14000c19f  jz      short loc_14000C1B2
0x14000c1a1  mov     edx, 6E6D7377h; Tag
0x14000c1a6  call    cs:__imp_ExFreePoolWithTag
0x14000c1ad  nop     dword ptr [rax+rax+00h]
0x14000c1b2  mov     [rdi], rbx
0x14000c1b5  mov     [rdi+8], rbp
0x14000c1b9  mov     [rdi+10h], r14
0x14000c1bd  jmp     short loc_14000C1C2
0x14000c1bf  xor     sil, sil
0x14000c1c2  mov     al, sil
0x14000c1c5  add     rsp, 20h
0x14000c1c9  pop     r14
0x14000c1cb  pop     rdi
0x14000c1cc  pop     rsi
0x14000c1cd  pop     rbp
0x14000c1ce  pop     rbx
0x14000c1cf  retn
```
