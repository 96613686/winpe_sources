# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)

- ea: `0x180005658`
- end: `0x180005881`
- name: `?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z`
- size: `553`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800052cc`
- `0x180009300`

## callees

- `0x1800048b8`
- `0x180004b50`
- `0x180004c10`
- `0x180005658`
- `0x180005888`

## import_xrefs

- `msvcrt!wcsstr` at `0x1800056cd`
- `msvcrt!wcsstr` at `0x1800056ea`
- `msvcrt!wcsstr` at `0x180005781`
- `msvcrt!wcsstr` at `0x18000581b`
- `msvcrt!wcsstr` at `0x1800056cd`
- `msvcrt!wcsstr` at `0x1800056ea`
- `msvcrt!wcsstr` at `0x180005781`
- `msvcrt!wcsstr` at `0x18000581b`
- `msvcrt!memmove_s` at `0x1800057cb`
- `msvcrt!memmove_s` at `0x1800057cb`
- `msvcrt!memcpy_s` at `0x1800057e8`
- `msvcrt!memcpy_s` at `0x1800057e8`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
        const wchar_t **a1)
{
  const wchar_t **v1; // rsi
  __int64 result; // rax
  __int64 v3; // r14
  int v4; // eax
  const wchar_t *v5; // rbx
  int v6; // ebp
  int v7; // r12d
  unsigned __int64 v8; // r15
  wchar_t *v9; // rax
  __int64 v10; // rdi
  __int64 v11; // r15
  int v12; // r13d
  unsigned int v13; // r8d
  const wchar_t *v14; // r12
  const wchar_t *v15; // rdi
  unsigned __int64 v16; // rbp
  wchar_t *v17; // rax
  wchar_t *v18; // rbp
  rsize_t v19; // r13
  int v20; // ebx
  errno_t v21; // eax
  errno_t v22; // eax
  unsigned __int64 v23; // [rsp+20h] [rbp-58h]
  int v25; // [rsp+88h] [rbp+10h]
  int v26; // [rsp+90h] [rbp+18h]
  int v27; // [rsp+98h] [rbp+20h]

  v1 = a1;
  result = ATL::ChTraitsCRT<unsigned short>::SafeStringLen(L"&");
  v3 = (int)result;
  if ( (_DWORD)result )
  {
    v4 = ATL::ChTraitsCRT<unsigned short>::SafeStringLen(L"&&");
    v5 = *v1;
    v6 = 0;
    v7 = v4;
    v26 = v4;
    v25 = 0;
    v8 = (unsigned __int64)&(*v1)[*((int *)*v1 - 4)];
    if ( (unsigned __int64)*v1 < v8 )
    {
      do
      {
        v9 = wcsstr(v5, L"&");
        if ( v9 )
        {
          v10 = v3;
          do
          {
            v5 = &v9[v10];
            ++v6;
            v9 = wcsstr(&v9[v10], L"&");
          }
          while ( v9 );
          v25 = v6;
        }
        v5 += (int)(ATL::ChTraitsCRT<unsigned short>::SafeStringLen(v5) + 1);
      }
      while ( (unsigned __int64)v5 < v8 );
      if ( v6 > 0 )
      {
        v11 = *((int *)*v1 - 4);
        v12 = v11 + v6 * (v7 - v3);
        v27 = v12;
        v13 = v12;
        if ( v12 <= (int)v11 )
          v13 = *((_DWORD *)*v1 - 4);
        if ( (((*((_DWORD *)*v1 - 3) - v13) | (1 - *((_DWORD *)*v1 - 2))) & 0x80000000) != 0 )
          ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(v1, v13);
        v14 = *v1;
        v15 = *v1;
        v23 = (unsigned __int64)&(*v1)[v11];
        if ( (unsigned __int64)*v1 < v23 )
        {
          v16 = (unsigned __int64)&(*v1)[v11];
          do
          {
            v17 = wcsstr(v15, L"&");
            if ( v17 )
            {
              v18 = v17;
              v19 = v26;
              do
              {
                v15 = &v18[v19];
                v20 = v11 - (v18 - v14) - v3;
                v21 = memmove_s(&v18[v19], 2LL * v20, &v18[v3], 2LL * v20);
                ATL::AtlCrtErrorCheck(v21);
                v22 = memcpy_s(v18, v19 * 2, L"&&", v19 * 2);
                ATL::AtlCrtErrorCheck(v22);
                v18[v20 + v26] = 0;
                LODWORD(v11) = v26 - v3 + v11;
                v18 = wcsstr(&v18[v19], L"&");
              }
              while ( v18 );
              v16 = v23;
            }
            v15 += (int)(ATL::ChTraitsCRT<unsigned short>::SafeStringLen(v15) + 1);
          }
          while ( (unsigned __int64)v15 < v16 );
          v1 = a1;
          v6 = v25;
          v12 = v27;
        }
        ATL::CSimpleStringT<unsigned short,0>::SetLength(v1, (unsigned int)v12);
      }
    }
    return (unsigned int)v6;
  }
  return result;
}

```

