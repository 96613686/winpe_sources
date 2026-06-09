# CPropertyBagProxy::SaveToSecDescr(void)

- ea: `0x180048030`
- end: `0x180048a9b`
- name: `?SaveToSecDescr@CPropertyBagProxy@@UEAAJXZ`
- size: `2667`
- prototype: `__int64 __fastcall(CPropertyBagProxy *__hidden this)`
- caller_count: `0`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001304`
- `0x180001350`
- `0x1800020ba`
- `0x180002520`
- `0x180002a6c`
- `0x180006a1c`
- `0x1800095f4`
- `0x18000eef4`
- `0x18001a184`
- `0x180044048`
- `0x180044284`
- `0x1800444e8`
- `0x180044b40`
- `0x18004635c`
- `0x1800468cc`
- `0x180048030`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x180073f54`
- `0x180075448`
- `0x18007c000`
- `0x18007e410`
- `0x180083a68`
- `0x180084bc4`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `ntdll!RtlInitializeSid` at `0x180048490`
- `ntdll!RtlInitializeSid` at `0x180048490`
- `KERNEL32!CreateFileW` at `0x180048627`
- `KERNEL32!CreateFileW` at `0x180048627`
- `KERNEL32!CloseHandle` at `0x1800487d4`
- `KERNEL32!CloseHandle` at `0x1800487d4`
- `KERNEL32!LocalFree` at `0x18004879e`
- `KERNEL32!LocalFree` at `0x18004879e`
- `ADVAPI32!SetSecurityInfo` at `0x180048675`
- `ADVAPI32!SetSecurityInfo` at `0x180048675`
- `ADVAPI32!GetSecurityInfo` at `0x18004875c`
- `ADVAPI32!GetSecurityInfo` at `0x18004875c`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800484de`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800484de`

## string_xrefs

