# WdcServiceMonitor::AssignGroupString(SC_HANDLE__ *,_ENUM_SERVICE_STATUS_PROCESSW *,ushort * *)

- ea: `0x180006658`
- end: `0x180006945`
- name: `?AssignGroupString@WdcServiceMonitor@@AEAAJPEAUSC_HANDLE__@@PEAU_ENUM_SERVICE_STATUS_PROCESSW@@PEAPEAG@Z`
- size: `749`
- prototype: `__int64 __fastcall(WdcServiceMonitor *this, SC_HANDLE, struct _ENUM_SERVICE_STATUS_PROCESSW *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180005ac0`

## callees

- `0x180006658`
- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000681d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006846`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000681d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006846`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800067ff`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800067ff`
- `ADVAPI32!OpenServiceW` at `0x180006697`
- `ADVAPI32!OpenServiceW` at `0x180006697`
- `ADVAPI32!CloseServiceHandle` at `0x180006926`
- `ADVAPI32!CloseServiceHandle` at `0x180006926`
- `ADVAPI32!QueryServiceConfigW` at `0x180006794`
- `ADVAPI32!QueryServiceConfigW` at `0x180006794`
- `SHELL32!CommandLineToArgvW` at `0x1800067ca`
- `SHELL32!CommandLineToArgvW` at `0x1800067ca`
- `KERNEL32!GetLastError` at `0x1800066ae`
- `KERNEL32!GetLastError` at `0x18000673d`
- `KERNEL32!GetLastError` at `0x1800067a2`
- `KERNEL32!GetLastError` at `0x1800067d8`
- `KERNEL32!GetLastError` at `0x1800066ae`
- `KERNEL32!GetLastError` at `0x18000673d`
- `KERNEL32!GetLastError` at `0x1800067a2`
- `KERNEL32!GetLastError` at `0x1800067d8`
- `KERNEL32!LocalFree` at `0x1800068e6`
- `KERNEL32!LocalFree` at `0x1800068e6`
- `OLEAUT32!__imp_SysAllocString` at `0x180006887`
- `OLEAUT32!__imp_SysAllocString` at `0x180006887`
- `OLEAUT32!__imp_SysFreeString` at `0x180006876`
- `OLEAUT32!__imp_SysFreeString` at `0x180006876`

## string_xrefs

- `0x1800066f2`: `WdcServiceMonitor::AssignGroupString`
- `0x18000671f`: `WdcServiceMonitor::AssignGroupString`
- `0x18000676c`: `WdcServiceMonitor::AssignGroupString`
- `0x1800068c6`: `WdcServiceMonitor::AssignGroupString`
- `0x180006903`: `WdcServiceMonitor::AssignGroupString`
- `0x1800066fb`: `base\diagnosis\pdui\perfmon\mon\service.cpp`
- `0x180006726`: `base\diagnosis\pdui\perfmon\mon\service.cpp`
- `0x180006773`: `base\diagnosis\pdui\perfmon\mon\service.cpp`
- `0x1800068cd`: `base\diagnosis\pdui\perfmon\mon\service.cpp`
- `0x18000690a`: `base\diagnosis\pdui\perfmon\mon\service.cpp`

## pseudocode

