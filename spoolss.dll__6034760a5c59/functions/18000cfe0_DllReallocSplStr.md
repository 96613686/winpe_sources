# DllReallocSplStr

- ea: `0x18000cfe0`
- end: `0x18000d048`
- name: `DllReallocSplStr`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000de80`

## callees

- `0x180002e18`
- `0x1800046b0`
- `0x18000cfe0`
- `0x180016010`

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
0x18000cfe0  mov     [rsp+arg_0], rbx
0x18000cfe5  mov     [rsp+arg_8], rsi
0x18000cfea  push    rdi
0x18000cfeb  sub     rsp, 20h
0x18000cfef  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000cff6  mov     rdi, rdx
0x18000cff9  mov     rbx, rcx
0x18000cffc  jnz     short loc_18000D013
0x18000cffe  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000d005  mov     rax, [rax+3A0h]
0x18000d00c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d011  jmp     short loc_18000D038
0x18000d013  mov     rcx, rdi
0x18000d016  call    DllAllocSplStr
0x18000d01b  mov     rsi, rax
0x18000d01e  test    rdi, rdi
0x18000d021  jz      short loc_18000D028
0x18000d023  test    rax, rax
0x18000d026  jz      short loc_18000D038
0x18000d028  mov     rcx, [rbx]; this
0x18000d02b  call    ?DllFreeSplStr@newSpooler@@YAHPEAG@Z; newSpooler::DllFreeSplStr(ushort *)
0x18000d030  mov     eax, 1
0x18000d035  mov     [rbx], rsi
0x18000d038  mov     rbx, [rsp+28h+arg_0]
0x18000d03d  mov     rsi, [rsp+28h+arg_8]
0x18000d042  add     rsp, 20h
0x18000d046  pop     rdi
0x18000d047  retn
```
