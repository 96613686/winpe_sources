# WdcStartService(ushort const *)

- ea: `0x180031248`
- end: `0x180031443`
- name: `?WdcStartService@@YAJPEBG@Z`
- size: `507`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180021c10`
- `0x18007c2b8`

## callees

- `0x18000b854`
- `0x180031248`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x18003125c`
- `ADVAPI32!OpenSCManagerW` at `0x18003125c`
- `ADVAPI32!OpenServiceW` at `0x180031296`
- `ADVAPI32!OpenServiceW` at `0x180031296`
- `ADVAPI32!CloseServiceHandle` at `0x180031424`
- `ADVAPI32!CloseServiceHandle` at `0x180031432`
- `ADVAPI32!CloseServiceHandle` at `0x180031424`
- `ADVAPI32!CloseServiceHandle` at `0x180031432`
- `ADVAPI32!StartServiceW` at `0x1800312cf`
- `ADVAPI32!StartServiceW` at `0x1800312cf`
- `KERNEL32!GetLastError` at `0x180031273`
- `KERNEL32!GetLastError` at `0x1800312a8`
- `KERNEL32!GetLastError` at `0x180031319`
- `KERNEL32!GetLastError` at `0x180031396`
- `KERNEL32!GetLastError` at `0x1800313db`
- `KERNEL32!GetLastError` at `0x180031273`
- `KERNEL32!GetLastError` at `0x1800312a8`
- `KERNEL32!GetLastError` at `0x180031319`
- `KERNEL32!GetLastError` at `0x180031396`
- `KERNEL32!GetLastError` at `0x1800313db`

## string_xrefs

- `0x1800312f7`: `WdcStartService`
- `0x180031349`: `WdcStartService`
- `0x180031374`: `WdcStartService`
- `0x1800313c6`: `WdcStartService`
- `0x180031409`: `WdcStartService`

## pseudocode

