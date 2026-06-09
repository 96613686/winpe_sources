# SeqExecute

- ea: `0x180003108`
- end: `0x18000367a`
- name: `SeqExecute`
- size: `1394`
- prototype: `__int64 __fastcall(LPVOID lpParameter)`
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x18000c1a0`
- `0x18000c850`

## callees

- `0x180001f24`
- `0x180002250`
- `0x180002344`
- `0x1800026fc`
- `0x180003108`
- `0x1800044f0`
- `0x180006740`
- `0x180006c44`
- `0x180007184`
- `0x18000720c`
- `0x1800086c4`
- `0x180008a6c`
- `0x180008abc`
- `0x180008b00`
- `0x18001dc70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003148`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003342`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003361`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000342c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003516`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003603`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003148`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003342`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003361`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000342c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003516`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003603`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003505`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800035a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003505`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800035a2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000357b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000357b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000320b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000320b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000311c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000311c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800035b3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800035b3`

## string_xrefs

- `0x18000315c`: `Unable to startup async event processing threads`

## pseudocode

```c
__int64 __fastcall SeqExecute(char *lpParameter)
{
  int v2; // ebp
  DWORD v3; // ebx
  int v4; // eax
  int v6; // edi
  __int64 NonDeletedItem; // rax
  unsigned int v8; // ecx
  __int64 v9; // rax
  __int64 FirstEvent; // rax
  _DWORD *v11; // rdi
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // r14
  __int64 v15; // r15
  __int64 NextListItem; // rbx
  unsigned int v17; // ebx
  int v18; // ebx
  DWORD v19; // eax
  unsigned int v20; // ecx
  const char *v21; // rdx
  int v22; // eax
  DWORD v23; // ebx
  int v24; // eax
  DWORD v25; // ebx
  int v26; // eax
  DWORD v27; // ebx
  int v28; // eax
  DWORD LastError; // ebx
  int v30; // eax
  unsigned int v31; // ebx
  DWORD v32; // ebx
  int v33; // eax
  LPCWSTR lpModuleName; // [rsp+A8h] [rbp+0h]
  unsigned int v35; // [rsp+B0h] [rbp+8h]
  int v36; // [rsp+B8h] [rbp+10h]
  int v37; // [rsp+C0h] [rbp+18h]

  v2 = 1;
  *((_DWORD *)lpParameter + 44) = GetCurrentThreadId();
  *((_DWORD *)lpParameter + 34) = 1;
  if ( (unsigned int)pStartWorkerThreads(lpParameter) )
  {
    *((_DWORD *)lpParameter + 35) = 0;
    v35 = 3;
    v6 = 1;
    v36 = 1;
    while ( v6 )
    {
      if ( WaitForSingleObject(*((HANDLE *)lpParameter + 21), 0xFFFFFFFF) == -1 )
      {
        LastError = GetLastError();
        v30 = (unsigned int)ConstructPartialMsgW(0x200008Bu, "Could not wait on event queue handle (SEQ7)");
        WdsSetupLogMessageW(
          v30,
          589824,
          (int)L"D",
          0,
          2656,
          L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
          (__int64)L"SeqExecute",
          lpModuleName,
          LastError,
          0,
          0);
        return 3;
      }
      pLock(lpParameter);
      while ( 1 )
      {
        if ( *((_DWORD *)lpParameter + 37) )
        {
          v27 = GetLastError();
          v28 = (unsigned int)ConstructPartialMsgW(
                                0x400008Cu,
                                "SeqExecute -- stopping, since WdsExitImmediate() was called");
          WdsSetupLogMessageW(
            v28,
            589824,
            (int)L"D",
            0,
            2670,
            L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
            (__int64)L"SeqExecute",
            lpModuleName,
            v27,
            0,
            0);
          goto LABEL_29;
        }
        if ( *((_DWORD *)lpParameter + 36) )
        {
          NonDeletedItem = privateGetNonDeletedItem(**((_QWORD **)lpParameter + 7), 1);
          v8 = *((_DWORD *)lpParameter + 38);
          if ( v8 < *(_DWORD *)(NonDeletedItem + 56) )
          {
            v25 = GetLastError();
            v26 = (unsigned int)ConstructPartialMsgW(
                                  0x400008Du,
                                  "SeqExecute -- stopping, since termination group# < current group#");
            WdsSetupLogMessageW(
              v26,
              589824,
              (int)L"D",
              0,
              2686,
              L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
              (__int64)L"SeqExecute",
              lpModuleName,
              v25,
              0,
              0);
            goto LABEL_29;
          }
          if ( v8 == *(_DWORD *)(NonDeletedItem + 56)
            && (unsigned int)IsManagedListEmpty(*(_QWORD *)(NonDeletedItem + 40))
            && !*((_DWORD *)lpParameter + 40) )
          {
            v23 = GetLastError();
            v24 = (unsigned int)ConstructPartialMsgW(
                                  0x400008Eu,
                                  "SeqExecute -- stopping, since termination group reached");
            WdsSetupLogMessageW(
              v24,
              589824,
              (int)L"D",
              0,
              2700,
              L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
              (__int64)L"SeqExecute",
              lpModuleName,
              v23,
              0,
              0);
LABEL_29:
            v6 = 0;
            v35 = 1;
            v36 = 0;
            goto LABEL_32;
          }
        }
        if ( *((_DWORD *)lpParameter + 40) )
        {
          v9 = privateGetNonDeletedItem(**((_QWORD **)lpParameter + 7), 1);
          FirstEvent = privateGetNonDeletedItem(**(_QWORD **)(v9 + 40), 1);
        }
        else
        {
          FirstEvent = pGetFirstEvent(lpParameter, 0);
        }
        v11 = (_DWORD *)FirstEvent;
        if ( !FirstEvent )
          break;
        v12 = *(_QWORD *)(FirstEvent + 72);
        v13 = privateGetNonDeletedItem(**((_QWORD **)lpParameter + 7), 1);
        if ( v12 != v13 )
        {
          v14 = v13;
          v15 = v12;
          do
          {
            NextListItem = GetNextListItem(v14);
            DeleteListItem(*((_QWORD *)lpParameter + 7), v14);
            v14 = NextListItem;
          }
          while ( v15 != NextListItem );
        }
        v17 = *(_DWORD *)(*((_QWORD *)v11 + 9) + 56LL);
        DelinkListItem(*(_QWORD *)v11, v11);
        CallSubscribers(lpParameter);
        if ( v11[24] )
        {
          if ( (unsigned int)pInsertEvent(*((_QWORD *)lpParameter + 9), v11, v17, 0) )
          {
            v18 = 2749;
            v19 = GetLastError();
            v20 = 67109008;
            v21 = "Successfully backed up PERMANENT event";
          }
          else
          {
            v18 = 2745;
            v19 = GetLastError();
            v20 = 33554575;
            v21 = "Failed to backup PERMANENT event!!";
          }
          v37 = v19;
          v22 = (unsigned int)ConstructPartialMsgW(v20, v21);
          WdsSetupLogMessageW(
            v22,
            589824,
            (int)L"D",
            0,
            v18,
            L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
            (__int64)L"SeqExecute",
            lpModuleName,
            v37,
            0,
            0);
        }
        else
        {
          pDestructEvent(v11);
        }
      }
      v6 = v36;
LABEL_32:
      LeaveCriticalSection((LPCRITICAL_SECTION)(lpParameter + 184));
    }
    SetEvent(*((HANDLE *)lpParameter + 31));
    do
    {
      pLock(lpParameter);
      v2 = *((_DWORD *)lpParameter + 58) != 0 ? v2 : 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)(lpParameter + 184));
      Sleep(0xAu);
    }
    while ( v2 );
    v31 = v35;
    if ( *((_DWORD *)lpParameter + 39) )
    {
      *((_QWORD *)lpParameter + 18) = 0;
      if ( (int)SeqPublishImmediateEx((_DWORD)lpParameter, 0, (unsigned int)L"SEQ Control", 2, 0, 0) >= 3 )
      {
        v32 = GetLastError();
        v33 = (unsigned int)ConstructPartialMsgW(0x4000091u, "Couldn't Publish EVENT_SERIALIZE_BEFORE_EXIT");
        WdsSetupLogMessageW(
          v33,
          589824,
          (int)L"D",
          0,
          2783,
          L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
          (__int64)L"SeqExecute",
          lpModuleName,
          v32,
          0,
          0);
        return v35;
      }
    }
    return v31;
  }
  else
  {
    v3 = GetLastError();
    v4 = (unsigned int)ConstructPartialMsgW(0x200008Au, "Unable to startup async event processing threads");
    WdsSetupLogMessageW(
      v4,
      589824,
      (int)L"D",
      0,
      2643,
      L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
      (__int64)L"SeqExecute",
      lpModuleName,
      v3,
      0,
      0);
    return 3;
  }
}

