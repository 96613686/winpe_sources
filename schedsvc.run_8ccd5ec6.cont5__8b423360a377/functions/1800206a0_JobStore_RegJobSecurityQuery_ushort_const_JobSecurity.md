# JobStore::RegJobSecurityQuery(ushort const *,JobSecurity &)

- ea: `0x1800206a0`
- end: `0x180020f2c`
- name: `?RegJobSecurityQuery@JobStore@@QEBAJPEBGAEAVJobSecurity@@@Z`
- size: `2188`
- prototype: `int(JobStore *__hidden this, const unsigned __int16 *, struct JobSecurity *)`
- caller_count: `8`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18001d7ac`
- `0x18001fe44`
- `0x1800204e0`
- `0x180023c4c`
- `0x180047ee0`
- `0x18004fc18`
- `0x18006fed4`
- `0x18007a294`

## callees

- `0x18000cc40`
- `0x18000d830`
- `0x18001fe10`
- `0x1800206a0`
- `0x180054824`
- `0x18005a2bc`
- `0x18005a2d6`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180020716`
- `OLEAUT32!__imp_SysAllocString` at `0x18002094d`
- `OLEAUT32!__imp_SysAllocString` at `0x180020ac6`
- `OLEAUT32!__imp_SysAllocString` at `0x180020716`
- `OLEAUT32!__imp_SysAllocString` at `0x18002094d`
- `OLEAUT32!__imp_SysAllocString` at `0x180020ac6`
- `OLEAUT32!__imp_SysFreeString` at `0x180020c06`
- `OLEAUT32!__imp_SysFreeString` at `0x180020c82`
- `OLEAUT32!__imp_SysFreeString` at `0x180020c06`
- `OLEAUT32!__imp_SysFreeString` at `0x180020c82`
- `OLEAUT32!__imp_SysStringLen` at `0x1800209ab`
- `OLEAUT32!__imp_SysStringLen` at `0x1800209c6`
- `OLEAUT32!__imp_SysStringLen` at `0x180020b29`
- `OLEAUT32!__imp_SysStringLen` at `0x180020b43`
- `OLEAUT32!__imp_SysStringLen` at `0x1800209ab`
- `OLEAUT32!__imp_SysStringLen` at `0x1800209c6`
- `OLEAUT32!__imp_SysStringLen` at `0x180020b29`
- `OLEAUT32!__imp_SysStringLen` at `0x180020b43`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180020a0b`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180020b78`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180020a0b`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180020b78`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020778`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020778`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002082c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002088c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002082c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002088c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800207b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800207f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800208ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800207b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800207f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800208ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020c2e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020caa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020c2e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020caa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800206e8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002091f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020978`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020a98`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020af1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800206e8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002091f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020978`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020a98`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020af1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800208d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020eee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020f17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800208d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020eee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020f17`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020851`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020851`

## string_xrefs

- `0x18002070f`: `TaskCache\Tree`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall JobStore::RegJobSecurityQuery(JobStore *this, OLECHAR *a2, struct JobSecurity *a3)
{
  struct JobSecurity *v3; // r12
  JobStore *v5; // r15
  HKEY v6; // rdi
  volatile signed __int32 *v7; // rax
  volatile signed __int32 *v8; // rbx
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
  volatile signed __int32 *v25; // rax
  struct IErrorInfo *v26; // rdx
  volatile signed __int32 *v27; // r12
  UINT v28; // eax
  UINT v29; // ecx
  UINT v30; // r13d
  struct IErrorInfo *v31; // rdx
  BSTR v32; // rcx
  unsigned int v33; // r13d
  BSTR *v34; // rax
  BSTR *v35; // r15
  BSTR v36; // rax
  struct IErrorInfo *v37; // rdx
  volatile signed __int32 *v38; // rax
  struct IErrorInfo *v39; // rdx
  UINT v40; // esi
  UINT v41; // eax
  UINT v42; // r13d
  struct IErrorInfo *v43; // rdx
  BSTR v44; // rcx
  void *v45; // rcx
  void *v46; // rcx
  HKEY hKey; // [rsp+30h] [rbp-49h] BYREF
  void **pExceptionObject; // [rsp+38h] [rbp-41h] BYREF
  char v49; // [rsp+40h] [rbp-39h]
  const unsigned __int16 *v50; // [rsp+48h] [rbp-31h]
  __int64 v51; // [rsp+50h] [rbp-29h]
  __int64 v52; // [rsp+58h] [rbp-21h]
  int v53; // [rsp+60h] [rbp-19h]
  __int64 v54; // [rsp+64h] [rbp-15h]
  volatile signed __int32 *v55; // [rsp+70h] [rbp-9h]
  volatile signed __int32 *v56; // [rsp+78h] [rbp-1h]
  __int64 v57; // [rsp+80h] [rbp+7h]
  BSTR *v58; // [rsp+88h] [rbp+Fh]
  _QWORD *cbData; // [rsp+E8h] [rbp+6Fh] BYREF
  struct JobSecurity *v61; // [rsp+F0h] [rbp+77h]
  BSTR *Type; // [rsp+F8h] [rbp+7Fh] BYREF

  v61 = a3;
  v3 = a3;
  v5 = this;
  v6 = 0;
  v57 = 0;
  hKey = 0;
  v7 = (volatile signed __int32 *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
  v8 = v7;
  if ( !v7 )
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
  cbData = v7;
  *((_QWORD *)v7 + 1) = 0;
  *((_DWORD *)v7 + 4) = 1;
  v9 = SysAllocString(L"TaskCache\\Tree");
  *(_QWORD *)v8 = v9;
  if ( !v9 )
    _com_raise_error(-2147024882, v10);
  v55 = v8;
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
        v49 = 0;
        v50 = &qword_1800A8718;
        v51 = 0;
        v52 = 0;
        v53 = 14;
        v54 = -1;
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
      v58 = v22;
      v25 = (volatile signed __int32 *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v27 = v25;
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
      v56 = v25;
      *((_QWORD *)v25 + 1) = 0;
      *((_DWORD *)v25 + 4) = 1;
      if ( *(_QWORD *)v8 )
        v28 = SysStringLen(*(BSTR *)v8);
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
      *(_QWORD *)v27 = v32;
      if ( v32 )
      {
        v33 = (unsigned int)cbData;
        if ( *(_QWORD *)v8 )
          memcpy_0(v32, *(const void **)v8, 2LL * (unsigned int)((_DWORD)cbData + 1));
        v31 = (struct IErrorInfo *)*v22;
        if ( *v22 )
          memcpy_0((void *)(*(_QWORD *)v27 + 2LL * v33), v31, 2LL * (unsigned int)((_DWORD)Type + 1));
      }
      else if ( v30 )
      {
        _com_raise_error(-2147024882, v31);
      }
      if ( _InterlockedExchangeAdd(v8 + 4, 0xFFFFFFFF) == 1 )
        _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v8, (unsigned int)v31);
      v55 = v27;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v22 + 4, 0xFFFFFFFF) == 1 )
        _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v22, (unsigned int)v31);
      v34 = (BSTR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v35 = v34;
      if ( !v34 )
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
      cbData = v34;
      v34[1] = 0;
      *((_DWORD *)v34 + 4) = 1;
      v36 = SysAllocString(a2);
      *v35 = v36;
      if ( !v36 && a2 )
        _com_raise_error(-2147024882, v37);
      Type = v35;
      v38 = (volatile signed __int32 *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v8 = v38;
      if ( !v38 )
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
      v56 = v38;
      *((_QWORD *)v38 + 1) = 0;
      *((_DWORD *)v38 + 4) = 1;
      if ( *(_QWORD *)v27 )
        v40 = SysStringLen(*(BSTR *)v27);
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
      *(_QWORD *)v8 = v44;
      if ( v44 )
      {
        if ( *(_QWORD *)v27 )
          memcpy_0(v44, *(const void **)v27, 2LL * (v40 + 1));
        v43 = (struct IErrorInfo *)*v35;
        if ( *v35 )
          memcpy_0((void *)(*(_QWORD *)v8 + 2LL * v40), v43, 2LL * (unsigned int)((_DWORD)cbData + 1));
      }
      else if ( v42 )
      {
        _com_raise_error(-2147024882, v43);
      }
      if ( _InterlockedExchangeAdd(v27 + 4, 0xFFFFFFFF) == 1 )
        _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v27, (unsigned int)v43);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v35 + 4, 0xFFFFFFFF) == 1 )
        _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v35, (unsigned int)v43);
      v3 = v61;
      v5 = this;
    }
  }
  if ( v8 )
    v12 = *(const WCHAR **)v8;
  else
    v12 = 0;
  v13 = RegOpenKeyExW(*((HKEY *)v5 + 2), v12, 0, 0xF003Fu, &hKey);
  v14 = v13;
  if ( v13 )
  {
    if ( v13 > 0 )
      v14 = (unsigned __int16)v13 | 0x80070000;
    if ( v8 && _InterlockedExchangeAdd(v8 + 4, 0xFFFFFFFF) == 1 )
    {
      if ( *(_QWORD *)v8 )
      {
        SysFreeString(*(BSTR *)v8);
        *(_QWORD *)v8 = 0;
      }
      v45 = (void *)*((_QWORD *)v8 + 1);
      if ( v45 )
      {
        operator delete(v45);
        *((_QWORD *)v8 + 1) = 0;
      }
      HeapFree(g_PrivateHeap, 0, (LPVOID)v8);
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
      if ( _InterlockedExchangeAdd(v8 + 4, 0xFFFFFFFF) == 1 )
      {
        if ( *(_QWORD *)v8 )
        {
          SysFreeString(*(BSTR *)v8);
          *(_QWORD *)v8 = 0;
        }
        v46 = (void *)*((_QWORD *)v8 + 1);
        if ( v46 )
        {
          operator delete(v46);
          *((_QWORD *)v8 + 1) = 0;
        }
        HeapFree(g_PrivateHeap, 0, (LPVOID)v8);
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
LABEL_109:
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
    goto LABEL_109;
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
0x1800206a0  mov     [rsp-8+arg_10], r8
0x1800206a5  mov     [rsp-8+arg_0], rcx
0x1800206aa  push    rbp
0x1800206ab  push    rbx
0x1800206ac  push    rsi
0x1800206ad  push    rdi
0x1800206ae  push    r12
0x1800206b0  push    r13
0x1800206b2  push    r14
0x1800206b4  push    r15
0x1800206b6  lea     rbp, [rsp-1Fh]
0x1800206bb  sub     rsp, 98h
0x1800206c2  mov     r12, r8
0x1800206c5  mov     rsi, rdx
0x1800206c8  mov     r15, rcx
0x1800206cb  xor     r13d, r13d
0x1800206ce  mov     edi, r13d
0x1800206d1  mov     [rbp+57h+var_50], r13
0x1800206d5  mov     [rbp+57h+hKey], r13
0x1800206d9  xor     edx, edx; dwFlags
0x1800206db  mov     r8d, 18h; dwBytes
0x1800206e1  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x1800206e8  call    cs:__imp_HeapAlloc
0x1800206ef  nop     dword ptr [rax+rax+00h]
0x1800206f4  mov     rbx, rax
0x1800206f7  test    rax, rax
0x1800206fa  jz      loc_180020D36
0x180020700  mov     [rbp+57h+cbData], rax
0x180020704  mov     [rax+8], r13
0x180020708  mov     dword ptr [rax+10h], 1
0x18002070f  lea     rcx, psz; "TaskCache\\Tree"
0x180020716  call    cs:__imp_SysAllocString
0x18002071d  nop     dword ptr [rax+rax+00h]
0x180020722  mov     [rbx], rax
0x180020725  test    rax, rax
0x180020728  jz      loc_1800209EE
0x18002072e  mov     [rbp+57h+var_60], rbx
0x180020732  mov     r14d, 0FFFFFFFFh
0x180020738  test    rsi, rsi
0x18002073b  jz      short loc_180020756
0x18002073d  movzx   eax, word ptr [rsi]
0x180020740  cmp     ax, 5Ch ; '\'
0x180020744  jnz     short loc_18002074D
0x180020746  add     rsi, 2
0x18002074a  movzx   eax, word ptr [rsi]
0x18002074d  test    ax, ax
0x180020750  jnz     loc_180020910
0x180020756  test    rbx, rbx
0x180020759  jz      loc_180020C3F
0x18002075f  mov     rdx, [rbx]; lpSubKey
0x180020762  lea     rax, [rbp+57h+hKey]
0x180020766  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18002076b  mov     r9d, 0F003Fh; samDesired
0x180020771  xor     r8d, r8d; ulOptions
0x180020774  mov     rcx, [r15+10h]; hKey
0x180020778  call    cs:__imp_RegOpenKeyExW
0x18002077f  nop     dword ptr [rax+rax+00h]
0x180020784  mov     esi, eax
0x180020786  test    eax, eax
0x180020788  jz      short loc_1800207C9
0x18002078a  jle     short loc_180020795
0x18002078c  movzx   esi, ax
0x18002078f  or      esi, 80070000h
0x180020795  test    rbx, rbx
0x180020798  jz      short loc_1800207AA
0x18002079a  lock xadd [rbx+10h], r14d
0x1800207a0  cmp     r14d, 1
0x1800207a4  jz      loc_180020BFE
0x1800207aa  mov     rcx, [rbp+57h+hKey]; hKey
0x1800207ae  test    rcx, rcx
0x1800207b1  jz      short loc_1800207BF
0x1800207b3  call    cs:__imp_RegCloseKey
0x1800207ba  nop     dword ptr [rax+rax+00h]
0x1800207bf  test    esi, esi
0x1800207c1  js      loc_1800208E5
0x1800207c7  jmp     short loc_1800207FE
0x1800207c9  mov     rdi, [rbp+57h+hKey]
0x1800207cd  mov     rcx, r13
0x1800207d0  mov     [rbp+57h+hKey], rcx
0x1800207d4  test    rbx, rbx
0x1800207d7  jz      short loc_1800207ED
0x1800207d9  lock xadd [rbx+10h], r14d
0x1800207df  cmp     r14d, 1
0x1800207e3  jz      loc_180020C7A
0x1800207e9  mov     rcx, [rbp+57h+hKey]; hKey
0x1800207ed  test    rcx, rcx
0x1800207f0  jz      short loc_1800207FE
0x1800207f2  call    cs:__imp_RegCloseKey
0x1800207f9  nop     dword ptr [rax+rax+00h]
0x1800207fe  mov     dword ptr [rbp+57h+Type], 3
0x180020805  mov     dword ptr [rbp+57h+cbData], r13d
0x180020809  mov     [rbp+57h+hKey], r13
0x18002080d  lea     rax, [rbp+57h+cbData]
0x180020811  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x180020816  mov     [rsp+0D0h+phkResult], r13; lpData
0x18002081b  lea     r9, [rbp+57h+Type]; lpType
0x18002081f  xor     r8d, r8d; lpReserved
0x180020822  lea     rdx, aSd; "SD"
0x180020829  mov     rcx, rdi; hKey
0x18002082c  call    cs:__imp_RegQueryValueExW
0x180020833  nop     dword ptr [rax+rax+00h]
0x180020838  mov     esi, eax
0x18002083a  test    eax, eax
0x18002083c  jnz     loc_180020D22
0x180020842  cmp     dword ptr [rbp+57h+Type], 3
0x180020846  jnz     loc_180020ECA
0x18002084c  mov     edx, dword ptr [rbp+57h+cbData]; uBytes
0x18002084f  xor     ecx, ecx; uFlags
0x180020851  call    cs:__imp_LocalAlloc
0x180020858  nop     dword ptr [rax+rax+00h]
0x18002085d  mov     rbx, rax
0x180020860  mov     [rbp+57h+hKey], rax
0x180020864  test    rax, rax
0x180020867  jz      loc_180020EDD
0x18002086d  lea     rax, [rbp+57h+cbData]
0x180020871  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x180020876  mov     [rsp+0D0h+phkResult], rbx; lpData
0x18002087b  lea     r9, [rbp+57h+Type]; lpType
0x18002087f  xor     r8d, r8d; lpReserved
0x180020882  lea     rdx, aSd; "SD"
0x180020889  mov     rcx, rdi; hKey
0x18002088c  call    cs:__imp_RegQueryValueExW
0x180020893  nop     dword ptr [rax+rax+00h]
0x180020898  mov     esi, eax
0x18002089a  test    eax, eax
0x18002089c  jnz     loc_180020C66
0x1800208a2  cmp     dword ptr [rbp+57h+Type], 3
0x1800208a6  jnz     loc_180020EEB
0x1800208ac  mov     eax, dword ptr [rbp+57h+cbData]
0x1800208af  test    eax, eax
0x1800208b1  jz      loc_180020F04
0x1800208b7  mov     rcx, [r12]; hMem
0x1800208bb  test    rcx, rcx
0x1800208be  jnz     loc_180020F17
0x1800208c4  mov     [r12], rbx
0x1800208c8  mov     [r12+8], eax
0x1800208cd  jmp     short loc_1800208E2
0x1800208cf  mov     rcx, rbx; hMem
0x1800208d2  call    cs:__imp_LocalFree
0x1800208d9  nop     dword ptr [rax+rax+00h]
0x1800208de  test    esi, esi
0x1800208e0  js      short loc_1800208E5
0x1800208e2  mov     esi, r13d
0x1800208e5  test    rdi, rdi
0x1800208e8  jz      short loc_1800208F9
0x1800208ea  mov     rcx, rdi; hKey
0x1800208ed  call    cs:__imp_RegCloseKey
0x1800208f4  nop     dword ptr [rax+rax+00h]
0x1800208f9  mov     eax, esi
0x1800208fb  add     rsp, 98h
0x180020902  pop     r15
0x180020904  pop     r14
0x180020906  pop     r13
0x180020908  pop     r12
0x18002090a  pop     rdi
0x18002090b  pop     rsi
0x18002090c  pop     rbx
0x18002090d  pop     rbp
0x18002090e  retn
0x180020910  xor     edx, edx; dwFlags
0x180020912  mov     r8d, 18h; dwBytes
0x180020918  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18002091f  call    cs:__imp_HeapAlloc
0x180020926  nop     dword ptr [rax+rax+00h]
0x18002092b  mov     r15, rax
0x18002092e  test    rax, rax
0x180020931  jz      loc_180020D78
0x180020937  mov     [rbp+57h+cbData], rax
0x18002093b  mov     [rax+8], r13
0x18002093f  mov     dword ptr [rax+10h], 1
0x180020946  lea     rcx, asc_1800A7EC0; "\\"
0x18002094d  call    cs:__imp_SysAllocString
0x180020954  nop     dword ptr [rax+rax+00h]
0x180020959  mov     [r15], rax
0x18002095c  test    rax, rax
0x18002095f  jz      loc_180020C47
0x180020965  mov     [rbp+57h+var_48], r15
0x180020969  xor     edx, edx; dwFlags
0x18002096b  mov     r8d, 18h; dwBytes
0x180020971  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180020978  call    cs:__imp_HeapAlloc
0x18002097f  nop     dword ptr [rax+rax+00h]
0x180020984  mov     r12, rax
0x180020987  test    rax, rax
0x18002098a  jz      loc_180020DBA
0x180020990  mov     [rbp+57h+var_58], rax
0x180020994  mov     [rax+8], r13
0x180020998  mov     dword ptr [rax+10h], 1
0x18002099f  mov     rcx, [rbx]; pbstr
0x1800209a2  test    rcx, rcx
0x1800209a5  jz      loc_180020DFC
0x1800209ab  call    cs:__imp_SysStringLen
0x1800209b2  nop     dword ptr [rax+rax+00h]
0x1800209b7  mov     dword ptr [rbp+57h+cbData], eax
0x1800209ba  mov     rcx, [r15]; pbstr
0x1800209bd  test    rcx, rcx
0x1800209c0  jz      loc_180020E04
0x1800209c6  call    cs:__imp_SysStringLen
0x1800209cd  nop     dword ptr [rax+rax+00h]
0x1800209d2  mov     ecx, eax
0x1800209d4  mov     eax, dword ptr [rbp+57h+cbData]
0x1800209d7  mov     dword ptr [rbp+57h+Type], ecx
0x1800209da  lea     r13d, [rcx+rax]
0x1800209de  cmp     r13d, eax
0x1800209e1  jnb     short loc_1800209F9
0x1800209e3  mov     ecx, 8007000Eh; int
0x1800209e8  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x1800209ee  mov     ecx, 8007000Eh; int
0x1800209f3  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x1800209f9  mov     edx, r13d
0x1800209fc  add     rdx, rdx; len
0x1800209ff  mov     eax, 0FFFFFFFFh
0x180020a04  cmp     rdx, rax
0x180020a07  ja      short loc_1800209E3
0x180020a09  xor     ecx, ecx; psz
0x180020a0b  call    cs:__imp_SysAllocStringByteLen
0x180020a12  nop     dword ptr [rax+rax+00h]
0x180020a17  mov     rcx, rax; void *
0x180020a1a  mov     [r12], rax
0x180020a1e  test    rax, rax
0x180020a21  jz      loc_180020CBB
0x180020a27  mov     rdx, [rbx]; Src
0x180020a2a  mov     r13d, dword ptr [rbp+57h+cbData]
0x180020a2e  test    rdx, rdx
0x180020a31  jz      short loc_180020A3F
0x180020a33  lea     r8d, [r13+1]
0x180020a37  add     r8, r8; Size
0x180020a3a  call    memcpy_0
0x180020a3f  mov     rdx, [r15]; Src
0x180020a42  test    rdx, rdx
0x180020a45  jz      short loc_180020A62
0x180020a47  mov     r8d, dword ptr [rbp+57h+Type]
0x180020a4b  inc     r8d
0x180020a4e  add     r8, r8; Size
0x180020a51  mov     ecx, r13d
0x180020a54  mov     rax, [r12]
0x180020a58  lea     rcx, [rax+rcx*2]; void *
0x180020a5c  call    memcpy_0
0x180020a61  nop
0x180020a62  mov     eax, r14d
0x180020a65  lock xadd [rbx+10h], eax
0x180020a6a  cmp     eax, 1
0x180020a6d  jz      loc_180020CE3
0x180020a73  mov     [rbp+57h+var_60], r12
0x180020a77  mov     eax, r14d
0x180020a7a  lock xadd [r15+10h], eax
0x180020a80  cmp     eax, 1
0x180020a83  jz      loc_180020CF0
0x180020a89  xor     edx, edx; dwFlags
0x180020a8b  mov     r8d, 18h; dwBytes
0x180020a91  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180020a98  call    cs:__imp_HeapAlloc
0x180020a9f  nop     dword ptr [rax+rax+00h]
0x180020aa4  mov     r15, rax
0x180020aa7  test    rax, rax
0x180020aaa  jz      loc_180020E0C
0x180020ab0  mov     [rbp+57h+cbData], rax
0x180020ab4  mov     qword ptr [rax+8], 0
0x180020abc  mov     dword ptr [rax+10h], 1
0x180020ac3  mov     rcx, rsi; psz
0x180020ac6  call    cs:__imp_SysAllocString
0x180020acd  nop     dword ptr [rax+rax+00h]
0x180020ad2  mov     [r15], rax
0x180020ad5  test    rax, rax
0x180020ad8  jz      loc_180020C52
0x180020ade  mov     [rbp+57h+Type], r15
0x180020ae2  xor     edx, edx; dwFlags
0x180020ae4  mov     r8d, 18h; dwBytes
0x180020aea  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180020af1  call    cs:__imp_HeapAlloc
0x180020af8  nop     dword ptr [rax+rax+00h]
0x180020afd  mov     rbx, rax
0x180020b00  test    rax, rax
0x180020b03  jz      loc_180020E56
0x180020b09  mov     [rbp+57h+var_58], rax
0x180020b0d  mov     qword ptr [rax+8], 0
0x180020b15  mov     dword ptr [rax+10h], 1
0x180020b1c  mov     rcx, [r12]; pbstr
0x180020b20  test    rcx, rcx
0x180020b23  jz      loc_180020EA0
0x180020b29  call    cs:__imp_SysStringLen
0x180020b30  nop     dword ptr [rax+rax+00h]
0x180020b35  mov     esi, eax
0x180020b37  mov     rcx, [r15]; pbstr
0x180020b3a  test    rcx, rcx
0x180020b3d  jz      loc_180020EA7
0x180020b43  call    cs:__imp_SysStringLen
0x180020b4a  nop     dword ptr [rax+rax+00h]
0x180020b4f  mov     dword ptr [rbp+57h+cbData], eax
0x180020b52  lea     r13d, [rax+rsi]
0x180020b56  cmp     r13d, esi
0x180020b59  jnb     short loc_180020B66
0x180020b5b  mov     ecx, 8007000Eh; int
0x180020b60  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180020b66  mov     edx, r13d
0x180020b69  add     rdx, rdx; len
0x180020b6c  mov     eax, 0FFFFFFFFh
0x180020b71  cmp     rdx, rax
0x180020b74  ja      short loc_180020B5B
0x180020b76  xor     ecx, ecx; psz
  ... truncated ...
```
