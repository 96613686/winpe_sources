# HbDrvRebalanceCacheTask

- ea: `0x1800a3490`
- end: `0x1800a3ae3`
- name: `HbDrvRebalanceCacheTask`
- size: `1619`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800ade14`

## callees

- `0x180021e0c`
- `0x18002341c`
- `0x180054f40`
- `0x18005c148`
- `0x18005ec74`
- `0x180062090`
- `0x180064170`
- `0x180069980`
- `0x18009f710`
- `0x18009f8a8`
- `0x18009fe2c`
- `0x1800a134c`
- `0x1800a1910`
- `0x1800a1c80`
- `0x1800a26d4`
- `0x1800a28e4`
- `0x1800a2dc8`
- `0x1800a3490`
- `0x1800a5240`
- `0x1800a5818`
- `0x1800a705c`
- `0x1800b57c0`
- `0x1800b62c8`
- `0x1800b645a`
- `0x1800b64c0`
- `0x1800b7010`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x1800a3537`
- `ntdll!NtQueryInformationThread` at `0x1800a3537`
- `ntdll!RtlNtStatusToDosError` at `0x1800a354b`
- `ntdll!RtlNtStatusToDosError` at `0x1800a354b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a3519`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a355b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a3a98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a3519`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a355b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a3a98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a3993`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a3a4c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a3a67`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a3993`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a3a4c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a3a67`

## string_xrefs

- `0x1800a3899`: `HybridDriveCachePrepopulate`
- `0x1800a38b9`: `HybridDriveCachePrepopulate`

## pseudocode

```c
__int64 __fastcall HbDrvRebalanceCacheTask(__int64 a1, unsigned int a2)
{
  char *v2; // r15
  unsigned __int8 *v3; // r13
  unsigned int v4; // r12d
  __int64 v5; // rdi
  HANDLE CurrentThread; // rax
  int v7; // eax
  HANDLE v8; // rax
  unsigned int PrefetchServiceThreadPrivileges; // ebx
  int IsSupportedHhd; // eax
  unsigned __int64 v11; // r14
  unsigned __int8 v12; // si
  unsigned __int64 v13; // rcx
  int v14; // eax
  unsigned int SupportedVolumes; // eax
  int PerfResult; // ebx
  unsigned __int64 v17; // rax
  HRESULT v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // esi
  void *v22; // rax
  unsigned int v23; // edx
  unsigned int v24; // ecx
  char *v25; // r8
  char *v26; // rsi
  __int64 i; // r14
  unsigned int v28; // edi
  char *v29; // rcx
  unsigned int v30; // r12d
  char *v31; // rsi
  __int64 j; // r14
  __int64 k; // rsi
  HANDLE v34; // rax
  unsigned int v36; // [rsp+30h] [rbp-D0h] BYREF
  int ThreadInformation; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v38; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned int v39; // [rsp+40h] [rbp-C0h]
  unsigned int v40; // [rsp+44h] [rbp-BCh] BYREF
  int v41; // [rsp+48h] [rbp-B8h]
  LPVOID lpMem; // [rsp+50h] [rbp-B0h] BYREF
  char *v43; // [rsp+58h] [rbp-A8h] BYREF
  char *v44; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v45; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v46; // [rsp+70h] [rbp-90h] BYREF
  __int64 v47; // [rsp+78h] [rbp-88h]
  _OWORD v48[3]; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v49[24]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t pszDest[264]; // [rsp+230h] [rbp+130h] BYREF

  v36 = a2;
  v47 = a1;
  v40 = 0;
  v2 = 0;
  v43 = 0;
  v3 = 0;
  v46 = 0;
  v4 = 0;
  v38 = 0;
  v5 = a1;
  lpMem = 0;
  v44 = 0;
  v45 = 0;
  v39 = 0;
  memset(v48, 0, sizeof(v48));
  CurrentThread = GetCurrentThread();
  ThreadInformation = 0;
  v7 = NtQueryInformationThread(CurrentThread, ThreadPagePriority, &ThreadInformation, 4u, 0);
  if ( v7 >= 0 )
  {
    v41 = ThreadInformation;
  }
  else
  {
    v41 = 8;
    RtlNtStatusToDosError(v7);
  }
  v8 = GetCurrentThread();
  PfSetPagePriorityThread(v8);
  PrefetchServiceThreadPrivileges = PfSvGetPrefetchServiceThreadPrivileges(1);
  if ( !PrefetchServiceThreadPrivileges )
  {
    PrefetchServiceThreadPrivileges = PfDiContextStart(v5 + 3632, 1);
    if ( !PrefetchServiceThreadPrivileges )
    {
      PrefetchServiceThreadPrivileges = HbDrvGetSystemVolumeInfo(v5 + 3632, v48);
      if ( !PrefetchServiceThreadPrivileges )
      {
        IsSupportedHhd = HbDrvIsSupportedHhd((unsigned int)v48, (unsigned int)&v45, (unsigned int)&v46, (int)v5 + 24, 0);
        v3 = (unsigned __int8 *)v45;
        if ( IsSupportedHhd )
        {
          v11 = v46;
          if ( v46 >= 0x2CB417800LL )
          {
            v12 = *(_BYTE *)(v45 + 44);
          }
          else
          {
            v12 = PrefetchServiceThreadPrivileges + 3;
            if ( *(_BYTE *)(v45 + 44) < (unsigned __int8)(PrefetchServiceThreadPrivileges + 3) )
              v12 = *(_BYTE *)(v45 + 44);
          }
          LODWORD(v13) = -1;
          if ( (v46 / *(unsigned int *)(v45 + 24)) >> 20 < 0xFFFFFFFF )
            v13 = (v46 / *(unsigned int *)(v45 + 24)) >> 20;
          v14 = 1;
          if ( (unsigned int)v13 > 1 )
            v14 = v13;
          *(_DWORD *)(v5 + 3628) = v14;
          memset_0(v49, 0, sizeof(v49));
          SupportedVolumes = HbDrvGetSupportedVolumes(v48, v5 + 3632, v49);
          v4 = v39;
          PrefetchServiceThreadPrivileges = SupportedVolumes;
          if ( !SupportedVolumes )
          {
            if ( v39 )
            {
              *(_DWORD *)(v5 + 28) = v39;
              *(_QWORD *)(v5 + 32) = v49;
              *(_DWORD *)(v5 + 3624) = v12;
              *(_QWORD *)(v5 + 3616) = -1;
              PrefetchServiceThreadPrivileges = HbDrvConfirmKernelComponentAttached(v5);
              if ( !PrefetchServiceThreadPrivileges )
              {
                PerfResult = HbDrvGetPerfResult(v5, v11, v3[44]);
                if ( PerfResult )
                {
                  HbDrvSyncDirtyDataAggressive(v5);
                  HbDrvGetCacheSpaceRemaining(v3, v11, &v43, PerfResult == 1);
                  v17 = (unsigned __int64)&v43[(1 << *(_BYTE *)(v5 + 24)) - 1]
                      / (unsigned int)(1 << *(_BYTE *)(v5 + 24));
                  if ( v17 >= 0xFFFFFFFFLL << *(_BYTE *)(v5 + 24) )
                    v17 = 0xFFFFFFFFLL << *(_BYTE *)(v5 + 24);
                  *(_QWORD *)(v5 + 3616) = v17;
                  v18 = StringCchPrintfW(
                          pszDest,
                          0x104u,
                          L"%s\\%s",
                          *(_QWORD *)&PfSvcGlobals + 888LL,
                          L"HybridDrive.vbm");
                  if ( v18 >= 0 )
                  {
                    v19 = HbDrvDeserializeBitmaps(v5, pszDest, &lpMem, &v40);
                    PrefetchServiceThreadPrivileges = v19;
                    if ( !v19
                      || (v19 == 11 || v19 == 1006 || v19 - 2 <= 1)
                      && (PrefetchServiceThreadPrivileges = HbDrvPrepareEmptyBitmaps(
                                                              v5,
                                                              (unsigned int)v49,
                                                              v4,
                                                              0,
                                                              (__int64)&lpMem,
                                                              (__int64)&v40)) == 0 )
                    {
                      v20 = HbDrvPrepareEmptyBitmaps(v5, (unsigned int)v49, v4, 0, (__int64)&v44, (__int64)&v38);
                      v2 = v44;
                      PrefetchServiceThreadPrivileges = v20;
                      if ( !v20 )
                      {
                        v21 = v38;
                        *(_QWORD *)(v5 + 56) = lpMem;
                        *(_QWORD *)(v5 + 48) = v2;
                        *(_DWORD *)(v5 + 40) = v21;
                        PrefetchServiceThreadPrivileges = HbDrvPopulateVolumeBitmaps(v5);
                        if ( !PrefetchServiceThreadPrivileges )
                        {
                          if ( (*(unsigned int (__fastcall **)(_QWORD))v5)(*(_QWORD *)(v5 + 16)) )
                          {
                            if ( v36 )
                            {
                              PrefetchServiceThreadPrivileges = HbDrvPrepopulateCache(v5, v3, v11);
                              if ( PrefetchServiceThreadPrivileges != 995 )
                              {
                                PfTaskUpdateTaskSettings(
                                  (__int64)L"HybridDriveCachePrepopulate",
                                  (__int64)HbDrvTskClearMaintenanceSettingsCallback,
                                  0);
                                v36 = 0;
                                PfTaskUpdateTaskSettings(
                                  (__int64)L"HybridDriveCachePrepopulate",
                                  (__int64)HbDrvTskSetEnabledCallback,
                                  (__int64)&v36);
                              }
                            }
                            else
                            {
                              PrefetchServiceThreadPrivileges = HbDrvSetBitmaps(v5, v2);
                              if ( !PrefetchServiceThreadPrivileges )
                              {
                                PrefetchServiceThreadPrivileges = HbDrvSerializeBitmaps((__int64)v2, v21, pszDest);
                                if ( !PrefetchServiceThreadPrivileges )
                                  HbDrvConsiderDemoteBySize(v5);
                              }
                            }
                          }
                          else
                          {
                            PrefetchServiceThreadPrivileges = 995;
                          }
                        }
                      }
                    }
                  }
                  else
                  {
                    PrefetchServiceThreadPrivileges = (unsigned __int16)v18;
                  }
                }
                else
                {
                  PrefetchServiceThreadPrivileges = 1359;
                }
              }
            }
          }
        }
        else
        {
          PrefetchServiceThreadPrivileges = 50;
        }
      }
    }
  }
  HbDrvVolumeInfoCleanup(v48);
  v22 = lpMem;
  if ( lpMem )
  {
    v23 = v40;
    v24 = 0;
    v36 = v40;
    ThreadInformation = 0;
    if ( v40 )
    {
      v25 = (char *)lpMem + 24;
      v43 = (char *)lpMem + 24;
      do
      {
        v26 = &v25[104 * v24];
        if ( *((_QWORD *)v26 + 1) )
        {
          for ( i = 0; (unsigned int)i < *((_DWORD *)v26 + 13); i = (unsigned int)(i + 1) )
          {
            if ( (unsigned __int8)RtlpSparseBitmapCheckRangeArrayPage(v26, (unsigned int)i) )
            {
              if ( *(_QWORD *)(*((_QWORD *)v26 + 1) + 8 * i) )
                (*((void (**)(void))v26 + 5))();
            }
            else
            {
              LODWORD(i) = i + 511;
            }
          }
          RtlpSparseBitmapRangeArrayCleanup(v26, *((_QWORD *)v26 + 1), *((_QWORD *)v26 + 3));
          v24 = ThreadInformation;
          v23 = v36;
          v25 = v43;
        }
        ThreadInformation = ++v24;
      }
      while ( v24 < v23 );
      v22 = lpMem;
    }
    if ( v22 )
      HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v22);
  }
  if ( v2 )
  {
    v36 = 0;
    if ( v38 )
    {
      v28 = v36;
      v29 = v2 + 24;
      v30 = v38;
      do
      {
        v31 = &v29[104 * v28];
        if ( *((_QWORD *)v31 + 1) )
        {
          for ( j = 0; (unsigned int)j < *((_DWORD *)v31 + 13); j = (unsigned int)(j + 1) )
          {
            if ( (unsigned __int8)RtlpSparseBitmapCheckRangeArrayPage(v31, (unsigned int)j) )
            {
              if ( *(_QWORD *)(*((_QWORD *)v31 + 1) + 8 * j) )
                (*((void (**)(void))v31 + 5))();
            }
            else
            {
              LODWORD(j) = j + 511;
            }
          }
          RtlpSparseBitmapRangeArrayCleanup(v31, *((_QWORD *)v31 + 1), *((_QWORD *)v31 + 3));
          v29 = v2 + 24;
        }
        ++v28;
      }
      while ( v28 < v30 );
      v5 = v47;
      v4 = v39;
    }
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v2);
  }
  if ( v3 )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v3);
  for ( k = 0; (unsigned int)k < v4; k = (unsigned int)(k + 1) )
    HbDrvVolumeInfoCleanup(&v49[3 * k]);
  if ( v41 != 8 )
  {
    v34 = GetCurrentThread();
    PfSetPagePriorityThread(v34);
  }
  if ( !(*(unsigned int (__fastcall **)(_QWORD))v5)(*(_QWORD *)(v5 + 16)) )
    return 995;
  return PrefetchServiceThreadPrivileges;
}

