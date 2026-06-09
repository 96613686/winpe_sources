# NotificationServiceImpl::HandleDeviceVersionVariation(char *)

- ea: `0x18006e2b0`
- end: `0x18006e523`
- name: `?HandleDeviceVersionVariation@NotificationServiceImpl@@AEAAJPEAD@Z`
- size: `627`
- prototype: `__int64 __fastcall(NotificationServiceImpl *__hidden this, char *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180070300`

## callees

- `0x180001afc`
- `0x1800055c4`
- `0x180007440`
- `0x180007464`
- `0x18000d06c`
- `0x18000fe0c`
- `0x18001d108`
- `0x180033910`
- `0x180045438`
- `0x18006a734`
- `0x18006e2b0`
- `0x180074998`
- `0x180075334`
- `0x1800758a4`
- `0x180084ac8`
- `0x180084cf0`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18006e2f1`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18006e2f1`
- `msvcp_win!??0?$codecvt@GDU_Mbstatet@@@std@@QEAA@_K@Z` at `0x18006e378`
- `msvcp_win!??0?$codecvt@GDU_Mbstatet@@@std@@QEAA@_K@Z` at `0x18006e378`

## string_xrefs

- `0x18006e510`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`

## pseudocode

```c
__int64 __fastcall NotificationServiceImpl::HandleDeviceVersionVariation(NotificationServiceImpl *this, char *a2)
{
  _QWORD *v3; // rbx
  __int64 v4; // rax
  int DeviceIdFromRegistry; // eax
  unsigned int v6; // ebx
  const unsigned __int16 *v7; // rdx
  NotificationServiceImpl *v8; // rcx
  __int64 v9; // rax
  char *v10; // r9
  int v11; // edx
  int v12; // ecx
  unsigned __int64 v13; // r8
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  const unsigned __int16 *v17; // rax
  NotificationServiceImpl *v18; // rcx
  unsigned __int64 v19; // r8
  const char *v20; // r9
  __int64 result; // rax
  int v22; // [rsp+20h] [rbp-E8h]
  unsigned __int16 *v23; // [rsp+30h] [rbp-D8h] BYREF
  unsigned __int64 v24; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE v26[40]; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v27[4]; // [rsp+70h] [rbp-98h] BYREF
  __int128 v28; // [rsp+90h] [rbp-78h]
  __int64 v29; // [rsp+A0h] [rbp-68h]
  __int64 v30; // [rsp+A8h] [rbp-60h]
  __int128 v31; // [rsp+B0h] [rbp-58h]
  __int64 v32; // [rsp+C0h] [rbp-48h]
  __int64 v33; // [rsp+C8h] [rbp-40h]
  __int16 v34; // [rsp+D8h] [rbp-30h]
  char v35; // [rsp+DAh] [rbp-2Eh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  try
  {
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD40,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)0x80070057LL,
        v22);
    v27[0] = &std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
    v27[3] = std::locale::_Init(1);
    v28 = 0;
    v29 = 0;
    v30 = 15;
    LOBYTE(v28) = 0;
    v31 = 0;
    v32 = 0;
    v33 = 7;
    LOWORD(v31) = 0;
    v34 = 0;
    v35 = 0;
    v3 = operator new(0x40u);
    v25 = (__int64)v3;
    std::codecvt<unsigned short,char,_Mbstatet>::codecvt<unsigned short,char,_Mbstatet>(v3, 0);
    *v3 = &std::codecvt_utf8_utf16<unsigned short,1114111,0>::`vftable';
    std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::_Init(
      v27,
      v3);
    v4 = -1;
    do
      ++v4;
    while ( a2[v4] );
    std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::from_bytes(
      v27,
      v26,
      a2,
      &a2[v4]);
    v23 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v23,
      0);
    DeviceIdFromRegistry = WpnGetDeviceIdFromRegistry(&v23);
    v6 = DeviceIdFromRegistry;
    if ( DeviceIdFromRegistry == -2147023728 )
    {
      v7 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
      NotificationServiceImpl::SendEventAndUpdateRegistryDeviceValues(v8, v7, 1u);
      v6 = 0;
    }
    else if ( DeviceIdFromRegistry >= 0 )
    {
      v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
      v10 = (char *)v23 - v9;
      do
      {
        v11 = *(unsigned __int16 *)&v10[v9];
        v12 = *(unsigned __int16 *)v9 - v11;
        if ( v12 )
          break;
        v9 += 2;
      }
      while ( v11 );
      if ( v12 )
      {
        if ( (unsigned int)dword_1800AF0C0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800AF0C0, 0x400000000000LL) )
        {
          v24 = v13;
          v25 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            v14,
            (unsigned int)byte_1800A2D25,
            v15,
            v16,
            (__int64)&v25,
            (__int64)&v24);
        }
        v24 = 0;
        WpnGetDeviceVersionFromRegistry(&v24);
        v17 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
        NotificationServiceImpl::SendEventAndUpdateRegistryDeviceValues(v18, v17, v19);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(&v23);
    std::wstring::_Tidy_deallocate(v26);
    std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v27);
    result = v6;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xD5D,
                           (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
                           v20);
  }
  return result;
}

```

