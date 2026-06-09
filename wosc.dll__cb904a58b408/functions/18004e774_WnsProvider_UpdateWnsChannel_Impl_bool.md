# WnsProvider::UpdateWnsChannel_Impl(bool)

- ea: `0x18004e774`
- end: `0x18004e954`
- name: `?UpdateWnsChannel_Impl@WnsProvider@@AEAAJ_N@Z`
- size: `480`
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
- `0x18004e774`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e82a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e8bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e82a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e8bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004e870`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004e870`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WnsProvider::UpdateWnsChannel_Impl(ClientState **this, char a2)
{
  __int64 result; // rax
  int v5; // eax
  unsigned int v6; // edi
  unsigned int v7; // edx
  const char *v8; // r9
  char v9; // si
  int ChannelUri; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  int v12; // eax
  int v13; // eax
  int v14[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v15; // [rsp+28h] [rbp-20h] BYREF
  std::_Ref_count_base *v16; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  UINT32 length; // [rsp+60h] [rbp+18h] BYREF
  HSTRING string; // [rsp+68h] [rbp+20h] BYREF

  result = WnsProvider::IsWnsAllowed_Impl((WnsProvider *)this);
  if ( (int)result >= 0 )
  {
    LOBYTE(length) = 0;
    v5 = WnsProvider::RegisterForWns_Impl((WnsProvider *)this, 0, (bool *)&length);
    try
    {
      v6 = v5;
      if ( v5 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x187,
          (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
          (const char *)(unsigned int)v5,
          v14[0]);
      WnsProvider::GetEnvironmentSettings(this, &v15);
      if ( a2
        || !WnsProvider::IsRegisteredWithWoscService((WnsProvider *)this, *(const unsigned __int16 **)(v15 + 32))
        || WnsProvider::IsWnsChannelExpiring((WnsProvider *)this, v7) )
      {
        ClientState::SetWnsRegisteredWithWoscService(this[1], 0);
        *(_QWORD *)((char *)this[1] + 444) = 0;
        *((_DWORD *)this[1] + 113) = 0;
        *(_QWORD *)v14 = 0;
        WindowsDeleteString(0);
        string = 0;
        ChannelUri = WnsProvider::GetChannelUri(
                       *(const unsigned __int16 **)(v15 + 24),
                       &string,
                       (struct Windows::Foundation::DateTime *)v14);
        if ( ChannelUri < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x191,
            (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
            (const char *)(unsigned int)ChannelUri,
            v14[0]);
        length = 0;
        StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
        v12 = WnsProvider::RegisterWNSChannelWithWosc(*(const unsigned __int16 **)(v15 + 32), StringRawBuffer);
        v6 = v12;
        if ( v12 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x196,
            (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
            (const char *)(unsigned int)v12,
            v14[0]);
        ClientState::SetWnsRegisteredWithWoscService(this[1], *(unsigned __int16 **)(v15 + 32));
        WnsProvider::SaveWnsChannelExpiration(this, *(_QWORD *)v14);
        v9 = 1;
        WindowsDeleteString(string);
      }
      else
      {
        v9 = length;
      }
      if ( v9 )
      {
        v13 = WnsProvider::SaveWnsState_Impl((WnsProvider *)this);
        if ( v13 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x19F,
            (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
            (const char *)(unsigned int)v13,
            v14[0]);
      }
      if ( v16 )
        std::_Ref_count_base::_Decref(v16);
      result = v6;
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x1A3,
                             (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
                             v8);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004e774  mov     [rsp+arg_0], rbx
0x18004e779  mov     [rsp+arg_8], rsi
0x18004e77e  push    rdi
0x18004e77f  sub     rsp, 40h
0x18004e783  mov     sil, dl
0x18004e786  mov     rbx, rcx
0x18004e789  call    ?IsWnsAllowed_Impl@WnsProvider@@AEAAJXZ; WnsProvider::IsWnsAllowed_Impl(void)
0x18004e78e  test    eax, eax
0x18004e790  js      loc_18004E905
0x18004e796  mov     byte ptr [rsp+48h+length], 0
0x18004e79b  lea     r8, [rsp+48h+length]; bool *
0x18004e7a0  xor     edx, edx; bool
0x18004e7a2  mov     rcx, rbx; this
0x18004e7a5  call    ?RegisterForWns_Impl@WnsProvider@@AEAAJ_NPEA_N@Z; WnsProvider::RegisterForWns_Impl(bool,bool *)
0x18004e7aa  mov     edi, eax
0x18004e7ac  mov     rcx, [rsp+48h]; this
0x18004e7b1  test    eax, eax
0x18004e7b3  js      loc_18004E915
0x18004e7b9  lea     rdx, [rsp+48h+var_20]
0x18004e7be  mov     rcx, rbx
0x18004e7c1  call    ?GetEnvironmentSettings@WnsProvider@@AEAA?AV?$shared_ptr@UWoscEnvironmentSettings@@@std@@XZ; WnsProvider::GetEnvironmentSettings(void)
0x18004e7c6  nop
0x18004e7c7  test    sil, sil
0x18004e7ca  jnz     short loc_18004E7F7
0x18004e7cc  mov     rdx, [rsp+48h+var_20]
0x18004e7d1  mov     rdx, [rdx+20h]; unsigned __int16 *
0x18004e7d5  mov     rcx, rbx; this
0x18004e7d8  call    ?IsRegisteredWithWoscService@WnsProvider@@AEAA_NPEBG@Z; WnsProvider::IsRegisteredWithWoscService(ushort const *)
0x18004e7dd  test    al, al
0x18004e7df  jz      short loc_18004E7F7
0x18004e7e1  mov     rcx, rbx; this
0x18004e7e4  call    ?IsWnsChannelExpiring@WnsProvider@@AEAA_NK@Z; WnsProvider::IsWnsChannelExpiring(ulong)
0x18004e7e9  test    al, al
0x18004e7eb  jnz     short loc_18004E7F7
0x18004e7ed  mov     sil, byte ptr [rsp+48h+length]
0x18004e7f2  jmp     loc_18004E8C3
0x18004e7f7  xor     edx, edx; unsigned __int16 *
0x18004e7f9  mov     rcx, [rbx+8]; this
0x18004e7fd  call    ?SetWnsRegisteredWithWoscService@ClientState@@QEAAXPEBG@Z; ClientState::SetWnsRegisteredWithWoscService(ushort const *)
0x18004e802  mov     rax, [rbx+8]
0x18004e806  mov     qword ptr [rax+1BCh], 0
0x18004e811  mov     rax, [rbx+8]
0x18004e815  mov     dword ptr [rax+1C4h], 0
0x18004e81f  mov     qword ptr [rsp+48h+var_28], 0; int
0x18004e828  xor     ecx, ecx; string
0x18004e82a  call    cs:__imp_WindowsDeleteString
0x18004e830  mov     [rsp+48h+string], 0
0x18004e839  lea     r8, [rsp+48h+var_28]; struct Windows::Foundation::DateTime *
0x18004e83e  lea     rdx, [rsp+48h+string]; HSTRING *
0x18004e843  mov     rcx, [rsp+48h+var_20]
0x18004e848  mov     rcx, [rcx+18h]; unsigned __int16 *
0x18004e84c  call    ?GetChannelUri@WnsProvider@@CAJPEBGPEAPEAUHSTRING__@@PEAUDateTime@Foundation@Windows@@@Z; WnsProvider::GetChannelUri(ushort const *,HSTRING__ * *,Windows::Foundation::DateTime *)
0x18004e851  mov     rcx, [rsp+48h]; this
0x18004e856  test    eax, eax
0x18004e858  js      loc_18004E92A
0x18004e85e  mov     [rsp+48h+length], 0
0x18004e866  lea     rdx, [rsp+48h+length]; length
0x18004e86b  mov     rcx, [rsp+48h+string]; string
0x18004e870  call    cs:__imp_WindowsGetStringRawBuffer
0x18004e876  mov     rdx, rax; unsigned __int16 *
0x18004e879  mov     rcx, [rsp+48h+var_20]
0x18004e87e  mov     rcx, [rcx+20h]; unsigned __int16 *
0x18004e882  call    ?RegisterWNSChannelWithWosc@WnsProvider@@CAJPEBG0@Z; WnsProvider::RegisterWNSChannelWithWosc(ushort const *,ushort const *)
0x18004e887  mov     edi, eax
0x18004e889  mov     rcx, [rsp+48h]; this
0x18004e88e  test    eax, eax
0x18004e890  js      loc_18004E93E
0x18004e896  mov     rdx, [rsp+48h+var_20]
0x18004e89b  mov     rdx, [rdx+20h]; unsigned __int16 *
0x18004e89f  mov     rcx, [rbx+8]; this
0x18004e8a3  call    ?SetWnsRegisteredWithWoscService@ClientState@@QEAAXPEBG@Z; ClientState::SetWnsRegisteredWithWoscService(ushort const *)
0x18004e8a8  mov     rdx, qword ptr [rsp+48h+var_28]
0x18004e8ad  mov     rcx, rbx
0x18004e8b0  call    ?SaveWnsChannelExpiration@WnsProvider@@AEAAJUDateTime@Foundation@Windows@@@Z; WnsProvider::SaveWnsChannelExpiration(Windows::Foundation::DateTime)
0x18004e8b5  mov     sil, 1
0x18004e8b8  mov     rcx, [rsp+48h+string]; string
0x18004e8bd  call    cs:__imp_WindowsDeleteString
0x18004e8c3  test    sil, sil
0x18004e8c6  jz      short loc_18004E8EE
0x18004e8c8  mov     rcx, rbx; this
0x18004e8cb  call    ?SaveWnsState_Impl@WnsProvider@@AEAAJXZ; WnsProvider::SaveWnsState_Impl(void)
0x18004e8d0  mov     rcx, [rsp+48h]; this
0x18004e8d5  test    eax, eax
0x18004e8d7  jns     short loc_18004E8EE
0x18004e8d9  mov     r9d, eax; char *
0x18004e8dc  lea     r8, aOnecoreBaseFli_32; "onecore\\base\\flighting\\onesettings\\"...
0x18004e8e3  mov     edx, 19Fh; void *
0x18004e8e8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004e8ed  nop
0x18004e8ee  mov     rcx, [rsp+48h+var_18]; this
0x18004e8f3  test    rcx, rcx
0x18004e8f6  jz      short loc_18004E8FD
0x18004e8f8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004e8fd  mov     eax, edi
0x18004e8ff  jmp     short loc_18004E905
0x18004e901  mov     eax, [rsp+48h+length]
0x18004e905  mov     rbx, [rsp+48h+arg_0]
0x18004e90a  mov     rsi, [rsp+48h+arg_8]
0x18004e90f  add     rsp, 40h
0x18004e913  pop     rdi
0x18004e914  retn
0x18004e915  mov     r9d, eax; char *
0x18004e918  lea     r8, aOnecoreBaseFli_32; "onecore\\base\\flighting\\onesettings\\"...
0x18004e91f  mov     edx, 187h; void *
0x18004e924  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004e92a  mov     r9d, eax; char *
0x18004e92d  lea     r8, aOnecoreBaseFli_32; "onecore\\base\\flighting\\onesettings\\"...
0x18004e934  mov     edx, 191h; void *
0x18004e939  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004e93e  mov     r9d, eax; char *
0x18004e941  lea     r8, aOnecoreBaseFli_32; "onecore\\base\\flighting\\onesettings\\"...
0x18004e948  mov     edx, 196h; void *
0x18004e94d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
