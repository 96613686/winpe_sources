# CSqlSortManager_100::CreateCompressionMap<2>(COMPRESS_NEW<2> *,ushort,CCompressionMap<2> * *)

- ea: `0x1004a3970`
- end: `0x1004a3b8b`
- name: `??$CreateCompressionMap@$01@CSqlSortManager_100@@KAHPEAU?$COMPRESS_NEW@$01@@GPEAPEAV?$CCompressionMap@$01@@@Z`
- size: `539`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1004a2fe0`

## callees

- `0x1004011fc`
- `0x1004a38a0`
- `0x1004a3970`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x1004a3b6b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004a3b6b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a39da`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a3a32`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a3af9`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a39da`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a3a32`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a3af9`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a39c0`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a3a18`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a3adf`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a39c0`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a3a18`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a3adf`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a3b63`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a3b63`

## string_xrefs

- `0x1004a39d3`: `sql\ntdbms\msql\sqlsort\common\sortutil.cpp`
- `0x1004a3a2b`: `sql\ntdbms\msql\sqlsort\common\sortutil.cpp`
- `0x1004a3af2`: `sql\ntdbms\msql\sqlsort\common\sortutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSqlSortManager_100::CreateCompressionMap<2>(__int64 a1, unsigned __int16 a2, __int64 *a3)
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
  unsigned __int64 v14; // rdi
  _QWORD *v15; // rax
  _QWORD *v16; // rax

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
      v9 = (unsigned int)(32 * v3);
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
        memset_0(v10, 0, (unsigned int)(32 * v3));
        *(_DWORD *)(v6 + 8) = 2 * v3;
        for ( i = 0; i < (unsigned __int16)v3; v4 = a1 )
        {
          v12 = (unsigned __int16 *)(v4 + 8LL * i);
          v13 = *((_DWORD *)v12 + 1);
          v14 = *(_QWORD *)v6
              + 16 * ((*v12 ^ (unsigned __int64)(2080 * *v12 + v12[1] + (*v12 >> 2))) % *(unsigned int *)(v6 + 8));
          if ( *(_DWORD *)(v14 + 8) )
          {
            v15 = *(_QWORD **)v14;
            if ( *(_QWORD *)v14 )
            {
              do
              {
                v14 = (unsigned __int64)v15;
                v15 = (_QWORD *)*v15;
              }
              while ( v15 );
            }
            if ( CSqlSortUtil::m_pmoSqlSort )
              v16 = operator new[](
                      0x10u,
                      CSqlSortUtil::m_pmoSqlSort,
                      "sql\\ntdbms\\msql\\sqlsort\\common\\sortutil.cpp",
                      139,
                      6u);
            else
              v16 = malloc(0x10u);
            *(_QWORD *)v14 = v16;
            if ( !v16 )
              goto LABEL_22;
            v14 = (unsigned __int64)v16;
            *v16 = 0;
          }
          *(_DWORD *)(v14 + 8) = v13;
          *(_DWORD *)(v14 + 12) = *(_DWORD *)v12;
          ++i;
        }
        v8 = 0;
        *a3 = v6;
        v7 = 1;
      }
