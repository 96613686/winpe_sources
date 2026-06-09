# wistd::__function::__func<_lambda_e92a0cc36032b557b0292d38c83af5d4_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::__move(wistd::__function::__base<long (wchar_t *,unsigned __int64,unsigned __int64 *)> *)

- ea: `0x18000a2f0`
- end: `0x18000a303`
- name: `?__move@?$__func@V_lambda_e92a0cc36032b557b0292d38c83af5d4_@@$$A6AJPEA_W_KPEA_K@Z@__function@wistd@@UEAAXPEAV?$__base@$$A6AJPEA_W_KPEA_K@Z@23@@Z`
- size: `19`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall wistd::__function::__func<_lambda_e92a0cc36032b557b0292d38c83af5d4_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::__move(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax

  *a2 = &wistd::__function::__func<_lambda_e92a0cc36032b557b0292d38c83af5d4_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::`vftable';
  result = *(_QWORD *)(a1 + 8);
  a2[1] = result;
  return result;
}

```

## disassembly

```asm
0x18000a2f0  lea     rax, ??_7?$__func@V_lambda_e92a0cc36032b557b0292d38c83af5d4_@@$$A6AJPEA_W_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_e92a0cc36032b557b0292d38c83af5d4_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x18000a2f7  mov     [rdx], rax
0x18000a2fa  mov     rax, [rcx+8]
0x18000a2fe  mov     [rdx+8], rax
0x18000a302  retn
```
