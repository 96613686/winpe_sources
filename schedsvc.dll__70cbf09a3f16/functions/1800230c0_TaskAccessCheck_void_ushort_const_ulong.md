# TaskAccessCheck(void *,ushort const *,ulong)

- ea: `0x1800230c0`
- end: `0x180023a0a`
- name: `?TaskAccessCheck@@YAJPEAXPEBGK@Z`
- size: `2378`
- prototype: `__int64 __fastcall(HANDLE ClientToken, OLECHAR *psz, DWORD DesiredAccess)`
- caller_count: `14`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000b5a0`
- `0x18001b0d0`
- `0x180021ca0`
- `0x180022b80`
- `0x18004c6d0`
- `0x18004d620`
- `0x18005105c`
- `0x1800755e8`
- `0x1800758a0`
- `0x1800758e4`
- `0x180075f84`
- `0x1800763cc`
- `0x1800769dc`
- `0x180076dcc`

## callees

- `0x18001b070`
- `0x1800230c0`
- `0x180025040`
- `0x180052118`
- `0x18005790c`
- `0x180057926`
- `0x18007e6d0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180023152`
- `OLEAUT32!__imp_SysAllocString` at `0x180023328`
- `OLEAUT32!__imp_SysAllocString` at `0x180023623`
- `OLEAUT32!__imp_SysAllocString` at `0x180023152`
- `OLEAUT32!__imp_SysAllocString` at `0x180023328`
- `OLEAUT32!__imp_SysAllocString` at `0x180023623`
- `OLEAUT32!__imp_SysStringLen` at `0x180023382`
- `OLEAUT32!__imp_SysStringLen` at `0x18002339b`
- `OLEAUT32!__imp_SysStringLen` at `0x18002367f`
- `OLEAUT32!__imp_SysStringLen` at `0x180023692`
- `OLEAUT32!__imp_SysStringLen` at `0x180023382`
- `OLEAUT32!__imp_SysStringLen` at `0x18002339b`
- `OLEAUT32!__imp_SysStringLen` at `0x18002367f`
- `OLEAUT32!__imp_SysStringLen` at `0x180023692`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18002355e`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800236c8`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18002355e`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800236c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800231b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800231b2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002325d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800232b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002325d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800232b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800231e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023221`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800233e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800231e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023221`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800233e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002312a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800232fb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002334f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800235fb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023649`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002312a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800232fb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002334f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800235fb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023649`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800233d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800233f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800234a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800239ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800233d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800233f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800234a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800239ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002327e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002327e`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180023479`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x1800239e4`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180023479`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x1800239e4`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180023528`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180023528`

## string_xrefs

- `0x18002314b`: `TaskCache\Tree`

## pseudocode

```c
__int64 __fastcall TaskAccessCheck(HANDLE ClientToken, OLECHAR *psz, DWORD DesiredAccess)
{
  HANDLE v5; // r13
  struct IErrorInfo *v6; // r12
  HKEY v7; // rdi
  struct IErrorInfo *v8; // rax
  struct IErrorInfo *v9; // rbx
  BSTR v10; // rax
  struct IErrorInfo *v11; // rdx
  OLECHAR v12; // ax
  const WCHAR *lpVtbl; // rdx
  LSTATUS v14; // eax
  unsigned int v15; // edx
  signed int v16; // esi
  HKEY v17; // rcx
  LSTATUS v18; // eax
  struct IErrorInfo *v19; // rbx
  LSTATUS v20; // eax
  struct IErrorInfo *v21; // rax
  struct IErrorInfo *v22; // r13
  BSTR v23; // rax
  struct IErrorInfo *v24; // rdx
  struct IErrorInfo *v25; // rax
  unsigned __int64 v26; // rdx
  UINT v27; // eax
  unsigned int v28; // eax
  struct IErrorInfoVtbl *v30; // rax
  struct IErrorInfo *v31; // rdx
  volatile signed __int32 *v32; // rax
  volatile signed __int32 *v33; // r13
  BSTR v34; // rax
  struct IErrorInfo *v35; // rdx
  struct IErrorInfo *v36; // rax
  struct IErrorInfo *v37; // rdx
  struct IErrorInfo *v38; // rsi
  UINT v39; // eax
  OLECHAR *v40; // rcx
  DWORD v41; // ecx
  struct IErrorInfo *v42; // rdx
  BSTR v43; // rcx
  DWORD Type; // [rsp+40h] [rbp-99h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-95h] BYREF
  DWORD PrivilegeSetLength[2]; // [rsp+48h] [rbp-91h] BYREF
  struct IErrorInfo *v47; // [rsp+50h] [rbp-89h] BYREF
  void **pExceptionObject; // [rsp+58h] [rbp-81h] BYREF
  char v49; // [rsp+60h] [rbp-79h]
  const unsigned __int16 *v50; // [rsp+68h] [rbp-71h]
  __int64 v51; // [rsp+70h] [rbp-69h]
  __int64 v52; // [rsp+78h] [rbp-61h]
  int v53; // [rsp+80h] [rbp-59h]
  __int64 v54; // [rsp+84h] [rbp-55h]
  HKEY hKey; // [rsp+90h] [rbp-49h] BYREF
  HANDLE v56; // [rsp+98h] [rbp-41h]
  struct IErrorInfo *v57; // [rsp+A0h] [rbp-39h]
  volatile signed __int32 *v58; // [rsp+A8h] [rbp-31h]
  struct IErrorInfo *v59; // [rsp+B0h] [rbp-29h] BYREF
  DWORD v60; // [rsp+B8h] [rbp-21h]
  JobStore *v61; // [rsp+C0h] [rbp-19h]
  __int64 v62; // [rsp+C8h] [rbp-11h]
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+D0h] [rbp-9h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+E8h] [rbp+Fh] BYREF

  v5 = ClientToken;
  v56 = ClientToken;
  v61 = JobStore::m_pCommonStore;
  v6 = 0;
  v59 = 0;
  v60 = 0;
  v7 = 0;
  v62 = 0;
  hKey = 0;
  v8 = (struct IErrorInfo *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
  v9 = v8;
  if ( !v8 )
  {
    v49 = 0;
    v50 = &qword_1800A4718;
    v51 = 0;
    v52 = 0;
    v53 = 14;
    v54 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  v57 = v8;
  v8[1].lpVtbl = 0;
  LODWORD(v8[2].lpVtbl) = 1;
  v10 = SysAllocString(L"TaskCache\\Tree");
  v9->lpVtbl = (struct IErrorInfoVtbl *)v10;
  if ( !v10 )
    _com_raise_error(-2147024882, v11);
  v57 = v9;
  if ( psz )
  {
    v12 = *psz;
    if ( *psz == 92 )
      v12 = *++psz;
    if ( v12 )
    {
      v21 = (struct IErrorInfo *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v22 = v21;
      if ( !v21 )
      {
        v49 = 0;
        v50 = &qword_1800A4718;
        v51 = 0;
        v52 = 0;
        v53 = 14;
        v54 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      v47 = v21;
      v21[1].lpVtbl = 0;
      LODWORD(v21[2].lpVtbl) = 1;
      v23 = SysAllocString(L"\\");
      v22->lpVtbl = (struct IErrorInfoVtbl *)v23;
      if ( !v23 )
        _com_raise_error(-2147024882, v24);
      *(_QWORD *)PrivilegeSetLength = v22;
      v25 = (struct IErrorInfo *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v47 = v25;
      if ( !v25 )
      {
        v49 = 0;
        v50 = &qword_1800A4718;
        v51 = 0;
        v52 = 0;
        v53 = 14;
        v54 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      v58 = (volatile signed __int32 *)v25;
      v25[1].lpVtbl = 0;
      LODWORD(v25[2].lpVtbl) = 1;
      if ( v9->lpVtbl )
        v26 = SysStringLen((BSTR)v9->lpVtbl);
      else
        v26 = 0;
      Type = v26;
      if ( v22->lpVtbl )
      {
        v27 = SysStringLen((BSTR)v22->lpVtbl);
        v26 = Type;
      }
      else
      {
        v27 = 0;
      }
      cbData = v27;
      v28 = v26 + v27;
      if ( v28 < (unsigned int)v26 || (v26 = 2LL * v28, v26 > 0xFFFFFFFF) )
        _com_raise_error(-2147024882, (struct IErrorInfo *)v26);
      v30 = (struct IErrorInfoVtbl *)SysAllocStringByteLen(0, v26);
      v31 = v47;
      v47->lpVtbl = v30;
      if ( v30 )
      {
        if ( v9->lpVtbl )
        {
          memcpy_0(v30, v9->lpVtbl, 2LL * (Type + 1));
          v31 = v47;
        }
        if ( v22->lpVtbl )
          memcpy_0((char *)v31->lpVtbl + 2 * Type, v22->lpVtbl, 2LL * (cbData + 1));
      }
      else if ( Type + cbData )
      {
        _com_raise_error(-2147024882, v31);
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v9[2], 0xFFFFFFFF) == 1 )
        _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v9, (unsigned int)v31);
      v57 = v47;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v22[2], 0xFFFFFFFF) == 1 )
        _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v22, (unsigned int)v31);
      v32 = (volatile signed __int32 *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v33 = v32;
      if ( !v32 )
      {
        v49 = 0;
        v50 = &qword_1800A4718;
        v51 = 0;
        v52 = 0;
        v53 = 14;
        v54 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      v58 = v32;
      *((_QWORD *)v32 + 1) = 0;
      *((_DWORD *)v32 + 4) = 1;
      v34 = SysAllocString(psz);
      *(_QWORD *)v33 = v34;
      if ( !v34 && psz )
        _com_raise_error(-2147024882, v35);
      v58 = v33;
      v36 = (struct IErrorInfo *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v9 = v36;
      if ( !v36 )
      {
        v49 = 0;
        v50 = &qword_1800A4718;
        v51 = 0;
        v52 = 0;
        v53 = 14;
        v54 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      *(_QWORD *)&GenericMapping.GenericRead = v36;
      v36[1].lpVtbl = 0;
      LODWORD(v36[2].lpVtbl) = 1;
      v38 = v47;
      if ( v47->lpVtbl )
        v39 = SysStringLen((BSTR)v47->lpVtbl);
      else
        v39 = 0;
      Type = v39;
      v40 = *(OLECHAR **)v33;
      if ( *(_QWORD *)v33 )
      {
        LODWORD(v40) = SysStringLen(v40);
        v39 = Type;
      }
      cbData = (unsigned int)v40;
      v41 = v39 + (_DWORD)v40;
      PrivilegeSetLength[0] = v41;
      if ( v41 < v39 || (v37 = (struct IErrorInfo *)(2LL * v41), (unsigned __int64)v37 > 0xFFFFFFFF) )
        _com_raise_error(-2147024882, v37);
      v43 = SysAllocStringByteLen(0, (UINT)v37);
      v9->lpVtbl = (struct IErrorInfoVtbl *)v43;
      if ( v43 )
      {
        if ( v38->lpVtbl )
          memcpy_0(v43, v38->lpVtbl, 2LL * (Type + 1));
        v42 = *(struct IErrorInfo **)v33;
        if ( *(_QWORD *)v33 )
          memcpy_0((char *)v9->lpVtbl + 2 * Type, v42, 2LL * (cbData + 1));
      }
      else if ( PrivilegeSetLength[0] )
      {
        _com_raise_error(-2147024882, v42);
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v38[2], 0xFFFFFFFF) == 1 )
        _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v38, (unsigned int)v42);
      if ( _InterlockedExchangeAdd(v33 + 4, 0xFFFFFFFF) == 1 )
        _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v33, (unsigned int)v42);
      v5 = v56;
    }
  }
  if ( v9 )
    lpVtbl = (const WCHAR *)v9->lpVtbl;
  else
    lpVtbl = 0;
  v14 = RegOpenKeyExW(*((HKEY *)v61 + 2), lpVtbl, 0, 0xF003Fu, &hKey);
  v16 = v14;
  if ( !v14 )
  {
    v7 = hKey;
    v17 = 0;
    hKey = 0;
    if ( v9 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v9[2], 0xFFFFFFFF) == 1 )
        _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v9, v15);
      v17 = hKey;
    }
    if ( v17 )
      RegCloseKey(v17);
