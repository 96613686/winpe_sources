# CHttp2::ProcessSends(int,ulong)

- ea: `0x18002a250`
- end: `0x18002a9a8`
- name: `?ProcessSends@CHttp2@@AEAAJHK@Z`
- size: `1880`
- prototype: `__int64 __fastcall(CHttp2 *__hidden this, int, unsigned int)`
- caller_count: `3`
- callee_count: `25`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180029120`
- `0x18002dae0`
- `0x180065ff0`

## callees

- `0x18002918c`
- `0x18002a250`
- `0x18002a9b0`
- `0x18002aa20`
- `0x18002be44`
- `0x18002c15c`
- `0x18002c94c`
- `0x18002d290`
- `0x18002da80`
- `0x18002db48`
- `0x18002e990`
- `0x18002f304`
- `0x18002ff28`
- `0x1800358d8`
- `0x180044b8c`
- `0x18004f9f0`
- `0x18004fa4c`
- `0x18005049c`
- `0x180059730`
- `0x180068318`
- `0x1800738bc`
- `0x1800971ec`
- `0x180097480`
- `0x180097810`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002a2d8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002a7a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002a8e9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002a2d8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002a7a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002a8e9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a2c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a2c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a45a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a48e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a51a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a45a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a48e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a51a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a3b6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a3b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a3dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a7d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a3dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a7d5`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002a3f8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002a3f8`
- `ntdll!RtlNtStatusToDosError` at `0x18002a8ad`
- `ntdll!RtlNtStatusToDosError` at `0x18002a8ad`

## pseudocode

```c
__int64 __fastcall CHttp2::ProcessSends(CHttp2 *this, int a2, __int64 a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  int v4; // ebp
  signed int v5; // r14d
  _QWORD **v7; // r12
  DWORD TickCount; // eax
  bool v9; // zf
  int v10; // edi
  signed int v11; // r13d
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r15
  __int64 v15; // rax
  CHttp2 *v16; // rcx
  __int64 v17; // rdi
  RTL_SRWLOCK *v18; // rcx
  CHttp2SendContext *v19; // rdi
  unsigned int v20; // edx
  _QWORD *v21; // rax
  unsigned int v22; // ebx
  _QWORD *v24; // rcx
  unsigned int v25; // ecx
  unsigned int v26; // edi
  struct CHttp2SendContext *v27; // rdx
  int v28; // eax
  int updated; // eax
  __int64 v30; // rax
  __int64 v31; // rdi
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // rdi
  __int64 v35; // rdi
  int v36; // eax
  unsigned int v37; // r8d
  unsigned int v38; // r9d
  DWORD v39; // eax
  unsigned int v40; // r9d
  CHttp2 *v41; // rcx
  ULONG v42; // eax
  unsigned int v43; // r8d
  int v44; // edi
  unsigned int v45; // eax
  unsigned int v46; // [rsp+40h] [rbp-68h]
  int v47; // [rsp+44h] [rbp-64h] BYREF
  unsigned int v48; // [rsp+48h] [rbp-60h]
  unsigned int v49; // [rsp+4Ch] [rbp-5Ch]
  unsigned int v50; // [rsp+50h] [rbp-58h]
  int v51; // [rsp+54h] [rbp-54h]
  unsigned int *v52; // [rsp+58h] [rbp-50h] BYREF
  struct _RTL_CRITICAL_SECTION *v53; // [rsp+60h] [rbp-48h] BYREF
  __int64 v54; // [rsp+68h] [rbp-40h]

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  v51 = 0;
  v4 = 0;
  v54 = 0;
  v5 = a3;
  v53 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  v47 = 0;
  v52 = 0;
  v48 = 0;
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_qld(this, 75, a3, this, a2, a3);
  v7 = (_QWORD **)((char *)this + 160);
  while ( 1 )
  {
LABEL_4:
    if ( v5 )
    {
      if ( v5 > 0 )
        v5 = (unsigned __int16)v5 | 0x80070000;
      CHttp2::Abort(this, v5);
    }
    if ( v3 && !v4 )
    {
      EnterCriticalSection(v3);
      v4 = 1;
      LODWORD(v54) = 1;
    }
    TickCount = GetTickCount();
    v9 = *((_DWORD *)this + 38) == 0;
    *((_DWORD *)this + 59) = TickCount;
    v51 = 0;
    if ( v9 )
    {
      v10 = 0;
    }
    else
    {
      v10 = *((_DWORD *)this + 39);
      v51 = 1358;
    }
    if ( (v10 & 0x1FFF0000) == 0xC0000 )
    {
      v5 = (unsigned __int16)v10;
    }
    else if ( v10 < 0 )
    {
      if ( (v10 & 0x1FFF0000) == 0x70000 )
      {
        v5 = (unsigned __int16)v10;
        if ( !(_WORD)v10 )
          v5 = 317;
      }
      else if ( (v10 & 0x10000000) != 0 )
      {
        v42 = RtlNtStatusToDosError(v10 & 0xEFFFFFFF);
        v5 = v42;
        if ( v42 )
        {
          if ( v42 == 317 )
            v5 = v10;
        }
        else
        {
          v5 = v10;
        }
      }
      else
      {
        v5 = v10;
      }
    }
    else
    {
      v5 = 0;
    }
    if ( !*((_QWORD *)this + 24) )
      break;
    v11 = v5;
    if ( !v5 && v47 < 0 )
      v11 = WX_WIN32_FROM_HR((unsigned int)v47);
    v12 = *((_QWORD *)this + 24);
    v13 = *(_QWORD *)(v12 + 64);
    v14 = v13 + 32;
    if ( !v13 )
      v14 = 0;
    if ( !v11 && *(_DWORD *)(v12 + 4) == 2 && *(_DWORD *)(v12 + 112) )
    {
      if ( *(_DWORD *)(v14 + 16) == 3 )
      {
        CHttp2::ResetSendTimer(0, (struct _HTTP2_STREAM_LINKAGE *)v14);
        CHttp2::InsertSendContext(this, *((struct CHttp2SendContext **)this + 24));
        *((_QWORD *)this + 24) = 0;
        break;
      }
      v11 = WX_WIN32_FROM_HR(*(unsigned int *)(v14 + 20));
    }
    v15 = *((_QWORD *)this + 24);
    v50 = *(_DWORD *)(v15 + 136);
    *(_DWORD *)(v15 + 136) = 0;
    if ( v14 && *(_QWORD *)(v14 + 40) == *((_QWORD *)this + 24) )
      *(_QWORD *)(v14 + 40) = 0;
    v16 = (CHttp2 *)(unsigned int)(*(_DWORD *)(*((_QWORD *)this + 24) + 4LL) - 1);
    if ( (unsigned int)v16 <= 1 )
    {
      --*(_DWORD *)(v14 + 56);
      v34 = v14 - 32;
      if ( *(_DWORD *)(v14 + 60) )
      {
        v35 = *(_QWORD *)(v34 + 24);
        if ( (unsigned __int8)WaCancelTwTimer(v35 + 104) )
        {
          *(_QWORD *)(v35 + 168) = 0;
          *(_QWORD *)(v35 + 176) = 0;
          v34 = v14 - 32;
          *(_DWORD *)(v14 + 60) = 0;
          CHttp2Stream::Release((CHttp2Stream *)(v14 - 32));
        }
        else
        {
          v34 = v14 - 32;
        }
      }
      v36 = *(_DWORD *)(v14 + 16);
      if ( v36 != 4 )
      {
        v9 = *(_DWORD *)(v14 + 56) == 0;
        v49 = 0;
        if ( v9 )
        {
          v37 = 0;
          v38 = 0;
LABEL_74:
          CHttp2::StartSendTimer(v16, (struct _HTTP2_STREAM_LINKAGE *)v14, v37, v38);
          goto LABEL_22;
        }
        if ( v36 == 1 )
        {
          v43 = *(_DWORD *)(v34 + 160);
          v44 = *(_DWORD *)(v14 + 68);
          v46 = v43;
          v38 = GetTickCount() - v44;
          if ( v38 >= v46 || v46 - v38 <= 0x1F4 )
          {
            if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
              WPP_SF_q(1050, 96, WPP_1eba17a514423a0ebe5ee43bce786d1b_Traceguids, v14 - 32);
            v37 = 500;
            v38 = 0;
          }
          else
          {
            v37 = v46;
          }
          goto LABEL_74;
        }
        v39 = GetTickCount();
        v40 = v49;
        *(_DWORD *)(v14 + 64) = v39;
        CHttp2::StartSendTimer(v41, (struct _HTTP2_STREAM_LINKAGE *)v14, *(_DWORD *)(v34 + 156), v40);
      }
    }
LABEL_22:
    v17 = *((_QWORD *)this + 24);
    if ( (unsigned int)(*(_DWORD *)(v17 + 4) - 1) <= 1 )
    {
      AcquireSRWLockExclusive((PSRWLOCK)(v17 + 24));
      v18 = (RTL_SRWLOCK *)(v17 + 24);
      if ( *(_DWORD *)(v17 + 144) )
      {
        ReleaseSRWLockExclusive(v18);
      }
      else
      {
        *(_DWORD *)(v17 + 144) = 1;
        ReleaseSRWLockExclusive(v18);
        *(_DWORD *)(v17 + 48) = v11;
        _InterlockedIncrement((volatile signed __int32 *)v17);
        SubmitThreadpoolWork(*(PTP_WORK *)(*(_QWORD *)(v17 + 56) + 8LL));
      }
    }
    v19 = (CHttp2SendContext *)*((_QWORD *)this + 24);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v19, 0xFFFFFFFF) == 1 && v19 )
    {
      CHttp2SendContext::~CHttp2SendContext(v19);
      operator delete(v19);
    }
    v20 = v50;
    *((_QWORD *)this + 24) = 0;
    if ( !v20 )
      break;
    v45 = CHttp2::IncrementSessionWindowLocked(this, v20);
    v5 = WX_WIN32_FROM_HR(v45);
    if ( !v5 )
      break;
    AutoCritSec::Unlock((AutoCritSec *)&v53);
    v4 = v54;
    v3 = v53;
  }
  while ( 1 )
  {
    v21 = *v7;
    if ( *v7 == v7 )
      break;
    if ( (_QWORD **)v21[1] != v7 || (v24 = (_QWORD *)*v21, *(_QWORD **)(*v21 + 8LL) != v21) )
      __fastfail(3u);
    *v7 = v24;
    v24[1] = v7;
    v21[1] = v21;
    *v21 = v21;
    *((_QWORD *)this + 24) = v21 - 1;
    CHttp2::GetAvailableSendWindow(this);
    if ( *((_QWORD *)this + 24) )
    {
      v25 = *((_DWORD *)this + 102);
      if ( v25 )
      {
        v26 = *((_DWORD *)this + 102);
        v52 = (unsigned int *)*((_QWORD *)this + 50);
        *((_QWORD *)this + 50) = 0;
        v48 = v25;
        *((_DWORD *)this + 102) = 0;
      }
      else
      {
        v26 = v48;
      }
      if ( v3 && v4 )
      {
        LeaveCriticalSection(v3);
        v4 = 0;
        LODWORD(v54) = 0;
      }
      if ( v26 )
      {
        updated = CHttp2::UpdateCompressionTableSize(this, &v52, v26);
        v48 = 0;
        if ( updated < 0 )
          goto LABEL_51;
      }
      v27 = (struct CHttp2SendContext *)*((_QWORD *)this + 24);
      v47 = 0;
      v28 = *((_DWORD *)v27 + 1);
      if ( v28 == 1 )
      {
        updated = CHttp2::OpenStream(this, v27, &v47);
        if ( updated < 0 )
          goto LABEL_51;
LABEL_53:
        if ( v47 < 0 )
          goto LABEL_4;
      }
      else if ( v28 == 2 )
      {
        updated = CHttp2::FrameData(this, v27, &v47);
        if ( updated < 0 )
        {
LABEL_51:
          v5 = WX_WIN32_FROM_HR((unsigned int)updated);
          goto LABEL_4;
        }
        goto LABEL_53;
      }
      CHttp2::StopPingTimer(this);
      _InterlockedIncrement((volatile signed __int32 *)this);
      v30 = *((_QWORD *)this + 24);
      v31 = *((_QWORD *)this + 6);
      v32 = *(unsigned int *)(v30 + 128);
      v33 = *(_QWORD *)(v30 + 120);
      *(_QWORD *)(v31 + 152) = CHttp2::SendCompletion;
      *(_DWORD *)(v31 + 128) = 0;
      *(_QWORD *)(v31 + 136) = v33;
      *(_QWORD *)(v31 + 144) = v32;
      *(_QWORD *)(v31 + 160) = this;
      _InterlockedIncrement((volatile signed __int32 *)(v31 + 4));
      v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, __int64 (__fastcall *)(), __int64))(*(_QWORD *)(v31 + 72) + 80LL))(
             *(_QWORD *)(*(_QWORD *)(v31 + 72) + 64LL),
             v31 + 128,
             1,
             0,
             WapHttp2ConnectionSendCompletion,
             v31);
      if ( v5 == 997 )
      {
        v22 = -2147023899;
        v51 = 2940;
        goto LABEL_31;
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v31 + 4), 0xFFFFFFFF) == 1 )
        WapDestroyHttp2Connection(v31);
      *(_OWORD *)(v31 + 128) = 0;
      *(_QWORD *)(v31 + 144) = 0;
      *(_QWORD *)(v31 + 152) = 0;
      *(_QWORD *)(v31 + 160) = 0;
      CHttp2::Release(this);
      goto LABEL_4;
    }
  }
  *((_DWORD *)this + 50) = 0;
  CHttp2::StartPingTimer(this);
  v22 = 0;
  if ( v3 && v4 )
  {
    LeaveCriticalSection(v3);
    v4 = 0;
  }
