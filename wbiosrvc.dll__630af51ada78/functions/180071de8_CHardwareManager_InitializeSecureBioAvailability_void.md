# CHardwareManager::InitializeSecureBioAvailability(void)

- ea: `0x180071de8`
- end: `0x1800721e8`
- name: `?InitializeSecureBioAvailability@CHardwareManager@@SAXXZ`
- size: `1024`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180045044`
- `0x180073538`

## callees

- `0x1800119c4`
- `0x180014110`
- `0x180014854`
- `0x180014894`
- `0x180023d88`
- `0x18002a5e4`
- `0x18002d3b4`
- `0x180035d78`
- `0x18003c780`
- `0x18003f2dc`
- `0x180044b1c`
- `0x180051030`
- `0x180055878`
- `0x1800559c8`
- `0x180055f74`
- `0x180056378`
- `0x180068f60`
- `0x180071de8`
- `0x180072410`
- `0x180072d58`
- `0x1800760f0`
- `0x1800b5134`
- `0x1800b53e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072033`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072033`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180072007`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180072007`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180071fbb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180071fbb`

## string_xrefs

- `0x180071e3a`: `onecore\ds\security\biometrics\service\server\hardwaremanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void CHardwareManager::InitializeSecureBioAvailability(void)
{
  struct CHardwareManager *v0; // rax
  struct CHardwareManager *v1; // rax
  int IsSecureBioAvailable; // eax
  int v3; // edi
  int exists; // eax
  int v5; // ebx
  struct CHardwareManager *v6; // rax
  struct CHardwareManager *v7; // rax
  struct CHardwareManager *v8; // rax
  struct CHardwareManager *v9; // rax
  int WinBioRegistryLocation; // eax
  const WCHAR *v11; // rax
  PHKEY v12; // r8
  unsigned int v13; // eax
  wil::details::in1diag3 *v14; // rcx
  __int64 v15; // rdx
  struct CHardwareManager *v16; // rax
  int v17; // ebx
  struct CHardwareManager *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  struct CHardwareManager *v22; // rax
  int v23; // eax
  struct CHardwareManager *v24; // rax
  struct CHardwareManager *v25; // rax
  __int64 v26; // r9
  bool *phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  bool v30[2]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE Data[12]; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey[2]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v33[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v34[360]; // [rsp+80h] [rbp-80h] BYREF
  int v35; // [rsp+1E8h] [rbp+E8h]
  __int16 v36; // [rsp+224h] [rbp+124h]
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v0 = CHardwareManager::Instance();
  *((_WORD *)v0 + 105) |= 1u;
  v1 = CHardwareManager::Instance();
  IsSecureBioAvailable = BioTrustlet::IsSecureBioAvailable((unsigned __int16 *)v1 + 105);
  v3 = IsSecureBioAvailable;
  if ( IsSecureBioAvailable < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x178,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
      (const char *)(unsigned int)IsSecureBioAvailable,
      (int)phkResult);
  v30[0] = 1;
  exists = CHardwareManager::ExistsNgcVtl0Container(v30);
  v5 = exists;
  if ( exists < 0 )
  {
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x180,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
      (const char *)(unsigned int)exists,
      (int)phkResult);
    v3 = v5;
  }
  if ( v30[0] )
  {
    v6 = CHardwareManager::Instance();
    *((_WORD *)v6 + 105) &= ~1u;
    v7 = CHardwareManager::Instance();
    *((_WORD *)v7 + 105) |= 0x40u;
  }
  if ( *((int *)CHardwareManager::Instance() + 39) >= 3 )
  {
    v8 = CHardwareManager::Instance();
    *((_WORD *)v8 + 105) |= 0x20u;
    v9 = CHardwareManager::Instance();
    *((_WORD *)v9 + 105) &= ~1u;
  }
  if ( (unsigned int)dword_18010F170 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18010F170, 0x400000000000LL) )
  {
    hKey[0] = (HKEY)50331648;
    *(_DWORD *)Data = v3;
    *(_WORD *)v30 = *((_WORD *)CHardwareManager::Instance() + 105);
    phkResult = v30;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      *(unsigned __int16 *)v30,
      (__int64)byte_1800ECE65);
  }
  v33[0] = 0;
  v33[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v33[0]) = 0;
  WinBioRegistryLocation = GetWinBioRegistryLocation((__int64)v33);
  if ( WinBioRegistryLocation < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x19B,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
      (const char *)(unsigned int)WinBioRegistryLocation,
      (int)phkResult);
    goto LABEL_21;
  }
  hKey[0] = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(hKey);
  v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v33);
  v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0x2001Fu, v12);
  v14 = retaddr;
  if ( v13 )
  {
    v15 = 423;
  }
  else
  {
    *(_DWORD *)Data = *((unsigned __int16 *)CHardwareManager::Instance() + 105);
    v13 = RegSetValueExW(hKey[0], L"SecureBioAvailabilityInCensus", 0, 4u, Data, 4u);
    v14 = retaddr;
    if ( !v13 )
      goto LABEL_19;
    v15 = 435;
  }
  wil::details::in1diag3::_Log_Win32(
    v14,
    (void *)v15,
    (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
    (const char *)v13,
    phkResulta);
LABEL_19:
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
LABEL_21:
  if ( (*((_BYTE *)CHardwareManager::Instance() + 210) & 1) != 0 )
  {
    *((_BYTE *)CHardwareManager::Instance() + 152) = 1;
    v16 = CHardwareManager::Instance();
    v17 = BioTrustlet::Start((struct CHardwareManager *)((char *)v16 + 88));
    if ( v17 >= 0 )
    {
      v18 = CHardwareManager::Instance();
      v17 = BioTrustlet::WaitForTrustletStarted((void **)v18 + 11, v19, v20, v21, phkResulta);
      if ( v17 >= 0 )
      {
        v22 = CHardwareManager::Instance();
        v17 = BioTrustlet::ServerBind((struct CHardwareManager *)((char *)v22 + 88));
        if ( v17 >= 0 )
        {
          *(_OWORD *)hKey = *(_OWORD *)&xmmword_1800DF158;
          v23 = StorageManagerImport((struct _GUID *)hKey);
          if ( v23 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1C7,
              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
              (const char *)(unsigned int)v23,
              phkResultb);
        }
      }
    }
    CEtwEvent::CEtwEvent((CEtwEvent *)v34);
    v35 = v17;
    if ( v17 < 0 )
    {
      if ( (unsigned __int64)(*((_QWORD *)CHardwareManager::Instance() + 16) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        v25 = CHardwareManager::Instance();
        BioTrustlet::Terminate((struct CHardwareManager *)((char *)v25 + 88));
      }
      v36 = *((_WORD *)CHardwareManager::Instance() + 105);
      CEtwEvent::Write(v34, 1600, 1);
      if ( (unsigned int)dword_18010F170 > 2 )
      {
        *(_DWORD *)Data = v17;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_18010F170,
          (unsigned __int8 *)&unk_1800ECE30,
          0,
          v26,
          (__int64)Data);
      }
    }
    else
    {
      CEtwEvent::Write(v34, 1601, 1);
      v24 = CHardwareManager::Instance();
      ++*((_DWORD *)v24 + 39);
    }
    goto LABEL_36;
  }
  if ( (*((_BYTE *)CHardwareManager::Instance() + 210) & 1) == 0 )
  {
    CEtwEvent::CEtwEvent((CEtwEvent *)v34);
    v35 = -2147024846;
    v36 = *((_WORD *)CHardwareManager::Instance() + 105);
    CEtwEvent::Write(v34, 1600, 1);
LABEL_36:
    CEtwEvent::~CEtwEvent((CEtwEvent *)v34);
  }
  std::wstring::_Tidy_deallocate(v33);
}

