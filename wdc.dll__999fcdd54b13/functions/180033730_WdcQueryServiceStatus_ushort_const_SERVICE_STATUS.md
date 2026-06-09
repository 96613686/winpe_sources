# WdcQueryServiceStatus(ushort const *,_SERVICE_STATUS *)

- ea: `0x180033730`
- end: `0x180033936`
- name: `?WdcQueryServiceStatus@@YAJPEBGPEAU_SERVICE_STATUS@@@Z`
- size: `518`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, LPSERVICE_STATUS lpServiceStatus)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180021c10`

## callees

- `0x18000b854`
- `0x180033730`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x180033749`
- `ADVAPI32!OpenSCManagerW` at `0x180033749`
- `ADVAPI32!OpenServiceW` at `0x180033785`
- `ADVAPI32!OpenServiceW` at `0x180033785`
- `ADVAPI32!QueryServiceStatus` at `0x1800337bd`
- `ADVAPI32!QueryServiceStatus` at `0x1800337bd`
- `ADVAPI32!CloseServiceHandle` at `0x180033915`
- `ADVAPI32!CloseServiceHandle` at `0x180033923`
- `ADVAPI32!CloseServiceHandle` at `0x180033915`
- `ADVAPI32!CloseServiceHandle` at `0x180033923`
- `KERNEL32!GetLastError` at `0x180033761`
- `KERNEL32!GetLastError` at `0x180033797`
- `KERNEL32!GetLastError` at `0x180033807`
- `KERNEL32!GetLastError` at `0x180033885`
- `KERNEL32!GetLastError` at `0x1800338cb`
- `KERNEL32!GetLastError` at `0x180033761`
- `KERNEL32!GetLastError` at `0x180033797`
- `KERNEL32!GetLastError` at `0x180033807`
- `KERNEL32!GetLastError` at `0x180033885`
- `KERNEL32!GetLastError` at `0x1800338cb`

## string_xrefs

- `0x1800337e5`: `WdcQueryServiceStatus`
- `0x180033838`: `WdcQueryServiceStatus`
- `0x180033863`: `WdcQueryServiceStatus`
- `0x1800338b6`: `WdcQueryServiceStatus`
- `0x1800338fa`: `WdcQueryServiceStatus`

## pseudocode

