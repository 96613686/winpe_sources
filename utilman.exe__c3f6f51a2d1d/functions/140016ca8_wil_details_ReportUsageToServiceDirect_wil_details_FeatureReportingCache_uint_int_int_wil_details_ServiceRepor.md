# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x140016ca8`
- end: `0x140016dc0`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x140016c04`

## callees

- `0x1400092d8`
- `0x140014c80`
- `0x140016874`
- `0x140016ca8`
- `0x140018474`
- `0x140029010`

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
0x140016ca8  mov     [rsp+arg_0], rbx
0x140016cad  mov     [rsp+arg_18], r9d
0x140016cb2  push    rbp
0x140016cb3  push    rsi
0x140016cb4  push    rdi
0x140016cb5  push    r12
0x140016cb7  push    r13
0x140016cb9  push    r14
0x140016cbb  push    r15
0x140016cbd  sub     rsp, 50h
0x140016cc1  mov     ebx, [rsp+88h+arg_20]
0x140016cc8  mov     edi, edx
0x140016cca  mov     rdx, rcx
0x140016ccd  mov     r13d, r8d
0x140016cd0  mov     r15, rcx
0x140016cd3  mov     r8d, ebx
0x140016cd6  lea     rcx, [rsp+88h+var_58]
0x140016cdb  call    wil_details_FeatureReporting_RecordUsageInCache
0x140016ce0  mov     esi, 1
0x140016ce5  mov     ecx, [rax+8]
0x140016ce8  mov     r12d, [rax]
0x140016ceb  mov     r14d, [rax+4]
0x140016cef  mov     ebp, [rax+10h]
0x140016cf2  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x140016cf9  mov     [rsp+88h+arg_10], ecx
0x140016d00  test    rax, rax
0x140016d03  jz      short loc_140016D1D
0x140016d05  test    ebx, ebx
0x140016d07  jz      short loc_140016D11
0x140016d09  lea     ecx, [rbx-64h]
0x140016d0c  cmp     ecx, 31h ; '1'
0x140016d0f  ja      short loc_140016D1D
0x140016d11  mov     r8d, esi
0x140016d14  mov     edx, ebx
0x140016d16  mov     ecx, edi
0x140016d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016d1d  test    r12d, r12d
0x140016d20  jz      short loc_140016D33
0x140016d22  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x140016d25  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x140016d2c  mov     edx, edi; unsigned int
0x140016d2e  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x140016d33  test    r14d, r14d
0x140016d36  jz      short loc_140016D49
0x140016d38  mov     edx, [rsp+88h+arg_10]; unsigned int
0x140016d3f  mov     r8d, r14d; unsigned int
0x140016d42  mov     ecx, edi; this
0x140016d44  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x140016d49  test    ebp, ebp
0x140016d4b  jnz     short loc_140016D60
0x140016d4d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x140016d54  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x140016d5b  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x140016d60  test    r13d, r13d
0x140016d63  jz      short loc_140016D80
0x140016d65  mov     edx, ebx
0x140016d67  mov     ecx, edi; this
0x140016d69  bts     edx, 1Fh
0x140016d6d  cmp     [rsp+88h+arg_18], 0
0x140016d75  cmovz   edx, ebx; unsigned int
0x140016d78  xor     r8d, r8d; unsigned int
0x140016d7b  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x140016d80  test    ebp, ebp
0x140016d82  jnz     short loc_140016DA3
0x140016d84  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x140016d8b  test    rax, rax
0x140016d8e  jz      short loc_140016DA5
0x140016d90  mov     r8b, [rsp+88h+arg_38]
0x140016d98  mov     edx, ebx
0x140016d9a  mov     ecx, edi
0x140016d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016da1  jmp     short loc_140016DA5
0x140016da3  xor     esi, esi
0x140016da5  mov     rbx, [rsp+88h+arg_0]
0x140016dad  mov     eax, esi
0x140016daf  add     rsp, 50h
0x140016db3  pop     r15
0x140016db5  pop     r14
0x140016db7  pop     r13
0x140016db9  pop     r12
0x140016dbb  pop     rdi
0x140016dbc  pop     rsi
0x140016dbd  pop     rbp
0x140016dbe  retn
```