LABEL_25:
    Type = 3;
    cbData = 0;
    v47 = 0;
    v18 = RegQueryValueExW(v7, L"SD", 0, &Type, 0, &cbData);
    v16 = v18;
    if ( v18 )
    {
      if ( v18 > 0 )
        v16 = (unsigned __int16)v18 | 0x80070000;
    }
    else
    {
      if ( Type != 3 )
        goto LABEL_115;
      v19 = (struct IErrorInfo *)LocalAlloc(0, cbData);
      v47 = v19;
      if ( !v19 )
      {
        tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v47);
        goto LABEL_44;
      }
      v20 = RegQueryValueExW(v7, L"SD", 0, &Type, (LPBYTE)v19, &cbData);
      v16 = v20;
      if ( !v20 )
      {
        if ( Type != 3 )
        {
          LocalFree(v19);
          v16 = -2147023537;
          goto LABEL_45;
        }
        if ( cbData )
        {
          v6 = v19;
          v59 = v19;
          v60 = cbData;
LABEL_44:
          v16 = 0;
          goto LABEL_45;
        }
LABEL_115:
        tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v47);
        v16 = -2147023537;
        goto LABEL_45;
      }
      if ( v20 > 0 )
        v16 = (unsigned __int16)v20 | 0x80070000;
      LocalFree(v19);
    }
    if ( v16 < 0 )
      goto LABEL_45;
    goto LABEL_44;
  }
  if ( v14 > 0 )
    v16 = (unsigned __int16)v14 | 0x80070000;
  if ( v9 && _InterlockedExchangeAdd((volatile signed __int32 *)&v9[2], 0xFFFFFFFF) == 1 )
    _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v9, v15);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v16 >= 0 )
    goto LABEL_25;
