# HTTP2ProxyVirtualConnection::SendComplete(long,HTTP2SendContext *,int)

- ea: `0x180018690`
- end: `0x1800187e4`
- name: `?SendComplete@HTTP2ProxyVirtualConnection@@UEAAJJPEAVHTTP2SendContext@@H@Z`
- size: `340`
- prototype: `int(HTTP2ProxyVirtualConnection *__hidden this, int, struct HTTP2SendContext *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005634`
- `0x18000aafc`
- `0x18000f2bc`
- `0x180018690`
- `0x18001ac1c`
- `0x180025010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800187b5`
- `ntdll!RtlLeaveCriticalSection` at `0x1800187b5`
- `ntdll!RtlEnterCriticalSection` at `0x180018726`
- `ntdll!RtlEnterCriticalSection` at `0x180018726`

## pseudocode

```c
__int64 __fastcall HTTP2ProxyVirtualConnection::SendComplete(
        HTTP2ProxyVirtualConnection *this,
        unsigned int a2,
        struct HTTP2SendContext *a3)
{
  unsigned int v5; // r15d
  __int64 v6; // rax
  HTTP2ChannelPointer *v7; // rsi
  __int64 v8; // rax
  int v9; // r12d
  int v10; // r13d
  __int64 v11; // rdx
  struct HTTP2Channel *v12; // rax
  struct HTTP2Channel *v13; // rbx
  struct HTTP2Channel *v14; // r14
  HTTP2GenericReceiver *v15; // rcx
  __int64 v16; // rax
  struct HTTP2Channel *v17; // rcx
  __int64 v18; // rdx
  unsigned int v20; // [rsp+30h] [rbp-18h] BYREF
  int v21; // [rsp+34h] [rbp-14h] BYREF
  PRTL_CRITICAL_SECTION CriticalSection; // [rsp+38h] [rbp-10h]
  unsigned int v23; // [rsp+98h] [rbp+50h] BYREF

  v5 = a2;
  v20 = 0;
  v23 = 0;
  if ( a2 || *((_DWORD *)a3 + 22) != 2 )
    goto LABEL_20;
  if ( *((unsigned __int16 *)this + 76) == *((_DWORD *)a3 + 24) )
  {
    v6 = 120;
  }
  else
  {
    if ( *((unsigned __int16 *)this + 78) != *((_DWORD *)a3 + 24) )
      goto LABEL_20;
    v6 = 136;
  }
  v7 = (HTTP2ProxyVirtualConnection *)((char *)this + v6);
  if ( !(HTTP2ProxyVirtualConnection *)((char *)this + v6) )
    goto LABEL_20;
  v8 = *(_QWORD *)this;
  v9 = 0;
  v21 = 0;
  v10 = (*(__int64 (__fastcall **)(HTTP2ProxyVirtualConnection *))(v8 + 184))(this);
  CriticalSection = (PRTL_CRITICAL_SECTION)((char *)this + 312);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 312));
  v12 = HTTP2ChannelPointer::LockChannelPointer(v7, v11);
  if ( v10 )
  {
    v13 = v12;
    if ( v12 )
    {
      v14 = 0;
      v15 = (struct HTTP2Channel *)((char *)v12 + 88);
      goto LABEL_13;
    }
  }
  else
  {
    v14 = v12;
    if ( v12 )
    {
      v13 = 0;
      v15 = (struct HTTP2Channel *)((char *)v12 + 112);
LABEL_13:
      v9 = 1;
      HTTP2GenericReceiver::BytesConsumedNotification(v15, *((_DWORD *)a3 + 14), 0, &v21, &v20, &v23);
      if ( v21 )
      {
        if ( v10 )
        {
          v16 = *(_QWORD *)v13;
          v17 = v13;
        }
        else
        {
          v16 = *(_QWORD *)v14;
          v17 = v14;
        }
        v5 = (*(__int64 (__fastcall **)(struct HTTP2Channel *, _QWORD, _QWORD))(v16 + 104))(v17, v20, v23);
      }
    }
  }
  RtlLeaveCriticalSection(CriticalSection);
  if ( v9 )
    HTTP2ChannelPointer::UnlockChannelPointer(v7, v18);
LABEL_20:
  FreeSendContextAndPossiblyData(a3);
  return v5;
}

```

## disassembly

