# WnpKaDetectorImpl::BeginKeepAliveMeasurement(void *,_KAMSS_MEASUREMENT_HANDLE *,_KEEP_ALIVE_SAMPLE_SET *,void * *)

- ea: `0x18008a040`
- end: `0x18008a6d7`
- name: `?BeginKeepAliveMeasurement@WnpKaDetectorImpl@@SAKPEAXPEAU_KAMSS_MEASUREMENT_HANDLE@@PEAU_KEEP_ALIVE_SAMPLE_SET@@PEAPEAX@Z`
- size: `1687`
- prototype: `__int64 __fastcall(char *, struct _KAMSS_MEASUREMENT_HANDLE *, struct _KEEP_ALIVE_SAMPLE_SET *, void **)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180007924`
- `0x18000795c`
- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18001c06c`
- `0x18002f348`
- `0x18008a040`
- `0x18008a9b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18008a4f6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18008a503`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18008a4f6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18008a503`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008a549`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008a549`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008a3a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008a3a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008a332`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008a332`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008a48f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008a48f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008a50c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008a50c`

## pseudocode

```c
__int64 __fastcall WnpKaDetectorImpl::BeginKeepAliveMeasurement(
        char *a1,
        struct _KAMSS_MEASUREMENT_HANDLE *a2,
        struct _KEEP_ALIVE_SAMPLE_SET *a3,
        void **a4)
{
  unsigned int v8; // eax
  unsigned int v9; // r15d
  unsigned int v10; // edi
  unsigned int v11; // ebx
  PVOID *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rax
  _OWORD *v17; // rax
  _DWORD *v18; // rbp
  __int64 v19; // rax
  int v20; // ecx
  struct _TP_WORK *v21; // r14
  void *v22; // rcx
  signed int v23; // eax
  __int64 v24; // r9
  PVOID *v25; // rcx
  int v27; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 202, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids);
  }
  v8 = WnpKaDetectorImpl::ConvertToSecond(*((_DWORD *)a1 + 49), *((_DWORD *)a1 + 59));
  *a4 = 0;
  v9 = v8;
  if ( !a2 )
  {
    v10 = 6;
    v11 = -2147024890;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 203, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids, 2147942406LL);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x80D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\kadetector\\wnpkadetectorimpl.cpp",
      (const char *)0x80070006LL,
      v27);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v13 = 204;
        v14 = 2147942406LL;
LABEL_108:
        WPP_SF_d(v12[2], v13, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids, v14);
        goto LABEL_109;
      }
      goto LABEL_110;
    }
    return v10;
  }
  if ( !a3 )
  {
    v10 = 87;
    v11 = -2147024809;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 207, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids, 2147942487LL);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x81B,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\kadetector\\wnpkadetectorimpl.cpp",
      (const char *)0x80070057LL,
      v27);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v10;
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_110;
    v13 = 208;
    goto LABEL_107;
  }
  v15 = *((_QWORD *)a3 + 2);
  if ( !v15 || (v16 = *(_QWORD *)(v15 + 8)) == 0 )
  {
    v10 = 87;
    v11 = -2147024809;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 209, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids, 2147942487LL);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x822,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\kadetector\\wnpkadetectorimpl.cpp",
      (const char *)0x80070057LL,
      v27);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v10;
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_110;
    v13 = 210;
