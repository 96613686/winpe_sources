# CKLLSketch<double>::Merge(CKLLSketch<double> const &)

- ea: `0x10081e730`
- end: `0x10081e9c6`
- name: `?Merge@?$CKLLSketch@N@@QEAA?AW4KLLRETCODE@@AEBV1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x10081a240`

## callees

- `0x10081e080`
- `0x10081e730`
- `0x10081e9d0`
- `0x100820bd0`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10081e87a`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081e8e3`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081e92c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081e964`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081e96e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081e978`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081e87a`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081e8e3`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081e92c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081e964`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081e96e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081e978`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081e866`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081e8cf`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081e91c`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081e866`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081e8cf`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081e91c`

## string_xrefs

- `0x10081e859`: `sql\ntdbms\common\sketches\KLLSketch.inl`
- `0x10081e8c2`: `sql\ntdbms\common\sketches\KLLSketch.inl`
- `0x10081e90f`: `sql\ntdbms\common\sketches\KLLSketch.inl`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CKLLSketch<double>::Merge(__int64 a1, __int64 a2)
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
              *(_QWORD *)(v4 + 32) + *(_QWORD *)(*(_QWORD *)(a2 + 24) + 32LL),
              *(unsigned __int16 *)(v4 + 2)) )
    return 6;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = *(_QWORD *)(a2 + 24);
  v11 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 32LL) + *(_QWORD *)(v10 + 32);
  v12 = *(unsigned __int16 **)(a2 + 32);
  v13 = *v12;
  if ( *v12 < v12[1] )
  {
    do
    {
      CKLLSketch<double>::Update(a1);
      ++v13;
      v12 = *(unsigned __int16 **)(a2 + 32);
    }
    while ( v13 < v12[1] );
    v10 = *(_QWORD *)(a2 + 24);
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
  v19 = *(_WORD *)(*(_QWORD *)(a2 + 24) + 6LL);
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
  v24 = CKLLSketch<double>::MergeHigherLevels(a1, a2, (_DWORD)v7, (_DWORD)v8, (__int64)v9);
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
0x10081e730  push    rbp
0x10081e732  push    rsi
0x10081e733  push    rdi
0x10081e734  push    r12
0x10081e736  push    r13
0x10081e738  push    r14
0x10081e73a  push    r15
0x10081e73c  sub     rsp, 40h
0x10081e740  mov     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFEh
0x10081e749  mov     [rsp+78h+arg_18], rbx
0x10081e751  mov     r14, rdx
0x10081e754  mov     r15, rcx
0x10081e757  mov     rdx, [rcx+18h]
0x10081e75b  movzx   r8d, word ptr [rdx+18h]
0x10081e760  movzx   eax, word ptr [rdx+6]
0x10081e764  lea     r8, [rax+r8*2]
0x10081e768  lea     rbx, ds:74h[r8*4]
0x10081e770  mov     rax, [r14+18h]
0x10081e774  mov     rcx, [rax+20h]
0x10081e778  add     rcx, [rdx+20h]
0x10081e77c  movzx   edx, word ptr [rdx+2]
0x10081e780  call    ?GetEstimateMemReq@?$CKLLSketch@N@@SA_K_KG@Z; CKLLSketch<double>::GetEstimateMemReq(unsigned __int64,ushort)
0x10081e785  cmp     rbx, rax
0x10081e788  jnb     short loc_10081E794
0x10081e78a  mov     eax, 6
0x10081e78f  jmp     loc_10081E980
0x10081e794  xor     r13d, r13d
0x10081e797  mov     edi, r13d
0x10081e79a  mov     [rsp+78h+arg_10], r13
0x10081e7a2  mov     esi, r13d
0x10081e7a5  mov     [rsp+78h+arg_8], r13
0x10081e7ad  mov     ebx, r13d
0x10081e7b0  mov     [rsp+78h+arg_0], rbx
0x10081e7b8  mov     rdx, [r14+18h]
0x10081e7bc  mov     rax, [r15+18h]
0x10081e7c0  mov     r12, [rdx+20h]
0x10081e7c4  add     r12, [rax+20h]
0x10081e7c8  mov     rax, [r14+20h]
0x10081e7cc  movzx   ebp, word ptr [rax]
0x10081e7cf  cmp     bp, [rax+2]
0x10081e7d3  jnb     short loc_10081E805
0x10081e7d5  nop     word ptr [rax+rax]
0x10081e7da  nop     word ptr [rax+rax+00h]
0x10081e7e0  movzx   ecx, bp
0x10081e7e3  mov     rax, [r14+28h]
0x10081e7e7  movsd   xmm1, qword ptr [rax+rcx*8]
0x10081e7ec  mov     rcx, r15
0x10081e7ef  call    ?Update@?$CKLLSketch@N@@QEAA?AW4KLLRETCODE@@N@Z; CKLLSketch<double>::Update(double)
0x10081e7f4  inc     bp
0x10081e7f7  mov     rax, [r14+20h]
0x10081e7fb  cmp     bp, [rax+2]
0x10081e7ff  jb      short loc_10081E7E0
0x10081e801  mov     rdx, [r14+18h]
0x10081e805  movzx   ecx, word ptr [rax+2]
0x10081e809  movzx   r8d, word ptr [rdx+18h]
0x10081e80e  cmp     cx, r8w
0x10081e812  jz      loc_10081E956
0x10081e818  cmp     r13w, [rdx+6]
0x10081e81d  jb      short loc_10081E825
0x10081e81f  movzx   ecx, r13w
0x10081e823  jmp     short loc_10081E828
0x10081e825  sub     cx, [rax]
0x10081e828  sub     r8w, cx
0x10081e82c  mov     rax, [r15+18h]
0x10081e830  movzx   ecx, word ptr [rax+18h]
0x10081e834  add     cx, r8w
0x10081e838  movzx   ecx, cx
0x10081e83b  mov     eax, 8
0x10081e840  mul     rcx
0x10081e843  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081e84a  cmovo   rax, rcx
0x10081e84e  mov     byte ptr [rsp+78h+var_58], 3
0x10081e853  mov     r9d, 181h
0x10081e859  lea     r8, aSqlNtdbmsCommo_1; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081e860  mov     rdx, [r15]
0x10081e863  mov     rcx, rax
0x10081e866  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081e86c  mov     rdi, rax
0x10081e86f  test    rax, rax
0x10081e872  jz      loc_10081E9B6
0x10081e878  xor     ecx, ecx
0x10081e87a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081e880  mov     [rsp+78h+arg_10], rdi
0x10081e888  mov     rax, [r14+18h]
0x10081e88c  movzx   edx, word ptr [rax+6]
0x10081e890  mov     rax, [r15+18h]
0x10081e894  cmp     dx, [rax+6]
0x10081e898  cmovbe  dx, [rax+6]
0x10081e89d  movzx   ebp, dx
0x10081e8a0  add     rbp, 2
0x10081e8a4  mov     eax, 2
0x10081e8a9  mul     rbp
0x10081e8ac  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081e8b3  cmovo   rax, rcx
0x10081e8b7  mov     byte ptr [rsp+78h+var_58], 3
0x10081e8bc  mov     r9d, 190h
0x10081e8c2  lea     r8, aSqlNtdbmsCommo_1; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081e8c9  mov     rdx, [r15]
0x10081e8cc  mov     rcx, rax
0x10081e8cf  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081e8d5  mov     rsi, rax
0x10081e8d8  test    rax, rax
0x10081e8db  jz      loc_10081E9A7
0x10081e8e1  xor     ecx, ecx
0x10081e8e3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081e8e9  mov     [rsp+78h+arg_8], rsi
0x10081e8f1  mov     eax, 2
0x10081e8f6  mul     rbp
0x10081e8f9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081e900  cmovo   rax, rcx
0x10081e904  mov     byte ptr [rsp+78h+var_58], 3
0x10081e909  mov     r9d, 199h
0x10081e90f  lea     r8, aSqlNtdbmsCommo_1; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081e916  mov     rdx, [r15]
0x10081e919  mov     rcx, rax
0x10081e91c  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081e922  mov     rbx, rax
0x10081e925  test    rax, rax
0x10081e928  jz      short loc_10081E998
0x10081e92a  xor     ecx, ecx
0x10081e92c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081e932  mov     [rsp+78h+arg_0], rbx
0x10081e93a  mov     [rsp+78h+var_58], rbx
0x10081e93f  mov     r9, rsi
0x10081e942  mov     r8, rdi
0x10081e945  mov     rdx, r14
0x10081e948  mov     rcx, r15
0x10081e94b  call    ?MergeHigherLevels@?$CKLLSketch@N@@AEAA?AW4KLLRETCODE@@AEBV1@PEANPEAG2@Z; CKLLSketch<double>::MergeHigherLevels(CKLLSketch<double> const &,double *,ushort *,ushort *)
0x10081e950  mov     ebp, eax
0x10081e952  test    eax, eax
0x10081e954  jnz     short loc_10081E961
0x10081e956  mov     rax, [r15+18h]
0x10081e95a  mov     [rax+20h], r12
0x10081e95e  mov     ebp, r13d
0x10081e961  mov     rcx, rbx
0x10081e964  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081e96a  nop
0x10081e96b  mov     rcx, rsi
0x10081e96e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081e974  nop
0x10081e975  mov     rcx, rdi
0x10081e978  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081e97e  mov     eax, ebp
0x10081e980  mov     rbx, [rsp+78h+arg_18]
0x10081e988  add     rsp, 40h
0x10081e98c  pop     r15
0x10081e98e  pop     r14
0x10081e990  pop     r13
0x10081e992  pop     r12
0x10081e994  pop     rdi
0x10081e995  pop     rsi
0x10081e996  pop     rbp
0x10081e997  retn
0x10081e998  mov     [rsp+78h+arg_0], rbx
0x10081e9a0  mov     ebp, 5
0x10081e9a5  jmp     short loc_10081E961
0x10081e9a7  mov     [rsp+78h+arg_8], rsi
0x10081e9af  mov     ebp, 5
0x10081e9b4  jmp     short loc_10081E961
0x10081e9b6  mov     [rsp+78h+arg_10], rdi
0x10081e9be  mov     ebp, 5
0x10081e9c3  jmp     short loc_10081E961
```
