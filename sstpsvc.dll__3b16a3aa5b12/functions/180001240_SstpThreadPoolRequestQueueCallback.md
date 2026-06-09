# SstpThreadPoolRequestQueueCallback

- ea: `0x180001240`
- end: `0x180001a75`
- name: `SstpThreadPoolRequestQueueCallback`
- size: `2101`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, unsigned int *Overlapped, ULONG IoResult)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x180001240`
- `0x180002908`
- `0x180002d40`
- `0x180002d70`
- `0x180004d10`
- `0x180007a84`
- `0x18000827c`
- `0x180008360`
- `0x1800085fc`
- `0x18000a0d4`
- `0x18000b9fc`
- `0x18000ec1c`
- `0x18000ec98`
- `0x18001bcba`
- `0x18001bcf0`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800012b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800014b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001618`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000163c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800017af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001846`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800018a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800012b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800014b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001618`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000163c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800017af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001846`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800018a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800012fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800014cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800015a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000183e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800018bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001994`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800012fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800014cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800015a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000183e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800018bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001994`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001a1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001a1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001a10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001a10`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800012ef`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800012ef`
- `rtutils!RouterLogEventW` at `0x180001777`
- `rtutils!RouterLogEventW` at `0x180001777`

## string_xrefs

- `0x1800018f6`: `CoId=%hs:Incoming call was not accepted - 0x%x`
- `0x1800019ba`: `CoId=%hs:Incoming call was not accepted - 0x%x`
- `0x180001934`: `CoId=%hs:Incoming call accepted`

## pseudocode

