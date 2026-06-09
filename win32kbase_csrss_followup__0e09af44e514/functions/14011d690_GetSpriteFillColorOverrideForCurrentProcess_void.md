# GetSpriteFillColorOverrideForCurrentProcess(void)

- ea: `0x14011d690`
- end: `0x14011d9bf`
- name: `?GetSpriteFillColorOverrideForCurrentProcess@@YAKXZ`
- size: `815`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14014c4ec`

## callees

- `0x14011d690`
- `0x14011d9c8`
- `0x1401a9f9c`
- `0x140238160`
- `0x1402bb164`
- `0x1402bb1a0`

## import_xrefs

- `ntoskrnl!PsGetProcessPeb` at `0x14011d718`
- `ntoskrnl!PsGetProcessPeb` at `0x14011d718`
- `ntoskrnl!PsGetCurrentProcess` at `0x14011d709`
- `ntoskrnl!PsGetCurrentProcess` at `0x14011d709`
- `ntoskrnl!ProbeForRead` at `0x14011d742`
- `ntoskrnl!ProbeForRead` at `0x14011d76e`
- `ntoskrnl!ProbeForRead` at `0x14011d7af`
- `ntoskrnl!ProbeForRead` at `0x14011d742`
- `ntoskrnl!ProbeForRead` at `0x14011d76e`
- `ntoskrnl!ProbeForRead` at `0x14011d7af`
- `ntoskrnl!ExRaiseAccessViolation` at `0x14011d831`
- `ntoskrnl!ExRaiseAccessViolation` at `0x14011d831`
- `ntoskrnl!ZwOpenKey` at `0x14011d917`
- `ntoskrnl!ZwOpenKey` at `0x14011d917`
- `ntoskrnl!ZwQueryValueKey` at `0x14011d96e`
- `ntoskrnl!ZwQueryValueKey` at `0x14011d96e`
- `ntoskrnl!ZwClose` at `0x14011d9a1`
- `ntoskrnl!ZwClose` at `0x14011d9a1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14011d8cb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14011d93b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14011d8cb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14011d93b`

## string_xrefs

- `0x14011d6b8`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\Image File Execution Options\`

## pseudocode

```c
__int64 GetSpriteFillColorOverrideForCurrentProcess(void)
{
  __int64 v0; // rax
  const wchar_t *v1; // r8
  __int64 v2; // rdx
  WCHAR *v3; // rcx
  wchar_t v4; // r9
  WCHAR *v5; // rax
  __int64 CurrentProcess; // rax
  char *v7; // rbx
  int ULongFromUser; // r15d
  WCHAR *ULong64FromUser; // r12
  int v10; // eax
  const unsigned __int16 *v11; // r8
  const unsigned __int16 *v12; // rcx
  int v13; // eax
  unsigned int v14; // ebx
  char v15; // r15
  ULONG ResultLength; // [rsp+30h] [rbp-2E8h] BYREF
  volatile void *Address; // [rsp+38h] [rbp-2E0h] BYREF
  int v19; // [rsp+40h] [rbp-2D8h]
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-2D0h] BYREF
  const unsigned __int16 *v21; // [rsp+58h] [rbp-2C0h]
  __int64 v22; // [rsp+60h] [rbp-2B8h]
  __int64 v23; // [rsp+68h] [rbp-2B0h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-2A8h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+A8h] [rbp-270h] BYREF
  int v26; // [rsp+ACh] [rbp-26Ch]
  int v27; // [rsp+B0h] [rbp-268h]
  unsigned int v28; // [rsp+B4h] [rbp-264h]
  WCHAR SourceString[264]; // [rsp+C0h] [rbp-258h] BYREF

  v0 = 2147483646;
  v1 = L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\Image File Execution Options\\";
  v2 = 260;
  v3 = SourceString;
  do
  {
    if ( !v0 )
      break;
    v4 = *v1;
    if ( !*v1 )
      break;
    ++v1;
    *v3++ = v4;
    --v0;
    --v2;
  }
  while ( v2 );
  v5 = v3 - 1;
  if ( v2 )
    v5 = v3;
  *v5 = 0;
  v21 = 0;
  CurrentProcess = PsGetCurrentProcess(v3, v2, v1);
  Address = (volatile void *)PsGetProcessPeb(CurrentProcess);
  v22 = 1;
  ProbeForRead(Address, 1u, 1u);
  v7 = (char *)*((_QWORD *)Address + 4);
  v23 = 1;
  ProbeForRead(v7, 1u, 1u);
  ULongFromUser = RtlReadULongFromUser(v7 + 96);
  *(_DWORD *)&DestinationString.Length = ULongFromUser;
  ULong64FromUser = (WCHAR *)RtlReadULong64FromUser(v7 + 104);
  DestinationString.Buffer = ULong64FromUser;
  ProbeForRead(ULong64FromUser, (unsigned __int16)ULongFromUser + 2LL, 2u);
  if ( (unsigned __int16)ULongFromUser > HIWORD(ULongFromUser) )
  {
    if ( (ULongFromUser & 1) == 0 )
      goto LABEL_16;
    goto LABEL_15;
  }
  if ( (ULongFromUser & 1) != 0 )
  {
LABEL_15:
    ResultLength = 0x20000;
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 382);
LABEL_16:
    ExRaiseAccessViolation();
  }
  v10 = (unsigned __int16)ULongFromUser;
  v11 = (WCHAR *)((char *)ULong64FromUser + (unsigned __int16)ULongFromUser);
  v21 = v11;
  while ( v10 )
  {
    v12 = v11 - 1;
    if ( *(v11 - 1) == 92 )
      break;
    --v11;
    v21 = v12;
    v10 -= 2;
  }
  v13 = RtlStringCchCatW(SourceString, 0x104u, v11);
  v19 = v13;
  v14 = 0;
  v15 = 0;
  if ( v13 >= 0 )
  {
    DestinationString = 0;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    Address = 0;
    RtlInitUnicodeString(&DestinationString, SourceString);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwOpenKey((PHANDLE)&Address, 0x20019u, &ObjectAttributes) >= 0 )
    {
      ResultLength = 0;
      RtlInitUnicodeString(&DestinationString, L"SpriteFillColor");
      if ( ZwQueryValueKey(
             (HANDLE)Address,
             &DestinationString,
             KeyValuePartialInformation,
             KeyValueInformation,
             0x14u,
             &ResultLength) >= 0
        && v26 == 4
        && v27 == 4 )
      {
        v14 = v28;
        v15 = 1;
      }
      ZwClose((HANDLE)Address);
    }
  }
  if ( v15 && v14 )
  {
    if ( (v14 & 0xFF000000) != 0 )
      return 0;
  }
  else
  {
    return (unsigned int)-1;
  }
  return v14;
}

