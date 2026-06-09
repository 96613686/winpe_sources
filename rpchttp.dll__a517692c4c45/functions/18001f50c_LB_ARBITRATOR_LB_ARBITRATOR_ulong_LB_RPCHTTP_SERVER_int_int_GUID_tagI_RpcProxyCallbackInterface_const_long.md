# LB_ARBITRATOR::LB_ARBITRATOR(ulong,LB_RPCHTTP_SERVER * *,int,int,_GUID *,tagI_RpcProxyCallbackInterface const *,long *)

- ea: `0x18001f50c`
- end: `0x18001f6a4`
- name: `??0LB_ARBITRATOR@@QEAA@KPEAPEAVLB_RPCHTTP_SERVER@@HHPEAU_GUID@@PEBUtagI_RpcProxyCallbackInterface@@PEAJ@Z`
- size: `408`
- prototype: `LB_ARBITRATOR *__fastcall(LB_ARBITRATOR *this, unsigned int, struct LB_RPCHTTP_SERVER **, int, int, struct _GUID *, const struct tagI_RpcProxyCallbackInterface *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001fc58`

## callees

- `0x18000185c`
- `0x18001f50c`
- `0x180024629`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18001f634`
- `RPCRT4!UuidCreate` at `0x18001f634`
- `RPCRT4!I_RpcAllocate` at `0x18001f57f`
- `RPCRT4!I_RpcAllocate` at `0x18001f5ca`
- `RPCRT4!I_RpcAllocate` at `0x18001f5fc`
- `RPCRT4!I_RpcAllocate` at `0x18001f57f`
- `RPCRT4!I_RpcAllocate` at `0x18001f5ca`
- `RPCRT4!I_RpcAllocate` at `0x18001f5fc`

## pseudocode

```c
LB_ARBITRATOR *__fastcall LB_ARBITRATOR::LB_ARBITRATOR(
        LB_ARBITRATOR *this,
        unsigned int a2,
        struct LB_RPCHTTP_SERVER **a3,
        int a4,
        int a5,
        struct _GUID *a6,
        const struct tagI_RpcProxyCallbackInterface *a7,
        int *a8)
{
  __int64 v9; // rbp
  unsigned __int64 v10; // rdi
  unsigned int v12; // eax
  void *v14; // rax
  void *v15; // rsi
  unsigned int v16; // eax
  void *v17; // rax
  unsigned int v18; // eax
  void *v19; // rax
  int v20; // eax
  unsigned int *v21; // rdi
  RPC_STATUS v22; // eax
  int v23; // ecx
  unsigned int v24; // ecx
  __int128 v25; // xmm0

  *((_QWORD *)this + 13) = a7;
  v9 = a2;
  v10 = a2;
  v12 = 184 * a2;
  *(_DWORD *)this = 0;
  *((_QWORD *)this + 3) = 0;
  if ( !is_mul_ok(a2, 0xB8u) )
    v12 = -1;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 7) = 0;
  v14 = I_RpcAllocate(v12);
  v15 = v14;
  if ( !v14 )
  {
    *((_QWORD *)this + 3) = 0;
LABEL_19:
    v23 = 14;
    goto LABEL_20;
  }
  `vector constructor iterator'(v14, 0xB8u, (unsigned int)v10, (void *(*)(void *))LBS_CALL::LBS_CALL);
  *((_QWORD *)this + 3) = v15;
  memset_0(v15, 0, 184 * v10);
  v16 = 8 * v10;
  if ( !is_mul_ok(v10, 8u) )
    v16 = -1;
  v17 = I_RpcAllocate(v16);
  *((_QWORD *)this + 4) = v17;
  if ( !v17 )
    goto LABEL_19;
  memset_0(v17, 0, 8 * v9);
  v18 = 4 * v10;
  if ( !is_mul_ok(v10, 4u) )
    v18 = -1;
  v19 = I_RpcAllocate(v18);
  *((_QWORD *)this + 5) = v19;
  if ( !v19 )
    goto LABEL_19;
  memset_0(v19, 0, 4 * v9);
  if ( a5 )
  {
    v20 = 1;
LABEL_17:
    *((_DWORD *)this + 16) = v20;
    v23 = 0;
    v25 = (__int128)*a6;
    *((_DWORD *)this + 12) = v9;
    *((_QWORD *)this + 7) = a3;
    *(_OWORD *)((char *)this + 84) = v25;
    goto LABEL_20;
  }
  v21 = (unsigned int *)((char *)this + 68);
  v22 = UuidCreate((UUID *)((char *)this + 68));
  v23 = v22;
  if ( !v22 || v22 == 1824 )
  {
    v24 = *v21 & 0x7FFFFFFF;
    if ( !a4 )
      v24 = *v21 | 0x80000000;
    v20 = 0;
    *v21 = v24;
    goto LABEL_17;
  }
LABEL_20:
  *a8 = v23;
  return this;
}

```

## disassembly

