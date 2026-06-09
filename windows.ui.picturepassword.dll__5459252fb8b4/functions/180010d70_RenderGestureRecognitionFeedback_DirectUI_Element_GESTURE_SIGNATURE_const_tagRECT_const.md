# RenderGestureRecognitionFeedback(DirectUI::Element *,GESTURE_SIGNATURE const &,tagRECT const &)

- ea: `0x180010d70`
- end: `0x180010f97`
- name: `?RenderGestureRecognitionFeedback@@YAJPEAVElement@DirectUI@@AEBUGESTURE_SIGNATURE@@AEBUtagRECT@@@Z`
- size: `551`
- prototype: `__int64 __fastcall(struct DirectUI::Element *, const struct GESTURE_SIGNATURE *, const struct tagRECT *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000f670`
- `0x1800149e4`

## callees

- `0x180010d70`
- `0x180012338`
- `0x1800123dc`
- `0x180012a94`
- `0x180015308`

## import_xrefs

- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180010f65`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180010f65`
- `DUI70!?SetX@Element@DirectUI@@QEAAJH@Z` at `0x180010f3c`
- `DUI70!?SetX@Element@DirectUI@@QEAAJH@Z` at `0x180010f3c`
- `DUI70!?SetY@Element@DirectUI@@QEAAJH@Z` at `0x180010f4c`
- `DUI70!?SetY@Element@DirectUI@@QEAAJH@Z` at `0x180010f4c`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180010f2a`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180010f2a`
- `DUI70!?SetAlpha@Element@DirectUI@@QEAAJH@Z` at `0x180010f5a`
- `DUI70!?SetAlpha@Element@DirectUI@@QEAAJH@Z` at `0x180010f5a`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x180010db8`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x180010db8`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x180010da8`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x180010da8`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x180010f76`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x180010f76`
- `DUI70!?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180010d90`
- `DUI70!?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180010d90`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180010dae`

## pseudocode

```c
__int64 __fastcall RenderGestureRecognitionFeedback(
        struct DirectUI::Element *a1,
        const struct GESTURE_SIGNATURE *a2,
        const struct tagRECT *a3)
{
  int v6; // ecx
  int v7; // ecx
  int v8; // r15d
  LONG v9; // eax
  int v10; // eax
  LONG v11; // r8d
  LONG x; // esi
  LONG v13; // edx
  LONG y; // r13d
  LONG left; // r14d
  LONG right; // ebx
  LONG v17; // esi
  LONG top; // esi
  LONG bottom; // edi
  int v20; // r13d
  LONG v21; // ebx
  LONG v22; // edi
  struct tagPOINT v24; // [rsp+20h] [rbp-20h] BYREF
  struct tagPOINT v25; // [rsp+28h] [rbp-18h] BYREF
  DirectUI::Element *Root; // [rsp+30h] [rbp-10h]
  unsigned int v27; // [rsp+38h] [rbp-8h] BYREF
  struct tagSIZE v28; // [rsp+88h] [rbp+48h] BYREF
  struct tagPOINT v29; // [rsp+98h] [rbp+58h] BYREF

  Root = DirectUI::Element::GetRoot(a1);
  v27 = 0;
  DirectUI::Element::StartDefer(Root, &v27);
  DirectUI::Element::RemoveLocalValue(
    a1,
    (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp);
  v6 = *(_DWORD *)a2;
  v28 = 0;
  v29 = 0;
  if ( !v6 )
  {
    v10 = _RenderPointFeedback(a1, &v28);
LABEL_13:
    v8 = v10;
    if ( v10 < 0 )
      goto LABEL_24;
    CPicturePasswordGestureHelper::s_PercentagePointToImagePoint((const struct tagPOINT *)((char *)a2 + 4), a3, &v29);
    x = v29.x;
    y = v29.y;
    goto LABEL_15;
  }
  v7 = v6 - 1;
  if ( v7 )
  {
    if ( v7 != 1 )
    {
      v8 = -2147418113;
      goto LABEL_24;
    }
    v9 = 2 * *((_DWORD *)a2 + 3);
    v25 = 0;
    v24.x = v9;
    v24.y = v9;
    CPicturePasswordGestureHelper::s_PercentagePointToImagePoint(&v24, a3, &v25);
    v10 = _RenderCircleFeedback(a1, (unsigned int)(v25.x - a3->left) >> 1, *((_BYTE *)a2 + 16), &v28);
    goto LABEL_13;
  }
  v24 = 0;
  CPicturePasswordGestureHelper::s_PercentagePointToImagePoint((const struct tagPOINT *)((char *)a2 + 4), a3, &v24);
  v29 = 0;
  CPicturePasswordGestureHelper::s_PercentagePointToImagePoint((const struct tagPOINT *)((char *)a2 + 12), a3, &v29);
  v11 = v29.x;
  x = (v29.x + v24.x) / 2;
  v13 = v29.y;
  y = (v29.y + v24.y) / 2;
  if ( v24.x - v29.x < 0 )
    v11 = v24.x;
  if ( v24.y - v29.y < 0 )
    v13 = v24.y;
  v24.x -= v11;
  v24.y -= v13;
  v29.x -= v11;
  v29.y -= v13;
  v8 = _RenderLineFeedback(a1, &v24, &v29, &v28);
  if ( v8 >= 0 )
  {
LABEL_15:
    left = a3->left;
    right = a3->right;
    v17 = x - v28.cx / 2;
    if ( v17 > a3->left )
      left = v17;
    top = a3->top;
    bottom = a3->bottom;
    v20 = y - v28.cy / 2;
    if ( v20 > top )
      top = v20;
    v21 = right - v28.cx;
    v22 = bottom - v28.cy;
    DirectUI::Element::SetLayoutPos(a1, -2);
    if ( v21 - left >= 0 )
      v21 = left;
    DirectUI::Element::SetX(a1, v21);
    if ( v22 - top >= 0 )
      v22 = top;
    DirectUI::Element::SetY(a1, v22);
    DirectUI::Element::SetAlpha(a1, 255);
    DirectUI::Element::SetVisible(a1, 1);
  }
LABEL_24:
  if ( v27 )
    DirectUI::Element::EndDefer(Root, v27);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180010d70  mov     [rsp-38h+arg_0], rbx
0x180010d75  push    rbp
0x180010d76  push    rsi
0x180010d77  push    rdi
0x180010d78  push    r12
0x180010d7a  push    r13
0x180010d7c  push    r14
0x180010d7e  push    r15
0x180010d80  mov     rbp, rsp
0x180010d83  sub     rsp, 40h
0x180010d87  mov     rdi, r8
0x180010d8a  mov     rbx, rdx
0x180010d8d  mov     r12, rcx
0x180010d90  call    cs:__imp_?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetRoot(void)
0x180010d96  xor     r14d, r14d
0x180010d99  lea     rdx, [rbp+var_8]
0x180010d9d  mov     rcx, rax
0x180010da0  mov     [rbp+var_10], rax
0x180010da4  mov     [rbp+var_8], r14d
0x180010da8  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x180010dae  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x180010db5  mov     rcx, r12
0x180010db8  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x180010dbe  mov     ecx, [rbx]
0x180010dc0  lea     r15d, [r14+2]
0x180010dc4  mov     qword ptr [rbp+arg_8.cx], r14
0x180010dc8  mov     qword ptr [rbp+arg_18.x], r14
0x180010dcc  test    ecx, ecx
0x180010dce  jz      loc_180010EC0
0x180010dd4  sub     ecx, 1
0x180010dd7  jz      short loc_180010E24
0x180010dd9  cmp     ecx, 1
0x180010ddc  jz      short loc_180010DE9
0x180010dde  mov     r15d, 8000FFFFh
0x180010de4  jmp     loc_180010F6B
0x180010de9  mov     eax, [rbx+0Ch]
0x180010dec  lea     r8, [rbp+var_18]; struct tagPOINT *
0x180010df0  add     eax, eax
0x180010df2  mov     qword ptr [rbp+var_18.x], r14
0x180010df6  mov     rdx, rdi; struct tagRECT *
0x180010df9  mov     [rbp+var_20.x], eax
0x180010dfc  lea     rcx, [rbp+var_20]; struct tagPOINT *
0x180010e00  mov     [rbp+var_20.y], eax
0x180010e03  call    ?s_PercentagePointToImagePoint@CPicturePasswordGestureHelper@@SAXAEBUtagPOINT@@AEBUtagRECT@@PEAU2@@Z; CPicturePasswordGestureHelper::s_PercentagePointToImagePoint(tagPOINT const &,tagRECT const &,tagPOINT *)
0x180010e08  mov     edx, [rbp+var_18.x]
0x180010e0b  lea     r9, [rbp+arg_8]; struct tagSIZE *
0x180010e0f  sub     edx, [rdi]
0x180010e11  mov     rcx, r12; struct DirectUI::Element *
0x180010e14  mov     r8b, [rbx+10h]; bool
0x180010e18  shr     edx, 1; unsigned int
0x180010e1a  call    ?_RenderCircleFeedback@@YAJPEAVElement@DirectUI@@I_NPEAUtagSIZE@@@Z; _RenderCircleFeedback(DirectUI::Element *,uint,bool,tagSIZE *)
0x180010e1f  jmp     loc_180010ECC
0x180010e24  lea     rcx, [rbx+4]; struct tagPOINT *
0x180010e28  mov     qword ptr [rbp+var_20.x], r14
0x180010e2c  lea     r8, [rbp+var_20]; struct tagPOINT *
0x180010e30  mov     rdx, rdi; struct tagRECT *
0x180010e33  call    ?s_PercentagePointToImagePoint@CPicturePasswordGestureHelper@@SAXAEBUtagPOINT@@AEBUtagRECT@@PEAU2@@Z; CPicturePasswordGestureHelper::s_PercentagePointToImagePoint(tagPOINT const &,tagRECT const &,tagPOINT *)
0x180010e38  lea     rcx, [rbx+0Ch]; struct tagPOINT *
0x180010e3c  mov     qword ptr [rbp+arg_18.x], r14
0x180010e40  lea     r8, [rbp+arg_18]; struct tagPOINT *
0x180010e44  mov     rdx, rdi; struct tagRECT *
0x180010e47  call    ?s_PercentagePointToImagePoint@CPicturePasswordGestureHelper@@SAXAEBUtagPOINT@@AEBUtagRECT@@PEAU2@@Z; CPicturePasswordGestureHelper::s_PercentagePointToImagePoint(tagPOINT const &,tagRECT const &,tagPOINT *)
0x180010e4c  mov     r10d, [rbp+var_20.x]
0x180010e50  mov     rcx, r12; struct DirectUI::Element *
0x180010e53  mov     ebx, [rbp+arg_18.x]
0x180010e56  mov     r8d, ebx
0x180010e59  mov     r9d, [rbp+var_20.y]
0x180010e5d  mov     r11d, [rbp+arg_18.y]
0x180010e61  lea     eax, [rbx+r10]
0x180010e65  cdq
0x180010e66  idiv    r15d
0x180010e69  mov     esi, eax
0x180010e6b  lea     eax, [r11+r9]
0x180010e6f  cdq
0x180010e70  idiv    r15d
0x180010e73  cmp     r10d, ebx
0x180010e76  mov     edx, r11d
0x180010e79  mov     r13d, eax
0x180010e7c  cmovs   r8d, r10d
0x180010e80  cmp     r9d, r11d
0x180010e83  cmovs   edx, r9d
0x180010e87  sub     r10d, r8d
0x180010e8a  sub     r9d, edx
0x180010e8d  mov     [rbp+var_20.x], r10d
0x180010e91  sub     ebx, r8d
0x180010e94  mov     [rbp+var_20.y], r9d
0x180010e98  sub     r11d, edx
0x180010e9b  mov     [rbp+arg_18.x], ebx
0x180010e9e  lea     r9, [rbp+arg_8]; struct tagSIZE *
0x180010ea2  mov     [rbp+arg_18.y], r11d
0x180010ea6  lea     r8, [rbp+arg_18]; struct tagPOINT *
0x180010eaa  lea     rdx, [rbp+var_20]; struct tagPOINT *
0x180010eae  call    ?_RenderLineFeedback@@YAJPEAVElement@DirectUI@@AEBUtagPOINT@@1PEAUtagSIZE@@@Z; _RenderLineFeedback(DirectUI::Element *,tagPOINT const &,tagPOINT const &,tagSIZE *)
0x180010eb3  mov     r15d, eax
0x180010eb6  test    eax, eax
0x180010eb8  js      loc_180010F6B
0x180010ebe  jmp     short loc_180010EEE
0x180010ec0  lea     rdx, [rbp+arg_8]; struct tagSIZE *
0x180010ec4  mov     rcx, r12; struct DirectUI::Element *
0x180010ec7  call    ?_RenderPointFeedback@@YAJPEAVElement@DirectUI@@PEAUtagSIZE@@@Z; _RenderPointFeedback(DirectUI::Element *,tagSIZE *)
0x180010ecc  mov     r15d, eax
0x180010ecf  test    eax, eax
0x180010ed1  js      loc_180010F6B
0x180010ed7  lea     r8, [rbp+arg_18]; struct tagPOINT *
0x180010edb  mov     rdx, rdi; struct tagRECT *
0x180010ede  lea     rcx, [rbx+4]; struct tagPOINT *
0x180010ee2  call    ?s_PercentagePointToImagePoint@CPicturePasswordGestureHelper@@SAXAEBUtagPOINT@@AEBUtagRECT@@PEAU2@@Z; CPicturePasswordGestureHelper::s_PercentagePointToImagePoint(tagPOINT const &,tagRECT const &,tagPOINT *)
0x180010ee7  mov     esi, [rbp+arg_18.x]
0x180010eea  mov     r13d, [rbp+arg_18.y]
0x180010eee  mov     r14d, [rdi]
0x180010ef1  mov     ecx, 2
0x180010ef6  mov     eax, [rbp+arg_8.cx]
0x180010ef9  mov     ebx, [rdi+8]
0x180010efc  cdq
0x180010efd  idiv    ecx
0x180010eff  sub     esi, eax
0x180010f01  mov     eax, [rbp+arg_8.cy]
0x180010f04  cmp     esi, r14d
0x180010f07  cdq
0x180010f08  cmovg   r14d, esi
0x180010f0c  mov     esi, [rdi+4]
0x180010f0f  mov     edi, [rdi+0Ch]
0x180010f12  idiv    ecx
0x180010f14  lea     edx, [rcx-4]
0x180010f17  mov     rcx, r12
0x180010f1a  sub     r13d, eax
0x180010f1d  cmp     r13d, esi
0x180010f20  cmovg   esi, r13d
0x180010f24  sub     ebx, [rbp+arg_8.cx]
0x180010f27  sub     edi, [rbp+arg_8.cy]
0x180010f2a  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180010f30  cmp     ebx, r14d
0x180010f33  mov     rcx, r12
0x180010f36  cmovns  ebx, r14d
0x180010f3a  mov     edx, ebx
0x180010f3c  call    cs:__imp_?SetX@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetX(int)
0x180010f42  cmp     edi, esi
0x180010f44  mov     rcx, r12
0x180010f47  cmovns  edi, esi
0x180010f4a  mov     edx, edi
0x180010f4c  call    cs:__imp_?SetY@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetY(int)
0x180010f52  mov     edx, 0FFh
0x180010f57  mov     rcx, r12
0x180010f5a  call    cs:__imp_?SetAlpha@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetAlpha(int)
0x180010f60  mov     dl, 1
0x180010f62  mov     rcx, r12
0x180010f65  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x180010f6b  mov     edx, [rbp+var_8]
0x180010f6e  test    edx, edx
0x180010f70  jz      short loc_180010F7C
0x180010f72  mov     rcx, [rbp+var_10]
0x180010f76  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x180010f7c  mov     rbx, [rsp+40h+arg_0]
0x180010f84  mov     eax, r15d
0x180010f87  add     rsp, 40h
0x180010f8b  pop     r15
0x180010f8d  pop     r14
0x180010f8f  pop     r13
0x180010f91  pop     r12
0x180010f93  pop     rdi
0x180010f94  pop     rsi
0x180010f95  pop     rbp
0x180010f96  retn
```
