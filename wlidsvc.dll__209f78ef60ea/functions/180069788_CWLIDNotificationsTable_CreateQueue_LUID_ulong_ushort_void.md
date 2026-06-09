# CWLIDNotificationsTable::CreateQueue(_LUID &,ulong,ushort * *,void * *)

- ea: `0x180069788`
- end: `0x180069b95`
- name: `?CreateQueue@CWLIDNotificationsTable@@QEAAJAEAU_LUID@@KPEAPEAGPEAPEAX@Z`
- size: `1037`
- prototype: `__int64 __fastcall(CWLIDNotificationsTable *__hidden this, struct _LUID *, unsigned int, unsigned __int16 **, void **)`
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b5634`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x18001426c`
- `0x1800151c4`
- `0x180015860`
- `0x180018f80`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180030120`
- `0x1800371c0`
- `0x18003b1e0`
- `0x18003c5c8`
- `0x18003c814`
- `0x180041890`
- `0x1800423f0`
- `0x180069788`
- `0x18007bedc`
- `0x1800a3b60`
- `0x1800a716c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180069b0e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180069b0e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800698d6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800698d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069b05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069b05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006994f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006994f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180069941`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180069941`
- `RPCRT4!UuidCreate` at `0x180069864`
- `RPCRT4!UuidCreate` at `0x180069864`

## string_xrefs

