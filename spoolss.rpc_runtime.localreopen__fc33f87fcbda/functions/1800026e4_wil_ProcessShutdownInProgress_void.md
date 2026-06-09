# wil::ProcessShutdownInProgress(void)

- ea: `0x1800026e4`
- end: `0x180002712`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `46`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008218`
- `0x180009f20`
- `0x180009fc4`
- `0x18000a354`
- `0x18000a5e0`
- `0x18000a66c`
- `0x18000b93c`
- `0x180016c20`
- `0x180016c50`

## callees

- `0x1800026e4`
- `0x180017010`

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
0x1800026e4  sub     rsp, 28h
0x1800026e8  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800026ef  jnz     short loc_18000270A
0x1800026f1  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800026f8  test    rax, rax
0x1800026fb  jz      short loc_180002706
0x1800026fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002702  test    al, al
0x180002704  jnz     short loc_18000270A
0x180002706  xor     al, al
0x180002708  jmp     short loc_18000270C
0x18000270a  mov     al, 1
0x18000270c  add     rsp, 28h
0x180002710  retn
```
