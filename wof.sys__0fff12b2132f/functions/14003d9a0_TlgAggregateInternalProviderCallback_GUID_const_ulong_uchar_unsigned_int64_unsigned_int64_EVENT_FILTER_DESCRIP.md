# TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x14003d9a0`
- end: `0x14003da02`
- name: `?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `98`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14003d5cc`
- `0x14003d9a0`

## import_xrefs

- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x14003d9b9`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x14003d9b9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003d9ef`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003d9ef`

## pseudocode

```c
void __fastcall TlgAggregateInternalProviderCallback(const struct _GUID *a1, int a2, __int64 a3, __int64 a4)
{
  __int64 i; // rbx

  if ( a2 == 2 && a4 == 32 && (unsigned __int8)ExTryAcquirePushLockExclusiveEx(&qword_1400190A8, 0) )
  {
    for ( i = qword_1400190B0; i; i = *(_QWORD *)(i + 352) )
      LookUpTableFlushComplete(i);
    ExReleasePushLockExclusiveEx(&qword_1400190A8, 0);
  }
}

```

## disassembly

```asm
0x14003d9a0  cmp     edx, 2
0x14003d9a3  jnz     short locret_14003DA00
0x14003d9a5  push    rbx
0x14003d9a6  sub     rsp, 20h
0x14003d9aa  cmp     r9, 20h ; ' '
0x14003d9ae  jnz     short loc_14003D9FB
0x14003d9b0  xor     edx, edx
0x14003d9b2  lea     rcx, qword_1400190A8
0x14003d9b9  call    cs:__imp_ExTryAcquirePushLockExclusiveEx
0x14003d9c0  nop     dword ptr [rax+rax+00h]
0x14003d9c5  test    al, al
0x14003d9c7  jz      short loc_14003D9FB
0x14003d9c9  mov     rbx, cs:qword_1400190B0
0x14003d9d0  jmp     short loc_14003D9E1
0x14003d9d2  mov     rcx, rbx
0x14003d9d5  call    LookUpTableFlushComplete
0x14003d9da  mov     rbx, [rbx+160h]
0x14003d9e1  test    rbx, rbx
0x14003d9e4  jnz     short loc_14003D9D2
0x14003d9e6  xor     edx, edx
0x14003d9e8  lea     rcx, qword_1400190A8
0x14003d9ef  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14003d9f6  nop     dword ptr [rax+rax+00h]
0x14003d9fb  add     rsp, 20h
0x14003d9ff  pop     rbx
0x14003da00  retn
```