- `0x1800697e6`: `CWLIDNotificationsTable::CreateQueue`
- `0x180069976`: `CWLIDNotificationsTable::CreateQueue`
- `0x180069adc`: `CWLIDNotificationsTable::CreateQueue`
- `0x18006980c`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\wlidnotifications.cpp`
- `0x180069924`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\wlidnotifications.cpp`
- `0x180069ae3`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\wlidnotifications.cpp`
- `0x180069874`: `UuidCreate(&guid) == RPC_S_OK`
- `0x18006990c`: `hr = StringCchCopy(pszEventName, strEventName.GetLength() + 1, CStringW::PCXSTR(strEventName))`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CWLIDNotificationsTable::CreateQueue(
        CWLIDNotificationsTable *this,
        struct _LUID *a2,
        int a3,
        unsigned __int16 **a4,
        void **a5)
{
  int v7; // esi
  int v8; // r9d
  const char *v9; // rax
  unsigned int v10; // r8d
  __int64 v11; // rax
  unsigned __int16 *v12; // rbx
  unsigned __int16 *v13; // r14
  signed int LastError; // eax
  const char *v15; // rcx
  unsigned int v16; // r8d
  HANDLE EventW; // rdi
  _DWORD *v18; // rax
  _DWORD *v19; // rbx
  int v20; // eax
  __int64 v21; // r11
  _QWORD *v22; // rax
  _QWORD *v23; // rdi
  unsigned int v24; // ebx
  char *v26; // [rsp+20h] [rbp-91h]
  int v27; // [rsp+30h] [rbp-81h] BYREF
  _DWORD *v28; // [rsp+38h] [rbp-79h] BYREF
  _DWORD *v29; // [rsp+40h] [rbp-71h] BYREF
  BYTE pbBuffer[8]; // [rsp+48h] [rbp-69h] BYREF
  unsigned __int16 *v31; // [rsp+50h] [rbp-61h] BYREF
  int v32; // [rsp+58h] [rbp-59h] BYREF
  __int64 v33; // [rsp+60h] [rbp-51h] BYREF
  struct _LUID *v34; // [rsp+68h] [rbp-49h]
  __int64 *v35; // [rsp+70h] [rbp-41h] BYREF
  char v36; // [rsp+78h] [rbp-39h]
  _QWORD v37[4]; // [rsp+80h] [rbp-31h] BYREF
  _BYTE v38[8]; // [rsp+A0h] [rbp-11h] BYREF
  UUID Uuid; // [rsp+A8h] [rbp-9h] BYREF

  v34 = a2;
  v7 = 0;
  v27 = 0;
  *(_QWORD *)pbBuffer = 0;
  v28 = 0;
  Uuid = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v33);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v31);
  v37[0] = "CWLIDNotificationsTable::CreateQueue";
  v37[1] = &v27;
  v37[2] = 0;
  v37[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\wlidnotifications.cpp",
    "CWLIDNotificationsTable::CreateQueue",
    (const char *)0x47,
    0,
    (const unsigned __int16 *)v26);
  v35 = g_NotificationTable;
  v36 = 0;
  if ( !a5 )
  {
    v8 = -2147467261;
    v9 = "pHandle != nullptr";
    v10 = 75;
LABEL_36:
    v27 = v8;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\wlidnotifications.cpp",
      "CWLIDNotificationsTable::CreateQueue",
      v10,
      v8,
      v9);
    goto LABEL_37;
  }
  if ( !a3 || !a4 )
  {
    v8 = -2147024809;
    v9 = "dwTypes != 0 && ppszEventName != nullptr";
    v10 = 76;
    goto LABEL_36;
  }
  *a5 = 0;
  *a4 = 0;
  if ( UuidCreate(&Uuid) )
  {
    v8 = -2147418113;
    v9 = "UuidCreate(&guid) == RPC_S_OK";
    v10 = 81;
    goto LABEL_36;
  }
  v11 = GuidToString(&v29, &Uuid);
  ATL::CSimpleStringT<unsigned short,0>::operator=(&v33, v11);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v29);
  ATL::CSimpleStringT<unsigned short,0>::SetString(&v31, L"Global\\");
  ATL::CSimpleStringT<unsigned short,0>::Append(&v31, &v33);
  v12 = v31;
  v13 = (unsigned __int16 *)malloc(2LL * (*((_DWORD *)v31 - 4) + 1));
  if ( v13 )
  {
    LastError = StringCchCopyW(v13, *((_DWORD *)v12 - 4) + 1, v12);
    v27 = LastError;
    if ( LastError >= 0 )
    {
      EventW = CreateEventW(0, 1, 0, v13);
      if ( EventW )
        goto LABEL_17;
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v27 = LastError;
      if ( LastError >= 0 )
      {
LABEL_17:
        v18 = operator new(0x48u, (const struct std::nothrow_t *)std::nothrow);
        v19 = v18;
        v29 = v18;
        if ( v18 )
        {
          v18[2] = 0;
          *((_QWORD *)v18 + 2) = 0;
          *((_QWORD *)v18 + 3) = 0;
          *((_QWORD *)v18 + 4) = 0;
          *((_QWORD *)v18 + 5) = 0;
          *((_QWORD *)v18 + 6) = 0;
          *((_QWORD *)v18 + 7) = 0;
          v18[16] = 10;
          *(_QWORD *)v18 = 0;
          ++g_dwNQueue;
          v28 = v18;
          CComCritSecLockWTry<CComAutoCriticalSectionWTry>::Lock(&v35);
          while ( 1 )
          {
            v20 = CCryptRandom::GenRandom((LPCRITICAL_SECTION)g_cryptRandom, pbBuffer, 8u);
            v27 = v20;
            if ( v20 < 0 )
              break;
            LODWORD(v29) = 0;
            v32 = 0;
            if ( !ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDNotificationQueue>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDNotificationQueue>>::GetNode(
                    (unsigned int)&qword_1801C4008,
                    *(_DWORD *)pbBuffer,
                    (unsigned int)&v29,
                    (unsigned int)&v32,
                    (__int64)v38)
              && v21 )
            {
              *(struct _LUID *)v19 = *v34;
              v19[2] = a3;
              *((_QWORD *)v19 + 2) = EventW;
              v22 = (_QWORD *)ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDNotificationQueue>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDNotificationQueue>>::operator[](
                                &qword_1801C4008,
                                *(_QWORD *)pbBuffer);
              v23 = v22;
              if ( (_DWORD *)*v22 == v19 )
              {
                if ( v22 != &v28 )
LABEL_28:
                  v28 = 0;
                *a4 = v13;
                *a5 = *(void **)pbBuffer;
                goto LABEL_37;
              }
              ATL::CAutoPtr<CWLIDNotificationQueue>::Free(v22);
              *v23 = v19;
              goto LABEL_28;
            }
            if ( (unsigned int)++v7 >= 0x400 )
            {
              v27 = -2147418113;
              Telemetry::IfFailExit(
                "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\wlidnotifications.cpp",
                "CWLIDNotificationsTable::CreateQueue",
                0x6Au,
                -2147418113,
                "dwRetries < PPCRL_MAX_HANDLE_RETRIES");
              goto LABEL_32;
            }
          }
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\wlidnotifications.cpp",
            "CWLIDNotificationsTable::CreateQueue",
            0x66u,
            v20,
            "hr = GenRandomNumber(reinterpret_cast<LPBYTE>(&handle), sizeof(handle))");
        }
        else
        {
          v28 = 0;
          v27 = -2147024882;
        }
LABEL_32:
        if ( EventW )
          CloseHandle(EventW);
        goto LABEL_34;
      }
      v15 = "hr = HRESULT_FROM_WIN32(GetLastError())";
      v16 = 93;
    }
    else
    {
      v15 = "hr = StringCchCopy(pszEventName, strEventName.GetLength() + 1, CStringW::PCXSTR(strEventName))";
      v16 = 91;
    }
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\wlidnotifications.cpp",
      "CWLIDNotificationsTable::CreateQueue",
      v16,
      LastError,
      v15);
LABEL_34:
    free(v13);
    goto LABEL_37;
  }
  v27 = -2147024882;
LABEL_37:
  v24 = v27;
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v35);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v37);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v31);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v33);
  ATL::CAutoPtr<CWLIDNotificationQueue>::Free(&v28);
  return v24;
}

```

