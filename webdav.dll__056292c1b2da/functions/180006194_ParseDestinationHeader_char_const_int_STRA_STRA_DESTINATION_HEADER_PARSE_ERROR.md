# ParseDestinationHeader(char const *,int *,STRA *,STRA *,DESTINATION_HEADER_PARSE_ERROR *)

- ea: `0x180006194`
- end: `0x180006308`
- name: `?ParseDestinationHeader@@YAJPEBDPEAHPEAVSTRA@@2PEAW4DESTINATION_HEADER_PARSE_ERROR@@@Z`
- size: `372`
- prototype: `int __fastcall(const char *, int *, struct STRA *, struct STRA *, enum DESTINATION_HEADER_PARSE_ERROR *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006ec8`
- `0x18000a9c4`

## callees

- `0x180005dec`
- `0x180006194`

## import_xrefs

- `msvcrt!strchr` at `0x1800062a7`
- `msvcrt!strchr` at `0x1800062a7`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x1800062d0`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x1800062d0`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800061ee`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800062bb`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800061ee`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800062bb`

## pseudocode

```c
int __fastcall ParseDestinationHeader(
        const char *a1,
        int *a2,
        struct STRA *a3,
        struct STRA *a4,
        enum DESTINATION_HEADER_PARSE_ERROR *a5)
{
  _BYTE *v7; // rax
  const char *v8; // r10
  const char *v9; // rdx
  int result; // eax
  char v11; // al
  const char *v12; // rbx
  int v13; // eax
  char *v14; // rax
  const char *v15; // rdi

  **((_BYTE **)a3 + 4) = 0;
  *((_DWORD *)a3 + 12) = 0;
  v7 = (_BYTE *)*((_QWORD *)a4 + 4);
  *(_DWORD *)a5 = 0;
  *v7 = 0;
  *((_DWORD *)a4 + 12) = 0;
  if ( *a1 == 47 )
  {
    if ( (unsigned int)IsValidUriStem(a1) )
    {
      v9 = v8;
      return STRA::Copy(a4, v9);
    }
LABEL_5:
    *(_DWORD *)a5 = 1;
    return -2147024809;
  }
  if ( ((*a1 - 72) & 0xDF) != 0
    || ((a1[1] - 84) & 0xDF) != 0
    || ((a1[2] - 84) & 0xDF) != 0
    || ((a1[3] - 80) & 0xDF) != 0 )
  {
    goto LABEL_29;
  }
  v11 = a1[4];
  if ( v11 == 58 )
  {
    if ( a1[5] == 47 && a1[6] == 47 )
    {
      v12 = a1 + 7;
      if ( a1[7] )
      {
        v13 = 0;
        goto LABEL_21;
      }
    }
LABEL_29:
    *(_DWORD *)a5 = 2;
    return -2147024809;
  }
  if ( ((v11 - 83) & 0xDF) != 0 )
    goto LABEL_29;
  if ( a1[5] != 58 )
    goto LABEL_29;
  if ( a1[6] != 47 )
    goto LABEL_29;
  if ( a1[7] != 47 )
    goto LABEL_29;
  v12 = a1 + 8;
  if ( !a1[8] )
    goto LABEL_29;
  v13 = 1;
LABEL_21:
  *a2 = v13;
  if ( *v12 == 47 )
  {
    *(_DWORD *)a5 = 3;
    return -2147024809;
  }
  v14 = strchr(v12, 47);
  v15 = v14;
  if ( v14 )
  {
    result = STRA::Copy(a3, v12, (_DWORD)v14 - (_DWORD)v12);
  }
  else
  {
    result = STRA::Copy(a3, v12);
    v15 = "/";
  }
  if ( result >= 0 )
  {
    if ( (unsigned int)IsValidUriStem(v15) )
    {
      v9 = v15;
      return STRA::Copy(a4, v9);
    }
    goto LABEL_5;
  }
  return result;
}

```

## disassembly

