# CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(void)

- ea: `0x1400091cc`
- end: `0x14000928f`
- name: `??1CTrackingPathInfo@CWsmTrackingConfig@@QEAA@XZ`
- size: `195`
- prototype: `void __fastcall(CWsmTrackingConfig::CTrackingPathInfo *__hidden this)`
- caller_count: `8`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400088ec`
- `0x140008bb0`
- `0x14000960c`
- `0x14000a0fc`
- `0x14000a8c4`
- `0x14000ab4c`
- `0x14000b77c`
- `0x14000c6f0`

## callees

- `0x14000888c`
- `0x1400091cc`
- `0x14000b414`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140009200`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000922b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000923f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009277`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009200`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000922b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000923f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009277`

## pseudocode

```c
void __fastcall CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(void ***this)
{
  void **v2; // rcx
  void **v3; // rdi
  void *v4; // rcx
  void **v5; // rdx
  __int64 v6; // r8
  void **v7; // rcx

  *this = &CWsmTrackingConfig::CTrackingPathInfo::`vftable';
  CWsmTrackingConfig::CTrackingPathInfo::Release((CWsmTrackingConfig::CTrackingPathInfo *)this);
  v2 = this[6];
  if ( v2 != (void **)-1LL )
  {
    this[7] = v2;
    if ( v2 )
      ExFreePoolWithTag(v2, 0x6E6D7377u);
  }
  v3 = this[5];
  if ( v3 )
  {
    v4 = *v3;
    if ( *v3 != v3 + 2 && v4 )
      ExFreePoolWithTag(v4, 0x6E6D7377u);
    ExFreePoolWithTag(v3, 0x6E6D7377u);
  }
  v5 = this[1];
  if ( v5 != (void **)-1LL )
  {
    v6 = (char *)this[2] - (char *)v5;
    this[2] = v5;
    utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>>>(
      v2,
      v5,
      v6 >> 3);
    v7 = this[1];
    if ( v7 )
      ExFreePoolWithTag(v7, 0x6E6D7377u);
  }
}

```

## disassembly

```asm
0x1400091cc  mov     [rsp+arg_0], rbx
0x1400091d1  push    rdi
0x1400091d2  sub     rsp, 20h
0x1400091d6  lea     rax, ??_7CTrackingPathInfo@CWsmTrackingConfig@@6B@; const CWsmTrackingConfig::CTrackingPathInfo::`vftable'
0x1400091dd  mov     rbx, rcx
0x1400091e0  mov     [rcx], rax
0x1400091e3  call    ?Release@CTrackingPathInfo@CWsmTrackingConfig@@IEAAXXZ; CWsmTrackingConfig::CTrackingPathInfo::Release(void)
0x1400091e8  mov     rcx, [rbx+30h]; P
0x1400091ec  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400091f0  jz      short loc_14000920C
0x1400091f2  mov     [rbx+38h], rcx
0x1400091f6  test    rcx, rcx
0x1400091f9  jz      short loc_14000920C
0x1400091fb  mov     edx, 6E6D7377h; Tag
0x140009200  call    cs:__imp_ExFreePoolWithTag
0x140009207  nop     dword ptr [rax+rax+00h]
0x14000920c  mov     rdi, [rbx+28h]
0x140009210  test    rdi, rdi
0x140009213  jz      short loc_14000924B
0x140009215  mov     rcx, [rdi]; P
0x140009218  lea     rax, [rdi+10h]
0x14000921c  cmp     rcx, rax
0x14000921f  jz      short loc_140009237
0x140009221  test    rcx, rcx
0x140009224  jz      short loc_140009237
0x140009226  mov     edx, 6E6D7377h; Tag
0x14000922b  call    cs:__imp_ExFreePoolWithTag
0x140009232  nop     dword ptr [rax+rax+00h]
0x140009237  mov     edx, 6E6D7377h; Tag
0x14000923c  mov     rcx, rdi; P
0x14000923f  call    cs:__imp_ExFreePoolWithTag
0x140009246  nop     dword ptr [rax+rax+00h]
0x14000924b  mov     rdx, [rbx+8]
0x14000924f  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x140009253  jz      short loc_140009283
0x140009255  mov     r8, [rbx+10h]
0x140009259  sub     r8, rdx
0x14000925c  mov     [rbx+10h], rdx
0x140009260  sar     r8, 3
0x140009264  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@@0@PEAV?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>>>(utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>> &,utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>> *,unsigned __int64)
0x140009269  mov     rcx, [rbx+8]; P
0x14000926d  test    rcx, rcx
0x140009270  jz      short loc_140009283
0x140009272  mov     edx, 6E6D7377h; Tag
0x140009277  call    cs:__imp_ExFreePoolWithTag
0x14000927e  nop     dword ptr [rax+rax+00h]
0x140009283  mov     rbx, [rsp+28h+arg_0]
0x140009288  add     rsp, 20h
0x14000928c  pop     rdi
0x14000928d  retn
```
