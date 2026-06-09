# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)

- ea: `0x18000c8e8`
- end: `0x18000c916`
- name: `?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z`
- size: `46`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *, int, int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000c7d0`

## callees

- `0x18000c9ec`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
        wil::details_abi::RawUsageIndex *a1,
        int a2,
        int a3,
        unsigned int a4)
{
  int v5; // [rsp+48h] [rbp+10h] BYREF
  int v6; // [rsp+50h] [rbp+18h] BYREF

  v6 = a3;
  v5 = a2;
  return wil::details_abi::RawUsageIndex::RecordUsage(a1, &v5, 4u, &v6, 4u, a4);
}

```

## disassembly

```asm
0x18000c8e8  mov     rax, rsp
0x18000c8eb  mov     [rax+18h], r8d
0x18000c8ef  mov     [rax+10h], edx
0x18000c8f2  sub     rsp, 38h
0x18000c8f6  mov     [rax-10h], r9d
0x18000c8fa  lea     rdx, [rax+10h]; void *
0x18000c8fe  mov     r8d, 4; unsigned __int64
0x18000c904  lea     r9, [rax+18h]; void *
0x18000c908  mov     [rax-18h], r8
0x18000c90c  call    ?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000c911  add     rsp, 38h
0x18000c915  retn
```
