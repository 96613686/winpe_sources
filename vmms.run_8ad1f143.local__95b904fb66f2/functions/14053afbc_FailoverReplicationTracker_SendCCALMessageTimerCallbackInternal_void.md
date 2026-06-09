# FailoverReplicationTracker::SendCCALMessageTimerCallbackInternal(void)

- ea: `0x14053afbc`
- end: `0x14053b5d4`
- name: `?SendCCALMessageTimerCallbackInternal@FailoverReplicationTracker@@AEAAXXZ`
- size: `1560`
- prototype: `void __fastcall(FailoverReplicationTracker *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14053a5c0`

## callees

- `0x140043d7c`
- `0x1400916d8`
- `0x14009d144`
- `0x1400e605c`
- `0x14017902c`
- `0x140188e18`
- `0x1402407a4`
- `0x1404828e0`
- `0x1404d5640`
- `0x140523868`
- `0x14053afbc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14053b020`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14053b04a`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14053b106`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14053b130`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14053b26f`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14053b299`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14053b355`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14053b37f`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14053b020`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14053b04a`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14053b106`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14053b130`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14053b26f`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14053b299`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14053b355`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14053b37f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14053b198`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14053b42f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14053b4b0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14053b198`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14053b42f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14053b4b0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14053b07c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14053b15c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14053b2cb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14053b3b4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14053b07c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14053b15c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14053b2cb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14053b3b4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14053b173`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14053b224`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14053b3d3`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14053b4e2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14053b173`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14053b224`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14053b3d3`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14053b4e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14053b0a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14053b2f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14053b0a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14053b2f0`

## string_xrefs

- `0x14053b537`: `onecore\vm\common\vml\VmReaderWriterLock.h`
- `0x14053b572`: `onecore\vm\common\vml\VmReaderWriterLock.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall FailoverReplicationTracker::SendCCALMessageTimerCallbackInternal(
        FailoverReplicationTracker *this,
        __int64 a2,
        const struct Vml::ExceptionTraceParameters *a3)
{
  DWORD dwLowDateTime; // r15d
  std::_Ref_count_base *v5; // r13
  __int128 v6; // xmm6
  __int64 v7; // rax
  DWORD v8; // ecx
  __int64 v9; // rax
  char v10; // al
  const char *v11; // r9
  volatile signed __int32 *v12; // rbx
  DWORD CurrentThreadId; // esi
  __int64 v14; // r8
  unsigned __int32 v15; // eax
  unsigned __int32 v16; // edx
  char v17; // al
  __int64 v18; // rax
  DWORD v19; // esi
  __int64 v20; // rax
  char v21; // al
  unsigned __int64 Value; // r14
  __int64 v23; // rdx
  std::_Ref_count_base **v24; // rax
  std::_Ref_count_base *v25; // rcx
  std::_Ref_count_base *v26; // rcx
  int v27; // r12d
  __int64 v28; // rax
  DWORD v29; // ecx
  __int64 v30; // rax
  char v31; // al
  const char *v32; // r9
  DWORD v33; // esi
  __int64 v34; // r8
  char v35; // r14
  unsigned __int32 v36; // eax
  unsigned __int32 v37; // edx
  char v38; // al
  __int64 v39; // rax
  DWORD v40; // esi
  __int64 v41; // rax
  char v42; // al
  unsigned int v43; // r15d
  unsigned __int64 v44; // rax
  std::_Ref_count_base *v45; // rcx
  unsigned int v47; // [rsp+20h] [rbp-C8h]
  unsigned int v48; // [rsp+30h] [rbp-B8h]
  __int128 v49; // [rsp+34h] [rbp-B4h]
  std::_Ref_count_base *v50[2]; // [rsp+48h] [rbp-A0h]
  __int128 v52; // [rsp+58h] [rbp-90h] BYREF
  char *v53; // [rsp+68h] [rbp-80h]
  char v54; // [rsp+70h] [rbp-78h]
  char *v55; // [rsp+78h] [rbp-70h]
  char v56; // [rsp+80h] [rbp-68h]
  _BYTE v57[8]; // [rsp+88h] [rbp-60h] BYREF
  std::_Ref_count_base *v58; // [rsp+90h] [rbp-58h]
  struct _FILETIME pftDueTime; // [rsp+98h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  *(_OWORD *)v50 = 0;
  dwLowDateTime = 1;
  pftDueTime.dwLowDateTime = 1;
  v5 = 0;
  v6 = v49;
  try
  {
    while ( 1 )
    {
      if ( !dwLowDateTime )
        goto LABEL_74;
      v7 = __RTtypeid(this);
      if ( (unsigned __int8)type_info::operator==(v7, &FailoverReplicationTracker `RTTI Type Descriptor') )
      {
        v8 = FailoverReplicationTracker::gm_FrTlsIndex;
      }
      else
      {
        v9 = __RTtypeid(this);
        v10 = type_info::operator==(v9, &ExtendedReplicationTracker `RTTI Type Descriptor');
        v8 = SharedReplicationTracker::gm_SrTlsIndex;
        if ( v10 )
          v8 = ExtendedReplicationTracker::gm_ErTlsIndex;
      }
      if ( ((unsigned __int8)TlsGetValue(v8) & 0x10) != 0 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x1E1D,
          (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationtrackerhelpers.cpp",
          v11);
      v12 = (volatile signed __int32 *)((char *)this + 4720);
      CurrentThreadId = GetCurrentThreadId();
      v15 = _InterlockedCompareExchange((volatile signed __int32 *)this + 1180, 1, 0);
      if ( !v15 )
        goto LABEL_15;
      if ( *((_DWORD *)this + 1181) != CurrentThreadId )
        break;
      _InterlockedAdd((volatile signed __int32 *)this + 1182, 1u);
LABEL_16:
      v53 = (char *)this + 4720;
      v17 = 1;
      v54 = 1;
      while ( v17 )
      {
        v18 = __RTtypeid(this);
        if ( (unsigned __int8)type_info::operator==(v18, &FailoverReplicationTracker `RTTI Type Descriptor') )
        {
          v19 = FailoverReplicationTracker::gm_FrTlsIndex;
        }
        else
        {
          v20 = __RTtypeid(this);
          v21 = type_info::operator==(v20, &ExtendedReplicationTracker `RTTI Type Descriptor');
          v19 = SharedReplicationTracker::gm_SrTlsIndex;
          if ( v21 )
            v19 = ExtendedReplicationTracker::gm_ErTlsIndex;
        }
        Value = (unsigned int)TlsGetValue(v19);
        TlsSetValue(v19, (LPVOID)(Value | 0x20));
        if ( *((_QWORD *)this + 605) )
        {
          v23 = *(_QWORD *)(*((_QWORD *)this + 602) + 8 * (*((_QWORD *)this + 604) & (*((_QWORD *)this + 603) - 1LL)));
          v48 = *(_DWORD *)v23;
          v6 = *(_OWORD *)(v23 + 4);
          v24 = (std::_Ref_count_base **)std::shared_ptr<ConfigurationRepositoryObjects>::shared_ptr<ConfigurationRepositoryObjects>(
                                           v57,
                                           v23 + 24);
          v25 = *v24;
          *v24 = v50[0];
          v50[0] = v25;
          v26 = v24[1];
          v24[1] = v5;
          v5 = v26;
          v50[1] = v26;
          if ( v58 )
            std::_Ref_count_base::_Decref(v58);
        }
        else
        {
          SetThreadpoolTimer(*((PTP_TIMER *)this + 1294), 0, 0, 0);
          dwLowDateTime = 0;
          pftDueTime.dwLowDateTime = 0;
        }
        TlsSetValue(v19, (LPVOID)Value);
        v17 = 0;
        v54 = 0;
      }
      RrwLockRelease((char *)this + 4720);
      if ( !dwLowDateTime )
        goto LABEL_74;
      v52 = v6;
      v27 = FailoverReplicationTracker::SendMessageUsingCCAL(
              this,
              (unsigned __int8 *)v50[0],
              v48,
              (const struct Vml::VmGuid *)&v52);
      v28 = __RTtypeid(this);
      if ( (unsigned __int8)type_info::operator==(v28, &FailoverReplicationTracker `RTTI Type Descriptor') )
      {
        v29 = FailoverReplicationTracker::gm_FrTlsIndex;
      }
      else
      {
        v30 = __RTtypeid(this);
        v31 = type_info::operator==(v30, &ExtendedReplicationTracker `RTTI Type Descriptor');
        v29 = SharedReplicationTracker::gm_SrTlsIndex;
        if ( v31 )
          v29 = ExtendedReplicationTracker::gm_ErTlsIndex;
      }
      if ( ((unsigned __int8)TlsGetValue(v29) & 0x10) != 0 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x1E37,
          (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationtrackerhelpers.cpp",
          v32);
      v33 = GetCurrentThreadId();
      v35 = 1;
      v36 = _InterlockedCompareExchange(v12, 1, 0);
      if ( !v36 )
        goto LABEL_40;
      if ( *((_DWORD *)this + 1181) != v33 )
      {
        do
        {
          while ( (v36 & 1) != 0 || v36 >= 4 )
          {
            LOBYTE(v34) = 1;
            if ( !(unsigned int)RrwpLockWait((char *)this + 4720, 0xFFFFFFFFLL, v34) )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x2FE,
                (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
                (const char *)0x102,
                v47);
            _m_prefetchw((const void *)v12);
            v36 = *v12;
          }
          v37 = v36;
          v36 = _InterlockedCompareExchange(v12, v36 + 1, v36);
        }
        while ( v36 != v37 );
LABEL_40:
        _InterlockedExchange((volatile __int32 *)this + 1181, v33);
        goto LABEL_41;
      }
      _InterlockedAdd((volatile signed __int32 *)this + 1182, 1u);
LABEL_41:
      v55 = (char *)this + 4720;
      v38 = 1;
      v56 = 1;
      while ( v38 )
      {
        v39 = __RTtypeid(this);
        if ( (unsigned __int8)type_info::operator==(v39, &FailoverReplicationTracker `RTTI Type Descriptor') )
        {
          v40 = FailoverReplicationTracker::gm_FrTlsIndex;
        }
        else
        {
          v41 = __RTtypeid(this);
          v42 = type_info::operator==(v41, &ExtendedReplicationTracker `RTTI Type Descriptor');
          v40 = SharedReplicationTracker::gm_SrTlsIndex;
          if ( v42 )
            v40 = ExtendedReplicationTracker::gm_ErTlsIndex;
        }
        v47 = v40;
        v43 = (unsigned int)TlsGetValue(v40);
        TlsSetValue(v40, (LPVOID)(v43 | 0x20));
        while ( v35 )
        {
          if ( v27 < 0 )
          {
            v44 = 2LL * *((_QWORD *)this + 606);
            if ( v44 > 0x927C0 )
              v44 = 600000;
            *((_QWORD *)this + 606) = v44;
            pftDueTime = (struct _FILETIME)(-10000LL * v44);
            SetThreadpoolTimer(*((PTP_TIMER *)this + 1294), &pftDueTime, 0, 0);
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1E44,
              (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationtrackerhelpers.cpp",
              (const char *)(unsigned int)v27,
              v40);
          }
          *((_QWORD *)this + 606) = 5000;
          v45 = *(std::_Ref_count_base **)(*(_QWORD *)(*((_QWORD *)this + 602)
                                                     + 8 * (*((_QWORD *)this + 604) & (*((_QWORD *)this + 603) - 1LL)))
                                         + 32LL);
          if ( v45 )
            std::_Ref_count_base::_Decref(v45);
          if ( (*((_QWORD *)this + 605))-- == 1 )
          {
            *((_QWORD *)this + 604) = 0;
            SetThreadpoolTimer(*((PTP_TIMER *)this + 1294), 0, 0, 0);
            pftDueTime.dwLowDateTime = 0;
          }
          else
          {
            ++*((_QWORD *)this + 604);
          }
          v35 = 0;
        }
        TlsSetValue(v40, (LPVOID)v43);
        v38 = 0;
        v56 = 0;
        v35 = 1;
      }
      RrwLockRelease((char *)this + 4720);
      dwLowDateTime = pftDueTime.dwLowDateTime;
    }
    do
    {
      while ( (v15 & 1) != 0 || v15 >= 4 )
      {
        LOBYTE(v14) = 1;
        if ( !(unsigned int)RrwpLockWait((char *)this + 4720, 0xFFFFFFFFLL, v14) )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x2FE,
            (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
            (const char *)0x102,
            v47);
        _m_prefetchw((const void *)v12);
        v15 = *v12;
      }
      v16 = v15;
      v15 = _InterlockedCompareExchange(v12, v15 + 1, v15);
    }
    while ( v15 != v16 );
LABEL_15:
    _InterlockedExchange((volatile __int32 *)this + 1181, CurrentThreadId);
    goto LABEL_16;
  }
  catch ( ... )
  {
    Vml::GetHResultFromThrownExceptionAndTrace((Vml *)0x41A0, (unsigned __int16)&off_14090C678, a3);
    v5 = v50[1];
  }
LABEL_74:
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
}

```

## disassembly

```asm
0x14053afbc  mov     rax, rsp
0x14053afbf  mov     [rax+10h], rbx
0x14053afc3  mov     [rax+18h], rsi
0x14053afc7  push    rdi
0x14053afc8  push    r12
0x14053afca  push    r13
0x14053afcc  push    r14
0x14053afce  push    r15
0x14053afd0  sub     rsp, 0C0h
0x14053afd7  movaps  xmmword ptr [rax-38h], xmm6
0x14053afdb  mov     rax, cs:__security_cookie
0x14053afe2  xor     rax, rsp
0x14053afe5  mov     [rsp+0E8h+var_48], rax
0x14053afed  mov     rdi, rcx
0x14053aff0  xorps   xmm0, xmm0
0x14053aff3  movdqu  xmmword ptr [rsp+0E8h+var_A0], xmm0
0x14053aff9  mov     r14d, 1
0x14053afff  mov     r15d, r14d
0x14053b002  mov     [rsp+0E8h+pftDueTime.dwLowDateTime], r14d
0x14053b00a  mov     r13, [rsp+0E8h+var_A0+8]
0x14053b00f  movups  xmm6, [rsp+0E8h+var_B4]
0x14053b014  test    r15d, r15d
0x14053b017  jz      loc_14053B58D
0x14053b01d  mov     rcx, rdi
0x14053b020  call    cs:__imp___RTtypeid
0x14053b027  nop     dword ptr [rax+rax+00h]
0x14053b02c  lea     rdx, ??_R0?AVFailoverReplicationTracker@@@8; FailoverReplicationTracker `RTTI Type Descriptor'
0x14053b033  mov     rcx, rax
0x14053b036  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x14053b03b  test    al, al
0x14053b03d  jz      short loc_14053B047
0x14053b03f  mov     ecx, cs:?gm_FrTlsIndex@FailoverReplicationTracker@@0KA; ulong FailoverReplicationTracker::gm_FrTlsIndex
0x14053b045  jmp     short loc_14053B074
0x14053b047  mov     rcx, rdi
0x14053b04a  call    cs:__imp___RTtypeid
0x14053b051  nop     dword ptr [rax+rax+00h]
0x14053b056  lea     rdx, ??_R0?AVExtendedReplicationTracker@@@8; ExtendedReplicationTracker `RTTI Type Descriptor'
0x14053b05d  mov     rcx, rax
0x14053b060  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x14053b065  mov     ecx, cs:?gm_SrTlsIndex@SharedReplicationTracker@@0KA; ulong SharedReplicationTracker::gm_SrTlsIndex
0x14053b06b  test    al, al
0x14053b06d  cmovnz  ecx, cs:?gm_ErTlsIndex@ExtendedReplicationTracker@@0KA; dwTlsIndex
0x14053b074  mov     rbx, [rsp+0E8h]
0x14053b07c  call    cs:__imp_TlsGetValue
0x14053b083  nop     dword ptr [rax+rax+00h]
0x14053b088  test    al, 10h
0x14053b08a  jz      short loc_14053B0A1
0x14053b08c  lea     r8, aOnecoreVmVmmsF_46; "onecore\\vm\\vmms\\fr\\lib\\failoverrep"...
0x14053b093  mov     edx, 1E1Dh; void *
0x14053b098  mov     rcx, rbx; this
0x14053b09b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14053b0a1  lea     rbx, [rdi+1270h]
0x14053b0a8  call    cs:__imp_GetCurrentThreadId
0x14053b0af  nop     dword ptr [rax+rax+00h]
0x14053b0b4  mov     esi, eax
0x14053b0b6  xor     eax, eax
0x14053b0b8  lock cmpxchg [rbx], r14d
0x14053b0bd  jz      short loc_14053B0EC
0x14053b0bf  mov     ecx, [rbx+4]
0x14053b0c2  cmp     ecx, esi
0x14053b0c4  jnz     short loc_14053B0CD
0x14053b0c6  lock add [rbx+8], r14d
0x14053b0cb  jmp     short loc_14053B0EF
0x14053b0cd  test    r14b, al
0x14053b0d0  jnz     loc_14053B552
0x14053b0d6  cmp     eax, 4
0x14053b0d9  jnb     loc_14053B552
0x14053b0df  mov     edx, eax
0x14053b0e1  lea     ecx, [rax+1]
0x14053b0e4  lock cmpxchg [rbx], ecx
0x14053b0e8  cmp     eax, edx
0x14053b0ea  jnz     short loc_14053B0CD
0x14053b0ec  xchg    esi, [rbx+4]
0x14053b0ef  mov     [rsp+0E8h+var_80], rbx
0x14053b0f4  mov     al, r14b
0x14053b0f7  mov     [rsp+0E8h+var_78], al
0x14053b0fb  test    al, al
0x14053b0fd  jz      loc_14053B23B
0x14053b103  mov     rcx, rdi
0x14053b106  call    cs:__imp___RTtypeid
0x14053b10d  nop     dword ptr [rax+rax+00h]
0x14053b112  lea     rdx, ??_R0?AVFailoverReplicationTracker@@@8; FailoverReplicationTracker `RTTI Type Descriptor'
0x14053b119  mov     rcx, rax
0x14053b11c  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x14053b121  test    al, al
0x14053b123  jz      short loc_14053B12D
0x14053b125  mov     esi, cs:?gm_FrTlsIndex@FailoverReplicationTracker@@0KA; ulong FailoverReplicationTracker::gm_FrTlsIndex
0x14053b12b  jmp     short loc_14053B15A
0x14053b12d  mov     rcx, rdi
0x14053b130  call    cs:__imp___RTtypeid
0x14053b137  nop     dword ptr [rax+rax+00h]
0x14053b13c  lea     rdx, ??_R0?AVExtendedReplicationTracker@@@8; ExtendedReplicationTracker `RTTI Type Descriptor'
0x14053b143  mov     rcx, rax
0x14053b146  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x14053b14b  mov     esi, cs:?gm_SrTlsIndex@SharedReplicationTracker@@0KA; ulong SharedReplicationTracker::gm_SrTlsIndex
0x14053b151  test    al, al
0x14053b153  cmovnz  esi, cs:?gm_ErTlsIndex@ExtendedReplicationTracker@@0KA; ulong ExtendedReplicationTracker::gm_ErTlsIndex
0x14053b15a  mov     ecx, esi; dwTlsIndex
0x14053b15c  call    cs:__imp_TlsGetValue
0x14053b163  nop     dword ptr [rax+rax+00h]
0x14053b168  mov     r14d, eax
0x14053b16b  mov     edx, eax
0x14053b16d  or      rdx, 20h; lpTlsValue
0x14053b171  mov     ecx, esi; dwTlsIndex
0x14053b173  call    cs:__imp_TlsSetValue
0x14053b17a  nop     dword ptr [rax+rax+00h]
0x14053b17f  cmp     qword ptr [rdi+12E8h], 0
0x14053b187  jnz     short loc_14053B1B1
0x14053b189  xor     r9d, r9d; msWindowLength
0x14053b18c  xor     r8d, r8d; msPeriod
0x14053b18f  xor     edx, edx; pftDueTime
0x14053b191  mov     rcx, [rdi+2870h]; pti
0x14053b198  call    cs:__imp_SetThreadpoolTimer
0x14053b19f  nop     dword ptr [rax+rax+00h]
0x14053b1a4  xor     r15d, r15d
0x14053b1a7  mov     [rsp+0E8h+pftDueTime.dwLowDateTime], r15d
0x14053b1af  jmp     short loc_14053B21F
0x14053b1b1  mov     rcx, [rdi+12D8h]
0x14053b1b8  dec     rcx
0x14053b1bb  and     rcx, [rdi+12E0h]
0x14053b1c2  mov     rax, [rdi+12D0h]
0x14053b1c9  mov     rdx, [rax+rcx*8]
0x14053b1cd  mov     eax, [rdx]
0x14053b1cf  mov     [rsp+0E8h+var_B8], eax
0x14053b1d3  movups  xmm6, xmmword ptr [rdx+4]
0x14053b1d7  movups  [rsp+0E8h+var_B4], xmm6
0x14053b1dc  add     rdx, 18h
0x14053b1e0  lea     rcx, [rsp+0E8h+var_60]
0x14053b1e8  call    ??0?$shared_ptr@UConfigurationRepositoryObjects@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ConfigurationRepositoryObjects>::shared_ptr<ConfigurationRepositoryObjects>(std::shared_ptr<ConfigurationRepositoryObjects> const &)
0x14053b1ed  mov     rcx, [rax]
0x14053b1f0  mov     rdx, [rsp+0E8h+var_A0]
0x14053b1f5  mov     [rax], rdx
0x14053b1f8  mov     [rsp+0E8h+var_A0], rcx
0x14053b1fd  mov     rcx, [rax+8]
0x14053b201  mov     [rax+8], r13
0x14053b205  mov     r13, rcx
0x14053b208  mov     [rsp+0E8h+var_A0+8], rcx
0x14053b20d  mov     rcx, [rsp+0E8h+var_58]; this
0x14053b215  test    rcx, rcx
0x14053b218  jz      short loc_14053B21F
0x14053b21a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14053b21f  mov     rdx, r14; lpTlsValue
0x14053b222  mov     ecx, esi; dwTlsIndex
0x14053b224  call    cs:__imp_TlsSetValue
0x14053b22b  nop     dword ptr [rax+rax+00h]
0x14053b230  xor     al, al
0x14053b232  mov     [rsp+0E8h+var_78], al
0x14053b236  jmp     loc_14053B0FB
0x14053b23b  mov     rcx, rbx
0x14053b23e  call    RrwLockRelease
0x14053b243  test    r15d, r15d
0x14053b246  jz      loc_14053B58D
0x14053b24c  movdqu  [rsp+0E8h+var_90], xmm6
0x14053b252  lea     r9, [rsp+0E8h+var_90]; struct Vml::VmGuid *
0x14053b257  mov     r8d, [rsp+0E8h+var_B8]; unsigned int
0x14053b25c  mov     rdx, [rsp+0E8h+var_A0]; unsigned __int8 *
0x14053b261  mov     rcx, rdi; this
0x14053b264  call    ?SendMessageUsingCCAL@FailoverReplicationTracker@@IEAAJPEAEKAEBVVmGuid@Vml@@@Z; FailoverReplicationTracker::SendMessageUsingCCAL(uchar *,ulong,Vml::VmGuid const &)
0x14053b269  mov     r12d, eax
0x14053b26c  mov     rcx, rdi
0x14053b26f  call    cs:__imp___RTtypeid
0x14053b276  nop     dword ptr [rax+rax+00h]
0x14053b27b  lea     rdx, ??_R0?AVFailoverReplicationTracker@@@8; FailoverReplicationTracker `RTTI Type Descriptor'
0x14053b282  mov     rcx, rax
0x14053b285  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x14053b28a  test    al, al
0x14053b28c  jz      short loc_14053B296
0x14053b28e  mov     ecx, cs:?gm_FrTlsIndex@FailoverReplicationTracker@@0KA; ulong FailoverReplicationTracker::gm_FrTlsIndex
0x14053b294  jmp     short loc_14053B2C3
0x14053b296  mov     rcx, rdi
0x14053b299  call    cs:__imp___RTtypeid
0x14053b2a0  nop     dword ptr [rax+rax+00h]
0x14053b2a5  lea     rdx, ??_R0?AVExtendedReplicationTracker@@@8; ExtendedReplicationTracker `RTTI Type Descriptor'
0x14053b2ac  mov     rcx, rax
0x14053b2af  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x14053b2b4  mov     ecx, cs:?gm_SrTlsIndex@SharedReplicationTracker@@0KA; ulong SharedReplicationTracker::gm_SrTlsIndex
0x14053b2ba  test    al, al
0x14053b2bc  cmovnz  ecx, cs:?gm_ErTlsIndex@ExtendedReplicationTracker@@0KA; dwTlsIndex
0x14053b2c3  mov     rsi, [rsp+0E8h]
0x14053b2cb  call    cs:__imp_TlsGetValue
0x14053b2d2  nop     dword ptr [rax+rax+00h]
0x14053b2d7  test    al, 10h
0x14053b2d9  jz      short loc_14053B2F0
0x14053b2db  lea     r8, aOnecoreVmVmmsF_46; "onecore\\vm\\vmms\\fr\\lib\\failoverrep"...
0x14053b2e2  mov     edx, 1E37h; void *
0x14053b2e7  mov     rcx, rsi; this
0x14053b2ea  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14053b2f0  call    cs:__imp_GetCurrentThreadId
0x14053b2f7  nop     dword ptr [rax+rax+00h]
0x14053b2fc  mov     esi, eax
0x14053b2fe  xor     eax, eax
0x14053b300  lea     r14d, [rax+1]
0x14053b304  lock cmpxchg [rbx], r14d
0x14053b309  jz      short loc_14053B338
0x14053b30b  mov     ecx, [rbx+4]
0x14053b30e  cmp     ecx, esi
0x14053b310  jnz     short loc_14053B319
0x14053b312  lock add [rbx+8], r14d
0x14053b317  jmp     short loc_14053B33B
0x14053b319  test    r14b, al
0x14053b31c  jnz     loc_14053B517
0x14053b322  cmp     eax, 4
0x14053b325  jnb     loc_14053B517
0x14053b32b  mov     edx, eax
0x14053b32d  lea     ecx, [rax+1]
0x14053b330  lock cmpxchg [rbx], ecx
0x14053b334  cmp     eax, edx
0x14053b336  jnz     short loc_14053B319
0x14053b338  xchg    esi, [rbx+4]
0x14053b33b  mov     [rsp+0E8h+var_70], rbx
0x14053b340  mov     al, r14b
0x14053b343  mov     [rsp+0E8h+var_68], al
0x14053b34a  test    al, al
0x14053b34c  jz      loc_14053B502
0x14053b352  mov     rcx, rdi
0x14053b355  call    cs:__imp___RTtypeid
0x14053b35c  nop     dword ptr [rax+rax+00h]
0x14053b361  lea     rdx, ??_R0?AVFailoverReplicationTracker@@@8; FailoverReplicationTracker `RTTI Type Descriptor'
0x14053b368  mov     rcx, rax
0x14053b36b  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x14053b370  test    al, al
0x14053b372  jz      short loc_14053B37C
0x14053b374  mov     esi, cs:?gm_FrTlsIndex@FailoverReplicationTracker@@0KA; ulong FailoverReplicationTracker::gm_FrTlsIndex
0x14053b37a  jmp     short loc_14053B3A9
0x14053b37c  mov     rcx, rdi
0x14053b37f  call    cs:__imp___RTtypeid
0x14053b386  nop     dword ptr [rax+rax+00h]
0x14053b38b  lea     rdx, ??_R0?AVExtendedReplicationTracker@@@8; ExtendedReplicationTracker `RTTI Type Descriptor'
0x14053b392  mov     rcx, rax
0x14053b395  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x14053b39a  mov     esi, cs:?gm_SrTlsIndex@SharedReplicationTracker@@0KA; ulong SharedReplicationTracker::gm_SrTlsIndex
0x14053b3a0  test    al, al
0x14053b3a2  cmovnz  esi, cs:?gm_ErTlsIndex@ExtendedReplicationTracker@@0KA; ulong ExtendedReplicationTracker::gm_ErTlsIndex
0x14053b3a9  mov     [rsp+0E8h+var_BC], r14b
0x14053b3ae  mov     [rsp+0E8h+var_C8], esi; int
0x14053b3b2  mov     ecx, esi; dwTlsIndex
0x14053b3b4  call    cs:__imp_TlsGetValue
0x14053b3bb  nop     dword ptr [rax+rax+00h]
0x14053b3c0  mov     r15, rax
0x14053b3c3  mov     [rsp+0E8h+var_C4], r15d
0x14053b3c8  mov     edx, eax
0x14053b3ca  or      edx, 20h; lpTlsValue
0x14053b3cd  mov     [rsp+0E8h+var_C0], edx
0x14053b3d1  mov     ecx, esi; dwTlsIndex
0x14053b3d3  call    cs:__imp_TlsSetValue
0x14053b3da  nop     dword ptr [rax+rax+00h]
0x14053b3df  nop
0x14053b3e0  test    r14b, r14b
0x14053b3e3  jz      loc_14053B4DD
0x14053b3e9  test    r12d, r12d
0x14053b3ec  jns     short loc_14053B457
0x14053b3ee  mov     rax, [rdi+12F0h]
0x14053b3f5  add     rax, rax
0x14053b3f8  mov     ecx, 927C0h
0x14053b3fd  cmp     rax, rcx
0x14053b400  cmova   rax, rcx
0x14053b404  mov     [rdi+12F0h], rax
0x14053b40b  imul    rax, 0FFFFFFFFFFFFD8F0h
0x14053b412  mov     qword ptr [rsp+0E8h+pftDueTime.dwLowDateTime], rax
0x14053b41a  xor     r9d, r9d; msWindowLength
0x14053b41d  xor     r8d, r8d; msPeriod
0x14053b420  lea     rdx, [rsp+0E8h+pftDueTime]; pftDueTime
0x14053b428  mov     rcx, [rdi+2870h]; pti
0x14053b42f  call    cs:__imp_SetThreadpoolTimer
0x14053b436  nop     dword ptr [rax+rax+00h]
0x14053b43b  mov     rcx, [rsp+0E8h]; this
0x14053b443  mov     r9d, r12d; char *
0x14053b446  lea     r8, aOnecoreVmVmmsF_46; "onecore\\vm\\vmms\\fr\\lib\\failoverrep"...
0x14053b44d  mov     edx, 1E44h; void *
0x14053b452  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14053b457  mov     qword ptr [rdi+12F0h], 1388h
0x14053b462  mov     rcx, [rdi+12D8h]
0x14053b469  dec     rcx
0x14053b46c  and     rcx, [rdi+12E0h]
0x14053b473  mov     rax, [rdi+12D0h]
0x14053b47a  mov     rcx, [rax+rcx*8]
0x14053b47e  mov     rcx, [rcx+20h]; this
0x14053b482  test    rcx, rcx
0x14053b485  jz      short loc_14053B48C
0x14053b487  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14053b48c  sub     qword ptr [rdi+12E8h], 1
0x14053b494  jnz     short loc_14053B4C9
0x14053b496  mov     qword ptr [rdi+12E0h], 0
0x14053b4a1  xor     r9d, r9d; msWindowLength
0x14053b4a4  xor     r8d, r8d; msPeriod
0x14053b4a7  xor     edx, edx; pftDueTime
0x14053b4a9  mov     rcx, [rdi+2870h]; pti
0x14053b4b0  call    cs:__imp_SetThreadpoolTimer
0x14053b4b7  nop     dword ptr [rax+rax+00h]
0x14053b4bc  mov     [rsp+0E8h+pftDueTime.dwLowDateTime], 0
0x14053b4c7  jmp     short loc_14053B4D0
0x14053b4c9  inc     qword ptr [rdi+12E0h]
0x14053b4d0  xor     r14b, r14b
0x14053b4d3  mov     [rsp+0E8h+var_BC], r14b
0x14053b4d8  jmp     loc_14053B3E0
0x14053b4dd  mov     edx, r15d; lpTlsValue
0x14053b4e0  mov     ecx, esi; dwTlsIndex
0x14053b4e2  call    cs:__imp_TlsSetValue
0x14053b4e9  nop     dword ptr [rax+rax+00h]
0x14053b4ee  xor     al, al
  ... truncated ...
```
