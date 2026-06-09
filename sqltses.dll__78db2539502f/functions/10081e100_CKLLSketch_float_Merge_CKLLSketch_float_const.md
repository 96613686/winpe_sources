# CKLLSketch<float>::Merge(CKLLSketch<float> const &)

- ea: `0x10081e100`
- end: `0x10081e396`
- name: `?Merge@?$CKLLSketch@M@@QEAA?AW4KLLRETCODE@@AEBV1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x10081a240`

## callees

- `0x10081d9f0`
- `0x10081e100`
- `0x10081e3a0`
- `0x1008209b0`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10081e24a`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081e2b3`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081e2fc`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081e334`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081e33e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081e348`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081e24a`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081e2b3`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081e2fc`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081e334`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081e33e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081e348`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081e236`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081e29f`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081e2ec`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081e236`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081e29f`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081e2ec`

## string_xrefs

- `0x10081e229`: `sql\ntdbms\common\sketches\KLLSketch.inl`
- `0x10081e292`: `sql\ntdbms\common\sketches\KLLSketch.inl`
- `0x10081e2df`: `sql\ntdbms\common\sketches\KLLSketch.inl`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CKLLSketch<float>::Merge(__int64 a1, __int64 a2)
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
              *(_QWORD *)(*(_QWORD *)(a2 + 24) + 32LL) + *(_QWORD *)(v4 + 32),
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
      CKLLSketch<float>::Update(a1);
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
  v24 = CKLLSketch<float>::MergeHigherLevels(a1, a2, (_DWORD)v7, (_DWORD)v8, (__int64)v9);
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
0x10081e100  push    rbp
0x10081e102  push    rsi
0x10081e103  push    rdi
0x10081e104  push    r12
0x10081e106  push    r13
0x10081e108  push    r14
0x10081e10a  push    r15
0x10081e10c  sub     rsp, 40h
0x10081e110  mov     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFEh
0x10081e119  mov     [rsp+78h+arg_18], rbx
0x10081e121  mov     r14, rdx
0x10081e124  mov     r15, rcx
0x10081e127  mov     rdx, [rcx+18h]
0x10081e12b  movzx   r8d, word ptr [rdx+18h]
0x10081e130  movzx   eax, word ptr [rdx+6]
0x10081e134  add     r8, rax
0x10081e137  lea     rbx, ds:74h[r8*4]
0x10081e13f  mov     rax, [r14+18h]
0x10081e143  mov     rcx, [rdx+20h]
0x10081e147  add     rcx, [rax+20h]
0x10081e14b  movzx   edx, word ptr [rdx+2]
0x10081e14f  call    ?GetEstimateMemReq@?$CKLLSketch@M@@SA_K_KG@Z; CKLLSketch<float>::GetEstimateMemReq(unsigned __int64,ushort)
0x10081e154  cmp     rbx, rax
0x10081e157  jnb     short loc_10081E163
0x10081e159  mov     eax, 6
0x10081e15e  jmp     loc_10081E350
0x10081e163  xor     r13d, r13d
0x10081e166  mov     edi, r13d
0x10081e169  mov     [rsp+78h+arg_10], r13
0x10081e171  mov     esi, r13d
0x10081e174  mov     [rsp+78h+arg_8], r13
0x10081e17c  mov     ebx, r13d
0x10081e17f  mov     [rsp+78h+arg_0], rbx
0x10081e187  mov     rdx, [r14+18h]
0x10081e18b  mov     rax, [r15+18h]
0x10081e18f  mov     r12, [rdx+20h]
0x10081e193  add     r12, [rax+20h]
0x10081e197  mov     rax, [r14+20h]
0x10081e19b  movzx   ebp, word ptr [rax]
0x10081e19e  cmp     bp, [rax+2]
0x10081e1a2  jnb     short loc_10081E1D5
0x10081e1a4  nop     dword ptr [rax+00h]
0x10081e1a8  nop     dword ptr [rax+rax+00000000h]
0x10081e1b0  movzx   ecx, bp
0x10081e1b3  mov     rax, [r14+28h]
0x10081e1b7  movss   xmm1, dword ptr [rax+rcx*4]
0x10081e1bc  mov     rcx, r15
0x10081e1bf  call    ?Update@?$CKLLSketch@M@@QEAA?AW4KLLRETCODE@@M@Z; CKLLSketch<float>::Update(float)
0x10081e1c4  inc     bp
0x10081e1c7  mov     rax, [r14+20h]
0x10081e1cb  cmp     bp, [rax+2]
0x10081e1cf  jb      short loc_10081E1B0
0x10081e1d1  mov     rdx, [r14+18h]
0x10081e1d5  movzx   ecx, word ptr [rax+2]
0x10081e1d9  movzx   r8d, word ptr [rdx+18h]
0x10081e1de  cmp     cx, r8w
0x10081e1e2  jz      loc_10081E326
0x10081e1e8  cmp     r13w, [rdx+6]
0x10081e1ed  jb      short loc_10081E1F5
0x10081e1ef  movzx   ecx, r13w
0x10081e1f3  jmp     short loc_10081E1F8
0x10081e1f5  sub     cx, [rax]
0x10081e1f8  sub     r8w, cx
0x10081e1fc  mov     rax, [r15+18h]
0x10081e200  movzx   ecx, word ptr [rax+18h]
0x10081e204  add     cx, r8w
0x10081e208  movzx   ecx, cx
0x10081e20b  mov     eax, 4
0x10081e210  mul     rcx
0x10081e213  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081e21a  cmovo   rax, rcx
0x10081e21e  mov     byte ptr [rsp+78h+var_58], 3
0x10081e223  mov     r9d, 181h
0x10081e229  lea     r8, aSqlNtdbmsCommo_1; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081e230  mov     rdx, [r15]
0x10081e233  mov     rcx, rax
0x10081e236  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081e23c  mov     rdi, rax
0x10081e23f  test    rax, rax
0x10081e242  jz      loc_10081E386
0x10081e248  xor     ecx, ecx
0x10081e24a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081e250  mov     [rsp+78h+arg_10], rdi
0x10081e258  mov     rax, [r14+18h]
0x10081e25c  movzx   edx, word ptr [rax+6]
0x10081e260  mov     rax, [r15+18h]
0x10081e264  cmp     dx, [rax+6]
0x10081e268  cmovbe  dx, [rax+6]
0x10081e26d  movzx   ebp, dx
0x10081e270  add     rbp, 2
0x10081e274  mov     eax, 2
0x10081e279  mul     rbp
0x10081e27c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081e283  cmovo   rax, rcx
0x10081e287  mov     byte ptr [rsp+78h+var_58], 3
0x10081e28c  mov     r9d, 190h
0x10081e292  lea     r8, aSqlNtdbmsCommo_1; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081e299  mov     rdx, [r15]
0x10081e29c  mov     rcx, rax
0x10081e29f  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081e2a5  mov     rsi, rax
0x10081e2a8  test    rax, rax
0x10081e2ab  jz      loc_10081E377
0x10081e2b1  xor     ecx, ecx
0x10081e2b3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081e2b9  mov     [rsp+78h+arg_8], rsi
0x10081e2c1  mov     eax, 2
0x10081e2c6  mul     rbp
0x10081e2c9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081e2d0  cmovo   rax, rcx
0x10081e2d4  mov     byte ptr [rsp+78h+var_58], 3
0x10081e2d9  mov     r9d, 199h
0x10081e2df  lea     r8, aSqlNtdbmsCommo_1; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081e2e6  mov     rdx, [r15]
0x10081e2e9  mov     rcx, rax
0x10081e2ec  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081e2f2  mov     rbx, rax
0x10081e2f5  test    rax, rax
0x10081e2f8  jz      short loc_10081E368
0x10081e2fa  xor     ecx, ecx
0x10081e2fc  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081e302  mov     [rsp+78h+arg_0], rbx
0x10081e30a  mov     [rsp+78h+var_58], rbx
0x10081e30f  mov     r9, rsi
0x10081e312  mov     r8, rdi
0x10081e315  mov     rdx, r14
0x10081e318  mov     rcx, r15
0x10081e31b  call    ?MergeHigherLevels@?$CKLLSketch@M@@AEAA?AW4KLLRETCODE@@AEBV1@PEAMPEAG2@Z; CKLLSketch<float>::MergeHigherLevels(CKLLSketch<float> const &,float *,ushort *,ushort *)
0x10081e320  mov     ebp, eax
0x10081e322  test    eax, eax
0x10081e324  jnz     short loc_10081E331
0x10081e326  mov     rax, [r15+18h]
0x10081e32a  mov     [rax+20h], r12
0x10081e32e  mov     ebp, r13d
0x10081e331  mov     rcx, rbx
0x10081e334  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081e33a  nop
0x10081e33b  mov     rcx, rsi
0x10081e33e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081e344  nop
0x10081e345  mov     rcx, rdi
0x10081e348  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081e34e  mov     eax, ebp
0x10081e350  mov     rbx, [rsp+78h+arg_18]
0x10081e358  add     rsp, 40h
0x10081e35c  pop     r15
0x10081e35e  pop     r14
0x10081e360  pop     r13
0x10081e362  pop     r12
0x10081e364  pop     rdi
0x10081e365  pop     rsi
0x10081e366  pop     rbp
0x10081e367  retn
0x10081e368  mov     [rsp+78h+arg_0], rbx
0x10081e370  mov     ebp, 5
0x10081e375  jmp     short loc_10081E331
0x10081e377  mov     [rsp+78h+arg_8], rsi
0x10081e37f  mov     ebp, 5
0x10081e384  jmp     short loc_10081E331
0x10081e386  mov     [rsp+78h+arg_10], rdi
0x10081e38e  mov     ebp, 5
0x10081e393  jmp     short loc_10081E331
```
