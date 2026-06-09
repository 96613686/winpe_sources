# CFilterDescriptionCache::_GetIFilter(_GUID const &,ushort * *)

- ea: `0x18000eebc`
- end: `0x18000f43b`
- name: `?_GetIFilter@CFilterDescriptionCache@@AEAAJAEBU_GUID@@PEAPEAG@Z`
- size: `1407`
- prototype: `__int64 __fastcall(CFilterDescriptionCache *this, const struct _GUID *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000e090`

## callees

- `0x180005cc0`
- `0x18000eaac`
- `0x18000ed54`
- `0x18000ee50`
- `0x18000ee80`
- `0x18000eebc`
- `0x18001a828`
- `0x18001cb38`
- `0x18001d210`
- `0x18001f014`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ef7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f116`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f2a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ef7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f116`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f2a5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000ef62`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000ef62`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f0b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f0b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f0e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f0e3`

## string_xrefs

- `0x18000ef39`: `CLSID\`
- `0x18000efb8`: `CLSID\`
- `0x18000f159`: `CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFilterDescriptionCache::_GetIFilter(
        CFilterDescriptionCache *this,
        const struct _GUID *a2,
        unsigned __int16 **a3)
{
  unsigned __int64 v5; // r12
  int RegUIString; // edi
  __int64 v7; // rbx
  WCHAR *v8; // rbx
  unsigned __int16 *v9; // r14
  WCHAR *v10; // rsi
  __int64 v11; // rbx
  unsigned __int64 v12; // r15
  __int64 v13; // rbx
  const unsigned __int16 *v14; // rdx
  unsigned int v15; // r9d
  WCHAR *v16; // rsi
  __int64 v17; // rbx
  __int64 v18; // rbx
  __int64 v19; // rbx
  unsigned __int64 v21; // rsi
  __int64 v22; // rbx
  int v23; // eax
  LPCWSTR v24; // rsi
  __int64 v25; // rbx
  int RegDwordOrString; // eax
  LPCWSTR lpSubKey; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v28; // [rsp+38h] [rbp-C8h]
  __int64 v29; // [rsp+40h] [rbp-C0h]
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v32[264]; // [rsp+A0h] [rbp-60h] BYREF

  lpSubKey = 0;
  v28 = 0;
  v29 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&lpSubKey);
  v5 = -1;
  RegUIString = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                  (__int64)&lpSubKey,
                  v28 + 6);
  if ( RegUIString < 0 )
    goto LABEL_4;
  v7 = v28;
  StringCchCopyNW((unsigned __int16 *)&lpSubKey[v28], 7u, L"CLSID\\", 6u);
  v28 = v7 + 6;
  if ( !StringFromGUID2(a2, sz, 39) )
  {
    RegUIString = -2147024883;
LABEL_4:
    v8 = 0;
    v9 = 0;
    goto LABEL_5;
  }
  v21 = -1;
  do
    ++v21;
  while ( sz[v21] );
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&lpSubKey);
  RegUIString = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                  (__int64)&lpSubKey,
                  v21 + v28);
  if ( RegUIString < 0 )
    goto LABEL_4;
  v22 = v28;
  StringCchCopyNW((unsigned __int16 *)&lpSubKey[v28], v21 + 1, sz, v21);
  v28 = v21 + v22;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&lpSubKey);
  v23 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
          (__int64)&lpSubKey,
          v28 + 66);
  v24 = lpSubKey;
  RegUIString = v23;
  if ( v23 >= 0 )
  {
    v25 = v28;
    StringCchCopyNW(
      (unsigned __int16 *)&lpSubKey[v28],
      0x43u,
      L"\\PersistentAddinsRegistered\\{89BCB740-6119-101A-BCB7-00DD010655AF}",
      0x42u);
    v28 = v25 + 66;
  }
  v8 = 0;
  if ( RegUIString >= 0 )
  {
    RegUIString = 0;
    if ( v24 )
    {
LABEL_45:
      v8 = (WCHAR *)v24;
      lpSubKey = 0;
      v29 = 0;
      v28 = 0;
      goto LABEL_46;
    }
    RegUIString = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                    (__int64)&lpSubKey,
                    0);
    if ( RegUIString >= 0 )
    {
      v24 = lpSubKey;
      StringCchCopyNW((unsigned __int16 *)lpSubKey, 1u, &strIn, 0);
      goto LABEL_45;
    }
  }
