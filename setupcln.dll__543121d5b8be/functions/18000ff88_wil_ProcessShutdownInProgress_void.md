# wil::ProcessShutdownInProgress(void)

- ea: `0x18000ff88`
- end: `0x18000ffb5`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `45`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000e614`
- `0x18000ffbc`
- `0x18001038c`
- `0x180010a84`
- `0x180010b04`
- `0x180011554`
- `0x1800139b0`

## callees

- `0x18000ff88`
- `0x180014010`

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
0x18000ff88  sub     rsp, 28h
0x18000ff8c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000ff93  jnz     short loc_18000FFAE
0x18000ff95  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ff9c  test    rax, rax
0x18000ff9f  jz      short loc_18000FFAA
0x18000ffa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffa6  test    al, al
0x18000ffa8  jnz     short loc_18000FFAE
0x18000ffaa  xor     al, al
0x18000ffac  jmp     short loc_18000FFB0
0x18000ffae  mov     al, 1
0x18000ffb0  add     rsp, 28h
0x18000ffb4  retn
```
