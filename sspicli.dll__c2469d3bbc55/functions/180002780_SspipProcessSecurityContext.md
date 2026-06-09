# SspipProcessSecurityContext

- ea: `0x180002780`
- end: `0x18000354f`
- name: `SspipProcessSecurityContext`
- size: `3535`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180002130`
- `0x18001b700`

## callees

- `0x180002780`
- `0x1800084f0`
- `0x18000f7ac`
- `0x180018e90`
- `0x18001b020`
- `0x180020928`
- `0x18002096c`
- `0x1800209c0`
- `0x180020a90`
- `0x180022047`
- `0x18002205f`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x180002c42`
- `ntdll!NtQueryInformationThread` at `0x180002c42`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800222b1`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800222b1`
- `RPCRT4!I_RpcMapWin32Status` at `0x180003081`
- `RPCRT4!I_RpcMapWin32Status` at `0x180003081`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002f05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003035`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800033f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003505`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002f05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003035`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800033f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003505`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002f45`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002f45`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180002d9b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180002d9b`

## pseudocode

```c
__int64 __fastcall SspipProcessSecurityContext(
        __int128 *a1,
        _OWORD *a2,
        __int64 a3,
        struct _SecBufferDesc *a4,
        int a5,
        int a6,
        _OWORD *a7,
        __int64 a8,
        _DWORD *a9,
        __int64 *a10,
        bool *a11,
        __int64 a12,
        _DWORD *a13,
        __int64 a14,
        __int64 a15)
{
  unsigned int v18; // esi
  __int64 v19; // r8
  NTSTATUS v20; // edi
  __int64 v21; // r15
  unsigned int cBuffers; // eax
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  struct _SecBufferDesc *v25; // r13
  __int128 *v26; // rax
  __int64 *v27; // rcx
  unsigned int v28; // ebx
  _DWORD *v29; // r14
  unsigned int v30; // edi
  _QWORD *v31; // r12
  int *v32; // r10
  unsigned int v33; // r9d
  int v34; // ebx
  __int64 v35; // rdx
  __int64 *v36; // r8
  char v37; // r13
  int v38; // eax
  unsigned int v39; // edx
  _BYTE *v40; // rcx
  __int64 v41; // rax
  __int64 v42; // rcx
  __int128 *v43; // rax
  __int64 v44; // rdi
  __int64 v45; // r14
  __int64 v46; // rbx
  _QWORD *Value; // rax
  __int64 **v48; // r9
  __int64 *i; // r10
  _BYTE *v50; // rcx
  __int64 v51; // rax
  __int64 v52; // rcx
  __int128 *v53; // rax
  unsigned int j; // r14d
  const void *v55; // rdx
  unsigned int v56; // r9d
  unsigned int v57; // eax
  _QWORD *v58; // r14
  _QWORD *v59; // r13
  PVOID *v60; // rcx
  _BYTE *v61; // rcx
  __int64 v62; // rax
  __int64 v63; // rcx
  __int128 *v64; // rax
  _BYTE *v65; // rcx
  __int64 v66; // rax
  __int128 *v67; // rax
  __int64 result; // rax
  int v69; // [rsp+B0h] [rbp-3D8h] BYREF
  struct _SecBufferDesc *v70; // [rsp+B8h] [rbp-3D0h] BYREF
  __int128 v71; // [rsp+C0h] [rbp-3C8h] BYREF
  HLOCAL v72; // [rsp+D0h] [rbp-3B8h] BYREF
  _DWORD *v73; // [rsp+D8h] [rbp-3B0h]
  __int64 v74; // [rsp+E0h] [rbp-3A8h]
  _DWORD *v75; // [rsp+E8h] [rbp-3A0h]
  _OWORD *v76; // [rsp+F0h] [rbp-398h]
  int v77; // [rsp+F8h] [rbp-390h]
  _QWORD *v78; // [rsp+100h] [rbp-388h]
  __int128 v79; // [rsp+110h] [rbp-378h] BYREF
  __int128 v80; // [rsp+120h] [rbp-368h] BYREF
  __int128 v81; // [rsp+130h] [rbp-358h] BYREF
  HLOCAL v82[2]; // [rsp+140h] [rbp-348h]
  __int64 *v83; // [rsp+150h] [rbp-338h]
  __int64 v84; // [rsp+158h] [rbp-330h]
  __int64 v85; // [rsp+160h] [rbp-328h]
  __int64 v86; // [rsp+168h] [rbp-320h]
  _DWORD *v87; // [rsp+170h] [rbp-318h]
  bool *v88; // [rsp+178h] [rbp-310h]
  __int128 v89; // [rsp+180h] [rbp-308h] BYREF
  __int128 v90; // [rsp+190h] [rbp-2F8h] BYREF
  HLOCAL hMem[2]; // [rsp+1A0h] [rbp-2E8h]
  __int64 v92; // [rsp+1B0h] [rbp-2D8h]
  __int64 v93; // [rsp+1B8h] [rbp-2D0h]
  char *v94; // [rsp+1C0h] [rbp-2C8h]
  _OWORD *v95; // [rsp+1C8h] [rbp-2C0h]
  __int64 v96; // [rsp+1D0h] [rbp-2B8h] BYREF
  PSecBuffer pBuffers; // [rsp+1D8h] [rbp-2B0h]
  _OWORD *v98; // [rsp+1E0h] [rbp-2A8h]
  struct _SecBufferDesc *v99; // [rsp+1E8h] [rbp-2A0h]
  __int128 v100; // [rsp+1F0h] [rbp-298h] BYREF
  __int128 v101; // [rsp+200h] [rbp-288h] BYREF
  __int128 ThreadInformation; // [rsp+210h] [rbp-278h] BYREF
  __int128 v103; // [rsp+220h] [rbp-268h]
  __int128 v104; // [rsp+230h] [rbp-258h]
  __int128 v105; // [rsp+240h] [rbp-248h] BYREF
  __int128 v106; // [rsp+250h] [rbp-238h] BYREF
  __int128 v107; // [rsp+260h] [rbp-228h] BYREF
  __int128 v108; // [rsp+270h] [rbp-218h] BYREF
  GUID ActivityId; // [rsp+280h] [rbp-208h] BYREF
  int v110; // [rsp+290h] [rbp-1F8h] BYREF
  __int128 v111; // [rsp+294h] [rbp-1F4h]
  __int128 v112; // [rsp+2A4h] [rbp-1E4h]
  __int128 v113; // [rsp+2B4h] [rbp-1D4h]
  __int128 v114; // [rsp+2C4h] [rbp-1C4h]
  __int128 v115; // [rsp+2D4h] [rbp-1B4h]
  __int128 v116; // [rsp+2E4h] [rbp-1A4h]
  __int128 v117; // [rsp+2F4h] [rbp-194h]
  _BYTE v118[28]; // [rsp+304h] [rbp-184h] BYREF
  int v119; // [rsp+320h] [rbp-168h] BYREF
  _BYTE v120[284]; // [rsp+324h] [rbp-164h] BYREF

  v74 = a3;
  v78 = a2;
  v88 = a11;
  v93 = (__int64)a11;
  v92 = a3;
  v76 = a7;
  v98 = a2;
  v95 = a2;
  v75 = a9;
  v84 = a12;
  v73 = a13;
  v86 = a14;
  v85 = a15;
  v18 = 0;
  v69 = 0;
  v107 = 0;
  v96 = 0;
  v106 = 0;
  v108 = 0;
  v105 = 0;
  v100 = 0;
  v101 = 0;
  v71 = 0;
  v119 = 0;
  memset_0(v120, 0, sizeof(v120));
  v110 = 0;
  v111 = 0;
  v112 = 0;
  v113 = 0;
  v114 = 0;
  v115 = 0;
  v116 = 0;
  v117 = 0;
  memset(v118, 0, sizeof(v118));
  v79 = 0;
  v72 = 0;
  v89 = 0;
  v90 = 0;
  *(_OWORD *)hMem = 0;
  v80 = 0;
  v81 = 0;
  *(_OWORD *)v82 = 0;
  if ( !a1 )
  {
    v20 = -2146893054;
    v21 = 48;
    goto LABEL_113;
  }
  if ( a4 )
  {
    cBuffers = a4->cBuffers;
    if ( cBuffers > 0x12 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_9;
      v24 = 13;
LABEL_8:
      WPP_SF_L(v23[2], v24, v19, cBuffers);
LABEL_9:
      v20 = -2146893048;
LABEL_10:
      v21 = 48;
      goto LABEL_113;
    }
    if ( cBuffers && !a4->pBuffers )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_54021242344439e0b4b6b44468378b0e_Traceguids);
        v20 = -2146893048;
        v21 = 48;
        goto LABEL_113;
      }
      goto LABEL_9;
    }
  }
  if ( a8 )
  {
    cBuffers = *(_DWORD *)(a8 + 4);
    if ( cBuffers > 0x12 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_9;
      v24 = 15;
      goto LABEL_8;
    }
    if ( cBuffers && !*(_QWORD *)(a8 + 8) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_54021242344439e0b4b6b44468378b0e_Traceguids);
        v20 = -2146893048;
        v21 = 48;
        goto LABEL_113;
      }
      goto LABEL_9;
    }
  }
  v70 = 0;
  v20 = IsOkayToExec(&v70);
  if ( v20 < 0 )
    goto LABEL_10;
  pBuffers = v70[1].pBuffers;
  v106 = *a1;
  if ( a2 )
    v108 = *a2;
  v25 = (struct _SecBufferDesc *)&v100;
  if ( a4 )
    v25 = a4;
  v70 = v25;
  v26 = &v101;
  if ( a8 )
    v26 = (__int128 *)a8;
  v27 = &v96;
  if ( a10 )
    v27 = a10;
  v83 = v27;
  LODWORD(v71) = *(_DWORD *)v26;
  v28 = v71;
  v29 = (_DWORD *)v26 + 1;
  v87 = (_DWORD *)v26 + 1;
  v30 = *((_DWORD *)v26 + 1);
  DWORD1(v71) = v30;
  *((_QWORD *)&v71 + 1) = &v119;
  v31 = (_QWORD *)v26 + 1;
  v94 = (char *)v26 + 8;
  memcpy_0(&v119, *((const void **)v26 + 1), 16LL * v30);
  *(_QWORD *)&v79 = __PAIR64__(v30, v28);
  v32 = &v110;
  *((_QWORD *)&v79 + 1) = &v110;
  v33 = 0;
  v34 = a5;
  if ( v30 )
  {
    while ( 1 )
    {
      v35 = 2LL * v33;
      v32[v35 + 1] = *(_DWORD *)(*v31 + 16LL * v33 + 4);
      *(_DWORD *)(v35 * 4 + *((_QWORD *)&v79 + 1)) = *(_DWORD *)(*v31 + 16LL * v33);
      if ( (a5 & 0x100) != 0 )
        *(_QWORD *)&v120[16 * v33 + 4] = 0;
      if ( ++v33 >= *v29 )
        break;
      v32 = (int *)*((_QWORD *)&v79 + 1);
    }
  }
  ThreadInformation = 0;
  v103 = 0;
  v104 = 0;
  v21 = 48;
  v20 = NtQueryInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadBasicInformation, &ThreadInformation, 0x30u, 0);
  if ( v20 >= 0 )
  {
    v107 = v103;
    v99 = v25;
    if ( SecpLsaInprocDispatch )
    {
      v20 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _DWORD *, __int64, __int128 *, __int128 *, int, int, __int64, __int64, struct _SecBufferDesc *, __int128 *, __int128 *, HLOCAL *, __int64, __int128 *, _DWORD *, __int64 *, int *, _QWORD, _QWORD))(SecpLsaInprocDispatch + 24))(
              0,
              &v107,
              v73,
              v74,
              &v106,
              &v108,
              a5,
              a6,
              v86,
              v85,
              v25,
              &v79,
              &v71,
              &v72,
              v84,
              &v105,
              v75,
              v83,
              &v69,
              0,
              0);
    }
    else
    {
      do
      {
        v37 = 0;
        ActivityId = 0;
        EventActivityIdControl(1u, &ActivityId);
        v38 = SspirProcessSecurityContext2(
                (_DWORD)pBuffers,
                (unsigned int)&ActivityId,
                (unsigned int)&v107,
                (_DWORD)v73,
                v74,
                (__int64)&v106,
                (__int64)&v108,
                v34,
                a6,
                v86,
                v85,
                (__int64)v70,
                (__int64)&v79,
                (__int64)&v71,
                (__int64)&v72,
                v84,
                (__int64)&v105,
                (__int64)v75,
                (__int64)v83,
                (__int64)&v69,
                (__int64)&v89,
                (__int64)&v80);
        v20 = v38;
        v77 = v38;
        v39 = v80;
        if ( (_DWORD)v80 && v38 >= 0 )
        {
          v40 = hMem[0];
          if ( hMem[0] )
          {
            v41 = DWORD2(v90);
            if ( DWORD2(v90) )
            {
              do
              {
                *v40++ = 0;
                --v41;
              }
              while ( v41 );
              v40 = hMem[0];
            }
            LocalFree(v40);
            v39 = v80;
          }
          v42 = 48;
          v43 = &v89;
          do
          {
            *(_BYTE *)v43 = 0;
            v43 = (__int128 *)((char *)v43 + 1);
            --v42;
          }
          while ( v42 );
          v44 = v81;
          v45 = *((_QWORD *)&v80 + 1);
          v46 = v39;
          Value = TlsGetValue(SecTlsPackage);
          if ( Value )
          {
            v48 = (__int64 **)(Value[26] + 16LL);
            v36 = *v48;
            for ( i = 0; v36 != (__int64 *)v48; v36 = (__int64 *)*v36 )
            {
              i = v36;
              if ( *((_DWORD *)v36 + 4) == v46 )
                break;
              i = 0;
            }
            if ( i )
              v20 = ((__int64 (__fastcall *)(__int64, __int64, char *, char *))i[3])(
                      v45,
                      v44,
                      (char *)&v81 + 8,
                      (char *)&v90 + 8);
            else
              v20 = -1073741511;
          }
          else
          {
            v20 = -1073741811;
          }
          if ( v20 >= 0 && LOBYTE(v82[1]) )
          {
            LODWORD(v89) = v80;
            *((_QWORD *)&v89 + 1) = *((_QWORD *)&v80 + 1);
            *(_QWORD *)&v90 = v81;
            LOBYTE(hMem[1]) = 0;
            v37 = 1;
            v50 = v82[0];
            if ( v82[0] )
            {
              v51 = DWORD2(v81);
              if ( DWORD2(v81) )
              {
                do
                {
                  *v50++ = 0;
                  --v51;
                }
                while ( v51 );
                v50 = v82[0];
              }
              LocalFree(v50);
            }
            v52 = 48;
            v53 = &v80;
            do
            {
              *(_BYTE *)v53 = 0;
              v53 = (__int128 *)((char *)v53 + 1);
              --v52;
            }
            while ( v52 );
          }
          v34 = a5;
        }
      }
      while ( v37 );
      v29 = v87;
    }
    if ( v20 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v36, (unsigned int)v20);
      goto LABEL_113;
    }
    if ( DWORD1(v71) > *v29 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_LL(*((_QWORD *)WPP_GLOBAL_Control + 2), 18);
      v20 = 261;
      goto LABEL_113;
    }
    for ( j = 0; j < DWORD1(v71); ++j )
    {
      v36 = (__int64 *)*((_QWORD *)&v71 + 1);
      v55 = *(const void **)(*((_QWORD *)&v71 + 1) + 16LL * j + 8);
      if ( v55 )
      {
        if ( !SecpLsaInprocDispatch || (a5 & 0x100) != 0 )
        {
          *(_QWORD *)(*v31 + 16LL * j + 8) = v55;
          *(_QWORD *)(*((_QWORD *)&v71 + 1) + 16LL * j + 8) = 0;
        }
        else
        {
          v56 = *(_DWORD *)(*v31 + 16LL * j);
          v57 = *(_DWORD *)(*((_QWORD *)&v71 + 1) + 16LL * j);
          if ( v56 < v57 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_LLL(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v55,
                *((_QWORD *)&v71 + 1),
                j,
                v56,
                *(_DWORD *)(*((_QWORD *)&v71 + 1) + 16LL * j));
            v20 = -1073741789;
            goto LABEL_113;
          }
          memcpy_0(*(void **)(*v31 + 16LL * j + 8), v55, v57);
        }
      }
      *(_QWORD *)(*v31 + 16LL * j) = *(_QWORD *)(*((_QWORD *)&v71 + 1) + 16LL * j);
    }
    if ( v69 >= 0 )
    {
      v58 = v76;
      v59 = v76;
LABEL_111:
      v20 = CopyExtraBuffers((struct _SecBufferInfoArray *)v72, v70);
      if ( v20 >= 0 )
      {
        *v88 = (*v73 & 0x2000) != 0;
        *v58 = v105;
        v59[1] = *((_QWORD *)&v105 + 1);
        v20 = 0;
      }
      goto LABEL_113;
    }
    if ( (*((_QWORD *)v95 + 1) || *v78) && (*(_BYTE *)v73 & 0x20) != 0 )
    {
      v58 = v76;
      *v76 = v105;
      v59 = v58;
      v20 = 0;
      v60 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_102:
        if ( v74 || (*v75 & 0x8000) == 0 )
        {
          if ( v60 != &WPP_GLOBAL_Control && (*((_BYTE *)v60 + 28) & 4) != 0 )
            WPP_SF_L(v60[2], 21, v36, (unsigned int)v69);
          if ( v69 == -2146893032 || v69 == -2146892950 )
            v20 = CopyExtraBuffers((struct _SecBufferInfoArray *)v72, v70);
          goto LABEL_113;
        }
        goto LABEL_111;
      }
      WPP_SF_PP(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_54021242344439e0b4b6b44468378b0e_Traceguids);
    }
    else
    {
      v58 = v76;
      v59 = v76;
    }
    v60 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_102;
  }
