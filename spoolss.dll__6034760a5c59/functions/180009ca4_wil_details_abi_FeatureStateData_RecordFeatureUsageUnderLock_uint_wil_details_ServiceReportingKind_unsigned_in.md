# wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180009ca4`
- end: `0x180009cf9`
- name: `?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180009bc4`

## callees

- `0x180009ca4`
- `0x180009d50`
- `0x180009d84`

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
0x180009ca4  push    rbx
0x180009ca6  sub     rsp, 20h
0x180009caa  lea     rbx, [rcx+8]
0x180009cae  mov     r10d, r8d
0x180009cb1  cmp     r8d, 7
0x180009cb5  ja      short loc_180009CC2
0x180009cb7  mov     eax, 0CCh
0x180009cbc  bt      eax, r8d
0x180009cc0  jb      short loc_180009CE2
0x180009cc2  lea     eax, [r8-100h]
0x180009cc9  cmp     eax, 7Fh
0x180009ccc  jbe     short loc_180009CE2
0x180009cce  mov     r8d, edx
0x180009cd1  lea     rcx, [rbx+40h]
0x180009cd5  mov     edx, r10d
0x180009cd8  add     rsp, 20h
0x180009cdc  pop     rbx
0x180009cdd  jmp     ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180009ce2  mov     r8d, edx
0x180009ce5  mov     rcx, rbx
0x180009ce8  mov     edx, r10d
0x180009ceb  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180009cf0  mov     al, [rbx+38h]
0x180009cf3  add     rsp, 20h
0x180009cf7  pop     rbx
0x180009cf8  retn
```
