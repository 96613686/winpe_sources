# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180002f30`
- end: `0x1800030b8`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `392`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002164`
- `0x1800034f0`
- `0x1800038f0`
- `0x180004380`

## callees

- `0x180002f30`

## import_xrefs

- `USER32!CharNextW` at `0x180002f65`
- `USER32!CharNextW` at `0x180002f8b`
- `USER32!CharNextW` at `0x180002fa5`
- `USER32!CharNextW` at `0x180002fbd`
- `USER32!CharNextW` at `0x180002fcc`
- `USER32!CharNextW` at `0x180003032`
- `USER32!CharNextW` at `0x180003057`
- `USER32!CharNextW` at `0x180002f65`
- `USER32!CharNextW` at `0x180002f8b`
- `USER32!CharNextW` at `0x180002fa5`
- `USER32!CharNextW` at `0x180002fbd`
- `USER32!CharNextW` at `0x180002fcc`
- `USER32!CharNextW` at `0x180003032`
- `USER32!CharNextW` at `0x180003057`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(LPCWSTR *this, unsigned __int16 *a2)
{
  const WCHAR *v4; // rbx
  WCHAR v5; // cx
  unsigned __int16 *v6; // rbp
  LPWSTR v7; // rax
  LPWSTR v8; // rdx
  WCHAR i; // cx
  const WCHAR *v10; // rbx
  unsigned __int16 v12; // ax
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  LPWSTR v16; // rax
  const WCHAR *v17; // rcx
  unsigned __int16 v18; // ax

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
  v6 = a2;
  if ( v5 != 39 )
  {
    while ( 1 )
    {
      v13 = v5 - 9;
      if ( !v13 )
        break;
      v14 = v13 - 1;
      if ( !v14 )
        break;
      v15 = v14 - 3;
      if ( !v15 || v15 == 19 )
        break;
      v16 = CharNextW(v4);
      *this = v16;
      if ( &a2[v16 - v4] >= v6 + 4096 )
        return 2147614729LL;
      v17 = v4;
      if ( v4 >= v16 )
      {
        v4 = v16;
      }
      else
      {
        do
        {
          v18 = *v17++;
          *a2++ = v18;
          v4 = *this;
        }
        while ( v17 < *this );
      }
      if ( !*v4 )
        break;
      v5 = *v4;
    }
    *a2 = 0;
    return 0;
  }
  v7 = CharNextW(*this);
  *this = v7;
  v8 = v7;
  for ( i = *v7; i && (i != 39 || *CharNextW(v8) == 39); i = *v8 )
  {
    v10 = *this;
    if ( **this == 39 )
    {
      v10 = CharNextW(*this);
      *this = v10;
    }
    v8 = CharNextW(v10);
    *this = v8;
    if ( &a2[v8 - v10] >= v6 + 4096 )
      return 2147614729LL;
    while ( v10 < v8 )
    {
      v12 = *v10++;
      *a2++ = v12;
      v8 = (LPWSTR)*this;
    }
  }
  if ( !**this )
    return 2147614729LL;
  *a2 = 0;
  *this = CharNextW(*this);
  return 0;
}

```

## disassembly

