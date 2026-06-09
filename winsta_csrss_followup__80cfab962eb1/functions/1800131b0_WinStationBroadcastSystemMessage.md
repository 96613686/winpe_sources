# WinStationBroadcastSystemMessage

- ea: `0x1800131b0`
- end: `0x1800134b5`
- name: `WinStationBroadcastSystemMessage`
- size: `773`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180005b40`
- `0x1800131b0`
- `0x1800134bc`
- `0x180013614`
- `0x180013994`
- `0x1800249e8`
- `0x18002b194`
- `0x18002b228`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001348a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001348a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800133be`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800133be`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18001340f`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18001340f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001343d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001343d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800133e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800133e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001344c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001344c`

## string_xrefs

- `0x18001341d`: `WinStationBroadcastSystemMessage(): failed to wait for thread to exit!`

## pseudocode

```c
__int64 __fastcall WinStationBroadcastSystemMessage(
        CPublicBinding *a1,
        int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6,
        unsigned int a7,
        unsigned __int64 a8,
        __int64 a9,
        int *a10)
{
  unsigned __int8 *v14; // r14
  BSM_DATA_PACKAGE *v15; // rax
  BSM_DATA_PACKAGE *v16; // rax
  unsigned int v17; // edx
  BSM_DATA_PACKAGE *v18; // rbx
  unsigned int v19; // eax
  int v20; // eax
  ULONG SessionId; // ecx
  HANDLE Thread; // rax
  unsigned int v23; // edx
  void *v24; // r14
  DWORD ExitCode; // [rsp+78h] [rbp-19h] BYREF
  unsigned int v26; // [rsp+7Ch] [rbp-15h] BYREF
  unsigned int v27; // [rsp+80h] [rbp-11h] BYREF
  int v28; // [rsp+84h] [rbp-Dh] BYREF
  DWORD ThreadId[2]; // [rsp+88h] [rbp-9h] BYREF

  ExitCode = 1;
  v26 = 0;
  *(_QWORD *)ThreadId = 0;
  v27 = 0;
  v28 = 0;
  if ( !(unsigned __int8)AllocateBSMRpcBuffer(a7, a9, ThreadId, &v27, &v28) )
    return 0;
  if ( a6 )
    v26 = *a6;
  v14 = *(unsigned __int8 **)ThreadId;
  if ( a7 != 26 && a7 != 27 )
  {
    if ( a7 - 536 < 2 )
    {
      ExitCode = WinStationBroadcastSystemMessageWorker(
                   a1,
                   a2,
                   a3,
                   a4,
                   a5,
                   &v26,
                   a7,
                   a8,
                   a9,
                   a10,
                   NtCurrentPeb()->SessionId,
                   *(unsigned __int8 **)ThreadId,
                   v27,
                   v28 != 0);
      if ( a6 )
        *a6 = v26;
      goto LABEL_32;
    }
    _DbgPrintMessage(8, "Request is rejected \n");
    goto LABEL_9;
  }
  v15 = (BSM_DATA_PACKAGE *)operator new(0x80u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v15 )
  {
    v16 = BSM_DATA_PACKAGE::BSM_DATA_PACKAGE(v15);
    ThreadId[0] = 0;
    v18 = v16;
    if ( v16 )
    {
      if ( *((_DWORD *)v16 + 16) )
      {
        *(_QWORD *)v16 = a1;
        *((_DWORD *)v16 + 2) = a2;
        *((_DWORD *)v16 + 4) = a4;
        *((_DWORD *)v16 + 3) = a3;
        *((_DWORD *)v16 + 5) = a5;
        v19 = v26;
        *((_DWORD *)v18 + 7) = a7;
        *((_DWORD *)v18 + 6) = v19;
        *((_QWORD *)v18 + 4) = a8;
        *((_QWORD *)v18 + 5) = a9;
        if ( a10 )
          v20 = *a10;
        else
          v20 = 0;
        *((_DWORD *)v18 + 12) = v20;
        SessionId = NtCurrentPeb()->SessionId;
        *((_DWORD *)v18 + 20) = v27;
        *((_DWORD *)v18 + 21) = v28;
        *((_DWORD *)v18 + 13) = SessionId;
        *((_QWORD *)v18 + 7) = 0;
        *((_QWORD *)v18 + 9) = v14;
        Thread = CreateThread(0, 0, WinStationBSMWorkerThread, v18, 0, ThreadId);
        v24 = Thread;
        if ( Thread )
        {
          MsgWaitForMultipleObjectsLoop(Thread, v23);
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)v18 + 88));
          if ( *((_DWORD *)v18 + 14) )
          {
            if ( a6 )
              *a6 = *((_DWORD *)v18 + 6);
            if ( a10 )
              *a10 = *((_DWORD *)v18 + 12);
            GetExitCodeThread(v24, &ExitCode);
          }
          else
          {
            *((_DWORD *)v18 + 15) = 1;
            _DbgPrintMessage(8, "WinStationBroadcastSystemMessage(): failed to wait for thread to exit!");
            ExitCode = 0;
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v18 + 88));
          CloseHandle(v24);
        }
        else
        {
          ExitCode = 0;
        }
        if ( !*((_DWORD *)v18 + 15) )
          BSM_DATA_PACKAGE::`scalar deleting destructor'(v18, v23);
        return ExitCode;
      }
      BSM_DATA_PACKAGE::`scalar deleting destructor'(v16, v17);
