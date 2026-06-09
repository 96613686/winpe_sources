# std::_Tree_buy<_DismReleaseType,std::allocator<_DismReleaseType>>::_Buynode0(void)

- ea: `0x1800037d8`
- end: `0x18000381b`
- name: `?_Buynode0@?$_Tree_buy@W4_DismReleaseType@@V?$allocator@W4_DismReleaseType@@@std@@@std@@QEAAPEAU?$_Tree_node@W4_DismReleaseType@@PEAX@2@XZ`
- size: `67`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002d1c`

## callees

- `0x180001064`
- `0x180001398`
- `0x1800037d8`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_buy<enum _DismReleaseType>::_Buynode0(_QWORD *a1)
{
  _QWORD *result; // rax

  result = operator new(0x20u);
  if ( !result )
    std::_Xbad_alloc();
  *result = *a1;
  result[1] = *a1;
  result[2] = *a1;
  return result;
}

```

## disassembly

```asm
0x1800037d8  push    rbx
0x1800037da  sub     rsp, 20h
0x1800037de  mov     rbx, rcx
0x1800037e1  mov     ecx, 20h ; ' '; Size
0x1800037e6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800037eb  mov     rdx, rax
0x1800037ee  mov     [rsp+28h+arg_8], rax
0x1800037f3  test    rax, rax
0x1800037f6  jz      short loc_180003815
0x1800037f8  mov     rax, [rbx]
0x1800037fb  mov     [rdx], rax
0x1800037fe  mov     rax, [rbx]
0x180003801  mov     [rdx+8], rax
0x180003805  mov     rax, [rbx]
0x180003808  mov     [rdx+10h], rax
0x18000380c  mov     rax, rdx
0x18000380f  add     rsp, 20h
0x180003813  pop     rbx
0x180003814  retn
0x180003815  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
