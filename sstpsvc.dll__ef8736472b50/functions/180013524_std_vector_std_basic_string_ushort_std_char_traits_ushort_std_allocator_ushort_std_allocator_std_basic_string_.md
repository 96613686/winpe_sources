# std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::_Tidy(void)

- ea: `0x180013524`
- end: `0x18001357f`
- name: `?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ`
- size: `91`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180010640`
- `0x1800108a4`
- `0x18001093c`
- `0x180010b08`
- `0x180010d80`
- `0x1800111f4`
- `0x180011820`
- `0x180012648`
- `0x1800142b8`
- `0x180014484`
- `0x1800151e0`
- `0x18001d80a`
- `0x18001d846`

## callees

- `0x180010188`
- `0x180013524`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180013552`
- `msvcrt!??3@YAXPEAX@Z` at `0x180013552`

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
0x180013524  push    rbx
0x180013526  push    rbp
0x180013527  push    rsi
0x180013528  push    rdi
0x180013529  sub     rsp, 28h
0x18001352d  mov     rdi, [rcx]
0x180013530  mov     rbx, rcx
0x180013533  test    rdi, rdi
0x180013536  jz      short loc_18001355E
0x180013538  mov     rbp, [rcx+8]
0x18001353c  jmp     short loc_18001354A
0x18001353e  mov     rdx, rdi
0x180013541  call    ??$_Dest_val@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@std@@YAXAEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::_Dest_val<std::allocator<std::wstring>,std::wstring>(std::allocator<std::wstring> &,std::wstring *)
0x180013546  add     rdi, 28h ; '('
0x18001354a  cmp     rdi, rbp
0x18001354d  jnz     short loc_18001353E
0x18001354f  mov     rcx, [rbx]
0x180013552  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180013559  nop     dword ptr [rax+rax+00h]
0x18001355e  mov     qword ptr [rbx], 0
0x180013565  mov     qword ptr [rbx+8], 0
0x18001356d  mov     qword ptr [rbx+10h], 0
0x180013575  add     rsp, 28h
0x180013579  pop     rdi
0x18001357a  pop     rsi
0x18001357b  pop     rbp
0x18001357c  pop     rbx
0x18001357d  retn
```
