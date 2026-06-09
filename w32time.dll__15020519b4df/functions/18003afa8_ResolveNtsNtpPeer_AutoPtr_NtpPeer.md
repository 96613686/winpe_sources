# ResolveNtsNtpPeer(AutoPtr<NtpPeer>)

- ea: `0x18003afa8`
- end: `0x18003b8da`
- name: `?ResolveNtsNtpPeer@@YAJV?$AutoPtr@UNtpPeer@@@@@Z`
- size: `2354`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180017e88`

## callees

- `0x18000a7e0`
- `0x180014054`
- `0x1800144ac`
- `0x1800144f0`
- `0x1800164b0`
- `0x180018138`
- `0x180018180`
- `0x180019828`
- `0x18001a714`
- `0x18001a780`
- `0x18001d9a0`
- `0x18002dd98`
- `0x18003afa8`
- `0x18003b8e0`
- `0x18003b8fc`
- `0x18003d270`
- `0x18003dd2c`
- `0x180041348`
- `0x180041384`
- `0x180054690`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18003b025`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18003b866`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18003b025`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18003b866`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b7ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b89b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b7ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b89b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b145`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b887`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b145`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b887`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b04f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b208`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b04f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b208`
- `ntdll!RtlInitUnicodeString` at `0x18003b3d2`
- `ntdll!RtlInitUnicodeString` at `0x18003b40a`
- `ntdll!RtlInitUnicodeString` at `0x18003b52d`
- `ntdll!RtlInitUnicodeString` at `0x18003b713`
- `ntdll!RtlInitUnicodeString` at `0x18003b3d2`
- `ntdll!RtlInitUnicodeString` at `0x18003b40a`
- `ntdll!RtlInitUnicodeString` at `0x18003b52d`
- `ntdll!RtlInitUnicodeString` at `0x18003b713`

## string_xrefs

- `0x18003afef`: `Failing as we are attempting to call ResolveNtsNtpPeer when nts feature is not enabled.\n`
- `0x18003b094`: `Attempted to resolve a NTS peer with a NULL wszManualConfigID.  This could indicate that the time service is in an inconsistent state.  The peer will be discarded, and the time service will attempt to proceed.\n`
- `0x18003b469`: `Logging warning: NtsNtpClient was unable to set a NTS peer to use as a time source because the NTS server is not ready. NtsNtpClient will check the NtsState again in %s minutes.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall ResolveNtsNtpPeer(volatile signed __int32 **a1)
{
  WCHAR *v3; // r12
  char *v4; // r14
  __int64 v5; // rcx
  const WCHAR *v6; // r13
  const WCHAR *v7; // rbx
  unsigned __int8 v8; // bl
  signed int NtsServerCurrentInfo; // r15d
  int v10; // r14d
  __int64 v11; // r14
  _NtpProvState *v12; // r8
  unsigned int v13; // ecx
  __int64 v14; // rdx
  unsigned __int64 v15; // rbx
  volatile signed __int32 **v16; // rax
  __int64 v17; // rcx
  int SystemErrorString; // r15d
  unsigned int v19; // ebx
  PCWSTR v20; // r15
  volatile signed __int32 **v21; // rax
  volatile signed __int32 *v22; // r14
  volatile signed __int32 *v23; // rbx
  int v24; // eax
  PCWSTR SourceString; // [rsp+78h] [rbp-230h] BYREF
  int v26; // [rsp+80h] [rbp-228h]
  unsigned int v27; // [rsp+84h] [rbp-224h] BYREF
  int v28; // [rsp+88h] [rbp-220h]
  unsigned int v29; // [rsp+8Ch] [rbp-21Ch]
  signed int active; // [rsp+90h] [rbp-218h]
  volatile signed __int32 *v31; // [rsp+98h] [rbp-210h] BYREF
  unsigned int v32; // [rsp+A0h] [rbp-208h] BYREF
  WCHAR *v33; // [rsp+A8h] [rbp-200h] BYREF
  volatile signed __int32 **v34; // [rsp+B0h] [rbp-1F8h] BYREF
  unsigned int v35; // [rsp+B8h] [rbp-1F0h]
  volatile signed __int32 **v36; // [rsp+C0h] [rbp-1E8h]
  volatile signed __int32 **v37; // [rsp+C8h] [rbp-1E0h] BYREF
  struct _UNICODE_STRING v38; // [rsp+D0h] [rbp-1D8h] BYREF
  __int64 v39; // [rsp+E0h] [rbp-1C8h]
  volatile signed __int32 *v40; // [rsp+E8h] [rbp-1C0h] BYREF
  __int64 v41; // [rsp+F0h] [rbp-1B8h]
  struct _UNICODE_STRING DestinationString; // [rsp+F8h] [rbp-1B0h] BYREF
  struct _UNICODE_STRING v43; // [rsp+108h] [rbp-1A0h] BYREF
  struct _UNICODE_STRING v44; // [rsp+118h] [rbp-190h] BYREF
  _QWORD v45[4]; // [rsp+160h] [rbp-148h] BYREF
  char v46; // [rsp+180h] [rbp-128h] BYREF
  int v47; // [rsp+181h] [rbp-127h]
  __int16 v48; // [rsp+185h] [rbp-123h]
  char v49; // [rsp+187h] [rbp-121h]
  _BYTE v50[32]; // [rsp+188h] [rbp-120h] BYREF
  sockaddr_storage v51; // [rsp+1A8h] [rbp-100h] BYREF
  int v52; // [rsp+228h] [rbp-80h]
  int v53; // [rsp+22Ch] [rbp-7Ch]
  __int64 v54; // [rsp+230h] [rbp-78h]
  __int64 v55; // [rsp+238h] [rbp-70h]
  _BYTE v56[32]; // [rsp+240h] [rbp-68h] BYREF

  v36 = a1;
  if ( !*((_BYTE *)g_pnpstate + 50) )
  {
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(L"Failing as we are attempting to call ResolveNtsNtpPeer when nts feature is not enabled.\n");
    AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(a1);
    return 2147500033LL;
  }
  v3 = 0;
  v33 = 0;
  v41 = _set_se_translator(SeTransFunc);
  v29 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
  v31 = (volatile signed __int32 *)g_pnpstate;
  v4 = (char *)g_pnpstate + 432;
  v5 = *((_QWORD *)*a1 + 1);
  v6 = *(const WCHAR **)(v5 + 72);
  if ( !v6 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(5) )
      FileLogAdd(
        L"Attempted to resolve a NTS peer with a NULL wszManualConfigID.  This could indicate that the time service is in "
         "an inconsistent state.  The peer will be discarded, and the time service will attempt to proceed.\n");
    v31 = (volatile signed __int32 *)*((_QWORD *)v4 + 1);
    v7 = (const WCHAR *)v31;
    v31 = *(volatile signed __int32 **)v4;
    std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,AutoPtr<NtpPeer>>(
      &SourceString,
      v31,
      v7,
      a1);
    v34 = (volatile signed __int32 **)v7;
    if ( v7 != SourceString )
      std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::erase(v4, &v34);
    AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(a1);
    return 0;
  }
  SourceString = (PCWSTR)((char *)g_pnpstate + 408);
  v8 = 0;
  if ( *(_DWORD *)(v5 + 112) == 2 )
  {
    v8 = 1;
    *(_DWORD *)(v5 + 112) = 0;
  }
  if ( (unsigned __int8)FileLogAllowEntry(50) )
    FileLogAdd(L"Resolving Nts peer: %s\n ForceResync: %d", v6, v8);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  std::wstring::wstring(v50);
  memset_0(&v51, 0, sizeof(v51));
  v52 = 123;
  v53 = 0xFFFF;
  v54 = 0;
  v55 = 0;
  std::wstring::wstring(v45, v6);
  NtsServerCurrentInfo = GetNtsServerCurrentInfo(v45, (__int64)&v46, v8);
  active = NtsServerCurrentInfo;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
  v10 = 0;
  v26 = 0;
  if ( NtsServerCurrentInfo < 0 )
  {
    if ( NtsServerCurrentInfo == -2147483638 )
    {
      v10 = 6;
LABEL_18:
      v26 = v10;
      v27 = 16;
      goto LABEL_19;
    }
    if ( NtsServerCurrentInfo == -2147013895 )
    {
      v10 = 3;
      goto LABEL_18;
    }
    v10 = 5;
    v26 = 5;
  }
  v27 = 16;
  if ( NtsServerCurrentInfo >= 0 )
  {
    NtsServerCurrentInfo = CheckDuplicatePeers(
                             (_DWORD)SourceString,
                             (unsigned int)&v51,
                             (unsigned int)&v27,
                             1,
                             (__int64)&v33);
    active = NtsServerCurrentInfo;
    if ( NtsServerCurrentInfo < 0 )
      v10 = 4;
    v26 = v10;
    v3 = v33;
  }
