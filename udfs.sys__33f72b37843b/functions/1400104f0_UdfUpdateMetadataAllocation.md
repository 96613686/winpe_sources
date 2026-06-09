# UdfUpdateMetadataAllocation

- ea: `0x1400104f0`
- end: `0x140010912`
- name: `UdfUpdateMetadataAllocation`
- size: `1058`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x14000b2b0`
- `0x14000efc8`

## callees

- `0x1400050d8`
- `0x1400104f0`
- `0x14004ce50`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140010893`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400108b5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400108cd`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400108eb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d835`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d857`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d874`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d896`
- `ntoskrnl!ExReleaseResourceLite` at `0x140010893`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400108b5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400108cd`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400108eb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d835`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d857`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d874`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d896`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x14001076e`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x1400107c0`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x14001076e`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x1400107c0`
- `ntoskrnl!CcSetFileSizes` at `0x140010654`
- `ntoskrnl!CcSetFileSizes` at `0x1400106f9`
- `ntoskrnl!CcSetFileSizes` at `0x140010654`
- `ntoskrnl!CcSetFileSizes` at `0x1400106f9`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400105b5`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400105cc`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400105b5`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400105cc`
- `ntoskrnl!ExReleaseFastMutex` at `0x140010710`
- `ntoskrnl!ExReleaseFastMutex` at `0x140010723`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001d800`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001d817`
- `ntoskrnl!ExReleaseFastMutex` at `0x140010710`
- `ntoskrnl!ExReleaseFastMutex` at `0x140010723`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001d800`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001d817`

## pseudocode

