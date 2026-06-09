# SignalSetupEvent

- ea: `0x1800133a0`
- end: `0x180013491`
- name: `SignalSetupEvent`
- size: `241`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180011890`

## callees

- `0x1800133a0`
- `0x1800135f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800133e3`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800133e3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013432`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013432`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800133ba`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800133ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800133c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800133f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001343c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800133c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800133f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001343c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001347e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001347e`

## string_xrefs

- `0x1800133ad`: `Global\PNP_Create_Pipe_Event`
- `0x1800133d5`: `Global\PNP_Create_Pipe_Event`
- `0x180013416`: `Global\PNP_Create_Pipe_Event`
- `0x180013461`: `Global\PNP_Create_Pipe_Event`

## pseudocode

```c
__int64 SignalSetupEvent()
{
  HANDLE EventW; // rbx
  DWORD LastError; // edi
  int v2; // r8d
  int v3; // r8d

  EventW = CreateEventW(0, 1, 0, L"Global\\PNP_Create_Pipe_Event");
  if ( EventW || GetLastError() == 183 && (EventW = OpenEventW(0x100000u, 0, L"Global\\PNP_Create_Pipe_Event")) != 0 )
  {
    LastError = 0;
    if ( SetEvent(EventW) )
      goto LABEL_12;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, v3, (unsigned int)L"Global\\PNP_Create_Pipe_Event", LastError);
    if ( EventW )
LABEL_12:
      CloseHandle(EventW);
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, v2, (unsigned int)L"Global\\PNP_Create_Pipe_Event", LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800133a0  mov     [rsp+arg_0], rbx
0x1800133a5  push    rdi
0x1800133a6  sub     rsp, 30h
0x1800133aa  xor     r8d, r8d; bInitialState
0x1800133ad  lea     r9, aGlobalPnpCreat; "Global\\PNP_Create_Pipe_Event"
0x1800133b4  xor     ecx, ecx; lpEventAttributes
0x1800133b6  lea     edx, [r8+1]; bManualReset
0x1800133ba  call    cs:__imp_CreateEventW
0x1800133c0  mov     rbx, rax
0x1800133c3  test    rax, rax
0x1800133c6  jnz     short loc_18001342D
0x1800133c8  call    cs:__imp_GetLastError
0x1800133ce  cmp     eax, 0B7h
0x1800133d3  jnz     short loc_1800133F1
0x1800133d5  lea     r8, aGlobalPnpCreat; "Global\\PNP_Create_Pipe_Event"
0x1800133dc  xor     edx, edx; bInheritHandle
0x1800133de  mov     ecx, 100000h; dwDesiredAccess
0x1800133e3  call    cs:__imp_OpenEventW
0x1800133e9  mov     rbx, rax
0x1800133ec  test    rax, rax
0x1800133ef  jnz     short loc_18001342D
0x1800133f1  call    cs:__imp_GetLastError
0x1800133f7  mov     edi, eax
0x1800133f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180013400  lea     rax, WPP_GLOBAL_Control
0x180013407  cmp     rcx, rax
0x18001340a  jz      short loc_180013484
0x18001340c  test    byte ptr [rcx+1Ch], 1
0x180013410  jz      short loc_180013484
0x180013412  mov     rcx, [rcx+10h]
0x180013416  lea     r9, aGlobalPnpCreat; "Global\\PNP_Create_Pipe_Event"
0x18001341d  mov     edx, 38h ; '8'
0x180013422  mov     [rsp+38h+var_18], edi
0x180013426  call    WPP_SF_Sd
0x18001342b  jmp     short loc_180013484
0x18001342d  mov     rcx, rbx; hEvent
0x180013430  xor     edi, edi
0x180013432  call    cs:__imp_SetEvent
0x180013438  test    eax, eax
0x18001343a  jnz     short loc_18001347B
0x18001343c  call    cs:__imp_GetLastError
0x180013442  mov     edi, eax
0x180013444  mov     rcx, cs:WPP_GLOBAL_Control
0x18001344b  lea     rax, WPP_GLOBAL_Control
0x180013452  cmp     rcx, rax
0x180013455  jz      short loc_180013476
0x180013457  test    byte ptr [rcx+1Ch], 1
0x18001345b  jz      short loc_180013476
0x18001345d  mov     rcx, [rcx+10h]
0x180013461  lea     r9, aGlobalPnpCreat; "Global\\PNP_Create_Pipe_Event"
0x180013468  mov     edx, 39h ; '9'
0x18001346d  mov     [rsp+38h+var_18], edi
0x180013471  call    WPP_SF_Sd
0x180013476  test    rbx, rbx
0x180013479  jz      short loc_180013484
0x18001347b  mov     rcx, rbx; hObject
0x18001347e  call    cs:__imp_CloseHandle
0x180013484  mov     rbx, [rsp+38h+arg_0]
0x180013489  mov     eax, edi
0x18001348b  add     rsp, 30h
0x18001348f  pop     rdi
0x180013490  retn
```
