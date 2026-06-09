# SXWriter::AddRef(void)

- ea: `0x100408240`
- end: `0x100408250`
- name: `?AddRef@SXWriter@@UEAAKXZ`
- size: `16`
- prototype: `unsigned int __fastcall(SXWriter *__hidden this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x100407c10`
- `0x100407c20`
- `0x100407c70`
- `0x100407cb0`
- `0x100407cc0`
- `0x100407d00`
- `0x100407d10`

## pseudocode

```c
__int64 __fastcall SXWriter::AddRef(SXWriter *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 59);
}

```

## disassembly

```asm
0x100408240  mov     eax, 1
0x100408245  lock xadd [rcx+0ECh], eax
0x10040824d  inc     eax
0x10040824f  retn
```
