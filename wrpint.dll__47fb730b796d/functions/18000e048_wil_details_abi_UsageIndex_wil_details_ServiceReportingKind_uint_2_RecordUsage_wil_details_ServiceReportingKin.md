# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)

- ea: `0x18000e048`
- end: `0x18000e093`
- name: `?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z`
- size: `75`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *, int, int, unsigned int)`
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
0x18000e048  mov     r11, rsp
0x18000e04b  sub     rsp, 58h
0x18000e04f  mov     rax, cs:__security_cookie
0x18000e056  xor     rax, rsp
0x18000e059  mov     [rsp+58h+var_18], rax
0x18000e05e  mov     [rsp+58h+var_20], edx
0x18000e062  lea     rdx, [r11-20h]; Buf1
0x18000e066  mov     [r11-30h], r9d
0x18000e06a  lea     r9, [r11-28h]; void *
0x18000e06e  mov     [r11-28h], r8d
0x18000e072  mov     r8d, 4; Size
0x18000e078  mov     [r11-38h], r8
0x18000e07c  call    ?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000e081  mov     rcx, [rsp+58h+var_18]
0x18000e086  xor     rcx, rsp; StackCookie
0x18000e089  call    __security_check_cookie
0x18000e08e  add     rsp, 58h
0x18000e092  retn
```
