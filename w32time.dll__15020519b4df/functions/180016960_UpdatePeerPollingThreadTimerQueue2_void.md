# UpdatePeerPollingThreadTimerQueue2(void)

- ea: `0x180016960`
- end: `0x18001722c`
- name: `?UpdatePeerPollingThreadTimerQueue2@@YAJXZ`
- size: `2252`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, installer_update`

## callers

- `0x180014f30`
- `0x1800164f0`

## callees

- `0x180003ac0`
- `0x1800144f0`
- `0x180014774`
- `0x180016454`
- `0x180016960`
- `0x180017240`
- `0x1800173bc`
- `0x180017e88`
- `0x180018138`
- `0x18001d9a0`
- `0x18002dbc4`
- `0x18003163c`
- `0x18003a900`
- `0x18003d270`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800169b4`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180016ada`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180016b1b`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180016b86`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180016cb7`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180016cfe`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800169b4`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180016ada`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180016b1b`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180016b86`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180016cb7`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180016cfe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016c09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016c6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016c09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016c6e`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x180016d42`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x180016d8f`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x180016d42`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x180016d8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016a4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016bbd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016eaa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016f11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001701b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800170b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017148`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800171c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016a4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016bbd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016eaa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016f11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001701b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800170b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017148`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800171c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800169da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016aa2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016e41`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001711a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800169da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016aa2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016e41`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001711a`

## string_xrefs

- `0x180017005`: `Logging error: NtpClient has been configured to acquire time from one or more time sources, however none of the sources are currently accessible and no attempt to contact a source will be made for %s minutes. NTPCLIENT HAS NO SOURCE OF ACCURATE TIME.\n`
- `0x180017186`: `Logging error: NtpClient has been configured to acquire time from one or more time sources, however none of the sources are accessible. NTPCLIENT HAS NO SOURCE OF ACCURATE TIME.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=23 #try_helpers=1
__int64 UpdatePeerPollingThreadTimerQueue2(void)
{
  _NtpProvState *v0; // rdx
  volatile signed __int32 *v1; // rbx
  int v2; // esi
  int v3; // r14d
  unsigned int v4; // edx
  volatile signed __int32 *i; // rbx
  volatile signed __int32 ***v6; // rbx
  volatile signed __int32 **j; // rbx
  volatile signed __int32 ***v8; // rsi
  volatile signed __int32 *v9; // rax
  int v10; // r14d
  volatile signed __int32 **v11; // rbx
  volatile signed __int32 **v12; // rbx
  volatile signed __int32 **v13; // rsi
  volatile signed __int32 **v14; // rbx
  volatile signed __int32 **v15; // rsi
  volatile signed __int32 *v17; // rax
  char **v18; // rdx
  volatile signed __int32 **v19; // r8
  volatile signed __int32 **v20; // r9
  volatile signed __int32 **v21; // r11
  volatile signed __int32 **v22; // r10
  struct _RTL_CRITICAL_SECTION *v23; // rcx
  volatile signed __int32 *v24; // rax
  volatile signed __int32 **k; // rax
  unsigned __int64 v26; // rdx
  __int64 v27; // rdx
  volatile signed __int32 *v28; // rax
  volatile signed __int32 **v29; // rax
  unsigned int v30; // eax
  unsigned int v31; // eax
  char v32; // [rsp+20h] [rbp-298h]
  int v33; // [rsp+24h] [rbp-294h]
  signed __int32 v34; // [rsp+28h] [rbp-290h] BYREF
  BOOL v35; // [rsp+2Ch] [rbp-28Ch]
  volatile signed __int32 **v36; // [rsp+30h] [rbp-288h]
  unsigned __int64 v37; // [rsp+38h] [rbp-280h]
  volatile signed __int32 ***v38; // [rsp+40h] [rbp-278h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp-270h]
  volatile signed __int32 ***v40; // [rsp+50h] [rbp-268h]
  volatile signed __int32 **v41; // [rsp+58h] [rbp-260h]
  volatile signed __int32 *v42; // [rsp+60h] [rbp-258h]
  volatile signed __int32 *v43; // [rsp+68h] [rbp-250h] BYREF
  HLOCAL hMem[2]; // [rsp+70h] [rbp-248h] BYREF
  HLOCAL v45; // [rsp+80h] [rbp-238h]
  HLOCAL v46[2]; // [rsp+88h] [rbp-230h] BYREF
  HLOCAL v47; // [rsp+98h] [rbp-220h]
  int v48; // [rsp+A0h] [rbp-218h]
  volatile signed __int32 **v49; // [rsp+A8h] [rbp-210h]
  volatile signed __int32 **v50; // [rsp+B0h] [rbp-208h]
  volatile signed __int32 ***v51; // [rsp+B8h] [rbp-200h]
  volatile signed __int32 *v52[2]; // [rsp+C0h] [rbp-1F8h] BYREF
  __int64 v53; // [rsp+D0h] [rbp-1E8h]
  volatile signed __int32 **v54; // [rsp+D8h] [rbp-1E0h]
  volatile signed __int32 **v55; // [rsp+E0h] [rbp-1D8h]
  volatile signed __int32 **v56; // [rsp+E8h] [rbp-1D0h]
  volatile signed __int32 **v57; // [rsp+F0h] [rbp-1C8h]
  volatile signed __int32 **v58; // [rsp+F8h] [rbp-1C0h]
  volatile signed __int32 **v59; // [rsp+100h] [rbp-1B8h]
  _BYTE v60[24]; // [rsp+108h] [rbp-1B0h] BYREF
  int v61; // [rsp+120h] [rbp-198h]
  _BYTE v62[24]; // [rsp+128h] [rbp-190h] BYREF
  int v63; // [rsp+140h] [rbp-178h]
  _BYTE v64[24]; // [rsp+168h] [rbp-150h] BYREF
  _BYTE v65[48]; // [rsp+180h] [rbp-138h] BYREF
  unsigned __int16 v66[104]; // [rsp+1B0h] [rbp-108h] BYREF

  v35 = 0;
  v37 = 0;
  lpCriticalSection = 0;
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v46);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(hMem);
  v53 = _set_se_translator(SeTransFunc);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
  v32 = 1;
  v0 = g_pnpstate;
  v49 = (volatile signed __int32 **)((char *)g_pnpstate + 408);
  v40 = (volatile signed __int32 ***)((char *)g_pnpstate + 408);
  v38 = (volatile signed __int32 ***)((char *)g_pnpstate + 432);
  v1 = (volatile signed __int32 *)*((_QWORD *)g_pnpstate + 51);
  v42 = v1;
  while ( 1 )
  {
    v51 = v40 + 1;
    v43 = (volatile signed __int32 *)v40[1];
    if ( v1 == v43 )
      break;
    v43 = (volatile signed __int32 *)_set_se_translator(SeTransFunc);
    v33 = 0;
    try
    {
      if ( v46[1] == v47 )
      {
        std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::_Emplace_reallocate<AutoPtr<NtpPeer> const &>(
          v46,
          v46[1],
          v1);
      }
      else
      {
        v17 = *(volatile signed __int32 **)v1;
        *(_QWORD *)v46[1] = *(_QWORD *)v1;
        if ( v17 )
          _InterlockedIncrement(v17);
        v46[1] = (char *)v46[1] + 8;
      }
    }
    catch ( SeException v62 )
    {
      v31 = v63;
      if ( v63 > 0 )
        v31 = (unsigned __int16)v63 | 0x80070000;
      v33 = v31;
      SeException::~SeException((SeException *)v62);
      v1 = v42;
    }
    catch ( std::bad_alloc v65 )
    {
      v33 = -2147024882;
      SeException::~SeException((SeException *)v65);
      v1 = v42;
    }
    catch ( ... )
    {
      v33 = -2147418113;
      v1 = v42;
    }
    _set_se_translator(v43);
    if ( v33 < 0 )
      goto LABEL_20;
    v54 = (volatile signed __int32 **)v1;
    v1 += 2;
    v42 = v1;
    v0 = g_pnpstate;
  }
  v2 = *((_DWORD *)v0 + 19);
  v3 = *((_DWORD *)v0 + 18);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v0 + 328));
  v32 = 0;
  for ( i = (volatile signed __int32 *)v46[0]; ; i += 2 )
  {
    v52[1] = i;
    v36 = (volatile signed __int32 **)v46[1];
    if ( i == v46[1] )
      break;
    lpCriticalSection = (LPCRITICAL_SECTION)(*(_QWORD *)(*(_QWORD *)i + 8LL) + 8LL);
    v35 = TryEnterCriticalSection(lpCriticalSection);
    if ( v35 )
    {
      if ( gc_toZero == *(_QWORD *)(*(_QWORD *)(*(_QWORD *)i + 8LL) + 280LL) )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
        v20 = *v51;
        v57 = *v51;
        v21 = *v51;
        v36 = *v51;
        v22 = *v40;
        v36 = *v40;
        while ( 1 )
        {
          v55 = v22;
          if ( v22 == v21 || (unsigned int)AutoPtr<NtpPeer>::operator==(v22, i) )
            break;
          ++v22;
        }
        v58 = v22;
        v23 = (struct _RTL_CRITICAL_SECTION *)((char *)g_pnpstate + 328);
        if ( v20 == v22 )
        {
          LeaveCriticalSection(v23);
          v32 = 0;
        }
        else
        {
          LeaveCriticalSection(v23);
          v32 = 0;
          LOBYTE(v34) = 0;
          v59 = v52;
          v24 = *(volatile signed __int32 **)i;
          v52[0] = v24;
          if ( v24 )
            _InterlockedIncrement(v24);
          v33 = PollPeer(v52, &v34);
          if ( v33 < 0 )
            goto LABEL_20;
          if ( (_BYTE)v34 )
          {
            v54 = &v43;
            v29 = AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(&v43, (volatile signed __int32 **)i);
            DemotePeer(v29);
          }
        }
      }
      LeaveCriticalSection(lpCriticalSection);
      v35 = 0;
    }
    v36 = (volatile signed __int32 **)i;
  }
  if ( v2 == v3 )
  {
LABEL_19:
    v33 = 0;
    goto LABEL_20;
  }
  v6 = v38;
  v40 = v38;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
  v38 = v6;
  v32 = 1;
  for ( j = *v6; ; ++j )
  {
    v41 = j;
    v8 = v38;
    v36 = v38[1];
    if ( j == v36 )
      break;
    v36 = (volatile signed __int32 **)_set_se_translator(SeTransFunc);
    v33 = 0;
    try
    {
      if ( hMem[1] == v45 )
      {
        std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::_Emplace_reallocate<AutoPtr<NtpPeer> const &>(
          hMem,
          hMem[1],
          j);
      }
      else
      {
        v9 = *j;
        *(_QWORD *)hMem[1] = *j;
        if ( v9 )
          _InterlockedIncrement(v9);
        hMem[1] = (char *)hMem[1] + 8;
      }
    }
    catch ( SeException v60 )
    {
      v30 = v61;
      if ( v61 > 0 )
        v30 = (unsigned __int16)v61 | 0x80070000;
      v33 = v30;
      SeException::~SeException((SeException *)v60);
      j = v41;
    }
    catch ( std::bad_alloc v64 )
    {
      v33 = -2147024882;
      SeException::~SeException((SeException *)v64);
      j = v41;
    }
    catch ( ... )
    {
      v33 = -2147418113;
      j = v41;
    }
    _set_se_translator(v36);
    if ( v33 < 0 )
      goto LABEL_20;
    v36 = j;
  }
  v10 = 0;
  v48 = 0;
  v11 = (volatile signed __int32 **)hMem[0];
  v56 = (volatile signed __int32 **)hMem[0];
  while ( 1 )
  {
    v36 = (volatile signed __int32 **)hMem[1];
    if ( v11 == hMem[1] )
      goto LABEL_17;
    lpCriticalSection = (LPCRITICAL_SECTION)(*((_QWORD *)*v11 + 1) + 8LL);
    v35 = TryEnterCriticalSection(lpCriticalSection);
    if ( v35 )
      break;
LABEL_47:
    v36 = v11++;
    v56 = v11;
    v48 = ++v10;
  }
  if ( gc_toZero != *(_QWORD *)(*((_QWORD *)*v11 + 1) + 280LL) )
  {
    LeaveCriticalSection(lpCriticalSection);
    v35 = 0;
    goto LABEL_47;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
  v32 = 0;
  *(_DWORD *)(*((_QWORD *)*v11 + 1) + 1528LL) = -2147023436;
  *(_DWORD *)(*((_QWORD *)*v11 + 1) + 1532LL) = 0;
  v36 = (volatile signed __int32 **)&v38;
  v28 = *v11;
  v38 = (volatile signed __int32 ***)v28;
  if ( v28 )
    _InterlockedIncrement(v28);
  v33 = ResolvePeer(&v38);
  if ( v33 >= 0 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
    v32 = 1;
    *((_BYTE *)g_pnpstate + 480) = 1;
    UpdatePeerListTimes();
LABEL_17:
    if ( *((_BYTE *)g_pnpstate + 480) == 1 && *v49 == (volatile signed __int32 *)*v51 && !*((_BYTE *)g_pnpstate + 481) )
    {
      v18 = (char **)*v40;
      v19 = v8[1];
      if ( *v40 != v19 )
      {
        v37 = *(_QWORD *)(*((_QWORD *)*v18 + 1) + 280LL);
        v36 = (volatile signed __int32 **)v18;
        v50 = (volatile signed __int32 **)v18;
        for ( k = (volatile signed __int32 **)(v18 + 1); ; ++k )
        {
          v50 = k;
          v49 = v19;
          if ( k == v19 )
            break;
          v27 = *((_QWORD *)*k + 1);
          if ( *(_QWORD *)(v27 + 280) < v37 )
            v37 = *(_QWORD *)(v27 + 280);
          v49 = k;
        }
      }
      if ( *v40 == v19 )
      {
        if ( (unsigned __int8)FileLogAllowEntry(13) )
          FileLogAdd(
            L"Logging error: NtpClient has been configured to acquire time from one or more time sources, however none of "
             "the sources are accessible. NTPCLIENT HAS NO SOURCE OF ACCURATE TIME.\n");
        goto LABEL_57;
      }
      if ( gc_toZero != v37 )
      {
        v26 = (v37 + 50000000) / 0x23C34600;
        v37 = v26;
        if ( !v26 )
          v26 = 1;
        v37 = v26;
        StringCchPrintfW(v66, 0x64u, L"%I64u", v26);
        if ( (unsigned __int8)FileLogAllowEntry(13) )
          FileLogAdd(
            L"Logging error: NtpClient has been configured to acquire time from one or more time sources, however none of "
             "the sources are currently accessible and no attempt to contact a source will be made for %s minutes. NTPCLI"
             "ENT HAS NO SOURCE OF ACCURATE TIME.\n",
            v66);
LABEL_57:
        *((_BYTE *)g_pnpstate + 480) = 0;
      }
    }
    _set_se_translator(v53);
    goto LABEL_19;
  }
LABEL_20:
  if ( v35 )
    LeaveCriticalSection(lpCriticalSection);
  if ( v32 )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
  v12 = (volatile signed __int32 **)hMem[0];
  if ( hMem[0] )
  {
    v13 = (volatile signed __int32 **)hMem[1];
    if ( hMem[0] != hMem[1] )
    {
      do
      {
        if ( *v12 && _InterlockedExchangeAdd(*v12, 0xFFFFFFFF) == 1 && *v12 )
          Ref<NtpPeer>::`scalar deleting destructor'(*v12, v4);
        ++v12;
      }
      while ( v12 != v13 );
      v12 = (volatile signed __int32 **)hMem[0];
    }
    LocalFree(v12);
    *(_OWORD *)hMem = 0;
    v45 = 0;
  }
  v14 = (volatile signed __int32 **)v46[0];
  if ( v46[0] )
  {
    v15 = (volatile signed __int32 **)v46[1];
    if ( v46[0] != v46[1] )
    {
      do
      {
        if ( *v14 && _InterlockedExchangeAdd(*v14, 0xFFFFFFFF) == 1 && *v14 )
          Ref<NtpPeer>::`scalar deleting destructor'(*v14, v4);
        ++v14;
      }
      while ( v14 != v15 );
      v14 = (volatile signed __int32 **)v46[0];
    }
    LocalFree(v14);
    *(_OWORD *)v46 = 0;
    v47 = 0;
  }
  return (unsigned int)v33;
}

