# CWshShell::AppActivate(tagVARIANT *,tagVARIANT *,short *)

- ea: `0x180009cf0`
- end: `0x18000a39e`
- name: `?AppActivate@CWshShell@@UEAAJPEAUtagVARIANT@@0PEAF@Z`
- size: `1710`
- prototype: `int(CWshShell *__hidden this, struct tagVARIANT *, struct tagVARIANT *, __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180005730`
- `0x180005850`
- `0x180005938`
- `0x1800060e4`
- `0x180006124`
- `0x180009cf0`
- `0x180010250`
- `0x1800102e0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000a240`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a240`
- `OLEAUT32!__imp_SysStringLen` at `0x180009d71`
- `OLEAUT32!__imp_SysStringLen` at `0x180009d71`
- `KERNEL32!GetLastError` at `0x180009dbd`
- `KERNEL32!GetLastError` at `0x180009fb6`
- `KERNEL32!GetLastError` at `0x180009fd8`
- `KERNEL32!GetLastError` at `0x18000a32a`
- `KERNEL32!GetLastError` at `0x180009dbd`
- `KERNEL32!GetLastError` at `0x180009fb6`
- `KERNEL32!GetLastError` at `0x180009fd8`
- `KERNEL32!GetLastError` at `0x18000a32a`
- `KERNEL32!WideCharToMultiByte` at `0x180009db0`
- `KERNEL32!WideCharToMultiByte` at `0x180009e2e`
- `KERNEL32!WideCharToMultiByte` at `0x180009db0`
- `KERNEL32!WideCharToMultiByte` at `0x180009e2e`
- `KERNEL32!MultiByteToWideChar` at `0x180009f2c`
- `KERNEL32!MultiByteToWideChar` at `0x180009f76`
- `KERNEL32!MultiByteToWideChar` at `0x18000a0ed`
- `KERNEL32!MultiByteToWideChar` at `0x18000a13b`
- `KERNEL32!MultiByteToWideChar` at `0x180009f2c`
- `KERNEL32!MultiByteToWideChar` at `0x180009f76`
- `KERNEL32!MultiByteToWideChar` at `0x18000a0ed`
- `KERNEL32!MultiByteToWideChar` at `0x18000a13b`
- `KERNEL32!GetCurrentThreadId` at `0x18000a2f8`
- `KERNEL32!GetCurrentThreadId` at `0x18000a359`
- `KERNEL32!GetCurrentThreadId` at `0x18000a2f8`
- `KERNEL32!GetCurrentThreadId` at `0x18000a359`
- `USER32!GetWindowTextLengthW` at `0x180009e79`
- `USER32!GetWindowTextLengthW` at `0x18000a033`
- `USER32!GetWindowTextLengthW` at `0x180009e79`
- `USER32!GetWindowTextLengthW` at `0x18000a033`
- `USER32!GetWindow` at `0x180009e5b`
- `USER32!GetWindow` at `0x18000a015`
- `USER32!GetWindow` at `0x18000a19d`
- `USER32!GetWindow` at `0x18000a1e6`
- `USER32!GetWindow` at `0x18000a221`
- `USER32!GetWindow` at `0x18000a270`
- `USER32!GetWindow` at `0x18000a28a`
- `USER32!GetWindow` at `0x18000a2b7`
- `USER32!GetWindow` at `0x18000a2c8`
- `USER32!GetWindow` at `0x180009e5b`
- `USER32!GetWindow` at `0x18000a015`
- `USER32!GetWindow` at `0x18000a19d`
- `USER32!GetWindow` at `0x18000a1e6`
- `USER32!GetWindow` at `0x18000a221`
- `USER32!GetWindow` at `0x18000a270`
- `USER32!GetWindow` at `0x18000a28a`
- `USER32!GetWindow` at `0x18000a2b7`
- `USER32!GetWindow` at `0x18000a2c8`
- `USER32!IsWindowEnabled` at `0x18000a1c7`
- `USER32!IsWindowEnabled` at `0x18000a254`
- `USER32!IsWindowEnabled` at `0x18000a298`
- `USER32!IsWindowEnabled` at `0x18000a1c7`
- `USER32!IsWindowEnabled` at `0x18000a254`
- `USER32!IsWindowEnabled` at `0x18000a298`
- `USER32!SetFocus` at `0x18000a31f`
- `USER32!SetFocus` at `0x18000a31f`
- `USER32!FindWindowW` at `0x180009d88`
- `USER32!FindWindowW` at `0x180009d88`
- `USER32!GetDesktopWindow` at `0x180009e4f`
- `USER32!GetDesktopWindow` at `0x18000a007`
- `USER32!GetDesktopWindow` at `0x18000a18d`
- `USER32!GetDesktopWindow` at `0x18000a1f9`
- `USER32!GetDesktopWindow` at `0x180009e4f`
- `USER32!GetDesktopWindow` at `0x18000a007`
- `USER32!GetDesktopWindow` at `0x18000a18d`
- `USER32!GetDesktopWindow` at `0x18000a1f9`
- `USER32!GetWindowTextLengthA` at `0x180009ed4`
- `USER32!GetWindowTextLengthA` at `0x18000a095`
- `USER32!GetWindowTextLengthA` at `0x180009ed4`
- `USER32!GetWindowTextLengthA` at `0x18000a095`
- `USER32!FindWindowA` at `0x180009e3d`
- `USER32!FindWindowA` at `0x180009e3d`
- `USER32!IsWindowVisible` at `0x18000a1d4`
- `USER32!IsWindowVisible` at `0x18000a261`
- `USER32!IsWindowVisible` at `0x18000a2a5`
- `USER32!IsWindowVisible` at `0x18000a1d4`
- `USER32!IsWindowVisible` at `0x18000a261`
- `USER32!IsWindowVisible` at `0x18000a2a5`
- `USER32!SetForegroundWindow` at `0x18000a316`
- `USER32!SetForegroundWindow` at `0x18000a316`
- `USER32!GetWindowTextA` at `0x180009f03`
- `USER32!GetWindowTextA` at `0x18000a0c4`
- `USER32!GetWindowTextA` at `0x180009f03`
- `USER32!GetWindowTextA` at `0x18000a0c4`
- `USER32!AttachThreadInput` at `0x18000a30b`
- `USER32!AttachThreadInput` at `0x18000a366`
- `USER32!AttachThreadInput` at `0x18000a30b`
- `USER32!AttachThreadInput` at `0x18000a366`
- `USER32!GetWindowThreadProcessId` at `0x18000a1b8`
- `USER32!GetWindowThreadProcessId` at `0x18000a20d`
- `USER32!GetWindowThreadProcessId` at `0x18000a2f0`
- `USER32!GetWindowThreadProcessId` at `0x18000a351`
- `USER32!GetWindowThreadProcessId` at `0x18000a1b8`
- `USER32!GetWindowThreadProcessId` at `0x18000a20d`
- `USER32!GetWindowThreadProcessId` at `0x18000a2f0`
- `USER32!GetWindowThreadProcessId` at `0x18000a351`
- `USER32!GetWindowTextW` at `0x180009eae`
- `USER32!GetWindowTextW` at `0x18000a068`
- `USER32!GetWindowTextW` at `0x180009eae`
- `USER32!GetWindowTextW` at `0x18000a068`

## pseudocode

```c
__int64 __fastcall CWshShell::AppActivate(CWshShell *this, struct tagVARIANT *a2, struct tagVARIANT *a3, __int16 *a4)
{
  __int16 *v4; // r14
  WCHAR *v6; // r13
  __int16 v7; // r15
  int v8; // eax
  unsigned int v9; // edi
  unsigned __int64 v10; // r12
  HWND WindowW; // rax
  int cbMultiByte; // eax
  signed int LastError; // eax
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  void *v16; // rsp
  void *v17; // rsp
  HWND v18; // rsi
  HWND v19; // rcx
  UINT j; // edx
  HWND v21; // rax
  int WindowTextLengthW; // eax
  int v23; // ebx
  WCHAR *v24; // r14
  int v25; // ebx
  BSTR v26; // rcx
  int WindowTextLengthA; // eax
  int v28; // ebx
  CHAR *v29; // rax
  int v30; // eax
  const unsigned __int16 *v31; // rbx
  signed int v32; // eax
  void *v33; // rcx
  signed int v34; // eax
  HWND v35; // rcx
  UINT k; // edx
  HWND v37; // rax
  int v38; // eax
  int v39; // ebx
  int WindowTextW; // eax
  int v41; // ebx
  BSTR v42; // rcx
  int v43; // eax
  int v44; // ebx
  CHAR *v45; // rax
  int v46; // eax
  int v47; // eax
  HWND DesktopWindow; // rax
  HWND Window; // rax
  int v50; // r14d
  HWND v51; // rcx
  UINT i; // edx
  HWND v53; // rax
  HWND v55; // rbx
  DWORD WindowThreadProcessId; // ebx
  DWORD CurrentThreadId; // eax
  BOOL v58; // ebx
  DWORD v59; // ebx
  DWORD v60; // eax
  CHAR MultiByteStr[4]; // [rsp+40h] [rbp+0h] BYREF
  BSTR pbstr; // [rsp+48h] [rbp+8h] BYREF
  __int16 *v63; // [rsp+50h] [rbp+10h]
  DWORD dwProcessId; // [rsp+58h] [rbp+18h] BYREF

  v63 = a4;
  v4 = a4;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *(_DWORD *)MultiByteStr = 0;
  pbstr = 0;
  v6 = 0;
  v7 = -1;
  if ( (int)Variant_I4(a2, (unsigned int *)MultiByteStr) >= 0 )
  {
    LODWORD(pbstr) = 0;
    DesktopWindow = GetDesktopWindow();
    Window = GetWindow(DesktopWindow, 5u);
    v50 = *(_DWORD *)MultiByteStr;
    v9 = 0;
    v18 = Window;
    if ( !Window )
      goto LABEL_61;
    do
    {
      GetWindowThreadProcessId(v18, (LPDWORD)&pbstr);
      if ( (_DWORD)pbstr == v50 && IsWindowEnabled(v18) && IsWindowVisible(v18) )
        break;
      v18 = GetWindow(v18, 2u);
    }
    while ( v18 );
    if ( !v18 )
    {
LABEL_61:
      v51 = GetDesktopWindow();
      for ( i = 5; ; i = 2 )
      {
        v53 = GetWindow(v51, i);
        v18 = v53;
        if ( !v53 )
        {
LABEL_65:
          *v63 = 0;
          goto LABEL_66;
        }
        GetWindowThreadProcessId(v53, (LPDWORD)&pbstr);
        if ( (_DWORD)pbstr == v50 )
          break;
        v51 = v18;
      }
    }
LABEL_68:
    v4 = v63;
  }
  else
  {
    v8 = Variant_BSTR(a2, &pbstr);
    v6 = pbstr;
    v9 = v8;
    if ( v8 < 0 )
      goto LABEL_67;
    v10 = (int)SysStringLen(pbstr);
    if ( Global::g_fWindowsNT )
    {
      WindowW = FindWindowW(0, v6);
    }
    else
    {
      cbMultiByte = WideCharToMultiByte(0, 0, v6, -1, 0, 0, 0, 0);
      if ( !cbMultiByte )
        goto LABEL_8;
      v14 = cbMultiByte + 15LL;
      if ( v14 < cbMultiByte )
        v14 = 0xFFFFFFFFFFFFFF0LL;
      v15 = v14 & 0xFFFFFFFFFFFFFFF0uLL;
      v16 = alloca(v15);
      v17 = alloca(v15);
      if ( !MultiByteStr )
        goto LABEL_13;
      if ( !WideCharToMultiByte(0, 0, v6, -1, MultiByteStr, cbMultiByte, 0, 0) )
      {
LABEL_8:
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_67;
      }
      WindowW = FindWindowA(0, MultiByteStr);
    }
    v18 = WindowW;
    if ( !WindowW )
    {
      v19 = GetDesktopWindow();
      for ( j = 5; ; j = 2 )
      {
        v21 = GetWindow(v19, j);
        v18 = v21;
        if ( !v21 )
          break;
        if ( Global::g_fWindowsNT )
        {
          WindowTextLengthW = GetWindowTextLengthW(v21);
          if ( WindowTextLengthW <= (int)v10 )
            goto LABEL_31;
          v23 = WindowTextLengthW + 1;
          v24 = (WCHAR *)operator new(saturated_mul(WindowTextLengthW + 1, 2u));
          if ( !GetWindowTextW(v18, v24, v23) )
            goto LABEL_32;
          v25 = CompareStrsCaseInsensitive(v6, v24, v10);
          v26 = v24;
        }
        else
        {
          WindowTextLengthA = GetWindowTextLengthA(v21);
          if ( WindowTextLengthA <= (int)v10 )
            goto LABEL_31;
          v28 = WindowTextLengthA + 1;
          v29 = (CHAR *)operator new(WindowTextLengthA + 1);
          v24 = (WCHAR *)v29;
          if ( !v29 )
            goto LABEL_13;
          if ( !GetWindowTextA(v18, v29, v28)
            || (v30 = MultiByteToWideChar(0, 0, (LPCCH)v24, -1, 0, 0), (*(_DWORD *)MultiByteStr = v30) == 0) )
          {
LABEL_32:
            v32 = GetLastError();
            v9 = v32;
            if ( v32 > 0 )
              v9 = (unsigned __int16)v32 | 0x80070000;
            v33 = v24;
LABEL_35:
            operator delete(v33);
            goto LABEL_67;
          }
          pbstr = (BSTR)operator new(saturated_mul(v30, 2u));
          v31 = pbstr;
          if ( !pbstr )
          {
LABEL_39:
            operator delete(v24);
LABEL_13:
            v9 = -2147024882;
            goto LABEL_67;
          }
          if ( !MultiByteToWideChar(0, 0, (LPCCH)v24, -1, pbstr, *(int *)MultiByteStr) )
          {
LABEL_36:
            v34 = GetLastError();
            v9 = v34;
            if ( v34 > 0 )
              v9 = (unsigned __int16)v34 | 0x80070000;
            operator delete(v24);
            v33 = (void *)v31;
            goto LABEL_35;
          }
          v25 = CompareStrsCaseInsensitive(v6, v31, v10);
          operator delete(v24);
          v26 = pbstr;
        }
        operator delete(v26);
        if ( !v25 )
          goto LABEL_68;
LABEL_31:
        v19 = v18;
      }
      v35 = GetDesktopWindow();
      for ( k = 5; ; k = 2 )
      {
        v37 = GetWindow(v35, k);
        v18 = v37;
        if ( !v37 )
          goto LABEL_65;
        if ( Global::g_fWindowsNT )
        {
          v38 = GetWindowTextLengthW(v37);
          if ( v38 <= (int)v10 )
            goto LABEL_54;
          v39 = v38 + 1;
          v24 = (WCHAR *)operator new(saturated_mul(v38 + 1, 2u));
          WindowTextW = GetWindowTextW(v18, v24, v39);
          if ( !WindowTextW )
            goto LABEL_32;
          v41 = CompareStrsCaseInsensitive(v6, &v24[WindowTextW - (int)v10], v10);
          v42 = v24;
        }
        else
        {
          v43 = GetWindowTextLengthA(v37);
          if ( v43 <= (int)v10 )
            goto LABEL_54;
          v44 = v43 + 1;
          v45 = (CHAR *)operator new(v43 + 1);
          v24 = (WCHAR *)v45;
          if ( !v45 )
            goto LABEL_13;
          if ( !GetWindowTextA(v18, v45, v44) )
            goto LABEL_32;
          v46 = MultiByteToWideChar(0, 0, (LPCCH)v24, -1, 0, 0);
          *(_DWORD *)MultiByteStr = v46;
          if ( !v46 )
            goto LABEL_32;
          pbstr = (BSTR)operator new(saturated_mul(v46, 2u));
          v31 = pbstr;
          if ( !pbstr )
            goto LABEL_39;
          v47 = MultiByteToWideChar(0, 0, (LPCCH)v24, -1, pbstr, *(int *)MultiByteStr);
          if ( !v47 )
            goto LABEL_36;
          v41 = CompareStrsCaseInsensitive(v6, &v31[v47 - (int)v10 - 1], v10);
          operator delete(v24);
          v42 = pbstr;
        }
        operator delete(v42);
        if ( !v41 )
          goto LABEL_68;
LABEL_54:
        v35 = v18;
      }
    }
  }
  if ( IsWindowEnabled(v18) && IsWindowVisible(v18) )
  {
LABEL_79:
    dwProcessId = 0;
    WindowThreadProcessId = GetWindowThreadProcessId(v18, &dwProcessId);
    CurrentThreadId = GetCurrentThreadId();
    v58 = AttachThreadInput(CurrentThreadId, WindowThreadProcessId, 1);
    SetForegroundWindow(v18);
    if ( !SetFocus(v18) )
      v7 = (GetLastError() != 0) - 1;
    *v4 = v7;
    if ( !v58 )
    {
      v59 = GetWindowThreadProcessId(v18, &dwProcessId);
      v60 = GetCurrentThreadId();
      AttachThreadInput(v60, v59, 0);
    }
    goto LABEL_67;
  }
  v55 = GetWindow(v18, 0);
  if ( !v55 )
    goto LABEL_83;
  while ( GetWindow(v55, 4u) != v18 )
  {
LABEL_76:
    v55 = GetWindow(v55, 2u);
    if ( !v55 )
      goto LABEL_77;
  }
  if ( !IsWindowEnabled(v55) || !IsWindowVisible(v55) )
  {
    v18 = v55;
    v55 = GetWindow(v55, 0);
    goto LABEL_76;
  }
LABEL_77:
  if ( v55 )
  {
    v18 = v55;
    goto LABEL_79;
  }
LABEL_83:
  *v4 = 0;
LABEL_66:
  v9 = 1;
LABEL_67:
  SysFreeString(v6);
  return v9;
}

