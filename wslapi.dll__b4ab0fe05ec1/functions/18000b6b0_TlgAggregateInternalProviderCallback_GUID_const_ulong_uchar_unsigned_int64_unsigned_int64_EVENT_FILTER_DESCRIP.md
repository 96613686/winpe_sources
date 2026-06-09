# TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x18000b6b0`
- end: `0x18000b701`
- name: `?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `81`
- prototype: `void __fastcall(const struct _GUID *, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000b280`
- `0x18000b6b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18000b6c7`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18000b6c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b6f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b6f5`

## pseudocode

```c
void __fastcall TlgAggregateInternalProviderCallback(const struct _GUID *a1, int a2, __int64 a3, __int64 a4)
{
  __int64 i; // rbx

  if ( a2 == 2 && a4 == 32 && TryAcquireSRWLockExclusive(&SRWLock) )
  {
    for ( i = qword_1800135E0; i; i = *(_QWORD *)(i + 336) )
      LookUpTableFlushComplete(i);
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x18000b6b0  cmp     edx, 2
0x18000b6b3  jnz     short locret_18000B700
0x18000b6b5  push    rbx
0x18000b6b6  sub     rsp, 20h
0x18000b6ba  cmp     r9, 20h ; ' '
0x18000b6be  jnz     short loc_18000B6FB
0x18000b6c0  lea     rcx, SRWLock; SRWLock
0x18000b6c7  call    cs:__imp_TryAcquireSRWLockExclusive
0x18000b6cd  test    al, al
0x18000b6cf  jz      short loc_18000B6FB
0x18000b6d1  mov     rbx, cs:qword_1800135E0
0x18000b6d8  jmp     short loc_18000B6E9
0x18000b6da  mov     rcx, rbx
0x18000b6dd  call    LookUpTableFlushComplete
0x18000b6e2  mov     rbx, [rbx+150h]
0x18000b6e9  test    rbx, rbx
0x18000b6ec  jnz     short loc_18000B6DA
0x18000b6ee  lea     rcx, SRWLock; SRWLock
0x18000b6f5  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b6fb  add     rsp, 20h
0x18000b6ff  pop     rbx
0x18000b700  retn
```
