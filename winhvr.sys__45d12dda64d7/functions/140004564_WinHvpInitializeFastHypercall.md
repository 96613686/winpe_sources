# WinHvpInitializeFastHypercall

- ea: `0x140004564`
- end: `0x140004574`
- name: `WinHvpInitializeFastHypercall`
- size: `16`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x14001d9e0`
- `0x14001fb40`
- `0x14001fd00`
- `0x140021030`
- `0x140022bc0`
- `0x140023820`
- `0x140023920`

## pseudocode

```c
void __fastcall WinHvpInitializeFastHypercall(_QWORD *a1)
{
  *a1 = 0;
  a1[1] = 0;
}

```

## disassembly

```asm
0x140004564  mov     qword ptr [rcx], 0
0x14000456b  mov     qword ptr [rcx+8], 0
0x140004573  retn
```
