# Windows::Internal::Notifications::CToastActivator_Foreground::CanActivate(HSTRING__ *,HSTRING__ *)

- ea: `0x1800101f0`
- end: `0x180010268`
- name: `?CanActivate@CToastActivator_Foreground@Notifications@Internal@Windows@@AEAA_NPEAUHSTRING__@@0@Z`
- size: `120`
- prototype: `bool(Windows::Internal::Notifications::CToastActivator_Foreground *__hidden this, HSTRING, HSTRING)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800186f0`

## callees

- `0x1800101f0`
- `0x180010270`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180010226`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180010226`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180010205`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180010249`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180010205`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180010249`

## pseudocode

```c
bool __fastcall Windows::Internal::Notifications::CToastActivator_Foreground::CanActivate(
        Windows::Internal::Notifications::CToastActivator_Foreground *this,
        HSTRING a2,
        HSTRING a3)
{
  const WCHAR *StringRawBuffer; // rax
  bool result; // al
  const unsigned __int16 *v7; // rax
  Windows::Internal::Notifications::CToastActivator_Foreground *v8; // rcx

  StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
  result = 0;
  if ( CompareStringOrdinal(StringRawBuffer, -1, L"foreground", -1, 1) == 2 )
  {
    if ( *((_BYTE *)this + 104) )
      return 1;
    v7 = WindowsGetStringRawBuffer(a2, 0);
    if ( Windows::Internal::Notifications::CToastActivator_Foreground::IsModernApp(v8, v7) )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800101f0  mov     [rsp+arg_0], rbx
0x1800101f5  push    rdi
0x1800101f6  sub     rsp, 30h
0x1800101fa  mov     rdi, rdx
0x1800101fd  mov     rbx, rcx
0x180010200  xor     edx, edx; length
0x180010202  mov     rcx, r8; string
0x180010205  call    cs:__imp_WindowsGetStringRawBuffer
0x18001020b  mov     r9d, 0FFFFFFFFh; cchCount2
0x180010211  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180010219  mov     edx, r9d; cchCount1
0x18001021c  lea     r8, aForeground; "foreground"
0x180010223  mov     rcx, rax; lpString1
0x180010226  call    cs:__imp_CompareStringOrdinal
0x18001022c  cmp     eax, 2
0x18001022f  jz      short loc_18001023E
0x180010231  xor     al, al
0x180010233  mov     rbx, [rsp+38h+arg_0]
0x180010238  add     rsp, 30h
0x18001023c  pop     rdi
0x18001023d  retn
0x18001023e  cmp     byte ptr [rbx+68h], 0
0x180010242  jnz     short loc_18001025B
0x180010244  xor     edx, edx; length
0x180010246  mov     rcx, rdi; string
0x180010249  call    cs:__imp_WindowsGetStringRawBuffer
0x18001024f  mov     rdx, rax; unsigned __int16 *
0x180010252  call    ?IsModernApp@CToastActivator_Foreground@Notifications@Internal@Windows@@AEAA_NPEBG@Z; Windows::Internal::Notifications::CToastActivator_Foreground::IsModernApp(ushort const *)
0x180010257  test    al, al
0x180010259  jz      short loc_180010231
0x18001025b  mov     rbx, [rsp+38h+arg_0]
0x180010260  mov     al, 1
0x180010262  add     rsp, 30h
0x180010266  pop     rdi
0x180010267  retn
```