```c
void __fastcall SstpThreadPoolRequestQueueCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        unsigned int *Overlapped,
        ULONG IoResult)
{
  __int64 v6; // r8
  unsigned int v7; // eax
  void (__fastcall **v8)(char *); // rdi
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // rsi
  unsigned int v16; // r14d
  unsigned int v17; // edx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rax
  char *v21; // rcx
  struct _RTL_CRITICAL_SECTION *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rsi
  int v25; // eax
  __int64 v26; // r9
  HANDLE ProcessHeap; // rax
  __int64 v28; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR plpszSubStringArray[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v30; // [rsp+48h] [rbp-B8h]
  _BYTE v31[96]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR WideCharStr[40]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v33[144]; // [rsp+110h] [rbp+10h] BYREF
  int v34; // [rsp+1A0h] [rbp+A0h] BYREF
  char v35[2044]; // [rsp+1A4h] [rbp+A4h] BYREF

  v34 = 0;
  memset_0(v35, 0, sizeof(v35));
  if ( Overlapped )
  {
    if ( (byte_18002D803 & 0x10) != 0 )
    {
      v13 = Overlapped[8];
      LOWORD(v34) = 0;
      FormatRRASErrorString(&v34, L"OverlapInfo with id %x received [%d - %d", v13, IoResult, IoResult);
      if ( (byte_18002D803 & 0x10) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v34);
    }
    v7 = Overlapped[8];
    if ( v7 == 17770 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(Overlapped + 62));
      if ( IoResult || *((_BYTE *)Overlapped + 395) )
      {
        Overlapped[53] &= ~4u;
        InitiateCallContextCleanup(Overlapped - 10, 2);
        v8 = (void (__fastcall **)(char *))(Overlapped + 42);
      }
      else
      {
        Overlapped[53] &= ~0x400u;
        v8 = (void (__fastcall **)(char *))(Overlapped + 42);
        _InterlockedIncrement((volatile signed __int32 *)Overlapped + 42);
        SubmitThreadpoolWork(*((PTP_WORK *)Overlapped + 36));
        LeaveCriticalSection((LPCRITICAL_SECTION)(Overlapped + 62));
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8, 0xFFFFFFFF) == 1 )
        v8[1]((char *)v8);
      return;
    }
    v9 = v7 - 17769;
    if ( v9 )
    {
      v10 = v9 - 3;
      if ( v10 )
      {
        v11 = v10 - 2;
        if ( v11 )
        {
          v12 = v11 - 3;
          if ( v12 )
          {
            if ( v12 != 2 )
              return;
            v14 = *((_QWORD *)SstpSvcGlobals + 22);
            if ( !v14 )
            {
              v15 = 0;
              v16 = 87;
LABEL_20:
              if ( !IoResult )
              {
                if ( Overlapped[16] )
                {
                  if ( (byte_18002D803 & 8) != 0 )
                  {
                    LOWORD(v34) = 0;
                    FormatRRASErrorString(&v34, L"CoId=%hs: CLIENT_FSM_FAILED, Status=%d", v15 + 552, v16);
                    if ( (byte_18002D803 & 8) != 0 )
                      McTemplateU0z_EventWriteTransfer(
                        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                        RasSSTPSvcTraceError,
                        &v34);
                  }
                  LogEventWithErrorParameter(5u);
                  EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 288));
                  InitiateCallContextCleanup(v15, 0);
                }
                else
                {
                  _InterlockedIncrement((volatile signed __int32 *)(v15 + 208));
                  EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 288));
                  if ( *(_BYTE *)(v15 + 435) )
                  {
                    LeaveCriticalSection((LPCRITICAL_SECTION)(v15 + 288));
                  }
                  else
                  {
                    if ( (byte_18002D803 & 0x10) != 0 )
                    {
                      LOWORD(v34) = 0;
                      FormatRRASErrorString(&v34, L"CoId=%hs:Established connection successfully", v15 + 552);
                      if ( (byte_18002D803 & 0x10) != 0 )
                        McTemplateU0z_EventWriteTransfer(
                          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                          RasSSTPSvcTraceInfo,
                          &v34);
                    }
                    *(_DWORD *)(v15 + 112) = 17777;
                    *(_OWORD *)(v15 + 80) = 0;
                    *(_OWORD *)(v15 + 96) = 0;
                    *(_DWORD *)(v15 + 120) = *(_DWORD *)(v15 + 240);
                    *(_BYTE *)(v15 + 124) = 0;
                    if ( (unsigned int)AsyncSstpDeviceControl(
                                         0x12801Cu,
                                         (LPVOID)(v15 + 120),
                                         8u,
                                         (LPVOID)(v15 + 120),
                                         8u,
                                         (LPOVERLAPPED)(v15 + 80)) )
                    {
                      *(_BYTE *)(v15 + 433) = 0;
                      InitiateCallContextCleanup(v15, 0);
                      DereferenceRefCount(v15 + 208);
                    }
                    else
                    {
                      *(_BYTE *)(v15 + 433) = 1;
                      LeaveCriticalSection((LPCRITICAL_SECTION)(v15 + 288));
                    }
                  }
                }
              }
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v15 + 208), 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(__int64))(v15 + 216))(v15 + 208);
              return;
            }
            v17 = Overlapped[11];
            v18 = *(_DWORD *)v14 - 1;
            v19 = *(_QWORD *)(v14 + 8);
            v20 = 32LL * (int)(v17 & v18);
            if ( *(_DWORD *)(v19 + v20) == v17 )
            {
              v15 = *(_QWORD *)(v19 + v20 + 8);
              if ( v15 )
              {
                v16 = 0;
                goto LABEL_20;
              }
            }
            else
            {
              v15 = 0;
            }
            v16 = 6;
            goto LABEL_20;
          }
          if ( !IoResult )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)(Overlapped + 52));
            if ( *((_BYTE *)Overlapped + 44) )
            {
              if ( (byte_18002D803 & 8) != 0 )
              {
                LOWORD(v34) = 0;
                FormatRRASErrorString(&v34, L"CoId=%hs: Crypto Binding failed notification received", Overlapped + 118);
                if ( (byte_18002D803 & 8) != 0 )
                  McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v34);
              }
              if ( *((_QWORD *)SstpSvcGlobals + 9) )
              {
                memset_0(v31, 0, 0x56u);
                memset_0(v33, 0, 0x86u);
                ConvertByteArrayToString((char *)Overlapped + 409, 20, v31, 43);
                ConvertByteArrayToString((char *)Overlapped + 429, 32, v33, 67);
                ConvertCorrelationIdToWideChar(WideCharStr);
                plpszSubStringArray[0] = WideCharStr;
                plpszSubStringArray[1] = (LPWSTR)v31;
                v30 = (unsigned __int64)v33;
                RouterLogEventW(*((HANDLE *)SstpSvcGlobals + 9), 1u, 6u, 3u, plpszSubStringArray, 0);
              }
            }
            InitiateCallContextCleanup(Overlapped - 20, 0);
          }
          v21 = (char *)(Overlapped + 32);
LABEL_53:
          DereferenceRefCount(v21);
          return;
        }
        v22 = (struct _RTL_CRITICAL_SECTION *)(Overlapped + 72);
        if ( IoResult )
        {
          EnterCriticalSection(v22);
          Overlapped[63] &= ~0x8000u;
          InitiateCallContextCleanup(Overlapped, 0);
          goto LABEL_61;
        }
        _InterlockedIncrement((volatile signed __int32 *)Overlapped + 52);
        EnterCriticalSection(v22);
        Overlapped[63] &= ~0x8000u;
        if ( !*((_BYTE *)Overlapped + 435) )
        {
          Overlapped[28] = 17777;
          *((_OWORD *)Overlapped + 5) = 0;
          *((_OWORD *)Overlapped + 6) = 0;
          Overlapped[30] = Overlapped[60];
          *((_BYTE *)Overlapped + 124) = 0;
          if ( (unsigned int)AsyncSstpDeviceControl(
                               0x12801Cu,
                               Overlapped + 30,
                               8u,
                               Overlapped + 30,
                               8u,
                               (LPOVERLAPPED)(Overlapped + 20)) )
          {
            *((_BYTE *)Overlapped + 433) = 0;
            InitiateCallContextCleanup(Overlapped, 0);
            DereferenceRefCount(Overlapped + 52);
LABEL_61:
            v21 = (char *)(Overlapped + 52);
            goto LABEL_53;
          }
          *((_BYTE *)Overlapped + 433) = 1;
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)(Overlapped + 72));
        goto LABEL_61;
      }
      v23 = Overlapped[10];
      v28 = 0;
      if ( (unsigned int)HfGetPointerFromHandle32(*((_QWORD *)SstpSvcGlobals + 22), v23, &v28) )
      {
LABEL_79:
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, Overlapped);
        return;
      }
      v24 = v28;
      EnterCriticalSection((LPCRITICAL_SECTION)(v28 + 288));
      v25 = *(_DWORD *)(v24 + 252);
      if ( (v25 & 0x10) == 0 )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)(v24 + 288));
        goto LABEL_79;
      }
      *(_DWORD *)(v24 + 252) = v25 & 0xFFFFFFEF;
      if ( IoResult )
      {
        if ( (byte_18002D803 & 8) == 0 )
          goto LABEL_77;
        v26 = Overlapped[18];
        LOWORD(v34) = 0;
        FormatRRASErrorString(&v34, L"CoId=%hs:Incoming call was not accepted - 0x%x", v24 + 552, v26);
        if ( (byte_18002D803 & 8) == 0 )
          goto LABEL_77;
      }
      else
      {
        if ( !Overlapped[18] )
        {
          if ( (byte_18002D803 & 0x10) != 0 )
          {
            LOWORD(v34) = 0;
            FormatRRASErrorString(&v34, L"CoId=%hs:Incoming call accepted", v24 + 552);
            if ( (byte_18002D803 & 0x10) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v34);
          }
          *(_DWORD *)(v24 + 240) = Overlapped[19];
          *(_DWORD *)(v24 + 252) = *(_DWORD *)(v24 + 252) & 0xFFFFFDDF | 0x20;
          LeaveCriticalSection((LPCRITICAL_SECTION)(v24 + 288));
          InitiateSstpResponse(v24);
          goto LABEL_78;
        }
        if ( (byte_18002D803 & 8) == 0
          || (LOWORD(v34) = 0,
              FormatRRASErrorString(&v34, L"CoId=%hs:Incoming call was not accepted - 0x%x", v24 + 552),
              (byte_18002D803 & 8) == 0) )
        {
LABEL_77:
          InitiateCallContextCleanup(v24, 2);
LABEL_78:
          DereferenceRefCount(v24 + 208);
          goto LABEL_79;
        }
      }
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v34);
      goto LABEL_77;
    }
    if ( IoResult )
    {
      if ( IoResult == 995 )
      {
        LOBYTE(v6) = 1;
        FreeBufferToPool((char *)SstpSvcGlobals + 312, Overlapped, v6);
      }
    }
    else
    {
      ProcessReceivedNotification(Overlapped);
    }
  }
  else if ( (byte_18002D803 & 8) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasSSTPSvcTraceError,
      L"No Overlapped info found...");
  }
}

```

