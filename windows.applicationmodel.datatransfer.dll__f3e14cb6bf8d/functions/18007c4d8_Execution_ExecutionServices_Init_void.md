# Execution::ExecutionServices::Init(void)

- ea: `0x18007c4d8`
- end: `0x18007c604`
- name: `?Init@ExecutionServices@Execution@@IEAAJXZ`
- size: `300`
- prototype: `__int64 __fastcall(Execution::ExecutionServices *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180066c70`

## callees

- `0x18007c4d8`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c4f4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c536`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c4f4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c536`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18007c58c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18007c58c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c5cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c5cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c50e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c550`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c5a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c50e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c550`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c5a9`

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
0x18007c4d8  mov     [rsp+arg_0], rbx
0x18007c4dd  mov     [rsp+arg_8], rsi
0x18007c4e2  push    rdi
0x18007c4e3  sub     rsp, 30h
0x18007c4e7  mov     rdi, rcx
0x18007c4ea  xor     r9d, r9d; lpName
0x18007c4ed  xor     ecx, ecx; lpEventAttributes
0x18007c4ef  xor     r8d, r8d; bInitialState
0x18007c4f2  xor     edx, edx; bManualReset
0x18007c4f4  call    cs:__imp_CreateEventW
0x18007c4fa  mov     rbx, rax
0x18007c4fd  mov     rax, [rdi+70h]
0x18007c501  cmp     rbx, rax
0x18007c504  jz      short loc_18007C51A
0x18007c506  test    rax, rax
0x18007c509  jz      short loc_18007C514
0x18007c50b  mov     rcx, rax; hObject
0x18007c50e  call    cs:__imp_CloseHandle
0x18007c514  mov     [rdi+70h], rbx
0x18007c518  jmp     short loc_18007C51D
0x18007c51a  mov     rbx, rax
0x18007c51d  test    rbx, rbx
0x18007c520  jnz     short loc_18007C52C
0x18007c522  mov     ebx, 80004005h
0x18007c527  jmp     loc_18007C5F2
0x18007c52c  xor     r9d, r9d; lpName
0x18007c52f  xor     r8d, r8d; bInitialState
0x18007c532  xor     edx, edx; bManualReset
0x18007c534  xor     ecx, ecx; lpEventAttributes
0x18007c536  call    cs:__imp_CreateEventW
0x18007c53c  mov     rbx, rax
0x18007c53f  mov     rax, [rdi+78h]
0x18007c543  cmp     rbx, rax
0x18007c546  jz      short loc_18007C55C
0x18007c548  test    rax, rax
0x18007c54b  jz      short loc_18007C556
0x18007c54d  mov     rcx, rax; hObject
0x18007c550  call    cs:__imp_CloseHandle
0x18007c556  mov     [rdi+78h], rbx
0x18007c55a  jmp     short loc_18007C55F
0x18007c55c  mov     rbx, rax
0x18007c55f  test    rbx, rbx
0x18007c562  jz      short loc_18007C522
0x18007c564  mov     rax, [rdi]
0x18007c567  mov     rcx, rdi
0x18007c56a  xor     ebx, ebx
0x18007c56c  mov     rax, [rax+8]
0x18007c570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c575  mov     r9, rdi; lpParameter
0x18007c578  mov     [rsp+38h+lpThreadId], rbx; lpThreadId
0x18007c57d  lea     r8, ?_WorkerThread@ExecutionServices@Execution@@KAKPEAX@Z; lpStartAddress
0x18007c584  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x18007c588  xor     edx, edx; dwStackSize
0x18007c58a  xor     ecx, ecx; lpThreadAttributes
0x18007c58c  call    cs:__imp_CreateThread
0x18007c592  mov     rsi, rax
0x18007c595  mov     rax, [rdi+80h]
0x18007c59c  cmp     rsi, rax
0x18007c59f  jz      short loc_18007C5B8
0x18007c5a1  test    rax, rax
0x18007c5a4  jz      short loc_18007C5AF
0x18007c5a6  mov     rcx, rax; hObject
0x18007c5a9  call    cs:__imp_CloseHandle
0x18007c5af  mov     [rdi+80h], rsi
0x18007c5b6  jmp     short loc_18007C5BB
0x18007c5b8  mov     rsi, rax
0x18007c5bb  test    rsi, rsi
0x18007c5be  jnz     short loc_18007C5E8
0x18007c5c0  mov     rax, [rdi]
0x18007c5c3  mov     rcx, rdi
0x18007c5c6  mov     rax, [rax+10h]
0x18007c5ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c5cf  call    cs:__imp_GetLastError
0x18007c5d5  mov     ebx, eax
0x18007c5d7  test    eax, eax
0x18007c5d9  jle     short loc_18007C5E4
0x18007c5db  movzx   ebx, ax
0x18007c5de  or      ebx, 80070000h
0x18007c5e4  test    ebx, ebx
0x18007c5e6  js      short loc_18007C5F2
0x18007c5e8  mov     dword ptr [rdi+88h], 1
0x18007c5f2  mov     rsi, [rsp+38h+arg_8]
0x18007c5f7  mov     eax, ebx
0x18007c5f9  mov     rbx, [rsp+38h+arg_0]
0x18007c5fe  add     rsp, 30h
0x18007c602  pop     rdi
0x18007c603  retn
```