```asm
0x180006194  push    rbx
0x180006196  push    rbp
0x180006197  push    rsi
0x180006198  push    rdi
0x180006199  push    r14
0x18000619b  sub     rsp, 20h
0x18000619f  mov     rax, [r8+20h]
0x1800061a3  mov     r10, rcx
0x1800061a6  mov     rsi, [rsp+48h+arg_20]
0x1800061ab  mov     rbp, r9
0x1800061ae  mov     r14, r8
0x1800061b1  mov     byte ptr [rax], 0
0x1800061b4  mov     dword ptr [r8+30h], 0
0x1800061bc  mov     rax, [r9+20h]
0x1800061c0  mov     dword ptr [rsi], 0
0x1800061c6  mov     byte ptr [rax], 0
0x1800061c9  mov     dword ptr [r9+30h], 0
0x1800061d1  mov     al, [rcx]
0x1800061d3  mov     ecx, 2Fh ; '/'
0x1800061d8  cmp     al, cl
0x1800061da  jnz     short loc_180006204
0x1800061dc  mov     rcx, r10; char *
0x1800061df  call    ?IsValidUriStem@@YAHPEBD@Z; IsValidUriStem(char const *)
0x1800061e4  test    eax, eax
0x1800061e6  jz      short loc_1800061F9
0x1800061e8  mov     rdx, r10
0x1800061eb  mov     rcx, rbp
0x1800061ee  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x1800061f4  jmp     loc_1800062FD
0x1800061f9  mov     dword ptr [rsi], 1
0x1800061ff  jmp     loc_1800062F8
0x180006204  sub     al, 48h ; 'H'
0x180006206  mov     r8b, 0DFh
0x180006209  test    r8b, al
0x18000620c  jnz     loc_1800062F2
0x180006212  mov     al, [r10+1]
0x180006216  sub     al, 54h ; 'T'
0x180006218  test    r8b, al
0x18000621b  jnz     loc_1800062F2
0x180006221  mov     al, [r10+2]
0x180006225  sub     al, 54h ; 'T'
0x180006227  test    r8b, al
0x18000622a  jnz     loc_1800062F2
0x180006230  mov     al, [r10+3]
0x180006234  sub     al, 50h ; 'P'
0x180006236  test    r8b, al
0x180006239  jnz     loc_1800062F2
0x18000623f  mov     al, [r10+4]
0x180006243  cmp     al, 3Ah ; ':'
0x180006245  jnz     short loc_18000626C
0x180006247  cmp     [r10+5], cl
0x18000624b  jnz     loc_1800062F2
0x180006251  cmp     [r10+6], cl
0x180006255  jnz     loc_1800062F2
0x18000625b  lea     rbx, [r10+7]
0x18000625f  cmp     byte ptr [rbx], 0
0x180006262  jz      loc_1800062F2
0x180006268  xor     eax, eax
0x18000626a  jmp     short loc_180006294
0x18000626c  sub     al, 53h ; 'S'
0x18000626e  test    r8b, al
0x180006271  jnz     short loc_1800062F2
0x180006273  cmp     byte ptr [r10+5], 3Ah ; ':'
0x180006278  jnz     short loc_1800062F2
0x18000627a  cmp     [r10+6], cl
0x18000627e  jnz     short loc_1800062F2
0x180006280  cmp     [r10+7], cl
0x180006284  jnz     short loc_1800062F2
0x180006286  lea     rbx, [r10+8]
0x18000628a  cmp     byte ptr [rbx], 0
0x18000628d  jz      short loc_1800062F2
0x18000628f  mov     eax, 1
0x180006294  mov     [rdx], eax
0x180006296  cmp     [rbx], cl
0x180006298  jnz     short loc_1800062A2
0x18000629a  mov     dword ptr [rsi], 3
0x1800062a0  jmp     short loc_1800062F8
0x1800062a2  mov     edx, ecx; Val
0x1800062a4  mov     rcx, rbx; Str
0x1800062a7  call    cs:__imp_strchr
0x1800062ad  mov     rdx, rbx
0x1800062b0  mov     rcx, r14
0x1800062b3  mov     rdi, rax
0x1800062b6  test    rax, rax
0x1800062b9  jnz     short loc_1800062CA
0x1800062bb  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x1800062c1  lea     rdi, asc_1800266F4; "/"
0x1800062c8  jmp     short loc_1800062D6
0x1800062ca  mov     r8d, eax
0x1800062cd  sub     r8d, ebx
0x1800062d0  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x1800062d6  test    eax, eax
0x1800062d8  js      short loc_1800062FD
0x1800062da  mov     rcx, rdi; char *
0x1800062dd  call    ?IsValidUriStem@@YAHPEBD@Z; IsValidUriStem(char const *)
0x1800062e2  test    eax, eax
0x1800062e4  jz      loc_1800061F9
0x1800062ea  mov     rdx, rdi
0x1800062ed  jmp     loc_1800061EB
0x1800062f2  mov     dword ptr [rsi], 2
0x1800062f8  mov     eax, 80070057h
0x1800062fd  add     rsp, 20h
0x180006301  pop     r14
0x180006303  pop     rdi
0x180006304  pop     rsi
0x180006305  pop     rbp
0x180006306  pop     rbx
0x180006307  retn
```
