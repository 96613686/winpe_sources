# CEssStateManager::SetNonVsmState(void)

- ea: `0x180073ee4`
- end: `0x18007421c`
- name: `?SetNonVsmState@CEssStateManager@@SAXXZ`
- size: `824`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800447b0`

## callees

- `0x180001434`
- `0x180014110`
- `0x180014854`
- `0x180014894`
- `0x180016d38`
- `0x18003f2dc`
- `0x180044b1c`
- `0x180068f60`
- `0x180069cc8`
- `0x180072d58`
- `0x180073060`
- `0x180073ee4`
- `0x1800743fc`
- `0x1800be5e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800741e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800741f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800741e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800741f2`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180074144`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180074144`

## string_xrefs

- `0x18007409d`: `SupportPeripheralsWithEnhancedSignInSecurity`
- `0x180073f51`: `onecore\ds\security\biometrics\service\server\essstatemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void CEssStateManager::SetNonVsmState(void)
{
  __int64 v0; // rax
  __int64 v1; // rcx
  unsigned int v2; // eax
  unsigned int value; // eax
  unsigned int *v4; // r9
  int EnrolledFactorsCommon; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  bool v9; // r8
  unsigned int v10; // esi
  unsigned int v11; // eax
  unsigned int v12; // ebx
  unsigned int v13; // edi
  int v14; // eax
  int v15; // eax
  __int64 v16; // rcx
  unsigned int lpData; // [rsp+20h] [rbp-A9h]
  unsigned int lpDataa; // [rsp+20h] [rbp-A9h]
  unsigned int lpDatab; // [rsp+20h] [rbp-A9h]
  unsigned int v20; // [rsp+40h] [rbp-89h] BYREF
  unsigned int v21; // [rsp+48h] [rbp-81h] BYREF
  int v22; // [rsp+50h] [rbp-79h] BYREF
  HKEY v23; // [rsp+58h] [rbp-71h] BYREF
  _DWORD v24[2]; // [rsp+60h] [rbp-69h] BYREF
  HKEY v25[2]; // [rsp+68h] [rbp-61h] BYREF
  _OWORD v26[2]; // [rsp+78h] [rbp-51h] BYREF
  _DWORD v27[20]; // [rsp+A0h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v26[0] = 0;
  v26[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v26[0]) = 0;
  if ( (int)GetWinBioRegistryLocation((__int64)v26) >= 0 )
  {
    v23 = 0;
    v0 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
    v2 = wil::reg::open_unique_key_nothrow(v1, v0, &v23);
    if ( v2 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x1C1,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\essstatemanager.cpp",
        (const char *)v2,
        lpData);
    v24[0] = 0;
    value = wil::reg::get_value_nothrow<unsigned long,0>(v23, 0, L"NonVsmStateUpgradeFlow", v24);
    if ( value )
    {
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x1C3,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\essstatemanager.cpp",
        (const char *)value,
        lpData);
      memset_0(v27, 0, 0x4Cu);
      v27[0] = 1;
      v27[1] = 621175426;
      v21 = 0;
      v20 = 0;
      EnrolledFactorsCommon = winbio::GetEnrolledFactorsCommon((winbio *)v27, (struct _WINBIO_IDENTITY *)&v20, &v21, v4);
      if ( EnrolledFactorsCommon >= 0 )
      {
        v25[0] = 0;
        v6 = wil::reg::open_unique_key_nothrow(
               retaddr,
               L"Software\\Microsoft\\Policies\\PassportForWork\\Biometrics",
               v25);
        if ( v6 )
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x1D7,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\essstatemanager.cpp",
            (const char *)v6,
            lpDataa);
        v22 = 1;
        v7 = wil::reg::get_value_nothrow<unsigned long,0>(v25[0], 0, L"EnableESSwithSupportedPeripherals", &v22);
        if ( v7 )
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x1DD,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\essstatemanager.cpp",
            (const char *)v7,
            lpDataa);
        v8 = wil::reg::get_value_nothrow<unsigned long,0>(v23, 0, L"EnableESS", &v22);
        v10 = v21;
        if ( v8 )
        {
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x1E1,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\essstatemanager.cpp",
            (const char *)v8,
            lpDataa);
          v11 = wil::reg::get_value_nothrow<unsigned long,0>(
                  v23,
                  0,
                  L"SupportPeripheralsWithEnhancedSignInSecurity",
                  &v22);
          if ( v11 )
          {
            wil::details::in1diag3::_Log_Win32(
              retaddr,
              (void *)0x1E5,
              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\essstatemanager.cpp",
              (const char *)v11,
              lpDataa);
            v12 = 0;
            v13 = v20;
            if ( !v10 )
              v12 = v20;
          }
          else
          {
            v13 = v20;
            v12 = v22 != 0 ? v20 : 0;
          }
        }
        else
        {
          v13 = v20;
          v12 = v20;
          if ( v22 == 1 )
            v12 = 0;
        }
        v14 = winbio::SetNonVsmFactorsForWildcard((winbio *)v27, (struct _WINBIO_IDENTITY *)v12, v9);
        if ( v14 >= 0 )
        {
          v21 = 1;
          v15 = RegSetKeyValueW(v23, 0, L"NonVsmStateUpgradeFlow", 4u, &v21, 4u);
          if ( v15 > 0 )
            v15 = (unsigned __int16)v15 | 0x80070000;
          if ( v15 )
            wil::details::in1diag3::_Log_Win32(
              retaddr,
              (void *)0x1F2,
              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\essstatemanager.cpp",
              (const char *)(unsigned int)v15,
              lpDatab);
          if ( (unsigned int)dword_18010F170 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18010F170, 0x400000000000LL) )
          {
            v25[1] = (HKEY)50331648;
            v21 = v12;
            v20 = v10;
            v24[1] = v13;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
              v16,
              (__int64)byte_1800ED093);
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1EF,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\essstatemanager.cpp",
            (const char *)(unsigned int)v14,
            lpDataa);
        }
        if ( v25[0] )
          RegCloseKey(v25[0]);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1CD,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\essstatemanager.cpp",
          (const char *)(unsigned int)EnrolledFactorsCommon,
          lpDataa);
      }
    }
    if ( v23 )
      RegCloseKey(v23);
  }
  std::wstring::_Tidy_deallocate(v26);
}

