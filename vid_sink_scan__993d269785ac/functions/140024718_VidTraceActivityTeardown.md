# VidTraceActivityTeardown

- ea: `0x140024718`
- end: `0x14002474d`
- name: `VidTraceActivityTeardown`
- size: `53`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `31`
- callee_count: `0`
- tags: ``

## callers

- `0x14007a578`
- `0x14007a840`
- `0x14007abc8`
- `0x14007b274`
- `0x14007b724`
- `0x14007ba88`
- `0x14007bdec`
- `0x14007c1f8`
- `0x14007c5bc`
- `0x14007cad0`
- `0x14007ce94`
- `0x14007d1a4`
- `0x14007d59c`
- `0x14007d9b4`
- `0x14007de28`
- `0x14007e1ec`
- `0x14007e4fc`
- `0x14007e8d4`
- `0x14007ece4`
- `0x14007f0bc`
- `0x14007f494`
- `0x14007f888`
- `0x14007fc98`
- `0x1400800a8`
- `0x1400803f8`
- `0x140080744`
- `0x140080c14`
- `0x140080f50`
- `0x140081424`
- `0x14008880c`
- `0x140088f6c`

## import_xrefs

- `ntoskrnl!IoClearActivityIdThread` at `0x140024725`
- `ntoskrnl!IoClearActivityIdThread` at `0x140024725`
- `ntoskrnl!EtwActivityIdControl` at `0x14002473a`
- `ntoskrnl!EtwActivityIdControl` at `0x14002473a`

## pseudocode

```c
NTSTATUS __fastcall VidTraceActivityTeardown(GUID *a1)
{
  IoClearActivityIdThread(*(_QWORD *)a1->Data4);
  return EtwActivityIdControl(2u, a1 + 1);
}

```

## disassembly

```asm
0x140024718  push    rbx
0x14002471a  sub     rsp, 20h
0x14002471e  mov     rbx, rcx
0x140024721  mov     rcx, [rcx+8]
0x140024725  call    cs:__imp_IoClearActivityIdThread
0x14002472c  nop     dword ptr [rax+rax+00h]
0x140024731  lea     rdx, [rbx+10h]; ActivityId
0x140024735  mov     ecx, 2; ControlCode
0x14002473a  call    cs:__imp_EtwActivityIdControl
0x140024741  nop     dword ptr [rax+rax+00h]
0x140024746  add     rsp, 20h
0x14002474a  pop     rbx
0x14002474b  retn
```
