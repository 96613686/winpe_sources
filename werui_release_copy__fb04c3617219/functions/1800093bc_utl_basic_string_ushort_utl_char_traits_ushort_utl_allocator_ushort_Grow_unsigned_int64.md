# utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Grow(unsigned __int64)

- ea: `0x1800093bc`
- end: `0x180009401`
- name: `?_Grow@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAA_N_K@Z`
- size: `69`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180005b40`
- `0x180008dfc`
- `0x18000af28`
- `0x180010ccc`
- `0x180013580`

## callees

- `0x1800093bc`
- `0x180009498`
- `0x18000977c`

## pseudocode

```c
bool __fastcall utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Grow(
        _QWORD *a1)
{
  unsigned __int64 v1; // rax
  unsigned __int64 v2; // rdx
  __int64 v3; // rcx

  v1 = 2
     * utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::capacity(a1)
     + 1;
  if ( v1 < v2 )
    v1 = v2;
  if ( v1 > 0x3FFFFFFFFFFFFFF7LL )
    v1 = 0x3FFFFFFFFFFFFFF7LL;
  return v2 <= v1
      && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_GrowTo(
                            v3,
                            v1,
                            0x3FFFFFFFFFFFFFF7LL);
}

```

## disassembly

```asm
0x1800093bc  sub     rsp, 28h
0x1800093c0  call    ?capacity@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::capacity(void)
0x1800093c5  mov     r8, 3FFFFFFFFFFFFFF7h
0x1800093cf  lea     rax, ds:1[rax*2]
0x1800093d7  cmp     rax, rdx
0x1800093da  cmovb   rax, rdx
0x1800093de  cmp     rax, r8
0x1800093e1  cmova   rax, r8
0x1800093e5  cmp     rdx, rax
0x1800093e8  ja      short loc_1800093FA
0x1800093ea  mov     rdx, rax
0x1800093ed  call    ?_GrowTo@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAA_N_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_GrowTo(unsigned __int64)
0x1800093f2  test    al, al
0x1800093f4  jz      short loc_1800093FA
0x1800093f6  mov     al, 1
0x1800093f8  jmp     short loc_1800093FC
0x1800093fa  xor     al, al
0x1800093fc  add     rsp, 28h
0x180009400  retn
```
