# _anonymous_namespace_::LazyData::LazyData

- ea: `0x14006fd90`
- end: `0x140070a96`
- name: `_anonymous_namespace_::LazyData::LazyData`
- size: `3334`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140073d00`

## callees

- `0x140005530`
- `0x140006308`
- `0x140006338`
- `0x140009858`
- `0x14000b814`
- `0x14000ccac`
- `0x14001c804`
- `0x14001f6b4`
- `0x14002f828`
- `0x140035800`
- `0x140060498`
- `0x140060e60`
- `0x140060f58`
- `0x14006fd90`
- `0x1400716a4`
- `0x140071c5c`
- `0x1400723b8`
- `0x14007aaf4`
- `0x140081af0`
- `0x140081b44`
- `0x1400a8010`

## import_xrefs

- `SHLWAPI!SHCreateStreamOnFileEx` at `0x14006ff34`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x14006ff34`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14006ff87`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140070216`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14006ff87`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140070216`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140070584`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140070597`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140070609`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14007068d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400706a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140070584`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140070597`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140070609`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14007068d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400706a1`

## string_xrefs

- `0x14006fede`: `AppxManifest.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=32
_QWORD *__fastcall anonymous_namespace_::LazyData::LazyData(_OWORD *a1, LPVOID *a2, char **a3)
{
  char **v3; // r15
  _QWORD *v4; // r13
  unsigned __int64 *v5; // rcx
  _QWORD *v6; // r12
  __int64 v7; // rax
  HRESULT v8; // ebx
  HRESULT v9; // ebx
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64); // rbx
  __int64 v15; // rdx
  int v16; // ebx
  _BYTE *v17; // rdx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64); // rbx
  __int64 v20; // rdx
  int v21; // ebx
  _BYTE *v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rcx
  LPVOID v25; // rcx
  IStream *v26; // rcx
  HRESULT v27; // ebx
  LPVOID *v28; // rbx
  _QWORD *v29; // rdx
  LPVOID v30; // rdi
  _QWORD *v31; // rax
  int v32; // edi
  int v33; // edi
  __int64 v34; // rcx
  __int64 v35; // rbx
  _QWORD *v36; // rdi
  __int64 v37; // rax
  __int64 v38; // rax
  void *v39; // r9
  unsigned __int64 v40; // rdi
  unsigned __int64 v41; // rdx
  char *v42; // r14
  __int64 v43; // rbx
  __int64 v44; // r8
  void *v45; // r9
  void **v46; // rax
  void *v47; // rdx
  void *v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rcx
  LPVOID v52; // rcx
  __int64 v53; // rcx
  __int64 v55; // rax
  int v56; // eax
  __int64 v57; // r10
  __int64 v58; // rax
  int v59; // eax
  __int64 v60; // r10
  __int64 v61; // rax
  int v62; // eax
  __int64 v63; // r10
  __int64 v64; // rax
  int v65; // eax
  __int64 v66; // r10
  __int64 v67; // rax
  int v68; // eax
  __int64 v69; // r10
  int v70; // eax
  __int64 v71; // r10
  unsigned int v72; // eax
  LPVOID v73; // rcx
  __int64 v74; // rcx
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // r8
  LPVOID v78; // [rsp+30h] [rbp-3B8h] BYREF
  __int64 v79; // [rsp+38h] [rbp-3B0h] BYREF
  __int64 v80; // [rsp+40h] [rbp-3A8h] BYREF
  __int64 v81; // [rsp+48h] [rbp-3A0h] BYREF
  __int64 v82; // [rsp+50h] [rbp-398h] BYREF
  __int64 v83; // [rsp+58h] [rbp-390h] BYREF
  __int64 v84; // [rsp+60h] [rbp-388h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-380h] BYREF
  IStream *ppstm; // [rsp+70h] [rbp-378h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-370h] BYREF
  LPVOID *v88; // [rsp+80h] [rbp-368h]
  _OWORD *v89; // [rsp+88h] [rbp-360h]
  _QWORD *v90; // [rsp+90h] [rbp-358h]
  void *Src; // [rsp+98h] [rbp-350h] BYREF
  void *v92; // [rsp+A0h] [rbp-348h] BYREF
  _QWORD *v93; // [rsp+A8h] [rbp-340h]
  _QWORD *v94; // [rsp+B0h] [rbp-338h]
  _QWORD *v95; // [rsp+B8h] [rbp-330h]
  _QWORD *v96; // [rsp+C0h] [rbp-328h]
  LPVOID *v97; // [rsp+C8h] [rbp-320h]
  unsigned __int64 *v98; // [rsp+D0h] [rbp-318h]
  unsigned __int64 *v99; // [rsp+D8h] [rbp-310h]
  unsigned __int64 *v100; // [rsp+E0h] [rbp-308h]
  LPVOID v101[2]; // [rsp+E8h] [rbp-300h] BYREF
  _QWORD v102[3]; // [rsp+F8h] [rbp-2F0h] BYREF
  const std::exception *v103; // [rsp+110h] [rbp-2D8h] BYREF
  const std::exception *v104; // [rsp+118h] [rbp-2D0h] BYREF
  const std::exception *v105; // [rsp+120h] [rbp-2C8h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+128h] [rbp-2C0h] BYREF
  _BYTE v107[40]; // [rsp+150h] [rbp-298h] BYREF
  _BYTE v108[40]; // [rsp+178h] [rbp-270h] BYREF
  _BYTE v109[40]; // [rsp+1A0h] [rbp-248h] BYREF
  _BYTE v110[40]; // [rsp+1C8h] [rbp-220h] BYREF
  _BYTE v111[40]; // [rsp+1F0h] [rbp-1F8h] BYREF
  _BYTE v112[40]; // [rsp+218h] [rbp-1D0h] BYREF
  _BYTE v113[40]; // [rsp+240h] [rbp-1A8h] BYREF
  _BYTE v114[40]; // [rsp+268h] [rbp-180h] BYREF
  _BYTE v115[40]; // [rsp+290h] [rbp-158h] BYREF
  char **v116; // [rsp+2B8h] [rbp-130h]
  __int128 v117; // [rsp+2C0h] [rbp-128h] BYREF
  LPVOID *p_pv; // [rsp+2D0h] [rbp-118h]
  LPVOID *v119; // [rsp+2D8h] [rbp-110h]
  char *v120[4]; // [rsp+2E0h] [rbp-108h] BYREF
  __int64 v121; // [rsp+300h] [rbp-E8h] BYREF
  _BYTE v122[56]; // [rsp+308h] [rbp-E0h] BYREF
  _BYTE *v123; // [rsp+340h] [rbp-A8h]
  __int64 v124; // [rsp+350h] [rbp-98h] BYREF
  _BYTE v125[56]; // [rsp+358h] [rbp-90h] BYREF
  _BYTE *v126; // [rsp+390h] [rbp-58h]

  v3 = a3;
  v88 = a2;
  v4 = a1;
  v89 = a1;
  v97 = a2;
  v116 = a3;
  *a1 = 0;
  v99 = (unsigned __int64 *)(a1 + 1);
  v5 = (unsigned __int64 *)a1 + 3;
  v98 = v5;
  *v99 = 0;
  *v5 = 7;
  *(_WORD *)v4 = 0;
  v94 = v4 + 4;
  *((_OWORD *)v4 + 2) = 0;
  v4[6] = 0;
  v4[7] = 7;
  *((_WORD *)v4 + 16) = 0;
  *((_OWORD *)v4 + 4) = 0;
  v4[10] = 0;
  v4[11] = 7;
  *((_WORD *)v4 + 32) = 0;
  v6 = v4 + 12;
  v90 = v4 + 12;
  *((_OWORD *)v4 + 6) = 0;
  v101[0] = v4 + 14;
  v100 = v4 + 15;
  v4[14] = 0;
  v4[15] = 7;
  *((_WORD *)v4 + 48) = 0;
  v95 = v4 + 16;
  v117 = 0;
  p_pv = 0;
  v119 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)&v117, &SubKey, 0);
  IO::Path::Path((__int64)(v4 + 16), (__int64)&v117);
  v92 = 0;
  Src = 0;
  v81 = 0;
  ppstm = 0;
  std::wstring::wstring(&v117, L"AppxManifest.xml");
  v7 = IO::operator/(v120, v3, &v117);
  if ( *(_QWORD *)(v7 + 24) > 7u )
    v7 = *(_QWORD *)v7;
  v8 = SHCreateStreamOnFileEx((LPCWSTR)v7, 0x20u, 0x80u, 0, 0, &ppstm);
  std::wstring::~wstring(v120);
  std::wstring::~wstring((char **)&v117);
  if ( v8 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v55 = std::array<unsigned short,16>::data(v3);
      v56 = std::wstring::c_str(v55);
      WPP_SF_Sd(*(_QWORD *)(v57 + 16), 31, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v56, v8);
    }
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v8);
    throw (ErrorCodeException *)pExceptionObject;
  }
  ppv = 0;
  v9 = CoCreateInstance(
         &GUID_5842a140_ff9f_4166_8f5c_62f5b7b0c781,
         0,
         1u,
         &GUID_beb94909_e451_438b_b5a7_d79e767b75d8,
         &ppv);
  if ( v9 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        32,
        WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids,
        (unsigned int)v9);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)v107, v9);
    throw (ErrorCodeException *)v107;
  }
  v83 = 0;
  v10 = (*(__int64 (__fastcall **)(LPVOID, IStream *, __int64 *))(*(_QWORD *)ppv + 40LL))(ppv, ppstm, &v83);
  if ( v10 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v58 = std::array<unsigned short,16>::data(v3);
      v59 = std::wstring::c_str(v58);
      WPP_SF_Sd(*(_QWORD *)(v60 + 16), 33, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v59, v10);
    }
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)v108, v10);
    throw (ErrorCodeException *)v108;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v83 + 32LL))(v83, &v81);
  if ( v11 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v61 = std::array<unsigned short,16>::data(v3);
      v62 = std::wstring::c_str(v61);
      WPP_SF_Sd(*(_QWORD *)(v63 + 16), 34, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v62, v11);
    }
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)v109, v11);
    throw (ErrorCodeException *)v109;
  }
  v82 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v83 + 24LL))(v83, &v82);
  if ( v12 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v64 = std::array<unsigned short,16>::data(v3);
      v65 = std::wstring::c_str(v64);
      WPP_SF_Sd(*(_QWORD *)(v66 + 16), 35, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v65, v12);
    }
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)v110, v12);
    throw (ErrorCodeException *)v110;
  }
  v13 = v82;
  v14 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v82 + 24LL);
  v15 = stdext::get_pointer<std::unique_ptr<unsigned short,ComDeallocator>>((__int64)&v121, (__int64)&Src);
  v16 = v14(v13, v15);
  if ( v123 )
  {
    v84 = v121;
    (*(void (__fastcall **)(_BYTE *, __int64 *))(*(_QWORD *)v123 + 16LL))(v123, &v84);
    if ( v123 )
    {
      v17 = v122;
      LOBYTE(v17) = v123 != v122;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v123 + 32LL))(v123, v17);
    }
  }
  if ( v16 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        36,
        WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids,
        (unsigned int)v16);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)v111, v16);
    throw (ErrorCodeException *)v111;
  }
  v18 = v82;
  v19 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v82 + 40LL);
  v20 = stdext::get_pointer<std::unique_ptr<unsigned short,ComDeallocator>>((__int64)&v124, (__int64)&v92);
  v21 = v19(v18, v20);
  if ( v126 )
  {
    v84 = v124;
    (*(void (__fastcall **)(_BYTE *, __int64 *))(*(_QWORD *)v126 + 16LL))(v126, &v84);
    if ( v126 )
    {
      v22 = v125;
      LOBYTE(v22) = v126 != v125;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v126 + 32LL))(v126, v22);
    }
  }
  if ( v21 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        37,
        WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids,
        (unsigned int)v21);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)v112, v21);
    throw (ErrorCodeException *)v112;
  }
  v96 = v94;
  v93 = v4 + 8;
  v23 = v82;
  if ( v82 )
  {
    v82 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  v24 = v83;
  if ( v83 )
  {
    v83 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  v25 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v25 + 16LL))(v25);
  }
  v26 = ppstm;
  if ( ppstm )
  {
    ppstm = 0;
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v26 + 16LL))(v26);
  }
  try
  {
    v78 = 0;
    v80 = 0;
    v79 = 0;
    v27 = CoCreateInstance(
            &GUID_dbce7e40_7345_439d_b12c_114a11819a09,
            0,
            1u,
            &GUID_130a2f65_2be7_4309_9a58_a9052ff2b61c,
            &v78);
    if ( v27 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          38,
          WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids,
          (unsigned int)v27);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)v113, v27);
      throw (ErrorCodeException *)v113;
    }
    v28 = v88;
    if ( (unsigned __int64)v88[3] <= 7 )
      v29 = v88;
    else
      v29 = *v88;
    if ( (*(int (__fastcall **)(LPVOID, _QWORD *))(*(_QWORD *)v78 + 40LL))(v78, v29) < 0 )
    {
      v30 = v78;
      v84 = *(_QWORD *)v78;
      std::wstring::wstring(&v117, L"resources.pri");
      v31 = (_QWORD *)IO::operator/(v120, v3, &v117);
      if ( v31[3] > 7u )
        v31 = (_QWORD *)*v31;
      v32 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *))(v84 + 48))(v30, v31);
      std::wstring::~wstring(v120);
      std::wstring::~wstring((char **)&v117);
      if ( v32 < 0 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v67 = std::array<unsigned short,16>::data(v3);
          v68 = std::wstring::c_str(v67);
          WPP_SF_Sd(*(_QWORD *)(v69 + 16), 39, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v68, v32);
        }
        ErrorCodeException::ErrorCodeException((ErrorCodeException *)v114, v32);
        throw (ErrorCodeException *)v114;
      }
    }
    v33 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64 *))(*(_QWORD *)v78 + 56LL))(
            v78,
            &GUID_6e21e72b_b9b0_42ae_a686_983cf784edcd,
            &v80);
    if ( v33 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v70 = std::wstring::c_str(v28);
        WPP_SF_Sd(*(_QWORD *)(v71 + 16), 40, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v70, v33);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)v115, v33);
      throw (ErrorCodeException *)v115;
    }
    if ( (*(int (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v80 + 32LL))(v80, L"Resources", &v79) < 0 )
    {
      v34 = v79;
      v35 = v80;
      if ( v79 != v80 )
      {
        if ( v80 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 8LL))(v80);
          v34 = v79;
        }
        v79 = v35;
        if ( v34 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      }
      v28 = v88;
    }
    v36 = v94;
  }
  catch ( const std::exception *v103 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v72 = ErrorCodeFromException(v103);
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 41, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v72);
    }
    v73 = v78;
    if ( v78 )
    {
      v78 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v73 + 16LL))(v73);
    }
    v74 = v79;
    if ( v79 )
    {
      v79 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
    }
    v36 = v96;
    v28 = v97;
    v4 = v89;
    v3 = v116;
    v6 = v90;
  }
  try
  {
    v102[0] = &v81;
    v102[1] = v28;
    v102[2] = &v78;
    *(_QWORD *)&v117 = v102;
    *((_QWORD *)&v117 + 1) = &v80;
    p_pv = v28;
    v119 = &v78;
    v37 = lambda_71aecd3417d7b7ddb55d9f1c3553005b_::operator()(&v117, v120, L"DisplayName");
    std::wstring::operator=(v36, v37);
    std::wstring::~wstring(v120);
  }
  catch ( const std::exception *v104 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v75 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v104 + 8LL))(v104);
      WPP_SF_s(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 48, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v75);
    }
    v4 = v89;
    v3 = v116;
    v6 = v90;
  }
  try
  {
    v38 = lambda_71aecd3417d7b7ddb55d9f1c3553005b_::operator()(&v117, v120, L"PublisherDisplayName");
    std::wstring::operator=(v93, v38);
    std::wstring::~wstring(v120);
  }
  catch ( const std::exception *v105 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v76 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v105 + 8LL))(v105);
      WPP_SF_s(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 49, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v76);
    }
    v4 = v89;
    v3 = v116;
    v6 = v90;
  }
  v39 = Src;
  v40 = -1;
  v41 = -1;
  do
    ++v41;
  while ( *((_WORD *)Src + v41) );
  if ( v41 > *v98 )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v4, v41, v77, Src);
  }
  else
  {
    if ( *v98 <= 7 )
      v42 = (char *)v4;
    else
      v42 = (char *)*v4;
    *v99 = v41;
    v43 = 2 * v41;
    memmove_0(v42, v39, 2 * v41);
    *(_WORD *)&v42[v43] = 0;
  }
  v45 = v92;
  do
    ++v40;
  while ( *((_WORD *)v92 + v40) );
  if ( v40 > *v100 )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v6, v40, v44, v92);
  }
  else
  {
    if ( *v100 > 7 )
      v6 = (_QWORD *)*v6;
    *(_QWORD *)v101[0] = v40;
    memmove_0(v6, v45, 2 * v40);
    *((_WORD *)v6 + v40) = 0;
  }
  pv = 0;
  v46 = (void **)lambda_d40de2733d855246ee074aa8c091e9f3_::operator()(v102, v101, L"Logo");
  v47 = *v46;
  *v46 = 0;
  v48 = pv;
  pv = v47;
  if ( v48 )
    CoTaskMemFree(v48);
  if ( v101[0] )
    CoTaskMemFree(v101[0]);
  *(_QWORD *)&v117 = &v78;
  *((_QWORD *)&v117 + 1) = &v80;
  p_pv = &pv;
  v119 = (LPVOID *)v3;
  v49 = lambda_522f252fccf6755638ce70b922f17e30_::operator()(&v117, v120);
  std::wstring::operator=(v95, v49);
  std::wstring::~wstring(v120);
  if ( pv )
    CoTaskMemFree(pv);
  v50 = v79;
  if ( v79 )
  {
    v79 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
  }
  v51 = v80;
  if ( v80 )
  {
    v80 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
  }
  v52 = v78;
  if ( v78 )
  {
    v78 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v52 + 16LL))(v52);
  }
  v53 = v81;
  if ( v81 )
  {
    v81 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
  }
  if ( Src )
    CoTaskMemFree(Src);
  if ( v92 )
    CoTaskMemFree(v92);
  std::wstring::~wstring(v3);
  return v4;
}

