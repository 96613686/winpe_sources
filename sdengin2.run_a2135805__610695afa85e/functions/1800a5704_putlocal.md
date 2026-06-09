# putlocal

- ea: `0x1800a5704`
- end: `0x1800a5c1b`
- name: `putlocal`
- size: `1303`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800a0b44`
- `0x1800a0c30`

## callees

- `0x18009fa48`
- `0x1800a1f1c`
- `0x1800a5704`
- `0x1800cf552`
- `0x1800cf5c0`

## import_xrefs

- `msvcrt!free` at `0x1800a5893`
- `msvcrt!free` at `0x1800a5a0a`
- `msvcrt!free` at `0x1800a5b7c`
- `msvcrt!free` at `0x1800a5b90`
- `msvcrt!free` at `0x1800a5bb4`
- `msvcrt!free` at `0x1800a5bc3`
- `msvcrt!free` at `0x1800a5bde`
- `msvcrt!free` at `0x1800a5893`
- `msvcrt!free` at `0x1800a5a0a`
- `msvcrt!free` at `0x1800a5b7c`
- `msvcrt!free` at `0x1800a5b90`
- `msvcrt!free` at `0x1800a5bb4`
- `msvcrt!free` at `0x1800a5bc3`
- `msvcrt!free` at `0x1800a5bde`
- `msvcrt!malloc` at `0x1800a57d8`
- `msvcrt!malloc` at `0x1800a58d8`
- `msvcrt!malloc` at `0x1800a5a39`
- `msvcrt!malloc` at `0x1800a57d8`
- `msvcrt!malloc` at `0x1800a58d8`
- `msvcrt!malloc` at `0x1800a5a39`
- `KERNEL32!WriteFile` at `0x1800a59d8`
- `KERNEL32!WriteFile` at `0x1800a5b4e`
- `KERNEL32!WriteFile` at `0x1800a59d8`
- `KERNEL32!WriteFile` at `0x1800a5b4e`
- `USER32!CharToOemBuffA` at `0x1800a577d`
- `USER32!CharToOemBuffA` at `0x1800a577d`

## pseudocode

```c
__int64 __fastcall putlocal(__int64 a1, HANDLE *a2, __int64 a3)
{
  const CHAR *v6; // rcx
  DWORD v7; // r8d
  __int64 v8; // rax
  void *v10; // rdi
  unsigned __int16 v11; // r15
  __int64 v12; // r14
  size_t v13; // rsi
  char *v14; // rax
  __int64 v15; // r14
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // rcx
  __int64 v19; // r8
  unsigned __int64 v20; // rdx
  size_t v21; // rcx
  _DWORD *v22; // rax
  _DWORD *v23; // rsi
  unsigned __int16 v24; // ax
  size_t v25; // rbp
  size_t v26; // r8
  const void *v27; // rdx
  void *v28; // rcx
  _DWORD *v29; // rax
  unsigned __int16 v30; // ax
  int v31; // r13d
  int v32; // r12d
  __int16 v33; // r15
  size_t v34; // r15
  size_t v35; // r8
  const void *v36; // rdx
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-168h] BYREF
  CHAR szDst[272]; // [rsp+40h] [rbp-158h] BYREF

  NumberOfBytesWritten = 0;
  if ( *(_DWORD *)(a3 + 620) )
  {
    StringCchCopyA(szDst, 0x104u, *(STRSAFE_LPCSTR *)(a1 + 120));
  }
  else
  {
    v6 = *(const CHAR **)(a1 + 120);
    v7 = 1;
    if ( v6 )
    {
      v8 = -1;
      do
        ++v8;
      while ( v6[v8] );
      v7 = v8 + 1;
      if ( (unsigned int)(v8 + 1) > 0x104 )
        return 14;
    }
    CharToOemBuffA(v6, szDst, v7);
  }
  v10 = 0;
  v11 = 0;
  if ( *(_DWORD *)(a3 + 624) )
  {
    v12 = *(_QWORD *)(a1 + 16);
    if ( v12 > 0xFFFFFFFFLL || *(__int64 *)(a1 + 24) > 3500000000LL || *(__int16 *)(a3 + 3740) < 0 )
    {
      v13 = *(_QWORD *)(a1 + 40);
      v14 = (char *)malloc(v13 + 20);
      v10 = v14;
      if ( !v14 )
        return 4;
      *(_DWORD *)v14 = 1048577;
      v11 = 20;
      *(_QWORD *)(v14 + 4) = *(_QWORD *)(a1 + 24);
      *(_QWORD *)(v14 + 12) = v12;
      if ( v13 )
        memcpy_0(v14 + 20, *(const void **)(a1 + 96), v13);
    }
  }
  v15 = v11;
  if ( *(_QWORD *)(a3 + 216) == -1 )
  {
    v16 = *(_QWORD *)(a3 + 3576) != 0 ? 42LL : 30LL;
    v17 = v11 + v16;
    if ( v17 < v16 )
      goto LABEL_73;
    v18 = v17 + *(_QWORD *)(a1 + 32);
    if ( v18 < v17 )
      goto LABEL_73;
    v19 = v18 + *(_QWORD *)(a1 + 40);
    if ( v19 < v18 || v19 < 0 )
      goto LABEL_73;
    if ( (unsigned int)PromptForNewDisk(a1, a2, v19, a3) )
    {
      if ( v10 )
        free(v10);
      return *(_DWORD *)(a3 + 208) != 0 ? 9 : 19;
    }
    v20 = v11 + 31LL + *(_QWORD *)(a1 + 32);
    if ( v20 < (unsigned __int64)v11 + 31 )
      goto LABEL_73;
    v21 = v20 + *(_QWORD *)(a1 + 40);
    if ( v21 < v20 )
      goto LABEL_73;
    v22 = malloc(v21);
    v23 = v22;
    if ( v22 )
    {
      *v22 = 67324752;
      v24 = *(_WORD *)(a1 + 2);
      if ( !v11 && v24 >= 0x2Du )
        v24 = 21 - (*(_WORD *)(a1 + 6) != 9);
      *((_WORD *)v23 + 2) = v24;
      *((_WORD *)v23 + 3) = *(_WORD *)(a1 + 70);
      *((_WORD *)v23 + 4) = *(_WORD *)(a1 + 6);
      *(_DWORD *)((char *)v23 + 10) = *(_DWORD *)(a1 + 8);
      *(_DWORD *)((char *)v23 + 14) = *(_DWORD *)(a1 + 12);
      if ( v11 && (*(__int64 *)(a1 + 16) > 0xFFFFFFFFLL || *(__int64 *)(a1 + 24) > 0xFFFFFFFFLL) )
      {
        *(_QWORD *)((char *)v23 + 18) = -1;
      }
      else
      {
        *(_DWORD *)((char *)v23 + 18) = *(_DWORD *)(a1 + 16);
        *(_DWORD *)((char *)v23 + 22) = *(_DWORD *)(a1 + 24);
      }
      v25 = *(_QWORD *)(a1 + 32);
      *((_WORD *)v23 + 13) = *(_WORD *)(a1 + 32);
      *((_WORD *)v23 + 14) = *(_WORD *)(a1 + 40) + v11;
      memcpy_0((char *)v23 + 30, szDst, v25);
      v26 = *(_QWORD *)(a1 + 40);
      if ( v11 )
      {
        v26 += v11;
        v27 = v10;
      }
      else
      {
        if ( !v26 )
        {
LABEL_41:
          if ( !WriteFile(*a2, v23, *(_DWORD *)(a1 + 32) + v11 + *(_DWORD *)(a1 + 40) + 30, &NumberOfBytesWritten, 0)
            || NumberOfBytesWritten != *(_QWORD *)(a1 + 40) + 30LL + v11 + *(_QWORD *)(a1 + 32) )
          {
            free(v23);
            if ( !v10 )
              return 10;
            v28 = v10;
LABEL_70:
            free(v28);
            return 10;
          }
          goto LABEL_63;
        }
        v27 = *(const void **)(a1 + 96);
      }
      memcpy_0((char *)v23 + v25 + 30, v27, v26);
      goto LABEL_41;
    }
LABEL_72:
    if ( v10 )
LABEL_73:
      free(v10);
    return 4;
  }
  v29 = malloc(*(_QWORD *)(a1 + 40) + 31LL + v11 + *(_QWORD *)(a1 + 32));
  v23 = v29;
  if ( !v29 )
    goto LABEL_72;
  *v29 = 67324752;
  v30 = *(_WORD *)(a1 + 2);
  v31 = v11;
  if ( !v11 && v30 >= 0x2Du )
    v30 = 21 - (*(_WORD *)(a1 + 6) != 9);
  *((_WORD *)v23 + 2) = v30;
  v32 = *(_DWORD *)(a3 + 624);
  *((_WORD *)v23 + 3) = *(_WORD *)(a1 + 70);
  *((_WORD *)v23 + 4) = *(_WORD *)(a1 + 6);
  *(_DWORD *)((char *)v23 + 10) = *(_DWORD *)(a1 + 8);
  *(_DWORD *)((char *)v23 + 14) = *(_DWORD *)(a1 + 12);
  if ( v32 && (*(__int64 *)(a1 + 16) > 0xFFFFFFFFLL || *(__int64 *)(a1 + 24) > 0xFFFFFFFFLL) )
  {
    *(_QWORD *)((char *)v23 + 18) = -1;
  }
  else
  {
    *(_DWORD *)((char *)v23 + 18) = *(_DWORD *)(a1 + 16);
    *(_DWORD *)((char *)v23 + 22) = *(_DWORD *)(a1 + 24);
  }
  v33 = *(_WORD *)(a1 + 40) + v11;
  *((_WORD *)v23 + 13) = *(_WORD *)(a1 + 32);
  if ( !v32 )
    v33 = *(_WORD *)(a1 + 40);
  *((_WORD *)v23 + 14) = v33;
  v34 = *(_QWORD *)(a1 + 32);
  memcpy_0((char *)v23 + 30, szDst, v34);
  v35 = *(_QWORD *)(a1 + 40);
  if ( v32 )
  {
    v35 += v15;
    v36 = v10;
LABEL_60:
    memcpy_0((char *)v23 + v34 + 30, v36, v35);
    goto LABEL_61;
  }
  if ( v35 )
  {
    v36 = *(const void **)(a1 + 96);
    goto LABEL_60;
  }
