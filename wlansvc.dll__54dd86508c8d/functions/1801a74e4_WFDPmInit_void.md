# WFDPmInit(void)

- ea: `0x1801a74e4`
- end: `0x1801a7667`
- name: `?WFDPmInit@@YAKXZ`
- size: `387`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800bce9c`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x1801a74e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801a7622`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801a7622`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801a7601`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801a7601`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801a75ea`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801a75ea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801a74fa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801a7546`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801a74fa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801a7546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a750c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a7558`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a750c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a7558`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a75ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a75c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a75ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a75c1`

## pseudocode

```c
__int64 WFDPmInit(void)
{
  DWORD LastError; // ebx
  _QWORD *v1; // rcx
  __int64 v2; // rdx

  qword_1802A2818 = CreateEventW(0, 1, 0, 0);
  if ( !qword_1802A2818 )
  {
    LastError = GetLastError();
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      v2 = 42;
LABEL_11:
      WPP_SF_d(v1[12], v2, WPP_31e54d649409365576704d3c1f2892b5_Traceguids, LastError);
      goto LABEL_12;
    }
    goto LABEL_12;
  }
  qword_1802A2810 = CreateEventW(0, 1, 0, 0);
  if ( !qword_1802A2810 )
  {
    LastError = GetLastError();
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      v2 = 43;
      goto LABEL_11;
    }
LABEL_12:
    if ( LastError )
    {
      if ( qword_1802A2818 )
        CloseHandle(qword_1802A2818);
      if ( qword_1802A2810 )
        CloseHandle(qword_1802A2810);
    }
    return LastError;
  }
  LastError = 0;
  qword_1802A2808 = (__int64)&qword_1802A2800;
  qword_1802A2800 = (__int64)&qword_1802A2800;
  InitializeCriticalSection(&stru_1802A27D8);
  dword_1802A27D0 = 1;
  EnterCriticalSection(&stru_1802A27D8);
  qword_1802A2808 = (__int64)&qword_1802A2800;
  qword_1802A2800 = (__int64)&qword_1802A2800;
  dword_1802A2820 = 0;
  LeaveCriticalSection(&stru_1802A27D8);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 44, WPP_31e54d649409365576704d3c1f2892b5_Traceguids);
  }
  return LastError;
}

```

## disassembly

```asm
0x1801a74e4  mov     [rsp+arg_0], rbx
0x1801a74e9  push    rsi
0x1801a74ea  sub     rsp, 20h
0x1801a74ee  xor     r9d, r9d; lpName
0x1801a74f1  xor     r8d, r8d; bInitialState
0x1801a74f4  xor     ecx, ecx; lpEventAttributes
0x1801a74f6  lea     edx, [r9+1]; bManualReset
0x1801a74fa  call    cs:__imp_CreateEventW
0x1801a7500  mov     cs:qword_1802A2818, rax
0x1801a7507  test    rax, rax
0x1801a750a  jnz     short loc_1801A753A
0x1801a750c  call    cs:__imp_GetLastError
0x1801a7512  mov     ebx, eax
0x1801a7514  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a751b  lea     rax, WPP_GLOBAL_Control
0x1801a7522  cmp     rcx, rax
0x1801a7525  jz      short loc_1801A7597
0x1801a7527  cmp     byte ptr [rcx+69h], 1
0x1801a752b  jb      short loc_1801A7597
0x1801a752d  test    byte ptr [rcx+6Ch], 1
0x1801a7531  jz      short loc_1801A7597
0x1801a7533  mov     edx, 2Ah ; '*'
0x1801a7538  jmp     short loc_1801A7584
0x1801a753a  xor     r9d, r9d; lpName
0x1801a753d  xor     r8d, r8d; bInitialState
0x1801a7540  xor     ecx, ecx; lpEventAttributes
0x1801a7542  lea     edx, [r9+1]; bManualReset
0x1801a7546  call    cs:__imp_CreateEventW
0x1801a754c  mov     cs:qword_1802A2810, rax
0x1801a7553  test    rax, rax
0x1801a7556  jnz     short loc_1801A75CC
0x1801a7558  call    cs:__imp_GetLastError
0x1801a755e  mov     ebx, eax
0x1801a7560  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a7567  lea     rax, WPP_GLOBAL_Control
0x1801a756e  cmp     rcx, rax
0x1801a7571  jz      short loc_1801A7597
0x1801a7573  cmp     byte ptr [rcx+69h], 1
0x1801a7577  jb      short loc_1801A7597
0x1801a7579  test    byte ptr [rcx+6Ch], 1
0x1801a757d  jz      short loc_1801A7597
0x1801a757f  mov     edx, 2Bh ; '+'
0x1801a7584  mov     rcx, [rcx+60h]
0x1801a7588  lea     r8, WPP_31e54d649409365576704d3c1f2892b5_Traceguids
0x1801a758f  mov     r9d, ebx
0x1801a7592  call    WPP_SF_d
0x1801a7597  test    ebx, ebx
0x1801a7599  jz      loc_1801A765A
0x1801a759f  mov     rcx, cs:qword_1802A2818; hObject
0x1801a75a6  test    rcx, rcx
0x1801a75a9  jz      short loc_1801A75B1
0x1801a75ab  call    cs:__imp_CloseHandle
0x1801a75b1  mov     rcx, cs:qword_1802A2810; hObject
0x1801a75b8  test    rcx, rcx
0x1801a75bb  jz      loc_1801A765A
0x1801a75c1  call    cs:__imp_CloseHandle
0x1801a75c7  jmp     loc_1801A765A
0x1801a75cc  lea     rsi, qword_1802A2800
0x1801a75d3  xor     ebx, ebx
0x1801a75d5  lea     rcx, stru_1802A27D8; lpCriticalSection
0x1801a75dc  mov     cs:qword_1802A2808, rsi
0x1801a75e3  mov     cs:qword_1802A2800, rsi
0x1801a75ea  call    cs:__imp_InitializeCriticalSection
0x1801a75f0  lea     rcx, stru_1802A27D8; lpCriticalSection
0x1801a75f7  mov     cs:dword_1802A27D0, 1
0x1801a7601  call    cs:__imp_EnterCriticalSection
0x1801a7607  lea     rcx, stru_1802A27D8; lpCriticalSection
0x1801a760e  mov     cs:qword_1802A2808, rsi
0x1801a7615  mov     cs:qword_1802A2800, rsi
0x1801a761c  mov     cs:dword_1802A2820, ebx
0x1801a7622  call    cs:__imp_LeaveCriticalSection
0x1801a7628  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a762f  lea     rax, WPP_GLOBAL_Control
0x1801a7636  cmp     rcx, rax
0x1801a7639  jz      short loc_1801A765A
0x1801a763b  cmp     byte ptr [rcx+69h], 3
0x1801a763f  jb      short loc_1801A765A
0x1801a7641  test    byte ptr [rcx+6Ch], 1
0x1801a7645  jz      short loc_1801A765A
0x1801a7647  mov     rcx, [rcx+60h]
0x1801a764b  lea     edx, [rbx+2Ch]
0x1801a764e  lea     r8, WPP_31e54d649409365576704d3c1f2892b5_Traceguids
0x1801a7655  call    WPP_SF_
0x1801a765a  mov     eax, ebx
0x1801a765c  mov     rbx, [rsp+28h+arg_0]
0x1801a7661  add     rsp, 20h
0x1801a7665  pop     rsi
0x1801a7666  retn
```
