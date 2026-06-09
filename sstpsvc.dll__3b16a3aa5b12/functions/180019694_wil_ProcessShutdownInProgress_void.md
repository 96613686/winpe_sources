# wil::ProcessShutdownInProgress(void)

- ea: `0x180019694`
- end: `0x1800196c1`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `45`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180017fa4`
- `0x1800196c8`
- `0x180019a9c`
- `0x18001a148`
- `0x18001a1c8`
- `0x18001a9b4`
- `0x18001c5a0`

## callees

- `0x180019694`
- `0x18001d010`

## pseudocode

```c
bool __fastcall wil::ProcessShutdownInProgress(wil *this)
{
  return wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress(this);
}

```

## disassembly

```asm
0x180019694  sub     rsp, 28h
0x180019698  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001969f  jnz     short loc_1800196BA
0x1800196a1  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800196a8  test    rax, rax
0x1800196ab  jz      short loc_1800196B6
0x1800196ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196b2  test    al, al
0x1800196b4  jnz     short loc_1800196BA
0x1800196b6  xor     al, al
0x1800196b8  jmp     short loc_1800196BC
0x1800196ba  mov     al, 1
0x1800196bc  add     rsp, 28h
0x1800196c0  retn
```
