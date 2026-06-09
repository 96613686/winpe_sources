# Windows::Internal::Notifications::CToastActivator_AppLaunch::CanActivate(HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IPropertySet *,uchar *)

- ea: `0x1800138f0`
- end: `0x180013965`
- name: `?CanActivate@CToastActivator_AppLaunch@Notifications@Internal@Windows@@UEAAJPEAUHSTRING__@@0PEAUIPropertySet@Collections@Foundation@4@PEAE@Z`
- size: `117`
- prototype: `int(Windows::Internal::Notifications::CToastActivator_AppLaunch *__hidden this, HSTRING, HSTRING, struct Windows::Foundation::Collections::IPropertySet *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800138f0`
- `0x180016e44`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013928`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013928`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013907`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013949`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013907`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013949`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Notifications::CToastActivator_AppLaunch::CanActivate(
        Windows::Internal::Notifications::CToastActivator_AppLaunch *this,
        HSTRING a2,
        HSTRING a3,
        struct Windows::Foundation::Collections::IPropertySet *a4,
        unsigned __int8 *a5)
{
  const WCHAR *StringRawBuffer; // rax
  unsigned __int8 v7; // al
  const unsigned __int16 *v9; // rax
  Windows::Internal::Notifications::CToastActivator_AppLaunch *v10; // rcx
  char IsAppCapable; // al
  const char *v12; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
  if ( CompareStringOrdinal(StringRawBuffer, -1, L"applaunch", -1, 1) != 2 )
    goto LABEL_2;
  v9 = WindowsGetStringRawBuffer(a2, 0);
  try
  {
    IsAppCapable = Windows::Internal::Notifications::CToastActivator_AppLaunch::IsAppCapable(v10, v9);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x7A,
                           (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactiva"
                                         "tor_applaunch.cpp",
                           v12);
  }
  if ( IsAppCapable )
    v7 = 1;
  else
LABEL_2:
    v7 = 0;
  *a5 = v7;
  return 0;
}

```

## disassembly

```asm
0x1800138f0  mov     [rsp+arg_0], rbx
0x1800138f5  push    rdi
0x1800138f6  sub     rsp, 40h
0x1800138fa  mov     rdi, rdx
0x1800138fd  mov     rbx, [rsp+48h+arg_20]
0x180013902  xor     edx, edx; length
0x180013904  mov     rcx, r8; string
0x180013907  call    cs:__imp_WindowsGetStringRawBuffer
0x18001390d  mov     [rsp+48h+bIgnoreCase], 1; bIgnoreCase
0x180013915  mov     r9d, 0FFFFFFFFh; cchCount2
0x18001391b  lea     r8, aApplaunch; "applaunch"
0x180013922  mov     edx, r9d; cchCount1
0x180013925  mov     rcx, rax; lpString1
0x180013928  call    cs:__imp_CompareStringOrdinal
0x18001392e  cmp     eax, 2
0x180013931  jz      short loc_180013944
0x180013933  xor     al, al
0x180013935  mov     [rbx], al
0x180013937  xor     eax, eax
0x180013939  mov     rbx, [rsp+48h+arg_0]
0x18001393e  add     rsp, 40h
0x180013942  pop     rdi
0x180013943  retn
0x180013944  xor     edx, edx; length
0x180013946  mov     rcx, rdi; string
0x180013949  call    cs:__imp_WindowsGetStringRawBuffer
0x18001394f  mov     rdx, rax; unsigned __int16 *
0x180013952  call    ?IsAppCapable@CToastActivator_AppLaunch@Notifications@Internal@Windows@@AEAA_NPEBG@Z; Windows::Internal::Notifications::CToastActivator_AppLaunch::IsAppCapable(ushort const *)
0x180013957  test    al, al
0x180013959  jz      short loc_180013933
0x18001395b  mov     al, 1
0x18001395d  jmp     short loc_180013935
0x18001395f  mov     eax, [rsp+48h+var_18]
0x180013963  jmp     short loc_180013939
```
