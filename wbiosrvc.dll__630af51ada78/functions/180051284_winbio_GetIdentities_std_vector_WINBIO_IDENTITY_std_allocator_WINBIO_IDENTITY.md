# winbio::GetIdentities(std::vector<_WINBIO_IDENTITY *,std::allocator<_WINBIO_IDENTITY *>> *)

- ea: `0x180051284`
- end: `0x1800515bf`
- name: `?GetIdentities@winbio@@YAJPEAV?$vector@PEAU_WINBIO_IDENTITY@@V?$allocator@PEAU_WINBIO_IDENTITY@@@std@@@std@@@Z`
- size: `827`
- prototype: ``
- caller_count: `5`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180044e74`
- `0x1800528a0`
- `0x180063224`
- `0x18007330c`
- `0x180073538`

## callees

- `0x180014110`
- `0x18001451c`
- `0x180014854`
- `0x180014894`
- `0x180035d78`
- `0x18003c468`
- `0x18003cff0`
- `0x18003f2dc`
- `0x1800488d0`
- `0x180051284`
- `0x180068f60`
- `0x180069cc8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800514bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800514f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800514bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800514f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005155c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051572`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005155c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051572`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005158e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005158e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18005140f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18005140f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005134b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005134b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180051457`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180051457`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800514e8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800514e8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180051510`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180051510`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800514a7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800514a7`

## string_xrefs

- `0x1800512e3`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`
- `0x18005135f`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall winbio::GetIdentities(__int64 a1)
{
  int WinBioRegistryLocation; // eax
  const WCHAR *v3; // rax
  PHKEY phkResult; // r9
  LSTATUS Key; // eax
  signed int v6; // edi
  DWORD i; // esi
  BOOL v8; // ebx
  signed int LastError; // eax
  signed int v10; // eax
  DWORD LengthSid; // eax
  HLOCAL v12; // rax
  _QWORD *v13; // rdx
  PSID v14; // rcx
  HLOCAL v15; // rcx
  int dwOptions; // [rsp+20h] [rbp-E0h]
  int dwOptionsa; // [rsp+20h] [rbp-E0h]
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-98h] BYREF
  PSID pSourceSid; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+80h] [rbp-80h] BYREF
  DWORD cbMaxValueLen; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD cbMaxValueNameLen; // [rsp+88h] [rbp-78h] BYREF
  DWORD cValues; // [rsp+8Ch] [rbp-74h] BYREF
  DWORD cbMaxClassLen; // [rsp+90h] [rbp-70h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+94h] [rbp-6Ch] BYREF
  DWORD cchClass; // [rsp+98h] [rbp-68h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+A0h] [rbp-60h] BYREF
  HLOCAL v32; // [rsp+A8h] [rbp-58h] BYREF
  PSID *p_pSourceSid; // [rsp+B0h] [rbp-50h] BYREF
  PSID Sid; // [rsp+B8h] [rbp-48h] BYREF
  char v35; // [rsp+C0h] [rbp-40h]
  _OWORD v36[2]; // [rsp+C8h] [rbp-38h] BYREF
  WCHAR Class; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v38[526]; // [rsp+F2h] [rbp-Eh] BYREF
  WCHAR Name[256]; // [rsp+300h] [rbp+200h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+548h] [rbp+448h]

  v36[0] = 0;
  v36[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v36[0]) = 0;
  WinBioRegistryLocation = GetWinBioRegistryLocation((__int64)v36);
  if ( WinBioRegistryLocation < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xA4,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
      (const char *)(unsigned int)WinBioRegistryLocation,
      dwOptions);
  std::wstring::append(v36, L"AccountInfo\\");
  hKey = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v36);
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
  if ( Key < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xA7,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
      (const char *)(unsigned int)Key,
      dwOptionsa);
  cchName = 0;
  Class = 0;
  memset_0(v38, 0, 0x206u);
  cchClass = 260;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cbMaxClassLen = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  cbSecurityDescriptor = 0;
  ftLastWriteTime = 0;
  v6 = 0;
  RegQueryInfoKeyW(
    hKey,
    &Class,
    &cchClass,
    0,
    &cSubKeys,
    &cbMaxSubKeyLen,
    &cbMaxClassLen,
    &cValues,
    &cbMaxValueNameLen,
    &cbMaxValueLen,
    &cbSecurityDescriptor,
    &ftLastWriteTime);
  if ( cSubKeys )
  {
    for ( i = 0; i < cSubKeys; ++i )
    {
      cchName = 255;
      if ( !RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, &ftLastWriteTime) && cchName > 9 )
      {
        wil::make_unique_hlocal<_WINBIO_IDENTITY,>(&hMem);
        *(_DWORD *)hMem = 3;
        pSourceSid = 0;
        p_pSourceSid = &pSourceSid;
        Sid = 0;
        v35 = 1;
        v8 = ConvertStringSidToSidW(Name, &Sid);
        wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_pSourceSid);
        if ( v8 )
        {
          LastError = GetLastError();
          v6 = LastError;
          if ( LastError > 0 )
            v6 = (unsigned __int16)LastError | 0x80070000;
        }
        if ( v6 >= 0 )
        {
          if ( CopySid(0x44u, (char *)hMem + 8, pSourceSid) )
            goto LABEL_17;
          v10 = GetLastError();
          v6 = v10;
          if ( v10 > 0 )
            v6 = (unsigned __int16)v10 | 0x80070000;
          if ( v6 >= 0 )
          {
LABEL_17:
            LengthSid = GetLengthSid(pSourceSid);
            *((_DWORD *)hMem + 1) = LengthSid;
            v12 = hMem;
            hMem = 0;
            v32 = v12;
            v13 = *(_QWORD **)(a1 + 8);
            if ( v13 == *(_QWORD **)(a1 + 16) )
            {
              std::vector<_WINBIO_IDENTITY *>::_Emplace_reallocate<_WINBIO_IDENTITY * const &>(a1, v13, &v32);
            }
            else
            {
              *v13 = v12;
              *(_QWORD *)(a1 + 8) += 8LL;
            }
          }
        }
        v14 = pSourceSid;
        pSourceSid = 0;
        if ( v14 )
          LocalFree(v14);
        v15 = hMem;
        hMem = 0;
        if ( v15 )
          LocalFree(v15);
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::_Tidy_deallocate(v36);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180051284  push    rbp
0x180051286  push    rbx
0x180051287  push    rsi
0x180051288  push    rdi
0x180051289  push    r14
0x18005128b  push    r15
0x18005128d  lea     rbp, [rsp-418h]
0x180051295  sub     rsp, 518h
0x18005129c  mov     rax, cs:__security_cookie
0x1800512a3  xor     rax, rsp
0x1800512a6  mov     [rbp+440h+var_40], rax
0x1800512ad  mov     r14, rcx
0x1800512b0  xorps   xmm0, xmm0
0x1800512b3  movups  [rbp+440h+var_478], xmm0
0x1800512b7  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800512bf  movdqu  [rbp+440h+var_468], xmm1
0x1800512c4  xor     r15d, r15d
0x1800512c7  mov     word ptr [rbp+440h+var_478], r15w
0x1800512cc  lea     rcx, [rbp+440h+var_478]
0x1800512d0  call    ?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWinBioRegistryLocation(std::wstring *)
0x1800512d5  mov     rcx, [rbp+448h]; this
0x1800512dc  test    eax, eax
0x1800512de  jns     short loc_1800512F4
0x1800512e0  mov     r9d, eax; char *
0x1800512e3  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\biometrics\\serv"...
0x1800512ea  mov     edx, 0A4h; void *
0x1800512ef  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800512f4  lea     rdx, aAccountinfo; "AccountInfo\\"
0x1800512fb  lea     rcx, [rbp+440h+var_478]
0x1800512ff  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180051304  mov     [rsp+540h+hKey], r15
0x180051309  lea     rcx, [rsp+540h+hKey]
0x18005130e  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180051313  mov     r9, rax
0x180051316  lea     rcx, [rbp+440h+var_478]
0x18005131a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005131f  mov     rdx, rax; lpSubKey
0x180051322  mov     [rsp+540h+lpdwDisposition], r15; lpdwDisposition
0x180051327  mov     [rsp+540h+phkResult], r9; phkResult
0x18005132c  mov     [rsp+540h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180051331  mov     [rsp+540h+samDesired], 0F003Fh; samDesired
0x180051339  mov     [rsp+540h+dwOptions], r15d; int
0x18005133e  xor     r9d, r9d; lpClass
0x180051341  xor     r8d, r8d; Reserved
0x180051344  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005134b  call    cs:__imp_RegCreateKeyExW
0x180051351  mov     rcx, [rbp+448h]; this
0x180051358  test    eax, eax
0x18005135a  jns     short loc_180051370
0x18005135c  mov     r9d, eax; char *
0x18005135f  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\biometrics\\serv"...
0x180051366  mov     edx, 0A7h; void *
0x18005136b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180051370  mov     [rsp+540h+cchName], r15d
0x180051375  mov     [rbp+440h+Class], r15w
0x18005137a  xor     edx, edx; Val
0x18005137c  mov     r8d, 206h; Size
0x180051382  lea     rcx, [rbp+440h+var_44E]; void *
0x180051386  call    memset_0
0x18005138b  mov     [rbp+440h+cchClass], 104h
0x180051392  mov     [rsp+540h+cSubKeys], r15d
0x180051397  mov     [rbp+440h+cbMaxSubKeyLen], r15d
0x18005139b  mov     [rbp+440h+cbMaxClassLen], r15d
0x18005139f  mov     [rbp+440h+cValues], r15d
0x1800513a3  mov     [rbp+440h+cbMaxValueNameLen], r15d
0x1800513a7  mov     [rbp+440h+cbMaxValueLen], r15d
0x1800513ab  mov     [rbp+440h+cbSecurityDescriptor], r15d
0x1800513af  mov     qword ptr [rbp+440h+ftLastWriteTime.dwLowDateTime], r15
0x1800513b3  mov     edi, r15d
0x1800513b6  lea     rax, [rbp+440h+ftLastWriteTime]
0x1800513ba  mov     [rsp+540h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800513bf  lea     rax, [rbp+440h+cbSecurityDescriptor]
0x1800513c3  mov     [rsp+540h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x1800513c8  lea     rax, [rbp+440h+cbMaxValueLen]
0x1800513cc  mov     [rsp+540h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800513d1  lea     rax, [rbp+440h+cbMaxValueNameLen]
0x1800513d5  mov     [rsp+540h+lpdwDisposition], rax; lpcbMaxValueNameLen
0x1800513da  lea     rax, [rbp+440h+cValues]
0x1800513de  mov     [rsp+540h+phkResult], rax; lpcValues
0x1800513e3  lea     rax, [rbp+440h+cbMaxClassLen]
0x1800513e7  mov     [rsp+540h+lpSecurityAttributes], rax; lpcbMaxClassLen
0x1800513ec  lea     rax, [rbp+440h+cbMaxSubKeyLen]
0x1800513f0  mov     qword ptr [rsp+540h+samDesired], rax; lpcbMaxSubKeyLen
0x1800513f5  lea     rax, [rsp+540h+cSubKeys]
0x1800513fa  mov     qword ptr [rsp+540h+dwOptions], rax; lpcSubKeys
0x1800513ff  xor     r9d, r9d; lpReserved
0x180051402  lea     r8, [rbp+440h+cchClass]; lpcchClass
0x180051406  lea     rdx, [rbp+440h+Class]; lpClass
0x18005140a  mov     rcx, [rsp+540h+hKey]; hKey
0x18005140f  call    cs:__imp_RegQueryInfoKeyW
0x180051415  mov     eax, [rsp+540h+cSubKeys]
0x180051419  test    eax, eax
0x18005141b  jz      loc_180051584
0x180051421  mov     esi, r15d
0x180051424  mov     [rsp+540h+cchName], 0FFh
0x18005142c  lea     rax, [rbp+440h+ftLastWriteTime]
0x180051430  mov     [rsp+540h+phkResult], rax; lpftLastWriteTime
0x180051435  mov     [rsp+540h+lpSecurityAttributes], r15; lpcchClass
0x18005143a  mov     qword ptr [rsp+540h+samDesired], r15; lpClass
0x18005143f  mov     qword ptr [rsp+540h+dwOptions], r15; lpReserved
0x180051444  lea     r9, [rsp+540h+cchName]; lpcchName
0x180051449  lea     r8, [rbp+440h+Name]; lpName
0x180051450  mov     edx, esi; dwIndex
0x180051452  mov     rcx, [rsp+540h+hKey]; hKey
0x180051457  call    cs:__imp_RegEnumKeyExW
0x18005145d  test    eax, eax
0x18005145f  jnz     loc_180051578
0x180051465  cmp     [rsp+540h+cchName], 9
0x18005146a  jbe     loc_180051578
0x180051470  lea     rcx, [rsp+540h+hMem]
0x180051475  call    ??$make_unique_hlocal@U_WINBIO_IDENTITY@@$$V@wil@@YA?AV?$unique_ptr@U_WINBIO_IDENTITY@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@XZ; wil::make_unique_hlocal<_WINBIO_IDENTITY,>(void)
0x18005147a  nop
0x18005147b  mov     rax, [rsp+540h+hMem]
0x180051480  mov     dword ptr [rax], 3
0x180051486  mov     [rsp+540h+pSourceSid], r15
0x18005148b  lea     rax, [rsp+540h+pSourceSid]
0x180051490  mov     [rbp+440h+var_490], rax
0x180051494  mov     [rbp+440h+Sid], r15
0x180051498  mov     [rbp+440h+var_480], 1
0x18005149c  lea     rdx, [rbp+440h+Sid]; Sid
0x1800514a0  lea     rcx, [rbp+440h+Name]; StringSid
0x1800514a7  call    cs:__imp_ConvertStringSidToSidW
0x1800514ad  mov     ebx, eax
0x1800514af  lea     rcx, [rbp+440h+var_490]
0x1800514b3  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800514b8  test    ebx, ebx
0x1800514ba  jz      short loc_1800514D1
0x1800514bc  call    cs:__imp_GetLastError
0x1800514c2  mov     edi, eax
0x1800514c4  test    eax, eax
0x1800514c6  jle     short loc_1800514D1
0x1800514c8  movzx   edi, ax
0x1800514cb  or      edi, 80070000h
0x1800514d1  test    edi, edi
0x1800514d3  js      short loc_18005154D
0x1800514d5  mov     rdx, [rsp+540h+hMem]
0x1800514da  add     rdx, 8; pDestinationSid
0x1800514de  mov     r8, [rsp+540h+pSourceSid]; pSourceSid
0x1800514e3  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x1800514e8  call    cs:__imp_CopySid
0x1800514ee  test    eax, eax
0x1800514f0  jnz     short loc_18005150B
0x1800514f2  call    cs:__imp_GetLastError
0x1800514f8  mov     edi, eax
0x1800514fa  test    eax, eax
0x1800514fc  jle     short loc_180051507
0x1800514fe  movzx   edi, ax
0x180051501  or      edi, 80070000h
0x180051507  test    edi, edi
0x180051509  js      short loc_18005154D
0x18005150b  mov     rcx, [rsp+540h+pSourceSid]; pSid
0x180051510  call    cs:__imp_GetLengthSid
0x180051516  mov     rcx, [rsp+540h+hMem]
0x18005151b  mov     [rcx+4], eax
0x18005151e  mov     rax, [rsp+540h+hMem]
0x180051523  mov     [rsp+540h+hMem], r15
0x180051528  mov     [rbp+440h+var_498], rax
0x18005152c  mov     rdx, [r14+8]
0x180051530  cmp     rdx, [r14+10h]
0x180051534  jz      short loc_180051540
0x180051536  mov     [rdx], rax
0x180051539  add     qword ptr [r14+8], 8
0x18005153e  jmp     short loc_18005154D
0x180051540  lea     r8, [rbp+440h+var_498]
0x180051544  mov     rcx, r14
0x180051547  call    ??$_Emplace_reallocate@AEBQEAU_WINBIO_IDENTITY@@@?$vector@PEAU_WINBIO_IDENTITY@@V?$allocator@PEAU_WINBIO_IDENTITY@@@std@@@std@@AEAAPEAPEAU_WINBIO_IDENTITY@@QEAPEAU2@AEBQEAU2@@Z; std::vector<_WINBIO_IDENTITY *>::_Emplace_reallocate<_WINBIO_IDENTITY * const &>(_WINBIO_IDENTITY * * const,_WINBIO_IDENTITY * const &)
0x18005154c  nop
0x18005154d  mov     rcx, [rsp+540h+pSourceSid]; hMem
0x180051552  mov     [rsp+540h+pSourceSid], r15
0x180051557  test    rcx, rcx
0x18005155a  jz      short loc_180051563
0x18005155c  call    cs:__imp_LocalFree
0x180051562  nop
0x180051563  mov     rcx, [rsp+540h+hMem]; hMem
0x180051568  mov     [rsp+540h+hMem], r15
0x18005156d  test    rcx, rcx
0x180051570  jz      short loc_180051578
0x180051572  call    cs:__imp_LocalFree
0x180051578  inc     esi
0x18005157a  cmp     esi, [rsp+540h+cSubKeys]
0x18005157e  jb      loc_180051424
0x180051584  mov     rcx, [rsp+540h+hKey]; hKey
0x180051589  test    rcx, rcx
0x18005158c  jz      short loc_180051595
0x18005158e  call    cs:__imp_RegCloseKey
0x180051594  nop
0x180051595  lea     rcx, [rbp+440h+var_478]
0x180051599  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005159e  mov     eax, edi
0x1800515a0  mov     rcx, [rbp+440h+var_40]
0x1800515a7  xor     rcx, rsp; StackCookie
0x1800515aa  call    __security_check_cookie
0x1800515af  add     rsp, 518h
0x1800515b6  pop     r15
0x1800515b8  pop     r14
0x1800515ba  pop     rdi
0x1800515bb  pop     rsi
0x1800515bc  pop     rbx
0x1800515bd  pop     rbp
0x1800515be  retn
```
