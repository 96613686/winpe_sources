# HTTP_CopyResolverHint(void *,void *,int)

- ea: `0x18000bfe0`
- end: `0x18000c159`
- name: `?HTTP_CopyResolverHint@@YAJPEAX0H@Z`
- size: `377`
- prototype: `__int64 __fastcall(HTTPResolverHint *this, void *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180006050`

## callees

- `0x18000a5dc`
- `0x18000aa98`
- `0x18000aac4`
- `0x18000bfe0`
- `0x18002461d`

## import_xrefs

- `RPCRT4!I_RpcAllocate` at `0x18000c0a8`
- `RPCRT4!I_RpcAllocate` at `0x18000c0cb`
- `RPCRT4!I_RpcAllocate` at `0x18000c106`
- `RPCRT4!I_RpcAllocate` at `0x18000c0a8`
- `RPCRT4!I_RpcAllocate` at `0x18000c0cb`
- `RPCRT4!I_RpcAllocate` at `0x18000c106`

## pseudocode

```c
__int64 __fastcall HTTP_CopyResolverHint(HTTPResolverHint *this, char *a2, int a3)
{
  __int64 v5; // rcx
  __int64 v6; // rax
  unsigned int v7; // esi
  void *v8; // rax
  void *v9; // rax
  void *v10; // rax

  *(_OWORD *)this = *(_OWORD *)a2;
  *((_OWORD *)this + 1) = *((_OWORD *)a2 + 1);
  *((_OWORD *)this + 2) = *((_OWORD *)a2 + 2);
  *((_OWORD *)this + 3) = *((_OWORD *)a2 + 3);
  *((_OWORD *)this + 4) = *((_OWORD *)a2 + 4);
  *((_OWORD *)this + 5) = *((_OWORD *)a2 + 5);
  *((_OWORD *)this + 6) = *((_OWORD *)a2 + 6);
  *((_OWORD *)this + 7) = *((_OWORD *)a2 + 7);
  *((_OWORD *)this + 8) = *((_OWORD *)a2 + 8);
  if ( a3 )
  {
    if ( *((char **)a2 + 5) == a2 + 48 )
      *((_QWORD *)this + 5) = (char *)this + 48;
    *((_QWORD *)a2 + 14) = 0;
    *((_QWORD *)a2 + 12) = 0;
    *((_QWORD *)a2 + 5) = 0;
    return 0;
  }
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 5) = 0;
  v5 = *((_QWORD *)a2 + 14);
  if ( v5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_BYTE *)(v5 + v6) );
    v7 = v6 + 1;
    v8 = I_RpcAllocate((int)v6 + 1);
    *((_QWORD *)this + 14) = v8;
    if ( !v8 )
      goto LABEL_16;
    memcpy_0(v8, *((const void **)a2 + 14), v7);
  }
  v9 = I_RpcAllocate(*((_DWORD *)a2 + 26) + 1);
  *((_QWORD *)this + 12) = v9;
  if ( v9 )
  {
    memcpy_0(v9, *((const void **)a2 + 12), (unsigned int)(*((_DWORD *)a2 + 26) + 1));
    if ( *((char **)a2 + 5) == a2 + 48 )
    {
      *((_QWORD *)this + 5) = (char *)this + 48;
      return 0;
    }
    v10 = I_RpcAllocate(*((_DWORD *)a2 + 22) + 1);
    *((_QWORD *)this + 5) = v10;
    if ( v10 )
    {
      memcpy_0(v10, *((const void **)a2 + 5), (unsigned int)(*((_DWORD *)a2 + 22) + 1));
      return 0;
    }
  }
LABEL_16:
  HTTPResolverHint::FreeHTTPProxy(this);
  HTTPResolverHint::FreeRpcProxy(this);
  HTTPResolverHint::FreeRpcServer(this);
  return 14;
}

```

## disassembly

