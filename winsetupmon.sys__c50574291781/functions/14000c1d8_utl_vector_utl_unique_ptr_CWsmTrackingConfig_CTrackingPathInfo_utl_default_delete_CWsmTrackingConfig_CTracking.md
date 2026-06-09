# utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>::_SetCapacity(unsigned __int64)

- ea: `0x14000c1d8`
- end: `0x14000c2b3`
- name: `?_SetCapacity@?$vector@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@@2@@utl@@AEAA_N_K@Z`
- size: `219`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000b77c`
- `0x14000d21c`

## callees

- `0x1400088ec`
- `0x140009368`
- `0x14000c1d8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000c288`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c288`

## pseudocode

```c
char __fastcall utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>::_SetCapacity(
        __int64 *a1,
        const struct std::nothrow_t *a2)
{
  __int64 v3; // rsi
  _QWORD *v4; // rdi
  _QWORD *v5; // r8
  char *v6; // r14
  __int64 v7; // rcx
  __int64 v8; // rdx
  char v9; // si
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8
  char *v14; // rbp

  if ( (unsigned __int64)a2 > 0x1FFFFFFFFFFFFFFFLL )
    return 0;
  v3 = (__int64)a2;
  v4 = operator new(8LL * (_QWORD)a2, a2);
  if ( (((unsigned __int64)v4 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    return 0;
  v5 = (_QWORD *)*a1;
  v6 = (char *)&v4[v3];
  v7 = 0;
  v8 = (a1[1] - *a1) >> 3;
  v9 = 1;
  if ( v8 )
  {
    do
    {
      v10 = v5[v7];
      v5[v7] = 0;
      v4[v7++] = v10;
    }
    while ( v7 != v8 );
  }
  utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>(
    v7,
    (__int64)v4,
    0);
  v12 = *a1;
  v13 = (a1[1] - *a1) >> 3;
  v14 = (char *)&v4[v13];
  if ( *a1 != -1 )
  {
    a1[1] = v12;
    utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>(
      v11,
      v12,
      v13);
    if ( *a1 )
      ExFreePoolWithTag((PVOID)*a1, 0x6E6D7377u);
  }
  *a1 = (__int64)v4;
  a1[1] = (__int64)v14;
  a1[2] = (__int64)v6;
  return v9;
}

```

## disassembly

```asm
0x14000c1d8  push    rbx
0x14000c1da  push    rbp
0x14000c1db  push    rsi
0x14000c1dc  push    rdi
0x14000c1dd  push    r14
0x14000c1df  sub     rsp, 20h
0x14000c1e3  mov     rax, 1FFFFFFFFFFFFFFFh
0x14000c1ed  mov     rbx, rcx
0x14000c1f0  cmp     rdx, rax
0x14000c1f3  ja      loc_14000C2A1
0x14000c1f9  lea     rsi, ds:0[rdx*8]
0x14000c201  mov     rcx, rsi; NumberOfBytes
0x14000c204  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000c209  mov     rdi, rax
0x14000c20c  inc     rax
0x14000c20f  test    rax, 0FFFFFFFFFFFFFFFEh
0x14000c215  jz      loc_14000C2A1
0x14000c21b  mov     r8, [rbx]
0x14000c21e  lea     r14, [rsi+rdi]
0x14000c222  mov     rdx, [rbx+8]
0x14000c226  xor     ecx, ecx
0x14000c228  sub     rdx, r8
0x14000c22b  sar     rdx, 3
0x14000c22f  lea     esi, [rcx+1]
0x14000c232  test    rdx, rdx
0x14000c235  jz      short loc_14000C24F
0x14000c237  mov     rax, [r8+rcx*8]
0x14000c23b  mov     qword ptr [r8+rcx*8], 0
0x14000c243  mov     [rdi+rcx*8], rax
0x14000c247  add     rcx, rsi
0x14000c24a  cmp     rcx, rdx
0x14000c24d  jnz     short loc_14000C237
0x14000c24f  xor     r8d, r8d
0x14000c252  mov     rdx, rdi
0x14000c255  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@@0@PEAV?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>(utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>> &,utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>> *,unsigned __int64)
0x14000c25a  mov     rdx, [rbx]
0x14000c25d  mov     r8, [rbx+8]
0x14000c261  sub     r8, rdx
0x14000c264  sar     r8, 3
0x14000c268  lea     rbp, [rdi+r8*8]
0x14000c26c  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x14000c270  jz      short loc_14000C294
0x14000c272  mov     [rbx+8], rdx
0x14000c276  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@@0@PEAV?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>(utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>> &,utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>> *,unsigned __int64)
0x14000c27b  mov     rcx, [rbx]; P
0x14000c27e  test    rcx, rcx
0x14000c281  jz      short loc_14000C294
0x14000c283  mov     edx, 6E6D7377h; Tag
0x14000c288  call    cs:__imp_ExFreePoolWithTag
0x14000c28f  nop     dword ptr [rax+rax+00h]
0x14000c294  mov     [rbx], rdi
0x14000c297  mov     [rbx+8], rbp
0x14000c29b  mov     [rbx+10h], r14
0x14000c29f  jmp     short loc_14000C2A4
0x14000c2a1  xor     sil, sil
0x14000c2a4  mov     al, sil
0x14000c2a7  add     rsp, 20h
0x14000c2ab  pop     r14
0x14000c2ad  pop     rdi
0x14000c2ae  pop     rsi
0x14000c2af  pop     rbp
0x14000c2b0  pop     rbx
0x14000c2b1  retn
```
