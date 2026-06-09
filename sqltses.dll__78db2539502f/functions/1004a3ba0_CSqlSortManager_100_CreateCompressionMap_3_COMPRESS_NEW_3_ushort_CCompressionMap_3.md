# CSqlSortManager_100::CreateCompressionMap<3>(COMPRESS_NEW<3> *,ushort,CCompressionMap<3> * *)

- ea: `0x1004a3ba0`
- end: `0x1004a3de4`
- name: `??$CreateCompressionMap@$02@CSqlSortManager_100@@KAHPEAU?$COMPRESS_NEW@$02@@GPEAPEAV?$CCompressionMap@$02@@@Z`
- size: `580`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1004a2fe0`

## callees

- `0x1004011fc`
- `0x1004a37e0`
- `0x1004a3ba0`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x1004a3dc4`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004a3dc4`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a3c0a`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a3c63`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a3d49`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a3c0a`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a3c63`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a3d49`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a3bf0`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a3c49`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a3d2f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a3bf0`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a3c49`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a3d2f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a3dbc`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a3dbc`

## string_xrefs

- `0x1004a3c03`: `sql\ntdbms\msql\sqlsort\common\sortutil.cpp`
- `0x1004a3c5c`: `sql\ntdbms\msql\sqlsort\common\sortutil.cpp`
- `0x1004a3d42`: `sql\ntdbms\msql\sqlsort\common\sortutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSqlSortManager_100::CreateCompressionMap<3>(__int64 a1, unsigned __int16 a2, __int64 *a3)
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
  unsigned __int64 v15; // rdi
  _QWORD *v16; // rax
  _QWORD *v17; // rax

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
          v12 = (unsigned __int16 *)(v4 + 10LL * i);
          v13 = *(_DWORD *)(v12 + 3);
          v14 = ((*v12 >> 2) + 2080 * *v12 + v12[1]) ^ *v12;
          v15 = *(_QWORD *)v6
              + 24 * ((v14 ^ (unsigned __int64)(2080 * v14 + v12[2] + (v14 >> 2))) % *(unsigned int *)(v6 + 8));
          if ( *(_DWORD *)(v15 + 8) )
          {
            v16 = *(_QWORD **)v15;
            if ( *(_QWORD *)v15 )
            {
              do
              {
                v15 = (unsigned __int64)v16;
                v16 = (_QWORD *)*v16;
              }
              while ( v16 );
            }
            if ( CSqlSortUtil::m_pmoSqlSort )
              v17 = operator new[](
                      0x18u,
                      CSqlSortUtil::m_pmoSqlSort,
                      "sql\\ntdbms\\msql\\sqlsort\\common\\sortutil.cpp",
                      139,
                      6u);
            else
              v17 = malloc(0x18u);
            *(_QWORD *)v15 = v17;
            if ( !v17 )
              goto LABEL_22;
            v15 = (unsigned __int64)v17;
            *v17 = 0;
          }
          *(_DWORD *)(v15 + 8) = v13;
          *(_DWORD *)(v15 + 12) = *(_DWORD *)v12;
          *(_WORD *)(v15 + 16) = v12[2];
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
0x1004a3ba0  mov     rax, rsp
0x1004a3ba3  mov     [rax+18h], r8
0x1004a3ba7  mov     [rax+8], rcx
0x1004a3bab  push    rbp
0x1004a3bac  push    rsi
0x1004a3bad  push    rdi
0x1004a3bae  push    r12
0x1004a3bb0  push    r13
0x1004a3bb2  push    r14
0x1004a3bb4  push    r15
0x1004a3bb6  sub     rsp, 40h
0x1004a3bba  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x1004a3bc2  mov     [rax+10h], rbx
0x1004a3bc6  movzx   r12d, dx
0x1004a3bca  mov     r15, rcx
0x1004a3bcd  test    rcx, rcx
0x1004a3bd0  jnz     short loc_1004A3BDF
0x1004a3bd2  xor     esi, esi
0x1004a3bd4  mov     [r8], rsi
0x1004a3bd7  lea     eax, [rcx+1]
0x1004a3bda  jmp     loc_1004A3DCC
0x1004a3bdf  mov     rdx, cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a3be6  mov     ecx, 10h; Size
0x1004a3beb  test    rdx, rdx
0x1004a3bee  jnz     short loc_1004A3BF8
0x1004a3bf0  call    cs:__imp_malloc
0x1004a3bf6  jmp     short loc_1004A3C10
0x1004a3bf8  mov     [rsp+78h+var_58], 6
0x1004a3bfd  mov     r9d, 8Bh
0x1004a3c03  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sqlsort\\common\\sor"...
0x1004a3c0a  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004a3c10  mov     r14, rax
0x1004a3c13  test    rax, rax
0x1004a3c16  jz      loc_1004A3DCC
0x1004a3c1c  xor     esi, esi
0x1004a3c1e  mov     [r14], rsi
0x1004a3c21  mov     [r14+8], esi
0x1004a3c25  mov     rbx, r14
0x1004a3c28  mov     [rsp+78h+arg_18], rbx
0x1004a3c30  mov     edi, r12d
0x1004a3c33  add     edi, edi
0x1004a3c35  lea     ebp, [rdi+rdi*2]
0x1004a3c38  shl     ebp, 3
0x1004a3c3b  mov     rdx, cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a3c42  mov     ecx, ebp; Size
0x1004a3c44  test    rdx, rdx
0x1004a3c47  jnz     short loc_1004A3C51
0x1004a3c49  call    cs:__imp_malloc
0x1004a3c4f  jmp     short loc_1004A3C69
0x1004a3c51  mov     [rsp+78h+var_58], 6
0x1004a3c56  mov     r9d, 8Bh
0x1004a3c5c  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sqlsort\\common\\sor"...
0x1004a3c63  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004a3c69  mov     [r14], rax
0x1004a3c6c  test    rax, rax
0x1004a3c6f  jz      loc_1004A3DA0
0x1004a3c75  mov     r8, rbp; Size
0x1004a3c78  xor     edx, edx; Val
0x1004a3c7a  mov     rcx, rax; void *
0x1004a3c7d  call    memset_0
0x1004a3c82  mov     [r14+8], edi
0x1004a3c86  movzx   ebp, si
0x1004a3c89  cmp     si, r12w
0x1004a3c8d  jnb     loc_1004A3D85
0x1004a3c93  nop     dword ptr [rax+00h]
0x1004a3c97  nop     word ptr [rax+rax+00000000h]
0x1004a3ca0  movzx   eax, bp
0x1004a3ca3  lea     rcx, [rax+rax*4]
0x1004a3ca7  lea     r15, [r15+rcx*2]
0x1004a3cab  mov     r13d, [r15+6]
0x1004a3caf  movzx   r8d, word ptr [r15]
0x1004a3cb3  movzx   ecx, word ptr [r15+2]
0x1004a3cb8  imul    eax, r8d, 820h
0x1004a3cbf  add     ecx, eax
0x1004a3cc1  mov     eax, r8d
0x1004a3cc4  shr     eax, 2
0x1004a3cc7  add     ecx, eax
0x1004a3cc9  xor     r8d, ecx
0x1004a3ccc  movzx   ecx, word ptr [r15+4]
0x1004a3cd1  imul    eax, r8d, 820h
0x1004a3cd8  add     ecx, eax
0x1004a3cda  mov     eax, r8d
0x1004a3cdd  shr     eax, 2
0x1004a3ce0  add     eax, ecx
0x1004a3ce2  xor     eax, r8d
0x1004a3ce5  xor     edx, edx
0x1004a3ce7  div     dword ptr [r14+8]
0x1004a3ceb  lea     rdx, [rdx+rdx*2]
0x1004a3cef  mov     rax, [r14]
0x1004a3cf2  lea     rdi, [rax+rdx*8]
0x1004a3cf6  cmp     dword ptr [rdi+8], 0
0x1004a3cfa  jz      short loc_1004A3D5D
0x1004a3cfc  mov     rax, [rdi]
0x1004a3cff  test    rax, rax
0x1004a3d02  jz      short loc_1004A3D1E
0x1004a3d04  nop     dword ptr [rax+00h]
0x1004a3d08  nop     dword ptr [rax+rax+00000000h]
0x1004a3d10  mov     rdi, rax
0x1004a3d13  mov     rcx, [rax]
0x1004a3d16  mov     rax, rcx
0x1004a3d19  test    rcx, rcx
0x1004a3d1c  jnz     short loc_1004A3D10
0x1004a3d1e  mov     rdx, cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a3d25  mov     ecx, 18h; Size
0x1004a3d2a  test    rdx, rdx
0x1004a3d2d  jnz     short loc_1004A3D37
0x1004a3d2f  call    cs:__imp_malloc
0x1004a3d35  jmp     short loc_1004A3D4F
0x1004a3d37  mov     [rsp+78h+var_58], 6
0x1004a3d3c  mov     r9d, 8Bh
0x1004a3d42  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sqlsort\\common\\sor"...
0x1004a3d49  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004a3d4f  mov     [rdi], rax
0x1004a3d52  test    rax, rax
0x1004a3d55  jz      short loc_1004A3DA0
0x1004a3d57  mov     rdi, rax
0x1004a3d5a  mov     [rax], rsi
0x1004a3d5d  mov     [rdi+8], r13d
0x1004a3d61  mov     eax, [r15]
0x1004a3d64  mov     [rdi+0Ch], eax
0x1004a3d67  movzx   eax, word ptr [r15+4]
0x1004a3d6c  mov     [rdi+10h], ax
0x1004a3d70  inc     bp
0x1004a3d73  cmp     bp, r12w
0x1004a3d77  mov     r15, [rsp+78h+arg_0]
0x1004a3d7f  jb      loc_1004A3CA0
0x1004a3d85  mov     rbx, rsi
0x1004a3d88  mov     [rsp+78h+arg_18], rbx
0x1004a3d90  mov     rax, [rsp+78h+arg_10]
0x1004a3d98  mov     [rax], r14
0x1004a3d9b  mov     esi, 1
0x1004a3da0  test    rbx, rbx
0x1004a3da3  jz      short loc_1004A3DCA
0x1004a3da5  xor     edx, edx
0x1004a3da7  mov     rcx, rbx
0x1004a3daa  call    ??_G?$CCompressionMap@$05@@QEAAPEAXI@Z; CCompressionMap<6>::`scalar deleting destructor'(uint)
0x1004a3daf  mov     rcx, rbx; Block
0x1004a3db2  cmp     cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA, 0; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a3dba  jnz     short loc_1004A3DC4
0x1004a3dbc  call    cs:__imp_free
0x1004a3dc2  jmp     short loc_1004A3DCA
0x1004a3dc4  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1004a3dca  mov     eax, esi
0x1004a3dcc  mov     rbx, [rsp+78h+arg_8]
0x1004a3dd4  add     rsp, 40h
0x1004a3dd8  pop     r15
0x1004a3dda  pop     r14
0x1004a3ddc  pop     r13
0x1004a3dde  pop     r12
0x1004a3de0  pop     rdi
0x1004a3de1  pop     rsi
0x1004a3de2  pop     rbp
0x1004a3de3  retn
```
