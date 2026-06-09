# Scanner::ScanNumericConstant(uint,int)

- ea: `0x18002cea0`
- end: `0x18002d266`
- name: `?ScanNumericConstant@Scanner@@AEAA?AW4tokens@@IH@Z`
- size: `966`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c4b0`

## callees

- `0x18002cea0`
- `0x18002f5f0`
- `0x180040fc8`
- `0x18004106c`

## import_xrefs

- `msvcrt!toupper` at `0x18002d220`
- `msvcrt!toupper` at `0x18002d220`
- `OLEAUT32!__imp_VarR8FromStr` at `0x18002d119`
- `OLEAUT32!__imp_VarR8FromStr` at `0x18002d119`

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
    if ( *((_BYTE *)&qword_18007DC10[8] + v10) == 3 )
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
      if ( v4 != 16 || (*((_BYTE *)&qword_18007DBD0 + v10) & 4) == 0 )
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
0x18002cea0  push    rbx
0x18002cea2  push    rbp
0x18002cea3  push    rsi
0x18002cea4  push    rdi
0x18002cea5  push    r12
0x18002cea7  push    r13
0x18002cea9  push    r14
0x18002ceab  push    r15
0x18002cead  sub     rsp, 28h
0x18002ceb1  mov     rax, [rcx+8]
0x18002ceb5  xor     esi, esi
0x18002ceb7  mov     r12, [rcx+28h]
0x18002cebb  xor     r14d, r14d
0x18002cebe  xor     r15d, r15d
0x18002cec1  mov     [rcx+58h], esi
0x18002cec4  xor     ebp, ebp
0x18002cec6  mov     r13d, r8d
0x18002cec9  mov     dword ptr [rax], 0B9h
0x18002cecf  mov     edi, edx
0x18002ced1  mov     rbx, rcx
0x18002ced4  cmp     edx, 26h ; '&'
0x18002ced7  jz      loc_18002D199
0x18002cedd  lea     rdx, __ImageBase
0x18002cee4  mov     eax, [rbx+54h]
0x18002cee7  cmp     [rbx+58h], eax
0x18002ceea  jge     loc_18002D069
0x18002cef0  movsxd  rcx, dword ptr [rbx+58h]
0x18002cef4  mov     rax, [rbx+60h]
0x18002cef8  mov     [rax+rcx*2], di
0x18002cefc  mov     ecx, [rbx+58h]
0x18002ceff  lea     eax, [rcx+1]
0x18002cf02  mov     [rbx+58h], eax
0x18002cf05  mov     eax, 80h
0x18002cf0a  cmp     di, ax
0x18002cf0d  jnb     short loc_18002CF3F
0x18002cf0f  mov     eax, edi
0x18002cf11  cmp     byte ptr [rax+rdx+7DC50h], 3
0x18002cf19  jz      loc_18002D036
0x18002cf1f  cmp     edi, 2Eh ; '.'
0x18002cf22  jz      loc_18002D07D
0x18002cf28  cmp     esi, 10h
0x18002cf2b  jz      loc_18002D172
0x18002cf31  lea     eax, [rdi-45h]
0x18002cf34  test    eax, 0FFFFFFDFh
0x18002cf39  jz      loc_18002D12C
0x18002cf3f  add     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFEh
0x18002cf44  mov     [rbx+58h], ecx
0x18002cf47  cmp     ecx, [rbx+54h]
0x18002cf4a  jge     loc_18002D0DC
0x18002cf50  movsxd  rdx, dword ptr [rbx+58h]
0x18002cf54  xor     eax, eax
0x18002cf56  mov     rcx, [rbx+60h]
0x18002cf5a  mov     [rcx+rdx*2], ax
0x18002cf5e  mov     ecx, [rbx+58h]
0x18002cf61  lea     eax, [rcx+1]
0x18002cf64  add     ecx, ecx
0x18002cf66  mov     [rbx+58h], eax
0x18002cf69  mov     rax, [rbx+60h]
0x18002cf6d  mov     [rax-4], ecx
0x18002cf70  test    ebp, ebp
0x18002cf72  jz      loc_18002D058
0x18002cf78  xor     ebp, ebp
0x18002cf7a  test    esi, esi
0x18002cf7c  jnz     loc_18002D1F5
0x18002cf82  mov     rax, [rbx+8]
0x18002cf86  cmp     dword ptr [rax], 0B9h
0x18002cf8c  jnz     loc_18002D102
0x18002cf92  xor     r8d, r8d
0x18002cf95  xor     edi, edi
0x18002cf97  cmp     esi, 8
0x18002cf9a  jz      loc_18002D215
0x18002cfa0  xor     r14d, r14d
0x18002cfa3  cmp     esi, 10h
0x18002cfa6  jz      loc_18002D0E9
0x18002cfac  mov     rax, [rbx+60h]
0x18002cfb0  movsxd  rcx, edi
0x18002cfb3  movzx   ecx, word ptr [rax+rcx*2]; C
0x18002cfb7  test    esi, esi
0x18002cfb9  jnz     loc_18002D0BB
0x18002cfbf  lea     eax, [r8+r8*4]
0x18002cfc3  lea     ecx, [rcx+rax*2]
0x18002cfc6  mov     eax, 66666667h
0x18002cfcb  add     ecx, 0FFFFFFD0h
0x18002cfce  imul    ecx
0x18002cfd0  sar     edx, 2
0x18002cfd3  mov     eax, edx
0x18002cfd5  shr     eax, 1Fh
0x18002cfd8  add     edx, eax
0x18002cfda  cmp     edx, r8d
0x18002cfdd  jl      loc_18002D22F
0x18002cfe3  mov     r8d, ecx
0x18002cfe6  inc     edi
0x18002cfe8  cmp     edi, [rbx+54h]
0x18002cfeb  jge     short loc_18002CFFB
0x18002cfed  mov     rcx, [rbx+60h]
0x18002cff1  movsxd  rdx, edi
0x18002cff4  cmp     word ptr [rcx+rdx*2], 0
0x18002cff9  jnz     short loc_18002CFAC
0x18002cffb  test    ebp, ebp
0x18002cffd  jnz     short loc_18002D017
0x18002cfff  test    esi, esi
0x18002d001  mov     eax, 0FFFF0000h
0x18002d006  mov     ecx, 0FFFF8000h
0x18002d00b  cmovz   eax, ecx
0x18002d00e  test    r8d, eax
0x18002d011  jnz     short loc_18002D017
0x18002d013  movsx   r8d, r8w
0x18002d017  mov     rax, [rbx+8]
0x18002d01b  mov     [rax+8], r8d
0x18002d01f  mov     rax, [rbx+8]
0x18002d023  mov     eax, [rax]
0x18002d025  add     rsp, 28h
0x18002d029  pop     r15
0x18002d02b  pop     r14
0x18002d02d  pop     r13
0x18002d02f  pop     r12
0x18002d031  pop     rdi
0x18002d032  pop     rsi
0x18002d033  pop     rbp
0x18002d034  pop     rbx
0x18002d035  retn
0x18002d036  cmp     edi, 37h ; '7'
0x18002d039  ja      loc_18002D0F4
0x18002d03f  mov     ebp, 1
0x18002d044  mov     rax, [rbx+28h]
0x18002d048  movzx   edi, word ptr [rax]
0x18002d04b  add     rax, 2
0x18002d04f  mov     [rbx+28h], rax
0x18002d053  jmp     loc_18002CEE4
0x18002d058  test    r13d, r13d
0x18002d05b  jnz     loc_18002D23E
0x18002d061  mov     [rbx+28h], r12
0x18002d065  xor     eax, eax
0x18002d067  jmp     short loc_18002D025
0x18002d069  mov     rcx, rbx; this
0x18002d06c  call    ?GrowBuf@Scanner@@AEAAXXZ; Scanner::GrowBuf(void)
0x18002d071  lea     rdx, __ImageBase
0x18002d078  jmp     loc_18002CEF0
0x18002d07d  test    r14d, r14d
0x18002d080  jnz     loc_18002CF28
0x18002d086  test    r15d, r15d
0x18002d089  jnz     loc_18002CF28
0x18002d08f  test    esi, esi
0x18002d091  jnz     loc_18002CF28
0x18002d097  mov     rax, [rbx+8]
0x18002d09b  mov     r14d, 1
0x18002d0a1  mov     dword ptr [rax], 0BAh
0x18002d0a7  mov     rax, [rbx+28h]
0x18002d0ab  movzx   edi, word ptr [rax]
0x18002d0ae  add     rax, 2
0x18002d0b2  mov     [rbx+28h], rax
0x18002d0b6  jmp     loc_18002CEE4
0x18002d0bb  test    r8d, r14d
0x18002d0be  jnz     short loc_18002D058
0x18002d0c0  imul    r8d, esi
0x18002d0c4  mov     r15d, r8d
0x18002d0c7  cmp     ecx, 39h ; '9'
0x18002d0ca  ja      loc_18002D220
0x18002d0d0  lea     r8d, [rcx-30h]
0x18002d0d4  or      r8d, r15d
0x18002d0d7  jmp     loc_18002CFE6
0x18002d0dc  mov     rcx, rbx; this
0x18002d0df  call    ?GrowBuf@Scanner@@AEAAXXZ; Scanner::GrowBuf(void)
0x18002d0e4  jmp     loc_18002CF50
0x18002d0e9  mov     r14d, 0F0000000h
0x18002d0ef  jmp     loc_18002CFAC
0x18002d0f4  cmp     esi, 8
0x18002d0f7  jnz     loc_18002D03F
0x18002d0fd  jmp     loc_18002D058
0x18002d102  mov     r9, [rbx+8]
0x18002d106  mov     edx, 409h; lcid
0x18002d10b  mov     rcx, [rbx+60h]; strIn
0x18002d10f  add     r9, 8; pdblOut
0x18002d113  mov     r8d, 80000000h; dwFlags
0x18002d119  call    cs:__imp_VarR8FromStr
0x18002d11f  test    eax, eax
0x18002d121  jz      loc_18002D01F
0x18002d127  jmp     loc_18002D058
0x18002d12c  test    r15d, r15d
0x18002d12f  jnz     loc_18002CF3F
0x18002d135  test    esi, esi
0x18002d137  jnz     loc_18002CF3F
0x18002d13d  test    ebp, ebp
0x18002d13f  jz      loc_18002D058
0x18002d145  mov     rax, [rbx+8]
0x18002d149  mov     r15d, 1
0x18002d14f  mov     dword ptr [rax], 0BAh
0x18002d155  mov     rax, [rbx+28h]
0x18002d159  movzx   edx, word ptr [rax]; unsigned int
0x18002d15c  lea     eax, [rdx-2Bh]
0x18002d15f  test    eax, 0FFFFFFFDh
0x18002d164  jz      short loc_18002D1E3
0x18002d166  lea     rdx, __ImageBase
0x18002d16d  jmp     loc_18002D044
0x18002d172  test    byte ptr [rax+rdx+7DBD0h], 4
0x18002d17a  jz      loc_18002CF31
0x18002d180  mov     rax, [rbx+28h]
0x18002d184  mov     ebp, 1
0x18002d189  movzx   edi, word ptr [rax]
0x18002d18c  add     rax, 2
0x18002d190  mov     [rbx+28h], rax
0x18002d194  jmp     loc_18002CEE4
0x18002d199  mov     rcx, [rcx+28h]
0x18002d19d  movzx   edi, word ptr [rcx]
0x18002d1a0  cmp     edi, 48h ; 'H'
0x18002d1a3  jz      short loc_18002D1C6
0x18002d1a5  cmp     edi, 4Fh ; 'O'
0x18002d1a8  jz      short loc_18002D1BF
0x18002d1aa  cmp     edi, 68h ; 'h'
0x18002d1ad  jz      short loc_18002D1C6
0x18002d1af  cmp     edi, 6Fh ; 'o'
0x18002d1b2  jz      short loc_18002D1BF
0x18002d1b4  mov     esi, 8
0x18002d1b9  lea     rax, [rcx+2]
0x18002d1bd  jmp     short loc_18002D1DA
0x18002d1bf  mov     esi, 8
0x18002d1c4  jmp     short loc_18002D1CB
0x18002d1c6  mov     esi, 10h
0x18002d1cb  lea     rax, [rcx+2]
0x18002d1cf  mov     [rbx+28h], rax
0x18002d1d3  movzx   edi, word ptr [rax]
0x18002d1d6  lea     rax, [rcx+4]
0x18002d1da  mov     [rbx+28h], rax
0x18002d1de  jmp     loc_18002CEDD
0x18002d1e3  mov     rcx, rbx; this
0x18002d1e6  call    ?AppendBufCh@Scanner@@AEAAXI@Z; Scanner::AppendBufCh(uint)
0x18002d1eb  add     qword ptr [rbx+28h], 2
0x18002d1f0  jmp     loc_18002D166
0x18002d1f5  mov     rax, [rbx+28h]
0x18002d1f9  cmp     word ptr [rax], 26h ; '&'
0x18002d1fd  jnz     loc_18002CF82
0x18002d203  add     rax, 2
0x18002d207  mov     ebp, 1
0x18002d20c  mov     [rbx+28h], rax
0x18002d210  jmp     loc_18002CF82
0x18002d215  mov     r14d, 0E0000000h
0x18002d21b  jmp     loc_18002CFAC
0x18002d220  call    cs:__imp_toupper
0x18002d226  lea     r8d, [rax-37h]
0x18002d22a  jmp     loc_18002D0D4
0x18002d22f  mov     rax, [rbx+8]
0x18002d233  mov     dword ptr [rax], 0BAh
0x18002d239  jmp     loc_18002D102
0x18002d23e  test    byte ptr [rbx+40h], 8
0x18002d242  jz      short loc_18002D258
0x18002d244  mov     rcx, [rbx+8]
0x18002d248  mov     eax, 0B4h
0x18002d24d  mov     dword ptr [rcx], 0B4h
0x18002d253  jmp     loc_18002D025
0x18002d258  mov     edx, 407h; int
0x18002d25d  mov     rcx, rbx; this
0x18002d260  call    ?Error@Scanner@@AEAAXH@Z; Scanner::Error(int)
```
