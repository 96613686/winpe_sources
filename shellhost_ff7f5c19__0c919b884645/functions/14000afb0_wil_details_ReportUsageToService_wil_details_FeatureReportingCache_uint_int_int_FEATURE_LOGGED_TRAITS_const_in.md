# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x14000afb0`
- end: `0x14000b053`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `163`
- prototype: ``
- caller_count: `13`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140056594`
- `0x140056a90`
- `0x140056c84`
- `0x14005a4cc`
- `0x14005a558`
- `0x14005a5e0`
- `0x14005a66c`
- `0x14005a6f4`
- `0x14005a77c`
- `0x14005a804`
- `0x14005a88c`
- `0x14005a914`
- `0x14005a9a0`

## callees

- `0x14000afb0`
- `0x14005aa28`
- `0x14006031c`
- `0x140067010`

## pseudocode

```c
void __fastcall wil::details::ReportUsageToService(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        unsigned int a7)
{
  unsigned int v8; // r10d
  __int64 v9; // r11
  char v10; // [rsp+30h] [rbp-28h]

  if ( a7 )
  {
    wil_details_MapReportingKind(a7, a6);
    if ( (unsigned int)wil::details::ReportUsageToServiceDirect(v9, a2, v8) )
    {
      if ( g_wil_details_pfnFeatureLoggingHook )
      {
        v10 = 0;
        g_wil_details_pfnFeatureLoggingHook(a2, a5, 0, a6, &a7, 0, v10, 1);
      }
    }
  }
}

```

## disassembly

```asm
0x14000afb0  push    rbx
0x14000afb2  sub     rsp, 50h
0x14000afb6  mov     r11, rcx
0x14000afb9  mov     r10d, r8d
0x14000afbc  mov     ecx, [rsp+58h+arg_30]
0x14000afc3  mov     ebx, edx
0x14000afc5  test    ecx, ecx
0x14000afc7  jz      loc_14000B04D
0x14000afcd  mov     edx, [rsp+58h+arg_28]
0x14000afd4  mov     [rsp+58h+arg_0], rsi
0x14000afd9  call    wil_details_MapReportingKind
0x14000afde  mov     rsi, [rsp+58h+arg_20]
0x14000afe6  mov     r8d, r10d
0x14000afe9  mov     rcx, r11
0x14000afec  movzx   edx, byte ptr [rsi+4]
0x14000aff0  mov     byte ptr [rsp+58h+var_20], dl
0x14000aff4  mov     edx, ebx
0x14000aff6  mov     dword ptr [rsp+58h+var_38], eax
0x14000affa  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x14000afff  test    eax, eax
0x14000b001  jz      short loc_14000B048
0x14000b003  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x14000b00a  test    rax, rax
0x14000b00d  jz      short loc_14000B048
0x14000b00f  mov     r9d, [rsp+58h+arg_28]
0x14000b017  lea     rcx, [rsp+58h+arg_30]
0x14000b01f  mov     [rsp+58h+var_20], 1
0x14000b028  xor     r8d, r8d
0x14000b02b  mov     [rsp+58h+var_28], 0
0x14000b030  mov     rdx, rsi
0x14000b033  mov     [rsp+58h+var_30], 0
0x14000b03c  mov     [rsp+58h+var_38], rcx
0x14000b041  mov     ecx, ebx
0x14000b043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b048  mov     rsi, [rsp+58h+arg_0]
0x14000b04d  add     rsp, 50h
0x14000b051  pop     rbx
0x14000b052  retn
```
