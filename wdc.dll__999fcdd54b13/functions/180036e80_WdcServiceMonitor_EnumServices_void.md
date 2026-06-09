# WdcServiceMonitor::EnumServices(void)

- ea: `0x180036e80`
- end: `0x18003714f`
- name: `?EnumServices@WdcServiceMonitor@@QEAAJXZ`
- size: `719`
- prototype: `__int64 __fastcall(WdcServiceMonitor *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, installer_update`

## callers

- `0x180035ad0`
- `0x180081420`

## callees

- `0x180004a90`
- `0x180005ac0`
- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x1800150d0`
- `0x180016880`
- `0x180036e80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180037040`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180037040`
- `ADVAPI32!I_QueryTagInformation` at `0x180036ecc`
- `ADVAPI32!I_QueryTagInformation` at `0x180036ecc`
- `ADVAPI32!OpenSCManagerW` at `0x180036ee6`
- `ADVAPI32!OpenSCManagerW` at `0x180036ee6`
- `ADVAPI32!CloseServiceHandle` at `0x180037125`
- `ADVAPI32!CloseServiceHandle` at `0x180037125`
- `ADVAPI32!EnumServicesStatusExW` at `0x180036f89`
- `ADVAPI32!EnumServicesStatusExW` at `0x180036f89`
- `KERNEL32!GetLastError` at `0x180036efd`
- `KERNEL32!GetLastError` at `0x180036f93`
- `KERNEL32!GetLastError` at `0x180036efd`
- `KERNEL32!GetLastError` at `0x180036f93`
- `KERNEL32!LocalFree` at `0x180037133`
- `KERNEL32!LocalFree` at `0x180037133`

## string_xrefs

- `0x180036f32`: `base\diagnosis\pdui\perfmon\mon\service.cpp`
- `0x18003709e`: `base\diagnosis\pdui\perfmon\mon\service.cpp`
- `0x180036f2b`: `WdcServiceMonitor::EnumServices`
- `0x180037097`: `WdcServiceMonitor::EnumServices`

## pseudocode

