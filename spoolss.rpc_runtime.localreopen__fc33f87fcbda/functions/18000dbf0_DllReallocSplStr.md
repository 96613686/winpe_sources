# DllReallocSplStr

- ea: `0x18000dbf0`
- end: `0x18000dc59`
- name: `DllReallocSplStr`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000ec50`

## callees

- `0x180002a94`
- `0x1800049e0`
- `0x18000dbf0`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall DllReallocSplStr(newSpooler **a1, __int64 a2)
{
  __int64 result; // rax
  unsigned __int16 *v5; // rdx
  newSpooler *v6; // rsi

  if ( !g_bSandbox )
    return (*((__int64 (**)(void))g_pSpoolSvForwards + 116))();
  result = DllAllocSplStr(a2);
  v6 = (newSpooler *)result;
  if ( !a2 || result )
  {
    newSpooler::DllFreeSplStr(*a1, v5);
    result = 1;
    *a1 = v6;
  }
  return result;
}

```

## disassembly

```asm
0x18000dbf0  mov     [rsp+arg_0], rbx
0x18000dbf5  mov     [rsp+arg_8], rsi
0x18000dbfa  push    rdi
0x18000dbfb  sub     rsp, 20h
0x18000dbff  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000dc06  mov     rdi, rdx
0x18000dc09  mov     rbx, rcx
0x18000dc0c  jnz     short loc_18000DC23
0x18000dc0e  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000dc15  mov     rax, [rax+3A0h]
0x18000dc1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc21  jmp     short loc_18000DC48
0x18000dc23  mov     rcx, rdi
0x18000dc26  call    DllAllocSplStr
0x18000dc2b  mov     rsi, rax
0x18000dc2e  test    rdi, rdi
0x18000dc31  jz      short loc_18000DC38
0x18000dc33  test    rax, rax
0x18000dc36  jz      short loc_18000DC48
0x18000dc38  mov     rcx, [rbx]; this
0x18000dc3b  call    ?DllFreeSplStr@newSpooler@@YAHPEAG@Z; newSpooler::DllFreeSplStr(ushort *)
0x18000dc40  mov     eax, 1
0x18000dc45  mov     [rbx], rsi
0x18000dc48  mov     rbx, [rsp+28h+arg_0]
0x18000dc4d  mov     rsi, [rsp+28h+arg_8]
0x18000dc52  add     rsp, 20h
0x18000dc56  pop     rdi
0x18000dc57  retn
```
