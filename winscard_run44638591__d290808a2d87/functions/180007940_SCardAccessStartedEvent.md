# SCardAccessStartedEvent

- ea: `0x180007940`
- end: `0x180007bad`
- name: `SCardAccessStartedEvent`
- size: `621`
- prototype: `HANDLE __stdcall()`
- caller_count: `23`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18000534c`
- `0x1800054a4`
- `0x180005898`
- `0x180008f70`
- `0x18000d554`
- `0x18000dab0`
- `0x180010298`
- `0x1800107a8`
- `0x180010e74`
- `0x180011244`
- `0x1800151b0`
- `0x180015280`
- `0x180015468`
- `0x1800157d8`
- `0x180016788`
- `0x1800193b8`
- `0x18001a5c4`
- `0x18001a6b4`
- `0x18002e430`
- `0x18002e514`
- `0x18002e5e8`
- `0x18002e718`
- `0x18002e808`

## callees

- `0x18000605c`
- `0x1800062f0`
- `0x180006400`
- `0x180006c80`
- `0x180007940`
- `0x180007bc0`
- `0x180008d20`
- `0x180014900`
- `0x18001991c`
- `0x1800239b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180007a1a`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180007a1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800079d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007a10`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800079d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007a10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800079f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007a23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800079f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007a23`

## pseudocode

```c
HANDLE __stdcall SCardAccessStartedEvent()
{
  __int64 v0; // rcx
  PVOID v1; // rcx
  LPCRITICAL_SECTION v2; // rbx
  __int64 v3; // rcx
  char v4; // r14
  char v5; // bp
  LPCRITICAL_SECTION v6; // rdi
  char v7; // si
  void *v8; // rbx
  int v10; // r9d
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp+8h] BYREF

  lpCriticalSection = 0;
  WppTraceIndent(v0, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids);
  }
  if ( (unsigned int)RedirectionContextLookup(&lpCriticalSection) )
    goto LABEL_21;
  v2 = lpCriticalSection;
  if ( (unsigned int)RegisterForSessionChangeNotifications(lpCriticalSection) )
  {
    v4 = 1;
  }
  else
  {
    v4 = 0;
    WppTraceIndent(v3, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids);
    }
  }
  UpdateConnectionStateForContext(v2);
  v5 = 0;
  lpCriticalSection = v2;
  v6 = v2;
  if ( !v2 )
  {
    if ( (unsigned int)RedirectionContextLookup(&lpCriticalSection) )
      goto LABEL_13;
    v6 = lpCriticalSection;
    v5 = 1;
  }
  EnterCriticalSection(v6);
  if ( !v6[3].DebugInfo )
    UpdateConnectionStateForContext(v6);
  v7 = BYTE2(v6[1].DebugInfo);
  LeaveCriticalSection(v6);
  if ( v5 )
    RedirectionContextRelease((struct _REDIRECTION_CONTEXT *)v6);
  if ( v7 )
  {
    EnterCriticalSection(v2);
    ResetEvent(v2[1].OwningThread);
    LeaveCriticalSection(v2);
  }
LABEL_13:
  if ( !(unsigned int)SetStartedEventWhenSCardSubsytemIsStarted((struct _REDIRECTION_CONTEXT *)v2) )
  {
    WppTraceIndent((__int64)v1, 2);
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids);
    }
    if ( v4 )
      UnRegisterForSessionChangeNotifications(v2);
LABEL_21:
    v8 = 0;
    goto LABEL_15;
  }
  v8 = *(void **)&v2[3].LockCount;
LABEL_15:
  WppTraceIndent((__int64)v1, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v10 = 0;
    if ( v8 )
      v10 = (int)v8;
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      65,
      (unsigned int)&WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids,
      v10,
      v10);
  }
  return v8;
}

