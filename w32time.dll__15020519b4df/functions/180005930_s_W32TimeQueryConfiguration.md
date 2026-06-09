# s_W32TimeQueryConfiguration

- ea: `0x180005930`
- end: `0x1800067a8`
- name: `s_W32TimeQueryConfiguration`
- size: `3704`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005480`

## callees

- `0x180005930`
- `0x180006930`
- `0x180018138`
- `0x18002a340`
- `0x18002aa10`
- `0x18003dd2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180005989`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180006228`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180005989`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180006228`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000641b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000645d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800065fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800066a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006701`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000671a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000674f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000676f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006788`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006797`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000641b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000645d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800065fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800066a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006701`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000671a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000674f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000676f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006788`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006797`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800059d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005ce0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005d8d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005ee4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000605f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000610a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800059d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005ce0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005d8d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005ee4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000605f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000610a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800062ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800062ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800059ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800059ba`
- `ntdll!RtlAcquireResourceExclusive` at `0x180005c9d`
- `ntdll!RtlAcquireResourceExclusive` at `0x180005ea7`
- `ntdll!RtlAcquireResourceExclusive` at `0x180005c9d`
- `ntdll!RtlAcquireResourceExclusive` at `0x180005ea7`
- `ntdll!RtlReleaseResource` at `0x180005d42`
- `ntdll!RtlReleaseResource` at `0x180005fed`
- `ntdll!RtlReleaseResource` at `0x18000655d`
- `ntdll!RtlReleaseResource` at `0x180005d42`
- `ntdll!RtlReleaseResource` at `0x180005fed`
- `ntdll!RtlReleaseResource` at `0x18000655d`
- `ntdll!RtlAcquireResourceShared` at `0x180006524`
- `ntdll!RtlAcquireResourceShared` at `0x180006524`

## string_xrefs

- `0x180006571`: `RPC Call - Query Configuration\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall s_W32TimeQueryConfiguration(__int64 a1, _QWORD *a2)
{
  unsigned int v2; // esi
  char v3; // bl
  HLOCAL v4; // rax
  void *v5; // r12
  unsigned __int16 *v6; // rbx
  __int64 v7; // rcx
  SIZE_T v8; // r15
  SIZE_T v9; // rdi
  const unsigned __int16 *v10; // r8
  int ProviderConfiguration; // edi
  SIZE_T v12; // rbx
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rcx
  unsigned __int16 *v15; // rdx
  unsigned __int64 v16; // rbx
  __int64 v17; // r13
  __int64 v18; // r8
  __int64 v19; // r9
  unsigned __int16 v20; // ax
  _WORD *v21; // r14
  __int64 v22; // rcx
  SIZE_T v23; // rbx
  _WORD *v24; // rcx
  unsigned __int64 v25; // rbx
  __int64 v26; // rdx
  _WORD *v27; // rax
  __int64 v28; // r9
  __int16 v29; // r8
  int v30; // ebx
  __int64 v31; // rax
  _WORD *v32; // rax
  __int16 *v33; // rcx
  __int64 v34; // rax
  int v35; // edx
  __int64 n; // rax
  int v37; // r14d
  int v38; // r15d
  unsigned __int64 v39; // rax
  SIZE_T v40; // rbx
  HLOCAL v41; // rax
  __int64 v42; // r13
  int v43; // ebx
  __int64 v44; // r14
  __int64 v46; // rax
  unsigned __int64 v47; // r15
  __int64 v48; // rdx
  __int16 v49; // r8
  unsigned int v50; // ebx
  __int64 v51; // r14
  __int64 i; // rdx
  __int64 v53; // rdx
  __int64 v54; // rdx
  void *v55; // rcx
  void *v56; // rcx
  void *v57; // rcx
  void *v58; // rcx
  __int64 v59; // [rsp+20h] [rbp-178h]
  int v60; // [rsp+28h] [rbp-170h]
  int v61; // [rsp+28h] [rbp-170h]
  int v62; // [rsp+38h] [rbp-160h]
  int v63; // [rsp+3Ch] [rbp-15Ch]
  unsigned __int16 *hMem; // [rsp+58h] [rbp-140h]
  __int16 *v65; // [rsp+60h] [rbp-138h]
  unsigned __int64 v66; // [rsp+70h] [rbp-128h] BYREF
  unsigned __int64 v67; // [rsp+78h] [rbp-120h] BYREF
  _WORD *v68; // [rsp+80h] [rbp-118h]
  __int64 m; // [rsp+88h] [rbp-110h]
  unsigned __int16 *v70; // [rsp+90h] [rbp-108h]
  unsigned __int16 *v71; // [rsp+98h] [rbp-100h]
  __int64 j; // [rsp+A0h] [rbp-F8h]
  _WORD *v73; // [rsp+A8h] [rbp-F0h]
  __int64 k; // [rsp+B0h] [rbp-E8h]
  _WORD *v75; // [rsp+B8h] [rbp-E0h]
  int v76; // [rsp+C0h] [rbp-D8h]
  int v77; // [rsp+C4h] [rbp-D4h]
  unsigned __int16 *v78; // [rsp+C8h] [rbp-D0h]
  unsigned __int64 v79; // [rsp+D0h] [rbp-C8h]
  __int64 v80; // [rsp+D8h] [rbp-C0h]
  _WORD *v81; // [rsp+E0h] [rbp-B8h]
  unsigned __int64 v82; // [rsp+E8h] [rbp-B0h]
  __int64 v83; // [rsp+F0h] [rbp-A8h]
  __int16 *v84; // [rsp+F8h] [rbp-A0h]
  unsigned __int64 v85; // [rsp+100h] [rbp-98h]
  __int64 v86; // [rsp+108h] [rbp-90h]
  __int64 v87; // [rsp+110h] [rbp-88h]
  __int64 v88; // [rsp+118h] [rbp-80h]
  __int64 v89; // [rsp+120h] [rbp-78h]
  int v92; // [rsp+1B0h] [rbp+18h]
  int v93; // [rsp+1B8h] [rbp+20h]

  v2 = 0;
  hMem = 0;
  v63 = 0;
  v65 = 0;
  if ( !a2 )
    return 2147942487LL;
  v93 = 0;
  v92 = 0;
  v87 = _set_se_translator(SeTransFunc);
  v3 = 0;
  HIBYTE(v59) = 0;
  if ( _InterlockedCompareExchange(&_lLoggingEnabled, 0, 0) )
  {
    if ( _pflstate
      && *((_BYTE *)_pflstate + 315)
      && RtlAcquireResourceShared((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
    {
      for ( i = *((_QWORD *)_pflstate + 3); i && *(_DWORD *)i <= 0x45u; i = *(_QWORD *)(i + 8) )
      {
        if ( (unsigned int)(*(_DWORD *)(i + 4) + *(_DWORD *)i) > 0x45 )
        {
          v3 = 1;
          HIBYTE(v59) = 1;
          break;
        }
      }
      RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
    }
    if ( v3 )
      FileLogAdd(L"RPC Call - Query Configuration\n");
  }
  EnterCriticalSection(&CriticalSection);
  BYTE6(v59) = 1;
  v4 = LocalAlloc(0x40u, 0xE0u);
  v5 = v4;
  if ( !v4 )
  {
    ProviderConfiguration = -2147024882;
    goto LABEL_88;
  }
  memset_0(v4, 0, 0xE0u);
  *(_DWORD *)v5 = 224;
  *((_DWORD *)v5 + 1) = 68;
  *((_DWORD *)v5 + 2) = *((_DWORD *)qword_1800A42F0 + 55);
  *((_DWORD *)v5 + 3) = *((_DWORD *)qword_1800A42F0 + 54);
  *((_DWORD *)v5 + 4) = *((_DWORD *)qword_1800A42F0 + 32);
  *((_DWORD *)v5 + 5) = *((_DWORD *)qword_1800A42F0 + 25);
  *((_DWORD *)v5 + 6) = *((_DWORD *)qword_1800A42F0 + 26);
  *((_DWORD *)v5 + 7) = *((_DWORD *)qword_1800A42F0 + 29);
  *((_DWORD *)v5 + 8) = *((_DWORD *)qword_1800A42F0 + 30);
  *((_DWORD *)v5 + 9) = *((_DWORD *)qword_1800A42F0 + 31);
  *((_DWORD *)v5 + 10) = *((_DWORD *)qword_1800A42F0 + 57);
  *((_DWORD *)v5 + 11) = *((_DWORD *)qword_1800A42F0 + 56);
  *((_DWORD *)v5 + 12) = *((_DWORD *)qword_1800A42F0 + 51);
  *((_DWORD *)v5 + 13) = *((_DWORD *)qword_1800A42F0 + 44);
  *((_DWORD *)v5 + 14) = *((_DWORD *)qword_1800A42F0 + 45);
  *((_DWORD *)v5 + 15) = *((_DWORD *)qword_1800A42F0 + 48);
  *((_DWORD *)v5 + 16) = *((_DWORD *)qword_1800A42F0 + 49);
  *((_DWORD *)v5 + 17) = *((_DWORD *)qword_1800A42F0 + 50);
  *((_DWORD *)v5 + 18) = 68;
  *((_DWORD *)v5 + 19) = *((_DWORD *)qword_1800A42F0 + 20);
  *((_DWORD *)v5 + 20) = *((_DWORD *)qword_1800A42F0 + 21);
  *((_DWORD *)v5 + 21) = *((_DWORD *)qword_1800A42F0 + 22);
  *((_DWORD *)v5 + 22) = *((_DWORD *)qword_1800A42F0 + 23);
  *((_DWORD *)v5 + 23) = *((_DWORD *)qword_1800A42F0 + 28);
  *((_DWORD *)v5 + 24) = *((_DWORD *)qword_1800A42F0 + 24);
  *((_DWORD *)v5 + 25) = *((_DWORD *)qword_1800A42F0 + 18);
  *((_DWORD *)v5 + 26) = *((_DWORD *)qword_1800A42F0 + 19);
  *((_DWORD *)v5 + 27) = *((_DWORD *)qword_1800A42F0 + 39);
  *((_DWORD *)v5 + 28) = *((_DWORD *)qword_1800A42F0 + 40);
  *((_DWORD *)v5 + 29) = *((_DWORD *)qword_1800A42F0 + 41);
  *((_DWORD *)v5 + 30) = *((_DWORD *)qword_1800A42F0 + 42);
  *((_DWORD *)v5 + 31) = *((_DWORD *)qword_1800A42F0 + 47);
  *((_DWORD *)v5 + 32) = *((_DWORD *)qword_1800A42F0 + 43);
  *((_DWORD *)v5 + 33) = *((_DWORD *)qword_1800A42F0 + 37);
  *((_DWORD *)v5 + 34) = *((_DWORD *)qword_1800A42F0 + 38);
  *((_DWORD *)v5 + 36) = 48;
  v62 = *((_DWORD *)_pflstate + 15);
  *((_DWORD *)v5 + 42) = *((_DWORD *)_pflstate + 2);
  *((_DWORD *)v5 + 46) = v62;
  BYTE4(v59) = 0;
  v66 = 0;
  v6 = 0;
  v70 = 0;
  if ( !RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
  {
    ProviderConfiguration = -2147023537;
    v8 = 2;
    goto LABEL_13;
  }
  v7 = *((_QWORD *)_pflstate + 2);
  if ( v7 )
  {
    v53 = -1;
    do
      ++v53;
    while ( *(_WORD *)(v7 + 2 * v53) );
    v8 = 2;
    ProviderConfiguration = ULongLongMult(2u, v53 + 1, &v66);
    if ( ProviderConfiguration < 0 )
      goto LABEL_11;
    v9 = v66;
  }
  else
  {
    v8 = 2;
    v9 = 2;
    v66 = 2;
  }
  v6 = (unsigned __int16 *)LocalAlloc(0x40u, v9);
  v70 = v6;
  if ( v6 )
  {
    v10 = (const unsigned __int16 *)*((_QWORD *)_pflstate + 2);
    if ( !v10 )
    {
      *v6 = 0;
LABEL_10:
      hMem = v6;
      v6 = 0;
      v70 = 0;
      v63 = *((_DWORD *)_pflstate + 16);
      ProviderConfiguration = 0;
      goto LABEL_11;
    }
    ProviderConfiguration = StringCbCopyW(v6, v9, v10);
    if ( ProviderConfiguration >= 0 )
      goto LABEL_10;
  }
  else
  {
    ProviderConfiguration = -2147024882;
  }
LABEL_11:
  RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
  BYTE4(v59) = 0;
  if ( v6 )
    LocalFree(v6);
LABEL_13:
  if ( ProviderConfiguration < 0 )
  {
LABEL_88:
    LeaveCriticalSection(&CriticalSection);
    goto LABEL_81;
  }
  *((_DWORD *)v5 + 45) = v63;
  if ( hMem )
  {
    v46 = -1;
    do
      ++v46;
    while ( hMem[v46] );
    v88 = 0;
    v12 = 2 * (v46 + 1);
    if ( !is_mul_ok(2u, v46 + 1) )
    {
      ProviderConfiguration = -2147024362;
      goto LABEL_88;
    }
  }
  else
  {
    v12 = 2;
  }
  v13 = (unsigned __int16 *)LocalAlloc(0x40u, v12);
  v14 = v13;
  *((_QWORD *)v5 + 20) = v13;
  if ( !v13 )
  {
    ProviderConfiguration = -2147024882;
    goto LABEL_88;
  }
  v15 = hMem;
  if ( hMem )
  {
    v16 = v12 >> 1;
    if ( !v16 || (ProviderConfiguration = 0, v16 > 0x7FFFFFFF) )
      ProviderConfiguration = -2147024809;
    v17 = 2147483646;
    if ( ProviderConfiguration < 0 )
    {
      if ( v16 )
        *v13 = 0;
    }
    else
    {
      v18 = 2147483646;
      v80 = 2147483646;
      v78 = hMem;
      v79 = v16;
      v71 = v13;
      v19 = 0;
      for ( j = 0; v16; j = v19 )
      {
        if ( !v18 )
          break;
        v20 = *v15;
        if ( !*v15 )
          break;
        v78 = ++v15;
        *v14++ = v20;
        v71 = v14;
        v79 = --v16;
        v80 = --v18;
        ++v19;
      }
      ProviderConfiguration = 0;
      if ( !v16 )
      {
        v71 = --v14;
        j = v19 - 1;
        ProviderConfiguration = -2147024774;
      }
      *v14 = 0;
    }
    if ( ProviderConfiguration < 0 )
      goto LABEL_80;
  }
  else
  {
    *v13 = 0;
    v17 = 2147483646;
  }
  BYTE5(v59) = 0;
  v67 = 0;
  v21 = 0;
  v75 = 0;
  if ( RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
  {
    v22 = *((_QWORD *)_pflstate + 4);
    if ( v22 )
    {
      v54 = -1;
      do
        ++v54;
      while ( *(_WORD *)(v22 + 2 * v54) );
      ProviderConfiguration = ULongLongMult(2u, v54 + 1, &v67);
      if ( ProviderConfiguration < 0 )
        goto LABEL_149;
      v23 = v67;
    }
    else
    {
      v23 = 2;
      v67 = 2;
    }
    v21 = LocalAlloc(0x40u, v23);
    v75 = v21;
    if ( v21 )
    {
      v24 = (_WORD *)*((_QWORD *)_pflstate + 4);
      if ( v24 )
      {
        v25 = v23 >> 1;
        if ( !v25 || (ProviderConfiguration = 0, v25 > 0x7FFFFFFF) )
          ProviderConfiguration = -2147024809;
        if ( ProviderConfiguration < 0 )
        {
          if ( v25 )
            *v21 = 0;
        }
        else
        {
          v26 = 2147483646;
          v83 = 2147483646;
          v81 = v24;
          v82 = v25;
          v27 = v21;
          v73 = v21;
          v28 = 0;
          for ( k = 0; v25; k = v28 )
          {
            if ( !v26 )
              break;
            v29 = *v24;
            if ( !*v24 )
              break;
            v81 = ++v24;
            *v27++ = v29;
            v73 = v27;
            v82 = --v25;
            v83 = --v26;
            ++v28;
          }
          ProviderConfiguration = 0;
          if ( !v25 )
          {
            v73 = --v27;
            k = v28 - 1;
            ProviderConfiguration = -2147024774;
          }
          *v27 = 0;
        }
        if ( ProviderConfiguration < 0 )
        {
          v30 = 0;
          goto LABEL_48;
        }
      }
      else
      {
        *v21 = 0;
      }
      v65 = v21;
      v21 = 0;
      v75 = 0;
      v30 = *((_DWORD *)_pflstate + 17);
      ProviderConfiguration = 0;
LABEL_48:
      RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
      BYTE5(v59) = 0;
      if ( v21 )
        LocalFree(v21);
      goto LABEL_50;
    }
    ProviderConfiguration = -2147024882;
LABEL_149:
    v30 = 0;
    goto LABEL_48;
  }
  ProviderConfiguration = -2147023537;
  v30 = 0;
LABEL_50:
  if ( ProviderConfiguration < 0 )
    goto LABEL_80;
  *((_DWORD *)v5 + 44) = v30;
  if ( v65 )
  {
    v31 = -1;
    do
      ++v31;
    while ( v65[v31] );
    v8 = 2 * (v31 + 1);
    if ( !is_mul_ok(2u, v31 + 1) )
    {
      ProviderConfiguration = -2147024362;
      goto LABEL_80;
    }
  }
  v32 = LocalAlloc(0x40u, v8);
  *((_QWORD *)v5 + 19) = v32;
  if ( !v32 )
  {
    ProviderConfiguration = -2147024882;
    goto LABEL_80;
  }
  v33 = v65;
  if ( v65 )
  {
    v47 = v8 >> 1;
    if ( !v47 || (ProviderConfiguration = 0, v47 > 0x7FFFFFFF) )
      ProviderConfiguration = -2147024809;
    if ( ProviderConfiguration < 0 )
    {
      if ( v47 )
        *v32 = 0;
    }
    else
    {
      v86 = 2147483646;
      v84 = v65;
      v85 = v47;
      v68 = v32;
      v48 = 0;
      for ( m = 0; v47; m = v48 )
      {
        if ( !v17 )
          break;
        v49 = *v33;
        if ( !*v33 )
          break;
        v84 = ++v33;
        *v32++ = v49;
        v68 = v32;
        v85 = --v47;
        v86 = --v17;
        ++v48;
      }
      ProviderConfiguration = 0;
      if ( !v47 )
      {
        v68 = --v32;
        m = v48 - 1;
        ProviderConfiguration = -2147024774;
      }
      *v32 = 0;
    }
    if ( ProviderConfiguration < 0 )
      goto LABEL_80;
  }
  else
  {
    *v32 = 0;
  }
  v34 = *(_QWORD *)qword_1800A42F0;
  v35 = 0;
  while ( v34 )
  {
    v93 = ++v35;
    v76 = v35;
    v34 = *(_QWORD *)(v34 + 24);
  }
  for ( n = *((_QWORD *)qword_1800A42F0 + 1); n; n = *(_QWORD *)(n + 24) )
    v77 = ++v92;
  v37 = v92;
  v38 = v93;
  v39 = (unsigned int)(v92 + v93);
  *((_DWORD *)v5 + 48) = v39;
  if ( !(_DWORD)v39 )
  {
    *((_QWORD *)v5 + 25) = 0;
LABEL_79:
    *((_DWORD *)v5 + 52) = 0;
    *((_QWORD *)v5 + 27) = 0;
    *a2 = v5;
    v5 = 0;
    _set_se_translator(v87);
    ProviderConfiguration = 0;
    goto LABEL_80;
  }
  v89 = 0;
  v40 = 8 * v39;
  if ( is_mul_ok(8u, v39) )
  {
    ProviderConfiguration = 0;
  }
  else
  {
    v40 = -1;
    ProviderConfiguration = -2147024362;
  }
  LODWORD(v59) = ProviderConfiguration;
  if ( ProviderConfiguration >= 0 )
  {
    v41 = LocalAlloc(0x40u, v40);
    *((_QWORD *)v5 + 25) = v41;
    if ( v41 )
    {
      memset_0(v41, 0, v40);
      if ( v93 )
      {
        v50 = 0;
        v61 = 0;
        v51 = *(_QWORD *)qword_1800A42F0;
        v42 = a1;
        while ( v51 && v50 < *((_DWORD *)v5 + 48) )
        {
          ProviderConfiguration = s_W32TimeQueryProviderConfiguration(
                                    a1,
                                    0,
                                    *(_QWORD *)(v51 + 8),
                                    *((_QWORD *)v5 + 25) + 8LL * v50,
                                    v59,
                                    v61);
          LODWORD(v59) = ProviderConfiguration;
          if ( ProviderConfiguration < 0 )
            goto LABEL_80;
          v51 = *(_QWORD *)(v51 + 24);
          v61 = ++v50;
        }
        v37 = v92;
        v38 = v93;
      }
      else
      {
        v42 = a1;
      }
      if ( v37 )
      {
        v43 = 0;
        v60 = 0;
        v44 = *((_QWORD *)qword_1800A42F0 + 1);
        while ( v44 && (unsigned int)(v38 + v43) < *((_DWORD *)v5 + 48) )
        {
          ProviderConfiguration = s_W32TimeQueryProviderConfiguration(
                                    v42,
                                    0,
                                    *(_QWORD *)(v44 + 8),
                                    *((_QWORD *)v5 + 25) + 8LL * (unsigned int)(v38 + v43),
                                    v59,
                                    v60);
          LODWORD(v59) = ProviderConfiguration;
          if ( ProviderConfiguration < 0 )
            goto LABEL_80;
          v44 = *(_QWORD *)(v44 + 24);
          v60 = ++v43;
        }
      }
      goto LABEL_79;
    }
    ProviderConfiguration = -2147024882;
  }
LABEL_80:
  if ( BYTE6(v59) )
    goto LABEL_88;
LABEL_81:
  if ( v5 )
  {
    v55 = (void *)*((_QWORD *)v5 + 20);
    if ( v55 )
      LocalFree(v55);
    v56 = (void *)*((_QWORD *)v5 + 19);
    if ( v56 )
      LocalFree(v56);
    if ( *((_QWORD *)v5 + 25) )
    {
      if ( *((_DWORD *)v5 + 48) )
      {
        do
        {
          v57 = *(void **)(*((_QWORD *)v5 + 25) + 8LL * v2);
          if ( v57 )
            LocalFree(v57);
          ++v2;
        }
        while ( v2 < *((_DWORD *)v5 + 48) );
      }
      LocalFree(*((HLOCAL *)v5 + 25));
    }
    v58 = (void *)*((_QWORD *)v5 + 27);
    if ( v58 )
      LocalFree(v58);
    LocalFree(v5);
  }
  if ( hMem )
    LocalFree(hMem);
  if ( v65 )
    LocalFree(v65);
  return (unsigned int)ProviderConfiguration;
}

```

## disassembly

```asm
0x180005930  mov     rax, rsp
0x180005933  mov     [rax+10h], rdx
0x180005937  mov     [rax+8], rcx
0x18000593b  push    rbx
0x18000593c  push    rsi
0x18000593d  push    rdi
0x18000593e  push    r12
0x180005940  push    r13
0x180005942  push    r14
0x180005944  push    r15
0x180005946  sub     rsp, 160h
0x18000594d  xor     esi, esi
0x18000594f  mov     [rsp+198h+hMem], rsi
0x180005954  mov     [rsp+198h+var_15C], esi
0x180005958  mov     [rsp+198h+var_138], rsi
0x18000595d  mov     [rsp+198h+var_130], esi
0x180005961  mov     [rsp+198h+var_160], esi
0x180005965  test    rdx, rdx
0x180005968  jz      loc_180006500
0x18000596e  mov     [rsp+198h+var_172], sil
0x180005973  mov     [rsp+198h+var_148], rsi
0x180005978  mov     dword ptr [rsp+198h+var_168], esi
0x18000597c  mov     [rax+20h], esi
0x18000597f  mov     [rax+18h], esi
0x180005982  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x180005989  call    cs:__imp__set_se_translator
0x180005990  nop     dword ptr [rax+rax+00h]
0x180005995  mov     [rsp+198h+var_88], rax
0x18000599d  xor     bl, bl
0x18000599f  mov     [rsp+198h+var_171], bl
0x1800059a3  xor     eax, eax
0x1800059a5  lock cmpxchg cs:?_lLoggingEnabled@@3JC, esi; long volatile _lLoggingEnabled
0x1800059ad  jnz     loc_18000650A
0x1800059b3  lea     rcx, CriticalSection; lpCriticalSection
0x1800059ba  call    cs:__imp_EnterCriticalSection
0x1800059c1  nop     dword ptr [rax+rax+00h]
0x1800059c6  mov     [rsp+198h+var_178], esi
0x1800059ca  mov     [rsp+198h+var_172], 1
0x1800059cf  mov     edx, 0E0h; uBytes
0x1800059d4  mov     ecx, 40h ; '@'; uFlags
0x1800059d9  call    cs:__imp_LocalAlloc
0x1800059e0  nop     dword ptr [rax+rax+00h]
0x1800059e5  mov     r12, rax
0x1800059e8  mov     [rsp+198h+var_148], rax
0x1800059ed  test    rax, rax
0x1800059f0  jz      loc_180006588
0x1800059f6  xor     edx, edx; Val
0x1800059f8  mov     r8d, 0E0h; Size
0x1800059fe  mov     rcx, rax; void *
0x180005a01  call    memset_0
0x180005a06  mov     dword ptr [r12], 0E0h
0x180005a0e  mov     dword ptr [r12+4], 44h ; 'D'
0x180005a17  mov     rax, cs:qword_1800A42F0
0x180005a1e  mov     ecx, [rax+0DCh]
0x180005a24  mov     [r12+8], ecx
0x180005a29  mov     rax, cs:qword_1800A42F0
0x180005a30  mov     ecx, [rax+0D8h]
0x180005a36  mov     [r12+0Ch], ecx
0x180005a3b  mov     rax, cs:qword_1800A42F0
0x180005a42  mov     ecx, [rax+80h]
0x180005a48  mov     [r12+10h], ecx
0x180005a4d  mov     rax, cs:qword_1800A42F0
0x180005a54  mov     ecx, [rax+64h]
0x180005a57  mov     [r12+14h], ecx
0x180005a5c  mov     rax, cs:qword_1800A42F0
0x180005a63  mov     ecx, [rax+68h]
0x180005a66  mov     [r12+18h], ecx
0x180005a6b  mov     rax, cs:qword_1800A42F0
0x180005a72  mov     ecx, [rax+74h]
0x180005a75  mov     [r12+1Ch], ecx
0x180005a7a  mov     rax, cs:qword_1800A42F0
0x180005a81  mov     ecx, [rax+78h]
0x180005a84  mov     [r12+20h], ecx
0x180005a89  mov     rax, cs:qword_1800A42F0
0x180005a90  mov     ecx, [rax+7Ch]
0x180005a93  mov     [r12+24h], ecx
0x180005a98  mov     rax, cs:qword_1800A42F0
0x180005a9f  mov     ecx, [rax+0E4h]
0x180005aa5  mov     [r12+28h], ecx
0x180005aaa  mov     rax, cs:qword_1800A42F0
0x180005ab1  mov     ecx, [rax+0E0h]
0x180005ab7  mov     [r12+2Ch], ecx
0x180005abc  mov     rax, cs:qword_1800A42F0
0x180005ac3  mov     ecx, [rax+0CCh]
0x180005ac9  mov     [r12+30h], ecx
0x180005ace  mov     rax, cs:qword_1800A42F0
0x180005ad5  mov     ecx, [rax+0B0h]
0x180005adb  mov     [r12+34h], ecx
0x180005ae0  mov     rax, cs:qword_1800A42F0
0x180005ae7  mov     ecx, [rax+0B4h]
0x180005aed  mov     [r12+38h], ecx
0x180005af2  mov     rax, cs:qword_1800A42F0
0x180005af9  mov     ecx, [rax+0C0h]
0x180005aff  mov     [r12+3Ch], ecx
0x180005b04  mov     rax, cs:qword_1800A42F0
0x180005b0b  mov     ecx, [rax+0C4h]
0x180005b11  mov     [r12+40h], ecx
0x180005b16  mov     rax, cs:qword_1800A42F0
0x180005b1d  mov     ecx, [rax+0C8h]
0x180005b23  mov     [r12+44h], ecx
0x180005b28  mov     dword ptr [r12+48h], 44h ; 'D'
0x180005b31  mov     rax, cs:qword_1800A42F0
0x180005b38  mov     ecx, [rax+50h]
0x180005b3b  mov     [r12+4Ch], ecx
0x180005b40  mov     rax, cs:qword_1800A42F0
0x180005b47  mov     ecx, [rax+54h]
0x180005b4a  mov     [r12+50h], ecx
0x180005b4f  mov     rax, cs:qword_1800A42F0
0x180005b56  mov     ecx, [rax+58h]
0x180005b59  mov     [r12+54h], ecx
0x180005b5e  mov     rax, cs:qword_1800A42F0
0x180005b65  mov     ecx, [rax+5Ch]
0x180005b68  mov     [r12+58h], ecx
0x180005b6d  mov     rax, cs:qword_1800A42F0
0x180005b74  mov     ecx, [rax+70h]
0x180005b77  mov     [r12+5Ch], ecx
0x180005b7c  mov     rax, cs:qword_1800A42F0
0x180005b83  mov     ecx, [rax+60h]
0x180005b86  mov     [r12+60h], ecx
0x180005b8b  mov     rax, cs:qword_1800A42F0
0x180005b92  mov     ecx, [rax+48h]
0x180005b95  mov     [r12+64h], ecx
0x180005b9a  mov     rax, cs:qword_1800A42F0
0x180005ba1  mov     ecx, [rax+4Ch]
0x180005ba4  mov     [r12+68h], ecx
0x180005ba9  mov     rax, cs:qword_1800A42F0
0x180005bb0  mov     ecx, [rax+9Ch]
0x180005bb6  mov     [r12+6Ch], ecx
0x180005bbb  mov     rax, cs:qword_1800A42F0
0x180005bc2  mov     ecx, [rax+0A0h]
0x180005bc8  mov     [r12+70h], ecx
0x180005bcd  mov     rax, cs:qword_1800A42F0
0x180005bd4  mov     ecx, [rax+0A4h]
0x180005bda  mov     [r12+74h], ecx
0x180005bdf  mov     rax, cs:qword_1800A42F0
0x180005be6  mov     ecx, [rax+0A8h]
0x180005bec  mov     [r12+78h], ecx
0x180005bf1  mov     rax, cs:qword_1800A42F0
0x180005bf8  mov     ecx, [rax+0BCh]
0x180005bfe  mov     [r12+7Ch], ecx
0x180005c03  mov     rax, cs:qword_1800A42F0
0x180005c0a  mov     ecx, [rax+0ACh]
0x180005c10  mov     [r12+80h], ecx
0x180005c18  mov     rax, cs:qword_1800A42F0
0x180005c1f  mov     ecx, [rax+94h]
0x180005c25  mov     [r12+84h], ecx
0x180005c2d  mov     rax, cs:qword_1800A42F0
0x180005c34  mov     ecx, [rax+98h]
0x180005c3a  mov     [r12+88h], ecx
0x180005c42  mov     dword ptr [r12+90h], 30h ; '0'
0x180005c4e  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180005c55  mov     eax, [rcx+3Ch]
0x180005c58  mov     [rsp+198h+var_160], eax
0x180005c5c  mov     eax, [rcx+8]
0x180005c5f  mov     [rsp+198h+var_130], eax
0x180005c63  mov     [rsp+198h+var_178], esi
0x180005c67  mov     [r12+0A8h], eax
0x180005c6f  mov     eax, [rsp+198h+var_160]
0x180005c73  mov     [r12+0B8h], eax
0x180005c7b  mov     [rsp+198h+var_174], 0
0x180005c80  mov     [rsp+198h+var_128], rsi
0x180005c85  mov     rbx, rsi
0x180005c88  mov     [rsp+198h+var_108], rbx
0x180005c90  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180005c97  add     rcx, 50h ; 'P'; Resource
0x180005c9b  mov     dl, 1; Wait
0x180005c9d  call    cs:__imp_RtlAcquireResourceExclusive
0x180005ca4  nop     dword ptr [rax+rax+00h]
0x180005ca9  test    al, al
0x180005cab  jz      loc_180006596
0x180005cb1  mov     [rsp+198h+var_174], 1
0x180005cb6  mov     rax, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180005cbd  mov     rcx, [rax+10h]
0x180005cc1  test    rcx, rcx
0x180005cc4  jnz     loc_1800065A6
0x180005cca  mov     r15d, 2
0x180005cd0  mov     edi, r15d
0x180005cd3  mov     [rsp+198h+var_128], r15
0x180005cd8  mov     rdx, rdi; uBytes
0x180005cdb  mov     ecx, 40h ; '@'; uFlags
0x180005ce0  call    cs:__imp_LocalAlloc
0x180005ce7  nop     dword ptr [rax+rax+00h]
0x180005cec  mov     rbx, rax
0x180005cef  mov     [rsp+198h+var_108], rax
0x180005cf7  test    rax, rax
0x180005cfa  jz      loc_180006411
0x180005d00  mov     rax, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180005d07  mov     r8, [rax+10h]; unsigned __int16 *
0x180005d0b  test    r8, r8
0x180005d0e  jnz     loc_1800065E0
0x180005d14  mov     [rbx], si
0x180005d17  mov     [rsp+198h+hMem], rbx
0x180005d1c  mov     rbx, rsi
0x180005d1f  mov     [rsp+198h+var_108], rbx
0x180005d27  mov     rax, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180005d2e  mov     ecx, [rax+40h]
0x180005d31  mov     [rsp+198h+var_15C], ecx
0x180005d35  mov     edi, esi
0x180005d37  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180005d3e  add     rcx, 50h ; 'P'; Resource
0x180005d42  call    cs:__imp_RtlReleaseResource
0x180005d49  nop     dword ptr [rax+rax+00h]
0x180005d4e  mov     [rsp+198h+var_174], 0
0x180005d53  test    rbx, rbx
0x180005d56  jnz     loc_1800065FA
0x180005d5c  mov     [rsp+198h+var_178], edi
0x180005d60  test    edi, edi
0x180005d62  js      loc_18000660E
0x180005d68  mov     eax, [rsp+198h+var_15C]
0x180005d6c  mov     [r12+0B4h], eax
0x180005d74  mov     rcx, [rsp+198h+hMem]
0x180005d79  test    rcx, rcx
0x180005d7c  jnz     loc_180006308
0x180005d82  mov     rbx, r15
0x180005d85  mov     rdx, rbx; uBytes
0x180005d88  mov     ecx, 40h ; '@'; uFlags
0x180005d8d  call    cs:__imp_LocalAlloc
0x180005d94  nop     dword ptr [rax+rax+00h]
0x180005d99  mov     rcx, rax
0x180005d9c  mov     [r12+0A0h], rax
0x180005da4  test    rax, rax
0x180005da7  jz      loc_180006613
0x180005dad  mov     rdx, [rsp+198h+hMem]
0x180005db2  test    rdx, rdx
0x180005db5  jz      loc_1800062BB
0x180005dbb  mov     [rsp+198h+var_158], esi
0x180005dbf  shr     rbx, 1
0x180005dc2  jz      loc_180006621
0x180005dc8  mov     edi, esi
0x180005dca  cmp     rbx, 7FFFFFFFh
0x180005dd1  ja      loc_180006621
0x180005dd7  mov     [rsp+198h+var_158], edi
0x180005ddb  mov     r13d, 7FFFFFFEh
0x180005de1  test    edi, edi
0x180005de3  js      loc_18000662B
0x180005de9  mov     r8d, r13d
0x180005dec  mov     [rsp+198h+var_C0], r13
0x180005df4  mov     [rsp+198h+var_D0], rdx
0x180005dfc  mov     [rsp+198h+var_C8], rbx
0x180005e04  mov     [rsp+198h+var_100], rax
0x180005e0c  mov     r9, rsi
0x180005e0f  mov     [rsp+198h+var_F8], rsi
0x180005e17  test    rbx, rbx
0x180005e1a  jz      short loc_180005E67
0x180005e1c  test    r8, r8
0x180005e1f  jz      short loc_180005E67
0x180005e21  movzx   eax, word ptr [rdx]
0x180005e24  test    ax, ax
0x180005e27  jz      short loc_180005E67
0x180005e29  add     rdx, 2
0x180005e2d  mov     [rsp+198h+var_D0], rdx
0x180005e35  mov     [rcx], ax
0x180005e38  add     rcx, 2
0x180005e3c  mov     [rsp+198h+var_100], rcx
0x180005e44  dec     rbx
0x180005e47  mov     [rsp+198h+var_C8], rbx
0x180005e4f  dec     r8
0x180005e52  mov     [rsp+198h+var_C0], r8
0x180005e5a  inc     r9
0x180005e5d  mov     [rsp+198h+var_F8], r9
0x180005e65  jmp     short loc_180005E17
0x180005e67  mov     edi, esi
0x180005e69  test    rbx, rbx
0x180005e6c  jz      loc_18000627C
0x180005e72  mov     [rcx], si
0x180005e75  mov     [rsp+198h+var_158], edi
0x180005e79  mov     [rsp+198h+var_178], edi
0x180005e7d  test    edi, edi
0x180005e7f  js      loc_18000640C
0x180005e85  mov     [rsp+198h+var_173], 0
0x180005e8a  mov     [rsp+198h+var_120], rsi
0x180005e8f  mov     r14, rsi
0x180005e92  mov     [rsp+198h+var_E0], rsi
0x180005e9a  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180005ea1  add     rcx, 50h ; 'P'; Resource
0x180005ea5  mov     dl, 1; Wait
0x180005ea7  call    cs:__imp_RtlAcquireResourceExclusive
0x180005eae  nop     dword ptr [rax+rax+00h]
0x180005eb3  test    al, al
0x180005eb5  jz      loc_18000663C
0x180005ebb  mov     [rsp+198h+var_173], 1
0x180005ec0  mov     rax, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180005ec7  mov     rcx, [rax+20h]
0x180005ecb  test    rcx, rcx
0x180005ece  jnz     loc_18000664A
0x180005ed4  mov     rbx, r15
0x180005ed7  mov     [rsp+198h+var_120], rbx
0x180005edc  mov     rdx, rbx; uBytes
0x180005edf  mov     ecx, 40h ; '@'; uFlags
0x180005ee4  call    cs:__imp_LocalAlloc
0x180005eeb  nop     dword ptr [rax+rax+00h]
0x180005ef0  mov     r14, rax
0x180005ef3  mov     [rsp+198h+var_E0], rax
0x180005efb  test    rax, rax
0x180005efe  jz      loc_18000667B
0x180005f04  mov     rax, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180005f0b  mov     rcx, [rax+20h]
0x180005f0f  test    rcx, rcx
0x180005f12  jz      loc_1800061D0
0x180005f18  mov     [rsp+198h+var_154], esi
  ... truncated ...
```