LABEL_45:
  if ( v7 )
    RegCloseKey(v7);
  if ( v16 >= 0 )
  {
    Type = 0;
    RequiredPrivileges.Privilege[0].Luid = 0;
    if ( !v5 || !v6 || !DesiredAccess )
      goto LABEL_65;
    RequiredPrivileges.Control = 1;
    RequiredPrivileges.PrivilegeCount = 1;
    RequiredPrivileges.Privilege[0].Attributes = 2;
    if ( (DesiredAccess & 1) != 0 )
    {
      RequiredPrivileges.Privilege[0].Luid = (LUID)17LL;
      if ( !PrivilegeCheck(v5, &RequiredPrivileges, (LPBOOL)&Type) )
        goto LABEL_65;
      if ( Type )
        DesiredAccess &= ~1u;
    }
    if ( (DesiredAccess & 0xD0006) == 0 )
      goto LABEL_59;
    RequiredPrivileges.Privilege[0].Luid = (LUID)18LL;
    if ( PrivilegeCheck(v5, &RequiredPrivileges, (LPBOOL)&Type) )
    {
      if ( Type )
        DesiredAccess &= 0xFFF2FFF9;
LABEL_59:
      if ( !DesiredAccess
        || (GenericMapping.GenericRead = 1179785,
            GenericMapping.GenericWrite = 1179926,
            GenericMapping.GenericExecute = 1179808,
            GenericMapping.GenericAll = 2032127,
            PrivilegeSetLength[0] = 20,
            memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges)),
            cbData = 0,
            AccessCheck(
              v6,
              v5,
              DesiredAccess,
              &GenericMapping,
              &RequiredPrivileges,
              PrivilegeSetLength,
              &cbData,
              (LPBOOL)&Type))
        && Type
        && (DesiredAccess & cbData) == DesiredAccess )
      {
        LocalFree(v6);
        return 0;
      }
    }
