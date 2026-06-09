# UdfOpenObjectByFileId

- ea: `0x14002e4fc`
- end: `0x14002e996`
- name: `UdfOpenObjectByFileId`
- size: `1178`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x140042c40`

## callees

- `0x140009014`
- `0x140009730`
- `0x140009b64`
- `0x14000b128`
- `0x14000c0ec`
- `0x14001c080`
- `0x14002e4fc`
- `0x14003dec8`
- `0x14003f360`
- `0x14004ce50`
- `0x14004cf74`
- `0x14004fc70`
- `0x140050ee0`
- `0x1400537b0`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002e5dd`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002e7ac`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002e827`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002e5dd`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002e7ac`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002e827`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002e7d9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002e7f5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002e854`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002e86d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002e91d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005b254`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002e7d9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002e7f5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002e854`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002e86d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002e91d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005b254`

## pseudocode

```c
__int64 __fastcall UdfOpenObjectByFileId(__int64 a1, __int64 a2, __int64 a3, unsigned int **a4, ULONG a5)
{
  __int64 v9; // rbx
  int v10; // esi
  BOOL v11; // r14d
  _QWORD *v12; // rax
  __int64 v13; // r8
  unsigned int *v14; // r14
  __int64 v15; // rcx
  _QWORD *v16; // rbx
  int v17; // edx
  signed int v18; // r9d
  __int64 *v19; // r10
  char v20; // [rsp+99h] [rbp-E7h]
  char v21; // [rsp+9Ah] [rbp-E6h] BYREF
  char v22; // [rsp+9Bh] [rbp-E5h] BYREF
  int v23; // [rsp+9Ch] [rbp-E4h]
  unsigned int v24; // [rsp+A0h] [rbp-E0h]
  _QWORD *v25; // [rsp+A8h] [rbp-D8h]
  int v26; // [rsp+B0h] [rbp-D0h]
  _QWORD *v27; // [rsp+B8h] [rbp-C8h]
  _QWORD *v28; // [rsp+C0h] [rbp-C0h]
  PFAST_MUTEX FastMutex; // [rsp+C8h] [rbp-B8h]
  __int64 v30; // [rsp+D0h] [rbp-B0h]
  PFAST_MUTEX v31; // [rsp+D8h] [rbp-A8h]
  _QWORD v32[19]; // [rsp+E8h] [rbp-98h] BYREF

  v22 = 0;
  memset(v32, 0, 0x60u);
  if ( (*(_DWORD *)(a3 + 48) & 0x90) == 0 )
    return 3221225506LL;
  v9 = **(_QWORD **)(*(_QWORD *)(a2 + 48) + 96LL);
  if ( (v9 & 0x7FFF000000000000LL) != 0 )
    return 3221225485LL;
  v30 = a3;
  v10 = -1073741790;
  v23 = -1073741790;
  v28 = 0;
  v11 = v9 >= 0;
  v24 = v11 + 3;
  v26 = v11 + 3;
  FastMutex = (PFAST_MUTEX)(a3 + 1648);
  v31 = (PFAST_MUTEX)(a3 + 1648);
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a3 + 1648));
  v25 = (_QWORD *)(a3 + 1704);
  *(_QWORD *)(a3 + 1704) = KeGetCurrentThread();
  v20 = 1;
  v12 = UdfCreateScb(a1, v9, (unsigned __int16)v11 + 2355, 0, &v22);
  v14 = (unsigned int *)v12;
  v28 = v12;
  if ( v22 )
  {
    v15 = (__int64)(v12 + 17);
    v27 = v12 + 17;
    v16 = (_QWORD *)(a3 + 1704);
  }
  else
  {
    if ( (*(_DWORD *)(a1 + 28) & 4) == 0 )
      UdfRaiseStatusEx(a1, 3221225688LL, 0);
    v27 = v12 + 17;
    v25 = v12 + 17;
    *(_QWORD *)(v12[17] + 16LL) = v12;
    UdfInitializeIcbContextFromScb(a1, (__int64)v32, (__int64)v12);
    UdfLookupActiveIcb(a1, v32, v14[44]);
    UdfInitializeScbFromIcbContext(a1, (__int64)v14, v32, 0);
    UdfCleanupIcbContext(a1, v32);
    v15 = (__int64)(v14 + 34);
    v16 = (_QWORD *)(v30 + 1704);
    v25 = (_QWORD *)(v30 + 1704);
  }
  if ( (v14[53] & 0x18) == 0 )
  {
    v17 = *(_DWORD *)(a2 + 16);
    if ( (v14[55] & 0x10) != 0 )
    {
      if ( (v17 & 0x40) != 0 )
      {
        v10 = -1073741638;
        goto LABEL_12;
      }
    }
    else if ( (v17 & 1) != 0 )
    {
      v10 = -1073741565;
      goto LABEL_12;
    }
    LOBYTE(v13) = 1;
    if ( (unsigned __int8)UdfAcquireResource(a1, *(_QWORD *)(*(_QWORD *)v15 + 80LL) + 8LL, v13, 0) )
    {
      *v16 = 0;
      ExReleaseFastMutexUnsafe(FastMutex);
      v20 = 0;
    }
    else
    {
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a3 + 1584));
      *(_QWORD *)(a3 + 1640) = KeGetCurrentThread();
      ++v14[51];
      *(_QWORD *)(a3 + 1640) = 0;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a3 + 1584));
      *v25 = 0;
      ExReleaseFastMutexUnsafe(FastMutex);
      v20 = 0;
      UdfAcquireResource(a1, *(_QWORD *)(*v27 + 80LL) + 8LL, 0, 0);
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a3 + 1584));
      *(_QWORD *)(a3 + 1640) = KeGetCurrentThread();
      --v14[51];
      *(_QWORD *)(a3 + 1640) = 0;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a3 + 1584));
    }
    *a4 = v14;
    if ( (v14[53] & 0x200) != 0 )
    {
      v10 = -1073741738;
      v23 = -1073741738;
    }
    else if ( !(unsigned __int8)UdfIllegalScbAccess(a1, v24, *(unsigned int *)(*(_QWORD *)(a2 + 8) + 16LL)) )
    {
      v10 = UdfCompleteScbOpen(a1, a2, a3, v19, 0, 0, v18, 1, a5, 0);
      v23 = v10;
    }
    goto LABEL_25;
  }
  v10 = -1073741811;
