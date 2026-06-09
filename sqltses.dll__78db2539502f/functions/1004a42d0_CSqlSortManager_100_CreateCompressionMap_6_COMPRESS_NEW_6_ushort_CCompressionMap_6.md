# CSqlSortManager_100::CreateCompressionMap<6>(COMPRESS_NEW<6> *,ushort,CCompressionMap<6> * *)

- ea: `0x1004a42d0`
- end: `0x1004a4556`
- name: `??$CreateCompressionMap@$05@CSqlSortManager_100@@KAHPEAU?$COMPRESS_NEW@$05@@GPEAPEAV?$CCompressionMap@$05@@@Z`
- size: `646`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1004a2fe0`

## callees

- `0x1004011fc`
- `0x1004a37e0`
- `0x1004a42d0`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x1004a4536`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004a4536`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a433a`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a4393`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a44b9`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a433a`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a4393`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a44b9`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a4320`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a4379`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a449f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a4320`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a4379`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a449f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a452e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a452e`

## string_xrefs

- `0x1004a4333`: `sql\ntdbms\msql\sqlsort\common\sortutil.cpp`
- `0x1004a438c`: `sql\ntdbms\msql\sqlsort\common\sortutil.cpp`
- `0x1004a44b2`: `sql\ntdbms\msql\sqlsort\common\sortutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSqlSortManager_100::CreateCompressionMap<6>(__int64 a1, unsigned __int16 a2, __int64 *a3)
{
  int v3; // r12d
  __int64 v4; // r14
  __int64 result; // rax
  __int64 v6; // r15
  unsigned int v7; // esi
  void *v8; // rbx
  unsigned __int64 v9; // rcx
  void *v10; // rax
  unsigned __int16 i; // bp
  unsigned __int16 *v12; // r14
  int v13; // r13d
  unsigned int v14; // r8d
  unsigned int v15; // r8d
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned __int64 v18; // rdi
  _QWORD *v19; // rax
  _QWORD *v20; // rax

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
      v9 = (unsigned int)(48 * v3);
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
        memset_0(v10, 0, (unsigned int)(48 * v3));
        *(_DWORD *)(v6 + 8) = 2 * v3;
        for ( i = 0; i < (unsigned __int16)v3; v4 = a1 )
        {
          v12 = (unsigned __int16 *)(16LL * i + v4);
          v13 = *((_DWORD *)v12 + 3);
          v14 = ((*v12 >> 2) + 2080 * *v12 + v12[1]) ^ *v12;
          v15 = ((v14 >> 2) + 2080 * v14 + v12[2]) ^ v14;
          v16 = ((v15 >> 2) + 2080 * v15 + v12[3]) ^ v15;
          v17 = ((v16 >> 2) + 2080 * v16 + v12[4]) ^ v16;
          v18 = *(_QWORD *)v6
              + 24 * ((v17 ^ (unsigned __int64)(2080 * v17 + v12[5] + (v17 >> 2))) % *(unsigned int *)(v6 + 8));
          if ( *(_DWORD *)(v18 + 8) )
          {
            v19 = *(_QWORD **)v18;
            if ( *(_QWORD *)v18 )
            {
              do
              {
                v18 = (unsigned __int64)v19;
                v19 = (_QWORD *)*v19;
              }
              while ( v19 );
            }
            if ( CSqlSortUtil::m_pmoSqlSort )
              v20 = operator new[](
                      0x18u,
                      CSqlSortUtil::m_pmoSqlSort,
                      "sql\\ntdbms\\msql\\sqlsort\\common\\sortutil.cpp",
                      139,
                      6u);
            else
              v20 = malloc(0x18u);
            *(_QWORD *)v18 = v20;
            if ( !v20 )
              goto LABEL_22;
            v18 = (unsigned __int64)v20;
            *v20 = 0;
          }
          *(_DWORD *)(v18 + 8) = v13;
          *(_QWORD *)(v18 + 12) = *(_QWORD *)v12;
          *(_DWORD *)(v18 + 20) = *((_DWORD *)v12 + 2);
          ++i;
        }
        v8 = 0;
        *a3 = v6;
        v7 = 1;
      }
LABEL_22:
      if ( v8 )
      {
        CCompressionMap<6>::`scalar deleting destructor'(v8, 0);
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
0x1004a42d0  mov     rax, rsp
0x1004a42d3  mov     [rax+18h], r8
0x1004a42d7  mov     [rax+8], rcx
0x1004a42db  push    rbp
0x1004a42dc  push    rsi
0x1004a42dd  push    rdi
0x1004a42de  push    r12
0x1004a42e0  push    r13
0x1004a42e2  push    r14
0x1004a42e4  push    r15
0x1004a42e6  sub     rsp, 40h
0x1004a42ea  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x1004a42f2  mov     [rax+10h], rbx
0x1004a42f6  movzx   r12d, dx
0x1004a42fa  mov     r14, rcx
0x1004a42fd  test    rcx, rcx
0x1004a4300  jnz     short loc_1004A430F
0x1004a4302  xor     esi, esi
0x1004a4304  mov     [r8], rsi
0x1004a4307  lea     eax, [rcx+1]
0x1004a430a  jmp     loc_1004A453E
0x1004a430f  mov     rdx, cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a4316  mov     ecx, 10h; Size
0x1004a431b  test    rdx, rdx
0x1004a431e  jnz     short loc_1004A4328
0x1004a4320  call    cs:__imp_malloc
0x1004a4326  jmp     short loc_1004A4340
0x1004a4328  mov     [rsp+78h+var_58], 6
0x1004a432d  mov     r9d, 8Bh
0x1004a4333  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sqlsort\\common\\sor"...
0x1004a433a  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004a4340  mov     r15, rax
0x1004a4343  test    rax, rax
0x1004a4346  jz      loc_1004A453E
0x1004a434c  xor     esi, esi
0x1004a434e  mov     [r15], rsi
0x1004a4351  mov     [r15+8], esi
0x1004a4355  mov     rbx, r15
0x1004a4358  mov     [rsp+78h+arg_18], rbx
0x1004a4360  mov     edi, r12d
0x1004a4363  add     edi, edi
0x1004a4365  lea     ebp, [rdi+rdi*2]
0x1004a4368  shl     ebp, 3
0x1004a436b  mov     rdx, cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a4372  mov     ecx, ebp; Size
0x1004a4374  test    rdx, rdx
0x1004a4377  jnz     short loc_1004A4381
0x1004a4379  call    cs:__imp_malloc
0x1004a437f  jmp     short loc_1004A4399
0x1004a4381  mov     [rsp+78h+var_58], 6
0x1004a4386  mov     r9d, 8Bh
0x1004a438c  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sqlsort\\common\\sor"...
0x1004a4393  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004a4399  mov     [r15], rax
0x1004a439c  test    rax, rax
0x1004a439f  jz      loc_1004A4512
0x1004a43a5  mov     r8, rbp; Size
0x1004a43a8  xor     edx, edx; Val
0x1004a43aa  mov     rcx, rax; void *
0x1004a43ad  call    memset_0
0x1004a43b2  mov     [r15+8], edi
0x1004a43b6  movzx   ebp, si
0x1004a43b9  cmp     si, r12w
0x1004a43bd  jnb     loc_1004A44F7
0x1004a43c3  nop     dword ptr [rax+00h]
0x1004a43c7  nop     word ptr [rax+rax+00000000h]
0x1004a43d0  movzx   eax, bp
0x1004a43d3  shl     rax, 4
0x1004a43d7  add     r14, rax
0x1004a43da  mov     r13d, [r14+0Ch]
0x1004a43de  movzx   r8d, word ptr [r14]
0x1004a43e2  movzx   ecx, word ptr [r14+2]
0x1004a43e7  imul    eax, r8d, 820h
0x1004a43ee  add     ecx, eax
0x1004a43f0  mov     eax, r8d
0x1004a43f3  shr     eax, 2
0x1004a43f6  add     ecx, eax
0x1004a43f8  xor     r8d, ecx
0x1004a43fb  movzx   ecx, word ptr [r14+4]
0x1004a4400  imul    eax, r8d, 820h
0x1004a4407  add     ecx, eax
0x1004a4409  mov     eax, r8d
0x1004a440c  shr     eax, 2
0x1004a440f  add     ecx, eax
0x1004a4411  xor     r8d, ecx
0x1004a4414  movzx   ecx, word ptr [r14+6]
0x1004a4419  imul    eax, r8d, 820h
0x1004a4420  add     ecx, eax
0x1004a4422  mov     eax, r8d
0x1004a4425  shr     eax, 2
0x1004a4428  add     ecx, eax
0x1004a442a  xor     r8d, ecx
0x1004a442d  movzx   ecx, word ptr [r14+8]
0x1004a4432  imul    eax, r8d, 820h
0x1004a4439  add     ecx, eax
0x1004a443b  mov     eax, r8d
0x1004a443e  shr     eax, 2
0x1004a4441  add     ecx, eax
0x1004a4443  xor     r8d, ecx
0x1004a4446  movzx   ecx, word ptr [r14+0Ah]
0x1004a444b  imul    eax, r8d, 820h
0x1004a4452  add     ecx, eax
0x1004a4454  mov     eax, r8d
0x1004a4457  shr     eax, 2
0x1004a445a  add     eax, ecx
0x1004a445c  xor     eax, r8d
0x1004a445f  xor     edx, edx
0x1004a4461  div     dword ptr [r15+8]
0x1004a4465  lea     rdx, [rdx+rdx*2]
0x1004a4469  mov     rax, [r15]
0x1004a446c  lea     rdi, [rax+rdx*8]
0x1004a4470  cmp     dword ptr [rdi+8], 0
0x1004a4474  jz      short loc_1004A44CD
0x1004a4476  mov     rax, [rdi]
0x1004a4479  test    rax, rax
0x1004a447c  jz      short loc_1004A448E
0x1004a447e  nop
0x1004a447f  nop
0x1004a4480  mov     rdi, rax
0x1004a4483  mov     rcx, [rax]
0x1004a4486  mov     rax, rcx
0x1004a4489  test    rcx, rcx
0x1004a448c  jnz     short loc_1004A4480
0x1004a448e  mov     rdx, cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a4495  mov     ecx, 18h; Size
0x1004a449a  test    rdx, rdx
0x1004a449d  jnz     short loc_1004A44A7
0x1004a449f  call    cs:__imp_malloc
0x1004a44a5  jmp     short loc_1004A44BF
0x1004a44a7  mov     [rsp+78h+var_58], 6
0x1004a44ac  mov     r9d, 8Bh
0x1004a44b2  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sqlsort\\common\\sor"...
0x1004a44b9  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004a44bf  mov     [rdi], rax
0x1004a44c2  test    rax, rax
0x1004a44c5  jz      short loc_1004A4512
0x1004a44c7  mov     rdi, rax
0x1004a44ca  mov     [rax], rsi
0x1004a44cd  mov     [rdi+8], r13d
0x1004a44d1  movsd   xmm0, qword ptr [r14]
0x1004a44d6  movsd   qword ptr [rdi+0Ch], xmm0
0x1004a44db  mov     eax, [r14+8]
0x1004a44df  mov     [rdi+14h], eax
0x1004a44e2  inc     bp
0x1004a44e5  cmp     bp, r12w
0x1004a44e9  mov     r14, [rsp+78h+arg_0]
0x1004a44f1  jb      loc_1004A43D0
0x1004a44f7  mov     rbx, rsi
0x1004a44fa  mov     [rsp+78h+arg_18], rbx
0x1004a4502  mov     rax, [rsp+78h+arg_10]
0x1004a450a  mov     [rax], r15
0x1004a450d  mov     esi, 1
0x1004a4512  test    rbx, rbx
0x1004a4515  jz      short loc_1004A453C
0x1004a4517  xor     edx, edx
0x1004a4519  mov     rcx, rbx
0x1004a451c  call    ??_G?$CCompressionMap@$05@@QEAAPEAXI@Z; CCompressionMap<6>::`scalar deleting destructor'(uint)
0x1004a4521  mov     rcx, rbx; Block
0x1004a4524  cmp     cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA, 0; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a452c  jnz     short loc_1004A4536
0x1004a452e  call    cs:__imp_free
0x1004a4534  jmp     short loc_1004A453C
0x1004a4536  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1004a453c  mov     eax, esi
0x1004a453e  mov     rbx, [rsp+78h+arg_8]
0x1004a4546  add     rsp, 40h
0x1004a454a  pop     r15
0x1004a454c  pop     r14
0x1004a454e  pop     r13
0x1004a4550  pop     r12
0x1004a4552  pop     rdi
0x1004a4553  pop     rsi
0x1004a4554  pop     rbp
0x1004a4555  retn
```
