# CSqlSortManager_100::CreateCompressionMap<7>(COMPRESS_NEW<7> *,ushort,CCompressionMap<7> * *)

- ea: `0x1004a4560`
- end: `0x1004a480e`
- name: `??$CreateCompressionMap@$06@CSqlSortManager_100@@KAHPEAU?$COMPRESS_NEW@$06@@GPEAPEAV?$CCompressionMap@$06@@@Z`
- size: `686`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1004a2fe0`

## callees

- `0x1004011fc`
- `0x1004a3710`
- `0x1004a4560`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x1004a47ee`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004a47ee`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a45ca`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a4622`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a4769`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a45ca`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a4622`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a4769`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a45b0`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a4608`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a474f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a45b0`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a4608`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a474f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a47e6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a47e6`

## string_xrefs

- `0x1004a45c3`: `sql\ntdbms\msql\sqlsort\common\sortutil.cpp`
- `0x1004a461b`: `sql\ntdbms\msql\sqlsort\common\sortutil.cpp`
- `0x1004a4762`: `sql\ntdbms\msql\sqlsort\common\sortutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSqlSortManager_100::CreateCompressionMap<7>(__int64 a1, unsigned __int16 a2, __int64 *a3)
{
  int v3; // r12d
  __int64 v4; // r13
  __int64 result; // rax
  __int64 v6; // r15
  unsigned int v7; // esi
  void *v8; // rbx
  unsigned __int64 v9; // rcx
  void *v10; // rax
  unsigned __int16 i; // r14
  unsigned __int16 *v12; // rbp
  int v13; // r13d
  unsigned int v14; // r8d
  unsigned int v15; // r8d
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  unsigned __int64 v19; // rdi
  _QWORD *v20; // rax
  _QWORD *v21; // rax

  v3 = a2;
  v4 = a1;
  if ( a1 )
  {
    if ( CSqlSortUtil::m_pmoSqlSort )
      result = (__int64)operator new[](
                          0x10u,
                          CSqlSortUtil::m_pmoSqlSort,
                          "sql\\ntdbms\\msql\\sqlsort\\common\\sortutil.cpp",
                          139,
                          6u);
    else
      result = (__int64)malloc(0x10u);
    v6 = result;
    if ( result )
    {
      v7 = 0;
      *(_QWORD *)result = 0;
      *(_DWORD *)(result + 8) = 0;
      v8 = (void *)result;
      v9 = (unsigned int)(v3 << 6);
      if ( CSqlSortUtil::m_pmoSqlSort )
        v10 = operator new[](
                v9,
                CSqlSortUtil::m_pmoSqlSort,
                "sql\\ntdbms\\msql\\sqlsort\\common\\sortutil.cpp",
                139,
                6u);
      else
        v10 = malloc(v9);
      *(_QWORD *)v6 = v10;
      if ( v10 )
      {
        memset_0(v10, 0, (unsigned int)(v3 << 6));
        *(_DWORD *)(v6 + 8) = 2 * v3;
        for ( i = 0; i < (unsigned __int16)v3; v4 = a1 )
        {
          v12 = (unsigned __int16 *)(v4 + 18LL * i);
          v13 = *(_DWORD *)(v12 + 7);
          v14 = ((*v12 >> 2) + 2080 * *v12 + v12[1]) ^ *v12;
          v15 = ((v14 >> 2) + 2080 * v14 + v12[2]) ^ v14;
          v16 = ((v15 >> 2) + 2080 * v15 + v12[3]) ^ v15;
          v17 = ((v16 >> 2) + 2080 * v16 + v12[4]) ^ v16;
          v18 = ((v17 >> 2) + 2080 * v17 + v12[5]) ^ v17;
          v19 = *(_QWORD *)v6
              + 32 * ((v18 ^ (unsigned __int64)(2080 * v18 + v12[6] + (v18 >> 2))) % *(unsigned int *)(v6 + 8));
          if ( *(_DWORD *)(v19 + 8) )
          {
            v20 = *(_QWORD **)v19;
            if ( *(_QWORD *)v19 )
            {
              do
              {
                v19 = (unsigned __int64)v20;
                v20 = (_QWORD *)*v20;
              }
              while ( v20 );
            }
            if ( CSqlSortUtil::m_pmoSqlSort )
              v21 = operator new[](
                      0x20u,
                      CSqlSortUtil::m_pmoSqlSort,
                      "sql\\ntdbms\\msql\\sqlsort\\common\\sortutil.cpp",
                      139,
                      6u);
            else
              v21 = malloc(0x20u);
            *(_QWORD *)v19 = v21;
            if ( !v21 )
              goto LABEL_22;
            v19 = (unsigned __int64)v21;
            *v21 = 0;
          }
          *(_DWORD *)(v19 + 8) = v13;
          *(_QWORD *)(v19 + 12) = *(_QWORD *)v12;
          *(_DWORD *)(v19 + 20) = *((_DWORD *)v12 + 2);
          *(_WORD *)(v19 + 24) = v12[6];
          ++i;
        }
        v8 = 0;
        *a3 = v6;
        v7 = 1;
      }
LABEL_22:
      if ( v8 )
      {
        CCompressionMap<8>::`scalar deleting destructor'(v8, 0);
        if ( CSqlSortUtil::m_pmoSqlSort )
          operator delete[](v8);
        else
          free(v8);
      }
      return v7;
    }
  }
  else
  {
    *a3 = 0;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x1004a4560  mov     rax, rsp
0x1004a4563  mov     [rax+18h], r8
0x1004a4567  mov     [rax+8], rcx
0x1004a456b  push    rbp
0x1004a456c  push    rsi
0x1004a456d  push    rdi
0x1004a456e  push    r12
0x1004a4570  push    r13
0x1004a4572  push    r14
0x1004a4574  push    r15
0x1004a4576  sub     rsp, 40h
0x1004a457a  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x1004a4582  mov     [rax+10h], rbx
0x1004a4586  movzx   r12d, dx
0x1004a458a  mov     r13, rcx
0x1004a458d  test    rcx, rcx
0x1004a4590  jnz     short loc_1004A459F
0x1004a4592  xor     esi, esi
0x1004a4594  mov     [r8], rsi
0x1004a4597  lea     eax, [rcx+1]
0x1004a459a  jmp     loc_1004A47F6
0x1004a459f  mov     rdx, cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a45a6  mov     ecx, 10h; Size
0x1004a45ab  test    rdx, rdx
0x1004a45ae  jnz     short loc_1004A45B8
0x1004a45b0  call    cs:__imp_malloc
0x1004a45b6  jmp     short loc_1004A45D0
0x1004a45b8  mov     [rsp+78h+var_58], 6
0x1004a45bd  mov     r9d, 8Bh
0x1004a45c3  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sqlsort\\common\\sor"...
0x1004a45ca  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004a45d0  mov     r15, rax
0x1004a45d3  test    rax, rax
0x1004a45d6  jz      loc_1004A47F6
0x1004a45dc  xor     esi, esi
0x1004a45de  mov     [r15], rsi
0x1004a45e1  mov     [r15+8], esi
0x1004a45e5  mov     rbx, r15
0x1004a45e8  mov     [rsp+78h+arg_18], rbx
0x1004a45f0  mov     edi, r12d
0x1004a45f3  add     edi, edi
0x1004a45f5  mov     ebp, edi
0x1004a45f7  shl     ebp, 5
0x1004a45fa  mov     rdx, cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a4601  mov     ecx, ebp; Size
0x1004a4603  test    rdx, rdx
0x1004a4606  jnz     short loc_1004A4610
0x1004a4608  call    cs:__imp_malloc
0x1004a460e  jmp     short loc_1004A4628
0x1004a4610  mov     [rsp+78h+var_58], 6
0x1004a4615  mov     r9d, 8Bh
0x1004a461b  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sqlsort\\common\\sor"...
0x1004a4622  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004a4628  mov     [r15], rax
0x1004a462b  test    rax, rax
0x1004a462e  jz      loc_1004A47CA
0x1004a4634  mov     r8, rbp; Size
0x1004a4637  xor     edx, edx; Val
0x1004a4639  mov     rcx, rax; void *
0x1004a463c  call    memset_0
0x1004a4641  mov     [r15+8], edi
0x1004a4645  movzx   r14d, si
0x1004a4649  cmp     si, r12w
0x1004a464d  jnb     loc_1004A47AF
0x1004a4653  nop     dword ptr [rax+00h]
0x1004a4657  nop     word ptr [rax+rax+00000000h]
0x1004a4660  movzx   eax, r14w
0x1004a4664  lea     rcx, [rax+rax*8]
0x1004a4668  lea     rbp, ds:0[rcx*2]
0x1004a4670  add     rbp, r13
0x1004a4673  mov     r13d, [rbp+0Eh]
0x1004a4677  movzx   r8d, word ptr [rbp+0]
0x1004a467c  movzx   ecx, word ptr [rbp+2]
0x1004a4680  imul    eax, r8d, 820h
0x1004a4687  add     ecx, eax
0x1004a4689  mov     eax, r8d
0x1004a468c  shr     eax, 2
0x1004a468f  add     ecx, eax
0x1004a4691  xor     r8d, ecx
0x1004a4694  movzx   ecx, word ptr [rbp+4]
0x1004a4698  imul    eax, r8d, 820h
0x1004a469f  add     ecx, eax
0x1004a46a1  mov     eax, r8d
0x1004a46a4  shr     eax, 2
0x1004a46a7  add     ecx, eax
0x1004a46a9  xor     r8d, ecx
0x1004a46ac  movzx   ecx, word ptr [rbp+6]
0x1004a46b0  imul    eax, r8d, 820h
0x1004a46b7  add     ecx, eax
0x1004a46b9  mov     eax, r8d
0x1004a46bc  shr     eax, 2
0x1004a46bf  add     ecx, eax
0x1004a46c1  xor     r8d, ecx
0x1004a46c4  movzx   ecx, word ptr [rbp+8]
0x1004a46c8  imul    eax, r8d, 820h
0x1004a46cf  add     ecx, eax
0x1004a46d1  mov     eax, r8d
0x1004a46d4  shr     eax, 2
0x1004a46d7  add     ecx, eax
0x1004a46d9  xor     r8d, ecx
0x1004a46dc  movzx   ecx, word ptr [rbp+0Ah]
0x1004a46e0  imul    eax, r8d, 820h
0x1004a46e7  add     ecx, eax
0x1004a46e9  mov     eax, r8d
0x1004a46ec  shr     eax, 2
0x1004a46ef  add     ecx, eax
0x1004a46f1  xor     r8d, ecx
0x1004a46f4  movzx   ecx, word ptr [rbp+0Ch]
0x1004a46f8  imul    eax, r8d, 820h
0x1004a46ff  add     ecx, eax
0x1004a4701  mov     eax, r8d
0x1004a4704  shr     eax, 2
0x1004a4707  add     eax, ecx
0x1004a4709  xor     eax, r8d
0x1004a470c  xor     edx, edx
0x1004a470e  div     dword ptr [r15+8]
0x1004a4712  mov     edi, edx
0x1004a4714  shl     rdi, 5
0x1004a4718  add     rdi, [r15]
0x1004a471b  cmp     dword ptr [rdi+8], 0
0x1004a471f  jz      short loc_1004A477D
0x1004a4721  mov     rax, [rdi]
0x1004a4724  test    rax, rax
0x1004a4727  jz      short loc_1004A473E
0x1004a4729  nop     dword ptr [rax]
0x1004a472c  nop     dword ptr [rax+00h]
0x1004a4730  mov     rdi, rax
0x1004a4733  mov     rcx, [rax]
0x1004a4736  mov     rax, rcx
0x1004a4739  test    rcx, rcx
0x1004a473c  jnz     short loc_1004A4730
0x1004a473e  mov     rdx, cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a4745  mov     ecx, 20h ; ' '; Size
0x1004a474a  test    rdx, rdx
0x1004a474d  jnz     short loc_1004A4757
0x1004a474f  call    cs:__imp_malloc
0x1004a4755  jmp     short loc_1004A476F
0x1004a4757  mov     [rsp+78h+var_58], 6
0x1004a475c  mov     r9d, 8Bh
0x1004a4762  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sqlsort\\common\\sor"...
0x1004a4769  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004a476f  mov     [rdi], rax
0x1004a4772  test    rax, rax
0x1004a4775  jz      short loc_1004A47CA
0x1004a4777  mov     rdi, rax
0x1004a477a  mov     [rax], rsi
0x1004a477d  mov     [rdi+8], r13d
0x1004a4781  movsd   xmm0, qword ptr [rbp+0]
0x1004a4786  movsd   qword ptr [rdi+0Ch], xmm0
0x1004a478b  mov     eax, [rbp+8]
0x1004a478e  mov     [rdi+14h], eax
0x1004a4791  movzx   eax, word ptr [rbp+0Ch]
0x1004a4795  mov     [rdi+18h], ax
0x1004a4799  inc     r14w
0x1004a479d  cmp     r14w, r12w
0x1004a47a1  mov     r13, [rsp+78h+arg_0]
0x1004a47a9  jb      loc_1004A4660
0x1004a47af  mov     rbx, rsi
0x1004a47b2  mov     [rsp+78h+arg_18], rbx
0x1004a47ba  mov     rax, [rsp+78h+arg_10]
0x1004a47c2  mov     [rax], r15
0x1004a47c5  mov     esi, 1
0x1004a47ca  test    rbx, rbx
0x1004a47cd  jz      short loc_1004A47F4
0x1004a47cf  xor     edx, edx
0x1004a47d1  mov     rcx, rbx
0x1004a47d4  call    ??_G?$CCompressionMap@$07@@QEAAPEAXI@Z; CCompressionMap<8>::`scalar deleting destructor'(uint)
0x1004a47d9  mov     rcx, rbx; Block
0x1004a47dc  cmp     cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA, 0; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a47e4  jnz     short loc_1004A47EE
0x1004a47e6  call    cs:__imp_free
0x1004a47ec  jmp     short loc_1004A47F4
0x1004a47ee  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1004a47f4  mov     eax, esi
0x1004a47f6  mov     rbx, [rsp+78h+arg_8]
0x1004a47fe  add     rsp, 40h
0x1004a4802  pop     r15
0x1004a4804  pop     r14
0x1004a4806  pop     r13
0x1004a4808  pop     r12
0x1004a480a  pop     rdi
0x1004a480b  pop     rsi
0x1004a480c  pop     rbp
0x1004a480d  retn
```
