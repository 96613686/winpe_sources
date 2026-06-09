# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)

- ea: `0x18000d69c`
- end: `0x18000d6cb`
- name: `?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000d514`

## callees

- `0x18000d7ac`

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
0x18000d69c  mov     rax, rsp
0x18000d69f  mov     [rax+18h], r8d
0x18000d6a3  mov     [rax+10h], edx
0x18000d6a6  sub     rsp, 38h
0x18000d6aa  mov     [rax-10h], r9d
0x18000d6ae  lea     rdx, [rax+10h]; Buf1
0x18000d6b2  mov     r8d, 4; Size
0x18000d6b8  lea     r9, [rax+18h]; void *
0x18000d6bc  mov     [rax-18h], r8
0x18000d6c0  call    ?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000d6c5  add     rsp, 38h
0x18000d6c9  retn
```