## disassembly

```asm
0x180069788  push    rbp
0x18006978a  push    rbx
0x18006978b  push    rsi
0x18006978c  push    rdi
0x18006978d  push    r12
0x18006978f  push    r13
0x180069791  push    r14
0x180069793  push    r15
0x180069795  lea     rbp, [rsp-17h]
0x18006979a  sub     rsp, 0C8h
0x1800697a1  mov     rax, cs:__security_cookie
0x1800697a8  xor     rax, rsp
0x1800697ab  mov     [rbp+4Fh+var_48], rax
0x1800697af  mov     r15, r9
0x1800697b2  mov     r13d, r8d
0x1800697b5  mov     [rbp+4Fh+var_98], rdx
0x1800697b9  mov     r12, [rbp+4Fh+arg_20]
0x1800697bd  xor     esi, esi
0x1800697bf  mov     [rsp+100h+var_D0], esi
0x1800697c3  mov     qword ptr [rbp+4Fh+pbBuffer], rsi
0x1800697c7  mov     [rbp+4Fh+var_C8], rsi
0x1800697cb  xorps   xmm0, xmm0
0x1800697ce  movups  xmmword ptr [rbp+4Fh+Uuid.Data1], xmm0
0x1800697d2  lea     rcx, [rbp+4Fh+var_A0]
0x1800697d6  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800697db  nop
0x1800697dc  lea     rcx, [rbp+4Fh+var_B0]
0x1800697e0  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800697e5  nop
0x1800697e6  lea     rdi, aCwlidnotificat_1; "CWLIDNotificationsTable::CreateQueue"
0x1800697ed  mov     [rbp+4Fh+var_80], rdi
0x1800697f1  lea     rax, [rsp+100h+var_D0]
0x1800697f6  mov     [rbp+4Fh+var_78], rax
0x1800697fa  mov     [rbp+4Fh+var_70], rsi
0x1800697fe  mov     [rbp+4Fh+var_68], rsi
0x180069802  xor     r9d, r9d; unsigned int
0x180069805  lea     r8d, [rsi+47h]; char *
0x180069809  mov     rdx, rdi; char *
0x18006980c  lea     rbx, aOnecoreuapDsEx_46; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180069813  mov     rcx, rbx; this
0x180069816  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18006981b  nop
0x18006981c  lea     rax, ?g_NotificationTable@@3VCWLIDNotificationsTable@@A; CWLIDNotificationsTable g_NotificationTable
0x180069823  mov     [rbp+4Fh+var_90], rax
0x180069827  mov     [rbp+4Fh+var_88], sil
0x18006982b  test    r12, r12
0x18006982e  jnz     short loc_180069847
0x180069830  mov     r9d, 80004003h
0x180069836  lea     rax, aPhandleNullptr_0; "pHandle != nullptr"
0x18006983d  lea     r8d, [r12+4Bh]
0x180069842  jmp     loc_180069B29
0x180069847  test    r13d, r13d
0x18006984a  jz      loc_180069B16
0x180069850  test    r15, r15
0x180069853  jz      loc_180069B16
0x180069859  mov     [r12], rsi
0x18006985d  mov     [r15], rsi
0x180069860  lea     rcx, [rbp+4Fh+Uuid]; Uuid
0x180069864  call    cs:__imp_UuidCreate
0x18006986a  test    eax, eax
0x18006986c  jz      short loc_180069886
0x18006986e  mov     r9d, 8000FFFFh
0x180069874  lea     rax, aUuidcreateGuid; "UuidCreate(&guid) == RPC_S_OK"
0x18006987b  mov     r8d, 51h ; 'Q'
0x180069881  jmp     loc_180069B29
0x180069886  lea     rdx, [rbp+4Fh+Uuid]
0x18006988a  lea     rcx, [rbp+4Fh+var_C0]
0x18006988e  call    ?GuidToString@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBU_GUID@@@Z; GuidToString(_GUID const &)
0x180069893  nop
0x180069894  mov     rdx, rax
0x180069897  lea     rcx, [rbp+4Fh+var_A0]
0x18006989b  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1800698a0  nop
0x1800698a1  lea     rcx, [rbp+4Fh+var_C0]
0x1800698a5  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800698aa  lea     rdx, aGlobal; "Global\\"
0x1800698b1  lea     rcx, [rbp+4Fh+var_B0]
0x1800698b5  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800698ba  lea     rdx, [rbp+4Fh+var_A0]
0x1800698be  lea     rcx, [rbp+4Fh+var_B0]
0x1800698c2  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<ushort,0>::Append(ATL::CSimpleStringT<ushort,0> const &)
0x1800698c7  mov     rbx, [rbp+4Fh+var_B0]
0x1800698cb  mov     eax, [rbx-10h]
0x1800698ce  inc     eax
0x1800698d0  movsxd  rcx, eax
0x1800698d3  add     rcx, rcx; Size
0x1800698d6  call    cs:__imp_malloc
0x1800698dc  mov     r14, rax
0x1800698df  test    rax, rax
0x1800698e2  jnz     short loc_1800698F1
0x1800698e4  mov     [rsp+100h+var_D0], 8007000Eh
0x1800698ec  jmp     loc_180069B3E
0x1800698f1  mov     eax, [rbx-10h]
0x1800698f4  inc     eax
0x1800698f6  movsxd  rdx, eax; unsigned __int64
0x1800698f9  mov     r8, rbx; unsigned __int16 *
0x1800698fc  mov     rcx, r14; unsigned __int16 *
0x1800698ff  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180069904  mov     [rsp+100h+var_D0], eax
0x180069908  test    eax, eax
0x18006990a  jns     short loc_180069935
0x18006990c  lea     rcx, aHrStringcchcop_20; "hr = StringCchCopy(pszEventName, strEve"...
0x180069913  mov     r8d, 5Bh ; '['; unsigned int
0x180069919  mov     rdx, rdi; char *
0x18006991c  mov     r9d, eax; int
0x18006991f  mov     [rsp+100h+var_E0], rcx; char *
0x180069924  lea     rcx, aOnecoreuapDsEx_46; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18006992b  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180069930  jmp     loc_180069B0B
0x180069935  mov     r9, r14; lpName
0x180069938  xor     r8d, r8d; bInitialState
0x18006993b  lea     edx, [r8+1]; bManualReset
0x18006993f  xor     ecx, ecx; lpEventAttributes
0x180069941  call    cs:__imp_CreateEventW
0x180069947  mov     rdi, rax
0x18006994a  test    rax, rax
0x18006994d  jnz     short loc_18006997F
0x18006994f  call    cs:__imp_GetLastError
0x180069955  test    eax, eax
0x180069957  jle     short loc_180069961
0x180069959  movzx   eax, ax
0x18006995c  or      eax, 80070000h
0x180069961  mov     [rsp+100h+var_D0], eax
0x180069965  test    eax, eax
0x180069967  jns     short loc_18006997F
0x180069969  lea     rcx, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x180069970  mov     r8d, 5Dh ; ']'
0x180069976  lea     rdx, aCwlidnotificat_1; "CWLIDNotificationsTable::CreateQueue"
0x18006997d  jmp     short loc_18006991C
0x18006997f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180069986  mov     ecx, 48h ; 'H'; unsigned __int64
0x18006998b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180069990  mov     rbx, rax
0x180069993  mov     [rbp+4Fh+var_C0], rax
0x180069997  test    rax, rax
0x18006999a  jz      loc_180069AF1
0x1800699a0  mov     [rax+8], esi
0x1800699a3  mov     [rax+10h], rsi
0x1800699a7  mov     [rax+18h], rsi
0x1800699ab  mov     [rax+20h], rsi
0x1800699af  mov     [rax+28h], rsi
0x1800699b3  mov     [rax+30h], rsi
0x1800699b7  mov     [rax+38h], rsi
0x1800699bb  mov     dword ptr [rax+40h], 0Ah
0x1800699c2  xor     eax, eax
0x1800699c4  mov     [rbx], rax
0x1800699c7  inc     cs:?g_dwNQueue@@3KA; ulong g_dwNQueue
0x1800699cd  mov     [rbp+4Fh+var_C8], rbx
0x1800699d1  test    rbx, rbx
0x1800699d4  jz      loc_180069AF5
0x1800699da  lea     rcx, [rbp+4Fh+var_90]
0x1800699de  call    ?Lock@?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAAJXZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::Lock(void)
0x1800699e3  mov     r8d, 8; dwLen
0x1800699e9  lea     rdx, [rbp+4Fh+pbBuffer]; pbBuffer
0x1800699ed  lea     rcx, ?g_cryptRandom@@3VCCryptRandom@@A; lpCriticalSection
0x1800699f4  call    ?GenRandom@CCryptRandom@@QEAAJPEAEK@Z; CCryptRandom::GenRandom(uchar *,ulong)
0x1800699f9  mov     [rsp+100h+var_D0], eax
0x1800699fd  test    eax, eax
0x1800699ff  js      loc_180069AC7
0x180069a05  mov     dword ptr [rbp+4Fh+var_C0], 0
0x180069a0c  mov     [rbp+4Fh+var_A8], 0
0x180069a13  lea     rax, [rbp+4Fh+var_60]
0x180069a17  mov     [rsp+100h+var_E0], rax
0x180069a1c  lea     r9, [rbp+4Fh+var_A8]
0x180069a20  lea     r8, [rbp+4Fh+var_C0]
0x180069a24  mov     r11, qword ptr [rbp+4Fh+pbBuffer]
0x180069a28  mov     rdx, r11
0x180069a2b  lea     rcx, qword_1801C4008
0x180069a32  call    ?GetNode@?$CAtlMap@PEAXV?$CAutoPtr@VCWLIDNotificationQueue@@@ATL@@V?$CElementTraits@PEAX@2@V?$CAutoPtrElementTraits@VCWLIDNotificationQueue@@@2@@ATL@@AEBAPEAVCNode@12@PEAXAEAI1AEAPEAV312@@Z; ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDNotificationQueue>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDNotificationQueue>>::GetNode(void *,uint &,uint &,ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDNotificationQueue>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDNotificationQueue>>::CNode * &)
0x180069a37  test    rax, rax
0x180069a3a  jnz     short loc_180069A41
0x180069a3c  test    r11, r11
0x180069a3f  jnz     short loc_180069A6A
0x180069a41  inc     esi
0x180069a43  cmp     esi, 400h
0x180069a49  jb      short loc_1800699E3
0x180069a4b  mov     r9d, 8000FFFFh
0x180069a51  mov     [rsp+100h+var_D0], r9d
0x180069a56  lea     rax, aDwretriesPpcrl; "dwRetries < PPCRL_MAX_HANDLE_RETRIES"
0x180069a5d  mov     [rsp+100h+var_E0], rax
0x180069a62  mov     r8d, 6Ah ; 'j'
0x180069a68  jmp     short loc_180069ADC
0x180069a6a  cmp     esi, 400h
0x180069a70  jnb     short loc_180069A4B
0x180069a72  mov     rax, [rbp+4Fh+var_98]
0x180069a76  mov     rax, [rax]
0x180069a79  mov     [rbx], rax
0x180069a7c  mov     [rbx+8], r13d
0x180069a80  mov     [rbx+10h], rdi
0x180069a84  mov     rdx, qword ptr [rbp+4Fh+pbBuffer]
0x180069a88  lea     rcx, qword_1801C4008
0x180069a8f  call    ??A?$CAtlMap@PEAXV?$CAutoPtr@VCWLIDNotificationQueue@@@ATL@@V?$CElementTraits@PEAX@2@V?$CAutoPtrElementTraits@VCWLIDNotificationQueue@@@2@@ATL@@QEAAAEAV?$CAutoPtr@VCWLIDNotificationQueue@@@1@PEAX@Z; ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDNotificationQueue>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDNotificationQueue>>::operator[](void *)
0x180069a94  mov     rdi, rax
0x180069a97  cmp     [rax], rbx
0x180069a9a  jnz     short loc_180069AA7
0x180069a9c  lea     rax, [rbp+4Fh+var_C8]
0x180069aa0  cmp     rdi, rax
0x180069aa3  jz      short loc_180069ABA
0x180069aa5  jmp     short loc_180069AB2
0x180069aa7  mov     rcx, rdi
0x180069aaa  call    ?Free@?$CAutoPtr@VCWLIDNotificationQueue@@@ATL@@QEAAXXZ; ATL::CAutoPtr<CWLIDNotificationQueue>::Free(void)
0x180069aaf  mov     [rdi], rbx
0x180069ab2  mov     [rbp+4Fh+var_C8], 0
0x180069aba  mov     [r15], r14
0x180069abd  mov     rax, qword ptr [rbp+4Fh+pbBuffer]
0x180069ac1  mov     [r12], rax
0x180069ac5  jmp     short loc_180069B3E
0x180069ac7  lea     rcx, aHrGenrandomnum_0; "hr = GenRandomNumber(reinterpret_cast<L"...
0x180069ace  mov     [rsp+100h+var_E0], rcx; char *
0x180069ad3  mov     r9d, eax; int
0x180069ad6  mov     r8d, 66h ; 'f'; unsigned int
0x180069adc  lea     rdx, aCwlidnotificat_1; "CWLIDNotificationsTable::CreateQueue"
0x180069ae3  lea     rcx, aOnecoreuapDsEx_46; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180069aea  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180069aef  jmp     short loc_180069AFD
0x180069af1  mov     [rbp+4Fh+var_C8], rsi
0x180069af5  mov     [rsp+100h+var_D0], 8007000Eh
0x180069afd  test    rdi, rdi
0x180069b00  jz      short loc_180069B0B
0x180069b02  mov     rcx, rdi; hObject
0x180069b05  call    cs:__imp_CloseHandle
0x180069b0b  mov     rcx, r14; Block
0x180069b0e  call    cs:__imp_free
0x180069b14  jmp     short loc_180069B3E
0x180069b16  mov     r9d, 80070057h; int
0x180069b1c  lea     rax, aDwtypes0Ppszev; "dwTypes != 0 && ppszEventName != nullpt"...
0x180069b23  mov     r8d, 4Ch ; 'L'; unsigned int
0x180069b29  mov     [rsp+100h+var_E0], rax; char *
0x180069b2e  mov     [rsp+100h+var_D0], r9d
0x180069b33  mov     rdx, rdi; char *
0x180069b36  mov     rcx, rbx; char *
0x180069b39  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180069b3e  mov     ebx, [rsp+100h+var_D0]
0x180069b42  lea     rcx, [rbp+4Fh+var_90]
0x180069b46  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x180069b4b  nop
0x180069b4c  lea     rcx, [rbp+4Fh+var_80]
0x180069b50  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180069b55  nop
0x180069b56  lea     rcx, [rbp+4Fh+var_B0]
0x180069b5a  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180069b5f  nop
0x180069b60  lea     rcx, [rbp+4Fh+var_A0]
0x180069b64  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180069b69  nop
0x180069b6a  lea     rcx, [rbp+4Fh+var_C8]
0x180069b6e  call    ?Free@?$CAutoPtr@VCWLIDNotificationQueue@@@ATL@@QEAAXXZ; ATL::CAutoPtr<CWLIDNotificationQueue>::Free(void)
0x180069b73  mov     eax, ebx
0x180069b75  mov     rcx, [rbp+4Fh+var_48]
0x180069b79  xor     rcx, rsp; StackCookie
0x180069b7c  call    __security_check_cookie
0x180069b81  add     rsp, 0C8h
0x180069b88  pop     r15
0x180069b8a  pop     r14
0x180069b8c  pop     r13
0x180069b8e  pop     r12
0x180069b90  pop     rdi
0x180069b91  pop     rsi
0x180069b92  pop     rbx
0x180069b93  pop     rbp
0x180069b94  retn
```
