# CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(void)

- ea: `0x140009018`
- end: `0x140009117`
- name: `??1CTrackingConfig@CWsmTrackingConfig@@QEAA@XZ`
- size: `255`
- prototype: `void __fastcall(CWsmTrackingConfig::CTrackingConfig *__hidden this)`
- caller_count: `10`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140008b00`
- `0x140009300`
- `0x1400099e0`
- `0x140009ee0`
- `0x14000a300`
- `0x14000a728`
- `0x14000b1b4`
- `0x14000b550`
- `0x14000b970`
- `0x14000bdf0`

## callees

- `0x1400088ec`
- `0x140009018`
- `0x14000b280`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000905a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000906b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009093`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400090a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400090c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400090fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000905a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000906b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009093`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400090a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400090c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400090fa`

## pseudocode

```c
void __fastcall CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(void ***this)
{
  void **v2; // rdi
  void *v3; // rcx
  void **v4; // rdi
  void *v5; // rcx
  void **v6; // rcx
  void **v7; // rdx
  __int64 v8; // r8
  void **v9; // rcx

  *this = &CWsmTrackingConfig::CTrackingConfig::`vftable';
  CWsmTrackingConfig::CTrackingConfig::Release((CWsmTrackingConfig::CTrackingConfig *)this);
  v2 = this[10];
  if ( v2 )
  {
    v3 = *v2;
    if ( *v2 != v2 + 2 && v3 )
      ExFreePoolWithTag(v3, 0x6E6D7377u);
    ExFreePoolWithTag(v2, 0x6E6D7377u);
  }
  v4 = this[8];
  if ( v4 )
  {
    v5 = *v4;
    if ( *v4 != v4 + 2 && v5 )
      ExFreePoolWithTag(v5, 0x6E6D7377u);
    ExFreePoolWithTag(v4, 0x6E6D7377u);
  }
  v6 = this[4];
  if ( v6 != (void **)-1LL )
  {
    this[5] = v6;
    if ( v6 )
      ExFreePoolWithTag(v6, 0x6E6D7377u);
  }
  v7 = this[1];
  if ( v7 != (void **)-1LL )
  {
    v8 = (char *)this[2] - (char *)v7;
    this[2] = v7;
    utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>(
      v6,
      v7,
      v8 >> 3);
    v9 = this[1];
    if ( v9 )
      ExFreePoolWithTag(v9, 0x6E6D7377u);
  }
}

```

## disassembly

```asm
0x140009018  mov     [rsp+arg_0], rbx
0x14000901d  mov     [rsp+arg_8], rsi
0x140009022  push    rdi
0x140009023  sub     rsp, 20h
0x140009027  lea     rax, ??_7CTrackingConfig@CWsmTrackingConfig@@6B@; const CWsmTrackingConfig::CTrackingConfig::`vftable'
0x14000902e  mov     rbx, rcx
0x140009031  mov     [rcx], rax
0x140009034  call    ?Release@CTrackingConfig@CWsmTrackingConfig@@IEAAXXZ; CWsmTrackingConfig::CTrackingConfig::Release(void)
0x140009039  mov     rdi, [rbx+50h]
0x14000903d  mov     esi, 6E6D7377h
0x140009042  test    rdi, rdi
0x140009045  jz      short loc_140009077
0x140009047  mov     rcx, [rdi]; P
0x14000904a  lea     rax, [rdi+10h]
0x14000904e  cmp     rcx, rax
0x140009051  jz      short loc_140009066
0x140009053  test    rcx, rcx
0x140009056  jz      short loc_140009066
0x140009058  mov     edx, esi; Tag
0x14000905a  call    cs:__imp_ExFreePoolWithTag
0x140009061  nop     dword ptr [rax+rax+00h]
0x140009066  mov     edx, esi; Tag
0x140009068  mov     rcx, rdi; P
0x14000906b  call    cs:__imp_ExFreePoolWithTag
0x140009072  nop     dword ptr [rax+rax+00h]
0x140009077  mov     rdi, [rbx+40h]
0x14000907b  test    rdi, rdi
0x14000907e  jz      short loc_1400090B0
0x140009080  mov     rcx, [rdi]; P
0x140009083  lea     rax, [rdi+10h]
0x140009087  cmp     rcx, rax
0x14000908a  jz      short loc_14000909F
0x14000908c  test    rcx, rcx
0x14000908f  jz      short loc_14000909F
0x140009091  mov     edx, esi; Tag
0x140009093  call    cs:__imp_ExFreePoolWithTag
0x14000909a  nop     dword ptr [rax+rax+00h]
0x14000909f  mov     edx, esi; Tag
0x1400090a1  mov     rcx, rdi; P
0x1400090a4  call    cs:__imp_ExFreePoolWithTag
0x1400090ab  nop     dword ptr [rax+rax+00h]
0x1400090b0  mov     rcx, [rbx+20h]; P
0x1400090b4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400090b8  jz      short loc_1400090D1
0x1400090ba  mov     [rbx+28h], rcx
0x1400090be  test    rcx, rcx
0x1400090c1  jz      short loc_1400090D1
0x1400090c3  mov     edx, esi; Tag
0x1400090c5  call    cs:__imp_ExFreePoolWithTag
0x1400090cc  nop     dword ptr [rax+rax+00h]
0x1400090d1  mov     rdx, [rbx+8]
0x1400090d5  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1400090d9  jz      short loc_140009106
0x1400090db  mov     r8, [rbx+10h]
0x1400090df  sub     r8, rdx
0x1400090e2  mov     [rbx+10h], rdx
0x1400090e6  sar     r8, 3
0x1400090ea  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@@0@PEAV?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>(utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>> &,utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>> *,unsigned __int64)
0x1400090ef  mov     rcx, [rbx+8]; P
0x1400090f3  test    rcx, rcx
0x1400090f6  jz      short loc_140009106
0x1400090f8  mov     edx, esi; Tag
0x1400090fa  call    cs:__imp_ExFreePoolWithTag
0x140009101  nop     dword ptr [rax+rax+00h]
0x140009106  mov     rbx, [rsp+28h+arg_0]
0x14000910b  mov     rsi, [rsp+28h+arg_8]
0x140009110  add     rsp, 20h
0x140009114  pop     rdi
0x140009115  retn
```
