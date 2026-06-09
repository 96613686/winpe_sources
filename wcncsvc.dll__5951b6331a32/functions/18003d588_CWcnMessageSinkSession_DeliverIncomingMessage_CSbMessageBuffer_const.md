# CWcnMessageSinkSession::DeliverIncomingMessage(CSbMessageBuffer const *)

- ea: `0x18003d588`
- end: `0x18003d6e0`
- name: `?DeliverIncomingMessage@CWcnMessageSinkSession@@QEAAJPEBVCSbMessageBuffer@@@Z`
- size: `344`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, const struct CSbMessageBuffer *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18003b9a0`

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18003d588`
- `0x180053004`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d617`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d617`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d696`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d696`

## string_xrefs

- `0x18003d5f7`: `pIncomingMessage`

## pseudocode

```c
__int64 __fastcall CWcnMessageSinkSession::DeliverIncomingMessage(
        struct _RTL_CRITICAL_SECTION *this,
        const struct CSbMessageBuffer *a2)
{
  _QWORD *v4; // r10
  const char *Indent; // rax
  __int64 v6; // r10
  struct _RTL_CRITICAL_SECTION *v8; // rsi
  __int64 (__fastcall ***LockSemaphore)(_QWORD, const struct CSbMessageBuffer *); // rcx
  int v10; // ebx
  const char *v11; // rax
  __int64 v12; // r10
  int v13; // eax
  unsigned int v14; // eax
  __int64 v15; // r10

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 10, WPP_f858ace61d993a6396e44ebc084c96fb_Traceguids, Indent);
    v4 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v8 = this + 1;
    EnterCriticalSection(this + 1);
    LockSemaphore = (__int64 (__fastcall ***)(_QWORD, const struct CSbMessageBuffer *))this->LockSemaphore;
    if ( LockSemaphore )
    {
      v13 = (**LockSemaphore)(LockSemaphore, a2);
      v10 = v13;
      if ( v13 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_f858ace61d993a6396e44ebc084c96fb_Traceguids,
          (unsigned int)v13);
    }
    else
    {
      v10 = -2147022646;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = GetIndent(0);
        WPP_SF_s(*(_QWORD *)(v12 + 16), 12, WPP_f858ace61d993a6396e44ebc084c96fb_Traceguids, v11);
      }
    }
    LeaveCriticalSection(v8);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v10 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
    {
      v14 = (unsigned int)GetIndent(-1);
      WPP_SF_sd(*(_QWORD *)(v15 + 16), 14, (unsigned int)WPP_f858ace61d993a6396e44ebc084c96fb_Traceguids, v14, v10);
    }
    return (unsigned int)v10;
  }
  else
  {
    if ( v4 != &WPP_GLOBAL_Control && *((_BYTE *)v4 + 25) >= 2u )
      WPP_SF_s(v4[2], 11, WPP_f858ace61d993a6396e44ebc084c96fb_Traceguids, "pIncomingMessage");
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x18003d588  push    rbx
0x18003d58a  push    rbp
0x18003d58b  push    rsi
0x18003d58c  push    rdi
0x18003d58d  push    r14
0x18003d58f  sub     rsp, 30h
0x18003d593  mov     rdi, rdx
0x18003d596  mov     rbx, rcx
0x18003d599  mov     r10, cs:WPP_GLOBAL_Control
0x18003d5a0  lea     rbp, WPP_GLOBAL_Control
0x18003d5a7  lea     r14, WPP_f858ace61d993a6396e44ebc084c96fb_Traceguids
0x18003d5ae  cmp     r10, rbp
0x18003d5b1  jz      short loc_18003D5DF
0x18003d5b3  cmp     byte ptr [r10+19h], 6
0x18003d5b8  jb      short loc_18003D5DF
0x18003d5ba  mov     ecx, 1; int
0x18003d5bf  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003d5c4  mov     rcx, [r10+10h]
0x18003d5c8  mov     edx, 0Ah
0x18003d5cd  mov     r9, rax
0x18003d5d0  mov     r8, r14
0x18003d5d3  call    WPP_SF_s
0x18003d5d8  mov     r10, cs:WPP_GLOBAL_Control
0x18003d5df  test    rdi, rdi
0x18003d5e2  jnz     short loc_18003D610
0x18003d5e4  cmp     r10, rbp
0x18003d5e7  jz      short loc_18003D606
0x18003d5e9  cmp     byte ptr [r10+19h], 2
0x18003d5ee  jb      short loc_18003D606
0x18003d5f0  mov     rcx, [r10+10h]
0x18003d5f4  lea     edx, [rdi+0Bh]
0x18003d5f7  lea     r9, aPincomingmessa; "pIncomingMessage"
0x18003d5fe  mov     r8, r14
0x18003d601  call    WPP_SF_s
0x18003d606  mov     eax, 80004003h
0x18003d60b  jmp     loc_18003D6D5
0x18003d610  lea     rsi, [rbx+28h]
0x18003d614  mov     rcx, rsi; lpCriticalSection
0x18003d617  call    cs:__imp_EnterCriticalSection
0x18003d61d  mov     rcx, [rbx+18h]; int
0x18003d621  test    rcx, rcx
0x18003d624  jnz     short loc_18003D659
0x18003d626  mov     ebx, 800708CAh
0x18003d62b  mov     r10, cs:WPP_GLOBAL_Control
0x18003d632  cmp     r10, rbp
0x18003d635  jz      short loc_18003D693
0x18003d637  cmp     byte ptr [r10+19h], 2
0x18003d63c  jb      short loc_18003D693
0x18003d63e  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003d643  mov     rcx, [r10+10h]
0x18003d647  mov     edx, 0Ch
0x18003d64c  mov     r9, rax
0x18003d64f  mov     r8, r14
0x18003d652  call    WPP_SF_s
0x18003d657  jmp     short loc_18003D693
0x18003d659  mov     rax, [rcx]
0x18003d65c  mov     rdx, rdi
0x18003d65f  mov     rax, [rax]
0x18003d662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d667  mov     ebx, eax
0x18003d669  test    eax, eax
0x18003d66b  jns     short loc_18003D693
0x18003d66d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d674  cmp     rcx, rbp
0x18003d677  jz      short loc_18003D693
0x18003d679  cmp     byte ptr [rcx+19h], 2
0x18003d67d  jb      short loc_18003D693
0x18003d67f  mov     rcx, [rcx+10h]
0x18003d683  mov     edx, 0Dh
0x18003d688  mov     r9d, eax
0x18003d68b  mov     r8, r14
0x18003d68e  call    WPP_SF_d
0x18003d693  mov     rcx, rsi; lpCriticalSection
0x18003d696  call    cs:__imp_LeaveCriticalSection
0x18003d69c  mov     r10, cs:WPP_GLOBAL_Control
0x18003d6a3  cmp     r10, rbp
0x18003d6a6  jz      short loc_18003D6D3
0x18003d6a8  test    ebx, ebx
0x18003d6aa  js      short loc_18003D6B3
0x18003d6ac  cmp     byte ptr [r10+19h], 6
0x18003d6b1  jb      short loc_18003D6D3
0x18003d6b3  or      ecx, 0FFFFFFFFh; int
0x18003d6b6  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003d6bb  mov     rcx, [r10+10h]
0x18003d6bf  mov     edx, 0Eh
0x18003d6c4  mov     r9, rax
0x18003d6c7  mov     [rsp+58h+var_38], ebx
0x18003d6cb  mov     r8, r14
0x18003d6ce  call    WPP_SF_sd
0x18003d6d3  mov     eax, ebx
0x18003d6d5  add     rsp, 30h
0x18003d6d9  pop     r14
0x18003d6db  pop     rdi
0x18003d6dc  pop     rsi
0x18003d6dd  pop     rbp
0x18003d6de  pop     rbx
0x18003d6df  retn
```
