# CKLLSketch<long>::Merge(CKLLSketch<long> const &)

- ea: `0x10081d3d0`
- end: `0x10081d664`
- name: `?Merge@?$CKLLSketch@J@@QEAA?AW4KLLRETCODE@@AEBV1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x10081a240`

## callees

- `0x10081d3d0`
- `0x10081d670`
- `0x10081d9f0`
- `0x100820550`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10081d518`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081d581`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081d5ca`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081d602`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081d60c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081d616`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081d518`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081d581`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081d5ca`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081d602`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081d60c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081d616`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081d504`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081d56d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081d5ba`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081d504`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081d56d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081d5ba`

## string_xrefs

- `0x10081d4f7`: `sql\ntdbms\common\sketches\KLLSketch.inl`
- `0x10081d560`: `sql\ntdbms\common\sketches\KLLSketch.inl`
- `0x10081d5ad`: `sql\ntdbms\common\sketches\KLLSketch.inl`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CKLLSketch<long>::Merge(__int64 a1, _QWORD *a2)
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
  v5 = 4 * (*(unsigned __int16 *)(v4 + 6) + (unsigned __int64)*(unsigned __int16 *)(v4 + 24)) + 116;
  if ( v5 < CKLLSketch<float>::GetEstimateMemReq(
              *(_QWORD *)(a2[3] + 32LL) + *(_QWORD *)(v4 + 32),
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
      CKLLSketch<long>::Update(a1, *(unsigned int *)(a2[5] + 4LL * v13++));
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
  v18 = 4LL * (unsigned __int16)(v17 + *(_WORD *)(*(_QWORD *)(a1 + 24) + 24LL));
  if ( !is_mul_ok((unsigned __int16)(v17 + *(_WORD *)(*(_QWORD *)(a1 + 24) + 24LL)), 4u) )
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
  v24 = CKLLSketch<long>::MergeHigherLevels(a1, (_DWORD)a2, (_DWORD)v7, (_DWORD)v8, (__int64)v9);
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
0x10081d3d0  push    rbp
0x10081d3d2  push    rsi
0x10081d3d3  push    rdi
0x10081d3d4  push    r12
0x10081d3d6  push    r13
0x10081d3d8  push    r14
0x10081d3da  push    r15
0x10081d3dc  sub     rsp, 40h
0x10081d3e0  mov     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFEh
0x10081d3e9  mov     [rsp+78h+arg_18], rbx
0x10081d3f1  mov     r14, rdx
0x10081d3f4  mov     r15, rcx
0x10081d3f7  mov     rdx, [rcx+18h]
0x10081d3fb  movzx   r8d, word ptr [rdx+18h]
0x10081d400  movzx   eax, word ptr [rdx+6]
0x10081d404  add     r8, rax
0x10081d407  lea     rbx, ds:74h[r8*4]
0x10081d40f  mov     rax, [r14+18h]
0x10081d413  mov     rcx, [rdx+20h]
0x10081d417  add     rcx, [rax+20h]
0x10081d41b  movzx   edx, word ptr [rdx+2]
0x10081d41f  call    ?GetEstimateMemReq@?$CKLLSketch@M@@SA_K_KG@Z; CKLLSketch<float>::GetEstimateMemReq(unsigned __int64,ushort)
0x10081d424  cmp     rbx, rax
0x10081d427  jnb     short loc_10081D433
0x10081d429  mov     eax, 6
0x10081d42e  jmp     loc_10081D61E
0x10081d433  xor     r13d, r13d
0x10081d436  mov     edi, r13d
0x10081d439  mov     [rsp+78h+arg_10], r13
0x10081d441  mov     esi, r13d
0x10081d444  mov     [rsp+78h+arg_8], r13
0x10081d44c  mov     ebx, r13d
0x10081d44f  mov     [rsp+78h+arg_0], rbx
0x10081d457  mov     rdx, [r14+18h]
0x10081d45b  mov     rax, [r15+18h]
0x10081d45f  mov     r12, [rdx+20h]
0x10081d463  add     r12, [rax+20h]
0x10081d467  mov     rax, [r14+20h]
0x10081d46b  movzx   ebp, word ptr [rax]
0x10081d46e  cmp     bp, [rax+2]
0x10081d472  jnb     short loc_10081D4A3
0x10081d474  nop     dword ptr [rax+00h]
0x10081d478  nop     dword ptr [rax+rax+00000000h]
0x10081d480  movzx   ecx, bp
0x10081d483  mov     rax, [r14+28h]
0x10081d487  mov     edx, [rax+rcx*4]
0x10081d48a  mov     rcx, r15
0x10081d48d  call    ?Update@?$CKLLSketch@J@@QEAA?AW4KLLRETCODE@@J@Z; CKLLSketch<long>::Update(long)
0x10081d492  inc     bp
0x10081d495  mov     rax, [r14+20h]
0x10081d499  cmp     bp, [rax+2]
0x10081d49d  jb      short loc_10081D480
0x10081d49f  mov     rdx, [r14+18h]
0x10081d4a3  movzx   ecx, word ptr [rax+2]
0x10081d4a7  movzx   r8d, word ptr [rdx+18h]
0x10081d4ac  cmp     cx, r8w
0x10081d4b0  jz      loc_10081D5F4
0x10081d4b6  cmp     r13w, [rdx+6]
0x10081d4bb  jb      short loc_10081D4C3
0x10081d4bd  movzx   ecx, r13w
0x10081d4c1  jmp     short loc_10081D4C6
0x10081d4c3  sub     cx, [rax]
0x10081d4c6  sub     r8w, cx
0x10081d4ca  mov     rax, [r15+18h]
0x10081d4ce  movzx   ecx, word ptr [rax+18h]
0x10081d4d2  add     cx, r8w
0x10081d4d6  movzx   ecx, cx
0x10081d4d9  mov     eax, 4
0x10081d4de  mul     rcx
0x10081d4e1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081d4e8  cmovo   rax, rcx
0x10081d4ec  mov     byte ptr [rsp+78h+var_58], 3
0x10081d4f1  mov     r9d, 181h
0x10081d4f7  lea     r8, aSqlNtdbmsCommo_1; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081d4fe  mov     rdx, [r15]
0x10081d501  mov     rcx, rax
0x10081d504  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081d50a  mov     rdi, rax
0x10081d50d  test    rax, rax
0x10081d510  jz      loc_10081D654
0x10081d516  xor     ecx, ecx
0x10081d518  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081d51e  mov     [rsp+78h+arg_10], rdi
0x10081d526  mov     rax, [r14+18h]
0x10081d52a  movzx   edx, word ptr [rax+6]
0x10081d52e  mov     rax, [r15+18h]
0x10081d532  cmp     dx, [rax+6]
0x10081d536  cmovbe  dx, [rax+6]
0x10081d53b  movzx   ebp, dx
0x10081d53e  add     rbp, 2
0x10081d542  mov     eax, 2
0x10081d547  mul     rbp
0x10081d54a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081d551  cmovo   rax, rcx
0x10081d555  mov     byte ptr [rsp+78h+var_58], 3
0x10081d55a  mov     r9d, 190h
0x10081d560  lea     r8, aSqlNtdbmsCommo_1; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081d567  mov     rdx, [r15]
0x10081d56a  mov     rcx, rax
0x10081d56d  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081d573  mov     rsi, rax
0x10081d576  test    rax, rax
0x10081d579  jz      loc_10081D645
0x10081d57f  xor     ecx, ecx
0x10081d581  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081d587  mov     [rsp+78h+arg_8], rsi
0x10081d58f  mov     eax, 2
0x10081d594  mul     rbp
0x10081d597  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081d59e  cmovo   rax, rcx
0x10081d5a2  mov     byte ptr [rsp+78h+var_58], 3
0x10081d5a7  mov     r9d, 199h
0x10081d5ad  lea     r8, aSqlNtdbmsCommo_1; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081d5b4  mov     rdx, [r15]
0x10081d5b7  mov     rcx, rax
0x10081d5ba  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081d5c0  mov     rbx, rax
0x10081d5c3  test    rax, rax
0x10081d5c6  jz      short loc_10081D636
0x10081d5c8  xor     ecx, ecx
0x10081d5ca  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081d5d0  mov     [rsp+78h+arg_0], rbx
0x10081d5d8  mov     [rsp+78h+var_58], rbx
0x10081d5dd  mov     r9, rsi
0x10081d5e0  mov     r8, rdi
0x10081d5e3  mov     rdx, r14
0x10081d5e6  mov     rcx, r15
0x10081d5e9  call    ?MergeHigherLevels@?$CKLLSketch@J@@AEAA?AW4KLLRETCODE@@AEBV1@PEAJPEAG2@Z; CKLLSketch<long>::MergeHigherLevels(CKLLSketch<long> const &,long *,ushort *,ushort *)
0x10081d5ee  mov     ebp, eax
0x10081d5f0  test    eax, eax
0x10081d5f2  jnz     short loc_10081D5FF
0x10081d5f4  mov     rax, [r15+18h]
0x10081d5f8  mov     [rax+20h], r12
0x10081d5fc  mov     ebp, r13d
0x10081d5ff  mov     rcx, rbx
0x10081d602  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081d608  nop
0x10081d609  mov     rcx, rsi
0x10081d60c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081d612  nop
0x10081d613  mov     rcx, rdi
0x10081d616  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081d61c  mov     eax, ebp
0x10081d61e  mov     rbx, [rsp+78h+arg_18]
0x10081d626  add     rsp, 40h
0x10081d62a  pop     r15
0x10081d62c  pop     r14
0x10081d62e  pop     r13
0x10081d630  pop     r12
0x10081d632  pop     rdi
0x10081d633  pop     rsi
0x10081d634  pop     rbp
0x10081d635  retn
0x10081d636  mov     [rsp+78h+arg_0], rbx
0x10081d63e  mov     ebp, 5
0x10081d643  jmp     short loc_10081D5FF
0x10081d645  mov     [rsp+78h+arg_8], rsi
0x10081d64d  mov     ebp, 5
0x10081d652  jmp     short loc_10081D5FF
0x10081d654  mov     [rsp+78h+arg_10], rdi
0x10081d65c  mov     ebp, 5
0x10081d661  jmp     short loc_10081D5FF
```