```c
char __fastcall UdfUpdateMetadataAllocation(__int64 a1, __int64 a2, _DWORD *a3, char a4)
{
  struct _CC_FILE_SIZES **v8; // rdi
  int v9; // ecx
  unsigned __int64 v10; // r12
  unsigned int v11; // eax
  int v12; // r10d
  unsigned int v13; // eax
  int v14; // r10d
  struct _CC_FILE_SIZES *v15; // rax
  __int64 v16; // rcx
  struct _CC_FILE_SIZES *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  _OWORD *v20; // rax

  v8 = (struct _CC_FILE_SIZES **)(a2 + 320);
  if ( !a4 )
  {
    UdfAcquireResource(a1, *(_QWORD *)((*v8)[5].ValidDataLength.QuadPart + 80) + 8LL, 0, 2);
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))UdfAcquireResource)(
      a1,
      (LARGE_INTEGER)(*v8)->ValidDataLength.QuadPart,
      0,
      0);
  }
  UdfAcquireResource(a1, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 328) + 136LL) + 80LL) + 8LL, 0, 2);
  UdfAcquireResource(a1, *(_QWORD *)(*(_QWORD *)(a2 + 328) + 16LL), 0, 0);
  ExAcquireFastMutex((PFAST_MUTEX)(*v8)[2].AllocationSize.QuadPart);
  ExAcquireFastMutex(*(PFAST_MUTEX *)(*(_QWORD *)(a2 + 328) + 48LL));
  v9 = *(_DWORD *)(a2 + 72);
  v10 = (unsigned __int64)(*v8)[1].AllocationSize.QuadPart >> v9;
  (*v8)[1].FileSize.QuadPart += (unsigned __int64)(unsigned int)a3[1] << v9;
  (*v8)[1].AllocationSize.QuadPart = (*v8)[1].FileSize.QuadPart;
  (*v8)[1].ValidDataLength.QuadPart = (*v8)[1].AllocationSize.QuadPart;
  (*v8)[12].FileSize.LowPart = (unsigned __int64)(*v8)[1].AllocationSize.QuadPart >> *(_DWORD *)(a2 + 72);
  (*v8)[12].ValidDataLength.QuadPart = (*v8)[1].FileSize.QuadPart;
  (*v8)[13].FileSize.HighPart += a3[1];
  (*v8)[13].FileSize.LowPart += a3[1];
  CcSetFileSizes((PFILE_OBJECT)(*v8)[21].AllocationSize.QuadPart, *v8 + 1);
  *(_QWORD *)(*(_QWORD *)(a2 + 328) + 32LL) += (unsigned __int64)(unsigned int)a3[1] << *(_DWORD *)(a2 + 72);
  *(_QWORD *)(*(_QWORD *)(a2 + 328) + 24LL) = *(_QWORD *)(*(_QWORD *)(a2 + 328) + 32LL);
  *(_QWORD *)(*(_QWORD *)(a2 + 328) + 40LL) = *(_QWORD *)(*(_QWORD *)(a2 + 328) + 24LL);
  *(_DWORD *)(*(_QWORD *)(a2 + 328) + 296LL) = *(_QWORD *)(*(_QWORD *)(a2 + 328) + 24LL) >> *(_DWORD *)(a2 + 72);
  *(_QWORD *)(*(_QWORD *)(a2 + 328) + 304LL) = *(_QWORD *)(*(_QWORD *)(a2 + 328) + 32LL);
  *(_DWORD *)(*(_QWORD *)(a2 + 328) + 324LL) += a3[1];
  *(_DWORD *)(*(_QWORD *)(a2 + 328) + 320LL) += a3[1];
  if ( (*(_DWORD *)(a2 + 48) & 0x8000000) != 0 )
    CcSetFileSizes(*(PFILE_OBJECT *)(*(_QWORD *)(a2 + 328) + 504LL), (PCC_FILE_SIZES)(*(_QWORD *)(a2 + 328) + 24LL));
  ExReleaseFastMutex(*(PFAST_MUTEX *)(*(_QWORD *)(a2 + 328) + 48LL));
  ExReleaseFastMutex((PFAST_MUTEX)(*v8)[2].AllocationSize.QuadPart);
  v11 = 0;
  if ( (*(_DWORD *)(a2 + 48) & 0x20000000) == 0 )
    v11 = *a3 + *(_DWORD *)(*(_QWORD *)(a1 + 16) + 656LL);
  FsRtlAddLargeMcbEntry(
    (PLARGE_MCB)((char *)*v8 + ((*(_DWORD *)(a2 + 48) & 0x20000000) != 0 ? 264LL : 232LL)),
    (unsigned int)v10,
    v11,
    (unsigned int)a3[1]);
  v12 = *(_DWORD *)(a2 + 48);
  if ( (v12 & 0x8000000) != 0 )
  {
    v13 = 0;
    v14 = v12 & 0x20000000;
    if ( !v14 )
      v13 = a3[3] + *(_DWORD *)(*(_QWORD *)(a1 + 16) + 656LL);
    FsRtlAddLargeMcbEntry(
      (PLARGE_MCB)(*(_QWORD *)(a2 + 328) + (v14 != 0 ? 264LL : 232LL)),
      (unsigned int)v10,
      v13,
      (unsigned int)a3[4]);
  }
  UdfUpdateAdsFromScb(
    a1,
    *v8,
    (unsigned int)v10,
    (unsigned __int64)(*v8)[1].AllocationSize.QuadPart >> *(_DWORD *)(a2 + 72));
  if ( !_bittest((const signed __int32 *)(a2 + 48), 0x1Bu) )
  {
    v15 = *v8;
    v16 = *(_QWORD *)(a2 + 328);
    *(_OWORD *)(v16 + 232) = *(_OWORD *)&(*v8)[9].ValidDataLength.LowPart;
    *(_OWORD *)(v16 + 248) = *(_OWORD *)&v15[10].FileSize.LowPart;
    v17 = *v8;
    v18 = *(_QWORD *)(a2 + 328);
    *(_OWORD *)(v18 + 264) = *(_OWORD *)&(*v8)[11].AllocationSize.LowPart;
    *(_OWORD *)(v18 + 280) = *(_OWORD *)&v17[11].ValidDataLength.LowPart;
  }
  UdfUpdateAdsFromScb(
    a1,
    *(_QWORD *)(a2 + 328),
    (unsigned int)v10,
    *(_QWORD *)(*(_QWORD *)(a2 + 328) + 24LL) >> *(_DWORD *)(a2 + 72));
  if ( (*(_DWORD *)(a2 + 48) & 0x8000000) == 0 )
  {
    v19 = *(_QWORD *)(a2 + 328);
    *(_OWORD *)(v19 + 232) = 0;
    *(_OWORD *)(v19 + 248) = 0;
    v20 = (_OWORD *)(*(_QWORD *)(a2 + 328) + 264LL);
    *v20 = 0;
    v20[1] = 0;
  }
  ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(a2 + 328) + 16LL));
  ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 328) + 136LL) + 80LL) + 8LL));
  if ( !a4 )
  {
    ExReleaseResourceLite((PERESOURCE)(*v8)->ValidDataLength.QuadPart);
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)((*v8)[5].ValidDataLength.QuadPart + 80) + 8LL));
  }
  return 1;
}

```

