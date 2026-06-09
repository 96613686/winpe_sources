# CVssJetWriter::CVssJetWriter(void)

- ea: `0x180002040`
- end: `0x180002053`
- name: `??0CVssJetWriter@@QEAA@XZ`
- size: `19`
- prototype: `CVssJetWriter *__fastcall(CVssJetWriter *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
CVssJetWriter *__fastcall CVssJetWriter::CVssJetWriter(CVssJetWriter *this)
{
  *((_QWORD *)this + 1) = 0;
  *(_QWORD *)this = &CVssJetWriter::`vftable';
  return this;
}

```

## disassembly

```asm
0x180002040  and     qword ptr [rcx+8], 0
0x180002045  lea     rax, ??_7CVssJetWriter@@6B@; const CVssJetWriter::`vftable'
0x18000204c  mov     [rcx], rax
0x18000204f  mov     rax, rcx
0x180002052  retn
```
