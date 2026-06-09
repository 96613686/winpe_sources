# Windows::Internal::Notifications::CToastActivator_AppLaunch::CanActivate(HSTRING__ *,HSTRING__ *)

- ea: `0x180013f50`
- end: `0x180013fad`
- name: `?CanActivate@CToastActivator_AppLaunch@Notifications@Internal@Windows@@AEAA_NPEAUHSTRING__@@0@Z`
- size: `93`
- prototype: `bool(Windows::Internal::Notifications::CToastActivator_AppLaunch *__hidden this, HSTRING, HSTRING)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180026d70`

## callees

- `0x180013f50`
- `0x180016e44`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013f7f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013f7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013f5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013f97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013f5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013f97`

## pseudocode

```c
bool __fastcall Windows::Internal::Notifications::CToastActivator_AppLaunch::CanActivate(
        Windows::Internal::Notifications::CToastActivator_AppLaunch *this,
        HSTRING a2,
        HSTRING a3)
{
  const WCHAR *StringRawBuffer; // rax
  bool result; // al
  const unsigned __int16 *v6; // rax
  Windows::Internal::Notifications::CToastActivator_AppLaunch *v7; // rcx

  StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
  result = 0;
  if ( CompareStringOrdinal(StringRawBuffer, -1, L"applaunch", -1, 1) == 2 )
  {
    v6 = WindowsGetStringRawBuffer(a2, 0);
    if ( Windows::Internal::Notifications::CToastActivator_AppLaunch::IsAppCapable(v7, v6) )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180013f50  push    rbx
0x180013f52  sub     rsp, 30h
0x180013f56  mov     rbx, rdx
0x180013f59  mov     rcx, r8; string
0x180013f5c  xor     edx, edx; length
0x180013f5e  call    cs:__imp_WindowsGetStringRawBuffer
0x180013f64  mov     r9d, 0FFFFFFFFh; cchCount2
0x180013f6a  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180013f72  mov     edx, r9d; cchCount1
0x180013f75  lea     r8, aApplaunch; "applaunch"
0x180013f7c  mov     rcx, rax; lpString1
0x180013f7f  call    cs:__imp_CompareStringOrdinal
0x180013f85  cmp     eax, 2
0x180013f88  jz      short loc_180013F92
0x180013f8a  xor     al, al
0x180013f8c  add     rsp, 30h
0x180013f90  pop     rbx
0x180013f91  retn
0x180013f92  xor     edx, edx; length
0x180013f94  mov     rcx, rbx; string
0x180013f97  call    cs:__imp_WindowsGetStringRawBuffer
0x180013f9d  mov     rdx, rax; unsigned __int16 *
0x180013fa0  call    ?IsAppCapable@CToastActivator_AppLaunch@Notifications@Internal@Windows@@AEAA_NPEBG@Z; Windows::Internal::Notifications::CToastActivator_AppLaunch::IsAppCapable(ushort const *)
0x180013fa5  test    al, al
0x180013fa7  jz      short loc_180013F8A
0x180013fa9  mov     al, 1
0x180013fab  jmp     short loc_180013F8C
```
