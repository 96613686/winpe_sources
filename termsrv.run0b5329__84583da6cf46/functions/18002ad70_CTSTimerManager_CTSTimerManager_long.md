# CTSTimerManager::CTSTimerManager(long &)

- ea: `0x18002ad70`
- end: `0x18002aee2`
- name: `??0CTSTimerManager@@AEAA@AEAJ@Z`
- size: `370`
- prototype: `CTSTimerManager *__fastcall(CTSTimerManager *__hidden this, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18006cb44`

## callees

- `0x180008770`
- `0x18000a210`
- `0x1800241f0`
- `0x180025fc4`
- `0x18002ad70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002ae22`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002ae65`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002ae22`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002ae65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae45`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002aea5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002aea5`

## string_xrefs

- `0x18002aebd`: `Error creating hThread of Timer Manager`

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
0x18002ad70  mov     [rsp+arg_8], rbx
0x18002ad75  mov     [rsp+arg_10], rsi
0x18002ad7a  mov     [rsp+arg_0], rcx
0x18002ad7f  push    rdi
0x18002ad80  sub     rsp, 30h
0x18002ad84  mov     rdi, rdx
0x18002ad87  mov     rbx, rcx
0x18002ad8a  lea     rdx, aCtstimermanage; "CTSTimerManager"
0x18002ad91  call    ??0?$CTSPrivateObject@UIUnknown@@@@QEAA@PEBD@Z; CTSPrivateObject<IUnknown>::CTSPrivateObject<IUnknown>(char const *)
0x18002ad96  nop
0x18002ad97  lea     rax, ??_7CTSTimerManager@@6B@; const CTSTimerManager::`vftable'
0x18002ad9e  mov     [rbx], rax
0x18002ada1  mov     qword ptr [rbx+638h], 0
0x18002adac  mov     qword ptr [rbx+640h], 0
0x18002adb7  mov     qword ptr [rbx+648h], 0
0x18002adc2  lea     rsi, [rbx+650h]
0x18002adc9  mov     qword ptr [rsi], 0
0x18002add0  lea     rcx, [rbx+658h]; this
0x18002add7  mov     dword ptr [rcx+60h], 0
0x18002adde  mov     qword ptr [rbx+6C0h], 0
0x18002ade9  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x18002adee  mov     [rdi], eax
0x18002adf0  test    eax, eax
0x18002adf2  jns     short loc_18002AE0A
0x18002adf4  lea     rdx, aFailedInitiali; "Failed initializing Lock"
0x18002adfb  mov     ecx, 8; int
0x18002ae00  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002ae05  jmp     loc_18002AECF
0x18002ae0a  xor     edx, edx
0x18002ae0c  mov     rcx, rsi
0x18002ae0f  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x18002ae14  xor     r9d, r9d; lpName
0x18002ae17  xor     r8d, r8d; bInitialState
0x18002ae1a  lea     esi, [r9+1]
0x18002ae1e  mov     edx, esi; bManualReset
0x18002ae20  xor     ecx, ecx; lpEventAttributes
0x18002ae22  call    cs:__imp_CreateEventW
0x18002ae28  mov     [rbx+640h], rax
0x18002ae2f  test    rax, rax
0x18002ae32  jnz     short loc_18002AE5B
0x18002ae34  lea     rdx, aErrorCreatingE; "Error creating event of Timer Manager"
0x18002ae3b  mov     ecx, 8; int
0x18002ae40  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002ae45  call    cs:__imp_GetLastError
0x18002ae4b  test    eax, eax
0x18002ae4d  jle     short loc_18002AE57
0x18002ae4f  movzx   eax, ax
0x18002ae52  or      eax, 80070000h
0x18002ae57  mov     [rdi], eax
0x18002ae59  jmp     short loc_18002AECF
0x18002ae5b  xor     r9d, r9d; lpName
0x18002ae5e  xor     r8d, r8d; bInitialState
0x18002ae61  xor     edx, edx; bManualReset
0x18002ae63  xor     ecx, ecx; lpEventAttributes
0x18002ae65  call    cs:__imp_CreateEventW
0x18002ae6b  mov     [rbx+648h], rax
0x18002ae72  test    rax, rax
0x18002ae75  jnz     short loc_18002AE80
0x18002ae77  lea     rdx, aErrorCreatingT; "Error creating terminate event of Timer"...
0x18002ae7e  jmp     short loc_18002AE3B
0x18002ae80  mov     [rbx+6C0h], esi
0x18002ae86  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18002ae8f  mov     [rsp+38h+dwCreationFlags], 20h ; ' '; dwCreationFlags
0x18002ae97  mov     r9, rbx; lpParameter
0x18002ae9a  lea     r8, ?staticTimerThread@CTSTimerManager@@SAKPEAX@Z; lpStartAddress
0x18002aea1  xor     edx, edx; dwStackSize
0x18002aea3  xor     ecx, ecx; lpThreadAttributes
0x18002aea5  call    cs:__imp_CreateThread
0x18002aeab  mov     [rbx+638h], rax
0x18002aeb2  test    rax, rax
0x18002aeb5  jnz     short loc_18002AEC9
0x18002aeb7  mov     [rbx+6C0h], eax
0x18002aebd  lea     rdx, aErrorCreatingH; "Error creating hThread of Timer Manager"
0x18002aec4  jmp     loc_18002AE3B
0x18002aec9  mov     dword ptr [rdi], 0
0x18002aecf  mov     rax, rbx
0x18002aed2  mov     rbx, [rsp+38h+arg_8]
0x18002aed7  mov     rsi, [rsp+38h+arg_10]
0x18002aedc  add     rsp, 30h
0x18002aee0  pop     rdi
0x18002aee1  retn
```