```c
__int64 __fastcall WdcQueryServiceStatus(LPCWSTR lpServiceName, LPSERVICE_STATUS lpServiceStatus)
{
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rsi
  signed int LastError; // eax
  signed int v7; // ebx
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // rdi
  signed int v10; // eax
  signed int v11; // eax
  signed int v12; // eax
  signed int v13; // eax

  v4 = OpenSCManagerW(0, 0, 1u);
  v5 = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( v7 >= 0 )
        goto LABEL_6;
    }
    else
    {
      v7 = -2147467259;
    }
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\listview.cpp",
      "WdcQueryServiceStatus",
      0,
      L"FAILURE: 0x%08x",
      v7);
    return (unsigned int)v7;
  }
  if ( v4 != (SC_HANDLE)-1LL )
    goto LABEL_6;
  v11 = GetLastError();
  v7 = v11;
  if ( !v11 )
  {
    v7 = -2147467259;
LABEL_22:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\listview.cpp",
      "WdcQueryServiceStatus",
      0,
      L"FAILURE: 0x%08x",
      v7);
LABEL_43:
    CloseServiceHandle(v5);
    return (unsigned int)v7;
  }
  if ( v11 > 0 )
    v7 = (unsigned __int16)v11 | 0x80070000;
  if ( v7 < 0 )
    goto LABEL_22;
LABEL_6:
  v8 = OpenServiceW(v5, lpServiceName, 4u);
  v9 = v8;
  if ( !v8 )
  {
    v10 = GetLastError();
    v7 = v10;
    if ( v10 )
    {
      if ( v10 > 0 )
        v7 = (unsigned __int16)v10 | 0x80070000;
      if ( v7 >= 0 )
        goto LABEL_11;
    }
    else
    {
      v7 = -2147467259;
    }
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\listview.cpp",
      "WdcQueryServiceStatus",
      0,
      L"FAILURE: 0x%08x",
      v7);
    goto LABEL_42;
  }
  if ( v8 != (SC_HANDLE)-1LL )
    goto LABEL_11;
  v12 = GetLastError();
  v7 = v12;
  if ( v12 )
  {
    if ( v12 > 0 )
      v7 = (unsigned __int16)v12 | 0x80070000;
    if ( v7 >= 0 )
    {
LABEL_11:
      if ( QueryServiceStatus(v9, lpServiceStatus) )
      {
        v7 = 0;
        goto LABEL_40;
      }
      v13 = GetLastError();
      v7 = v13;
      if ( v13 )
      {
        if ( v13 > 0 )
          v7 = (unsigned __int16)v13 | 0x80070000;
        if ( v7 >= 0 )
        {
LABEL_40:
          if ( !v9 )
            goto LABEL_42;
          goto LABEL_41;
        }
      }
      else
      {
        v7 = -2147467259;
      }
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mon\\listview.cpp",
        "WdcQueryServiceStatus",
        0,
        L"FAILURE: 0x%08x",
        v7);
      goto LABEL_40;
    }
  }
  else
  {
    v7 = -2147467259;
  }
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mon\\listview.cpp",
    "WdcQueryServiceStatus",
    0,
    L"FAILURE: 0x%08x",
    v7);
LABEL_41:
  CloseServiceHandle(v9);
LABEL_42:
  if ( v5 )
    goto LABEL_43;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180033730  push    rbx
0x180033732  push    rbp
0x180033733  push    rsi
0x180033734  push    rdi
0x180033735  push    r14
0x180033737  sub     rsp, 30h
0x18003373b  mov     rbp, rdx
0x18003373e  mov     rdi, rcx
0x180033741  xor     edx, edx; lpDatabaseName
0x180033743  xor     ecx, ecx; lpMachineName
0x180033745  lea     r8d, [rdx+1]; dwDesiredAccess
0x180033749  call    cs:__imp_OpenSCManagerW
0x18003374f  mov     rsi, rax
0x180033752  mov     r14d, 80070000h
0x180033758  test    rax, rax
0x18003375b  jnz     loc_1800337FD
0x180033761  call    cs:__imp_GetLastError
0x180033767  mov     ebx, eax
0x180033769  test    eax, eax
0x18003376b  jz      short loc_1800337D2
0x18003376d  jle     short loc_180033775
0x18003376f  movzx   ebx, ax
0x180033772  or      ebx, r14d
0x180033775  test    ebx, ebx
0x180033777  js      short loc_1800337D7
0x180033779  mov     r8d, 4; dwDesiredAccess
0x18003377f  mov     rdx, rdi; lpServiceName
0x180033782  mov     rcx, rsi; hSCManager
0x180033785  call    cs:__imp_OpenServiceW
0x18003378b  mov     rdi, rax
0x18003378e  test    rax, rax
0x180033791  jnz     loc_18003387B
0x180033797  call    cs:__imp_GetLastError
0x18003379d  mov     ebx, eax
0x18003379f  test    eax, eax
0x1800337a1  jz      loc_180033850
0x1800337a7  jle     short loc_1800337AF
0x1800337a9  movzx   ebx, ax
0x1800337ac  or      ebx, r14d
0x1800337af  test    ebx, ebx
0x1800337b1  js      loc_180033855
0x1800337b7  mov     rdx, rbp; lpServiceStatus
0x1800337ba  mov     rcx, rdi; hService
0x1800337bd  call    cs:__imp_QueryServiceStatus
0x1800337c3  test    eax, eax
0x1800337c5  jz      loc_1800338CB
0x1800337cb  xor     ebx, ebx
0x1800337cd  jmp     loc_18003390D
0x1800337d2  mov     ebx, 80004005h
0x1800337d7  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800337de  mov     [rsp+58h+var_38], ebx
0x1800337e2  xor     r8d, r8d; int
0x1800337e5  lea     rdx, aWdcqueryservic; "WdcQueryServiceStatus"
0x1800337ec  lea     rcx, aBaseDiagnosisP_29; "base\\diagnosis\\pdui\\perfmon\\mon\\li"...
0x1800337f3  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800337f8  jmp     loc_180033929
0x1800337fd  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180033801  jnz     loc_180033779
0x180033807  call    cs:__imp_GetLastError
0x18003380d  mov     ebx, eax
0x18003380f  test    eax, eax
0x180033811  jz      short loc_180033825
0x180033813  jle     short loc_18003381B
0x180033815  movzx   ebx, ax
0x180033818  or      ebx, r14d
0x18003381b  test    ebx, ebx
0x18003381d  jns     loc_180033779
0x180033823  jmp     short loc_18003382A
0x180033825  mov     ebx, 80004005h
0x18003382a  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180033831  mov     [rsp+58h+var_38], ebx
0x180033835  xor     r8d, r8d; int
0x180033838  lea     rdx, aWdcqueryservic; "WdcQueryServiceStatus"
0x18003383f  lea     rcx, aBaseDiagnosisP_29; "base\\diagnosis\\pdui\\perfmon\\mon\\li"...
0x180033846  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18003384b  jmp     loc_180033920
0x180033850  mov     ebx, 80004005h
0x180033855  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18003385c  mov     [rsp+58h+var_38], ebx
0x180033860  xor     r8d, r8d; int
0x180033863  lea     rdx, aWdcqueryservic; "WdcQueryServiceStatus"
0x18003386a  lea     rcx, aBaseDiagnosisP_29; "base\\diagnosis\\pdui\\perfmon\\mon\\li"...
0x180033871  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180033876  jmp     loc_18003391B
0x18003387b  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18003387f  jnz     loc_1800337B7
0x180033885  call    cs:__imp_GetLastError
0x18003388b  mov     ebx, eax
0x18003388d  test    eax, eax
0x18003388f  jz      short loc_1800338A3
0x180033891  jle     short loc_180033899
0x180033893  movzx   ebx, ax
0x180033896  or      ebx, r14d
0x180033899  test    ebx, ebx
0x18003389b  jns     loc_1800337B7
0x1800338a1  jmp     short loc_1800338A8
0x1800338a3  mov     ebx, 80004005h
0x1800338a8  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800338af  mov     [rsp+58h+var_38], ebx
0x1800338b3  xor     r8d, r8d; int
0x1800338b6  lea     rdx, aWdcqueryservic; "WdcQueryServiceStatus"
0x1800338bd  lea     rcx, aBaseDiagnosisP_29; "base\\diagnosis\\pdui\\perfmon\\mon\\li"...
0x1800338c4  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800338c9  jmp     short loc_180033912
0x1800338cb  call    cs:__imp_GetLastError
0x1800338d1  mov     ebx, eax
0x1800338d3  test    eax, eax
0x1800338d5  jz      short loc_1800338E5
0x1800338d7  jle     short loc_1800338DF
0x1800338d9  movzx   ebx, ax
0x1800338dc  or      ebx, r14d
0x1800338df  test    ebx, ebx
0x1800338e1  jns     short loc_18003390D
0x1800338e3  jmp     short loc_1800338EA
0x1800338e5  mov     ebx, 80004005h
0x1800338ea  mov     eax, ebx
0x1800338ec  mov     [rsp+58h+var_38], ebx
0x1800338f0  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800338f7  xor     r8d, r8d; int
0x1800338fa  lea     rdx, aWdcqueryservic; "WdcQueryServiceStatus"
0x180033901  lea     rcx, aBaseDiagnosisP_29; "base\\diagnosis\\pdui\\perfmon\\mon\\li"...
0x180033908  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18003390d  test    rdi, rdi
0x180033910  jz      short loc_18003391B
0x180033912  mov     rcx, rdi; hSCObject
0x180033915  call    cs:__imp_CloseServiceHandle
0x18003391b  test    rsi, rsi
0x18003391e  jz      short loc_180033929
0x180033920  mov     rcx, rsi; hSCObject
0x180033923  call    cs:__imp_CloseServiceHandle
0x180033929  mov     eax, ebx
0x18003392b  add     rsp, 30h
0x18003392f  pop     r14
0x180033931  pop     rdi
0x180033932  pop     rsi
0x180033933  pop     rbp
0x180033934  pop     rbx
0x180033935  retn
```