## disassembly

```asm
0x180005658  mov     [rsp+arg_10], r8
0x18000565d  mov     [rsp+arg_8], rdx
0x180005662  mov     [rsp+arg_0], rcx
0x180005667  push    rbx
0x180005668  push    rbp
0x180005669  push    rsi
0x18000566a  push    rdi
0x18000566b  push    r12
0x18000566d  push    r13
0x18000566f  push    r14
0x180005671  push    r15
0x180005673  sub     rsp, 38h
0x180005677  lea     r13, SubStr; "&"
0x18000567e  mov     rsi, rcx
0x180005681  mov     rcx, r13
0x180005684  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x180005689  movsxd  r14, eax
0x18000568c  test    eax, eax
0x18000568e  jz      loc_180005870
0x180005694  lea     rcx, asc_18000F750; "&&"
0x18000569b  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x1800056a0  mov     rbx, [rsi]
0x1800056a3  xor     ebp, ebp
0x1800056a5  mov     r12d, eax
0x1800056a8  mov     dword ptr [rsp+78h+arg_10], eax
0x1800056af  mov     dword ptr [rsp+78h+arg_8], ebp
0x1800056b6  movsxd  rcx, dword ptr [rbx-10h]
0x1800056ba  lea     r15, [rbx+rcx*2]
0x1800056be  cmp     rbx, r15
0x1800056c1  jnb     loc_18000586E
0x1800056c7  mov     rdx, r13; SubStr
0x1800056ca  mov     rcx, rbx; Str
0x1800056cd  call    cs:__imp_wcsstr
0x1800056d3  test    rax, rax
0x1800056d6  jz      short loc_1800056FC
0x1800056d8  mov     rdi, r14
0x1800056db  add     rdi, rdi
0x1800056de  lea     rbx, [rdi+rax]
0x1800056e2  mov     rdx, r13; SubStr
0x1800056e5  mov     rcx, rbx; Str
0x1800056e8  inc     ebp
0x1800056ea  call    cs:__imp_wcsstr
0x1800056f0  test    rax, rax
0x1800056f3  jnz     short loc_1800056DE
0x1800056f5  mov     dword ptr [rsp+78h+arg_8], ebp
0x1800056fc  mov     rcx, rbx
0x1800056ff  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x180005704  inc     eax
0x180005706  cdqe
0x180005708  lea     rbx, [rbx+rax*2]
0x18000570c  cmp     rbx, r15
0x18000570f  jb      short loc_1800056C7
0x180005711  test    ebp, ebp
0x180005713  jle     loc_18000586E
0x180005719  mov     rdx, [rsi]
0x18000571c  mov     r13d, r12d
0x18000571f  sub     r13d, r14d
0x180005722  mov     ecx, 1
0x180005727  imul    r13d, ebp
0x18000572b  movsxd  r15, dword ptr [rdx-10h]
0x18000572f  mov     eax, [rdx-0Ch]
0x180005732  add     r13d, r15d
0x180005735  cmp     r13d, r15d
0x180005738  mov     [rsp+78h+arg_18], r13d
0x180005740  mov     r8d, r13d
0x180005743  cmovle  r8d, r15d
0x180005747  sub     ecx, [rdx-8]
0x18000574a  sub     eax, r8d
0x18000574d  or      ecx, eax
0x18000574f  jge     short loc_18000575C
0x180005751  mov     edx, r8d
0x180005754  mov     rcx, rsi
0x180005757  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18000575c  mov     r12, [rsi]
0x18000575f  mov     rdi, r12
0x180005762  lea     rax, [r12+r15*2]
0x180005766  mov     [rsp+78h+var_58], rax
0x18000576b  cmp     r12, rax
0x18000576e  jnb     loc_180005863
0x180005774  mov     rbp, rax
0x180005777  lea     rdx, SubStr; "&"
0x18000577e  mov     rcx, rdi; Str
0x180005781  call    cs:__imp_wcsstr
0x180005787  test    rax, rax
0x18000578a  jz      loc_180005832
0x180005790  movsxd  r13, dword ptr [rsp+78h+arg_10]
0x180005798  mov     rsi, r14
0x18000579b  add     rsi, rsi
0x18000579e  mov     rbp, rax
0x1800057a1  add     r13, r13
0x1800057a4  mov     rcx, rbp
0x1800057a7  lea     r8, [rsi+rbp]; Source
0x1800057ab  sub     rcx, r12
0x1800057ae  mov     ebx, r15d
0x1800057b1  sar     rcx, 1
0x1800057b4  mov     rdi, rbp
0x1800057b7  sub     ebx, ecx
0x1800057b9  add     rdi, r13
0x1800057bc  sub     ebx, r14d
0x1800057bf  mov     rcx, rdi; Destination
0x1800057c2  movsxd  rdx, ebx
0x1800057c5  add     rdx, rdx; DestinationSize
0x1800057c8  mov     r9, rdx; SourceSize
0x1800057cb  call    cs:__imp_memmove_s
0x1800057d1  mov     ecx, eax; int
0x1800057d3  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800057d8  mov     r9, r13; SourceSize
0x1800057db  lea     r8, asc_18000F750; "&&"
0x1800057e2  mov     rdx, r13; DestinationSize
0x1800057e5  mov     rcx, rbp; Destination
0x1800057e8  call    cs:__imp_memcpy_s
0x1800057ee  mov     ecx, eax; int
0x1800057f0  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800057f5  mov     edx, dword ptr [rsp+78h+arg_10]
0x1800057fc  lea     eax, [rbx+rdx]
0x1800057ff  movsxd  rcx, eax
0x180005802  xor     eax, eax
0x180005804  mov     [rbp+rcx*2+0], ax
0x180005809  mov     eax, edx
0x18000580b  sub     eax, r14d
0x18000580e  lea     rdx, SubStr; "&"
0x180005815  mov     rcx, rdi; Str
0x180005818  add     r15d, eax
0x18000581b  call    cs:__imp_wcsstr
0x180005821  mov     rbp, rax
0x180005824  test    rax, rax
0x180005827  jnz     loc_1800057A4
0x18000582d  mov     rbp, [rsp+78h+var_58]
0x180005832  mov     rcx, rdi
0x180005835  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x18000583a  inc     eax
0x18000583c  movsxd  rcx, eax
0x18000583f  lea     rdi, [rdi+rcx*2]
0x180005843  cmp     rdi, rbp
0x180005846  jb      loc_180005777
0x18000584c  mov     rsi, [rsp+78h+arg_0]
0x180005854  mov     ebp, dword ptr [rsp+78h+arg_8]
0x18000585b  mov     r13d, [rsp+78h+arg_18]
0x180005863  mov     edx, r13d
0x180005866  mov     rcx, rsi
0x180005869  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x18000586e  mov     eax, ebp
0x180005870  add     rsp, 38h
0x180005874  pop     r15
0x180005876  pop     r14
0x180005878  pop     r13
0x18000587a  pop     r12
0x18000587c  pop     rdi
0x18000587d  pop     rsi
0x18000587e  pop     rbp
0x18000587f  pop     rbx
0x180005880  retn
```
