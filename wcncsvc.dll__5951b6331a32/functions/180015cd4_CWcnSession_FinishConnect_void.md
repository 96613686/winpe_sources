# CWcnSession::FinishConnect(void)

- ea: `0x180015cd4`
- end: `0x180015dae`
- name: `?FinishConnect@CWcnSession@@QEAAXXZ`
- size: `218`
- prototype: `void __fastcall(CWcnSession *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1800157bc`
- `0x180046e54`
- `0x18004a7a8`
- `0x18004f8f8`
- `0x1800569c0`

## callees

- `0x180004fb8`
- `0x180015cd4`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015d2e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015d2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015d6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015d6a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015d5c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015d5c`

## pseudocode

```c
void __fastcall CWcnSession::FinishConnect(CWcnSession *this)
{
  const char *Indent; // rax
  __int64 v3; // r10
  struct _TP_TIMER *v4; // rcx
  const char *v5; // rax
  __int64 v6; // r10
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  pftDueTime = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v3 + 16), 30, WPP_a137d119f5dc35a130051116e3170526_Traceguids, Indent);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this + 4) + 16LL));
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 29);
  *((_DWORD *)this + 56) = 2;
  pftDueTime = (struct _FILETIME)-300000000LL;
  SetThreadpoolTimer(v4, &pftDueTime, 0, 0x3E8u);
  LeaveCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this + 4) + 16LL));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v5 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 31, WPP_a137d119f5dc35a130051116e3170526_Traceguids, v5);
  }
}

```

## disassembly

```asm
0x180015cd4  mov     [rsp+arg_8], rbx
0x180015cd9  push    rdi
0x180015cda  sub     rsp, 20h
0x180015cde  mov     rbx, rcx
0x180015ce1  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0
0x180015cea  mov     r10, cs:WPP_GLOBAL_Control
0x180015cf1  lea     rdi, WPP_GLOBAL_Control
0x180015cf8  cmp     r10, rdi
0x180015cfb  jz      short loc_180015D26
0x180015cfd  cmp     byte ptr [r10+19h], 6
0x180015d02  jb      short loc_180015D26
0x180015d04  mov     ecx, 1; int
0x180015d09  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180015d0e  mov     rcx, [r10+10h]
0x180015d12  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180015d19  mov     edx, 1Eh
0x180015d1e  mov     r9, rax
0x180015d21  call    WPP_SF_s
0x180015d26  mov     rcx, [rbx+20h]
0x180015d2a  add     rcx, 10h; lpCriticalSection
0x180015d2e  call    cs:__imp_EnterCriticalSection
0x180015d34  mov     rcx, [rbx+0E8h]; pti
0x180015d3b  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180015d40  mov     r9d, 3E8h; msWindowLength
0x180015d46  mov     dword ptr [rbx+0E0h], 2
0x180015d50  xor     r8d, r8d; msPeriod
0x180015d53  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0FFFFFFFFEE1E5D00h
0x180015d5c  call    cs:__imp_SetThreadpoolTimer
0x180015d62  mov     rcx, [rbx+20h]
0x180015d66  add     rcx, 10h; lpCriticalSection
0x180015d6a  call    cs:__imp_LeaveCriticalSection
0x180015d70  mov     r10, cs:WPP_GLOBAL_Control
0x180015d77  cmp     r10, rdi
0x180015d7a  jz      short loc_180015DA3
0x180015d7c  cmp     byte ptr [r10+19h], 6
0x180015d81  jb      short loc_180015DA3
0x180015d83  or      ecx, 0FFFFFFFFh; int
0x180015d86  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180015d8b  mov     rcx, [r10+10h]
0x180015d8f  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180015d96  mov     edx, 1Fh
0x180015d9b  mov     r9, rax
0x180015d9e  call    WPP_SF_s
0x180015da3  mov     rbx, [rsp+28h+arg_8]
0x180015da8  add     rsp, 20h
0x180015dac  pop     rdi
0x180015dad  retn
```
