# PostReceiveOnCall

- ea: `0x180002320`
- end: `0x180002aa5`
- name: `PostReceiveOnCall`
- size: `1925`
- prototype: ``
- caller_count: `5`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180001fe0`
- `0x180002320`
- `0x18000afb0`
- `0x18000b9c8`
- `0x18000ebd0`

## callees

- `0x180002320`
- `0x180002aac`
- `0x180002f50`
- `0x180002f80`
- `0x1800071cc`
- `0x1800075a0`
- `0x180007f48`
- `0x1800089dc`
- `0x180008b90`
- `0x18001d1da`
- `0x18001d210`
- `0x18001d2a0`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000238b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800023da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002575`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002680`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800026d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000291f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000238b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800023da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002575`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002680`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800026d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000291f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000241c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002458`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800025e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002706`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800027ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000241c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002458`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800025e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002706`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800027ba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180002515`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180002515`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180002535`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180002535`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800028a8`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800028a8`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180002842`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180002842`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800025d0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800025d0`
- `HTTPAPI!HttpReceiveRequestEntityBody` at `0x180002878`
- `HTTPAPI!HttpReceiveRequestEntityBody` at `0x180002878`
- `webio!__imp_WebReceiveHttpResponseEntity` at `0x1800024b7`
- `webio!__imp_WebReceiveHttpResponseEntity` at `0x1800024b7`

## string_xrefs

- `0x18000276c`: `CoId=%hs:Disconnect already in progress`

## pseudocode

