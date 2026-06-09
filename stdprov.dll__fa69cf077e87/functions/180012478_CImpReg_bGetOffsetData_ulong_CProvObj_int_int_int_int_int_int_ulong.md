# CImpReg::bGetOffsetData(ulong,CProvObj &,int &,int &,int &,int &,int &,int &,ulong)

- ea: `0x180012478`
- end: `0x180012671`
- name: `?bGetOffsetData@CImpReg@@QEAAHKAEAVCProvObj@@AEAH11111K@Z`
- size: `505`
- prototype: `_BOOL8 __fastcall(CImpReg *this, int, struct CProvObj *, int *, int *, int *, int *, int *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180011aa8`

## callees

- `0x180008fc0`
- `0x18000dd8c`
- `0x18000deb4`
- `0x18000dee8`
- `0x180012478`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180012526`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180012608`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180012526`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180012608`

## pseudocode

```c
_BOOL8 __fastcall CImpReg::bGetOffsetData(
        CImpReg *this,
        int a2,
        struct CProvObj *a3,
        int *a4,
        int *a5,
        int *a6,
        int *a7,
        int *a8,
        int *a9)
{
  int v9; // ebx
  int v10; // esi
  struct CToken *TokenPointer; // rax
  int v15; // r9d
  int v16; // eax
  int v17; // r9d
  const WCHAR *StringExp; // rbp
  int v19; // r9d
  int i; // ebx
  int IntExp; // eax
  int v22; // ebx
  int v23; // eax
  int v24; // ebx
  int v25; // r9d
  const WCHAR *v26; // rsi
  int j; // ebx
  int v28; // edx

  v9 = 4;
  v10 = *((_DWORD *)a3 + 2) - 1;
  if ( a2 != 8 )
    v9 = 2;
  TokenPointer = CProvObj::GetTokenPointer(a3, *((_DWORD *)a3 + 2) - 1);
  if ( TokenPointer )
    v16 = *((_DWORD *)TokenPointer + 12);
  else
    v16 = -1;
  if ( v16 >= v9 )
  {
    if ( a2 == 8 )
    {
      if ( CProvObj::IsExpString(a3, v10, 0) )
      {
        StringExp = CProvObj::sGetStringExp(a3, v10, 0);
        for ( i = 0; i < 13; ++i )
        {
          if ( StringExp && CompareStringW(0x7Fu, 1u, StringExp, -1, (PCNZWCH)(&cpIntTypes)[i], -1) == 2 )
            goto LABEL_16;
        }
        i = -1;
      }
      else
      {
        i = CProvObj::iGetIntExp(a3, v10, 0, v17);
      }
LABEL_16:
      *a4 = i;
      IntExp = CProvObj::iGetIntExp(a3, v10, 1, v19);
      *a5 = IntExp;
      if ( IntExp == -1 || *a4 == -1 )
        return 0;
      v22 = 2;
    }
    else
    {
      v22 = 0;
    }
    v23 = CProvObj::iGetIntExp(a3, v10, v22, v15);
    v24 = v22 + 1;
    *a6 = v23;
    *a8 = -1;
    *a9 = 0;
    if ( CProvObj::IsExpString(a3, v10, v24) )
    {
      v26 = CProvObj::sGetStringExp(a3, v10, v24);
      for ( j = 0; j < 18; ++j )
      {
        if ( v26 && CompareStringW(0x7Fu, 1u, v26, -1, (PCNZWCH)*(&Offsets + 3 * j), -1) == 2 )
        {
          v28 = dword_180021078[6 * j];
          *a8 = dword_18002107C[6 * j];
          *a9 = dword_180021080[6 * j];
          goto LABEL_29;
        }
      }
      v28 = -1;
    }
    else
    {
      v28 = CProvObj::iGetIntExp(a3, v10, v24, v25);
    }
LABEL_29:
    *a7 = v28;
    if ( *a6 != -1 )
      return v28 != -1;
  }
  return 0;
}

```

## disassembly

