# Windows::Internal::Notifications::CToastActivator_Protocol::CanActivate(HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IPropertySet *,uchar *)

- ea: `0x180015580`
- end: `0x1800155ca`
- name: `?CanActivate@CToastActivator_Protocol@Notifications@Internal@Windows@@UEAAJPEAUHSTRING__@@0PEAUIPropertySet@Collections@Foundation@4@PEAE@Z`
- size: `74`
- prototype: `int(Windows::Internal::Notifications::CToastActivator_Protocol *__hidden this, HSTRING, HSTRING, struct Windows::Foundation::Collections::IPropertySet *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180015580`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800155ae`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800155ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015590`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015590`

## string_xrefs

- `0x1800155a4`: `protocol`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Notifications::CToastActivator_Protocol::CanActivate(
        Windows::Internal::Notifications::CToastActivator_Protocol *this,
        HSTRING a2,
        HSTRING a3,
        struct Windows::Foundation::Collections::IPropertySet *a4,
        bool *a5)
{
  const WCHAR *StringRawBuffer; // rax

  StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
  *a5 = CompareStringOrdinal(StringRawBuffer, -1, L"protocol", -1, 1) == 2;
  return 0;
}

```

## disassembly

```asm
0x180015580  push    rbx
0x180015582  sub     rsp, 40h
0x180015586  mov     rbx, [rsp+48h+arg_20]
0x18001558b  xor     edx, edx; length
0x18001558d  mov     rcx, r8; string
0x180015590  call    cs:__imp_WindowsGetStringRawBuffer
0x180015596  mov     [rsp+48h+bIgnoreCase], 1; bIgnoreCase
0x18001559e  or      edx, 0FFFFFFFFh; cchCount1
0x1800155a1  mov     r9d, edx; cchCount2
0x1800155a4  lea     r8, aProtocol; "protocol"
0x1800155ab  mov     rcx, rax; lpString1
0x1800155ae  call    cs:__imp_CompareStringOrdinal
0x1800155b4  cmp     eax, 2
0x1800155b7  setz    al
0x1800155ba  mov     [rbx], al
0x1800155bc  xor     eax, eax
0x1800155be  add     rsp, 40h
0x1800155c2  pop     rbx
0x1800155c3  retn
0x1800155c4  mov     eax, [rsp+48h+var_18]
0x1800155c8  jmp     short loc_1800155BE
```
