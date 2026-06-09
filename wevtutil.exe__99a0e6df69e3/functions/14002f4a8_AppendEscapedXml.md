# AppendEscapedXml

- ea: `0x14002f4a8`
- end: `0x14002f696`
- name: `AppendEscapedXml`
- size: `494`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140029664`
- `0x14002987c`

## callees

- `0x140007db0`
- `0x14000d6e8`
- `0x14001a9b8`
- `0x14002f4a8`

## pseudocode

```c
char __fastcall AppendEscapedXml(_QWORD *a1, _QWORD *a2, char a3)
{
  __int64 v3; // rbp
  __int64 v7; // rsi
  __int64 v8; // r8
  unsigned __int16 *v9; // r9
  __int64 v10; // rdx
  char v11; // al
  _QWORD *v12; // rcx
  const wchar_t *v13; // rdx

  v3 = a2[1];
  if ( !v3 )
    return 1;
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(
                          a1,
                          v3 + ((__int64)(a1[1] - *a1) >> 1)) )
  {
    v7 = 0;
    v8 = 5;
    while ( 1 )
    {
      if ( v7 == v3 )
        return 1;
      v9 = (unsigned __int16 *)(*a2 + 2 * v7);
      v10 = *v9;
      switch ( *v9 )
      {
        case 9u:
          if ( !a3 )
          {
            v13 = L"&#9;";
LABEL_39:
            v8 = 4;
LABEL_40:
            v12 = a1;
LABEL_41:
            v11 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v12, v13, v8);
            goto LABEL_42;
          }
          goto LABEL_36;
        case 0xAu:
          v12 = a1;
          if ( !a3 )
          {
            v13 = L"&#10;";
            goto LABEL_41;
          }
          goto LABEL_37;
        case 0xDu:
          v12 = a1;
          if ( !a3 )
          {
            v13 = L"&#13;";
            goto LABEL_41;
          }
          goto LABEL_37;
        case 0x22u:
          v12 = a1;
          if ( a3 )
          {
            v8 = 6;
            v13 = L"&quot;";
            goto LABEL_41;
          }
          goto LABEL_37;
        case 0x26u:
          v13 = L"&amp;";
          goto LABEL_40;
        case 0x27u:
          v12 = a1;
          if ( a3 )
          {
            v8 = 6;
            v13 = L"&apos;";
            goto LABEL_41;
          }
          goto LABEL_37;
        case 0x3Cu:
          v13 = L"&lt;";
          goto LABEL_39;
        case 0x3Eu:
          v13 = L"&gt;";
          goto LABEL_39;
      }
      if ( (unsigned int)v10 < 0x20 )
        break;
      if ( (unsigned __int16)v10 < 0xD800u )
        goto LABEL_36;
      if ( (unsigned __int16)v10 >= 0xDC00u )
      {
        v12 = a1;
        if ( (unsigned __int16)(v10 + 0x2000) > 0x1FFDu )
          v10 = 95;
        goto LABEL_37;
      }
      if ( v7 + 1 == v3 || (unsigned __int16)(v9[1] + 9216) > 0x3FFu )
        goto LABEL_16;
      v11 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(a1, *a2 + 2 * v7++, 2);
LABEL_42:
      if ( !v11 )
        return 0;
      v8 = 5;
LABEL_44:
      ++v7;
    }
    if ( !(_WORD)v10 && v7 == v3 - 1 )
      goto LABEL_44;
LABEL_16:
    v10 = 95;
LABEL_36:
    v12 = a1;
LABEL_37:
    v11 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(v12, v10);
    goto LABEL_42;
  }
  return 0;
}

