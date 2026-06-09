# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x1800072a8`
- end: `0x180007405`
- name: `?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z`
- size: `349`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800074d0`
- `0x180009a6c`
- `0x180009d8c`

## callees

- `0x1800012e0`
- `0x1800012ec`
- `0x180001830`
- `0x1800072a8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180007352`
- `msvcrt!memcpy_s` at `0x180007364`
- `msvcrt!memcpy_s` at `0x180007352`
- `msvcrt!memcpy_s` at `0x180007364`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::Add(
        ATL::CExpansionVector *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rax
  __int64 v7; // r12
  void *v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // r15
  void *v11; // rax
  void *v12; // rbx
  unsigned int v13; // ebp
  void *v14; // rax
  void *v15; // rcx
  void *v16; // rax
  __int64 v17; // rdx
  _QWORD *v18; // rcx
  _QWORD *v19; // rcx

  if ( !a2 || !a3 )
    return 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6 + 2;
  v8 = operator new[](saturated_mul(v7, 2u));
  v9 = -1;
  do
    ++v9;
  while ( a3[v9] );
  v10 = 2LL * ((int)v9 + 1);
  v11 = operator new[](saturated_mul(v10, 2u));
  v12 = v11;
  if ( v8
    && v11
    && (memcpy_s(v8, v7, a2, v7),
        memcpy_s(v12, v10, a3, v10),
        v13 = 1,
        (v14 = _recalloc(*(void **)this, *((_DWORD *)this + 4) + 1, 8u)) != 0)
    && (v15 = (void *)*((_QWORD *)this + 1),
        *(_QWORD *)this = v14,
        (v16 = _recalloc(v15, *((_DWORD *)this + 4) + 1, 8u)) != 0) )
  {
    v17 = *((int *)this + 4);
    *((_QWORD *)this + 1) = v16;
    v18 = (_QWORD *)(*(_QWORD *)this + 8 * v17);
    if ( v18 )
      *v18 = v8;
    v19 = (_QWORD *)(*((_QWORD *)this + 1) + 8 * v17);
    if ( v19 )
      *v19 = v12;
    ++*((_DWORD *)this + 4);
    v8 = 0;
    v12 = 0;
  }
  else
  {
    v13 = 0;
  }
  operator delete[](v12);
  operator delete[](v8);
  return v13;
}

```

## disassembly

```asm
0x1800072a8  push    rbx
0x1800072aa  push    rbp
0x1800072ab  push    rsi
0x1800072ac  push    rdi
0x1800072ad  push    r12
0x1800072af  push    r13
0x1800072b1  push    r14
0x1800072b3  push    r15
0x1800072b5  sub     rsp, 28h
0x1800072b9  xor     r13d, r13d
0x1800072bc  mov     rbp, r8
0x1800072bf  mov     r14, rdx
0x1800072c2  mov     rsi, rcx
0x1800072c5  test    rdx, rdx
0x1800072c8  jz      loc_1800073F2
0x1800072ce  test    r8, r8
0x1800072d1  jz      loc_1800073F2
0x1800072d7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800072db  mov     rax, rbx
0x1800072de  inc     rax
0x1800072e1  cmp     [rdx+rax*2], r13w
0x1800072e6  jnz     short loc_1800072DE
0x1800072e8  lea     r12, ds:2[rax*2]
0x1800072f0  mov     eax, 2
0x1800072f5  mul     r12
0x1800072f8  cmovb   rax, rbx
0x1800072fc  mov     rcx, rax; unsigned __int64
0x1800072ff  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007304  mov     rdi, rax
0x180007307  mov     rcx, rbx
0x18000730a  inc     rcx
0x18000730d  cmp     [rbp+rcx*2+0], r13w
0x180007313  jnz     short loc_18000730A
0x180007315  inc     ecx
0x180007317  mov     eax, 2
0x18000731c  movsxd  r15, ecx
0x18000731f  add     r15, r15
0x180007322  mul     r15
0x180007325  cmovb   rax, rbx
0x180007329  mov     rcx, rax; unsigned __int64
0x18000732c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007331  mov     rbx, rax
0x180007334  test    rdi, rdi
0x180007337  jz      loc_1800073DB
0x18000733d  test    rax, rax
0x180007340  jz      loc_1800073DB
0x180007346  mov     r9, r12; SourceSize
0x180007349  mov     r8, r14; Source
0x18000734c  mov     rdx, r12; DestinationSize
0x18000734f  mov     rcx, rdi; Destination
0x180007352  call    cs:__imp_memcpy_s
0x180007358  mov     r9, r15; SourceSize
0x18000735b  mov     r8, rbp; Source
0x18000735e  mov     rdx, r15; DestinationSize
0x180007361  mov     rcx, rbx; Destination
0x180007364  call    cs:__imp_memcpy_s
0x18000736a  mov     eax, [rsi+10h]
0x18000736d  mov     ebp, 1
0x180007372  mov     rcx, [rsi]; Block
0x180007375  add     eax, ebp
0x180007377  movsxd  rdx, eax; Count
0x18000737a  lea     r14d, [rbp+7]
0x18000737e  mov     r8d, r14d; Size
0x180007381  call    cs:__imp__recalloc
0x180007387  test    rax, rax
0x18000738a  jz      short loc_1800073DB
0x18000738c  mov     rcx, [rsi+8]; Block
0x180007390  mov     r8d, r14d; Size
0x180007393  mov     [rsi], rax
0x180007396  mov     eax, [rsi+10h]
0x180007399  add     eax, ebp
0x18000739b  movsxd  rdx, eax; Count
0x18000739e  call    cs:__imp__recalloc
0x1800073a4  test    rax, rax
0x1800073a7  jz      short loc_1800073DB
0x1800073a9  movsxd  rdx, dword ptr [rsi+10h]
0x1800073ad  mov     [rsi+8], rax
0x1800073b1  mov     rax, [rsi]
0x1800073b4  lea     rcx, [rax+rdx*8]
0x1800073b8  test    rcx, rcx
0x1800073bb  jz      short loc_1800073C0
0x1800073bd  mov     [rcx], rdi
0x1800073c0  mov     rax, [rsi+8]
0x1800073c4  lea     rcx, [rax+rdx*8]
0x1800073c8  test    rcx, rcx
0x1800073cb  jz      short loc_1800073D0
0x1800073cd  mov     [rcx], rbx
0x1800073d0  add     [rsi+10h], ebp
0x1800073d3  mov     rdi, r13
0x1800073d6  mov     rbx, r13
0x1800073d9  jmp     short loc_1800073DE
0x1800073db  mov     ebp, r13d
0x1800073de  mov     rcx, rbx; Block
0x1800073e1  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800073e6  mov     rcx, rdi; Block
0x1800073e9  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800073ee  mov     eax, ebp
0x1800073f0  jmp     short loc_1800073F4
0x1800073f2  xor     eax, eax
0x1800073f4  add     rsp, 28h
0x1800073f8  pop     r15
0x1800073fa  pop     r14
0x1800073fc  pop     r13
0x1800073fe  pop     r12
0x180007400  pop     rdi
0x180007401  pop     rsi
0x180007402  pop     rbp
0x180007403  pop     rbx
0x180007404  retn
```
