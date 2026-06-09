# SstpThreadPoolRequestQueueCallback

- ea: `0x1800012b0`
- end: `0x180001b38`
- name: `SstpThreadPoolRequestQueueCallback`
- size: `2184`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PVOID Overlapped, ULONG IoResult, ULONG_PTR NumberOfBytesTransferred, PTP_IO Io)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x1800012b0`
- `0x180002aac`
- `0x180002f50`
- `0x180002f80`
- `0x180005110`
- `0x18000823c`
- `0x1800089dc`
- `0x180008b90`
- `0x180008df8`
- `0x18000aa44`
- `0x18000c4c4`
- `0x18000f984`
- `0x18000fa00`
- `0x18001d1da`
- `0x18001d210`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001329`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000153a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001699`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800016c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001842`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800018e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001949`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001329`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000153a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001699`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800016c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001842`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800018e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001949`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001378`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000161b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800018d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001966`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001a45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001378`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000161b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800018d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001966`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001a45`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001adb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001adb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001ac7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001ac7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180001365`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180001365`
- `rtutils!RouterLogEventW` at `0x180001804`
- `rtutils!RouterLogEventW` at `0x180001804`

## string_xrefs

- `0x1800019a7`: `CoId=%hs:Incoming call was not accepted - 0x%x`
- `0x180001a71`: `CoId=%hs:Incoming call was not accepted - 0x%x`
- `0x1800019e5`: `CoId=%hs:Incoming call accepted`

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
    if ( (byte_18002E903 & 0x10) != 0 )
    {
      v13 = Overlapped[8];
      LOWORD(v34) = 0;
      FormatRRASErrorString(&v34, L"OverlapInfo with id %x received [%d - %d", v13, IoResult, IoResult);
      if ( (byte_18002E903 & 0x10) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v34);
    }
    v7 = Overlapped[8];
    if ( v7 == 17770 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(Overlapped + 62));
      if ( IoResult || *((_BYTE *)Overlapped + 395) )
      {
        Overlapped[53] &= ~4u;
        InitiateCallContextCleanup((__int64)(Overlapped - 10), 2u);
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
              goto LABEL_20;
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
LABEL_20:
            if ( IoResult )
              goto LABEL_21;
            if ( Overlapped[16] )
            {
              if ( (byte_18002E903 & 8) != 0 )
              {
                LOWORD(v34) = 0;
                FormatRRASErrorString(&v34, L"CoId=%hs: CLIENT_FSM_FAILED, Status=%d", v15 + 552, v16);
                if ( (byte_18002E903 & 8) != 0 )
                  McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v34);
              }
              LogEventWithErrorParameter(5u);
              EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 288));
              InitiateCallContextCleanup(v15, 0);
              goto LABEL_21;
            }
            _InterlockedIncrement((volatile signed __int32 *)(v15 + 208));
            EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 288));
            if ( !*(_BYTE *)(v15 + 435) )
            {
              if ( (byte_18002E903 & 0x10) != 0 )
              {
                LOWORD(v34) = 0;
                FormatRRASErrorString(&v34, L"CoId=%hs:Established connection successfully", v15 + 552);
                if ( (byte_18002E903 & 0x10) != 0 )
                  McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v34);
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
                goto LABEL_21;
              }
              *(_BYTE *)(v15 + 433) = 1;
            }
            LeaveCriticalSection((LPCRITICAL_SECTION)(v15 + 288));
