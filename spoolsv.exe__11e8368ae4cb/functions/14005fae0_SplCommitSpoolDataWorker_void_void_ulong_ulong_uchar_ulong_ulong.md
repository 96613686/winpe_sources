# SplCommitSpoolDataWorker(void *,void *,ulong,ulong,uchar *,ulong,ulong *)

- ea: `0x14005fae0`
- end: `0x14005febf`
- name: `?SplCommitSpoolDataWorker@@YAHPEAX0KKPEAEKPEAK@Z`
- size: `991`
- prototype: `__int64 __fastcall(void *, void *, unsigned int, unsigned int, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14001dc90`

## callees

- `0x1400041c0`
- `0x140013fe8`
- `0x1400140cc`
- `0x14005fae0`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005fddb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005fe02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005fddb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005fe02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005fc14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005fd97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005fe60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005fc14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005fd97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005fe60`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005fb58`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005fb86`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005fba7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005fc5d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005fe89`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005fb58`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005fb86`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005fba7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005fc5d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005fe89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14005fe08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14005fe08`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14005fe3c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14005fe3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005fe5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005fe5a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14005fca8`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14005fca8`

## string_xrefs

- `0x14005fb00`: `Enter, cbCommit: %u, dwLevel: %u, cbBuf: %u`
- `0x14005fb1c`: `SplCommitSpoolDataWorker`
- `0x14005fb68`: `SplCommitSpoolDataWorker`
- `0x14005fbb4`: `SplCommitSpoolDataWorker`
- `0x14005fbed`: `SplCommitSpoolDataWorker`
- `0x14005fc27`: `SplCommitSpoolDataWorker`
- `0x14005fc79`: `SplCommitSpoolDataWorker`
- `0x14005fcc7`: `SplCommitSpoolDataWorker`
- `0x14005fd5d`: `SplCommitSpoolDataWorker`
- `0x14005fd80`: `SplCommitSpoolDataWorker`
- `0x14005fda7`: `SplCommitSpoolDataWorker`
- `0x14005fdea`: `SplCommitSpoolDataWorker`
- `0x14005fe73`: `SplCommitSpoolDataWorker`
- `0x14005fe99`: `SplCommitSpoolDataWorker`
- `0x14005fbe6`: `Calling pLocalProvidor->PrintProvidor.fpCommitSpoolData(cbCommit: %u)..`
- `0x14005fcb9`: `[L1] - cbCommit: %u, cbToRead: %u, cbRead: %u`
- `0x14005fdc3`: `[L1] - ReadFile returned ZERO bytes, premature loop end`
- `0x14005fda0`: `[L2] - pPrintHandle->pProvidor->PrintProvidor.fpWritePrinter failed, LE: %d`
- `0x14005fd00`: `[L1] - new cbCommit: %u = %u - %u`
- `0x14005fdb5`: `[L1] - cbCommit about to overflow! (%u - %u)`
- `0x14005fde3`: `Main 'while' loop normally completed`
- `0x14005fd52`: `[L2] - cbWritten: %u, cbTotalWritten: %u (of cbRead: %u)`
- `0x14005fd79`: `[L1] - completed 'for' loop, cbTotalWritten: %u`

## pseudocode

```c
__int64 __fastcall SplCommitSpoolDataWorker(
        void *a1,
        void *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int a6,
        unsigned int *a7)
{
  unsigned int v7; // r14d
  unsigned int v11; // r13d
  unsigned __int16 *v12; // rdx
  unsigned __int8 *v13; // rdi
  struct _PROVIDOR *v14; // rax
  unsigned int v15; // ebx
  DWORD v16; // eax
  DWORD v18; // r14d
  char *v19; // r12
  DWORD i; // r14d
  DWORD v21; // eax
  HANDLE CurrentProcess; // rax
  void *v23; // r15
  DWORD LastError; // eax
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-30h]
  LPOVERLAPPED lpOverlappeda; // [rsp+20h] [rbp-30h]
  LPOVERLAPPED lpOverlappedb; // [rsp+20h] [rbp-30h]
  unsigned int v28; // [rsp+40h] [rbp-10h] BYREF
  HANDLE TargetHandle; // [rsp+48h] [rbp-8h] BYREF
  DWORD NumberOfBytesRead; // [rsp+90h] [rbp+40h] BYREF
  HANDLE hTargetProcessHandle; // [rsp+98h] [rbp+48h]

  hTargetProcessHandle = a2;
  v7 = a6;
  v28 = 0;
  NumberOfBytesRead = 0;
  TargetHandle = (HANDLE)-1LL;
  PrvSpoolssTelemetry::WriteDbgTraceInfo("SplCommitSpoolDataWorker", L"Enter, cbCommit: %u, dwLevel: %u, cbBuf: %u");
  if ( a1 && *(_DWORD *)a1 == 24672 )
  {
    v11 = 0;
    if ( a4 != 1 )
    {
      SetLastError(0x7Cu);
      v12 = L"LE: ERROR_INVALID_LEVEL, invalid level: %u";
LABEL_5:
      PrvSpoolssTelemetry::WriteDbgTraceError("SplCommitSpoolDataWorker", v12, a4);
      goto LABEL_36;
    }
    a4 = 24;
    if ( v7 < 0x18 )
    {
      SetLastError(0x7Au);
      v12 = L"LE: ERROR_INSUFFICIENT_BUFFER, *pcbNeeded: %u";
      *a7 = 24;
      goto LABEL_5;
    }
    v13 = a5;
    if ( !a5 )
    {
      SetLastError(0x57u);
      PrvSpoolssTelemetry::WriteDbgTraceError(
        "SplCommitSpoolDataWorker",
        L"LE: ERROR_INVALID_PARAMETER, NULL pSpoolFileInfo");
LABEL_36:
      LastError = GetLastError();
      PrvSpoolssTelemetry::WriteDbgTraceInfo("SplCommitSpoolDataWorker", L"Return %u, LE: %d", v11, LastError);
      return v11;
    }
    v14 = pLocalProvidor;
    *(_DWORD *)a5 = 1;
    *((_DWORD *)v13 + 4) = 1;
    *((_QWORD *)v13 + 1) = -1;
    if ( *((struct _PROVIDOR **)a1 + 1) == v14 )
    {
      PrvSpoolssTelemetry::WriteDbgTraceInfo(
        "SplCommitSpoolDataWorker",
        L"Calling pLocalProvidor->PrintProvidor.fpCommitSpoolData(cbCommit: %u)..",
        a3);
      v15 = (*((__int64 (__fastcall **)(_QWORD, _QWORD))pLocalProvidor + 85))(*((_QWORD *)a1 + 2), a3);
      v16 = GetLastError();
      PrvSpoolssTelemetry::WriteDbgTraceInfo("SplCommitSpoolDataWorker", L"Return %u, LE: %d", v15, v16);
      return v15;
    }
    if ( *((_QWORD *)a1 + 7) != -1 )
    {
      v18 = 0x40000;
      v19 = (char *)DllAllocSplMem(0x40000u);
      if ( !v19 )
      {
        SetLastError(8u);
        PrvSpoolssTelemetry::WriteDbgTraceError(
          "SplCommitSpoolDataWorker",
          L"LE: ERROR_NOT_ENOUGH_MEMORY, failed to allocate %u bytes",
          0x40000);
        goto LABEL_36;
      }
      PrvSpoolssTelemetry::WriteDbgTraceInfo("SplCommitSpoolDataWorker", L"Begin main 'while' loop..");
LABEL_17:
      if ( a3 < 0x40000 )
      {
        if ( !a3 )
        {
LABEL_32:
          PrvSpoolssTelemetry::WriteDbgTraceInfo("SplCommitSpoolDataWorker", L"Main 'while' loop normally completed");
          HeapFree(g_hSpoolssHeap, 0, v19);
          CurrentProcess = GetCurrentProcess();
          v23 = CurrentProcess;
          if ( CurrentProcess )
          {
            if ( DuplicateHandle(CurrentProcess, *((HANDLE *)a1 + 7), hTargetProcessHandle, &TargetHandle, 0, 1, 2u) )
            {
              v11 = 1;
              *((_QWORD *)v13 + 1) = TargetHandle;
              *(_DWORD *)v13 = 1;
              *((_DWORD *)v13 + 4) = 2;
            }
            CloseHandle(v23);
          }
          goto LABEL_36;
        }
        v18 = a3;
      }
      if ( ReadFile(*((HANDLE *)a1 + 7), v19, v18, &NumberOfBytesRead, 0) )
      {
        LODWORD(lpOverlapped) = NumberOfBytesRead;
        PrvSpoolssTelemetry::WriteDbgTraceInfo(
          "SplCommitSpoolDataWorker",
          L"[L1] - cbCommit: %u, cbToRead: %u, cbRead: %u",
          a3,
          v18,
          lpOverlapped);
        if ( NumberOfBytesRead )
        {
          if ( a3 < NumberOfBytesRead )
          {
            PrvSpoolssTelemetry::WriteDbgTraceError(
              "SplCommitSpoolDataWorker",
              L"[L1] - cbCommit about to overflow! (%u - %u)",
              a3);
          }
          else
          {
            LODWORD(lpOverlappeda) = NumberOfBytesRead;
            PrvSpoolssTelemetry::WriteDbgTraceInfo(
              "SplCommitSpoolDataWorker",
              L"[L1] - new cbCommit: %u = %u - %u",
              a3 - NumberOfBytesRead,
              a3,
              lpOverlappeda);
            a3 -= NumberOfBytesRead;
            PrvSpoolssTelemetry::WriteDbgTraceInfo("SplCommitSpoolDataWorker", L"[L1] - begin secondary 'for' loop..");
            for ( i = 0; ; i += v28 )
            {
              if ( i >= NumberOfBytesRead )
              {
                PrvSpoolssTelemetry::WriteDbgTraceInfo(
                  "SplCommitSpoolDataWorker",
                  L"[L1] - completed 'for' loop, cbTotalWritten: %u",
                  i);
                v18 = 0x40000;
                goto LABEL_17;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD, char *, _QWORD, unsigned int *))(*((_QWORD *)a1 + 1) + 200LL))(
                      *((_QWORD *)a1 + 2),
                      &v19[i],
                      NumberOfBytesRead - i,
                      &v28) )
                break;
              LODWORD(lpOverlappedb) = NumberOfBytesRead;
              PrvSpoolssTelemetry::WriteDbgTraceInfo(
                "SplCommitSpoolDataWorker",
                L"[L2] - cbWritten: %u, cbTotalWritten: %u (of cbRead: %u)",
                v28,
                i,
                lpOverlappedb);
            }
            v21 = GetLastError();
            PrvSpoolssTelemetry::WriteDbgTraceError(
              "SplCommitSpoolDataWorker",
              L"[L2] - pPrintHandle->pProvidor->PrintProvidor.fpWritePrinter failed, LE: %d",
              v21);
          }
        }
        else
        {
          PrvSpoolssTelemetry::WriteDbgTraceError(
            "SplCommitSpoolDataWorker",
            L"[L1] - ReadFile returned ZERO bytes, premature loop end");
        }
        HeapFree(g_hSpoolssHeap, 0, v19);
        goto LABEL_36;
      }
      goto LABEL_32;
    }
  }
  SetLastError(6u);
  PrvSpoolssTelemetry::WriteDbgTraceError("SplCommitSpoolDataWorker", L"Return %u, LE: ERROR_INVALID_HANDLE", 0);
  return 0;
}

