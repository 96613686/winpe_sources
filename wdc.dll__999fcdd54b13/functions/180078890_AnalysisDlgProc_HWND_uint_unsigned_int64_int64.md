# AnalysisDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180078890`
- end: `0x180078d65`
- name: `?AnalysisDlgProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `1237`
- prototype: `INT_PTR __fastcall(HWND, int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800150d0`
- `0x180016880`
- `0x1800295c4`
- `0x18002d2c8`
- `0x18002fda8`
- `0x1800761cc`
- `0x180076438`
- `0x180078890`
- `0x180078ea0`
- `0x1800792a8`
- `0x18007c538`
- `0x18007c728`

## import_xrefs

- `ADVAPI32!RegisterWaitChainCOMCallback` at `0x180078acc`
- `ADVAPI32!RegisterWaitChainCOMCallback` at `0x180078acc`
- `SHELL32!ShellExecuteW` at `0x180078d50`
- `SHELL32!ShellExecuteW` at `0x180078d50`
- `USER32!EndDialog` at `0x180078929`
- `USER32!EndDialog` at `0x180078a6e`
- `USER32!EndDialog` at `0x180078bf5`
- `USER32!EndDialog` at `0x180078929`
- `USER32!EndDialog` at `0x180078a6e`
- `USER32!EndDialog` at `0x180078bf5`
- `USER32!GetWindowLongPtrW` at `0x180078b0a`
- `USER32!GetWindowLongPtrW` at `0x180078b0a`
- `USER32!SetWindowLongPtrW` at `0x180078b22`
- `USER32!SetWindowLongPtrW` at `0x180078c83`
- `USER32!SetWindowLongPtrW` at `0x180078b22`
- `USER32!SetWindowLongPtrW` at `0x180078c83`
- `USER32!EnableWindow` at `0x180078b52`
- `USER32!EnableWindow` at `0x180078b6b`
- `USER32!EnableWindow` at `0x180078d01`
- `USER32!EnableWindow` at `0x180078b52`
- `USER32!EnableWindow` at `0x180078b6b`
- `USER32!EnableWindow` at `0x180078d01`
- `USER32!SendMessageW` at `0x180078984`
- `USER32!SendMessageW` at `0x180078a1d`
- `USER32!SendMessageW` at `0x180078b39`
- `USER32!SendMessageW` at `0x180078984`
- `USER32!SendMessageW` at `0x180078a1d`
- `USER32!SendMessageW` at `0x180078b39`
- `USER32!GetDlgItem` at `0x18007895a`
- `USER32!GetDlgItem` at `0x180078ae4`
- `USER32!GetDlgItem` at `0x180078b47`
- `USER32!GetDlgItem` at `0x180078b60`
- `USER32!GetDlgItem` at `0x180078ce9`
- `USER32!GetDlgItem` at `0x180078cf6`
- `USER32!GetDlgItem` at `0x18007895a`
- `USER32!GetDlgItem` at `0x180078ae4`
- `USER32!GetDlgItem` at `0x180078b47`
- `USER32!GetDlgItem` at `0x180078b60`
- `USER32!GetDlgItem` at `0x180078ce9`
- `USER32!GetDlgItem` at `0x180078cf6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800789ec`
- `OLEAUT32!__imp_SysFreeString` at `0x1800789ec`
- `ole32!CoGetActivationState` at `0x180078abe`
- `ole32!CoGetCallState` at `0x180078ac5`
- `UxTheme!SetWindowTheme` at `0x180078afa`
- `UxTheme!SetWindowTheme` at `0x180078afa`

## pseudocode

```c
INT_PTR __fastcall AnalysisDlgProc(HWND a1, int a2, unsigned int a3, __int64 a4)
{
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int WaitChain; // eax
  unsigned int v9; // edx
  unsigned int v10; // r8d
  INT_PTR v11; // r14
  HWND DlgItem; // rax
  HWND v13; // r15
  struct WdcTraceControl *v14; // rbx
  LRESULT v15; // rax
  int v16; // eax
  int v17; // r9d
  int v18; // ebx
  unsigned int v19; // ebx
  struct WdcTraceControl *v20; // rdi
  LRESULT v21; // rax
  int v22; // eax
  HWND v23; // rbx
  LONG_PTR WindowLongPtrW; // rax
  HWND v25; // rax
  HWND v26; // rax
  unsigned int v27; // edx
  unsigned int v28; // r8d
  unsigned int v29; // ebx
  void **v30; // r9
  int ProcessWaitChainAsync; // eax
  LONG_PTR v33; // rax
  int v34; // eax
  int v35; // eax
  HWND v36; // rax
  BOOL v37; // edx
  unsigned int *lpDirectory; // [rsp+20h] [rbp-48h]
  int v39; // [rsp+40h] [rbp-28h] BYREF
  int v40; // [rsp+44h] [rbp-24h] BYREF
  unsigned int v41; // [rsp+48h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-18h] BYREF
  int v43; // [rsp+A8h] [rbp+40h] BYREF

  v43 = 0;
  v39 = 0;
  v41 = -1;
  v40 = 0;
  bstrString = 0;
  v5 = a2 - 78;
  if ( v5 )
  {
    v6 = v5 - 194;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        if ( v7 == 754 )
        {
          WaitChain = OnPostGetWaitChain(
                        (struct _WDC_WCT_PARAM *)qword_1800B5530,
                        *(const unsigned __int16 **)(qword_1800B5510 + 8),
                        *(_DWORD *)(qword_1800B5510 + 24),
                        *(struct WdcTraceControl **)qword_1800B5510,
                        lpDirectory);
          if ( WaitChain < 0 )
          {
            if ( WaitChain != -2147467259 )
              WdcErrorMessage(a1, v9, v10, WaitChain);
            EndDialog(a1, 2);
          }
          CleanupWctSession(&qword_1800B5520, (struct _WDC_WCT_PARAM *)qword_1800B5530);
          return 1;
        }
        return 0;
      }
      v11 = (unsigned __int16)a3;
      if ( (unsigned __int16)a3 == 1 )
      {
        DlgItem = GetDlgItem(a1, 30122);
        v13 = DlgItem;
        if ( DlgItem )
        {
          v14 = *(struct WdcTraceControl **)qword_1800B5510;
          v15 = SendMessageW(DlgItem, 0x110Au, 0, 0);
          if ( (int)TreeView_GetCheckedProcessCount(v13, v15, v14, &v39, &v41, &bstrString, &v40) >= 0 )
          {
            v16 = v39;
            v17 = v40;
          }
          else
          {
            v16 = v11 + 1;
            v17 = 0;
          }
          v18 = WdcConfirmProcessCommand(v13, v16, bstrString, v17, 0x76C0u);
          if ( bstrString )
          {
            SysFreeString(bstrString);
            bstrString = 0;
          }
          if ( v18 )
            return 1;
          v19 = *(_DWORD *)(qword_1800B5510 + 32);
          v20 = *(struct WdcTraceControl **)qword_1800B5510;
          v21 = SendMessageW(v13, 0x110Au, 0, 0);
          v22 = TreeView_KillCheckedProcess(v13, v21, v20, v19);
          if ( (int)(v22 + 0x80000000) >= 0 && v22 != -2147467259 )
            WdcErrorMessage(a1, 0x80000000, a3, v22);
        }
      }
      RmSqmWaitChainUsage(*(_DWORD *)(qword_1800B5510 + 32), *(const unsigned __int16 **)(qword_1800B5510 + 8), a3, v11);
      EndDialog(a1, v11);
      WdcLockObject::LockEnter((WdcLockObject *)&off_1800AE800, &v43);
      qword_1800B5540 = 0;
      WdcLockObject::LockLeave((WdcLockObject *)&off_1800AE800, &v43);
      return 1;
    }
    dword_1800B5518 = 0;
    qword_1800B5510 = a4;
    if ( !dword_1800B5508 )
    {
      RegisterWaitChainCOMCallback(CoGetCallState, CoGetActivationState);
      dword_1800B5508 = 1;
    }
    v23 = GetDlgItem(a1, 30122);
    SetWindowTheme(v23, L"Explorer", 0);
    WindowLongPtrW = GetWindowLongPtrW(v23, -16);
    if ( WindowLongPtrW )
      SetWindowLongPtrW(v23, -16, WindowLongPtrW | 0x100);
    SendMessageW(v23, 0x112Cu, 4u, 4);
    v25 = GetDlgItem(a1, 30124);
    EnableWindow(v25, 0);
    v26 = GetDlgItem(a1, 30122);
    EnableWindow(v26, 0);
    if ( dword_1800B5554 <= 0 )
    {
      WdcLockObject::LockEnter((WdcLockObject *)&off_1800AE800, &v43);
      qword_1800B5540 = (__int64)a1;
      WdcLockObject::LockLeave((WdcLockObject *)&off_1800AE800, &v43);
      CleanupWctSession(&qword_1800B5520, (struct _WDC_WCT_PARAM *)qword_1800B5530);
      ProcessWaitChainAsync = GetProcessWaitChainAsync(
                                *(_DWORD *)(qword_1800B5510 + 28),
                                *(_QWORD *)(qword_1800B5510 + 16),
                                (struct _WDC_WCT_PARAM *)qword_1800B5530,
                                v30);
      v29 = ProcessWaitChainAsync;
      if ( ProcessWaitChainAsync >= 0 )
      {
LABEL_32:
        RmSqmAction(*(_DWORD *)(qword_1800B5510 + 32), 0x76CBu, *(const unsigned __int16 **)(qword_1800B5510 + 8), v29);
        return 1;
      }
      if ( ProcessWaitChainAsync == -2147467259 )
      {
LABEL_31:
        EndDialog(a1, 2);
        goto LABEL_32;
      }
    }
    else
    {
      v29 = -2147023899;
    }
    WdcErrorMessage(a1, v27, v28, v29);
    goto LABEL_31;
  }
  if ( a3 != 30122 )
  {
    if ( a3 == 30102 && a4 && (*(_DWORD *)(a4 + 16) == -4 || *(_DWORD *)(a4 + 16) == -2) && !*(_DWORD *)(a4 + 28) )
      ShellExecuteW(0, L"open", (LPCWSTR)(a4 + 136), 0, 0, 5);
    return 0;
  }
  if ( a4 )
  {
    if ( *(_DWORD *)(a4 + 16) != -419 )
    {
      if ( *(_DWORD *)(a4 + 16) == -12 )
      {
        if ( *(_DWORD *)(a4 + 24) == 1 )
        {
          v33 = 32;
        }
        else if ( *(_DWORD *)(a4 + 24) == 65537 )
        {
          if ( (*(_BYTE *)(a4 + 72) & 1) != 0 )
            *(_DWORD *)(a4 + 80) = 255;
          v33 = 2;
        }
        else
        {
          v33 = 0;
        }
        SetWindowLongPtrW(a1, 0, v33);
        return 1;
      }
      return 0;
    }
    v34 = *(_DWORD *)(a4 + 44) & 0xF000;
    if ( v34 == 4096 )
    {
      if ( (*(_DWORD *)(a4 + 40) & 0xF000) == 0x2000 )
      {
        v35 = dword_1800B5518 + 1;
LABEL_49:
        dword_1800B5518 = v35;
LABEL_54:
        if ( v35 <= 0 )
        {
          v36 = GetDlgItem(a1, 1);
          v37 = 0;
        }
        else
        {
          v36 = GetDlgItem(a1, 1);
          v37 = 1;
        }
        EnableWindow(v36, v37);
        return 0;
      }
    }
    else if ( v34 == 0x2000 && (*(_DWORD *)(a4 + 40) & 0xF000) == 0x1000 )
    {
      v35 = dword_1800B5518 - 1;
      goto LABEL_49;
    }
    v35 = dword_1800B5518;
    goto LABEL_54;
  }
  return 0;
}

