# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180004594`
- end: `0x18000474d`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `441`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000304c`
- `0x180004b10`
- `0x180004f1c`
- `0x180005578`

## callees

- `0x180004594`
- `0x180005614`

## import_xrefs

- `USER32!CharNextW` at `0x1800045e4`
- `USER32!CharNextW` at `0x180004606`
- `USER32!CharNextW` at `0x180004624`
- `USER32!CharNextW` at `0x180004639`
- `USER32!CharNextW` at `0x1800046a2`
- `USER32!CharNextW` at `0x1800046d6`
- `USER32!CharNextW` at `0x1800045e4`
- `USER32!CharNextW` at `0x180004606`
- `USER32!CharNextW` at `0x180004624`
- `USER32!CharNextW` at `0x180004639`
- `USER32!CharNextW` at `0x1800046a2`
- `USER32!CharNextW` at `0x1800046d6`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(ATL::CRegParser *this, unsigned __int16 *a2)
{
  const WCHAR *v4; // rcx
  unsigned __int16 *v5; // r14
  unsigned __int16 *v6; // rbp
  const WCHAR *v7; // rcx
  const WCHAR *v8; // rsi
  LPWSTR v9; // rax
  __int64 v10; // rax
  signed __int64 v11; // rsi
  __int64 v12; // rcx
  char *v13; // rsi
  LPWSTR v14; // rax
  __int64 v15; // rax
  signed __int64 v16; // rsi
  __int64 v17; // rcx

  ATL::CRegParser::SkipWhiteSpace(this);
  v4 = *(const WCHAR **)this;
  if ( **(_WORD **)this )
  {
    v5 = a2;
    v6 = a2 + 4096;
    if ( *v4 == 39 )
    {
      *(_QWORD *)this = CharNextW(v4);
      while ( 1 )
      {
        v7 = *(const WCHAR **)this;
        if ( !**(_WORD **)this || *v7 == 39 && *CharNextW(v7) != 39 )
          break;
        v8 = *(const WCHAR **)this;
        if ( **(_WORD **)this == 39 )
        {
          v8 = CharNextW(*(LPCWSTR *)this);
          *(_QWORD *)this = v8;
        }
        v9 = CharNextW(v8);
        *(_QWORD *)this = v9;
        v10 = v9 - v8;
        if ( &a2[v10 + 1] >= v5 + 4096 )
          return 2147614729LL;
        if ( (int)v10 > 0 )
        {
          v11 = (char *)v8 - (char *)a2;
          v12 = (unsigned int)v10;
          do
          {
            *a2 = *(unsigned __int16 *)((char *)a2 + v11);
            ++a2;
            --v12;
          }
          while ( v12 );
        }
      }
      if ( **(_WORD **)this && a2 < v6 )
      {
        *a2 = 0;
        *(_QWORD *)this = CharNextW(*(LPCWSTR *)this);
        return 0;
      }
    }
    else
    {
      while ( 1 )
      {
        v13 = *(char **)this;
        if ( !**(_WORD **)this
          || *(_WORD *)v13 == 9
          || *(_WORD *)v13 == 10
          || *(_WORD *)v13 == 13
          || *(_WORD *)v13 == 32 )
        {
          break;
        }
        v14 = CharNextW(*(LPCWSTR *)this);
        *(_QWORD *)this = v14;
        v15 = ((char *)v14 - v13) >> 1;
        if ( &a2[v15 + 1] >= v5 + 4096 )
          return 2147614729LL;
        if ( (int)v15 > 0 )
        {
          v16 = v13 - (char *)a2;
          v17 = (unsigned int)v15;
          do
          {
            *a2 = *(unsigned __int16 *)((char *)a2 + v16);
            ++a2;
            --v17;
          }
          while ( v17 );
        }
      }
      if ( a2 < v6 )
      {
        *a2 = 0;
        return 0;
      }
    }
  }
  return 2147614729LL;
}

```

## disassembly