- `0x180048076`: `base\fs\fsrm\service\modulewrp\propertybagproxy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CPropertyBagProxy::SaveToSecDescr(CPropertyBagProxy *this)
{
  int v2; // edi
  int v3; // eax
  __int64 *v4; // rax
  const char *v5; // rdx
  char v6; // r15
  char *v7; // r13
  __int64 v8; // rdx
  unsigned int v9; // r14d
  __int64 v10; // rax
  __int64 v11; // rsi
  __int64 v12; // rbx
  _QWORD *v13; // rax
  void (__fastcall ***v14)(_QWORD); // rcx
  int v15; // ecx
  _OWORD *v16; // rax
  unsigned int v17; // eax
  int v18; // eax
  struct _ACL *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 *v22; // rbx
  __int64 *v23; // rax
  __int64 *v24; // rax
  __int64 *v25; // rax
  PACL v26; // rbx
  const WCHAR *v27; // rcx
  HANDLE FileW; // rax
  __int64 v29; // rdx
  void *v30; // rdi
  signed int v31; // eax
  __int64 v32; // rsi
  const unsigned __int16 *v33; // r14
  CFciUsnScanner *v34; // rax
  signed int SecurityInfo; // eax
  WORD AceCount; // bx
  unsigned int v37; // ebx
  int Hr; // eax
  char v40; // al
  int v41; // eax
  char v42; // al
  int LastFailureAsHRESULT; // eax
  char v44; // al
  int v45; // eax
  char v46; // al
  int v47; // eax
  char v48; // al
  char v49; // al
  int v50; // eax
  char v51; // al
  PACL ppSacl; // [rsp+48h] [rbp-520h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+50h] [rbp-518h] BYREF
  void **v54; // [rsp+58h] [rbp-510h]
  __int64 v55; // [rsp+60h] [rbp-508h]
  unsigned int i; // [rsp+68h] [rbp-500h]
  _BYTE v57[4]; // [rsp+6Ch] [rbp-4FCh] BYREF
  __int64 *v58; // [rsp+70h] [rbp-4F8h]
  void *v59; // [rsp+78h] [rbp-4F0h] BYREF
  __int64 v60; // [rsp+80h] [rbp-4E8h]
  void (__fastcall ***v61)(_QWORD); // [rsp+88h] [rbp-4E0h]
  _QWORD *v62; // [rsp+90h] [rbp-4D8h]
  char v63[8]; // [rsp+98h] [rbp-4D0h] BYREF
  __int64 *v64; // [rsp+A0h] [rbp-4C8h]
  __int64 v65; // [rsp+A8h] [rbp-4C0h]
  int v66; // [rsp+B8h] [rbp-4B0h] BYREF
  __int64 *j; // [rsp+C0h] [rbp-4A8h]
  _QWORD *v68; // [rsp+C8h] [rbp-4A0h]
  __int128 v69; // [rsp+D0h] [rbp-498h]
  _com_error *v70; // [rsp+E0h] [rbp-488h] BYREF
  const exception *v71; // [rsp+E8h] [rbp-480h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+F0h] [rbp-478h] BYREF
  _QWORD v73[3]; // [rsp+108h] [rbp-460h] BYREF
  int v74; // [rsp+120h] [rbp-448h]
  int v75; // [rsp+124h] [rbp-444h]
  int v76; // [rsp+128h] [rbp-440h]
  _DWORD v77[26]; // [rsp+130h] [rbp-438h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+198h] [rbp-3D0h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+1A0h] [rbp-3C8h] BYREF
  __int64 v80; // [rsp+1B0h] [rbp-3B8h]
  unsigned __int64 v81; // [rsp+1B8h] [rbp-3B0h]
  void **v82; // [rsp+1D0h] [rbp-398h] BYREF
  unsigned int v83; // [rsp+1D8h] [rbp-390h]
  unsigned int v84; // [rsp+1FCh] [rbp-36Ch]
  void *Block[3]; // [rsp+280h] [rbp-2E8h] BYREF
  unsigned __int64 v86; // [rsp+298h] [rbp-2D0h]
  void *v87[3]; // [rsp+2A8h] [rbp-2C0h] BYREF
  unsigned __int64 v88; // [rsp+2C0h] [rbp-2A8h]
  DWORD nAclLength[2]; // [rsp+2D0h] [rbp-298h] BYREF
  PACL pAcl; // [rsp+2D8h] [rbp-290h]
  _BYTE v91[512]; // [rsp+2E0h] [rbp-288h] BYREF
  _BYTE Sid[80]; // [rsp+4E0h] [rbp-88h] BYREF

  v2 = 0;
  v62 = v73;
  v73[0] = L"base\\fs\\fsrm\\service\\modulewrp\\propertybagproxy.cpp";
  v73[1] = L"CPropertyBagProxy::SaveToSecDescr";
  v73[2] = L"PROPBGPC";
  v74 = 1007;
  v75 = 22;
  v76 = 255;
  v77[24] = 0x1000000;
  memset_0(v77, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer(&v82, v73, 0);
  try
  {
    v59 = 0;
    v3 = (*(__int64 (__fastcall **)(CPropertyBagProxy *, void **))(*(_QWORD *)this + 64LL))(this, &v59);
    v83 = v3;
    if ( v3 < 0 )
    {
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v82);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v82, Hr);
      v40 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v82);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v82, 0x3F8u, v40, 0);
    }
    v83 = v3;
    CSrmImpersonationSession::CSrmImpersonationSession((CSrmImpersonationSession *)v57, v59);
    v65 = 0;
    v4 = (__int64 *)operator new(0x58u);
    if ( !v4 )
    {
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, v5);
      throw (std::bad_alloc *)pExceptionObject;
    }
    v64 = v4;
    *v4 = (__int64)v4;
    v4[1] = (__int64)v64;
    v4[2] = (__int64)v64;
    *((_BYTE *)v4 + 80) = 1;
    *((_BYTE *)v4 + 81) = 1;
    v81 = 7;
    v80 = 0;
    LOWORD(lpFileName[0]) = 0;
    v6 = 0;
    memset_0(Sid, 0, 0x44u);
    IdentifierAuthority.Value[0] = 0;
    IdentifierAuthority.Value[1] = 0;
    IdentifierAuthority.Value[2] = 0;
    IdentifierAuthority.Value[3] = 0;
    IdentifierAuthority.Value[4] = 0;
    IdentifierAuthority.Value[5] = 1;
    v7 = (char *)this + 80;
    LOBYTE(v8) = 1;
    CPropertyBagFieldsBase::BuildFullPath((char *)this + 80, v8, 0, lpFileName);
    SrmConvertToLongPath(lpFileName);
    v9 = 0;
    for ( i = 0; ; i = v9 )
    {
      v10 = *((_QWORD *)this + 12);
      if ( v9 >= *(_DWORD *)(v10 + 16) )
        break;
      v11 = *(_QWORD *)(v10 + 24) + 32LL * v9;
      v12 = *((_QWORD *)this + 72);
      std::wstring::wstring(Block);
      std::_Tree<std::_Tmap_traits<std::wstring,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>>>,0>>::find(
        v12,
        &ppSacl,
        Block);
      if ( v86 >= 8 )
        operator delete(Block[0]);
      v86 = 7;
      Block[2] = 0;
      LOWORD(Block[0]) = 0;
      hMem = *(PSECURITY_DESCRIPTOR *)(*((_QWORD *)this + 72) + 8LL);
      if ( ppSacl == hMem )
      {
        v60 = 0;
        v2 |= 2u;
        v13 = 0;
      }
      else
      {
        v14 = (void (__fastcall ***)(_QWORD))ppSacl[8];
        v61 = v14;
        if ( v14 )
          (**v14)(v14);
        v2 |= 1u;
        v13 = v61;
      }
      v62 = v13;
      if ( (v2 & 2) != 0 )
      {
        v2 &= ~2u;
        if ( v60 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 8LL))(v60);
      }
      if ( (v2 & 1) != 0 )
      {
        v2 &= ~1u;
        if ( v61 )
          (*v61)[1](v61);
      }
      v15 = *(_DWORD *)(v11 + 24);
      if ( (v15 & 0x800) != 0 )
      {
        if ( (v15 & 0x2000) != 0 )
        {
          if ( (v15 & 0x8000) != 0 )
            v6 = 1;
        }
        else if ( (v15 & 0x10) != 0 )
        {
          v6 = 1;
        }
        else if ( *(_QWORD *)(v11 + 8) )
        {
          v68 = (_QWORD *)v11;
          *(_QWORD *)&v69 = v11;
          *((_QWORD *)&v69 + 1) = v62;
          std::wstring::wstring(v87);
          v16 = (_OWORD *)std::map<std::wstring,std::pair<_FSRM_AGGREGATED_PROPERTY const *,CSerializedPropertyDefinition const *>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<_FSRM_AGGREGATED_PROPERTY const *,CSerializedPropertyDefinition const *>>>>::operator[](
                            v63,
                            v87);
          *v16 = v69;
          if ( v88 >= 8 )
            operator delete(v87[0]);
          v88 = 7;
          v87[2] = 0;
          LOWORD(v87[0]) = 0;
        }
        else if ( (v15 & 0x40) == 0 )
        {
          CSrmFunctionTracer::Trace(
            (CSrmFunctionTracer *)&v82,
            0x28u,
            0x441u,
            L"No value available for property %s",
            *(_QWORD *)v11);
        }
      }
      ++v9;
    }
    *(_QWORD *)nAclLength = 512;
    pAcl = 0;
    memset_0(v91, 0, sizeof(v91));
    v17 = RtlInitializeSid(Sid, &IdentifierAuthority, 1u);
    v18 = HRESULTFromNTSTATUS(v17);
    v83 = v18;
    if ( v18 < 0 )
    {
      v41 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v82);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v82, v41);
      v42 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v82);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v82, 0x44Du, v42, 0);
    }
    v83 = v18;
    v19 = (struct _ACL *)v91;
    if ( pAcl )
      v19 = pAcl;
    if ( !InitializeAcl(v19, nAclLength[0], 2u) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v21, v20);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v82, LastFailureAsHRESULT);
      v44 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v82);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v82, 0x44Fu, v44, 0);
    }
    v83 = 0;
    if ( v65 )
    {
      v22 = (__int64 *)*v64;
LABEL_38:
      v58 = v22;
      while ( 1 )
      {
        v68 = v64;
        if ( v22 == v64 )
          break;
        CPropertyBagProxy::AddPropertyToResourceAcl(
          (_DWORD)this - 8,
          (unsigned int)nAclLength,
          (unsigned int)Sid,
          v22[8],
          v22[9]);
        if ( !*((_BYTE *)v22 + 81) )
        {
          v23 = (__int64 *)v22[2];
          if ( !*((_BYTE *)v23 + 81) )
          {
            v22 = (__int64 *)v22[2];
            for ( j = v23; ; j = v24 )
            {
              v24 = (__int64 *)*v22;
              if ( *(_BYTE *)(*v22 + 81) )
                break;
              v22 = (__int64 *)*v22;
            }
            goto LABEL_38;
          }
          while ( 1 )
          {
            v25 = (__int64 *)v22[1];
            if ( *((_BYTE *)v25 + 81) || v22 != (__int64 *)v25[2] )
              break;
            v22 = (__int64 *)v22[1];
            v58 = v25;
          }
          v22 = (__int64 *)v22[1];
          v58 = v25;
        }
      }
    }
    v26 = (PACL)v91;
    if ( pAcl )
      v26 = pAcl;
    if ( v26->AceCount || v6 )
    {
      v55 = -1;
      v54 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
      v27 = (const WCHAR *)lpFileName;
      if ( v81 >= 8 )
        v27 = lpFileName[0];
      FileW = CreateFileW(v27, 0x60000u, 7u, 0, 3u, 0x2000000u, 0);
      v30 = FileW;
      v55 = (__int64)FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        v50 = GetLastFailureAsHRESULT(v83, v29);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v82, v50);
        v51 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v82);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v82, 0x471u, v51, 0);
      }
      v83 = 0;
      v31 = SetSecurityInfo(FileW, SE_FILE_OBJECT, 0x20u, 0, 0, 0, v26);
      if ( v31 > 0 )
        v31 = (unsigned __int16)v31 | 0x80070000;
      v83 = v31;
      if ( v31 < 0 )
      {
        v45 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v82);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v82, v45);
        v46 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v82);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v82, 0x47Au, v46, 0);
      }
      v83 = v31;
      if ( (*(unsigned __int8 (__fastcall **)(char *, __int64))(*(_QWORD *)v7 + 72LL))(v7, 0x8000) )
      {
        v32 = SrmWriteCloseUsnRecord(v30);
        if ( v32 )
        {
          v33 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v7 + 24LL))(v7);
          if ( CSrmSingleton<CFciUsnScanner>::m_pInstance )
          {
            v34 = (CFciUsnScanner *)CSrmSingleton<CFciUsnScanner>::Instance();
            CFciUsnScanner::IgnoreUsnInternal(v34, v33, v32);
          }
        }
      }
      if ( v26->AceCount && (*(unsigned __int8 (__fastcall **)(char *, __int64))(*(_QWORD *)v7 + 72LL))(v7, 0x20000) )
      {
        hMem = 0;
        ppSacl = 0;
        SecurityInfo = GetSecurityInfo(v30, SE_FILE_OBJECT, 0x20u, 0, 0, 0, &ppSacl, &hMem);
        if ( SecurityInfo > 0 )
          SecurityInfo = (unsigned __int16)SecurityInfo | 0x80070000;
        v83 = SecurityInfo;
        if ( SecurityInfo < 0 )
        {
          v47 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v82);
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v82, v47);
          v48 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v82);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v82, 0x497u, v48, 0);
        }
        AceCount = 0;
        v83 = SecurityInfo;
        if ( ppSacl )
          AceCount = ppSacl->AceCount;
        if ( hMem )
        {
          LocalFree(hMem);
          hMem = 0;
          ppSacl = 0;
          SecurityInfo = v83;
        }
        v83 = SecurityInfo;
        if ( !AceCount )
        {
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v82, -2147200127);
          v49 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v82);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v82, 0x4A8u, v49, 0);
        }
        v83 = 0;
      }
      v54 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
      CloseHandle(v30);
      v54 = &CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::`vftable';
      v55 = -1;
    }
    if ( pAcl )
    {
      operator delete(pAcl);
      pAcl = 0;
    }
    *(_QWORD *)nAclLength = 512;
    memset_0(v91, 0, sizeof(v91));
    if ( v81 >= 8 )
      operator delete((void *)lpFileName[0]);
    v81 = 7;
    v80 = 0;
    LOWORD(lpFileName[0]) = 0;
    std::_Tree<std::_Tmap_traits<std::wstring,std::pair<_FSRM_AGGREGATED_PROPERTY const *,CSerializedPropertyDefinition const *>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<_FSRM_AGGREGATED_PROPERTY const *,CSerializedPropertyDefinition const *>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::pair<_FSRM_AGGREGATED_PROPERTY const *,CSerializedPropertyDefinition const *>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<_FSRM_AGGREGATED_PROPERTY const *,CSerializedPropertyDefinition const *>>>,0>>(v63);
    CSrmImpersonationSession::RevertImpersonation((CSrmImpersonationSession *)v57);
  }
  catch ( long v66 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v82,
      v66,
      L"base\\fs\\fsrm\\service\\modulewrp\\propertybagproxy.cpp",
      L"PROPBGPC",
      L"CPropertyBagProxy::SaveToSecDescr",
      0x4ACu,
      v84);
  }
  catch ( _com_error *v70 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v82,
      v70,
      L"base\\fs\\fsrm\\service\\modulewrp\\propertybagproxy.cpp",
      L"PROPBGPC",
      L"CPropertyBagProxy::SaveToSecDescr",
      0x4ACu,
      v84);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v82,
      L"base\\fs\\fsrm\\service\\modulewrp\\propertybagproxy.cpp",
      L"PROPBGPC",
      L"CPropertyBagProxy::SaveToSecDescr",
      0x4ACu,
      v84);
  }
  catch ( const exception *v71 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v82,
      v71,
      L"base\\fs\\fsrm\\service\\modulewrp\\propertybagproxy.cpp",
      L"PROPBGPC",
      L"CPropertyBagProxy::SaveToSecDescr",
      0x4ACu,
      v84);
  }
  v59 = 0;
  v3 = (*(__int64 (__fastcall **)(CPropertyBagProxy *, void **))(*(_QWORD *)this + 64LL))(this, &v59);
  v83 = v3;
  if ( v3 < 0 )
  {
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v82);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v82, Hr);
    v40 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v82);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v82, 0x3F8u, v40, 0);
  }
}