LABEL_113:
  if ( v72 )
  {
    if ( SecpLsaInprocDispatch )
      (*(void (**)(void))SecpLsaInprocDispatch)();
    else
      LocalFree(v72);
  }
  if ( *((_QWORD *)&v71 + 1) && *((int **)&v71 + 1) != &v119 && SecpLsaInprocDispatch )
  {
    if ( DWORD1(v71) )
    {
      do
      {
        if ( *(_QWORD *)(*((_QWORD *)&v71 + 1) + 16LL * v18 + 8) )
          (*(void (**)(void))SecpLsaInprocDispatch)();
        ++v18;
      }
      while ( v18 < DWORD1(v71) );
    }
    (*(void (__fastcall **)(_QWORD))SecpLsaInprocDispatch)(*((_QWORD *)&v71 + 1));
  }
  v61 = hMem[0];
  if ( hMem[0] )
  {
    v62 = DWORD2(v90);
    if ( DWORD2(v90) )
    {
      do
      {
        *v61++ = 0;
        --v62;
      }
      while ( v62 );
      v61 = hMem[0];
    }
    LocalFree(v61);
  }
  v63 = 48;
  v64 = &v89;
  do
  {
    *(_BYTE *)v64 = 0;
    v64 = (__int128 *)((char *)v64 + 1);
    --v63;
  }
  while ( v63 );
  v65 = v82[0];
  if ( v82[0] )
  {
    v66 = DWORD2(v81);
    if ( DWORD2(v81) )
    {
      do
      {
        *v65++ = 0;
        --v66;
      }
      while ( v66 );
      v65 = v82[0];
    }
    LocalFree(v65);
  }
  v67 = &v80;
  do
  {
    *(_BYTE *)v67 = 0;
    v67 = (__int128 *)((char *)v67 + 1);
    --v21;
  }
  while ( v21 );
  result = (unsigned int)v69;
  if ( v20 < 0 )
    return (unsigned int)v20;
  return result;
}