```c
__int64 __fastcall WdcStartService(LPCWSTR lpServiceName)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rsi
  signed int LastError; // eax
  signed int v5; // ebx
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rdi
  signed int v8; // eax
  signed int v9; // eax
  signed int v10; // eax
  signed int v11; // eax

  v2 = OpenSCManagerW(0, 0, 1u);
  v3 = v2;
  if ( !v2 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 >= 0 )
        goto LABEL_6;
    }
    else
    {
      v5 = -2147467259;
    }
    WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mon\\listview.cpp", "WdcStartService", 0, L"FAILURE: 0x%08x", v5);
    return (unsigned int)v5;
  }
  if ( v2 != (SC_HANDLE)-1LL )
    goto LABEL_6;
  v9 = GetLastError();
  v5 = v9;
  if ( !v9 )
  {
    v5 = -2147467259;
LABEL_22:
    WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mon\\listview.cpp", "WdcStartService", 0, L"FAILURE: 0x%08x", v5);
LABEL_43:
    CloseServiceHandle(v3);
    return (unsigned int)v5;
  }
  if ( v9 > 0 )
    v5 = (unsigned __int16)v9 | 0x80070000;
  if ( v5 < 0 )
    goto LABEL_22;
LABEL_6:
  v6 = OpenServiceW(v3, lpServiceName, 0x10u);
  v7 = v6;
  if ( !v6 )
  {
    v8 = GetLastError();
    v5 = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        v5 = (unsigned __int16)v8 | 0x80070000;
      if ( v5 >= 0 )
        goto LABEL_11;
    }
    else
    {
      v5 = -2147467259;
    }
    WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mon\\listview.cpp", "WdcStartService", 0, L"FAILURE: 0x%08x", v5);
    goto LABEL_42;
  }
  if ( v6 != (SC_HANDLE)-1LL )
    goto LABEL_11;
  v10 = GetLastError();
  v5 = v10;
  if ( v10 )
  {
    if ( v10 > 0 )
      v5 = (unsigned __int16)v10 | 0x80070000;
    if ( v5 >= 0 )
    {
LABEL_11:
      if ( StartServiceW(v7, 0, 0) )
      {
        v5 = 0;
        goto LABEL_40;
      }
      v11 = GetLastError();
      v5 = v11;
      if ( v11 )
      {
        if ( v11 > 0 )
          v5 = (unsigned __int16)v11 | 0x80070000;
        if ( v5 >= 0 )
        {
LABEL_40:
          if ( !v7 )
            goto LABEL_42;
          goto LABEL_41;
        }
      }
      else
      {
        v5 = -2147467259;
      }
      WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mon\\listview.cpp", "WdcStartService", 0, L"FAILURE: 0x%08x", v5);
      goto LABEL_40;
    }
  }
  else
  {
    v5 = -2147467259;
  }
  WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mon\\listview.cpp", "WdcStartService", 0, L"FAILURE: 0x%08x", v5);
LABEL_41:
  CloseServiceHandle(v7);
LABEL_42:
  if ( v3 )
    goto LABEL_43;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180031248  push    rbx
0x18003124a  push    rbp
0x18003124b  push    rsi
0x18003124c  push    rdi
0x18003124d  sub     rsp, 38h
0x180031251  xor     edx, edx; lpDatabaseName
0x180031253  mov     rdi, rcx
0x180031256  xor     ecx, ecx; lpMachineName
0x180031258  lea     r8d, [rdx+1]; dwDesiredAccess
0x18003125c  call    cs:__imp_OpenSCManagerW
0x180031262  mov     rsi, rax
0x180031265  mov     ebp, 80070000h
0x18003126a  test    rax, rax
0x18003126d  jnz     loc_18003130F
0x180031273  call    cs:__imp_GetLastError
0x180031279  mov     ebx, eax
0x18003127b  test    eax, eax
0x18003127d  jz      short loc_1800312E4
0x18003127f  jle     short loc_180031286
0x180031281  movzx   ebx, ax
0x180031284  or      ebx, ebp
0x180031286  test    ebx, ebx
0x180031288  js      short loc_1800312E9
0x18003128a  mov     r8d, 10h; dwDesiredAccess
0x180031290  mov     rdx, rdi; lpServiceName
0x180031293  mov     rcx, rsi; hSCManager
0x180031296  call    cs:__imp_OpenServiceW
0x18003129c  mov     rdi, rax
0x18003129f  test    rax, rax
0x1800312a2  jnz     loc_18003138C
0x1800312a8  call    cs:__imp_GetLastError
0x1800312ae  mov     ebx, eax
0x1800312b0  test    eax, eax
0x1800312b2  jz      loc_180031361
0x1800312b8  jle     short loc_1800312BF
0x1800312ba  movzx   ebx, ax
0x1800312bd  or      ebx, ebp
0x1800312bf  test    ebx, ebx
0x1800312c1  js      loc_180031366
0x1800312c7  xor     r8d, r8d; lpServiceArgVectors
0x1800312ca  xor     edx, edx; dwNumServiceArgs
0x1800312cc  mov     rcx, rdi; hService
0x1800312cf  call    cs:__imp_StartServiceW
0x1800312d5  test    eax, eax
0x1800312d7  jz      loc_1800313DB
0x1800312dd  xor     ebx, ebx
0x1800312df  jmp     loc_18003141C
0x1800312e4  mov     ebx, 80004005h
0x1800312e9  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800312f0  mov     [rsp+58h+var_38], ebx
0x1800312f4  xor     r8d, r8d; int
0x1800312f7  lea     rdx, aWdcstartservic; "WdcStartService"
0x1800312fe  lea     rcx, aBaseDiagnosisP_29; "base\\diagnosis\\pdui\\perfmon\\mon\\li"...
0x180031305  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18003130a  jmp     loc_180031438
0x18003130f  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180031313  jnz     loc_18003128A
0x180031319  call    cs:__imp_GetLastError
0x18003131f  mov     ebx, eax
0x180031321  test    eax, eax
0x180031323  jz      short loc_180031336
0x180031325  jle     short loc_18003132C
0x180031327  movzx   ebx, ax
0x18003132a  or      ebx, ebp
0x18003132c  test    ebx, ebx
0x18003132e  jns     loc_18003128A
0x180031334  jmp     short loc_18003133B
0x180031336  mov     ebx, 80004005h
0x18003133b  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180031342  mov     [rsp+58h+var_38], ebx
0x180031346  xor     r8d, r8d; int
0x180031349  lea     rdx, aWdcstartservic; "WdcStartService"
0x180031350  lea     rcx, aBaseDiagnosisP_29; "base\\diagnosis\\pdui\\perfmon\\mon\\li"...
0x180031357  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18003135c  jmp     loc_18003142F
0x180031361  mov     ebx, 80004005h
0x180031366  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18003136d  mov     [rsp+58h+var_38], ebx
0x180031371  xor     r8d, r8d; int
0x180031374  lea     rdx, aWdcstartservic; "WdcStartService"
0x18003137b  lea     rcx, aBaseDiagnosisP_29; "base\\diagnosis\\pdui\\perfmon\\mon\\li"...
0x180031382  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180031387  jmp     loc_18003142A
0x18003138c  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180031390  jnz     loc_1800312C7
0x180031396  call    cs:__imp_GetLastError
0x18003139c  mov     ebx, eax
0x18003139e  test    eax, eax
0x1800313a0  jz      short loc_1800313B3
0x1800313a2  jle     short loc_1800313A9
0x1800313a4  movzx   ebx, ax
0x1800313a7  or      ebx, ebp
0x1800313a9  test    ebx, ebx
0x1800313ab  jns     loc_1800312C7
0x1800313b1  jmp     short loc_1800313B8
0x1800313b3  mov     ebx, 80004005h
0x1800313b8  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800313bf  mov     [rsp+58h+var_38], ebx
0x1800313c3  xor     r8d, r8d; int
0x1800313c6  lea     rdx, aWdcstartservic; "WdcStartService"
0x1800313cd  lea     rcx, aBaseDiagnosisP_29; "base\\diagnosis\\pdui\\perfmon\\mon\\li"...
0x1800313d4  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800313d9  jmp     short loc_180031421
0x1800313db  call    cs:__imp_GetLastError
0x1800313e1  mov     ebx, eax
0x1800313e3  test    eax, eax
0x1800313e5  jz      short loc_1800313F4
0x1800313e7  jle     short loc_1800313EE
0x1800313e9  movzx   ebx, ax
0x1800313ec  or      ebx, ebp
0x1800313ee  test    ebx, ebx
0x1800313f0  jns     short loc_18003141C
0x1800313f2  jmp     short loc_1800313F9
0x1800313f4  mov     ebx, 80004005h
0x1800313f9  mov     eax, ebx
0x1800313fb  mov     [rsp+58h+var_38], ebx
0x1800313ff  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180031406  xor     r8d, r8d; int
0x180031409  lea     rdx, aWdcstartservic; "WdcStartService"
0x180031410  lea     rcx, aBaseDiagnosisP_29; "base\\diagnosis\\pdui\\perfmon\\mon\\li"...
0x180031417  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18003141c  test    rdi, rdi
0x18003141f  jz      short loc_18003142A
0x180031421  mov     rcx, rdi; hSCObject
0x180031424  call    cs:__imp_CloseServiceHandle
0x18003142a  test    rsi, rsi
0x18003142d  jz      short loc_180031438
0x18003142f  mov     rcx, rsi; hSCObject
0x180031432  call    cs:__imp_CloseServiceHandle
0x180031438  mov     eax, ebx
0x18003143a  add     rsp, 38h
0x18003143e  pop     rdi
0x18003143f  pop     rsi
0x180031440  pop     rbp
0x180031441  pop     rbx
0x180031442  retn
```
