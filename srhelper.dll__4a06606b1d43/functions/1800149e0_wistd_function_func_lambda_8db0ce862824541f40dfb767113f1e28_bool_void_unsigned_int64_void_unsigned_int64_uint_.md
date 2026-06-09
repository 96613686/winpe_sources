# wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::__move(wistd::__function::__base<bool (void *,unsigned __int64,void *,unsigned __int64,uint)> *)

- ea: `0x1800149e0`
- end: `0x1800149fd`
- name: `?__move@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXPEAV?$__base@$$A6A_NPEAX_K01I@Z@23@@Z`
- size: `29`
- prototype: `void **__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void **__fastcall wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::__move(
        __int64 a1,
        __int64 a2)
{
  void **result; // rax

  result = &wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::`vftable';
  *(_QWORD *)a2 = &wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::`vftable';
  *(_OWORD *)(a2 + 8) = *(_OWORD *)(a1 + 8);
  *(_QWORD *)(a2 + 24) = *(_QWORD *)(a1 + 24);
  return result;
}

```

## disassembly

```asm
0x1800149e0  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x1800149e7  mov     [rdx], rax
0x1800149ea  movups  xmm0, xmmword ptr [rcx+8]
0x1800149ee  movups  xmmword ptr [rdx+8], xmm0
0x1800149f2  movsd   xmm1, qword ptr [rcx+18h]
0x1800149f7  movsd   qword ptr [rdx+18h], xmm1
0x1800149fc  retn
```