```asm
0x180004594  mov     rax, rsp
0x180004597  mov     [rax+8], rbx
0x18000459b  mov     [rax+10h], rbp
0x18000459f  mov     [rax+18h], rsi
0x1800045a3  mov     [rax+20h], rdi
0x1800045a7  push    r12
0x1800045a9  push    r14
0x1800045ab  push    r15
0x1800045ad  sub     rsp, 20h
0x1800045b1  mov     rbx, rdx
0x1800045b4  mov     rdi, rcx
0x1800045b7  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1800045bc  mov     rcx, [rdi]; lpsz
0x1800045bf  xor     r15d, r15d
0x1800045c2  cmp     r15w, [rcx]
0x1800045c6  jz      loc_180004728
0x1800045cc  lea     r12d, [r15+27h]
0x1800045d0  mov     r14, rbx
0x1800045d3  lea     rbp, [rbx+2000h]
0x1800045da  cmp     r12w, [rcx]
0x1800045de  jnz     loc_1800046B3
0x1800045e4  call    cs:__imp_CharNextW
0x1800045eb  nop     dword ptr [rax+rax+00h]
0x1800045f0  mov     [rdi], rax
0x1800045f3  mov     rcx, [rdi]; lpsz
0x1800045f6  cmp     r15w, [rcx]
0x1800045fa  jz      loc_180004685
0x180004600  cmp     r12w, [rcx]
0x180004604  jnz     short loc_180004618
0x180004606  call    cs:__imp_CharNextW
0x18000460d  nop     dword ptr [rax+rax+00h]
0x180004612  cmp     r12w, [rax]
0x180004616  jnz     short loc_180004685
0x180004618  mov     rsi, [rdi]
0x18000461b  cmp     r12w, [rsi]
0x18000461f  jnz     short loc_180004636
0x180004621  mov     rcx, rsi; lpsz
0x180004624  call    cs:__imp_CharNextW
0x18000462b  nop     dword ptr [rax+rax+00h]
0x180004630  mov     rsi, rax
0x180004633  mov     [rdi], rax
0x180004636  mov     rcx, rsi; lpsz
0x180004639  call    cs:__imp_CharNextW
0x180004640  nop     dword ptr [rax+rax+00h]
0x180004645  mov     [rdi], rax
0x180004648  lea     rcx, [r14+2000h]
0x18000464f  sub     rax, rsi
0x180004652  sar     rax, 1
0x180004655  lea     rdx, [rax+1]
0x180004659  lea     rdx, [rbx+rdx*2]
0x18000465d  cmp     rdx, rcx
0x180004660  jnb     loc_180004728
0x180004666  test    eax, eax
0x180004668  jle     short loc_1800045F3
0x18000466a  sub     rsi, rbx
0x18000466d  mov     ecx, eax
0x18000466f  movzx   eax, word ptr [rsi+rbx]
0x180004673  mov     [rbx], ax
0x180004676  add     rbx, 2
0x18000467a  sub     rcx, 1
0x18000467e  jnz     short loc_18000466F
0x180004680  jmp     loc_1800045F3
0x180004685  mov     rax, [rdi]
0x180004688  cmp     r15w, [rax]
0x18000468c  jz      loc_180004728
0x180004692  cmp     rbx, rbp
0x180004695  jnb     loc_180004728
0x18000469b  mov     [rbx], r15w
0x18000469f  mov     rcx, [rdi]; lpsz
0x1800046a2  call    cs:__imp_CharNextW
0x1800046a9  nop     dword ptr [rax+rax+00h]
0x1800046ae  mov     [rdi], rax
0x1800046b1  jmp     short loc_180004724
0x1800046b3  mov     rsi, [rdi]
0x1800046b6  cmp     r15w, [rsi]
0x1800046ba  jz      short loc_18000471B
0x1800046bc  movzx   ecx, word ptr [rsi]
0x1800046bf  sub     ecx, 9
0x1800046c2  jz      short loc_18000471B
0x1800046c4  sub     ecx, 1
0x1800046c7  jz      short loc_18000471B
0x1800046c9  sub     ecx, 3
0x1800046cc  jz      short loc_18000471B
0x1800046ce  cmp     ecx, 13h
0x1800046d1  jz      short loc_18000471B
0x1800046d3  mov     rcx, rsi; lpsz
0x1800046d6  call    cs:__imp_CharNextW
0x1800046dd  nop     dword ptr [rax+rax+00h]
0x1800046e2  mov     [rdi], rax
0x1800046e5  lea     rcx, [r14+2000h]
0x1800046ec  sub     rax, rsi
0x1800046ef  sar     rax, 1
0x1800046f2  lea     rdx, [rax+1]
0x1800046f6  lea     rdx, [rbx+rdx*2]
0x1800046fa  cmp     rdx, rcx
0x1800046fd  jnb     short loc_180004728
0x1800046ff  test    eax, eax
0x180004701  jle     short loc_1800046B3
0x180004703  sub     rsi, rbx
0x180004706  mov     ecx, eax
0x180004708  movzx   eax, word ptr [rsi+rbx]
0x18000470c  mov     [rbx], ax
0x18000470f  add     rbx, 2
0x180004713  sub     rcx, 1
0x180004717  jnz     short loc_180004708
0x180004719  jmp     short loc_1800046B3
0x18000471b  cmp     rbx, rbp
0x18000471e  jnb     short loc_180004728
0x180004720  mov     [rbx], r15w
0x180004724  xor     eax, eax
0x180004726  jmp     short loc_18000472D
0x180004728  mov     eax, 80020009h
0x18000472d  mov     rbx, [rsp+38h+arg_0]
0x180004732  mov     rbp, [rsp+38h+arg_8]
0x180004737  mov     rsi, [rsp+38h+arg_10]
0x18000473c  mov     rdi, [rsp+38h+arg_18]
0x180004741  add     rsp, 20h
0x180004745  pop     r15
0x180004747  pop     r14
0x180004749  pop     r12
0x18000474b  retn
```
