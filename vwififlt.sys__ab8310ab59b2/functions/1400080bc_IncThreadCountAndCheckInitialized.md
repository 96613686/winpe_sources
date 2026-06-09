# IncThreadCountAndCheckInitialized

- ea: `0x1400080bc`
- end: `0x1400080dd`
- name: `IncThreadCountAndCheckInitialized`
- size: `33`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1400038f0`
- `0x1400069a0`
- `0x140006bc0`
- `0x140007f70`
- `0x14000a260`
- `0x14000e6e0`
- `0x14000e7b0`
- `0x14000e880`
- `0x14000e960`

## callees

- `0x1400080bc`

## pseudocode

```c
__int64 IncThreadCountAndCheckInitialized()
{
  _InterlockedIncrement(&g_lThreadCount);
  if ( g_fModuleInitialized )
    return 0;
  _InterlockedDecrement(&g_lThreadCount);
  return 3221225860LL;
}

```

## disassembly

```asm
0x1400080bc  lock inc cs:g_lThreadCount
0x1400080c3  cmp     cs:g_fModuleInitialized, 0
0x1400080ca  jz      short loc_1400080D0
0x1400080cc  xor     eax, eax
0x1400080ce  retn
0x1400080d0  lock dec cs:g_lThreadCount
0x1400080d7  mov     eax, 0C0000184h
0x1400080dc  retn
```
