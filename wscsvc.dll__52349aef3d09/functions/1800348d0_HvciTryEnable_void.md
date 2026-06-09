# HvciTryEnable(void)

- ea: `0x1800348d0`
- end: `0x1800349a8`
- name: `?HvciTryEnable@@YAXXZ`
- size: `216`
- prototype: `void __fastcall(HKEY)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800343b8`
- `0x180034640`
- `0x1800348d0`

## import_xrefs

- `VbsApi!VbsIsCapable` at `0x180034919`
- `VbsApi!VbsIsCapable` at `0x180034919`
- `VbsApi!HvciGetConfig` at `0x180034935`
- `VbsApi!HvciGetConfig` at `0x180034935`
- `VbsApi!HvciIncompatibilityScanStart` at `0x180034968`
- `VbsApi!HvciIncompatibilityScanStart` at `0x180034968`
- `VbsApi!HvciIncompatibilityScanInitialize` at `0x18003495a`
- `VbsApi!HvciIncompatibilityScanInitialize` at `0x18003495a`
- `VbsApi!HvciIncompatibilityScanFree` at `0x18003499c`
- `VbsApi!HvciIncompatibilityScanFree` at `0x18003499c`
- `VbsApi!HvciIncompatibilityScanGetResult` at `0x180034976`
- `VbsApi!HvciIncompatibilityScanGetResult` at `0x180034976`
- `VbsApi!VbsGetIssues` at `0x180034910`
- `VbsApi!VbsGetIssues` at `0x180034910`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall HvciTryEnable(HKEY a1)
{
  HKEY v1; // rcx
  unsigned int v2; // r9d
  unsigned int v3; // [rsp+30h] [rbp+10h] BYREF
  unsigned int v4; // [rsp+38h] [rbp+18h] BYREF
  int v5; // [rsp+40h] [rbp+20h] BYREF
  __int64 v6; // [rsp+48h] [rbp+28h] BYREF

  v4 = 0;
  if ( !VelocityGetRegDword(
          a1,
          L"SYSTEM\\CurrentControlSet\\Control\\DeviceGuard\\VelocityScenarios\\HypervisorEnforcedCodeIntegrity",
          L"Enabled",
          &v4)
    || v4 )
  {
    v3 = 0;
    VbsGetIssues(&v3);
    if ( (unsigned int)VbsIsCapable(v3) )
    {
      if ( (v3 & 8) == 0 )
      {
        v5 = 0;
        if ( (unsigned int)HvciGetConfig(&v5) )
        {
          if ( !v5 )
          {
            v6 = 0;
            if ( (unsigned int)HvciIncompatibilityScanInitialize(
                                 wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
                                 0,
                                 &v6) )
            {
              if ( (unsigned int)HvciIncompatibilityScanStart(v6) && (unsigned int)HvciIncompatibilityScanGetResult(v6) )
                VelocitySetRegDword(
                  v1,
                  L"SYSTEM\\CurrentControlSet\\Control\\DeviceGuard\\VelocityScenarios\\HypervisorEnforcedCodeIntegrity",
                  L"Enabled",
                  v2);
              if ( v6 )
                HvciIncompatibilityScanFree();
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800348d0  push    rbp
0x1800348d2  mov     rbp, rsp
0x1800348d5  sub     rsp, 20h
0x1800348d9  lea     r9, [rbp+arg_8]; unsigned int *
0x1800348dd  mov     [rbp+arg_8], 0
0x1800348e4  lea     r8, aEnabled; "Enabled"
0x1800348eb  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Dev"...
0x1800348f2  call    ?VelocityGetRegDword@@YAHPEAUHKEY__@@PEBG1PEAK@Z; VelocityGetRegDword(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800348f7  test    eax, eax
0x1800348f9  jz      short loc_180034905
0x1800348fb  cmp     [rbp+arg_8], 0
0x1800348ff  jz      loc_1800349A2
0x180034905  lea     rcx, [rbp+arg_0]
0x180034909  mov     [rbp+arg_0], 0
0x180034910  call    cs:__imp_VbsGetIssues
0x180034916  mov     ecx, [rbp+arg_0]
0x180034919  call    cs:__imp_VbsIsCapable
0x18003491f  test    eax, eax
0x180034921  jz      short loc_1800349A2
0x180034923  mov     eax, [rbp+arg_0]
0x180034926  test    al, 8
0x180034928  jnz     short loc_1800349A2
0x18003492a  lea     rcx, [rbp+arg_10]
0x18003492e  mov     [rbp+arg_10], 0
0x180034935  call    cs:__imp_HvciGetConfig
0x18003493b  test    eax, eax
0x18003493d  jz      short loc_1800349A2
0x18003493f  cmp     [rbp+arg_10], 0
0x180034943  jnz     short loc_1800349A2
0x180034945  lea     r8, [rbp+arg_18]
0x180034949  mov     [rbp+arg_18], 0
0x180034951  xor     edx, edx
0x180034953  lea     rcx, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x18003495a  call    cs:__imp_HvciIncompatibilityScanInitialize
0x180034960  test    eax, eax
0x180034962  jz      short loc_1800349A2
0x180034964  mov     rcx, [rbp+arg_18]
0x180034968  call    cs:__imp_HvciIncompatibilityScanStart
0x18003496e  test    eax, eax
0x180034970  jz      short loc_180034993
0x180034972  mov     rcx, [rbp+arg_18]
0x180034976  call    cs:__imp_HvciIncompatibilityScanGetResult
0x18003497c  test    eax, eax
0x18003497e  jz      short loc_180034993
0x180034980  lea     r8, aEnabled; "Enabled"
0x180034987  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Dev"...
0x18003498e  call    ?VelocitySetRegDword@@YAHPEAUHKEY__@@PEBG1K@Z; VelocitySetRegDword(HKEY__ *,ushort const *,ushort const *,ulong)
0x180034993  mov     rcx, [rbp+arg_18]
0x180034997  test    rcx, rcx
0x18003499a  jz      short loc_1800349A2
0x18003499c  call    cs:__imp_HvciIncompatibilityScanFree
0x1800349a2  add     rsp, 20h
0x1800349a6  pop     rbp
0x1800349a7  retn
```
