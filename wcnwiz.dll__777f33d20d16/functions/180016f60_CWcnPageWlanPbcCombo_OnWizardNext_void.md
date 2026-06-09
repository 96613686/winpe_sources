# CWcnPageWlanPbcCombo::OnWizardNext(void)

- ea: `0x180016f60`
- end: `0x180017102`
- name: `?OnWizardNext@CWcnPageWlanPbcCombo@@UEAA_JXZ`
- size: `418`
- prototype: `__int64 __fastcall(CWcnPageWlanPbcCombo *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180001820`
- `0x18000ce94`
- `0x18000d630`
- `0x180013744`
- `0x180016f60`
- `0x1800172f8`
- `0x180017840`
- `0x18002de1c`

## import_xrefs

- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180017043`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180017043`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180017034`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180017034`

## pseudocode

```c
__int64 __fastcall CWcnPageWlanPbcCombo::OnWizardNext(CWcnPageWlanPbcCombo *this, __int64 a2, __int64 a3, __int64 a4)
{
  const char *Indent; // rax
  __int64 v6; // r10
  const char *v7; // rax
  __int64 v8; // r10
  DirectUI::Element *v9; // rcx
  __int64 v10; // rbx
  const char *v11; // rax
  __int64 v12; // r10
  _BYTE v14[16]; // [rsp+30h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 15, WPP_5d28c7bb4c503e99a1827b75a81abd2f_Traceguids, Indent);
  }
  if ( *((_BYTE *)this + 510) && !*((_BYTE *)this + 509)
    || *((_BYTE *)this + 507)
    || CWcnPageWlanPbcCombo::_ReadPassword(this) && CWcnPageWlanPbcCombo::_ValidateKeyAndPromptError(this) )
  {
    if ( (Microsoft_Windows_WCNWizEnableBits & 1) != 0 )
      McGenEventWrite_EtwEventWriteTransfer((__int64)this, (__int64)AcceptUserKeyInput, a3, a4, (__int64)v14);
    CXWizardClassRoot::SetProperty(
      (CWcnPageWlanPbcCombo *)((char *)this + 64),
      (const struct _GUID *)((char *)this + 104),
      L"_WlanDlg_WLAN_Pre_Connect_Input",
      *((void *const *)this + 68),
      2u);
    CXWizardClassRoot::SetProperty(
      (CWcnPageWlanPbcCombo *)((char *)this + 64),
      (const struct _GUID *)((char *)this + 104),
      L"WlanCfe.ForceSNL",
      (void *const)1,
      2u);
    v10 = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v7 = GetIndent(0);
      WPP_SF_s(*(_QWORD *)(v8 + 16), 16, WPP_5d28c7bb4c503e99a1827b75a81abd2f_Traceguids, v7);
    }
    v9 = (DirectUI::Element *)*((_QWORD *)this + 76);
    *((_BYTE *)this + 616) = 0;
    DirectUI::Element::SetLayoutPos(v9, -3);
    DirectUI::Element::SetVisible(*((DirectUI::Element **)this + 76), 0);
    v10 = -1;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v11 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v12 + 16), 17, WPP_5d28c7bb4c503e99a1827b75a81abd2f_Traceguids, v11);
  }
  return v10;
}

```

## disassembly

