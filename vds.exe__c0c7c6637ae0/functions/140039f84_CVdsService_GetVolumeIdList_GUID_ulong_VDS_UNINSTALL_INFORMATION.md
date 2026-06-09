# CVdsService::GetVolumeIdList(_GUID *,ulong,_VDS_UNINSTALL_INFORMATION *)

- ea: `0x140039f84`
- end: `0x14003a2d6`
- name: `?GetVolumeIdList@CVdsService@@SAJPEAU_GUID@@KPEAU_VDS_UNINSTALL_INFORMATION@@@Z`
- size: `850`
- prototype: `__int64 __fastcall(struct _GUID *, unsigned int, struct _VDS_UNINSTALL_INFORMATION *)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x140022400`
- `0x140028768`
- `0x140029cf4`

## callees

- `0x14002de26`
- `0x140039f84`
- `0x140052e46`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003a007`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003a15c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003a21b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003a26f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003a29a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003a007`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003a15c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003a21b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003a26f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003a29a`
- `vdsutil!VdsHeapAlloc` at `0x14003a018`
- `vdsutil!VdsHeapAlloc` at `0x14003a16d`
- `vdsutil!VdsHeapAlloc` at `0x14003a018`
- `vdsutil!VdsHeapAlloc` at `0x14003a16d`
- `vdsutil!VdsHeapFree` at `0x14003a229`
- `vdsutil!VdsHeapFree` at `0x14003a27d`
- `vdsutil!VdsHeapFree` at `0x14003a2a8`
- `vdsutil!VdsHeapFree` at `0x14003a229`
- `vdsutil!VdsHeapFree` at `0x14003a27d`
- `vdsutil!VdsHeapFree` at `0x14003a2a8`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003a044`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003a044`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003a05d`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003a05d`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14003a08a`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14003a08a`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14003a105`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14003a105`
- `vdsutil!VdsTraceW` at `0x140039fba`
- `vdsutil!VdsTraceW` at `0x140039ff5`
- `vdsutil!VdsTraceW` at `0x14003a1e3`
- `vdsutil!VdsTraceW` at `0x14003a20c`
- `vdsutil!VdsTraceW` at `0x14003a2bd`
- `vdsutil!VdsTraceW` at `0x140039fba`
- `vdsutil!VdsTraceW` at `0x140039ff5`
- `vdsutil!VdsTraceW` at `0x14003a1e3`
- `vdsutil!VdsTraceW` at `0x14003a20c`
- `vdsutil!VdsTraceW` at `0x14003a2bd`

## string_xrefs

- `0x140039fa8`: `CVdsService::GetVolumeIdList`
- `0x14003a1fb`: `CVdsService::GetVolumeIdList, 1, pDiskIdArray=%p, ulDiskCount=%lu, pUninstallInfo=%p`
- `0x140039fec`: `CVdsService::GetVolumeIdList, 2`
- `0x14003a02b`: `CVdsService::GetVolumeIdList, 3`
- `0x14003a11f`: `CVdsService::GetVolumeIdList, 4, %lX`
- `0x14003a110`: `CVdsService::GetVolumeIdList, 5, %lX`
- `0x14003a184`: `CVdsService::GetVolumeIdList, 6`
- `0x14003a1d7`: `CVdsService::GetVolumeIdList, 7, %lX`
- `0x14003a2b1`: `EXIT CVdsService::GetVolumeIdList, hr=%lX`

## pseudocode

```c
__int64 __fastcall CVdsService::GetVolumeIdList(
        struct _GUID *a1,
        unsigned int a2,
        struct _VDS_UNINSTALL_INFORMATION *a3)
{
  _DWORD *v3; // r14
  unsigned __int64 v7; // rsi
  unsigned int v8; // edi
  __int64 v9; // rdx
  _DWORD *v10; // r8
  __int64 v11; // r9
  HANDLE v12; // rax
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 (__fastcall ***EntryPointer)(void *, GUID *, __int64 *); // rax
  int v16; // eax
  const wchar_t *v17; // rdx
  unsigned int v18; // ecx
  __int64 v19; // rbx
  HANDLE v20; // rax
  __int64 v21; // rax
  char *v22; // r13
  unsigned int *v23; // rbx
  unsigned int i; // r12d
  const void *v25; // rdx
  __int64 v26; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v28; // r12d
  _DWORD *j; // r15
  __int64 v30; // rbx
  HANDLE v31; // rax
  HANDLE v32; // rax
  __int128 Buf1; // [rsp+30h] [rbp-38h] BYREF
  __int128 Buf2; // [rsp+40h] [rbp-28h] BYREF
  char v36[24]; // [rsp+50h] [rbp-18h] BYREF
  __int64 v37; // [rsp+B0h] [rbp+48h] BYREF

