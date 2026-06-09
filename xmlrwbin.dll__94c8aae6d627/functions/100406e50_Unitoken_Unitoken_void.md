# Unitoken::Unitoken(void)

- ea: `0x100406e50`
- end: `0x100406e61`
- name: `??0Unitoken@@QEAA@XZ`
- size: `17`
- prototype: `Unitoken *__fastcall(Unitoken *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1004098d0`
- `0x10040af70`
- `0x100410010`

## pseudocode

```c
Unitoken *__fastcall Unitoken::Unitoken(Unitoken *this)
{
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  return this;
}

```

## disassembly

```asm
0x100406e50  xor     eax, eax
0x100406e52  mov     [rcx], rax
0x100406e55  mov     [rcx+8], rax
0x100406e59  mov     [rcx+10h], rax
0x100406e5d  mov     rax, rcx
0x100406e60  retn
```
