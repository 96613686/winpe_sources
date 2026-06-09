# __tailMerge_rpcrt4_dll

- ea: `0x18001ef90`
- end: `0x18001f009`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `39`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001f00f`
- `0x18001f137`
- `0x18001f149`
- `0x18001f15b`
- `0x18001f16d`
- `0x18001f17f`
- `0x18001f21c`
- `0x18001f22e`
- `0x18001f240`
- `0x18001f264`
- `0x18001f276`
- `0x18001f288`
- `0x18001f29a`
- `0x18001f2ac`
- `0x18001f2be`
- `0x18001f2d0`
- `0x18001f37f`
- `0x18001fa5c`
- `0x18001fa7c`
- `0x18001ff69`
- `0x18002002a`
- `0x18002004e`
- `0x180020072`
- `0x1800203ec`
- `0x18002040c`
- `0x18002041e`
- `0x180020430`
- `0x180020442`
- `0x180020454`
- `0x180020466`
- `0x180020478`
- `0x18002048a`
- `0x18002049c`
- `0x1800204ae`
- `0x1800204c0`
- `0x1800204d2`
- `0x1800204e4`
- `0x1800204f6`
- `0x180020508`

## callees

- `0x18000c9b0`
- `0x18001ef90`

## pseudocode

```c
__int64 __fastcall _tailMerge_rpcrt4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001ef90  mov     [rsp+arg_0], rcx
0x18001ef95  mov     [rsp+arg_8], rdx
0x18001ef9a  mov     [rsp+arg_10], r8
0x18001ef9f  mov     [rsp+arg_18], r9
0x18001efa4  sub     rsp, 68h
0x18001efa8  movdqa  [rsp+68h+var_48], xmm0
0x18001efae  movdqa  [rsp+68h+var_38], xmm1
0x18001efb4  movdqa  [rsp+68h+var_28], xmm2
0x18001efba  movdqa  [rsp+68h+var_18], xmm3
0x18001efc0  mov     rdx, rax
0x18001efc3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x18001efca  call    __delayLoadHelper2
0x18001efcf  movdqa  xmm0, [rsp+68h+var_48]
0x18001efd5  movdqa  xmm1, [rsp+68h+var_38]
0x18001efdb  movdqa  xmm2, [rsp+68h+var_28]
0x18001efe1  movdqa  xmm3, [rsp+68h+var_18]
0x18001efe7  mov     rcx, [rsp+68h+arg_0]
0x18001efec  mov     rdx, [rsp+68h+arg_8]
0x18001eff1  mov     r8, [rsp+68h+arg_10]
0x18001eff9  mov     r9, [rsp+68h+arg_18]
0x18001f001  add     rsp, 68h
0x18001f005  jmp     short $+2
0x18001f007  jmp     rax
```