  v3 = 0;
  v37 = 0;
  Buf1 = 0;
  VdsTraceW(2, L"CVdsService::GetVolumeIdList");
  if ( !a1 || !a2 || !a3 )
  {
    v7 = 0;
    v8 = -2147024809;
    VdsTraceW(0, L"CVdsService::GetVolumeIdList, 1, pDiskIdArray=%p, ulDiskCount=%lu, pUninstallInfo=%p", a1, a2, a3);
    goto LABEL_36;
  }
  v7 = dword_14009B170;
  if ( !dword_14009B170 )
  {
    v8 = -2147212032;
    VdsTraceW(0, L"CVdsService::GetVolumeIdList, 2");
LABEL_36:
    v26 = *((_QWORD *)a3 + 1);
    if ( v26 )
    {
      ProcessHeap = GetProcessHeap();
      VdsHeapFree(ProcessHeap, 0, v26);
      *((_QWORD *)a3 + 1) = 0;
      *(_DWORD *)a3 = 0;
    }
    goto LABEL_38;
  }
  v12 = GetProcessHeap();
  v13 = VdsHeapAlloc(v12, 8, 16 * v7);
  v3 = (_DWORD *)v13;
  if ( !v13 )
  {
    v8 = -2147024882;
    VdsTraceW(0, L"CVdsService::GetVolumeIdList, 3");
    goto LABEL_36;
  }
  v8 = 0;
  v14 = v13;
  for ( Buf1 = *(_OWORD *)CRtlList::Begin(CVdsService::m_lstSoftwareProviders, &Buf2);
        ;
        CRtlListIter::Next((CRtlListIter *)&Buf1) )
  {
    Buf2 = *(_OWORD *)CRtlList::End(CVdsService::m_lstSoftwareProviders, v36);
    if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
      break;
    EntryPointer = (__int64 (__fastcall ***)(void *, GUID *, __int64 *))CRtlListIter::GetEntryPointer((CRtlListIter *)&Buf1);
    v16 = (**EntryPointer)(EntryPointer, &IID_IVdsSwProviderPrivateUninstall, &v37);
    v8 = v16;
    if ( v16 < 0 )
    {
      VdsTraceW(0, L"CVdsService::GetVolumeIdList, 4, %lX", (unsigned int)v16);
      goto LABEL_36;
    }
    v8 = (*(__int64 (__fastcall **)(__int64, struct _GUID *, _QWORD, __int64))(*(_QWORD *)v37 + 24LL))(v37, a1, a2, v14);
    if ( (int)(v8 + 0x80000000) >= 0 && v8 != -2147212283 )
    {
      v17 = L"CVdsService::GetVolumeIdList, 5, %lX";
LABEL_31:
      VdsTraceW(0, v17, v8);
      goto LABEL_36;
    }
    if ( v37 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      v37 = 0;
    }
    v14 += 16;
  }
  v18 = 0;
  v11 = 0;
  v10 = v3;
  if ( v7 )
  {
    do
    {
      v18 += *v10;
      v11 = (unsigned int)(v11 + 1);
      v10 += 4;
    }
    while ( (unsigned int)v11 < v7 );
    if ( v18 )
    {
      v19 = 16LL * v18;
      v20 = GetProcessHeap();
      v21 = VdsHeapAlloc(v20, 8, v19);
      *((_QWORD *)a3 + 1) = v21;
      v22 = (char *)v21;
      if ( !v21 )
      {
        v8 = -2147024882;
        VdsTraceW(0, L"CVdsService::GetVolumeIdList, 6");
        goto LABEL_36;
      }
      v23 = v3;
      for ( i = 0; i < v7; ++i )
      {
        if ( *v23 )
        {
          v25 = (const void *)*((_QWORD *)v23 + 1);
          if ( !v25 )
          {
            v8 = -2147212216;
            v17 = L"CVdsService::GetVolumeIdList, 7, %lX";
            goto LABEL_31;
          }
          memcpy_0(v22, v25, 16LL * *v23);
          *(_DWORD *)a3 += *v23;
          v22 += 16 * *v23;
        }
        v23 += 4;
      }
    }
  }
  if ( (v8 & 0x80000000) != 0 )
    goto LABEL_36;
LABEL_38:
  if ( v37 )
  {
    (*(void (__fastcall **)(__int64, __int64, _DWORD *, __int64))(*(_QWORD *)v37 + 16LL))(v37, v9, v10, v11);
    v37 = 0;
  }
  if ( v3 )
  {
    v28 = 0;
    for ( j = v3; v28 < v7; j += 4 )
    {
      v30 = *((_QWORD *)j + 1);
      v31 = GetProcessHeap();
      VdsHeapFree(v31, 0, v30);
      ++v28;
      *((_QWORD *)j + 1) = 0;
    }
  }
  v32 = GetProcessHeap();
  VdsHeapFree(v32, 0, v3);
  VdsTraceW(2, L"EXIT CVdsService::GetVolumeIdList, hr=%lX", v8);
  return v8;
}

