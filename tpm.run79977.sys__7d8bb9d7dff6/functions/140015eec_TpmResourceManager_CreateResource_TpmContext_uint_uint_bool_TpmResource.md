# TpmResourceManager::CreateResource(TpmContext *,uint,uint,bool,TpmResource * *)

- ea: `0x140015eec`
- end: `0x14001600d`
- name: `?CreateResource@TpmResourceManager@@AEAAJPEAVTpmContext@@II_NPEAPEAVTpmResource@@@Z`
- size: `289`
- prototype: `__int64 __usercall@<rax>(TpmResourceManager *__hidden this@<rcx>, struct _LIST_ENTRY *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, bool, struct TpmResource **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400135d0`

## callees

- `0x140015eec`
- `0x14001aa30`
- `0x14001f4bc`
- `0x140039b40`
- `0x140045430`

## pseudocode

```c
__int64 __fastcall TpmResourceManager::CreateResource(
        TpmResourceManager ***this,
        struct _LIST_ENTRY *a2,
        unsigned int a3,
        unsigned int a4,
        bool a5,
        struct TpmResource **a6)
{
  unsigned int v10; // esi
  struct TpmResource **v11; // r14
  unsigned __int8 *v12; // rax
  unsigned __int8 *v13; // rbx
  struct _LIST_ENTRY *Blink; // rcx
  TpmResourceManager **v15; // rcx
  unsigned int v16; // edi
  unsigned __int64 retaddr; // [rsp+48h] [rbp+0h]
  unsigned int v19; // [rsp+60h] [rbp+18h] BYREF

  v19 = a3;
  v10 = -1;
  do
  {
    if ( a5 )
    {
      v10 = ++LODWORD(a2[2].Flink);
    }
    else
    {
      if ( v10 == a3 )
      {
        v16 = -2144861182;
        goto LABEL_14;
      }
      v10 = a3;
    }
  }
  while ( TpmResourceManager::FindResource((TpmResourceManager *)this, a2, v10) );
  v11 = a6;
  v12 = TpmAlloc(1, 0x60u, retaddr);
  v13 = v12;
  if ( !v12 )
  {
    *v11 = 0;
    v16 = -1073741670;
LABEL_14:
    TpmResourceManager::FlushResource((TpmResourceManager *)this, a4, &v19, 0);
    return v16;
  }
  memset(v12, 0, 0x60u);
  *((_DWORD *)v13 + 9) = v10;
  *((_DWORD *)v13 + 10) = a3;
  *((_DWORD *)v13 + 11) = a4;
  v13[76] = 1;
  *((_QWORD *)v13 + 1) = v13;
  *(_QWORD *)v13 = v13;
  *((_QWORD *)v13 + 3) = v13 + 16;
  *((_QWORD *)v13 + 2) = v13 + 16;
  Blink = a2->Blink;
  *v11 = (struct TpmResource *)v13;
  if ( Blink->Flink != a2
    || (*((_QWORD *)v13 + 2) = a2,
        *((_QWORD *)v13 + 3) = Blink,
        Blink->Flink = (struct _LIST_ENTRY *)(v13 + 16),
        a2->Blink = (struct _LIST_ENTRY *)(v13 + 16),
        v15 = this[2],
        *v15 != (TpmResourceManager *)(this + 1)) )
  {
    __fastfail(3u);
  }
  *(_QWORD *)v13 = this + 1;
  v16 = 0;
  *((_QWORD *)v13 + 1) = v15;
  *v15 = (TpmResourceManager *)v13;
  this[2] = (TpmResourceManager **)v13;
  return v16;
}

```

## disassembly

