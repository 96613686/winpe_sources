# std::_Func_class<void,>::_Tidy(void)

- ea: `0x18000b938`
- end: `0x18000b96a`
- name: `?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ`
- size: `50`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a5c4`
- `0x18000a90c`
- `0x18000a918`
- `0x18000b9b0`

## callees

- `0x18000b938`
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
0x18000b938  push    rbx
0x18000b93a  sub     rsp, 20h
0x18000b93e  mov     rbx, rcx
0x18000b941  mov     rcx, [rcx+38h]
0x18000b945  test    rcx, rcx
0x18000b948  jz      short loc_18000B964
0x18000b94a  mov     rax, [rcx]
0x18000b94d  cmp     rcx, rbx
0x18000b950  setnz   dl
0x18000b953  mov     rax, [rax+20h]
0x18000b957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b95c  mov     qword ptr [rbx+38h], 0
0x18000b964  add     rsp, 20h
0x18000b968  pop     rbx
0x18000b969  retn
```
