# W3WP_HOST::AddRef(void)

- ea: `0x1800032a0`
- end: `0x1800032ad`
- name: `?AddRef@W3WP_HOST@@UEAAKXZ`
- size: `13`
- prototype: `unsigned int __fastcall(W3WP_HOST *__hidden this)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x1800032c0`
- `0x1800032d0`
- `0x1800032e0`
- `0x1800032f0`
- `0x180003300`
- `0x180003310`
- `0x180003320`
- `0x180003330`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::AddRef(W3WP_HOST *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 19);
}

```

## disassembly

```asm
0x1800032a0  mov     eax, 1
0x1800032a5  lock xadd [rcx+4Ch], eax
0x1800032aa  inc     eax
0x1800032ac  retn
```
