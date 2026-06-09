# CUserConfig::LoadConfigFromDC(int,ushort *,ushort *,ushort *,_USERCONFIGW *,ulong,ulong *)

- ea: `0x18006f2ac`
- end: `0x18006f5bd`
- name: `?LoadConfigFromDC@CUserConfig@@AEAAKHPEAG00PEAU_USERCONFIGW@@KPEAK@Z`
- size: `785`
- prototype: `unsigned int(CUserConfig *__hidden this, int, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, struct _USERCONFIGW *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006f6a0`

## callees

- `0x180009940`
- `0x180033f60`
- `0x18006efac`
- `0x18006f02c`
- `0x18006f078`
- `0x18006f2ac`
- `0x1800a38f8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006f302`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006f39f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006f3c0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006f4cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006f538`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006f302`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006f39f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006f3c0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006f4cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006f538`
- `logoncli!DsGetDcNameW` at `0x18006f43a`
- `logoncli!DsGetDcNameW` at `0x18006f479`
- `logoncli!DsGetDcNameW` at `0x18006f43a`
- `logoncli!DsGetDcNameW` at `0x18006f479`
- `netutils!NetApiBufferFree` at `0x18006f57d`
- `netutils!NetApiBufferFree` at `0x18006f57d`
- `REGAPI!RegUserConfigQuery` at `0x18006f37a`
- `REGAPI!RegUserConfigQuery` at `0x18006f520`
- `REGAPI!RegUserConfigQuery` at `0x18006f37a`
- `REGAPI!RegUserConfigQuery` at `0x18006f520`

## string_xrefs

- `0x18006f31a`: `Loading user configuration from %ws for user %ws`
- `0x18006f327`: `CUserConfig::LoadConfigFromDC`
- `0x18006f4a6`: `CUserConfig::LoadConfigFromDC`
- `0x18006f345`: `RegUserConfigQuery`
- `0x18006f3ae`: `RegUserConfigQuery 1 - to server '%S', failed with 0x%x, took %d ms`
- `0x18006f3cf`: `RegUserConfigQuery 1 - to server '%S', Return=0x%x, took %d ms`
- `0x18006f408`: `RegUserConfigQuery 1 failed with 0x%08x - will retry`
- `0x18006f4e6`: `RegUserConfigQuery from DC`
- `0x18006f554`: `RegUserConfigQuery 2 - to server '%S', failed with 0x%x, took %d ms`
- `0x18006f563`: `RegUserConfigQuery 2 - to server '%S', Return=0x%x, took %d ms`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUserConfig::LoadConfigFromDC(
        CUserConfig *this,
        int a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        struct _USERCONFIGW *a6,
        unsigned int a7,
        unsigned int *a8)
{
  DWORD TickCount; // esi
  unsigned int v12; // ebx
  DWORD v13; // eax
  __int64 v14; // r9
  const char *v15; // rdx
  int v16; // eax
  DWORD DcNameW; // eax
  signed int v18; // eax
  unsigned int v19; // r8d
  unsigned __int16 *DomainControllerName; // rdi
  DWORD v21; // esi
  ULONG Flags[2]; // [rsp+20h] [rbp-E0h]
  ULONG Flagsa[2]; // [rsp+20h] [rbp-E0h]
  unsigned int DomainControllerInfo; // [rsp+28h] [rbp-D8h]
  PDOMAIN_CONTROLLER_INFOW v26; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int *v27; // [rsp+38h] [rbp-C8h]
  struct _EVENT_DESCRIPTOR v28; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE Parameter[80]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v30[176]; // [rsp+A0h] [rbp-60h] BYREF

  v27 = a8;
  v26 = 0;
  TickCount = GetTickCount();
  CGenericTraceEx::CGenericTraceEx(
    (CGenericTraceEx *)v30,
    "CUserConfig::LoadConfigFromDC",
    4u,
    "Loading user configuration from %ws for user %ws",
    a4);
  v28 = (struct _EVENT_DESCRIPTOR)EVENT_LOAD_USERCONFIG_FROM_SERVER;
  CUserConfigMonitor::CUserConfigMonitor(Parameter, &v28, a4, a5, "RegUserConfigQuery", (unsigned int)a5);
  v12 = RegUserConfigQuery(a4, a5, a6, 2536, a8);
  CUserConfigMonitor::~CUserConfigMonitor((CUserConfigMonitor *)Parameter);
  if ( v12 )
  {
    if ( (g_DebugTraceComponent & 4) != 0 )
    {
      v13 = GetTickCount();
      v14 = v12;
      v15 = "RegUserConfigQuery 1 - to server '%S', failed with 0x%x, took %d ms";
LABEL_6:
      Flags[0] = v13 - TickCount;
      _DbgPrintMessage(2, v15, a4, v14, *(_QWORD *)Flags);
    }
  }
  else if ( (g_DebugTraceComponent & 4) != 0 )
  {
    v13 = GetTickCount();
    v14 = 0;
    v15 = "RegUserConfigQuery 1 - to server '%S', Return=0x%x, took %d ms";
    goto LABEL_6;
  }
  if ( a2 )
  {
    if ( v12 > 8 || (v16 = 293, !_bittest(&v16, v12)) )
    {
      _DbgPrintMessage(4, "RegUserConfigQuery 1 failed with 0x%08x - will retry", v12);
      DcNameW = DsGetDcNameW(0, a3, 0, 0, 0x40000001u, &v26);
      if ( DcNameW
        && (_DbgPrintMessage(
              4,
              "DsGetDcName failed with 0x%08x for (DS_FORCE_REDISCOVERY | DS_RETURN_DNS_NAME) - will retry",
              DcNameW),
            v18 = DsGetDcNameW(0, a3, 0, 0, 1u, &v26),
            (v12 = v18) != 0) )
      {
        if ( v18 > 0 )
          v19 = (unsigned __int16)v18 | 0x80070000;
        else
          v19 = v18;
        _DbgPrintMessage(8, "DsGetDcName 2 failed: 0x%x in %s", v19, "CUserConfig::LoadConfigFromDC");
      }
      else
      {
        DomainControllerName = v26->DomainControllerName;
        v21 = GetTickCount();
        v28 = (struct _EVENT_DESCRIPTOR)EVENT_LOAD_USERCONFIG_FROM_SERVER;
        CUserConfigMonitor::CUserConfigMonitor(
          Parameter,
          &v28,
          DomainControllerName,
          a5,
          "RegUserConfigQuery from DC",
          DomainControllerInfo);
        v12 = RegUserConfigQuery(DomainControllerName, a5, a6, 2536, v27);
        CUserConfigMonitor::~CUserConfigMonitor((CUserConfigMonitor *)Parameter);
        Flagsa[0] = GetTickCount() - v21;
        if ( v12 )
          _DbgPrintMessage(
            4,
            "RegUserConfigQuery 2 - to server '%S', failed with 0x%x, took %d ms",
            DomainControllerName,
            v12,
            *(_QWORD *)Flagsa);
        else
          _DbgPrintMessage(
            1,
            "RegUserConfigQuery 2 - to server '%S', Return=0x%x, took %d ms",
            DomainControllerName,
            0,
            *(_QWORD *)Flagsa);
      }
    }
  }
  if ( v26 )
    NetApiBufferFree(v26);
  CGenericTraceEx::~CGenericTraceEx((CGenericTraceEx *)v30);
  return v12;
}

```

