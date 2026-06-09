# DvpRemoveWorkQueueRunningDown

- ea: `0x140016ed4`
- end: `0x140016f13`
- name: `DvpRemoveWorkQueueRunningDown`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140016e8c`

## callees

- `0x140016ed4`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140016efd`
- `ntoskrnl!KeSetEvent` at `0x140016efd`

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
0x140016ed4  push    rbx
0x140016ed6  sub     rsp, 20h
0x140016eda  mov     rdx, rcx
0x140016edd  mov     rcx, [rcx]
0x140016ee0  add     rcx, 0FFFFFFFFFFFFFFFEh; Event
0x140016ee4  mov     rbx, [rcx+18h]
0x140016ee8  mov     qword ptr [rcx+18h], 0
0x140016ef0  test    rbx, rbx
0x140016ef3  jnz     short loc_140016F09
0x140016ef5  mov     [rdx], rbx
0x140016ef8  xor     r8d, r8d; Wait
0x140016efb  xor     edx, edx; Increment
0x140016efd  call    cs:__imp_KeSetEvent
0x140016f04  nop     dword ptr [rax+rax+00h]
0x140016f09  mov     rax, rbx
0x140016f0c  add     rsp, 20h
0x140016f10  pop     rbx
0x140016f11  retn
```
