# W3WP_HOST::AddRef(void)

- ea: `0x1800030b0`
- end: `0x1800030bd`
- name: `?AddRef@W3WP_HOST@@UEAAKXZ`
- size: `13`
- prototype: `unsigned int __fastcall(W3WP_HOST *__hidden this)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x1800030d0`
- `0x1800030e0`
- `0x1800030f0`
- `0x180003100`
- `0x180003110`
- `0x180003120`
- `0x180003130`
- `0x180003140`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::AddRef(W3WP_HOST *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 19);
}

```

## disassembly

```asm
0x1800030b0  mov     eax, 1
0x1800030b5  lock xadd [rcx+4Ch], eax
0x1800030ba  inc     eax
0x1800030bc  retn
```
