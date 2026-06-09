# __GSHandlerCheck

- ea: `0x140003684`
- end: `0x1400036a1`
- name: `__GSHandlerCheck`
- size: `29`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400036a8`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheck(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  _GSHandlerCheckCommon(a2, a4, *(_QWORD *)(a4 + 56));
  return 1;
}

```

## disassembly

```asm
0x140003684  sub     rsp, 28h
0x140003688  mov     r8, [r9+38h]
0x14000368c  mov     rcx, rdx
0x14000368f  mov     rdx, r9
0x140003692  call    __GSHandlerCheckCommon
0x140003697  mov     eax, 1
0x14000369c  add     rsp, 28h
0x1400036a0  retn
```
