# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)

- ea: `0x18000f2a0`
- end: `0x18000f2ec`
- name: `?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000f0b8`

## callees

- `0x180008a90`
- `0x18000f3d8`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
        wil::details_abi::RawUsageIndex *a1,
        int a2,
        int a3,
        unsigned int a4)
{
  int v5; // [rsp+30h] [rbp-28h] BYREF
  int v6; // [rsp+38h] [rbp-20h] BYREF

  v6 = a2;
  v5 = a3;
  return wil::details_abi::RawUsageIndex::RecordUsage(a1, &v6, 4u, &v5, 4u, a4);
}

```

## disassembly

```asm
0x18000f2a0  mov     r11, rsp
0x18000f2a3  sub     rsp, 58h
0x18000f2a7  mov     rax, cs:__security_cookie
0x18000f2ae  xor     rax, rsp
0x18000f2b1  mov     [rsp+58h+var_18], rax
0x18000f2b6  mov     [rsp+58h+var_20], edx
0x18000f2ba  lea     rdx, [r11-20h]; void *
0x18000f2be  mov     [r11-30h], r9d
0x18000f2c2  lea     r9, [r11-28h]; void *
0x18000f2c6  mov     [r11-28h], r8d
0x18000f2ca  mov     r8d, 4; unsigned __int64
0x18000f2d0  mov     [r11-38h], r8
0x18000f2d4  call    ?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000f2d9  mov     rcx, [rsp+58h+var_18]
0x18000f2de  xor     rcx, rsp; StackCookie
0x18000f2e1  call    __security_check_cookie
0x18000f2e6  add     rsp, 58h
0x18000f2ea  retn
```
