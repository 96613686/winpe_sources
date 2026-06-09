# FailoverReplicationTracker::GetReplicationMode(int *)

- ea: `0x14009ce8c`
- end: `0x14009d13c`
- name: `?GetReplicationMode@FailoverReplicationTracker@@QEBA?AW4WMI_FAILOVER_REPLICATION_MODE@@PEAH@Z`
- size: `688`
- prototype: ``
- caller_count: `9`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1401e1260`
- `0x14036e670`
- `0x14044d1a0`
- `0x1404f8dc8`
- `0x1405197c8`
- `0x140545208`
- `0x140665ef0`
- `0x14066b780`
- `0x14066d7f0`

## callees

- `0x14004f3c4`
- `0x14005c630`
- `0x14009ce8c`
- `0x14009d144`
- `0x14009d170`
- `0x140228fa4`
- `0x1402407a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009cec2`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009cf23`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009cf78`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009d057`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009cec2`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009cf23`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009cf78`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009d057`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009cea8`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009cf10`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009cf65`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009cf8f`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009cfba`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009cfe8`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009cea8`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009cf10`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009cf65`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009cf8f`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009cfba`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009cfe8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14009d09a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14009d09a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14009cf01`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14009cf01`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14009cee3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14009cf3f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14009d035`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14009cee3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14009cf3f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14009d035`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14009cf56`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14009d08b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14009cf56`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14009d08b`

## pseudocode

```c
__int64 __fastcall FailoverReplicationTracker::GetReplicationMode(__int64 a1, int *a2)
{
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

  v4 = __RTtypeid(a1);
  if ( (unsigned int)__std_type_info_compare(v4 + 8, &qword_140C752B0) )
  {
    v16 = __RTtypeid(a1);
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
  AcquireSRWLockShared((PSRWLOCK)(a1 + 4984));
  v7 = __RTtypeid(a1);
  if ( (unsigned int)__std_type_info_compare(v7 + 8, &qword_140C752B0) )
  {
    v14 = __RTtypeid(a1);
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
  v10 = __RTtypeid(a1);
  if ( (unsigned int)__std_type_info_compare(v10 + 8, &qword_140C752B0) )
  {
    v11 = __RTtypeid(a1);
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
    v21 = *(_DWORD *)(a1 + 5784);
    goto LABEL_21;
  }
  if ( (unsigned __int8)type_info::operator==(
                          &enum FailoverReplicationTracker::FrOperationalFlags `RTTI Type Descriptor',
                          &enum FailoverReplicationTracker::NetworkOperationalFlags `RTTI Type Descriptor') )
  {
    v21 = *(_DWORD *)(a1 + 5788);
LABEL_21:
    if ( ((v21 >> 2) & 1) != 0 )
    {
      v20 = 1;
      ReplicationModeInternal = FailoverReplicationTracker::GetReplicationModeInternal(a1);
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
  ReleaseSRWLockShared((PSRWLOCK)(a1 + 4984));
  if ( a2 )
    *a2 = v20;
  return ReplicationModeInternal;
}

```

## disassembly

