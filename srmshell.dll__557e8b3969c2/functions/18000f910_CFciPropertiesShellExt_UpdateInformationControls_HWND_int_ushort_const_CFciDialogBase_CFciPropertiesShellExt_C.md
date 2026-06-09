# CFciPropertiesShellExt::UpdateInformationControls(HWND__ *,int,ushort const *,CFciDialogBase<CFciPropertiesShellExt>::ControlState,CFciDialogBase<CFciPropertiesShellExt>::ControlState)

- ea: `0x18000f910`
- end: `0x18000fa85`
- name: `?UpdateInformationControls@CFciPropertiesShellExt@@CAXPEAUHWND__@@HPEBGW4ControlState@?$CFciDialogBase@VCFciPropertiesShellExt@@@@2@Z`
- size: `373`
- prototype: `int __fastcall(HWND hDlg, UINT, __int64, int, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000baf0`
- `0x18000e87c`
- `0x18000fa8c`

## callees

- `0x18000a87c`
- `0x18000f910`
- `0x18001161c`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000f9b4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f9b4`
- `USER32!DestroyIcon` at `0x18000f975`
- `USER32!DestroyIcon` at `0x18000f975`
- `USER32!GetDlgItem` at `0x18000f951`
- `USER32!GetDlgItem` at `0x18000f9c5`
- `USER32!GetDlgItem` at `0x18000f9de`
- `USER32!GetDlgItem` at `0x18000f9f8`
- `USER32!GetDlgItem` at `0x18000fa39`
- `USER32!GetDlgItem` at `0x18000f951`
- `USER32!GetDlgItem` at `0x18000f9c5`
- `USER32!GetDlgItem` at `0x18000f9de`
- `USER32!GetDlgItem` at `0x18000f9f8`
- `USER32!GetDlgItem` at `0x18000fa39`
- `USER32!ShowWindow` at `0x18000f9d0`
- `USER32!ShowWindow` at `0x18000f9ea`
- `USER32!ShowWindow` at `0x18000fa2b`
- `USER32!ShowWindow` at `0x18000fa72`
- `USER32!ShowWindow` at `0x18000f9d0`
- `USER32!ShowWindow` at `0x18000f9ea`
- `USER32!ShowWindow` at `0x18000fa2b`
- `USER32!ShowWindow` at `0x18000fa72`
- `USER32!SetDlgItemTextW` at `0x18000f9a8`
- `USER32!SetDlgItemTextW` at `0x18000f9a8`
- `USER32!SendMessageW` at `0x18000f967`
- `USER32!SendMessageW` at `0x18000f967`
- `USER32!EnableWindow` at `0x18000fa17`
- `USER32!EnableWindow` at `0x18000fa5e`
- `USER32!EnableWindow` at `0x18000fa17`
- `USER32!EnableWindow` at `0x18000fa5e`

## pseudocode

```c
int __fastcall CFciPropertiesShellExt::UpdateInformationControls(HWND hDlg, UINT a2, __int64 a3, int a4, int a5)
{
  int v8; // ebp
  int v9; // r14d
  HWND DlgItem; // rax
  HICON v11; // rax
  HWND v12; // rax
  HWND v13; // rax
  HWND v14; // rax
  HWND v15; // rdi
  int v16; // ebx
  BOOL v17; // edx
  int v18; // edx
  HWND v19; // rax
  HWND v20; // rbx
  BOOL v21; // edx
  int v22; // edx
  WPARAM wParam; // [rsp+70h] [rbp+18h] BYREF

  v8 = 0;
  v9 = 0;
  if ( a3 )
  {
    wParam = 0;
    if ( (int)IsolationAwareLoadIconMetric(hDlg, a3, a3, &wParam) >= 0 )
    {
      DlgItem = GetDlgItem(hDlg, 1010);
      v11 = (HICON)SendMessageW(DlgItem, 0x170u, wParam, 0);
      if ( v11 )
        DestroyIcon(v11);
      v8 = 5;
    }
  }
  if ( a2 )
  {
    wParam = 0;
    CSrmComBSTR::LoadStringW((BSTR *)&wParam, off_18002B230, a2);
    SetDlgItemTextW(hDlg, 1011, (LPCWSTR)wParam);
    SysFreeString((BSTR)wParam);
    v9 = 5;
  }
  v12 = GetDlgItem(hDlg, 1010);
  ShowWindow(v12, v8);
  v13 = GetDlgItem(hDlg, 1011);
  ShowWindow(v13, v9);
  v14 = GetDlgItem(hDlg, 1007);
  v15 = v14;
  if ( a4 )
  {
    v16 = a4 - 1;
    if ( v16 )
    {
      if ( v16 != 1 )
        goto LABEL_16;
      v17 = 1;
    }
    else
    {
      v17 = 0;
    }
    EnableWindow(v14, v17);
    v18 = 5;
  }
  else
  {
    v18 = 0;
  }
  ShowWindow(v15, v18);
LABEL_16:
  v19 = GetDlgItem(hDlg, 1012);
  v20 = v19;
  switch ( a5 )
  {
    case 0:
      v22 = 0;
      goto LABEL_23;
    case 1:
      v21 = 0;
      goto LABEL_20;
    case 2:
      v21 = 1;
LABEL_20:
      EnableWindow(v19, v21);
      v22 = 5;
LABEL_23:
      LODWORD(v19) = ShowWindow(v20, v22);
      break;
  }
  return (int)v19;
}