LABEL_46:
  hKey = 0;
  v9 = 0;
  if ( RegUIString >= 0 )
  {
    RegDwordOrString = GetRegDwordOrString(HKEY_CLASSES_ROOT, v8, 0, 1, 0, (unsigned __int16 **)&hKey);
    v9 = (unsigned __int16 *)hKey;
    RegUIString = RegDwordOrString;
    if ( RegDwordOrString == 1 )
      RegUIString = -2147024894;
  }
LABEL_5:
  CoTaskMemFree(v8);
  if ( RegUIString >= 0 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&lpSubKey);
    RegUIString = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                    (__int64)&lpSubKey,
                    v28 + 6);
    if ( RegUIString >= 0 )
    {
      v10 = (WCHAR *)lpSubKey;
      v11 = v28;
      StringCchCopyNW((unsigned __int16 *)&lpSubKey[v28], 7u, L"CLSID\\", 6u);
      v28 = v11 + 6;
      if ( v9 )
      {
        v12 = -1;
        do
          ++v12;
        while ( v9[v12] );
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&lpSubKey);
        RegUIString = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                        (__int64)&lpSubKey,
                        v12 + v28);
        if ( RegUIString < 0 )
          goto LABEL_35;
        v10 = (WCHAR *)lpSubKey;
        v13 = v28;
        StringCchCopyNW((unsigned __int16 *)&lpSubKey[v28], v12 + 1, v9, v12);
        v28 = v12 + v13;
      }
      RegUIString = 0;
      if ( !v10 )
      {
        RegUIString = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                        (__int64)&lpSubKey,
                        0);
        if ( RegUIString < 0 )
          goto LABEL_35;
        v10 = (WCHAR *)lpSubKey;
        StringCchCopyNW((unsigned __int16 *)lpSubKey, 1u, &strIn, 0);
      }
      lpSubKey = 0;
      v29 = 0;
      v28 = 0;
      *a3 = 0;
      hKey = 0;
      if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, v10, 0, 0x20019u, &hKey) )
      {
        RegUIString = LoadRegUIString(hKey, v14, v32, v15);
        if ( RegUIString >= 0 )
          RegUIString = StrDupUsingNew(v32, a3);
        RegCloseKey(hKey);
        if ( RegUIString < 0 )
          goto LABEL_20;
      }
      if ( !*a3 )
LABEL_20:
        RegUIString = GetRegDwordOrString(HKEY_CLASSES_ROOT, v10, 0, 1, 0, a3);
      CoTaskMemFree(v10);
      if ( RegUIString )
      {
        v16 = 0;
        if ( RegUIString >= 0 )
        {
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&lpSubKey);
          RegUIString = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                          (__int64)&lpSubKey,
                          v28 + 6);
          if ( RegUIString >= 0 )
          {
            v17 = v28;
            StringCchCopyNW((unsigned __int16 *)&lpSubKey[v28], 7u, L"CLSID\\", 6u);
            v28 = v17 + 6;
            if ( v9 )
            {
              do
                ++v5;
              while ( v9[v5] );
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&lpSubKey);
              RegUIString = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                              (__int64)&lpSubKey,
                              v5 + v28);
              if ( RegUIString < 0 )
                goto LABEL_34;
              v18 = v28;
              StringCchCopyNW((unsigned __int16 *)&lpSubKey[v28], v5 + 1, v9, v5);
              v28 = v5 + v18;
            }
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&lpSubKey);
            RegUIString = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                            (__int64)&lpSubKey,
                            v28 + 15);
            if ( RegUIString >= 0 )
            {
              v16 = (WCHAR *)lpSubKey;
              v19 = v28;
              StringCchCopyNW((unsigned __int16 *)&lpSubKey[v28], 0x10u, L"\\InprocServer32", 0xFu);
              v28 = v19 + 15;
              if ( v16 )
                goto LABEL_32;
              RegUIString = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                              (__int64)&lpSubKey,
                              0);
              if ( RegUIString >= 0 )
              {
                v16 = (WCHAR *)lpSubKey;
                StringCchCopyNW((unsigned __int16 *)lpSubKey, 1u, &strIn, 0);
LABEL_32:
                lpSubKey = 0;
                v29 = 0;
                v28 = 0;
                RegUIString = GetRegDwordOrString(HKEY_CLASSES_ROOT, v16, 0, 1, 0, a3);
                if ( RegUIString == 1 )
                  RegUIString = -2147024894;
                goto LABEL_34;
              }
              v16 = 0;
            }
          }
        }
LABEL_34:
        CoTaskMemFree(v16);
      }
    }
  }
