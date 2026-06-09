# ATL::CComPtrBase<IFunctionInstance>::Release(void)

- ea: `0x180008430`
- end: `0x180008458`
- name: `?Release@?$CComPtrBase@UIFunctionInstance@@@ATL@@QEAAXXZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007b00`
- `0x18000a3e8`

## callees

- `0x180008430`
- `0x180012010`

## pseudocode

```c
_QWORD *__fastcall ATL::CComPtrBase<IFunctionInstance>::Release(_QWORD *a1)
{
  _QWORD *result; // rax
  __int64 v2; // rcx

  result = a1;
  v2 = *a1;
  if ( v2 )
  {
    *result = 0;
    return (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return result;
}

```

## disassembly

```asm
0x180008430  sub     rsp, 28h
0x180008434  mov     rax, rcx
0x180008437  mov     rcx, [rcx]
0x18000843a  test    rcx, rcx
0x18000843d  jz      short loc_180008453
0x18000843f  mov     qword ptr [rax], 0
0x180008446  mov     rax, [rcx]
0x180008449  mov     rax, [rax+10h]
0x18000844d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008452  nop
0x180008453  add     rsp, 28h
0x180008457  retn
```
