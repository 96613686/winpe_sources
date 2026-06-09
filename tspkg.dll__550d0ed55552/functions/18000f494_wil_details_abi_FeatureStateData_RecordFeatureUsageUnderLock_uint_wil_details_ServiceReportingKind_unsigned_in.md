# wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000f494`
- end: `0x18000f4e9`
- name: `?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000f3b4`

## callees

- `0x18000f494`
- `0x18000f528`
- `0x18000f55c`

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
0x18000f494  push    rbx
0x18000f496  sub     rsp, 20h
0x18000f49a  lea     rbx, [rcx+8]
0x18000f49e  mov     r10d, r8d
0x18000f4a1  cmp     r8d, 7
0x18000f4a5  ja      short loc_18000F4B2
0x18000f4a7  mov     eax, 0CCh
0x18000f4ac  bt      eax, r8d
0x18000f4b0  jb      short loc_18000F4D2
0x18000f4b2  lea     eax, [r8-100h]
0x18000f4b9  cmp     eax, 7Fh
0x18000f4bc  jbe     short loc_18000F4D2
0x18000f4be  mov     r8d, edx
0x18000f4c1  lea     rcx, [rbx+40h]
0x18000f4c5  mov     edx, r10d
0x18000f4c8  add     rsp, 20h
0x18000f4cc  pop     rbx
0x18000f4cd  jmp     ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000f4d2  mov     r8d, edx
0x18000f4d5  mov     rcx, rbx
0x18000f4d8  mov     edx, r10d
0x18000f4db  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000f4e0  mov     al, [rbx+38h]
0x18000f4e3  add     rsp, 20h
0x18000f4e7  pop     rbx
0x18000f4e8  retn
```
