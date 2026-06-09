# GetSpriteFillColorOverrideForCurrentProcess(void)

- ea: `0x14011d320`
- end: `0x14011d64f`
- name: `?GetSpriteFillColorOverrideForCurrentProcess@@YAKXZ`
- size: `815`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400b471c`

## callees

- `0x14011d320`
- `0x14011d658`
- `0x1401aa4fc`
- `0x140238b10`
- `0x1402bd208`
- `0x1402bd244`

## import_xrefs

- `ntoskrnl!PsGetProcessPeb` at `0x14011d3a8`
- `ntoskrnl!PsGetProcessPeb` at `0x14011d3a8`
- `ntoskrnl!PsGetCurrentProcess` at `0x14011d399`
- `ntoskrnl!PsGetCurrentProcess` at `0x14011d399`
- `ntoskrnl!ProbeForRead` at `0x14011d3d2`
- `ntoskrnl!ProbeForRead` at `0x14011d3fe`
- `ntoskrnl!ProbeForRead` at `0x14011d43f`
- `ntoskrnl!ProbeForRead` at `0x14011d3d2`
- `ntoskrnl!ProbeForRead` at `0x14011d3fe`
- `ntoskrnl!ProbeForRead` at `0x14011d43f`
- `ntoskrnl!ExRaiseAccessViolation` at `0x14011d4c1`
- `ntoskrnl!ExRaiseAccessViolation` at `0x14011d4c1`
- `ntoskrnl!ZwOpenKey` at `0x14011d5a7`
- `ntoskrnl!ZwOpenKey` at `0x14011d5a7`
- `ntoskrnl!ZwQueryValueKey` at `0x14011d5fe`
- `ntoskrnl!ZwQueryValueKey` at `0x14011d5fe`
- `ntoskrnl!ZwClose` at `0x14011d631`
- `ntoskrnl!ZwClose` at `0x14011d631`
- `ntoskrnl!RtlInitUnicodeString` at `0x14011d55b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14011d5cb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14011d55b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14011d5cb`

## string_xrefs

- `0x14011d348`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\Image File Execution Options\`

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
0x14011d320  push    rbx
0x14011d322  push    rsi
0x14011d323  push    rdi
0x14011d324  push    r12
0x14011d326  push    r14
0x14011d328  push    r15
0x14011d32a  sub     rsp, 2E8h
0x14011d331  mov     rax, cs:__security_cookie
0x14011d338  xor     rax, rsp
0x14011d33b  mov     [rsp+318h+var_48], rax
0x14011d343  mov     eax, 7FFFFFFEh
0x14011d348  lea     r8, aRegistryMachin_27; "\\Registry\\Machine\\Software\\Microsof"...
0x14011d34f  mov     edx, 104h
0x14011d354  lea     rcx, [rsp+318h+SourceString]
0x14011d35c  xor     edi, edi
0x14011d35e  lea     esi, [rdi+2]
0x14011d361  lea     r14d, [rdi+1]
0x14011d365  test    rax, rax
0x14011d368  jz      short loc_14011D386
0x14011d36a  movzx   r9d, word ptr [r8]
0x14011d36e  test    r9w, r9w
0x14011d372  jz      short loc_14011D386
0x14011d374  add     r8, rsi
0x14011d377  mov     [rcx], r9w
0x14011d37b  add     rcx, rsi
0x14011d37e  sub     rax, r14
0x14011d381  sub     rdx, r14
0x14011d384  jnz     short loc_14011D365
0x14011d386  lea     rax, [rcx-2]
0x14011d38a  test    rdx, rdx
0x14011d38d  cmovnz  rax, rcx
0x14011d391  mov     [rax], di
0x14011d394  mov     [rsp+318h+var_2C0], rdi
0x14011d399  call    cs:__imp_PsGetCurrentProcess
0x14011d3a0  nop     dword ptr [rax+rax+00h]
0x14011d3a5  mov     rcx, rax
0x14011d3a8  call    cs:__imp_PsGetProcessPeb
0x14011d3af  nop     dword ptr [rax+rax+00h]
0x14011d3b4  mov     [rsp+318h+Address], rax
0x14011d3b9  mov     [rsp+318h+var_2B8], 7D0h
0x14011d3c2  mov     rcx, [rsp+318h+Address]; Address
0x14011d3c7  mov     [rsp+318h+var_2B8], r14
0x14011d3cc  mov     r8d, r14d; Alignment
0x14011d3cf  mov     rdx, r14; Length
0x14011d3d2  call    cs:__imp_ProbeForRead
0x14011d3d9  nop     dword ptr [rax+rax+00h]
0x14011d3de  mov     rax, [rsp+318h+Address]
0x14011d3e3  mov     rbx, [rax+20h]
0x14011d3e7  mov     [rsp+318h+var_2B0], 450h
0x14011d3f0  mov     [rsp+318h+var_2B0], r14
0x14011d3f5  mov     r8d, r14d; Alignment
0x14011d3f8  mov     rdx, r14; Length
0x14011d3fb  mov     rcx, rbx; Address
0x14011d3fe  call    cs:__imp_ProbeForRead
0x14011d405  nop     dword ptr [rax+rax+00h]
0x14011d40a  lea     rcx, [rbx+60h]
0x14011d40e  call    RtlReadULongFromUser
0x14011d413  mov     r15d, eax
0x14011d416  mov     dword ptr [rsp+318h+DestinationString.Length], r15d
0x14011d41b  lea     rcx, [rbx+68h]
0x14011d41f  call    RtlReadULong64FromUser
0x14011d424  mov     r12, rax
0x14011d427  mov     [rsp+318h+DestinationString.Buffer], rax
0x14011d42c  mov     ebx, r15d
0x14011d42f  shr     ebx, 10h
0x14011d432  movzx   edx, r15w
0x14011d436  add     rdx, rsi; Length
0x14011d439  mov     r8d, esi; Alignment
0x14011d43c  mov     rcx, rax; Address
0x14011d43f  call    cs:__imp_ProbeForRead
0x14011d446  nop     dword ptr [rax+rax+00h]
0x14011d44b  movzx   ecx, r15w
0x14011d44f  and     cx, r14w
0x14011d453  cmp     r15w, bx
0x14011d457  ja      short loc_14011D49E
0x14011d459  test    cx, cx
0x14011d45c  jnz     short loc_14011D4A3
0x14011d45e  movzx   eax, r15w
0x14011d462  lea     r8, [r12+rax]; unsigned __int16 *
0x14011d466  mov     [rsp+318h+var_2C0], r8
0x14011d46b  test    eax, eax
0x14011d46d  jz      short loc_14011D479
0x14011d46f  lea     rcx, [r8-2]
0x14011d473  cmp     word ptr [rcx], 5Ch ; '\'
0x14011d477  jnz     short loc_14011D491
0x14011d479  mov     edx, 104h; unsigned __int64
0x14011d47e  lea     rcx, [rsp+318h+SourceString]; unsigned __int16 *
0x14011d486  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14011d48b  mov     [rsp+318h+var_2D8], eax
0x14011d48f  jmp     short loc_14011D4E0
0x14011d491  mov     r8, rcx
0x14011d494  mov     [rsp+318h+var_2C0], rcx
0x14011d499  add     eax, 0FFFFFFFEh
0x14011d49c  jmp     short loc_14011D46B
0x14011d49e  test    cx, cx
0x14011d4a1  jz      short loc_14011D4C1
0x14011d4a3  mov     [rsp+318h+var_2E8], 20000h
0x14011d4ab  mov     r8d, 17Eh
0x14011d4b1  mov     edx, [rsp+318h+var_2E8]
0x14011d4b5  lea     rcx, aIxptelassert; "IXPTelAssert"
0x14011d4bc  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x14011d4c1  call    cs:__imp_ExRaiseAccessViolation
0x14011d4c8  nop     dword ptr [rax+rax+00h]
0x14011d4cd  nop
0x14011d4ce  mov     eax, 0C0000005h
0x14011d4d3  mov     [rsp+318h+var_2D8], eax
0x14011d4d7  xor     edi, edi
0x14011d4d9  lea     esi, [rdi+2]
0x14011d4dc  lea     r14d, [rdi+1]
0x14011d4e0  mov     ebx, edi
0x14011d4e2  mov     r15b, dil
0x14011d4e5  test    eax, eax
0x14011d4e7  jns     short loc_14011D529
0x14011d4e9  test    r15b, r15b
0x14011d4ec  jnz     loc_14011D642
0x14011d4f2  or      ebx, 0FFFFFFFFh
0x14011d4f5  jmp     short loc_14011D505
0x14011d4f7  test    ebx, 0FF000000h
0x14011d4fd  cmovnz  ebx, edi
0x14011d500  test    r15b, r15b
0x14011d503  jz      short loc_14011D4F2
0x14011d505  mov     eax, ebx
0x14011d507  mov     rcx, [rsp+318h+var_48]
0x14011d50f  xor     rcx, rsp; StackCookie
0x14011d512  call    __security_check_cookie
0x14011d517  add     rsp, 2E8h
0x14011d51e  pop     r15
0x14011d520  pop     r14
0x14011d522  pop     r12
0x14011d524  pop     rdi
0x14011d525  pop     rsi
0x14011d526  pop     rbx
0x14011d527  retn
0x14011d529  xorps   xmm0, xmm0
0x14011d52c  movups  xmmword ptr [rsp+318h+DestinationString.Length], xmm0
0x14011d531  xorps   xmm1, xmm1
0x14011d534  movups  xmmword ptr [rsp+318h+ObjectAttributes.Length], xmm1
0x14011d539  movups  xmmword ptr [rsp+318h+ObjectAttributes.ObjectName], xmm1
0x14011d541  movups  xmmword ptr [rsp+318h+ObjectAttributes.SecurityDescriptor], xmm1
0x14011d549  mov     [rsp+318h+Address], rdi
0x14011d54e  lea     rdx, [rsp+318h+SourceString]; SourceString
0x14011d556  lea     rcx, [rsp+318h+DestinationString]; DestinationString
0x14011d55b  call    cs:__imp_RtlInitUnicodeString
0x14011d562  nop     dword ptr [rax+rax+00h]
0x14011d567  mov     [rsp+318h+ObjectAttributes.Length], 30h ; '0'
0x14011d56f  mov     [rsp+318h+ObjectAttributes.RootDirectory], rdi
0x14011d574  mov     [rsp+318h+ObjectAttributes.Attributes], 240h
0x14011d57f  lea     rax, [rsp+318h+DestinationString]
0x14011d584  mov     [rsp+318h+ObjectAttributes.ObjectName], rax
0x14011d58c  xorps   xmm0, xmm0
0x14011d58f  movdqu  xmmword ptr [rsp+318h+ObjectAttributes.SecurityDescriptor], xmm0
0x14011d598  lea     r8, [rsp+318h+ObjectAttributes]; ObjectAttributes
0x14011d59d  mov     edx, 20019h; DesiredAccess
0x14011d5a2  lea     rcx, [rsp+318h+Address]; KeyHandle
0x14011d5a7  call    cs:__imp_ZwOpenKey
0x14011d5ae  nop     dword ptr [rax+rax+00h]
0x14011d5b3  test    eax, eax
0x14011d5b5  js      loc_14011D4E9
0x14011d5bb  mov     [rsp+318h+var_2E8], edi
0x14011d5bf  lea     rdx, aSpritefillcolo; "SpriteFillColor"
0x14011d5c6  lea     rcx, [rsp+318h+DestinationString]; DestinationString
0x14011d5cb  call    cs:__imp_RtlInitUnicodeString
0x14011d5d2  nop     dword ptr [rax+rax+00h]
0x14011d5d7  lea     rax, [rsp+318h+var_2E8]
0x14011d5dc  mov     [rsp+318h+ResultLength], rax; ResultLength
0x14011d5e1  mov     [rsp+318h+Length], 14h; Length
0x14011d5e9  lea     r9, [rsp+318h+KeyValueInformation]; KeyValueInformation
0x14011d5f1  mov     r8d, esi; KeyValueInformationClass
0x14011d5f4  lea     rdx, [rsp+318h+DestinationString]; ValueName
0x14011d5f9  mov     rcx, [rsp+318h+Address]; KeyHandle
0x14011d5fe  call    cs:__imp_ZwQueryValueKey
0x14011d605  nop     dword ptr [rax+rax+00h]
0x14011d60a  test    eax, eax
0x14011d60c  js      short loc_14011D62C
0x14011d60e  cmp     [rsp+318h+var_26C], 4
0x14011d616  jnz     short loc_14011D62C
0x14011d618  cmp     [rsp+318h+var_268], 4
0x14011d620  jnz     short loc_14011D62C
0x14011d622  mov     ebx, [rsp+318h+var_264]
0x14011d629  mov     r15b, r14b
0x14011d62c  mov     rcx, [rsp+318h+Address]; Handle
0x14011d631  call    cs:__imp_ZwClose
0x14011d638  nop     dword ptr [rax+rax+00h]
0x14011d63d  jmp     loc_14011D4E9
0x14011d642  test    ebx, ebx
0x14011d644  jz      loc_14011D4F2
0x14011d64a  jmp     loc_14011D4F7
0x140239c8e  push    rbp
0x140239c90  sub     rsp, 30h
0x140239c94  mov     rbp, rdx
0x140239c97  mov     eax, 1
0x140239c9c  add     rsp, 30h
0x140239ca0  pop     rbp
0x140239ca1  retn
```
