# SXReader::AddRef(void)

- ea: `0x100404860`
- end: `0x100404870`
- name: `?AddRef@SXReader@@UEAAKXZ`
- size: `16`
- prototype: `unsigned int __fastcall(SXReader *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x100406430`
- `0x100406480`

## pseudocode

```c
__int64 __fastcall SXReader::AddRef(SXReader *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 368);
}

```

## disassembly

```asm
0x100404860  mov     eax, 1
0x100404865  lock xadd [rcx+5C0h], eax
0x10040486d  inc     eax
0x10040486f  retn
```
