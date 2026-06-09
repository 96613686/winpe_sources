# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18003a450`
- end: `0x18003a508`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `184`
- prototype: `int __high(struct wil_details_FeatureReportingCache *, unsigned int, int, int, enum wil_details_ServiceReportingKind, unsigned int, unsigned __int64, unsigned __int8)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18003a328`

## callees

- `0x180039884`
- `0x18003a450`
- `0x18003bc6c`
- `0x18003c508`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        __int64 a1,
        unsigned int a2,
        int a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        char a8)
{
  __int64 v12; // rax
  __int64 v13; // xmm0_8
  __int64 v14; // r8
  __int64 v15; // r8
  unsigned int v16; // r9d
  unsigned int v17; // edx
  char *v19; // [rsp+20h] [rbp-68h]
  char v20[16]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v21; // [rsp+40h] [rbp-48h]
  _BYTE v22[64]; // [rsp+48h] [rbp-40h] BYREF

  v12 = wil_details_FeatureReporting_RecordUsageInCache(v22, a1, a5);
  v13 = *(_QWORD *)(v12 + 16);
  *(_OWORD *)v20 = *(_OWORD *)v12;
  v21 = v13;
  wil::details::RecordFeatureUsageCallback((wil *)a2, a5, v14, a1, v20);
  if ( a3 )
  {
    v17 = a5 | 0x80000000;
    if ( !a4 )
      v17 = a5;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v17, 0, v16, v19);
  }
  if ( (_DWORD)v21 )
    return 0;
  if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v15) = a8;
    g_wil_details_realtimeFeatureUsageHook(a2, a5, v15);
  }
  return 1;
}

```

## disassembly

```asm
0x18003a450  push    rbx
0x18003a452  push    rbp
0x18003a453  push    rdi
0x18003a454  push    r14
0x18003a456  sub     rsp, 68h
0x18003a45a  mov     ebp, edx
0x18003a45c  mov     edi, r8d
0x18003a45f  mov     r8d, [rsp+88h+arg_20]
0x18003a467  mov     rdx, rcx
0x18003a46a  mov     rbx, rcx
0x18003a46d  mov     r14d, r9d
0x18003a470  lea     rcx, [rsp+88h+var_40]
0x18003a475  call    wil_details_FeatureReporting_RecordUsageInCache
0x18003a47a  mov     edx, [rsp+88h+arg_20]
0x18003a481  mov     r9, rbx
0x18003a484  mov     ecx, ebp
0x18003a486  movups  xmm1, xmmword ptr [rax]
0x18003a489  movsd   xmm0, qword ptr [rax+10h]
0x18003a48e  lea     rax, [rsp+88h+var_58]
0x18003a493  movups  xmmword ptr [rsp+88h+var_58], xmm1
0x18003a498  mov     [rsp+88h+var_68], rax; char *
0x18003a49d  movsd   [rsp+88h+var_48], xmm0
0x18003a4a3  call    ?RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z; wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)
0x18003a4a8  test    edi, edi
0x18003a4aa  jz      short loc_18003A4CC
0x18003a4ac  mov     edx, [rsp+88h+arg_20]
0x18003a4b3  mov     ecx, ebp; this
0x18003a4b5  bts     edx, 1Fh
0x18003a4b9  test    r14d, r14d
0x18003a4bc  cmovz   edx, [rsp+88h+arg_20]; unsigned int
0x18003a4c4  xor     r8d, r8d; unsigned int
0x18003a4c7  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18003a4cc  cmp     dword ptr [rsp+88h+var_48], 0
0x18003a4d1  jnz     short loc_18003A4FC
0x18003a4d3  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18003a4da  test    rax, rax
0x18003a4dd  jz      short loc_18003A4F5
0x18003a4df  mov     r8b, [rsp+88h+arg_38]
0x18003a4e7  mov     ecx, ebp
0x18003a4e9  mov     edx, [rsp+88h+arg_20]
0x18003a4f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a4f5  mov     eax, 1
0x18003a4fa  jmp     short loc_18003A4FE
0x18003a4fc  xor     eax, eax
0x18003a4fe  add     rsp, 68h
0x18003a502  pop     r14
0x18003a504  pop     rdi
0x18003a505  pop     rbp
0x18003a506  pop     rbx
0x18003a507  retn
```