LABEL_12:
  v23 = v10;
LABEL_25:
  if ( v20 )
  {
    *(_QWORD *)(a3 + 1704) = 0;
    ExReleaseFastMutexUnsafe(v31);
  }
  if ( (v14[53] & 1) != 0 )
  {
    if ( v10 < 0 && !v22 )
    {
      v21 = 0;
      UdfTeardownStructures(a1, (_DWORD)v14, 0, 0, (__int64)&v21);
      if ( v21 )
        *a4 = 0;
    }
  }
  else
  {
    UdfDeleteScb(v15, (ULONG_PTR)v14);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14002e4fc  mov     rax, rsp
0x14002e4ff  mov     [rax+20h], r9
0x14002e503  mov     [rax+18h], r8
0x14002e507  mov     [rax+10h], rdx
0x14002e50b  mov     [rax+8], rcx
0x14002e50f  push    rbx
0x14002e510  push    rsi
0x14002e511  push    rdi
0x14002e512  push    r12
0x14002e514  push    r13
0x14002e516  push    r14
0x14002e518  push    r15
0x14002e51a  sub     rsp, 100h
0x14002e521  mov     r13, r8
0x14002e524  mov     r12, rdx
0x14002e527  mov     r15, rcx
0x14002e52a  xor     edi, edi
0x14002e52c  mov     [rsp+138h+var_E5], dil
0x14002e531  xor     edx, edx; Val
0x14002e533  lea     r8d, [rdi+60h]; Size
0x14002e537  lea     rcx, [rax-98h]; void *
0x14002e53e  call    memset
0x14002e543  mov     eax, [r13+30h]
0x14002e547  test    al, 90h
0x14002e549  jnz     short loc_14002E564
0x14002e54b  mov     eax, 0C0000022h
0x14002e550  add     rsp, 100h
0x14002e557  pop     r15
0x14002e559  pop     r14
0x14002e55b  pop     r13
0x14002e55d  pop     r12
0x14002e55f  pop     rdi
0x14002e560  pop     rsi
0x14002e561  pop     rbx
0x14002e562  retn
0x14002e564  mov     rax, [r12+30h]
0x14002e569  mov     rbx, [rax+60h]
0x14002e56d  mov     rbx, [rbx]
0x14002e570  mov     rax, rbx
0x14002e573  shr     rax, 20h
0x14002e577  test    eax, 7FFF0000h
0x14002e57c  jz      short loc_14002E585
0x14002e57e  mov     eax, 0C000000Dh
0x14002e583  jmp     short loc_14002E550
0x14002e585  mov     [rsp+138h+var_B0], r13
0x14002e58d  mov     esi, 0C0000022h
0x14002e592  mov     [rsp+138h+var_E4], esi
0x14002e596  mov     [rsp+138h+var_E8], dil
0x14002e59b  mov     [rsp+138h+var_C0], rdi
0x14002e5a0  shr     eax, 1Fh
0x14002e5a3  xor     al, 1
0x14002e5a5  movzx   r14d, al
0x14002e5a9  lea     eax, [r14+3]
0x14002e5ad  mov     [rsp+138h+var_E0], eax
0x14002e5b1  mov     [rsp+138h+var_D0], eax
0x14002e5b5  mov     eax, 933h
0x14002e5ba  add     r14w, ax
0x14002e5be  mov     [rsp+138h+var_E7], dil
0x14002e5c3  lea     rax, [r13+670h]
0x14002e5ca  mov     [rsp+138h+FastMutex], rax
0x14002e5d2  mov     [rsp+138h+var_A8], rax
0x14002e5da  mov     rcx, rax; FastMutex
0x14002e5dd  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14002e5e4  nop     dword ptr [rax+rax+00h]
0x14002e5e9  mov     rax, gs:188h
0x14002e5f2  lea     rcx, [r13+6A8h]
0x14002e5f9  mov     [rsp+138h+var_D8], rcx
0x14002e5fe  mov     [rcx], rax
0x14002e601  mov     [rsp+138h+var_E7], 1
0x14002e606  lea     rax, [rsp+138h+var_E5]
0x14002e60b  mov     qword ptr [rsp+138h+var_118], rax
0x14002e610  xor     r9d, r9d
0x14002e613  movzx   r8d, r14w
0x14002e617  mov     rdx, rbx
0x14002e61a  mov     rcx, r15
0x14002e61d  call    UdfCreateScb
0x14002e622  mov     r14, rax
0x14002e625  mov     [rsp+138h+var_C0], rax
0x14002e62a  cmp     [rsp+138h+var_E5], dil
0x14002e62f  jnz     loc_14002E72A
0x14002e635  mov     ecx, [r15+1Ch]
0x14002e639  test    cl, 4
0x14002e63c  jnz     short loc_14002E64E
0x14002e63e  xor     r8d, r8d
0x14002e641  mov     edx, 0C00000D8h
0x14002e646  mov     rcx, r15
0x14002e649  call    UdfRaiseStatusEx
0x14002e64e  add     rax, 88h
0x14002e654  mov     [rsp+138h+var_C8], rax
0x14002e659  mov     [rsp+138h+var_D8], rax
0x14002e65e  mov     rax, [rax]
0x14002e661  mov     [rax+10h], r14
0x14002e665  mov     r8, r14
0x14002e668  lea     rdx, [rsp+138h+var_98]
0x14002e670  mov     rcx, r15
0x14002e673  call    UdfInitializeIcbContextFromScb
0x14002e678  mov     [rsp+138h+var_E8], 1
0x14002e67d  mov     r8d, [r14+0B0h]
0x14002e684  lea     rdx, [rsp+138h+var_98]
0x14002e68c  mov     rcx, r15
0x14002e68f  call    UdfLookupActiveIcb
0x14002e694  xor     r9d, r9d
0x14002e697  lea     r8, [rsp+138h+var_98]
0x14002e69f  mov     rdx, r14
0x14002e6a2  mov     rcx, r15
0x14002e6a5  call    UdfInitializeScbFromIcbContext
0x14002e6aa  lea     rdx, [rsp+138h+var_98]
0x14002e6b2  mov     rcx, r15
0x14002e6b5  call    UdfCleanupIcbContext
0x14002e6ba  mov     bl, dil
0x14002e6bd  mov     [rsp+138h+var_E8], bl
0x14002e6c1  lea     rcx, [r14+88h]
0x14002e6c8  jmp     short loc_14002E708
0x14002e6ca  mov     esi, 0C000000Dh
0x14002e6cf  mov     [rsp+138h+var_E4], esi
0x14002e6d3  xor     edi, edi
0x14002e6d5  mov     r13, [rsp+138h+arg_10]
0x14002e6dd  mov     r12, [rsp+138h+arg_8]
0x14002e6e5  mov     r15, [rsp+138h+arg_0]
0x14002e6ed  mov     bl, [rsp+138h+var_E8]
0x14002e6f1  mov     r14, [rsp+138h+var_C0]
0x14002e6f6  mov     eax, [rsp+138h+var_D0]
0x14002e6fa  mov     [rsp+138h+var_E0], eax
0x14002e6fe  mov     rcx, [rsp+138h+var_D8]
0x14002e703  mov     [rsp+138h+var_C8], rcx
0x14002e708  cmp     esi, 0C000000Dh
0x14002e70e  jz      loc_14002E907
0x14002e714  mov     rbx, [rsp+138h+var_B0]
0x14002e71c  add     rbx, 6A8h
0x14002e723  mov     [rsp+138h+var_D8], rbx
0x14002e728  jmp     short loc_14002E73D
0x14002e72a  lea     rcx, [rax+88h]
0x14002e731  mov     [rsp+138h+var_C8], rcx
0x14002e736  lea     rbx, [r13+6A8h]
0x14002e73d  mov     eax, [r14+0D4h]
0x14002e744  test    al, 18h
0x14002e746  jz      short loc_14002E759
0x14002e748  mov     esi, 0C000000Dh
0x14002e74d  mov     [rsp+138h+var_E4], esi
0x14002e751  mov     bl, dil
0x14002e754  jmp     loc_14002E903
0x14002e759  mov     edx, [r12+10h]
0x14002e75e  mov     eax, [r14+0DCh]
0x14002e765  test    al, 10h
0x14002e767  jz      short loc_14002E775
0x14002e769  test    dl, 40h
0x14002e76c  jz      short loc_14002E781
0x14002e76e  mov     esi, 0C00000BAh
0x14002e773  jmp     short loc_14002E74D
0x14002e775  test    dl, 1
0x14002e778  jz      short loc_14002E781
0x14002e77a  mov     esi, 0C0000103h
0x14002e77f  jmp     short loc_14002E74D
0x14002e781  mov     rax, [rcx]
0x14002e784  mov     rdx, [rax+50h]
0x14002e788  add     rdx, 8
0x14002e78c  xor     r9d, r9d
0x14002e78f  mov     r8b, 1
0x14002e792  mov     rcx, r15
0x14002e795  call    UdfAcquireResource
0x14002e79a  test    al, al
0x14002e79c  jnz     loc_14002E862
0x14002e7a2  lea     rbx, [r13+630h]
0x14002e7a9  mov     rcx, rbx; FastMutex
0x14002e7ac  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14002e7b3  nop     dword ptr [rax+rax+00h]
0x14002e7b8  mov     rax, gs:188h
0x14002e7c1  mov     [r13+668h], rax
0x14002e7c8  inc     dword ptr [r14+0CCh]
0x14002e7cf  mov     [r13+668h], rdi
0x14002e7d6  mov     rcx, rbx; FastMutex
0x14002e7d9  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002e7e0  nop     dword ptr [rax+rax+00h]
0x14002e7e5  mov     rax, [rsp+138h+var_D8]
0x14002e7ea  mov     [rax], rdi
0x14002e7ed  mov     rcx, [rsp+138h+FastMutex]; FastMutex
0x14002e7f5  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002e7fc  nop     dword ptr [rax+rax+00h]
0x14002e801  mov     [rsp+138h+var_E7], dil
0x14002e806  mov     rax, [rsp+138h+var_C8]
0x14002e80b  mov     rax, [rax]
0x14002e80e  mov     rdx, [rax+50h]
0x14002e812  add     rdx, 8
0x14002e816  xor     r9d, r9d
0x14002e819  xor     r8d, r8d
0x14002e81c  mov     rcx, r15
0x14002e81f  call    UdfAcquireResource
0x14002e824  mov     rcx, rbx; FastMutex
0x14002e827  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14002e82e  nop     dword ptr [rax+rax+00h]
0x14002e833  mov     rax, gs:188h
0x14002e83c  mov     [r13+668h], rax
0x14002e843  dec     dword ptr [r14+0CCh]
0x14002e84a  mov     [r13+668h], rdi
0x14002e851  mov     rcx, rbx; FastMutex
0x14002e854  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002e85b  nop     dword ptr [rax+rax+00h]
0x14002e860  jmp     short loc_14002E87E
0x14002e862  mov     [rbx], rdi
0x14002e865  mov     rcx, [rsp+138h+FastMutex]; FastMutex
0x14002e86d  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002e874  nop     dword ptr [rax+rax+00h]
0x14002e879  mov     [rsp+138h+var_E7], dil
0x14002e87e  mov     r10, [rsp+138h+arg_18]
0x14002e886  mov     [r10], r14
0x14002e889  mov     eax, [r14+0D4h]
0x14002e890  mov     bl, dil
0x14002e893  bt      eax, 9
0x14002e897  jnb     short loc_14002E8A4
0x14002e899  mov     esi, 0C0000056h
0x14002e89e  mov     [rsp+138h+var_E4], esi
0x14002e8a2  jmp     short loc_14002E903
0x14002e8a4  mov     [rsp+138h+var_E8], bl
0x14002e8a8  mov     r8, [r12+8]
0x14002e8ad  mov     r8d, [r8+10h]
0x14002e8b1  mov     r9d, [rsp+138h+var_E0]
0x14002e8b6  mov     edx, r9d
0x14002e8b9  mov     rcx, r15
0x14002e8bc  call    UdfIllegalScbAccess
0x14002e8c1  test    al, al
0x14002e8c3  jnz     short loc_14002E907
0x14002e8c5  mov     [rsp+138h+var_F0], dil; char
0x14002e8ca  mov     eax, [rsp+138h+arg_20]
0x14002e8d1  mov     [rsp+138h+var_F8], eax; ULONG
0x14002e8d5  mov     [rsp+138h+var_100], 1; int
0x14002e8dd  mov     [rsp+138h+var_108], r9d; ULONG
0x14002e8e2  mov     [rsp+138h+var_110], rdi; __int64
0x14002e8e7  mov     qword ptr [rsp+138h+var_118], rdi; int
0x14002e8ec  mov     r9, r10; int
0x14002e8ef  mov     r8, r13; int
0x14002e8f2  mov     rdx, r12; int
0x14002e8f5  mov     rcx, r15; int
0x14002e8f8  call    UdfCompleteScbOpen
0x14002e8fd  mov     esi, eax
0x14002e8ff  mov     [rsp+138h+var_E4], eax
0x14002e903  mov     [rsp+138h+var_E8], bl
0x14002e907  cmp     [rsp+138h+var_E7], dil
0x14002e90c  jz      short loc_14002E929
0x14002e90e  mov     [r13+6A8h], rdi
0x14002e915  mov     rcx, [rsp+138h+var_A8]; FastMutex
0x14002e91d  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002e924  nop     dword ptr [rax+rax+00h]
0x14002e929  test    bl, bl
0x14002e92b  jz      short loc_14002E93D
0x14002e92d  lea     rdx, [rsp+138h+var_98]
0x14002e935  mov     rcx, r15
0x14002e938  call    UdfCleanupIcbContext
0x14002e93d  mov     eax, [r14+0D4h]
0x14002e944  test    al, 1
0x14002e946  jnz     short loc_14002E952
0x14002e948  mov     rdx, r14
0x14002e94b  call    UdfDeleteScb
0x14002e950  jmp     short loc_14002E98F
0x14002e952  test    esi, esi
0x14002e954  jns     short loc_14002E98F
0x14002e956  cmp     [rsp+138h+var_E5], dil
0x14002e95b  jnz     short loc_14002E98F
0x14002e95d  mov     [rsp+138h+var_E6], dil
0x14002e962  lea     rax, [rsp+138h+var_E6]
0x14002e967  mov     qword ptr [rsp+138h+var_118], rax
0x14002e96c  xor     r9d, r9d
0x14002e96f  xor     r8d, r8d
0x14002e972  mov     rdx, r14
0x14002e975  mov     rcx, r15
0x14002e978  call    UdfTeardownStructures
0x14002e97d  cmp     [rsp+138h+var_E6], dil
0x14002e982  jz      short loc_14002E98F
0x14002e984  mov     rax, [rsp+138h+arg_18]
0x14002e98c  mov     [rax], rdi
0x14002e98f  mov     eax, esi
0x14002e991  jmp     loc_14002E550
0x14005b208  push    rbp
0x14005b20a  sub     rsp, 50h
0x14005b20e  mov     rbp, rdx
0x14005b211  mov     rdx, rcx
0x14005b214  mov     rcx, [rbp+140h]
0x14005b21b  call    UdfExceptionFilter
0x14005b220  nop
0x14005b221  add     rsp, 50h
0x14005b225  pop     rbp
0x14005b226  retn
0x14005b228  push    rbx
0x14005b22a  push    rbp
0x14005b22b  sub     rsp, 58h
0x14005b22f  mov     rbp, rdx
0x14005b232  movzx   ebx, cl
0x14005b235  cmp     byte ptr [rbp+51h], 0
0x14005b239  jz      short loc_14005B261
0x14005b23b  mov     rcx, [rbp+150h]
0x14005b242  mov     qword ptr [rcx+6A8h], 0
0x14005b24d  add     rcx, 670h; FastMutex
0x14005b254  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14005b25b  nop     dword ptr [rax+rax+00h]
0x14005b260  nop
0x14005b261  cmp     byte ptr [rbp+50h], 0
0x14005b265  jz      short loc_14005B27B
0x14005b267  lea     rdx, [rbp+0A0h]
0x14005b26e  mov     rcx, [rbp+140h]
0x14005b275  call    UdfCleanupIcbContext
0x14005b27a  nop
  ... truncated ...
```