```

## disassembly

```asm
0x14002f4a8  push    rbx
0x14002f4aa  push    rbp
0x14002f4ab  push    rsi
0x14002f4ac  push    rdi
0x14002f4ad  push    r12
0x14002f4af  push    r13
0x14002f4b1  push    r14
0x14002f4b3  push    r15
0x14002f4b5  sub     rsp, 28h
0x14002f4b9  mov     rbp, [rdx+8]
0x14002f4bd  xor     r12d, r12d
0x14002f4c0  mov     r14b, r8b
0x14002f4c3  mov     r15, rdx
0x14002f4c6  mov     rbx, rcx
0x14002f4c9  test    rbp, rbp
0x14002f4cc  jz      loc_14002F683
0x14002f4d2  mov     rdx, [rcx+8]
0x14002f4d6  sub     rdx, [rcx]
0x14002f4d9  sar     rdx, 1
0x14002f4dc  add     rdx, rbp
0x14002f4df  call    ?reserve@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(unsigned __int64)
0x14002f4e4  test    al, al
0x14002f4e6  jz      loc_14002F67F
0x14002f4ec  mov     esi, r12d
0x14002f4ef  lea     r13d, [r12+4]
0x14002f4f4  lea     r8d, [r12+5]
0x14002f4f9  cmp     rsi, rbp
0x14002f4fc  jz      loc_14002F683
0x14002f502  mov     rax, [r15]
0x14002f505  lea     r9, [rax+rsi*2]
0x14002f509  movzx   edx, word ptr [r9]
0x14002f50d  mov     ecx, edx
0x14002f50f  sub     ecx, 9
0x14002f512  jz      loc_14002F64C
0x14002f518  sub     ecx, 1
0x14002f51b  jz      loc_14002F63B
0x14002f521  sub     ecx, 3
0x14002f524  jz      loc_14002F62A
0x14002f52a  sub     ecx, 15h
0x14002f52d  jz      loc_14002F613
0x14002f533  sub     ecx, r13d
0x14002f536  jz      loc_14002F60A
0x14002f53c  sub     ecx, 1
0x14002f53f  jz      loc_14002F5F3
0x14002f545  sub     ecx, 15h
0x14002f548  jz      loc_14002F5EA
0x14002f54e  cmp     ecx, 2
0x14002f551  jz      loc_14002F5E1
0x14002f557  cmp     edx, 20h ; ' '
0x14002f55a  jnb     short loc_14002F578
0x14002f55c  test    dx, dx
0x14002f55f  jnz     short loc_14002F56E
0x14002f561  lea     rax, [rbp-1]
0x14002f565  cmp     rsi, rax
0x14002f568  jz      loc_14002F677
0x14002f56e  mov     edx, 5Fh ; '_'
0x14002f573  jmp     loc_14002F651
0x14002f578  mov     eax, 0D800h
0x14002f57d  cmp     dx, ax
0x14002f580  jb      loc_14002F651
0x14002f586  mov     eax, 0DC00h
0x14002f58b  cmp     dx, ax
0x14002f58e  jnb     short loc_14002F5C6
0x14002f590  lea     rdi, [rsi+1]
0x14002f594  cmp     rdi, rbp
0x14002f597  jz      short loc_14002F56E
0x14002f599  mov     eax, 2400h
0x14002f59e  mov     ecx, 3FFh
0x14002f5a3  add     ax, [r9+2]
0x14002f5a8  cmp     ax, cx
0x14002f5ab  ja      short loc_14002F56E
0x14002f5ad  mov     r8d, 2
0x14002f5b3  mov     rdx, r9
0x14002f5b6  mov     rcx, rbx
0x14002f5b9  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x14002f5be  mov     rsi, rdi
0x14002f5c1  jmp     loc_14002F66D
0x14002f5c6  mov     ecx, 1FFDh
0x14002f5cb  mov     eax, 2000h
0x14002f5d0  add     eax, edx
0x14002f5d2  cmp     ax, cx
0x14002f5d5  mov     rcx, rbx
0x14002f5d8  jbe     short loc_14002F654
0x14002f5da  mov     edx, 5Fh ; '_'
0x14002f5df  jmp     short loc_14002F654
0x14002f5e1  lea     rdx, aGt; "&gt;"
0x14002f5e8  jmp     short loc_14002F662
0x14002f5ea  lea     rdx, aLt; "&lt;"
0x14002f5f1  jmp     short loc_14002F662
0x14002f5f3  mov     rcx, rbx
0x14002f5f6  test    r14b, r14b
0x14002f5f9  jz      short loc_14002F654
0x14002f5fb  mov     r8d, 6
0x14002f601  lea     rdx, aApos; "&apos;"
0x14002f608  jmp     short loc_14002F668
0x14002f60a  lea     rdx, aAmp; "&amp;"
0x14002f611  jmp     short loc_14002F665
0x14002f613  mov     rcx, rbx
0x14002f616  test    r14b, r14b
0x14002f619  jz      short loc_14002F654
0x14002f61b  mov     r8d, 6
0x14002f621  lea     rdx, aQuot; "&quot;"
0x14002f628  jmp     short loc_14002F668
0x14002f62a  mov     rcx, rbx
0x14002f62d  test    r14b, r14b
0x14002f630  jnz     short loc_14002F654
0x14002f632  lea     rdx, a13; "&#13;"
0x14002f639  jmp     short loc_14002F668
0x14002f63b  mov     rcx, rbx
0x14002f63e  test    r14b, r14b
0x14002f641  jnz     short loc_14002F654
0x14002f643  lea     rdx, a10; "&#10;"
0x14002f64a  jmp     short loc_14002F668
0x14002f64c  test    r14b, r14b
0x14002f64f  jz      short loc_14002F65B
0x14002f651  mov     rcx, rbx
0x14002f654  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x14002f659  jmp     short loc_14002F66D
0x14002f65b  lea     rdx, a9; "&#9;"
0x14002f662  mov     r8, r13
0x14002f665  mov     rcx, rbx
0x14002f668  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x14002f66d  test    al, al
0x14002f66f  jz      short loc_14002F67F
0x14002f671  mov     r8d, 5
0x14002f677  inc     rsi
0x14002f67a  jmp     loc_14002F4F9
0x14002f67f  xor     al, al
0x14002f681  jmp     short loc_14002F685
0x14002f683  mov     al, 1
0x14002f685  add     rsp, 28h
0x14002f689  pop     r15
0x14002f68b  pop     r14
0x14002f68d  pop     r13
0x14002f68f  pop     r12
0x14002f691  pop     rdi
0x14002f692  pop     rsi
0x14002f693  pop     rbp
0x14002f694  pop     rbx
0x14002f695  retn
```
