# W3WP_HOST_WORKITEM::~W3WP_HOST_WORKITEM(void)

- ea: `0x18000a048`
- end: `0x18000a067`
- name: `??1W3WP_HOST_WORKITEM@@UEAA@XZ`
- size: `31`
- prototype: `void __fastcall(W3WP_HOST_WORKITEM *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a004`
- `0x18000a130`
- `0x18000b12c`

## callees

- `0x18000a048`

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
0x18000a048  cmp     dword ptr [rcx+20h], 0
0x18000a04c  lea     rax, ??_7W3WP_HOST_WORKITEM@@6B@; const W3WP_HOST_WORKITEM::`vftable'
0x18000a053  mov     [rcx], rax
0x18000a056  mov     dword ptr [rcx+8], 58777077h
0x18000a05d  jz      short locret_18000A066
0x18000a05f  lock dec cs:?sm_OutstandingWorkItemCount@W3WP_HOST_WORKITEM@@0JA; long W3WP_HOST_WORKITEM::sm_OutstandingWorkItemCount
0x18000a066  retn
```
