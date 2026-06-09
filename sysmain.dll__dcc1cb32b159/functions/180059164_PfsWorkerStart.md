# PfsWorkerStart

- ea: `0x180059164`
- end: `0x18005925e`
- name: `PfsWorkerStart`
- size: `250`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18003f9e4`
- `0x18004e494`
- `0x180064c68`
- `0x180096950`

## callees

- `0x180059164`
- `0x180059264`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800591a0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800591a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800591af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800591af`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180059222`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180059222`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005924d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005924d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800591ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800591f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800591ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800591f6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800591d7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800591d7`

## pseudocode

```c
__int64 __fastcall PfsWorkerStart(__int64 a1, ULONG (__stdcall *a2)(PVOID Parameter), void *a3, _QWORD *a4)
{
  HANDLE EventW; // rax
  DWORD LastError; // ebx
  HANDLE Thread; // rax
  void *v11; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v13; // rax
  HANDLE v14; // rax
  HANDLE TargetHandle; // [rsp+70h] [rbp+8h] BYREF

  TargetHandle = 0;
  PfsWorkerStop(a1, 0);
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)(a1 + 8) = EventW;
  if ( EventW && (Thread = CreateThread(0, 0, a2, a3, 0, 0), (*(_QWORD *)a1 = Thread) != 0) )
  {
    if ( a4 )
    {
      v11 = Thread;
      CurrentProcess = GetCurrentProcess();
      v13 = GetCurrentProcess();
      if ( DuplicateHandle(v13, v11, CurrentProcess, &TargetHandle, 0, 0, 2u) )
        v14 = TargetHandle;
      else
        v14 = 0;
      *a4 = v14;
      TargetHandle = 0;
    }
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
  }
  if ( TargetHandle )
    CloseHandle(TargetHandle);
  return LastError;
}

```

## disassembly

```asm
0x180059164  push    rbx
0x180059166  push    rbp
0x180059167  push    rsi
0x180059168  push    rdi
0x180059169  sub     rsp, 48h
0x18005916d  mov     rbp, rdx
0x180059170  mov     [rsp+68h+TargetHandle], 0
0x180059179  xor     edx, edx
0x18005917b  mov     rsi, r9
0x18005917e  mov     rbx, r8
0x180059181  mov     rdi, rcx
0x180059184  call    PfsWorkerStop
0x180059189  xor     eax, eax
0x18005918b  xorps   xmm0, xmm0
0x18005918e  movups  xmmword ptr [rdi], xmm0
0x180059191  xor     r9d, r9d; lpName
0x180059194  mov     [rdi+10h], rax
0x180059198  xor     r8d, r8d; bInitialState
0x18005919b  xor     ecx, ecx; lpEventAttributes
0x18005919d  lea     edx, [rax+1]; bManualReset
0x1800591a0  call    cs:__imp_CreateEventW
0x1800591a6  mov     [rdi+8], rax
0x1800591aa  test    rax, rax
0x1800591ad  jnz     short loc_1800591BC
0x1800591af  call    cs:__imp_GetLastError
0x1800591b5  mov     ebx, eax
0x1800591b7  jmp     loc_180059243
0x1800591bc  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x1800591c5  mov     r9, rbx; lpParameter
0x1800591c8  mov     r8, rbp; lpStartAddress
0x1800591cb  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x1800591d3  xor     edx, edx; dwStackSize
0x1800591d5  xor     ecx, ecx; lpThreadAttributes
0x1800591d7  call    cs:__imp_CreateThread
0x1800591dd  mov     [rdi], rax
0x1800591e0  test    rax, rax
0x1800591e3  jz      short loc_1800591AF
0x1800591e5  test    rsi, rsi
0x1800591e8  jz      short loc_180059241
0x1800591ea  mov     rdi, rax
0x1800591ed  call    cs:__imp_GetCurrentProcess
0x1800591f3  mov     rbx, rax
0x1800591f6  call    cs:__imp_GetCurrentProcess
0x1800591fc  mov     [rsp+68h+dwOptions], 2; dwOptions
0x180059204  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x180059209  mov     rcx, rax; hSourceProcessHandle
0x18005920c  mov     dword ptr [rsp+68h+lpThreadId], 0; bInheritHandle
0x180059214  mov     r8, rbx; hTargetProcessHandle
0x180059217  mov     [rsp+68h+dwCreationFlags], 0; dwDesiredAccess
0x18005921f  mov     rdx, rdi; hSourceHandle
0x180059222  call    cs:__imp_DuplicateHandle
0x180059228  test    eax, eax
0x18005922a  jnz     short loc_180059230
0x18005922c  xor     eax, eax
0x18005922e  jmp     short loc_180059235
0x180059230  mov     rax, [rsp+68h+TargetHandle]
0x180059235  mov     [rsi], rax
0x180059238  mov     [rsp+68h+TargetHandle], 0
0x180059241  xor     ebx, ebx
0x180059243  mov     rcx, [rsp+68h+TargetHandle]; hObject
0x180059248  test    rcx, rcx
0x18005924b  jz      short loc_180059253
0x18005924d  call    cs:__imp_CloseHandle
0x180059253  mov     eax, ebx
0x180059255  add     rsp, 48h
0x180059259  pop     rdi
0x18005925a  pop     rsi
0x18005925b  pop     rbp
0x18005925c  pop     rbx
0x18005925d  retn
```
