# W3WP_HOST_WORKITEM::~W3WP_HOST_WORKITEM(void)

- ea: `0x18000ac68`
- end: `0x18000ac87`
- name: `??1W3WP_HOST_WORKITEM@@UEAA@XZ`
- size: `31`
- prototype: `void __fastcall(W3WP_HOST_WORKITEM *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ac24`
- `0x18000ad50`
- `0x18000befc`

## callees

- `0x18000ac68`

## pseudocode

```c
void __fastcall W3WP_HOST_WORKITEM::~W3WP_HOST_WORKITEM(W3WP_HOST_WORKITEM *this)
{
  bool v1; // zf

  v1 = *((_DWORD *)this + 8) == 0;
  *(_QWORD *)this = &W3WP_HOST_WORKITEM::`vftable';
  *((_DWORD *)this + 2) = 1484222583;
  if ( !v1 )
    _InterlockedDecrement(&W3WP_HOST_WORKITEM::sm_OutstandingWorkItemCount);
}

```

## disassembly

```asm
0x18000ac68  cmp     dword ptr [rcx+20h], 0
0x18000ac6c  lea     rax, ??_7W3WP_HOST_WORKITEM@@6B@; const W3WP_HOST_WORKITEM::`vftable'
0x18000ac73  mov     [rcx], rax
0x18000ac76  mov     dword ptr [rcx+8], 58777077h
0x18000ac7d  jz      short locret_18000AC86
0x18000ac7f  lock dec cs:?sm_OutstandingWorkItemCount@W3WP_HOST_WORKITEM@@0JA; long W3WP_HOST_WORKITEM::sm_OutstandingWorkItemCount
0x18000ac86  retn
```
