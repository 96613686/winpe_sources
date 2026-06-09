# AddStringValAsBytes(ulong *,uchar const *,int,CTypeInfo const *,CHashString const *,wchar_t *)

- ea: `0x10082a400`
- end: `0x10082a87d`
- name: `?AddStringValAsBytes@@YAXPEAKPEBEHPEBVCTypeInfo@@PEBVCHashString@@PEA_W@Z`
- size: `1149`
- prototype: `void(unsigned int *, const unsigned __int8 *, int, const struct CTypeInfo *, const struct CHashString *, wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x10082b3c0`

## callees

- `0x10040ce20`
- `0x10082a400`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10082a500`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082a859`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082a500`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082a859`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10082a4f0`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10082a4f0`
- `sqldk!SystemThread_TlsIndex` at `0x10082a490`
- `sqldk!SystemThread_TlsOffset` at `0x10082a499`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082a4b4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082a4b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AddStringValAsBytes(
        unsigned int *a1,
        const char *a2,
        int a3,
        const struct CTypeInfo *a4,
        const struct CHashString *a5,
        wchar_t *a6)
{
  unsigned __int64 v6; // r15
  unsigned int v9; // esi
  wchar_t *v10; // rbx
  __int64 v11; // rcx
  unsigned int v12; // edi
  char v13; // r8
  unsigned __int64 v14; // r14
  wchar_t *v15; // r13
  __int64 v16; // rbx
  __int64 v17; // r10
  unsigned __int64 v18; // rax
  unsigned int v19; // ecx
  __int64 v20; // rcx
  const unsigned __int8 *v21; // rax
  int j; // r8d
  int v23; // edx
  int v24; // ecx
  int v25; // r15d
  __int64 v26; // r8
  unsigned int v27; // r15d
  int v28; // edi
  int v29; // edi
  int v30; // edi
  void ***v31; // rdi
  __int64 v32; // rax
  unsigned int v33; // edi
  unsigned __int64 v34; // rcx
  const unsigned __int8 *v35; // rdx
  int v36; // eax
  __int64 i; // rdx
  __int64 v38; // rax
  unsigned int v39; // [rsp+B8h] [rbp+20h] BYREF

  v6 = a3;
  v9 = 0;
  v10 = 0;
  v11 = *(unsigned __int8 *)a4;
  if ( (unsigned __int8)(v11 + 16) <= 1u )
    v12 = 0;
  else
    v12 = *((_DWORD *)a4 + 5);
  v13 = v12;
  if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsUnicode + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v11)) )
  {
    v14 = v6 >> 1;
  }
  else
  {
    v15 = a6;
    if ( !a6 )
    {
      v16 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v17 = *(_QWORD *)(v16 + 256);
      if ( !v17 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v17 = *(_QWORD *)(v16 + 256);
      }
      v18 = 2 * v6;
      if ( !is_mul_ok(v6, 2u) )
        v18 = -1;
      v10 = (wchar_t *)operator new[](
                         v18,
                         *(struct IMemObj **)(v17 + 1000),
                         "sql\\ntdbms\\msql\\expr\\runtime\\DwEsIntrinsic.inl",
                         487,
                         3u);
      if ( v10 )
        operator delete[](0);
      v15 = v10;
    }
    if ( (v12 & 0x80) != 0 )
    {
      v19 = 65001;
    }
    else if ( HIBYTE(v12) )
    {
      v19 = *((_DWORD *)&x_uiCodePage + (unsigned __int8)byte_10085C9DC[40 * HIBYTE(v12)]);
    }
    else
    {
      v19 = qword_100856AB0[4 * (v12 & 0x7F)];
    }
    LODWORD(v14) = FastDBCSToUnicode(v19, a2, v6, v15, v6);
    LODWORD(v6) = 2 * v14;
    a2 = (const char *)v15;
    v13 = v12;
  }
  if ( v12 != 2056 )
  {
    if ( (v12 & 0x10800) != 0 )
    {
      v33 = HIBYTE(v12);
      if ( !(_BYTE)v33
        || v33 < 0x100
        && *((_QWORD *)&x_rgSortOrderMap + 5 * (unsigned __int8)v33)
        && (dword_10085C9D8[10 * (unsigned __int8)v33] & 0x10800) != 0 )
      {
        v34 = (unsigned __int64)(int)v6 >> 1;
        v35 = (const unsigned __int8 *)&a2[2 * (int)v34 - 2];
        if ( (_DWORD)v34 )
        {
          while ( *(_WORD *)v35 == 32 || *(_WORD *)v35 == 12288 )
          {
            v35 -= 2;
            LODWORD(v34) = v34 - 1;
            if ( !(_DWORD)v34 )
              goto LABEL_63;
          }
          v36 = 255;
          if ( (int)v34 < 255 )
            v36 = v34;
          if ( v36 > 0 )
          {
            for ( i = 0; i < v36; v9 = (v9 >> 28) ^ *(unsigned __int16 *)&a2[2 * i++] ^ (16 * v9) )
              ;
          }
        }
LABEL_63:
        v39 = v9;
        goto LABEL_64;
      }
    }
    else if ( !HIBYTE(v12) )
    {
      v23 = (v12 >> 12) & 1 | 2;
      if ( (v12 & 0x2000) == 0 )
        v23 = (v12 >> 12) & 1;
      v24 = v23 | 0x10000;
      if ( (v12 & 0x4000) == 0 )
        v24 = v23;
      v25 = v24 | 0x20000;
      if ( (v12 & 0x8000) == 0 )
        v25 = v24;
      if ( (v12 & 0x200) != 0 )
        v25 |= 8u;
      v26 = 32LL * (v13 & 0x7F);
      v27 = v25 | 0x80000400;
      v28 = (v12 >> 17) & 0x7F;
      if ( v28 )
      {
        v29 = v28 - 1;
        if ( v29 )
        {
          v30 = v29 - 1;
          if ( v30 )
          {
            if ( v30 == 1 )
            {
              v31 = &x_SqlSortManager_140;
              goto LABEL_46;
            }
LABEL_64:
            v38 = (unsigned __int8)(LOBYTE(dword_10089EAC0[(unsigned __int8)(LOBYTE(dword_10089EAC0[(unsigned __int8)(LOBYTE(dword_10089EAC0[(unsigned __int8)(v39 ^ *a1)]) ^ BYTE1(*a1) ^ BYTE1(v39))])
                                                                           ^ ((unsigned __int16)(LOWORD(dword_10089EAC0[(unsigned __int8)(v39 ^ *a1)])
                                                                                               ^ (*a1 >> 8)) >> 8)
                                                                           ^ BYTE2(v39))])
                                  ^ ((unsigned __int16)(LOWORD(dword_10089EAC0[(unsigned __int8)(LOBYTE(dword_10089EAC0[(unsigned __int8)(v39 ^ *a1)])
                                                                                               ^ BYTE1(*a1)
                                                                                               ^ BYTE1(v39))])
                                                      ^ ((dword_10089EAC0[(unsigned __int8)(v39 ^ *a1)] ^ (*a1 >> 8)) >> 8)) >> 8)
                                  ^ HIBYTE(v39));
            *a1 = dword_10089EAC0[v38]
                ^ ((dword_10089EAC0[(unsigned __int8)(LOBYTE(dword_10089EAC0[(unsigned __int8)(LOBYTE(dword_10089EAC0[(unsigned __int8)(v39 ^ *a1)])
                                                                                             ^ BYTE1(*a1)
                                                                                             ^ BYTE1(v39))])
                                                    ^ ((unsigned __int16)(LOWORD(dword_10089EAC0[(unsigned __int8)(v39 ^ *a1)])
                                                                        ^ (*a1 >> 8)) >> 8)
                                                    ^ BYTE2(v39))]
                  ^ ((dword_10089EAC0[(unsigned __int8)(LOBYTE(dword_10089EAC0[(unsigned __int8)(v39 ^ *a1)])
                                                      ^ BYTE1(*a1)
                                                      ^ BYTE1(v39))]
                    ^ ((dword_10089EAC0[(unsigned __int8)(v39 ^ *a1)] ^ (*a1 >> 8)) >> 8)) >> 8)) >> 8);
            goto LABEL_65;
          }
          v31 = &x_SqlSortManager_100;
        }
        else
        {
          v31 = &x_SqlSortManager_90;
        }
      }
      else
      {
        v31 = &x_SqlSortManager_80;
      }
LABEL_46:
      v32 = ((__int64 (__fastcall *)(void ***, _QWORD))(*v31)[1])(v31, *(unsigned int *)((char *)&x_rgLocaleMap + v26));
      if ( v32 )
        ((void (__fastcall *)(void ***, __int64, _QWORD, const char *, _DWORD, unsigned int *, _DWORD))(*v31)[11])(
          v31,
          v32,
          v27,
          a2,
          v14,
          &v39,
          0);
      goto LABEL_64;
    }
    v39 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, const struct CHashString *, const char *, _DWORD, _BYTE, _DWORD))a5
           + 12))(
            *((_QWORD *)a5 + 8),
            *((unsigned int *)a5 + 21),
            *((_QWORD *)a5 + 9),
            *((unsigned int *)a5 + 20),
            a5,
            a2,
            v6,
            0,
            0);
    goto LABEL_64;
  }
  v20 = (int)v14;
  if ( (int)v14 > 0 )
  {
    v21 = (const unsigned __int8 *)&a2[2 * (int)v14 - 2];
    do
    {
      if ( *(_WORD *)v21 != 32 )
        break;
      LODWORD(v14) = v14 - 1;
      --v20;
      v21 -= 2;
    }
    while ( v20 > 0 );
  }
  for ( j = 2 * v14; j > 0; --j )
    *a1 = dword_10089EAC0[(unsigned __int8)(*a2++ ^ *a1)] ^ (*a1 >> 8);