```

## disassembly

```asm
0x180007940  sub     rsp, 48h
0x180007944  xor     edx, edx
0x180007946  mov     [rsp+48h+var_18], r15
0x18000794b  mov     [rsp+48h+lpCriticalSection], 0
0x180007954  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180007959  mov     rcx, cs:WPP_GLOBAL_Control
0x180007960  lea     r15, WPP_GLOBAL_Control
0x180007967  cmp     rcx, r15
0x18000796a  jz      short loc_180007976
0x18000796c  test    byte ptr [rcx+1Ch], 2
0x180007970  jnz     loc_180007AA4
0x180007976  mov     [rsp+48h+arg_8], rbx
0x18000797b  lea     rcx, [rsp+48h+lpCriticalSection]; struct _REDIRECTION_CONTEXT **
0x180007980  mov     [rsp+48h+var_10], r14
0x180007985  call    ?RedirectionContextLookup@@YAKPEAPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextLookup(_REDIRECTION_CONTEXT * *)
0x18000798a  test    eax, eax
0x18000798c  jnz     loc_180007AA0
0x180007992  mov     rbx, [rsp+48h+lpCriticalSection]
0x180007997  mov     rcx, rbx; lpCriticalSection
0x18000799a  mov     [rsp+48h+arg_10], rbp
0x18000799f  mov     [rsp+48h+var_8], rdi
0x1800079a4  call    ?RegisterForSessionChangeNotifications@@YAHPEAU_REDIRECTION_CONTEXT@@@Z; RegisterForSessionChangeNotifications(_REDIRECTION_CONTEXT *)
0x1800079a9  test    eax, eax
0x1800079ab  jz      loc_180007AC8
0x1800079b1  mov     r14b, 1
0x1800079b4  mov     rcx, rbx; lpCriticalSection
0x1800079b7  call    ?UpdateConnectionStateForContext@@YAXPEAU_REDIRECTION_CONTEXT@@@Z; UpdateConnectionStateForContext(_REDIRECTION_CONTEXT *)
0x1800079bc  xor     bpl, bpl
0x1800079bf  mov     [rsp+48h+lpCriticalSection], rbx
0x1800079c4  mov     rdi, rbx
0x1800079c7  test    rbx, rbx
0x1800079ca  jz      loc_180007B13
0x1800079d0  mov     rcx, rdi; lpCriticalSection
0x1800079d3  mov     [rsp+48h+arg_18], rsi
0x1800079d8  call    cs:__imp_EnterCriticalSection
0x1800079de  cmp     qword ptr [rdi+78h], 0
0x1800079e3  jnz     short loc_1800079ED
0x1800079e5  mov     rcx, rdi; lpCriticalSection
0x1800079e8  call    ?UpdateConnectionStateForContext@@YAXPEAU_REDIRECTION_CONTEXT@@@Z; UpdateConnectionStateForContext(_REDIRECTION_CONTEXT *)
0x1800079ed  movzx   esi, byte ptr [rdi+2Ah]
0x1800079f1  mov     rcx, rdi; lpCriticalSection
0x1800079f4  call    cs:__imp_LeaveCriticalSection
0x1800079fa  test    bpl, bpl
0x1800079fd  jnz     loc_180007B32
0x180007a03  test    sil, sil
0x180007a06  mov     rsi, [rsp+48h+arg_18]
0x180007a0b  jz      short loc_180007A29
0x180007a0d  mov     rcx, rbx; lpCriticalSection
0x180007a10  call    cs:__imp_EnterCriticalSection
0x180007a16  mov     rcx, [rbx+38h]; hEvent
0x180007a1a  call    cs:__imp_ResetEvent
0x180007a20  mov     rcx, rbx; lpCriticalSection
0x180007a23  call    cs:__imp_LeaveCriticalSection
0x180007a29  mov     rcx, rbx; struct _REDIRECTION_CONTEXT *
0x180007a2c  call    ?SetStartedEventWhenSCardSubsytemIsStarted@@YAHPEAU_REDIRECTION_CONTEXT@@@Z; SetStartedEventWhenSCardSubsytemIsStarted(_REDIRECTION_CONTEXT *)
0x180007a31  mov     rdi, [rsp+48h+var_8]
0x180007a36  mov     rbp, [rsp+48h+arg_10]
0x180007a3b  test    eax, eax
0x180007a3d  jz      short loc_180007A7D
0x180007a3f  mov     rbx, [rbx+80h]
0x180007a46  mov     edx, 1
0x180007a4b  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180007a50  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a57  mov     r14, [rsp+48h+var_10]
0x180007a5c  cmp     rcx, r15
0x180007a5f  mov     r15, [rsp+48h+var_18]
0x180007a64  jz      short loc_180007A70
0x180007a66  test    byte ptr [rcx+1Ch], 2
0x180007a6a  jnz     loc_180007B7A
0x180007a70  mov     rax, rbx
0x180007a73  mov     rbx, [rsp+48h+arg_8]
0x180007a78  add     rsp, 48h
0x180007a7c  retn
0x180007a7d  mov     edx, 2
0x180007a82  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180007a87  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a8e  cmp     rcx, r15
0x180007a91  jnz     loc_180007B3F
0x180007a97  test    r14b, r14b
0x180007a9a  jnz     loc_180007B6D
0x180007aa0  xor     ebx, ebx
0x180007aa2  jmp     short loc_180007A46
0x180007aa4  cmp     byte ptr [rcx+19h], 5
0x180007aa8  jb      loc_180007976
0x180007aae  mov     rcx, [rcx+10h]
0x180007ab2  lea     r8, WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids
0x180007ab9  mov     edx, 3Eh ; '>'
0x180007abe  call    WPP_SF_s
0x180007ac3  jmp     loc_180007976
0x180007ac8  xor     r14b, r14b
0x180007acb  mov     edx, 2
0x180007ad0  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180007ad5  mov     rcx, cs:WPP_GLOBAL_Control
0x180007adc  cmp     rcx, r15
0x180007adf  jz      loc_1800079B4
0x180007ae5  test    byte ptr [rcx+1Ch], 1
0x180007ae9  jz      loc_1800079B4
0x180007aef  cmp     byte ptr [rcx+19h], 2
0x180007af3  jb      loc_1800079B4
0x180007af9  mov     rcx, [rcx+10h]
0x180007afd  lea     r8, WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids
0x180007b04  mov     edx, 3Fh ; '?'
0x180007b09  call    WPP_SF_s
0x180007b0e  jmp     loc_1800079B4
0x180007b13  lea     rcx, [rsp+48h+lpCriticalSection]; struct _REDIRECTION_CONTEXT **
0x180007b18  call    ?RedirectionContextLookup@@YAKPEAPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextLookup(_REDIRECTION_CONTEXT * *)
0x180007b1d  test    eax, eax
0x180007b1f  jnz     loc_180007A29
0x180007b25  mov     rdi, [rsp+48h+lpCriticalSection]
0x180007b2a  mov     bpl, 1
0x180007b2d  jmp     loc_1800079D0
0x180007b32  mov     rcx, rdi; struct _REDIRECTION_CONTEXT *
0x180007b35  call    ?RedirectionContextRelease@@YAKPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextRelease(_REDIRECTION_CONTEXT *)
0x180007b3a  jmp     loc_180007A03
0x180007b3f  test    byte ptr [rcx+1Ch], 1
0x180007b43  jz      loc_180007A97
0x180007b49  cmp     byte ptr [rcx+19h], 2
0x180007b4d  jb      loc_180007A97
0x180007b53  mov     rcx, [rcx+10h]
0x180007b57  lea     r8, WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids
0x180007b5e  mov     edx, 40h ; '@'
0x180007b63  call    WPP_SF_s
0x180007b68  jmp     loc_180007A97
0x180007b6d  mov     rcx, rbx; lpCriticalSection
0x180007b70  call    ?UnRegisterForSessionChangeNotifications@@YAHPEAU_REDIRECTION_CONTEXT@@@Z; UnRegisterForSessionChangeNotifications(_REDIRECTION_CONTEXT *)
0x180007b75  jmp     loc_180007AA0
0x180007b7a  cmp     byte ptr [rcx+19h], 5
0x180007b7e  jb      loc_180007A70
0x180007b84  mov     rcx, [rcx+10h]
0x180007b88  lea     r8, WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids
0x180007b8f  xor     r9d, r9d
0x180007b92  mov     edx, 41h ; 'A'
0x180007b97  test    rbx, rbx
0x180007b9a  cmovnz  r9d, ebx
0x180007b9e  mov     [rsp+48h+var_28], r9d
0x180007ba3  call    WPP_SF_sd
0x180007ba8  jmp     loc_180007A70
```