```

## disassembly

```asm
0x14005fae0  mov     [rsp-38h+arg_10], rbx
0x14005fae5  mov     [rsp-38h+hTargetProcessHandle], rdx
0x14005faea  push    rbp
0x14005faeb  push    rsi
0x14005faec  push    rdi
0x14005faed  push    r12
0x14005faef  push    r13
0x14005faf1  push    r14
0x14005faf3  push    r15
0x14005faf5  mov     rbp, rsp
0x14005faf8  sub     rsp, 50h
0x14005fafc  mov     r14d, [rbp+arg_28]
0x14005fb00  lea     rdx, aEnterCbcommitU; "Enter, cbCommit: %u, dwLevel: %u, cbBuf"...
0x14005fb07  mov     rsi, rcx
0x14005fb0a  mov     [rbp+var_10], 0
0x14005fb11  or      r15, 0FFFFFFFFFFFFFFFFh
0x14005fb15  mov     [rbp+NumberOfBytesRead], 0
0x14005fb1c  lea     rcx, aSplcommitspool_0; "SplCommitSpoolDataWorker"
0x14005fb23  mov     [rbp+TargetHandle], r15
0x14005fb27  mov     edi, r9d
0x14005fb2a  mov     dword ptr [rsp+50h+lpOverlapped], r14d
0x14005fb2f  mov     ebx, r8d
0x14005fb32  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14005fb37  test    rsi, rsi
0x14005fb3a  jz      loc_14005FE84
0x14005fb40  cmp     dword ptr [rsi], 6060h
0x14005fb46  jnz     loc_14005FE84
0x14005fb4c  xor     r13d, r13d
0x14005fb4f  cmp     edi, 1
0x14005fb52  jz      short loc_14005FB79
0x14005fb54  lea     ecx, [r15+7Dh]; dwErrCode
0x14005fb58  call    cs:__imp_SetLastError
0x14005fb5e  lea     rdx, aLeErrorInvalid_0; "LE: ERROR_INVALID_LEVEL, invalid level:"...
0x14005fb65  mov     r8d, edi
0x14005fb68  lea     rcx, aSplcommitspool_0; "SplCommitSpoolDataWorker"
0x14005fb6f  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14005fb74  jmp     loc_14005FE60
0x14005fb79  mov     edi, 18h
0x14005fb7e  cmp     r14d, edi
0x14005fb81  jnb     short loc_14005FB9B
0x14005fb83  lea     ecx, [rdi+62h]; dwErrCode
0x14005fb86  call    cs:__imp_SetLastError
0x14005fb8c  mov     rax, [rbp+arg_30]
0x14005fb90  lea     rdx, aLeErrorInsuffi; "LE: ERROR_INSUFFICIENT_BUFFER, *pcbNeed"...
0x14005fb97  mov     [rax], edi
0x14005fb99  jmp     short loc_14005FB65
0x14005fb9b  mov     rdi, [rbp+arg_20]
0x14005fb9f  test    rdi, rdi
0x14005fba2  jnz     short loc_14005FBC5
0x14005fba4  lea     ecx, [rdi+57h]; dwErrCode
0x14005fba7  call    cs:__imp_SetLastError
0x14005fbad  lea     rdx, aLeErrorInvalid; "LE: ERROR_INVALID_PARAMETER, NULL pSpoo"...
0x14005fbb4  lea     rcx, aSplcommitspool_0; "SplCommitSpoolDataWorker"
0x14005fbbb  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14005fbc0  jmp     loc_14005FE60
0x14005fbc5  mov     rax, cs:?pLocalProvidor@@3PEAU_PROVIDOR@@EA; _PROVIDOR * pLocalProvidor
0x14005fbcc  mov     r14d, 1
0x14005fbd2  mov     [rdi], r14d
0x14005fbd5  mov     [rdi+10h], r14d
0x14005fbd9  mov     [rdi+8], r15
0x14005fbdd  cmp     [rsi+8], rax
0x14005fbe1  jnz     short loc_14005FC3A
0x14005fbe3  mov     r8d, ebx
0x14005fbe6  lea     rdx, aCallingPlocalp; "Calling pLocalProvidor->PrintProvidor.f"...
0x14005fbed  lea     rcx, aSplcommitspool_0; "SplCommitSpoolDataWorker"
0x14005fbf4  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14005fbf9  mov     rax, cs:?pLocalProvidor@@3PEAU_PROVIDOR@@EA; _PROVIDOR * pLocalProvidor
0x14005fc00  mov     edx, ebx
0x14005fc02  mov     rcx, [rsi+10h]
0x14005fc06  mov     rax, [rax+2A8h]
0x14005fc0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005fc12  mov     ebx, eax
0x14005fc14  call    cs:__imp_GetLastError
0x14005fc1a  mov     r8d, ebx
0x14005fc1d  lea     rdx, aReturnULeD; "Return %u, LE: %d"
0x14005fc24  mov     r9d, eax
0x14005fc27  lea     rcx, aSplcommitspool_0; "SplCommitSpoolDataWorker"
0x14005fc2e  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14005fc33  mov     eax, ebx
0x14005fc35  jmp     loc_14005FEA7
0x14005fc3a  cmp     [rsi+38h], r15
0x14005fc3e  jz      loc_14005FE84
0x14005fc44  mov     r14d, 40000h
0x14005fc4a  mov     ecx, r14d; dwBytes
0x14005fc4d  call    DllAllocSplMem
0x14005fc52  mov     r12, rax
0x14005fc55  test    rax, rax
0x14005fc58  jnz     short loc_14005FC72
0x14005fc5a  lea     ecx, [rax+8]; dwErrCode
0x14005fc5d  call    cs:__imp_SetLastError
0x14005fc63  mov     r8d, r14d
0x14005fc66  lea     rdx, aLeErrorNotEnou; "LE: ERROR_NOT_ENOUGH_MEMORY, failed to "...
0x14005fc6d  jmp     loc_14005FB68
0x14005fc72  lea     rdx, aBeginMainWhile; "Begin main 'while' loop.."
0x14005fc79  lea     rcx, aSplcommitspool_0; "SplCommitSpoolDataWorker"
0x14005fc80  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14005fc85  cmp     ebx, r14d
0x14005fc88  jnb     short loc_14005FC95
0x14005fc8a  test    ebx, ebx
0x14005fc8c  jz      loc_14005FDE3
0x14005fc92  mov     r14d, ebx
0x14005fc95  mov     rcx, [rsi+38h]; hFile
0x14005fc99  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x14005fc9d  mov     r8d, r14d; nNumberOfBytesToRead
0x14005fca0  mov     [rsp+50h+lpOverlapped], r13; lpOverlapped
0x14005fca5  mov     rdx, r12; lpBuffer
0x14005fca8  call    cs:__imp_ReadFile
0x14005fcae  test    eax, eax
0x14005fcb0  jz      loc_14005FDE3
0x14005fcb6  mov     eax, [rbp+NumberOfBytesRead]
0x14005fcb9  lea     rdx, aL1CbcommitUCbt; "[L1] - cbCommit: %u, cbToRead: %u, cbRe"...
0x14005fcc0  mov     r9d, r14d
0x14005fcc3  mov     dword ptr [rsp+50h+lpOverlapped], eax
0x14005fcc7  lea     r14, aSplcommitspool_0; "SplCommitSpoolDataWorker"
0x14005fcce  mov     r8d, ebx
0x14005fcd1  mov     rcx, r14; char *
0x14005fcd4  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14005fcd9  mov     r9d, [rbp+NumberOfBytesRead]
0x14005fcdd  mov     rcx, r14; char *
0x14005fce0  test    r9d, r9d
0x14005fce3  jz      loc_14005FDC3
0x14005fce9  mov     r8d, ebx
0x14005fcec  cmp     ebx, r9d
0x14005fcef  jb      loc_14005FDB5
0x14005fcf5  sub     r8d, r9d
0x14005fcf8  mov     dword ptr [rsp+50h+lpOverlapped], r9d
0x14005fcfd  mov     r9d, ebx
0x14005fd00  lea     rdx, aL1NewCbcommitU; "[L1] - new cbCommit: %u = %u - %u"
0x14005fd07  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14005fd0c  sub     ebx, [rbp+NumberOfBytesRead]
0x14005fd0f  lea     rdx, aL1BeginSeconda; "[L1] - begin secondary 'for' loop.."
0x14005fd16  mov     rcx, r14; char *
0x14005fd19  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14005fd1e  xor     r14d, r14d
0x14005fd21  mov     r8d, [rbp+NumberOfBytesRead]
0x14005fd25  cmp     r14d, r8d
0x14005fd28  jnb     short loc_14005FD76
0x14005fd2a  mov     rax, [rsi+8]
0x14005fd2e  lea     r9, [rbp+var_10]
0x14005fd32  mov     rcx, [rsi+10h]
0x14005fd36  sub     r8d, r14d
0x14005fd39  mov     edx, r14d
0x14005fd3c  add     rdx, r12
0x14005fd3f  mov     rax, [rax+0C8h]
0x14005fd46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005fd4b  test    eax, eax
0x14005fd4d  jz      short loc_14005FD97
0x14005fd4f  mov     eax, [rbp+NumberOfBytesRead]
0x14005fd52  lea     rdx, aL2CbwrittenUCb; "[L2] - cbWritten: %u, cbTotalWritten: %"...
0x14005fd59  mov     r8d, [rbp+var_10]
0x14005fd5d  lea     rcx, aSplcommitspool_0; "SplCommitSpoolDataWorker"
0x14005fd64  mov     r9d, r14d
0x14005fd67  mov     dword ptr [rsp+50h+lpOverlapped], eax
0x14005fd6b  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14005fd70  add     r14d, [rbp+var_10]
0x14005fd74  jmp     short loc_14005FD21
0x14005fd76  mov     r8d, r14d
0x14005fd79  lea     rdx, aL1CompletedFor; "[L1] - completed 'for' loop, cbTotalWri"...
0x14005fd80  lea     rcx, aSplcommitspool_0; "SplCommitSpoolDataWorker"
0x14005fd87  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14005fd8c  mov     r14d, 40000h
0x14005fd92  jmp     loc_14005FC85
0x14005fd97  call    cs:__imp_GetLastError
0x14005fd9d  mov     r8d, eax
0x14005fda0  lea     rdx, aL2Pprinthandle; "[L2] - pPrintHandle->pProvidor->PrintPr"...
0x14005fda7  lea     rcx, aSplcommitspool_0; "SplCommitSpoolDataWorker"
0x14005fdae  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14005fdb3  jmp     short loc_14005FDCF
0x14005fdb5  lea     rdx, aL1CbcommitAbou; "[L1] - cbCommit about to overflow! (%u "...
0x14005fdbc  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14005fdc1  jmp     short loc_14005FDCF
0x14005fdc3  lea     rdx, aL1ReadfileRetu; "[L1] - ReadFile returned ZERO bytes, pr"...
0x14005fdca  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14005fdcf  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14005fdd6  mov     r8, r12; lpMem
0x14005fdd9  xor     edx, edx; dwFlags
0x14005fddb  call    cs:__imp_HeapFree
0x14005fde1  jmp     short loc_14005FE60
0x14005fde3  lea     rdx, aMainWhileLoopN; "Main 'while' loop normally completed"
0x14005fdea  lea     rcx, aSplcommitspool_0; "SplCommitSpoolDataWorker"
0x14005fdf1  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14005fdf6  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14005fdfd  mov     r8, r12; lpMem
0x14005fe00  xor     edx, edx; dwFlags
0x14005fe02  call    cs:__imp_HeapFree
0x14005fe08  call    cs:__imp_GetCurrentProcess
0x14005fe0e  mov     r15, rax
0x14005fe11  test    rax, rax
0x14005fe14  jz      short loc_14005FE60
0x14005fe16  mov     r8, [rbp+hTargetProcessHandle]; hTargetProcessHandle
0x14005fe1a  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x14005fe1e  mov     rdx, [rsi+38h]; hSourceHandle
0x14005fe22  mov     ebx, 2
0x14005fe27  mov     [rsp+50h+dwOptions], ebx; dwOptions
0x14005fe2b  mov     rcx, rax; hSourceProcessHandle
0x14005fe2e  lea     r14d, [rbx-1]
0x14005fe32  mov     [rsp+50h+bInheritHandle], r14d; bInheritHandle
0x14005fe37  mov     dword ptr [rsp+50h+lpOverlapped], r13d; dwDesiredAccess
0x14005fe3c  call    cs:__imp_DuplicateHandle
0x14005fe42  test    eax, eax
0x14005fe44  jz      short loc_14005FE57
0x14005fe46  mov     rax, [rbp+TargetHandle]
0x14005fe4a  mov     r13d, r14d
0x14005fe4d  mov     [rdi+8], rax
0x14005fe51  mov     [rdi], r14d
0x14005fe54  mov     [rdi+10h], ebx
0x14005fe57  mov     rcx, r15; hObject
0x14005fe5a  call    cs:__imp_CloseHandle
0x14005fe60  call    cs:__imp_GetLastError
0x14005fe66  mov     r8d, r13d
0x14005fe69  lea     rdx, aReturnULeD; "Return %u, LE: %d"
0x14005fe70  mov     r9d, eax
0x14005fe73  lea     rcx, aSplcommitspool_0; "SplCommitSpoolDataWorker"
0x14005fe7a  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14005fe7f  mov     eax, r13d
0x14005fe82  jmp     short loc_14005FEA7
0x14005fe84  mov     ecx, 6; dwErrCode
0x14005fe89  call    cs:__imp_SetLastError
0x14005fe8f  xor     r8d, r8d
0x14005fe92  lea     rdx, aReturnULeError; "Return %u, LE: ERROR_INVALID_HANDLE"
0x14005fe99  lea     rcx, aSplcommitspool_0; "SplCommitSpoolDataWorker"
0x14005fea0  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14005fea5  xor     eax, eax
0x14005fea7  mov     rbx, [rsp+50h+arg_10]
0x14005feaf  add     rsp, 50h
0x14005feb3  pop     r15
0x14005feb5  pop     r14
0x14005feb7  pop     r13
0x14005feb9  pop     r12
0x14005febb  pop     rdi
0x14005febc  pop     rsi
0x14005febd  pop     rbp
0x14005febe  retn
```
