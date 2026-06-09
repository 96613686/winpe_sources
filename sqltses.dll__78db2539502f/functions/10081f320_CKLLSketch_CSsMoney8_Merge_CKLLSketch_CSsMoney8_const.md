# CKLLSketch<CSsMoney8>::Merge(CKLLSketch<CSsMoney8> const &)

- ea: `0x10081f320`
- end: `0x10081f5b5`
- name: `?Merge@?$CKLLSketch@VCSsMoney8@@@@QEAA?AW4KLLRETCODE@@AEBV1@@Z`
- size: `661`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x10081a240`

## callees

- `0x10081e080`
- `0x10081f320`
- `0x10081f5c0`
- `0x1008212a0`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10081f469`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081f4d2`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081f51b`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081f553`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081f55d`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081f567`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081f469`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081f4d2`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081f51b`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081f553`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081f55d`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081f567`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081f455`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081f4be`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081f50b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081f455`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081f4be`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081f50b`

## string_xrefs

- `0x10081f448`: `sql\ntdbms\common\sketches\KLLSketch.inl`
- `0x10081f4b1`: `sql\ntdbms\common\sketches\KLLSketch.inl`
- `0x10081f4fe`: `sql\ntdbms\common\sketches\KLLSketch.inl`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CKLLSketch<CSsMoney8>::Merge(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rdx
  unsigned __int64 v5; // rbx
  void *v7; // rdi
  void *v8; // rsi
  void *v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // r12
  unsigned __int16 *v12; // rax
  unsigned __int16 v13; // bp
  unsigned __int16 v14; // cx
  __int16 v15; // r8
  __int16 v16; // cx
  __int16 v17; // r8
  unsigned __int64 v18; // rax
  unsigned __int16 v19; // dx
  __int64 v20; // rax
  unsigned __int64 v21; // rbp
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // rax
  unsigned int v24; // ebp

  v4 = *(_QWORD *)(a1 + 24);
  v5 = 4 * (*(unsigned __int16 *)(v4 + 6) + 2LL * *(unsigned __int16 *)(v4 + 24)) + 116;
  if ( v5 < CKLLSketch<double>::GetEstimateMemReq(
              *(_QWORD *)(v4 + 32) + *(_QWORD *)(a2[3] + 32LL),
              *(unsigned __int16 *)(v4 + 2)) )
    return 6;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = a2[3];
  v11 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 32LL) + *(_QWORD *)(v10 + 32);
  v12 = (unsigned __int16 *)a2[4];
  v13 = *v12;
  if ( *v12 < v12[1] )
  {
    do
    {
      CKLLSketch<CSsMoney8>::Update(a1, *(_QWORD *)(a2[5] + 8LL * v13++));
      v12 = (unsigned __int16 *)a2[4];
    }
    while ( v13 < v12[1] );
    v10 = a2[3];
  }
  v14 = v12[1];
  v15 = *(_WORD *)(v10 + 24);
  if ( v14 == v15 )
    goto LABEL_22;
  if ( *(_WORD *)(v10 + 6) )
    v16 = v14 - *v12;
  else
    v16 = 0;
  v17 = v15 - v16;
  v18 = 8LL * (unsigned __int16)(v17 + *(_WORD *)(*(_QWORD *)(a1 + 24) + 24LL));
  if ( !is_mul_ok((unsigned __int16)(v17 + *(_WORD *)(*(_QWORD *)(a1 + 24) + 24LL)), 8u) )
    v18 = -1;
  v7 = operator new[](v18, *(struct IMemObj **)a1, "sql\\ntdbms\\common\\sketches\\KLLSketch.inl", 385, 3u);
  if ( !v7 )
  {
    v24 = 5;
    goto LABEL_23;
  }
  operator delete[](0);
  v19 = *(_WORD *)(a2[3] + 6LL);
  v20 = *(_QWORD *)(a1 + 24);
  if ( v19 <= *(_WORD *)(v20 + 6) )
    v19 = *(_WORD *)(v20 + 6);
  v21 = v19 + 2LL;
  v22 = 2 * v21;
  if ( !is_mul_ok(v21, 2u) )
    v22 = -1;
  v8 = operator new[](v22, *(struct IMemObj **)a1, "sql\\ntdbms\\common\\sketches\\KLLSketch.inl", 400, 3u);
  if ( !v8 )
  {
    v24 = 5;
    goto LABEL_23;
  }
  operator delete[](0);
  v23 = 2 * v21;
  if ( !is_mul_ok(v21, 2u) )
    v23 = -1;
  v9 = operator new[](v23, *(struct IMemObj **)a1, "sql\\ntdbms\\common\\sketches\\KLLSketch.inl", 409, 3u);
  if ( !v9 )
  {
    v24 = 5;
    goto LABEL_23;
  }
  operator delete[](0);
  v24 = CKLLSketch<CSsMoney8>::MergeHigherLevels(a1, (_DWORD)a2, (_DWORD)v7, (_DWORD)v8, (__int64)v9);
  if ( !v24 )
  {
LABEL_22:
    *(_QWORD *)(*(_QWORD *)(a1 + 24) + 32LL) = v11;
    v24 = 0;
  }
