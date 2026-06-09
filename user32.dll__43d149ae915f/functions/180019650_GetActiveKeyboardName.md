# GetActiveKeyboardName

- ea: `0x180019650`
- end: `0x18001985a`
- name: `GetActiveKeyboardName`
- size: `522`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800564a0`
- `0x18005f274`

## callees

- `0x1800192f4`
- `0x180019650`
- `0x18001a430`
- `0x18004ed44`
- `0x180096e00`

## import_xrefs

- `ntdll!NtDeleteValueKey` at `0x180099b69`
- `ntdll!NtDeleteValueKey` at `0x180099b69`
- `ntdll!NtSetValueKey` at `0x180099b46`
- `ntdll!NtSetValueKey` at `0x180099b46`
- `ntdll!NtCreateKey` at `0x180099af9`
- `ntdll!NtCreateKey` at `0x180099af9`
- `ntdll!wcstoul` at `0x180099a6b`
- `ntdll!wcstoul` at `0x180099a6b`
- `ntdll!NtQueryValueKey` at `0x180019758`
- `ntdll!NtQueryValueKey` at `0x180099941`
- `ntdll!NtQueryValueKey` at `0x180099983`
- `ntdll!NtQueryValueKey` at `0x180099a2a`
- `ntdll!NtQueryValueKey` at `0x180019758`
- `ntdll!NtQueryValueKey` at `0x180099941`
- `ntdll!NtQueryValueKey` at `0x180099983`
- `ntdll!NtQueryValueKey` at `0x180099a2a`
- `ntdll!RtlOpenCurrentUser` at `0x1800196b2`
- `ntdll!RtlOpenCurrentUser` at `0x1800196b2`
- `ntdll!NtClose` at `0x1800197b2`
- `ntdll!NtClose` at `0x1800197bc`
- `ntdll!NtClose` at `0x1800999e8`
- `ntdll!NtClose` at `0x180099b73`
- `ntdll!NtClose` at `0x180099b7d`
- `ntdll!NtClose` at `0x1800197b2`
- `ntdll!NtClose` at `0x1800197bc`
- `ntdll!NtClose` at `0x1800999e8`
- `ntdll!NtClose` at `0x180099b73`
- `ntdll!NtClose` at `0x180099b7d`
- `ntdll!NtOpenKey` at `0x180019704`
- `ntdll!NtOpenKey` at `0x1800999dc`
- `ntdll!NtOpenKey` at `0x180019704`
- `ntdll!NtOpenKey` at `0x1800999dc`
- `ntdll!RtlInitUnicodeString` at `0x1800196cb`
- `ntdll!RtlInitUnicodeString` at `0x180019731`
- `ntdll!RtlInitUnicodeString` at `0x180099918`
- `ntdll!RtlInitUnicodeString` at `0x18009995a`
- `ntdll!RtlInitUnicodeString` at `0x1800999a3`
- `ntdll!RtlInitUnicodeString` at `0x180099a01`
- `ntdll!RtlInitUnicodeString` at `0x180099aab`
- `ntdll!RtlInitUnicodeString` at `0x180099b12`
- `ntdll!RtlInitUnicodeString` at `0x180099b5b`
- `ntdll!RtlInitUnicodeString` at `0x1800196cb`
- `ntdll!RtlInitUnicodeString` at `0x180019731`
- `ntdll!RtlInitUnicodeString` at `0x180099918`
- `ntdll!RtlInitUnicodeString` at `0x18009995a`
- `ntdll!RtlInitUnicodeString` at `0x1800999a3`
- `ntdll!RtlInitUnicodeString` at `0x180099a01`
- `ntdll!RtlInitUnicodeString` at `0x180099aab`
- `ntdll!RtlInitUnicodeString` at `0x180099b12`
- `ntdll!RtlInitUnicodeString` at `0x180099b5b`

## pseudocode

```c
void __fastcall GetActiveKeyboardName(unsigned __int16 *a1)
{
  NTSTATUS v2; // ecx
  __int64 v3; // rax
  unsigned __int16 *v4; // rdx
  __int64 v5; // rbx
  unsigned __int16 *v6; // rcx
  unsigned __int16 *v7; // rdx
  const wchar_t *v8; // r8
  unsigned __int16 *v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rbx
  unsigned __int16 *v12; // rcx
  NTSTATUS v13; // eax
  NTSTATUS v14; // ebx
  NTSTATUS v15; // eax
  int v16; // ecx
  __int16 v17; // ax
  const unsigned __int16 *v18; // r8
  __int64 v19; // rax
  HANDLE v20; // rcx
  HANDLE Handle; // [rsp+40h] [rbp-69h] BYREF
  ULONG ResultLength; // [rsp+48h] [rbp-61h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-59h] BYREF
  void *KeyHandle; // [rsp+60h] [rbp-49h] BYREF
  HANDLE v25; // [rsp+68h] [rbp-41h] BYREF
  ULONG Disposition; // [rsp+70h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-31h] BYREF
  _OWORD KeyValueInformation[2]; // [rsp+A8h] [rbp-1h] BYREF
  int v29; // [rsp+C8h] [rbp+1Fh]

  ResultLength = 0;
  KeyHandle = 0;
  Handle = 0;
  v25 = 0;
  Disposition = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v29 = 0;
  DestinationString = 0;
  memset(KeyValueInformation, 0, sizeof(KeyValueInformation));
  if ( RtlOpenCurrentUser(0x2000000u, &KeyHandle) < 0 )
    goto LABEL_23;
  RtlInitUnicodeString(&DestinationString, L"Keyboard Layout\\Preload");
  ObjectAttributes.RootDirectory = KeyHandle;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey(&Handle, 0x20019u, &ObjectAttributes) < 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"Keyboard Layout");
    ObjectAttributes.RootDirectory = KeyHandle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v14 = NtOpenKey(&Handle, 0xF003Fu, &ObjectAttributes);
    NtClose(KeyHandle);
    if ( v14 >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"Active");
      v15 = NtQueryValueKey(
              Handle,
              &DestinationString,
              KeyValuePartialInformation,
              KeyValueInformation,
              0x24u,
              &ResultLength);
      v16 = 0;
      if ( v15 != -2147483643 )
        v16 = v15;
      if ( v16 < 0 )
      {
        StringCchCopyW(a1, 9u, L"00000409");
        goto LABEL_46;
      }
      StringCchCopyW(a1, 9u, (const unsigned __int16 *)KeyValueInformation + 6);
      if ( (*(_BYTE *)gpsi & 4) != 0 )
      {
        v17 = wcstoul(a1, 0, 16) & 0x3FF;
        if ( v17 == 17 )
        {
          v18 = L"E0010411";
        }
        else
        {
          if ( v17 != 18 )
            goto LABEL_38;
          v18 = L"E0010412";
        }
        StringCchCopyW(a1, 9u, v18);
      }
