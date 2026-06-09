# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::compare(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x18000d1d8`
- end: `0x18000d238`
- name: `?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAH_K0PEBG0@Z`
- size: `96`
- prototype: `__int64 __fastcall(_QWORD *, __int64, unsigned __int64, _WORD *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000d048`
- `0x18000d260`

## callees

- `0x18000d1d8`

## pseudocode

```c
__int64 __fastcall std::wstring::compare(_QWORD *a1, __int64 a2, unsigned __int64 a3, _WORD *a4, unsigned __int64 a5)
{
  unsigned __int64 v6; // rax

  if ( a1[2] < a3 )
    a3 = a1[2];
  v6 = a5;
  if ( a3 < a5 )
    v6 = a3;
  if ( a1[3] >= 8u )
    a1 = (_QWORD *)*a1;
  if ( v6 )
  {
    while ( v6 )
    {
      if ( *(_WORD *)a1 != *a4 )
        return *(_WORD *)a1 < *a4 ? -1 : 1;
      a1 = (_QWORD *)((char *)a1 + 2);
      ++a4;
      --v6;
    }
  }
  if ( a3 >= a5 )
    return a3 != a5;
  else
    return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18000d1d8  cmp     [rcx+10h], r8
0x18000d1dc  mov     r10, r9
0x18000d1df  mov     rdx, [rsp+arg_20]
0x18000d1e4  cmovb   r8, [rcx+10h]
0x18000d1e9  mov     rax, rdx
0x18000d1ec  cmp     r8, rdx
0x18000d1ef  cmovb   rax, r8
0x18000d1f3  cmp     qword ptr [rcx+18h], 8
0x18000d1f8  jb      short loc_18000D1FD
0x18000d1fa  mov     rcx, [rcx]
0x18000d1fd  test    rax, rax
0x18000d200  jz      short loc_18000D226
0x18000d202  test    rax, rax
0x18000d205  jz      short loc_18000D226
0x18000d207  movzx   r9d, word ptr [rcx]
0x18000d20b  cmp     r9w, [r10]
0x18000d20f  jnz     short loc_18000D21E
0x18000d211  add     rcx, 2
0x18000d215  add     r10, 2
0x18000d219  dec     rax
0x18000d21c  jmp     short loc_18000D202
0x18000d21e  sbb     eax, eax
0x18000d220  and     eax, 0FFFFFFFEh
0x18000d223  inc     eax
0x18000d225  retn
0x18000d226  cmp     r8, rdx
0x18000d229  jnb     short loc_18000D22F
0x18000d22b  or      eax, 0FFFFFFFFh
0x18000d22e  retn
0x18000d22f  xor     eax, eax
0x18000d231  cmp     r8, rdx
0x18000d234  setnz   al
0x18000d237  retn
```
