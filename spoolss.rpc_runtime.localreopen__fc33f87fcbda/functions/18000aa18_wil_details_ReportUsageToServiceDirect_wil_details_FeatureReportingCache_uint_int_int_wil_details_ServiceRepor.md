# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000aa18`
- end: `0x18000ab30`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000a974`

## callees

- `0x180007ffc`
- `0x180009fc4`
- `0x18000aa18`
- `0x18000c094`
- `0x18001075c`
- `0x180017010`

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
0x18000aa18  mov     [rsp+arg_0], rbx
0x18000aa1d  mov     [rsp+arg_18], r9d
0x18000aa22  push    rbp
0x18000aa23  push    rsi
0x18000aa24  push    rdi
0x18000aa25  push    r12
0x18000aa27  push    r13
0x18000aa29  push    r14
0x18000aa2b  push    r15
0x18000aa2d  sub     rsp, 50h
0x18000aa31  mov     ebx, [rsp+88h+arg_20]
0x18000aa38  mov     edi, edx
0x18000aa3a  mov     rdx, rcx
0x18000aa3d  mov     r13d, r8d
0x18000aa40  mov     r15, rcx
0x18000aa43  mov     r8d, ebx
0x18000aa46  lea     rcx, [rsp+88h+var_58]
0x18000aa4b  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000aa50  mov     esi, 1
0x18000aa55  mov     ecx, [rax+8]
0x18000aa58  mov     r12d, [rax]
0x18000aa5b  mov     r14d, [rax+4]
0x18000aa5f  mov     ebp, [rax+10h]
0x18000aa62  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000aa69  mov     [rsp+88h+arg_10], ecx
0x18000aa70  test    rax, rax
0x18000aa73  jz      short loc_18000AA8D
0x18000aa75  test    ebx, ebx
0x18000aa77  jz      short loc_18000AA81
0x18000aa79  lea     ecx, [rbx-64h]
0x18000aa7c  cmp     ecx, 31h ; '1'
0x18000aa7f  ja      short loc_18000AA8D
0x18000aa81  mov     r8d, esi
0x18000aa84  mov     edx, ebx
0x18000aa86  mov     ecx, edi
0x18000aa88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa8d  test    r12d, r12d
0x18000aa90  jz      short loc_18000AAA3
0x18000aa92  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x18000aa95  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000aa9c  mov     edx, edi; unsigned int
0x18000aa9e  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000aaa3  test    r14d, r14d
0x18000aaa6  jz      short loc_18000AAB9
0x18000aaa8  mov     edx, [rsp+88h+arg_10]; unsigned int
0x18000aaaf  mov     r8d, r14d; unsigned int
0x18000aab2  mov     ecx, edi; this
0x18000aab4  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000aab9  test    ebp, ebp
0x18000aabb  jnz     short loc_18000AAD0
0x18000aabd  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x18000aac4  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18000aacb  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x18000aad0  test    r13d, r13d
0x18000aad3  jz      short loc_18000AAF0
0x18000aad5  mov     edx, ebx
0x18000aad7  mov     ecx, edi; this
0x18000aad9  bts     edx, 1Fh
0x18000aadd  cmp     [rsp+88h+arg_18], 0
0x18000aae5  cmovz   edx, ebx; unsigned int
0x18000aae8  xor     r8d, r8d; unsigned int
0x18000aaeb  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000aaf0  test    ebp, ebp
0x18000aaf2  jnz     short loc_18000AB13
0x18000aaf4  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000aafb  test    rax, rax
0x18000aafe  jz      short loc_18000AB15
0x18000ab00  mov     r8b, [rsp+88h+arg_38]
0x18000ab08  mov     edx, ebx
0x18000ab0a  mov     ecx, edi
0x18000ab0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab11  jmp     short loc_18000AB15
0x18000ab13  xor     esi, esi
0x18000ab15  mov     rbx, [rsp+88h+arg_0]
0x18000ab1d  mov     eax, esi
0x18000ab1f  add     rsp, 50h
0x18000ab23  pop     r15
0x18000ab25  pop     r14
0x18000ab27  pop     r13
0x18000ab29  pop     r12
0x18000ab2b  pop     rdi
0x18000ab2c  pop     rsi
0x18000ab2d  pop     rbp
0x18000ab2e  retn
```
