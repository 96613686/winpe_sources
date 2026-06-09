# CSqlSortManager_100::CreateCompressionMap<4>(COMPRESS_NEW<4> *,ushort,CCompressionMap<4> * *)

- ea: `0x1004a3df0`
- end: `0x1004a403c`
- name: `??$CreateCompressionMap@$03@CSqlSortManager_100@@KAHPEAU?$COMPRESS_NEW@$03@@GPEAPEAV?$CCompressionMap@$03@@@Z`
- size: `588`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1004a2fe0`

## callees

- `0x1004011fc`
- `0x1004a37e0`
- `0x1004a3df0`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x1004a401c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004a401c`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a3e5a`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a3eb3`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a3fa9`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a3e5a`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a3eb3`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a3fa9`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a3e40`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a3e99`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a3f8f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a3e40`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a3e99`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a3f8f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a4014`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a4014`

## string_xrefs

- `0x1004a3e53`: `sql\ntdbms\msql\sqlsort\common\sortutil.cpp`
- `0x1004a3eac`: `sql\ntdbms\msql\sqlsort\common\sortutil.cpp`
- `0x1004a3fa2`: `sql\ntdbms\msql\sqlsort\common\sortutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSqlSortManager_100::CreateCompressionMap<4>(__int64 a1, unsigned __int16 a2, __int64 *a3)
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
  unsigned __int64 v16; // rdi
  _QWORD *v17; // rax
  _QWORD *v18; // rax

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
          v12 = (unsigned __int16 *)(v4 + 12LL * i);
          v13 = *((_DWORD *)v12 + 2);
          v14 = ((*v12 >> 2) + 2080 * *v12 + v12[1]) ^ *v12;
          v15 = ((v14 >> 2) + 2080 * v14 + v12[2]) ^ v14;
          v16 = *(_QWORD *)v6
              + 24 * ((v15 ^ (unsigned __int64)(2080 * v15 + v12[3] + (v15 >> 2))) % *(unsigned int *)(v6 + 8));
          if ( *(_DWORD *)(v16 + 8) )
          {
            v17 = *(_QWORD **)v16;
            if ( *(_QWORD *)v16 )
            {
              do
              {
                v16 = (unsigned __int64)v17;
                v17 = (_QWORD *)*v17;
              }
              while ( v17 );
            }
            if ( CSqlSortUtil::m_pmoSqlSort )
              v18 = operator new[](
                      0x18u,
                      CSqlSortUtil::m_pmoSqlSort,
                      "sql\\ntdbms\\msql\\sqlsort\\common\\sortutil.cpp",
                      139,
                      6u);
            else
              v18 = malloc(0x18u);
            *(_QWORD *)v16 = v18;
            if ( !v18 )
              goto LABEL_22;
            v16 = (unsigned __int64)v18;
            *v18 = 0;
          }
          *(_DWORD *)(v16 + 8) = v13;
          *(_QWORD *)(v16 + 12) = *(_QWORD *)v12;
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
0x1004a3df0  mov     rax, rsp
0x1004a3df3  mov     [rax+18h], r8
0x1004a3df7  mov     [rax+8], rcx
0x1004a3dfb  push    rbp
0x1004a3dfc  push    rsi
0x1004a3dfd  push    rdi
0x1004a3dfe  push    r12
0x1004a3e00  push    r13
0x1004a3e02  push    r14
0x1004a3e04  push    r15
0x1004a3e06  sub     rsp, 40h
0x1004a3e0a  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x1004a3e12  mov     [rax+10h], rbx
0x1004a3e16  movzx   r12d, dx
0x1004a3e1a  mov     r15, rcx
0x1004a3e1d  test    rcx, rcx
0x1004a3e20  jnz     short loc_1004A3E2F
0x1004a3e22  xor     esi, esi
0x1004a3e24  mov     [r8], rsi
0x1004a3e27  lea     eax, [rcx+1]
0x1004a3e2a  jmp     loc_1004A4024
0x1004a3e2f  mov     rdx, cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a3e36  mov     ecx, 10h; Size
0x1004a3e3b  test    rdx, rdx
0x1004a3e3e  jnz     short loc_1004A3E48
0x1004a3e40  call    cs:__imp_malloc
0x1004a3e46  jmp     short loc_1004A3E60
0x1004a3e48  mov     [rsp+78h+var_58], 6
0x1004a3e4d  mov     r9d, 8Bh
0x1004a3e53  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sqlsort\\common\\sor"...
0x1004a3e5a  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004a3e60  mov     r14, rax
0x1004a3e63  test    rax, rax
0x1004a3e66  jz      loc_1004A4024
0x1004a3e6c  xor     esi, esi
0x1004a3e6e  mov     [r14], rsi
0x1004a3e71  mov     [r14+8], esi
0x1004a3e75  mov     rbx, r14
0x1004a3e78  mov     [rsp+78h+arg_18], rbx
0x1004a3e80  mov     edi, r12d
0x1004a3e83  add     edi, edi
0x1004a3e85  lea     ebp, [rdi+rdi*2]
0x1004a3e88  shl     ebp, 3
0x1004a3e8b  mov     rdx, cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a3e92  mov     ecx, ebp; Size
0x1004a3e94  test    rdx, rdx
0x1004a3e97  jnz     short loc_1004A3EA1
0x1004a3e99  call    cs:__imp_malloc
0x1004a3e9f  jmp     short loc_1004A3EB9
0x1004a3ea1  mov     [rsp+78h+var_58], 6
0x1004a3ea6  mov     r9d, 8Bh
0x1004a3eac  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sqlsort\\common\\sor"...
0x1004a3eb3  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004a3eb9  mov     [r14], rax
0x1004a3ebc  test    rax, rax
0x1004a3ebf  jz      loc_1004A3FF8
0x1004a3ec5  mov     r8, rbp; Size
0x1004a3ec8  xor     edx, edx; Val
0x1004a3eca  mov     rcx, rax; void *
0x1004a3ecd  call    memset_0
0x1004a3ed2  mov     [r14+8], edi
0x1004a3ed6  movzx   ebp, si
0x1004a3ed9  cmp     si, r12w
0x1004a3edd  jnb     loc_1004A3FDD
0x1004a3ee3  nop     dword ptr [rax+00h]
0x1004a3ee7  nop     word ptr [rax+rax+00000000h]
0x1004a3ef0  movzx   eax, bp
0x1004a3ef3  lea     rcx, [rax+rax*2]
0x1004a3ef7  lea     r15, [r15+rcx*4]
0x1004a3efb  mov     r13d, [r15+8]
0x1004a3eff  movzx   r8d, word ptr [r15]
0x1004a3f03  movzx   ecx, word ptr [r15+2]
0x1004a3f08  imul    eax, r8d, 820h
0x1004a3f0f  add     ecx, eax
0x1004a3f11  mov     eax, r8d
0x1004a3f14  shr     eax, 2
0x1004a3f17  add     ecx, eax
0x1004a3f19  xor     r8d, ecx
0x1004a3f1c  movzx   ecx, word ptr [r15+4]
0x1004a3f21  imul    eax, r8d, 820h
0x1004a3f28  add     ecx, eax
0x1004a3f2a  mov     eax, r8d
0x1004a3f2d  shr     eax, 2
0x1004a3f30  add     ecx, eax
0x1004a3f32  xor     r8d, ecx
0x1004a3f35  movzx   ecx, word ptr [r15+6]
0x1004a3f3a  imul    eax, r8d, 820h
0x1004a3f41  add     ecx, eax
0x1004a3f43  mov     eax, r8d
0x1004a3f46  shr     eax, 2
0x1004a3f49  add     eax, ecx
0x1004a3f4b  xor     eax, r8d
0x1004a3f4e  xor     edx, edx
0x1004a3f50  div     dword ptr [r14+8]
0x1004a3f54  lea     rdx, [rdx+rdx*2]
0x1004a3f58  mov     rax, [r14]
0x1004a3f5b  lea     rdi, [rax+rdx*8]
0x1004a3f5f  cmp     dword ptr [rdi+8], 0
0x1004a3f63  jz      short loc_1004A3FBD
0x1004a3f65  mov     rax, [rdi]
0x1004a3f68  test    rax, rax
0x1004a3f6b  jz      short loc_1004A3F7E
0x1004a3f6d  nop     dword ptr [rax]
0x1004a3f70  mov     rdi, rax
0x1004a3f73  mov     rcx, [rax]
0x1004a3f76  mov     rax, rcx
0x1004a3f79  test    rcx, rcx
0x1004a3f7c  jnz     short loc_1004A3F70
0x1004a3f7e  mov     rdx, cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a3f85  mov     ecx, 18h; Size
0x1004a3f8a  test    rdx, rdx
0x1004a3f8d  jnz     short loc_1004A3F97
0x1004a3f8f  call    cs:__imp_malloc
0x1004a3f95  jmp     short loc_1004A3FAF
0x1004a3f97  mov     [rsp+78h+var_58], 6
0x1004a3f9c  mov     r9d, 8Bh
0x1004a3fa2  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sqlsort\\common\\sor"...
0x1004a3fa9  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004a3faf  mov     [rdi], rax
0x1004a3fb2  test    rax, rax
0x1004a3fb5  jz      short loc_1004A3FF8
0x1004a3fb7  mov     rdi, rax
0x1004a3fba  mov     [rax], rsi
0x1004a3fbd  mov     [rdi+8], r13d
0x1004a3fc1  mov     rax, [r15]
0x1004a3fc4  mov     [rdi+0Ch], rax
0x1004a3fc8  inc     bp
0x1004a3fcb  cmp     bp, r12w
0x1004a3fcf  mov     r15, [rsp+78h+arg_0]
0x1004a3fd7  jb      loc_1004A3EF0
0x1004a3fdd  mov     rbx, rsi
0x1004a3fe0  mov     [rsp+78h+arg_18], rbx
0x1004a3fe8  mov     rax, [rsp+78h+arg_10]
0x1004a3ff0  mov     [rax], r14
0x1004a3ff3  mov     esi, 1
0x1004a3ff8  test    rbx, rbx
0x1004a3ffb  jz      short loc_1004A4022
0x1004a3ffd  xor     edx, edx
0x1004a3fff  mov     rcx, rbx
0x1004a4002  call    ??_G?$CCompressionMap@$05@@QEAAPEAXI@Z; CCompressionMap<6>::`scalar deleting destructor'(uint)
0x1004a4007  mov     rcx, rbx; Block
0x1004a400a  cmp     cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA, 0; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a4012  jnz     short loc_1004A401C
0x1004a4014  call    cs:__imp_free
0x1004a401a  jmp     short loc_1004A4022
0x1004a401c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1004a4022  mov     eax, esi
0x1004a4024  mov     rbx, [rsp+78h+arg_8]
0x1004a402c  add     rsp, 40h
0x1004a4030  pop     r15
0x1004a4032  pop     r14
0x1004a4034  pop     r13
0x1004a4036  pop     r12
0x1004a4038  pop     rdi
0x1004a4039  pop     rsi
0x1004a403a  pop     rbp
0x1004a403b  retn
```
