# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180010938`
- end: `0x180010a52`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180010894`

## callees

- `0x18000b600`
- `0x18000d70c`
- `0x18000fa8c`
- `0x180010938`
- `0x180011da4`
- `0x18003d010`

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
0x180010938  mov     [rsp+arg_0], rbx
0x18001093d  mov     [rsp+arg_18], r9d
0x180010942  push    rbp
0x180010943  push    rsi
0x180010944  push    rdi
0x180010945  push    r12
0x180010947  push    r13
0x180010949  push    r14
0x18001094b  push    r15
0x18001094d  sub     rsp, 50h
0x180010951  mov     ebx, [rsp+88h+arg_20]
0x180010958  mov     edi, edx
0x18001095a  mov     rdx, rcx
0x18001095d  mov     r13d, r8d
0x180010960  mov     r15, rcx
0x180010963  xor     r9d, r9d
0x180010966  lea     rcx, [rsp+88h+var_58]
0x18001096b  mov     r8d, ebx
0x18001096e  call    wil_details_FeatureReporting_RecordUsageInCache
0x180010973  mov     esi, 1
0x180010978  mov     ecx, [rax+8]
0x18001097b  mov     r12d, [rax]
0x18001097e  mov     r14d, [rax+4]
0x180010982  mov     ebp, [rax+10h]
0x180010985  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18001098c  mov     [rsp+88h+arg_10], ecx
0x180010993  test    rax, rax
0x180010996  jz      short loc_1800109B0
0x180010998  test    ebx, ebx
0x18001099a  jz      short loc_1800109A4
0x18001099c  lea     ecx, [rbx-64h]
0x18001099f  cmp     ecx, 31h ; '1'
0x1800109a2  ja      short loc_1800109B0
0x1800109a4  mov     r8d, esi
0x1800109a7  mov     edx, ebx
0x1800109a9  mov     ecx, edi
0x1800109ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109b0  test    r12d, r12d
0x1800109b3  jz      short loc_1800109C6
0x1800109b5  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x1800109b8  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1800109bf  mov     edx, edi; unsigned int
0x1800109c1  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x1800109c6  test    r14d, r14d
0x1800109c9  jz      short loc_1800109DC
0x1800109cb  mov     edx, [rsp+88h+arg_10]; unsigned int
0x1800109d2  mov     r8d, r14d; unsigned int
0x1800109d5  mov     ecx, edi; this
0x1800109d7  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800109dc  test    ebp, ebp
0x1800109de  jnz     short loc_1800109F3
0x1800109e0  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x1800109e7  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x1800109ee  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x1800109f3  test    r13d, r13d
0x1800109f6  jz      short loc_180010A13
0x1800109f8  mov     edx, ebx
0x1800109fa  mov     ecx, edi; this
0x1800109fc  bts     edx, 1Fh
0x180010a00  cmp     [rsp+88h+arg_18], 0
0x180010a08  cmovz   edx, ebx; unsigned int
0x180010a0b  xor     r8d, r8d; unsigned int
0x180010a0e  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180010a13  test    ebp, ebp
0x180010a15  jnz     short loc_180010A36
0x180010a17  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180010a1e  test    rax, rax
0x180010a21  jz      short loc_180010A38
0x180010a23  mov     r8b, [rsp+88h+arg_38]
0x180010a2b  mov     edx, ebx
0x180010a2d  mov     ecx, edi
0x180010a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a34  jmp     short loc_180010A38
0x180010a36  xor     esi, esi
0x180010a38  mov     rbx, [rsp+88h+arg_0]
0x180010a40  mov     eax, esi
0x180010a42  add     rsp, 50h
0x180010a46  pop     r15
0x180010a48  pop     r14
0x180010a4a  pop     r13
0x180010a4c  pop     r12
0x180010a4e  pop     rdi
0x180010a4f  pop     rsi
0x180010a50  pop     rbp
0x180010a51  retn
```