## disassembly

```asm
0x18006f2ac  mov     [rsp-8+arg_0], rbx
0x18006f2b1  push    rbp
0x18006f2b2  push    rsi
0x18006f2b3  push    rdi
0x18006f2b4  push    r12
0x18006f2b6  push    r13
0x18006f2b8  push    r14
0x18006f2ba  push    r15
0x18006f2bc  lea     rbp, [rsp-60h]
0x18006f2c1  sub     rsp, 160h
0x18006f2c8  mov     rax, cs:__security_cookie
0x18006f2cf  xor     rax, rsp
0x18006f2d2  mov     [rbp+90h+var_40], rax
0x18006f2d6  mov     rdi, r9
0x18006f2d9  mov     r14, r8
0x18006f2dc  mov     r15d, edx
0x18006f2df  mov     r12, [rbp+90h+arg_20]
0x18006f2e6  mov     r13, [rbp+90h+arg_28]
0x18006f2ed  mov     rbx, [rbp+90h+arg_38]
0x18006f2f4  mov     [rsp+190h+var_158], rbx
0x18006f2f9  mov     [rsp+190h+var_160], 0
0x18006f302  call    cs:__imp_GetTickCount
0x18006f309  nop     dword ptr [rax+rax+00h]
0x18006f30e  mov     esi, eax
0x18006f310  mov     [rsp+190h+DomainControllerInfo], r12; unsigned int
0x18006f315  mov     qword ptr [rsp+190h+Flags], rdi
0x18006f31a  lea     r9, aLoadingUserCon_0; "Loading user configuration from %ws for"...
0x18006f321  mov     r8d, 4; unsigned int
0x18006f327  lea     rdx, aCuserconfigLoa; "CUserConfig::LoadConfigFromDC"
0x18006f32e  lea     rcx, [rbp+90h+var_F0]; this
0x18006f332  call    ??0CGenericTraceEx@@QEAA@PEBDK0ZZ; CGenericTraceEx::CGenericTraceEx(char const *,ulong,char const *,...)
0x18006f337  nop
0x18006f338  movups  xmm0, cs:EVENT_LOAD_USERCONFIG_FROM_SERVER
0x18006f33f  movdqu  xmmword ptr [rsp+190h+var_150.Id], xmm0
0x18006f345  lea     rax, aReguserconfigq_5; "RegUserConfigQuery"
0x18006f34c  mov     qword ptr [rsp+190h+Flags], rax; char *
0x18006f351  mov     r9, r12; unsigned __int16 *
0x18006f354  mov     r8, rdi; unsigned __int16 *
0x18006f357  lea     rdx, [rsp+190h+var_150]; struct _EVENT_DESCRIPTOR
0x18006f35c  lea     rcx, [rsp+190h+Parameter]; Parameter
0x18006f361  call    ??0CUserConfigMonitor@@QEAA@U_EVENT_DESCRIPTOR@@PEAG1PEBDK@Z; CUserConfigMonitor::CUserConfigMonitor(_EVENT_DESCRIPTOR,ushort *,ushort *,char const *,ulong)
0x18006f366  mov     qword ptr [rsp+190h+Flags], rbx
0x18006f36b  mov     r9d, 9E8h
0x18006f371  mov     r8, r13
0x18006f374  mov     rdx, r12
0x18006f377  mov     rcx, rdi
0x18006f37a  call    cs:__imp_RegUserConfigQuery
0x18006f381  nop     dword ptr [rax+rax+00h]
0x18006f386  mov     ebx, eax
0x18006f388  lea     rcx, [rsp+190h+Parameter]; this
0x18006f38d  call    ??1CUserConfigMonitor@@UEAA@XZ; CUserConfigMonitor::~CUserConfigMonitor(void)
0x18006f392  test    ebx, ebx
0x18006f394  jz      short loc_18006F3B7
0x18006f396  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18006f39d  jz      short loc_18006F3E9
0x18006f39f  call    cs:__imp_GetTickCount
0x18006f3a6  nop     dword ptr [rax+rax+00h]
0x18006f3ab  mov     r9d, ebx
0x18006f3ae  lea     rdx, aReguserconfigq_0; "RegUserConfigQuery 1 - to server '%S', "...
0x18006f3b5  jmp     short loc_18006F3D6
0x18006f3b7  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18006f3be  jz      short loc_18006F3E9
0x18006f3c0  call    cs:__imp_GetTickCount
0x18006f3c7  nop     dword ptr [rax+rax+00h]
0x18006f3cc  xor     r9d, r9d
0x18006f3cf  lea     rdx, aReguserconfigq_6; "RegUserConfigQuery 1 - to server '%S', "...
0x18006f3d6  sub     eax, esi
0x18006f3d8  mov     [rsp+190h+Flags], eax
0x18006f3dc  mov     r8, rdi
0x18006f3df  mov     ecx, 2; int
0x18006f3e4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006f3e9  test    r15d, r15d
0x18006f3ec  jz      loc_18006F573
0x18006f3f2  cmp     ebx, 8
0x18006f3f5  ja      short loc_18006F405
0x18006f3f7  mov     eax, 125h
0x18006f3fc  bt      eax, ebx
0x18006f3ff  jb      loc_18006F573
0x18006f405  mov     r8d, ebx
0x18006f408  lea     rdx, aReguserconfigq_1; "RegUserConfigQuery 1 failed with 0x%08x"...
0x18006f40f  mov     r15d, 4
0x18006f415  mov     ecx, r15d; int
0x18006f418  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006f41d  lea     rax, [rsp+190h+var_160]
0x18006f422  mov     [rsp+190h+DomainControllerInfo], rax; unsigned int
0x18006f427  mov     [rsp+190h+Flags], 40000001h; Flags
0x18006f42f  xor     r9d, r9d; SiteName
0x18006f432  xor     r8d, r8d; DomainGuid
0x18006f435  mov     rdx, r14; DomainName
0x18006f438  xor     ecx, ecx; ComputerName
0x18006f43a  call    cs:__imp_DsGetDcNameW
0x18006f441  nop     dword ptr [rax+rax+00h]
0x18006f446  test    eax, eax
0x18006f448  jz      short loc_18006F4C3
0x18006f44a  mov     r8d, eax
0x18006f44d  lea     rdx, aDsgetdcnameFai_0; "DsGetDcName failed with 0x%08x for (DS_"...
0x18006f454  mov     ecx, r15d; int
0x18006f457  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006f45c  lea     rax, [rsp+190h+var_160]
0x18006f461  mov     [rsp+190h+DomainControllerInfo], rax; DomainControllerInfo
0x18006f466  mov     [rsp+190h+Flags], 1; Flags
0x18006f46e  xor     r9d, r9d; SiteName
0x18006f471  xor     r8d, r8d; DomainGuid
0x18006f474  mov     rdx, r14; DomainName
0x18006f477  xor     ecx, ecx; ComputerName
0x18006f479  call    cs:__imp_DsGetDcNameW
0x18006f480  nop     dword ptr [rax+rax+00h]
0x18006f485  mov     ebx, eax
0x18006f487  test    eax, eax
0x18006f489  jz      short loc_18006F4C3
0x18006f48b  xor     edi, edi
0x18006f48d  test    eax, eax
0x18006f48f  jg      short loc_18006F496
0x18006f491  mov     r8d, eax
0x18006f494  jmp     short loc_18006F4A1
0x18006f496  movzx   r8d, ax
0x18006f49a  or      r8d, 80070000h
0x18006f4a1  test    r8d, r8d
0x18006f4a4  jns     short loc_18006F4CB
0x18006f4a6  lea     r9, aCuserconfigLoa; "CUserConfig::LoadConfigFromDC"
0x18006f4ad  lea     rdx, aDsgetdcname2Fa; "DsGetDcName 2 failed: 0x%x in %s"
0x18006f4b4  mov     ecx, 8; int
0x18006f4b9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006f4be  jmp     loc_18006F573
0x18006f4c3  mov     rax, [rsp+190h+var_160]
0x18006f4c8  mov     rdi, [rax]
0x18006f4cb  call    cs:__imp_GetTickCount
0x18006f4d2  nop     dword ptr [rax+rax+00h]
0x18006f4d7  mov     esi, eax
0x18006f4d9  movups  xmm0, cs:EVENT_LOAD_USERCONFIG_FROM_SERVER
0x18006f4e0  movdqu  xmmword ptr [rsp+190h+var_150.Id], xmm0
0x18006f4e6  lea     rax, aReguserconfigq_4; "RegUserConfigQuery from DC"
0x18006f4ed  mov     qword ptr [rsp+190h+Flags], rax; char *
0x18006f4f2  mov     r9, r12; unsigned __int16 *
0x18006f4f5  mov     r8, rdi; unsigned __int16 *
0x18006f4f8  lea     rdx, [rsp+190h+var_150]; struct _EVENT_DESCRIPTOR
0x18006f4fd  lea     rcx, [rsp+190h+Parameter]; Parameter
0x18006f502  call    ??0CUserConfigMonitor@@QEAA@U_EVENT_DESCRIPTOR@@PEAG1PEBDK@Z; CUserConfigMonitor::CUserConfigMonitor(_EVENT_DESCRIPTOR,ushort *,ushort *,char const *,ulong)
0x18006f507  mov     rax, [rsp+190h+var_158]
0x18006f50c  mov     qword ptr [rsp+190h+Flags], rax
0x18006f511  mov     r9d, 9E8h
0x18006f517  mov     r8, r13
0x18006f51a  mov     rdx, r12
0x18006f51d  mov     rcx, rdi
0x18006f520  call    cs:__imp_RegUserConfigQuery
0x18006f527  nop     dword ptr [rax+rax+00h]
0x18006f52c  mov     ebx, eax
0x18006f52e  lea     rcx, [rsp+190h+Parameter]; this
0x18006f533  call    ??1CUserConfigMonitor@@UEAA@XZ; CUserConfigMonitor::~CUserConfigMonitor(void)
0x18006f538  call    cs:__imp_GetTickCount
0x18006f53f  nop     dword ptr [rax+rax+00h]
0x18006f544  sub     eax, esi
0x18006f546  mov     r8, rdi
0x18006f549  mov     [rsp+190h+Flags], eax
0x18006f54d  test    ebx, ebx
0x18006f54f  jz      short loc_18006F560
0x18006f551  mov     r9d, ebx
0x18006f554  lea     rdx, aReguserconfigq_2; "RegUserConfigQuery 2 - to server '%S', "...
0x18006f55b  mov     ecx, r15d
0x18006f55e  jmp     short loc_18006F56E
0x18006f560  xor     r9d, r9d
0x18006f563  lea     rdx, aReguserconfigq_3; "RegUserConfigQuery 2 - to server '%S', "...
0x18006f56a  lea     ecx, [r9+1]; int
0x18006f56e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006f573  mov     rcx, [rsp+190h+var_160]; Buffer
0x18006f578  test    rcx, rcx
0x18006f57b  jz      short loc_18006F58A
0x18006f57d  call    cs:__imp_NetApiBufferFree
0x18006f584  nop     dword ptr [rax+rax+00h]
0x18006f589  nop
0x18006f58a  lea     rcx, [rbp+90h+var_F0]; this
0x18006f58e  call    ??1CGenericTraceEx@@UEAA@XZ; CGenericTraceEx::~CGenericTraceEx(void)
0x18006f593  mov     eax, ebx
0x18006f595  mov     rcx, [rbp+90h+var_40]
0x18006f599  xor     rcx, rsp; StackCookie
0x18006f59c  call    __security_check_cookie
0x18006f5a1  mov     rbx, [rsp+190h+arg_0]
0x18006f5a9  add     rsp, 160h
0x18006f5b0  pop     r15
0x18006f5b2  pop     r14
0x18006f5b4  pop     r13
0x18006f5b6  pop     r12
0x18006f5b8  pop     rdi
0x18006f5b9  pop     rsi
0x18006f5ba  pop     rbp
0x18006f5bb  retn
```
