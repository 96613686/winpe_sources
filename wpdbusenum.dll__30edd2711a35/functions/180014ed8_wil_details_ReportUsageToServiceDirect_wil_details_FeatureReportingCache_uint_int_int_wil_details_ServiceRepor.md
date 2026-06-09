# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180014ed8`
- end: `0x180014fef`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `279`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180014da0`

## callees

- `0x18000d660`
- `0x180014824`
- `0x180014c7c`
- `0x180014ed8`
- `0x18001520c`
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
0x180014ed8  mov     [rsp+arg_0], rbx
0x180014edd  mov     [rsp+arg_18], r9d
0x180014ee2  push    rbp
0x180014ee3  push    rsi
0x180014ee4  push    rdi
0x180014ee5  push    r12
0x180014ee7  push    r13
0x180014ee9  push    r14
0x180014eeb  push    r15
0x180014eed  sub     rsp, 50h
0x180014ef1  mov     ebx, [rsp+88h+arg_20]
0x180014ef8  mov     edi, edx
0x180014efa  mov     rdx, rcx
0x180014efd  mov     r13d, r8d
0x180014f00  mov     r15, rcx
0x180014f03  mov     r8d, ebx
0x180014f06  lea     rcx, [rsp+88h+var_58]
0x180014f0b  call    wil_details_FeatureReporting_RecordUsageInCache
0x180014f10  mov     esi, 1
0x180014f15  mov     ecx, [rax+8]
0x180014f18  mov     r12d, [rax]
0x180014f1b  mov     r14d, [rax+4]
0x180014f1f  mov     ebp, [rax+10h]
0x180014f22  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180014f29  mov     [rsp+88h+arg_10], ecx
0x180014f30  test    rax, rax
0x180014f33  jz      short loc_180014F4D
0x180014f35  test    ebx, ebx
0x180014f37  jz      short loc_180014F41
0x180014f39  lea     ecx, [rbx-64h]
0x180014f3c  cmp     ecx, 31h ; '1'
0x180014f3f  ja      short loc_180014F4D
0x180014f41  mov     r8d, esi
0x180014f44  mov     edx, ebx
0x180014f46  mov     ecx, edi
0x180014f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f4d  test    r12d, r12d
0x180014f50  jz      short loc_180014F63
0x180014f52  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x180014f55  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180014f5c  mov     edx, edi; unsigned int
0x180014f5e  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180014f63  test    r14d, r14d
0x180014f66  jz      short loc_180014F79
0x180014f68  mov     edx, [rsp+88h+arg_10]; unsigned int
0x180014f6f  mov     r8d, r14d; unsigned int
0x180014f72  mov     ecx, edi; this
0x180014f74  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180014f79  test    ebp, ebp
0x180014f7b  jnz     short loc_180014F90
0x180014f7d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x180014f84  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180014f8b  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x180014f90  test    r13d, r13d
0x180014f93  jz      short loc_180014FB0
0x180014f95  mov     edx, ebx
0x180014f97  mov     ecx, edi; this
0x180014f99  bts     edx, 1Fh
0x180014f9d  cmp     [rsp+88h+arg_18], 0
0x180014fa5  cmovz   edx, ebx; unsigned int
0x180014fa8  xor     r8d, r8d; unsigned int
0x180014fab  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180014fb0  test    ebp, ebp
0x180014fb2  jnz     short loc_180014FD3
0x180014fb4  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180014fbb  test    rax, rax
0x180014fbe  jz      short loc_180014FD5
0x180014fc0  mov     r8b, [rsp+88h+arg_38]
0x180014fc8  mov     edx, ebx
0x180014fca  mov     ecx, edi
0x180014fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fd1  jmp     short loc_180014FD5
0x180014fd3  xor     esi, esi
0x180014fd5  mov     rbx, [rsp+88h+arg_0]
0x180014fdd  mov     eax, esi
0x180014fdf  add     rsp, 50h
0x180014fe3  pop     r15
0x180014fe5  pop     r14
0x180014fe7  pop     r13
0x180014fe9  pop     r12
0x180014feb  pop     rdi
0x180014fec  pop     rsi
0x180014fed  pop     rbp
0x180014fee  retn
```