```

## disassembly

```asm
0x180078890  push    rbp
0x180078892  push    rbx
0x180078893  push    rsi
0x180078894  push    rdi
0x180078895  push    r14
0x180078897  push    r15
0x180078899  mov     rbp, rsp
0x18007889c  sub     rsp, 68h
0x1800788a0  mov     [rbp+arg_8], 0
0x1800788a7  mov     rsi, rcx
0x1800788aa  mov     [rbp+var_28], 0
0x1800788b1  mov     [rbp+var_20], 0FFFFFFFFh
0x1800788b8  mov     [rbp+var_24], 0
0x1800788bf  mov     [rbp+bstrString], 0
0x1800788c7  sub     edx, 4Eh ; 'N'
0x1800788ca  jz      loc_180078C20
0x1800788d0  sub     edx, 0C2h
0x1800788d6  jz      loc_180078AA4
0x1800788dc  sub     edx, 1
0x1800788df  jz      short loc_180078947
0x1800788e1  cmp     edx, 2F2h
0x1800788e7  jnz     loc_180078D56
0x1800788ed  mov     rdx, cs:qword_1800B5510
0x1800788f4  lea     rcx, qword_1800B5530; struct _WDC_WCT_PARAM *
0x1800788fb  mov     r9, [rdx]; struct WdcTraceControl *
0x1800788fe  mov     r8d, [rdx+18h]; unsigned int
0x180078902  mov     rdx, [rdx+8]; unsigned __int16 *
0x180078906  call    ?OnPostGetWaitChain@@YAJPEAU_WDC_WCT_PARAM@@PEBGIPEAVWdcTraceControl@@PEAK@Z; OnPostGetWaitChain(_WDC_WCT_PARAM *,ushort const *,uint,WdcTraceControl *,ulong *)
0x18007890b  test    eax, eax
0x18007890d  jns     short loc_18007892F
0x18007890f  cmp     eax, 80004005h
0x180078914  jz      short loc_180078921
0x180078916  mov     r9d, eax; int
0x180078919  mov     rcx, rsi; hwndOwner
0x18007891c  call    ?WdcErrorMessage@@YAJPEAUHWND__@@IIJ@Z; WdcErrorMessage(HWND__ *,uint,uint,long)
0x180078921  mov     edx, 2; nResult
0x180078926  mov     rcx, rsi; hDlg
0x180078929  call    cs:__imp_EndDialog
0x18007892f  lea     rdx, qword_1800B5530; struct _WDC_WCT_PARAM *
0x180078936  lea     rcx, qword_1800B5520; void **
0x18007893d  call    ?CleanupWctSession@@YAXPEAPEAXPEAU_WDC_WCT_PARAM@@@Z; CleanupWctSession(void * *,_WDC_WCT_PARAM *)
0x180078942  jmp     loc_180078C16
0x180078947  movzx   r14d, r8w
0x18007894b  cmp     r14d, 1
0x18007894f  jnz     loc_180078A52
0x180078955  mov     edx, 75AAh; nIDDlgItem
0x18007895a  call    cs:__imp_GetDlgItem
0x180078960  mov     r15, rax
0x180078963  test    rax, rax
0x180078966  jz      loc_180078A52
0x18007896c  mov     rcx, cs:qword_1800B5510
0x180078973  xor     r9d, r9d; lParam
0x180078976  xor     r8d, r8d; wParam
0x180078979  mov     edx, 110Ah; Msg
0x18007897e  mov     rbx, [rcx]
0x180078981  mov     rcx, rax; hWnd
0x180078984  call    cs:__imp_SendMessageW
0x18007898a  lea     rcx, [rbp+var_24]
0x18007898e  mov     r8, rbx; struct WdcTraceControl *
0x180078991  mov     [rsp+68h+var_38], rcx; int *
0x180078996  lea     r9, [rbp+var_28]; int *
0x18007899a  lea     rcx, [rbp+bstrString]
0x18007899e  mov     rdx, rax; lParam
0x1800789a1  mov     qword ptr [rsp+68h+nShowCmd], rcx; unsigned __int16 **
0x1800789a6  lea     rcx, [rbp+var_20]
0x1800789aa  mov     [rsp+68h+lpDirectory], rcx; unsigned int *
0x1800789af  mov     rcx, r15; hWnd
0x1800789b2  call    ?TreeView_GetCheckedProcessCount@@YAJPEAUHWND__@@PEAU_TREEITEM@@PEAVWdcTraceControl@@PEAHPEAKPEAPEAG3@Z; TreeView_GetCheckedProcessCount(HWND__ *,_TREEITEM *,WdcTraceControl *,int *,ulong *,ushort * *,int *)
0x1800789b7  test    eax, eax
0x1800789b9  jns     short loc_1800789C4
0x1800789bb  lea     eax, [r14+1]
0x1800789bf  xor     r9d, r9d
0x1800789c2  jmp     short loc_1800789CB
0x1800789c4  mov     eax, [rbp+var_28]
0x1800789c7  mov     r9d, [rbp+var_24]; int
0x1800789cb  mov     r8, [rbp+bstrString]; unsigned __int16 *
0x1800789cf  mov     edx, eax; int
0x1800789d1  mov     rcx, r15; HWND
0x1800789d4  mov     dword ptr [rsp+68h+lpDirectory], 76C0h; unsigned int
0x1800789dc  call    ?WdcConfirmProcessCommand@@YAJPEAUHWND__@@HPEBGHI@Z; WdcConfirmProcessCommand(HWND__ *,int,ushort const *,int,uint)
0x1800789e1  mov     rcx, [rbp+bstrString]; bstrString
0x1800789e5  mov     ebx, eax
0x1800789e7  test    rcx, rcx
0x1800789ea  jz      short loc_1800789FA
0x1800789ec  call    cs:__imp_SysFreeString
0x1800789f2  mov     [rbp+bstrString], 0
0x1800789fa  test    ebx, ebx
0x1800789fc  jnz     loc_180078C16
0x180078a02  mov     rax, cs:qword_1800B5510
0x180078a09  xor     r9d, r9d; lParam
0x180078a0c  xor     r8d, r8d; wParam
0x180078a0f  mov     edx, 110Ah; Msg
0x180078a14  mov     rcx, r15; hWnd
0x180078a17  mov     ebx, [rax+20h]
0x180078a1a  mov     rdi, [rax]
0x180078a1d  call    cs:__imp_SendMessageW
0x180078a23  mov     r9d, ebx; unsigned int
0x180078a26  mov     r8, rdi; struct WdcTraceControl *
0x180078a29  mov     rdx, rax; lParam
0x180078a2c  mov     rcx, r15; hWnd
0x180078a2f  call    ?TreeView_KillCheckedProcess@@YAJPEAUHWND__@@PEAU_TREEITEM@@PEAVWdcTraceControl@@K@Z; TreeView_KillCheckedProcess(HWND__ *,_TREEITEM *,WdcTraceControl *,ulong)
0x180078a34  mov     edx, 80000000h; unsigned int
0x180078a39  lea     ecx, [rax+rdx]
0x180078a3c  test    edx, ecx
0x180078a3e  jnz     short loc_180078A52
0x180078a40  cmp     eax, 80004005h
0x180078a45  jz      short loc_180078A52
0x180078a47  mov     r9d, eax; int
0x180078a4a  mov     rcx, rsi; hwndOwner
0x180078a4d  call    ?WdcErrorMessage@@YAJPEAUHWND__@@IIJ@Z; WdcErrorMessage(HWND__ *,uint,uint,long)
0x180078a52  mov     rcx, cs:qword_1800B5510
0x180078a59  mov     r9d, r14d; unsigned int
0x180078a5c  mov     rdx, [rcx+8]; unsigned __int16 *
0x180078a60  mov     ecx, [rcx+20h]; unsigned int
0x180078a63  call    ?RmSqmWaitChainUsage@@YAJKPEBGKK@Z; RmSqmWaitChainUsage(ulong,ushort const *,ulong,ulong)
0x180078a68  mov     rdx, r14; nResult
0x180078a6b  mov     rcx, rsi; hDlg
0x180078a6e  call    cs:__imp_EndDialog
0x180078a74  lea     rdx, [rbp+arg_8]; int *
0x180078a78  lea     rcx, off_1800AE800; this
0x180078a7f  call    ?LockEnter@WdcLockObject@@QEAAXPEAH@Z; WdcLockObject::LockEnter(int *)
0x180078a84  lea     rdx, [rbp+arg_8]; int *
0x180078a88  mov     cs:qword_1800B5540, 0
0x180078a93  lea     rcx, off_1800AE800; this
0x180078a9a  call    ?LockLeave@WdcLockObject@@QEAAXPEAH@Z; WdcLockObject::LockLeave(int *)
0x180078a9f  jmp     loc_180078C16
0x180078aa4  cmp     cs:dword_1800B5508, 0
0x180078aab  mov     cs:dword_1800B5518, 0
0x180078ab5  mov     cs:qword_1800B5510, r9
0x180078abc  jnz     short loc_180078ADC
0x180078abe  mov     rdx, cs:__imp_CoGetActivationState; ActivationStateCallback
0x180078ac5  mov     rcx, cs:__imp_CoGetCallState; CallStateCallback
0x180078acc  call    cs:__imp_RegisterWaitChainCOMCallback
0x180078ad2  mov     cs:dword_1800B5508, 1
0x180078adc  mov     edx, 75AAh; nIDDlgItem
0x180078ae1  mov     rcx, rsi; hDlg
0x180078ae4  call    cs:__imp_GetDlgItem
0x180078aea  xor     r8d, r8d; pszSubIdList
0x180078aed  lea     rdx, pszSubAppName; "Explorer"
0x180078af4  mov     rcx, rax; hwnd
0x180078af7  mov     rbx, rax
0x180078afa  call    cs:__imp_SetWindowTheme
0x180078b00  mov     edi, 0FFFFFFF0h
0x180078b05  mov     rcx, rbx; hWnd
0x180078b08  mov     edx, edi; nIndex
0x180078b0a  call    cs:__imp_GetWindowLongPtrW
0x180078b10  test    rax, rax
0x180078b13  jz      short loc_180078B28
0x180078b15  bts     rax, 8
0x180078b1a  mov     edx, edi; nIndex
0x180078b1c  mov     r8, rax; dwNewLong
0x180078b1f  mov     rcx, rbx; hWnd
0x180078b22  call    cs:__imp_SetWindowLongPtrW
0x180078b28  mov     r8d, 4; wParam
0x180078b2e  mov     edx, 112Ch; Msg
0x180078b33  mov     r9d, r8d; lParam
0x180078b36  mov     rcx, rbx; hWnd
0x180078b39  call    cs:__imp_SendMessageW
0x180078b3f  mov     edx, 75ACh; nIDDlgItem
0x180078b44  mov     rcx, rsi; hDlg
0x180078b47  call    cs:__imp_GetDlgItem
0x180078b4d  mov     rcx, rax; hWnd
0x180078b50  xor     edx, edx; bEnable
0x180078b52  call    cs:__imp_EnableWindow
0x180078b58  mov     edx, 75AAh; nIDDlgItem
0x180078b5d  mov     rcx, rsi; hDlg
0x180078b60  call    cs:__imp_GetDlgItem
0x180078b66  mov     rcx, rax; hWnd
0x180078b69  xor     edx, edx; bEnable
0x180078b6b  call    cs:__imp_EnableWindow
0x180078b71  cmp     cs:dword_1800B5554, 0
0x180078b78  jle     short loc_180078B81
0x180078b7a  mov     ebx, 800703E5h
0x180078b7f  jmp     short loc_180078BE2
0x180078b81  lea     rdx, [rbp+arg_8]; int *
0x180078b85  lea     rcx, off_1800AE800; this
0x180078b8c  call    ?LockEnter@WdcLockObject@@QEAAXPEAH@Z; WdcLockObject::LockEnter(int *)
0x180078b91  lea     rdx, [rbp+arg_8]; int *
0x180078b95  mov     cs:qword_1800B5540, rsi
0x180078b9c  lea     rcx, off_1800AE800; this
0x180078ba3  call    ?LockLeave@WdcLockObject@@QEAAXPEAH@Z; WdcLockObject::LockLeave(int *)
0x180078ba8  lea     rdx, qword_1800B5530; struct _WDC_WCT_PARAM *
0x180078baf  lea     rcx, qword_1800B5520; void **
0x180078bb6  call    ?CleanupWctSession@@YAXPEAPEAXPEAU_WDC_WCT_PARAM@@@Z; CleanupWctSession(void * *,_WDC_WCT_PARAM *)
0x180078bbb  mov     rcx, cs:qword_1800B5510
0x180078bc2  lea     r8, qword_1800B5530; struct _WDC_WCT_PARAM *
0x180078bc9  mov     rdx, [rcx+10h]; __int64
0x180078bcd  mov     ecx, [rcx+1Ch]; unsigned int
0x180078bd0  call    ?GetProcessWaitChainAsync@@YAJK_JPEAU_WDC_WCT_PARAM@@PEAPEAX@Z; GetProcessWaitChainAsync(ulong,__int64,_WDC_WCT_PARAM *,void * *)
0x180078bd5  mov     ebx, eax
0x180078bd7  test    eax, eax
0x180078bd9  jns     short loc_180078BFB
0x180078bdb  cmp     eax, 80004005h
0x180078be0  jz      short loc_180078BED
0x180078be2  mov     r9d, ebx; int
0x180078be5  mov     rcx, rsi; hwndOwner
0x180078be8  call    ?WdcErrorMessage@@YAJPEAUHWND__@@IIJ@Z; WdcErrorMessage(HWND__ *,uint,uint,long)
0x180078bed  mov     edx, 2; nResult
0x180078bf2  mov     rcx, rsi; hDlg
0x180078bf5  call    cs:__imp_EndDialog
0x180078bfb  mov     rcx, cs:qword_1800B5510
0x180078c02  mov     r9d, ebx; unsigned int
0x180078c05  mov     edx, 76CBh; unsigned int
0x180078c0a  mov     r8, [rcx+8]; unsigned __int16 *
0x180078c0e  mov     ecx, [rcx+20h]; unsigned int
0x180078c11  call    ?RmSqmAction@@YAJKKPEBGK@Z; RmSqmAction(ulong,ulong,ushort const *,ulong)
0x180078c16  mov     eax, 1
0x180078c1b  jmp     loc_180078D58
0x180078c20  cmp     r8d, 75AAh
0x180078c27  jnz     loc_180078D09
0x180078c2d  test    r9, r9
0x180078c30  jz      loc_180078D56
0x180078c36  cmp     dword ptr [r9+10h], 0FFFFFE5Dh
0x180078c3e  jz      short loc_180078C8B
0x180078c40  cmp     dword ptr [r9+10h], 0FFFFFFF4h
0x180078c45  jnz     loc_180078D56
0x180078c4b  mov     ecx, [r9+18h]
0x180078c4f  sub     ecx, 1
0x180078c52  jz      short loc_180078C76
0x180078c54  cmp     ecx, 10000h
0x180078c5a  jz      short loc_180078C60
0x180078c5c  xor     eax, eax
0x180078c5e  jmp     short loc_180078C7B
0x180078c60  test    byte ptr [r9+48h], 1
0x180078c65  jz      short loc_180078C6F
0x180078c67  mov     dword ptr [r9+50h], 0FFh
0x180078c6f  mov     eax, 2
0x180078c74  jmp     short loc_180078C7B
0x180078c76  mov     eax, 20h ; ' '
0x180078c7b  mov     r8, rax; dwNewLong
0x180078c7e  xor     edx, edx; nIndex
0x180078c80  mov     rcx, rsi; hWnd
0x180078c83  call    cs:__imp_SetWindowLongPtrW
0x180078c89  jmp     short loc_180078C16
0x180078c8b  mov     eax, [r9+2Ch]
0x180078c8f  mov     ecx, 0F000h
0x180078c94  and     eax, ecx
0x180078c96  mov     edx, 1000h
0x180078c9b  cmp     eax, edx
0x180078c9d  jnz     short loc_180078CBC
0x180078c9f  mov     eax, [r9+28h]
0x180078ca3  and     eax, ecx
0x180078ca5  cmp     eax, 2000h
0x180078caa  jnz     short loc_180078CD7
0x180078cac  mov     eax, cs:dword_1800B5518
0x180078cb2  inc     eax
0x180078cb4  mov     cs:dword_1800B5518, eax
0x180078cba  jmp     short loc_180078CDD
0x180078cbc  cmp     eax, 2000h
0x180078cc1  jnz     short loc_180078CD7
0x180078cc3  mov     eax, [r9+28h]
0x180078cc7  and     eax, ecx
0x180078cc9  cmp     eax, edx
0x180078ccb  jnz     short loc_180078CD7
0x180078ccd  mov     eax, cs:dword_1800B5518
0x180078cd3  dec     eax
0x180078cd5  jmp     short loc_180078CB4
0x180078cd7  mov     eax, cs:dword_1800B5518
0x180078cdd  mov     edx, 1; nIDDlgItem
0x180078ce2  mov     rcx, rsi; hDlg
0x180078ce5  test    eax, eax
0x180078ce7  jle     short loc_180078CF6
0x180078ce9  call    cs:__imp_GetDlgItem
0x180078cef  mov     edx, 1
0x180078cf4  jmp     short loc_180078CFE
0x180078cf6  call    cs:__imp_GetDlgItem
0x180078cfc  xor     edx, edx; bEnable
0x180078cfe  mov     rcx, rax; hWnd
0x180078d01  call    cs:__imp_EnableWindow
0x180078d07  jmp     short loc_180078D56
0x180078d09  cmp     r8d, 7596h
0x180078d10  jnz     short loc_180078D56
0x180078d12  test    r9, r9
0x180078d15  jz      short loc_180078D56
0x180078d17  cmp     dword ptr [r9+10h], 0FFFFFFFCh
0x180078d1c  jz      short loc_180078D25
0x180078d1e  cmp     dword ptr [r9+10h], 0FFFFFFFEh
0x180078d23  jnz     short loc_180078D56
0x180078d25  cmp     dword ptr [r9+1Ch], 0
0x180078d2a  jnz     short loc_180078D56
0x180078d2c  lea     r8, [r9+88h]; lpFile
0x180078d33  mov     [rsp+68h+nShowCmd], 5; nShowCmd
0x180078d3b  xor     r9d, r9d; lpParameters
0x180078d3e  mov     [rsp+68h+lpDirectory], 0; lpDirectory
0x180078d47  lea     rdx, Operation; "open"
0x180078d4e  xor     ecx, ecx; hwnd
0x180078d50  call    cs:__imp_ShellExecuteW
0x180078d56  xor     eax, eax
0x180078d58  add     rsp, 68h
0x180078d5c  pop     r15
0x180078d5e  pop     r14
0x180078d60  pop     rdi
0x180078d61  pop     rsi
0x180078d62  pop     rbx
0x180078d63  pop     rbp
0x180078d64  retn
```
