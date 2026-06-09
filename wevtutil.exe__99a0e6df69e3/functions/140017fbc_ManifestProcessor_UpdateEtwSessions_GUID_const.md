# ManifestProcessor::UpdateEtwSessions(_GUID const &)

- ea: `0x140017fbc`
- end: `0x140018142`
- name: `?UpdateEtwSessions@ManifestProcessor@@AEAAXAEBU_GUID@@@Z`
- size: `390`
- prototype: `void(ManifestProcessor *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14001663c`

## callees

- `0x140003b50`
- `0x140004cb0`
- `0x1400050a0`
- `0x140007f00`
- `0x140008b40`
- `0x1400099c8`
- `0x140017fbc`
- `0x140018d98`
- `0x140021b00`
- `0x14002daf0`
- `0x14002e018`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018017`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018017`

## string_xrefs

- `0x140018067`: `Security`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ManifestProcessor::UpdateEtwSessions(ManifestProcessor *this, const struct _GUID *a2)
{
  void *v4; // rbx
  HKEY *v5; // rax
  unsigned __int64 v6; // rbx
  const struct std::nothrow_t *i; // rcx
  const struct std::nothrow_t *v8; // [rsp+20h] [rbp-89h] BYREF
  __int64 v9; // [rsp+28h] [rbp-81h]
  HKEY hKey[2]; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v11[72]; // [rsp+50h] [rbp-59h] BYREF
  __int64 v12; // [rsp+98h] [rbp-11h]
  __int64 v13; // [rsp+A0h] [rbp-9h]

  v4 = (void *)*((_QWORD *)this + 1);
  v5 = (HKEY *)OpenPublishersKeyOrThrow(hKey, v4);
  PublisherConfigReader::PublisherConfigReader((PublisherConfigReader *)v11, a2, *v5, v4);
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  if ( v13 - v12 == 52
    && !(unsigned int)tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(
                        v12,
                        L"Microsoft-Windows-Eventlog",
                        26) )
  {
    SessionConfig::OfflineUpdateAutologgerForChannel(L"Application", *((void **)this + 1));
    SessionConfig::OfflineUpdateAutologgerForChannel(L"System", *((void **)this + 1));
    SessionConfig::OfflineUpdateAutologgerForChannel(L"Security", *((void **)this + 1));
  }
  utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(&v8);
  PublisherConfigReader::GetAndValidateManifestedChannelReferences((__int64)v11, &v8);
  v6 = 0;
  for ( i = v8; v6 < 0xAAAAAAAAAAAAAAABuLL * ((v9 - (__int64)v8) >> 4); i = v8 )
  {
    if ( (*((_BYTE *)i + 48 * v6 + 40) & 1) != 0 )
    {
      *(struct _GUID *)hKey = *a2;
      SessionConfig::AddProviderToChannel(
        (struct _GUID *)hKey,
        *((const wchar_t **)i + 6 * v6),
        *((_DWORD *)i + 12 * v6 + 9),
        *((void **)this + 1));
    }
    else
    {
      SessionConfig::OfflineUpdateAutologgerForChannel(*((const wchar_t **)i + 6 * v6), *((void **)this + 1));
    }
    ++v6;
  }
  utl::vector<ChannelReference,utl::allocator<ChannelReference>>::_Uninit(&v8);
  PublisherConfigReader::~PublisherConfigReader((PublisherConfigReader *)v11);
}

