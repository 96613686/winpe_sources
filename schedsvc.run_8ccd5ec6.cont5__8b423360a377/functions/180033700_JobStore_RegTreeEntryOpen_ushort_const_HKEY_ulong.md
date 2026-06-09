# JobStore::RegTreeEntryOpen(ushort const *,HKEY__ * *,ulong)

- ea: `0x180033700`
- end: `0x180033f1a`
- name: `?RegTreeEntryOpen@JobStore@@AEBAJPEBGPEAPEAUHKEY__@@K@Z`
- size: `2074`
- prototype: `int(JobStore *__hidden this, const unsigned __int16 *, HKEY *, unsigned int)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180031cf0`
- `0x180071400`
- `0x180071af8`
- `0x180071f14`

## callees

- `0x18000cc40`
- `0x180033700`
- `0x180054824`
- `0x18005a2bc`
- `0x18005a2d6`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180033773`
- `OLEAUT32!__imp_SysAllocString` at `0x1800338af`
- `OLEAUT32!__imp_SysAllocString` at `0x180033a25`
- `OLEAUT32!__imp_SysAllocString` at `0x180033773`
- `OLEAUT32!__imp_SysAllocString` at `0x1800338af`
- `OLEAUT32!__imp_SysAllocString` at `0x180033a25`
- `OLEAUT32!__imp_SysFreeString` at `0x180033b5c`
- `OLEAUT32!__imp_SysFreeString` at `0x180033bc4`
- `OLEAUT32!__imp_SysFreeString` at `0x180033c2d`
- `OLEAUT32!__imp_SysFreeString` at `0x180033c72`
- `OLEAUT32!__imp_SysFreeString` at `0x180033cb7`
- `OLEAUT32!__imp_SysFreeString` at `0x180033cfc`
- `OLEAUT32!__imp_SysFreeString` at `0x180033b5c`
- `OLEAUT32!__imp_SysFreeString` at `0x180033bc4`
- `OLEAUT32!__imp_SysFreeString` at `0x180033c2d`
- `OLEAUT32!__imp_SysFreeString` at `0x180033c72`
- `OLEAUT32!__imp_SysFreeString` at `0x180033cb7`
- `OLEAUT32!__imp_SysFreeString` at `0x180033cfc`
- `OLEAUT32!__imp_SysStringLen` at `0x18003390d`
- `OLEAUT32!__imp_SysStringLen` at `0x180033928`
- `OLEAUT32!__imp_SysStringLen` at `0x180033a87`
- `OLEAUT32!__imp_SysStringLen` at `0x180033aa1`
- `OLEAUT32!__imp_SysStringLen` at `0x18003390d`
- `OLEAUT32!__imp_SysStringLen` at `0x180033928`
- `OLEAUT32!__imp_SysStringLen` at `0x180033a87`
- `OLEAUT32!__imp_SysStringLen` at `0x180033aa1`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18003396d`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180033ad6`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18003396d`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180033ad6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800337d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800337d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003380d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033862`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003380d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033862`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033b84`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033bec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033c59`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033c9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033ce3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033d27`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033b84`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033bec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033c59`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033c9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033ce3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033d27`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033745`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033881`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800338da`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800339f7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033a50`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033745`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033881`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800338da`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800339f7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033a50`

## string_xrefs

