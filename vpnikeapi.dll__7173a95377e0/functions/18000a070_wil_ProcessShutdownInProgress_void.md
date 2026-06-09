# wil::ProcessShutdownInProgress(void)

- ea: `0x18000a070`
- end: `0x18000a09d`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `45`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008788`
- `0x18000a0a4`
- `0x18000a4dc`
- `0x18000ab9c`
- `0x18000ac1c`
- `0x18000b348`
- `0x18000d460`
- `0x18000d490`

## callees

- `0x18000a070`
- `0x18000e010`

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
0x18000a070  sub     rsp, 28h
0x18000a074  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000a07b  jnz     short loc_18000A096
0x18000a07d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a084  test    rax, rax
0x18000a087  jz      short loc_18000A092
0x18000a089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a08e  test    al, al
0x18000a090  jnz     short loc_18000A096
0x18000a092  xor     al, al
0x18000a094  jmp     short loc_18000A098
0x18000a096  mov     al, 1
0x18000a098  add     rsp, 28h
0x18000a09c  retn
```
