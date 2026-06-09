# winbio::GetRegPathForSID(_WINBIO_IDENTITY *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180016650`
- end: `0x180016787`
- name: `?GetRegPathForSID@winbio@@YAJPEAU_WINBIO_IDENTITY@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `311`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180016430`
- `0x1800528a0`

## callees

- `0x180011d90`
- `0x180014110`
- `0x18001451c`
- `0x1800148b4`
- `0x180016650`
- `0x180043744`
- `0x18005388c`
- `0x180058504`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001671e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001671e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800166b8`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800166b8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800166fc`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800166fc`

## string_xrefs

- `0x180016682`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`
- `0x180016742`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`
- `0x180016765`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winbio::GetRegPathForSID(_DWORD *a1, __int64 a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rdx
  void *v6; // rsi
  int WinBioRegistryLocation; // eax
  unsigned int v8; // edi
  __int64 v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  LPWSTR StringSid; // [rsp+30h] [rbp+8h] BYREF

  if ( !a1 )
  {
    v3 = -2147467261;
    v4 = 549;
    goto LABEL_5;
  }
  if ( !a2 )
  {
    v3 = -2147467261;
    v4 = 550;
    goto LABEL_5;
  }
  if ( *a1 != 3 || (v6 = a1 + 2, !IsValidSid(a1 + 2)) )
  {
    v3 = -2147024809;
    v4 = 552;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
      (const char *)v3,
      v11);
    return v3;
  }
  WinBioRegistryLocation = GetWinBioRegistryLocation(a2);
  v8 = WinBioRegistryLocation;
  if ( WinBioRegistryLocation < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x229,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
      (const char *)(unsigned int)WinBioRegistryLocation,
      v11);
    return v8;
  }
  v9 = std::_WChar_traits<unsigned short>::length(L"AccountInfo\\");
  std::wstring::_Append<unsigned short>(a2, v10, v9);
  StringSid = 0;
  if ( !ConvertSidToStringSidW(v6, &StringSid) )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x22D,
           (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
           (const char *)1,
           v11);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    return v3;
  }
  std::wstring::append(a2, StringSid);
  if ( StringSid )
    LocalFree(StringSid);
  return 0;
}

```

## disassembly

```asm
0x180016650  mov     [rsp+arg_8], rbx
0x180016655  mov     [rsp+arg_10], rsi
0x18001665a  push    rdi; unsigned int
0x18001665b  sub     rsp, 20h
0x18001665f  mov     rbx, rdx
0x180016662  test    rcx, rcx
0x180016665  jz      short loc_1800166A5
0x180016667  test    rdx, rdx
0x18001666a  jz      loc_18001672B
0x180016670  cmp     dword ptr [rcx], 3
0x180016673  jz      short loc_1800166B1
0x180016675  mov     ebx, 80070057h
0x18001667a  mov     edx, 228h; void *
0x18001667f  mov     r9d, ebx; char *
0x180016682  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\biometrics\\serv"...
0x180016689  mov     rcx, [rsp+28h]; this
0x18001668e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016693  mov     eax, ebx
0x180016695  mov     rbx, [rsp+28h+arg_8]
0x18001669a  mov     rsi, [rsp+28h+arg_10]
0x18001669f  add     rsp, 20h
0x1800166a3  pop     rdi
0x1800166a4  retn
0x1800166a5  mov     ebx, 80004003h
0x1800166aa  mov     edx, 225h
0x1800166af  jmp     short loc_18001667F
0x1800166b1  lea     rsi, [rcx+8]
0x1800166b5  mov     rcx, rsi; pSid
0x1800166b8  call    cs:__imp_IsValidSid
0x1800166be  test    eax, eax
0x1800166c0  jz      short loc_180016675
0x1800166c2  mov     rcx, rbx
0x1800166c5  call    ?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWinBioRegistryLocation(std::wstring *)
0x1800166ca  mov     edi, eax
0x1800166cc  test    eax, eax
0x1800166ce  js      short loc_18001673A
0x1800166d0  lea     rcx, aAccountinfo; "AccountInfo\\"
0x1800166d7  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800166dc  mov     r8, rax
0x1800166df  mov     rdx, rcx
0x1800166e2  mov     rcx, rbx
0x1800166e5  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800166ea  nop
0x1800166eb  mov     [rsp+28h+StringSid], 0
0x1800166f4  lea     rdx, [rsp+28h+StringSid]; StringSid
0x1800166f9  mov     rcx, rsi; Sid
0x1800166fc  call    cs:__imp_ConvertSidToStringSidW
0x180016702  test    eax, eax
0x180016704  jz      short loc_18001675A
0x180016706  mov     rdx, [rsp+28h+StringSid]
0x18001670b  mov     rcx, rbx
0x18001670e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180016713  nop
0x180016714  mov     rcx, [rsp+28h+StringSid]; hMem
0x180016719  test    rcx, rcx
0x18001671c  jz      short loc_180016724
0x18001671e  call    cs:__imp_LocalFree
0x180016724  xor     eax, eax
0x180016726  jmp     loc_180016695
0x18001672b  mov     ebx, 80004003h
0x180016730  mov     edx, 226h
0x180016735  jmp     loc_18001667F
0x18001673a  mov     rcx, [rsp+28h]; this
0x18001673f  mov     r9d, edi; char *
0x180016742  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\biometrics\\serv"...
0x180016749  mov     edx, 229h; void *
0x18001674e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016753  mov     eax, edi
0x180016755  jmp     loc_180016695
0x18001675a  mov     rcx, [rsp+28h]; this
0x18001675f  mov     r9d, 1; char *
0x180016765  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\biometrics\\serv"...
0x18001676c  mov     edx, 22Dh; void *
0x180016771  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180016776  mov     ebx, eax
0x180016778  lea     rcx, [rsp+28h+StringSid]
0x18001677d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016782  jmp     loc_180016693
```
