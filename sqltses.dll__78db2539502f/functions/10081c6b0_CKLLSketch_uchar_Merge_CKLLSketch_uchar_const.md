# CKLLSketch<uchar>::Merge(CKLLSketch<uchar> const &)

- ea: `0x10081c6b0`
- end: `0x10081c920`
- name: `?Merge@?$CKLLSketch@E@@QEAA?AW4KLLRETCODE@@AEBV1@@Z`
- size: `624`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x10081a240`

## callees

- `0x10081c6b0`
- `0x10081c930`
- `0x10081ccb0`
- `0x1008200f0`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10081c7d4`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081c83d`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081c886`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081c8be`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081c8c8`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081c8d2`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081c7d4`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081c83d`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081c886`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081c8be`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081c8c8`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081c8d2`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081c7c0`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081c829`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081c876`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081c7c0`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081c829`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081c876`

## string_xrefs

- `0x10081c7b6`: `sql\ntdbms\common\sketches\KLLSketch.inl`
- `0x10081c81c`: `sql\ntdbms\common\sketches\KLLSketch.inl`
- `0x10081c869`: `sql\ntdbms\common\sketches\KLLSketch.inl`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CKLLSketch<unsigned char>::Merge(__int64 a1, _QWORD *a2)
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
  unsigned __int16 v17; // dx
  __int64 v18; // rax
  unsigned __int64 v19; // rbp
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rax
  unsigned int v22; // ebp

  v4 = *(_QWORD *)(a1 + 24);
  v5 = *(unsigned __int16 *)(v4 + 24) + 4 * (*(unsigned __int16 *)(v4 + 6) + 29LL);
  if ( v5 < CKLLSketch<unsigned char>::GetEstimateMemReq(
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
      CKLLSketch<unsigned char>::Update(a1, *(unsigned __int8 *)(v13++ + a2[5]));
      v12 = (unsigned __int16 *)a2[4];
    }
    while ( v13 < v12[1] );
    v10 = a2[3];
  }
  v14 = v12[1];
  v15 = *(_WORD *)(v10 + 24);
  if ( v14 == v15 )
    goto LABEL_20;
  if ( *(_WORD *)(v10 + 6) )
    v16 = v14 - *v12;
  else
    v16 = 0;
  v7 = operator new[](
         (unsigned __int16)(v15 - v16 + *(_WORD *)(*(_QWORD *)(a1 + 24) + 24LL)),
         *(struct IMemObj **)a1,
         "sql\\ntdbms\\common\\sketches\\KLLSketch.inl",
         385,
         3u);
  if ( !v7 )
  {
    v22 = 5;
    goto LABEL_21;
  }
  operator delete[](0);
  v17 = *(_WORD *)(a2[3] + 6LL);
  v18 = *(_QWORD *)(a1 + 24);
  if ( v17 <= *(_WORD *)(v18 + 6) )
    v17 = *(_WORD *)(v18 + 6);
  v19 = v17 + 2LL;
  v20 = 2 * v19;
  if ( !is_mul_ok(v19, 2u) )
    v20 = -1;
  v8 = operator new[](v20, *(struct IMemObj **)a1, "sql\\ntdbms\\common\\sketches\\KLLSketch.inl", 400, 3u);
  if ( !v8 )
  {
    v22 = 5;
    goto LABEL_21;
  }
  operator delete[](0);
  v21 = 2 * v19;
  if ( !is_mul_ok(v19, 2u) )
    v21 = -1;
  v9 = operator new[](v21, *(struct IMemObj **)a1, "sql\\ntdbms\\common\\sketches\\KLLSketch.inl", 409, 3u);
  if ( !v9 )
  {
    v22 = 5;
    goto LABEL_21;
  }
  operator delete[](0);
  v22 = CKLLSketch<unsigned char>::MergeHigherLevels(a1, (_DWORD)a2, (_DWORD)v7, (_DWORD)v8, (__int64)v9);
  if ( !v22 )
  {
LABEL_20:
    *(_QWORD *)(*(_QWORD *)(a1 + 24) + 32LL) = v11;
    v22 = 0;
  }
LABEL_21:
  operator delete[](v9);
  operator delete[](v8);
  operator delete[](v7);
  return v22;
}

```

