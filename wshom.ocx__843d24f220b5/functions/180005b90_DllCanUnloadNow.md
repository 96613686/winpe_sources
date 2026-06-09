# DllCanUnloadNow

- ea: `0x180005b90`
- end: `0x180005bb3`
- name: `DllCanUnloadNow`
- size: `35`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005b90`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return _InterlockedCompareExchange(&Global::g_cObjects, 0, 0) || _InterlockedCompareExchange(&Global::g_cLocks, 0, 0);
}

```

## disassembly

```asm
0x180005b90  xor     ecx, ecx
0x180005b92  xor     eax, eax
0x180005b94  lock cmpxchg cs:?g_cObjects@Global@@2JA, ecx; long Global::g_cObjects
0x180005b9c  jnz     short loc_180005BAD
0x180005b9e  xor     eax, eax
0x180005ba0  lock cmpxchg cs:?g_cLocks@Global@@2JA, ecx; long Global::g_cLocks
0x180005ba8  jnz     short loc_180005BAD
0x180005baa  xor     eax, eax
0x180005bac  retn
0x180005bad  mov     eax, 1
0x180005bb2  retn
```
