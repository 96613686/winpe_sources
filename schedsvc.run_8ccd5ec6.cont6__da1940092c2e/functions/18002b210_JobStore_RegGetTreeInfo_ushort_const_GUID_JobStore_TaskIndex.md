# JobStore::RegGetTreeInfo(ushort const *,_GUID *,JobStore::TaskIndex *)

- ea: `0x18002b210`
- end: `0x18002bdd4`
- name: `?RegGetTreeInfo@JobStore@@QEBAJPEBGPEAU_GUID@@PEAW4TaskIndex@1@@Z`
- size: `3012`
- prototype: `int(JobStore *__hidden this, const unsigned __int16 *, struct _GUID *, enum JobStore::TaskIndex *)`
- caller_count: `12`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000ff40`
- `0x180011ed0`
- `0x1800141e0`
- `0x18001d67c`
- `0x18001d7ac`
- `0x180023c4c`
- `0x180027990`
- `0x18002bde0`
- `0x18002c470`
- `0x180031cf0`
- `0x180047ee0`
- `0x18004e9d0`

## callees

- `0x18000cc40`
- `0x18002b210`
- `0x18002db40`
- `0x180054824`
- `0x180056714`
- `0x180059140`
- `0x18005a2bc`
- `0x18005a2d6`
- `0x180082a40`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002b2a8`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b4af`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b670`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b2a8`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b4af`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b670`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b7b0`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b873`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b8e7`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b92c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b971`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b9b6`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b7b0`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b873`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b8e7`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b92c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b971`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b9b6`
- `OLEAUT32!__imp_SysStringLen` at `0x18002b511`
- `OLEAUT32!__imp_SysStringLen` at `0x18002b52f`
- `OLEAUT32!__imp_SysStringLen` at `0x18002b6d2`
- `OLEAUT32!__imp_SysStringLen` at `0x18002b6ed`
- `OLEAUT32!__imp_SysStringLen` at `0x18002b511`
- `OLEAUT32!__imp_SysStringLen` at `0x18002b52f`
- `OLEAUT32!__imp_SysStringLen` at `0x18002b6d2`
- `OLEAUT32!__imp_SysStringLen` at `0x18002b6ed`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18002b5b6`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18002b725`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18002b5b6`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18002b725`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b316`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b316`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b3b4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ba31`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b3b4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ba31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b355`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b3fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b45c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ba71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b355`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b3fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b45c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ba71`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b7dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b89f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b913`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b958`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b99d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b9e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b7dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b89f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b913`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b958`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b99d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b9e2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b27a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b47c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b4da`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b642`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b69b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b27a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b47c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b4da`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b642`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b69b`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18002b586`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18002b586`

## string_xrefs

