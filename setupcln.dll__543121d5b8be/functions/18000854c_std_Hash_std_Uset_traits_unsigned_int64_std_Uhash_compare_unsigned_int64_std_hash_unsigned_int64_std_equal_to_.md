# std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Hashval(unsigned __int64 const &)

- ea: `0x18000854c`
- end: `0x18000859c`
- name: `?_Hashval@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEBA_KAEB_K@Z`
- size: `80`
- prototype: `unsigned __int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003754`
- `0x180003894`
- `0x1800071a8`
- `0x1800089c8`

## callees

- `0x18000854c`

## pseudocode

```c
unsigned __int64 __fastcall std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Hashval(
        __int64 a1,
        __int64 a2)
{
  unsigned __int64 v3; // r8
  unsigned __int64 i; // r9
  __int64 v5; // rax
  unsigned __int64 v6; // rcx
  unsigned __int64 result; // rax

  v3 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 8; ++i )
  {
    v5 = *(unsigned __int8 *)(a2 + i);
    v3 = 0x100000001B3LL * (v5 ^ v3);
  }
  v6 = *(_QWORD *)(a1 + 40);
  result = v6 & (v3 ^ HIDWORD(v3));
  if ( *(_QWORD *)(a1 + 48) <= result )
    return result - (v6 >> 1) - 1;
  return result;
}

```

## disassembly

```asm
0x18000854c  mov     r10, rcx
0x18000854f  mov     r8, 0CBF29CE484222325h
0x180008559  xor     r9d, r9d
0x18000855c  movzx   eax, byte ptr [rdx+r9]
0x180008561  mov     rcx, 100000001B3h
0x18000856b  xor     r8, rax
0x18000856e  inc     r9
0x180008571  imul    r8, rcx
0x180008575  cmp     r9, 8
0x180008579  jb      short loc_18000855C
0x18000857b  mov     rcx, [r10+28h]
0x18000857f  mov     rax, r8
0x180008582  shr     rax, 20h
0x180008586  xor     rax, r8
0x180008589  and     rax, rcx
0x18000858c  cmp     [r10+30h], rax
0x180008590  ja      short locret_18000859B
0x180008592  shr     rcx, 1
0x180008595  sub     rax, rcx
0x180008598  dec     rax
0x18000859b  retn
```