## disassembly

```asm
0x1400104f0  mov     rax, rsp
0x1400104f3  mov     [rax+8], rbx
0x1400104f7  mov     [rax+18h], rsi
0x1400104fb  mov     [rax+20h], r9b
0x1400104ff  mov     [rax+10h], rdx
0x140010503  push    rdi
0x140010504  push    r12
0x140010506  push    r13
0x140010508  push    r14
0x14001050a  push    r15
0x14001050c  sub     rsp, 30h
0x140010510  mov     r15b, r9b
0x140010513  mov     r14, r8
0x140010516  mov     rbx, rdx
0x140010519  mov     rsi, rcx
0x14001051c  xor     r13d, r13d
0x14001051f  mov     [rax-37h], r13b
0x140010523  mov     [rax-38h], r13b
0x140010527  lea     rdi, [rdx+140h]
0x14001052e  test    r9b, r9b
0x140010531  jnz     short loc_140010569
0x140010533  mov     rax, [rdi]
0x140010536  mov     rcx, [rax+88h]
0x14001053d  mov     rdx, [rcx+50h]
0x140010541  add     rdx, 8
0x140010545  lea     r9d, [r13+2]
0x140010549  xor     r8d, r8d
0x14001054c  mov     rcx, rsi
0x14001054f  call    UdfAcquireResource
0x140010554  mov     rdx, [rdi]
0x140010557  xor     r9d, r9d
0x14001055a  xor     r8d, r8d
0x14001055d  mov     rdx, [rdx+10h]
0x140010561  mov     rcx, rsi
0x140010564  call    UdfAcquireResource
0x140010569  mov     rax, [rbx+148h]
0x140010570  mov     rcx, [rax+88h]
0x140010577  mov     rdx, [rcx+50h]
0x14001057b  add     rdx, 8
0x14001057f  mov     r9d, 2
0x140010585  xor     r8d, r8d
0x140010588  mov     rcx, rsi
0x14001058b  call    UdfAcquireResource
0x140010590  mov     rdx, [rbx+148h]
0x140010597  xor     r9d, r9d
0x14001059a  xor     r8d, r8d
0x14001059d  mov     rdx, [rdx+10h]
0x1400105a1  mov     rcx, rsi
0x1400105a4  call    UdfAcquireResource
0x1400105a9  mov     [rsp+58h+var_37], 1
0x1400105ae  mov     rcx, [rdi]
0x1400105b1  mov     rcx, [rcx+30h]; FastMutex
0x1400105b5  call    cs:__imp_ExAcquireFastMutex
0x1400105bc  nop     dword ptr [rax+rax+00h]
0x1400105c1  mov     rcx, [rbx+148h]
0x1400105c8  mov     rcx, [rcx+30h]; FastMutex
0x1400105cc  call    cs:__imp_ExAcquireFastMutex
0x1400105d3  nop     dword ptr [rax+rax+00h]
0x1400105d8  mov     [rsp+58h+var_38], 1
0x1400105dd  mov     ecx, [rbx+48h]
0x1400105e0  mov     rdx, [rdi]
0x1400105e3  mov     r12, [rdx+18h]
0x1400105e7  shr     r12, cl
0x1400105ea  mov     eax, [r14+4]
0x1400105ee  shl     rax, cl
0x1400105f1  add     [rdx+20h], rax
0x1400105f5  mov     rcx, [rdi]
0x1400105f8  mov     rax, [rcx+20h]
0x1400105fc  mov     [rcx+18h], rax
0x140010600  mov     rcx, [rdi]
0x140010603  mov     rax, [rcx+18h]
0x140010607  mov     [rcx+28h], rax
0x14001060b  mov     rdx, [rdi]
0x14001060e  mov     rax, [rdx+18h]
0x140010612  mov     ecx, [rbx+48h]
0x140010615  shr     rax, cl
0x140010618  mov     [rdx+128h], eax
0x14001061e  mov     rcx, [rdi]
0x140010621  mov     rax, [rcx+20h]
0x140010625  mov     [rcx+130h], rax
0x14001062c  mov     rcx, [rdi]
0x14001062f  mov     eax, [r14+4]
0x140010633  add     [rcx+144h], eax
0x140010639  mov     rcx, [rdi]
0x14001063c  mov     eax, [r14+4]
0x140010640  add     [rcx+140h], eax
0x140010646  mov     rcx, [rdi]
0x140010649  lea     rdx, [rcx+18h]; FileSizes
0x14001064d  mov     rcx, [rcx+1F8h]; FileObject
0x140010654  call    cs:__imp_CcSetFileSizes
0x14001065b  nop     dword ptr [rax+rax+00h]
0x140010660  mov     rdx, [rbx+148h]
0x140010667  mov     eax, [r14+4]
0x14001066b  mov     ecx, [rbx+48h]
0x14001066e  shl     rax, cl
0x140010671  add     [rdx+20h], rax
0x140010675  mov     rcx, [rbx+148h]
0x14001067c  mov     rax, [rcx+20h]
0x140010680  mov     [rcx+18h], rax
0x140010684  mov     rcx, [rbx+148h]
0x14001068b  mov     rax, [rcx+18h]
0x14001068f  mov     [rcx+28h], rax
0x140010693  mov     rdx, [rbx+148h]
0x14001069a  mov     rax, [rdx+18h]
0x14001069e  mov     ecx, [rbx+48h]
0x1400106a1  shr     rax, cl
0x1400106a4  mov     [rdx+128h], eax
0x1400106aa  mov     rcx, [rbx+148h]
0x1400106b1  mov     rax, [rcx+20h]
0x1400106b5  mov     [rcx+130h], rax
0x1400106bc  mov     rcx, [rbx+148h]
0x1400106c3  mov     eax, [r14+4]
0x1400106c7  add     [rcx+144h], eax
0x1400106cd  mov     rcx, [rbx+148h]
0x1400106d4  mov     eax, [r14+4]
0x1400106d8  add     [rcx+140h], eax
0x1400106de  test    dword ptr [rbx+30h], 8000000h
0x1400106e5  jz      short loc_140010705
0x1400106e7  mov     rcx, [rbx+148h]
0x1400106ee  lea     rdx, [rcx+18h]; FileSizes
0x1400106f2  mov     rcx, [rcx+1F8h]; FileObject
0x1400106f9  call    cs:__imp_CcSetFileSizes
0x140010700  nop     dword ptr [rax+rax+00h]
0x140010705  mov     rcx, [rbx+148h]
0x14001070c  mov     rcx, [rcx+30h]; FastMutex
0x140010710  call    cs:__imp_ExReleaseFastMutex
0x140010717  nop     dword ptr [rax+rax+00h]
0x14001071c  mov     rcx, [rdi]
0x14001071f  mov     rcx, [rcx+30h]; FastMutex
0x140010723  call    cs:__imp_ExReleaseFastMutex
0x14001072a  nop     dword ptr [rax+rax+00h]
0x14001072f  mov     [rsp+58h+var_38], r13b
0x140010734  mov     edx, [rbx+30h]
0x140010737  mov     r13d, r12d
0x14001073a  mov     r9d, [r14+4]; SectorCount
0x14001073e  mov     rax, [rsi+10h]
0x140010742  mov     ecx, [rax+290h]
0x140010748  add     ecx, [r14]
0x14001074b  xor     eax, eax
0x14001074d  and     edx, 20000000h
0x140010753  cmovz   eax, ecx
0x140010756  mov     r8d, eax; Lbn
0x140010759  neg     edx
0x14001075b  sbb     rcx, rcx
0x14001075e  and     ecx, 20h
0x140010761  add     rcx, 0E8h
0x140010768  add     rcx, [rdi]; Mcb
0x14001076b  mov     edx, r12d; Vbn
0x14001076e  call    cs:__imp_FsRtlAddLargeMcbEntry
0x140010775  nop     dword ptr [rax+rax+00h]
0x14001077a  mov     r10d, [rbx+30h]
0x14001077e  bt      r10d, 1Bh
0x140010783  jnb     short loc_1400107CC
0x140010785  mov     r9d, [r14+10h]; SectorCount
0x140010789  mov     rax, [rsi+10h]
0x14001078d  mov     ecx, [rax+290h]
0x140010793  add     ecx, [r14+0Ch]
0x140010797  xor     eax, eax
0x140010799  and     r10d, 20000000h
0x1400107a0  cmovz   eax, ecx
0x1400107a3  mov     r8d, eax; Lbn
0x1400107a6  neg     r10d
0x1400107a9  sbb     rcx, rcx
0x1400107ac  and     ecx, 20h
0x1400107af  add     rcx, 0E8h
0x1400107b6  add     rcx, [rbx+148h]; Mcb
0x1400107bd  mov     edx, r13d; Vbn
0x1400107c0  call    cs:__imp_FsRtlAddLargeMcbEntry
0x1400107c7  nop     dword ptr [rax+rax+00h]
0x1400107cc  mov     rdx, [rdi]
0x1400107cf  mov     r9, [rdx+18h]
0x1400107d3  mov     ecx, [rbx+48h]
0x1400107d6  shr     r9, cl
0x1400107d9  mov     r8d, r12d
0x1400107dc  mov     rcx, rsi
0x1400107df  call    UdfUpdateAdsFromScb
0x1400107e4  bt      dword ptr [rbx+30h], 1Bh
0x1400107e9  jb      short loc_140010837
0x1400107eb  mov     rax, [rdi]
0x1400107ee  mov     rcx, [rbx+148h]
0x1400107f5  movups  xmm0, xmmword ptr [rax+0E8h]
0x1400107fc  movups  xmmword ptr [rcx+0E8h], xmm0
0x140010803  movups  xmm1, xmmword ptr [rax+0F8h]
0x14001080a  movups  xmmword ptr [rcx+0F8h], xmm1
0x140010811  mov     rax, [rdi]
0x140010814  mov     rcx, [rbx+148h]
0x14001081b  movups  xmm0, xmmword ptr [rax+108h]
0x140010822  movups  xmmword ptr [rcx+108h], xmm0
0x140010829  movups  xmm1, xmmword ptr [rax+118h]
0x140010830  movups  xmmword ptr [rcx+118h], xmm1
0x140010837  mov     rdx, [rbx+148h]
0x14001083e  mov     r9, [rdx+18h]
0x140010842  mov     ecx, [rbx+48h]
0x140010845  shr     r9, cl
0x140010848  mov     r8d, r12d
0x14001084b  mov     rcx, rsi
0x14001084e  call    UdfUpdateAdsFromScb
0x140010853  mov     eax, [rbx+30h]
0x140010856  bt      eax, 1Bh
0x14001085a  jb      short loc_140010888
0x14001085c  mov     rax, [rbx+148h]
0x140010863  xorps   xmm0, xmm0
0x140010866  movups  xmmword ptr [rax+0E8h], xmm0
0x14001086d  movups  xmmword ptr [rax+0F8h], xmm0
0x140010874  mov     rax, [rbx+148h]
0x14001087b  add     rax, 108h
0x140010881  movups  xmmword ptr [rax], xmm0
0x140010884  movups  xmmword ptr [rax+10h], xmm0
0x140010888  mov     rcx, [rbx+148h]
0x14001088f  mov     rcx, [rcx+10h]; Resource
0x140010893  call    cs:__imp_ExReleaseResourceLite
0x14001089a  nop     dword ptr [rax+rax+00h]
0x14001089f  mov     rax, [rbx+148h]
0x1400108a6  mov     rcx, [rax+88h]
0x1400108ad  mov     rcx, [rcx+50h]
0x1400108b1  add     rcx, 8; Resource
0x1400108b5  call    cs:__imp_ExReleaseResourceLite
0x1400108bc  nop     dword ptr [rax+rax+00h]
0x1400108c1  test    r15b, r15b
0x1400108c4  jnz     short loc_1400108F7
0x1400108c6  mov     rcx, [rdi]
0x1400108c9  mov     rcx, [rcx+10h]; Resource
0x1400108cd  call    cs:__imp_ExReleaseResourceLite
0x1400108d4  nop     dword ptr [rax+rax+00h]
0x1400108d9  mov     rcx, [rdi]
0x1400108dc  mov     rdx, [rcx+88h]
0x1400108e3  mov     rcx, [rdx+50h]
0x1400108e7  add     rcx, 8; Resource
0x1400108eb  call    cs:__imp_ExReleaseResourceLite
0x1400108f2  nop     dword ptr [rax+rax+00h]
0x1400108f7  mov     al, 1
0x1400108f9  mov     rbx, [rsp+58h+arg_0]
0x1400108fe  mov     rsi, [rsp+58h+arg_10]
0x140010903  add     rsp, 30h
0x140010907  pop     r15
0x140010909  pop     r14
0x14001090b  pop     r13
0x14001090d  pop     r12
0x14001090f  pop     rdi
0x140010910  retn
0x14001d7e1  push    rbx
0x14001d7e3  push    rbp
0x14001d7e4  sub     rsp, 28h
0x14001d7e8  mov     rbp, rdx
0x14001d7eb  mov     rbx, [rbp+68h]
0x14001d7ef  cmp     byte ptr [rbp+20h], 0
0x14001d7f3  jz      short loc_14001D824
0x14001d7f5  mov     rcx, [rbx+148h]
0x14001d7fc  mov     rcx, [rcx+30h]; FastMutex
0x14001d800  call    cs:__imp_ExReleaseFastMutex
0x14001d807  nop     dword ptr [rax+rax+00h]
0x14001d80c  mov     rcx, [rbx+140h]
0x14001d813  mov     rcx, [rcx+30h]; FastMutex
0x14001d817  call    cs:__imp_ExReleaseFastMutex
0x14001d81e  nop     dword ptr [rax+rax+00h]
0x14001d823  nop
0x14001d824  cmp     byte ptr [rbp+21h], 0
0x14001d828  jz      short loc_14001D8A3
0x14001d82a  mov     rcx, [rbx+148h]
0x14001d831  mov     rcx, [rcx+10h]; Resource
0x14001d835  call    cs:__imp_ExReleaseResourceLite
0x14001d83c  nop     dword ptr [rax+rax+00h]
0x14001d841  mov     rax, [rbx+148h]
0x14001d848  mov     rcx, [rax+88h]
0x14001d84f  mov     rcx, [rcx+50h]
0x14001d853  add     rcx, 8; Resource
0x14001d857  call    cs:__imp_ExReleaseResourceLite
0x14001d85e  nop     dword ptr [rax+rax+00h]
0x14001d863  cmp     byte ptr [rbp+78h], 0
0x14001d867  jnz     short loc_14001D8A3
0x14001d869  mov     rcx, [rbx+140h]
0x14001d870  mov     rcx, [rcx+10h]; Resource
0x14001d874  call    cs:__imp_ExReleaseResourceLite
0x14001d87b  nop     dword ptr [rax+rax+00h]
0x14001d880  mov     rax, [rbx+140h]
0x14001d887  mov     rcx, [rax+88h]
0x14001d88e  mov     rcx, [rcx+50h]
0x14001d892  add     rcx, 8; Resource
0x14001d896  call    cs:__imp_ExReleaseResourceLite
0x14001d89d  nop     dword ptr [rax+rax+00h]
0x14001d8a2  nop
0x14001d8a3  add     rsp, 28h
0x14001d8a7  pop     rbp
0x14001d8a8  pop     rbx
0x14001d8a9  retn
```
