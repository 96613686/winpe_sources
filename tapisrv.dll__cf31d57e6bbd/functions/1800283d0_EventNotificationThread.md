# EventNotificationThread

- ea: `0x1800283d0`
- end: `0x180028ada`
- name: `EventNotificationThread`
- size: `1802`
- prototype: `void __fastcall __noreturn(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x18001f494`
- `0x180026730`
- `0x1800283d0`
- `0x18002c8d4`
- `0x18003dc84`
- `0x18003fb7c`

## import_xrefs

- `RPCRT4!RpcMgmtSetCancelTimeout` at `0x18002843c`
- `RPCRT4!RpcMgmtSetCancelTimeout` at `0x18002843c`
- `RPCRT4!NdrClientCall3` at `0x1800289a7`
- `RPCRT4!NdrClientCall3` at `0x1800289a7`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003fcb4`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003fcb4`
- `KERNEL32!HeapAlloc` at `0x180028466`
- `KERNEL32!HeapAlloc` at `0x18002859e`
- `KERNEL32!HeapAlloc` at `0x1800287dd`
- `KERNEL32!HeapAlloc` at `0x180028466`
- `KERNEL32!HeapAlloc` at `0x18002859e`
- `KERNEL32!HeapAlloc` at `0x1800287dd`
- `KERNEL32!ResetEvent` at `0x180028abd`
- `KERNEL32!ResetEvent` at `0x180028abd`
- `KERNEL32!GetCurrentThread` at `0x180028413`
- `KERNEL32!GetCurrentThread` at `0x180028413`
- `KERNEL32!ExitThread` at `0x18002884b`
- `KERNEL32!ExitThread` at `0x18002884b`
- `KERNEL32!SetThreadPriority` at `0x18002841f`
- `KERNEL32!SetThreadPriority` at `0x18002841f`
- `KERNEL32!WriteFile` at `0x1800286dc`
- `KERNEL32!WriteFile` at `0x1800286dc`
- `KERNEL32!GetTickCount` at `0x1800284cc`
- `KERNEL32!GetTickCount` at `0x180028943`
- `KERNEL32!GetTickCount` at `0x1800284cc`
- `KERNEL32!GetTickCount` at `0x180028943`
- `KERNEL32!CloseHandle` at `0x18002882b`
- `KERNEL32!CloseHandle` at `0x18002882b`
- `KERNEL32!GetLastError` at `0x1800286e6`
- `KERNEL32!GetLastError` at `0x1800286e6`
- `KERNEL32!Sleep` at `0x180028499`
- `KERNEL32!Sleep` at `0x180028499`
- `KERNEL32!WaitForSingleObject` at `0x18002871f`
- `KERNEL32!WaitForSingleObject` at `0x18002871f`
- `KERNEL32!LeaveCriticalSection` at `0x180028563`
- `KERNEL32!LeaveCriticalSection` at `0x18002869c`
- `KERNEL32!LeaveCriticalSection` at `0x1800287a3`
- `KERNEL32!LeaveCriticalSection` at `0x180028807`
- `KERNEL32!LeaveCriticalSection` at `0x18002893d`
- `KERNEL32!LeaveCriticalSection` at `0x180028a9c`
- `KERNEL32!LeaveCriticalSection` at `0x180028563`
- `KERNEL32!LeaveCriticalSection` at `0x18002869c`
- `KERNEL32!LeaveCriticalSection` at `0x1800287a3`
- `KERNEL32!LeaveCriticalSection` at `0x180028807`
- `KERNEL32!LeaveCriticalSection` at `0x18002893d`
- `KERNEL32!LeaveCriticalSection` at `0x180028a9c`
- `KERNEL32!EnterCriticalSection` at `0x1800284e0`
- `KERNEL32!EnterCriticalSection` at `0x180028746`
- `KERNEL32!EnterCriticalSection` at `0x1800284e0`
- `KERNEL32!EnterCriticalSection` at `0x180028746`

## string_xrefs

- `0x180028402`: `EventNotificationThread: enter`
- `0x180028429`: `Could not raise priority of EventNotificationThread`
- `0x18002854b`: `EventNotificationThread: timeout, cleaning up Dg client=x%p`
- `0x1800286ef`: `EventNotificationThread: Writefile(mailslot) failed, err=%u`
- `0x1800289bf`: `EventNotificationThread: exception #%d`
- `0x1800289ec`: `EventNotificationThread: rpc timeout (ptClient=x%p)`
- `0x180028838`: `EventNotificationThread: exit`

