# FlpDestroyInterface

- ea: `0x1400c4584`
- end: `0x1400c4699`
- name: `FlpDestroyInterface`
- size: `277`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400c5290`
- `0x1401bebd0`
- `0x1401bed7c`

## callees

- `0x1400c4584`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x1400c4643`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400c4643`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400c4601`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400c4616`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400c462b`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400c4601`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400c4616`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400c462b`
- `ntoskrnl!IoFreeWorkItem` at `0x1400c45dc`
- `ntoskrnl!IoFreeWorkItem` at `0x1400c45dc`
- `ntoskrnl!RtlDeleteHashTable` at `0x1400c459c`
- `ntoskrnl!RtlDeleteHashTable` at `0x1400c45af`
- `ntoskrnl!RtlDeleteHashTable` at `0x1400c459c`
- `ntoskrnl!RtlDeleteHashTable` at `0x1400c45af`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c4654`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c4654`
- `NETIO!NetioShutdownWorkQueue` at `0x1400c45ec`
- `NETIO!NetioShutdownWorkQueue` at `0x1400c45ec`
- `NETIO!NmrProviderDetachClientComplete` at `0x1400c4681`
- `NETIO!NmrProviderDetachClientComplete` at `0x1400c4681`
- `NDIS!NdisFreeRWLock` at `0x1400c45c4`
- `NDIS!NdisFreeRWLock` at `0x1400c45c4`

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
0x1400c4584  mov     [rsp+arg_0], rbx
0x1400c4589  push    rdi
0x1400c458a  sub     rsp, 20h
0x1400c458e  mov     rdi, [rcx+20h]
0x1400c4592  mov     rbx, rcx
0x1400c4595  add     rcx, 0D0h; HashTable
0x1400c459c  call    cs:__imp_RtlDeleteHashTable
0x1400c45a3  nop     dword ptr [rax+rax+00h]
0x1400c45a8  lea     rcx, [rbx+0F8h]; HashTable
0x1400c45af  call    cs:__imp_RtlDeleteHashTable
0x1400c45b6  nop     dword ptr [rax+rax+00h]
0x1400c45bb  mov     rcx, [rbx+28h]; Lock
0x1400c45bf  test    rcx, rcx
0x1400c45c2  jz      short loc_1400C45D8
0x1400c45c4  call    cs:__imp_NdisFreeRWLock
0x1400c45cb  nop     dword ptr [rax+rax+00h]
0x1400c45d0  mov     qword ptr [rbx+28h], 0
0x1400c45d8  mov     rcx, [rbx+60h]; IoWorkItem
0x1400c45dc  call    cs:__imp_IoFreeWorkItem
0x1400c45e3  nop     dword ptr [rax+rax+00h]
0x1400c45e8  lea     rcx, [rbx+78h]
0x1400c45ec  call    cs:__imp_NetioShutdownWorkQueue
0x1400c45f3  nop     dword ptr [rax+rax+00h]
0x1400c45f8  mov     rcx, [rbx+40h]; RunRefCacheAware
0x1400c45fc  test    rcx, rcx
0x1400c45ff  jz      short loc_1400C460D
0x1400c4601  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1400c4608  nop     dword ptr [rax+rax+00h]
0x1400c460d  mov     rcx, [rbx+48h]; RunRefCacheAware
0x1400c4611  test    rcx, rcx
0x1400c4614  jz      short loc_1400C4622
0x1400c4616  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1400c461d  nop     dword ptr [rax+rax+00h]
0x1400c4622  mov     rcx, [rbx+50h]; RunRefCacheAware
0x1400c4626  test    rcx, rcx
0x1400c4629  jz      short loc_1400C4637
0x1400c462b  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1400c4632  nop     dword ptr [rax+rax+00h]
0x1400c4637  mov     rcx, [rbx+438h]; RunRef
0x1400c463e  test    rcx, rcx
0x1400c4641  jz      short loc_1400C464F
0x1400c4643  call    cs:__imp_ExReleaseRundownProtection
0x1400c464a  nop     dword ptr [rax+rax+00h]
0x1400c464f  xor     edx, edx; Tag
0x1400c4651  mov     rcx, rbx; P
0x1400c4654  call    cs:__imp_ExFreePoolWithTag
0x1400c465b  nop     dword ptr [rax+rax+00h]
0x1400c4660  mov     rcx, [rdi+0D8h]
0x1400c4667  mov     eax, 0FFFFFFFEh
0x1400c466c  lock xadd [rcx+20h], eax
0x1400c4671  cmp     eax, 3
0x1400c4674  jnz     short loc_1400C468D
0x1400c4676  mov     rcx, [rdi+0D8h]
0x1400c467d  mov     rcx, [rcx+10h]; NmrBindingHandle
0x1400c4681  call    cs:__imp_NmrProviderDetachClientComplete
0x1400c4688  nop     dword ptr [rax+rax+00h]
0x1400c468d  mov     rbx, [rsp+28h+arg_0]
0x1400c4692  add     rsp, 20h
0x1400c4696  pop     rdi
0x1400c4697  retn
```
