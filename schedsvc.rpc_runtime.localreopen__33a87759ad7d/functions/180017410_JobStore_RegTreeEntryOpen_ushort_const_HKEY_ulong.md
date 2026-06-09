# JobStore::RegTreeEntryOpen(ushort const *,HKEY__ * *,ulong)

- ea: `0x180017410`
- end: `0x180017b7b`
- name: `?RegTreeEntryOpen@JobStore@@AEBAJPEBGPEAPEAUHKEY__@@K@Z`
- size: `1899`
- prototype: `int(JobStore *__hidden this, const unsigned __int16 *, HKEY *, unsigned int)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180018110`
- `0x18006dd0c`
- `0x18006e3e0`
- `0x18006e7d4`

## callees

- `0x180017410`
- `0x18001a260`
- `0x180052118`
- `0x18005790c`
- `0x180057926`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001747d`
- `OLEAUT32!__imp_SysAllocString` at `0x18001759a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800176ec`
- `OLEAUT32!__imp_SysAllocString` at `0x18001747d`
- `OLEAUT32!__imp_SysAllocString` at `0x18001759a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800176ec`
- `OLEAUT32!__imp_SysFreeString` at `0x180017805`
- `OLEAUT32!__imp_SysFreeString` at `0x180017861`
- `OLEAUT32!__imp_SysFreeString` at `0x1800178be`
- `OLEAUT32!__imp_SysFreeString` at `0x1800178f7`
- `OLEAUT32!__imp_SysFreeString` at `0x180017930`
- `OLEAUT32!__imp_SysFreeString` at `0x180017969`
- `OLEAUT32!__imp_SysFreeString` at `0x180017805`
- `OLEAUT32!__imp_SysFreeString` at `0x180017861`
- `OLEAUT32!__imp_SysFreeString` at `0x1800178be`
- `OLEAUT32!__imp_SysFreeString` at `0x1800178f7`
- `OLEAUT32!__imp_SysFreeString` at `0x180017930`
- `OLEAUT32!__imp_SysFreeString` at `0x180017969`
- `OLEAUT32!__imp_SysStringLen` at `0x1800175ec`
- `OLEAUT32!__imp_SysStringLen` at `0x180017601`
- `OLEAUT32!__imp_SysStringLen` at `0x180017742`
- `OLEAUT32!__imp_SysStringLen` at `0x180017756`
- `OLEAUT32!__imp_SysStringLen` at `0x1800175ec`
- `OLEAUT32!__imp_SysStringLen` at `0x180017601`
- `OLEAUT32!__imp_SysStringLen` at `0x180017742`
- `OLEAUT32!__imp_SysStringLen` at `0x180017756`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180017640`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180017785`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180017640`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180017785`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800174d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800174d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001750b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017559`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001750b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017559`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017827`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017883`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800178e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001791d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017956`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001798e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017827`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017883`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800178e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001791d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017956`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001798e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017455`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017572`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800175bf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800176c4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017711`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017455`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017572`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800175bf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800176c4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017711`

## string_xrefs

- `0x180017476`: `TaskCache\Tree`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall JobStore::RegTreeEntryOpen(JobStore *this, OLECHAR *a2, HKEY *a3)
{
  JobStore *v5; // r14
  BSTR *v6; // rax
  BSTR *v7; // rbx
  BSTR v8; // rax
  struct IErrorInfo *v9; // rdx
  OLECHAR v10; // ax
  const WCHAR *v11; // rdx
  LSTATUS v12; // eax
  unsigned int v13; // esi
  HKEY v15; // rax
  HKEY v16; // rcx
  BSTR *v17; // rax
  BSTR *v18; // r14
  BSTR v19; // rax
  struct IErrorInfo *v20; // rdx
  BSTR *v21; // rax
  struct IErrorInfo *v22; // rdx
  BSTR *v23; // r15
  UINT v24; // eax
  UINT v25; // ecx
  UINT v26; // r12d
  struct IErrorInfo *v27; // rdx
  BSTR v28; // rcx
  BSTR *v29; // rax
  BSTR *v30; // r14
  BSTR v31; // rax
  struct IErrorInfo *v32; // rdx
  BSTR *v33; // rax
  struct IErrorInfo *v34; // rdx
  UINT v35; // esi
  UINT v36; // eax
  UINT v37; // r12d
  struct IErrorInfo *v38; // rdx
  BSTR v39; // rcx
  BSTR v40; // rcx
  BSTR v41; // rcx
  BSTR v42; // rcx
  BSTR v43; // rcx
  BSTR v44; // rcx
  BSTR v45; // rcx
  void **pExceptionObject; // [rsp+30h] [rbp-39h] BYREF
  char v47; // [rsp+38h] [rbp-31h]
  const unsigned __int16 *v48; // [rsp+40h] [rbp-29h]
  __int64 v49; // [rsp+48h] [rbp-21h]
  __int64 v50; // [rsp+50h] [rbp-19h]
  int v51; // [rsp+58h] [rbp-11h]
  __int64 v52; // [rsp+5Ch] [rbp-Dh]
  HKEY hKey; // [rsp+68h] [rbp-1h] BYREF
  BSTR *v54; // [rsp+70h] [rbp+7h]
  BSTR *v55; // [rsp+78h] [rbp+Fh]
  BSTR *v56; // [rsp+80h] [rbp+17h]
  BSTR *v57; // [rsp+88h] [rbp+1Fh]
  UINT v59; // [rsp+E8h] [rbp+7Fh]
  UINT v60; // [rsp+E8h] [rbp+7Fh]

  v5 = this;
  hKey = 0;
  v6 = (BSTR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
  v7 = v6;
  if ( !v6 )
  {
    v47 = 0;
    v48 = &qword_1800A4718;
    v49 = 0;
    v50 = 0;
    v51 = 14;
    v52 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  v55 = v6;
  v6[1] = 0;
  *((_DWORD *)v6 + 4) = 1;
  v8 = SysAllocString(L"TaskCache\\Tree");
  *v7 = v8;
  if ( !v8 )
    _com_raise_error(-2147024882, v9);
  v55 = v7;
  if ( a2 )
  {
    v10 = *a2;
    if ( *a2 == 92 )
      v10 = *++a2;
    if ( v10 )
    {
      v17 = (BSTR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v18 = v17;
      if ( !v17 )
      {
        v47 = 0;
        v48 = &qword_1800A4718;
        v49 = 0;
        v50 = 0;
        v51 = 14;
        v52 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      v54 = v17;
      v17[1] = 0;
      *((_DWORD *)v17 + 4) = 1;
      v19 = SysAllocString(L"\\");
      *v18 = v19;
      if ( !v19 )
        _com_raise_error(-2147024882, v20);
      v57 = v18;
      v21 = (BSTR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v23 = v21;
      if ( !v21 )
      {
        v47 = 0;
        v48 = &qword_1800A4718;
        v49 = 0;
        v50 = 0;
        v51 = 14;
        v52 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      v56 = v21;
      v21[1] = 0;
      *((_DWORD *)v21 + 4) = 1;
      if ( *v7 )
        v24 = SysStringLen(*v7);
      else
        v24 = 0;
      v59 = v24;
      if ( *v18 )
      {
        v25 = SysStringLen(*v18);
        v24 = v59;
      }
      else
      {
        v25 = 0;
      }
      LODWORD(v54) = v25;
      v26 = v25 + v24;
      if ( v25 + v24 < v24 || (v22 = (struct IErrorInfo *)(2LL * v26), (unsigned __int64)v22 > 0xFFFFFFFF) )
        _com_raise_error(-2147024882, v22);
      v28 = SysAllocStringByteLen(0, (UINT)v22);
      *v23 = v28;
      if ( v28 )
      {
        if ( *v7 )
          memcpy_0(v28, *v7, 2LL * (v59 + 1));
        if ( *v18 )
          memcpy_0(&(*v23)[v59], *v18, 2LL * (unsigned int)((_DWORD)v54 + 1));
      }
      else if ( v26 )
      {
        _com_raise_error(-2147024882, v27);
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 4, 0xFFFFFFFF) == 1 )
      {
        if ( *v7 )
        {
          SysFreeString(*v7);
          *v7 = 0;
        }
        v42 = v7[1];
        if ( v42 )
        {
          operator delete(v42);
          v7[1] = 0;
        }
        HeapFree(g_PrivateHeap, 0, v7);
      }
      v55 = v23;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v18 + 4, 0xFFFFFFFF) == 1 )
      {
        if ( *v18 )
        {
          SysFreeString(*v18);
          *v18 = 0;
        }
        v43 = v18[1];
        if ( v43 )
        {
          operator delete(v43);
          v18[1] = 0;
        }
        HeapFree(g_PrivateHeap, 0, v18);
      }
      v29 = (BSTR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v30 = v29;
      if ( !v29 )
      {
        v47 = 0;
        v48 = &qword_1800A4718;
        v49 = 0;
        v50 = 0;
        v51 = 14;
        v52 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      v56 = v29;
      v29[1] = 0;
      *((_DWORD *)v29 + 4) = 1;
      v31 = SysAllocString(a2);
      *v30 = v31;
      if ( !v31 && a2 )
        _com_raise_error(-2147024882, v32);
      v56 = v30;
      v33 = (BSTR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v7 = v33;
      if ( !v33 )
      {
        v47 = 0;
        v48 = &qword_1800A4718;
        v49 = 0;
        v50 = 0;
        v51 = 14;
        v52 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      v57 = v33;
      v33[1] = 0;
      *((_DWORD *)v33 + 4) = 1;
      if ( *v23 )
        v35 = SysStringLen(*v23);
      else
        v35 = 0;
      if ( *v30 )
        v36 = SysStringLen(*v30);
      else
        v36 = 0;
      v60 = v36;
      v37 = v36 + v35;
      if ( v36 + v35 < v35 || (v34 = (struct IErrorInfo *)(2LL * v37), (unsigned __int64)v34 > 0xFFFFFFFF) )
        _com_raise_error(-2147024882, v34);
      v39 = SysAllocStringByteLen(0, (UINT)v34);
      *v7 = v39;
      if ( v39 )
      {
        if ( *v23 )
          memcpy_0(v39, *v23, 2LL * (v35 + 1));
        if ( *v30 )
          memcpy_0(&(*v7)[v35], *v30, 2LL * (v60 + 1));
      }
      else if ( v37 )
      {
        _com_raise_error(-2147024882, v38);
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v23 + 4, 0xFFFFFFFF) == 1 )
      {
        if ( *v23 )
        {
          SysFreeString(*v23);
          *v23 = 0;
        }
        v44 = v23[1];
        if ( v44 )
        {
          operator delete(v44);
          v23[1] = 0;
        }
        HeapFree(g_PrivateHeap, 0, v23);
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v30 + 4, 0xFFFFFFFF) == 1 )
      {
        if ( *v30 )
        {
          SysFreeString(*v30);
          *v30 = 0;
        }
        v45 = v30[1];
        if ( v45 )
        {
          operator delete(v45);
          v30[1] = 0;
        }
        HeapFree(g_PrivateHeap, 0, v30);
        v5 = this;
      }
      else
      {
        v5 = this;
      }
    }
  }
  if ( v7 )
    v11 = *v7;
  else
    v11 = 0;
  v12 = RegOpenKeyExW(*((HKEY *)v5 + 2), v11, 0, 0xF003Fu, &hKey);
  v13 = v12;
  if ( v12 )
  {
    if ( v12 > 0 )
      v13 = (unsigned __int16)v12 | 0x80070000;
    if ( v7 && _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 4, 0xFFFFFFFF) == 1 )
    {
      if ( *v7 )
      {
        SysFreeString(*v7);
        *v7 = 0;
      }
      v40 = v7[1];
      if ( v40 )
      {
        operator delete(v40);
        v7[1] = 0;
      }
      HeapFree(g_PrivateHeap, 0, v7);
    }
    if ( hKey )
      RegCloseKey(hKey);
    return v13;
  }
  else
  {
    v15 = hKey;
    v16 = 0;
    hKey = 0;
    *a3 = v15;
    if ( v7 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 4, 0xFFFFFFFF) == 1 )
      {
        if ( *v7 )
        {
          SysFreeString(*v7);
          *v7 = 0;
        }
        v41 = v7[1];
        if ( v41 )
        {
          operator delete(v41);
          v7[1] = 0;
        }
        HeapFree(g_PrivateHeap, 0, v7);
      }
      v16 = hKey;
    }
    if ( v16 )
      RegCloseKey(v16);
    return 0;
  }
}

```

