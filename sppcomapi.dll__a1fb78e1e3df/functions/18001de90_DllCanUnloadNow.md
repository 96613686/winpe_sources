# DllCanUnloadNow

- ea: `0x18001de90`
- end: `0x18001de9c`
- name: `DllCanUnloadNow`
- size: `12`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return CComProcessCounter<0>::g_lServerLockCount != 0;
}

```

## disassembly

```asm
0x18001de90  xor     eax, eax
0x18001de92  cmp     cs:?g_lServerLockCount@?$CComProcessCounter@$0A@@@0JA, eax; long CComProcessCounter<0>::g_lServerLockCount
0x18001de98  setnz   al
0x18001de9b  retn
```
