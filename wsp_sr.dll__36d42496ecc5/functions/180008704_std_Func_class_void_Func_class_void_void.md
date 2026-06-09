# std::_Func_class<void,>::~_Func_class<void,>(void)

- ea: `0x180008704`
- end: `0x180008736`
- name: `??1?$_Func_class@X$$V@std@@QEAA@XZ`
- size: `50`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `41`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d25c`
- `0x18001da60`
- `0x18001decc`
- `0x18001e0d4`
- `0x18001e264`
- `0x18001e4a8`
- `0x18001e664`
- `0x18001e75c`
- `0x18001e8d8`
- `0x18001eaa0`
- `0x18001ec00`
- `0x18001ed90`
- `0x18001f058`
- `0x18001f220`
- `0x18001f3b0`
- `0x18001f540`
- `0x18001f6a0`
- `0x18001f910`
- `0x180020874`
- `0x1800212f4`
- `0x180021950`
- `0x180021a50`
- `0x180024c98`
- `0x180024d20`
- `0x18002752c`
- `0x180027628`
- `0x1800276dc`
- `0x180027cdc`
- `0x180028ad0`
- `0x1800293f4`
- `0x180029ab8`
- `0x18002a653`
- `0x18002a933`
- `0x18002b35b`
- `0x18002b37f`
- `0x18002b447`
- `0x18002b4c7`
- `0x18002bd26`
- `0x18002bdb2`
- `0x18002bf53`
- `0x18002c36b`

## callees

- `0x180008704`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall std::_Func_class<void,>::~_Func_class<void,>(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  __int64 result; // rax

  v3 = *(_QWORD *)(a1 + 56);
  if ( v3 )
  {
    LOBYTE(a2) = v3 != a1;
    result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 32LL))(v3, a2);
    *(_QWORD *)(a1 + 56) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180008704  push    rbx
0x180008706  sub     rsp, 20h
0x18000870a  mov     rbx, rcx
0x18000870d  mov     rcx, [rcx+38h]
0x180008711  test    rcx, rcx
0x180008714  jz      short loc_180008730
0x180008716  mov     rax, [rcx]
0x180008719  cmp     rcx, rbx
0x18000871c  setnz   dl
0x18000871f  mov     rax, [rax+20h]
0x180008723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008728  mov     qword ptr [rbx+38h], 0
0x180008730  add     rsp, 20h
0x180008734  pop     rbx
0x180008735  retn
```
