# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x1800208b0`
- end: `0x1800209c7`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18002080c`

## callees

- `0x18001ac68`
- `0x18001f934`
- `0x1800208b0`
- `0x180026d8c`
- `0x1800275d0`
- `0x18002b010`

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
      (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
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
0x1800208b0  mov     [rsp+arg_0], rbx
0x1800208b5  mov     [rsp+arg_18], r9d
0x1800208ba  push    rbp
0x1800208bb  push    rsi
0x1800208bc  push    rdi
0x1800208bd  push    r12
0x1800208bf  push    r13
0x1800208c1  push    r14
0x1800208c3  push    r15
0x1800208c5  sub     rsp, 50h
0x1800208c9  mov     ebx, [rsp+88h+arg_20]
0x1800208d0  mov     edi, edx
0x1800208d2  mov     rdx, rcx
0x1800208d5  mov     r13d, r8d
0x1800208d8  mov     r15, rcx
0x1800208db  mov     r8d, ebx
0x1800208de  lea     rcx, [rsp+88h+var_58]
0x1800208e3  call    wil_details_FeatureReporting_RecordUsageInCache
0x1800208e8  mov     esi, 1
0x1800208ed  mov     ecx, [rax+8]
0x1800208f0  mov     r12d, [rax]
0x1800208f3  mov     r14d, [rax+4]
0x1800208f7  mov     ebp, [rax+10h]
0x1800208fa  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180020901  mov     [rsp+88h+arg_10], ecx
0x180020908  test    rax, rax
0x18002090b  jz      short loc_180020925
0x18002090d  test    ebx, ebx
0x18002090f  jz      short loc_180020919
0x180020911  lea     ecx, [rbx-64h]
0x180020914  cmp     ecx, 31h ; '1'
0x180020917  ja      short loc_180020925
0x180020919  mov     r8d, esi
0x18002091c  mov     edx, ebx
0x18002091e  mov     ecx, edi
0x180020920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020925  test    r12d, r12d
0x180020928  jz      short loc_18002093B
0x18002092a  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x18002092d  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180020934  mov     edx, edi; unsigned int
0x180020936  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18002093b  test    r14d, r14d
0x18002093e  jz      short loc_180020951
0x180020940  mov     edx, [rsp+88h+arg_10]; unsigned int
0x180020947  mov     r8d, r14d; unsigned int
0x18002094a  mov     ecx, edi; this
0x18002094c  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180020951  test    ebp, ebp
0x180020953  jnz     short loc_180020968
0x180020955  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x18002095c  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180020963  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x180020968  test    r13d, r13d
0x18002096b  jz      short loc_180020988
0x18002096d  mov     edx, ebx
0x18002096f  mov     ecx, edi; this
0x180020971  bts     edx, 1Fh
0x180020975  cmp     [rsp+88h+arg_18], 0
0x18002097d  cmovz   edx, ebx; unsigned int
0x180020980  xor     r8d, r8d; unsigned int
0x180020983  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180020988  test    ebp, ebp
0x18002098a  jnz     short loc_1800209AB
0x18002098c  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180020993  test    rax, rax
0x180020996  jz      short loc_1800209AD
0x180020998  mov     r8b, [rsp+88h+arg_38]
0x1800209a0  mov     edx, ebx
0x1800209a2  mov     ecx, edi
0x1800209a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209a9  jmp     short loc_1800209AD
0x1800209ab  xor     esi, esi
0x1800209ad  mov     rbx, [rsp+88h+arg_0]
0x1800209b5  mov     eax, esi
0x1800209b7  add     rsp, 50h
0x1800209bb  pop     r15
0x1800209bd  pop     r14
0x1800209bf  pop     r13
0x1800209c1  pop     r12
0x1800209c3  pop     rdi
0x1800209c4  pop     rsi
0x1800209c5  pop     rbp
0x1800209c6  retn
```
