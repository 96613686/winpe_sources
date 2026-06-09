# HandleManagerNetTopoChange(unsigned __int64 *,bool,_NetTopoChangeSource)

- ea: `0x180010748`
- end: `0x180010b6b`
- name: `?HandleManagerNetTopoChange@@YAJPEA_K_NW4_NetTopoChangeSource@@@Z`
- size: `1059`
- prototype: `__int64 __fastcall(unsigned __int64 *, char, int)`
- caller_count: `5`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x18000ea00`
- `0x180010730`
- `0x180010e24`
- `0x1800120f0`
- `0x1800123b0`

## callees

- `0x18000a818`
- `0x18000e620`
- `0x18000ee90`
- `0x180010748`
- `0x1800127a0`
- `0x180018138`
- `0x18001d9a0`
- `0x1800279b0`
- `0x18002a980`
- `0x18002b7b0`
- `0x18003f60c`
- `0x18004cd1c`
- `0x18004d3e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180010780`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180010a99`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180010780`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180010a99`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800108b3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800109ae`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800108b3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800109ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010ab8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010ab8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800107ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800107ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010958`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010958`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a53`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180010940`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180010a3b`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180010940`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180010a3b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180010910`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180010a0b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180010910`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180010a0b`

## string_xrefs

- `0x1800107ee`: `A net topo refresh request already pending. Ignoring this notification\n`
- `0x180010b41`: `Failed in handling network topology change, restart service async`

## pseudocode

```c
__int64 __fastcall HandleManagerNetTopoChange(unsigned __int64 *a1, char a2, int a3)
{
  unsigned __int64 v3; // rbx
  void *v6; // rcx
  void *v7; // rdx
  void *v8; // r9
  int started; // ebx
  signed int LastError; // eax
  int v11; // ebx
  signed int v12; // eax
  signed int v13; // eax
  signed int v14; // eax
  int v15; // eax
  unsigned int v17; // [rsp+30h] [rbp-78h]
  char v18; // [rsp+44h] [rbp-64h]
  char v19; // [rsp+46h] [rbp-62h]
  __int64 v20; // [rsp+48h] [rbp-60h]
  unsigned __int64 v22; // [rsp+C8h] [rbp+20h] BYREF

  v3 = a3;
  v18 = 0;
  v22 = 0;
  v19 = 1;
  v20 = _set_se_translator(SeTransFunc);
  AccurateGetTickCount(&v22);
  qword_1800A4348 = v3;
  EnterCriticalSection(&CriticalSection);
  if ( a2 )
  {
    HandleManagerNetTopoChangeActual((void *)1, 0);
  }
  else if ( byte_1800A4648 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(67) )
      FileLogAdd(L"A net topo refresh request already pending. Ignoring this notification\n");
    v19 = 0;
  }
  else
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TCPIP_2025_Wave4_W32Time_Timer_Fix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TCPIP_2025_Wave4_W32Time_Timer_Fix>::GetImpl'::`2'::impl) )
      myStopTimerQueueTimerNoWait(v6, qword_1800A4650);
    else
      myStopTimerQueueTimer(v6, qword_1800A4650, 0);
    started = myStartTimerQueueTimer(
                qword_1800A4650,
                v7,
                (void (*)(void *, unsigned __int8))HandleManagerNetTopoChangeActual,
                v8,
                0xAFC8u,
                0,
                v17);
    if ( started < 0 )
    {
      if ( (unsigned __int8)FileLogAllowEntry(67) )
        FileLogAdd(L"Failed to schedule a net topo refresh request. Ignoring error: 0x%08x\n", (unsigned int)started);
    }
    else
    {
      byte_1800A4648 = 1;
      if ( (unsigned __int8)FileLogAllowEntry(67) )
        FileLogAdd(L"A net topo refresh will run in %d milliseconds\n", 45000);
    }
  }
  if ( a2 )
    goto LABEL_55;
  if ( a1 == &qword_1800A37B8 )
  {
    if ( !ResetEvent(qword_1800A3710) )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_43;
    }
    v11 = AllowShutdown(0);
    if ( v11 < 0 )
      goto LABEL_43;
    v18 = 1;
    if ( qword_1800A3778 )
    {
      UnregisterWaitEx(qword_1800A3778, 0);
      qword_1800A3778 = 0;
    }
    qword_1800A3778 = (HANDLE)RegisterWaitForSingleObjectEx(
                                qword_1800A3710,
                                HandleManagerNetTopoChangeNoRPC4,
                                0,
                                0xFFFFFFFFLL,
                                8);
    if ( !qword_1800A3778 )
    {
      v12 = GetLastError();
      v11 = v12;
      if ( v12 > 0 )
        v11 = (unsigned __int16)v12 | 0x80070000;
      goto LABEL_43;
    }
    v11 = RequestNetTopoChangeNotification(a1);
    if ( v11 < 0 )
      goto LABEL_43;