## disassembly

```asm
0x180001240  push    rbp
0x180001242  push    rbx
0x180001243  push    rdi
0x180001244  lea     rbp, [rsp-8B0h]
0x18000124c  sub     rsp, 9B0h
0x180001253  mov     rax, cs:__security_cookie
0x18000125a  xor     rax, rsp
0x18000125d  mov     [rbp+8C0h+var_20], rax
0x180001264  mov     rbx, r8
0x180001267  lea     rcx, [rbp+8C0h+var_81C]; void *
0x18000126e  xor     eax, eax
0x180001270  mov     r8d, 7FCh; Size
0x180001276  xor     edx, edx; Val
0x180001278  mov     [rbp+8C0h+var_820], eax
0x18000127e  mov     edi, r9d
0x180001281  call    memset_0
0x180001286  test    rbx, rbx
0x180001289  jz      loc_18000143C
0x18000128f  test    cs:byte_18002D803, 10h
0x180001296  jnz     loc_180001373
0x18000129c  mov     eax, [rbx+20h]
0x18000129f  mov     [rsp+9C0h+arg_0], rsi
0x1800012a7  cmp     eax, 456Ah
0x1800012ac  jnz     loc_180001336
0x1800012b2  lea     rcx, [rbx+0F8h]; lpCriticalSection
0x1800012b9  call    cs:__imp_EnterCriticalSection
0x1800012bf  test    edi, edi
0x1800012c1  jnz     loc_18000141B
0x1800012c7  cmp     [rbx+18Bh], dil
0x1800012ce  jnz     loc_18000141B
0x1800012d4  and     dword ptr [rbx+0D4h], 0FFFFFBFFh
0x1800012de  lea     rdi, [rbx+0A8h]
0x1800012e5  lock inc dword ptr [rdi]
0x1800012e8  mov     rcx, [rbx+120h]; pwk
0x1800012ef  call    cs:__imp_SubmitThreadpoolWork
0x1800012f5  lea     rcx, [rbx+0F8h]; lpCriticalSection
0x1800012fc  call    cs:__imp_LeaveCriticalSection
0x180001302  mov     eax, 0FFFFFFFFh
0x180001307  lock xadd [rdi], eax
0x18000130b  cmp     eax, 1
0x18000130e  jz      loc_180001A64
0x180001314  mov     rsi, [rsp+9C0h+arg_0]
0x18000131c  mov     rcx, [rbp+8C0h+var_20]
0x180001323  xor     rcx, rsp; StackCookie
0x180001326  call    __security_check_cookie
0x18000132b  add     rsp, 9B0h
0x180001332  pop     rdi
0x180001333  pop     rbx
0x180001334  pop     rbp
0x180001335  retn
0x180001336  sub     eax, 4569h
0x18000133b  jz      loc_180001A29
0x180001341  mov     [rsp+9C0h+arg_8], r14
0x180001349  sub     eax, 3
0x18000134c  jz      loc_18000186C
0x180001352  sub     eax, 2
0x180001355  jz      loc_180001799
0x18000135b  sub     eax, 3
0x18000135e  jz      loc_18000162D
0x180001364  cmp     eax, 2
0x180001367  jz      short loc_1800013C6
0x180001369  mov     r14, [rsp+9C0h+arg_8]
0x180001371  jmp     short loc_180001314
0x180001373  mov     r8d, [rbx+20h]
0x180001377  lea     rdx, aOverlapinfoWit; "OverlapInfo with id %x received [%d - %"...
0x18000137e  xor     eax, eax
0x180001380  mov     dword ptr [rsp+9C0h+plpszSubStringArray], edi
0x180001384  mov     r9d, edi
0x180001387  mov     word ptr [rbp+8C0h+var_820], ax
0x18000138e  lea     rcx, [rbp+8C0h+var_820]
0x180001395  call    FormatRRASErrorString
0x18000139a  test    cs:byte_18002D803, 10h
0x1800013a1  jz      loc_18000129C
0x1800013a7  lea     r8, [rbp+8C0h+var_820]
0x1800013ae  lea     rdx, RasSSTPSvcTraceInfo
0x1800013b5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800013bc  call    McTemplateU0z_EventWriteTransfer
0x1800013c1  jmp     loc_18000129C
0x1800013c6  mov     rax, cs:SstpSvcGlobals
0x1800013cd  mov     rcx, [rax+0B0h]
0x1800013d4  test    rcx, rcx
0x1800013d7  jnz     loc_180001468
0x1800013dd  xor     esi, esi
0x1800013df  mov     r14d, 57h ; 'W'
0x1800013e5  test    edi, edi
0x1800013e7  jz      loc_18000149F
0x1800013ed  mov     eax, 0FFFFFFFFh
0x1800013f2  lock xadd [rsi+0D0h], eax
0x1800013fa  cmp     eax, 1
0x1800013fd  jnz     loc_180001369
0x180001403  mov     rax, [rsi+0D8h]
0x18000140a  lea     rcx, [rsi+0D0h]
0x180001411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001416  jmp     loc_180001369
0x18000141b  and     dword ptr [rbx+0D4h], 0FFFFFFFBh
0x180001422  lea     rcx, [rbx-28h]
0x180001426  mov     edx, 2
0x18000142b  call    InitiateCallContextCleanup
0x180001430  lea     rdi, [rbx+0A8h]
0x180001437  jmp     loc_180001302
0x18000143c  test    cs:byte_18002D803, 8
0x180001443  jz      loc_18000131C
0x180001449  lea     r8, aNoOverlappedIn; "No Overlapped info found..."
0x180001450  lea     rdx, RasSSTPSvcTraceError
0x180001457  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000145e  call    McTemplateU0z_EventWriteTransfer
0x180001463  jmp     loc_18000131C
0x180001468  mov     eax, [rcx]
0x18000146a  mov     edx, [rbx+2Ch]
0x18000146d  dec     eax
0x18000146f  mov     rcx, [rcx+8]
0x180001473  and     eax, edx
0x180001475  cdqe
0x180001477  shl     rax, 5
0x18000147b  cmp     [rcx+rax], edx
0x18000147e  jnz     short loc_180001492
0x180001480  mov     rsi, [rcx+rax+8]
0x180001485  test    rsi, rsi
0x180001488  jz      short loc_180001494
0x18000148a  xor     r14d, r14d
0x18000148d  jmp     loc_1800013E5
0x180001492  xor     esi, esi
0x180001494  mov     r14d, 6
0x18000149a  jmp     loc_1800013E5
0x18000149f  cmp     dword ptr [rbx+40h], 0
0x1800014a3  jnz     loc_1800015AB
0x1800014a9  lock inc dword ptr [rsi+0D0h]
0x1800014b0  lea     rcx, [rsi+120h]; lpCriticalSection
0x1800014b7  call    cs:__imp_EnterCriticalSection
0x1800014bd  cmp     byte ptr [rsi+1B3h], 0
0x1800014c4  jz      short loc_1800014D8
0x1800014c6  lea     rcx, [rsi+120h]; lpCriticalSection
0x1800014cd  call    cs:__imp_LeaveCriticalSection
0x1800014d3  jmp     loc_1800013ED
0x1800014d8  test    cs:byte_18002D803, 10h
0x1800014df  jz      short loc_180001527
0x1800014e1  xor     eax, eax
0x1800014e3  lea     r8, [rsi+228h]
0x1800014ea  lea     rdx, aCoidHsEstablis; "CoId=%hs:Established connection success"...
0x1800014f1  mov     word ptr [rbp+8C0h+var_820], ax
0x1800014f8  lea     rcx, [rbp+8C0h+var_820]
0x1800014ff  call    FormatRRASErrorString
0x180001504  test    cs:byte_18002D803, 10h
0x18000150b  jz      short loc_180001527
0x18000150d  lea     r8, [rbp+8C0h+var_820]
0x180001514  lea     rdx, RasSSTPSvcTraceInfo
0x18000151b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180001522  call    McTemplateU0z_EventWriteTransfer
0x180001527  lea     rcx, [rsi+50h]
0x18000152b  mov     dword ptr [rsi+70h], 4571h
0x180001532  xorps   xmm0, xmm0
0x180001535  mov     qword ptr [rsp+9C0h+dwErrorCode], rcx; LPOVERLAPPED
0x18000153a  movups  xmmword ptr [rcx], xmm0
0x18000153d  lea     rdx, [rsi+78h]; lpInBuffer
0x180001541  mov     r8d, 8; nInBufferSize
0x180001547  movups  xmmword ptr [rcx+10h], xmm0
0x18000154b  mov     eax, [rsi+0F0h]
0x180001551  mov     ecx, 12801Ch; dwIoControlCode
0x180001556  mov     r9, rdx; lpOutBuffer
0x180001559  mov     [rdx], eax
0x18000155b  mov     byte ptr [rsi+7Ch], 0
0x18000155f  mov     dword ptr [rsp+9C0h+plpszSubStringArray], 8; DWORD
0x180001567  call    AsyncSstpDeviceControl
0x18000156c  test    eax, eax
0x18000156e  jz      short loc_180001592
0x180001570  xor     edx, edx
0x180001572  mov     byte ptr [rsi+1B1h], 0
0x180001579  mov     rcx, rsi
0x18000157c  call    InitiateCallContextCleanup
0x180001581  lea     rcx, [rsi+0D0h]
0x180001588  call    DereferenceRefCount
0x18000158d  jmp     loc_1800013ED
0x180001592  lea     rcx, [rsi+120h]; lpCriticalSection
0x180001599  mov     byte ptr [rsi+1B1h], 1
0x1800015a0  call    cs:__imp_LeaveCriticalSection
0x1800015a6  jmp     loc_1800013ED
0x1800015ab  test    cs:byte_18002D803, 8
0x1800015b2  jz      short loc_1800015FD
0x1800015b4  xor     eax, eax
0x1800015b6  lea     r8, [rsi+228h]
0x1800015bd  mov     r9d, r14d
0x1800015c0  mov     word ptr [rbp+8C0h+var_820], ax
0x1800015c7  lea     rdx, aCoidHsClientFs; "CoId=%hs: CLIENT_FSM_FAILED, Status=%d"
0x1800015ce  lea     rcx, [rbp+8C0h+var_820]
0x1800015d5  call    FormatRRASErrorString
0x1800015da  test    cs:byte_18002D803, 8
0x1800015e1  jz      short loc_1800015FD
0x1800015e3  lea     r8, [rbp+8C0h+var_820]
0x1800015ea  lea     rdx, RasSSTPSvcTraceError
0x1800015f1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800015f8  call    McTemplateU0z_EventWriteTransfer
0x1800015fd  lea     r9, [rsi+228h]
0x180001604  mov     r8d, r14d
0x180001607  mov     ecx, 5; dwMessageId
0x18000160c  call    LogEventWithErrorParameter
0x180001611  lea     rcx, [rsi+120h]; lpCriticalSection
0x180001618  call    cs:__imp_EnterCriticalSection
0x18000161e  xor     edx, edx
0x180001620  mov     rcx, rsi
0x180001623  call    InitiateCallContextCleanup
0x180001628  jmp     loc_1800013ED
0x18000162d  test    edi, edi
0x18000162f  jnz     loc_180001788
0x180001635  lea     rcx, [rbx+0D0h]; lpCriticalSection
0x18000163c  call    cs:__imp_EnterCriticalSection
0x180001642  cmp     [rbx+2Ch], dil
0x180001646  jz      loc_18000177D
0x18000164c  test    cs:byte_18002D803, 8
0x180001653  jz      short loc_18000169B
0x180001655  xor     eax, eax
0x180001657  lea     r8, [rbx+1D8h]
0x18000165e  lea     rdx, aCoidHsCryptoBi; "CoId=%hs: Crypto Binding failed notific"...
0x180001665  mov     word ptr [rbp+8C0h+var_820], ax
0x18000166c  lea     rcx, [rbp+8C0h+var_820]
0x180001673  call    FormatRRASErrorString
0x180001678  test    cs:byte_18002D803, 8
0x18000167f  jz      short loc_18000169B
0x180001681  lea     r8, [rbp+8C0h+var_820]
0x180001688  lea     rdx, RasSSTPSvcTraceError
0x18000168f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180001696  call    McTemplateU0z_EventWriteTransfer
0x18000169b  mov     rax, cs:SstpSvcGlobals
0x1800016a2  cmp     qword ptr [rax+48h], 0
0x1800016a7  jz      loc_18000177D
0x1800016ad  xorps   xmm0, xmm0
0x1800016b0  lea     rcx, [rsp+9C0h+var_960]; void *
0x1800016b5  xor     edx, edx; Val
0x1800016b7  mov     r8d, 56h ; 'V'; Size
0x1800016bd  movups  xmmword ptr [rsp+9C0h+var_988], xmm0
0x1800016c2  movups  [rsp+9C0h+var_978], xmm0
0x1800016c7  call    memset_0
0x1800016cc  xor     edx, edx; Val
0x1800016ce  lea     rcx, [rbp+8C0h+var_8B0]; void *
0x1800016d2  mov     r8d, 86h; Size
0x1800016d8  call    memset_0
0x1800016dd  lea     rcx, [rbx+199h]
0x1800016e4  mov     r9d, 2Bh ; '+'
0x1800016ea  lea     r8, [rsp+9C0h+var_960]
0x1800016ef  mov     edx, 14h
0x1800016f4  call    ConvertByteArrayToString
0x1800016f9  lea     rcx, [rbx+1ADh]
0x180001700  mov     r9d, 43h ; 'C'
0x180001706  lea     r8, [rbp+8C0h+var_8B0]
0x18000170a  mov     edx, 20h ; ' '
0x18000170f  call    ConvertByteArrayToString
0x180001714  lea     r8, [rbx+1D8h]
0x18000171b  lea     rcx, [rbp+8C0h+WideCharStr]; lpWideCharStr
0x18000171f  call    ConvertCorrelationIdToWideChar
0x180001724  mov     rcx, cs:SstpSvcGlobals
0x18000172b  lea     rax, [rbp+8C0h+WideCharStr]
0x18000172f  mov     [rsp+9C0h+var_988], rax
0x180001734  mov     edx, 1; dwEventType
0x180001739  lea     rax, [rsp+9C0h+var_960]
0x18000173e  mov     qword ptr [rsp+9C0h+var_978+8], 0
0x180001747  mov     [rsp+9C0h+var_988+8], rax
0x18000174c  mov     r9d, 3; dwSubStringCount
0x180001752  lea     rax, [rbp+8C0h+var_8B0]
0x180001756  mov     [rsp+9C0h+dwErrorCode], 0; dwErrorCode
0x18000175e  mov     qword ptr [rsp+9C0h+var_978], rax
0x180001763  mov     r8d, 6; dwMessageId
0x180001769  mov     rcx, [rcx+48h]; hLogHandle
0x18000176d  lea     rax, [rsp+9C0h+var_988]
0x180001772  mov     [rsp+9C0h+plpszSubStringArray], rax; plpszSubStringArray
0x180001777  call    cs:__imp_RouterLogEventW
0x18000177d  xor     edx, edx
0x18000177f  lea     rcx, [rbx-50h]
0x180001783  call    InitiateCallContextCleanup
0x180001788  lea     rcx, [rbx+80h]
0x18000178f  call    DereferenceRefCount
0x180001794  jmp     loc_180001369
0x180001799  lea     rcx, [rbx+120h]; lpCriticalSection
0x1800017a0  test    edi, edi
0x1800017a2  jnz     loc_180001846
0x1800017a8  lock inc dword ptr [rbx+0D0h]
0x1800017af  call    cs:__imp_EnterCriticalSection
0x1800017b5  and     dword ptr [rbx+0FCh], 0FFFF7FFFh
0x1800017bf  cmp     [rbx+1B3h], dil
0x1800017c6  jnz     short loc_180001837
0x1800017c8  lea     rcx, [rbx+50h]
0x1800017cc  mov     dword ptr [rbx+70h], 4571h
0x1800017d3  xorps   xmm0, xmm0
0x1800017d6  mov     qword ptr [rsp+9C0h+dwErrorCode], rcx; LPOVERLAPPED
0x1800017db  movups  xmmword ptr [rcx], xmm0
0x1800017de  lea     rdx, [rbx+78h]; lpInBuffer
0x1800017e2  mov     r8d, 8; nInBufferSize
0x1800017e8  movups  xmmword ptr [rcx+10h], xmm0
0x1800017ec  mov     eax, [rbx+0F0h]
0x1800017f2  mov     ecx, 12801Ch; dwIoControlCode
0x1800017f7  mov     r9, rdx; lpOutBuffer
0x1800017fa  mov     [rdx], eax
0x1800017fc  mov     [rbx+7Ch], dil
0x180001800  mov     dword ptr [rsp+9C0h+plpszSubStringArray], 8; DWORD
0x180001808  call    AsyncSstpDeviceControl
0x18000180d  test    eax, eax
0x18000180f  jz      short loc_180001830
0x180001811  xor     edx, edx
0x180001813  mov     [rbx+1B1h], dil
0x18000181a  mov     rcx, rbx
0x18000181d  call    InitiateCallContextCleanup
0x180001822  lea     rcx, [rbx+0D0h]
  ... truncated ...
```
