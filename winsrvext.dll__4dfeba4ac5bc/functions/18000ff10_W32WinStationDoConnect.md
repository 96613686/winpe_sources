# W32WinStationDoConnect

- ea: `0x18000ff10`
- end: `0x180010210`
- name: `W32WinStationDoConnect`
- size: `768`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e290`
- `0x18000e4ec`
- `0x18000e6b4`
- `0x18000e928`
- `0x18000f37c`
- `0x18000fa90`
- `0x18000ff10`
- `0x1800138c5`
- `0x1800138f0`

## import_xrefs

- `ntdll!NtDuplicateObject` at `0x180010045`
- `ntdll!NtDuplicateObject` at `0x18001007f`
- `ntdll!NtDuplicateObject` at `0x180010045`
- `ntdll!NtDuplicateObject` at `0x18001007f`
- `ntdll!NtClose` at `0x180010098`
- `ntdll!NtClose` at `0x180010098`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800101aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800101aa`
- `CSRSRV!CsrConnectToUser` at `0x180010173`
- `CSRSRV!CsrConnectToUser` at `0x180010173`
- `win32u!NtUserRemoteReconnect` at `0x1800100f7`
- `win32u!NtUserRemoteReconnect` at `0x1800100f7`
- `win32u!NtUserRemoteConnect` at `0x180010117`
- `win32u!NtUserRemoteConnect` at `0x180010117`
- `USER32!CtxInitUser32` at `0x18001018b`
- `USER32!CtxInitUser32` at `0x18001018b`
- `USER32!SystemParametersInfoW` at `0x18000ffec`
- `USER32!SystemParametersInfoW` at `0x18001000d`
- `USER32!SystemParametersInfoW` at `0x18000ffec`
- `USER32!SystemParametersInfoW` at `0x18001000d`

## pseudocode

```c
__int64 __fastcall W32WinStationDoConnect(__int64 a1)
{
  __int64 v2; // rdi
  int fixed; // ebx
  void *v4; // rsi
  int v5; // eax
  int v6; // eax
  char v8[320]; // [rsp+40h] [rbp-178h] BYREF
  _BYTE v9[24]; // [rsp+180h] [rbp-38h] BYREF

  v2 = a1 + 56;
  memset_0(v8, 0, sizeof(v8));
  gRelatedActivityId = *(_OWORD *)(a1 + 1164);
  fixed = FixDoConnectHandles(v2);
  if ( fixed < 0 )
    return (unsigned int)fixed;
  if ( *(_BYTE *)v2 )
  {
    G_ConsoleShadowVideoChannel = *(HANDLE *)(v2 + 8);
    G_ConsoleShadowMouseChannel = *(HANDLE *)(v2 + 16);
    G_ConsoleShadowKeyboardChannel = *(HANDLE *)(v2 + 24);
    G_ConsoleShadowBeepChannel = *(HANDLE *)(v2 + 32);
    G_ConsoleShadowCommandChannel = *(HANDLE *)(v2 + 40);
    G_ConsoleShadowThinwireChannel = *(HANDLE *)(v2 + 48);
    G_fCursorShadow = 0;
    SystemParametersInfoW(0x101Au, 0, &G_fCursorShadow, 0);
    if ( G_fCursorShadow )
      SystemParametersInfoW(0x101Bu, 0, 0, 0);
    v4 = *(void **)(v2 + 56);
    fixed = NtDuplicateObject(
              (HANDLE)0xFFFFFFFFFFFFFFFFLL,
              G_ConsoleShadowVideoChannel,
              (HANDLE)0xFFFFFFFFFFFFFFFFLL,
              &G_DupConsoleShadowVideoChannel,
              0,
              0,
              2u);
    if ( fixed < 0 )
      return (unsigned int)fixed;
    fixed = NtDuplicateObject(
              (HANDLE)0xFFFFFFFFFFFFFFFFLL,
              G_ConsoleShadowCommandChannel,
              (HANDLE)0xFFFFFFFFFFFFFFFFLL,
              &G_DupConsoleShadowCommandChannel,
              0,
              0,
              2u);
    if ( fixed < 0 )
    {
      NtClose(G_DupConsoleShadowVideoChannel);
      G_DupConsoleShadowVideoChannel = 0;
      return (unsigned int)fixed;
    }
    v5 = 1;
  }
  else
  {
    fixed = CaptureDoConnectMsg(v2);
    if ( fixed < 0 )
      return (unsigned int)fixed;
    v4 = 0;
    v5 = 0;
  }
  G_fConsoleShadow = v5;
  StringCopyNoNull(v9, 20, v2 + 134, 18);
  CreateDoConnectMsgForWin32(v8, (unsigned __int8 *)v2);
  if ( !g_bInitialConnected || *(_BYTE *)v2 )
    v6 = NtUserRemoteConnect(v8, 10, v9);
  else
    v6 = NtUserRemoteReconnect(v8);
  fixed = v6;
  if ( !v6 )
  {
    if ( !*(_DWORD *)(v2 + 1104) || *(_DWORD *)(v2 + 1124) || (fixed = CreateRemoteDisplayDeviceNode(v2), fixed >= 0) )
    {
      if ( !G_DupIcaCommandChannel || (fixed = CreateCommandChannelThread(v2)) == 0 )
      {
        if ( *(_BYTE *)v2 )
        {
          CloseHandle(v4);
        }
        else if ( !g_bInitialConnected )
        {
          if ( !CsrConnectToUser() || !(unsigned int)CtxInitUser32() )
            return (unsigned int)-1073741801;
          g_bInitialConnected = 1;
        }
        if ( !*(_BYTE *)v2 )
        {
          gHRes = *(_WORD *)(v2 + 188);
          gVRes = *(_WORD *)(v2 + 190);
          gColorDepth = *(_WORD *)(v2 + 192);
        }
      }
    }
  }
  return (unsigned int)fixed;
}

```

