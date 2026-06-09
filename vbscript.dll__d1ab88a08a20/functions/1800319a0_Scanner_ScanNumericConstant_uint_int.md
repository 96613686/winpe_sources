# Scanner::ScanNumericConstant(uint,int)

- ea: `0x1800319a0`
- end: `0x180031d73`
- name: `?ScanNumericConstant@Scanner@@AEAA?AW4tokens@@IH@Z`
- size: `979`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a6c0`

## callees

- `0x1800319a0`
- `0x180034360`
- `0x180042688`
- `0x180042738`

## import_xrefs

- `msvcrt!toupper` at `0x180031d27`
- `msvcrt!toupper` at `0x180031d27`
- `OLEAUT32!__imp_VarR8FromStr` at `0x180031c1a`
- `OLEAUT32!__imp_VarR8FromStr` at `0x180031c1a`

## pseudocode

```c
__int64 __fastcall Scanner::ScanNumericConstant(__int64 a1, unsigned int a2, int a3)
{
  _DWORD *v3; // rax
  int v4; // esi
  __int64 v5; // r12
  int v6; // r14d
  int v7; // r15d
  int v8; // ebp
  unsigned int v10; // edi
  int v12; // ecx
  int v13; // ecx
  int v14; // ebp
  int v15; // r8d
  int v16; // edi
  int v17; // r14d
  unsigned int v18; // ecx
  int v19; // ecx
  int v20; // eax
  __int64 result; // rax
  unsigned __int16 *v22; // rax
  unsigned __int16 *v23; // rax
  int v24; // r15d
  int v25; // r8d
  unsigned int v26; // edx
  unsigned __int16 *v27; // rax
  unsigned __int16 *v28; // rcx
  unsigned __int16 *v29; // rax
  _WORD *v30; // rax

  v3 = *(_DWORD **)(a1 + 8);
  v4 = 0;
  v5 = *(_QWORD *)(a1 + 40);
  v6 = 0;
  v7 = 0;
  *(_DWORD *)(a1 + 88) = 0;
  v8 = 0;
  *v3 = 185;
  v10 = a2;
  if ( a2 == 38 )
  {
    v28 = *(unsigned __int16 **)(a1 + 40);
    v10 = *v28;
    if ( v10 != 72 )
    {
      if ( v10 == 79 )
      {
LABEL_59:
        v4 = 8;
LABEL_61:
        *(_QWORD *)(a1 + 40) = v28 + 1;
        v10 = v28[1];
        v29 = v28 + 2;
        goto LABEL_62;
      }
      if ( v10 != 104 )
      {
        if ( v10 != 111 )
        {
          v4 = 8;
          v29 = v28 + 1;
LABEL_62:
          *(_QWORD *)(a1 + 40) = v29;
          goto LABEL_2;
        }
        goto LABEL_59;
      }
    }
    v4 = 16;
    goto LABEL_61;
  }
  while ( 1 )
  {
LABEL_2:
    if ( *(_DWORD *)(a1 + 88) >= *(_DWORD *)(a1 + 84) )
      Scanner::GrowBuf((Scanner *)a1);
    *(_WORD *)(*(_QWORD *)(a1 + 96) + 2LL * *(int *)(a1 + 88)) = v10;
    v12 = *(_DWORD *)(a1 + 88);
    *(_DWORD *)(a1 + 88) = v12 + 1;
    if ( (unsigned __int16)v10 >= 0x80u )
      break;
    if ( *((_BYTE *)&qword_180080C50[8] + v10) == 3 )
    {
      if ( v10 > 0x37 && v4 == 8 )
        goto LABEL_32;
      v8 = 1;
LABEL_31:
      v22 = *(unsigned __int16 **)(a1 + 40);
      v10 = *v22;
      *(_QWORD *)(a1 + 40) = v22 + 1;
    }
    else if ( v10 != 46 || v6 || v7 || v4 )
    {
      if ( v4 != 16 || (*((_BYTE *)&qword_180080C10 + v10) & 4) == 0 )
      {
        if ( ((v10 - 69) & 0xFFFFFFDF) != 0 || v7 || v4 )
          break;
        if ( !v8 )
          goto LABEL_32;
        v7 = 1;
        **(_DWORD **)(a1 + 8) = 186;
        v26 = **(unsigned __int16 **)(a1 + 40);
        if ( ((v26 - 43) & 0xFFFFFFFD) == 0 )
        {
          Scanner::AppendBufCh((Scanner *)a1, v26);
          *(_QWORD *)(a1 + 40) += 2LL;
        }
        goto LABEL_31;
      }
      v27 = *(unsigned __int16 **)(a1 + 40);
      v8 = 1;
      v10 = *v27;
      *(_QWORD *)(a1 + 40) = v27 + 1;
    }
    else
    {
      v6 = 1;
      **(_DWORD **)(a1 + 8) = 186;
      v23 = *(unsigned __int16 **)(a1 + 40);
      v10 = *v23;
      *(_QWORD *)(a1 + 40) = v23 + 1;
    }
  }
  *(_QWORD *)(a1 + 40) -= 2LL;
  *(_DWORD *)(a1 + 88) = v12;
  if ( v12 >= *(_DWORD *)(a1 + 84) )
    Scanner::GrowBuf((Scanner *)a1);
  *(_WORD *)(*(_QWORD *)(a1 + 96) + 2LL * *(int *)(a1 + 88)) = 0;
  v13 = *(_DWORD *)(a1 + 88);
  *(_DWORD *)(a1 + 88) = v13 + 1;
  *(_DWORD *)(*(_QWORD *)(a1 + 96) - 4LL) = 2 * v13;
  if ( v8 )
  {
    v14 = 0;
    if ( v4 )
    {
      v30 = *(_WORD **)(a1 + 40);
      if ( *v30 == 38 )
      {
        v14 = 1;
        *(_QWORD *)(a1 + 40) = v30 + 1;
      }
    }
    if ( **(_DWORD **)(a1 + 8) == 185 )
    {
      v15 = 0;
      v16 = 0;
      if ( v4 == 8 )
      {
        v17 = -536870912;
      }
      else
      {
        v17 = 0;
        if ( v4 == 16 )
          v17 = -268435456;
      }
      do
      {
        v18 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 96) + 2LL * v16);
        if ( v4 )
        {
          if ( (v17 & v15) != 0 )
            goto LABEL_32;
          v24 = v4 * v15;
          if ( v18 > 0x39 )
            v25 = toupper(v18) - 55;
          else
            v25 = v18 - 48;
          v15 = v24 | v25;
        }
        else
        {
          v19 = v18 + 10 * v15 - 48;
          if ( v19 / 10 < v15 )
          {
            **(_DWORD **)(a1 + 8) = 186;
            goto LABEL_44;
          }
          v15 = v19;
        }
        ++v16;
      }
      while ( v16 < *(_DWORD *)(a1 + 84) && *(_WORD *)(*(_QWORD *)(a1 + 96) + 2LL * v16) );
      if ( !v14 )
      {
        v20 = -65536;
        if ( !v4 )
          v20 = -32768;
        if ( (v20 & v15) == 0 )
          v15 = (__int16)v15;
      }
      *(_DWORD *)(*(_QWORD *)(a1 + 8) + 8LL) = v15;
      return **(unsigned int **)(a1 + 8);
    }