```

## disassembly

```asm
0x1800a3490  push    rbp
0x1800a3492  push    rbx
0x1800a3493  push    rsi
0x1800a3494  push    rdi
0x1800a3495  push    r12
0x1800a3497  push    r13
0x1800a3499  push    r14
0x1800a349b  push    r15
0x1800a349d  lea     rbp, [rsp-358h]
0x1800a34a5  sub     rsp, 458h
0x1800a34ac  mov     rax, cs:__security_cookie
0x1800a34b3  xor     rax, rsp
0x1800a34b6  mov     [rbp+390h+var_50], rax
0x1800a34bd  xorps   xmm0, xmm0
0x1800a34c0  mov     [rsp+490h+var_460], edx
0x1800a34c4  xor     esi, esi
0x1800a34c6  mov     [rsp+490h+var_418], rcx
0x1800a34cb  mov     [rsp+490h+var_44C], esi
0x1800a34cf  mov     eax, 7FFE0014h
0x1800a34d4  xor     r15d, r15d
0x1800a34d7  mov     [rsp+490h+var_438], 0
0x1800a34e0  xor     r13d, r13d
0x1800a34e3  mov     [rsp+490h+var_420], 0
0x1800a34ec  xor     r12d, r12d
0x1800a34ef  mov     [rsp+490h+var_454], esi
0x1800a34f3  mov     rax, [rax]
0x1800a34f6  mov     rdi, rcx
0x1800a34f9  mov     [rsp+490h+lpMem], rsi
0x1800a34fe  mov     [rsp+490h+var_430], r15
0x1800a3503  mov     [rsp+490h+var_428], r13
0x1800a3508  mov     [rsp+490h+var_450], r12d
0x1800a350d  movups  [rbp+390h+var_410], xmm0
0x1800a3511  movups  [rbp+390h+var_400], xmm0
0x1800a3515  movups  [rbp+390h+var_3F0], xmm0
0x1800a3519  call    cs:__imp_GetCurrentThread
0x1800a351f  lea     r9d, [rsi+4]; ThreadInformationLength
0x1800a3523  mov     [rsp+490h+ThreadInformation], esi
0x1800a3527  mov     rcx, rax; ThreadHandle
0x1800a352a  mov     [rsp+490h+ReturnLength], rsi; ReturnLength
0x1800a352f  lea     r8, [rsp+490h+ThreadInformation]; ThreadInformation
0x1800a3534  lea     edx, [rsi+18h]; ThreadInformationClass
0x1800a3537  call    cs:__imp_NtQueryInformationThread
0x1800a353d  test    eax, eax
0x1800a353f  jns     short loc_1800A3553
0x1800a3541  mov     ecx, eax; Status
0x1800a3543  mov     [rsp+490h+var_448], 8
0x1800a354b  call    cs:__imp_RtlNtStatusToDosError
0x1800a3551  jmp     short loc_1800A355B
0x1800a3553  mov     eax, [rsp+490h+ThreadInformation]
0x1800a3557  mov     [rsp+490h+var_448], eax
0x1800a355b  call    cs:__imp_GetCurrentThread
0x1800a3561  mov     esi, 1
0x1800a3566  mov     rcx, rax; ThreadHandle
0x1800a3569  mov     edx, esi
0x1800a356b  call    PfSetPagePriorityThread
0x1800a3570  mov     ecx, esi
0x1800a3572  call    PfSvGetPrefetchServiceThreadPrivileges
0x1800a3577  mov     ebx, eax
0x1800a3579  test    eax, eax
0x1800a357b  jnz     loc_1800A38CC
0x1800a3581  lea     rsi, [rdi+0E30h]
0x1800a3588  mov     rcx, rsi
0x1800a358b  lea     edx, [rax+1]
0x1800a358e  call    PfDiContextStart
0x1800a3593  mov     ebx, eax
0x1800a3595  test    eax, eax
0x1800a3597  jnz     loc_1800A38CC
0x1800a359d  lea     rdx, [rbp+390h+var_410]
0x1800a35a1  mov     rcx, rsi
0x1800a35a4  call    HbDrvGetSystemVolumeInfo
0x1800a35a9  mov     ebx, eax
0x1800a35ab  test    eax, eax
0x1800a35ad  jnz     loc_1800A38CC
0x1800a35b3  lea     r9, [rdi+18h]
0x1800a35b7  mov     [rsp+490h+ReturnLength], r12
0x1800a35bc  lea     r8, [rsp+490h+var_420]
0x1800a35c1  lea     rdx, [rsp+490h+var_428]
0x1800a35c6  lea     rcx, [rbp+390h+var_410]
0x1800a35ca  call    HbDrvIsSupportedHhd
0x1800a35cf  mov     r13, [rsp+490h+var_428]
0x1800a35d4  test    eax, eax
0x1800a35d6  jz      loc_1800A38C7
0x1800a35dc  mov     r14, [rsp+490h+var_420]
0x1800a35e1  mov     rax, 2CB417800h
0x1800a35eb  cmp     r14, rax
0x1800a35ee  jnb     short loc_1800A3601
0x1800a35f0  movzx   eax, byte ptr [r13+2Ch]
0x1800a35f5  lea     esi, [rbx+3]
0x1800a35f8  cmp     [r13+2Ch], sil
0x1800a35fc  cmovb   esi, eax
0x1800a35ff  jmp     short loc_1800A3605
0x1800a3601  mov     sil, [r13+2Ch]
0x1800a3605  mov     ecx, [r13+18h]
0x1800a3609  xor     edx, edx
0x1800a360b  mov     rax, r14
0x1800a360e  mov     r8d, 180h; Size
0x1800a3614  div     rcx
0x1800a3617  mov     edx, 0FFFFFFFFh
0x1800a361c  shr     rax, 14h
0x1800a3620  mov     ecx, edx
0x1800a3622  cmp     rax, rdx
0x1800a3625  cmovb   rcx, rax
0x1800a3629  mov     eax, 1
0x1800a362e  cmp     ecx, eax
0x1800a3630  cmova   eax, ecx
0x1800a3633  xor     edx, edx; Val
0x1800a3635  lea     rcx, [rbp+390h+var_3E0]; void *
0x1800a3639  mov     [rdi+0E2Ch], eax
0x1800a363f  call    memset_0
0x1800a3644  lea     rax, [rsp+490h+var_450]
0x1800a3649  lea     r8, [rbp+390h+var_3E0]
0x1800a364d  mov     [rsp+490h+ReturnLength], rax
0x1800a3652  lea     rdx, [rdi+0E30h]
0x1800a3659  lea     rcx, [rbp+390h+var_410]
0x1800a365d  call    HbDrvGetSupportedVolumes
0x1800a3662  mov     r12d, [rsp+490h+var_450]
0x1800a3667  mov     ebx, eax
0x1800a3669  test    eax, eax
0x1800a366b  jnz     loc_1800A38CC
0x1800a3671  test    r12d, r12d
0x1800a3674  jz      loc_1800A38CC
0x1800a367a  lea     rax, [rbp+390h+var_3E0]
0x1800a367e  mov     [rdi+1Ch], r12d
0x1800a3682  mov     [rdi+20h], rax
0x1800a3686  mov     rcx, rdi
0x1800a3689  movzx   eax, sil
0x1800a368d  mov     [rdi+0E28h], eax
0x1800a3693  mov     qword ptr [rdi+0E20h], 0FFFFFFFFFFFFFFFFh
0x1800a369e  call    HbDrvConfirmKernelComponentAttached
0x1800a36a3  mov     ebx, eax
0x1800a36a5  test    eax, eax
0x1800a36a7  jnz     loc_1800A38CC
0x1800a36ad  movzx   r8d, byte ptr [r13+2Ch]
0x1800a36b2  mov     rdx, r14
0x1800a36b5  mov     rcx, rdi
0x1800a36b8  call    HbDrvGetPerfResult
0x1800a36bd  mov     ebx, eax
0x1800a36bf  test    eax, eax
0x1800a36c1  jnz     short loc_1800A36CD
0x1800a36c3  mov     ebx, 54Fh
0x1800a36c8  jmp     loc_1800A38CC
0x1800a36cd  mov     rcx, rdi
0x1800a36d0  call    HbDrvSyncDirtyDataAggressive
0x1800a36d5  xor     r9d, r9d
0x1800a36d8  lea     r8, [rsp+490h+var_438]
0x1800a36dd  mov     rdx, r14
0x1800a36e0  mov     rcx, r13
0x1800a36e3  lea     esi, [r9+1]
0x1800a36e7  cmp     ebx, esi
0x1800a36e9  setz    r9b
0x1800a36ed  call    HbDrvGetCacheSpaceRemaining
0x1800a36f2  movzx   r8d, byte ptr [rdi+18h]
0x1800a36f7  xor     edx, edx
0x1800a36f9  mov     ecx, r8d
0x1800a36fc  mov     eax, esi
0x1800a36fe  shl     eax, cl
0x1800a3700  mov     ecx, eax
0x1800a3702  mov     rax, [rsp+490h+var_438]
0x1800a3707  dec     rax
0x1800a370a  add     rax, rcx
0x1800a370d  div     rcx
0x1800a3710  mov     ecx, r8d
0x1800a3713  mov     edx, 0FFFFFFFFh
0x1800a3718  shl     rdx, cl
0x1800a371b  lea     r8, aSS; "%s\\%s"
0x1800a3722  cmp     rax, rdx
0x1800a3725  lea     rcx, [rbp+390h+pszDest]; pszDest
0x1800a372c  cmovnb  rax, rdx
0x1800a3730  mov     edx, 104h; cchDest
0x1800a3735  mov     [rdi+0E20h], rax
0x1800a373c  lea     rax, aHybriddriveVbm; "HybridDrive.vbm"
0x1800a3743  mov     r9, cs:PfSvcGlobals
0x1800a374a  add     r9, 378h
0x1800a3751  mov     [rsp+490h+ReturnLength], rax
0x1800a3756  call    StringCchPrintfW
0x1800a375b  test    eax, eax
0x1800a375d  jns     short loc_1800A3767
0x1800a375f  movzx   ebx, ax
0x1800a3762  jmp     loc_1800A38CC
0x1800a3767  lea     r9, [rsp+490h+var_44C]
0x1800a376c  mov     rcx, rdi
0x1800a376f  lea     r8, [rsp+490h+lpMem]
0x1800a3774  lea     rdx, [rbp+390h+pszDest]
0x1800a377b  call    HbDrvDeserializeBitmaps
0x1800a3780  mov     ebx, eax
0x1800a3782  test    eax, eax
0x1800a3784  jz      short loc_1800A37CD
0x1800a3786  cmp     eax, 0Bh
0x1800a3789  jz      short loc_1800A379D
0x1800a378b  cmp     eax, 3EEh
0x1800a3790  jz      short loc_1800A379D
0x1800a3792  add     eax, 0FFFFFFFEh
0x1800a3795  cmp     eax, esi
0x1800a3797  ja      loc_1800A38CC
0x1800a379d  lea     rax, [rsp+490h+var_44C]
0x1800a37a2  xor     r9d, r9d
0x1800a37a5  mov     [rsp+490h+var_468], rax
0x1800a37aa  lea     rdx, [rbp+390h+var_3E0]
0x1800a37ae  lea     rax, [rsp+490h+lpMem]
0x1800a37b3  mov     r8d, r12d
0x1800a37b6  mov     rcx, rdi
0x1800a37b9  mov     [rsp+490h+ReturnLength], rax
0x1800a37be  call    HbDrvPrepareEmptyBitmaps
0x1800a37c3  mov     ebx, eax
0x1800a37c5  test    eax, eax
0x1800a37c7  jnz     loc_1800A38CC
0x1800a37cd  lea     rax, [rsp+490h+var_454]
0x1800a37d2  xor     r9d, r9d
0x1800a37d5  mov     [rsp+490h+var_468], rax
0x1800a37da  lea     rdx, [rbp+390h+var_3E0]
0x1800a37de  lea     rax, [rsp+490h+var_430]
0x1800a37e3  mov     r8d, r12d
0x1800a37e6  mov     rcx, rdi
0x1800a37e9  mov     [rsp+490h+ReturnLength], rax
0x1800a37ee  call    HbDrvPrepareEmptyBitmaps
0x1800a37f3  mov     r15, [rsp+490h+var_430]
0x1800a37f8  mov     ebx, eax
0x1800a37fa  test    eax, eax
0x1800a37fc  jnz     loc_1800A38CC
0x1800a3802  mov     rax, [rsp+490h+lpMem]
0x1800a3807  mov     rcx, rdi
0x1800a380a  mov     esi, [rsp+490h+var_454]
0x1800a380e  mov     [rdi+38h], rax
0x1800a3812  mov     [rdi+30h], r15
0x1800a3816  mov     [rdi+28h], esi
0x1800a3819  call    HbDrvPopulateVolumeBitmaps
0x1800a381e  mov     ebx, eax
0x1800a3820  test    eax, eax
0x1800a3822  jnz     loc_1800A38CC
0x1800a3828  mov     rcx, [rdi+10h]
0x1800a382c  mov     rax, [rdi]
0x1800a382f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3834  test    eax, eax
0x1800a3836  jnz     short loc_1800A3842
0x1800a3838  mov     ebx, 3E3h
0x1800a383d  jmp     loc_1800A38CC
0x1800a3842  cmp     [rsp+490h+var_460], 0
0x1800a3847  mov     rcx, rdi
0x1800a384a  jnz     short loc_1800A387B
0x1800a384c  mov     rdx, r15
0x1800a384f  call    HbDrvSetBitmaps
0x1800a3854  mov     ebx, eax
0x1800a3856  test    eax, eax
0x1800a3858  jnz     short loc_1800A38CC
0x1800a385a  lea     r8, [rbp+390h+pszDest]
0x1800a3861  mov     edx, esi
0x1800a3863  mov     rcx, r15
0x1800a3866  call    HbDrvSerializeBitmaps
0x1800a386b  mov     ebx, eax
0x1800a386d  test    eax, eax
0x1800a386f  jnz     short loc_1800A38CC
0x1800a3871  mov     rcx, rdi
0x1800a3874  call    HbDrvConsiderDemoteBySize
0x1800a3879  jmp     short loc_1800A38CC
0x1800a387b  mov     r8, r14
0x1800a387e  mov     rdx, r13
0x1800a3881  call    HbDrvPrepopulateCache
0x1800a3886  mov     ebx, eax
0x1800a3888  cmp     eax, 3E3h
0x1800a388d  jz      short loc_1800A38CC
0x1800a388f  xor     r8d, r8d
0x1800a3892  lea     rdx, ?HbDrvTskClearMaintenanceSettingsCallback@@YAJPEAUITaskSettings3@@PEAUIMaintenanceSettings@@PEAKPEAX@Z; HbDrvTskClearMaintenanceSettingsCallback(ITaskSettings3 *,IMaintenanceSettings *,ulong *,void *)
0x1800a3899  lea     rcx, aHybriddrivecac; "HybridDriveCachePrepopulate"
0x1800a38a0  call    PfTaskUpdateTaskSettings
0x1800a38a5  lea     r8, [rsp+490h+var_460]
0x1800a38aa  mov     [rsp+490h+var_460], 0
0x1800a38b2  lea     rdx, ?HbDrvTskSetEnabledCallback@@YAJPEAUITaskSettings3@@PEAUIMaintenanceSettings@@PEAKPEAX@Z; HbDrvTskSetEnabledCallback(ITaskSettings3 *,IMaintenanceSettings *,ulong *,void *)
0x1800a38b9  lea     rcx, aHybriddrivecac; "HybridDriveCachePrepopulate"
0x1800a38c0  call    PfTaskUpdateTaskSettings
0x1800a38c5  jmp     short loc_1800A38CC
0x1800a38c7  mov     ebx, 32h ; '2'
0x1800a38cc  lea     rcx, [rbp+390h+var_410]
0x1800a38d0  call    HbDrvVolumeInfoCleanup
0x1800a38d5  mov     rax, [rsp+490h+lpMem]
0x1800a38da  test    rax, rax
0x1800a38dd  jz      loc_1800A3999
0x1800a38e3  mov     edx, [rsp+490h+var_44C]
0x1800a38e7  xor     ecx, ecx
0x1800a38e9  mov     [rsp+490h+var_460], edx
0x1800a38ed  mov     [rsp+490h+ThreadInformation], ecx
0x1800a38f1  test    edx, edx
0x1800a38f3  jz      loc_1800A397E
0x1800a38f9  lea     r8, [rax+18h]
0x1800a38fd  mov     [rsp+490h+var_438], r8
0x1800a3902  mov     eax, ecx
0x1800a3904  imul    rsi, rax, 68h ; 'h'
0x1800a3908  add     rsi, r8
0x1800a390b  cmp     qword ptr [rsi+8], 0
0x1800a3910  jz      short loc_1800A396F
0x1800a3912  xor     r14d, r14d
0x1800a3915  cmp     [rsi+34h], r14d
0x1800a3919  jbe     short loc_1800A3952
0x1800a391b  mov     edx, r14d
0x1800a391e  mov     rcx, rsi
0x1800a3921  call    RtlpSparseBitmapCheckRangeArrayPage
0x1800a3926  test    al, al
0x1800a3928  jnz     short loc_1800A3933
0x1800a392a  add     r14d, 1FFh
0x1800a3931  jmp     short loc_1800A3949
0x1800a3933  mov     rax, [rsi+8]
  ... truncated ...
```