```asm
0x18000bfe0  mov     [rsp+arg_0], rbx
0x18000bfe5  mov     [rsp+arg_8], rsi
0x18000bfea  push    rdi
0x18000bfeb  sub     rsp, 20h
0x18000bfef  mov     rbx, rdx
0x18000bff2  mov     rdi, rcx
0x18000bff5  movups  xmm0, xmmword ptr [rdx]
0x18000bff8  movups  xmmword ptr [rcx], xmm0
0x18000bffb  movups  xmm1, xmmword ptr [rdx+10h]
0x18000bfff  movups  xmmword ptr [rcx+10h], xmm1
0x18000c003  movups  xmm0, xmmword ptr [rdx+20h]
0x18000c007  movups  xmmword ptr [rcx+20h], xmm0
0x18000c00b  movups  xmm1, xmmword ptr [rdx+30h]
0x18000c00f  movups  xmmword ptr [rcx+30h], xmm1
0x18000c013  movups  xmm0, xmmword ptr [rdx+40h]
0x18000c017  movups  xmmword ptr [rcx+40h], xmm0
0x18000c01b  movups  xmm1, xmmword ptr [rdx+50h]
0x18000c01f  movups  xmmword ptr [rcx+50h], xmm1
0x18000c023  movups  xmm0, xmmword ptr [rdx+60h]
0x18000c027  movups  xmmword ptr [rcx+60h], xmm0
0x18000c02b  movups  xmm1, xmmword ptr [rdx+70h]
0x18000c02f  movups  xmmword ptr [rcx+70h], xmm1
0x18000c033  movups  xmm0, xmmword ptr [rdx+80h]
0x18000c03a  movups  xmmword ptr [rcx+80h], xmm0
0x18000c041  test    r8d, r8d
0x18000c044  jz      short loc_18000C075
0x18000c046  lea     rax, [rdx+30h]
0x18000c04a  cmp     [rdx+28h], rax
0x18000c04e  jnz     short loc_18000C058
0x18000c050  lea     rax, [rcx+30h]
0x18000c054  mov     [rcx+28h], rax
0x18000c058  mov     qword ptr [rdx+70h], 0
0x18000c060  mov     qword ptr [rdx+60h], 0
0x18000c068  mov     qword ptr [rdx+28h], 0
0x18000c070  jmp     loc_18000C128
0x18000c075  mov     qword ptr [rcx+70h], 0
0x18000c07d  mov     qword ptr [rcx+60h], 0
0x18000c085  mov     qword ptr [rcx+28h], 0
0x18000c08d  mov     rcx, [rdx+70h]
0x18000c091  test    rcx, rcx
0x18000c094  jz      short loc_18000C0C6
0x18000c096  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c09a  inc     rax
0x18000c09d  cmp     byte ptr [rcx+rax], 0
0x18000c0a1  jnz     short loc_18000C09A
0x18000c0a3  lea     esi, [rax+1]
0x18000c0a6  mov     ecx, esi; Size
0x18000c0a8  call    cs:__imp_I_RpcAllocate
0x18000c0ae  mov     [rdi+70h], rax
0x18000c0b2  test    rax, rax
0x18000c0b5  jz      short loc_18000C12C
0x18000c0b7  mov     rdx, [rbx+70h]; Src
0x18000c0bb  mov     rcx, rax; void *
0x18000c0be  mov     r8d, esi; Size
0x18000c0c1  call    memcpy_0
0x18000c0c6  mov     ecx, [rbx+68h]
0x18000c0c9  inc     ecx; Size
0x18000c0cb  call    cs:__imp_I_RpcAllocate
0x18000c0d1  mov     [rdi+60h], rax
0x18000c0d5  test    rax, rax
0x18000c0d8  jz      short loc_18000C12C
0x18000c0da  mov     r8d, [rbx+68h]
0x18000c0de  mov     rcx, rax; void *
0x18000c0e1  mov     rdx, [rbx+60h]; Src
0x18000c0e5  inc     r8d; Size
0x18000c0e8  call    memcpy_0
0x18000c0ed  lea     rax, [rbx+30h]
0x18000c0f1  cmp     [rbx+28h], rax
0x18000c0f5  jnz     short loc_18000C101
0x18000c0f7  lea     rax, [rdi+30h]
0x18000c0fb  mov     [rdi+28h], rax
0x18000c0ff  jmp     short loc_18000C128
0x18000c101  mov     ecx, [rbx+58h]
0x18000c104  inc     ecx; Size
0x18000c106  call    cs:__imp_I_RpcAllocate
0x18000c10c  mov     [rdi+28h], rax
0x18000c110  test    rax, rax
0x18000c113  jz      short loc_18000C12C
0x18000c115  mov     r8d, [rbx+58h]
0x18000c119  mov     rcx, rax; void *
0x18000c11c  mov     rdx, [rbx+28h]; Src
0x18000c120  inc     r8d; Size
0x18000c123  call    memcpy_0
0x18000c128  xor     eax, eax
0x18000c12a  jmp     short loc_18000C149
0x18000c12c  mov     rcx, rdi; this
0x18000c12f  call    ?FreeHTTPProxy@HTTPResolverHint@@QEAAXXZ; HTTPResolverHint::FreeHTTPProxy(void)
0x18000c134  mov     rcx, rdi; this
0x18000c137  call    ?FreeRpcProxy@HTTPResolverHint@@QEAAXXZ; HTTPResolverHint::FreeRpcProxy(void)
0x18000c13c  mov     rcx, rdi; this
0x18000c13f  call    ?FreeRpcServer@HTTPResolverHint@@QEAAXXZ; HTTPResolverHint::FreeRpcServer(void)
0x18000c144  mov     eax, 0Eh
0x18000c149  mov     rbx, [rsp+28h+arg_0]
0x18000c14e  mov     rsi, [rsp+28h+arg_8]
0x18000c153  add     rsp, 20h
0x18000c157  pop     rdi
0x18000c158  retn
```
