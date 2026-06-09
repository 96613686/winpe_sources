# CWdiHandler::Stop(long *)

- ea: `0x180003a30`
- end: `0x180003b1a`
- name: `?Stop@CWdiHandler@@UEAAJPEAJ@Z`
- size: `234`
- prototype: `__int64 __fastcall(HANDLE *this, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002ba0`
- `0x180003a30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003a75`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003a75`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003a60`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003a60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ab0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ab0`

## string_xrefs

- `0x180003af9`: `clientcore\base\diagnosis\pdi\wdi\framework\library\taskhandler.cpp`

## pseudocode

```c
__int64 __fastcall CWdiHandler::Stop(HANDLE *this, int *a2)
{
  signed int Args; // edi
  DWORD v4; // eax
  signed int v5; // eax
  signed int LastError; // eax

  if ( this[2] )
  {
    if ( SetEvent(this[3]) )
    {
      Args = 0;
    }
    else
    {
      LastError = GetLastError();
      Args = LastError;
      if ( LastError > 0 )
        Args = (unsigned __int16)LastError | 0x80070000;
      if ( Args < 0 )
      {
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\taskhandler.cpp",
          (int)L"CWdiHandler::Stop",
          167,
          (int)L"Error = %d",
          Args);
        goto LABEL_16;
      }
    }
    v4 = WaitForSingleObject(this[2], 0xFFFFFFFF);
    if ( v4 )
    {
      if ( v4 != -1 )
        goto LABEL_15;
      v5 = GetLastError();
      Args = v5;
      if ( v5 > 0 )
        Args = (unsigned __int16)v5 | 0x80070000;
      if ( Args < 0 )
      {
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\taskhandler.cpp",
          (int)L"CWdiHandler::Stop",
          180,
          (int)L"Error = %d",
          Args);
      }
      else
      {
LABEL_15:
        Args = -2147467259;
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\taskhandler.cpp",
          (int)L"CWdiHandler::Stop",
          184,
          (int)L"Error = %d",
          5);
      }
    }
  }
  else
  {
    Args = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\taskhandler.cpp",
      (int)L"CWdiHandler::Stop",
      161,
      (int)L"Error = %d",
      87);
  }
LABEL_16:
  _InterlockedExchange(&g_HostState, 0);
  return (unsigned int)Args;
}

```

## disassembly

```asm
0x180003a30  mov     [rsp+arg_0], rbx
0x180003a35  push    rdi
0x180003a36  sub     rsp, 30h
0x180003a3a  cmp     qword ptr [rcx+10h], 0
0x180003a3f  mov     rbx, rcx
0x180003a42  jnz     short loc_180003A5C
0x180003a44  mov     edi, 80070057h
0x180003a49  mov     dword ptr [rsp+38h+Args], 57h ; 'W'
0x180003a51  mov     r8d, 0A1h
0x180003a57  jmp     loc_180003AEB
0x180003a5c  mov     rcx, [rcx+18h]; hEvent
0x180003a60  call    cs:__imp_SetEvent
0x180003a66  test    eax, eax
0x180003a68  jz      short loc_180003AB0
0x180003a6a  xor     edi, edi
0x180003a6c  mov     rcx, [rbx+10h]; hHandle
0x180003a70  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180003a75  call    cs:__imp_WaitForSingleObject
0x180003a7b  test    eax, eax
0x180003a7d  jz      loc_180003B05
0x180003a83  cmp     eax, 0FFFFFFFFh
0x180003a86  jnz     short loc_180003AD8
0x180003a88  call    cs:__imp_GetLastError
0x180003a8e  mov     edi, eax
0x180003a90  test    eax, eax
0x180003a92  jle     short loc_180003A9D
0x180003a94  movzx   edi, ax
0x180003a97  or      edi, 80070000h
0x180003a9d  test    edi, edi
0x180003a9f  jns     short loc_180003AD8
0x180003aa1  movzx   eax, di
0x180003aa4  mov     r8d, 0B4h
0x180003aaa  mov     dword ptr [rsp+38h+Args], eax
0x180003aae  jmp     short loc_180003AEB
0x180003ab0  call    cs:__imp_GetLastError
0x180003ab6  mov     edi, eax
0x180003ab8  test    eax, eax
0x180003aba  jle     short loc_180003AC5
0x180003abc  movzx   edi, ax
0x180003abf  or      edi, 80070000h
0x180003ac5  test    edi, edi
0x180003ac7  jns     short loc_180003A6C
0x180003ac9  movzx   eax, di
0x180003acc  mov     r8d, 0A7h
0x180003ad2  mov     dword ptr [rsp+38h+Args], eax
0x180003ad6  jmp     short loc_180003AEB
0x180003ad8  mov     edi, 80004005h
0x180003add  mov     dword ptr [rsp+38h+Args], 4005h; Args
0x180003ae5  mov     r8d, 0B8h; int
0x180003aeb  lea     r9, aErrorD_0; "Error = %d"
0x180003af2  lea     rdx, aCwdihandlerSto; "CWdiHandler::Stop"
0x180003af9  lea     rcx, aClientcoreBase_9; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180003b00  call    WdipTraceError
0x180003b05  mov     rbx, [rsp+38h+arg_0]
0x180003b0a  xor     ecx, ecx
0x180003b0c  xchg    ecx, cs:g_HostState
0x180003b12  mov     eax, edi
0x180003b14  add     rsp, 30h
0x180003b18  pop     rdi
0x180003b19  retn
```
