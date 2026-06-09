# CKLLSketch<CSsNumeric>::Merge(CKLLSketch<CSsNumeric> const &)

- ea: `0x10081f940`
- end: `0x10081fbeb`
- name: `?Merge@?$CKLLSketch@VCSsNumeric@@@@QEAA?AW4KLLRETCODE@@AEBV1@@Z`
- size: `683`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x10081a240`

## callees

- `0x10081f940`
- `0x10081fc00`
- `0x10081fff0`
- `0x1008214d0`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10081fa9f`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081fb08`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081fb51`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081fb89`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081fb93`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081fb9d`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081fa9f`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081fb08`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081fb51`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081fb89`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081fb93`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081fb9d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081fa8b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081faf4`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081fb41`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081fa8b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081faf4`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081fb41`

## string_xrefs

- `0x10081fa7e`: `sql\ntdbms\common\sketches\KLLSketch.inl`
- `0x10081fae7`: `sql\ntdbms\common\sketches\KLLSketch.inl`
- `0x10081fb34`: `sql\ntdbms\common\sketches\KLLSketch.inl`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CKLLSketch<CSsNumeric>::Merge(__int64 a1, _QWORD *a2)
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
  __int64 v14; // rax
  unsigned __int16 v15; // cx
  __int16 v16; // r8
  __int16 v17; // cx
  __int16 v18; // r8
  unsigned __int64 v19; // rax
  unsigned __int16 v20; // dx
  __int64 v21; // rax
  unsigned __int64 v22; // rbp
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rax
  unsigned int v25; // ebp
  __int128 v26; // [rsp+40h] [rbp-58h] BYREF
  int v27; // [rsp+50h] [rbp-48h]

  v4 = *(_QWORD *)(a1 + 24);
  v5 = 4 * (*(unsigned __int16 *)(v4 + 6) + 5LL * *(unsigned __int16 *)(v4 + 24)) + 116;
  if ( v5 < CKLLSketch<CSsNumeric>::GetEstimateMemReq(
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
      v14 = a2[5];
      v26 = *(_OWORD *)(v14 + 20LL * v13);
      v27 = *(_DWORD *)(v14 + 20LL * v13 + 16);
      CKLLSketch<CSsNumeric>::Update(a1, &v26);
      ++v13;
      v12 = (unsigned __int16 *)a2[4];
    }
    while ( v13 < v12[1] );
    v10 = a2[3];
  }
  v15 = v12[1];
  v16 = *(_WORD *)(v10 + 24);
  if ( v15 == v16 )
    goto LABEL_22;
  if ( *(_WORD *)(v10 + 6) )
    v17 = v15 - *v12;
  else
    v17 = 0;
  v18 = v16 - v17;
  v19 = 20LL * (unsigned __int16)(v18 + *(_WORD *)(*(_QWORD *)(a1 + 24) + 24LL));
  if ( !is_mul_ok((unsigned __int16)(v18 + *(_WORD *)(*(_QWORD *)(a1 + 24) + 24LL)), 0x14u) )
    v19 = -1;
  v7 = operator new[](v19, *(struct IMemObj **)a1, "sql\\ntdbms\\common\\sketches\\KLLSketch.inl", 385, 3u);
  if ( !v7 )
  {
    v25 = 5;
    goto LABEL_23;
  }
  operator delete[](0);
  v20 = *(_WORD *)(a2[3] + 6LL);
  v21 = *(_QWORD *)(a1 + 24);
  if ( v20 <= *(_WORD *)(v21 + 6) )
    v20 = *(_WORD *)(v21 + 6);
  v22 = v20 + 2LL;
  v23 = 2 * v22;
  if ( !is_mul_ok(v22, 2u) )
    v23 = -1;
  v8 = operator new[](v23, *(struct IMemObj **)a1, "sql\\ntdbms\\common\\sketches\\KLLSketch.inl", 400, 3u);
  if ( !v8 )
  {
    v25 = 5;
    goto LABEL_23;
  }
  operator delete[](0);
  v24 = 2 * v22;
  if ( !is_mul_ok(v22, 2u) )
    v24 = -1;
  v9 = operator new[](v24, *(struct IMemObj **)a1, "sql\\ntdbms\\common\\sketches\\KLLSketch.inl", 409, 3u);
  if ( !v9 )
  {
    v25 = 5;
    goto LABEL_23;
  }
  operator delete[](0);
  v25 = CKLLSketch<CSsNumeric>::MergeHigherLevels(a1, (_DWORD)a2, (_DWORD)v7, (_DWORD)v8, (__int64)v9);
  if ( !v25 )
  {
LABEL_22:
    *(_QWORD *)(*(_QWORD *)(a1 + 24) + 32LL) = v11;
    v25 = 0;
  }