LABEL_44:
    if ( !VarR8FromStr(*(LPCOLESTR *)(a1 + 96), 0x409u, 0x80000000, (DOUBLE *)(*(_QWORD *)(a1 + 8) + 8LL)) )
      return **(unsigned int **)(a1 + 8);
  }
LABEL_32:
  if ( a3 )
  {
    if ( (*(_BYTE *)(a1 + 64) & 8) == 0 )
      Scanner::Error((Scanner *)a1, 1031);
    result = 180;
    **(_DWORD **)(a1 + 8) = 180;
  }
  else
  {
    *(_QWORD *)(a1 + 40) = v5;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800319a0  push    rbx
0x1800319a2  push    rbp
0x1800319a3  push    rsi
0x1800319a4  push    rdi
0x1800319a5  push    r12
0x1800319a7  push    r13
0x1800319a9  push    r14
0x1800319ab  push    r15
0x1800319ad  sub     rsp, 28h
0x1800319b1  mov     rax, [rcx+8]
0x1800319b5  xor     esi, esi
0x1800319b7  mov     r12, [rcx+28h]
0x1800319bb  xor     r14d, r14d
0x1800319be  xor     r15d, r15d
0x1800319c1  mov     [rcx+58h], esi
0x1800319c4  xor     ebp, ebp
0x1800319c6  mov     r13d, r8d
0x1800319c9  mov     dword ptr [rax], 0B9h
0x1800319cf  mov     edi, edx
0x1800319d1  mov     rbx, rcx
0x1800319d4  cmp     edx, 26h ; '&'
0x1800319d7  jz      loc_180031CA0
0x1800319dd  lea     rdx, __ImageBase
0x1800319e4  mov     eax, [rbx+54h]
0x1800319e7  cmp     [rbx+58h], eax
0x1800319ea  jge     loc_180031B6A
0x1800319f0  movsxd  rcx, dword ptr [rbx+58h]
0x1800319f4  mov     rax, [rbx+60h]
0x1800319f8  mov     [rax+rcx*2], di
0x1800319fc  mov     ecx, [rbx+58h]
0x1800319ff  lea     eax, [rcx+1]
0x180031a02  mov     [rbx+58h], eax
0x180031a05  mov     eax, 80h
0x180031a0a  cmp     di, ax
0x180031a0d  jnb     short loc_180031A3F
0x180031a0f  mov     eax, edi
0x180031a11  cmp     byte ptr [rax+rdx+80C90h], 3
0x180031a19  jz      loc_180031B37
0x180031a1f  cmp     edi, 2Eh ; '.'
0x180031a22  jz      loc_180031B7E
0x180031a28  cmp     esi, 10h
0x180031a2b  jz      loc_180031C79
0x180031a31  lea     eax, [rdi-45h]
0x180031a34  test    eax, 0FFFFFFDFh
0x180031a39  jz      loc_180031C33
0x180031a3f  add     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFEh
0x180031a44  mov     [rbx+58h], ecx
0x180031a47  cmp     ecx, [rbx+54h]
0x180031a4a  jge     loc_180031BDD
0x180031a50  movsxd  rdx, dword ptr [rbx+58h]
0x180031a54  xor     eax, eax
0x180031a56  mov     rcx, [rbx+60h]
0x180031a5a  mov     [rcx+rdx*2], ax
0x180031a5e  mov     ecx, [rbx+58h]
0x180031a61  lea     eax, [rcx+1]
0x180031a64  add     ecx, ecx
0x180031a66  mov     [rbx+58h], eax
0x180031a69  mov     rax, [rbx+60h]
0x180031a6d  mov     [rax-4], ecx
0x180031a70  test    ebp, ebp
0x180031a72  jz      loc_180031B59
0x180031a78  xor     ebp, ebp
0x180031a7a  test    esi, esi
0x180031a7c  jnz     loc_180031CFC
0x180031a82  mov     rax, [rbx+8]
0x180031a86  cmp     dword ptr [rax], 0B9h
0x180031a8c  jnz     loc_180031C03
0x180031a92  xor     r8d, r8d
0x180031a95  xor     edi, edi
0x180031a97  cmp     esi, 8
0x180031a9a  jz      loc_180031D1C
0x180031aa0  xor     r14d, r14d
0x180031aa3  cmp     esi, 10h
0x180031aa6  jz      loc_180031BEA
0x180031aac  mov     rax, [rbx+60h]
0x180031ab0  movsxd  rcx, edi
0x180031ab3  movzx   ecx, word ptr [rax+rcx*2]; C
0x180031ab7  test    esi, esi
0x180031ab9  jnz     loc_180031BBC
0x180031abf  lea     eax, [r8+r8*4]
0x180031ac3  lea     ecx, [rcx+rax*2]
0x180031ac6  mov     eax, 66666667h
0x180031acb  add     ecx, 0FFFFFFD0h
0x180031ace  imul    ecx
0x180031ad0  sar     edx, 2
0x180031ad3  mov     eax, edx
0x180031ad5  shr     eax, 1Fh
0x180031ad8  add     edx, eax
0x180031ada  cmp     edx, r8d
0x180031add  jl      loc_180031D3C
0x180031ae3  mov     r8d, ecx
0x180031ae6  inc     edi
0x180031ae8  cmp     edi, [rbx+54h]
0x180031aeb  jge     short loc_180031AFB
0x180031aed  mov     rcx, [rbx+60h]
0x180031af1  movsxd  rdx, edi
0x180031af4  cmp     word ptr [rcx+rdx*2], 0
0x180031af9  jnz     short loc_180031AAC
0x180031afb  test    ebp, ebp
0x180031afd  jnz     short loc_180031B17
0x180031aff  test    esi, esi
0x180031b01  mov     eax, 0FFFF0000h
0x180031b06  mov     ecx, 0FFFF8000h
0x180031b0b  cmovz   eax, ecx
0x180031b0e  test    r8d, eax
0x180031b11  jnz     short loc_180031B17
0x180031b13  movsx   r8d, r8w
0x180031b17  mov     rax, [rbx+8]
0x180031b1b  mov     [rax+8], r8d
0x180031b1f  mov     rax, [rbx+8]
0x180031b23  mov     eax, [rax]
0x180031b25  add     rsp, 28h
0x180031b29  pop     r15
0x180031b2b  pop     r14
0x180031b2d  pop     r13
0x180031b2f  pop     r12
0x180031b31  pop     rdi
0x180031b32  pop     rsi
0x180031b33  pop     rbp
0x180031b34  pop     rbx
0x180031b35  retn
0x180031b37  cmp     edi, 37h ; '7'
0x180031b3a  ja      loc_180031BF5
0x180031b40  mov     ebp, 1
0x180031b45  mov     rax, [rbx+28h]
0x180031b49  movzx   edi, word ptr [rax]
0x180031b4c  add     rax, 2
0x180031b50  mov     [rbx+28h], rax
0x180031b54  jmp     loc_1800319E4
0x180031b59  test    r13d, r13d
0x180031b5c  jnz     loc_180031D4B
0x180031b62  mov     [rbx+28h], r12
0x180031b66  xor     eax, eax
0x180031b68  jmp     short loc_180031B25
0x180031b6a  mov     rcx, rbx; this
0x180031b6d  call    ?GrowBuf@Scanner@@AEAAXXZ; Scanner::GrowBuf(void)
0x180031b72  lea     rdx, __ImageBase
0x180031b79  jmp     loc_1800319F0
0x180031b7e  test    r14d, r14d
0x180031b81  jnz     loc_180031A28
0x180031b87  test    r15d, r15d
0x180031b8a  jnz     loc_180031A28
0x180031b90  test    esi, esi
0x180031b92  jnz     loc_180031A28
0x180031b98  mov     rax, [rbx+8]
0x180031b9c  mov     r14d, 1
0x180031ba2  mov     dword ptr [rax], 0BAh
0x180031ba8  mov     rax, [rbx+28h]
0x180031bac  movzx   edi, word ptr [rax]
0x180031baf  add     rax, 2
0x180031bb3  mov     [rbx+28h], rax
0x180031bb7  jmp     loc_1800319E4
0x180031bbc  test    r8d, r14d
0x180031bbf  jnz     short loc_180031B59
0x180031bc1  imul    r8d, esi
0x180031bc5  mov     r15d, r8d
0x180031bc8  cmp     ecx, 39h ; '9'
0x180031bcb  ja      loc_180031D27
0x180031bd1  lea     r8d, [rcx-30h]
0x180031bd5  or      r8d, r15d
0x180031bd8  jmp     loc_180031AE6
0x180031bdd  mov     rcx, rbx; this
0x180031be0  call    ?GrowBuf@Scanner@@AEAAXXZ; Scanner::GrowBuf(void)
0x180031be5  jmp     loc_180031A50
0x180031bea  mov     r14d, 0F0000000h
0x180031bf0  jmp     loc_180031AAC
0x180031bf5  cmp     esi, 8
0x180031bf8  jnz     loc_180031B40
0x180031bfe  jmp     loc_180031B59
0x180031c03  mov     r9, [rbx+8]
0x180031c07  mov     edx, 409h; lcid
0x180031c0c  mov     rcx, [rbx+60h]; strIn
0x180031c10  add     r9, 8; pdblOut
0x180031c14  mov     r8d, 80000000h; dwFlags
0x180031c1a  call    cs:__imp_VarR8FromStr
0x180031c21  nop     dword ptr [rax+rax+00h]
0x180031c26  test    eax, eax
0x180031c28  jz      loc_180031B1F
0x180031c2e  jmp     loc_180031B59
0x180031c33  test    r15d, r15d
0x180031c36  jnz     loc_180031A3F
0x180031c3c  test    esi, esi
0x180031c3e  jnz     loc_180031A3F
0x180031c44  test    ebp, ebp
0x180031c46  jz      loc_180031B59
0x180031c4c  mov     rax, [rbx+8]
0x180031c50  mov     r15d, 1
0x180031c56  mov     dword ptr [rax], 0BAh
0x180031c5c  mov     rax, [rbx+28h]
0x180031c60  movzx   edx, word ptr [rax]; unsigned int
0x180031c63  lea     eax, [rdx-2Bh]
0x180031c66  test    eax, 0FFFFFFFDh
0x180031c6b  jz      short loc_180031CEA
0x180031c6d  lea     rdx, __ImageBase
0x180031c74  jmp     loc_180031B45
0x180031c79  test    byte ptr [rax+rdx+80C10h], 4
0x180031c81  jz      loc_180031A31
0x180031c87  mov     rax, [rbx+28h]
0x180031c8b  mov     ebp, 1
0x180031c90  movzx   edi, word ptr [rax]
0x180031c93  add     rax, 2
0x180031c97  mov     [rbx+28h], rax
0x180031c9b  jmp     loc_1800319E4
0x180031ca0  mov     rcx, [rcx+28h]
0x180031ca4  movzx   edi, word ptr [rcx]
0x180031ca7  cmp     edi, 48h ; 'H'
0x180031caa  jz      short loc_180031CCD
0x180031cac  cmp     edi, 4Fh ; 'O'
0x180031caf  jz      short loc_180031CC6
0x180031cb1  cmp     edi, 68h ; 'h'
0x180031cb4  jz      short loc_180031CCD
0x180031cb6  cmp     edi, 6Fh ; 'o'
0x180031cb9  jz      short loc_180031CC6
0x180031cbb  mov     esi, 8
0x180031cc0  lea     rax, [rcx+2]
0x180031cc4  jmp     short loc_180031CE1
0x180031cc6  mov     esi, 8
0x180031ccb  jmp     short loc_180031CD2
0x180031ccd  mov     esi, 10h
0x180031cd2  lea     rax, [rcx+2]
0x180031cd6  mov     [rbx+28h], rax
0x180031cda  movzx   edi, word ptr [rax]
0x180031cdd  lea     rax, [rcx+4]
0x180031ce1  mov     [rbx+28h], rax
0x180031ce5  jmp     loc_1800319DD
0x180031cea  mov     rcx, rbx; this
0x180031ced  call    ?AppendBufCh@Scanner@@AEAAXI@Z; Scanner::AppendBufCh(uint)
0x180031cf2  add     qword ptr [rbx+28h], 2
0x180031cf7  jmp     loc_180031C6D
0x180031cfc  mov     rax, [rbx+28h]
0x180031d00  cmp     word ptr [rax], 26h ; '&'
0x180031d04  jnz     loc_180031A82
0x180031d0a  add     rax, 2
0x180031d0e  mov     ebp, 1
0x180031d13  mov     [rbx+28h], rax
0x180031d17  jmp     loc_180031A82
0x180031d1c  mov     r14d, 0E0000000h
0x180031d22  jmp     loc_180031AAC
0x180031d27  call    cs:__imp_toupper
0x180031d2e  nop     dword ptr [rax+rax+00h]
0x180031d33  lea     r8d, [rax-37h]
0x180031d37  jmp     loc_180031BD5
0x180031d3c  mov     rax, [rbx+8]
0x180031d40  mov     dword ptr [rax], 0BAh
0x180031d46  jmp     loc_180031C03
0x180031d4b  test    byte ptr [rbx+40h], 8
0x180031d4f  jz      short loc_180031D65
0x180031d51  mov     rcx, [rbx+8]
0x180031d55  mov     eax, 0B4h
0x180031d5a  mov     dword ptr [rcx], 0B4h
0x180031d60  jmp     loc_180031B25
0x180031d65  mov     edx, 407h; int
0x180031d6a  mov     rcx, rbx; this
0x180031d6d  call    ?Error@Scanner@@AEAAXH@Z; Scanner::Error(int)
```
