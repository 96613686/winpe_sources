# CDeviceStateManager::EnumerateCameras(int &,int &)

- ea: `0x180085e3c`
- end: `0x18008651b`
- name: `?EnumerateCameras@CDeviceStateManager@@QEAAJAEAH0@Z`
- size: `1759`
- prototype: `__int64 __fastcall(CDeviceStateManager *__hidden this, int *, int *)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180086524`
- `0x180086710`

## callees

- `0x1800058ec`
- `0x18001434c`
- `0x180014854`
- `0x180014894`
- `0x18002ad10`
- `0x18002d3b4`
- `0x18003f2dc`
- `0x180044b1c`
- `0x1800530c4`
- `0x18005388c`
- `0x180068f60`
- `0x180069cc8`
- `0x18007eed0`
- `0x180083618`
- `0x180083dac`
- `0x180084fe8`
- `0x18008550c`
- `0x180085e3c`
- `0x180086e14`
- `0x180086eb8`
- `0x180088d28`
- `0x1800d2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180085f1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180085f1b`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Registry_PropertyW` at `0x1800861fd`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Registry_PropertyW` at `0x1800861fd`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800860e4`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800860e4`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800860f5`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800861a6`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18008620e`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800860f5`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800861a6`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18008620e`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180086195`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180086195`
- `MFSENSORGROUP!MFCreateSensorGroup` at `0x180085f29`
- `MFSENSORGROUP!MFCreateSensorGroup` at `0x180085f29`

## string_xrefs

