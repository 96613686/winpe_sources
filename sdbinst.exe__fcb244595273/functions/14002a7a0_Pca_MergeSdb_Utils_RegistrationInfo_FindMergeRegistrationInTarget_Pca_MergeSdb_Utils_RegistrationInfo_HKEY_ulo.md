# Pca::MergeSdb::Utils::RegistrationInfo::FindMergeRegistrationInTarget(Pca::MergeSdb::Utils::RegistrationInfo &,HKEY__ *,ulong (*)(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,bool &),void *)

- ea: `0x14002a7a0`
- end: `0x14002aa46`
- name: `?FindMergeRegistrationInTarget@RegistrationInfo@Utils@MergeSdb@Pca@@SAKAEAV1234@PEAUHKEY__@@P6AKPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEA_N@Z2@Z`
- size: `678`
- prototype: `__int64 __fastcall(Pca::MergeSdb::Utils::RegistrationInfo *this, HKEY hKey, __int64 (__fastcall *)(__int64, HKEY *, char *), __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14002aa4c`

## callees

- `0x14001008c`
- `0x140020f9c`
- `0x14002a7a0`
- `0x14002d660`
- `0x14002df00`
- `0x14002f010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14002a924`
- `ADVAPI32!RegOpenKeyExW` at `0x14002a924`
- `ADVAPI32!RegEnumKeyExW` at `0x14002a8d2`
- `ADVAPI32!RegEnumKeyExW` at `0x14002a8d2`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14002a81a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14002a81a`
- `ADVAPI32!RegCloseKey` at `0x14002a89d`
- `ADVAPI32!RegCloseKey` at `0x14002a8f6`
- `ADVAPI32!RegCloseKey` at `0x14002a9db`
- `ADVAPI32!RegCloseKey` at `0x14002aa06`
- `ADVAPI32!RegCloseKey` at `0x14002a89d`
- `ADVAPI32!RegCloseKey` at `0x14002a8f6`
- `ADVAPI32!RegCloseKey` at `0x14002a9db`
- `ADVAPI32!RegCloseKey` at `0x14002aa06`
- `KERNEL32!GetLastError` at `0x14002a892`
- `KERNEL32!GetLastError` at `0x14002a8eb`
- `KERNEL32!GetLastError` at `0x14002a892`
- `KERNEL32!GetLastError` at `0x14002a8eb`
- `KERNEL32!GetProcessHeap` at `0x14002a9e2`
- `KERNEL32!GetProcessHeap` at `0x14002aa0d`
- `KERNEL32!GetProcessHeap` at `0x14002a9e2`
- `KERNEL32!GetProcessHeap` at `0x14002aa0d`
- `KERNEL32!SetLastError` at `0x14002a8a5`
- `KERNEL32!SetLastError` at `0x14002a8fe`
- `KERNEL32!SetLastError` at `0x14002a8a5`
- `KERNEL32!SetLastError` at `0x14002a8fe`
- `KERNEL32!HeapFree` at `0x14002a9f0`
- `KERNEL32!HeapFree` at `0x14002aa1b`
- `KERNEL32!HeapFree` at `0x14002a9f0`
- `KERNEL32!HeapFree` at `0x14002aa1b`

## string_xrefs

- `0x14002a999`: `Failed to open a registration key (%d)`
- `0x14002a953`: `Failed to read data from a registration key (%d)`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::RegistrationInfo::FindMergeRegistrationInTarget(
        Pca::MergeSdb::Utils::RegistrationInfo *this,
        HKEY hKey,
        __int64 (__fastcall *a3)(__int64, HKEY *, char *),
        __int64 a4)
{
  LSTATUS v6; // eax
  const char *v7; // r9
  unsigned int v8; // ebx
  WCHAR *v10; // rbx
  HKEY v11; // rsi
  DWORD v12; // r15d
  DWORD LastError; // edi
  LSTATUS v14; // eax
  unsigned int RegistrationFromRegistry; // edi
  HKEY v16; // rsi
  DWORD v17; // edi
  int v18; // eax
  const char *v19; // r9
  __int64 v20; // r8
  HANDLE ProcessHeap; // rax
  HANDLE v22; // rax
  LPDWORD lpcSubKeys; // [rsp+20h] [rbp-60h]
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-20h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-1Ch] BYREF
  DWORD cchName; // [rsp+68h] [rbp-18h] BYREF
  HKEY hKeya; // [rsp+70h] [rbp-10h] BYREF
  LPWSTR lpName; // [rsp+78h] [rbp-8h] BYREF
  char v29; // [rsp+C8h] [rbp+48h] BYREF
  __int64 (__fastcall *v30)(__int64, HKEY *, char *); // [rsp+D0h] [rbp+50h]
  __int64 v31; // [rsp+D8h] [rbp+58h]

  v31 = a4;
  v30 = a3;
  Pca::MergeSdb::Utils::RegistrationInfo::Reset(this);
  if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    return 87;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  v8 = v6;
  if ( v6 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::FindMergeRegistrationInTarget",
      1039,
      "RegQueryInfoKeyW failed for target key (%d)",
      v6);
    return v8;
  }
  else
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &lpName,
      0,
      ++cbMaxSubKeyLen,
      v7);
    v10 = lpName;
    if ( lpName )
    {
      cchName = 0;
      v11 = 0;
      hKeya = 0;
      v12 = 0;
      if ( cSubKeys )
      {
        while ( 1 )
        {
          cchName = cbMaxSubKeyLen;
          if ( v11 )
          {
            LastError = GetLastError();
            RegCloseKey(v11);
            SetLastError(LastError);
          }
          hKeya = 0;
          v14 = RegEnumKeyExW(hKey, v12, v10, &cchName, 0, 0, 0, 0);
          RegistrationFromRegistry = v14;
          if ( v14 )
            break;
          v16 = hKeya;
          if ( hKeya )
          {
            v17 = GetLastError();
            RegCloseKey(v16);
            SetLastError(v17);
          }
          hKeya = 0;
          v14 = RegOpenKeyExW(hKey, v10, 0, 0x20019u, &hKeya);
          RegistrationFromRegistry = v14;
          if ( v14 )
          {
            v19 = "Failed to open a registration key (%d)";
            v20 = 1079;
            goto LABEL_21;
          }
          v29 = 0;
          v18 = v30(v31, &hKeya, &v29);
          if ( v18 )
          {
            AslLogCallPrintf(
              1,
              "Pca::MergeSdb::Utils::RegistrationInfo::FindMergeRegistrationInTarget",
              1087,
              "Failed to read data from a registration key (%d)",
              v18);
          }
          else if ( v29 )
          {
            RegistrationFromRegistry = Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry(this, hKeya);
            goto LABEL_22;
          }
          if ( ++v12 >= cSubKeys )
            goto LABEL_25;
          v11 = hKeya;
        }
        if ( v14 == 259 )
        {
LABEL_25:
          v11 = hKeya;
          goto LABEL_26;
        }
        v19 = "RegEnumKeyExW failed (%d)";
        v20 = 1070;
LABEL_21:
        LODWORD(lpcSubKeys) = v14;
        AslLogCallPrintf(
          1,
          "Pca::MergeSdb::Utils::RegistrationInfo::FindMergeRegistrationInTarget",
          v20,
          v19,
          lpcSubKeys);
LABEL_22:
        if ( hKeya )
          RegCloseKey(hKeya);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v10);
        return RegistrationFromRegistry;
      }
      else
      {
LABEL_26:
        if ( v11 )
          RegCloseKey(v11);
        v22 = GetProcessHeap();
        HeapFree(v22, 0, v10);
        return 2;
      }
    }
    else
    {
      return 14;
    }
  }
}

```

