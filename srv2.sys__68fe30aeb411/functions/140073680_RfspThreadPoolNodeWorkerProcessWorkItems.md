# RfspThreadPoolNodeWorkerProcessWorkItems

- ea: `0x140073680`
- end: `0x140073a4c`
- name: `RfspThreadPoolNodeWorkerProcessWorkItems`
- size: `972`
- prototype: `EXPAND_STACK_CALLOUT`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400734b0`

## callees

- `0x140004960`
- `0x140038490`
- `0x1400384d0`
- `0x140073680`

## import_xrefs

- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x1400737e2`
- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x1400737e2`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14007381a`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14007381a`
- `ntoskrnl!KeSetEvent` at `0x140073988`
- `ntoskrnl!KeSetEvent` at `0x1400739c0`
- `ntoskrnl!KeSetEvent` at `0x140073988`
- `ntoskrnl!KeSetEvent` at `0x1400739c0`
- `ntoskrnl!KeWaitForSingleObject` at `0x140073874`
- `ntoskrnl!KeWaitForSingleObject` at `0x140073874`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x140073709`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x1400738e4`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x140073709`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x1400738e4`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400736ea`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400738c9`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400736ea`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400738c9`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400739ab`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400739ab`
- `ntoskrnl!InterlockedPushListSList` at `0x140073753`
- `ntoskrnl!InterlockedPushListSList` at `0x14007392a`
- `ntoskrnl!InterlockedPushListSList` at `0x140073753`
- `ntoskrnl!InterlockedPushListSList` at `0x14007392a`

## pseudocode

```c
void __fastcall RfspThreadPoolNodeWorkerProcessWorkItems(_QWORD *Parameter)
{
  __int64 v1; // rbp
  char v2; // r12
  char v3; // r13
  int v4; // r15d
  char v5; // r14
  char v6; // di
  PSLIST_ENTRY v7; // rax
  PSLIST_ENTRY v8; // rbx
  PSLIST_ENTRY v9; // rax
  struct _SLIST_ENTRY *v10; // rcx
  struct _SLIST_ENTRY *Next; // rdx
  ULONG v12; // r9d
  struct _SLIST_ENTRY *v13; // rax
  char v14; // al
  __int64 v15; // rdx
  USHORT v16; // cx
  union _LARGE_INTEGER *Timeout; // rax
  NTSTATUS v18; // eax
  PSLIST_ENTRY v19; // rax
  PSLIST_ENTRY v20; // rax
  struct _SLIST_ENTRY *v21; // rdx
  struct _SLIST_ENTRY *v22; // rcx
  ULONG v23; // r9d
  struct _SLIST_ENTRY *v24; // rax
  char v25; // di
  __int16 epi16; // [rsp+30h] [rbp-98h]
  unsigned __int16 v27; // [rsp+38h] [rbp-90h]
  union _LARGE_INTEGER v28; // [rsp+40h] [rbp-88h] BYREF
  KAFFINITY Mask; // [rsp+50h] [rbp-78h]
  struct _GROUP_AFFINITY Affinity; // [rsp+60h] [rbp-68h] BYREF

  v1 = Parameter[2];
  Affinity = 0;
  v28.QuadPart = 0;
  v2 = 0;
  v3 = 1;
  v27 = *(_WORD *)(v1 + 234);
  epi16 = 0;
  Mask = 0;
LABEL_2:
  v4 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      v5 = 0;
      v6 = 0;
      while ( 1 )
      {
        v7 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v1);
        v8 = v7;
        if ( v7 )
          break;
        v9 = ExpInterlockedFlushSList((PSLIST_HEADER)(v1 + 16));
        v10 = v9;
        if ( v9 )
        {
          Next = v9->Next;
          v8 = v9;
          if ( !v9->Next )
            goto LABEL_55;
          v12 = 0;
          do
          {
            v13 = Next->Next;
            ++v12;
            Next->Next = v8;
            Next = v13;
            v8 = v10->Next;
            v10->Next = v13;
          }
          while ( v13 );
          InterlockedPushListSList((PSLIST_HEADER)v1, v8->Next, v10, v12);
          v10 = v8;
          v14 = 1;
          if ( v8 )
            goto LABEL_10;
        }
        if ( _InterlockedIncrement16((volatile signed __int16 *)(v1 + 66)) == 1 )
        {
          v19 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v1);
          v8 = v19;
          if ( v19 )
          {
            v21 = v19;
LABEL_35:
            if ( !_InterlockedDecrement16((volatile signed __int16 *)(v1 + 66)) )
            {
              v5 = 1;
              goto LABEL_13;
            }
            if ( !v21->Next )
              goto LABEL_13;
LABEL_28:
            RfspThreadPoolNodeWakeIdleWorker(v1);
            goto LABEL_13;
          }
          v20 = ExpInterlockedFlushSList((PSLIST_HEADER)(v1 + 16));
          v21 = v20;
          if ( v20 )
          {
            v22 = v20->Next;
            v8 = v20;
            if ( !v20->Next )
              goto LABEL_35;
            v23 = 0;
            do
            {
              v24 = v22->Next;
              ++v23;
              v22->Next = v8;
              v22 = v24;
              v8 = v21->Next;
              v21->Next = v24;
            }
            while ( v24 );
            InterlockedPushListSList((PSLIST_HEADER)v1, v8->Next, v21, v23);
            v21 = v8;
            if ( v8 )
              goto LABEL_35;
          }
          Timeout = 0;
        }
        else
        {
          v28.QuadPart = -300000000;
          Timeout = &v28;
        }
        v18 = KeWaitForSingleObject((PVOID)(v1 + 72), Executive, 0, 0, Timeout);
        if ( _InterlockedExchangeAdd16((volatile signed __int16 *)(v1 + 66), 0xFFFFu) == 1 )
        {
          v5 = 1;
        }
        else
        {
          if ( v18 == 258 )
            goto LABEL_43;
          v6 = 1;
        }
      }
      v10 = v7;
