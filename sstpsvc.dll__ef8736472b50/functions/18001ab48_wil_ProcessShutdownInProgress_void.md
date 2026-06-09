# wil::ProcessShutdownInProgress(void)

- ea: `0x18001ab48`
- end: `0x18001ab76`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `46`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001937c`
- `0x18001ab7c`
- `0x18001af74`
- `0x18001b64c`
- `0x18001b6d8`
- `0x18001bef8`
- `0x18001dae0`

## callees

- `0x18001ab48`
- `0x18001e010`

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
0x18001ab48  sub     rsp, 28h
0x18001ab4c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001ab53  jnz     short loc_18001AB6E
0x18001ab55  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001ab5c  test    rax, rax
0x18001ab5f  jz      short loc_18001AB6A
0x18001ab61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab66  test    al, al
0x18001ab68  jnz     short loc_18001AB6E
0x18001ab6a  xor     al, al
0x18001ab6c  jmp     short loc_18001AB70
0x18001ab6e  mov     al, 1
0x18001ab70  add     rsp, 28h
0x18001ab74  retn
```
