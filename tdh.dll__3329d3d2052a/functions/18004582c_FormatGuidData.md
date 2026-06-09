# FormatGuidData

- ea: `0x18004582c`
- end: `0x180045b62`
- name: `FormatGuidData`
- size: `822`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, struct _GUID *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x180043390`

## callees

- `0x18000f7d4`
- `0x180012f5c`
- `0x18001305c`
- `0x180018318`
- `0x180018a3c`
- `0x18003eb10`
- `0x18003f4c0`
- `0x180042140`
- `0x1800422ec`
- `0x180042f7c`
- `0x180043078`
- `0x1800431b4`
- `0x1800431ec`
- `0x18004321c`
- `0x18004582c`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800459ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800459cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045a5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045a70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045b29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045b3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800459ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800459cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045a5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045a70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045b29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045b3b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180045a3c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180045a3c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045989`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045ad7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045989`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045ad7`

## string_xrefs

- `0x1800459b1`: ` Failed to open registry path %s, GLE = %x\n`
- `0x1800459d2`: ` Failed to open registry path %s, GLE = %x\n`
- `0x180045b2f`: ` Failed to query default value for registry path %s, GLE = %x\n`
- `0x180045b41`: ` Failed to query default value for registry path %s, GLE = %x\n`

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
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&lpName);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpSubKey);
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
                off_180056500[v4],
                lpName) >= 0 )
    {
      phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
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
      v20 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
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
0x18004582c  push    rbp
0x18004582e  push    rbx
0x18004582f  push    rsi
0x180045830  push    rdi
0x180045831  push    r12
0x180045833  push    r13
0x180045835  push    r14
0x180045837  push    r15
0x180045839  lea     rbp, [rsp-1Fh]
0x18004583e  sub     rsp, 0B8h
0x180045845  movsxd  rbx, r9d
0x180045848  mov     r13, r8
0x18004584b  mov     r15d, edx
0x18004584e  mov     r12, rcx
0x180045851  lea     rcx, [rbp+57h+lpName]
0x180045855  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18004585a  nop
0x18004585b  lea     rcx, [rbp+57h+lpSubKey]
0x18004585f  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180045864  nop
0x180045865  mov     esi, 101h
0x18004586a  mov     [rbp+57h+hKey], 0
0x180045872  mov     ecx, ebx
0x180045874  test    r9d, r9d
0x180045877  jz      short loc_1800458F3
0x180045879  sub     ecx, 1
0x18004587c  jz      short loc_1800458EE
0x18004587e  cmp     ecx, 1
0x180045881  jz      short loc_1800458F3
0x180045883  mov     rax, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x18004588a  test    rax, rax
0x18004588d  jz      short loc_1800458A6
0x18004588f  mov     edx, ebx
0x180045891  lea     rcx, aUnknownGuidTyp; " Unknown GUID_TYPE: %x\n"
0x180045898  cmp     cs:?DebugExtPrint@@3HA, 0; int DebugExtPrint
0x18004589f  jnz     short loc_1800458E6
0x1800458a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800458a6  mov     r8, r13; struct _GUID *
0x1800458a9  mov     edx, r15d; unsigned int
0x1800458ac  mov     rcx, r12; unsigned __int16 *
0x1800458af  call    ?TraceprtGuidToString@@YAPEAGPEAGKPEAU_GUID@@@Z; TraceprtGuidToString(ushort *,ulong,_GUID *)
0x1800458b4  nop
0x1800458b5  lea     rcx, [rbp+57h+hKey]
0x1800458b9  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x1800458be  nop
0x1800458bf  lea     rcx, [rbp+57h+lpSubKey]
0x1800458c3  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800458c8  nop
0x1800458c9  lea     rcx, [rbp+57h+lpName]
0x1800458cd  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800458d2  add     rsp, 0B8h
0x1800458d9  pop     r15
0x1800458db  pop     r14
0x1800458dd  pop     r13
0x1800458df  pop     r12
0x1800458e1  pop     rdi
0x1800458e2  pop     rsi
0x1800458e3  pop     rbx
0x1800458e4  pop     rbp
0x1800458e5  retn
0x1800458e6  call    ?TracePrinterExt@@YAKPEBGZZ; TracePrinterExt(ushort const *,...)
0x1800458eb  nop
0x1800458ec  jmp     short loc_1800458A6
0x1800458ee  mov     esi, 109h
0x1800458f3  mov     rcx, [rbp+57h+lpName]
0x1800458f7  mov     [rbp+57h+var_80], rcx
0x1800458fb  xor     eax, eax
0x1800458fd  mov     [rcx], ax
0x180045900  mov     rdi, [rbp+57h+var_80]
0x180045904  sub     rdi, [rbp+57h+lpName]
0x180045908  lea     edx, [rax+24h]
0x18004590b  lea     rcx, [rbp+57h+lpName]
0x18004590f  call    ??$_GetAppendBuffer@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAPEAGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@_K@Z; tlx::_GetAppendBuffer<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,unsigned __int64)
0x180045914  mov     r14, rax
0x180045917  test    rax, rax
0x18004591a  jz      short loc_1800458A6
0x18004591c  mov     rdx, r13
0x18004591f  mov     rcx, rax
0x180045922  call    ??$guid_to_string_lower@G@tlx@@YAXPEAGAEBU_GUID@@_N@Z; tlx::guid_to_string_lower<ushort>(ushort *,_GUID const &,bool)
0x180045927  xor     ecx, ecx
0x180045929  mov     [r14+48h], cx
0x18004592e  sar     rdi, 1
0x180045931  lea     rdx, [rdi+24h]
0x180045935  lea     rcx, [rbp+57h+lpName]
0x180045939  call    ?_Resize@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAX_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Resize(unsigned __int64)
0x18004593e  lea     rax, off_180056500; "CLSID"
0x180045945  mov     r9, [rbp+57h+lpName]
0x180045949  mov     r8, [rax+rbx*8]
0x18004594d  lea     rdx, aSS_1; "%s\\{%s}"
0x180045954  lea     rcx, [rbp+57h+lpSubKey]
0x180045958  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x18004595d  xor     edi, edi
0x18004595f  test    eax, eax
0x180045961  js      loc_1800458A6
0x180045967  lea     rcx, [rbp+57h+hKey]
0x18004596b  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180045970  mov     [rsp+0F0h+phkResult], rax; phkResult
0x180045975  mov     r9d, esi; samDesired
0x180045978  xor     r8d, r8d; ulOptions
0x18004597b  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18004597f  mov     r14, 0FFFFFFFF80000000h
0x180045986  mov     rcx, r14; hKey
0x180045989  call    cs:__imp_RegOpenKeyExW
0x18004598f  test    eax, eax
0x180045991  jz      short loc_1800459EA
0x180045993  mov     rbx, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x18004599a  test    rbx, rbx
0x18004599d  jz      loc_1800458A6
0x1800459a3  cmp     cs:?DebugExtPrint@@3HA, edi; int DebugExtPrint
0x1800459a9  jnz     short loc_1800459CC
0x1800459ab  call    cs:__imp_GetLastError
0x1800459b1  lea     rcx, aFailedToOpenRe; " Failed to open registry path %s, GLE ="...
0x1800459b8  mov     r8d, eax
0x1800459bb  mov     rdx, [rbp+57h+lpSubKey]
0x1800459bf  mov     rax, rbx
0x1800459c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800459c7  jmp     loc_1800458A6
0x1800459cc  call    cs:__imp_GetLastError
0x1800459d2  lea     rcx, aFailedToOpenRe; " Failed to open registry path %s, GLE ="...
0x1800459d9  mov     r8d, eax
0x1800459dc  mov     rdx, [rbp+57h+lpSubKey]
0x1800459e0  call    ?TracePrinterExt@@YAKPEBGZZ; TracePrinterExt(ushort const *,...)
0x1800459e5  jmp     loc_1800458A6
0x1800459ea  mov     esi, 1
0x1800459ef  cmp     ebx, esi
0x1800459f1  jnz     loc_180045AE5
0x1800459f7  mov     edx, 0FFh
0x1800459fc  lea     rcx, [rbp+57h+lpName]
0x180045a00  call    ?resize@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_N_KG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::resize(unsigned __int64,ushort)
0x180045a05  mov     rax, [rbp+57h+var_80]
0x180045a09  mov     r8, [rbp+57h+lpName]; lpName
0x180045a0d  sub     rax, r8
0x180045a10  sar     rax, 1
0x180045a13  mov     [rbp+57h+cchName], eax
0x180045a16  mov     qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime], rdi
0x180045a1a  lea     rax, [rbp+57h+ftLastWriteTime]
0x180045a1e  mov     [rsp+0F0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180045a23  mov     [rsp+0F0h+lpcchClass], rdi; lpcchClass
0x180045a28  mov     [rsp+0F0h+lpClass], rdi; lpClass
0x180045a2d  mov     [rsp+0F0h+phkResult], rdi; lpReserved
0x180045a32  lea     r9, [rbp+57h+cchName]; lpcchName
0x180045a36  xor     edx, edx; dwIndex
0x180045a38  mov     rcx, [rbp+57h+hKey]; hKey
0x180045a3c  call    cs:__imp_RegEnumKeyExW
0x180045a42  test    eax, eax
0x180045a44  jz      short loc_180045A82
0x180045a46  mov     rbx, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x180045a4d  test    rbx, rbx
0x180045a50  jz      loc_1800458A6
0x180045a56  cmp     cs:?DebugExtPrint@@3HA, edi; int DebugExtPrint
0x180045a5c  jnz     short loc_180045A70
0x180045a5e  call    cs:__imp_GetLastError
0x180045a64  lea     rcx, aFailedToEnumer; " Failed to enumerate first subkey for %"...
0x180045a6b  jmp     loc_1800459B8
0x180045a70  call    cs:__imp_GetLastError
0x180045a76  lea     rcx, aFailedToEnumer; " Failed to enumerate first subkey for %"...
0x180045a7d  jmp     loc_1800459D9
0x180045a82  mov     r8, rsi
0x180045a85  lea     rdx, asc_180057D4C; "\\"
0x180045a8c  lea     rcx, [rbp+57h+lpSubKey]
0x180045a90  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180045a95  test    al, al
0x180045a97  jz      loc_1800458A6
0x180045a9d  mov     r8, [rbp+57h+var_80]
0x180045aa1  mov     rdx, [rbp+57h+lpName]
0x180045aa5  sub     r8, rdx
0x180045aa8  sar     r8, 1
0x180045aab  lea     rcx, [rbp+57h+lpSubKey]
0x180045aaf  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180045ab4  test    al, al
0x180045ab6  jz      loc_1800458A6
0x180045abc  lea     rcx, [rbp+57h+hKey]
0x180045ac0  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180045ac5  mov     [rsp+0F0h+phkResult], rax; phkResult
0x180045aca  mov     r9d, esi; samDesired
0x180045acd  xor     r8d, r8d; ulOptions
0x180045ad0  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180045ad4  mov     rcx, r14; hKey
0x180045ad7  call    cs:__imp_RegOpenKeyExW
0x180045add  test    eax, eax
0x180045adf  jnz     loc_180045993
0x180045ae5  mov     rdx, [rbp+57h+hKey]
0x180045ae9  mov     rcx, [rbp+57h+lpName]
0x180045aed  mov     [rbp+57h+var_80], rcx
0x180045af1  mov     [rcx], di
0x180045af4  mov     [rbp+57h+var_A0], rdx
0x180045af8  xorps   xmm0, xmm0
0x180045afb  movdqu  [rbp+57h+var_98], xmm0
0x180045b00  lea     rdx, [rbp+57h+var_A0]
0x180045b04  lea     rcx, [rbp+57h+lpName]
0x180045b08  call    ??$_AppendFnImpl@GU?$char_traits@G@utl@@V?$allocator@G@2@V_lambda_01deaffebe426f0eea4c98c3933b105d_@@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@$$QEAV_lambda_01deaffebe426f0eea4c98c3933b105d_@@@Z; tlx::_AppendFnImpl<ushort,utl::char_traits<ushort>,utl::allocator<ushort>,_lambda_01deaffebe426f0eea4c98c3933b105d_>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,_lambda_01deaffebe426f0eea4c98c3933b105d_ &&)
0x180045b0d  test    eax, eax
0x180045b0f  jns     short loc_180045B4D
0x180045b11  mov     rbx, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x180045b18  test    rbx, rbx
0x180045b1b  jz      loc_1800458A6
0x180045b21  cmp     cs:?DebugExtPrint@@3HA, edi; int DebugExtPrint
0x180045b27  jnz     short loc_180045B3B
0x180045b29  call    cs:__imp_GetLastError
0x180045b2f  lea     rcx, aFailedToQueryD; " Failed to query default value for regi"...
0x180045b36  jmp     loc_1800459B8
0x180045b3b  call    cs:__imp_GetLastError
0x180045b41  lea     rcx, aFailedToQueryD; " Failed to query default value for regi"...
0x180045b48  jmp     loc_1800459D9
0x180045b4d  mov     rdx, r15; unsigned __int64
0x180045b50  mov     r8, [rbp+57h+lpName]; unsigned __int16 *
0x180045b54  mov     rcx, r12; unsigned __int16 *
0x180045b57  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180045b5c  jmp     loc_1800458B5
```
