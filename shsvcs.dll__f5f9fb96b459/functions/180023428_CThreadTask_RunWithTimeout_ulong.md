# CThreadTask::RunWithTimeout(ulong)

- ea: `0x180023428`
- end: `0x18002355a`
- name: `?RunWithTimeout@CThreadTask@@QEAAJK@Z`
- size: `306`
- prototype: `__int64 __fastcall(CThreadTask *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18002a650`

## callees

- `0x180003570`
- `0x180023428`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002345d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002345d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800234e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002351f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800234e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002351f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180023441`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180023441`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800234c0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800234c0`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002348a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002348a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800234fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023517`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023538`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800234fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023517`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023538`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800234ac`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800234ac`

## pseudocode

```c
__int64 __fastcall CThreadTask::RunWithTimeout(CThreadTask *this)
{
  HANDLE EventW; // rax
  HANDLE CurrentProcess; // rax
  DWORD v4; // eax
  unsigned int v5; // ebx
  signed int LastError; // eax
  signed int v7; // eax
  HANDLE TargetHandle; // [rsp+50h] [rbp+8h] BYREF

  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 3) = EventW;
  if ( EventW )
  {
    TargetHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( DuplicateHandle(CurrentProcess, *((HANDLE *)this + 3), CurrentProcess, &TargetHandle, 0, 0, 2u) )
    {
      _InterlockedIncrement((volatile signed __int32 *)this + 2);
      if ( QueueUserWorkItem(CThreadTask::_ThreadProcWithTimeout, this, 0x10u) )
      {
        v4 = WaitForSingleObject(TargetHandle, 0xBB8u);
        if ( v4 )
        {
          v5 = -2147418113;
          if ( v4 == 258 )
            v5 = -2147221001;
        }
        else
        {
          v5 = *((_DWORD *)this + 4);
        }
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        CloseHandle(*((HANDLE *)this + 3));
        *((_QWORD *)this + 3) = 0;
        CRefCounted::Release(this);
      }
      CloseHandle(TargetHandle);
    }
    else
    {
      v7 = GetLastError();
      v5 = v7;
      if ( v7 > 0 )
        v5 = (unsigned __int16)v7 | 0x80070000;
      CloseHandle(*((HANDLE *)this + 3));
      *((_QWORD *)this + 3) = 0;
    }
  }
  else
  {
    return (unsigned int)-2147221002;
  }
  return v5;
}

```

## disassembly

```asm
0x180023428  mov     [rsp+arg_8], rbx
0x18002342d  push    rdi
0x18002342e  sub     rsp, 40h
0x180023432  xor     r9d, r9d; lpName
0x180023435  mov     rdi, rcx
0x180023438  xor     r8d, r8d; bInitialState
0x18002343b  xor     ecx, ecx; lpEventAttributes
0x18002343d  lea     edx, [r9+1]; bManualReset
0x180023441  call    cs:__imp_CreateEventW
0x180023447  mov     [rdi+18h], rax
0x18002344b  test    rax, rax
0x18002344e  jz      loc_180023548
0x180023454  mov     [rsp+48h+TargetHandle], 0
0x18002345d  call    cs:__imp_GetCurrentProcess
0x180023463  mov     rdx, [rdi+18h]; hSourceHandle
0x180023467  lea     r9, [rsp+48h+TargetHandle]; lpTargetHandle
0x18002346c  mov     [rsp+48h+dwOptions], 2; dwOptions
0x180023474  mov     r8, rax; hTargetProcessHandle
0x180023477  mov     rcx, rax; hSourceProcessHandle
0x18002347a  mov     [rsp+48h+bInheritHandle], 0; bInheritHandle
0x180023482  mov     [rsp+48h+dwDesiredAccess], 0; dwDesiredAccess
0x18002348a  call    cs:__imp_DuplicateHandle
0x180023490  test    eax, eax
0x180023492  jz      loc_18002351F
0x180023498  lock inc dword ptr [rdi+8]
0x18002349c  mov     r8d, 10h; Flags
0x1800234a2  lea     rcx, ?_ThreadProcWithTimeout@CThreadTask@@CAKPEAX@Z; Function
0x1800234a9  mov     rdx, rdi; Context
0x1800234ac  call    cs:__imp_QueueUserWorkItem
0x1800234b2  test    eax, eax
0x1800234b4  jz      short loc_1800234E3
0x1800234b6  mov     rcx, [rsp+48h+TargetHandle]; hHandle
0x1800234bb  mov     edx, 0BB8h; dwMilliseconds
0x1800234c0  call    cs:__imp_WaitForSingleObject
0x1800234c6  test    eax, eax
0x1800234c8  jnz     short loc_1800234CF
0x1800234ca  mov     ebx, [rdi+10h]
0x1800234cd  jmp     short loc_180023512
0x1800234cf  cmp     eax, 102h
0x1800234d4  mov     ebx, 8000FFFFh
0x1800234d9  mov     ecx, 800401F7h
0x1800234de  cmovz   ebx, ecx
0x1800234e1  jmp     short loc_180023512
0x1800234e3  call    cs:__imp_GetLastError
0x1800234e9  mov     ebx, eax
0x1800234eb  test    eax, eax
0x1800234ed  jle     short loc_1800234F8
0x1800234ef  movzx   ebx, ax
0x1800234f2  or      ebx, 80070000h
0x1800234f8  mov     rcx, [rdi+18h]; hObject
0x1800234fc  call    cs:__imp_CloseHandle
0x180023502  mov     rcx, rdi; this
0x180023505  mov     qword ptr [rdi+18h], 0
0x18002350d  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180023512  mov     rcx, [rsp+48h+TargetHandle]; hObject
0x180023517  call    cs:__imp_CloseHandle
0x18002351d  jmp     short loc_18002354D
0x18002351f  call    cs:__imp_GetLastError
0x180023525  mov     ebx, eax
0x180023527  test    eax, eax
0x180023529  jle     short loc_180023534
0x18002352b  movzx   ebx, ax
0x18002352e  or      ebx, 80070000h
0x180023534  mov     rcx, [rdi+18h]; hObject
0x180023538  call    cs:__imp_CloseHandle
0x18002353e  mov     qword ptr [rdi+18h], 0
0x180023546  jmp     short loc_18002354D
0x180023548  mov     ebx, 800401F6h
0x18002354d  mov     eax, ebx
0x18002354f  mov     rbx, [rsp+48h+arg_8]
0x180023554  add     rsp, 40h
0x180023558  pop     rdi
0x180023559  retn
```
