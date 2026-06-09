# FailoverReplicationTracker::IsStartupBlocked(void)

- ea: `0x14009b6a0`
- end: `0x14009ba68`
- name: `?IsStartupBlocked@FailoverReplicationTracker@@QEBAHXZ`
- size: `968`
- prototype: `__int64 __fastcall(FailoverReplicationTracker *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14066bbe0`

## callees

- `0x14004f3c4`
- `0x14005c630`
- `0x14009b6a0`
- `0x14009d144`
- `0x140228fa4`
- `0x1402407a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009b6c7`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009b766`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009b7ec`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009b854`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009b8e8`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009b954`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009b6c7`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009b766`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009b7ec`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009b854`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009b8e8`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009b954`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009b6b0`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009b6e9`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009b74f`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009b781`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009b7d5`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009b807`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009b8d1`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009b903`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009b6b0`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009b6e9`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009b74f`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009b781`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009b7d5`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009b807`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009b8d1`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14009b903`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14009b9e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14009b9e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14009b740`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14009b740`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14009b70f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14009b7a9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14009b832`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14009b932`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14009b70f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14009b7a9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14009b832`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14009b932`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14009b7c0`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14009b9d6`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14009b7c0`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14009b9d6`

## pseudocode

```c
__int64 __fastcall FailoverReplicationTracker::IsStartupBlocked(RTL_SRWLOCK *this)
{
  __int64 v2; // rax
  DWORD v3; // ecx
  __int64 v4; // rax
  char v5; // al
  const char *v6; // r9
  __int64 v7; // rax
  DWORD v8; // ebp
  __int64 v9; // rax
  char v10; // al
  unsigned __int64 Value; // r15
  int Ptr_high; // ebx
  __int64 v13; // rax
  DWORD v14; // ecx
  __int64 v15; // rax
  char v16; // al
  const char *v17; // r9
  unsigned int v18; // eax
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rax
  DWORD v22; // ecx
  __int64 v23; // rax
  char v24; // al
  const char *v25; // r9
  unsigned int Ptr; // eax
  unsigned int v27; // esi
  __int64 v28; // r8
  __int64 v29; // r9
  RTL_SRWLOCK *v30; // rcx
  unsigned int v31; // edi
  int v32; // ebx
  int v33; // ebx
  int v35; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = __RTtypeid(this);
  if ( (unsigned int)__std_type_info_compare(v2 + 8, &qword_140C752B0) )
  {
    v4 = __RTtypeid(this);
    v5 = type_info::operator==(v4, &ExtendedReplicationTracker `RTTI Type Descriptor');
    v3 = SharedReplicationTracker::gm_SrTlsIndex;
    if ( v5 )
      v3 = ExtendedReplicationTracker::gm_ErTlsIndex;
  }
  else
  {
    v3 = FailoverReplicationTracker::gm_FrTlsIndex;
  }
  if ( ((unsigned __int8)TlsGetValue(v3) & 1) != 0 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xB75,
      (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationtrackerstatemachinetable.cpp",
      v6);
  AcquireSRWLockShared(this + 623);
  v7 = __RTtypeid(this);
  if ( (unsigned int)__std_type_info_compare(v7 + 8, &qword_140C752B0) )
  {
    v9 = __RTtypeid(this);
    v10 = type_info::operator==(v9, &ExtendedReplicationTracker `RTTI Type Descriptor');
    v8 = SharedReplicationTracker::gm_SrTlsIndex;
    if ( v10 )
      v8 = ExtendedReplicationTracker::gm_ErTlsIndex;
  }
  else
  {
    v8 = FailoverReplicationTracker::gm_FrTlsIndex;
  }
  Value = (unsigned int)TlsGetValue(v8);
  TlsSetValue(v8, (LPVOID)(Value | 4));
  Ptr_high = HIDWORD(this[621].Ptr);
  v13 = __RTtypeid(this);
  if ( (unsigned int)__std_type_info_compare(v13 + 8, &qword_140C752B0) )
  {
    v15 = __RTtypeid(this);
    v16 = type_info::operator==(v15, &ExtendedReplicationTracker `RTTI Type Descriptor');
    v14 = SharedReplicationTracker::gm_SrTlsIndex;
    if ( v16 )
      v14 = ExtendedReplicationTracker::gm_ErTlsIndex;
  }
  else
  {
    v14 = FailoverReplicationTracker::gm_FrTlsIndex;
  }
  if ( ((unsigned __int8)TlsGetValue(v14) & 5) == 0 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x21F,
      (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\FailoverReplicationTrackerInternal.h",
      v17);
  if ( (unsigned int)__std_type_info_compare(&qword_140C751D8, &qword_140C751D8) )
  {
    if ( !(unsigned __int8)type_info::operator==(
                             &enum FailoverReplicationTracker::FrOperationalFlags `RTTI Type Descriptor',
                             &enum FailoverReplicationTracker::NetworkOperationalFlags `RTTI Type Descriptor') )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x22B,
        (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\FailoverReplicationTrackerInternal.h",
        (const char *)0x8000FFFFLL,
        v35);
      if ( (unsigned int)VmlIsDebugTraceEnabled(0) )
        VmlDebugTraceEx(
          0,
          &`FailoverReplicationTracker::TestOperationalFlag<enum FailoverReplicationTracker::FrOperationalFlags>'::`16'::traceParameters,
          v19,
          v20);
LABEL_24:
      v21 = __RTtypeid(this);
      if ( (unsigned int)__std_type_info_compare(v21 + 8, &qword_140C752B0) )
      {
        v23 = __RTtypeid(this);
        v24 = type_info::operator==(v23, &ExtendedReplicationTracker `RTTI Type Descriptor');
        v22 = SharedReplicationTracker::gm_SrTlsIndex;
        if ( v24 )
          v22 = ExtendedReplicationTracker::gm_ErTlsIndex;
      }
      else
      {
        v22 = FailoverReplicationTracker::gm_FrTlsIndex;
      }
      if ( ((unsigned __int8)TlsGetValue(v22) & 5) == 0 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x21F,
          (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\FailoverReplicationTrackerInternal.h",
          v25);
      if ( (unsigned int)__std_type_info_compare(&qword_140C751D8, &qword_140C751D8) )
      {
        if ( !(unsigned __int8)type_info::operator==(
                                 &enum FailoverReplicationTracker::FrOperationalFlags `RTTI Type Descriptor',
                                 &enum FailoverReplicationTracker::NetworkOperationalFlags `RTTI Type Descriptor') )
        {
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x22B,
            (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\FailoverReplicationTrackerInternal.h",
            (const char *)0x8000FFFFLL,
            v35);
          if ( (unsigned int)VmlIsDebugTraceEnabled(0) )
            VmlDebugTraceEx(
              0,
              &`FailoverReplicationTracker::TestOperationalFlag<enum FailoverReplicationTracker::FrOperationalFlags>'::`16'::traceParameters,
              v28,
              v29);
          goto LABEL_37;
        }
        Ptr = HIDWORD(this[723].Ptr);
      }
      else
      {
        Ptr = (unsigned int)this[723].Ptr;
      }
      if ( ((Ptr >> 21) & 1) != 0 )
        goto LABEL_34;
LABEL_37:
      v27 = 0;
      goto LABEL_38;
    }
    v18 = HIDWORD(this[723].Ptr);
  }
  else
  {
    v18 = (unsigned int)this[723].Ptr;
  }
  if ( ((v18 >> 3) & 1) == 0 )
    goto LABEL_24;