- `0x18002b2a1`: `TaskCache\Tree`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall JobStore::RegGetTreeInfo(
        JobStore *this,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        enum JobStore::TaskIndex *a4)
{
  enum JobStore::TaskIndex *v4; // r12
  GUID *v5; // r15
  JobStore *v7; // rsi
  HKEY v8; // rdi
  BSTR *v9; // rax
  BSTR *v10; // rbx
  BSTR v11; // rax
  struct IErrorInfo *v12; // rdx
  unsigned __int16 v13; // ax
  const OLECHAR *v14; // r12
  const WCHAR *v15; // rdx
  LSTATUS v16; // eax
  int v17; // esi
  LSTATUS v18; // eax
  HKEY v20; // rcx
  BSTR *v21; // rax
  BSTR *v22; // rsi
  BSTR v23; // rax
  struct IErrorInfo *v24; // rdx
  BSTR *v25; // rax
  BSTR *v26; // r15
  unsigned __int64 v27; // rdx
  UINT v28; // eax
  unsigned int v29; // eax
  BSTR v30; // rax
  struct IErrorInfo *v31; // rdx
  BSTR *v32; // rax
  BSTR *v33; // rsi
  BSTR v34; // rax
  struct IErrorInfo *v35; // rdx
  BSTR *v36; // rax
  struct IErrorInfo *v37; // rdx
  UINT v38; // r12d
  UINT v39; // eax
  UINT v40; // eax
  struct IErrorInfo *v41; // rdx
  BSTR v42; // rcx
  BSTR v43; // rcx
  BSTR v44; // rcx
  BSTR v45; // rcx
  BSTR v46; // rcx
  BSTR v47; // rcx
  BSTR v48; // rcx
  LSTATUS v49; // eax
  unsigned int v50; // ebx
  _QWORD *v51; // rcx
  int v52; // edx
  BYTE *v53; // r9
  unsigned int v54; // [rsp+30h] [rbp-D0h]
  UINT v55; // [rsp+30h] [rbp-D0h]
  DWORD lpcbData[2]; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  BYTE v58[4]; // [rsp+44h] [rbp-BCh] BYREF
  void **pExceptionObject; // [rsp+48h] [rbp-B8h] BYREF
  char v60; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v61; // [rsp+58h] [rbp-A8h]
  __int64 v62; // [rsp+60h] [rbp-A0h]
  __int64 v63; // [rsp+68h] [rbp-98h]
  int v64; // [rsp+70h] [rbp-90h]
  __int64 v65; // [rsp+74h] [rbp-8Ch]
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  DWORD cbData; // [rsp+88h] [rbp-78h] BYREF
  enum JobStore::TaskIndex *v68; // [rsp+90h] [rbp-70h]
  JobStore *v69; // [rsp+98h] [rbp-68h]
  struct _GUID *v70; // [rsp+A0h] [rbp-60h]
  HKEY v71; // [rsp+A8h] [rbp-58h] BYREF
  BSTR *v72; // [rsp+B0h] [rbp-50h]
  BSTR *v73; // [rsp+B8h] [rbp-48h]
  BSTR *v74; // [rsp+C0h] [rbp-40h]
  BYTE Data[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v76; // [rsp+E0h] [rbp-20h]
  __int128 v77; // [rsp+F0h] [rbp-10h]
  __int128 v78; // [rsp+100h] [rbp+0h]
  __int128 v79; // [rsp+110h] [rbp+10h]

  v4 = a4;
  v68 = a4;
  v5 = a3;
  v70 = a3;
  v7 = this;
  v69 = this;
  Type = 0;
  cbData = 0;
  *(_DWORD *)v58 = 0;
  v8 = 0;
  v71 = 0;
  hKey = 0;
  v9 = (BSTR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
  v10 = v9;
  if ( !v9 )
  {
    v60 = 0;
    v61 = &qword_1800A8718;
    v62 = 0;
    v63 = 0;
    v64 = 14;
    v65 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  v72 = v9;
  v9[1] = 0;
  *((_DWORD *)v9 + 4) = 1;
  v11 = SysAllocString(L"TaskCache\\Tree");
  *v10 = v11;
  if ( !v11 )
    _com_raise_error(-2147024882, v12);
  v72 = v10;
  if ( a2 )
  {
    v13 = *a2;
    if ( *a2 == 92 )
    {
      v14 = a2 + 1;
      v13 = a2[1];
    }
    else
    {
      v14 = a2;
    }
    if ( v13 )
    {
      v21 = (BSTR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v22 = v21;
      if ( !v21 )
      {
        v60 = 0;
        v61 = &qword_1800A8718;
        v62 = 0;
        v63 = 0;
        v64 = 14;
        v65 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      *(_QWORD *)lpcbData = v21;
      v21[1] = 0;
      *((_DWORD *)v21 + 4) = 1;
      v23 = SysAllocString(L"\\");
      *v22 = v23;
      if ( !v23 )
        _com_raise_error(-2147024882, v24);
      v74 = v22;
      v25 = (BSTR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v26 = v25;
      if ( !v25 )
      {
        v60 = 0;
        v61 = &qword_1800A8718;
        v62 = 0;
        v63 = 0;
        v64 = 14;
        v65 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      v73 = v25;
      v25[1] = 0;
      *((_DWORD *)v25 + 4) = 1;
      if ( *v10 )
        v27 = SysStringLen(*v10);
      else
        v27 = 0;
      v54 = v27;
      if ( *v22 )
      {
        v28 = SysStringLen(*v22);
        v27 = v54;
      }
      else
      {
        v28 = 0;
      }
      lpcbData[0] = v28;
      v29 = v27 + v28;
      if ( v29 < (unsigned int)v27 || (v27 = 2LL * v29, v27 > 0xFFFFFFFF) )
        _com_raise_error(-2147024882, (struct IErrorInfo *)v27);
      v30 = SysAllocStringByteLen(0, v27);
      *v26 = v30;
      if ( v30 )
      {
        if ( *v10 )
          memcpy_0(v30, *v10, 2LL * (v54 + 1));
        if ( *v22 )
          memcpy_0(&(*v26)[v54], *v22, 2LL * (lpcbData[0] + 1));
      }
      else if ( v54 + lpcbData[0] )
      {
        _com_raise_error(-2147024882, v31);
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 4, 0xFFFFFFFF) == 1 )
      {
        if ( *v10 )
        {
          SysFreeString(*v10);
          *v10 = 0;
        }
        v45 = v10[1];
        if ( v45 )
        {
          operator delete(v45);
          v10[1] = 0;
        }
        HeapFree(g_PrivateHeap, 0, v10);
      }
      v72 = v26;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v22 + 4, 0xFFFFFFFF) == 1 )
      {
        if ( *v22 )
        {
          SysFreeString(*v22);
          *v22 = 0;
        }
        v46 = v22[1];
        if ( v46 )
        {
          operator delete(v46);
          v22[1] = 0;
        }
        HeapFree(g_PrivateHeap, 0, v22);
      }
      v32 = (BSTR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v33 = v32;
      if ( !v32 )
      {
        v60 = 0;
        v61 = &qword_1800A8718;
        v62 = 0;
        v63 = 0;
        v64 = 14;
        v65 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      v73 = v32;
      v32[1] = 0;
      *((_DWORD *)v32 + 4) = 1;
      v34 = SysAllocString(v14);
      *v33 = v34;
      if ( !v34 && v14 )
        _com_raise_error(-2147024882, v35);
      v73 = v33;
      v36 = (BSTR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v10 = v36;
      if ( !v36 )
      {
        v60 = 0;
        v61 = &qword_1800A8718;
        v62 = 0;
        v63 = 0;
        v64 = 14;
        v65 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      v74 = v36;
      v36[1] = 0;
      *((_DWORD *)v36 + 4) = 1;
      if ( *v26 )
        v38 = SysStringLen(*v26);
      else
        v38 = 0;
      if ( *v33 )
        v39 = SysStringLen(*v33);
      else
        v39 = 0;
      lpcbData[0] = v39;
      v40 = v38 + v39;
      v55 = v40;
      if ( v40 < v38 || (v37 = (struct IErrorInfo *)(2LL * v40), (unsigned __int64)v37 > 0xFFFFFFFF) )
        _com_raise_error(-2147024882, v37);
      v42 = SysAllocStringByteLen(0, (UINT)v37);
      *v10 = v42;
      if ( v42 )
      {
        if ( *v26 )
          memcpy_0(v42, *v26, 2LL * (v38 + 1));
        if ( *v33 )
          memcpy_0(&(*v10)[v38], *v33, 2LL * (lpcbData[0] + 1));
      }
      else if ( v55 )
      {
        _com_raise_error(-2147024882, v41);
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v26 + 4, 0xFFFFFFFF) == 1 )
      {
        if ( *v26 )
        {
          SysFreeString(*v26);
          *v26 = 0;
        }
        v47 = v26[1];
        if ( v47 )
        {
          operator delete(v47);
          v26[1] = 0;
        }
        HeapFree(g_PrivateHeap, 0, v26);
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v33 + 4, 0xFFFFFFFF) == 1 )
      {
        if ( *v33 )
        {
          SysFreeString(*v33);
          *v33 = 0;
        }
        v48 = v33[1];
        if ( v48 )
        {
          operator delete(v48);
          v33[1] = 0;
        }
        HeapFree(g_PrivateHeap, 0, v33);
        v5 = v70;
        v7 = v69;
      }
      else
      {
        v5 = v70;
        v7 = v69;
      }
    }
    v4 = v68;
  }
  if ( v10 )
    v15 = *v10;
  else
    v15 = 0;
  v16 = RegOpenKeyExW(*((HKEY *)v7 + 2), v15, 0, 0xF003Fu, &hKey);
  v17 = v16;
  if ( v16 )
  {
    if ( v16 > 0 )
      v17 = (unsigned __int16)v16 | 0x80070000;
    if ( v10 && _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 4, 0xFFFFFFFF) == 1 )
    {
      if ( *v10 )
      {
        SysFreeString(*v10);
        *v10 = 0;
      }
      v43 = v10[1];
      if ( v43 )
      {
        operator delete(v43);
        v10[1] = 0;
      }
      HeapFree(g_PrivateHeap, 0, v10);
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( v17 < 0 )
    {
      v51 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v52 = 82;
        LODWORD(v53) = (_DWORD)a2;
LABEL_135:
        WPP_SF_SSD(
          v51[2],
          v52,
          (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
          (_DWORD)v53,
          (__int64)a2,
          v17);
      }
LABEL_24:
      if ( v8 )
        RegCloseKey(v8);
      return (unsigned int)v17;
    }
  }
  else
  {
    v8 = hKey;
    v20 = 0;
    hKey = 0;
    v71 = v8;
    if ( v10 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 4, 0xFFFFFFFF) == 1 )
      {
        if ( *v10 )
        {
          SysFreeString(*v10);
          *v10 = 0;
        }
        v44 = v10[1];
        if ( v44 )
        {
          operator delete(v44);
          v10[1] = 0;
        }
        HeapFree(g_PrivateHeap, 0, v10);
      }
      v20 = hKey;
    }
    if ( v20 )
      RegCloseKey(v20);
  }
  *(_OWORD *)Data = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  cbData = 80;
  if ( v5 )
  {
    v18 = RegQueryValueExW(v8, L"Id", 0, &Type, Data, &cbData);
    v17 = v18;
    if ( v18 )
    {
      if ( v18 > 0 )
        v17 = (unsigned __int16)v18 | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          83,
          (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
          (_DWORD)a2,
          v17);
      }
      goto LABEL_24;
    }
    if ( Type != 1 )
    {
      v17 = -2147352571;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          84,
          (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
          (_DWORD)a2,
          5);
      }
      goto LABEL_24;
    }
    HIWORD(v79) = 0;
    v17 = IIDFromString((LPCOLESTR)Data, v5);
    if ( v17 < 0 )
    {
      v51 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v52 = 85;
        v53 = Data;
        goto LABEL_135;
      }
      goto LABEL_24;
    }
  }
  *(_DWORD *)v58 = 0;
  if ( !v4 )
  {
LABEL_46:
    v17 = 0;
    goto LABEL_24;
  }
  lpcbData[0] = 4;
  v49 = RegQueryValueExW(v8, L"Index", 0, &Type, v58, lpcbData);
  v50 = v49;
  if ( v49 )
  {
    if ( v49 > 0 )
      v50 = (unsigned __int16)v49 | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        86,
        (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
        (_DWORD)a2,
        v50);
    }
    if ( v8 )
      RegCloseKey(v8);
    return v50;
  }
  else
  {
    if ( Type == 4 )
    {
      *(_DWORD *)v4 = *(_DWORD *)v58;
      goto LABEL_46;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        87,
        (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
        (_DWORD)a2,
        5);
    }
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&v71);
    return 2147614725LL;
  }
}

