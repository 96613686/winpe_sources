# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)

- ea: `0x18000e09c`
- end: `0x18000e0eb`
- name: `?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z`
- size: `79`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000def4`

## callees

- `0x18000e1ac`
- `0x18001b7b0`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(
        wil::details_abi::RawUsageIndex *a1,
        int a2,
        int a3)
{
  int v4; // [rsp+30h] [rbp-28h] BYREF
  int v5; // [rsp+38h] [rbp-20h] BYREF

  v5 = a2;
  v4 = a3;
  return wil::details_abi::RawUsageIndex::RecordUsage(a1, &v5, 4u, &v4, 4u, 1u);
}

```

## disassembly

```asm
0x18000e09c  mov     r11, rsp
0x18000e09f  sub     rsp, 58h
0x18000e0a3  mov     rax, cs:__security_cookie
0x18000e0aa  xor     rax, rsp
0x18000e0ad  mov     [rsp+58h+var_18], rax
0x18000e0b2  mov     [rsp+58h+var_20], edx
0x18000e0b6  lea     r9, [r11-28h]; void *
0x18000e0ba  mov     [r11-28h], r8d
0x18000e0be  lea     rdx, [r11-20h]; Buf1
0x18000e0c2  mov     r8d, 4; Size
0x18000e0c8  mov     [rsp+58h+var_30], 1; unsigned int
0x18000e0d0  mov     [r11-38h], r8
0x18000e0d4  call    ?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000e0d9  mov     rcx, [rsp+58h+var_18]
0x18000e0de  xor     rcx, rsp; StackCookie
0x18000e0e1  call    __security_check_cookie
0x18000e0e6  add     rsp, 58h
0x18000e0ea  retn
```
