# GetChannelPropertyName(ulong)

- ea: `0x14002f7fc`
- end: `0x14002f8fc`
- name: `?GetChannelPropertyName@@YAPEB_WK@Z`
- size: `256`
- prototype: `const wchar_t *__fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14002f704`
- `0x140031bd0`

## callees

- `0x14002f7fc`

## string_xrefs

- `0x14002f84f`: `ChannelAccess`
- `0x14002f8bc`: `SidType`
- `0x14002f82f`: `LogFilePath`

## pseudocode

```c
const wchar_t *__fastcall GetChannelPropertyName(unsigned int a1)
{
  unsigned int v1; // ecx
  unsigned int v2; // ecx
  unsigned int v3; // ecx
  unsigned int v4; // ecx
  unsigned int v5; // ecx
  unsigned int v6; // ecx
  unsigned int v7; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx

  if ( a1 <= 0xA )
  {
    if ( a1 == 10 )
      return L"Level";
    if ( !a1 )
      return L"Enabled";
    v1 = a1 - 1;
    if ( !v1 )
      return L"Isolation";
    v2 = v1 - 1;
    if ( !v2 )
      return L"Type";
    v3 = v2 - 2;
    if ( !v3 )
      return L"ClassicEventlog";
    v4 = v3 - 1;
    if ( !v4 )
      return L"ChannelAccess";
    v5 = v4 - 1;
    if ( !v5 )
      return L"Retention";
    v6 = v5 - 1;
    if ( !v6 )
      return L"AutoBackup";
    v7 = v6 - 1;
    if ( !v7 )
      return L"MaxSize";
    if ( v7 == 1 )
      return L"LogFilePath";
    return L"Unknown";
  }
  v9 = a1 - 11;
  if ( !v9 )
    return L"Keywords";
  v10 = v9 - 1;
  if ( !v10 )
    return L"ControlGuid";
  v11 = v10 - 1;
  if ( !v11 )
    return L"BufferSize";
  v12 = v11 - 1;
  if ( !v12 )
    return L"MinBuffers";
  v13 = v12 - 1;
  if ( !v13 )
    return L"MaxBuffers";
  v14 = v13 - 1;
  if ( !v14 )
    return L"Latency";
  v15 = v14 - 1;
  if ( !v15 )
    return L"ClockType";
  v16 = v15 - 1;
  if ( !v16 )
    return L"SidType";
  if ( v16 != 2 )
    return L"Unknown";
  return L"FileMax";
}

```

## disassembly

```asm
0x14002f7fc  cmp     ecx, 0Ah
0x14002f7ff  ja      short loc_14002F87F
0x14002f801  jz      short loc_14002F877
0x14002f803  test    ecx, ecx
0x14002f805  jz      short loc_14002F86F
0x14002f807  sub     ecx, 1
0x14002f80a  jz      short loc_14002F867
0x14002f80c  sub     ecx, 1
0x14002f80f  jz      short loc_14002F85F
0x14002f811  sub     ecx, 2
0x14002f814  jz      short loc_14002F857
0x14002f816  sub     ecx, 1
0x14002f819  jz      short loc_14002F84F
0x14002f81b  sub     ecx, 1
0x14002f81e  jz      short loc_14002F847
0x14002f820  sub     ecx, 1
0x14002f823  jz      short loc_14002F83F
0x14002f825  sub     ecx, 1
0x14002f828  jz      short loc_14002F837
0x14002f82a  cmp     ecx, 1
0x14002f82d  jnz     short loc_14002F8AC
0x14002f82f  lea     rax, aLogfilepath; "LogFilePath"
0x14002f836  retn
0x14002f837  lea     rax, aMaxsize_0; "MaxSize"
0x14002f83e  retn
0x14002f83f  lea     rax, aAutobackup_0; "AutoBackup"
0x14002f846  retn
0x14002f847  lea     rax, aRetention; "Retention"
0x14002f84e  retn
0x14002f84f  lea     rax, aChannelaccess_0; "ChannelAccess"
0x14002f856  retn
0x14002f857  lea     rax, aClassiceventlo; "ClassicEventlog"
0x14002f85e  retn
0x14002f85f  lea     rax, aType_0; "Type"
0x14002f866  retn
0x14002f867  lea     rax, aIsolation; "Isolation"
0x14002f86e  retn
0x14002f86f  lea     rax, aEnabled; "Enabled"
0x14002f876  retn
0x14002f877  lea     rax, aLevel_0; "Level"
0x14002f87e  retn
0x14002f87f  sub     ecx, 0Bh
0x14002f882  jz      short loc_14002F8F4
0x14002f884  sub     ecx, 1
0x14002f887  jz      short loc_14002F8EC
0x14002f889  sub     ecx, 1
0x14002f88c  jz      short loc_14002F8E4
0x14002f88e  sub     ecx, 1
0x14002f891  jz      short loc_14002F8DC
0x14002f893  sub     ecx, 1
0x14002f896  jz      short loc_14002F8D4
0x14002f898  sub     ecx, 1
0x14002f89b  jz      short loc_14002F8CC
0x14002f89d  sub     ecx, 1
0x14002f8a0  jz      short loc_14002F8C4
0x14002f8a2  sub     ecx, 1
0x14002f8a5  jz      short loc_14002F8BC
0x14002f8a7  cmp     ecx, 2
0x14002f8aa  jz      short loc_14002F8B4
0x14002f8ac  lea     rax, aUnknown; "Unknown"
0x14002f8b3  retn
0x14002f8b4  lea     rax, aFilemax; "FileMax"
0x14002f8bb  retn
0x14002f8bc  lea     rax, aSidtype; "SidType"
0x14002f8c3  retn
0x14002f8c4  lea     rax, aClocktype; "ClockType"
0x14002f8cb  retn
0x14002f8cc  lea     rax, aLatency; "Latency"
0x14002f8d3  retn
0x14002f8d4  lea     rax, aMaxbuffers_0; "MaxBuffers"
0x14002f8db  retn
0x14002f8dc  lea     rax, aMinbuffers; "MinBuffers"
0x14002f8e3  retn
0x14002f8e4  lea     rax, aBuffersize_0; "BufferSize"
0x14002f8eb  retn
0x14002f8ec  lea     rax, aControlguid; "ControlGuid"
0x14002f8f3  retn
0x14002f8f4  lea     rax, aKeywords_0; "Keywords"
0x14002f8fb  retn
```
