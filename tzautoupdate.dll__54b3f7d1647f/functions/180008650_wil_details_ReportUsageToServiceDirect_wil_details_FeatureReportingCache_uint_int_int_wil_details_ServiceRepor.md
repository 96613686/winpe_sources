# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180008650`
- end: `0x180008767`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `279`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800085ac`

## callees

- `0x1800054c0`
- `0x180007734`
- `0x180008650`
- `0x180009bb0`
- `0x18000cb18`
- `0x18001d010`

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
  __int64 v12; // r8
  unsigned int v13; // r9d
  unsigned int v14; // esi
  int v15; // r12d
  unsigned int v16; // r14d
  int v17; // ebp
  unsigned int v18; // edx
  const char *v20; // [rsp+20h] [rbp-68h]
  _BYTE v21[88]; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v22; // [rsp+A0h] [rbp+18h]

  v11 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v21, a1, a5);
  v14 = 1;
  v15 = *v11;
  v16 = v11[1];
  v17 = v11[4];
  v22 = v11[2];
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(a2, a5, 1);
  if ( v15 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (char *)&wil::details::g_enabledStateManager,
      a2,
      a1);
  if ( v16 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v22, v16, v13, v20);
  if ( !v17 )
    wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(
      (wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager,
      (void (*)(void *))_lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_);
  if ( a3 )
  {
    v18 = a5 | 0x80000000;
    if ( !a4 )
      v18 = a5;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v18, 0, v13, v20);
  }
  if ( v17 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v12) = a8;
    g_wil_details_realtimeFeatureUsageHook(a2, a5, v12);
  }
  return v14;
}

```

## disassembly

```asm
0x180008650  mov     [rsp+arg_0], rbx
0x180008655  mov     [rsp+arg_18], r9d
0x18000865a  push    rbp
0x18000865b  push    rsi
0x18000865c  push    rdi
0x18000865d  push    r12
0x18000865f  push    r13
0x180008661  push    r14
0x180008663  push    r15
0x180008665  sub     rsp, 50h
0x180008669  mov     ebx, [rsp+88h+arg_20]
0x180008670  mov     edi, edx
0x180008672  mov     rdx, rcx
0x180008675  mov     r13d, r8d
0x180008678  mov     r15, rcx
0x18000867b  mov     r8d, ebx
0x18000867e  lea     rcx, [rsp+88h+var_58]
0x180008683  call    wil_details_FeatureReporting_RecordUsageInCache
0x180008688  mov     esi, 1
0x18000868d  mov     ecx, [rax+8]
0x180008690  mov     r12d, [rax]
0x180008693  mov     r14d, [rax+4]
0x180008697  mov     ebp, [rax+10h]
0x18000869a  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x1800086a1  mov     [rsp+88h+arg_10], ecx
0x1800086a8  test    rax, rax
0x1800086ab  jz      short loc_1800086C5
0x1800086ad  test    ebx, ebx
0x1800086af  jz      short loc_1800086B9
0x1800086b1  lea     ecx, [rbx-64h]
0x1800086b4  cmp     ecx, 31h ; '1'
0x1800086b7  ja      short loc_1800086C5
0x1800086b9  mov     r8d, esi
0x1800086bc  mov     edx, ebx
0x1800086be  mov     ecx, edi
0x1800086c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086c5  test    r12d, r12d
0x1800086c8  jz      short loc_1800086DB
0x1800086ca  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x1800086cd  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1800086d4  mov     edx, edi; unsigned int
0x1800086d6  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x1800086db  test    r14d, r14d
0x1800086de  jz      short loc_1800086F1
0x1800086e0  mov     edx, [rsp+88h+arg_10]; unsigned int
0x1800086e7  mov     r8d, r14d; unsigned int
0x1800086ea  mov     ecx, edi; this
0x1800086ec  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800086f1  test    ebp, ebp
0x1800086f3  jnz     short loc_180008708
0x1800086f5  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x1800086fc  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180008703  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x180008708  test    r13d, r13d
0x18000870b  jz      short loc_180008728
0x18000870d  mov     edx, ebx
0x18000870f  mov     ecx, edi; this
0x180008711  bts     edx, 1Fh
0x180008715  cmp     [rsp+88h+arg_18], 0
0x18000871d  cmovz   edx, ebx; unsigned int
0x180008720  xor     r8d, r8d; unsigned int
0x180008723  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180008728  test    ebp, ebp
0x18000872a  jnz     short loc_18000874B
0x18000872c  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180008733  test    rax, rax
0x180008736  jz      short loc_18000874D
0x180008738  mov     r8b, [rsp+88h+arg_38]
0x180008740  mov     edx, ebx
0x180008742  mov     ecx, edi
0x180008744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008749  jmp     short loc_18000874D
0x18000874b  xor     esi, esi
0x18000874d  mov     rbx, [rsp+88h+arg_0]
0x180008755  mov     eax, esi
0x180008757  add     rsp, 50h
0x18000875b  pop     r15
0x18000875d  pop     r14
0x18000875f  pop     r13
0x180008761  pop     r12
0x180008763  pop     rdi
0x180008764  pop     rsi
0x180008765  pop     rbp
0x180008766  retn
```
