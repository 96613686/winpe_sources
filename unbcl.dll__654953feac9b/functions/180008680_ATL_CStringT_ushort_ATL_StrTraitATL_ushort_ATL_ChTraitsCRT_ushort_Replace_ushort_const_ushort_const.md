# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)

- ea: `0x180008680`
- end: `0x18000896f`
- name: `?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z`
- size: `751`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18005d720`

## callees

- `0x1800066cc`
- `0x180008310`
- `0x180008680`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000883a`
- `msvcrt!memmove_s` at `0x18000883a`
- `msvcrt!wcsstr` at `0x180008712`
- `msvcrt!wcsstr` at `0x180008733`
- `msvcrt!wcsstr` at `0x1800087e3`
- `msvcrt!wcsstr` at `0x1800088cb`
- `msvcrt!wcsstr` at `0x180008712`
- `msvcrt!wcsstr` at `0x180008733`
- `msvcrt!wcsstr` at `0x1800087e3`
- `msvcrt!wcsstr` at `0x1800088cb`
- `msvcrt!memcpy_s` at `0x18000887b`
- `msvcrt!memcpy_s` at `0x18000887b`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
        const wchar_t **a1,
        const wchar_t *a2,
        _WORD *a3)
{
  __int64 v4; // rdi
  __int64 v5; // r14
  const wchar_t *v6; // rbx
  unsigned int v7; // esi
  unsigned __int64 v8; // r12
  int v9; // r15d
  wchar_t *v10; // rax
  __int64 v11; // rsi
  __int64 v12; // rax
  __int64 v13; // r12
  int v14; // ebx
  __int64 v15; // rdx
  const wchar_t *v16; // rsi
  wchar_t *v17; // rbp
  __int64 v18; // rcx
  __int64 v19; // r8
  errno_t v20; // eax
  errno_t v21; // eax
  wchar_t *v22; // rax
  __int64 v23; // rax
  const wchar_t *v25; // [rsp+28h] [rbp-60h]
  unsigned __int64 v26; // [rsp+38h] [rbp-50h]
  int v28; // [rsp+98h] [rbp+10h]
  unsigned __int64 v30; // [rsp+A8h] [rbp+20h]
  int v31; // [rsp+A8h] [rbp+20h]

  if ( !a2 )
    return 0;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  if ( !(_DWORD)v4 )
    return 0;
  if ( a3 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a3[v5] );
  }
  else
  {
    LODWORD(v5) = 0;
  }
  v6 = *a1;
  v7 = 0;
  v28 = 0;
  v8 = (unsigned __int64)&(*a1)[*((int *)*a1 - 4)];
  v30 = v8;
  if ( (unsigned __int64)*a1 < v8 )
  {
    v9 = 0;
    do
    {
      v10 = wcsstr(v6, a2);
      if ( v10 )
      {
        v11 = (int)v4;
        do
        {
          v6 = &v10[v11];
          ++v9;
          v10 = wcsstr(&v10[v11], a2);
        }
        while ( v10 );
        v8 = v30;
        v28 = v9;
      }
      if ( v6 )
      {
        v12 = -1;
        do
          ++v12;
        while ( v6[v12] );
      }
      else
      {
        LODWORD(v12) = 0;
      }
      v6 += (int)v12 + 1;
    }
    while ( (unsigned __int64)v6 < v8 );
    v7 = v28;
    if ( v28 > 0 )
    {
      v13 = *((int *)*a1 - 4);
      v14 = v13 + v28 * (v5 - v4);
      v15 = (unsigned int)v14;
      if ( v14 <= (int)v13 )
        v15 = (unsigned int)v13;
      if ( (int)((*((_DWORD *)*a1 - 3) - v15) | (1 - *((_DWORD *)*a1 - 2))) < 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, v15, 0);
      v25 = *a1;
      v16 = *a1;
      v26 = (unsigned __int64)&(*a1)[v13];
      if ( (unsigned __int64)*a1 < v26 )
      {
        do
        {
          v17 = wcsstr(v16, a2);
          if ( v17 )
          {
            v18 = (int)v5;
            v19 = (int)v4;
            do
            {
              v16 = &v17[v18];
              v31 = v13 - (v17 - v25) - v4;
              v20 = memmove_s(&v17[v18], 2LL * v31, &v17[v19], 2LL * v31);
              if ( v20 )
              {
                if ( v20 == 12 )
                  goto LABEL_53;
                if ( v20 == 22 || v20 == 34 )
                  goto LABEL_54;
                if ( v20 != 80 )
                  goto LABEL_52;
              }
              v21 = memcpy_s(v17, 2LL * (int)v5, a3, 2LL * (int)v5);
              if ( v21 )
              {
                if ( v21 == 12 )
LABEL_53:
                  ATL::AtlThrowImpl(-2147024882);
                if ( v21 == 22 || v21 == 34 )
                  goto LABEL_54;
                if ( v21 != 80 )
LABEL_52:
                  ATL::AtlThrowImpl(-2147467259);
              }
              v17[(int)v5 + v31] = 0;
              LODWORD(v13) = v5 - v4 + v13;
              v22 = wcsstr(v16, a2);
              v18 = (int)v5;
              v17 = v22;
              v19 = (int)v4;
            }
            while ( v22 );
          }
          if ( v16 )
          {
            v23 = -1;
            do
              ++v23;
            while ( v16[v23] );
          }
          else
          {
            LODWORD(v23) = 0;
          }
          v16 += (int)v23 + 1;
        }
        while ( (unsigned __int64)v16 < v26 );
      }
      if ( v14 < 0 || v14 > *((_DWORD *)*a1 - 3) )
LABEL_54:
        ATL::AtlThrowImpl(-2147024809);
      v7 = v28;
      *((_DWORD *)*a1 - 4) = v14;
      (*a1)[v14] = 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180008680  mov     [rsp+Source], r8
0x180008685  mov     [rsp+arg_0], rcx
0x18000868a  push    rbx
0x18000868b  push    rbp
0x18000868c  push    rsi
0x18000868d  push    rdi
0x18000868e  push    r12
0x180008690  push    r13
0x180008692  push    r14
0x180008694  push    r15
0x180008696  sub     rsp, 48h
0x18000869a  mov     r15, rcx
0x18000869d  mov     rax, r8
0x1800086a0  xor     ecx, ecx
0x1800086a2  mov     r13, rdx
0x1800086a5  test    rdx, rdx
0x1800086a8  jz      loc_18000893B
0x1800086ae  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800086b2  mov     rdi, rdx
0x1800086b5  inc     rdi
0x1800086b8  cmp     [r13+rdi*2+0], cx
0x1800086be  jnz     short loc_1800086B5
0x1800086c0  test    edi, edi
0x1800086c2  jz      loc_18000893B
0x1800086c8  test    rax, rax
0x1800086cb  jz      short loc_1800086DC
0x1800086cd  mov     r14, rdx
0x1800086d0  inc     r14
0x1800086d3  cmp     [r8+r14*2], cx
0x1800086d8  jnz     short loc_1800086D0
0x1800086da  jmp     short loc_1800086DF
0x1800086dc  mov     r14d, ecx
0x1800086df  mov     rbx, [r15]
0x1800086e2  mov     esi, ecx
0x1800086e4  mov     [rsp+88h+arg_8], ecx
0x1800086eb  movsxd  rax, dword ptr [rbx-10h]
0x1800086ef  lea     r12, [rbx+rax*2]
0x1800086f3  mov     [rsp+88h+arg_18], r12
0x1800086fb  cmp     rbx, r12
0x1800086fe  jnb     loc_180008937
0x180008704  mov     ebp, 1
0x180008709  mov     r15d, ecx
0x18000870c  mov     rdx, r13; SubStr
0x18000870f  mov     rcx, rbx; Str
0x180008712  call    cs:__imp_wcsstr
0x180008718  xor     r8d, r8d
0x18000871b  test    rax, rax
0x18000871e  jz      short loc_180008751
0x180008720  movsxd  rsi, edi
0x180008723  add     rsi, rsi
0x180008726  lea     rbx, [rsi+rax]
0x18000872a  mov     rdx, r13; SubStr
0x18000872d  mov     rcx, rbx; Str
0x180008730  add     r15d, ebp
0x180008733  call    cs:__imp_wcsstr
0x180008739  test    rax, rax
0x18000873c  jnz     short loc_180008726
0x18000873e  mov     r12, [rsp+88h+arg_18]
0x180008746  xor     r8d, r8d
0x180008749  mov     [rsp+88h+arg_8], r15d
0x180008751  test    rbx, rbx
0x180008754  jz      short loc_180008766
0x180008756  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000875a  inc     rax
0x18000875d  cmp     [rbx+rax*2], r8w
0x180008762  jnz     short loc_18000875A
0x180008764  jmp     short loc_180008769
0x180008766  mov     eax, r8d
0x180008769  inc     eax
0x18000876b  movsxd  rcx, eax
0x18000876e  lea     rbx, [rbx+rcx*2]
0x180008772  cmp     rbx, r12
0x180008775  jb      short loc_18000870C
0x180008777  mov     esi, [rsp+88h+arg_8]
0x18000877e  mov     r15, [rsp+88h+arg_0]
0x180008786  test    esi, esi
0x180008788  jle     loc_180008937
0x18000878e  mov     rcx, [r15]
0x180008791  mov     ebx, r14d
0x180008794  sub     ebx, edi
0x180008796  imul    ebx, esi
0x180008799  movsxd  r12, dword ptr [rcx-10h]
0x18000879d  mov     eax, [rcx-0Ch]
0x1800087a0  add     ebx, r12d
0x1800087a3  cmp     ebx, r12d
0x1800087a6  mov     edx, ebx
0x1800087a8  cmovle  edx, r12d
0x1800087ac  sub     ebp, [rcx-8]
0x1800087af  sub     eax, edx
0x1800087b1  or      ebp, eax
0x1800087b3  jge     short loc_1800087C0
0x1800087b5  mov     rcx, r15
0x1800087b8  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800087bd  xor     r8d, r8d
0x1800087c0  mov     rcx, [r15]
0x1800087c3  mov     [rsp+88h+var_60], rcx
0x1800087c8  mov     rsi, rcx
0x1800087cb  lea     rax, [rcx+r12*2]
0x1800087cf  mov     [rsp+88h+var_50], rax
0x1800087d4  cmp     rcx, rax
0x1800087d7  jnb     loc_180008916
0x1800087dd  mov     rdx, r13; SubStr
0x1800087e0  mov     rcx, rsi; Str
0x1800087e3  call    cs:__imp_wcsstr
0x1800087e9  xor     r8d, r8d
0x1800087ec  mov     rbp, rax
0x1800087ef  test    rax, rax
0x1800087f2  jz      loc_1800088EA
0x1800087f8  movsxd  rcx, r14d
0x1800087fb  add     rcx, rcx
0x1800087fe  movsxd  r8, edi
0x180008801  add     r8, r8
0x180008804  mov     [rsp+88h+SourceSize], rcx
0x180008809  mov     [rsp+88h+var_58], r8
0x18000880e  mov     edx, r12d
0x180008811  lea     rsi, [rcx+rbp]
0x180008815  mov     rax, rbp
0x180008818  add     r8, rbp; Source
0x18000881b  sub     rax, [rsp+88h+var_60]
0x180008820  mov     rcx, rsi; Destination
0x180008823  sar     rax, 1
0x180008826  sub     edx, eax
0x180008828  sub     edx, edi
0x18000882a  mov     dword ptr [rsp+88h+arg_18], edx
0x180008831  movsxd  rdx, edx
0x180008834  add     rdx, rdx; DestinationSize
0x180008837  mov     r9, rdx; SourceSize
0x18000883a  call    cs:__imp_memmove_s
0x180008840  test    eax, eax
0x180008842  jz      short loc_180008868
0x180008844  cmp     eax, 0Ch
0x180008847  jz      loc_180008959
0x18000884d  cmp     eax, 16h
0x180008850  jz      loc_180008964
0x180008856  cmp     eax, 22h ; '"'
0x180008859  jz      loc_180008964
0x18000885f  cmp     eax, 50h ; 'P'
0x180008862  jnz     loc_18000894E
0x180008868  mov     rdx, [rsp+88h+SourceSize]; DestinationSize
0x18000886d  mov     rcx, rbp; Destination
0x180008870  mov     r8, [rsp+88h+Source]; Source
0x180008878  mov     r9, rdx; SourceSize
0x18000887b  call    cs:__imp_memcpy_s
0x180008881  test    eax, eax
0x180008883  jz      short loc_1800088A9
0x180008885  cmp     eax, 0Ch
0x180008888  jz      loc_180008959
0x18000888e  cmp     eax, 16h
0x180008891  jz      loc_180008964
0x180008897  cmp     eax, 22h ; '"'
0x18000889a  jz      loc_180008964
0x1800088a0  cmp     eax, 50h ; 'P'
0x1800088a3  jnz     loc_18000894E
0x1800088a9  mov     eax, dword ptr [rsp+88h+arg_18]
0x1800088b0  mov     rdx, r13; SubStr
0x1800088b3  add     eax, r14d
0x1800088b6  movsxd  rcx, eax
0x1800088b9  xor     eax, eax
0x1800088bb  mov     [rbp+rcx*2+0], ax
0x1800088c0  mov     eax, r14d
0x1800088c3  sub     eax, edi
0x1800088c5  mov     rcx, rsi; Str
0x1800088c8  add     r12d, eax
0x1800088cb  call    cs:__imp_wcsstr
0x1800088d1  mov     rcx, [rsp+88h+SourceSize]
0x1800088d6  mov     rbp, rax
0x1800088d9  mov     r8, [rsp+88h+var_58]
0x1800088de  test    rax, rax
0x1800088e1  jnz     loc_18000880E
0x1800088e7  xor     r8d, r8d
0x1800088ea  test    rsi, rsi
0x1800088ed  jz      short loc_1800088FF
0x1800088ef  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800088f3  inc     rax
0x1800088f6  cmp     [rsi+rax*2], r8w
0x1800088fb  jnz     short loc_1800088F3
0x1800088fd  jmp     short loc_180008902
0x1800088ff  mov     eax, r8d
0x180008902  inc     eax
0x180008904  movsxd  rcx, eax
0x180008907  lea     rsi, [rsi+rcx*2]
0x18000890b  cmp     rsi, [rsp+88h+var_50]
0x180008910  jb      loc_1800087DD
0x180008916  test    ebx, ebx
0x180008918  js      short loc_180008964
0x18000891a  mov     rax, [r15]
0x18000891d  cmp     ebx, [rax-0Ch]
0x180008920  jg      short loc_180008964
0x180008922  mov     esi, [rsp+88h+arg_8]
0x180008929  mov     [rax-10h], ebx
0x18000892c  mov     rcx, [r15]
0x18000892f  movsxd  rdx, ebx
0x180008932  mov     [rcx+rdx*2], r8w
0x180008937  mov     eax, esi
0x180008939  jmp     short loc_18000893D
0x18000893b  xor     eax, eax
0x18000893d  add     rsp, 48h
0x180008941  pop     r15
0x180008943  pop     r14
0x180008945  pop     r13
0x180008947  pop     r12
0x180008949  pop     rdi
0x18000894a  pop     rsi
0x18000894b  pop     rbp
0x18000894c  pop     rbx
0x18000894d  retn
0x18000894e  mov     ecx, 80004005h; int
0x180008953  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180008959  mov     ecx, 8007000Eh; int
0x18000895e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180008964  mov     ecx, 80070057h; int
0x180008969  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
