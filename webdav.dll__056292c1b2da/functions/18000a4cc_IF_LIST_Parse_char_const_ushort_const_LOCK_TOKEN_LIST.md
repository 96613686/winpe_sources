# IF_LIST::Parse(char const * *,ushort const *,LOCK_TOKEN_LIST *)

- ea: `0x18000a4cc`
- end: `0x18000a7cc`
- name: `?Parse@IF_LIST@@QEAAJPEAPEBDPEBGPEAVLOCK_TOKEN_LIST@@@Z`
- size: `768`
- prototype: `int(IF_LIST *__hidden this, const char **, const unsigned __int16 *, struct LOCK_TOKEN_LIST *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18000a7d4`

## callees

- `0x1800011d4`
- `0x180001214`
- `0x1800043b0`
- `0x180004808`
- `0x18000a4cc`
- `0x18001c3c8`
- `0x180022520`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a51b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a600`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a72c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a51b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a600`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a72c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000a50e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000a5ec`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000a701`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000a50e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000a5ec`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000a701`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a62c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a760`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a7a4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a62c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a760`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a7a4`
- `iisutil!?CopyA@STRU@@QEAAJPEBDK@Z` at `0x18000a6d7`
- `iisutil!?CopyA@STRU@@QEAAJPEBDK@Z` at `0x18000a6d7`

## pseudocode

```c
__int64 __fastcall IF_LIST::Parse(IF_LIST *this, char **a2, const unsigned __int16 *a3, struct LOCK_TOKEN_LIST *a4)
{
  char *v4; // rdi
  IF_LIST *v5; // r13
  struct LOCK_TOKEN_LIST *v6; // r12
  int AngleBracketString; // ebx
  char *v10; // rdi
  char v11; // al
  int v12; // r13d
  char v13; // al
  int v14; // r8d
  unsigned __int16 *v15; // rbx
  _QWORD *v16; // rax
  _QWORD *v17; // rdi
  int v18; // r12d
  _BYTE *v19; // rdx
  __int64 v20; // rax
  char *i; // rsi
  char v22; // al
  char *v23; // rax
  _DWORD *v24; // rsi
  unsigned __int16 *v25; // rdx
  char *v27; // [rsp+20h] [rbp-49h] BYREF
  IF_LIST *v28; // [rsp+28h] [rbp-41h]
  struct LOCK_TOKEN_LIST *v29; // [rsp+30h] [rbp-39h]
  _BYTE v30[32]; // [rsp+38h] [rbp-31h] BYREF
  unsigned __int16 *v31; // [rsp+58h] [rbp-11h]

  v4 = *a2;
  v5 = this;
  v28 = this;
  v6 = a4;
  v29 = a4;
  STRU::STRU((STRU *)v30);
  AngleBracketString = STRU::Copy((IF_LIST *)((char *)v5 + 24), a3);
  if ( AngleBracketString < 0 )
    goto LABEL_59;
  v10 = v4 + 1;
  while ( 1 )
  {
    while ( 1 )
    {
      v11 = *v10;
      if ( !*v10 || v11 != 32 && v11 != 9 )
        break;
      ++v10;
    }
    v27 = v10;
    if ( !v11 )
    {
LABEL_57:
      AngleBracketString = -2147024809;
      goto LABEL_58;
    }
    if ( *v10 == 41 )
    {
      *a2 = v10 + 1;
      goto LABEL_54;
    }
    v12 = 0;
    if ( *v10 == 78 && v10[1] == 111 && v10[2] == 116 )
    {
      for ( v10 += 3; ; ++v10 )
      {
        v13 = *v10;
        if ( !*v10 || v13 != 32 && v13 != 9 )
          break;
      }
      v27 = v10;
      if ( !v13 )
        goto LABEL_57;
      v12 = 1;
    }
    if ( *v10 == 60 )
    {
      AngleBracketString = GetAngleBracketString((const char **)&v27, 0, (struct STRU *)v30);
      if ( AngleBracketString < 0 )
        goto LABEL_48;
      v15 = v31;
      if ( !STATIC_WSTRING_HASH::FindKey(v6, v31, v14) )
      {
        v16 = operator new(0x50u);
        v17 = v16;
        if ( v16 )
        {
          STRU::STRU((STRU *)(v16 + 3));
          *v17 = 0;
          AngleBracketString = STRU::Copy((STRU *)(v17 + 3), v15);
          if ( AngleBracketString < 0 )
          {
            STRU::~STRU((STRU *)(v17 + 3));
            operator delete(v17);
          }
          else
          {
            *v17 = v17[7];
            STATIC_WSTRING_HASH::InsertRecord(v6, (struct STATIC_WSTRING_HASH_RECORD *)v17);
            ++*((_DWORD *)v6 + 264);
          }
        }
        else
        {
          AngleBracketString = -2147024882;
        }
        if ( AngleBracketString < 0 )
        {
LABEL_48:
          *a2 = v27;
          goto LABEL_59;
        }
      }
      v10 = v27;
      v18 = 0;
      goto LABEL_45;
    }
    if ( *v10 != 91 )
      goto LABEL_57;
    v19 = v10 + 1;
    if ( v10[1] == 87 )
    {
      if ( v10[2] != 47 || v10[3] != 34 )
        break;
      v20 = 3;
      v18 = 2;
    }
    else
    {
      if ( *v19 != 34 )
        break;
      v20 = 1;
      v18 = 1;
    }
    for ( i = &v19[v20]; ; ++i )
    {
      v22 = *i;
      if ( !*i || v22 == 34 || !v22 )
        break;
    }
    if ( *i != 34 || i[1] != 93 )
      break;
    AngleBracketString = STRU::CopyA((STRU *)v30, v10 + 1, (_DWORD)i - (_DWORD)v10);
    if ( AngleBracketString < 0 )
      goto LABEL_52;
    v10 = i + 2;
LABEL_45:
    v23 = (char *)operator new(0x48u);
    v24 = v23;
    if ( !v23 )
    {
      AngleBracketString = -2147024882;
LABEL_58:
      *a2 = v10;
      goto LABEL_59;
    }
    STRU::STRU((STRU *)(v23 + 16));
    v24[2] = 0;
    v24[3] = -1;
    *(_QWORD *)v24 = 0;
    v25 = v31;
    v24[2] = v12;
    v24[3] = v18;
    AngleBracketString = STRU::Copy((STRU *)(v24 + 4), v25);
    if ( AngleBracketString < 0 )
    {
      *a2 = v10;
      STRU::~STRU((STRU *)(v24 + 4));
      operator delete(v24);
      goto LABEL_59;
    }
    v5 = v28;
    v6 = v29;
    **((_QWORD **)v28 + 2) = v24;
    *((_QWORD *)v5 + 2) = v24;
  }
  AngleBracketString = -2147024809;
LABEL_52:
  v5 = v28;
  *a2 = v10;
LABEL_54:
  if ( AngleBracketString >= 0 && !*((_QWORD *)v5 + 1) )
    AngleBracketString = -2147024809;
LABEL_59:
  STRU::~STRU((STRU *)v30);
  return (unsigned int)AngleBracketString;
}