LABEL_55:
    _set_se_translator(v20);
    v11 = 0;
    goto LABEL_43;
  }
  if ( a1 != &s )
    goto LABEL_55;
  if ( ResetEvent(qword_1800A3718) )
  {
    v11 = AllowShutdown(0);
    if ( v11 < 0 )
      goto LABEL_43;
    v18 = 1;
    if ( qword_1800A3780 )
    {
      UnregisterWaitEx(qword_1800A3780, 0);
      qword_1800A3780 = 0;
    }
    qword_1800A3780 = (HANDLE)RegisterWaitForSingleObjectEx(
                                qword_1800A3718,
                                HandleManagerNetTopoChangeNoRPC6,
                                0,
                                0xFFFFFFFFLL,
                                8);
    if ( qword_1800A3780 )
    {
      v11 = RequestNetTopoChangeNotification(a1);
      if ( v11 < 0 )
        goto LABEL_43;
      goto LABEL_55;
    }
    v14 = GetLastError();
    v11 = v14;
    if ( v14 > 0 )
      v11 = (unsigned __int16)v14 | 0x80070000;
  }
  else
  {
    v13 = GetLastError();
    v11 = v13;
    if ( v13 > 0 )
      v11 = (unsigned __int16)v13 | 0x80070000;
  }