```

## disassembly

```asm
0x140039f84  push    rbp
0x140039f86  push    rbx
0x140039f87  push    rsi
0x140039f88  push    rdi
0x140039f89  push    r12
0x140039f8b  push    r13
0x140039f8d  push    r14
0x140039f8f  push    r15
0x140039f91  mov     rbp, rsp
0x140039f94  sub     rsp, 68h
0x140039f98  xor     r14d, r14d
0x140039f9b  mov     r12d, edx
0x140039f9e  mov     r13, rcx
0x140039fa1  mov     [rbp+arg_0], r14
0x140039fa5  xorps   xmm0, xmm0
0x140039fa8  lea     rdx, aCvdsserviceGet_92; "CVdsService::GetVolumeIdList"
0x140039faf  mov     r15, r8
0x140039fb2  lea     ecx, [r14+2]
0x140039fb6  movups  [rbp+Buf1], xmm0
0x140039fba  call    cs:__imp_VdsTraceW
0x140039fc0  test    r13, r13
0x140039fc3  jz      loc_14003A1F1
0x140039fc9  test    r12d, r12d
0x140039fcc  jz      loc_14003A1F1
0x140039fd2  test    r15, r15
0x140039fd5  jz      loc_14003A1F1
0x140039fdb  movsxd  rsi, cs:dword_14009B170
0x140039fe2  test    rsi, rsi
0x140039fe5  jnz     short loc_14003A000
0x140039fe7  mov     edi, 80042500h
0x140039fec  lea     rdx, aCvdsserviceGet_125; "CVdsService::GetVolumeIdList, 2"
0x140039ff3  xor     ecx, ecx
0x140039ff5  call    cs:__imp_VdsTraceW
0x140039ffb  jmp     loc_14003A212
0x14003a000  mov     rbx, rsi
0x14003a003  shl     rbx, 4
0x14003a007  call    cs:__imp_GetProcessHeap
0x14003a00d  mov     r8, rbx
0x14003a010  mov     edx, 8
0x14003a015  mov     rcx, rax
0x14003a018  call    cs:__imp_VdsHeapAlloc
0x14003a01e  mov     r14, rax
0x14003a021  test    rax, rax
0x14003a024  jnz     short loc_14003A034
0x14003a026  mov     edi, 8007000Eh
0x14003a02b  lea     rdx, aCvdsserviceGet_50; "CVdsService::GetVolumeIdList, 3"
0x14003a032  jmp     short loc_140039FF3
0x14003a034  xor     edi, edi
0x14003a036  lea     rdx, [rbp+Buf2]
0x14003a03a  lea     rcx, ?m_lstSoftwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstSoftwareProviders
0x14003a041  mov     rbx, r14
0x14003a044  call    cs:__imp_?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::Begin(void)
0x14003a04a  movups  xmm0, xmmword ptr [rax]
0x14003a04d  movdqu  [rbp+Buf1], xmm0
0x14003a052  lea     rdx, [rbp+var_18]
0x14003a056  lea     rcx, ?m_lstSoftwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstSoftwareProviders
0x14003a05d  call    cs:__imp_?End@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::End(void)
0x14003a063  mov     r8d, 10h; Size
0x14003a069  lea     rdx, [rbp+Buf2]; Buf2
0x14003a06d  lea     rcx, [rbp+Buf1]; Buf1
0x14003a071  movups  xmm0, xmmword ptr [rax]
0x14003a074  movdqu  [rbp+Buf2], xmm0
0x14003a079  call    memcmp_0
0x14003a07e  test    eax, eax
0x14003a080  jz      loc_14003A12B
0x14003a086  lea     rcx, [rbp+Buf1]
0x14003a08a  call    cs:__imp_?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ; CRtlListIter::GetEntryPointer(void)
0x14003a090  mov     r9, rax
0x14003a093  lea     r8, [rbp+arg_0]
0x14003a097  lea     rdx, IID_IVdsSwProviderPrivateUninstall
0x14003a09e  mov     rcx, [rax]
0x14003a0a1  mov     rax, [rcx]
0x14003a0a4  mov     rcx, r9
0x14003a0a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a0ac  mov     edi, eax
0x14003a0ae  test    eax, eax
0x14003a0b0  js      short loc_14003A11C
0x14003a0b2  mov     rcx, [rbp+arg_0]
0x14003a0b6  mov     r9, rbx
0x14003a0b9  mov     r8d, r12d
0x14003a0bc  mov     rdx, r13
0x14003a0bf  mov     rax, [rcx]
0x14003a0c2  mov     rax, [rax+18h]
0x14003a0c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a0cb  mov     ecx, 80000000h
0x14003a0d0  mov     edi, eax
0x14003a0d2  add     eax, ecx
0x14003a0d4  test    ecx, eax
0x14003a0d6  jnz     short loc_14003A0E0
0x14003a0d8  cmp     edi, 80042405h
0x14003a0de  jnz     short loc_14003A110
0x14003a0e0  mov     rcx, [rbp+arg_0]
0x14003a0e4  test    rcx, rcx
0x14003a0e7  jz      short loc_14003A0FD
0x14003a0e9  mov     rax, [rcx]
0x14003a0ec  mov     rax, [rax+10h]
0x14003a0f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a0f5  mov     [rbp+arg_0], 0
0x14003a0fd  add     rbx, 10h
0x14003a101  lea     rcx, [rbp+Buf1]
0x14003a105  call    cs:__imp_?Next@CRtlListIter@@QEAAAEAV1@XZ; CRtlListIter::Next(void)
0x14003a10b  jmp     loc_14003A052
0x14003a110  lea     rdx, aCvdsserviceGet_17; "CVdsService::GetVolumeIdList, 5, %lX"
0x14003a117  jmp     loc_14003A1DE
0x14003a11c  mov     r8d, eax
0x14003a11f  lea     rdx, aCvdsserviceGet_58; "CVdsService::GetVolumeIdList, 4, %lX"
0x14003a126  jmp     loc_14003A1E1
0x14003a12b  xor     ecx, ecx
0x14003a12d  xor     r9d, r9d
0x14003a130  mov     r8, r14
0x14003a133  test    rsi, rsi
0x14003a136  jz      loc_14003A1EB
0x14003a13c  add     ecx, [r8]
0x14003a13f  inc     r9d
0x14003a142  mov     eax, r9d
0x14003a145  lea     r8, [r8+10h]
0x14003a149  cmp     rax, rsi
0x14003a14c  jb      short loc_14003A13C
0x14003a14e  test    ecx, ecx
0x14003a150  jz      loc_14003A1EB
0x14003a156  mov     ebx, ecx
0x14003a158  shl     rbx, 4
0x14003a15c  call    cs:__imp_GetProcessHeap
0x14003a162  mov     r8, rbx
0x14003a165  mov     edx, 8
0x14003a16a  mov     rcx, rax
0x14003a16d  call    cs:__imp_VdsHeapAlloc
0x14003a173  mov     [r15+8], rax
0x14003a177  mov     r13, rax
0x14003a17a  test    rax, rax
0x14003a17d  jnz     short loc_14003A190
0x14003a17f  mov     edi, 8007000Eh
0x14003a184  lea     rdx, aCvdsserviceGet_6; "CVdsService::GetVolumeIdList, 6"
0x14003a18b  jmp     loc_140039FF3
0x14003a190  mov     rbx, r14
0x14003a193  xor     r12d, r12d
0x14003a196  mov     eax, r12d
0x14003a199  cmp     rax, rsi
0x14003a19c  jnb     short loc_14003A1EB
0x14003a19e  cmp     dword ptr [rbx], 0
0x14003a1a1  jz      short loc_14003A1C9
0x14003a1a3  mov     rdx, [rbx+8]; Src
0x14003a1a7  test    rdx, rdx
0x14003a1aa  jz      short loc_14003A1D2
0x14003a1ac  mov     r8d, [rbx]
0x14003a1af  mov     rcx, r13; void *
0x14003a1b2  shl     r8, 4; Size
0x14003a1b6  call    memcpy_0
0x14003a1bb  mov     eax, [rbx]
0x14003a1bd  add     [r15], eax
0x14003a1c0  mov     eax, [rbx]
0x14003a1c2  shl     rax, 4
0x14003a1c6  add     r13, rax
0x14003a1c9  inc     r12d
0x14003a1cc  add     rbx, 10h
0x14003a1d0  jmp     short loc_14003A196
0x14003a1d2  mov     edi, 80042448h
0x14003a1d7  lea     rdx, aCvdsserviceGet_32; "CVdsService::GetVolumeIdList, 7, %lX"
0x14003a1de  mov     r8d, edi
0x14003a1e1  xor     ecx, ecx
0x14003a1e3  call    cs:__imp_VdsTraceW
0x14003a1e9  jmp     short loc_14003A212
0x14003a1eb  test    edi, edi
0x14003a1ed  jns     short loc_14003A23E
0x14003a1ef  jmp     short loc_14003A212
0x14003a1f1  xor     esi, esi
0x14003a1f3  mov     [rsp+68h+var_48], r15
0x14003a1f8  mov     r9d, r12d
0x14003a1fb  lea     rdx, aCvdsserviceGet_94; "CVdsService::GetVolumeIdList, 1, pDiskI"...
0x14003a202  mov     r8, r13
0x14003a205  xor     ecx, ecx
0x14003a207  mov     edi, 80070057h
0x14003a20c  call    cs:__imp_VdsTraceW
0x14003a212  mov     rbx, [r15+8]
0x14003a216  test    rbx, rbx
0x14003a219  jz      short loc_14003A23E
0x14003a21b  call    cs:__imp_GetProcessHeap
0x14003a221  mov     r8, rbx
0x14003a224  xor     edx, edx
0x14003a226  mov     rcx, rax
0x14003a229  call    cs:__imp_VdsHeapFree
0x14003a22f  mov     qword ptr [r15+8], 0
0x14003a237  mov     dword ptr [r15], 0
0x14003a23e  mov     rcx, [rbp+arg_0]
0x14003a242  test    rcx, rcx
0x14003a245  jz      short loc_14003A25B
0x14003a247  mov     rax, [rcx]
0x14003a24a  mov     rax, [rax+10h]
0x14003a24e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a253  mov     [rbp+arg_0], 0
0x14003a25b  test    r14, r14
0x14003a25e  jz      short loc_14003A29A
0x14003a260  xor     r12d, r12d
0x14003a263  mov     r15, r14
0x14003a266  test    rsi, rsi
0x14003a269  jz      short loc_14003A29A
0x14003a26b  mov     rbx, [r15+8]
0x14003a26f  call    cs:__imp_GetProcessHeap
0x14003a275  mov     r8, rbx
0x14003a278  xor     edx, edx
0x14003a27a  mov     rcx, rax
0x14003a27d  call    cs:__imp_VdsHeapFree
0x14003a283  inc     r12d
0x14003a286  mov     qword ptr [r15+8], 0
0x14003a28e  mov     eax, r12d
0x14003a291  lea     r15, [r15+10h]
0x14003a295  cmp     rax, rsi
0x14003a298  jb      short loc_14003A26B
0x14003a29a  call    cs:__imp_GetProcessHeap
0x14003a2a0  mov     r8, r14
0x14003a2a3  xor     edx, edx
0x14003a2a5  mov     rcx, rax
0x14003a2a8  call    cs:__imp_VdsHeapFree
0x14003a2ae  mov     r8d, edi
0x14003a2b1  lea     rdx, aExitCvdsservic_10; "EXIT CVdsService::GetVolumeIdList, hr=%"...
0x14003a2b8  mov     ecx, 2
0x14003a2bd  call    cs:__imp_VdsTraceW
0x14003a2c3  mov     eax, edi
0x14003a2c5  add     rsp, 68h
0x14003a2c9  pop     r15
0x14003a2cb  pop     r14
0x14003a2cd  pop     r13
0x14003a2cf  pop     r12
0x14003a2d1  pop     rdi
0x14003a2d2  pop     rsi
0x14003a2d3  pop     rbx
0x14003a2d4  pop     rbp
0x14003a2d5  retn
```