```asm
0x180018690  push    rbp
0x180018692  push    rbx
0x180018693  push    rsi
0x180018694  push    rdi
0x180018695  push    r12
0x180018697  push    r13
0x180018699  push    r14
0x18001869b  push    r15
0x18001869d  mov     rbp, rsp
0x1800186a0  sub     rsp, 48h
0x1800186a4  mov     rbx, rcx
0x1800186a7  mov     rdi, r8
0x1800186aa  xor     ecx, ecx
0x1800186ac  mov     r15d, edx
0x1800186af  mov     [rbp+var_18], ecx
0x1800186b2  mov     [rbp+arg_8], ecx
0x1800186b5  test    edx, edx
0x1800186b7  jnz     loc_1800187C8
0x1800186bd  cmp     dword ptr [r8+58h], 2
0x1800186c2  jnz     loc_1800187C8
0x1800186c8  movzx   eax, word ptr [rbx+98h]
0x1800186cf  cmp     eax, [r8+60h]
0x1800186d3  jnz     short loc_1800186DA
0x1800186d5  lea     eax, [rdx+78h]
0x1800186d8  jmp     short loc_1800186F0
0x1800186da  movzx   eax, word ptr [rbx+9Ch]
0x1800186e1  cmp     eax, [r8+60h]
0x1800186e5  jnz     loc_1800187C8
0x1800186eb  mov     eax, 88h
0x1800186f0  lea     rsi, [rax+rbx]
0x1800186f4  test    rsi, rsi
0x1800186f7  jz      loc_1800187C8
0x1800186fd  mov     rax, [rbx]
0x180018700  mov     r12d, ecx
0x180018703  mov     [rbp+var_14], ecx
0x180018706  mov     rcx, rbx
0x180018709  mov     rax, [rax+0B8h]
0x180018710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018715  mov     r13d, eax
0x180018718  lea     rax, [rbx+138h]
0x18001871f  mov     rcx, rax; CriticalSection
0x180018722  mov     [rbp+CriticalSection], rax
0x180018726  call    cs:__imp_RtlEnterCriticalSection
0x18001872c  mov     rcx, rsi; this
0x18001872f  call    ?LockChannelPointer@HTTP2ChannelPointer@@QEAAPEAVHTTP2Channel@@XZ; HTTP2ChannelPointer::LockChannelPointer(void)
0x180018734  test    r13d, r13d
0x180018737  jz      short loc_18001874A
0x180018739  mov     rbx, rax
0x18001873c  test    rax, rax
0x18001873f  jz      short loc_1800187B1
0x180018741  xor     r14d, r14d
0x180018744  lea     rcx, [rax+58h]
0x180018748  jmp     short loc_180018758
0x18001874a  mov     r14, rax
0x18001874d  test    rax, rax
0x180018750  jz      short loc_1800187B1
0x180018752  xor     ebx, ebx
0x180018754  lea     rcx, [rax+70h]; this
0x180018758  mov     edx, 38h ; '8'
0x18001875d  lea     r10, [rbp+arg_8]
0x180018761  lea     rax, [rbp+var_18]
0x180018765  mov     [rsp+48h+var_20], r10; unsigned int *
0x18001876a  mov     r11, rdi
0x18001876d  mov     [rsp+48h+var_28], rax; unsigned int *
0x180018772  lea     r9, [rbp+var_14]; int *
0x180018776  xor     r8d, r8d; int
0x180018779  lea     r12d, [rdx-37h]
0x18001877d  mov     edx, [rdi+rdx]; unsigned int
0x180018780  call    ?BytesConsumedNotification@HTTP2GenericReceiver@@QEAAXKHPEAHPEAK1@Z; HTTP2GenericReceiver::BytesConsumedNotification(ulong,int,int *,ulong *,ulong *)
0x180018785  cmp     [rbp+var_14], 0
0x180018789  jz      short loc_1800187B1
0x18001878b  mov     r8d, [rbp+arg_8]
0x18001878f  mov     edx, [rbp+var_18]
0x180018792  test    r13d, r13d
0x180018795  jz      short loc_18001879F
0x180018797  mov     rax, [rbx]
0x18001879a  mov     rcx, rbx
0x18001879d  jmp     short loc_1800187A5
0x18001879f  mov     rax, [r14]
0x1800187a2  mov     rcx, r14
0x1800187a5  mov     rax, [rax+68h]
0x1800187a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187ae  mov     r15d, eax
0x1800187b1  mov     rcx, [rbp+CriticalSection]; CriticalSection
0x1800187b5  call    cs:__imp_RtlLeaveCriticalSection
0x1800187bb  test    r12d, r12d
0x1800187be  jz      short loc_1800187C8
0x1800187c0  mov     rcx, rsi; this
0x1800187c3  call    ?UnlockChannelPointer@HTTP2ChannelPointer@@QEAAXXZ; HTTP2ChannelPointer::UnlockChannelPointer(void)
0x1800187c8  mov     rcx, rdi; struct HTTP2SendContext *
0x1800187cb  call    ?FreeSendContextAndPossiblyData@@YAXPEAVHTTP2SendContext@@@Z; FreeSendContextAndPossiblyData(HTTP2SendContext *)
0x1800187d0  mov     eax, r15d
0x1800187d3  add     rsp, 48h
0x1800187d7  pop     r15
0x1800187d9  pop     r14
0x1800187db  pop     r13
0x1800187dd  pop     r12
0x1800187df  pop     rdi
0x1800187e0  pop     rsi
0x1800187e1  pop     rbx
0x1800187e2  pop     rbp
0x1800187e3  retn
```
