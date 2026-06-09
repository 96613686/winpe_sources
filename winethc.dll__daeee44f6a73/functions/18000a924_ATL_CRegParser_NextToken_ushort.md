# ATL::CRegParser::NextToken(ushort *)

- ea: `0x18000a924`
- end: `0x18000aaee`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `458`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003b40`
- `0x18000b374`
- `0x18000b6fc`
- `0x18000c82c`

## callees

- `0x18000a924`

## import_xrefs

- `USER32!CharNextW` at `0x18000a959`
- `USER32!CharNextW` at `0x18000a98d`
- `USER32!CharNextW` at `0x18000a9b3`
- `USER32!CharNextW` at `0x18000a9d5`
- `USER32!CharNextW` at `0x18000a9ea`
- `USER32!CharNextW` at `0x18000aa60`
- `USER32!CharNextW` at `0x18000aa8b`
- `USER32!CharNextW` at `0x18000a959`
- `USER32!CharNextW` at `0x18000a98d`
- `USER32!CharNextW` at `0x18000a9b3`
- `USER32!CharNextW` at `0x18000a9d5`
- `USER32!CharNextW` at `0x18000a9ea`
- `USER32!CharNextW` at `0x18000aa60`
- `USER32!CharNextW` at `0x18000aa8b`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(LPCWSTR *this, unsigned __int16 *a2)
{
  const WCHAR *v4; // rsi
  WCHAR v5; // cx
  unsigned __int16 *v6; // rbp
  LPWSTR v7; // rax
  const WCHAR *v8; // rcx
  __int16 v9; // dx
  const WCHAR *v10; // rsi
  LPWSTR v11; // rax
  __int64 v12; // rdx
  int j; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  LPWSTR v18; // rax
  __int64 v19; // rdx
  int i; // ecx

  while ( 1 )
  {
    v4 = *this;
    v5 = **this;
    if ( v5 != 9 && **this != 10 && **this != 13 && **this != 32 )
      break;
    *this = CharNextW(*this);
  }
  if ( !v5 )
    return 2147614729LL;
  v6 = a2 + 4096;
  if ( v5 != 39 )
  {
    while ( 1 )
    {
      v15 = v5 - 9;
      if ( !v15 )
        break;
      v16 = v15 - 1;
      if ( !v16 )
        break;
      v17 = v16 - 3;
      if ( !v17 || v17 == 19 )
        break;
      v18 = CharNextW(v4);
      *this = v18;
      v19 = v18 - v4;
      if ( &a2[v19 + 1] >= v6 )
        return 2147614729LL;
      for ( i = 0; i < (int)v19; ++a2 )
      {
        ++i;
        *a2 = *v4++;
      }
      v4 = *this;
      if ( !**this )
        break;
      v5 = *v4;
    }
    if ( a2 < v6 )
    {
      *a2 = 0;
      return 0;
    }
    return 2147614729LL;
  }
  v7 = CharNextW(*this);
  *this = v7;
  v8 = v7;
  v9 = *v7;
  if ( *v7 )
  {
    while ( v9 != 39 || *CharNextW(v8) == 39 )
    {
      v10 = *this;
      if ( **this == 39 )
      {
        v10 = CharNextW(*this);
        *this = v10;
      }
      v11 = CharNextW(v10);
      *this = v11;
      v12 = v11 - v10;
      if ( &a2[v12 + 1] < v6 )
      {
        for ( j = 0; j < (int)v12; ++a2 )
        {
          ++j;
          *a2 = *v10++;
        }
        v8 = *this;
        v9 = **this;
        if ( v9 )
          continue;
      }
      return 2147614729LL;
    }
  }
  if ( !**this || a2 >= v6 )
    return 2147614729LL;
  *a2 = 0;
  *this = CharNextW(*this);
  return 0;
}

```

## disassembly

