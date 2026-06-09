# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000a1ac`
- end: `0x18000a2c3`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000a108`

## callees

- `0x180007bb8`
- `0x18000984c`
- `0x18000a1ac`
- `0x18000b770`
- `0x18000f688`
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
0x18000a1ac  mov     [rsp+arg_0], rbx
0x18000a1b1  mov     [rsp+arg_18], r9d
0x18000a1b6  push    rbp
0x18000a1b7  push    rsi
0x18000a1b8  push    rdi
0x18000a1b9  push    r12
0x18000a1bb  push    r13
0x18000a1bd  push    r14
0x18000a1bf  push    r15
0x18000a1c1  sub     rsp, 50h
0x18000a1c5  mov     ebx, [rsp+88h+arg_20]
0x18000a1cc  mov     edi, edx
0x18000a1ce  mov     rdx, rcx
0x18000a1d1  mov     r13d, r8d
0x18000a1d4  mov     r15, rcx
0x18000a1d7  mov     r8d, ebx
0x18000a1da  lea     rcx, [rsp+88h+var_58]
0x18000a1df  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000a1e4  mov     esi, 1
0x18000a1e9  mov     ecx, [rax+8]
0x18000a1ec  mov     r12d, [rax]
0x18000a1ef  mov     r14d, [rax+4]
0x18000a1f3  mov     ebp, [rax+10h]
0x18000a1f6  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000a1fd  mov     [rsp+88h+arg_10], ecx
0x18000a204  test    rax, rax
0x18000a207  jz      short loc_18000A221
0x18000a209  test    ebx, ebx
0x18000a20b  jz      short loc_18000A215
0x18000a20d  lea     ecx, [rbx-64h]
0x18000a210  cmp     ecx, 31h ; '1'
0x18000a213  ja      short loc_18000A221
0x18000a215  mov     r8d, esi
0x18000a218  mov     edx, ebx
0x18000a21a  mov     ecx, edi
0x18000a21c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a221  test    r12d, r12d
0x18000a224  jz      short loc_18000A237
0x18000a226  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x18000a229  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000a230  mov     edx, edi; unsigned int
0x18000a232  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000a237  test    r14d, r14d
0x18000a23a  jz      short loc_18000A24D
0x18000a23c  mov     edx, [rsp+88h+arg_10]; unsigned int
0x18000a243  mov     r8d, r14d; unsigned int
0x18000a246  mov     ecx, edi; this
0x18000a248  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000a24d  test    ebp, ebp
0x18000a24f  jnz     short loc_18000A264
0x18000a251  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x18000a258  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18000a25f  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x18000a264  test    r13d, r13d
0x18000a267  jz      short loc_18000A284
0x18000a269  mov     edx, ebx
0x18000a26b  mov     ecx, edi; this
0x18000a26d  bts     edx, 1Fh
0x18000a271  cmp     [rsp+88h+arg_18], 0
0x18000a279  cmovz   edx, ebx; unsigned int
0x18000a27c  xor     r8d, r8d; unsigned int
0x18000a27f  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000a284  test    ebp, ebp
0x18000a286  jnz     short loc_18000A2A7
0x18000a288  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000a28f  test    rax, rax
0x18000a292  jz      short loc_18000A2A9
0x18000a294  mov     r8b, [rsp+88h+arg_38]
0x18000a29c  mov     edx, ebx
0x18000a29e  mov     ecx, edi
0x18000a2a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2a5  jmp     short loc_18000A2A9
0x18000a2a7  xor     esi, esi
0x18000a2a9  mov     rbx, [rsp+88h+arg_0]
0x18000a2b1  mov     eax, esi
0x18000a2b3  add     rsp, 50h
0x18000a2b7  pop     r15
0x18000a2b9  pop     r14
0x18000a2bb  pop     r13
0x18000a2bd  pop     r12
0x18000a2bf  pop     rdi
0x18000a2c0  pop     rsi
0x18000a2c1  pop     rbp
0x18000a2c2  retn
```
