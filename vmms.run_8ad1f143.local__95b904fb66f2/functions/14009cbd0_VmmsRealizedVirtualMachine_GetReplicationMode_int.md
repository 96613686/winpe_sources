# VmmsRealizedVirtualMachine::GetReplicationMode(int *)

- ea: `0x14009cbd0`
- end: `0x14009ce84`
- name: `?GetReplicationMode@VmmsRealizedVirtualMachine@@UEBA?AW4WMI_FAILOVER_REPLICATION_MODE@@PEAH@Z`
- size: `692`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x14004f3c4`
- `0x14005c630`
- `0x14009cbd0`
- `0x14009d144`
- `0x14009d170`
- `0x140228fa4`
- `0x1402407a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009cc0a`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009cc6b`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009ccc0`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009cd9f`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009cc0a`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009cc6b`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009ccc0`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009cd9f`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009cbf0`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009cc58`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009ccad`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009ccd7`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009cd02`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009cd30`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009cbf0`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009cc58`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009ccad`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009ccd7`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009cd02`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009cd30`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14009cde2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14009cde2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14009cc49`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14009cc49`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14009cc2b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14009cc87`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14009cd7d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14009cc2b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14009cc87`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14009cd7d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14009cc9e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14009cdd3`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14009cc9e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14009cdd3`

## pseudocode