LABEL_31:
  if ( v52 )
    WxHeapFree<_HK_PAIR>(&v52);
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_d(1050, 76, WPP_1eba17a514423a0ebe5ee43bce786d1b_Traceguids, v22);
  if ( v4 && v3 )
    LeaveCriticalSection(v3);
  return v22;
}

```

## disassembly

```asm
0x18002a250  mov     [rsp+arg_8], rbx
0x18002a255  push    rbp
0x18002a256  push    rsi
0x18002a257  push    rdi
0x18002a258  push    r12
0x18002a25a  push    r13
0x18002a25c  push    r14
0x18002a25e  push    r15
0x18002a260  sub     rsp, 70h
0x18002a264  xor     r13d, r13d
0x18002a267  lea     rsi, [rcx+8]
0x18002a26b  mov     [rsp+0A8h+var_54], r13d
0x18002a270  mov     ebp, r13d
0x18002a273  mov     [rsp+0A8h+var_40], r13
0x18002a278  mov     r14d, r8d
0x18002a27b  mov     [rsp+0A8h+var_48], rsi
0x18002a280  mov     eax, edx
0x18002a282  mov     [rsp+0A8h+var_64], r13d
0x18002a287  mov     rbx, rcx
0x18002a28a  mov     [rsp+0A8h+var_50], r13
0x18002a28f  mov     [rsp+0A8h+var_60], r13d
0x18002a294  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18002a29b  jnz     loc_18002A813
0x18002a2a1  lea     r12, [rbx+0A0h]
0x18002a2a8  mov     r15d, 13Dh
0x18002a2ae  test    r14d, r14d
0x18002a2b1  jnz     loc_18002A82E
0x18002a2b7  test    rsi, rsi
0x18002a2ba  jz      short loc_18002A2D8
0x18002a2bc  test    ebp, ebp
0x18002a2be  jnz     short loc_18002A2D8
0x18002a2c0  mov     rcx, rsi; lpCriticalSection
0x18002a2c3  call    cs:__imp_EnterCriticalSection
0x18002a2ca  nop     dword ptr [rax+rax+00h]
0x18002a2cf  mov     ebp, 1
0x18002a2d4  mov     dword ptr [rsp+0A8h+var_40], ebp
0x18002a2d8  call    cs:__imp_GetTickCount
0x18002a2df  nop     dword ptr [rax+rax+00h]
0x18002a2e4  cmp     dword ptr [rbx+98h], 0
0x18002a2eb  mov     [rbx+0ECh], eax
0x18002a2f1  mov     [rsp+0A8h+var_54], r13d
0x18002a2f6  jnz     loc_18002A7EF
0x18002a2fc  mov     edi, r13d
0x18002a2ff  mov     eax, edi
0x18002a301  and     eax, 1FFF0000h
0x18002a306  cmp     eax, 0C0000h
0x18002a30b  jz      loc_18002A890
0x18002a311  test    edi, edi
0x18002a313  js      loc_18002A69A
0x18002a319  mov     r14d, r13d
0x18002a31c  cmp     qword ptr [rbx+0C0h], 0
0x18002a324  jz      loc_18002A433
0x18002a32a  mov     r13d, r14d
0x18002a32d  test    r14d, r14d
0x18002a330  jz      loc_18002A6B5
0x18002a336  mov     r8, [rbx+0C0h]
0x18002a33d  xor     ecx, ecx; this
0x18002a33f  mov     rdx, [r8+40h]
0x18002a343  test    rdx, rdx
0x18002a346  lea     r15, [rdx+20h]
0x18002a34a  cmovz   r15, rcx
0x18002a34e  test    r13d, r13d
0x18002a351  jz      loc_18002A631
0x18002a357  mov     rax, [rbx+0C0h]
0x18002a35e  mov     ecx, [rax+88h]
0x18002a364  mov     [rsp+0A8h+var_58], ecx
0x18002a368  mov     dword ptr [rax+88h], 0
0x18002a372  test    r15, r15
0x18002a375  jz      short loc_18002A38C
0x18002a377  mov     rax, [rbx+0C0h]
0x18002a37e  cmp     [r15+28h], rax
0x18002a382  jnz     short loc_18002A38C
0x18002a384  mov     qword ptr [r15+28h], 0
0x18002a38c  mov     rax, [rbx+0C0h]
0x18002a393  mov     ecx, [rax+4]
0x18002a396  dec     ecx
0x18002a398  cmp     ecx, 1
0x18002a39b  jbe     loc_18002A6CE
0x18002a3a1  mov     rdi, [rbx+0C0h]
0x18002a3a8  mov     eax, [rdi+4]
0x18002a3ab  dec     eax
0x18002a3ad  cmp     eax, 1
0x18002a3b0  ja      short loc_18002A404
0x18002a3b2  lea     rcx, [rdi+18h]; SRWLock
0x18002a3b6  call    cs:__imp_AcquireSRWLockExclusive
0x18002a3bd  nop     dword ptr [rax+rax+00h]
0x18002a3c2  cmp     dword ptr [rdi+90h], 0
0x18002a3c9  lea     rcx, [rdi+18h]; SRWLock
0x18002a3cd  jnz     loc_18002A7D5
0x18002a3d3  mov     dword ptr [rdi+90h], 1
0x18002a3dd  call    cs:__imp_ReleaseSRWLockExclusive
0x18002a3e4  nop     dword ptr [rax+rax+00h]
0x18002a3e9  mov     [rdi+30h], r13d
0x18002a3ed  lock inc dword ptr [rdi]
0x18002a3f0  mov     rcx, [rdi+38h]
0x18002a3f4  mov     rcx, [rcx+8]; pwk
0x18002a3f8  call    cs:__imp_SubmitThreadpoolWork
0x18002a3ff  nop     dword ptr [rax+rax+00h]
0x18002a404  mov     rdi, [rbx+0C0h]
0x18002a40b  mov     eax, 0FFFFFFFFh
0x18002a410  lock xadd [rdi], eax
0x18002a414  cmp     eax, 1
0x18002a417  jz      loc_18002A677
0x18002a41d  mov     edx, [rsp+0A8h+var_58]; unsigned int
0x18002a421  xor     r13d, r13d
0x18002a424  mov     [rbx+0C0h], r13
0x18002a42b  test    edx, edx
0x18002a42d  jnz     loc_18002A949
0x18002a433  mov     rax, [r12]
0x18002a437  cmp     rax, r12
0x18002a43a  jnz     short loc_18002A4B5
0x18002a43c  mov     rcx, rbx; this
0x18002a43f  mov     [rbx+0C8h], r13d
0x18002a446  call    ?StartPingTimer@CHttp2@@AEAAXXZ; CHttp2::StartPingTimer(void)
0x18002a44b  mov     ebx, r13d
0x18002a44e  test    rsi, rsi
0x18002a451  jz      short loc_18002A469
0x18002a453  test    ebp, ebp
0x18002a455  jz      short loc_18002A469
0x18002a457  mov     rcx, rsi; lpCriticalSection
0x18002a45a  call    cs:__imp_LeaveCriticalSection
0x18002a461  nop     dword ptr [rax+rax+00h]
0x18002a466  mov     ebp, r13d
0x18002a469  cmp     [rsp+0A8h+var_50], 0
0x18002a46f  jnz     loc_18002A97B
0x18002a475  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18002a47c  jnz     loc_18002A98A
0x18002a482  test    ebp, ebp
0x18002a484  jz      short loc_18002A49A
0x18002a486  test    rsi, rsi
0x18002a489  jz      short loc_18002A49A
0x18002a48b  mov     rcx, rsi; lpCriticalSection
0x18002a48e  call    cs:__imp_LeaveCriticalSection
0x18002a495  nop     dword ptr [rax+rax+00h]
0x18002a49a  mov     eax, ebx
0x18002a49c  mov     rbx, [rsp+0A8h+arg_8]
0x18002a4a4  add     rsp, 70h
0x18002a4a8  pop     r15
0x18002a4aa  pop     r14
0x18002a4ac  pop     r13
0x18002a4ae  pop     r12
0x18002a4b0  pop     rdi
0x18002a4b1  pop     rsi
0x18002a4b2  pop     rbp
0x18002a4b3  retn
0x18002a4b5  cmp     [rax+8], r12
0x18002a4b9  jnz     loc_18002A7CE
0x18002a4bf  mov     rcx, [rax]
0x18002a4c2  cmp     [rcx+8], rax
0x18002a4c6  jnz     loc_18002A7CE
0x18002a4cc  mov     [r12], rcx
0x18002a4d0  mov     [rcx+8], r12
0x18002a4d4  mov     rcx, rbx; this
0x18002a4d7  mov     [rax+8], rax
0x18002a4db  mov     [rax], rax
0x18002a4de  add     rax, 0FFFFFFFFFFFFFFF8h
0x18002a4e2  mov     [rbx+0C0h], rax
0x18002a4e9  call    ?GetAvailableSendWindow@CHttp2@@AEAAHXZ; CHttp2::GetAvailableSendWindow(void)
0x18002a4ee  cmp     qword ptr [rbx+0C0h], 0
0x18002a4f6  jz      loc_18002A433
0x18002a4fc  mov     ecx, [rbx+198h]
0x18002a502  test    ecx, ecx
0x18002a504  jnz     loc_18002A755
0x18002a50a  mov     edi, [rsp+0A8h+var_60]
0x18002a50e  test    rsi, rsi
0x18002a511  jz      short loc_18002A52E
0x18002a513  test    ebp, ebp
0x18002a515  jz      short loc_18002A52E
0x18002a517  mov     rcx, rsi; lpCriticalSection
0x18002a51a  call    cs:__imp_LeaveCriticalSection
0x18002a521  nop     dword ptr [rax+rax+00h]
0x18002a526  mov     ebp, r13d
0x18002a529  mov     dword ptr [rsp+0A8h+var_40], r13d
0x18002a52e  test    edi, edi
0x18002a530  jnz     loc_18002A77A
0x18002a536  mov     rdx, [rbx+0C0h]; struct CHttp2SendContext *
0x18002a53d  mov     [rsp+0A8h+var_64], r13d
0x18002a542  mov     eax, [rdx+4]
0x18002a545  cmp     eax, 1
0x18002a548  jz      short loc_18002A56F
0x18002a54a  cmp     eax, 2
0x18002a54d  jnz     short loc_18002A591
0x18002a54f  lea     r8, [rsp+0A8h+var_64]; int *
0x18002a554  mov     rcx, rbx; this
0x18002a557  call    ?FrameData@CHttp2@@AEAAJPEAVCHttp2SendContext@@PEAJ@Z; CHttp2::FrameData(CHttp2SendContext *,long *)
0x18002a55c  test    eax, eax
0x18002a55e  jns     short loc_18002A580
0x18002a560  mov     ecx, eax
0x18002a562  call    WX_WIN32_FROM_HR
0x18002a567  mov     r14d, eax
0x18002a56a  jmp     loc_18002A2A8
0x18002a56f  lea     r8, [rsp+0A8h+var_64]; int *
0x18002a574  mov     rcx, rbx; this
0x18002a577  call    ?OpenStream@CHttp2@@AEAAJPEAVCHttp2SendContext@@PEAJ@Z; CHttp2::OpenStream(CHttp2SendContext *,long *)
0x18002a57c  test    eax, eax
0x18002a57e  js      short loc_18002A560
0x18002a580  cmp     [rsp+0A8h+var_64], 0
0x18002a585  mov     r15d, 13Dh
0x18002a58b  jl      loc_18002A2AE
0x18002a591  mov     rcx, rbx; this
0x18002a594  call    ?StopPingTimer@CHttp2@@AEAAXXZ; CHttp2::StopPingTimer(void)
0x18002a599  lock inc dword ptr [rbx]
0x18002a59c  mov     rax, [rbx+0C0h]
0x18002a5a3  mov     rdi, [rbx+30h]
0x18002a5a7  mov     edx, [rax+80h]
0x18002a5ad  mov     rcx, [rax+78h]
0x18002a5b1  lea     rax, ?SendCompletion@CHttp2@@CAXPEAXKK@Z; CHttp2::SendCompletion(void *,ulong,ulong)
0x18002a5b8  mov     [rdi+98h], rax
0x18002a5bf  mov     [rdi+80h], r13d
0x18002a5c6  mov     [rdi+88h], rcx
0x18002a5cd  mov     [rdi+90h], rdx
0x18002a5d4  mov     [rdi+0A0h], rbx
0x18002a5db  lock inc dword ptr [rdi+4]
0x18002a5df  mov     rcx, [rdi+48h]
0x18002a5e3  lea     rdx, WapHttp2ConnectionSendCompletion
0x18002a5ea  mov     [rsp+0A8h+var_80], rdi
0x18002a5ef  xor     r9d, r9d
0x18002a5f2  mov     [rsp+0A8h+var_88], rdx
0x18002a5f7  mov     r8d, 1
0x18002a5fd  lea     rdx, [rdi+80h]
0x18002a604  mov     rax, [rcx+50h]
0x18002a608  mov     rcx, [rcx+40h]
0x18002a60c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a611  mov     r14d, eax
0x18002a614  cmp     eax, 3E5h
0x18002a619  jnz     loc_18002A84B
0x18002a61f  mov     ebx, 800703E5h
0x18002a624  mov     [rsp+0A8h+var_54], 0B7Ch
0x18002a62c  jmp     loc_18002A469
0x18002a631  cmp     dword ptr [r8+4], 2
0x18002a636  jnz     loc_18002A357
0x18002a63c  cmp     [r8+70h], ecx
0x18002a640  jz      loc_18002A357
0x18002a646  cmp     dword ptr [r15+10h], 3
0x18002a64b  jnz     loc_18002A802
0x18002a651  mov     rdx, r15; struct _HTTP2_STREAM_LINKAGE *
0x18002a654  call    ?ResetSendTimer@CHttp2@@AEAAXPEAU_HTTP2_STREAM_LINKAGE@@@Z; CHttp2::ResetSendTimer(_HTTP2_STREAM_LINKAGE *)
0x18002a659  mov     rdx, [rbx+0C0h]; struct CHttp2SendContext *
0x18002a660  mov     rcx, rbx; this
0x18002a663  call    ?InsertSendContext@CHttp2@@AEAAXPEAVCHttp2SendContext@@@Z; CHttp2::InsertSendContext(CHttp2SendContext *)
0x18002a668  xor     r13d, r13d
0x18002a66b  mov     [rbx+0C0h], r13
0x18002a672  jmp     loc_18002A433
0x18002a677  test    rdi, rdi
0x18002a67a  jz      loc_18002A41D
0x18002a680  mov     rcx, rdi; this
0x18002a683  call    ??1CHttp2SendContext@@AEAA@XZ; CHttp2SendContext::~CHttp2SendContext(void)
0x18002a688  mov     edx, 98h
0x18002a68d  mov     rcx, rdi; Block
0x18002a690  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002a695  jmp     loc_18002A41D
0x18002a69a  cmp     eax, 70000h
0x18002a69f  jnz     loc_18002A899
0x18002a6a5  movzx   r14d, di
0x18002a6a9  test    r14d, r14d
0x18002a6ac  cmovz   r14d, r15d
0x18002a6b0  jmp     loc_18002A31C
0x18002a6b5  mov     ecx, [rsp+0A8h+var_64]
0x18002a6b9  test    ecx, ecx
0x18002a6bb  jns     loc_18002A336
0x18002a6c1  call    WX_WIN32_FROM_HR
0x18002a6c6  mov     r13d, eax
0x18002a6c9  jmp     loc_18002A336
0x18002a6ce  dec     dword ptr [r15+38h]
0x18002a6d2  lea     rdi, [r15-20h]
0x18002a6d6  cmp     dword ptr [r15+3Ch], 0
0x18002a6db  jz      short loc_18002A71C
0x18002a6dd  mov     rdi, [rdi+18h]
0x18002a6e1  lea     rcx, [rdi+68h]
0x18002a6e5  call    WaCancelTwTimer
0x18002a6ea  test    al, al
0x18002a6ec  jz      loc_18002A7E6
0x18002a6f2  mov     qword ptr [rdi+0A8h], 0
0x18002a6fd  mov     qword ptr [rdi+0B0h], 0
0x18002a708  lea     rdi, [r15-20h]
0x18002a70c  mov     rcx, rdi; this
0x18002a70f  mov     dword ptr [r15+3Ch], 0
0x18002a717  call    ?Release@CHttp2Stream@@QEAAKXZ; CHttp2Stream::Release(void)
0x18002a71c  mov     eax, [r15+10h]
0x18002a720  cmp     eax, 4
0x18002a723  jz      loc_18002A3A1
0x18002a729  cmp     dword ptr [r15+38h], 0
0x18002a72e  mov     [rsp+0A8h+var_68], 0
0x18002a736  mov     [rsp+0A8h+var_5C], 0
0x18002a73e  jnz     short loc_18002A79C
0x18002a740  mov     r8d, [rsp+0A8h+var_68]; unsigned int
0x18002a745  mov     r9d, r8d; unsigned int
0x18002a748  mov     rdx, r15; struct _HTTP2_STREAM_LINKAGE *
0x18002a74b  call    ?StartSendTimer@CHttp2@@AEAAXPEAU_HTTP2_STREAM_LINKAGE@@KK@Z; CHttp2::StartSendTimer(_HTTP2_STREAM_LINKAGE *,ulong,ulong)
0x18002a750  jmp     loc_18002A3A1
0x18002a755  mov     rax, [rbx+190h]
0x18002a75c  mov     edi, ecx
0x18002a75e  mov     [rsp+0A8h+var_50], rax
0x18002a763  mov     [rbx+190h], r13
0x18002a76a  mov     [rsp+0A8h+var_60], ecx
0x18002a76e  mov     [rbx+198h], r13d
0x18002a775  jmp     loc_18002A50E
0x18002a77a  mov     r8d, edi; unsigned int
0x18002a77d  lea     rdx, [rsp+0A8h+var_50]; unsigned int **
0x18002a782  mov     rcx, rbx; this
  ... truncated ...
```
