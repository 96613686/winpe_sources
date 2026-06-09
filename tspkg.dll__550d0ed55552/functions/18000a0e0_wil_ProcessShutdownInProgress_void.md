# wil::ProcessShutdownInProgress(void)

- ea: `0x18000a0e0`
- end: `0x18000a10d`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `45`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000de40`
- `0x18000f0ec`
- `0x18000f3b4`
- `0x18000f7f4`
- `0x18000f874`
- `0x18001000c`
- `0x18001c7b0`

## callees

- `0x18000a0e0`
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
0x18000a0e0  sub     rsp, 28h
0x18000a0e4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000a0eb  jnz     short loc_18000A106
0x18000a0ed  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a0f4  test    rax, rax
0x18000a0f7  jz      short loc_18000A102
0x18000a0f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0fe  test    al, al
0x18000a100  jnz     short loc_18000A106
0x18000a102  xor     al, al
0x18000a104  jmp     short loc_18000A108
0x18000a106  mov     al, 1
0x18000a108  add     rsp, 28h
0x18000a10c  retn
```
