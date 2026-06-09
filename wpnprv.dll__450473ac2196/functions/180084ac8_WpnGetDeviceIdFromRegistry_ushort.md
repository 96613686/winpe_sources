# WpnGetDeviceIdFromRegistry(ushort * *)

- ea: `0x180084ac8`
- end: `0x180084ce9`
- name: `?WpnGetDeviceIdFromRegistry@@YAJPEAPEAG@Z`
- size: `545`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006e2b0`

## callees

- `0x180008294`
- `0x18000a518`
- `0x18000fe0c`
- `0x18001c768`
- `0x18004e768`
- `0x180063934`
- `0x180066964`
- `0x180084598`
- `0x180084ac8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180084b6f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180084c2e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180084b6f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180084c2e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180084b0b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180084b0b`

## string_xrefs

- `0x180084b1d`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x180084c40`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x180084c6a`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WpnGetDeviceIdFromRegistry(unsigned __int16 **a1)
{
  LSTATUS v2; // eax
  char *v3; // rsi
  unsigned __int64 v4; // rcx
  char *v5; // rax
  size_t v6; // rbx
  unsigned int ValueW; // eax
  int v8; // eax
  const char *v9; // r9
  __int64 result; // rax
  int pdwType; // [rsp+20h] [rbp-58h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-58h]
  PVOID pvData[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v14; // [rsp+50h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  DWORD pcbData; // [rsp+80h] [rbp+8h] BYREF
  HKEY v17; // [rsp+88h] [rbp+10h] BYREF

  *a1 = 0;
  v17 = 0;
  v2 = RegOpenKeyExW(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\PushNotifications\\DeviceInfo",
         0,
         0xF003Fu,
         &v17);
  try
  {
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7B8,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
        (const char *)(unsigned int)v2,
        pdwType);
    pcbData = 0;
    if ( RegGetValueW(
           HKEY_CURRENT_USER,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\PushNotifications\\DeviceInfo",
           L"DeviceVersionRepresentation",
           2u,
           0,
           0,
           &pcbData)
      || !pcbData )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v17);
      return 2147943568LL;
    }
    std::vector<std::wstring>::vector<std::wstring>(pvData);
    v3 = (char *)pvData[1];
    v4 = ((char *)pvData[1] - (char *)pvData[0]) >> 1;
    if ( pcbData < v4 )
    {
      v5 = (char *)pvData[0] + 2 * pcbData;
LABEL_12:
      pvData[1] = v5;
      goto LABEL_13;
    }
    if ( pcbData > v4 )
    {
      if ( pcbData <= (unsigned __int64)((signed __int64)(v14 - (unsigned __int64)pvData[0]) >> 1) )
      {
        v6 = 2 * (pcbData - v4);
        memset_0(pvData[1], 0, v6);
        v5 = &v3[v6];
        goto LABEL_12;
      }
      std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(pvData, pcbData);
    }
LABEL_13:
    ValueW = RegGetValueW(
               HKEY_CURRENT_USER,
               L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\PushNotifications\\DeviceInfo",
               L"DeviceVersionRepresentation",
               2u,
               0,
               pvData[0],
               &pcbData);
    if ( ValueW )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x7C7,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
        (const char *)ValueW,
        pdwTypea);
    v8 = WpnCoTaskStrCpy((const unsigned __int16 *)pvData[0], a1);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7C9,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
        (const char *)(unsigned int)v8,
        pdwTypea);
    if ( pvData[0] )
    {
      std::_Deallocate<16>(
        (_QWORD *)pvData[0],
        (const struct std::nothrow_t *)(2 * ((signed __int64)(v14 - (unsigned __int64)pvData[0]) >> 1)));
      *(_OWORD *)pvData = 0;
      v14 = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v17);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x7CE,
                           (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x180084ac8  mov     r11, rsp
0x180084acb  mov     [r11+18h], rbx
0x180084acf  push    rsi
0x180084ad0  push    rdi
0x180084ad1  push    r12
0x180084ad3  sub     rsp, 60h
0x180084ad7  mov     rdi, rcx
0x180084ada  mov     qword ptr [rcx], 0
0x180084ae1  mov     qword ptr [r11+10h], 0
0x180084ae9  lea     rax, [r11+10h]
0x180084aed  mov     [r11-58h], rax
0x180084af1  mov     r9d, 0F003Fh; samDesired
0x180084af7  xor     r8d, r8d; ulOptions
0x180084afa  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180084b01  mov     r12, 0FFFFFFFF80000001h
0x180084b08  mov     rcx, r12; hKey
0x180084b0b  call    cs:__imp_RegOpenKeyExW
0x180084b11  mov     rcx, [rsp+78h]; this
0x180084b16  test    eax, eax
0x180084b18  jns     short loc_180084B2E
0x180084b1a  mov     r9d, eax; char *
0x180084b1d  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180084b24  mov     edx, 7B8h; void *
0x180084b29  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180084b2e  mov     [rsp+78h+arg_0], 0
0x180084b39  lea     rax, [rsp+78h+arg_0]
0x180084b41  mov     [rsp+78h+pcbData], rax; pcbData
0x180084b46  mov     [rsp+78h+pvData], 0; pvData
0x180084b4f  mov     [rsp+78h+pdwType], 0; pdwType
0x180084b58  mov     r9d, 2; dwFlags
0x180084b5e  lea     r8, aDeviceversionr; "DeviceVersionRepresentation"
0x180084b65  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180084b6c  mov     rcx, r12; hkey
0x180084b6f  call    cs:__imp_RegGetValueW
0x180084b75  test    eax, eax
0x180084b77  jnz     loc_180084CBC
0x180084b7d  cmp     [rsp+78h+arg_0], eax
0x180084b84  jz      loc_180084CBC
0x180084b8a  lea     rcx, [rsp+78h+var_38]
0x180084b8f  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::vector<std::wstring>(void)
0x180084b94  nop
0x180084b95  mov     ebx, [rsp+78h+arg_0]
0x180084b9c  mov     rdx, [rsp+78h+var_38]
0x180084ba1  mov     rsi, [rsp+78h+var_38+8]
0x180084ba6  mov     rcx, rsi
0x180084ba9  sub     rcx, rdx
0x180084bac  sar     rcx, 1
0x180084baf  cmp     rbx, rcx
0x180084bb2  jnb     short loc_180084BBA
0x180084bb4  lea     rax, [rdx+rbx*2]
0x180084bb8  jmp     short loc_180084BF2
0x180084bba  jbe     short loc_180084BF7
0x180084bbc  mov     rax, [rsp+78h+var_28]
0x180084bc1  sub     rax, rdx
0x180084bc4  sar     rax, 1
0x180084bc7  cmp     rbx, rax
0x180084bca  jbe     short loc_180084BDB
0x180084bcc  mov     rdx, rbx
0x180084bcf  lea     rcx, [rsp+78h+var_38]
0x180084bd4  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180084bd9  jmp     short loc_180084BF7
0x180084bdb  sub     rbx, rcx
0x180084bde  add     rbx, rbx
0x180084be1  mov     r8, rbx; Size
0x180084be4  xor     edx, edx; Val
0x180084be6  mov     rcx, rsi; void *
0x180084be9  call    memset_0
0x180084bee  lea     rax, [rbx+rsi]
0x180084bf2  mov     [rsp+78h+var_38+8], rax
0x180084bf7  mov     rax, [rsp+78h+var_38]
0x180084bfc  lea     r10, [rsp+78h+arg_0]
0x180084c04  mov     [rsp+78h+pcbData], r10; pcbData
0x180084c09  mov     [rsp+78h+pvData], rax; pvData
0x180084c0e  mov     [rsp+78h+pdwType], 0; int
0x180084c17  mov     r9d, 2; dwFlags
0x180084c1d  lea     r8, aDeviceversionr; "DeviceVersionRepresentation"
0x180084c24  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180084c2b  mov     rcx, r12; hkey
0x180084c2e  call    cs:__imp_RegGetValueW
0x180084c34  mov     rcx, [rsp+78h]; this
0x180084c39  test    eax, eax
0x180084c3b  jz      short loc_180084C51
0x180084c3d  mov     r9d, eax; char *
0x180084c40  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180084c47  mov     edx, 7C7h; void *
0x180084c4c  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180084c51  mov     rdx, rdi; unsigned __int16 **
0x180084c54  mov     rcx, [rsp+78h+var_38]; unsigned __int16 *
0x180084c59  call    ?WpnCoTaskStrCpy@@YAJPEBGPEAPEAG@Z; WpnCoTaskStrCpy(ushort const *,ushort * *)
0x180084c5e  mov     rcx, [rsp+78h]; this
0x180084c63  test    eax, eax
0x180084c65  jns     short loc_180084C7C
0x180084c67  mov     r9d, eax; char *
0x180084c6a  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180084c71  mov     edx, 7C9h; void *
0x180084c76  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180084c7c  mov     rcx, [rsp+78h+var_38]
0x180084c81  test    rcx, rcx
0x180084c84  jz      short loc_180084CAB
0x180084c86  mov     rdx, [rsp+78h+var_28]
0x180084c8b  sub     rdx, rcx
0x180084c8e  sar     rdx, 1
0x180084c91  add     rdx, rdx
0x180084c94  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180084c99  xorps   xmm0, xmm0
0x180084c9c  movdqu  xmmword ptr [rsp+78h+var_38], xmm0
0x180084ca2  mov     [rsp+78h+var_28], 0
0x180084cab  lea     rcx, [rsp+78h+arg_8]
0x180084cb3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180084cb8  xor     eax, eax
0x180084cba  jmp     short loc_180084CD7
0x180084cbc  lea     rcx, [rsp+78h+arg_8]
0x180084cc4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180084cc9  mov     eax, 80070490h
0x180084cce  jmp     short loc_180084CD7
0x180084cd0  mov     eax, [rsp+78h+arg_0]
0x180084cd7  mov     rbx, [rsp+78h+arg_10]
0x180084cdf  add     rsp, 60h
0x180084ce3  pop     r12
0x180084ce5  pop     rdi
0x180084ce6  pop     rsi
0x180084ce7  retn
```
