# GetTestSubstituteFileName

- ea: `0x18002ee9c`
- end: `0x18002f18e`
- name: `GetTestSubstituteFileName`
- size: `754`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002f6ac`

## callees

- `0x180003950`
- `0x18000b658`
- `0x18000fdac`
- `0x180010f54`
- `0x180013d2c`
- `0x18002ee9c`
- `0x180042630`
- `0x180042a24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ef4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f0e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ef4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f0e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002eff8`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002eff8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ef75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ef75`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002f07c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002f07c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002f0a2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002f0a2`

## string_xrefs

- `0x18002ef67`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test\Security\HashSubstitution`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetTestSubstituteFileName(const WCHAR *a1, _DWORD *a2, wchar_t **a3)
{
  unsigned int v6; // esi
  WCHAR *v7; // rdi
  wchar_t *v8; // rbx
  __int64 v9; // rdx
  const struct std::nothrow_t *v10; // rdx
  LSTATUS v11; // eax
  signed int v12; // r15d
  unsigned int v13; // eax
  __int64 v14; // rdx
  int v15; // eax
  DWORD v16; // esi
  wchar_t *v17; // rax
  int v19; // eax
  unsigned int v20; // r9d
  int phkResult; // [rsp+20h] [rbp-49h]
  int phkResulta; // [rsp+20h] [rbp-49h]
  unsigned int phkResultb; // [rsp+20h] [rbp-49h]
  int phkResultc; // [rsp+20h] [rbp-49h]
  LPWSTR lpValueName; // [rsp+60h] [rbp-9h] BYREF
  wchar_t *v26; // [rsp+68h] [rbp-1h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+70h] [rbp+7h] BYREF
  DWORD cchValueName; // [rsp+74h] [rbp+Bh] BYREF
  DWORD cValues; // [rsp+78h] [rbp+Fh] BYREF
  HKEY hKey; // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v6 = 0;
  hKey = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cchValueName = 0;
  v7 = 0;
  lpValueName = 0;
  v8 = 0;
  v26 = 0;
  if ( a2 )
    *a2 = 0;
  if ( !a1 )
  {
    v9 = 151;
LABEL_9:
    v6 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileCheck.cpp",
      (const char *)0x80004003LL,
      phkResult);
    goto LABEL_28;
  }
  if ( !a2 )
  {
    v9 = 152;
    goto LABEL_9;
  }
  if ( !a3 )
  {
    v9 = 153;
    goto LABEL_9;
  }
  *a2 = 0;
  *a3 = 0;
  if ( (unsigned int)AreTestKeysAllowed((bool)a1) )
  {
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    v11 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test\\Security\\HashSubstitution",
            0,
            1u,
            &hKey);
    v12 = (unsigned __int16)v11 | 0x80070000;
    if ( v11 <= 0 )
      v12 = v11;
    if ( v12 < 0 )
    {
      v6 = -2147024894;
      if ( v12 == -2147024894 )
        goto LABEL_28;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA7,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileCheck.cpp",
        (const char *)(unsigned int)v12,
        phkResulta);
LABEL_27:
      v6 = v12;
      goto LABEL_28;
    }
    v13 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
    if ( !v13 )
    {
      cchValueName = cbMaxValueNameLen + 1;
      v15 = WuSmartPtr::XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::STArrayZeroAllocPolicy<wchar_t>>::ReleaseAndAllocArray(
              &lpValueName,
              cbMaxValueNameLen + 1);
      v6 = v15;
      v12 = 0;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB8,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileCheck.cpp",
          (const char *)(unsigned int)v15,
          phkResultb);
        v7 = lpValueName;
        goto LABEL_28;
      }
      v16 = 0;
      v7 = lpValueName;
      if ( cValues )
      {
        while ( 1 )
        {
          cchValueName = cbMaxValueNameLen + 1;
          v13 = RegEnumValueW(hKey, v16, v7, &cchValueName, 0, 0, 0, 0);
          if ( v13 )
          {
            v14 = 191;
            goto LABEL_39;
          }
          if ( CompareStringW(0x7Fu, 1u, v7, -1, a1, -1) == 2 )
            break;
          if ( ++v16 >= cValues )
            goto LABEL_26;
        }
        v19 = WuSmartPtr::XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::STArrayZeroAllocPolicy<wchar_t>>::ReleaseAndAllocArray(
                &v26,
                260);
        v6 = v19;
        if ( v19 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC4,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileCheck.cpp",
            (const char *)(unsigned int)v19,
            phkResultc);
          v8 = v26;
          goto LABEL_28;
        }
        v8 = v26;
        RegQueryStringValueWithDefault(hKey, v7, v26, v20, a1);
        *a2 = 1;
      }