LABEL_107:
    v14 = 2147942487LL;
    goto LABEL_108;
  }
  if ( *(_DWORD *)(v15 + 16) == -1 )
  {
    v10 = 87;
    v11 = -2147024809;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 211, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids, 2147942487LL);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x829,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\kadetector\\wnpkadetectorimpl.cpp",
      (const char *)0x80070057LL,
      v27);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v10;
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_110;
    v13 = 212;
    goto LABEL_107;
  }
  if ( *(_DWORD *)v16 || *(_DWORD *)(v16 + 4) != 6 || *(_WORD *)(v16 + 8) != 443 )
  {
    v10 = 50;
    v11 = -2147024846;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 213, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids, 2147942450LL);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x834,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\kadetector\\wnpkadetectorimpl.cpp",
      (const char *)0x80070032LL,
      v27);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v13 = 214;
        v14 = 2147942450LL;
        goto LABEL_108;
      }
      goto LABEL_110;
    }
    return v10;
  }
  if ( *(_QWORD *)v15 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v15);
  v17 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v18 = v17;
  if ( v17 )
  {
    *v17 = 0;
    v17[1] = 0;
    *((_DWORD *)v17 + 4) = *(_DWORD *)(*((_QWORD *)a3 + 2) + 16LL);
    v19 = *((_QWORD *)a3 + 2);
    if ( *(_DWORD *)(v19 + 20) < v9 )
      v9 = *(_DWORD *)(v19 + 20);
    v18[5] = v9;
    v18[6] = *(_DWORD *)(*((_QWORD *)a3 + 2) + 24LL);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 352));
    if ( *((_QWORD *)a1 + 40) )
    {
      v21 = 0;
      v10 = 50;
    }
    else
    {
      v10 = 0;
      if ( (byte_1800AFD84 & 1) != 0 )
        McTemplateU0qqq_EventWriteTransfer(v20, (unsigned int)WPNPRV_TRANS_START_KA_MEASUREMENT, v18[4], v18[5], v18[6]);
      v22 = (void *)*((_QWORD *)a1 + 35);
      if ( v22 )
        operator delete(v22, (const struct std::nothrow_t *)0x20);
      *((_QWORD *)a1 + 35) = v18;
      v18 = 0;
      *((_QWORD *)a1 + 40) = a2;
      v21 = (struct _TP_WORK *)*((_QWORD *)a1 + 49);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 352));
    v23 = v10;
    if ( v10 )
      v23 = v10 | 0x80070000;
    if ( v23 < 0 )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_63:
        v11 = v10;
        if ( v10 )
          v11 = v10 | 0x80070000;
        if ( (v11 & 0x80000000) == 0 )
        {
          if ( v21 )
          {
            if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 && *((_BYTE *)v12 + 25) >= 5u )
              WPP_SF_(v12[2], 219, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids);
            WaitForThreadpoolWorkCallbacks(v21, 0);
            v25 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 220, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids);
                v25 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 8) != 0 && *((_BYTE *)v25 + 25) >= 5u )
                WPP_SF_(v25[2], 221, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids);
            }
            ResetEvent(*((HANDLE *)a1 + 50));
            ResetEvent(*((HANDLE *)a1 + 51));
            SubmitThreadpoolWork(v21);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 222, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids);
            }
            WaitForSingleObject(*((HANDLE *)a1 + 51), 0xFFFFFFFF);
            v12 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 223, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids);
              goto LABEL_90;
            }
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x861,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\kadetector\\wnpkadetectorimpl.cpp",
            (const char *)v11,
            v27);
          v12 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 218, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids, v11);
LABEL_90:
            v12 = (PVOID *)WPP_GLOBAL_Control;
          }
        }
        if ( v18 )
        {
          operator delete(v18, (const struct std::nothrow_t *)0x20);
LABEL_109:
          v12 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_110;
        }
        goto LABEL_110;
      }
      v24 = v10;
      if ( v10 )
        v24 = v10 | 0x80070000;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 217, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids, v24);
    }
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_63;
  }
  v10 = 14;
  v11 = -2147024882;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 215, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids, 2147942414LL);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x83F,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\kadetector\\wnpkadetectorimpl.cpp",
    (const char *)0x8007000ELL,
    v27);
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v13 = 216;
      v14 = 2147942414LL;
      goto LABEL_108;
    }
LABEL_110:
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 && *((_BYTE *)v12 + 25) >= 6u )
      WPP_SF_d(v12[2], 224, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids, v11);
  }
  return v10;
}

