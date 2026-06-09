# WdcConnectingCallback(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180034dd0`
- end: `0x180035092`
- name: `?WdcConnectingCallback@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `706`
- prototype: `__int64 __fastcall(HWND hDlg, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b7d0`
- `0x18000b854`
- `0x180034dd0`

## import_xrefs

- `KERNEL32!CancelSynchronousIo` at `0x18003504b`
- `KERNEL32!CancelSynchronousIo` at `0x18003504b`
- `KERNEL32!CreateThread` at `0x180034f78`
- `KERNEL32!CreateThread` at `0x180034f78`
- `KERNEL32!CloseHandle` at `0x180035062`
- `KERNEL32!CloseHandle` at `0x180035062`
- `KERNEL32!GetLastError` at `0x180034f0f`
- `KERNEL32!GetLastError` at `0x180034f8a`
- `KERNEL32!GetLastError` at `0x180034fb2`
- `KERNEL32!GetLastError` at `0x180034f0f`
- `KERNEL32!GetLastError` at `0x180034f8a`
- `KERNEL32!GetLastError` at `0x180034fb2`
- `USER32!SendDlgItemMessageW` at `0x180034f4f`
- `USER32!SendDlgItemMessageW` at `0x180034f4f`
- `USER32!GetDlgItemTextW` at `0x180034ec1`
- `USER32!GetDlgItemTextW` at `0x180034ec1`
- `USER32!EndDialog` at `0x18003507d`
- `USER32!EndDialog` at `0x18003507d`
- `USER32!SetDlgItemTextW` at `0x180034f01`
- `USER32!SetDlgItemTextW` at `0x180034f01`
- `USER32!SetWindowLongPtrW` at `0x180034e45`
- `USER32!SetWindowLongPtrW` at `0x180034e45`
- `USER32!EnableWindow` at `0x180034fe1`
- `USER32!EnableWindow` at `0x180034fe1`
- `USER32!GetDlgItem` at `0x180034fd3`
- `USER32!GetDlgItem` at `0x180034fd3`

## pseudocode

```c
__int64 __fastcall WdcConnectingCallback(HWND hDlg, int a2, int a3, void *a4)
{
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  const char *v10; // rdx
  int v11; // r8d
  _WORD *v12; // rax
  const char *v13; // rdx
  int v14; // r8d
  void *v15; // r14
  WCHAR *v16; // rax
  WCHAR *v17; // rsi
  signed int v18; // ebx
  signed int DlgItemTextW; // eax
  signed int LastError; // eax
  void *v21; // r9
  HANDLE v22; // rax
  signed int v23; // eax
  signed int v24; // eax
  HWND DlgItem; // rax
  const char *v26; // rdx
  int v27; // r8d
  const char *v28; // rdx
  int v29; // r8d
  INT_PTR v30; // rdx
  HANDLE v31; // rcx
  LPARAM lParam; // [rsp+20h] [rbp-48h]
  DWORD ThreadId; // [rsp+78h] [rbp+10h] BYREF

  ThreadId = 0;
  v6 = a2 - 2;
  if ( !v6 )
  {
    v31 = hObject;
    if ( !hObject )
    {
LABEL_45:
      v30 = *((int *)lpParameter + 5);
      goto LABEL_46;
    }
    *((_DWORD *)lpParameter + 5) = 1223;
    CancelSynchronousIo(v31);
LABEL_43:
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    goto LABEL_45;
  }
  v7 = v6 - 14;
  if ( !v7 )
    goto LABEL_40;
  v8 = v7 - 256;
  if ( !v8 )
  {
    SetWindowLongPtrW(hDlg, -21, (LONG_PTR)a4);
    lpParameter = a4;
    v12 = WdcAlloc(0x100u, v10, v11);
    v15 = v12;
    if ( !v12 )
    {
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\dialogs.cpp",
        "WdcConnectingCallback",
        0,
        L"FAILURE: 0x%08x",
        -2147024882);
      goto LABEL_40;
    }
    *v12 = 0;
    v16 = (WCHAR *)WdcAlloc(0x100u, v13, v14);
    v17 = v16;
    if ( !v16 )
    {
      v18 = -2147024882;
      LODWORD(lParam) = -2147024882;
LABEL_36:
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\dialogs.cpp",
        "WdcConnectingCallback",
        0,
        L"FAILURE: 0x%08x",
        lParam);
LABEL_37:
      WdcFree(v15, v26, v27);
      if ( v17 )
        WdcFree(v17, v28, v29);
      if ( v18 >= 0 )
        return 0;
LABEL_40:
      v30 = 1223;
LABEL_46:
      EndDialog(hDlg, v30);
      return 0;
    }
    *v16 = 0;
    DlgItemTextW = GetDlgItemTextW(hDlg, 2712, v16, 128);
    v18 = DlgItemTextW;
    if ( DlgItemTextW < 0
      || (DlgItemTextW = StringCchPrintfW((unsigned __int16 *)v15, 0x80u, v17, *((_QWORD *)lpParameter + 1)),
          v18 = DlgItemTextW,
          DlgItemTextW < 0) )
    {
LABEL_35:
      LODWORD(lParam) = DlgItemTextW;
      goto LABEL_36;
    }
    if ( SetDlgItemTextW(hDlg, 2712, (LPCWSTR)v15) )
    {
      v18 = 0;
    }
    else
    {
      LastError = GetLastError();
      v18 = LastError;
      if ( !LastError )
        goto LABEL_33;
      if ( LastError > 0 )
        v18 = (unsigned __int16)LastError | 0x80070000;
      if ( v18 < 0 )
        goto LABEL_34;
    }
    SendDlgItemMessageW(hDlg, 2711, 0x40Au, 1u, 50);
    v21 = lpParameter;
    *(_QWORD *)lpParameter = hDlg;
    v22 = CreateThread(0, 0, WdcConnectServer, v21, 0, &ThreadId);
    hObject = v22;
    if ( v22 )
    {
LABEL_27:
      if ( v22 != (HANDLE)-1LL )
      {
LABEL_32:
        DlgItem = GetDlgItem(hDlg, 2);
        EnableWindow(DlgItem, 1);
        goto LABEL_37;
      }
      v24 = GetLastError();
      v18 = v24;
      if ( v24 )
      {
        if ( v24 > 0 )
          v18 = (unsigned __int16)v24 | 0x80070000;
        if ( v18 >= 0 )
          goto LABEL_32;
        goto LABEL_34;
      }
      goto LABEL_33;
    }
    v23 = GetLastError();
    v18 = v23;
    if ( v23 )
    {
      if ( v23 > 0 )
        v18 = (unsigned __int16)v23 | 0x80070000;
      if ( v18 < 0 )
        goto LABEL_34;
      v22 = hObject;
      goto LABEL_27;
    }
LABEL_33:
    v18 = -2147467259;
LABEL_34:
    DlgItemTextW = v18;
    goto LABEL_35;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    if ( a3 != 2 )
      return 0;
    goto LABEL_40;
  }
  if ( v9 == 1752 )
    goto LABEL_43;
  return 0;
}

