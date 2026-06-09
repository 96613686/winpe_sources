# CheckOAEPPadding

- ea: `0x18002bb90`
- end: `0x18002be37`
- name: `CheckOAEPPadding`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001bdf8`

## callees

- `0x180009e76`
- `0x18002bb90`
- `0x18002be40`
- `0x18002c048`
- `0x18002c068`
- `0x18002c428`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x18002bd5a`
- `bcrypt!BCryptFinishHash` at `0x18002bd5a`
- `bcrypt!BCryptDestroyHash` at `0x18002be0a`
- `bcrypt!BCryptDestroyHash` at `0x18002be0a`
- `bcrypt!BCryptHashData` at `0x18002bd30`
- `bcrypt!BCryptHashData` at `0x18002bd30`
- `bcrypt!BCryptCreateHash` at `0x18002bcfc`
- `bcrypt!BCryptCreateHash` at `0x18002bcfc`

## pseudocode

```c
__int64 __fastcall CheckOAEPPadding(
        void *a1,
        __int64 j,
        __int64 a3,
        UCHAR *a4,
        ULONG cbInput,
        _BYTE *a6,
        unsigned int a7,
        void *a8,
        unsigned int a9,
        unsigned int *a10)
{
  ULONG v10; // r13d
  __int64 v11; // rdi
  unsigned int v13; // esi
  __int64 v14; // rax
  __int64 v15; // rbp
  unsigned int v16; // ebx
  NTSTATUS v17; // eax
  __int64 v18; // r9
  __int64 v19; // rcx
  __int64 v20; // r9
  unsigned int v21; // eax
  __int64 v22; // rdx
  PUCHAR v23; // r10
  __int64 v24; // r9
  UCHAR *v25; // r14
  UCHAR *i; // r8
  PUCHAR v27; // r15
  unsigned int v28; // esi
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-48h] BYREF
  PUCHAR pbOutput; // [rsp+48h] [rbp-40h]

  v10 = a3;
  v11 = (unsigned int)j;
  phHash = 0;
  if ( a7 < (int)j + 1 || *a6 )
  {
    v15 = 0;
    v18 = 728;
LABEL_38:
    v16 = -1073741811;
    v19 = 3221225485LL;
  }
  else
  {
    v13 = a7 - j - 1;
    v14 = MSCryptAlloc((_DWORD)j + 5 + (_DWORD)a3 + 2 * ((_DWORD)j + 5) + 2 * v13);
    v15 = v14;
    if ( !v14 )
    {
      v16 = -1073741801;
      goto LABEL_40;
    }
    v17 = MaskGeneration(a1, (unsigned int)v11, v10, &a6[v11 + 1], v13, v14, v11);
    v16 = v17;
    if ( v17 >= 0 )
    {
      v20 = v11 + v15;
      v21 = 0;
      for ( pbOutput = (PUCHAR)(v11 + v15 + v11);
            v21 < (unsigned int)v11;
            *(_BYTE *)(v22 + v20) = *(_BYTE *)(v22 + v15) ^ a6[v21] )
      {
        v22 = v21++;
      }
      v17 = MaskGeneration(a1, (unsigned int)v11, v10, v20, v11, v11 + v15 + v11, v13);
      v16 = v17;
      if ( v17 >= 0 )
      {
        v23 = pbOutput;
        v24 = 0;
        v25 = &pbOutput[v13];
        pbOutput = &v25[v13];
        for ( i = (UCHAR *)((unsigned __int64)&pbOutput[v11 + 15] & 0xFFFFFFFFFFFFFFF0uLL);
              (unsigned int)v24 < v13;
              v24 = (unsigned int)(v24 + 1) )
        {
          v25[v24] = v23[v24] ^ a6[(unsigned int)(v11 + 1 + v24)];
        }
        v17 = BCryptCreateHash(a1, &phHash, i, v10, 0, 0, 0);
        v16 = v17;
        if ( v17 >= 0 )
        {
          if ( cbInput && (v17 = BCryptHashData(phHash, a4, cbInput, 0), v16 = v17, v17 < 0) )
          {
            v18 = 813;
          }
          else
          {
            v27 = pbOutput;
            v17 = BCryptFinishHash(phHash, pbOutput, v11, 0);
            v16 = v17;
            if ( v17 >= 0 )
            {
              for ( j = 0; (unsigned int)j < (unsigned int)v11; j = (unsigned int)(j + 1) )
              {
                if ( v27[j] != v25[j] )
                {
                  v18 = 834;
                  goto LABEL_38;
                }
              }
              while ( (unsigned int)v11 < v13 )
              {
                if ( v25[v11] == 1 )
                {
                  LODWORD(v11) = v11 + 1;
                  break;
                }
                if ( v25[v11] )
                {
                  v18 = 850;
                  goto LABEL_38;
                }
                v11 = (unsigned int)(v11 + 1);
              }
              v28 = v13 - v11;
              *a10 = v28;
              if ( a8 )
              {
                if ( a9 < v28 )
                {
                  v16 = -1073741789;
                  goto LABEL_40;
                }
                memcpy_0(a8, &v25[(unsigned int)v11], v28);
              }
              v16 = 0;
              goto LABEL_40;
            }
            v18 = 824;
          }
        }
        else
        {
          v18 = 800;
        }
      }
      else
      {
        v18 = 780;
      }
    }
    else
    {
      v18 = 760;
    }
    v19 = (unsigned int)v17;
  }
  DebugTraceError(v19, j, a3, v18);
LABEL_40:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v15 )
    MSCryptFree(v15);
  return v16;
}

```

