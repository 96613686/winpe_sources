# CConsentUI::UpSellShowUI(int *,int)

- ea: `0x18000ab00`
- end: `0x18000ad0a`
- name: `?UpSellShowUI@CConsentUI@@AEAAJPEAHH@Z`
- size: `522`
- prototype: `__int64 __fastcall(CConsentUI *__hidden this, int *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000a70c`
- `0x18000a8f4`

## callees

- `0x1800035dc`
- `0x180003604`
- `0x180004874`
- `0x18000ab00`
- `0x18000c8a0`
- `0x180016c1e`

## import_xrefs

- `COMCTL32!TaskDialogIndirect` at `0x18000ac69`
- `COMCTL32!TaskDialogIndirect` at `0x18000ac69`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x18000ac1e`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x18000ac1e`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000abac`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000ac33`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000ac89`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000abac`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000ac33`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000ac89`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x18000ac9c`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x18000ac9c`
- `ext-ms-win-ntuser-window-l1-1-0!SetForegroundWindow` at `0x18000aca6`
- `ext-ms-win-ntuser-window-l1-1-0!SetForegroundWindow` at `0x18000aca6`

## pseudocode

```c
__int64 __fastcall CConsentUI::UpSellShowUI(HWND *this, int *a2, int a3)
{
  HWND v7; // rax
  HICON IconW; // rax
  HWND v9; // rcx
  HRESULT v10; // edi
  _QWORD v11[4]; // [rsp+20h] [rbp-79h] BYREF
  TASKDIALOGCONFIG pTaskConfig; // [rsp+40h] [rbp-59h] BYREF
  int pnButton; // [rsp+108h] [rbp+6Fh] BYREF

  memset_0(&pTaskConfig, 0, sizeof(pTaskConfig));
  pnButton = 0;
  memset((char *)v11 + 4, 0, 20);
  if ( a2 )
  {
    *a2 = 0;
    HIDWORD(v11[1]) = 2;
    LODWORD(v11[0]) = 1;
    *(_QWORD *)((char *)v11 + 4) = 266;
    v11[2] = 267;
    if ( a3 && IsWindow(this[13]) )
      UINotifyGhostWindowAndHide(this[13], *(enum _WER_REPORT_TYPE *)this);
    v7 = this[2];
    pTaskConfig.cbSize = 160;
    pTaskConfig.pszWindowTitle = (PCWSTR)(v7 + 100);
    pTaskConfig.hInstance = &_ImageBase;
    pTaskConfig.pButtons = (const TASKDIALOG_BUTTON *)v11;
    pTaskConfig.pfCallback = (PFTASKDIALOGCALLBACK)CConsentUI::Static_UpSellTaskDialogCallbackProc;
    pTaskConfig.pszMainInstruction = (PCWSTR)264;
    pTaskConfig.pszContent = (PCWSTR)265;
    pTaskConfig.cButtons = 2;
    pTaskConfig.dwFlags = 19;
    pTaskConfig.lpCallbackData = (LONG_PTR)this;
    pTaskConfig.cxWidth = 211;
    IconW = LoadIconW(&_ImageBase, (LPCWSTR)0x194);
    v9 = this[2];
    pTaskConfig.hMainIcon = IconW;
    if ( IsWindow(*((HWND *)v9 + 275)) )
      pTaskConfig.hwndParent = (HWND)*((_QWORD *)this[2] + 275);
    CUIDlgBase::UICallback(this, 7);
    v10 = TaskDialogIndirect(&pTaskConfig, &pnButton, 0, 0);
    CUIDlgBase::UICallback(this, 8);
    if ( a3 && IsWindow(this[13]) )
    {
      ShowWindow(this[13], 5);
      SetForegroundWindow(this[13]);
    }
    if ( v10 >= 0 )
    {
      v10 = 0;
      *a2 = pnButton == 1;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_fea2387d138a3e728ec0a3daac89d932_Traceguids,
        (unsigned int)v10);
    }
    return (unsigned int)v10;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_fea2387d138a3e728ec0a3daac89d932_Traceguids);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18000ab00  mov     [rsp-8+arg_0], rbx
0x18000ab05  mov     [rsp-8+arg_10], rsi
0x18000ab0a  push    rbp
0x18000ab0b  push    rdi
0x18000ab0c  push    r14
0x18000ab0e  lea     rbp, [rsp-47h]
0x18000ab13  sub     rsp, 0E0h
0x18000ab1a  mov     r14d, r8d
0x18000ab1d  mov     rsi, rdx
0x18000ab20  mov     rbx, rcx
0x18000ab23  xor     edx, edx; Val
0x18000ab25  mov     r8d, 0A0h; Size
0x18000ab2b  lea     rcx, [rbp+57h+pTaskConfig]; void *
0x18000ab2f  call    memset_0
0x18000ab34  xor     eax, eax
0x18000ab36  mov     [rbp+57h+pnButton], 0
0x18000ab3d  mov     [rbp+57h+var_BC], eax
0x18000ab40  xorps   xmm0, xmm0
0x18000ab43  movups  [rbp+57h+var_CC], xmm0
0x18000ab47  test    rsi, rsi
0x18000ab4a  jnz     short loc_18000AB82
0x18000ab4c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab53  lea     rax, WPP_GLOBAL_Control
0x18000ab5a  cmp     rcx, rax
0x18000ab5d  jz      short loc_18000AB78
0x18000ab5f  test    byte ptr [rcx+1Ch], 1
0x18000ab63  jz      short loc_18000AB78
0x18000ab65  mov     rcx, [rcx+10h]
0x18000ab69  lea     edx, [rsi+0Eh]
0x18000ab6c  lea     r8, WPP_fea2387d138a3e728ec0a3daac89d932_Traceguids
0x18000ab73  call    WPP_SF_
0x18000ab78  mov     eax, 80070057h
0x18000ab7d  jmp     loc_18000ACF2
0x18000ab82  mov     [rsi], eax
0x18000ab84  mov     edi, 2
0x18000ab89  mov     dword ptr [rbp+57h+var_CC+8], edi
0x18000ab8c  mov     [rbp+57h+var_D0], 1
0x18000ab93  mov     qword ptr [rbp+57h+var_CC], 10Ah
0x18000ab9b  mov     qword ptr [rbp+57h+var_CC+0Ch], 10Bh
0x18000aba3  test    r14d, r14d
0x18000aba6  jz      short loc_18000ABC1
0x18000aba8  mov     rcx, [rbx+68h]; hWnd
0x18000abac  call    cs:__imp_IsWindow
0x18000abb2  test    eax, eax
0x18000abb4  jz      short loc_18000ABC1
0x18000abb6  mov     edx, [rbx]; enum _WER_REPORT_TYPE
0x18000abb8  mov     rcx, [rbx+68h]; hWndChild
0x18000abbc  call    ?UINotifyGhostWindowAndHide@@YAJPEAUHWND__@@W4_WER_REPORT_TYPE@@@Z; UINotifyGhostWindowAndHide(HWND__ *,_WER_REPORT_TYPE)
0x18000abc1  mov     rax, [rbx+10h]
0x18000abc5  lea     rcx, __ImageBase; hInstance
0x18000abcc  add     rax, 190h
0x18000abd2  mov     [rbp+57h+pTaskConfig.cbSize], 0A0h
0x18000abd9  mov     [rbp+57h+pTaskConfig.pszWindowTitle], rax
0x18000abdd  mov     edx, 194h; lpIconName
0x18000abe2  lea     rax, [rbp+57h+var_D0]
0x18000abe6  mov     [rbp+57h+pTaskConfig.hInstance], rcx
0x18000abea  mov     [rbp+57h+pTaskConfig.pButtons], rax
0x18000abee  lea     rax, ?Static_UpSellTaskDialogCallbackProc@CConsentUI@@CAJPEAUHWND__@@I_K_J2@Z; CConsentUI::Static_UpSellTaskDialogCallbackProc(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x18000abf5  mov     [rbp+57h+pTaskConfig.pfCallback], rax
0x18000abf9  mov     [rbp+57h+pTaskConfig.pszMainInstruction], 108h
0x18000ac01  mov     [rbp+57h+pTaskConfig.pszContent], 109h
0x18000ac09  mov     [rbp+57h+pTaskConfig.cButtons], edi
0x18000ac0c  mov     [rbp+57h+pTaskConfig.dwFlags], 13h
0x18000ac13  mov     [rbp+57h+pTaskConfig.lpCallbackData], rbx
0x18000ac17  mov     [rbp+57h+pTaskConfig.cxWidth], 0D3h
0x18000ac1e  call    cs:__imp_LoadIconW
0x18000ac24  mov     rcx, [rbx+10h]
0x18000ac28  mov     qword ptr [rbp+57h+pTaskConfig.24h], rax
0x18000ac2c  mov     rcx, [rcx+898h]; hWnd
0x18000ac33  call    cs:__imp_IsWindow
0x18000ac39  test    eax, eax
0x18000ac3b  jz      short loc_18000AC4C
0x18000ac3d  mov     rax, [rbx+10h]
0x18000ac41  mov     rcx, [rax+898h]
0x18000ac48  mov     [rbp+57h+pTaskConfig.hwndParent], rcx
0x18000ac4c  xor     r8d, r8d
0x18000ac4f  mov     rcx, rbx
0x18000ac52  lea     edx, [r8+7]
0x18000ac56  call    ?UICallback@CUIDlgBase@@IEAAHW4_UICALLBACKTYPE@@_K@Z; CUIDlgBase::UICallback(_UICALLBACKTYPE,unsigned __int64)
0x18000ac5b  xor     r9d, r9d; pfVerificationFlagChecked
0x18000ac5e  lea     rdx, [rbp+57h+pnButton]; pnButton
0x18000ac62  xor     r8d, r8d; pnRadioButton
0x18000ac65  lea     rcx, [rbp+57h+pTaskConfig]; pTaskConfig
0x18000ac69  call    cs:__imp_TaskDialogIndirect
0x18000ac6f  xor     r8d, r8d
0x18000ac72  mov     rcx, rbx
0x18000ac75  mov     edi, eax
0x18000ac77  lea     edx, [r8+8]
0x18000ac7b  call    ?UICallback@CUIDlgBase@@IEAAHW4_UICALLBACKTYPE@@_K@Z; CUIDlgBase::UICallback(_UICALLBACKTYPE,unsigned __int64)
0x18000ac80  test    r14d, r14d
0x18000ac83  jz      short loc_18000ACAC
0x18000ac85  mov     rcx, [rbx+68h]; hWnd
0x18000ac89  call    cs:__imp_IsWindow
0x18000ac8f  test    eax, eax
0x18000ac91  jz      short loc_18000ACAC
0x18000ac93  mov     rcx, [rbx+68h]; hWnd
0x18000ac97  mov     edx, 5; nCmdShow
0x18000ac9c  call    cs:__imp_ShowWindow
0x18000aca2  mov     rcx, [rbx+68h]; hWnd
0x18000aca6  call    cs:__imp_SetForegroundWindow
0x18000acac  test    edi, edi
0x18000acae  jns     short loc_18000ACE3
0x18000acb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000acb7  lea     rax, WPP_GLOBAL_Control
0x18000acbe  cmp     rcx, rax
0x18000acc1  jz      short loc_18000ACF0
0x18000acc3  test    byte ptr [rcx+1Ch], 1
0x18000acc7  jz      short loc_18000ACF0
0x18000acc9  mov     rcx, [rcx+10h]
0x18000accd  lea     r8, WPP_fea2387d138a3e728ec0a3daac89d932_Traceguids
0x18000acd4  mov     edx, 0Fh
0x18000acd9  mov     r9d, edi
0x18000acdc  call    WPP_SF_d
0x18000ace1  jmp     short loc_18000ACF0
0x18000ace3  xor     eax, eax
0x18000ace5  cmp     [rbp+57h+pnButton], 1
0x18000ace9  setz    al
0x18000acec  xor     edi, edi
0x18000acee  mov     [rsi], eax
0x18000acf0  mov     eax, edi
0x18000acf2  lea     r11, [rsp+0F0h+var_10]
0x18000acfa  mov     rbx, [r11+20h]
0x18000acfe  mov     rsi, [r11+30h]
0x18000ad02  mov     rsp, r11
0x18000ad05  pop     r14
0x18000ad07  pop     rdi
0x18000ad08  pop     rbp
0x18000ad09  retn
```
