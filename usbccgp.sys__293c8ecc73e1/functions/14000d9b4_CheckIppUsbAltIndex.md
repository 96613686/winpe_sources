# CheckIppUsbAltIndex

- ea: `0x14000d9b4`
- end: `0x14000db90`
- name: `CheckIppUsbAltIndex`
- size: `476`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140023938`
- `0x1400249d4`

## callees

- `0x14000d9b4`
- `0x14000db98`
- `0x140014d10`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000db5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000db5f`
- `ntoskrnl!ZwCreateKey` at `0x14000daf4`
- `ntoskrnl!ZwCreateKey` at `0x14000daf4`
- `ntoskrnl!ZwQueryValueKey` at `0x14000db26`
- `ntoskrnl!ZwQueryValueKey` at `0x14000db26`
- `ntoskrnl!ZwClose` at `0x14000db49`
- `ntoskrnl!ZwClose` at `0x14000db49`
- `ntoskrnl!ExAllocatePool2` at `0x14000da68`
- `ntoskrnl!ExAllocatePool2` at `0x14000da68`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000da88`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000da9c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000da88`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000da9c`

## string_xrefs

- `0x14000d9ee`: `\Registry\Machine\System\CurrentControlSet\Control\Print\Monitors\USB Monitor\IppUsbAltIndex\VID_%04X&PID_%04X`

## pseudocode

```c
_BOOL8 __fastcall CheckIppUsbAltIndex(unsigned __int16 a1, unsigned __int16 a2, unsigned __int8 a3)
{
  unsigned int v3; // esi
  BOOL v4; // edi
  _DWORD *Pool2; // rbx
  ULONG Length; // [rsp+40h] [rbp-C0h] BYREF
  ULONG Disposition; // [rsp+44h] [rbp-BCh] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+90h] [rbp-70h] BYREF
  wchar_t SourceString[16]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t pszDest[264]; // [rsp+C0h] [rbp-40h] BYREF

  v3 = a3;
  KeyHandle = 0;
  Length = 0;
  Disposition = 0;
  v4 = 0;
  DestinationString = 0;
  Pool2 = 0;
  ValueName = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( RtlStringCbPrintfW(
         pszDest,
         0x208u,
         L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Print\\Monitors\\USB Monitor\\IppUsbAltIndex\\VID_%04X&PID_%04X",
         a1,
         a2) >= 0
    && RtlStringCbPrintfW(SourceString, 0x20u, L"%d", v3) >= 0 )
  {
    Length = 20;
    Pool2 = (_DWORD *)ExAllocatePool2(256, 20, 1130525525);
    if ( Pool2 )
    {
      RtlInitUnicodeString(&DestinationString, pszDest);
      RtlInitUnicodeString(&ValueName, SourceString);
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( ZwCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, &Disposition) >= 0
        && ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, Pool2, Length, &Length) >= 0 )
      {
        v4 = Pool2[3] != 0;
      }
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0);
  return v4;
}

