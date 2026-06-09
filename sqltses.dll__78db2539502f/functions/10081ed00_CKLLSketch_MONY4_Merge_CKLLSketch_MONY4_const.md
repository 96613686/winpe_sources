# CKLLSketch<MONY4>::Merge(CKLLSketch<MONY4> const &)

- ea: `0x10081ed00`
- end: `0x10081ef94`
- name: `?Merge@?$CKLLSketch@UMONY4@@@@QEAA?AW4KLLRETCODE@@AEBV1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x10081a240`

## callees

- `0x10081d9f0`
- `0x10081ed00`
- `0x10081efa0`
- `0x100821070`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10081ee48`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081eeb1`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081eefa`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081ef32`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081ef3c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081ef46`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081ee48`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081eeb1`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081eefa`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081ef32`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081ef3c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081ef46`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081ee34`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081ee9d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081eeea`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081ee34`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081ee9d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081eeea`

## string_xrefs

- `0x10081ee27`: `sql\ntdbms\common\sketches\KLLSketch.inl`
- `0x10081ee90`: `sql\ntdbms\common\sketches\KLLSketch.inl`
- `0x10081eedd`: `sql\ntdbms\common\sketches\KLLSketch.inl`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CKLLSketch<MONY4>::Merge(__int64 a1, _QWORD *a2)
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
      CKLLSketch<MONY4>::Update(a1, *(unsigned int *)(a2[5] + 4LL * v13++));
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
  v24 = CKLLSketch<MONY4>::MergeHigherLevels(a1, (_DWORD)a2, (_DWORD)v7, (_DWORD)v8, (__int64)v9);
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
0x10081ed00  push    rbp
0x10081ed02  push    rsi
0x10081ed03  push    rdi
0x10081ed04  push    r12
0x10081ed06  push    r13
0x10081ed08  push    r14
0x10081ed0a  push    r15
0x10081ed0c  sub     rsp, 40h
0x10081ed10  mov     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFEh
0x10081ed19  mov     [rsp+78h+arg_18], rbx
0x10081ed21  mov     r14, rdx
0x10081ed24  mov     r15, rcx
0x10081ed27  mov     rdx, [rcx+18h]
0x10081ed2b  movzx   r8d, word ptr [rdx+18h]
0x10081ed30  movzx   eax, word ptr [rdx+6]
0x10081ed34  add     r8, rax
0x10081ed37  lea     rbx, ds:74h[r8*4]
0x10081ed3f  mov     rax, [r14+18h]
0x10081ed43  mov     rcx, [rdx+20h]
0x10081ed47  add     rcx, [rax+20h]
0x10081ed4b  movzx   edx, word ptr [rdx+2]
0x10081ed4f  call    ?GetEstimateMemReq@?$CKLLSketch@M@@SA_K_KG@Z; CKLLSketch<float>::GetEstimateMemReq(unsigned __int64,ushort)
0x10081ed54  cmp     rbx, rax
0x10081ed57  jnb     short loc_10081ED63
0x10081ed59  mov     eax, 6
0x10081ed5e  jmp     loc_10081EF4E
0x10081ed63  xor     r13d, r13d
0x10081ed66  mov     edi, r13d
0x10081ed69  mov     [rsp+78h+arg_10], r13
0x10081ed71  mov     esi, r13d
0x10081ed74  mov     [rsp+78h+arg_8], r13
0x10081ed7c  mov     ebx, r13d
0x10081ed7f  mov     [rsp+78h+arg_0], rbx
0x10081ed87  mov     rdx, [r14+18h]
0x10081ed8b  mov     rax, [r15+18h]
0x10081ed8f  mov     r12, [rdx+20h]
0x10081ed93  add     r12, [rax+20h]
0x10081ed97  mov     rax, [r14+20h]
0x10081ed9b  movzx   ebp, word ptr [rax]
0x10081ed9e  cmp     bp, [rax+2]
0x10081eda2  jnb     short loc_10081EDD3
0x10081eda4  nop     dword ptr [rax+00h]
0x10081eda8  nop     dword ptr [rax+rax+00000000h]
0x10081edb0  movzx   ecx, bp
0x10081edb3  mov     rax, [r14+28h]
0x10081edb7  mov     edx, [rax+rcx*4]
0x10081edba  mov     rcx, r15
0x10081edbd  call    ?Update@?$CKLLSketch@UMONY4@@@@QEAA?AW4KLLRETCODE@@UMONY4@@@Z; CKLLSketch<MONY4>::Update(MONY4)
0x10081edc2  inc     bp
0x10081edc5  mov     rax, [r14+20h]
0x10081edc9  cmp     bp, [rax+2]
0x10081edcd  jb      short loc_10081EDB0
0x10081edcf  mov     rdx, [r14+18h]
0x10081edd3  movzx   ecx, word ptr [rax+2]
0x10081edd7  movzx   r8d, word ptr [rdx+18h]
0x10081eddc  cmp     cx, r8w
0x10081ede0  jz      loc_10081EF24
0x10081ede6  cmp     r13w, [rdx+6]
0x10081edeb  jb      short loc_10081EDF3
0x10081eded  movzx   ecx, r13w
0x10081edf1  jmp     short loc_10081EDF6
0x10081edf3  sub     cx, [rax]
0x10081edf6  sub     r8w, cx
0x10081edfa  mov     rax, [r15+18h]
0x10081edfe  movzx   ecx, word ptr [rax+18h]
0x10081ee02  add     cx, r8w
0x10081ee06  movzx   ecx, cx
0x10081ee09  mov     eax, 4
0x10081ee0e  mul     rcx
0x10081ee11  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081ee18  cmovo   rax, rcx
0x10081ee1c  mov     byte ptr [rsp+78h+var_58], 3
0x10081ee21  mov     r9d, 181h
0x10081ee27  lea     r8, aSqlNtdbmsCommo_1; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081ee2e  mov     rdx, [r15]
0x10081ee31  mov     rcx, rax
0x10081ee34  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081ee3a  mov     rdi, rax
0x10081ee3d  test    rax, rax
0x10081ee40  jz      loc_10081EF84
0x10081ee46  xor     ecx, ecx
0x10081ee48  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081ee4e  mov     [rsp+78h+arg_10], rdi
0x10081ee56  mov     rax, [r14+18h]
0x10081ee5a  movzx   edx, word ptr [rax+6]
0x10081ee5e  mov     rax, [r15+18h]
0x10081ee62  cmp     dx, [rax+6]
0x10081ee66  cmovbe  dx, [rax+6]
0x10081ee6b  movzx   ebp, dx
0x10081ee6e  add     rbp, 2
0x10081ee72  mov     eax, 2
0x10081ee77  mul     rbp
0x10081ee7a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081ee81  cmovo   rax, rcx
0x10081ee85  mov     byte ptr [rsp+78h+var_58], 3
0x10081ee8a  mov     r9d, 190h
0x10081ee90  lea     r8, aSqlNtdbmsCommo_1; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081ee97  mov     rdx, [r15]
0x10081ee9a  mov     rcx, rax
0x10081ee9d  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081eea3  mov     rsi, rax
0x10081eea6  test    rax, rax
0x10081eea9  jz      loc_10081EF75
0x10081eeaf  xor     ecx, ecx
0x10081eeb1  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081eeb7  mov     [rsp+78h+arg_8], rsi
0x10081eebf  mov     eax, 2
0x10081eec4  mul     rbp
0x10081eec7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081eece  cmovo   rax, rcx
0x10081eed2  mov     byte ptr [rsp+78h+var_58], 3
0x10081eed7  mov     r9d, 199h
0x10081eedd  lea     r8, aSqlNtdbmsCommo_1; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081eee4  mov     rdx, [r15]
0x10081eee7  mov     rcx, rax
0x10081eeea  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081eef0  mov     rbx, rax
0x10081eef3  test    rax, rax
0x10081eef6  jz      short loc_10081EF66
0x10081eef8  xor     ecx, ecx
0x10081eefa  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081ef00  mov     [rsp+78h+arg_0], rbx
0x10081ef08  mov     [rsp+78h+var_58], rbx
0x10081ef0d  mov     r9, rsi
0x10081ef10  mov     r8, rdi
0x10081ef13  mov     rdx, r14
0x10081ef16  mov     rcx, r15
0x10081ef19  call    ?MergeHigherLevels@?$CKLLSketch@UMONY4@@@@AEAA?AW4KLLRETCODE@@AEBV1@PEAUMONY4@@PEAG2@Z; CKLLSketch<MONY4>::MergeHigherLevels(CKLLSketch<MONY4> const &,MONY4 *,ushort *,ushort *)
0x10081ef1e  mov     ebp, eax
0x10081ef20  test    eax, eax
0x10081ef22  jnz     short loc_10081EF2F
0x10081ef24  mov     rax, [r15+18h]
0x10081ef28  mov     [rax+20h], r12
0x10081ef2c  mov     ebp, r13d
0x10081ef2f  mov     rcx, rbx
0x10081ef32  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081ef38  nop
0x10081ef39  mov     rcx, rsi
0x10081ef3c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081ef42  nop
0x10081ef43  mov     rcx, rdi
0x10081ef46  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081ef4c  mov     eax, ebp
0x10081ef4e  mov     rbx, [rsp+78h+arg_18]
0x10081ef56  add     rsp, 40h
0x10081ef5a  pop     r15
0x10081ef5c  pop     r14
0x10081ef5e  pop     r13
0x10081ef60  pop     r12
0x10081ef62  pop     rdi
0x10081ef63  pop     rsi
0x10081ef64  pop     rbp
0x10081ef65  retn
0x10081ef66  mov     [rsp+78h+arg_0], rbx
0x10081ef6e  mov     ebp, 5
0x10081ef73  jmp     short loc_10081EF2F
0x10081ef75  mov     [rsp+78h+arg_8], rsi
0x10081ef7d  mov     ebp, 5
0x10081ef82  jmp     short loc_10081EF2F
0x10081ef84  mov     [rsp+78h+arg_10], rdi
0x10081ef8c  mov     ebp, 5
0x10081ef91  jmp     short loc_10081EF2F
```
