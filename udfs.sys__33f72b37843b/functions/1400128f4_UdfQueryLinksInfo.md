# UdfQueryLinksInfo

- ea: `0x1400128f4`
- end: `0x140012a83`
- name: `UdfQueryLinksInfo`
- size: `399`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140047a10`

## callees

- `0x1400128f4`
- `0x14001bd80`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14001295c`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001295c`
- `ntoskrnl!ExReleaseFastMutex` at `0x140012a63`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001d9c4`
- `ntoskrnl!ExReleaseFastMutex` at `0x140012a63`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001d9c4`

## pseudocode

```c
__int64 __fastcall UdfQueryLinksInfo(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  unsigned int v7; // edx
  unsigned int v8; // r12d
  unsigned int *v9; // r13
  struct _KTHREAD *CurrentThread; // rbx
  __int64 v11; // rcx
  __int64 *v12; // rax
  __int64 *v13; // rsi
  int v14; // ecx
  unsigned int v15; // ebx
  __int64 v16; // rcx
  int v18; // [rsp+70h] [rbp+8h]
  unsigned int v19; // [rsp+80h] [rbp+18h]

  v7 = 0;
  v19 = 0;
  v8 = 0;
  *(_DWORD *)(a1 + 28) |= 4u;
  *a5 -= 32;
  *(_QWORD *)a4 = 32;
  v9 = (unsigned int *)(a4 + 8);
  CurrentThread = KeGetCurrentThread();
  v11 = *(_QWORD *)(a2 + 136);
  if ( CurrentThread != *(struct _KTHREAD **)(v11 + 64) )
  {
    ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v11 + 80) + 216LL));
    *(_QWORD *)(*(_QWORD *)(a2 + 136) + 64LL) = CurrentThread;
    v7 = 0;
  }
  ++*(_DWORD *)(*(_QWORD *)(a2 + 136) + 72LL);
  v12 = (__int64 *)(a2 + 160);
  v13 = *(__int64 **)(a2 + 160);
  while ( v13 != v12 )
  {
    v14 = *((unsigned __int16 *)v13 + 48) + 20;
    v18 = v14;
    *(_DWORD *)a4 += v14 + v7;
    if ( v14 + v7 > *a5 )
    {
      v8 = -2147483643;
      break;
    }
    ++*(_DWORD *)(a4 + 4);
    v15 = (v14 + 7) & 0xFFFFFFF8;
    *v9 = v15;
    *((_QWORD *)v9 + 1) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(v13 - 1) + 136) + 16LL) + 184LL);
    v9[4] = *((unsigned __int16 *)v13 + 48) >> 1;
    memmove(v9 + 5, (const void *)v13[13], *((unsigned __int16 *)v13 + 48));
    *a5 -= v18 + v19;
    v9 = (unsigned int *)((char *)v9 + *v9);
    v7 = v15 - v18;
    v19 = v15 - v18;
    v13 = (__int64 *)*v13;
    v12 = (__int64 *)(a2 + 160);
  }
  --*(_DWORD *)(*(_QWORD *)(a2 + 136) + 72LL);
  v16 = *(_QWORD *)(a2 + 136);
  if ( !*(_DWORD *)(v16 + 72) )
  {
    *(_QWORD *)(v16 + 64) = 0;
    ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(a2 + 136) + 80LL) + 216LL));
  }
  return v8;
}