LABEL_61:
  if ( !WriteFile(
          *(HANDLE *)(a3 + 216),
          v23,
          v31 + *(_DWORD *)(a1 + 32) + *(_DWORD *)(a1 + 40) + 30,
          &NumberOfBytesWritten,
          0)
    || NumberOfBytesWritten != *(_QWORD *)(a1 + 40) + 30LL + v15 + *(_QWORD *)(a1 + 32) )
  {
    if ( v10 )
      free(v10);
    v28 = v23;
    goto LABEL_70;
  }
LABEL_63:
  free(v23);
  if ( v10 )
    free(v10);
  else
    v15 = 0;
  *(_QWORD *)(a1 + 136) = v15;
  return 0;
}

```

## disassembly

```asm
0x1800a5704  mov     [rsp+arg_18], rbx
0x1800a5709  push    rbp
0x1800a570a  push    rsi
0x1800a570b  push    rdi
0x1800a570c  push    r12
0x1800a570e  push    r13
0x1800a5710  push    r14
0x1800a5712  push    r15
0x1800a5714  sub     rsp, 160h
0x1800a571b  mov     rax, cs:__security_cookie
0x1800a5722  xor     rax, rsp
0x1800a5725  mov     [rsp+198h+var_48], rax
0x1800a572d  xor     r13d, r13d
0x1800a5730  mov     rbp, r8
0x1800a5733  mov     r12, rdx
0x1800a5736  mov     rbx, rcx
0x1800a5739  mov     [rsp+198h+NumberOfBytesWritten], r13d
0x1800a573e  cmp     [r8+26Ch], r13d
0x1800a5745  jnz     short loc_1800A578B
0x1800a5747  mov     rcx, [rcx+78h]; lpszSrc
0x1800a574b  lea     r8d, [r13+1]; cchDstLength
0x1800a574f  test    rcx, rcx
0x1800a5752  jz      short loc_1800A5778
0x1800a5754  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a5758  inc     rax
0x1800a575b  cmp     [rcx+rax], r13b
0x1800a575f  jnz     short loc_1800A5758
0x1800a5761  lea     r8d, [rax+1]
0x1800a5765  cmp     r8d, 104h
0x1800a576c  jbe     short loc_1800A5778
0x1800a576e  mov     eax, 0Eh
0x1800a5773  jmp     loc_1800A5BEF
0x1800a5778  lea     rdx, [rsp+198h+szDst]; lpszDst
0x1800a577d  call    cs:__imp_CharToOemBuffA
0x1800a5784  nop     dword ptr [rax+rax+00h]
0x1800a5789  jmp     short loc_1800A579E
0x1800a578b  mov     r8, [rcx+78h]; pszSrc
0x1800a578f  mov     edx, 104h; cchDest
0x1800a5794  lea     rcx, [rsp+198h+szDst]; pszDest
0x1800a5799  call    StringCchCopyA
0x1800a579e  mov     rdi, r13
0x1800a57a1  mov     r15d, r13d
0x1800a57a4  mov     eax, 0FFFFFFFFh
0x1800a57a9  cmp     [rbp+270h], r13d
0x1800a57b0  jz      short loc_1800A581D
0x1800a57b2  mov     r14, [rbx+10h]
0x1800a57b6  cmp     r14, rax
0x1800a57b9  jg      short loc_1800A57D0
0x1800a57bb  mov     eax, 0D09DC300h
0x1800a57c0  cmp     [rbx+18h], rax
0x1800a57c4  jg      short loc_1800A57D0
0x1800a57c6  cmp     [rbp+0E9Ch], r13w
0x1800a57ce  jge     short loc_1800A581D
0x1800a57d0  mov     rsi, [rbx+28h]
0x1800a57d4  lea     rcx, [rsi+14h]; Size
0x1800a57d8  call    cs:__imp_malloc
0x1800a57df  nop     dword ptr [rax+rax+00h]
0x1800a57e4  mov     rdi, rax
0x1800a57e7  test    rax, rax
0x1800a57ea  jz      loc_1800A5BEA
0x1800a57f0  mov     dword ptr [rax], 100001h
0x1800a57f6  mov     r15d, 14h
0x1800a57fc  mov     rax, [rbx+18h]
0x1800a5800  mov     [rdi+4], rax
0x1800a5804  mov     [rdi+0Ch], r14
0x1800a5808  test    rsi, rsi
0x1800a580b  jz      short loc_1800A581D
0x1800a580d  mov     rdx, [rbx+60h]; Src
0x1800a5811  lea     rcx, [rdi+14h]; void *
0x1800a5815  mov     r8, rsi; Size
0x1800a5818  call    memcpy_0
0x1800a581d  cmp     qword ptr [rbp+0D8h], 0FFFFFFFFFFFFFFFFh
0x1800a5825  movzx   r14d, r15w
0x1800a5829  jnz     loc_1800A5A27
0x1800a582f  mov     rax, [rbp+0DF8h]
0x1800a5836  neg     rax
0x1800a5839  sbb     rcx, rcx
0x1800a583c  and     ecx, 0Ch
0x1800a583f  add     rcx, 1Eh
0x1800a5843  lea     rdx, [r14+rcx]
0x1800a5847  cmp     rdx, rcx
0x1800a584a  jb      loc_1800A5BDB
0x1800a5850  mov     rcx, [rbx+20h]
0x1800a5854  add     rcx, rdx
0x1800a5857  cmp     rcx, rdx
0x1800a585a  jb      loc_1800A5BDB
0x1800a5860  mov     r8, [rbx+28h]
0x1800a5864  add     r8, rcx
0x1800a5867  cmp     r8, rcx
0x1800a586a  jb      loc_1800A5BDB
0x1800a5870  test    r8, r8
0x1800a5873  js      loc_1800A5BDB
0x1800a5879  mov     r9, rbp
0x1800a587c  mov     rdx, r12
0x1800a587f  mov     rcx, rbx
0x1800a5882  call    PromptForNewDisk
0x1800a5887  test    eax, eax
0x1800a5889  jz      short loc_1800A58B4
0x1800a588b  test    rdi, rdi
0x1800a588e  jz      short loc_1800A589F
0x1800a5890  mov     rcx, rdi; Block
0x1800a5893  call    cs:__imp_free
0x1800a589a  nop     dword ptr [rax+rax+00h]
0x1800a589f  mov     eax, [rbp+0D0h]
0x1800a58a5  neg     eax
0x1800a58a7  sbb     eax, eax
0x1800a58a9  and     eax, 0FFFFFFF6h
0x1800a58ac  add     eax, 13h
0x1800a58af  jmp     loc_1800A5BEF
0x1800a58b4  mov     rdx, [rbx+20h]
0x1800a58b8  lea     rcx, [r14+1Fh]
0x1800a58bc  add     rdx, rcx
0x1800a58bf  cmp     rdx, rcx
0x1800a58c2  jb      loc_1800A5BDB
0x1800a58c8  mov     rcx, [rbx+28h]
0x1800a58cc  add     rcx, rdx; Size
0x1800a58cf  cmp     rcx, rdx
0x1800a58d2  jb      loc_1800A5BDB
0x1800a58d8  call    cs:__imp_malloc
0x1800a58df  nop     dword ptr [rax+rax+00h]
0x1800a58e4  mov     rsi, rax
0x1800a58e7  test    rax, rax
0x1800a58ea  jz      loc_1800A5BD6
0x1800a58f0  mov     dword ptr [rax], 4034B50h
0x1800a58f6  movzx   eax, word ptr [rbx+2]
0x1800a58fa  test    r15w, r15w
0x1800a58fe  jnz     short loc_1800A5918
0x1800a5900  cmp     ax, 2Dh ; '-'
0x1800a5904  jb      short loc_1800A5918
0x1800a5906  movzx   eax, word ptr [rbx+6]
0x1800a590a  sub     ax, 9
0x1800a590e  neg     ax
0x1800a5911  sbb     ax, ax
0x1800a5914  add     ax, 15h
0x1800a5918  mov     [rsi+4], ax
0x1800a591c  movzx   eax, word ptr [rbx+46h]
0x1800a5920  mov     [rsi+6], ax
0x1800a5924  movzx   eax, word ptr [rbx+6]
0x1800a5928  mov     [rsi+8], ax
0x1800a592c  mov     eax, [rbx+8]
0x1800a592f  mov     [rsi+0Ah], eax
0x1800a5932  mov     eax, [rbx+0Ch]
0x1800a5935  mov     [rsi+0Eh], eax
0x1800a5938  test    r15w, r15w
0x1800a593c  jz      short loc_1800A5959
0x1800a593e  mov     eax, 0FFFFFFFFh
0x1800a5943  cmp     [rbx+10h], rax
0x1800a5947  jg      short loc_1800A594F
0x1800a5949  cmp     [rbx+18h], rax
0x1800a594d  jle     short loc_1800A5959
0x1800a594f  mov     qword ptr [rsi+12h], 0FFFFFFFFFFFFFFFFh
0x1800a5957  jmp     short loc_1800A5965
0x1800a5959  mov     eax, [rbx+10h]
0x1800a595c  mov     [rsi+12h], eax
0x1800a595f  mov     eax, [rbx+18h]
0x1800a5962  mov     [rsi+16h], eax
0x1800a5965  movzx   eax, word ptr [rbx+20h]
0x1800a5969  lea     rcx, [rsi+1Eh]; void *
0x1800a596d  mov     rbp, [rbx+20h]
0x1800a5971  lea     rdx, [rsp+198h+szDst]; Src
0x1800a5976  mov     [rsi+1Ah], ax
0x1800a597a  mov     r8, rbp; Size
0x1800a597d  movzx   eax, r15w
0x1800a5981  add     ax, [rbx+28h]
0x1800a5985  mov     [rsi+1Ch], ax
0x1800a5989  call    memcpy_0
0x1800a598e  mov     r8, [rbx+28h]; Size
0x1800a5992  test    r15w, r15w
0x1800a5996  jz      short loc_1800A59A0
0x1800a5998  add     r8, r14
0x1800a599b  mov     rdx, rdi
0x1800a599e  jmp     short loc_1800A59A9
0x1800a59a0  test    r8, r8
0x1800a59a3  jz      short loc_1800A59B5
0x1800a59a5  mov     rdx, [rbx+60h]; Src
0x1800a59a9  lea     rcx, [rbp+1Eh]
0x1800a59ad  add     rcx, rsi; void *
0x1800a59b0  call    memcpy_0
0x1800a59b5  mov     r8d, [rbx+28h]
0x1800a59b9  lea     r9, [rsp+198h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800a59be  mov     rcx, [r12]; hFile
0x1800a59c2  add     r8d, 1Eh
0x1800a59c6  movzx   edx, r15w
0x1800a59ca  add     edx, [rbx+20h]
0x1800a59cd  add     r8d, edx; nNumberOfBytesToWrite
0x1800a59d0  mov     [rsp+198h+lpOverlapped], r13; lpOverlapped
0x1800a59d5  mov     rdx, rsi; lpBuffer
0x1800a59d8  call    cs:__imp_WriteFile
0x1800a59df  nop     dword ptr [rax+rax+00h]
0x1800a59e4  test    eax, eax
0x1800a59e6  jz      short loc_1800A5A07
0x1800a59e8  mov     rcx, [rbx+20h]
0x1800a59ec  mov     rax, [rbx+28h]
0x1800a59f0  add     rcx, r14
0x1800a59f3  add     rax, 1Eh
0x1800a59f7  add     rcx, rax
0x1800a59fa  mov     eax, [rsp+198h+NumberOfBytesWritten]
0x1800a59fe  cmp     rax, rcx
0x1800a5a01  jz      loc_1800A5B79
0x1800a5a07  mov     rcx, rsi; Block
0x1800a5a0a  call    cs:__imp_free
0x1800a5a11  nop     dword ptr [rax+rax+00h]
0x1800a5a16  test    rdi, rdi
0x1800a5a19  jz      loc_1800A5BCF
0x1800a5a1f  mov     rcx, rdi
0x1800a5a22  jmp     loc_1800A5BC3
0x1800a5a27  mov     rcx, [rbx+20h]
0x1800a5a2b  mov     rax, [rbx+28h]
0x1800a5a2f  add     rcx, r14
0x1800a5a32  add     rax, 1Fh
0x1800a5a36  add     rcx, rax; Size
0x1800a5a39  call    cs:__imp_malloc
0x1800a5a40  nop     dword ptr [rax+rax+00h]
0x1800a5a45  mov     rsi, rax
0x1800a5a48  test    rax, rax
0x1800a5a4b  jz      loc_1800A5BD6
0x1800a5a51  mov     dword ptr [rax], 4034B50h
0x1800a5a57  movzx   eax, word ptr [rbx+2]
0x1800a5a5b  movzx   r13d, r15w
0x1800a5a5f  test    r15w, r15w
0x1800a5a63  jnz     short loc_1800A5A7D
0x1800a5a65  cmp     ax, 2Dh ; '-'
0x1800a5a69  jb      short loc_1800A5A7D
0x1800a5a6b  movzx   eax, word ptr [rbx+6]
0x1800a5a6f  sub     ax, 9
0x1800a5a73  neg     ax
0x1800a5a76  sbb     ax, ax
0x1800a5a79  add     ax, 15h
0x1800a5a7d  mov     [rsi+4], ax
0x1800a5a81  movzx   eax, word ptr [rbx+46h]
0x1800a5a85  mov     r12d, [rbp+270h]
0x1800a5a8c  mov     [rsi+6], ax
0x1800a5a90  movzx   eax, word ptr [rbx+6]
0x1800a5a94  mov     [rsi+8], ax
0x1800a5a98  mov     eax, [rbx+8]
0x1800a5a9b  mov     [rsi+0Ah], eax
0x1800a5a9e  mov     eax, [rbx+0Ch]
0x1800a5aa1  mov     [rsi+0Eh], eax
0x1800a5aa4  test    r12d, r12d
0x1800a5aa7  jz      short loc_1800A5AC4
0x1800a5aa9  mov     eax, 0FFFFFFFFh
0x1800a5aae  cmp     [rbx+10h], rax
0x1800a5ab2  jg      short loc_1800A5ABA
0x1800a5ab4  cmp     [rbx+18h], rax
0x1800a5ab8  jle     short loc_1800A5AC4
0x1800a5aba  mov     qword ptr [rsi+12h], 0FFFFFFFFFFFFFFFFh
0x1800a5ac2  jmp     short loc_1800A5AD0
0x1800a5ac4  mov     eax, [rbx+10h]
0x1800a5ac7  mov     [rsi+12h], eax
0x1800a5aca  mov     eax, [rbx+18h]
0x1800a5acd  mov     [rsi+16h], eax
0x1800a5ad0  add     r15w, [rbx+28h]
0x1800a5ad5  lea     rcx, [rsi+1Eh]; void *
0x1800a5ad9  movzx   eax, word ptr [rbx+20h]
0x1800a5add  lea     rdx, [rsp+198h+szDst]; Src
0x1800a5ae2  mov     [rsi+1Ah], ax
0x1800a5ae6  test    r12d, r12d
0x1800a5ae9  cmovz   r15w, [rbx+28h]
0x1800a5aef  mov     [rsi+1Ch], r15w
0x1800a5af4  mov     r15, [rbx+20h]
0x1800a5af8  mov     r8, r15; Size
0x1800a5afb  call    memcpy_0
0x1800a5b00  mov     r8, [rbx+28h]; Size
0x1800a5b04  test    r12d, r12d
0x1800a5b07  jz      short loc_1800A5B11
0x1800a5b09  add     r8, r14
0x1800a5b0c  mov     rdx, rdi
0x1800a5b0f  jmp     short loc_1800A5B1A
0x1800a5b11  test    r8, r8
0x1800a5b14  jz      short loc_1800A5B26
0x1800a5b16  mov     rdx, [rbx+60h]; Src
0x1800a5b1a  lea     rcx, [r15+1Eh]
0x1800a5b1e  add     rcx, rsi; void *
0x1800a5b21  call    memcpy_0
0x1800a5b26  mov     ecx, [rbx+20h]
0x1800a5b29  lea     r9, [rsp+198h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800a5b2e  mov     r8d, [rbx+28h]
0x1800a5b32  add     ecx, r13d
0x1800a5b35  add     r8d, 1Eh
0x1800a5b39  xor     r13d, r13d
0x1800a5b3c  add     r8d, ecx; nNumberOfBytesToWrite
0x1800a5b3f  mov     [rsp+198h+lpOverlapped], r13; lpOverlapped
0x1800a5b44  mov     rcx, [rbp+0D8h]; hFile
0x1800a5b4b  mov     rdx, rsi; lpBuffer
0x1800a5b4e  call    cs:__imp_WriteFile
0x1800a5b55  nop     dword ptr [rax+rax+00h]
0x1800a5b5a  test    eax, eax
0x1800a5b5c  jz      short loc_1800A5BAC
0x1800a5b5e  mov     rcx, [rbx+20h]
0x1800a5b62  mov     rax, [rbx+28h]
0x1800a5b66  add     rcx, r14
0x1800a5b69  add     rax, 1Eh
0x1800a5b6d  add     rcx, rax
0x1800a5b70  mov     eax, [rsp+198h+NumberOfBytesWritten]
0x1800a5b74  cmp     rax, rcx
0x1800a5b77  jnz     short loc_1800A5BAC
0x1800a5b79  mov     rcx, rsi; Block
0x1800a5b7c  call    cs:__imp_free
0x1800a5b83  nop     dword ptr [rax+rax+00h]
0x1800a5b88  test    rdi, rdi
  ... truncated ...
```
