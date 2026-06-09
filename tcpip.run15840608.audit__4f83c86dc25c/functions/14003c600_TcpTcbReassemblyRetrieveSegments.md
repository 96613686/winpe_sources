# TcpTcbReassemblyRetrieveSegments

- ea: `0x14003c600`
- end: `0x14003cd5b`
- name: `TcpTcbReassemblyRetrieveSegments`
- size: `1883`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x14003b294`
- `0x140134d40`

## callees

- `0x140014974`
- `0x14003b788`
- `0x14003b850`
- `0x14003c600`
- `0x14003cd70`
- `0x14003d348`
- `0x1400f7060`
- `0x14015421c`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14003c71f`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14003c71f`
- `ntoskrnl!IoAllocateMdl` at `0x14003c702`
- `ntoskrnl!IoAllocateMdl` at `0x14003c702`
- `ntoskrnl!IoFreeMdl` at `0x14003c923`
- `ntoskrnl!IoFreeMdl` at `0x14003c923`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003c8f2`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003ca6d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003c8f2`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003ca6d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c8a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ca0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ca23`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cc51`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cc65`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c8a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ca0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ca23`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cc51`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cc65`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x14003cb99`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x14003cb99`
- `NETIO!NetioAllocateAndReferenceNetBufferAndNetBufferList` at `0x14003c75e`
- `NETIO!NetioAllocateAndReferenceNetBufferAndNetBufferList` at `0x14003c75e`

## pseudocode

```c
__int64 __fastcall TcpTcbReassemblyRetrieveSegments(__int64 a1, __int64 *a2, _QWORD **a3, __int64 a4, int a5, char *a6)
{
  int v6; // eax
  int v7; // esi
  __int64 *v8; // rbx
  __int64 v10; // r8
  __int64 *v11; // r15
  __int64 v12; // r9
  unsigned int v14; // r11d
  unsigned int v15; // r12d
  PMDL *p_Mdl; // r14
  __int64 *v17; // rsi
  ULONG v18; // edi
  ULONG v19; // ebx
  struct _MDL *v20; // rax
  struct _MDL *v21; // rbx
  __int64 v22; // rax
  __int64 v23; // r8
  unsigned int v24; // esi
  int v25; // eax
  unsigned int v26; // edx
  int v27; // eax
  char v28; // dl
  char v29; // cl
  __int64 *v30; // r8
  __int64 v31; // rcx
  __int64 *v32; // rdx
  __int64 *v33; // rax
  __int64 **v34; // rdx
  __int64 *v35; // rcx
  __int64 *v36; // r8
  __int64 *v37; // rax
  __int64 v38; // rax
  _QWORD *v39; // rax
  int v40; // edx
  _QWORD *v41; // rcx
  int v42; // edi
  _QWORD *v43; // rbx
  char *v44; // rbx
  __int64 v45; // r8
  __int64 v46; // r9
  PMDL v47; // rcx
  struct _MDL *Next; // rbx
  __int64 v49; // rdx
  __int64 *v50; // rcx
  __int64 *v51; // r8
  __int64 *v52; // rax
  __int64 **v53; // rdx
  __int64 *v54; // rcx
  __int64 *v55; // r8
  __int64 *v56; // rax
  __int64 v57; // rax
  _QWORD *v58; // rax
  int v59; // edx
  _QWORD *v60; // rdi
  int v61; // ebx
  void *v62; // rcx
  _QWORD *v63; // rsi
  char *v64; // rdi
  __int64 v65; // rbx
  _QWORD *v66; // rax
  _DWORD *v67; // r14
  __int64 v68; // rdx
  int v69; // r11d
  __int64 v70; // rcx
  unsigned int v71; // eax
  unsigned int v72; // ebx
  unsigned int v73; // eax
  int v74; // ecx
  unsigned int v75; // edx
  __int64 *v76; // rbx
  int v77; // edx
  void *v78; // rcx
  int UrgentBoundary; // eax
  unsigned int v80; // r10d
  int v81; // r11d
  bool v82; // zf
  PMDL Mdl; // [rsp+30h] [rbp-58h] BYREF
  __int64 v84; // [rsp+38h] [rbp-50h]
  __int64 v85[9]; // [rsp+40h] [rbp-48h] BYREF
  __int64 *v86; // [rsp+98h] [rbp+10h]

  v86 = a2;
  v6 = *(_DWORD *)(a1 + 124);
  v7 = a4;
  v85[0] = 0;
  v8 = a2;
  if ( (v6 & 0x10) != 0 )
  {
    LOBYTE(a2) = 1;
    TcpTcbSetReassembly(a1, a2, a3, a4);
    v11 = **(__int64 ***)(a1 + 936);
    if ( v11 )
    {
      v12 = 0;
      if ( *((_DWORD *)v11 + 5) - a5 <= 0 )
      {
        while ( 1 )
        {
          if ( !v11 )
            return 0;
          v14 = *((_DWORD *)v11 + 5);
          if ( (int)(v14 - a5) >= 0 )
            break;
          v67 = (_DWORD *)v11[4];
          if ( !*((_DWORD *)v11 + 6) )
            goto LABEL_87;
          if ( *v8 )
          {
            v68 = *(_QWORD *)(*v8 + 8);
            v69 = v14 - v7;
            v70 = *((unsigned int *)v11 + 7);
            v71 = v67[2] - v70;
            if ( v71 >= *(_DWORD *)(v68 + 24) - v69 )
              v71 = *(_DWORD *)(v68 + 24) - v69;
            v72 = v71;
            RtlCopyKernelBufferToMdl(
              *((_QWORD *)v67 + 2) + v70,
              *(_QWORD *)(v68 + 8),
              (unsigned int)(v69 + *(_DWORD *)(v68 + 16)),
              v71,
              v85);
            TcpTcbReassemblySetDsack(a1, *((unsigned int *)v11 + 5), v72);
            v12 = 0;
          }
          else
          {
            v72 = v67[2] - *((_DWORD *)v11 + 7);
            if ( v72 >= v7 - v14 )
              v72 = v7 - v14;
          }
          v73 = *((_DWORD *)v11 + 7);
          *((_DWORD *)v11 + 6) -= v72;
          *((_DWORD *)v11 + 5) += v72;
          v74 = *((_DWORD *)v11 + 6);
          v75 = v73 + v72;
          if ( v73 + v72 < v73 )
          {
            v65 = *v11;
            LOBYTE(v10) = 1;
            TcpTcbReassemblyCleanupHeader(a1, v11, v10, 0);
            v24 = 0;
LABEL_69:
            **(_QWORD **)(a1 + 936) = v65;
            v66 = *(_QWORD **)(a1 + 936);
            if ( !*v66 )
            {
              v66[1] = 0;
              if ( !*(_DWORD *)(*(_QWORD *)(a1 + 936) + 48LL) )
                TcpTcbSetReassembly(a1, 0, v45, v46);
            }
            return v24;
          }
          v8 = v86;
          *((_DWORD *)v11 + 7) = v75;
          if ( v74 )
          {
            if ( v67[2] == *((_DWORD *)v11 + 7) )
            {
              v11[4] = *(_QWORD *)v67;
              *((_DWORD *)v11 + 7) = 0;
              v77 = v67[2];
              *(_DWORD *)(*(_QWORD *)(a1 + 936) + 24LL) -= v77;
              _InterlockedAdd64(&ReassemblySize, -v77);
              v78 = (void *)*((_QWORD *)v67 + 2);
              if ( v78 )
                ExFreePoolWithTag(v78, 0x42526354u);
              ExFreePoolWithTag(v67, 0x48526354u);
              --*(_DWORD *)(*(_QWORD *)(a1 + 936) + 28LL);
              v12 = 0;
            }
          }
          else
          {
LABEL_87:
            LOBYTE(v10) = 1;
            *a6 |= *((_BYTE *)v11 + 16);
            v76 = (__int64 *)*v11;
            TcpTcbReassemblyCleanupHeader(a1, v11, v10, 0);
            v11 = v76;
            v12 = 0;
            v8 = v86;
          }
        }
        if ( (int)(v14 - a5) > 0 )
          return 0;
        if ( (*(_DWORD *)(a1 + 124) & 0x40) != 0 )
        {
          if ( (*(_DWORD *)(a1 + 120) & 0x1000000) != 0 )
            v82 = *(_DWORD *)(a1 + 536) == v14;
          else
            v82 = *(_DWORD *)(a1 + 532) == v14;
          if ( v82 )
            return 0;
          UrgentBoundary = TcpFindUrgentBoundary(a1, v14, *((unsigned int *)v11 + 6));
          v15 = UrgentBoundary - v81;
          if ( UrgentBoundary == v81 )
            v15 = v80;
          v12 = 0;
        }
        else
        {
          v15 = *((_DWORD *)v11 + 6);
        }
        v84 = *v11;
        if ( v15 )
        {
          p_Mdl = &Mdl;
          v17 = (__int64 *)v11[4];
          v18 = v15 + *((_DWORD *)v11 + 7);
          Mdl = 0;
          while ( v17 && v18 )
          {
            v19 = *((_DWORD *)v17 + 2);
            if ( v18 < v19 )
              v19 = v18;
            v20 = IoAllocateMdl((PVOID)v17[2], v19, 0, 0, 0);
            *p_Mdl = v20;
            if ( !v20 )
            {
              v47 = Mdl;
              if ( Mdl )
              {
                do
                {
                  Next = v47->Next;
                  IoFreeMdl(v47);
                  v47 = Next;
                }
                while ( Next );
              }
              goto LABEL_48;
            }
            v18 -= v19;
            MmBuildMdlForNonPagedPool(v20);
            p_Mdl = (PMDL *)*p_Mdl;
            v17 = (__int64 *)*v17;
          }
          v21 = Mdl;
          if ( Mdl )
          {
            v22 = NetioAllocateAndReferenceNetBufferAndNetBufferList(
                    TcpTcbReassemblyFreeNetBufferList,
                    0,
                    Mdl,
                    *((unsigned int *)v11 + 7),
                    v15,
                    1);
            v23 = v22;
            if ( v22 )
            {
              v24 = v15;
              v25 = *(_DWORD *)(v22 + 136);
              v26 = v25 | 0x80000000;
              v27 = v25 & 0x7FFFFFFF;
              if ( (v11[2] & 8) == 0 )
                v26 = v27;
              *(_DWORD *)(v23 + 136) = v26;
              if ( !*v86 )
                *v86 = v23;
              if ( *a3 )
                **a3 = v23;
              *a3 = (_QWORD *)v23;
              goto LABEL_27;
            }
            TcpTcbReassemblyFreeMdlChain(v21);
          }
LABEL_48:
          v49 = *(_QWORD *)(a1 + 936);
          v50 = 0;
          v51 = *(__int64 **)(v49 + 16);
          v52 = v51;
          if ( v51 )
          {
            while ( v52 != v11 )
            {
              v50 = v52;
              v52 = (__int64 *)v52[1];
              if ( !v52 )
                goto LABEL_52;
            }
            if ( v50 )
              v50[1] = v11[1];
            else
              *(_QWORD *)(v49 + 16) = v51[1];
          }
LABEL_52:
          v53 = *(__int64 ***)(a1 + 936);
          v54 = 0;
          v55 = *v53;
          v56 = *v53;
          if ( !*v53 )
            goto LABEL_55;
          do
          {
            if ( v56 == v11 )
              break;
            v54 = v56;
            v56 = (__int64 *)*v56;
          }
          while ( v56 );
          if ( v54 )
            *v54 = *v11;
          else
LABEL_55:
            *v53 = (__int64 *)*v55;
          v57 = *(_QWORD *)(a1 + 936);
          if ( *(__int64 **)(v57 + 8) == v11 )
            *(_QWORD *)(v57 + 8) = v54;
          v58 = *(_QWORD **)(a1 + 936);
          if ( !*v58 )
          {
            v58[1] = 0;
            if ( !*(_DWORD *)(*(_QWORD *)(a1 + 936) + 48LL) )
              TcpTcbSetReassembly(a1, 0, v55, 0);
          }
          v59 = *((_DWORD *)v11 + 7) + *((_DWORD *)v11 + 6);
          *(_DWORD *)(*(_QWORD *)(a1 + 936) + 24LL) -= v59;
          _InterlockedAdd64(&ReassemblySize, -v59);
          v60 = (_QWORD *)v11[4];
          v61 = 0;
          if ( v60 )
          {
            do
            {
              v62 = (void *)v60[2];
              v63 = (_QWORD *)*v60;
              if ( v62 )
                ExFreePoolWithTag(v62, 0x42526354u);
              ExFreePoolWithTag(v60, 0x48526354u);
              ++v61;
              v60 = v63;
            }
            while ( v63 );
          }
          v64 = (char *)ReassemblyPool + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
          if ( !v64[176] )
            PplpLazyInitializeLookasideList(ReassemblyPool, v64 + 64);
          ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v64 + 64), v11);
          v24 = 0;
          *(_DWORD *)(*(_QWORD *)(a1 + 936) + 28LL) -= v61;
        }
        else
        {
          v24 = 0;
LABEL_27:
          v28 = *a6;
          v29 = *((_BYTE *)v11 + 16);
          if ( v15 < *((_DWORD *)v11 + 6) )
          {
            *a6 = v28 | v29 & 0xFE;
            TcpTcbReassemblyAdvanceHeader(a1, v11, v15);
            return v24;
          }
          v30 = 0;
          *a6 = v28 | v29;
          v31 = *(_QWORD *)(a1 + 936);
          v32 = *(__int64 **)(v31 + 16);
          v33 = v32;
          if ( v32 )
          {
            while ( v33 != v11 )
            {
              v30 = v33;
              v33 = (__int64 *)v33[1];
              if ( !v33 )
                goto LABEL_32;
            }
            if ( v30 )
              v30[1] = v11[1];
            else
              *(_QWORD *)(v31 + 16) = v32[1];
          }
LABEL_32:
          v34 = *(__int64 ***)(a1 + 936);
          v35 = 0;
          v36 = *v34;
          v37 = *v34;
          if ( !*v34 )
            goto LABEL_35;
          do
          {
            if ( v37 == v11 )
              break;
            v35 = v37;
            v37 = (__int64 *)*v37;
          }
          while ( v37 );
          if ( v35 )
            *v35 = *v11;
          else
LABEL_35:
            *v34 = (__int64 *)*v36;
          v38 = *(_QWORD *)(a1 + 936);
          if ( *(__int64 **)(v38 + 8) == v11 )
            *(_QWORD *)(v38 + 8) = v35;
          v39 = *(_QWORD **)(a1 + 936);
          if ( !*v39 )
          {
            v39[1] = 0;
            if ( !*(_DWORD *)(*(_QWORD *)(a1 + 936) + 48LL) )
              TcpTcbSetReassembly(a1, 0, v36, v12);
          }
          v40 = *((_DWORD *)v11 + 6) + *((_DWORD *)v11 + 7);
          *(_DWORD *)(*(_QWORD *)(a1 + 936) + 24LL) -= v40;
          _InterlockedAdd64(&ReassemblySize, -v40);
          v41 = (_QWORD *)v11[4];
          v42 = 0;
          if ( v41 )
          {
            do
            {
              v43 = (_QWORD *)*v41;
              ExFreePoolWithTag(v41, 0x48526354u);
              ++v42;
              v41 = v43;
            }
            while ( v43 );
          }
          v44 = (char *)ReassemblyPool + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
          if ( !v44[176] )
            PplpLazyInitializeLookasideList(ReassemblyPool, v44 + 64);
          ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v44 + 64), v11);
          *(_DWORD *)(*(_QWORD *)(a1 + 936) + 28LL) -= v42;
        }
        v65 = v84;
        --*(_WORD *)(*(_QWORD *)(a1 + 936) + 32LL);
        goto LABEL_69;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14003c600  mov     [rsp+arg_18], rbx
