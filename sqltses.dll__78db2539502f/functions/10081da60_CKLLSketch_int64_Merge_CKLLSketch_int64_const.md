# CKLLSketch<__int64>::Merge(CKLLSketch<__int64> const &)

- ea: `0x10081da60`
- end: `0x10081dcf5`
- name: `?Merge@?$CKLLSketch@_J@@QEAA?AW4KLLRETCODE@@AEBV1@@Z`
- size: `661`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x10081a240`

## callees

- `0x10081da60`
- `0x10081dd00`
- `0x10081e080`
- `0x100820780`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10081dba9`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081dc12`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081dc5b`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081dc93`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081dc9d`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081dca7`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081dba9`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081dc12`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081dc5b`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081dc93`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081dc9d`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081dca7`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081db95`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081dbfe`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081dc4b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081db95`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081dbfe`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081dc4b`

## string_xrefs

- `0x10081db88`: `sql\ntdbms\common\sketches\KLLSketch.inl`
- `0x10081dbf1`: `sql\ntdbms\common\sketches\KLLSketch.inl`
- `0x10081dc3e`: `sql\ntdbms\common\sketches\KLLSketch.inl`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CKLLSketch<__int64>::Merge(__int64 a1, _QWORD *a2)
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
      CKLLSketch<__int64>::Update(a1, *(_QWORD *)(a2[5] + 8LL * v13++));
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
  v24 = CKLLSketch<__int64>::MergeHigherLevels(a1, (_DWORD)a2, (_DWORD)v7, (_DWORD)v8, (__int64)v9);
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
0x10081da60  push    rbp
0x10081da62  push    rsi
0x10081da63  push    rdi
0x10081da64  push    r12
0x10081da66  push    r13
0x10081da68  push    r14
0x10081da6a  push    r15
0x10081da6c  sub     rsp, 40h
0x10081da70  mov     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFEh
0x10081da79  mov     [rsp+78h+arg_18], rbx
0x10081da81  mov     r14, rdx
0x10081da84  mov     r15, rcx
0x10081da87  mov     rdx, [rcx+18h]
0x10081da8b  movzx   r8d, word ptr [rdx+18h]
0x10081da90  movzx   eax, word ptr [rdx+6]
0x10081da94  lea     r8, [rax+r8*2]
0x10081da98  lea     rbx, ds:74h[r8*4]
0x10081daa0  mov     rax, [r14+18h]
0x10081daa4  mov     rcx, [rax+20h]
0x10081daa8  add     rcx, [rdx+20h]
0x10081daac  movzx   edx, word ptr [rdx+2]
0x10081dab0  call    ?GetEstimateMemReq@?$CKLLSketch@N@@SA_K_KG@Z; CKLLSketch<double>::GetEstimateMemReq(unsigned __int64,ushort)
0x10081dab5  cmp     rbx, rax
0x10081dab8  jnb     short loc_10081DAC4
0x10081daba  mov     eax, 6
0x10081dabf  jmp     loc_10081DCAF
0x10081dac4  xor     r13d, r13d
0x10081dac7  mov     edi, r13d
0x10081daca  mov     [rsp+78h+arg_10], r13
0x10081dad2  mov     esi, r13d
0x10081dad5  mov     [rsp+78h+arg_8], r13
0x10081dadd  mov     ebx, r13d
0x10081dae0  mov     [rsp+78h+arg_0], rbx
0x10081dae8  mov     rdx, [r14+18h]
0x10081daec  mov     rax, [r15+18h]
0x10081daf0  mov     r12, [rdx+20h]
0x10081daf4  add     r12, [rax+20h]
0x10081daf8  mov     rax, [r14+20h]
0x10081dafc  movzx   ebp, word ptr [rax]
0x10081daff  cmp     bp, [rax+2]
0x10081db03  jnb     short loc_10081DB34
0x10081db05  nop     word ptr [rax+rax]
0x10081db0a  nop     word ptr [rax+rax+00h]
0x10081db10  movzx   eax, bp
0x10081db13  mov     rdx, [r14+28h]
0x10081db17  mov     rdx, [rdx+rax*8]
0x10081db1b  mov     rcx, r15
0x10081db1e  call    ?Update@?$CKLLSketch@_J@@QEAA?AW4KLLRETCODE@@_J@Z; CKLLSketch<__int64>::Update(__int64)
0x10081db23  inc     bp
0x10081db26  mov     rax, [r14+20h]
0x10081db2a  cmp     bp, [rax+2]
0x10081db2e  jb      short loc_10081DB10
0x10081db30  mov     rdx, [r14+18h]
0x10081db34  movzx   ecx, word ptr [rax+2]
0x10081db38  movzx   r8d, word ptr [rdx+18h]
0x10081db3d  cmp     cx, r8w
0x10081db41  jz      loc_10081DC85
0x10081db47  cmp     r13w, [rdx+6]
0x10081db4c  jb      short loc_10081DB54
0x10081db4e  movzx   ecx, r13w
0x10081db52  jmp     short loc_10081DB57
0x10081db54  sub     cx, [rax]
0x10081db57  sub     r8w, cx
0x10081db5b  mov     rax, [r15+18h]
0x10081db5f  movzx   ecx, word ptr [rax+18h]
0x10081db63  add     cx, r8w
0x10081db67  movzx   ecx, cx
0x10081db6a  mov     eax, 8
0x10081db6f  mul     rcx
0x10081db72  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081db79  cmovo   rax, rcx
0x10081db7d  mov     byte ptr [rsp+78h+var_58], 3
0x10081db82  mov     r9d, 181h
0x10081db88  lea     r8, aSqlNtdbmsCommo_1; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081db8f  mov     rdx, [r15]
0x10081db92  mov     rcx, rax
0x10081db95  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081db9b  mov     rdi, rax
0x10081db9e  test    rax, rax
0x10081dba1  jz      loc_10081DCE5
0x10081dba7  xor     ecx, ecx
0x10081dba9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081dbaf  mov     [rsp+78h+arg_10], rdi
0x10081dbb7  mov     rax, [r14+18h]
0x10081dbbb  movzx   edx, word ptr [rax+6]
0x10081dbbf  mov     rax, [r15+18h]
0x10081dbc3  cmp     dx, [rax+6]
0x10081dbc7  cmovbe  dx, [rax+6]
0x10081dbcc  movzx   ebp, dx
0x10081dbcf  add     rbp, 2
0x10081dbd3  mov     eax, 2
0x10081dbd8  mul     rbp
0x10081dbdb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081dbe2  cmovo   rax, rcx
0x10081dbe6  mov     byte ptr [rsp+78h+var_58], 3
0x10081dbeb  mov     r9d, 190h
0x10081dbf1  lea     r8, aSqlNtdbmsCommo_1; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081dbf8  mov     rdx, [r15]
0x10081dbfb  mov     rcx, rax
0x10081dbfe  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081dc04  mov     rsi, rax
0x10081dc07  test    rax, rax
0x10081dc0a  jz      loc_10081DCD6
0x10081dc10  xor     ecx, ecx
0x10081dc12  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081dc18  mov     [rsp+78h+arg_8], rsi
0x10081dc20  mov     eax, 2
0x10081dc25  mul     rbp
0x10081dc28  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081dc2f  cmovo   rax, rcx
0x10081dc33  mov     byte ptr [rsp+78h+var_58], 3
0x10081dc38  mov     r9d, 199h
0x10081dc3e  lea     r8, aSqlNtdbmsCommo_1; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081dc45  mov     rdx, [r15]
0x10081dc48  mov     rcx, rax
0x10081dc4b  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081dc51  mov     rbx, rax
0x10081dc54  test    rax, rax
0x10081dc57  jz      short loc_10081DCC7
0x10081dc59  xor     ecx, ecx
0x10081dc5b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081dc61  mov     [rsp+78h+arg_0], rbx
0x10081dc69  mov     [rsp+78h+var_58], rbx
0x10081dc6e  mov     r9, rsi
0x10081dc71  mov     r8, rdi
0x10081dc74  mov     rdx, r14
0x10081dc77  mov     rcx, r15
0x10081dc7a  call    ?MergeHigherLevels@?$CKLLSketch@_J@@AEAA?AW4KLLRETCODE@@AEBV1@PEA_JPEAG2@Z; CKLLSketch<__int64>::MergeHigherLevels(CKLLSketch<__int64> const &,__int64 *,ushort *,ushort *)
0x10081dc7f  mov     ebp, eax
0x10081dc81  test    eax, eax
0x10081dc83  jnz     short loc_10081DC90
0x10081dc85  mov     rax, [r15+18h]
0x10081dc89  mov     [rax+20h], r12
0x10081dc8d  mov     ebp, r13d
0x10081dc90  mov     rcx, rbx
0x10081dc93  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081dc99  nop
0x10081dc9a  mov     rcx, rsi
0x10081dc9d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081dca3  nop
0x10081dca4  mov     rcx, rdi
0x10081dca7  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081dcad  mov     eax, ebp
0x10081dcaf  mov     rbx, [rsp+78h+arg_18]
0x10081dcb7  add     rsp, 40h
0x10081dcbb  pop     r15
0x10081dcbd  pop     r14
0x10081dcbf  pop     r13
0x10081dcc1  pop     r12
0x10081dcc3  pop     rdi
0x10081dcc4  pop     rsi
0x10081dcc5  pop     rbp
0x10081dcc6  retn
0x10081dcc7  mov     [rsp+78h+arg_0], rbx
0x10081dccf  mov     ebp, 5
0x10081dcd4  jmp     short loc_10081DC90
0x10081dcd6  mov     [rsp+78h+arg_8], rsi
0x10081dcde  mov     ebp, 5
0x10081dce3  jmp     short loc_10081DC90
0x10081dce5  mov     [rsp+78h+arg_10], rdi
0x10081dced  mov     ebp, 5
0x10081dcf2  jmp     short loc_10081DC90
```
