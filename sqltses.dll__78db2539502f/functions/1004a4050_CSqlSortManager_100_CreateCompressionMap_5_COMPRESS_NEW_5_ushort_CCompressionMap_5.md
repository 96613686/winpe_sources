# CSqlSortManager_100::CreateCompressionMap<5>(COMPRESS_NEW<5> *,ushort,CCompressionMap<5> * *)

- ea: `0x1004a4050`
- end: `0x1004a42c8`
- name: `??$CreateCompressionMap@$04@CSqlSortManager_100@@KAHPEAU?$COMPRESS_NEW@$04@@GPEAPEAV?$CCompressionMap@$04@@@Z`
- size: `632`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1004a2fe0`

## callees

- `0x1004011fc`
- `0x1004a37e0`
- `0x1004a4050`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x1004a42a8`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004a42a8`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a40ba`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a4113`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a4229`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a40ba`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a4113`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a4229`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a40a0`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a40f9`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a420f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a40a0`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a40f9`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a420f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a42a0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a42a0`

## string_xrefs

- `0x1004a40b3`: `sql\ntdbms\msql\sqlsort\common\sortutil.cpp`
- `0x1004a410c`: `sql\ntdbms\msql\sqlsort\common\sortutil.cpp`
- `0x1004a4222`: `sql\ntdbms\msql\sqlsort\common\sortutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSqlSortManager_100::CreateCompressionMap<5>(__int64 a1, unsigned __int16 a2, __int64 *a3)
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
  unsigned __int64 v17; // rdi
  _QWORD *v18; // rax
  _QWORD *v19; // rax

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
          v12 = (unsigned __int16 *)(14LL * i + v4);
          v13 = *(_DWORD *)(v12 + 5);
          v14 = ((*v12 >> 2) + 2080 * *v12 + v12[1]) ^ *v12;
          v15 = ((v14 >> 2) + 2080 * v14 + v12[2]) ^ v14;
          v16 = ((v15 >> 2) + 2080 * v15 + v12[3]) ^ v15;
          v17 = *(_QWORD *)v6
              + 24 * ((v16 ^ (unsigned __int64)(2080 * v16 + v12[4] + (v16 >> 2))) % *(unsigned int *)(v6 + 8));
          if ( *(_DWORD *)(v17 + 8) )
          {
            v18 = *(_QWORD **)v17;
            if ( *(_QWORD *)v17 )
            {
              do
              {
                v17 = (unsigned __int64)v18;
                v18 = (_QWORD *)*v18;
              }
              while ( v18 );
            }
            if ( CSqlSortUtil::m_pmoSqlSort )
              v19 = operator new[](
                      0x18u,
                      CSqlSortUtil::m_pmoSqlSort,
                      "sql\\ntdbms\\msql\\sqlsort\\common\\sortutil.cpp",
                      139,
                      6u);
            else
              v19 = malloc(0x18u);
            *(_QWORD *)v17 = v19;
            if ( !v19 )
              goto LABEL_22;
            v17 = (unsigned __int64)v19;
            *v19 = 0;
          }
          *(_DWORD *)(v17 + 8) = v13;
          *(_QWORD *)(v17 + 12) = *(_QWORD *)v12;
          *(_WORD *)(v17 + 20) = v12[4];
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
0x1004a4050  mov     rax, rsp
0x1004a4053  mov     [rax+18h], r8
0x1004a4057  mov     [rax+8], rcx
0x1004a405b  push    rbp
0x1004a405c  push    rsi
0x1004a405d  push    rdi
0x1004a405e  push    r12
0x1004a4060  push    r13
0x1004a4062  push    r14
0x1004a4064  push    r15
0x1004a4066  sub     rsp, 40h
0x1004a406a  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x1004a4072  mov     [rax+10h], rbx
0x1004a4076  movzx   r12d, dx
0x1004a407a  mov     r14, rcx
0x1004a407d  test    rcx, rcx
0x1004a4080  jnz     short loc_1004A408F
0x1004a4082  xor     esi, esi
0x1004a4084  mov     [r8], rsi
0x1004a4087  lea     eax, [rcx+1]
0x1004a408a  jmp     loc_1004A42B0
0x1004a408f  mov     rdx, cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a4096  mov     ecx, 10h; Size
0x1004a409b  test    rdx, rdx
0x1004a409e  jnz     short loc_1004A40A8
0x1004a40a0  call    cs:__imp_malloc
0x1004a40a6  jmp     short loc_1004A40C0
0x1004a40a8  mov     [rsp+78h+var_58], 6
0x1004a40ad  mov     r9d, 8Bh
0x1004a40b3  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sqlsort\\common\\sor"...
0x1004a40ba  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004a40c0  mov     r15, rax
0x1004a40c3  test    rax, rax
0x1004a40c6  jz      loc_1004A42B0
0x1004a40cc  xor     esi, esi
0x1004a40ce  mov     [r15], rsi
0x1004a40d1  mov     [r15+8], esi
0x1004a40d5  mov     rbx, r15
0x1004a40d8  mov     [rsp+78h+arg_18], rbx
0x1004a40e0  mov     edi, r12d
0x1004a40e3  add     edi, edi
0x1004a40e5  lea     ebp, [rdi+rdi*2]
0x1004a40e8  shl     ebp, 3
0x1004a40eb  mov     rdx, cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a40f2  mov     ecx, ebp; Size
0x1004a40f4  test    rdx, rdx
0x1004a40f7  jnz     short loc_1004A4101
0x1004a40f9  call    cs:__imp_malloc
0x1004a40ff  jmp     short loc_1004A4119
0x1004a4101  mov     [rsp+78h+var_58], 6
0x1004a4106  mov     r9d, 8Bh
0x1004a410c  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sqlsort\\common\\sor"...
0x1004a4113  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004a4119  mov     [r15], rax
0x1004a411c  test    rax, rax
0x1004a411f  jz      loc_1004A4284
0x1004a4125  mov     r8, rbp; Size
0x1004a4128  xor     edx, edx; Val
0x1004a412a  mov     rcx, rax; void *
0x1004a412d  call    memset_0
0x1004a4132  mov     [r15+8], edi
0x1004a4136  movzx   ebp, si
0x1004a4139  cmp     si, r12w
0x1004a413d  jnb     loc_1004A4269
0x1004a4143  nop     dword ptr [rax+00h]
0x1004a4147  nop     word ptr [rax+rax+00000000h]
0x1004a4150  movzx   eax, bp
0x1004a4153  imul    rcx, rax, 0Eh
0x1004a4157  add     r14, rcx
0x1004a415a  mov     r13d, [r14+0Ah]
0x1004a415e  movzx   r8d, word ptr [r14]
0x1004a4162  movzx   ecx, word ptr [r14+2]
0x1004a4167  imul    eax, r8d, 820h
0x1004a416e  add     ecx, eax
0x1004a4170  mov     eax, r8d
0x1004a4173  shr     eax, 2
0x1004a4176  add     ecx, eax
0x1004a4178  xor     r8d, ecx
0x1004a417b  movzx   ecx, word ptr [r14+4]
0x1004a4180  imul    eax, r8d, 820h
0x1004a4187  add     ecx, eax
0x1004a4189  mov     eax, r8d
0x1004a418c  shr     eax, 2
0x1004a418f  add     ecx, eax
0x1004a4191  xor     r8d, ecx
0x1004a4194  movzx   ecx, word ptr [r14+6]
0x1004a4199  imul    eax, r8d, 820h
0x1004a41a0  add     ecx, eax
0x1004a41a2  mov     eax, r8d
0x1004a41a5  shr     eax, 2
0x1004a41a8  add     ecx, eax
0x1004a41aa  xor     r8d, ecx
0x1004a41ad  movzx   ecx, word ptr [r14+8]
0x1004a41b2  imul    eax, r8d, 820h
0x1004a41b9  add     ecx, eax
0x1004a41bb  mov     eax, r8d
0x1004a41be  shr     eax, 2
0x1004a41c1  add     eax, ecx
0x1004a41c3  xor     eax, r8d
0x1004a41c6  xor     edx, edx
0x1004a41c8  div     dword ptr [r15+8]
0x1004a41cc  lea     rdx, [rdx+rdx*2]
0x1004a41d0  mov     rax, [r15]
0x1004a41d3  lea     rdi, [rax+rdx*8]
0x1004a41d7  cmp     dword ptr [rdi+8], 0
0x1004a41db  jz      short loc_1004A423D
0x1004a41dd  mov     rax, [rdi]
0x1004a41e0  test    rax, rax
0x1004a41e3  jz      short loc_1004A41FE
0x1004a41e5  nop     word ptr [rax+rax]
0x1004a41ea  nop     word ptr [rax+rax+00h]
0x1004a41f0  mov     rdi, rax
0x1004a41f3  mov     rcx, [rax]
0x1004a41f6  mov     rax, rcx
0x1004a41f9  test    rcx, rcx
0x1004a41fc  jnz     short loc_1004A41F0
0x1004a41fe  mov     rdx, cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a4205  mov     ecx, 18h; Size
0x1004a420a  test    rdx, rdx
0x1004a420d  jnz     short loc_1004A4217
0x1004a420f  call    cs:__imp_malloc
0x1004a4215  jmp     short loc_1004A422F
0x1004a4217  mov     [rsp+78h+var_58], 6
0x1004a421c  mov     r9d, 8Bh
0x1004a4222  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sqlsort\\common\\sor"...
0x1004a4229  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004a422f  mov     [rdi], rax
0x1004a4232  test    rax, rax
0x1004a4235  jz      short loc_1004A4284
0x1004a4237  mov     rdi, rax
0x1004a423a  mov     [rax], rsi
0x1004a423d  mov     [rdi+8], r13d
0x1004a4241  movsd   xmm0, qword ptr [r14]
0x1004a4246  movsd   qword ptr [rdi+0Ch], xmm0
0x1004a424b  movzx   eax, word ptr [r14+8]
0x1004a4250  mov     [rdi+14h], ax
0x1004a4254  inc     bp
0x1004a4257  cmp     bp, r12w
0x1004a425b  mov     r14, [rsp+78h+arg_0]
0x1004a4263  jb      loc_1004A4150
0x1004a4269  mov     rbx, rsi
0x1004a426c  mov     [rsp+78h+arg_18], rbx
0x1004a4274  mov     rax, [rsp+78h+arg_10]
0x1004a427c  mov     [rax], r15
0x1004a427f  mov     esi, 1
0x1004a4284  test    rbx, rbx
0x1004a4287  jz      short loc_1004A42AE
0x1004a4289  xor     edx, edx
0x1004a428b  mov     rcx, rbx
0x1004a428e  call    ??_G?$CCompressionMap@$05@@QEAAPEAXI@Z; CCompressionMap<6>::`scalar deleting destructor'(uint)
0x1004a4293  mov     rcx, rbx; Block
0x1004a4296  cmp     cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA, 0; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a429e  jnz     short loc_1004A42A8
0x1004a42a0  call    cs:__imp_free
0x1004a42a6  jmp     short loc_1004A42AE
0x1004a42a8  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1004a42ae  mov     eax, esi
0x1004a42b0  mov     rbx, [rsp+78h+arg_8]
0x1004a42b8  add     rsp, 40h
0x1004a42bc  pop     r15
0x1004a42be  pop     r14
0x1004a42c0  pop     r13
0x1004a42c2  pop     r12
0x1004a42c4  pop     rdi
0x1004a42c5  pop     rsi
0x1004a42c6  pop     rbp
0x1004a42c7  retn
```
