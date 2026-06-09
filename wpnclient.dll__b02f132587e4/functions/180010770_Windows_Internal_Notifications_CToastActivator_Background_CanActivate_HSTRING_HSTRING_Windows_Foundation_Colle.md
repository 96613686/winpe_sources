# Windows::Internal::Notifications::CToastActivator_Background::CanActivate(HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IPropertySet *,uchar *)

- ea: `0x180010770`
- end: `0x1800107eb`
- name: `?CanActivate@CToastActivator_Background@Notifications@Internal@Windows@@UEAAJPEAUHSTRING__@@0PEAUIPropertySet@Collections@Foundation@4@PEAE@Z`
- size: `123`
- prototype: `int(Windows::Internal::Notifications::CToastActivator_Background *__hidden this, HSTRING, HSTRING, struct Windows::Foundation::Collections::IPropertySet *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180010770`
- `0x180010800`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800107b0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800107b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001078f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001078f`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Notifications::CToastActivator_Background::CanActivate(
        Windows::Internal::Notifications::CToastActivator_Background *this,
        HSTRING a2,
        HSTRING a3,
        struct Windows::Foundation::Collections::IPropertySet *a4,
        unsigned __int8 *a5)
{
  const WCHAR *StringRawBuffer; // rax
  const unsigned __int16 *v7; // rdx
  unsigned __int8 v8; // di
  const char *v10; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a5 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
  if ( CompareStringOrdinal(StringRawBuffer, -1, L"background", -1, 1) == 2 )
  {
    v8 = 1;
    if ( a4 )
    {
      try
      {
        Windows::Internal::Notifications::Utilities::InsertBoolIntoPropertySet(a4, v7);
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x8C,
                               (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastac"
                                             "tivator_background.cpp",
                               v10);
      }
    }
  }
  else
  {
    v8 = 0;
  }
  *a5 = v8;
  return 0;
}

```

## disassembly

```asm
0x180010770  mov     [rsp+arg_0], rbx
0x180010775  mov     [rsp+arg_8], rsi
0x18001077a  push    rdi
0x18001077b  sub     rsp, 40h
0x18001077f  mov     rsi, r9
0x180010782  mov     rbx, [rsp+48h+arg_20]
0x180010787  mov     byte ptr [rbx], 0
0x18001078a  xor     edx, edx; length
0x18001078c  mov     rcx, r8; string
0x18001078f  call    cs:__imp_WindowsGetStringRawBuffer
0x180010795  mov     [rsp+48h+bIgnoreCase], 1; bIgnoreCase
0x18001079d  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800107a3  lea     r8, aBackground; "background"
0x1800107aa  mov     edx, r9d; cchCount1
0x1800107ad  mov     rcx, rax; lpString1
0x1800107b0  call    cs:__imp_CompareStringOrdinal
0x1800107b6  cmp     eax, 2
0x1800107b9  jz      short loc_1800107D3
0x1800107bb  xor     dil, dil
0x1800107be  mov     [rbx], dil
0x1800107c1  xor     eax, eax
0x1800107c3  mov     rbx, [rsp+48h+arg_0]
0x1800107c8  mov     rsi, [rsp+48h+arg_8]
0x1800107cd  add     rsp, 40h
0x1800107d1  pop     rdi
0x1800107d2  retn
0x1800107d3  mov     dil, 1
0x1800107d6  test    rsi, rsi
0x1800107d9  jz      short loc_1800107BE
0x1800107db  mov     rcx, rsi; struct Windows::Foundation::Collections::IPropertySet *
0x1800107de  call    ?InsertBoolIntoPropertySet@Utilities@Notifications@Internal@Windows@@SAXPEAUIPropertySet@Collections@Foundation@4@PEBG_N@Z; Windows::Internal::Notifications::Utilities::InsertBoolIntoPropertySet(Windows::Foundation::Collections::IPropertySet *,ushort const *,bool)
0x1800107e3  jmp     short loc_1800107BE
0x1800107e5  mov     eax, [rsp+48h+var_18]
0x1800107e9  jmp     short loc_1800107C3
```