```

## disassembly

```asm
0x180009cf0  push    rbp
0x180009cf2  push    rbx
0x180009cf3  push    rsi
0x180009cf4  push    rdi
0x180009cf5  push    r12
0x180009cf7  push    r13
0x180009cf9  push    r14
0x180009cfb  push    r15
0x180009cfd  sub     rsp, 78h
0x180009d01  lea     rbp, [rsp+40h]
0x180009d06  mov     rax, cs:__security_cookie
0x180009d0d  xor     rax, rbp
0x180009d10  mov     [rbp+70h+var_50], rax
0x180009d14  xor     esi, esi
0x180009d16  mov     [rbp+70h+var_60], r9
0x180009d1a  mov     r14, r9
0x180009d1d  mov     rbx, rdx
0x180009d20  test    rdx, rdx
0x180009d23  jz      loc_18000A37C
0x180009d29  test    r8, r8
0x180009d2c  jz      loc_18000A37C
0x180009d32  lea     rdx, [rbp+70h+MultiByteStr]; unsigned int *
0x180009d36  mov     dword ptr [rbp+70h+MultiByteStr], esi
0x180009d39  mov     rcx, rbx; pvarSrc
0x180009d3c  mov     [rbp+70h+pbstr], rsi
0x180009d40  mov     r13d, esi
0x180009d43  call    ?Variant_I4@@YAJPEAUtagVARIANT@@PEAK@Z; Variant_I4(tagVARIANT *,ulong *)
0x180009d48  or      r15, 0FFFFFFFFFFFFFFFFh
0x180009d4c  test    eax, eax
0x180009d4e  jns     loc_18000A187
0x180009d54  lea     rdx, [rbp+70h+pbstr]; unsigned __int16 **
0x180009d58  mov     rcx, rbx; pvarSrc
0x180009d5b  call    ?Variant_BSTR@@YAJPEAUtagVARIANT@@PEAPEAG@Z; Variant_BSTR(tagVARIANT *,ushort * *)
0x180009d60  mov     r13, [rbp+70h+pbstr]
0x180009d64  mov     edi, eax
0x180009d66  test    eax, eax
0x180009d68  js      loc_18000A23D
0x180009d6e  mov     rcx, r13; pbstr
0x180009d71  call    cs:__imp_SysStringLen
0x180009d77  cmp     cs:?g_fWindowsNT@Global@@2_NA, sil; bool Global::g_fWindowsNT
0x180009d7e  movsxd  r12, eax
0x180009d81  jz      short loc_180009D93
0x180009d83  mov     rdx, r13; lpWindowName
0x180009d86  xor     ecx, ecx; lpClassName
0x180009d88  call    cs:__imp_FindWindowW
0x180009d8e  jmp     loc_180009E43
0x180009d93  mov     [rsp+0B0h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x180009d98  mov     r9d, r15d; cchWideChar
0x180009d9b  mov     [rsp+0B0h+lpDefaultChar], rsi; lpDefaultChar
0x180009da0  mov     r8, r13; lpWideCharStr
0x180009da3  mov     [rsp+0B0h+cbMultiByte], esi; cbMultiByte
0x180009da7  xor     edx, edx; dwFlags
0x180009da9  xor     ecx, ecx; CodePage
0x180009dab  mov     [rsp+0B0h+lpMultiByteStr], rsi; lpMultiByteStr
0x180009db0  call    cs:__imp_WideCharToMultiByte
0x180009db6  movsxd  rdx, eax
0x180009db9  test    eax, eax
0x180009dbb  jnz     short loc_180009DDB
0x180009dbd  call    cs:__imp_GetLastError
0x180009dc3  mov     edi, eax
0x180009dc5  test    eax, eax
0x180009dc7  jle     loc_18000A23D
0x180009dcd  movzx   edi, ax
0x180009dd0  or      edi, 80070000h
0x180009dd6  jmp     loc_18000A23D
0x180009ddb  lea     rcx, [rdx+0Fh]
0x180009ddf  cmp     rcx, rdx
0x180009de2  ja      short loc_180009DEE
0x180009de4  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180009dee  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180009df2  mov     rax, rcx
0x180009df5  call    _alloca_probe
0x180009dfa  sub     rsp, rcx
0x180009dfd  lea     rbx, [rsp+0B0h+MultiByteStr]
0x180009e02  test    rbx, rbx
0x180009e05  jnz     short loc_180009E11
0x180009e07  mov     edi, 8007000Eh
0x180009e0c  jmp     loc_18000A23D
0x180009e11  mov     [rsp+0B0h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x180009e16  mov     r9d, r15d; cchWideChar
0x180009e19  mov     [rsp+0B0h+lpDefaultChar], rsi; lpDefaultChar
0x180009e1e  mov     r8, r13; lpWideCharStr
0x180009e21  mov     [rsp+0B0h+cbMultiByte], edx; cbMultiByte
0x180009e25  xor     ecx, ecx; CodePage
0x180009e27  xor     edx, edx; dwFlags
0x180009e29  mov     [rsp+0B0h+lpMultiByteStr], rbx; lpMultiByteStr
0x180009e2e  call    cs:__imp_WideCharToMultiByte
0x180009e34  test    eax, eax
0x180009e36  jz      short loc_180009DBD
0x180009e38  mov     rdx, rbx; lpWindowName
0x180009e3b  xor     ecx, ecx; lpClassName
0x180009e3d  call    cs:__imp_FindWindowA
0x180009e43  mov     rsi, rax
0x180009e46  test    rax, rax
0x180009e49  jnz     loc_18000A251
0x180009e4f  call    cs:__imp_GetDesktopWindow
0x180009e55  mov     rcx, rax; hWnd
0x180009e58  lea     edx, [rsi+5]; uCmd
0x180009e5b  call    cs:__imp_GetWindow
0x180009e61  mov     rsi, rax
0x180009e64  test    rax, rax
0x180009e67  jz      loc_18000A007
0x180009e6d  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x180009e74  mov     rcx, rax; hWnd
0x180009e77  jz      short loc_180009ED4
0x180009e79  call    cs:__imp_GetWindowTextLengthW
0x180009e7f  cmp     eax, r12d
0x180009e82  jle     loc_180009FA9
0x180009e88  lea     ebx, [rax+1]
0x180009e8b  mov     eax, 2
0x180009e90  movsxd  rcx, ebx
0x180009e93  mul     rcx
0x180009e96  cmovb   rax, r15
0x180009e9a  mov     rcx, rax; Size
0x180009e9d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009ea2  mov     r8d, ebx; nMaxCount
0x180009ea5  mov     rdx, rax; lpString
0x180009ea8  mov     rcx, rsi; hWnd
0x180009eab  mov     r14, rax
0x180009eae  call    cs:__imp_GetWindowTextW
0x180009eb4  test    eax, eax
0x180009eb6  jz      loc_180009FB6
0x180009ebc  mov     r8, r12; unsigned __int64
0x180009ebf  mov     rdx, r14; unsigned __int16 *
0x180009ec2  mov     rcx, r13; unsigned __int16 *
0x180009ec5  call    ?CompareStrsCaseInsensitive@@YAHPEBG0_K@Z; CompareStrsCaseInsensitive(ushort const *,ushort const *,unsigned __int64)
0x180009eca  mov     ebx, eax
0x180009ecc  mov     rcx, r14
0x180009ecf  jmp     loc_180009F9C
0x180009ed4  call    cs:__imp_GetWindowTextLengthA
0x180009eda  cmp     eax, r12d
0x180009edd  jle     loc_180009FA9
0x180009ee3  lea     ebx, [rax+1]
0x180009ee6  movsxd  rcx, ebx; Size
0x180009ee9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009eee  mov     r14, rax
0x180009ef1  test    rax, rax
0x180009ef4  jz      loc_180009E07
0x180009efa  mov     r8d, ebx; nMaxCount
0x180009efd  mov     rdx, rax; lpString
0x180009f00  mov     rcx, rsi; hWnd
0x180009f03  call    cs:__imp_GetWindowTextA
0x180009f09  test    eax, eax
0x180009f0b  jz      loc_180009FB6
0x180009f11  mov     [rsp+0B0h+cbMultiByte], 0; cchWideChar
0x180009f19  mov     r9d, r15d; cbMultiByte
0x180009f1c  mov     r8, r14; lpMultiByteStr
0x180009f1f  mov     [rsp+0B0h+lpMultiByteStr], 0; lpWideCharStr
0x180009f28  xor     edx, edx; dwFlags
0x180009f2a  xor     ecx, ecx; CodePage
0x180009f2c  call    cs:__imp_MultiByteToWideChar
0x180009f32  mov     dword ptr [rbp+70h+MultiByteStr], eax
0x180009f35  test    eax, eax
0x180009f37  jz      short loc_180009FB6
0x180009f39  movsxd  rcx, eax
0x180009f3c  mov     eax, 2
0x180009f41  mul     rcx
0x180009f44  cmovb   rax, r15
0x180009f48  mov     rcx, rax; Size
0x180009f4b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009f50  mov     [rbp+70h+pbstr], rax
0x180009f54  mov     rbx, rax
0x180009f57  test    rax, rax
0x180009f5a  jz      loc_180009FFA
0x180009f60  mov     eax, dword ptr [rbp+70h+MultiByteStr]
0x180009f63  mov     r9d, r15d; cbMultiByte
0x180009f66  mov     [rsp+0B0h+cbMultiByte], eax; cchWideChar
0x180009f6a  mov     r8, r14; lpMultiByteStr
0x180009f6d  xor     edx, edx; dwFlags
0x180009f6f  mov     [rsp+0B0h+lpMultiByteStr], rbx; lpWideCharStr
0x180009f74  xor     ecx, ecx; CodePage
0x180009f76  call    cs:__imp_MultiByteToWideChar
0x180009f7c  test    eax, eax
0x180009f7e  jz      short loc_180009FD8
0x180009f80  mov     r8, r12; unsigned __int64
0x180009f83  mov     rdx, rbx; unsigned __int16 *
0x180009f86  mov     rcx, r13; unsigned __int16 *
0x180009f89  call    ?CompareStrsCaseInsensitive@@YAHPEBG0_K@Z; CompareStrsCaseInsensitive(ushort const *,ushort const *,unsigned __int64)
0x180009f8e  mov     rcx, r14; Block
0x180009f91  mov     ebx, eax
0x180009f93  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009f98  mov     rcx, [rbp+70h+pbstr]; Block
0x180009f9c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009fa1  test    ebx, ebx
0x180009fa3  jz      loc_18000A24D
0x180009fa9  mov     edx, 2
0x180009fae  mov     rcx, rsi
0x180009fb1  jmp     loc_180009E5B
0x180009fb6  call    cs:__imp_GetLastError
0x180009fbc  mov     edi, eax
0x180009fbe  test    eax, eax
0x180009fc0  jle     short loc_180009FCB
0x180009fc2  movzx   edi, ax
0x180009fc5  or      edi, 80070000h
0x180009fcb  mov     rcx, r14; Block
0x180009fce  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009fd3  jmp     loc_18000A23D
0x180009fd8  call    cs:__imp_GetLastError
0x180009fde  mov     edi, eax
0x180009fe0  test    eax, eax
0x180009fe2  jle     short loc_180009FED
0x180009fe4  movzx   edi, ax
0x180009fe7  or      edi, 80070000h
0x180009fed  mov     rcx, r14; Block
0x180009ff0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009ff5  mov     rcx, rbx
0x180009ff8  jmp     short loc_180009FCE
0x180009ffa  mov     rcx, r14; Block
0x180009ffd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a002  jmp     loc_180009E07
0x18000a007  call    cs:__imp_GetDesktopWindow
0x18000a00d  mov     rcx, rax; hWnd
0x18000a010  mov     edx, 5; uCmd
0x18000a015  call    cs:__imp_GetWindow
0x18000a01b  mov     rsi, rax
0x18000a01e  test    rax, rax
0x18000a021  jz      loc_18000A22F
0x18000a027  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x18000a02e  mov     rcx, rax; hWnd
0x18000a031  jz      short loc_18000A095
0x18000a033  call    cs:__imp_GetWindowTextLengthW
0x18000a039  cmp     eax, r12d
0x18000a03c  jle     loc_18000A17A
0x18000a042  lea     ebx, [rax+1]
0x18000a045  mov     eax, 2
0x18000a04a  movsxd  rcx, ebx
0x18000a04d  mul     rcx
0x18000a050  cmovb   rax, r15
0x18000a054  mov     rcx, rax; Size
0x18000a057  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a05c  mov     r8d, ebx; nMaxCount
0x18000a05f  mov     rdx, rax; lpString
0x18000a062  mov     rcx, rsi; hWnd
0x18000a065  mov     r14, rax
0x18000a068  call    cs:__imp_GetWindowTextW
0x18000a06e  test    eax, eax
0x18000a070  jz      loc_180009FB6
0x18000a076  sub     eax, r12d
0x18000a079  mov     r8, r12; unsigned __int64
0x18000a07c  movsxd  rcx, eax
0x18000a07f  lea     rdx, [r14+rcx*2]; unsigned __int16 *
0x18000a083  mov     rcx, r13; unsigned __int16 *
0x18000a086  call    ?CompareStrsCaseInsensitive@@YAHPEBG0_K@Z; CompareStrsCaseInsensitive(ushort const *,ushort const *,unsigned __int64)
0x18000a08b  mov     ebx, eax
0x18000a08d  mov     rcx, r14
0x18000a090  jmp     loc_18000A16D
0x18000a095  call    cs:__imp_GetWindowTextLengthA
0x18000a09b  cmp     eax, r12d
0x18000a09e  jle     loc_18000A17A
0x18000a0a4  lea     ebx, [rax+1]
0x18000a0a7  movsxd  rcx, ebx; Size
0x18000a0aa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a0af  mov     r14, rax
0x18000a0b2  test    rax, rax
0x18000a0b5  jz      loc_180009E07
0x18000a0bb  mov     r8d, ebx; nMaxCount
0x18000a0be  mov     rdx, rax; lpString
0x18000a0c1  mov     rcx, rsi; hWnd
0x18000a0c4  call    cs:__imp_GetWindowTextA
0x18000a0ca  test    eax, eax
0x18000a0cc  jz      loc_180009FB6
0x18000a0d2  mov     [rsp+0B0h+cbMultiByte], 0; cchWideChar
0x18000a0da  mov     r9d, r15d; cbMultiByte
0x18000a0dd  mov     r8, r14; lpMultiByteStr
0x18000a0e0  mov     [rsp+0B0h+lpMultiByteStr], 0; lpWideCharStr
0x18000a0e9  xor     edx, edx; dwFlags
0x18000a0eb  xor     ecx, ecx; CodePage
0x18000a0ed  call    cs:__imp_MultiByteToWideChar
0x18000a0f3  mov     dword ptr [rbp+70h+MultiByteStr], eax
0x18000a0f6  test    eax, eax
0x18000a0f8  jz      loc_180009FB6
0x18000a0fe  movsxd  rcx, eax
0x18000a101  mov     eax, 2
0x18000a106  mul     rcx
0x18000a109  cmovb   rax, r15
0x18000a10d  mov     rcx, rax; Size
0x18000a110  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a115  mov     [rbp+70h+pbstr], rax
0x18000a119  mov     rbx, rax
0x18000a11c  test    rax, rax
0x18000a11f  jz      loc_180009FFA
0x18000a125  mov     eax, dword ptr [rbp+70h+MultiByteStr]
0x18000a128  mov     r9d, r15d; cbMultiByte
0x18000a12b  mov     [rsp+0B0h+cbMultiByte], eax; cchWideChar
0x18000a12f  mov     r8, r14; lpMultiByteStr
0x18000a132  xor     edx, edx; dwFlags
0x18000a134  mov     [rsp+0B0h+lpMultiByteStr], rbx; lpWideCharStr
0x18000a139  xor     ecx, ecx; CodePage
0x18000a13b  call    cs:__imp_MultiByteToWideChar
0x18000a141  test    eax, eax
0x18000a143  jz      loc_180009FD8
0x18000a149  sub     eax, r12d
0x18000a14c  mov     r8, r12; unsigned __int64
0x18000a14f  dec     eax
0x18000a151  mov     rcx, r13; unsigned __int16 *
0x18000a154  cdqe
0x18000a156  lea     rdx, [rbx+rax*2]; unsigned __int16 *
0x18000a15a  call    ?CompareStrsCaseInsensitive@@YAHPEBG0_K@Z; CompareStrsCaseInsensitive(ushort const *,ushort const *,unsigned __int64)
0x18000a15f  mov     rcx, r14; Block
0x18000a162  mov     ebx, eax
  ... truncated ...
```