LABEL_22:
      if ( v8 )
      {
        CCompressionMap<2>::`scalar deleting destructor'(v8, 0);
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
0x1004a3970  mov     rax, rsp
0x1004a3973  mov     [rax+18h], r8
0x1004a3977  mov     [rax+8], rcx
0x1004a397b  push    rbp
0x1004a397c  push    rsi
0x1004a397d  push    rdi
0x1004a397e  push    r12
0x1004a3980  push    r13
0x1004a3982  push    r14
0x1004a3984  push    r15
0x1004a3986  sub     rsp, 40h
0x1004a398a  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x1004a3992  mov     [rax+10h], rbx
0x1004a3996  movzx   r12d, dx
0x1004a399a  mov     r15, rcx
0x1004a399d  test    rcx, rcx
0x1004a39a0  jnz     short loc_1004A39AF
0x1004a39a2  xor     esi, esi
0x1004a39a4  mov     [r8], rsi
0x1004a39a7  lea     eax, [rcx+1]
0x1004a39aa  jmp     loc_1004A3B73
0x1004a39af  mov     rdx, cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a39b6  mov     ecx, 10h; Size
0x1004a39bb  test    rdx, rdx
0x1004a39be  jnz     short loc_1004A39C8
0x1004a39c0  call    cs:__imp_malloc
0x1004a39c6  jmp     short loc_1004A39E0
0x1004a39c8  mov     [rsp+78h+var_58], 6
0x1004a39cd  mov     r9d, 8Bh
0x1004a39d3  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sqlsort\\common\\sor"...
0x1004a39da  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004a39e0  mov     r14, rax
0x1004a39e3  test    rax, rax
0x1004a39e6  jz      loc_1004A3B73
0x1004a39ec  xor     esi, esi
0x1004a39ee  mov     [r14], rsi
0x1004a39f1  mov     [r14+8], esi
0x1004a39f5  mov     rbx, r14
0x1004a39f8  mov     [rsp+78h+arg_18], rbx
0x1004a3a00  mov     edi, r12d
0x1004a3a03  add     edi, edi
0x1004a3a05  mov     ebp, edi
0x1004a3a07  shl     ebp, 4
0x1004a3a0a  mov     rdx, cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a3a11  mov     ecx, ebp; Size
0x1004a3a13  test    rdx, rdx
0x1004a3a16  jnz     short loc_1004A3A20
0x1004a3a18  call    cs:__imp_malloc
0x1004a3a1e  jmp     short loc_1004A3A38
0x1004a3a20  mov     [rsp+78h+var_58], 6
0x1004a3a25  mov     r9d, 8Bh
0x1004a3a2b  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sqlsort\\common\\sor"...
0x1004a3a32  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004a3a38  mov     [r14], rax
0x1004a3a3b  test    rax, rax
0x1004a3a3e  jz      loc_1004A3B47
0x1004a3a44  mov     r8, rbp; Size
0x1004a3a47  xor     edx, edx; Val
0x1004a3a49  mov     rcx, rax; void *
0x1004a3a4c  call    memset_0
0x1004a3a51  mov     [r14+8], edi
0x1004a3a55  movzx   ebp, si
0x1004a3a58  cmp     si, r12w
0x1004a3a5c  jnb     loc_1004A3B2C
0x1004a3a62  nop     dword ptr [rax+00h]
0x1004a3a66  nop     word ptr [rax+rax+00000000h]
0x1004a3a70  movzx   eax, bp
0x1004a3a73  lea     r15, [r15+rax*8]
0x1004a3a77  mov     r13d, [r15+4]
0x1004a3a7b  movzx   r8d, word ptr [r15]
0x1004a3a7f  movzx   ecx, word ptr [r15+2]
0x1004a3a84  imul    eax, r8d, 820h
0x1004a3a8b  add     ecx, eax
0x1004a3a8d  mov     eax, r8d
0x1004a3a90  shr     eax, 2
0x1004a3a93  add     eax, ecx
0x1004a3a95  xor     eax, r8d
0x1004a3a98  xor     edx, edx
0x1004a3a9a  div     dword ptr [r14+8]
0x1004a3a9e  mov     edi, edx
0x1004a3aa0  shl     rdi, 4
0x1004a3aa4  add     rdi, [r14]
0x1004a3aa7  cmp     dword ptr [rdi+8], 0
0x1004a3aab  jz      short loc_1004A3B0D
0x1004a3aad  mov     rax, [rdi]
0x1004a3ab0  test    rax, rax
0x1004a3ab3  jz      short loc_1004A3ACE
0x1004a3ab5  nop     word ptr [rax+rax]
0x1004a3aba  nop     word ptr [rax+rax+00h]
0x1004a3ac0  mov     rdi, rax
0x1004a3ac3  mov     rcx, [rax]
0x1004a3ac6  mov     rax, rcx
0x1004a3ac9  test    rcx, rcx
0x1004a3acc  jnz     short loc_1004A3AC0
0x1004a3ace  mov     rdx, cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a3ad5  mov     ecx, 10h; Size
0x1004a3ada  test    rdx, rdx
0x1004a3add  jnz     short loc_1004A3AE7
0x1004a3adf  call    cs:__imp_malloc
0x1004a3ae5  jmp     short loc_1004A3AFF
0x1004a3ae7  mov     [rsp+78h+var_58], 6
0x1004a3aec  mov     r9d, 8Bh
0x1004a3af2  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sqlsort\\common\\sor"...
0x1004a3af9  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004a3aff  mov     [rdi], rax
0x1004a3b02  test    rax, rax
0x1004a3b05  jz      short loc_1004A3B47
0x1004a3b07  mov     rdi, rax
0x1004a3b0a  mov     [rax], rsi
0x1004a3b0d  mov     [rdi+8], r13d
0x1004a3b11  mov     eax, [r15]
0x1004a3b14  mov     [rdi+0Ch], eax
0x1004a3b17  inc     bp
0x1004a3b1a  cmp     bp, r12w
0x1004a3b1e  mov     r15, [rsp+78h+arg_0]
0x1004a3b26  jb      loc_1004A3A70
0x1004a3b2c  mov     rbx, rsi
0x1004a3b2f  mov     [rsp+78h+arg_18], rbx
0x1004a3b37  mov     rax, [rsp+78h+arg_10]
0x1004a3b3f  mov     [rax], r14
0x1004a3b42  mov     esi, 1
0x1004a3b47  test    rbx, rbx
0x1004a3b4a  jz      short loc_1004A3B71
0x1004a3b4c  xor     edx, edx
0x1004a3b4e  mov     rcx, rbx
0x1004a3b51  call    ??_G?$CCompressionMap@$01@@QEAAPEAXI@Z; CCompressionMap<2>::`scalar deleting destructor'(uint)
0x1004a3b56  mov     rcx, rbx; Block
0x1004a3b59  cmp     cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA, 0; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a3b61  jnz     short loc_1004A3B6B
0x1004a3b63  call    cs:__imp_free
0x1004a3b69  jmp     short loc_1004A3B71
0x1004a3b6b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1004a3b71  mov     eax, esi
0x1004a3b73  mov     rbx, [rsp+78h+arg_8]
0x1004a3b7b  add     rsp, 40h
0x1004a3b7f  pop     r15
0x1004a3b81  pop     r14
0x1004a3b83  pop     r13
0x1004a3b85  pop     r12
0x1004a3b87  pop     rdi
0x1004a3b88  pop     rsi
0x1004a3b89  pop     rbp
0x1004a3b8a  retn
```