```asm
0x18000a924  push    rbx
0x18000a926  push    rbp
0x18000a927  push    rsi
0x18000a928  push    rdi
0x18000a929  push    r14
0x18000a92b  sub     rsp, 20h
0x18000a92f  mov     rbx, rdx
0x18000a932  mov     rdi, rcx
0x18000a935  mov     rsi, [rdi]
0x18000a938  movzx   ecx, word ptr [rsi]
0x18000a93b  mov     r8d, ecx
0x18000a93e  sub     r8d, 9
0x18000a942  jz      short loc_18000A956
0x18000a944  sub     r8d, 1
0x18000a948  jz      short loc_18000A956
0x18000a94a  sub     r8d, 3
0x18000a94e  jz      short loc_18000A956
0x18000a950  cmp     r8d, 13h
0x18000a954  jnz     short loc_18000A96A
0x18000a956  mov     rcx, rsi; lpsz
0x18000a959  call    cs:__imp_CharNextW
0x18000a960  nop     dword ptr [rax+rax+00h]
0x18000a965  mov     [rdi], rax
0x18000a968  jmp     short loc_18000A935
0x18000a96a  xor     eax, eax
0x18000a96c  cmp     ax, cx
0x18000a96f  jz      loc_18000AA3A
0x18000a975  lea     r14d, [rax+27h]
0x18000a979  lea     rbp, [rbx+2000h]
0x18000a980  cmp     r14w, cx
0x18000a984  jnz     loc_18000AA71
0x18000a98a  mov     rcx, rsi; lpsz
0x18000a98d  call    cs:__imp_CharNextW
0x18000a994  nop     dword ptr [rax+rax+00h]
0x18000a999  mov     [rdi], rax
0x18000a99c  mov     rcx, rax; lpsz
0x18000a99f  movzx   edx, word ptr [rax]
0x18000a9a2  xor     eax, eax
0x18000a9a4  cmp     ax, dx
0x18000a9a7  jz      loc_18000AA4B
0x18000a9ad  cmp     r14w, dx
0x18000a9b1  jnz     short loc_18000A9C9
0x18000a9b3  call    cs:__imp_CharNextW
0x18000a9ba  nop     dword ptr [rax+rax+00h]
0x18000a9bf  cmp     r14w, [rax]
0x18000a9c3  jnz     loc_18000AA4B
0x18000a9c9  mov     rsi, [rdi]
0x18000a9cc  cmp     r14w, [rsi]
0x18000a9d0  jnz     short loc_18000A9E7
0x18000a9d2  mov     rcx, rsi; lpsz
0x18000a9d5  call    cs:__imp_CharNextW
0x18000a9dc  nop     dword ptr [rax+rax+00h]
0x18000a9e1  mov     rsi, rax
0x18000a9e4  mov     [rdi], rax
0x18000a9e7  mov     rcx, rsi; lpsz
0x18000a9ea  call    cs:__imp_CharNextW
0x18000a9f1  nop     dword ptr [rax+rax+00h]
0x18000a9f6  mov     rdx, rax
0x18000a9f9  mov     [rdi], rax
0x18000a9fc  sub     rdx, rsi
0x18000a9ff  sar     rdx, 1
0x18000aa02  lea     rcx, [rdx+1]
0x18000aa06  lea     rcx, [rbx+rcx*2]
0x18000aa0a  cmp     rcx, rbp
0x18000aa0d  jnb     short loc_18000AA3A
0x18000aa0f  xor     ecx, ecx
0x18000aa11  test    edx, edx
0x18000aa13  jle     short loc_18000AA29
0x18000aa15  movzx   eax, word ptr [rsi]
0x18000aa18  inc     ecx
0x18000aa1a  mov     [rbx], ax
0x18000aa1d  lea     rsi, [rsi+2]
0x18000aa21  add     rbx, 2
0x18000aa25  cmp     ecx, edx
0x18000aa27  jl      short loc_18000AA15
0x18000aa29  mov     rcx, [rdi]
0x18000aa2c  xor     eax, eax
0x18000aa2e  movzx   edx, word ptr [rcx]
0x18000aa31  cmp     ax, dx
0x18000aa34  jnz     loc_18000A9AD
0x18000aa3a  mov     eax, 80020009h
0x18000aa3f  add     rsp, 20h
0x18000aa43  pop     r14
0x18000aa45  pop     rdi
0x18000aa46  pop     rsi
0x18000aa47  pop     rbp
0x18000aa48  pop     rbx
0x18000aa49  retn
0x18000aa4b  mov     rcx, [rdi]
0x18000aa4e  xor     eax, eax
0x18000aa50  cmp     ax, [rcx]
0x18000aa53  jz      short loc_18000AA3A
0x18000aa55  cmp     rbx, rbp
0x18000aa58  jnb     short loc_18000AA3A
0x18000aa5a  mov     [rbx], ax
0x18000aa5d  mov     rcx, [rdi]; lpsz
0x18000aa60  call    cs:__imp_CharNextW
0x18000aa67  nop     dword ptr [rax+rax+00h]
0x18000aa6c  mov     [rdi], rax
0x18000aa6f  jmp     short loc_18000AAE7
0x18000aa71  movzx   ecx, cx
0x18000aa74  sub     ecx, 9
0x18000aa77  jz      short loc_18000AAD9
0x18000aa79  sub     ecx, 1
0x18000aa7c  jz      short loc_18000AAD9
0x18000aa7e  sub     ecx, 3
0x18000aa81  jz      short loc_18000AAD9
0x18000aa83  cmp     ecx, 13h
0x18000aa86  jz      short loc_18000AAD9
0x18000aa88  mov     rcx, rsi; lpsz
0x18000aa8b  call    cs:__imp_CharNextW
0x18000aa92  nop     dword ptr [rax+rax+00h]
0x18000aa97  mov     rdx, rax
0x18000aa9a  mov     [rdi], rax
0x18000aa9d  sub     rdx, rsi
0x18000aaa0  sar     rdx, 1
0x18000aaa3  lea     rcx, [rdx+1]
0x18000aaa7  lea     rcx, [rbx+rcx*2]
0x18000aaab  cmp     rcx, rbp
0x18000aaae  jnb     short loc_18000AA3A
0x18000aab0  xor     ecx, ecx
0x18000aab2  test    edx, edx
0x18000aab4  jle     short loc_18000AACA
0x18000aab6  movzx   eax, word ptr [rsi]
0x18000aab9  inc     ecx
0x18000aabb  mov     [rbx], ax
0x18000aabe  lea     rsi, [rsi+2]
0x18000aac2  add     rbx, 2
0x18000aac6  cmp     ecx, edx
0x18000aac8  jl      short loc_18000AAB6
0x18000aaca  mov     rsi, [rdi]
0x18000aacd  xor     eax, eax
0x18000aacf  cmp     ax, [rsi]
0x18000aad2  jz      short loc_18000AAD9
0x18000aad4  movzx   ecx, word ptr [rsi]
0x18000aad7  jmp     short loc_18000AA71
0x18000aad9  cmp     rbx, rbp
0x18000aadc  jnb     loc_18000AA3A
0x18000aae2  xor     eax, eax
0x18000aae4  mov     [rbx], ax
0x18000aae7  xor     eax, eax
0x18000aae9  jmp     loc_18000AA3F
```
