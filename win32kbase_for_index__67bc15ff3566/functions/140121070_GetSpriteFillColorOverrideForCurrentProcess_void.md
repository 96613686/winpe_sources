# GetSpriteFillColorOverrideForCurrentProcess(void)

- ea: `0x140121070`
- end: `0x14012139f`
- name: `?GetSpriteFillColorOverrideForCurrentProcess@@YAKXZ`
- size: `815`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14014e31c`

## callees

- `0x140121070`
- `0x1401213a8`
- `0x1401aab9c`
- `0x1402388e0`
- `0x1402bb164`
- `0x1402bb1a0`

## import_xrefs

- `ntoskrnl!PsGetProcessPeb` at `0x1401210f8`
- `ntoskrnl!PsGetProcessPeb` at `0x1401210f8`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401210e9`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401210e9`
- `ntoskrnl!ProbeForRead` at `0x140121122`
- `ntoskrnl!ProbeForRead` at `0x14012114e`
- `ntoskrnl!ProbeForRead` at `0x14012118f`
- `ntoskrnl!ProbeForRead` at `0x140121122`
- `ntoskrnl!ProbeForRead` at `0x14012114e`
- `ntoskrnl!ProbeForRead` at `0x14012118f`
- `ntoskrnl!ExRaiseAccessViolation` at `0x140121211`
- `ntoskrnl!ExRaiseAccessViolation` at `0x140121211`
- `ntoskrnl!ZwOpenKey` at `0x1401212f7`
- `ntoskrnl!ZwOpenKey` at `0x1401212f7`
- `ntoskrnl!ZwQueryValueKey` at `0x14012134e`
- `ntoskrnl!ZwQueryValueKey` at `0x14012134e`
- `ntoskrnl!ZwClose` at `0x140121381`
- `ntoskrnl!ZwClose` at `0x140121381`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401212ab`
- `ntoskrnl!RtlInitUnicodeString` at `0x14012131b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401212ab`
- `ntoskrnl!RtlInitUnicodeString` at `0x14012131b`

## string_xrefs