0x14003c605  mov     [rsp+arg_10], r8
0x14003c60a  mov     [rsp+arg_8], rdx
0x14003c60f  push    rbp
0x14003c610  push    rsi
0x14003c611  push    rdi
0x14003c612  push    r12
0x14003c614  push    r13
0x14003c616  push    r14
0x14003c618  push    r15
0x14003c61a  sub     rsp, 50h
0x14003c61e  mov     eax, [rcx+7Ch]
0x14003c621  mov     esi, r9d
0x14003c624  mov     [rsp+88h+var_48], 0
0x14003c62d  mov     rbx, rdx
0x14003c630  mov     rbp, rcx
0x14003c633  test    al, 10h
0x14003c635  jz      short loc_14003C676
0x14003c637  mov     dl, 1
0x14003c639  call    TcpTcbSetReassembly
0x14003c63e  mov     rax, [rbp+3A8h]
0x14003c645  mov     r15, [rax]
0x14003c648  test    r15, r15
0x14003c64b  jz      short loc_14003C676
0x14003c64d  mov     eax, [r15+14h]
0x14003c651  xor     r9d, r9d
0x14003c654  mov     edi, [rsp+88h+arg_20]
0x14003c65b  sub     eax, edi
0x14003c65d  mov     [rsp+88h+arg_0], r9d
0x14003c665  test    eax, eax
0x14003c667  jg      short loc_14003C676
0x14003c669  mov     r13, [rsp+88h+arg_28]
0x14003c671  test    r15, r15
0x14003c674  jnz     short loc_14003C691
0x14003c676  xor     eax, eax
0x14003c678  mov     rbx, [rsp+88h+arg_18]
0x14003c680  add     rsp, 50h
0x14003c684  pop     r15
0x14003c686  pop     r14
0x14003c688  pop     r13
0x14003c68a  pop     r12
0x14003c68c  pop     rdi
0x14003c68d  pop     rsi
0x14003c68e  pop     rbp
0x14003c68f  retn
0x14003c691  mov     r11d, [r15+14h]
0x14003c695  mov     eax, r11d
0x14003c698  sub     eax, edi
0x14003c69a  js      loc_14003CB40
0x14003c6a0  test    eax, eax
0x14003c6a2  jg      short loc_14003C676
0x14003c6a4  mov     eax, [rbp+7Ch]
0x14003c6a7  test    al, 40h
0x14003c6a9  jnz     loc_14003CD22
0x14003c6af  mov     r12d, [r15+18h]
0x14003c6b3  mov     rax, [r15]
0x14003c6b6  mov     [rsp+88h+var_50], rax
0x14003c6bb  test    r12d, r12d
0x14003c6be  jz      loc_14003CD4F
0x14003c6c4  mov     edi, [r15+1Ch]
0x14003c6c8  lea     r14, [rsp+88h+Mdl]
0x14003c6cd  mov     rsi, [r15+20h]
0x14003c6d1  add     edi, r12d
0x14003c6d4  mov     [rsp+88h+Mdl], r9
0x14003c6d9  nop     dword ptr [rax+00000000h]
0x14003c6e0  test    rsi, rsi
0x14003c6e3  jz      short loc_14003C736
0x14003c6e5  test    edi, edi
0x14003c6e7  jz      short loc_14003C736
0x14003c6e9  mov     ebx, [rsi+8]
0x14003c6ec  cmp     edi, ebx
0x14003c6ee  mov     rcx, [rsi+10h]; VirtualAddress
0x14003c6f2  cmovb   ebx, edi
0x14003c6f5  mov     [rsp+88h+Irp], r9; Irp
0x14003c6fa  mov     edx, ebx; Length
0x14003c6fc  xor     r9d, r9d; ChargeQuota
0x14003c6ff  xor     r8d, r8d; SecondaryBuffer
0x14003c702  call    cs:__imp_IoAllocateMdl
0x14003c709  nop     dword ptr [rax+rax+00h]
0x14003c70e  mov     [r14], rax
0x14003c711  test    rax, rax
0x14003c714  jz      loc_14003C90D
0x14003c71a  mov     rcx, rax; MemoryDescriptorList
0x14003c71d  sub     edi, ebx
0x14003c71f  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14003c726  nop     dword ptr [rax+rax+00h]
0x14003c72b  mov     r14, [r14]
0x14003c72e  xor     r9d, r9d
0x14003c731  mov     rsi, [rsi]
0x14003c734  jmp     short loc_14003C6E0
0x14003c736  mov     rbx, [rsp+88h+Mdl]
0x14003c73b  test    rbx, rbx
0x14003c73e  jz      loc_14003C93A
0x14003c744  mov     r9d, [r15+1Ch]
0x14003c748  lea     rcx, TcpTcbReassemblyFreeNetBufferList
0x14003c74f  mov     [rsp+88h+var_60], 1
0x14003c754  mov     r8, rbx
0x14003c757  xor     edx, edx
0x14003c759  mov     dword ptr [rsp+88h+Irp], r12d
0x14003c75e  call    cs:__imp_NetioAllocateAndReferenceNetBufferAndNetBufferList
0x14003c765  nop     dword ptr [rax+rax+00h]
0x14003c76a  mov     r8, rax
0x14003c76d  test    rax, rax
0x14003c770  jz      loc_14003CD40
0x14003c776  mov     edx, [rax+88h]
0x14003c77c  mov     esi, r12d
0x14003c77f  mov     eax, edx
0x14003c781  bts     edx, 1Fh
0x14003c785  btr     eax, 1Fh
0x14003c789  test    byte ptr [r15+10h], 8
0x14003c78e  cmovz   edx, eax
0x14003c791  mov     rax, [rsp+88h+arg_8]
0x14003c799  mov     [r8+88h], edx
0x14003c7a0  cmp     qword ptr [rax], 0
0x14003c7a4  jz      loc_14003CD38
0x14003c7aa  mov     rcx, [rsp+88h+arg_10]
0x14003c7b2  mov     rax, [rcx]
0x14003c7b5  test    rax, rax
0x14003c7b8  jz      short loc_14003C7BD
0x14003c7ba  mov     [rax], r8
0x14003c7bd  mov     [rcx], r8
0x14003c7c0  movzx   edx, byte ptr [r13+0]
0x14003c7c5  movzx   ecx, byte ptr [r15+10h]
0x14003c7ca  cmp     r12d, [r15+18h]
0x14003c7ce  jb      loc_14003CB15
0x14003c7d4  or      cl, dl
0x14003c7d6  xor     r8d, r8d
0x14003c7d9  mov     [r13+0], cl
0x14003c7dd  mov     rcx, [rbp+3A8h]
0x14003c7e4  mov     rdx, [rcx+10h]
0x14003c7e8  mov     rax, rdx
0x14003c7eb  test    rdx, rdx
0x14003c7ee  jz      short loc_14003C80A
0x14003c7f0  cmp     rax, r15
0x14003c7f3  jnz     loc_14003CAD2
0x14003c7f9  test    r8, r8
0x14003c7fc  jnz     loc_14003CB33
0x14003c802  mov     rax, [rdx+8]
0x14003c806  mov     [rcx+10h], rax
0x14003c80a  mov     rdx, [rbp+3A8h]
0x14003c811  xor     ecx, ecx
0x14003c813  mov     r8, [rdx]
0x14003c816  mov     rax, r8
0x14003c819  test    r8, r8
0x14003c81c  jz      short loc_14003C830
0x14003c81e  cmp     rax, r15
0x14003c821  jnz     loc_14003CCC4
0x14003c827  test    rcx, rcx
0x14003c82a  jnz     loc_14003CCA5
0x14003c830  mov     rax, [r8]
0x14003c833  mov     [rdx], rax
0x14003c836  mov     rax, [rbp+3A8h]
0x14003c83d  cmp     [rax+8], r15
0x14003c841  jnz     short loc_14003C847
0x14003c843  mov     [rax+8], rcx
0x14003c847  mov     rax, [rbp+3A8h]
0x14003c84e  cmp     qword ptr [rax], 0
0x14003c852  jnz     short loc_14003C873
0x14003c854  mov     qword ptr [rax+8], 0
0x14003c85c  mov     rax, [rbp+3A8h]
0x14003c863  cmp     dword ptr [rax+30h], 0
0x14003c867  jnz     short loc_14003C873
0x14003c869  xor     edx, edx
0x14003c86b  mov     rcx, rbp
0x14003c86e  call    TcpTcbSetReassembly
0x14003c873  mov     rax, [rbp+3A8h]
0x14003c87a  mov     edx, [r15+1Ch]
0x14003c87e  add     edx, [r15+18h]
0x14003c882  sub     [rax+18h], edx
0x14003c885  neg     edx
0x14003c887  movsxd  rax, edx
0x14003c88a  lock add cs:ReassemblySize, rax
0x14003c892  mov     rcx, [r15+20h]; P
0x14003c896  xor     edi, edi
0x14003c898  test    rcx, rcx
0x14003c89b  jz      short loc_14003C8BE
0x14003c89d  nop     dword ptr [rax]
0x14003c8a0  mov     rbx, [rcx]
0x14003c8a3  mov     edx, 48526354h; Tag
0x14003c8a8  call    cs:__imp_ExFreePoolWithTag
0x14003c8af  nop     dword ptr [rax+rax+00h]
0x14003c8b4  inc     edi
0x14003c8b6  mov     rcx, rbx
0x14003c8b9  test    rbx, rbx
0x14003c8bc  jnz     short loc_14003C8A0
0x14003c8be  mov     eax, gs:1A4h
0x14003c8c6  mov     rcx, cs:ReassemblyPool
0x14003c8cd  lea     ebx, [rax+1]
0x14003c8d0  shl     rbx, 7
0x14003c8d4  add     rbx, rcx
0x14003c8d7  movzx   eax, byte ptr [rbx+0B0h]
0x14003c8de  test    al, al
0x14003c8e0  jnz     short loc_14003C8EB
0x14003c8e2  lea     rdx, [rbx+40h]
0x14003c8e6  call    PplpLazyInitializeLookasideList
0x14003c8eb  mov     rdx, r15; Entry
0x14003c8ee  lea     rcx, [rbx+40h]; Lookaside
0x14003c8f2  call    cs:__imp_ExFreeToLookasideListEx
0x14003c8f9  nop     dword ptr [rax+rax+00h]
0x14003c8fe  mov     rax, [rbp+3A8h]
0x14003c905  sub     [rax+1Ch], edi
0x14003c908  jmp     loc_14003CA8A
0x14003c90d  mov     rcx, [rsp+88h+Mdl]; Mdl
0x14003c912  test    rcx, rcx
0x14003c915  jz      short loc_14003C937
0x14003c917  nop     word ptr [rax+rax+00000000h]
0x14003c920  mov     rbx, [rcx]
0x14003c923  call    cs:__imp_IoFreeMdl
0x14003c92a  nop     dword ptr [rax+rax+00h]
0x14003c92f  mov     rcx, rbx
0x14003c932  test    rbx, rbx
0x14003c935  jnz     short loc_14003C920
0x14003c937  xor     r9d, r9d
0x14003c93a  mov     rdx, [rbp+3A8h]
0x14003c941  mov     rcx, r9
0x14003c944  mov     r8, [rdx+10h]
0x14003c948  mov     rax, r8
0x14003c94b  test    r8, r8
0x14003c94e  jz      short loc_14003C96A
0x14003c950  cmp     rax, r15
0x14003c953  jnz     loc_14003CABD
0x14003c959  test    rcx, rcx
0x14003c95c  jnz     loc_14003CB08
0x14003c962  mov     rax, [r8+8]
0x14003c966  mov     [rdx+10h], rax
0x14003c96a  mov     rdx, [rbp+3A8h]
0x14003c971  mov     rcx, r9
0x14003c974  mov     r8, [rdx]
0x14003c977  mov     rax, r8
0x14003c97a  test    r8, r8
0x14003c97d  jz      short loc_14003C991
0x14003c97f  cmp     rax, r15
0x14003c982  jnz     loc_14003CCB0
0x14003c988  test    rcx, rcx
0x14003c98b  jnz     loc_14003CC83
0x14003c991  mov     rax, [r8]
0x14003c994  mov     [rdx], rax
0x14003c997  mov     rax, [rbp+3A8h]
0x14003c99e  cmp     [rax+8], r15
0x14003c9a2  jnz     short loc_14003C9A8
0x14003c9a4  mov     [rax+8], rcx
0x14003c9a8  mov     rax, [rbp+3A8h]
0x14003c9af  cmp     qword ptr [rax], 0
0x14003c9b3  jnz     short loc_14003C9D3
0x14003c9b5  mov     [rax+8], r9
0x14003c9b9  mov     rax, [rbp+3A8h]
0x14003c9c0  cmp     dword ptr [rax+30h], 0
0x14003c9c4  jnz     short loc_14003C9D3
0x14003c9c6  xor     edx, edx
0x14003c9c8  mov     rcx, rbp
0x14003c9cb  call    TcpTcbSetReassembly
0x14003c9d0  xor     r9d, r9d
0x14003c9d3  mov     rax, [rbp+3A8h]
0x14003c9da  mov     edx, [r15+18h]
0x14003c9de  add     edx, [r15+1Ch]
0x14003c9e2  sub     [rax+18h], edx
0x14003c9e5  neg     edx
0x14003c9e7  movsxd  rax, edx
0x14003c9ea  lock add cs:ReassemblySize, rax
0x14003c9f2  mov     rdi, [r15+20h]
0x14003c9f6  mov     ebx, r9d
0x14003c9f9  test    rdi, rdi
0x14003c9fc  jz      short loc_14003CA39
0x14003c9fe  mov     rcx, [rdi+10h]; P
0x14003ca02  mov     rsi, [rdi]
0x14003ca05  test    rcx, rcx
0x14003ca08  jz      short loc_14003CA1B
0x14003ca0a  mov     edx, 42526354h; Tag
0x14003ca0f  call    cs:__imp_ExFreePoolWithTag
0x14003ca16  nop     dword ptr [rax+rax+00h]
0x14003ca1b  mov     edx, 48526354h; Tag
0x14003ca20  mov     rcx, rdi; P
0x14003ca23  call    cs:__imp_ExFreePoolWithTag
0x14003ca2a  nop     dword ptr [rax+rax+00h]
0x14003ca2f  inc     ebx
0x14003ca31  mov     rdi, rsi
0x14003ca34  test    rsi, rsi
0x14003ca37  jnz     short loc_14003C9FE
0x14003ca39  mov     eax, gs:1A4h
0x14003ca41  mov     rcx, cs:ReassemblyPool
0x14003ca48  lea     edi, [rax+1]
0x14003ca4b  shl     rdi, 7
0x14003ca4f  add     rdi, rcx
0x14003ca52  movzx   eax, byte ptr [rdi+0B0h]
0x14003ca59  test    al, al
0x14003ca5b  jnz     short loc_14003CA66
0x14003ca5d  lea     rdx, [rdi+40h]
0x14003ca61  call    PplpLazyInitializeLookasideList
0x14003ca66  mov     rdx, r15; Entry
0x14003ca69  lea     rcx, [rdi+40h]; Lookaside
0x14003ca6d  call    cs:__imp_ExFreeToLookasideListEx
0x14003ca74  nop     dword ptr [rax+rax+00h]
0x14003ca79  mov     rax, [rbp+3A8h]
0x14003ca80  mov     esi, [rsp+88h+arg_0]
0x14003ca87  sub     [rax+1Ch], ebx
0x14003ca8a  mov     rax, [rbp+3A8h]
0x14003ca91  mov     ecx, 0FFFFh
0x14003ca96  mov     rbx, [rsp+88h+var_50]
0x14003ca9b  add     [rax+20h], cx
0x14003ca9f  mov     rax, [rbp+3A8h]
  ... truncated ...
```
