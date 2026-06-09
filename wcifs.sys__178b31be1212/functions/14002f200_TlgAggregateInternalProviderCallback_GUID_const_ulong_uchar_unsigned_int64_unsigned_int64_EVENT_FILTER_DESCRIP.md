# TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x14002f200`
- end: `0x14002f264`
- name: `?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `100`
- prototype: `void __fastcall(const struct _GUID *, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14002eaac`
- `0x14002f200`

## import_xrefs

- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x14002f21b`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x14002f21b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002f251`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002f251`

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
0x14002f200  cmp     edx, 2
0x14002f203  jz      short loc_14002F207
0x14002f205  retn
0x14002f207  push    rbx
0x14002f208  sub     rsp, 20h
0x14002f20c  cmp     r9, 20h ; ' '
0x14002f210  jnz     short loc_14002F25D
0x14002f212  xor     edx, edx
0x14002f214  lea     rcx, qword_14000E740
0x14002f21b  call    cs:__imp_ExTryAcquirePushLockExclusiveEx
0x14002f222  nop     dword ptr [rax+rax+00h]
0x14002f227  test    al, al
0x14002f229  jz      short loc_14002F25D
0x14002f22b  mov     rbx, cs:qword_14000E748
0x14002f232  jmp     short loc_14002F243
0x14002f234  mov     rcx, rbx
0x14002f237  call    LookUpTableFlushComplete
0x14002f23c  mov     rbx, [rbx+160h]
0x14002f243  test    rbx, rbx
0x14002f246  jnz     short loc_14002F234
0x14002f248  xor     edx, edx
0x14002f24a  lea     rcx, qword_14000E740
0x14002f251  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14002f258  nop     dword ptr [rax+rax+00h]
0x14002f25d  add     rsp, 20h
0x14002f261  pop     rbx
0x14002f262  retn
```
