# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)

- ea: `0x14000b17c`
- end: `0x14000b1aa`
- name: `?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x14000b064`

## callees

- `0x14000b280`

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
0x14000b17c  mov     rax, rsp
0x14000b17f  mov     [rax+18h], r8d
0x14000b183  mov     [rax+10h], edx
0x14000b186  sub     rsp, 38h
0x14000b18a  mov     [rax-10h], r9d
0x14000b18e  lea     rdx, [rax+10h]; void *
0x14000b192  mov     r8d, 4; unsigned __int64
0x14000b198  lea     r9, [rax+18h]; void *
0x14000b19c  mov     [rax-18h], r8
0x14000b1a0  call    ?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)
0x14000b1a5  add     rsp, 38h
0x14000b1a9  retn
```