```c
void __fastcall PostReceiveOnCall(__int64 a1)
{
  __int64 Overlapped; // rbx
  char *v3; // r14
  char *v4; // rbx
  _QWORD *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned int v9; // edi
  __int64 v10; // rsi
  RTL_SRWLOCK *v11; // rcx
  int v12; // edi
  __int64 v13; // rdi
  __int64 v14; // r8
  _QWORD *v15; // rax
  _QWORD *v16; // rbx
  char *v17; // rdi
  __int64 v18; // rax
  ULONG v19; // eax
  ULONG v20; // r15d
  __int64 v21; // r8
  __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  char v24[2044]; // [rsp+54h] [rbp-ACh] BYREF
  int v25; // [rsp+850h] [rbp+750h] BYREF
  char v26[2044]; // [rsp+854h] [rbp+754h] BYREF
  int v27; // [rsp+1050h] [rbp+F50h] BYREF
  char v28[2044]; // [rsp+1054h] [rbp+F54h] BYREF

  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v23) = 0;
    FormatRRASErrorString(&v23, L"Entering %ws", L"PostReceiveOnCall");
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v23);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
  if ( *(_BYTE *)(a1 + 435) )
  {
    if ( (byte_18002E903 & 0x10) != 0 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"CoId=%hs:Disconnect already in progress", a1 + 552);
      if ( (byte_18002E903 & 0x10) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v23);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
  }
  else
  {
    Overlapped = *(_QWORD *)(a1 + 256);
    if ( Overlapped )
    {
      *(_QWORD *)(a1 + 256) = 0;
      goto LABEL_7;
    }
    v3 = (char *)SstpSvcGlobals;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)SstpSvcGlobals + 488));
    v4 = (char *)*((_QWORD *)v3 + 58);
    if ( v4 == v3 + 464 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 488));
      Overlapped = AddBufferBlockToPool(v3 + 424);
    }
    else
    {
      v5 = (_QWORD *)*((_QWORD *)v4 + 1);
      v6 = *(_QWORD *)v4;
      *v5 = *(_QWORD *)v4;
      *(_QWORD *)(v6 + 8) = v5;
      v7 = *((_QWORD *)v4 + 2);
      *((_QWORD *)v4 + 1) = v4;
      *(_QWORD *)v4 = v4;
      --*(_DWORD *)(v7 + 28);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 488));
      Overlapped = (__int64)(v4 + 24);
    }
    if ( Overlapped )
    {
LABEL_7:
      *(_OWORD *)Overlapped = 0;
      *(_OWORD *)(Overlapped + 16) = 0;
      *(_DWORD *)(Overlapped + 32) = 17776;
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 208));
      *(_QWORD *)(Overlapped + 56) = a1;
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
      if ( *(_BYTE *)(a1 + 248) )
      {
        *(_DWORD *)(Overlapped + 64) = 0;
        *(_QWORD *)(Overlapped + 72) = Overlapped + 96;
        *(_QWORD *)(Overlapped + 80) = 0x4000;
        v8 = *(_QWORD *)(a1 + 448);
        v22 = 0;
        v9 = WebReceiveHttpResponseEntity(
               v8,
               0,
               Overlapped + 64,
               1,
               &v22,
               SstpWebReceiveResponseEntityCompletion,
               Overlapped);
        if ( v9 != 997 )
        {
          v10 = *(_QWORD *)(Overlapped + 56);
          v25 = 0;
          memset_0(v26, 0, sizeof(v26));
          if ( v9 )
          {
            if ( (byte_18002E903 & 8) != 0 )
            {
              LOWORD(v25) = 0;
              FormatRRASErrorString(&v25, L"CoId=%hs:ReceiveResponseEntity fails with %d", v10 + 552, v9);
              if ( (byte_18002E903 & 8) != 0 )
                McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v25);
            }
            v16 = (_QWORD *)(Overlapped - 24);
            v17 = (char *)SstpSvcGlobals + 424;
            EnterCriticalSection((LPCRITICAL_SECTION)((char *)SstpSvcGlobals + 488));
            if ( (_QWORD *)*v16 == v16 )
            {
              v18 = *((_QWORD *)v17 + 5);
              *v16 = v18;
              v16[1] = v17 + 40;
              *(_QWORD *)(v18 + 8) = v16;
              *((_QWORD *)v17 + 5) = v16;
              ++*(_DWORD *)(v16[2] + 28LL);
              if ( ++*((_DWORD *)v17 + 5) >= *((_DWORD *)v17 + 4) )
              {
                FreeUnusedBufferPoolBlocks(v17);
                *((_DWORD *)v17 + 5) = 0;
              }
            }
            else
            {
              ++g_ulDoubleBufferFrees;
            }
            LeaveCriticalSection((LPCRITICAL_SECTION)(v17 + 64));
            EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 288));
            InitiateCallContextCleanup(v10, 1);
          }
          else
          {
            v11 = (RTL_SRWLOCK *)SstpSvcGlobals;
            *(_DWORD *)(Overlapped + 92) = v22;
            *(_DWORD *)(Overlapped + 88) = *(_DWORD *)(v10 + 240);
            AcquireSRWLockShared(v11 + 96);
            v12 = *((_DWORD *)SstpSvcGlobals + 194);
            ReleaseSRWLockShared((PSRWLOCK)SstpSvcGlobals + 96);
            if ( (v12 & 1) != 0 && v10 && *(_QWORD *)(v10 + 624) )
            {
              ProxySendToRelatedCtx((LPOVERLAPPED)Overlapped);
            }
            else
            {
              v27 = 0;
              memset_0(v28, 0, sizeof(v28));
              v13 = *(_QWORD *)(Overlapped + 56);
              *(_QWORD *)(Overlapped + 56) = 0;
              EnterCriticalSection((LPCRITICAL_SECTION)(v13 + 288));
              if ( *(_BYTE *)(v13 + 435) )
              {
                if ( (byte_18002E903 & 8) != 0 )
                {
                  LOWORD(v27) = 0;
                  FormatRRASErrorString(&v27, L"CoId=%hs:Dropping packet since disconnect in progress", v13 + 552);
                  if ( (byte_18002E903 & 8) != 0 )
                    McTemplateU0z_EventWriteTransfer(
                      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      RasSSTPSvcTraceError,
                      &v27);
                }
                LOBYTE(v14) = 1;
                FreeBufferToPool((char *)SstpSvcGlobals + 424, Overlapped, v14);
              }
              else
              {
                *(_QWORD *)(Overlapped + 48) = Overlapped + 40;
                *(_QWORD *)(Overlapped + 40) = Overlapped + 40;
                v15 = *(_QWORD **)(v13 + 424);
                *(_QWORD *)(Overlapped + 40) = v13 + 416;
                *(_QWORD *)(Overlapped + 48) = v15;
                *v15 = Overlapped + 40;
                *(_QWORD *)(v13 + 424) = Overlapped + 40;
                if ( !*(_BYTE *)(v13 + 432) )
                {
                  *(_BYTE *)(v13 + 432) = 1;
                  _InterlockedIncrement((volatile signed __int32 *)(v13 + 208));
                  SubmitThreadpoolWork(*(PTP_WORK *)(v13 + 336));
                }
              }
              LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 288));
            }
            PostReceiveOnCall(v10);
          }
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v10 + 208), 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(__int64))(v10 + 216))(v10 + 208);
        }
      }
      else
      {
        StartThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 21));
        v19 = HttpReceiveRequestEntityBody(
                *((HANDLE *)SstpSvcGlobals + 8),
                *(_QWORD *)(a1 + 272),
                0,
                (PVOID)(Overlapped + 96),
                0x4000u,
                0,
                (LPOVERLAPPED)Overlapped);
        v20 = v19;
        if ( v19 != 997 && v19 )
        {
          CancelThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 21));
          if ( (byte_18002E903 & 8) != 0 )
          {
            LOWORD(v23) = 0;
            FormatRRASErrorString(&v23, L"CoId=%hs:ReceiveEntityBody fails with %d", a1 + 552, v20);
            if ( (byte_18002E903 & 8) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v23);
          }
          LOBYTE(v21) = 1;
          FreeBufferToPool((char *)SstpSvcGlobals + 424, Overlapped, v21);
          EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
          InitiateCallContextCleanup(a1, 1);
          DereferenceRefCount(a1 + 208);
        }
      }
      goto LABEL_18;
    }
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"CoId=%hs:Unable to allocate buffer for receive", a1 + 552);
      if ( (byte_18002E903 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v23);
    }
    InitiateCallContextCleanup(a1, 2);
  }
LABEL_18:
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v23) = 0;
    FormatRRASErrorString(&v23, L"LEaving %ws", L"PostReceiveOnCall");
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v23);
  }
}

```

