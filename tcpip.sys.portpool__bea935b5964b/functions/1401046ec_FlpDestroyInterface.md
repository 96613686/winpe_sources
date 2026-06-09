# FlpDestroyInterface

- ea: `0x1401046ec`
- end: `0x140104801`
- name: `FlpDestroyInterface`
- size: `277`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140103de4`
- `0x1401c06d0`
- `0x1401c087c`

## callees

- `0x1401046ec`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x1401047ab`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1401047ab`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140104769`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14010477e`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140104793`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140104769`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14010477e`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140104793`
- `ntoskrnl!IoFreeWorkItem` at `0x140104744`
- `ntoskrnl!IoFreeWorkItem` at `0x140104744`
- `ntoskrnl!RtlDeleteHashTable` at `0x140104704`
- `ntoskrnl!RtlDeleteHashTable` at `0x140104717`
- `ntoskrnl!RtlDeleteHashTable` at `0x140104704`
- `ntoskrnl!RtlDeleteHashTable` at `0x140104717`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401047bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401047bc`
- `NETIO!NetioShutdownWorkQueue` at `0x140104754`
- `NETIO!NetioShutdownWorkQueue` at `0x140104754`
- `NETIO!NmrProviderDetachClientComplete` at `0x1401047e9`
- `NETIO!NmrProviderDetachClientComplete` at `0x1401047e9`
- `NDIS!NdisFreeRWLock` at `0x14010472c`
- `NDIS!NdisFreeRWLock` at `0x14010472c`

## pseudocode

```c
void __fastcall FlpDestroyInterface(char *P)
{
  __int64 v1; // rdi
  struct _NDIS_RW_LOCK_EX *v3; // rcx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v4; // rcx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v5; // rcx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v6; // rcx
  struct _EX_RUNDOWN_REF *v7; // rcx

  v1 = *((_QWORD *)P + 4);
  RtlDeleteHashTable((PRTL_DYNAMIC_HASH_TABLE)(P + 208));
  RtlDeleteHashTable((PRTL_DYNAMIC_HASH_TABLE)(P + 248));
  v3 = (struct _NDIS_RW_LOCK_EX *)*((_QWORD *)P + 5);
  if ( v3 )
  {
    NdisFreeRWLock(v3);
    *((_QWORD *)P + 5) = 0;
  }
  IoFreeWorkItem(*((PIO_WORKITEM *)P + 12));
  NetioShutdownWorkQueue(P + 120);
  v4 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)P + 8);
  if ( v4 )
    ExFreeCacheAwareRundownProtection(v4);
  v5 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)P + 9);
  if ( v5 )
    ExFreeCacheAwareRundownProtection(v5);
  v6 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)P + 10);
  if ( v6 )
    ExFreeCacheAwareRundownProtection(v6);
  v7 = (struct _EX_RUNDOWN_REF *)*((_QWORD *)P + 135);
  if ( v7 )
    ExReleaseRundownProtection(v7);
  ExFreePoolWithTag(P, 0);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)(v1 + 216) + 32LL), 0xFFFFFFFE) == 3 )
    NmrProviderDetachClientComplete(*(HANDLE *)(*(_QWORD *)(v1 + 216) + 16LL));
}

```

## disassembly

```asm
0x1401046ec  mov     [rsp+arg_0], rbx
0x1401046f1  push    rdi
0x1401046f2  sub     rsp, 20h
0x1401046f6  mov     rdi, [rcx+20h]
0x1401046fa  mov     rbx, rcx
0x1401046fd  add     rcx, 0D0h; HashTable
0x140104704  call    cs:__imp_RtlDeleteHashTable
0x14010470b  nop     dword ptr [rax+rax+00h]
0x140104710  lea     rcx, [rbx+0F8h]; HashTable
0x140104717  call    cs:__imp_RtlDeleteHashTable
0x14010471e  nop     dword ptr [rax+rax+00h]
0x140104723  mov     rcx, [rbx+28h]; Lock
0x140104727  test    rcx, rcx
0x14010472a  jz      short loc_140104740
0x14010472c  call    cs:__imp_NdisFreeRWLock
0x140104733  nop     dword ptr [rax+rax+00h]
0x140104738  mov     qword ptr [rbx+28h], 0
0x140104740  mov     rcx, [rbx+60h]; IoWorkItem
0x140104744  call    cs:__imp_IoFreeWorkItem
0x14010474b  nop     dword ptr [rax+rax+00h]
0x140104750  lea     rcx, [rbx+78h]
0x140104754  call    cs:__imp_NetioShutdownWorkQueue
0x14010475b  nop     dword ptr [rax+rax+00h]
0x140104760  mov     rcx, [rbx+40h]; RunRefCacheAware
0x140104764  test    rcx, rcx
0x140104767  jz      short loc_140104775
0x140104769  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x140104770  nop     dword ptr [rax+rax+00h]
0x140104775  mov     rcx, [rbx+48h]; RunRefCacheAware
0x140104779  test    rcx, rcx
0x14010477c  jz      short loc_14010478A
0x14010477e  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x140104785  nop     dword ptr [rax+rax+00h]
0x14010478a  mov     rcx, [rbx+50h]; RunRefCacheAware
0x14010478e  test    rcx, rcx
0x140104791  jz      short loc_14010479F
0x140104793  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14010479a  nop     dword ptr [rax+rax+00h]
0x14010479f  mov     rcx, [rbx+438h]; RunRef
0x1401047a6  test    rcx, rcx
0x1401047a9  jz      short loc_1401047B7
0x1401047ab  call    cs:__imp_ExReleaseRundownProtection
0x1401047b2  nop     dword ptr [rax+rax+00h]
0x1401047b7  xor     edx, edx; Tag
0x1401047b9  mov     rcx, rbx; P
0x1401047bc  call    cs:__imp_ExFreePoolWithTag
0x1401047c3  nop     dword ptr [rax+rax+00h]
0x1401047c8  mov     rcx, [rdi+0D8h]
0x1401047cf  mov     eax, 0FFFFFFFEh
0x1401047d4  lock xadd [rcx+20h], eax
0x1401047d9  cmp     eax, 3
0x1401047dc  jnz     short loc_1401047F5
0x1401047de  mov     rcx, [rdi+0D8h]
0x1401047e5  mov     rcx, [rcx+10h]; NmrBindingHandle
0x1401047e9  call    cs:__imp_NmrProviderDetachClientComplete
0x1401047f0  nop     dword ptr [rax+rax+00h]
0x1401047f5  mov     rbx, [rsp+28h+arg_0]
0x1401047fa  add     rsp, 20h
0x1401047fe  pop     rdi
0x1401047ff  retn
```
