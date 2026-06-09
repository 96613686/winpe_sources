# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Tidy(bool,unsigned __int64)

- ea: `0x1800062d4`
- end: `0x18000632e`
- name: `?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z`
- size: `90`
- prototype: `__int64 __fastcall(_QWORD *, char, __int64)`
- caller_count: `65`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003b34`
- `0x180003c10`
- `0x180003dec`
- `0x180003f08`
- `0x180004434`
- `0x180004b80`
- `0x1800052cc`
- `0x180005ad0`
- `0x180005f68`
- `0x1800060e8`
- `0x180008068`
- `0x180008094`
- `0x180008188`
- `0x1800081e4`
- `0x1800083a0`
- `0x180008828`
- `0x180009170`
- `0x180009a10`
- `0x18000a938`
- `0x18000b260`
- `0x18000b300`
- `0x18000bae0`
- `0x18000d03c`
- `0x18000d15c`
- `0x18000d830`
- `0x18000d940`
- `0x18000da2c`
- `0x18000e2f8`
- `0x18000ef44`
- `0x18000f1f8`
- `0x18000f3d0`
- `0x18000fb2c`
- `0x18000fc80`
- `0x18000fd88`
- `0x1800103b8`
- `0x18001259c`
- `0x180014310`
- `0x1800145cc`
- `0x18001483c`
- `0x180015134`
- `0x18001546c`
- `0x1800155e8`
- `0x1800159e0`
- `0x180015c30`
- `0x180015dd4`
- `0x180016098`
- `0x1800161e4`
- `0x180016514`
- `0x1800165c0`
- `0x180017510`

## callees

- `0x1800034f0`
- `0x1800062d4`
- `0x180006780`

## pseudocode

```c
__int64 __fastcall std::wstring::_Tidy(_QWORD *a1, char a2, __int64 a3)
{
  void *v5; // rsi
  __int64 result; // rax

  if ( a2 && a1[3] >= 8u )
  {
    v5 = (void *)*a1;
    if ( a3 )
      std::char_traits<unsigned short>::copy(a1, *a1, a3);
    operator delete(v5);
  }
  result = 0;
  a1[3] = 7;
  a1[2] = a3;
  *((_WORD *)a1 + a3) = 0;
  return result;
}

```

## disassembly

```asm
0x1800062d4  mov     [rsp+arg_0], rbx
0x1800062d9  mov     [rsp+arg_8], rsi
0x1800062de  push    rdi
0x1800062df  sub     rsp, 20h
0x1800062e3  mov     rdi, r8
0x1800062e6  mov     rbx, rcx
0x1800062e9  test    dl, dl
0x1800062eb  jz      short loc_18000630C
0x1800062ed  cmp     qword ptr [rcx+18h], 8
0x1800062f2  jb      short loc_18000630C
0x1800062f4  mov     rsi, [rcx]
0x1800062f7  test    r8, r8
0x1800062fa  jz      short loc_180006304
0x1800062fc  mov     rdx, rsi
0x1800062ff  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x180006304  mov     rcx, rsi; void *
0x180006307  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000630c  mov     rsi, [rsp+28h+arg_8]
0x180006311  xor     eax, eax
0x180006313  mov     qword ptr [rbx+18h], 7
0x18000631b  mov     [rbx+10h], rdi
0x18000631f  mov     [rbx+rdi*2], ax
0x180006323  mov     rbx, [rsp+28h+arg_0]
0x180006328  add     rsp, 20h
0x18000632c  pop     rdi
0x18000632d  retn
```