LABEL_65:
    tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v59);
    return 2147942405LL;
  }
  if ( v6 )
    LocalFree(v6);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800230c0  mov     [rsp-8+arg_18], rbx
0x1800230c5  push    rbp
0x1800230c6  push    rsi
0x1800230c7  push    rdi
0x1800230c8  push    r12
0x1800230ca  push    r13
0x1800230cc  push    r14
0x1800230ce  push    r15
0x1800230d0  lea     rbp, [rsp-27h]
0x1800230d5  sub     rsp, 100h
0x1800230dc  mov     rax, cs:__security_cookie
0x1800230e3  xor     rax, rsp
0x1800230e6  mov     [rbp+57h+var_38], rax
0x1800230ea  mov     r15d, r8d
0x1800230ed  mov     rsi, rdx
0x1800230f0  mov     r13, rcx
0x1800230f3  mov     [rbp+57h+var_98], rcx
0x1800230f7  mov     rax, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; JobStore * JobStore::m_pCommonStore
0x1800230fe  mov     [rbp+57h+var_70], rax
0x180023102  xor     r14d, r14d
0x180023105  mov     r12d, r14d
0x180023108  mov     [rbp+57h+var_80], r14
0x18002310c  mov     [rbp+57h+var_78], r14d
0x180023110  mov     edi, r14d
0x180023113  mov     [rbp+57h+var_68], r14
0x180023117  mov     [rbp+57h+hKey], r14
0x18002311b  xor     edx, edx; dwFlags
0x18002311d  mov     r8d, 18h; dwBytes
0x180023123  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18002312a  call    cs:__imp_HeapAlloc
0x180023130  mov     rbx, rax
0x180023133  test    rax, rax
0x180023136  jz      loc_180023815
0x18002313c  mov     [rbp+57h+var_90], rax
0x180023140  mov     [rax+8], r14
0x180023144  mov     dword ptr [rax+10h], 1
0x18002314b  lea     rcx, aTaskcacheTree; "TaskCache\\Tree"
0x180023152  call    cs:__imp_SysAllocString
0x180023158  mov     [rbx], rax
0x18002315b  test    rax, rax
0x18002315e  jz      loc_1800234B4
0x180023164  mov     [rbp+57h+var_90], rbx
0x180023168  mov     r14d, 0FFFFFFFFh
0x18002316e  test    rsi, rsi
0x180023171  jz      short loc_18002318C
0x180023173  movzx   eax, word ptr [rsi]
0x180023176  cmp     ax, 5Ch ; '\'
0x18002317a  jnz     short loc_180023183
0x18002317c  add     rsi, 2
0x180023180  movzx   eax, word ptr [rsi]
0x180023183  test    ax, ax
0x180023186  jnz     loc_1800232EC
0x18002318c  test    rbx, rbx
0x18002318f  jz      loc_180023753
0x180023195  mov     rdx, [rbx]; lpSubKey
0x180023198  lea     rax, [rbp+57h+hKey]
0x18002319c  mov     [rsp+130h+phkResult], rax; phkResult
0x1800231a1  mov     r9d, 0F003Fh; samDesired
0x1800231a7  xor     r8d, r8d; ulOptions
0x1800231aa  mov     rcx, [rbp+57h+var_70]
0x1800231ae  mov     rcx, [rcx+10h]; hKey
0x1800231b2  call    cs:__imp_RegOpenKeyExW
0x1800231b8  mov     esi, eax
0x1800231ba  test    eax, eax
0x1800231bc  jz      short loc_1800231F9
0x1800231be  jle     short loc_1800231C9
0x1800231c0  movzx   esi, ax
0x1800231c3  or      esi, 80070000h
0x1800231c9  test    rbx, rbx
0x1800231cc  jz      short loc_1800231DE
0x1800231ce  lock xadd [rbx+10h], r14d
0x1800231d4  cmp     r14d, 1
0x1800231d8  jz      loc_180023746
0x1800231de  mov     rcx, [rbp+57h+hKey]; hKey
0x1800231e2  test    rcx, rcx
0x1800231e5  jz      short loc_1800231ED
0x1800231e7  call    cs:__imp_RegCloseKey
0x1800231ed  test    esi, esi
0x1800231ef  jns     short loc_180023227
0x1800231f1  xor     r14d, r14d
0x1800231f4  jmp     loc_1800233DD
0x1800231f9  mov     rdi, [rbp+57h+hKey]
0x1800231fd  xor     ecx, ecx
0x1800231ff  mov     [rbp+57h+hKey], rcx
0x180023203  test    rbx, rbx
0x180023206  jz      short loc_18002321C
0x180023208  lock xadd [rbx+10h], r14d
0x18002320e  cmp     r14d, 1
0x180023212  jz      loc_18002378D
0x180023218  mov     rcx, [rbp+57h+hKey]; hKey
0x18002321c  test    rcx, rcx
0x18002321f  jz      short loc_180023227
0x180023221  call    cs:__imp_RegCloseKey
0x180023227  mov     [rsp+130h+Type], 3
0x18002322f  xor     r14d, r14d
0x180023232  mov     [rsp+130h+cbData], r14d
0x180023237  mov     [rsp+130h+var_E0], r14
0x18002323c  lea     rax, [rsp+130h+cbData]
0x180023241  mov     [rsp+130h+lpcbData], rax; lpcbData
0x180023246  mov     [rsp+130h+phkResult], r14; lpData
0x18002324b  lea     r9, [rsp+130h+Type]; lpType
0x180023250  xor     r8d, r8d; lpReserved
0x180023253  lea     rdx, ValueName; "SD"
0x18002325a  mov     rcx, rdi; hKey
0x18002325d  call    cs:__imp_RegQueryValueExW
0x180023263  mov     esi, eax
0x180023265  test    eax, eax
0x180023267  jnz     loc_180023801
0x18002326d  cmp     [rsp+130h+Type], 3
0x180023272  jnz     loc_180023986
0x180023278  mov     edx, [rsp+130h+cbData]; uBytes
0x18002327c  xor     ecx, ecx; uFlags
0x18002327e  call    cs:__imp_LocalAlloc
0x180023284  mov     rbx, rax
0x180023287  mov     [rsp+130h+var_E0], rax
0x18002328c  test    rax, rax
0x18002328f  jz      loc_18002399A
0x180023295  lea     rax, [rsp+130h+cbData]
0x18002329a  mov     [rsp+130h+lpcbData], rax; lpcbData
0x18002329f  mov     [rsp+130h+phkResult], rbx; lpData
0x1800232a4  lea     r9, [rsp+130h+Type]; lpType
0x1800232a9  xor     r8d, r8d; lpReserved
0x1800232ac  lea     rdx, ValueName; "SD"
0x1800232b3  mov     rcx, rdi; hKey
0x1800232b6  call    cs:__imp_RegQueryValueExW
0x1800232bc  mov     esi, eax
0x1800232be  test    eax, eax
0x1800232c0  jnz     loc_180023779
0x1800232c6  cmp     [rsp+130h+Type], 3
0x1800232cb  jnz     loc_1800239A9
0x1800232d1  mov     eax, [rsp+130h+cbData]
0x1800232d5  test    eax, eax
0x1800232d7  jz      loc_1800239BC
0x1800232dd  mov     r12, rbx
0x1800232e0  mov     [rbp+57h+var_80], rbx
0x1800232e4  mov     [rbp+57h+var_78], eax
0x1800232e7  jmp     loc_1800233DA
0x1800232ec  xor     edx, edx; dwFlags
0x1800232ee  mov     r8d, 18h; dwBytes
0x1800232f4  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x1800232fb  call    cs:__imp_HeapAlloc
0x180023301  mov     r13, rax
0x180023304  test    rax, rax
0x180023307  jz      loc_180023859
0x18002330d  mov     [rsp+130h+var_E0], rax
0x180023312  mov     qword ptr [rax+8], 0
0x18002331a  mov     dword ptr [rax+10h], 1
0x180023321  lea     rcx, asc_1800A3DA8; "\\"
0x180023328  call    cs:__imp_SysAllocString
0x18002332e  mov     [r13+0], rax
0x180023332  test    rax, rax
0x180023335  jz      loc_18002375A
0x18002333b  mov     qword ptr [rsp+130h+PrivilegeSetLength], r13
0x180023340  xor     edx, edx; dwFlags
0x180023342  mov     r8d, 18h; dwBytes
0x180023348  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18002334f  call    cs:__imp_HeapAlloc
0x180023355  mov     [rsp+130h+var_E0], rax
0x18002335a  test    rax, rax
0x18002335d  jz      loc_18002389F
0x180023363  mov     [rbp+57h+var_88], rax
0x180023367  mov     qword ptr [rax+8], 0
0x18002336f  mov     dword ptr [rax+10h], 1
0x180023376  mov     rcx, [rbx]; pbstr
0x180023379  test    rcx, rcx
0x18002337c  jz      loc_1800238E5
0x180023382  call    cs:__imp_SysStringLen
0x180023388  mov     edx, eax
0x18002338a  mov     [rsp+130h+Type], edx
0x18002338e  mov     rcx, [r13+0]; pbstr
0x180023392  test    rcx, rcx
0x180023395  jz      loc_1800238EC
0x18002339b  call    cs:__imp_SysStringLen
0x1800233a1  mov     edx, [rsp+130h+Type]
0x1800233a5  mov     [rsp+130h+cbData], eax
0x1800233a9  add     eax, edx
0x1800233ab  cmp     eax, edx
0x1800233ad  jb      short loc_1800233C2
0x1800233af  mov     edx, eax
0x1800233b1  add     rdx, rdx; struct IErrorInfo *
0x1800233b4  mov     eax, 0FFFFFFFFh
0x1800233b9  cmp     rdx, rax
0x1800233bc  jbe     loc_18002355C
0x1800233c2  mov     ecx, 8007000Eh; int
0x1800233c7  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x1800233cd  mov     rcx, rbx; hMem
0x1800233d0  call    cs:__imp_LocalFree
0x1800233d6  test    esi, esi
0x1800233d8  js      short loc_1800233DD
0x1800233da  mov     esi, r14d
0x1800233dd  test    rdi, rdi
0x1800233e0  jz      short loc_1800233EB
0x1800233e2  mov     rcx, rdi; hKey
0x1800233e5  call    cs:__imp_RegCloseKey
0x1800233eb  test    esi, esi
0x1800233ed  jns     short loc_180023426
0x1800233ef  test    r12, r12
0x1800233f2  jz      short loc_1800233FD
0x1800233f4  mov     rcx, r12; hMem
0x1800233f7  call    cs:__imp_LocalFree
0x1800233fd  mov     eax, esi
0x1800233ff  mov     rcx, [rbp+57h+var_38]
0x180023403  xor     rcx, rsp; StackCookie
0x180023406  call    __security_check_cookie
0x18002340b  mov     rbx, [rsp+130h+arg_18]
0x180023413  add     rsp, 100h
0x18002341a  pop     r15
0x18002341c  pop     r14
0x18002341e  pop     r13
0x180023420  pop     r12
0x180023422  pop     rdi
0x180023423  pop     rsi
0x180023424  pop     rbp
0x180023425  retn
0x180023426  mov     [rsp+130h+Type], r14d
0x18002342b  mov     qword ptr [rbp+57h+RequiredPrivileges.Privilege.Luid.LowPart], r14
0x18002342f  test    r13, r13
0x180023432  jz      loc_180023549
0x180023438  test    r12, r12
0x18002343b  jz      loc_180023549
0x180023441  test    r15d, r15d
0x180023444  jz      loc_180023549
0x18002344a  mov     [rbp+57h+RequiredPrivileges.Control], 1
0x180023451  mov     [rbp+57h+RequiredPrivileges.PrivilegeCount], 1
0x180023458  mov     [rbp+57h+RequiredPrivileges.Privilege.Attributes], 2
0x18002345f  test    r15b, 1
0x180023463  jz      short loc_180023492
0x180023465  mov     qword ptr [rbp+57h+RequiredPrivileges.Privilege.Luid.LowPart], 11h
0x18002346d  lea     r8, [rsp+130h+Type]; pfResult
0x180023472  lea     rdx, [rbp+57h+RequiredPrivileges]; RequiredPrivileges
0x180023476  mov     rcx, r13; ClientToken
0x180023479  call    cs:__imp_PrivilegeCheck
0x18002347f  test    eax, eax
0x180023481  jz      loc_180023549
0x180023487  cmp     [rsp+130h+Type], 0
0x18002348c  jz      short loc_180023492
0x18002348e  and     r15d, 0FFFFFFFEh
0x180023492  test    r15d, 0D0006h
0x180023499  jnz     loc_1800239D0
0x18002349f  test    r15d, r15d
0x1800234a2  jnz     short loc_1800234BF
0x1800234a4  mov     rcx, r12; hMem
0x1800234a7  call    cs:__imp_LocalFree
0x1800234ad  xor     eax, eax
0x1800234af  jmp     loc_1800233FF
0x1800234b4  mov     ecx, 8007000Eh; int
0x1800234b9  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x1800234bf  mov     [rbp+57h+GenericMapping.GenericRead], 120089h
0x1800234c6  mov     [rbp+57h+GenericMapping.GenericWrite], 120116h
0x1800234cd  mov     [rbp+57h+GenericMapping.GenericExecute], 1200A0h
0x1800234d4  mov     [rbp+57h+GenericMapping.GenericAll], 1F01FFh
0x1800234db  mov     [rsp+130h+PrivilegeSetLength], 14h
0x1800234e3  xorps   xmm0, xmm0
0x1800234e6  xor     eax, eax
0x1800234e8  movups  xmmword ptr [rbp+57h+RequiredPrivileges.PrivilegeCount], xmm0
0x1800234ec  mov     [rbp+57h+RequiredPrivileges.Privilege.Attributes], eax
0x1800234ef  mov     [rsp+130h+cbData], r14d
0x1800234f4  lea     rax, [rsp+130h+Type]
0x1800234f9  mov     [rsp+130h+AccessStatus], rax; AccessStatus
0x1800234fe  lea     rax, [rsp+130h+cbData]
0x180023503  mov     [rsp+130h+GrantedAccess], rax; GrantedAccess
0x180023508  lea     rax, [rsp+130h+PrivilegeSetLength]
0x18002350d  mov     [rsp+130h+lpcbData], rax; PrivilegeSetLength
0x180023512  lea     rax, [rbp+57h+RequiredPrivileges]
0x180023516  mov     [rsp+130h+phkResult], rax; PrivilegeSet
0x18002351b  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x18002351f  mov     r8d, r15d; DesiredAccess
0x180023522  mov     rdx, r13; ClientToken
0x180023525  mov     rcx, r12; pSecurityDescriptor
0x180023528  call    cs:__imp_AccessCheck
0x18002352e  test    eax, eax
0x180023530  jz      short loc_180023549
0x180023532  cmp     [rsp+130h+Type], 0
0x180023537  jz      short loc_180023549
0x180023539  mov     eax, [rsp+130h+cbData]
0x18002353d  and     eax, r15d
0x180023540  cmp     eax, r15d
0x180023543  jz      loc_1800234A4
0x180023549  lea     rcx, [rbp+57h+var_80]
0x18002354d  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180023552  mov     eax, 80070005h
0x180023557  jmp     loc_1800233FF
0x18002355c  xor     ecx, ecx; psz
0x18002355e  call    cs:__imp_SysAllocStringByteLen
0x180023564  mov     rdx, [rsp+130h+var_E0]; struct IErrorInfo *
0x180023569  mov     [rdx], rax
0x18002356c  test    rax, rax
0x18002356f  jz      loc_18002379A
0x180023575  mov     r9, [rbx]
0x180023578  test    r9, r9
0x18002357b  jz      short loc_180023598
0x18002357d  mov     r8d, [rsp+130h+Type]
0x180023582  inc     r8d
0x180023585  add     r8, r8; Size
0x180023588  mov     rdx, r9; Src
0x18002358b  mov     rcx, rax; void *
0x18002358e  call    memcpy_0
0x180023593  mov     rdx, [rsp+130h+var_E0]
0x180023598  mov     r9, [r13+0]
0x18002359c  test    r9, r9
  ... truncated ...
```