```asm
0x18001f50c  push    rbx
0x18001f50e  push    rbp
0x18001f50f  push    rsi
0x18001f510  push    rdi
0x18001f511  push    r13
0x18001f513  push    r14
0x18001f515  push    r15
0x18001f517  sub     rsp, 20h
0x18001f51b  mov     rax, [rsp+58h+arg_30]
0x18001f523  mov     rbx, rcx
0x18001f526  mov     [rcx+68h], rax
0x18001f52a  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18001f531  mov     ebp, edx
0x18001f533  mov     eax, 0B8h
0x18001f538  mov     edi, edx
0x18001f53a  mov     r15d, r9d
0x18001f53d  mul     rbp
0x18001f540  mov     dword ptr [rcx], 0
0x18001f546  mov     r14, r8
0x18001f549  mov     qword ptr [rcx+18h], 0
0x18001f551  cmovb   rax, r13
0x18001f555  mov     qword ptr [rcx+20h], 0
0x18001f55d  mov     qword ptr [rcx+28h], 0
0x18001f565  mov     qword ptr [rcx+8], 0
0x18001f56d  mov     qword ptr [rcx+10h], 0
0x18001f575  mov     qword ptr [rcx+38h], 0
0x18001f57d  mov     ecx, eax; Size
0x18001f57f  call    cs:__imp_I_RpcAllocate
0x18001f585  mov     rsi, rax
0x18001f588  test    rax, rax
0x18001f58b  jz      loc_18001F67B
0x18001f591  lea     r9, ??0LBS_CALL@@QEAA@XZ; void *(*)(void *)
0x18001f598  mov     r8d, edi; unsigned __int64
0x18001f59b  mov     edx, 0B8h; unsigned __int64
0x18001f5a0  mov     rcx, rax; void *
0x18001f5a3  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18001f5a8  imul    r8, rdi, 0B8h; Size
0x18001f5af  xor     edx, edx; Val
0x18001f5b1  mov     [rbx+18h], rsi
0x18001f5b5  mov     rcx, rsi; void *
0x18001f5b8  call    memset_0
0x18001f5bd  lea     eax, [r13+9]
0x18001f5c1  mul     rdi
0x18001f5c4  cmovb   rax, r13
0x18001f5c8  mov     ecx, eax; Size
0x18001f5ca  call    cs:__imp_I_RpcAllocate
0x18001f5d0  mov     [rbx+20h], rax
0x18001f5d4  test    rax, rax
0x18001f5d7  jz      loc_18001F683
0x18001f5dd  lea     r8, ds:0[rbp*8]; Size
0x18001f5e5  xor     edx, edx; Val
0x18001f5e7  mov     rcx, rax; void *
0x18001f5ea  call    memset_0
0x18001f5ef  lea     eax, [r13+5]
0x18001f5f3  mul     rdi
0x18001f5f6  cmovb   rax, r13
0x18001f5fa  mov     ecx, eax; Size
0x18001f5fc  call    cs:__imp_I_RpcAllocate
0x18001f602  mov     [rbx+28h], rax
0x18001f606  test    rax, rax
0x18001f609  jz      short loc_18001F683
0x18001f60b  lea     r8, ds:0[rbp*4]; Size
0x18001f613  xor     edx, edx; Val
0x18001f615  mov     rcx, rax; void *
0x18001f618  call    memset_0
0x18001f61d  cmp     [rsp+58h+arg_20], 0
0x18001f625  jz      short loc_18001F62D
0x18001f627  lea     eax, [r13+2]
0x18001f62b  jmp     short loc_18001F65D
0x18001f62d  lea     rdi, [rbx+44h]
0x18001f631  mov     rcx, rdi; Uuid
0x18001f634  call    cs:__imp_UuidCreate
0x18001f63a  mov     ecx, eax
0x18001f63c  test    eax, eax
0x18001f63e  jz      short loc_18001F647
0x18001f640  cmp     eax, 720h
0x18001f645  jnz     short loc_18001F688
0x18001f647  mov     ecx, [rdi]
0x18001f649  mov     eax, ecx
0x18001f64b  bts     eax, 1Fh
0x18001f64f  btr     ecx, 1Fh
0x18001f653  test    r15d, r15d
0x18001f656  cmovz   ecx, eax
0x18001f659  xor     eax, eax
0x18001f65b  mov     [rdi], ecx
0x18001f65d  mov     [rbx+40h], eax
0x18001f660  xor     ecx, ecx
0x18001f662  mov     rax, [rsp+58h+arg_28]
0x18001f66a  movups  xmm0, xmmword ptr [rax]
0x18001f66d  mov     [rbx+30h], ebp
0x18001f670  mov     [rbx+38h], r14
0x18001f674  movdqu  xmmword ptr [rbx+54h], xmm0
0x18001f679  jmp     short loc_18001F688
0x18001f67b  mov     qword ptr [rbx+18h], 0
0x18001f683  mov     ecx, 0Eh
0x18001f688  mov     rax, [rsp+58h+arg_38]
0x18001f690  mov     [rax], ecx
0x18001f692  mov     rax, rbx
0x18001f695  add     rsp, 20h
0x18001f699  pop     r15
0x18001f69b  pop     r14
0x18001f69d  pop     r13
0x18001f69f  pop     rdi
0x18001f6a0  pop     rsi
0x18001f6a1  pop     rbp
0x18001f6a2  pop     rbx
0x18001f6a3  retn
```
