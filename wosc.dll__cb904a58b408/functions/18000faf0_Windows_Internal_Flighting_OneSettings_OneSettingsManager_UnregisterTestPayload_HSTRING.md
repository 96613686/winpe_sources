# Windows::Internal::Flighting::OneSettings::OneSettingsManager::UnregisterTestPayload(HSTRING__ *)

- ea: `0x18000faf0`
- end: `0x18000fb64`
- name: `?UnregisterTestPayload@OneSettingsManager@OneSettings@Flighting@Internal@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `116`
- prototype: `int(Windows::Internal::Flighting::OneSettings::OneSettingsManager *__hidden this, HSTRING)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180008a80`
- `0x18000a194`
- `0x18000faf0`
- `0x18002a954`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fb2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fb2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000fafe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000fafe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::Flighting::OneSettings::OneSettingsManager::UnregisterTestPayload(
        Windows::Internal::Flighting::OneSettings::OneSettingsManager *this,
        HSTRING a2)
{
  unsigned __int16 *StringRawBuffer; // rax
  ClientState *v3; // rbx
  HSTRING v4; // rcx
  const char *v5; // r9
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  ClientState *v8; // [rsp+40h] [rbp+18h] BYREF
  unsigned __int16 *v9; // [rsp+48h] [rbp+20h] BYREF

  StringRawBuffer = (unsigned __int16 *)WindowsGetStringRawBuffer(a2, 0);
  v9 = StringRawBuffer;
  try
  {
    std::make_unique<ClientState,unsigned short const * &,0>(&v8, &v9);
    v3 = v8;
    v4 = (HSTRING)*((_QWORD *)v8 + 42);
    if ( v4 )
    {
      WindowsDeleteString(v4);
      *((_QWORD *)v3 + 42) = 0;
    }
    ClientState::SaveRegData(v3, *((HKEY *)v3 + 52));
    std::_Temporary_owner<ClientState>::~_Temporary_owner<ClientState>(&v8);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xB3,
                           (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\onesettingsmanager.cpp",
                           v5);
  }
  return result;
}

```

## disassembly

```asm
0x18000faf0  push    rbx
0x18000faf2  sub     rsp, 20h
0x18000faf6  mov     rax, rdx
0x18000faf9  xor     edx, edx; length
0x18000fafb  mov     rcx, rax; string
0x18000fafe  call    cs:__imp_WindowsGetStringRawBuffer
0x18000fb04  mov     [rsp+28h+arg_18], rax
0x18000fb09  lea     rdx, [rsp+28h+arg_18]
0x18000fb0e  lea     rcx, [rsp+28h+arg_10]
0x18000fb13  call    ??$make_unique@VClientState@@AEAPEBG$0A@@std@@YA?AV?$unique_ptr@VClientState@@U?$default_delete@VClientState@@@std@@@0@AEAPEBG@Z; std::make_unique<ClientState,ushort const * &,0>(ushort const * &)
0x18000fb18  nop
0x18000fb19  mov     rbx, [rsp+28h+arg_10]
0x18000fb1e  mov     rcx, [rbx+150h]; string
0x18000fb25  test    rcx, rcx
0x18000fb28  jz      short loc_18000FB3B
0x18000fb2a  call    cs:__imp_WindowsDeleteString
0x18000fb30  mov     qword ptr [rbx+150h], 0
0x18000fb3b  mov     rdx, [rbx+1A0h]; HKEY
0x18000fb42  mov     rcx, rbx; this
0x18000fb45  call    ?SaveRegData@ClientState@@AEBAXPEAUHKEY__@@@Z; ClientState::SaveRegData(HKEY__ *)
0x18000fb4a  nop
0x18000fb4b  lea     rcx, [rsp+28h+arg_10]
0x18000fb50  call    ??1?$_Temporary_owner@VClientState@@@std@@QEAA@XZ; std::_Temporary_owner<ClientState>::~_Temporary_owner<ClientState>(void)
0x18000fb55  xor     eax, eax
0x18000fb57  jmp     short loc_18000FB5D
0x18000fb59  mov     eax, dword ptr [rsp+28h+arg_10]
0x18000fb5d  add     rsp, 20h
0x18000fb61  pop     rbx
0x18000fb62  retn
```