LABEL_38:
      RtlInitUnicodeString(&DestinationString, L"Preload");
      ObjectAttributes.RootDirectory = Handle;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( NtCreateKey(&v25, 0x2000Fu, &ObjectAttributes, 0, 0, 0, &Disposition) >= 0 )
      {
        RtlInitUnicodeString(&DestinationString, L"1");
        v19 = -1;
        do
          ++v19;
        while ( a1[v19] );
        if ( NtSetValueKey(v25, &DestinationString, 0, 1u, a1, 2 * v19 + 2) >= 0 )
        {
          RtlInitUnicodeString(&DestinationString, L"Active");
          NtDeleteValueKey(Handle, &DestinationString);
        }
        NtClose(Handle);
        v20 = v25;
        goto LABEL_44;
      }
LABEL_46:
      v20 = Handle;
LABEL_44:
      NtClose(v20);
      return;
    }
LABEL_23:
    StringCchCopyW(a1, 9u, L"00000409");
    return;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultKeyboardInputProfile>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DefaultKeyboardInputProfile>::GetImpl'::`2'::impl) )
  {
    RtlInitUnicodeString(&DestinationString, 0);
    if ( NtQueryValueKey(
           Handle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x24u,
           &ResultLength) >= 0 )
      goto LABEL_5;
    RtlInitUnicodeString(&DestinationString, L"1");
    v13 = NtQueryValueKey(
            Handle,
            &DestinationString,
            KeyValuePartialInformation,
            KeyValueInformation,
            0x24u,
            &ResultLength);
    v2 = 0;
    if ( v13 != -2147483643 )
      v2 = v13;
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, L"1");
    v2 = NtQueryValueKey(
           Handle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x24u,
           &ResultLength);
    if ( v2 == -2147483643 )
      goto LABEL_5;
  }
  if ( v2 < 0 )
  {
    v10 = 2147483646;
    v8 = L"00000409";
    v11 = 9;
    v9 = a1;
    do
    {
      if ( !v10 )
        break;
      if ( !*v8 )
        break;
      *v9++ = *v8++;
      --v10;
      --v11;
    }
    while ( v11 );
    v12 = v9 - 1;
    if ( v11 )
      v12 = v9;
    *v12 = 0;
    goto LABEL_12;
  }
