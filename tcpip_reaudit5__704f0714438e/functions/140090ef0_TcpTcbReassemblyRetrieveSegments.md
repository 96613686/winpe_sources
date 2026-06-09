# TcpTcbReassemblyRetrieveSegments

- ea: `0x140090ef0`
- end: `0x14009164b`
- name: `TcpTcbReassemblyRetrieveSegments`
- size: `1883`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x14008fb84`
- `0x14012ddd4`

## callees

- `0x1400540a4`
- `0x140090078`
- `0x140090140`
- `0x140090ef0`
- `0x140091660`
- `0x140091c38`
- `0x1400efc60`
- `0x14015233c`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14009100f`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14009100f`
- `ntoskrnl!IoAllocateMdl` at `0x140090ff2`
- `ntoskrnl!IoAllocateMdl` at `0x140090ff2`
- `ntoskrnl!IoFreeMdl` at `0x140091213`
- `ntoskrnl!IoFreeMdl` at `0x140091213`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400911e2`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14009135d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400911e2`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14009135d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140091198`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400912ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140091313`
- `ntoskrnl!ExFreePoolWithTag` at `0x140091541`
- `ntoskrnl!ExFreePoolWithTag` at `0x140091555`
- `ntoskrnl!ExFreePoolWithTag` at `0x140091198`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400912ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140091313`
- `ntoskrnl!ExFreePoolWithTag` at `0x140091541`
- `ntoskrnl!ExFreePoolWithTag` at `0x140091555`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140091489`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140091489`
- `NETIO!NetioAllocateAndReferenceNetBufferAndNetBufferList` at `0x14009104e`
- `NETIO!NetioAllocateAndReferenceNetBufferAndNetBufferList` at `0x14009104e`

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
0x140090ef0  mov     [rsp+arg_18], rbx
0x140090ef5  mov     [rsp+arg_10], r8
0x140090efa  mov     [rsp+arg_8], rdx
0x140090eff  push    rbp
0x140090f00  push    rsi
0x140090f01  push    rdi
0x140090f02  push    r12
0x140090f04  push    r13
0x140090f06  push    r14
0x140090f08  push    r15
0x140090f0a  sub     rsp, 50h
0x140090f0e  mov     eax, [rcx+7Ch]
0x140090f11  mov     esi, r9d
0x140090f14  mov     [rsp+88h+var_48], 0
0x140090f1d  mov     rbx, rdx
0x140090f20  mov     rbp, rcx
0x140090f23  test    al, 10h
0x140090f25  jz      short loc_140090F66
0x140090f27  mov     dl, 1
0x140090f29  call    TcpTcbSetReassembly
0x140090f2e  mov     rax, [rbp+3A8h]
0x140090f35  mov     r15, [rax]
0x140090f38  test    r15, r15
0x140090f3b  jz      short loc_140090F66
0x140090f3d  mov     eax, [r15+14h]
0x140090f41  xor     r9d, r9d
0x140090f44  mov     edi, [rsp+88h+arg_20]
0x140090f4b  sub     eax, edi
0x140090f4d  mov     [rsp+88h+arg_0], r9d
0x140090f55  test    eax, eax
0x140090f57  jg      short loc_140090F66
0x140090f59  mov     r13, [rsp+88h+arg_28]
0x140090f61  test    r15, r15
0x140090f64  jnz     short loc_140090F81
0x140090f66  xor     eax, eax
0x140090f68  mov     rbx, [rsp+88h+arg_18]
0x140090f70  add     rsp, 50h
0x140090f74  pop     r15
0x140090f76  pop     r14
0x140090f78  pop     r13
0x140090f7a  pop     r12
0x140090f7c  pop     rdi
0x140090f7d  pop     rsi
0x140090f7e  pop     rbp
0x140090f7f  retn
0x140090f81  mov     r11d, [r15+14h]
0x140090f85  mov     eax, r11d
0x140090f88  sub     eax, edi
0x140090f8a  js      loc_140091430
0x140090f90  test    eax, eax
0x140090f92  jg      short loc_140090F66
0x140090f94  mov     eax, [rbp+7Ch]
0x140090f97  test    al, 40h
0x140090f99  jnz     loc_140091612
0x140090f9f  mov     r12d, [r15+18h]
0x140090fa3  mov     rax, [r15]
0x140090fa6  mov     [rsp+88h+var_50], rax
0x140090fab  test    r12d, r12d
0x140090fae  jz      loc_14009163F
0x140090fb4  mov     edi, [r15+1Ch]
0x140090fb8  lea     r14, [rsp+88h+Mdl]
0x140090fbd  mov     rsi, [r15+20h]
0x140090fc1  add     edi, r12d
0x140090fc4  mov     [rsp+88h+Mdl], r9
0x140090fc9  nop     dword ptr [rax+00000000h]
0x140090fd0  test    rsi, rsi
0x140090fd3  jz      short loc_140091026
0x140090fd5  test    edi, edi
0x140090fd7  jz      short loc_140091026
0x140090fd9  mov     ebx, [rsi+8]
0x140090fdc  cmp     edi, ebx
0x140090fde  mov     rcx, [rsi+10h]; VirtualAddress
0x140090fe2  cmovb   ebx, edi
0x140090fe5  mov     [rsp+88h+Irp], r9; Irp
0x140090fea  mov     edx, ebx; Length
0x140090fec  xor     r9d, r9d; ChargeQuota
0x140090fef  xor     r8d, r8d; SecondaryBuffer
0x140090ff2  call    cs:__imp_IoAllocateMdl
0x140090ff9  nop     dword ptr [rax+rax+00h]
0x140090ffe  mov     [r14], rax
0x140091001  test    rax, rax
0x140091004  jz      loc_1400911FD
0x14009100a  mov     rcx, rax; MemoryDescriptorList
0x14009100d  sub     edi, ebx
0x14009100f  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140091016  nop     dword ptr [rax+rax+00h]
0x14009101b  mov     r14, [r14]
0x14009101e  xor     r9d, r9d
0x140091021  mov     rsi, [rsi]
0x140091024  jmp     short loc_140090FD0
0x140091026  mov     rbx, [rsp+88h+Mdl]
0x14009102b  test    rbx, rbx
0x14009102e  jz      loc_14009122A
0x140091034  mov     r9d, [r15+1Ch]
0x140091038  lea     rcx, TcpTcbReassemblyFreeNetBufferList
0x14009103f  mov     [rsp+88h+var_60], 1
0x140091044  mov     r8, rbx
0x140091047  xor     edx, edx
0x140091049  mov     dword ptr [rsp+88h+Irp], r12d
0x14009104e  call    cs:__imp_NetioAllocateAndReferenceNetBufferAndNetBufferList
0x140091055  nop     dword ptr [rax+rax+00h]
0x14009105a  mov     r8, rax
0x14009105d  test    rax, rax
0x140091060  jz      loc_140091630
0x140091066  mov     edx, [rax+88h]
0x14009106c  mov     esi, r12d
0x14009106f  mov     eax, edx
0x140091071  bts     edx, 1Fh
0x140091075  btr     eax, 1Fh
0x140091079  test    byte ptr [r15+10h], 8
0x14009107e  cmovz   edx, eax
0x140091081  mov     rax, [rsp+88h+arg_8]
0x140091089  mov     [r8+88h], edx
0x140091090  cmp     qword ptr [rax], 0
0x140091094  jz      loc_140091628
0x14009109a  mov     rcx, [rsp+88h+arg_10]
0x1400910a2  mov     rax, [rcx]
0x1400910a5  test    rax, rax
0x1400910a8  jz      short loc_1400910AD
0x1400910aa  mov     [rax], r8
0x1400910ad  mov     [rcx], r8
0x1400910b0  movzx   edx, byte ptr [r13+0]
0x1400910b5  movzx   ecx, byte ptr [r15+10h]
0x1400910ba  cmp     r12d, [r15+18h]
0x1400910be  jb      loc_140091405
0x1400910c4  or      cl, dl
0x1400910c6  xor     r8d, r8d
0x1400910c9  mov     [r13+0], cl
0x1400910cd  mov     rcx, [rbp+3A8h]
0x1400910d4  mov     rdx, [rcx+10h]
0x1400910d8  mov     rax, rdx
0x1400910db  test    rdx, rdx
0x1400910de  jz      short loc_1400910FA
0x1400910e0  cmp     rax, r15
0x1400910e3  jnz     loc_1400913C2
0x1400910e9  test    r8, r8
0x1400910ec  jnz     loc_140091423
0x1400910f2  mov     rax, [rdx+8]
0x1400910f6  mov     [rcx+10h], rax
0x1400910fa  mov     rdx, [rbp+3A8h]
0x140091101  xor     ecx, ecx
0x140091103  mov     r8, [rdx]
0x140091106  mov     rax, r8
0x140091109  test    r8, r8
0x14009110c  jz      short loc_140091120
0x14009110e  cmp     rax, r15
0x140091111  jnz     loc_1400915B4
0x140091117  test    rcx, rcx
0x14009111a  jnz     loc_140091595
0x140091120  mov     rax, [r8]
0x140091123  mov     [rdx], rax
0x140091126  mov     rax, [rbp+3A8h]
0x14009112d  cmp     [rax+8], r15
0x140091131  jnz     short loc_140091137
0x140091133  mov     [rax+8], rcx
0x140091137  mov     rax, [rbp+3A8h]
0x14009113e  cmp     qword ptr [rax], 0
0x140091142  jnz     short loc_140091163
0x140091144  mov     qword ptr [rax+8], 0
0x14009114c  mov     rax, [rbp+3A8h]
0x140091153  cmp     dword ptr [rax+30h], 0
0x140091157  jnz     short loc_140091163
0x140091159  xor     edx, edx
0x14009115b  mov     rcx, rbp
0x14009115e  call    TcpTcbSetReassembly
0x140091163  mov     rax, [rbp+3A8h]
0x14009116a  mov     edx, [r15+1Ch]
0x14009116e  add     edx, [r15+18h]
0x140091172  sub     [rax+18h], edx
0x140091175  neg     edx
0x140091177  movsxd  rax, edx
0x14009117a  lock add cs:ReassemblySize, rax
0x140091182  mov     rcx, [r15+20h]; P
0x140091186  xor     edi, edi
0x140091188  test    rcx, rcx
0x14009118b  jz      short loc_1400911AE
0x14009118d  nop     dword ptr [rax]
0x140091190  mov     rbx, [rcx]
0x140091193  mov     edx, 48526354h; Tag
0x140091198  call    cs:__imp_ExFreePoolWithTag
0x14009119f  nop     dword ptr [rax+rax+00h]
0x1400911a4  inc     edi
0x1400911a6  mov     rcx, rbx
0x1400911a9  test    rbx, rbx
0x1400911ac  jnz     short loc_140091190
0x1400911ae  mov     eax, gs:1A4h
0x1400911b6  mov     rcx, cs:ReassemblyPool
0x1400911bd  lea     ebx, [rax+1]
0x1400911c0  shl     rbx, 7
0x1400911c4  add     rbx, rcx
0x1400911c7  movzx   eax, byte ptr [rbx+0B0h]
0x1400911ce  test    al, al
0x1400911d0  jnz     short loc_1400911DB
0x1400911d2  lea     rdx, [rbx+40h]
0x1400911d6  call    PplpLazyInitializeLookasideList
0x1400911db  mov     rdx, r15; Entry
0x1400911de  lea     rcx, [rbx+40h]; Lookaside
0x1400911e2  call    cs:__imp_ExFreeToLookasideListEx
0x1400911e9  nop     dword ptr [rax+rax+00h]
0x1400911ee  mov     rax, [rbp+3A8h]
0x1400911f5  sub     [rax+1Ch], edi
0x1400911f8  jmp     loc_14009137A
0x1400911fd  mov     rcx, [rsp+88h+Mdl]; Mdl
0x140091202  test    rcx, rcx
0x140091205  jz      short loc_140091227
0x140091207  nop     word ptr [rax+rax+00000000h]
0x140091210  mov     rbx, [rcx]
0x140091213  call    cs:__imp_IoFreeMdl
0x14009121a  nop     dword ptr [rax+rax+00h]
0x14009121f  mov     rcx, rbx
0x140091222  test    rbx, rbx
0x140091225  jnz     short loc_140091210
0x140091227  xor     r9d, r9d
0x14009122a  mov     rdx, [rbp+3A8h]
0x140091231  mov     rcx, r9
0x140091234  mov     r8, [rdx+10h]
0x140091238  mov     rax, r8
0x14009123b  test    r8, r8
0x14009123e  jz      short loc_14009125A
0x140091240  cmp     rax, r15
0x140091243  jnz     loc_1400913AD
0x140091249  test    rcx, rcx
0x14009124c  jnz     loc_1400913F8
0x140091252  mov     rax, [r8+8]
0x140091256  mov     [rdx+10h], rax
0x14009125a  mov     rdx, [rbp+3A8h]
0x140091261  mov     rcx, r9
0x140091264  mov     r8, [rdx]
0x140091267  mov     rax, r8
0x14009126a  test    r8, r8
0x14009126d  jz      short loc_140091281
0x14009126f  cmp     rax, r15
0x140091272  jnz     loc_1400915A0
0x140091278  test    rcx, rcx
0x14009127b  jnz     loc_140091573
0x140091281  mov     rax, [r8]
0x140091284  mov     [rdx], rax
0x140091287  mov     rax, [rbp+3A8h]
0x14009128e  cmp     [rax+8], r15
0x140091292  jnz     short loc_140091298
0x140091294  mov     [rax+8], rcx
0x140091298  mov     rax, [rbp+3A8h]
0x14009129f  cmp     qword ptr [rax], 0
0x1400912a3  jnz     short loc_1400912C3
0x1400912a5  mov     [rax+8], r9
0x1400912a9  mov     rax, [rbp+3A8h]
0x1400912b0  cmp     dword ptr [rax+30h], 0
0x1400912b4  jnz     short loc_1400912C3
0x1400912b6  xor     edx, edx
0x1400912b8  mov     rcx, rbp
0x1400912bb  call    TcpTcbSetReassembly
0x1400912c0  xor     r9d, r9d
0x1400912c3  mov     rax, [rbp+3A8h]
0x1400912ca  mov     edx, [r15+18h]
0x1400912ce  add     edx, [r15+1Ch]
0x1400912d2  sub     [rax+18h], edx
0x1400912d5  neg     edx
0x1400912d7  movsxd  rax, edx
0x1400912da  lock add cs:ReassemblySize, rax
0x1400912e2  mov     rdi, [r15+20h]
0x1400912e6  mov     ebx, r9d
0x1400912e9  test    rdi, rdi
0x1400912ec  jz      short loc_140091329
0x1400912ee  mov     rcx, [rdi+10h]; P
0x1400912f2  mov     rsi, [rdi]
0x1400912f5  test    rcx, rcx
0x1400912f8  jz      short loc_14009130B
0x1400912fa  mov     edx, 42526354h; Tag
0x1400912ff  call    cs:__imp_ExFreePoolWithTag
0x140091306  nop     dword ptr [rax+rax+00h]
0x14009130b  mov     edx, 48526354h; Tag
0x140091310  mov     rcx, rdi; P
0x140091313  call    cs:__imp_ExFreePoolWithTag
0x14009131a  nop     dword ptr [rax+rax+00h]
0x14009131f  inc     ebx
0x140091321  mov     rdi, rsi
0x140091324  test    rsi, rsi
0x140091327  jnz     short loc_1400912EE
0x140091329  mov     eax, gs:1A4h
0x140091331  mov     rcx, cs:ReassemblyPool
0x140091338  lea     edi, [rax+1]
0x14009133b  shl     rdi, 7
0x14009133f  add     rdi, rcx
0x140091342  movzx   eax, byte ptr [rdi+0B0h]
0x140091349  test    al, al
0x14009134b  jnz     short loc_140091356
0x14009134d  lea     rdx, [rdi+40h]
0x140091351  call    PplpLazyInitializeLookasideList
0x140091356  mov     rdx, r15; Entry
0x140091359  lea     rcx, [rdi+40h]; Lookaside
0x14009135d  call    cs:__imp_ExFreeToLookasideListEx
0x140091364  nop     dword ptr [rax+rax+00h]
0x140091369  mov     rax, [rbp+3A8h]
0x140091370  mov     esi, [rsp+88h+arg_0]
0x140091377  sub     [rax+1Ch], ebx
0x14009137a  mov     rax, [rbp+3A8h]
0x140091381  mov     ecx, 0FFFFh
0x140091386  mov     rbx, [rsp+88h+var_50]
0x14009138b  add     [rax+20h], cx
0x14009138f  mov     rax, [rbp+3A8h]
  ... truncated ...
```
