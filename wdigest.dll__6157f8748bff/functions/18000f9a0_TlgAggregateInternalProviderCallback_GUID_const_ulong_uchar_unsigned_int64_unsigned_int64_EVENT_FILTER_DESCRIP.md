# TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x18000f9a0`
- end: `0x18000f9f1`
- name: `?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `81`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000e180`
- `0x18000f9a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18000f9b7`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18000f9b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f9e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f9e5`

## pseudocode

```c
void __fastcall TlgAggregateInternalProviderCallback(const struct _GUID *a1, int a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  int v6; // r9d
  const __m128i *i; // rbx

  if ( a2 == 2 && a4 == 32 && TryAcquireSRWLockExclusive(&SRWLock) )
  {
    for ( i = (const __m128i *)qword_1800463E8; i; i = (const __m128i *)i[21].m128i_i64[0] )
      LookUpTableFlushComplete(i, v4, v5, v6);
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x18000f9a0  cmp     edx, 2
0x18000f9a3  jnz     short locret_18000F9F0
0x18000f9a5  push    rbx
0x18000f9a6  sub     rsp, 20h
0x18000f9aa  cmp     r9, 20h ; ' '
0x18000f9ae  jnz     short loc_18000F9EB
0x18000f9b0  lea     rcx, SRWLock; SRWLock
0x18000f9b7  call    cs:__imp_TryAcquireSRWLockExclusive
0x18000f9bd  test    al, al
0x18000f9bf  jz      short loc_18000F9EB
0x18000f9c1  mov     rbx, cs:qword_1800463E8
0x18000f9c8  jmp     short loc_18000F9D9
0x18000f9ca  mov     rcx, rbx
0x18000f9cd  call    LookUpTableFlushComplete
0x18000f9d2  mov     rbx, [rbx+150h]
0x18000f9d9  test    rbx, rbx
0x18000f9dc  jnz     short loc_18000F9CA
0x18000f9de  lea     rcx, SRWLock; SRWLock
0x18000f9e5  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f9eb  add     rsp, 20h
0x18000f9ef  pop     rbx
0x18000f9f0  retn
```
