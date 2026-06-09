# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180018854`
- end: `0x18001896c`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800187b0`

## callees

- `0x1800164a4`
- `0x180017ac0`
- `0x180018854`
- `0x180019074`
- `0x180019efc`
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
0x180018854  mov     [rsp+arg_0], rbx
0x180018859  mov     [rsp+arg_18], r9d
0x18001885e  push    rbp
0x18001885f  push    rsi
0x180018860  push    rdi
0x180018861  push    r12
0x180018863  push    r13
0x180018865  push    r14
0x180018867  push    r15
0x180018869  sub     rsp, 50h
0x18001886d  mov     ebx, [rsp+88h+arg_20]
0x180018874  mov     edi, edx
0x180018876  mov     rdx, rcx
0x180018879  mov     r13d, r8d
0x18001887c  mov     r15, rcx
0x18001887f  mov     r8d, ebx
0x180018882  lea     rcx, [rsp+88h+var_58]
0x180018887  call    wil_details_FeatureReporting_RecordUsageInCache
0x18001888c  mov     esi, 1
0x180018891  mov     ecx, [rax+8]
0x180018894  mov     r12d, [rax]
0x180018897  mov     r14d, [rax+4]
0x18001889b  mov     ebp, [rax+10h]
0x18001889e  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x1800188a5  mov     [rsp+88h+arg_10], ecx
0x1800188ac  test    rax, rax
0x1800188af  jz      short loc_1800188C9
0x1800188b1  test    ebx, ebx
0x1800188b3  jz      short loc_1800188BD
0x1800188b5  lea     ecx, [rbx-64h]
0x1800188b8  cmp     ecx, 31h ; '1'
0x1800188bb  ja      short loc_1800188C9
0x1800188bd  mov     r8d, esi
0x1800188c0  mov     edx, ebx
0x1800188c2  mov     ecx, edi
0x1800188c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188c9  test    r12d, r12d
0x1800188cc  jz      short loc_1800188DF
0x1800188ce  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x1800188d1  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1800188d8  mov     edx, edi; unsigned int
0x1800188da  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x1800188df  test    r14d, r14d
0x1800188e2  jz      short loc_1800188F5
0x1800188e4  mov     edx, [rsp+88h+arg_10]; unsigned int
0x1800188eb  mov     r8d, r14d; unsigned int
0x1800188ee  mov     ecx, edi; this
0x1800188f0  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800188f5  test    ebp, ebp
0x1800188f7  jnz     short loc_18001890C
0x1800188f9  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x180018900  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180018907  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x18001890c  test    r13d, r13d
0x18001890f  jz      short loc_18001892C
0x180018911  mov     edx, ebx
0x180018913  mov     ecx, edi; this
0x180018915  bts     edx, 1Fh
0x180018919  cmp     [rsp+88h+arg_18], 0
0x180018921  cmovz   edx, ebx; unsigned int
0x180018924  xor     r8d, r8d; unsigned int
0x180018927  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18001892c  test    ebp, ebp
0x18001892e  jnz     short loc_18001894F
0x180018930  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180018937  test    rax, rax
0x18001893a  jz      short loc_180018951
0x18001893c  mov     r8b, [rsp+88h+arg_38]
0x180018944  mov     edx, ebx
0x180018946  mov     ecx, edi
0x180018948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001894d  jmp     short loc_180018951
0x18001894f  xor     esi, esi
0x180018951  mov     rbx, [rsp+88h+arg_0]
0x180018959  mov     eax, esi
0x18001895b  add     rsp, 50h
0x18001895f  pop     r15
0x180018961  pop     r14
0x180018963  pop     r13
0x180018965  pop     r12
0x180018967  pop     rdi
0x180018968  pop     rsi
0x180018969  pop     rbp
0x18001896a  retn
```
