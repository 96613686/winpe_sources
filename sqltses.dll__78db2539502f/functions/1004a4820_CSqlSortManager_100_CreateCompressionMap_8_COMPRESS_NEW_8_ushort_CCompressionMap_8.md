# CSqlSortManager_100::CreateCompressionMap<8>(COMPRESS_NEW<8> *,ushort,CCompressionMap<8> * *)

- ea: `0x1004a4820`
- end: `0x1004a4acd`
- name: `??$CreateCompressionMap@$07@CSqlSortManager_100@@KAHPEAU?$COMPRESS_NEW@$07@@GPEAPEAV?$CCompressionMap@$07@@@Z`
- size: `685`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1004a2fe0`

## callees

- `0x1004011fc`
- `0x1004a3710`
- `0x1004a4820`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x1004a4aad`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004a4aad`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a488a`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a48e2`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a4a39`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a488a`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a48e2`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a4a39`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a4870`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a48c8`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a4a1f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a4870`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a48c8`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a4a1f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a4aa5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a4aa5`

## string_xrefs

- `0x1004a4883`: `sql\ntdbms\msql\sqlsort\common\sortutil.cpp`
- `0x1004a48db`: `sql\ntdbms\msql\sqlsort\common\sortutil.cpp`
- `0x1004a4a32`: `sql\ntdbms\msql\sqlsort\common\sortutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSqlSortManager_100::CreateCompressionMap<8>(__int64 a1, unsigned __int16 a2, __int64 *a3)
{
  int v3; // r12d
  __int64 v4; // r15
  __int64 result; // rax
  __int64 v6; // r14
  unsigned int v7; // esi
  void *v8; // rbx
  unsigned __int64 v9; // rcx
  void *v10; // rax
  unsigned __int16 i; // bp
  unsigned __int16 *v12; // r15
  int v13; // r13d
  unsigned int v14; // r8d
  unsigned int v15; // r8d
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  unsigned int v19; // r8d
  unsigned __int64 v20; // rdi
  _QWORD *v21; // rax
  _QWORD *v22; // rax

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
          v12 = (unsigned __int16 *)(v4 + 20LL * i);
          v13 = *((_DWORD *)v12 + 4);
          v14 = ((*v12 >> 2) + 2080 * *v12 + v12[1]) ^ *v12;
          v15 = ((v14 >> 2) + 2080 * v14 + v12[2]) ^ v14;
          v16 = ((v15 >> 2) + 2080 * v15 + v12[3]) ^ v15;
          v17 = ((v16 >> 2) + 2080 * v16 + v12[4]) ^ v16;
          v18 = ((v17 >> 2) + 2080 * v17 + v12[5]) ^ v17;
          v19 = ((v18 >> 2) + 2080 * v18 + v12[6]) ^ v18;
          v20 = *(_QWORD *)v6
              + 32 * ((v19 ^ (unsigned __int64)(2080 * v19 + v12[7] + (v19 >> 2))) % *(unsigned int *)(v6 + 8));
          if ( *(_DWORD *)(v20 + 8) )
          {
            v21 = *(_QWORD **)v20;
            if ( *(_QWORD *)v20 )
            {
              do
              {
                v20 = (unsigned __int64)v21;
                v21 = (_QWORD *)*v21;
              }
              while ( v21 );
            }
            if ( CSqlSortUtil::m_pmoSqlSort )
              v22 = operator new[](
                      0x20u,
                      CSqlSortUtil::m_pmoSqlSort,
                      "sql\\ntdbms\\msql\\sqlsort\\common\\sortutil.cpp",
                      139,
                      6u);
            else
              v22 = malloc(0x20u);
            *(_QWORD *)v20 = v22;
            if ( !v22 )
              goto LABEL_22;
            v20 = (unsigned __int64)v22;
            *v22 = 0;
          }
          *(_DWORD *)(v20 + 8) = v13;
          *(_OWORD *)(v20 + 12) = *(_OWORD *)v12;
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
0x1004a4820  mov     rax, rsp
0x1004a4823  mov     [rax+18h], r8
0x1004a4827  mov     [rax+8], rcx
0x1004a482b  push    rbp
0x1004a482c  push    rsi
0x1004a482d  push    rdi
0x1004a482e  push    r12
0x1004a4830  push    r13
0x1004a4832  push    r14
0x1004a4834  push    r15
0x1004a4836  sub     rsp, 40h
0x1004a483a  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x1004a4842  mov     [rax+10h], rbx
0x1004a4846  movzx   r12d, dx
0x1004a484a  mov     r15, rcx
0x1004a484d  test    rcx, rcx
0x1004a4850  jnz     short loc_1004A485F
0x1004a4852  xor     esi, esi
0x1004a4854  mov     [r8], rsi
0x1004a4857  lea     eax, [rcx+1]
0x1004a485a  jmp     loc_1004A4AB5
0x1004a485f  mov     rdx, cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a4866  mov     ecx, 10h; Size
0x1004a486b  test    rdx, rdx
0x1004a486e  jnz     short loc_1004A4878
0x1004a4870  call    cs:__imp_malloc
0x1004a4876  jmp     short loc_1004A4890
0x1004a4878  mov     [rsp+78h+var_58], 6
0x1004a487d  mov     r9d, 8Bh
0x1004a4883  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sqlsort\\common\\sor"...
0x1004a488a  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004a4890  mov     r14, rax
0x1004a4893  test    rax, rax
0x1004a4896  jz      loc_1004A4AB5
0x1004a489c  xor     esi, esi
0x1004a489e  mov     [r14], rsi
0x1004a48a1  mov     [r14+8], esi
0x1004a48a5  mov     rbx, r14
0x1004a48a8  mov     [rsp+78h+arg_18], rbx
0x1004a48b0  mov     edi, r12d
0x1004a48b3  add     edi, edi
0x1004a48b5  mov     ebp, edi
0x1004a48b7  shl     ebp, 5
0x1004a48ba  mov     rdx, cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a48c1  mov     ecx, ebp; Size
0x1004a48c3  test    rdx, rdx
0x1004a48c6  jnz     short loc_1004A48D0
0x1004a48c8  call    cs:__imp_malloc
0x1004a48ce  jmp     short loc_1004A48E8
0x1004a48d0  mov     [rsp+78h+var_58], 6
0x1004a48d5  mov     r9d, 8Bh
0x1004a48db  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sqlsort\\common\\sor"...
0x1004a48e2  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004a48e8  mov     [r14], rax
0x1004a48eb  test    rax, rax
0x1004a48ee  jz      loc_1004A4A89
0x1004a48f4  mov     r8, rbp; Size
0x1004a48f7  xor     edx, edx; Val
0x1004a48f9  mov     rcx, rax; void *
0x1004a48fc  call    memset_0
0x1004a4901  mov     [r14+8], edi
0x1004a4905  movzx   ebp, si
0x1004a4908  cmp     si, r12w
0x1004a490c  jnb     loc_1004A4A6E
0x1004a4912  nop     dword ptr [rax+00h]
0x1004a4916  nop     word ptr [rax+rax+00000000h]
0x1004a4920  movzx   eax, bp
0x1004a4923  lea     rcx, [rax+rax*4]
0x1004a4927  lea     r15, [r15+rcx*4]
0x1004a492b  mov     r13d, [r15+10h]
0x1004a492f  movzx   r8d, word ptr [r15]
0x1004a4933  movzx   ecx, word ptr [r15+2]
0x1004a4938  imul    eax, r8d, 820h
0x1004a493f  add     ecx, eax
0x1004a4941  mov     eax, r8d
0x1004a4944  shr     eax, 2
0x1004a4947  add     ecx, eax
0x1004a4949  xor     r8d, ecx
0x1004a494c  movzx   ecx, word ptr [r15+4]
0x1004a4951  imul    eax, r8d, 820h
0x1004a4958  add     ecx, eax
0x1004a495a  mov     eax, r8d
0x1004a495d  shr     eax, 2
0x1004a4960  add     ecx, eax
0x1004a4962  xor     r8d, ecx
0x1004a4965  movzx   ecx, word ptr [r15+6]
0x1004a496a  imul    eax, r8d, 820h
0x1004a4971  add     ecx, eax
0x1004a4973  mov     eax, r8d
0x1004a4976  shr     eax, 2
0x1004a4979  add     ecx, eax
0x1004a497b  xor     r8d, ecx
0x1004a497e  movzx   ecx, word ptr [r15+8]
0x1004a4983  imul    eax, r8d, 820h
0x1004a498a  add     ecx, eax
0x1004a498c  mov     eax, r8d
0x1004a498f  shr     eax, 2
0x1004a4992  add     ecx, eax
0x1004a4994  xor     r8d, ecx
0x1004a4997  movzx   ecx, word ptr [r15+0Ah]
0x1004a499c  imul    eax, r8d, 820h
0x1004a49a3  add     ecx, eax
0x1004a49a5  mov     eax, r8d
0x1004a49a8  shr     eax, 2
0x1004a49ab  add     ecx, eax
0x1004a49ad  xor     r8d, ecx
0x1004a49b0  movzx   ecx, word ptr [r15+0Ch]
0x1004a49b5  imul    eax, r8d, 820h
0x1004a49bc  add     ecx, eax
0x1004a49be  mov     eax, r8d
0x1004a49c1  shr     eax, 2
0x1004a49c4  add     ecx, eax
0x1004a49c6  xor     r8d, ecx
0x1004a49c9  movzx   ecx, word ptr [r15+0Eh]
0x1004a49ce  imul    eax, r8d, 820h
0x1004a49d5  add     ecx, eax
0x1004a49d7  mov     eax, r8d
0x1004a49da  shr     eax, 2
0x1004a49dd  add     eax, ecx
0x1004a49df  xor     eax, r8d
0x1004a49e2  xor     edx, edx
0x1004a49e4  div     dword ptr [r14+8]
0x1004a49e8  mov     edi, edx
0x1004a49ea  shl     rdi, 5
0x1004a49ee  add     rdi, [r14]
0x1004a49f1  cmp     dword ptr [rdi+8], 0
0x1004a49f5  jz      short loc_1004A4A4D
0x1004a49f7  mov     rax, [rdi]
0x1004a49fa  test    rax, rax
0x1004a49fd  jz      short loc_1004A4A0E
0x1004a49ff  nop
0x1004a4a00  mov     rdi, rax
0x1004a4a03  mov     rcx, [rax]
0x1004a4a06  mov     rax, rcx
0x1004a4a09  test    rcx, rcx
0x1004a4a0c  jnz     short loc_1004A4A00
0x1004a4a0e  mov     rdx, cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a4a15  mov     ecx, 20h ; ' '; Size
0x1004a4a1a  test    rdx, rdx
0x1004a4a1d  jnz     short loc_1004A4A27
0x1004a4a1f  call    cs:__imp_malloc
0x1004a4a25  jmp     short loc_1004A4A3F
0x1004a4a27  mov     [rsp+78h+var_58], 6
0x1004a4a2c  mov     r9d, 8Bh
0x1004a4a32  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sqlsort\\common\\sor"...
0x1004a4a39  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004a4a3f  mov     [rdi], rax
0x1004a4a42  test    rax, rax
0x1004a4a45  jz      short loc_1004A4A89
0x1004a4a47  mov     rdi, rax
0x1004a4a4a  mov     [rax], rsi
0x1004a4a4d  mov     [rdi+8], r13d
0x1004a4a51  movups  xmm0, xmmword ptr [r15]
0x1004a4a55  movups  xmmword ptr [rdi+0Ch], xmm0
0x1004a4a59  inc     bp
0x1004a4a5c  cmp     bp, r12w
0x1004a4a60  mov     r15, [rsp+78h+arg_0]
0x1004a4a68  jb      loc_1004A4920
0x1004a4a6e  mov     rbx, rsi
0x1004a4a71  mov     [rsp+78h+arg_18], rbx
0x1004a4a79  mov     rax, [rsp+78h+arg_10]
0x1004a4a81  mov     [rax], r14
0x1004a4a84  mov     esi, 1
0x1004a4a89  test    rbx, rbx
0x1004a4a8c  jz      short loc_1004A4AB3
0x1004a4a8e  xor     edx, edx
0x1004a4a90  mov     rcx, rbx
0x1004a4a93  call    ??_G?$CCompressionMap@$07@@QEAAPEAXI@Z; CCompressionMap<8>::`scalar deleting destructor'(uint)
0x1004a4a98  mov     rcx, rbx; Block
0x1004a4a9b  cmp     cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA, 0; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a4aa3  jnz     short loc_1004A4AAD
0x1004a4aa5  call    cs:__imp_free
0x1004a4aab  jmp     short loc_1004A4AB3
0x1004a4aad  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1004a4ab3  mov     eax, esi
0x1004a4ab5  mov     rbx, [rsp+78h+arg_8]
0x1004a4abd  add     rsp, 40h
0x1004a4ac1  pop     r15
0x1004a4ac3  pop     r14
0x1004a4ac5  pop     r13
0x1004a4ac7  pop     r12
0x1004a4ac9  pop     rdi
0x1004a4aca  pop     rsi
0x1004a4acb  pop     rbp
0x1004a4acc  retn
```