```c
__int64 __fastcall WdcServiceMonitor::EnumServices(WdcServiceMonitor *this)
{
  WdcServiceMonitor *v1; // r13
  BYTE *v2; // rdi
  unsigned int *v3; // r15
  struct SC_HANDLE__ *v4; // rax
  struct SC_HANDLE__ *v5; // r14
  signed int LastError; // eax
  signed int v7; // ebx
  signed int v8; // eax
  DWORD cbBufSize; // esi
  signed int v10; // eax
  const char *v11; // rdx
  int v12; // r8d
  DWORD v13; // r14d
  struct _ENUM_SERVICE_STATUS_PROCESSW *v14; // rsi
  unsigned int v15; // r13d
  LPWSTR lpServiceName; // rcx
  __int64 v17; // rbx
  unsigned int v18; // eax
  __int64 v19; // r12
  unsigned int v20; // r9d
  int updated; // eax
  char *v22; // r11
  char *v23; // r10
  int v24; // eax
  WdcDataMonitor *v25; // rcx
  const char *v26; // rdx
  int v27; // r8d
  LPBYTE lpServices; // [rsp+20h] [rbp-49h]
  int v30; // [rsp+50h] [rbp-19h] BYREF
  unsigned int v31; // [rsp+54h] [rbp-15h]
  struct SC_HANDLE__ *v32; // [rsp+58h] [rbp-11h]
  unsigned int *v33; // [rsp+60h] [rbp-9h]
  LPWSTR v34; // [rsp+68h] [rbp-1h]
  __int64 v35; // [rsp+70h] [rbp+7h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+Fh]
  DWORD ResumeHandle; // [rsp+D8h] [rbp+6Fh] BYREF
  DWORD pcbBytesNeeded; // [rsp+E0h] [rbp+77h] BYREF
  DWORD ServicesReturned; // [rsp+E8h] [rbp+7Fh] BYREF

  v1 = this;
  pcbBytesNeeded = 0;
  ServicesReturned = 0;
  v2 = 0;
  ResumeHandle = 0;
  v30 = 0;
  v35 = 0;
  v3 = 0;
  hMem = 0;
  if ( !(unsigned int)I_QueryTagInformation(0, 3, &v35) )
    v3 = (unsigned int *)hMem;
  v33 = v3;
  v4 = OpenSCManagerW(0, 0, 4u);
  v32 = v4;
  v5 = v4;
  if ( !v4 || (v7 = 0, v4 == (struct SC_HANDLE__ *)-1LL) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( v7 >= 0 )
        goto LABEL_14;
    }
    else
    {
LABEL_9:
      v7 = -2147467259;
    }
    v8 = v7;
    goto LABEL_11;
  }
LABEL_14:
  cbBufSize = 0;
  ResumeHandle = 0;
  while ( 1 )
  {
    if ( EnumServicesStatusExW(
           v5,
           SC_ENUM_PROCESS_INFO,
           0x30u,
           3u,
           v2,
           cbBufSize,
           &pcbBytesNeeded,
           &ServicesReturned,
           &ResumeHandle,
           0) )
    {
      WdcLockObject::LockEnter(v1, &v30);
      v13 = 0;
      v14 = (struct _ENUM_SERVICE_STATUS_PROCESSW *)v2;
      while ( v13 < ServicesReturned )
      {
        v15 = 0;
        if ( v3 )
        {
          lpServiceName = v14->lpServiceName;
          v17 = 0;
          v18 = *v3;
          v19 = *((_QWORD *)v3 + 1);
          v34 = v14->lpServiceName;
          v31 = v18;
          while ( (unsigned int)v17 < v18 )
          {
            if ( *(_DWORD *)(v19 + 24 * v17) == 1 )
            {
              if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)(v19 + 24 * v17 + 8), lpServiceName) )
              {
                v15 = *(_DWORD *)(v19 + 24 * v17 + 4);
                break;
              }
              lpServiceName = v34;
            }
            v18 = v31;
            v17 = (unsigned int)(v17 + 1);
          }
          v3 = v33;
        }
        v20 = v15;
        v1 = this;
        updated = WdcServiceMonitor::UpdateService(this, v32, v14, v20);
        v7 = updated;
        if ( updated < 0 )
        {
          LODWORD(lpServices) = updated;
          WdcDebugMessage(
            "base\\diagnosis\\pdui\\perfmon\\mon\\service.cpp",
            "WdcServiceMonitor::EnumServices",
            0,
            L"FAILURE: 0x%08x",
            lpServices);
          goto LABEL_48;
        }
        ++v13;
        ++v14;
      }
      v22 = (char *)v1 + 88;
      v23 = (char *)*((_QWORD *)v1 + 11);
      if ( v23 != (char *)v1 + 88 )
      {
        do
        {
          v24 = *((_DWORD *)v23 + 13);
          v25 = (WdcDataMonitor *)(v24 & 0x10000000);
          if ( (v24 & 8) != 0 )
          {
            if ( (_DWORD)v25 )
            {
              *((_DWORD *)v23 + 13) = v24 & 0xEFFFFFFF;
              WdcDataMonitor::SetRowDirty(v25, (struct _WDC_DATA_INFO *)(v23 - 16));
            }
            *((_DWORD *)v23 + 13) &= ~8u;
          }
          else if ( !(_DWORD)v25 )
          {
            *((_DWORD *)v23 + 13) = v24 | 0x10000000;
            WdcDataMonitor::SetRowDirty(v25, (struct _WDC_DATA_INFO *)(v23 - 16));
          }
          v23 = *(char **)v23;
        }
        while ( v23 != v22 );
      }
LABEL_48:
      v5 = v32;
      goto LABEL_49;
    }
    v10 = GetLastError();
    if ( v10 != 234 )
      break;
    cbBufSize += pcbBytesNeeded;
    if ( v2 )
      WdcFree(v2, v11, v12);
    v2 = (BYTE *)WdcAlloc(cbBufSize, v11, v12);
    if ( !v2 )
    {
      v7 = -2147024882;
      LODWORD(lpServices) = -2147024882;
      goto LABEL_12;
    }
  }
  if ( !v10 )
    goto LABEL_9;
  if ( v10 > 0 )
    v7 = (unsigned __int16)v10 | 0x80070000;
  else
    v7 = v10;
  v8 = v7;
LABEL_11:
  LODWORD(lpServices) = v8;
LABEL_12:
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mon\\service.cpp",
    "WdcServiceMonitor::EnumServices",
    0,
    L"FAILURE: 0x%08x",
    lpServices);
LABEL_49:
  WdcLockObject::LockLeave(v1, &v30);
  if ( v2 )
    WdcFree(v2, v26, v27);
  if ( v5 )
    CloseServiceHandle(v5);
  if ( v3 )
    LocalFree(v3);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180036e80  mov     [rsp-8+arg_0], rcx
0x180036e85  push    rbp
0x180036e86  push    rbx
0x180036e87  push    rsi
0x180036e88  push    rdi
0x180036e89  push    r12
0x180036e8b  push    r13
0x180036e8d  push    r14
0x180036e8f  push    r15
0x180036e91  lea     rbp, [rsp-1Fh]
0x180036e96  sub     rsp, 88h
0x180036e9d  xor     r12d, r12d
0x180036ea0  lea     r8, [rbp+57h+var_50]
0x180036ea4  mov     r13, rcx
0x180036ea7  mov     [rbp+57h+arg_10], r12d
0x180036eab  xor     ecx, ecx
0x180036ead  mov     [rbp+57h+ServicesReturned], r12d
0x180036eb1  mov     edi, r12d
0x180036eb4  mov     [rbp+57h+ResumeHandle], r12d
0x180036eb8  lea     edx, [r12+3]
0x180036ebd  mov     [rbp+57h+var_70], r12d
0x180036ec1  mov     [rbp+57h+var_50], r12
0x180036ec5  mov     r15d, r12d
0x180036ec8  mov     [rbp+57h+hMem], r12
0x180036ecc  call    cs:__imp_I_QueryTagInformation
0x180036ed2  test    eax, eax
0x180036ed4  lea     r8d, [r12+4]; dwDesiredAccess
0x180036ed9  cmovz   r15, [rbp+57h+hMem]
0x180036ede  xor     edx, edx; lpDatabaseName
0x180036ee0  xor     ecx, ecx; lpMachineName
0x180036ee2  mov     [rbp+57h+var_60], r15
0x180036ee6  call    cs:__imp_OpenSCManagerW
0x180036eec  mov     [rbp+57h+var_68], rax
0x180036ef0  mov     r14, rax
0x180036ef3  mov     esi, 80070000h
0x180036ef8  test    rax, rax
0x180036efb  jnz     short loc_180036F43
0x180036efd  call    cs:__imp_GetLastError
0x180036f03  mov     ebx, eax
0x180036f05  test    eax, eax
0x180036f07  jz      short loc_180036F16
0x180036f09  jle     short loc_180036F10
0x180036f0b  movzx   ebx, ax
0x180036f0e  or      ebx, esi
0x180036f10  test    ebx, ebx
0x180036f12  jns     short loc_180036F4C
0x180036f14  jmp     short loc_180036F1B
0x180036f16  mov     ebx, 80004005h
0x180036f1b  mov     eax, ebx
0x180036f1d  mov     dword ptr [rsp+0C0h+lpServices], eax
0x180036f21  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180036f28  xor     r8d, r8d; int
0x180036f2b  lea     rdx, aWdcservicemoni_5; "WdcServiceMonitor::EnumServices"
0x180036f32  lea     rcx, aBaseDiagnosisP_45; "base\\diagnosis\\pdui\\perfmon\\mon\\se"...
0x180036f39  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180036f3e  jmp     loc_180037104
0x180036f43  mov     ebx, r12d
0x180036f46  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180036f4a  jz      short loc_180036EFD
0x180036f4c  mov     esi, r12d
0x180036f4f  mov     [rbp+57h+ResumeHandle], r12d
0x180036f53  mov     [rsp+0C0h+pszGroupName], r12; pszGroupName
0x180036f58  lea     rax, [rbp+57h+ResumeHandle]
0x180036f5c  mov     [rsp+0C0h+lpResumeHandle], rax; lpResumeHandle
0x180036f61  xor     edx, edx; InfoLevel
0x180036f63  lea     rax, [rbp+57h+ServicesReturned]
0x180036f67  mov     rcx, r14; hSCManager
0x180036f6a  mov     [rsp+0C0h+lpServicesReturned], rax; lpServicesReturned
0x180036f6f  lea     rax, [rbp+57h+arg_10]
0x180036f73  mov     [rsp+0C0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180036f78  mov     [rsp+0C0h+cbBufSize], esi; cbBufSize
0x180036f7c  lea     r9d, [rdx+3]; dwServiceState
0x180036f80  lea     r8d, [rdx+30h]; dwServiceType
0x180036f84  mov     [rsp+0C0h+lpServices], rdi; lpServices
0x180036f89  call    cs:__imp_EnumServicesStatusExW
0x180036f8f  test    eax, eax
0x180036f91  jnz     short loc_180036FF2
0x180036f93  call    cs:__imp_GetLastError
0x180036f99  cmp     eax, 0EAh
0x180036f9e  jz      short loc_180036FC1
0x180036fa0  test    eax, eax
0x180036fa2  jz      loc_180036F16
0x180036fa8  jg      short loc_180036FAE
0x180036faa  mov     ebx, eax
0x180036fac  jmp     short loc_180036FB7
0x180036fae  movzx   ebx, ax
0x180036fb1  or      ebx, 80070000h
0x180036fb7  mov     eax, ebx
0x180036fb9  test    ebx, ebx
0x180036fbb  js      loc_180036F1D
0x180036fc1  add     esi, [rbp+57h+arg_10]
0x180036fc4  test    rdi, rdi
0x180036fc7  jz      short loc_180036FD1
0x180036fc9  mov     rcx, rdi; void *
0x180036fcc  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x180036fd1  mov     ecx, esi; dwBytes
0x180036fd3  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180036fd8  mov     rdi, rax
0x180036fdb  test    rax, rax
0x180036fde  jnz     loc_180036F53
0x180036fe4  mov     ebx, 8007000Eh
0x180036fe9  mov     dword ptr [rsp+0C0h+lpServices], ebx
0x180036fed  jmp     loc_180036F21
0x180036ff2  lea     rdx, [rbp+57h+var_70]; int *
0x180036ff6  mov     rcx, r13; this
0x180036ff9  call    ?LockEnter@WdcLockObject@@QEAAXPEAH@Z; WdcLockObject::LockEnter(int *)
0x180036ffe  mov     r14d, r12d
0x180037001  mov     rsi, rdi
0x180037004  cmp     r14d, [rbp+57h+ServicesReturned]
0x180037008  jnb     loc_1800370AC
0x18003700e  mov     r13d, r12d
0x180037011  test    r15, r15
0x180037014  jz      short loc_180037061
0x180037016  mov     rcx, [rsi]
0x180037019  xor     ebx, ebx
0x18003701b  mov     eax, [r15]
0x18003701e  mov     r12, [r15+8]
0x180037022  mov     [rbp+57h+var_58], rcx
0x180037026  mov     [rbp+57h+var_6C], eax
0x180037029  cmp     ebx, eax
0x18003702b  jnb     short loc_18003705A
0x18003702d  lea     r15, [rbx+rbx*2]
0x180037031  cmp     dword ptr [r12+r15*8], 1
0x180037036  jnz     short loc_18003704E
0x180037038  mov     rdx, rcx
0x18003703b  mov     rcx, [r12+r15*8+8]
0x180037040  call    cs:__imp__o__wcsicmp
0x180037046  test    eax, eax
0x180037048  jz      short loc_180037055
0x18003704a  mov     rcx, [rbp+57h+var_58]
0x18003704e  mov     eax, [rbp+57h+var_6C]
0x180037051  inc     ebx
0x180037053  jmp     short loc_180037029
0x180037055  mov     r13d, [r12+r15*8+4]
0x18003705a  mov     r15, [rbp+57h+var_60]
0x18003705e  xor     r12d, r12d
0x180037061  mov     rdx, [rbp+57h+var_68]; struct SC_HANDLE__ *
0x180037065  mov     r9d, r13d; unsigned int
0x180037068  mov     r13, [rbp+57h+arg_0]
0x18003706c  mov     r8, rsi; struct _ENUM_SERVICE_STATUS_PROCESSW *
0x18003706f  mov     rcx, r13; this
0x180037072  call    ?UpdateService@WdcServiceMonitor@@AEAAJPEAUSC_HANDLE__@@PEAU_ENUM_SERVICE_STATUS_PROCESSW@@K@Z; WdcServiceMonitor::UpdateService(SC_HANDLE__ *,_ENUM_SERVICE_STATUS_PROCESSW *,ulong)
0x180037077  mov     ebx, eax
0x180037079  test    eax, eax
0x18003707b  js      short loc_180037089
0x18003707d  inc     r14d
0x180037080  add     rsi, 38h ; '8'
0x180037084  jmp     loc_180037004
0x180037089  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180037090  mov     dword ptr [rsp+0C0h+lpServices], eax
0x180037094  xor     r8d, r8d; int
0x180037097  lea     rdx, aWdcservicemoni_5; "WdcServiceMonitor::EnumServices"
0x18003709e  lea     rcx, aBaseDiagnosisP_45; "base\\diagnosis\\pdui\\perfmon\\mon\\se"...
0x1800370a5  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800370aa  jmp     short loc_180037100
0x1800370ac  lea     r11, [r13+58h]
0x1800370b0  mov     r10, [r11]
0x1800370b3  cmp     r10, r11
0x1800370b6  jz      short loc_180037100
0x1800370b8  mov     esi, 10000000h
0x1800370bd  mov     eax, [r10+34h]
0x1800370c1  mov     ecx, eax
0x1800370c3  and     ecx, esi; this
0x1800370c5  test    al, 8
0x1800370c7  jz      short loc_1800370E5
0x1800370c9  test    ecx, ecx
0x1800370cb  jz      short loc_1800370DE
0x1800370cd  btr     eax, 1Ch
0x1800370d1  lea     rdx, [r10-10h]; struct _WDC_DATA_INFO *
0x1800370d5  mov     [r10+34h], eax
0x1800370d9  call    ?SetRowDirty@WdcDataMonitor@@QEAAJPEAU_WDC_DATA_INFO@@@Z; WdcDataMonitor::SetRowDirty(_WDC_DATA_INFO *)
0x1800370de  and     dword ptr [r10+34h], 0FFFFFFF7h
0x1800370e3  jmp     short loc_1800370F8
0x1800370e5  test    ecx, ecx
0x1800370e7  jnz     short loc_1800370F8
0x1800370e9  or      eax, esi
0x1800370eb  lea     rdx, [r10-10h]; struct _WDC_DATA_INFO *
0x1800370ef  mov     [r10+34h], eax
0x1800370f3  call    ?SetRowDirty@WdcDataMonitor@@QEAAJPEAU_WDC_DATA_INFO@@@Z; WdcDataMonitor::SetRowDirty(_WDC_DATA_INFO *)
0x1800370f8  mov     r10, [r10]
0x1800370fb  cmp     r10, r11
0x1800370fe  jnz     short loc_1800370BD
0x180037100  mov     r14, [rbp+57h+var_68]
0x180037104  lea     rdx, [rbp+57h+var_70]; int *
0x180037108  mov     rcx, r13; this
0x18003710b  call    ?LockLeave@WdcLockObject@@QEAAXPEAH@Z; WdcLockObject::LockLeave(int *)
0x180037110  test    rdi, rdi
0x180037113  jz      short loc_18003711D
0x180037115  mov     rcx, rdi; void *
0x180037118  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x18003711d  test    r14, r14
0x180037120  jz      short loc_18003712B
0x180037122  mov     rcx, r14; hSCObject
0x180037125  call    cs:__imp_CloseServiceHandle
0x18003712b  test    r15, r15
0x18003712e  jz      short loc_180037139
0x180037130  mov     rcx, r15; hMem
0x180037133  call    cs:__imp_LocalFree
0x180037139  mov     eax, ebx
0x18003713b  add     rsp, 88h
0x180037142  pop     r15
0x180037144  pop     r14
0x180037146  pop     r13
0x180037148  pop     r12
0x18003714a  pop     rdi
0x18003714b  pop     rsi
0x18003714c  pop     rbx
0x18003714d  pop     rbp
0x18003714e  retn
```