```

## disassembly

```asm
0x14011d690  push    rbx
0x14011d692  push    rsi
0x14011d693  push    rdi
0x14011d694  push    r12
0x14011d696  push    r14
0x14011d698  push    r15
0x14011d69a  sub     rsp, 2E8h
0x14011d6a1  mov     rax, cs:__security_cookie
0x14011d6a8  xor     rax, rsp
0x14011d6ab  mov     [rsp+318h+var_48], rax
0x14011d6b3  mov     eax, 7FFFFFFEh
0x14011d6b8  lea     r8, aRegistryMachin_27; "\\Registry\\Machine\\Software\\Microsof"...
0x14011d6bf  mov     edx, 104h
0x14011d6c4  lea     rcx, [rsp+318h+SourceString]
0x14011d6cc  xor     edi, edi
0x14011d6ce  lea     esi, [rdi+2]
0x14011d6d1  lea     r14d, [rdi+1]
0x14011d6d5  test    rax, rax
0x14011d6d8  jz      short loc_14011D6F6
0x14011d6da  movzx   r9d, word ptr [r8]
0x14011d6de  test    r9w, r9w
0x14011d6e2  jz      short loc_14011D6F6
0x14011d6e4  add     r8, rsi
0x14011d6e7  mov     [rcx], r9w
0x14011d6eb  add     rcx, rsi
0x14011d6ee  sub     rax, r14
0x14011d6f1  sub     rdx, r14
0x14011d6f4  jnz     short loc_14011D6D5
0x14011d6f6  lea     rax, [rcx-2]
0x14011d6fa  test    rdx, rdx
0x14011d6fd  cmovnz  rax, rcx
0x14011d701  mov     [rax], di
0x14011d704  mov     [rsp+318h+var_2C0], rdi
0x14011d709  call    cs:__imp_PsGetCurrentProcess
0x14011d710  nop     dword ptr [rax+rax+00h]
0x14011d715  mov     rcx, rax
0x14011d718  call    cs:__imp_PsGetProcessPeb
0x14011d71f  nop     dword ptr [rax+rax+00h]
0x14011d724  mov     [rsp+318h+Address], rax
0x14011d729  mov     [rsp+318h+var_2B8], 7D0h
0x14011d732  mov     rcx, [rsp+318h+Address]; Address
0x14011d737  mov     [rsp+318h+var_2B8], r14
0x14011d73c  mov     r8d, r14d; Alignment
0x14011d73f  mov     rdx, r14; Length
0x14011d742  call    cs:__imp_ProbeForRead
0x14011d749  nop     dword ptr [rax+rax+00h]
0x14011d74e  mov     rax, [rsp+318h+Address]
0x14011d753  mov     rbx, [rax+20h]
0x14011d757  mov     [rsp+318h+var_2B0], 450h
0x14011d760  mov     [rsp+318h+var_2B0], r14
0x14011d765  mov     r8d, r14d; Alignment
0x14011d768  mov     rdx, r14; Length
0x14011d76b  mov     rcx, rbx; Address
0x14011d76e  call    cs:__imp_ProbeForRead
0x14011d775  nop     dword ptr [rax+rax+00h]
0x14011d77a  lea     rcx, [rbx+60h]
0x14011d77e  call    RtlReadULongFromUser
0x14011d783  mov     r15d, eax
0x14011d786  mov     dword ptr [rsp+318h+DestinationString.Length], r15d
0x14011d78b  lea     rcx, [rbx+68h]
0x14011d78f  call    RtlReadULong64FromUser
0x14011d794  mov     r12, rax
0x14011d797  mov     [rsp+318h+DestinationString.Buffer], rax
0x14011d79c  mov     ebx, r15d
0x14011d79f  shr     ebx, 10h
0x14011d7a2  movzx   edx, r15w
0x14011d7a6  add     rdx, rsi; Length
0x14011d7a9  mov     r8d, esi; Alignment
0x14011d7ac  mov     rcx, rax; Address
0x14011d7af  call    cs:__imp_ProbeForRead
0x14011d7b6  nop     dword ptr [rax+rax+00h]
0x14011d7bb  movzx   ecx, r15w
0x14011d7bf  and     cx, r14w
0x14011d7c3  cmp     r15w, bx
0x14011d7c7  ja      short loc_14011D80E
0x14011d7c9  test    cx, cx
0x14011d7cc  jnz     short loc_14011D813
0x14011d7ce  movzx   eax, r15w
0x14011d7d2  lea     r8, [r12+rax]; unsigned __int16 *
0x14011d7d6  mov     [rsp+318h+var_2C0], r8
0x14011d7db  test    eax, eax
0x14011d7dd  jz      short loc_14011D7E9
0x14011d7df  lea     rcx, [r8-2]
0x14011d7e3  cmp     word ptr [rcx], 5Ch ; '\'
0x14011d7e7  jnz     short loc_14011D801
0x14011d7e9  mov     edx, 104h; unsigned __int64
0x14011d7ee  lea     rcx, [rsp+318h+SourceString]; unsigned __int16 *
0x14011d7f6  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14011d7fb  mov     [rsp+318h+var_2D8], eax
0x14011d7ff  jmp     short loc_14011D850
0x14011d801  mov     r8, rcx
0x14011d804  mov     [rsp+318h+var_2C0], rcx
0x14011d809  add     eax, 0FFFFFFFEh
0x14011d80c  jmp     short loc_14011D7DB
0x14011d80e  test    cx, cx
0x14011d811  jz      short loc_14011D831
0x14011d813  mov     [rsp+318h+var_2E8], 20000h
0x14011d81b  mov     r8d, 17Eh
0x14011d821  mov     edx, [rsp+318h+var_2E8]
0x14011d825  lea     rcx, aIxptelassert; "IXPTelAssert"
0x14011d82c  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x14011d831  call    cs:__imp_ExRaiseAccessViolation
0x14011d838  nop     dword ptr [rax+rax+00h]
0x14011d83d  nop
0x14011d83e  mov     eax, 0C0000005h
0x14011d843  mov     [rsp+318h+var_2D8], eax
0x14011d847  xor     edi, edi
0x14011d849  lea     esi, [rdi+2]
0x14011d84c  lea     r14d, [rdi+1]
0x14011d850  mov     ebx, edi
0x14011d852  mov     r15b, dil
0x14011d855  test    eax, eax
0x14011d857  jns     short loc_14011D899
0x14011d859  test    r15b, r15b
0x14011d85c  jnz     loc_14011D9B2
0x14011d862  or      ebx, 0FFFFFFFFh
0x14011d865  jmp     short loc_14011D875
0x14011d867  test    ebx, 0FF000000h
0x14011d86d  cmovnz  ebx, edi
0x14011d870  test    r15b, r15b
0x14011d873  jz      short loc_14011D862
0x14011d875  mov     eax, ebx
0x14011d877  mov     rcx, [rsp+318h+var_48]
0x14011d87f  xor     rcx, rsp; StackCookie
0x14011d882  call    __security_check_cookie
0x14011d887  add     rsp, 2E8h
0x14011d88e  pop     r15
0x14011d890  pop     r14
0x14011d892  pop     r12
0x14011d894  pop     rdi
0x14011d895  pop     rsi
0x14011d896  pop     rbx
0x14011d897  retn
0x14011d899  xorps   xmm0, xmm0
0x14011d89c  movups  xmmword ptr [rsp+318h+DestinationString.Length], xmm0
0x14011d8a1  xorps   xmm1, xmm1
0x14011d8a4  movups  xmmword ptr [rsp+318h+ObjectAttributes.Length], xmm1
0x14011d8a9  movups  xmmword ptr [rsp+318h+ObjectAttributes.ObjectName], xmm1
0x14011d8b1  movups  xmmword ptr [rsp+318h+ObjectAttributes.SecurityDescriptor], xmm1
0x14011d8b9  mov     [rsp+318h+Address], rdi
0x14011d8be  lea     rdx, [rsp+318h+SourceString]; SourceString
0x14011d8c6  lea     rcx, [rsp+318h+DestinationString]; DestinationString
0x14011d8cb  call    cs:__imp_RtlInitUnicodeString
0x14011d8d2  nop     dword ptr [rax+rax+00h]
0x14011d8d7  mov     [rsp+318h+ObjectAttributes.Length], 30h ; '0'
0x14011d8df  mov     [rsp+318h+ObjectAttributes.RootDirectory], rdi
0x14011d8e4  mov     [rsp+318h+ObjectAttributes.Attributes], 240h
0x14011d8ef  lea     rax, [rsp+318h+DestinationString]
0x14011d8f4  mov     [rsp+318h+ObjectAttributes.ObjectName], rax
0x14011d8fc  xorps   xmm0, xmm0
0x14011d8ff  movdqu  xmmword ptr [rsp+318h+ObjectAttributes.SecurityDescriptor], xmm0
0x14011d908  lea     r8, [rsp+318h+ObjectAttributes]; ObjectAttributes
0x14011d90d  mov     edx, 20019h; DesiredAccess
0x14011d912  lea     rcx, [rsp+318h+Address]; KeyHandle
0x14011d917  call    cs:__imp_ZwOpenKey
0x14011d91e  nop     dword ptr [rax+rax+00h]
0x14011d923  test    eax, eax
0x14011d925  js      loc_14011D859
0x14011d92b  mov     [rsp+318h+var_2E8], edi
0x14011d92f  lea     rdx, aSpritefillcolo; "SpriteFillColor"
0x14011d936  lea     rcx, [rsp+318h+DestinationString]; DestinationString
0x14011d93b  call    cs:__imp_RtlInitUnicodeString
0x14011d942  nop     dword ptr [rax+rax+00h]
0x14011d947  lea     rax, [rsp+318h+var_2E8]
0x14011d94c  mov     [rsp+318h+ResultLength], rax; ResultLength
0x14011d951  mov     [rsp+318h+Length], 14h; Length
0x14011d959  lea     r9, [rsp+318h+KeyValueInformation]; KeyValueInformation
0x14011d961  mov     r8d, esi; KeyValueInformationClass
0x14011d964  lea     rdx, [rsp+318h+DestinationString]; ValueName
0x14011d969  mov     rcx, [rsp+318h+Address]; KeyHandle
0x14011d96e  call    cs:__imp_ZwQueryValueKey
0x14011d975  nop     dword ptr [rax+rax+00h]
0x14011d97a  test    eax, eax
0x14011d97c  js      short loc_14011D99C
0x14011d97e  cmp     [rsp+318h+var_26C], 4
0x14011d986  jnz     short loc_14011D99C
0x14011d988  cmp     [rsp+318h+var_268], 4
0x14011d990  jnz     short loc_14011D99C
0x14011d992  mov     ebx, [rsp+318h+var_264]
0x14011d999  mov     r15b, r14b
0x14011d99c  mov     rcx, [rsp+318h+Address]; Handle
0x14011d9a1  call    cs:__imp_ZwClose
0x14011d9a8  nop     dword ptr [rax+rax+00h]
0x14011d9ad  jmp     loc_14011D859
0x14011d9b2  test    ebx, ebx
0x14011d9b4  jz      loc_14011D862
0x14011d9ba  jmp     loc_14011D867
0x1402392e9  push    rbp
0x1402392eb  sub     rsp, 30h
0x1402392ef  mov     rbp, rdx
0x1402392f2  mov     eax, 1
0x1402392f7  add     rsp, 30h
0x1402392fb  pop     rbp
0x1402392fc  retn
```