```c
__int64 __fastcall WdcServiceMonitor::AssignGroupString(
        WdcServiceMonitor *this,
        SC_HANDLE a2,
        struct _ENUM_SERVICE_STATUS_PROCESSW *a3,
        unsigned __int16 **a4)
{
  int v4; // ebp
  SC_HANDLE v6; // rax
  const char *v7; // rdx
  int v8; // r8d
  SC_HANDLE v9; // r15
  signed int LastError; // eax
  signed int v11; // ebx
  struct _QUERY_SERVICE_CONFIGW *v12; // rax
  LPCWSTR *v13; // r14
  signed int v14; // eax
  signed int v15; // eax
  const wchar_t **v16; // rdi
  signed int v17; // eax
  wchar_t *v18; // rax
  const wchar_t *v19; // rax
  const OLECHAR *v20; // rsi
  unsigned __int16 *v21; // rax
  const char *v22; // rdx
  int v23; // r8d
  __int64 v25; // [rsp+20h] [rbp-38h]
  DWORD pcbBytesNeeded; // [rsp+60h] [rbp+8h] BYREF
  int v27; // [rsp+64h] [rbp+Ch]
  int pNumArgs; // [rsp+70h] [rbp+18h] BYREF

  v27 = HIDWORD(this);
  pcbBytesNeeded = 0;
  pNumArgs = 0;
  v4 = 1;
  v6 = OpenServiceW(a2, a3->lpServiceName, 1u);
  v9 = v6;
  if ( !v6 )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( v11 >= 0 )
        goto LABEL_6;
    }
    else
    {
      v11 = -2147467259;
    }
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\service.cpp",
      "WdcServiceMonitor::AssignGroupString",
      0,
      L"FAILURE: 0x%08x",
      v11);
    return (unsigned int)v11;
  }
  if ( v6 != (SC_HANDLE)-1LL )
    goto LABEL_6;
  v14 = GetLastError();
  v11 = v14;
  if ( !v14 )
  {
    v11 = -2147467259;
LABEL_17:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\service.cpp",
      "WdcServiceMonitor::AssignGroupString",
      0,
      L"FAILURE: 0x%08x",
      v11);
LABEL_48:
    CloseServiceHandle(v9);
    return (unsigned int)v11;
  }
  if ( v14 > 0 )
    v11 = (unsigned __int16)v14 | 0x80070000;
  if ( v11 < 0 )
    goto LABEL_17;
LABEL_6:
  pcbBytesNeeded = 1024;
  v12 = (struct _QUERY_SERVICE_CONFIGW *)WdcAlloc(0x400u, v7, v8);
  v13 = (LPCWSTR *)v12;
  if ( !v12 )
  {
    v11 = -2147024882;
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\service.cpp",
      "WdcServiceMonitor::AssignGroupString",
      0,
      L"FAILURE: 0x%08x",
      -2147024882);
    goto LABEL_47;
  }
  if ( QueryServiceConfigW(v9, v12, pcbBytesNeeded, &pcbBytesNeeded) )
  {
    v11 = 0;
  }
  else
  {
    v15 = GetLastError();
    v11 = v15;
    if ( !v15 )
    {
LABEL_44:
      v11 = -2147467259;
      goto LABEL_45;
    }
    if ( v15 > 0 )
      v11 = (unsigned __int16)v15 | 0x80070000;
    if ( v11 < 0 )
      goto LABEL_45;
  }
  v16 = (const wchar_t **)CommandLineToArgvW(v13[2], &pNumArgs);
  if ( v16 )
  {
LABEL_29:
    v18 = wcsrchr(*v16, 0x5Cu);
    if ( v18 )
      v19 = v18 + 1;
    else
      v19 = *v16;
    if ( !(unsigned int)_o__wcsicmp(L"svchost.exe", v19) )
    {
      while ( v4 < pNumArgs )
      {
        if ( !(unsigned int)_o__wcsicmp(L"-k", v16[v4]) )
        {
          if ( v4 + 1 < pNumArgs )
          {
            _mm_lfence();
            v20 = v16[v4 + 1];
            if ( *v20 )
            {
              if ( *a4 )
              {
                SysFreeString(*a4);
                *a4 = 0;
              }
              v21 = SysAllocString(v20);
              if ( v21 )
              {
                *a4 = v21;
                v11 = 0;
              }
              else
              {
                WdcDebugMessage(
                  "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
                  "WdcAssignString",
                  0,
                  L"FAILURE: 0x%08x",
                  -2147024882);
                LODWORD(v25) = -2147024882;
                v11 = -2147024882;
                WdcDebugMessage(
                  "base\\diagnosis\\pdui\\perfmon\\mon\\service.cpp",
                  "WdcServiceMonitor::AssignGroupString",
                  0,
                  L"FAILURE: 0x%08x",
                  v25);
              }
            }
          }
          break;
        }
        ++v4;
      }
    }
    LocalFree(v16);
    goto LABEL_46;
  }
  v17 = GetLastError();
  v11 = v17;
  if ( !v17 )
    goto LABEL_44;
  if ( v17 > 0 )
    v11 = (unsigned __int16)v17 | 0x80070000;
  if ( v11 >= 0 )
    goto LABEL_29;
LABEL_45:
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mon\\service.cpp",
    "WdcServiceMonitor::AssignGroupString",
    0,
    L"FAILURE: 0x%08x",
    v11);
LABEL_46:
  WdcFree(v13, v22, v23);
LABEL_47:
  if ( v9 )
    goto LABEL_48;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180006658  mov     [rsp+arg_8], rbx
0x18000665d  mov     [rsp+arg_18], rbp
0x180006662  mov     qword ptr [rsp+pcbBytesNeeded], rcx
0x180006667  push    rsi
0x180006668  push    rdi
0x180006669  push    r12
0x18000666b  push    r14
0x18000666d  push    r15
0x18000666f  sub     rsp, 30h
0x180006673  mov     rax, r8
0x180006676  mov     [rsp+58h+pcbBytesNeeded], 0
0x18000667e  mov     rcx, rdx; hSCManager
0x180006681  mov     [rsp+58h+pNumArgs], 0
0x180006689  mov     ebp, 1
0x18000668e  mov     r12, r9
0x180006691  mov     r8d, ebp; dwDesiredAccess
0x180006694  mov     rdx, [rax]; lpServiceName
0x180006697  call    cs:__imp_OpenServiceW
0x18000669d  mov     r15, rax
0x1800066a0  mov     esi, 80070000h
0x1800066a5  test    rax, rax
0x1800066a8  jnz     loc_180006737
0x1800066ae  call    cs:__imp_GetLastError
0x1800066b4  mov     ebx, eax
0x1800066b6  test    eax, eax
0x1800066b8  jz      short loc_18000670C
0x1800066ba  jle     short loc_1800066C1
0x1800066bc  movzx   ebx, ax
0x1800066bf  or      ebx, esi
0x1800066c1  test    ebx, ebx
0x1800066c3  js      short loc_180006711
0x1800066c5  mov     ecx, 400h; dwBytes
0x1800066ca  mov     [rsp+58h+pcbBytesNeeded], ecx
0x1800066ce  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x1800066d3  mov     r14, rax
0x1800066d6  test    rax, rax
0x1800066d9  jnz     loc_180006784
0x1800066df  mov     esi, 8007000Eh
0x1800066e4  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800066eb  xor     r8d, r8d; int
0x1800066ee  mov     dword ptr [rsp+58h+var_38], esi
0x1800066f2  lea     rdx, aWdcservicemoni_1; "WdcServiceMonitor::AssignGroupString"
0x1800066f9  mov     ebx, esi
0x1800066fb  lea     rcx, aBaseDiagnosisP_45; "base\\diagnosis\\pdui\\perfmon\\mon\\se"...
0x180006702  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180006707  jmp     loc_18000691E
0x18000670c  mov     ebx, 80004005h
0x180006711  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180006718  mov     dword ptr [rsp+58h+var_38], ebx
0x18000671c  xor     r8d, r8d; int
0x18000671f  lea     rdx, aWdcservicemoni_1; "WdcServiceMonitor::AssignGroupString"
0x180006726  lea     rcx, aBaseDiagnosisP_45; "base\\diagnosis\\pdui\\perfmon\\mon\\se"...
0x18000672d  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180006732  jmp     loc_18000692C
0x180006737  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18000673b  jnz     short loc_1800066C5
0x18000673d  call    cs:__imp_GetLastError
0x180006743  mov     ebx, eax
0x180006745  test    eax, eax
0x180006747  jz      short loc_180006759
0x180006749  jle     short loc_180006750
0x18000674b  movzx   ebx, ax
0x18000674e  or      ebx, esi
0x180006750  test    ebx, ebx
0x180006752  js      short loc_18000675E
0x180006754  jmp     loc_1800066C5
0x180006759  mov     ebx, 80004005h
0x18000675e  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180006765  mov     dword ptr [rsp+58h+var_38], ebx
0x180006769  xor     r8d, r8d; int
0x18000676c  lea     rdx, aWdcservicemoni_1; "WdcServiceMonitor::AssignGroupString"
0x180006773  lea     rcx, aBaseDiagnosisP_45; "base\\diagnosis\\pdui\\perfmon\\mon\\se"...
0x18000677a  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18000677f  jmp     loc_180006923
0x180006784  mov     r8d, [rsp+58h+pcbBytesNeeded]; cbBufSize
0x180006789  lea     r9, [rsp+58h+pcbBytesNeeded]; pcbBytesNeeded
0x18000678e  mov     rdx, r14; lpServiceConfig
0x180006791  mov     rcx, r15; hService
0x180006794  call    cs:__imp_QueryServiceConfigW
0x18000679a  test    eax, eax
0x18000679c  jz      short loc_1800067A2
0x18000679e  xor     ebx, ebx
0x1800067a0  jmp     short loc_1800067C1
0x1800067a2  call    cs:__imp_GetLastError
0x1800067a8  mov     ebx, eax
0x1800067aa  test    eax, eax
0x1800067ac  jz      loc_1800068EE
0x1800067b2  jle     short loc_1800067B9
0x1800067b4  movzx   ebx, ax
0x1800067b7  or      ebx, esi
0x1800067b9  test    ebx, ebx
0x1800067bb  js      loc_1800068F3
0x1800067c1  mov     rcx, [r14+10h]; lpCmdLine
0x1800067c5  lea     rdx, [rsp+58h+pNumArgs]; pNumArgs
0x1800067ca  call    cs:__imp_CommandLineToArgvW
0x1800067d0  mov     rdi, rax
0x1800067d3  test    rax, rax
0x1800067d6  jnz     short loc_1800067F7
0x1800067d8  call    cs:__imp_GetLastError
0x1800067de  mov     ebx, eax
0x1800067e0  test    eax, eax
0x1800067e2  jz      loc_1800068EE
0x1800067e8  jle     short loc_1800067EF
0x1800067ea  movzx   ebx, ax
0x1800067ed  or      ebx, esi
0x1800067ef  test    ebx, ebx
0x1800067f1  js      loc_1800068F3
0x1800067f7  mov     rcx, [rdi]; Str
0x1800067fa  mov     edx, 5Ch ; '\'; Ch
0x1800067ff  call    cs:__imp_wcsrchr
0x180006805  test    rax, rax
0x180006808  jnz     short loc_18000680F
0x18000680a  mov     rax, [rdi]
0x18000680d  jmp     short loc_180006813
0x18000680f  add     rax, 2
0x180006813  mov     rdx, rax
0x180006816  lea     rcx, aSvchostExe; "svchost.exe"
0x18000681d  call    cs:__imp__o__wcsicmp
0x180006823  test    eax, eax
0x180006825  jnz     loc_1800068E3
0x18000682b  cmp     ebp, [rsp+58h+pNumArgs]
0x18000682f  jge     loc_1800068E3
0x180006835  lea     esi, [rbp+1]
0x180006838  movsxd  rbp, ebp
0x18000683b  lea     rcx, aK_0; "-k"
0x180006842  mov     rdx, [rdi+rbp*8]
0x180006846  call    cs:__imp__o__wcsicmp
0x18000684c  test    eax, eax
0x18000684e  jz      short loc_180006854
0x180006850  mov     ebp, esi
0x180006852  jmp     short loc_18000682B
0x180006854  cmp     esi, [rsp+58h+pNumArgs]
0x180006858  jge     loc_1800068E3
0x18000685e  lfence
0x180006861  mov     rsi, [rdi+rbp*8+8]
0x180006866  xor     eax, eax
0x180006868  cmp     ax, [rsi]
0x18000686b  jz      short loc_1800068E3
0x18000686d  mov     rcx, [r12]; bstrString
0x180006871  test    rcx, rcx
0x180006874  jz      short loc_180006884
0x180006876  call    cs:__imp_SysFreeString
0x18000687c  mov     qword ptr [r12], 0
0x180006884  mov     rcx, rsi; psz
0x180006887  call    cs:__imp_SysAllocString
0x18000688d  test    rax, rax
0x180006890  jnz     short loc_1800068DD
0x180006892  mov     esi, 8007000Eh
0x180006897  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18000689e  xor     r8d, r8d; int
0x1800068a1  mov     dword ptr [rsp+58h+var_38], esi
0x1800068a5  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x1800068ac  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x1800068b3  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800068b8  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800068bf  mov     dword ptr [rsp+58h+var_38], esi
0x1800068c3  xor     r8d, r8d; int
0x1800068c6  lea     rdx, aWdcservicemoni_1; "WdcServiceMonitor::AssignGroupString"
0x1800068cd  lea     rcx, aBaseDiagnosisP_45; "base\\diagnosis\\pdui\\perfmon\\mon\\se"...
0x1800068d4  mov     ebx, esi
0x1800068d6  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800068db  jmp     short loc_1800068E3
0x1800068dd  mov     [r12], rax
0x1800068e1  xor     ebx, ebx
0x1800068e3  mov     rcx, rdi; hMem
0x1800068e6  call    cs:__imp_LocalFree
0x1800068ec  jmp     short loc_180006916
0x1800068ee  mov     ebx, 80004005h
0x1800068f3  mov     eax, ebx
0x1800068f5  mov     dword ptr [rsp+58h+var_38], ebx
0x1800068f9  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180006900  xor     r8d, r8d; int
0x180006903  lea     rdx, aWdcservicemoni_1; "WdcServiceMonitor::AssignGroupString"
0x18000690a  lea     rcx, aBaseDiagnosisP_45; "base\\diagnosis\\pdui\\perfmon\\mon\\se"...
0x180006911  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180006916  mov     rcx, r14; void *
0x180006919  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x18000691e  test    r15, r15
0x180006921  jz      short loc_18000692C
0x180006923  mov     rcx, r15; hSCObject
0x180006926  call    cs:__imp_CloseServiceHandle
0x18000692c  mov     rbp, [rsp+58h+arg_18]
0x180006931  mov     eax, ebx
0x180006933  mov     rbx, [rsp+58h+arg_8]
0x180006938  add     rsp, 30h
0x18000693c  pop     r15
0x18000693e  pop     r14
0x180006940  pop     r12
0x180006942  pop     rdi
0x180006943  pop     rsi
0x180006944  retn
```