LABEL_5:
  v3 = 2147483646;
  v4 = (unsigned __int16 *)KeyValueInformation + 6;
  v5 = 9;
  v6 = a1;
  do
  {
    if ( !v3 )
      break;
    if ( !*v4 )
      break;
    *v6++ = *v4++;
    --v3;
    --v5;
  }
  while ( v5 );
  v7 = v6 - 1;
  if ( v5 )
    v7 = v6;
  *v7 = 0;
LABEL_12:
  NtClose(Handle);
  NtClose(KeyHandle);
  if ( (*(_BYTE *)gpsi & 4) != 0 )
    CheckValidLayoutName(a1);
}

```

## disassembly

```asm
0x180019650  push    rbp
0x180019652  push    rbx
0x180019653  push    rsi
0x180019654  push    rdi
0x180019655  lea     rbp, [rsp-3Fh]
0x18001965a  sub     rsp, 0E8h
0x180019661  mov     rax, cs:__security_cookie
0x180019668  xor     rax, rsp
0x18001966b  mov     [rbp+57h+var_30], rax
0x18001966f  xor     esi, esi
0x180019671  lea     rdx, [rbp+57h+KeyHandle]; KeyHandle
0x180019675  xorps   xmm0, xmm0
0x180019678  mov     [rbp+57h+var_B8], esi
0x18001967b  xorps   xmm1, xmm1
0x18001967e  mov     [rbp+57h+KeyHandle], rsi
0x180019682  mov     rdi, rcx
0x180019685  mov     [rbp+57h+Handle], rsi
0x180019689  xor     eax, eax
0x18001968b  mov     [rbp+57h+var_98], rsi
0x18001968f  mov     ecx, 2000000h; DesiredAccess
0x180019694  mov     [rbp+57h+var_90], esi
0x180019697  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18001969b  mov     [rbp+57h+var_38], eax
0x18001969e  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800196a2  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800196a6  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800196aa  movups  [rbp+57h+KeyValueInformation], xmm1
0x1800196ae  movups  [rbp+57h+var_48], xmm1
0x1800196b2  call    cs:__imp_RtlOpenCurrentUser
0x1800196b8  test    eax, eax
0x1800196ba  js      loc_180019841
0x1800196c0  lea     rdx, aKeyboardLayout_0; "Keyboard Layout\\Preload"
0x1800196c7  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800196cb  call    cs:__imp_RtlInitUnicodeString
0x1800196d1  mov     rax, [rbp+57h+KeyHandle]
0x1800196d5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800196d9  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800196dd  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x1800196e1  lea     rax, [rbp+57h+DestinationString]
0x1800196e5  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800196ec  xorps   xmm0, xmm0
0x1800196ef  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800196f3  mov     edx, 20019h; DesiredAccess
0x1800196f8  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800196ff  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180019704  call    cs:__imp_NtOpenKey
0x18001970a  test    eax, eax
0x18001970c  js      loc_180099998
0x180019712  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DefaultKeyboardInputProfile@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DefaultKeyboardInputProfile@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultKeyboardInputProfile> `wil::Feature<__WilFeatureTraits_Feature_DefaultKeyboardInputProfile>::GetImpl(void)'::`2'::impl
0x180019719  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DefaultKeyboardInputProfile@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultKeyboardInputProfile>::__private_IsEnabled(void)
0x18001971e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180019722  test    al, al
0x180019724  jnz     loc_180099916
0x18001972a  lea     rdx, a1; "1"
0x180019731  call    cs:__imp_RtlInitUnicodeString
0x180019737  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x18001973b  lea     rax, [rbp+57h+var_B8]
0x18001973f  mov     [rsp+100h+ResultLength], rax; ResultLength
0x180019744  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180019748  lea     r8d, [rsi+2]; KeyValueInformationClass
0x18001974c  mov     [rsp+100h+Length], 24h ; '$'; Length
0x180019754  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180019758  call    cs:__imp_NtQueryValueKey
0x18001975e  mov     ecx, eax
0x180019760  cmp     eax, 80000005h
0x180019765  jnz     loc_180019837
0x18001976b  mov     eax, 7FFFFFFEh
0x180019770  lea     rdx, [rbp+57h+KeyValueInformation+0Ch]
0x180019774  mov     ebx, 9
0x180019779  mov     rcx, rdi
0x18001977c  test    rax, rax
0x18001977f  jz      short loc_1800197A0
0x180019781  movzx   r8d, word ptr [rdx]
0x180019785  test    r8w, r8w
0x180019789  jz      short loc_1800197A0
0x18001978b  mov     [rcx], r8w
0x18001978f  add     rdx, 2
0x180019793  add     rcx, 2
0x180019797  dec     rax
0x18001979a  sub     rbx, 1
0x18001979e  jnz     short loc_18001977C
0x1800197a0  test    rbx, rbx
0x1800197a3  lea     rdx, [rcx-2]
0x1800197a7  cmovnz  rdx, rcx
0x1800197ab  mov     [rdx], si
0x1800197ae  mov     rcx, [rbp+57h+Handle]; Handle
0x1800197b2  call    cs:__imp_NtClose
0x1800197b8  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800197bc  call    cs:__imp_NtClose
0x1800197c2  mov     rax, cs:gpsi
0x1800197c9  test    byte ptr [rax], 4
0x1800197cc  jz      short loc_1800197D6
0x1800197ce  mov     rcx, rdi; unsigned __int16 *
0x1800197d1  call    ?CheckValidLayoutName@@YAXPEAG@Z; CheckValidLayoutName(ushort *)
0x1800197d6  mov     rcx, [rbp+57h+var_30]
0x1800197da  xor     rcx, rsp; StackCookie
0x1800197dd  call    __security_check_cookie
0x1800197e2  add     rsp, 0E8h
0x1800197e9  pop     rdi
0x1800197ea  pop     rsi
0x1800197eb  pop     rbx
0x1800197ec  pop     rbp
0x1800197ed  retn
0x1800197ee  mov     eax, 7FFFFFFEh
0x1800197f3  lea     r8, a00000409; "00000409"
0x1800197fa  mov     ebx, 9
0x1800197ff  mov     rdx, rdi
0x180019802  test    rax, rax
0x180019805  jz      short loc_180019824
0x180019807  movzx   ecx, word ptr [r8]
0x18001980b  test    cx, cx
0x18001980e  jz      short loc_180019824
0x180019810  mov     [rdx], cx
0x180019813  add     r8, 2
0x180019817  add     rdx, 2
0x18001981b  dec     rax
0x18001981e  sub     rbx, 1
0x180019822  jnz     short loc_180019802
0x180019824  test    rbx, rbx
0x180019827  lea     rcx, [rdx-2]
0x18001982b  cmovnz  rcx, rdx
0x18001982f  mov     [rcx], si
0x180019832  jmp     loc_1800197AE
0x180019837  test    ecx, ecx
0x180019839  jns     loc_18001976B
0x18001983f  jmp     short loc_1800197EE
0x180019841  lea     r8, a00000409; "00000409"
0x180019848  mov     edx, 9; unsigned __int64
0x18001984d  mov     rcx, rdi; unsigned __int16 *
0x180019850  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180019855  jmp     loc_1800197D6
0x180099916  xor     edx, edx; SourceString
0x180099918  call    cs:__imp_RtlInitUnicodeString
0x18009991e  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x180099922  lea     rax, [rbp+57h+var_B8]
0x180099926  mov     [rsp+100h+ResultLength], rax; ResultLength
0x18009992b  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18009992f  mov     r8d, 2; KeyValueInformationClass
0x180099935  mov     [rsp+100h+Length], 24h ; '$'; Length
0x18009993d  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180099941  call    cs:__imp_NtQueryValueKey
0x180099947  test    eax, eax
0x180099949  jns     loc_18001976B
0x18009994f  lea     rdx, a1; "1"
0x180099956  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18009995a  call    cs:__imp_RtlInitUnicodeString
0x180099960  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x180099964  lea     rax, [rbp+57h+var_B8]
0x180099968  mov     [rsp+100h+ResultLength], rax; ResultLength
0x18009996d  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180099971  mov     r8d, 2; KeyValueInformationClass
0x180099977  mov     [rsp+100h+Length], 24h ; '$'; Length
0x18009997f  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180099983  call    cs:__imp_NtQueryValueKey
0x180099989  cmp     eax, 80000005h
0x18009998e  mov     ecx, esi
0x180099990  cmovnz  ecx, eax
0x180099993  jmp     loc_180019837
0x180099998  lea     rdx, aKeyboardLayout; "Keyboard Layout"
0x18009999f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800999a3  call    cs:__imp_RtlInitUnicodeString
0x1800999a9  mov     rax, [rbp+57h+KeyHandle]
0x1800999ad  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800999b1  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800999b5  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x1800999b9  lea     rax, [rbp+57h+DestinationString]
0x1800999bd  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800999c4  xorps   xmm0, xmm0
0x1800999c7  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800999cb  mov     edx, 0F003Fh; DesiredAccess
0x1800999d0  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800999d7  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800999dc  call    cs:__imp_NtOpenKey
0x1800999e2  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800999e6  mov     ebx, eax
0x1800999e8  call    cs:__imp_NtClose
0x1800999ee  test    ebx, ebx
0x1800999f0  js      loc_180019841
0x1800999f6  lea     rdx, aActive; "Active"
0x1800999fd  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180099a01  call    cs:__imp_RtlInitUnicodeString
0x180099a07  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x180099a0b  lea     rax, [rbp+57h+var_B8]
0x180099a0f  mov     [rsp+100h+ResultLength], rax; ResultLength
0x180099a14  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180099a18  mov     r8d, 2; KeyValueInformationClass
0x180099a1e  mov     [rsp+100h+Length], 24h ; '$'; Length
0x180099a26  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180099a2a  call    cs:__imp_NtQueryValueKey
0x180099a30  cmp     eax, 80000005h
0x180099a35  mov     ecx, esi
0x180099a37  cmovnz  ecx, eax
0x180099a3a  test    ecx, ecx
0x180099a3c  mov     rcx, rdi; unsigned __int16 *
0x180099a3f  js      loc_180099B89
0x180099a45  mov     ebx, 9
0x180099a4a  lea     r8, [rbp+57h+KeyValueInformation+0Ch]; unsigned __int16 *
0x180099a4e  mov     edx, ebx; unsigned __int64
0x180099a50  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180099a55  mov     r11, cs:gpsi
0x180099a5c  test    byte ptr [r11], 4
0x180099a60  jz      short loc_180099AA0
0x180099a62  xor     edx, edx; EndPtr
0x180099a64  lea     r8d, [rbx+7]; Radix
0x180099a68  mov     rcx, rdi; String
0x180099a6b  call    cs:__imp_wcstoul
0x180099a71  mov     ecx, 3FFh
0x180099a76  and     ax, cx
0x180099a79  cmp     ax, 11h
0x180099a7d  jnz     short loc_180099A88
0x180099a7f  lea     r8, aE0010411; "E0010411"
0x180099a86  jmp     short loc_180099A95
0x180099a88  cmp     ax, 12h
0x180099a8c  jnz     short loc_180099AA0
0x180099a8e  lea     r8, aE0010412; "E0010412"
0x180099a95  mov     rdx, rbx; unsigned __int64
0x180099a98  mov     rcx, rdi; unsigned __int16 *
0x180099a9b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180099aa0  lea     rdx, aPreload; "Preload"
0x180099aa7  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180099aab  call    cs:__imp_RtlInitUnicodeString
0x180099ab1  mov     rax, [rbp+57h+Handle]
0x180099ab5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180099ab9  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180099abd  lea     rcx, [rbp+57h+var_98]; KeyHandle
0x180099ac1  lea     rax, [rbp+57h+DestinationString]
0x180099ac5  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180099acc  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180099ad0  xorps   xmm0, xmm0
0x180099ad3  lea     rax, [rbp+57h+var_90]
0x180099ad7  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180099ade  mov     [rsp+100h+Disposition], rax; Disposition
0x180099ae3  xor     r9d, r9d; TitleIndex
0x180099ae6  mov     dword ptr [rsp+100h+ResultLength], esi; CreateOptions
0x180099aea  mov     edx, 2000Fh; DesiredAccess
0x180099aef  mov     qword ptr [rsp+100h+Length], rsi; Class
0x180099af4  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180099af9  call    cs:__imp_NtCreateKey
0x180099aff  test    eax, eax
0x180099b01  js      loc_180099B9A
0x180099b07  lea     rdx, a1; "1"
0x180099b0e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180099b12  call    cs:__imp_RtlInitUnicodeString
0x180099b18  or      rax, 0FFFFFFFFFFFFFFFFh
0x180099b1c  inc     rax
0x180099b1f  cmp     [rdi+rax*2], si
0x180099b23  jnz     short loc_180099B1C
0x180099b25  mov     rcx, [rbp+57h+var_98]; KeyHandle
0x180099b29  lea     eax, ds:2[rax*2]
0x180099b30  mov     dword ptr [rsp+100h+ResultLength], eax; DataSize
0x180099b34  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180099b38  mov     r9d, 1; Type
0x180099b3e  mov     qword ptr [rsp+100h+Length], rdi; Data
0x180099b43  xor     r8d, r8d; TitleIndex
0x180099b46  call    cs:__imp_NtSetValueKey
0x180099b4c  test    eax, eax
0x180099b4e  js      short loc_180099B6F
0x180099b50  lea     rdx, aActive; "Active"
0x180099b57  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180099b5b  call    cs:__imp_RtlInitUnicodeString
0x180099b61  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x180099b65  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180099b69  call    cs:__imp_NtDeleteValueKey
0x180099b6f  mov     rcx, [rbp+57h+Handle]; Handle
0x180099b73  call    cs:__imp_NtClose
0x180099b79  mov     rcx, [rbp+57h+var_98]; Handle
0x180099b7d  call    cs:__imp_NtClose
0x180099b83  nop
0x180099b84  jmp     loc_1800197D6
0x180099b89  lea     r8, a00000409; "00000409"
0x180099b90  mov     edx, 9; unsigned __int64
0x180099b95  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180099b9a  mov     rcx, [rbp+57h+Handle]
0x180099b9e  jmp     short loc_180099B7D
```
