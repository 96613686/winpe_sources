# Win32FreePool_0

- ea: `0x14001790a`
- end: `0x140017911`
- name: `Win32FreePool_0`
- size: `7`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `25`
- callee_count: `0`
- tags: ``

## callers

- `0x140003740`
- `0x140004cc0`
- `0x140004e40`
- `0x140005590`
- `0x1400096c0`
- `0x14000a400`
- `0x14000a5f0`
- `0x14000acb0`
- `0x14000bc20`
- `0x1400101f0`
- `0x1400133c0`
- `0x140013a70`
- `0x140013e50`
- `0x140014dd0`
- `0x1400153c0`
- `0x140015ac0`
- `0x140017440`
- `0x1400189a0`
- `0x140018ab0`
- `0x140018d00`
- `0x140018e10`
- `0x140018f20`
- `0x140019030`
- `0x140019140`
- `0x1400193b0`

## import_xrefs

- `win32kbase!Win32FreePool` at `0x14001790a`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Win32FreePool_0(__int64 a1)
{
  return Win32FreePool(a1);
}

```

## disassembly

```asm
0x14001790a  jmp     cs:__imp_Win32FreePool
```