LABEL_19:
  v32 = 0;
  v39 = 0;
  if ( NtsServerCurrentInfo >= 0 )
  {
    v11 = (__int64)(*((_QWORD *)SourceString + 1) - *(_QWORD *)SourceString) >> 3;
    v39 = v11;
    NtsServerCurrentInfo = CreateNewActivePeers(&v51, &v27, 1u, &v32);
    active = NtsServerCurrentInfo;
    if ( NtsServerCurrentInfo >= 0 )
    {
      if ( *(_BYTE *)(*((_QWORD *)*a1 + 1) + 1544LL) )
      {
        v43 = 0;
        RtlInitUnicodeString(&v43, v6);
        if ( (unsigned __int8)FileLogAllowEntry(4) )
          FileLogAdd(L"Logging warning: NtsNtpClient succeeds in resolving NTS peer %s after a previous failure.\n", v6);
        LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_MANUAL_PEER_SUCCESS_ERROR, L"u", &v43);
      }
      v19 = 0;
      v35 = 0;
      v20 = SourceString;
      while ( v19 < v32 )
      {
        AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(
          (volatile signed __int32 **)&SourceString,
          (volatile signed __int32 **)(*(_QWORD *)v20 + 8 * (v11 + v19)));
        v34 = &v40;
        v21 = AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(&v40, (volatile signed __int32 **)&SourceString);
        active = MyFillInActivePeersDetail(v21, 4, 3, L"NtsNtp", v6, 0);
        AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>((volatile signed __int32 **)&SourceString);
        v35 = ++v19;
      }
      v22 = v31;
      v34 = (volatile signed __int32 **)*((_QWORD *)v31 + 55);
      v23 = (volatile signed __int32 *)v34;
      v34 = (volatile signed __int32 **)*((_QWORD *)v31 + 54);
      std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,AutoPtr<NtpPeer>>(
        &v31,
        v34,
        v23,
        a1);
      v37 = (volatile signed __int32 **)v23;
      if ( v23 != v31 )
        std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::erase(v22 + 108, &v37);
      goto LABEL_63;
    }
    v10 = 5;
    v26 = 5;
  }
  *(_DWORD *)(*((_QWORD *)*a1 + 1) + 1528LL) = NtsServerCurrentInfo;
  *(_DWORD *)(*((_QWORD *)*a1 + 1) + 1532LL) = 112;
  ++*(_DWORD *)(*((_QWORD *)*a1 + 1) + 52LL);
  v12 = g_pnpstate;
  v13 = *((_DWORD *)g_pnpstate + 45);
  v14 = *((_QWORD *)*a1 + 1);
  if ( *(_DWORD *)(v14 + 52) > v13 )
    *(_DWORD *)(v14 + 52) = v13;
  v15 = 600000000LL * *((unsigned int *)v12 + 44);
  v37 = &v31;
  v16 = AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(&v31, a1);
  SetPeerTimeRemaining(v16, v15);
  if ( (unsigned __int8)FileLogAllowEntry(5) )
    FileLogAdd(L"Checking NTS KE results for %s in %u minutes.\n", v6, (unsigned int)(v15 / 0x23C34600));
  v17 = *((_QWORD *)*a1 + 1);
  if ( !*(_BYTE *)(v17 + 1544) || *(_DWORD *)(v17 + 1548) != v10 )
  {
    v28 = 0;
    SourceString = 0;
    v38 = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, v6);
    SystemErrorString = GetSystemErrorString(NtsServerCurrentInfo, (unsigned __int16 **)&SourceString);
    v28 = SystemErrorString;
    if ( SystemErrorString >= 0 )
    {
      RtlInitUnicodeString(&v38, SourceString);
      switch ( v10 )
      {
        case 3:
          if ( (unsigned __int8)FileLogAllowEntry(5) )
            FileLogAdd(
              L"Logging warning: NtpClient was unable to set a NTS peer to use as a time source because of DNS resolution "
               "error on '%s'. NtpClient will check the NtsState again in %s minutes. The error was: %s\n",
              v6,
              v56,
              SourceString);
          v24 = LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_MANUAL_PEER_DNS_ERROR, L"udu", &v38);
          break;
        case 4:
          v44 = 0;
          RtlInitUnicodeString(&v44, v3);
          if ( (unsigned __int8)FileLogAllowEntry(5) )
            FileLogAdd(
              L"Logging warning: NtpClient was unable to set a NTS peer to use as a time source because of duplicate error"
               " on '%s'. The same time source '%s' has been either specified as manual peer in NtpServer or selected as "
               "domain peer. NtpClient will check the NtsState again in %s minutes. The error was: %s\n",
              v6,
              v3,
              v56,
              SourceString);
          v24 = LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_MANUAL_PEER_DUPLICATE_ERROR, L"uduu", &v38);
          break;
        case 5:
          if ( (unsigned __int8)FileLogAllowEntry(5) )
            FileLogAdd(
              L"Logging warning: NtsNtpClient was unable to set a NTS peer to use as a time source because of an unexpecte"
               "d error. NtsNtpClient will will check the NtsState again in %s minutes. The error was: %s\n",
              v56,
              SourceString);
          v24 = LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_MANUAL_PEER_UNEXPECTED_ERROR, L"ud", &v38);
          break;
        default:
          if ( v10 == 6 && (unsigned __int8)FileLogAllowEntry(5) )
            FileLogAdd(
              L"Logging warning: NtsNtpClient was unable to set a NTS peer to use as a time source because the NTS server "
               "is not ready. NtsNtpClient will check the NtsState again in %s minutes.\n",
              v56);
          goto LABEL_61;
      }
      SystemErrorString = v24;
      v28 = v24;
