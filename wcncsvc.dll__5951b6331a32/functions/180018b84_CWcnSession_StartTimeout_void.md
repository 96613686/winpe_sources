# CWcnSession::StartTimeout(void)

- ea: `0x180018b84`
- end: `0x180018c64`
- name: `?StartTimeout@CWcnSession@@QEAAXXZ`
- size: `224`
- prototype: `void __fastcall(CWcnSession *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800195d0`

## callees

- `0x180004fb8`
- `0x180018104`
- `0x180018b84`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180018c20`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180018c20`

## pseudocode

```c
void __fastcall CWcnSession::StartTimeout(CWcnSession *this)
{
  _BYTE *v2; // r10
  const char *Indent; // rax
  __int64 v4; // r10
  const char *v5; // rax
  __int64 v6; // r10
  const char *v7; // rax
  __int64 v8; // r10

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      Indent = GetIndent(1);
      WPP_SF_s(*(_QWORD *)(v4 + 16), 38, WPP_a137d119f5dc35a130051116e3170526_Traceguids, Indent);
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != (_BYTE *)&WPP_GLOBAL_Control && v2[25] >= 3u )
    {
      v5 = GetIndent(0);
      WPP_SF_s(*(_QWORD *)(v6 + 16), 39, WPP_a137d119f5dc35a130051116e3170526_Traceguids, v5);
    }
  }
  if ( *((_DWORD *)this + 5) != 2 )
    CWcnSession::SetSessionResult((__int64)this, 1);
  _InterlockedIncrement((volatile signed __int32 *)this + 398);
  SubmitThreadpoolWork(*((PTP_WORK *)this + 31));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v7 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v8 + 16), 40, WPP_a137d119f5dc35a130051116e3170526_Traceguids, v7);
  }
}

```

## disassembly

```asm
0x180018b84  mov     [rsp+arg_0], rbx
0x180018b89  push    rdi
0x180018b8a  sub     rsp, 20h
0x180018b8e  mov     rbx, rcx
0x180018b91  mov     r10, cs:WPP_GLOBAL_Control
0x180018b98  lea     rdi, WPP_GLOBAL_Control
0x180018b9f  cmp     r10, rdi
0x180018ba2  jz      short loc_180018BFF
0x180018ba4  cmp     byte ptr [r10+19h], 6
0x180018ba9  jb      short loc_180018BD4
0x180018bab  mov     ecx, 1; int
0x180018bb0  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180018bb5  mov     rcx, [r10+10h]
0x180018bb9  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180018bc0  mov     edx, 26h ; '&'
0x180018bc5  mov     r9, rax
0x180018bc8  call    WPP_SF_s
0x180018bcd  mov     r10, cs:WPP_GLOBAL_Control
0x180018bd4  cmp     r10, rdi
0x180018bd7  jz      short loc_180018BFF
0x180018bd9  cmp     byte ptr [r10+19h], 3
0x180018bde  jb      short loc_180018BFF
0x180018be0  xor     ecx, ecx; int
0x180018be2  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180018be7  mov     rcx, [r10+10h]
0x180018beb  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180018bf2  mov     edx, 27h ; '''
0x180018bf7  mov     r9, rax
0x180018bfa  call    WPP_SF_s
0x180018bff  cmp     dword ptr [rbx+14h], 2
0x180018c03  jz      short loc_180018C12
0x180018c05  mov     edx, 1
0x180018c0a  mov     rcx, rbx
0x180018c0d  call    ?SetSessionResult@CWcnSession@@QEAAXW4tagWCNPRPC_SESSION_NOTIFICATION_TYPE@@@Z; CWcnSession::SetSessionResult(tagWCNPRPC_SESSION_NOTIFICATION_TYPE)
0x180018c12  lock inc dword ptr [rbx+638h]
0x180018c19  mov     rcx, [rbx+0F8h]; pwk
0x180018c20  call    cs:__imp_SubmitThreadpoolWork
0x180018c26  mov     r10, cs:WPP_GLOBAL_Control
0x180018c2d  cmp     r10, rdi
0x180018c30  jz      short loc_180018C59
0x180018c32  cmp     byte ptr [r10+19h], 6
0x180018c37  jb      short loc_180018C59
0x180018c39  or      ecx, 0FFFFFFFFh; int
0x180018c3c  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180018c41  mov     rcx, [r10+10h]
0x180018c45  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180018c4c  mov     edx, 28h ; '('
0x180018c51  mov     r9, rax
0x180018c54  call    WPP_SF_s
0x180018c59  mov     rbx, [rsp+28h+arg_0]
0x180018c5e  add     rsp, 20h
0x180018c62  pop     rdi
0x180018c63  retn
```
