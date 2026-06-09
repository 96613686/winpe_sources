# UnRegisterAHandler(SHandlerEntry const &)

- ea: `0x18000ba74`
- end: `0x18000bdd5`
- name: `?UnRegisterAHandler@@YAJAEBUSHandlerEntry@@@Z`
- size: `865`
- prototype: `__int64 __fastcall(const struct SHandlerEntry *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000cee0`

## callees

- `0x180001e40`
- `0x180001e80`
- `0x180005ae4`
- `0x180009e20`
- `0x18000b288`
- `0x18000ba74`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000bca5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000bca5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bc89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bd65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bd96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bc89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bd65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bd96`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bc7c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bc7c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000bbdd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000bd58`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000bbdd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000bd58`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bb1f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bc3c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bcfa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bb1f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bc3c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bcfa`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000bd14`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000bd1e`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000bd14`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000bd1e`

## string_xrefs

- `0x18000baf2`: `CLSID`
- `0x18000bb3d`: `CLSID\`

## pseudocode

```c
__int64 __fastcall UnRegisterAHandler(const struct SHandlerEntry *a1)
{
  unsigned int v1; // edi
  unsigned int v2; // esi
  unsigned int v3; // ebx
  DWORD v4; // r14d
  __int64 v5; // rax
  const wchar_t *v6; // rcx
  __int64 v7; // rdx
  WCHAR *v8; // r8
  WCHAR *v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rax
  LSTATUS v12; // ebx
  __int64 v13; // rax
  unsigned __int64 v14; // rcx
  LSTATUS v15; // ebx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *v22[7]; // [rsp+68h] [rbp-98h] BYREF
  wchar_t SubKey[6]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR v24[258]; // [rsp+ACh] [rbp-54h] BYREF
  WCHAR Data[264]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v22[0] = (wchar_t *)L"{2e2294a9-50d7-4fe7-a09f-e6492e185884}";
  v22[1] = L"rtf persistent handler";
  v22[2] = L"PersistentAddinsRegistered";
  v22[4] = L"{89BCB740-6119-101A-BCB7-00DD010655AF}";
  v22[5] = L"{e2403e98-663b-4df6-b234-687789db8560}";
  v22[3] = 0;
  v1 = DestroyKeyValues((const wchar_t *const *)v22, 6);
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v2 = 0;
  v3 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0x2001Fu, &hKey);
  v4 = 0;
  if ( !v3 )
  {
    while ( 1 )
    {
      v5 = 2147483646;
      v6 = L"CLSID\\";
      v7 = 260;
      v8 = SubKey;
      do
      {
        if ( !v5 )
          break;
        if ( !*v6 )
          break;
        *v8++ = *v6++;
        --v5;
        --v7;
      }
      while ( v7 );
      v9 = v8 - 1;
      v2 = v7 == 0 ? 0x8007007A : 0;
      if ( v7 )
        v9 = v8;
      *v9 = 0;
      v10 = -1;
      do
        ++v10;
      while ( SubKey[v10] );
      ftLastWriteTime = 0;
      cchName = 260 - v10;
      v3 = RegEnumKeyExW(hKey, v4, &SubKey[(unsigned int)v10], &cchName, 0, 0, 0, &ftLastWriteTime);
      if ( v3 )
        break;
      ++v4;
      v11 = -1;
      do
        ++v11;
      while ( SubKey[v11] );
      StringCchCatW(SubKey, 260 - v11, L"\\PersistentHandler");
      phkResult = 0;
      if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x2001Fu, &phkResult) )
      {
        Type = 0;
        cchName = 520;
        v12 = RegQueryValueExW(phkResult, 0, 0, &Type, (LPBYTE)Data, &cchName);
        RegCloseKey(phkResult);
        if ( v12 || (unsigned int)_o__wcsicmp(Data, L"{2e2294a9-50d7-4fe7-a09f-e6492e185884}") )
        {
          v1 = v12;
        }
        else
        {
          v13 = -1;
          do
            ++v13;
          while ( SubKey[v13] );
          v14 = 2 * v13 - 36;
          if ( v14 >= 0x208 )
            _report_rangecheckfailure();
          *(wchar_t *)((char *)SubKey + v14) = 0;
          if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x2001Fu, &phkResult) )
          {
            if ( v1 )
              RegDeleteKeyW(phkResult, L"PersistentHandler");
            else
              v1 = RegDeleteKeyW(phkResult, L"PersistentHandler");
            v4 = 0;
          }
          cchName = 260;
          v15 = RegEnumKeyExW(phkResult, 0, Data, &cchName, 0, 0, 0, &ftLastWriteTime);
          RegCloseKey(phkResult);
          if ( v15 == 259 )
            RemoveAClass(v24);
        }
      }
    }
  }
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(hKey);
  if ( v3 == 259 )
    v3 = v2;
  if ( v3 )
    return v3;
  return v1;
}

