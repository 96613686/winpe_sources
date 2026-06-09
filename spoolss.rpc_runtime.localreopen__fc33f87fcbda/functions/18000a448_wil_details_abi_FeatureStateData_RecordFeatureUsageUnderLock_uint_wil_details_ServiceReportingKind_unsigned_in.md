# wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000a448`
- end: `0x18000a49e`
- name: `?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000a354`

## callees

- `0x18000a448`
- `0x18000a500`
- `0x18000a538`

## pseudocode

```c
char __fastcall wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(
        __int64 a1,
        unsigned int a2,
        unsigned int a3)
{
  __int64 v3; // rbx
  int v4; // eax

  v3 = a1 + 8;
  if ( a3 > 7 || (v4 = 204, !_bittest(&v4, a3)) )
  {
    if ( a3 - 256 > 0x7F )
      return wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
               a1 + 72,
               a3,
               a2);
  }
  wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(a1 + 8, a3, a2);
  return *(_BYTE *)(v3 + 56);
}

```

## disassembly

```asm
0x18000a448  push    rbx
0x18000a44a  sub     rsp, 20h
0x18000a44e  lea     rbx, [rcx+8]
0x18000a452  mov     r10d, r8d
0x18000a455  cmp     r8d, 7
0x18000a459  ja      short loc_18000A466
0x18000a45b  mov     eax, 0CCh
0x18000a460  bt      eax, r8d
0x18000a464  jb      short loc_18000A486
0x18000a466  lea     eax, [r8-100h]
0x18000a46d  cmp     eax, 7Fh
0x18000a470  jbe     short loc_18000A486
0x18000a472  mov     r8d, edx
0x18000a475  lea     rcx, [rbx+40h]
0x18000a479  mov     edx, r10d
0x18000a47c  add     rsp, 20h
0x18000a480  pop     rbx
0x18000a481  jmp     ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000a486  mov     r8d, edx
0x18000a489  mov     rcx, rbx
0x18000a48c  mov     edx, r10d
0x18000a48f  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000a494  mov     al, [rbx+38h]
0x18000a497  add     rsp, 20h
0x18000a49b  pop     rbx
0x18000a49c  retn
```