```

## disassembly

```asm
0x18000a4cc  push    rbp
0x18000a4ce  push    rbx
0x18000a4cf  push    rsi
0x18000a4d0  push    rdi
0x18000a4d1  push    r12
0x18000a4d3  push    r13
0x18000a4d5  push    r14
0x18000a4d7  push    r15
0x18000a4d9  lea     rbp, [rsp-1Fh]
0x18000a4de  sub     rsp, 88h
0x18000a4e5  mov     rax, cs:__security_cookie
0x18000a4ec  xor     rax, rsp
0x18000a4ef  mov     [rbp+57h+var_50], rax
0x18000a4f3  mov     rdi, [rdx]
0x18000a4f6  mov     r13, rcx
0x18000a4f9  mov     [rbp+57h+var_98], rcx
0x18000a4fd  mov     r12, r9
0x18000a500  lea     rcx, [rbp+57h+var_88]
0x18000a504  mov     [rbp+57h+var_90], r9
0x18000a508  mov     rbx, r8
0x18000a50b  mov     r15, rdx
0x18000a50e  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000a514  lea     rcx, [r13+18h]
0x18000a518  mov     rdx, rbx
0x18000a51b  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000a521  mov     ebx, eax
0x18000a523  test    eax, eax
0x18000a525  js      loc_18000A7A0
0x18000a52b  inc     rdi
0x18000a52e  mov     r14d, 80070057h
0x18000a534  jmp     short loc_18000A541
0x18000a536  cmp     al, 20h ; ' '
0x18000a538  jz      short loc_18000A53E
0x18000a53a  cmp     al, 9
0x18000a53c  jnz     short loc_18000A547
0x18000a53e  inc     rdi
0x18000a541  mov     al, [rdi]
0x18000a543  test    al, al
0x18000a545  jnz     short loc_18000A536
0x18000a547  mov     [rbp+57h+var_A0], rdi
0x18000a54b  test    al, al
0x18000a54d  jz      loc_18000A79A
0x18000a553  cmp     byte ptr [rdi], 29h ; ')'
0x18000a556  mov     r14d, 80070057h
0x18000a55c  jz      loc_18000A783
0x18000a562  xor     r13d, r13d
0x18000a565  cmp     byte ptr [rdi], 4Eh ; 'N'
0x18000a568  jnz     short loc_18000A59F
0x18000a56a  cmp     byte ptr [rdi+1], 6Fh ; 'o'
0x18000a56e  jnz     short loc_18000A59F
0x18000a570  cmp     byte ptr [rdi+2], 74h ; 't'
0x18000a574  jnz     short loc_18000A59F
0x18000a576  add     rdi, 3
0x18000a57a  jmp     short loc_18000A587
0x18000a57c  cmp     al, 20h ; ' '
0x18000a57e  jz      short loc_18000A584
0x18000a580  cmp     al, 9
0x18000a582  jnz     short loc_18000A58D
0x18000a584  inc     rdi
0x18000a587  mov     al, [rdi]
0x18000a589  test    al, al
0x18000a58b  jnz     short loc_18000A57C
0x18000a58d  mov     [rbp+57h+var_A0], rdi
0x18000a591  test    al, al
0x18000a593  jz      loc_18000A79A
0x18000a599  mov     r13d, 1
0x18000a59f  cmp     byte ptr [rdi], 3Ch ; '<'
0x18000a5a2  mov     rax, rdi
0x18000a5a5  jnz     loc_18000A655
0x18000a5ab  lea     r8, [rbp+57h+var_88]; struct STRU *
0x18000a5af  xor     edx, edx; struct STRA *
0x18000a5b1  lea     rcx, [rbp+57h+var_A0]; char **
0x18000a5b5  call    ?GetAngleBracketString@@YAJPEAPEBDPEAVSTRA@@PEAVSTRU@@@Z; GetAngleBracketString(char const * *,STRA *,STRU *)
0x18000a5ba  mov     ebx, eax
0x18000a5bc  test    eax, eax
0x18000a5be  js      loc_18000A750
0x18000a5c4  mov     rbx, [rbp+57h+var_68]
0x18000a5c8  mov     rcx, r12; this
0x18000a5cb  mov     rdx, rbx; unsigned __int16 *
0x18000a5ce  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x18000a5d3  test    rax, rax
0x18000a5d6  jnz     short loc_18000A649
0x18000a5d8  lea     ecx, [rax+50h]; Size
0x18000a5db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a5e0  mov     rdi, rax
0x18000a5e3  test    rax, rax
0x18000a5e6  jz      short loc_18000A63C
0x18000a5e8  lea     rcx, [rax+18h]
0x18000a5ec  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000a5f2  mov     rdx, rbx
0x18000a5f5  mov     qword ptr [rdi], 0
0x18000a5fc  lea     rcx, [rdi+18h]
0x18000a600  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000a606  mov     ebx, eax
0x18000a608  test    eax, eax
0x18000a60a  js      short loc_18000A628
0x18000a60c  mov     rax, [rdi+38h]
0x18000a610  mov     rdx, rdi; struct STATIC_WSTRING_HASH_RECORD *
0x18000a613  mov     rcx, r12; this
0x18000a616  mov     [rdi], rax
0x18000a619  call    ?InsertRecord@STATIC_WSTRING_HASH@@QEAAXPEAUSTATIC_WSTRING_HASH_RECORD@@@Z; STATIC_WSTRING_HASH::InsertRecord(STATIC_WSTRING_HASH_RECORD *)
0x18000a61e  inc     dword ptr [r12+420h]
0x18000a626  jmp     short loc_18000A641
0x18000a628  lea     rcx, [rdi+18h]
0x18000a62c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000a632  mov     rcx, rdi; Block
0x18000a635  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a63a  jmp     short loc_18000A641
0x18000a63c  mov     ebx, 8007000Eh
0x18000a641  test    ebx, ebx
0x18000a643  js      loc_18000A750
0x18000a649  mov     rdi, [rbp+57h+var_A0]
0x18000a64d  xor     r12d, r12d
0x18000a650  jmp     loc_18000A6EB
0x18000a655  cmp     byte ptr [rdi], 5Bh ; '['
0x18000a658  jnz     loc_18000A79A
0x18000a65e  cmp     byte ptr [rax], 5Bh ; '['
0x18000a661  jnz     loc_18000A777
0x18000a667  lea     rdx, [rax+1]
0x18000a66b  cmp     byte ptr [rdx], 57h ; 'W'
0x18000a66e  jnz     short loc_18000A68F
0x18000a670  cmp     byte ptr [rdx+1], 2Fh ; '/'
0x18000a674  jnz     loc_18000A777
0x18000a67a  cmp     byte ptr [rdx+2], 22h ; '"'
0x18000a67e  jnz     loc_18000A777
0x18000a684  mov     eax, 3
0x18000a689  lea     r12d, [rax-1]
0x18000a68d  jmp     short loc_18000A6A0
0x18000a68f  cmp     byte ptr [rdx], 22h ; '"'
0x18000a692  jnz     loc_18000A777
0x18000a698  mov     eax, 1
0x18000a69d  mov     r12d, eax
0x18000a6a0  lea     rsi, [rdx+rax]
0x18000a6a4  jmp     short loc_18000A6B1
0x18000a6a6  cmp     al, 22h ; '"'
0x18000a6a8  jz      short loc_18000A6B7
0x18000a6aa  test    al, al
0x18000a6ac  jz      short loc_18000A6B7
0x18000a6ae  inc     rsi
0x18000a6b1  mov     al, [rsi]
0x18000a6b3  test    al, al
0x18000a6b5  jnz     short loc_18000A6A6
0x18000a6b7  cmp     byte ptr [rsi], 22h ; '"'
0x18000a6ba  jnz     loc_18000A777
0x18000a6c0  cmp     byte ptr [rsi+1], 5Dh ; ']'
0x18000a6c4  jnz     loc_18000A777
0x18000a6ca  mov     r8d, esi
0x18000a6cd  lea     rcx, [rbp+57h+var_88]
0x18000a6d1  sub     r8d, edx
0x18000a6d4  inc     r8d
0x18000a6d7  call    cs:__imp_?CopyA@STRU@@QEAAJPEBDK@Z; STRU::CopyA(char const *,ulong)
0x18000a6dd  mov     ebx, eax
0x18000a6df  test    eax, eax
0x18000a6e1  js      loc_18000A77A
0x18000a6e7  lea     rdi, [rsi+2]
0x18000a6eb  mov     ecx, 48h ; 'H'; Size
0x18000a6f0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a6f5  mov     rsi, rax
0x18000a6f8  test    rax, rax
0x18000a6fb  jz      short loc_18000A770
0x18000a6fd  lea     rcx, [rax+10h]
0x18000a701  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000a707  mov     dword ptr [rsi+8], 0
0x18000a70e  lea     rcx, [rsi+10h]
0x18000a712  mov     dword ptr [rsi+0Ch], 0FFFFFFFFh
0x18000a719  mov     qword ptr [rsi], 0
0x18000a720  mov     rdx, [rbp+57h+var_68]
0x18000a724  mov     [rsi+8], r13d
0x18000a728  mov     [rsi+0Ch], r12d
0x18000a72c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000a732  mov     ebx, eax
0x18000a734  test    eax, eax
0x18000a736  js      short loc_18000A759
0x18000a738  mov     r13, [rbp+57h+var_98]
0x18000a73c  mov     r12, [rbp+57h+var_90]
0x18000a740  mov     rax, [r13+10h]
0x18000a744  mov     [rax], rsi
0x18000a747  mov     [r13+10h], rsi
0x18000a74b  jmp     loc_18000A541
0x18000a750  mov     rax, [rbp+57h+var_A0]
0x18000a754  mov     [r15], rax
0x18000a757  jmp     short loc_18000A7A0
0x18000a759  lea     rcx, [rsi+10h]
0x18000a75d  mov     [r15], rdi
0x18000a760  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000a766  mov     rcx, rsi; Block
0x18000a769  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a76e  jmp     short loc_18000A7A0
0x18000a770  mov     ebx, 8007000Eh
0x18000a775  jmp     short loc_18000A79D
0x18000a777  mov     ebx, r14d
0x18000a77a  mov     r13, [rbp+57h+var_98]
0x18000a77e  mov     [r15], rdi
0x18000a781  jmp     short loc_18000A78A
0x18000a783  lea     rax, [rdi+1]
0x18000a787  mov     [r15], rax
0x18000a78a  test    ebx, ebx
0x18000a78c  js      short loc_18000A7A0
0x18000a78e  cmp     qword ptr [r13+8], 0
0x18000a793  jnz     short loc_18000A7A0
0x18000a795  mov     ebx, r14d
0x18000a798  jmp     short loc_18000A7A0
0x18000a79a  mov     ebx, r14d
0x18000a79d  mov     [r15], rdi
0x18000a7a0  lea     rcx, [rbp+57h+var_88]
0x18000a7a4  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000a7aa  mov     eax, ebx
0x18000a7ac  mov     rcx, [rbp+57h+var_50]
0x18000a7b0  xor     rcx, rsp; StackCookie
0x18000a7b3  call    __security_check_cookie
0x18000a7b8  add     rsp, 88h
0x18000a7bf  pop     r15
0x18000a7c1  pop     r14
0x18000a7c3  pop     r13
0x18000a7c5  pop     r12
0x18000a7c7  pop     rdi
0x18000a7c8  pop     rsi
0x18000a7c9  pop     rbx
0x18000a7ca  pop     rbp
0x18000a7cb  retn
```
