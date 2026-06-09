# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x1800110f0`
- end: `0x18001120a`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18001104c`

## callees

- `0x180008e94`
- `0x18000f734`
- `0x180010e28`
- `0x1800110f0`
- `0x180011e9c`
- `0x180016010`

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

  v11 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v21, a1, a5, 0);
  v14 = 1;
  v15 = *v11;
  v16 = v11[1];
  v17 = v11[4];
  v22 = v11[2];
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(a2, a5, 1);
  if ( v15 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (wil::details::EnabledStateManager *)wil::details::g_enabledStateManager,
      a2,
      a1);
  if ( v16 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v22, v16, v13, v20);
  if ( !v17 )
    wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(
      (wil::details::EnabledStateManager *)wil::details::g_enabledStateManager,
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
0x1800110f0  mov     [rsp+arg_0], rbx
0x1800110f5  mov     [rsp+arg_18], r9d
0x1800110fa  push    rbp
0x1800110fb  push    rsi
0x1800110fc  push    rdi
0x1800110fd  push    r12
0x1800110ff  push    r13
0x180011101  push    r14
0x180011103  push    r15
0x180011105  sub     rsp, 50h
0x180011109  mov     ebx, [rsp+88h+arg_20]
0x180011110  mov     edi, edx
0x180011112  mov     rdx, rcx
0x180011115  mov     r13d, r8d
0x180011118  mov     r15, rcx
0x18001111b  xor     r9d, r9d
0x18001111e  lea     rcx, [rsp+88h+var_58]
0x180011123  mov     r8d, ebx
0x180011126  call    wil_details_FeatureReporting_RecordUsageInCache
0x18001112b  mov     esi, 1
0x180011130  mov     ecx, [rax+8]
0x180011133  mov     r12d, [rax]
0x180011136  mov     r14d, [rax+4]
0x18001113a  mov     ebp, [rax+10h]
0x18001113d  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180011144  mov     [rsp+88h+arg_10], ecx
0x18001114b  test    rax, rax
0x18001114e  jz      short loc_180011168
0x180011150  test    ebx, ebx
0x180011152  jz      short loc_18001115C
0x180011154  lea     ecx, [rbx-64h]
0x180011157  cmp     ecx, 31h ; '1'
0x18001115a  ja      short loc_180011168
0x18001115c  mov     r8d, esi
0x18001115f  mov     edx, ebx
0x180011161  mov     ecx, edi
0x180011163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011168  test    r12d, r12d
0x18001116b  jz      short loc_18001117E
0x18001116d  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x180011170  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180011177  mov     edx, edi; unsigned int
0x180011179  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18001117e  test    r14d, r14d
0x180011181  jz      short loc_180011194
0x180011183  mov     edx, [rsp+88h+arg_10]; unsigned int
0x18001118a  mov     r8d, r14d; unsigned int
0x18001118d  mov     ecx, edi; this
0x18001118f  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180011194  test    ebp, ebp
0x180011196  jnz     short loc_1800111AB
0x180011198  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x18001119f  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x1800111a6  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x1800111ab  test    r13d, r13d
0x1800111ae  jz      short loc_1800111CB
0x1800111b0  mov     edx, ebx
0x1800111b2  mov     ecx, edi; this
0x1800111b4  bts     edx, 1Fh
0x1800111b8  cmp     [rsp+88h+arg_18], 0
0x1800111c0  cmovz   edx, ebx; unsigned int
0x1800111c3  xor     r8d, r8d; unsigned int
0x1800111c6  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800111cb  test    ebp, ebp
0x1800111cd  jnz     short loc_1800111EE
0x1800111cf  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x1800111d6  test    rax, rax
0x1800111d9  jz      short loc_1800111F0
0x1800111db  mov     r8b, [rsp+88h+arg_38]
0x1800111e3  mov     edx, ebx
0x1800111e5  mov     ecx, edi
0x1800111e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111ec  jmp     short loc_1800111F0
0x1800111ee  xor     esi, esi
0x1800111f0  mov     rbx, [rsp+88h+arg_0]
0x1800111f8  mov     eax, esi
0x1800111fa  add     rsp, 50h
0x1800111fe  pop     r15
0x180011200  pop     r14
0x180011202  pop     r13
0x180011204  pop     r12
0x180011206  pop     rdi
0x180011207  pop     rsi
0x180011208  pop     rbp
0x180011209  retn
```
