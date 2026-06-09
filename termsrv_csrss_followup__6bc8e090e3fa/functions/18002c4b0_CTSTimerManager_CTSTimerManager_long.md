# CTSTimerManager::CTSTimerManager(long &)

- ea: `0x18002c4b0`
- end: `0x18002c63e`
- name: `??0CTSTimerManager@@AEAA@AEAJ@Z`
- size: `398`
- prototype: `CTSTimerManager *__fastcall(CTSTimerManager *__hidden this, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18006fff4`

## callees

- `0x180007d10`
- `0x180009940`
- `0x18002558c`
- `0x180027434`
- `0x18002c4b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c562`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c5b4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c562`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c5b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c58b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c58b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002c5fa`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002c5fa`

## string_xrefs

- `0x18002c618`: `Error creating hThread of Timer Manager`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
CTSTimerManager *__fastcall CTSTimerManager::CTSTimerManager(CTSTimerManager *this, int *a2)
{
  int v4; // eax
  HANDLE EventW; // rax
  signed int LastError; // eax
  HANDLE v7; // rax
  HANDLE Thread; // rax

  CTSPrivateObject<IUnknown>::CTSPrivateObject<IUnknown>(this, "CTSTimerManager");
  *(_QWORD *)this = &CTSTimerManager::`vftable';
  *((_QWORD *)this + 199) = 0;
  *((_QWORD *)this + 200) = 0;
  *((_QWORD *)this + 201) = 0;
  *((_QWORD *)this + 202) = 0;
  *((_DWORD *)this + 430) = 0;
  *((_QWORD *)this + 216) = 0;
  v4 = CResource::Initialize((CTSTimerManager *)((char *)this + 1624));
  *a2 = v4;
  if ( v4 >= 0 )
  {
    SmartPtr<ITerminal>::operator=((char *)this + 1616, 0);
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 200) = EventW;
    if ( EventW )
    {
      v7 = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)this + 201) = v7;
      if ( v7 )
      {
        *((_DWORD *)this + 432) = 1;
        Thread = CreateThread(0, 0, CTSTimerManager::staticTimerThread, this, 0x20u, 0);
        *((_QWORD *)this + 199) = Thread;
        if ( Thread )
        {
          *a2 = 0;
          return this;
        }
        *((_DWORD *)this + 432) = 0;
        _DbgPrintMessage(8, "Error creating hThread of Timer Manager");
      }
      else
      {
        _DbgPrintMessage(8, "Error creating terminate event of Timer Manager");
      }
    }
    else
    {
      _DbgPrintMessage(8, "Error creating event of Timer Manager");
    }
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    *a2 = LastError;
  }
  else
  {
    _DbgPrintMessage(8, "Failed initializing Lock");
  }
  return this;
}

