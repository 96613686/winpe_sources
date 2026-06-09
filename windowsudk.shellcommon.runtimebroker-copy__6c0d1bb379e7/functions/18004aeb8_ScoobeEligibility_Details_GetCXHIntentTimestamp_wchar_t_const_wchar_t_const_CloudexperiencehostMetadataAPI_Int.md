# ScoobeEligibility::Details::GetCXHIntentTimestamp(wchar_t const *,wchar_t const *,CloudexperiencehostMetadataAPI::IntentValues)

- ea: `0x18004aeb8`
- end: `0x18004b0fc`
- name: `?GetCXHIntentTimestamp@Details@ScoobeEligibility@@YA?AU_FILETIME@@PEB_W0W4IntentValues@CloudexperiencehostMetadataAPI@@@Z`
- size: `580`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180049bf8`

## callees

- `0x18004aeb8`
- `0x18004b104`
- `0x18004b58c`
- `0x18004c8c4`
- `0x1800e488c`
- `0x18015cb00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004af44`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004b017`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004af44`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004b017`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004af85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b059`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004af85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b059`

## string_xrefs

- `0x18004b07f`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\scoobe\ScoobeEligibility.h`
- `0x18004b0aa`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\scoobe\ScoobeEligibility.h`
- `0x18004b0d4`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\scoobe\ScoobeEligibility.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ScoobeEligibility::Details::GetCXHIntentTimestamp(__int64 a1, __int64 a2, int a3)
{
  LSTATUS ValueW; // eax
  int v6; // edx
  unsigned __int64 v7; // rcx
  char v8; // al
  char v9; // bl
  const char *v10; // r9
  LSTATUS v12; // eax
  int v13; // edx
  const wchar_t *v14; // r8
  unsigned __int64 v15; // rcx
  int QwordAsBinary; // eax
  int pdwType; // [rsp+20h] [rbp-58h]
  unsigned __int64 *pdwTypea; // [rsp+20h] [rbp-58h]
  int pdwTypeb; // [rsp+20h] [rbp-58h]
  DWORD pcbData; // [rsp+40h] [rbp-38h] BYREF
  wchar_t pvData[4]; // [rsp+48h] [rbp-30h] BYREF
  LPCWSTR v22; // [rsp+50h] [rbp-28h] BYREF
  LPCWSTR lpSubKey; // [rsp+58h] [rbp-20h] BYREF
  DWORD v24; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  try
  {
    wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
      &lpSubKey,
      L"%ws\\%ws",
      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost\\Intent",
      a1);
    *(_QWORD *)pvData = 0;
    pcbData = 8;
    ValueW = RegGetValueW(HKEY_CURRENT_USER, lpSubKey, L"Timestamp", 8u, 0, pvData, &pcbData);
    v7 = (unsigned int)ValueW;
    if ( ValueW > 0 )
      v7 = (unsigned __int16)ValueW | 0x80070000;
    if ( (v7 & 0x80000000) == 0LL || ScoobeEligibility::Details::IsNotFoundError((ScoobeEligibility::Details *)v7, v6) )
    {
      v8 = 0;
      v9 = 1;
    }
    else
    {
      v9 = 1;
      v8 = 1;
    }
    if ( v8 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x72,
        (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\scoobe\\ScoobeEligibility.h",
        (const char *)(unsigned int)v7,
        pdwType);
    if ( ScoobeEligibility::Details::IsNotFoundError((ScoobeEligibility::Details *)v7, v6) && a2 )
    {
      pcbData = 0;
      wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
        &v22,
        L"%ws\\%ws",
        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost\\Intent",
        a2);
      v24 = 4;
      v12 = RegGetValueW(HKEY_CURRENT_USER, v22, L"Intent", 0x10u, 0, &pcbData, &v24);
      v15 = (unsigned int)v12;
      if ( v12 > 0 )
        v15 = (unsigned __int16)v12 | 0x80070000;
      if ( (v15 & 0x80000000) == 0LL
        || ScoobeEligibility::Details::IsNotFoundError((ScoobeEligibility::Details *)v15, v13) )
      {
        v9 = 0;
      }
      if ( v9 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x7A,
          (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\scoobe\\ScoobeEligibility.h",
          (const char *)(unsigned int)v15,
          (int)pdwTypea);
      if ( (v15 & 0x80000000) == 0LL && pcbData == a3 )
      {
        QwordAsBinary = ScoobeEligibility::Details::RegGetQwordAsBinary(
                          (ScoobeEligibility::Details *)v15,
                          (HKEY)v22,
                          v14,
                          pvData,
                          pdwTypea);
        if ( QwordAsBinary < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x7F,
            (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\scoobe\\ScoobeEligibility.h",
            (const char *)(unsigned int)QwordAsBinary,
            pdwTypeb);
      }
      if ( v22 )
        CoTaskMemFree((LPVOID)v22);
    }
    if ( lpSubKey )
      CoTaskMemFree((LPVOID)lpSubKey);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x83,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\scoobe\\ScoobeEligibility.h",
      v10);
  }
  return *(_QWORD *)pvData;
}

