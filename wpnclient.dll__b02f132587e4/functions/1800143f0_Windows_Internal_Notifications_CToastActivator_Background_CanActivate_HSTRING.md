# Windows::Internal::Notifications::CToastActivator_Background::CanActivate(HSTRING__ *)

- ea: `0x1800143f0`
- end: `0x18001442b`
- name: `?CanActivate@CToastActivator_Background@Notifications@Internal@Windows@@AEAA_NPEAUHSTRING__@@@Z`
- size: `59`
- prototype: `bool(Windows::Internal::Notifications::CToastActivator_Background *__hidden this, HSTRING)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18001c270`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001441a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001441a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800143f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800143f9`

## pseudocode

```c
bool __fastcall Windows::Internal::Notifications::CToastActivator_Background::CanActivate(
        Windows::Internal::Notifications::CToastActivator_Background *this,
        HSTRING a2)
{
  const WCHAR *StringRawBuffer; // rax

  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  return CompareStringOrdinal(StringRawBuffer, -1, L"background", -1, 1) == 2;
}

```

## disassembly

```asm
0x1800143f0  sub     rsp, 38h
0x1800143f4  mov     rcx, rdx; string
0x1800143f7  xor     edx, edx; length
0x1800143f9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800143ff  mov     r9d, 0FFFFFFFFh; cchCount2
0x180014405  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18001440d  mov     edx, r9d; cchCount1
0x180014410  lea     r8, aBackground; "background"
0x180014417  mov     rcx, rax; lpString1
0x18001441a  call    cs:__imp_CompareStringOrdinal
0x180014420  cmp     eax, 2
0x180014423  setz    al
0x180014426  add     rsp, 38h
0x18001442a  retn
```
