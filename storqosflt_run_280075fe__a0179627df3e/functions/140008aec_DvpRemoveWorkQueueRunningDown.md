# DvpRemoveWorkQueueRunningDown

- ea: `0x140008aec`
- end: `0x140008b2b`
- name: `DvpRemoveWorkQueueRunningDown`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140008a8c`

## callees

- `0x140008aec`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140008b15`
- `ntoskrnl!KeSetEvent` at `0x140008b15`

## pseudocode

```c
__int64 __fastcall DvpRemoveWorkQueueRunningDown(_QWORD *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rbx

  v2 = *a1 - 2LL;
  v3 = *(_QWORD *)(v2 + 24);
  *(_QWORD *)(v2 + 24) = 0;
  if ( !v3 )
  {
    *a1 = 0;
    KeSetEvent((PRKEVENT)v2, 0, 0);
  }
  return v3;
}

```

## disassembly

```asm
0x140008aec  push    rbx
0x140008aee  sub     rsp, 20h
0x140008af2  mov     rdx, rcx
0x140008af5  mov     rcx, [rcx]
0x140008af8  add     rcx, 0FFFFFFFFFFFFFFFEh; Event
0x140008afc  mov     rbx, [rcx+18h]
0x140008b00  mov     qword ptr [rcx+18h], 0
0x140008b08  test    rbx, rbx
0x140008b0b  jnz     short loc_140008B21
0x140008b0d  mov     [rdx], rbx
0x140008b10  xor     r8d, r8d; Wait
0x140008b13  xor     edx, edx; Increment
0x140008b15  call    cs:__imp_KeSetEvent
0x140008b1c  nop     dword ptr [rax+rax+00h]
0x140008b21  mov     rax, rbx
0x140008b24  add     rsp, 20h
0x140008b28  pop     rbx
0x140008b29  retn
```