LABEL_43:
  LeaveCriticalSection(&CriticalSection);
  if ( v18 )
  {
    v15 = AllowShutdown(1);
    if ( v15 < 0 && v11 >= 0 )
      v11 = v15;
  }
  if ( v19 )
    LogThrottledEvent(&_W32TimeRegistrationHandle, W32TIME_OPS_TIME_RESYNC_EVENT, L"ii", 60000, a3);
  if ( (int)(v11 + 0x80000000) >= 0 && v11 != -2147023835 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(73) )
      FileLogAdd(L"Failed in handling network topology change, restart service async");
    NotifyShutdown(v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180010748  mov     rax, rsp
0x18001074b  mov     [rax+8], rbx
0x18001074f  mov     [rax+18h], r8d
0x180010753  push    rsi
0x180010754  push    rdi
0x180010755  push    r14
0x180010757  sub     rsp, 90h
0x18001075e  movsxd  rbx, r8d
0x180010761  mov     r14b, dl
0x180010764  mov     rsi, rcx
0x180010767  xor     edi, edi
0x180010769  mov     [rax-64h], dil
0x18001076d  mov     [rax-63h], dil
0x180010771  mov     [rax+20h], rdi
0x180010775  mov     byte ptr [rax-62h], 1
0x180010779  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x180010780  call    cs:__imp__set_se_translator
0x180010787  nop     dword ptr [rax+rax+00h]
0x18001078c  mov     [rsp+0A8h+var_60], rax
0x180010791  lea     rcx, [rsp+0A8h+arg_18]; unsigned __int64 *
0x180010799  call    ?AccurateGetTickCount@@YAXPEA_K@Z; AccurateGetTickCount(unsigned __int64 *)
0x18001079e  mov     cs:qword_1800A4348, rbx
0x1800107a5  lea     rcx, CriticalSection; lpCriticalSection
0x1800107ac  call    cs:__imp_EnterCriticalSection
0x1800107b3  nop     dword ptr [rax+rax+00h]
0x1800107b8  mov     ebx, edi
0x1800107ba  mov     [rsp+0A8h+var_68], ebx
0x1800107be  mov     [rsp+0A8h+var_63], 1
0x1800107c3  test    r14b, r14b
0x1800107c6  jz      short loc_1800107D7
0x1800107c8  xor     edx, edx; unsigned __int8
0x1800107ca  lea     ecx, [rdi+1]; void *
0x1800107cd  call    ?HandleManagerNetTopoChangeActual@@YAXPEAXE@Z; HandleManagerNetTopoChangeActual(void *,uchar)
0x1800107d2  jmp     loc_180010893
0x1800107d7  cmp     cs:byte_1800A4648, dil
0x1800107de  jz      short loc_180010804
0x1800107e0  mov     ecx, 43h ; 'C'
0x1800107e5  call    FileLogAllowEntry
0x1800107ea  test    al, al
0x1800107ec  jz      short loc_1800107FA
0x1800107ee  lea     rcx, aANetTopoRefres; "A net topo refresh request already pend"...
0x1800107f5  call    FileLogAdd
0x1800107fa  mov     [rsp+0A8h+var_62], dil
0x1800107ff  jmp     loc_180010893
0x180010804  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TCPIP_2025_Wave4_W32Time_Timer_Fix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TCPIP_2025_Wave4_W32Time_Timer_Fix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TCPIP_2025_Wave4_W32Time_Timer_Fix> `wil::Feature<__WilFeatureTraits_Feature_TCPIP_2025_Wave4_W32Time_Timer_Fix>::GetImpl(void)'::`2'::impl
0x18001080b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TCPIP_2025_Wave4_W32Time_Timer_Fix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TCPIP_2025_Wave4_W32Time_Timer_Fix>::__private_IsEnabled(void)
0x180010810  mov     rdx, cs:qword_1800A4650; void *
0x180010817  test    al, al
0x180010819  jz      short loc_180010822
0x18001081b  call    ?myStopTimerQueueTimerNoWait@@YAJPEAX0@Z; myStopTimerQueueTimerNoWait(void *,void *)
0x180010820  jmp     short loc_18001082A
0x180010822  xor     r8d, r8d; void *
0x180010825  call    ?myStopTimerQueueTimer@@YAJPEAX00@Z; myStopTimerQueueTimer(void *,void *,void *)
0x18001082a  mov     [rsp+0A8h+var_80], edi; unsigned int
0x18001082e  mov     [rsp+0A8h+var_88], 0AFC8h; unsigned int
0x180010836  lea     r8, ?HandleManagerNetTopoChangeActual@@YAXPEAXE@Z; void (*)(void *, unsigned __int8)
0x18001083d  mov     rcx, cs:qword_1800A4650; lpCriticalSection
0x180010844  call    ?myStartTimerQueueTimer@@YAJPEAX0P6AX0E@Z0KKK@Z; myStartTimerQueueTimer(void *,void *,void (*)(void *,uchar),void *,ulong,ulong,ulong)
0x180010849  mov     ebx, eax
0x18001084b  mov     [rsp+0A8h+var_68], eax
0x18001084f  mov     ecx, 43h ; 'C'
0x180010854  test    eax, eax
0x180010856  js      short loc_180010876
0x180010858  mov     cs:byte_1800A4648, 1
0x18001085f  call    FileLogAllowEntry
0x180010864  test    al, al
0x180010866  jz      short loc_18001088D
0x180010868  mov     edx, 0AFC8h
0x18001086d  lea     rcx, aANetTopoRefres_0; "A net topo refresh will run in %d milli"...
0x180010874  jmp     short loc_180010888
0x180010876  call    FileLogAllowEntry
0x18001087b  test    al, al
0x18001087d  jz      short loc_18001088D
0x18001087f  mov     edx, ebx
0x180010881  lea     rcx, aFailedToSchedu; "Failed to schedule a net topo refresh r"...
0x180010888  call    FileLogAdd
0x18001088d  mov     ebx, edi
0x18001088f  mov     [rsp+0A8h+var_68], ebx
0x180010893  test    r14b, r14b
0x180010896  jnz     loc_180010A88
0x18001089c  lea     rax, qword_1800A37B8
0x1800108a3  cmp     rsi, rax
0x1800108a6  jnz     loc_180010997
0x1800108ac  mov     rcx, cs:qword_1800A3710; hEvent
0x1800108b3  call    cs:__imp_ResetEvent
0x1800108ba  nop     dword ptr [rax+rax+00h]
0x1800108bf  test    eax, eax
0x1800108c1  jnz     short loc_1800108E7
0x1800108c3  call    cs:__imp_GetLastError
0x1800108ca  nop     dword ptr [rax+rax+00h]
0x1800108cf  mov     ebx, eax
0x1800108d1  test    eax, eax
0x1800108d3  jle     short loc_1800108DE
0x1800108d5  movzx   ebx, ax
0x1800108d8  or      ebx, 80070000h
0x1800108de  mov     [rsp+0A8h+var_68], ebx
0x1800108e2  jmp     loc_180010AB1
0x1800108e7  xor     ecx, ecx; int
0x1800108e9  call    ?AllowShutdown@@YAJH@Z; AllowShutdown(int)
0x1800108ee  mov     ebx, eax
0x1800108f0  mov     [rsp+0A8h+var_68], eax
0x1800108f4  test    eax, eax
0x1800108f6  jns     short loc_1800108FD
0x1800108f8  jmp     loc_180010AB1
0x1800108fd  mov     [rsp+0A8h+var_64], 1
0x180010902  mov     rcx, cs:qword_1800A3778; WaitHandle
0x180010909  test    rcx, rcx
0x18001090c  jz      short loc_180010923
0x18001090e  xor     edx, edx; CompletionEvent
0x180010910  call    cs:__imp_UnregisterWaitEx
0x180010917  nop     dword ptr [rax+rax+00h]
0x18001091c  mov     cs:qword_1800A3778, rdi
0x180010923  mov     [rsp+0A8h+var_88], 8
0x18001092b  or      r9d, 0FFFFFFFFh
0x18001092f  xor     r8d, r8d
0x180010932  lea     rdx, ?HandleManagerNetTopoChangeNoRPC4@@YAXPEAXE@Z; HandleManagerNetTopoChangeNoRPC4(void *,uchar)
0x180010939  mov     rcx, cs:qword_1800A3710
0x180010940  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180010947  nop     dword ptr [rax+rax+00h]
0x18001094c  mov     cs:qword_1800A3778, rax
0x180010953  test    rax, rax
0x180010956  jnz     short loc_18001097C
0x180010958  call    cs:__imp_GetLastError
0x18001095f  nop     dword ptr [rax+rax+00h]
0x180010964  mov     ebx, eax
0x180010966  test    eax, eax
0x180010968  jle     short loc_180010973
0x18001096a  movzx   ebx, ax
0x18001096d  or      ebx, 80070000h
0x180010973  mov     [rsp+0A8h+var_68], ebx
0x180010977  jmp     loc_180010AB1
0x18001097c  mov     rcx, rsi; unsigned __int64 *
0x18001097f  call    ?RequestNetTopoChangeNotification@@YAJPEA_K@Z; RequestNetTopoChangeNotification(unsigned __int64 *)
0x180010984  mov     ebx, eax
0x180010986  mov     [rsp+0A8h+var_68], eax
0x18001098a  test    eax, eax
0x18001098c  jns     loc_180010A88
0x180010992  jmp     loc_180010AB1
0x180010997  lea     rax, s
0x18001099e  cmp     rsi, rax
0x1800109a1  jnz     loc_180010A88
0x1800109a7  mov     rcx, cs:qword_1800A3718; hEvent
0x1800109ae  call    cs:__imp_ResetEvent
0x1800109b5  nop     dword ptr [rax+rax+00h]
0x1800109ba  test    eax, eax
0x1800109bc  jnz     short loc_1800109E2
0x1800109be  call    cs:__imp_GetLastError
0x1800109c5  nop     dword ptr [rax+rax+00h]
0x1800109ca  mov     ebx, eax
0x1800109cc  test    eax, eax
0x1800109ce  jle     short loc_1800109D9
0x1800109d0  movzx   ebx, ax
0x1800109d3  or      ebx, 80070000h
0x1800109d9  mov     [rsp+0A8h+var_68], ebx
0x1800109dd  jmp     loc_180010AB1
0x1800109e2  xor     ecx, ecx; int
0x1800109e4  call    ?AllowShutdown@@YAJH@Z; AllowShutdown(int)
0x1800109e9  mov     ebx, eax
0x1800109eb  mov     [rsp+0A8h+var_68], eax
0x1800109ef  test    eax, eax
0x1800109f1  jns     short loc_1800109F8
0x1800109f3  jmp     loc_180010AB1
0x1800109f8  mov     [rsp+0A8h+var_64], 1
0x1800109fd  mov     rcx, cs:qword_1800A3780; WaitHandle
0x180010a04  test    rcx, rcx
0x180010a07  jz      short loc_180010A1E
0x180010a09  xor     edx, edx; CompletionEvent
0x180010a0b  call    cs:__imp_UnregisterWaitEx
0x180010a12  nop     dword ptr [rax+rax+00h]
0x180010a17  mov     cs:qword_1800A3780, rdi
0x180010a1e  mov     [rsp+0A8h+var_88], 8
0x180010a26  or      r9d, 0FFFFFFFFh
0x180010a2a  xor     r8d, r8d
0x180010a2d  lea     rdx, ?HandleManagerNetTopoChangeNoRPC6@@YAXPEAXE@Z; HandleManagerNetTopoChangeNoRPC6(void *,uchar)
0x180010a34  mov     rcx, cs:qword_1800A3718
0x180010a3b  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180010a42  nop     dword ptr [rax+rax+00h]
0x180010a47  mov     cs:qword_1800A3780, rax
0x180010a4e  test    rax, rax
0x180010a51  jnz     short loc_180010A74
0x180010a53  call    cs:__imp_GetLastError
0x180010a5a  nop     dword ptr [rax+rax+00h]
0x180010a5f  mov     ebx, eax
0x180010a61  test    eax, eax
0x180010a63  jle     short loc_180010A6E
0x180010a65  movzx   ebx, ax
0x180010a68  or      ebx, 80070000h
0x180010a6e  mov     [rsp+0A8h+var_68], ebx
0x180010a72  jmp     short loc_180010AB1
0x180010a74  mov     rcx, rsi; unsigned __int64 *
0x180010a77  call    ?RequestNetTopoChangeNotification@@YAJPEA_K@Z; RequestNetTopoChangeNotification(unsigned __int64 *)
0x180010a7c  mov     ebx, eax
0x180010a7e  mov     [rsp+0A8h+var_68], eax
0x180010a82  test    eax, eax
0x180010a84  jns     short loc_180010A88
0x180010a86  jmp     short loc_180010AB1
0x180010a88  jmp     short loc_180010A94
0x180010a8a  jmp     short loc_180010A8E
0x180010a8c  jmp     short $+2
0x180010a8e  xor     edi, edi
0x180010a90  mov     ebx, [rsp+0A8h+var_68]
0x180010a94  mov     rcx, [rsp+0A8h+var_60]
0x180010a99  call    cs:__imp__set_se_translator
0x180010aa0  nop     dword ptr [rax+rax+00h]
0x180010aa5  test    ebx, ebx
0x180010aa7  cmovns  ebx, edi
0x180010aaa  cmp     [rsp+0A8h+var_63], dil
0x180010aaf  jz      short loc_180010AC4
0x180010ab1  lea     rcx, CriticalSection; lpCriticalSection
0x180010ab8  call    cs:__imp_LeaveCriticalSection
0x180010abf  nop     dword ptr [rax+rax+00h]
0x180010ac4  cmp     [rsp+0A8h+var_64], dil
0x180010ac9  jz      short loc_180010ADE
0x180010acb  mov     ecx, 1; int
0x180010ad0  call    ?AllowShutdown@@YAJH@Z; AllowShutdown(int)
0x180010ad5  test    eax, eax
0x180010ad7  jns     short loc_180010ADE
0x180010ad9  test    ebx, ebx
0x180010adb  cmovns  ebx, eax
0x180010ade  cmp     [rsp+0A8h+var_62], dil
0x180010ae3  jz      short loc_180010B1F
0x180010ae5  movsxd  rcx, [rsp+0A8h+arg_10]
0x180010aed  mov     rax, [rsp+0A8h+arg_18]
0x180010af5  mov     qword ptr [rsp+0A8h+var_80], rax
0x180010afa  mov     qword ptr [rsp+0A8h+var_88], rcx
0x180010aff  mov     r9d, 0EA60h
0x180010b05  lea     r8, aIi; "ii"
0x180010b0c  lea     rdx, W32TIME_OPS_TIME_RESYNC_EVENT
0x180010b13  lea     rcx, ?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x180010b1a  call    LogThrottledEvent
0x180010b1f  mov     ecx, 80000000h
0x180010b24  lea     eax, [rbx+rcx]
0x180010b27  test    ecx, eax
0x180010b29  jnz     short loc_180010B54
0x180010b2b  cmp     ebx, 80070425h
0x180010b31  jz      short loc_180010B54
0x180010b33  mov     ecx, 49h ; 'I'
0x180010b38  call    FileLogAllowEntry
0x180010b3d  test    al, al
0x180010b3f  jz      short loc_180010B4D
0x180010b41  lea     rcx, aFailedInHandli_1; "Failed in handling network topology cha"...
0x180010b48  call    FileLogAdd
0x180010b4d  mov     ecx, ebx; unsigned int
0x180010b4f  call    ?NotifyShutdown@@YAJK@Z; NotifyShutdown(ulong)
0x180010b54  mov     eax, ebx
0x180010b56  mov     rbx, [rsp+0A8h+arg_0]
0x180010b5e  add     rsp, 90h
0x180010b65  pop     r14
0x180010b67  pop     rdi
0x180010b68  pop     rsi
0x180010b69  retn
```