LABEL_65:
  operator delete[](v10);
}

```

## disassembly

```asm
0x10082a400  mov     rax, rsp
0x10082a403  push    rdi
0x10082a404  push    r12
0x10082a406  push    r13
0x10082a408  push    r14
0x10082a40a  push    r15
0x10082a40c  sub     rsp, 70h
0x10082a410  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x10082a418  mov     [rax+8], rbx
0x10082a41c  mov     [rax+10h], rbp
0x10082a420  mov     [rax+18h], rsi
0x10082a424  movsxd  r15, r8d
0x10082a427  mov     rbp, rdx
0x10082a42a  mov     r12, rcx
0x10082a42d  xor     esi, esi
0x10082a42f  mov     ebx, esi
0x10082a431  mov     [rax-48h], rbx
0x10082a435  movzx   ecx, byte ptr [r9]
0x10082a439  lea     eax, [rcx+10h]
0x10082a43c  cmp     al, 1
0x10082a43e  jbe     short loc_10082A446
0x10082a440  mov     edi, [r9+14h]
0x10082a444  jmp     short loc_10082A448
0x10082a446  mov     edi, esi
0x10082a448  mov     r8d, edi
0x10082a44b  mov     [rsp+98h+var_40], r8
0x10082a450  lea     r13, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10082a457  movzx   eax, byte ptr [rcx+r13+45AE60h]
0x10082a460  cmp     byte ptr [rax+r13+45AF60h], 0
0x10082a469  jz      short loc_10082A476
0x10082a46b  mov     r14, r15
0x10082a46e  shr     r14, 1
0x10082a471  jmp     loc_10082A581
0x10082a476  mov     r13, [rsp+98h+arg_28]
0x10082a47e  test    r13, r13
0x10082a481  jnz     loc_10082A50E
0x10082a487  mov     rdx, gs:58h
0x10082a490  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10082a497  mov     ecx, [rax]
0x10082a499  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10082a4a0  mov     ebx, [rax]
0x10082a4a2  add     rbx, [rdx+rcx*8]
0x10082a4a6  mov     r10, [rbx+100h]
0x10082a4ad  test    r10, r10
0x10082a4b0  jnz     short loc_10082A4C1
0x10082a4b2  xor     ecx, ecx
0x10082a4b4  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10082a4ba  mov     r10, [rbx+100h]
0x10082a4c1  mov     eax, 2
0x10082a4c6  mul     r15
0x10082a4c9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10082a4d0  cmovo   rax, rcx
0x10082a4d4  mov     byte ptr [rsp+98h+var_78], 3
0x10082a4d9  mov     r9d, 1E7h
0x10082a4df  lea     r8, aSqlNtdbmsMsqlE_7; "sql\\ntdbms\\msql\\expr\\runtime\\DwEsI"...
0x10082a4e6  mov     rdx, [r10+3E8h]
0x10082a4ed  mov     rcx, rax
0x10082a4f0  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10082a4f6  mov     rbx, rax
0x10082a4f9  test    rax, rax
0x10082a4fc  jz      short loc_10082A506
0x10082a4fe  xor     ecx, ecx
0x10082a500  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10082a506  mov     [rsp+98h+var_48], rbx
0x10082a50b  mov     r13, rbx
0x10082a50e  mov     eax, edi
0x10082a510  shr     eax, 7
0x10082a513  test    al, 1
0x10082a515  jz      short loc_10082A51E
0x10082a517  mov     ecx, 0FDE9h
0x10082a51c  jmp     short loc_10082A558
0x10082a51e  mov     eax, edi
0x10082a520  shr     eax, 18h
0x10082a523  lea     rdx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10082a52a  test    al, al
0x10082a52c  jnz     short loc_10082A542
0x10082a52e  movzx   eax, dil
0x10082a532  and     eax, 7Fh
0x10082a535  shl     rax, 5
0x10082a539  mov     ecx, [rax+rdx+456AB0h]
0x10082a540  jmp     short loc_10082A558
0x10082a542  movzx   eax, al
0x10082a545  lea     rcx, [rax+rax*4]
0x10082a549  movzx   eax, ds:rva byte_10085C9DC[rdx+rcx*8]; CTypeInfo const CTypeInfo::tiBit ...
0x10082a551  mov     ecx, ds:rva ?x_uiCodePage@@3QBIB[rdx+rax*4]; unsigned int
0x10082a558  mov     [rsp+98h+var_78], r15d; int
0x10082a55d  mov     r9, r13; wchar_t *
0x10082a560  mov     r8d, r15d; int
0x10082a563  mov     rdx, rbp; char *
0x10082a566  call    ?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z; FastDBCSToUnicode(uint,char const *,int,wchar_t *,int)
0x10082a56b  mov     r14d, eax
0x10082a56e  lea     r15d, [rax+rax]
0x10082a572  mov     rbp, r13
0x10082a575  mov     r8, [rsp+98h+var_40]
0x10082a57a  lea     r13, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10082a581  cmp     edi, 808h
0x10082a587  jnz     short loc_10082A600
0x10082a589  movsxd  rcx, r14d
0x10082a58c  test    r14d, r14d
0x10082a58f  jle     short loc_10082A5B5
0x10082a591  lea     rax, ds:0FFFFFFFFFFFFFFFEh[rcx*2]
0x10082a599  add     rax, rbp
0x10082a59c  nop     dword ptr [rax+00h]
0x10082a5a0  cmp     word ptr [rax], 20h ; ' '
0x10082a5a4  jnz     short loc_10082A5B5
0x10082a5a6  dec     r14d
0x10082a5a9  dec     rcx
0x10082a5ac  sub     rax, 2
0x10082a5b0  test    rcx, rcx
0x10082a5b3  jg      short loc_10082A5A0
0x10082a5b5  lea     r8d, [r14+r14]
0x10082a5b9  test    r8d, r8d
0x10082a5bc  jle     loc_10082A856
0x10082a5c2  nop     dword ptr [rax+00h]
0x10082a5c6  nop     word ptr [rax+rax+00000000h]
0x10082a5d0  mov     edx, [r12]
0x10082a5d4  mov     ecx, edx
0x10082a5d6  movzx   eax, byte ptr [rbp+0]
0x10082a5da  xor     rcx, rax
0x10082a5dd  movzx   eax, cl
0x10082a5e0  shr     edx, 8
0x10082a5e3  xor     edx, ds:rva dword_10089EAC0[r13+rax*4]; CTypeInfo const CTypeInfo::tiBit ...
0x10082a5eb  mov     [r12], edx
0x10082a5ef  lea     rbp, [rbp+1]
0x10082a5f3  dec     r8d
0x10082a5f6  test    r8d, r8d
0x10082a5f9  jg      short loc_10082A5D0
0x10082a5fb  jmp     loc_10082A856
0x10082a600  test    edi, 10800h
0x10082a606  jnz     loc_10082A6F1
0x10082a60c  mov     eax, edi
0x10082a60e  shr     eax, 18h
0x10082a611  test    al, al
0x10082a613  jnz     loc_10082A722
0x10082a619  mov     ecx, edi
0x10082a61b  shr     ecx, 0Ch
0x10082a61e  and     ecx, 1
0x10082a621  mov     eax, edi
0x10082a623  mov     edx, ecx
0x10082a625  or      edx, 2
0x10082a628  and     eax, 2000h
0x10082a62d  cmovz   edx, ecx
0x10082a630  mov     eax, edi
0x10082a632  mov     ecx, edx
0x10082a634  bts     ecx, 10h
0x10082a638  and     eax, 4000h
0x10082a63d  cmovz   ecx, edx
0x10082a640  mov     eax, edi
0x10082a642  mov     r15d, ecx
0x10082a645  bts     r15d, 11h
0x10082a64a  and     eax, 8000h
0x10082a64f  cmovz   r15d, ecx
0x10082a653  bt      edi, 9
0x10082a657  jnb     short loc_10082A65D
0x10082a659  or      r15d, 8
0x10082a65d  and     r8d, 7Fh
0x10082a661  shl     r8, 5
0x10082a665  or      r15d, 80000400h
0x10082a66c  shr     edi, 11h
0x10082a66f  and     edi, 7Fh
0x10082a672  jz      short loc_10082A6A2
0x10082a674  sub     edi, 1
0x10082a677  jz      short loc_10082A699
0x10082a679  sub     edi, 1
0x10082a67c  jz      short loc_10082A690
0x10082a67e  cmp     edi, 1
0x10082a681  jnz     loc_10082A7E0
0x10082a687  lea     rdi, ?x_SqlSortManager_140@@3VCSqlSortManager_140@@A; CSqlSortManager_140 x_SqlSortManager_140
0x10082a68e  jmp     short loc_10082A6A9
0x10082a690  lea     rdi, ?x_SqlSortManager_100@@3VCSqlSortManager_100@@A; CSqlSortManager_100 x_SqlSortManager_100
0x10082a697  jmp     short loc_10082A6A9
0x10082a699  lea     rdi, ?x_SqlSortManager_90@@3VCSqlSortManager_90@@A; CSqlSortManager_90 x_SqlSortManager_90
0x10082a6a0  jmp     short loc_10082A6A9
0x10082a6a2  lea     rdi, ?x_SqlSortManager_80@@3VCSqlSortManager_80@@A; CSqlSortManager_80 x_SqlSortManager_80
0x10082a6a9  mov     rax, [rdi]
0x10082a6ac  mov     edx, [r8+r13+456AA0h]
0x10082a6b4  mov     rcx, rdi
0x10082a6b7  call    qword ptr [rax+8]
0x10082a6ba  test    rax, rax
0x10082a6bd  jz      loc_10082A7E0
0x10082a6c3  mov     r10, [rdi]
0x10082a6c6  mov     [rsp+98h+var_68], esi
0x10082a6ca  lea     rcx, [rsp+98h+arg_18]
0x10082a6d2  mov     [rsp+98h+var_70], rcx
0x10082a6d7  mov     [rsp+98h+var_78], r14d
0x10082a6dc  mov     r9, rbp
0x10082a6df  mov     r8d, r15d
0x10082a6e2  mov     rdx, rax
0x10082a6e5  mov     rcx, rdi
0x10082a6e8  call    qword ptr [r10+58h]
0x10082a6ec  jmp     loc_10082A7E0
0x10082a6f1  shr     edi, 18h
0x10082a6f4  test    dil, dil
0x10082a6f7  jz      short loc_10082A760
0x10082a6f9  cmp     edi, 100h
0x10082a6ff  jnb     short loc_10082A722
0x10082a701  movzx   eax, dil
0x10082a705  lea     rcx, [rax+rax*4]
0x10082a709  cmp     ds:rva ?x_rgSortOrderMap@@3QBUSSortOrderMapItem@@B[r13+rcx*8], 0; CTypeInfo const CTypeInfo::tiBit
0x10082a712  jz      short loc_10082A722
0x10082a714  test    ds:rva dword_10085C9D8[r13+rcx*8], 10800h; CTypeInfo const CTypeInfo::tiBit ...
0x10082a720  jnz     short loc_10082A760
0x10082a722  mov     [rsp+98h+var_58], esi
0x10082a726  mov     [rsp+98h+var_60], 0
0x10082a72b  mov     [rsp+98h+var_68], r15d
0x10082a730  mov     [rsp+98h+var_70], rbp
0x10082a735  mov     rax, [rsp+98h+arg_20]
0x10082a73d  mov     qword ptr [rsp+98h+var_78], rax
0x10082a742  mov     r9d, [rax+50h]
0x10082a746  mov     r8, [rax+48h]
0x10082a74a  mov     edx, [rax+54h]
0x10082a74d  mov     rcx, [rax+40h]
0x10082a751  call    qword ptr [rax+60h]
0x10082a754  mov     [rsp+98h+arg_18], eax
0x10082a75b  jmp     loc_10082A7E0
0x10082a760  movsxd  rcx, r15d
0x10082a763  shr     rcx, 1
0x10082a766  movsxd  rax, ecx
0x10082a769  lea     rdx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x10082a771  add     rdx, rbp
0x10082a774  test    ecx, ecx
0x10082a776  jz      short loc_10082A7D9
0x10082a778  mov     r8d, 20h ; ' '
0x10082a77e  mov     r9d, 3000h
0x10082a784  movzx   eax, word ptr [rdx]
0x10082a787  cmp     r8w, ax
0x10082a78b  jz      short loc_10082A793
0x10082a78d  cmp     r9w, ax
0x10082a791  jnz     short loc_10082A79E
0x10082a793  sub     rdx, 2
0x10082a797  sub     ecx, 1
0x10082a79a  jz      short loc_10082A7D9
0x10082a79c  jmp     short loc_10082A784
0x10082a79e  test    ecx, ecx
0x10082a7a0  jz      short loc_10082A7D9
0x10082a7a2  mov     eax, 0FFh
0x10082a7a7  cmp     ecx, eax
0x10082a7a9  cmovl   eax, ecx
0x10082a7ac  movsxd  r8, eax
0x10082a7af  test    eax, eax
0x10082a7b1  jle     short loc_10082A7D9
0x10082a7b3  mov     rdx, rsi
0x10082a7b6  nop     word ptr [rax+rax+00000000h]
0x10082a7c0  mov     ecx, esi
0x10082a7c2  shr     ecx, 1Ch
0x10082a7c5  movzx   eax, word ptr [rbp+rdx*2+0]
0x10082a7ca  shl     esi, 4
0x10082a7cd  xor     esi, eax
0x10082a7cf  xor     esi, ecx
0x10082a7d1  inc     rdx
0x10082a7d4  cmp     rdx, r8
0x10082a7d7  jl      short loc_10082A7C0
0x10082a7d9  mov     [rsp+98h+arg_18], esi
0x10082a7e0  mov     r8d, [r12]
0x10082a7e4  movsxd  rdx, [rsp+98h+arg_18]
0x10082a7ec  mov     eax, r8d
0x10082a7ef  xor     rax, rdx
0x10082a7f2  movzx   ecx, al
0x10082a7f5  shr     r8d, 8
0x10082a7f9  xor     r8d, ds:rva dword_10089EAC0[r13+rcx*4]; CTypeInfo const CTypeInfo::tiBit ...
0x10082a801  mov     rcx, rdx
0x10082a804  sar     rcx, 8
0x10082a808  mov     eax, r8d
0x10082a80b  xor     rcx, rax
0x10082a80e  movzx   eax, cl
0x10082a811  shr     r8d, 8
0x10082a815  xor     r8d, ds:rva dword_10089EAC0[r13+rax*4]; CTypeInfo const CTypeInfo::tiBit ...
0x10082a81d  mov     rcx, rdx
0x10082a820  sar     rcx, 10h
0x10082a824  mov     eax, r8d
0x10082a827  xor     rcx, rax
0x10082a82a  movzx   eax, cl
0x10082a82d  shr     r8d, 8
0x10082a831  xor     r8d, ds:rva dword_10089EAC0[r13+rax*4]; CTypeInfo const CTypeInfo::tiBit ...
0x10082a839  sar     rdx, 18h
0x10082a83d  mov     eax, r8d
0x10082a840  xor     rdx, rax
0x10082a843  movzx   eax, dl
0x10082a846  shr     r8d, 8
0x10082a84a  xor     r8d, ds:rva dword_10089EAC0[r13+rax*4]; CTypeInfo const CTypeInfo::tiBit ...
0x10082a852  mov     [r12], r8d
0x10082a856  mov     rcx, rbx
0x10082a859  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10082a85f  lea     r11, [rsp+98h+var_28]
0x10082a864  mov     rbx, [r11+30h]
0x10082a868  mov     rbp, [r11+38h]
0x10082a86c  mov     rsi, [r11+40h]
0x10082a870  mov     rsp, r11
0x10082a873  pop     r15
0x10082a875  pop     r14
0x10082a877  pop     r13
0x10082a879  pop     r12
0x10082a87b  pop     rdi
0x10082a87c  retn
```