LABEL_55:
      v14 = 0;
LABEL_10:
      if ( v10->Next && (v6 || v14 && *(_WORD *)(v1 + 66)) )
        goto LABEL_28;
LABEL_13:
      v15 = 1;
      if ( v3 )
      {
        _InterlockedExchange((volatile __int32 *)(v1 + 68), 0);
        v3 = 0;
        if ( !*(_WORD *)(v1 + 66) )
          v5 = 1;
      }
      if ( (PSLIST_ENTRY)(v1 + 192) == v8 )
        break;
      v2 = 0;
      if ( v5 && *(_WORD *)(v1 + 64) < v27 && !_InterlockedCompareExchange((volatile signed __int32 *)(v1 + 68), 1, 0) )
        KeSetEvent((PRKEVENT)(v1 + 96), 0, 0);
      ((void (__fastcall *)(_QWORD, __int64))v8[1].Next)(*((_QWORD *)&v8[1].Next + 1), v15);
      if ( ++v4 == 0x4000 )
      {
        v16 = *(_WORD *)(v1 + 232);
        Affinity = 0;
        KeQueryNodeActiveAffinity(v16, &Affinity, 0);
        if ( Mask != Affinity.Mask || epi16 != Affinity.Group )
        {
          if ( Affinity.Mask )
          {
            KeSetSystemGroupAffinityThread(&Affinity, 0);
            Mask = Affinity.Mask;
            epi16 = _mm_extract_epi16((__m128i)Affinity, 4);
          }
        }
        goto LABEL_2;
      }
    }
    v25 = 0;
    if ( !v8->Next )
      v25 = v2;
    ExpInterlockedPushEntrySList((PSLIST_HEADER)(v1 + 16), (PSLIST_ENTRY)(v1 + 192));
    KeSetEvent((PRKEVENT)(v1 + 72), 0, 0);
    if ( v25 )
      break;
    v2 = 1;
  }
LABEL_43:
  if ( v3 )
    _InterlockedExchange((volatile __int32 *)(v1 + 68), 0);
}