```

## disassembly

```asm
0x180016960  push    rbx
0x180016962  push    rsi
0x180016963  push    rdi
0x180016964  push    r14
0x180016966  sub     rsp, 298h
0x18001696d  mov     rax, cs:__security_cookie
0x180016974  xor     rax, rsp
0x180016977  mov     [rsp+2B8h+var_38], rax
0x18001697f  mov     [rsp+2B8h+var_298], 0
0x180016984  xor     edi, edi
0x180016986  mov     [rsp+2B8h+var_28C], edi
0x18001698a  mov     [rsp+2B8h+var_280], rdi
0x18001698f  mov     [rsp+2B8h+lpCriticalSection], rdi
0x180016994  lea     rcx, [rsp+2B8h+var_230]
0x18001699c  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x1800169a1  nop
0x1800169a2  lea     rcx, [rsp+2B8h+hMem]
0x1800169a7  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x1800169ac  nop
0x1800169ad  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x1800169b4  call    cs:__imp__set_se_translator
0x1800169bb  nop     dword ptr [rax+rax+00h]
0x1800169c0  mov     [rsp+2B8h+var_1E8], rax
0x1800169c8  mov     [rsp+2B8h+var_294], edi
0x1800169cc  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800169d3  add     rcx, 148h; lpCriticalSection
0x1800169da  call    cs:__imp_EnterCriticalSection
0x1800169e1  nop     dword ptr [rax+rax+00h]
0x1800169e6  mov     [rsp+2B8h+var_298], 1
0x1800169eb  mov     rdx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800169f2  lea     rbx, [rdx+198h]
0x1800169f9  mov     [rsp+2B8h+var_210], rbx
0x180016a01  mov     [rsp+2B8h+var_268], rbx
0x180016a06  lea     rax, [rdx+1B0h]
0x180016a0d  mov     [rsp+2B8h+var_278], rax
0x180016a12  mov     rbx, [rbx]
0x180016a15  mov     [rsp+2B8h+var_258], rbx
0x180016a1a  mov     rax, [rsp+2B8h+var_268]
0x180016a1f  add     rax, 8
0x180016a23  mov     [rsp+2B8h+var_200], rax
0x180016a2b  mov     rcx, [rax]
0x180016a2e  mov     [rsp+2B8h+var_250], rcx
0x180016a33  cmp     rbx, rcx
0x180016a36  jnz     loc_180016CB0
0x180016a3c  mov     esi, [rdx+4Ch]
0x180016a3f  mov     r14d, [rdx+48h]
0x180016a43  lea     rcx, [rdx+148h]; lpCriticalSection
0x180016a4a  call    cs:__imp_LeaveCriticalSection
0x180016a51  nop     dword ptr [rax+rax+00h]
0x180016a56  mov     [rsp+2B8h+var_298], 0
0x180016a5b  mov     rbx, [rsp+2B8h+var_230]
0x180016a63  mov     [rsp+2B8h+var_1F0], rbx
0x180016a6b  mov     rax, [rsp+2B8h+var_230+8]
0x180016a73  mov     [rsp+2B8h+var_288], rax
0x180016a78  cmp     rbx, rax
0x180016a7b  jnz     loc_180016D7F
0x180016a81  cmp     esi, r14d
0x180016a84  jz      loc_18001702C
0x180016a8a  mov     rbx, [rsp+2B8h+var_278]
0x180016a8f  mov     [rsp+2B8h+var_268], rbx
0x180016a94  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180016a9b  add     rcx, 148h; lpCriticalSection
0x180016aa2  call    cs:__imp_EnterCriticalSection
0x180016aa9  nop     dword ptr [rax+rax+00h]
0x180016aae  mov     [rsp+2B8h+var_278], rbx
0x180016ab3  mov     [rsp+2B8h+var_298], 1
0x180016ab8  mov     rbx, [rbx]
0x180016abb  mov     [rsp+2B8h+var_260], rbx
0x180016ac0  mov     rsi, [rsp+2B8h+var_278]
0x180016ac5  mov     rax, [rsi+8]
0x180016ac9  mov     [rsp+2B8h+var_288], rax
0x180016ace  cmp     rbx, rax
0x180016ad1  jz      short loc_180016B40
0x180016ad3  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x180016ada  call    cs:__imp__set_se_translator
0x180016ae1  nop     dword ptr [rax+rax+00h]
0x180016ae6  mov     [rsp+2B8h+var_288], rax
0x180016aeb  mov     [rsp+2B8h+var_294], edi
0x180016aef  mov     rdx, [rsp+2B8h+hMem+8]
0x180016af4  cmp     rdx, [rsp+2B8h+var_238]
0x180016afc  jz      loc_180016DB0
0x180016b02  mov     rax, [rbx]
0x180016b05  mov     [rdx], rax
0x180016b08  test    rax, rax
0x180016b0b  jz      short loc_180016B10
0x180016b0d  lock inc dword ptr [rax]
0x180016b10  add     [rsp+2B8h+hMem+8], 8
0x180016b16  mov     rcx, [rsp+2B8h+var_288]
0x180016b1b  call    cs:__imp__set_se_translator
0x180016b22  nop     dword ptr [rax+rax+00h]
0x180016b27  cmp     [rsp+2B8h+var_294], 0
0x180016b2c  jl      loc_1800171A7
0x180016b32  mov     [rsp+2B8h+var_288], rbx
0x180016b37  add     rbx, 8
0x180016b3b  jmp     loc_180016ABB
0x180016b40  mov     r14d, edi
0x180016b43  mov     [rsp+2B8h+var_218], edi
0x180016b4a  mov     rbx, [rsp+2B8h+hMem]
0x180016b4f  mov     [rsp+2B8h+var_1D0], rbx
0x180016b57  mov     rax, [rsp+2B8h+hMem+8]
0x180016b5c  mov     [rsp+2B8h+var_288], rax
0x180016b61  cmp     rbx, rax
0x180016b64  jnz     loc_180016D32
0x180016b6a  mov     rdx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180016b71  cmp     byte ptr [rdx+1E0h], 1
0x180016b78  jz      loc_180016DC2
0x180016b7e  mov     rcx, [rsp+2B8h+var_1E8]
0x180016b86  call    cs:__imp__set_se_translator
0x180016b8d  nop     dword ptr [rax+rax+00h]
0x180016b92  cmp     [rsp+2B8h+var_294], 0
0x180016b97  jl      short loc_180016B9D
0x180016b99  mov     [rsp+2B8h+var_294], edi
0x180016b9d  cmp     [rsp+2B8h+var_28C], 0
0x180016ba2  jnz     loc_180017016
0x180016ba8  cmp     [rsp+2B8h+var_298], 0
0x180016bad  jz      short loc_180016BCA
0x180016baf  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180016bb6  add     rcx, 148h; lpCriticalSection
0x180016bbd  call    cs:__imp_LeaveCriticalSection
0x180016bc4  nop     dword ptr [rax+rax+00h]
0x180016bc9  nop
0x180016bca  mov     rbx, [rsp+2B8h+hMem]
0x180016bcf  test    rbx, rbx
0x180016bd2  jz      short loc_180016C26
0x180016bd4  mov     rsi, [rsp+2B8h+hMem+8]
0x180016bd9  cmp     rbx, rsi
0x180016bdc  jz      short loc_180016C06
0x180016bde  mov     rcx, [rbx]
0x180016be1  test    rcx, rcx
0x180016be4  jz      short loc_180016BF8
0x180016be6  mov     eax, 0FFFFFFFFh
0x180016beb  lock xadd [rcx], eax
0x180016bef  cmp     eax, 1
0x180016bf2  jz      loc_18001705C
0x180016bf8  add     rbx, 8
0x180016bfc  cmp     rbx, rsi
0x180016bff  jnz     short loc_180016BDE
0x180016c01  mov     rbx, [rsp+2B8h+hMem]
0x180016c06  mov     rcx, rbx; hMem
0x180016c09  call    cs:__imp_LocalFree
0x180016c10  nop     dword ptr [rax+rax+00h]
0x180016c15  xorps   xmm0, xmm0
0x180016c18  movdqu  xmmword ptr [rsp+2B8h+hMem], xmm0
0x180016c1e  mov     [rsp+2B8h+var_238], rdi
0x180016c26  mov     rbx, [rsp+2B8h+var_230]
0x180016c2e  test    rbx, rbx
0x180016c31  jz      short loc_180016C8E
0x180016c33  mov     rsi, [rsp+2B8h+var_230+8]
0x180016c3b  cmp     rbx, rsi
0x180016c3e  jz      short loc_180016C6B
0x180016c40  mov     rcx, [rbx]
0x180016c43  test    rcx, rcx
0x180016c46  jz      short loc_180016C5A
0x180016c48  mov     eax, 0FFFFFFFFh
0x180016c4d  lock xadd [rcx], eax
0x180016c51  cmp     eax, 1
0x180016c54  jz      loc_180017072
0x180016c5a  add     rbx, 8
0x180016c5e  cmp     rbx, rsi
0x180016c61  jnz     short loc_180016C40
0x180016c63  mov     rbx, [rsp+2B8h+var_230]
0x180016c6b  mov     rcx, rbx; hMem
0x180016c6e  call    cs:__imp_LocalFree
0x180016c75  nop     dword ptr [rax+rax+00h]
0x180016c7a  xorps   xmm0, xmm0
0x180016c7d  movdqu  xmmword ptr [rsp+2B8h+var_230], xmm0
0x180016c86  mov     [rsp+2B8h+var_220], rdi
0x180016c8e  mov     eax, [rsp+2B8h+var_294]
0x180016c92  mov     rcx, [rsp+2B8h+var_38]
0x180016c9a  xor     rcx, rsp; StackCookie
0x180016c9d  call    __security_check_cookie
0x180016ca2  add     rsp, 298h
0x180016ca9  pop     r14
0x180016cab  pop     rdi
0x180016cac  pop     rsi
0x180016cad  pop     rbx
0x180016cae  retn
0x180016cb0  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x180016cb7  call    cs:__imp__set_se_translator
0x180016cbe  nop     dword ptr [rax+rax+00h]
0x180016cc3  mov     [rsp+2B8h+var_250], rax
0x180016cc8  mov     [rsp+2B8h+var_294], edi
0x180016ccc  mov     rdx, [rsp+2B8h+var_230+8]
0x180016cd4  cmp     rdx, [rsp+2B8h+var_220]
0x180016cdc  jz      loc_180016F33
0x180016ce2  mov     rax, [rbx]
0x180016ce5  mov     [rdx], rax
0x180016ce8  test    rax, rax
0x180016ceb  jz      short loc_180016CF0
0x180016ced  lock inc dword ptr [rax]
0x180016cf0  add     [rsp+2B8h+var_230+8], 8
0x180016cf9  mov     rcx, [rsp+2B8h+var_250]
0x180016cfe  call    cs:__imp__set_se_translator
0x180016d05  nop     dword ptr [rax+rax+00h]
0x180016d0a  cmp     [rsp+2B8h+var_294], 0
0x180016d0f  jl      loc_18001721B
0x180016d15  mov     [rsp+2B8h+var_1E0], rbx
0x180016d1d  add     rbx, 8
0x180016d21  mov     [rsp+2B8h+var_258], rbx
0x180016d26  mov     rdx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180016d2d  jmp     loc_180016A1A
0x180016d32  mov     rax, [rbx]
0x180016d35  mov     rcx, [rax+8]
0x180016d39  add     rcx, 8; lpCriticalSection
0x180016d3d  mov     [rsp+2B8h+lpCriticalSection], rcx
0x180016d42  call    cs:__imp_TryEnterCriticalSection
0x180016d49  nop     dword ptr [rax+rax+00h]
0x180016d4e  mov     [rsp+2B8h+var_28C], eax
0x180016d52  mov     [rsp+2B8h+var_294], edi
0x180016d56  test    eax, eax
0x180016d58  jnz     loc_180017088
0x180016d5e  mov     [rsp+2B8h+var_288], rbx
0x180016d63  add     rbx, 8
0x180016d67  mov     [rsp+2B8h+var_1D0], rbx
0x180016d6f  inc     r14d
0x180016d72  mov     [rsp+2B8h+var_218], r14d
0x180016d7a  jmp     loc_180016B57
0x180016d7f  mov     rax, [rbx]
0x180016d82  mov     rcx, [rax+8]
0x180016d86  add     rcx, 8; lpCriticalSection
0x180016d8a  mov     [rsp+2B8h+lpCriticalSection], rcx
0x180016d8f  call    cs:__imp_TryEnterCriticalSection
0x180016d96  nop     dword ptr [rax+rax+00h]
0x180016d9b  mov     [rsp+2B8h+var_28C], eax
0x180016d9f  mov     [rsp+2B8h+var_294], edi
0x180016da3  test    eax, eax
0x180016da5  jnz     loc_180017166
0x180016dab  jmp     loc_180016F25
0x180016db0  mov     r8, rbx
0x180016db3  lea     rcx, [rsp+2B8h+hMem]
0x180016db8  call    ??$_Emplace_reallocate@AEBV?$AutoPtr@UNtpPeer@@@@@?$vector@V?$AutoPtr@UNtpPeer@@@@V?$MyThrowingAllocator@V?$AutoPtr@UNtpPeer@@@@@@@std@@AEAAPEAV?$AutoPtr@UNtpPeer@@@@QEAV2@AEBV2@@Z; std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::_Emplace_reallocate<AutoPtr<NtpPeer> const &>(AutoPtr<NtpPeer> * const,AutoPtr<NtpPeer> const &)
0x180016dbd  jmp     loc_180016B16
0x180016dc2  mov     rax, [rsp+2B8h+var_200]
0x180016dca  mov     rcx, [rax]
0x180016dcd  mov     rax, [rsp+2B8h+var_210]
0x180016dd5  cmp     [rax], rcx
0x180016dd8  jnz     loc_180016B7E
0x180016dde  cmp     byte ptr [rdx+1E1h], 0
0x180016de5  jnz     loc_180016B7E
0x180016deb  mov     rax, [rsp+2B8h+var_268]
0x180016df0  mov     rdx, [rax]
0x180016df3  mov     r8, [rsi+8]
0x180016df7  cmp     rdx, r8
0x180016dfa  jnz     loc_180016F48
0x180016e00  mov     rax, [rsp+2B8h+var_268]
0x180016e05  cmp     [rax], r8
0x180016e08  jnz     loc_180016F8A
0x180016e0e  mov     ecx, 0Dh
0x180016e13  call    FileLogAllowEntry
0x180016e18  test    al, al
0x180016e1a  jnz     loc_180017186
0x180016e20  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180016e27  mov     byte ptr [rax+1E0h], 0
0x180016e2e  jmp     loc_180016B7E
0x180016e33  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180016e3a  add     rcx, 148h; lpCriticalSection
0x180016e41  call    cs:__imp_EnterCriticalSection
0x180016e48  nop     dword ptr [rax+rax+00h]
0x180016e4d  mov     [rsp+2B8h+var_298], 1
0x180016e52  mov     rax, [rsp+2B8h+var_200]
0x180016e5a  mov     r9, [rax]
0x180016e5d  mov     [rsp+2B8h+var_1C8], r9
0x180016e65  mov     r11, [rax]
0x180016e68  mov     [rsp+2B8h+var_288], r11
0x180016e6d  mov     rax, [rsp+2B8h+var_268]
0x180016e72  mov     r10, [rax]
0x180016e75  mov     [rsp+2B8h+var_288], r10
0x180016e7a  mov     [rsp+2B8h+var_1D8], r10
0x180016e82  cmp     r10, r11
0x180016e85  jnz     loc_1800171AC
0x180016e8b  mov     [rsp+2B8h+var_1C0], r10
0x180016e93  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180016e9a  add     rcx, 148h; lpCriticalSection
0x180016ea1  cmp     r9, r10
0x180016ea4  jz      loc_1800171C8
0x180016eaa  call    cs:__imp_LeaveCriticalSection
0x180016eb1  nop     dword ptr [rax+rax+00h]
0x180016eb6  mov     [rsp+2B8h+var_298], 0
0x180016ebb  mov     byte ptr [rsp+2B8h+var_290], 0
0x180016ec0  lea     rax, [rsp+2B8h+var_1F8]
0x180016ec8  mov     [rsp+2B8h+var_1B8], rax
0x180016ed0  mov     rax, [rbx]
0x180016ed3  mov     [rsp+2B8h+var_1F8], rax
0x180016edb  test    rax, rax
0x180016ede  jz      short loc_180016EE3
0x180016ee0  lock inc dword ptr [rax]
0x180016ee3  lea     rdx, [rsp+2B8h+var_290]
0x180016ee8  lea     rcx, [rsp+2B8h+var_1F8]
0x180016ef0  call    ?PollPeer@@YAJV?$AutoPtr@UNtpPeer@@@@PEA_N@Z; PollPeer(AutoPtr<NtpPeer>,bool *)
0x180016ef5  mov     [rsp+2B8h+var_294], eax
0x180016ef9  test    eax, eax
0x180016efb  js      loc_1800171DE
0x180016f01  cmp     byte ptr [rsp+2B8h+var_290], 0
0x180016f06  jnz     loc_1800171E3
0x180016f0c  mov     rcx, [rsp+2B8h+lpCriticalSection]; lpCriticalSection
0x180016f11  call    cs:__imp_LeaveCriticalSection
0x180016f18  nop     dword ptr [rax+rax+00h]
0x180016f1d  mov     [rsp+2B8h+var_294], edi
0x180016f21  mov     [rsp+2B8h+var_28C], edi
0x180016f25  mov     [rsp+2B8h+var_288], rbx
  ... truncated ...
```