LABEL_21:
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v15 + 208), 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(__int64))(v15 + 216))(v15 + 208);
            return;
          }
          if ( !IoResult )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)(Overlapped + 52));
            if ( *((_BYTE *)Overlapped + 44) )
            {
              if ( (byte_18002E903 & 8) != 0 )
              {
                LOWORD(v34) = 0;
                FormatRRASErrorString(&v34, L"CoId=%hs: Crypto Binding failed notification received", Overlapped + 118);
                if ( (byte_18002E903 & 8) != 0 )
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
            InitiateCallContextCleanup((__int64)(Overlapped - 20), 0);
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
          InitiateCallContextCleanup((__int64)Overlapped, 0);
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
            InitiateCallContextCleanup((__int64)Overlapped, 0);
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
        if ( (byte_18002E903 & 8) == 0 )
          goto LABEL_77;
        v26 = Overlapped[18];
        LOWORD(v34) = 0;
        FormatRRASErrorString(&v34, L"CoId=%hs:Incoming call was not accepted - 0x%x", v24 + 552, v26);
        if ( (byte_18002E903 & 8) == 0 )
          goto LABEL_77;
      }
      else
      {
        if ( !Overlapped[18] )
        {
          if ( (byte_18002E903 & 0x10) != 0 )
          {
            LOWORD(v34) = 0;
            FormatRRASErrorString(&v34, L"CoId=%hs:Incoming call accepted", v24 + 552);
            if ( (byte_18002E903 & 0x10) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v34);
          }
          *(_DWORD *)(v24 + 240) = Overlapped[19];
          *(_DWORD *)(v24 + 252) = *(_DWORD *)(v24 + 252) & 0xFFFFFDDF | 0x20;
          LeaveCriticalSection((LPCRITICAL_SECTION)(v24 + 288));
          InitiateSstpResponse(v24);
          goto LABEL_78;
        }
        if ( (byte_18002E903 & 8) == 0
          || (LOWORD(v34) = 0,
              FormatRRASErrorString(&v34, L"CoId=%hs:Incoming call was not accepted - 0x%x", v24 + 552),
              (byte_18002E903 & 8) == 0) )
        {
LABEL_77:
          InitiateCallContextCleanup(v24, 2u);
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
  else if ( (byte_18002E903 & 8) != 0 )
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
0x1800012b0  push    rbp
0x1800012b2  push    rbx
0x1800012b3  push    rdi
0x1800012b4  lea     rbp, [rsp-8B0h]
0x1800012bc  sub     rsp, 9B0h
0x1800012c3  mov     rax, cs:__security_cookie
0x1800012ca  xor     rax, rsp
0x1800012cd  mov     [rbp+8C0h+var_20], rax
0x1800012d4  mov     rbx, r8
0x1800012d7  lea     rcx, [rbp+8C0h+var_81C]; void *
0x1800012de  xor     eax, eax
0x1800012e0  mov     r8d, 7FCh; Size
0x1800012e6  xor     edx, edx; Val
0x1800012e8  mov     [rbp+8C0h+var_820], eax
0x1800012ee  mov     edi, r9d
0x1800012f1  call    memset_0
0x1800012f6  test    rbx, rbx
0x1800012f9  jz      loc_1800014BF
0x1800012ff  test    cs:byte_18002E903, 10h
0x180001306  jnz     loc_1800013F6
0x18000130c  mov     eax, [rbx+20h]
0x18000130f  mov     [rsp+9C0h+arg_0], rsi
0x180001317  cmp     eax, 456Ah
0x18000131c  jnz     loc_1800013B9
0x180001322  lea     rcx, [rbx+0F8h]; lpCriticalSection
0x180001329  call    cs:__imp_EnterCriticalSection
0x180001330  nop     dword ptr [rax+rax+00h]
0x180001335  test    edi, edi
0x180001337  jnz     loc_18000149E
0x18000133d  cmp     [rbx+18Bh], dil
0x180001344  jnz     loc_18000149E
0x18000134a  and     dword ptr [rbx+0D4h], 0FFFFFBFFh
0x180001354  lea     rdi, [rbx+0A8h]
0x18000135b  lock inc dword ptr [rdi]
0x18000135e  mov     rcx, [rbx+120h]; pwk
0x180001365  call    cs:__imp_SubmitThreadpoolWork
0x18000136c  nop     dword ptr [rax+rax+00h]
0x180001371  lea     rcx, [rbx+0F8h]; lpCriticalSection
0x180001378  call    cs:__imp_LeaveCriticalSection
0x18000137f  nop     dword ptr [rax+rax+00h]
0x180001384  mov     eax, 0FFFFFFFFh
0x180001389  lock xadd [rdi], eax
0x18000138d  cmp     eax, 1
0x180001390  jz      loc_180001B27
0x180001396  mov     rsi, [rsp+9C0h+arg_0]
0x18000139e  mov     rcx, [rbp+8C0h+var_20]
0x1800013a5  xor     rcx, rsp; StackCookie
0x1800013a8  call    __security_check_cookie
0x1800013ad  add     rsp, 9B0h
0x1800013b4  pop     rdi
0x1800013b5  pop     rbx
0x1800013b6  pop     rbp
0x1800013b7  retn
0x1800013b9  sub     eax, 4569h
0x1800013be  jz      loc_180001AEC
0x1800013c4  mov     [rsp+9C0h+arg_8], r14
0x1800013cc  sub     eax, 3
0x1800013cf  jz      loc_180001911
0x1800013d5  sub     eax, 2
0x1800013d8  jz      loc_18000182C
0x1800013de  sub     eax, 3
0x1800013e1  jz      loc_1800016B4
0x1800013e7  cmp     eax, 2
0x1800013ea  jz      short loc_180001449
0x1800013ec  mov     r14, [rsp+9C0h+arg_8]
0x1800013f4  jmp     short loc_180001396
0x1800013f6  mov     r8d, [rbx+20h]
0x1800013fa  lea     rdx, aOverlapinfoWit; "OverlapInfo with id %x received [%d - %"...
0x180001401  xor     eax, eax
0x180001403  mov     dword ptr [rsp+9C0h+plpszSubStringArray], edi
0x180001407  mov     r9d, edi
0x18000140a  mov     word ptr [rbp+8C0h+var_820], ax
0x180001411  lea     rcx, [rbp+8C0h+var_820]
0x180001418  call    FormatRRASErrorString
0x18000141d  test    cs:byte_18002E903, 10h
0x180001424  jz      loc_18000130C
0x18000142a  lea     r8, [rbp+8C0h+var_820]
0x180001431  lea     rdx, RasSSTPSvcTraceInfo
0x180001438  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000143f  call    McTemplateU0z_EventWriteTransfer
0x180001444  jmp     loc_18000130C
0x180001449  mov     rax, cs:SstpSvcGlobals
0x180001450  mov     rcx, [rax+0B0h]
0x180001457  test    rcx, rcx
0x18000145a  jnz     loc_1800014EB
0x180001460  xor     esi, esi
0x180001462  mov     r14d, 57h ; 'W'
0x180001468  test    edi, edi
0x18000146a  jz      loc_180001522
0x180001470  mov     eax, 0FFFFFFFFh
0x180001475  lock xadd [rsi+0D0h], eax
0x18000147d  cmp     eax, 1
0x180001480  jnz     loc_1800013EC
0x180001486  mov     rax, [rsi+0D8h]
0x18000148d  lea     rcx, [rsi+0D0h]
0x180001494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001499  jmp     loc_1800013EC
0x18000149e  and     dword ptr [rbx+0D4h], 0FFFFFFFBh
0x1800014a5  lea     rcx, [rbx-28h]
0x1800014a9  mov     edx, 2
0x1800014ae  call    InitiateCallContextCleanup
0x1800014b3  lea     rdi, [rbx+0A8h]
0x1800014ba  jmp     loc_180001384
0x1800014bf  test    cs:byte_18002E903, 8
0x1800014c6  jz      loc_18000139E
0x1800014cc  lea     r8, aNoOverlappedIn; "No Overlapped info found..."
0x1800014d3  lea     rdx, RasSSTPSvcTraceError
0x1800014da  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800014e1  call    McTemplateU0z_EventWriteTransfer
0x1800014e6  jmp     loc_18000139E
0x1800014eb  mov     eax, [rcx]
0x1800014ed  mov     edx, [rbx+2Ch]
0x1800014f0  dec     eax
0x1800014f2  mov     rcx, [rcx+8]
0x1800014f6  and     eax, edx
0x1800014f8  cdqe
0x1800014fa  shl     rax, 5
0x1800014fe  cmp     [rcx+rax], edx
0x180001501  jnz     short loc_180001515
0x180001503  mov     rsi, [rcx+rax+8]
0x180001508  test    rsi, rsi
0x18000150b  jz      short loc_180001517
0x18000150d  xor     r14d, r14d
0x180001510  jmp     loc_180001468
0x180001515  xor     esi, esi
0x180001517  mov     r14d, 6
0x18000151d  jmp     loc_180001468
0x180001522  cmp     dword ptr [rbx+40h], 0
0x180001526  jnz     loc_18000162C
0x18000152c  lock inc dword ptr [rsi+0D0h]
0x180001533  lea     rcx, [rsi+120h]; lpCriticalSection
0x18000153a  call    cs:__imp_EnterCriticalSection
0x180001541  nop     dword ptr [rax+rax+00h]
0x180001546  cmp     byte ptr [rsi+1B3h], 0
0x18000154d  jnz     loc_180001614
0x180001553  test    cs:byte_18002E903, 10h
0x18000155a  jz      short loc_1800015A2
0x18000155c  xor     eax, eax
0x18000155e  lea     r8, [rsi+228h]
0x180001565  lea     rdx, aCoidHsEstablis; "CoId=%hs:Established connection success"...
0x18000156c  mov     word ptr [rbp+8C0h+var_820], ax
0x180001573  lea     rcx, [rbp+8C0h+var_820]
0x18000157a  call    FormatRRASErrorString
0x18000157f  test    cs:byte_18002E903, 10h
0x180001586  jz      short loc_1800015A2
0x180001588  lea     r8, [rbp+8C0h+var_820]
0x18000158f  lea     rdx, RasSSTPSvcTraceInfo
0x180001596  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000159d  call    McTemplateU0z_EventWriteTransfer
0x1800015a2  lea     rcx, [rsi+50h]
0x1800015a6  mov     dword ptr [rsi+70h], 4571h
0x1800015ad  xorps   xmm0, xmm0
0x1800015b0  mov     qword ptr [rsp+9C0h+dwErrorCode], rcx; LPOVERLAPPED
0x1800015b5  movups  xmmword ptr [rcx], xmm0
0x1800015b8  lea     rdx, [rsi+78h]; lpInBuffer
0x1800015bc  mov     r8d, 8; nInBufferSize
0x1800015c2  movups  xmmword ptr [rcx+10h], xmm0
0x1800015c6  mov     eax, [rsi+0F0h]
0x1800015cc  mov     ecx, 12801Ch; dwIoControlCode
0x1800015d1  mov     r9, rdx; lpOutBuffer
0x1800015d4  mov     [rdx], eax
0x1800015d6  mov     byte ptr [rsi+7Ch], 0
0x1800015da  mov     dword ptr [rsp+9C0h+plpszSubStringArray], 8; DWORD
0x1800015e2  call    AsyncSstpDeviceControl
0x1800015e7  test    eax, eax
0x1800015e9  jz      short loc_18000160D
0x1800015eb  xor     edx, edx
0x1800015ed  mov     byte ptr [rsi+1B1h], 0
0x1800015f4  mov     rcx, rsi
0x1800015f7  call    InitiateCallContextCleanup
0x1800015fc  lea     rcx, [rsi+0D0h]
0x180001603  call    DereferenceRefCount
0x180001608  jmp     loc_180001470
0x18000160d  mov     byte ptr [rsi+1B1h], 1
0x180001614  lea     rcx, [rsi+120h]; lpCriticalSection
0x18000161b  call    cs:__imp_LeaveCriticalSection
0x180001622  nop     dword ptr [rax+rax+00h]
0x180001627  jmp     loc_180001470
0x18000162c  test    cs:byte_18002E903, 8
0x180001633  jz      short loc_18000167E
0x180001635  xor     eax, eax
0x180001637  lea     r8, [rsi+228h]
0x18000163e  mov     r9d, r14d
0x180001641  mov     word ptr [rbp+8C0h+var_820], ax
0x180001648  lea     rdx, aCoidHsClientFs; "CoId=%hs: CLIENT_FSM_FAILED, Status=%d"
0x18000164f  lea     rcx, [rbp+8C0h+var_820]
0x180001656  call    FormatRRASErrorString
0x18000165b  test    cs:byte_18002E903, 8
0x180001662  jz      short loc_18000167E
0x180001664  lea     r8, [rbp+8C0h+var_820]
0x18000166b  lea     rdx, RasSSTPSvcTraceError
0x180001672  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180001679  call    McTemplateU0z_EventWriteTransfer
0x18000167e  lea     r9, [rsi+228h]
0x180001685  mov     r8d, r14d
0x180001688  mov     ecx, 5; dwMessageId
0x18000168d  call    LogEventWithErrorParameter
0x180001692  lea     rcx, [rsi+120h]; lpCriticalSection
0x180001699  call    cs:__imp_EnterCriticalSection
0x1800016a0  nop     dword ptr [rax+rax+00h]
0x1800016a5  xor     edx, edx
0x1800016a7  mov     rcx, rsi
0x1800016aa  call    InitiateCallContextCleanup
0x1800016af  jmp     loc_180001470
0x1800016b4  test    edi, edi
0x1800016b6  jnz     loc_18000181B
0x1800016bc  lea     rcx, [rbx+0D0h]; lpCriticalSection
0x1800016c3  call    cs:__imp_EnterCriticalSection
0x1800016ca  nop     dword ptr [rax+rax+00h]
0x1800016cf  cmp     [rbx+2Ch], dil
0x1800016d3  jz      loc_180001810
0x1800016d9  test    cs:byte_18002E903, 8
0x1800016e0  jz      short loc_180001728
0x1800016e2  xor     eax, eax
0x1800016e4  lea     r8, [rbx+1D8h]
0x1800016eb  lea     rdx, aCoidHsCryptoBi; "CoId=%hs: Crypto Binding failed notific"...
0x1800016f2  mov     word ptr [rbp+8C0h+var_820], ax
0x1800016f9  lea     rcx, [rbp+8C0h+var_820]
0x180001700  call    FormatRRASErrorString
0x180001705  test    cs:byte_18002E903, 8
0x18000170c  jz      short loc_180001728
0x18000170e  lea     r8, [rbp+8C0h+var_820]
0x180001715  lea     rdx, RasSSTPSvcTraceError
0x18000171c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180001723  call    McTemplateU0z_EventWriteTransfer
0x180001728  mov     rax, cs:SstpSvcGlobals
0x18000172f  cmp     qword ptr [rax+48h], 0
0x180001734  jz      loc_180001810
0x18000173a  xorps   xmm0, xmm0
0x18000173d  lea     rcx, [rsp+9C0h+var_960]; void *
0x180001742  xor     edx, edx; Val
0x180001744  mov     r8d, 56h ; 'V'; Size
0x18000174a  movups  xmmword ptr [rsp+9C0h+var_988], xmm0
0x18000174f  movups  [rsp+9C0h+var_978], xmm0
0x180001754  call    memset_0
0x180001759  xor     edx, edx; Val
0x18000175b  lea     rcx, [rbp+8C0h+var_8B0]; void *
0x18000175f  mov     r8d, 86h; Size
0x180001765  call    memset_0
0x18000176a  lea     rcx, [rbx+199h]
0x180001771  mov     r9d, 2Bh ; '+'
0x180001777  lea     r8, [rsp+9C0h+var_960]
0x18000177c  mov     edx, 14h
0x180001781  call    ConvertByteArrayToString
0x180001786  lea     rcx, [rbx+1ADh]
0x18000178d  mov     r9d, 43h ; 'C'
0x180001793  lea     r8, [rbp+8C0h+var_8B0]
0x180001797  mov     edx, 20h ; ' '
0x18000179c  call    ConvertByteArrayToString
0x1800017a1  lea     r8, [rbx+1D8h]
0x1800017a8  lea     rcx, [rbp+8C0h+WideCharStr]; lpWideCharStr
0x1800017ac  call    ConvertCorrelationIdToWideChar
0x1800017b1  mov     rcx, cs:SstpSvcGlobals
0x1800017b8  lea     rax, [rbp+8C0h+WideCharStr]
0x1800017bc  mov     [rsp+9C0h+var_988], rax
0x1800017c1  mov     edx, 1; dwEventType
0x1800017c6  lea     rax, [rsp+9C0h+var_960]
0x1800017cb  mov     qword ptr [rsp+9C0h+var_978+8], 0
0x1800017d4  mov     [rsp+9C0h+var_988+8], rax
0x1800017d9  mov     r9d, 3; dwSubStringCount
0x1800017df  lea     rax, [rbp+8C0h+var_8B0]
0x1800017e3  mov     [rsp+9C0h+dwErrorCode], 0; dwErrorCode
0x1800017eb  mov     qword ptr [rsp+9C0h+var_978], rax
0x1800017f0  mov     r8d, 6; dwMessageId
0x1800017f6  mov     rcx, [rcx+48h]; hLogHandle
0x1800017fa  lea     rax, [rsp+9C0h+var_988]
0x1800017ff  mov     [rsp+9C0h+plpszSubStringArray], rax; plpszSubStringArray
0x180001804  call    cs:__imp_RouterLogEventW
0x18000180b  nop     dword ptr [rax+rax+00h]
0x180001810  xor     edx, edx
0x180001812  lea     rcx, [rbx-50h]
0x180001816  call    InitiateCallContextCleanup
0x18000181b  lea     rcx, [rbx+80h]
0x180001822  call    DereferenceRefCount
0x180001827  jmp     loc_1800013EC
0x18000182c  lea     rcx, [rbx+120h]; lpCriticalSection
0x180001833  test    edi, edi
0x180001835  jnz     loc_1800018E5
0x18000183b  lock inc dword ptr [rbx+0D0h]
0x180001842  call    cs:__imp_EnterCriticalSection
0x180001849  nop     dword ptr [rax+rax+00h]
0x18000184e  and     dword ptr [rbx+0FCh], 0FFFF7FFFh
0x180001858  cmp     [rbx+1B3h], dil
0x18000185f  jnz     short loc_1800018D0
0x180001861  lea     rcx, [rbx+50h]
0x180001865  mov     dword ptr [rbx+70h], 4571h
0x18000186c  xorps   xmm0, xmm0
0x18000186f  mov     qword ptr [rsp+9C0h+dwErrorCode], rcx; LPOVERLAPPED
0x180001874  movups  xmmword ptr [rcx], xmm0
0x180001877  lea     rdx, [rbx+78h]; lpInBuffer
0x18000187b  mov     r8d, 8; nInBufferSize
0x180001881  movups  xmmword ptr [rcx+10h], xmm0
0x180001885  mov     eax, [rbx+0F0h]
0x18000188b  mov     ecx, 12801Ch; dwIoControlCode
0x180001890  mov     r9, rdx; lpOutBuffer
0x180001893  mov     [rdx], eax
0x180001895  mov     [rbx+7Ch], dil
0x180001899  mov     dword ptr [rsp+9C0h+plpszSubStringArray], 8; DWORD
0x1800018a1  call    AsyncSstpDeviceControl
0x1800018a6  test    eax, eax
  ... truncated ...
```
