# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180016ba4`
- end: `0x180016cb5`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180016b00`

## callees

- `0x1800109f8`
- `0x1800155dc`
- `0x180016420`
- `0x180016ba4`
- `0x18001706c`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        struct wil_details_FeatureReportingCache *a1,
        unsigned int a2,
        int a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        char a8)
{
  int *v11; // rax
  void (*v12)(void *); // rdx
  __int64 v13; // r8
  unsigned int v14; // r9d
  unsigned int v15; // esi
  int v16; // r12d
  unsigned int v17; // r14d
  int v18; // ebp
  unsigned int v19; // edx
  const char *v21; // [rsp+20h] [rbp-68h]
  _BYTE v22[88]; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v23; // [rsp+A0h] [rbp+18h]

  v11 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v22, a1, a5);
  v15 = 1;
  v16 = *v11;
  v17 = v11[1];
  v18 = v11[4];
  v23 = v11[2];
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(a2, a5, 1);
  if ( v16 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
      a2,
      a1);
  if ( v17 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v23, v17, v14, v21);
  if ( !v18 )
    wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(
      (wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager,
      v12);
  if ( a3 )
  {
    v19 = a5 | 0x80000000;
    if ( !a4 )
      v19 = a5;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v19, 0, v14, v21);
  }
  if ( v18 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v13) = a8;
    g_wil_details_realtimeFeatureUsageHook(a2, a5, v13);
  }
  return v15;
}

```

## disassembly

```asm
0x180016ba4  mov     [rsp+arg_0], rbx
0x180016ba9  mov     [rsp+arg_18], r9d
0x180016bae  push    rbp
0x180016baf  push    rsi
0x180016bb0  push    rdi
0x180016bb1  push    r12
0x180016bb3  push    r13
0x180016bb5  push    r14
0x180016bb7  push    r15
0x180016bb9  sub     rsp, 50h
0x180016bbd  mov     ebx, [rsp+88h+arg_20]
0x180016bc4  mov     edi, edx
0x180016bc6  mov     rdx, rcx
0x180016bc9  mov     r13d, r8d
0x180016bcc  mov     r15, rcx
0x180016bcf  mov     r8d, ebx
0x180016bd2  lea     rcx, [rsp+88h+var_58]
0x180016bd7  call    wil_details_FeatureReporting_RecordUsageInCache
0x180016bdc  mov     esi, 1
0x180016be1  mov     ecx, [rax+8]
0x180016be4  mov     r12d, [rax]
0x180016be7  mov     r14d, [rax+4]
0x180016beb  mov     ebp, [rax+10h]
0x180016bee  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180016bf5  mov     [rsp+88h+arg_10], ecx
0x180016bfc  test    rax, rax
0x180016bff  jz      short loc_180016C19
0x180016c01  test    ebx, ebx
0x180016c03  jz      short loc_180016C0D
0x180016c05  lea     ecx, [rbx-64h]
0x180016c08  cmp     ecx, 31h ; '1'
0x180016c0b  ja      short loc_180016C19
0x180016c0d  mov     r8d, esi
0x180016c10  mov     edx, ebx
0x180016c12  mov     ecx, edi
0x180016c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c19  test    r12d, r12d
0x180016c1c  jz      short loc_180016C2F
0x180016c1e  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x180016c21  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180016c28  mov     edx, edi; unsigned int
0x180016c2a  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180016c2f  test    r14d, r14d
0x180016c32  jz      short loc_180016C45
0x180016c34  mov     edx, [rsp+88h+arg_10]; unsigned int
0x180016c3b  mov     r8d, r14d; unsigned int
0x180016c3e  mov     ecx, edi; this
0x180016c40  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180016c45  test    ebp, ebp
0x180016c47  jnz     short loc_180016C55
0x180016c49  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180016c50  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x180016c55  test    r13d, r13d
0x180016c58  jz      short loc_180016C75
0x180016c5a  mov     edx, ebx
0x180016c5c  mov     ecx, edi; this
0x180016c5e  bts     edx, 1Fh
0x180016c62  cmp     [rsp+88h+arg_18], 0
0x180016c6a  cmovz   edx, ebx; unsigned int
0x180016c6d  xor     r8d, r8d; unsigned int
0x180016c70  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180016c75  test    ebp, ebp
0x180016c77  jnz     short loc_180016C98
0x180016c79  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180016c80  test    rax, rax
0x180016c83  jz      short loc_180016C9A
0x180016c85  mov     r8b, [rsp+88h+arg_38]
0x180016c8d  mov     edx, ebx
0x180016c8f  mov     ecx, edi
0x180016c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c96  jmp     short loc_180016C9A
0x180016c98  xor     esi, esi
0x180016c9a  mov     rbx, [rsp+88h+arg_0]
0x180016ca2  mov     eax, esi
0x180016ca4  add     rsp, 50h
0x180016ca8  pop     r15
0x180016caa  pop     r14
0x180016cac  pop     r13
0x180016cae  pop     r12
0x180016cb0  pop     rdi
0x180016cb1  pop     rsi
0x180016cb2  pop     rbp
0x180016cb3  retn
```
