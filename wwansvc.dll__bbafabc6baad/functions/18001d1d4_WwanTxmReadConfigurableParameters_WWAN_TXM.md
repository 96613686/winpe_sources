# WwanTxmReadConfigurableParameters(WWAN_TXM *)

- ea: `0x18001d1d4`
- end: `0x18001d592`
- name: `?WwanTxmReadConfigurableParameters@@YAXPEAUWWAN_TXM@@@Z`
- size: `958`
- prototype: `void __fastcall(struct WWAN_TXM *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18001ce84`

## callees

- `0x180008abc`
- `0x180010e94`
- `0x1800117a8`
- `0x180011a1c`
- `0x180012300`
- `0x180014b5c`
- `0x180014f1c`
- `0x180016c50`
- `0x18001d1d4`

## string_xrefs

- `0x18001d284`: `Reg sub path %s or value %s not present`
- `0x18001d31d`: `Reg sub path %s or value %s not present`
- `0x18001d3ce`: `Reg sub path %s or value %s not present`
- `0x18001d49c`: `Reg sub path %s or value %s not present`
- `0x18001d270`: `WwanTxmReadConfigurableParameters`
- `0x18001d29f`: `Failed to read Reg sub path %s or value %s (err 0x%x)`
- `0x18001d338`: `Failed to read Reg sub path %s or value %s (err 0x%x)`
- `0x18001d3f3`: `Failed to read Reg sub path %s or value %s (err 0x%x)`
- `0x18001d4c1`: `Failed to read Reg sub path %s or value %s (err 0x%x)`
- `0x18001d2b9`: `Reg sub path %s value %s contains 0`
- `0x18001d352`: `Reg sub path %s value %s contains 0`
- `0x18001d414`: `Reg sub path %s value %s contains 0`
- `0x18001d4e2`: `Reg sub path %s value %s contains 0`
- `0x18001d2d0`: `Reg sub path %s value %s contains %d`
- `0x18001d383`: `Reg sub path %s value %s contains %d`
- `0x18001d451`: `Reg sub path %s value %s contains %d`
- `0x18001d51f`: `Reg sub path %s value %s contains %d`
- `0x18001d36e`: `Reg sub path %s value %s contains ivalid data %d. Limit it to max`
- `0x18001d430`: `Reg sub path %s value %s contains ivalid data %d. Limit it to max`
- `0x18001d4fe`: `Reg sub path %s value %s contains ivalid data %d. Limit it to max`
- `0x18001d55d`: `Configuration: response time limits (low %d medium %d high %d) consecutive OID timeout threshold %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WwanTxmReadConfigurableParameters(struct WWAN_TXM *a1)
{
  __int64 v2; // rax
  unsigned int DWORD; // eax
  const struct _GUID *v4; // rdx
  unsigned int v5; // eax
  const struct _GUID *v6; // rdx
  unsigned int v7; // eax
  const struct _GUID *v8; // rdx
  unsigned int v9; // eax
  const struct _GUID *v10; // rdx
  __int64 v11; // [rsp+20h] [rbp-20h]
  __int64 v12; // [rsp+28h] [rbp-18h]
  unsigned int v13; // [rsp+70h] [rbp+30h] BYREF
  StateSeparation *v14; // [rsp+78h] [rbp+38h] BYREF

  *((_DWORD *)a1 + 75) = 3;
  *((_DWORD *)a1 + 72) = 10;
  *((_DWORD *)a1 + 73) = 60;
  *((_DWORD *)a1 + 74) = 200;
  v13 = 0;
  v14 = (StateSeparation *)operator new(0x20u);
  v2 = StateSeparation::StateSeparation((__int64)v14);
  std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>((__int64)&v14, v2);
  DWORD = StateSeparation::GetDWORD(v14, L"OIDResponseParameters", L"ConsecutiveRspTimeoutThreshold", &v13);
  v4 = (const struct _GUID *)((char *)a1 + 88);
  if ( DWORD == 2 )
  {
    WwanLog::Verbose(
      "WwanTxmReadConfigurableParameters",
      v4,
      L"Reg sub path %s or value %s not present",
      L"ConsecutiveRspTimeoutThreshold",
      L"ConsecutiveRspTimeoutThreshold");
  }
  else if ( DWORD )
  {
    WwanLog::Error(
      "WwanTxmReadConfigurableParameters",
      v4,
      L"Failed to read Reg sub path %s or value %s (err 0x%x)",
      L"ConsecutiveRspTimeoutThreshold",
      L"ConsecutiveRspTimeoutThreshold",
      DWORD);
  }
  else if ( v13 )
  {
    WwanLog::Info(
      "WwanTxmReadConfigurableParameters",
      v4,
      L"Reg sub path %s value %s contains %d",
      L"ConsecutiveRspTimeoutThreshold",
      L"ConsecutiveRspTimeoutThreshold",
      v13);
    *((_DWORD *)a1 + 75) = v13;
  }
  else
  {
    WwanLog::Error(
      "WwanTxmReadConfigurableParameters",
      v4,
      L"Reg sub path %s value %s contains 0",
      L"ConsecutiveRspTimeoutThreshold",
      L"ConsecutiveRspTimeoutThreshold");
  }
  v5 = StateSeparation::GetDWORD(v14, L"OIDResponseParameters", L"RspTimeLimitLowLatencyGroup", &v13);
  v6 = (const struct _GUID *)((char *)a1 + 88);
  if ( v5 == 2 )
  {
    WwanLog::Verbose(
      "WwanTxmReadConfigurableParameters",
      v6,
      L"Reg sub path %s or value %s not present",
      L"ConsecutiveRspTimeoutThreshold",
      L"RspTimeLimitLowLatencyGroup");
  }
  else if ( v5 )
  {
    LODWORD(v12) = v5;
    WwanLog::Error(
      "WwanTxmReadConfigurableParameters",
      v6,
      L"Failed to read Reg sub path %s or value %s (err 0x%x)",
      L"ConsecutiveRspTimeoutThreshold",
      L"RspTimeLimitLowLatencyGroup",
      v12);
  }
  else if ( v13 )
  {
    LODWORD(v12) = v13;
    if ( v13 <= 0x12C )
    {
      WwanLog::Info(
        "WwanTxmReadConfigurableParameters",
        v6,
        L"Reg sub path %s value %s contains %d",
        L"ConsecutiveRspTimeoutThreshold",
        L"RspTimeLimitLowLatencyGroup",
        v12);
      *((_DWORD *)a1 + 72) = v13;
    }
    else
    {
      WwanLog::Error(
        "WwanTxmReadConfigurableParameters",
        v6,
        L"Reg sub path %s value %s contains ivalid data %d. Limit it to max",
        L"ConsecutiveRspTimeoutThreshold",
        L"RspTimeLimitLowLatencyGroup",
        v12);
      *((_DWORD *)a1 + 72) = 300;
    }
  }
  else
  {
    WwanLog::Error(
      "WwanTxmReadConfigurableParameters",
      v6,
      L"Reg sub path %s value %s contains 0",
      L"ConsecutiveRspTimeoutThreshold",
      L"RspTimeLimitLowLatencyGroup");
  }
  v7 = StateSeparation::GetDWORD(v14, L"OIDResponseParameters", L"RspTimeLimitMediumLatencyGroup", &v13);
  v8 = (const struct _GUID *)((char *)a1 + 88);
  if ( v7 == 2 )
  {
    WwanLog::Verbose(
      "WwanTxmReadConfigurableParameters",
      v8,
      L"Reg sub path %s or value %s not present",
      L"ConsecutiveRspTimeoutThreshold",
      L"RspTimeLimitMediumLatencyGroup");
  }
  else if ( v7 )
  {
    LODWORD(v12) = v7;
    WwanLog::Error(
      "WwanTxmReadConfigurableParameters",
      v8,
      L"Failed to read Reg sub path %s or value %s (err 0x%x)",
      L"ConsecutiveRspTimeoutThreshold",
      L"RspTimeLimitMediumLatencyGroup",
      v12);
  }
  else if ( v13 )
  {
    LODWORD(v12) = v13;
    if ( v13 <= 0x12C )
    {
      WwanLog::Info(
        "WwanTxmReadConfigurableParameters",
        v8,
        L"Reg sub path %s value %s contains %d",
        L"ConsecutiveRspTimeoutThreshold",
        L"RspTimeLimitMediumLatencyGroup",
        v12);
      *((_DWORD *)a1 + 73) = v13;
    }
    else
    {
      WwanLog::Error(
        "WwanTxmReadConfigurableParameters",
        v8,
        L"Reg sub path %s value %s contains ivalid data %d. Limit it to max",
        L"ConsecutiveRspTimeoutThreshold",
        L"RspTimeLimitLowLatencyGroup",
        v12);
      *((_DWORD *)a1 + 73) = 300;
    }
  }
  else
  {
    WwanLog::Error(
      "WwanTxmReadConfigurableParameters",
      v8,
      L"Reg sub path %s value %s contains 0",
      L"ConsecutiveRspTimeoutThreshold",
      L"RspTimeLimitMediumLatencyGroup");
  }
  v9 = StateSeparation::GetDWORD(v14, L"OIDResponseParameters", L"RspTimeLimitMediumLatencyGroup", &v13);
  v10 = (const struct _GUID *)((char *)a1 + 88);
  if ( v9 == 2 )
  {
    WwanLog::Verbose(
      "WwanTxmReadConfigurableParameters",
      v10,
      L"Reg sub path %s or value %s not present",
      L"ConsecutiveRspTimeoutThreshold",
      L"RspTimeLimitHighLatencyGroup");
  }
  else if ( v9 )
  {
    LODWORD(v12) = v9;
    WwanLog::Error(
      "WwanTxmReadConfigurableParameters",
      v10,
      L"Failed to read Reg sub path %s or value %s (err 0x%x)",
      L"ConsecutiveRspTimeoutThreshold",
      L"RspTimeLimitHighLatencyGroup",
      v12);
  }
  else if ( v13 )
  {
    LODWORD(v12) = v13;
    if ( v13 <= 0x12C )
    {
      WwanLog::Info(
        "WwanTxmReadConfigurableParameters",
        v10,
        L"Reg sub path %s value %s contains %d",
        L"ConsecutiveRspTimeoutThreshold",
        L"RspTimeLimitHighLatencyGroup",
        v12);
      *((_DWORD *)a1 + 74) = v13;
    }
    else
    {
      WwanLog::Error(
        "WwanTxmReadConfigurableParameters",
        v10,
        L"Reg sub path %s value %s contains ivalid data %d. Limit it to max",
        L"ConsecutiveRspTimeoutThreshold",
        L"RspTimeLimitLowLatencyGroup",
        v12);
      *((_DWORD *)a1 + 74) = 300;
    }
  }
  else
  {
    WwanLog::Error(
      "WwanTxmReadConfigurableParameters",
      v10,
      L"Reg sub path %s value %s contains 0",
      L"ConsecutiveRspTimeoutThreshold",
      L"RspTimeLimitHighLatencyGroup");
  }
  LODWORD(v12) = *((_DWORD *)a1 + 74);
  LODWORD(v11) = *((_DWORD *)a1 + 73);
  WwanLog::Info(
    "WwanTxmReadConfigurableParameters",
    (const struct _GUID *)((char *)a1 + 88),
    L"Configuration: response time limits (low %d medium %d high %d) consecutive OID timeout threshold %d",
    *((unsigned int *)a1 + 72),
    v11,
    v12,
    *((_DWORD *)a1 + 75));
  std::unique_ptr<StateSeparation>::~unique_ptr<StateSeparation>(&v14);
}

```