- `0x140121098`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\Image File Execution Options\`

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
0x140121070  push    rbx
0x140121072  push    rsi
0x140121073  push    rdi
0x140121074  push    r12
0x140121076  push    r14
0x140121078  push    r15
0x14012107a  sub     rsp, 2E8h
0x140121081  mov     rax, cs:__security_cookie
0x140121088  xor     rax, rsp
0x14012108b  mov     [rsp+318h+var_48], rax
0x140121093  mov     eax, 7FFFFFFEh
0x140121098  lea     r8, aRegistryMachin_27; "\\Registry\\Machine\\Software\\Microsof"...
0x14012109f  mov     edx, 104h
0x1401210a4  lea     rcx, [rsp+318h+SourceString]
0x1401210ac  xor     edi, edi
0x1401210ae  lea     esi, [rdi+2]
0x1401210b1  lea     r14d, [rdi+1]
0x1401210b5  test    rax, rax
0x1401210b8  jz      short loc_1401210D6
0x1401210ba  movzx   r9d, word ptr [r8]
0x1401210be  test    r9w, r9w
0x1401210c2  jz      short loc_1401210D6
0x1401210c4  add     r8, rsi
0x1401210c7  mov     [rcx], r9w
0x1401210cb  add     rcx, rsi
0x1401210ce  sub     rax, r14
0x1401210d1  sub     rdx, r14
0x1401210d4  jnz     short loc_1401210B5
0x1401210d6  lea     rax, [rcx-2]
0x1401210da  test    rdx, rdx
0x1401210dd  cmovnz  rax, rcx
0x1401210e1  mov     [rax], di
0x1401210e4  mov     [rsp+318h+var_2C0], rdi
0x1401210e9  call    cs:__imp_PsGetCurrentProcess
0x1401210f0  nop     dword ptr [rax+rax+00h]
0x1401210f5  mov     rcx, rax
0x1401210f8  call    cs:__imp_PsGetProcessPeb
0x1401210ff  nop     dword ptr [rax+rax+00h]
0x140121104  mov     [rsp+318h+Address], rax
0x140121109  mov     [rsp+318h+var_2B8], 7D0h
0x140121112  mov     rcx, [rsp+318h+Address]; Address
0x140121117  mov     [rsp+318h+var_2B8], r14
0x14012111c  mov     r8d, r14d; Alignment
0x14012111f  mov     rdx, r14; Length
0x140121122  call    cs:__imp_ProbeForRead
0x140121129  nop     dword ptr [rax+rax+00h]
0x14012112e  mov     rax, [rsp+318h+Address]
0x140121133  mov     rbx, [rax+20h]
0x140121137  mov     [rsp+318h+var_2B0], 448h
0x140121140  mov     [rsp+318h+var_2B0], r14
0x140121145  mov     r8d, r14d; Alignment
0x140121148  mov     rdx, r14; Length
0x14012114b  mov     rcx, rbx; Address
0x14012114e  call    cs:__imp_ProbeForRead
0x140121155  nop     dword ptr [rax+rax+00h]
0x14012115a  lea     rcx, [rbx+60h]
0x14012115e  call    RtlReadULongFromUser
0x140121163  mov     r15d, eax
0x140121166  mov     dword ptr [rsp+318h+DestinationString.Length], r15d
0x14012116b  lea     rcx, [rbx+68h]
0x14012116f  call    RtlReadULong64FromUser
0x140121174  mov     r12, rax
0x140121177  mov     [rsp+318h+DestinationString.Buffer], rax
0x14012117c  mov     ebx, r15d
0x14012117f  shr     ebx, 10h
0x140121182  movzx   edx, r15w
0x140121186  add     rdx, rsi; Length
0x140121189  mov     r8d, esi; Alignment
0x14012118c  mov     rcx, rax; Address
0x14012118f  call    cs:__imp_ProbeForRead
0x140121196  nop     dword ptr [rax+rax+00h]
0x14012119b  movzx   ecx, r15w
0x14012119f  and     cx, r14w
0x1401211a3  cmp     r15w, bx
0x1401211a7  ja      short loc_1401211EE
0x1401211a9  test    cx, cx
0x1401211ac  jnz     short loc_1401211F3
0x1401211ae  movzx   eax, r15w
0x1401211b2  lea     r8, [r12+rax]; unsigned __int16 *
0x1401211b6  mov     [rsp+318h+var_2C0], r8
0x1401211bb  test    eax, eax
0x1401211bd  jz      short loc_1401211C9
0x1401211bf  lea     rcx, [r8-2]
0x1401211c3  cmp     word ptr [rcx], 5Ch ; '\'
0x1401211c7  jnz     short loc_1401211E1
0x1401211c9  mov     edx, 104h; unsigned __int64
0x1401211ce  lea     rcx, [rsp+318h+SourceString]; unsigned __int16 *
0x1401211d6  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1401211db  mov     [rsp+318h+var_2D8], eax
0x1401211df  jmp     short loc_140121230
0x1401211e1  mov     r8, rcx
0x1401211e4  mov     [rsp+318h+var_2C0], rcx
0x1401211e9  add     eax, 0FFFFFFFEh
0x1401211ec  jmp     short loc_1401211BB
0x1401211ee  test    cx, cx
0x1401211f1  jz      short loc_140121211
0x1401211f3  mov     [rsp+318h+var_2E8], 20000h
0x1401211fb  mov     r8d, 17Eh
0x140121201  mov     edx, [rsp+318h+var_2E8]
0x140121205  lea     rcx, aIxptelassert; "IXPTelAssert"
0x14012120c  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x140121211  call    cs:__imp_ExRaiseAccessViolation
0x140121218  nop     dword ptr [rax+rax+00h]
0x14012121d  nop
0x14012121e  mov     eax, 0C0000005h
0x140121223  mov     [rsp+318h+var_2D8], eax
0x140121227  xor     edi, edi
0x140121229  lea     esi, [rdi+2]
0x14012122c  lea     r14d, [rdi+1]
0x140121230  mov     ebx, edi
0x140121232  mov     r15b, dil
0x140121235  test    eax, eax
0x140121237  jns     short loc_140121279
0x140121239  test    r15b, r15b
0x14012123c  jnz     loc_140121392
0x140121242  or      ebx, 0FFFFFFFFh
0x140121245  jmp     short loc_140121255
0x140121247  test    ebx, 0FF000000h
0x14012124d  cmovnz  ebx, edi
0x140121250  test    r15b, r15b
0x140121253  jz      short loc_140121242
0x140121255  mov     eax, ebx
0x140121257  mov     rcx, [rsp+318h+var_48]
0x14012125f  xor     rcx, rsp; StackCookie
0x140121262  call    __security_check_cookie
0x140121267  add     rsp, 2E8h
0x14012126e  pop     r15
0x140121270  pop     r14
0x140121272  pop     r12
0x140121274  pop     rdi
0x140121275  pop     rsi
0x140121276  pop     rbx
0x140121277  retn
0x140121279  xorps   xmm0, xmm0
0x14012127c  movups  xmmword ptr [rsp+318h+DestinationString.Length], xmm0
0x140121281  xorps   xmm1, xmm1
0x140121284  movups  xmmword ptr [rsp+318h+ObjectAttributes.Length], xmm1
0x140121289  movups  xmmword ptr [rsp+318h+ObjectAttributes.ObjectName], xmm1
0x140121291  movups  xmmword ptr [rsp+318h+ObjectAttributes.SecurityDescriptor], xmm1
0x140121299  mov     [rsp+318h+Address], rdi
0x14012129e  lea     rdx, [rsp+318h+SourceString]; SourceString
0x1401212a6  lea     rcx, [rsp+318h+DestinationString]; DestinationString
0x1401212ab  call    cs:__imp_RtlInitUnicodeString
0x1401212b2  nop     dword ptr [rax+rax+00h]
0x1401212b7  mov     [rsp+318h+ObjectAttributes.Length], 30h ; '0'
0x1401212bf  mov     [rsp+318h+ObjectAttributes.RootDirectory], rdi
0x1401212c4  mov     [rsp+318h+ObjectAttributes.Attributes], 240h
0x1401212cf  lea     rax, [rsp+318h+DestinationString]
0x1401212d4  mov     [rsp+318h+ObjectAttributes.ObjectName], rax
0x1401212dc  xorps   xmm0, xmm0
0x1401212df  movdqu  xmmword ptr [rsp+318h+ObjectAttributes.SecurityDescriptor], xmm0
0x1401212e8  lea     r8, [rsp+318h+ObjectAttributes]; ObjectAttributes
0x1401212ed  mov     edx, 20019h; DesiredAccess
0x1401212f2  lea     rcx, [rsp+318h+Address]; KeyHandle
0x1401212f7  call    cs:__imp_ZwOpenKey
0x1401212fe  nop     dword ptr [rax+rax+00h]
0x140121303  test    eax, eax
0x140121305  js      loc_140121239
0x14012130b  mov     [rsp+318h+var_2E8], edi
0x14012130f  lea     rdx, aSpritefillcolo; "SpriteFillColor"
0x140121316  lea     rcx, [rsp+318h+DestinationString]; DestinationString
0x14012131b  call    cs:__imp_RtlInitUnicodeString
0x140121322  nop     dword ptr [rax+rax+00h]
0x140121327  lea     rax, [rsp+318h+var_2E8]
0x14012132c  mov     [rsp+318h+ResultLength], rax; ResultLength
0x140121331  mov     [rsp+318h+Length], 14h; Length
0x140121339  lea     r9, [rsp+318h+KeyValueInformation]; KeyValueInformation
0x140121341  mov     r8d, esi; KeyValueInformationClass
0x140121344  lea     rdx, [rsp+318h+DestinationString]; ValueName
0x140121349  mov     rcx, [rsp+318h+Address]; KeyHandle
0x14012134e  call    cs:__imp_ZwQueryValueKey
0x140121355  nop     dword ptr [rax+rax+00h]
0x14012135a  test    eax, eax
0x14012135c  js      short loc_14012137C
0x14012135e  cmp     [rsp+318h+var_26C], 4
0x140121366  jnz     short loc_14012137C
0x140121368  cmp     [rsp+318h+var_268], 4
0x140121370  jnz     short loc_14012137C
0x140121372  mov     ebx, [rsp+318h+var_264]
0x140121379  mov     r15b, r14b
0x14012137c  mov     rcx, [rsp+318h+Address]; Handle
0x140121381  call    cs:__imp_ZwClose
0x140121388  nop     dword ptr [rax+rax+00h]
0x14012138d  jmp     loc_140121239
0x140121392  test    ebx, ebx
0x140121394  jz      loc_140121242
0x14012139a  jmp     loc_140121247
0x140239a71  push    rbp
0x140239a73  sub     rsp, 30h
0x140239a77  mov     rbp, rdx
0x140239a7a  mov     eax, 1
0x140239a7f  add     rsp, 30h
0x140239a83  pop     rbp
0x140239a84  retn
```