```

## disassembly

```asm
0x180073ee4  push    rbp
0x180073ee6  push    rbx
0x180073ee7  push    rsi
0x180073ee8  push    rdi
0x180073ee9  push    r15
0x180073eeb  lea     rbp, [rsp-37h]
0x180073ef0  sub     rsp, 100h
0x180073ef7  mov     rax, cs:__security_cookie
0x180073efe  xor     rax, rsp
0x180073f01  mov     [rbp+57h+var_30], rax
0x180073f05  xorps   xmm0, xmm0
0x180073f08  movups  xmmword ptr [rbp+57h+var_E0.Value+34h], xmm0
0x180073f0c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180073f14  movdqu  xmmword ptr [rbp+57h+var_E0.Value+44h], xmm1
0x180073f19  xor     eax, eax
0x180073f1b  mov     word ptr [rbp+57h+var_E0.Value+34h], ax
0x180073f1f  lea     rcx, [rbp+57h+var_E0.Value+34h]
0x180073f23  call    ?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWinBioRegistryLocation(std::wstring *)
0x180073f28  test    eax, eax
0x180073f2a  js      loc_1800741F9
0x180073f30  mov     qword ptr [rbp+57h+var_E0.Value+14h], 0
0x180073f38  lea     rcx, [rbp+57h+var_E0.Value+34h]
0x180073f3c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180073f41  mov     rdx, rax
0x180073f44  lea     r8, [rbp+57h+var_E0.Value+14h]
0x180073f48  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x180073f4d  mov     rcx, [rbp+5Fh]; this
0x180073f51  lea     r15, aOnecoreDsSecur_28; "onecore\\ds\\security\\biometrics\\serv"...
0x180073f58  test    eax, eax
0x180073f5a  jz      short loc_180073F6C
0x180073f5c  mov     r9d, eax; char *
0x180073f5f  mov     r8, r15; unsigned int
0x180073f62  mov     edx, 1C1h; void *
0x180073f67  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180073f6c  mov     dword ptr [rbp+57h+var_E0.Value+1Ch], 0
0x180073f73  lea     r9, [rbp+57h+var_E0.Value+1Ch]
0x180073f77  lea     r8, aNonvsmstateupg; "NonVsmStateUpgradeFlow"
0x180073f7e  xor     edx, edx
0x180073f80  mov     rcx, qword ptr [rbp+57h+var_E0.Value+14h]
0x180073f84  call    ??$get_value_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180073f89  mov     rcx, [rbp+5Fh]; this
0x180073f8d  test    eax, eax
0x180073f8f  jz      loc_1800741E9
0x180073f95  mov     r9d, eax; char *
0x180073f98  mov     r8, r15; unsigned int
0x180073f9b  mov     edx, 1C3h; void *
0x180073fa0  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180073fa5  xor     edx, edx; Val
0x180073fa7  lea     r8d, [rdx+4Ch]; Size
0x180073fab  lea     rcx, [rbp+57h+var_80]; void *
0x180073faf  call    memset_0
0x180073fb4  mov     [rbp+57h+var_80], 1
0x180073fbb  mov     [rbp+57h+var_7C], 25066282h
0x180073fc2  mov     dword ptr [rsp+120h+var_E0.Value+4], 0
0x180073fca  mov     [rsp+120h+var_E0.Type], 0
0x180073fd2  lea     r8, [rsp+120h+var_E0.Value+4]; unsigned int *
0x180073fd7  lea     rdx, [rsp+120h+var_E0]; struct _WINBIO_IDENTITY *
0x180073fdc  lea     rcx, [rbp+57h+var_80]; this
0x180073fe0  call    ?GetEnrolledFactorsCommon@winbio@@YAJPEAU_WINBIO_IDENTITY@@PEAI1@Z; winbio::GetEnrolledFactorsCommon(_WINBIO_IDENTITY *,uint *,uint *)
0x180073fe5  mov     rcx, [rbp+5Fh]; this
0x180073fe9  test    eax, eax
0x180073feb  jns     short loc_180074002
0x180073fed  mov     r9d, eax; char *
0x180073ff0  mov     r8, r15; unsigned int
0x180073ff3  mov     edx, 1CDh; void *
0x180073ff8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180073ffd  jmp     loc_1800741E9
0x180074002  mov     qword ptr [rbp+57h+var_E0.Value+24h], 0
0x18007400a  lea     r8, [rbp+57h+var_E0.Value+24h]
0x18007400e  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Policies\\Passport"...
0x180074015  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18007401a  mov     rcx, [rbp+5Fh]; this
0x18007401e  test    eax, eax
0x180074020  jz      short loc_180074032
0x180074022  mov     r9d, eax; char *
0x180074025  mov     r8, r15; unsigned int
0x180074028  mov     edx, 1D7h; void *
0x18007402d  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180074032  mov     dword ptr [rbp+57h+var_E0.Value+0Ch], 1
0x180074039  lea     r9, [rbp+57h+var_E0.Value+0Ch]
0x18007403d  lea     r8, aEnableesswiths; "EnableESSwithSupportedPeripherals"
0x180074044  xor     edx, edx
0x180074046  mov     rcx, qword ptr [rbp+57h+var_E0.Value+24h]
0x18007404a  call    ??$get_value_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18007404f  mov     rcx, [rbp+5Fh]; this
0x180074053  test    eax, eax
0x180074055  jz      short loc_180074067
0x180074057  mov     r9d, eax; char *
0x18007405a  mov     r8, r15; unsigned int
0x18007405d  mov     edx, 1DDh; void *
0x180074062  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180074067  lea     r9, [rbp+57h+var_E0.Value+0Ch]
0x18007406b  lea     r8, aEnableess; "EnableESS"
0x180074072  xor     edx, edx
0x180074074  mov     rcx, qword ptr [rbp+57h+var_E0.Value+14h]
0x180074078  call    ??$get_value_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18007407d  mov     rcx, [rbp+5Fh]; this
0x180074081  mov     esi, dword ptr [rsp+120h+var_E0.Value+4]
0x180074085  test    eax, eax
0x180074087  jz      short loc_1800740E3
0x180074089  mov     r9d, eax; char *
0x18007408c  mov     r8, r15; unsigned int
0x18007408f  mov     edx, 1E1h; void *
0x180074094  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180074099  lea     r9, [rbp+57h+var_E0.Value+0Ch]
0x18007409d  lea     r8, aSupportperiphe; "SupportPeripheralsWithEnhancedSignInSec"...
0x1800740a4  xor     edx, edx
0x1800740a6  mov     rcx, qword ptr [rbp+57h+var_E0.Value+14h]
0x1800740aa  call    ??$get_value_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800740af  mov     rcx, [rbp+5Fh]; this
0x1800740b3  test    eax, eax
0x1800740b5  jz      short loc_1800740D4
0x1800740b7  mov     r9d, eax; char *
0x1800740ba  mov     r8, r15; unsigned int
0x1800740bd  mov     edx, 1E5h; void *
0x1800740c2  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800740c7  xor     ebx, ebx
0x1800740c9  mov     edi, [rsp+120h+var_E0.Type]
0x1800740cd  test    esi, esi
0x1800740cf  cmovz   ebx, edi
0x1800740d2  jmp     short loc_1800740F2
0x1800740d4  mov     eax, dword ptr [rbp+57h+var_E0.Value+0Ch]
0x1800740d7  neg     eax
0x1800740d9  sbb     ebx, ebx
0x1800740db  mov     edi, [rsp+120h+var_E0.Type]
0x1800740df  and     ebx, edi
0x1800740e1  jmp     short loc_1800740F2
0x1800740e3  mov     edi, [rsp+120h+var_E0.Type]
0x1800740e7  mov     ebx, edi
0x1800740e9  xor     eax, eax
0x1800740eb  cmp     dword ptr [rbp+57h+var_E0.Value+0Ch], 1
0x1800740ef  cmovz   ebx, eax
0x1800740f2  mov     edx, ebx; struct _WINBIO_IDENTITY *
0x1800740f4  lea     rcx, [rbp+57h+var_80]; this
0x1800740f8  call    ?SetNonVsmFactorsForWildcard@winbio@@YAJPEAU_WINBIO_IDENTITY@@I@Z; winbio::SetNonVsmFactorsForWildcard(_WINBIO_IDENTITY *,uint)
0x1800740fd  mov     rcx, [rbp+5Fh]; this
0x180074101  test    eax, eax
0x180074103  jns     short loc_18007411A
0x180074105  mov     r9d, eax; char *
0x180074108  mov     r8, r15; unsigned int
0x18007410b  mov     edx, 1EFh; void *
0x180074110  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180074115  jmp     loc_1800741D9
0x18007411a  mov     dword ptr [rsp+120h+var_E0.Value+4], 1
0x180074122  mov     r9d, 4; dwType
0x180074128  mov     [rsp+120h+cbData], r9d; cbData
0x18007412d  lea     rax, [rsp+120h+var_E0.Value+4]
0x180074132  mov     [rsp+120h+lpData], rax; unsigned int
0x180074137  lea     r8, aNonvsmstateupg; "NonVsmStateUpgradeFlow"
0x18007413e  xor     edx, edx; lpSubKey
0x180074140  mov     rcx, qword ptr [rbp+57h+var_E0.Value+14h]; hKey
0x180074144  call    cs:__imp_RegSetKeyValueW
0x18007414a  test    eax, eax
0x18007414c  jle     short loc_180074156
0x18007414e  movzx   eax, ax
0x180074151  or      eax, 80070000h
0x180074156  mov     rcx, [rbp+5Fh]; this
0x18007415a  test    eax, eax
0x18007415c  jz      short loc_18007416E
0x18007415e  mov     r9d, eax; char *
0x180074161  mov     r8, r15; unsigned int
0x180074164  mov     edx, 1F2h; void *
0x180074169  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18007416e  mov     eax, cs:dword_18010F170
0x180074174  cmp     eax, 5
0x180074177  jbe     short loc_1800741D9
0x180074179  mov     rdx, 400000000000h
0x180074183  lea     rcx, dword_18010F170
0x18007418a  call    _tlgKeywordOn
0x18007418f  test    al, al
0x180074191  jz      short loc_1800741D9
0x180074193  mov     qword ptr [rbp+57h+var_E0.Value+2Ch], 3000000h
0x18007419b  mov     dword ptr [rsp+120h+var_E0.Value+4], ebx
0x18007419f  mov     [rsp+120h+var_E0.Type], esi
0x1800741a3  mov     dword ptr [rbp+57h+var_E0.Value+20h], edi
0x1800741a6  lea     rax, [rbp+57h+var_E0.Value+2Ch]
0x1800741aa  mov     [rsp+120h+var_E8], rax
0x1800741af  lea     rax, [rsp+120h+var_E0.Value+4]
0x1800741b4  mov     [rsp+120h+var_F0], rax
0x1800741b9  lea     rax, [rsp+120h+var_E0]
0x1800741be  mov     qword ptr [rsp+120h+cbData], rax
0x1800741c3  lea     rax, [rbp+57h+var_E0.Value+20h]
0x1800741c7  mov     [rsp+120h+lpData], rax
0x1800741cc  lea     rdx, byte_1800ED093
0x1800741d3  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800741d8  nop
0x1800741d9  mov     rcx, qword ptr [rbp+57h+var_E0.Value+24h]; hKey
0x1800741dd  test    rcx, rcx
0x1800741e0  jz      short loc_1800741E9
0x1800741e2  call    cs:__imp_RegCloseKey
0x1800741e8  nop
0x1800741e9  mov     rcx, qword ptr [rbp+57h+var_E0.Value+14h]; hKey
0x1800741ed  test    rcx, rcx
0x1800741f0  jz      short loc_1800741F9
0x1800741f2  call    cs:__imp_RegCloseKey
0x1800741f8  nop
0x1800741f9  lea     rcx, [rbp+57h+var_E0.Value+34h]
0x1800741fd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180074202  mov     rcx, [rbp+57h+var_30]
0x180074206  xor     rcx, rsp; StackCookie
0x180074209  call    __security_check_cookie
0x18007420e  add     rsp, 100h
0x180074215  pop     r15
0x180074217  pop     rdi
0x180074218  pop     rsi
0x180074219  pop     rbx
0x18007421a  pop     rbp
0x18007421b  retn
```
