# FlpDestroyInterface

- ea: `0x1400c47a4`
- end: `0x1400c48b9`
- name: `FlpDestroyInterface`
- size: `277`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400c54b0`
- `0x1401bea90`
- `0x1401bec3c`

## callees

- `0x1400c47a4`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x1400c4863`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400c4863`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400c4821`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400c4836`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400c484b`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400c4821`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400c4836`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400c484b`
- `ntoskrnl!IoFreeWorkItem` at `0x1400c47fc`
- `ntoskrnl!IoFreeWorkItem` at `0x1400c47fc`
- `ntoskrnl!RtlDeleteHashTable` at `0x1400c47bc`
- `ntoskrnl!RtlDeleteHashTable` at `0x1400c47cf`
- `ntoskrnl!RtlDeleteHashTable` at `0x1400c47bc`
- `ntoskrnl!RtlDeleteHashTable` at `0x1400c47cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c4874`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c4874`
- `NETIO!NetioShutdownWorkQueue` at `0x1400c480c`
- `NETIO!NetioShutdownWorkQueue` at `0x1400c480c`
- `NETIO!NmrProviderDetachClientComplete` at `0x1400c48a1`
- `NETIO!NmrProviderDetachClientComplete` at `0x1400c48a1`
- `NDIS!NdisFreeRWLock` at `0x1400c47e4`
- `NDIS!NdisFreeRWLock` at `0x1400c47e4`

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
0x1400c47a4  mov     [rsp+arg_0], rbx
0x1400c47a9  push    rdi
0x1400c47aa  sub     rsp, 20h
0x1400c47ae  mov     rdi, [rcx+20h]
0x1400c47b2  mov     rbx, rcx
0x1400c47b5  add     rcx, 0D0h; HashTable
0x1400c47bc  call    cs:__imp_RtlDeleteHashTable
0x1400c47c3  nop     dword ptr [rax+rax+00h]
0x1400c47c8  lea     rcx, [rbx+0F8h]; HashTable
0x1400c47cf  call    cs:__imp_RtlDeleteHashTable
0x1400c47d6  nop     dword ptr [rax+rax+00h]
0x1400c47db  mov     rcx, [rbx+28h]; Lock
0x1400c47df  test    rcx, rcx
0x1400c47e2  jz      short loc_1400C47F8
0x1400c47e4  call    cs:__imp_NdisFreeRWLock
0x1400c47eb  nop     dword ptr [rax+rax+00h]
0x1400c47f0  mov     qword ptr [rbx+28h], 0
0x1400c47f8  mov     rcx, [rbx+60h]; IoWorkItem
0x1400c47fc  call    cs:__imp_IoFreeWorkItem
0x1400c4803  nop     dword ptr [rax+rax+00h]
0x1400c4808  lea     rcx, [rbx+78h]
0x1400c480c  call    cs:__imp_NetioShutdownWorkQueue
0x1400c4813  nop     dword ptr [rax+rax+00h]
0x1400c4818  mov     rcx, [rbx+40h]; RunRefCacheAware
0x1400c481c  test    rcx, rcx
0x1400c481f  jz      short loc_1400C482D
0x1400c4821  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1400c4828  nop     dword ptr [rax+rax+00h]
0x1400c482d  mov     rcx, [rbx+48h]; RunRefCacheAware
0x1400c4831  test    rcx, rcx
0x1400c4834  jz      short loc_1400C4842
0x1400c4836  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1400c483d  nop     dword ptr [rax+rax+00h]
0x1400c4842  mov     rcx, [rbx+50h]; RunRefCacheAware
0x1400c4846  test    rcx, rcx
0x1400c4849  jz      short loc_1400C4857
0x1400c484b  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1400c4852  nop     dword ptr [rax+rax+00h]
0x1400c4857  mov     rcx, [rbx+438h]; RunRef
0x1400c485e  test    rcx, rcx
0x1400c4861  jz      short loc_1400C486F
0x1400c4863  call    cs:__imp_ExReleaseRundownProtection
0x1400c486a  nop     dword ptr [rax+rax+00h]
0x1400c486f  xor     edx, edx; Tag
0x1400c4871  mov     rcx, rbx; P
0x1400c4874  call    cs:__imp_ExFreePoolWithTag
0x1400c487b  nop     dword ptr [rax+rax+00h]
0x1400c4880  mov     rcx, [rdi+0D8h]
0x1400c4887  mov     eax, 0FFFFFFFEh
0x1400c488c  lock xadd [rcx+20h], eax
0x1400c4891  cmp     eax, 3
0x1400c4894  jnz     short loc_1400C48AD
0x1400c4896  mov     rcx, [rdi+0D8h]
0x1400c489d  mov     rcx, [rcx+10h]; NmrBindingHandle
0x1400c48a1  call    cs:__imp_NmrProviderDetachClientComplete
0x1400c48a8  nop     dword ptr [rax+rax+00h]
0x1400c48ad  mov     rbx, [rsp+28h+arg_0]
0x1400c48b2  add     rsp, 20h
0x1400c48b6  pop     rdi
0x1400c48b7  retn
```