## disassembly

```asm
0x180002320  push    rbp
0x180002322  push    r12
0x180002324  lea     rbp, [rsp-1778h]
0x18000232c  mov     eax, 1878h
0x180002331  call    _alloca_probe
0x180002336  sub     rsp, rax
0x180002339  mov     rax, cs:__security_cookie
0x180002340  xor     rax, rsp
0x180002343  mov     [rbp+1780h+var_30], rax
0x18000234a  mov     [rsp+1880h+arg_10], rsi
0x180002352  xor     r12d, r12d
0x180002355  mov     [rsp+1880h+var_10], rdi
0x18000235d  xor     edx, edx; Val
0x18000235f  mov     rdi, rcx
0x180002362  mov     [rsp+1880h+var_1830], r12d
0x180002367  lea     rcx, [rsp+1880h+var_182C]; void *
0x18000236c  mov     r8d, 7FCh; Size
0x180002372  call    memset_0
0x180002377  test    cs:byte_18002E903, 10h
0x18000237e  jnz     loc_180002717
0x180002384  lea     rcx, [rdi+120h]; lpCriticalSection
0x18000238b  call    cs:__imp_EnterCriticalSection
0x180002392  nop     dword ptr [rax+rax+00h]
0x180002397  cmp     [rdi+1B3h], r12b
0x18000239e  jnz     loc_1800026F6
0x1800023a4  mov     [rsp+1880h+arg_8], rbx
0x1800023ac  mov     rbx, [rdi+100h]
0x1800023b3  mov     [rsp+1880h+var_18], r14
0x1800023bb  mov     [rsp+1880h+var_20], r15
0x1800023c3  test    rbx, rbx
0x1800023c6  jnz     loc_1800027A7
0x1800023cc  mov     r14, cs:SstpSvcGlobals
0x1800023d3  lea     rcx, [r14+1E8h]; lpCriticalSection
0x1800023da  call    cs:__imp_EnterCriticalSection
0x1800023e1  nop     dword ptr [rax+rax+00h]
0x1800023e6  lea     rax, [r14+1D0h]
0x1800023ed  mov     rbx, [rax]
0x1800023f0  cmp     rbx, rax
0x1800023f3  jz      loc_1800027B3
0x1800023f9  mov     rax, [rbx+8]
0x1800023fd  mov     rcx, [rbx]
0x180002400  mov     [rax], rcx
0x180002403  mov     [rcx+8], rax
0x180002407  lea     rcx, [r14+1E8h]; lpCriticalSection
0x18000240e  mov     rax, [rbx+10h]
0x180002412  mov     [rbx+8], rbx
0x180002416  mov     [rbx], rbx
0x180002419  dec     dword ptr [rax+1Ch]
0x18000241c  call    cs:__imp_LeaveCriticalSection
0x180002423  nop     dword ptr [rax+rax+00h]
0x180002428  add     rbx, 18h
0x18000242c  test    rbx, rbx
0x18000242f  jz      loc_1800027DA
0x180002435  xorps   xmm0, xmm0
0x180002438  movups  xmmword ptr [rbx], xmm0
0x18000243b  movups  xmmword ptr [rbx+10h], xmm0
0x18000243f  mov     dword ptr [rbx+20h], 4570h
0x180002446  lock inc dword ptr [rdi+0D0h]
0x18000244d  lea     rcx, [rdi+120h]; lpCriticalSection
0x180002454  mov     [rbx+38h], rdi
0x180002458  call    cs:__imp_LeaveCriticalSection
0x18000245f  nop     dword ptr [rax+rax+00h]
0x180002464  lea     r15, [rbx+60h]
0x180002468  cmp     [rdi+0F8h], r12b
0x18000246f  jz      loc_180002834
0x180002475  lea     r8, [rbx+40h]
0x180002479  mov     [rsp+1880h+Overlapped], rbx
0x18000247e  lea     rax, SstpWebReceiveResponseEntityCompletion
0x180002485  mov     [r8], r12d
0x180002488  mov     [rsp+1880h+BytesReturned], rax
0x18000248d  xor     edx, edx
0x18000248f  lea     rax, [rsp+1880h+var_1840]
0x180002494  mov     [r8+8], r15
0x180002498  mov     qword ptr [r8+10h], 4000h
0x1800024a0  mov     r9d, 1
0x1800024a6  mov     rcx, [rdi+1C0h]
0x1800024ad  mov     qword ptr [rsp+1880h+EntityBufferLength], rax
0x1800024b2  mov     [rsp+1880h+var_1840], r12
0x1800024b7  call    cs:__imp_WebReceiveHttpResponseEntity
0x1800024be  nop     dword ptr [rax+rax+00h]
0x1800024c3  mov     edi, eax
0x1800024c5  cmp     eax, 3E5h
0x1800024ca  jz      loc_18000260D
0x1800024d0  mov     rsi, [rbx+38h]
0x1800024d4  lea     rcx, [rbp+1780h+var_102C]; void *
0x1800024db  xor     edx, edx; Val
0x1800024dd  mov     [rbp+1780h+var_1030], r12d
0x1800024e4  mov     r8d, 7FCh; Size
0x1800024ea  call    memset_0
0x1800024ef  test    edi, edi
0x1800024f1  jnz     loc_18000265D
0x1800024f7  mov     eax, dword ptr [rsp+1880h+var_1840]
0x1800024fb  mov     rcx, cs:SstpSvcGlobals
0x180002502  mov     [rbx+5Ch], eax
0x180002505  add     rcx, 300h; SRWLock
0x18000250c  mov     eax, [rsi+0F0h]
0x180002512  mov     [rbx+58h], eax
0x180002515  call    cs:__imp_AcquireSRWLockShared
0x18000251c  nop     dword ptr [rax+rax+00h]
0x180002521  mov     rcx, cs:SstpSvcGlobals
0x180002528  mov     edi, [rcx+308h]
0x18000252e  add     rcx, 300h; SRWLock
0x180002535  call    cs:__imp_ReleaseSRWLockShared
0x18000253c  nop     dword ptr [rax+rax+00h]
0x180002541  bt      edi, 0
0x180002545  jb      loc_1800029B6
0x18000254b  xor     edx, edx; Val
0x18000254d  mov     [rbp+1780h+var_830], r12d
0x180002554  mov     r8d, 7FCh; Size
0x18000255a  lea     rcx, [rbp+1780h+var_82C]; void *
0x180002561  call    memset_0
0x180002566  mov     rdi, [rbx+38h]
0x18000256a  mov     [rbx+38h], r12
0x18000256e  lea     rcx, [rdi+120h]; lpCriticalSection
0x180002575  call    cs:__imp_EnterCriticalSection
0x18000257c  nop     dword ptr [rax+rax+00h]
0x180002581  cmp     [rdi+1B3h], r12b
0x180002588  jnz     loc_1800029D9
0x18000258e  lea     r8, [rbx+28h]
0x180002592  mov     [rbx+30h], r8
0x180002596  lea     rdx, [rdi+1A0h]
0x18000259d  mov     [r8], r8
0x1800025a0  mov     rax, [rdx+8]
0x1800025a4  mov     [r8], rdx
0x1800025a7  mov     [rbx+30h], rax
0x1800025ab  mov     [rax], r8
0x1800025ae  mov     [rdx+8], r8
0x1800025b2  cmp     [rdi+1B0h], r12b
0x1800025b9  jnz     short loc_1800025DC
0x1800025bb  mov     byte ptr [rdi+1B0h], 1
0x1800025c2  lock inc dword ptr [rdi+0D0h]
0x1800025c9  mov     rcx, [rdi+150h]; pwk
0x1800025d0  call    cs:__imp_SubmitThreadpoolWork
0x1800025d7  nop     dword ptr [rax+rax+00h]
0x1800025dc  lea     rcx, [rdi+120h]; lpCriticalSection
0x1800025e3  call    cs:__imp_LeaveCriticalSection
0x1800025ea  nop     dword ptr [rax+rax+00h]
0x1800025ef  mov     rcx, rsi
0x1800025f2  call    PostReceiveOnCall
0x1800025f7  mov     eax, 0FFFFFFFFh
0x1800025fc  lock xadd [rsi+0D0h], eax
0x180002604  cmp     eax, 1
0x180002607  jz      loc_180002A45
0x18000260d  mov     r14, [rsp+1880h+var_18]
0x180002615  mov     rbx, [rsp+1880h+arg_8]
0x18000261d  mov     r15, [rsp+1880h+var_20]
0x180002625  test    cs:byte_18002E903, 10h
0x18000262c  mov     rdi, [rsp+1880h+var_10]
0x180002634  mov     rsi, [rsp+1880h+arg_10]
0x18000263c  jnz     loc_180002A5D
0x180002642  mov     rcx, [rbp+1780h+var_30]
0x180002649  xor     rcx, rsp; StackCookie
0x18000264c  call    __security_check_cookie
0x180002651  add     rsp, 1878h
0x180002658  pop     r12
0x18000265a  pop     rbp
0x18000265b  retn
0x18000265d  test    cs:byte_18002E903, 8
0x180002664  jnz     loc_180002949
0x18000266a  mov     rdi, cs:SstpSvcGlobals
0x180002671  add     rbx, 0FFFFFFFFFFFFFFE8h
0x180002675  add     rdi, 1A8h
0x18000267c  lea     rcx, [rdi+40h]; lpCriticalSection
0x180002680  call    cs:__imp_EnterCriticalSection
0x180002687  nop     dword ptr [rax+rax+00h]
0x18000268c  cmp     [rbx], rbx
0x18000268f  jnz     loc_18000299A
0x180002695  mov     rax, [rdi+28h]
0x180002699  lea     rcx, [rdi+28h]
0x18000269d  mov     [rbx], rax
0x1800026a0  mov     [rbx+8], rcx
0x1800026a4  mov     [rax+8], rbx
0x1800026a8  mov     [rcx], rbx
0x1800026ab  mov     rax, [rbx+10h]
0x1800026af  inc     dword ptr [rax+1Ch]
0x1800026b2  inc     dword ptr [rdi+14h]
0x1800026b5  mov     eax, [rdi+14h]
0x1800026b8  cmp     eax, [rdi+10h]
0x1800026bb  jnb     loc_1800029A5
0x1800026c1  lea     rcx, [rdi+40h]; lpCriticalSection
0x1800026c5  call    cs:__imp_LeaveCriticalSection
0x1800026cc  nop     dword ptr [rax+rax+00h]
0x1800026d1  lea     rcx, [rsi+120h]; lpCriticalSection
0x1800026d8  call    cs:__imp_EnterCriticalSection
0x1800026df  nop     dword ptr [rax+rax+00h]
0x1800026e4  mov     edx, 1
0x1800026e9  mov     rcx, rsi
0x1800026ec  call    InitiateCallContextCleanup
0x1800026f1  jmp     loc_1800025F7
0x1800026f6  test    cs:byte_18002E903, 10h
0x1800026fd  jnz     short loc_18000275F
0x1800026ff  lea     rcx, [rdi+120h]; lpCriticalSection
0x180002706  call    cs:__imp_LeaveCriticalSection
0x18000270d  nop     dword ptr [rax+rax+00h]
0x180002712  jmp     loc_180002625
0x180002717  lea     r8, aPostreceiveonc; "PostReceiveOnCall"
0x18000271e  mov     word ptr [rsp+1880h+var_1830], r12w
0x180002724  lea     rdx, aEnteringWs; "Entering %ws"
0x18000272b  lea     rcx, [rsp+1880h+var_1830]
0x180002730  call    FormatRRASErrorString
0x180002735  test    cs:byte_18002E903, 10h
0x18000273c  jz      loc_180002384
0x180002742  lea     r8, [rsp+1880h+var_1830]
0x180002747  lea     rdx, RasSSTPSvcTraceInfo
0x18000274e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002755  call    McTemplateU0z_EventWriteTransfer
0x18000275a  jmp     loc_180002384
0x18000275f  lea     r8, [rdi+228h]
0x180002766  mov     word ptr [rsp+1880h+var_1830], r12w
0x18000276c  lea     rdx, aCoidHsDisconne; "CoId=%hs:Disconnect already in progress"
0x180002773  lea     rcx, [rsp+1880h+var_1830]
0x180002778  call    FormatRRASErrorString
0x18000277d  test    cs:byte_18002E903, 10h
0x180002784  jz      loc_1800026FF
0x18000278a  lea     r8, [rsp+1880h+var_1830]
0x18000278f  lea     rdx, RasSSTPSvcTraceInfo
0x180002796  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000279d  call    McTemplateU0z_EventWriteTransfer
0x1800027a2  jmp     loc_1800026FF
0x1800027a7  mov     [rdi+100h], r12
0x1800027ae  jmp     loc_180002435
0x1800027b3  lea     rcx, [r14+1E8h]; lpCriticalSection
0x1800027ba  call    cs:__imp_LeaveCriticalSection
0x1800027c1  nop     dword ptr [rax+rax+00h]
0x1800027c6  lea     rcx, [r14+1A8h]
0x1800027cd  call    AddBufferBlockToPool
0x1800027d2  mov     rbx, rax
0x1800027d5  jmp     loc_18000242C
0x1800027da  test    cs:byte_18002E903, 8
0x1800027e1  jz      short loc_180002822
0x1800027e3  lea     r8, [rdi+228h]
0x1800027ea  mov     word ptr [rsp+1880h+var_1830], r12w
0x1800027f0  lea     rdx, aCoidHsUnableTo_3; "CoId=%hs:Unable to allocate buffer for "...
0x1800027f7  lea     rcx, [rsp+1880h+var_1830]
0x1800027fc  call    FormatRRASErrorString
0x180002801  test    cs:byte_18002E903, 8
0x180002808  jz      short loc_180002822
0x18000280a  lea     r8, [rsp+1880h+var_1830]
0x18000280f  lea     rdx, RasSSTPSvcTraceError
0x180002816  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000281d  call    McTemplateU0z_EventWriteTransfer
0x180002822  mov     edx, 2
0x180002827  mov     rcx, rdi
0x18000282a  call    InitiateCallContextCleanup
0x18000282f  jmp     loc_18000260D
0x180002834  mov     rcx, cs:SstpSvcGlobals
0x18000283b  mov     rcx, [rcx+0A8h]; pio
0x180002842  call    cs:__imp_StartThreadpoolIo
0x180002849  nop     dword ptr [rax+rax+00h]
0x18000284e  mov     rcx, cs:SstpSvcGlobals
0x180002855  mov     r9, r15; EntityBuffer
0x180002858  mov     rdx, [rdi+110h]; RequestId
0x18000285f  xor     r8d, r8d; Flags
0x180002862  mov     [rsp+1880h+Overlapped], rbx; Overlapped
0x180002867  mov     [rsp+1880h+BytesReturned], r12; BytesReturned
0x18000286c  mov     rcx, [rcx+40h]; RequestQueueHandle
0x180002870  mov     [rsp+1880h+EntityBufferLength], 4000h; EntityBufferLength
0x180002878  call    cs:__imp_HttpReceiveRequestEntityBody
0x18000287f  nop     dword ptr [rax+rax+00h]
0x180002884  mov     r15d, eax
0x180002887  cmp     eax, 3E5h
0x18000288c  jz      loc_18000260D
0x180002892  test    eax, eax
0x180002894  jz      loc_18000260D
0x18000289a  mov     rcx, cs:SstpSvcGlobals
0x1800028a1  mov     rcx, [rcx+0A8h]; pio
0x1800028a8  call    cs:__imp_CancelThreadpoolIo
0x1800028af  nop     dword ptr [rax+rax+00h]
0x1800028b4  test    cs:byte_18002E903, 8
0x1800028bb  jz      short loc_1800028FF
0x1800028bd  lea     r8, [rdi+228h]
0x1800028c4  mov     word ptr [rsp+1880h+var_1830], r12w
0x1800028ca  mov     r9d, r15d
0x1800028cd  lea     rdx, aCoidHsReceivee; "CoId=%hs:ReceiveEntityBody fails with %"...
0x1800028d4  lea     rcx, [rsp+1880h+var_1830]
0x1800028d9  call    FormatRRASErrorString
0x1800028de  test    cs:byte_18002E903, 8
0x1800028e5  jz      short loc_1800028FF
0x1800028e7  lea     r8, [rsp+1880h+var_1830]
0x1800028ec  lea     rdx, RasSSTPSvcTraceError
0x1800028f3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800028fa  call    McTemplateU0z_EventWriteTransfer
0x1800028ff  mov     rcx, cs:SstpSvcGlobals
0x180002906  mov     r8b, 1
0x180002909  add     rcx, 1A8h
0x180002910  mov     rdx, rbx
0x180002913  call    FreeBufferToPool
0x180002918  lea     rcx, [rdi+120h]; lpCriticalSection
0x18000291f  call    cs:__imp_EnterCriticalSection
0x180002926  nop     dword ptr [rax+rax+00h]
0x18000292b  mov     edx, 1
0x180002930  mov     rcx, rdi
0x180002933  call    InitiateCallContextCleanup
0x180002938  lea     rcx, [rdi+0D0h]
0x18000293f  call    DereferenceRefCount
0x180002944  jmp     loc_18000260D
0x180002949  lea     r8, [rsi+228h]
0x180002950  mov     word ptr [rbp+1780h+var_1030], r12w
0x180002958  mov     r9d, edi
0x18000295b  lea     rdx, aCoidHsReceiver; "CoId=%hs:ReceiveResponseEntity fails wi"...
  ... truncated ...
```
