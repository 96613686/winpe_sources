# Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache::ReadAllObjectIdsForTypeFromCache(Windows::Internal::Security::Authentication::Web::IWamObjectStore *,Windows::Internal::Security::Authentication::TokenBroker::StoredObjectType,HSTRING__ * const,std::vector<std::shared_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId>,std::allocator<std::shared_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId>>> &)

- ea: `0x180076f60`
- end: `0x1800780ef`
- name: `?ReadAllObjectIdsForTypeFromCache@StoredObjectInfoWithCache@TokenBroker@Authentication@Security@Internal@Windows@@CAJPEAUIWamObjectStore@Web@3456@W4StoredObjectType@23456@QEAUHSTRING__@@AEAV?$vector@V?$shared_ptr@VStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@@std@@V?$allocator@V?$shared_ptr@VStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@2@@std@@@Z`
- size: `4495`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18005a8ec`

## callees

- `0x180008fb0`
- `0x18000a5d0`
- `0x18000bd40`
- `0x1800426b0`
- `0x180076f60`
- `0x18007f9b0`
- `0x18008e690`
- `0x18008e6b4`
- `0x18008e6cc`
- `0x18009c780`
- `0x180110bf4`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076fc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077652`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077662`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076fc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077652`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077662`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077128`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077dbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077e32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077f88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800780bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077128`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077dbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077e32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077f88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800780bb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180077099`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180077099`

## string_xrefs

- `0x1800770fe`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x1800771c4`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180077247`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x1800772ca`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180077760`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180077830`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180077999`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180077afd`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180077c60`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180077fa5`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache::ReadAllObjectIdsForTypeFromCache(
        __int64 a1,
        unsigned int a2,
        HSTRING a3,
        void **a4)
{
  void **v4; // r14
  PCWSTR StringRawBuffer; // rax
  __int64 v6; // rcx
  int v7; // ecx
  int AllObjectsCacheKey; // eax
  int v9; // ebx
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  unsigned __int64 v21; // r13
  __int64 v22; // rcx
  unsigned __int16 *v23; // r12
  char *v24; // r14
  char *v25; // rsi
  unsigned int v26; // r8d
  int v27; // eax
  unsigned int v28; // r15d
  _QWORD *v29; // rdi
  signed __int64 v30; // rbx
  unsigned __int64 v31; // rcx
  unsigned __int64 v32; // rdx
  unsigned __int64 v33; // r13
  size_t v34; // r13
  _QWORD *v35; // r15
  void *v36; // rax
  _QWORD *v37; // rdx
  _QWORD *v38; // rsi
  _QWORD *v39; // rcx
  _QWORD *v40; // rbx
  _QWORD *v41; // rcx
  volatile signed __int32 *v42; // rdi
  _BYTE *v43; // rcx
  int v44; // ecx
  int v45; // r8d
  int v46; // r9d
  unsigned __int64 v47; // rax
  unsigned __int64 v48; // rcx
  __int64 v49; // rax
  const WCHAR *v50; // rbx
  char *v51; // rdi
  char *v52; // rsi
  volatile signed __int32 *v53; // rbx
  _BYTE *v54; // rcx
  char *v55; // rdi
  char *v56; // r14
  volatile signed __int32 *v57; // rbx
  _BYTE *v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // rcx
  char *v61; // rdi
  char *v62; // r14
  volatile signed __int32 *v63; // rbx
  _BYTE *v64; // rcx
  __int64 v65; // rcx
  __int64 v66; // rcx
  char *v67; // rdi
  char *v68; // r14
  volatile signed __int32 *v69; // rbx
  void *v70; // rcx
  __int64 v71; // rcx
  __int64 v72; // rcx
  char *v73; // rdi
  char *v74; // rsi
  volatile signed __int32 *v75; // rbx
  _BYTE *v76; // rcx
  __int64 v77; // rcx
  __int64 v78; // rcx
  __int64 v79; // rcx
  __int64 v80; // rcx
  char *v81; // rax
  char *v82; // rdi
  char *v83; // rax
  char *v84; // rsi
  char *v85; // rcx
  volatile signed __int32 *v86; // rbx
  _BYTE *v87; // rcx
  __int64 v88; // rcx
  __int64 v89; // rcx
  char *v90; // rdi
  char *v91; // r14
  volatile signed __int32 *v92; // rbx
  _BYTE *v93; // rcx
  __int64 v94; // rcx
  __int64 v95; // rcx
  int UserDataCount; // [rsp+20h] [rbp-E0h]
  int v97; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v98; // [rsp+48h] [rbp-B8h] BYREF
  char v99; // [rsp+50h] [rbp-B0h] BYREF
  void *Block[2]; // [rsp+58h] [rbp-A8h] BYREF
  char *v101; // [rsp+68h] [rbp-98h]
  __int64 v102; // [rsp+70h] [rbp-90h] BYREF
  HSTRING v103; // [rsp+78h] [rbp-88h] BYREF
  PCWSTR v104; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v105; // [rsp+88h] [rbp-78h] BYREF
  PCWSTR v106; // [rsp+90h] [rbp-70h] BYREF
  HSTRING string; // [rsp+98h] [rbp-68h] BYREF
  int v108[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v109; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v110; // [rsp+B0h] [rbp-50h] BYREF
  void **v111; // [rsp+B8h] [rbp-48h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+C0h] [rbp-40h] BYREF
  char *v113; // [rsp+D0h] [rbp-30h]
  char *v114; // [rsp+D8h] [rbp-28h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING *p_string; // [rsp+F0h] [rbp-10h]
  __int64 v117; // [rsp+F8h] [rbp-8h]
  PCWSTR *v118; // [rsp+100h] [rbp+0h]
  __int64 v119; // [rsp+108h] [rbp+8h]
  PCWSTR v120; // [rsp+110h] [rbp+10h]
  int v121; // [rsp+118h] [rbp+18h]
  int v122; // [rsp+11Ch] [rbp+1Ch]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]
  unsigned int v124; // [rsp+188h] [rbp+88h] BYREF

  v124 = a2;
  v4 = a4;
  v111 = a4;
  v109 = a1;
  string = a3;
  v97 = 0;
  v103 = 0;
  v99 = 0;
  if ( (unsigned int)dword_180175000 > 4 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    LODWORD(v106) = v124;
    if ( StringRawBuffer )
    {
      v6 = -1;
      do
        ++v6;
      while ( StringRawBuffer[v6] );
      v7 = 2 * v6 + 2;
    }
    else
    {
      StringRawBuffer = &word_1801330B0;
      v7 = 2;
    }
    v120 = StringRawBuffer;
    v121 = v7;
    v122 = 0;
    v118 = &v106;
    v119 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 4;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_180175008;
    UserData.Size = *(unsigned __int16 *)off_180175008;
    UserData.Reserved = 2;
    p_string = (HSTRING *)byte_180159541;
    v117 = 0x100000056LL;
    LODWORD(v104) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
  }
  UserData.Ptr = (ULONGLONG)&v97;
  *(_QWORD *)&UserData.Size = &v124;
  p_string = &string;
  v117 = (__int64)&v99;
  v118 = (PCWSTR *)&v109;
  v119 = (__int64)&v103;
  LOBYTE(v120) = 1;
  AllObjectsCacheKey = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache::GetAllObjectsCacheKey(
                         v124,
                         string,
                         &v103);
  v9 = AllObjectsCacheKey;
  v97 = AllObjectsCacheKey;
  if ( AllObjectsCacheKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6EB,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
      (const char *)(unsigned int)AllObjectsCacheKey,
      UserDataCount);
    LOBYTE(v120) = 0;
    lambda_0b5cd7e7fd28f92ba728069fe5e99cbb_::operator()(&UserData);
LABEL_10:
    if ( v103 )
      WindowsDeleteString(v103);
    return (unsigned int)v9;
  }
  v98 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v109 + 48LL))(v109, v103, &v98);
  v97 = v9;
  if ( v9 < 0 )
  {
    v11 = v98;
    if ( v98 )
    {
      v98 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
LABEL_34:
    LOBYTE(v120) = 0;
    lambda_0b5cd7e7fd28f92ba728069fe5e99cbb_::operator()(&UserData);
    goto LABEL_10;
  }
  v102 = 0;
  v110 = 0;
  v105 = 0;
  v12 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v98)(
          v98,
          &GUID_905a0fef_bc53_11df_8c49_001e4fc686da,
          &v102);
  v9 = v12;
  v97 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6F3,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
      (const char *)(unsigned int)v12,
      UserDataCount);
    v13 = v102;
    if ( v102 )
    {
      v102 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v14 = v98;
    if ( v98 )
    {
      v98 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    goto LABEL_34;
  }
  v15 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v102 + 24LL))(v102, &v110);
  v9 = v15;
  v97 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6F4,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
      (const char *)(unsigned int)v15,
      UserDataCount);
    v16 = v102;
    if ( v102 )
    {
      v102 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    v17 = v98;
    if ( v98 )
    {
      v98 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    goto LABEL_34;
  }
  v18 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v98 + 56LL))(v98, &v105);
  v9 = v18;
  v97 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6F5,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
      (const char *)(unsigned int)v18,
      UserDataCount);
    v19 = v102;
    if ( v102 )
    {
      v102 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v20 = v98;
    if ( v98 )
    {
      v98 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    goto LABEL_34;
  }
  *(_OWORD *)Block = 0;
  v101 = 0;
  v21 = 0;
  v104 = 0;
  v22 = v105;
  *(_QWORD *)&EventDescriptor.Id = v105;
  v23 = v110;
  v99 = 1;
  if ( !v105 )
  {
LABEL_88:
    if ( v21 + 2 < v21 )
    {
      v97 = -2147024362;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x71B,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
        (const char *)0x80070216LL,
        UserDataCount);
      v90 = (char *)Block[0];
      if ( Block[0] )
      {
        v91 = (char *)Block[1];
        if ( Block[0] != Block[1] )
        {
          do
          {
            v92 = (volatile signed __int32 *)*((_QWORD *)v90 + 1);
            if ( v92 )
            {
              if ( _InterlockedExchangeAdd(v92 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v92)(v92);
                if ( _InterlockedExchangeAdd(v92 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v92 + 8LL))(v92);
              }
            }
            v90 += 16;
          }
          while ( v90 != v91 );
          v90 = (char *)Block[0];
        }
        if ( ((v101 - v90) & 0xFFFFFFFFFFFFFFF0uLL) < 0x1000 )
        {
          v93 = v90;
        }
        else
        {
          v93 = (_BYTE *)*((_QWORD *)v90 - 1);
          if ( (unsigned __int64)(v90 - v93 - 8) > 0x1F )
            goto LABEL_230;
        }
        operator delete(v93);
        *(_OWORD *)Block = 0;
        v101 = 0;
      }
      v94 = v102;
      if ( v102 )
      {
        v102 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
      }
      v95 = v98;
      if ( v98 )
      {
        v98 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
      }
      LOBYTE(v120) = 0;
      lambda_0b5cd7e7fd28f92ba728069fe5e99cbb_::operator()(&UserData);
      if ( v103 )
        WindowsDeleteString(v103);
      return 2147942934LL;
    }
    else if ( v21 + 2 == v22 )
    {
      if ( Block == v4 )
      {
        v84 = (char *)Block[1];
        v82 = (char *)Block[0];
      }
      else
      {
        v81 = (char *)Block[0];
        v82 = (char *)*v4;
        Block[0] = *v4;
        *v4 = v81;
        v83 = (char *)Block[1];
        v84 = (char *)v4[1];
        Block[1] = v84;
        v4[1] = v83;
        v85 = v101;
        v101 = (char *)v4[2];
        v4[2] = v85;
      }
      v97 = 0;
      if ( v82 )
      {
        if ( v82 != v84 )
        {
          do
          {
            v86 = (volatile signed __int32 *)*((_QWORD *)v82 + 1);
            if ( v86 )
            {
              if ( _InterlockedExchangeAdd(v86 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v86)(v86);
                if ( _InterlockedExchangeAdd(v86 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v86 + 8LL))(v86);
              }
            }
            v82 += 16;
          }
          while ( v82 != v84 );
          v82 = (char *)Block[0];
        }
        if ( ((v101 - v82) & 0xFFFFFFFFFFFFFFF0uLL) < 0x1000 )
        {
          v87 = v82;
        }
        else
        {
          v87 = (_BYTE *)*((_QWORD *)v82 - 1);
          if ( (unsigned __int64)(v82 - v87 - 8) > 0x1F )
            goto LABEL_230;
        }
        operator delete(v87);
        *(_OWORD *)Block = 0;
        v101 = 0;
      }
      v88 = v102;
      if ( v102 )
      {
        v102 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
      }
      v89 = v98;
      if ( v98 )
      {
        v98 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
      }
      LOBYTE(v120) = 0;
      lambda_0b5cd7e7fd28f92ba728069fe5e99cbb_::operator()(&UserData);
      if ( v103 )
        WindowsDeleteString(v103);
      return 0;
    }
    else
    {
      v97 = -2147024883;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x723,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
        (const char *)0x8007000DLL,
        UserDataCount);
      v51 = (char *)Block[0];
      if ( Block[0] )
      {
        v52 = (char *)Block[1];
        if ( Block[0] != Block[1] )
        {
          do
          {
            v53 = (volatile signed __int32 *)*((_QWORD *)v51 + 1);
            if ( v53 )
            {
              if ( _InterlockedExchangeAdd(v53 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v53)(v53);
                if ( _InterlockedExchangeAdd(v53 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v53 + 8LL))(v53);
              }
            }
            v51 += 16;
          }
          while ( v51 != v52 );
          v51 = (char *)Block[0];
        }
        if ( ((v101 - v51) & 0xFFFFFFFFFFFFFFF0uLL) < 0x1000 )
        {
          v54 = v51;
        }
        else
        {
          v54 = (_BYTE *)*((_QWORD *)v51 - 1);
          if ( (unsigned __int64)(v51 - v54 - 8) > 0x1F )
            goto LABEL_230;
        }
        operator delete(v54);
        *(_OWORD *)Block = 0;
        v101 = 0;
      }
      v79 = v102;
      if ( v102 )
      {
        v102 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
      }
      v80 = v98;
      if ( v98 )
      {
        v98 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
      }
      LOBYTE(v120) = 0;
      lambda_0b5cd7e7fd28f92ba728069fe5e99cbb_::operator()(&UserData);
      if ( v103 )
        WindowsDeleteString(v103);
      return 2147942413LL;
    }
  }
  while ( 1 )
  {
    if ( !*v23 )
    {
LABEL_87:
      v4 = v111;
      goto LABEL_88;
    }
    v24 = (char *)operator new(0x38u);
    *(_QWORD *)v108 = v24;
    *(_OWORD *)v24 = 0;
    *((_DWORD *)v24 + 2) = 1;
    *((_DWORD *)v24 + 3) = 1;
    *(_QWORD *)v24 = &std::_Ref_count_obj2<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId>::`vftable';
    v25 = v24 + 16;
    *((_QWORD *)v24 + 2) = 0;
    *((_DWORD *)v24 + 6) = 0;
    *((_QWORD *)v24 + 4) = 0;
    *((_QWORD *)v24 + 5) = 0;
    *((_QWORD *)v24 + 6) = 0;
    v113 = v24 + 16;
    v114 = v24;
    v27 = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InitializeFromCryptString(
            (Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)(v24 + 16),
            v23,
            v26);
    v28 = v27;
    v97 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x707,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
        (const char *)(unsigned int)v27,
        UserDataCount);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(void *))v24)(v24);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v24 + 8LL))(v24);
      }
      v73 = (char *)Block[0];
      if ( Block[0] )
      {
        v74 = (char *)Block[1];
        if ( Block[0] != Block[1] )
        {
          do
          {
            v75 = (volatile signed __int32 *)*((_QWORD *)v73 + 1);
            if ( v75 )
            {
              if ( _InterlockedExchangeAdd(v75 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v75)(v75);
                if ( _InterlockedExchangeAdd(v75 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v75 + 8LL))(v75);
              }
            }
            v73 += 16;
          }
          while ( v73 != v74 );
          v73 = (char *)Block[0];
        }
        if ( ((v101 - v73) & 0xFFFFFFFFFFFFFFF0uLL) < 0x1000 )
        {
          v76 = v73;
        }
        else
        {
          v76 = (_BYTE *)*((_QWORD *)v73 - 1);
          if ( (unsigned __int64)(v73 - v76 - 8) > 0x1F )
            goto LABEL_230;
        }
        operator delete(v76);
        *(_OWORD *)Block = 0;
        v101 = 0;
      }
      v77 = v102;
      if ( v102 )
      {
        v102 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
      }
      v78 = v98;
      if ( v98 )
      {
        v98 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
      }
      goto LABEL_185;
    }
    v29 = Block[1];
    if ( Block[1] != v101 )
    {
      *(_QWORD *)Block[1] = 0;
      v29[1] = 0;
      _InterlockedIncrement((volatile signed __int32 *)v24 + 2);
      *v29 = v25;
      v29[1] = v24;
      Block[1] = (char *)Block[1] + 16;
      goto LABEL_76;
    }
    v30 = ((char *)Block[1] - (char *)Block[0]) >> 4;
    if ( v30 == 0xFFFFFFFFFFFFFFFLL )
      std::vector<std::shared_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId>>::_Xlength();
    v31 = (v101 - (char *)Block[0]) >> 4;
    v32 = v31 >> 1;
    if ( v31 > 0xFFFFFFFFFFFFFFFLL - (v31 >> 1) )
      goto LABEL_241;
    v106 = (PCWSTR)(v30 + 1);
    v33 = v30 + 1;
    if ( v32 + v31 >= v30 + 1 )
      v33 = v32 + v31;
    if ( v33 > 0xFFFFFFFFFFFFFFFLL )
LABEL_241:
      std::_Throw_bad_array_new_length();
    v34 = 16 * v33;
    if ( v34 )
    {
      if ( v34 < 0x1000 )
      {
        v35 = operator new(v34);
      }
      else
      {
        if ( v34 + 39 < v34 )
          goto LABEL_241;
        v36 = operator new(v34 + 39);
        if ( !v36 )
LABEL_101:
          __fastfail(5u);
        v35 = (_QWORD *)(((unsigned __int64)v36 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v35 - 1) = v36;
      }
    }
    else
    {
      v35 = 0;
    }
    v37 = &v35[2 * v30];
    *v37 = 0;
    v37[1] = 0;
    _InterlockedIncrement((volatile signed __int32 *)v24 + 2);
    *v37 = v25;
    v37[1] = v24;
    v38 = Block[1];
    v39 = v35;
    v40 = Block[0];
    if ( v29 != Block[1] )
    {
      if ( Block[0] != v29 )
      {
        do
        {
          *v39 = 0;
          v39[1] = 0;
          *v39 = *v40;
          v39[1] = v40[1];
          *v40 = 0;
          v40[1] = 0;
          v39 += 2;
          v40 += 2;
        }
        while ( v40 != v29 );
        v38 = Block[1];
        v40 = Block[0];
      }
      v41 = v37 + 2;
      if ( v29 == v38 )
        goto LABEL_62;
      do
      {
        *v41 = 0;
        v41[1] = 0;
        *v41 = *v29;
        v41[1] = v29[1];
        *v29 = 0;
        v29[1] = 0;
        v41 += 2;
        v29 += 2;
      }
      while ( v29 != v38 );
      goto LABEL_61;
    }
    if ( Block[0] != Block[1] )
    {
      do
      {
        *v39 = 0;
        v39[1] = 0;
        *v39 = *v40;
        v39[1] = v40[1];
        *v40 = 0;
        v40[1] = 0;
        v39 += 2;
        v40 += 2;
      }
      while ( v40 != v38 );
LABEL_61:
      v40 = Block[0];
      v38 = Block[1];
    }
LABEL_62:
    if ( v40 )
    {
      if ( v40 != v38 )
      {
        do
        {
          v42 = (volatile signed __int32 *)v40[1];
          if ( v42 )
          {
            if ( _InterlockedExchangeAdd(v42 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v42)(v42);
              if ( _InterlockedExchangeAdd(v42 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v42 + 8LL))(v42);
            }
          }
          v40 += 2;
        }
        while ( v40 != v38 );
        v40 = Block[0];
      }
      if ( ((v101 - (char *)v40) & 0xFFFFFFFFFFFFFFF0uLL) < 0x1000 )
      {
        v43 = v40;
      }
      else
      {
        v43 = (_BYTE *)*(v40 - 1);
        if ( (unsigned __int64)((char *)v40 - v43 - 8) > 0x1F )
          goto LABEL_101;
      }
      operator delete(v43);
    }
    Block[0] = v35;
    Block[1] = &v35[2 * (_QWORD)v106];
    v101 = (char *)&v35[v34 / 8];
    v21 = (unsigned __int64)v104;
LABEL_76:
    if ( (unsigned int)dword_180175000 > 5 )
    {
      v104 = WindowsGetStringRawBuffer(v103, 0);
      v106 = WindowsGetStringRawBuffer(string, 0);
      *(_QWORD *)v108 = v23;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v44,
        (unsigned int)&byte_1801596AF,
        v45,
        v46,
        (__int64)v108,
        (__int64)&v106,
        (__int64)&v104);
    }
    v47 = -1;
    do
      ++v47;
    while ( v23[v47] );
    v48 = v47 + 1;
    if ( v47 + 1 < v47 )
      break;
    *(_QWORD *)v108 = 0;
    v49 = 2 * v48;
    if ( !is_mul_ok(v48, 2u) )
    {
      v97 = -2147024362;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x717,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
        (const char *)0x80070216LL,
        UserDataCount);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(void *))v24)(v24);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v24 + 8LL))(v24);
      }
      v28 = -2147024362;
      v61 = (char *)Block[0];
      if ( Block[0] )
      {
        v62 = (char *)Block[1];
        if ( Block[0] != Block[1] )
        {
          do
          {
            v63 = (volatile signed __int32 *)*((_QWORD *)v61 + 1);
            if ( v63 )
            {
              if ( _InterlockedExchangeAdd(v63 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v63)(v63);
                if ( _InterlockedExchangeAdd(v63 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v63 + 8LL))(v63);
              }
            }
            v61 += 16;
          }
          while ( v61 != v62 );
          v61 = (char *)Block[0];
        }
        if ( ((v101 - v61) & 0xFFFFFFFFFFFFFFF0uLL) < 0x1000 )
        {
          v64 = v61;
        }
        else
        {
          v64 = (_BYTE *)*((_QWORD *)v61 - 1);
          if ( (unsigned __int64)(v61 - v64 - 8) > 0x1F )
            goto LABEL_230;
        }
        operator delete(v64);
        *(_OWORD *)Block = 0;
        v101 = 0;
      }
      v65 = v102;
      if ( v102 )
      {
        v102 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
      }
      v66 = v98;
      if ( v98 )
      {
        v98 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
      }
      goto LABEL_185;
    }
    v50 = (const WCHAR *)(v49 + v21);
    if ( v49 + v21 < v21 )
    {
      v97 = -2147024362;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x718,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
        (const char *)0x80070216LL,
        UserDataCount);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(void *))v24)(v24);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v24 + 8LL))(v24);
      }
      v28 = -2147024362;
      v55 = (char *)Block[0];
      if ( Block[0] )
      {
        v56 = (char *)Block[1];
        if ( Block[0] != Block[1] )
        {
          do
          {
            v57 = (volatile signed __int32 *)*((_QWORD *)v55 + 1);
            if ( v57 )
            {
              if ( _InterlockedExchangeAdd(v57 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v57)(v57);
                if ( _InterlockedExchangeAdd(v57 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v57 + 8LL))(v57);
              }
            }
            v55 += 16;
          }
          while ( v55 != v56 );
          v55 = (char *)Block[0];
        }
        if ( ((v101 - v55) & 0xFFFFFFFFFFFFFFF0uLL) < 0x1000 )
        {
          v58 = v55;
        }
        else
        {
          v58 = (_BYTE *)*((_QWORD *)v55 - 1);
          if ( (unsigned __int64)(v55 - v58 - 8) > 0x1F )
            goto LABEL_230;
        }
        operator delete(v58);
        *(_OWORD *)Block = 0;
        v101 = 0;
      }
      v59 = v102;
      if ( v102 )
      {
        v102 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
      }
      v60 = v98;
      if ( v98 )
      {
        v98 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
      }
      goto LABEL_185;
    }
    v23 += v48;
    v97 = 0;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(void *))v24)(v24);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v24 + 8LL))(v24);
    }
    v21 = (unsigned __int64)v50;
    v104 = v50;
    v22 = *(_QWORD *)&EventDescriptor.Id;
    if ( (unsigned __int64)v50 >= *(_QWORD *)&EventDescriptor.Id )
      goto LABEL_87;
  }
  v97 = -2147024362;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x713,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
    (const char *)0x80070216LL,
    UserDataCount);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(void *))v24)(v24);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v24 + 8LL))(v24);
  }
  v28 = -2147024362;
  v67 = (char *)Block[0];
  if ( Block[0] )
  {
    v68 = (char *)Block[1];
    if ( Block[0] != Block[1] )
    {
      do
      {
        v69 = (volatile signed __int32 *)*((_QWORD *)v67 + 1);
        if ( v69 )
        {
          if ( _InterlockedExchangeAdd(v69 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v69)(v69);
            if ( _InterlockedExchangeAdd(v69 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v69 + 8LL))(v69);
          }
        }
        v67 += 16;
      }
      while ( v67 != v68 );
      v67 = (char *)Block[0];
    }
    if ( ((v101 - v67) & 0xFFFFFFFFFFFFFFF0uLL) < 0x1000 )
    {
      v70 = v67;
      goto LABEL_159;
    }
    v70 = (void *)*((_QWORD *)v67 - 1);
    if ( (unsigned __int64)(v67 - (_BYTE *)v70 - 8) <= 0x1F )
    {
LABEL_159:
      operator delete(v70);
      *(_OWORD *)Block = 0;
      v101 = 0;
      goto LABEL_160;
    }
LABEL_230:
    __fastfail(5u);
  }
LABEL_160:
  v71 = v102;
  if ( v102 )
  {
    v102 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
  }
  v72 = v98;
  if ( v98 )
  {
    v98 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
  }
LABEL_185:
  LOBYTE(v120) = 0;
  lambda_0b5cd7e7fd28f92ba728069fe5e99cbb_::operator()(&UserData);
  if ( v103 )
    WindowsDeleteString(v103);
  return v28;
}

```

## disassembly

```asm
0x180076f60  mov     [rsp-8+arg_8], edx
0x180076f64  push    rbp
0x180076f65  push    rbx
0x180076f66  push    rsi
0x180076f67  push    rdi
0x180076f68  push    r12
0x180076f6a  push    r13
0x180076f6c  push    r14
0x180076f6e  push    r15
0x180076f70  lea     rbp, [rsp-38h]
0x180076f75  sub     rsp, 138h
0x180076f7c  mov     rax, cs:__security_cookie
0x180076f83  xor     rax, rsp
0x180076f86  mov     [rbp+70h+var_50], rax
0x180076f8a  mov     r14, r9
0x180076f8d  mov     [rbp+70h+var_B8], r9
0x180076f91  mov     [rbp+70h+var_C8], rcx
0x180076f95  mov     [rbp+70h+string], r8
0x180076f99  xor     r15d, r15d
0x180076f9c  mov     [rsp+170h+var_130], r15d
0x180076fa1  mov     [rsp+170h+var_F8], r15
0x180076fa6  mov     [rsp+170h+var_120], r15b
0x180076fab  mov     eax, cs:dword_180175000
0x180076fb1  cmp     eax, 4
0x180076fb4  jbe     loc_18007709F
0x180076fba  xor     edx, edx; length
0x180076fbc  mov     rcx, [rbp+70h+string]; string
0x180076fc0  call    cs:__imp_WindowsGetStringRawBuffer
0x180076fc6  mov     ecx, [rbp+70h+arg_8]
0x180076fcc  mov     dword ptr [rbp+70h+var_E0], ecx
0x180076fcf  test    rax, rax
0x180076fd2  jz      short loc_180076FF4
0x180076fd4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180076fdb  nop     dword ptr [rax+rax+00h]
0x180076fe0  lea     rcx, [rcx+1]
0x180076fe4  cmp     word ptr [rax+rcx*2], 0
0x180076fe9  jnz     short loc_180076FE0
0x180076feb  lea     ecx, ds:2[rcx*2]
0x180076ff2  jmp     short loc_180077000
0x180076ff4  lea     rax, word_1801330B0
0x180076ffb  mov     ecx, 2
0x180077000  mov     [rbp+70h+var_60], rax
0x180077004  mov     [rbp+70h+var_58], ecx
0x180077007  mov     [rbp+70h+var_54], r15d
0x18007700b  lea     rax, [rbp+70h+var_E0]
0x18007700f  mov     [rbp+70h+var_70], rax
0x180077013  mov     [rbp+70h+var_68], 4
0x18007701b  mov     dword ptr [rbp+70h+EventDescriptor.Id], 0B000000h
0x180077022  movzx   eax, cs:word_180159537
0x180077029  mov     dword ptr [rbp+70h+EventDescriptor.Level], eax
0x18007702c  mov     [rbp+70h+EventDescriptor.Keyword], r15
0x180077030  mov     rax, cs:off_180175008
0x180077037  mov     [rbp+70h+var_90.Ptr], rax
0x18007703b  movzx   eax, word ptr [rax]
0x18007703e  mov     [rbp+70h+var_90.Size], eax
0x180077041  mov     dword ptr [rbp+70h+var_90.0Ch], 2
0x180077048  lea     rax, byte_180159541
0x18007704f  mov     [rbp+70h+var_80], rax
0x180077053  mov     dword ptr [rbp+70h+var_78], 56h ; 'V'
0x18007705a  mov     dword ptr [rbp+70h+var_78+4], 1
0x180077061  lea     rax, _TraceLoggingMetadataEnd
0x180077068  lea     rcx, _TraceLoggingMetadata
0x18007706f  sub     eax, ecx
0x180077071  mov     dword ptr [rbp+70h+var_F0], eax
0x180077074  mov     eax, dword ptr [rbp+70h+var_F0]
0x180077077  lea     rax, [rbp+70h+var_90]
0x18007707b  mov     [rsp+170h+UserData], rax; UserData
0x180077080  mov     [rsp+170h+UserDataCount], 4; int
0x180077088  xor     r9d, r9d; RelatedActivityId
0x18007708b  xor     r8d, r8d; ActivityId
0x18007708e  lea     rdx, [rbp+70h+EventDescriptor]; EventDescriptor
0x180077092  mov     rcx, cs:RegHandle; RegHandle
0x180077099  call    cs:__imp_EventWriteTransfer
0x18007709f  lea     rax, [rsp+170h+var_130]
0x1800770a4  mov     [rbp+70h+var_90.Ptr], rax
0x1800770a8  lea     rax, [rbp+70h+arg_8]
0x1800770af  mov     qword ptr [rbp+70h+var_90.Size], rax
0x1800770b3  lea     rax, [rbp+70h+string]
0x1800770b7  mov     [rbp+70h+var_80], rax
0x1800770bb  lea     rax, [rsp+170h+var_120]
0x1800770c0  mov     [rbp+70h+var_78], rax
0x1800770c4  lea     rax, [rbp+70h+var_C8]
0x1800770c8  mov     [rbp+70h+var_70], rax
0x1800770cc  lea     rax, [rsp+170h+var_F8]
0x1800770d1  mov     [rbp+70h+var_68], rax
0x1800770d5  mov     byte ptr [rbp+70h+var_60], 1
0x1800770d9  lea     r8, [rsp+170h+var_F8]
0x1800770de  mov     rdx, [rbp+70h+string]
0x1800770e2  mov     ecx, [rbp+70h+arg_8]
0x1800770e8  call    ?GetAllObjectsCacheKey@StoredObjectInfoWithCache@TokenBroker@Authentication@Security@Internal@Windows@@SAJW4StoredObjectType@23456@QEAUHSTRING__@@AEAVString@56@@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache::GetAllObjectsCacheKey(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectType,HSTRING__ * const,Windows::Internal::String &)
0x1800770ed  mov     ebx, eax
0x1800770ef  mov     [rsp+170h+var_130], eax
0x1800770f3  test    eax, eax
0x1800770f5  jns     short loc_180077135
0x1800770f7  mov     rcx, [rbp+78h]; this
0x1800770fb  mov     r9d, eax; char *
0x1800770fe  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180077105  mov     edx, 6EBh; void *
0x18007710a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007710f  nop
0x180077110  mov     byte ptr [rbp+70h+var_60], 0
0x180077114  lea     rcx, [rbp+70h+var_90]
0x180077118  call    _lambda_0b5cd7e7fd28f92ba728069fe5e99cbb___operator__
0x18007711d  nop
0x18007711e  mov     rcx, [rsp+170h+var_F8]; string
0x180077123  test    rcx, rcx
0x180077126  jz      short loc_18007712E
0x180077128  call    cs:__imp_WindowsDeleteString
0x18007712e  mov     eax, ebx
0x180077130  jmp     loc_1800780C3
0x180077135  mov     [rsp+170h+var_128], r15
0x18007713a  mov     rcx, [rbp+70h+var_C8]
0x18007713e  mov     rax, [rcx]
0x180077141  lea     r8, [rsp+170h+var_128]
0x180077146  mov     rdx, [rsp+170h+var_F8]
0x18007714b  mov     rax, [rax+30h]
0x18007714f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077154  mov     ebx, eax
0x180077156  mov     [rsp+170h+var_130], eax
0x18007715a  test    eax, eax
0x18007715c  jns     short loc_18007718A
0x18007715e  mov     rcx, [rsp+170h+var_128]
0x180077163  test    rcx, rcx
0x180077166  jz      short loc_18007717A
0x180077168  mov     [rsp+170h+var_128], r15
0x18007716d  mov     rdx, [rcx]
0x180077170  mov     rax, [rdx+10h]
0x180077174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077179  nop
0x18007717a  mov     byte ptr [rbp+70h+var_60], 0
0x18007717e  lea     rcx, [rbp+70h+var_90]
0x180077182  call    _lambda_0b5cd7e7fd28f92ba728069fe5e99cbb___operator__
0x180077187  nop
0x180077188  jmp     short loc_18007711E
0x18007718a  mov     [rsp+170h+var_100], r15
0x18007718f  mov     [rbp+70h+var_C0], r15
0x180077193  mov     [rbp+70h+var_E8], r15d
0x180077197  mov     rcx, [rsp+170h+var_128]
0x18007719c  mov     rax, [rcx]
0x18007719f  lea     r8, [rsp+170h+var_100]
0x1800771a4  lea     rdx, _GUID_905a0fef_bc53_11df_8c49_001e4fc686da
0x1800771ab  mov     rax, [rax]
0x1800771ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800771b3  mov     ebx, eax
0x1800771b5  mov     [rsp+170h+var_130], eax
0x1800771b9  test    eax, eax
0x1800771bb  jns     short loc_180077221
0x1800771bd  mov     rcx, [rbp+78h]; this
0x1800771c1  mov     r9d, eax; char *
0x1800771c4  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x1800771cb  mov     edx, 6F3h; void *
0x1800771d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800771d5  nop
0x1800771d6  mov     rcx, [rsp+170h+var_100]
0x1800771db  test    rcx, rcx
0x1800771de  jz      short loc_1800771F2
0x1800771e0  mov     [rsp+170h+var_100], r15
0x1800771e5  mov     rax, [rcx]
0x1800771e8  mov     rax, [rax+10h]
0x1800771ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800771f1  nop
0x1800771f2  mov     rcx, [rsp+170h+var_128]
0x1800771f7  test    rcx, rcx
0x1800771fa  jz      short loc_18007720E
0x1800771fc  mov     [rsp+170h+var_128], r15
0x180077201  mov     rax, [rcx]
0x180077204  mov     rax, [rax+10h]
0x180077208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007720d  nop
0x18007720e  mov     byte ptr [rbp+70h+var_60], 0
0x180077212  lea     rcx, [rbp+70h+var_90]
0x180077216  call    _lambda_0b5cd7e7fd28f92ba728069fe5e99cbb___operator__
0x18007721b  nop
0x18007721c  jmp     loc_18007711E
0x180077221  mov     rcx, [rsp+170h+var_100]
0x180077226  mov     rax, [rcx]
0x180077229  lea     rdx, [rbp+70h+var_C0]
0x18007722d  mov     rax, [rax+18h]
0x180077231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077236  mov     ebx, eax
0x180077238  mov     [rsp+170h+var_130], eax
0x18007723c  test    eax, eax
0x18007723e  jns     short loc_1800772A4
0x180077240  mov     rcx, [rbp+78h]; this
0x180077244  mov     r9d, eax; char *
0x180077247  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18007724e  mov     edx, 6F4h; void *
0x180077253  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077258  nop
0x180077259  mov     rcx, [rsp+170h+var_100]
0x18007725e  test    rcx, rcx
0x180077261  jz      short loc_180077275
0x180077263  mov     [rsp+170h+var_100], r15
0x180077268  mov     rax, [rcx]
0x18007726b  mov     rax, [rax+10h]
0x18007726f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077274  nop
0x180077275  mov     rcx, [rsp+170h+var_128]
0x18007727a  test    rcx, rcx
0x18007727d  jz      short loc_180077291
0x18007727f  mov     [rsp+170h+var_128], r15
0x180077284  mov     rax, [rcx]
0x180077287  mov     rax, [rax+10h]
0x18007728b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077290  nop
0x180077291  mov     byte ptr [rbp+70h+var_60], 0
0x180077295  lea     rcx, [rbp+70h+var_90]
0x180077299  call    _lambda_0b5cd7e7fd28f92ba728069fe5e99cbb___operator__
0x18007729e  nop
0x18007729f  jmp     loc_18007711E
0x1800772a4  mov     rcx, [rsp+170h+var_128]
0x1800772a9  mov     rax, [rcx]
0x1800772ac  lea     rdx, [rbp+70h+var_E8]
0x1800772b0  mov     rax, [rax+38h]
0x1800772b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800772b9  mov     ebx, eax
0x1800772bb  mov     [rsp+170h+var_130], eax
0x1800772bf  test    eax, eax
0x1800772c1  jns     short loc_180077327
0x1800772c3  mov     rcx, [rbp+78h]; this
0x1800772c7  mov     r9d, eax; char *
0x1800772ca  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x1800772d1  mov     edx, 6F5h; void *
0x1800772d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800772db  nop
0x1800772dc  mov     rcx, [rsp+170h+var_100]
0x1800772e1  test    rcx, rcx
0x1800772e4  jz      short loc_1800772F8
0x1800772e6  mov     [rsp+170h+var_100], r15
0x1800772eb  mov     rax, [rcx]
0x1800772ee  mov     rax, [rax+10h]
0x1800772f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800772f7  nop
0x1800772f8  mov     rcx, [rsp+170h+var_128]
0x1800772fd  test    rcx, rcx
0x180077300  jz      short loc_180077314
0x180077302  mov     [rsp+170h+var_128], r15
0x180077307  mov     rax, [rcx]
0x18007730a  mov     rax, [rax+10h]
0x18007730e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077313  nop
0x180077314  mov     byte ptr [rbp+70h+var_60], 0
0x180077318  lea     rcx, [rbp+70h+var_90]
0x18007731c  call    _lambda_0b5cd7e7fd28f92ba728069fe5e99cbb___operator__
0x180077321  nop
0x180077322  jmp     loc_18007711E
0x180077327  xorps   xmm0, xmm0
0x18007732a  movdqu  xmmword ptr [rsp+170h+Block], xmm0
0x180077330  mov     [rsp+170h+var_108], r15
0x180077335  mov     r13, r15
0x180077338  mov     [rbp+70h+var_F0], r15
0x18007733c  mov     ecx, [rbp+70h+var_E8]
0x18007733f  mov     qword ptr [rbp+70h+EventDescriptor.Id], rcx
0x180077343  mov     r12, [rbp+70h+var_C0]
0x180077347  mov     [rsp+170h+var_120], 1
0x18007734c  test    rcx, rcx
0x18007734f  jz      loc_180077738
0x180077355  lea     rbx, ??_7?$_Ref_count_obj2@VStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@@std@@6B@; const std::_Ref_count_obj2<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId>::`vftable'
0x18007735c  cmp     word ptr [r12], 0
0x180077362  jz      loc_180077734
0x180077368  mov     ecx, 38h ; '8'; Size
0x18007736d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180077372  mov     r14, rax
0x180077375  mov     qword ptr [rbp+70h+var_D0], rax
0x180077379  xorps   xmm0, xmm0
0x18007737c  movups  xmmword ptr [rax], xmm0
0x18007737f  mov     dword ptr [rax+8], 1
0x180077386  mov     dword ptr [rax+0Ch], 1
0x18007738d  mov     [rax], rbx
0x180077390  lea     rsi, [rax+10h]
0x180077394  mov     [rsi], r15
0x180077397  mov     [rsi+8], r15d
0x18007739b  mov     [rsi+10h], r15
0x18007739f  mov     [rsi+18h], r15
0x1800773a3  mov     [rsi+20h], r15
0x1800773a7  mov     [rbp+70h+var_A0], rsi
0x1800773ab  mov     [rbp+70h+var_98], rax
0x1800773af  mov     rdx, r12; unsigned __int16 *
0x1800773b2  mov     rcx, rsi; this
0x1800773b5  call    ?InitializeFromCryptString@StoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@AEAAJPEBGK@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InitializeFromCryptString(ushort const *,ulong)
0x1800773ba  mov     r15d, eax
0x1800773bd  mov     [rsp+170h+var_130], eax
0x1800773c1  test    eax, eax
0x1800773c3  js      loc_180077C59
0x1800773c9  mov     rdi, [rsp+170h+Block+8]
0x1800773ce  mov     rcx, [rsp+170h+var_108]
0x1800773d3  cmp     rdi, rcx
0x1800773d6  jz      short loc_1800773F9
0x1800773d8  xor     r15d, r15d
0x1800773db  mov     [rdi], r15
0x1800773de  mov     [rdi+8], r15
0x1800773e2  lock inc dword ptr [r14+8]
0x1800773e7  mov     [rdi], rsi
0x1800773ea  mov     [rdi+8], r14
0x1800773ee  add     [rsp+170h+Block+8], 10h
0x1800773f4  jmp     loc_180077640
0x1800773f9  mov     rbx, rdi
0x1800773fc  mov     rax, [rsp+170h+Block]
0x180077401  sub     rbx, rax
0x180077404  sar     rbx, 4
  ... truncated ...
```
