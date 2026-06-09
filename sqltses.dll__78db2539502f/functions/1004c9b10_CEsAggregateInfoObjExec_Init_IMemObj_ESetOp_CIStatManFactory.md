# CEsAggregateInfoObjExec::Init(IMemObj *,ESetOp,CIStatManFactory *)

- ea: `0x1004c9b10`
- end: `0x1004c9e07`
- name: `?Init@CEsAggregateInfoObjExec@@QEAAXPEAVIMemObj@@W4ESetOp@@PEAVCIStatManFactory@@@Z`
- size: `759`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1004c9a40`

## callees

- `0x10048cee0`
- `0x1004c89b0`
- `0x1004c9b10`

## import_xrefs

- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004c9b58`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004c9b97`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004c9bf9`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004c9c6d`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004c9cc3`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004c9b58`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004c9b97`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004c9bf9`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004c9c6d`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004c9cc3`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004c9d55`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004c9d8b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004c9dca`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004c9ddd`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004c9df0`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004c9d55`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004c9d8b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004c9dca`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004c9ddd`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004c9df0`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004c9d43`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004c9d79`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004c9daf`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004c9d43`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004c9d79`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004c9daf`

## string_xrefs

- `0x1004c9b89`: `sql\ntdbms\common\inc\approxcountdistincthelpers.h`
- `0x1004c9bee`: `sql\ntdbms\common\inc\approxcountdistincthelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CEsAggregateInfoObjExec::Init(__int64 a1, struct IMemObj *a2, int a3, __int64 a4)
{
  struct IMemObj **v7; // rax
  struct IMemObj **v8; // r14
  __int64 v9; // rbp
  _DWORD *v10; // rax
  void *v11; // rbx
  _QWORD *v12; // rax
  CMinMaxCounter *v13; // rax
  CMinMaxCounter *v14; // rbp
  CMinMaxCounter **v15; // rax
  signed __int64 v16; // rcx
  signed __int64 v17; // rax
  signed __int64 v18; // rax
  void *v19; // rbx
  void *v20; // rcx
  void *v21; // rbx
  void *v22; // rcx
  void *v23; // rcx
  bool v24; // zf
  void *v25; // rcx
  void *v26; // rcx
  _QWORD *v27; // [rsp+90h] [rbp+8h] BYREF
  struct IMemObj *v28; // [rsp+98h] [rbp+10h]
  int v29; // [rsp+A0h] [rbp+18h]
  __int64 v30; // [rsp+A8h] [rbp+20h]

  v30 = a4;
  v28 = a2;
  *(_DWORD *)(a1 + 16) = a3;
  v29 = 67;
  v7 = (struct IMemObj **)operator new(0x10u, a2, "sql\\ntdbms\\msql\\expr\\runtime\\esx_aggregateinfo.cpp", 67, 3u);
  v8 = v7;
  v9 = 4007;
  if ( v7 )
  {
    *v7 = a2;
    LODWORD(v27) = 73;
    v10 = operator new(0x20u, a2, "sql\\ntdbms\\common\\inc\\approxcountdistincthelpers.h", 73, 3u);
    v11 = 0;
    if ( v10 )
    {
      *(_QWORD *)v10 = a2;
      v10[3] = 0;
      v10[4] = 4007;
      *((_QWORD *)v10 + 3) = 0;
    }
    else
    {
      v10 = 0;
    }
    v8[1] = (struct IMemObj *)v10;
  }
  else
  {
    v11 = 0;
    v8 = 0;
  }
  *(_QWORD *)(a1 + 8) = v8;
  do
  {
    v29 = 86;
    v12 = operator new(0x10u, *v8, "sql\\ntdbms\\common\\inc\\approxcountdistincthelpers.h", 86, 1u);
    if ( v12 )
    {
      *v12 = 1;
      v12[1] = 0;
    }
    else
    {
      v12 = 0;
    }
    v27 = v12;
    CTDynArray<ApproxCountDistinctHashValueItem *,CFnI_Default<ApproxCountDistinctHashValueItem *>,CFnD_Ptr<ApproxCountDistinctHashValueItem>,CMemObjAlloc<0>>::UlAdd(
      v8[1],
      &v27);
    --v9;
  }
  while ( v9 );
  *(_QWORD *)(a1 + 72) = 0;
  if ( a4 )
  {
    v29 = 75;
    v13 = (CMinMaxCounter *)operator new(
                              0xA0u,
                              *(struct IMemObj **)(a4 + 8),
                              "sql\\ntdbms\\msql\\expr\\runtime\\esx_aggregateinfo.cpp",
                              75,
                              3u);
    v14 = v13
        ? CMinMaxCounter::CMinMaxCounter(
            v13,
            *(struct IMemObj **)(a4 + 8),
            *(struct CTypeInfo **)(a4 + 64),
            *(struct CColumnInfo **)(a4 + 56))
        : 0LL;
    *(_QWORD *)(a1 + 72) = v14;
    v29 = 528;
    v15 = (CMinMaxCounter **)operator new(
                               0x10u,
                               *(struct IMemObj **)(a4 + 8),
                               "sql\\ntdbms\\ntinc\\statisti.h",
                               528,
                               3u);
    v16 = (signed __int64)v15;
    if ( v15 )
    {
      *v15 = v14;
      v15[1] = 0;
    }
    else
    {
      v16 = 0;
    }
    v17 = *(_QWORD *)(a4 + 184);
    *(_QWORD *)(v16 + 8) = v17;
    if ( *(_QWORD *)(v16 + 8) != _InterlockedCompareExchange64((volatile signed __int64 *)(a4 + 184), v16, v17) )
    {
      _m_prefetchw((const void *)(a4 + 184));
      do
      {
        _mm_pause();
        v18 = *(_QWORD *)(a4 + 184);
        *(_QWORD *)(v16 + 8) = v18;
      }
      while ( *(_QWORD *)(v16 + 8) != _InterlockedCompareExchange64((volatile signed __int64 *)(a4 + 184), v16, v18) );
    }
  }
  if ( *(_BYTE *)(a1 + 56) )
  {
    v19 = operator new[](0x50140u, a2, "sql\\ntdbms\\msql\\expr\\runtime\\esx_aggregateinfo.cpp", 85, 3u);
    v20 = *(void **)(a1 + 24);
    if ( v20 != v19 )
      operator delete[](v20);
    *(_QWORD *)(a1 + 24) = v19;
    v21 = operator new[](0x50140u, a2, "sql\\ntdbms\\msql\\expr\\runtime\\esx_aggregateinfo.cpp", 86, 3u);
    v22 = *(void **)(a1 + 32);
    if ( v22 != v21 )
      operator delete[](v22);
    *(_QWORD *)(a1 + 32) = v21;
    v11 = operator new[](0x50140u, a2, "sql\\ntdbms\\msql\\expr\\runtime\\esx_aggregateinfo.cpp", 87, 3u);
    v23 = *(void **)(a1 + 40);
    v24 = v23 == v11;
  }
  else
  {
    v25 = *(void **)(a1 + 24);
    if ( v25 )
      operator delete[](v25);
    *(_QWORD *)(a1 + 24) = 0;
    v26 = *(void **)(a1 + 32);
    if ( v26 )
      operator delete[](v26);
    *(_QWORD *)(a1 + 32) = 0;
    v23 = *(void **)(a1 + 40);
    v24 = v23 == 0;
  }
  if ( !v24 )
    operator delete[](v23);
  *(_QWORD *)(a1 + 40) = v11;
}