LABEL_23:
  operator delete[](v9);
  operator delete[](v8);
  operator delete[](v7);
  return v25;
}

```

## disassembly

```asm
0x10081f940  push    rbp
0x10081f942  push    rsi
0x10081f943  push    rdi
0x10081f944  push    r12
0x10081f946  push    r13
0x10081f948  push    r14
0x10081f94a  push    r15
0x10081f94c  sub     rsp, 60h
0x10081f950  mov     [rsp+98h+var_68], 0FFFFFFFFFFFFFFFEh
0x10081f959  mov     [rsp+98h+arg_18], rbx
0x10081f961  mov     r14, rdx
0x10081f964  mov     r15, rcx
0x10081f967  mov     rdx, [rcx+18h]
0x10081f96b  movzx   eax, word ptr [rdx+18h]
0x10081f96f  lea     r8, [rax+rax*4]
0x10081f973  movzx   eax, word ptr [rdx+6]
0x10081f977  add     r8, rax
0x10081f97a  lea     rbx, ds:74h[r8*4]
0x10081f982  mov     rax, [r14+18h]
0x10081f986  mov     rcx, [rdx+20h]
0x10081f98a  add     rcx, [rax+20h]
0x10081f98e  movzx   edx, word ptr [rdx+2]
0x10081f992  call    ?GetEstimateMemReq@?$CKLLSketch@VCSsNumeric@@@@SA_K_KG@Z; CKLLSketch<CSsNumeric>::GetEstimateMemReq(unsigned __int64,ushort)
0x10081f997  cmp     rbx, rax
0x10081f99a  jnb     short loc_10081F9A6
0x10081f99c  mov     eax, 6
0x10081f9a1  jmp     loc_10081FBA5
0x10081f9a6  xor     r13d, r13d
0x10081f9a9  mov     edi, r13d
0x10081f9ac  mov     [rsp+98h+arg_10], r13
0x10081f9b4  mov     esi, r13d
0x10081f9b7  mov     [rsp+98h+arg_8], r13
0x10081f9bf  mov     ebx, r13d
0x10081f9c2  mov     [rsp+98h+arg_0], rbx
0x10081f9ca  mov     rdx, [r14+18h]
0x10081f9ce  mov     rax, [r15+18h]
0x10081f9d2  mov     r12, [rdx+20h]
0x10081f9d6  add     r12, [rax+20h]
0x10081f9da  mov     rax, [r14+20h]
0x10081f9de  movzx   ebp, word ptr [rax]
0x10081f9e1  cmp     bp, [rax+2]
0x10081f9e5  jnb     short loc_10081FA2A
0x10081f9e7  nop     word ptr [rax+rax]
0x10081f9ec  nop     dword ptr [rax+00h]
0x10081f9f0  movzx   eax, bp
0x10081f9f3  lea     rcx, [rax+rax*4]
0x10081f9f7  mov     rax, [r14+28h]
0x10081f9fb  movups  xmm0, xmmword ptr [rax+rcx*4]
0x10081f9ff  movaps  [rsp+98h+var_58], xmm0
0x10081fa04  mov     eax, [rax+rcx*4+10h]
0x10081fa08  mov     [rsp+98h+var_48], eax
0x10081fa0c  lea     rdx, [rsp+98h+var_58]
0x10081fa11  mov     rcx, r15
0x10081fa14  call    ?Update@?$CKLLSketch@VCSsNumeric@@@@QEAA?AW4KLLRETCODE@@VCSsNumeric@@@Z; CKLLSketch<CSsNumeric>::Update(CSsNumeric)
0x10081fa19  inc     bp
0x10081fa1c  mov     rax, [r14+20h]
0x10081fa20  cmp     bp, [rax+2]
0x10081fa24  jb      short loc_10081F9F0
0x10081fa26  mov     rdx, [r14+18h]
0x10081fa2a  movzx   ecx, word ptr [rax+2]
0x10081fa2e  movzx   r8d, word ptr [rdx+18h]
0x10081fa33  cmp     cx, r8w
0x10081fa37  jz      loc_10081FB7B
0x10081fa3d  cmp     r13w, [rdx+6]
0x10081fa42  jb      short loc_10081FA4A
0x10081fa44  movzx   ecx, r13w
0x10081fa48  jmp     short loc_10081FA4D
0x10081fa4a  sub     cx, [rax]
0x10081fa4d  sub     r8w, cx
0x10081fa51  mov     rax, [r15+18h]
0x10081fa55  movzx   ecx, word ptr [rax+18h]
0x10081fa59  add     cx, r8w
0x10081fa5d  movzx   ecx, cx
0x10081fa60  mov     eax, 14h
0x10081fa65  mul     rcx
0x10081fa68  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081fa6f  cmovo   rax, rcx
0x10081fa73  mov     byte ptr [rsp+98h+var_78], 3
0x10081fa78  mov     r9d, 181h
0x10081fa7e  lea     r8, aSqlNtdbmsCommo_1; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081fa85  mov     rdx, [r15]
0x10081fa88  mov     rcx, rax
0x10081fa8b  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081fa91  mov     rdi, rax
0x10081fa94  test    rax, rax
0x10081fa97  jz      loc_10081FBDB
0x10081fa9d  xor     ecx, ecx
0x10081fa9f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081faa5  mov     [rsp+98h+arg_10], rdi
0x10081faad  mov     rax, [r14+18h]
0x10081fab1  movzx   edx, word ptr [rax+6]
0x10081fab5  mov     rax, [r15+18h]
0x10081fab9  cmp     dx, [rax+6]
0x10081fabd  cmovbe  dx, [rax+6]
0x10081fac2  movzx   ebp, dx
0x10081fac5  add     rbp, 2
0x10081fac9  mov     eax, 2
0x10081face  mul     rbp
0x10081fad1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081fad8  cmovo   rax, rcx
0x10081fadc  mov     byte ptr [rsp+98h+var_78], 3
0x10081fae1  mov     r9d, 190h
0x10081fae7  lea     r8, aSqlNtdbmsCommo_1; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081faee  mov     rdx, [r15]
0x10081faf1  mov     rcx, rax
0x10081faf4  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081fafa  mov     rsi, rax
0x10081fafd  test    rax, rax
0x10081fb00  jz      loc_10081FBCC
0x10081fb06  xor     ecx, ecx
0x10081fb08  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081fb0e  mov     [rsp+98h+arg_8], rsi
0x10081fb16  mov     eax, 2
0x10081fb1b  mul     rbp
0x10081fb1e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081fb25  cmovo   rax, rcx
0x10081fb29  mov     byte ptr [rsp+98h+var_78], 3
0x10081fb2e  mov     r9d, 199h
0x10081fb34  lea     r8, aSqlNtdbmsCommo_1; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081fb3b  mov     rdx, [r15]
0x10081fb3e  mov     rcx, rax
0x10081fb41  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081fb47  mov     rbx, rax
0x10081fb4a  test    rax, rax
0x10081fb4d  jz      short loc_10081FBBD
0x10081fb4f  xor     ecx, ecx
0x10081fb51  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081fb57  mov     [rsp+98h+arg_0], rbx
0x10081fb5f  mov     [rsp+98h+var_78], rbx
0x10081fb64  mov     r9, rsi
0x10081fb67  mov     r8, rdi
0x10081fb6a  mov     rdx, r14
0x10081fb6d  mov     rcx, r15
0x10081fb70  call    ?MergeHigherLevels@?$CKLLSketch@VCSsNumeric@@@@AEAA?AW4KLLRETCODE@@AEBV1@PEAVCSsNumeric@@PEAG2@Z; CKLLSketch<CSsNumeric>::MergeHigherLevels(CKLLSketch<CSsNumeric> const &,CSsNumeric *,ushort *,ushort *)
0x10081fb75  mov     ebp, eax
0x10081fb77  test    eax, eax
0x10081fb79  jnz     short loc_10081FB86
0x10081fb7b  mov     rax, [r15+18h]
0x10081fb7f  mov     [rax+20h], r12
0x10081fb83  mov     ebp, r13d
0x10081fb86  mov     rcx, rbx
0x10081fb89  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081fb8f  nop
0x10081fb90  mov     rcx, rsi
0x10081fb93  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081fb99  nop
0x10081fb9a  mov     rcx, rdi
0x10081fb9d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081fba3  mov     eax, ebp
0x10081fba5  mov     rbx, [rsp+98h+arg_18]
0x10081fbad  add     rsp, 60h
0x10081fbb1  pop     r15
0x10081fbb3  pop     r14
0x10081fbb5  pop     r13
0x10081fbb7  pop     r12
0x10081fbb9  pop     rdi
0x10081fbba  pop     rsi
0x10081fbbb  pop     rbp
0x10081fbbc  retn
0x10081fbbd  mov     [rsp+98h+arg_0], rbx
0x10081fbc5  mov     ebp, 5
0x10081fbca  jmp     short loc_10081FB86
0x10081fbcc  mov     [rsp+98h+arg_8], rsi
0x10081fbd4  mov     ebp, 5
0x10081fbd9  jmp     short loc_10081FB86
0x10081fbdb  mov     [rsp+98h+arg_10], rdi
0x10081fbe3  mov     ebp, 5
0x10081fbe8  jmp     short loc_10081FB86
```
