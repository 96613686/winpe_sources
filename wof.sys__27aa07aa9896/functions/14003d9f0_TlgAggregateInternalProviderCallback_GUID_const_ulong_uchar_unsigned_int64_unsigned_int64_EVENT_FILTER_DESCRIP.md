# TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x14003d9f0`
- end: `0x14003da52`
- name: `?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `98`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14003d61c`
- `0x14003d9f0`

## import_xrefs

- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x14003da09`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x14003da09`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003da3f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003da3f`

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
0x14003d9f0  cmp     edx, 2
0x14003d9f3  jnz     short locret_14003DA50
0x14003d9f5  push    rbx
0x14003d9f6  sub     rsp, 20h
0x14003d9fa  cmp     r9, 20h ; ' '
0x14003d9fe  jnz     short loc_14003DA4B
0x14003da00  xor     edx, edx
0x14003da02  lea     rcx, qword_1400190A8
0x14003da09  call    cs:__imp_ExTryAcquirePushLockExclusiveEx
0x14003da10  nop     dword ptr [rax+rax+00h]
0x14003da15  test    al, al
0x14003da17  jz      short loc_14003DA4B
0x14003da19  mov     rbx, cs:qword_1400190B0
0x14003da20  jmp     short loc_14003DA31
0x14003da22  mov     rcx, rbx
0x14003da25  call    LookUpTableFlushComplete
0x14003da2a  mov     rbx, [rbx+160h]
0x14003da31  test    rbx, rbx
0x14003da34  jnz     short loc_14003DA22
0x14003da36  xor     edx, edx
0x14003da38  lea     rcx, qword_1400190A8
0x14003da3f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14003da46  nop     dword ptr [rax+rax+00h]
0x14003da4b  add     rsp, 20h
0x14003da4f  pop     rbx
0x14003da50  retn
```
