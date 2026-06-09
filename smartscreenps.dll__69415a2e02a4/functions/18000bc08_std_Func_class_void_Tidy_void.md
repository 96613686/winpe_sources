# std::_Func_class<void,>::_Tidy(void)

- ea: `0x18000bc08`
- end: `0x18000bc3b`
- name: `?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ`
- size: `51`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a838`
- `0x18000ab94`
- `0x18000aba0`
- `0x18000bc90`

## callees

- `0x18000bc08`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall std::_Func_class<void,>::_Tidy(__int64 a1, __int64 a2)
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
0x18000bc08  push    rbx
0x18000bc0a  sub     rsp, 20h
0x18000bc0e  mov     rbx, rcx
0x18000bc11  mov     rcx, [rcx+38h]
0x18000bc15  test    rcx, rcx
0x18000bc18  jz      short loc_18000BC34
0x18000bc1a  mov     rax, [rcx]
0x18000bc1d  cmp     rcx, rbx
0x18000bc20  setnz   dl
0x18000bc23  mov     rax, [rax+20h]
0x18000bc27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc2c  mov     qword ptr [rbx+38h], 0
0x18000bc34  add     rsp, 20h
0x18000bc38  pop     rbx
0x18000bc39  retn
```
