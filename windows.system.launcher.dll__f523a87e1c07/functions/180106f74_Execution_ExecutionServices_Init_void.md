# Execution::ExecutionServices::Init(void)

- ea: `0x180106f74`
- end: `0x1801070a0`
- name: `?Init@ExecutionServices@Execution@@IEAAJXZ`
- size: `300`
- prototype: `__int64 __fastcall(Execution::ExecutionServices *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180087ef8`

## callees

- `0x180106f74`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180106f90`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180106fd2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180106f90`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180106fd2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180107028`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180107028`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010706b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010706b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180106faa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180106fec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180107045`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180106faa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180106fec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180107045`

## pseudocode

```c
__int64 __fastcall Execution::ExecutionServices::Init(Execution::ExecutionServices *this)
{
  HANDLE EventW; // rbx
  HANDLE v3; // rax
  signed int v4; // ebx
  HANDLE v5; // rbx
  HANDLE v6; // rax
  HANDLE Thread; // rsi
  HANDLE v8; // rax
  signed int LastError; // eax

  EventW = CreateEventW(0, 0, 0, 0);
  v3 = (HANDLE)*((_QWORD *)this + 14);
  if ( EventW == v3 )
  {
    EventW = (HANDLE)*((_QWORD *)this + 14);
  }
  else
  {
    if ( v3 )
      CloseHandle(*((HANDLE *)this + 14));
    *((_QWORD *)this + 14) = EventW;
  }
  if ( !EventW )
    return (unsigned int)-2147467259;
  v5 = CreateEventW(0, 0, 0, 0);
  v6 = (HANDLE)*((_QWORD *)this + 15);
  if ( v5 == v6 )
  {
    v5 = (HANDLE)*((_QWORD *)this + 15);
  }
  else
  {
    if ( v6 )
      CloseHandle(*((HANDLE *)this + 15));
    *((_QWORD *)this + 15) = v5;
  }
  if ( v5 )
  {
    v4 = 0;
    (*(void (__fastcall **)(Execution::ExecutionServices *))(*(_QWORD *)this + 8LL))(this);
    Thread = CreateThread(0, 0, Execution::ExecutionServices::_WorkerThread, this, 0, 0);
    v8 = (HANDLE)*((_QWORD *)this + 16);
    if ( Thread == v8 )
    {
      Thread = (HANDLE)*((_QWORD *)this + 16);
    }
    else
    {
      if ( v8 )
        CloseHandle(*((HANDLE *)this + 16));
      *((_QWORD *)this + 16) = Thread;
    }
    if ( Thread )
      goto LABEL_23;
    (*(void (__fastcall **)(Execution::ExecutionServices *))(*(_QWORD *)this + 16LL))(this);
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
LABEL_23:
      *((_DWORD *)this + 34) = 1;
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180106f74  mov     [rsp+arg_0], rbx
0x180106f79  mov     [rsp+arg_8], rsi
0x180106f7e  push    rdi
0x180106f7f  sub     rsp, 30h
0x180106f83  mov     rdi, rcx
0x180106f86  xor     r9d, r9d; lpName
0x180106f89  xor     ecx, ecx; lpEventAttributes
0x180106f8b  xor     r8d, r8d; bInitialState
0x180106f8e  xor     edx, edx; bManualReset
0x180106f90  call    cs:__imp_CreateEventW
0x180106f96  mov     rbx, rax
0x180106f99  mov     rax, [rdi+70h]
0x180106f9d  cmp     rbx, rax
0x180106fa0  jz      short loc_180106FB6
0x180106fa2  test    rax, rax
0x180106fa5  jz      short loc_180106FB0
0x180106fa7  mov     rcx, rax; hObject
0x180106faa  call    cs:__imp_CloseHandle
0x180106fb0  mov     [rdi+70h], rbx
0x180106fb4  jmp     short loc_180106FB9
0x180106fb6  mov     rbx, rax
0x180106fb9  test    rbx, rbx
0x180106fbc  jnz     short loc_180106FC8
0x180106fbe  mov     ebx, 80004005h
0x180106fc3  jmp     loc_18010708E
0x180106fc8  xor     r9d, r9d; lpName
0x180106fcb  xor     r8d, r8d; bInitialState
0x180106fce  xor     edx, edx; bManualReset
0x180106fd0  xor     ecx, ecx; lpEventAttributes
0x180106fd2  call    cs:__imp_CreateEventW
0x180106fd8  mov     rbx, rax
0x180106fdb  mov     rax, [rdi+78h]
0x180106fdf  cmp     rbx, rax
0x180106fe2  jz      short loc_180106FF8
0x180106fe4  test    rax, rax
0x180106fe7  jz      short loc_180106FF2
0x180106fe9  mov     rcx, rax; hObject
0x180106fec  call    cs:__imp_CloseHandle
0x180106ff2  mov     [rdi+78h], rbx
0x180106ff6  jmp     short loc_180106FFB
0x180106ff8  mov     rbx, rax
0x180106ffb  test    rbx, rbx
0x180106ffe  jz      short loc_180106FBE
0x180107000  mov     rax, [rdi]
0x180107003  mov     rcx, rdi
0x180107006  xor     ebx, ebx
0x180107008  mov     rax, [rax+8]
0x18010700c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180107011  mov     r9, rdi; lpParameter
0x180107014  mov     [rsp+38h+lpThreadId], rbx; lpThreadId
0x180107019  lea     r8, ?_WorkerThread@ExecutionServices@Execution@@KAKPEAX@Z; lpStartAddress
0x180107020  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x180107024  xor     edx, edx; dwStackSize
0x180107026  xor     ecx, ecx; lpThreadAttributes
0x180107028  call    cs:__imp_CreateThread
0x18010702e  mov     rsi, rax
0x180107031  mov     rax, [rdi+80h]
0x180107038  cmp     rsi, rax
0x18010703b  jz      short loc_180107054
0x18010703d  test    rax, rax
0x180107040  jz      short loc_18010704B
0x180107042  mov     rcx, rax; hObject
0x180107045  call    cs:__imp_CloseHandle
0x18010704b  mov     [rdi+80h], rsi
0x180107052  jmp     short loc_180107057
0x180107054  mov     rsi, rax
0x180107057  test    rsi, rsi
0x18010705a  jnz     short loc_180107084
0x18010705c  mov     rax, [rdi]
0x18010705f  mov     rcx, rdi
0x180107062  mov     rax, [rax+10h]
0x180107066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010706b  call    cs:__imp_GetLastError
0x180107071  mov     ebx, eax
0x180107073  test    eax, eax
0x180107075  jle     short loc_180107080
0x180107077  movzx   ebx, ax
0x18010707a  or      ebx, 80070000h
0x180107080  test    ebx, ebx
0x180107082  js      short loc_18010708E
0x180107084  mov     dword ptr [rdi+88h], 1
0x18010708e  mov     rsi, [rsp+38h+arg_8]
0x180107093  mov     eax, ebx
0x180107095  mov     rbx, [rsp+38h+arg_0]
0x18010709a  add     rsp, 30h
0x18010709e  pop     rdi
0x18010709f  retn
```
