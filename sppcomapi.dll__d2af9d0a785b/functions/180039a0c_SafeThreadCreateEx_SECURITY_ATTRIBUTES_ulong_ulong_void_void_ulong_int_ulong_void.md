# SafeThreadCreateEx(_SECURITY_ATTRIBUTES *,ulong,ulong (*)(void *),void *,ulong,int,ulong *,void * *)

- ea: `0x180039a0c`
- end: `0x180039bef`
- name: `?SafeThreadCreateEx@@YAJPEAU_SECURITY_ATTRIBUTES@@KP6AKPEAX@Z1KHPEAKPEAPEAX@Z`
- size: `483`
- prototype: `int(struct _SECURITY_ATTRIBUTES *, unsigned int, unsigned int (*)(void *), void *, unsigned int, int, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180037288`

## callees

- `0x180003520`
- `0x180004288`
- `0x180036f4c`
- `0x180038d30`
- `0x180039a0c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039a31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039b45`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039a31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039b45`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039b59`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039b59`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039a46`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039a46`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180039b35`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180039b35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039bd8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039bd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039b65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039b65`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180039b05`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180039b05`

## pseudocode

```c
__int64 __fastcall SafeThreadCreateEx(
        struct _SECURITY_ATTRIBUTES *a1,
        __int64 a2,
        unsigned int (*a3)(void *),
        void *a4,
        unsigned int a5,
        int a6,
        unsigned int *a7,
        void **a8)
{
  CSafeThreadsInfo *v8; // rsi
  HANDLE ProcessHeap; // rax
  char *v11; // rax
  unsigned int (*v12)(void *); // rdx
  char v13; // cl
  CSafeThreadsInfo *v14; // rbx
  unsigned int v15; // edi
  __int64 v16; // rcx
  int v17; // eax
  void *v18; // rbx
  HANDLE v19; // rdx
  HMODULE v20; // rcx
  HANDLE v21; // rax
  signed int LastError; // eax
  CSafeThreadsInfo *v24; // [rsp+50h] [rbp+8h] BYREF
  DWORD ThreadId; // [rsp+58h] [rbp+10h] BYREF
  unsigned int (*v26)(void *); // [rsp+60h] [rbp+18h] BYREF

  v26 = a3;
  v8 = 0;
  ThreadId = 0;
  v24 = 0;
  ProcessHeap = GetProcessHeap();
  v11 = (char *)HeapAlloc(ProcessHeap, 0, 0x28u);
  if ( v11 )
  {
    *(_QWORD *)(v11 + 4) = 0;
    v13 = 0;
    *(_QWORD *)(v11 + 12) = 0;
    *((_DWORD *)v11 + 5) = 0;
    *((_QWORD *)v11 + 4) = 0;
    *(_DWORD *)v11 = 1;
    *((_QWORD *)v11 + 3) = 0;
  }
  else
  {
    v13 = 1;
    v11 = 0;
  }
  v14 = 0;
  if ( !v13 )
    v14 = (CSafeThreadsInfo *)v11;
  v26 = (unsigned int (*)(void *))v14;
  if ( !v14 )
  {
    v15 = -2147024882;
    v16 = 2147942414LL;
LABEL_8:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v16);
    goto LABEL_12;
  }
  v17 = CSafeThreadsInfo::Initialize(v14, v12, a4, a6);
  v15 = v17;
  if ( v17 < 0 )
  {
    v16 = (unsigned int)v17;
    goto LABEL_8;
  }
  v26 = 0;
  v8 = v14;
  v24 = v14;
LABEL_12:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v15);
  SP<CSafeThreadsInfo,SP_COM<CSafeThreadsInfo>>::~SP<CSafeThreadsInfo,SP_COM<CSafeThreadsInfo>>(&v26);
  if ( (v15 & 0x80000000) != 0 )
  {
    v18 = 0;
LABEL_14:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v15);
    goto LABEL_30;
  }
  _InterlockedIncrement((volatile signed __int32 *)v8);
  v19 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CSafeThreadsInfo::ThreadProc, v8, 0, &ThreadId);
  if ( !v19 )
  {
    v18 = 0;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8, 0xFFFFFFFF) == 1 && v8 )
    {
      v20 = (HMODULE)*((_QWORD *)v8 + 3);
      if ( v20 )
      {
        FreeLibrary(v20);
        *((_QWORD *)v8 + 3) = 0;
      }
      v21 = GetProcessHeap();
      HeapFree(v21, 0, v8);
    }
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v15 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v15 = -2147467259;
    }
    goto LABEL_14;
  }
  if ( a7 )
    *a7 = ThreadId;
  if ( a8 )
  {
    v18 = 0;
    *a8 = v19;
  }
  else
  {
    v18 = v19;
  }
