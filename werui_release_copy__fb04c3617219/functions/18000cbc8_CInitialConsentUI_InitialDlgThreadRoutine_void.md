# CInitialConsentUI::InitialDlgThreadRoutine(void)

- ea: `0x18000cbc8`
- end: `0x18000d10c`
- name: `?InitialDlgThreadRoutine@CInitialConsentUI@@QEAAJXZ`
- size: `1348`
- prototype: `__int64 __fastcall(CInitialConsentUI *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000dd40`

## callees

- `0x1800035dc`
- `0x180003604`
- `0x180003fe4`
- `0x180005c80`
- `0x180008f3c`
- `0x180009580`
- `0x18000c268`
- `0x18000c8a0`
- `0x18000c8d8`
- `0x18000cbc8`
- `0x18000d4c0`
- `0x18000d6b8`
- `0x180016c50`

## import_xrefs

- `wer!WerpGetUIParamByIndex` at `0x18000cd99`
- `wer!WerpGetUIParamByIndex` at `0x18000ce3c`
- `wer!WerpGetUIParamByIndex` at `0x18000ce80`
- `wer!WerpGetUIParamByIndex` at `0x18000cd99`
- `wer!WerpGetUIParamByIndex` at `0x18000ce3c`
- `wer!WerpGetUIParamByIndex` at `0x18000ce80`
- `wer!WerpIsDisabled` at `0x18000cceb`
- `wer!WerpIsDisabled` at `0x18000cceb`
- `wer!WerpGetReportFlags` at `0x18000cc7d`
- `wer!WerpGetReportFlags` at `0x18000cc7d`
- `KERNEL32!GetLastError` at `0x18000cffe`
- `KERNEL32!GetLastError` at `0x18000cffe`
- `KERNEL32!SetEvent` at `0x18000d09c`
- `KERNEL32!SetEvent` at `0x18000d09c`
- `COMCTL32!TaskDialogIndirect` at `0x18000d067`
- `COMCTL32!TaskDialogIndirect` at `0x18000d067`
- `SHELL32!ExtractIconExW` at `0x18000cfef`
- `SHELL32!ExtractIconExW` at `0x18000cfef`
- `ext-ms-win-ntuser-gui-l1-1-0!DestroyIcon` at `0x18000d0c7`
- `ext-ms-win-ntuser-gui-l1-1-0!DestroyIcon` at `0x18000d0c7`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x18000d020`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x18000d020`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000cfb2`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000cfb2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInitialConsentUI::InitialDlgThreadRoutine(CInitialConsentUI *this)
{
  __int64 i; // rdx
  _WORD *v3; // rcx
  int v4; // r14d
  HRESULT ReportFlags; // eax
  int UIParamByIndex; // esi
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  int v9; // edi
  unsigned int v10; // r8d
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  int v13; // r15d
  int v14; // r14d
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // eax
  DWORD LastError; // eax
  HICON IconW; // rax
  int v22; // [rsp+30h] [rbp-99h] BYREF
  unsigned int v23; // [rsp+34h] [rbp-95h] BYREF
  unsigned int v24; // [rsp+38h] [rbp-91h] BYREF
  __int64 v25; // [rsp+40h] [rbp-89h] BYREF
  int v26; // [rsp+48h] [rbp-81h] BYREF
  int pnButton; // [rsp+4Ch] [rbp-7Dh] BYREF
  HICON phiconLarge; // [rsp+50h] [rbp-79h] BYREF
  __int64 v29; // [rsp+58h] [rbp-71h] BYREF
  LPCWSTR lpszFile; // [rsp+60h] [rbp-69h] BYREF
  struct IUnknown *v31; // [rsp+68h] [rbp-61h] BYREF
  _QWORD v32[4]; // [rsp+70h] [rbp-59h] BYREF
  _BYTE v33[20]; // [rsp+90h] [rbp-39h] BYREF
  __int128 v34; // [rsp+A4h] [rbp-25h]
  __int128 v35; // [rsp+B4h] [rbp-15h]
  __int64 v36; // [rsp+C4h] [rbp-5h]

  v23 = 0;
  v29 = 0;
  v25 = 0;
  lpszFile = 0;
  pnButton = 0;
  v31 = 0;
  v24 = 2;
  phiconLarge = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v32);
  memset(v33, 0, sizeof(v33));
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v22 = 0;
  v26 = 0;
  for ( i = 0; i != 5; ++i )
  {
    v3 = (_WORD *)*((_QWORD *)this + 4 * i + 11);
    *((_QWORD *)this + 4 * i + 12) = v3;
    *v3 = 0;
  }
  v4 = *(_DWORD *)this;
  ReportFlags = WerpGetReportFlags(*((_QWORD *)this + 5), &v26);
  UIParamByIndex = ReportFlags;
  if ( ReportFlags < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 31;
LABEL_7:
      WPP_SF_d(v7[2], v8, WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids, (unsigned int)ReportFlags);
      goto LABEL_70;
    }
    goto LABEL_70;
  }
  v9 = 2056;
  if ( v4 != 4 )
    v9 = 2072;
  *((_DWORD *)this + 111) = 2;
  WerpIsDisabled(*((_QWORD *)this + 5), &v22);
  if ( *(_DWORD *)this != 3 || v22 || *(int *)(*((_QWORD *)this + 1) + 5100LL) < 2 )
  {
    v13 = 0;
    if ( !v22 )
      v9 |= 0x200040u;
    UIParamByIndex = CInitialConsentUI::SetOptionButtons(this, (struct _TASKDIALOG_BUTTON *)v33, v10, &v23, &v24);
    if ( UIParamByIndex < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_70;
      v12 = 33;
LABEL_17:
      WPP_SF_(v11[2], v12, WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids);
      goto LABEL_70;
    }
  }
  else
  {
    UIParamByIndex = CInitialConsentUI::SetOptedinEndTaskOptions(
                       this,
                       (struct _TASKDIALOG_BUTTON *)v33,
                       v10,
                       &v23,
                       &v24);
    if ( UIParamByIndex < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_70;
      v12 = 32;
      goto LABEL_17;
    }
    v13 = 1;
  }
  v14 = v9 | 0x8000;
  if ( !*((_DWORD *)this + 133) )
    v14 = v9;
  UIParamByIndex = WerpGetUIParamByIndex(*((_QWORD *)this + 5), 3, &v29);
  if ( UIParamByIndex < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_70;
    v12 = 34;
    goto LABEL_17;
  }
  UIParamByIndex = WerpGetUIParamByIndex(*((_QWORD *)this + 5), 4, &v25);
  if ( UIParamByIndex < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_70;
    v12 = 35;
    goto LABEL_17;
  }
  WerpGetUIParamByIndex(*((_QWORD *)this + 5), 2, &lpszFile);
  ReportFlags = CUIDlgBase::InitializeDUI(
                  this,
                  (int (*)(unsigned int, unsigned __int64, __int64, __int64 *, void *))CInitialConsentUI::Static_NotifyHandler,
                  this,
                  &v31);
  UIParamByIndex = ReportFlags;
  if ( ReportFlags >= 0 )
  {
    if ( v22 )
    {
      if ( (v26 & 2) != 0 )
      {
        if ( (v26 & 1) != 0 )
          v15 = 288;
        else
          v15 = 289;
        goto LABEL_46;
      }
      if ( (v26 & 1) != 0 )
      {
        v15 = 290;
LABEL_46:
        UtilLoadString(v32, v15);
        v16 = v32[0];
        v25 = v32[0];
        goto LABEL_50;
      }
      if ( *(_DWORD *)this == 2 )
      {
        v15 = 287;
        goto LABEL_46;
      }
    }
    v16 = v25;
LABEL_50:
    *((_DWORD *)this + 93) = 160;
    *((_QWORD *)this + 48) = &_ImageBase;
    *((_QWORD *)this + 52) = v29;
    *((_QWORD *)this + 53) = v16;
    v17 = *((_QWORD *)this + 2);
    *((_QWORD *)this + 50) = v17 + 400;
    *((_QWORD *)this + 60) = 207;
    *((_QWORD *)this + 61) = 206;
    *(_QWORD *)((char *)this + 436) = v33;
    *((_DWORD *)this + 108) = v23;
    *((_QWORD *)this + 64) = CInitialConsentUI::Static_TaskDialogCallbackProc;
    *((_QWORD *)this + 65) = this;
    *((_DWORD *)this + 132) = 0;
    *((_DWORD *)this + 111) = v24;
    if ( IsWindow(*(HWND *)(v17 + 2200)) )
      *((_QWORD *)this + 47) = *(_QWORD *)(*((_QWORD *)this + 2) + 2200LL);
    if ( lpszFile )
    {
      if ( ExtractIconExW(lpszFile, 0, &phiconLarge, 0, 1u) )
      {
        v18 = 0;
      }
      else
      {
        LastError = GetLastError();
        v18 = ERROR_HR_FROM_WIN32(LastError);
      }
      v14 |= 2u;
      if ( v18 < 0 )
        IconW = LoadIconW(0, (LPCWSTR)0x7F00);
      else
        IconW = phiconLarge;
      *((_QWORD *)this + 51) = IconW;
    }
    if ( !v13 && !v22 )
      *((_QWORD *)this + 59) = v31;
    CUIDlgBase::UICallback(this, 7);
    *((_DWORD *)this + 98) = v14;
    ReportFlags = TaskDialogIndirect((const TASKDIALOGCONFIG *)((char *)this + 372), &pnButton, 0, 0);
    UIParamByIndex = ReportFlags;
    if ( ReportFlags >= 0 )
    {
      if ( pnButton == 2 )
      {
        SetEvent(*((HANDLE *)this + 45));
        *((_DWORD *)this + 92) = 2;
      }
      CUIDlgBase::UICallback(this, 8);
      UIParamByIndex = 0;
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 37;
        goto LABEL_7;
      }
    }
    goto LABEL_70;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v8 = 36;
    goto LABEL_7;
  }
LABEL_70:
  if ( phiconLarge )
  {
    DestroyIcon(phiconLarge);
    *((_DWORD *)this + 98) &= ~2u;
    phiconLarge = 0;
  }
  CUIDlgBase::UnInitializeDUI(this);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v32);
  return (unsigned int)UIParamByIndex;
}

```