```asm
0x180012478  push    rbx
0x18001247a  push    rbp
0x18001247b  push    rsi
0x18001247c  push    rdi
0x18001247d  push    r12
0x18001247f  push    r14
0x180012481  push    r15
0x180012483  sub     rsp, 30h
0x180012487  mov     esi, [r8+8]
0x18001248b  mov     ebx, 4
0x180012490  dec     esi
0x180012492  mov     ebp, edx
0x180012494  cmp     edx, 8
0x180012497  mov     rcx, r8; this
0x18001249a  mov     edx, esi; int
0x18001249c  mov     r14, r9
0x18001249f  lea     eax, [rbx-2]
0x1800124a2  mov     rdi, r8
0x1800124a5  cmovnz  ebx, eax
0x1800124a8  call    ?GetTokenPointer@CProvObj@@AEAAPEAVCToken@@H@Z; CProvObj::GetTokenPointer(int)
0x1800124ad  or      r12d, 0FFFFFFFFh
0x1800124b1  test    rax, rax
0x1800124b4  jz      short loc_1800124BB
0x1800124b6  mov     eax, [rax+30h]
0x1800124b9  jmp     short loc_1800124BE
0x1800124bb  mov     eax, r12d
0x1800124be  cmp     eax, ebx
0x1800124c0  jl      loc_180012660
0x1800124c6  lea     r15, __ImageBase
0x1800124cd  cmp     ebp, 8
0x1800124d0  jnz     loc_180012577
0x1800124d6  xor     r8d, r8d; int
0x1800124d9  mov     edx, esi; int
0x1800124db  mov     rcx, rdi; this
0x1800124de  call    ?IsExpString@CProvObj@@QEAAHHH@Z; CProvObj::IsExpString(int,int)
0x1800124e3  xor     r8d, r8d; int
0x1800124e6  mov     edx, esi; int
0x1800124e8  mov     rcx, rdi; this
0x1800124eb  test    eax, eax
0x1800124ed  jz      short loc_18001253A
0x1800124ef  call    ?sGetStringExp@CProvObj@@QEAAPEBGHH@Z; CProvObj::sGetStringExp(int,int)
0x1800124f4  mov     rbp, rax
0x1800124f7  xor     ebx, ebx
0x1800124f9  cmp     ebx, 0Dh
0x1800124fc  jge     short loc_180012535
0x1800124fe  test    rbp, rbp
0x180012501  jz      short loc_180012531
0x180012503  mov     edx, 1; dwCmpFlags
0x180012508  movsxd  rax, ebx
0x18001250b  mov     [rsp+68h+cchCount2], r12d; cchCount2
0x180012510  mov     r9d, r12d; cchCount1
0x180012513  mov     r8, rbp; lpString1
0x180012516  mov     rax, ds:rva ?cpIntTypes@@3PAPEAGA[r15+rax*8]; ushort * near * cpIntTypes ...
0x18001251e  lea     ecx, [rdx+7Eh]; Locale
0x180012521  mov     [rsp+68h+lpString2], rax; lpString2
0x180012526  call    cs:__imp_CompareStringW
0x18001252c  cmp     eax, 2
0x18001252f  jz      short loc_180012541
0x180012531  inc     ebx
0x180012533  jmp     short loc_1800124F9
0x180012535  mov     ebx, r12d
0x180012538  jmp     short loc_180012541
0x18001253a  call    ?iGetIntExp@CProvObj@@QEAAJHHH@Z; CProvObj::iGetIntExp(int,int,int)
0x18001253f  mov     ebx, eax
0x180012541  mov     r8d, 1; int
0x180012547  mov     [r14], ebx
0x18001254a  mov     edx, esi; int
0x18001254c  mov     rcx, rdi; this
0x18001254f  call    ?iGetIntExp@CProvObj@@QEAAJHHH@Z; CProvObj::iGetIntExp(int,int,int)
0x180012554  mov     rcx, [rsp+68h+arg_20]
0x18001255c  mov     [rcx], eax
0x18001255e  cmp     eax, r12d
0x180012561  jz      loc_180012660
0x180012567  cmp     [r14], r12d
0x18001256a  jz      loc_180012660
0x180012570  mov     ebx, 2
0x180012575  jmp     short loc_180012579
0x180012577  xor     ebx, ebx
0x180012579  mov     r8d, ebx; int
0x18001257c  mov     edx, esi; int
0x18001257e  mov     rcx, rdi; this
0x180012581  call    ?iGetIntExp@CProvObj@@QEAAJHHH@Z; CProvObj::iGetIntExp(int,int,int)
0x180012586  mov     r14, [rsp+68h+arg_28]
0x18001258e  inc     ebx
0x180012590  mov     r15, [rsp+68h+arg_38]
0x180012598  mov     r8d, ebx; int
0x18001259b  mov     rbp, [rsp+68h+arg_40]
0x1800125a3  mov     edx, esi; int
0x1800125a5  mov     rcx, rdi; this
0x1800125a8  mov     [r14], eax
0x1800125ab  mov     [r15], r12d
0x1800125ae  mov     dword ptr [rbp+0], 0
0x1800125b5  call    ?IsExpString@CProvObj@@QEAAHHH@Z; CProvObj::IsExpString(int,int)
0x1800125ba  mov     r8d, ebx; int
0x1800125bd  mov     edx, esi; int
0x1800125bf  mov     rcx, rdi; this
0x1800125c2  test    eax, eax
0x1800125c4  jz      short loc_180012640
0x1800125c6  call    ?sGetStringExp@CProvObj@@QEAAPEBGHH@Z; CProvObj::sGetStringExp(int,int)
0x1800125cb  mov     rsi, rax
0x1800125ce  xor     ebx, ebx
0x1800125d0  cmp     ebx, 12h
0x1800125d3  jge     short loc_18001263B
0x1800125d5  test    rsi, rsi
0x1800125d8  jz      short loc_180012613
0x1800125da  movsxd  rcx, ebx
0x1800125dd  lea     rax, __ImageBase
0x1800125e4  mov     edx, 1; dwCmpFlags
0x1800125e9  mov     [rsp+68h+cchCount2], r12d; cchCount2
0x1800125ee  mov     r9d, r12d; cchCount1
0x1800125f1  mov     r8, rsi; lpString1
0x1800125f4  lea     rdi, [rcx+rcx*2]
0x1800125f8  mov     rax, rva ?Offsets@@3PAUUnionOffset@@A[rax+rdi*8]; UnionOffset near * Offsets ...
0x180012600  lea     ecx, [rdx+7Eh]; Locale
0x180012603  mov     [rsp+68h+lpString2], rax; lpString2
0x180012608  call    cs:__imp_CompareStringW
0x18001260e  cmp     eax, 2
0x180012611  jz      short loc_180012617
0x180012613  inc     ebx
0x180012615  jmp     short loc_1800125D0
0x180012617  lea     rcx, __ImageBase
0x18001261e  mov     eax, rva dword_18002107C[rcx+rdi*8]
0x180012625  mov     edx, rva dword_180021078[rcx+rdi*8]
0x18001262c  mov     [r15], eax
0x18001262f  mov     eax, rva dword_180021080[rcx+rdi*8]
0x180012636  mov     [rbp+0], eax
0x180012639  jmp     short loc_180012647
0x18001263b  mov     edx, r12d
0x18001263e  jmp     short loc_180012647
0x180012640  call    ?iGetIntExp@CProvObj@@QEAAJHHH@Z; CProvObj::iGetIntExp(int,int,int)
0x180012645  mov     edx, eax
0x180012647  mov     rcx, [rsp+68h+arg_30]
0x18001264f  mov     [rcx], edx
0x180012651  cmp     [r14], r12d
0x180012654  jz      short loc_180012660
0x180012656  xor     eax, eax
0x180012658  cmp     edx, r12d
0x18001265b  setnz   al
0x18001265e  jmp     short loc_180012662
0x180012660  xor     eax, eax
0x180012662  add     rsp, 30h
0x180012666  pop     r15
0x180012668  pop     r14
0x18001266a  pop     r12
0x18001266c  pop     rdi
0x18001266d  pop     rsi
0x18001266e  pop     rbp
0x18001266f  pop     rbx
0x180012670  retn
```