```

## disassembly

```asm
0x1004c9b10  mov     rax, rsp
0x1004c9b13  mov     [rax+20h], r9
0x1004c9b17  mov     [rax+10h], rdx
0x1004c9b1b  push    rbx
0x1004c9b1c  push    rbp
0x1004c9b1d  push    rsi
0x1004c9b1e  push    rdi
0x1004c9b1f  push    r14
0x1004c9b21  push    r15
0x1004c9b23  sub     rsp, 58h
0x1004c9b27  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x1004c9b2f  mov     rsi, r9
0x1004c9b32  mov     r15, rdx
0x1004c9b35  mov     rdi, rcx
0x1004c9b38  mov     [rcx+10h], r8d
0x1004c9b3c  mov     dword ptr [rax+18h], 43h ; 'C'
0x1004c9b43  mov     byte ptr [rax-68h], 3
0x1004c9b47  mov     r9d, 43h ; 'C'
0x1004c9b4d  lea     r8, aSqlNtdbmsMsqlE_15; "sql\\ntdbms\\msql\\expr\\runtime\\esx_a"...
0x1004c9b54  lea     ecx, [r9-33h]
0x1004c9b58  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004c9b5e  mov     r14, rax
0x1004c9b61  mov     [rsp+88h+var_50], rax
0x1004c9b66  mov     ebp, 0FA7h
0x1004c9b6b  test    rax, rax
0x1004c9b6e  jz      short loc_1004C9BC1
0x1004c9b70  mov     [rax], r15
0x1004c9b73  mov     dword ptr [rsp+88h+arg_0], 49h ; 'I'
0x1004c9b7e  mov     [rsp+88h+var_68], 3
0x1004c9b83  mov     r9d, 49h ; 'I'
0x1004c9b89  lea     r8, aSqlNtdbmsCommo_3; "sql\\ntdbms\\common\\inc\\approxcountdi"...
0x1004c9b90  mov     rdx, r15
0x1004c9b93  lea     ecx, [r9-29h]
0x1004c9b97  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004c9b9d  mov     [rsp+88h+var_48], rax
0x1004c9ba2  xor     ebx, ebx
0x1004c9ba4  test    rax, rax
0x1004c9ba7  jz      short loc_1004C9BB8
0x1004c9ba9  mov     [rax], r15
0x1004c9bac  mov     [rax+0Ch], ebx
0x1004c9baf  mov     [rax+10h], ebp
0x1004c9bb2  mov     [rax+18h], rbx
0x1004c9bb6  jmp     short loc_1004C9BBB
0x1004c9bb8  mov     rax, rbx
0x1004c9bbb  mov     [r14+8], rax
0x1004c9bbf  jmp     short loc_1004C9BC6
0x1004c9bc1  xor     ebx, ebx
0x1004c9bc3  mov     r14d, ebx
0x1004c9bc6  mov     [rdi+8], r14
0x1004c9bca  nop     word ptr [rax+rax+00h]
0x1004c9bd0  mov     [rsp+88h+arg_10], 56h ; 'V'
0x1004c9bdb  mov     rdx, [r14]
0x1004c9bde  mov     [rsp+88h+var_48], rdx
0x1004c9be3  mov     [rsp+88h+var_68], 1
0x1004c9be8  mov     r9d, 56h ; 'V'
0x1004c9bee  lea     r8, aSqlNtdbmsCommo_3; "sql\\ntdbms\\common\\inc\\approxcountdi"...
0x1004c9bf5  lea     ecx, [r9-46h]
0x1004c9bf9  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004c9bff  mov     [rsp+88h+var_50], rax
0x1004c9c04  test    rax, rax
0x1004c9c07  jz      short loc_1004C9C16
0x1004c9c09  mov     qword ptr [rax], 1
0x1004c9c10  mov     [rax+8], rbx
0x1004c9c14  jmp     short loc_1004C9C19
0x1004c9c16  mov     rax, rbx
0x1004c9c19  mov     [rsp+88h+arg_0], rax
0x1004c9c21  lea     rdx, [rsp+88h+arg_0]
0x1004c9c29  mov     rcx, [r14+8]
0x1004c9c2d  call    ?UlAdd@?$CTDynArray@PEAUApproxCountDistinctHashValueItem@@V?$CFnI_Default@PEAUApproxCountDistinctHashValueItem@@@@V?$CFnD_Ptr@UApproxCountDistinctHashValueItem@@@@V?$CMemObjAlloc@$0A@@@@@QEAAKAEBQEAUApproxCountDistinctHashValueItem@@@Z; CTDynArray<ApproxCountDistinctHashValueItem *,CFnI_Default<ApproxCountDistinctHashValueItem *>,CFnD_Ptr<ApproxCountDistinctHashValueItem>,CMemObjAlloc<0>>::UlAdd(ApproxCountDistinctHashValueItem * const &)
0x1004c9c32  sub     rbp, 1
0x1004c9c36  jnz     short loc_1004C9BD0
0x1004c9c38  mov     [rdi+48h], rbx
0x1004c9c3c  test    rsi, rsi
0x1004c9c3f  jz      loc_1004C9D1F
0x1004c9c45  mov     [rsp+88h+arg_10], 4Bh ; 'K'
0x1004c9c50  mov     rdx, [rsi+8]
0x1004c9c54  mov     [rsp+88h+var_48], rdx
0x1004c9c59  mov     [rsp+88h+var_68], 3
0x1004c9c5e  lea     r9d, [rbp+4Bh]
0x1004c9c62  lea     r8, aSqlNtdbmsMsqlE_15; "sql\\ntdbms\\msql\\expr\\runtime\\esx_a"...
0x1004c9c69  lea     ecx, [r9+55h]
0x1004c9c6d  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004c9c73  mov     [rsp+88h+var_50], rax
0x1004c9c78  test    rax, rax
0x1004c9c7b  jz      short loc_1004C9C96
0x1004c9c7d  mov     r9, [rsi+38h]; struct CColumnInfo *
0x1004c9c81  mov     r8, [rsi+40h]; struct CTypeInfo *
0x1004c9c85  mov     rdx, [rsi+8]; struct IMemObj *
0x1004c9c89  mov     rcx, rax; this
0x1004c9c8c  call    ??0CMinMaxCounter@@QEAA@PEAVIMemObj@@PEAVCTypeInfo@@PEAVCColumnInfo@@@Z; CMinMaxCounter::CMinMaxCounter(IMemObj *,CTypeInfo *,CColumnInfo *)
0x1004c9c91  mov     rbp, rax
0x1004c9c94  jmp     short loc_1004C9C99
0x1004c9c96  mov     rbp, rbx
0x1004c9c99  mov     [rdi+48h], rbp
0x1004c9c9d  mov     [rsp+88h+arg_10], 210h
0x1004c9ca8  mov     [rsp+88h+var_68], 3
0x1004c9cad  mov     r9d, 210h
0x1004c9cb3  lea     r8, aSqlNtdbmsNtinc; "sql\\ntdbms\\ntinc\\statisti.h"
0x1004c9cba  mov     rdx, [rsi+8]
0x1004c9cbe  mov     ecx, 10h
0x1004c9cc3  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004c9cc9  mov     rcx, rax
0x1004c9ccc  mov     [rsp+88h+var_48], rax
0x1004c9cd1  test    rax, rax
0x1004c9cd4  jz      short loc_1004C9CDF
0x1004c9cd6  mov     [rax], rbp
0x1004c9cd9  mov     [rax+8], rbx
0x1004c9cdd  jmp     short loc_1004C9CE2
0x1004c9cdf  mov     rcx, rbx
0x1004c9ce2  mov     rax, [rsi+0B8h]
0x1004c9ce9  mov     [rcx+8], rax
0x1004c9ced  lock cmpxchg [rsi+0B8h], rcx
0x1004c9cf6  cmp     [rcx+8], rax
0x1004c9cfa  jz      short loc_1004C9D1F
0x1004c9cfc  prefetchw byte ptr [rsi+0B8h]
0x1004c9d03  pause
0x1004c9d05  mov     rax, [rsi+0B8h]
0x1004c9d0c  mov     [rcx+8], rax
0x1004c9d10  lock cmpxchg [rsi+0B8h], rcx
0x1004c9d19  cmp     [rcx+8], rax
0x1004c9d1d  jnz     short loc_1004C9D03
0x1004c9d1f  cmp     byte ptr [rdi+38h], 0
0x1004c9d23  jz      loc_1004C9DC1
0x1004c9d29  mov     [rsp+88h+var_68], 3
0x1004c9d2e  mov     r9d, 55h ; 'U'
0x1004c9d34  lea     r8, aSqlNtdbmsMsqlE_15; "sql\\ntdbms\\msql\\expr\\runtime\\esx_a"...
0x1004c9d3b  mov     rdx, r15
0x1004c9d3e  mov     ecx, 50140h
0x1004c9d43  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004c9d49  mov     rbx, rax
0x1004c9d4c  mov     rcx, [rdi+18h]
0x1004c9d50  cmp     rcx, rax
0x1004c9d53  jz      short loc_1004C9D5B
0x1004c9d55  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1004c9d5b  mov     [rdi+18h], rbx
0x1004c9d5f  mov     [rsp+88h+var_68], 3
0x1004c9d64  mov     r9d, 56h ; 'V'
0x1004c9d6a  lea     r8, aSqlNtdbmsMsqlE_15; "sql\\ntdbms\\msql\\expr\\runtime\\esx_a"...
0x1004c9d71  mov     rdx, r15
0x1004c9d74  mov     ecx, 50140h
0x1004c9d79  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004c9d7f  mov     rbx, rax
0x1004c9d82  mov     rcx, [rdi+20h]
0x1004c9d86  cmp     rcx, rax
0x1004c9d89  jz      short loc_1004C9D91
0x1004c9d8b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1004c9d91  mov     [rdi+20h], rbx
0x1004c9d95  mov     [rsp+88h+var_68], 3
0x1004c9d9a  mov     r9d, 57h ; 'W'
0x1004c9da0  lea     r8, aSqlNtdbmsMsqlE_15; "sql\\ntdbms\\msql\\expr\\runtime\\esx_a"...
0x1004c9da7  mov     rdx, r15
0x1004c9daa  mov     ecx, 50140h
0x1004c9daf  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004c9db5  mov     rbx, rax
0x1004c9db8  mov     rcx, [rdi+28h]
0x1004c9dbc  cmp     rcx, rax
0x1004c9dbf  jmp     short loc_1004C9DEE
0x1004c9dc1  mov     rcx, [rdi+18h]
0x1004c9dc5  test    rcx, rcx
0x1004c9dc8  jz      short loc_1004C9DD0
0x1004c9dca  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1004c9dd0  mov     [rdi+18h], rbx
0x1004c9dd4  mov     rcx, [rdi+20h]
0x1004c9dd8  test    rcx, rcx
0x1004c9ddb  jz      short loc_1004C9DE3
0x1004c9ddd  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1004c9de3  mov     [rdi+20h], rbx
0x1004c9de7  mov     rcx, [rdi+28h]
0x1004c9deb  test    rcx, rcx
0x1004c9dee  jz      short loc_1004C9DF6
0x1004c9df0  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1004c9df6  mov     [rdi+28h], rbx
0x1004c9dfa  add     rsp, 58h
0x1004c9dfe  pop     r15
0x1004c9e00  pop     r14
0x1004c9e02  pop     rdi
0x1004c9e03  pop     rsi
0x1004c9e04  pop     rbp
0x1004c9e05  pop     rbx
0x1004c9e06  retn
```
