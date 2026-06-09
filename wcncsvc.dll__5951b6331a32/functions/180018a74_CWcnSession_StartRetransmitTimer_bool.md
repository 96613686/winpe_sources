# CWcnSession::StartRetransmitTimer(bool)

- ea: `0x180018a74`
- end: `0x180018b7d`
- name: `?StartRetransmitTimer@CWcnSession@@QEAAX_N@Z`
- size: `265`
- prototype: `void __fastcall(CWcnSession *__hidden this, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800156c8`
- `0x18002b61c`

## callees

- `0x180004fb8`
- `0x180018a74`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180018b02`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180018b02`

## pseudocode

```c
void __fastcall CWcnSession::StartRetransmitTimer(CWcnSession *this, char a2)
{
  _BYTE *v4; // r10
  const char *Indent; // rax
  __int64 v6; // r10
  struct _TP_TIMER *v7; // rcx
  const char *v8; // rax
  __int64 v9; // r10
  const char *v10; // rax
  __int64 v11; // r10
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 128, WPP_a137d119f5dc35a130051116e3170526_Traceguids, Indent);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !*((_BYTE *)this + 448) )
    goto LABEL_10;
  if ( a2 )
    *((_DWORD *)this + 111) = 0;
  v7 = (struct _TP_TIMER *)*((_QWORD *)this + 30);
  pftDueTime = (struct _FILETIME)-5000000LL;
  SetThreadpoolTimer(v7, &pftDueTime, 0, 0x3E8u);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v8 = GetIndent(0);
      WPP_SF_s(*(_QWORD *)(v9 + 16), 129, WPP_a137d119f5dc35a130051116e3170526_Traceguids, v8);
      v4 = WPP_GLOBAL_Control;
    }
LABEL_10:
    if ( v4 != (_BYTE *)&WPP_GLOBAL_Control && v4[25] >= 6u )
    {
      v10 = GetIndent(-1);
      WPP_SF_s(*(_QWORD *)(v11 + 16), 130, WPP_a137d119f5dc35a130051116e3170526_Traceguids, v10);
    }
  }
}

```

## disassembly

```asm
0x180018a74  mov     [rsp+arg_8], rbx
0x180018a79  mov     [rsp+arg_10], rsi
0x180018a7e  push    rdi
0x180018a7f  sub     rsp, 20h
0x180018a83  mov     dil, dl
0x180018a86  mov     rbx, rcx
0x180018a89  mov     r10, cs:WPP_GLOBAL_Control
0x180018a90  lea     rsi, WPP_GLOBAL_Control
0x180018a97  cmp     r10, rsi
0x180018a9a  jz      short loc_180018ACC
0x180018a9c  cmp     byte ptr [r10+19h], 6
0x180018aa1  jb      short loc_180018ACC
0x180018aa3  mov     ecx, 1; int
0x180018aa8  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180018aad  mov     rcx, [r10+10h]
0x180018ab1  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180018ab8  mov     edx, 80h
0x180018abd  mov     r9, rax
0x180018ac0  call    WPP_SF_s
0x180018ac5  mov     r10, cs:WPP_GLOBAL_Control
0x180018acc  cmp     byte ptr [rbx+1C0h], 0
0x180018ad3  jz      short loc_180018B41
0x180018ad5  test    dil, dil
0x180018ad8  jz      short loc_180018AE4
0x180018ada  mov     dword ptr [rbx+1BCh], 0
0x180018ae4  mov     rcx, [rbx+0F0h]; pti
0x180018aeb  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180018af0  mov     r9d, 3E8h; msWindowLength
0x180018af6  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0FFFFFFFFFFB3B4C0h
0x180018aff  xor     r8d, r8d; msPeriod
0x180018b02  call    cs:__imp_SetThreadpoolTimer
0x180018b08  mov     r10, cs:WPP_GLOBAL_Control
0x180018b0f  cmp     r10, rsi
0x180018b12  jz      short loc_180018B6D
0x180018b14  cmp     byte ptr [r10+19h], 4
0x180018b19  jb      short loc_180018B41
0x180018b1b  xor     ecx, ecx; int
0x180018b1d  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180018b22  mov     rcx, [r10+10h]
0x180018b26  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180018b2d  mov     edx, 81h
0x180018b32  mov     r9, rax
0x180018b35  call    WPP_SF_s
0x180018b3a  mov     r10, cs:WPP_GLOBAL_Control
0x180018b41  cmp     r10, rsi
0x180018b44  jz      short loc_180018B6D
0x180018b46  cmp     byte ptr [r10+19h], 6
0x180018b4b  jb      short loc_180018B6D
0x180018b4d  or      ecx, 0FFFFFFFFh; int
0x180018b50  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180018b55  mov     rcx, [r10+10h]
0x180018b59  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180018b60  mov     edx, 82h
0x180018b65  mov     r9, rax
0x180018b68  call    WPP_SF_s
0x180018b6d  mov     rbx, [rsp+28h+arg_8]
0x180018b72  mov     rsi, [rsp+28h+arg_10]
0x180018b77  add     rsp, 20h
0x180018b7b  pop     rdi
0x180018b7c  retn
```
