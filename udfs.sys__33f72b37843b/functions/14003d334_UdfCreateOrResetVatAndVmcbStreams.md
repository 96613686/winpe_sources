# UdfCreateOrResetVatAndVmcbStreams

- ea: `0x14003d334`
- end: `0x14003d65a`
- name: `UdfCreateOrResetVatAndVmcbStreams`
- size: `806`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x14004e020`

## callees

- `0x14001c080`
- `0x14002fbd8`
- `0x14003d334`
- `0x14003d660`
- `0x14003e368`
- `0x14003f360`
- `0x14004f8ac`
- `0x14004fc70`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14003d551`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003d551`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003d3e1`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003d426`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003d3e1`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003d426`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003d49a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003d4b5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140059be2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003d49a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003d4b5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140059be2`
- `ntoskrnl!CcSetFileSizes` at `0x14003d64c`
- `ntoskrnl!CcSetFileSizes` at `0x14003d64c`
- `ntoskrnl!CcPurgeCacheSection` at `0x14003d39e`
- `ntoskrnl!CcPurgeCacheSection` at `0x14003d3c4`
- `ntoskrnl!CcPurgeCacheSection` at `0x14003d39e`
- `ntoskrnl!CcPurgeCacheSection` at `0x14003d3c4`

## pseudocode

```c
void __fastcall UdfCreateOrResetVatAndVmcbStreams(__int64 a1, __int64 a2, int a3, __int64 a4, unsigned __int16 a5)
{
  __int64 v9; // rax
  __int64 v10; // rax
  int v11; // ebx
  __int64 v12; // rcx
  _QWORD v13[17]; // [rsp+40h] [rbp-88h] BYREF

  memset(v13, 0, 0x60u);
  if ( *(_QWORD *)(a2 + 344) )
  {
    UdfResetVmcb(a2 + 984);
    CcPurgeCacheSection(*(PSECTION_OBJECT_POINTERS *)(*(_QWORD *)(*(_QWORD *)(a2 + 272) + 504LL) + 40LL), 0, 0, 0);
    CcPurgeCacheSection(*(PSECTION_OBJECT_POINTERS *)(*(_QWORD *)(*(_QWORD *)(a2 + 344) + 504LL) + 40LL), 0, 0, 0);
  }
  else
  {
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a2 + 1648));
    *(_QWORD *)(a2 + 1704) = KeGetCurrentThread();
    *(_QWORD *)(a2 + 344) = UdfCreateScb(a1, 0, 0x933u, 0, 0);
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a2 + 1584));
    *(_QWORD *)(a2 + 1640) = KeGetCurrentThread();
    ++*(_DWORD *)(*(_QWORD *)(a2 + 344) + 204LL);
    ++*(_DWORD *)(*(_QWORD *)(a2 + 344) + 208LL);
    v9 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 344) + 136LL) + 8LL);
    ++*(_DWORD *)(v9 + 256);
    v10 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 344) + 136LL) + 8LL);
    ++*(_DWORD *)(v10 + 260);
    *(_QWORD *)(a2 + 1640) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 + 1584));
    *(_QWORD *)(a2 + 1704) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 + 1648));
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 344) + 136LL) + 76LL) |= 1u;
    *(_QWORD *)(*(_QWORD *)(a2 + 344) + 8LL) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 344) + 136LL) + 80LL) + 8LL;
    *(_QWORD *)(*(_QWORD *)(a2 + 344) + 16LL) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 344) + 136LL) + 80LL) + 112LL;
  }
  *(_DWORD *)(*(_QWORD *)(a2 + 344) + 184LL) = a3;
  *(_DWORD *)(*(_QWORD *)(a2 + 344) + 188LL) = a5;
  v11 = UdfLookupMetaVsnOfExtent(a1, a2, a5, a3, *(_DWORD *)(a2 + 68), 1);
  ExReleaseResourceLite((PERESOURCE)(a2 + 992));
  *(_QWORD *)(*(_QWORD *)(a2 + 344) + 24LL) = ~(unsigned __int64)(unsigned int)(*(_DWORD *)(a2 + 68) - 1)
                                            & ((unsigned int)(*(_DWORD *)(a2 + 68) - 1) + *(_QWORD *)(a4 + 56));
  *(_QWORD *)(*(_QWORD *)(a2 + 344) + 40LL) = *(_QWORD *)(a4 + 56);
  *(_QWORD *)(*(_QWORD *)(a2 + 344) + 32LL) = *(_QWORD *)(*(_QWORD *)(a2 + 344) + 40LL);
  memset(v13, 0, 0x60u);
  v13[2] = a4;
  LOWORD(v13[4]) = a5;
  HIDWORD(v13[4]) = a3;
  LODWORD(v13[5]) = -*(_DWORD *)(a2 + 68) & (2 * *(_DWORD *)(a2 + 68) - 1);
  HIDWORD(v13[5]) = v11;
  UdfInitializeAllocations(a1, *(_QWORD *)(a2 + 344), (__int64)v13, 0);
  UdfCleanupIcbContext(a1, v13);
  v12 = *(_QWORD *)(a2 + 344);
  if ( (*(_DWORD *)(v12 + 212) & 1) != 0 )
  {
    CcSetFileSizes(*(PFILE_OBJECT *)(v12 + 504), (PCC_FILE_SIZES)(v12 + 24));
  }
  else
  {
    UdfCreateInternalStream(a1, a2, *(_QWORD *)(a2 + 344), &qword_140025100);
    *(_DWORD *)(*(_QWORD *)(a2 + 344) + 212LL) |= 1u;
  }
}

```