```

## disassembly

```asm
0x14000d9b4  mov     [rsp-8+arg_18], rbx
0x14000d9b9  push    rbp
0x14000d9ba  push    rsi
0x14000d9bb  push    rdi
0x14000d9bc  lea     rbp, [rsp-1E0h]
0x14000d9c4  sub     rsp, 2E0h
0x14000d9cb  mov     rax, cs:__security_cookie
0x14000d9d2  xor     rax, rsp
0x14000d9d5  mov     [rbp+1F0h+var_20], rax
0x14000d9dc  xor     eax, eax
0x14000d9de  movzx   esi, r8b
0x14000d9e2  xorps   xmm0, xmm0
0x14000d9e5  mov     [rsp+2F0h+KeyHandle], rax
0x14000d9ea  mov     [rsp+2F0h+Length], eax
0x14000d9ee  lea     r8, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x14000d9f5  mov     [rsp+2F0h+var_2AC], eax
0x14000d9f9  xorps   xmm1, xmm1
0x14000d9fc  movzx   eax, dx
0x14000d9ff  xor     edi, edi
0x14000da01  movzx   r9d, cx
0x14000da05  mov     edx, 208h; cbDest
0x14000da0a  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.ObjectName], xmm0
0x14000da0f  lea     rcx, [rbp+1F0h+pszDest]; pszDest
0x14000da13  mov     dword ptr [rsp+2F0h+Class], eax
0x14000da17  movups  xmmword ptr [rbp+1F0h+DestinationString.Length], xmm0
0x14000da1b  xor     ebx, ebx
0x14000da1d  movups  xmmword ptr [rbp+1F0h+ValueName.Length], xmm1
0x14000da21  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.Length], xmm0
0x14000da26  movups  xmmword ptr [rsp+2F0h+ObjectAttributes+1Ch], xmm0
0x14000da2b  call    RtlStringCbPrintfW
0x14000da30  test    eax, eax
0x14000da32  js      loc_14000DB3F
0x14000da38  mov     r9d, esi
0x14000da3b  lea     r8, aD; "%d"
0x14000da42  lea     edx, [rdi+20h]; cbDest
0x14000da45  lea     rcx, [rbp+1F0h+SourceString]; pszDest
0x14000da49  call    RtlStringCbPrintfW
0x14000da4e  test    eax, eax
0x14000da50  js      loc_14000DB3F
0x14000da56  lea     edx, [rdi+14h]
0x14000da59  mov     ecx, 100h
0x14000da5e  mov     r8d, 43627355h
0x14000da64  mov     [rsp+2F0h+Length], edx
0x14000da68  call    cs:__imp_ExAllocatePool2
0x14000da6f  nop     dword ptr [rax+rax+00h]
0x14000da74  mov     rbx, rax
0x14000da77  test    rax, rax
0x14000da7a  jz      loc_14000DB3F
0x14000da80  lea     rdx, [rbp+1F0h+pszDest]; SourceString
0x14000da84  lea     rcx, [rbp+1F0h+DestinationString]; DestinationString
0x14000da88  call    cs:__imp_RtlInitUnicodeString
0x14000da8f  nop     dword ptr [rax+rax+00h]
0x14000da94  lea     rdx, [rbp+1F0h+SourceString]; SourceString
0x14000da98  lea     rcx, [rbp+1F0h+ValueName]; DestinationString
0x14000da9c  call    cs:__imp_RtlInitUnicodeString
0x14000daa3  nop     dword ptr [rax+rax+00h]
0x14000daa8  lea     rax, [rbp+1F0h+DestinationString]
0x14000daac  mov     [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x14000dab4  mov     [rsp+2F0h+ObjectAttributes.ObjectName], rax
0x14000dab9  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x14000dabe  lea     rax, [rsp+2F0h+var_2AC]
0x14000dac3  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], rdi
0x14000dac8  mov     [rsp+2F0h+Disposition], rax; Disposition
0x14000dacd  lea     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x14000dad2  xorps   xmm0, xmm0
0x14000dad5  mov     [rsp+2F0h+CreateOptions], edi; CreateOptions
0x14000dad9  xor     r9d, r9d; TitleIndex
0x14000dadc  mov     [rsp+2F0h+Class], rdi; Class
0x14000dae1  mov     edx, 0F003Fh; DesiredAccess
0x14000dae6  mov     [rsp+2F0h+ObjectAttributes.Attributes], 240h
0x14000daee  movdqu  xmmword ptr [rsp+2F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000daf4  call    cs:__imp_ZwCreateKey
0x14000dafb  nop     dword ptr [rax+rax+00h]
0x14000db00  test    eax, eax
0x14000db02  js      short loc_14000DB3F
0x14000db04  mov     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x14000db09  lea     rax, [rsp+2F0h+Length]
0x14000db0e  mov     qword ptr [rsp+2F0h+CreateOptions], rax; ResultLength
0x14000db13  lea     r8d, [rdi+2]; KeyValueInformationClass
0x14000db17  mov     eax, [rsp+2F0h+Length]
0x14000db1b  lea     rdx, [rbp+1F0h+ValueName]; ValueName
0x14000db1f  mov     r9, rbx; KeyValueInformation
0x14000db22  mov     dword ptr [rsp+2F0h+Class], eax; Length
0x14000db26  call    cs:__imp_ZwQueryValueKey
0x14000db2d  nop     dword ptr [rax+rax+00h]
0x14000db32  test    eax, eax
0x14000db34  js      short loc_14000DB3F
0x14000db36  cmp     [rbx+0Ch], edi
0x14000db39  lea     eax, [rdi+1]
0x14000db3c  cmovnz  edi, eax
0x14000db3f  mov     rcx, [rsp+2F0h+KeyHandle]; Handle
0x14000db44  test    rcx, rcx
0x14000db47  jz      short loc_14000DB55
0x14000db49  call    cs:__imp_ZwClose
0x14000db50  nop     dword ptr [rax+rax+00h]
0x14000db55  test    rbx, rbx
0x14000db58  jz      short loc_14000DB6B
0x14000db5a  xor     edx, edx; Tag
0x14000db5c  mov     rcx, rbx; P
0x14000db5f  call    cs:__imp_ExFreePoolWithTag
0x14000db66  nop     dword ptr [rax+rax+00h]
0x14000db6b  mov     eax, edi
0x14000db6d  mov     rcx, [rbp+1F0h+var_20]
0x14000db74  xor     rcx, rsp; StackCookie
0x14000db77  call    __security_check_cookie
0x14000db7c  mov     rbx, [rsp+2F0h+arg_18]
0x14000db84  add     rsp, 2E0h
0x14000db8b  pop     rdi
0x14000db8c  pop     rsi
0x14000db8d  pop     rbp
0x14000db8e  retn
```
