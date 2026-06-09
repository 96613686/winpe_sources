# PostReceiveOnCall

- ea: `0x1800021f0`
- end: `0x180002902`
- name: `PostReceiveOnCall`
- size: `1810`
- prototype: `void __fastcall(__int64)`
- caller_count: `5`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180001ee0`
- `0x1800021f0`
- `0x18000a620`
- `0x18000afbc`
- `0x18000df30`

## callees

- `0x1800021f0`
- `0x180002908`
- `0x180002d40`
- `0x180002d70`
- `0x180006b64`
- `0x180006ef0`
- `0x1800077bc`
- `0x18000827c`
- `0x180008360`
- `0x18001bcba`
- `0x18001bcf0`
- `0x18001bd80`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000225b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800022a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000241b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002513`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000255f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002782`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000225b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800022a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000241b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002513`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000255f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002782`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800022e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002316`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000247d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002552`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002587`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002635`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800022e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002316`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000247d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002552`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002587`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002635`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800023c7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800023c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800023e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800023e1`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180002711`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180002711`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800026b7`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800026b7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180002470`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180002470`
- `HTTPAPI!HttpReceiveRequestEntityBody` at `0x1800026e7`
- `HTTPAPI!HttpReceiveRequestEntityBody` at `0x1800026e7`
- `webio!__imp_WebReceiveHttpResponseEntity` at `0x18000236f`
- `webio!__imp_WebReceiveHttpResponseEntity` at `0x18000236f`

## string_xrefs

- `0x1800025e7`: `CoId=%hs:Disconnect already in progress`

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
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v23) = 0;
    FormatRRASErrorString(&v23, L"Entering %ws", L"PostReceiveOnCall");
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v23);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
  if ( *(_BYTE *)(a1 + 435) )
  {
    if ( (byte_18002D803 & 0x10) != 0 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"CoId=%hs:Disconnect already in progress", a1 + 552);
      if ( (byte_18002D803 & 0x10) != 0 )
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
            if ( (byte_18002D803 & 8) != 0 )
            {
              LOWORD(v25) = 0;
              FormatRRASErrorString(&v25, L"CoId=%hs:ReceiveResponseEntity fails with %d", v10 + 552, v9);
              if ( (byte_18002D803 & 8) != 0 )
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
                if ( (byte_18002D803 & 8) != 0 )
                {
                  LOWORD(v27) = 0;
                  FormatRRASErrorString(&v27, L"CoId=%hs:Dropping packet since disconnect in progress", v13 + 552);
                  if ( (byte_18002D803 & 8) != 0 )
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
          if ( (byte_18002D803 & 8) != 0 )
          {
            LOWORD(v23) = 0;
            FormatRRASErrorString(&v23, L"CoId=%hs:ReceiveEntityBody fails with %d", a1 + 552, v20);
            if ( (byte_18002D803 & 8) != 0 )
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
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"CoId=%hs:Unable to allocate buffer for receive", a1 + 552);
      if ( (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v23);
    }
    InitiateCallContextCleanup(a1, 2);
  }
LABEL_18:
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v23) = 0;
    FormatRRASErrorString(&v23, L"LEaving %ws", L"PostReceiveOnCall");
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v23);
  }
}

```

## disassembly

