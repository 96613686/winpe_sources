# CConsentUI::ShowConsentDlg(void)

- ea: `0x18000a42c`
- end: `0x18000a636`
- name: `?ShowConsentDlg@CConsentUI@@QEAAKXZ`
- size: `522`
- prototype: `unsigned int __fastcall(CConsentUI *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a14c`
- `0x18000a238`

## callees

- `0x180003604`
- `0x18000a42c`
- `0x18000c268`
- `0x18000c8d8`
- `0x180016c1e`

## import_xrefs

- `COMCTL32!TaskDialogIndirect` at `0x18000a5be`
- `COMCTL32!TaskDialogIndirect` at `0x18000a5be`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x18000a56d`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x18000a56d`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000a5aa`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000a5e4`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000a5aa`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000a5e4`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000a590`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000a5ca`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000a590`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000a5ca`

## pseudocode

```c
__int64 __fastcall CConsentUI::ShowConsentDlg(CConsentUI *this)
{
  HRESULT v2; // edi
  unsigned int v3; // esi
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rax
  HICON IconW; // rax
  bool v8; // zf
  _QWORD v10[4]; // [rsp+20h] [rbp-79h] BYREF
  TASKDIALOGCONFIG pTaskConfig; // [rsp+40h] [rbp-59h] BYREF
  int pnButton; // [rsp+108h] [rbp+6Fh] BYREF
  struct IUnknown *v13; // [rsp+110h] [rbp+77h] BYREF

  memset_0(&pTaskConfig, 0, sizeof(pTaskConfig));
  pnButton = 0;
  v13 = 0;
  memset(v10, 0, 24);
  v2 = CUIDlgBase::InitializeDUI(
         this,
         (int (*)(unsigned int, unsigned __int64, __int64, __int64 *, void *))CConsentUI::Static_NotifyHandler,
         this,
         &v13);
  v3 = 2;
  if ( v2 >= 0 )
  {
    *(_QWORD *)((char *)v10 + 4) = *((_QWORD *)this + 31);
    v10[2] = *((_QWORD *)this + 35);
    pTaskConfig.hwndParent = (HWND)*((_QWORD *)this + 13);
    pTaskConfig.pszMainInstruction = (PCWSTR)*((_QWORD *)this + 23);
    pTaskConfig.pszContent = (PCWSTR)*((_QWORD *)this + 27);
    v6 = *((_QWORD *)this + 2);
    LODWORD(v10[0]) = 1;
    pTaskConfig.pszWindowTitle = (PCWSTR)(v6 + 400);
    pTaskConfig.pButtons = (const TASKDIALOG_BUTTON *)v10;
    pTaskConfig.pfCallback = (PFTASKDIALOGCALLBACK)CConsentUI::Static_ConsentDlgProc;
    HIDWORD(v10[1]) = 2;
    pTaskConfig.cbSize = 160;
    pTaskConfig.hInstance = &_ImageBase;
    pTaskConfig.cButtons = 2;
    pTaskConfig.dwFlags = 10;
    pTaskConfig.lpCallbackData = (LONG_PTR)this;
    pTaskConfig.cxWidth = 0;
    pTaskConfig.nDefaultButton = 2;
    pTaskConfig.pszExpandedControlText = (PCWSTR)3019;
    pTaskConfig.pszCollapsedControlText = (PCWSTR)3018;
    IconW = LoadIconW(&_ImageBase, (LPCWSTR)0x194);
    v8 = *((_DWORD *)this + 30) == 1;
    pTaskConfig.hMainIcon = IconW;
    if ( v8 )
    {
      pTaskConfig.dwFlags |= 0x200040u;
      pTaskConfig.pszExpandedInformation = (PCWSTR)v13;
    }
    if ( IsWindow(*((HWND *)this + 13)) )
      SendMessageW(*((HWND *)this + 13), 0x468u, 3u, 0);
    v2 = TaskDialogIndirect(&pTaskConfig, &pnButton, 0, 0);
    if ( IsWindow(*((HWND *)this + 13)) )
      SendMessageW(*((HWND *)this + 13), 0x468u, 1u, 0);
    if ( v2 >= 0 )
    {
      v2 = 0;
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 13;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 12;
LABEL_5:
      WPP_SF_d(v4[2], v5, WPP_fea2387d138a3e728ec0a3daac89d932_Traceguids, (unsigned int)v2);
    }
  }
  CUIDlgBase::UnInitializeDUI(this);
  if ( v2 >= 0 )
    return (unsigned int)pnButton;
  return v3;
}

```

