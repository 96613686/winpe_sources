# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Tidy(bool,unsigned __int64)

- ea: `0x1800134bc`
- end: `0x18001351e`
- name: `?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z`
- size: `98`
- prototype: ``
- caller_count: `16`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180010188`
- `0x1800108a4`
- `0x180010914`
- `0x180010c08`
- `0x180010cac`
- `0x1800111f4`
- `0x180011820`
- `0x180012ae8`
- `0x180012d3c`
- `0x180013588`
- `0x1800142b8`
- `0x180014484`
- `0x180014900`
- `0x1800151e0`
- `0x180015500`
- `0x18001d999`

## callees

- `0x1800134bc`
- `0x180013814`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800134ef`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800134ef`

## pseudocode

```c
__int64 __fastcall std::wstring::_Tidy(void **a1, char a2, __int64 a3)
{
  void *v5; // rsi
  __int64 result; // rax

  if ( a2 && (unsigned __int64)a1[3] >= 8 )
  {
    v5 = *a1;
    if ( a3 )
      std::char_traits<unsigned short>::copy(a1, *a1, a3);
    operator delete(v5);
  }
  result = 0;
  a1[3] = (void *)7;
  a1[2] = (void *)a3;
  *((_WORD *)a1 + a3) = 0;
  return result;
}

```

## disassembly

```asm
0x1800134bc  mov     [rsp+arg_0], rbx
0x1800134c1  mov     [rsp+arg_8], rsi
0x1800134c6  push    rdi
0x1800134c7  sub     rsp, 20h
0x1800134cb  mov     rdi, r8
0x1800134ce  mov     rbx, rcx
0x1800134d1  test    dl, dl
0x1800134d3  jz      short loc_1800134FB
0x1800134d5  cmp     qword ptr [rcx+18h], 8
0x1800134da  jb      short loc_1800134FB
0x1800134dc  mov     rsi, [rcx]
0x1800134df  test    r8, r8
0x1800134e2  jz      short loc_1800134EC
0x1800134e4  mov     rdx, rsi
0x1800134e7  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x1800134ec  mov     rcx, rsi
0x1800134ef  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800134f6  nop     dword ptr [rax+rax+00h]
0x1800134fb  mov     rsi, [rsp+28h+arg_8]
0x180013500  xor     eax, eax
0x180013502  mov     qword ptr [rbx+18h], 7
0x18001350a  mov     [rbx+10h], rdi
0x18001350e  mov     [rbx+rdi*2], ax
0x180013512  mov     rbx, [rsp+28h+arg_0]
0x180013517  add     rsp, 20h
0x18001351b  pop     rdi
0x18001351c  retn
```