```

## disassembly

```asm
0x18004aeb8  mov     r11, rsp
0x18004aebb  mov     [r11+18h], rbx
0x18004aebf  mov     [r11+20h], rsi
0x18004aec3  push    rdi
0x18004aec4  sub     rsp, 70h
0x18004aec8  mov     rax, cs:__security_cookie
0x18004aecf  xor     rax, rsp
0x18004aed2  mov     [rsp+78h+var_10], rax
0x18004aed7  mov     esi, r8d
0x18004aeda  mov     rdi, rdx
0x18004aedd  mov     qword ptr [r11-30h], 0
0x18004aee5  mov     r9, rcx
0x18004aee8  lea     r8, aSoftwareMicros_67; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18004aeef  lea     rdx, aWsWs_0; "%ws\\%ws"
0x18004aef6  lea     rcx, [r11-20h]
0x18004aefa  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_WZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,...)
0x18004aeff  nop
0x18004af00  mov     qword ptr [rsp+78h+var_30], 0
0x18004af09  mov     r9d, 8; dwFlags
0x18004af0f  mov     [rsp+78h+var_38], r9d
0x18004af14  lea     rax, [rsp+78h+var_38]
0x18004af19  mov     [rsp+78h+pcbData], rax; pcbData
0x18004af1e  lea     rax, [rsp+78h+var_30]
0x18004af23  mov     [rsp+78h+pvData], rax; pvData
0x18004af28  mov     [rsp+78h+pdwType], 0; int
0x18004af31  lea     r8, aTimestamp; "Timestamp"
0x18004af38  mov     rdx, [rsp+78h+lpSubKey]; lpSubKey
0x18004af3d  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18004af44  call    cs:__imp_RegGetValueW
0x18004af4a  mov     ecx, eax
0x18004af4c  test    eax, eax
0x18004af4e  jle     short loc_18004AF59
0x18004af50  movzx   ecx, ax
0x18004af53  or      ecx, 80070000h; this
0x18004af59  test    ecx, ecx
0x18004af5b  js      loc_18004B091
0x18004af61  xor     al, al
0x18004af63  mov     bl, 1
0x18004af65  mov     r10, [rsp+78h]
0x18004af6a  test    al, al
0x18004af6c  jnz     loc_18004B0A7
0x18004af72  call    ?IsNotFoundError@Details@ScoobeEligibility@@YA_NJ@Z; ScoobeEligibility::Details::IsNotFoundError(long)
0x18004af77  test    al, al
0x18004af79  jnz     short loc_18004AFB0
0x18004af7b  mov     rcx, [rsp+78h+lpSubKey]; pv
0x18004af80  test    rcx, rcx
0x18004af83  jz      short loc_18004AF8C
0x18004af85  call    cs:__imp_CoTaskMemFree
0x18004af8b  nop
0x18004af8c  mov     rax, qword ptr [rsp+78h+var_30]
0x18004af91  mov     rcx, [rsp+78h+var_10]
0x18004af96  xor     rcx, rsp; StackCookie
0x18004af99  call    __security_check_cookie
0x18004af9e  lea     r11, [rsp+78h+var_8]
0x18004afa3  mov     rbx, [r11+20h]
0x18004afa7  mov     rsi, [r11+28h]
0x18004afab  mov     rsp, r11
0x18004afae  pop     rdi
0x18004afaf  retn
0x18004afb0  test    rdi, rdi
0x18004afb3  jz      short loc_18004AF7B
0x18004afb5  mov     [rsp+78h+var_38], 0
0x18004afbd  mov     r9, rdi
0x18004afc0  lea     r8, aSoftwareMicros_67; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18004afc7  lea     rdx, aWsWs_0; "%ws\\%ws"
0x18004afce  lea     rcx, [rsp+78h+var_28]
0x18004afd3  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_WZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,...)
0x18004afd8  nop
0x18004afd9  mov     [rsp+78h+var_18], 4
0x18004afe1  lea     rax, [rsp+78h+var_18]
0x18004afe6  mov     [rsp+78h+pcbData], rax; pcbData
0x18004afeb  lea     rax, [rsp+78h+var_38]
0x18004aff0  mov     [rsp+78h+pvData], rax; pvData
0x18004aff5  mov     [rsp+78h+pdwType], 0; int
0x18004affe  mov     r9d, 10h; dwFlags
0x18004b004  lea     r8, aIntent; "Intent"
0x18004b00b  mov     rdx, [rsp+78h+var_28]; lpSubKey
0x18004b010  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18004b017  call    cs:__imp_RegGetValueW
0x18004b01d  mov     ecx, eax
0x18004b01f  test    eax, eax
0x18004b021  jle     short loc_18004B02C
0x18004b023  movzx   ecx, ax
0x18004b026  or      ecx, 80070000h; this
0x18004b02c  test    ecx, ecx
0x18004b02e  js      loc_18004B0BF
0x18004b034  xor     bl, bl
0x18004b036  mov     rax, [rsp+78h]
0x18004b03b  test    bl, bl
0x18004b03d  jnz     loc_18004B0D1
0x18004b043  test    ecx, ecx
0x18004b045  jns     loc_18004B0E8
0x18004b04b  mov     rcx, [rsp+78h+var_28]; pv
0x18004b050  test    rcx, rcx
0x18004b053  jz      loc_18004AF7B
0x18004b059  call    cs:__imp_CoTaskMemFree
0x18004b05f  jmp     loc_18004AF7B
0x18004b064  lea     r9, [rsp+78h+var_30]; wchar_t *
0x18004b069  mov     rdx, [rsp+78h+var_28]; HKEY
0x18004b06e  call    ?RegGetQwordAsBinary@Details@ScoobeEligibility@@YAJPEAUHKEY__@@PEB_W1PEA_K@Z; ScoobeEligibility::Details::RegGetQwordAsBinary(HKEY__ *,wchar_t const *,wchar_t const *,unsigned __int64 *)
0x18004b073  mov     rcx, [rsp+78h]; this
0x18004b078  test    eax, eax
0x18004b07a  jns     short loc_18004B04B
0x18004b07c  mov     r9d, eax; char *
0x18004b07f  lea     r8, aShellcommondes_6; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18004b086  mov     edx, 7Fh; void *
0x18004b08b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b091  call    ?IsNotFoundError@Details@ScoobeEligibility@@YA_NJ@Z; ScoobeEligibility::Details::IsNotFoundError(long)
0x18004b096  test    al, al
0x18004b098  jnz     loc_18004AF61
0x18004b09e  mov     bl, 1
0x18004b0a0  mov     al, bl
0x18004b0a2  jmp     loc_18004AF65
0x18004b0a7  mov     r9d, ecx; char *
0x18004b0aa  lea     r8, aShellcommondes_6; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18004b0b1  mov     edx, 72h ; 'r'; void *
0x18004b0b6  mov     rcx, r10; this
0x18004b0b9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b0bf  call    ?IsNotFoundError@Details@ScoobeEligibility@@YA_NJ@Z; ScoobeEligibility::Details::IsNotFoundError(long)
0x18004b0c4  test    al, al
0x18004b0c6  jz      loc_18004B036
0x18004b0cc  jmp     loc_18004B034
0x18004b0d1  mov     r9d, ecx; char *
0x18004b0d4  lea     r8, aShellcommondes_6; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18004b0db  mov     edx, 7Ah ; 'z'; void *
0x18004b0e0  mov     rcx, rax; this
0x18004b0e3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b0e8  cmp     [rsp+78h+var_38], esi
0x18004b0ec  jnz     loc_18004B04B
0x18004b0f2  jmp     loc_18004B064
0x18004b0f7  jmp     loc_18004AF8C
```
