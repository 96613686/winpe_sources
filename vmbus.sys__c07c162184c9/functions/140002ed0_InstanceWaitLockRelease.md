# InstanceWaitLockRelease

- ea: `0x140002ed0`
- end: `0x140002efb`
- name: `InstanceWaitLockRelease`
- size: `43`
- prototype: ``
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x140001b70`
- `0x140003c24`
- `0x1400043c8`
- `0x1400044b8`
- `0x140004780`
- `0x14000b4f0`
- `0x14000b800`
- `0x14000b980`
- `0x14000ba60`
- `0x140028354`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140002edd`
- `ntoskrnl!KeSetEvent` at `0x140002edd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002ee9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002ee9`

## pseudocode

```c
void __fastcall InstanceWaitLockRelease(__int64 a1)
{
  KeSetEvent((PRKEVENT)(a1 + 32), 0, 0);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x140002ed0  sub     rsp, 28h
0x140002ed4  add     rcx, 20h ; ' '; Event
0x140002ed8  xor     r8d, r8d; Wait
0x140002edb  xor     edx, edx; Increment
0x140002edd  call    cs:__imp_KeSetEvent
0x140002ee4  nop     dword ptr [rax+rax+00h]
0x140002ee9  call    cs:__imp_KeLeaveCriticalRegion
0x140002ef0  nop     dword ptr [rax+rax+00h]
0x140002ef5  add     rsp, 28h
0x140002ef9  retn
```
