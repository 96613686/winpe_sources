# WnsProvider::UpdateWnsChannel_Impl_Old(bool)

- ea: `0x18004e95c`
- end: `0x18004eb2e`
- name: `?UpdateWnsChannel_Impl_Old@WnsProvider@@AEAAJ_N@Z`
- size: `466`
- prototype: `__int64 __fastcall(WnsProvider *__hidden this, bool)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004e730`

## callees

- `0x18000fe24`
- `0x1800101fc`
- `0x180019e18`
- `0x18002b074`
- `0x18004bc1c`
- `0x18004c02c`
- `0x18004cb40`
- `0x18004cb9c`
- `0x18004cc34`
- `0x18004e028`
- `0x18004e144`
- `0x18004e52c`
- `0x18004e6cc`
- `0x18004e95c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ea10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004eac6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ea10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004eac6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004ea56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004ea56`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WnsProvider::UpdateWnsChannel_Impl_Old(ClientState **this, char a2)
{
  __int64 result; // rax
  unsigned int v5; // edx
  const char *v6; // r9
  int v7; // eax
  int ChannelUri; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  int v10; // eax
  unsigned int v11; // edi
  int v12; // eax
  int v13[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v14; // [rsp+28h] [rbp-20h] BYREF
  std::_Ref_count_base *v15; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  UINT32 length; // [rsp+60h] [rbp+18h] BYREF
  HSTRING string; // [rsp+68h] [rbp+20h] BYREF

  result = WnsProvider::IsWnsAllowed_Impl((WnsProvider *)this);
  if ( (int)result >= 0 )
  {
    try
    {
      WnsProvider::GetEnvironmentSettings(this, &v14);
      if ( a2
        || !WnsProvider::IsRegisteredWithWoscService((WnsProvider *)this, *(const unsigned __int16 **)(v14 + 32))
        || WnsProvider::IsWnsChannelExpiring((WnsProvider *)this, v5) )
      {
        v7 = WnsProvider::RegisterForWns_Impl((WnsProvider *)this, 0, 0);
        if ( v7 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x161,
            (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
            (const char *)(unsigned int)v7,
            v13[0]);
        ClientState::SetWnsRegisteredWithWoscService(this[1], 0);
        *(_QWORD *)((char *)this[1] + 444) = 0;
        *((_DWORD *)this[1] + 113) = 0;
        *(_QWORD *)v13 = 0;
        WindowsDeleteString(0);
        string = 0;
        ChannelUri = WnsProvider::GetChannelUri(
                       *(const unsigned __int16 **)(v14 + 24),
                       &string,
                       (struct Windows::Foundation::DateTime *)v13);
        if ( ChannelUri < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x167,
            (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
            (const char *)(unsigned int)ChannelUri,
            v13[0]);
        length = 0;
        StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
        v10 = WnsProvider::RegisterWNSChannelWithWosc(*(const unsigned __int16 **)(v14 + 32), StringRawBuffer);
        v11 = v10;
        if ( v10 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x16C,
            (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
            (const char *)(unsigned int)v10,
            v13[0]);
        ClientState::SetWnsRegisteredWithWoscService(this[1], *(unsigned __int16 **)(v14 + 32));
        WnsProvider::SaveWnsChannelExpiration(this, *(_QWORD *)v13);
        v12 = WnsProvider::SaveWnsState_Impl((WnsProvider *)this);
        if ( v12 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x16F,
            (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
            (const char *)(unsigned int)v12,
            v13[0]);
        WindowsDeleteString(string);
        if ( v15 )
          std::_Ref_count_base::_Decref(v15);
        result = v11;
      }
      else
      {
        if ( v15 )
          std::_Ref_count_base::_Decref(v15);
        result = 0;
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x172,
                             (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
                             v6);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004e95c  mov     [rsp+arg_0], rbx
0x18004e961  push    rdi
0x18004e962  sub     rsp, 40h
0x18004e966  mov     dil, dl
0x18004e969  mov     rbx, rcx
0x18004e96c  call    ?IsWnsAllowed_Impl@WnsProvider@@AEAAJXZ; WnsProvider::IsWnsAllowed_Impl(void)
0x18004e971  test    eax, eax
0x18004e973  js      loc_18004EAE4
0x18004e979  lea     rdx, [rsp+48h+var_20]
0x18004e97e  mov     rcx, rbx
0x18004e981  call    ?GetEnvironmentSettings@WnsProvider@@AEAA?AV?$shared_ptr@UWoscEnvironmentSettings@@@std@@XZ; WnsProvider::GetEnvironmentSettings(void)
0x18004e986  nop
0x18004e987  test    dil, dil
0x18004e98a  jnz     short loc_18004E9C3
0x18004e98c  mov     rdx, [rsp+48h+var_20]
0x18004e991  mov     rdx, [rdx+20h]; unsigned __int16 *
0x18004e995  mov     rcx, rbx; this
0x18004e998  call    ?IsRegisteredWithWoscService@WnsProvider@@AEAA_NPEBG@Z; WnsProvider::IsRegisteredWithWoscService(ushort const *)
0x18004e99d  test    al, al
0x18004e99f  jz      short loc_18004E9C3
0x18004e9a1  mov     rcx, rbx; this
0x18004e9a4  call    ?IsWnsChannelExpiring@WnsProvider@@AEAA_NK@Z; WnsProvider::IsWnsChannelExpiring(ulong)
0x18004e9a9  test    al, al
0x18004e9ab  jnz     short loc_18004E9C3
0x18004e9ad  mov     rcx, [rsp+48h+var_18]; this
0x18004e9b2  test    rcx, rcx
0x18004e9b5  jz      short loc_18004E9BC
0x18004e9b7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004e9bc  xor     eax, eax
0x18004e9be  jmp     loc_18004EAE4
0x18004e9c3  xor     r8d, r8d; bool *
0x18004e9c6  xor     edx, edx; bool
0x18004e9c8  mov     rcx, rbx; this
0x18004e9cb  call    ?RegisterForWns_Impl@WnsProvider@@AEAAJ_NPEA_N@Z; WnsProvider::RegisterForWns_Impl(bool,bool *)
0x18004e9d0  mov     rcx, [rsp+48h]; this
0x18004e9d5  test    eax, eax
0x18004e9d7  js      loc_18004EAEF
0x18004e9dd  xor     edx, edx; unsigned __int16 *
0x18004e9df  mov     rcx, [rbx+8]; this
0x18004e9e3  call    ?SetWnsRegisteredWithWoscService@ClientState@@QEAAXPEBG@Z; ClientState::SetWnsRegisteredWithWoscService(ushort const *)
0x18004e9e8  mov     rax, [rbx+8]
0x18004e9ec  mov     qword ptr [rax+1BCh], 0
0x18004e9f7  mov     rax, [rbx+8]
0x18004e9fb  mov     dword ptr [rax+1C4h], 0
0x18004ea05  mov     qword ptr [rsp+48h+var_28], 0; int
0x18004ea0e  xor     ecx, ecx; string
0x18004ea10  call    cs:__imp_WindowsDeleteString
0x18004ea16  mov     [rsp+48h+string], 0
0x18004ea1f  lea     r8, [rsp+48h+var_28]; struct Windows::Foundation::DateTime *
0x18004ea24  lea     rdx, [rsp+48h+string]; HSTRING *
0x18004ea29  mov     rcx, [rsp+48h+var_20]
0x18004ea2e  mov     rcx, [rcx+18h]; unsigned __int16 *
0x18004ea32  call    ?GetChannelUri@WnsProvider@@CAJPEBGPEAPEAUHSTRING__@@PEAUDateTime@Foundation@Windows@@@Z; WnsProvider::GetChannelUri(ushort const *,HSTRING__ * *,Windows::Foundation::DateTime *)
0x18004ea37  mov     rcx, [rsp+48h]; this
0x18004ea3c  test    eax, eax
0x18004ea3e  js      loc_18004EB04
0x18004ea44  mov     [rsp+48h+length], 0
0x18004ea4c  lea     rdx, [rsp+48h+length]; length
0x18004ea51  mov     rcx, [rsp+48h+string]; string
0x18004ea56  call    cs:__imp_WindowsGetStringRawBuffer
0x18004ea5c  mov     rdx, rax; unsigned __int16 *
0x18004ea5f  mov     rcx, [rsp+48h+var_20]
0x18004ea64  mov     rcx, [rcx+20h]; unsigned __int16 *
0x18004ea68  call    ?RegisterWNSChannelWithWosc@WnsProvider@@CAJPEBG0@Z; WnsProvider::RegisterWNSChannelWithWosc(ushort const *,ushort const *)
0x18004ea6d  mov     edi, eax
0x18004ea6f  mov     rcx, [rsp+48h]; this
0x18004ea74  test    eax, eax
0x18004ea76  js      loc_18004EB18
0x18004ea7c  mov     rdx, [rsp+48h+var_20]
0x18004ea81  mov     rdx, [rdx+20h]; unsigned __int16 *
0x18004ea85  mov     rcx, [rbx+8]; this
0x18004ea89  call    ?SetWnsRegisteredWithWoscService@ClientState@@QEAAXPEBG@Z; ClientState::SetWnsRegisteredWithWoscService(ushort const *)
0x18004ea8e  mov     rdx, qword ptr [rsp+48h+var_28]
0x18004ea93  mov     rcx, rbx
0x18004ea96  call    ?SaveWnsChannelExpiration@WnsProvider@@AEAAJUDateTime@Foundation@Windows@@@Z; WnsProvider::SaveWnsChannelExpiration(Windows::Foundation::DateTime)
0x18004ea9b  mov     rcx, rbx; this
0x18004ea9e  call    ?SaveWnsState_Impl@WnsProvider@@AEAAJXZ; WnsProvider::SaveWnsState_Impl(void)
0x18004eaa3  mov     rcx, [rsp+48h]; this
0x18004eaa8  test    eax, eax
0x18004eaaa  jns     short loc_18004EAC1
0x18004eaac  mov     r9d, eax; char *
0x18004eaaf  lea     r8, aOnecoreBaseFli_32; "onecore\\base\\flighting\\onesettings\\"...
0x18004eab6  mov     edx, 16Fh; void *
0x18004eabb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004eac0  nop
0x18004eac1  mov     rcx, [rsp+48h+string]; string
0x18004eac6  call    cs:__imp_WindowsDeleteString
0x18004eacc  nop
0x18004eacd  mov     rcx, [rsp+48h+var_18]; this
0x18004ead2  test    rcx, rcx
0x18004ead5  jz      short loc_18004EADC
0x18004ead7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004eadc  mov     eax, edi
0x18004eade  jmp     short loc_18004EAE4
0x18004eae0  mov     eax, [rsp+48h+length]
0x18004eae4  mov     rbx, [rsp+48h+arg_0]
0x18004eae9  add     rsp, 40h
0x18004eaed  pop     rdi
0x18004eaee  retn
0x18004eaef  mov     r9d, eax; char *
0x18004eaf2  lea     r8, aOnecoreBaseFli_32; "onecore\\base\\flighting\\onesettings\\"...
0x18004eaf9  mov     edx, 161h; void *
0x18004eafe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004eb04  mov     r9d, eax; char *
0x18004eb07  lea     r8, aOnecoreBaseFli_32; "onecore\\base\\flighting\\onesettings\\"...
0x18004eb0e  mov     edx, 167h; void *
0x18004eb13  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004eb18  mov     r9d, eax; char *
0x18004eb1b  lea     r8, aOnecoreBaseFli_32; "onecore\\base\\flighting\\onesettings\\"...
0x18004eb22  mov     edx, 16Ch; void *
0x18004eb27  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
