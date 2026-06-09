# wfioReadHeaders

- ea: `0x1801fe070`
- end: `0x1801fe3f7`
- name: `wfioReadHeaders`
- size: `903`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1801fdec8`

## callees

- `0x18007aae4`
- `0x1801fe070`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1801fe0be`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1801fe0eb`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1801fe107`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1801fe131`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1801fe155`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1801fe1fb`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1801fe380`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1801fe3a5`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1801fe3d8`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1801fe0be`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1801fe0eb`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1801fe107`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1801fe131`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1801fe155`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1801fe1fb`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1801fe380`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1801fe3a5`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1801fe3d8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801fe191`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801fe191`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1801fe179`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1801fe3c3`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1801fe179`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1801fe3c3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1801fe1cb`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1801fe1cb`

## pseudocode

```c
__int64 __fastcall wfioReadHeaders(__int64 a1)
{
  unsigned int v2; // edi
  FILE *v3; // r9
  FILE *v4; // r9
  __int64 v5; // r14
  int v6; // r15d
  size_t v7; // rbx
  __int64 v8; // r14
  void *v9; // rcx
  unsigned int v11; // eax
  void *v12; // rax
  size_t v13; // r8
  __int16 *v14; // rcx
  __int16 v15; // ax
  __int64 v16; // rdx
  _WORD *v17; // rcx
  __int64 v18; // rax
  size_t v19; // r14
  FILE *v20; // r9
  size_t v21; // r14
  int Buffer; // [rsp+60h] [rbp+40h] BYREF
  size_t ElementCount; // [rsp+68h] [rbp+48h] BYREF

  LODWORD(ElementCount) = 0;
  Buffer = 0;
  v2 = 1;
  if ( !a1 )
    return v2;
  v3 = *(FILE **)(a1 + 8);
  if ( v3 )
  {
    if ( fread(&Buffer, 1u, 4u, v3) == 4 )
    {
      if ( Buffer != 1179011410 )
        goto LABEL_16;
      v4 = *(FILE **)(a1 + 8);
      *(_QWORD *)(a1 + 16) = 4;
      if ( fread(&ElementCount, 1u, 4u, v4) == 4 && fread(&Buffer, 1u, 4u, *(FILE **)(a1 + 8)) == 4 )
      {
        if ( Buffer != 1163280727 )
          goto LABEL_16;
        v5 = 12;
        v6 = 0;
        do
        {
          if ( fread(&Buffer, 1u, 4u, *(FILE **)(a1 + 8)) != 4 )
            break;
          if ( Buffer == 544501094 )
            v6 = 1;
          if ( fread(&ElementCount, 1u, 4u, *(FILE **)(a1 + 8)) != 4 )
            break;
          v7 = (unsigned int)ElementCount;
          v8 = v5 + 8;
          if ( v6 )
          {
            v11 = 40;
            *(_DWORD *)(a1 + 40) = ElementCount;
            if ( (unsigned int)v7 >= 0x28 )
              v11 = v7;
            else
              *(_DWORD *)(a1 + 40) = 40;
            v12 = malloc(v11);
            *(_QWORD *)(a1 + 32) = v12;
            if ( !v12 )
            {
              v2 = 7;
              goto LABEL_16;
            }
            memset_0(v12, 0, *(unsigned int *)(a1 + 40));
            v13 = fread(*(void **)(a1 + 32), 1u, v7, *(FILE **)(a1 + 8));
            if ( v13 != v7 )
              break;
            v14 = *(__int16 **)(a1 + 32);
            v15 = *v14;
            if ( *v14 != -2 && v15 != 354 && ((v15 - 1) & 0xFFFD) == 0 )
            {
              v14[9] = v14[7];
              v16 = *(_QWORD *)(a1 + 32);
              if ( *(_WORD *)(v16 + 2) == 1 )
              {
                *(_DWORD *)(v16 + 20) = 4;
              }
              else if ( *(_WORD *)(v16 + 2) == 2 )
              {
                *(_DWORD *)(v16 + 20) = 3;
              }
              else
              {
                *(_DWORD *)(v16 + 20) = 63;
              }
            }
            v17 = *(_WORD **)(a1 + 32);
            if ( *v17 == 1 )
              v17[8] = 0;
            v18 = *(_QWORD *)(a1 + 32);
            if ( *(_WORD *)v18 == 0xFFFE )
            {
              if ( (*(_BYTE *)(v18 + 14) & 7) != 0 || *(_WORD *)(v18 + 16) != 22 )
                goto LABEL_16;
              if ( *(_DWORD *)(v18 + 24) != 1 )
                goto LABEL_59;
              if ( *(_WORD *)(v18 + 28)
                || *(_WORD *)(v18 + 30) != 16
                || *(_BYTE *)(v18 + 32) != 0x80
                || *(_BYTE *)(v18 + 33)
                || *(_BYTE *)(v18 + 34)
                || *(_BYTE *)(v18 + 35) != 0xAA
                || *(_BYTE *)(v18 + 36)
                || *(_BYTE *)(v18 + 37) != 56
                || *(_BYTE *)(v18 + 38) != 0x9B )
              {
                goto LABEL_16;
              }
              if ( *(_BYTE *)(v18 + 39) != 113 )
              {
LABEL_59:
                if ( *(_DWORD *)(v18 + 24) != 3
                  || *(_WORD *)(v18 + 28)
                  || *(_WORD *)(v18 + 30) != 16
                  || *(_BYTE *)(v18 + 32) != 0x80
                  || *(_BYTE *)(v18 + 33)
                  || *(_BYTE *)(v18 + 34)
                  || *(_BYTE *)(v18 + 35) != 0xAA
                  || *(_BYTE *)(v18 + 36)
                  || *(_BYTE *)(v18 + 37) != 56
                  || *(_BYTE *)(v18 + 38) != 0x9B
                  || *(_BYTE *)(v18 + 39) != 113 )
                {
                  goto LABEL_16;
                }
              }
            }
            v19 = v13 + v8;
            while ( 1 )
            {
              if ( fread(&Buffer, 1u, 4u, *(FILE **)(a1 + 8)) != 4 )
                goto LABEL_65;
              v20 = *(FILE **)(a1 + 8);
              v21 = v19 + 4;
              if ( Buffer == 1635017060 )
                break;
              if ( fread(&ElementCount, 1u, 4u, v20) == 4 )
              {
                v19 = (unsigned int)ElementCount + 4LL + v21;
                if ( !fseek(*(FILE **)(a1 + 8), v19, 0) )
                  continue;
              }
              goto LABEL_65;
            }
            *(_QWORD *)(a1 + 24) = v21;
            if ( fread(&ElementCount, 1u, 4u, v20) != 4 )
            {
LABEL_65:
              v2 = 16;
              goto LABEL_16;
            }
            *(_DWORD *)(a1 + 44) = ElementCount;
            *(_DWORD *)(a1 + 48) = v21 + 4;
            return 0;
          }
          v5 = (unsigned int)ElementCount + v8;
        }
        while ( !fseek(*(FILE **)(a1 + 8), v5, 0) );
      }
    }
    v2 = 16;
  }
LABEL_16:
  v9 = *(void **)(a1 + 32);
  if ( v9 )
  {
    free(v9);
    *(_QWORD *)(a1 + 32) = 0;
    *(_DWORD *)(a1 + 40) = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x1801fe070  mov     [rsp-38h+arg_18], rbx
0x1801fe075  push    rbp
0x1801fe076  push    rsi
0x1801fe077  push    rdi
0x1801fe078  push    r12
0x1801fe07a  push    r13
0x1801fe07c  push    r14
0x1801fe07e  push    r15
0x1801fe080  mov     rbp, rsp
0x1801fe083  sub     rsp, 20h
0x1801fe087  xor     r12d, r12d
0x1801fe08a  mov     rsi, rcx
0x1801fe08d  mov     dword ptr [rbp+ElementCount], r12d
0x1801fe091  mov     [rbp+Buffer], r12d
0x1801fe095  lea     edi, [r12+1]
0x1801fe09a  test    rcx, rcx
0x1801fe09d  jz      loc_1801FE19F
0x1801fe0a3  mov     r9, [rcx+8]; Stream
0x1801fe0a7  test    r9, r9
0x1801fe0aa  jz      loc_1801FE188
0x1801fe0b0  lea     r13d, [r12+4]
0x1801fe0b5  mov     edx, edi; ElementSize
0x1801fe0b7  mov     r8d, r13d; ElementCount
0x1801fe0ba  lea     rcx, [rbp+Buffer]; Buffer
0x1801fe0be  call    cs:__imp_fread
0x1801fe0c4  cmp     rax, r13
0x1801fe0c7  jnz     loc_1801FE183
0x1801fe0cd  cmp     [rbp+Buffer], 46464952h
0x1801fe0d4  jnz     loc_1801FE188
0x1801fe0da  mov     r9, [rsi+8]; Stream
0x1801fe0de  lea     rcx, [rbp+ElementCount]; Buffer
0x1801fe0e2  mov     r8d, r13d; ElementCount
0x1801fe0e5  mov     [rsi+10h], r13
0x1801fe0e9  mov     edx, edi; ElementSize
0x1801fe0eb  call    cs:__imp_fread
0x1801fe0f1  cmp     rax, r13
0x1801fe0f4  jnz     loc_1801FE183
0x1801fe0fa  mov     r9, [rsi+8]; Stream
0x1801fe0fe  lea     rcx, [rbp+Buffer]; Buffer
0x1801fe102  mov     r8d, r13d; ElementCount
0x1801fe105  mov     edx, edi; ElementSize
0x1801fe107  call    cs:__imp_fread
0x1801fe10d  cmp     rax, r13
0x1801fe110  jnz     short loc_1801FE183
0x1801fe112  cmp     [rbp+Buffer], 45564157h
0x1801fe119  jnz     short loc_1801FE188
0x1801fe11b  lea     r14d, [r12+0Ch]
0x1801fe120  mov     r15d, r12d
0x1801fe123  mov     r9, [rsi+8]; Stream
0x1801fe127  lea     rcx, [rbp+Buffer]; Buffer
0x1801fe12b  mov     r8, r13; ElementCount
0x1801fe12e  mov     rdx, rdi; ElementSize
0x1801fe131  call    cs:__imp_fread
0x1801fe137  cmp     rax, r13
0x1801fe13a  jnz     short loc_1801FE183
0x1801fe13c  cmp     [rbp+Buffer], 20746D66h
0x1801fe143  lea     rcx, [rbp+ElementCount]; Buffer
0x1801fe147  mov     r9, [rsi+8]; Stream
0x1801fe14b  mov     r8, r13; ElementCount
0x1801fe14e  mov     rdx, rdi; ElementSize
0x1801fe151  cmovz   r15d, edi
0x1801fe155  call    cs:__imp_fread
0x1801fe15b  cmp     rax, r13
0x1801fe15e  jnz     short loc_1801FE183
0x1801fe160  mov     ebx, dword ptr [rbp+ElementCount]
0x1801fe163  add     r14, 8
0x1801fe167  test    r15d, r15d
0x1801fe16a  jnz     short loc_1801FE1B6
0x1801fe16c  mov     rcx, [rsi+8]; Stream
0x1801fe170  add     r14, rbx
0x1801fe173  mov     edx, r14d; Offset
0x1801fe176  xor     r8d, r8d; Origin
0x1801fe179  call    cs:__imp_fseek
0x1801fe17f  test    eax, eax
0x1801fe181  jz      short loc_1801FE123
0x1801fe183  mov     edi, 10h
0x1801fe188  mov     rcx, [rsi+20h]; Block
0x1801fe18c  test    rcx, rcx
0x1801fe18f  jz      short loc_1801FE19F
0x1801fe191  call    cs:__imp_free
0x1801fe197  mov     [rsi+20h], r12
0x1801fe19b  mov     [rsi+28h], r12d
0x1801fe19f  mov     eax, edi
0x1801fe1a1  mov     rbx, [rsp+20h+arg_18]
0x1801fe1a6  add     rsp, 20h
0x1801fe1aa  pop     r15
0x1801fe1ac  pop     r14
0x1801fe1ae  pop     r13
0x1801fe1b0  pop     r12
0x1801fe1b2  pop     rdi
0x1801fe1b3  pop     rsi
0x1801fe1b4  pop     rbp
0x1801fe1b5  retn
0x1801fe1b6  mov     eax, 28h ; '('
0x1801fe1bb  mov     [rsi+28h], ebx
0x1801fe1be  cmp     ebx, eax
0x1801fe1c0  jnb     short loc_1801FE1C7
0x1801fe1c2  mov     [rsi+28h], eax
0x1801fe1c5  jmp     short loc_1801FE1C9
0x1801fe1c7  mov     eax, ebx
0x1801fe1c9  mov     ecx, eax; Size
0x1801fe1cb  call    cs:__imp_malloc
0x1801fe1d1  mov     [rsi+20h], rax
0x1801fe1d5  test    rax, rax
0x1801fe1d8  jnz     short loc_1801FE1DF
0x1801fe1da  lea     edi, [rax+7]
0x1801fe1dd  jmp     short loc_1801FE188
0x1801fe1df  mov     r8d, [rsi+28h]; Size
0x1801fe1e3  xor     edx, edx; Val
0x1801fe1e5  mov     rcx, rax; void *
0x1801fe1e8  call    memset_0
0x1801fe1ed  mov     r9, [rsi+8]; Stream
0x1801fe1f1  mov     r8, rbx; ElementCount
0x1801fe1f4  mov     rcx, [rsi+20h]; Buffer
0x1801fe1f8  mov     rdx, rdi; ElementSize
0x1801fe1fb  call    cs:__imp_fread
0x1801fe201  mov     r8, rax
0x1801fe204  cmp     rax, rbx
0x1801fe207  jnz     loc_1801FE183
0x1801fe20d  mov     rcx, [rsi+20h]
0x1801fe211  mov     r9d, 0FFFEh
0x1801fe217  movzx   eax, word ptr [rcx]
0x1801fe21a  cmp     ax, r9w
0x1801fe21e  jz      short loc_1801FE264
0x1801fe220  mov     edx, 162h
0x1801fe225  cmp     ax, dx
0x1801fe228  jz      short loc_1801FE264
0x1801fe22a  sub     ax, di
0x1801fe22d  lea     edx, [r9-1]
0x1801fe231  test    dx, ax
0x1801fe234  jnz     short loc_1801FE264
0x1801fe236  movzx   eax, word ptr [rcx+0Eh]
0x1801fe23a  mov     [rcx+12h], ax
0x1801fe23e  mov     rdx, [rsi+20h]
0x1801fe242  movzx   ecx, word ptr [rdx+2]
0x1801fe246  sub     ecx, edi
0x1801fe248  jz      short loc_1801FE260
0x1801fe24a  cmp     ecx, edi
0x1801fe24c  jz      short loc_1801FE257
0x1801fe24e  mov     dword ptr [rdx+14h], 3Fh ; '?'
0x1801fe255  jmp     short loc_1801FE264
0x1801fe257  mov     dword ptr [rdx+14h], 3
0x1801fe25e  jmp     short loc_1801FE264
0x1801fe260  mov     [rdx+14h], r13d
0x1801fe264  mov     rcx, [rsi+20h]
0x1801fe268  cmp     [rcx], di
0x1801fe26b  jnz     short loc_1801FE272
0x1801fe26d  mov     [rcx+10h], r12w
0x1801fe272  mov     rax, [rsi+20h]
0x1801fe276  mov     ebx, 10h
0x1801fe27b  cmp     [rax], r9w
0x1801fe27f  jnz     loc_1801FE36F
0x1801fe285  test    byte ptr [rax+0Eh], 7
0x1801fe289  jnz     loc_1801FE188
0x1801fe28f  cmp     word ptr [rax+10h], 16h
0x1801fe294  jnz     loc_1801FE188
0x1801fe29a  cmp     [rax+18h], edi
0x1801fe29d  jnz     short loc_1801FE300
0x1801fe29f  cmp     [rax+1Ch], r12w
0x1801fe2a4  jnz     loc_1801FE188
0x1801fe2aa  cmp     [rax+1Eh], bx
0x1801fe2ae  jnz     loc_1801FE188
0x1801fe2b4  cmp     byte ptr [rax+20h], 80h
0x1801fe2b8  jnz     loc_1801FE188
0x1801fe2be  cmp     [rax+21h], r12b
0x1801fe2c2  jnz     loc_1801FE188
0x1801fe2c8  cmp     [rax+22h], r12b
0x1801fe2cc  jnz     loc_1801FE188
0x1801fe2d2  cmp     byte ptr [rax+23h], 0AAh
0x1801fe2d6  jnz     loc_1801FE188
0x1801fe2dc  cmp     [rax+24h], r12b
0x1801fe2e0  jnz     loc_1801FE188
0x1801fe2e6  cmp     byte ptr [rax+25h], 38h ; '8'
0x1801fe2ea  jnz     loc_1801FE188
0x1801fe2f0  cmp     byte ptr [rax+26h], 9Bh
0x1801fe2f4  jnz     loc_1801FE188
0x1801fe2fa  cmp     byte ptr [rax+27h], 71h ; 'q'
0x1801fe2fe  jz      short loc_1801FE36F
0x1801fe300  cmp     dword ptr [rax+18h], 3
0x1801fe304  jnz     loc_1801FE188
0x1801fe30a  cmp     [rax+1Ch], r12w
0x1801fe30f  jnz     loc_1801FE188
0x1801fe315  cmp     [rax+1Eh], bx
0x1801fe319  jnz     loc_1801FE188
0x1801fe31f  cmp     byte ptr [rax+20h], 80h
0x1801fe323  jnz     loc_1801FE188
0x1801fe329  cmp     [rax+21h], r12b
0x1801fe32d  jnz     loc_1801FE188
0x1801fe333  cmp     [rax+22h], r12b
0x1801fe337  jnz     loc_1801FE188
0x1801fe33d  cmp     byte ptr [rax+23h], 0AAh
0x1801fe341  jnz     loc_1801FE188
0x1801fe347  cmp     [rax+24h], r12b
0x1801fe34b  jnz     loc_1801FE188
0x1801fe351  cmp     byte ptr [rax+25h], 38h ; '8'
0x1801fe355  jnz     loc_1801FE188
0x1801fe35b  cmp     byte ptr [rax+26h], 9Bh
0x1801fe35f  jnz     loc_1801FE188
0x1801fe365  cmp     byte ptr [rax+27h], 71h ; 'q'
0x1801fe369  jnz     loc_1801FE188
0x1801fe36f  add     r14, r8
0x1801fe372  mov     r9, [rsi+8]; Stream
0x1801fe376  lea     rcx, [rbp+Buffer]; Buffer
0x1801fe37a  mov     r8, r13; ElementCount
0x1801fe37d  mov     rdx, rdi; ElementSize
0x1801fe380  call    cs:__imp_fread
0x1801fe386  cmp     rax, r13
0x1801fe389  jnz     short loc_1801FE3CD
0x1801fe38b  mov     r9, [rsi+8]; Stream
0x1801fe38f  lea     rcx, [rbp+ElementCount]; Buffer
0x1801fe393  add     r14, r13
0x1801fe396  mov     r8, r13; ElementCount
0x1801fe399  cmp     [rbp+Buffer], 61746164h
0x1801fe3a0  mov     rdx, rdi; ElementSize
0x1801fe3a3  jz      short loc_1801FE3D4
0x1801fe3a5  call    cs:__imp_fread
0x1801fe3ab  cmp     rax, r13
0x1801fe3ae  jnz     short loc_1801FE3CD
0x1801fe3b0  mov     eax, dword ptr [rbp+ElementCount]
0x1801fe3b3  xor     r8d, r8d; Origin
0x1801fe3b6  mov     rcx, [rsi+8]; Stream
0x1801fe3ba  add     rax, r13
0x1801fe3bd  add     r14, rax
0x1801fe3c0  mov     edx, r14d; Offset
0x1801fe3c3  call    cs:__imp_fseek
0x1801fe3c9  test    eax, eax
0x1801fe3cb  jz      short loc_1801FE372
0x1801fe3cd  mov     edi, ebx
0x1801fe3cf  jmp     loc_1801FE188
0x1801fe3d4  mov     [rsi+18h], r14
0x1801fe3d8  call    cs:__imp_fread
0x1801fe3de  cmp     rax, r13
0x1801fe3e1  jnz     short loc_1801FE3CD
0x1801fe3e3  mov     eax, dword ptr [rbp+ElementCount]
0x1801fe3e6  mov     [rsi+2Ch], eax
0x1801fe3e9  lea     eax, [r14+4]
0x1801fe3ed  mov     [rsi+30h], eax
0x1801fe3f0  xor     eax, eax
0x1801fe3f2  jmp     loc_1801FE1A1
```
