# VidTraceActivityTeardown

- ea: `0x1400248b8`
- end: `0x1400248ed`
- name: `VidTraceActivityTeardown`
- size: `53`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `31`
- callee_count: `0`
- tags: ``

## callers

- `0x14007b454`
- `0x14007b71c`
- `0x14007baa4`
- `0x14007c150`
- `0x14007c600`
- `0x14007c964`
- `0x14007ccc8`
- `0x14007d0d4`
- `0x14007d498`
- `0x14007d9ac`
- `0x14007dd70`
- `0x14007e080`
- `0x14007e478`
- `0x14007e890`
- `0x14007ed04`
- `0x14007f0c8`
- `0x14007f3d8`
- `0x14007f7b0`
- `0x14007fbc0`
- `0x14007ff98`
- `0x140080370`
- `0x140080764`
- `0x140080b74`
- `0x140080f84`
- `0x1400812d4`
- `0x140081620`
- `0x140081af0`
- `0x140081e2c`
- `0x140082300`
- `0x140089b94`
- `0x14008a2f0`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x1400248da`
- `ntoskrnl!EtwActivityIdControl` at `0x1400248da`
- `ntoskrnl!IoClearActivityIdThread` at `0x1400248c5`
- `ntoskrnl!IoClearActivityIdThread` at `0x1400248c5`

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
0x1400248b8  push    rbx
0x1400248ba  sub     rsp, 20h
0x1400248be  mov     rbx, rcx
0x1400248c1  mov     rcx, [rcx+8]
0x1400248c5  call    cs:__imp_IoClearActivityIdThread
0x1400248cc  nop     dword ptr [rax+rax+00h]
0x1400248d1  lea     rdx, [rbx+10h]; ActivityId
0x1400248d5  mov     ecx, 2; ControlCode
0x1400248da  call    cs:__imp_EtwActivityIdControl
0x1400248e1  nop     dword ptr [rax+rax+00h]
0x1400248e6  add     rsp, 20h
0x1400248ea  pop     rbx
0x1400248eb  retn
```
