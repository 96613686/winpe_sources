# wil::ProcessShutdownInProgress(void)

- ea: `0x180005fe8`
- end: `0x180006015`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `45`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006e30`
- `0x180006f24`
- `0x180009a0c`
- `0x18000b364`
- `0x18000bed0`
- `0x18000c3ac`
- `0x18000fe40`

## callees

- `0x180005fe8`
- `0x180010010`

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
0x180005fe8  sub     rsp, 28h
0x180005fec  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180005ff3  jnz     short loc_18000600E
0x180005ff5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180005ffc  test    rax, rax
0x180005fff  jz      short loc_18000600A
0x180006001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006006  test    al, al
0x180006008  jnz     short loc_18000600E
0x18000600a  xor     al, al
0x18000600c  jmp     short loc_180006010
0x18000600e  mov     al, 1
0x180006010  add     rsp, 28h
0x180006014  retn
```