## pseudocode

```c
void __fastcall __noreturn EventNotificationThread(LPVOID lpThreadParameter)
{
  unsigned int v1; // r12d
  unsigned int v2; // r13d
  __int64 *v3; // rbx
  HANDLE CurrentThread; // rax
  char *v5; // rsi
  __int64 *v6; // r15
  unsigned int v7; // r14d
  unsigned int k; // r12d
  DWORD v9; // ecx
  char *v10; // rax
  __int64 v11; // rax
  unsigned int v12; // r15d
  DWORD LastError; // eax
  __int64 *i; // r14
  __int64 v15; // rcx
  __int64 *v16; // rax
  unsigned int v17; // eax
  char *v18; // r14
  const void *v19; // rdx
  int v20; // r14d
  unsigned int v21; // r15d
  unsigned int v22; // r14d
  int v23; // eax
  __int64 v24; // rax
  DWORD TickCount; // eax
  __int64 v26; // r12
  __int64 v27; // [rsp+28h] [rbp-90h]
  int j; // [rsp+30h] [rbp-88h]
  __int64 v29; // [rsp+50h] [rbp-68h]
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp-58h] BYREF
  char *v31; // [rsp+68h] [rbp-50h]
  __int64 *v32; // [rsp+70h] [rbp-48h]
  unsigned int v33; // [rsp+C0h] [rbp+8h]
  DWORD v34; // [rsp+D0h] [rbp+18h]

  v33 = (unsigned int)lpThreadParameter;
  v1 = (unsigned int)lpThreadParameter;
  v2 = 512;
  v3 = 0;
  TRACELogPrint(524290, "EventNotificationThread: enter");
  CurrentThread = GetCurrentThread();
  if ( !SetThreadPriority(CurrentThread, 1) )
    TRACELogPrint(65538, "Could not raise priority of EventNotificationThread");
  if ( RpcMgmtSetCancelTimeout(0) )
    TRACELogPrint(65538, "Could not set the RPC cancel timeout");
  v5 = (char *)HeapAlloc(ghTapisrvHeap, 8u, 0x200u);
  if ( !v5 )
  {
LABEL_43:
    ServerFree(v5);
    CloseHandle(*((HANDLE *)gEventNotificationThreadParams + v1));
    _InterlockedDecrement(&dword_180051D08);
    TRACELogPrint(524290, "EventNotificationThread: exit");
    ExitThread(0);
  }
LABEL_6:
  while ( 2 )
  {
    while ( 2 )
    {
      if ( v1 )
      {
        WaitForSingleObject(hEvent, 0xFFFFFFFF);
        if ( dword_180051D20 )
          goto LABEL_43;
        if ( (__int64 *)CnClientMsgPendingListHead != &CnClientMsgPendingListHead )
        {
          while ( 1 )
          {
            EnterCriticalSection(&gCnClientMsgPendingCritSec);
            for ( i = (__int64 *)CnClientMsgPendingListHead; ; i = (__int64 *)*i )
            {
              if ( i == &CnClientMsgPendingListHead )
                goto LABEL_38;
              v3 = i - 28;
              if ( !*((_DWORD *)i + 4) )
                break;
            }
            *((_DWORD *)v3 + 60) = 1;
            v15 = *i;
            v16 = (__int64 *)i[1];
            *v16 = *i;
            *(_QWORD *)(v15 + 8) = v16;
            v3[29] = 0;
            *i = 0;
LABEL_38:
            LeaveCriticalSection(&gCnClientMsgPendingCritSec);
            if ( i == &CnClientMsgPendingListHead )
              break;
            if ( WaitForExclusiveClientAccess(v3) )
            {
              v17 = *((_DWORD *)v3 + 35);
              if ( v17 > v2 )
              {
                v18 = (char *)HeapAlloc(ghTapisrvHeap, 8u, v17);
                if ( !v18 )
                {
                  LeaveCriticalSection(
                    (LPCRITICAL_SECTION)gLockTable
                  + ((unsigned int)gdwPointerToLockTableIndexBits & ((unsigned __int64)v3 >> 4)));
                  v1 = v33;
                  goto LABEL_43;
                }
                ServerFree(v5);
                v5 = v18;
                v2 = *((_DWORD *)v3 + 35);
              }
              v19 = (const void *)v3[20];
              v20 = *((_DWORD *)v3 + 38);
              if ( (unsigned __int64)v19 >= v3[19] )
              {
                v23 = *((_DWORD *)v3 + 36);
                v21 = v23 + *((_DWORD *)v3 + 34) - v3[20];
                v22 = v20 - v23;
              }
              else
              {
                v21 = v20 - (_DWORD)v19;
                v22 = 0;
              }
              memcpy_0(v5, v19, v21);
              if ( v22 )
                memcpy_0(&v5[16 * v21], (const void *)v3[18], v22);
              *((_DWORD *)v3 + 35) = 0;
              v24 = v3[18];
              v3[20] = v24;
              v3[19] = v24;
              v29 = v3[7];
              v32 = (__int64 *)((unsigned __int64)v3 >> 4);
              LeaveCriticalSection(
                (LPCRITICAL_SECTION)gLockTable
              + (((unsigned __int64)v3 >> 4) & (unsigned int)gdwPointerToLockTableIndexBits));
              TickCount = GetTickCount();
              v26 = 16LL * v33;
              v31 = (char *)v26;
              *(_DWORD *)((char *)qword_180051D10 + v26) = TickCount;
              *(_QWORD *)((char *)qword_180051D10 + v26 + 8) = v3;
              for ( j = 5; j; j = 0 )
              {
                LODWORD(v27) = v22 + v21;
                NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 1u, 0, v29, v5, v27);
              }
              *(_QWORD *)((char *)qword_180051D10 + v26 + 8) = 0;
              if ( WaitForExclusiveClientAccess(v3) )
              {
                *((_DWORD *)v3 + 60) = 0;
                LeaveCriticalSection(
                  (LPCRITICAL_SECTION)gLockTable
                + (((unsigned __int64)v3 >> 4) & (unsigned int)gdwPointerToLockTableIndexBits));
              }
            }
          }
          v1 = v33;
        }
        ResetEvent(hEvent);
        continue;
      }
      break;
    }
    Sleep(0x3E8u);
LABEL_8:
    v1 = v33;
    if ( dword_180051D20 )
      goto LABEL_43;
    if ( (__int64 *)DgClientMsgPendingListHead == &DgClientMsgPendingListHead )
      continue;
    break;
  }
  NumberOfBytesWritten = 0;
  v34 = GetTickCount();
  EnterCriticalSection(&gDgClientMsgPendingCritSec);
  v6 = (__int64 *)DgClientMsgPendingListHead;
  v7 = 0;
  for ( k = 16; ; k += 16 )
  {
    if ( v6 == &DgClientMsgPendingListHead )
    {
      LeaveCriticalSection(&gDgClientMsgPendingCritSec);
      v12 = 0;
      v1 = v33;
      if ( v7 )
      {
        do
        {
          if ( !WriteFile(*(HANDLE *)&v5[16 * v12], &v5[16 * v12 + 8], 4u, &NumberOfBytesWritten, 0) )
          {
            LastError = GetLastError();
            TRACELogPrint(65538, "EventNotificationThread: Writefile(mailslot) failed, err=%u", LastError);
          }
          ++v12;
        }
        while ( v12 < v7 );
        v1 = v33;
      }
      goto LABEL_6;
    }
    v9 = v34;
    while ( 1 )
    {
      v3 = v6 - 28;
      v6 = (__int64 *)*v6;
      v32 = v6;
      if ( (int)(*((_DWORD *)v3 + 60) - v34) < 0 )
        break;
      if ( v6 == &DgClientMsgPendingListHead )
        goto LABEL_25;
    }
    if ( v34 - *((_DWORD *)v3 + 61) > gdwRpcTimeout )
    {
      TRACELogPrint(65538, "EventNotificationThread: timeout, cleaning up Dg client=x%p", v3);
      LeaveCriticalSection(&gDgClientMsgPendingCritSec);
      CleanUpClient(v3, 0);
      goto LABEL_8;
    }
    if ( k > v2 )
    {
      v10 = (char *)HeapAlloc(ghTapisrvHeap, 8u, v2 + 512);
      v31 = v10;
      if ( !v10 )
      {
        v6 = &DgClientMsgPendingListHead;
        continue;
      }
      memcpy_0(v10, v5, v2);
      ServerFree(v5);
      v5 = v31;
      v2 += 512;
      v9 = v34;
    }
    *((_DWORD *)v3 + 60) = v9 + 1000;
    *(_QWORD *)&v5[16 * v7] = v3[16];
    v11 = v3[21];
    if ( v11 )
      *(_DWORD *)&v5[16 * v7 + 8] = *(_DWORD *)(v11 + 28);
    else
      *(_DWORD *)&v5[16 * v7 + 8] = 0;
    ++v7;
LABEL_25:
    ;
  }
}

```

