# CWcnSession::SetSessionResult(tagWCNPRPC_SESSION_NOTIFICATION_TYPE)

- ea: `0x180018104`
- end: `0x1800181fe`
- name: `?SetSessionResult@CWcnSession@@QEAAXW4tagWCNPRPC_SESSION_NOTIFICATION_TYPE@@@Z`
- size: `250`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180018b84`
- `0x18002b61c`

## callees

- `0x180004fb8`
- `0x180005014`
- `0x180018104`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800181b2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800181b2`

## pseudocode

```c
void __fastcall CWcnSession::SetSessionResult(__int64 a1, int a2)
{
  _BYTE *v4; // r10
  const char *Indent; // rax
  __int64 v6; // r10
  unsigned int v7; // eax
  __int64 v8; // r10
  struct _TP_TIMER *v9; // rcx
  const char *v10; // rax
  __int64 v11; // r10
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      Indent = GetIndent(1);
      WPP_SF_s(*(_QWORD *)(v6 + 16), 41, WPP_a137d119f5dc35a130051116e3170526_Traceguids, Indent);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 != (_BYTE *)&WPP_GLOBAL_Control && v4[25] >= 4u )
    {
      v7 = (unsigned int)GetIndent(0);
      WPP_SF_sd(*(_QWORD *)(v8 + 16), 42, (unsigned int)WPP_a137d119f5dc35a130051116e3170526_Traceguids, v7, a2);
    }
  }
  if ( a2 == 2 && *(_DWORD *)(a1 + 20) != 2 )
  {
    v9 = *(struct _TP_TIMER **)(a1 + 232);
    pftDueTime = (struct _FILETIME)-10000000LL;
    SetThreadpoolTimer(v9, &pftDueTime, 0, 0x3E8u);
  }
  *(_DWORD *)(a1 + 20) = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v10 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v11 + 16), 43, WPP_a137d119f5dc35a130051116e3170526_Traceguids, v10);
  }
}

```

## disassembly

```asm
0x180018104  mov     [rsp+arg_8], rbx
0x180018109  mov     [rsp+arg_10], rsi
0x18001810e  push    rdi
0x18001810f  sub     rsp, 30h
0x180018113  mov     edi, edx
0x180018115  mov     rbx, rcx
0x180018118  mov     r10, cs:WPP_GLOBAL_Control
0x18001811f  lea     rsi, WPP_GLOBAL_Control
0x180018126  cmp     r10, rsi
0x180018129  jz      short loc_18001818A
0x18001812b  cmp     byte ptr [r10+19h], 6
0x180018130  jb      short loc_18001815B
0x180018132  mov     ecx, 1; int
0x180018137  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001813c  mov     rcx, [r10+10h]
0x180018140  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180018147  mov     edx, 29h ; ')'
0x18001814c  mov     r9, rax
0x18001814f  call    WPP_SF_s
0x180018154  mov     r10, cs:WPP_GLOBAL_Control
0x18001815b  cmp     r10, rsi
0x18001815e  jz      short loc_18001818A
0x180018160  cmp     byte ptr [r10+19h], 4
0x180018165  jb      short loc_18001818A
0x180018167  xor     ecx, ecx; int
0x180018169  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001816e  mov     rcx, [r10+10h]
0x180018172  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180018179  mov     edx, 2Ah ; '*'
0x18001817e  mov     [rsp+38h+var_18], edi
0x180018182  mov     r9, rax
0x180018185  call    WPP_SF_sd
0x18001818a  cmp     edi, 2
0x18001818d  jnz     short loc_1800181B8
0x18001818f  cmp     [rbx+14h], edi
0x180018192  jz      short loc_1800181B8
0x180018194  mov     rcx, [rbx+0E8h]; pti
0x18001819b  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800181a0  mov     r9d, 3E8h; msWindowLength
0x1800181a6  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], 0FFFFFFFFFF676980h
0x1800181af  xor     r8d, r8d; msPeriod
0x1800181b2  call    cs:__imp_SetThreadpoolTimer
0x1800181b8  mov     [rbx+14h], edi
0x1800181bb  mov     r10, cs:WPP_GLOBAL_Control
0x1800181c2  cmp     r10, rsi
0x1800181c5  jz      short loc_1800181EE
0x1800181c7  cmp     byte ptr [r10+19h], 6
0x1800181cc  jb      short loc_1800181EE
0x1800181ce  or      ecx, 0FFFFFFFFh; int
0x1800181d1  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800181d6  mov     rcx, [r10+10h]
0x1800181da  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x1800181e1  mov     edx, 2Bh ; '+'
0x1800181e6  mov     r9, rax
0x1800181e9  call    WPP_SF_s
0x1800181ee  mov     rbx, [rsp+38h+arg_8]
0x1800181f3  mov     rsi, [rsp+38h+arg_10]
0x1800181f8  add     rsp, 30h
0x1800181fc  pop     rdi
0x1800181fd  retn
```
