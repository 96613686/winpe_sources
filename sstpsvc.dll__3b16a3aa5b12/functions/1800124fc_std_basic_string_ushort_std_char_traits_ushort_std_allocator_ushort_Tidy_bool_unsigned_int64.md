# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Tidy(bool,unsigned __int64)

- ea: `0x1800124fc`
- end: `0x180012557`
- name: `?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z`
- size: `91`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000f3e0`
- `0x18000fad4`
- `0x18000fb38`
- `0x18000fe1c`
- `0x18000feb8`
- `0x1800103e8`
- `0x1800109ac`
- `0x180011b54`
- `0x180011d98`
- `0x1800125bc`
- `0x1800132c0`
- `0x180013464`
- `0x1800138c0`
- `0x180014170`
- `0x180014490`
- `0x18001c45d`

## callees

- `0x1800124fc`
- `0x180012848`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001252f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001252f`

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
0x1800124fc  mov     [rsp+arg_0], rbx
0x180012501  mov     [rsp+arg_8], rsi
0x180012506  push    rdi
0x180012507  sub     rsp, 20h
0x18001250b  mov     rdi, r8
0x18001250e  mov     rbx, rcx
0x180012511  test    dl, dl
0x180012513  jz      short loc_180012535
0x180012515  cmp     qword ptr [rcx+18h], 8
0x18001251a  jb      short loc_180012535
0x18001251c  mov     rsi, [rcx]
0x18001251f  test    r8, r8
0x180012522  jz      short loc_18001252C
0x180012524  mov     rdx, rsi
0x180012527  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x18001252c  mov     rcx, rsi
0x18001252f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180012535  mov     rsi, [rsp+28h+arg_8]
0x18001253a  xor     eax, eax
0x18001253c  mov     qword ptr [rbx+18h], 7
0x180012544  mov     [rbx+10h], rdi
0x180012548  mov     [rbx+rdi*2], ax
0x18001254c  mov     rbx, [rsp+28h+arg_0]
0x180012551  add     rsp, 20h
0x180012555  pop     rdi
0x180012556  retn
```
