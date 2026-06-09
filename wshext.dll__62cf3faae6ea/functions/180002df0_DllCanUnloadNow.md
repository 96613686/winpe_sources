# DllCanUnloadNow

- ea: `0x180002df0`
- end: `0x180002e31`
- name: `DllCanUnloadNow`
- size: `65`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002df0`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return _InterlockedCompareExchange((volatile signed __int32 *)&g_cRefPropSheet, 0, 0)
      || _InterlockedCompareExchange(&g_crefDll, 0, 0) >= 1
      || _InterlockedCompareExchange(&Global::g_cObjects, 0, 0)
      || _InterlockedCompareExchange(&Global::g_cLocks, 0, 0);
}

```

## disassembly

```asm
0x180002df0  xor     ecx, ecx
0x180002df2  xor     eax, eax
0x180002df4  lock cmpxchg cs:?g_cRefPropSheet@@3IA, ecx; uint g_cRefPropSheet
0x180002dfc  cmp     eax, 1
0x180002dff  jnb     short loc_180002E2B
0x180002e01  xor     eax, eax
0x180002e03  lock cmpxchg cs:?g_crefDll@@3JA, ecx; long g_crefDll
0x180002e0b  cmp     eax, 1
0x180002e0e  jge     short loc_180002E2B
0x180002e10  xor     eax, eax
0x180002e12  lock cmpxchg cs:?g_cObjects@Global@@2JA, ecx; long Global::g_cObjects
0x180002e1a  jnz     short loc_180002E2B
0x180002e1c  xor     eax, eax
0x180002e1e  lock cmpxchg cs:?g_cLocks@Global@@2JA, ecx; long Global::g_cLocks
0x180002e26  jnz     short loc_180002E2B
0x180002e28  xor     eax, eax
0x180002e2a  retn
0x180002e2b  mov     eax, 1
0x180002e30  retn
```