```asm
0x180016f60  push    rbx
0x180016f62  push    rsi
0x180016f63  push    rdi
0x180016f64  push    r15
0x180016f66  sub     rsp, 58h
0x180016f6a  mov     rax, cs:__security_cookie
0x180016f71  xor     rax, rsp
0x180016f74  mov     [rsp+78h+var_38], rax
0x180016f79  mov     rsi, rcx
0x180016f7c  mov     r10, cs:WPP_GLOBAL_Control
0x180016f83  lea     r15, WPP_GLOBAL_Control
0x180016f8a  cmp     r10, r15
0x180016f8d  jz      short loc_180016FB8
0x180016f8f  cmp     byte ptr [r10+19h], 6
0x180016f94  jb      short loc_180016FB8
0x180016f96  mov     ecx, 1; int
0x180016f9b  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180016fa0  mov     rcx, [r10+10h]
0x180016fa4  lea     r8, WPP_5d28c7bb4c503e99a1827b75a81abd2f_Traceguids
0x180016fab  mov     edx, 0Fh
0x180016fb0  mov     r9, rax
0x180016fb3  call    WPP_SF_s
0x180016fb8  cmp     byte ptr [rsi+1FEh], 0
0x180016fbf  jz      short loc_180016FCE
0x180016fc1  cmp     byte ptr [rsi+1FDh], 0
0x180016fc8  jz      loc_18001704F
0x180016fce  cmp     byte ptr [rsi+1FBh], 0
0x180016fd5  jnz     short loc_18001704F
0x180016fd7  mov     rcx, rsi; this
0x180016fda  call    ?_ReadPassword@CWcnPageWlanPbcCombo@@AEAA_NXZ; CWcnPageWlanPbcCombo::_ReadPassword(void)
0x180016fdf  test    al, al
0x180016fe1  jz      short loc_180016FEF
0x180016fe3  mov     rcx, rsi; this
0x180016fe6  call    ?_ValidateKeyAndPromptError@CWcnPageWlanPbcCombo@@AEAA_NXZ; CWcnPageWlanPbcCombo::_ValidateKeyAndPromptError(void)
0x180016feb  test    al, al
0x180016fed  jnz     short loc_18001704F
0x180016fef  mov     r10, cs:WPP_GLOBAL_Control
0x180016ff6  cmp     r10, r15
0x180016ff9  jz      short loc_180017021
0x180016ffb  cmp     byte ptr [r10+19h], 4
0x180017000  jb      short loc_180017021
0x180017002  xor     ecx, ecx; int
0x180017004  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180017009  mov     rcx, [r10+10h]
0x18001700d  lea     r8, WPP_5d28c7bb4c503e99a1827b75a81abd2f_Traceguids
0x180017014  mov     edx, 10h
0x180017019  mov     r9, rax
0x18001701c  call    WPP_SF_s
0x180017021  mov     rcx, [rsi+260h]
0x180017028  mov     edx, 0FFFFFFFDh
0x18001702d  mov     byte ptr [rsi+268h], 0
0x180017034  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18001703a  mov     rcx, [rsi+260h]
0x180017041  xor     edx, edx
0x180017043  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x180017049  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001704d  jmp     short loc_1800170B5
0x18001704f  test    cs:Microsoft_Windows_WCNWizEnableBits, 1
0x180017056  jz      short loc_18001706E
0x180017058  lea     rax, [rsp+78h+var_48]
0x18001705d  lea     rdx, AcceptUserKeyInput
0x180017064  mov     qword ptr [rsp+78h+var_58], rax
0x180017069  call    McGenEventWrite_EtwEventWriteTransfer
0x18001706e  mov     r9, [rsi+220h]; void *
0x180017075  lea     r8, aWlandlgWlanPre; "_WlanDlg_WLAN_Pre_Connect_Input"
0x18001707c  lea     rdx, [rsi+68h]; struct _GUID *
0x180017080  mov     [rsp+78h+var_58], 2; unsigned int
0x180017088  lea     rcx, [rsi+40h]; this
0x18001708c  call    ?SetProperty@CXWizardClassRoot@@QEAAJPEBU_GUID@@QEAGQEAXK@Z; CXWizardClassRoot::SetProperty(_GUID const *,ushort * const,void * const,ulong)
0x180017091  mov     r9d, 1; void *
0x180017097  mov     [rsp+78h+var_58], 2; unsigned int
0x18001709f  lea     r8, aWlancfeForcesn; "WlanCfe.ForceSNL"
0x1800170a6  lea     rdx, [rsi+68h]; struct _GUID *
0x1800170aa  lea     rcx, [rsi+40h]; this
0x1800170ae  call    ?SetProperty@CXWizardClassRoot@@QEAAJPEBU_GUID@@QEAGQEAXK@Z; CXWizardClassRoot::SetProperty(_GUID const *,ushort * const,void * const,ulong)
0x1800170b3  xor     ebx, ebx
0x1800170b5  mov     r10, cs:WPP_GLOBAL_Control
0x1800170bc  cmp     r10, r15
0x1800170bf  jz      short loc_1800170E8
0x1800170c1  cmp     byte ptr [r10+19h], 6
0x1800170c6  jb      short loc_1800170E8
0x1800170c8  or      ecx, 0FFFFFFFFh; int
0x1800170cb  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800170d0  mov     rcx, [r10+10h]
0x1800170d4  lea     r8, WPP_5d28c7bb4c503e99a1827b75a81abd2f_Traceguids
0x1800170db  mov     edx, 11h
0x1800170e0  mov     r9, rax
0x1800170e3  call    WPP_SF_s
0x1800170e8  mov     rax, rbx
0x1800170eb  mov     rcx, [rsp+78h+var_38]
0x1800170f0  xor     rcx, rsp; StackCookie
0x1800170f3  call    __security_check_cookie
0x1800170f8  add     rsp, 58h
0x1800170fc  pop     r15
0x1800170fe  pop     rdi
0x1800170ff  pop     rsi
0x180017100  pop     rbx
0x180017101  retn
```
