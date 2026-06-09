# CUserConfig::LoadConfigFromDC(int,ushort *,ushort *,ushort *,_USERCONFIGW *,ulong,ulong *)

- ea: `0x18006bed8`
- end: `0x18006c1ac`
- name: `?LoadConfigFromDC@CUserConfig@@AEAAKHPEAG00PEAU_USERCONFIGW@@KPEAK@Z`
- size: `724`
- prototype: `unsigned int(CUserConfig *__hidden this, int, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, struct _USERCONFIGW *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006c290`

## callees

- `0x18000a210`
- `0x1800321f0`
- `0x18006bbec`
- `0x18006bc60`
- `0x18006bcac`
- `0x18006bed8`
- `0x18009e4f8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006bf2e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006bfbf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006bfda`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006c0d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006c134`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006bf2e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006bfbf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006bfda`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006c0d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006c134`
- `logoncli!DsGetDcNameW` at `0x18006c04e`
- `logoncli!DsGetDcNameW` at `0x18006c087`
- `logoncli!DsGetDcNameW` at `0x18006c04e`
- `logoncli!DsGetDcNameW` at `0x18006c087`
- `netutils!NetApiBufferFree` at `0x18006c173`
- `netutils!NetApiBufferFree` at `0x18006c173`
- `REGAPI!RegUserConfigQuery` at `0x18006bfa0`
- `REGAPI!RegUserConfigQuery` at `0x18006c122`
- `REGAPI!RegUserConfigQuery` at `0x18006bfa0`
- `REGAPI!RegUserConfigQuery` at `0x18006c122`

## string_xrefs

- `0x18006bf40`: `Loading user configuration from %ws for user %ws`
- `0x18006bf4d`: `CUserConfig::LoadConfigFromDC`
- `0x18006c0ae`: `CUserConfig::LoadConfigFromDC`
- `0x18006bf6b`: `RegUserConfigQuery`
- `0x18006bfc8`: `RegUserConfigQuery 1 - to server '%S', failed with 0x%x, took %d ms`
- `0x18006bfe3`: `RegUserConfigQuery 1 - to server '%S', Return=0x%x, took %d ms`
- `0x18006c01c`: `RegUserConfigQuery 1 failed with 0x%08x - will retry`
- `0x18006c0e8`: `RegUserConfigQuery from DC`
- `0x18006c14a`: `RegUserConfigQuery 2 - to server '%S', failed with 0x%x, took %d ms`
- `0x18006c159`: `RegUserConfigQuery 2 - to server '%S', Return=0x%x, took %d ms`

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
  PDOMAIN_CONTROLLER_INFOW DomainControllerInfo; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int *v26; // [rsp+38h] [rbp-C8h]
  struct _EVENT_DESCRIPTOR v27; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD Parameter[10]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v29[176]; // [rsp+A0h] [rbp-60h] BYREF

  v26 = a8;
  DomainControllerInfo = 0;
  TickCount = GetTickCount();
  CGenericTraceEx::CGenericTraceEx(
    (CGenericTraceEx *)v29,
    "CUserConfig::LoadConfigFromDC",
    4u,
    "Loading user configuration from %ws for user %ws",
    a4,
    a5);
  v27 = (struct _EVENT_DESCRIPTOR)EVENT_LOAD_USERCONFIG_FROM_SERVER;
  CUserConfigMonitor::CUserConfigMonitor(Parameter, &v27, a4, a5, "RegUserConfigQuery");
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
      DcNameW = DsGetDcNameW(0, a3, 0, 0, 0x40000001u, &DomainControllerInfo);
      if ( DcNameW
        && (_DbgPrintMessage(
              4,
              "DsGetDcName failed with 0x%08x for (DS_FORCE_REDISCOVERY | DS_RETURN_DNS_NAME) - will retry",
              DcNameW),
            v18 = DsGetDcNameW(0, a3, 0, 0, 1u, &DomainControllerInfo),
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
        DomainControllerName = DomainControllerInfo->DomainControllerName;
        v21 = GetTickCount();
        v27 = (struct _EVENT_DESCRIPTOR)EVENT_LOAD_USERCONFIG_FROM_SERVER;
        CUserConfigMonitor::CUserConfigMonitor(Parameter, &v27, DomainControllerName, a5, "RegUserConfigQuery from DC");
        v12 = RegUserConfigQuery(DomainControllerName, a5, a6, 2536, v26);
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
  if ( DomainControllerInfo )
    NetApiBufferFree(DomainControllerInfo);
  CGenericTraceEx::~CGenericTraceEx((CGenericTraceEx *)v29);
  return v12;
}

```

