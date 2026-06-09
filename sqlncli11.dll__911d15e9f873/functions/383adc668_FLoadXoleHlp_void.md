# FLoadXoleHlp(void)

- ea: `0x383adc668`
- end: `0x383adc6a3`
- name: `?FLoadXoleHlp@@YAHXZ`
- size: `59`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x383adc6bc`

## callees

- `0x383adc668`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x383adc689`
- `KERNEL32!FreeLibrary` at `0x383adc689`
- `KERNEL32!LoadLibraryA` at `0x383adc673`
- `KERNEL32!LoadLibraryA` at `0x383adc673`

## string_xrefs

- `0x383adc66c`: `XOLEHLP.DLL`

## pseudocode

```c
_BOOL8 FLoadXoleHlp(void)
{
  HMODULE LibraryA; // rcx

  LibraryA = LoadLibraryA("XOLEHLP.DLL");
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hXoleHlpDll, (signed __int64)LibraryA, 0) )
    FreeLibrary(LibraryA);
  return g_hXoleHlpDll != 0;
}

```

## disassembly

```asm
0x383adc668  sub     rsp, 28h
0x383adc66c  lea     rcx, aXolehlpDll; "XOLEHLP.DLL"
0x383adc673  call    cs:__imp_LoadLibraryA
0x383adc679  mov     rcx, rax; hLibModule
0x383adc67c  xor     eax, eax
0x383adc67e  lock cmpxchg cs:?g_hXoleHlpDll@@3REAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hXoleHlpDll
0x383adc687  jz      short loc_383ADC68F
0x383adc689  call    cs:__imp_FreeLibrary
0x383adc68f  mov     rcx, cs:?g_hXoleHlpDll@@3REAUHINSTANCE__@@EA; HINSTANCE__ * g_hXoleHlpDll
0x383adc696  xor     eax, eax
0x383adc698  cmp     rcx, rax
0x383adc69b  setnz   al
0x383adc69e  add     rsp, 28h
0x383adc6a2  retn
```
