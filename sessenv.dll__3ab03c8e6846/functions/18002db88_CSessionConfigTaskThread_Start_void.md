# CSessionConfigTaskThread::Start(void)

- ea: `0x18002db88`
- end: `0x18002dc1c`
- name: `?Start@CSessionConfigTaskThread@@QEAAJXZ`
- size: `148`
- prototype: `__int64 __fastcall(CSessionConfigTaskThread *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18002c890`
- `0x18002d3cc`

## callees

- `0x180003f30`
- `0x18002db88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dbbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dbbd`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18002dbf2`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18002dbf2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002dbae`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002dbae`

## string_xrefs

- `0x18002dbd6`: `CSessionConfigTaskThread::Start`
- `0x18002dbe0`: `CreateThread failed: 0x%x in %s`
- `0x18002dbfb`: `thread started:  id = 0x%X  obj = 0x%X\n`

## pseudocode

```c
__int64 __fastcall CSessionConfigTaskThread::Start(HANDLE *this)
{
  unsigned int v1; // ebx
  HANDLE Thread; // rax
  signed int LastError; // eax
  DWORD ThreadId; // eax

  v1 = 0;
  Thread = CreateThread(0, 0, CSessionConfigTaskThread::s_ThreadProc, this, 0, 0);
  this[1] = Thread;
  if ( Thread )
    goto LABEL_6;
  LastError = GetLastError();
  v1 = LastError;
  if ( LastError > 0 )
    v1 = (unsigned __int16)LastError | 0x80070000;
  if ( (v1 & 0x80000000) == 0 )
  {
LABEL_6:
    ThreadId = GetThreadId(this[1]);
    _DbgPrintMessage(1, "thread started:  id = 0x%X  obj = 0x%X\n", ThreadId, this);
  }
  else
  {
    _DbgPrintMessage(8, "CreateThread failed: 0x%x in %s", v1, "CSessionConfigTaskThread::Start");
  }
  return v1;
}

```

## disassembly

```asm
0x18002db88  mov     [rsp+arg_0], rbx
0x18002db8d  push    rdi
0x18002db8e  sub     rsp, 30h
0x18002db92  xor     ebx, ebx
0x18002db94  lea     r8, ?s_ThreadProc@CSessionConfigTaskThread@@CAKPEAX@Z; lpStartAddress
0x18002db9b  mov     rdi, rcx
0x18002db9e  mov     [rsp+38h+lpThreadId], rbx; lpThreadId
0x18002dba3  mov     r9, rcx; lpParameter
0x18002dba6  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x18002dbaa  xor     edx, edx; dwStackSize
0x18002dbac  xor     ecx, ecx; lpThreadAttributes
0x18002dbae  call    cs:__imp_CreateThread
0x18002dbb4  mov     [rdi+8], rax
0x18002dbb8  test    rax, rax
0x18002dbbb  jnz     short loc_18002DBEE
0x18002dbbd  call    cs:__imp_GetLastError
0x18002dbc3  mov     ebx, eax
0x18002dbc5  test    eax, eax
0x18002dbc7  jle     short loc_18002DBD2
0x18002dbc9  movzx   ebx, ax
0x18002dbcc  or      ebx, 80070000h
0x18002dbd2  test    ebx, ebx
0x18002dbd4  jns     short loc_18002DBEE
0x18002dbd6  lea     r9, aCsessionconfig_5; "CSessionConfigTaskThread::Start"
0x18002dbdd  mov     r8d, ebx
0x18002dbe0  lea     rdx, aCreatethreadFa_0; "CreateThread failed: 0x%x in %s"
0x18002dbe7  mov     ecx, 8
0x18002dbec  jmp     short loc_18002DC0A
0x18002dbee  mov     rcx, [rdi+8]; Thread
0x18002dbf2  call    cs:__imp_GetThreadId
0x18002dbf8  mov     r9, rdi
0x18002dbfb  lea     rdx, aThreadStartedI; "thread started:  id = 0x%X  obj = 0x%X"...
0x18002dc02  mov     r8d, eax
0x18002dc05  mov     ecx, 1; int
0x18002dc0a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002dc0f  mov     eax, ebx
0x18002dc11  mov     rbx, [rsp+38h+arg_0]
0x18002dc16  add     rsp, 30h
0x18002dc1a  pop     rdi
0x18002dc1b  retn
```