LABEL_30:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v15);
  SP<CSafeThreadsInfo,SP_COM<CSafeThreadsInfo>>::~SP<CSafeThreadsInfo,SP_COM<CSafeThreadsInfo>>(&v24);
  if ( v18 )
    CloseHandle(v18);
  return v15;
}

```

## disassembly

```asm
0x180039a0c  mov     rax, rsp
0x180039a0f  mov     [rax+18h], r8
0x180039a13  mov     [rax+10h], edx
0x180039a16  mov     [rax+8], rcx
0x180039a1a  push    rbx
0x180039a1b  push    rsi
0x180039a1c  push    rdi
0x180039a1d  sub     rsp, 30h
0x180039a21  xor     esi, esi
0x180039a23  mov     dword ptr [rax+10h], 0
0x180039a2a  mov     [rax+8], rsi
0x180039a2e  mov     rdi, r9
0x180039a31  call    cs:__imp_GetProcessHeap
0x180039a38  nop     dword ptr [rax+rax+00h]
0x180039a3d  xor     edx, edx; dwFlags
0x180039a3f  lea     r8d, [rsi+28h]; dwBytes
0x180039a43  mov     rcx, rax; hHeap
0x180039a46  call    cs:__imp_HeapAlloc
0x180039a4d  nop     dword ptr [rax+rax+00h]
0x180039a52  test    rax, rax
0x180039a55  jz      short loc_180039A74
0x180039a57  mov     [rax+4], rsi
0x180039a5b  xor     cl, cl
0x180039a5d  mov     [rax+0Ch], rsi
0x180039a61  mov     [rax+14h], esi
0x180039a64  mov     [rax+20h], rsi
0x180039a68  mov     dword ptr [rax], 1
0x180039a6e  mov     [rax+18h], rsi
0x180039a72  jmp     short loc_180039A78
0x180039a74  mov     cl, 1
0x180039a76  xor     eax, eax
0x180039a78  xor     ebx, ebx
0x180039a7a  test    cl, cl
0x180039a7c  cmovz   rbx, rax
0x180039a80  mov     [rsp+48h+arg_10], rbx
0x180039a85  test    rbx, rbx
0x180039a88  jnz     short loc_180039A98
0x180039a8a  mov     edi, 8007000Eh
0x180039a8f  mov     ecx, edi
0x180039a91  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180039a96  jmp     short loc_180039ABF
0x180039a98  mov     r9d, [rsp+48h+arg_28]; int
0x180039a9d  mov     r8, rdi; void *
0x180039aa0  mov     rcx, rbx; this
0x180039aa3  call    ?Initialize@CSafeThreadsInfo@@AEAAJP6AKPEAX@Z0H@Z; CSafeThreadsInfo::Initialize(ulong (*)(void *),void *,int)
0x180039aa8  mov     edi, eax
0x180039aaa  test    eax, eax
0x180039aac  jns     short loc_180039AB2
0x180039aae  mov     ecx, eax
0x180039ab0  jmp     short loc_180039A91
0x180039ab2  mov     [rsp+48h+arg_10], rsi
0x180039ab7  mov     rsi, rbx
0x180039aba  mov     [rsp+48h+arg_0], rbx
0x180039abf  mov     ecx, edi
0x180039ac1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180039ac6  lea     rcx, [rsp+48h+arg_10]
0x180039acb  call    ??1?$SP@VCSafeThreadsInfo@@V?$SP_COM@VCSafeThreadsInfo@@@@@@QEAA@XZ; SP<CSafeThreadsInfo,SP_COM<CSafeThreadsInfo>>::~SP<CSafeThreadsInfo,SP_COM<CSafeThreadsInfo>>(void)
0x180039ad0  test    edi, edi
0x180039ad2  jns     short loc_180039AE2
0x180039ad4  xor     ebx, ebx
0x180039ad6  mov     ecx, edi
0x180039ad8  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180039add  jmp     loc_180039BBF
0x180039ae2  lock inc dword ptr [rsi]
0x180039ae5  lea     rax, [rsp+48h+ThreadId]
0x180039aea  mov     r9, rsi; lpParameter
0x180039aed  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x180039af2  lea     r8, ?ThreadProc@CSafeThreadsInfo@@SAKPEAX@Z; lpStartAddress
0x180039af9  xor     edx, edx; dwStackSize
0x180039afb  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x180039b03  xor     ecx, ecx; lpThreadAttributes
0x180039b05  call    cs:__imp_CreateThread
0x180039b0c  nop     dword ptr [rax+rax+00h]
0x180039b11  mov     rdx, rax
0x180039b14  test    rax, rax
0x180039b17  jnz     short loc_180039B95
0x180039b19  xor     ebx, ebx
0x180039b1b  or      eax, 0FFFFFFFFh
0x180039b1e  lock xadd [rsi], eax
0x180039b22  cmp     eax, 1
0x180039b25  jnz     short loc_180039B65
0x180039b27  test    rsi, rsi
0x180039b2a  jz      short loc_180039B65
0x180039b2c  mov     rcx, [rsi+18h]; hLibModule
0x180039b30  test    rcx, rcx
0x180039b33  jz      short loc_180039B45
0x180039b35  call    cs:__imp_FreeLibrary
0x180039b3c  nop     dword ptr [rax+rax+00h]
0x180039b41  mov     [rsi+18h], rbx
0x180039b45  call    cs:__imp_GetProcessHeap
0x180039b4c  nop     dword ptr [rax+rax+00h]
0x180039b51  mov     r8, rsi; lpMem
0x180039b54  xor     edx, edx; dwFlags
0x180039b56  mov     rcx, rax; hHeap
0x180039b59  call    cs:__imp_HeapFree
0x180039b60  nop     dword ptr [rax+rax+00h]
0x180039b65  call    cs:__imp_GetLastError
0x180039b6c  nop     dword ptr [rax+rax+00h]
0x180039b71  mov     edi, eax
0x180039b73  test    eax, eax
0x180039b75  jnz     short loc_180039B81
0x180039b77  mov     edi, 80004005h
0x180039b7c  jmp     loc_180039AD6
0x180039b81  jle     loc_180039AD6
0x180039b87  movzx   edi, ax
0x180039b8a  or      edi, 80070000h
0x180039b90  jmp     loc_180039AD6
0x180039b95  mov     rcx, [rsp+48h+arg_30]
0x180039b9d  test    rcx, rcx
0x180039ba0  jz      short loc_180039BA8
0x180039ba2  mov     eax, [rsp+48h+ThreadId]
0x180039ba6  mov     [rcx], eax
0x180039ba8  mov     rax, [rsp+48h+arg_38]
0x180039bb0  test    rax, rax
0x180039bb3  jz      short loc_180039BBC
0x180039bb5  xor     ebx, ebx
0x180039bb7  mov     [rax], rdx
0x180039bba  jmp     short loc_180039BBF
0x180039bbc  mov     rbx, rdx
0x180039bbf  mov     ecx, edi
0x180039bc1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180039bc6  lea     rcx, [rsp+48h+arg_0]
0x180039bcb  call    ??1?$SP@VCSafeThreadsInfo@@V?$SP_COM@VCSafeThreadsInfo@@@@@@QEAA@XZ; SP<CSafeThreadsInfo,SP_COM<CSafeThreadsInfo>>::~SP<CSafeThreadsInfo,SP_COM<CSafeThreadsInfo>>(void)
0x180039bd0  test    rbx, rbx
0x180039bd3  jz      short loc_180039BE4
0x180039bd5  mov     rcx, rbx; hObject
0x180039bd8  call    cs:__imp_CloseHandle
0x180039bdf  nop     dword ptr [rax+rax+00h]
0x180039be4  mov     eax, edi
0x180039be6  add     rsp, 30h
0x180039bea  pop     rdi
0x180039beb  pop     rsi
0x180039bec  pop     rbx
0x180039bed  retn
```