- `0x180085e9e`: `onecore\ds\security\biometrics\service\server\devicestatemanager.cpp`
- `0x180085efc`: `onecore\ds\security\biometrics\service\server\devicestatemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CDeviceStateManager::EnumerateCameras(CDeviceStateManager *this, ULONG *a2, int *a3)
{
  int v3; // eax
  int v4; // ebx
  HSTRING *v6; // r13
  HSTRING *v7; // r14
  PCWSTR StringRawBuffer; // rax
  unsigned int v9; // r12d
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, _QWORD, __int64 *); // rbx
  unsigned int i; // r15d
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64, _QWORD, __int64 *); // rbx
  int v15; // eax
  bool v16; // sf
  __int64 v17; // rax
  int v18; // eax
  CONFIGRET Device_Interface_PropertyW; // eax
  signed int v20; // eax
  __int64 v21; // r9
  unsigned int v22; // ecx
  __int64 **v23; // rax
  CONFIGRET v24; // eax
  signed int v25; // eax
  __int64 v26; // r9
  unsigned int v27; // ecx
  char *v28; // rdx
  CONFIGRET DevNode_Registry_PropertyW; // eax
  signed int v30; // eax
  _DWORD *v31; // rax
  __int64 *v32; // rsi
  __int64 *j; // rbx
  __int64 v34; // rax
  int v35; // r9d
  __int64 v36; // rdx
  __int64 v37; // rdx
  int PropertyBufferSize; // [rsp+20h] [rbp-E0h]
  unsigned int v39; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v40; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE v41[2]; // [rsp+36h] [rbp-CAh] BYREF
  __int64 v42; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v43; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v44; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v45; // [rsp+58h] [rbp-A8h]
  __int64 v46; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v47; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v48; // [rsp+70h] [rbp-90h] BYREF
  ULONG pulLength; // [rsp+74h] [rbp-8Ch] BYREF
  DEVNODE pdnDevInst; // [rsp+78h] [rbp-88h] BYREF
  int Buffer; // [rsp+7Ch] [rbp-84h] BYREF
  int v52; // [rsp+80h] [rbp-80h] BYREF
  ULONG v53; // [rsp+84h] [rbp-7Ch] BYREF
  DEVPROPTYPE PropertyType; // [rsp+88h] [rbp-78h] BYREF
  __int128 v55; // [rsp+90h] [rbp-70h] BYREF
  __int64 v56; // [rsp+A0h] [rbp-60h]
  ULONG *v57; // [rsp+A8h] [rbp-58h]
  int *v58; // [rsp+B0h] [rbp-50h]
  _BYTE v59[8]; // [rsp+B8h] [rbp-48h] BYREF
  float v60; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v61; // [rsp+C8h] [rbp-38h]
  __int16 v62; // [rsp+D0h] [rbp-30h]
  _BYTE v63[16]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v64[32]; // [rsp+110h] [rbp+10h] BYREF
  __int64 *v65; // [rsp+150h] [rbp+50h]
  __int64 v66; // [rsp+158h] [rbp+58h]
  ULONG *p_pulLength; // [rsp+160h] [rbp+60h]
  __int64 v68; // [rsp+168h] [rbp+68h]
  __int64 v69; // [rsp+170h] [rbp+70h]
  int v70; // [rsp+178h] [rbp+78h]
  int v71; // [rsp+17Ch] [rbp+7Ch]
  __int64 *v72; // [rsp+180h] [rbp+80h]
  __int64 v73; // [rsp+188h] [rbp+88h]
  WCHAR PropertyBuffer[264]; // [rsp+190h] [rbp+90h] BYREF
  WCHAR pszDeviceInterface[264]; // [rsp+3A0h] [rbp+2A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5F8h] [rbp+4F8h]

  v58 = a3;
  v57 = a2;
  v44 = 0;
  v45 = 0;
  v3 = Windows::Security::Biometrics::FaceSharedUtilites::FaceSensorUtility::QueryAllPossibleHelloFaceCameras(&v44);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\devicestatemanager.cpp",
      (const char *)(unsigned int)v3,
      PropertyBufferSize);
LABEL_3:
    if ( (_QWORD)v44 )
    {
      std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HString>>((HSTRING *)v44, *((HSTRING **)&v44 + 1));
      std::_Deallocate<16>((void *)v44, (v45 - v44) & 0xFFFFFFFFFFFFFFF8uLL);
    }
    return (unsigned int)v4;
  }
  std::unordered_set<std::wstring>::unordered_set<std::wstring>(&v60);
  v6 = (HSTRING *)*((_QWORD *)&v44 + 1);
  v7 = (HSTRING *)v44;
  if ( (_QWORD)v44 != *((_QWORD *)&v44 + 1) )
  {
    while ( 1 )
    {
      v43 = 0;
      v48 = 0;
      Microsoft::WRL::ComPtr<IMFAttributes>::InternalRelease(&v43);
      StringRawBuffer = WindowsGetStringRawBuffer(*v7, 0);
      v4 = MFCreateSensorGroup(StringRawBuffer, &v43);
      if ( v4 < 0 )
        break;
      v4 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v43 + 48LL))(v43, &v48);
      if ( v4 < 0 )
      {
        v37 = 84;
LABEL_53:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v37,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\devicestatemanager.cpp",
          (const char *)(unsigned int)v4,
          PropertyBufferSize);
        goto LABEL_54;
      }
      v9 = 0;
      if ( v48 )
      {
        while ( 1 )
        {
          v46 = 0;
          v10 = v43;
          v11 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v43 + 56LL);
          Microsoft::WRL::ComPtr<IMFAttributes>::InternalRelease(&v46);
          v4 = v11(v10, v9, &v46);
          if ( v4 < 0 )
          {
            v36 = 89;
            goto LABEL_49;
          }
          v39 = 0;
          v4 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v46 + 64LL))(v46, 2, &v39);
          if ( v4 < 0 )
            break;
          for ( i = 0; i < v39; ++i )
          {
            v47 = 0;
            v13 = v46;
            v14 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v46 + 72LL);
            Microsoft::WRL::ComPtr<IMFAttributes>::InternalRelease(&v47);
            v15 = v14(v13, 2, i, &v47);
            v4 = v15;
            if ( v15 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x62,
                (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\devicestatemanager.cpp",
                (const char *)(unsigned int)v15,
                PropertyBufferSize);
              Microsoft::WRL::ComPtr<IMFAttributes>::InternalRelease(&v47);
              goto LABEL_50;
            }
            v42 = 0;
            v16 = (*(int (__fastcall **)(__int64, const GUID *, __int64 *))(*(_QWORD *)v47 + 64LL))(
                    v47,
                    &MF_DEVICESTREAM_ATTRIBUTE_FACEAUTH_CAPABILITY,
                    &v42) < 0;
            v17 = 0;
            if ( !v16 )
              v17 = v42;
            if ( (v17 & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
            {
              memset_0(pszDeviceInterface, 0, 0x208u);
              v52 = 0;
              v18 = (*(__int64 (__fastcall **)(__int64, WCHAR *, __int64, int *))(*(_QWORD *)v46 + 48LL))(
                      v46,
                      pszDeviceInterface,
                      260,
                      &v52);
              if ( v18 >= 0 )
              {
                memset_0(PropertyBuffer, 0, 0x208u);
                v53 = 520;
                PropertyType = 0;
                Device_Interface_PropertyW = CM_Get_Device_Interface_PropertyW(
                                               pszDeviceInterface,
                                               &DEVPKEY_Device_InstanceId,
                                               &PropertyType,
                                               (PBYTE)PropertyBuffer,
                                               &v53,
                                               0);
                if ( Device_Interface_PropertyW )
                {
                  v20 = CM_MapCrToWin32Err(Device_Interface_PropertyW, 0x507u);
                  v22 = v20;
                  if ( v20 > 0 )
                    v22 = (unsigned __int16)v20 | 0x80070000;
                  if ( (unsigned int)dword_18010F170 > 4 )
                  {
                    LODWORD(v42) = v22;
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                      (__int64)&dword_18010F170,
                      (unsigned __int8 *)&dword_1800EF24C,
                      0,
                      v21,
                      (__int64)&v42);
                  }
                  goto LABEL_40;
                }
                std::wstring::wstring((__int64)v64, (__int64)PropertyBuffer);
                v23 = (__int64 **)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(
                                    &v60,
                                    v59,
                                    v64);
                if ( *v23 == v61 )
                {
                  std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
                    &v60,
                    (__int64)v63,
                    (__int64)v64);
                  pdnDevInst = 0;
                  v24 = CM_Locate_DevNodeW(&pdnDevInst, PropertyBuffer, 0);
                  if ( v24 )
                  {
                    v25 = CM_MapCrToWin32Err(v24, 0x507u);
                    v27 = v25;
                    if ( v25 > 0 )
                      v27 = (unsigned __int16)v25 | 0x80070000;
                    if ( (unsigned int)dword_18010F170 > 4 )
                    {
                      v28 = byte_1800EF211;
                      goto LABEL_35;
                    }
                  }
                  else
                  {
                    Buffer = 0;
                    pulLength = 4;
                    DevNode_Registry_PropertyW = CM_Get_DevNode_Registry_PropertyW(
                                                   pdnDevInst,
                                                   0x10u,
                                                   0,
                                                   &Buffer,
                                                   &pulLength,
                                                   0);
                    if ( DevNode_Registry_PropertyW )
                    {
                      v30 = CM_MapCrToWin32Err(DevNode_Registry_PropertyW, 0x507u);
                      v27 = v30;
                      if ( v30 > 0 )
                        v27 = (unsigned __int16)v30 | 0x80070000;
                      if ( (unsigned int)dword_18010F170 > 4 )
                      {
                        v28 = byte_1800EF1D1;
LABEL_35:
                        LODWORD(v42) = v27;
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                          (__int64)&dword_18010F170,
                          (unsigned __int8 *)v28,
                          0,
                          v26,
                          (__int64)&v42);
                      }
                    }
                    else
                    {
                      v31 = v58;
                      if ( (Buffer & 0x400) != 0 )
                        v31 = v57;
                      ++*v31;
                    }
                  }
                }
                std::wstring::_Tidy_deallocate(v64);
                goto LABEL_40;
              }
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x71,
                (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\devicestatemanager.cpp",
                (const char *)(unsigned int)v18,
                PropertyBufferSize);
            }
LABEL_40:
            Microsoft::WRL::ComPtr<IMFAttributes>::InternalRelease(&v47);
          }
          Microsoft::WRL::ComPtr<IMFAttributes>::InternalRelease(&v46);
          if ( ++v9 >= v48 )
            goto LABEL_42;
        }
        v36 = 92;
LABEL_49:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v36,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\devicestatemanager.cpp",
          (const char *)(unsigned int)v4,
          PropertyBufferSize);
LABEL_50:
        Microsoft::WRL::ComPtr<IMFAttributes>::InternalRelease(&v46);
LABEL_54:
        Microsoft::WRL::ComPtr<IMFAttributes>::InternalRelease(&v43);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(&v60);
        goto LABEL_3;
      }
LABEL_42:
      Microsoft::WRL::ComPtr<IMFAttributes>::InternalRelease(&v43);
      if ( ++v7 == v6 )
        goto LABEL_43;
    }
    v37 = 83;
    goto LABEL_53;
  }
LABEL_43:
  v55 = 0;
  v56 = 0;
  v40 = v62;
  std::vector<unsigned char>::insert<unsigned char const *,0>(
    (unsigned int)&v55,
    (unsigned int)v59,
    0,
    (unsigned int)&v40,
    (__int64)v41);
  v32 = v61;
  for ( j = (__int64 *)*v61; j != v32; j = (__int64 *)*j )
  {
    LOWORD(v39) = 2 * *((_WORD *)j + 16);
    std::vector<unsigned char>::insert<unsigned char const *,0>(
      (unsigned int)&v55,
      (unsigned int)v59,
      DWORD2(v55),
      (unsigned int)&v39,
      (__int64)&v39 + 2);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(j + 2);
    v34 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(j + 2);
    std::vector<unsigned char>::insert<unsigned char const *,0>(
      (unsigned int)&v55,
      (unsigned int)&v47,
      DWORD2(v55),
      v35,
      (unsigned __int16)v39 + v34);
  }
  if ( (unsigned int)dword_18010F170 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18010F170, 0x400000000000LL) )
  {
    v47 = 50331648;
    pulLength = *v57;
    LODWORD(v42) = *v58;
    v72 = &v47;
    v73 = 8;
    v69 = v55;
    v70 = (unsigned __int16)(WORD4(v55) - v55);
    v71 = 0;
    p_pulLength = &pulLength;
    v68 = 4;
    v65 = &v42;
    v66 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_18010F170, byte_1800EF14B);
  }
  std::vector<unsigned char>::_Tidy(&v55);
  std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(&v60);
  if ( (_QWORD)v44 )
  {
    std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HString>>((HSTRING *)v44, *((HSTRING **)&v44 + 1));
    std::_Deallocate<16>((void *)v44, (v45 - v44) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  return 0;
}

```