LABEL_35:
  operator delete(v9);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&lpSubKey);
  return (unsigned int)RegUIString;
}

```

## disassembly

```asm
0x18000eebc  mov     [rsp-8+arg_0], rbx
0x18000eec1  push    rbp
0x18000eec2  push    rsi
0x18000eec3  push    rdi
0x18000eec4  push    r12
0x18000eec6  push    r13
0x18000eec8  push    r14
0x18000eeca  push    r15
0x18000eecc  lea     rbp, [rsp-1C0h]
0x18000eed4  sub     rsp, 2C0h
0x18000eedb  mov     rax, cs:__security_cookie
0x18000eee2  xor     rax, rsp
0x18000eee5  mov     [rbp+1F0h+var_40], rax
0x18000eeec  xor     r15d, r15d
0x18000eeef  lea     rcx, [rsp+2F0h+lpSubKey]
0x18000eef4  mov     [rsp+2F0h+lpSubKey], r15
0x18000eef9  mov     r13, r8
0x18000eefc  mov     [rsp+2F0h+var_2B8], r15
0x18000ef01  mov     rsi, rdx
0x18000ef04  mov     [rsp+2F0h+var_2B0], r15
0x18000ef09  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18000ef0e  mov     rdx, [rsp+2F0h+var_2B8]
0x18000ef13  lea     rcx, [rsp+2F0h+lpSubKey]
0x18000ef18  add     rdx, 6
0x18000ef1c  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x18000ef21  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000ef25  mov     edi, eax
0x18000ef27  test    eax, eax
0x18000ef29  js      short loc_18000EF75
0x18000ef2b  mov     rax, [rsp+2F0h+lpSubKey]
0x18000ef30  lea     r9d, [r15+6]; unsigned __int64
0x18000ef34  mov     rbx, [rsp+2F0h+var_2B8]
0x18000ef39  lea     r8, aClsid; "CLSID\\"
0x18000ef40  lea     edx, [r15+7]; unsigned __int64
0x18000ef44  lea     rcx, [rax+rbx*2]; unsigned __int16 *
0x18000ef48  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000ef4d  add     rbx, 6
0x18000ef51  lea     r8d, [r15+27h]; cchMax
0x18000ef55  lea     rdx, [rsp+2F0h+sz]; lpsz
0x18000ef5a  mov     [rsp+2F0h+var_2B8], rbx
0x18000ef5f  mov     rcx, rsi; rguid
0x18000ef62  call    cs:__imp_StringFromGUID2
0x18000ef68  test    eax, eax
0x18000ef6a  jnz     loc_18000F2E9
0x18000ef70  mov     edi, 8007000Dh
0x18000ef75  mov     rbx, r15
0x18000ef78  mov     r14, r15
0x18000ef7b  mov     rcx, rbx; pv
0x18000ef7e  call    cs:__imp_CoTaskMemFree
0x18000ef84  test    edi, edi
0x18000ef86  js      loc_18000F2AB
0x18000ef8c  lea     rcx, [rsp+2F0h+lpSubKey]
0x18000ef91  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18000ef96  mov     rdx, [rsp+2F0h+var_2B8]
0x18000ef9b  lea     rcx, [rsp+2F0h+lpSubKey]
0x18000efa0  add     rdx, 6
0x18000efa4  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x18000efa9  mov     edi, eax
0x18000efab  test    eax, eax
0x18000efad  js      loc_18000F2AB
0x18000efb3  mov     rsi, [rsp+2F0h+lpSubKey]
0x18000efb8  lea     r8, aClsid; "CLSID\\"
0x18000efbf  mov     rbx, [rsp+2F0h+var_2B8]
0x18000efc4  mov     r9d, 6; unsigned __int64
0x18000efca  lea     rcx, [rsi+rbx*2]; unsigned __int16 *
0x18000efce  lea     edx, [r9+1]; unsigned __int64
0x18000efd2  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000efd7  add     rbx, 6
0x18000efdb  mov     [rsp+2F0h+var_2B8], rbx
0x18000efe0  test    r14, r14
0x18000efe3  jz      short loc_18000F042
0x18000efe5  mov     r15, r12
0x18000efe8  xor     ebx, ebx
0x18000efea  inc     r15
0x18000efed  cmp     [r14+r15*2], bx
0x18000eff2  jnz     short loc_18000EFEA
0x18000eff4  lea     rcx, [rsp+2F0h+lpSubKey]
0x18000eff9  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18000effe  mov     rdx, [rsp+2F0h+var_2B8]
0x18000f003  lea     rcx, [rsp+2F0h+lpSubKey]
0x18000f008  add     rdx, r15
0x18000f00b  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x18000f010  mov     edi, eax
0x18000f012  test    eax, eax
0x18000f014  js      loc_18000F2AB
0x18000f01a  mov     rsi, [rsp+2F0h+lpSubKey]
0x18000f01f  lea     rdx, [r15+1]; unsigned __int64
0x18000f023  mov     rbx, [rsp+2F0h+var_2B8]
0x18000f028  mov     r9, r15; unsigned __int64
0x18000f02b  mov     r8, r14; unsigned __int16 *
0x18000f02e  lea     rcx, [rsi+rbx*2]; unsigned __int16 *
0x18000f032  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000f037  add     rbx, r15
0x18000f03a  mov     [rsp+2F0h+var_2B8], rbx
0x18000f03f  xor     r15d, r15d
0x18000f042  mov     edi, r15d
0x18000f045  test    rsi, rsi
0x18000f048  jnz     short loc_18000F07A
0x18000f04a  xor     edx, edx
0x18000f04c  lea     rcx, [rsp+2F0h+lpSubKey]
0x18000f051  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x18000f056  mov     edi, eax
0x18000f058  test    eax, eax
0x18000f05a  js      loc_18000F2AB
0x18000f060  lea     edx, [rsi+1]; unsigned __int64
0x18000f063  xor     r9d, r9d; unsigned __int64
0x18000f066  mov     rsi, [rsp+2F0h+lpSubKey]
0x18000f06b  lea     r8, strIn; unsigned __int16 *
0x18000f072  mov     rcx, rsi; unsigned __int16 *
0x18000f075  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000f07a  lea     rax, [rsp+2F0h+hKey]
0x18000f07f  mov     [rsp+2F0h+lpSubKey], r15
0x18000f084  mov     rbx, 0FFFFFFFF80000000h
0x18000f08b  mov     [rsp+2F0h+var_2B0], r15
0x18000f090  mov     rcx, rbx; hKey
0x18000f093  mov     [rsp+2F0h+var_2B8], r15
0x18000f098  mov     r9d, 20019h; samDesired
0x18000f09e  mov     [r13+0], r15
0x18000f0a2  xor     r8d, r8d; ulOptions
0x18000f0a5  mov     [rsp+2F0h+hKey], r15
0x18000f0aa  mov     rdx, rsi; lpSubKey
0x18000f0ad  mov     [rsp+2F0h+phkResult], rax; phkResult
0x18000f0b2  call    cs:__imp_RegOpenKeyExW
0x18000f0b8  test    eax, eax
0x18000f0ba  jnz     short loc_18000F0ED
0x18000f0bc  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18000f0c1  lea     r8, [rbp+1F0h+var_250]; unsigned __int16 *
0x18000f0c5  call    ?LoadRegUIString@@YAJPEAUHKEY__@@PEBGPEAGI@Z; LoadRegUIString(HKEY__ *,ushort const *,ushort *,uint)
0x18000f0ca  mov     edi, eax
0x18000f0cc  test    eax, eax
0x18000f0ce  js      short loc_18000F0DE
0x18000f0d0  mov     rdx, r13; unsigned __int16 **
0x18000f0d3  lea     rcx, [rbp+1F0h+var_250]; unsigned __int16 *
0x18000f0d7  call    ?StrDupUsingNew@@YAJPEBGPEAPEAG@Z; StrDupUsingNew(ushort const *,ushort * *)
0x18000f0dc  mov     edi, eax
0x18000f0de  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18000f0e3  call    cs:__imp_RegCloseKey
0x18000f0e9  test    edi, edi
0x18000f0eb  js      short loc_18000F0F3
0x18000f0ed  cmp     [r13+0], r15
0x18000f0f1  jnz     short loc_18000F113
0x18000f0f3  mov     [rsp+2F0h+var_2C8], r13; unsigned __int16 **
0x18000f0f8  mov     r9d, 1; unsigned int
0x18000f0fe  xor     r8d, r8d; lpValue
0x18000f101  mov     [rsp+2F0h+phkResult], r15; unsigned int *
0x18000f106  mov     rdx, rsi; lpSubKey
0x18000f109  mov     rcx, rbx; hkey
0x18000f10c  call    ?GetRegDwordOrString@@YAJPEAUHKEY__@@PEBG1KPEAKPEAPEAG@Z; GetRegDwordOrString(HKEY__ *,ushort const *,ushort const *,ulong,ulong *,ushort * *)
0x18000f111  mov     edi, eax
0x18000f113  mov     rcx, rsi; pv
0x18000f116  call    cs:__imp_CoTaskMemFree
0x18000f11c  test    edi, edi
0x18000f11e  jz      loc_18000F2AB
0x18000f124  mov     rsi, r15
0x18000f127  js      loc_18000F2A2
0x18000f12d  lea     rcx, [rsp+2F0h+lpSubKey]
0x18000f132  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18000f137  mov     rdx, [rsp+2F0h+var_2B8]
0x18000f13c  lea     rcx, [rsp+2F0h+lpSubKey]
0x18000f141  add     rdx, 6
0x18000f145  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x18000f14a  mov     edi, eax
0x18000f14c  test    eax, eax
0x18000f14e  js      loc_18000F2A2
0x18000f154  mov     rax, [rsp+2F0h+lpSubKey]
0x18000f159  lea     r8, aClsid; "CLSID\\"
0x18000f160  mov     rbx, [rsp+2F0h+var_2B8]
0x18000f165  mov     r9d, 6; unsigned __int64
0x18000f16b  lea     rcx, [rax+rbx*2]; unsigned __int16 *
0x18000f16f  lea     edx, [r9+1]; unsigned __int64
0x18000f173  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000f178  add     rbx, 6
0x18000f17c  mov     [rsp+2F0h+var_2B8], rbx
0x18000f181  test    r14, r14
0x18000f184  jz      short loc_18000F1DC
0x18000f186  inc     r12
0x18000f189  cmp     [r14+r12*2], r15w
0x18000f18e  jnz     short loc_18000F186
0x18000f190  lea     rcx, [rsp+2F0h+lpSubKey]
0x18000f195  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18000f19a  mov     rdx, [rsp+2F0h+var_2B8]
0x18000f19f  lea     rcx, [rsp+2F0h+lpSubKey]
0x18000f1a4  add     rdx, r12
0x18000f1a7  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x18000f1ac  mov     edi, eax
0x18000f1ae  test    eax, eax
0x18000f1b0  js      loc_18000F2A2
0x18000f1b6  mov     rax, [rsp+2F0h+lpSubKey]
0x18000f1bb  lea     rdx, [r12+1]; unsigned __int64
0x18000f1c0  mov     rbx, [rsp+2F0h+var_2B8]
0x18000f1c5  mov     r9, r12; unsigned __int64
0x18000f1c8  mov     r8, r14; unsigned __int16 *
0x18000f1cb  lea     rcx, [rax+rbx*2]; unsigned __int16 *
0x18000f1cf  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000f1d4  add     rbx, r12
0x18000f1d7  mov     [rsp+2F0h+var_2B8], rbx
0x18000f1dc  lea     rcx, [rsp+2F0h+lpSubKey]
0x18000f1e1  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18000f1e6  mov     rdx, [rsp+2F0h+var_2B8]
0x18000f1eb  lea     rcx, [rsp+2F0h+lpSubKey]
0x18000f1f0  add     rdx, 0Fh
0x18000f1f4  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x18000f1f9  mov     edi, eax
0x18000f1fb  test    eax, eax
0x18000f1fd  js      loc_18000F2A2
0x18000f203  mov     rsi, [rsp+2F0h+lpSubKey]
0x18000f208  lea     r8, aInprocserver32; "\\InprocServer32"
0x18000f20f  mov     rbx, [rsp+2F0h+var_2B8]
0x18000f214  mov     r9d, 0Fh; unsigned __int64
0x18000f21a  lea     rcx, [rsi+rbx*2]; unsigned __int16 *
0x18000f21e  lea     edx, [r9+1]; unsigned __int64
0x18000f222  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000f227  add     rbx, 0Fh
0x18000f22b  mov     [rsp+2F0h+var_2B8], rbx
0x18000f230  test    rsi, rsi
0x18000f233  jnz     short loc_18000F265
0x18000f235  xor     edx, edx
0x18000f237  lea     rcx, [rsp+2F0h+lpSubKey]
0x18000f23c  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x18000f241  mov     edi, eax
0x18000f243  test    eax, eax
0x18000f245  js      loc_18000F433
0x18000f24b  lea     edx, [rsi+1]; unsigned __int64
0x18000f24e  xor     r9d, r9d; unsigned __int64
0x18000f251  mov     rsi, [rsp+2F0h+lpSubKey]
0x18000f256  lea     r8, strIn; unsigned __int16 *
0x18000f25d  mov     rcx, rsi; unsigned __int16 *
0x18000f260  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000f265  mov     [rsp+2F0h+var_2C8], r13; unsigned __int16 **
0x18000f26a  mov     r9d, 1; unsigned int
0x18000f270  xor     r8d, r8d; lpValue
0x18000f273  mov     [rsp+2F0h+phkResult], r15; unsigned int *
0x18000f278  mov     rdx, rsi; lpSubKey
0x18000f27b  mov     [rsp+2F0h+lpSubKey], r15
0x18000f280  mov     rcx, 0FFFFFFFF80000000h; hkey
0x18000f287  mov     [rsp+2F0h+var_2B0], r15
0x18000f28c  mov     [rsp+2F0h+var_2B8], r15
0x18000f291  call    ?GetRegDwordOrString@@YAJPEAUHKEY__@@PEBG1KPEAKPEAPEAG@Z; GetRegDwordOrString(HKEY__ *,ushort const *,ushort const *,ulong,ulong *,ushort * *)
0x18000f296  mov     edi, eax
0x18000f298  cmp     eax, 1
0x18000f29b  jnz     short loc_18000F2A2
0x18000f29d  mov     edi, 80070002h
0x18000f2a2  mov     rcx, rsi; pv
0x18000f2a5  call    cs:__imp_CoTaskMemFree
0x18000f2ab  mov     rcx, r14; lpMem
0x18000f2ae  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f2b3  lea     rcx, [rsp+2F0h+lpSubKey]
0x18000f2b8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000f2bd  mov     eax, edi
0x18000f2bf  mov     rcx, [rbp+1F0h+var_40]
0x18000f2c6  xor     rcx, rsp; StackCookie
0x18000f2c9  call    __security_check_cookie
0x18000f2ce  mov     rbx, [rsp+2F0h+arg_0]
0x18000f2d6  add     rsp, 2C0h
0x18000f2dd  pop     r15
0x18000f2df  pop     r14
0x18000f2e1  pop     r13
0x18000f2e3  pop     r12
0x18000f2e5  pop     rdi
0x18000f2e6  pop     rsi
0x18000f2e7  pop     rbp
0x18000f2e8  retn
0x18000f2e9  lea     rax, [rsp+2F0h+sz]
0x18000f2ee  mov     rsi, r12
0x18000f2f1  inc     rsi
0x18000f2f4  cmp     [rax+rsi*2], r15w
0x18000f2f9  jnz     short loc_18000F2F1
0x18000f2fb  lea     rcx, [rsp+2F0h+lpSubKey]
0x18000f300  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18000f305  mov     rdx, [rsp+2F0h+var_2B8]
0x18000f30a  lea     rcx, [rsp+2F0h+lpSubKey]
0x18000f30f  add     rdx, rsi
0x18000f312  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x18000f317  mov     edi, eax
0x18000f319  test    eax, eax
0x18000f31b  js      loc_18000EF75
0x18000f321  mov     rax, [rsp+2F0h+lpSubKey]
0x18000f326  lea     rdx, [rsi+1]; unsigned __int64
0x18000f32a  mov     rbx, [rsp+2F0h+var_2B8]
0x18000f32f  lea     r8, [rsp+2F0h+sz]; unsigned __int16 *
0x18000f334  mov     r9, rsi; unsigned __int64
0x18000f337  lea     rcx, [rax+rbx*2]; unsigned __int16 *
0x18000f33b  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000f340  add     rbx, rsi
0x18000f343  lea     rcx, [rsp+2F0h+lpSubKey]
0x18000f348  mov     [rsp+2F0h+var_2B8], rbx
0x18000f34d  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18000f352  mov     rdx, [rsp+2F0h+var_2B8]
0x18000f357  lea     rcx, [rsp+2F0h+lpSubKey]
0x18000f35c  add     rdx, 42h ; 'B'
0x18000f360  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x18000f365  mov     rsi, [rsp+2F0h+lpSubKey]
0x18000f36a  mov     edi, eax
0x18000f36c  test    eax, eax
0x18000f36e  js      short loc_18000F398
0x18000f370  mov     rbx, [rsp+2F0h+var_2B8]
0x18000f375  lea     r8, aPersistentaddi; "\\PersistentAddinsRegistered\\{89BCB740"...
0x18000f37c  mov     r9d, 42h ; 'B'; unsigned __int64
0x18000f382  lea     rcx, [rsi+rbx*2]; unsigned __int16 *
0x18000f386  lea     edx, [r9+1]; unsigned __int64
  ... truncated ...
```
