# MediaSenseRegister(void)

- ea: `0x180009c38`
- end: `0x180009cbc`
- name: `?MediaSenseRegister@@YAHXZ`
- size: `132`
- prototype: `BOOL(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007dd0`

## callees

- `0x180008300`
- `0x180009c38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c90`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180009c67`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180009c67`

## pseudocode

```c
BOOL MediaSenseRegister(void)
{
  BOOL result; // eax
  DWORD LastError; // eax

  result = CreateTimerQueueTimer(&ghMediaTimer, 0, MediaSenseRegisterHelper, 0, 0x124F8u, 0, 0x10u);
  if ( !result )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_c7cc13fe6dc03834cd55671891cfefc7_Traceguids, LastError);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180009c38  sub     rsp, 48h
0x180009c3c  mov     [rsp+48h+Flags], 10h; Flags
0x180009c44  lea     r8, ?MediaSenseRegisterHelper@@YAXPEAXE@Z; Callback
0x180009c4b  mov     [rsp+48h+Period], 0; Period
0x180009c53  lea     rcx, ?ghMediaTimer@@3PEAXEA; phNewTimer
0x180009c5a  xor     r9d, r9d; Parameter
0x180009c5d  mov     [rsp+48h+DueTime], 124F8h; DueTime
0x180009c65  xor     edx, edx; TimerQueue
0x180009c67  call    cs:__imp_CreateTimerQueueTimer
0x180009c6d  test    eax, eax
0x180009c6f  jnz     short loc_180009CB7
0x180009c71  mov     rax, cs:WPP_GLOBAL_Control
0x180009c78  lea     rcx, WPP_GLOBAL_Control
0x180009c7f  cmp     rax, rcx
0x180009c82  jz      short loc_180009CB5
0x180009c84  test    byte ptr [rax+1Ch], 1
0x180009c88  jz      short loc_180009CB5
0x180009c8a  cmp     byte ptr [rax+19h], 2
0x180009c8e  jb      short loc_180009CB5
0x180009c90  call    cs:__imp_GetLastError
0x180009c96  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c9d  lea     r8, WPP_c7cc13fe6dc03834cd55671891cfefc7_Traceguids
0x180009ca4  mov     edx, 19h
0x180009ca9  mov     r9d, eax
0x180009cac  mov     rcx, [rcx+10h]
0x180009cb0  call    WPP_SF_d
0x180009cb5  xor     eax, eax
0x180009cb7  add     rsp, 48h
0x180009cbb  retn
```