```

## disassembly

```asm
0x18002b210  push    rbp
0x18002b212  push    rbx
0x18002b213  push    rsi
0x18002b214  push    rdi
0x18002b215  push    r12
0x18002b217  push    r13
0x18002b219  push    r14
0x18002b21b  push    r15
0x18002b21d  lea     rbp, [rsp-38h]
0x18002b222  sub     rsp, 138h
0x18002b229  mov     rax, cs:__security_cookie
0x18002b230  xor     rax, rsp
0x18002b233  mov     [rbp+70h+var_50], rax
0x18002b237  mov     r12, r9
0x18002b23a  mov     [rbp+70h+var_E0], r9
0x18002b23e  mov     r15, r8
0x18002b241  mov     [rbp+70h+var_D0], r8
0x18002b245  mov     r13, rdx
0x18002b248  mov     rsi, rcx
0x18002b24b  mov     [rbp+70h+var_D8], rcx
0x18002b24f  xor     r14d, r14d
0x18002b252  mov     [rsp+170h+Type], r14d
0x18002b257  mov     [rbp+70h+cbData], r14d
0x18002b25b  mov     dword ptr [rsp+170h+var_12C], r14d
0x18002b260  mov     edi, r14d
0x18002b263  mov     [rbp+70h+var_C8], r14
0x18002b267  mov     [rbp+70h+hKey], r14
0x18002b26b  xor     edx, edx; dwFlags
0x18002b26d  mov     r8d, 18h; dwBytes
0x18002b273  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18002b27a  call    cs:__imp_HeapAlloc
0x18002b281  nop     dword ptr [rax+rax+00h]
0x18002b286  mov     rbx, rax
0x18002b289  test    rax, rax
0x18002b28c  jz      loc_18002BA84
0x18002b292  mov     [rbp+70h+var_C0], rax
0x18002b296  mov     [rax+8], r14
0x18002b29a  mov     dword ptr [rax+10h], 1
0x18002b2a1  lea     rcx, psz; "TaskCache\\Tree"
0x18002b2a8  call    cs:__imp_SysAllocString
0x18002b2af  nop     dword ptr [rax+rax+00h]
0x18002b2b4  mov     [rbx], rax
0x18002b2b7  test    rax, rax
0x18002b2ba  jz      loc_18002B563
0x18002b2c0  mov     [rbp+70h+var_C0], rbx
0x18002b2c4  mov     r14d, 0FFFFFFFFh
0x18002b2ca  test    r13, r13
0x18002b2cd  jz      short loc_18002B2F4
0x18002b2cf  movzx   eax, word ptr [r13+0]
0x18002b2d4  cmp     ax, 5Ch ; '\'
0x18002b2d8  jnz     loc_18002B9FB
0x18002b2de  lea     r12, [r13+2]
0x18002b2e2  movzx   eax, word ptr [r12]
0x18002b2e7  test    ax, ax
0x18002b2ea  jnz     loc_18002B46D
0x18002b2f0  mov     r12, [rbp+70h+var_E0]
0x18002b2f4  test    rbx, rbx
0x18002b2f7  jz      loc_18002B7ED
0x18002b2fd  mov     rdx, [rbx]; lpSubKey
0x18002b300  lea     rax, [rbp+70h+hKey]
0x18002b304  mov     [rsp+170h+phkResult], rax; phkResult
0x18002b309  mov     r9d, 0F003Fh; samDesired
0x18002b30f  xor     r8d, r8d; ulOptions
0x18002b312  mov     rcx, [rsi+10h]; hKey
0x18002b316  call    cs:__imp_RegOpenKeyExW
0x18002b31d  nop     dword ptr [rax+rax+00h]
0x18002b322  mov     esi, eax
0x18002b324  test    eax, eax
0x18002b326  jz      loc_18002B42C
0x18002b32c  jle     short loc_18002B337
0x18002b32e  movzx   esi, ax
0x18002b331  or      esi, 80070000h
0x18002b337  test    rbx, rbx
0x18002b33a  jz      short loc_18002B34C
0x18002b33c  lock xadd [rbx+10h], r14d
0x18002b342  cmp     r14d, 1
0x18002b346  jz      loc_18002B7A8
0x18002b34c  mov     rcx, [rbp+70h+hKey]; hKey
0x18002b350  test    rcx, rcx
0x18002b353  jz      short loc_18002B361
0x18002b355  call    cs:__imp_RegCloseKey
0x18002b35c  nop     dword ptr [rax+rax+00h]
0x18002b361  test    esi, esi
0x18002b363  js      loc_18002BC75
0x18002b369  xorps   xmm0, xmm0
0x18002b36c  movups  xmmword ptr [rbp+70h+Data], xmm0
0x18002b370  movups  [rbp+70h+var_90], xmm0
0x18002b374  movups  [rbp+70h+var_80], xmm0
0x18002b378  movups  [rbp+70h+var_70], xmm0
0x18002b37c  movups  [rbp+70h+var_60], xmm0
0x18002b380  mov     [rbp+70h+cbData], 50h ; 'P'
0x18002b387  test    r15, r15
0x18002b38a  jz      loc_18002B59C
0x18002b390  lea     rax, [rbp+70h+cbData]
0x18002b394  mov     [rsp+170h+lpcbData], rax; lpcbData
0x18002b399  lea     rax, [rbp+70h+Data]
0x18002b39d  mov     [rsp+170h+phkResult], rax; lpData
0x18002b3a2  lea     r9, [rsp+170h+Type]; lpType
0x18002b3a7  xor     r8d, r8d; lpReserved
0x18002b3aa  lea     rdx, aId; "Id"
0x18002b3b1  mov     rcx, rdi; hKey
0x18002b3b4  call    cs:__imp_RegQueryValueExW
0x18002b3bb  nop     dword ptr [rax+rax+00h]
0x18002b3c0  mov     esi, eax
0x18002b3c2  test    eax, eax
0x18002b3c4  jz      loc_18002B56E
0x18002b3ca  jle     short loc_18002B3D5
0x18002b3cc  movzx   esi, ax
0x18002b3cf  or      esi, 80070000h
0x18002b3d5  lea     rax, WPP_GLOBAL_Control
0x18002b3dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b3e3  cmp     rcx, rax
0x18002b3e6  jz      short loc_18002B3F5
0x18002b3e8  test    dword ptr [rcx+1Ch], 40000h
0x18002b3ef  jnz     loc_18002BCE6
0x18002b3f5  test    rdi, rdi
0x18002b3f8  jz      short loc_18002B409
0x18002b3fa  mov     rcx, rdi; hKey
0x18002b3fd  call    cs:__imp_RegCloseKey
0x18002b404  nop     dword ptr [rax+rax+00h]
0x18002b409  mov     eax, esi
0x18002b40b  mov     rcx, [rbp+70h+var_50]
0x18002b40f  xor     rcx, rsp; StackCookie
0x18002b412  call    __security_check_cookie
0x18002b417  add     rsp, 138h
0x18002b41e  pop     r15
0x18002b420  pop     r14
0x18002b422  pop     r13
0x18002b424  pop     r12
0x18002b426  pop     rdi
0x18002b427  pop     rsi
0x18002b428  pop     rbx
0x18002b429  pop     rbp
0x18002b42a  retn
0x18002b42c  mov     rdi, [rbp+70h+hKey]
0x18002b430  xor     ecx, ecx
0x18002b432  mov     [rbp+70h+hKey], rcx
0x18002b436  mov     [rbp+70h+var_C8], rdi
0x18002b43a  test    rbx, rbx
0x18002b43d  jz      short loc_18002B453
0x18002b43f  lock xadd [rbx+10h], r14d
0x18002b445  cmp     r14d, 1
0x18002b449  jz      loc_18002B86B
0x18002b44f  mov     rcx, [rbp+70h+hKey]; hKey
0x18002b453  test    rcx, rcx
0x18002b456  jz      loc_18002B369
0x18002b45c  call    cs:__imp_RegCloseKey
0x18002b463  nop     dword ptr [rax+rax+00h]
0x18002b468  jmp     loc_18002B369
0x18002b46d  xor     edx, edx; dwFlags
0x18002b46f  mov     r8d, 18h; dwBytes
0x18002b475  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18002b47c  call    cs:__imp_HeapAlloc
0x18002b483  nop     dword ptr [rax+rax+00h]
0x18002b488  mov     rsi, rax
0x18002b48b  test    rax, rax
0x18002b48e  jz      loc_18002BACE
0x18002b494  mov     qword ptr [rsp+170h+var_138], rax
0x18002b499  mov     qword ptr [rax+8], 0
0x18002b4a1  mov     dword ptr [rax+10h], 1
0x18002b4a8  lea     rcx, asc_1800A7EC0; "\\"
0x18002b4af  call    cs:__imp_SysAllocString
0x18002b4b6  nop     dword ptr [rax+rax+00h]
0x18002b4bb  mov     [rsi], rax
0x18002b4be  test    rax, rax
0x18002b4c1  jz      loc_18002B84C
0x18002b4c7  mov     [rbp+70h+var_B0], rsi
0x18002b4cb  xor     edx, edx; dwFlags
0x18002b4cd  mov     r8d, 18h; dwBytes
0x18002b4d3  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18002b4da  call    cs:__imp_HeapAlloc
0x18002b4e1  nop     dword ptr [rax+rax+00h]
0x18002b4e6  mov     r15, rax
0x18002b4e9  test    rax, rax
0x18002b4ec  jz      loc_18002BB1A
0x18002b4f2  mov     [rbp+70h+var_B8], rax
0x18002b4f6  mov     qword ptr [rax+8], 0
0x18002b4fe  mov     dword ptr [rax+10h], 1
0x18002b505  mov     rcx, [rbx]; pbstr
0x18002b508  test    rcx, rcx
0x18002b50b  jz      loc_18002BB66
0x18002b511  call    cs:__imp_SysStringLen
0x18002b518  nop     dword ptr [rax+rax+00h]
0x18002b51d  mov     edx, eax
0x18002b51f  mov     [rsp+170h+var_140], edx
0x18002b523  mov     rcx, [rsi]; pbstr
0x18002b526  test    rcx, rcx
0x18002b529  jz      loc_18002BB6D
0x18002b52f  call    cs:__imp_SysStringLen
0x18002b536  nop     dword ptr [rax+rax+00h]
0x18002b53b  mov     edx, [rsp+170h+var_140]
0x18002b53f  mov     [rsp+170h+var_138], eax
0x18002b543  add     eax, edx
0x18002b545  cmp     eax, edx
0x18002b547  jb      short loc_18002B558
0x18002b549  mov     edx, eax
0x18002b54b  add     rdx, rdx; struct IErrorInfo *
0x18002b54e  mov     eax, 0FFFFFFFFh
0x18002b553  cmp     rdx, rax
0x18002b556  jbe     short loc_18002B5B4
0x18002b558  mov     ecx, 8007000Eh; int
0x18002b55d  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18002b563  mov     ecx, 8007000Eh; int
0x18002b568  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18002b56e  cmp     [rsp+170h+Type], 1
0x18002b573  jnz     loc_18002B7F4
0x18002b579  xor     eax, eax
0x18002b57b  mov     word ptr [rbp+70h+var_60+0Eh], ax
0x18002b57f  mov     rdx, r15; lpiid
0x18002b582  lea     rcx, [rbp+70h+Data]; lpsz
0x18002b586  call    cs:__imp_IIDFromString
0x18002b58d  nop     dword ptr [rax+rax+00h]
0x18002b592  mov     esi, eax
0x18002b594  test    eax, eax
0x18002b596  js      loc_18002BCFE
0x18002b59c  mov     dword ptr [rsp+170h+var_12C], 0
0x18002b5a4  test    r12, r12
0x18002b5a7  jnz     loc_18002BA03
0x18002b5ad  xor     esi, esi
0x18002b5af  jmp     loc_18002B3F5
0x18002b5b4  xor     ecx, ecx; psz
0x18002b5b6  call    cs:__imp_SysAllocStringByteLen
0x18002b5bd  nop     dword ptr [rax+rax+00h]
0x18002b5c2  mov     [r15], rax
0x18002b5c5  test    rax, rax
0x18002b5c8  jz      loc_18002B8B0
0x18002b5ce  mov     rdx, [rbx]; Src
0x18002b5d1  test    rdx, rdx
0x18002b5d4  jz      short loc_18002B5E9
0x18002b5d6  mov     r8d, [rsp+170h+var_140]
0x18002b5db  inc     r8d
0x18002b5de  add     r8, r8; Size
0x18002b5e1  mov     rcx, rax; void *
0x18002b5e4  call    memcpy_0
0x18002b5e9  mov     rdx, [rsi]; Src
0x18002b5ec  test    rdx, rdx
0x18002b5ef  jz      short loc_18002B60D
0x18002b5f1  mov     r8d, [rsp+170h+var_138]
0x18002b5f6  inc     r8d
0x18002b5f9  add     r8, r8; Size
0x18002b5fc  mov     ecx, [rsp+170h+var_140]
0x18002b600  mov     rax, [r15]
0x18002b603  lea     rcx, [rax+rcx*2]; void *
0x18002b607  call    memcpy_0
0x18002b60c  nop
0x18002b60d  mov     eax, r14d
0x18002b610  lock xadd [rbx+10h], eax
0x18002b615  cmp     eax, 1
0x18002b618  jz      loc_18002B8DF
0x18002b61e  mov     [rbp+70h+var_C0], r15
0x18002b622  mov     eax, r14d
0x18002b625  lock xadd [rsi+10h], eax
0x18002b62a  cmp     eax, 1
0x18002b62d  jz      loc_18002B924
0x18002b633  xor     edx, edx; dwFlags
0x18002b635  mov     r8d, 18h; dwBytes
0x18002b63b  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18002b642  call    cs:__imp_HeapAlloc
0x18002b649  nop     dword ptr [rax+rax+00h]
0x18002b64e  mov     rsi, rax
0x18002b651  test    rax, rax
0x18002b654  jz      loc_18002BB98
0x18002b65a  mov     [rbp+70h+var_B8], rax
0x18002b65e  mov     qword ptr [rax+8], 0
0x18002b666  mov     dword ptr [rax+10h], 1
0x18002b66d  mov     rcx, r12; psz
0x18002b670  call    cs:__imp_SysAllocString
0x18002b677  nop     dword ptr [rax+rax+00h]
0x18002b67c  mov     [rsi], rax
0x18002b67f  test    rax, rax
0x18002b682  jz      loc_18002B857
0x18002b688  mov     [rbp+70h+var_B8], rsi
0x18002b68c  xor     edx, edx; dwFlags
0x18002b68e  mov     r8d, 18h; dwBytes
0x18002b694  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18002b69b  call    cs:__imp_HeapAlloc
0x18002b6a2  nop     dword ptr [rax+rax+00h]
0x18002b6a7  mov     rbx, rax
0x18002b6aa  test    rax, rax
0x18002b6ad  jz      loc_18002BBE4
0x18002b6b3  mov     [rbp+70h+var_B0], rax
0x18002b6b7  mov     qword ptr [rax+8], 0
0x18002b6bf  mov     dword ptr [rax+10h], 1
0x18002b6c6  mov     rcx, [r15]; pbstr
0x18002b6c9  test    rcx, rcx
0x18002b6cc  jz      loc_18002BC30
0x18002b6d2  call    cs:__imp_SysStringLen
0x18002b6d9  nop     dword ptr [rax+rax+00h]
0x18002b6de  mov     r12d, eax
0x18002b6e1  mov     rcx, [rsi]; pbstr
0x18002b6e4  test    rcx, rcx
0x18002b6e7  jz      loc_18002BC38
0x18002b6ed  call    cs:__imp_SysStringLen
0x18002b6f4  nop     dword ptr [rax+rax+00h]
0x18002b6f9  mov     [rsp+170h+var_138], eax
0x18002b6fd  add     eax, r12d
0x18002b700  mov     [rsp+170h+var_140], eax
0x18002b704  cmp     eax, r12d
0x18002b707  jb      short loc_18002B718
0x18002b709  mov     edx, eax
  ... truncated ...
```
