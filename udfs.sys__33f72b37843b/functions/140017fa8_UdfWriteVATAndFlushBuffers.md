# UdfWriteVATAndFlushBuffers

- ea: `0x140017fa8`
- end: `0x14001858b`
- name: `UdfWriteVATAndFlushBuffers`
- size: `1507`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x140017c08`

## callees

- `0x140007b90`
- `0x140009450`
- `0x14000a2e8`
- `0x14000a870`
- `0x14000cbcc`
- `0x14001093c`
- `0x140016ac0`
- `0x140017fa8`
- `0x14001bc30`
- `0x14001c080`
- `0x14002c774`
- `0x140039750`
- `0x14003b730`
- `0x14004ce50`

## import_xrefs

- `ntoskrnl!CcUnpinData` at `0x140018199`
- `ntoskrnl!CcUnpinData` at `0x140018199`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001804a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001838c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140018495`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001853e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001df65`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001df80`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001804a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001838c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140018495`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001853e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001df65`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001df80`
- `ntoskrnl!CcPinRead` at `0x140018188`
- `ntoskrnl!CcPinRead` at `0x140018188`
- `ntoskrnl!CcFlushCache` at `0x140018079`
- `ntoskrnl!CcFlushCache` at `0x1400180a3`
- `ntoskrnl!CcFlushCache` at `0x140018079`
- `ntoskrnl!CcFlushCache` at `0x1400180a3`

## pseudocode

```c
__int64 __fastcall UdfWriteVATAndFlushBuffers(__int64 a1, __int64 a2)
{
  unsigned int v4; // edi
  __int64 v5; // r13
  __int64 v6; // r15
  char v7; // r14
  int v8; // r15d
  unsigned int v9; // edi
  __int64 v10; // rcx
  int *v11; // r15
  __int64 v12; // rax
  int v13; // ecx
  __int64 v14; // rcx
  __int64 v15; // r12
  _WORD *v16; // rcx
  __int64 v17; // rax
  _WORD *v18; // rax
  __int64 v19; // r8
  unsigned int v20; // r12d
  _WORD *v21; // rcx
  __int16 v22; // r8
  __int64 v23; // rax
  int v24; // r10d
  _DWORD *v25; // rax
  int v26; // edx
  __int64 v27; // rcx
  __int64 v28; // rcx
  unsigned int v30; // [rsp+44h] [rbp-874h] BYREF
  unsigned int Size; // [rsp+48h] [rbp-870h] BYREF
  unsigned int Size_4; // [rsp+4Ch] [rbp-86Ch] BYREF
  __int64 v33; // [rsp+50h] [rbp-868h] BYREF
  PVOID Bcb; // [rsp+58h] [rbp-860h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+60h] [rbp-858h] BYREF
  __int64 v36; // [rsp+68h] [rbp-850h]
  PVOID Buffer; // [rsp+70h] [rbp-848h] BYREF
  __int64 v38; // [rsp+78h] [rbp-840h]
  _BYTE v39[2048]; // [rsp+80h] [rbp-838h] BYREF

  v36 = a2;
  Size_4 = 0;
  v4 = 0;
  v30 = 0;
  v38 = *(_QWORD *)(a2 + 344);
  v5 = v38;
  v6 = *(_QWORD *)(a2 + 352);
  v33 = 0;
  FileOffset.QuadPart = 0;
  Buffer = 0;
  Bcb = 0;
  UdfAcquireResource(a1, *(_QWORD *)(v38 + 16), 0, 0);
  v7 = 1;
  UdfUpdateVatHeader(a1);
  ExReleaseResourceLite(*(PERESOURCE *)(v38 + 16));
  UdfSeqCacheFlush(a1, a2);
  CcFlushCache(*(PSECTION_OBJECT_POINTERS *)(*(_QWORD *)(v6 + 504) + 40LL), 0, 0, 0);
  UdfSeqCacheFlush(a1, a2);
  CcFlushCache(*(PSECTION_OBJECT_POINTERS *)(*(_QWORD *)(v38 + 504) + 40LL), 0, 0, 0);
  UdfAcquireResource(a1, *(_QWORD *)(a2 + 104) + 344LL, 0, 0);
  UdfSeqCacheFlush(a1, a2);
  UdfAcquireResource(0, a2 + 136, 0, 0);
  v8 = UdfSeqCacheSyncCache(a2);
  if ( v8 >= 0 )
  {
    v8 = UdfQueryFreeBlocksAndNWA(a2, &Size_4, &v30);
    v4 = v30;
  }
  if ( v8 >= 0 )
  {
    v9 = v4 - *(_DWORD *)(*(_QWORD *)(a1 + 16) + 656LL);
    v30 = v9;
    UdfAcquireResource(a1, *(_QWORD *)(v5 + 16), 0, 0);
    v10 = *(_QWORD *)(a2 + 344);
    v11 = (int *)(v5 + 32);
    if ( (*(_DWORD *)(v10 + 212) & 2) != 0 )
    {
      FileOffset.QuadPart = 0;
      CcPinRead(*(PFILE_OBJECT *)(v10 + 504), &FileOffset, *(_DWORD *)(v10 + 32), 1u, &Bcb, &Buffer);
      CcUnpinData(Bcb);
      Bcb = 0;
      v12 = *(_QWORD *)(a2 + 464);
      v13 = *v11;
      if ( *(_WORD *)v12 == 266 )
        *(_DWORD *)(v12 + 212) = v13;
      else
        *(_DWORD *)(v12 + 172) = v13;
      v30 = v9;
    }
    else
    {
      *(_WORD *)(*(_QWORD *)(a2 + 464) + 34LL) &= 0xFFF8u;
      *(_QWORD *)(*(_QWORD *)(a2 + 464) + 64LL) = (unsigned int)((~(unsigned __int64)(unsigned int)(*(_DWORD *)(a2 + 68)
                                                                                                  - 1)
                                                                & ((unsigned int)(*(_DWORD *)(a2 + 68) - 1)
                                                                 + *(_QWORD *)v11)) >> *(_DWORD *)(a2 + 72));
      v14 = *(unsigned int *)(v5 + 224);
      Size = (*(_DWORD *)(a2 + 68) - v14) & 0xFFFFFFFC;
      memset((void *)(*(_QWORD *)(a2 + 464) + v14), 0, Size);
      UdfGenerateVatAds(a1, (unsigned int)&v33, *(_DWORD *)(a2 + 464) + *(_DWORD *)(v5 + 224), (unsigned int)&Size, v9);
      v15 = v33;
      while ( 1 )
      {
        v30 = v9;
        Size_4 = v9;
        if ( v15 >= *(_QWORD *)v11 )
          break;
        Size = *(_DWORD *)(a2 + 68);
        UdfGenerateVatAds(a1, (unsigned int)&v33, (unsigned int)v39, (unsigned int)&Size, v9);
        v15 = v33;
        if ( v33 >= *(_QWORD *)v11 )
          memset(&v39[*(_DWORD *)(a2 + 68) - Size], 0, Size);
        UdfSeqCacheWriteBlocksForFile(a1, -1, 0, 1, v5 + 32, (__int64)v39, 0);
        v9 = Size_4 + 1;
        v30 = Size_4 + 1;
      }
    }
    *(_DWORD *)(*(_QWORD *)(a2 + 464) + 28LL) = 0;
    *(_WORD *)(*(_QWORD *)(a2 + 464) + 32LL) = 0;
    v16 = *(_WORD **)(a2 + 464);
    v17 = 64;
    if ( *v16 != 261 )
      v17 = 84;
    *(_OWORD *)&v16[v17] = UdfMsRegId;
    *(_OWORD *)&v16[v17 + 8] = xmmword_140025350;
    *(_QWORD *)(*(_QWORD *)(a2 + 464) + 56LL) = *(_QWORD *)v11;
    *(_QWORD *)(v5 + 480) = MEMORY[0xFFFFF78000000014];
    *(_DWORD *)(v5 + 212) |= 0x10000u;
    v18 = *(_WORD **)(a2 + 464);
    v19 = 42;
    if ( *v18 != 261 )
      v19 = 46;
    UdfConvertNtTimeToUdfTime(92, v5 + 480, &v18[v19]);
    ExReleaseResourceLite(*(PERESOURCE *)(v5 + 16));
    v20 = *(_DWORD *)(*(_QWORD *)(a2 + 104) + 12LL) + ~(v30 & (*(_DWORD *)(*(_QWORD *)(a2 + 104) + 12LL) - 1));
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10000000) != 0 )
    {
      WPP_SF_dd(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
        22,
        WPP_3e271ebed6f63f8fe36d0f7ec1e80eae_Traceguids,
        v20,
        v9);
    }
    if ( v20 )
    {
      UdfSeqCacheWriteBlocksForFile(a1, -1, 0, v20, v5 + 32, 0, 0);
      v9 = v20 + v30;
      v30 += v20;
    }
    UdfAcquireResource(a1, *(_QWORD *)(v5 + 16), 0, 0);
    *(_DWORD *)(*(_QWORD *)(a2 + 464) + 12LL) = v9;
    v21 = *(_WORD **)(a2 + 464);
    v22 = *v21;
    v23 = 84;
    if ( *v21 != 261 )
      v23 = 104;
    v24 = *(_DWORD *)&v21[v23];
    v25 = v21 + 86;
    if ( v22 != 261 )
      v25 = v21 + 106;
    v26 = 216;
    if ( v22 != 266 )
      v26 = 176;
    UdfUpdateChecksumAndCrc(v21, (unsigned int)(*v25 + v24 + v26));
    ExReleaseResourceLite(*(PERESOURCE *)(v5 + 16));
    v8 = UdfSeqCacheWriteBlocksForFile(a1, -1, 0, 1, v5 + 32, *(_QWORD *)(a2 + 464), 0);
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10000000) != 0 )
    {
      WPP_SF_dd(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
        23,
        WPP_3e271ebed6f63f8fe36d0f7ec1e80eae_Traceguids,
        v9,
        v9 + *(_DWORD *)(*(_QWORD *)(a1 + 16) + 656LL));
    }
    UdfReleaseDevice(v27, a2, 0);
    v7 = 0;
    UdfSeqCacheFlush(a1, a2);
  }
  ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(a2 + 104) + 344LL));
  if ( v7 )
    UdfReleaseDevice(v28, a2, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140017fa8  mov     [rsp+arg_10], rbx
0x140017fad  mov     [rsp+arg_18], rsi
0x140017fb2  push    rdi
0x140017fb3  push    r12
0x140017fb5  push    r13
0x140017fb7  push    r14
0x140017fb9  push    r15
0x140017fbb  sub     rsp, 890h
0x140017fc2  mov     rax, cs:__security_cookie
0x140017fc9  xor     rax, rsp
0x140017fcc  mov     [rsp+8B8h+var_38], rax
0x140017fd4  mov     rbx, rdx
0x140017fd7  mov     rsi, rcx
0x140017fda  mov     [rsp+8B8h+var_850], rdx
0x140017fdf  xor     r12d, r12d
0x140017fe2  mov     dword ptr [rsp+8B8h+Size+4], r12d
0x140017fe7  mov     edi, r12d
0x140017fea  mov     [rsp+8B8h+var_874], r12d
0x140017fef  mov     r13, [rdx+158h]
0x140017ff6  mov     [rsp+8B8h+var_840], r13
0x140017ffb  mov     r15, [rdx+160h]
0x140018002  mov     [rsp+8B8h+var_868], r12
0x140018007  mov     [rsp+8B8h+var_878], r12b
0x14001800c  mov     [rsp+8B8h+var_876], r12b
0x140018011  mov     [rsp+8B8h+var_877], r12b
0x140018016  mov     qword ptr [rsp+8B8h+FileOffset], r12
0x14001801b  mov     [rsp+8B8h+var_848], r12
0x140018020  mov     [rsp+8B8h+var_860], r12
0x140018025  xor     r9d, r9d
0x140018028  xor     r8d, r8d
0x14001802b  mov     rdx, [r13+10h]
0x14001802f  call    UdfAcquireResource
0x140018034  lea     r14d, [r12+1]
0x140018039  mov     [rsp+8B8h+var_878], r14b
0x14001803e  mov     rcx, rsi
0x140018041  call    UdfUpdateVatHeader
0x140018046  mov     rcx, [r13+10h]; Resource
0x14001804a  call    cs:__imp_ExReleaseResourceLite
0x140018051  nop     dword ptr [rax+rax+00h]
0x140018056  mov     [rsp+8B8h+var_878], r12b
0x14001805b  mov     rdx, rbx
0x14001805e  mov     rcx, rsi
0x140018061  call    UdfSeqCacheFlush
0x140018066  mov     rcx, [r15+1F8h]
0x14001806d  xor     r9d, r9d; IoStatus
0x140018070  xor     r8d, r8d; Length
0x140018073  xor     edx, edx; FileOffset
0x140018075  mov     rcx, [rcx+28h]; SectionObjectPointer
0x140018079  call    cs:__imp_CcFlushCache
0x140018080  nop     dword ptr [rax+rax+00h]
0x140018085  mov     rdx, rbx
0x140018088  mov     rcx, rsi
0x14001808b  call    UdfSeqCacheFlush
0x140018090  mov     rcx, [r13+1F8h]
0x140018097  xor     r9d, r9d; IoStatus
0x14001809a  xor     r8d, r8d; Length
0x14001809d  xor     edx, edx; FileOffset
0x14001809f  mov     rcx, [rcx+28h]; SectionObjectPointer
0x1400180a3  call    cs:__imp_CcFlushCache
0x1400180aa  nop     dword ptr [rax+rax+00h]
0x1400180af  mov     rdx, [rbx+68h]
0x1400180b3  add     rdx, 158h
0x1400180ba  xor     r9d, r9d
0x1400180bd  xor     r8d, r8d
0x1400180c0  mov     rcx, rsi
0x1400180c3  call    UdfAcquireResource
0x1400180c8  mov     [rsp+8B8h+var_876], r14b
0x1400180cd  mov     rdx, rbx
0x1400180d0  mov     rcx, rsi
0x1400180d3  call    UdfSeqCacheFlush
0x1400180d8  lea     rdx, [rbx+88h]
0x1400180df  xor     r9d, r9d
0x1400180e2  xor     r8d, r8d
0x1400180e5  xor     ecx, ecx
0x1400180e7  call    UdfAcquireResource
0x1400180ec  mov     [rsp+8B8h+var_877], r14b
0x1400180f1  mov     rcx, rbx
0x1400180f4  call    UdfSeqCacheSyncCache
0x1400180f9  mov     r15d, eax
0x1400180fc  test    eax, eax
0x1400180fe  js      short loc_140018119
0x140018100  lea     r8, [rsp+8B8h+var_874]
0x140018105  lea     rdx, [rsp+8B8h+Size+4]
0x14001810a  mov     rcx, rbx
0x14001810d  call    UdfQueryFreeBlocksAndNWA
0x140018112  mov     r15d, eax
0x140018115  mov     edi, [rsp+8B8h+var_874]
0x140018119  test    r15d, r15d
0x14001811c  js      loc_140018533
0x140018122  mov     rax, [rsi+10h]
0x140018126  sub     edi, [rax+290h]
0x14001812c  mov     [rsp+8B8h+var_874], edi
0x140018130  xor     r9d, r9d
0x140018133  xor     r8d, r8d
0x140018136  mov     rdx, [r13+10h]
0x14001813a  mov     rcx, rsi
0x14001813d  call    UdfAcquireResource
0x140018142  mov     [rsp+8B8h+var_878], r14b
0x140018147  mov     rcx, [rbx+158h]
0x14001814e  lea     r15, [r13+20h]
0x140018152  mov     eax, [rcx+0D4h]
0x140018158  test    al, 2
0x14001815a  jz      short loc_1400181D5
0x14001815c  mov     qword ptr [rsp+8B8h+FileOffset], r12
0x140018161  lea     rax, [rsp+8B8h+var_848]
0x140018166  mov     [rsp+8B8h+Buffer], rax; Buffer
0x14001816b  lea     rax, [rsp+8B8h+var_860]
0x140018170  mov     [rsp+8B8h+Bcb], rax; Bcb
0x140018175  mov     r9d, r14d; Flags
0x140018178  mov     r8d, [rcx+20h]; Length
0x14001817c  lea     rdx, [rsp+8B8h+FileOffset]; FileOffset
0x140018181  mov     rcx, [rcx+1F8h]; FileObject
0x140018188  call    cs:__imp_CcPinRead
0x14001818f  nop     dword ptr [rax+rax+00h]
0x140018194  mov     rcx, [rsp+8B8h+var_860]; Bcb
0x140018199  call    cs:__imp_CcUnpinData
0x1400181a0  nop     dword ptr [rax+rax+00h]
0x1400181a5  mov     [rsp+8B8h+var_860], r12
0x1400181aa  mov     rax, [rbx+1D0h]
0x1400181b1  mov     ecx, [r15]
0x1400181b4  mov     edx, 10Ah
0x1400181b9  cmp     [rax], dx
0x1400181bc  jnz     short loc_1400181C6
0x1400181be  mov     [rax+0D4h], ecx
0x1400181c4  jmp     short loc_1400181CC
0x1400181c6  mov     [rax+0ACh], ecx
0x1400181cc  mov     [rsp+8B8h+var_874], edi
0x1400181d0  jmp     loc_1400182F5
0x1400181d5  mov     rax, [rbx+1D0h]
0x1400181dc  mov     ecx, 0FFF8h
0x1400181e1  and     [rax+22h], cx
0x1400181e5  mov     ecx, [rbx+44h]
0x1400181e8  sub     ecx, r14d
0x1400181eb  mov     rdx, [r15]
0x1400181ee  add     rdx, rcx
0x1400181f1  not     rcx
0x1400181f4  and     rdx, rcx
0x1400181f7  mov     ecx, [rbx+48h]
0x1400181fa  shr     rdx, cl
0x1400181fd  mov     ecx, edx
0x1400181ff  mov     rax, [rbx+1D0h]
0x140018206  mov     [rax+40h], rcx
0x14001820a  mov     ecx, [r13+0E0h]
0x140018211  mov     r8d, [rbx+44h]
0x140018215  sub     r8d, ecx
0x140018218  and     r8d, 0FFFFFFFCh; Size
0x14001821c  mov     dword ptr [rsp+8B8h+Size], r8d
0x140018221  add     rcx, [rbx+1D0h]; void *
0x140018228  xor     edx, edx; Val
0x14001822a  call    memset
0x14001822f  mov     r8d, [r13+0E0h]
0x140018236  add     r8, [rbx+1D0h]
0x14001823d  mov     dword ptr [rsp+8B8h+Bcb], edi
0x140018241  lea     r9, [rsp+8B8h+Size]
0x140018246  lea     rdx, [rsp+8B8h+var_868]
0x14001824b  mov     rcx, rsi
0x14001824e  call    UdfGenerateVatAds
0x140018253  mov     r12, [rsp+8B8h+var_868]
0x140018258  mov     [rsp+8B8h+var_874], edi
0x14001825c  mov     dword ptr [rsp+8B8h+Size+4], edi
0x140018260  cmp     r12, [r15]
0x140018263  jge     loc_1400182F2
0x140018269  mov     eax, [rbx+44h]
0x14001826c  mov     dword ptr [rsp+8B8h+Size], eax
0x140018270  mov     dword ptr [rsp+8B8h+Bcb], edi
0x140018274  lea     r9, [rsp+8B8h+Size]
0x140018279  lea     r8, [rsp+8B8h+var_838]
0x140018281  lea     rdx, [rsp+8B8h+var_868]
0x140018286  mov     rcx, rsi
0x140018289  call    UdfGenerateVatAds
0x14001828e  mov     r12, [rsp+8B8h+var_868]
0x140018293  cmp     r12, [r15]
0x140018296  jl      short loc_1400182B6
0x140018298  mov     r8d, dword ptr [rsp+8B8h+Size]; Size
0x14001829d  mov     eax, [rbx+44h]
0x1400182a0  sub     eax, dword ptr [rsp+8B8h+Size]
0x1400182a4  lea     rcx, [rsp+8B8h+var_838]
0x1400182ac  add     rcx, rax; void *
0x1400182af  xor     edx, edx; Val
0x1400182b1  call    memset
0x1400182b6  mov     [rsp+8B8h+var_888], 0
0x1400182bf  lea     rax, [rsp+8B8h+var_838]
0x1400182c7  mov     [rsp+8B8h+Buffer], rax
0x1400182cc  mov     [rsp+8B8h+Bcb], r15
0x1400182d1  mov     r9d, r14d
0x1400182d4  xor     r8d, r8d
0x1400182d7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400182db  mov     rcx, rsi
0x1400182de  call    UdfSeqCacheWriteBlocksForFile
0x1400182e3  mov     edi, dword ptr [rsp+8B8h+Size+4]
0x1400182e7  inc     edi
0x1400182e9  mov     [rsp+8B8h+var_874], edi
0x1400182ed  jmp     loc_140018258
0x1400182f2  xor     r12d, r12d
0x1400182f5  mov     rax, [rbx+1D0h]
0x1400182fc  mov     [rax+1Ch], r12d
0x140018300  mov     rcx, [rbx+1D0h]
0x140018307  mov     [rcx+20h], r12w
0x14001830c  mov     rcx, [rbx+1D0h]
0x140018313  mov     eax, 80h
0x140018318  lea     edx, [rax+28h]
0x14001831b  lea     r9d, [rdx+5Dh]
0x14001831f  cmp     [rcx], r9w
0x140018323  cmovnz  eax, edx
0x140018326  movups  xmm0, cs:UdfMsRegId
0x14001832d  movups  xmmword ptr [rax+rcx], xmm0
0x140018331  movups  xmm1, cs:xmmword_140025350
0x140018338  movups  xmmword ptr [rax+rcx+10h], xmm1
0x14001833d  mov     rcx, [rbx+1D0h]
0x140018344  mov     rax, [r15]
0x140018347  mov     [rcx+38h], rax
0x14001834b  lea     rdx, [r13+1E0h]
0x140018352  mov     rax, ds:0FFFFF78000000014h
0x14001835c  mov     [rdx], rax
0x14001835f  bts     dword ptr [r13+0D4h], 10h
0x140018368  mov     rax, [rbx+1D0h]
0x14001836f  mov     ecx, 5Ch ; '\'
0x140018374  lea     r8d, [rcx-8]
0x140018378  cmp     [rax], r9w
0x14001837c  cmovnz  r8d, ecx
0x140018380  add     r8, rax
0x140018383  call    UdfConvertNtTimeToUdfTime
0x140018388  mov     rcx, [r13+10h]; Resource
0x14001838c  call    cs:__imp_ExReleaseResourceLite
0x140018393  nop     dword ptr [rax+rax+00h]
0x140018398  mov     [rsp+8B8h+var_878], r12b
0x14001839d  mov     rax, [rbx+68h]
0x1400183a1  mov     ecx, [rax+0Ch]
0x1400183a4  lea     r12d, [rcx-1]
0x1400183a8  and     r12d, [rsp+8B8h+var_874]
0x1400183ad  not     r12d
0x1400183b0  add     r12d, ecx
0x1400183b3  lea     rax, WPP_GLOBAL_Control
0x1400183ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400183c1  cmp     rcx, rax
0x1400183c4  jz      short loc_1400183EB
0x1400183c6  test    dword ptr [rcx+2Ch], 10000000h
0x1400183cd  jz      short loc_1400183EB
0x1400183cf  mov     edx, 16h
0x1400183d4  mov     dword ptr [rsp+8B8h+Bcb], edi
0x1400183d8  mov     r9d, r12d
0x1400183db  lea     r8, WPP_3e271ebed6f63f8fe36d0f7ec1e80eae_Traceguids
0x1400183e2  mov     rcx, [rcx+18h]
0x1400183e6  call    WPP_SF_dd
0x1400183eb  test    r12d, r12d
0x1400183ee  jz      short loc_140018424
0x1400183f0  mov     [rsp+8B8h+var_888], 0
0x1400183f9  mov     [rsp+8B8h+Buffer], 0
0x140018402  mov     [rsp+8B8h+Bcb], r15
0x140018407  mov     r9d, r12d
0x14001840a  xor     r8d, r8d
0x14001840d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140018411  mov     rcx, rsi
0x140018414  call    UdfSeqCacheWriteBlocksForFile
0x140018419  mov     edi, [rsp+8B8h+var_874]
0x14001841d  add     edi, r12d
0x140018420  mov     [rsp+8B8h+var_874], edi
0x140018424  xor     r9d, r9d
0x140018427  xor     r8d, r8d
0x14001842a  mov     rdx, [r13+10h]
0x14001842e  mov     rcx, rsi
0x140018431  call    UdfAcquireResource
0x140018436  mov     rax, [rbx+1D0h]
0x14001843d  mov     [rax+0Ch], edi
0x140018440  mov     rcx, [rbx+1D0h]
0x140018447  movzx   r8d, word ptr [rcx]
0x14001844b  mov     edx, 0D0h
0x140018450  lea     r9d, [rdx+35h]
0x140018454  cmp     r8w, r9w
0x140018458  lea     eax, [rdx-28h]
0x14001845b  cmovnz  eax, edx
0x14001845e  mov     r10d, [rax+rcx]
0x140018462  lea     rax, [rcx+0ACh]
0x140018469  jz      short loc_140018472
0x14001846b  lea     rax, [rcx+0D4h]
0x140018472  mov     edx, 0D8h
0x140018477  lea     r11d, [rdx-28h]
0x14001847b  lea     r9d, [rdx+32h]
0x14001847f  cmp     r8w, r9w
0x140018483  cmovnz  edx, r11d
0x140018487  add     edx, r10d
0x14001848a  add     edx, [rax]
0x14001848c  call    UdfUpdateChecksumAndCrc
0x140018491  mov     rcx, [r13+10h]; Resource
0x140018495  call    cs:__imp_ExReleaseResourceLite
0x14001849c  nop     dword ptr [rax+rax+00h]
0x1400184a1  xor     r12d, r12d
0x1400184a4  mov     [rsp+8B8h+var_888], r12
0x1400184a9  mov     rax, [rbx+1D0h]
0x1400184b0  mov     [rsp+8B8h+Buffer], rax
0x1400184b5  mov     [rsp+8B8h+Bcb], r15
0x1400184ba  mov     r9d, r14d
0x1400184bd  xor     r8d, r8d
0x1400184c0  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400184c4  mov     rcx, rsi
0x1400184c7  call    UdfSeqCacheWriteBlocksForFile
0x1400184cc  mov     r15d, eax
0x1400184cf  mov     r10, cs:WPP_GLOBAL_Control
0x1400184d6  lea     rax, WPP_GLOBAL_Control
0x1400184dd  cmp     r10, rax
  ... truncated ...
```