LABEL_23:
  operator delete[](v9);
  operator delete[](v8);
  operator delete[](v7);
  return v24;
}

```

## disassembly

```asm
0x10081f320  push    rbp
0x10081f322  push    rsi
0x10081f323  push    rdi
0x10081f324  push    r12
0x10081f326  push    r13
0x10081f328  push    r14
0x10081f32a  push    r15
0x10081f32c  sub     rsp, 40h
0x10081f330  mov     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFEh
0x10081f339  mov     [rsp+78h+arg_18], rbx
0x10081f341  mov     r14, rdx
0x10081f344  mov     r15, rcx
0x10081f347  mov     rdx, [rcx+18h]
0x10081f34b  movzx   r8d, word ptr [rdx+18h]
0x10081f350  movzx   eax, word ptr [rdx+6]
0x10081f354  lea     r8, [rax+r8*2]
0x10081f358  lea     rbx, ds:74h[r8*4]
0x10081f360  mov     rax, [r14+18h]
0x10081f364  mov     rcx, [rax+20h]
0x10081f368  add     rcx, [rdx+20h]
0x10081f36c  movzx   edx, word ptr [rdx+2]
0x10081f370  call    ?GetEstimateMemReq@?$CKLLSketch@N@@SA_K_KG@Z; CKLLSketch<double>::GetEstimateMemReq(unsigned __int64,ushort)
0x10081f375  cmp     rbx, rax
0x10081f378  jnb     short loc_10081F384
0x10081f37a  mov     eax, 6
0x10081f37f  jmp     loc_10081F56F
0x10081f384  xor     r13d, r13d
0x10081f387  mov     edi, r13d
0x10081f38a  mov     [rsp+78h+arg_10], r13
0x10081f392  mov     esi, r13d
0x10081f395  mov     [rsp+78h+arg_8], r13
0x10081f39d  mov     ebx, r13d
0x10081f3a0  mov     [rsp+78h+arg_0], rbx
0x10081f3a8  mov     rdx, [r14+18h]
0x10081f3ac  mov     rax, [r15+18h]
0x10081f3b0  mov     r12, [rdx+20h]
0x10081f3b4  add     r12, [rax+20h]
0x10081f3b8  mov     rax, [r14+20h]
0x10081f3bc  movzx   ebp, word ptr [rax]
0x10081f3bf  cmp     bp, [rax+2]
0x10081f3c3  jnb     short loc_10081F3F4
0x10081f3c5  nop     word ptr [rax+rax]
0x10081f3ca  nop     word ptr [rax+rax+00h]
0x10081f3d0  movzx   eax, bp
0x10081f3d3  mov     rdx, [r14+28h]
0x10081f3d7  mov     rdx, [rdx+rax*8]
0x10081f3db  mov     rcx, r15
0x10081f3de  call    ?Update@?$CKLLSketch@VCSsMoney8@@@@QEAA?AW4KLLRETCODE@@VCSsMoney8@@@Z; CKLLSketch<CSsMoney8>::Update(CSsMoney8)
0x10081f3e3  inc     bp
0x10081f3e6  mov     rax, [r14+20h]
0x10081f3ea  cmp     bp, [rax+2]
0x10081f3ee  jb      short loc_10081F3D0
0x10081f3f0  mov     rdx, [r14+18h]
0x10081f3f4  movzx   ecx, word ptr [rax+2]
0x10081f3f8  movzx   r8d, word ptr [rdx+18h]
0x10081f3fd  cmp     cx, r8w
0x10081f401  jz      loc_10081F545
0x10081f407  cmp     r13w, [rdx+6]
0x10081f40c  jb      short loc_10081F414
0x10081f40e  movzx   ecx, r13w
0x10081f412  jmp     short loc_10081F417
0x10081f414  sub     cx, [rax]
0x10081f417  sub     r8w, cx
0x10081f41b  mov     rax, [r15+18h]
0x10081f41f  movzx   ecx, word ptr [rax+18h]
0x10081f423  add     cx, r8w
0x10081f427  movzx   ecx, cx
0x10081f42a  mov     eax, 8
0x10081f42f  mul     rcx
0x10081f432  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081f439  cmovo   rax, rcx
0x10081f43d  mov     byte ptr [rsp+78h+var_58], 3
0x10081f442  mov     r9d, 181h
0x10081f448  lea     r8, aSqlNtdbmsCommo_1; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081f44f  mov     rdx, [r15]
0x10081f452  mov     rcx, rax
0x10081f455  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081f45b  mov     rdi, rax
0x10081f45e  test    rax, rax
0x10081f461  jz      loc_10081F5A5
0x10081f467  xor     ecx, ecx
0x10081f469  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081f46f  mov     [rsp+78h+arg_10], rdi
0x10081f477  mov     rax, [r14+18h]
0x10081f47b  movzx   edx, word ptr [rax+6]
0x10081f47f  mov     rax, [r15+18h]
0x10081f483  cmp     dx, [rax+6]
0x10081f487  cmovbe  dx, [rax+6]
0x10081f48c  movzx   ebp, dx
0x10081f48f  add     rbp, 2
0x10081f493  mov     eax, 2
0x10081f498  mul     rbp
0x10081f49b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081f4a2  cmovo   rax, rcx
0x10081f4a6  mov     byte ptr [rsp+78h+var_58], 3
0x10081f4ab  mov     r9d, 190h
0x10081f4b1  lea     r8, aSqlNtdbmsCommo_1; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081f4b8  mov     rdx, [r15]
0x10081f4bb  mov     rcx, rax
0x10081f4be  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081f4c4  mov     rsi, rax
0x10081f4c7  test    rax, rax
0x10081f4ca  jz      loc_10081F596
0x10081f4d0  xor     ecx, ecx
0x10081f4d2  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081f4d8  mov     [rsp+78h+arg_8], rsi
0x10081f4e0  mov     eax, 2
0x10081f4e5  mul     rbp
0x10081f4e8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081f4ef  cmovo   rax, rcx
0x10081f4f3  mov     byte ptr [rsp+78h+var_58], 3
0x10081f4f8  mov     r9d, 199h
0x10081f4fe  lea     r8, aSqlNtdbmsCommo_1; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081f505  mov     rdx, [r15]
0x10081f508  mov     rcx, rax
0x10081f50b  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081f511  mov     rbx, rax
0x10081f514  test    rax, rax
0x10081f517  jz      short loc_10081F587
0x10081f519  xor     ecx, ecx
0x10081f51b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081f521  mov     [rsp+78h+arg_0], rbx
0x10081f529  mov     [rsp+78h+var_58], rbx
0x10081f52e  mov     r9, rsi
0x10081f531  mov     r8, rdi
0x10081f534  mov     rdx, r14
0x10081f537  mov     rcx, r15
0x10081f53a  call    ?MergeHigherLevels@?$CKLLSketch@VCSsMoney8@@@@AEAA?AW4KLLRETCODE@@AEBV1@PEAVCSsMoney8@@PEAG2@Z; CKLLSketch<CSsMoney8>::MergeHigherLevels(CKLLSketch<CSsMoney8> const &,CSsMoney8 *,ushort *,ushort *)
0x10081f53f  mov     ebp, eax
0x10081f541  test    eax, eax
0x10081f543  jnz     short loc_10081F550
0x10081f545  mov     rax, [r15+18h]
0x10081f549  mov     [rax+20h], r12
0x10081f54d  mov     ebp, r13d
0x10081f550  mov     rcx, rbx
0x10081f553  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081f559  nop
0x10081f55a  mov     rcx, rsi
0x10081f55d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081f563  nop
0x10081f564  mov     rcx, rdi
0x10081f567  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081f56d  mov     eax, ebp
0x10081f56f  mov     rbx, [rsp+78h+arg_18]
0x10081f577  add     rsp, 40h
0x10081f57b  pop     r15
0x10081f57d  pop     r14
0x10081f57f  pop     r13
0x10081f581  pop     r12
0x10081f583  pop     rdi
0x10081f584  pop     rsi
0x10081f585  pop     rbp
0x10081f586  retn
0x10081f587  mov     [rsp+78h+arg_0], rbx
0x10081f58f  mov     ebp, 5
0x10081f594  jmp     short loc_10081F550
0x10081f596  mov     [rsp+78h+arg_8], rsi
0x10081f59e  mov     ebp, 5
0x10081f5a3  jmp     short loc_10081F550
0x10081f5a5  mov     [rsp+78h+arg_10], rdi
0x10081f5ad  mov     ebp, 5
0x10081f5b2  jmp     short loc_10081F550
```
