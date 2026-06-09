# GetChannelPropertyName(ulong)

- ea: `0x1800308cc`
- end: `0x1800309cc`
- name: `?GetChannelPropertyName@@YAPEB_WK@Z`
- size: `256`
- prototype: `const wchar_t *__fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800307dc`

## callees

- `0x1800308cc`

## string_xrefs

- `0x18003091f`: `ChannelAccess`
- `0x1800308ff`: `LogFilePath`
- `0x18003098c`: `SidType`

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
0x1800308cc  cmp     ecx, 0Ah
0x1800308cf  ja      short loc_18003094F
0x1800308d1  jz      short loc_180030947
0x1800308d3  test    ecx, ecx
0x1800308d5  jz      short loc_18003093F
0x1800308d7  sub     ecx, 1
0x1800308da  jz      short loc_180030937
0x1800308dc  sub     ecx, 1
0x1800308df  jz      short loc_18003092F
0x1800308e1  sub     ecx, 2
0x1800308e4  jz      short loc_180030927
0x1800308e6  sub     ecx, 1
0x1800308e9  jz      short loc_18003091F
0x1800308eb  sub     ecx, 1
0x1800308ee  jz      short loc_180030917
0x1800308f0  sub     ecx, 1
0x1800308f3  jz      short loc_18003090F
0x1800308f5  sub     ecx, 1
0x1800308f8  jz      short loc_180030907
0x1800308fa  cmp     ecx, 1
0x1800308fd  jnz     short loc_18003097C
0x1800308ff  lea     rax, aLogfilepath; "LogFilePath"
0x180030906  retn
0x180030907  lea     rax, aMaxsize; "MaxSize"
0x18003090e  retn
0x18003090f  lea     rax, aAutobackup; "AutoBackup"
0x180030916  retn
0x180030917  lea     rax, aRetention; "Retention"
0x18003091e  retn
0x18003091f  lea     rax, aChannelaccess; "ChannelAccess"
0x180030926  retn
0x180030927  lea     rax, aClassiceventlo; "ClassicEventlog"
0x18003092e  retn
0x18003092f  lea     rax, aType; "Type"
0x180030936  retn
0x180030937  lea     rax, aIsolation; "Isolation"
0x18003093e  retn
0x18003093f  lea     rax, aEnabled; "Enabled"
0x180030946  retn
0x180030947  lea     rax, aLevel_1; "Level"
0x18003094e  retn
0x18003094f  sub     ecx, 0Bh
0x180030952  jz      short loc_1800309C4
0x180030954  sub     ecx, 1
0x180030957  jz      short loc_1800309BC
0x180030959  sub     ecx, 1
0x18003095c  jz      short loc_1800309B4
0x18003095e  sub     ecx, 1
0x180030961  jz      short loc_1800309AC
0x180030963  sub     ecx, 1
0x180030966  jz      short loc_1800309A4
0x180030968  sub     ecx, 1
0x18003096b  jz      short loc_18003099C
0x18003096d  sub     ecx, 1
0x180030970  jz      short loc_180030994
0x180030972  sub     ecx, 1
0x180030975  jz      short loc_18003098C
0x180030977  cmp     ecx, 2
0x18003097a  jz      short loc_180030984
0x18003097c  lea     rax, aUnknown; "Unknown"
0x180030983  retn
0x180030984  lea     rax, aFilemax; "FileMax"
0x18003098b  retn
0x18003098c  lea     rax, aSidtype; "SidType"
0x180030993  retn
0x180030994  lea     rax, aClocktype; "ClockType"
0x18003099b  retn
0x18003099c  lea     rax, aLatency; "Latency"
0x1800309a3  retn
0x1800309a4  lea     rax, aMaxbuffers; "MaxBuffers"
0x1800309ab  retn
0x1800309ac  lea     rax, aMinbuffers; "MinBuffers"
0x1800309b3  retn
0x1800309b4  lea     rax, aBuffersize; "BufferSize"
0x1800309bb  retn
0x1800309bc  lea     rax, aControlguid; "ControlGuid"
0x1800309c3  retn
0x1800309c4  lea     rax, aKeywords_1; "Keywords"
0x1800309cb  retn
```
