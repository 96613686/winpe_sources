# Windows::Internal::Flighting::OneSettings::OneSettingsPayload::RuntimeClassInitialize(ushort const *,ushort const *,bool)

- ea: `0x1800197a8`
- end: `0x180019827`
- name: `?RuntimeClassInitialize@OneSettingsPayload@OneSettings@Flighting@Internal@Windows@@QEAAJPEBG0_N@Z`
- size: `127`
- prototype: `__int64 __fastcall(Windows::Internal::Flighting::OneSettings::OneSettingsPayload *__hidden this, const unsigned __int16 *, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800203c4`
- `0x18002c968`

## callees

- `0x1800156e4`
- `0x180017714`
- `0x180017c50`
- `0x180017d80`
- `0x1800197a8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800197d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019816`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800197d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019816`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800197ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800197ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::Flighting::OneSettings::OneSettingsPayload::RuntimeClassInitialize(
        Windows::Internal::Flighting::OneSettings::OneSettingsPayload *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char a4)
{
  int v7; // edx
  HSTRING StringFromFile; // rbx
  const unsigned __int16 *StringRawBuffer; // rax

  Windows::Internal::Flighting::OneSettings::OneSettingsPayload::InitState((__int64)this, a2);
  StringFromFile = FileContentPurveyor::CreateStringFromFile(a3, v7);
  WindowsDeleteString(0);
  if ( StringFromFile )
    StringRawBuffer = WindowsGetStringRawBuffer(StringFromFile, 0);
  else
    StringRawBuffer = 0;
  Windows::Internal::Flighting::OneSettings::OneSettingsPayload::InitJsonSettings(this, StringRawBuffer);
  if ( a4 )
    Windows::Internal::Flighting::OneSettings::OneSettingsPayload::InitDefaultJsonSettings(this, a3);
  WindowsDeleteString(StringFromFile);
  return 0;
}

```

## disassembly

```asm
0x1800197a8  push    rbx
0x1800197aa  push    rbp
0x1800197ab  push    rsi
0x1800197ac  push    rdi
0x1800197ad  sub     rsp, 38h
0x1800197b1  mov     bpl, r9b
0x1800197b4  mov     rsi, r8
0x1800197b7  mov     rdi, rcx
0x1800197ba  xor     r8d, r8d
0x1800197bd  call    ?InitState@OneSettingsPayload@OneSettings@Flighting@Internal@Windows@@AEAAXPEBGPEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@5@@Z; Windows::Internal::Flighting::OneSettings::OneSettingsPayload::InitState(ushort const *,Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *)
0x1800197c2  mov     [rsp+58h+var_38], 0
0x1800197cb  mov     rcx, rsi; lpSrc
0x1800197ce  call    ?CreateStringFromFile@FileContentPurveyor@@SAPEAUHSTRING__@@PEBGI@Z; FileContentPurveyor::CreateStringFromFile(ushort const *,uint)
0x1800197d3  mov     rbx, rax
0x1800197d6  xor     ecx, ecx; string
0x1800197d8  call    cs:__imp_WindowsDeleteString
0x1800197de  mov     [rsp+58h+var_38], rbx
0x1800197e3  test    rbx, rbx
0x1800197e6  jz      short loc_1800197F5
0x1800197e8  xor     edx, edx; length
0x1800197ea  mov     rcx, rbx; string
0x1800197ed  call    cs:__imp_WindowsGetStringRawBuffer
0x1800197f3  jmp     short loc_1800197F7
0x1800197f5  xor     eax, eax
0x1800197f7  mov     rdx, rax; unsigned __int16 *
0x1800197fa  mov     rcx, rdi; this
0x1800197fd  call    ?InitJsonSettings@OneSettingsPayload@OneSettings@Flighting@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::Flighting::OneSettings::OneSettingsPayload::InitJsonSettings(ushort const *)
0x180019802  test    bpl, bpl
0x180019805  jz      short loc_180019813
0x180019807  mov     rdx, rsi; unsigned __int16 *
0x18001980a  mov     rcx, rdi; this
0x18001980d  call    ?InitDefaultJsonSettings@OneSettingsPayload@OneSettings@Flighting@Internal@Windows@@QEAAXPEBG@Z; Windows::Internal::Flighting::OneSettings::OneSettingsPayload::InitDefaultJsonSettings(ushort const *)
0x180019812  nop
0x180019813  mov     rcx, rbx; string
0x180019816  call    cs:__imp_WindowsDeleteString
0x18001981c  xor     eax, eax
0x18001981e  add     rsp, 38h
0x180019822  pop     rdi
0x180019823  pop     rsi
0x180019824  pop     rbp
0x180019825  pop     rbx
0x180019826  retn
```
