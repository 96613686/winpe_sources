# WinStationBroadcastSystemMessage

- ea: `0x180012360`
- end: `0x18001263c`
- name: `WinStationBroadcastSystemMessage`
- size: `732`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180007890`
- `0x180012360`
- `0x180012644`
- `0x180012780`
- `0x180012b14`
- `0x1800230b8`
- `0x180029574`
- `0x1800295f4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012618`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012618`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001256e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001256e`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800125af`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800125af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800125d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800125d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012588`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012588`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800125e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800125e0`

## string_xrefs

- `0x1800125b7`: `WinStationBroadcastSystemMessage(): failed to wait for thread to exit!`

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
0x180012360  mov     rax, rsp
0x180012363  mov     [rax+18h], rbx
0x180012367  mov     [rax+10h], edx
0x18001236a  mov     [rax+8], rcx
0x18001236e  push    rbp
0x18001236f  push    rsi
0x180012370  push    rdi
0x180012371  push    r12
0x180012373  push    r13
0x180012375  push    r14
0x180012377  push    r15
0x180012379  lea     rbp, [rax-3Fh]
0x18001237d  sub     rsp, 90h
0x180012384  mov     r15, [rbp+37h+arg_40]
0x18001238b  lea     rax, [rbp+37h+var_44]
0x18001238f  mov     esi, [rbp+37h+arg_30]
0x180012392  xor     r14d, r14d
0x180012395  mov     r12d, r9d
0x180012398  mov     [rbp+37h+ExitCode], 1
0x18001239f  mov     r13d, r8d
0x1800123a2  mov     [rbp+37h+var_4C], r14d
0x1800123a6  mov     ebx, edx
0x1800123a8  mov     qword ptr [rbp+37h+ThreadId], r14
0x1800123ac  mov     rdx, r15
0x1800123af  mov     [rbp+37h+var_48], r14d
0x1800123b3  lea     r9, [rbp+37h+var_48]
0x1800123b7  mov     [rbp+37h+var_44], r14d
0x1800123bb  lea     r8, [rbp+37h+ThreadId]
0x1800123bf  mov     qword ptr [rsp+0C0h+dwCreationFlags], rax
0x1800123c4  mov     ecx, esi
0x1800123c6  call    AllocateBSMRpcBuffer
0x1800123cb  test    al, al
0x1800123cd  jnz     short loc_1800123D6
0x1800123cf  xor     eax, eax
0x1800123d1  jmp     loc_180012621
0x1800123d6  mov     rdi, [rbp+37h+arg_28]
0x1800123da  test    rdi, rdi
0x1800123dd  jz      short loc_1800123E4
0x1800123df  mov     eax, [rdi]
0x1800123e1  mov     [rbp+37h+var_4C], eax
0x1800123e4  mov     r14, qword ptr [rbp+37h+ThreadId]
0x1800123e8  mov     eax, esi
0x1800123ea  sub     eax, 1Ah
0x1800123ed  jz      loc_1800124A4
0x1800123f3  sub     eax, 1
0x1800123f6  jz      loc_1800124A4
0x1800123fc  sub     eax, 1FDh
0x180012401  jz      short loc_180012425
0x180012403  cmp     eax, 1
0x180012406  jz      short loc_180012425
0x180012408  lea     rdx, aRequestIsRejec_0; "Request is rejected \n"
0x18001240f  mov     ecx, 8; int
0x180012414  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180012419  mov     [rbp+37h+ExitCode], 0
0x180012420  jmp     loc_180012610
0x180012425  mov     rcx, gs:60h
0x18001242e  mov     r9d, r12d; unsigned int
0x180012431  cmp     [rbp+37h+var_44], 0
0x180012435  mov     r8d, r13d; unsigned int
0x180012438  mov     edx, ebx; int
0x18001243a  setnz   al
0x18001243d  mov     [rsp+68h], al; unsigned __int8
0x180012441  mov     eax, [rbp+37h+var_48]
0x180012444  mov     [rsp+0C0h+var_60], eax; unsigned int
0x180012448  mov     eax, [rcx+2C0h]
0x18001244e  mov     rcx, [rbp+37h+arg_0]; this
0x180012452  mov     [rsp+0C0h+var_68], r14; unsigned __int8 *
0x180012457  mov     [rsp+0C0h+var_70], eax; unsigned int
0x18001245b  mov     rax, [rbp+37h+arg_48]
0x180012462  mov     [rsp+0C0h+var_78], rax; int *
0x180012467  mov     rax, [rbp+37h+arg_38]
0x18001246b  mov     [rsp+0C0h+var_80], r15; __int64
0x180012470  mov     [rsp+0C0h+var_88], rax; unsigned __int64
0x180012475  lea     rax, [rbp+37h+var_4C]
0x180012479  mov     [rsp+0C0h+var_90], esi; unsigned int
0x18001247d  mov     [rsp+0C0h+lpThreadId], rax; unsigned int *
0x180012482  mov     eax, [rbp+37h+arg_20]
0x180012485  mov     [rsp+0C0h+dwCreationFlags], eax; unsigned int
0x180012489  call    ?WinStationBroadcastSystemMessageWorker@@YAJPEAXHKKKPEAKK_K_JPEAJKPEAEKE@Z; WinStationBroadcastSystemMessageWorker(void *,int,ulong,ulong,ulong,ulong *,ulong,unsigned __int64,__int64,long *,ulong,uchar *,ulong,uchar)
0x18001248e  mov     [rbp+37h+ExitCode], eax
0x180012491  test    rdi, rdi
0x180012494  jz      loc_180012610
0x18001249a  mov     eax, [rbp+37h+var_4C]
0x18001249d  mov     [rdi], eax
0x18001249f  jmp     loc_180012610
0x1800124a4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800124ab  mov     ecx, 80h; unsigned __int64
0x1800124b0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800124b5  test    rax, rax
0x1800124b8  jz      loc_180012609
0x1800124be  mov     rcx, rax; this
0x1800124c1  call    ??0BSM_DATA_PACKAGE@@QEAA@XZ; BSM_DATA_PACKAGE::BSM_DATA_PACKAGE(void)
0x1800124c6  mov     [rbp+37h+ThreadId], 0
0x1800124cd  mov     rbx, rax
0x1800124d0  test    rax, rax
0x1800124d3  jz      loc_180012610
0x1800124d9  cmp     dword ptr [rax+40h], 0
0x1800124dd  jz      loc_1800125FC
0x1800124e3  mov     rax, [rbp+37h+arg_0]
0x1800124e7  mov     ecx, [rbp+37h+arg_20]
0x1800124ea  mov     [rbx], rax
0x1800124ed  mov     eax, [rbp+37h+arg_8]
0x1800124f0  mov     [rbx+8], eax
0x1800124f3  mov     [rbx+10h], r12d
0x1800124f7  xor     r12d, r12d
0x1800124fa  mov     [rbx+0Ch], r13d
0x1800124fe  mov     [rbx+14h], ecx
0x180012501  mov     eax, [rbp+37h+var_4C]
0x180012504  mov     [rbx+1Ch], esi
0x180012507  mov     rsi, [rbp+37h+arg_48]
0x18001250e  mov     [rbx+18h], eax
0x180012511  mov     rax, [rbp+37h+arg_38]
0x180012515  mov     [rbx+20h], rax
0x180012519  mov     [rbx+28h], r15
0x18001251d  test    rsi, rsi
0x180012520  jz      short loc_180012526
0x180012522  mov     eax, [rsi]
0x180012524  jmp     short loc_180012529
0x180012526  mov     eax, r12d
0x180012529  mov     [rbx+30h], eax
0x18001252c  lea     r8, ?WinStationBSMWorkerThread@@YAKPEAX@Z; lpStartAddress
0x180012533  mov     rax, gs:60h
0x18001253c  mov     r9, rbx; lpParameter
0x18001253f  xor     edx, edx; dwStackSize
0x180012541  mov     ecx, [rax+2C0h]
0x180012547  mov     eax, [rbp+37h+var_48]
0x18001254a  mov     [rbx+50h], eax
0x18001254d  mov     eax, [rbp+37h+var_44]
0x180012550  mov     [rbx+54h], eax
0x180012553  lea     rax, [rbp+37h+ThreadId]
0x180012557  mov     [rbx+34h], ecx
0x18001255a  xor     ecx, ecx; lpThreadAttributes
0x18001255c  mov     [rsp+0C0h+lpThreadId], rax; lpThreadId
0x180012561  mov     [rsp+0C0h+dwCreationFlags], r12d; dwCreationFlags
0x180012566  mov     [rbx+38h], r12
0x18001256a  mov     [rbx+48h], r14
0x18001256e  call    cs:__imp_CreateThread
0x180012574  mov     r14, rax
0x180012577  test    rax, rax
0x18001257a  jz      short loc_1800125E8
0x18001257c  mov     rcx, rax; void *
0x18001257f  call    ?MsgWaitForMultipleObjectsLoop@@YAXPEAXK@Z; MsgWaitForMultipleObjectsLoop(void *,ulong)
0x180012584  lea     rcx, [rbx+58h]; lpCriticalSection
0x180012588  call    cs:__imp_EnterCriticalSection
0x18001258e  cmp     [rbx+38h], r12d
0x180012592  jz      short loc_1800125B7
0x180012594  test    rdi, rdi
0x180012597  jz      short loc_18001259E
0x180012599  mov     eax, [rbx+18h]
0x18001259c  mov     [rdi], eax
0x18001259e  test    rsi, rsi
0x1800125a1  jz      short loc_1800125A8
0x1800125a3  mov     eax, [rbx+30h]
0x1800125a6  mov     [rsi], eax
0x1800125a8  lea     rdx, [rbp+37h+ExitCode]; lpExitCode
0x1800125ac  mov     rcx, r14; hThread
0x1800125af  call    cs:__imp_GetExitCodeThread
0x1800125b5  jmp     short loc_1800125D3
0x1800125b7  lea     rdx, aWinstationbroa_0; "WinStationBroadcastSystemMessage(): fai"...
0x1800125be  mov     dword ptr [rbx+3Ch], 1
0x1800125c5  mov     ecx, 8; int
0x1800125ca  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800125cf  mov     [rbp+37h+ExitCode], r12d
0x1800125d3  lea     rcx, [rbx+58h]; lpCriticalSection
0x1800125d7  call    cs:__imp_LeaveCriticalSection
0x1800125dd  mov     rcx, r14; hObject
0x1800125e0  call    cs:__imp_CloseHandle
0x1800125e6  jmp     short loc_1800125EC
0x1800125e8  mov     [rbp+37h+ExitCode], r12d
0x1800125ec  cmp     [rbx+3Ch], r12d
0x1800125f0  jnz     short loc_18001261E
0x1800125f2  mov     rcx, rbx; this
0x1800125f5  call    ??_GBSM_DATA_PACKAGE@@QEAAPEAXI@Z; BSM_DATA_PACKAGE::`scalar deleting destructor'(uint)
0x1800125fa  jmp     short loc_18001261E
0x1800125fc  mov     rcx, rbx; this
0x1800125ff  call    ??_GBSM_DATA_PACKAGE@@QEAAPEAXI@Z; BSM_DATA_PACKAGE::`scalar deleting destructor'(uint)
0x180012604  jmp     loc_180012419
0x180012609  mov     [rbp+37h+ThreadId], 0
0x180012610  test    r14, r14
0x180012613  jz      short loc_18001261E
0x180012615  mov     rcx, r14; hMem
0x180012618  call    cs:__imp_LocalFree
0x18001261e  mov     eax, [rbp+37h+ExitCode]
0x180012621  mov     rbx, [rsp+0C0h+arg_10]
0x180012629  add     rsp, 90h
0x180012630  pop     r15
0x180012632  pop     r14
0x180012634  pop     r13
0x180012636  pop     r12
0x180012638  pop     rdi
0x180012639  pop     rsi
0x18001263a  pop     rbp
0x18001263b  retn
```
