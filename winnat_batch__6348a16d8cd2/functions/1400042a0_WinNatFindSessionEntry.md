# WinNatFindSessionEntry

- ea: `0x1400042a0`
- end: `0x14000463f`
- name: `WinNatFindSessionEntry`
- size: `927`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400020e0`
- `0x14000425c`
- `0x14001c4e4`
- `0x14001cef8`

## callees

- `0x1400042a0`
- `0x14000caa0`
- `0x14001f020`

## import_xrefs

- `ntoskrnl!KeTestSpinLock` at `0x140004313`
- `ntoskrnl!KeTestSpinLock` at `0x140004313`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000432e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000432e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140004342`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140004342`
- `ntoskrnl!KeLowerIrql` at `0x14000461e`
- `ntoskrnl!KeLowerIrql` at `0x14000461e`
- `ntoskrnl!KfRaiseIrql` at `0x1400042c8`
- `ntoskrnl!KfRaiseIrql` at `0x1400042c8`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140004458`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140004458`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400045b8`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400045b8`
- `NETIO!RtlComputeToeplitzHash` at `0x140004392`
- `NETIO!RtlComputeToeplitzHash` at `0x1400043b1`
- `NETIO!RtlComputeToeplitzHash` at `0x1400043e6`
- `NETIO!RtlComputeToeplitzHash` at `0x140004406`
- `NETIO!RtlComputeToeplitzHash` at `0x140004392`
- `NETIO!RtlComputeToeplitzHash` at `0x1400043b1`
- `NETIO!RtlComputeToeplitzHash` at `0x1400043e6`
- `NETIO!RtlComputeToeplitzHash` at `0x140004406`

## pseudocode

```c
volatile signed __int64 *__fastcall WinNatFindSessionEntry(
        __int64 a1,
        int a2,
        _WORD *a3,
        _WORD *a4,
        unsigned __int8 a5,
        char a6)
{
  __int64 v7; // r13
  volatile signed __int32 *v10; // rbx
  __int64 v11; // rsi
  __int64 v12; // r8
  volatile signed __int64 *v13; // rbp
  __int64 v14; // rdx
  bool v15; // zf
  int v16; // ebx
  int v17; // eax
  __int64 v18; // r8
  __int64 v19; // rdx
  int v20; // ebx
  ULONG_PTR v21; // rdx
  __int64 v22; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY i; // rax
  __int64 v24; // rdx
  __int64 v25; // r9
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v26; // rsi
  int v27; // r8d
  _WORD *Signature; // rdx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v29; // rbx
  struct _LIST_ENTRY *Flink; // rcx
  _WORD *v31; // rdx
  struct _LIST_ENTRY *v32; // rdi
  struct _LIST_ENTRY *Blink; // rcx
  int v34; // eax
  size_t v35; // r8
  __int64 v36; // rcx
  const void *v37; // rdx
  size_t v38; // r8
  __int64 v39; // rcx
  __int64 v40; // rbp
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-68h] BYREF
  struct _RTL_DYNAMIC_HASH_TABLE *HashTablea; // [rsp+90h] [rbp+8h]
  KIRQL v46; // [rsp+A0h] [rbp+18h]
  unsigned int LockArray_high; // [rsp+A8h] [rbp+20h]

  v7 = a1 + 64;
  v46 = KfRaiseIrql(2u);
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v10 = (volatile signed __int32 *)(v7 + (((LockArray_high & *(_DWORD *)(v7 + 8)) + 1LL) << 6));
  memset(&LockHandle, 0, sizeof(LockHandle));
  _InterlockedIncrement(v10);
  if ( !KeTestSpinLock((PKSPIN_LOCK)v7) )
  {
    _InterlockedDecrement(v10);
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)v7, &LockHandle);
    _InterlockedIncrement(v10);
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  }
  v11 = a1 + 408;
  v12 = 4;
  v13 = 0;
  v14 = 2;
  v15 = *a3 == 2;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( !v15 )
  {
    v14 = 4;
    v12 = 16;
  }
  v16 = RtlComputeToeplitzHash(a1 + 408, &a3[v14], v12, 0);
  v17 = RtlComputeToeplitzHash(a1 + 408, a3 + 1, 2, 0);
  v18 = 4;
  v19 = 2;
  if ( *a4 != 2 )
  {
    v19 = 4;
    v18 = 16;
  }
  v20 = v16 ^ v17 ^ RtlComputeToeplitzHash(v11, &a4[v19], v18, 0);
  v21 = v20 ^ (unsigned int)RtlComputeToeplitzHash(v11, a4 + 1, 2, 0) | 0x80000000;
  v22 = 384;
  if ( !a6 )
    v22 = 392;
  HashTablea = *(struct _RTL_DYNAMIC_HASH_TABLE **)(v22 + a1);
  LockHandle.LockQueue = 0;
  for ( i = RtlLookupEntryHashTable(HashTablea, v21, (PRTL_DYNAMIC_HASH_TABLE_CONTEXT)&LockHandle);
        ;
        i = RtlGetNextEntryHashTable(HashTablea, (PRTL_DYNAMIC_HASH_TABLE_CONTEXT)&LockHandle) )
  {
    v26 = i;
    if ( !i )
      break;
    v27 = a5;
    if ( a6 )
    {
      Signature = (_WORD *)i[-4].Signature;
      v29 = i - 7;
      Flink = i[-3].Linkage.Flink->Flink;
      if ( *Signature != (_WORD)Flink )
      {
        MicrosoftTelemetryAssertTriggeredNoArgsKM(Flink, Signature, a5, v25);
        v27 = a5;
      }
      v31 = (_WORD *)v29[3].Signature;
      v32 = v29[4].Linkage.Flink;
    }
    else
    {
      v29 = i - 8;
      Blink = i[-4].Linkage.Blink;
      if ( LOWORD(Blink->Flink) != *(_WORD *)i[-4].Signature )
      {
        MicrosoftTelemetryAssertTriggeredNoArgsKM(Blink, v24, a5, v25);
        v27 = a5;
      }
      v32 = v29[4].Linkage.Blink;
      v31 = (_WORD *)v29[4].Signature;
    }
    v34 = (int)v29[5].Linkage.Flink;
    if ( (v34 == v27 || v34 == 58 && a5 == 1) && *a3 == *v31 && a3[1] == v31[1] )
    {
      v35 = 4;
      if ( *v31 != 2 )
        v35 = 16;
      v36 = 2;
      v37 = v31 + 2;
      if ( *a3 != 2 )
        v36 = 4;
      if ( !memcmp(&a3[v36], v37, v35) && *a4 == LOWORD(v32->Flink) && a4[1] == WORD1(v32->Flink) )
      {
        v38 = 4;
        if ( LOWORD(v32->Flink) != 2 )
          v38 = 16;
        v39 = 2;
        if ( *a4 != 2 )
          v39 = 4;
        if ( !memcmp(&a4[v39], (char *)&v32->Flink + 4, v38) && (!a6 || a2 == LODWORD(v29->Linkage.Blink)) )
        {
          v40 = -168;
          if ( !a6 )
            v40 = -192;
          v13 = (volatile signed __int64 *)((char *)v26 + v40);
          if ( v13 && _InterlockedIncrement64(v13) <= 1 )
            __fastfail(0xEu);
          break;
        }
      }
    }
    v13 = 0;
  }
  _InterlockedDecrement((volatile signed __int32 *)((((LockArray_high & *(_DWORD *)(v7 + 8)) + 1LL) << 6) + v7));
  KeLowerIrql(v46);
  return v13;
}