```c
__int64 __fastcall VmmsRealizedVirtualMachine::GetReplicationMode(__int64 a1, int *a2)
{
  __int64 v2; // rbx
  __int64 v4; // rax
  DWORD v5; // ecx
  const char *v6; // r9
  __int64 v7; // rax
  DWORD v8; // edi
  unsigned __int64 Value; // r12
  __int64 v10; // rax
  __int64 v11; // rax
  char v12; // al
  DWORD v13; // ecx
  __int64 v14; // rax
  char v15; // al
  __int64 v16; // rax
  char v17; // al
  const char *v18; // r9
  unsigned int ReplicationModeInternal; // esi
  int v20; // ebp
  unsigned int v21; // eax
  __int64 v23; // r8
  __int64 v24; // r9
  int v25; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = a1 + 96;
  v4 = __RTtypeid(a1 + 96);
  if ( (unsigned int)__std_type_info_compare(v4 + 8, &qword_140C752B0) )
  {
    v16 = __RTtypeid(v2);
    v17 = type_info::operator==(v16, &ExtendedReplicationTracker `RTTI Type Descriptor');
    v5 = SharedReplicationTracker::gm_SrTlsIndex;
    if ( v17 )
      v5 = ExtendedReplicationTracker::gm_ErTlsIndex;
  }
  else
  {
    v5 = FailoverReplicationTracker::gm_FrTlsIndex;
  }
  if ( ((unsigned __int8)TlsGetValue(v5) & 1) != 0 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x9E1,
      (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationtrackerstatemachinetable.cpp",
      v6);
  AcquireSRWLockShared((PSRWLOCK)(v2 + 4984));
  v7 = __RTtypeid(v2);
  if ( (unsigned int)__std_type_info_compare(v7 + 8, &qword_140C752B0) )
  {
    v14 = __RTtypeid(v2);
    v15 = type_info::operator==(v14, &ExtendedReplicationTracker `RTTI Type Descriptor');
    v8 = SharedReplicationTracker::gm_SrTlsIndex;
    if ( v15 )
      v8 = ExtendedReplicationTracker::gm_ErTlsIndex;
  }
  else
  {
    v8 = FailoverReplicationTracker::gm_FrTlsIndex;
  }
  Value = (unsigned int)TlsGetValue(v8);
  TlsSetValue(v8, (LPVOID)(Value | 4));
  v10 = __RTtypeid(v2);
  if ( (unsigned int)__std_type_info_compare(v10 + 8, &qword_140C752B0) )
  {
    v11 = __RTtypeid(v2);
    v12 = type_info::operator==(v11, &ExtendedReplicationTracker `RTTI Type Descriptor');
    v13 = SharedReplicationTracker::gm_SrTlsIndex;
    if ( v12 )
      v13 = ExtendedReplicationTracker::gm_ErTlsIndex;
  }
  else
  {
    v13 = FailoverReplicationTracker::gm_FrTlsIndex;
  }
  if ( ((unsigned __int8)TlsGetValue(v13) & 5) == 0 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x21F,
      (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\FailoverReplicationTrackerInternal.h",
      v18);
  ReplicationModeInternal = 0;
  v20 = 0;
  if ( !(unsigned int)__std_type_info_compare(&qword_140C751D8, &qword_140C751D8) )
  {
    v21 = *(_DWORD *)(v2 + 5784);
    goto LABEL_21;
  }
  if ( (unsigned __int8)type_info::operator==(
                          &enum FailoverReplicationTracker::FrOperationalFlags `RTTI Type Descriptor',
                          &enum FailoverReplicationTracker::NetworkOperationalFlags `RTTI Type Descriptor') )
  {
    v21 = *(_DWORD *)(v2 + 5788);
LABEL_21:
    if ( ((v21 >> 2) & 1) != 0 )
    {
      v20 = 1;
      ReplicationModeInternal = FailoverReplicationTracker::GetReplicationModeInternal(v2);
    }
    goto LABEL_23;
  }
  wil::details::in1diag3::Log_Hr(
    retaddr,
    (void *)0x22B,
    (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\FailoverReplicationTrackerInternal.h",
    (const char *)0x8000FFFFLL,
    v25);
  if ( (unsigned int)VmlIsDebugTraceEnabled(0) )
    VmlDebugTraceEx(
      0,
      &`FailoverReplicationTracker::TestOperationalFlag<enum FailoverReplicationTracker::FrOperationalFlags>'::`16'::traceParameters,
      v23,
      v24);
LABEL_23:
  TlsSetValue(v8, (LPVOID)Value);
  ReleaseSRWLockShared((PSRWLOCK)(v2 + 4984));
  if ( a2 )
    *a2 = v20;
  return ReplicationModeInternal;
}

```

## disassembly

```asm
0x14009cbd0  mov     [rsp+arg_10], rbx
0x14009cbd5  mov     [rsp+arg_18], rbp
0x14009cbda  push    rsi
0x14009cbdb  push    rdi
0x14009cbdc  push    r12
0x14009cbde  push    r14
0x14009cbe0  push    r15; int
0x14009cbe2  sub     rsp, 20h
0x14009cbe6  lea     rbx, [rcx+60h]
0x14009cbea  mov     r14, rdx
0x14009cbed  mov     rcx, rbx
0x14009cbf0  call    cs:__imp___RTtypeid
0x14009cbf7  nop     dword ptr [rax+rax+00h]
0x14009cbfc  lea     rbp, qword_140C752B0
0x14009cc03  mov     rdx, rbp
0x14009cc06  lea     rcx, [rax+8]
0x14009cc0a  call    cs:__imp___std_type_info_compare
0x14009cc11  nop     dword ptr [rax+rax+00h]
0x14009cc16  lea     rsi, ??_R0?AVExtendedReplicationTracker@@@8; ExtendedReplicationTracker `RTTI Type Descriptor'
0x14009cc1d  test    eax, eax
0x14009cc1f  jnz     loc_14009CD2D
0x14009cc25  mov     ecx, cs:?gm_FrTlsIndex@FailoverReplicationTracker@@0KA; dwTlsIndex
0x14009cc2b  call    cs:__imp_TlsGetValue
0x14009cc32  nop     dword ptr [rax+rax+00h]
0x14009cc37  test    al, 1
0x14009cc39  jnz     loc_14009CD5B
0x14009cc3f  lea     r15, [rbx+1378h]
0x14009cc46  mov     rcx, r15; SRWLock
0x14009cc49  call    cs:__imp_AcquireSRWLockShared
0x14009cc50  nop     dword ptr [rax+rax+00h]
0x14009cc55  mov     rcx, rbx
0x14009cc58  call    cs:__imp___RTtypeid
0x14009cc5f  nop     dword ptr [rax+rax+00h]
0x14009cc64  mov     rdx, rbp
0x14009cc67  lea     rcx, [rax+8]
0x14009cc6b  call    cs:__imp___std_type_info_compare
0x14009cc72  nop     dword ptr [rax+rax+00h]
0x14009cc77  test    eax, eax
0x14009cc79  jnz     loc_14009CCFF
0x14009cc7f  mov     edi, cs:?gm_FrTlsIndex@FailoverReplicationTracker@@0KA; ulong FailoverReplicationTracker::gm_FrTlsIndex
0x14009cc85  mov     ecx, edi; dwTlsIndex
0x14009cc87  call    cs:__imp_TlsGetValue
0x14009cc8e  nop     dword ptr [rax+rax+00h]
0x14009cc93  mov     edx, eax
0x14009cc95  mov     ecx, edi; dwTlsIndex
0x14009cc97  or      rdx, 4; lpTlsValue
0x14009cc9b  mov     r12d, eax
0x14009cc9e  call    cs:__imp_TlsSetValue
0x14009cca5  nop     dword ptr [rax+rax+00h]
0x14009ccaa  mov     rcx, rbx
0x14009ccad  call    cs:__imp___RTtypeid
0x14009ccb4  nop     dword ptr [rax+rax+00h]
0x14009ccb9  mov     rdx, rbp
0x14009ccbc  lea     rcx, [rax+8]
0x14009ccc0  call    cs:__imp___std_type_info_compare
0x14009ccc7  nop     dword ptr [rax+rax+00h]
0x14009cccc  test    eax, eax
0x14009ccce  jz      loc_14009CD72
0x14009ccd4  mov     rcx, rbx
0x14009ccd7  call    cs:__imp___RTtypeid
0x14009ccde  nop     dword ptr [rax+rax+00h]
0x14009cce3  mov     rcx, rax
0x14009cce6  mov     rdx, rsi
0x14009cce9  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x14009ccee  mov     ecx, cs:?gm_SrTlsIndex@SharedReplicationTracker@@0KA; ulong SharedReplicationTracker::gm_SrTlsIndex
0x14009ccf4  test    al, al
0x14009ccf6  cmovnz  ecx, cs:?gm_ErTlsIndex@ExtendedReplicationTracker@@0KA; ulong ExtendedReplicationTracker::gm_ErTlsIndex
0x14009ccfd  jmp     short loc_14009CD78
0x14009ccff  mov     rcx, rbx
0x14009cd02  call    cs:__imp___RTtypeid
0x14009cd09  nop     dword ptr [rax+rax+00h]
0x14009cd0e  mov     rcx, rax
0x14009cd11  mov     rdx, rsi
0x14009cd14  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x14009cd19  mov     edi, cs:?gm_SrTlsIndex@SharedReplicationTracker@@0KA; ulong SharedReplicationTracker::gm_SrTlsIndex
0x14009cd1f  test    al, al
0x14009cd21  cmovnz  edi, cs:?gm_ErTlsIndex@ExtendedReplicationTracker@@0KA; ulong ExtendedReplicationTracker::gm_ErTlsIndex
0x14009cd28  jmp     loc_14009CC85
0x14009cd2d  mov     rcx, rbx
0x14009cd30  call    cs:__imp___RTtypeid
0x14009cd37  nop     dword ptr [rax+rax+00h]
0x14009cd3c  mov     rcx, rax
0x14009cd3f  mov     rdx, rsi
0x14009cd42  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x14009cd47  mov     ecx, cs:?gm_SrTlsIndex@SharedReplicationTracker@@0KA; ulong SharedReplicationTracker::gm_SrTlsIndex
0x14009cd4d  test    al, al
0x14009cd4f  cmovnz  ecx, cs:?gm_ErTlsIndex@ExtendedReplicationTracker@@0KA; ulong ExtendedReplicationTracker::gm_ErTlsIndex
0x14009cd56  jmp     loc_14009CC2B
0x14009cd5b  mov     rcx, [rsp+48h]; this
0x14009cd60  lea     r8, aOnecoreVmVmmsF_26; "onecore\\vm\\vmms\\fr\\lib\\failoverrep"...
0x14009cd67  mov     edx, 9E1h; void *
0x14009cd6c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14009cd72  mov     ecx, cs:?gm_FrTlsIndex@FailoverReplicationTracker@@0KA; dwTlsIndex
0x14009cd78  mov     rsi, [rsp+48h]
0x14009cd7d  call    cs:__imp_TlsGetValue
0x14009cd84  nop     dword ptr [rax+rax+00h]
0x14009cd89  test    al, 5
0x14009cd8b  jz      loc_14009CE6F
0x14009cd91  lea     rcx, qword_140C751D8
0x14009cd98  xor     esi, esi
0x14009cd9a  mov     rdx, rcx
0x14009cd9d  xor     ebp, ebp
0x14009cd9f  call    cs:__imp___std_type_info_compare
0x14009cda6  nop     dword ptr [rax+rax+00h]
0x14009cdab  test    eax, eax
0x14009cdad  jnz     short loc_14009CE0D
0x14009cdaf  mov     eax, [rbx+1698h]
0x14009cdb5  shr     eax, 2
0x14009cdb8  and     eax, 1
0x14009cdbb  test    eax, eax
0x14009cdbd  jz      short loc_14009CDCE
0x14009cdbf  mov     rcx, rbx
0x14009cdc2  mov     ebp, 1
0x14009cdc7  call    ?GetReplicationModeInternal@FailoverReplicationTracker@@AEBA?AW4WMI_FAILOVER_REPLICATION_MODE@@XZ; FailoverReplicationTracker::GetReplicationModeInternal(void)
0x14009cdcc  mov     esi, eax
0x14009cdce  mov     rdx, r12; lpTlsValue
0x14009cdd1  mov     ecx, edi; dwTlsIndex
0x14009cdd3  call    cs:__imp_TlsSetValue
0x14009cdda  nop     dword ptr [rax+rax+00h]
0x14009cddf  mov     rcx, r15; SRWLock
0x14009cde2  call    cs:__imp_ReleaseSRWLockShared
0x14009cde9  nop     dword ptr [rax+rax+00h]
0x14009cdee  test    r14, r14
0x14009cdf1  jnz     short loc_14009CE6A
0x14009cdf3  mov     rbx, [rsp+48h+arg_10]
0x14009cdf8  mov     eax, esi
0x14009cdfa  mov     rbp, [rsp+48h+arg_18]
0x14009cdff  add     rsp, 20h
0x14009ce03  pop     r15
0x14009ce05  pop     r14
0x14009ce07  pop     r12
0x14009ce09  pop     rdi
0x14009ce0a  pop     rsi
0x14009ce0b  retn
0x14009ce0d  lea     rdx, ??_R0?AW4NetworkOperationalFlags@FailoverReplicationTracker@@@8; FailoverReplicationTracker::NetworkOperationalFlags `RTTI Type Descriptor'
0x14009ce14  lea     rcx, ??_R0?AW4FrOperationalFlags@FailoverReplicationTracker@@@8; FailoverReplicationTracker::FrOperationalFlags `RTTI Type Descriptor'
0x14009ce1b  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x14009ce20  test    al, al
0x14009ce22  jz      short loc_14009CE2C
0x14009ce24  mov     eax, [rbx+169Ch]
0x14009ce2a  jmp     short loc_14009CDB5
0x14009ce2c  mov     rcx, [rsp+48h]; this
0x14009ce31  lea     r8, aOnecoreVmVmmsF_34; "onecore\\vm\\vmms\\fr\\lib\\FailoverRep"...
0x14009ce38  mov     r9d, 8000FFFFh; char *
0x14009ce3e  mov     edx, 22Bh; void *
0x14009ce43  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x14009ce48  xor     ecx, ecx
0x14009ce4a  call    VmlIsDebugTraceEnabled
0x14009ce4f  test    eax, eax
0x14009ce51  jz      loc_14009CDCE
0x14009ce57  lea     rdx, ?traceParameters@?BA@???$TestOperationalFlag@W4FrOperationalFlags@FailoverReplicationTracker@@@FailoverReplicationTracker@@IEBAHW4FrOperationalFlags@1@@Z@4UVmlDebugTraceParameters@@B; VmlDebugTraceParameters const `FailoverReplicationTracker::TestOperationalFlag<FailoverReplicationTracker::FrOperationalFlags>(FailoverReplicationTracker::FrOperationalFlags)'::`16'::traceParameters
0x14009ce5e  xor     ecx, ecx
0x14009ce60  call    VmlDebugTraceEx
0x14009ce65  jmp     loc_14009CDCE
0x14009ce6a  mov     [r14], ebp
0x14009ce6d  jmp     short loc_14009CDF3
0x14009ce6f  lea     r8, aOnecoreVmVmmsF_34; "onecore\\vm\\vmms\\fr\\lib\\FailoverRep"...
0x14009ce76  mov     edx, 21Fh; void *
0x14009ce7b  mov     rcx, rsi; this
0x14009ce7e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
