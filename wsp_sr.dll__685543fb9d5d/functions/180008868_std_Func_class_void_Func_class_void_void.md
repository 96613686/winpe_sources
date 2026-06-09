# std::_Func_class<void,>::~_Func_class<void,>(void)

- ea: `0x180008868`
- end: `0x18000889b`
- name: `??1?$_Func_class@X$$V@std@@QEAA@XZ`
- size: `51`
- prototype: ``
- caller_count: `41`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d380`
- `0x18001db88`
- `0x18001dff4`
- `0x18001e200`
- `0x18001e390`
- `0x18001e5d4`
- `0x18001e790`
- `0x18001e88c`
- `0x18001ea08`
- `0x18001ebd0`
- `0x18001ed30`
- `0x18001eec0`
- `0x18001f18c`
- `0x18001f354`
- `0x18001f4e4`
- `0x18001f674`
- `0x18001f7d8`
- `0x18001fa48`
- `0x1800209d4`
- `0x180021480`
- `0x180021af0`
- `0x180021bf0`
- `0x180024f88`
- `0x180025014`
- `0x180027890`
- `0x18002798c`
- `0x180027a40`
- `0x180028078`
- `0x180028f20`
- `0x180029884`
- `0x180029f64`
- `0x18002ab20`
- `0x18002ae00`
- `0x18002b839`
- `0x18002b85d`
- `0x18002b927`
- `0x18002b9a7`
- `0x18002c21a`
- `0x18002c2a6`
- `0x18002c44a`
- `0x18002c86e`

## callees

- `0x180008868`
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
0x180008868  push    rbx
0x18000886a  sub     rsp, 20h
0x18000886e  mov     rbx, rcx
0x180008871  mov     rcx, [rcx+38h]
0x180008875  test    rcx, rcx
0x180008878  jz      short loc_180008894
0x18000887a  mov     rax, [rcx]
0x18000887d  cmp     rcx, rbx
0x180008880  setnz   dl
0x180008883  mov     rax, [rax+20h]
0x180008887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000888c  mov     qword ptr [rbx+38h], 0
0x180008894  add     rsp, 20h
0x180008898  pop     rbx
0x180008899  retn
```
