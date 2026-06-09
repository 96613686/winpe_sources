# PgmTdiCompletionRoutine

- ea: `0x14001c020`
- end: `0x14001c08b`
- name: `PgmTdiCompletionRoutine`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140005524`
- `0x14001c020`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14001c073`
- `ntoskrnl!KeSetEvent` at `0x14001c073`

## pseudocode

```c
__int64 __fastcall PgmTdiCompletionRoutine(__int64 a1, __int64 a2, struct _KEVENT *a3)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids);
  KeSetEvent(a3, 0, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14001c020  push    rbx
0x14001c022  sub     rsp, 30h
0x14001c026  mov     rbx, r8
0x14001c029  mov     r9, rcx
0x14001c02c  mov     r8, rdx
0x14001c02f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c036  lea     rax, WPP_GLOBAL_Control
0x14001c03d  cmp     rcx, rax
0x14001c040  jz      short loc_14001C06B
0x14001c042  mov     eax, [rcx+2Ch]
0x14001c045  test    al, 10h
0x14001c047  jz      short loc_14001C06B
0x14001c049  mov     rcx, [rcx+18h]
0x14001c04d  mov     edx, 0Ah
0x14001c052  mov     [rsp+38h+var_10], r9
0x14001c057  mov     r9, rbx
0x14001c05a  mov     [rsp+38h+var_18], r8
0x14001c05f  lea     r8, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids
0x14001c066  call    WPP_SF_qqq
0x14001c06b  xor     r8d, r8d; Wait
0x14001c06e  xor     edx, edx; Increment
0x14001c070  mov     rcx, rbx; Event
0x14001c073  call    cs:__imp_KeSetEvent
0x14001c07a  nop     dword ptr [rax+rax+00h]
0x14001c07f  mov     eax, 0C0000016h
0x14001c084  add     rsp, 30h
0x14001c088  pop     rbx
0x14001c089  retn
```
