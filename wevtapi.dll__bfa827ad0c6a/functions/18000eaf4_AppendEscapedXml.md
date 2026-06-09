# AppendEscapedXml

- ea: `0x18000eaf4`
- end: `0x18000ec8f`
- name: `AppendEscapedXml`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001b3d4`

## callees

- `0x18000c034`
- `0x18000c10c`
- `0x18000e960`
- `0x18000eaf4`
- `0x18000f2b0`

## pseudocode

```c
char __fastcall AppendEscapedXml(_QWORD *a1, _QWORD *a2)
{
  __int64 v2; // rbp
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // rdi
  __int64 v8; // r8
  unsigned __int16 *v9; // r9
  __int64 v10; // rdx
  _QWORD *v11; // rcx
  char v12; // al
  const wchar_t *v13; // rdx

  v2 = a2[1];
  if ( !v2 )
    return 1;
  v5 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::capacity(
         a1,
         v2 + ((__int64)(a1[1] - *a1) >> 1));
  if ( v6 <= v5
    || (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Grow() )
  {
    v7 = 0;
    v8 = 5;
    while ( 1 )
    {
      if ( v7 == v2 )
        return 1;
      v9 = (unsigned __int16 *)(*a2 + 2 * v7);
      v10 = *v9;
      switch ( *v9 )
      {
        case 9u:
          v13 = L"&#9;";
          goto LABEL_21;
        case 0xAu:
          v13 = L"&#10;";
          goto LABEL_22;
        case 0xDu:
          v13 = L"&#13;";
          goto LABEL_22;
        case 0x22u:
          goto LABEL_15;
        case 0x26u:
          v13 = L"&amp;";
          goto LABEL_22;
        case 0x27u:
          goto LABEL_15;
        case 0x3Cu:
          v13 = L"&lt;";
LABEL_21:
          v8 = 4;
LABEL_22:
          v12 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(a1, v13, v8);
          goto LABEL_17;
        case 0x3Eu:
          v13 = L"&gt;";
          goto LABEL_21;
      }
      if ( (unsigned int)v10 < 0x20 )
      {
        if ( !(_WORD)v10 && v7 == v2 - 1 )
          goto LABEL_19;
LABEL_30:
        v11 = a1;
LABEL_36:
        v10 = 95;
        goto LABEL_16;
      }
      if ( (unsigned __int16)v10 < 0xD800u )
      {
LABEL_15:
        v11 = a1;
      }
      else
      {
        if ( (unsigned __int16)v10 < 0xDC00u )
        {
          if ( v7 + 1 != v2 && (unsigned __int16)(v9[1] + 9216) <= 0x3FFu )
          {
            v12 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                    a1,
                    *a2 + 2 * v7++,
                    2);
            goto LABEL_17;
          }
          goto LABEL_30;
        }
        v11 = a1;
        if ( (unsigned __int16)(v10 + 0x2000) > 0x1FFDu )
          goto LABEL_36;
      }
LABEL_16:
      v12 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(v11, v10);
LABEL_17:
      if ( !v12 )
        return 0;
      v8 = 5;
LABEL_19:
      ++v7;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000eaf4  push    rbx
0x18000eaf6  push    rbp
0x18000eaf7  push    rsi
0x18000eaf8  push    rdi
0x18000eaf9  push    r12
0x18000eafb  push    r14
0x18000eafd  push    r15
0x18000eaff  sub     rsp, 20h
0x18000eb03  mov     rbp, [rdx+8]
0x18000eb07  xor     r15d, r15d
0x18000eb0a  mov     r14, rdx
0x18000eb0d  mov     rbx, rcx
0x18000eb10  test    rbp, rbp
0x18000eb13  jz      loc_18000EBC2
0x18000eb19  mov     rdx, [rcx+8]
0x18000eb1d  sub     rdx, [rcx]
0x18000eb20  sar     rdx, 1
0x18000eb23  add     rdx, rbp
0x18000eb26  call    ?capacity@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEBA_KXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::capacity(void)
0x18000eb2b  cmp     rdx, rax
0x18000eb2e  ja      loc_18000EBE5
0x18000eb34  mov     r12d, 4
0x18000eb3a  mov     rdi, r15
0x18000eb3d  lea     r8d, [r12+1]
0x18000eb42  cmp     rdi, rbp
0x18000eb45  jz      short loc_18000EBC2
0x18000eb47  mov     rax, [r14]
0x18000eb4a  lea     r9, [rax+rdi*2]
0x18000eb4e  movzx   edx, word ptr [r9]
0x18000eb52  mov     ecx, edx
0x18000eb54  sub     ecx, 9
0x18000eb57  jz      short loc_18000EBAE
0x18000eb59  sub     ecx, 1
0x18000eb5c  jz      short loc_18000EBDC
0x18000eb5e  sub     ecx, 3
0x18000eb61  jz      short loc_18000EBD3
0x18000eb63  sub     ecx, 15h
0x18000eb66  jz      short loc_18000EB97
0x18000eb68  sub     ecx, r12d
0x18000eb6b  jz      loc_18000EC83
0x18000eb71  sub     ecx, 1
0x18000eb74  jz      short loc_18000EB97
0x18000eb76  sub     ecx, 15h
0x18000eb79  jz      loc_18000EC77
0x18000eb7f  cmp     ecx, 2
0x18000eb82  jz      loc_18000EC6B
0x18000eb88  cmp     edx, 20h ; ' '
0x18000eb8b  jb      short loc_18000EBF6
0x18000eb8d  mov     eax, 0D800h
0x18000eb92  cmp     dx, ax
0x18000eb95  jnb     short loc_18000EC09
0x18000eb97  mov     rcx, rbx
0x18000eb9a  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x18000eb9f  test    al, al
0x18000eba1  jz      short loc_18000EBF2
0x18000eba3  mov     r8d, 5
0x18000eba9  inc     rdi
0x18000ebac  jmp     short loc_18000EB42
0x18000ebae  lea     rdx, a9; "&#9;"
0x18000ebb5  mov     r8, r12
0x18000ebb8  mov     rcx, rbx
0x18000ebbb  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18000ebc0  jmp     short loc_18000EB9F
0x18000ebc2  mov     al, 1
0x18000ebc4  add     rsp, 20h
0x18000ebc8  pop     r15
0x18000ebca  pop     r14
0x18000ebcc  pop     r12
0x18000ebce  pop     rdi
0x18000ebcf  pop     rsi
0x18000ebd0  pop     rbp
0x18000ebd1  pop     rbx
0x18000ebd2  retn
0x18000ebd3  lea     rdx, a13; "&#13;"
0x18000ebda  jmp     short loc_18000EBB8
0x18000ebdc  lea     rdx, a10; "&#10;"
0x18000ebe3  jmp     short loc_18000EBB8
0x18000ebe5  call    ?_Grow@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Grow(unsigned __int64)
0x18000ebea  test    al, al
0x18000ebec  jnz     loc_18000EB34
0x18000ebf2  xor     al, al
0x18000ebf4  jmp     short loc_18000EBC4
0x18000ebf6  test    dx, dx
0x18000ebf9  jnz     short loc_18000EC04
0x18000ebfb  lea     rax, [rbp-1]
0x18000ebff  cmp     rdi, rax
0x18000ec02  jz      short loc_18000EBA9
0x18000ec04  mov     rcx, rbx
0x18000ec07  jmp     short loc_18000EC61
0x18000ec09  mov     eax, 0DC00h
0x18000ec0e  cmp     dx, ax
0x18000ec11  jnb     short loc_18000EC49
0x18000ec13  lea     rsi, [rdi+1]
0x18000ec17  cmp     rsi, rbp
0x18000ec1a  jz      short loc_18000EC04
0x18000ec1c  mov     eax, 2400h
0x18000ec21  mov     ecx, 3FFh
0x18000ec26  add     ax, [r9+2]
0x18000ec2b  cmp     ax, cx
0x18000ec2e  ja      short loc_18000EC04
0x18000ec30  mov     r8d, 2
0x18000ec36  mov     rdx, r9
0x18000ec39  mov     rcx, rbx
0x18000ec3c  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18000ec41  mov     rdi, rsi
0x18000ec44  jmp     loc_18000EB9F
0x18000ec49  mov     ecx, 1FFDh
0x18000ec4e  mov     eax, 2000h
0x18000ec53  add     eax, edx
0x18000ec55  cmp     ax, cx
0x18000ec58  mov     rcx, rbx
0x18000ec5b  jbe     loc_18000EB9A
0x18000ec61  mov     edx, 5Fh ; '_'
0x18000ec66  jmp     loc_18000EB9A
0x18000ec6b  lea     rdx, aGt; "&gt;"
0x18000ec72  jmp     loc_18000EBB5
0x18000ec77  lea     rdx, aLt; "&lt;"
0x18000ec7e  jmp     loc_18000EBB5
0x18000ec83  lea     rdx, aAmp; "&amp;"
0x18000ec8a  jmp     loc_18000EBB8
```