```

## disassembly

```asm
0x1400128f4  mov     rax, rsp
0x1400128f7  mov     [rax+18h], r8
0x1400128fb  mov     [rax+10h], rdx
0x1400128ff  push    rbx
0x140012900  push    rsi
0x140012901  push    rdi
0x140012902  push    r12
0x140012904  push    r13
0x140012906  push    r14
0x140012908  push    r15
0x14001290a  sub     rsp, 30h
0x14001290e  mov     r14, r9
0x140012911  mov     rdi, rdx
0x140012914  xor     edx, edx
0x140012916  mov     [rax+18h], edx
0x140012919  xor     r12d, r12d
0x14001291c  or      dword ptr [rcx+1Ch], 4
0x140012920  mov     r15, [rsp+68h+arg_20]
0x140012928  add     dword ptr [r15], 0FFFFFFE0h
0x14001292c  mov     qword ptr [r9], 20h ; ' '
0x140012933  lea     r13, [r9+8]
0x140012937  mov     [rax-48h], r13
0x14001293b  mov     rbx, gs:188h
0x140012944  mov     rcx, [rdi+88h]
0x14001294b  cmp     rbx, [rcx+40h]
0x14001294f  jz      short loc_14001297A
0x140012951  mov     rcx, [rcx+50h]
0x140012955  add     rcx, 0D8h; FastMutex
0x14001295c  call    cs:__imp_ExAcquireFastMutex
0x140012963  nop     dword ptr [rax+rax+00h]
0x140012968  mov     rax, [rdi+88h]
0x14001296f  mov     [rax+40h], rbx
0x140012973  mov     edx, [rsp+68h+arg_10]
0x14001297a  mov     rax, [rdi+88h]
0x140012981  inc     dword ptr [rax+48h]
0x140012984  lea     rax, [rdi+0A0h]
0x14001298b  mov     rsi, [rax]
0x14001298e  cmp     rsi, rax
0x140012991  jz      loc_140012A32
0x140012997  movzx   ecx, word ptr [rsi+60h]
0x14001299b  add     ecx, 14h
0x14001299e  mov     [rsp+68h+arg_0], ecx
0x1400129a2  lea     eax, [rcx+rdx]
0x1400129a5  add     [r14], eax
0x1400129a8  lea     eax, [rcx+rdx]
0x1400129ab  cmp     eax, [r15]
0x1400129ae  jbe     short loc_1400129B8
0x1400129b0  mov     r12d, 80000005h
0x1400129b6  jmp     short loc_140012A32
0x1400129b8  inc     dword ptr [r14+4]
0x1400129bc  lea     ebx, [rcx+7]
0x1400129bf  and     ebx, 0FFFFFFF8h
0x1400129c2  mov     [r13+0], ebx
0x1400129c6  mov     rax, [rsi-8]
0x1400129ca  mov     rcx, [rax+88h]
0x1400129d1  mov     rax, [rcx+10h]
0x1400129d5  mov     rcx, [rax+0B8h]
0x1400129dc  mov     [r13+8], rcx
0x1400129e0  movzx   eax, word ptr [rsi+60h]
0x1400129e4  shr     eax, 1
0x1400129e6  mov     [r13+10h], eax
0x1400129ea  movzx   r8d, word ptr [rsi+60h]; Size
0x1400129ef  lea     rcx, [r13+14h]; void *
0x1400129f3  mov     rdx, [rsi+68h]; Src
0x1400129f7  call    memmove
0x1400129fc  mov     eax, [rsp+68h+arg_10]
0x140012a03  add     eax, [rsp+68h+arg_0]
0x140012a07  sub     [r15], eax
0x140012a0a  mov     eax, [r13+0]
0x140012a0e  add     r13, rax
0x140012a11  mov     [rsp+68h+var_48], r13
0x140012a16  mov     edx, ebx
0x140012a18  sub     edx, [rsp+68h+arg_0]
0x140012a1c  mov     [rsp+68h+arg_10], edx
0x140012a23  mov     rsi, [rsi]
0x140012a26  lea     rax, [rdi+0A0h]
0x140012a2d  jmp     loc_14001298E
0x140012a32  mov     rcx, [rdi+88h]
0x140012a39  dec     dword ptr [rcx+48h]
0x140012a3c  mov     rcx, [rdi+88h]
0x140012a43  cmp     dword ptr [rcx+48h], 0
0x140012a47  jnz     short loc_140012A6F
0x140012a49  mov     qword ptr [rcx+40h], 0
0x140012a51  mov     rcx, [rdi+88h]
0x140012a58  mov     rcx, [rcx+50h]
0x140012a5c  add     rcx, 0D8h; FastMutex
0x140012a63  call    cs:__imp_ExReleaseFastMutex
0x140012a6a  nop     dword ptr [rax+rax+00h]
0x140012a6f  mov     eax, r12d
0x140012a72  add     rsp, 30h
0x140012a76  pop     r15
0x140012a78  pop     r14
0x140012a7a  pop     r13
0x140012a7c  pop     r12
0x140012a7e  pop     rdi
0x140012a7f  pop     rsi
0x140012a80  pop     rbx
0x140012a81  retn
0x14001d981  push    rbp
0x14001d983  sub     rsp, 20h
0x14001d987  mov     rbp, rdx
0x14001d98a  mov     rdx, [rbp+78h]
0x14001d98e  mov     rax, [rdx+88h]
0x14001d995  mov     ecx, [rax+48h]
0x14001d998  dec     ecx
0x14001d99a  mov     [rax+48h], ecx
0x14001d99d  mov     rax, [rdx+88h]
0x14001d9a4  cmp     dword ptr [rax+48h], 0
0x14001d9a8  jnz     short loc_14001D9D1
0x14001d9aa  mov     qword ptr [rax+40h], 0
0x14001d9b2  mov     rax, [rdx+88h]
0x14001d9b9  mov     rcx, [rax+50h]
0x14001d9bd  add     rcx, 0D8h; FastMutex
0x14001d9c4  call    cs:__imp_ExReleaseFastMutex
0x14001d9cb  nop     dword ptr [rax+rax+00h]
0x14001d9d0  nop
0x14001d9d1  add     rsp, 20h
0x14001d9d5  pop     rbp
0x14001d9d6  retn
```