LABEL_9:
      ExitCode = 0;
    }
  }
  else
  {
    ThreadId[0] = 0;
  }
LABEL_32:
  if ( v14 )
    LocalFree(v14);
  return ExitCode;
}

```

## disassembly

```asm
0x1800131b0  mov     rax, rsp
0x1800131b3  mov     [rax+18h], rbx
0x1800131b7  mov     [rax+10h], edx
0x1800131ba  mov     [rax+8], rcx
0x1800131be  push    rbp
0x1800131bf  push    rsi
0x1800131c0  push    rdi
0x1800131c1  push    r12
0x1800131c3  push    r13
0x1800131c5  push    r14
0x1800131c7  push    r15
0x1800131c9  lea     rbp, [rax-3Fh]
0x1800131cd  sub     rsp, 90h
0x1800131d4  mov     r15, [rbp+37h+arg_40]
0x1800131db  lea     rax, [rbp+37h+var_44]
0x1800131df  mov     esi, [rbp+37h+arg_30]
0x1800131e2  xor     r14d, r14d
0x1800131e5  mov     r12d, r9d
0x1800131e8  mov     [rbp+37h+ExitCode], 1
0x1800131ef  mov     r13d, r8d
0x1800131f2  mov     [rbp+37h+var_4C], r14d
0x1800131f6  mov     ebx, edx
0x1800131f8  mov     qword ptr [rbp+37h+ThreadId], r14
0x1800131fc  mov     rdx, r15
0x1800131ff  mov     [rbp+37h+var_48], r14d
0x180013203  lea     r9, [rbp+37h+var_48]
0x180013207  mov     [rbp+37h+var_44], r14d
0x18001320b  lea     r8, [rbp+37h+ThreadId]
0x18001320f  mov     qword ptr [rsp+0C0h+dwCreationFlags], rax
0x180013214  mov     ecx, esi
0x180013216  call    AllocateBSMRpcBuffer
0x18001321b  test    al, al
0x18001321d  jnz     short loc_180013226
0x18001321f  xor     eax, eax
0x180013221  jmp     loc_180013499
0x180013226  mov     rdi, [rbp+37h+arg_28]
0x18001322a  test    rdi, rdi
0x18001322d  jz      short loc_180013234
0x18001322f  mov     eax, [rdi]
0x180013231  mov     [rbp+37h+var_4C], eax
0x180013234  mov     r14, qword ptr [rbp+37h+ThreadId]
0x180013238  mov     eax, esi
0x18001323a  sub     eax, 1Ah
0x18001323d  jz      loc_1800132F4
0x180013243  sub     eax, 1
0x180013246  jz      loc_1800132F4
0x18001324c  sub     eax, 1FDh
0x180013251  jz      short loc_180013275
0x180013253  cmp     eax, 1
0x180013256  jz      short loc_180013275
0x180013258  lea     rdx, aRequestIsRejec_0; "Request is rejected \n"
0x18001325f  mov     ecx, 8; int
0x180013264  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180013269  mov     [rbp+37h+ExitCode], 0
0x180013270  jmp     loc_180013482
0x180013275  mov     rcx, gs:60h
0x18001327e  mov     r9d, r12d; unsigned int
0x180013281  cmp     [rbp+37h+var_44], 0
0x180013285  mov     r8d, r13d; unsigned int
0x180013288  mov     edx, ebx; int
0x18001328a  setnz   al
0x18001328d  mov     [rsp+68h], al; unsigned __int8
0x180013291  mov     eax, [rbp+37h+var_48]
0x180013294  mov     [rsp+0C0h+var_60], eax; unsigned int
0x180013298  mov     eax, [rcx+2C0h]
0x18001329e  mov     rcx, [rbp+37h+arg_0]; this
0x1800132a2  mov     [rsp+0C0h+var_68], r14; unsigned __int8 *
0x1800132a7  mov     [rsp+0C0h+var_70], eax; unsigned int
0x1800132ab  mov     rax, [rbp+37h+arg_48]
0x1800132b2  mov     [rsp+0C0h+var_78], rax; int *
0x1800132b7  mov     rax, [rbp+37h+arg_38]
0x1800132bb  mov     [rsp+0C0h+var_80], r15; __int64
0x1800132c0  mov     [rsp+0C0h+var_88], rax; unsigned __int64
0x1800132c5  lea     rax, [rbp+37h+var_4C]
0x1800132c9  mov     [rsp+0C0h+var_90], esi; unsigned int
0x1800132cd  mov     [rsp+0C0h+lpThreadId], rax; unsigned int *
0x1800132d2  mov     eax, [rbp+37h+arg_20]
0x1800132d5  mov     [rsp+0C0h+dwCreationFlags], eax; unsigned int
0x1800132d9  call    ?WinStationBroadcastSystemMessageWorker@@YAJPEAXHKKKPEAKK_K_JPEAJKPEAEKE@Z; WinStationBroadcastSystemMessageWorker(void *,int,ulong,ulong,ulong,ulong *,ulong,unsigned __int64,__int64,long *,ulong,uchar *,ulong,uchar)
0x1800132de  mov     [rbp+37h+ExitCode], eax
0x1800132e1  test    rdi, rdi
0x1800132e4  jz      loc_180013482
0x1800132ea  mov     eax, [rbp+37h+var_4C]
0x1800132ed  mov     [rdi], eax
0x1800132ef  jmp     loc_180013482
0x1800132f4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800132fb  mov     ecx, 80h; unsigned __int64
0x180013300  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180013305  test    rax, rax
0x180013308  jz      loc_18001347B
0x18001330e  mov     rcx, rax; this
0x180013311  call    ??0BSM_DATA_PACKAGE@@QEAA@XZ; BSM_DATA_PACKAGE::BSM_DATA_PACKAGE(void)
0x180013316  mov     [rbp+37h+ThreadId], 0
0x18001331d  mov     rbx, rax
0x180013320  test    rax, rax
0x180013323  jz      loc_180013482
0x180013329  cmp     dword ptr [rax+40h], 0
0x18001332d  jz      loc_18001346E
0x180013333  mov     rax, [rbp+37h+arg_0]
0x180013337  mov     ecx, [rbp+37h+arg_20]
0x18001333a  mov     [rbx], rax
0x18001333d  mov     eax, [rbp+37h+arg_8]
0x180013340  mov     [rbx+8], eax
0x180013343  mov     [rbx+10h], r12d
0x180013347  xor     r12d, r12d
0x18001334a  mov     [rbx+0Ch], r13d
0x18001334e  mov     [rbx+14h], ecx
0x180013351  mov     eax, [rbp+37h+var_4C]
0x180013354  mov     [rbx+1Ch], esi
0x180013357  mov     rsi, [rbp+37h+arg_48]
0x18001335e  mov     [rbx+18h], eax
0x180013361  mov     rax, [rbp+37h+arg_38]
0x180013365  mov     [rbx+20h], rax
0x180013369  mov     [rbx+28h], r15
0x18001336d  test    rsi, rsi
0x180013370  jz      short loc_180013376
0x180013372  mov     eax, [rsi]
0x180013374  jmp     short loc_180013379
0x180013376  mov     eax, r12d
0x180013379  mov     [rbx+30h], eax
0x18001337c  lea     r8, ?WinStationBSMWorkerThread@@YAKPEAX@Z; lpStartAddress
0x180013383  mov     rax, gs:60h
0x18001338c  mov     r9, rbx; lpParameter
0x18001338f  xor     edx, edx; dwStackSize
0x180013391  mov     ecx, [rax+2C0h]
0x180013397  mov     eax, [rbp+37h+var_48]
0x18001339a  mov     [rbx+50h], eax
0x18001339d  mov     eax, [rbp+37h+var_44]
0x1800133a0  mov     [rbx+54h], eax
0x1800133a3  lea     rax, [rbp+37h+ThreadId]
0x1800133a7  mov     [rbx+34h], ecx
0x1800133aa  xor     ecx, ecx; lpThreadAttributes
0x1800133ac  mov     [rsp+0C0h+lpThreadId], rax; lpThreadId
0x1800133b1  mov     [rsp+0C0h+dwCreationFlags], r12d; dwCreationFlags
0x1800133b6  mov     [rbx+38h], r12
0x1800133ba  mov     [rbx+48h], r14
0x1800133be  call    cs:__imp_CreateThread
0x1800133c5  nop     dword ptr [rax+rax+00h]
0x1800133ca  mov     r14, rax
0x1800133cd  test    rax, rax
0x1800133d0  jz      loc_18001345A
0x1800133d6  mov     rcx, rax; void *
0x1800133d9  call    ?MsgWaitForMultipleObjectsLoop@@YAXPEAXK@Z; MsgWaitForMultipleObjectsLoop(void *,ulong)
0x1800133de  lea     rcx, [rbx+58h]; lpCriticalSection
0x1800133e2  call    cs:__imp_EnterCriticalSection
0x1800133e9  nop     dword ptr [rax+rax+00h]
0x1800133ee  cmp     [rbx+38h], r12d
0x1800133f2  jz      short loc_18001341D
0x1800133f4  test    rdi, rdi
0x1800133f7  jz      short loc_1800133FE
0x1800133f9  mov     eax, [rbx+18h]
0x1800133fc  mov     [rdi], eax
0x1800133fe  test    rsi, rsi
0x180013401  jz      short loc_180013408
0x180013403  mov     eax, [rbx+30h]
0x180013406  mov     [rsi], eax
0x180013408  lea     rdx, [rbp+37h+ExitCode]; lpExitCode
0x18001340c  mov     rcx, r14; hThread
0x18001340f  call    cs:__imp_GetExitCodeThread
0x180013416  nop     dword ptr [rax+rax+00h]
0x18001341b  jmp     short loc_180013439
0x18001341d  lea     rdx, aWinstationbroa_0; "WinStationBroadcastSystemMessage(): fai"...
0x180013424  mov     dword ptr [rbx+3Ch], 1
0x18001342b  mov     ecx, 8; int
0x180013430  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180013435  mov     [rbp+37h+ExitCode], r12d
0x180013439  lea     rcx, [rbx+58h]; lpCriticalSection
0x18001343d  call    cs:__imp_LeaveCriticalSection
0x180013444  nop     dword ptr [rax+rax+00h]
0x180013449  mov     rcx, r14; hObject
0x18001344c  call    cs:__imp_CloseHandle
0x180013453  nop     dword ptr [rax+rax+00h]
0x180013458  jmp     short loc_18001345E
0x18001345a  mov     [rbp+37h+ExitCode], r12d
0x18001345e  cmp     [rbx+3Ch], r12d
0x180013462  jnz     short loc_180013496
0x180013464  mov     rcx, rbx; this
0x180013467  call    ??_GBSM_DATA_PACKAGE@@QEAAPEAXI@Z; BSM_DATA_PACKAGE::`scalar deleting destructor'(uint)
0x18001346c  jmp     short loc_180013496
0x18001346e  mov     rcx, rbx; this
0x180013471  call    ??_GBSM_DATA_PACKAGE@@QEAAPEAXI@Z; BSM_DATA_PACKAGE::`scalar deleting destructor'(uint)
0x180013476  jmp     loc_180013269
0x18001347b  mov     [rbp+37h+ThreadId], 0
0x180013482  test    r14, r14
0x180013485  jz      short loc_180013496
0x180013487  mov     rcx, r14; hMem
0x18001348a  call    cs:__imp_LocalFree
0x180013491  nop     dword ptr [rax+rax+00h]
0x180013496  mov     eax, [rbp+37h+ExitCode]
0x180013499  mov     rbx, [rsp+0C0h+arg_10]
0x1800134a1  add     rsp, 90h
0x1800134a8  pop     r15
0x1800134aa  pop     r14
0x1800134ac  pop     r13
0x1800134ae  pop     r12
0x1800134b0  pop     rdi
0x1800134b1  pop     rsi
0x1800134b2  pop     rbp
0x1800134b3  retn
```
