# GetServerIMEKeyboardLayout(ushort *)

- ea: `0x180064ba4`
- end: `0x180064e3a`
- name: `?GetServerIMEKeyboardLayout@@YAKPEAG@Z`
- size: `662`
- prototype: `unsigned int __fastcall(LPCWSTR lpString2)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800565e0`

## callees

- `0x180064ba4`
- `0x180093910`
- `0x1800939b0`
- `0x180096dc5`
- `0x180096e00`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x180064dbf`
- `ntdll!NtQueryValueKey` at `0x180064dbf`
- `ntdll!NtEnumerateKey` at `0x180064c8a`
- `ntdll!NtEnumerateKey` at `0x180064c8a`
- `ntdll!NtClose` at `0x180064dcc`
- `ntdll!NtClose` at `0x180064e01`
- `ntdll!NtClose` at `0x180064dcc`
- `ntdll!NtClose` at `0x180064e01`
- `ntdll!NtOpenKey` at `0x180064c51`
- `ntdll!NtOpenKey` at `0x180064d6a`
- `ntdll!NtOpenKey` at `0x180064c51`
- `ntdll!NtOpenKey` at `0x180064d6a`
- `ntdll!RtlUnicodeStringToInteger` at `0x180064cc4`
- `ntdll!RtlUnicodeStringToInteger` at `0x180064cc4`
- `ntdll!RtlInitUnicodeString` at `0x180064c13`
- `ntdll!RtlInitUnicodeString` at `0x180064d30`
- `ntdll!RtlInitUnicodeString` at `0x180064d94`
- `ntdll!RtlInitUnicodeString` at `0x180064c13`
- `ntdll!RtlInitUnicodeString` at `0x180064d30`
- `ntdll!RtlInitUnicodeString` at `0x180064d94`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180064de6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180064de6`

## string_xrefs

- `0x180064bec`: `\Registry\Machine\System\CurrentControlSet\Control\Keyboard Layouts\`
- `0x180064ce7`: `\Registry\Machine\System\CurrentControlSet\Control\Keyboard Layouts\`

## pseudocode

```c
__int64 __fastcall GetServerIMEKeyboardLayout(LPCWSTR lpString2)
{
  int v2; // esi
  ULONG i; // edi
  size_t *v4; // r8
  unsigned __int64 v5; // rdx
  NTSTATUS v6; // ebx
  ULONG Value; // [rsp+30h] [rbp-D0h] BYREF
  ULONG ResultLength; // [rsp+34h] [rbp-CCh] BYREF
  ULONG v10; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-C0h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  UNICODE_STRING String; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE KeyValueInformation[12]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR String1[258]; // [rsp+BCh] [rbp-44h] BYREF
  _BYTE KeyInformation[12]; // [rsp+2C0h] [rbp+1C0h] BYREF
  USHORT v20; // [rsp+2CCh] [rbp+1CCh]
  char v21; // [rsp+2D0h] [rbp+1D0h] BYREF
  wchar_t pszDest[160]; // [rsp+2F0h] [rbp+1F0h] BYREF

  Value = 0;
  KeyHandle = 0;
  DestinationString = 0;
  String = 0;
  ValueName = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Keyboard Layouts\\");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) < 0 )
    return 0;
  v2 = 0;
  for ( i = 0; ; ++i )
  {
    ResultLength = 0;
    if ( NtEnumerateKey(KeyHandle, i, KeyBasicInformation, KeyInformation, 0x2Au, &ResultLength) < 0 )
      break;
    String.Buffer = (PWSTR)&v21;
    String.Length = v20;
    String.MaximumLength = v20;
    RtlUnicodeStringToInteger(&String, 0x10u, &Value);
    if ( (HIWORD(Value) & 0xF000) == 0xE000 )
    {
      Handle = 0;
      StringCopyWorkerW(
        pszDest,
        0x9Au,
        v4,
        L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Keyboard Layouts\\",
        0x7FFFFFFEu);
      StringCbCatNW(pszDest, v5, String.Buffer, String.Length);
      RtlInitUnicodeString(&DestinationString, pszDest);
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( NtOpenKey(&Handle, 0x20019u, &ObjectAttributes) >= 0 )
      {
        memset_0(KeyValueInformation, 0, 0x210u);
        v10 = 0;
        RtlInitUnicodeString(&ValueName, L"IME file");
        v6 = NtQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x210u, &v10);
        NtClose(Handle);
        if ( v6 >= 0 )
        {
          String1[255] = 0;
          if ( !lstrcmpiW(String1, lpString2) )
          {
            v2 = 1;
            break;
          }
        }
      }
    }
  }
  NtClose(KeyHandle);
  if ( v2 )
    return Value;
  else
    return 0;
}

