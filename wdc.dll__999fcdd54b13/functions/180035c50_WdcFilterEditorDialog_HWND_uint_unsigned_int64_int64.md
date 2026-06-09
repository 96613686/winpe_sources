# WdcFilterEditorDialog(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180035c50`
- end: `0x180035fc8`
- name: `?WdcFilterEditorDialog@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `888`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x18000b854`
- `0x18002ac84`
- `0x18002fafc`
- `0x180035c50`
- `0x180045648`
- `0x1800458bc`

## import_xrefs

- `GDI32!DeleteObject` at `0x180035fb1`
- `GDI32!DeleteObject` at `0x180035fb1`
- `GDI32!CreateFontIndirectW` at `0x180035e1f`
- `GDI32!CreateFontIndirectW` at `0x180035e1f`
- `GDI32!GetDeviceCaps` at `0x180035df8`
- `GDI32!GetDeviceCaps` at `0x180035df8`
- `KERNEL32!GetLastError` at `0x180035e76`
- `KERNEL32!GetLastError` at `0x180035ebb`
- `KERNEL32!GetLastError` at `0x180035f6c`
- `KERNEL32!GetLastError` at `0x180035e76`
- `KERNEL32!GetLastError` at `0x180035ebb`
- `KERNEL32!GetLastError` at `0x180035f6c`
- `USER32!GetDC` at `0x180035dea`
- `USER32!GetDC` at `0x180035dea`
- `USER32!CheckDlgButton` at `0x180035e65`
- `USER32!CheckDlgButton` at `0x180035eb1`
- `USER32!CheckDlgButton` at `0x180035f62`
- `USER32!CheckDlgButton` at `0x180035e65`
- `USER32!CheckDlgButton` at `0x180035eb1`
- `USER32!CheckDlgButton` at `0x180035f62`
- `USER32!IsDlgButtonChecked` at `0x180035d95`
- `USER32!IsDlgButtonChecked` at `0x180035d95`
- `USER32!EndDialog` at `0x180035da3`
- `USER32!EndDialog` at `0x180035da3`
- `USER32!GetWindowLongPtrW` at `0x180035cd7`
- `USER32!GetWindowLongPtrW` at `0x180035d55`
- `USER32!GetWindowLongPtrW` at `0x180035f9d`
- `USER32!GetWindowLongPtrW` at `0x180035cd7`
- `USER32!GetWindowLongPtrW` at `0x180035d55`
- `USER32!GetWindowLongPtrW` at `0x180035f9d`
- `USER32!SetWindowLongPtrW` at `0x180035dca`
- `USER32!SetWindowLongPtrW` at `0x180035e38`
- `USER32!SetWindowLongPtrW` at `0x180035dca`
- `USER32!SetWindowLongPtrW` at `0x180035e38`
- `USER32!EnableWindow` at `0x180035f2a`
- `USER32!EnableWindow` at `0x180035f2a`
- `USER32!SendMessageW` at `0x180035ddd`
- `USER32!SendMessageW` at `0x180035e53`
- `USER32!SendMessageW` at `0x180035ddd`
- `USER32!SendMessageW` at `0x180035e53`
- `USER32!GetDlgItem` at `0x180035cf0`
- `USER32!GetDlgItem` at `0x180035d66`
- `USER32!GetDlgItem` at `0x180035db6`
- `USER32!GetDlgItem` at `0x180035ef7`
- `USER32!GetDlgItem` at `0x180035f1f`
- `USER32!GetDlgItem` at `0x180035cf0`
- `USER32!GetDlgItem` at `0x180035d66`
- `USER32!GetDlgItem` at `0x180035db6`
- `USER32!GetDlgItem` at `0x180035ef7`
- `USER32!GetDlgItem` at `0x180035f1f`
- `OLEAUT32!__imp_VariantInit` at `0x180035c7a`
- `OLEAUT32!__imp_VariantInit` at `0x180035c7a`

## pseudocode