## disassembly

```asm
0x18002bb90  mov     rax, rsp
0x18002bb93  mov     [rax+10h], rbx
0x18002bb97  mov     [rax+20h], r9
0x18002bb9b  mov     [rax+8], rcx
0x18002bb9f  push    rbp
0x18002bba0  push    rsi
0x18002bba1  push    rdi
0x18002bba2  push    r12
0x18002bba4  push    r13
0x18002bba6  push    r14
0x18002bba8  push    r15
0x18002bbaa  sub     rsp, 50h
0x18002bbae  mov     esi, [rsp+88h+arg_30]
0x18002bbb5  mov     r13d, r8d
0x18002bbb8  mov     edi, edx
0x18002bbba  mov     r14, rcx
0x18002bbbd  mov     qword ptr [rax-48h], 0
0x18002bbc5  lea     eax, [rdi+1]
0x18002bbc8  cmp     esi, eax
0x18002bbca  jb      loc_18002BDE9
0x18002bbd0  mov     r15, [rsp+88h+arg_28]
0x18002bbd8  cmp     byte ptr [r15], 0
0x18002bbdc  jnz     loc_18002BDE9
0x18002bbe2  lea     ecx, [rdi+5]
0x18002bbe5  sub     esi, edi
0x18002bbe7  lea     eax, [rcx+r8]
0x18002bbeb  dec     esi
0x18002bbed  lea     eax, [rax+rcx*2]
0x18002bbf0  lea     ecx, [rax+rsi*2]
0x18002bbf3  call    MSCryptAlloc
0x18002bbf8  mov     rbp, rax
0x18002bbfb  test    rax, rax
0x18002bbfe  jnz     short loc_18002BC0A
0x18002bc00  mov     ebx, 0C0000017h
0x18002bc05  jmp     loc_18002BE00
0x18002bc0a  mov     [rsp+88h+dwFlags], edi
0x18002bc0e  lea     r9, [r15+1]
0x18002bc12  add     r9, rdi
0x18002bc15  mov     qword ptr [rsp+88h+cbSecret], rbp
0x18002bc1a  mov     r8d, r13d
0x18002bc1d  mov     dword ptr [rsp+88h+pbSecret], esi
0x18002bc21  mov     edx, edi
0x18002bc23  mov     rcx, r14
0x18002bc26  call    MaskGeneration
0x18002bc2b  mov     ebx, eax
0x18002bc2d  test    eax, eax
0x18002bc2f  jns     short loc_18002BC3E
0x18002bc31  mov     r9d, 2F8h
0x18002bc37  mov     ecx, eax
0x18002bc39  jmp     loc_18002BDFB
0x18002bc3e  lea     r9, [rdi+rbp]
0x18002bc42  xor     eax, eax
0x18002bc44  lea     r10, [r9+rdi]
0x18002bc48  mov     [rsp+88h+pbOutput], r10
0x18002bc4d  test    edi, edi
0x18002bc4f  jz      short loc_18002BC6A
0x18002bc51  mov     edx, eax
0x18002bc53  lea     r8d, [rax+1]
0x18002bc57  mov     cl, [r8+r15]
0x18002bc5b  mov     eax, r8d
0x18002bc5e  xor     cl, [rdx+rbp]
0x18002bc61  mov     [rdx+r9], cl
0x18002bc65  cmp     r8d, edi
0x18002bc68  jb      short loc_18002BC51
0x18002bc6a  mov     [rsp+88h+dwFlags], esi
0x18002bc6e  mov     r8d, r13d
0x18002bc71  mov     qword ptr [rsp+88h+cbSecret], r10
0x18002bc76  mov     edx, edi
0x18002bc78  mov     rcx, r14
0x18002bc7b  mov     dword ptr [rsp+88h+pbSecret], edi
0x18002bc7f  call    MaskGeneration
0x18002bc84  mov     ebx, eax
0x18002bc86  test    eax, eax
0x18002bc88  jns     short loc_18002BC92
0x18002bc8a  mov     r9d, 30Ch
0x18002bc90  jmp     short loc_18002BC37
0x18002bc92  mov     r10, [rsp+88h+pbOutput]
0x18002bc97  lea     r8, [rdi+0Fh]
0x18002bc9b  mov     eax, esi
0x18002bc9d  xor     r9d, r9d
0x18002bca0  lea     r14, [rsi+r10]
0x18002bca4  add     rax, r14
0x18002bca7  add     r8, rax
0x18002bcaa  mov     [rsp+88h+pbOutput], rax
0x18002bcaf  and     r8, 0FFFFFFFFFFFFFFF0h; pbHashObject
0x18002bcb3  test    esi, esi
0x18002bcb5  jz      short loc_18002BCD3
0x18002bcb7  lea     r11d, [rdi+1]
0x18002bcbb  lea     eax, [r11+r9]
0x18002bcbf  mov     al, [rax+r15]
0x18002bcc3  xor     al, [r9+r10]
0x18002bcc7  mov     [r9+r14], al
0x18002bccb  inc     r9d
0x18002bcce  cmp     r9d, esi
0x18002bcd1  jb      short loc_18002BCBB
0x18002bcd3  mov     rcx, [rsp+88h+hAlgorithm]; hAlgorithm
0x18002bcdb  lea     rdx, [rsp+88h+phHash]; phHash
0x18002bce0  mov     [rsp+88h+dwFlags], 0; dwFlags
0x18002bce8  mov     r9d, r13d; cbHashObject
0x18002bceb  mov     [rsp+88h+cbSecret], 0; cbSecret
0x18002bcf3  mov     [rsp+88h+pbSecret], 0; pbSecret
0x18002bcfc  call    cs:__imp_BCryptCreateHash
0x18002bd02  mov     ebx, eax
0x18002bd04  test    eax, eax
0x18002bd06  jns     short loc_18002BD13
0x18002bd08  mov     r9d, 320h
0x18002bd0e  jmp     loc_18002BC37
0x18002bd13  mov     r8d, [rsp+88h+cbInput]; cbInput
0x18002bd1b  test    r8d, r8d
0x18002bd1e  jz      short loc_18002BD47
0x18002bd20  mov     rdx, [rsp+88h+pbInput]; pbInput
0x18002bd28  xor     r9d, r9d; dwFlags
0x18002bd2b  mov     rcx, [rsp+88h+phHash]; hHash
0x18002bd30  call    cs:__imp_BCryptHashData
0x18002bd36  mov     ebx, eax
0x18002bd38  test    eax, eax
0x18002bd3a  jns     short loc_18002BD47
0x18002bd3c  mov     r9d, 32Dh
0x18002bd42  jmp     loc_18002BC37
0x18002bd47  mov     r15, [rsp+88h+pbOutput]
0x18002bd4c  xor     r9d, r9d; dwFlags
0x18002bd4f  mov     rcx, [rsp+88h+phHash]; hHash
0x18002bd54  mov     rdx, r15; pbOutput
0x18002bd57  mov     r8d, edi; cbOutput
0x18002bd5a  call    cs:__imp_BCryptFinishHash
0x18002bd60  mov     ebx, eax
0x18002bd62  test    eax, eax
0x18002bd64  jns     short loc_18002BD71
0x18002bd66  mov     r9d, 338h
0x18002bd6c  jmp     loc_18002BC37
0x18002bd71  xor     edx, edx
0x18002bd73  cmp     edx, edi
0x18002bd75  jnb     short loc_18002BD8D
0x18002bd77  mov     al, [rdx+r14]
0x18002bd7b  cmp     [rdx+r15], al
0x18002bd7f  jnz     short loc_18002BD85
0x18002bd81  inc     edx
0x18002bd83  jmp     short loc_18002BD73
0x18002bd85  mov     r9d, 342h
0x18002bd8b  jmp     short loc_18002BDF1
0x18002bd8d  cmp     edi, esi
0x18002bd8f  jnb     short loc_18002BDAD
0x18002bd91  cmp     byte ptr [rdi+r14], 1
0x18002bd96  jz      short loc_18002BDAB
0x18002bd98  cmp     byte ptr [rdi+r14], 0
0x18002bd9d  jnz     short loc_18002BDA3
0x18002bd9f  inc     edi
0x18002bda1  jmp     short loc_18002BD8D
0x18002bda3  mov     r9d, 352h
0x18002bda9  jmp     short loc_18002BDF1
0x18002bdab  inc     edi
0x18002bdad  mov     rax, [rsp+88h+arg_48]
0x18002bdb5  sub     esi, edi
0x18002bdb7  mov     rcx, [rsp+88h+arg_38]; void *
0x18002bdbf  mov     [rax], esi
0x18002bdc1  test    rcx, rcx
0x18002bdc4  jnz     short loc_18002BDCA
0x18002bdc6  xor     ebx, ebx
0x18002bdc8  jmp     short loc_18002BE00
0x18002bdca  cmp     [rsp+88h+arg_40], esi
0x18002bdd1  jnb     short loc_18002BDDA
0x18002bdd3  mov     ebx, 0C0000023h
0x18002bdd8  jmp     short loc_18002BE00
0x18002bdda  mov     edx, edi
0x18002bddc  add     rdx, r14; Src
0x18002bddf  mov     r8d, esi; Size
0x18002bde2  call    memcpy_0
0x18002bde7  jmp     short loc_18002BDC6
0x18002bde9  xor     ebp, ebp
0x18002bdeb  mov     r9d, 2D8h
0x18002bdf1  mov     ebx, 0C000000Dh
0x18002bdf6  mov     ecx, 0C000000Dh
0x18002bdfb  call    DebugTraceError
0x18002be00  mov     rcx, [rsp+88h+phHash]; hHash
0x18002be05  test    rcx, rcx
0x18002be08  jz      short loc_18002BE10
0x18002be0a  call    cs:__imp_BCryptDestroyHash
0x18002be10  test    rbp, rbp
0x18002be13  jz      short loc_18002BE1D
0x18002be15  mov     rcx, rbp
0x18002be18  call    MSCryptFree
0x18002be1d  mov     eax, ebx
0x18002be1f  mov     rbx, [rsp+88h+arg_8]
0x18002be27  add     rsp, 50h
0x18002be2b  pop     r15
0x18002be2d  pop     r14
0x18002be2f  pop     r13
0x18002be31  pop     r12
0x18002be33  pop     rdi
0x18002be34  pop     rsi
0x18002be35  pop     rbp
0x18002be36  retn
```
