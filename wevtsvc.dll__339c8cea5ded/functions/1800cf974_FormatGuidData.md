# FormatGuidData

- ea: `0x1800cf974`
- end: `0x1800cfcaa`
- name: `FormatGuidData`
- size: `822`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, struct _GUID *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x1800cd530`

## callees

- `0x180006770`
- `0x180014bd0`
- `0x180017b98`
- `0x18001c214`
- `0x18008b798`
- `0x18008b7c4`
- `0x1800953c8`
- `0x1800cb8d8`
- `0x1800cba84`
- `0x1800cce68`
- `0x1800ccee0`
- `0x1800ccf7c`
- `0x1800cd020`
- `0x1800cd058`
- `0x1800cf974`
- `0x1800dd010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cfad1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cfc1f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cfad1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cfc1f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800cfb84`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800cfb84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfaf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfb14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfba6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfbb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfc71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfc83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfaf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfb14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfba6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfbb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfc71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfc83`

## string_xrefs

- `0x1800cfaf9`: ` Failed to open registry path %s, GLE = %x\n`
- `0x1800cfb1a`: ` Failed to open registry path %s, GLE = %x\n`
- `0x1800cfc77`: ` Failed to query default value for registry path %s, GLE = %x\n`
- `0x1800cfc89`: ` Failed to query default value for registry path %s, GLE = %x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FormatGuidData(unsigned __int16 *a1, unsigned int a2, struct _GUID *a3, int a4)
{
  __int64 v4; // rbx
  unsigned __int64 v6; // r15
  REGSAM v8; // esi
  int v9; // r9d
  __int64 v11; // rdi
  __int64 v12; // rax
  __int64 v13; // r14
  HKEY *phkResult; // rax
  unsigned int (*v15)(unsigned __int16 *, ...); // rbx
  DWORD v16; // eax
  const wchar_t *v17; // rcx
  DWORD v18; // eax
  DWORD LastError; // eax
  HKEY *v20; // rax
  HKEY v21; // rdx
  DWORD v22; // eax
  HKEY hKey; // [rsp+40h] [rbp-59h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+48h] [rbp-51h] BYREF
  HKEY v25; // [rsp+50h] [rbp-49h] BYREF
  __int128 v26; // [rsp+58h] [rbp-41h]
  LPWSTR lpName; // [rsp+68h] [rbp-31h] BYREF
  LPWSTR v28; // [rsp+70h] [rbp-29h]
  LPCWSTR lpSubKey[13]; // [rsp+88h] [rbp-11h] BYREF
  DWORD cchName; // [rsp+118h] [rbp+7Fh] BYREF

  v4 = a4;
  v6 = a2;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&lpName);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
  v8 = 257;
  hKey = 0;
  if ( v9 )
  {
    if ( (_DWORD)v4 == 1 )
    {
      v8 = 265;
    }
    else if ( (_DWORD)v4 != 2 )
    {
      if ( TracePrinter )
      {
        if ( DebugExtPrint )
          TracePrinterExt((wchar_t *)L" Unknown GUID_TYPE: %x\n", (unsigned int)v4);
        else
          TracePrinter(L" Unknown GUID_TYPE: %x\n", (unsigned int)v4);
      }
      goto LABEL_7;
    }
  }
  v28 = lpName;
  *lpName = 0;
  v11 = (char *)v28 - (char *)lpName;
  v12 = tlx::_GetAppendBuffer<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
          &lpName,
          36);
  v13 = v12;
  if ( v12 )
  {
    tlx::guid_to_string_lower<unsigned short>(v12, a3);
    *(_WORD *)(v13 + 72) = 0;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Resize(
      &lpName,
      (v11 >> 1) + 36);
    if ( (int)tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
                lpSubKey,
                L"%s\\{%s}",
                off_1800E8BC0[v4],
                lpName) >= 0 )
    {
      phkResult = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
      if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, lpSubKey[0], 0, v8, phkResult) )
        goto LABEL_14;
      if ( (_DWORD)v4 != 1 )
        goto LABEL_29;
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::resize(
        &lpName,
        255);
      cchName = v28 - lpName;
      ftLastWriteTime = 0;
      if ( RegEnumKeyExW(hKey, 0, lpName, &cchName, 0, 0, 0, &ftLastWriteTime) )
      {
        v15 = TracePrinter;
        if ( !TracePrinter )
          goto LABEL_7;
        if ( DebugExtPrint )
        {
          LastError = GetLastError();
          TracePrinterExt(L" Failed to enumerate first subkey for %s, GLE = %x\n", lpSubKey[0], LastError);
          goto LABEL_7;
        }
        v16 = GetLastError();
        v17 = L" Failed to enumerate first subkey for %s, GLE = %x\n";
        goto LABEL_17;
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               lpSubKey,
                               L"\\",
                               1)
        || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               lpSubKey,
                               lpName,
                               v28 - lpName) )
      {
        goto LABEL_7;
      }
      v20 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
      if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, lpSubKey[0], 0, 1u, v20) )
      {
LABEL_14:
        v15 = TracePrinter;
        if ( TracePrinter )
        {
          if ( DebugExtPrint )
          {
            v18 = GetLastError();
            TracePrinterExt((wchar_t *)L" Failed to open registry path %s, GLE = %x\n", lpSubKey[0], v18);
            goto LABEL_7;
          }
          v16 = GetLastError();
          v17 = L" Failed to open registry path %s, GLE = %x\n";
LABEL_17:
          v15((unsigned __int16 *)v17, lpSubKey[0], v16);
        }
      }
      else
      {
LABEL_29:
        v21 = hKey;
        v28 = lpName;
        *lpName = 0;
        v25 = v21;
        v26 = 0;
        if ( (int)tlx::_AppendFnImpl<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>,_lambda_01deaffebe426f0eea4c98c3933b105d_>(
                    &lpName,
                    &v25) >= 0 )
        {
          StringCchCopyW(a1, v6, lpName);
          goto LABEL_8;
        }
        v15 = TracePrinter;
        if ( TracePrinter )
        {
          if ( DebugExtPrint )
          {
            v22 = GetLastError();
            TracePrinterExt(L" Failed to query default value for registry path %s, GLE = %x\n", lpSubKey[0], v22);
            goto LABEL_7;
          }
          v16 = GetLastError();
          v17 = L" Failed to query default value for registry path %s, GLE = %x\n";
          goto LABEL_17;
        }
      }
    }
  }
LABEL_7:
  TraceprtGuidToString(a1, v6, a3);
LABEL_8:
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpSubKey);
  return utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&lpName);
}

```

