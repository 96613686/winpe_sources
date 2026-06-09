# AccessibilityDialog::ComputeRectForFlyout(void)

- ea: `0x14001f948`
- end: `0x14001fadb`
- name: `?ComputeRectForFlyout@AccessibilityDialog@@AEAA?AUtagRECT@@XZ`
- size: `403`
- prototype: `struct tagRECT *__fastcall(AccessibilityDialog *__hidden this, struct tagRECT *__return_ptr __struct_ptr retstr)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14001fb44`

## callees

- `0x14001eecc`
- `0x14001f948`
- `0x1400203d8`
- `0x140020d98`
- `0x140021130`
- `0x140021e38`

## pseudocode

```c
struct tagRECT *__fastcall AccessibilityDialog::ComputeRectForFlyout(
        AccessibilityDialog *this,
        struct tagRECT *__return_ptr retstr)
{
  LONG *p_top; // rdi
  int v5; // r14d
  int v6; // r15d
  __int64 v7; // rcx
  __int64 v8; // rdx
  int v9; // ebx
  int v10; // eax
  int v11; // ebx
  LONG left; // ebx
  LONG v13; // ebx
  __int64 v14; // rdx
  LONG v15; // r14d
  struct tagRECT v17; // [rsp+20h] [rbp-48h] BYREF
  char v18; // [rsp+78h] [rbp+10h] BYREF

  AccessibilityDialog::GetMonitorRect(this, &v17);
  p_top = &retstr->top;
  v5 = v17.right - v17.left;
  v6 = v17.bottom - v17.top;
  *retstr = 0;
  v18 = 0;
  if ( (int)wil::wnf_query_nothrow<tagRECT>(v7, &v18, retstr) >= 0 && (retstr->left || *p_top) )
  {
    LOBYTE(v8) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AFGU>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_AFGU>::GetImpl'::`2'::impl,
      v8);
    v9 = (int)AccessibilityDialog::LogicalToPhysicalSize(this, 358) / 2;
    v10 = (int)AccessibilityDialog::LogicalToPhysicalSize(this, 40) / 2 - v9;
    v11 = *p_top;
    retstr->left += v10;
    *p_top = v11 - AccessibilityDialog::LogicalToPhysicalSize(this, 358);
    left = retstr->left;
    if ( retstr->left < 0 )
    {
      left = AccessibilityDialog::LogicalToPhysicalSize(this, 12);
      retstr->left = left;
    }
    if ( (int)(left + AccessibilityDialog::LogicalToPhysicalSize(this, 370)) > v5 )
      retstr->left = v5 - AccessibilityDialog::LogicalToPhysicalSize(this, 370);
    v13 = *p_top;
    if ( *p_top < 0 )
    {
      v13 = AccessibilityDialog::LogicalToPhysicalSize(this, 12);
      *p_top = v13;
    }
    if ( (int)(v13 + AccessibilityDialog::LogicalToPhysicalSize(this, 358)) > v6 )
      *p_top = v6 - AccessibilityDialog::LogicalToPhysicalSize(this, 358);
  }
  else
  {
    *p_top = v6 - AccessibilityDialog::LogicalToPhysicalSize(this, 416);
    LOBYTE(v14) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AFGU>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_AFGU>::GetImpl'::`2'::impl,
      v14);
    if ( anonymous_namespace_::IsRightToLeft() )
      v15 = AccessibilityDialog::LogicalToPhysicalSize(this, 12);
    else
      v15 = v5 - AccessibilityDialog::LogicalToPhysicalSize(this, 370);
    retstr->left = v15;
  }
  retstr->right = retstr->left;
  retstr->bottom = *p_top;
  return retstr;
}

