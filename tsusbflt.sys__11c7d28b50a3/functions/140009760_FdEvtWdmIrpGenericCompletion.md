# FdEvtWdmIrpGenericCompletion

- ea: `0x140009760`
- end: `0x14000979e`
- name: `FdEvtWdmIrpGenericCompletion`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140009760`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140009787`
- `ntoskrnl!KeSetEvent` at `0x140009787`

## pseudocode

```c
__int64 __fastcall FdEvtWdmIrpGenericCompletion(__int64 a1, __int64 a2, struct _KEVENT *a3)
{
  if ( a1 && *(_BYTE *)(a2 + 65) )
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
  KeSetEvent(a3, 1, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140009760  sub     rsp, 28h
0x140009764  mov     r9, r8
0x140009767  test    rcx, rcx
0x14000976a  jz      short loc_14000977D
0x14000976c  cmp     byte ptr [rdx+41h], 0
0x140009770  jz      short loc_14000977D
0x140009772  mov     rax, [rdx+0B8h]
0x140009779  or      byte ptr [rax+3], 1
0x14000977d  xor     r8d, r8d; Wait
0x140009780  mov     rcx, r9; Event
0x140009783  lea     edx, [r8+1]; Increment
0x140009787  call    cs:__imp_KeSetEvent
0x14000978e  nop     dword ptr [rax+rax+00h]
0x140009793  mov     eax, 0C0000016h
0x140009798  add     rsp, 28h
0x14000979c  retn
```
