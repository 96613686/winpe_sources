# JobStore::RegJobSecurityQuery(ushort const *,JobSecurity &)

- ea: `0x180025870`
- end: `0x18002614c`
- name: `?RegJobSecurityQuery@JobStore@@QEBAJPEBGAEAVJobSecurity@@@Z`
- size: `2268`
- prototype: `int(JobStore *__hidden this, const unsigned __int16 *, struct JobSecurity *)`
- caller_count: `8`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800213f8`
- `0x18002506c`
- `0x1800256d0`
- `0x180029978`
- `0x180045df0`
- `0x18004d868`
- `0x18006c840`
- `0x1800762b8`

## callees

- `0x18001a260`
- `0x180025040`
- `0x180025870`
- `0x180052118`
- `0x18005790c`
- `0x180057926`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800258e0`
- `OLEAUT32!__imp_SysAllocString` at `0x180025ada`
- `OLEAUT32!__imp_SysAllocString` at `0x180025c2f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800258e0`
- `OLEAUT32!__imp_SysAllocString` at `0x180025ada`
- `OLEAUT32!__imp_SysAllocString` at `0x180025c2f`
- `OLEAUT32!__imp_SysFreeString` at `0x180025d51`
- `OLEAUT32!__imp_SysFreeString` at `0x180025dc1`
- `OLEAUT32!__imp_SysFreeString` at `0x180025e1e`
- `OLEAUT32!__imp_SysFreeString` at `0x180025e57`
- `OLEAUT32!__imp_SysFreeString` at `0x180025e91`
- `OLEAUT32!__imp_SysFreeString` at `0x180025ecc`
- `OLEAUT32!__imp_SysFreeString` at `0x180025d51`
- `OLEAUT32!__imp_SysFreeString` at `0x180025dc1`
- `OLEAUT32!__imp_SysFreeString` at `0x180025e1e`
- `OLEAUT32!__imp_SysFreeString` at `0x180025e57`
- `OLEAUT32!__imp_SysFreeString` at `0x180025e91`
- `OLEAUT32!__imp_SysFreeString` at `0x180025ecc`
- `OLEAUT32!__imp_SysStringLen` at `0x180025b2c`
- `OLEAUT32!__imp_SysStringLen` at `0x180025b41`
- `OLEAUT32!__imp_SysStringLen` at `0x180025c86`
- `OLEAUT32!__imp_SysStringLen` at `0x180025c9a`
- `OLEAUT32!__imp_SysStringLen` at `0x180025b2c`
- `OLEAUT32!__imp_SysStringLen` at `0x180025b41`
- `OLEAUT32!__imp_SysStringLen` at `0x180025c86`
- `OLEAUT32!__imp_SysStringLen` at `0x180025c9a`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180025b80`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180025cc9`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180025b80`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180025cc9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002593c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002593c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800259de`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025a32`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800259de`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025a32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025971`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800259aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025a87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025971`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800259aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025a87`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025d73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025de3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025e44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025e7d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025eb9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025ef1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025d73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025de3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025e44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025e7d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025eb9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025ef1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800258b8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025ab2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025aff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025c07`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025c54`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800258b8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025ab2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025aff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025c07`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025c54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025a72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002611a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002613d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025a72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002611a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002613d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800259fd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800259fd`

## string_xrefs

- `0x1800258d9`: `TaskCache\Tree`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall JobStore::RegJobSecurityQuery(JobStore *this, OLECHAR *a2, struct JobSecurity *a3)
{
  struct JobSecurity *v3; // r12
  JobStore *v5; // r15
  HKEY v6; // rdi
  BSTR *v7; // rax
  BSTR *v8; // rbx
  BSTR v9; // rax
  struct IErrorInfo *v10; // rdx
  OLECHAR v11; // ax
  const WCHAR *v12; // rdx
  LSTATUS v13; // eax
  signed int v14; // esi
  HKEY v15; // rcx
  LSTATUS Value; // eax
  BYTE *v17; // rbx
  LSTATUS v18; // eax
  int v19; // eax
  BSTR *v21; // rax
  BSTR *v22; // r15
  BSTR v23; // rax
  struct IErrorInfo *v24; // rdx
  BSTR *v25; // rax
  struct IErrorInfo *v26; // rdx
  BSTR *v27; // r12
  UINT v28; // eax
  UINT v29; // ecx
  UINT v30; // r13d
  struct IErrorInfo *v31; // rdx
  BSTR v32; // rcx
  int v33; // r13d
  BSTR *v34; // rax
  BSTR *v35; // r15
  BSTR v36; // rax
  struct IErrorInfo *v37; // rdx
  BSTR *v38; // rax
  struct IErrorInfo *v39; // rdx
  UINT v40; // esi
  UINT v41; // eax
  UINT v42; // r13d
  struct IErrorInfo *v43; // rdx
  BSTR v44; // rcx
  BSTR v45; // rcx
  BSTR v46; // rcx
  BSTR v47; // rcx
  BSTR v48; // rcx
  BSTR v49; // rcx
  BSTR v50; // rcx
  HKEY hKey; // [rsp+30h] [rbp-49h] BYREF
  void **pExceptionObject; // [rsp+38h] [rbp-41h] BYREF
  char v53; // [rsp+40h] [rbp-39h]
  const unsigned __int16 *v54; // [rsp+48h] [rbp-31h]
  __int64 v55; // [rsp+50h] [rbp-29h]
  __int64 v56; // [rsp+58h] [rbp-21h]
  int v57; // [rsp+60h] [rbp-19h]
  __int64 v58; // [rsp+64h] [rbp-15h]
  BSTR *v59; // [rsp+70h] [rbp-9h]
  BSTR *v60; // [rsp+78h] [rbp-1h]
  __int64 v61; // [rsp+80h] [rbp+7h]
  BSTR *v62; // [rsp+88h] [rbp+Fh]
  BSTR *cbData; // [rsp+E8h] [rbp+6Fh] BYREF
  struct JobSecurity *v65; // [rsp+F0h] [rbp+77h]
  BSTR *Type; // [rsp+F8h] [rbp+7Fh] BYREF

  v65 = a3;
  v3 = a3;
  v5 = this;
  v6 = 0;
  v61 = 0;
  hKey = 0;
  v7 = (BSTR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
  v8 = v7;
  if ( !v7 )
  {
    v53 = 0;
    v54 = &qword_1800A4718;
    v55 = 0;
    v56 = 0;
    v57 = 14;
    v58 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  cbData = v7;
  v7[1] = 0;
  *((_DWORD *)v7 + 4) = 1;
  v9 = SysAllocString(L"TaskCache\\Tree");
  *v8 = v9;
  if ( !v9 )
    _com_raise_error(-2147024882, v10);
  v59 = v8;
  if ( a2 )
  {
    v11 = *a2;
    if ( *a2 == 92 )
      v11 = *++a2;
    if ( v11 )
    {
      v21 = (BSTR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v22 = v21;
      if ( !v21 )
      {
        v53 = 0;
        v54 = &qword_1800A4718;
        v55 = 0;
        v56 = 0;
        v57 = 14;
        v58 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      cbData = v21;
      v21[1] = 0;
      *((_DWORD *)v21 + 4) = 1;
      v23 = SysAllocString(L"\\");
      *v22 = v23;
      if ( !v23 )
        _com_raise_error(-2147024882, v24);
      v62 = v22;
      v25 = (BSTR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v27 = v25;
      if ( !v25 )
      {
        v53 = 0;
        v54 = &qword_1800A4718;
        v55 = 0;
        v56 = 0;
        v57 = 14;
        v58 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      v60 = v25;
      v25[1] = 0;
      *((_DWORD *)v25 + 4) = 1;
      if ( *v8 )
        v28 = SysStringLen(*v8);
      else
        v28 = 0;
      LODWORD(cbData) = v28;
      if ( *v22 )
      {
        v29 = SysStringLen(*v22);
        v28 = (unsigned int)cbData;
      }
      else
      {
        v29 = 0;
      }
      LODWORD(Type) = v29;
      v30 = v29 + v28;
      if ( v29 + v28 < v28 || (v26 = (struct IErrorInfo *)(2LL * v30), (unsigned __int64)v26 > 0xFFFFFFFF) )
        _com_raise_error(-2147024882, v26);
      v32 = SysAllocStringByteLen(0, (UINT)v26);
      *v27 = v32;
      if ( v32 )
      {
        v33 = (int)cbData;
        if ( *v8 )
          memcpy_0(v32, *v8, 2LL * (unsigned int)((_DWORD)cbData + 1));
        if ( *v22 )
          memcpy_0(&(*v27)[v33], *v22, 2LL * (unsigned int)((_DWORD)Type + 1));
      }
      else if ( v30 )
      {
        _com_raise_error(-2147024882, v31);
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 4, 0xFFFFFFFF) == 1 )
      {
        if ( *v8 )
        {
          SysFreeString(*v8);
          *v8 = 0;
        }
        v47 = v8[1];
        if ( v47 )
        {
          operator delete(v47);
          v8[1] = 0;
        }
        HeapFree(g_PrivateHeap, 0, v8);
      }
      v59 = v27;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v22 + 4, 0xFFFFFFFF) == 1 )
      {
        if ( *v22 )
        {
          SysFreeString(*v22);
          *v22 = 0;
        }
        v48 = v22[1];
        if ( v48 )
        {
          operator delete(v48);
          v22[1] = 0;
        }
        HeapFree(g_PrivateHeap, 0, v22);
      }
      v34 = (BSTR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v35 = v34;
      if ( !v34 )
      {
        v53 = 0;
        v54 = &qword_1800A4718;
        v55 = 0;
        v56 = 0;
        v57 = 14;
        v58 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      cbData = v34;
      v34[1] = 0;
      *((_DWORD *)v34 + 4) = 1;
      v36 = SysAllocString(a2);
      *v35 = v36;
      if ( !v36 && a2 )
        _com_raise_error(-2147024882, v37);
      Type = v35;
      v38 = (BSTR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v8 = v38;
      if ( !v38 )
      {
        v53 = 0;
        v54 = &qword_1800A4718;
        v55 = 0;
        v56 = 0;
        v57 = 14;
        v58 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      v60 = v38;
      v38[1] = 0;
      *((_DWORD *)v38 + 4) = 1;
      if ( *v27 )
        v40 = SysStringLen(*v27);
      else
        v40 = 0;
      if ( *v35 )
        v41 = SysStringLen(*v35);
      else
        v41 = 0;
      LODWORD(cbData) = v41;
      v42 = v41 + v40;
      if ( v41 + v40 < v40 || (v39 = (struct IErrorInfo *)(2LL * v42), (unsigned __int64)v39 > 0xFFFFFFFF) )
        _com_raise_error(-2147024882, v39);
      v44 = SysAllocStringByteLen(0, (UINT)v39);
      *v8 = v44;
      if ( v44 )
      {
        if ( *v27 )
          memcpy_0(v44, *v27, 2LL * (v40 + 1));
        if ( *v35 )
          memcpy_0(&(*v8)[v40], *v35, 2LL * (unsigned int)((_DWORD)cbData + 1));
      }
      else if ( v42 )
      {
        _com_raise_error(-2147024882, v43);
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v27 + 4, 0xFFFFFFFF) == 1 )
      {
        if ( *v27 )
        {
          SysFreeString(*v27);
          *v27 = 0;
        }
        v49 = v27[1];
        if ( v49 )
        {
          operator delete(v49);
          v27[1] = 0;
        }
        HeapFree(g_PrivateHeap, 0, v27);
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v35 + 4, 0xFFFFFFFF) == 1 )
      {
        if ( *v35 )
        {
          SysFreeString(*v35);
          *v35 = 0;
        }
        v50 = v35[1];
        if ( v50 )
        {
          operator delete(v50);
          v35[1] = 0;
        }
        HeapFree(g_PrivateHeap, 0, v35);
        v3 = v65;
        v5 = this;
      }
      else
      {
        v3 = v65;
        v5 = this;
      }
    }
  }
  if ( v8 )
    v12 = *v8;
  else
    v12 = 0;
  v13 = RegOpenKeyExW(*((HKEY *)v5 + 2), v12, 0, 0xF003Fu, &hKey);
  v14 = v13;
  if ( v13 )
  {
    if ( v13 > 0 )
      v14 = (unsigned __int16)v13 | 0x80070000;
    if ( v8 && _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 4, 0xFFFFFFFF) == 1 )
    {
      if ( *v8 )
      {
        SysFreeString(*v8);
        *v8 = 0;
      }
      v45 = v8[1];
      if ( v45 )
      {
        operator delete(v45);
        v8[1] = 0;
      }
      HeapFree(g_PrivateHeap, 0, v8);
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( v14 < 0 )
      goto LABEL_35;
  }
  else
  {
    v6 = hKey;
    v15 = 0;
    hKey = 0;
    if ( v8 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 4, 0xFFFFFFFF) == 1 )
      {
        if ( *v8 )
        {
          SysFreeString(*v8);
          *v8 = 0;
        }
        v46 = v8[1];
        if ( v46 )
        {
          operator delete(v46);
          v8[1] = 0;
        }
        HeapFree(g_PrivateHeap, 0, v8);
      }
      v15 = hKey;
    }
    if ( v15 )
      RegCloseKey(v15);
  }
  LODWORD(Type) = 3;
  LODWORD(cbData) = 0;
  hKey = 0;
  Value = RegQueryValueExW(v6, L"SD", 0, (LPDWORD)&Type, 0, (LPDWORD)&cbData);
  v14 = Value;
  if ( Value )
  {
    if ( Value > 0 )
      v14 = (unsigned __int16)Value | 0x80070000;
LABEL_33:
    if ( v14 < 0 )
      goto LABEL_35;
    goto LABEL_34;
  }
  if ( (_DWORD)Type != 3 )
  {
LABEL_126:
    tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&hKey);
    v14 = -2147023537;
    goto LABEL_35;
  }
  v17 = (BYTE *)LocalAlloc(0, (unsigned int)cbData);
  hKey = (HKEY)v17;
  if ( !v17 )
  {
    tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&hKey);
LABEL_34:
    v14 = 0;
    goto LABEL_35;
  }
  v18 = RegQueryValueExW(v6, L"SD", 0, (LPDWORD)&Type, v17, (LPDWORD)&cbData);
  v14 = v18;
  if ( v18 )
  {
    if ( v18 > 0 )
      v14 = (unsigned __int16)v18 | 0x80070000;
    LocalFree(v17);
    goto LABEL_33;
  }
  if ( (_DWORD)Type == 3 )
  {
    v19 = (int)cbData;
    if ( (_DWORD)cbData )
    {
      if ( *(_QWORD *)v3 )
      {
        LocalFree(*(HLOCAL *)v3);
        v19 = (int)cbData;
      }
      *(_QWORD *)v3 = v17;
      *((_DWORD *)v3 + 2) = v19;
      goto LABEL_34;
    }
    goto LABEL_126;
  }
  LocalFree(v17);
  v14 = -2147023537;
LABEL_35:
  if ( v6 )
    RegCloseKey(v6);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180025870  mov     [rsp-8+arg_10], r8
0x180025875  mov     [rsp-8+arg_0], rcx
0x18002587a  push    rbp
0x18002587b  push    rbx
0x18002587c  push    rsi
0x18002587d  push    rdi
0x18002587e  push    r12
0x180025880  push    r13
0x180025882  push    r14
0x180025884  push    r15
0x180025886  lea     rbp, [rsp-1Fh]
0x18002588b  sub     rsp, 98h
0x180025892  mov     r12, r8
0x180025895  mov     rsi, rdx
0x180025898  mov     r15, rcx
0x18002589b  xor     r13d, r13d
0x18002589e  mov     edi, r13d
0x1800258a1  mov     [rbp+57h+var_50], r13
0x1800258a5  mov     [rbp+57h+hKey], r13
0x1800258a9  xor     edx, edx; dwFlags
0x1800258ab  mov     r8d, 18h; dwBytes
0x1800258b1  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x1800258b8  call    cs:__imp_HeapAlloc
0x1800258be  mov     rbx, rax
0x1800258c1  test    rax, rax
0x1800258c4  jz      loc_180025F1D
0x1800258ca  mov     [rbp+57h+cbData], rax
0x1800258ce  mov     [rax+8], r13
0x1800258d2  mov     dword ptr [rax+10h], 1
0x1800258d9  lea     rcx, aTaskcacheTree; "TaskCache\\Tree"
0x1800258e0  call    cs:__imp_SysAllocString
0x1800258e6  mov     [rbx], rax
0x1800258e9  test    rax, rax
0x1800258ec  jz      loc_180025B63
0x1800258f2  mov     [rbp+57h+var_60], rbx
0x1800258f6  mov     r14d, 0FFFFFFFFh
0x1800258fc  test    rsi, rsi
0x1800258ff  jz      short loc_18002591A
0x180025901  movzx   eax, word ptr [rsi]
0x180025904  cmp     ax, 5Ch ; '\'
0x180025908  jnz     short loc_180025911
0x18002590a  add     rsi, 2
0x18002590e  movzx   eax, word ptr [rsi]
0x180025911  test    ax, ax
0x180025914  jnz     loc_180025AA3
0x18002591a  test    rbx, rbx
0x18002591d  jz      loc_180025D7E
0x180025923  mov     rdx, [rbx]; lpSubKey
0x180025926  lea     rax, [rbp+57h+hKey]
0x18002592a  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18002592f  mov     r9d, 0F003Fh; samDesired
0x180025935  xor     r8d, r8d; ulOptions
0x180025938  mov     rcx, [r15+10h]; hKey
0x18002593c  call    cs:__imp_RegOpenKeyExW
0x180025942  mov     esi, eax
0x180025944  test    eax, eax
0x180025946  jz      short loc_180025981
0x180025948  jle     short loc_180025953
0x18002594a  movzx   esi, ax
0x18002594d  or      esi, 80070000h
0x180025953  test    rbx, rbx
0x180025956  jz      short loc_180025968
0x180025958  lock xadd [rbx+10h], r14d
0x18002595e  cmp     r14d, 1
0x180025962  jz      loc_180025D49
0x180025968  mov     rcx, [rbp+57h+hKey]; hKey
0x18002596c  test    rcx, rcx
0x18002596f  jz      short loc_180025977
0x180025971  call    cs:__imp_RegCloseKey
0x180025977  test    esi, esi
0x180025979  js      loc_180025A7F
0x18002597f  jmp     short loc_1800259B0
0x180025981  mov     rdi, [rbp+57h+hKey]
0x180025985  mov     rcx, r13
0x180025988  mov     [rbp+57h+hKey], rcx
0x18002598c  test    rbx, rbx
0x18002598f  jz      short loc_1800259A5
0x180025991  lock xadd [rbx+10h], r14d
0x180025997  cmp     r14d, 1
0x18002599b  jz      loc_180025DB9
0x1800259a1  mov     rcx, [rbp+57h+hKey]; hKey
0x1800259a5  test    rcx, rcx
0x1800259a8  jz      short loc_1800259B0
0x1800259aa  call    cs:__imp_RegCloseKey
0x1800259b0  mov     dword ptr [rbp+57h+Type], 3
0x1800259b7  mov     dword ptr [rbp+57h+cbData], r13d
0x1800259bb  mov     [rbp+57h+hKey], r13
0x1800259bf  lea     rax, [rbp+57h+cbData]
0x1800259c3  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x1800259c8  mov     [rsp+0D0h+phkResult], r13; lpData
0x1800259cd  lea     r9, [rbp+57h+Type]; lpType
0x1800259d1  xor     r8d, r8d; lpReserved
0x1800259d4  lea     rdx, ValueName; "SD"
0x1800259db  mov     rcx, rdi; hKey
0x1800259de  call    cs:__imp_RegQueryValueExW
0x1800259e4  mov     esi, eax
0x1800259e6  test    eax, eax
0x1800259e8  jnz     loc_180025F04
0x1800259ee  cmp     dword ptr [rbp+57h+Type], 3
0x1800259f2  jnz     loc_1800260F6
0x1800259f8  mov     edx, dword ptr [rbp+57h+cbData]; uBytes
0x1800259fb  xor     ecx, ecx; uFlags
0x1800259fd  call    cs:__imp_LocalAlloc
0x180025a03  mov     rbx, rax
0x180025a06  mov     [rbp+57h+hKey], rax
0x180025a0a  test    rax, rax
0x180025a0d  jz      loc_180026109
0x180025a13  lea     rax, [rbp+57h+cbData]
0x180025a17  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x180025a1c  mov     [rsp+0D0h+phkResult], rbx; lpData
0x180025a21  lea     r9, [rbp+57h+Type]; lpType
0x180025a25  xor     r8d, r8d; lpReserved
0x180025a28  lea     rdx, ValueName; "SD"
0x180025a2f  mov     rcx, rdi; hKey
0x180025a32  call    cs:__imp_RegQueryValueExW
0x180025a38  mov     esi, eax
0x180025a3a  test    eax, eax
0x180025a3c  jnz     loc_180025DA5
0x180025a42  cmp     dword ptr [rbp+57h+Type], 3
0x180025a46  jnz     loc_180026117
0x180025a4c  mov     eax, dword ptr [rbp+57h+cbData]
0x180025a4f  test    eax, eax
0x180025a51  jz      loc_18002612A
0x180025a57  mov     rcx, [r12]; hMem
0x180025a5b  test    rcx, rcx
0x180025a5e  jnz     loc_18002613D
0x180025a64  mov     [r12], rbx
0x180025a68  mov     [r12+8], eax
0x180025a6d  jmp     short loc_180025A7C
0x180025a6f  mov     rcx, rbx; hMem
0x180025a72  call    cs:__imp_LocalFree
0x180025a78  test    esi, esi
0x180025a7a  js      short loc_180025A7F
0x180025a7c  mov     esi, r13d
0x180025a7f  test    rdi, rdi
0x180025a82  jz      short loc_180025A8D
0x180025a84  mov     rcx, rdi; hKey
0x180025a87  call    cs:__imp_RegCloseKey
0x180025a8d  mov     eax, esi
0x180025a8f  add     rsp, 98h
0x180025a96  pop     r15
0x180025a98  pop     r14
0x180025a9a  pop     r13
0x180025a9c  pop     r12
0x180025a9e  pop     rdi
0x180025a9f  pop     rsi
0x180025aa0  pop     rbx
0x180025aa1  pop     rbp
0x180025aa2  retn
0x180025aa3  xor     edx, edx; dwFlags
0x180025aa5  mov     r8d, 18h; dwBytes
0x180025aab  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180025ab2  call    cs:__imp_HeapAlloc
0x180025ab8  mov     r15, rax
0x180025abb  test    rax, rax
0x180025abe  jz      loc_180025F5F
0x180025ac4  mov     [rbp+57h+cbData], rax
0x180025ac8  mov     [rax+8], r13
0x180025acc  mov     dword ptr [rax+10h], 1
0x180025ad3  lea     rcx, asc_1800A3DA8; "\\"
0x180025ada  call    cs:__imp_SysAllocString
0x180025ae0  mov     [r15], rax
0x180025ae3  test    rax, rax
0x180025ae6  jz      loc_180025D86
0x180025aec  mov     [rbp+57h+var_48], r15
0x180025af0  xor     edx, edx; dwFlags
0x180025af2  mov     r8d, 18h; dwBytes
0x180025af8  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180025aff  call    cs:__imp_HeapAlloc
0x180025b05  mov     r12, rax
0x180025b08  test    rax, rax
0x180025b0b  jz      loc_180025FA1
0x180025b11  mov     [rbp+57h+var_58], rax
0x180025b15  mov     [rax+8], r13
0x180025b19  mov     dword ptr [rax+10h], 1
0x180025b20  mov     rcx, [rbx]; pbstr
0x180025b23  test    rcx, rcx
0x180025b26  jz      loc_180025FE3
0x180025b2c  call    cs:__imp_SysStringLen
0x180025b32  mov     dword ptr [rbp+57h+cbData], eax
0x180025b35  mov     rcx, [r15]; pbstr
0x180025b38  test    rcx, rcx
0x180025b3b  jz      loc_180025FEB
0x180025b41  call    cs:__imp_SysStringLen
0x180025b47  mov     ecx, eax
0x180025b49  mov     eax, dword ptr [rbp+57h+cbData]
0x180025b4c  mov     dword ptr [rbp+57h+Type], ecx
0x180025b4f  lea     r13d, [rcx+rax]
0x180025b53  cmp     r13d, eax
0x180025b56  jnb     short loc_180025B6E
0x180025b58  mov     ecx, 8007000Eh; int
0x180025b5d  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180025b63  mov     ecx, 8007000Eh; int
0x180025b68  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180025b6e  mov     edx, r13d
0x180025b71  add     rdx, rdx; len
0x180025b74  mov     eax, 0FFFFFFFFh
0x180025b79  cmp     rdx, rax
0x180025b7c  ja      short loc_180025B58
0x180025b7e  xor     ecx, ecx; psz
0x180025b80  call    cs:__imp_SysAllocStringByteLen
0x180025b86  mov     rcx, rax; void *
0x180025b89  mov     [r12], rax
0x180025b8d  test    rax, rax
0x180025b90  jz      loc_180025DEE
0x180025b96  mov     rdx, [rbx]; Src
0x180025b99  mov     r13d, dword ptr [rbp+57h+cbData]
0x180025b9d  test    rdx, rdx
0x180025ba0  jz      short loc_180025BAE
0x180025ba2  lea     r8d, [r13+1]
0x180025ba6  add     r8, r8; Size
0x180025ba9  call    memcpy_0
0x180025bae  mov     rdx, [r15]; Src
0x180025bb1  test    rdx, rdx
0x180025bb4  jz      short loc_180025BD1
0x180025bb6  mov     r8d, dword ptr [rbp+57h+Type]
0x180025bba  inc     r8d
0x180025bbd  add     r8, r8; Size
0x180025bc0  mov     ecx, r13d
0x180025bc3  mov     rax, [r12]
0x180025bc7  lea     rcx, [rax+rcx*2]; void *
0x180025bcb  call    memcpy_0
0x180025bd0  nop
0x180025bd1  mov     eax, r14d
0x180025bd4  lock xadd [rbx+10h], eax
0x180025bd9  cmp     eax, 1
0x180025bdc  jz      loc_180025E16
0x180025be2  mov     [rbp+57h+var_60], r12
0x180025be6  mov     eax, r14d
0x180025be9  lock xadd [r15+10h], eax
0x180025bef  cmp     eax, 1
0x180025bf2  jz      loc_180025E4F
0x180025bf8  xor     edx, edx; dwFlags
0x180025bfa  mov     r8d, 18h; dwBytes
0x180025c00  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180025c07  call    cs:__imp_HeapAlloc
0x180025c0d  mov     r15, rax
0x180025c10  test    rax, rax
0x180025c13  jz      loc_180026017
0x180025c19  mov     [rbp+57h+cbData], rax
0x180025c1d  mov     qword ptr [rax+8], 0
0x180025c25  mov     dword ptr [rax+10h], 1
0x180025c2c  mov     rcx, rsi; psz
0x180025c2f  call    cs:__imp_SysAllocString
0x180025c35  mov     [r15], rax
0x180025c38  test    rax, rax
0x180025c3b  jz      loc_180025D91
0x180025c41  mov     [rbp+57h+Type], r15
0x180025c45  xor     edx, edx; dwFlags
0x180025c47  mov     r8d, 18h; dwBytes
0x180025c4d  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180025c54  call    cs:__imp_HeapAlloc
0x180025c5a  mov     rbx, rax
0x180025c5d  test    rax, rax
0x180025c60  jz      loc_180026061
0x180025c66  mov     [rbp+57h+var_58], rax
0x180025c6a  mov     qword ptr [rax+8], 0
0x180025c72  mov     dword ptr [rax+10h], 1
0x180025c79  mov     rcx, [r12]; pbstr
0x180025c7d  test    rcx, rcx
0x180025c80  jz      loc_1800260AB
0x180025c86  call    cs:__imp_SysStringLen
0x180025c8c  mov     esi, eax
0x180025c8e  mov     rcx, [r15]; pbstr
0x180025c91  test    rcx, rcx
0x180025c94  jz      loc_1800260B2
0x180025c9a  call    cs:__imp_SysStringLen
0x180025ca0  mov     dword ptr [rbp+57h+cbData], eax
0x180025ca3  lea     r13d, [rax+rsi]
0x180025ca7  cmp     r13d, esi
0x180025caa  jnb     short loc_180025CB7
0x180025cac  mov     ecx, 8007000Eh; int
0x180025cb1  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180025cb7  mov     edx, r13d
0x180025cba  add     rdx, rdx; len
0x180025cbd  mov     eax, 0FFFFFFFFh
0x180025cc2  cmp     rdx, rax
0x180025cc5  ja      short loc_180025CAC
0x180025cc7  xor     ecx, ecx; psz
0x180025cc9  call    cs:__imp_SysAllocStringByteLen
0x180025ccf  mov     rcx, rax; void *
0x180025cd2  mov     [rbx], rax
0x180025cd5  test    rax, rax
0x180025cd8  jz      loc_180025E02
0x180025cde  mov     rdx, [r12]; Src
0x180025ce2  test    rdx, rdx
0x180025ce5  jz      short loc_180025CF3
0x180025ce7  lea     r8d, [rsi+1]
0x180025ceb  add     r8, r8; Size
0x180025cee  call    memcpy_0
0x180025cf3  mov     rdx, [r15]; Src
0x180025cf6  test    rdx, rdx
0x180025cf9  jz      short loc_180025D14
0x180025cfb  mov     r8d, dword ptr [rbp+57h+cbData]
0x180025cff  inc     r8d
0x180025d02  add     r8, r8; Size
0x180025d05  mov     ecx, esi
0x180025d07  mov     rax, [rbx]
0x180025d0a  lea     rcx, [rax+rcx*2]; void *
0x180025d0e  call    memcpy_0
  ... truncated ...
```