```

## disassembly

```asm
0x180048030  mov     r11, rsp
0x180048033  mov     [r11+10h], rbx
0x180048037  mov     [r11+18h], rsi
0x18004803b  push    rdi
0x18004803c  push    r12
0x18004803e  push    r13
0x180048040  push    r14
0x180048042  push    r15
0x180048044  sub     rsp, 540h
0x18004804b  mov     rax, cs:__security_cookie
0x180048052  xor     rax, rsp
0x180048055  mov     [rsp+568h+var_38], rax
0x18004805d  mov     r12, rcx
0x180048060  xor     esi, esi
0x180048062  mov     edi, esi
0x180048064  mov     [rsp+568h+var_524], esi
0x180048068  lea     rax, [r11-460h]
0x18004806f  mov     [r11-4D8h], rax
0x180048076  lea     rax, aBaseFsFsrmServ_8; "base\\fs\\fsrm\\service\\modulewrp\\pro"...
0x18004807d  mov     [r11-460h], rax
0x180048084  lea     rax, aCpropertybagpr_23; "CPropertyBagProxy::SaveToSecDescr"
0x18004808b  mov     [r11-458h], rax
0x180048092  lea     rax, aPropbgpc; "PROPBGPC"
0x180048099  mov     [r11-450h], rax
0x1800480a0  mov     [rsp+568h+var_448], 3EFh
0x1800480ab  mov     [rsp+568h+var_444], 16h
0x1800480b6  mov     [rsp+568h+var_440], 0FFh
0x1800480c1  mov     [rsp+568h+var_3D8], 1000000h
0x1800480cc  xor     edx, edx; Val
0x1800480ce  lea     r14d, [rsi+1]
0x1800480d2  lea     r8d, [rsi+60h]; Size
0x1800480d6  lea     rcx, [r11-438h]; void *
0x1800480dd  call    memset_0
0x1800480e2  nop
0x1800480e3  xor     r8d, r8d
0x1800480e6  lea     rdx, [rsp+568h+var_460]
0x1800480ee  lea     rcx, [rsp+568h+var_398]
0x1800480f6  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x1800480fb  nop
0x1800480fc  mov     [rsp+568h+var_4F0], rsi
0x180048101  mov     rax, [r12]
0x180048105  lea     rdx, [rsp+568h+var_4F0]
0x18004810a  mov     rcx, r12
0x18004810d  mov     rax, [rax+40h]
0x180048111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048116  mov     [rsp+568h+var_390], eax
0x18004811d  test    eax, eax
0x18004811f  js      loc_1800488C8
0x180048125  mov     [rsp+568h+var_390], eax
0x18004812c  mov     rdx, [rsp+568h+var_4F0]; void *
0x180048131  lea     rcx, [rsp+568h+var_4FC]; this
0x180048136  call    ??0CSrmImpersonationSession@@QEAA@PEAX@Z; CSrmImpersonationSession::CSrmImpersonationSession(void *)
0x18004813b  nop
0x18004813c  mov     [rsp+568h+var_4C0], rsi
0x180048144  mov     ecx, 58h ; 'X'; Size
0x180048149  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004814e  test    rax, rax
0x180048151  jz      loc_180048A78
0x180048157  mov     [rsp+568h+var_4C8], rax
0x18004815f  mov     [rax], rax
0x180048162  mov     rcx, [rsp+568h+var_4C8]
0x18004816a  mov     [rax+8], rcx
0x18004816e  mov     rcx, [rsp+568h+var_4C8]
0x180048176  mov     [rax+10h], rcx
0x18004817a  mov     [rax+50h], r14b
0x18004817e  mov     [rax+51h], r14b
0x180048182  mov     [rsp+568h+var_3B0], 7
0x18004818e  mov     [rsp+568h+var_3B8], rsi
0x180048196  mov     word ptr [rsp+568h+lpFileName], si
0x18004819e  mov     r15b, sil
0x1800481a1  mov     [rsp+568h+var_528], sil
0x1800481a6  xor     edx, edx; Val
0x1800481a8  lea     r8d, [rdx+44h]; Size
0x1800481ac  lea     rcx, [rsp+568h+Sid]; void *
0x1800481b4  call    memset_0
0x1800481b9  mov     [rsp+568h+IdentifierAuthority.Value], sil
0x1800481c1  mov     [rsp+568h+IdentifierAuthority.Value+1], sil
0x1800481c9  mov     [rsp+568h+IdentifierAuthority.Value+2], sil
0x1800481d1  mov     [rsp+568h+IdentifierAuthority.Value+3], sil
0x1800481d9  mov     [rsp+568h+IdentifierAuthority.Value+4], sil
0x1800481e1  mov     [rsp+568h+IdentifierAuthority.Value+5], r14b
0x1800481e9  lea     r13, [r12+50h]
0x1800481ee  lea     r9, [rsp+568h+lpFileName]
0x1800481f6  xor     r8d, r8d
0x1800481f9  mov     dl, r14b
0x1800481fc  mov     rcx, r13
0x1800481ff  call    ?BuildFullPath@CPropertyBagFieldsBase@@QEBAX_NPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CPropertyBagFieldsBase::BuildFullPath(bool,ushort const *,std::wstring &)
0x180048204  lea     rcx, [rsp+568h+lpFileName]
0x18004820c  call    ?SrmConvertToLongPath@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SrmConvertToLongPath(std::wstring &)
0x180048211  mov     r14d, esi
0x180048214  mov     [rsp+568h+var_500], esi
0x180048218  mov     rax, [r12+60h]
0x18004821d  cmp     r14d, [rax+10h]
0x180048221  jnb     loc_180048455
0x180048227  mov     esi, r14d
0x18004822a  shl     rsi, 5
0x18004822e  add     rsi, [rax+18h]
0x180048232  mov     rbx, [r12+240h]
0x18004823a  mov     rdx, [rsi]
0x18004823d  lea     rcx, [rsp+568h+Block]; void *
0x180048245  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18004824a  nop
0x18004824b  lea     r8, [rsp+568h+Block]
0x180048253  lea     rdx, [rsp+568h+ppSacl]
0x180048258  mov     rcx, rbx
0x18004825b  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@@std@@@2@$0A@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>>>,0>>::find(std::wstring const &)
0x180048260  nop
0x180048261  cmp     [rsp+568h+var_2D0], 8
0x18004826a  jb      short loc_180048279
0x18004826c  mov     rcx, [rsp+568h+Block]; Block
0x180048274  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180048279  mov     [rsp+568h+var_2D0], 7
0x180048285  xor     ebx, ebx
0x180048287  mov     [rsp+568h+var_2D8], rbx
0x18004828f  mov     word ptr [rsp+568h+Block], bx
0x180048297  mov     rax, [r12+240h]
0x18004829f  mov     rdx, [rax+8]
0x1800482a3  mov     [rsp+568h+hMem], rdx
0x1800482a8  mov     rcx, [rsp+568h+ppSacl]
0x1800482ad  cmp     rcx, rdx
0x1800482b0  jnz     short loc_1800482CB
0x1800482b2  mov     [rsp+568h+var_4E8], rbx
0x1800482ba  or      edi, 2
0x1800482bd  mov     [rsp+568h+var_524], edi
0x1800482c1  mov     rax, [rsp+568h+var_4E8]
0x1800482c9  jmp     short loc_1800482F7
0x1800482cb  mov     rcx, [rcx+40h]
0x1800482cf  mov     [rsp+568h+var_4E0], rcx
0x1800482d7  test    rcx, rcx
0x1800482da  jz      short loc_1800482E8
0x1800482dc  mov     rax, [rcx]
0x1800482df  mov     rax, [rax]
0x1800482e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482e7  nop
0x1800482e8  or      edi, 1
0x1800482eb  mov     [rsp+568h+var_524], edi
0x1800482ef  mov     rax, [rsp+568h+var_4E0]
0x1800482f7  mov     [rsp+568h+var_4D8], rax
0x1800482ff  test    dil, 2
0x180048303  jz      short loc_180048326
0x180048305  and     edi, 0FFFFFFFDh
0x180048308  mov     [rsp+568h+var_524], edi
0x18004830c  mov     rcx, [rsp+568h+var_4E8]
0x180048314  test    rcx, rcx
0x180048317  jz      short loc_180048326
0x180048319  mov     rax, [rcx]
0x18004831c  mov     rax, [rax+8]
0x180048320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048325  nop
0x180048326  mov     edx, 1
0x18004832b  test    dl, dil
0x18004832e  jz      short loc_180048355
0x180048330  and     edi, 0FFFFFFFEh
0x180048333  mov     [rsp+568h+var_524], edi
0x180048337  mov     rcx, [rsp+568h+var_4E0]
0x18004833f  test    rcx, rcx
0x180048342  jz      short loc_180048355
0x180048344  mov     rax, [rcx]
0x180048347  mov     rax, [rax+8]
0x18004834b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048350  mov     edx, 1
0x180048355  mov     ecx, [rsi+18h]
0x180048358  bt      ecx, 0Bh
0x18004835c  jb      short loc_180048365
0x18004835e  xor     esi, esi
0x180048360  jmp     loc_180048448
0x180048365  bt      ecx, 0Dh
0x180048369  jnb     short loc_18004837E
0x18004836b  bt      ecx, 0Fh
0x18004836f  movzx   r15d, r15b
0x180048373  cmovb   r15d, edx
0x180048377  mov     [rsp+568h+var_528], r15b
0x18004837c  jmp     short loc_18004835E
0x18004837e  test    cl, 10h
0x180048381  jz      short loc_18004838C
0x180048383  mov     r15b, dl
0x180048386  mov     [rsp+568h+var_528], dl
0x18004838a  jmp     short loc_18004835E
0x18004838c  cmp     [rsi+8], rbx
0x180048390  jnz     short loc_1800483C0
0x180048392  test    cl, 40h
0x180048395  jnz     short loc_18004835E
0x180048397  mov     rax, [rsi]
0x18004839a  mov     qword ptr [rsp+568h+dwCreationDisposition], rax
0x18004839f  lea     r9, aNoValueAvailab; "No value available for property %s"
0x1800483a6  mov     edx, 28h ; '('; unsigned int
0x1800483ab  mov     r8d, 441h; unsigned int
0x1800483b1  lea     rcx, [rsp+568h+var_398]; this
0x1800483b9  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x1800483be  jmp     short loc_18004835E
0x1800483c0  mov     [rsp+568h+var_4A0], rsi
0x1800483c8  mov     qword ptr [rsp+568h+var_498], rsi
0x1800483d0  mov     rax, [rsp+568h+var_4D8]
0x1800483d8  mov     qword ptr [rsp+568h+var_498+8], rax
0x1800483e0  mov     rdx, [rsi]
0x1800483e3  lea     rcx, [rsp+568h+var_2C0]; void *
0x1800483eb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800483f0  nop
0x1800483f1  lea     rdx, [rsp+568h+var_2C0]
0x1800483f9  lea     rcx, [rsp+568h+var_4D0]
0x180048401  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@PEBU_FSRM_AGGREGATED_PROPERTY@@PEBVCSerializedPropertyDefinition@@@2@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@PEBU_FSRM_AGGREGATED_PROPERTY@@PEBVCSerializedPropertyDefinition@@@2@@std@@@2@@std@@QEAAAEAU?$pair@PEBU_FSRM_AGGREGATED_PROPERTY@@PEBVCSerializedPropertyDefinition@@@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::pair<_FSRM_AGGREGATED_PROPERTY const *,CSerializedPropertyDefinition const *>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<_FSRM_AGGREGATED_PROPERTY const *,CSerializedPropertyDefinition const *>>>>::operator[](std::wstring &&)
0x180048406  movups  xmm0, [rsp+568h+var_498]
0x18004840e  movdqu  xmmword ptr [rax], xmm0
0x180048412  cmp     [rsp+568h+var_2A8], 8
0x18004841b  jb      short loc_18004842A
0x18004841d  mov     rcx, [rsp+568h+var_2C0]; Block
0x180048425  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004842a  mov     [rsp+568h+var_2A8], 7
0x180048436  xor     esi, esi
0x180048438  mov     [rsp+568h+var_2B0], rsi
0x180048440  mov     word ptr [rsp+568h+var_2C0], si
0x180048448  inc     r14d
0x18004844b  mov     [rsp+568h+var_500], r14d
0x180048450  jmp     loc_180048218
0x180048455  mov     edi, 200h
0x18004845a  mov     qword ptr [rsp+568h+nAclLength], rdi
0x180048462  mov     [rsp+568h+pAcl], rsi
0x18004846a  mov     r8d, edi; Size
0x18004846d  xor     edx, edx; Val
0x18004846f  lea     rcx, [rsp+568h+var_288]; void *
0x180048477  call    memset_0
0x18004847c  nop
0x18004847d  mov     r8b, 1; SubAuthorityCount
0x180048480  lea     rdx, [rsp+568h+IdentifierAuthority]; IdentifierAuthority
0x180048488  lea     rcx, [rsp+568h+Sid]; Sid
0x180048490  call    cs:__imp_RtlInitializeSid
0x180048496  mov     ecx, eax
0x180048498  call    HRESULTFromNTSTATUS
0x18004849d  mov     [rsp+568h+var_390], eax
0x1800484a4  test    eax, eax
0x1800484a6  js      loc_18004890A
0x1800484ac  mov     [rsp+568h+var_390], eax
0x1800484b3  mov     [rsp+568h+var_390], eax
0x1800484ba  lea     rcx, [rsp+568h+var_288]
0x1800484c2  mov     rax, [rsp+568h+pAcl]
0x1800484ca  test    rax, rax
0x1800484cd  cmovnz  rcx, rax; pAcl
0x1800484d1  mov     r8d, 2; dwAclRevision
0x1800484d7  mov     edx, [rsp+568h+nAclLength]; nAclLength
0x1800484de  call    cs:__imp_InitializeAcl
0x1800484e4  test    eax, eax
0x1800484e6  jz      loc_18004894B
0x1800484ec  mov     [rsp+568h+var_390], esi
0x1800484f3  cmp     [rsp+568h+var_4C0], rsi
0x1800484fb  jz      loc_1800485A5
0x180048501  mov     rbx, [rsp+568h+var_4C8]
0x180048509  mov     rbx, [rbx]
0x18004850c  mov     [rsp+568h+var_4F8], rbx
0x180048511  mov     rax, [rsp+568h+var_4C8]
0x180048519  mov     [rsp+568h+var_4A0], rax
0x180048521  cmp     rbx, rax
0x180048524  jz      short loc_1800485A5
0x180048526  lea     rcx, [r12-8]
0x18004852b  mov     rax, [rbx+48h]
0x18004852f  mov     qword ptr [rsp+568h+dwCreationDisposition], rax
0x180048534  mov     r9, [rbx+40h]
0x180048538  lea     r8, [rsp+568h+Sid]
0x180048540  lea     rdx, [rsp+568h+nAclLength]
0x180048548  call    ?AddPropertyToResourceAcl@CPropertyBagProxy@@AEAAXAEAV?$CSrmPreallocArray@E$0CAA@@@PEAXAEBU_FSRM_AGGREGATED_PROPERTY@@PEBVCSerializedPropertyDefinition@@@Z; CPropertyBagProxy::AddPropertyToResourceAcl(CSrmPreallocArray<uchar,512> &,void *,_FSRM_AGGREGATED_PROPERTY const &,CSerializedPropertyDefinition const *)
0x18004854d  cmp     [rbx+51h], sil
0x180048551  jnz     short loc_180048511
0x180048553  mov     rax, [rbx+10h]
0x180048557  cmp     [rax+51h], sil
0x18004855b  jnz     short loc_18004857E
0x18004855d  mov     rbx, rax
0x180048560  mov     [rsp+568h+var_4A8], rax
0x180048568  mov     rax, [rbx]
0x18004856b  cmp     [rax+51h], sil
0x18004856f  jnz     short loc_18004850C
0x180048571  mov     rbx, rax
0x180048574  mov     [rsp+568h+var_4A8], rax
0x18004857c  jmp     short loc_180048568
0x18004857e  mov     rax, [rbx+8]
0x180048582  cmp     [rax+51h], sil
0x180048586  jnz     short loc_180048598
0x180048588  cmp     rbx, [rax+10h]
0x18004858c  jnz     short loc_180048598
0x18004858e  mov     rbx, rax
0x180048591  mov     [rsp+568h+var_4F8], rax
0x180048596  jmp     short loc_18004857E
0x180048598  mov     rbx, rax
0x18004859b  mov     [rsp+568h+var_4F8], rax
0x1800485a0  jmp     loc_180048511
0x1800485a5  lea     rbx, [rsp+568h+var_288]
0x1800485ad  mov     rax, [rsp+568h+pAcl]
0x1800485b5  test    rax, rax
0x1800485b8  cmovnz  rbx, rax
0x1800485bc  cmp     [rbx+4], si
0x1800485c0  jnz     short loc_1800485CB
0x1800485c2  test    r15b, r15b
0x1800485c5  jz      loc_1800487EE
0x1800485cb  lea     r14, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x1800485d2  mov     [rsp+568h+var_510], r14
0x1800485d7  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800485db  mov     [rsp+568h+var_508], r15
0x1800485e0  lea     r12, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x1800485e7  mov     [rsp+568h+var_510], r12
0x1800485ec  lea     rcx, [rsp+568h+lpFileName]
0x1800485f4  cmp     [rsp+568h+var_3B0], 8
0x1800485fd  cmovnb  rcx, [rsp+568h+lpFileName]; lpFileName
  ... truncated ...
```
