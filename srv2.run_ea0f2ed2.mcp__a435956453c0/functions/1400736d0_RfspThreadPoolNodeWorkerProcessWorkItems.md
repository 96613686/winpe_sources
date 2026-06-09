# RfspThreadPoolNodeWorkerProcessWorkItems

- ea: `0x1400736d0`
- end: `0x140073a9c`
- name: `RfspThreadPoolNodeWorkerProcessWorkItems`
- size: `972`
- prototype: `EXPAND_STACK_CALLOUT`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140073500`

## callees

- `0x140004960`
- `0x140038490`
- `0x1400384d0`
- `0x1400736d0`

## import_xrefs

- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x140073832`
- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x140073832`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14007386a`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14007386a`
- `ntoskrnl!KeSetEvent` at `0x1400739d8`
- `ntoskrnl!KeSetEvent` at `0x140073a10`
- `ntoskrnl!KeSetEvent` at `0x1400739d8`
- `ntoskrnl!KeSetEvent` at `0x140073a10`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400738c4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400738c4`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x140073759`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x140073934`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x140073759`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x140073934`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14007373a`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140073919`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14007373a`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140073919`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400739fb`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400739fb`
- `ntoskrnl!InterlockedPushListSList` at `0x1400737a3`
- `ntoskrnl!InterlockedPushListSList` at `0x14007397a`
- `ntoskrnl!InterlockedPushListSList` at `0x1400737a3`
- `ntoskrnl!InterlockedPushListSList` at `0x14007397a`

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
0x1400736d0  push    rbx
0x1400736d2  push    rbp
0x1400736d3  push    rsi
0x1400736d4  push    rdi
0x1400736d5  push    r12
0x1400736d7  push    r13
0x1400736d9  push    r14
0x1400736db  push    r15
0x1400736dd  sub     rsp, 88h
0x1400736e4  mov     rax, cs:__security_cookie
0x1400736eb  xor     rax, rsp
0x1400736ee  mov     [rsp+0C8h+var_58], rax
0x1400736f3  mov     rbp, [rcx+10h]
0x1400736f7  xorps   xmm0, xmm0
0x1400736fa  movups  xmmword ptr [rsp+0C8h+Affinity.Mask], xmm0
0x1400736ff  mov     qword ptr [rsp+0C8h+var_88], 0
0x140073708  xor     r12b, r12b
0x14007370b  mov     r13b, 1
0x14007370e  movzx   eax, word ptr [rbp+0EAh]
0x140073715  mov     [rsp+0C8h+var_90], ax
0x14007371a  movzx   eax, [rsp+0C8h+Affinity.Group]
0x14007371f  mov     [rsp+0C8h+var_98], ax
0x140073724  mov     rax, [rsp+0C8h+Affinity.Mask]
0x140073729  mov     [rsp+0C8h+var_78], rax
0x14007372e  xor     r15d, r15d
0x140073731  xor     r14b, r14b
0x140073734  xor     dil, dil
0x140073737  mov     rcx, rbp; ListHead
0x14007373a  call    cs:__imp_ExpInterlockedPopEntrySList
0x140073741  nop     dword ptr [rax+rax+00h]
0x140073746  lea     rsi, [rbp+10h]
0x14007374a  mov     rbx, rax
0x14007374d  test    rax, rax
0x140073750  jnz     loc_140073A92
0x140073756  mov     rcx, rsi; ListHead
0x140073759  call    cs:__imp_ExpInterlockedFlushSList
0x140073760  nop     dword ptr [rax+rax+00h]
0x140073765  mov     rcx, rax
0x140073768  test    rax, rax
0x14007376b  jz      loc_140073890
0x140073771  mov     rdx, [rax]
0x140073774  mov     rbx, rax
0x140073777  test    rdx, rdx
0x14007377a  jz      loc_140073A95
0x140073780  xor     r9d, r9d
0x140073783  mov     rax, [rdx]
0x140073786  inc     r9d; Count
0x140073789  mov     [rdx], rbx
0x14007378c  mov     rdx, rax
0x14007378f  mov     rbx, [rcx]
0x140073792  mov     [rcx], rax
0x140073795  test    rax, rax
0x140073798  jnz     short loc_140073783
0x14007379a  mov     rdx, [rbx]; List
0x14007379d  mov     r8, rcx; ListEnd
0x1400737a0  mov     rcx, rbp; ListHead
0x1400737a3  call    cs:__imp_InterlockedPushListSList
0x1400737aa  nop     dword ptr [rax+rax+00h]
0x1400737af  mov     rcx, rbx
0x1400737b2  mov     al, 1
0x1400737b4  test    rbx, rbx
0x1400737b7  jz      loc_140073890
0x1400737bd  cmp     qword ptr [rcx], 0
0x1400737c1  jz      short loc_1400737D4
0x1400737c3  test    dil, dil
0x1400737c6  jnz     loc_140073909
0x1400737cc  test    al, al
0x1400737ce  jnz     loc_1400738FC
0x1400737d4  mov     edx, 1
0x1400737d9  test    r13b, r13b
0x1400737dc  jnz     loc_140073A48
0x1400737e2  lea     rcx, [rbp+0C0h]
0x1400737e9  cmp     rcx, rbx
0x1400737ec  jz      loc_1400739E9
0x1400737f2  xor     r12b, r12b
0x1400737f5  test    r14b, r14b
0x1400737f8  jnz     loc_1400739B3
0x1400737fe  mov     rax, [rbx+10h]
0x140073802  mov     rcx, [rbx+18h]
0x140073806  call    _guard_dispatch_icall
0x14007380b  inc     r15d
0x14007380e  cmp     r15d, 4000h
0x140073815  jnz     loc_140073731
0x14007381b  movzx   ecx, word ptr [rbp+0E8h]; NodeNumber
0x140073822  lea     rdx, [rsp+0C8h+Affinity]; Affinity
0x140073827  xorps   xmm0, xmm0
0x14007382a  xor     r8d, r8d; Count
0x14007382d  movups  xmmword ptr [rsp+0C8h+Affinity.Mask], xmm0
0x140073832  call    cs:__imp_KeQueryNodeActiveAffinity
0x140073839  nop     dword ptr [rax+rax+00h]
0x14007383e  mov     rax, [rsp+0C8h+Affinity.Mask]
0x140073843  cmp     [rsp+0C8h+var_78], rax
0x140073848  jnz     short loc_14007385A
0x14007384a  movzx   ecx, [rsp+0C8h+var_98]
0x14007384f  cmp     cx, [rsp+0C8h+Affinity.Group]
0x140073854  jz      loc_14007372E
0x14007385a  test    rax, rax
0x14007385d  jz      loc_14007372E
0x140073863  xor     edx, edx; PreviousAffinity
0x140073865  lea     rcx, [rsp+0C8h+Affinity]; Affinity
0x14007386a  call    cs:__imp_KeSetSystemGroupAffinityThread
0x140073871  nop     dword ptr [rax+rax+00h]
0x140073876  movaps  xmm0, xmmword ptr [rsp+0C8h+Affinity.Mask]
0x14007387b  pextrw  eax, xmm0, 4
0x140073880  movsd   [rsp+0C8h+var_78], xmm0
0x140073886  mov     [rsp+0C8h+var_98], ax
0x14007388b  jmp     loc_14007372E
0x140073890  mov     ecx, 1
0x140073895  mov     eax, ecx
0x140073897  lock xadd [rbp+42h], ax
0x14007389d  inc     ax
0x1400738a0  cmp     cx, ax
0x1400738a3  jz      short loc_140073916
0x1400738a5  mov     qword ptr [rsp+0C8h+var_88], 0FFFFFFFFEE1E5D00h
0x1400738ae  lea     rax, [rsp+0C8h+var_88]
0x1400738b3  lea     rcx, [rbp+48h]; Object
0x1400738b7  mov     [rsp+0C8h+Timeout], rax; Timeout
0x1400738bc  xor     r9d, r9d; Alertable
0x1400738bf  xor     r8d, r8d; WaitMode
0x1400738c2  xor     edx, edx; WaitReason
0x1400738c4  call    cs:__imp_KeWaitForSingleObject
0x1400738cb  nop     dword ptr [rax+rax+00h]
0x1400738d0  mov     ecx, 0FFFFFFFFh
0x1400738d5  lock xadd [rbp+42h], cx
0x1400738db  cmp     cx, 1
0x1400738df  jz      short loc_1400738F4
0x1400738e1  cmp     eax, 102h
0x1400738e6  jz      loc_140073A21
0x1400738ec  mov     dil, 1
0x1400738ef  jmp     loc_140073737
0x1400738f4  mov     r14b, 1
0x1400738f7  jmp     loc_140073737
0x1400738fc  movzx   eax, word ptr [rbp+42h]
0x140073900  test    ax, ax
0x140073903  jz      loc_1400737D4
0x140073909  mov     rcx, rbp
0x14007390c  call    RfspThreadPoolNodeWakeIdleWorker
0x140073911  jmp     loc_1400737D4
0x140073916  mov     rcx, rbp; ListHead
0x140073919  call    cs:__imp_ExpInterlockedPopEntrySList
0x140073920  nop     dword ptr [rax+rax+00h]
0x140073925  mov     rbx, rax
0x140073928  test    rax, rax
0x14007392b  jnz     loc_140073A7C
0x140073931  mov     rcx, rsi; ListHead
0x140073934  call    cs:__imp_ExpInterlockedFlushSList
0x14007393b  nop     dword ptr [rax+rax+00h]
0x140073940  mov     rdx, rax
0x140073943  test    rax, rax
0x140073946  jz      loc_140073A6E
0x14007394c  mov     rcx, [rax]
0x14007394f  mov     rbx, rax
0x140073952  test    rcx, rcx
0x140073955  jz      short loc_140073992
0x140073957  xor     r9d, r9d
0x14007395a  mov     rax, [rcx]
0x14007395d  inc     r9d; Count
0x140073960  mov     [rcx], rbx
0x140073963  mov     rcx, rax
0x140073966  mov     rbx, [rdx]
0x140073969  mov     [rdx], rax
0x14007396c  test    rax, rax
0x14007396f  jnz     short loc_14007395A
0x140073971  mov     r8, rdx; ListEnd
0x140073974  mov     rcx, rbp; ListHead
0x140073977  mov     rdx, [rbx]; List
0x14007397a  call    cs:__imp_InterlockedPushListSList
0x140073981  nop     dword ptr [rax+rax+00h]
0x140073986  mov     rdx, rbx
0x140073989  test    rbx, rbx
0x14007398c  jz      loc_140073A6E
0x140073992  mov     ecx, 0FFFFFFFFh
0x140073997  lock xadd [rbp+42h], cx
0x14007399d  dec     cx
0x1400739a0  xor     eax, eax
0x1400739a2  cmp     ax, cx
0x1400739a5  jnz     loc_140073A84
0x1400739ab  mov     r14b, 1
0x1400739ae  jmp     loc_1400737D4
0x1400739b3  movzx   eax, word ptr [rbp+40h]
0x1400739b7  cmp     ax, [rsp+0C8h+var_90]
0x1400739bc  jnb     loc_1400737FE
0x1400739c2  xor     eax, eax
0x1400739c4  lock cmpxchg [rbp+44h], edx
0x1400739c9  jnz     loc_1400737FE
0x1400739cf  lea     rcx, [rbp+60h]; Event
0x1400739d3  xor     r8d, r8d; Wait
0x1400739d6  xor     edx, edx; Increment
0x1400739d8  call    cs:__imp_KeSetEvent
0x1400739df  nop     dword ptr [rax+rax+00h]
0x1400739e4  jmp     loc_1400737FE
0x1400739e9  xor     edi, edi
0x1400739eb  movzx   eax, r12b
0x1400739ef  cmp     [rbx], rdi
0x1400739f2  mov     rdx, rcx; ListEntry
0x1400739f5  mov     rcx, rsi; ListHead
0x1400739f8  cmovz   edi, eax
0x1400739fb  call    cs:__imp_ExpInterlockedPushEntrySList
0x140073a02  nop     dword ptr [rax+rax+00h]
0x140073a07  lea     rcx, [rbp+48h]; Event
0x140073a0b  xor     r8d, r8d; Wait
0x140073a0e  xor     edx, edx; Increment
0x140073a10  call    cs:__imp_KeSetEvent
0x140073a17  nop     dword ptr [rax+rax+00h]
0x140073a1c  test    dil, dil
0x140073a1f  jz      short loc_140073A66
0x140073a21  test    r13b, r13b
0x140073a24  jnz     short loc_140073A75
0x140073a26  mov     rcx, [rsp+0C8h+var_58]
0x140073a2b  xor     rcx, rsp; StackCookie
0x140073a2e  call    __security_check_cookie
0x140073a33  add     rsp, 88h
0x140073a3a  pop     r15
0x140073a3c  pop     r14
0x140073a3e  pop     r13
0x140073a40  pop     r12
0x140073a42  pop     rdi
0x140073a43  pop     rsi
0x140073a44  pop     rbp
0x140073a45  pop     rbx
0x140073a46  retn
0x140073a48  xor     eax, eax
0x140073a4a  movzx   r14d, r14b
0x140073a4e  xchg    eax, [rbp+44h]
0x140073a51  movzx   eax, word ptr [rbp+42h]
0x140073a55  xor     r13b, r13b
0x140073a58  xor     ecx, ecx
0x140073a5a  cmp     cx, ax
0x140073a5d  cmovz   r14d, edx
0x140073a61  jmp     loc_1400737E2
0x140073a66  mov     r12b, 1
0x140073a69  jmp     loc_140073731
0x140073a6e  xor     eax, eax
0x140073a70  jmp     loc_1400738B3
0x140073a75  xor     eax, eax
0x140073a77  xchg    eax, [rbp+44h]
0x140073a7a  jmp     short loc_140073A26
0x140073a7c  mov     rdx, rax
0x140073a7f  jmp     loc_140073992
0x140073a84  cmp     [rdx], rax
0x140073a87  jnz     loc_140073909
0x140073a8d  jmp     loc_1400737D4
0x140073a92  mov     rcx, rbx
0x140073a95  xor     al, al
0x140073a97  jmp     loc_1400737BD
```