```

## disassembly

```asm
0x140017fbc  mov     [rsp-8+arg_10], rbx
0x140017fc1  mov     [rsp-8+arg_18], rsi
0x140017fc6  push    rbp
0x140017fc7  push    rdi
0x140017fc8  push    r14
0x140017fca  lea     rbp, [rsp-47h]
0x140017fcf  sub     rsp, 0F0h
0x140017fd6  mov     rax, cs:__security_cookie
0x140017fdd  xor     rax, rsp
0x140017fe0  mov     [rbp+57h+var_20], rax
0x140017fe4  mov     rsi, rdx
0x140017fe7  mov     rdi, rcx
0x140017fea  mov     rbx, [rcx+8]
0x140017fee  mov     rdx, rbx
0x140017ff1  lea     rcx, [rbp+57h+hKey]
0x140017ff5  call    OpenPublishersKeyOrThrow
0x140017ffa  nop
0x140017ffb  mov     r9, rbx; void *
0x140017ffe  mov     r8, [rax]; HKEY
0x140018001  mov     rdx, rsi; struct _GUID *
0x140018004  lea     rcx, [rbp+57h+var_B0]; this
0x140018008  call    ??0PublisherConfigReader@@IEAA@AEBU_GUID@@PEAUHKEY__@@PEAX@Z; PublisherConfigReader::PublisherConfigReader(_GUID const &,HKEY__ *,void *)
0x14001800d  nop
0x14001800e  mov     rcx, [rbp+57h+hKey]; hKey
0x140018012  test    rcx, rcx
0x140018015  jz      short loc_14001801E
0x140018017  call    cs:__imp_RegCloseKey
0x14001801d  nop
0x14001801e  mov     rcx, [rbp+57h+var_68]
0x140018022  mov     rax, [rbp+57h+var_60]
0x140018026  sub     rax, rcx
0x140018029  cmp     rax, 34h ; '4'
0x14001802d  jnz     short loc_140018073
0x14001802f  lea     r8d, [rax-1Ah]
0x140018033  lea     rdx, aMicrosoftWindo; "Microsoft-Windows-Eventlog"
0x14001803a  call    ?compare@?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@SAHPEB_W0_K@Z; tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(wchar_t const *,wchar_t const *,unsigned __int64)
0x14001803f  test    eax, eax
0x140018041  jnz     short loc_140018073
0x140018043  mov     rdx, [rdi+8]; void *
0x140018047  lea     rcx, aApplication; "Application"
0x14001804e  call    ?OfflineUpdateAutologgerForChannel@SessionConfig@@SAXPEB_WPEAX@Z; SessionConfig::OfflineUpdateAutologgerForChannel(wchar_t const *,void *)
0x140018053  mov     rdx, [rdi+8]; void *
0x140018057  lea     rcx, aSystem; "System"
0x14001805e  call    ?OfflineUpdateAutologgerForChannel@SessionConfig@@SAXPEB_WPEAX@Z; SessionConfig::OfflineUpdateAutologgerForChannel(wchar_t const *,void *)
0x140018063  mov     rdx, [rdi+8]; void *
0x140018067  lea     rcx, aSecurity; "Security"
0x14001806e  call    ?OfflineUpdateAutologgerForChannel@SessionConfig@@SAXPEB_WPEAX@Z; SessionConfig::OfflineUpdateAutologgerForChannel(wchar_t const *,void *)
0x140018073  lea     rcx, [rsp+100h+var_E0]
0x140018078  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(void)
0x14001807d  nop
0x14001807e  lea     rdx, [rsp+100h+var_E0]
0x140018083  lea     rcx, [rbp+57h+var_B0]
0x140018087  call    ?GetAndValidateManifestedChannelReferences@PublisherConfigReader@@QEBA_NAEAV?$vector@UChannelReference@@V?$allocator@UChannelReference@@@utl@@@utl@@@Z; PublisherConfigReader::GetAndValidateManifestedChannelReferences(utl::vector<ChannelReference,utl::allocator<ChannelReference>> &)
0x14001808c  xor     ebx, ebx
0x14001808e  mov     rax, [rsp+100h+var_D8]
0x140018093  mov     rcx, [rsp+100h+var_E0]
0x140018098  sub     rax, rcx
0x14001809b  sar     rax, 4
0x14001809f  mov     r14, 0AAAAAAAAAAAAAAABh
0x1400180a9  imul    rax, r14
0x1400180ad  test    rax, rax
0x1400180b0  jz      short loc_14001810A
0x1400180b2  lea     rax, [rbx+rbx*2]
0x1400180b6  add     rax, rax
0x1400180b9  test    byte ptr [rcx+rax*8+28h], 1
0x1400180be  jnz     short loc_1400180CF
0x1400180c0  mov     rdx, [rdi+8]; void *
0x1400180c4  mov     rcx, [rcx+rax*8]; wchar_t *
0x1400180c8  call    ?OfflineUpdateAutologgerForChannel@SessionConfig@@SAXPEB_WPEAX@Z; SessionConfig::OfflineUpdateAutologgerForChannel(wchar_t const *,void *)
0x1400180cd  jmp     short loc_1400180ED
0x1400180cf  movups  xmm0, xmmword ptr [rsi]
0x1400180d2  movdqu  xmmword ptr [rbp+57h+hKey], xmm0
0x1400180d7  mov     r9, [rdi+8]; void *
0x1400180db  mov     r8d, [rcx+rax*8+24h]; unsigned int
0x1400180e0  mov     rdx, [rcx+rax*8]; wchar_t *
0x1400180e4  lea     rcx, [rbp+57h+hKey]; struct _GUID
0x1400180e8  call    ?AddProviderToChannel@SessionConfig@@SAXU_GUID@@PEB_WKPEAX@Z; SessionConfig::AddProviderToChannel(_GUID,wchar_t const *,ulong,void *)
0x1400180ed  inc     rbx
0x1400180f0  mov     rax, [rsp+100h+var_D8]
0x1400180f5  mov     rcx, [rsp+100h+var_E0]
0x1400180fa  sub     rax, rcx
0x1400180fd  sar     rax, 4
0x140018101  imul    rax, r14
0x140018105  cmp     rbx, rax
0x140018108  jb      short loc_1400180B2
0x14001810a  lea     rcx, [rsp+100h+var_E0]
0x14001810f  call    ?_Uninit@?$vector@UChannelReference@@V?$allocator@UChannelReference@@@utl@@@utl@@AEAAXXZ; utl::vector<ChannelReference,utl::allocator<ChannelReference>>::_Uninit(void)
0x140018114  nop
0x140018115  lea     rcx, [rbp+57h+var_B0]; this
0x140018119  call    ??1PublisherConfigReader@@QEAA@XZ; PublisherConfigReader::~PublisherConfigReader(void)
0x14001811e  mov     rcx, [rbp+57h+var_20]
0x140018122  xor     rcx, rsp; StackCookie
0x140018125  call    __security_check_cookie
0x14001812a  lea     r11, [rsp+100h+var_10]
0x140018132  mov     rbx, [r11+30h]
0x140018136  mov     rsi, [r11+38h]
0x14001813a  mov     rsp, r11
0x14001813d  pop     r14
0x14001813f  pop     rdi
0x140018140  pop     rbp
0x140018141  retn
```