```

## disassembly

```asm
0x140073680  push    rbx
0x140073682  push    rbp
0x140073683  push    rsi
0x140073684  push    rdi
0x140073685  push    r12
0x140073687  push    r13
0x140073689  push    r14
0x14007368b  push    r15
0x14007368d  sub     rsp, 88h
0x140073694  mov     rax, cs:__security_cookie
0x14007369b  xor     rax, rsp
0x14007369e  mov     [rsp+0C8h+var_58], rax
0x1400736a3  mov     rbp, [rcx+10h]
0x1400736a7  xorps   xmm0, xmm0
0x1400736aa  movups  xmmword ptr [rsp+0C8h+Affinity.Mask], xmm0
0x1400736af  mov     qword ptr [rsp+0C8h+var_88], 0
0x1400736b8  xor     r12b, r12b
0x1400736bb  mov     r13b, 1
0x1400736be  movzx   eax, word ptr [rbp+0EAh]
0x1400736c5  mov     [rsp+0C8h+var_90], ax
0x1400736ca  movzx   eax, [rsp+0C8h+Affinity.Group]
0x1400736cf  mov     [rsp+0C8h+var_98], ax
0x1400736d4  mov     rax, [rsp+0C8h+Affinity.Mask]
0x1400736d9  mov     [rsp+0C8h+var_78], rax
0x1400736de  xor     r15d, r15d
0x1400736e1  xor     r14b, r14b
0x1400736e4  xor     dil, dil
0x1400736e7  mov     rcx, rbp; ListHead
0x1400736ea  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400736f1  nop     dword ptr [rax+rax+00h]
0x1400736f6  lea     rsi, [rbp+10h]
0x1400736fa  mov     rbx, rax
0x1400736fd  test    rax, rax
0x140073700  jnz     loc_140073A42
0x140073706  mov     rcx, rsi; ListHead
0x140073709  call    cs:__imp_ExpInterlockedFlushSList
0x140073710  nop     dword ptr [rax+rax+00h]
0x140073715  mov     rcx, rax
0x140073718  test    rax, rax
0x14007371b  jz      loc_140073840
0x140073721  mov     rdx, [rax]
0x140073724  mov     rbx, rax
0x140073727  test    rdx, rdx
0x14007372a  jz      loc_140073A45
0x140073730  xor     r9d, r9d
0x140073733  mov     rax, [rdx]
0x140073736  inc     r9d; Count
0x140073739  mov     [rdx], rbx
0x14007373c  mov     rdx, rax
0x14007373f  mov     rbx, [rcx]
0x140073742  mov     [rcx], rax
0x140073745  test    rax, rax
0x140073748  jnz     short loc_140073733
0x14007374a  mov     rdx, [rbx]; List
0x14007374d  mov     r8, rcx; ListEnd
0x140073750  mov     rcx, rbp; ListHead
0x140073753  call    cs:__imp_InterlockedPushListSList
0x14007375a  nop     dword ptr [rax+rax+00h]
0x14007375f  mov     rcx, rbx
0x140073762  mov     al, 1
0x140073764  test    rbx, rbx
0x140073767  jz      loc_140073840
0x14007376d  cmp     qword ptr [rcx], 0
0x140073771  jz      short loc_140073784
0x140073773  test    dil, dil
0x140073776  jnz     loc_1400738B9
0x14007377c  test    al, al
0x14007377e  jnz     loc_1400738AC
0x140073784  mov     edx, 1
0x140073789  test    r13b, r13b
0x14007378c  jnz     loc_1400739F8
0x140073792  lea     rcx, [rbp+0C0h]
0x140073799  cmp     rcx, rbx
0x14007379c  jz      loc_140073999
0x1400737a2  xor     r12b, r12b
0x1400737a5  test    r14b, r14b
0x1400737a8  jnz     loc_140073963
0x1400737ae  mov     rax, [rbx+10h]
0x1400737b2  mov     rcx, [rbx+18h]
0x1400737b6  call    _guard_dispatch_icall
0x1400737bb  inc     r15d
0x1400737be  cmp     r15d, 4000h
0x1400737c5  jnz     loc_1400736E1
0x1400737cb  movzx   ecx, word ptr [rbp+0E8h]; NodeNumber
0x1400737d2  lea     rdx, [rsp+0C8h+Affinity]; Affinity
0x1400737d7  xorps   xmm0, xmm0
0x1400737da  xor     r8d, r8d; Count
0x1400737dd  movups  xmmword ptr [rsp+0C8h+Affinity.Mask], xmm0
0x1400737e2  call    cs:__imp_KeQueryNodeActiveAffinity
0x1400737e9  nop     dword ptr [rax+rax+00h]
0x1400737ee  mov     rax, [rsp+0C8h+Affinity.Mask]
0x1400737f3  cmp     [rsp+0C8h+var_78], rax
0x1400737f8  jnz     short loc_14007380A
0x1400737fa  movzx   ecx, [rsp+0C8h+var_98]
0x1400737ff  cmp     cx, [rsp+0C8h+Affinity.Group]
0x140073804  jz      loc_1400736DE
0x14007380a  test    rax, rax
0x14007380d  jz      loc_1400736DE
0x140073813  xor     edx, edx; PreviousAffinity
0x140073815  lea     rcx, [rsp+0C8h+Affinity]; Affinity
0x14007381a  call    cs:__imp_KeSetSystemGroupAffinityThread
0x140073821  nop     dword ptr [rax+rax+00h]
0x140073826  movaps  xmm0, xmmword ptr [rsp+0C8h+Affinity.Mask]
0x14007382b  pextrw  eax, xmm0, 4
0x140073830  movsd   [rsp+0C8h+var_78], xmm0
0x140073836  mov     [rsp+0C8h+var_98], ax
0x14007383b  jmp     loc_1400736DE
0x140073840  mov     ecx, 1
0x140073845  mov     eax, ecx
0x140073847  lock xadd [rbp+42h], ax
0x14007384d  inc     ax
0x140073850  cmp     cx, ax
0x140073853  jz      short loc_1400738C6
0x140073855  mov     qword ptr [rsp+0C8h+var_88], 0FFFFFFFFEE1E5D00h
0x14007385e  lea     rax, [rsp+0C8h+var_88]
0x140073863  lea     rcx, [rbp+48h]; Object
0x140073867  mov     [rsp+0C8h+Timeout], rax; Timeout
0x14007386c  xor     r9d, r9d; Alertable
0x14007386f  xor     r8d, r8d; WaitMode
0x140073872  xor     edx, edx; WaitReason
0x140073874  call    cs:__imp_KeWaitForSingleObject
0x14007387b  nop     dword ptr [rax+rax+00h]
0x140073880  mov     ecx, 0FFFFFFFFh
0x140073885  lock xadd [rbp+42h], cx
0x14007388b  cmp     cx, 1
0x14007388f  jz      short loc_1400738A4
0x140073891  cmp     eax, 102h
0x140073896  jz      loc_1400739D1
0x14007389c  mov     dil, 1
0x14007389f  jmp     loc_1400736E7
0x1400738a4  mov     r14b, 1
0x1400738a7  jmp     loc_1400736E7
0x1400738ac  movzx   eax, word ptr [rbp+42h]
0x1400738b0  test    ax, ax
0x1400738b3  jz      loc_140073784
0x1400738b9  mov     rcx, rbp
0x1400738bc  call    RfspThreadPoolNodeWakeIdleWorker
0x1400738c1  jmp     loc_140073784
0x1400738c6  mov     rcx, rbp; ListHead
0x1400738c9  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400738d0  nop     dword ptr [rax+rax+00h]
0x1400738d5  mov     rbx, rax
0x1400738d8  test    rax, rax
0x1400738db  jnz     loc_140073A2C
0x1400738e1  mov     rcx, rsi; ListHead
0x1400738e4  call    cs:__imp_ExpInterlockedFlushSList
0x1400738eb  nop     dword ptr [rax+rax+00h]
0x1400738f0  mov     rdx, rax
0x1400738f3  test    rax, rax
0x1400738f6  jz      loc_140073A1E
0x1400738fc  mov     rcx, [rax]
0x1400738ff  mov     rbx, rax
0x140073902  test    rcx, rcx
0x140073905  jz      short loc_140073942
0x140073907  xor     r9d, r9d
0x14007390a  mov     rax, [rcx]
0x14007390d  inc     r9d; Count
0x140073910  mov     [rcx], rbx
0x140073913  mov     rcx, rax
0x140073916  mov     rbx, [rdx]
0x140073919  mov     [rdx], rax
0x14007391c  test    rax, rax
0x14007391f  jnz     short loc_14007390A
0x140073921  mov     r8, rdx; ListEnd
0x140073924  mov     rcx, rbp; ListHead
0x140073927  mov     rdx, [rbx]; List
0x14007392a  call    cs:__imp_InterlockedPushListSList
0x140073931  nop     dword ptr [rax+rax+00h]
0x140073936  mov     rdx, rbx
0x140073939  test    rbx, rbx
0x14007393c  jz      loc_140073A1E
0x140073942  mov     ecx, 0FFFFFFFFh
0x140073947  lock xadd [rbp+42h], cx
0x14007394d  dec     cx
0x140073950  xor     eax, eax
0x140073952  cmp     ax, cx
0x140073955  jnz     loc_140073A34
0x14007395b  mov     r14b, 1
0x14007395e  jmp     loc_140073784
0x140073963  movzx   eax, word ptr [rbp+40h]
0x140073967  cmp     ax, [rsp+0C8h+var_90]
0x14007396c  jnb     loc_1400737AE
0x140073972  xor     eax, eax
0x140073974  lock cmpxchg [rbp+44h], edx
0x140073979  jnz     loc_1400737AE
0x14007397f  lea     rcx, [rbp+60h]; Event
0x140073983  xor     r8d, r8d; Wait
0x140073986  xor     edx, edx; Increment
0x140073988  call    cs:__imp_KeSetEvent
0x14007398f  nop     dword ptr [rax+rax+00h]
0x140073994  jmp     loc_1400737AE
0x140073999  xor     edi, edi
0x14007399b  movzx   eax, r12b
0x14007399f  cmp     [rbx], rdi
0x1400739a2  mov     rdx, rcx; ListEntry
0x1400739a5  mov     rcx, rsi; ListHead
0x1400739a8  cmovz   edi, eax
0x1400739ab  call    cs:__imp_ExpInterlockedPushEntrySList
0x1400739b2  nop     dword ptr [rax+rax+00h]
0x1400739b7  lea     rcx, [rbp+48h]; Event
0x1400739bb  xor     r8d, r8d; Wait
0x1400739be  xor     edx, edx; Increment
0x1400739c0  call    cs:__imp_KeSetEvent
0x1400739c7  nop     dword ptr [rax+rax+00h]
0x1400739cc  test    dil, dil
0x1400739cf  jz      short loc_140073A16
0x1400739d1  test    r13b, r13b
0x1400739d4  jnz     short loc_140073A25
0x1400739d6  mov     rcx, [rsp+0C8h+var_58]
0x1400739db  xor     rcx, rsp; StackCookie
0x1400739de  call    __security_check_cookie
0x1400739e3  add     rsp, 88h
0x1400739ea  pop     r15
0x1400739ec  pop     r14
0x1400739ee  pop     r13
0x1400739f0  pop     r12
0x1400739f2  pop     rdi
0x1400739f3  pop     rsi
0x1400739f4  pop     rbp
0x1400739f5  pop     rbx
0x1400739f6  retn
0x1400739f8  xor     eax, eax
0x1400739fa  movzx   r14d, r14b
0x1400739fe  xchg    eax, [rbp+44h]
0x140073a01  movzx   eax, word ptr [rbp+42h]
0x140073a05  xor     r13b, r13b
0x140073a08  xor     ecx, ecx
0x140073a0a  cmp     cx, ax
0x140073a0d  cmovz   r14d, edx
0x140073a11  jmp     loc_140073792
0x140073a16  mov     r12b, 1
0x140073a19  jmp     loc_1400736E1
0x140073a1e  xor     eax, eax
0x140073a20  jmp     loc_140073863
0x140073a25  xor     eax, eax
0x140073a27  xchg    eax, [rbp+44h]
0x140073a2a  jmp     short loc_1400739D6
0x140073a2c  mov     rdx, rax
0x140073a2f  jmp     loc_140073942
0x140073a34  cmp     [rdx], rax
0x140073a37  jnz     loc_1400738B9
0x140073a3d  jmp     loc_140073784
0x140073a42  mov     rcx, rbx
0x140073a45  xor     al, al
0x140073a47  jmp     loc_14007376D
```
