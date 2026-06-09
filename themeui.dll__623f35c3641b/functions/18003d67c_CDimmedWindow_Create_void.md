# CDimmedWindow::Create(void)

- ea: `0x18003d67c`
- end: `0x18003d76e`
- name: `?Create@CDimmedWindow@@QEAAJXZ`
- size: `242`
- prototype: `__int64 __fastcall(CDimmedWindow *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001e6d0`
- `0x18004fb2c`

## callees

- `0x180030f64`
- `0x18003d67c`
- `0x18003dbb8`

## import_xrefs

- `SHCORE!SHCreateThread` at `0x18003d720`
- `SHCORE!SHCreateThread` at `0x18003d720`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003d6a2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003d6a2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003d736`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003d736`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003d6c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003d6d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003d6c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003d6d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d74b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d74b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003d702`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003d702`

## pseudocode

```c
__int64 __fastcall CDimmedWindow::Create(CDimmedWindow *this)
{
  HANDLE EventW; // rax
  HANDLE CurrentProcess; // rax
  void *v4; // rdi
  void *v5; // rbx
  HANDLE v6; // rax
  BOOL v7; // ebx
  HANDLE TargetHandle; // [rsp+50h] [rbp+8h] BYREF

  EventW = (HANDLE)*((_QWORD *)this + 4);
  if ( !EventW )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 4) = EventW;
  }
  if ( *((_QWORD *)this + 3) )
    return ResultFromKnownLastError();
  if ( !EventW )
    return ResultFromKnownLastError();
  TargetHandle = 0;
  CurrentProcess = GetCurrentProcess();
  v4 = (void *)*((_QWORD *)this + 4);
  v5 = CurrentProcess;
  v6 = GetCurrentProcess();
  if ( !DuplicateHandle(v6, v4, v5, &TargetHandle, 0, 0, 2u) )
    return ResultFromKnownLastError();
  _InterlockedIncrement((volatile signed __int32 *)this);
  v7 = SHCreateThread((LPTHREAD_START_ROUTINE)CDimmedWindow::WorkerThread, this, 1u, 0);
  if ( v7 )
    WaitForSingleObject(TargetHandle, 0x2710u);
  else
    CDimmedWindow::Release(this);
  CloseHandle(TargetHandle);
  if ( v7 )
    return 0;
  else
    return ResultFromKnownLastError();
}

```

## disassembly

```asm
0x18003d67c  mov     [rsp+arg_8], rbx
0x18003d681  mov     [rsp+arg_10], rsi
0x18003d686  push    rdi
0x18003d687  sub     rsp, 40h
0x18003d68b  mov     rax, [rcx+20h]
0x18003d68f  mov     rsi, rcx
0x18003d692  test    rax, rax
0x18003d695  jnz     short loc_18003D6AC
0x18003d697  xor     r9d, r9d; lpName
0x18003d69a  lea     edx, [rax+1]; bManualReset
0x18003d69d  xor     r8d, r8d; bInitialState
0x18003d6a0  xor     ecx, ecx; lpEventAttributes
0x18003d6a2  call    cs:__imp_CreateEventW
0x18003d6a8  mov     [rsi+20h], rax
0x18003d6ac  cmp     qword ptr [rsi+18h], 0
0x18003d6b1  jnz     loc_18003D759
0x18003d6b7  test    rax, rax
0x18003d6ba  jz      loc_18003D759
0x18003d6c0  mov     [rsp+48h+TargetHandle], 0
0x18003d6c9  call    cs:__imp_GetCurrentProcess
0x18003d6cf  mov     rdi, [rsi+20h]
0x18003d6d3  mov     rbx, rax
0x18003d6d6  call    cs:__imp_GetCurrentProcess
0x18003d6dc  mov     [rsp+48h+dwOptions], 2; dwOptions
0x18003d6e4  lea     r9, [rsp+48h+TargetHandle]; lpTargetHandle
0x18003d6e9  mov     rcx, rax; hSourceProcessHandle
0x18003d6ec  mov     [rsp+48h+bInheritHandle], 0; bInheritHandle
0x18003d6f4  mov     r8, rbx; hTargetProcessHandle
0x18003d6f7  mov     [rsp+48h+dwDesiredAccess], 0; dwDesiredAccess
0x18003d6ff  mov     rdx, rdi; hSourceHandle
0x18003d702  call    cs:__imp_DuplicateHandle
0x18003d708  test    eax, eax
0x18003d70a  jz      short loc_18003D759
0x18003d70c  lock inc dword ptr [rsi]
0x18003d70f  xor     r9d, r9d; pfnCallback
0x18003d712  lea     rcx, ?WorkerThread@CDimmedWindow@@CAKPEAX@Z; pfnThreadProc
0x18003d719  mov     rdx, rsi; pData
0x18003d71c  lea     r8d, [r9+1]; flags
0x18003d720  call    cs:__imp_SHCreateThread
0x18003d726  mov     ebx, eax
0x18003d728  test    eax, eax
0x18003d72a  jz      short loc_18003D73E
0x18003d72c  mov     rcx, [rsp+48h+TargetHandle]; hHandle
0x18003d731  mov     edx, 2710h; dwMilliseconds
0x18003d736  call    cs:__imp_WaitForSingleObject
0x18003d73c  jmp     short loc_18003D746
0x18003d73e  mov     rcx, rsi; this
0x18003d741  call    ?Release@CDimmedWindow@@QEAAKXZ; CDimmedWindow::Release(void)
0x18003d746  mov     rcx, [rsp+48h+TargetHandle]; hObject
0x18003d74b  call    cs:__imp_CloseHandle
0x18003d751  test    ebx, ebx
0x18003d753  jz      short loc_18003D759
0x18003d755  xor     eax, eax
0x18003d757  jmp     short loc_18003D75E
0x18003d759  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003d75e  mov     rbx, [rsp+48h+arg_8]
0x18003d763  mov     rsi, [rsp+48h+arg_10]
0x18003d768  add     rsp, 40h
0x18003d76c  pop     rdi
0x18003d76d  retn
```