- `0x18003376c`: `TaskCache\Tree`

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
    v48 = &qword_1800A8718;
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
        v48 = &qword_1800A8718;
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
        v48 = &qword_1800A8718;
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
        v48 = &qword_1800A8718;
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
        v48 = &qword_1800A8718;
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
0x180033700  mov     [rsp-8+arg_8], rbx
0x180033705  mov     [rsp-8+arg_18], r9d
0x18003370a  mov     [rsp-8+arg_0], rcx
0x18003370f  push    rbp
0x180033710  push    rsi
0x180033711  push    rdi
0x180033712  push    r12
0x180033714  push    r13
0x180033716  push    r14
0x180033718  push    r15
0x18003371a  lea     rbp, [rsp-27h]
0x18003371f  sub     rsp, 90h
0x180033726  mov     r13, r8
0x180033729  mov     rsi, rdx
0x18003372c  mov     r14, rcx
0x18003372f  xor     r12d, r12d
0x180033732  mov     [rbp+57h+hKey], r12
0x180033736  xor     edx, edx; dwFlags
0x180033738  mov     r8d, 18h; dwBytes
0x18003373e  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180033745  call    cs:__imp_HeapAlloc
0x18003374c  nop     dword ptr [rax+rax+00h]
0x180033751  mov     rbx, rax
0x180033754  test    rax, rax
0x180033757  jz      loc_180033D41
0x18003375d  mov     [rbp+57h+var_48], rax
0x180033761  mov     [rax+8], r12
0x180033765  mov     dword ptr [rax+10h], 1
0x18003376c  lea     rcx, psz; "TaskCache\\Tree"
0x180033773  call    cs:__imp_SysAllocString
0x18003377a  nop     dword ptr [rax+rax+00h]
0x18003377f  mov     [rbx], rax
0x180033782  test    rax, rax
0x180033785  jz      loc_180033950
0x18003378b  mov     [rbp+57h+var_48], rbx
0x18003378f  mov     edi, 0FFFFFFFFh
0x180033794  test    rsi, rsi
0x180033797  jz      short loc_1800337B2
0x180033799  movzx   eax, word ptr [rsi]
0x18003379c  cmp     ax, 5Ch ; '\'
0x1800337a0  jnz     short loc_1800337A9
0x1800337a2  add     rsi, 2
0x1800337a6  movzx   eax, word ptr [rsi]
0x1800337a9  test    ax, ax
0x1800337ac  jnz     loc_180033872
0x1800337b2  test    rbx, rbx
0x1800337b5  jz      loc_180033B95
0x1800337bb  mov     rdx, [rbx]; lpSubKey
0x1800337be  lea     rax, [rbp+57h+hKey]
0x1800337c2  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800337c7  mov     r9d, 0F003Fh; samDesired
0x1800337cd  xor     r8d, r8d; ulOptions
0x1800337d0  mov     rcx, [r14+10h]; hKey
0x1800337d4  call    cs:__imp_RegOpenKeyExW
0x1800337db  nop     dword ptr [rax+rax+00h]
0x1800337e0  mov     esi, eax
0x1800337e2  test    eax, eax
0x1800337e4  jz      short loc_180033837
0x1800337e6  jle     short loc_1800337F1
0x1800337e8  movzx   esi, ax
0x1800337eb  or      esi, 80070000h
0x1800337f1  test    rbx, rbx
0x1800337f4  jz      short loc_180033804
0x1800337f6  lock xadd [rbx+10h], edi
0x1800337fb  cmp     edi, 1
0x1800337fe  jz      loc_180033B54
0x180033804  mov     rcx, [rbp+57h+hKey]; hKey
0x180033808  test    rcx, rcx
0x18003380b  jz      short loc_180033819
0x18003380d  call    cs:__imp_RegCloseKey
0x180033814  nop     dword ptr [rax+rax+00h]
0x180033819  mov     eax, esi
0x18003381b  mov     rbx, [rsp+0C0h+arg_8]
0x180033823  add     rsp, 90h
0x18003382a  pop     r15
0x18003382c  pop     r14
0x18003382e  pop     r13
0x180033830  pop     r12
0x180033832  pop     rdi
0x180033833  pop     rsi
0x180033834  pop     rbp
0x180033835  retn
0x180033837  mov     rax, [rbp+57h+hKey]
0x18003383b  mov     rcx, r12
0x18003383e  mov     [rbp+57h+hKey], rcx
0x180033842  mov     [r13+0], rax
0x180033846  test    rbx, rbx
0x180033849  jz      short loc_18003385D
0x18003384b  lock xadd [rbx+10h], edi
0x180033850  cmp     edi, 1
0x180033853  jz      loc_180033BBC
0x180033859  mov     rcx, [rbp+57h+hKey]; hKey
0x18003385d  test    rcx, rcx
0x180033860  jz      short loc_18003386E
0x180033862  call    cs:__imp_RegCloseKey
0x180033869  nop     dword ptr [rax+rax+00h]
0x18003386e  xor     eax, eax
0x180033870  jmp     short loc_18003381B
0x180033872  xor     edx, edx; dwFlags
0x180033874  mov     r8d, 18h; dwBytes
0x18003387a  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180033881  call    cs:__imp_HeapAlloc
0x180033888  nop     dword ptr [rax+rax+00h]
0x18003388d  mov     r14, rax
0x180033890  test    rax, rax
0x180033893  jz      loc_180033D83
0x180033899  mov     [rbp+57h+var_50], rax
0x18003389d  mov     [rax+8], r12
0x1800338a1  mov     dword ptr [rax+10h], 1
0x1800338a8  lea     rcx, asc_1800A7EC0; "\\"
0x1800338af  call    cs:__imp_SysAllocString
0x1800338b6  nop     dword ptr [rax+rax+00h]
0x1800338bb  mov     [r14], rax
0x1800338be  test    rax, rax
0x1800338c1  jz      loc_180033B9D
0x1800338c7  mov     [rbp+57h+var_38], r14
0x1800338cb  xor     edx, edx; dwFlags
0x1800338cd  mov     r8d, 18h; dwBytes
0x1800338d3  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x1800338da  call    cs:__imp_HeapAlloc
0x1800338e1  nop     dword ptr [rax+rax+00h]
0x1800338e6  mov     r15, rax
0x1800338e9  test    rax, rax
0x1800338ec  jz      loc_180033DC5
0x1800338f2  mov     [rbp+57h+var_40], rax
0x1800338f6  mov     [rax+8], r12
0x1800338fa  mov     dword ptr [rax+10h], 1
0x180033901  mov     rcx, [rbx]; pbstr
0x180033904  test    rcx, rcx
0x180033907  jz      loc_180033E07
0x18003390d  call    cs:__imp_SysStringLen
0x180033914  nop     dword ptr [rax+rax+00h]
0x180033919  mov     [rbp+57h+arg_18], eax
0x18003391c  mov     rcx, [r14]; pbstr
0x18003391f  test    rcx, rcx
0x180033922  jz      loc_180033E0F
0x180033928  call    cs:__imp_SysStringLen
0x18003392f  nop     dword ptr [rax+rax+00h]
0x180033934  mov     ecx, eax
0x180033936  mov     eax, [rbp+57h+arg_18]
0x180033939  mov     dword ptr [rbp+57h+var_50], ecx
0x18003393c  lea     r12d, [rcx+rax]
0x180033940  cmp     r12d, eax
0x180033943  jnb     short loc_18003395B
0x180033945  mov     ecx, 8007000Eh; int
0x18003394a  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180033950  mov     ecx, 8007000Eh; int
0x180033955  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18003395b  mov     edx, r12d
0x18003395e  add     rdx, rdx; len
0x180033961  mov     eax, 0FFFFFFFFh
0x180033966  cmp     rdx, rax
0x180033969  ja      short loc_180033945
0x18003396b  xor     ecx, ecx; psz
0x18003396d  call    cs:__imp_SysAllocStringByteLen
0x180033974  nop     dword ptr [rax+rax+00h]
0x180033979  mov     rcx, rax; void *
0x18003397c  mov     [r15], rax
0x18003397f  test    rax, rax
0x180033982  jz      loc_180033BFD
0x180033988  mov     rdx, [rbx]; Src
0x18003398b  mov     r12d, [rbp+57h+arg_18]
0x18003398f  test    rdx, rdx
0x180033992  jz      short loc_1800339A1
0x180033994  lea     r8d, [r12+1]
0x180033999  add     r8, r8; Size
0x18003399c  call    memcpy_0
0x1800339a1  mov     rdx, [r14]; Src
0x1800339a4  test    rdx, rdx
0x1800339a7  jz      short loc_1800339C3
0x1800339a9  mov     r8d, dword ptr [rbp+57h+var_50]
0x1800339ad  inc     r8d
0x1800339b0  add     r8, r8; Size
0x1800339b3  mov     ecx, r12d
0x1800339b6  mov     rax, [r15]
0x1800339b9  lea     rcx, [rax+rcx*2]; void *
0x1800339bd  call    memcpy_0
0x1800339c2  nop
0x1800339c3  mov     eax, edi
0x1800339c5  lock xadd [rbx+10h], eax
0x1800339ca  cmp     eax, 1
0x1800339cd  jz      loc_180033C25
0x1800339d3  mov     [rbp+57h+var_48], r15
0x1800339d7  mov     eax, edi
0x1800339d9  lock xadd [r14+10h], eax
0x1800339df  cmp     eax, 1
0x1800339e2  jz      loc_180033C6A
0x1800339e8  xor     edx, edx; dwFlags
0x1800339ea  mov     r8d, 18h; dwBytes
0x1800339f0  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x1800339f7  call    cs:__imp_HeapAlloc
0x1800339fe  nop     dword ptr [rax+rax+00h]
0x180033a03  mov     r14, rax
0x180033a06  test    rax, rax
0x180033a09  jz      loc_180033E3B
0x180033a0f  mov     [rbp+57h+var_40], rax
0x180033a13  mov     qword ptr [rax+8], 0
0x180033a1b  mov     dword ptr [rax+10h], 1
0x180033a22  mov     rcx, rsi; psz
0x180033a25  call    cs:__imp_SysAllocString
0x180033a2c  nop     dword ptr [rax+rax+00h]
0x180033a31  mov     [r14], rax
0x180033a34  test    rax, rax
0x180033a37  jz      loc_180033BA8
0x180033a3d  mov     [rbp+57h+var_40], r14
0x180033a41  xor     edx, edx; dwFlags
0x180033a43  mov     r8d, 18h; dwBytes
0x180033a49  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180033a50  call    cs:__imp_HeapAlloc
0x180033a57  nop     dword ptr [rax+rax+00h]
0x180033a5c  mov     rbx, rax
0x180033a5f  test    rax, rax
0x180033a62  jz      loc_180033E85
0x180033a68  mov     [rbp+57h+var_38], rax
0x180033a6c  mov     qword ptr [rax+8], 0
0x180033a74  mov     dword ptr [rax+10h], 1
0x180033a7b  mov     rcx, [r15]; pbstr
0x180033a7e  test    rcx, rcx
0x180033a81  jz      loc_180033ECF
0x180033a87  call    cs:__imp_SysStringLen
0x180033a8e  nop     dword ptr [rax+rax+00h]
0x180033a93  mov     esi, eax
0x180033a95  mov     rcx, [r14]; pbstr
0x180033a98  test    rcx, rcx
0x180033a9b  jz      loc_180033ED6
0x180033aa1  call    cs:__imp_SysStringLen
0x180033aa8  nop     dword ptr [rax+rax+00h]
0x180033aad  mov     [rbp+57h+arg_18], eax
0x180033ab0  lea     r12d, [rax+rsi]
0x180033ab4  cmp     r12d, esi
0x180033ab7  jnb     short loc_180033AC4
0x180033ab9  mov     ecx, 8007000Eh; int
0x180033abe  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180033ac4  mov     edx, r12d
0x180033ac7  add     rdx, rdx; len
0x180033aca  mov     eax, 0FFFFFFFFh
0x180033acf  cmp     rdx, rax
0x180033ad2  ja      short loc_180033AB9
0x180033ad4  xor     ecx, ecx; psz
0x180033ad6  call    cs:__imp_SysAllocStringByteLen
0x180033add  nop     dword ptr [rax+rax+00h]
0x180033ae2  mov     rcx, rax; void *
0x180033ae5  mov     [rbx], rax
0x180033ae8  test    rax, rax
0x180033aeb  jz      loc_180033C11
0x180033af1  mov     rdx, [r15]; Src
0x180033af4  test    rdx, rdx
0x180033af7  jz      short loc_180033B05
0x180033af9  lea     r8d, [rsi+1]
0x180033afd  add     r8, r8; Size
0x180033b00  call    memcpy_0
0x180033b05  mov     rdx, [r14]; Src
0x180033b08  test    rdx, rdx
0x180033b0b  jz      short loc_180033B26
0x180033b0d  mov     r8d, [rbp+57h+arg_18]
0x180033b11  inc     r8d
0x180033b14  add     r8, r8; Size
0x180033b17  mov     ecx, esi
0x180033b19  mov     rax, [rbx]
0x180033b1c  lea     rcx, [rax+rcx*2]; void *
0x180033b20  call    memcpy_0
0x180033b25  nop
0x180033b26  mov     eax, edi
0x180033b28  lock xadd [r15+10h], eax
0x180033b2e  cmp     eax, 1
0x180033b31  jz      loc_180033CAF
0x180033b37  mov     eax, edi
0x180033b39  lock xadd [r14+10h], eax
0x180033b3f  cmp     eax, 1
0x180033b42  jz      loc_180033CF4
0x180033b48  xor     r12d, r12d
0x180033b4b  mov     r14, [rbp+57h+arg_0]
0x180033b4f  jmp     loc_1800337B2
0x180033b54  mov     rcx, [rbx]; bstrString
0x180033b57  test    rcx, rcx
0x180033b5a  jz      short loc_180033B6B
0x180033b5c  call    cs:__imp_SysFreeString
0x180033b63  nop     dword ptr [rax+rax+00h]
0x180033b68  mov     [rbx], r12
0x180033b6b  mov     rcx, [rbx+8]; void *
0x180033b6f  test    rcx, rcx
0x180033b72  jnz     loc_180033EFD
0x180033b78  mov     r8, rbx; lpMem
0x180033b7b  xor     edx, edx; dwFlags
0x180033b7d  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180033b84  call    cs:__imp_HeapFree
0x180033b8b  nop     dword ptr [rax+rax+00h]
0x180033b90  jmp     loc_180033804
0x180033b95  mov     rdx, r12
0x180033b98  jmp     loc_1800337BE
0x180033b9d  mov     ecx, 8007000Eh; int
0x180033ba2  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180033ba8  test    rsi, rsi
0x180033bab  jz      loc_180033A3D
0x180033bb1  mov     ecx, 8007000Eh; int
0x180033bb6  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180033bbc  mov     rcx, [rbx]; bstrString
0x180033bbf  test    rcx, rcx
0x180033bc2  jz      short loc_180033BD3
0x180033bc4  call    cs:__imp_SysFreeString
  ... truncated ...
```
