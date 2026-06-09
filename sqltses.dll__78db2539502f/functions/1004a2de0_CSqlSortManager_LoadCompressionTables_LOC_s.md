# CSqlSortManager::LoadCompressionTables(LOC_s *)

- ea: `0x1004a2de0`
- end: `0x1004a2fcc`
- name: `?LoadCompressionTables@CSqlSortManager@@MEAAHPEAULOC_s@@@Z`
- size: `492`
- prototype: `__int64 __fastcall(CSqlSortManager *__hidden this, struct LOC_s *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x100401cc0`
- `0x1004a2de0`

## import_xrefs

- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a2ec3`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a2f33`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a2ec3`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a2f33`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a2ea9`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a2f19`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a2ea9`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a2f19`

## string_xrefs

- `0x1004a2ebc`: `sql\ntdbms\msql\sqlsort\common\sortutil.cpp`
- `0x1004a2f2c`: `sql\ntdbms\msql\sqlsort\common\sortutil.cpp`

## pseudocode

```c
__int64 __fastcall CSqlSortManager::LoadCompressionTables(CSqlSortManager *this, struct LOC_s *a2)
{
  __int64 v2; // rbx
  __int64 v4; // rdx
  int v6; // eax
  __int64 v7; // r8
  _DWORD *i; // r9
  __int64 v10; // rdx
  _WORD *v11; // rcx
  unsigned __int16 *v12; // rdi
  unsigned __int64 v13; // rcx
  void *v14; // rax
  __int64 v15; // r14
  unsigned int v16; // r15d
  unsigned __int64 v17; // rcx
  void *v18; // rax
  int v19; // edx
  __int64 v20; // rcx
  _DWORD *j; // rax

  v2 = 0;
  v4 = *((int *)this + 32);
  v6 = 0;
  if ( (int)v4 <= 0 )
    return 1;
  v7 = 0;
  for ( i = (_DWORD *)*((_QWORD *)this + 17); *i != *(_DWORD *)a2; i += 4 )
  {
    ++v6;
    if ( ++v7 >= v4 )
      return 1;
  }
  *((_DWORD *)a2 + 5) = 1;
  v10 = *((_QWORD *)this + 17);
  if ( !*(_WORD *)(v10 + 16LL * v6 + 4) )
  {
    v11 = (_WORD *)(16 * v7 + v10 + 4);
    do
    {
      ++v6;
      v11 += 8;
    }
    while ( !*v11 );
  }
  v12 = (unsigned __int16 *)(v10 + 16LL * v6);
  v13 = 16LL * v12[2];
  if ( CSqlSortUtil::m_pmoSqlSort )
    v14 = operator new[](v13, CSqlSortUtil::m_pmoSqlSort, "sql\\ntdbms\\msql\\sqlsort\\common\\sortutil.cpp", 139, 6u);
  else
    v14 = malloc(v13);
  *((_QWORD *)a2 + 4) = v14;
  if ( v14 )
  {
    memmove(v14, v12, 16LL * v12[2]);
    v15 = v12[4];
    v16 = v12[8 * v12[2] - 3] + v12[8 * v12[2] - 4];
    v17 = 8 * (v16 - (unsigned int)v15);
    v18 = CSqlSortUtil::m_pmoSqlSort
        ? operator new[](v17, CSqlSortUtil::m_pmoSqlSort, "sql\\ntdbms\\msql\\sqlsort\\common\\sortutil.cpp", 139, 6u)
        : malloc(v17);
    *((_QWORD *)a2 + 5) = v18;
    if ( v18 )
    {
      memmove(v18, (const void *)(*((_QWORD *)this + 18) + 8 * v15), 8 * (v16 - v15));
      v19 = 0;
      if ( v12[2] )
      {
        v20 = 0;
        do
        {
          v20 += 16;
          ++v19;
          *(_WORD *)(v20 + *((_QWORD *)a2 + 4) - 8) -= v15;
        }
        while ( v19 < v12[2] );
      }
      if ( *((int *)this + 38) > 0 )
      {
        for ( j = (_DWORD *)*((_QWORD *)this + 20); *j != *(_DWORD *)a2; ++j )
        {
          if ( ++v2 >= *((int *)this + 38) )
            return 1;
        }
        *((_DWORD *)a2 + 6) = 1;
      }
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1004a2de0  mov     [rsp+arg_0], rbx
0x1004a2de5  mov     [rsp+arg_8], rbp
0x1004a2dea  mov     [rsp+arg_10], rsi
0x1004a2def  push    rdi
0x1004a2df0  push    r14
0x1004a2df2  push    r15
0x1004a2df4  sub     rsp, 30h
0x1004a2df8  xor     ebx, ebx
0x1004a2dfa  mov     rsi, rdx
0x1004a2dfd  movsxd  rdx, dword ptr [rcx+80h]
0x1004a2e04  mov     rbp, rcx
0x1004a2e07  mov     eax, ebx
0x1004a2e09  test    edx, edx
0x1004a2e0b  jle     short loc_1004A2E33
0x1004a2e0d  mov     ecx, [rsi]
0x1004a2e0f  mov     r8d, ebx
0x1004a2e12  mov     r9, [rbp+88h]
0x1004a2e19  nop     dword ptr [rax+00000000h]
0x1004a2e20  cmp     [r9], ecx
0x1004a2e23  jz      short loc_1004A2E51
0x1004a2e25  inc     eax
0x1004a2e27  inc     r8
0x1004a2e2a  add     r9, 10h
0x1004a2e2e  cmp     r8, rdx
0x1004a2e31  jl      short loc_1004A2E20
0x1004a2e33  mov     eax, 1
0x1004a2e38  mov     rbx, [rsp+48h+arg_0]
0x1004a2e3d  mov     rbp, [rsp+48h+arg_8]
0x1004a2e42  mov     rsi, [rsp+48h+arg_10]
0x1004a2e47  add     rsp, 30h
0x1004a2e4b  pop     r15
0x1004a2e4d  pop     r14
0x1004a2e4f  pop     rdi
0x1004a2e50  retn
0x1004a2e51  mov     dword ptr [rsi+14h], 1
0x1004a2e58  mov     rdx, [rbp+88h]
0x1004a2e5f  movsxd  rcx, eax
0x1004a2e62  add     rcx, rcx
0x1004a2e65  cmp     [rdx+rcx*8+4], bx
0x1004a2e6a  jnz     short loc_1004A2E8B
0x1004a2e6c  shl     r8, 4
0x1004a2e70  lea     rcx, [rdx+4]
0x1004a2e74  add     rcx, r8
0x1004a2e77  nop     word ptr [rax+rax+00000000h]
0x1004a2e80  inc     eax
0x1004a2e82  lea     rcx, [rcx+10h]
0x1004a2e86  cmp     [rcx], bx
0x1004a2e89  jz      short loc_1004A2E80
0x1004a2e8b  movsxd  rdi, eax
0x1004a2e8e  shl     rdi, 4
0x1004a2e92  add     rdi, rdx
0x1004a2e95  mov     rdx, cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a2e9c  movzx   ecx, word ptr [rdi+4]
0x1004a2ea0  shl     rcx, 4; Size
0x1004a2ea4  test    rdx, rdx
0x1004a2ea7  jnz     short loc_1004A2EB1
0x1004a2ea9  call    cs:__imp_malloc
0x1004a2eaf  jmp     short loc_1004A2EC9
0x1004a2eb1  mov     r9d, 8Bh
0x1004a2eb7  mov     [rsp+48h+var_28], 6
0x1004a2ebc  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sqlsort\\common\\sor"...
0x1004a2ec3  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004a2ec9  mov     [rsi+20h], rax
0x1004a2ecd  test    rax, rax
0x1004a2ed0  jz      loc_1004A2FC4
0x1004a2ed6  movzx   r8d, word ptr [rdi+4]
0x1004a2edb  mov     rdx, rdi; Src
0x1004a2ede  shl     r8, 4; Size
0x1004a2ee2  mov     rcx, rax; void *
0x1004a2ee5  call    memmove
0x1004a2eea  movzx   eax, word ptr [rdi+4]
0x1004a2eee  movzx   r14d, word ptr [rdi+8]
0x1004a2ef3  add     rax, rax
0x1004a2ef6  mov     rdx, cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a2efd  movzx   r15d, word ptr [rdi+rax*8-8]
0x1004a2f03  movzx   eax, word ptr [rdi+rax*8-6]
0x1004a2f08  add     r15d, eax
0x1004a2f0b  mov     ecx, r15d
0x1004a2f0e  sub     ecx, r14d
0x1004a2f11  shl     ecx, 3; Size
0x1004a2f14  test    rdx, rdx
0x1004a2f17  jnz     short loc_1004A2F21
0x1004a2f19  call    cs:__imp_malloc
0x1004a2f1f  jmp     short loc_1004A2F39
0x1004a2f21  mov     r9d, 8Bh
0x1004a2f27  mov     [rsp+48h+var_28], 6
0x1004a2f2c  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sqlsort\\common\\sor"...
0x1004a2f33  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004a2f39  mov     [rsi+28h], rax
0x1004a2f3d  mov     r9, rax
0x1004a2f40  test    rax, rax
0x1004a2f43  jz      short loc_1004A2FC4
0x1004a2f45  mov     rax, [rbp+90h]
0x1004a2f4c  mov     rcx, r9; void *
0x1004a2f4f  mov     r8d, r15d
0x1004a2f52  sub     r8, r14
0x1004a2f55  shl     r8, 3; Size
0x1004a2f59  lea     rdx, [rax+r14*8]; Src
0x1004a2f5d  call    memmove
0x1004a2f62  mov     edx, ebx
0x1004a2f64  cmp     bx, [rdi+4]
0x1004a2f68  jnb     short loc_1004A2F88
0x1004a2f6a  mov     rcx, rbx
0x1004a2f6d  nop     dword ptr [rax]
0x1004a2f70  mov     rax, [rsi+20h]
0x1004a2f74  lea     rcx, [rcx+10h]
0x1004a2f78  inc     edx
0x1004a2f7a  sub     [rcx+rax-8], r14w
0x1004a2f80  movzx   eax, word ptr [rdi+4]
0x1004a2f84  cmp     edx, eax
0x1004a2f86  jl      short loc_1004A2F70
0x1004a2f88  movsxd  rax, dword ptr [rbp+98h]
0x1004a2f8f  test    eax, eax
0x1004a2f91  jle     loc_1004A2E33
0x1004a2f97  mov     ecx, [rsi]
0x1004a2f99  mov     rdx, rax
0x1004a2f9c  mov     rax, [rbp+0A0h]
0x1004a2fa3  cmp     [rax], ecx
0x1004a2fa5  jz      short loc_1004A2FB8
0x1004a2fa7  inc     rbx
0x1004a2faa  add     rax, 4
0x1004a2fae  cmp     rbx, rdx
0x1004a2fb1  jl      short loc_1004A2FA3
0x1004a2fb3  jmp     loc_1004A2E33
0x1004a2fb8  mov     dword ptr [rsi+18h], 1
0x1004a2fbf  jmp     loc_1004A2E33
0x1004a2fc4  xor     eax, eax
0x1004a2fc6  jmp     loc_1004A2E38
```