## disassembly

```asm
0x180085e3c  mov     [rsp-8+arg_0], rbx
0x180085e41  push    rbp
0x180085e42  push    rsi
0x180085e43  push    rdi
0x180085e44  push    r12
0x180085e46  push    r13
0x180085e48  push    r14
0x180085e4a  push    r15
0x180085e4c  lea     rbp, [rsp-4C0h]
0x180085e54  sub     rsp, 5C0h
0x180085e5b  mov     rax, cs:__security_cookie
0x180085e62  xor     rax, rsp
0x180085e65  mov     [rbp+4F0h+var_40], rax
0x180085e6c  mov     [rbp+4F0h+var_540], r8
0x180085e70  mov     [rbp+4F0h+var_548], rdx
0x180085e74  xorps   xmm0, xmm0
0x180085e77  movdqu  [rsp+5F0h+var_5A8], xmm0
0x180085e7d  xor     edi, edi
0x180085e7f  mov     [rsp+5F0h+var_598], rdi
0x180085e84  lea     rcx, [rsp+5F0h+var_5A8]
0x180085e89  call    ?QueryAllPossibleHelloFaceCameras@FaceSensorUtility@FaceSharedUtilites@Biometrics@Security@Windows@@SAJPEAV?$vector@VHString@Wrappers@WRL@Microsoft@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@@Z; Windows::Security::Biometrics::FaceSharedUtilites::FaceSensorUtility::QueryAllPossibleHelloFaceCameras(std::vector<Microsoft::WRL::Wrappers::HString> *)
0x180085e8e  mov     ebx, eax
0x180085e90  test    eax, eax
0x180085e92  jns     short loc_180085EDF
0x180085e94  mov     rcx, [rbp+4F8h]; this
0x180085e9b  mov     r9d, eax; char *
0x180085e9e  lea     r8, aOnecoreDsSecur_44; "onecore\\ds\\security\\biometrics\\serv"...
0x180085ea5  lea     edx, [rdi+4Ah]; void *
0x180085ea8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085ead  nop
0x180085eae  mov     rcx, qword ptr [rsp+5F0h+var_5A8]
0x180085eb3  test    rcx, rcx
0x180085eb6  jz      short loc_180085ED8
0x180085eb8  mov     rdx, qword ptr [rsp+5F0h+var_5A8+8]
0x180085ebd  call    ??$_Destroy_range@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@YAXPEAVHString@Wrappers@WRL@Microsoft@@QEAV1234@AEAV?$allocator@VHString@Wrappers@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HString>>(Microsoft::WRL::Wrappers::HString *,Microsoft::WRL::Wrappers::HString * const,std::allocator<Microsoft::WRL::Wrappers::HString> &)
0x180085ec2  mov     rcx, qword ptr [rsp+5F0h+var_5A8]
0x180085ec7  mov     rdx, [rsp+5F0h+var_598]
0x180085ecc  sub     rdx, rcx
0x180085ecf  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180085ed3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180085ed8  mov     eax, ebx
0x180085eda  jmp     loc_1800864F1
0x180085edf  lea     rcx, [rbp+4F0h+var_530]
0x180085ee3  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::wstring>::unordered_set<std::wstring>(void)
0x180085ee8  nop
0x180085ee9  mov     r14, qword ptr [rsp+5F0h+var_5A8]
0x180085eee  mov     r13, qword ptr [rsp+5F0h+var_5A8+8]
0x180085ef3  cmp     r14, r13
0x180085ef6  jz      loc_1800862B9
0x180085efc  lea     rsi, aOnecoreDsSecur_44; "onecore\\ds\\security\\biometrics\\serv"...
0x180085f03  mov     [rsp+5F0h+var_5B0], rdi
0x180085f08  mov     [rsp+5F0h+var_580], edi
0x180085f0c  lea     rcx, [rsp+5F0h+var_5B0]
0x180085f11  call    ?InternalRelease@?$ComPtr@UIMFAttributes@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFAttributes>::InternalRelease(void)
0x180085f16  xor     edx, edx; length
0x180085f18  mov     rcx, [r14]; string
0x180085f1b  call    cs:__imp_WindowsGetStringRawBuffer
0x180085f21  lea     rdx, [rsp+5F0h+var_5B0]
0x180085f26  mov     rcx, rax
0x180085f29  call    cs:__imp_MFCreateSensorGroup
0x180085f2f  mov     ebx, eax
0x180085f31  test    eax, eax
0x180085f33  js      loc_1800863B8
0x180085f39  mov     rcx, [rsp+5F0h+var_5B0]
0x180085f3e  mov     rax, [rcx]
0x180085f41  lea     rdx, [rsp+5F0h+var_580]
0x180085f46  mov     rax, [rax+30h]
0x180085f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085f4f  mov     ebx, eax
0x180085f51  test    eax, eax
0x180085f53  js      loc_1800863B1
0x180085f59  mov     r12d, edi
0x180085f5c  cmp     [rsp+5F0h+var_580], edi
0x180085f60  jbe     loc_1800862A2
0x180085f66  mov     [rsp+5F0h+var_590], rdi
0x180085f6b  mov     rdi, [rsp+5F0h+var_5B0]
0x180085f70  mov     rax, [rdi]
0x180085f73  mov     rbx, [rax+38h]
0x180085f77  lea     rcx, [rsp+5F0h+var_590]
0x180085f7c  call    ?InternalRelease@?$ComPtr@UIMFAttributes@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFAttributes>::InternalRelease(void)
0x180085f81  lea     r8, [rsp+5F0h+var_590]
0x180085f86  mov     edx, r12d
0x180085f89  mov     rcx, rdi
0x180085f8c  mov     rax, rbx
0x180085f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085f94  mov     ebx, eax
0x180085f96  xor     edi, edi
0x180085f98  test    eax, eax
0x180085f9a  js      loc_18008638D
0x180085fa0  mov     [rsp+5F0h+var_5C0], edi
0x180085fa4  mov     rcx, [rsp+5F0h+var_590]
0x180085fa9  mov     rax, [rcx]
0x180085fac  lea     r8, [rsp+5F0h+var_5C0]
0x180085fb1  lea     edx, [rdi+2]
0x180085fb4  mov     rax, [rax+40h]
0x180085fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085fbd  mov     ebx, eax
0x180085fbf  test    eax, eax
0x180085fc1  js      loc_180086386
0x180085fc7  mov     r15d, edi
0x180085fca  cmp     [rsp+5F0h+var_5C0], edi
0x180085fce  jbe     loc_18008628A
0x180085fd4  mov     [rsp+5F0h+var_588], rdi
0x180085fd9  mov     rdi, [rsp+5F0h+var_590]
0x180085fde  mov     rax, [rdi]
0x180085fe1  mov     rbx, [rax+48h]
0x180085fe5  lea     rcx, [rsp+5F0h+var_588]
0x180085fea  call    ?InternalRelease@?$ComPtr@UIMFAttributes@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFAttributes>::InternalRelease(void)
0x180085fef  lea     r9, [rsp+5F0h+var_588]
0x180085ff4  mov     r8d, r15d
0x180085ff7  mov     edx, 2
0x180085ffc  mov     rcx, rdi
0x180085fff  mov     rax, rbx
0x180086002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086007  mov     ebx, eax
0x180086009  xor     edi, edi
0x18008600b  test    eax, eax
0x18008600d  js      loc_180086362
0x180086013  mov     rcx, [rsp+5F0h+var_588]
0x180086018  mov     [rsp+5F0h+var_5B8], rdi
0x18008601d  mov     rax, [rcx]
0x180086020  lea     r8, [rsp+5F0h+var_5B8]
0x180086025  lea     rdx, MF_DEVICESTREAM_ATTRIBUTE_FACEAUTH_CAPABILITY
0x18008602c  mov     rax, [rax+40h]
0x180086030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086035  test    eax, eax
0x180086037  mov     eax, edi
0x180086039  js      short loc_180086040
0x18008603b  mov     rax, [rsp+5F0h+var_5B8]
0x180086040  test    rax, 0FFFFFFFFFFFFFFFEh
0x180086046  jz      loc_180086272
0x18008604c  mov     ebx, 208h
0x180086051  mov     r8d, ebx; Size
0x180086054  xor     edx, edx; Val
0x180086056  lea     rcx, [rbp+4F0h+pszDeviceInterface]; void *
0x18008605d  call    memset_0
0x180086062  mov     [rbp+4F0h+var_570], edi
0x180086065  mov     rcx, [rsp+5F0h+var_590]
0x18008606a  mov     rax, [rcx]
0x18008606d  lea     r9, [rbp+4F0h+var_570]
0x180086071  mov     r8d, 104h
0x180086077  lea     rdx, [rbp+4F0h+pszDeviceInterface]
0x18008607e  mov     rax, [rax+30h]
0x180086082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086087  mov     rcx, [rbp+4F8h]; this
0x18008608e  test    eax, eax
0x180086090  jns     short loc_1800860A7
0x180086092  mov     r9d, eax; char *
0x180086095  mov     r8, rsi; unsigned int
0x180086098  mov     edx, 71h ; 'q'; void *
0x18008609d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800860a2  jmp     loc_180086272
0x1800860a7  mov     r8, rbx; Size
0x1800860aa  xor     edx, edx; Val
0x1800860ac  lea     rcx, [rbp+4F0h+PropertyBuffer]; void *
0x1800860b3  call    memset_0
0x1800860b8  mov     [rbp+4F0h+var_56C], ebx
0x1800860bb  mov     [rbp+4F0h+PropertyType], edi
0x1800860be  mov     [rsp+5F0h+ulFlags], edi; ulFlags
0x1800860c2  lea     rax, [rbp+4F0h+var_56C]
0x1800860c6  mov     [rsp+5F0h+PropertyBufferSize], rax; PropertyBufferSize
0x1800860cb  lea     r9, [rbp+4F0h+PropertyBuffer]; PropertyBuffer
0x1800860d2  lea     r8, [rbp+4F0h+PropertyType]; PropertyType
0x1800860d6  lea     rdx, DEVPKEY_Device_InstanceId; PropertyKey
0x1800860dd  lea     rcx, [rbp+4F0h+pszDeviceInterface]; pszDeviceInterface
0x1800860e4  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x1800860ea  test    eax, eax
0x1800860ec  jz      short loc_180086142
0x1800860ee  mov     edx, 507h; DefaultErr
0x1800860f3  mov     ecx, eax; CmReturnCode
0x1800860f5  call    cs:__imp_CM_MapCrToWin32Err
0x1800860fb  mov     ecx, eax
0x1800860fd  test    eax, eax
0x1800860ff  jle     short loc_18008610A
0x180086101  movzx   ecx, ax
0x180086104  or      ecx, 80070000h
0x18008610a  mov     eax, cs:dword_18010F170
0x180086110  cmp     eax, 4
0x180086113  jbe     loc_180086272
0x180086119  mov     dword ptr [rsp+5F0h+var_5B8], ecx
0x18008611d  lea     rax, [rsp+5F0h+var_5B8]
0x180086122  mov     [rsp+5F0h+PropertyBufferSize], rax
0x180086127  xor     r8d, r8d
0x18008612a  lea     rdx, dword_1800EF24C
0x180086131  lea     rcx, dword_18010F170
0x180086138  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18008613d  jmp     loc_180086272
0x180086142  lea     rdx, [rbp+4F0h+PropertyBuffer]
0x180086149  lea     rcx, [rbp+4F0h+var_4E0]
0x18008614d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180086152  nop
0x180086153  lea     r8, [rbp+4F0h+var_4E0]
0x180086157  lea     rdx, [rbp+4F0h+var_538]
0x18008615b  lea     rcx, [rbp+4F0h+var_530]
0x18008615f  call    ?find@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x180086164  mov     rcx, [rbp+4F0h+var_528]
0x180086168  cmp     [rax], rcx
0x18008616b  jnz     loc_180086268
0x180086171  lea     r8, [rbp+4F0h+var_4E0]
0x180086175  lea     rdx, [rbp+4F0h+var_4F0]
0x180086179  lea     rcx, [rbp+4F0h+var_530]
0x18008617d  call    ??$emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(std::wstring const &)
0x180086182  mov     [rsp+5F0h+pdnDevInst], edi
0x180086186  xor     r8d, r8d; ulFlags
0x180086189  lea     rdx, [rbp+4F0h+PropertyBuffer]; pDeviceID
0x180086190  lea     rcx, [rsp+5F0h+pdnDevInst]; pdnDevInst
0x180086195  call    cs:__imp_CM_Locate_DevNodeW
0x18008619b  test    eax, eax
0x18008619d  jz      short loc_1800861D3
0x18008619f  mov     edx, 507h; DefaultErr
0x1800861a4  mov     ecx, eax; CmReturnCode
0x1800861a6  call    cs:__imp_CM_MapCrToWin32Err
0x1800861ac  mov     ecx, eax
0x1800861ae  test    eax, eax
0x1800861b0  jle     short loc_1800861BB
0x1800861b2  movzx   ecx, ax
0x1800861b5  or      ecx, 80070000h
0x1800861bb  mov     eax, cs:dword_18010F170
0x1800861c1  cmp     eax, 4
0x1800861c4  jbe     loc_180086268
0x1800861ca  lea     rdx, byte_1800EF211
0x1800861d1  jmp     short loc_180086235
0x1800861d3  mov     [rsp+5F0h+Buffer], edi
0x1800861d7  mov     [rsp+5F0h+pulLength], 4
0x1800861df  mov     [rsp+5F0h+ulFlags], edi; ulFlags
0x1800861e3  lea     rax, [rsp+5F0h+pulLength]
0x1800861e8  mov     [rsp+5F0h+PropertyBufferSize], rax; pulLength
0x1800861ed  lea     r9, [rsp+5F0h+Buffer]; Buffer
0x1800861f2  xor     r8d, r8d; pulRegDataType
0x1800861f5  lea     edx, [r8+10h]; ulProperty
0x1800861f9  mov     ecx, [rsp+5F0h+pdnDevInst]; dnDevInst
0x1800861fd  call    cs:__imp_CM_Get_DevNode_Registry_PropertyW
0x180086203  test    eax, eax
0x180086205  jz      short loc_180086254
0x180086207  mov     edx, 507h; DefaultErr
0x18008620c  mov     ecx, eax; CmReturnCode
0x18008620e  call    cs:__imp_CM_MapCrToWin32Err
0x180086214  mov     ecx, eax
0x180086216  test    eax, eax
0x180086218  jle     short loc_180086223
0x18008621a  movzx   ecx, ax
0x18008621d  or      ecx, 80070000h
0x180086223  mov     eax, cs:dword_18010F170
0x180086229  cmp     eax, 4
0x18008622c  jbe     short loc_180086268
0x18008622e  lea     rdx, byte_1800EF1D1
0x180086235  lea     rax, [rsp+5F0h+var_5B8]
0x18008623a  xor     r8d, r8d
0x18008623d  mov     [rsp+5F0h+PropertyBufferSize], rax
0x180086242  mov     dword ptr [rsp+5F0h+var_5B8], ecx
0x180086246  lea     rcx, dword_18010F170
0x18008624d  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180086252  jmp     short loc_180086268
0x180086254  test    [rsp+5F0h+Buffer], 400h
0x18008625c  mov     rax, [rbp+4F0h+var_540]
0x180086260  jz      short loc_180086266
0x180086262  mov     rax, [rbp+4F0h+var_548]
0x180086266  inc     dword ptr [rax]
0x180086268  lea     rcx, [rbp+4F0h+var_4E0]
0x18008626c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180086271  nop
0x180086272  lea     rcx, [rsp+5F0h+var_588]
0x180086277  call    ?InternalRelease@?$ComPtr@UIMFAttributes@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFAttributes>::InternalRelease(void)
0x18008627c  inc     r15d
0x18008627f  cmp     r15d, [rsp+5F0h+var_5C0]
0x180086284  jb      loc_180085FD4
0x18008628a  lea     rcx, [rsp+5F0h+var_590]
0x18008628f  call    ?InternalRelease@?$ComPtr@UIMFAttributes@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFAttributes>::InternalRelease(void)
0x180086294  inc     r12d
0x180086297  cmp     r12d, [rsp+5F0h+var_580]
0x18008629c  jb      loc_180085F66
0x1800862a2  lea     rcx, [rsp+5F0h+var_5B0]
0x1800862a7  call    ?InternalRelease@?$ComPtr@UIMFAttributes@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFAttributes>::InternalRelease(void)
0x1800862ac  add     r14, 8
0x1800862b0  cmp     r14, r13
0x1800862b3  jnz     loc_180085F03
0x1800862b9  xorps   xmm0, xmm0
0x1800862bc  movdqu  [rbp+4F0h+var_560], xmm0
0x1800862c1  mov     [rbp+4F0h+var_550], rdi
0x1800862c5  movzx   eax, [rbp+4F0h+var_520]
0x1800862c9  mov     [rsp+5F0h+var_5BC], ax
0x1800862ce  xor     r8d, r8d
0x1800862d1  lea     rax, [rsp+5F0h+var_5BA]
0x1800862d6  mov     [rsp+5F0h+PropertyBufferSize], rax
0x1800862db  lea     r9, [rsp+5F0h+var_5BC]
0x1800862e0  lea     rdx, [rbp+4F0h+var_538]
0x1800862e4  lea     rcx, [rbp+4F0h+var_560]
0x1800862e8  call    ??$insert@PEBE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEBE1@Z; std::vector<uchar>::insert<uchar const *,0>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar const *,uchar const *)
0x1800862ed  mov     rsi, [rbp+4F0h+var_528]
0x1800862f1  mov     rbx, [rsi]
0x1800862f4  cmp     rbx, rsi
0x1800862f7  jz      loc_1800863E9
0x1800862fd  movzx   eax, word ptr [rbx+20h]
0x180086301  add     ax, ax
0x180086304  mov     word ptr [rsp+5F0h+var_5C0], ax
0x180086309  lea     rax, [rsp+5F0h+var_5C0+2]
0x18008630e  mov     [rsp+5F0h+PropertyBufferSize], rax
0x180086313  lea     r9, [rsp+5F0h+var_5C0]
0x180086318  mov     r8, qword ptr [rbp+4F0h+var_560+8]
0x18008631c  lea     rdx, [rbp+4F0h+var_538]
  ... truncated ...
```