```

## disassembly

```asm
0x14006fd90  mov     r11, rsp
0x14006fd93  push    rbx
0x14006fd94  push    rsi
0x14006fd95  push    rdi
0x14006fd96  push    r12
0x14006fd98  push    r13
0x14006fd9a  push    r14
0x14006fd9c  push    r15
0x14006fd9e  sub     rsp, 3B0h
0x14006fda5  mov     rax, cs:__security_cookie
0x14006fdac  xor     rax, rsp
0x14006fdaf  mov     [rsp+3E8h+var_48], rax
0x14006fdb7  mov     r15, r8
0x14006fdba  mov     [rsp+3E8h+var_368], rdx
0x14006fdc2  mov     r13, rcx
0x14006fdc5  mov     [r11-360h], rcx
0x14006fdcc  mov     [rsp+3E8h+var_320], rdx
0x14006fdd4  mov     [r11-130h], r8
0x14006fddb  xorps   xmm0, xmm0
0x14006fdde  movups  xmmword ptr [rcx], xmm0
0x14006fde1  lea     rax, [rcx+10h]
0x14006fde5  mov     [rsp+3E8h+var_310], rax
0x14006fded  add     rcx, 18h
0x14006fdf1  mov     [rsp+3E8h+var_318], rcx
0x14006fdf9  xor     esi, esi
0x14006fdfb  mov     [rax], rsi
0x14006fdfe  mov     qword ptr [rcx], 7
0x14006fe05  mov     [r13+0], si
0x14006fe0a  lea     rax, [r13+20h]
0x14006fe0e  mov     [rsp+3E8h+var_338], rax
0x14006fe16  movups  xmmword ptr [rax], xmm0
0x14006fe19  mov     [rax+10h], rsi
0x14006fe1d  mov     qword ptr [rax+18h], 7
0x14006fe25  mov     [rax], si
0x14006fe28  movups  xmmword ptr [r13+40h], xmm0
0x14006fe2d  mov     [r13+50h], rsi
0x14006fe31  mov     qword ptr [r13+58h], 7
0x14006fe39  mov     [r13+40h], si
0x14006fe3e  lea     r12, [r13+60h]
0x14006fe42  mov     [rsp+3E8h+var_358], r12
0x14006fe4a  movups  xmmword ptr [r12], xmm0
0x14006fe4f  lea     rcx, [r12+10h]
0x14006fe54  mov     [rsp+3E8h+var_300], rcx
0x14006fe5c  lea     rax, [r12+18h]
0x14006fe61  mov     [rsp+3E8h+var_308], rax
0x14006fe69  mov     [rcx], rsi
0x14006fe6c  mov     qword ptr [rax], 7
0x14006fe73  mov     [r12], si
0x14006fe78  lea     rbx, [r13+80h]
0x14006fe7f  mov     [rsp+3E8h+var_330], rbx
0x14006fe87  movups  [rsp+3E8h+var_128], xmm0
0x14006fe8f  mov     [r11-118h], rsi
0x14006fe96  mov     [r11-110h], rsi
0x14006fe9d  xor     r8d, r8d
0x14006fea0  lea     rdx, SubKey
0x14006fea7  lea     rcx, [r11-128h]
0x14006feae  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14006feb3  lea     rdx, [rsp+3E8h+var_128]
0x14006febb  mov     rcx, rbx
0x14006febe  call    ??0Path@IO@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IO::Path::Path(std::wstring)
0x14006fec3  nop
0x14006fec4  mov     [rsp+3E8h+var_348], rsi
0x14006fecc  mov     [rsp+3E8h+Src], rsi
0x14006fed4  mov     [rsp+3E8h+var_3A0], rsi
0x14006fed9  mov     [rsp+3E8h+var_378], rsi
0x14006fede  lea     rdx, aAppxmanifestXm; "AppxManifest.xml"
0x14006fee5  lea     rcx, [rsp+3E8h+var_128]
0x14006feed  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14006fef2  nop
0x14006fef3  lea     r8, [rsp+3E8h+var_128]
0x14006fefb  mov     rdx, r15
0x14006fefe  lea     rcx, [rsp+3E8h+var_108]
0x14006ff06  call    ??KIO@@YA?AVPath@0@AEBV10@0@Z; IO::operator/(IO::Path const &,IO::Path const &)
0x14006ff0b  cmp     qword ptr [rax+18h], 7
0x14006ff10  jbe     short loc_14006FF15
0x14006ff12  mov     rax, [rax]
0x14006ff15  lea     rcx, [rsp+3E8h+var_378]
0x14006ff1a  mov     [rsp+3E8h+ppstm], rcx; ppstm
0x14006ff1f  mov     [rsp+3E8h+pstmTemplate], rsi; pstmTemplate
0x14006ff24  xor     r9d, r9d; fCreate
0x14006ff27  lea     edi, [r9+20h]
0x14006ff2b  lea     r8d, [rdi+60h]; dwAttributes
0x14006ff2f  mov     edx, edi; grfMode
0x14006ff31  mov     rcx, rax; pszFile
0x14006ff34  call    cs:__imp_SHCreateStreamOnFileEx
0x14006ff3a  mov     ebx, eax
0x14006ff3c  lea     rcx, [rsp+3E8h+var_108]
0x14006ff44  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14006ff49  nop
0x14006ff4a  lea     rcx, [rsp+3E8h+var_128]
0x14006ff52  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14006ff57  test    ebx, ebx
0x14006ff59  js      loc_1400706D6
0x14006ff5f  mov     [rsp+3E8h+ppv], rsi
0x14006ff64  lea     rax, [rsp+3E8h+ppv]
0x14006ff69  mov     [rsp+3E8h+pstmTemplate], rax; ppv
0x14006ff6e  lea     r9, _GUID_beb94909_e451_438b_b5a7_d79e767b75d8; riid
0x14006ff75  mov     r14d, 1
0x14006ff7b  mov     r8d, r14d; dwClsContext
0x14006ff7e  xor     edx, edx; pUnkOuter
0x14006ff80  lea     rcx, _GUID_5842a140_ff9f_4166_8f5c_62f5b7b0c781; rclsid
0x14006ff87  call    cs:__imp_CoCreateInstance
0x14006ff8d  mov     ebx, eax
0x14006ff8f  test    eax, eax
0x14006ff91  js      loc_140070741
0x14006ff97  mov     [rsp+3E8h+var_390], rsi
0x14006ff9c  mov     rcx, [rsp+3E8h+ppv]
0x14006ffa1  mov     rax, [rcx]
0x14006ffa4  lea     r8, [rsp+3E8h+var_390]
0x14006ffa9  mov     rdx, [rsp+3E8h+var_378]
0x14006ffae  mov     rax, [rax+28h]
0x14006ffb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006ffb7  mov     ebx, eax
0x14006ffb9  test    eax, eax
0x14006ffbb  js      loc_140070793
0x14006ffc1  mov     rbx, [rsp+3E8h+var_390]
0x14006ffc6  mov     rax, [rbx]
0x14006ffc9  mov     rdi, [rax+20h]
0x14006ffcd  mov     rcx, [rsp+3E8h+var_3A0]
0x14006ffd2  test    rcx, rcx
0x14006ffd5  jz      short loc_14006FFE9
0x14006ffd7  mov     [rsp+3E8h+var_3A0], rsi
0x14006ffdc  mov     rax, [rcx]
0x14006ffdf  mov     rax, [rax+10h]
0x14006ffe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006ffe8  nop
0x14006ffe9  lea     rdx, [rsp+3E8h+var_3A0]
0x14006ffee  mov     rcx, rbx
0x14006fff1  mov     rax, rdi
0x14006fff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006fff9  mov     ebx, eax
0x14006fffb  test    eax, eax
0x14006fffd  js      loc_1400707FC
0x140070003  mov     [rsp+3E8h+var_398], rsi
0x140070008  mov     rcx, [rsp+3E8h+var_390]
0x14007000d  mov     rax, [rcx]
0x140070010  lea     rdx, [rsp+3E8h+var_398]
0x140070015  mov     rax, [rax+18h]
0x140070019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007001e  mov     ebx, eax
0x140070020  test    eax, eax
0x140070022  js      loc_140070865
0x140070028  mov     rdi, [rsp+3E8h+var_398]
0x14007002d  mov     rax, [rdi]
0x140070030  mov     rbx, [rax+18h]
0x140070034  lea     rdx, [rsp+3E8h+Src]
0x14007003c  lea     rcx, [rsp+3E8h+var_E8]
0x140070044  call    ??$get_pointer@V?$unique_ptr@GUComDeallocator@@@std@@@stdext@@YA?AV?$GetPointer@PEAG@0@AEAV?$unique_ptr@GUComDeallocator@@@std@@@Z; stdext::get_pointer<std::unique_ptr<ushort,ComDeallocator>>(std::unique_ptr<ushort,ComDeallocator> &)
0x140070049  nop
0x14007004a  mov     rdx, rax
0x14007004d  mov     rcx, rdi
0x140070050  mov     rax, rbx
0x140070053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140070058  mov     ebx, eax
0x14007005a  mov     rcx, [rsp+3E8h+var_A8]
0x140070062  test    rcx, rcx
0x140070065  jz      short loc_1400700AD
0x140070067  mov     rax, [rsp+3E8h+var_E8]
0x14007006f  mov     [rsp+3E8h+var_388], rax
0x140070074  mov     rax, [rcx]
0x140070077  lea     rdx, [rsp+3E8h+var_388]
0x14007007c  mov     rax, [rax+10h]
0x140070080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140070085  mov     rcx, [rsp+3E8h+var_A8]
0x14007008d  test    rcx, rcx
0x140070090  jz      short loc_1400700AD
0x140070092  mov     rax, [rcx]
0x140070095  lea     rdx, [rsp+3E8h+var_E0]
0x14007009d  cmp     rcx, rdx
0x1400700a0  setnz   dl
0x1400700a3  mov     rax, [rax+20h]
0x1400700a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400700ac  nop
0x1400700ad  test    ebx, ebx
0x1400700af  js      loc_1400708CE
0x1400700b5  mov     rdi, [rsp+3E8h+var_398]
0x1400700ba  mov     rax, [rdi]
0x1400700bd  mov     rbx, [rax+28h]
0x1400700c1  lea     rdx, [rsp+3E8h+var_348]
0x1400700c9  lea     rcx, [rsp+3E8h+var_98]
0x1400700d1  call    ??$get_pointer@V?$unique_ptr@GUComDeallocator@@@std@@@stdext@@YA?AV?$GetPointer@PEAG@0@AEAV?$unique_ptr@GUComDeallocator@@@std@@@Z; stdext::get_pointer<std::unique_ptr<ushort,ComDeallocator>>(std::unique_ptr<ushort,ComDeallocator> &)
0x1400700d6  nop
0x1400700d7  mov     rdx, rax
0x1400700da  mov     rcx, rdi
0x1400700dd  mov     rax, rbx
0x1400700e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400700e5  mov     ebx, eax
0x1400700e7  mov     rcx, [rsp+3E8h+var_58]
0x1400700ef  test    rcx, rcx
0x1400700f2  jz      short loc_14007013A
0x1400700f4  mov     rax, [rsp+3E8h+var_98]
0x1400700fc  mov     [rsp+3E8h+var_388], rax
0x140070101  mov     rax, [rcx]
0x140070104  lea     rdx, [rsp+3E8h+var_388]
0x140070109  mov     rax, [rax+10h]
0x14007010d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140070112  mov     rcx, [rsp+3E8h+var_58]
0x14007011a  test    rcx, rcx
0x14007011d  jz      short loc_14007013A
0x14007011f  mov     rax, [rcx]
0x140070122  lea     rdx, [rsp+3E8h+var_90]
0x14007012a  cmp     rcx, rdx
0x14007012d  setnz   dl
0x140070130  mov     rax, [rax+20h]
0x140070134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140070139  nop
0x14007013a  test    ebx, ebx
0x14007013c  js      loc_140070923
0x140070142  mov     rax, [rsp+3E8h+var_338]
0x14007014a  mov     [rsp+3E8h+var_328], rax
0x140070152  lea     rax, [r13+40h]
0x140070156  mov     [rsp+3E8h+var_340], rax
0x14007015e  mov     rcx, [rsp+3E8h+var_398]
0x140070163  test    rcx, rcx
0x140070166  jz      short loc_14007017A
0x140070168  mov     [rsp+3E8h+var_398], rsi
0x14007016d  mov     rax, [rcx]
0x140070170  mov     rax, [rax+10h]
0x140070174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140070179  nop
0x14007017a  mov     rcx, [rsp+3E8h+var_390]
0x14007017f  test    rcx, rcx
0x140070182  jz      short loc_140070196
0x140070184  mov     [rsp+3E8h+var_390], rsi
0x140070189  mov     rax, [rcx]
0x14007018c  mov     rax, [rax+10h]
0x140070190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140070195  nop
0x140070196  mov     rcx, [rsp+3E8h+ppv]
0x14007019b  test    rcx, rcx
0x14007019e  jz      short loc_1400701B2
0x1400701a0  mov     [rsp+3E8h+ppv], rsi
0x1400701a5  mov     rax, [rcx]
0x1400701a8  mov     rax, [rax+10h]
0x1400701ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400701b1  nop
0x1400701b2  mov     rcx, [rsp+3E8h+var_378]
0x1400701b7  test    rcx, rcx
0x1400701ba  jz      short loc_1400701CE
0x1400701bc  mov     [rsp+3E8h+var_378], rsi
0x1400701c1  mov     rax, [rcx]
0x1400701c4  mov     rax, [rax+10h]
0x1400701c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400701cd  nop
0x1400701ce  mov     [rsp+3E8h+var_3B8], rsi
0x1400701d3  mov     [rsp+3E8h+var_3A8], rsi
0x1400701d8  mov     [rsp+3E8h+var_3B0], rsi
0x1400701dd  mov     rcx, [rsp+3E8h+var_3B8]
0x1400701e2  test    rcx, rcx
0x1400701e5  jz      short loc_1400701F9
0x1400701e7  mov     [rsp+3E8h+var_3B8], rsi
0x1400701ec  mov     rax, [rcx]
0x1400701ef  mov     rax, [rax+10h]
0x1400701f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400701f8  nop
0x1400701f9  lea     rax, [rsp+3E8h+var_3B8]
0x1400701fe  mov     [rsp+3E8h+pstmTemplate], rax; ppv
0x140070203  lea     r9, _GUID_130a2f65_2be7_4309_9a58_a9052ff2b61c; riid
0x14007020a  mov     r8d, r14d; dwClsContext
0x14007020d  xor     edx, edx; pUnkOuter
0x14007020f  lea     rcx, _GUID_dbce7e40_7345_439d_b12c_114a11819a09; rclsid
0x140070216  call    cs:__imp_CoCreateInstance
0x14007021c  mov     ebx, eax
0x14007021e  test    eax, eax
0x140070220  js      loc_140070978
0x140070226  mov     rcx, [rsp+3E8h+var_3B8]
0x14007022b  mov     rax, [rcx]
0x14007022e  mov     rbx, [rsp+3E8h+var_368]
0x140070236  cmp     qword ptr [rbx+18h], 7
0x14007023b  jbe     short loc_140070242
0x14007023d  mov     rdx, [rbx]
0x140070240  jmp     short loc_140070245
0x140070242  mov     rdx, rbx
0x140070245  mov     rax, [rax+28h]
0x140070249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007024e  test    eax, eax
0x140070250  jns     loc_1400702D7
0x140070256  mov     rdi, [rsp+3E8h+var_3B8]
0x14007025b  mov     rax, [rdi]
0x14007025e  mov     [rsp+3E8h+var_388], rax
0x140070263  lea     rdx, aResourcesPri; "resources.pri"
0x14007026a  lea     rcx, [rsp+3E8h+var_128]
0x140070272  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140070277  nop
0x140070278  lea     r8, [rsp+3E8h+var_128]
0x140070280  mov     rdx, r15
0x140070283  lea     rcx, [rsp+3E8h+var_108]
0x14007028b  call    ??KIO@@YA?AVPath@0@AEBV10@0@Z; IO::operator/(IO::Path const &,IO::Path const &)
0x140070290  nop
0x140070291  mov     rcx, [rsp+3E8h+var_388]
0x140070296  mov     r8, [rcx+30h]
0x14007029a  cmp     qword ptr [rax+18h], 7
0x14007029f  jbe     short loc_1400702A4
0x1400702a1  mov     rax, [rax]
0x1400702a4  mov     rdx, rax
0x1400702a7  mov     rcx, rdi
0x1400702aa  mov     rax, r8
0x1400702ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400702b2  mov     edi, eax
0x1400702b4  lea     rcx, [rsp+3E8h+var_108]
  ... truncated ...
```
