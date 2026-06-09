# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180016e5c`
- end: `0x180016f64`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `264`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, __int64, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180016d84`

## callees

- `0x1800151dc`
- `0x180016238`
- `0x180016e5c`
- `0x180017724`
- `0x180018558`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        struct wil_details_FeatureReportingCache *a1,
        __int64 a2,
        int a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        char a8)
{
  int *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int v13; // r9d
  unsigned int v14; // edi
  int v15; // r15d
  unsigned int v16; // ebp
  unsigned int v17; // r13d
  int v18; // esi
  unsigned int v19; // edx
  const char *v21; // [rsp+20h] [rbp-78h]
  _BYTE v22[104]; // [rsp+30h] [rbp-68h] BYREF

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v22, a1, a5);
  v14 = 1;
  v15 = *v10;
  v16 = v10[1];
  v17 = v10[2];
  v18 = v10[4];
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(46832940, a5, 1);
  if ( v15 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (char *)&wil::details::g_enabledStateManager,
      v11,
      a1);
  if ( v16 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x2CA9D2C, v17, v16, v13, v21);
  if ( !v18 )
    wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(
      (wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager,
      (void (*)(void *))_lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_);
  if ( a3 )
  {
    v19 = a5 | 0x80000000;
    if ( !a4 )
      v19 = a5;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x2CA9D2C, v19, 0, v13, v21);
  }
  if ( v18 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v12) = a8;
    g_wil_details_realtimeFeatureUsageHook(46832940, a5, v12);
  }
  return v14;
}

```

## disassembly

```asm
0x180016e5c  mov     [rsp+arg_18], r9d
0x180016e61  push    rbx
0x180016e62  push    rbp
0x180016e63  push    rsi
0x180016e64  push    rdi
0x180016e65  push    r12
0x180016e67  push    r13
0x180016e69  push    r14
0x180016e6b  push    r15
0x180016e6d  sub     rsp, 58h
0x180016e71  mov     ebx, [rsp+98h+arg_20]
0x180016e78  mov     r12d, r8d
0x180016e7b  mov     r14, rcx
0x180016e7e  mov     rdx, rcx
0x180016e81  mov     r8d, ebx
0x180016e84  lea     rcx, [rsp+98h+var_68]
0x180016e89  call    wil_details_FeatureReporting_RecordUsageInCache
0x180016e8e  mov     edi, 1
0x180016e93  mov     r15d, [rax]
0x180016e96  mov     ebp, [rax+4]
0x180016e99  mov     r13d, [rax+8]
0x180016e9d  mov     esi, [rax+10h]
0x180016ea0  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180016ea7  test    rax, rax
0x180016eaa  jz      short loc_180016EC7
0x180016eac  test    ebx, ebx
0x180016eae  jz      short loc_180016EB8
0x180016eb0  lea     ecx, [rbx-64h]
0x180016eb3  cmp     ecx, 31h ; '1'
0x180016eb6  ja      short loc_180016EC7
0x180016eb8  mov     r8d, edi
0x180016ebb  mov     edx, ebx
0x180016ebd  mov     ecx, 2CA9D2Ch
0x180016ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ec7  test    r15d, r15d
0x180016eca  jz      short loc_180016EDB
0x180016ecc  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x180016ecf  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180016ed6  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180016edb  test    ebp, ebp
0x180016edd  jz      short loc_180016EEF
0x180016edf  mov     r8d, ebp; unsigned int
0x180016ee2  mov     edx, r13d; unsigned int
0x180016ee5  mov     ecx, 2CA9D2Ch; this
0x180016eea  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180016eef  test    esi, esi
0x180016ef1  jnz     short loc_180016F06
0x180016ef3  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x180016efa  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180016f01  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x180016f06  test    r12d, r12d
0x180016f09  jz      short loc_180016F29
0x180016f0b  mov     edx, ebx
0x180016f0d  mov     ecx, 2CA9D2Ch; this
0x180016f12  bts     edx, 1Fh
0x180016f16  cmp     [rsp+98h+arg_18], 0
0x180016f1e  cmovz   edx, ebx; unsigned int
0x180016f21  xor     r8d, r8d; unsigned int
0x180016f24  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180016f29  test    esi, esi
0x180016f2b  jnz     short loc_180016F4F
0x180016f2d  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180016f34  test    rax, rax
0x180016f37  jz      short loc_180016F51
0x180016f39  mov     r8b, [rsp+98h+arg_38]
0x180016f41  mov     edx, ebx
0x180016f43  mov     ecx, 2CA9D2Ch
0x180016f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f4d  jmp     short loc_180016F51
0x180016f4f  xor     edi, edi
0x180016f51  mov     eax, edi
0x180016f53  add     rsp, 58h
0x180016f57  pop     r15
0x180016f59  pop     r14
0x180016f5b  pop     r13
0x180016f5d  pop     r12
0x180016f5f  pop     rdi
0x180016f60  pop     rsi
0x180016f61  pop     rbp
0x180016f62  pop     rbx
0x180016f63  retn
```