## disassembly

```asm
0x14002a7a0  mov     [rsp-38h+arg_18], r9
0x14002a7a5  mov     [rsp-38h+arg_10], r8
0x14002a7aa  push    rbp
0x14002a7ab  push    rbx
0x14002a7ac  push    rsi
0x14002a7ad  push    rdi
0x14002a7ae  push    r12
0x14002a7b0  push    r13
0x14002a7b2  push    r15
0x14002a7b4  mov     rbp, rsp
0x14002a7b7  sub     rsp, 80h
0x14002a7be  mov     r13, rdx
0x14002a7c1  mov     r12, rcx
0x14002a7c4  call    ?Reset@RegistrationInfo@Utils@MergeSdb@Pca@@QEAAXXZ; Pca::MergeSdb::Utils::RegistrationInfo::Reset(void)
0x14002a7c9  lea     rax, [r13-1]
0x14002a7cd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002a7d1  ja      loc_14002AA2F
0x14002a7d7  xor     edi, edi
0x14002a7d9  mov     [rbp+cSubKeys], edi
0x14002a7dc  mov     [rbp+cbMaxSubKeyLen], edi
0x14002a7df  mov     [rsp+80h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x14002a7e4  mov     [rsp+80h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x14002a7e9  mov     [rsp+80h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x14002a7ee  mov     [rsp+80h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x14002a7f3  mov     [rsp+80h+lpcValues], rdi; lpcValues
0x14002a7f8  mov     [rsp+80h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x14002a7fd  lea     rax, [rbp+cbMaxSubKeyLen]
0x14002a801  mov     [rsp+80h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x14002a806  lea     rax, [rbp+cSubKeys]
0x14002a80a  mov     [rsp+80h+lpcSubKeys], rax; lpcSubKeys
0x14002a80f  xor     r9d, r9d; lpReserved
0x14002a812  xor     r8d, r8d; lpcchClass
0x14002a815  xor     edx, edx; lpClass
0x14002a817  mov     rcx, r13; hKey
0x14002a81a  call    cs:__imp_RegQueryInfoKeyW
0x14002a820  mov     ebx, eax
0x14002a822  test    eax, eax
0x14002a824  jz      short loc_14002A84D
0x14002a826  mov     dword ptr [rsp+80h+lpcSubKeys], eax
0x14002a82a  lea     r9, aRegqueryinfoke_2; "RegQueryInfoKeyW failed for target key "...
0x14002a831  mov     r8d, 40Fh
0x14002a837  lea     rdx, aPcaMergesdbUti_7; "Pca::MergeSdb::Utils::RegistrationInfo:"...
0x14002a83e  lea     ecx, [rdi+1]
0x14002a841  call    AslLogCallPrintf
0x14002a846  mov     eax, ebx
0x14002a848  jmp     loc_14002AA34
0x14002a84d  mov     eax, [rbp+cbMaxSubKeyLen]
0x14002a850  inc     eax
0x14002a852  mov     [rbp+cbMaxSubKeyLen], eax
0x14002a855  mov     r8d, eax
0x14002a858  xor     edx, edx
0x14002a85a  lea     rcx, [rbp+lpName]
0x14002a85e  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x14002a863  nop
0x14002a864  mov     rbx, [rbp+lpName]
0x14002a868  test    rbx, rbx
0x14002a86b  jz      loc_14002AA28
0x14002a871  mov     [rbp+cchName], edi
0x14002a874  mov     rsi, rdi
0x14002a877  mov     [rbp+hKey], rdi
0x14002a87b  mov     r15d, edi
0x14002a87e  cmp     [rbp+cSubKeys], edi
0x14002a881  jbe     loc_14002A9FE
0x14002a887  mov     eax, [rbp+cbMaxSubKeyLen]
0x14002a88a  mov     [rbp+cchName], eax
0x14002a88d  test    rsi, rsi
0x14002a890  jz      short loc_14002A8AD
0x14002a892  call    cs:__imp_GetLastError
0x14002a898  mov     edi, eax
0x14002a89a  mov     rcx, rsi; hKey
0x14002a89d  call    cs:__imp_RegCloseKey
0x14002a8a3  mov     ecx, edi; dwErrCode
0x14002a8a5  call    cs:__imp_SetLastError
0x14002a8ab  xor     edi, edi
0x14002a8ad  mov     [rbp+hKey], rdi
0x14002a8b1  mov     [rsp+80h+lpcValues], rdi; lpftLastWriteTime
0x14002a8b6  mov     [rsp+80h+lpcbMaxClassLen], rdi; lpcchClass
0x14002a8bb  mov     [rsp+80h+lpcbMaxSubKeyLen], rdi; lpClass
0x14002a8c0  mov     [rsp+80h+lpcSubKeys], rdi; lpReserved
0x14002a8c5  lea     r9, [rbp+cchName]; lpcchName
0x14002a8c9  mov     r8, rbx; lpName
0x14002a8cc  mov     edx, r15d; dwIndex
0x14002a8cf  mov     rcx, r13; hKey
0x14002a8d2  call    cs:__imp_RegEnumKeyExW
0x14002a8d8  mov     edi, eax
0x14002a8da  test    eax, eax
0x14002a8dc  jnz     loc_14002A9A8
0x14002a8e2  mov     rsi, [rbp+hKey]
0x14002a8e6  test    rsi, rsi
0x14002a8e9  jz      short loc_14002A904
0x14002a8eb  call    cs:__imp_GetLastError
0x14002a8f1  mov     edi, eax
0x14002a8f3  mov     rcx, rsi; hKey
0x14002a8f6  call    cs:__imp_RegCloseKey
0x14002a8fc  mov     ecx, edi; dwErrCode
0x14002a8fe  call    cs:__imp_SetLastError
0x14002a904  mov     [rbp+hKey], 0
0x14002a90c  lea     rax, [rbp+hKey]
0x14002a910  mov     [rsp+80h+lpcSubKeys], rax; phkResult
0x14002a915  mov     r9d, 20019h; samDesired
0x14002a91b  xor     r8d, r8d; ulOptions
0x14002a91e  mov     rdx, rbx; lpSubKey
0x14002a921  mov     rcx, r13; hKey
0x14002a924  call    cs:__imp_RegOpenKeyExW
0x14002a92a  mov     edi, eax
0x14002a92c  test    eax, eax
0x14002a92e  jnz     short loc_14002A999
0x14002a930  xor     edi, edi
0x14002a932  mov     [rbp+arg_8], dil
0x14002a936  lea     r8, [rbp+arg_8]
0x14002a93a  lea     rdx, [rbp+hKey]
0x14002a93e  mov     rcx, [rbp+arg_18]
0x14002a942  mov     rax, [rbp+arg_10]
0x14002a946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a94b  test    eax, eax
0x14002a94d  jz      short loc_14002A971
0x14002a94f  mov     dword ptr [rsp+80h+lpcSubKeys], eax
0x14002a953  lea     r9, aFailedToReadDa_1; "Failed to read data from a registration"...
0x14002a95a  mov     r8d, 43Fh
0x14002a960  lea     rdx, aPcaMergesdbUti_7; "Pca::MergeSdb::Utils::RegistrationInfo:"...
0x14002a967  lea     ecx, [rdi+1]
0x14002a96a  call    AslLogCallPrintf
0x14002a96f  jmp     short loc_14002A977
0x14002a971  cmp     [rbp+arg_8], dil
0x14002a975  jnz     short loc_14002A989
0x14002a977  inc     r15d
0x14002a97a  cmp     r15d, [rbp+cSubKeys]
0x14002a97e  jnb     short loc_14002A9FA
0x14002a980  mov     rsi, [rbp+hKey]
0x14002a984  jmp     loc_14002A887
0x14002a989  mov     rdx, [rbp+hKey]; hkey
0x14002a98d  mov     rcx, r12; this
0x14002a990  call    ?ReadRegistrationFromRegistry@RegistrationInfo@Utils@MergeSdb@Pca@@QEAAKPEAUHKEY__@@@Z; Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry(HKEY__ *)
0x14002a995  mov     edi, eax
0x14002a997  jmp     short loc_14002A9D2
0x14002a999  lea     r9, aFailedToOpenAR; "Failed to open a registration key (%d)"
0x14002a9a0  mov     r8d, 437h
0x14002a9a6  jmp     short loc_14002A9BC
0x14002a9a8  cmp     eax, 103h
0x14002a9ad  jz      short loc_14002A9FA
0x14002a9af  lea     r9, aRegenumkeyexwF; "RegEnumKeyExW failed (%d)"
0x14002a9b6  mov     r8d, 42Eh
0x14002a9bc  mov     dword ptr [rsp+80h+lpcSubKeys], eax
0x14002a9c0  lea     rdx, aPcaMergesdbUti_7; "Pca::MergeSdb::Utils::RegistrationInfo:"...
0x14002a9c7  mov     ecx, 1
0x14002a9cc  call    AslLogCallPrintf
0x14002a9d1  nop
0x14002a9d2  mov     rcx, [rbp+hKey]; hKey
0x14002a9d6  test    rcx, rcx
0x14002a9d9  jz      short loc_14002A9E2
0x14002a9db  call    cs:__imp_RegCloseKey
0x14002a9e1  nop
0x14002a9e2  call    cs:__imp_GetProcessHeap
0x14002a9e8  mov     rcx, rax; hHeap
0x14002a9eb  mov     r8, rbx; lpMem
0x14002a9ee  xor     edx, edx; dwFlags
0x14002a9f0  call    cs:__imp_HeapFree
0x14002a9f6  mov     eax, edi
0x14002a9f8  jmp     short loc_14002AA34
0x14002a9fa  mov     rsi, [rbp+hKey]
0x14002a9fe  test    rsi, rsi
0x14002aa01  jz      short loc_14002AA0D
0x14002aa03  mov     rcx, rsi; hKey
0x14002aa06  call    cs:__imp_RegCloseKey
0x14002aa0c  nop
0x14002aa0d  call    cs:__imp_GetProcessHeap
0x14002aa13  mov     rcx, rax; hHeap
0x14002aa16  mov     r8, rbx; lpMem
0x14002aa19  xor     edx, edx; dwFlags
0x14002aa1b  call    cs:__imp_HeapFree
0x14002aa21  mov     eax, 2
0x14002aa26  jmp     short loc_14002AA34
0x14002aa28  mov     eax, 0Eh
0x14002aa2d  jmp     short loc_14002AA34
0x14002aa2f  mov     eax, 57h ; 'W'
0x14002aa34  add     rsp, 80h
0x14002aa3b  pop     r15
0x14002aa3d  pop     r13
0x14002aa3f  pop     r12
0x14002aa41  pop     rdi
0x14002aa42  pop     rsi
0x14002aa43  pop     rbx
0x14002aa44  pop     rbp
0x14002aa45  retn
```