## disassembly

```asm
0x18001d1d4  mov     [rsp-28h+arg_10], rsi
0x18001d1d9  mov     [rsp-28h+arg_18], rdi
0x18001d1de  push    rbp
0x18001d1df  push    r12
0x18001d1e1  push    r13
0x18001d1e3  push    r14
0x18001d1e5  push    r15
0x18001d1e7  mov     rbp, rsp
0x18001d1ea  sub     rsp, 40h
0x18001d1ee  mov     r14, rcx
0x18001d1f1  mov     dword ptr [rcx+12Ch], 3
0x18001d1fb  mov     dword ptr [rcx+120h], 0Ah
0x18001d205  mov     dword ptr [rcx+124h], 3Ch ; '<'
0x18001d20f  mov     dword ptr [rcx+128h], 0C8h
0x18001d219  mov     [rbp+arg_0], 0
0x18001d220  mov     ecx, 20h ; ' '; Size
0x18001d225  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d22a  mov     [rbp+arg_8], rax
0x18001d22e  mov     edx, 2
0x18001d233  mov     rcx, rax
0x18001d236  call    ??0StateSeparation@@QEAA@W4_REG_ROOT_PATH@@@Z; StateSeparation::StateSeparation(_REG_ROOT_PATH)
0x18001d23b  nop
0x18001d23c  mov     rdx, rax
0x18001d23f  lea     rcx, [rbp+arg_8]
0x18001d243  call    ??$?0U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@$0A@@?$unique_ptr@U_WWAN_SET_LTE_ATTACH@@U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@@std@@QEAA@PEAU_WWAN_SET_LTE_ATTACH@@@Z; std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(_WWAN_SET_LTE_ATTACH *)
0x18001d248  lea     r9, [rbp+arg_0]; unsigned int *
0x18001d24c  lea     r15, aConsecutiversp; "ConsecutiveRspTimeoutThreshold"
0x18001d253  mov     r8, r15; unsigned __int16 *
0x18001d256  lea     rdx, aOidresponsepar; "OIDResponseParameters"
0x18001d25d  mov     rcx, [rbp+arg_8]; this
0x18001d261  call    ?GetDWORD@StateSeparation@@QEAAKPEBG0PEAK@Z; StateSeparation::GetDWORD(ushort const *,ushort const *,ulong *)
0x18001d266  lea     rsi, [r14+58h]
0x18001d26a  mov     r9, r15
0x18001d26d  mov     rdx, rsi; struct _GUID *
0x18001d270  lea     rdi, aWwantxmreadcon; "WwanTxmReadConfigurableParameters"
0x18001d277  mov     rcx, rdi; char *
0x18001d27a  cmp     eax, 2
0x18001d27d  jnz     short loc_18001D292
0x18001d27f  mov     [rsp+40h+var_20], r15
0x18001d284  lea     r8, aRegSubPathSOrV; "Reg sub path %s or value %s not present"
0x18001d28b  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x18001d290  jmp     short loc_18001D2E6
0x18001d292  test    eax, eax
0x18001d294  jz      short loc_18001D2AD
0x18001d296  mov     dword ptr [rsp+40h+var_18], eax
0x18001d29a  mov     [rsp+40h+var_20], r15
0x18001d29f  lea     r8, aFailedToReadRe; "Failed to read Reg sub path %s or value"...
0x18001d2a6  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001d2ab  jmp     short loc_18001D2E6
0x18001d2ad  mov     eax, [rbp+arg_0]
0x18001d2b0  test    eax, eax
0x18001d2b2  jnz     short loc_18001D2C7
0x18001d2b4  mov     [rsp+40h+var_20], r15
0x18001d2b9  lea     r8, aRegSubPathSVal_2; "Reg sub path %s value %s contains 0"
0x18001d2c0  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001d2c5  jmp     short loc_18001D2E6
0x18001d2c7  mov     dword ptr [rsp+40h+var_18], eax
0x18001d2cb  mov     [rsp+40h+var_20], r15
0x18001d2d0  lea     r8, aRegSubPathSVal_1; "Reg sub path %s value %s contains %d"
0x18001d2d7  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18001d2dc  mov     eax, [rbp+arg_0]
0x18001d2df  mov     [r14+12Ch], eax
0x18001d2e6  lea     r9, [rbp+arg_0]; unsigned int *
0x18001d2ea  lea     r12, aRsptimelimitlo; "RspTimeLimitLowLatencyGroup"
0x18001d2f1  mov     r8, r12; unsigned __int16 *
0x18001d2f4  lea     rdx, aOidresponsepar; "OIDResponseParameters"
0x18001d2fb  mov     rcx, [rbp+arg_8]; this
0x18001d2ff  call    ?GetDWORD@StateSeparation@@QEAAKPEBG0PEAK@Z; StateSeparation::GetDWORD(ushort const *,ushort const *,ulong *)
0x18001d304  mov     r13d, 12Ch
0x18001d30a  mov     r9, r15
0x18001d30d  mov     rdx, rsi; struct _GUID *
0x18001d310  mov     rcx, rdi; char *
0x18001d313  cmp     eax, 2
0x18001d316  jnz     short loc_18001D32B
0x18001d318  mov     [rsp+40h+var_20], r12
0x18001d31d  lea     r8, aRegSubPathSOrV; "Reg sub path %s or value %s not present"
0x18001d324  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x18001d329  jmp     short loc_18001D399
0x18001d32b  test    eax, eax
0x18001d32d  jz      short loc_18001D346
0x18001d32f  mov     dword ptr [rsp+40h+var_18], eax
0x18001d333  mov     [rsp+40h+var_20], r12
0x18001d338  lea     r8, aFailedToReadRe; "Failed to read Reg sub path %s or value"...
0x18001d33f  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001d344  jmp     short loc_18001D399
0x18001d346  mov     eax, [rbp+arg_0]
0x18001d349  test    eax, eax
0x18001d34b  jnz     short loc_18001D360
0x18001d34d  mov     [rsp+40h+var_20], r12
0x18001d352  lea     r8, aRegSubPathSVal_2; "Reg sub path %s value %s contains 0"
0x18001d359  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001d35e  jmp     short loc_18001D399
0x18001d360  mov     dword ptr [rsp+40h+var_18], eax
0x18001d364  mov     [rsp+40h+var_20], r12
0x18001d369  cmp     eax, r13d
0x18001d36c  jbe     short loc_18001D383
0x18001d36e  lea     r8, aRegSubPathSVal_0; "Reg sub path %s value %s contains ivali"...
0x18001d375  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001d37a  mov     [r14+120h], r13d
0x18001d381  jmp     short loc_18001D399
0x18001d383  lea     r8, aRegSubPathSVal_1; "Reg sub path %s value %s contains %d"
0x18001d38a  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18001d38f  mov     eax, [rbp+arg_0]
0x18001d392  mov     [r14+120h], eax
0x18001d399  lea     r9, [rbp+arg_0]; unsigned int *
0x18001d39d  lea     r8, aRsptimelimitme; "RspTimeLimitMediumLatencyGroup"
0x18001d3a4  lea     rdx, aOidresponsepar; "OIDResponseParameters"
0x18001d3ab  mov     rcx, [rbp+arg_8]; this
0x18001d3af  call    ?GetDWORD@StateSeparation@@QEAAKPEBG0PEAK@Z; StateSeparation::GetDWORD(ushort const *,ushort const *,ulong *)
0x18001d3b4  mov     r9, r15
0x18001d3b7  mov     rdx, rsi; struct _GUID *
0x18001d3ba  mov     rcx, rdi; char *
0x18001d3bd  cmp     eax, 2
0x18001d3c0  jnz     short loc_18001D3DF
0x18001d3c2  lea     rax, aRsptimelimitme; "RspTimeLimitMediumLatencyGroup"
0x18001d3c9  mov     [rsp+40h+var_20], rax
0x18001d3ce  lea     r8, aRegSubPathSOrV; "Reg sub path %s or value %s not present"
0x18001d3d5  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x18001d3da  jmp     loc_18001D467
0x18001d3df  test    eax, eax
0x18001d3e1  jz      short loc_18001D401
0x18001d3e3  mov     dword ptr [rsp+40h+var_18], eax
0x18001d3e7  lea     rax, aRsptimelimitme; "RspTimeLimitMediumLatencyGroup"
0x18001d3ee  mov     [rsp+40h+var_20], rax
0x18001d3f3  lea     r8, aFailedToReadRe; "Failed to read Reg sub path %s or value"...
0x18001d3fa  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001d3ff  jmp     short loc_18001D467
0x18001d401  mov     eax, [rbp+arg_0]
0x18001d404  test    eax, eax
0x18001d406  jnz     short loc_18001D422
0x18001d408  lea     rax, aRsptimelimitme; "RspTimeLimitMediumLatencyGroup"
0x18001d40f  mov     [rsp+40h+var_20], rax
0x18001d414  lea     r8, aRegSubPathSVal_2; "Reg sub path %s value %s contains 0"
0x18001d41b  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001d420  jmp     short loc_18001D467
0x18001d422  mov     dword ptr [rsp+40h+var_18], eax
0x18001d426  cmp     eax, r13d
0x18001d429  jbe     short loc_18001D445
0x18001d42b  mov     [rsp+40h+var_20], r12
0x18001d430  lea     r8, aRegSubPathSVal_0; "Reg sub path %s value %s contains ivali"...
0x18001d437  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001d43c  mov     [r14+124h], r13d
0x18001d443  jmp     short loc_18001D467
0x18001d445  lea     rax, aRsptimelimitme; "RspTimeLimitMediumLatencyGroup"
0x18001d44c  mov     [rsp+40h+var_20], rax
0x18001d451  lea     r8, aRegSubPathSVal_1; "Reg sub path %s value %s contains %d"
0x18001d458  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18001d45d  mov     eax, [rbp+arg_0]
0x18001d460  mov     [r14+124h], eax
0x18001d467  lea     r9, [rbp+arg_0]; unsigned int *
0x18001d46b  lea     r8, aRsptimelimitme; "RspTimeLimitMediumLatencyGroup"
0x18001d472  lea     rdx, aOidresponsepar; "OIDResponseParameters"
0x18001d479  mov     rcx, [rbp+arg_8]; this
0x18001d47d  call    ?GetDWORD@StateSeparation@@QEAAKPEBG0PEAK@Z; StateSeparation::GetDWORD(ushort const *,ushort const *,ulong *)
0x18001d482  mov     r9, r15
0x18001d485  mov     rdx, rsi; struct _GUID *
0x18001d488  mov     rcx, rdi; char *
0x18001d48b  cmp     eax, 2
0x18001d48e  jnz     short loc_18001D4AD
0x18001d490  lea     rax, aRsptimelimithi; "RspTimeLimitHighLatencyGroup"
0x18001d497  mov     [rsp+40h+var_20], rax
0x18001d49c  lea     r8, aRegSubPathSOrV; "Reg sub path %s or value %s not present"
0x18001d4a3  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x18001d4a8  jmp     loc_18001D535
0x18001d4ad  test    eax, eax
0x18001d4af  jz      short loc_18001D4CF
0x18001d4b1  mov     dword ptr [rsp+40h+var_18], eax
0x18001d4b5  lea     rax, aRsptimelimithi; "RspTimeLimitHighLatencyGroup"
0x18001d4bc  mov     [rsp+40h+var_20], rax
0x18001d4c1  lea     r8, aFailedToReadRe; "Failed to read Reg sub path %s or value"...
0x18001d4c8  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001d4cd  jmp     short loc_18001D535
0x18001d4cf  mov     eax, [rbp+arg_0]
0x18001d4d2  test    eax, eax
0x18001d4d4  jnz     short loc_18001D4F0
0x18001d4d6  lea     rax, aRsptimelimithi; "RspTimeLimitHighLatencyGroup"
0x18001d4dd  mov     [rsp+40h+var_20], rax
0x18001d4e2  lea     r8, aRegSubPathSVal_2; "Reg sub path %s value %s contains 0"
0x18001d4e9  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001d4ee  jmp     short loc_18001D535
0x18001d4f0  mov     dword ptr [rsp+40h+var_18], eax
0x18001d4f4  cmp     eax, r13d
0x18001d4f7  jbe     short loc_18001D513
0x18001d4f9  mov     [rsp+40h+var_20], r12
0x18001d4fe  lea     r8, aRegSubPathSVal_0; "Reg sub path %s value %s contains ivali"...
0x18001d505  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001d50a  mov     [r14+128h], r13d
0x18001d511  jmp     short loc_18001D535
0x18001d513  lea     rax, aRsptimelimithi; "RspTimeLimitHighLatencyGroup"
0x18001d51a  mov     [rsp+40h+var_20], rax
0x18001d51f  lea     r8, aRegSubPathSVal_1; "Reg sub path %s value %s contains %d"
0x18001d526  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18001d52b  mov     eax, [rbp+arg_0]
0x18001d52e  mov     [r14+128h], eax
0x18001d535  mov     eax, [r14+12Ch]
0x18001d53c  mov     [rsp+40h+var_10], eax
0x18001d540  mov     eax, [r14+128h]
0x18001d547  mov     dword ptr [rsp+40h+var_18], eax
0x18001d54b  mov     eax, [r14+124h]
0x18001d552  mov     dword ptr [rsp+40h+var_20], eax
0x18001d556  mov     r9d, [r14+120h]
0x18001d55d  lea     r8, aConfigurationR; "Configuration: response time limits (lo"...
0x18001d564  mov     rdx, rsi; struct _GUID *
0x18001d567  mov     rcx, rdi; char *
0x18001d56a  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18001d56f  lea     rcx, [rbp+arg_8]
0x18001d573  call    ??1?$unique_ptr@VStateSeparation@@U?$default_delete@VStateSeparation@@@std@@@std@@QEAA@XZ; std::unique_ptr<StateSeparation>::~unique_ptr<StateSeparation>(void)
0x18001d578  lea     r11, [rsp+40h+var_s0]
0x18001d57d  mov     rsi, [r11+40h]
0x18001d581  mov     rdi, [r11+48h]
0x18001d585  mov     rsp, r11
0x18001d588  pop     r15
0x18001d58a  pop     r14
0x18001d58c  pop     r13
0x18001d58e  pop     r12
0x18001d590  pop     rbp
0x18001d591  retn
```
