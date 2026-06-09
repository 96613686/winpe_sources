# DllCanUnloadNow

- ea: `0x18000c0f0`
- end: `0x18000c10b`
- name: `DllCanUnloadNow`
- size: `27`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000c0f0`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rax

  if ( g_cServerLocks )
    LODWORD(v0) = 1;
  else
    return g_cRefDll != 0;
  return v0;
}

```

## disassembly

```asm
0x18000c0f0  cmp     cs:?g_cServerLocks@@3JA, 0; long g_cServerLocks
0x18000c0f7  jnz     short loc_18000C105
0x18000c0f9  xor     eax, eax
0x18000c0fb  cmp     cs:?g_cRefDll@@3JA, eax; long g_cRefDll
0x18000c101  setnz   al
0x18000c104  retn
0x18000c105  mov     eax, 1
0x18000c10a  retn
```
