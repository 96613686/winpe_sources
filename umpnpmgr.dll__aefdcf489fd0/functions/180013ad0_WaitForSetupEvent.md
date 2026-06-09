# WaitForSetupEvent

- ea: `0x180013ad0`
- end: `0x180013b85`
- name: `WaitForSetupEvent`
- size: `181`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000a6b0`

## callees

- `0x1800135f0`
- `0x180013ad0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180013b13`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180013b13`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180013b69`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180013b69`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180013aea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180013aea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013af8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013af8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013b72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013b72`

## string_xrefs

- `0x180013add`: `Global\PNP_Create_Pipe_Event`
- `0x180013b05`: `Global\PNP_Create_Pipe_Event`
- `0x180013b46`: `Global\PNP_Create_Pipe_Event`

## pseudocode

```c
__int64 WaitForSetupEvent()
{
  HANDLE EventW; // rdi
  DWORD LastError; // ebx
  int v2; // r8d

  EventW = CreateEventW(0, 1, 0, L"Global\\PNP_Create_Pipe_Event");
  if ( EventW || GetLastError() == 183 && (EventW = OpenEventW(0x100000u, 0, L"Global\\PNP_Create_Pipe_Event")) != 0 )
  {
    LastError = 0;
    WaitForSingleObjectEx(EventW, 0xFFFFFFFF, 1);
    CloseHandle(EventW);
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, v2, (unsigned int)L"Global\\PNP_Create_Pipe_Event", LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180013ad0  mov     [rsp+arg_0], rbx
0x180013ad5  push    rdi
0x180013ad6  sub     rsp, 30h
0x180013ada  xor     r8d, r8d; bInitialState
0x180013add  lea     r9, aGlobalPnpCreat; "Global\\PNP_Create_Pipe_Event"
0x180013ae4  xor     ecx, ecx; lpEventAttributes
0x180013ae6  lea     edx, [r8+1]; bManualReset
0x180013aea  call    cs:__imp_CreateEventW
0x180013af0  mov     rdi, rax
0x180013af3  test    rax, rax
0x180013af6  jnz     short loc_180013B5D
0x180013af8  call    cs:__imp_GetLastError
0x180013afe  cmp     eax, 0B7h
0x180013b03  jnz     short loc_180013B21
0x180013b05  lea     r8, aGlobalPnpCreat; "Global\\PNP_Create_Pipe_Event"
0x180013b0c  xor     edx, edx; bInheritHandle
0x180013b0e  mov     ecx, 100000h; dwDesiredAccess
0x180013b13  call    cs:__imp_OpenEventW
0x180013b19  mov     rdi, rax
0x180013b1c  test    rax, rax
0x180013b1f  jnz     short loc_180013B5D
0x180013b21  call    cs:__imp_GetLastError
0x180013b27  mov     ebx, eax
0x180013b29  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b30  lea     rax, WPP_GLOBAL_Control
0x180013b37  cmp     rcx, rax
0x180013b3a  jz      short loc_180013B78
0x180013b3c  test    byte ptr [rcx+1Ch], 1
0x180013b40  jz      short loc_180013B78
0x180013b42  mov     rcx, [rcx+10h]
0x180013b46  lea     r9, aGlobalPnpCreat; "Global\\PNP_Create_Pipe_Event"
0x180013b4d  mov     edx, 37h ; '7'
0x180013b52  mov     [rsp+38h+var_18], ebx
0x180013b56  call    WPP_SF_Sd
0x180013b5b  jmp     short loc_180013B78
0x180013b5d  xor     ebx, ebx
0x180013b5f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180013b62  mov     rcx, rdi; hHandle
0x180013b65  lea     r8d, [rbx+1]; bAlertable
0x180013b69  call    cs:__imp_WaitForSingleObjectEx
0x180013b6f  mov     rcx, rdi; hObject
0x180013b72  call    cs:__imp_CloseHandle
0x180013b78  mov     eax, ebx
0x180013b7a  mov     rbx, [rsp+38h+arg_0]
0x180013b7f  add     rsp, 30h
0x180013b83  pop     rdi
0x180013b84  retn
```