```asm
0x140015eec  mov     [rsp+arg_0], rbx
0x140015ef1  mov     [rsp+arg_8], rbp
0x140015ef6  mov     [rsp+arg_10], r8d
0x140015efb  push    rsi
0x140015efc  push    rdi
0x140015efd  push    r12
0x140015eff  push    r14
0x140015f01  push    r15
0x140015f03  sub     rsp, 20h
0x140015f07  mov     r12d, r9d
0x140015f0a  mov     ebp, r8d
0x140015f0d  mov     rdi, rdx
0x140015f10  mov     r15, rcx
0x140015f13  or      esi, 0FFFFFFFFh
0x140015f16  cmp     [rsp+48h+arg_20], 0
0x140015f1b  jz      short loc_140015F25
0x140015f1d  inc     dword ptr [rdi+20h]
0x140015f20  mov     esi, [rdi+20h]
0x140015f23  jmp     short loc_140015F2F
0x140015f25  cmp     esi, ebp
0x140015f27  jz      loc_140015FDB
0x140015f2d  mov     esi, ebp
0x140015f2f  mov     r8d, esi; unsigned int
0x140015f32  mov     rdx, rdi; struct _LIST_ENTRY *
0x140015f35  call    ?FindResource@TpmResourceManager@@AEAAPEAVTpmResource@@PEAU_LIST_ENTRY@@I@Z; TpmResourceManager::FindResource(_LIST_ENTRY *,uint)
0x140015f3a  test    rax, rax
0x140015f3d  jnz     short loc_140015F16
0x140015f3f  mov     r8, [rsp+48h]; unsigned __int64
0x140015f44  lea     edx, [rax+60h]; unsigned __int64
0x140015f47  mov     r14, [rsp+48h+arg_28]
0x140015f4c  mov     cl, 1; bool
0x140015f4e  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x140015f53  mov     rbx, rax
0x140015f56  test    rax, rax
0x140015f59  jz      short loc_140015FCD
0x140015f5b  xor     edx, edx; Val
0x140015f5d  mov     rcx, rax; void *
0x140015f60  lea     r8d, [rdx+60h]; Size
0x140015f64  call    memset
0x140015f69  mov     [rbx+24h], esi
0x140015f6c  lea     rcx, [rbx+10h]
0x140015f70  mov     [rbx+28h], ebp
0x140015f73  mov     [rbx+2Ch], r12d
0x140015f77  mov     byte ptr [rbx+4Ch], 1
0x140015f7b  mov     [rbx+8], rbx
0x140015f7f  mov     [rbx], rbx
0x140015f82  mov     [rcx+8], rcx
0x140015f86  mov     [rcx], rcx
0x140015f89  mov     rcx, [rdi+8]
0x140015f8d  mov     [r14], rbx
0x140015f90  cmp     [rcx], rdi
0x140015f93  jnz     short loc_140015FC6
0x140015f95  lea     rax, [rbx+10h]
0x140015f99  mov     [rax], rdi
0x140015f9c  mov     [rax+8], rcx
0x140015fa0  mov     [rcx], rax
0x140015fa3  mov     [rdi+8], rax
0x140015fa7  lea     rax, [r15+8]
0x140015fab  mov     rcx, [rax+8]
0x140015faf  cmp     [rcx], rax
0x140015fb2  jnz     short loc_140015FC6
0x140015fb4  mov     [rbx], rax
0x140015fb7  xor     edi, edi
0x140015fb9  mov     [rbx+8], rcx
0x140015fbd  mov     [rcx], rbx
0x140015fc0  mov     [rax+8], rbx
0x140015fc4  jmp     short loc_140015FF3
0x140015fc6  mov     ecx, 3
0x140015fcb  int     29h; Win8: RtlFailFast(ecx)
0x140015fcd  mov     qword ptr [r14], 0
0x140015fd4  mov     edi, 0C000009Ah
0x140015fd9  jmp     short loc_140015FE0
0x140015fdb  mov     edi, 80280402h
0x140015fe0  xor     r9d, r9d; struct _LIST_ENTRY *
0x140015fe3  lea     r8, [rsp+48h+arg_10]; unsigned int *
0x140015fe8  mov     edx, r12d; unsigned int
0x140015feb  mov     rcx, r15; this
0x140015fee  call    ?FlushResource@TpmResourceManager@@AEAAJIPEAIPEAU_LIST_ENTRY@@@Z; TpmResourceManager::FlushResource(uint,uint *,_LIST_ENTRY *)
0x140015ff3  mov     rbx, [rsp+48h+arg_0]
0x140015ff8  mov     eax, edi
0x140015ffa  mov     rbp, [rsp+48h+arg_8]
0x140015fff  add     rsp, 20h
0x140016003  pop     r15
0x140016005  pop     r14
0x140016007  pop     r12
0x140016009  pop     rdi
0x14001600a  pop     rsi
0x14001600b  retn
```