## disassembly

```asm
0x1800cf974  push    rbp
0x1800cf976  push    rbx
0x1800cf977  push    rsi
0x1800cf978  push    rdi
0x1800cf979  push    r12
0x1800cf97b  push    r13
0x1800cf97d  push    r14
0x1800cf97f  push    r15
0x1800cf981  lea     rbp, [rsp-1Fh]
0x1800cf986  sub     rsp, 0B8h
0x1800cf98d  movsxd  rbx, r9d
0x1800cf990  mov     r13, r8
0x1800cf993  mov     r15d, edx
0x1800cf996  mov     r12, rcx
0x1800cf999  lea     rcx, [rbp+57h+lpName]; void *
0x1800cf99d  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800cf9a2  nop
0x1800cf9a3  lea     rcx, [rbp+57h+lpSubKey]; void *
0x1800cf9a7  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800cf9ac  nop
0x1800cf9ad  mov     esi, 101h
0x1800cf9b2  mov     [rbp+57h+hKey], 0
0x1800cf9ba  mov     ecx, ebx
0x1800cf9bc  test    r9d, r9d
0x1800cf9bf  jz      short loc_1800CFA3B
0x1800cf9c1  sub     ecx, 1
0x1800cf9c4  jz      short loc_1800CFA36
0x1800cf9c6  cmp     ecx, 1
0x1800cf9c9  jz      short loc_1800CFA3B
0x1800cf9cb  mov     rax, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x1800cf9d2  test    rax, rax
0x1800cf9d5  jz      short loc_1800CF9EE
0x1800cf9d7  mov     edx, ebx
0x1800cf9d9  lea     rcx, aUnknownGuidTyp; " Unknown GUID_TYPE: %x\n"
0x1800cf9e0  cmp     cs:?DebugExtPrint@@3HA, 0; int DebugExtPrint
0x1800cf9e7  jnz     short loc_1800CFA2E
0x1800cf9e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf9ee  mov     r8, r13; struct _GUID *
0x1800cf9f1  mov     edx, r15d; unsigned int
0x1800cf9f4  mov     rcx, r12; unsigned __int16 *
0x1800cf9f7  call    ?TraceprtGuidToString@@YAPEAGPEAGKPEAU_GUID@@@Z; TraceprtGuidToString(ushort *,ulong,_GUID *)
0x1800cf9fc  nop
0x1800cf9fd  lea     rcx, [rbp+57h+hKey]
0x1800cfa01  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x1800cfa06  nop
0x1800cfa07  lea     rcx, [rbp+57h+lpSubKey]
0x1800cfa0b  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800cfa10  nop
0x1800cfa11  lea     rcx, [rbp+57h+lpName]
0x1800cfa15  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800cfa1a  add     rsp, 0B8h
0x1800cfa21  pop     r15
0x1800cfa23  pop     r14
0x1800cfa25  pop     r13
0x1800cfa27  pop     r12
0x1800cfa29  pop     rdi
0x1800cfa2a  pop     rsi
0x1800cfa2b  pop     rbx
0x1800cfa2c  pop     rbp
0x1800cfa2d  retn
0x1800cfa2e  call    ?TracePrinterExt@@YAKPEBGZZ; TracePrinterExt(ushort const *,...)
0x1800cfa33  nop
0x1800cfa34  jmp     short loc_1800CF9EE
0x1800cfa36  mov     esi, 109h
0x1800cfa3b  mov     rcx, [rbp+57h+lpName]
0x1800cfa3f  mov     [rbp+57h+var_80], rcx
0x1800cfa43  xor     eax, eax
0x1800cfa45  mov     [rcx], ax
0x1800cfa48  mov     rdi, [rbp+57h+var_80]
0x1800cfa4c  sub     rdi, [rbp+57h+lpName]
0x1800cfa50  lea     edx, [rax+24h]
0x1800cfa53  lea     rcx, [rbp+57h+lpName]
0x1800cfa57  call    ??$_GetAppendBuffer@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAPEAGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@_K@Z; tlx::_GetAppendBuffer<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,unsigned __int64)
0x1800cfa5c  mov     r14, rax
0x1800cfa5f  test    rax, rax
0x1800cfa62  jz      short loc_1800CF9EE
0x1800cfa64  mov     rdx, r13
0x1800cfa67  mov     rcx, rax
0x1800cfa6a  call    ??$guid_to_string_lower@G@tlx@@YAXPEAGAEBU_GUID@@_N@Z; tlx::guid_to_string_lower<ushort>(ushort *,_GUID const &,bool)
0x1800cfa6f  xor     ecx, ecx
0x1800cfa71  mov     [r14+48h], cx
0x1800cfa76  sar     rdi, 1
0x1800cfa79  lea     rdx, [rdi+24h]
0x1800cfa7d  lea     rcx, [rbp+57h+lpName]
0x1800cfa81  call    ?_Resize@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAX_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Resize(unsigned __int64)
0x1800cfa86  lea     rax, off_1800E8BC0; "CLSID"
0x1800cfa8d  mov     r9, [rbp+57h+lpName]
0x1800cfa91  mov     r8, [rax+rbx*8]
0x1800cfa95  lea     rdx, aSS_0; "%s\\{%s}"
0x1800cfa9c  lea     rcx, [rbp+57h+lpSubKey]
0x1800cfaa0  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x1800cfaa5  xor     edi, edi
0x1800cfaa7  test    eax, eax
0x1800cfaa9  js      loc_1800CF9EE
0x1800cfaaf  lea     rcx, [rbp+57h+hKey]
0x1800cfab3  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800cfab8  mov     [rsp+0F0h+phkResult], rax; phkResult
0x1800cfabd  mov     r9d, esi; samDesired
0x1800cfac0  xor     r8d, r8d; ulOptions
0x1800cfac3  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1800cfac7  mov     r14, 0FFFFFFFF80000000h
0x1800cface  mov     rcx, r14; hKey
0x1800cfad1  call    cs:__imp_RegOpenKeyExW
0x1800cfad7  test    eax, eax
0x1800cfad9  jz      short loc_1800CFB32
0x1800cfadb  mov     rbx, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x1800cfae2  test    rbx, rbx
0x1800cfae5  jz      loc_1800CF9EE
0x1800cfaeb  cmp     cs:?DebugExtPrint@@3HA, edi; int DebugExtPrint
0x1800cfaf1  jnz     short loc_1800CFB14
0x1800cfaf3  call    cs:__imp_GetLastError
0x1800cfaf9  lea     rcx, aFailedToOpenRe; " Failed to open registry path %s, GLE ="...
0x1800cfb00  mov     r8d, eax
0x1800cfb03  mov     rdx, [rbp+57h+lpSubKey]
0x1800cfb07  mov     rax, rbx
0x1800cfb0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cfb0f  jmp     loc_1800CF9EE
0x1800cfb14  call    cs:__imp_GetLastError
0x1800cfb1a  lea     rcx, aFailedToOpenRe; " Failed to open registry path %s, GLE ="...
0x1800cfb21  mov     r8d, eax
0x1800cfb24  mov     rdx, [rbp+57h+lpSubKey]
0x1800cfb28  call    ?TracePrinterExt@@YAKPEBGZZ; TracePrinterExt(ushort const *,...)
0x1800cfb2d  jmp     loc_1800CF9EE
0x1800cfb32  mov     esi, 1
0x1800cfb37  cmp     ebx, esi
0x1800cfb39  jnz     loc_1800CFC2D
0x1800cfb3f  mov     edx, 0FFh
0x1800cfb44  lea     rcx, [rbp+57h+lpName]
0x1800cfb48  call    ?resize@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_N_KG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::resize(unsigned __int64,ushort)
0x1800cfb4d  mov     rax, [rbp+57h+var_80]
0x1800cfb51  mov     r8, [rbp+57h+lpName]; lpName
0x1800cfb55  sub     rax, r8
0x1800cfb58  sar     rax, 1
0x1800cfb5b  mov     [rbp+57h+cchName], eax
0x1800cfb5e  mov     qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime], rdi
0x1800cfb62  lea     rax, [rbp+57h+ftLastWriteTime]
0x1800cfb66  mov     [rsp+0F0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800cfb6b  mov     [rsp+0F0h+lpcchClass], rdi; lpcchClass
0x1800cfb70  mov     [rsp+0F0h+lpClass], rdi; lpClass
0x1800cfb75  mov     [rsp+0F0h+phkResult], rdi; lpReserved
0x1800cfb7a  lea     r9, [rbp+57h+cchName]; lpcchName
0x1800cfb7e  xor     edx, edx; dwIndex
0x1800cfb80  mov     rcx, [rbp+57h+hKey]; hKey
0x1800cfb84  call    cs:__imp_RegEnumKeyExW
0x1800cfb8a  test    eax, eax
0x1800cfb8c  jz      short loc_1800CFBCA
0x1800cfb8e  mov     rbx, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x1800cfb95  test    rbx, rbx
0x1800cfb98  jz      loc_1800CF9EE
0x1800cfb9e  cmp     cs:?DebugExtPrint@@3HA, edi; int DebugExtPrint
0x1800cfba4  jnz     short loc_1800CFBB8
0x1800cfba6  call    cs:__imp_GetLastError
0x1800cfbac  lea     rcx, aFailedToEnumer; " Failed to enumerate first subkey for %"...
0x1800cfbb3  jmp     loc_1800CFB00
0x1800cfbb8  call    cs:__imp_GetLastError
0x1800cfbbe  lea     rcx, aFailedToEnumer; " Failed to enumerate first subkey for %"...
0x1800cfbc5  jmp     loc_1800CFB21
0x1800cfbca  mov     r8, rsi
0x1800cfbcd  lea     rdx, SubBlock; "\\"
0x1800cfbd4  lea     rcx, [rbp+57h+lpSubKey]
0x1800cfbd8  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800cfbdd  test    al, al
0x1800cfbdf  jz      loc_1800CF9EE
0x1800cfbe5  mov     r8, [rbp+57h+var_80]
0x1800cfbe9  mov     rdx, [rbp+57h+lpName]
0x1800cfbed  sub     r8, rdx
0x1800cfbf0  sar     r8, 1
0x1800cfbf3  lea     rcx, [rbp+57h+lpSubKey]
0x1800cfbf7  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800cfbfc  test    al, al
0x1800cfbfe  jz      loc_1800CF9EE
0x1800cfc04  lea     rcx, [rbp+57h+hKey]
0x1800cfc08  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800cfc0d  mov     [rsp+0F0h+phkResult], rax; phkResult
0x1800cfc12  mov     r9d, esi; samDesired
0x1800cfc15  xor     r8d, r8d; ulOptions
0x1800cfc18  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1800cfc1c  mov     rcx, r14; hKey
0x1800cfc1f  call    cs:__imp_RegOpenKeyExW
0x1800cfc25  test    eax, eax
0x1800cfc27  jnz     loc_1800CFADB
0x1800cfc2d  mov     rdx, [rbp+57h+hKey]
0x1800cfc31  mov     rcx, [rbp+57h+lpName]
0x1800cfc35  mov     [rbp+57h+var_80], rcx
0x1800cfc39  mov     [rcx], di
0x1800cfc3c  mov     [rbp+57h+var_A0], rdx
0x1800cfc40  xorps   xmm0, xmm0
0x1800cfc43  movdqu  [rbp+57h+var_98], xmm0
0x1800cfc48  lea     rdx, [rbp+57h+var_A0]
0x1800cfc4c  lea     rcx, [rbp+57h+lpName]
0x1800cfc50  call    ??$_AppendFnImpl@GU?$char_traits@G@utl@@V?$allocator@G@2@V_lambda_01deaffebe426f0eea4c98c3933b105d_@@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@$$QEAV_lambda_01deaffebe426f0eea4c98c3933b105d_@@@Z; tlx::_AppendFnImpl<ushort,utl::char_traits<ushort>,utl::allocator<ushort>,_lambda_01deaffebe426f0eea4c98c3933b105d_>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,_lambda_01deaffebe426f0eea4c98c3933b105d_ &&)
0x1800cfc55  test    eax, eax
0x1800cfc57  jns     short loc_1800CFC95
0x1800cfc59  mov     rbx, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x1800cfc60  test    rbx, rbx
0x1800cfc63  jz      loc_1800CF9EE
0x1800cfc69  cmp     cs:?DebugExtPrint@@3HA, edi; int DebugExtPrint
0x1800cfc6f  jnz     short loc_1800CFC83
0x1800cfc71  call    cs:__imp_GetLastError
0x1800cfc77  lea     rcx, aFailedToQueryD; " Failed to query default value for regi"...
0x1800cfc7e  jmp     loc_1800CFB00
0x1800cfc83  call    cs:__imp_GetLastError
0x1800cfc89  lea     rcx, aFailedToQueryD; " Failed to query default value for regi"...
0x1800cfc90  jmp     loc_1800CFB21
0x1800cfc95  mov     rdx, r15; unsigned __int64
0x1800cfc98  mov     r8, [rbp+57h+lpName]; unsigned __int16 *
0x1800cfc9c  mov     rcx, r12; unsigned __int16 *
0x1800cfc9f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800cfca4  jmp     loc_1800CF9FD
```