```

## disassembly

```asm
0x180002780  push    rbx
0x180002782  push    rsi
0x180002783  push    rdi
0x180002784  push    r12
0x180002786  push    r13
0x180002788  push    r14
0x18000278a  push    r15
0x18000278c  sub     rsp, 450h
0x180002793  mov     rax, cs:__security_cookie
0x18000279a  xor     rax, rsp
0x18000279d  mov     [rsp+488h+var_48], rax
0x1800027a5  mov     rbx, r9
0x1800027a8  mov     rax, r8
0x1800027ab  mov     [rsp+488h+var_3A8], rax
0x1800027b3  mov     [rsp+488h+var_388], rdx
0x1800027bb  mov     r15, rcx
0x1800027be  mov     rcx, [rsp+488h+arg_50]
0x1800027c6  mov     [rsp+488h+var_310], rcx
0x1800027ce  mov     [rsp+488h+var_2D0], rcx
0x1800027d6  mov     [rsp+488h+var_2D8], rax
0x1800027de  mov     r12, [rsp+488h+arg_48]
0x1800027e6  mov     r14, [rsp+488h+arg_38]
0x1800027ee  mov     rax, [rsp+488h+arg_30]
0x1800027f6  mov     [rsp+488h+var_398], rax
0x1800027fe  mov     [rsp+488h+var_2A8], rdx
0x180002806  mov     r13, rdx
0x180002809  mov     [rsp+488h+var_2C0], rdx
0x180002811  mov     rax, [rsp+488h+arg_40]
0x180002819  mov     [rsp+488h+var_3A0], rax
0x180002821  mov     rax, [rsp+488h+arg_58]
0x180002829  mov     [rsp+488h+var_330], rax
0x180002831  mov     rax, [rsp+488h+arg_60]
0x180002839  mov     [rsp+488h+var_3B0], rax
0x180002841  mov     rax, [rsp+488h+arg_68]
0x180002849  mov     [rsp+488h+var_320], rax
0x180002851  mov     rax, [rsp+488h+arg_70]
0x180002859  mov     [rsp+488h+var_328], rax
0x180002861  xor     esi, esi
0x180002863  mov     [rsp+488h+var_3D8], esi
0x18000286a  xorps   xmm0, xmm0
0x18000286d  movups  [rsp+488h+var_228], xmm0
0x180002875  mov     [rsp+488h+var_2B8], rsi
0x18000287d  xorps   xmm1, xmm1
0x180002880  movups  [rsp+488h+var_238], xmm1
0x180002888  movups  [rsp+488h+var_218], xmm0
0x180002890  movups  [rsp+488h+var_248], xmm1
0x180002898  movups  [rsp+488h+var_298], xmm0
0x1800028a0  movups  [rsp+488h+var_288], xmm1
0x1800028a8  movups  [rsp+488h+var_3C8], xmm0
0x1800028b0  mov     [rsp+488h+var_168], esi
0x1800028b7  xor     edx, edx; Val
0x1800028b9  mov     r8d, 11Ch; Size
0x1800028bf  lea     rcx, [rsp+488h+var_164]; void *
0x1800028c7  call    memset_0
0x1800028cc  mov     [rsp+488h+var_1F8], esi
0x1800028d3  xorps   xmm0, xmm0
0x1800028d6  movups  [rsp+488h+var_1F4], xmm0
0x1800028de  movups  [rsp+488h+var_1E4], xmm0
0x1800028e6  movups  [rsp+488h+var_1D4], xmm0
0x1800028ee  movups  [rsp+488h+var_1C4], xmm0
0x1800028f6  movups  [rsp+488h+var_1B4], xmm0
0x1800028fe  movups  [rsp+488h+var_1A4], xmm0
0x180002906  movups  [rsp+488h+var_194], xmm0
0x18000290e  movups  xmmword ptr [rsp+488h+var_184], xmm0
0x180002916  movups  xmmword ptr [rsp+488h+var_184+0Ch], xmm0
0x18000291e  movups  [rsp+488h+var_378], xmm0
0x180002926  mov     [rsp+488h+var_3B8], rsi
0x18000292e  xorps   xmm1, xmm1
0x180002931  movups  [rsp+488h+var_308], xmm1
0x180002939  movups  [rsp+488h+var_2F8], xmm1
0x180002941  movups  xmmword ptr [rsp+488h+hMem], xmm1
0x180002949  movups  [rsp+488h+var_368], xmm0
0x180002951  movups  [rsp+488h+var_358], xmm0
0x180002959  movups  xmmword ptr [rsp+488h+var_348], xmm0
0x180002961  test    r15, r15
0x180002964  jnz     short loc_180002976
0x180002966  mov     edi, 80090302h
0x18000296b  mov     r15d, 30h ; '0'
0x180002971  jmp     loc_1800033C8
0x180002976  test    rbx, rbx
0x180002979  jz      loc_180002A09
0x18000297f  mov     eax, [rbx+4]
0x180002982  cmp     eax, 12h
0x180002985  jbe     short loc_1800029C1
0x180002987  lea     rbx, WPP_GLOBAL_Control
0x18000298e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002995  cmp     rcx, rbx
0x180002998  jz      short loc_1800029B1
0x18000299a  test    byte ptr [rcx+1Ch], 1
0x18000299e  jz      short loc_1800029B1
0x1800029a0  mov     edx, 0Dh
0x1800029a5  mov     r9d, eax
0x1800029a8  mov     rcx, [rcx+10h]
0x1800029ac  call    WPP_SF_L
0x1800029b1  mov     edi, 80090308h
0x1800029b6  mov     r15d, 30h ; '0'
0x1800029bc  jmp     loc_1800033C8
0x1800029c1  test    eax, eax
0x1800029c3  jz      short loc_180002A09
0x1800029c5  cmp     [rbx+8], rsi
0x1800029c9  jnz     short loc_180002A09
0x1800029cb  lea     rbx, WPP_GLOBAL_Control
0x1800029d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029d9  cmp     rcx, rbx
0x1800029dc  jz      short loc_1800029B1
0x1800029de  test    byte ptr [rcx+1Ch], 1
0x1800029e2  jz      short loc_1800029B1
0x1800029e4  mov     edx, 0Eh
0x1800029e9  lea     r8, WPP_54021242344439e0b4b6b44468378b0e_Traceguids
0x1800029f0  mov     rcx, [rcx+10h]
0x1800029f4  call    WPP_SF_
0x1800029f9  mov     edi, 80090308h
0x1800029fe  mov     r15d, 30h ; '0'
0x180002a04  jmp     loc_1800033C8
0x180002a09  test    r14, r14
0x180002a0c  jz      short loc_180002A8A
0x180002a0e  mov     eax, [r14+4]
0x180002a12  cmp     eax, 12h
0x180002a15  jbe     short loc_180002A3A
0x180002a17  lea     rbx, WPP_GLOBAL_Control
0x180002a1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a25  cmp     rcx, rbx
0x180002a28  jz      short loc_1800029B1
0x180002a2a  test    byte ptr [rcx+1Ch], 1
0x180002a2e  jz      short loc_1800029B1
0x180002a30  mov     edx, 0Fh
0x180002a35  jmp     loc_1800029A5
0x180002a3a  test    eax, eax
0x180002a3c  jz      short loc_180002A8A
0x180002a3e  cmp     [r14+8], rsi
0x180002a42  jnz     short loc_180002A8A
0x180002a44  lea     rbx, WPP_GLOBAL_Control
0x180002a4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a52  cmp     rcx, rbx
0x180002a55  jz      loc_1800029B1
0x180002a5b  test    byte ptr [rcx+1Ch], 1
0x180002a5f  jz      loc_1800029B1
0x180002a65  mov     edx, 10h
0x180002a6a  lea     r8, WPP_54021242344439e0b4b6b44468378b0e_Traceguids
0x180002a71  mov     rcx, [rcx+10h]
0x180002a75  call    WPP_SF_
0x180002a7a  mov     edi, 80090308h
0x180002a7f  mov     r15d, 30h ; '0'
0x180002a85  jmp     loc_1800033C8
0x180002a8a  mov     [rsp+488h+var_3D0], rsi
0x180002a92  lea     rcx, [rsp+488h+var_3D0]
0x180002a9a  call    IsOkayToExec
0x180002a9f  mov     edi, eax
0x180002aa1  test    eax, eax
0x180002aa3  js      loc_1800029B6
0x180002aa9  mov     rax, [rsp+488h+var_3D0]
0x180002ab1  mov     rax, [rax+18h]
0x180002ab5  mov     [rsp+488h+var_2B0], rax
0x180002abd  mov     rax, [r15]
0x180002ac0  mov     qword ptr [rsp+488h+var_238], rax
0x180002ac8  mov     rax, [r15+8]
0x180002acc  mov     qword ptr [rsp+488h+var_238+8], rax
0x180002ad4  test    r13, r13
0x180002ad7  jz      short loc_180002AF1
0x180002ad9  mov     rax, [r13+0]
0x180002add  mov     qword ptr [rsp+488h+var_218], rax
0x180002ae5  mov     rax, [r13+8]
0x180002ae9  mov     qword ptr [rsp+488h+var_218+8], rax
0x180002af1  lea     r13, [rsp+488h+var_298]
0x180002af9  test    rbx, rbx
0x180002afc  cmovnz  r13, rbx
0x180002b00  mov     [rsp+488h+var_3D0], r13
0x180002b08  lea     rax, [rsp+488h+var_288]
0x180002b10  test    r14, r14
0x180002b13  cmovnz  rax, r14
0x180002b17  lea     rcx, [rsp+488h+var_2B8]
0x180002b1f  test    r12, r12
0x180002b22  cmovnz  rcx, r12
0x180002b26  mov     [rsp+488h+var_338], rcx
0x180002b2e  mov     ebx, [rax]
0x180002b30  mov     dword ptr [rsp+488h+var_3C8], ebx
0x180002b37  lea     r14, [rax+4]
0x180002b3b  mov     [rsp+488h+var_318], r14
0x180002b43  mov     edi, [r14]
0x180002b46  mov     dword ptr [rsp+488h+var_3C8+4], edi
0x180002b4d  lea     rcx, [rsp+488h+var_168]
0x180002b55  mov     qword ptr [rsp+488h+var_3C8+8], rcx
0x180002b5d  lea     r12, [rax+8]
0x180002b61  mov     [rsp+488h+var_2C8], r12
0x180002b69  mov     r8d, edi
0x180002b6c  shl     r8, 4; Size
0x180002b70  mov     rdx, [r12]; Src
0x180002b74  lea     rcx, [rsp+488h+var_168]; void *
0x180002b7c  call    memcpy_0
0x180002b81  mov     dword ptr [rsp+488h+var_378], ebx
0x180002b88  mov     dword ptr [rsp+488h+var_378+4], edi
0x180002b8f  lea     r10, [rsp+488h+var_1F8]
0x180002b97  mov     qword ptr [rsp+488h+var_378+8], r10
0x180002b9f  mov     r9d, esi
0x180002ba2  mov     ebx, [rsp+488h+arg_20]
0x180002ba9  test    edi, edi
0x180002bab  jz      short loc_180002C08
0x180002bad  mov     r11d, ebx
0x180002bb0  and     r11d, 100h
0x180002bb7  mov     eax, r9d
0x180002bba  mov     r8d, r9d
0x180002bbd  add     r8, r8
0x180002bc0  lea     rdx, ds:0[rax*8]
0x180002bc8  mov     rax, [r12]
0x180002bcc  mov     ecx, [rax+r8*8+4]
0x180002bd1  mov     [rdx+r10+4], ecx
0x180002bd6  mov     rax, [r12]
0x180002bda  mov     ecx, [rax+r8*8]
0x180002bde  mov     rax, qword ptr [rsp+488h+var_378+8]
0x180002be6  mov     [rdx+rax], ecx
0x180002be9  test    r11d, r11d
0x180002bec  jz      short loc_180002BF6
0x180002bee  mov     [rsp+r8*8+488h+var_160], rsi
0x180002bf6  inc     r9d
0x180002bf9  cmp     r9d, [r14]
0x180002bfc  jnb     short loc_180002C08
0x180002bfe  mov     r10, qword ptr [rsp+488h+var_378+8]
0x180002c06  jmp     short loc_180002BB7
0x180002c08  xorps   xmm0, xmm0
0x180002c0b  movups  [rsp+488h+ThreadInformation], xmm0
0x180002c13  movups  [rsp+488h+var_268], xmm0
0x180002c1b  movups  [rsp+488h+var_258], xmm0
0x180002c23  mov     [rsp+488h+ReturnLength], rsi; ReturnLength
0x180002c28  mov     r15d, 30h ; '0'
0x180002c2e  mov     r9d, r15d; ThreadInformationLength
0x180002c31  lea     r8, [rsp+488h+ThreadInformation]; ThreadInformation
0x180002c39  xor     edx, edx; ThreadInformationClass
0x180002c3b  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180002c42  call    cs:__imp_NtQueryInformationThread
0x180002c48  mov     edi, eax
0x180002c4a  test    eax, eax
0x180002c4c  js      loc_1800033C8
0x180002c52  mov     rax, qword ptr [rsp+488h+var_268]
0x180002c5a  mov     qword ptr [rsp+488h+var_228], rax
0x180002c62  mov     rax, qword ptr [rsp+488h+var_268+8]
0x180002c6a  mov     qword ptr [rsp+488h+var_228+8], rax
0x180002c72  mov     [rsp+488h+var_2A0], r13
0x180002c7a  mov     r10, cs:SecpLsaInprocDispatch
0x180002c81  test    r10, r10
0x180002c84  jz      loc_180002D80
0x180002c8a  mov     [rsp+488h+var_3E8], rsi
0x180002c92  mov     [rsp+488h+var_3F0], rsi
0x180002c9a  lea     rax, [rsp+488h+var_3D8]
0x180002ca2  mov     [rsp+488h+var_3F8], rax
0x180002caa  mov     rax, [rsp+488h+var_338]
0x180002cb2  mov     [rsp+488h+var_400], rax
0x180002cba  mov     rax, [rsp+488h+var_3A0]
0x180002cc2  mov     [rsp+488h+var_408], rax
0x180002cca  lea     rax, [rsp+488h+var_248]
0x180002cd2  mov     [rsp+488h+var_410], rax
0x180002cd7  mov     rax, [rsp+488h+var_330]
0x180002cdf  mov     [rsp+488h+var_418], rax
0x180002ce4  lea     rax, [rsp+488h+var_3B8]
0x180002cec  mov     [rsp+488h+var_420], rax
0x180002cf1  lea     rax, [rsp+488h+var_3C8]
0x180002cf9  mov     [rsp+488h+var_428], rax
0x180002cfe  lea     rax, [rsp+488h+var_378]
0x180002d06  mov     [rsp+488h+var_430], rax
0x180002d0b  mov     [rsp+488h+var_438], r13
0x180002d10  mov     rax, [rsp+488h+var_328]
0x180002d18  mov     [rsp+488h+var_440], rax
0x180002d1d  mov     rax, [rsp+488h+var_320]
0x180002d25  mov     [rsp+488h+var_448], rax
0x180002d2a  mov     eax, [rsp+488h+arg_28]
0x180002d31  mov     [rsp+488h+var_450], eax
0x180002d35  mov     dword ptr [rsp+488h+var_458], ebx
0x180002d39  lea     rax, [rsp+488h+var_218]
0x180002d41  mov     [rsp+488h+var_460], rax
0x180002d46  lea     rax, [rsp+488h+var_238]
0x180002d4e  mov     [rsp+488h+ReturnLength], rax
0x180002d53  mov     r9, [rsp+488h+var_3A8]
0x180002d5b  mov     r8, [rsp+488h+var_3B0]
0x180002d63  lea     rdx, [rsp+488h+var_228]
0x180002d6b  xor     ecx, ecx
0x180002d6d  mov     rax, [r10+18h]
0x180002d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d76  mov     edi, eax
0x180002d78  jmp     loc_1800030E8
0x180002d80  xor     r13b, r13b
0x180002d83  xorps   xmm0, xmm0
0x180002d86  movups  xmmword ptr [rsp+488h+ActivityId.Data1], xmm0
0x180002d8e  lea     rdx, [rsp+488h+ActivityId]; ActivityId
0x180002d96  mov     ecx, 1; ControlCode
0x180002d9b  call    cs:__imp_EventActivityIdControl
0x180002da1  lea     rax, [rsp+488h+var_368]
0x180002da9  mov     [rsp+488h+var_3E0], rax
0x180002db1  lea     rax, [rsp+488h+var_308]
0x180002db9  mov     [rsp+488h+var_3E8], rax
0x180002dc1  lea     rax, [rsp+488h+var_3D8]
0x180002dc9  mov     [rsp+488h+var_3F0], rax
0x180002dd1  mov     rax, [rsp+488h+var_338]
0x180002dd9  mov     [rsp+488h+var_3F8], rax
0x180002de1  mov     rax, [rsp+488h+var_3A0]
0x180002de9  mov     [rsp+488h+var_400], rax
0x180002df1  lea     rax, [rsp+488h+var_248]
0x180002df9  mov     [rsp+488h+var_408], rax
0x180002e01  mov     rax, [rsp+488h+var_330]
0x180002e09  mov     [rsp+488h+var_410], rax
0x180002e0e  lea     rax, [rsp+488h+var_3B8]
0x180002e16  mov     [rsp+488h+var_418], rax
  ... truncated ...
```
