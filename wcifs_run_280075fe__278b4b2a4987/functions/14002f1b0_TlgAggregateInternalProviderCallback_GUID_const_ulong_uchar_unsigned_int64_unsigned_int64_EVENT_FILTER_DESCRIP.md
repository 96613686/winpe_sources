# TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x14002f1b0`
- end: `0x14002f214`
- name: `?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `100`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14002ea5c`
- `0x14002f1b0`

## import_xrefs

- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x14002f1cb`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x14002f1cb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002f201`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002f201`

## pseudocode

```c
void __fastcall TlgAggregateInternalProviderCallback(const struct _GUID *a1, int a2, __int64 a3, __int64 a4)
{
  __int64 i; // rbx

  if ( a2 == 2 && a4 == 32 && (unsigned __int8)ExTryAcquirePushLockExclusiveEx(&qword_14000E740, 0) )
  {
    for ( i = qword_14000E748; i; i = *(_QWORD *)(i + 352) )
      LookUpTableFlushComplete(i);
    ExReleasePushLockExclusiveEx(&qword_14000E740, 0);
  }
}

```

## disassembly

```asm
0x14002f1b0  cmp     edx, 2
0x14002f1b3  jz      short loc_14002F1B7
0x14002f1b5  retn
0x14002f1b7  push    rbx
0x14002f1b8  sub     rsp, 20h
0x14002f1bc  cmp     r9, 20h ; ' '
0x14002f1c0  jnz     short loc_14002F20D
0x14002f1c2  xor     edx, edx
0x14002f1c4  lea     rcx, qword_14000E740
0x14002f1cb  call    cs:__imp_ExTryAcquirePushLockExclusiveEx
0x14002f1d2  nop     dword ptr [rax+rax+00h]
0x14002f1d7  test    al, al
0x14002f1d9  jz      short loc_14002F20D
0x14002f1db  mov     rbx, cs:qword_14000E748
0x14002f1e2  jmp     short loc_14002F1F3
0x14002f1e4  mov     rcx, rbx
0x14002f1e7  call    LookUpTableFlushComplete
0x14002f1ec  mov     rbx, [rbx+160h]
0x14002f1f3  test    rbx, rbx
0x14002f1f6  jnz     short loc_14002F1E4
0x14002f1f8  xor     edx, edx
0x14002f1fa  lea     rcx, qword_14000E740
0x14002f201  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14002f208  nop     dword ptr [rax+rax+00h]
0x14002f20d  add     rsp, 20h
0x14002f211  pop     rbx
0x14002f212  retn
```