## disassembly

```asm
0x180017410  mov     [rsp-8+arg_8], rbx
0x180017415  mov     [rsp-8+arg_18], r9d
0x18001741a  mov     [rsp-8+arg_0], rcx
0x18001741f  push    rbp
0x180017420  push    rsi
0x180017421  push    rdi
0x180017422  push    r12
0x180017424  push    r13
0x180017426  push    r14
0x180017428  push    r15
0x18001742a  lea     rbp, [rsp-27h]
0x18001742f  sub     rsp, 90h
0x180017436  mov     r13, r8
0x180017439  mov     rsi, rdx
0x18001743c  mov     r14, rcx
0x18001743f  xor     r12d, r12d
0x180017442  mov     [rbp+57h+hKey], r12
0x180017446  xor     edx, edx; dwFlags
0x180017448  mov     r8d, 18h; dwBytes
0x18001744e  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180017455  call    cs:__imp_HeapAlloc
0x18001745b  mov     rbx, rax
0x18001745e  test    rax, rax
0x180017461  jz      loc_1800179A2
0x180017467  mov     [rbp+57h+var_48], rax
0x18001746b  mov     [rax+8], r12
0x18001746f  mov     dword ptr [rax+10h], 1
0x180017476  lea     rcx, aTaskcacheTree; "TaskCache\\Tree"
0x18001747d  call    cs:__imp_SysAllocString
0x180017483  mov     [rbx], rax
0x180017486  test    rax, rax
0x180017489  jz      loc_180017623
0x18001748f  mov     [rbp+57h+var_48], rbx
0x180017493  mov     edi, 0FFFFFFFFh
0x180017498  test    rsi, rsi
0x18001749b  jz      short loc_1800174B6
0x18001749d  movzx   eax, word ptr [rsi]
0x1800174a0  cmp     ax, 5Ch ; '\'
0x1800174a4  jnz     short loc_1800174AD
0x1800174a6  add     rsi, 2
0x1800174aa  movzx   eax, word ptr [rsi]
0x1800174ad  test    ax, ax
0x1800174b0  jnz     loc_180017563
0x1800174b6  test    rbx, rbx
0x1800174b9  jz      loc_180017832
0x1800174bf  mov     rdx, [rbx]; lpSubKey
0x1800174c2  lea     rax, [rbp+57h+hKey]
0x1800174c6  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800174cb  mov     r9d, 0F003Fh; samDesired
0x1800174d1  xor     r8d, r8d; ulOptions
0x1800174d4  mov     rcx, [r14+10h]; hKey
0x1800174d8  call    cs:__imp_RegOpenKeyExW
0x1800174de  mov     esi, eax
0x1800174e0  test    eax, eax
0x1800174e2  jz      short loc_18001752E
0x1800174e4  jle     short loc_1800174EF
0x1800174e6  movzx   esi, ax
0x1800174e9  or      esi, 80070000h
0x1800174ef  test    rbx, rbx
0x1800174f2  jz      short loc_180017502
0x1800174f4  lock xadd [rbx+10h], edi
0x1800174f9  cmp     edi, 1
0x1800174fc  jz      loc_1800177FD
0x180017502  mov     rcx, [rbp+57h+hKey]; hKey
0x180017506  test    rcx, rcx
0x180017509  jz      short loc_180017511
0x18001750b  call    cs:__imp_RegCloseKey
0x180017511  mov     eax, esi
0x180017513  mov     rbx, [rsp+0C0h+arg_8]
0x18001751b  add     rsp, 90h
0x180017522  pop     r15
0x180017524  pop     r14
0x180017526  pop     r13
0x180017528  pop     r12
0x18001752a  pop     rdi
0x18001752b  pop     rsi
0x18001752c  pop     rbp
0x18001752d  retn
0x18001752e  mov     rax, [rbp+57h+hKey]
0x180017532  mov     rcx, r12
0x180017535  mov     [rbp+57h+hKey], rcx
0x180017539  mov     [r13+0], rax
0x18001753d  test    rbx, rbx
0x180017540  jz      short loc_180017554
0x180017542  lock xadd [rbx+10h], edi
0x180017547  cmp     edi, 1
0x18001754a  jz      loc_180017859
0x180017550  mov     rcx, [rbp+57h+hKey]; hKey
0x180017554  test    rcx, rcx
0x180017557  jz      short loc_18001755F
0x180017559  call    cs:__imp_RegCloseKey
0x18001755f  xor     eax, eax
0x180017561  jmp     short loc_180017513
0x180017563  xor     edx, edx; dwFlags
0x180017565  mov     r8d, 18h; dwBytes
0x18001756b  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180017572  call    cs:__imp_HeapAlloc
0x180017578  mov     r14, rax
0x18001757b  test    rax, rax
0x18001757e  jz      loc_1800179E4
0x180017584  mov     [rbp+57h+var_50], rax
0x180017588  mov     [rax+8], r12
0x18001758c  mov     dword ptr [rax+10h], 1
0x180017593  lea     rcx, asc_1800A3DA8; "\\"
0x18001759a  call    cs:__imp_SysAllocString
0x1800175a0  mov     [r14], rax
0x1800175a3  test    rax, rax
0x1800175a6  jz      loc_18001783A
0x1800175ac  mov     [rbp+57h+var_38], r14
0x1800175b0  xor     edx, edx; dwFlags
0x1800175b2  mov     r8d, 18h; dwBytes
0x1800175b8  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x1800175bf  call    cs:__imp_HeapAlloc
0x1800175c5  mov     r15, rax
0x1800175c8  test    rax, rax
0x1800175cb  jz      loc_180017A26
0x1800175d1  mov     [rbp+57h+var_40], rax
0x1800175d5  mov     [rax+8], r12
0x1800175d9  mov     dword ptr [rax+10h], 1
0x1800175e0  mov     rcx, [rbx]; pbstr
0x1800175e3  test    rcx, rcx
0x1800175e6  jz      loc_180017A68
0x1800175ec  call    cs:__imp_SysStringLen
0x1800175f2  mov     [rbp+57h+arg_18], eax
0x1800175f5  mov     rcx, [r14]; pbstr
0x1800175f8  test    rcx, rcx
0x1800175fb  jz      loc_180017A70
0x180017601  call    cs:__imp_SysStringLen
0x180017607  mov     ecx, eax
0x180017609  mov     eax, [rbp+57h+arg_18]
0x18001760c  mov     dword ptr [rbp+57h+var_50], ecx
0x18001760f  lea     r12d, [rcx+rax]
0x180017613  cmp     r12d, eax
0x180017616  jnb     short loc_18001762E
0x180017618  mov     ecx, 8007000Eh; int
0x18001761d  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180017623  mov     ecx, 8007000Eh; int
0x180017628  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18001762e  mov     edx, r12d
0x180017631  add     rdx, rdx; len
0x180017634  mov     eax, 0FFFFFFFFh
0x180017639  cmp     rdx, rax
0x18001763c  ja      short loc_180017618
0x18001763e  xor     ecx, ecx; psz
0x180017640  call    cs:__imp_SysAllocStringByteLen
0x180017646  mov     rcx, rax; void *
0x180017649  mov     [r15], rax
0x18001764c  test    rax, rax
0x18001764f  jz      loc_18001788E
0x180017655  mov     rdx, [rbx]; Src
0x180017658  mov     r12d, [rbp+57h+arg_18]
0x18001765c  test    rdx, rdx
0x18001765f  jz      short loc_18001766E
0x180017661  lea     r8d, [r12+1]
0x180017666  add     r8, r8; Size
0x180017669  call    memcpy_0
0x18001766e  mov     rdx, [r14]; Src
0x180017671  test    rdx, rdx
0x180017674  jz      short loc_180017690
0x180017676  mov     r8d, dword ptr [rbp+57h+var_50]
0x18001767a  inc     r8d
0x18001767d  add     r8, r8; Size
0x180017680  mov     ecx, r12d
0x180017683  mov     rax, [r15]
0x180017686  lea     rcx, [rax+rcx*2]; void *
0x18001768a  call    memcpy_0
0x18001768f  nop
0x180017690  mov     eax, edi
0x180017692  lock xadd [rbx+10h], eax
0x180017697  cmp     eax, 1
0x18001769a  jz      loc_1800178B6
0x1800176a0  mov     [rbp+57h+var_48], r15
0x1800176a4  mov     eax, edi
0x1800176a6  lock xadd [r14+10h], eax
0x1800176ac  cmp     eax, 1
0x1800176af  jz      loc_1800178EF
0x1800176b5  xor     edx, edx; dwFlags
0x1800176b7  mov     r8d, 18h; dwBytes
0x1800176bd  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x1800176c4  call    cs:__imp_HeapAlloc
0x1800176ca  mov     r14, rax
0x1800176cd  test    rax, rax
0x1800176d0  jz      loc_180017A9C
0x1800176d6  mov     [rbp+57h+var_40], rax
0x1800176da  mov     qword ptr [rax+8], 0
0x1800176e2  mov     dword ptr [rax+10h], 1
0x1800176e9  mov     rcx, rsi; psz
0x1800176ec  call    cs:__imp_SysAllocString
0x1800176f2  mov     [r14], rax
0x1800176f5  test    rax, rax
0x1800176f8  jz      loc_180017845
0x1800176fe  mov     [rbp+57h+var_40], r14
0x180017702  xor     edx, edx; dwFlags
0x180017704  mov     r8d, 18h; dwBytes
0x18001770a  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180017711  call    cs:__imp_HeapAlloc
0x180017717  mov     rbx, rax
0x18001771a  test    rax, rax
0x18001771d  jz      loc_180017AE6
0x180017723  mov     [rbp+57h+var_38], rax
0x180017727  mov     qword ptr [rax+8], 0
0x18001772f  mov     dword ptr [rax+10h], 1
0x180017736  mov     rcx, [r15]; pbstr
0x180017739  test    rcx, rcx
0x18001773c  jz      loc_180017B30
0x180017742  call    cs:__imp_SysStringLen
0x180017748  mov     esi, eax
0x18001774a  mov     rcx, [r14]; pbstr
0x18001774d  test    rcx, rcx
0x180017750  jz      loc_180017B37
0x180017756  call    cs:__imp_SysStringLen
0x18001775c  mov     [rbp+57h+arg_18], eax
0x18001775f  lea     r12d, [rax+rsi]
0x180017763  cmp     r12d, esi
0x180017766  jnb     short loc_180017773
0x180017768  mov     ecx, 8007000Eh; int
0x18001776d  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180017773  mov     edx, r12d
0x180017776  add     rdx, rdx; len
0x180017779  mov     eax, 0FFFFFFFFh
0x18001777e  cmp     rdx, rax
0x180017781  ja      short loc_180017768
0x180017783  xor     ecx, ecx; psz
0x180017785  call    cs:__imp_SysAllocStringByteLen
0x18001778b  mov     rcx, rax; void *
0x18001778e  mov     [rbx], rax
0x180017791  test    rax, rax
0x180017794  jz      loc_1800178A2
0x18001779a  mov     rdx, [r15]; Src
0x18001779d  test    rdx, rdx
0x1800177a0  jz      short loc_1800177AE
0x1800177a2  lea     r8d, [rsi+1]
0x1800177a6  add     r8, r8; Size
0x1800177a9  call    memcpy_0
0x1800177ae  mov     rdx, [r14]; Src
0x1800177b1  test    rdx, rdx
0x1800177b4  jz      short loc_1800177CF
0x1800177b6  mov     r8d, [rbp+57h+arg_18]
0x1800177ba  inc     r8d
0x1800177bd  add     r8, r8; Size
0x1800177c0  mov     ecx, esi
0x1800177c2  mov     rax, [rbx]
0x1800177c5  lea     rcx, [rax+rcx*2]; void *
0x1800177c9  call    memcpy_0
0x1800177ce  nop
0x1800177cf  mov     eax, edi
0x1800177d1  lock xadd [r15+10h], eax
0x1800177d7  cmp     eax, 1
0x1800177da  jz      loc_180017928
0x1800177e0  mov     eax, edi
0x1800177e2  lock xadd [r14+10h], eax
0x1800177e8  cmp     eax, 1
0x1800177eb  jz      loc_180017961
0x1800177f1  xor     r12d, r12d
0x1800177f4  mov     r14, [rbp+57h+arg_0]
0x1800177f8  jmp     loc_1800174B6
0x1800177fd  mov     rcx, [rbx]; bstrString
0x180017800  test    rcx, rcx
0x180017803  jz      short loc_18001780E
0x180017805  call    cs:__imp_SysFreeString
0x18001780b  mov     [rbx], r12
0x18001780e  mov     rcx, [rbx+8]; void *
0x180017812  test    rcx, rcx
0x180017815  jnz     loc_180017B5E
0x18001781b  mov     r8, rbx; lpMem
0x18001781e  xor     edx, edx; dwFlags
0x180017820  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180017827  call    cs:__imp_HeapFree
0x18001782d  jmp     loc_180017502
0x180017832  mov     rdx, r12
0x180017835  jmp     loc_1800174C2
0x18001783a  mov     ecx, 8007000Eh; int
0x18001783f  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180017845  test    rsi, rsi
0x180017848  jz      loc_1800176FE
0x18001784e  mov     ecx, 8007000Eh; int
0x180017853  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180017859  mov     rcx, [rbx]; bstrString
0x18001785c  test    rcx, rcx
0x18001785f  jz      short loc_18001786A
0x180017861  call    cs:__imp_SysFreeString
0x180017867  mov     [rbx], r12
0x18001786a  mov     rcx, [rbx+8]; void *
0x18001786e  test    rcx, rcx
0x180017871  jnz     loc_180017B6C
0x180017877  mov     r8, rbx; lpMem
0x18001787a  xor     edx, edx; dwFlags
0x18001787c  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180017883  call    cs:__imp_HeapFree
0x180017889  jmp     loc_180017550
0x18001788e  test    r12d, r12d
0x180017891  jz      loc_180017690
0x180017897  mov     ecx, 8007000Eh; int
0x18001789c  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x1800178a2  test    r12d, r12d
0x1800178a5  jz      loc_1800177CF
0x1800178ab  mov     ecx, 8007000Eh; int
0x1800178b0  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x1800178b6  mov     rcx, [rbx]; bstrString
0x1800178b9  test    rcx, rcx
  ... truncated ...
```