```

## disassembly

```asm
0x180064ba4  mov     [rsp-8+arg_8], rbx
0x180064ba9  mov     [rsp-8+arg_10], rsi
0x180064bae  push    rbp
0x180064baf  push    rdi
0x180064bb0  push    r14
0x180064bb2  lea     rbp, [rsp-340h]
0x180064bba  sub     rsp, 440h
0x180064bc1  mov     rax, cs:__security_cookie
0x180064bc8  xor     rax, rsp
0x180064bcb  mov     [rbp+350h+var_20], rax
0x180064bd2  xorps   xmm1, xmm1
0x180064bd5  mov     [rsp+450h+Value], 0
0x180064bdd  xorps   xmm0, xmm0
0x180064be0  mov     [rsp+450h+KeyHandle], 0
0x180064be9  mov     r14, rcx
0x180064bec  lea     rdx, aRegistryMachin_4; "\\Registry\\Machine\\System\\CurrentCon"...
0x180064bf3  lea     rcx, [rsp+450h+DestinationString]; DestinationString
0x180064bf8  movups  xmmword ptr [rsp+450h+DestinationString.Length], xmm0
0x180064bfd  movups  xmmword ptr [rsp+450h+String.Length], xmm1
0x180064c02  movups  xmmword ptr [rbp+350h+ValueName.Length], xmm0
0x180064c06  movups  xmmword ptr [rsp+450h+ObjectAttributes.Length], xmm1
0x180064c0b  movups  xmmword ptr [rbp+350h+ObjectAttributes.ObjectName], xmm1
0x180064c0f  movups  xmmword ptr [rbp+350h+ObjectAttributes.SecurityDescriptor], xmm1
0x180064c13  call    cs:__imp_RtlInitUnicodeString
0x180064c19  lea     rax, [rsp+450h+DestinationString]
0x180064c1e  mov     [rsp+450h+ObjectAttributes.Length], 30h ; '0'
0x180064c26  xorps   xmm0, xmm0
0x180064c29  mov     [rbp+350h+ObjectAttributes.ObjectName], rax
0x180064c2d  lea     r8, [rsp+450h+ObjectAttributes]; ObjectAttributes
0x180064c32  mov     [rsp+450h+ObjectAttributes.RootDirectory], 0
0x180064c3b  mov     edx, 20019h; DesiredAccess
0x180064c40  mov     [rbp+350h+ObjectAttributes.Attributes], 40h ; '@'
0x180064c47  lea     rcx, [rsp+450h+KeyHandle]; KeyHandle
0x180064c4c  movdqu  xmmword ptr [rbp+350h+ObjectAttributes.SecurityDescriptor], xmm0
0x180064c51  call    cs:__imp_NtOpenKey
0x180064c57  test    eax, eax
0x180064c59  js      loc_180064E11
0x180064c5f  xor     esi, esi
0x180064c61  xor     edi, edi
0x180064c63  mov     rcx, [rsp+450h+KeyHandle]; KeyHandle
0x180064c68  lea     rax, [rsp+450h+var_41C]
0x180064c6d  mov     [rsp+450h+ResultLength], rax; ResultLength
0x180064c72  lea     r9, [rbp+350h+KeyInformation]; KeyInformation
0x180064c79  xor     r8d, r8d; KeyInformationClass
0x180064c7c  mov     [rsp+450h+Length], 2Ah ; '*'; Length
0x180064c84  mov     edx, edi; Index
0x180064c86  mov     [rsp+450h+var_41C], esi
0x180064c8a  call    cs:__imp_NtEnumerateKey
0x180064c90  test    eax, eax
0x180064c92  js      loc_180064DFC
0x180064c98  lea     rax, [rbp+350h+var_180]
0x180064c9f  mov     edx, 10h; Base
0x180064ca4  mov     [rsp+450h+String.Buffer], rax
0x180064ca9  lea     r8, [rsp+450h+Value]; Value
0x180064cae  movzx   eax, [rbp+350h+var_184]
0x180064cb5  lea     rcx, [rsp+450h+String]; String
0x180064cba  mov     [rsp+450h+String.Length], ax
0x180064cbf  mov     [rsp+450h+String.MaximumLength], ax
0x180064cc4  call    cs:__imp_RtlUnicodeStringToInteger
0x180064cca  mov     eax, [rsp+450h+Value]
0x180064cce  mov     ecx, 0F000h
0x180064cd3  shr     eax, 10h
0x180064cd6  and     ax, cx
0x180064cd9  mov     ecx, 0E000h
0x180064cde  cmp     ax, cx
0x180064ce1  jnz     loc_180064DF0
0x180064ce7  lea     r9, aRegistryMachin_4; "\\Registry\\Machine\\System\\CurrentCon"...
0x180064cee  mov     [rsp+450h+Handle], rsi
0x180064cf3  mov     edx, 9Ah; cchDest
0x180064cf8  mov     qword ptr [rsp+450h+Length], 7FFFFFFEh; cchToCopy
0x180064d01  lea     rcx, [rbp+350h+pszDest]; pszDest
0x180064d08  call    StringCopyWorkerW
0x180064d0d  movzx   r9d, [rsp+450h+String.Length]; unsigned __int64
0x180064d13  lea     rcx, [rbp+350h+pszDest]; unsigned __int16 *
0x180064d1a  mov     r8, [rsp+450h+String.Buffer]; unsigned __int16 *
0x180064d1f  call    ?StringCbCatNW@@YAJPEAG_KPEBG1@Z; StringCbCatNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180064d24  lea     rdx, [rbp+350h+pszDest]; SourceString
0x180064d2b  lea     rcx, [rsp+450h+DestinationString]; DestinationString
0x180064d30  call    cs:__imp_RtlInitUnicodeString
0x180064d36  lea     rax, [rsp+450h+DestinationString]
0x180064d3b  mov     [rsp+450h+ObjectAttributes.Length], 30h ; '0'
0x180064d43  xorps   xmm0, xmm0
0x180064d46  mov     [rbp+350h+ObjectAttributes.ObjectName], rax
0x180064d4a  lea     r8, [rsp+450h+ObjectAttributes]; ObjectAttributes
0x180064d4f  mov     [rsp+450h+ObjectAttributes.RootDirectory], rsi
0x180064d54  mov     edx, 20019h; DesiredAccess
0x180064d59  mov     [rbp+350h+ObjectAttributes.Attributes], 40h ; '@'
0x180064d60  lea     rcx, [rsp+450h+Handle]; KeyHandle
0x180064d65  movdqu  xmmword ptr [rbp+350h+ObjectAttributes.SecurityDescriptor], xmm0
0x180064d6a  call    cs:__imp_NtOpenKey
0x180064d70  test    eax, eax
0x180064d72  js      short loc_180064DF0
0x180064d74  xor     edx, edx; Val
0x180064d76  lea     rcx, [rbp+350h+KeyValueInformation]; void *
0x180064d7a  mov     r8d, 210h; Size
0x180064d80  call    memset_0
0x180064d85  lea     rdx, aImeFile; "IME file"
0x180064d8c  mov     [rsp+450h+var_418], esi
0x180064d90  lea     rcx, [rbp+350h+ValueName]; DestinationString
0x180064d94  call    cs:__imp_RtlInitUnicodeString
0x180064d9a  mov     rcx, [rsp+450h+Handle]; KeyHandle
0x180064d9f  lea     rax, [rsp+450h+var_418]
0x180064da4  mov     [rsp+450h+ResultLength], rax; ResultLength
0x180064da9  lea     r9, [rbp+350h+KeyValueInformation]; KeyValueInformation
0x180064dad  mov     r8d, 2; KeyValueInformationClass
0x180064db3  mov     [rsp+450h+Length], 210h; Length
0x180064dbb  lea     rdx, [rbp+350h+ValueName]; ValueName
0x180064dbf  call    cs:__imp_NtQueryValueKey
0x180064dc5  mov     rcx, [rsp+450h+Handle]; Handle
0x180064dca  mov     ebx, eax
0x180064dcc  call    cs:__imp_NtClose
0x180064dd2  test    ebx, ebx
0x180064dd4  js      short loc_180064DF0
0x180064dd6  xor     eax, eax
0x180064dd8  lea     rcx, [rbp+350h+String1]; lpString1
0x180064ddc  mov     rdx, r14; lpString2
0x180064ddf  mov     [rbp+350h+var_196], ax
0x180064de6  call    cs:__imp_lstrcmpiW
0x180064dec  test    eax, eax
0x180064dee  jz      short loc_180064DF7
0x180064df0  inc     edi
0x180064df2  jmp     loc_180064C63
0x180064df7  mov     esi, 1
0x180064dfc  mov     rcx, [rsp+450h+KeyHandle]; Handle
0x180064e01  call    cs:__imp_NtClose
0x180064e07  test    esi, esi
0x180064e09  jz      short loc_180064E11
0x180064e0b  mov     eax, [rsp+450h+Value]
0x180064e0f  jmp     short loc_180064E13
0x180064e11  xor     eax, eax
0x180064e13  mov     rcx, [rbp+350h+var_20]
0x180064e1a  xor     rcx, rsp; StackCookie
0x180064e1d  call    __security_check_cookie
0x180064e22  lea     r11, [rsp+450h+var_10]
0x180064e2a  mov     rbx, [r11+28h]
0x180064e2e  mov     rsi, [r11+30h]
0x180064e32  mov     rsp, r11
0x180064e35  pop     r14
0x180064e37  pop     rdi
0x180064e38  pop     rbp
0x180064e39  retn
```