```

## disassembly

```asm
0x180034dd0  push    rbx
0x180034dd2  push    rbp
0x180034dd3  push    rsi
0x180034dd4  push    rdi
0x180034dd5  push    r13
0x180034dd7  push    r14
0x180034dd9  sub     rsp, 38h
0x180034ddd  xor     ebp, ebp
0x180034ddf  mov     rbx, r9
0x180034de2  mov     rdi, rcx
0x180034de5  mov     [rsp+68h+ThreadId], ebp
0x180034de9  lea     r13d, [rbp+2]
0x180034ded  sub     edx, r13d
0x180034df0  jz      loc_180035031
0x180034df6  sub     edx, 0Eh
0x180034df9  jz      loc_18003502A
0x180034dff  mov     esi, 100h
0x180034e04  sub     edx, esi
0x180034e06  jz      short loc_180034E3D
0x180034e08  sub     edx, 1
0x180034e0b  jz      short loc_180034E1E
0x180034e0d  cmp     edx, 6D8h
0x180034e13  jnz     loc_180035083
0x180034e19  jmp     loc_180035051
0x180034e1e  mov     rax, r8
0x180034e21  shr     rax, 10h
0x180034e25  test    ax, ax
0x180034e28  jnz     loc_180035083
0x180034e2e  cmp     r8w, r13w
0x180034e32  jz      loc_18003502A
0x180034e38  jmp     loc_180035083
0x180034e3d  mov     r8, rbx; dwNewLong
0x180034e40  mov     edx, 0FFFFFFEBh; nIndex
0x180034e45  call    cs:__imp_SetWindowLongPtrW
0x180034e4b  mov     rcx, rsi; dwBytes
0x180034e4e  mov     cs:lpParameter, rbx
0x180034e55  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180034e5a  mov     r14, rax
0x180034e5d  test    rax, rax
0x180034e60  jnz     short loc_180034E8C
0x180034e62  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180034e69  mov     dword ptr [rsp+68h+lParam], 8007000Eh
0x180034e71  xor     r8d, r8d; int
0x180034e74  lea     rdx, aWdcconnectingc; "WdcConnectingCallback"
0x180034e7b  lea     rcx, aBaseDiagnosisP_28; "base\\diagnosis\\pdui\\perfmon\\mmc\\di"...
0x180034e82  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180034e87  jmp     loc_18003502A
0x180034e8c  mov     rcx, rsi; dwBytes
0x180034e8f  mov     [rax], bp
0x180034e92  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180034e97  mov     rsi, rax
0x180034e9a  test    rax, rax
0x180034e9d  jnz     short loc_180034EAD
0x180034e9f  mov     ebx, 8007000Eh
0x180034ea4  mov     dword ptr [rsp+68h+lParam], ebx
0x180034ea8  jmp     loc_180034FF4
0x180034ead  mov     r9d, 80h; cchMax
0x180034eb3  mov     [rax], bp
0x180034eb6  mov     r8, rsi; lpString
0x180034eb9  mov     edx, 0A98h; nIDDlgItem
0x180034ebe  mov     rcx, rdi; hDlg
0x180034ec1  call    cs:__imp_GetDlgItemTextW
0x180034ec7  mov     ebx, eax
0x180034ec9  test    eax, eax
0x180034ecb  js      loc_180034FF0
0x180034ed1  mov     r9, cs:lpParameter
0x180034ed8  mov     r8, rsi; unsigned __int16 *
0x180034edb  mov     edx, 80h; unsigned __int64
0x180034ee0  mov     rcx, r14; unsigned __int16 *
0x180034ee3  mov     r9, [r9+8]
0x180034ee7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180034eec  mov     ebx, eax
0x180034eee  test    eax, eax
0x180034ef0  js      loc_180034FF0
0x180034ef6  mov     r8, r14; lpString
0x180034ef9  mov     edx, 0A98h; nIDDlgItem
0x180034efe  mov     rcx, rdi; hDlg
0x180034f01  call    cs:__imp_SetDlgItemTextW
0x180034f07  test    eax, eax
0x180034f09  jz      short loc_180034F0F
0x180034f0b  mov     ebx, ebp
0x180034f0d  jmp     short loc_180034F32
0x180034f0f  call    cs:__imp_GetLastError
0x180034f15  mov     ebx, eax
0x180034f17  test    eax, eax
0x180034f19  jz      loc_180034FE9
0x180034f1f  jle     short loc_180034F2A
0x180034f21  movzx   ebx, ax
0x180034f24  or      ebx, 80070000h
0x180034f2a  test    ebx, ebx
0x180034f2c  js      loc_180034FEE
0x180034f32  mov     edx, 0A97h; nIDDlgItem
0x180034f37  mov     [rsp+68h+lParam], 32h ; '2'; lParam
0x180034f40  mov     r9d, 1; wParam
0x180034f46  mov     r8d, 40Ah; Msg
0x180034f4c  mov     rcx, rdi; hDlg
0x180034f4f  call    cs:__imp_SendDlgItemMessageW
0x180034f55  mov     r9, cs:lpParameter; lpParameter
0x180034f5c  lea     rax, [rsp+68h+ThreadId]
0x180034f61  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x180034f66  lea     r8, ?WdcConnectServer@@YAKPEAX@Z; lpStartAddress
0x180034f6d  xor     edx, edx; dwStackSize
0x180034f6f  mov     dword ptr [rsp+68h+lParam], ebp; dwCreationFlags
0x180034f73  xor     ecx, ecx; lpThreadAttributes
0x180034f75  mov     [r9], rdi
0x180034f78  call    cs:__imp_CreateThread
0x180034f7e  mov     cs:hObject, rax
0x180034f85  test    rax, rax
0x180034f88  jnz     short loc_180034FAC
0x180034f8a  call    cs:__imp_GetLastError
0x180034f90  mov     ebx, eax
0x180034f92  test    eax, eax
0x180034f94  jz      short loc_180034FE9
0x180034f96  jle     short loc_180034FA1
0x180034f98  movzx   ebx, ax
0x180034f9b  or      ebx, 80070000h
0x180034fa1  test    ebx, ebx
0x180034fa3  js      short loc_180034FEE
0x180034fa5  mov     rax, cs:hObject
0x180034fac  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180034fb0  jnz     short loc_180034FCD
0x180034fb2  call    cs:__imp_GetLastError
0x180034fb8  mov     ebx, eax
0x180034fba  test    eax, eax
0x180034fbc  jz      short loc_180034FE9
0x180034fbe  jle     short loc_180034FC9
0x180034fc0  movzx   ebx, ax
0x180034fc3  or      ebx, 80070000h
0x180034fc9  test    ebx, ebx
0x180034fcb  js      short loc_180034FEE
0x180034fcd  mov     edx, r13d; nIDDlgItem
0x180034fd0  mov     rcx, rdi; hDlg
0x180034fd3  call    cs:__imp_GetDlgItem
0x180034fd9  mov     rcx, rax; hWnd
0x180034fdc  mov     edx, 1; bEnable
0x180034fe1  call    cs:__imp_EnableWindow
0x180034fe7  jmp     short loc_180035011
0x180034fe9  mov     ebx, 80004005h
0x180034fee  mov     eax, ebx
0x180034ff0  mov     dword ptr [rsp+68h+lParam], eax
0x180034ff4  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180034ffb  xor     r8d, r8d; int
0x180034ffe  lea     rdx, aWdcconnectingc; "WdcConnectingCallback"
0x180035005  lea     rcx, aBaseDiagnosisP_28; "base\\diagnosis\\pdui\\perfmon\\mmc\\di"...
0x18003500c  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180035011  mov     rcx, r14; void *
0x180035014  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x180035019  test    rsi, rsi
0x18003501c  jz      short loc_180035026
0x18003501e  mov     rcx, rsi; void *
0x180035021  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x180035026  test    ebx, ebx
0x180035028  jns     short loc_180035083
0x18003502a  mov     edx, 4C7h
0x18003502f  jmp     short loc_18003507A
0x180035031  mov     rcx, cs:hObject; hThread
0x180035038  test    rcx, rcx
0x18003503b  jz      short loc_18003506F
0x18003503d  mov     rax, cs:lpParameter
0x180035044  mov     dword ptr [rax+14h], 4C7h
0x18003504b  call    cs:__imp_CancelSynchronousIo
0x180035051  mov     rcx, cs:hObject; hObject
0x180035058  lea     rax, [rcx-1]
0x18003505c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180035060  ja      short loc_18003506F
0x180035062  call    cs:__imp_CloseHandle
0x180035068  mov     cs:hObject, rbp
0x18003506f  mov     rax, cs:lpParameter
0x180035076  movsxd  rdx, dword ptr [rax+14h]; nResult
0x18003507a  mov     rcx, rdi; hDlg
0x18003507d  call    cs:__imp_EndDialog
0x180035083  xor     eax, eax
0x180035085  add     rsp, 38h
0x180035089  pop     r14
0x18003508b  pop     r13
0x18003508d  pop     rdi
0x18003508e  pop     rsi
0x18003508f  pop     rbp
0x180035090  pop     rbx
0x180035091  retn
```
