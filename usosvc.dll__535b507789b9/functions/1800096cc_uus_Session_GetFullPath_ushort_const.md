# uus::Session::GetFullPath(ushort const *)

- ea: `0x1800096cc`
- end: `0x1800097f6`
- name: `?GetFullPath@Session@uus@@QEBA?AVpath@filesystem@std@@PEBG@Z`
- size: `298`
- prototype: `void *__fastcall(__int64, void *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180009bf0`
- `0x18000c0b0`

## callees

- `0x1800026d0`
- `0x180006b28`
- `0x1800074ac`
- `0x180008b08`
- `0x180008c74`
- `0x1800096cc`
- `0x1800097fc`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009791`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009791`

## string_xrefs

- `0x1800096fa`: `UsoSvcImpl.dll`

## pseudocode

```c
void *__fastcall uus::Session::GetFullPath(__int64 a1, void *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rcx
  LPVOID pv[2]; // [rsp+20h] [rbp-49h] BYREF
  const wchar_t *v10; // [rsp+30h] [rbp-39h]
  __int64 v11; // [rsp+38h] [rbp-31h]
  _BYTE v12[32]; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v13[32]; // [rsp+68h] [rbp-1h] BYREF
  _BYTE v14[32]; // [rsp+88h] [rbp+1Fh] BYREF

  pv[0] = a2;
  v10 = L"UsoSvcImpl.dll";
  v11 = 14;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v14);
  v4 = *(_QWORD *)(a1 + 8);
  if ( v4 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 40LL))(v4, 1);
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(v5 + 2 * v6) );
    v10 = (const wchar_t *)v5;
    v11 = v6;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v12);
  }
  else
  {
    wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(pv);
    v7 = -1;
    do
      ++v7;
    while ( *((_WORD *)pv[0] + v7) );
    v10 = (const wchar_t *)pv[0];
    v11 = v7;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v13);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    uus::Utility::GetGuestOrNativeArchFolder(v12, v13);
    std::wstring::~wstring(v13);
  }
  std::filesystem::operator/(a2, (struct std::filesystem::path *)v12, (std::filesystem *)v14);
  std::wstring::~wstring(v12);
  std::wstring::~wstring(v14);
  return a2;
}

```

## disassembly

```asm
0x1800096cc  mov     [rsp-8+arg_10], rbx
0x1800096d1  push    rbp
0x1800096d2  push    rsi
0x1800096d3  push    rdi
0x1800096d4  lea     rbp, [rsp-47h]
0x1800096d9  sub     rsp, 0B0h
0x1800096e0  mov     rax, cs:__security_cookie
0x1800096e7  xor     rax, rsp
0x1800096ea  mov     [rbp+57h+var_18], rax
0x1800096ee  mov     rdi, rdx
0x1800096f1  mov     rbx, rcx
0x1800096f4  mov     [rbp+57h+pv], rdx
0x1800096f8  xor     esi, esi
0x1800096fa  lea     rax, aUsosvcimplDll; "UsoSvcImpl.dll"
0x180009701  mov     [rbp+57h+var_90], rax
0x180009705  mov     [rbp+57h+var_88], 0Eh
0x18000970d  lea     rdx, [rbp+57h+var_90]
0x180009711  lea     rcx, [rbp+57h+var_38]; void *
0x180009715  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x18000971a  nop
0x18000971b  mov     rcx, [rbx+8]
0x18000971f  test    rcx, rcx
0x180009722  jz      short loc_180009757
0x180009724  mov     rax, [rcx]
0x180009727  lea     edx, [rsi+1]
0x18000972a  mov     rax, [rax+28h]
0x18000972e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009733  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180009737  inc     rcx
0x18000973a  cmp     [rax+rcx*2], si
0x18000973e  jnz     short loc_180009737
0x180009740  mov     [rbp+57h+var_90], rax
0x180009744  mov     [rbp+57h+var_88], rcx
0x180009748  lea     rdx, [rbp+57h+var_90]
0x18000974c  lea     rcx, [rbp+57h+var_78]; void *
0x180009750  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x180009755  jmp     short loc_1800097B0
0x180009757  lea     rcx, [rbp+57h+pv]
0x18000975b  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *)
0x180009760  nop
0x180009761  mov     rax, [rbp+57h+pv]
0x180009765  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180009769  inc     rcx
0x18000976c  cmp     [rax+rcx*2], si
0x180009770  jnz     short loc_180009769
0x180009772  mov     [rbp+57h+var_90], rax
0x180009776  mov     [rbp+57h+var_88], rcx
0x18000977a  lea     rdx, [rbp+57h+var_90]
0x18000977e  lea     rcx, [rbp+57h+var_58]; void *
0x180009782  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x180009787  nop
0x180009788  mov     rcx, [rbp+57h+pv]; pv
0x18000978c  test    rcx, rcx
0x18000978f  jz      short loc_180009798
0x180009791  call    cs:__imp_CoTaskMemFree
0x180009797  nop
0x180009798  lea     rdx, [rbp+57h+var_58]
0x18000979c  lea     rcx, [rbp+57h+var_78]
0x1800097a0  call    ?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z; uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)
0x1800097a5  nop
0x1800097a6  lea     rcx, [rbp+57h+var_58]
0x1800097aa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800097af  nop
0x1800097b0  lea     r8, [rbp+57h+var_38]; this
0x1800097b4  lea     rdx, [rbp+57h+var_78]; struct std::filesystem::path *
0x1800097b8  mov     rcx, rdi; Src
0x1800097bb  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x1800097c0  nop
0x1800097c1  lea     rcx, [rbp+57h+var_78]
0x1800097c5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800097ca  nop
0x1800097cb  lea     rcx, [rbp+57h+var_38]
0x1800097cf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800097d4  mov     rax, rdi
0x1800097d7  mov     rcx, [rbp+57h+var_18]
0x1800097db  xor     rcx, rsp; StackCookie
0x1800097de  call    __security_check_cookie
0x1800097e3  mov     rbx, [rsp+0C0h+arg_10]
0x1800097eb  add     rsp, 0B0h
0x1800097f2  pop     rdi
0x1800097f3  pop     rsi
0x1800097f4  pop     rbp
0x1800097f5  retn
```
