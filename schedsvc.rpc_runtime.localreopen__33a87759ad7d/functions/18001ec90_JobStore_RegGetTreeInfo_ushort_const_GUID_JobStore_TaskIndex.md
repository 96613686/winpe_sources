# JobStore::RegGetTreeInfo(ushort const *,_GUID *,JobStore::TaskIndex *)

- ea: `0x18001ec90`
- end: `0x18001f787`
- name: `?RegGetTreeInfo@JobStore@@QEBAJPEBGPEAU_GUID@@PEAW4TaskIndex@1@@Z`
- size: `2807`
- prototype: `int(JobStore *__hidden this, const unsigned __int16 *, struct _GUID *, enum JobStore::TaskIndex *)`
- caller_count: `12`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000b5a0`
- `0x18000e510`
- `0x180018110`
- `0x18001b0d0`
- `0x18001f790`
- `0x18001fdb0`
- `0x180020854`
- `0x1800213f8`
- `0x180023b60`
- `0x180029978`
- `0x180045df0`
- `0x18004c6d0`

## callees

- `0x18001a260`
- `0x18001ec90`
- `0x180021300`
- `0x180052118`
- `0x180053e54`
- `0x180056794`
- `0x18005790c`
- `0x180057926`
- `0x18007e6d0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001ed22`
- `OLEAUT32!__imp_SysAllocString` at `0x18001eefe`
- `OLEAUT32!__imp_SysAllocString` at `0x18001f095`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ed22`
- `OLEAUT32!__imp_SysAllocString` at `0x18001eefe`
- `OLEAUT32!__imp_SysAllocString` at `0x18001f095`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f1b7`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f26e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f2d6`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f30f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f348`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f381`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f1b7`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f26e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f2d6`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f30f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f348`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f381`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ef54`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ef6c`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f0eb`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f100`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ef54`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ef6c`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f0eb`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f100`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001efe7`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001f132`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001efe7`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001f132`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ed8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ed8a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ee1c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f3f0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ee1c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f3f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001edc3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ee5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001eeb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f42a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001edc3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ee5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001eeb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f42a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f1dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f294`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f2fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f335`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f36e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f3a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f1dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f294`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f2fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f335`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f36e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f3a7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ecfa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001eed1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ef23`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f06d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f0ba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ecfa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001eed1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ef23`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f06d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f0ba`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18001efbd`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18001efbd`

## string_xrefs

- `0x18001ed1b`: `TaskCache\Tree`

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
    v61 = &qword_1800A4718;
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
        v61 = &qword_1800A4718;
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
        v61 = &qword_1800A4718;
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
        v61 = &qword_1800A4718;
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
        v61 = &qword_1800A4718;
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
0x18001ec90  push    rbp
0x18001ec92  push    rbx
0x18001ec93  push    rsi
0x18001ec94  push    rdi
0x18001ec95  push    r12
0x18001ec97  push    r13
0x18001ec99  push    r14
0x18001ec9b  push    r15
0x18001ec9d  lea     rbp, [rsp-38h]
0x18001eca2  sub     rsp, 138h
0x18001eca9  mov     rax, cs:__security_cookie
0x18001ecb0  xor     rax, rsp
0x18001ecb3  mov     [rbp+70h+var_50], rax
0x18001ecb7  mov     r12, r9
0x18001ecba  mov     [rbp+70h+var_E0], r9
0x18001ecbe  mov     r15, r8
0x18001ecc1  mov     [rbp+70h+var_D0], r8
0x18001ecc5  mov     r13, rdx
0x18001ecc8  mov     rsi, rcx
0x18001eccb  mov     [rbp+70h+var_D8], rcx
0x18001eccf  xor     r14d, r14d
0x18001ecd2  mov     [rsp+170h+Type], r14d
0x18001ecd7  mov     [rbp+70h+cbData], r14d
0x18001ecdb  mov     dword ptr [rsp+170h+var_12C], r14d
0x18001ece0  mov     edi, r14d
0x18001ece3  mov     [rbp+70h+var_C8], r14
0x18001ece7  mov     [rbp+70h+hKey], r14
0x18001eceb  xor     edx, edx; dwFlags
0x18001eced  mov     r8d, 18h; dwBytes
0x18001ecf3  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18001ecfa  call    cs:__imp_HeapAlloc
0x18001ed00  mov     rbx, rax
0x18001ed03  test    rax, rax
0x18001ed06  jz      loc_18001F437
0x18001ed0c  mov     [rbp+70h+var_C0], rax
0x18001ed10  mov     [rax+8], r14
0x18001ed14  mov     dword ptr [rax+10h], 1
0x18001ed1b  lea     rcx, aTaskcacheTree; "TaskCache\\Tree"
0x18001ed22  call    cs:__imp_SysAllocString
0x18001ed28  mov     [rbx], rax
0x18001ed2b  test    rax, rax
0x18001ed2e  jz      loc_18001EF9A
0x18001ed34  mov     [rbp+70h+var_C0], rbx
0x18001ed38  mov     r14d, 0FFFFFFFFh
0x18001ed3e  test    r13, r13
0x18001ed41  jz      short loc_18001ED68
0x18001ed43  movzx   eax, word ptr [r13+0]
0x18001ed48  cmp     ax, 5Ch ; '\'
0x18001ed4c  jnz     loc_18001F3BA
0x18001ed52  lea     r12, [r13+2]
0x18001ed56  movzx   eax, word ptr [r12]
0x18001ed5b  test    ax, ax
0x18001ed5e  jnz     loc_18001EEC2
0x18001ed64  mov     r12, [rbp+70h+var_E0]
0x18001ed68  test    rbx, rbx
0x18001ed6b  jz      loc_18001F1E8
0x18001ed71  mov     rdx, [rbx]; lpSubKey
0x18001ed74  lea     rax, [rbp+70h+hKey]
0x18001ed78  mov     [rsp+170h+phkResult], rax; phkResult
0x18001ed7d  mov     r9d, 0F003Fh; samDesired
0x18001ed83  xor     r8d, r8d; ulOptions
0x18001ed86  mov     rcx, [rsi+10h]; hKey
0x18001ed8a  call    cs:__imp_RegOpenKeyExW
0x18001ed90  mov     esi, eax
0x18001ed92  test    eax, eax
0x18001ed94  jz      loc_18001EE87
0x18001ed9a  jle     short loc_18001EDA5
0x18001ed9c  movzx   esi, ax
0x18001ed9f  or      esi, 80070000h
0x18001eda5  test    rbx, rbx
0x18001eda8  jz      short loc_18001EDBA
0x18001edaa  lock xadd [rbx+10h], r14d
0x18001edb0  cmp     r14d, 1
0x18001edb4  jz      loc_18001F1AF
0x18001edba  mov     rcx, [rbp+70h+hKey]; hKey
0x18001edbe  test    rcx, rcx
0x18001edc1  jz      short loc_18001EDC9
0x18001edc3  call    cs:__imp_RegCloseKey
0x18001edc9  test    esi, esi
0x18001edcb  js      loc_18001F628
0x18001edd1  xorps   xmm0, xmm0
0x18001edd4  movups  xmmword ptr [rbp+70h+Data], xmm0
0x18001edd8  movups  [rbp+70h+var_90], xmm0
0x18001eddc  movups  [rbp+70h+var_80], xmm0
0x18001ede0  movups  [rbp+70h+var_70], xmm0
0x18001ede4  movups  [rbp+70h+var_60], xmm0
0x18001ede8  mov     [rbp+70h+cbData], 50h ; 'P'
0x18001edef  test    r15, r15
0x18001edf2  jz      loc_18001EFCD
0x18001edf8  lea     rax, [rbp+70h+cbData]
0x18001edfc  mov     [rsp+170h+lpcbData], rax; lpcbData
0x18001ee01  lea     rax, [rbp+70h+Data]
0x18001ee05  mov     [rsp+170h+phkResult], rax; lpData
0x18001ee0a  lea     r9, [rsp+170h+Type]; lpType
0x18001ee0f  xor     r8d, r8d; lpReserved
0x18001ee12  lea     rdx, aId; "Id"
0x18001ee19  mov     rcx, rdi; hKey
0x18001ee1c  call    cs:__imp_RegQueryValueExW
0x18001ee22  mov     esi, eax
0x18001ee24  test    eax, eax
0x18001ee26  jz      loc_18001EFA5
0x18001ee2c  jle     short loc_18001EE37
0x18001ee2e  movzx   esi, ax
0x18001ee31  or      esi, 80070000h
0x18001ee37  lea     rax, WPP_GLOBAL_Control
0x18001ee3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee45  cmp     rcx, rax
0x18001ee48  jz      short loc_18001EE57
0x18001ee4a  test    dword ptr [rcx+1Ch], 40000h
0x18001ee51  jnz     loc_18001F699
0x18001ee57  test    rdi, rdi
0x18001ee5a  jz      short loc_18001EE65
0x18001ee5c  mov     rcx, rdi; hKey
0x18001ee5f  call    cs:__imp_RegCloseKey
0x18001ee65  mov     eax, esi
0x18001ee67  mov     rcx, [rbp+70h+var_50]
0x18001ee6b  xor     rcx, rsp; StackCookie
0x18001ee6e  call    __security_check_cookie
0x18001ee73  add     rsp, 138h
0x18001ee7a  pop     r15
0x18001ee7c  pop     r14
0x18001ee7e  pop     r13
0x18001ee80  pop     r12
0x18001ee82  pop     rdi
0x18001ee83  pop     rsi
0x18001ee84  pop     rbx
0x18001ee85  pop     rbp
0x18001ee86  retn
0x18001ee87  mov     rdi, [rbp+70h+hKey]
0x18001ee8b  xor     ecx, ecx
0x18001ee8d  mov     [rbp+70h+hKey], rcx
0x18001ee91  mov     [rbp+70h+var_C8], rdi
0x18001ee95  test    rbx, rbx
0x18001ee98  jz      short loc_18001EEAE
0x18001ee9a  lock xadd [rbx+10h], r14d
0x18001eea0  cmp     r14d, 1
0x18001eea4  jz      loc_18001F266
0x18001eeaa  mov     rcx, [rbp+70h+hKey]; hKey
0x18001eeae  test    rcx, rcx
0x18001eeb1  jz      loc_18001EDD1
0x18001eeb7  call    cs:__imp_RegCloseKey
0x18001eebd  jmp     loc_18001EDD1
0x18001eec2  xor     edx, edx; dwFlags
0x18001eec4  mov     r8d, 18h; dwBytes
0x18001eeca  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18001eed1  call    cs:__imp_HeapAlloc
0x18001eed7  mov     rsi, rax
0x18001eeda  test    rax, rax
0x18001eedd  jz      loc_18001F481
0x18001eee3  mov     qword ptr [rsp+170h+var_138], rax
0x18001eee8  mov     qword ptr [rax+8], 0
0x18001eef0  mov     dword ptr [rax+10h], 1
0x18001eef7  lea     rcx, asc_1800A3DA8; "\\"
0x18001eefe  call    cs:__imp_SysAllocString
0x18001ef04  mov     [rsi], rax
0x18001ef07  test    rax, rax
0x18001ef0a  jz      loc_18001F247
0x18001ef10  mov     [rbp+70h+var_B0], rsi
0x18001ef14  xor     edx, edx; dwFlags
0x18001ef16  mov     r8d, 18h; dwBytes
0x18001ef1c  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18001ef23  call    cs:__imp_HeapAlloc
0x18001ef29  mov     r15, rax
0x18001ef2c  test    rax, rax
0x18001ef2f  jz      loc_18001F4CD
0x18001ef35  mov     [rbp+70h+var_B8], rax
0x18001ef39  mov     qword ptr [rax+8], 0
0x18001ef41  mov     dword ptr [rax+10h], 1
0x18001ef48  mov     rcx, [rbx]; pbstr
0x18001ef4b  test    rcx, rcx
0x18001ef4e  jz      loc_18001F519
0x18001ef54  call    cs:__imp_SysStringLen
0x18001ef5a  mov     edx, eax
0x18001ef5c  mov     [rsp+170h+var_140], edx
0x18001ef60  mov     rcx, [rsi]; pbstr
0x18001ef63  test    rcx, rcx
0x18001ef66  jz      loc_18001F520
0x18001ef6c  call    cs:__imp_SysStringLen
0x18001ef72  mov     edx, [rsp+170h+var_140]
0x18001ef76  mov     [rsp+170h+var_138], eax
0x18001ef7a  add     eax, edx
0x18001ef7c  cmp     eax, edx
0x18001ef7e  jb      short loc_18001EF8F
0x18001ef80  mov     edx, eax
0x18001ef82  add     rdx, rdx; struct IErrorInfo *
0x18001ef85  mov     eax, 0FFFFFFFFh
0x18001ef8a  cmp     rdx, rax
0x18001ef8d  jbe     short loc_18001EFE5
0x18001ef8f  mov     ecx, 8007000Eh; int
0x18001ef94  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18001ef9a  mov     ecx, 8007000Eh; int
0x18001ef9f  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18001efa5  cmp     [rsp+170h+Type], 1
0x18001efaa  jnz     loc_18001F1EF
0x18001efb0  xor     eax, eax
0x18001efb2  mov     word ptr [rbp+70h+var_60+0Eh], ax
0x18001efb6  mov     rdx, r15; lpiid
0x18001efb9  lea     rcx, [rbp+70h+Data]; lpsz
0x18001efbd  call    cs:__imp_IIDFromString
0x18001efc3  mov     esi, eax
0x18001efc5  test    eax, eax
0x18001efc7  js      loc_18001F6B1
0x18001efcd  mov     dword ptr [rsp+170h+var_12C], 0
0x18001efd5  test    r12, r12
0x18001efd8  jnz     loc_18001F3C2
0x18001efde  xor     esi, esi
0x18001efe0  jmp     loc_18001EE57
0x18001efe5  xor     ecx, ecx; psz
0x18001efe7  call    cs:__imp_SysAllocStringByteLen
0x18001efed  mov     [r15], rax
0x18001eff0  test    rax, rax
0x18001eff3  jz      loc_18001F29F
0x18001eff9  mov     rdx, [rbx]; Src
0x18001effc  test    rdx, rdx
0x18001efff  jz      short loc_18001F014
0x18001f001  mov     r8d, [rsp+170h+var_140]
0x18001f006  inc     r8d
0x18001f009  add     r8, r8; Size
0x18001f00c  mov     rcx, rax; void *
0x18001f00f  call    memcpy_0
0x18001f014  mov     rdx, [rsi]; Src
0x18001f017  test    rdx, rdx
0x18001f01a  jz      short loc_18001F038
0x18001f01c  mov     r8d, [rsp+170h+var_138]
0x18001f021  inc     r8d
0x18001f024  add     r8, r8; Size
0x18001f027  mov     ecx, [rsp+170h+var_140]
0x18001f02b  mov     rax, [r15]
0x18001f02e  lea     rcx, [rax+rcx*2]; void *
0x18001f032  call    memcpy_0
0x18001f037  nop
0x18001f038  mov     eax, r14d
0x18001f03b  lock xadd [rbx+10h], eax
0x18001f040  cmp     eax, 1
0x18001f043  jz      loc_18001F2CE
0x18001f049  mov     [rbp+70h+var_C0], r15
0x18001f04d  mov     eax, r14d
0x18001f050  lock xadd [rsi+10h], eax
0x18001f055  cmp     eax, 1
0x18001f058  jz      loc_18001F307
0x18001f05e  xor     edx, edx; dwFlags
0x18001f060  mov     r8d, 18h; dwBytes
0x18001f066  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18001f06d  call    cs:__imp_HeapAlloc
0x18001f073  mov     rsi, rax
0x18001f076  test    rax, rax
0x18001f079  jz      loc_18001F54B
0x18001f07f  mov     [rbp+70h+var_B8], rax
0x18001f083  mov     qword ptr [rax+8], 0
0x18001f08b  mov     dword ptr [rax+10h], 1
0x18001f092  mov     rcx, r12; psz
0x18001f095  call    cs:__imp_SysAllocString
0x18001f09b  mov     [rsi], rax
0x18001f09e  test    rax, rax
0x18001f0a1  jz      loc_18001F252
0x18001f0a7  mov     [rbp+70h+var_B8], rsi
0x18001f0ab  xor     edx, edx; dwFlags
0x18001f0ad  mov     r8d, 18h; dwBytes
0x18001f0b3  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18001f0ba  call    cs:__imp_HeapAlloc
0x18001f0c0  mov     rbx, rax
0x18001f0c3  test    rax, rax
0x18001f0c6  jz      loc_18001F597
0x18001f0cc  mov     [rbp+70h+var_B0], rax
0x18001f0d0  mov     qword ptr [rax+8], 0
0x18001f0d8  mov     dword ptr [rax+10h], 1
0x18001f0df  mov     rcx, [r15]; pbstr
0x18001f0e2  test    rcx, rcx
0x18001f0e5  jz      loc_18001F5E3
0x18001f0eb  call    cs:__imp_SysStringLen
0x18001f0f1  mov     r12d, eax
0x18001f0f4  mov     rcx, [rsi]; pbstr
0x18001f0f7  test    rcx, rcx
0x18001f0fa  jz      loc_18001F5EB
0x18001f100  call    cs:__imp_SysStringLen
0x18001f106  mov     [rsp+170h+var_138], eax
0x18001f10a  add     eax, r12d
0x18001f10d  mov     [rsp+170h+var_140], eax
0x18001f111  cmp     eax, r12d
0x18001f114  jb      short loc_18001F125
0x18001f116  mov     edx, eax
0x18001f118  add     rdx, rdx; struct IErrorInfo *
0x18001f11b  mov     eax, 0FFFFFFFFh
0x18001f120  cmp     rdx, rax
0x18001f123  jbe     short loc_18001F130
0x18001f125  mov     ecx, 8007000Eh; int
0x18001f12a  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18001f130  xor     ecx, ecx; psz
0x18001f132  call    cs:__imp_SysAllocStringByteLen
0x18001f138  mov     rcx, rax; void *
0x18001f13b  mov     [rbx], rax
0x18001f13e  test    rax, rax
0x18001f141  jz      loc_18001F2B8
0x18001f147  mov     rdx, [r15]; Src
0x18001f14a  test    rdx, rdx
0x18001f14d  jz      short loc_18001F15C
0x18001f14f  lea     r8d, [r12+1]
0x18001f154  add     r8, r8; Size
0x18001f157  call    memcpy_0
0x18001f15c  mov     rdx, [rsi]; Src
  ... truncated ...
```