```

## disassembly

```asm
0x180071de8  push    rbp
0x180071dea  push    rbx
0x180071deb  push    rsi
0x180071dec  push    rdi
0x180071ded  push    r14
0x180071def  lea     rbp, [rsp-1A0h]
0x180071df7  sub     rsp, 2A0h
0x180071dfe  mov     rax, cs:__security_cookie
0x180071e05  xor     rax, rsp
0x180071e08  mov     [rbp+1C0h+var_30], rax
0x180071e0f  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180071e14  mov     esi, 1
0x180071e19  or      [rax+0D2h], si
0x180071e20  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180071e25  lea     rcx, [rax+0D2h]; unsigned __int16 *
0x180071e2c  call    ?IsSecureBioAvailable@BioTrustlet@@SAJAEAG@Z; BioTrustlet::IsSecureBioAvailable(ushort &)
0x180071e31  mov     edi, eax
0x180071e33  mov     rcx, [rbp+1C8h]; this
0x180071e3a  lea     r14, aOnecoreDsSecur_25; "onecore\\ds\\security\\biometrics\\serv"...
0x180071e41  test    eax, eax
0x180071e43  jns     short loc_180071E55
0x180071e45  mov     r9d, eax; char *
0x180071e48  mov     r8, r14; unsigned int
0x180071e4b  mov     edx, 178h; void *
0x180071e50  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180071e55  mov     [rsp+2C0h+var_280], sil
0x180071e5a  lea     rcx, [rsp+2C0h+var_280]; bool *
0x180071e5f  call    ?ExistsNgcVtl0Container@CHardwareManager@@SAJPEA_N@Z; CHardwareManager::ExistsNgcVtl0Container(bool *)
0x180071e64  mov     ebx, eax
0x180071e66  test    eax, eax
0x180071e68  jns     short loc_180071E83
0x180071e6a  mov     rcx, [rbp+1C8h]; this
0x180071e71  mov     r9d, eax; char *
0x180071e74  mov     r8, r14; unsigned int
0x180071e77  mov     edx, 180h; void *
0x180071e7c  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180071e81  mov     edi, ebx
0x180071e83  mov     ebx, 0FFFEh
0x180071e88  cmp     [rsp+2C0h+var_280], 0
0x180071e8d  jz      short loc_180071EA8
0x180071e8f  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180071e94  and     [rax+0D2h], bx
0x180071e9b  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180071ea0  or      word ptr [rax+0D2h], 40h
0x180071ea8  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180071ead  cmp     dword ptr [rax+9Ch], 3
0x180071eb4  jl      short loc_180071ECF
0x180071eb6  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180071ebb  or      word ptr [rax+0D2h], 20h
0x180071ec3  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180071ec8  and     [rax+0D2h], bx
0x180071ecf  mov     eax, cs:dword_18010F170
0x180071ed5  cmp     eax, 5
0x180071ed8  jbe     short loc_180071F3C
0x180071eda  mov     rdx, 400000000000h
0x180071ee4  lea     rcx, dword_18010F170
0x180071eeb  call    _tlgKeywordOn
0x180071ef0  test    al, al
0x180071ef2  jz      short loc_180071F3C
0x180071ef4  mov     [rsp+2C0h+hKey], 3000000h
0x180071efd  mov     dword ptr [rsp+2C0h+Data], edi
0x180071f01  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180071f06  movzx   ecx, word ptr [rax+0D2h]
0x180071f0d  mov     word ptr [rsp+2C0h+var_280], cx
0x180071f12  lea     rax, [rsp+2C0h+hKey]
0x180071f17  mov     [rsp+2C0h+var_290], rax
0x180071f1c  lea     rax, [rsp+2C0h+Data]
0x180071f21  mov     qword ptr [rsp+2C0h+cbData], rax
0x180071f26  lea     rax, [rsp+2C0h+var_280]
0x180071f2b  mov     [rsp+2C0h+phkResult], rax; int
0x180071f30  lea     rdx, byte_1800ECE65
0x180071f37  call    ??$Write@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180071f3c  xorps   xmm0, xmm0
0x180071f3f  movups  [rsp+2C0h+var_260], xmm0
0x180071f44  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180071f4c  movdqu  [rsp+2C0h+var_250], xmm1
0x180071f52  xor     eax, eax
0x180071f54  mov     word ptr [rsp+2C0h+var_260], ax
0x180071f59  lea     rcx, [rsp+2C0h+var_260]
0x180071f5e  call    ?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWinBioRegistryLocation(std::wstring *)
0x180071f63  mov     rcx, [rbp+1C8h]; this
0x180071f6a  test    eax, eax
0x180071f6c  jns     short loc_180071F83
0x180071f6e  mov     r9d, eax; char *
0x180071f71  mov     r8, r14; unsigned int
0x180071f74  mov     edx, 19Bh; void *
0x180071f79  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180071f7e  jmp     loc_180072039
0x180071f83  mov     [rsp+2C0h+hKey], 0
0x180071f8c  lea     rcx, [rsp+2C0h+hKey]
0x180071f91  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180071f96  mov     r8, rax
0x180071f99  lea     rcx, [rsp+2C0h+var_260]
0x180071f9e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180071fa3  mov     rdx, rax; lpSubKey
0x180071fa6  mov     [rsp+2C0h+phkResult], r8; phkResult
0x180071fab  mov     r9d, 2001Fh; samDesired
0x180071fb1  xor     r8d, r8d; ulOptions
0x180071fb4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180071fbb  call    cs:__imp_RegOpenKeyExW
0x180071fc1  mov     rcx, [rbp+1C8h]
0x180071fc8  test    eax, eax
0x180071fca  jz      short loc_180071FD3
0x180071fcc  mov     edx, 1A7h
0x180071fd1  jmp     short loc_18007201D
0x180071fd3  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180071fd8  movzx   ecx, word ptr [rax+0D2h]
0x180071fdf  mov     dword ptr [rsp+2C0h+Data], ecx
0x180071fe3  mov     r9d, 4; dwType
0x180071fe9  mov     [rsp+2C0h+cbData], r9d; cbData
0x180071fee  lea     rax, [rsp+2C0h+Data]
0x180071ff3  mov     [rsp+2C0h+phkResult], rax; int
0x180071ff8  xor     r8d, r8d; Reserved
0x180071ffb  lea     rdx, aSecurebioavail; "SecureBioAvailabilityInCensus"
0x180072002  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180072007  call    cs:__imp_RegSetValueExW
0x18007200d  mov     rcx, [rbp+1C8h]; this
0x180072014  test    eax, eax
0x180072016  jz      short loc_180072029
0x180072018  mov     edx, 1B3h; void *
0x18007201d  mov     r9d, eax; char *
0x180072020  mov     r8, r14; unsigned int
0x180072023  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180072028  nop
0x180072029  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18007202e  test    rcx, rcx
0x180072031  jz      short loc_180072039
0x180072033  call    cs:__imp_RegCloseKey
0x180072039  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x18007203e  test    [rax+0D2h], sil
0x180072045  jz      loc_180072170
0x18007204b  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180072050  mov     [rax+98h], sil
0x180072057  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x18007205c  lea     rcx, [rax+58h]; this
0x180072060  call    ?Start@BioTrustlet@@QEAAJ_N@Z; BioTrustlet::Start(bool)
0x180072065  mov     ebx, eax
0x180072067  test    eax, eax
0x180072069  js      short loc_1800720C5
0x18007206b  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180072070  lea     rcx, [rax+58h]; this
0x180072074  call    ?WaitForTrustletStarted@BioTrustlet@@QEAAJK@Z; BioTrustlet::WaitForTrustletStarted(ulong)
0x180072079  mov     ebx, eax
0x18007207b  test    eax, eax
0x18007207d  js      short loc_1800720C5
0x18007207f  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180072084  lea     rcx, [rax+58h]; this
0x180072088  call    ?ServerBind@BioTrustlet@@QEAAJXZ; BioTrustlet::ServerBind(void)
0x18007208d  mov     ebx, eax
0x18007208f  test    eax, eax
0x180072091  js      short loc_1800720C5
0x180072093  movups  xmm0, cs:xmmword_1800DF158
0x18007209a  movdqu  xmmword ptr [rsp+2C0h+hKey], xmm0
0x1800720a0  lea     rcx, [rsp+2C0h+hKey]; struct _GUID
0x1800720a5  call    ?StorageManagerImport@@YAJU_GUID@@@Z; StorageManagerImport(_GUID)
0x1800720aa  mov     rcx, [rbp+1C8h]; this
0x1800720b1  test    eax, eax
0x1800720b3  jns     short loc_1800720C5
0x1800720b5  mov     r9d, eax; char *
0x1800720b8  mov     r8, r14; unsigned int
0x1800720bb  mov     edx, 1C7h; void *
0x1800720c0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800720c5  lea     rcx, [rbp+1C0h+var_240]; this
0x1800720c9  call    ??0CEtwEvent@@QEAA@XZ; CEtwEvent::CEtwEvent(void)
0x1800720ce  nop
0x1800720cf  mov     [rbp+1C0h+var_D8], ebx
0x1800720d5  test    ebx, ebx
0x1800720d7  js      short loc_1800720F7
0x1800720d9  mov     r8d, esi
0x1800720dc  mov     edx, 641h
0x1800720e1  lea     rcx, [rbp+1C0h+var_240]
0x1800720e5  call    ?Write@CEtwEvent@@QEAAJKW4WBioEventLevel@@@Z; CEtwEvent::Write(ulong,WBioEventLevel)
0x1800720ea  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800720ef  add     [rax+9Ch], esi
0x1800720f5  jmp     short loc_18007216E
0x1800720f7  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800720fc  mov     rcx, [rax+80h]
0x180072103  sub     rcx, rsi
0x180072106  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18007210a  ja      short loc_18007211A
0x18007210c  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180072111  lea     rcx, [rax+58h]; this
0x180072115  call    ?Terminate@BioTrustlet@@QEAAJXZ; BioTrustlet::Terminate(void)
0x18007211a  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x18007211f  movzx   ecx, word ptr [rax+0D2h]
0x180072126  mov     [rbp+1C0h+var_9C], cx
0x18007212d  mov     r8d, esi
0x180072130  mov     edx, 640h
0x180072135  lea     rcx, [rbp+1C0h+var_240]
0x180072139  call    ?Write@CEtwEvent@@QEAAJKW4WBioEventLevel@@@Z; CEtwEvent::Write(ulong,WBioEventLevel)
0x18007213e  mov     eax, cs:dword_18010F170
0x180072144  cmp     eax, 2
0x180072147  jbe     short loc_18007216E
0x180072149  mov     dword ptr [rsp+2C0h+Data], ebx
0x18007214d  lea     rax, [rsp+2C0h+Data]
0x180072152  mov     [rsp+2C0h+phkResult], rax
0x180072157  xor     r8d, r8d
0x18007215a  lea     rdx, unk_1800ECE30
0x180072161  lea     rcx, dword_18010F170
0x180072168  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18007216d  nop
0x18007216e  jmp     short loc_1800721B7
0x180072170  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180072175  test    [rax+0D2h], sil
0x18007217c  jnz     short loc_1800721C1
0x18007217e  lea     rcx, [rbp+1C0h+var_240]; this
0x180072182  call    ??0CEtwEvent@@QEAA@XZ; CEtwEvent::CEtwEvent(void)
0x180072187  nop
0x180072188  mov     [rbp+1C0h+var_D8], 80070032h
0x180072192  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180072197  movzx   ecx, word ptr [rax+0D2h]
0x18007219e  mov     [rbp+1C0h+var_9C], cx
0x1800721a5  mov     r8d, esi
0x1800721a8  mov     edx, 640h
0x1800721ad  lea     rcx, [rbp+1C0h+var_240]
0x1800721b1  call    ?Write@CEtwEvent@@QEAAJKW4WBioEventLevel@@@Z; CEtwEvent::Write(ulong,WBioEventLevel)
0x1800721b6  nop
0x1800721b7  lea     rcx, [rbp+1C0h+var_240]; this
0x1800721bb  call    ??1CEtwEvent@@QEAA@XZ; CEtwEvent::~CEtwEvent(void)
0x1800721c0  nop
0x1800721c1  lea     rcx, [rsp+2C0h+var_260]
0x1800721c6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800721cb  mov     rcx, [rbp+1C0h+var_30]
0x1800721d2  xor     rcx, rsp; StackCookie
0x1800721d5  call    __security_check_cookie
0x1800721da  add     rsp, 2A0h
0x1800721e1  pop     r14
0x1800721e3  pop     rdi
0x1800721e4  pop     rsi
0x1800721e5  pop     rbx
0x1800721e6  pop     rbp
0x1800721e7  retn
```