LABEL_26:
      v17 = v8;
      v8 = 0;
      *a3 = v17;
      goto LABEL_27;
    }
    v14 = 180;
LABEL_39:
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v14,
           (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileCheck.cpp",
           (const char *)v13,
           phkResultb);
  }
LABEL_28:
  if ( v8 )
    operator delete(v8, v10);
  if ( v7 )
    operator delete(v7, v10);
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x18002ee9c  mov     [rsp-8+arg_18], rbx
0x18002eea1  push    rbp
0x18002eea2  push    rsi
0x18002eea3  push    rdi
0x18002eea4  push    r12
0x18002eea6  push    r13
0x18002eea8  push    r14
0x18002eeaa  push    r15
0x18002eeac  lea     rbp, [rsp-27h]
0x18002eeb1  sub     rsp, 90h
0x18002eeb8  mov     rax, cs:__security_cookie
0x18002eebf  xor     rax, rsp
0x18002eec2  mov     [rbp+57h+var_38], rax
0x18002eec6  mov     r12, r8
0x18002eec9  mov     r14, rdx
0x18002eecc  mov     r13, rcx
0x18002eecf  xor     esi, esi
0x18002eed1  mov     [rbp+57h+hKey], rsi
0x18002eed5  mov     [rbp+57h+cValues], esi
0x18002eed8  mov     [rbp+57h+cbMaxValueNameLen], esi
0x18002eedb  mov     [rbp+57h+cchValueName], esi
0x18002eede  mov     edi, esi
0x18002eee0  mov     [rbp+57h+lpValueName], rsi
0x18002eee4  mov     ebx, esi
0x18002eee6  mov     [rbp+57h+var_58], rbx
0x18002eeea  test    rdx, rdx
0x18002eeed  jz      short loc_18002EEF1
0x18002eeef  mov     [rdx], esi
0x18002eef1  test    r13, r13
0x18002eef4  jnz     short loc_18002EEFD
0x18002eef6  mov     edx, 97h
0x18002eefb  jmp     short loc_18002EF13
0x18002eefd  test    r14, r14
0x18002ef00  jnz     short loc_18002EF09
0x18002ef02  mov     edx, 98h
0x18002ef07  jmp     short loc_18002EF13
0x18002ef09  test    r12, r12
0x18002ef0c  jnz     short loc_18002EF30
0x18002ef0e  mov     edx, 99h; void *
0x18002ef13  mov     rcx, [rbp+5Fh]; this
0x18002ef17  mov     esi, 80004003h
0x18002ef1c  mov     r9d, esi; char *
0x18002ef1f  lea     r8, aCW1SSrcClientL_21; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18002ef26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ef2b  jmp     loc_18002F0C1
0x18002ef30  mov     [rdx], esi
0x18002ef32  mov     [r8], rsi
0x18002ef35  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x18002ef3a  test    eax, eax
0x18002ef3c  jz      loc_18002F0C1
0x18002ef42  mov     rcx, [rbp+57h+hKey]; hKey
0x18002ef46  test    rcx, rcx
0x18002ef49  jz      short loc_18002EF55
0x18002ef4b  call    cs:__imp_RegCloseKey
0x18002ef51  mov     [rbp+57h+hKey], rsi
0x18002ef55  lea     rax, [rbp+57h+hKey]
0x18002ef59  mov     [rsp+0C0h+phkResult], rax; int
0x18002ef5e  mov     r9d, 1; samDesired
0x18002ef64  xor     r8d, r8d; ulOptions
0x18002ef67  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002ef6e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ef75  call    cs:__imp_RegOpenKeyExW
0x18002ef7b  movzx   r15d, ax
0x18002ef7f  or      r15d, 80070000h
0x18002ef86  test    eax, eax
0x18002ef88  cmovle  r15d, eax
0x18002ef8c  test    r15d, r15d
0x18002ef8f  jns     short loc_18002EFBC
0x18002ef91  mov     esi, 80070002h
0x18002ef96  cmp     r15d, esi
0x18002ef99  jz      loc_18002F0C1
0x18002ef9f  mov     rcx, [rbp+5Fh]; this
0x18002efa3  mov     r9d, r15d; char *
0x18002efa6  lea     r8, aCW1SSrcClientL_21; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18002efad  mov     edx, 0A7h; void *
0x18002efb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002efb7  jmp     loc_18002F0BE
0x18002efbc  mov     [rsp+0C0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x18002efc1  mov     [rsp+0C0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x18002efc6  mov     [rsp+0C0h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x18002efcb  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x18002efcf  mov     [rsp+0C0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18002efd4  lea     rax, [rbp+57h+cValues]
0x18002efd8  mov     [rsp+0C0h+lpcValues], rax; lpcValues
0x18002efdd  mov     [rsp+0C0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x18002efe2  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x18002efe7  mov     [rsp+0C0h+phkResult], rsi; int
0x18002efec  xor     r9d, r9d; lpReserved
0x18002efef  xor     r8d, r8d; lpcchClass
0x18002eff2  xor     edx, edx; lpClass
0x18002eff4  mov     rcx, [rbp+57h+hKey]; hKey
0x18002eff8  call    cs:__imp_RegQueryInfoKeyW
0x18002effe  test    eax, eax
0x18002f000  jz      short loc_18002F00C
0x18002f002  mov     edx, 0B4h
0x18002f007  jmp     loc_18002F173
0x18002f00c  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18002f00f  inc     eax
0x18002f011  mov     [rbp+57h+cchValueName], eax
0x18002f014  mov     edx, eax
0x18002f016  lea     rcx, [rbp+57h+lpValueName]
0x18002f01a  call    ?ReleaseAndAllocArray@?$XPtrBaseWithArrayAllocation@_WU?$STArrayZeroAllocPolicy@_W@Policies@WuSmartPtr@@@WuSmartPtr@@QEAAJ_K@Z; WuSmartPtr::XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::STArrayZeroAllocPolicy<wchar_t>>::ReleaseAndAllocArray(unsigned __int64)
0x18002f01f  mov     esi, eax
0x18002f021  xor     r15d, r15d
0x18002f024  test    eax, eax
0x18002f026  jns     short loc_18002F046
0x18002f028  mov     rcx, [rbp+5Fh]; this
0x18002f02c  mov     r9d, eax; char *
0x18002f02f  lea     r8, aCW1SSrcClientL_21; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18002f036  mov     edx, 0B8h; void *
0x18002f03b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f040  mov     rdi, [rbp+57h+lpValueName]
0x18002f044  jmp     short loc_18002F0C1
0x18002f046  mov     esi, r15d
0x18002f049  mov     rdi, [rbp+57h+lpValueName]
0x18002f04d  cmp     [rbp+57h+cValues], r15d
0x18002f051  jbe     short loc_18002F0B4
0x18002f053  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18002f056  inc     eax
0x18002f058  mov     [rbp+57h+cchValueName], eax
0x18002f05b  mov     [rsp+0C0h+lpcValues], r15; lpcbData
0x18002f060  mov     [rsp+0C0h+lpcbMaxClassLen], r15; lpData
0x18002f065  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r15; lpType
0x18002f06a  mov     [rsp+0C0h+phkResult], r15; unsigned int
0x18002f06f  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18002f073  mov     r8, rdi; lpValueName
0x18002f076  mov     edx, esi; dwIndex
0x18002f078  mov     rcx, [rbp+57h+hKey]; hKey
0x18002f07c  call    cs:__imp_RegEnumValueW
0x18002f082  test    eax, eax
0x18002f084  jnz     loc_18002F16E
0x18002f08a  or      eax, 0FFFFFFFFh
0x18002f08d  mov     dword ptr [rsp+0C0h+lpcbMaxSubKeyLen], eax; cchCount2
0x18002f091  mov     [rsp+0C0h+phkResult], r13; int
0x18002f096  mov     r9d, eax; cchCount1
0x18002f099  mov     r8, rdi; lpString1
0x18002f09c  lea     edx, [rax+2]; dwCmpFlags
0x18002f09f  lea     ecx, [rdx+7Eh]; Locale
0x18002f0a2  call    cs:__imp_CompareStringW
0x18002f0a8  cmp     eax, 2
0x18002f0ab  jz      short loc_18002F115
0x18002f0ad  inc     esi
0x18002f0af  cmp     esi, [rbp+57h+cValues]
0x18002f0b2  jb      short loc_18002F053
0x18002f0b4  mov     rax, rbx
0x18002f0b7  mov     rbx, r15
0x18002f0ba  mov     [r12], rax
0x18002f0be  mov     esi, r15d
0x18002f0c1  test    rbx, rbx
0x18002f0c4  jz      short loc_18002F0CF
0x18002f0c6  mov     rcx, rbx; void *
0x18002f0c9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002f0ce  nop
0x18002f0cf  test    rdi, rdi
0x18002f0d2  jz      short loc_18002F0DD
0x18002f0d4  mov     rcx, rdi; void *
0x18002f0d7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002f0dc  nop
0x18002f0dd  mov     rcx, [rbp+57h+hKey]; hKey
0x18002f0e1  test    rcx, rcx
0x18002f0e4  jz      short loc_18002F0EC
0x18002f0e6  call    cs:__imp_RegCloseKey
0x18002f0ec  mov     eax, esi
0x18002f0ee  mov     rcx, [rbp+57h+var_38]
0x18002f0f2  xor     rcx, rsp; StackCookie
0x18002f0f5  call    __security_check_cookie
0x18002f0fa  mov     rbx, [rsp+0C0h+arg_18]
0x18002f102  add     rsp, 90h
0x18002f109  pop     r15
0x18002f10b  pop     r14
0x18002f10d  pop     r13
0x18002f10f  pop     r12
0x18002f111  pop     rdi
0x18002f112  pop     rsi
0x18002f113  pop     rbp
0x18002f114  retn
0x18002f115  mov     edx, 104h
0x18002f11a  lea     rcx, [rbp+57h+var_58]
0x18002f11e  call    ?ReleaseAndAllocArray@?$XPtrBaseWithArrayAllocation@_WU?$STArrayZeroAllocPolicy@_W@Policies@WuSmartPtr@@@WuSmartPtr@@QEAAJ_K@Z; WuSmartPtr::XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::STArrayZeroAllocPolicy<wchar_t>>::ReleaseAndAllocArray(unsigned __int64)
0x18002f123  mov     esi, eax
0x18002f125  test    eax, eax
0x18002f127  jns     short loc_18002F14A
0x18002f129  mov     rcx, [rbp+5Fh]; this
0x18002f12d  mov     r9d, eax; char *
0x18002f130  lea     r8, aCW1SSrcClientL_21; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18002f137  mov     edx, 0C4h; void *
0x18002f13c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f141  mov     rbx, [rbp+57h+var_58]
0x18002f145  jmp     loc_18002F0C1
0x18002f14a  mov     [rsp+0C0h+phkResult], r13; wchar_t *
0x18002f14f  mov     rbx, [rbp+57h+var_58]
0x18002f153  mov     r8, rbx; wchar_t *
0x18002f156  mov     rdx, rdi; wchar_t *
0x18002f159  mov     rcx, [rbp+57h+hKey]; HKEY
0x18002f15d  call    ?RegQueryStringValueWithDefault@@YAXPEAUHKEY__@@PEB_WPEA_WK1@Z; RegQueryStringValueWithDefault(HKEY__ *,wchar_t const *,wchar_t *,ulong,wchar_t const *)
0x18002f162  mov     dword ptr [r14], 1
0x18002f169  jmp     loc_18002F0B4
0x18002f16e  mov     edx, 0BFh; void *
0x18002f173  lea     r8, aCW1SSrcClientL_21; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18002f17a  mov     r9d, eax; char *
0x18002f17d  mov     rcx, [rbp+5Fh]; this
0x18002f181  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002f186  mov     esi, eax
0x18002f188  jmp     loc_18002F0C1
```