## disassembly

```asm
0x18000cbc8  push    rbp
0x18000cbca  push    rbx
0x18000cbcb  push    rsi
0x18000cbcc  push    rdi
0x18000cbcd  push    r12
0x18000cbcf  push    r13
0x18000cbd1  push    r14
0x18000cbd3  push    r15
0x18000cbd5  lea     rbp, [rsp-1Fh]
0x18000cbda  sub     rsp, 0E8h
0x18000cbe1  mov     rax, cs:__security_cookie
0x18000cbe8  xor     rax, rsp
0x18000cbeb  mov     [rbp+57h+var_50], rax
0x18000cbef  mov     rbx, rcx
0x18000cbf2  xor     r13d, r13d
0x18000cbf5  mov     [rsp+120h+var_EC], r13d
0x18000cbfa  mov     [rbp+57h+var_C8], r13
0x18000cbfe  mov     [rsp+120h+var_E0], r13
0x18000cc03  mov     [rbp+57h+lpszFile], r13
0x18000cc07  mov     [rbp+57h+pnButton], r13d
0x18000cc0b  mov     [rbp+57h+var_B8], r13
0x18000cc0f  lea     r15d, [r13+2]
0x18000cc13  mov     [rsp+120h+var_E8], r15d
0x18000cc18  mov     [rbp+57h+phiconLarge], r13
0x18000cc1c  lea     rcx, [rbp+57h+var_B0]; void *
0x18000cc20  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x18000cc25  nop
0x18000cc26  mov     dword ptr [rbp+57h+var_90], r13d
0x18000cc2a  xorps   xmm0, xmm0
0x18000cc2d  xor     eax, eax
0x18000cc2f  movups  xmmword ptr [rbp+57h+var_90+4], xmm0
0x18000cc33  movups  [rbp+57h+var_7C], xmm0
0x18000cc37  movups  [rbp+57h+var_6C], xmm0
0x18000cc3b  mov     [rbp+57h+var_5C], rax
0x18000cc3f  mov     [rsp+120h+var_F0], r13d
0x18000cc44  mov     [rsp+120h+var_D8], r13d
0x18000cc49  mov     edx, r13d
0x18000cc4c  mov     rax, rdx
0x18000cc4f  shl     rax, 5
0x18000cc53  mov     rcx, [rax+rbx+58h]
0x18000cc58  lea     rax, [rdx+3]
0x18000cc5c  shl     rax, 5
0x18000cc60  mov     [rax+rbx], rcx
0x18000cc64  mov     [rcx], r13w
0x18000cc68  inc     rdx
0x18000cc6b  cmp     rdx, 5
0x18000cc6f  jnz     short loc_18000CC4C
0x18000cc71  mov     r14d, [rbx]
0x18000cc74  lea     rdx, [rsp+120h+var_D8]
0x18000cc79  mov     rcx, [rbx+28h]
0x18000cc7d  call    cs:__imp_WerpGetReportFlags
0x18000cc83  mov     esi, eax
0x18000cc85  test    eax, eax
0x18000cc87  jns     short loc_18000CCC7
0x18000cc89  lea     rdi, WPP_GLOBAL_Control
0x18000cc90  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc97  cmp     rcx, rdi
0x18000cc9a  jz      loc_18000D0BE
0x18000cca0  test    byte ptr [rcx+1Ch], 1
0x18000cca4  jz      loc_18000D0BE
0x18000ccaa  mov     edx, 1Fh
0x18000ccaf  mov     r9d, eax
0x18000ccb2  lea     r8, WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids
0x18000ccb9  mov     rcx, [rcx+10h]
0x18000ccbd  call    WPP_SF_d
0x18000ccc2  jmp     loc_18000D0BE
0x18000ccc7  mov     edi, 808h
0x18000cccc  lea     eax, [rdi+10h]
0x18000cccf  cmp     r14d, 4
0x18000ccd3  cmovnz  edi, eax
0x18000ccd6  lea     r12, [rbx+174h]
0x18000ccdd  mov     [r12+48h], r15d
0x18000cce2  lea     rdx, [rsp+120h+var_F0]
0x18000cce7  mov     rcx, [rbx+28h]
0x18000cceb  call    cs:__imp_WerpIsDisabled
0x18000ccf1  mov     ecx, [rsp+120h+var_F0]
0x18000ccf5  cmp     dword ptr [rbx], 3
0x18000ccf8  jnz     loc_18000CDD1
0x18000ccfe  test    ecx, ecx
0x18000cd00  jnz     loc_18000CDD1
0x18000cd06  mov     rax, [rbx+8]
0x18000cd0a  cmp     [rax+13ECh], r15d
0x18000cd11  jl      loc_18000CDD1
0x18000cd17  lea     rax, [rsp+120h+var_E8]
0x18000cd1c  mov     qword ptr [rsp+120h+nIcons], rax; unsigned int *
0x18000cd21  lea     r9, [rsp+120h+var_EC]; unsigned int *
0x18000cd26  lea     rdx, [rbp+57h+var_90]; struct _TASKDIALOG_BUTTON *
0x18000cd2a  mov     rcx, rbx; this
0x18000cd2d  call    ?SetOptedinEndTaskOptions@CInitialConsentUI@@AEAAJPEAU_TASKDIALOG_BUTTON@@KPEAK1@Z; CInitialConsentUI::SetOptedinEndTaskOptions(_TASKDIALOG_BUTTON *,ulong,ulong *,ulong *)
0x18000cd32  mov     esi, eax
0x18000cd34  test    eax, eax
0x18000cd36  jns     short loc_18000CD73
0x18000cd38  lea     rdi, WPP_GLOBAL_Control
0x18000cd3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd46  cmp     rcx, rdi
0x18000cd49  jz      loc_18000D0BE
0x18000cd4f  test    byte ptr [rcx+1Ch], 1
0x18000cd53  jz      loc_18000D0BE
0x18000cd59  mov     edx, 20h ; ' '
0x18000cd5e  lea     r8, WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids
0x18000cd65  mov     rcx, [rcx+10h]
0x18000cd69  call    WPP_SF_
0x18000cd6e  jmp     loc_18000D0BE
0x18000cd73  mov     r15d, 1
0x18000cd79  mov     r14d, edi
0x18000cd7c  bts     r14d, 0Fh
0x18000cd81  cmp     [rbx+214h], r13d
0x18000cd88  cmovz   r14d, edi
0x18000cd8c  lea     r8, [rbp+57h+var_C8]
0x18000cd90  mov     edx, 3
0x18000cd95  mov     rcx, [rbx+28h]
0x18000cd99  call    cs:__imp_WerpGetUIParamByIndex
0x18000cd9f  mov     esi, eax
0x18000cda1  test    eax, eax
0x18000cda3  jns     loc_18000CE2E
0x18000cda9  lea     rdi, WPP_GLOBAL_Control
0x18000cdb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cdb7  cmp     rcx, rdi
0x18000cdba  jz      loc_18000D0BE
0x18000cdc0  test    byte ptr [rcx+1Ch], 1
0x18000cdc4  jz      loc_18000D0BE
0x18000cdca  mov     edx, 22h ; '"'
0x18000cdcf  jmp     short loc_18000CD5E
0x18000cdd1  mov     r15d, r13d
0x18000cdd4  test    ecx, ecx
0x18000cdd6  jnz     short loc_18000CDDE
0x18000cdd8  or      edi, 200040h
0x18000cdde  lea     rax, [rsp+120h+var_E8]
0x18000cde3  mov     qword ptr [rsp+120h+nIcons], rax; unsigned int *
0x18000cde8  lea     r9, [rsp+120h+var_EC]; unsigned int *
0x18000cded  lea     rdx, [rbp+57h+var_90]; struct _TASKDIALOG_BUTTON *
0x18000cdf1  mov     rcx, rbx; this
0x18000cdf4  call    ?SetOptionButtons@CInitialConsentUI@@AEAAJPEAU_TASKDIALOG_BUTTON@@KPEAK1@Z; CInitialConsentUI::SetOptionButtons(_TASKDIALOG_BUTTON *,ulong,ulong *,ulong *)
0x18000cdf9  mov     esi, eax
0x18000cdfb  test    eax, eax
0x18000cdfd  jns     loc_18000CD79
0x18000ce03  lea     rdi, WPP_GLOBAL_Control
0x18000ce0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce11  cmp     rcx, rdi
0x18000ce14  jz      loc_18000D0BE
0x18000ce1a  test    byte ptr [rcx+1Ch], 1
0x18000ce1e  jz      loc_18000D0BE
0x18000ce24  mov     edx, 21h ; '!'
0x18000ce29  jmp     loc_18000CD5E
0x18000ce2e  lea     r8, [rsp+120h+var_E0]
0x18000ce33  mov     edx, 4
0x18000ce38  mov     rcx, [rbx+28h]
0x18000ce3c  call    cs:__imp_WerpGetUIParamByIndex
0x18000ce42  mov     esi, eax
0x18000ce44  test    eax, eax
0x18000ce46  jns     short loc_18000CE73
0x18000ce48  lea     rdi, WPP_GLOBAL_Control
0x18000ce4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce56  cmp     rcx, rdi
0x18000ce59  jz      loc_18000D0BE
0x18000ce5f  test    byte ptr [rcx+1Ch], 1
0x18000ce63  jz      loc_18000D0BE
0x18000ce69  mov     edx, 23h ; '#'
0x18000ce6e  jmp     loc_18000CD5E
0x18000ce73  lea     r8, [rbp+57h+lpszFile]
0x18000ce77  mov     edx, 2
0x18000ce7c  mov     rcx, [rbx+28h]
0x18000ce80  call    cs:__imp_WerpGetUIParamByIndex
0x18000ce86  lea     r9, [rbp+57h+var_B8]; struct IUnknown **
0x18000ce8a  mov     r8, rbx; void *
0x18000ce8d  lea     rdx, ?Static_NotifyHandler@CInitialConsentUI@@CAHI_K_JPEA_JPEAX@Z; int (*)(unsigned int, unsigned __int64, __int64, __int64 *, void *)
0x18000ce94  mov     rcx, rbx; this
0x18000ce97  call    ?InitializeDUI@CUIDlgBase@@IEAAJP6AHI_K_JPEA_JPEAX@Z3PEAPEAUIUnknown@@@Z; CUIDlgBase::InitializeDUI(int (*)(uint,unsigned __int64,__int64,__int64 *,void *),void *,IUnknown * *)
0x18000ce9c  mov     esi, eax
0x18000ce9e  test    eax, eax
0x18000cea0  jns     short loc_18000CECD
0x18000cea2  lea     rdi, WPP_GLOBAL_Control
0x18000cea9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ceb0  cmp     rcx, rdi
0x18000ceb3  jz      loc_18000D0BE
0x18000ceb9  test    byte ptr [rcx+1Ch], 1
0x18000cebd  jz      loc_18000D0BE
0x18000cec3  mov     edx, 24h ; '$'
0x18000cec8  jmp     loc_18000CCAF
0x18000cecd  cmp     [rsp+120h+var_F0], r13d
0x18000ced2  jz      short loc_18000CF1B
0x18000ced4  mov     eax, [rsp+120h+var_D8]
0x18000ced8  test    al, 2
0x18000ceda  jz      short loc_18000CEF2
0x18000cedc  lea     rcx, [rbp+57h+var_B0]
0x18000cee0  test    al, 1
0x18000cee2  jz      short loc_18000CEEB
0x18000cee4  mov     edx, 120h
0x18000cee9  jmp     short loc_18000CEFF
0x18000ceeb  mov     edx, 121h
0x18000cef0  jmp     short loc_18000CEFF
0x18000cef2  test    al, 1
0x18000cef4  jz      short loc_18000CF0F
0x18000cef6  mov     edx, 122h
0x18000cefb  lea     rcx, [rbp+57h+var_B0]
0x18000ceff  call    ?UtilLoadString@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ulong,HINSTANCE__ *)
0x18000cf04  mov     rcx, [rbp+57h+var_B0]
0x18000cf08  mov     [rsp+120h+var_E0], rcx
0x18000cf0d  jmp     short loc_18000CF20
0x18000cf0f  cmp     dword ptr [rbx], 2
0x18000cf12  jnz     short loc_18000CF1B
0x18000cf14  mov     edx, 11Fh
0x18000cf19  jmp     short loc_18000CEFB
0x18000cf1b  mov     rcx, [rsp+120h+var_E0]
0x18000cf20  mov     dword ptr [r12], 0A0h
0x18000cf28  lea     rax, __ImageBase
0x18000cf2f  mov     [rbx+180h], rax
0x18000cf36  mov     rax, [rbp+57h+var_C8]
0x18000cf3a  mov     [rbx+1A0h], rax
0x18000cf41  mov     [rbx+1A8h], rcx
0x18000cf48  mov     rcx, [rbx+10h]
0x18000cf4c  lea     rax, [rcx+190h]
0x18000cf53  mov     [rbx+190h], rax
0x18000cf5a  mov     qword ptr [rbx+1E0h], 0CFh
0x18000cf65  mov     qword ptr [rbx+1E8h], 0CEh
0x18000cf70  lea     rax, [rbp+57h+var_90]
0x18000cf74  mov     [rbx+1B4h], rax
0x18000cf7b  mov     eax, [rsp+120h+var_EC]
0x18000cf7f  mov     [rbx+1B0h], eax
0x18000cf85  lea     rax, ?Static_TaskDialogCallbackProc@CInitialConsentUI@@CAJPEAUHWND__@@I_K_J2@Z; CInitialConsentUI::Static_TaskDialogCallbackProc(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x18000cf8c  mov     [rbx+200h], rax
0x18000cf93  mov     [rbx+208h], rbx
0x18000cf9a  mov     [rbx+210h], r13d
0x18000cfa1  mov     eax, [rsp+120h+var_E8]
0x18000cfa5  mov     [rbx+1BCh], eax
0x18000cfab  mov     rcx, [rcx+898h]; hWnd
0x18000cfb2  call    cs:__imp_IsWindow
0x18000cfb8  test    eax, eax
0x18000cfba  jz      short loc_18000CFCE
0x18000cfbc  mov     rax, [rbx+10h]
0x18000cfc0  mov     rcx, [rax+898h]
0x18000cfc7  mov     [rbx+178h], rcx
0x18000cfce  lea     rdi, WPP_GLOBAL_Control
0x18000cfd5  mov     rcx, [rbp+57h+lpszFile]; lpszFile
0x18000cfd9  test    rcx, rcx
0x18000cfdc  jz      short loc_18000D02D
0x18000cfde  mov     [rsp+120h+nIcons], 1; nIcons
0x18000cfe6  xor     r9d, r9d; phiconSmall
0x18000cfe9  lea     r8, [rbp+57h+phiconLarge]; phiconLarge
0x18000cfed  xor     edx, edx; nIconIndex
0x18000cfef  call    cs:__imp_ExtractIconExW
0x18000cff5  test    eax, eax
0x18000cff7  jz      short loc_18000CFFE
0x18000cff9  mov     eax, r13d
0x18000cffc  jmp     short loc_18000D00B
0x18000cffe  call    cs:__imp_GetLastError
0x18000d004  mov     ecx, eax; unsigned int
0x18000d006  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18000d00b  or      r14d, 2
0x18000d00f  test    eax, eax
0x18000d011  js      short loc_18000D019
0x18000d013  mov     rax, [rbp+57h+phiconLarge]
0x18000d017  jmp     short loc_18000D026
0x18000d019  mov     edx, 7F00h; lpIconName
0x18000d01e  xor     ecx, ecx; hInstance
0x18000d020  call    cs:__imp_LoadIconW
0x18000d026  mov     [rbx+198h], rax
0x18000d02d  test    r15d, r15d
0x18000d030  jnz     short loc_18000D044
0x18000d032  cmp     [rsp+120h+var_F0], r13d
0x18000d037  jnz     short loc_18000D044
0x18000d039  mov     rax, [rbp+57h+var_B8]
0x18000d03d  mov     [rbx+1D8h], rax
0x18000d044  xor     r8d, r8d
0x18000d047  lea     edx, [r8+7]
0x18000d04b  mov     rcx, rbx
0x18000d04e  call    ?UICallback@CUIDlgBase@@IEAAHW4_UICALLBACKTYPE@@_K@Z; CUIDlgBase::UICallback(_UICALLBACKTYPE,unsigned __int64)
0x18000d053  mov     [rbx+188h], r14d
0x18000d05a  xor     r9d, r9d; pfVerificationFlagChecked
0x18000d05d  xor     r8d, r8d; pnRadioButton
0x18000d060  lea     rdx, [rbp+57h+pnButton]; pnButton
0x18000d064  mov     rcx, r12; pTaskConfig
0x18000d067  call    cs:__imp_TaskDialogIndirect
0x18000d06d  mov     esi, eax
0x18000d06f  test    eax, eax
0x18000d071  jns     short loc_18000D08F
0x18000d073  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d07a  cmp     rcx, rdi
0x18000d07d  jz      short loc_18000D0BE
0x18000d07f  test    byte ptr [rcx+1Ch], 1
0x18000d083  jz      short loc_18000D0BE
0x18000d085  mov     edx, 25h ; '%'
0x18000d08a  jmp     loc_18000CCAF
0x18000d08f  cmp     [rbp+57h+pnButton], 2
0x18000d093  jnz     short loc_18000D0AC
0x18000d095  mov     rcx, [rbx+168h]; hEvent
0x18000d09c  call    cs:__imp_SetEvent
0x18000d0a2  mov     dword ptr [rbx+170h], 2
0x18000d0ac  xor     r8d, r8d
0x18000d0af  lea     edx, [r8+8]
0x18000d0b3  mov     rcx, rbx
0x18000d0b6  call    ?UICallback@CUIDlgBase@@IEAAHW4_UICALLBACKTYPE@@_K@Z; CUIDlgBase::UICallback(_UICALLBACKTYPE,unsigned __int64)
0x18000d0bb  mov     esi, r13d
0x18000d0be  mov     rcx, [rbp+57h+phiconLarge]; hIcon
0x18000d0c2  test    rcx, rcx
0x18000d0c5  jz      short loc_18000D0D8
0x18000d0c7  call    cs:__imp_DestroyIcon
0x18000d0cd  and     dword ptr [rbx+188h], 0FFFFFFFDh
0x18000d0d4  mov     [rbp+57h+phiconLarge], r13
0x18000d0d8  mov     rcx, rbx; this
  ... truncated ...
```