## disassembly

```asm
0x18000ff10  mov     [rsp+arg_8], rbx
0x18000ff15  mov     [rsp+arg_10], rbp
0x18000ff1a  push    rsi
0x18000ff1b  push    rdi
0x18000ff1c  push    r14
0x18000ff1e  sub     rsp, 1A0h
0x18000ff25  mov     rax, cs:__security_cookie
0x18000ff2c  xor     rax, rsp
0x18000ff2f  mov     [rsp+1B8h+var_20], rax
0x18000ff37  mov     rbx, rcx
0x18000ff3a  lea     rdi, [rcx+38h]
0x18000ff3e  lea     rcx, [rsp+1B8h+var_178]; void *
0x18000ff43  xor     edx, edx; Val
0x18000ff45  mov     r8d, 140h; Size
0x18000ff4b  call    memset_0
0x18000ff50  movups  xmm0, xmmword ptr [rbx+48Ch]
0x18000ff57  mov     rcx, rdi
0x18000ff5a  movdqu  cs:gRelatedActivityId, xmm0
0x18000ff62  call    FixDoConnectHandles
0x18000ff67  xor     ebp, ebp
0x18000ff69  mov     ebx, eax
0x18000ff6b  test    eax, eax
0x18000ff6d  js      loc_1800101E5
0x18000ff73  cmp     [rdi], bpl
0x18000ff76  jnz     short loc_18000FF93
0x18000ff78  mov     rcx, rdi
0x18000ff7b  call    CaptureDoConnectMsg
0x18000ff80  mov     ebx, eax
0x18000ff82  test    eax, eax
0x18000ff84  js      loc_1800101E5
0x18000ff8a  mov     esi, ebp
0x18000ff8c  mov     eax, ebp
0x18000ff8e  jmp     loc_1800100B5
0x18000ff93  mov     rax, [rdi+8]
0x18000ff97  lea     r8, G_fCursorShadow; pvParam
0x18000ff9e  mov     cs:G_ConsoleShadowVideoChannel, rax
0x18000ffa5  xor     r9d, r9d; fWinIni
0x18000ffa8  mov     rax, [rdi+10h]
0x18000ffac  xor     edx, edx; uiParam
0x18000ffae  mov     cs:G_ConsoleShadowMouseChannel, rax
0x18000ffb5  mov     ecx, 101Ah; uiAction
0x18000ffba  mov     rax, [rdi+18h]
0x18000ffbe  mov     cs:G_ConsoleShadowKeyboardChannel, rax
0x18000ffc5  mov     rax, [rdi+20h]
0x18000ffc9  mov     cs:G_ConsoleShadowBeepChannel, rax
0x18000ffd0  mov     rax, [rdi+28h]
0x18000ffd4  mov     cs:G_ConsoleShadowCommandChannel, rax
0x18000ffdb  mov     rax, [rdi+30h]
0x18000ffdf  mov     cs:G_ConsoleShadowThinwireChannel, rax
0x18000ffe6  mov     cs:G_fCursorShadow, ebp
0x18000ffec  call    cs:__imp_SystemParametersInfoW
0x18000fff3  nop     dword ptr [rax+rax+00h]
0x18000fff8  cmp     cs:G_fCursorShadow, ebp
0x18000fffe  jz      short loc_180010019
0x180010000  xor     r9d, r9d; fWinIni
0x180010003  xor     r8d, r8d; pvParam
0x180010006  xor     edx, edx; uiParam
0x180010008  mov     ecx, 101Bh; uiAction
0x18001000d  call    cs:__imp_SystemParametersInfoW
0x180010014  nop     dword ptr [rax+rax+00h]
0x180010019  mov     rdx, cs:G_ConsoleShadowVideoChannel; SourceHandle
0x180010020  lea     r9, G_DupConsoleShadowVideoChannel; TargetHandle
0x180010027  mov     rsi, [rdi+38h]
0x18001002b  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001002f  mov     [rsp+1B8h+Options], 2; Options
0x180010037  mov     r8, r14; TargetProcessHandle
0x18001003a  mov     rcx, r14; SourceProcessHandle
0x18001003d  mov     [rsp+1B8h+HandleAttributes], ebp; HandleAttributes
0x180010041  mov     [rsp+1B8h+DesiredAccess], ebp; DesiredAccess
0x180010045  call    cs:__imp_NtDuplicateObject
0x18001004c  nop     dword ptr [rax+rax+00h]
0x180010051  mov     ebx, eax
0x180010053  test    eax, eax
0x180010055  js      loc_1800101E5
0x18001005b  mov     rdx, cs:G_ConsoleShadowCommandChannel; SourceHandle
0x180010062  lea     r9, G_DupConsoleShadowCommandChannel; TargetHandle
0x180010069  mov     [rsp+1B8h+Options], 2; Options
0x180010071  mov     r8, r14; TargetProcessHandle
0x180010074  mov     [rsp+1B8h+HandleAttributes], ebp; HandleAttributes
0x180010078  mov     rcx, r14; SourceProcessHandle
0x18001007b  mov     [rsp+1B8h+DesiredAccess], ebp; DesiredAccess
0x18001007f  call    cs:__imp_NtDuplicateObject
0x180010086  nop     dword ptr [rax+rax+00h]
0x18001008b  mov     ebx, eax
0x18001008d  test    eax, eax
0x18001008f  jns     short loc_1800100B0
0x180010091  mov     rcx, cs:G_DupConsoleShadowVideoChannel; Handle
0x180010098  call    cs:__imp_NtClose
0x18001009f  nop     dword ptr [rax+rax+00h]
0x1800100a4  mov     cs:G_DupConsoleShadowVideoChannel, rbp
0x1800100ab  jmp     loc_1800101E5
0x1800100b0  mov     eax, 1
0x1800100b5  mov     edx, 14h
0x1800100ba  mov     cs:G_fConsoleShadow, eax
0x1800100c0  lea     r8, [rdi+86h]
0x1800100c7  lea     rcx, [rsp+1B8h+var_38]
0x1800100cf  lea     r9d, [rdx-2]
0x1800100d3  call    StringCopyNoNull
0x1800100d8  mov     rdx, rdi
0x1800100db  lea     rcx, [rsp+1B8h+var_178]
0x1800100e0  call    CreateDoConnectMsgForWin32
0x1800100e5  cmp     cs:g_bInitialConnected, ebp
0x1800100eb  jz      short loc_180010105
0x1800100ed  cmp     [rdi], bpl
0x1800100f0  jnz     short loc_180010105
0x1800100f2  lea     rcx, [rsp+1B8h+var_178]
0x1800100f7  call    cs:__imp_NtUserRemoteReconnect
0x1800100fe  nop     dword ptr [rax+rax+00h]
0x180010103  jmp     short loc_180010123
0x180010105  lea     r8, [rsp+1B8h+var_38]
0x18001010d  mov     edx, 0Ah
0x180010112  lea     rcx, [rsp+1B8h+var_178]
0x180010117  call    cs:__imp_NtUserRemoteConnect
0x18001011e  nop     dword ptr [rax+rax+00h]
0x180010123  mov     ebx, eax
0x180010125  test    eax, eax
0x180010127  jnz     loc_1800101E5
0x18001012d  cmp     [rdi+450h], ebp
0x180010133  jz      short loc_18001014F
0x180010135  cmp     [rdi+464h], ebp
0x18001013b  jnz     short loc_18001014F
0x18001013d  mov     rcx, rdi
0x180010140  call    CreateRemoteDisplayDeviceNode
0x180010145  mov     ebx, eax
0x180010147  test    eax, eax
0x180010149  js      loc_1800101E5
0x18001014f  cmp     cs:G_DupIcaCommandChannel, rbp
0x180010156  jz      short loc_180010166
0x180010158  mov     rcx, rdi
0x18001015b  call    CreateCommandChannelThread
0x180010160  mov     ebx, eax
0x180010162  test    eax, eax
0x180010164  jnz     short loc_1800101E5
0x180010166  cmp     [rdi], bpl
0x180010169  jnz     short loc_1800101A7
0x18001016b  cmp     cs:g_bInitialConnected, ebp
0x180010171  jnz     short loc_1800101B6
0x180010173  call    cs:__imp_CsrConnectToUser
0x18001017a  nop     dword ptr [rax+rax+00h]
0x18001017f  test    rax, rax
0x180010182  jnz     short loc_18001018B
0x180010184  mov     ebx, 0C0000017h
0x180010189  jmp     short loc_1800101E5
0x18001018b  call    cs:__imp_CtxInitUser32
0x180010192  nop     dword ptr [rax+rax+00h]
0x180010197  test    eax, eax
0x180010199  jz      short loc_180010184
0x18001019b  mov     cs:g_bInitialConnected, 1
0x1800101a5  jmp     short loc_1800101B6
0x1800101a7  mov     rcx, rsi; hObject
0x1800101aa  call    cs:__imp_CloseHandle
0x1800101b1  nop     dword ptr [rax+rax+00h]
0x1800101b6  cmp     [rdi], bpl
0x1800101b9  jnz     short loc_1800101E5
0x1800101bb  movzx   eax, word ptr [rdi+0BCh]
0x1800101c2  mov     cs:gHRes, ax
0x1800101c9  movzx   eax, word ptr [rdi+0BEh]
0x1800101d0  mov     cs:gVRes, ax
0x1800101d7  movzx   eax, word ptr [rdi+0C0h]
0x1800101de  mov     cs:gColorDepth, ax
0x1800101e5  mov     eax, ebx
0x1800101e7  mov     rcx, [rsp+1B8h+var_20]
0x1800101ef  xor     rcx, rsp; StackCookie
0x1800101f2  call    __security_check_cookie
0x1800101f7  lea     r11, [rsp+1B8h+var_18]
0x1800101ff  mov     rbx, [r11+28h]
0x180010203  mov     rbp, [r11+30h]
0x180010207  mov     rsp, r11
0x18001020a  pop     r14
0x18001020c  pop     rdi
0x18001020d  pop     rsi
0x18001020e  retn
```
