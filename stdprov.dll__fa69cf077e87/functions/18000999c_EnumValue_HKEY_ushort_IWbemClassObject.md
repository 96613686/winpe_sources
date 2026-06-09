# EnumValue(HKEY__ *,ushort *,IWbemClassObject *)

- ea: `0x18000999c`
- end: `0x180009c64`
- name: `?EnumValue@@YAJPEAUHKEY__@@PEAGPEAUIWbemClassObject@@@Z`
- size: `712`
- prototype: `LSTATUS __fastcall(HKEY, unsigned __int16 *, struct IWbemClassObject *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800043c0`

## callees

- `0x180004390`
- `0x18000999c`
- `0x180009c6c`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800099ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800099ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009a44`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009a44`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180009b39`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180009b39`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180009c3e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180009c3e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180009a73`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180009a73`
- `OLEAUT32!__imp_SysAllocString` at `0x180009b4e`
- `OLEAUT32!__imp_SysAllocString` at `0x180009b4e`
- `OLEAUT32!__imp_SysFreeString` at `0x180009b85`
- `OLEAUT32!__imp_SysFreeString` at `0x180009b85`
- `OLEAUT32!__imp_VariantClear` at `0x180009bf8`
- `OLEAUT32!__imp_VariantClear` at `0x180009c34`
- `OLEAUT32!__imp_VariantClear` at `0x180009bf8`
- `OLEAUT32!__imp_VariantClear` at `0x180009c34`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180009ab2`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180009ae1`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180009ab2`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180009ae1`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180009af2`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180009b9a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180009af2`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180009b9a`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180009b66`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180009b79`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180009b66`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180009b79`

## pseudocode

```c
LSTATUS __fastcall EnumValue(HKEY a1, unsigned __int16 *a2, struct IWbemClassObject *a3)
{
  LSTATUS result; // eax
  LSTATUS v5; // ebx
  OLECHAR *v6; // rax
  OLECHAR *v7; // rdi
  SAFEARRAY *v8; // rsi
  SAFEARRAY *v9; // r14
  SAFEARRAY *v10; // rcx
  int v11; // ecx
  DWORD i; // eax
  BSTR v13; // rax
  OLECHAR *v14; // r15
  HRESULT v15; // ebx
  HRESULT v16; // r12d
  DWORD cValues; // [rsp+60h] [rbp-49h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+64h] [rbp-45h] BYREF
  HKEY v19; // [rsp+68h] [rbp-41h] BYREF
  DWORD cchValueName; // [rsp+70h] [rbp-39h] BYREF
  DWORD Type; // [rsp+74h] [rbp-35h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-31h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+80h] [rbp-29h] BYREF
  DWORD cSubKeys; // [rsp+84h] [rbp-25h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-21h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+A0h] [rbp-9h] BYREF
  SAFEARRAYBOUND v27; // [rsp+A8h] [rbp-1h] BYREF
  void *v28[10]; // [rsp+B0h] [rbp+7h] BYREF
  LONG rgIndices; // [rsp+128h] [rbp+7Fh] BYREF

  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  Type = 0;
  cchValueName = 0;
  hKey = 0;
  result = RegOpenKeyExW(a1, a2, 0, 1u, &hKey);
  if ( !result )
  {
    v19 = hKey;
    v5 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
    if ( !v5 && cbMaxValueNameLen )
    {
      v6 = (OLECHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(cbMaxValueNameLen + 1, (unsigned int)(v5 + 2)));
      v7 = v6;
      if ( !v6 )
      {
LABEL_5:
        CRegCloseMe::~CRegCloseMe((CRegCloseMe *)&v19);
        return -2147217402;
      }
      v28[0] = v6;
      v28[1] = 0;
      rgsabound.lLbound = 0;
      rgsabound.cElements = cValues;
      v8 = SafeArrayCreate(8u, 1u, &rgsabound);
      if ( !v8 )
      {
LABEL_7:
        CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v28);
        goto LABEL_5;
      }
      v27.lLbound = 0;
      v27.cElements = cValues;
      v9 = SafeArrayCreate(3u, 1u, &v27);
      if ( !v9 )
      {
        v10 = v8;
LABEL_10:
        SafeArrayDestroy(v10);
        goto LABEL_7;
      }
      v11 = 0;
      for ( i = 0; ; i = rgIndices + 1 )
      {
        rgIndices = v11;
        if ( i >= cValues )
          break;
        cchValueName = cbMaxValueNameLen + 1;
        if ( !RegEnumValueW(hKey, v11, v7, &cchValueName, 0, &Type, 0, 0) )
        {
          v7[cbMaxValueNameLen] = 0;
          v13 = SysAllocString(v7);
          v14 = v13;
          if ( v13 )
          {
            v15 = SafeArrayPutElement(v8, &rgIndices, v13);
            v16 = SafeArrayPutElement(v9, &rgIndices, &Type);
            SysFreeString(v14);
            if ( v15 < 0 || v16 < 0 )
            {
              SafeArrayDestroy(v8);
              v10 = v9;
              goto LABEL_10;
            }
          }
        }
        v11 = rgIndices + 1;
      }
      *(_QWORD *)&pvarg.vt = 8200;
      *(_OWORD *)&pvarg.decVal.Lo32 = (unsigned __int64)v8;
      ((void (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))a3->lpVtbl->Put)(
        a3,
        L"sNames",
        0,
        &pvarg,
        0);
      VariantClear(&pvarg);
      pvarg.vt = 8195;
      pvarg.llVal = (LONGLONG)v9;
      v5 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))a3->lpVtbl->Put)(
             a3,
             L"Types",
             0,
             &pvarg,
             0);
      VariantClear(&pvarg);
      CWin32DefaultArena::WbemMemFree(v7);
    }
    CRegCloseMe::~CRegCloseMe((CRegCloseMe *)&v19);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18000999c  push    rbp
