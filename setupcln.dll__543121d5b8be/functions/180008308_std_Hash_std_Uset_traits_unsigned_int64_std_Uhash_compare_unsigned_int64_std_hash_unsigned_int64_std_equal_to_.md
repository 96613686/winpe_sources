# std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Check_size(void)

- ea: `0x180008308`
- end: `0x1800083a6`
- name: `?_Check_size@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEAAXXZ`
- size: `158`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003754`
- `0x180003894`

## callees

- `0x180008308`
- `0x1800085a4`
- `0x180008900`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Check_size(
        __int64 a1)
{
  __int64 v1; // r8
  unsigned __int64 v3; // rdx
  float v4; // xmm0_4
  __int64 result; // rax
  float v6; // xmm1_4

  v1 = *(_QWORD *)(a1 + 8);
  v3 = *(_QWORD *)(a1 + 48);
  if ( v1 < 0 )
  {
    result = *(_QWORD *)(a1 + 8) & 1LL | (*(_QWORD *)(a1 + 8) >> 1);
    v4 = (float)(int)result + (float)(int)result;
  }
  else
  {
    v4 = (float)(int)v1;
  }
  if ( (v3 & 0x8000000000000000uLL) != 0LL )
  {
    result = *(_QWORD *)(a1 + 48) & 1LL;
    v6 = (float)(int)(result | (v3 >> 1)) + (float)(int)(result | (v3 >> 1));
  }
  else
  {
    v6 = (float)(int)v3;
  }
  if ( (float)(v4 / v6) > *(float *)(a1 + 56) )
  {
    if ( v3 >= 0x200 )
    {
      if ( v3 < 0xFFFFFFFFFFFFFFFLL )
        v3 *= 2LL;
    }
    else
    {
      v3 *= 8LL;
    }
    std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Init(
      a1,
      v3);
    return std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Reinsert(a1);
  }
  return result;
}

```

## disassembly

```asm
0x180008308  push    rbx
0x18000830a  sub     rsp, 20h
0x18000830e  mov     r8, [rcx+8]
0x180008312  mov     rbx, rcx
0x180008315  mov     rdx, [rcx+30h]
0x180008319  xorps   xmm0, xmm0
0x18000831c  test    r8, r8
0x18000831f  js      short loc_180008328
0x180008321  cvtsi2ss xmm0, r8
0x180008326  jmp     short loc_18000833E
0x180008328  mov     rax, r8
0x18000832b  and     r8d, 1
0x18000832f  shr     rax, 1
0x180008332  or      rax, r8
0x180008335  cvtsi2ss xmm0, rax
0x18000833a  addss   xmm0, xmm0
0x18000833e  xorps   xmm1, xmm1
0x180008341  test    rdx, rdx
0x180008344  js      short loc_18000834D
0x180008346  cvtsi2ss xmm1, rdx
0x18000834b  jmp     short loc_180008365
0x18000834d  mov     rax, rdx
0x180008350  mov     rcx, rdx
0x180008353  shr     rcx, 1
0x180008356  and     eax, 1
0x180008359  or      rcx, rax
0x18000835c  cvtsi2ss xmm1, rcx
0x180008361  addss   xmm1, xmm1
0x180008365  divss   xmm0, xmm1
0x180008369  comiss  xmm0, dword ptr [rbx+38h]
0x18000836d  jbe     short loc_1800083A0
0x18000836f  cmp     rdx, 200h
0x180008376  jnb     short loc_18000837E
0x180008378  shl     rdx, 3
0x18000837c  jmp     short loc_180008390
0x18000837e  mov     rax, 0FFFFFFFFFFFFFFFh
0x180008388  cmp     rdx, rax
0x18000838b  jnb     short loc_180008390
0x18000838d  add     rdx, rdx
0x180008390  mov     rcx, rbx
0x180008393  call    ?_Init@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Init(unsigned __int64)
0x180008398  mov     rcx, rbx
0x18000839b  call    ?_Reinsert@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Reinsert(void)
0x1800083a0  add     rsp, 20h
0x1800083a4  pop     rbx
0x1800083a5  retn
```