## disassembly

```asm
0x14003d334  mov     [rsp+arg_10], rbx
0x14003d339  mov     [rsp+arg_8], rdx
0x14003d33e  mov     [rsp+arg_0], rcx
0x14003d343  push    rsi
0x14003d344  push    rdi
0x14003d345  push    r12
0x14003d347  push    r14
0x14003d349  push    r15
0x14003d34b  sub     rsp, 0A0h
0x14003d352  mov     r15, r9
0x14003d355  mov     r12d, r8d
0x14003d358  mov     rsi, rdx
0x14003d35b  mov     r14, rcx
0x14003d35e  xor     edx, edx; Val
0x14003d360  lea     r8d, [rdx+60h]; Size
0x14003d364  lea     rcx, [rsp+0C8h+var_88]; void *
0x14003d369  call    memset
0x14003d36e  cmp     qword ptr [rsi+158h], 0
0x14003d376  jz      short loc_14003D3D5
0x14003d378  lea     rcx, [rsi+3D8h]
0x14003d37f  call    UdfResetVmcb
0x14003d384  mov     rax, [rsi+110h]
0x14003d38b  mov     rcx, [rax+1F8h]
0x14003d392  xor     r9d, r9d; Flags
0x14003d395  xor     r8d, r8d; Length
0x14003d398  xor     edx, edx; FileOffset
0x14003d39a  mov     rcx, [rcx+28h]; SectionObjectPointer
0x14003d39e  call    cs:__imp_CcPurgeCacheSection
0x14003d3a5  nop     dword ptr [rax+rax+00h]
0x14003d3aa  mov     rax, [rsi+158h]
0x14003d3b1  mov     rcx, [rax+1F8h]
0x14003d3b8  xor     r9d, r9d; Flags
0x14003d3bb  xor     r8d, r8d; Length
0x14003d3be  xor     edx, edx; FileOffset
0x14003d3c0  mov     rcx, [rcx+28h]; SectionObjectPointer
0x14003d3c4  call    cs:__imp_CcPurgeCacheSection
0x14003d3cb  nop     dword ptr [rax+rax+00h]
0x14003d3d0  jmp     loc_14003D507
0x14003d3d5  xor     ebx, ebx
0x14003d3d7  lea     rdi, [rsi+670h]
0x14003d3de  mov     rcx, rdi; FastMutex
0x14003d3e1  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14003d3e8  nop     dword ptr [rax+rax+00h]
0x14003d3ed  mov     rax, gs:188h
0x14003d3f6  mov     [rsi+6A8h], rax
0x14003d3fd  mov     r8d, 933h
0x14003d403  mov     [rsp+0C8h+var_A8], rbx
0x14003d408  xor     r9d, r9d
0x14003d40b  mov     edx, ebx
0x14003d40d  mov     rcx, r14
0x14003d410  call    UdfCreateScb
0x14003d415  mov     [rsi+158h], rax
0x14003d41c  lea     rbx, [rsi+630h]
0x14003d423  mov     rcx, rbx; FastMutex
0x14003d426  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14003d42d  nop     dword ptr [rax+rax+00h]
0x14003d432  mov     rax, gs:188h
0x14003d43b  mov     [rsi+668h], rax
0x14003d442  mov     rax, [rsi+158h]
0x14003d449  inc     dword ptr [rax+0CCh]
0x14003d44f  mov     rax, [rsi+158h]
0x14003d456  inc     dword ptr [rax+0D0h]
0x14003d45c  mov     rax, [rsi+158h]
0x14003d463  mov     rdx, [rax+88h]
0x14003d46a  mov     rax, [rdx+8]
0x14003d46e  inc     dword ptr [rax+100h]
0x14003d474  mov     rax, [rsi+158h]
0x14003d47b  mov     rdx, [rax+88h]
0x14003d482  mov     rax, [rdx+8]
0x14003d486  inc     dword ptr [rax+104h]
0x14003d48c  mov     qword ptr [rsi+668h], 0
0x14003d497  mov     rcx, rbx; FastMutex
0x14003d49a  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14003d4a1  nop     dword ptr [rax+rax+00h]
0x14003d4a6  nop
0x14003d4a7  mov     qword ptr [rsi+6A8h], 0
0x14003d4b2  mov     rcx, rdi; FastMutex
0x14003d4b5  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14003d4bc  nop     dword ptr [rax+rax+00h]
0x14003d4c1  mov     rax, [rsi+158h]
0x14003d4c8  mov     rcx, [rax+88h]
0x14003d4cf  or      dword ptr [rcx+4Ch], 1
0x14003d4d3  mov     rdx, [rsi+158h]
0x14003d4da  mov     rax, [rdx+88h]
0x14003d4e1  mov     rcx, [rax+50h]
0x14003d4e5  add     rcx, 8
0x14003d4e9  mov     [rdx+8], rcx
0x14003d4ed  mov     rdx, [rsi+158h]
0x14003d4f4  mov     rax, [rdx+88h]
0x14003d4fb  mov     rcx, [rax+50h]
0x14003d4ff  add     rcx, 70h ; 'p'
0x14003d503  mov     [rdx+10h], rcx
0x14003d507  mov     rax, [rsi+158h]
0x14003d50e  mov     [rax+0B8h], r12d
0x14003d515  movzx   edi, [rsp+0C8h+arg_20]
0x14003d51d  mov     rax, [rsi+158h]
0x14003d524  mov     [rax+0BCh], edi
0x14003d52a  mov     [rsp+0C8h+var_A0], 1
0x14003d52f  mov     eax, [rsi+44h]
0x14003d532  mov     dword ptr [rsp+0C8h+var_A8], eax
0x14003d536  mov     r9d, r12d
0x14003d539  movzx   r8d, di
0x14003d53d  mov     rdx, rsi
0x14003d540  mov     rcx, r14
0x14003d543  call    UdfLookupMetaVsnOfExtent
0x14003d548  mov     ebx, eax
0x14003d54a  lea     rcx, [rsi+3E0h]; Resource
0x14003d551  call    cs:__imp_ExReleaseResourceLite
0x14003d558  nop     dword ptr [rax+rax+00h]
0x14003d55d  mov     r9d, [rsi+44h]
0x14003d561  dec     r9d
0x14003d564  mov     rdx, [r15+38h]
0x14003d568  add     rdx, r9
0x14003d56b  not     r9
0x14003d56e  and     rdx, r9
0x14003d571  mov     rcx, [rsi+158h]
0x14003d578  mov     [rcx+18h], rdx
0x14003d57c  mov     rcx, [rsi+158h]
0x14003d583  mov     rax, [r15+38h]
0x14003d587  mov     [rcx+28h], rax
0x14003d58b  mov     rcx, [rsi+158h]
0x14003d592  mov     rax, [rcx+28h]
0x14003d596  mov     [rcx+20h], rax
0x14003d59a  xor     edx, edx; Val
0x14003d59c  lea     r8d, [rdx+60h]; Size
0x14003d5a0  lea     rcx, [rsp+0C8h+var_88]; void *
0x14003d5a5  call    memset
0x14003d5aa  mov     [rsp+0C8h+var_78], r15
0x14003d5af  mov     [rsp+0C8h+var_68], di
0x14003d5b4  mov     [rsp+0C8h+var_64], r12d
0x14003d5b9  mov     ecx, [rsi+44h]
0x14003d5bc  lea     eax, ds:0FFFFFFFFFFFFFFFFh[rcx*2]
0x14003d5c3  neg     ecx
0x14003d5c5  and     eax, ecx
0x14003d5c7  mov     [rsp+0C8h+var_60], eax
0x14003d5cb  mov     [rsp+0C8h+var_5C], ebx
0x14003d5cf  xor     r9d, r9d
0x14003d5d2  lea     r8, [rsp+0C8h+var_88]
0x14003d5d7  mov     rdx, [rsi+158h]
0x14003d5de  mov     rcx, r14
0x14003d5e1  call    UdfInitializeAllocations
0x14003d5e6  nop
0x14003d5e7  lea     rdx, [rsp+0C8h+var_88]
0x14003d5ec  mov     rcx, r14
0x14003d5ef  call    UdfCleanupIcbContext
0x14003d5f4  mov     rcx, [rsi+158h]
0x14003d5fb  mov     eax, [rcx+0D4h]
0x14003d601  test    al, 1
0x14003d603  jnz     short loc_14003D641
0x14003d605  lea     r9, qword_140025100
0x14003d60c  mov     r8, rcx
0x14003d60f  mov     rdx, rsi
0x14003d612  mov     rcx, r14
0x14003d615  call    UdfCreateInternalStream
0x14003d61a  mov     rax, [rsi+158h]
0x14003d621  or      dword ptr [rax+0D4h], 1
0x14003d628  mov     rbx, [rsp+0C8h+arg_10]
0x14003d630  add     rsp, 0A0h
0x14003d637  pop     r15
0x14003d639  pop     r14
0x14003d63b  pop     r12
0x14003d63d  pop     rdi
0x14003d63e  pop     rsi
0x14003d63f  retn
0x14003d641  lea     rdx, [rcx+18h]; FileSizes
0x14003d645  mov     rcx, [rcx+1F8h]; FileObject
0x14003d64c  call    cs:__imp_CcSetFileSizes
0x14003d653  nop     dword ptr [rax+rax+00h]
0x14003d658  jmp     short loc_14003D628
0x140059bc0  push    rbp
0x140059bc2  sub     rsp, 40h
0x140059bc6  mov     rbp, rdx
0x140059bc9  mov     rcx, [rbp+0D8h]
0x140059bd0  mov     qword ptr [rcx+6A8h], 0
0x140059bdb  add     rcx, 670h; FastMutex
0x140059be2  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140059be9  nop     dword ptr [rax+rax+00h]
0x140059bee  nop
0x140059bef  add     rsp, 40h
0x140059bf3  pop     rbp
0x140059bf4  retn
0x140059bf6  push    rbp
0x140059bf8  sub     rsp, 40h
0x140059bfc  mov     rbp, rdx
0x140059bff  lea     rdx, [rbp+40h]
0x140059c03  mov     rcx, [rbp+0D0h]
0x140059c0a  call    UdfCleanupIcbContext
0x140059c0f  nop
0x140059c10  add     rsp, 40h
0x140059c14  pop     rbp
0x140059c15  retn
```