## disassembly

```asm
0x18006e2b0  mov     [rsp+arg_0], rbx
0x18006e2b5  push    rdi
0x18006e2b6  sub     rsp, 100h
0x18006e2bd  mov     rax, cs:__security_cookie
0x18006e2c4  xor     rax, rsp
0x18006e2c7  mov     [rsp+108h+var_18], rax
0x18006e2cf  mov     rdi, rdx
0x18006e2d2  mov     rcx, [rsp+108h]; this
0x18006e2da  test    rdx, rdx
0x18006e2dd  jz      loc_18006E50A
0x18006e2e3  lea     rax, ??_7?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@6B@; const std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::`vftable'
0x18006e2ea  mov     [rsp+108h+var_98], rax
0x18006e2ef  mov     cl, 1
0x18006e2f1  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18006e2f7  mov     [rsp+108h+var_80], rax
0x18006e2ff  xorps   xmm0, xmm0
0x18006e302  movups  [rsp+108h+var_78], xmm0
0x18006e30a  mov     [rsp+108h+var_68], 0
0x18006e316  mov     [rsp+108h+var_60], 0Fh
0x18006e322  mov     byte ptr [rsp+108h+var_78], 0
0x18006e32a  movups  [rsp+108h+var_58], xmm0
0x18006e332  mov     [rsp+108h+var_48], 0
0x18006e33e  mov     [rsp+108h+var_40], 7
0x18006e34a  xor     eax, eax
0x18006e34c  mov     word ptr [rsp+108h+var_58], ax
0x18006e354  mov     [rsp+108h+var_30], ax
0x18006e35c  mov     [rsp+108h+var_2E], al
0x18006e363  lea     ecx, [rax+40h]; Size
0x18006e366  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006e36b  mov     rbx, rax
0x18006e36e  mov     [rsp+108h+var_C8], rax
0x18006e373  xor     edx, edx
0x18006e375  mov     rcx, rax
0x18006e378  call    cs:__imp_??0?$codecvt@GDU_Mbstatet@@@std@@QEAA@_K@Z; std::codecvt<ushort,char,_Mbstatet>::codecvt<ushort,char,_Mbstatet>(unsigned __int64)
0x18006e37e  lea     rax, ??_7?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@6B@; const std::codecvt_utf8_utf16<ushort,1114111,0>::`vftable'
0x18006e385  mov     [rbx], rax
0x18006e388  mov     rdx, rbx
0x18006e38b  lea     rcx, [rsp+108h+var_98]
0x18006e390  call    ?_Init@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@AEAAXPEBV?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@2@@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::_Init(std::codecvt_utf8_utf16<ushort,1114111,0> const *)
0x18006e395  nop
0x18006e396  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006e39a  inc     rax
0x18006e39d  cmp     byte ptr [rdi+rax], 0
0x18006e3a1  jnz     short loc_18006E39A
0x18006e3a3  lea     r9, [rax+rdi]
0x18006e3a7  mov     r8, rdi
0x18006e3aa  lea     rdx, [rsp+108h+var_C0]
0x18006e3af  lea     rcx, [rsp+108h+var_98]
0x18006e3b4  call    ?from_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@PEBD0@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::from_bytes(char const *,char const *)
0x18006e3b9  nop
0x18006e3ba  mov     [rsp+108h+var_D8], 0
0x18006e3c3  xor     edx, edx
0x18006e3c5  lea     rcx, [rsp+108h+var_D8]
0x18006e3ca  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18006e3cf  lea     rcx, [rsp+108h+var_D8]; unsigned __int16 **
0x18006e3d4  call    ?WpnGetDeviceIdFromRegistry@@YAJPEAPEAG@Z; WpnGetDeviceIdFromRegistry(ushort * *)
0x18006e3d9  mov     ebx, eax
0x18006e3db  cmp     eax, 80070490h
0x18006e3e0  jnz     short loc_18006E401
0x18006e3e2  lea     rcx, [rsp+108h+var_C0]
0x18006e3e7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006e3ec  mov     rdx, rax; unsigned __int16 *
0x18006e3ef  mov     r8d, 1; unsigned __int64
0x18006e3f5  call    ?SendEventAndUpdateRegistryDeviceValues@NotificationServiceImpl@@AEAAXPEBG_K@Z; NotificationServiceImpl::SendEventAndUpdateRegistryDeviceValues(ushort const *,unsigned __int64)
0x18006e3fa  xor     ebx, ebx
0x18006e3fc  jmp     loc_18006E4C1
0x18006e401  test    eax, eax
0x18006e403  js      loc_18006E4C1
0x18006e409  lea     rcx, [rsp+108h+var_C0]
0x18006e40e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006e413  mov     r8, [rsp+108h+var_D8]
0x18006e418  mov     r9, r8
0x18006e41b  sub     r9, rax
0x18006e41e  movzx   ecx, word ptr [rax]
0x18006e421  movzx   edx, word ptr [rax+r9]
0x18006e426  sub     ecx, edx
0x18006e428  jnz     short loc_18006E432
0x18006e42a  add     rax, 2
0x18006e42e  test    edx, edx
0x18006e430  jnz     short loc_18006E41E
0x18006e432  test    ecx, ecx
0x18006e434  jz      loc_18006E4C1
0x18006e43a  mov     eax, cs:dword_1800AF0C0
0x18006e440  cmp     eax, 5
0x18006e443  jbe     short loc_18006E493
0x18006e445  mov     rdx, 400000000000h
0x18006e44f  lea     rcx, dword_1800AF0C0
0x18006e456  call    _tlgKeywordOn
0x18006e45b  test    al, al
0x18006e45d  jz      short loc_18006E493
0x18006e45f  mov     [rsp+108h+var_D0], r8
0x18006e464  lea     rcx, [rsp+108h+var_C0]
0x18006e469  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006e46e  mov     [rsp+108h+var_C8], rax
0x18006e473  lea     rax, [rsp+108h+var_D0]
0x18006e478  mov     [rsp+108h+var_E0], rax
0x18006e47d  lea     rax, [rsp+108h+var_C8]
0x18006e482  mov     [rsp+108h+var_E8], rax
0x18006e487  lea     rdx, byte_1800A2D25
0x18006e48e  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18006e493  mov     [rsp+108h+var_D0], 0
0x18006e49c  lea     rcx, [rsp+108h+var_D0]; unsigned __int64 *
0x18006e4a1  call    ?WpnGetDeviceVersionFromRegistry@@YAXPEA_K@Z; WpnGetDeviceVersionFromRegistry(unsigned __int64 *)
0x18006e4a6  mov     r8, [rsp+108h+var_D0]
0x18006e4ab  inc     r8
0x18006e4ae  lea     rcx, [rsp+108h+var_C0]
0x18006e4b3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006e4b8  mov     rdx, rax; unsigned __int16 *
0x18006e4bb  call    ?SendEventAndUpdateRegistryDeviceValues@NotificationServiceImpl@@AEAAXPEBG_K@Z; NotificationServiceImpl::SendEventAndUpdateRegistryDeviceValues(ushort const *,unsigned __int64)
0x18006e4c0  nop
0x18006e4c1  lea     rcx, [rsp+108h+var_D8]
0x18006e4c6  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x18006e4cb  nop
0x18006e4cc  lea     rcx, [rsp+108h+var_C0]
0x18006e4d1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006e4d6  nop
0x18006e4d7  lea     rcx, [rsp+108h+var_98]
0x18006e4dc  call    ??1?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x18006e4e1  mov     eax, ebx
0x18006e4e3  jmp     short loc_18006E4E9
0x18006e4e5  mov     eax, dword ptr [rsp+108h+var_D8]
0x18006e4e9  mov     rcx, [rsp+108h+var_18]
0x18006e4f1  xor     rcx, rsp; StackCookie
0x18006e4f4  call    __security_check_cookie
0x18006e4f9  mov     rbx, [rsp+108h+arg_0]
0x18006e501  add     rsp, 100h
0x18006e508  pop     rdi
0x18006e509  retn
0x18006e50a  mov     r9d, 80070057h; char *
0x18006e510  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006e517  mov     edx, 0D40h; void *
0x18006e51c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
