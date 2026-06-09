# DllCanUnloadNow

- ea: `0x180008f70`
- end: `0x180008f8b`
- name: `DllCanUnloadNow`
- size: `27`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008f70`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rax

  if ( lLock )
    LODWORD(v0) = 1;
  else
    return lObj != 0;
  return v0;
}

```

## disassembly

```asm
0x180008f70  cmp     cs:?lLock@@3JA, 0; long lLock
0x180008f77  jnz     short loc_180008F85
0x180008f79  xor     eax, eax
0x180008f7b  cmp     cs:?lObj@@3JA, eax; long lObj
0x180008f81  setnz   al
0x180008f84  retn
0x180008f85  mov     eax, 1
0x180008f8a  retn
```
