# CToken::CToken(ushort const *,ushort,bool)

- ea: `0x1800020c0`
- end: `0x180002766`
- name: `??0CToken@@QEAA@PEBGG_N@Z`
- size: `1702`
- prototype: `CToken *__fastcall(CToken *this, const unsigned __int16 *, __int16, char)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180001490`
- `0x180001590`
- `0x180001640`

## callees

- `0x1800020c0`
- `0x180002e10`
- `0x1800086b0`
- `0x1800087f0`
- `0x18000b458`
- `0x180015680`

## import_xrefs

- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x180002140`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x180002140`
- `wbemcomn!?InsertAt@CFlexArray@@QEAAHHPEAX@Z` at `0x180002699`
- `wbemcomn!?InsertAt@CFlexArray@@QEAAHHPEAX@Z` at `0x180002699`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000221b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180002274`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000221b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180002274`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180002254`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800022b0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800023d0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180002490`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180002520`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180002652`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180002254`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800022b0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800023d0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180002490`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180002520`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180002652`

## pseudocode

```c
CToken *__fastcall CToken::CToken(CToken *this, const unsigned __int16 *a2, __int16 a3, char a4)
{
  _WORD *v8; // rcx
  char *v9; // r15
  char v10; // cl
  const unsigned __int16 *v11; // rdi
  unsigned __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  unsigned __int16 *v17; // rax
  unsigned __int16 v18; // r8
  unsigned __int16 *v19; // rcx
  char *v20; // rcx
  __int64 v21; // rax
  int v22; // ebx
  unsigned __int16 *v23; // rax
  char *v24; // rcx
  __int64 v25; // rax
  int v26; // ebx
  unsigned __int16 *v27; // rax
  int *v29; // r15
  int v30; // r13d
  const unsigned __int16 *v31; // rax
  unsigned __int16 v32; // r12
  unsigned __int16 *v33; // rdi
  __int64 v34; // rcx
  unsigned __int64 v35; // rbp
  __int64 v36; // rax
  unsigned __int16 *v37; // rax
  const unsigned __int16 *v38; // rax
  unsigned __int16 v39; // r12
  unsigned __int16 *v40; // rdi
  __int64 v41; // rcx
  unsigned __int64 v42; // rbp
  __int64 v43; // rax
  unsigned __int16 *v44; // rax
  __int64 v45; // rcx
  __int64 v46; // rax
  unsigned __int16 *v47; // rax
  unsigned __int16 *v48; // r8
  char *v49; // rax
  void *v50; // r13
  int v51; // ecx
  int v52; // [rsp+20h] [rbp-1B8h]
  int v53; // [rsp+24h] [rbp-1B4h]
  const unsigned __int16 *v54; // [rsp+28h] [rbp-1B0h]
  int v55; // [rsp+30h] [rbp-1A8h]
  TString *v56; // [rsp+38h] [rbp-1A0h]
  unsigned __int16 v57[2]; // [rsp+40h] [rbp-198h] BYREF
  _WORD v58[2]; // [rsp+44h] [rbp-194h] BYREF
  unsigned __int16 v59[4]; // [rsp+48h] [rbp-190h] BYREF
  CToken *v60; // [rsp+50h] [rbp-188h]
  char *v61; // [rsp+58h] [rbp-180h]
  unsigned __int16 v62[152]; // [rsp+60h] [rbp-178h] BYREF

  v60 = this;
  *(_QWORD *)this = &CObject::`vftable';
  *(_QWORD *)this = &CToken::`vftable';
  v8 = (_WORD *)((char *)this + 24);
  *v8 = 0;
  *((_QWORD *)this + 2) = v8;
  *((_DWORD *)this + 7) = 0;
  v9 = (char *)this + 40;
  *((_WORD *)this + 20) = 0;
  *((_QWORD *)this + 4) = (char *)this + 40;
  *((_DWORD *)this + 11) = 0;
  CFlexArray::CFlexArray((CToken *)((char *)this + 48), 8, 100);
  *((_DWORD *)this + 2) = -1;
  v10 = 0;
  v11 = a2;
  v12 = *a2;
  if ( (_WORD)v12 )
  {
    v13 = 0x1000000000000041LL;
    do
    {
      if ( (_WORD)v12 == a3 )
        break;
      LOWORD(v12) = v12 - 34;
      if ( (unsigned __int16)v12 <= 0x3Cu && _bittest64(&v13, v12) )
        v10 = 1;
      v12 = *++v11;
    }
    while ( (_WORD)v12 );
  }
  if ( a4 && a3 == 124 && *v11 != 124 && v10
    || (v14 = v11 - a2, *((_DWORD *)this + 2) = v14, v15 = 150, (int)v14 >= 150) )
  {
    v29 = 0;
    v56 = 0;
    v55 = 0;
    v53 = 0;
    v52 = 0;
    v30 = 0;
    v31 = a2;
    v54 = a2;
    while ( 1 )
    {
      v32 = *v31;
      if ( !*v31 )
      {
LABEL_76:
        if ( !v53 && !v52 )
          *((_DWORD *)this + 2) = v31 - a2;
        return this;
      }
      if ( v32 == a3 && !v30 )
      {
        ++v31;
        goto LABEL_76;
      }
      v33 = (unsigned __int16 *)*((_QWORD *)this + 4);
      if ( v33 )
      {
        v34 = -1;
        do
          ++v34;
        while ( v33[v34] );
      }
      else
      {
        v34 = 0;
      }
      v35 = *((int *)this + 11);
      if ( v34 + 2 > v35 )
      {
        v36 = -1;
        do
          ++v36;
        while ( v33[v36] );
        LODWORD(v35) = v36 + 32;
        v37 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((int)v36 + 32, 2u));
        v33 = v37;
        if ( !v37 )
        {
          v29 = (int *)v56;
          goto LABEL_47;
        }
        StringCchCopyW(v37, (int)v35, *((const unsigned __int16 **)this + 4));
        TString::Empty((CToken *)((char *)this + 32));
        *((_QWORD *)this + 4) = v33;
        *((_DWORD *)this + 11) = v35;
        v29 = (int *)v56;
      }
      v57[0] = v32;
      v57[1] = 0;
      StringCchCatW(v33, (int)v35, v57);
LABEL_47:
      v38 = v54;
      v39 = *v54;
      if ( *v54 != 94 )
      {
        switch ( v39 )
        {
          case '(':
            if ( v52 )
              goto LABEL_53;
            if ( v30 )
              goto LABEL_64;
            break;
          case ',':
            if ( !v52 )
              goto LABEL_64;
            if ( v30 )
              goto LABEL_53;
            break;
          case ')':
            if ( !v52 )
              goto LABEL_64;
            if ( v53 || v30 )
              goto LABEL_53;
            v52 = 0;
            goto LABEL_61;
          case '"':
            if ( !v52 )
              goto LABEL_64;
            if ( !v30 )
            {
              v51 = v55 + 1;
              v55 = v51;
              if ( v51 == 1 )
              {
                v53 = 1;
                TString::operator+=((TString *)v29);
                goto LABEL_60;
              }
              if ( v51 != 2 )
                return this;
              v53 = 0;
              goto LABEL_61;
            }
LABEL_53:
            v40 = *(unsigned __int16 **)v29;
            if ( *(_QWORD *)v29 )
            {
              v41 = -1;
              do
                ++v41;
              while ( v40[v41] );
            }
            else
            {
              v41 = 0;
            }
            v42 = v29[3];
            if ( v41 + 2 > v42 )
            {
              v43 = -1;
              do
                ++v43;
              while ( v40[v43] );
              LODWORD(v42) = v43 + 32;
              v44 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((int)v43 + 32, 2u));
              v40 = v44;
              if ( !v44 )
                goto LABEL_60;
              StringCchCopyW(v44, (int)v42, *(const unsigned __int16 **)v56);
              TString::Empty(v56);
              *(_QWORD *)v56 = v40;
              *((_DWORD *)v56 + 3) = v42;
            }
            v58[0] = v39;
            v58[1] = 0;
            v48 = v58;
            goto LABEL_73;
          default:
LABEL_52:
            if ( v52 )
              goto LABEL_53;
LABEL_64:
            v40 = (unsigned __int16 *)*((_QWORD *)this + 2);
            if ( v40 )
            {
              v45 = -1;
              do
                ++v45;
              while ( v40[v45] );
            }
            else
            {
              v45 = 0;
            }
            v42 = *((int *)this + 7);
            if ( v45 + 2 > v42 )
            {
              v46 = -1;
              do
                ++v46;
              while ( v40[v46] );
              LODWORD(v42) = v46 + 32;
              v47 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((int)v46 + 32, 2u));
              v40 = v47;
              if ( v47 )
              {
                StringCchCopyW(v47, (int)v42, *((const unsigned __int16 **)this + 2));
                TString::Empty((CToken *)((char *)this + 16));
                *((_QWORD *)this + 2) = v40;
                *((_DWORD *)this + 7) = v42;
                goto LABEL_72;
              }
LABEL_60:
              v38 = v54;
LABEL_61:
              v30 = 0;
              goto LABEL_62;
            }
LABEL_72:
            v59[0] = v39;
            v59[1] = 0;
            v48 = v59;
LABEL_73:
            StringCchCatW(v40, (int)v42, v48);
            goto LABEL_60;
        }
        v49 = (char *)CWin32DefaultArena::WbemMemAlloc(0x10u);
        v50 = v49;
        v56 = (TString *)v49;
        v61 = v49;
        if ( v49 )
        {
          *((_WORD *)v49 + 4) = 0;
          *(_QWORD *)v49 = v49 + 8;
          *((_DWORD *)v49 + 3) = 0;
        }
        else
        {
          v50 = 0;
          v56 = 0;
        }
        if ( v50 )
        {
          CFlexArray::InsertAt((CToken *)((char *)this + 48), *((_DWORD *)this + 12), v50);
          v52 = 1;
          v55 = 0;
        }
        goto LABEL_60;
      }
      if ( v30 )
        goto LABEL_52;
      v30 = 1;
LABEL_62:
      v31 = v38 + 1;
      v54 = v31;
      v29 = (int *)v56;
    }
  }
  v16 = (int)v14;
  if ( (unsigned __int64)(int)v14 > 0x7FFFFFFE )
  {
    v62[0] = 0;
  }
  else
  {
    v17 = v62;
    do
    {
      if ( !v16 )
        break;
      v18 = *a2;
      if ( !*a2 )
        break;
      ++a2;
      *v17++ = v18;
      --v16;
      --v15;
    }
    while ( v15 );
    v19 = v17 - 1;
    if ( v15 )
      v19 = v17;
    *v19 = 0;
  }
  *((_DWORD *)this + 11) = 0;
  v20 = (char *)*((_QWORD *)this + 4);
  if ( v20 != v9 )
    CWin32DefaultArena::WbemMemFree(v20);
  *((_QWORD *)this + 4) = v9;
  v21 = -1;
  do
    ++v21;
  while ( v62[v21] );
  v22 = v21 + 1;
  v23 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((int)v21 + 1, 2u));
  if ( v23 )
  {
    *((_QWORD *)this + 4) = v23;
    *((_DWORD *)this + 11) = v22;
    StringCchCopyW(v23, v22, v62);
  }
  *((_DWORD *)this + 7) = 0;
  v24 = (char *)*((_QWORD *)this + 2);
  if ( v24 != (char *)this + 24 )
    CWin32DefaultArena::WbemMemFree(v24);
  *((_QWORD *)this + 2) = (char *)this + 24;
  v25 = -1;
  do
    ++v25;
  while ( v62[v25] );
  v26 = v25 + 1;
  v27 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((int)v25 + 1, 2u));
  if ( v27 )
  {
    *((_QWORD *)this + 2) = v27;
    *((_DWORD *)this + 7) = v26;
    StringCchCopyW(v27, v26, v62);
  }
  if ( *v11 )
    ++*((_DWORD *)this + 2);
  return this;
}

```