```

## disassembly

```asm
0x18002c4b0  mov     [rsp+arg_8], rbx
0x18002c4b5  mov     [rsp+arg_10], rsi
0x18002c4ba  mov     [rsp+arg_0], rcx
0x18002c4bf  push    rdi
0x18002c4c0  sub     rsp, 30h
0x18002c4c4  mov     rdi, rdx
0x18002c4c7  mov     rbx, rcx
0x18002c4ca  lea     rdx, aCtstimermanage; "CTSTimerManager"
0x18002c4d1  call    ??0?$CTSPrivateObject@UIUnknown@@@@QEAA@PEBD@Z; CTSPrivateObject<IUnknown>::CTSPrivateObject<IUnknown>(char const *)
0x18002c4d6  nop
0x18002c4d7  lea     rax, ??_7CTSTimerManager@@6B@; const CTSTimerManager::`vftable'
0x18002c4de  mov     [rbx], rax
0x18002c4e1  mov     qword ptr [rbx+638h], 0
0x18002c4ec  mov     qword ptr [rbx+640h], 0
0x18002c4f7  mov     qword ptr [rbx+648h], 0
0x18002c502  lea     rsi, [rbx+650h]
0x18002c509  mov     qword ptr [rsi], 0
0x18002c510  lea     rcx, [rbx+658h]; this
0x18002c517  mov     dword ptr [rcx+60h], 0
0x18002c51e  mov     qword ptr [rbx+6C0h], 0
0x18002c529  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x18002c52e  mov     [rdi], eax
0x18002c530  test    eax, eax
0x18002c532  jns     short loc_18002C54A
0x18002c534  lea     rdx, aFailedInitiali; "Failed initializing Lock"
0x18002c53b  mov     ecx, 8; int
0x18002c540  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002c545  jmp     loc_18002C62A
0x18002c54a  xor     edx, edx
0x18002c54c  mov     rcx, rsi
0x18002c54f  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x18002c554  xor     r9d, r9d; lpName
0x18002c557  xor     r8d, r8d; bInitialState
0x18002c55a  lea     esi, [r9+1]
0x18002c55e  mov     edx, esi; bManualReset
0x18002c560  xor     ecx, ecx; lpEventAttributes
0x18002c562  call    cs:__imp_CreateEventW
0x18002c569  nop     dword ptr [rax+rax+00h]
0x18002c56e  mov     [rbx+640h], rax
0x18002c575  test    rax, rax
0x18002c578  jnz     short loc_18002C5AA
0x18002c57a  lea     rdx, aErrorCreatingE; "Error creating event of Timer Manager"
0x18002c581  mov     ecx, 8; int
0x18002c586  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002c58b  call    cs:__imp_GetLastError
0x18002c592  nop     dword ptr [rax+rax+00h]
0x18002c597  test    eax, eax
0x18002c599  jle     short loc_18002C5A3
0x18002c59b  movzx   eax, ax
0x18002c59e  or      eax, 80070000h
0x18002c5a3  mov     [rdi], eax
0x18002c5a5  jmp     loc_18002C62A
0x18002c5aa  xor     r9d, r9d; lpName
0x18002c5ad  xor     r8d, r8d; bInitialState
0x18002c5b0  xor     edx, edx; bManualReset
0x18002c5b2  xor     ecx, ecx; lpEventAttributes
0x18002c5b4  call    cs:__imp_CreateEventW
0x18002c5bb  nop     dword ptr [rax+rax+00h]
0x18002c5c0  mov     [rbx+648h], rax
0x18002c5c7  test    rax, rax
0x18002c5ca  jnz     short loc_18002C5D5
0x18002c5cc  lea     rdx, aErrorCreatingT; "Error creating terminate event of Timer"...
0x18002c5d3  jmp     short loc_18002C581
0x18002c5d5  mov     [rbx+6C0h], esi
0x18002c5db  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18002c5e4  mov     [rsp+38h+dwCreationFlags], 20h ; ' '; dwCreationFlags
0x18002c5ec  mov     r9, rbx; lpParameter
0x18002c5ef  lea     r8, ?staticTimerThread@CTSTimerManager@@SAKPEAX@Z; lpStartAddress
0x18002c5f6  xor     edx, edx; dwStackSize
0x18002c5f8  xor     ecx, ecx; lpThreadAttributes
0x18002c5fa  call    cs:__imp_CreateThread
0x18002c601  nop     dword ptr [rax+rax+00h]
0x18002c606  mov     [rbx+638h], rax
0x18002c60d  test    rax, rax
0x18002c610  jnz     short loc_18002C624
0x18002c612  mov     [rbx+6C0h], eax
0x18002c618  lea     rdx, aErrorCreatingH; "Error creating hThread of Timer Manager"
0x18002c61f  jmp     loc_18002C581
0x18002c624  mov     dword ptr [rdi], 0
0x18002c62a  mov     rax, rbx
0x18002c62d  mov     rbx, [rsp+38h+arg_8]
0x18002c632  mov     rsi, [rsp+38h+arg_10]
0x18002c637  add     rsp, 30h
0x18002c63b  pop     rdi
0x18002c63c  retn
```
