# std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::_Tidy(void)

- ea: `0x180012560`
- end: `0x1800125b4`
- name: `?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ`
- size: `84`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `13`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000f888`
- `0x18000fad4`
- `0x18000fb60`
- `0x18000fd1c`
- `0x18000ff74`
- `0x1800103e8`
- `0x1800109ac`
- `0x180011700`
- `0x1800132c0`
- `0x180013464`
- `0x180014170`
- `0x18001c2ce`
- `0x18001c30a`

## callees

- `0x18000f3e0`
- `0x180012560`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001258e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001258e`

## pseudocode

```c
void __fastcall std::vector<std::wstring>::_Tidy(void **a1)
{
  char *v1; // rdi
  char *v3; // rbp

  v1 = (char *)*a1;
  if ( *a1 )
  {
    v3 = (char *)a1[1];
    while ( v1 != v3 )
    {
      std::_Dest_val<std::allocator<std::wstring>,std::wstring>(a1, v1);
      v1 += 40;
    }
    operator delete(*a1);
  }
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
}

```

## disassembly

```asm
0x180012560  push    rbx
0x180012562  push    rbp
0x180012563  push    rsi
0x180012564  push    rdi
0x180012565  sub     rsp, 28h
0x180012569  mov     rdi, [rcx]
0x18001256c  mov     rbx, rcx
0x18001256f  test    rdi, rdi
0x180012572  jz      short loc_180012594
0x180012574  mov     rbp, [rcx+8]
0x180012578  jmp     short loc_180012586
0x18001257a  mov     rdx, rdi
0x18001257d  call    ??$_Dest_val@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@std@@YAXAEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::_Dest_val<std::allocator<std::wstring>,std::wstring>(std::allocator<std::wstring> &,std::wstring *)
0x180012582  add     rdi, 28h ; '('
0x180012586  cmp     rdi, rbp
0x180012589  jnz     short loc_18001257A
0x18001258b  mov     rcx, [rbx]
0x18001258e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180012594  mov     qword ptr [rbx], 0
0x18001259b  mov     qword ptr [rbx+8], 0
0x1800125a3  mov     qword ptr [rbx+10h], 0
0x1800125ab  add     rsp, 28h
0x1800125af  pop     rdi
0x1800125b0  pop     rsi
0x1800125b1  pop     rbp
0x1800125b2  pop     rbx
0x1800125b3  retn
```