```asm
0x14009ce8c  mov     [rsp+arg_10], rbx
0x14009ce91  mov     [rsp+arg_18], rbp
0x14009ce96  push    rsi
0x14009ce97  push    rdi
0x14009ce98  push    r12
0x14009ce9a  push    r14
0x14009ce9c  push    r15; int
0x14009ce9e  sub     rsp, 20h
0x14009cea2  mov     r14, rdx
0x14009cea5  mov     rbx, rcx
0x14009cea8  call    cs:__imp___RTtypeid
0x14009ceaf  nop     dword ptr [rax+rax+00h]
0x14009ceb4  lea     rbp, qword_140C752B0
0x14009cebb  mov     rdx, rbp
0x14009cebe  lea     rcx, [rax+8]
0x14009cec2  call    cs:__imp___std_type_info_compare
0x14009cec9  nop     dword ptr [rax+rax+00h]
0x14009cece  lea     rsi, ??_R0?AVExtendedReplicationTracker@@@8; ExtendedReplicationTracker `RTTI Type Descriptor'
0x14009ced5  test    eax, eax
0x14009ced7  jnz     loc_14009CFE5
0x14009cedd  mov     ecx, cs:?gm_FrTlsIndex@FailoverReplicationTracker@@0KA; dwTlsIndex
0x14009cee3  call    cs:__imp_TlsGetValue
0x14009ceea  nop     dword ptr [rax+rax+00h]
0x14009ceef  test    al, 1
0x14009cef1  jnz     loc_14009D013
0x14009cef7  lea     r15, [rbx+1378h]
0x14009cefe  mov     rcx, r15; SRWLock
0x14009cf01  call    cs:__imp_AcquireSRWLockShared
0x14009cf08  nop     dword ptr [rax+rax+00h]
0x14009cf0d  mov     rcx, rbx
0x14009cf10  call    cs:__imp___RTtypeid
0x14009cf17  nop     dword ptr [rax+rax+00h]
0x14009cf1c  mov     rdx, rbp
0x14009cf1f  lea     rcx, [rax+8]
0x14009cf23  call    cs:__imp___std_type_info_compare
0x14009cf2a  nop     dword ptr [rax+rax+00h]
0x14009cf2f  test    eax, eax
0x14009cf31  jnz     loc_14009CFB7
0x14009cf37  mov     edi, cs:?gm_FrTlsIndex@FailoverReplicationTracker@@0KA; ulong FailoverReplicationTracker::gm_FrTlsIndex
0x14009cf3d  mov     ecx, edi; dwTlsIndex
0x14009cf3f  call    cs:__imp_TlsGetValue
0x14009cf46  nop     dword ptr [rax+rax+00h]
0x14009cf4b  mov     edx, eax
0x14009cf4d  mov     ecx, edi; dwTlsIndex
0x14009cf4f  or      rdx, 4; lpTlsValue
0x14009cf53  mov     r12d, eax
0x14009cf56  call    cs:__imp_TlsSetValue
0x14009cf5d  nop     dword ptr [rax+rax+00h]
0x14009cf62  mov     rcx, rbx
0x14009cf65  call    cs:__imp___RTtypeid
0x14009cf6c  nop     dword ptr [rax+rax+00h]
0x14009cf71  mov     rdx, rbp
0x14009cf74  lea     rcx, [rax+8]
0x14009cf78  call    cs:__imp___std_type_info_compare
0x14009cf7f  nop     dword ptr [rax+rax+00h]
0x14009cf84  test    eax, eax
0x14009cf86  jz      loc_14009D02A
0x14009cf8c  mov     rcx, rbx
0x14009cf8f  call    cs:__imp___RTtypeid
0x14009cf96  nop     dword ptr [rax+rax+00h]
0x14009cf9b  mov     rcx, rax
0x14009cf9e  mov     rdx, rsi
0x14009cfa1  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x14009cfa6  mov     ecx, cs:?gm_SrTlsIndex@SharedReplicationTracker@@0KA; ulong SharedReplicationTracker::gm_SrTlsIndex
0x14009cfac  test    al, al
0x14009cfae  cmovnz  ecx, cs:?gm_ErTlsIndex@ExtendedReplicationTracker@@0KA; ulong ExtendedReplicationTracker::gm_ErTlsIndex
0x14009cfb5  jmp     short loc_14009D030
0x14009cfb7  mov     rcx, rbx
0x14009cfba  call    cs:__imp___RTtypeid
0x14009cfc1  nop     dword ptr [rax+rax+00h]
0x14009cfc6  mov     rcx, rax
0x14009cfc9  mov     rdx, rsi
0x14009cfcc  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x14009cfd1  mov     edi, cs:?gm_SrTlsIndex@SharedReplicationTracker@@0KA; ulong SharedReplicationTracker::gm_SrTlsIndex
0x14009cfd7  test    al, al
0x14009cfd9  cmovnz  edi, cs:?gm_ErTlsIndex@ExtendedReplicationTracker@@0KA; ulong ExtendedReplicationTracker::gm_ErTlsIndex
0x14009cfe0  jmp     loc_14009CF3D
0x14009cfe5  mov     rcx, rbx
0x14009cfe8  call    cs:__imp___RTtypeid
0x14009cfef  nop     dword ptr [rax+rax+00h]
0x14009cff4  mov     rcx, rax
0x14009cff7  mov     rdx, rsi
0x14009cffa  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x14009cfff  mov     ecx, cs:?gm_SrTlsIndex@SharedReplicationTracker@@0KA; ulong SharedReplicationTracker::gm_SrTlsIndex
0x14009d005  test    al, al
0x14009d007  cmovnz  ecx, cs:?gm_ErTlsIndex@ExtendedReplicationTracker@@0KA; ulong ExtendedReplicationTracker::gm_ErTlsIndex
0x14009d00e  jmp     loc_14009CEE3
0x14009d013  mov     rcx, [rsp+48h]; this
0x14009d018  lea     r8, aOnecoreVmVmmsF_26; "onecore\\vm\\vmms\\fr\\lib\\failoverrep"...
0x14009d01f  mov     edx, 9E1h; void *
0x14009d024  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14009d02a  mov     ecx, cs:?gm_FrTlsIndex@FailoverReplicationTracker@@0KA; dwTlsIndex
0x14009d030  mov     rsi, [rsp+48h]
0x14009d035  call    cs:__imp_TlsGetValue
0x14009d03c  nop     dword ptr [rax+rax+00h]
0x14009d041  test    al, 5
0x14009d043  jz      loc_14009D127
0x14009d049  lea     rcx, qword_140C751D8
0x14009d050  xor     esi, esi
0x14009d052  mov     rdx, rcx
0x14009d055  xor     ebp, ebp
0x14009d057  call    cs:__imp___std_type_info_compare
0x14009d05e  nop     dword ptr [rax+rax+00h]
0x14009d063  test    eax, eax
0x14009d065  jnz     short loc_14009D0C5
0x14009d067  mov     eax, [rbx+1698h]
0x14009d06d  shr     eax, 2
0x14009d070  and     eax, 1
0x14009d073  test    eax, eax
0x14009d075  jz      short loc_14009D086
0x14009d077  mov     rcx, rbx
0x14009d07a  mov     ebp, 1
0x14009d07f  call    ?GetReplicationModeInternal@FailoverReplicationTracker@@AEBA?AW4WMI_FAILOVER_REPLICATION_MODE@@XZ; FailoverReplicationTracker::GetReplicationModeInternal(void)
0x14009d084  mov     esi, eax
0x14009d086  mov     rdx, r12; lpTlsValue
0x14009d089  mov     ecx, edi; dwTlsIndex
0x14009d08b  call    cs:__imp_TlsSetValue
0x14009d092  nop     dword ptr [rax+rax+00h]
0x14009d097  mov     rcx, r15; SRWLock
0x14009d09a  call    cs:__imp_ReleaseSRWLockShared
0x14009d0a1  nop     dword ptr [rax+rax+00h]
0x14009d0a6  test    r14, r14
0x14009d0a9  jnz     short loc_14009D122
0x14009d0ab  mov     rbx, [rsp+48h+arg_10]
0x14009d0b0  mov     eax, esi
0x14009d0b2  mov     rbp, [rsp+48h+arg_18]
0x14009d0b7  add     rsp, 20h
0x14009d0bb  pop     r15
0x14009d0bd  pop     r14
0x14009d0bf  pop     r12
0x14009d0c1  pop     rdi
0x14009d0c2  pop     rsi
0x14009d0c3  retn
0x14009d0c5  lea     rdx, ??_R0?AW4NetworkOperationalFlags@FailoverReplicationTracker@@@8; FailoverReplicationTracker::NetworkOperationalFlags `RTTI Type Descriptor'
0x14009d0cc  lea     rcx, ??_R0?AW4FrOperationalFlags@FailoverReplicationTracker@@@8; FailoverReplicationTracker::FrOperationalFlags `RTTI Type Descriptor'
0x14009d0d3  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x14009d0d8  test    al, al
0x14009d0da  jz      short loc_14009D0E4
0x14009d0dc  mov     eax, [rbx+169Ch]
0x14009d0e2  jmp     short loc_14009D06D
0x14009d0e4  mov     rcx, [rsp+48h]; this
0x14009d0e9  lea     r8, aOnecoreVmVmmsF_34; "onecore\\vm\\vmms\\fr\\lib\\FailoverRep"...
0x14009d0f0  mov     r9d, 8000FFFFh; char *
0x14009d0f6  mov     edx, 22Bh; void *
0x14009d0fb  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x14009d100  xor     ecx, ecx
0x14009d102  call    VmlIsDebugTraceEnabled
0x14009d107  test    eax, eax
0x14009d109  jz      loc_14009D086
0x14009d10f  lea     rdx, ?traceParameters@?BA@???$TestOperationalFlag@W4FrOperationalFlags@FailoverReplicationTracker@@@FailoverReplicationTracker@@IEBAHW4FrOperationalFlags@1@@Z@4UVmlDebugTraceParameters@@B; VmlDebugTraceParameters const `FailoverReplicationTracker::TestOperationalFlag<FailoverReplicationTracker::FrOperationalFlags>(FailoverReplicationTracker::FrOperationalFlags)'::`16'::traceParameters
0x14009d116  xor     ecx, ecx
0x14009d118  call    VmlDebugTraceEx
0x14009d11d  jmp     loc_14009D086
0x14009d122  mov     [r14], ebp
0x14009d125  jmp     short loc_14009D0AB
0x14009d127  lea     r8, aOnecoreVmVmmsF_34; "onecore\\vm\\vmms\\fr\\lib\\FailoverRep"...
0x14009d12e  mov     edx, 21Fh; void *
0x14009d133  mov     rcx, rsi; this
0x14009d136  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
