# TcpTcbReassemblyRetrieveSegments

- ea: `0x140090040`
- end: `0x14009079b`
- name: `TcpTcbReassemblyRetrieveSegments`
- size: `1883`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x14008ecd4`
- `0x14012dc94`

## callees

- `0x140053e04`
- `0x14008f1c8`
- `0x14008f290`
- `0x140090040`
- `0x1400907b0`
- `0x140090d88`
- `0x1400efd70`
- `0x1401521fc`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14009015f`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14009015f`
- `ntoskrnl!IoAllocateMdl` at `0x140090142`
- `ntoskrnl!IoAllocateMdl` at `0x140090142`
- `ntoskrnl!IoFreeMdl` at `0x140090363`
- `ntoskrnl!IoFreeMdl` at `0x140090363`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140090332`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400904ad`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140090332`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400904ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400902e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009044f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140090463`
- `ntoskrnl!ExFreePoolWithTag` at `0x140090691`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400906a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400902e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009044f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140090463`
- `ntoskrnl!ExFreePoolWithTag` at `0x140090691`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400906a5`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x1400905d9`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x1400905d9`
- `NETIO!NetioAllocateAndReferenceNetBufferAndNetBufferList` at `0x14009019e`
- `NETIO!NetioAllocateAndReferenceNetBufferAndNetBufferList` at `0x14009019e`

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
0x140090040  mov     [rsp+arg_18], rbx
0x140090045  mov     [rsp+arg_10], r8
0x14009004a  mov     [rsp+arg_8], rdx
0x14009004f  push    rbp
0x140090050  push    rsi
0x140090051  push    rdi
0x140090052  push    r12
0x140090054  push    r13
0x140090056  push    r14
0x140090058  push    r15
0x14009005a  sub     rsp, 50h
0x14009005e  mov     eax, [rcx+7Ch]
0x140090061  mov     esi, r9d
0x140090064  mov     [rsp+88h+var_48], 0
0x14009006d  mov     rbx, rdx
0x140090070  mov     rbp, rcx
0x140090073  test    al, 10h
0x140090075  jz      short loc_1400900B6
0x140090077  mov     dl, 1
0x140090079  call    TcpTcbSetReassembly
0x14009007e  mov     rax, [rbp+3A8h]
0x140090085  mov     r15, [rax]
0x140090088  test    r15, r15
0x14009008b  jz      short loc_1400900B6
0x14009008d  mov     eax, [r15+14h]
0x140090091  xor     r9d, r9d
0x140090094  mov     edi, [rsp+88h+arg_20]
0x14009009b  sub     eax, edi
0x14009009d  mov     [rsp+88h+arg_0], r9d
0x1400900a5  test    eax, eax
0x1400900a7  jg      short loc_1400900B6
0x1400900a9  mov     r13, [rsp+88h+arg_28]
0x1400900b1  test    r15, r15
0x1400900b4  jnz     short loc_1400900D1
0x1400900b6  xor     eax, eax
0x1400900b8  mov     rbx, [rsp+88h+arg_18]
0x1400900c0  add     rsp, 50h
0x1400900c4  pop     r15
0x1400900c6  pop     r14
0x1400900c8  pop     r13
0x1400900ca  pop     r12
0x1400900cc  pop     rdi
0x1400900cd  pop     rsi
0x1400900ce  pop     rbp
0x1400900cf  retn
0x1400900d1  mov     r11d, [r15+14h]
0x1400900d5  mov     eax, r11d
0x1400900d8  sub     eax, edi
0x1400900da  js      loc_140090580
0x1400900e0  test    eax, eax
0x1400900e2  jg      short loc_1400900B6
0x1400900e4  mov     eax, [rbp+7Ch]
0x1400900e7  test    al, 40h
0x1400900e9  jnz     loc_140090762
0x1400900ef  mov     r12d, [r15+18h]
0x1400900f3  mov     rax, [r15]
0x1400900f6  mov     [rsp+88h+var_50], rax
0x1400900fb  test    r12d, r12d
0x1400900fe  jz      loc_14009078F
0x140090104  mov     edi, [r15+1Ch]
0x140090108  lea     r14, [rsp+88h+Mdl]
0x14009010d  mov     rsi, [r15+20h]
0x140090111  add     edi, r12d
0x140090114  mov     [rsp+88h+Mdl], r9
0x140090119  nop     dword ptr [rax+00000000h]
0x140090120  test    rsi, rsi
0x140090123  jz      short loc_140090176
0x140090125  test    edi, edi
0x140090127  jz      short loc_140090176
0x140090129  mov     ebx, [rsi+8]
0x14009012c  cmp     edi, ebx
0x14009012e  mov     rcx, [rsi+10h]; VirtualAddress
0x140090132  cmovb   ebx, edi
0x140090135  mov     [rsp+88h+Irp], r9; Irp
0x14009013a  mov     edx, ebx; Length
0x14009013c  xor     r9d, r9d; ChargeQuota
0x14009013f  xor     r8d, r8d; SecondaryBuffer
0x140090142  call    cs:__imp_IoAllocateMdl
0x140090149  nop     dword ptr [rax+rax+00h]
0x14009014e  mov     [r14], rax
0x140090151  test    rax, rax
0x140090154  jz      loc_14009034D
0x14009015a  mov     rcx, rax; MemoryDescriptorList
0x14009015d  sub     edi, ebx
0x14009015f  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140090166  nop     dword ptr [rax+rax+00h]
0x14009016b  mov     r14, [r14]
0x14009016e  xor     r9d, r9d
0x140090171  mov     rsi, [rsi]
0x140090174  jmp     short loc_140090120
0x140090176  mov     rbx, [rsp+88h+Mdl]
0x14009017b  test    rbx, rbx
0x14009017e  jz      loc_14009037A
0x140090184  mov     r9d, [r15+1Ch]
0x140090188  lea     rcx, TcpTcbReassemblyFreeNetBufferList
0x14009018f  mov     [rsp+88h+var_60], 1
0x140090194  mov     r8, rbx
0x140090197  xor     edx, edx
0x140090199  mov     dword ptr [rsp+88h+Irp], r12d
0x14009019e  call    cs:__imp_NetioAllocateAndReferenceNetBufferAndNetBufferList
0x1400901a5  nop     dword ptr [rax+rax+00h]
0x1400901aa  mov     r8, rax
0x1400901ad  test    rax, rax
0x1400901b0  jz      loc_140090780
0x1400901b6  mov     edx, [rax+88h]
0x1400901bc  mov     esi, r12d
0x1400901bf  mov     eax, edx
0x1400901c1  bts     edx, 1Fh
0x1400901c5  btr     eax, 1Fh
0x1400901c9  test    byte ptr [r15+10h], 8
0x1400901ce  cmovz   edx, eax
0x1400901d1  mov     rax, [rsp+88h+arg_8]
0x1400901d9  mov     [r8+88h], edx
0x1400901e0  cmp     qword ptr [rax], 0
0x1400901e4  jz      loc_140090778
0x1400901ea  mov     rcx, [rsp+88h+arg_10]
0x1400901f2  mov     rax, [rcx]
0x1400901f5  test    rax, rax
0x1400901f8  jz      short loc_1400901FD
0x1400901fa  mov     [rax], r8
0x1400901fd  mov     [rcx], r8
0x140090200  movzx   edx, byte ptr [r13+0]
0x140090205  movzx   ecx, byte ptr [r15+10h]
0x14009020a  cmp     r12d, [r15+18h]
0x14009020e  jb      loc_140090555
0x140090214  or      cl, dl
0x140090216  xor     r8d, r8d
0x140090219  mov     [r13+0], cl
0x14009021d  mov     rcx, [rbp+3A8h]
0x140090224  mov     rdx, [rcx+10h]
0x140090228  mov     rax, rdx
0x14009022b  test    rdx, rdx
0x14009022e  jz      short loc_14009024A
0x140090230  cmp     rax, r15
0x140090233  jnz     loc_140090512
0x140090239  test    r8, r8
0x14009023c  jnz     loc_140090573
0x140090242  mov     rax, [rdx+8]
0x140090246  mov     [rcx+10h], rax
0x14009024a  mov     rdx, [rbp+3A8h]
0x140090251  xor     ecx, ecx
0x140090253  mov     r8, [rdx]
0x140090256  mov     rax, r8
0x140090259  test    r8, r8
0x14009025c  jz      short loc_140090270
0x14009025e  cmp     rax, r15
0x140090261  jnz     loc_140090704
0x140090267  test    rcx, rcx
0x14009026a  jnz     loc_1400906E5
0x140090270  mov     rax, [r8]
0x140090273  mov     [rdx], rax
0x140090276  mov     rax, [rbp+3A8h]
0x14009027d  cmp     [rax+8], r15
0x140090281  jnz     short loc_140090287
0x140090283  mov     [rax+8], rcx
0x140090287  mov     rax, [rbp+3A8h]
0x14009028e  cmp     qword ptr [rax], 0
0x140090292  jnz     short loc_1400902B3
0x140090294  mov     qword ptr [rax+8], 0
0x14009029c  mov     rax, [rbp+3A8h]
0x1400902a3  cmp     dword ptr [rax+30h], 0
0x1400902a7  jnz     short loc_1400902B3
0x1400902a9  xor     edx, edx
0x1400902ab  mov     rcx, rbp
0x1400902ae  call    TcpTcbSetReassembly
0x1400902b3  mov     rax, [rbp+3A8h]
0x1400902ba  mov     edx, [r15+1Ch]
0x1400902be  add     edx, [r15+18h]
0x1400902c2  sub     [rax+18h], edx
0x1400902c5  neg     edx
0x1400902c7  movsxd  rax, edx
0x1400902ca  lock add cs:ReassemblySize, rax
0x1400902d2  mov     rcx, [r15+20h]; P
0x1400902d6  xor     edi, edi
0x1400902d8  test    rcx, rcx
0x1400902db  jz      short loc_1400902FE
0x1400902dd  nop     dword ptr [rax]
0x1400902e0  mov     rbx, [rcx]
0x1400902e3  mov     edx, 48526354h; Tag
0x1400902e8  call    cs:__imp_ExFreePoolWithTag
0x1400902ef  nop     dword ptr [rax+rax+00h]
0x1400902f4  inc     edi
0x1400902f6  mov     rcx, rbx
0x1400902f9  test    rbx, rbx
0x1400902fc  jnz     short loc_1400902E0
0x1400902fe  mov     eax, gs:1A4h
0x140090306  mov     rcx, cs:ReassemblyPool
0x14009030d  lea     ebx, [rax+1]
0x140090310  shl     rbx, 7
0x140090314  add     rbx, rcx
0x140090317  movzx   eax, byte ptr [rbx+0B0h]
0x14009031e  test    al, al
0x140090320  jnz     short loc_14009032B
0x140090322  lea     rdx, [rbx+40h]
0x140090326  call    PplpLazyInitializeLookasideList
0x14009032b  mov     rdx, r15; Entry
0x14009032e  lea     rcx, [rbx+40h]; Lookaside
0x140090332  call    cs:__imp_ExFreeToLookasideListEx
0x140090339  nop     dword ptr [rax+rax+00h]
0x14009033e  mov     rax, [rbp+3A8h]
0x140090345  sub     [rax+1Ch], edi
0x140090348  jmp     loc_1400904CA
0x14009034d  mov     rcx, [rsp+88h+Mdl]; Mdl
0x140090352  test    rcx, rcx
0x140090355  jz      short loc_140090377
0x140090357  nop     word ptr [rax+rax+00000000h]
0x140090360  mov     rbx, [rcx]
0x140090363  call    cs:__imp_IoFreeMdl
0x14009036a  nop     dword ptr [rax+rax+00h]
0x14009036f  mov     rcx, rbx
0x140090372  test    rbx, rbx
0x140090375  jnz     short loc_140090360
0x140090377  xor     r9d, r9d
0x14009037a  mov     rdx, [rbp+3A8h]
0x140090381  mov     rcx, r9
0x140090384  mov     r8, [rdx+10h]
0x140090388  mov     rax, r8
0x14009038b  test    r8, r8
0x14009038e  jz      short loc_1400903AA
0x140090390  cmp     rax, r15
0x140090393  jnz     loc_1400904FD
0x140090399  test    rcx, rcx
0x14009039c  jnz     loc_140090548
0x1400903a2  mov     rax, [r8+8]
0x1400903a6  mov     [rdx+10h], rax
0x1400903aa  mov     rdx, [rbp+3A8h]
0x1400903b1  mov     rcx, r9
0x1400903b4  mov     r8, [rdx]
0x1400903b7  mov     rax, r8
0x1400903ba  test    r8, r8
0x1400903bd  jz      short loc_1400903D1
0x1400903bf  cmp     rax, r15
0x1400903c2  jnz     loc_1400906F0
0x1400903c8  test    rcx, rcx
0x1400903cb  jnz     loc_1400906C3
0x1400903d1  mov     rax, [r8]
0x1400903d4  mov     [rdx], rax
0x1400903d7  mov     rax, [rbp+3A8h]
0x1400903de  cmp     [rax+8], r15
0x1400903e2  jnz     short loc_1400903E8
0x1400903e4  mov     [rax+8], rcx
0x1400903e8  mov     rax, [rbp+3A8h]
0x1400903ef  cmp     qword ptr [rax], 0
0x1400903f3  jnz     short loc_140090413
0x1400903f5  mov     [rax+8], r9
0x1400903f9  mov     rax, [rbp+3A8h]
0x140090400  cmp     dword ptr [rax+30h], 0
0x140090404  jnz     short loc_140090413
0x140090406  xor     edx, edx
0x140090408  mov     rcx, rbp
0x14009040b  call    TcpTcbSetReassembly
0x140090410  xor     r9d, r9d
0x140090413  mov     rax, [rbp+3A8h]
0x14009041a  mov     edx, [r15+18h]
0x14009041e  add     edx, [r15+1Ch]
0x140090422  sub     [rax+18h], edx
0x140090425  neg     edx
0x140090427  movsxd  rax, edx
0x14009042a  lock add cs:ReassemblySize, rax
0x140090432  mov     rdi, [r15+20h]
0x140090436  mov     ebx, r9d
0x140090439  test    rdi, rdi
0x14009043c  jz      short loc_140090479
0x14009043e  mov     rcx, [rdi+10h]; P
0x140090442  mov     rsi, [rdi]
0x140090445  test    rcx, rcx
0x140090448  jz      short loc_14009045B
0x14009044a  mov     edx, 42526354h; Tag
0x14009044f  call    cs:__imp_ExFreePoolWithTag
0x140090456  nop     dword ptr [rax+rax+00h]
0x14009045b  mov     edx, 48526354h; Tag
0x140090460  mov     rcx, rdi; P
0x140090463  call    cs:__imp_ExFreePoolWithTag
0x14009046a  nop     dword ptr [rax+rax+00h]
0x14009046f  inc     ebx
0x140090471  mov     rdi, rsi
0x140090474  test    rsi, rsi
0x140090477  jnz     short loc_14009043E
0x140090479  mov     eax, gs:1A4h
0x140090481  mov     rcx, cs:ReassemblyPool
0x140090488  lea     edi, [rax+1]
0x14009048b  shl     rdi, 7
0x14009048f  add     rdi, rcx
0x140090492  movzx   eax, byte ptr [rdi+0B0h]
0x140090499  test    al, al
0x14009049b  jnz     short loc_1400904A6
0x14009049d  lea     rdx, [rdi+40h]
0x1400904a1  call    PplpLazyInitializeLookasideList
0x1400904a6  mov     rdx, r15; Entry
0x1400904a9  lea     rcx, [rdi+40h]; Lookaside
0x1400904ad  call    cs:__imp_ExFreeToLookasideListEx
0x1400904b4  nop     dword ptr [rax+rax+00h]
0x1400904b9  mov     rax, [rbp+3A8h]
0x1400904c0  mov     esi, [rsp+88h+arg_0]
0x1400904c7  sub     [rax+1Ch], ebx
0x1400904ca  mov     rax, [rbp+3A8h]
0x1400904d1  mov     ecx, 0FFFFh
0x1400904d6  mov     rbx, [rsp+88h+var_50]
0x1400904db  add     [rax+20h], cx
0x1400904df  mov     rax, [rbp+3A8h]
  ... truncated ...
```
