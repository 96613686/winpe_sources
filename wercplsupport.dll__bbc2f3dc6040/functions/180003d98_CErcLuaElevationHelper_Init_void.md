# CErcLuaElevationHelper::Init(void)

- ea: `0x180003d98`
- end: `0x180003e45`
- name: `?Init@CErcLuaElevationHelper@@QEAAJXZ`
- size: `173`
- prototype: `__int64 __fastcall(CErcLuaElevationHelper *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002e70`

## callees

- `0x180003d98`
- `0x180006c9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003dbe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003dbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003de9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003de9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dd6`

## pseudocode

```c
__int64 __fastcall CErcLuaElevationHelper::Init(CErcLuaElevationHelper *this)
{
  HANDLE EventW; // rax
  void *v3; // rcx
  signed int LastError; // eax
  unsigned int v5; // ebx

  if ( *((_QWORD *)this + 5) != -1 && *((_QWORD *)this + 5) != 0 )
    return 0;
  EventW = CreateEventW(0, 1, 0, 0);
  v3 = (void *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = EventW;
  if ( (unsigned __int64)v3 + 1 > 1 )
    CloseHandle(v3);
  if ( *((_QWORD *)this + 5) == -1 || *((_QWORD *)this + 5) == 0 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( (v5 & 0x80000000) == 0 )
      v5 = -2147467259;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids, v5);
  }
  else
  {
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180003d98  push    rbx
0x180003d9a  sub     rsp, 20h
0x180003d9e  mov     rax, [rcx+28h]
0x180003da2  mov     rbx, rcx
0x180003da5  inc     rax
0x180003da8  cmp     rax, 1
0x180003dac  ja      loc_180003E3B
0x180003db2  xor     r9d, r9d; lpName
0x180003db5  xor     r8d, r8d; bInitialState
0x180003db8  xor     ecx, ecx; lpEventAttributes
0x180003dba  lea     edx, [r9+1]; bManualReset
0x180003dbe  call    cs:__imp_CreateEventW
0x180003dc4  mov     rcx, [rbx+28h]; hObject
0x180003dc8  mov     [rbx+28h], rax
0x180003dcc  lea     rax, [rcx+1]
0x180003dd0  cmp     rax, 1
0x180003dd4  jbe     short loc_180003DDC
0x180003dd6  call    cs:__imp_CloseHandle
0x180003ddc  mov     rax, [rbx+28h]
0x180003de0  inc     rax
0x180003de3  cmp     rax, 1
0x180003de7  ja      short loc_180003E3B
0x180003de9  call    cs:__imp_GetLastError
0x180003def  mov     ebx, eax
0x180003df1  test    eax, eax
0x180003df3  jle     short loc_180003DFE
0x180003df5  movzx   ebx, ax
0x180003df8  or      ebx, 80070000h
0x180003dfe  test    ebx, ebx
0x180003e00  mov     eax, 80004005h
0x180003e05  cmovns  ebx, eax
0x180003e08  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e0f  lea     rax, WPP_GLOBAL_Control
0x180003e16  cmp     rcx, rax
0x180003e19  jz      short loc_180003E3D
0x180003e1b  test    byte ptr [rcx+1Ch], 1
0x180003e1f  jz      short loc_180003E3D
0x180003e21  mov     rcx, [rcx+10h]
0x180003e25  lea     r8, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids
0x180003e2c  mov     edx, 31h ; '1'
0x180003e31  mov     r9d, ebx
0x180003e34  call    WPP_SF_d
0x180003e39  jmp     short loc_180003E3D
0x180003e3b  xor     ebx, ebx
0x180003e3d  mov     eax, ebx
0x180003e3f  add     rsp, 20h
0x180003e43  pop     rbx
0x180003e44  retn
```