## disassembly

```asm
0x10081c6b0  push    rbp
0x10081c6b2  push    rsi
0x10081c6b3  push    rdi
0x10081c6b4  push    r12
0x10081c6b6  push    r13
0x10081c6b8  push    r14
0x10081c6ba  push    r15
0x10081c6bc  sub     rsp, 40h
0x10081c6c0  mov     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFEh
0x10081c6c9  mov     [rsp+78h+arg_18], rbx
0x10081c6d1  mov     r14, rdx
0x10081c6d4  mov     r15, rcx
0x10081c6d7  mov     rdx, [rcx+18h]
0x10081c6db  movzx   r8d, word ptr [rdx+6]
0x10081c6e0  movzx   eax, word ptr [rdx+18h]
0x10081c6e4  add     r8, 1Dh
0x10081c6e8  lea     rbx, [rax+r8*4]
0x10081c6ec  mov     rax, [r14+18h]
0x10081c6f0  mov     rcx, [rdx+20h]
0x10081c6f4  add     rcx, [rax+20h]
0x10081c6f8  movzx   edx, word ptr [rdx+2]
0x10081c6fc  call    ?GetEstimateMemReq@?$CKLLSketch@E@@SA_K_KG@Z; CKLLSketch<uchar>::GetEstimateMemReq(unsigned __int64,ushort)
0x10081c701  cmp     rbx, rax
0x10081c704  jnb     short loc_10081C710
0x10081c706  mov     eax, 6
0x10081c70b  jmp     loc_10081C8DA
0x10081c710  xor     r13d, r13d
0x10081c713  mov     edi, r13d
0x10081c716  mov     [rsp+78h+arg_10], r13
0x10081c71e  mov     esi, r13d
0x10081c721  mov     [rsp+78h+arg_8], r13
0x10081c729  mov     ebx, r13d
0x10081c72c  mov     [rsp+78h+arg_0], rbx
0x10081c734  mov     rdx, [r14+18h]
0x10081c738  mov     rax, [r15+18h]
0x10081c73c  mov     r12, [rdx+20h]
0x10081c740  add     r12, [rax+20h]
0x10081c744  mov     rax, [r14+20h]
0x10081c748  movzx   ebp, word ptr [rax]
0x10081c74b  cmp     bp, [rax+2]
0x10081c74f  jnb     short loc_10081C775
0x10081c751  movzx   ecx, bp
0x10081c754  mov     rax, [r14+28h]
0x10081c758  movzx   edx, byte ptr [rcx+rax]
0x10081c75c  mov     rcx, r15
0x10081c75f  call    ?Update@?$CKLLSketch@E@@QEAA?AW4KLLRETCODE@@E@Z; CKLLSketch<uchar>::Update(uchar)
0x10081c764  inc     bp
0x10081c767  mov     rax, [r14+20h]
0x10081c76b  cmp     bp, [rax+2]
0x10081c76f  jb      short loc_10081C751
0x10081c771  mov     rdx, [r14+18h]
0x10081c775  movzx   ecx, word ptr [rax+2]
0x10081c779  movzx   r8d, word ptr [rdx+18h]
0x10081c77e  cmp     cx, r8w
0x10081c782  jz      loc_10081C8B0
0x10081c788  cmp     r13w, [rdx+6]
0x10081c78d  jb      short loc_10081C795
0x10081c78f  movzx   ecx, r13w
0x10081c793  jmp     short loc_10081C798
0x10081c795  sub     cx, [rax]
0x10081c798  sub     r8w, cx
0x10081c79c  mov     rax, [r15+18h]
0x10081c7a0  movzx   ecx, word ptr [rax+18h]
0x10081c7a4  add     cx, r8w
0x10081c7a8  movzx   ecx, cx
0x10081c7ab  mov     byte ptr [rsp+78h+var_58], 3
0x10081c7b0  mov     r9d, 181h
0x10081c7b6  lea     r8, aSqlNtdbmsCommo_1; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081c7bd  mov     rdx, [r15]
0x10081c7c0  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081c7c6  mov     rdi, rax
0x10081c7c9  test    rax, rax
0x10081c7cc  jz      loc_10081C910
0x10081c7d2  xor     ecx, ecx
0x10081c7d4  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081c7da  mov     [rsp+78h+arg_10], rdi
0x10081c7e2  mov     rax, [r14+18h]
0x10081c7e6  movzx   edx, word ptr [rax+6]
0x10081c7ea  mov     rax, [r15+18h]
0x10081c7ee  cmp     dx, [rax+6]
0x10081c7f2  cmovbe  dx, [rax+6]
0x10081c7f7  movzx   ebp, dx
0x10081c7fa  add     rbp, 2
0x10081c7fe  mov     eax, 2
0x10081c803  mul     rbp
0x10081c806  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081c80d  cmovo   rax, rcx
0x10081c811  mov     byte ptr [rsp+78h+var_58], 3
0x10081c816  mov     r9d, 190h
0x10081c81c  lea     r8, aSqlNtdbmsCommo_1; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081c823  mov     rdx, [r15]
0x10081c826  mov     rcx, rax
0x10081c829  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081c82f  mov     rsi, rax
0x10081c832  test    rax, rax
0x10081c835  jz      loc_10081C901
0x10081c83b  xor     ecx, ecx
0x10081c83d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081c843  mov     [rsp+78h+arg_8], rsi
0x10081c84b  mov     eax, 2
0x10081c850  mul     rbp
0x10081c853  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081c85a  cmovo   rax, rcx
0x10081c85e  mov     byte ptr [rsp+78h+var_58], 3
0x10081c863  mov     r9d, 199h
0x10081c869  lea     r8, aSqlNtdbmsCommo_1; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081c870  mov     rdx, [r15]
0x10081c873  mov     rcx, rax
0x10081c876  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081c87c  mov     rbx, rax
0x10081c87f  test    rax, rax
0x10081c882  jz      short loc_10081C8F2
0x10081c884  xor     ecx, ecx
0x10081c886  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081c88c  mov     [rsp+78h+arg_0], rbx
0x10081c894  mov     [rsp+78h+var_58], rbx
0x10081c899  mov     r9, rsi
0x10081c89c  mov     r8, rdi
0x10081c89f  mov     rdx, r14
0x10081c8a2  mov     rcx, r15
0x10081c8a5  call    ?MergeHigherLevels@?$CKLLSketch@E@@AEAA?AW4KLLRETCODE@@AEBV1@PEAEPEAG2@Z; CKLLSketch<uchar>::MergeHigherLevels(CKLLSketch<uchar> const &,uchar *,ushort *,ushort *)
0x10081c8aa  mov     ebp, eax
0x10081c8ac  test    eax, eax
0x10081c8ae  jnz     short loc_10081C8BB
0x10081c8b0  mov     rax, [r15+18h]
0x10081c8b4  mov     [rax+20h], r12
0x10081c8b8  mov     ebp, r13d
0x10081c8bb  mov     rcx, rbx
0x10081c8be  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081c8c4  nop
0x10081c8c5  mov     rcx, rsi
0x10081c8c8  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081c8ce  nop
0x10081c8cf  mov     rcx, rdi
0x10081c8d2  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081c8d8  mov     eax, ebp
0x10081c8da  mov     rbx, [rsp+78h+arg_18]
0x10081c8e2  add     rsp, 40h
0x10081c8e6  pop     r15
0x10081c8e8  pop     r14
0x10081c8ea  pop     r13
0x10081c8ec  pop     r12
0x10081c8ee  pop     rdi
0x10081c8ef  pop     rsi
0x10081c8f0  pop     rbp
0x10081c8f1  retn
0x10081c8f2  mov     [rsp+78h+arg_0], rbx
0x10081c8fa  mov     ebp, 5
0x10081c8ff  jmp     short loc_10081C8BB
0x10081c901  mov     [rsp+78h+arg_8], rsi
0x10081c909  mov     ebp, 5
0x10081c90e  jmp     short loc_10081C8BB
0x10081c910  mov     [rsp+78h+arg_10], rdi
0x10081c918  mov     ebp, 5
0x10081c91d  jmp     short loc_10081C8BB
```