```c
__int64 __fastcall WdcFilterEditorDialog(HWND hWnd, int a2, int a3, LONG_PTR a4)
{
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  LONG_PTR v11; // rsi
  HWND v12; // rax
  signed int LastError; // eax
  __int64 v14; // rdx
  LONG_PTR v15; // rbx
  HWND v16; // rax
  INT_PTR v17; // rdx
  HWND DlgItem; // rbx
  HDC DC; // rax
  BOOL v20; // ebx
  bool v21; // sf
  bool v22; // sf
  __int64 v23; // rdx
  HWND v24; // rax
  HWND v25; // rax
  bool v26; // sf
  LONG_PTR WindowLongPtrW; // rdi
  void *v28; // rcx
  VARIANTARG pvarg; // [rsp+30h] [rbp-48h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v8 = a2 - 2;
  if ( !v8 )
  {
    WindowLongPtrW = GetWindowLongPtrW(hWnd, -21);
    v28 = *(void **)(WindowLongPtrW + 16);
    if ( v28 )
    {
      DeleteObject(v28);
      *(_QWORD *)(WindowLongPtrW + 16) = 0;
    }
    return 0;
  }
  v9 = v8 - 14;
  if ( !v9 )
    goto LABEL_45;
  v10 = v9 - 256;
  if ( !v10 )
  {
    DlgItem = GetDlgItem(hWnd, 4206);
    SetWindowLongPtrW(hWnd, -21, a4);
    *(_QWORD *)(a4 + 16) = SendMessageW(DlgItem, 0x31u, 0, 0);
    DC = GetDC(DlgItem);
    g_HexEditFont.lfHeight = -10 * GetDeviceCaps(DC, 90) / 72;
    *(_QWORD *)(a4 + 24) = CreateFontIndirectW(&g_HexEditFont);
    *(_QWORD *)(a4 + 72) = SetWindowLongPtrW(DlgItem, -4, (LONG_PTR)WdcFilterEditorWindow);
    SendMessageW(DlgItem, 0xC5u, 0x200u, 0);
    v20 = 0;
    if ( !CheckDlgButton(hWnd, 4202, *(_DWORD *)(a4 + 4)) )
    {
      LastError = GetLastError();
      v21 = LastError < 0;
      if ( !LastError )
        goto LABEL_37;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v21 = LastError < 0;
      }
      if ( v21 )
        goto LABEL_38;
    }
    *(_DWORD *)(a4 + 12) = 2;
    if ( *(_DWORD *)(a4 + 32) )
    {
      if ( !CheckDlgButton(hWnd, 4205, 1u) )
      {
        LastError = GetLastError();
        v26 = LastError < 0;
        if ( !LastError )
          goto LABEL_37;
        if ( LastError > 0 )
        {
          LastError = (unsigned __int16)LastError | 0x80070000;
          v26 = LastError < 0;
        }
        if ( v26 )
          goto LABEL_38;
      }
      v23 = 2;
LABEL_34:
      LastError = WdcFilterEditorSetFormat(hWnd, v23);
      if ( LastError < 0 )
        goto LABEL_38;
      pvarg.vt = 3;
      pvarg.lVal = *(_DWORD *)(a4 + 64);
      v24 = GetDlgItem(hWnd, 4201);
      LastError = WdcNumericEditorSetup(v24, &pvarg, 0);
      if ( LastError < 0 )
        goto LABEL_38;
      LOBYTE(v20) = *(_DWORD *)(a4 + 8) == 0;
      v25 = GetDlgItem(hWnd, 1);
      EnableWindow(v25, v20);
      return 0;
    }
    if ( CheckDlgButton(hWnd, 4203, 1u) )
    {
LABEL_33:
      v23 = 0;
      goto LABEL_34;
    }
    LastError = GetLastError();
    v22 = LastError < 0;
    if ( LastError )
    {
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v22 = LastError < 0;
      }
      if ( v22 )
        goto LABEL_38;
      goto LABEL_33;
    }
LABEL_37:
    LastError = -2147467259;
LABEL_38:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\dialogs.cpp",
      "WdcFilterEditorDialog",
      0,
      L"FAILURE: 0x%08x",
      LastError);
    return 0;
  }
  if ( v10 != 1 )
    return 0;
  if ( HIWORD(a3) )
  {
    if ( a3 != 67113070 )
      return 0;
    v11 = GetWindowLongPtrW(hWnd, -21);
    if ( *(_DWORD *)(v11 + 12) != 2 )
      return 0;
    v12 = GetDlgItem(hWnd, 4206);
    LastError = WdcFilterEditorLoad(v12, (struct _WDC_FILTER_EDITOR *)v11);
    goto LABEL_9;
  }
  switch ( (unsigned __int16)a3 )
  {
    case 1u:
      v15 = GetWindowLongPtrW(hWnd, -21);
      v16 = GetDlgItem(hWnd, 4201);
      WdcNumericEditorGetValue(v16, &pvarg);
      *(_DWORD *)(v15 + 64) = pvarg.lVal;
      WdcFilterEditorSetFormat(hWnd, 2);
      *(_DWORD *)(v15 + 4) = IsDlgButtonChecked(hWnd, 4202);
      v17 = 0;
LABEL_21:
      EndDialog(hWnd, v17);
      return 0;
    case 2u:
LABEL_45:
      v17 = 1223;
      goto LABEL_21;
    case 0x106Bu:
      v14 = 0;
      break;
    case 0x106Cu:
      v14 = 1;
      break;
    case 0x106Du:
      v14 = 2;
      break;
    default:
      return 0;
  }
  LastError = WdcFilterEditorSetFormat(hWnd, v14);
LABEL_9:
  if ( LastError < 0 )
    goto LABEL_38;
  return 0;
}

```

