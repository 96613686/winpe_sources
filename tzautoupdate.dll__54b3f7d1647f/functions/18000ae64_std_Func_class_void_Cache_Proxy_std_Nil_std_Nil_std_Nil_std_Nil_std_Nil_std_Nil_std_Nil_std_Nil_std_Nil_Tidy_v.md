# std::_Func_class<void,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::_Tidy(void)

- ea: `0x18000ae64`
- end: `0x18000ae96`
- name: `?_Tidy@?$_Func_class@XAEAVProxy@Cache@@U_Nil@std@@U34@U34@U34@U34@U34@U34@U34@U34@@std@@IEAAXXZ`
- size: `50`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800044ec`
- `0x180004528`
- `0x180014c60`

## callees

- `0x18000ae64`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall std::_Func_class<void,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::_Tidy(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  __int64 result; // rax

  v3 = *(_QWORD *)(a1 + 24);
  if ( v3 )
  {
    LOBYTE(a2) = v3 != a1;
    result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 32LL))(v3, a2);
    *(_QWORD *)(a1 + 24) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000ae64  push    rbx
0x18000ae66  sub     rsp, 20h
0x18000ae6a  mov     rbx, rcx
0x18000ae6d  mov     rcx, [rcx+18h]
0x18000ae71  test    rcx, rcx
0x18000ae74  jz      short loc_18000AE90
0x18000ae76  mov     rax, [rcx]
0x18000ae79  cmp     rcx, rbx
0x18000ae7c  setnz   dl
0x18000ae7f  mov     rax, [rax+20h]
0x18000ae83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae88  mov     qword ptr [rbx+18h], 0
0x18000ae90  add     rsp, 20h
0x18000ae94  pop     rbx
0x18000ae95  retn
```
