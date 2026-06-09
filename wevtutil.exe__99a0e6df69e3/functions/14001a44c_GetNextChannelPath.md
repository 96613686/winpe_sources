# GetNextChannelPath

- ea: `0x14001a44c`
- end: `0x14001a500`
- name: `GetNextChannelPath`
- size: `180`
- prototype: `__int64 __fastcall(EVT_HANDLE ChannelEnum, LPWSTR ChannelPathBuffer)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140025890`

## callees

- `0x14001a44c`
- `0x14001a774`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a498`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a4d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a498`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a4d6`
- `ext-ms-win-wevtapi-eventlog-l1-1-3!EvtNextChannelPath` at `0x14001a48e`
- `ext-ms-win-wevtapi-eventlog-l1-1-3!EvtNextChannelPath` at `0x14001a4cc`
- `ext-ms-win-wevtapi-eventlog-l1-1-3!EvtNextChannelPath` at `0x14001a48e`
- `ext-ms-win-wevtapi-eventlog-l1-1-3!EvtNextChannelPath` at `0x14001a4cc`

## pseudocode

```c
__int64 __fastcall GetNextChannelPath(EVT_HANDLE ChannelEnum, _QWORD *ChannelPathBuffer)
{
  DWORD LastError; // edi
  bool v5; // cc
  DWORD v6; // edx
  WCHAR *v7; // r8
  WCHAR *v8; // r8
  DWORD ChannelPathBufferUsed; // [rsp+38h] [rbp+10h] BYREF

  LastError = 0;
  std::wstring::resize(ChannelPathBuffer, 128);
  v5 = ChannelPathBuffer[3] <= 7u;
  v6 = *((_DWORD *)ChannelPathBuffer + 4);
  ChannelPathBufferUsed = v6;
  if ( v5 )
    v7 = (WCHAR *)ChannelPathBuffer;
  else
    v7 = (WCHAR *)*ChannelPathBuffer;
  if ( !EvtNextChannelPath(ChannelEnum, v6, v7, &ChannelPathBufferUsed) )
  {
    LastError = GetLastError();
    if ( LastError == 122 )
    {
      std::wstring::resize(ChannelPathBuffer, ChannelPathBufferUsed);
      if ( ChannelPathBuffer[3] <= 7u )
        v8 = (WCHAR *)ChannelPathBuffer;
      else
        v8 = (WCHAR *)*ChannelPathBuffer;
      if ( EvtNextChannelPath(ChannelEnum, ChannelPathBufferUsed, v8, &ChannelPathBufferUsed) )
      {
        LastError = 0;
        std::wstring::resize(ChannelPathBuffer, ChannelPathBufferUsed);
      }
      else
      {
        return GetLastError();
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x14001a44c  mov     [rsp+arg_0], rbx
0x14001a451  mov     [rsp+arg_10], rsi
0x14001a456  push    rdi
0x14001a457  sub     rsp, 20h
0x14001a45b  mov     rbx, rdx
0x14001a45e  mov     rsi, rcx
0x14001a461  mov     rcx, rbx
0x14001a464  mov     edx, 80h
0x14001a469  xor     edi, edi
0x14001a46b  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x14001a470  cmp     qword ptr [rbx+18h], 7
0x14001a475  mov     edx, [rbx+10h]; ChannelPathBufferSize
0x14001a478  mov     [rsp+28h+ChannelPathBufferUsed], edx
0x14001a47c  jbe     short loc_14001A483
0x14001a47e  mov     r8, [rbx]
0x14001a481  jmp     short loc_14001A486
0x14001a483  mov     r8, rbx; ChannelPathBuffer
0x14001a486  lea     r9, [rsp+28h+ChannelPathBufferUsed]; ChannelPathBufferUsed
0x14001a48b  mov     rcx, rsi; ChannelEnum
0x14001a48e  call    cs:__imp_EvtNextChannelPath
0x14001a494  test    eax, eax
0x14001a496  jnz     short loc_14001A4EE
0x14001a498  call    cs:__imp_GetLastError
0x14001a49e  mov     edi, eax
0x14001a4a0  cmp     eax, 7Ah ; 'z'
0x14001a4a3  jnz     short loc_14001A4EE
0x14001a4a5  mov     edx, [rsp+28h+ChannelPathBufferUsed]
0x14001a4a9  mov     rcx, rbx
0x14001a4ac  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x14001a4b1  cmp     qword ptr [rbx+18h], 7
0x14001a4b6  jbe     short loc_14001A4BD
0x14001a4b8  mov     r8, [rbx]
0x14001a4bb  jmp     short loc_14001A4C0
0x14001a4bd  mov     r8, rbx; ChannelPathBuffer
0x14001a4c0  mov     edx, [rsp+28h+ChannelPathBufferUsed]; ChannelPathBufferSize
0x14001a4c4  lea     r9, [rsp+28h+ChannelPathBufferUsed]; ChannelPathBufferUsed
0x14001a4c9  mov     rcx, rsi; ChannelEnum
0x14001a4cc  call    cs:__imp_EvtNextChannelPath
0x14001a4d2  test    eax, eax
0x14001a4d4  jnz     short loc_14001A4E0
0x14001a4d6  call    cs:__imp_GetLastError
0x14001a4dc  mov     edi, eax
0x14001a4de  jmp     short loc_14001A4EE
0x14001a4e0  mov     edx, [rsp+28h+ChannelPathBufferUsed]
0x14001a4e4  xor     edi, edi
0x14001a4e6  mov     rcx, rbx
0x14001a4e9  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x14001a4ee  mov     rbx, [rsp+28h+arg_0]
0x14001a4f3  mov     eax, edi
0x14001a4f5  mov     rsi, [rsp+28h+arg_10]
0x14001a4fa  add     rsp, 20h
0x14001a4fe  pop     rdi
0x14001a4ff  retn
```