```

## disassembly

```asm
0x1400042a0  mov     [rsp+arg_8], edx
0x1400042a4  mov     [rsp+HashTable], rcx
0x1400042a9  push    rbx
0x1400042aa  push    rbp
0x1400042ab  push    rsi
0x1400042ac  push    rdi
0x1400042ad  push    r12
0x1400042af  push    r13
0x1400042b1  push    r14
0x1400042b3  push    r15
0x1400042b5  sub     rsp, 48h
0x1400042b9  mov     rdi, rcx
0x1400042bc  lea     r13, [rcx+40h]
0x1400042c0  mov     cl, 2; NewIrql
0x1400042c2  mov     r15, r9
0x1400042c5  mov     r12, r8
0x1400042c8  call    cs:__imp_KfRaiseIrql
0x1400042cf  nop     dword ptr [rax+rax+00h]
0x1400042d4  mov     ecx, gs:1A4h
0x1400042dc  xorps   xmm0, xmm0
0x1400042df  mov     ebx, [r13+8]
0x1400042e3  mov     [rsp+88h+arg_10], al
0x1400042ea  xor     eax, eax
0x1400042ec  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x1400042f1  mov     eax, ecx
0x1400042f3  and     rbx, rax
0x1400042f6  mov     [rsp+88h+arg_18], rax
0x1400042fe  inc     rbx
0x140004301  shl     rbx, 6
0x140004305  add     rbx, r13
0x140004308  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x14000430d  lock inc dword ptr [rbx]
0x140004310  mov     rcx, r13; SpinLock
0x140004313  call    cs:__imp_KeTestSpinLock
0x14000431a  nop     dword ptr [rax+rax+00h]
0x14000431f  test    al, al
0x140004321  jnz     short loc_14000434E
0x140004323  lock dec dword ptr [rbx]
0x140004326  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x14000432b  mov     rcx, r13; SpinLock
0x14000432e  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140004335  nop     dword ptr [rax+rax+00h]
0x14000433a  lock inc dword ptr [rbx]
0x14000433d  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x140004342  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140004349  nop     dword ptr [rax+rax+00h]
0x14000434e  xor     eax, eax
0x140004350  lea     rsi, [rdi+198h]
0x140004357  mov     ecx, 8
0x14000435c  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x140004361  mov     r8d, 4
0x140004367  xorps   xmm0, xmm0
0x14000436a  xor     ebp, ebp
0x14000436c  mov     edx, 4
0x140004371  cmp     word ptr [r12], 2
0x140004377  mov     r14d, 10h
0x14000437d  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x140004382  cmovnz  edx, ecx
0x140004385  cmovnz  r8d, r14d
0x140004389  add     rdx, r12
0x14000438c  xor     r9d, r9d
0x14000438f  mov     rcx, rsi
0x140004392  call    cs:__imp_RtlComputeToeplitzHash
0x140004399  nop     dword ptr [rax+rax+00h]
0x14000439e  lea     rdx, [r12+2]
0x1400043a3  xor     r9d, r9d
0x1400043a6  mov     r8d, 2
0x1400043ac  mov     rcx, rsi
0x1400043af  mov     ebx, eax
0x1400043b1  call    cs:__imp_RtlComputeToeplitzHash
0x1400043b8  nop     dword ptr [rax+rax+00h]
0x1400043bd  mov     r8d, 4
0x1400043c3  mov     edx, 4
0x1400043c8  mov     edi, eax
0x1400043ca  mov     rcx, rsi
0x1400043cd  mov     eax, 8
0x1400043d2  xor     edi, ebx
0x1400043d4  cmp     word ptr [r15], 2
0x1400043d9  cmovnz  edx, eax
0x1400043dc  cmovnz  r8d, r14d
0x1400043e0  add     rdx, r15
0x1400043e3  xor     r9d, r9d
0x1400043e6  call    cs:__imp_RtlComputeToeplitzHash
0x1400043ed  nop     dword ptr [rax+rax+00h]
0x1400043f2  lea     rdx, [r15+2]
0x1400043f6  xor     r9d, r9d
0x1400043f9  mov     ebx, eax
0x1400043fb  mov     r8d, 2
0x140004401  mov     rcx, rsi
0x140004404  xor     ebx, edi
0x140004406  call    cs:__imp_RtlComputeToeplitzHash
0x14000440d  nop     dword ptr [rax+rax+00h]
0x140004412  movzx   r14d, [rsp+88h+arg_28]
0x14000441b  lea     r8, [rsp+88h+LockHandle]; Context
0x140004420  xor     eax, ebx
0x140004422  mov     ecx, 188h
0x140004427  bts     eax, 1Fh
0x14000442b  xorps   xmm0, xmm0
0x14000442e  mov     edx, eax; Signature
0x140004430  test    r14b, r14b
0x140004433  mov     eax, 180h
0x140004438  cmovz   eax, ecx
0x14000443b  mov     rcx, [rsp+88h+HashTable]
0x140004443  mov     rax, [rax+rcx]
0x140004447  mov     rcx, rax; HashTable
0x14000444a  mov     [rsp+88h+HashTable], rax
0x140004452  movdqu  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x140004458  call    cs:__imp_RtlLookupEntryHashTable
0x14000445f  nop     dword ptr [rax+rax+00h]
0x140004464  mov     rsi, rax
0x140004467  test    rax, rax
0x14000446a  jz      loc_1400045FE
0x140004470  movzx   r8d, [rsp+88h+arg_20]
0x140004479  test    r14b, r14b
0x14000447c  jz      short loc_1400044AD
0x14000447e  mov     rdx, [rax-50h]
0x140004482  lea     rbx, [rax-0A8h]
0x140004489  mov     rax, [rax-48h]
0x14000448d  movzx   ecx, word ptr [rax]
0x140004490  cmp     [rdx], cx
0x140004493  jz      short loc_1400044A3
0x140004495  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000449a  movzx   r8d, [rsp+88h+arg_20]
0x1400044a3  mov     rdx, [rbx+58h]
0x1400044a7  mov     rdi, [rbx+60h]
0x1400044ab  jmp     short loc_1400044DA
0x1400044ad  mov     rax, [rsi-50h]
0x1400044b1  lea     rbx, [rsi-0C0h]
0x1400044b8  mov     rcx, [rbx+68h]
0x1400044bc  movzx   eax, word ptr [rax]
0x1400044bf  cmp     [rcx], ax
0x1400044c2  jz      short loc_1400044D2
0x1400044c4  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400044c9  movzx   r8d, [rsp+88h+arg_20]
0x1400044d2  mov     rdi, [rbx+68h]
0x1400044d6  mov     rdx, [rbx+70h]
0x1400044da  mov     eax, [rbx+78h]
0x1400044dd  cmp     eax, r8d
0x1400044e0  jz      short loc_1400044F9
0x1400044e2  cmp     eax, 3Ah ; ':'
0x1400044e5  jnz     loc_1400045A9
0x1400044eb  cmp     [rsp+88h+arg_20], 1
0x1400044f3  jnz     loc_1400045A9
0x1400044f9  movzx   ecx, word ptr [rdx]
0x1400044fc  movzx   r9d, word ptr [r12]
0x140004501  cmp     r9w, cx
0x140004505  jnz     loc_1400045A9
0x14000450b  movzx   eax, word ptr [rdx+2]
0x14000450f  cmp     [r12+2], ax
0x140004515  jnz     loc_1400045A9
0x14000451b  cmp     cx, 2
0x14000451f  mov     eax, 8
0x140004524  mov     r8d, 4
0x14000452a  mov     ebp, 10h
0x14000452f  cmovnz  r8d, ebp; Size
0x140004533  mov     ecx, 4
0x140004538  add     rdx, 4; Buf2
0x14000453c  cmp     r9w, 2
0x140004541  cmovnz  ecx, eax
0x140004544  add     rcx, r12; Buf1
0x140004547  call    memcmp
0x14000454c  test    eax, eax
0x14000454e  jnz     short loc_1400045A9
0x140004550  movzx   ecx, word ptr [rdi]
0x140004553  movzx   r9d, word ptr [r15]
0x140004557  cmp     r9w, cx
0x14000455b  jnz     short loc_1400045A9
0x14000455d  movzx   eax, word ptr [rdi+2]
0x140004561  cmp     [r15+2], ax
0x140004566  jnz     short loc_1400045A9
0x140004568  cmp     cx, 2
0x14000456c  lea     rdx, [rdi+4]; Buf2
0x140004570  mov     eax, 8
0x140004575  mov     r8d, 4
0x14000457b  cmovnz  r8d, ebp; Size
0x14000457f  mov     ecx, 4
0x140004584  cmp     r9w, 2
0x140004589  cmovnz  ecx, eax
0x14000458c  add     rcx, r15; Buf1
0x14000458f  call    memcmp
0x140004594  test    eax, eax
0x140004596  jnz     short loc_1400045A9
0x140004598  test    r14b, r14b
0x14000459b  jz      short loc_1400045C9
0x14000459d  mov     eax, [rsp+88h+arg_8]
0x1400045a4  cmp     eax, [rbx+8]
0x1400045a7  jz      short loc_1400045C9
0x1400045a9  mov     rcx, [rsp+88h+HashTable]; HashTable
0x1400045b1  lea     rdx, [rsp+88h+LockHandle]; Context
0x1400045b6  xor     ebp, ebp
0x1400045b8  call    cs:__imp_RtlGetNextEntryHashTable
0x1400045bf  nop     dword ptr [rax+rax+00h]
0x1400045c4  jmp     loc_140004464
0x1400045c9  test    r14b, r14b
0x1400045cc  mov     rbp, 0FFFFFFFFFFFFFF58h
0x1400045d3  mov     rcx, 0FFFFFFFFFFFFFF40h
0x1400045da  cmovz   rbp, rcx
0x1400045de  add     rbp, rsi
0x1400045e1  jz      short loc_1400045FE
0x1400045e3  mov     eax, 1
0x1400045e8  lock xadd [rbp+0], rax
0x1400045ee  inc     rax
0x1400045f1  cmp     rax, 1
0x1400045f5  jg      short loc_1400045FE
0x1400045f7  mov     ecx, 0Eh
0x1400045fc  int     29h; Win8: RtlFailFast(ecx)
0x1400045fe  mov     ecx, [r13+8]
0x140004602  and     rcx, [rsp+88h+arg_18]
0x14000460a  inc     rcx
0x14000460d  shl     rcx, 6
0x140004611  lock dec dword ptr [rcx+r13]
0x140004616  movzx   ecx, [rsp+88h+arg_10]; NewIrql
0x14000461e  call    cs:__imp_KeLowerIrql
0x140004625  nop     dword ptr [rax+rax+00h]
0x14000462a  mov     rax, rbp
0x14000462d  add     rsp, 48h
0x140004631  pop     r15
0x140004633  pop     r14
0x140004635  pop     r13
0x140004637  pop     r12
0x140004639  pop     rdi
0x14000463a  pop     rsi
0x14000463b  pop     rbp
0x14000463c  pop     rbx
0x14000463d  retn
```