```

## disassembly

```asm
0x14001f948  push    rbx
0x14001f94a  push    rbp
0x14001f94b  push    rsi
0x14001f94c  push    rdi
0x14001f94d  push    r14
0x14001f94f  push    r15
0x14001f951  sub     rsp, 38h
0x14001f955  mov     rsi, rdx
0x14001f958  mov     rbp, rcx
0x14001f95b  lea     rdx, [rsp+68h+var_48]; retstr
0x14001f960  call    ?GetMonitorRect@AccessibilityDialog@@AEAA?AUtagRECT@@XZ; AccessibilityDialog::GetMonitorRect(void)
0x14001f965  mov     r14d, [rsp+68h+var_48.right]
0x14001f96a  lea     rdx, [rsp+68h+arg_8]
0x14001f96f  mov     r15d, [rsp+68h+var_48.bottom]
0x14001f974  lea     rdi, [rsi+4]
0x14001f978  sub     r14d, [rsp+68h+var_48.left]
0x14001f97d  xorps   xmm0, xmm0
0x14001f980  sub     r15d, [rsp+68h+var_48.top]
0x14001f985  mov     r8, rsi
0x14001f988  movups  xmmword ptr [rsi], xmm0
0x14001f98b  mov     [rsp+68h+arg_8], 0
0x14001f990  call    ??$wnf_query_nothrow@UtagRECT@@@wil@@YAJAEBU_WNF_STATE_NAME@@PEA_NPEAUtagRECT@@PEAUWNF_CHANGE_STAMP_STRUCT@0@@Z; wil::wnf_query_nothrow<tagRECT>(_WNF_STATE_NAME const &,bool *,tagRECT *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x14001f995  test    eax, eax
0x14001f997  js      loc_14001FA74
0x14001f99d  cmp     dword ptr [rsi], 0
0x14001f9a0  jnz     short loc_14001F9AB
0x14001f9a2  cmp     dword ptr [rdi], 0
0x14001f9a5  jz      loc_14001FA74
0x14001f9ab  mov     dl, 1
0x14001f9ad  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AFGU@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AFGU@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AFGU> `wil::Feature<__WilFeatureTraits_Feature_AFGU>::GetImpl(void)'::`2'::impl
0x14001f9b4  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AFGU@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AFGU>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14001f9b9  mov     edx, 166h; int
0x14001f9be  mov     rcx, rbp; this
0x14001f9c1  call    ?LogicalToPhysicalSize@AccessibilityDialog@@AEAAHH@Z; AccessibilityDialog::LogicalToPhysicalSize(int)
0x14001f9c6  cdq
0x14001f9c7  mov     rcx, rbp; this
0x14001f9ca  sub     eax, edx
0x14001f9cc  mov     edx, 28h ; '('; int
0x14001f9d1  sar     eax, 1
0x14001f9d3  mov     ebx, eax
0x14001f9d5  call    ?LogicalToPhysicalSize@AccessibilityDialog@@AEAAHH@Z; AccessibilityDialog::LogicalToPhysicalSize(int)
0x14001f9da  cdq
0x14001f9db  mov     rcx, rbp; this
0x14001f9de  sub     eax, edx
0x14001f9e0  mov     edx, 166h; int
0x14001f9e5  sar     eax, 1
0x14001f9e7  sub     eax, ebx
0x14001f9e9  mov     ebx, [rdi]
0x14001f9eb  add     [rsi], eax
0x14001f9ed  call    ?LogicalToPhysicalSize@AccessibilityDialog@@AEAAHH@Z; AccessibilityDialog::LogicalToPhysicalSize(int)
0x14001f9f2  sub     ebx, eax
0x14001f9f4  mov     [rdi], ebx
0x14001f9f6  mov     ebx, [rsi]
0x14001f9f8  test    ebx, ebx
0x14001f9fa  jns     short loc_14001FA0D
0x14001f9fc  mov     edx, 0Ch; int
0x14001fa01  mov     rcx, rbp; this
0x14001fa04  call    ?LogicalToPhysicalSize@AccessibilityDialog@@AEAAHH@Z; AccessibilityDialog::LogicalToPhysicalSize(int)
0x14001fa09  mov     ebx, eax
0x14001fa0b  mov     [rsi], eax
0x14001fa0d  mov     edx, 172h; int
0x14001fa12  mov     rcx, rbp; this
0x14001fa15  call    ?LogicalToPhysicalSize@AccessibilityDialog@@AEAAHH@Z; AccessibilityDialog::LogicalToPhysicalSize(int)
0x14001fa1a  add     eax, ebx
0x14001fa1c  cmp     eax, r14d
0x14001fa1f  jle     short loc_14001FA34
0x14001fa21  mov     edx, 172h; int
0x14001fa26  mov     rcx, rbp; this
0x14001fa29  call    ?LogicalToPhysicalSize@AccessibilityDialog@@AEAAHH@Z; AccessibilityDialog::LogicalToPhysicalSize(int)
0x14001fa2e  sub     r14d, eax
0x14001fa31  mov     [rsi], r14d
0x14001fa34  mov     ebx, [rdi]
0x14001fa36  test    ebx, ebx
0x14001fa38  jns     short loc_14001FA4B
0x14001fa3a  mov     edx, 0Ch; int
0x14001fa3f  mov     rcx, rbp; this
0x14001fa42  call    ?LogicalToPhysicalSize@AccessibilityDialog@@AEAAHH@Z; AccessibilityDialog::LogicalToPhysicalSize(int)
0x14001fa47  mov     ebx, eax
0x14001fa49  mov     [rdi], eax
0x14001fa4b  mov     edx, 166h; int
0x14001fa50  mov     rcx, rbp; this
0x14001fa53  call    ?LogicalToPhysicalSize@AccessibilityDialog@@AEAAHH@Z; AccessibilityDialog::LogicalToPhysicalSize(int)
0x14001fa58  add     eax, ebx
0x14001fa5a  cmp     eax, r15d
0x14001fa5d  jle     short loc_14001FAC0
0x14001fa5f  mov     edx, 166h; int
0x14001fa64  mov     rcx, rbp; this
0x14001fa67  call    ?LogicalToPhysicalSize@AccessibilityDialog@@AEAAHH@Z; AccessibilityDialog::LogicalToPhysicalSize(int)
0x14001fa6c  sub     r15d, eax
0x14001fa6f  mov     [rdi], r15d
0x14001fa72  jmp     short loc_14001FAC0
0x14001fa74  mov     edx, 1A0h; int
0x14001fa79  mov     rcx, rbp; this
0x14001fa7c  call    ?LogicalToPhysicalSize@AccessibilityDialog@@AEAAHH@Z; AccessibilityDialog::LogicalToPhysicalSize(int)
0x14001fa81  sub     r15d, eax
0x14001fa84  mov     [rdi], r15d
0x14001fa87  mov     dl, 1
0x14001fa89  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AFGU@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AFGU@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AFGU> `wil::Feature<__WilFeatureTraits_Feature_AFGU>::GetImpl(void)'::`2'::impl
0x14001fa90  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AFGU@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AFGU>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14001fa95  call    _anonymous_namespace___IsRightToLeft
0x14001fa9a  mov     rcx, rbp; this
0x14001fa9d  test    al, al
0x14001fa9f  jz      short loc_14001FAB0
0x14001faa1  mov     edx, 0Ch; int
0x14001faa6  call    ?LogicalToPhysicalSize@AccessibilityDialog@@AEAAHH@Z; AccessibilityDialog::LogicalToPhysicalSize(int)
0x14001faab  mov     r14d, eax
0x14001faae  jmp     short loc_14001FABD
0x14001fab0  mov     edx, 172h; int
0x14001fab5  call    ?LogicalToPhysicalSize@AccessibilityDialog@@AEAAHH@Z; AccessibilityDialog::LogicalToPhysicalSize(int)
0x14001faba  sub     r14d, eax
0x14001fabd  mov     [rsi], r14d
0x14001fac0  mov     eax, [rsi]
0x14001fac2  mov     [rsi+8], eax
0x14001fac5  mov     eax, [rdi]
0x14001fac7  mov     [rsi+0Ch], eax
0x14001faca  mov     rax, rsi
0x14001facd  add     rsp, 38h
0x14001fad1  pop     r15
0x14001fad3  pop     r14
0x14001fad5  pop     rdi
0x14001fad6  pop     rsi
0x14001fad7  pop     rbp
0x14001fad8  pop     rbx
0x14001fad9  retn
```
