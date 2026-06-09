# CWsmTrackingConfig::CTrackingConfig::Release(void)

- ea: `0x14000b280`
- end: `0x14000b352`
- name: `?Release@CTrackingConfig@CWsmTrackingConfig@@IEAAXXZ`
- size: `210`
- prototype: `void __fastcall(CWsmTrackingConfig::CTrackingConfig *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140009018`
- `0x14000c6f0`

## callees

- `0x1400088ec`
- `0x14000b280`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000b2d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b2e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b31b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b32f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b2d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b2e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b31b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b32f`

## pseudocode

```c
void __fastcall CWsmTrackingConfig::CTrackingConfig::Release(CWsmTrackingConfig::CTrackingConfig *this)
{
  __int64 v1; // rdx
  __int64 v3; // r8
  void **v4; // rdi
  void *v5; // rcx
  void **v6; // rdi
  void *v7; // rcx

  v1 = *((_QWORD *)this + 1);
  v3 = *((_QWORD *)this + 2) - v1;
  *((_QWORD *)this + 2) = v1;
  utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>(
    (__int64)this,
    v1,
    v3 >> 3);
  v4 = (void **)*((_QWORD *)this + 8);
  *((_QWORD *)this + 5) = *((_QWORD *)this + 4);
  *((_QWORD *)this + 8) = 0;
  if ( v4 )
  {
    v5 = *v4;
    if ( *v4 != v4 + 2 && v5 )
      ExFreePoolWithTag(v5, 0x6E6D7377u);
    ExFreePoolWithTag(v4, 0x6E6D7377u);
  }
  v6 = (void **)*((_QWORD *)this + 10);
  *((_QWORD *)this + 10) = 0;
  if ( v6 )
  {
    v7 = *v6;
    if ( *v6 != v6 + 2 && v7 )
      ExFreePoolWithTag(v7, 0x6E6D7377u);
    ExFreePoolWithTag(v6, 0x6E6D7377u);
  }
  *(_OWORD *)((char *)this + 88) = 0;
  *(_OWORD *)((char *)this + 104) = 0;
}

```

## disassembly

```asm
0x14000b280  mov     [rsp+arg_0], rbx
0x14000b285  push    rdi
0x14000b286  sub     rsp, 20h
0x14000b28a  mov     rdx, [rcx+8]
0x14000b28e  mov     rbx, rcx
0x14000b291  mov     r8, [rcx+10h]
0x14000b295  sub     r8, rdx
0x14000b298  mov     [rcx+10h], rdx
0x14000b29c  sar     r8, 3
0x14000b2a0  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@@0@PEAV?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>(utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>> &,utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>> *,unsigned __int64)
0x14000b2a5  mov     rdi, [rbx+40h]
0x14000b2a9  mov     rax, [rbx+20h]
0x14000b2ad  mov     [rbx+28h], rax
0x14000b2b1  mov     qword ptr [rbx+40h], 0
0x14000b2b9  test    rdi, rdi
0x14000b2bc  jz      short loc_14000B2F4
0x14000b2be  mov     rcx, [rdi]; P
0x14000b2c1  lea     rax, [rdi+10h]
0x14000b2c5  cmp     rcx, rax
0x14000b2c8  jz      short loc_14000B2E0
0x14000b2ca  test    rcx, rcx
0x14000b2cd  jz      short loc_14000B2E0
0x14000b2cf  mov     edx, 6E6D7377h; Tag
0x14000b2d4  call    cs:__imp_ExFreePoolWithTag
0x14000b2db  nop     dword ptr [rax+rax+00h]
0x14000b2e0  mov     edx, 6E6D7377h; Tag
0x14000b2e5  mov     rcx, rdi; P
0x14000b2e8  call    cs:__imp_ExFreePoolWithTag
0x14000b2ef  nop     dword ptr [rax+rax+00h]
0x14000b2f4  mov     rdi, [rbx+50h]
0x14000b2f8  mov     qword ptr [rbx+50h], 0
0x14000b300  test    rdi, rdi
0x14000b303  jz      short loc_14000B33B
0x14000b305  mov     rcx, [rdi]; P
0x14000b308  lea     rax, [rdi+10h]
0x14000b30c  cmp     rcx, rax
0x14000b30f  jz      short loc_14000B327
0x14000b311  test    rcx, rcx
0x14000b314  jz      short loc_14000B327
0x14000b316  mov     edx, 6E6D7377h; Tag
0x14000b31b  call    cs:__imp_ExFreePoolWithTag
0x14000b322  nop     dword ptr [rax+rax+00h]
0x14000b327  mov     edx, 6E6D7377h; Tag
0x14000b32c  mov     rcx, rdi; P
0x14000b32f  call    cs:__imp_ExFreePoolWithTag
0x14000b336  nop     dword ptr [rax+rax+00h]
0x14000b33b  xorps   xmm0, xmm0
0x14000b33e  movups  xmmword ptr [rbx+58h], xmm0
0x14000b342  movups  xmmword ptr [rbx+68h], xmm0
0x14000b346  mov     rbx, [rsp+28h+arg_0]
0x14000b34b  add     rsp, 20h
0x14000b34f  pop     rdi
0x14000b350  retn
```
