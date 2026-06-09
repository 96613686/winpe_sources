# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x14005aa28`
- end: `0x14005ab3f`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `279`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1400093dc`
- `0x14000afb0`

## callees

- `0x14004a354`
- `0x14005535c`
- `0x14005a0ec`
- `0x14005aa28`
- `0x1400601a0`
- `0x140067010`

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
      (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
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
0x14005aa28  mov     [rsp+arg_0], rbx
0x14005aa2d  mov     [rsp+arg_18], r9d
0x14005aa32  push    rbp
0x14005aa33  push    rsi
0x14005aa34  push    rdi
0x14005aa35  push    r12
0x14005aa37  push    r13
0x14005aa39  push    r14
0x14005aa3b  push    r15
0x14005aa3d  sub     rsp, 50h
0x14005aa41  mov     ebx, [rsp+88h+arg_20]
0x14005aa48  mov     edi, edx
0x14005aa4a  mov     rdx, rcx
0x14005aa4d  mov     r13d, r8d
0x14005aa50  mov     r15, rcx
0x14005aa53  mov     r8d, ebx
0x14005aa56  lea     rcx, [rsp+88h+var_58]
0x14005aa5b  call    wil_details_FeatureReporting_RecordUsageInCache
0x14005aa60  mov     esi, 1
0x14005aa65  mov     ecx, [rax+8]
0x14005aa68  mov     r12d, [rax]
0x14005aa6b  mov     r14d, [rax+4]
0x14005aa6f  mov     ebp, [rax+10h]
0x14005aa72  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x14005aa79  mov     [rsp+88h+arg_10], ecx
0x14005aa80  test    rax, rax
0x14005aa83  jz      short loc_14005AA9D
0x14005aa85  test    ebx, ebx
0x14005aa87  jz      short loc_14005AA91
0x14005aa89  lea     ecx, [rbx-64h]
0x14005aa8c  cmp     ecx, 31h ; '1'
0x14005aa8f  ja      short loc_14005AA9D
0x14005aa91  mov     r8d, esi
0x14005aa94  mov     edx, ebx
0x14005aa96  mov     ecx, edi
0x14005aa98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005aa9d  test    r12d, r12d
0x14005aaa0  jz      short loc_14005AAB3
0x14005aaa2  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x14005aaa5  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x14005aaac  mov     edx, edi; unsigned int
0x14005aaae  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x14005aab3  test    r14d, r14d
0x14005aab6  jz      short loc_14005AAC9
0x14005aab8  mov     edx, [rsp+88h+arg_10]; unsigned int
0x14005aabf  mov     r8d, r14d; unsigned int
0x14005aac2  mov     ecx, edi; this
0x14005aac4  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x14005aac9  test    ebp, ebp
0x14005aacb  jnz     short loc_14005AAE0
0x14005aacd  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x14005aad4  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x14005aadb  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x14005aae0  test    r13d, r13d
0x14005aae3  jz      short loc_14005AB00
0x14005aae5  mov     edx, ebx
0x14005aae7  mov     ecx, edi; this
0x14005aae9  bts     edx, 1Fh
0x14005aaed  cmp     [rsp+88h+arg_18], 0
0x14005aaf5  cmovz   edx, ebx; unsigned int
0x14005aaf8  xor     r8d, r8d; unsigned int
0x14005aafb  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x14005ab00  test    ebp, ebp
0x14005ab02  jnz     short loc_14005AB23
0x14005ab04  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x14005ab0b  test    rax, rax
0x14005ab0e  jz      short loc_14005AB25
0x14005ab10  mov     r8b, [rsp+88h+arg_38]
0x14005ab18  mov     edx, ebx
0x14005ab1a  mov     ecx, edi
0x14005ab1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005ab21  jmp     short loc_14005AB25
0x14005ab23  xor     esi, esi
0x14005ab25  mov     rbx, [rsp+88h+arg_0]
0x14005ab2d  mov     eax, esi
0x14005ab2f  add     rsp, 50h
0x14005ab33  pop     r15
0x14005ab35  pop     r14
0x14005ab37  pop     r13
0x14005ab39  pop     r12
0x14005ab3b  pop     rdi
0x14005ab3c  pop     rsi
0x14005ab3d  pop     rbp
0x14005ab3e  retn
```
