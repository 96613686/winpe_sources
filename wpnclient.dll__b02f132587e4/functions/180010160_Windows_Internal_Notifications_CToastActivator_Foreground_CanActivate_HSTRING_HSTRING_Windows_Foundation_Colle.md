# Windows::Internal::Notifications::CToastActivator_Foreground::CanActivate(HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IPropertySet *,uchar *)

- ea: `0x180010160`
- end: `0x1800101dc`
- name: `?CanActivate@CToastActivator_Foreground@Notifications@Internal@Windows@@UEAAJPEAUHSTRING__@@0PEAUIPropertySet@Collections@Foundation@4@PEAE@Z`
- size: `124`
- prototype: `int(Windows::Internal::Notifications::CToastActivator_Foreground *__hidden this, HSTRING, HSTRING, struct Windows::Foundation::Collections::IPropertySet *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180010160`
- `0x180010270`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001019c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001019c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001017d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800101c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001017d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800101c2`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Notifications::CToastActivator_Foreground::CanActivate(
        Windows::Internal::Notifications::CToastActivator_Foreground *this,
        HSTRING a2,
        HSTRING a3,
        struct Windows::Foundation::Collections::IPropertySet *a4,
        unsigned __int8 *a5)
{
  const WCHAR *StringRawBuffer; // rax
  unsigned __int8 v8; // bl
  const unsigned __int16 *v10; // rax
  Windows::Internal::Notifications::CToastActivator_Foreground *v11; // rcx
  bool IsModernApp; // al
  const char *v13; // r9
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
  v8 = 1;
  if ( CompareStringOrdinal(StringRawBuffer, -1, L"foreground", -1, 1) != 2 )
    goto LABEL_2;
  if ( !*((_BYTE *)this + 56) )
  {
    v10 = WindowsGetStringRawBuffer(a2, 0);
    try
    {
      IsModernApp = Windows::Internal::Notifications::CToastActivator_Foreground::IsModernApp(v11, v10);
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0xA8,
                             (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastacti"
                                           "vator_foreground.cpp",
                             v13);
    }
    if ( !IsModernApp )
LABEL_2:
      v8 = 0;
  }
  *a5 = v8;
  return 0;
}

```

## disassembly

```asm
0x180010160  push    rbx
0x180010162  push    rsi
0x180010163  push    rdi
0x180010164  push    r14
0x180010166  sub     rsp, 48h
0x18001016a  mov     r14, rdx
0x18001016d  mov     rdi, rcx
0x180010170  mov     rsi, [rsp+68h+arg_20]
0x180010178  xor     edx, edx; length
0x18001017a  mov     rcx, r8; string
0x18001017d  call    cs:__imp_WindowsGetStringRawBuffer
0x180010183  mov     ebx, 1
0x180010188  mov     [rsp+68h+bIgnoreCase], ebx; bIgnoreCase
0x18001018c  or      edx, 0FFFFFFFFh; cchCount1
0x18001018f  mov     r9d, edx; cchCount2
0x180010192  lea     r8, aForeground; "foreground"
0x180010199  mov     rcx, rax; lpString1
0x18001019c  call    cs:__imp_CompareStringOrdinal
0x1800101a2  cmp     eax, 2
0x1800101a5  jz      short loc_1800101B7
0x1800101a7  xor     bl, bl
0x1800101a9  mov     [rsi], bl
0x1800101ab  xor     eax, eax
0x1800101ad  add     rsp, 48h
0x1800101b1  pop     r14
0x1800101b3  pop     rdi
0x1800101b4  pop     rsi
0x1800101b5  pop     rbx
0x1800101b6  retn
0x1800101b7  cmp     byte ptr [rdi+38h], 0
0x1800101bb  jnz     short loc_1800101A9
0x1800101bd  xor     edx, edx; length
0x1800101bf  mov     rcx, r14; string
0x1800101c2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800101c8  mov     rdx, rax; unsigned __int16 *
0x1800101cb  call    ?IsModernApp@CToastActivator_Foreground@Notifications@Internal@Windows@@AEAA_NPEBG@Z; Windows::Internal::Notifications::CToastActivator_Foreground::IsModernApp(ushort const *)
0x1800101d0  test    al, al
0x1800101d2  jnz     short loc_1800101A9
0x1800101d4  jmp     short loc_1800101A7
0x1800101d6  mov     eax, [rsp+68h+var_38]
0x1800101da  jmp     short loc_1800101AD
```