## disassembly

```asm
0x18006bed8  mov     [rsp-8+arg_0], rbx
0x18006bedd  push    rbp
0x18006bede  push    rsi
0x18006bedf  push    rdi
0x18006bee0  push    r12
0x18006bee2  push    r13
0x18006bee4  push    r14
0x18006bee6  push    r15
0x18006bee8  lea     rbp, [rsp-60h]
0x18006beed  sub     rsp, 160h
0x18006bef4  mov     rax, cs:__security_cookie
0x18006befb  xor     rax, rsp
0x18006befe  mov     [rbp+90h+var_40], rax
0x18006bf02  mov     rdi, r9
0x18006bf05  mov     r14, r8
0x18006bf08  mov     r15d, edx
0x18006bf0b  mov     r12, [rbp+90h+arg_20]
0x18006bf12  mov     r13, [rbp+90h+arg_28]
0x18006bf19  mov     rbx, [rbp+90h+arg_38]
0x18006bf20  mov     [rsp+190h+var_158], rbx
0x18006bf25  mov     [rsp+190h+var_160], 0
0x18006bf2e  call    cs:__imp_GetTickCount
0x18006bf34  mov     esi, eax
0x18006bf36  mov     [rsp+190h+DomainControllerInfo], r12; unsigned int
0x18006bf3b  mov     qword ptr [rsp+190h+Flags], rdi
0x18006bf40  lea     r9, aLoadingUserCon_0; "Loading user configuration from %ws for"...
0x18006bf47  mov     r8d, 4; unsigned int
0x18006bf4d  lea     rdx, aCuserconfigLoa; "CUserConfig::LoadConfigFromDC"
0x18006bf54  lea     rcx, [rbp+90h+var_F0]; this
0x18006bf58  call    ??0CGenericTraceEx@@QEAA@PEBDK0ZZ; CGenericTraceEx::CGenericTraceEx(char const *,ulong,char const *,...)
0x18006bf5d  nop
0x18006bf5e  movups  xmm0, cs:EVENT_LOAD_USERCONFIG_FROM_SERVER
0x18006bf65  movdqu  xmmword ptr [rsp+190h+var_150.Id], xmm0
0x18006bf6b  lea     rax, aReguserconfigq_5; "RegUserConfigQuery"
0x18006bf72  mov     qword ptr [rsp+190h+Flags], rax; char *
0x18006bf77  mov     r9, r12; unsigned __int16 *
0x18006bf7a  mov     r8, rdi; unsigned __int16 *
0x18006bf7d  lea     rdx, [rsp+190h+var_150]; struct _EVENT_DESCRIPTOR
0x18006bf82  lea     rcx, [rsp+190h+Parameter]; Parameter
0x18006bf87  call    ??0CUserConfigMonitor@@QEAA@U_EVENT_DESCRIPTOR@@PEAG1PEBDK@Z; CUserConfigMonitor::CUserConfigMonitor(_EVENT_DESCRIPTOR,ushort *,ushort *,char const *,ulong)
0x18006bf8c  mov     qword ptr [rsp+190h+Flags], rbx
0x18006bf91  mov     r9d, 9E8h
0x18006bf97  mov     r8, r13
0x18006bf9a  mov     rdx, r12
0x18006bf9d  mov     rcx, rdi
0x18006bfa0  call    cs:__imp_RegUserConfigQuery
0x18006bfa6  mov     ebx, eax
0x18006bfa8  lea     rcx, [rsp+190h+Parameter]; this
0x18006bfad  call    ??1CUserConfigMonitor@@UEAA@XZ; CUserConfigMonitor::~CUserConfigMonitor(void)
0x18006bfb2  test    ebx, ebx
0x18006bfb4  jz      short loc_18006BFD1
0x18006bfb6  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18006bfbd  jz      short loc_18006BFFD
0x18006bfbf  call    cs:__imp_GetTickCount
0x18006bfc5  mov     r9d, ebx
0x18006bfc8  lea     rdx, aReguserconfigq_0; "RegUserConfigQuery 1 - to server '%S', "...
0x18006bfcf  jmp     short loc_18006BFEA
0x18006bfd1  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18006bfd8  jz      short loc_18006BFFD
0x18006bfda  call    cs:__imp_GetTickCount
0x18006bfe0  xor     r9d, r9d
0x18006bfe3  lea     rdx, aReguserconfigq_6; "RegUserConfigQuery 1 - to server '%S', "...
0x18006bfea  sub     eax, esi
0x18006bfec  mov     [rsp+190h+Flags], eax
0x18006bff0  mov     r8, rdi
0x18006bff3  mov     ecx, 2; int
0x18006bff8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006bffd  test    r15d, r15d
0x18006c000  jz      loc_18006C169
0x18006c006  cmp     ebx, 8
0x18006c009  ja      short loc_18006C019
0x18006c00b  mov     eax, 125h
0x18006c010  bt      eax, ebx
0x18006c013  jb      loc_18006C169
0x18006c019  mov     r8d, ebx
0x18006c01c  lea     rdx, aReguserconfigq_1; "RegUserConfigQuery 1 failed with 0x%08x"...
0x18006c023  mov     r15d, 4
0x18006c029  mov     ecx, r15d; int
0x18006c02c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006c031  lea     rax, [rsp+190h+var_160]
0x18006c036  mov     [rsp+190h+DomainControllerInfo], rax; unsigned int
0x18006c03b  mov     [rsp+190h+Flags], 40000001h; Flags
0x18006c043  xor     r9d, r9d; SiteName
0x18006c046  xor     r8d, r8d; DomainGuid
0x18006c049  mov     rdx, r14; DomainName
0x18006c04c  xor     ecx, ecx; ComputerName
0x18006c04e  call    cs:__imp_DsGetDcNameW
0x18006c054  test    eax, eax
0x18006c056  jz      short loc_18006C0CB
0x18006c058  mov     r8d, eax
0x18006c05b  lea     rdx, aDsgetdcnameFai_0; "DsGetDcName failed with 0x%08x for (DS_"...
0x18006c062  mov     ecx, r15d; int
0x18006c065  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006c06a  lea     rax, [rsp+190h+var_160]
0x18006c06f  mov     [rsp+190h+DomainControllerInfo], rax; DomainControllerInfo
0x18006c074  mov     [rsp+190h+Flags], 1; Flags
0x18006c07c  xor     r9d, r9d; SiteName
0x18006c07f  xor     r8d, r8d; DomainGuid
0x18006c082  mov     rdx, r14; DomainName
0x18006c085  xor     ecx, ecx; ComputerName
0x18006c087  call    cs:__imp_DsGetDcNameW
0x18006c08d  mov     ebx, eax
0x18006c08f  test    eax, eax
0x18006c091  jz      short loc_18006C0CB
0x18006c093  xor     edi, edi
0x18006c095  test    eax, eax
0x18006c097  jg      short loc_18006C09E
0x18006c099  mov     r8d, eax
0x18006c09c  jmp     short loc_18006C0A9
0x18006c09e  movzx   r8d, ax
0x18006c0a2  or      r8d, 80070000h
0x18006c0a9  test    r8d, r8d
0x18006c0ac  jns     short loc_18006C0D3
0x18006c0ae  lea     r9, aCuserconfigLoa; "CUserConfig::LoadConfigFromDC"
0x18006c0b5  lea     rdx, aDsgetdcname2Fa; "DsGetDcName 2 failed: 0x%x in %s"
0x18006c0bc  mov     ecx, 8; int
0x18006c0c1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006c0c6  jmp     loc_18006C169
0x18006c0cb  mov     rax, [rsp+190h+var_160]
0x18006c0d0  mov     rdi, [rax]
0x18006c0d3  call    cs:__imp_GetTickCount
0x18006c0d9  mov     esi, eax
0x18006c0db  movups  xmm0, cs:EVENT_LOAD_USERCONFIG_FROM_SERVER
0x18006c0e2  movdqu  xmmword ptr [rsp+190h+var_150.Id], xmm0
0x18006c0e8  lea     rax, aReguserconfigq_4; "RegUserConfigQuery from DC"
0x18006c0ef  mov     qword ptr [rsp+190h+Flags], rax; char *
0x18006c0f4  mov     r9, r12; unsigned __int16 *
0x18006c0f7  mov     r8, rdi; unsigned __int16 *
0x18006c0fa  lea     rdx, [rsp+190h+var_150]; struct _EVENT_DESCRIPTOR
0x18006c0ff  lea     rcx, [rsp+190h+Parameter]; Parameter
0x18006c104  call    ??0CUserConfigMonitor@@QEAA@U_EVENT_DESCRIPTOR@@PEAG1PEBDK@Z; CUserConfigMonitor::CUserConfigMonitor(_EVENT_DESCRIPTOR,ushort *,ushort *,char const *,ulong)
0x18006c109  mov     rax, [rsp+190h+var_158]
0x18006c10e  mov     qword ptr [rsp+190h+Flags], rax
0x18006c113  mov     r9d, 9E8h
0x18006c119  mov     r8, r13
0x18006c11c  mov     rdx, r12
0x18006c11f  mov     rcx, rdi
0x18006c122  call    cs:__imp_RegUserConfigQuery
0x18006c128  mov     ebx, eax
0x18006c12a  lea     rcx, [rsp+190h+Parameter]; this
0x18006c12f  call    ??1CUserConfigMonitor@@UEAA@XZ; CUserConfigMonitor::~CUserConfigMonitor(void)
0x18006c134  call    cs:__imp_GetTickCount
0x18006c13a  sub     eax, esi
0x18006c13c  mov     r8, rdi
0x18006c13f  mov     [rsp+190h+Flags], eax
0x18006c143  test    ebx, ebx
0x18006c145  jz      short loc_18006C156
0x18006c147  mov     r9d, ebx
0x18006c14a  lea     rdx, aReguserconfigq_2; "RegUserConfigQuery 2 - to server '%S', "...
0x18006c151  mov     ecx, r15d
0x18006c154  jmp     short loc_18006C164
0x18006c156  xor     r9d, r9d
0x18006c159  lea     rdx, aReguserconfigq_3; "RegUserConfigQuery 2 - to server '%S', "...
0x18006c160  lea     ecx, [r9+1]; int
0x18006c164  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006c169  mov     rcx, [rsp+190h+var_160]; Buffer
0x18006c16e  test    rcx, rcx
0x18006c171  jz      short loc_18006C17A
0x18006c173  call    cs:__imp_NetApiBufferFree
0x18006c179  nop
0x18006c17a  lea     rcx, [rbp+90h+var_F0]; this
0x18006c17e  call    ??1CGenericTraceEx@@UEAA@XZ; CGenericTraceEx::~CGenericTraceEx(void)
0x18006c183  mov     eax, ebx
0x18006c185  mov     rcx, [rbp+90h+var_40]
0x18006c189  xor     rcx, rsp; StackCookie
0x18006c18c  call    __security_check_cookie
0x18006c191  mov     rbx, [rsp+190h+arg_0]
0x18006c199  add     rsp, 160h
0x18006c1a0  pop     r15
0x18006c1a2  pop     r14
0x18006c1a4  pop     r13
0x18006c1a6  pop     r12
0x18006c1a8  pop     rdi
0x18006c1a9  pop     rsi
0x18006c1aa  pop     rbp
0x18006c1ab  retn
```
