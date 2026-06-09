# XamlResourceUtils::EscapeWString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x140025bc4`
- end: `0x140025c42`
- name: `?EscapeWString@XamlResourceUtils@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140025c48`

## callees

- `0x140022d84`
- `0x140025a24`
- `0x140025bc4`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x140025bf1`

## pseudocode

```c
void __fastcall XamlResourceUtils::EscapeWString(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int64 i; // rbx
  __int64 v5; // rax
  __int64 *j; // r9
  __int64 v7; // rsi

  for ( i = 0; i < *(_QWORD *)(a1 + 16); i += v7 )
  {
    v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1, a2, a3);
    for ( j = &qword_14002B640; j != (__int64 *)&GetTokenInformation; j += 3 )
    {
      if ( *(_WORD *)j == *(_WORD *)(v5 + 2 * i) )
      {
        v7 = j[2];
        std::wstring::_Replace<unsigned short>(a1, i, a3, j[1], v7);
        goto LABEL_8;
      }
    }
    v7 = 1;
LABEL_8:
    ;
  }
}

```

## disassembly

```asm
0x140025bc4  mov     [rsp+arg_0], rbx
0x140025bc9  mov     [rsp+arg_8], rsi
0x140025bce  push    rdi
0x140025bcf  sub     rsp, 30h
0x140025bd3  xor     ebx, ebx
0x140025bd5  mov     rdi, rcx
0x140025bd8  cmp     [rcx+10h], rbx
0x140025bdc  jbe     short loc_140025C31
0x140025bde  mov     rcx, rdi
0x140025be1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140025be6  lea     r9, qword_14002B640
0x140025bed  movzx   ecx, word ptr [rax+rbx*2]
0x140025bf1  lea     rax, __imp_GetTokenInformation
0x140025bf8  cmp     r9, rax
0x140025bfb  jz      short loc_140025C23
0x140025bfd  cmp     [r9], cx
0x140025c01  jz      short loc_140025C09
0x140025c03  add     r9, 18h
0x140025c07  jmp     short loc_140025BF1
0x140025c09  mov     rsi, [r9+10h]
0x140025c0d  mov     rdx, rbx
0x140025c10  mov     r9, [r9+8]
0x140025c14  mov     rcx, rdi
0x140025c17  mov     [rsp+38h+var_18], rsi
0x140025c1c  call    ??$_Replace@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_K_KQEBG0@Z; std::wstring::_Replace<ushort>(unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x140025c21  jmp     short loc_140025C28
0x140025c23  mov     esi, 1
0x140025c28  add     rbx, rsi
0x140025c2b  cmp     rbx, [rdi+10h]
0x140025c2f  jb      short loc_140025BDE
0x140025c31  mov     rbx, [rsp+38h+arg_0]
0x140025c36  mov     rsi, [rsp+38h+arg_8]
0x140025c3b  add     rsp, 30h
0x140025c3f  pop     rdi
0x140025c40  retn
```
