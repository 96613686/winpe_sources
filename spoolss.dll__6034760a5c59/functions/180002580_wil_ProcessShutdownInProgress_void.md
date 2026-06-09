# wil::ProcessShutdownInProgress(void)

- ea: `0x180002580`
- end: `0x1800025ad`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `45`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007dc8`
- `0x1800097ac`
- `0x18000984c`
- `0x180009bc4`
- `0x180009e24`
- `0x180009ea4`
- `0x18000b030`
- `0x180015220`
- `0x180015250`

## callees

- `0x180002580`
- `0x180016010`

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
0x180002580  sub     rsp, 28h
0x180002584  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000258b  jnz     short loc_1800025A6
0x18000258d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180002594  test    rax, rax
0x180002597  jz      short loc_1800025A2
0x180002599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000259e  test    al, al
0x1800025a0  jnz     short loc_1800025A6
0x1800025a2  xor     al, al
0x1800025a4  jmp     short loc_1800025A8
0x1800025a6  mov     al, 1
0x1800025a8  add     rsp, 28h
0x1800025ac  retn
```
