# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::compare(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x180010bd0`
- end: `0x180010c30`
- name: `?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAH_K0PEBG0@Z`
- size: `96`
- prototype: `__int64 __fastcall(_QWORD *, __int64, unsigned __int64, _WORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010ba0`

## callees

- `0x180010bd0`

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
0x180010bd0  cmp     [rcx+10h], r8
0x180010bd4  mov     r10, r9
0x180010bd7  mov     rdx, [rsp+arg_20]
0x180010bdc  cmovb   r8, [rcx+10h]
0x180010be1  mov     rax, rdx
0x180010be4  cmp     r8, rdx
0x180010be7  cmovb   rax, r8
0x180010beb  cmp     qword ptr [rcx+18h], 8
0x180010bf0  jb      short loc_180010BF5
0x180010bf2  mov     rcx, [rcx]
0x180010bf5  test    rax, rax
0x180010bf8  jz      short loc_180010C1E
0x180010bfa  test    rax, rax
0x180010bfd  jz      short loc_180010C1E
0x180010bff  movzx   r9d, word ptr [rcx]
0x180010c03  cmp     r9w, [r10]
0x180010c07  jnz     short loc_180010C16
0x180010c09  add     rcx, 2
0x180010c0d  add     r10, 2
0x180010c11  dec     rax
0x180010c14  jmp     short loc_180010BFA
0x180010c16  sbb     eax, eax
0x180010c18  and     eax, 0FFFFFFFEh
0x180010c1b  inc     eax
0x180010c1d  retn
0x180010c1e  cmp     r8, rdx
0x180010c21  jnb     short loc_180010C27
0x180010c23  or      eax, 0FFFFFFFFh
0x180010c26  retn
0x180010c27  xor     eax, eax
0x180010c29  cmp     r8, rdx
0x180010c2c  setnz   al
0x180010c2f  retn
```
