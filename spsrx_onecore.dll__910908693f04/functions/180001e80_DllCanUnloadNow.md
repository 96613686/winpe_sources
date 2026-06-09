# DllCanUnloadNow

- ea: `0x180001e80`
- end: `0x180001e8c`
- name: `DllCanUnloadNow`
- size: `12`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return HIDWORD(qword_1800152B8) != 0;
}

```

## disassembly

```asm
0x180001e80  xor     eax, eax
0x180001e82  cmp     dword ptr cs:qword_1800152B8+4, eax
0x180001e88  setnz   al
0x180001e8b  retn
```
