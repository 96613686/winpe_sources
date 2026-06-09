# TaskAccessCheck(void *,ushort const *,ulong)

- ea: `0x18001f060`
- end: `0x18001fa53`
- name: `?TaskAccessCheck@@YAJPEAXPEBGK@Z`
- size: `2547`
- prototype: `__int64 __fastcall(HANDLE ClientToken, OLECHAR *psz, DWORD DesiredAccess)`
- caller_count: `14`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180011ed0`
- `0x18001e06c`
- `0x18001eae0`
- `0x180027990`
- `0x18004e9d0`
- `0x18004f9b8`
- `0x1800535dc`
- `0x180079560`
- `0x180079830`
- `0x180079874`
- `0x180079f48`
- `0x18007a3b8`
- `0x18007a9dc`
- `0x18007ae0c`

## callees

- `0x18000d830`
- `0x18001f060`
- `0x18001fe10`
- `0x180054824`
- `0x18005a2bc`
- `0x18005a2d6`
- `0x180082a40`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001f0f8`
- `OLEAUT32!__imp_SysAllocString` at `0x18001f2fe`
- `OLEAUT32!__imp_SysAllocString` at `0x18001f642`
- `OLEAUT32!__imp_SysAllocString` at `0x18001f0f8`
- `OLEAUT32!__imp_SysAllocString` at `0x18001f2fe`
- `OLEAUT32!__imp_SysAllocString` at `0x18001f642`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f364`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f383`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f6aa`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f6c3`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f364`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f383`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f6aa`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f6c3`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001f571`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001f6ff`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001f571`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001f6ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f15e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f15e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f21b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f280`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f21b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f280`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f199`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f1d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f3d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f199`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f1d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f3d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f0ca`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f2cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f32b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f614`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f66e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f0ca`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f2cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f32b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f614`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f66e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f3be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f3f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f4ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f9e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f3be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f3f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f4ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f9e9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f242`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f242`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x18001f47a`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x18001fa27`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x18001f47a`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x18001fa27`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18001f535`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18001f535`

## string_xrefs

- `0x18001f0f1`: `TaskCache\Tree`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
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
    v50 = &qword_1800A8718;
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
        v50 = &qword_1800A8718;
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
        v50 = &qword_1800A8718;
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
        v50 = &qword_1800A8718;
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
        v50 = &qword_1800A8718;
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
0x18001f060  mov     [rsp-8+arg_18], rbx
0x18001f065  push    rbp
0x18001f066  push    rsi
0x18001f067  push    rdi
0x18001f068  push    r12
0x18001f06a  push    r13
0x18001f06c  push    r14
0x18001f06e  push    r15
0x18001f070  lea     rbp, [rsp-27h]
0x18001f075  sub     rsp, 100h
0x18001f07c  mov     rax, cs:__security_cookie
0x18001f083  xor     rax, rsp
0x18001f086  mov     [rbp+57h+var_38], rax
0x18001f08a  mov     r15d, r8d
0x18001f08d  mov     rsi, rdx
0x18001f090  mov     r13, rcx
0x18001f093  mov     [rbp+57h+var_98], rcx
0x18001f097  mov     rax, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; JobStore * JobStore::m_pCommonStore
0x18001f09e  mov     [rbp+57h+var_70], rax
0x18001f0a2  xor     r14d, r14d
0x18001f0a5  mov     r12d, r14d
0x18001f0a8  mov     [rbp+57h+var_80], r14
0x18001f0ac  mov     [rbp+57h+var_78], r14d
0x18001f0b0  mov     edi, r14d
0x18001f0b3  mov     [rbp+57h+var_68], r14
0x18001f0b7  mov     [rbp+57h+hKey], r14
0x18001f0bb  xor     edx, edx; dwFlags
0x18001f0bd  mov     r8d, 18h; dwBytes
0x18001f0c3  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18001f0ca  call    cs:__imp_HeapAlloc
0x18001f0d1  nop     dword ptr [rax+rax+00h]
0x18001f0d6  mov     rbx, rax
0x18001f0d9  test    rax, rax
0x18001f0dc  jz      loc_18001F852
0x18001f0e2  mov     [rbp+57h+var_90], rax
0x18001f0e6  mov     [rax+8], r14
0x18001f0ea  mov     dword ptr [rax+10h], 1
0x18001f0f1  lea     rcx, psz; "TaskCache\\Tree"
0x18001f0f8  call    cs:__imp_SysAllocString
0x18001f0ff  nop     dword ptr [rax+rax+00h]
0x18001f104  mov     [rbx], rax
0x18001f107  test    rax, rax
0x18001f10a  jz      loc_18001F4C1
0x18001f110  mov     [rbp+57h+var_90], rbx
0x18001f114  mov     r14d, 0FFFFFFFFh
0x18001f11a  test    rsi, rsi
0x18001f11d  jz      short loc_18001F138
0x18001f11f  movzx   eax, word ptr [rsi]
0x18001f122  cmp     ax, 5Ch ; '\'
0x18001f126  jnz     short loc_18001F12F
0x18001f128  add     rsi, 2
0x18001f12c  movzx   eax, word ptr [rsi]
0x18001f12f  test    ax, ax
0x18001f132  jnz     loc_18001F2BC
0x18001f138  test    rbx, rbx
0x18001f13b  jz      loc_18001F790
0x18001f141  mov     rdx, [rbx]; lpSubKey
0x18001f144  lea     rax, [rbp+57h+hKey]
0x18001f148  mov     [rsp+130h+phkResult], rax; phkResult
0x18001f14d  mov     r9d, 0F003Fh; samDesired
0x18001f153  xor     r8d, r8d; ulOptions
0x18001f156  mov     rcx, [rbp+57h+var_70]
0x18001f15a  mov     rcx, [rcx+10h]; hKey
0x18001f15e  call    cs:__imp_RegOpenKeyExW
0x18001f165  nop     dword ptr [rax+rax+00h]
0x18001f16a  mov     esi, eax
0x18001f16c  test    eax, eax
0x18001f16e  jz      short loc_18001F1B1
0x18001f170  jle     short loc_18001F17B
0x18001f172  movzx   esi, ax
0x18001f175  or      esi, 80070000h
0x18001f17b  test    rbx, rbx
0x18001f17e  jz      short loc_18001F190
0x18001f180  lock xadd [rbx+10h], r14d
0x18001f186  cmp     r14d, 1
0x18001f18a  jz      loc_18001F783
0x18001f190  mov     rcx, [rbp+57h+hKey]; hKey
0x18001f194  test    rcx, rcx
0x18001f197  jz      short loc_18001F1A5
0x18001f199  call    cs:__imp_RegCloseKey
0x18001f1a0  nop     dword ptr [rax+rax+00h]
0x18001f1a5  test    esi, esi
0x18001f1a7  jns     short loc_18001F1E5
0x18001f1a9  xor     r14d, r14d
0x18001f1ac  jmp     loc_18001F3D1
0x18001f1b1  mov     rdi, [rbp+57h+hKey]
0x18001f1b5  xor     ecx, ecx
0x18001f1b7  mov     [rbp+57h+hKey], rcx
0x18001f1bb  test    rbx, rbx
0x18001f1be  jz      short loc_18001F1D4
0x18001f1c0  lock xadd [rbx+10h], r14d
0x18001f1c6  cmp     r14d, 1
0x18001f1ca  jz      loc_18001F7CA
0x18001f1d0  mov     rcx, [rbp+57h+hKey]; hKey
0x18001f1d4  test    rcx, rcx
0x18001f1d7  jz      short loc_18001F1E5
0x18001f1d9  call    cs:__imp_RegCloseKey
0x18001f1e0  nop     dword ptr [rax+rax+00h]
0x18001f1e5  mov     [rsp+130h+Type], 3
0x18001f1ed  xor     r14d, r14d
0x18001f1f0  mov     [rsp+130h+cbData], r14d
0x18001f1f5  mov     [rsp+130h+var_E0], r14
0x18001f1fa  lea     rax, [rsp+130h+cbData]
0x18001f1ff  mov     [rsp+130h+lpcbData], rax; lpcbData
0x18001f204  mov     [rsp+130h+phkResult], r14; lpData
0x18001f209  lea     r9, [rsp+130h+Type]; lpType
0x18001f20e  xor     r8d, r8d; lpReserved
0x18001f211  lea     rdx, aSd; "SD"
0x18001f218  mov     rcx, rdi; hKey
0x18001f21b  call    cs:__imp_RegQueryValueExW
0x18001f222  nop     dword ptr [rax+rax+00h]
0x18001f227  mov     esi, eax
0x18001f229  test    eax, eax
0x18001f22b  jnz     loc_18001F83E
0x18001f231  cmp     [rsp+130h+Type], 3
0x18001f236  jnz     loc_18001F9C3
0x18001f23c  mov     edx, [rsp+130h+cbData]; uBytes
0x18001f240  xor     ecx, ecx; uFlags
0x18001f242  call    cs:__imp_LocalAlloc
0x18001f249  nop     dword ptr [rax+rax+00h]
0x18001f24e  mov     rbx, rax
0x18001f251  mov     [rsp+130h+var_E0], rax
0x18001f256  test    rax, rax
0x18001f259  jz      loc_18001F9D7
0x18001f25f  lea     rax, [rsp+130h+cbData]
0x18001f264  mov     [rsp+130h+lpcbData], rax; lpcbData
0x18001f269  mov     [rsp+130h+phkResult], rbx; lpData
0x18001f26e  lea     r9, [rsp+130h+Type]; lpType
0x18001f273  xor     r8d, r8d; lpReserved
0x18001f276  lea     rdx, aSd; "SD"
0x18001f27d  mov     rcx, rdi; hKey
0x18001f280  call    cs:__imp_RegQueryValueExW
0x18001f287  nop     dword ptr [rax+rax+00h]
0x18001f28c  mov     esi, eax
0x18001f28e  test    eax, eax
0x18001f290  jnz     loc_18001F7B6
0x18001f296  cmp     [rsp+130h+Type], 3
0x18001f29b  jnz     loc_18001F9E6
0x18001f2a1  mov     eax, [rsp+130h+cbData]
0x18001f2a5  test    eax, eax
0x18001f2a7  jz      loc_18001F9FF
0x18001f2ad  mov     r12, rbx
0x18001f2b0  mov     [rbp+57h+var_80], rbx
0x18001f2b4  mov     [rbp+57h+var_78], eax
0x18001f2b7  jmp     loc_18001F3CE
0x18001f2bc  xor     edx, edx; dwFlags
0x18001f2be  mov     r8d, 18h; dwBytes
0x18001f2c4  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18001f2cb  call    cs:__imp_HeapAlloc
0x18001f2d2  nop     dword ptr [rax+rax+00h]
0x18001f2d7  mov     r13, rax
0x18001f2da  test    rax, rax
0x18001f2dd  jz      loc_18001F896
0x18001f2e3  mov     [rsp+130h+var_E0], rax
0x18001f2e8  mov     qword ptr [rax+8], 0
0x18001f2f0  mov     dword ptr [rax+10h], 1
0x18001f2f7  lea     rcx, asc_1800A7EC0; "\\"
0x18001f2fe  call    cs:__imp_SysAllocString
0x18001f305  nop     dword ptr [rax+rax+00h]
0x18001f30a  mov     [r13+0], rax
0x18001f30e  test    rax, rax
0x18001f311  jz      loc_18001F797
0x18001f317  mov     qword ptr [rsp+130h+PrivilegeSetLength], r13
0x18001f31c  xor     edx, edx; dwFlags
0x18001f31e  mov     r8d, 18h; dwBytes
0x18001f324  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18001f32b  call    cs:__imp_HeapAlloc
0x18001f332  nop     dword ptr [rax+rax+00h]
0x18001f337  mov     [rsp+130h+var_E0], rax
0x18001f33c  test    rax, rax
0x18001f33f  jz      loc_18001F8DC
0x18001f345  mov     [rbp+57h+var_88], rax
0x18001f349  mov     qword ptr [rax+8], 0
0x18001f351  mov     dword ptr [rax+10h], 1
0x18001f358  mov     rcx, [rbx]; pbstr
0x18001f35b  test    rcx, rcx
0x18001f35e  jz      loc_18001F922
0x18001f364  call    cs:__imp_SysStringLen
0x18001f36b  nop     dword ptr [rax+rax+00h]
0x18001f370  mov     edx, eax
0x18001f372  mov     [rsp+130h+Type], edx
0x18001f376  mov     rcx, [r13+0]; pbstr
0x18001f37a  test    rcx, rcx
0x18001f37d  jz      loc_18001F929
0x18001f383  call    cs:__imp_SysStringLen
0x18001f38a  nop     dword ptr [rax+rax+00h]
0x18001f38f  mov     edx, [rsp+130h+Type]
0x18001f393  mov     [rsp+130h+cbData], eax
0x18001f397  add     eax, edx
0x18001f399  cmp     eax, edx
0x18001f39b  jb      short loc_18001F3B0
0x18001f39d  mov     edx, eax
0x18001f39f  add     rdx, rdx; struct IErrorInfo *
0x18001f3a2  mov     eax, 0FFFFFFFFh
0x18001f3a7  cmp     rdx, rax
0x18001f3aa  jbe     loc_18001F56F
0x18001f3b0  mov     ecx, 8007000Eh; int
0x18001f3b5  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18001f3bb  mov     rcx, rbx; hMem
0x18001f3be  call    cs:__imp_LocalFree
0x18001f3c5  nop     dword ptr [rax+rax+00h]
0x18001f3ca  test    esi, esi
0x18001f3cc  js      short loc_18001F3D1
0x18001f3ce  mov     esi, r14d
0x18001f3d1  test    rdi, rdi
0x18001f3d4  jz      short loc_18001F3E5
0x18001f3d6  mov     rcx, rdi; hKey
0x18001f3d9  call    cs:__imp_RegCloseKey
0x18001f3e0  nop     dword ptr [rax+rax+00h]
0x18001f3e5  test    esi, esi
0x18001f3e7  jns     short loc_18001F427
0x18001f3e9  test    r12, r12
0x18001f3ec  jz      short loc_18001F3FD
0x18001f3ee  mov     rcx, r12; hMem
0x18001f3f1  call    cs:__imp_LocalFree
0x18001f3f8  nop     dword ptr [rax+rax+00h]
0x18001f3fd  mov     eax, esi
0x18001f3ff  mov     rcx, [rbp+57h+var_38]
0x18001f403  xor     rcx, rsp; StackCookie
0x18001f406  call    __security_check_cookie
0x18001f40b  mov     rbx, [rsp+130h+arg_18]
0x18001f413  add     rsp, 100h
0x18001f41a  pop     r15
0x18001f41c  pop     r14
0x18001f41e  pop     r13
0x18001f420  pop     r12
0x18001f422  pop     rdi
0x18001f423  pop     rsi
0x18001f424  pop     rbp
0x18001f425  retn
0x18001f427  mov     [rsp+130h+Type], r14d
0x18001f42c  mov     qword ptr [rbp+57h+RequiredPrivileges.Privilege.Luid.LowPart], r14
0x18001f430  test    r13, r13
0x18001f433  jz      loc_18001F55C
0x18001f439  test    r12, r12
0x18001f43c  jz      loc_18001F55C
0x18001f442  test    r15d, r15d
0x18001f445  jz      loc_18001F55C
0x18001f44b  mov     [rbp+57h+RequiredPrivileges.Control], 1
0x18001f452  mov     [rbp+57h+RequiredPrivileges.PrivilegeCount], 1
0x18001f459  mov     [rbp+57h+RequiredPrivileges.Privilege.Attributes], 2
0x18001f460  test    r15b, 1
0x18001f464  jz      short loc_18001F499
0x18001f466  mov     qword ptr [rbp+57h+RequiredPrivileges.Privilege.Luid.LowPart], 11h
0x18001f46e  lea     r8, [rsp+130h+Type]; pfResult
0x18001f473  lea     rdx, [rbp+57h+RequiredPrivileges]; RequiredPrivileges
0x18001f477  mov     rcx, r13; ClientToken
0x18001f47a  call    cs:__imp_PrivilegeCheck
0x18001f481  nop     dword ptr [rax+rax+00h]
0x18001f486  test    eax, eax
0x18001f488  jz      loc_18001F55C
0x18001f48e  cmp     [rsp+130h+Type], 0
0x18001f493  jz      short loc_18001F499
0x18001f495  and     r15d, 0FFFFFFFEh
0x18001f499  test    r15d, 0D0006h
0x18001f4a0  jnz     loc_18001FA13
0x18001f4a6  test    r15d, r15d
0x18001f4a9  jnz     short loc_18001F4CC
0x18001f4ab  mov     rcx, r12; hMem
0x18001f4ae  call    cs:__imp_LocalFree
0x18001f4b5  nop     dword ptr [rax+rax+00h]
0x18001f4ba  xor     eax, eax
0x18001f4bc  jmp     loc_18001F3FF
0x18001f4c1  mov     ecx, 8007000Eh; int
0x18001f4c6  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18001f4cc  mov     [rbp+57h+GenericMapping.GenericRead], 120089h
0x18001f4d3  mov     [rbp+57h+GenericMapping.GenericWrite], 120116h
0x18001f4da  mov     [rbp+57h+GenericMapping.GenericExecute], 1200A0h
0x18001f4e1  mov     [rbp+57h+GenericMapping.GenericAll], 1F01FFh
0x18001f4e8  mov     [rsp+130h+PrivilegeSetLength], 14h
0x18001f4f0  xorps   xmm0, xmm0
0x18001f4f3  xor     eax, eax
0x18001f4f5  movups  xmmword ptr [rbp+57h+RequiredPrivileges.PrivilegeCount], xmm0
0x18001f4f9  mov     [rbp+57h+RequiredPrivileges.Privilege.Attributes], eax
0x18001f4fc  mov     [rsp+130h+cbData], r14d
0x18001f501  lea     rax, [rsp+130h+Type]
0x18001f506  mov     [rsp+130h+AccessStatus], rax; AccessStatus
0x18001f50b  lea     rax, [rsp+130h+cbData]
0x18001f510  mov     [rsp+130h+GrantedAccess], rax; GrantedAccess
0x18001f515  lea     rax, [rsp+130h+PrivilegeSetLength]
0x18001f51a  mov     [rsp+130h+lpcbData], rax; PrivilegeSetLength
0x18001f51f  lea     rax, [rbp+57h+RequiredPrivileges]
0x18001f523  mov     [rsp+130h+phkResult], rax; PrivilegeSet
0x18001f528  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x18001f52c  mov     r8d, r15d; DesiredAccess
0x18001f52f  mov     rdx, r13; ClientToken
0x18001f532  mov     rcx, r12; pSecurityDescriptor
0x18001f535  call    cs:__imp_AccessCheck
0x18001f53c  nop     dword ptr [rax+rax+00h]
0x18001f541  test    eax, eax
0x18001f543  jz      short loc_18001F55C
0x18001f545  cmp     [rsp+130h+Type], 0
0x18001f54a  jz      short loc_18001F55C
0x18001f54c  mov     eax, [rsp+130h+cbData]
0x18001f550  and     eax, r15d
0x18001f553  cmp     eax, r15d
0x18001f556  jz      loc_18001F4AB
0x18001f55c  lea     rcx, [rbp+57h+var_80]
0x18001f560  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18001f565  mov     eax, 80070005h
  ... truncated ...
```
