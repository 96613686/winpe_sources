# KsppEndCardCall

- ea: `0x18001594c`
- end: `0x180015a55`
- name: `KsppEndCardCall`
- size: `265`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `21`
- callee_count: `7`
- tags: ``

## callers

- `0x180013b68`
- `0x180015a5c`
- `0x180016624`
- `0x180016adc`
- `0x180017f6c`
- `0x180018968`
- `0x1800199b0`
- `0x18001a59c`
- `0x18001b6f8`
- `0x18001c818`
- `0x18001d4e0`
- `0x18001dbc8`
- `0x18001e590`
- `0x18001e92c`
- `0x180020ed4`
- `0x1800229fc`
- `0x180023dd0`
- `0x180024250`
- `0x1800253c0`
- `0x1800283dc`
- `0x180028a30`

## callees

- `0x18000a408`
- `0x180011fd8`
- `0x180013734`
- `0x18001594c`
- `0x18001c6ec`
- `0x18003afc0`
- `0x18003bb88`

## pseudocode

```c
__int64 __fastcall KsppEndCardCall(__int64 a1)
{
  __int64 v2; // rcx
  unsigned int started; // ebx
  int v4; // r8d
  int v5; // r9d
  __int64 v6; // rcx

  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids, WPP_pszIndent);
  }
  started = TransactionManagerStartTimer(*(struct _CARD_STATE **)(a1 + 16));
  if ( started )
  {
    WppTraceIndent(v2, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDl(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, v4, v5, started, *(_DWORD *)(*(_QWORD *)(a1 + 16) + 592LL));
    }
  }
  KspLeaveCriticalSection(*(_QWORD *)(a1 + 16) + 624LL);
  WppTraceIndent(v6, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      68,
      (unsigned int)&WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids,
      (_DWORD)WPP_pszIndent,
      started);
  }
  return started;
}

```

## disassembly

```asm
0x18001594c  mov     [rsp+arg_0], rbx
0x180015951  mov     [rsp+arg_8], rbp
0x180015956  push    rdi
0x180015957  sub     rsp, 30h
0x18001595b  xor     edx, edx
0x18001595d  mov     rdi, rcx
0x180015960  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180015965  mov     rcx, cs:WPP_GLOBAL_Control
0x18001596c  lea     rbp, WPP_GLOBAL_Control
0x180015973  cmp     rcx, rbp
0x180015976  jz      short loc_1800159A0
0x180015978  test    byte ptr [rcx+1Ch], 2
0x18001597c  jz      short loc_1800159A0
0x18001597e  cmp     byte ptr [rcx+19h], 5
0x180015982  jb      short loc_1800159A0
0x180015984  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001598b  lea     r8, WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids
0x180015992  mov     rcx, [rcx+10h]
0x180015996  mov     edx, 42h ; 'B'
0x18001599b  call    WPP_SF_s
0x1800159a0  mov     rcx, [rdi+10h]; struct _CARD_STATE *
0x1800159a4  call    TransactionManagerStartTimer
0x1800159a9  mov     ebx, eax
0x1800159ab  test    eax, eax
0x1800159ad  jz      short loc_1800159F1
0x1800159af  mov     edx, 2
0x1800159b4  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800159b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800159c0  cmp     rcx, rbp
0x1800159c3  jz      short loc_1800159F1
0x1800159c5  test    byte ptr [rcx+1Ch], 1
0x1800159c9  jz      short loc_1800159F1
0x1800159cb  cmp     byte ptr [rcx+19h], 2
0x1800159cf  jb      short loc_1800159F1
0x1800159d1  mov     rax, [rdi+10h]
0x1800159d5  mov     edx, 43h ; 'C'
0x1800159da  mov     rcx, [rcx+10h]
0x1800159de  mov     eax, [rax+250h]
0x1800159e4  mov     [rsp+38h+var_10], eax
0x1800159e8  mov     [rsp+38h+var_18], ebx
0x1800159ec  call    WPP_SF_sDl
0x1800159f1  mov     rcx, [rdi+10h]
0x1800159f5  add     rcx, 270h
0x1800159fc  call    KspLeaveCriticalSection
0x180015a01  mov     edx, 1
0x180015a06  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180015a0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015a12  cmp     rcx, rbp
0x180015a15  jz      short loc_180015A43
0x180015a17  test    byte ptr [rcx+1Ch], 2
0x180015a1b  jz      short loc_180015A43
0x180015a1d  cmp     byte ptr [rcx+19h], 5
0x180015a21  jb      short loc_180015A43
0x180015a23  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180015a2a  lea     r8, WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids
0x180015a31  mov     rcx, [rcx+10h]
0x180015a35  mov     edx, 44h ; 'D'
0x180015a3a  mov     [rsp+38h+var_18], ebx
0x180015a3e  call    WPP_SF_sd
0x180015a43  mov     rbp, [rsp+38h+arg_8]
0x180015a48  mov     eax, ebx
0x180015a4a  mov     rbx, [rsp+38h+arg_0]
0x180015a4f  add     rsp, 30h
0x180015a53  pop     rdi
0x180015a54  retn
```
