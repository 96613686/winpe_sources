# SplCommitSpoolDataWorker(void *,void *,ulong,ulong,uchar *,ulong,ulong *)

- ea: `0x1400658f8`
- end: `0x140065d2f`
- name: `?SplCommitSpoolDataWorker@@YAHPEAX0KKPEAEKPEAK@Z`
- size: `1079`
- prototype: `__int64 __fastcall(void *, void *, unsigned int, unsigned int, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14001f6c0`

## callees

- `0x140004790`
- `0x140015290`
- `0x140015378`
- `0x1400658f8`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140065c1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140065c4d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140065c1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140065c4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065a3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065bd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065cc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065a3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065bd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065cc3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140065970`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400659a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400659cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140065a8d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140065cf2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140065970`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400659a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400659cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140065a8d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140065cf2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140065c59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140065c59`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140065c93`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140065c93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140065cb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140065cb7`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140065ade`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140065ade`

## string_xrefs

- `0x140065918`: `Enter, cbCommit: %u, dwLevel: %u, cbBuf: %u`
- `0x140065934`: `SplCommitSpoolDataWorker`
- `0x140065986`: `SplCommitSpoolDataWorker`
- `0x1400659de`: `SplCommitSpoolDataWorker`
- `0x140065a17`: `SplCommitSpoolDataWorker`
- `0x140065a57`: `SplCommitSpoolDataWorker`
- `0x140065aaf`: `SplCommitSpoolDataWorker`
- `0x140065b03`: `SplCommitSpoolDataWorker`
- `0x140065b99`: `SplCommitSpoolDataWorker`
- `0x140065bbc`: `SplCommitSpoolDataWorker`
- `0x140065be9`: `SplCommitSpoolDataWorker`
- `0x140065c35`: `SplCommitSpoolDataWorker`
- `0x140065cdc`: `SplCommitSpoolDataWorker`
- `0x140065d08`: `SplCommitSpoolDataWorker`
- `0x140065a10`: `Calling pLocalProvidor->PrintProvidor.fpCommitSpoolData(cbCommit: %u)..`
- `0x140065c05`: `[L1] - ReadFile returned ZERO bytes, premature loop end`
- `0x140065b3c`: `[L1] - new cbCommit: %u = %u - %u`
- `0x140065af5`: `[L1] - cbCommit: %u, cbToRead: %u, cbRead: %u`
- `0x140065be2`: `[L2] - pPrintHandle->pProvidor->PrintProvidor.fpWritePrinter failed, LE: %d`
- `0x140065b8e`: `[L2] - cbWritten: %u, cbTotalWritten: %u (of cbRead: %u)`
- `0x140065bf7`: `[L1] - cbCommit about to overflow! (%u - %u)`
- `0x140065bb5`: `[L1] - completed 'for' loop, cbTotalWritten: %u`
- `0x140065c2e`: `Main 'while' loop normally completed`

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
0x1400658f8  mov     [rsp-38h+arg_10], rbx
0x1400658fd  mov     [rsp-38h+hTargetProcessHandle], rdx
0x140065902  push    rbp
0x140065903  push    rsi
0x140065904  push    rdi
0x140065905  push    r12
0x140065907  push    r13
0x140065909  push    r14
0x14006590b  push    r15
0x14006590d  mov     rbp, rsp
0x140065910  sub     rsp, 50h
0x140065914  mov     r14d, [rbp+arg_28]
0x140065918  lea     rdx, aEnterCbcommitU; "Enter, cbCommit: %u, dwLevel: %u, cbBuf"...
0x14006591f  mov     rsi, rcx
0x140065922  mov     [rbp+var_10], 0
0x140065929  or      r15, 0FFFFFFFFFFFFFFFFh
0x14006592d  mov     [rbp+NumberOfBytesRead], 0
0x140065934  lea     rcx, aSplcommitspool_0; "SplCommitSpoolDataWorker"
0x14006593b  mov     [rbp+TargetHandle], r15
0x14006593f  mov     edi, r9d
0x140065942  mov     dword ptr [rsp+50h+lpOverlapped], r14d
0x140065947  mov     ebx, r8d
0x14006594a  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006594f  test    rsi, rsi
0x140065952  jz      loc_140065CED
0x140065958  cmp     dword ptr [rsi], 6060h
0x14006595e  jnz     loc_140065CED
0x140065964  xor     r13d, r13d
0x140065967  cmp     edi, 1
0x14006596a  jz      short loc_140065997
0x14006596c  lea     ecx, [r15+7Dh]; dwErrCode
0x140065970  call    cs:__imp_SetLastError
0x140065977  nop     dword ptr [rax+rax+00h]
0x14006597c  lea     rdx, aLeErrorInvalid_0; "LE: ERROR_INVALID_LEVEL, invalid level:"...
0x140065983  mov     r8d, edi
0x140065986  lea     rcx, aSplcommitspool_0; "SplCommitSpoolDataWorker"
0x14006598d  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140065992  jmp     loc_140065CC3
0x140065997  mov     edi, 18h
0x14006599c  cmp     r14d, edi
0x14006599f  jnb     short loc_1400659BF
0x1400659a1  lea     ecx, [rdi+62h]; dwErrCode
0x1400659a4  call    cs:__imp_SetLastError
0x1400659ab  nop     dword ptr [rax+rax+00h]
0x1400659b0  mov     rax, [rbp+arg_30]
0x1400659b4  lea     rdx, aLeErrorInsuffi; "LE: ERROR_INSUFFICIENT_BUFFER, *pcbNeed"...
0x1400659bb  mov     [rax], edi
0x1400659bd  jmp     short loc_140065983
0x1400659bf  mov     rdi, [rbp+arg_20]
0x1400659c3  test    rdi, rdi
0x1400659c6  jnz     short loc_1400659EF
0x1400659c8  lea     ecx, [rdi+57h]; dwErrCode
0x1400659cb  call    cs:__imp_SetLastError
0x1400659d2  nop     dword ptr [rax+rax+00h]
0x1400659d7  lea     rdx, aLeErrorInvalid; "LE: ERROR_INVALID_PARAMETER, NULL pSpoo"...
0x1400659de  lea     rcx, aSplcommitspool_0; "SplCommitSpoolDataWorker"
0x1400659e5  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400659ea  jmp     loc_140065CC3
0x1400659ef  mov     rax, cs:?pLocalProvidor@@3PEAU_PROVIDOR@@EA; _PROVIDOR * pLocalProvidor
0x1400659f6  mov     r14d, 1
0x1400659fc  mov     [rdi], r14d
0x1400659ff  mov     [rdi+10h], r14d
0x140065a03  mov     [rdi+8], r15
0x140065a07  cmp     [rsi+8], rax
0x140065a0b  jnz     short loc_140065A6A
0x140065a0d  mov     r8d, ebx
0x140065a10  lea     rdx, aCallingPlocalp; "Calling pLocalProvidor->PrintProvidor.f"...
0x140065a17  lea     rcx, aSplcommitspool_0; "SplCommitSpoolDataWorker"
0x140065a1e  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140065a23  mov     rax, cs:?pLocalProvidor@@3PEAU_PROVIDOR@@EA; _PROVIDOR * pLocalProvidor
0x140065a2a  mov     edx, ebx
0x140065a2c  mov     rcx, [rsi+10h]
0x140065a30  mov     rax, [rax+2A8h]
0x140065a37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140065a3c  mov     ebx, eax
0x140065a3e  call    cs:__imp_GetLastError
0x140065a45  nop     dword ptr [rax+rax+00h]
0x140065a4a  mov     r8d, ebx
0x140065a4d  lea     rdx, aReturnULeD; "Return %u, LE: %d"
0x140065a54  mov     r9d, eax
0x140065a57  lea     rcx, aSplcommitspool_0; "SplCommitSpoolDataWorker"
0x140065a5e  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140065a63  mov     eax, ebx
0x140065a65  jmp     loc_140065D16
0x140065a6a  cmp     [rsi+38h], r15
0x140065a6e  jz      loc_140065CED
0x140065a74  mov     r14d, 40000h
0x140065a7a  mov     ecx, r14d; dwBytes
0x140065a7d  call    DllAllocSplMem
0x140065a82  mov     r12, rax
0x140065a85  test    rax, rax
0x140065a88  jnz     short loc_140065AA8
0x140065a8a  lea     ecx, [rax+8]; dwErrCode
0x140065a8d  call    cs:__imp_SetLastError
0x140065a94  nop     dword ptr [rax+rax+00h]
0x140065a99  mov     r8d, r14d
0x140065a9c  lea     rdx, aLeErrorNotEnou; "LE: ERROR_NOT_ENOUGH_MEMORY, failed to "...
0x140065aa3  jmp     loc_140065986
0x140065aa8  lea     rdx, aBeginMainWhile; "Begin main 'while' loop.."
0x140065aaf  lea     rcx, aSplcommitspool_0; "SplCommitSpoolDataWorker"
0x140065ab6  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140065abb  cmp     ebx, r14d
0x140065abe  jnb     short loc_140065ACB
0x140065ac0  test    ebx, ebx
0x140065ac2  jz      loc_140065C2E
0x140065ac8  mov     r14d, ebx
0x140065acb  mov     rcx, [rsi+38h]; hFile
0x140065acf  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x140065ad3  mov     r8d, r14d; nNumberOfBytesToRead
0x140065ad6  mov     [rsp+50h+lpOverlapped], r13; lpOverlapped
0x140065adb  mov     rdx, r12; lpBuffer
0x140065ade  call    cs:__imp_ReadFile
0x140065ae5  nop     dword ptr [rax+rax+00h]
0x140065aea  test    eax, eax
0x140065aec  jz      loc_140065C2E
0x140065af2  mov     eax, [rbp+NumberOfBytesRead]
0x140065af5  lea     rdx, aL1CbcommitUCbt; "[L1] - cbCommit: %u, cbToRead: %u, cbRe"...
0x140065afc  mov     r9d, r14d
0x140065aff  mov     dword ptr [rsp+50h+lpOverlapped], eax
0x140065b03  lea     r14, aSplcommitspool_0; "SplCommitSpoolDataWorker"
0x140065b0a  mov     r8d, ebx
0x140065b0d  mov     rcx, r14; char *
0x140065b10  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140065b15  mov     r9d, [rbp+NumberOfBytesRead]
0x140065b19  mov     rcx, r14; char *
0x140065b1c  test    r9d, r9d
0x140065b1f  jz      loc_140065C05
0x140065b25  mov     r8d, ebx
0x140065b28  cmp     ebx, r9d
0x140065b2b  jb      loc_140065BF7
0x140065b31  sub     r8d, r9d
0x140065b34  mov     dword ptr [rsp+50h+lpOverlapped], r9d
0x140065b39  mov     r9d, ebx
0x140065b3c  lea     rdx, aL1NewCbcommitU; "[L1] - new cbCommit: %u = %u - %u"
0x140065b43  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140065b48  sub     ebx, [rbp+NumberOfBytesRead]
0x140065b4b  lea     rdx, aL1BeginSeconda; "[L1] - begin secondary 'for' loop.."
0x140065b52  mov     rcx, r14; char *
0x140065b55  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140065b5a  xor     r14d, r14d
0x140065b5d  mov     r8d, [rbp+NumberOfBytesRead]
0x140065b61  cmp     r14d, r8d
0x140065b64  jnb     short loc_140065BB2
0x140065b66  mov     rax, [rsi+8]
0x140065b6a  lea     r9, [rbp+var_10]
0x140065b6e  mov     rcx, [rsi+10h]
0x140065b72  sub     r8d, r14d
0x140065b75  mov     edx, r14d
0x140065b78  add     rdx, r12
0x140065b7b  mov     rax, [rax+0C8h]
0x140065b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140065b87  test    eax, eax
0x140065b89  jz      short loc_140065BD3
0x140065b8b  mov     eax, [rbp+NumberOfBytesRead]
0x140065b8e  lea     rdx, aL2CbwrittenUCb; "[L2] - cbWritten: %u, cbTotalWritten: %"...
0x140065b95  mov     r8d, [rbp+var_10]
0x140065b99  lea     rcx, aSplcommitspool_0; "SplCommitSpoolDataWorker"
0x140065ba0  mov     r9d, r14d
0x140065ba3  mov     dword ptr [rsp+50h+lpOverlapped], eax
0x140065ba7  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140065bac  add     r14d, [rbp+var_10]
0x140065bb0  jmp     short loc_140065B5D
0x140065bb2  mov     r8d, r14d
0x140065bb5  lea     rdx, aL1CompletedFor; "[L1] - completed 'for' loop, cbTotalWri"...
0x140065bbc  lea     rcx, aSplcommitspool_0; "SplCommitSpoolDataWorker"
0x140065bc3  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140065bc8  mov     r14d, 40000h
0x140065bce  jmp     loc_140065ABB
0x140065bd3  call    cs:__imp_GetLastError
0x140065bda  nop     dword ptr [rax+rax+00h]
0x140065bdf  mov     r8d, eax
0x140065be2  lea     rdx, aL2Pprinthandle; "[L2] - pPrintHandle->pProvidor->PrintPr"...
0x140065be9  lea     rcx, aSplcommitspool_0; "SplCommitSpoolDataWorker"
0x140065bf0  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140065bf5  jmp     short loc_140065C11
0x140065bf7  lea     rdx, aL1CbcommitAbou; "[L1] - cbCommit about to overflow! (%u "...
0x140065bfe  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140065c03  jmp     short loc_140065C11
0x140065c05  lea     rdx, aL1ReadfileRetu; "[L1] - ReadFile returned ZERO bytes, pr"...
0x140065c0c  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140065c11  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140065c18  mov     r8, r12; lpMem
0x140065c1b  xor     edx, edx; dwFlags
0x140065c1d  call    cs:__imp_HeapFree
0x140065c24  nop     dword ptr [rax+rax+00h]
0x140065c29  jmp     loc_140065CC3
0x140065c2e  lea     rdx, aMainWhileLoopN; "Main 'while' loop normally completed"
0x140065c35  lea     rcx, aSplcommitspool_0; "SplCommitSpoolDataWorker"
0x140065c3c  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140065c41  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140065c48  mov     r8, r12; lpMem
0x140065c4b  xor     edx, edx; dwFlags
0x140065c4d  call    cs:__imp_HeapFree
0x140065c54  nop     dword ptr [rax+rax+00h]
0x140065c59  call    cs:__imp_GetCurrentProcess
0x140065c60  nop     dword ptr [rax+rax+00h]
0x140065c65  mov     r15, rax
0x140065c68  test    rax, rax
0x140065c6b  jz      short loc_140065CC3
0x140065c6d  mov     r8, [rbp+hTargetProcessHandle]; hTargetProcessHandle
0x140065c71  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x140065c75  mov     rdx, [rsi+38h]; hSourceHandle
0x140065c79  mov     ebx, 2
0x140065c7e  mov     [rsp+50h+dwOptions], ebx; dwOptions
0x140065c82  mov     rcx, rax; hSourceProcessHandle
0x140065c85  lea     r14d, [rbx-1]
0x140065c89  mov     [rsp+50h+bInheritHandle], r14d; bInheritHandle
0x140065c8e  mov     dword ptr [rsp+50h+lpOverlapped], r13d; dwDesiredAccess
0x140065c93  call    cs:__imp_DuplicateHandle
0x140065c9a  nop     dword ptr [rax+rax+00h]
0x140065c9f  test    eax, eax
0x140065ca1  jz      short loc_140065CB4
0x140065ca3  mov     rax, [rbp+TargetHandle]
0x140065ca7  mov     r13d, r14d
0x140065caa  mov     [rdi+8], rax
0x140065cae  mov     [rdi], r14d
0x140065cb1  mov     [rdi+10h], ebx
0x140065cb4  mov     rcx, r15; hObject
0x140065cb7  call    cs:__imp_CloseHandle
0x140065cbe  nop     dword ptr [rax+rax+00h]
0x140065cc3  call    cs:__imp_GetLastError
0x140065cca  nop     dword ptr [rax+rax+00h]
0x140065ccf  mov     r8d, r13d
0x140065cd2  lea     rdx, aReturnULeD; "Return %u, LE: %d"
0x140065cd9  mov     r9d, eax
0x140065cdc  lea     rcx, aSplcommitspool_0; "SplCommitSpoolDataWorker"
0x140065ce3  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140065ce8  mov     eax, r13d
0x140065ceb  jmp     short loc_140065D16
0x140065ced  mov     ecx, 6; dwErrCode
0x140065cf2  call    cs:__imp_SetLastError
0x140065cf9  nop     dword ptr [rax+rax+00h]
0x140065cfe  xor     r8d, r8d
0x140065d01  lea     rdx, aReturnULeError; "Return %u, LE: ERROR_INVALID_HANDLE"
0x140065d08  lea     rcx, aSplcommitspool_0; "SplCommitSpoolDataWorker"
0x140065d0f  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140065d14  xor     eax, eax
0x140065d16  mov     rbx, [rsp+50h+arg_10]
0x140065d1e  add     rsp, 50h
0x140065d22  pop     r15
0x140065d24  pop     r14
0x140065d26  pop     r13
0x140065d28  pop     r12
0x140065d2a  pop     rdi
0x140065d2b  pop     rsi
0x140065d2c  pop     rbp
0x140065d2d  retn
```
