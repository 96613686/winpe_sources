# _pSpUtilsInitializeSynchronizedAccess

- ea: `0x180017fa4`
- end: `0x180018026`
- name: `_pSpUtilsInitializeSynchronizedAccess`
- size: `130`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001165c`

## callees

- `0x180017fa4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180017fd9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180017fd9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180017fc4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180017fc4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018006`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018006`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017fec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017fec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017ff7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017ff7`

## pseudocode

```c
__int64 __fastcall pSpUtilsInitializeSynchronizedAccess(__int64 a1)
{
  HANDLE EventW; // rax
  HANDLE MutexW; // rax
  DWORD LastError; // ebx

  EventW = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)a1 = EventW;
  if ( EventW )
  {
    MutexW = CreateMutexW(0, 0, 0);
    *(_QWORD *)(a1 + 8) = MutexW;
    if ( MutexW )
      return 1;
    LastError = GetLastError();
    CloseHandle(*(HANDLE *)a1);
    *(_QWORD *)a1 = 0;
    SetLastError(LastError);
  }
  *(_QWORD *)(a1 + 8) = 0;
  return 0;
}

```

## disassembly

```asm
0x180017fa4  mov     [rsp+arg_0], rbx
0x180017fa9  mov     [rsp+arg_8], rsi
0x180017fae  push    rdi
0x180017faf  sub     rsp, 20h
0x180017fb3  xor     r9d, r9d; lpName
0x180017fb6  mov     rsi, rcx
0x180017fb9  xor     r8d, r8d; bInitialState
0x180017fbc  xor     ecx, ecx; lpEventAttributes
0x180017fbe  lea     ebx, [r9+1]
0x180017fc2  mov     edx, ebx; bManualReset
0x180017fc4  call    cs:__imp_CreateEventW
0x180017fca  mov     [rsi], rax
0x180017fcd  test    rax, rax
0x180017fd0  jz      short loc_18001800C
0x180017fd2  xor     r8d, r8d; lpName
0x180017fd5  xor     edx, edx; bInitialOwner
0x180017fd7  xor     ecx, ecx; lpMutexAttributes
0x180017fd9  call    cs:__imp_CreateMutexW
0x180017fdf  mov     [rsi+8], rax
0x180017fe3  test    rax, rax
0x180017fe6  jz      short loc_180017FEC
0x180017fe8  mov     eax, ebx
0x180017fea  jmp     short loc_180018016
0x180017fec  call    cs:__imp_GetLastError
0x180017ff2  mov     rcx, [rsi]; hObject
0x180017ff5  mov     ebx, eax
0x180017ff7  call    cs:__imp_CloseHandle
0x180017ffd  mov     ecx, ebx; dwErrCode
0x180017fff  mov     qword ptr [rsi], 0
0x180018006  call    cs:__imp_SetLastError
0x18001800c  mov     qword ptr [rsi+8], 0
0x180018014  xor     eax, eax
0x180018016  mov     rbx, [rsp+28h+arg_0]
0x18001801b  mov     rsi, [rsp+28h+arg_8]
0x180018020  add     rsp, 20h
0x180018024  pop     rdi
0x180018025  retn
```