```

## disassembly

```asm
0x18008a040  push    rbx
0x18008a042  push    rbp
0x18008a043  push    rsi
0x18008a044  push    rdi
0x18008a045  push    r13
0x18008a047  push    r14
0x18008a049  push    r15
0x18008a04b  sub     rsp, 30h
0x18008a04f  mov     rdi, r9
0x18008a052  mov     rbx, r8
0x18008a055  mov     r14, rdx
0x18008a058  mov     rsi, rcx
0x18008a05b  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a062  lea     r13, WPP_GLOBAL_Control
0x18008a069  cmp     rcx, r13
0x18008a06c  jz      short loc_18008A08F
0x18008a06e  test    byte ptr [rcx+1Ch], 8
0x18008a072  jz      short loc_18008A08F
0x18008a074  cmp     byte ptr [rcx+19h], 6
0x18008a078  jb      short loc_18008A08F
0x18008a07a  mov     rcx, [rcx+10h]
0x18008a07e  lea     r8, WPP_9a262fb51b93373699b13bc917fc3706_Traceguids
0x18008a085  mov     edx, 0CAh
0x18008a08a  call    WPP_SF_
0x18008a08f  mov     edx, [rsi+0ECh]; unsigned int
0x18008a095  mov     ecx, [rsi+0C4h]; unsigned int
0x18008a09b  call    ?ConvertToSecond@WnpKaDetectorImpl@@SAKKK@Z; WnpKaDetectorImpl::ConvertToSecond(ulong,ulong)
0x18008a0a0  mov     qword ptr [rdi], 0
0x18008a0a7  mov     r15d, eax
0x18008a0aa  test    r14, r14
0x18008a0ad  jnz     short loc_18008A12B
0x18008a0af  lea     edi, [r14+6]
0x18008a0b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a0ba  mov     ebx, 80070006h
0x18008a0bf  cmp     rcx, r13
0x18008a0c2  jz      short loc_18008A0E8
0x18008a0c4  test    byte ptr [rcx+1Ch], 8
0x18008a0c8  jz      short loc_18008A0E8
0x18008a0ca  cmp     byte ptr [rcx+19h], 2
0x18008a0ce  jb      short loc_18008A0E8
0x18008a0d0  mov     rcx, [rcx+10h]
0x18008a0d4  lea     r8, WPP_9a262fb51b93373699b13bc917fc3706_Traceguids
0x18008a0db  mov     edx, 0CBh
0x18008a0e0  mov     r9d, ebx
0x18008a0e3  call    WPP_SF_d
0x18008a0e8  mov     rcx, [rsp+68h]; this
0x18008a0ed  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008a0f4  mov     r9d, ebx; char *
0x18008a0f7  mov     edx, 80Dh; void *
0x18008a0fc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008a101  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a108  cmp     rcx, r13
0x18008a10b  jz      loc_18008A6C6
0x18008a111  test    byte ptr [rcx+1Ch], 80h
0x18008a115  jz      loc_18008A69D
0x18008a11b  mov     edx, 0CCh
0x18008a120  mov     r9d, 80070006h
0x18008a126  jmp     loc_18008A686
0x18008a12b  test    rbx, rbx
0x18008a12e  jnz     short loc_18008A1A3
0x18008a130  lea     edi, [rbx+57h]
0x18008a133  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a13a  mov     ebx, 80070057h
0x18008a13f  cmp     rcx, r13
0x18008a142  jz      short loc_18008A166
0x18008a144  test    byte ptr [rcx+1Ch], 8
0x18008a148  jz      short loc_18008A166
0x18008a14a  cmp     byte ptr [rcx+19h], 2
0x18008a14e  jb      short loc_18008A166
0x18008a150  mov     rcx, [rcx+10h]
0x18008a154  lea     edx, [rdi+78h]
0x18008a157  mov     r9d, ebx
0x18008a15a  lea     r8, WPP_9a262fb51b93373699b13bc917fc3706_Traceguids
0x18008a161  call    WPP_SF_d
0x18008a166  mov     rcx, [rsp+68h]; this
0x18008a16b  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008a172  mov     r9d, ebx; char *
0x18008a175  mov     edx, 81Bh; void *
0x18008a17a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008a17f  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a186  cmp     rcx, r13
0x18008a189  jz      loc_18008A6C6
0x18008a18f  test    byte ptr [rcx+1Ch], 80h
0x18008a193  jz      loc_18008A69D
0x18008a199  mov     edx, 0D0h
0x18008a19e  jmp     loc_18008A680
0x18008a1a3  mov     rcx, [rbx+10h]
0x18008a1a7  test    rcx, rcx
0x18008a1aa  jz      loc_18008A618
0x18008a1b0  mov     rax, [rcx+8]
0x18008a1b4  test    rax, rax
0x18008a1b7  jz      loc_18008A618
0x18008a1bd  cmp     dword ptr [rcx+10h], 0FFFFFFFFh
0x18008a1c1  jnz     short loc_18008A238
0x18008a1c3  mov     edi, 57h ; 'W'
0x18008a1c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a1cf  mov     ebx, 80070057h
0x18008a1d4  cmp     rcx, r13
0x18008a1d7  jz      short loc_18008A1FB
0x18008a1d9  test    byte ptr [rcx+1Ch], 8
0x18008a1dd  jz      short loc_18008A1FB
0x18008a1df  cmp     byte ptr [rcx+19h], 2
0x18008a1e3  jb      short loc_18008A1FB
0x18008a1e5  mov     rcx, [rcx+10h]
0x18008a1e9  lea     edx, [rdi+7Ch]
0x18008a1ec  mov     r9d, ebx
0x18008a1ef  lea     r8, WPP_9a262fb51b93373699b13bc917fc3706_Traceguids
0x18008a1f6  call    WPP_SF_d
0x18008a1fb  mov     rcx, [rsp+68h]; this
0x18008a200  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008a207  mov     r9d, ebx; char *
0x18008a20a  mov     edx, 829h; void *
0x18008a20f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008a214  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a21b  cmp     rcx, r13
0x18008a21e  jz      loc_18008A6C6
0x18008a224  test    byte ptr [rcx+1Ch], 80h
0x18008a228  jz      loc_18008A69D
0x18008a22e  mov     edx, 0D4h
0x18008a233  jmp     loc_18008A680
0x18008a238  cmp     dword ptr [rax], 0
0x18008a23b  jnz     loc_18008A59E
0x18008a241  cmp     dword ptr [rax+4], 6
0x18008a245  jnz     loc_18008A59E
0x18008a24b  mov     edx, 1BBh
0x18008a250  cmp     [rax+8], dx
0x18008a254  jnz     loc_18008A59E
0x18008a25a  cmp     qword ptr [rcx], 0
0x18008a25e  jz      short loc_18008A265
0x18008a260  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008a265  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008a26c  mov     ecx, 20h ; ' '; unsigned __int64
0x18008a271  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18008a276  mov     rbp, rax
0x18008a279  test    rax, rax
0x18008a27c  jnz     short loc_18008A2F9
0x18008a27e  lea     edi, [rax+0Eh]
0x18008a281  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a288  mov     ebx, 8007000Eh
0x18008a28d  cmp     rcx, r13
0x18008a290  jz      short loc_18008A2B6
0x18008a292  test    byte ptr [rcx+1Ch], 8
0x18008a296  jz      short loc_18008A2B6
0x18008a298  cmp     byte ptr [rcx+19h], 2
0x18008a29c  jb      short loc_18008A2B6
0x18008a29e  mov     rcx, [rcx+10h]
0x18008a2a2  lea     r8, WPP_9a262fb51b93373699b13bc917fc3706_Traceguids
0x18008a2a9  mov     edx, 0D7h
0x18008a2ae  mov     r9d, ebx
0x18008a2b1  call    WPP_SF_d
0x18008a2b6  mov     rcx, [rsp+68h]; this
0x18008a2bb  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008a2c2  mov     r9d, ebx; char *
0x18008a2c5  mov     edx, 83Fh; void *
0x18008a2ca  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008a2cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a2d6  cmp     rcx, r13
0x18008a2d9  jz      loc_18008A6C6
0x18008a2df  test    byte ptr [rcx+1Ch], 80h
0x18008a2e3  jz      loc_18008A69D
0x18008a2e9  mov     edx, 0D8h
0x18008a2ee  mov     r9d, 8007000Eh
0x18008a2f4  jmp     loc_18008A686
0x18008a2f9  xorps   xmm0, xmm0
0x18008a2fc  movups  xmmword ptr [rax], xmm0
0x18008a2ff  movups  xmmword ptr [rax+10h], xmm0
0x18008a303  mov     rax, [rbx+10h]
0x18008a307  mov     ecx, [rax+10h]
0x18008a30a  mov     [rbp+10h], ecx
0x18008a30d  mov     rax, [rbx+10h]
0x18008a311  cmp     [rax+14h], r15d
0x18008a315  cmovb   r15d, [rax+14h]
0x18008a31a  mov     [rbp+14h], r15d
0x18008a31e  mov     rax, [rbx+10h]
0x18008a322  lea     rbx, [rsi+160h]
0x18008a329  mov     ecx, [rax+18h]
0x18008a32c  mov     [rbp+18h], ecx
0x18008a32f  mov     rcx, rbx; lpCriticalSection
0x18008a332  call    cs:__imp_EnterCriticalSection
0x18008a338  cmp     qword ptr [rsi+140h], 0
0x18008a340  jz      short loc_18008A34B
0x18008a342  xor     r14d, r14d
0x18008a345  lea     edi, [r14+32h]
0x18008a349  jmp     short loc_18008A39E
0x18008a34b  xor     edi, edi
0x18008a34d  test    cs:byte_1800AFD84, 1
0x18008a354  jz      short loc_18008A371
0x18008a356  mov     eax, [rbp+18h]
0x18008a359  lea     rdx, WPNPRV_TRANS_START_KA_MEASUREMENT
0x18008a360  mov     r9d, [rbp+14h]
0x18008a364  mov     r8d, [rbp+10h]
0x18008a368  mov     [rsp+68h+var_48], eax; int
0x18008a36c  call    McTemplateU0qqq_EventWriteTransfer
0x18008a371  mov     rcx, [rsi+118h]; void *
0x18008a378  test    rcx, rcx
0x18008a37b  jz      short loc_18008A387
0x18008a37d  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x18008a382  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008a387  mov     [rsi+118h], rbp
0x18008a38e  xor     ebp, ebp
0x18008a390  mov     [rsi+140h], r14
0x18008a397  mov     r14, [rsi+188h]
0x18008a39e  mov     rcx, rbx; lpCriticalSection
0x18008a3a1  call    cs:__imp_LeaveCriticalSection
0x18008a3a7  mov     ecx, edi
0x18008a3a9  mov     r15d, 80070000h
0x18008a3af  or      ecx, r15d
0x18008a3b2  mov     eax, edi
0x18008a3b4  test    edi, edi
0x18008a3b6  cmovnz  eax, ecx
0x18008a3b9  test    eax, eax
0x18008a3bb  jns     short loc_18008A3F4
0x18008a3bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a3c4  cmp     rcx, r13
0x18008a3c7  jz      short loc_18008A3FB
0x18008a3c9  test    byte ptr [rcx+1Ch], 8
0x18008a3cd  jz      short loc_18008A3FB
0x18008a3cf  cmp     byte ptr [rcx+19h], 2
0x18008a3d3  jb      short loc_18008A3FB
0x18008a3d5  mov     r9d, edi
0x18008a3d8  test    edi, edi
0x18008a3da  jz      short loc_18008A3DF
0x18008a3dc  or      r9d, r15d
0x18008a3df  mov     rcx, [rcx+10h]
0x18008a3e3  lea     r8, WPP_9a262fb51b93373699b13bc917fc3706_Traceguids
0x18008a3ea  mov     edx, 0D9h
0x18008a3ef  call    WPP_SF_d
0x18008a3f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a3fb  mov     ebx, edi
0x18008a3fd  test    edi, edi
0x18008a3ff  jz      short loc_18008A404
0x18008a401  or      ebx, r15d
0x18008a404  test    ebx, ebx
0x18008a406  jns     short loc_18008A458
0x18008a408  mov     rcx, [rsp+68h]; this
0x18008a40d  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008a414  mov     r9d, ebx; char *
0x18008a417  mov     edx, 861h; void *
0x18008a41c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008a421  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a428  cmp     rcx, r13
0x18008a42b  jz      loc_18008A583
0x18008a431  test    byte ptr [rcx+1Ch], 80h
0x18008a435  jz      loc_18008A583
0x18008a43b  mov     rcx, [rcx+10h]
0x18008a43f  lea     r8, WPP_9a262fb51b93373699b13bc917fc3706_Traceguids
0x18008a446  mov     edx, 0DAh
0x18008a44b  mov     r9d, ebx
0x18008a44e  call    WPP_SF_d
0x18008a453  jmp     loc_18008A57C
0x18008a458  test    r14, r14
0x18008a45b  jz      loc_18008A583
0x18008a461  mov     r15b, 5
0x18008a464  cmp     rcx, r13
0x18008a467  jz      short loc_18008A48A
0x18008a469  test    byte ptr [rcx+1Ch], 8
0x18008a46d  jz      short loc_18008A48A
0x18008a46f  cmp     [rcx+19h], r15b
0x18008a473  jb      short loc_18008A48A
0x18008a475  mov     rcx, [rcx+10h]
0x18008a479  lea     r8, WPP_9a262fb51b93373699b13bc917fc3706_Traceguids
0x18008a480  mov     edx, 0DBh
0x18008a485  call    WPP_SF_
0x18008a48a  xor     edx, edx; fCancelPendingCallbacks
0x18008a48c  mov     rcx, r14; pwk
0x18008a48f  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18008a495  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a49c  cmp     rcx, r13
0x18008a49f  jz      short loc_18008A4EF
0x18008a4a1  test    byte ptr [rcx+1Ch], 8
0x18008a4a5  jz      short loc_18008A4C9
0x18008a4a7  cmp     [rcx+19h], r15b
0x18008a4ab  jb      short loc_18008A4C9
0x18008a4ad  mov     rcx, [rcx+10h]
0x18008a4b1  lea     r8, WPP_9a262fb51b93373699b13bc917fc3706_Traceguids
0x18008a4b8  mov     edx, 0DCh
0x18008a4bd  call    WPP_SF_
0x18008a4c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a4c9  cmp     rcx, r13
0x18008a4cc  jz      short loc_18008A4EF
0x18008a4ce  test    byte ptr [rcx+1Ch], 8
0x18008a4d2  jz      short loc_18008A4EF
0x18008a4d4  cmp     [rcx+19h], r15b
0x18008a4d8  jb      short loc_18008A4EF
0x18008a4da  mov     rcx, [rcx+10h]
0x18008a4de  lea     r8, WPP_9a262fb51b93373699b13bc917fc3706_Traceguids
0x18008a4e5  mov     edx, 0DDh
0x18008a4ea  call    WPP_SF_
0x18008a4ef  mov     rcx, [rsi+190h]; hEvent
0x18008a4f6  call    cs:__imp_ResetEvent
0x18008a4fc  mov     rcx, [rsi+198h]; hEvent
0x18008a503  call    cs:__imp_ResetEvent
0x18008a509  mov     rcx, r14; pwk
0x18008a50c  call    cs:__imp_SubmitThreadpoolWork
0x18008a512  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a519  cmp     rcx, r13
0x18008a51c  jz      short loc_18008A53F
0x18008a51e  test    byte ptr [rcx+1Ch], 8
0x18008a522  jz      short loc_18008A53F
0x18008a524  cmp     [rcx+19h], r15b
  ... truncated ...
```
