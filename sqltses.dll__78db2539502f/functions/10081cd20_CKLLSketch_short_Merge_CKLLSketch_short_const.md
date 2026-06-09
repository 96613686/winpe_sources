# CKLLSketch<short>::Merge(CKLLSketch<short> const &)

- ea: `0x10081cd20`
- end: `0x10081cfb5`
- name: `?Merge@?$CKLLSketch@F@@QEAA?AW4KLLRETCODE@@AEBV1@@Z`
- size: `661`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x10081a240`

## callees

- `0x10081cd20`
- `0x10081cfc0`
- `0x10081d350`
- `0x100820320`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10081ce69`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081ced2`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081cf1b`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081cf53`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081cf5d`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081cf67`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081ce69`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081ced2`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081cf1b`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081cf53`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081cf5d`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081cf67`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081ce55`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081cebe`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081cf0b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081ce55`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081cebe`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081cf0b`

## string_xrefs

- `0x10081ce48`: `sql\ntdbms\common\sketches\KLLSketch.inl`
- `0x10081ceb1`: `sql\ntdbms\common\sketches\KLLSketch.inl`
- `0x10081cefe`: `sql\ntdbms\common\sketches\KLLSketch.inl`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CKLLSketch<short>::Merge(__int64 a1, _QWORD *a2)
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
  v5 = 2 * (*(unsigned __int16 *)(v4 + 24) + 2 * (*(unsigned __int16 *)(v4 + 6) + 29LL));
  if ( v5 < CKLLSketch<short>::GetEstimateMemReq(
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
      CKLLSketch<short>::Update(a1, *(unsigned __int16 *)(a2[5] + 2LL * v13++));
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
  v18 = 2LL * (unsigned __int16)(v17 + *(_WORD *)(*(_QWORD *)(a1 + 24) + 24LL));
  if ( !is_mul_ok((unsigned __int16)(v17 + *(_WORD *)(*(_QWORD *)(a1 + 24) + 24LL)), 2u) )
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
  v24 = CKLLSketch<short>::MergeHigherLevels(a1, (_DWORD)a2, (_DWORD)v7, (_DWORD)v8, (__int64)v9);
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
0x10081cd20  push    rbp
0x10081cd22  push    rsi
0x10081cd23  push    rdi
0x10081cd24  push    r12
0x10081cd26  push    r13
0x10081cd28  push    r14
0x10081cd2a  push    r15
0x10081cd2c  sub     rsp, 40h
0x10081cd30  mov     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFEh
0x10081cd39  mov     [rsp+78h+arg_18], rbx
0x10081cd41  mov     r14, rdx
0x10081cd44  mov     r15, rcx
0x10081cd47  mov     rdx, [rcx+18h]
0x10081cd4b  movzx   r8d, word ptr [rdx+6]
0x10081cd50  movzx   eax, word ptr [rdx+18h]
0x10081cd54  add     r8, 1Dh
0x10081cd58  lea     rbx, [rax+r8*2]
0x10081cd5c  add     rbx, rbx
0x10081cd5f  mov     rax, [r14+18h]
0x10081cd63  mov     rcx, [rax+20h]
0x10081cd67  add     rcx, [rdx+20h]
0x10081cd6b  movzx   edx, word ptr [rdx+2]
0x10081cd6f  call    ?GetEstimateMemReq@?$CKLLSketch@F@@SA_K_KG@Z; CKLLSketch<short>::GetEstimateMemReq(unsigned __int64,ushort)
0x10081cd74  cmp     rbx, rax
0x10081cd77  jnb     short loc_10081CD83
0x10081cd79  mov     eax, 6
0x10081cd7e  jmp     loc_10081CF6F
0x10081cd83  xor     r13d, r13d
0x10081cd86  mov     edi, r13d
0x10081cd89  mov     [rsp+78h+arg_10], r13
0x10081cd91  mov     esi, r13d
0x10081cd94  mov     [rsp+78h+arg_8], r13
0x10081cd9c  mov     ebx, r13d
0x10081cd9f  mov     [rsp+78h+arg_0], rbx
0x10081cda7  mov     rdx, [r14+18h]
0x10081cdab  mov     rax, [r15+18h]
0x10081cdaf  mov     r12, [rdx+20h]
0x10081cdb3  add     r12, [rax+20h]
0x10081cdb7  mov     rax, [r14+20h]
0x10081cdbb  movzx   ebp, word ptr [rax]
0x10081cdbe  cmp     bp, [rax+2]
0x10081cdc2  jnb     short loc_10081CDF4
0x10081cdc4  nop     dword ptr [rax+00h]
0x10081cdc8  nop     dword ptr [rax+rax+00000000h]
0x10081cdd0  movzx   ecx, bp
0x10081cdd3  mov     rax, [r14+28h]
0x10081cdd7  movzx   edx, word ptr [rax+rcx*2]
0x10081cddb  mov     rcx, r15
0x10081cdde  call    ?Update@?$CKLLSketch@F@@QEAA?AW4KLLRETCODE@@F@Z; CKLLSketch<short>::Update(short)
0x10081cde3  inc     bp
0x10081cde6  mov     rax, [r14+20h]
0x10081cdea  cmp     bp, [rax+2]
0x10081cdee  jb      short loc_10081CDD0
0x10081cdf0  mov     rdx, [r14+18h]
0x10081cdf4  movzx   ecx, word ptr [rax+2]
0x10081cdf8  movzx   r8d, word ptr [rdx+18h]
0x10081cdfd  cmp     cx, r8w
0x10081ce01  jz      loc_10081CF45
0x10081ce07  cmp     r13w, [rdx+6]
0x10081ce0c  jb      short loc_10081CE14
0x10081ce0e  movzx   ecx, r13w
0x10081ce12  jmp     short loc_10081CE17
0x10081ce14  sub     cx, [rax]
0x10081ce17  sub     r8w, cx
0x10081ce1b  mov     rax, [r15+18h]
0x10081ce1f  movzx   ecx, word ptr [rax+18h]
0x10081ce23  add     cx, r8w
0x10081ce27  movzx   ecx, cx
0x10081ce2a  mov     eax, 2
0x10081ce2f  mul     rcx
0x10081ce32  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081ce39  cmovo   rax, rcx
0x10081ce3d  mov     byte ptr [rsp+78h+var_58], 3
0x10081ce42  mov     r9d, 181h
0x10081ce48  lea     r8, aSqlNtdbmsCommo_1; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081ce4f  mov     rdx, [r15]
0x10081ce52  mov     rcx, rax
0x10081ce55  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081ce5b  mov     rdi, rax
0x10081ce5e  test    rax, rax
0x10081ce61  jz      loc_10081CFA5
0x10081ce67  xor     ecx, ecx
0x10081ce69  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081ce6f  mov     [rsp+78h+arg_10], rdi
0x10081ce77  mov     rax, [r14+18h]
0x10081ce7b  movzx   edx, word ptr [rax+6]
0x10081ce7f  mov     rax, [r15+18h]
0x10081ce83  cmp     dx, [rax+6]
0x10081ce87  cmovbe  dx, [rax+6]
0x10081ce8c  movzx   ebp, dx
0x10081ce8f  add     rbp, 2
0x10081ce93  mov     eax, 2
0x10081ce98  mul     rbp
0x10081ce9b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081cea2  cmovo   rax, rcx
0x10081cea6  mov     byte ptr [rsp+78h+var_58], 3
0x10081ceab  mov     r9d, 190h
0x10081ceb1  lea     r8, aSqlNtdbmsCommo_1; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081ceb8  mov     rdx, [r15]
0x10081cebb  mov     rcx, rax
0x10081cebe  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081cec4  mov     rsi, rax
0x10081cec7  test    rax, rax
0x10081ceca  jz      loc_10081CF96
0x10081ced0  xor     ecx, ecx
0x10081ced2  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081ced8  mov     [rsp+78h+arg_8], rsi
0x10081cee0  mov     eax, 2
0x10081cee5  mul     rbp
0x10081cee8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081ceef  cmovo   rax, rcx
0x10081cef3  mov     byte ptr [rsp+78h+var_58], 3
0x10081cef8  mov     r9d, 199h
0x10081cefe  lea     r8, aSqlNtdbmsCommo_1; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081cf05  mov     rdx, [r15]
0x10081cf08  mov     rcx, rax
0x10081cf0b  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081cf11  mov     rbx, rax
0x10081cf14  test    rax, rax
0x10081cf17  jz      short loc_10081CF87
0x10081cf19  xor     ecx, ecx
0x10081cf1b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081cf21  mov     [rsp+78h+arg_0], rbx
0x10081cf29  mov     [rsp+78h+var_58], rbx
0x10081cf2e  mov     r9, rsi
0x10081cf31  mov     r8, rdi
0x10081cf34  mov     rdx, r14
0x10081cf37  mov     rcx, r15
0x10081cf3a  call    ?MergeHigherLevels@?$CKLLSketch@F@@AEAA?AW4KLLRETCODE@@AEBV1@PEAFPEAG2@Z; CKLLSketch<short>::MergeHigherLevels(CKLLSketch<short> const &,short *,ushort *,ushort *)
0x10081cf3f  mov     ebp, eax
0x10081cf41  test    eax, eax
0x10081cf43  jnz     short loc_10081CF50
0x10081cf45  mov     rax, [r15+18h]
0x10081cf49  mov     [rax+20h], r12
0x10081cf4d  mov     ebp, r13d
0x10081cf50  mov     rcx, rbx
0x10081cf53  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081cf59  nop
0x10081cf5a  mov     rcx, rsi
0x10081cf5d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081cf63  nop
0x10081cf64  mov     rcx, rdi
0x10081cf67  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081cf6d  mov     eax, ebp
0x10081cf6f  mov     rbx, [rsp+78h+arg_18]
0x10081cf77  add     rsp, 40h
0x10081cf7b  pop     r15
0x10081cf7d  pop     r14
0x10081cf7f  pop     r13
0x10081cf81  pop     r12
0x10081cf83  pop     rdi
0x10081cf84  pop     rsi
0x10081cf85  pop     rbp
0x10081cf86  retn
0x10081cf87  mov     [rsp+78h+arg_0], rbx
0x10081cf8f  mov     ebp, 5
0x10081cf94  jmp     short loc_10081CF50
0x10081cf96  mov     [rsp+78h+arg_8], rsi
0x10081cf9e  mov     ebp, 5
0x10081cfa3  jmp     short loc_10081CF50
0x10081cfa5  mov     [rsp+78h+arg_10], rdi
0x10081cfad  mov     ebp, 5
0x10081cfb2  jmp     short loc_10081CF50
```