```asm
0x1800021f0  push    rbp
0x1800021f2  push    r12
0x1800021f4  lea     rbp, [rsp-1778h]
0x1800021fc  mov     eax, 1878h
0x180002201  call    _alloca_probe
0x180002206  sub     rsp, rax
0x180002209  mov     rax, cs:__security_cookie
0x180002210  xor     rax, rsp
0x180002213  mov     [rbp+1780h+var_30], rax
0x18000221a  mov     [rsp+1880h+arg_10], rsi
0x180002222  xor     r12d, r12d
0x180002225  mov     [rsp+1880h+var_10], rdi
0x18000222d  xor     edx, edx; Val
0x18000222f  mov     rdi, rcx
0x180002232  mov     [rsp+1880h+var_1830], r12d
0x180002237  lea     rcx, [rsp+1880h+var_182C]; void *
0x18000223c  mov     r8d, 7FCh; Size
0x180002242  call    memset_0
0x180002247  test    cs:byte_18002D803, 10h
0x18000224e  jnz     loc_180002592
0x180002254  lea     rcx, [rdi+120h]; lpCriticalSection
0x18000225b  call    cs:__imp_EnterCriticalSection
0x180002261  cmp     [rdi+1B3h], r12b
0x180002268  jnz     loc_180002577
0x18000226e  mov     [rsp+1880h+arg_8], rbx
0x180002276  mov     rbx, [rdi+100h]
0x18000227d  mov     [rsp+1880h+var_18], r14
0x180002285  mov     [rsp+1880h+var_20], r15
0x18000228d  test    rbx, rbx
0x180002290  jnz     loc_180002622
0x180002296  mov     r14, cs:SstpSvcGlobals
0x18000229d  lea     rcx, [r14+1E8h]; lpCriticalSection
0x1800022a4  call    cs:__imp_EnterCriticalSection
0x1800022aa  lea     rax, [r14+1D0h]
0x1800022b1  mov     rbx, [rax]
0x1800022b4  cmp     rbx, rax
0x1800022b7  jz      loc_18000262E
0x1800022bd  mov     rax, [rbx+8]
0x1800022c1  mov     rcx, [rbx]
0x1800022c4  mov     [rax], rcx
0x1800022c7  mov     [rcx+8], rax
0x1800022cb  lea     rcx, [r14+1E8h]; lpCriticalSection
0x1800022d2  mov     rax, [rbx+10h]
0x1800022d6  mov     [rbx+8], rbx
0x1800022da  mov     [rbx], rbx
0x1800022dd  dec     dword ptr [rax+1Ch]
0x1800022e0  call    cs:__imp_LeaveCriticalSection
0x1800022e6  add     rbx, 18h
0x1800022ea  test    rbx, rbx
0x1800022ed  jz      loc_18000264F
0x1800022f3  xorps   xmm0, xmm0
0x1800022f6  movups  xmmword ptr [rbx], xmm0
0x1800022f9  movups  xmmword ptr [rbx+10h], xmm0
0x1800022fd  mov     dword ptr [rbx+20h], 4570h
0x180002304  lock inc dword ptr [rdi+0D0h]
0x18000230b  lea     rcx, [rdi+120h]; lpCriticalSection
0x180002312  mov     [rbx+38h], rdi
0x180002316  call    cs:__imp_LeaveCriticalSection
0x18000231c  lea     r15, [rbx+60h]
0x180002320  cmp     [rdi+0F8h], r12b
0x180002327  jz      loc_1800026A9
0x18000232d  lea     r8, [rbx+40h]
0x180002331  mov     [rsp+1880h+Overlapped], rbx
0x180002336  lea     rax, SstpWebReceiveResponseEntityCompletion
0x18000233d  mov     [r8], r12d
0x180002340  mov     [rsp+1880h+BytesReturned], rax
0x180002345  xor     edx, edx
0x180002347  lea     rax, [rsp+1880h+var_1840]
0x18000234c  mov     [r8+8], r15
0x180002350  mov     qword ptr [r8+10h], 4000h
0x180002358  mov     r9d, 1
0x18000235e  mov     rcx, [rdi+1C0h]
0x180002365  mov     qword ptr [rsp+1880h+EntityBufferLength], rax
0x18000236a  mov     [rsp+1880h+var_1840], r12
0x18000236f  call    cs:__imp_WebReceiveHttpResponseEntity
0x180002375  mov     edi, eax
0x180002377  cmp     eax, 3E5h
0x18000237c  jz      loc_1800024A1
0x180002382  mov     rsi, [rbx+38h]
0x180002386  lea     rcx, [rbp+1780h+var_102C]; void *
0x18000238d  xor     edx, edx; Val
0x18000238f  mov     [rbp+1780h+var_1030], r12d
0x180002396  mov     r8d, 7FCh; Size
0x18000239c  call    memset_0
0x1800023a1  test    edi, edi
0x1800023a3  jnz     loc_1800024F0
0x1800023a9  mov     eax, dword ptr [rsp+1880h+var_1840]
0x1800023ad  mov     rcx, cs:SstpSvcGlobals
0x1800023b4  mov     [rbx+5Ch], eax
0x1800023b7  add     rcx, 300h; SRWLock
0x1800023be  mov     eax, [rsi+0F0h]
0x1800023c4  mov     [rbx+58h], eax
0x1800023c7  call    cs:__imp_AcquireSRWLockShared
0x1800023cd  mov     rcx, cs:SstpSvcGlobals
0x1800023d4  mov     edi, [rcx+308h]
0x1800023da  add     rcx, 300h; SRWLock
0x1800023e1  call    cs:__imp_ReleaseSRWLockShared
0x1800023e7  bt      edi, 0
0x1800023eb  jb      loc_180002813
0x1800023f1  xor     edx, edx; Val
0x1800023f3  mov     [rbp+1780h+var_830], r12d
0x1800023fa  mov     r8d, 7FCh; Size
0x180002400  lea     rcx, [rbp+1780h+var_82C]; void *
0x180002407  call    memset_0
0x18000240c  mov     rdi, [rbx+38h]
0x180002410  mov     [rbx+38h], r12
0x180002414  lea     rcx, [rdi+120h]; lpCriticalSection
0x18000241b  call    cs:__imp_EnterCriticalSection
0x180002421  cmp     [rdi+1B3h], r12b
0x180002428  jnz     loc_180002836
0x18000242e  lea     r8, [rbx+28h]
0x180002432  mov     [rbx+30h], r8
0x180002436  lea     rdx, [rdi+1A0h]
0x18000243d  mov     [r8], r8
0x180002440  mov     rax, [rdx+8]
0x180002444  mov     [r8], rdx
0x180002447  mov     [rbx+30h], rax
0x18000244b  mov     [rax], r8
0x18000244e  mov     [rdx+8], r8
0x180002452  cmp     [rdi+1B0h], r12b
0x180002459  jnz     short loc_180002476
0x18000245b  mov     byte ptr [rdi+1B0h], 1
0x180002462  lock inc dword ptr [rdi+0D0h]
0x180002469  mov     rcx, [rdi+150h]; pwk
0x180002470  call    cs:__imp_SubmitThreadpoolWork
0x180002476  lea     rcx, [rdi+120h]; lpCriticalSection
0x18000247d  call    cs:__imp_LeaveCriticalSection
0x180002483  mov     rcx, rsi
0x180002486  call    PostReceiveOnCall
0x18000248b  mov     eax, 0FFFFFFFFh
0x180002490  lock xadd [rsi+0D0h], eax
0x180002498  cmp     eax, 1
0x18000249b  jz      loc_1800028A2
0x1800024a1  mov     r14, [rsp+1880h+var_18]
0x1800024a9  mov     rbx, [rsp+1880h+arg_8]
0x1800024b1  mov     r15, [rsp+1880h+var_20]
0x1800024b9  test    cs:byte_18002D803, 10h
0x1800024c0  mov     rdi, [rsp+1880h+var_10]
0x1800024c8  mov     rsi, [rsp+1880h+arg_10]
0x1800024d0  jnz     loc_1800028BA
0x1800024d6  mov     rcx, [rbp+1780h+var_30]
0x1800024dd  xor     rcx, rsp; StackCookie
0x1800024e0  call    __security_check_cookie
0x1800024e5  add     rsp, 1878h
0x1800024ec  pop     r12
0x1800024ee  pop     rbp
0x1800024ef  retn
0x1800024f0  test    cs:byte_18002D803, 8
0x1800024f7  jnz     loc_1800027A6
0x1800024fd  mov     rdi, cs:SstpSvcGlobals
0x180002504  add     rbx, 0FFFFFFFFFFFFFFE8h
0x180002508  add     rdi, 1A8h
0x18000250f  lea     rcx, [rdi+40h]; lpCriticalSection
0x180002513  call    cs:__imp_EnterCriticalSection
0x180002519  cmp     [rbx], rbx
0x18000251c  jnz     loc_1800027F7
0x180002522  mov     rax, [rdi+28h]
0x180002526  lea     rcx, [rdi+28h]
0x18000252a  mov     [rbx], rax
0x18000252d  mov     [rbx+8], rcx
0x180002531  mov     [rax+8], rbx
0x180002535  mov     [rcx], rbx
0x180002538  mov     rax, [rbx+10h]
0x18000253c  inc     dword ptr [rax+1Ch]
0x18000253f  inc     dword ptr [rdi+14h]
0x180002542  mov     eax, [rdi+14h]
0x180002545  cmp     eax, [rdi+10h]
0x180002548  jnb     loc_180002802
0x18000254e  lea     rcx, [rdi+40h]; lpCriticalSection
0x180002552  call    cs:__imp_LeaveCriticalSection
0x180002558  lea     rcx, [rsi+120h]; lpCriticalSection
0x18000255f  call    cs:__imp_EnterCriticalSection
0x180002565  mov     edx, 1
0x18000256a  mov     rcx, rsi
0x18000256d  call    InitiateCallContextCleanup
0x180002572  jmp     loc_18000248B
0x180002577  test    cs:byte_18002D803, 10h
0x18000257e  jnz     short loc_1800025DA
0x180002580  lea     rcx, [rdi+120h]; lpCriticalSection
0x180002587  call    cs:__imp_LeaveCriticalSection
0x18000258d  jmp     loc_1800024B9
0x180002592  lea     r8, aPostreceiveonc; "PostReceiveOnCall"
0x180002599  mov     word ptr [rsp+1880h+var_1830], r12w
0x18000259f  lea     rdx, aEnteringWs; "Entering %ws"
0x1800025a6  lea     rcx, [rsp+1880h+var_1830]
0x1800025ab  call    FormatRRASErrorString
0x1800025b0  test    cs:byte_18002D803, 10h
0x1800025b7  jz      loc_180002254
0x1800025bd  lea     r8, [rsp+1880h+var_1830]
0x1800025c2  lea     rdx, RasSSTPSvcTraceInfo
0x1800025c9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800025d0  call    McTemplateU0z_EventWriteTransfer
0x1800025d5  jmp     loc_180002254
0x1800025da  lea     r8, [rdi+228h]
0x1800025e1  mov     word ptr [rsp+1880h+var_1830], r12w
0x1800025e7  lea     rdx, aCoidHsDisconne; "CoId=%hs:Disconnect already in progress"
0x1800025ee  lea     rcx, [rsp+1880h+var_1830]
0x1800025f3  call    FormatRRASErrorString
0x1800025f8  test    cs:byte_18002D803, 10h
0x1800025ff  jz      loc_180002580
0x180002605  lea     r8, [rsp+1880h+var_1830]
0x18000260a  lea     rdx, RasSSTPSvcTraceInfo
0x180002611  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002618  call    McTemplateU0z_EventWriteTransfer
0x18000261d  jmp     loc_180002580
0x180002622  mov     [rdi+100h], r12
0x180002629  jmp     loc_1800022F3
0x18000262e  lea     rcx, [r14+1E8h]; lpCriticalSection
0x180002635  call    cs:__imp_LeaveCriticalSection
0x18000263b  lea     rcx, [r14+1A8h]
0x180002642  call    AddBufferBlockToPool
0x180002647  mov     rbx, rax
0x18000264a  jmp     loc_1800022EA
0x18000264f  test    cs:byte_18002D803, 8
0x180002656  jz      short loc_180002697
0x180002658  lea     r8, [rdi+228h]
0x18000265f  mov     word ptr [rsp+1880h+var_1830], r12w
0x180002665  lea     rdx, aCoidHsUnableTo_3; "CoId=%hs:Unable to allocate buffer for "...
0x18000266c  lea     rcx, [rsp+1880h+var_1830]
0x180002671  call    FormatRRASErrorString
0x180002676  test    cs:byte_18002D803, 8
0x18000267d  jz      short loc_180002697
0x18000267f  lea     r8, [rsp+1880h+var_1830]
0x180002684  lea     rdx, RasSSTPSvcTraceError
0x18000268b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002692  call    McTemplateU0z_EventWriteTransfer
0x180002697  mov     edx, 2
0x18000269c  mov     rcx, rdi
0x18000269f  call    InitiateCallContextCleanup
0x1800026a4  jmp     loc_1800024A1
0x1800026a9  mov     rcx, cs:SstpSvcGlobals
0x1800026b0  mov     rcx, [rcx+0A8h]; pio
0x1800026b7  call    cs:__imp_StartThreadpoolIo
0x1800026bd  mov     rcx, cs:SstpSvcGlobals
0x1800026c4  mov     r9, r15; EntityBuffer
0x1800026c7  mov     rdx, [rdi+110h]; RequestId
0x1800026ce  xor     r8d, r8d; Flags
0x1800026d1  mov     [rsp+1880h+Overlapped], rbx; Overlapped
0x1800026d6  mov     [rsp+1880h+BytesReturned], r12; BytesReturned
0x1800026db  mov     rcx, [rcx+40h]; RequestQueueHandle
0x1800026df  mov     [rsp+1880h+EntityBufferLength], 4000h; EntityBufferLength
0x1800026e7  call    cs:__imp_HttpReceiveRequestEntityBody
0x1800026ed  mov     r15d, eax
0x1800026f0  cmp     eax, 3E5h
0x1800026f5  jz      loc_1800024A1
0x1800026fb  test    eax, eax
0x1800026fd  jz      loc_1800024A1
0x180002703  mov     rcx, cs:SstpSvcGlobals
0x18000270a  mov     rcx, [rcx+0A8h]; pio
0x180002711  call    cs:__imp_CancelThreadpoolIo
0x180002717  test    cs:byte_18002D803, 8
0x18000271e  jz      short loc_180002762
0x180002720  lea     r8, [rdi+228h]
0x180002727  mov     word ptr [rsp+1880h+var_1830], r12w
0x18000272d  mov     r9d, r15d
0x180002730  lea     rdx, aCoidHsReceivee; "CoId=%hs:ReceiveEntityBody fails with %"...
0x180002737  lea     rcx, [rsp+1880h+var_1830]
0x18000273c  call    FormatRRASErrorString
0x180002741  test    cs:byte_18002D803, 8
0x180002748  jz      short loc_180002762
0x18000274a  lea     r8, [rsp+1880h+var_1830]
0x18000274f  lea     rdx, RasSSTPSvcTraceError
0x180002756  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000275d  call    McTemplateU0z_EventWriteTransfer
0x180002762  mov     rcx, cs:SstpSvcGlobals
0x180002769  mov     r8b, 1
0x18000276c  add     rcx, 1A8h
0x180002773  mov     rdx, rbx
0x180002776  call    FreeBufferToPool
0x18000277b  lea     rcx, [rdi+120h]; lpCriticalSection
0x180002782  call    cs:__imp_EnterCriticalSection
0x180002788  mov     edx, 1
0x18000278d  mov     rcx, rdi
0x180002790  call    InitiateCallContextCleanup
0x180002795  lea     rcx, [rdi+0D0h]
0x18000279c  call    DereferenceRefCount
0x1800027a1  jmp     loc_1800024A1
0x1800027a6  lea     r8, [rsi+228h]
0x1800027ad  mov     word ptr [rbp+1780h+var_1030], r12w
0x1800027b5  mov     r9d, edi
0x1800027b8  lea     rdx, aCoidHsReceiver; "CoId=%hs:ReceiveResponseEntity fails wi"...
0x1800027bf  lea     rcx, [rbp+1780h+var_1030]
0x1800027c6  call    FormatRRASErrorString
0x1800027cb  test    cs:byte_18002D803, 8
0x1800027d2  jz      loc_1800024FD
0x1800027d8  lea     r8, [rbp+1780h+var_1030]
0x1800027df  lea     rdx, RasSSTPSvcTraceError
0x1800027e6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800027ed  call    McTemplateU0z_EventWriteTransfer
0x1800027f2  jmp     loc_1800024FD
0x1800027f7  inc     cs:g_ulDoubleBufferFrees
0x1800027fd  jmp     loc_18000254E
0x180002802  mov     rcx, rdi
0x180002805  call    FreeUnusedBufferPoolBlocks
0x18000280a  mov     [rdi+14h], r12d
0x18000280e  jmp     loc_18000254E
0x180002813  test    rsi, rsi
0x180002816  jz      loc_1800023F1
0x18000281c  cmp     [rsi+270h], r12
0x180002823  jz      loc_1800023F1
  ... truncated ...
```
