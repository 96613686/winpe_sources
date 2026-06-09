# CRemoteConnectionManager::ChangeRCMReadyEventState(int)

- ea: `0x18002dddc`
- end: `0x18002deb8`
- name: `?ChangeRCMReadyEventState@CRemoteConnectionManager@@QEAAJH@Z`
- size: `220`
- prototype: `__int64 __fastcall(CRemoteConnectionManager *__hidden this, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18004aeb0`
- `0x18004cfb0`

## callees

- `0x18000a210`
- `0x18002dddc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002ddf4`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002ddf4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002de60`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002de60`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002de34`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002de34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002de02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002de3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002de6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002de02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002de3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002de6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dea5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dea5`

## string_xrefs

- `0x18002de1a`: `OpenEvent( Global\RCMReadyEvent ): 0x%x`
- `0x18002dde8`: `Global\RCMReadyEvent`
- `0x18002de8d`: `CRemoteConnectionManager::ChangeRCMReadyEventState`
- `0x18002de57`: `SetEvent( Global\hRCMReadyEvent ) failed: 0x%x in %s`
- `0x18002de83`: `ResetEvent( Global\hRCMReadyEvent ) failed: 0x%x in %s`

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
0x18002dddc  mov     [rsp+arg_0], rbx
0x18002dde1  push    rdi
0x18002dde2  sub     rsp, 20h
0x18002dde6  mov     ebx, edx
0x18002dde8  lea     r8, Name; "Global\\RCMReadyEvent"
0x18002ddef  xor     edx, edx; bInheritHandle
0x18002ddf1  lea     ecx, [rdx+2]; dwDesiredAccess
0x18002ddf4  call    cs:__imp_OpenEventW
0x18002ddfa  mov     rdi, rax
0x18002ddfd  test    rax, rax
0x18002de00  jnz     short loc_18002DE2D
0x18002de02  call    cs:__imp_GetLastError
0x18002de08  mov     ebx, eax
0x18002de0a  test    eax, eax
0x18002de0c  jle     short loc_18002DE17
0x18002de0e  movzx   ebx, ax
0x18002de11  or      ebx, 80070000h
0x18002de17  mov     r8d, ebx
0x18002de1a  lea     rdx, aOpeneventGloba; "OpenEvent( Global\\RCMReadyEvent ): 0x%"...
0x18002de21  mov     ecx, 8; int
0x18002de26  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002de2b  jmp     short loc_18002DEAB
0x18002de2d  mov     rcx, rdi; hEvent
0x18002de30  test    ebx, ebx
0x18002de32  jz      short loc_18002DE60
0x18002de34  call    cs:__imp_SetEvent
0x18002de3a  test    eax, eax
0x18002de3c  jnz     short loc_18002DEA0
0x18002de3e  call    cs:__imp_GetLastError
0x18002de44  mov     ebx, eax
0x18002de46  test    eax, eax
0x18002de48  jle     short loc_18002DE53
0x18002de4a  movzx   ebx, ax
0x18002de4d  or      ebx, 80070000h
0x18002de53  test    ebx, ebx
0x18002de55  jns     short loc_18002DEA2
0x18002de57  lea     rdx, aSeteventGlobal; "SetEvent( Global\\hRCMReadyEvent ) fail"...
0x18002de5e  jmp     short loc_18002DE8A
0x18002de60  call    cs:__imp_ResetEvent
0x18002de66  test    eax, eax
0x18002de68  jnz     short loc_18002DEA0
0x18002de6a  call    cs:__imp_GetLastError
0x18002de70  mov     ebx, eax
0x18002de72  test    eax, eax
0x18002de74  jle     short loc_18002DE7F
0x18002de76  movzx   ebx, ax
0x18002de79  or      ebx, 80070000h
0x18002de7f  test    ebx, ebx
0x18002de81  jns     short loc_18002DEA2
0x18002de83  lea     rdx, aReseteventGlob; "ResetEvent( Global\\hRCMReadyEvent ) fa"...
0x18002de8a  mov     r8d, ebx
0x18002de8d  lea     r9, aCremoteconnect_24; "CRemoteConnectionManager::ChangeRCMRead"...
0x18002de94  mov     ecx, 8; int
0x18002de99  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002de9e  jmp     short loc_18002DEA2
0x18002dea0  xor     ebx, ebx
0x18002dea2  mov     rcx, rdi; hObject
0x18002dea5  call    cs:__imp_CloseHandle
0x18002deab  mov     eax, ebx
0x18002dead  mov     rbx, [rsp+28h+arg_0]
0x18002deb2  add     rsp, 20h
0x18002deb6  pop     rdi
0x18002deb7  retn
```
