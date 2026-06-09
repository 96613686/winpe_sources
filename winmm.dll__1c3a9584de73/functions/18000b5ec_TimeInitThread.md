# TimeInitThread

- ea: `0x18000b5ec`
- end: `0x18000b6cd`
- name: `TimeInitThread`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800021d0`

## callees

- `0x1800020d0`
- `0x18000b5ec`

## import_xrefs

- `ntdll!NtCreateEvent` at `0x18000b613`
- `ntdll!NtCreateEvent` at `0x18000b613`
- `ntdll!NtClose` at `0x18000b642`
- `ntdll!NtClose` at `0x18000b6a5`
- `ntdll!NtClose` at `0x18000b642`
- `ntdll!NtClose` at `0x18000b6a5`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000b629`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000b629`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000b6c0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000b6c0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000b67f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000b67f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b698`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b698`

## pseudocode

```c
__int64 TimeInitThread()
{
  HANDLE Thread; // rax

  if ( !LoadWINMM() || NtCreateEvent(&Handle, 0x1F0003u, 0, SynchronizationEvent, 0) < 0 )
    return 0;
  hHandle = CreateEventA(0, 1, 1, 0);
  if ( !hHandle )
  {
    NtClose(Handle);
LABEL_5:
    Handle = 0;
    return 0;
  }
  Thread = CreateThread(0, 0x12Cu, timeThread, 0, 0x20u, &TimerThreadId);
  hTimerThread = (__int64)Thread;
  if ( !Thread )
  {
    CloseHandle(hHandle);
    NtClose(Handle);
    hHandle = 0;
    goto LABEL_5;
  }
  SetThreadPriority(Thread, 15);
  return 1;
}

```

## disassembly

```asm
0x18000b5ec  sub     rsp, 38h
0x18000b5f0  call    LoadWINMM
0x18000b5f5  test    eax, eax
0x18000b5f7  jz      short loc_18000B653
0x18000b5f9  mov     r9d, 1; EventType
0x18000b5ff  mov     [rsp+38h+InitialState], 0; InitialState
0x18000b604  xor     r8d, r8d; ObjectAttributes
0x18000b607  lea     rcx, Handle; EventHandle
0x18000b60e  mov     edx, 1F0003h; DesiredAccess
0x18000b613  call    cs:__imp_NtCreateEvent
0x18000b619  test    eax, eax
0x18000b61b  js      short loc_18000B653
0x18000b61d  xor     r9d, r9d; lpName
0x18000b620  xor     ecx, ecx; lpEventAttributes
0x18000b622  lea     edx, [r9+1]; bManualReset
0x18000b626  mov     r8d, edx; bInitialState
0x18000b629  call    cs:__imp_CreateEventA
0x18000b62f  mov     cs:hHandle, rax
0x18000b636  test    rax, rax
0x18000b639  jnz     short loc_18000B65A
0x18000b63b  mov     rcx, cs:Handle; Handle
0x18000b642  call    cs:__imp_NtClose
0x18000b648  mov     cs:Handle, 0
0x18000b653  xor     eax, eax
0x18000b655  add     rsp, 38h
0x18000b659  retn
0x18000b65a  lea     rax, TimerThreadId
0x18000b661  xor     r9d, r9d; lpParameter
0x18000b664  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18000b669  lea     r8, timeThread; lpStartAddress
0x18000b670  mov     edx, 12Ch; dwStackSize
0x18000b675  mov     dword ptr [rsp+38h+InitialState], 20h ; ' '; dwCreationFlags
0x18000b67d  xor     ecx, ecx; lpThreadAttributes
0x18000b67f  call    cs:__imp_CreateThread
0x18000b685  mov     cs:hTimerThread, rax
0x18000b68c  test    rax, rax
0x18000b68f  jnz     short loc_18000B6B8
0x18000b691  mov     rcx, cs:hHandle; hObject
0x18000b698  call    cs:__imp_CloseHandle
0x18000b69e  mov     rcx, cs:Handle; Handle
0x18000b6a5  call    cs:__imp_NtClose
0x18000b6ab  mov     cs:hHandle, 0
0x18000b6b6  jmp     short loc_18000B648
0x18000b6b8  mov     edx, 0Fh; nPriority
0x18000b6bd  mov     rcx, rax; hThread
0x18000b6c0  call    cs:__imp_SetThreadPriority
0x18000b6c6  mov     eax, 1
0x18000b6cb  jmp     short loc_18000B655
```