## disassembly

```asm
0x18000a42c  mov     [rsp-8+arg_0], rbx
0x18000a431  push    rbp
0x18000a432  push    rsi
0x18000a433  push    rdi
0x18000a434  lea     rbp, [rsp-47h]
0x18000a439  sub     rsp, 0E0h
0x18000a440  mov     rbx, rcx
0x18000a443  xor     edx, edx; Val
0x18000a445  lea     rcx, [rbp+57h+pTaskConfig]; void *
0x18000a449  mov     r8d, 0A0h; Size
0x18000a44f  call    memset_0
0x18000a454  xor     eax, eax
0x18000a456  mov     [rbp+57h+pnButton], 0
0x18000a45d  xorps   xmm0, xmm0
0x18000a460  mov     [rbp+57h+var_BC], eax
0x18000a463  lea     r9, [rbp+57h+arg_10]; struct IUnknown **
0x18000a467  mov     [rbp+57h+arg_10], rax
0x18000a46b  mov     r8, rbx; void *
0x18000a46e  mov     [rbp+57h+var_D0], 0
0x18000a475  lea     rdx, ?Static_NotifyHandler@CConsentUI@@CAHI_K_JPEA_JPEAX@Z; int (*)(unsigned int, unsigned __int64, __int64, __int64 *, void *)
0x18000a47c  mov     rcx, rbx; this
0x18000a47f  movups  [rbp+57h+var_CC], xmm0
0x18000a483  call    ?InitializeDUI@CUIDlgBase@@IEAAJP6AHI_K_JPEA_JPEAX@Z3PEAPEAUIUnknown@@@Z; CUIDlgBase::InitializeDUI(int (*)(uint,unsigned __int64,__int64,__int64 *,void *),void *,IUnknown * *)
0x18000a488  mov     edi, eax
0x18000a48a  mov     esi, 2
0x18000a48f  test    eax, eax
0x18000a491  jns     short loc_18000A4CF
0x18000a493  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a49a  lea     rax, WPP_GLOBAL_Control
0x18000a4a1  cmp     rcx, rax
0x18000a4a4  jz      loc_18000A613
0x18000a4aa  test    byte ptr [rcx+1Ch], 1
0x18000a4ae  jz      loc_18000A613
0x18000a4b4  lea     edx, [rsi+0Ah]
0x18000a4b7  mov     rcx, [rcx+10h]
0x18000a4bb  lea     r8, WPP_fea2387d138a3e728ec0a3daac89d932_Traceguids
0x18000a4c2  mov     r9d, edi
0x18000a4c5  call    WPP_SF_d
0x18000a4ca  jmp     loc_18000A613
0x18000a4cf  mov     rax, [rbx+0F8h]
0x18000a4d6  lea     rcx, __ImageBase; hInstance
0x18000a4dd  mov     qword ptr [rbp+57h+var_CC], rax
0x18000a4e1  mov     edx, 194h; lpIconName
0x18000a4e6  mov     rax, [rbx+118h]
0x18000a4ed  mov     qword ptr [rbp+57h+var_CC+0Ch], rax
0x18000a4f1  mov     rax, [rbx+68h]
0x18000a4f5  mov     [rbp+57h+pTaskConfig.hwndParent], rax
0x18000a4f9  mov     rax, [rbx+0B8h]
0x18000a500  mov     [rbp+57h+pTaskConfig.pszMainInstruction], rax
0x18000a504  mov     rax, [rbx+0D8h]
0x18000a50b  mov     [rbp+57h+pTaskConfig.pszContent], rax
0x18000a50f  mov     rax, [rbx+10h]
0x18000a513  add     rax, 190h
0x18000a519  mov     [rbp+57h+var_D0], 1
0x18000a520  mov     [rbp+57h+pTaskConfig.pszWindowTitle], rax
0x18000a524  lea     rax, [rbp+57h+var_D0]
0x18000a528  mov     [rbp+57h+pTaskConfig.pButtons], rax
0x18000a52c  lea     rax, ?Static_ConsentDlgProc@CConsentUI@@CAJPEAUHWND__@@I_K_J2@Z; CConsentUI::Static_ConsentDlgProc(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x18000a533  mov     [rbp+57h+pTaskConfig.pfCallback], rax
0x18000a537  mov     dword ptr [rbp+57h+var_CC+8], esi
0x18000a53a  mov     [rbp+57h+pTaskConfig.cbSize], 0A0h
0x18000a541  mov     [rbp+57h+pTaskConfig.hInstance], rcx
0x18000a545  mov     [rbp+57h+pTaskConfig.cButtons], esi
0x18000a548  mov     [rbp+57h+pTaskConfig.dwFlags], 0Ah
0x18000a54f  mov     [rbp+57h+pTaskConfig.lpCallbackData], rbx
0x18000a553  mov     [rbp+57h+pTaskConfig.cxWidth], 0
0x18000a55a  mov     [rbp+57h+pTaskConfig.nDefaultButton], esi
0x18000a55d  mov     [rbp+57h+pTaskConfig.pszExpandedControlText], 0BCBh
0x18000a565  mov     [rbp+57h+pTaskConfig.pszCollapsedControlText], 0BCAh
0x18000a56d  call    cs:__imp_LoadIconW
0x18000a573  cmp     dword ptr [rbx+78h], 1
0x18000a577  mov     qword ptr [rbp+57h+pTaskConfig.24h], rax
0x18000a57b  jnz     short loc_18000A58C
0x18000a57d  mov     rax, [rbp+57h+arg_10]
0x18000a581  or      [rbp+57h+pTaskConfig.dwFlags], 200040h
0x18000a588  mov     [rbp+57h+pTaskConfig.pszExpandedInformation], rax
0x18000a58c  mov     rcx, [rbx+68h]; hWnd
0x18000a590  call    cs:__imp_IsWindow
0x18000a596  test    eax, eax
0x18000a598  jz      short loc_18000A5B0
0x18000a59a  mov     rcx, [rbx+68h]; hWnd
0x18000a59e  xor     r9d, r9d; lParam
0x18000a5a1  mov     edx, 468h; Msg
0x18000a5a6  lea     r8d, [r9+3]; wParam
0x18000a5aa  call    cs:__imp_SendMessageW
0x18000a5b0  xor     r9d, r9d; pfVerificationFlagChecked
0x18000a5b3  lea     rdx, [rbp+57h+pnButton]; pnButton
0x18000a5b7  xor     r8d, r8d; pnRadioButton
0x18000a5ba  lea     rcx, [rbp+57h+pTaskConfig]; pTaskConfig
0x18000a5be  call    cs:__imp_TaskDialogIndirect
0x18000a5c4  mov     rcx, [rbx+68h]; hWnd
0x18000a5c8  mov     edi, eax
0x18000a5ca  call    cs:__imp_IsWindow
0x18000a5d0  test    eax, eax
0x18000a5d2  jz      short loc_18000A5EA
0x18000a5d4  mov     rcx, [rbx+68h]; hWnd
0x18000a5d8  xor     r9d, r9d; lParam
0x18000a5db  mov     edx, 468h; Msg
0x18000a5e0  lea     r8d, [r9+1]; wParam
0x18000a5e4  call    cs:__imp_SendMessageW
0x18000a5ea  test    edi, edi
0x18000a5ec  jns     short loc_18000A611
0x18000a5ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a5f5  lea     rax, WPP_GLOBAL_Control
0x18000a5fc  cmp     rcx, rax
0x18000a5ff  jz      short loc_18000A613
0x18000a601  test    byte ptr [rcx+1Ch], 1
0x18000a605  jz      short loc_18000A613
0x18000a607  mov     edx, 0Dh
0x18000a60c  jmp     loc_18000A4B7
0x18000a611  xor     edi, edi
0x18000a613  mov     rcx, rbx; this
0x18000a616  call    ?UnInitializeDUI@CUIDlgBase@@IEAAXXZ; CUIDlgBase::UnInitializeDUI(void)
0x18000a61b  mov     rbx, [rsp+0F0h+arg_0]
0x18000a623  test    edi, edi
0x18000a625  cmovns  esi, [rbp+57h+pnButton]
0x18000a629  mov     eax, esi
0x18000a62b  add     rsp, 0E0h
0x18000a632  pop     rdi
0x18000a633  pop     rsi
0x18000a634  pop     rbp
0x18000a635  retn
```