## disassembly

```asm
0x180035c50  push    rbx
0x180035c52  push    rbp
0x180035c53  push    rsi
0x180035c54  push    rdi
0x180035c55  push    r14
0x180035c57  sub     rsp, 50h
0x180035c5b  mov     rdi, rcx
0x180035c5e  xorps   xmm0, xmm0
0x180035c61  xor     eax, eax
0x180035c63  lea     rcx, [rsp+78h+pvarg]; pvarg
0x180035c68  movups  xmmword ptr [rsp+78h+pvarg], xmm0
0x180035c6d  mov     qword ptr [rsp+78h+pvarg+10h], rax
0x180035c72  mov     rsi, r9
0x180035c75  mov     rbp, r8
0x180035c78  mov     ebx, edx
0x180035c7a  call    cs:__imp_VariantInit
0x180035c80  sub     ebx, 2
0x180035c83  jz      loc_180035F95
0x180035c89  sub     ebx, 0Eh
0x180035c8c  jz      loc_180035F8B
0x180035c92  sub     ebx, 100h
0x180035c98  jz      loc_180035DAE
0x180035c9e  cmp     ebx, 1
0x180035ca1  jnz     loc_180035FBB
0x180035ca7  mov     rax, rbp
0x180035caa  shr     rax, 10h
0x180035cae  test    ax, ax
0x180035cb1  jz      short loc_180035D0E
0x180035cb3  mov     ecx, 400h
0x180035cb8  cmp     ax, cx
0x180035cbb  jnz     loc_180035FBB
0x180035cc1  mov     r14d, 106Eh
0x180035cc7  cmp     bp, r14w
0x180035ccb  jnz     loc_180035FBB
0x180035cd1  lea     edx, [rbx-16h]; nIndex
0x180035cd4  mov     rcx, rdi; hWnd
0x180035cd7  call    cs:__imp_GetWindowLongPtrW
0x180035cdd  mov     rsi, rax
0x180035ce0  cmp     dword ptr [rax+0Ch], 2
0x180035ce4  jnz     loc_180035FBB
0x180035cea  mov     edx, r14d; nIDDlgItem
0x180035ced  mov     rcx, rdi; hDlg
0x180035cf0  call    cs:__imp_GetDlgItem
0x180035cf6  mov     rcx, rax; hWnd
0x180035cf9  mov     rdx, rsi; struct _WDC_FILTER_EDITOR *
0x180035cfc  call    ?WdcFilterEditorLoad@@YAJPEAUHWND__@@PEAU_WDC_FILTER_EDITOR@@@Z; WdcFilterEditorLoad(HWND__ *,_WDC_FILTER_EDITOR *)
0x180035d01  test    eax, eax
0x180035d03  jns     loc_180035FBB
0x180035d09  jmp     loc_180035F3A
0x180035d0e  movzx   ecx, bp
0x180035d11  sub     ecx, 1
0x180035d14  jz      short loc_180035D4D
0x180035d16  sub     ecx, 1
0x180035d19  jz      loc_180035F8B
0x180035d1f  sub     ecx, 1069h
0x180035d25  jz      short loc_180035D41
0x180035d27  sub     ecx, 1
0x180035d2a  jz      short loc_180035D3A
0x180035d2c  cmp     ecx, 1
0x180035d2f  jnz     loc_180035FBB
0x180035d35  lea     edx, [rcx+1]
0x180035d38  jmp     short loc_180035D43
0x180035d3a  mov     edx, 1
0x180035d3f  jmp     short loc_180035D43
0x180035d41  xor     edx, edx
0x180035d43  mov     rcx, rdi
0x180035d46  call    ?WdcFilterEditorSetFormat@@YAJPEAUHWND__@@W4WDC_FORMAT@@@Z; WdcFilterEditorSetFormat(HWND__ *,WDC_FORMAT)
0x180035d4b  jmp     short loc_180035D01
0x180035d4d  mov     edx, 0FFFFFFEBh; nIndex
0x180035d52  mov     rcx, rdi; hWnd
0x180035d55  call    cs:__imp_GetWindowLongPtrW
0x180035d5b  mov     edx, 1069h; nIDDlgItem
0x180035d60  mov     rcx, rdi; hDlg
0x180035d63  mov     rbx, rax
0x180035d66  call    cs:__imp_GetDlgItem
0x180035d6c  mov     rcx, rax; hWnd
0x180035d6f  lea     rdx, [rsp+78h+pvarg]; pvarSrc
0x180035d74  call    ?WdcNumericEditorGetValue@@YAJPEAUHWND__@@PEAUtagVARIANT@@@Z; WdcNumericEditorGetValue(HWND__ *,tagVARIANT *)
0x180035d79  mov     ecx, dword ptr [rsp+78h+pvarg+8]
0x180035d7d  mov     edx, 2
0x180035d82  mov     [rbx+40h], ecx
0x180035d85  mov     rcx, rdi
0x180035d88  call    ?WdcFilterEditorSetFormat@@YAJPEAUHWND__@@W4WDC_FORMAT@@@Z; WdcFilterEditorSetFormat(HWND__ *,WDC_FORMAT)
0x180035d8d  mov     edx, 106Ah; nIDButton
0x180035d92  mov     rcx, rdi; hDlg
0x180035d95  call    cs:__imp_IsDlgButtonChecked
0x180035d9b  mov     [rbx+4], eax
0x180035d9e  xor     edx, edx; nResult
0x180035da0  mov     rcx, rdi; hDlg
0x180035da3  call    cs:__imp_EndDialog
0x180035da9  jmp     loc_180035FBB
0x180035dae  mov     edx, 106Eh; nIDDlgItem
0x180035db3  mov     rcx, rdi; hDlg
0x180035db6  call    cs:__imp_GetDlgItem
0x180035dbc  mov     r8, rsi; dwNewLong
0x180035dbf  mov     edx, 0FFFFFFEBh; nIndex
0x180035dc4  mov     rcx, rdi; hWnd
0x180035dc7  mov     rbx, rax
0x180035dca  call    cs:__imp_SetWindowLongPtrW
0x180035dd0  xor     r9d, r9d; lParam
0x180035dd3  xor     r8d, r8d; wParam
0x180035dd6  mov     rcx, rbx; hWnd
0x180035dd9  lea     edx, [r9+31h]; Msg
0x180035ddd  call    cs:__imp_SendMessageW
0x180035de3  mov     rcx, rbx; hWnd
0x180035de6  mov     [rsi+10h], rax
0x180035dea  call    cs:__imp_GetDC
0x180035df0  mov     rcx, rax; hdc
0x180035df3  mov     edx, 5Ah ; 'Z'; index
0x180035df8  call    cs:__imp_GetDeviceCaps
0x180035dfe  imul    ecx, eax, -0Ah
0x180035e01  mov     eax, 38E38E39h
0x180035e06  imul    ecx
0x180035e08  lea     rcx, ?g_HexEditFont@@3UtagLOGFONTW@@A; lplf
0x180035e0f  sar     edx, 4
0x180035e12  mov     eax, edx
0x180035e14  shr     eax, 1Fh
0x180035e17  add     edx, eax
0x180035e19  mov     cs:?g_HexEditFont@@3UtagLOGFONTW@@A.lfHeight, edx; tagLOGFONTW g_HexEditFont ...
0x180035e1f  call    cs:__imp_CreateFontIndirectW
0x180035e25  lea     r8, ?WdcFilterEditorWindow@@YA_JPEAUHWND__@@I_K_J@Z; dwNewLong
0x180035e2c  mov     edx, 0FFFFFFFCh; nIndex
0x180035e31  mov     rcx, rbx; hWnd
0x180035e34  mov     [rsi+18h], rax
0x180035e38  call    cs:__imp_SetWindowLongPtrW
0x180035e3e  xor     r9d, r9d; lParam
0x180035e41  mov     edx, 0C5h; Msg
0x180035e46  mov     r8d, 200h; wParam
0x180035e4c  mov     [rsi+48h], rax
0x180035e50  mov     rcx, rbx; hWnd
0x180035e53  call    cs:__imp_SendMessageW
0x180035e59  mov     r8d, [rsi+4]; uCheck
0x180035e5d  mov     edx, 106Ah; nIDButton
0x180035e62  mov     rcx, rdi; hDlg
0x180035e65  call    cs:__imp_CheckDlgButton
0x180035e6b  xor     ebx, ebx
0x180035e6d  mov     ebp, 80070000h
0x180035e72  test    eax, eax
0x180035e74  jnz     short loc_180035E93
0x180035e76  call    cs:__imp_GetLastError
0x180035e7c  test    eax, eax
0x180035e7e  jz      loc_180035F35
0x180035e84  jle     short loc_180035E8D
0x180035e86  movzx   eax, ax
0x180035e89  or      eax, ebp
0x180035e8b  test    eax, eax
0x180035e8d  js      loc_180035F3A
0x180035e93  mov     r8d, 1; uCheck
0x180035e99  mov     dword ptr [rsi+0Ch], 2
0x180035ea0  mov     rcx, rdi; hDlg
0x180035ea3  cmp     [rsi+20h], ebx
0x180035ea6  jnz     loc_180035F5D
0x180035eac  mov     edx, 106Bh; nIDButton
0x180035eb1  call    cs:__imp_CheckDlgButton
0x180035eb7  test    eax, eax
0x180035eb9  jnz     short loc_180035ED0
0x180035ebb  call    cs:__imp_GetLastError
0x180035ec1  test    eax, eax
0x180035ec3  jz      short loc_180035F35
0x180035ec5  jle     short loc_180035ECE
0x180035ec7  movzx   eax, ax
0x180035eca  or      eax, ebp
0x180035ecc  test    eax, eax
0x180035ece  js      short loc_180035F3A
0x180035ed0  xor     edx, edx
0x180035ed2  mov     rcx, rdi
0x180035ed5  call    ?WdcFilterEditorSetFormat@@YAJPEAUHWND__@@W4WDC_FORMAT@@@Z; WdcFilterEditorSetFormat(HWND__ *,WDC_FORMAT)
0x180035eda  test    eax, eax
0x180035edc  js      short loc_180035F3A
0x180035ede  mov     eax, 3
0x180035ee3  mov     edx, 1069h; nIDDlgItem
0x180035ee8  mov     word ptr [rsp+78h+pvarg], ax
0x180035eed  mov     rcx, rdi; hDlg
0x180035ef0  mov     eax, [rsi+40h]
0x180035ef3  mov     dword ptr [rsp+78h+pvarg+8], eax
0x180035ef7  call    cs:__imp_GetDlgItem
0x180035efd  xor     r8d, r8d; int
0x180035f00  lea     rdx, [rsp+78h+pvarg]; struct tagVARIANT *
0x180035f05  mov     rcx, rax; hWnd
0x180035f08  call    ?WdcNumericEditorSetup@@YAJPEAUHWND__@@PEAUtagVARIANT@@H@Z; WdcNumericEditorSetup(HWND__ *,tagVARIANT *,int)
0x180035f0d  test    eax, eax
0x180035f0f  js      short loc_180035F3A
0x180035f11  cmp     [rsi+8], ebx
0x180035f14  mov     edx, 1; nIDDlgItem
0x180035f19  mov     rcx, rdi; hDlg
0x180035f1c  setz    bl
0x180035f1f  call    cs:__imp_GetDlgItem
0x180035f25  mov     rcx, rax; hWnd
0x180035f28  mov     edx, ebx; bEnable
0x180035f2a  call    cs:__imp_EnableWindow
0x180035f30  jmp     loc_180035FBB
0x180035f35  mov     eax, 80004005h
0x180035f3a  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180035f41  mov     [rsp+78h+var_58], eax
0x180035f45  xor     r8d, r8d; int
0x180035f48  lea     rdx, aWdcfilteredito_5; "WdcFilterEditorDialog"
0x180035f4f  lea     rcx, aBaseDiagnosisP_28; "base\\diagnosis\\pdui\\perfmon\\mmc\\di"...
0x180035f56  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180035f5b  jmp     short loc_180035FBB
0x180035f5d  mov     edx, 106Dh; nIDButton
0x180035f62  call    cs:__imp_CheckDlgButton
0x180035f68  test    eax, eax
0x180035f6a  jnz     short loc_180035F81
0x180035f6c  call    cs:__imp_GetLastError
0x180035f72  test    eax, eax
0x180035f74  jz      short loc_180035F35
0x180035f76  jle     short loc_180035F7F
0x180035f78  movzx   eax, ax
0x180035f7b  or      eax, ebp
0x180035f7d  test    eax, eax
0x180035f7f  js      short loc_180035F3A
0x180035f81  mov     edx, 2
0x180035f86  jmp     loc_180035ED2
0x180035f8b  mov     edx, 4C7h
0x180035f90  jmp     loc_180035DA0
0x180035f95  mov     edx, 0FFFFFFEBh; nIndex
0x180035f9a  mov     rcx, rdi; hWnd
0x180035f9d  call    cs:__imp_GetWindowLongPtrW
0x180035fa3  xor     ebx, ebx
0x180035fa5  mov     rdi, rax
0x180035fa8  mov     rcx, [rax+10h]; ho
0x180035fac  test    rcx, rcx
0x180035faf  jz      short loc_180035FBB
0x180035fb1  call    cs:__imp_DeleteObject
0x180035fb7  mov     [rdi+10h], rbx
0x180035fbb  xor     eax, eax
0x180035fbd  add     rsp, 50h
0x180035fc1  pop     r14
0x180035fc3  pop     rdi
0x180035fc4  pop     rsi
0x180035fc5  pop     rbp
0x180035fc6  pop     rbx
0x180035fc7  retn
```