LABEL_34:
  v27 = 1;
LABEL_38:
  TlsSetValue(v8, (LPVOID)Value);
  v30 = this + 623;
  v31 = 0;
  ReleaseSRWLockShared(v30);
  if ( (unsigned int)(Ptr_high - 32) <= 0x10F || (unsigned int)(Ptr_high - 1024) <= 0x113 )
  {
    if ( (unsigned int)(Ptr_high - 32) > 0x10F )
    {
      v32 = Ptr_high - 1029;
      if ( v32 )
      {
        v33 = v32 - 2;
        if ( v33 )
        {
          if ( v33 != 9 )
            return 1;
        }
      }
    }
    else
    {
      return v27;
    }
  }
  return v31;
}

```

## disassembly

```asm
0x14009b6a0  push    rbx
0x14009b6a2  push    rbp
0x14009b6a3  push    rsi
0x14009b6a4  push    rdi
0x14009b6a5  push    r14
0x14009b6a7  push    r15
0x14009b6a9  sub     rsp, 28h
0x14009b6ad  mov     rdi, rcx
0x14009b6b0  call    cs:__imp___RTtypeid
0x14009b6b7  nop     dword ptr [rax+rax+00h]
0x14009b6bc  lea     rdx, qword_140C752B0
0x14009b6c3  lea     rcx, [rax+8]
0x14009b6c7  call    cs:__imp___std_type_info_compare
0x14009b6ce  nop     dword ptr [rax+rax+00h]
0x14009b6d3  lea     rsi, ??_R0?AVExtendedReplicationTracker@@@8; ExtendedReplicationTracker `RTTI Type Descriptor'
0x14009b6da  test    eax, eax
0x14009b6dc  jnz     short loc_14009B6E6
0x14009b6de  mov     ecx, cs:?gm_FrTlsIndex@FailoverReplicationTracker@@0KA; ulong FailoverReplicationTracker::gm_FrTlsIndex
0x14009b6e4  jmp     short loc_14009B70F
0x14009b6e6  mov     rcx, rdi
0x14009b6e9  call    cs:__imp___RTtypeid
0x14009b6f0  nop     dword ptr [rax+rax+00h]
0x14009b6f5  mov     rcx, rax
0x14009b6f8  mov     rdx, rsi
0x14009b6fb  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x14009b700  mov     ecx, cs:?gm_SrTlsIndex@SharedReplicationTracker@@0KA; ulong SharedReplicationTracker::gm_SrTlsIndex
0x14009b706  test    al, al
0x14009b708  cmovnz  ecx, cs:?gm_ErTlsIndex@ExtendedReplicationTracker@@0KA; dwTlsIndex
0x14009b70f  call    cs:__imp_TlsGetValue
0x14009b716  nop     dword ptr [rax+rax+00h]
0x14009b71b  test    al, 1
0x14009b71d  jz      short loc_14009B736
0x14009b71f  mov     rcx, [rsp+58h]; this
0x14009b724  lea     r8, aOnecoreVmVmmsF_26; "onecore\\vm\\vmms\\fr\\lib\\failoverrep"...
0x14009b72b  mov     edx, 0B75h; void *
0x14009b730  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14009b736  lea     r14, [rdi+1378h]
0x14009b73d  mov     rcx, r14; SRWLock
0x14009b740  call    cs:__imp_AcquireSRWLockShared
0x14009b747  nop     dword ptr [rax+rax+00h]
0x14009b74c  mov     rcx, rdi
0x14009b74f  call    cs:__imp___RTtypeid
0x14009b756  nop     dword ptr [rax+rax+00h]
0x14009b75b  lea     rdx, qword_140C752B0
0x14009b762  lea     rcx, [rax+8]
0x14009b766  call    cs:__imp___std_type_info_compare
0x14009b76d  nop     dword ptr [rax+rax+00h]
0x14009b772  test    eax, eax
0x14009b774  jnz     short loc_14009B77E
0x14009b776  mov     ebp, cs:?gm_FrTlsIndex@FailoverReplicationTracker@@0KA; ulong FailoverReplicationTracker::gm_FrTlsIndex
0x14009b77c  jmp     short loc_14009B7A7
0x14009b77e  mov     rcx, rdi
0x14009b781  call    cs:__imp___RTtypeid
0x14009b788  nop     dword ptr [rax+rax+00h]
0x14009b78d  mov     rcx, rax
0x14009b790  mov     rdx, rsi
0x14009b793  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x14009b798  mov     ebp, cs:?gm_SrTlsIndex@SharedReplicationTracker@@0KA; ulong SharedReplicationTracker::gm_SrTlsIndex
0x14009b79e  test    al, al
0x14009b7a0  cmovnz  ebp, cs:?gm_ErTlsIndex@ExtendedReplicationTracker@@0KA; ulong ExtendedReplicationTracker::gm_ErTlsIndex
0x14009b7a7  mov     ecx, ebp; dwTlsIndex
0x14009b7a9  call    cs:__imp_TlsGetValue
0x14009b7b0  nop     dword ptr [rax+rax+00h]
0x14009b7b5  mov     edx, eax
0x14009b7b7  mov     ecx, ebp; dwTlsIndex
0x14009b7b9  or      rdx, 4; lpTlsValue
0x14009b7bd  mov     r15d, eax
0x14009b7c0  call    cs:__imp_TlsSetValue
0x14009b7c7  nop     dword ptr [rax+rax+00h]
0x14009b7cc  mov     ebx, [rdi+136Ch]
0x14009b7d2  mov     rcx, rdi
0x14009b7d5  call    cs:__imp___RTtypeid
0x14009b7dc  nop     dword ptr [rax+rax+00h]
0x14009b7e1  lea     rdx, qword_140C752B0
0x14009b7e8  lea     rcx, [rax+8]
0x14009b7ec  call    cs:__imp___std_type_info_compare
0x14009b7f3  nop     dword ptr [rax+rax+00h]
0x14009b7f8  test    eax, eax
0x14009b7fa  jnz     short loc_14009B804
0x14009b7fc  mov     ecx, cs:?gm_FrTlsIndex@FailoverReplicationTracker@@0KA; ulong FailoverReplicationTracker::gm_FrTlsIndex
0x14009b802  jmp     short loc_14009B82D
0x14009b804  mov     rcx, rdi
0x14009b807  call    cs:__imp___RTtypeid
0x14009b80e  nop     dword ptr [rax+rax+00h]
0x14009b813  mov     rcx, rax
0x14009b816  mov     rdx, rsi
0x14009b819  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x14009b81e  mov     ecx, cs:?gm_SrTlsIndex@SharedReplicationTracker@@0KA; ulong SharedReplicationTracker::gm_SrTlsIndex
0x14009b824  test    al, al
0x14009b826  cmovnz  ecx, cs:?gm_ErTlsIndex@ExtendedReplicationTracker@@0KA; dwTlsIndex
0x14009b82d  mov     rsi, [rsp+58h]
0x14009b832  call    cs:__imp_TlsGetValue
0x14009b839  nop     dword ptr [rax+rax+00h]
0x14009b83e  test    al, 5
0x14009b840  jz      loc_14009BA53
0x14009b846  lea     rdx, qword_140C751D8
0x14009b84d  lea     rcx, qword_140C751D8
0x14009b854  call    cs:__imp___std_type_info_compare
0x14009b85b  nop     dword ptr [rax+rax+00h]
0x14009b860  test    eax, eax
0x14009b862  jnz     short loc_14009B86C
0x14009b864  mov     eax, [rdi+1698h]
0x14009b86a  jmp     short loc_14009B889
0x14009b86c  lea     rdx, ??_R0?AW4NetworkOperationalFlags@FailoverReplicationTracker@@@8; FailoverReplicationTracker::NetworkOperationalFlags `RTTI Type Descriptor'
0x14009b873  lea     rcx, ??_R0?AW4FrOperationalFlags@FailoverReplicationTracker@@@8; FailoverReplicationTracker::FrOperationalFlags `RTTI Type Descriptor'
0x14009b87a  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x14009b87f  test    al, al
0x14009b881  jz      short loc_14009B899
0x14009b883  mov     eax, [rdi+169Ch]
0x14009b889  shr     eax, 3
0x14009b88c  and     eax, 1
0x14009b88f  test    eax, eax
0x14009b891  jnz     loc_14009B993
0x14009b897  jmp     short loc_14009B8CE
0x14009b899  mov     rcx, [rsp+58h]; this
0x14009b89e  lea     r8, aOnecoreVmVmmsF_34; "onecore\\vm\\vmms\\fr\\lib\\FailoverRep"...
0x14009b8a5  mov     r9d, 8000FFFFh; char *
0x14009b8ab  mov     edx, 22Bh; void *
0x14009b8b0  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x14009b8b5  xor     ecx, ecx
0x14009b8b7  call    VmlIsDebugTraceEnabled
0x14009b8bc  test    eax, eax
0x14009b8be  jz      short loc_14009B8CE
0x14009b8c0  lea     rdx, ?traceParameters@?BA@???$TestOperationalFlag@W4FrOperationalFlags@FailoverReplicationTracker@@@FailoverReplicationTracker@@IEBAHW4FrOperationalFlags@1@@Z@4UVmlDebugTraceParameters@@B; VmlDebugTraceParameters const `FailoverReplicationTracker::TestOperationalFlag<FailoverReplicationTracker::FrOperationalFlags>(FailoverReplicationTracker::FrOperationalFlags)'::`16'::traceParameters
0x14009b8c7  xor     ecx, ecx
0x14009b8c9  call    VmlDebugTraceEx
0x14009b8ce  mov     rcx, rdi
0x14009b8d1  call    cs:__imp___RTtypeid
0x14009b8d8  nop     dword ptr [rax+rax+00h]
0x14009b8dd  lea     rdx, qword_140C752B0
0x14009b8e4  lea     rcx, [rax+8]
0x14009b8e8  call    cs:__imp___std_type_info_compare
0x14009b8ef  nop     dword ptr [rax+rax+00h]
0x14009b8f4  test    eax, eax
0x14009b8f6  jnz     short loc_14009B900
0x14009b8f8  mov     ecx, cs:?gm_FrTlsIndex@FailoverReplicationTracker@@0KA; ulong FailoverReplicationTracker::gm_FrTlsIndex
0x14009b8fe  jmp     short loc_14009B92D
0x14009b900  mov     rcx, rdi
0x14009b903  call    cs:__imp___RTtypeid
0x14009b90a  nop     dword ptr [rax+rax+00h]
0x14009b90f  mov     rcx, rax
0x14009b912  lea     rdx, ??_R0?AVExtendedReplicationTracker@@@8; ExtendedReplicationTracker `RTTI Type Descriptor'
0x14009b919  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x14009b91e  mov     ecx, cs:?gm_SrTlsIndex@SharedReplicationTracker@@0KA; ulong SharedReplicationTracker::gm_SrTlsIndex
0x14009b924  test    al, al
0x14009b926  cmovnz  ecx, cs:?gm_ErTlsIndex@ExtendedReplicationTracker@@0KA; dwTlsIndex
0x14009b92d  mov     rsi, [rsp+58h]
0x14009b932  call    cs:__imp_TlsGetValue
0x14009b939  nop     dword ptr [rax+rax+00h]
0x14009b93e  test    al, 5
0x14009b940  jz      loc_14009BA3E
0x14009b946  lea     rdx, qword_140C751D8
0x14009b94d  lea     rcx, qword_140C751D8
0x14009b954  call    cs:__imp___std_type_info_compare
0x14009b95b  nop     dword ptr [rax+rax+00h]
0x14009b960  test    eax, eax
0x14009b962  jnz     short loc_14009B96C
0x14009b964  mov     eax, [rdi+1698h]
0x14009b96a  jmp     short loc_14009B989
0x14009b96c  lea     rdx, ??_R0?AW4NetworkOperationalFlags@FailoverReplicationTracker@@@8; FailoverReplicationTracker::NetworkOperationalFlags `RTTI Type Descriptor'
0x14009b973  lea     rcx, ??_R0?AW4FrOperationalFlags@FailoverReplicationTracker@@@8; FailoverReplicationTracker::FrOperationalFlags `RTTI Type Descriptor'
0x14009b97a  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x14009b97f  test    al, al
0x14009b981  jz      short loc_14009B99A
0x14009b983  mov     eax, [rdi+169Ch]
0x14009b989  shr     eax, 15h
0x14009b98c  and     eax, 1
0x14009b98f  test    eax, eax
0x14009b991  jz      short loc_14009B9CF
0x14009b993  mov     esi, 1
0x14009b998  jmp     short loc_14009B9D1
0x14009b99a  mov     rcx, [rsp+58h]; this
0x14009b99f  lea     r8, aOnecoreVmVmmsF_34; "onecore\\vm\\vmms\\fr\\lib\\FailoverRep"...
0x14009b9a6  mov     r9d, 8000FFFFh; char *
0x14009b9ac  mov     edx, 22Bh; void *
0x14009b9b1  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x14009b9b6  xor     ecx, ecx
0x14009b9b8  call    VmlIsDebugTraceEnabled
0x14009b9bd  test    eax, eax
0x14009b9bf  jz      short loc_14009B9CF
0x14009b9c1  lea     rdx, ?traceParameters@?BA@???$TestOperationalFlag@W4FrOperationalFlags@FailoverReplicationTracker@@@FailoverReplicationTracker@@IEBAHW4FrOperationalFlags@1@@Z@4UVmlDebugTraceParameters@@B; VmlDebugTraceParameters const `FailoverReplicationTracker::TestOperationalFlag<FailoverReplicationTracker::FrOperationalFlags>(FailoverReplicationTracker::FrOperationalFlags)'::`16'::traceParameters
0x14009b9c8  xor     ecx, ecx
0x14009b9ca  call    VmlDebugTraceEx
0x14009b9cf  xor     esi, esi
0x14009b9d1  mov     rdx, r15; lpTlsValue
0x14009b9d4  mov     ecx, ebp; dwTlsIndex
0x14009b9d6  call    cs:__imp_TlsSetValue
0x14009b9dd  nop     dword ptr [rax+rax+00h]
0x14009b9e2  mov     rcx, r14; SRWLock
0x14009b9e5  xor     edi, edi
0x14009b9e7  call    cs:__imp_ReleaseSRWLockShared
0x14009b9ee  nop     dword ptr [rax+rax+00h]
0x14009b9f3  lea     eax, [rbx-20h]
0x14009b9f6  mov     ecx, 10Fh
0x14009b9fb  cmp     eax, ecx
0x14009b9fd  jbe     short loc_14009BA0C
0x14009b9ff  lea     eax, [rbx-400h]
0x14009ba05  cmp     eax, 113h
0x14009ba0a  ja      short loc_14009BA2E
0x14009ba0c  lea     eax, [rbx-20h]
0x14009ba0f  cmp     eax, ecx
0x14009ba11  ja      short loc_14009BA17
0x14009ba13  mov     edi, esi
0x14009ba15  jmp     short loc_14009BA2E
0x14009ba17  sub     ebx, 405h
0x14009ba1d  jz      short loc_14009BA2E
0x14009ba1f  sub     ebx, 2
0x14009ba22  jz      short loc_14009BA2E
0x14009ba24  cmp     ebx, 9
0x14009ba27  jz      short loc_14009BA2E
0x14009ba29  mov     edi, 1
0x14009ba2e  mov     eax, edi
0x14009ba30  add     rsp, 28h
0x14009ba34  pop     r15
0x14009ba36  pop     r14
0x14009ba38  pop     rdi
0x14009ba39  pop     rsi
0x14009ba3a  pop     rbp
0x14009ba3b  pop     rbx
0x14009ba3c  retn
0x14009ba3e  lea     r8, aOnecoreVmVmmsF_34; "onecore\\vm\\vmms\\fr\\lib\\FailoverRep"...
0x14009ba45  mov     edx, 21Fh; void *
0x14009ba4a  mov     rcx, rsi; this
0x14009ba4d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14009ba53  lea     r8, aOnecoreVmVmmsF_34; "onecore\\vm\\vmms\\fr\\lib\\FailoverRep"...
0x14009ba5a  mov     edx, 21Fh; void *
0x14009ba5f  mov     rcx, rsi; this
0x14009ba62  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