```

## disassembly

```asm
0x180003108  push    rbx
0x18000310a  push    rbp
0x18000310b  push    rsi
0x18000310c  push    rdi
0x18000310d  push    r12
0x18000310f  push    r13
0x180003111  push    r14
0x180003113  push    r15
0x180003115  sub     rsp, 68h
0x180003119  mov     rsi, rcx
0x18000311c  call    cs:__imp_GetCurrentThreadId
0x180003123  nop     dword ptr [rax+rax+00h]
0x180003128  mov     ebp, 1
0x18000312d  mov     rcx, rsi; lpParameter
0x180003130  mov     [rsi+0B0h], eax
0x180003136  mov     [rsi+88h], ebp
0x18000313c  call    pStartWorkerThreads
0x180003141  xor     r14d, r14d
0x180003144  test    eax, eax
0x180003146  jnz     short loc_1800031C3
0x180003148  call    cs:__imp_GetLastError
0x18000314f  nop     dword ptr [rax+rax+00h]
0x180003154  mov     rdi, [rsp+0A8h]
0x18000315c  lea     rdx, aUnableToStartu; "Unable to startup async event processin"...
0x180003163  mov     ecx, 200008Ah; unsigned int
0x180003168  mov     ebx, eax
0x18000316a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000316f  mov     [rsp+0A8h+var_58], r14d; int
0x180003174  lea     r12, aSeqexecute; "SeqExecute"
0x18000317b  mov     [rsp+0A8h+var_60], r14; __int64
0x180003180  lea     r13, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x180003187  mov     [rsp+0A8h+var_68], ebx; int
0x18000318b  lea     r8, aD_1; "D"
0x180003192  mov     [rsp+0A8h+lpModuleName], rdi; lpModuleName
0x180003197  mov     edx, 90000h; int
0x18000319c  mov     [rsp+0A8h+var_78], r12; __int64
0x1800031a1  mov     [rsp+0A8h+var_80], r13; unsigned __int16 *
0x1800031a6  mov     [rsp+0A8h+var_88], 0A53h; int
0x1800031ae  xor     r9d, r9d; int
0x1800031b1  mov     rcx, rax; int
0x1800031b4  call    WdsSetupLogMessageW
0x1800031b9  mov     eax, 3
0x1800031be  jmp     loc_180003668
0x1800031c3  mov     [rsi+8Ch], r14d
0x1800031ca  lea     r12, aSeqexecute; "SeqExecute"
0x1800031d1  lea     r14, aD_1; "D"
0x1800031d8  mov     [rsp+0A8h+arg_0], 3
0x1800031e3  mov     edi, ebp
0x1800031e5  mov     [rsp+0A8h+arg_8], ebp
0x1800031ec  lea     r13, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x1800031f3  mov     r15d, 90000h
0x1800031f9  test    edi, edi
0x1800031fb  jz      loc_180003574
0x180003201  mov     rcx, [rsi+0A8h]; hHandle
0x180003208  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000320b  call    cs:__imp_WaitForSingleObject
0x180003212  nop     dword ptr [rax+rax+00h]
0x180003217  cmp     eax, 0FFFFFFFFh
0x18000321a  jz      loc_180003516
0x180003220  mov     rcx, rsi
0x180003223  call    pLock
0x180003228  xor     ebx, ebx
0x18000322a  cmp     [rsi+94h], ebx
0x180003230  jnz     loc_1800034A2
0x180003236  cmp     [rsi+90h], ebx
0x18000323c  jz      short loc_180003276
0x18000323e  mov     rcx, [rsi+38h]
0x180003242  mov     edx, ebp
0x180003244  mov     rcx, [rcx]
0x180003247  call    privateGetNonDeletedItem
0x18000324c  mov     ecx, [rsi+98h]
0x180003252  cmp     ecx, [rax+38h]
0x180003255  jb      loc_18000342C
0x18000325b  jnz     short loc_180003276
0x18000325d  mov     rcx, [rax+28h]
0x180003261  call    IsManagedListEmpty
0x180003266  test    eax, eax
0x180003268  jz      short loc_180003276
0x18000326a  cmp     [rsi+0A0h], ebx
0x180003270  jz      loc_1800033D7
0x180003276  cmp     [rsi+0A0h], ebx
0x18000327c  jz      short loc_18000329C
0x18000327e  mov     rcx, [rsi+38h]
0x180003282  mov     edx, ebp
0x180003284  mov     rcx, [rcx]
0x180003287  call    privateGetNonDeletedItem
0x18000328c  mov     edx, ebp
0x18000328e  mov     rcx, [rax+28h]
0x180003292  mov     rcx, [rcx]
0x180003295  call    privateGetNonDeletedItem
0x18000329a  jmp     short loc_1800032A6
0x18000329c  xor     edx, edx
0x18000329e  mov     rcx, rsi
0x1800032a1  call    pGetFirstEvent
0x1800032a6  mov     rdi, rax
0x1800032a9  test    rax, rax
0x1800032ac  jz      loc_1800034F7
0x1800032b2  mov     rcx, [rsi+38h]
0x1800032b6  mov     edx, ebp
0x1800032b8  mov     rbx, [rax+48h]
0x1800032bc  mov     rcx, [rcx]
0x1800032bf  call    privateGetNonDeletedItem
0x1800032c4  cmp     rbx, rax
0x1800032c7  jz      short loc_1800032FB
0x1800032c9  mov     r14, rax
0x1800032cc  mov     r15, rbx
0x1800032cf  mov     rcx, r14
0x1800032d2  call    GetNextListItem
0x1800032d7  mov     rcx, [rsi+38h]
0x1800032db  mov     rdx, r14
0x1800032de  mov     rbx, rax
0x1800032e1  call    DeleteListItem
0x1800032e6  mov     r14, rbx
0x1800032e9  cmp     r15, rbx
0x1800032ec  jnz     short loc_1800032CF
0x1800032ee  lea     r14, aD_1; "D"
0x1800032f5  mov     r15d, 90000h
0x1800032fb  mov     rax, [rdi+48h]
0x1800032ff  mov     rdx, rdi
0x180003302  mov     rcx, [rdi]
0x180003305  mov     ebx, [rax+38h]
0x180003308  call    DelinkListItem
0x18000330d  mov     rcx, rsi
0x180003310  call    CallSubscribers
0x180003315  cmp     dword ptr [rdi+60h], 0
0x180003319  jz      loc_1800033CA
0x18000331f  mov     rcx, [rsi+48h]
0x180003323  xor     r9d, r9d
0x180003326  mov     r8d, ebx
0x180003329  mov     rdx, rdi
0x18000332c  call    pInsertEvent
0x180003331  mov     rdi, [rsp+0A8h]
0x180003339  test    eax, eax
0x18000333b  jnz     short loc_18000335C
0x18000333d  mov     ebx, 0AB9h
0x180003342  call    cs:__imp_GetLastError
0x180003349  nop     dword ptr [rax+rax+00h]
0x18000334e  mov     ecx, 200008Fh
0x180003353  lea     rdx, aFailedToBackup_0; "Failed to backup PERMANENT event!!"
0x18000335a  jmp     short loc_180003379
0x18000335c  mov     ebx, 0ABDh
0x180003361  call    cs:__imp_GetLastError
0x180003368  nop     dword ptr [rax+rax+00h]
0x18000336d  mov     ecx, 4000090h; unsigned int
0x180003372  lea     rdx, aSuccessfullyBa; "Successfully backed up PERMANENT event"
0x180003379  mov     [rsp+0A8h+arg_10], eax
0x180003380  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180003385  mov     [rsp+0A8h+var_58], 0; int
0x18000338d  mov     rcx, rax; int
0x180003390  mov     eax, [rsp+0A8h+arg_10]
0x180003397  xor     r9d, r9d; int
0x18000339a  mov     [rsp+0A8h+var_60], 0; __int64
0x1800033a3  mov     r8, r14; int
0x1800033a6  mov     [rsp+0A8h+var_68], eax; int
0x1800033aa  mov     edx, r15d; int
0x1800033ad  mov     [rsp+0A8h+lpModuleName], rdi; lpModuleName
0x1800033b2  mov     [rsp+0A8h+var_78], r12; __int64
0x1800033b7  mov     [rsp+0A8h+var_80], r13; unsigned __int16 *
0x1800033bc  mov     [rsp+0A8h+var_88], ebx; int
0x1800033c0  call    WdsSetupLogMessageW
0x1800033c5  jmp     loc_180003228
0x1800033ca  mov     rcx, rdi; lpMem
0x1800033cd  call    pDestructEvent
0x1800033d2  jmp     loc_180003228
0x1800033d7  call    cs:__imp_GetLastError
0x1800033de  nop     dword ptr [rax+rax+00h]
0x1800033e3  mov     rdi, [rsp+0A8h]
0x1800033eb  lea     rdx, aSeqexecuteStop_0; "SeqExecute -- stopping, since terminati"...
0x1800033f2  mov     ecx, 400008Eh; unsigned int
0x1800033f7  mov     ebx, eax
0x1800033f9  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800033fe  mov     [rsp+0A8h+var_58], 0
0x180003406  mov     [rsp+0A8h+var_60], 0
0x18000340f  mov     [rsp+0A8h+var_68], ebx
0x180003413  mov     [rsp+0A8h+lpModuleName], rdi
0x180003418  mov     [rsp+0A8h+var_78], r12
0x18000341d  mov     [rsp+0A8h+var_80], r13
0x180003422  mov     [rsp+0A8h+var_88], 0A8Ch
0x18000342a  jmp     short loc_18000347F
0x18000342c  call    cs:__imp_GetLastError
0x180003433  nop     dword ptr [rax+rax+00h]
0x180003438  mov     rdi, [rsp+0A8h]
0x180003440  lea     rdx, aSeqexecuteStop; "SeqExecute -- stopping, since terminati"...
0x180003447  mov     ecx, 400008Dh; unsigned int
0x18000344c  mov     ebx, eax
0x18000344e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180003453  mov     [rsp+0A8h+var_58], 0; int
0x18000345b  mov     [rsp+0A8h+var_60], 0; __int64
0x180003464  mov     [rsp+0A8h+var_68], ebx; int
0x180003468  mov     [rsp+0A8h+lpModuleName], rdi; lpModuleName
0x18000346d  mov     [rsp+0A8h+var_78], r12; __int64
0x180003472  mov     [rsp+0A8h+var_80], r13; unsigned __int16 *
0x180003477  mov     [rsp+0A8h+var_88], 0A7Eh; int
0x18000347f  mov     rcx, rax; int
0x180003482  xor     r9d, r9d; int
0x180003485  mov     r8, r14; int
0x180003488  mov     edx, r15d; int
0x18000348b  call    WdsSetupLogMessageW
0x180003490  xor     edi, edi
0x180003492  mov     [rsp+0A8h+arg_0], ebp
0x180003499  mov     [rsp+0A8h+arg_8], edi
0x1800034a0  jmp     short loc_1800034FE
0x1800034a2  call    cs:__imp_GetLastError
0x1800034a9  nop     dword ptr [rax+rax+00h]
0x1800034ae  mov     rdi, [rsp+0A8h]
0x1800034b6  lea     rdx, aSeqexecuteStop_1; "SeqExecute -- stopping, since WdsExitIm"...
0x1800034bd  mov     ecx, 400008Ch; unsigned int
0x1800034c2  mov     ebx, eax
0x1800034c4  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800034c9  mov     [rsp+0A8h+var_58], 0
0x1800034d1  mov     [rsp+0A8h+var_60], 0
0x1800034da  mov     [rsp+0A8h+var_68], ebx
0x1800034de  mov     [rsp+0A8h+lpModuleName], rdi
0x1800034e3  mov     [rsp+0A8h+var_78], r12
0x1800034e8  mov     [rsp+0A8h+var_80], r13
0x1800034ed  mov     [rsp+0A8h+var_88], 0A6Eh
0x1800034f5  jmp     short loc_18000347F
0x1800034f7  mov     edi, [rsp+0A8h+arg_8]
0x1800034fe  lea     rcx, [rsi+0B8h]; lpCriticalSection
0x180003505  call    cs:__imp_LeaveCriticalSection
0x18000350c  nop     dword ptr [rax+rax+00h]
0x180003511  jmp     loc_1800031F9
0x180003516  call    cs:__imp_GetLastError
0x18000351d  nop     dword ptr [rax+rax+00h]
0x180003522  mov     rdi, [rsp+0A8h]
0x18000352a  lea     rdx, aCouldNotWaitOn; "Could not wait on event queue handle (S"...
0x180003531  mov     ecx, 200008Bh; unsigned int
0x180003536  mov     ebx, eax
0x180003538  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000353d  mov     [rsp+0A8h+var_58], 0
0x180003545  mov     r8, r14
0x180003548  mov     [rsp+0A8h+var_60], 0
0x180003551  mov     edx, r15d
0x180003554  mov     [rsp+0A8h+var_68], ebx
0x180003558  mov     [rsp+0A8h+lpModuleName], rdi
0x18000355d  mov     [rsp+0A8h+var_78], r12
0x180003562  mov     [rsp+0A8h+var_80], r13
0x180003567  mov     [rsp+0A8h+var_88], 0A60h
0x18000356f  jmp     loc_1800031AE
0x180003574  mov     rcx, [rsi+0F8h]; hEvent
0x18000357b  call    cs:__imp_SetEvent
0x180003582  nop     dword ptr [rax+rax+00h]
0x180003587  mov     rcx, rsi
0x18000358a  call    pLock
0x18000358f  mov     eax, [rsi+0E8h]
0x180003595  neg     eax
0x180003597  sbb     ecx, ecx
0x180003599  and     ebp, ecx
0x18000359b  lea     rcx, [rsi+0B8h]; lpCriticalSection
0x1800035a2  call    cs:__imp_LeaveCriticalSection
0x1800035a9  nop     dword ptr [rax+rax+00h]
0x1800035ae  mov     ecx, 0Ah; dwMilliseconds
0x1800035b3  call    cs:__imp_Sleep
0x1800035ba  nop     dword ptr [rax+rax+00h]
0x1800035bf  test    ebp, ebp
0x1800035c1  jnz     short loc_180003587
0x1800035c3  mov     ebx, [rsp+0A8h+arg_0]
0x1800035ca  xor     ebp, ebp
0x1800035cc  cmp     [rsi+9Ch], ebp
0x1800035d2  jz      loc_180003666
0x1800035d8  mov     [rsp+0A8h+var_80], rbp
0x1800035dd  lea     r9d, [rbp+2]
0x1800035e1  lea     r8, aSeqControl; "SEQ Control"
0x1800035e8  mov     qword ptr [rsp+0A8h+var_88], rbp
0x1800035ed  xor     edx, edx
0x1800035ef  mov     [rsi+90h], rbp
0x1800035f6  mov     rcx, rsi
0x1800035f9  call    SeqPublishImmediateEx
0x1800035fe  cmp     eax, 3
0x180003601  jl      short loc_180003666
0x180003603  call    cs:__imp_GetLastError
0x18000360a  nop     dword ptr [rax+rax+00h]
0x18000360f  mov     rdi, [rsp+0A8h]
0x180003617  lea     rdx, aCouldnTPublish; "Couldn't Publish EVENT_SERIALIZE_BEFORE"...
0x18000361e  mov     ecx, 4000091h; unsigned int
0x180003623  mov     ebx, eax
0x180003625  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000362a  mov     [rsp+0A8h+var_58], ebp; int
0x18000362e  mov     rcx, rax; int
0x180003631  mov     [rsp+0A8h+var_60], rbp; __int64
0x180003636  xor     r9d, r9d; int
0x180003639  mov     [rsp+0A8h+var_68], ebx; int
0x18000363d  mov     r8, r14; int
0x180003640  mov     [rsp+0A8h+lpModuleName], rdi; lpModuleName
0x180003645  mov     edx, r15d; int
0x180003648  mov     [rsp+0A8h+var_78], r12; __int64
0x18000364d  mov     [rsp+0A8h+var_80], r13; unsigned __int16 *
0x180003652  mov     [rsp+0A8h+var_88], 0ADFh; int
0x18000365a  call    WdsSetupLogMessageW
0x18000365f  mov     ebx, [rsp+0A8h+arg_0]
0x180003666  mov     eax, ebx
0x180003668  add     rsp, 68h
0x18000366c  pop     r15
0x18000366e  pop     r14
0x180003670  pop     r13
0x180003672  pop     r12
0x180003674  pop     rdi
0x180003675  pop     rsi
0x180003676  pop     rbp
0x180003677  pop     rbx
  ... truncated ...
```
