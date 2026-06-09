# PtReleaseSessionDevice

- ea: `0x140001724`
- end: `0x140001733`
- name: `PtReleaseSessionDevice`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400092f0`

## callees

- `0x140002c9c`

## pseudocode

```c
void __fastcall PtReleaseSessionDevice(_QWORD *a1, int a2, int a3)
{
  TiRemoveDeviceFromSession(a1, a2, a3);
}

```

## disassembly

```asm
0x140001724  sub     rsp, 28h
0x140001728  call    TiRemoveDeviceFromSession
0x14000172d  add     rsp, 28h
0x140001731  retn
```