```

## disassembly

```asm
0x18000f910  push    rbx
0x18000f912  push    rbp
0x18000f913  push    rsi
0x18000f914  push    rdi
0x18000f915  push    r14
0x18000f917  push    r15
0x18000f919  sub     rsp, 28h
0x18000f91d  mov     ebx, r9d
0x18000f920  mov     edi, edx
0x18000f922  mov     rsi, rcx
0x18000f925  xor     ebp, ebp
0x18000f927  xor     r14d, r14d
0x18000f92a  lea     r15d, [rbp+5]
0x18000f92e  test    r8, r8
0x18000f931  jz      short loc_18000F97E
0x18000f933  mov     [rsp+58h+wParam], rbp
0x18000f938  lea     r9, [rsp+58h+wParam]
0x18000f93d  mov     rdx, r8
0x18000f940  call    IsolationAwareLoadIconMetric
0x18000f945  test    eax, eax
0x18000f947  js      short loc_18000F97E
0x18000f949  mov     edx, 3F2h; nIDDlgItem
0x18000f94e  mov     rcx, rsi; hDlg
0x18000f951  call    cs:__imp_GetDlgItem
0x18000f957  xor     r9d, r9d; lParam
0x18000f95a  mov     r8, [rsp+58h+wParam]; wParam
0x18000f95f  mov     edx, 170h; Msg
0x18000f964  mov     rcx, rax; hWnd
0x18000f967  call    cs:__imp_SendMessageW
0x18000f96d  test    rax, rax
0x18000f970  jz      short loc_18000F97B
0x18000f972  mov     rcx, rax; hIcon
0x18000f975  call    cs:__imp_DestroyIcon
0x18000f97b  mov     ebp, r15d
0x18000f97e  test    edi, edi
0x18000f980  jz      short loc_18000F9BD
0x18000f982  mov     [rsp+58h+wParam], r14
0x18000f987  mov     r8d, edi; unsigned int
0x18000f98a  mov     rdx, cs:off_18002B230; HINSTANCE
0x18000f991  lea     rcx, [rsp+58h+wParam]; this
0x18000f996  call    ?LoadStringW@CSrmComBSTR@@QEAA_NPEAUHINSTANCE__@@I@Z; CSrmComBSTR::LoadStringW(HINSTANCE__ *,uint)
0x18000f99b  mov     r8, [rsp+58h+wParam]; lpString
0x18000f9a0  mov     edx, 3F3h; nIDDlgItem
0x18000f9a5  mov     rcx, rsi; hDlg
0x18000f9a8  call    cs:__imp_SetDlgItemTextW
0x18000f9ae  nop
0x18000f9af  mov     rcx, [rsp+58h+wParam]; bstrString
0x18000f9b4  call    cs:__imp_SysFreeString
0x18000f9ba  mov     r14d, r15d
0x18000f9bd  mov     edx, 3F2h; nIDDlgItem
0x18000f9c2  mov     rcx, rsi; hDlg
0x18000f9c5  call    cs:__imp_GetDlgItem
0x18000f9cb  mov     edx, ebp; nCmdShow
0x18000f9cd  mov     rcx, rax; hWnd
0x18000f9d0  call    cs:__imp_ShowWindow
0x18000f9d6  mov     edx, 3F3h; nIDDlgItem
0x18000f9db  mov     rcx, rsi; hDlg
0x18000f9de  call    cs:__imp_GetDlgItem
0x18000f9e4  mov     edx, r14d; nCmdShow
0x18000f9e7  mov     rcx, rax; hWnd
0x18000f9ea  call    cs:__imp_ShowWindow
0x18000f9f0  mov     edx, 3EFh; nIDDlgItem
0x18000f9f5  mov     rcx, rsi; hDlg
0x18000f9f8  call    cs:__imp_GetDlgItem
0x18000f9fe  mov     rdi, rax
0x18000fa01  mov     ebp, 1
0x18000fa06  test    ebx, ebx
0x18000fa08  jz      short loc_18000FA26
0x18000fa0a  sub     ebx, ebp
0x18000fa0c  jz      short loc_18000FA22
0x18000fa0e  cmp     ebx, ebp
0x18000fa10  jnz     short loc_18000FA31
0x18000fa12  mov     edx, ebp; bEnable
0x18000fa14  mov     rcx, rdi; hWnd
0x18000fa17  call    cs:__imp_EnableWindow
0x18000fa1d  mov     edx, r15d
0x18000fa20  jmp     short loc_18000FA28
0x18000fa22  xor     edx, edx
0x18000fa24  jmp     short loc_18000FA14
0x18000fa26  xor     edx, edx; nCmdShow
0x18000fa28  mov     rcx, rdi; hWnd
0x18000fa2b  call    cs:__imp_ShowWindow
0x18000fa31  mov     edx, 3F4h; nIDDlgItem
0x18000fa36  mov     rcx, rsi; hDlg
0x18000fa39  call    cs:__imp_GetDlgItem
0x18000fa3f  mov     rbx, rax
0x18000fa42  mov     r8d, [rsp+58h+arg_20]
0x18000fa4a  test    r8d, r8d
0x18000fa4d  jz      short loc_18000FA6D
0x18000fa4f  sub     r8d, ebp
0x18000fa52  jz      short loc_18000FA69
0x18000fa54  cmp     r8d, ebp
0x18000fa57  jnz     short loc_18000FA78
0x18000fa59  mov     edx, ebp; bEnable
0x18000fa5b  mov     rcx, rbx; hWnd
0x18000fa5e  call    cs:__imp_EnableWindow
0x18000fa64  mov     edx, r15d
0x18000fa67  jmp     short loc_18000FA6F
0x18000fa69  xor     edx, edx
0x18000fa6b  jmp     short loc_18000FA5B
0x18000fa6d  xor     edx, edx; nCmdShow
0x18000fa6f  mov     rcx, rbx; hWnd
0x18000fa72  call    cs:__imp_ShowWindow
0x18000fa78  add     rsp, 28h
0x18000fa7c  pop     r15
0x18000fa7e  pop     r14
0x18000fa80  pop     rdi
0x18000fa81  pop     rsi
0x18000fa82  pop     rbp
0x18000fa83  pop     rbx
0x18000fa84  retn
```
