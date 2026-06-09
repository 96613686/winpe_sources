# WebSendHttpRequestEntity

- ea: `0x180017550`
- end: `0x1800180d8`
- name: `WebSendHttpRequestEntity`
- size: `2952`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180017550`
- `0x1800180e0`
- `0x180018370`
- `0x18001b150`
- `0x18001f9e8`
- `0x180024390`
- `0x18002e460`
- `0x180035edc`
- `0x18005db14`
- `0x1800722f0`
- `0x180083b8c`
- `0x180092500`
- `0x180092564`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180017a1b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180017ca0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180017a1b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180017ca0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017c68`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017c68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017c49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017c49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017861`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017861`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180017660`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180017660`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180017680`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180017680`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800176d4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800176f9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180017bb8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800176d4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800176f9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180017bb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017a3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001802b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017a3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001802b`

## pseudocode

```c
__int64 __fastcall WebSendHttpRequestEntity(
        unsigned __int64 a1,
        int a2,
        char *a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6)
{
  unsigned int v6; // r12d
  int v8; // r14d
  char *v10; // r9
  RTL_SRWLOCK *v11; // rbx
  RTL_SRWLOCK *v12; // rdi
  char *Ptr; // rbx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  int v17; // r9d
  __int64 v18; // rdi
  __int64 v19; // r13
  int v20; // eax
  unsigned int v21; // esi
  int v22; // eax
  unsigned int v23; // edx
  int v24; // r12d
  int v25; // ecx
  bool v26; // r14
  unsigned __int64 v27; // rdi
  __int64 HttpRequestSendTracker; // rax
  __int64 v29; // r8
  __int64 v30; // rsi
  unsigned int v31; // ecx
  bool v32; // zf
  PVOID *v33; // rdx
  __int64 v34; // r8
  unsigned int locked; // edi
  unsigned int v36; // esi
  __int64 v37; // rax
  unsigned __int64 v38; // rax
  void *v39; // r14
  HANDLE CurrentThread; // rax
  __int64 v41; // r8
  DWORD LastError; // eax
  void *TokenHandle; // [rsp+70h] [rbp-308h] BYREF
  char *v45; // [rsp+78h] [rbp-300h] BYREF
  __int64 v46; // [rsp+80h] [rbp-2F8h] BYREF
  char *v47; // [rsp+88h] [rbp-2F0h] BYREF
  char *v48; // [rsp+90h] [rbp-2E8h] BYREF
  char *v49; // [rsp+98h] [rbp-2E0h] BYREF
  char *v50; // [rsp+A0h] [rbp-2D8h] BYREF
  __int64 v51; // [rsp+A8h] [rbp-2D0h] BYREF
  char *v52; // [rsp+B0h] [rbp-2C8h] BYREF
  unsigned int v53; // [rsp+B8h] [rbp-2C0h] BYREF
  int v54; // [rsp+C0h] [rbp-2B8h] BYREF
  char *v55; // [rsp+C8h] [rbp-2B0h] BYREF
  __int64 v56; // [rsp+D0h] [rbp-2A8h] BYREF
  __int64 v57; // [rsp+D8h] [rbp-2A0h] BYREF
  int v58; // [rsp+E0h] [rbp-298h] BYREF
  unsigned int v59; // [rsp+E8h] [rbp-290h] BYREF
  int v60; // [rsp+F0h] [rbp-288h] BYREF
  int v61; // [rsp+F8h] [rbp-280h] BYREF
  unsigned int v62; // [rsp+100h] [rbp-278h] BYREF
  int v63; // [rsp+108h] [rbp-270h] BYREF
  __int128 v64; // [rsp+110h] [rbp-268h]
  GUID ActivityId; // [rsp+120h] [rbp-258h] BYREF
  int v66; // [rsp+130h] [rbp-248h]
  unsigned __int64 v67; // [rsp+138h] [rbp-240h] BYREF
  void *v68; // [rsp+140h] [rbp-238h] BYREF
  __int64 v69; // [rsp+148h] [rbp-230h] BYREF
  unsigned __int64 v70; // [rsp+150h] [rbp-228h] BYREF
  __int64 v71; // [rsp+158h] [rbp-220h] BYREF
  char v72[16]; // [rsp+160h] [rbp-218h] BYREF
  char **v73; // [rsp+170h] [rbp-208h]
  __int64 v74; // [rsp+178h] [rbp-200h]
  unsigned __int64 *v75; // [rsp+180h] [rbp-1F8h]
  __int64 v76; // [rsp+188h] [rbp-1F0h]
  int *v77; // [rsp+190h] [rbp-1E8h]
  __int64 v78; // [rsp+198h] [rbp-1E0h]
  __int64 *v79; // [rsp+1A0h] [rbp-1D8h]
  __int64 v80; // [rsp+1A8h] [rbp-1D0h]
  int *v81; // [rsp+1B0h] [rbp-1C8h]
  __int64 v82; // [rsp+1B8h] [rbp-1C0h]
  __int64 *v83; // [rsp+1C0h] [rbp-1B8h]
  __int64 v84; // [rsp+1C8h] [rbp-1B0h]
  int *v85; // [rsp+1D0h] [rbp-1A8h]
  __int64 v86; // [rsp+1D8h] [rbp-1A0h]
  char v87[16]; // [rsp+1E0h] [rbp-198h] BYREF
  char **v88; // [rsp+1F0h] [rbp-188h]
  __int64 v89; // [rsp+1F8h] [rbp-180h]
  char **v90; // [rsp+200h] [rbp-178h]
  __int64 v91; // [rsp+208h] [rbp-170h]
  int *v92; // [rsp+210h] [rbp-168h]
  __int64 v93; // [rsp+218h] [rbp-160h]
  char **v94; // [rsp+220h] [rbp-158h]
  __int64 v95; // [rsp+228h] [rbp-150h]
  __int64 *v96; // [rsp+230h] [rbp-148h]
  __int64 v97; // [rsp+238h] [rbp-140h]
  __int64 *v98; // [rsp+240h] [rbp-138h]
  __int64 v99; // [rsp+248h] [rbp-130h]
  __int64 *v100; // [rsp+250h] [rbp-128h]
  __int64 v101; // [rsp+258h] [rbp-120h]
  char v102[16]; // [rsp+260h] [rbp-118h] BYREF
  char **v103; // [rsp+270h] [rbp-108h]
  __int64 v104; // [rsp+278h] [rbp-100h]
  char **v105; // [rsp+280h] [rbp-F8h]
  __int64 v106; // [rsp+288h] [rbp-F0h]
  __int64 *v107; // [rsp+290h] [rbp-E8h]
  __int64 v108; // [rsp+298h] [rbp-E0h]
  int *v109; // [rsp+2A0h] [rbp-D8h]
  __int64 v110; // [rsp+2A8h] [rbp-D0h]
  int *v111; // [rsp+2B0h] [rbp-C8h]
  __int64 v112; // [rsp+2B8h] [rbp-C0h]
  char v113[16]; // [rsp+2C0h] [rbp-B8h] BYREF
  void **v114; // [rsp+2D0h] [rbp-A8h]
  __int64 v115; // [rsp+2D8h] [rbp-A0h]
  __int64 *v116; // [rsp+2E0h] [rbp-98h]
  __int64 v117; // [rsp+2E8h] [rbp-90h]
  unsigned int *v118; // [rsp+2F0h] [rbp-88h]
  __int64 v119; // [rsp+2F8h] [rbp-80h]
  char v120[16]; // [rsp+300h] [rbp-78h] BYREF
  __int64 *v121; // [rsp+310h] [rbp-68h]
  __int64 v122; // [rsp+318h] [rbp-60h]
  unsigned int *v123; // [rsp+320h] [rbp-58h]
  __int64 v124; // [rsp+328h] [rbp-50h]

  v6 = a4;
  v53 = a4;
  v55 = a3;
  v8 = a2;
  v54 = a2;
  v45 = (char *)a1;
  v56 = a5;
  v57 = a6;
  if ( !a5 )
    return (unsigned int)WapSynchronousSendHttpRequestEntity(a1);
  v64 = 0;
  ActivityId = 0;
  v66 = 0;
  if ( !WaHandleTableInitialized )
    return 6;
  if ( (a1 & 0xF0000000) != 0x30000000 )
    return 6;
  v10 = (char *)WaHandleTable + 64 * (unsigned __int64)BYTE4(a1);
  if ( (unsigned int)(unsigned __int16)(HIDWORD(a1) >> 8) >= *((_DWORD *)v10 + 4) )
    return 6;
  v11 = (RTL_SRWLOCK *)(32 * HIBYTE(a1) + *(_QWORD *)(*((_QWORD *)v10 + 1) + 8LL * (unsigned __int16)(HIDWORD(a1) >> 8)));
  if ( v11[3].Ptr != (PVOID)a1 )
    return 6;
  v12 = v11 + 2;
  AcquireSRWLockShared(v11 + 2);
  if ( v11[3].Ptr == (PVOID)a1 )
  {
    Ptr = (char *)v11->Ptr;
    _InterlockedIncrement((volatile signed __int32 *)Ptr + 1);
  }
  else
  {
    Ptr = 0;
  }
  ReleaseSRWLockShared(v12);
  if ( !Ptr )
    return 6;
  v64 = 0;
  ActivityId = 0;
  v66 = 0;
  v64 = *(_OWORD *)(Ptr + 4572);
  if ( !EventActivityIdControl(1u, &ActivityId) )
  {
    if ( !(_BYTE)v66 )
      LOBYTE(v66) = EventActivityIdControl(2u, (LPGUID)(Ptr + 4572)) == 0;
    if ( Microsoft_Windows_Networking_CorrelationEnabled )
      EtwEx_tidActivityInfoTransfer(v15, v14, Ptr + 4572, &ActivityId);
  }
  if ( !(_BYTE)v66 )
    ActivityId = 0;
  if ( (Microsoft_Windows_WebIOEnableBits & 0x80u) != 0 )
  {
    v63 = 0;
    v51 = a6;
    v59 = v6;
    v52 = a3;
    v58 = v8;
    v67 = a1;
    v47 = Ptr;
    v73 = &v47;
    v74 = 8;
    v75 = &v67;
    v76 = 8;
    v77 = &v58;
    v78 = 4;
    v79 = (__int64 *)&v52;
    v80 = 8;
    v81 = (int *)&v59;
    v82 = 4;
    v83 = &v51;
    v84 = 8;
    v85 = &v63;
    v86 = 4;
    McGenEventWrite_EventWriteTransfer(&WEB_ETW_PROVIDER_ID_Context, HttpSendHttpRequestEntity, v16, 8, v72);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(Ptr + 8));
  v18 = *((_QWORD *)Ptr + 9);
  if ( *(_BYTE *)(v18 + 33) )
  {
    v19 = -1;
    goto LABEL_20;
  }
  v39 = *(void **)(v18 + 112);
  TokenHandle = (void *)-1LL;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
  {
    v19 = (__int64)TokenHandle;
LABEL_68:
    v21 = 0;
    goto LABEL_69;
  }
  LastError = GetLastError();
  v21 = LastError;
  if ( LastError )
  {
    if ( LastError == 1008 )
    {
      v19 = 0;
      TokenHandle = 0;
      goto LABEL_68;
    }
  }
  else
  {
    v21 = 1359;
  }
  v19 = -1;
  TokenHandle = (void *)-1LL;
LABEL_69:
  if ( v21 )
  {
LABEL_73:
    if ( v19 != -1 && (Microsoft_Windows_WebIOEnableBits & 0x20000) != 0 )
    {
      v62 = v21;
      v69 = v19;
      v68 = v39;
      v114 = &v68;
      v115 = 8;
      v116 = &v69;
      v117 = 8;
      v118 = &v62;
      v119 = 4;
      McGenEventWrite_EventWriteTransfer(&WEB_ETW_PROVIDER_ID_Context, ThreadTokenSet, v41, 4, v113);
    }
    goto LABEL_76;
  }
  if ( v39 || v19 )
  {
    v21 = 0;
    if ( !SetThreadToken(0, v39) )
      v21 = WaGetLastError();
    goto LABEL_73;
  }
  v19 = -1;
LABEL_76:
  if ( v21 )
  {
    if ( (unsigned __int64)(v19 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle((HANDLE)v19);
    v19 = -1;
    if ( (xmmword_1800AD710 & 2) != 0 )
      WPP_SF_qD(513, 17, WPP_247e30510a1b3c47cfbd7b690ee005cd_Traceguids, v18, v21);
    goto LABEL_46;
  }
  v8 = v54;
LABEL_20:
  if ( Ptr[56] || (v20 = *((_DWORD *)Ptr + 12)) == 0 )
  {
    v21 = *((_DWORD *)Ptr + 13);
    goto LABEL_46;
  }
  if ( v20 <= 1 )
  {
    v21 = 5023;
    goto LABEL_103;
  }
  if ( (v8 & 0x7FFFFFFF) != 0 )
  {
    v21 = 87;
    v22 = 87;
    v23 = 0;
  }
  else
  {
    if ( v8 >= 0 )
    {
      if ( !v55 || !v6 )
      {
        v21 = 87;
        v22 = 87;
        v23 = 0;
        goto LABEL_28;
      }
      goto LABEL_89;
    }
    if ( !v55 || !v6 )
    {
LABEL_89:
      v23 = 0;
      v22 = 0;
      v21 = 87;
      goto LABEL_28;
    }
    v21 = 87;
    v22 = 87;
    v23 = 0;
  }
LABEL_28:
  v24 = v8;
  if ( v22 )
  {
    v21 = v22;
    v6 = v53;
  }
  else
  {
    v25 = *((_DWORD *)Ptr + 450);
    v26 = (v25 & 0x40000000) == 0 && v25 >= 0;
    v27 = 0;
    while ( 1 )
    {
      if ( v23 >= v53 )
      {
        if ( !v26 || v27 <= *((_QWORD *)Ptr + 227) )
        {
          LOBYTE(v17) = 1;
          HttpRequestSendTracker = WapCreateHttpRequestSendTracker((_DWORD)Ptr, (_DWORD)v55, v53, v17, v56, v57);
          v30 = HttpRequestSendTracker;
          if ( HttpRequestSendTracker )
          {
            *((_DWORD *)Ptr + 76) |= 2u;
            v31 = *((_DWORD *)Ptr + 76);
            if ( v26 )
            {
              v32 = *((_QWORD *)Ptr + 227) == v27;
              *((_QWORD *)Ptr + 227) -= v27;
              if ( v32 )
              {
                v31 |= 0x10u;
                *((_DWORD *)Ptr + 76) = v31;
              }
            }
            if ( v24 < 0 )
            {
              v31 |= 0x10u;
              *((_DWORD *)Ptr + 76) = v31;
            }
            if ( (Microsoft_Windows_WebIOEnableBits & 0x100) != 0 )
            {
              v60 = (v31 >> 4) & 1;
              v61 = *(unsigned __int8 *)(HttpRequestSendTracker + 65);
              v70 = v27;
              v49 = v55;
              v50 = Ptr;
              v103 = &v50;
              v104 = 8;
              v105 = &v49;
              v106 = 8;
              v107 = (__int64 *)&v70;
              v108 = 8;
              v109 = &v61;
              v110 = 4;
              v111 = &v60;
              v112 = 4;
              McGenEventWrite_EventWriteTransfer(&WEB_ETW_PROVIDER_ID_Context, HttpQueueRequestEntity, v29, 6, v102);
            }
            v33 = (PVOID *)*((_QWORD *)Ptr + 234);
            if ( *v33 != Ptr + 1864 )
              __fastfail(3u);
            *(_QWORD *)(v30 + 16) = Ptr + 1864;
            *(_QWORD *)(v30 + 24) = v33;
            *v33 = (PVOID)(v30 + 16);
            *((_QWORD *)Ptr + 234) = v30 + 16;
            v21 = 0;
          }
          else
          {
            v21 = 8;
          }
        }
        goto LABEL_45;
      }
      if ( *(_DWORD *)&v55[24 * v23] )
        goto LABEL_45;
      if ( !*(_QWORD *)&v55[24 * v23 + 8] )
        goto LABEL_45;
      v37 = *(_QWORD *)&v55[24 * v23 + 16];
      if ( !v37 )
        goto LABEL_45;
      v38 = v27 + v37;
      if ( v38 < v27 )
        break;
      v27 = v38;
      ++v23;
    }
    if ( (xmmword_1800AD710 & 2) != 0 )
      WPP_SF_(513, 12, WPP_f51a302de63d353b45f08d7caef3fd03_Traceguids);
    v21 = 534;
LABEL_45:
    v6 = v53;
  }
LABEL_46:
  if ( v21 )
  {
LABEL_103:
    locked = WaCancelLockedHttpRequest(Ptr, v21);
    goto LABEL_48;
  }
  WapSendHttpRequestEntities(Ptr);
  locked = 997;
LABEL_48:
  LODWORD(v56) = _InterlockedDecrement((volatile signed __int32 *)Ptr + 1);
  if ( !(_DWORD)v56 )
    WapDestroyHttpRequest(Ptr);
  v36 = 0;
  if ( v19 != -1 )
  {
    if ( !SetThreadToken(0, (HANDLE)v19) )
      v36 = WaGetLastError();
    if ( v19 )
      CloseHandle((HANDLE)v19);
    if ( (Microsoft_Windows_WebIOEnableBits & 0x20000) != 0 )
    {
      v53 = v36;
      v71 = v19;
      v121 = &v71;
      v122 = 8;
      v123 = &v53;
      v124 = 4;
      McGenEventWrite_EventWriteTransfer(&WEB_ETW_PROVIDER_ID_Context, ThreadTokenRestore, v34, 3, v120);
    }
  }
  if ( (Microsoft_Windows_WebIOEnableBits & 0x80u) != 0 )
  {
    LODWORD(v56) = locked;
    v46 = v57;
    LODWORD(v57) = v6;
    v48 = v55;
    v55 = v45;
    v45 = Ptr;
    v88 = &v45;
    v89 = 8;
    v90 = &v55;
    v91 = 8;
    v92 = &v54;
    v93 = 4;
    v94 = &v48;
    v95 = 8;
    v96 = &v57;
    v97 = 4;
    v98 = &v46;
    v99 = 8;
    v100 = &v56;
    v101 = 4;
    McGenEventWrite_EventWriteTransfer(&WEB_ETW_PROVIDER_ID_Context, "l", v34, 8, v87);
  }
  if ( (_BYTE)v66 )
    EventActivityIdControl(2u, &ActivityId);
  return locked;
}

```

## disassembly

```asm
0x180017550  push    rbx
0x180017552  push    rsi
0x180017553  push    rdi
0x180017554  push    r12
0x180017556  push    r13
0x180017558  push    r14
0x18001755a  push    r15
0x18001755c  sub     rsp, 340h
0x180017563  mov     rax, cs:__security_cookie
0x18001756a  xor     rax, rsp
0x18001756d  mov     [rsp+378h+var_48], rax
0x180017575  mov     r12d, r9d
0x180017578  mov     [rsp+378h+var_2C0], r9d
0x180017580  mov     r15, r8
0x180017583  mov     [rsp+378h+var_2B0], r8
0x18001758b  mov     r14d, edx
0x18001758e  mov     [rsp+378h+var_2B8], edx
0x180017595  mov     rsi, rcx
0x180017598  mov     [rsp+378h+var_300], rcx
0x18001759d  mov     rax, [rsp+378h+arg_20]
0x1800175a5  mov     [rsp+378h+var_2A8], rax
0x1800175ad  mov     r13, [rsp+378h+arg_28]
0x1800175b5  mov     [rsp+378h+var_2A0], r13
0x1800175bd  xor     ecx, ecx
0x1800175bf  mov     [rsp+378h+var_330], ecx
0x1800175c3  test    rax, rax
0x1800175c6  jz      loc_180017FCB
0x1800175cc  xorps   xmm0, xmm0
0x1800175cf  xor     eax, eax
0x1800175d1  movups  [rsp+378h+var_268], xmm0
0x1800175d9  movups  xmmword ptr [rsp+378h+ActivityId.Data1], xmm0
0x1800175e1  mov     [rsp+378h+var_248], eax
0x1800175e8  cmp     cs:WaHandleTableInitialized, al
0x1800175ee  jz      loc_1800180A3
0x1800175f4  mov     eax, esi
0x1800175f6  and     eax, 0F0000000h
0x1800175fb  cmp     eax, 30000000h
0x180017600  jnz     loc_1800180A3
0x180017606  mov     rax, rsi
0x180017609  shr     rax, 20h
0x18001760d  mov     r8, rax
0x180017610  movzx   r9d, al
0x180017614  shl     r9, 6
0x180017618  add     r9, cs:WaHandleTable
0x18001761f  shr     eax, 8
0x180017622  movzx   eax, ax
0x180017625  cmp     eax, [r9+10h]
0x180017629  jnb     loc_1800180A3
0x18001762f  mov     rax, rsi
0x180017632  shr     rax, 28h
0x180017636  movzx   edx, ax
0x180017639  mov     rax, [r9+8]
0x18001763d  mov     rcx, r8
0x180017640  shr     rcx, 18h
0x180017644  shl     rcx, 5
0x180017648  mov     rbx, [rax+rdx*8]
0x18001764c  add     rbx, rcx
0x18001764f  cmp     [rbx+18h], rsi
0x180017653  jnz     loc_1800180A3
0x180017659  lea     rdi, [rbx+10h]
0x18001765d  mov     rcx, rdi; SRWLock
0x180017660  call    cs:__imp_AcquireSRWLockShared
0x180017667  nop     dword ptr [rax+rax+00h]
0x18001766c  cmp     [rbx+18h], rsi
0x180017670  jnz     loc_180017CE9
0x180017676  mov     rbx, [rbx]
0x180017679  lock inc dword ptr [rbx+4]
0x18001767d  mov     rcx, rdi; SRWLock
0x180017680  call    cs:__imp_ReleaseSRWLockShared
0x180017687  nop     dword ptr [rax+rax+00h]
0x18001768c  test    rbx, rbx
0x18001768f  jz      loc_1800180A3
0x180017695  xorps   xmm0, xmm0
0x180017698  xor     eax, eax
0x18001769a  movups  [rsp+378h+var_268], xmm0
0x1800176a2  movups  xmmword ptr [rsp+378h+ActivityId.Data1], xmm0
0x1800176aa  mov     [rsp+378h+var_248], eax
0x1800176b1  movups  xmm0, xmmword ptr [rbx+11DCh]
0x1800176b8  movups  [rsp+378h+var_268], xmm0
0x1800176c0  mov     byte ptr [rsp+378h+var_248], al
0x1800176c7  lea     rdx, [rsp+378h+ActivityId]; ActivityId
0x1800176cf  mov     ecx, 1; ControlCode
0x1800176d4  call    cs:__imp_EventActivityIdControl
0x1800176db  nop     dword ptr [rax+rax+00h]
0x1800176e0  test    eax, eax
0x1800176e2  jnz     short loc_18001771F
0x1800176e4  cmp     byte ptr [rsp+378h+var_248], al
0x1800176eb  jnz     short loc_180017711
0x1800176ed  lea     rdx, [rbx+11DCh]; ActivityId
0x1800176f4  mov     ecx, 2; ControlCode
0x1800176f9  call    cs:__imp_EventActivityIdControl
0x180017700  nop     dword ptr [rax+rax+00h]
0x180017705  test    eax, eax
0x180017707  jnz     short loc_180017711
0x180017709  mov     byte ptr [rsp+378h+var_248], 1
0x180017711  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x180017717  test    eax, eax
0x180017719  jnz     loc_180017F70
0x18001771f  cmp     byte ptr [rsp+378h+var_248], 0
0x180017727  jz      loc_180017C23
0x18001772d  cmp     byte ptr cs:Microsoft_Windows_WebIOEnableBits, 0
0x180017734  jge     loc_18001785D
0x18001773a  xor     ecx, ecx
0x18001773c  mov     [rsp+378h+var_270], ecx
0x180017743  mov     [rsp+378h+var_2D0], r13
0x18001774b  mov     [rsp+378h+var_290], r12d
0x180017753  mov     [rsp+378h+var_2C8], r15
0x18001775b  mov     [rsp+378h+var_298], r14d
0x180017763  mov     [rsp+378h+var_240], rsi
0x18001776b  mov     [rsp+378h+var_2F0], rbx
0x180017773  lea     rax, [rsp+378h+var_2F0]
0x18001777b  mov     [rsp+378h+var_208], rax
0x180017783  mov     [rsp+378h+var_200], 8
0x18001778f  lea     rax, [rsp+378h+var_240]
0x180017797  mov     [rsp+378h+var_1F8], rax
0x18001779f  mov     [rsp+378h+var_1F0], 8
0x1800177ab  lea     rax, [rsp+378h+var_298]
0x1800177b3  mov     [rsp+378h+var_1E8], rax
0x1800177bb  mov     [rsp+378h+var_1E0], 4
0x1800177c7  lea     rax, [rsp+378h+var_2C8]
0x1800177cf  mov     [rsp+378h+var_1D8], rax
0x1800177d7  mov     [rsp+378h+var_1D0], 8
0x1800177e3  lea     rax, [rsp+378h+var_290]
0x1800177eb  mov     [rsp+378h+var_1C8], rax
0x1800177f3  mov     [rsp+378h+var_1C0], 4
0x1800177ff  lea     rax, [rsp+378h+var_2D0]
0x180017807  mov     [rsp+378h+var_1B8], rax
0x18001780f  mov     [rsp+378h+var_1B0], 8
0x18001781b  lea     rax, [rsp+378h+var_270]
0x180017823  mov     [rsp+378h+var_1A8], rax
0x18001782b  mov     [rsp+378h+var_1A0], 4
0x180017837  lea     rax, [rsp+378h+var_218]
0x18001783f  mov     [rsp+378h+var_358], rax
0x180017844  mov     r9d, 8
0x18001784a  lea     rdx, HttpSendHttpRequestEntity
0x180017851  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x180017858  call    McGenEventWrite_EventWriteTransfer
0x18001785d  lea     rcx, [rbx+8]; lpCriticalSection
0x180017861  call    cs:__imp_EnterCriticalSection
0x180017868  nop     dword ptr [rax+rax+00h]
0x18001786d  mov     rdi, [rbx+48h]
0x180017871  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180017878  cmp     byte ptr [rdi+21h], 0
0x18001787c  jz      loc_180017C33
0x180017882  mov     r13, r15
0x180017885  cmp     byte ptr [rbx+38h], 0
0x180017889  jnz     loc_180017FA0
0x18001788f  mov     eax, [rbx+30h]
0x180017892  test    eax, eax
0x180017894  jz      loc_180017FA0
0x18001789a  cmp     eax, 1
0x18001789d  jle     loc_180018039
0x1800178a3  test    r14d, 7FFFFFFFh
0x1800178aa  jnz     loc_180017FA8
0x1800178b0  test    r14d, r14d
0x1800178b3  js      loc_180017F44
0x1800178b9  cmp     [rsp+378h+var_2B0], 0
0x1800178c2  jz      short loc_1800178CD
0x1800178c4  test    r12d, r12d
0x1800178c7  jnz     loc_180017F53
0x1800178cd  mov     esi, 57h ; 'W'
0x1800178d2  mov     eax, esi
0x1800178d4  xor     edx, edx
0x1800178d6  mov     r12d, r14d
0x1800178d9  test    eax, eax
0x1800178db  jnz     loc_180017F61
0x1800178e1  mov     [rsp+378h+var_318], rdx
0x1800178e6  mov     [rsp+378h+var_334], edx
0x1800178ea  mov     ecx, [rbx+708h]
0x1800178f0  bt      ecx, 1Eh
0x1800178f4  jb      loc_180018066
0x1800178fa  mov     al, 1
0x1800178fc  movzx   r14d, al
0x180017900  test    ecx, ecx
0x180017902  cmovs   r14d, edx
0x180017906  mov     rdi, rdx
0x180017909  mov     [rsp+378h+var_318], rdx
0x18001790e  mov     r8d, [rsp+378h+var_2C0]
0x180017916  mov     [rsp+378h+var_334], edx
0x18001791a  cmp     edx, r8d
0x18001791d  jb      loc_180017BC9
0x180017923  test    r14b, r14b
0x180017926  jz      short loc_180017935
0x180017928  cmp     rdi, [rbx+718h]
0x18001792f  ja      loc_1800179D0
0x180017935  mov     rax, [rsp+378h+var_2A0]
0x18001793d  mov     [rsp+378h+var_350], rax
0x180017942  mov     rax, [rsp+378h+var_2A8]
0x18001794a  mov     [rsp+378h+var_358], rax
0x18001794f  mov     r9b, 1
0x180017952  mov     rdx, [rsp+378h+var_2B0]
0x18001795a  mov     rcx, rbx
0x18001795d  call    WapCreateHttpRequestSendTracker
0x180017962  mov     rsi, rax
0x180017965  test    rax, rax
0x180017968  jz      loc_180017CDF
0x18001796e  or      dword ptr [rbx+130h], 2
0x180017975  mov     ecx, [rbx+130h]
0x18001797b  test    r14b, r14b
0x18001797e  jz      short loc_180017992
0x180017980  sub     [rbx+718h], rdi
0x180017987  jnz     short loc_180017992
0x180017989  or      ecx, 10h
0x18001798c  mov     [rbx+130h], ecx
0x180017992  test    r12d, r12d
0x180017995  js      loc_180018089
0x18001799b  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+1, 1
0x1800179a2  jnz     loc_180017D62
0x1800179a8  lea     rcx, [rbx+748h]
0x1800179af  mov     rdx, [rcx+8]
0x1800179b3  cmp     [rdx], rcx
0x1800179b6  jnz     loc_180017E8F
0x1800179bc  lea     rax, [rsi+10h]
0x1800179c0  mov     [rax], rcx
0x1800179c3  mov     [rax+8], rdx
0x1800179c7  mov     [rdx], rax
0x1800179ca  mov     [rcx+8], rax
0x1800179ce  xor     esi, esi
0x1800179d0  mov     r12d, [rsp+378h+var_2C0]
0x1800179d8  test    esi, esi
0x1800179da  jnz     loc_18001803E
0x1800179e0  mov     rcx, rbx
0x1800179e3  call    WapSendHttpRequestEntities
0x1800179e8  mov     edi, 3E5h
0x1800179ed  lock xadd [rbx+4], r15d
0x1800179f3  sub     r15d, 1
0x1800179f7  mov     dword ptr [rsp+378h+var_2A8], r15d
0x1800179ff  jz      loc_180017C16
0x180017a05  xor     r14d, r14d
0x180017a08  mov     esi, r14d
0x180017a0b  mov     [rsp+378h+var_320], r14d
0x180017a10  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x180017a14  jz      short loc_180017A5A
0x180017a16  mov     rdx, r13; Token
0x180017a19  xor     ecx, ecx; Thread
0x180017a1b  call    cs:__imp_SetThreadToken
0x180017a22  nop     dword ptr [rax+rax+00h]
0x180017a27  test    eax, eax
0x180017a29  jz      loc_180018097
0x180017a2f  mov     [rsp+378h+var_320], esi
0x180017a33  test    r13, r13
0x180017a36  jz      short loc_180017A47
0x180017a38  mov     rcx, r13; hObject
0x180017a3b  call    cs:__imp_CloseHandle
0x180017a42  nop     dword ptr [rax+rax+00h]
0x180017a47  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x180017a4b  jz      short loc_180017A5A
0x180017a4d  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+2, 2
0x180017a54  jnz     loc_180017CF0
0x180017a5a  cmp     byte ptr cs:Microsoft_Windows_WebIOEnableBits, r14b
0x180017a61  jge     loc_180017B9D
0x180017a67  mov     dword ptr [rsp+378h+var_2A8], edi
0x180017a6e  mov     rax, [rsp+378h+var_2A0]
0x180017a76  mov     [rsp+378h+var_2F8], rax
0x180017a7e  mov     dword ptr [rsp+378h+var_2A0], r12d
0x180017a86  mov     rax, [rsp+378h+var_2B0]
0x180017a8e  mov     [rsp+378h+var_2E8], rax
0x180017a96  mov     eax, [rsp+378h+var_2B8]
0x180017a9d  mov     [rsp+378h+var_2B8], eax
0x180017aa4  mov     rax, [rsp+378h+var_300]
0x180017aa9  mov     [rsp+378h+var_2B0], rax
0x180017ab1  mov     [rsp+378h+var_300], rbx
0x180017ab6  lea     rax, [rsp+378h+var_300]
0x180017abb  mov     [rsp+378h+var_188], rax
0x180017ac3  mov     [rsp+378h+var_180], 8
0x180017acf  lea     rax, [rsp+378h+var_2B0]
0x180017ad7  mov     [rsp+378h+var_178], rax
0x180017adf  mov     [rsp+378h+var_170], 8
0x180017aeb  lea     rax, [rsp+378h+var_2B8]
0x180017af3  mov     [rsp+378h+var_168], rax
0x180017afb  mov     [rsp+378h+var_160], 4
0x180017b07  lea     rax, [rsp+378h+var_2E8]
0x180017b0f  mov     [rsp+378h+var_158], rax
0x180017b17  mov     [rsp+378h+var_150], 8
0x180017b23  lea     rax, [rsp+378h+var_2A0]
0x180017b2b  mov     [rsp+378h+var_148], rax
0x180017b33  mov     [rsp+378h+var_140], 4
0x180017b3f  lea     rax, [rsp+378h+var_2F8]
0x180017b47  mov     [rsp+378h+var_138], rax
0x180017b4f  mov     [rsp+378h+var_130], 8
0x180017b5b  lea     rax, [rsp+378h+var_2A8]
0x180017b63  mov     [rsp+378h+var_128], rax
0x180017b6b  mov     [rsp+378h+var_120], 4
0x180017b77  lea     rax, [rsp+378h+var_198]
0x180017b7f  mov     [rsp+378h+var_358], rax
0x180017b84  mov     r9d, 8
0x180017b8a  lea     rdx, HttpSendHttpRequestEntityCompleteInline; "l"
0x180017b91  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x180017b98  call    McGenEventWrite_EventWriteTransfer
0x180017b9d  cmp     byte ptr [rsp+378h+var_248], r14b
0x180017ba5  jz      loc_1800180A8
0x180017bab  lea     rdx, [rsp+378h+ActivityId]; ActivityId
0x180017bb3  mov     ecx, 2; ControlCode
0x180017bb8  call    cs:__imp_EventActivityIdControl
0x180017bbf  nop     dword ptr [rax+rax+00h]
0x180017bc4  jmp     loc_1800180A8
0x180017bc9  mov     eax, edx
0x180017bcb  lea     rcx, [rax+rax*2]
0x180017bcf  mov     rax, [rsp+378h+var_2B0]
0x180017bd7  cmp     dword ptr [rax+rcx*8], 0
  ... truncated ...
```