0x18000999e  push    rbx
0x18000999f  push    rsi
0x1800099a0  push    rdi
0x1800099a1  push    r12
0x1800099a3  push    r13
0x1800099a5  push    r14
0x1800099a7  push    r15
0x1800099a9  lea     rbp, [rsp-1Fh]
0x1800099ae  sub     rsp, 0C8h
0x1800099b5  mov     r13, r8
0x1800099b8  xor     r15d, r15d
0x1800099bb  mov     [rbp+57h+cSubKeys], r15d
0x1800099bf  mov     [rbp+57h+cbMaxSubKeyLen], r15d
0x1800099c3  mov     [rbp+57h+cValues], r15d
0x1800099c7  mov     [rbp+57h+cbMaxValueNameLen], r15d
0x1800099cb  mov     [rbp+57h+Type], r15d
0x1800099cf  mov     [rbp+57h+cchValueName], r15d
0x1800099d3  mov     [rbp+57h+hKey], r15
0x1800099d7  lea     rax, [rbp+57h+hKey]
0x1800099db  mov     [rsp+100h+phkResult], rax; phkResult
0x1800099e0  lea     r14d, [r15+1]
0x1800099e4  mov     r9d, r14d; samDesired
0x1800099e7  xor     r8d, r8d; ulOptions
0x1800099ea  call    cs:__imp_RegOpenKeyExW
0x1800099f0  test    eax, eax
0x1800099f2  jnz     loc_180009C50
0x1800099f8  mov     rax, [rbp+57h+hKey]
0x1800099fc  mov     [rbp+57h+var_98], rax
0x180009a00  mov     [rsp+100h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180009a05  mov     [rsp+100h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180009a0a  mov     [rsp+100h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180009a0f  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x180009a13  mov     [rsp+100h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180009a18  lea     rax, [rbp+57h+cValues]
0x180009a1c  mov     [rsp+100h+lpcValues], rax; lpcValues
0x180009a21  mov     [rsp+100h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180009a26  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x180009a2a  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180009a2f  lea     rax, [rbp+57h+cSubKeys]
0x180009a33  mov     [rsp+100h+phkResult], rax; lpcSubKeys
0x180009a38  xor     r9d, r9d; lpReserved
0x180009a3b  xor     r8d, r8d; lpcchClass
0x180009a3e  xor     edx, edx; lpClass
0x180009a40  mov     rcx, [rbp+57h+hKey]; hKey
0x180009a44  call    cs:__imp_RegQueryInfoKeyW
0x180009a4a  mov     ebx, eax
0x180009a4c  test    eax, eax
0x180009a4e  jnz     loc_180009C45
0x180009a54  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x180009a57  test    eax, eax
0x180009a59  jz      loc_180009C45
0x180009a5f  lea     ecx, [rax+1]
0x180009a62  lea     eax, [rbx+2]
0x180009a65  mul     rcx
0x180009a68  lea     rcx, [r15-1]
0x180009a6c  cmovb   rax, rcx
0x180009a70  mov     rcx, rax
0x180009a73  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180009a79  mov     rdi, rax
0x180009a7c  test    rax, rax
0x180009a7f  jnz     short loc_180009A94
0x180009a81  lea     rcx, [rbp+57h+var_98]; this
0x180009a85  call    ??1CRegCloseMe@@QEAA@XZ; CRegCloseMe::~CRegCloseMe(void)
0x180009a8a  mov     eax, 80041006h
0x180009a8f  jmp     loc_180009C50
0x180009a94  mov     [rbp+57h+var_50], rdi
0x180009a98  mov     [rbp+57h+var_48], r15
0x180009a9c  mov     [rbp+57h+rgsabound.lLbound], r15d
0x180009aa0  mov     eax, [rbp+57h+cValues]
0x180009aa3  mov     [rbp+57h+rgsabound.cElements], eax
0x180009aa6  mov     ecx, 8; vt
0x180009aab  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x180009aaf  mov     edx, r14d; cDims
0x180009ab2  call    cs:__imp_SafeArrayCreate
0x180009ab8  mov     rsi, rax
0x180009abb  test    rax, rax
0x180009abe  jnz     short loc_180009ACB
0x180009ac0  lea     rcx, [rbp+57h+var_50]
0x180009ac4  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x180009ac9  jmp     short loc_180009A81
0x180009acb  mov     [rbp+57h+var_58.lLbound], r15d
0x180009acf  mov     eax, [rbp+57h+cValues]
0x180009ad2  mov     [rbp+57h+var_58.cElements], eax
0x180009ad5  mov     ecx, 3; vt
0x180009ada  lea     r8, [rbp+57h+var_58]; rgsabound
0x180009ade  mov     edx, r14d; cDims
0x180009ae1  call    cs:__imp_SafeArrayCreate
0x180009ae7  mov     r14, rax
0x180009aea  test    rax, rax
0x180009aed  jnz     short loc_180009AFA
0x180009aef  mov     rcx, rsi; psa
0x180009af2  call    cs:__imp_SafeArrayDestroy
0x180009af8  jmp     short loc_180009AC0
0x180009afa  mov     ecx, r15d
0x180009afd  mov     eax, r15d
0x180009b00  mov     [rbp+57h+rgIndices], ecx
0x180009b03  cmp     eax, [rbp+57h+cValues]
0x180009b06  jnb     loc_180009BB7
0x180009b0c  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x180009b0f  inc     eax
0x180009b11  mov     [rbp+57h+cchValueName], eax
0x180009b14  mov     [rsp+100h+lpcValues], r15; lpcbData
0x180009b19  mov     [rsp+100h+lpcbMaxClassLen], r15; lpData
0x180009b1e  lea     rax, [rbp+57h+Type]
0x180009b22  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpType
0x180009b27  mov     [rsp+100h+phkResult], r15; lpReserved
0x180009b2c  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x180009b30  mov     r8, rdi; lpValueName
0x180009b33  mov     edx, ecx; dwIndex
0x180009b35  mov     rcx, [rbp+57h+hKey]; hKey
0x180009b39  call    cs:__imp_RegEnumValueW
0x180009b3f  test    eax, eax
0x180009b41  jnz     short loc_180009BAB
0x180009b43  mov     ecx, [rbp+57h+cbMaxValueNameLen]
0x180009b46  mov     [rdi+rcx*2], r15w
0x180009b4b  mov     rcx, rdi; psz
0x180009b4e  call    cs:__imp_SysAllocString
0x180009b54  mov     r15, rax
0x180009b57  test    rax, rax
0x180009b5a  jz      short loc_180009BA8
0x180009b5c  mov     r8, rax; pv
0x180009b5f  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x180009b63  mov     rcx, rsi; psa
0x180009b66  call    cs:__imp_SafeArrayPutElement
0x180009b6c  mov     ebx, eax
0x180009b6e  lea     r8, [rbp+57h+Type]; pv
0x180009b72  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x180009b76  mov     rcx, r14; psa
0x180009b79  call    cs:__imp_SafeArrayPutElement
0x180009b7f  mov     r12d, eax
0x180009b82  mov     rcx, r15; bstrString
0x180009b85  call    cs:__imp_SysFreeString
0x180009b8b  xor     r15d, r15d
0x180009b8e  test    ebx, ebx
0x180009b90  js      short loc_180009B97
0x180009b92  test    r12d, r12d
0x180009b95  jns     short loc_180009BAB
0x180009b97  mov     rcx, rsi; psa
0x180009b9a  call    cs:__imp_SafeArrayDestroy
0x180009ba0  mov     rcx, r14
0x180009ba3  jmp     loc_180009AF2
0x180009ba8  xor     r15d, r15d
0x180009bab  mov     ecx, [rbp+57h+rgIndices]
0x180009bae  inc     ecx
0x180009bb0  mov     eax, ecx
0x180009bb2  jmp     loc_180009B00
0x180009bb7  xorps   xmm0, xmm0
0x180009bba  xor     eax, eax
0x180009bbc  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180009bc0  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180009bc4  mov     eax, 2008h
0x180009bc9  mov     word ptr [rbp+57h+pvarg], ax
0x180009bcd  mov     qword ptr [rbp+57h+pvarg+8], rsi
0x180009bd1  mov     rax, [r13+0]
0x180009bd5  mov     dword ptr [rsp+100h+phkResult], r15d
0x180009bda  lea     r9, [rbp+57h+pvarg]
0x180009bde  xor     r8d, r8d
0x180009be1  lea     rdx, aSnames; "sNames"
0x180009be8  mov     rcx, r13
0x180009beb  mov     rax, [rax+28h]
0x180009bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bf4  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180009bf8  call    cs:__imp_VariantClear
0x180009bfe  mov     eax, 2003h
0x180009c03  mov     word ptr [rbp+57h+pvarg], ax
0x180009c07  mov     qword ptr [rbp+57h+pvarg+8], r14
0x180009c0b  mov     rax, [r13+0]
0x180009c0f  mov     dword ptr [rsp+100h+phkResult], r15d
0x180009c14  lea     r9, [rbp+57h+pvarg]
0x180009c18  xor     r8d, r8d
0x180009c1b  lea     rdx, aTypes; "Types"
0x180009c22  mov     rcx, r13
0x180009c25  mov     rax, [rax+28h]
0x180009c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c2e  mov     ebx, eax
0x180009c30  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180009c34  call    cs:__imp_VariantClear
0x180009c3a  nop
0x180009c3b  mov     rcx, rdi
0x180009c3e  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180009c44  nop
0x180009c45  lea     rcx, [rbp+57h+var_98]; this
0x180009c49  call    ??1CRegCloseMe@@QEAA@XZ; CRegCloseMe::~CRegCloseMe(void)
0x180009c4e  mov     eax, ebx
0x180009c50  add     rsp, 0C8h
0x180009c57  pop     r15
0x180009c59  pop     r14
0x180009c5b  pop     r13
0x180009c5d  pop     r12
0x180009c5f  pop     rdi
0x180009c60  pop     rsi
0x180009c61  pop     rbx
0x180009c62  pop     rbp
0x180009c63  retn
```