LABEL_61:
      LocalFree((HLOCAL)SourceString);
      if ( SystemErrorString >= 0 )
      {
        *(_BYTE *)(*((_QWORD *)*a1 + 1) + 1544LL) = 1;
        *(_DWORD *)(*((_QWORD *)*a1 + 1) + 1548LL) = v10;
      }
    }
  }
LABEL_63:
  std::wstring::~wstring((__int64)v45);
  NtsForNtpInfo::~NtsForNtpInfo((NtsForNtpInfo *)&v46);
  _set_se_translator(v41);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
  if ( v3 )
    LocalFree(v3);
  AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(a1);
  return v29;
}

```

## disassembly

```asm
0x18003afa8  push    rbx
0x18003afaa  push    rsi
0x18003afab  push    r12
0x18003afad  push    r13
0x18003afaf  push    r14
0x18003afb1  push    r15
0x18003afb3  sub     rsp, 278h
0x18003afba  mov     rax, cs:__security_cookie
0x18003afc1  xor     rax, rsp
0x18003afc4  mov     [rsp+2A8h+var_48], rax
0x18003afcc  mov     rsi, rcx
0x18003afcf  mov     [rsp+2A8h+var_1E8], rcx
0x18003afd7  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18003afde  cmp     byte ptr [rax+32h], 0
0x18003afe2  jnz     short loc_18003B00E
0x18003afe4  xor     ecx, ecx
0x18003afe6  call    FileLogAllowEntry
0x18003afeb  test    al, al
0x18003afed  jz      short loc_18003AFFC
0x18003afef  lea     rcx, aFailingAsWeAre_3; "Failing as we are attempting to call Re"...
0x18003aff6  call    FileLogAdd
0x18003affb  nop
0x18003affc  mov     rcx, rsi
0x18003afff  call    ??1?$AutoPtr@UNtpPeer@@@@QEAA@XZ; AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(void)
0x18003b004  mov     eax, 80004001h
0x18003b009  jmp     loc_18003B8B7
0x18003b00e  mov     [rsp+2A8h+var_238], 0
0x18003b013  xor     r12d, r12d
0x18003b016  mov     [rsp+2A8h+var_200], r12
0x18003b01e  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x18003b025  call    cs:__imp__set_se_translator
0x18003b02c  nop     dword ptr [rax+rax+00h]
0x18003b031  mov     [rsp+2A8h+var_1B8], rax
0x18003b039  mov     [rsp+2A8h+var_21C], r12d
0x18003b041  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18003b048  add     rcx, 148h; lpCriticalSection
0x18003b04f  call    cs:__imp_EnterCriticalSection
0x18003b056  nop     dword ptr [rax+rax+00h]
0x18003b05b  mov     [rsp+2A8h+var_238], 1
0x18003b060  mov     rdx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18003b067  mov     [rsp+2A8h+var_210], rdx
0x18003b06f  lea     r14, [rdx+1B0h]
0x18003b076  mov     rax, [rsi]
0x18003b079  mov     rcx, [rax+8]
0x18003b07d  mov     r13, [rcx+48h]
0x18003b081  test    r13, r13
0x18003b084  jnz     short loc_18003B0F9
0x18003b086  lea     ecx, [r12+5]
0x18003b08b  call    FileLogAllowEntry
0x18003b090  test    al, al
0x18003b092  jz      short loc_18003B0A0
0x18003b094  lea     rcx, aAttemptedToRes; "Attempted to resolve a NTS peer with a "...
0x18003b09b  call    FileLogAdd
0x18003b0a0  mov     rbx, [r14+8]
0x18003b0a4  mov     [rsp+2A8h+var_210], rbx
0x18003b0ac  mov     rdx, [r14]
0x18003b0af  mov     [rsp+2A8h+var_210], rdx
0x18003b0b7  mov     r9, rsi
0x18003b0ba  mov     r8, rbx
0x18003b0bd  lea     rcx, [rsp+2A8h+SourceString]
0x18003b0c2  call    ??$find@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$AutoPtr@UNtpPeer@@@@@std@@@std@@@std@@V?$AutoPtr@UNtpPeer@@@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$AutoPtr@UNtpPeer@@@@@std@@@std@@@0@V10@V10@AEBV?$AutoPtr@UNtpPeer@@@@@Z; std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,AutoPtr<NtpPeer>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,AutoPtr<NtpPeer> const &)
0x18003b0c7  mov     [rsp+2A8h+var_1F8], rbx
0x18003b0cf  mov     r8, [rsp+2A8h+SourceString]
0x18003b0d4  cmp     rbx, r8
0x18003b0d7  jz      short loc_18003B0EA
0x18003b0d9  lea     rdx, [rsp+2A8h+var_1F8]
0x18003b0e1  mov     rcx, r14
0x18003b0e4  call    ?erase@?$vector@V?$AutoPtr@UNtpPeer@@@@V?$MyThrowingAllocator@V?$AutoPtr@UNtpPeer@@@@@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$AutoPtr@UNtpPeer@@@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$AutoPtr@UNtpPeer@@@@@std@@@std@@@2@@Z; std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>)
0x18003b0e9  nop
0x18003b0ea  mov     rcx, rsi
0x18003b0ed  call    ??1?$AutoPtr@UNtpPeer@@@@QEAA@XZ; AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(void)
0x18003b0f2  xor     eax, eax
0x18003b0f4  jmp     loc_18003B8B7
0x18003b0f9  lea     rax, [rdx+198h]
0x18003b100  mov     [rsp+2A8h+SourceString], rax
0x18003b105  xor     bl, bl
0x18003b107  cmp     dword ptr [rcx+70h], 2
0x18003b10b  jnz     short loc_18003B116
0x18003b10d  mov     bl, 1
0x18003b10f  mov     dword ptr [rcx+70h], 0
0x18003b116  mov     ecx, 32h ; '2'
0x18003b11b  call    FileLogAllowEntry
0x18003b120  test    al, al
0x18003b122  jz      short loc_18003B137
0x18003b124  movzx   r8d, bl
0x18003b128  mov     rdx, r13
0x18003b12b  lea     rcx, aResolvingNtsPe; "Resolving Nts peer: %s\n ForceResync: %"...
0x18003b132  call    FileLogAdd
0x18003b137  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18003b13e  add     rcx, 148h; lpCriticalSection
0x18003b145  call    cs:__imp_LeaveCriticalSection
0x18003b14c  nop     dword ptr [rax+rax+00h]
0x18003b151  mov     [rsp+2A8h+var_238], 0
0x18003b156  mov     [rsp+2A8h+var_128], 0
0x18003b15e  xor     eax, eax
0x18003b160  mov     [rsp+2A8h+var_127], eax
0x18003b167  mov     [rsp+2A8h+var_123], ax
0x18003b16f  mov     [rsp+2A8h+var_121], al
0x18003b176  lea     rcx, [rsp+2A8h+var_120]
0x18003b17e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003b183  nop
0x18003b184  xor     edx, edx; Val
0x18003b186  mov     r8d, 80h; Size
0x18003b18c  lea     rcx, [rsp+2A8h+var_100]; void *
0x18003b194  call    memset_0
0x18003b199  mov     [rsp+2A8h+var_80], 7Bh ; '{'
0x18003b1a4  mov     [rsp+2A8h+var_7C], 0FFFFh
0x18003b1af  mov     [rsp+2A8h+var_78], 0
0x18003b1bb  mov     [rsp+2A8h+var_70], 0
0x18003b1c7  mov     rdx, r13
0x18003b1ca  lea     rcx, [rsp+2A8h+var_148]
0x18003b1d2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003b1d7  nop
0x18003b1d8  mov     r8b, bl
0x18003b1db  lea     rdx, [rsp+2A8h+var_128]
0x18003b1e3  lea     rcx, [rsp+2A8h+var_148]
0x18003b1eb  call    ?GetNtsServerCurrentInfo@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUNtsForNtpInfo@@_N@Z; GetNtsServerCurrentInfo(std::wstring const &,NtsForNtpInfo &,bool)
0x18003b1f0  mov     r15d, eax
0x18003b1f3  mov     [rsp+2A8h+var_218], eax
0x18003b1fa  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18003b201  add     rcx, 148h; lpCriticalSection
0x18003b208  call    cs:__imp_EnterCriticalSection
0x18003b20f  nop     dword ptr [rax+rax+00h]
0x18003b214  mov     [rsp+2A8h+var_238], 1
0x18003b219  xor     r14d, r14d
0x18003b21c  mov     [rsp+2A8h+var_228], r14d
0x18003b224  test    r15d, r15d
0x18003b227  jns     loc_18003B49C
0x18003b22d  cmp     r15d, 8000000Ah
0x18003b234  jnz     loc_18003B47A
0x18003b23a  mov     r14d, 6
0x18003b240  mov     [rsp+2A8h+var_228], r14d
0x18003b248  mov     [rsp+2A8h+var_224], 10h
0x18003b253  mov     ebx, 4
0x18003b258  mov     [rsp+2A8h+var_208], 0
0x18003b263  mov     [rsp+2A8h+var_1C8], 0
0x18003b26f  test    r15d, r15d
0x18003b272  js      short loc_18003B2CF
0x18003b274  mov     rax, [rsp+2A8h+SourceString]
0x18003b279  mov     r14, [rax+8]
0x18003b27d  sub     r14, [rax]
0x18003b280  sar     r14, 3
0x18003b284  mov     [rsp+2A8h+var_1C8], r14
0x18003b28c  lea     r9, [rsp+2A8h+var_208]; unsigned int *
0x18003b294  mov     r8d, 1; unsigned int
0x18003b29a  lea     rdx, [rsp+2A8h+var_224]; unsigned int *
0x18003b2a2  lea     rcx, [rsp+2A8h+var_100]; struct sockaddr_storage *
0x18003b2aa  call    ?CreateNewActivePeers@@YAJPEAUsockaddr_storage@@PEAII1@Z; CreateNewActivePeers(sockaddr_storage *,uint *,uint,uint *)
0x18003b2af  mov     r15d, eax
0x18003b2b2  mov     [rsp+2A8h+var_218], eax
0x18003b2b9  test    eax, eax
0x18003b2bb  jns     loc_18003B507
0x18003b2c1  mov     r14d, 5
0x18003b2c7  mov     [rsp+2A8h+var_228], r14d
0x18003b2cf  mov     rax, [rsi]
0x18003b2d2  mov     rcx, [rax+8]
0x18003b2d6  mov     [rcx+5F8h], r15d
0x18003b2dd  mov     rax, [rsi]
0x18003b2e0  mov     rcx, [rax+8]
0x18003b2e4  mov     dword ptr [rcx+5FCh], 70h ; 'p'
0x18003b2ee  mov     rax, [rsi]
0x18003b2f1  mov     rcx, [rax+8]
0x18003b2f5  inc     dword ptr [rcx+34h]
0x18003b2f8  mov     r8, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18003b2ff  mov     ecx, [r8+0B4h]
0x18003b306  mov     rax, [rsi]
0x18003b309  mov     rdx, [rax+8]
0x18003b30d  cmp     [rdx+34h], ecx
0x18003b310  jbe     short loc_18003B315
0x18003b312  mov     [rdx+34h], ecx
0x18003b315  mov     eax, [r8+0B0h]
0x18003b31c  imul    rbx, rax, 23C34600h
0x18003b323  lea     rax, [rsp+2A8h+var_210]
0x18003b32b  mov     [rsp+2A8h+var_1E0], rax
0x18003b333  mov     rdx, rsi
0x18003b336  lea     rcx, [rsp+2A8h+var_210]
0x18003b33e  call    ??0?$AutoPtr@UNtpPeer@@@@QEAA@AEBV0@@Z; AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(AutoPtr<NtpPeer> const &)
0x18003b343  nop
0x18003b344  mov     rdx, rbx
0x18003b347  mov     rcx, rax
0x18003b34a  call    ?SetPeerTimeRemaining@@YAXV?$AutoPtr@UNtpPeer@@@@UNtTimePeriod@@@Z; SetPeerTimeRemaining(AutoPtr<NtpPeer>,NtTimePeriod)
0x18003b34f  mov     ecx, 5
0x18003b354  call    FileLogAllowEntry
0x18003b359  test    al, al
0x18003b35b  jz      short loc_18003B380
0x18003b35d  mov     rax, 0E5109EC205D7BEA7h
0x18003b367  mul     rbx
0x18003b36a  shr     rdx, 1Dh
0x18003b36e  mov     r8d, edx
0x18003b371  mov     rdx, r13
0x18003b374  lea     rcx, aCheckingNtsKeR; "Checking NTS KE results for %s in %u mi"...
0x18003b37b  call    FileLogAdd
0x18003b380  mov     rax, [rsi]
0x18003b383  mov     rcx, [rax+8]
0x18003b387  cmp     byte ptr [rcx+608h], 0
0x18003b38e  jz      short loc_18003B39D
0x18003b390  cmp     [rcx+60Ch], r14d
0x18003b397  jz      loc_18003B82C
0x18003b39d  mov     [rsp+2A8h+var_220], 0
0x18003b3a8  mov     [rsp+2A8h+SourceString], 0
0x18003b3b1  xorps   xmm0, xmm0
0x18003b3b4  movups  xmmword ptr [rsp+2A8h+var_1D8.Length], xmm0
0x18003b3bc  xorps   xmm1, xmm1
0x18003b3bf  movups  xmmword ptr [rsp+2A8h+DestinationString.Length], xmm1
0x18003b3c7  mov     rdx, r13; SourceString
0x18003b3ca  lea     rcx, [rsp+2A8h+DestinationString]; DestinationString
0x18003b3d2  call    cs:__imp_RtlInitUnicodeString
0x18003b3d9  nop     dword ptr [rax+rax+00h]
0x18003b3de  lea     rdx, [rsp+2A8h+SourceString]; unsigned __int16 **
0x18003b3e3  mov     ecx, r15d; dwMessageId
0x18003b3e6  call    ?GetSystemErrorString@@YAJJPEAPEAG@Z; GetSystemErrorString(long,ushort * *)
0x18003b3eb  mov     r15d, eax
0x18003b3ee  mov     [rsp+2A8h+var_220], eax
0x18003b3f5  test    eax, eax
0x18003b3f7  js      loc_18003B82C
0x18003b3fd  mov     rdx, [rsp+2A8h+SourceString]; SourceString
0x18003b402  lea     rcx, [rsp+2A8h+var_1D8]; DestinationString
0x18003b40a  call    cs:__imp_RtlInitUnicodeString
0x18003b411  nop     dword ptr [rax+rax+00h]
0x18003b416  mov     rax, 0E5109EC205D7BEA7h
0x18003b420  mul     rbx
0x18003b423  mov     rbx, rdx
0x18003b426  shr     rbx, 1Dh
0x18003b42a  mov     eax, r14d
0x18003b42d  sub     eax, 3
0x18003b430  jz      loc_18003B793
0x18003b436  sub     eax, 1
0x18003b439  jz      loc_18003B6FD
0x18003b43f  sub     eax, 1
0x18003b442  jz      loc_18003B6AB
0x18003b448  cmp     eax, 1
0x18003b44b  jnz     loc_18003B7FA
0x18003b451  lea     ecx, [rax+4]
0x18003b454  call    FileLogAllowEntry
0x18003b459  test    al, al
0x18003b45b  jz      loc_18003B7FA
0x18003b461  lea     rdx, [rsp+2A8h+var_68]
0x18003b469  lea     rcx, aLoggingWarning_16; "Logging warning: NtsNtpClient was unabl"...
0x18003b470  call    FileLogAdd
0x18003b475  jmp     loc_18003B7FA
0x18003b47a  cmp     r15d, 80072AF9h
0x18003b481  jnz     short loc_18003B48E
0x18003b483  mov     r14d, 3
0x18003b489  jmp     loc_18003B240
0x18003b48e  mov     r14d, 5
0x18003b494  mov     [rsp+2A8h+var_228], r14d
0x18003b49c  mov     [rsp+2A8h+var_224], 10h
0x18003b4a7  test    r15d, r15d
0x18003b4aa  js      loc_18003B253
0x18003b4b0  lea     rax, [rsp+2A8h+var_200]
0x18003b4b8  mov     [rsp+2A8h+var_288], rax
0x18003b4bd  mov     r9d, 1
0x18003b4c3  lea     r8, [rsp+2A8h+var_224]
0x18003b4cb  lea     rdx, [rsp+2A8h+var_100]
0x18003b4d3  mov     rcx, [rsp+2A8h+SourceString]
0x18003b4d8  call    ?CheckDuplicatePeers@@YAJAEAV?$vector@V?$AutoPtr@UNtpPeer@@@@V?$MyThrowingAllocator@V?$AutoPtr@UNtpPeer@@@@@@@std@@PEAUsockaddr_storage@@PEAIIPEAPEAG@Z; CheckDuplicatePeers(std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>> &,sockaddr_storage *,uint *,uint,ushort * *)
0x18003b4dd  mov     r15d, eax
0x18003b4e0  mov     [rsp+2A8h+var_218], eax
0x18003b4e7  mov     ebx, 4
0x18003b4ec  test    eax, eax
0x18003b4ee  cmovs   r14d, ebx
0x18003b4f2  mov     [rsp+2A8h+var_228], r14d
0x18003b4fa  mov     r12, [rsp+2A8h+var_200]
0x18003b502  jmp     loc_18003B258
0x18003b507  mov     rax, [rsi]
0x18003b50a  mov     rcx, [rax+8]
0x18003b50e  cmp     byte ptr [rcx+608h], 0
0x18003b515  jz      short loc_18003B575
0x18003b517  xorps   xmm0, xmm0
0x18003b51a  movups  xmmword ptr [rsp+2A8h+var_1A0.Length], xmm0
0x18003b522  mov     rdx, r13; SourceString
0x18003b525  lea     rcx, [rsp+2A8h+var_1A0]; DestinationString
0x18003b52d  call    cs:__imp_RtlInitUnicodeString
0x18003b534  nop     dword ptr [rax+rax+00h]
0x18003b539  mov     ecx, ebx
0x18003b53b  call    FileLogAllowEntry
0x18003b540  test    al, al
0x18003b542  jz      short loc_18003B553
0x18003b544  mov     rdx, r13
0x18003b547  lea     rcx, aLoggingWarning; "Logging warning: NtsNtpClient succeeds "...
0x18003b54e  call    FileLogAdd
0x18003b553  lea     r9, [rsp+2A8h+var_1A0]
0x18003b55b  lea     r8, aU; "u"
0x18003b562  lea     rdx, W32TIME_EVENT_MANUAL_PEER_SUCCESS_ERROR
0x18003b569  lea     rcx, ?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x18003b570  call    LogEvent
0x18003b575  xor     ebx, ebx
0x18003b577  mov     [rsp+2A8h+var_1F0], ebx
0x18003b57e  mov     r15, [rsp+2A8h+SourceString]
0x18003b583  cmp     ebx, [rsp+2A8h+var_208]
0x18003b58a  jnb     loc_18003B640
0x18003b590  mov     ecx, ebx
0x18003b592  add     rcx, r14
0x18003b595  mov     rax, [r15]
0x18003b598  lea     rdx, [rax+rcx*8]
0x18003b59c  lea     rcx, [rsp+2A8h+SourceString]
0x18003b5a1  call    ??0?$AutoPtr@UNtpPeer@@@@QEAA@AEBV0@@Z; AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(AutoPtr<NtpPeer> const &)
0x18003b5a6  nop
0x18003b5a7  mov     rax, [rsi]
0x18003b5aa  mov     rcx, [rax+8]
  ... truncated ...
```