```asm
0x180002f30  push    rbx
0x180002f32  push    rbp
0x180002f33  push    rsi
0x180002f34  push    rdi
0x180002f35  push    r14
0x180002f37  sub     rsp, 20h
0x180002f3b  mov     rsi, rdx
0x180002f3e  mov     rdi, rcx
0x180002f41  mov     rbx, [rdi]
0x180002f44  movzx   ecx, word ptr [rbx]
0x180002f47  mov     r8d, ecx
0x180002f4a  sub     r8d, 9
0x180002f4e  jz      short loc_180002F62
0x180002f50  sub     r8d, 1
0x180002f54  jz      short loc_180002F62
0x180002f56  sub     r8d, 3
0x180002f5a  jz      short loc_180002F62
0x180002f5c  cmp     r8d, 13h
0x180002f60  jnz     short loc_180002F70
0x180002f62  mov     rcx, rbx; lpsz
0x180002f65  call    cs:__imp_CharNextW
0x180002f6b  mov     [rdi], rax
0x180002f6e  jmp     short loc_180002F41
0x180002f70  xor     eax, eax
0x180002f72  cmp     ax, cx
0x180002f75  jz      short loc_180002FEE
0x180002f77  lea     r14d, [rax+27h]
0x180002f7b  mov     rbp, rsi
0x180002f7e  cmp     r14w, cx
0x180002f82  jnz     loc_18000303D
0x180002f88  mov     rcx, rbx; lpsz
0x180002f8b  call    cs:__imp_CharNextW
0x180002f91  mov     [rdi], rax
0x180002f94  mov     rdx, rax
0x180002f97  movzx   ecx, word ptr [rax]
0x180002f9a  jmp     short loc_180003017
0x180002f9c  cmp     r14w, cx
0x180002fa0  jnz     short loc_180002FB1
0x180002fa2  mov     rcx, rdx; lpsz
0x180002fa5  call    cs:__imp_CharNextW
0x180002fab  cmp     r14w, [rax]
0x180002faf  jnz     short loc_180003022
0x180002fb1  mov     rbx, [rdi]
0x180002fb4  cmp     r14w, [rbx]
0x180002fb8  jnz     short loc_180002FC9
0x180002fba  mov     rcx, rbx; lpsz
0x180002fbd  call    cs:__imp_CharNextW
0x180002fc3  mov     rbx, rax
0x180002fc6  mov     [rdi], rax
0x180002fc9  mov     rcx, rbx; lpsz
0x180002fcc  call    cs:__imp_CharNextW
0x180002fd2  mov     rdx, rax
0x180002fd5  mov     [rdi], rax
0x180002fd8  sub     rax, rbx
0x180002fdb  sar     rax, 1
0x180002fde  lea     rcx, [rsi+rax*2]
0x180002fe2  lea     rax, [rbp+2000h]
0x180002fe9  cmp     rcx, rax
0x180002fec  jb      short loc_18000300F
0x180002fee  mov     eax, 80020009h
0x180002ff3  add     rsp, 20h
0x180002ff7  pop     r14
0x180002ff9  pop     rdi
0x180002ffa  pop     rsi
0x180002ffb  pop     rbp
0x180002ffc  pop     rbx
0x180002ffd  retn
0x180002ffe  movzx   eax, word ptr [rbx]
0x180003001  add     rbx, 2
0x180003005  mov     [rsi], ax
0x180003008  add     rsi, 2
0x18000300c  mov     rdx, [rdi]
0x18000300f  cmp     rbx, rdx
0x180003012  jb      short loc_180002FFE
0x180003014  movzx   ecx, word ptr [rdx]
0x180003017  xor     eax, eax
0x180003019  cmp     ax, cx
0x18000301c  jnz     loc_180002F9C
0x180003022  mov     rcx, [rdi]
0x180003025  xor     eax, eax
0x180003027  cmp     ax, [rcx]
0x18000302a  jz      short loc_180002FEE
0x18000302c  mov     [rsi], ax
0x18000302f  mov     rcx, [rdi]; lpsz
0x180003032  call    cs:__imp_CharNextW
0x180003038  mov     [rdi], rax
0x18000303b  jmp     short loc_1800030B1
0x18000303d  movzx   ecx, cx
0x180003040  sub     ecx, 9
0x180003043  jz      short loc_1800030AC
0x180003045  sub     ecx, 1
0x180003048  jz      short loc_1800030AC
0x18000304a  sub     ecx, 3
0x18000304d  jz      short loc_1800030AC
0x18000304f  cmp     ecx, 13h
0x180003052  jz      short loc_1800030AC
0x180003054  mov     rcx, rbx; lpsz
0x180003057  call    cs:__imp_CharNextW
0x18000305d  mov     rcx, rax
0x180003060  mov     [rdi], rax
0x180003063  sub     rcx, rbx
0x180003066  sar     rcx, 1
0x180003069  lea     rdx, [rsi+rcx*2]
0x18000306d  lea     rcx, [rbp+2000h]
0x180003074  cmp     rdx, rcx
0x180003077  jnb     loc_180002FEE
0x18000307d  mov     rcx, rbx
0x180003080  cmp     rbx, rax
0x180003083  jnb     short loc_18000309D
0x180003085  movzx   eax, word ptr [rcx]
0x180003088  add     rcx, 2
0x18000308c  mov     [rsi], ax
0x18000308f  add     rsi, 2
0x180003093  mov     rbx, [rdi]
0x180003096  cmp     rcx, rbx
0x180003099  jb      short loc_180003085
0x18000309b  jmp     short loc_1800030A0
0x18000309d  mov     rbx, rax
0x1800030a0  xor     eax, eax
0x1800030a2  cmp     ax, [rbx]
0x1800030a5  jz      short loc_1800030AC
0x1800030a7  movzx   ecx, word ptr [rbx]
0x1800030aa  jmp     short loc_18000303D
0x1800030ac  xor     eax, eax
0x1800030ae  mov     [rsi], ax
0x1800030b1  xor     eax, eax
0x1800030b3  jmp     loc_180002FF3
```