## disassembly

```asm
0x1800283d0  mov     [rsp+arg_0], rcx
0x1800283d5  push    rbx
0x1800283d6  push    rsi
0x1800283d7  push    r12
0x1800283d9  push    r13
0x1800283db  push    r14
0x1800283dd  push    r15
0x1800283df  sub     rsp, 88h
0x1800283e6  mov     r12, rcx
0x1800283e9  mov     [rsp+0B8h+var_78], ecx
0x1800283ed  mov     r13d, 200h
0x1800283f3  mov     [rsp+0B8h+arg_8], r13d
0x1800283fb  xor     ebx, ebx
0x1800283fd  mov     [rsp+0B8h+var_70], rbx
0x180028402  lea     rdx, aEventnotificat_2; "EventNotificationThread: enter"
0x180028409  mov     ecx, 80002h
0x18002840e  call    TRACELogPrint
0x180028413  call    cs:__imp_GetCurrentThread
0x180028419  mov     rcx, rax; hThread
0x18002841c  lea     edx, [rbx+1]; nPriority
0x18002841f  call    cs:__imp_SetThreadPriority
0x180028425  test    eax, eax
0x180028427  jnz     short loc_18002843A
0x180028429  lea     rdx, aCouldNotRaiseP_0; "Could not raise priority of EventNotifi"...
0x180028430  mov     ecx, 10002h
0x180028435  call    TRACELogPrint
0x18002843a  xor     ecx, ecx; Timeout
0x18002843c  call    cs:__imp_RpcMgmtSetCancelTimeout
0x180028442  test    eax, eax
0x180028444  jz      short loc_180028457
0x180028446  lea     rdx, aCouldNotSetThe; "Could not set the RPC cancel timeout"
0x18002844d  mov     ecx, 10002h
0x180028452  call    TRACELogPrint
0x180028457  mov     r8, r13; dwBytes
0x18002845a  mov     edx, 8; dwFlags
0x18002845f  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180028466  call    cs:__imp_HeapAlloc
0x18002846c  mov     rsi, rax
0x18002846f  mov     [rsp+0B8h+var_60], rax
0x180028474  test    rax, rax
0x180028477  jz      loc_180028815
0x18002847d  lea     r15, CnClientMsgPendingListHead
0x180028484  lea     r14, DgClientMsgPendingListHead
0x18002848b  test    r12d, r12d
0x18002848e  jnz     loc_180028715
0x180028494  mov     ecx, 3E8h; dwMilliseconds
0x180028499  call    cs:__imp_Sleep
0x18002849f  mov     r12, [rsp+0B8h+arg_0]
0x1800284a7  cmp     cs:dword_180051D20, 0
0x1800284ae  jnz     loc_180028815
0x1800284b4  cmp     cs:DgClientMsgPendingListHead, r14
0x1800284bb  lea     r15, CnClientMsgPendingListHead
0x1800284c2  jz      short loc_18002848B
0x1800284c4  mov     [rsp+0B8h+NumberOfBytesWritten], 0
0x1800284cc  call    cs:__imp_GetTickCount
0x1800284d2  mov     [rsp+0B8h+arg_10], eax
0x1800284d9  lea     rcx, gDgClientMsgPendingCritSec; lpCriticalSection
0x1800284e0  call    cs:__imp_EnterCriticalSection
0x1800284e6  mov     r15, cs:DgClientMsgPendingListHead
0x1800284ed  xor     r14d, r14d
0x1800284f0  mov     [rsp+0B8h+arg_18], r14d
0x1800284f8  lea     r12d, [r14+10h]
0x1800284fc  lea     rdx, DgClientMsgPendingListHead
0x180028503  mov     dword ptr [rsp+0B8h+var_80], r12d
0x180028508  cmp     r15, rdx
0x18002850b  jz      loc_180028695
0x180028511  mov     ecx, [rsp+0B8h+arg_10]
0x180028518  lea     rbx, [r15-0E0h]
0x18002851f  mov     [rsp+0B8h+var_70], rbx
0x180028524  mov     r15, [r15]
0x180028527  mov     [rsp+0B8h+var_48], r15
0x18002852c  cmp     [rbx+0F0h], ecx
0x180028532  jns     loc_180028683
0x180028538  mov     eax, ecx
0x18002853a  sub     eax, [rbx+0F4h]
0x180028540  cmp     eax, cs:gdwRpcTimeout
0x180028546  jbe     short loc_18002857F
0x180028548  mov     r8, rbx
0x18002854b  lea     rdx, aEventnotificat_4; "EventNotificationThread: timeout, clean"...
0x180028552  mov     ecx, 10002h
0x180028557  call    TRACELogPrint
0x18002855c  lea     rcx, gDgClientMsgPendingCritSec; lpCriticalSection
0x180028563  call    cs:__imp_LeaveCriticalSection
0x180028569  xor     edx, edx
0x18002856b  mov     rcx, rbx
0x18002856e  call    CleanUpClient
0x180028573  lea     r14, DgClientMsgPendingListHead
0x18002857a  jmp     loc_18002849F
0x18002857f  cmp     r12d, r13d
0x180028582  jbe     short loc_1800285E9
0x180028584  lea     eax, [r13+200h]
0x18002858b  mov     dword ptr [rsp+0B8h+var_68], eax
0x18002858f  mov     r8d, eax; dwBytes
0x180028592  mov     edx, 8; dwFlags
0x180028597  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18002859e  call    cs:__imp_HeapAlloc
0x1800285a4  mov     [rsp+0B8h+var_50], rax
0x1800285a9  test    rax, rax
0x1800285ac  jz      short loc_18002861B
0x1800285ae  mov     r8d, r13d; Size
0x1800285b1  mov     rdx, rsi; Src
0x1800285b4  mov     rcx, rax; void *
0x1800285b7  call    memcpy_0
0x1800285bc  mov     rcx, rsi; lpMem
0x1800285bf  call    ServerFree
0x1800285c4  mov     rsi, [rsp+0B8h+var_50]
0x1800285c9  mov     [rsp+0B8h+var_60], rsi
0x1800285ce  mov     r13d, dword ptr [rsp+0B8h+var_68]
0x1800285d3  mov     [rsp+0B8h+arg_8], r13d
0x1800285db  mov     ecx, [rsp+0B8h+arg_10]
0x1800285e2  lea     rdx, DgClientMsgPendingListHead
0x1800285e9  lea     eax, [rcx+3E8h]
0x1800285ef  mov     [rbx+0F0h], eax
0x1800285f5  mov     ecx, r14d
0x1800285f8  add     rcx, rcx
0x1800285fb  mov     rax, [rbx+80h]
0x180028602  mov     [rsi+rcx*8], rax
0x180028606  mov     rax, [rbx+0A8h]
0x18002860d  test    rax, rax
0x180028610  jz      short loc_180028627
0x180028612  mov     eax, [rax+1Ch]
0x180028615  mov     [rsi+rcx*8+8], eax
0x180028619  jmp     short loc_18002862F
0x18002861b  lea     rdx, DgClientMsgPendingListHead
0x180028622  mov     r15, rdx
0x180028625  jmp     short loc_18002868C
0x180028627  mov     dword ptr [rsi+rcx*8+8], 0
0x18002862f  jmp     short loc_180028676
0x180028631  mov     r14d, [rsp+0B8h+arg_18]
0x180028639  mov     eax, r14d
0x18002863c  add     rax, rax
0x18002863f  mov     rsi, [rsp+0B8h+var_60]
0x180028644  mov     dword ptr [rsi+rax*8+8], 0
0x18002864c  lea     rdx, DgClientMsgPendingListHead
0x180028653  mov     ecx, [rsp+0B8h+var_78]
0x180028657  mov     [rsp+0B8h+arg_0], rcx
0x18002865f  mov     r13d, [rsp+0B8h+arg_8]
0x180028667  mov     rbx, [rsp+0B8h+var_70]
0x18002866c  mov     r15, [rsp+0B8h+var_48]
0x180028671  mov     r12d, dword ptr [rsp+0B8h+var_80]
0x180028676  inc     r14d
0x180028679  mov     [rsp+0B8h+arg_18], r14d
0x180028681  jmp     short loc_18002868C
0x180028683  cmp     r15, rdx
0x180028686  jnz     loc_180028518
0x18002868c  add     r12d, 10h
0x180028690  jmp     loc_180028503
0x180028695  lea     rcx, gDgClientMsgPendingCritSec; lpCriticalSection
0x18002869c  call    cs:__imp_LeaveCriticalSection
0x1800286a2  xor     r15d, r15d
0x1800286a5  test    r14d, r14d
0x1800286a8  mov     r12, [rsp+0B8h+arg_0]
0x1800286b0  jz      loc_18002847D
0x1800286b6  mov     ecx, r15d
0x1800286b9  shl     rcx, 4
0x1800286bd  lea     rdx, [rcx+8]
0x1800286c1  add     rdx, rsi; lpBuffer
0x1800286c4  mov     [rsp+0B8h+lpOverlapped], 0; lpOverlapped
0x1800286cd  lea     r9, [rsp+0B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800286d2  mov     r8d, 4; nNumberOfBytesToWrite
0x1800286d8  mov     rcx, [rcx+rsi]; hFile
0x1800286dc  call    cs:__imp_WriteFile
0x1800286e2  test    eax, eax
0x1800286e4  jnz     short loc_180028700
0x1800286e6  call    cs:__imp_GetLastError
0x1800286ec  mov     r8d, eax
0x1800286ef  lea     rdx, aEventnotificat_1; "EventNotificationThread: Writefile(mail"...
0x1800286f6  mov     ecx, 10002h
0x1800286fb  call    TRACELogPrint
0x180028700  inc     r15d
0x180028703  cmp     r15d, r14d
0x180028706  jb      short loc_1800286B6
0x180028708  mov     r12, [rsp+0B8h+arg_0]
0x180028710  jmp     loc_18002847D
0x180028715  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180028718  mov     rcx, cs:hEvent; hHandle
0x18002871f  call    cs:__imp_WaitForSingleObject
0x180028725  cmp     cs:dword_180051D20, 0
0x18002872c  jnz     loc_180028815
0x180028732  cmp     cs:CnClientMsgPendingListHead, r15
0x180028739  jz      loc_180028AB6
0x18002873f  lea     rcx, gCnClientMsgPendingCritSec; lpCriticalSection
0x180028746  call    cs:__imp_EnterCriticalSection
0x18002874c  mov     r14, cs:CnClientMsgPendingListHead
0x180028753  cmp     r14, r15
0x180028756  jz      short loc_18002879C
0x180028758  lea     rbx, [r14-0E0h]
0x18002875f  mov     [rsp+0B8h+var_70], rbx
0x180028764  cmp     dword ptr [rbx+0F0h], 0
0x18002876b  jz      short loc_180028772
0x18002876d  mov     r14, [r14]
0x180028770  jmp     short loc_180028753
0x180028772  mov     dword ptr [rbx+0F0h], 1
0x18002877c  mov     rcx, [r14]
0x18002877f  mov     rax, [r14+8]
0x180028783  mov     [rax], rcx
0x180028786  mov     [rcx+8], rax
0x18002878a  mov     qword ptr [rbx+0E8h], 0
0x180028795  mov     qword ptr [r14], 0
0x18002879c  lea     rcx, gCnClientMsgPendingCritSec; lpCriticalSection
0x1800287a3  call    cs:__imp_LeaveCriticalSection
0x1800287a9  cmp     r14, r15
0x1800287ac  jz      loc_180028AAE
0x1800287b2  mov     rcx, rbx
0x1800287b5  call    WaitForExclusiveClientAccess
0x1800287ba  test    rax, rax
0x1800287bd  jz      short loc_18002873F
0x1800287bf  mov     eax, [rbx+8Ch]
0x1800287c5  cmp     eax, r13d
0x1800287c8  jbe     loc_180028871
0x1800287ce  mov     r8d, eax; dwBytes
0x1800287d1  mov     edx, 8; dwFlags
0x1800287d6  mov     rcx, cs:ghTapisrvHeap; hHeap
0x1800287dd  call    cs:__imp_HeapAlloc
0x1800287e3  mov     r14, rax
0x1800287e6  test    rax, rax
0x1800287e9  jnz     short loc_180028852
0x1800287eb  shr     rbx, 4
0x1800287ef  mov     eax, cs:gdwPointerToLockTableIndexBits
0x1800287f5  and     rbx, rax
0x1800287f8  lea     rcx, [rbx+rbx*4]
0x1800287fc  mov     rax, cs:gLockTable
0x180028803  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180028807  call    cs:__imp_LeaveCriticalSection
0x18002880d  mov     r12, [rsp+0B8h+arg_0]
0x180028815  mov     rcx, rsi; lpMem
0x180028818  call    ServerFree
0x18002881d  mov     eax, r12d
0x180028820  mov     rcx, cs:gEventNotificationThreadParams
0x180028827  mov     rcx, [rcx+rax*8]; hObject
0x18002882b  call    cs:__imp_CloseHandle
0x180028831  lock dec cs:dword_180051D08
0x180028838  lea     rdx, aEventnotificat_0; "EventNotificationThread: exit"
0x18002883f  mov     ecx, 80002h
0x180028844  call    TRACELogPrint
0x180028849  xor     ecx, ecx; dwExitCode
0x18002884b  call    cs:__imp_ExitThread
0x180028852  mov     rcx, rsi; lpMem
0x180028855  call    ServerFree
0x18002885a  mov     rsi, r14
0x18002885d  mov     [rsp+0B8h+var_60], r14
0x180028862  mov     r13d, [rbx+8Ch]
0x180028869  mov     [rsp+0B8h+arg_8], r13d
0x180028871  mov     rdx, [rbx+0A0h]; Src
0x180028878  mov     ecx, edx
0x18002887a  mov     r14d, [rbx+98h]
0x180028881  cmp     rdx, [rbx+98h]
0x180028888  jnb     short loc_18002889D
0x18002888a  sub     r14d, edx
0x18002888d  mov     r15d, r14d
0x180028890  mov     [rsp+0B8h+arg_10], r14d
0x180028898  xor     r14d, r14d
0x18002889b  jmp     short loc_1800288BB
0x18002889d  mov     eax, [rbx+90h]
0x1800288a3  mov     r15d, [rbx+88h]
0x1800288aa  sub     r15d, ecx
0x1800288ad  add     r15d, eax
0x1800288b0  mov     [rsp+0B8h+arg_10], r15d
0x1800288b8  sub     r14d, eax
0x1800288bb  mov     [rsp+0B8h+arg_18], r14d
0x1800288c3  mov     r12d, r15d
0x1800288c6  mov     r8d, r15d; Size
0x1800288c9  mov     rcx, rsi; void *
0x1800288cc  call    memcpy_0
0x1800288d1  test    r14d, r14d
0x1800288d4  jz      short loc_1800288EC
0x1800288d6  mov     r8d, r14d; Size
0x1800288d9  add     r12, r12
0x1800288dc  lea     rcx, [rsi+r12*8]; void *
0x1800288e0  mov     rdx, [rbx+90h]; Src
0x1800288e7  call    memcpy_0
0x1800288ec  mov     dword ptr [rbx+8Ch], 0
0x1800288f6  mov     rax, [rbx+90h]
0x1800288fd  mov     [rbx+0A0h], rax
0x180028904  mov     [rbx+98h], rax
0x18002890b  mov     rax, [rbx+38h]
0x18002890f  mov     [rsp+0B8h+var_68], rax
0x180028914  mov     rcx, rbx
0x180028917  shr     rcx, 4
0x18002891b  mov     [rsp+0B8h+var_80], rcx
0x180028920  mov     [rsp+0B8h+var_48], rcx
0x180028925  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18002892b  and     rax, rcx
0x18002892e  lea     rcx, [rax+rax*4]
0x180028932  mov     rax, cs:gLockTable
0x180028939  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18002893d  call    cs:__imp_LeaveCriticalSection
0x180028943  call    cs:__imp_GetTickCount
0x180028949  mov     r12, [rsp+0B8h+arg_0]
0x180028951  mov     r12d, r12d
0x180028954  shl     r12, 4
0x180028958  mov     [rsp+0B8h+var_50], r12
0x18002895d  mov     rcx, cs:qword_180051D10
0x180028964  mov     [r12+rcx], eax
0x180028968  mov     rax, cs:qword_180051D10
0x18002896f  mov     [r12+rax+8], rbx
0x180028974  mov     [rsp+0B8h+var_88], 5
0x18002897c  cmp     [rsp+0B8h+var_88], 0
0x180028981  jz      loc_180028A50
0x180028987  lea     eax, [r14+r15]
  ... truncated ...
```