## disassembly

```asm
0x1800020c0  mov     [rsp+arg_10], rbx
0x1800020c5  push    rbp
0x1800020c6  push    rsi
0x1800020c7  push    rdi
0x1800020c8  push    r12
0x1800020ca  push    r13
0x1800020cc  push    r14
0x1800020ce  push    r15
0x1800020d0  sub     rsp, 1A0h
0x1800020d7  mov     rax, cs:__security_cookie
0x1800020de  xor     rax, rsp
0x1800020e1  mov     [rsp+1D8h+var_48], rax
0x1800020e9  movzx   ebp, r9b
0x1800020ed  movzx   esi, r8w
0x1800020f1  mov     rbx, rdx
0x1800020f4  mov     r14, rcx
0x1800020f7  mov     [rsp+1D8h+var_188], rcx
0x1800020fc  lea     rax, ??_7CObject@@6B@; const CObject::`vftable'
0x180002103  mov     [rcx], rax
0x180002106  lea     rax, ??_7CToken@@6B@; const CToken::`vftable'
0x18000210d  mov     [rcx], rax
0x180002110  add     rcx, 18h
0x180002114  xor     edx, edx
0x180002116  mov     [rcx], dx
0x180002119  mov     [r14+10h], rcx
0x18000211d  mov     [r14+1Ch], edx
0x180002121  lea     r15, [r14+28h]
0x180002125  mov     [r15], dx
0x180002129  mov     [r14+20h], r15
0x18000212d  mov     [r14+2Ch], edx
0x180002131  lea     rcx, [r14+30h]
0x180002135  mov     edx, 8
0x18000213a  mov     r8d, 64h ; 'd'
0x180002140  call    cs:__imp_??0CFlexArray@@QEAA@HH@Z; CFlexArray::CFlexArray(int,int)
0x180002146  nop
0x180002147  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000214e  mov     [r14+8], r8d
0x180002152  xor     cl, cl
0x180002154  mov     rdi, rbx
0x180002157  movzx   eax, word ptr [rbx]
0x18000215a  test    ax, ax
0x18000215d  jz      short loc_180002195
0x18000215f  mov     rdx, 1000000000000041h
0x180002169  nop     dword ptr [rax+00000000h]
0x180002170  cmp     ax, si
0x180002173  jz      short loc_180002195
0x180002175  sub     ax, 22h ; '"'
0x180002179  cmp     ax, 3Ch ; '<'
0x18000217d  ja      short loc_180002189
0x18000217f  bt      rdx, rax
0x180002183  jb      loc_1800025A7
0x180002189  add     rdi, 2
0x18000218d  movzx   eax, word ptr [rdi]
0x180002190  test    ax, ax
0x180002193  jnz     short loc_180002170
0x180002195  test    bpl, bpl
0x180002198  jz      short loc_1800021A4
0x18000219a  cmp     si, 7Ch ; '|'
0x18000219e  jz      loc_18000232A
0x1800021a4  mov     rax, rdi
0x1800021a7  sub     rax, rbx
0x1800021aa  sar     rax, 1
0x1800021ad  mov     [r14+8], eax
0x1800021b1  mov     edx, 96h
0x1800021b6  cmp     eax, edx
0x1800021b8  jge     loc_18000233C
0x1800021be  movsxd  rcx, eax
0x1800021c1  cmp     rcx, 7FFFFFFEh
0x1800021c8  ja      loc_1800025AE
0x1800021ce  lea     rax, [rsp+1D8h+var_178]
0x1800021d3  test    rcx, rcx
0x1800021d6  jz      short loc_1800021F7
0x1800021d8  movzx   r8d, word ptr [rbx]
0x1800021dc  test    r8w, r8w
0x1800021e0  jz      short loc_1800021F7
0x1800021e2  add     rbx, 2
0x1800021e6  mov     [rax], r8w
0x1800021ea  add     rax, 2
0x1800021ee  dec     rcx
0x1800021f1  sub     rdx, 1
0x1800021f5  jnz     short loc_1800021D3
0x1800021f7  lea     rcx, [rax-2]
0x1800021fb  test    rdx, rdx
0x1800021fe  cmovnz  rcx, rax
0x180002202  xor     ebp, ebp
0x180002204  mov     [rcx], bp
0x180002207  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000220e  mov     [r14+2Ch], ebp
0x180002212  mov     rcx, [r14+20h]
0x180002216  cmp     rcx, r15
0x180002219  jz      short loc_180002228
0x18000221b  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180002221  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180002228  mov     [r14+20h], r15
0x18000222c  lea     rcx, [rsp+1D8h+var_178]
0x180002231  mov     rax, r8
0x180002234  lea     rax, [rax+1]
0x180002238  cmp     word ptr [rcx+rax*2], 0
0x18000223d  jnz     short loc_180002234
0x18000223f  lea     ebx, [rax+1]
0x180002242  movsxd  rsi, ebx
0x180002245  mov     eax, 2
0x18000224a  mul     rsi
0x18000224d  cmovb   rax, r8
0x180002251  mov     rcx, rax
0x180002254  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000225a  test    rax, rax
0x18000225d  jnz     loc_1800022F3
0x180002263  mov     [r14+1Ch], ebp
0x180002267  mov     rcx, [r14+10h]
0x18000226b  lea     rbx, [r14+18h]
0x18000226f  cmp     rcx, rbx
0x180002272  jz      short loc_18000227A
0x180002274  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000227a  mov     [r14+10h], rbx
0x18000227e  lea     rcx, [rsp+1D8h+var_178]
0x180002283  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000228a  mov     rax, r8
0x18000228d  nop     dword ptr [rax]
0x180002290  lea     rax, [rax+1]
0x180002294  cmp     word ptr [rcx+rax*2], 0
0x180002299  jnz     short loc_180002290
0x18000229b  lea     ebx, [rax+1]
0x18000229e  movsxd  rsi, ebx
0x1800022a1  mov     eax, 2
0x1800022a6  mul     rsi
0x1800022a9  cmovb   rax, r8
0x1800022ad  mov     rcx, rax
0x1800022b0  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800022b6  test    rax, rax
0x1800022b9  jnz     short loc_180002310
0x1800022bb  cmp     word ptr [rdi], 0
0x1800022bf  jz      short loc_1800022C5
0x1800022c1  inc     dword ptr [r14+8]
0x1800022c5  mov     rax, r14
0x1800022c8  mov     rcx, [rsp+1D8h+var_48]
0x1800022d0  xor     rcx, rsp; StackCookie
0x1800022d3  call    __security_check_cookie
0x1800022d8  mov     rbx, [rsp+1D8h+arg_10]
0x1800022e0  add     rsp, 1A0h
0x1800022e7  pop     r15
0x1800022e9  pop     r14
0x1800022eb  pop     r13
0x1800022ed  pop     r12
0x1800022ef  pop     rdi
0x1800022f0  pop     rsi
0x1800022f1  pop     rbp
0x1800022f2  retn
0x1800022f3  mov     [r14+20h], rax
0x1800022f7  mov     [r14+2Ch], ebx
0x1800022fb  lea     r8, [rsp+1D8h+var_178]; unsigned __int16 *
0x180002300  mov     rdx, rsi; unsigned __int64
0x180002303  mov     rcx, rax; unsigned __int16 *
0x180002306  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000230b  jmp     loc_180002263
0x180002310  mov     [r14+10h], rax
0x180002314  mov     [r14+1Ch], ebx
0x180002318  lea     r8, [rsp+1D8h+var_178]; unsigned __int16 *
0x18000231d  mov     rdx, rsi; unsigned __int64
0x180002320  mov     rcx, rax; unsigned __int16 *
0x180002323  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180002328  jmp     short loc_1800022BB
0x18000232a  cmp     word ptr [rdi], 7Ch ; '|'
0x18000232e  jz      loc_1800021A4
0x180002334  test    cl, cl
0x180002336  jz      loc_1800021A4
0x18000233c  xor     r15d, r15d
0x18000233f  mov     [rsp+1D8h+var_1A0], r15
0x180002344  xor     eax, eax
0x180002346  mov     [rsp+1D8h+var_1A8], eax
0x18000234a  mov     [rsp+1D8h+var_1B4], eax
0x18000234e  mov     [rsp+1D8h+var_1B8], eax
0x180002352  xor     r13d, r13d
0x180002355  mov     rax, rbx
0x180002358  mov     [rsp+1D8h+var_1B0], rbx
0x18000235d  nop     dword ptr [rax]
0x180002360  movzx   r12d, word ptr [rax]
0x180002364  test    r12w, r12w
0x180002368  jz      loc_180002582
0x18000236e  cmp     r12w, si
0x180002372  jz      loc_1800025BA
0x180002378  mov     rdi, [r14+20h]
0x18000237c  test    rdi, rdi
0x18000237f  jz      loc_1800024C4
0x180002385  mov     rcx, r8
0x180002388  nop     dword ptr [rax+rax+00000000h]
0x180002390  inc     rcx
0x180002393  cmp     word ptr [rdi+rcx*2], 0
0x180002398  jnz     short loc_180002390
0x18000239a  movsxd  rbp, dword ptr [r14+2Ch]
0x18000239e  add     rcx, 2
0x1800023a2  cmp     rcx, rbp
0x1800023a5  jbe     loc_1800025EE
0x1800023ab  mov     rax, r8
0x1800023ae  xchg    ax, ax
0x1800023b0  lea     rax, [rax+1]
0x1800023b4  cmp     word ptr [rdi+rax*2], 0
0x1800023b9  jnz     short loc_1800023B0
0x1800023bb  lea     ebp, [rax+20h]
0x1800023be  movsxd  r15, ebp
0x1800023c1  mov     eax, 2
0x1800023c6  mul     r15
0x1800023c9  cmovb   rax, r8
0x1800023cd  mov     rcx, rax
0x1800023d0  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800023d6  mov     rdi, rax
0x1800023d9  test    rax, rax
0x1800023dc  jnz     loc_1800025C9
0x1800023e2  mov     r15, [rsp+1D8h+var_1A0]
0x1800023e7  mov     rax, [rsp+1D8h+var_1B0]
0x1800023ec  movzx   r12d, word ptr [rax]
0x1800023f0  cmp     r12w, 5Eh ; '^'
0x1800023f5  jz      loc_180002610
0x1800023fb  cmp     r12w, 28h ; '('
0x180002400  jz      loc_180002624
0x180002406  cmp     r12w, 2Ch ; ','
0x18000240b  jz      loc_180002639
0x180002411  cmp     r12w, 29h ; ')'
0x180002416  jz      loc_1800026B2
0x18000241c  cmp     r12w, 22h ; '"'
0x180002421  jz      loc_1800026DB
0x180002427  cmp     [rsp+1D8h+var_1B8], 0
0x18000242c  jz      loc_1800024CB
0x180002432  mov     rdi, [r15]
0x180002435  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000243c  test    rdi, rdi
0x18000243f  jz      loc_180002574
0x180002445  mov     rcx, r8
0x180002448  nop     dword ptr [rax+rax+00000000h]
0x180002450  inc     rcx
0x180002453  cmp     word ptr [rdi+rcx*2], 0
0x180002458  jnz     short loc_180002450
0x18000245a  movsxd  rbp, dword ptr [r15+0Ch]
0x18000245e  add     rcx, 2
0x180002462  cmp     rcx, rbp
0x180002465  jbe     loc_18000274E
0x18000246b  mov     rax, r8
0x18000246e  xchg    ax, ax
0x180002470  lea     rax, [rax+1]
0x180002474  cmp     word ptr [rdi+rax*2], 0
0x180002479  jnz     short loc_180002470
0x18000247b  lea     ebp, [rax+20h]
0x18000247e  movsxd  r15, ebp
0x180002481  mov     eax, 2
0x180002486  mul     r15
0x180002489  cmovb   rax, r8
0x18000248d  mov     rcx, rax
0x180002490  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180002496  mov     rdi, rax
0x180002499  test    rax, rax
0x18000249c  jnz     loc_18000272A
0x1800024a2  mov     rax, [rsp+1D8h+var_1B0]
0x1800024a7  xor     r13d, r13d
0x1800024aa  add     rax, 2
0x1800024ae  mov     [rsp+1D8h+var_1B0], rax
0x1800024b3  mov     r15, [rsp+1D8h+var_1A0]
0x1800024b8  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800024bf  jmp     loc_180002360
0x1800024c4  xor     ecx, ecx
0x1800024c6  jmp     loc_18000239A
0x1800024cb  mov     rdi, [r14+10h]
0x1800024cf  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800024d6  test    rdi, rdi
0x1800024d9  jz      loc_18000257B
0x1800024df  mov     rcx, r8
0x1800024e2  inc     rcx
0x1800024e5  cmp     word ptr [rdi+rcx*2], 0
0x1800024ea  jnz     short loc_1800024E2
0x1800024ec  movsxd  rbp, dword ptr [r14+1Ch]
0x1800024f0  add     rcx, 2
0x1800024f4  cmp     rcx, rbp
0x1800024f7  jbe     short loc_180002552
0x1800024f9  mov     rax, r8
0x1800024fc  nop     dword ptr [rax+00h]
0x180002500  lea     rax, [rax+1]
0x180002504  cmp     word ptr [rdi+rax*2], 0
0x180002509  jnz     short loc_180002500
0x18000250b  lea     ebp, [rax+20h]
0x18000250e  movsxd  r15, ebp
0x180002511  mov     eax, 2
0x180002516  mul     r15
0x180002519  cmovb   rax, r8
0x18000251d  mov     rcx, rax
0x180002520  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180002526  mov     rdi, rax
0x180002529  test    rax, rax
0x18000252c  jz      loc_1800024A2
0x180002532  mov     r8, [r14+10h]; unsigned __int16 *
0x180002536  mov     rdx, r15; unsigned __int64
0x180002539  mov     rcx, rax; unsigned __int16 *
0x18000253c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180002541  lea     rcx, [r14+10h]; this
0x180002545  call    ?Empty@TString@@QEAAXXZ; TString::Empty(void)
0x18000254a  mov     [r14+10h], rdi
0x18000254e  mov     [r14+1Ch], ebp
0x180002552  mov     [rsp+1D8h+var_190], r12w
0x180002558  xor     eax, eax
0x18000255a  mov     [rsp+1D8h+var_18E], ax
0x18000255f  lea     r8, [rsp+1D8h+var_190]; unsigned __int16 *
0x180002564  movsxd  rdx, ebp; unsigned __int64
  ... truncated ...
```
