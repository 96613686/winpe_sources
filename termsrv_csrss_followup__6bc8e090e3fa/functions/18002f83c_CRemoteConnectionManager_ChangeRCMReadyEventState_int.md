# CRemoteConnectionManager::ChangeRCMReadyEventState(int)

- ea: `0x18002f83c`
- end: `0x18002f946`
- name: `?ChangeRCMReadyEventState@CRemoteConnectionManager@@QEAAJH@Z`
- size: `266`
- prototype: `__int64 __fastcall(CRemoteConnectionManager *__hidden this, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18004d4d0`
- `0x18004f5e0`

## callees

- `0x180009940`
- `0x18002f83c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002f854`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002f854`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002f8db`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002f8db`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f8a3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f8a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f868`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f8b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f8eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f868`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f8b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f8eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f92c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f92c`

## string_xrefs

- `0x18002f886`: `OpenEvent( Global\RCMReadyEvent ): 0x%x`
- `0x18002f848`: `Global\RCMReadyEvent`
- `0x18002f914`: `CRemoteConnectionManager::ChangeRCMReadyEventState`
- `0x18002f8d2`: `SetEvent( Global\hRCMReadyEvent ) failed: 0x%x in %s`
- `0x18002f90a`: `ResetEvent( Global\hRCMReadyEvent ) failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CRemoteConnectionManager::ChangeRCMReadyEventState(CRemoteConnectionManager *this, int a2)
{
  HANDLE v3; // rax
  void *v4; // rdi
  signed int v5; // eax
  unsigned int v6; // ebx
  signed int LastError; // eax
  signed int v8; // eax

  v3 = OpenEventW(2u, 0, L"Global\\RCMReadyEvent");
  v4 = v3;
  if ( v3 )
  {
    if ( a2 )
    {
      if ( !SetEvent(v3) )
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        if ( (v6 & 0x80000000) != 0 )
          _DbgPrintMessage(
            8,
            "SetEvent( Global\\hRCMReadyEvent ) failed: 0x%x in %s",
            v6,
            "CRemoteConnectionManager::ChangeRCMReadyEventState");
        goto LABEL_18;
      }
    }
    else if ( !ResetEvent(v3) )
    {
      v8 = GetLastError();
      v6 = v8;
      if ( v8 > 0 )
        v6 = (unsigned __int16)v8 | 0x80070000;
      if ( (v6 & 0x80000000) != 0 )
        _DbgPrintMessage(
          8,
          "ResetEvent( Global\\hRCMReadyEvent ) failed: 0x%x in %s",
          v6,
          "CRemoteConnectionManager::ChangeRCMReadyEventState");
      goto LABEL_18;
    }
    v6 = 0;
LABEL_18:
    CloseHandle(v4);
    return v6;
  }
  v5 = GetLastError();
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  _DbgPrintMessage(8, "OpenEvent( Global\\RCMReadyEvent ): 0x%x", v6);
  return v6;
}

```

## disassembly

```asm
0x18002f83c  mov     [rsp+arg_0], rbx
0x18002f841  push    rdi
0x18002f842  sub     rsp, 20h
0x18002f846  mov     ebx, edx
0x18002f848  lea     r8, Name; "Global\\RCMReadyEvent"
0x18002f84f  xor     edx, edx; bInheritHandle
0x18002f851  lea     ecx, [rdx+2]; dwDesiredAccess
0x18002f854  call    cs:__imp_OpenEventW
0x18002f85b  nop     dword ptr [rax+rax+00h]
0x18002f860  mov     rdi, rax
0x18002f863  test    rax, rax
0x18002f866  jnz     short loc_18002F89C
0x18002f868  call    cs:__imp_GetLastError
0x18002f86f  nop     dword ptr [rax+rax+00h]
0x18002f874  mov     ebx, eax
0x18002f876  test    eax, eax
0x18002f878  jle     short loc_18002F883
0x18002f87a  movzx   ebx, ax
0x18002f87d  or      ebx, 80070000h
0x18002f883  mov     r8d, ebx
0x18002f886  lea     rdx, aOpeneventGloba; "OpenEvent( Global\\RCMReadyEvent ): 0x%"...
0x18002f88d  mov     ecx, 8; int
0x18002f892  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002f897  jmp     loc_18002F938
0x18002f89c  mov     rcx, rdi; hEvent
0x18002f89f  test    ebx, ebx
0x18002f8a1  jz      short loc_18002F8DB
0x18002f8a3  call    cs:__imp_SetEvent
0x18002f8aa  nop     dword ptr [rax+rax+00h]
0x18002f8af  test    eax, eax
0x18002f8b1  jnz     short loc_18002F927
0x18002f8b3  call    cs:__imp_GetLastError
0x18002f8ba  nop     dword ptr [rax+rax+00h]
0x18002f8bf  mov     ebx, eax
0x18002f8c1  test    eax, eax
0x18002f8c3  jle     short loc_18002F8CE
0x18002f8c5  movzx   ebx, ax
0x18002f8c8  or      ebx, 80070000h
0x18002f8ce  test    ebx, ebx
0x18002f8d0  jns     short loc_18002F929
0x18002f8d2  lea     rdx, aSeteventGlobal; "SetEvent( Global\\hRCMReadyEvent ) fail"...
0x18002f8d9  jmp     short loc_18002F911
0x18002f8db  call    cs:__imp_ResetEvent
0x18002f8e2  nop     dword ptr [rax+rax+00h]
0x18002f8e7  test    eax, eax
0x18002f8e9  jnz     short loc_18002F927
0x18002f8eb  call    cs:__imp_GetLastError
0x18002f8f2  nop     dword ptr [rax+rax+00h]
0x18002f8f7  mov     ebx, eax
0x18002f8f9  test    eax, eax
0x18002f8fb  jle     short loc_18002F906
0x18002f8fd  movzx   ebx, ax
0x18002f900  or      ebx, 80070000h
0x18002f906  test    ebx, ebx
0x18002f908  jns     short loc_18002F929
0x18002f90a  lea     rdx, aReseteventGlob; "ResetEvent( Global\\hRCMReadyEvent ) fa"...
0x18002f911  mov     r8d, ebx
0x18002f914  lea     r9, aCremoteconnect_24; "CRemoteConnectionManager::ChangeRCMRead"...
0x18002f91b  mov     ecx, 8; int
0x18002f920  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002f925  jmp     short loc_18002F929
0x18002f927  xor     ebx, ebx
0x18002f929  mov     rcx, rdi; hObject
0x18002f92c  call    cs:__imp_CloseHandle
0x18002f933  nop     dword ptr [rax+rax+00h]
0x18002f938  mov     eax, ebx
0x18002f93a  mov     rbx, [rsp+28h+arg_0]
0x18002f93f  add     rsp, 20h
0x18002f943  pop     rdi
0x18002f944  retn
```