```

## disassembly

```asm
0x18000ba74  push    rbp
0x18000ba76  push    rbx
0x18000ba77  push    rsi
0x18000ba78  push    rdi
0x18000ba79  push    r12
0x18000ba7b  push    r13
0x18000ba7d  push    r14
0x18000ba7f  push    r15
0x18000ba81  lea     rbp, [rsp-3D8h]
0x18000ba89  sub     rsp, 4D8h
0x18000ba90  mov     rax, cs:__security_cookie
0x18000ba97  xor     rax, rsp
0x18000ba9a  mov     [rbp+410h+var_50], rax
0x18000baa1  mov     rax, cs:off_18001C460; "{2e2294a9-50d7-4fe7-a09f-e6492e185884}"
0x18000baa8  lea     rcx, [rsp+510h+var_4A8]; wchar_t **
0x18000baad  mov     [rsp+510h+var_4A8], rax
0x18000bab2  xor     r15d, r15d
0x18000bab5  mov     rax, cs:off_18001C468; "rtf persistent handler"
0x18000babc  mov     [rsp+510h+var_4A0], rax
0x18000bac1  lea     rax, aPersistentaddi; "PersistentAddinsRegistered"
0x18000bac8  mov     [rsp+510h+var_498], rax
0x18000bacd  lea     rax, a89bcb740611910; "{89BCB740-6119-101A-BCB7-00DD010655AF}"
0x18000bad4  mov     [rbp+410h+var_488], rax
0x18000bad8  lea     edx, [r15+6]; int
0x18000badc  mov     rax, cs:off_18001C470; "{e2403e98-663b-4df6-b234-687789db8560}"
0x18000bae3  mov     [rbp+410h+var_480], rax
0x18000bae7  mov     [rbp+410h+var_490], r15
0x18000baeb  call    ?DestroyKeyValues@@YAJPEBQEB_WH@Z; DestroyKeyValues(wchar_t const * const *,int)
0x18000baf0  mov     edi, eax
0x18000baf2  lea     rdx, aClsid_1; "CLSID"
0x18000baf9  lea     rax, [rsp+510h+hKey]
0x18000bafe  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000bb02  mov     r9d, 2001Fh; samDesired
0x18000bb08  mov     [rsp+510h+phkResult], rax; phkResult
0x18000bb0d  xor     r8d, r8d; ulOptions
0x18000bb10  mov     [rsp+510h+hKey], r12
0x18000bb15  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000bb1c  mov     esi, r15d
0x18000bb1f  call    cs:__imp_RegOpenKeyExW
0x18000bb25  mov     ebx, eax
0x18000bb27  mov     r14d, r15d
0x18000bb2a  test    eax, eax
0x18000bb2c  jnz     loc_18000BD8C
0x18000bb32  mov     r13d, 104h
0x18000bb38  mov     eax, 7FFFFFFEh
0x18000bb3d  lea     rcx, aClsid; "CLSID\\"
0x18000bb44  mov     rdx, r13
0x18000bb47  lea     r8, [rbp+410h+SubKey]
0x18000bb4b  test    rax, rax
0x18000bb4e  jz      short loc_18000BB6F
0x18000bb50  movzx   r9d, word ptr [rcx]
0x18000bb54  test    r9w, r9w
0x18000bb58  jz      short loc_18000BB6F
0x18000bb5a  mov     [r8], r9w
0x18000bb5e  add     rcx, 2
0x18000bb62  add     r8, 2
0x18000bb66  dec     rax
0x18000bb69  sub     rdx, 1
0x18000bb6d  jnz     short loc_18000BB4B
0x18000bb6f  mov     rax, rdx
0x18000bb72  lea     rcx, [r8-2]
0x18000bb76  neg     rax
0x18000bb79  lea     rax, [rbp+410h+SubKey]
0x18000bb7d  sbb     esi, esi
0x18000bb7f  not     esi
0x18000bb81  and     esi, 8007007Ah
0x18000bb87  test    rdx, rdx
0x18000bb8a  cmovnz  rcx, r8
0x18000bb8e  mov     [rcx], r15w
0x18000bb92  mov     rcx, r12
0x18000bb95  inc     rcx
0x18000bb98  cmp     [rax+rcx*2], r15w
0x18000bb9d  jnz     short loc_18000BB95
0x18000bb9f  mov     eax, r13d
0x18000bba2  mov     qword ptr [rsp+510h+ftLastWriteTime.dwLowDateTime], r15
0x18000bba7  sub     eax, ecx
0x18000bba9  lea     r8, [rbp+410h+SubKey]
0x18000bbad  mov     [rsp+510h+cchName], eax
0x18000bbb1  lea     r9, [rsp+510h+cchName]; lpcchName
0x18000bbb6  mov     eax, ecx
0x18000bbb8  mov     edx, r14d; dwIndex
0x18000bbbb  mov     rcx, [rsp+510h+hKey]; hKey
0x18000bbc0  lea     r8, [r8+rax*2]; lpName
0x18000bbc4  lea     rax, [rsp+510h+ftLastWriteTime]
0x18000bbc9  mov     [rsp+510h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000bbce  mov     [rsp+510h+lpcchClass], r15; lpcchClass
0x18000bbd3  mov     [rsp+510h+lpClass], r15; lpClass
0x18000bbd8  mov     [rsp+510h+phkResult], r15; lpReserved
0x18000bbdd  call    cs:__imp_RegEnumKeyExW
0x18000bbe3  mov     ebx, eax
0x18000bbe5  test    eax, eax
0x18000bbe7  jnz     loc_18000BD8C
0x18000bbed  inc     r14d
0x18000bbf0  lea     rcx, [rbp+410h+SubKey]
0x18000bbf4  mov     rax, r12
0x18000bbf7  inc     rax
0x18000bbfa  cmp     [rcx+rax*2], r15w
0x18000bbff  jnz     short loc_18000BBF7
0x18000bc01  mov     rdx, r13
0x18000bc04  lea     r8, aPersistenthand; "\\PersistentHandler"
0x18000bc0b  sub     rdx, rax; unsigned __int64
0x18000bc0e  lea     rcx, [rbp+410h+SubKey]; wchar_t *
0x18000bc12  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000bc17  lea     rax, [rsp+510h+var_4C8]
0x18000bc1c  mov     [rsp+510h+var_4C8], r15
0x18000bc21  mov     esi, 2001Fh
0x18000bc26  mov     [rsp+510h+phkResult], rax; phkResult
0x18000bc2b  mov     r9d, esi; samDesired
0x18000bc2e  lea     rdx, [rbp+410h+SubKey]; lpSubKey
0x18000bc32  xor     r8d, r8d; ulOptions
0x18000bc35  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000bc3c  call    cs:__imp_RegOpenKeyExW
0x18000bc42  test    eax, eax
0x18000bc44  jnz     loc_18000BB38
0x18000bc4a  mov     rcx, [rsp+510h+var_4C8]; hKey
0x18000bc4f  lea     rax, [rsp+510h+cchName]
0x18000bc54  mov     [rsp+510h+lpClass], rax; lpcbData
0x18000bc59  lea     r9, [rsp+510h+Type]; lpType
0x18000bc5e  lea     rax, [rbp+410h+Data]
0x18000bc65  mov     [rsp+510h+Type], r15d
0x18000bc6a  xor     r8d, r8d; lpReserved
0x18000bc6d  mov     [rsp+510h+phkResult], rax; lpData
0x18000bc72  xor     edx, edx; lpValueName
0x18000bc74  mov     [rsp+510h+cchName], 208h
0x18000bc7c  call    cs:__imp_RegQueryValueExW
0x18000bc82  mov     rcx, [rsp+510h+var_4C8]; hKey
0x18000bc87  mov     ebx, eax
0x18000bc89  call    cs:__imp_RegCloseKey
0x18000bc8f  test    ebx, ebx
0x18000bc91  jnz     loc_18000BD85
0x18000bc97  mov     rdx, cs:off_18001C460; "{2e2294a9-50d7-4fe7-a09f-e6492e185884}"
0x18000bc9e  lea     rcx, [rbp+410h+Data]
0x18000bca5  call    cs:__imp__o__wcsicmp
0x18000bcab  test    eax, eax
0x18000bcad  jnz     loc_18000BD85
0x18000bcb3  lea     rcx, [rbp+410h+SubKey]
0x18000bcb7  mov     rax, r12
0x18000bcba  inc     rax
0x18000bcbd  cmp     [rcx+rax*2], r15w
0x18000bcc2  jnz     short loc_18000BCBA
0x18000bcc4  lea     rcx, ds:0FFFFFFFFFFFFFFDCh[rax*2]
0x18000bccc  cmp     rcx, 208h
0x18000bcd3  jnb     loc_18000BDCF
0x18000bcd9  mov     [rbp+rcx+410h+SubKey], r15w
0x18000bcdf  lea     rax, [rsp+510h+var_4C8]
0x18000bce4  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000bceb  mov     [rsp+510h+phkResult], rax; phkResult
0x18000bcf0  mov     r9d, esi; samDesired
0x18000bcf3  lea     rdx, [rbp+410h+SubKey]; lpSubKey
0x18000bcf7  xor     r8d, r8d; ulOptions
0x18000bcfa  call    cs:__imp_RegOpenKeyExW
0x18000bd00  test    eax, eax
0x18000bd02  jnz     short loc_18000BD27
0x18000bd04  mov     rcx, [rsp+510h+var_4C8]; hKey
0x18000bd09  lea     rdx, SubKey; "PersistentHandler"
0x18000bd10  test    edi, edi
0x18000bd12  jnz     short loc_18000BD1E
0x18000bd14  call    cs:__imp_RegDeleteKeyW
0x18000bd1a  mov     edi, eax
0x18000bd1c  jmp     short loc_18000BD24
0x18000bd1e  call    cs:__imp_RegDeleteKeyW
0x18000bd24  mov     r14d, r15d
0x18000bd27  mov     rcx, [rsp+510h+var_4C8]; hKey
0x18000bd2c  lea     rax, [rsp+510h+ftLastWriteTime]
0x18000bd31  mov     [rsp+510h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000bd36  lea     r9, [rsp+510h+cchName]; lpcchName
0x18000bd3b  mov     [rsp+510h+lpcchClass], r15; lpcchClass
0x18000bd40  lea     r8, [rbp+410h+Data]; lpName
0x18000bd47  mov     [rsp+510h+lpClass], r15; lpClass
0x18000bd4c  xor     edx, edx; dwIndex
0x18000bd4e  mov     [rsp+510h+phkResult], r15; lpReserved
0x18000bd53  mov     [rsp+510h+cchName], r13d
0x18000bd58  call    cs:__imp_RegEnumKeyExW
0x18000bd5e  mov     rcx, [rsp+510h+var_4C8]; hKey
0x18000bd63  mov     ebx, eax
0x18000bd65  call    cs:__imp_RegCloseKey
0x18000bd6b  cmp     ebx, 103h
0x18000bd71  jnz     loc_18000BB38
0x18000bd77  lea     rcx, [rbp+410h+var_464]; lpSubKey
0x18000bd7b  call    ?RemoveAClass@@YAJPEB_W@Z; RemoveAClass(wchar_t const *)
0x18000bd80  jmp     loc_18000BB38
0x18000bd85  mov     edi, ebx
0x18000bd87  jmp     loc_18000BB38
0x18000bd8c  mov     rcx, [rsp+510h+hKey]; hKey
0x18000bd91  cmp     rcx, r12
0x18000bd94  jz      short loc_18000BD9C
0x18000bd96  call    cs:__imp_RegCloseKey
0x18000bd9c  cmp     ebx, 103h
0x18000bda2  cmovz   ebx, esi
0x18000bda5  test    ebx, ebx
0x18000bda7  cmovnz  edi, ebx
0x18000bdaa  mov     eax, edi
0x18000bdac  mov     rcx, [rbp+410h+var_50]
0x18000bdb3  xor     rcx, rsp; StackCookie
0x18000bdb6  call    __security_check_cookie
0x18000bdbb  add     rsp, 4D8h
0x18000bdc2  pop     r15
0x18000bdc4  pop     r14
0x18000bdc6  pop     r13
0x18000bdc8  pop     r12
0x18000bdca  pop     rdi
0x18000bdcb  pop     rsi
0x18000bdcc  pop     rbx
0x18000bdcd  pop     rbp
0x18000bdce  retn
0x18000bdcf  call    __report_rangecheckfailure
```
