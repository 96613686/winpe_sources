# SmpCreateDynamicEnvironmentVariables

- ea: `0x140013a40`
- end: `0x140013fd2`
- name: `SmpCreateDynamicEnvironmentVariables`
- size: `1426`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000c638`

## callees

- `0x1400010ec`
- `0x140004e30`
- `0x14000d4c0`
- `0x140013a40`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtClose` at `0x140013d81`
- `ntdll!NtClose` at `0x140013dc5`
- `ntdll!NtClose` at `0x140013d81`
- `ntdll!NtClose` at `0x140013dc5`
- `ntdll!NtQuerySystemInformation` at `0x140013bbc`
- `ntdll!NtQuerySystemInformation` at `0x140013bbc`
- `ntdll!NtOpenKey` at `0x140013d33`
- `ntdll!NtOpenKey` at `0x140013d33`
- `ntdll!NtSetValueKey` at `0x140013bf0`
- `ntdll!NtSetValueKey` at `0x140013c77`
- `ntdll!NtSetValueKey` at `0x140013ce7`
- `ntdll!NtSetValueKey` at `0x140013e56`
- `ntdll!NtSetValueKey` at `0x140013f12`
- `ntdll!NtSetValueKey` at `0x140013f85`
- `ntdll!NtSetValueKey` at `0x140013bf0`
- `ntdll!NtSetValueKey` at `0x140013c77`
- `ntdll!NtSetValueKey` at `0x140013ce7`
- `ntdll!NtSetValueKey` at `0x140013e56`
- `ntdll!NtSetValueKey` at `0x140013f12`
- `ntdll!NtSetValueKey` at `0x140013f85`
- `ntdll!NtQueryValueKey` at `0x140013d70`
- `ntdll!NtQueryValueKey` at `0x140013db8`
- `ntdll!NtQueryValueKey` at `0x140013d70`
- `ntdll!NtQueryValueKey` at `0x140013db8`
- `ntdll!_wcsupr_s` at `0x140013ec5`
- `ntdll!_wcsupr_s` at `0x140013ec5`

## string_xrefs

- `0x140013aed`: `\Registry\Machine\Hardware\Description\System\CentralProcessor\0`
- `0x140013c09`: `SmpCreateDynamicEnvironmentVariables`
- `0x140013e13`: `SmpCreateDynamicEnvironmentVariables`
- `0x140013f4b`: `DSREPAIR`

## pseudocode

```c
__int64 __fastcall SmpCreateDynamicEnvironmentVariables(HANDLE KeyHandle)
{
  NTSTATUS v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // r8
  __int64 v5; // rdx
  NTSTATUS v6; // eax
  PWSTR Buffer; // r8
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 *v10; // rcx
  ULONG DataSize; // eax
  __int64 v12; // rdi
  __int64 v13; // rax
  NTSTATUS v14; // ebx
  __int64 v15; // rax
  NTSTATUS v16; // eax
  __int64 v17; // rax
  unsigned __int16 v18; // dx
  wchar_t *v19; // rcx
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandlea; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING v24; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING v25; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v27; // [rsp+78h] [rbp-88h]
  struct _UNICODE_STRING v28; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING v29; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING v30; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING v31; // [rsp+B0h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-40h] BYREF
  __int64 SystemInformation; // [rsp+100h] [rbp+0h] BYREF
  int v34; // [rsp+108h] [rbp+8h]
  __int64 v35; // [rsp+110h] [rbp+10h] BYREF
  __int64 v36; // [rsp+118h] [rbp+18h] BYREF
  __int64 v37; // [rsp+120h] [rbp+20h] BYREF
  int v38; // [rsp+128h] [rbp+28h]
  __int64 v39; // [rsp+130h] [rbp+30h] BYREF
  int v40; // [rsp+138h] [rbp+38h]
  _BYTE Data[22]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v42; // [rsp+158h] [rbp+58h] BYREF
  wchar_t pszDest[6]; // [rsp+170h] [rbp+70h] BYREF
  wchar_t v44[250]; // [rsp+17Ch] [rbp+7Ch] BYREF
  _BYTE KeyValueInformation[12]; // [rsp+370h] [rbp+270h] BYREF
  _BYTE v46[500]; // [rsp+37Ch] [rbp+27Ch] BYREF

  *(_QWORD *)&ValueName.Length = 393220;
  SystemInformation = 0;
  v34 = 0;
  v36 = 0x3600380078LL;
  v40 = *(_DWORD *)L"4";
  memset(&ObjectAttributes, 0, 44);
  v35 = 0x4D00520041LL;
  v38 = *(_DWORD *)L"4";
  ValueName.Buffer = L"OS";
  v27 = L"\\Registry\\Machine\\Hardware\\Description\\System\\CentralProcessor\\0";
  v24.Buffer = L"PROCESSOR_ARCHITECTURE";
  v25.Buffer = L"PROCESSOR_LEVEL";
  v29.Buffer = L"PROCESSOR_IDENTIFIER";
  v30.Buffer = L"PROCESSOR_REVISION";
  *(_OWORD *)Data = *(_OWORD *)L"Windows_NT";
  v28.Buffer = L"Identifier";
  v39 = *(_QWORD *)L"AMD64";
  v37 = *(_QWORD *)L"ARM64";
  v31.Buffer = L"VendorIdentifier";
  ResultLength = 0;
  KeyHandlea = 0;
  *(_QWORD *)&Data[14] = *(_QWORD *)L"_NT";
  v42 = *(_OWORD *)L"Unknown";
  v26 = 8519808;
  *(_QWORD *)&v24.Length = 3014700;
  *(_QWORD *)&v25.Length = 2097182;
  *(_QWORD *)&v29.Length = 2752552;
  *(_QWORD *)&v30.Length = 2490404;
  *(_QWORD *)&v28.Length = 1441812;
  *(_QWORD *)&v31.Length = 2228256;
  v2 = NtQuerySystemInformation(SystemProcessorInformation, &SystemInformation, 0xCu, 0);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = (unsigned int)v2;
    v5 = 3196;
LABEL_33:
    SmpLogFailure("SmpCreateDynamicEnvironmentVariables", v5, v4);
    return v3;
  }
  v6 = NtSetValueKey(KeyHandle, &ValueName, 0, 1u, Data, 0x16u);
  v3 = v6;
  if ( v6 >= 0 )
  {
    if ( (_WORD)SystemInformation )
    {
      if ( (unsigned __int16)SystemInformation != 5 )
      {
        if ( (unsigned __int16)SystemInformation == 9 )
        {
          v10 = &v39;
        }
        else
        {
          if ( (unsigned __int16)SystemInformation != 12 )
          {
            v10 = (__int64 *)&v42;
            DataSize = 16;
            goto LABEL_18;
          }
          v10 = &v37;
        }
        DataSize = 12;
LABEL_18:
        ResultLength = DataSize;
        v6 = NtSetValueKey(KeyHandle, &v24, 0, 1u, v10, DataSize);
        v3 = v6;
        if ( v6 < 0 )
        {
          Buffer = v24.Buffer;
          v8 = 3254;
          goto LABEL_5;
        }
        RtlStringCbPrintfW(pszDest, 0x200u, L"%u", WORD1(SystemInformation));
        v12 = -1;
        v13 = -1;
        do
          ++v13;
        while ( pszDest[v13] );
        v6 = NtSetValueKey(KeyHandle, &v25, 0, 1u, pszDest, 2 * v13 + 2);
        v3 = v6;
        if ( v6 < 0 )
        {
          Buffer = v25.Buffer;
          v8 = 3291;
          goto LABEL_5;
        }
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = (PUNICODE_STRING)&v26;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v6 = NtOpenKey(&KeyHandlea, 0x20019u, &ObjectAttributes);
        v3 = v6;
        if ( v6 < 0 )
        {
          Buffer = (PWSTR)v27;
          v8 = 3311;
          goto LABEL_5;
        }
        v3 = NtQueryValueKey(KeyHandlea, &v28, KeyValuePartialInformation, pszDest, 0x200u, &ResultLength);
        if ( (v3 & 0x80000000) != 0 )
        {
          NtClose(KeyHandlea);
          Buffer = v28.Buffer;
          v9 = v3;
          v8 = 3330;
          goto LABEL_6;
        }
        v14 = NtQueryValueKey(KeyHandlea, &v31, KeyValuePartialInformation, KeyValueInformation, 0x200u, &ResultLength);
        NtClose(KeyHandlea);
        if ( v14 >= 0 )
        {
          v15 = -1;
          do
            ++v15;
          while ( v44[v15] );
          v16 = RtlStringCbPrintfW(&v44[v15], 500 - 2 * v15, L", %ws", v46);
          v3 = v16;
          if ( v16 < 0 )
          {
            v4 = (unsigned int)v16;
            v5 = 3373;
            goto LABEL_33;
          }
        }
        v17 = -1;
        do
          ++v17;
        while ( v44[v17] );
        v6 = NtSetValueKey(KeyHandle, &v29, 0, 1u, v44, 2 * v17 + 2);
        v3 = v6;
        if ( v6 < 0 )
        {
          Buffer = v29.Buffer;
          v8 = 3389;
          goto LABEL_5;
        }
        if ( (_WORD)SystemInformation )
        {
          if ( (unsigned __int16)SystemInformation != 5
            && (unsigned __int16)SystemInformation != 9
            && (unsigned __int16)SystemInformation != 12 )
          {
            RtlStringCbPrintfW(pszDest, 0x200u, L"%u", WORD2(SystemInformation));
            goto LABEL_46;
          }
        }
        else if ( (WORD2(SystemInformation) & 0xFF00) == 0xFF00 )
        {
          RtlStringCbPrintfW(pszDest, 0x200u, L"%02x", BYTE4(SystemInformation));
          _wcsupr_s(pszDest, 0x100u);
          goto LABEL_46;
        }
        RtlStringCbPrintfW(pszDest, 0x200u, L"%04x", WORD2(SystemInformation));
        do
LABEL_46:
          ++v12;
        while ( pszDest[v12] );
        v6 = NtSetValueKey(KeyHandle, &v30, 0, 1u, pszDest, 2 * v12 + 2);
        v3 = v6;
        if ( v6 < 0 )
        {
          Buffer = v30.Buffer;
          v8 = 3465;
          goto LABEL_5;
        }
        if ( SmpSafeBootOption == -1 )
          return 0;
        v18 = 18;
        if ( SmpSafeBootOption != 1 )
        {
          if ( SmpSafeBootOption == 2 )
          {
            v19 = L"NETWORK";
LABEL_56:
            v18 = 16;
LABEL_57:
            v6 = NtSetValueKey(KeyHandle, (PUNICODE_STRING)&SmpSafeBootEnvironmentValue, 0, 1u, v19, v18);
            v3 = v6;
            if ( v6 < 0 )
            {
              Buffer = L"SAFEBOOT_OPTION";
              v8 = 3506;
              goto LABEL_5;
            }
            return 0;
          }
          if ( SmpSafeBootOption == 3 )
          {
            v19 = L"DSREPAIR";
            goto LABEL_57;
          }
        }
        v19 = L"MINIMAL";
        goto LABEL_56;
      }
      v10 = &v35;
    }
    else
    {
      v10 = &v36;
    }
    DataSize = 8;
    goto LABEL_18;
  }
  Buffer = ValueName.Buffer;
  v8 = 3211;
LABEL_5:
  v9 = (unsigned int)v6;
LABEL_6:
  SmpLogFailureString("SmpCreateDynamicEnvironmentVariables", v8, Buffer, v9);
  return v3;
}

```

## disassembly

```asm
0x140013a40  mov     [rsp-8+arg_8], rbx
0x140013a45  mov     [rsp-8+arg_10], rsi
0x140013a4a  push    rbp
0x140013a4b  push    rdi
0x140013a4c  push    r12
0x140013a4e  push    r14
0x140013a50  push    r15
0x140013a52  lea     rbp, [rsp-480h]
0x140013a5a  sub     rsp, 580h
0x140013a61  mov     rax, cs:__security_cookie
0x140013a68  xor     rax, rsp
0x140013a6b  mov     [rbp+4A0h+var_30], rax
0x140013a72  movsd   xmm1, qword ptr cs:aWindowsNt+0Eh; "_NT"
0x140013a7a  lea     rdx, [rbp+4A0h+SystemInformation]; SystemInformation
0x140013a7e  xor     eax, eax
0x140013a80  mov     qword ptr [rsp+5A0h+ValueName.Length], 60004h
0x140013a89  mov     [rbp+4A0h+SystemInformation], rax
0x140013a8d  xorps   xmm0, xmm0
0x140013a90  mov     [rbp+4A0h+var_498], eax
0x140013a93  xor     r14d, r14d
0x140013a96  movups  xmmword ptr [rbp+4A0h+ObjectAttributes.ObjectName], xmm0
0x140013a9a  mov     rax, 3600380078h
0x140013aa4  mov     rsi, rcx
0x140013aa7  mov     [rbp+4A0h+var_488], rax
0x140013aab  xor     r9d, r9d; ReturnLength
0x140013aae  mov     eax, dword ptr cs:aAmd64+8; "4"
0x140013ab4  lea     r12d, [r14+1]
0x140013ab8  mov     [rbp+4A0h+var_468], eax
0x140013abb  lea     r8d, [r14+0Ch]; SystemInformationLength
0x140013abf  movups  xmmword ptr [rbp+4A0h+ObjectAttributes.Length], xmm0
0x140013ac3  mov     rax, 4D00520041h
0x140013acd  mov     ecx, r12d; SystemInformationClass
0x140013ad0  mov     [rbp+4A0h+var_490], rax
0x140013ad4  lea     edi, [r14+16h]
0x140013ad8  mov     eax, dword ptr cs:aArm64+8; "4"
0x140013ade  mov     [rbp+4A0h+var_478], eax
0x140013ae1  lea     rax, aOs; "OS"
0x140013ae8  mov     [rsp+5A0h+ValueName.Buffer], rax
0x140013aed  lea     rax, aRegistryMachin_76; "\\Registry\\Machine\\Hardware\\Descript"...
0x140013af4  mov     [rsp+5A0h+var_528], rax
0x140013af9  lea     rax, aProcessorArchi; "PROCESSOR_ARCHITECTURE"
0x140013b00  mov     [rsp+5A0h+var_550.Buffer], rax
0x140013b05  lea     rax, aProcessorLevel; "PROCESSOR_LEVEL"
0x140013b0c  movups  xmmword ptr [rbp+4A0h+ObjectAttributes+1Ch], xmm0
0x140013b10  mov     [rsp+5A0h+var_540.Buffer], rax
0x140013b15  lea     rax, aProcessorIdent; "PROCESSOR_IDENTIFIER"
0x140013b1c  movups  xmm0, xmmword ptr cs:aWindowsNt; "Windows_NT"
0x140013b23  mov     [rbp+4A0h+var_510.Buffer], rax
0x140013b27  lea     rax, aProcessorRevis; "PROCESSOR_REVISION"
0x140013b2e  mov     [rbp+4A0h+var_500.Buffer], rax
0x140013b32  lea     rax, aIdentifier; "Identifier"
0x140013b39  movups  xmmword ptr [rbp+4A0h+var_460], xmm0
0x140013b3d  mov     [rbp+4A0h+var_520.Buffer], rax
0x140013b41  lea     rax, aVendoridentifi; "VendorIdentifier"
0x140013b48  movsd   xmm0, qword ptr cs:aAmd64; "AMD64"
0x140013b50  movsd   [rbp+4A0h+var_470], xmm0
0x140013b55  movsd   xmm0, qword ptr cs:aArm64; "ARM64"
0x140013b5d  movsd   [rbp+4A0h+var_480], xmm0
0x140013b62  movups  xmm0, xmmword ptr cs:aUnknown; "Unknown"
0x140013b69  mov     [rbp+4A0h+var_4F0.Buffer], rax
0x140013b6d  mov     [rsp+5A0h+ResultLength], r14d
0x140013b72  mov     [rsp+5A0h+KeyHandle], r14
0x140013b77  movsd   qword ptr [rbp+4A0h+var_460+0Eh], xmm1
0x140013b7c  movdqu  [rbp+4A0h+var_448], xmm0
0x140013b81  mov     [rsp+5A0h+var_530], 820080h
0x140013b8a  mov     qword ptr [rsp+5A0h+var_550.Length], 2E002Ch
0x140013b93  mov     qword ptr [rsp+5A0h+var_540.Length], 20001Eh
0x140013b9c  mov     qword ptr [rbp+4A0h+var_510.Length], 2A0028h
0x140013ba4  mov     qword ptr [rbp+4A0h+var_500.Length], 260024h
0x140013bac  mov     qword ptr [rbp+4A0h+var_520.Length], 160014h
0x140013bb4  mov     qword ptr [rbp+4A0h+var_4F0.Length], 220020h
0x140013bbc  call    cs:__imp_NtQuerySystemInformation
0x140013bc2  mov     ebx, eax
0x140013bc4  test    eax, eax
0x140013bc6  jns     short loc_140013BD5
0x140013bc8  mov     r8d, eax
0x140013bcb  mov     edx, 0C7Ch
0x140013bd0  jmp     loc_140013E13
0x140013bd5  lea     rax, [rbp+4A0h+var_460]
0x140013bd9  mov     [rsp+5A0h+DataSize], edi; DataSize
0x140013bdd  mov     r9d, r12d; Type
0x140013be0  mov     [rsp+5A0h+Data], rax; Data
0x140013be5  xor     r8d, r8d; TitleIndex
0x140013be8  lea     rdx, [rsp+5A0h+ValueName]; ValueName
0x140013bed  mov     rcx, rsi; KeyHandle
0x140013bf0  call    cs:__imp_NtSetValueKey
0x140013bf6  mov     ebx, eax
0x140013bf8  test    eax, eax
0x140013bfa  jns     short loc_140013C1A
0x140013bfc  mov     r8, [rsp+5A0h+ValueName.Buffer]
0x140013c01  mov     edx, 0C8Bh
0x140013c06  mov     r9d, eax
0x140013c09  lea     rcx, aSmpcreatedynam; "SmpCreateDynamicEnvironmentVariables"
0x140013c10  call    SmpLogFailureString
0x140013c15  jmp     loc_140013FA5
0x140013c1a  movzx   eax, word ptr [rbp+4A0h+SystemInformation]
0x140013c1e  test    eax, eax
0x140013c20  jz      short loc_140013C53
0x140013c22  cmp     eax, 5
0x140013c25  jz      short loc_140013C4D
0x140013c27  cmp     eax, 9
0x140013c2a  jz      short loc_140013C47
0x140013c2c  cmp     eax, 0Ch
0x140013c2f  jz      short loc_140013C3C
0x140013c31  lea     rcx, [rbp+4A0h+var_448]
0x140013c35  mov     eax, 10h
0x140013c3a  jmp     short loc_140013C5C
0x140013c3c  lea     rcx, [rbp+4A0h+var_480]
0x140013c40  mov     eax, 0Ch
0x140013c45  jmp     short loc_140013C5C
0x140013c47  lea     rcx, [rbp+4A0h+var_470]
0x140013c4b  jmp     short loc_140013C40
0x140013c4d  lea     rcx, [rbp+4A0h+var_490]
0x140013c51  jmp     short loc_140013C57
0x140013c53  lea     rcx, [rbp+4A0h+var_488]
0x140013c57  mov     eax, 8
0x140013c5c  mov     [rsp+5A0h+DataSize], eax; DataSize
0x140013c60  lea     rdx, [rsp+5A0h+var_550]; ValueName
0x140013c65  mov     [rsp+5A0h+Data], rcx; Data
0x140013c6a  mov     r9d, r12d; Type
0x140013c6d  mov     rcx, rsi; KeyHandle
0x140013c70  mov     [rsp+5A0h+ResultLength], eax
0x140013c74  xor     r8d, r8d; TitleIndex
0x140013c77  call    cs:__imp_NtSetValueKey
0x140013c7d  mov     ebx, eax
0x140013c7f  test    eax, eax
0x140013c81  jns     short loc_140013C92
0x140013c83  mov     r8, [rsp+5A0h+var_550.Buffer]
0x140013c88  mov     edx, 0CB6h
0x140013c8d  jmp     loc_140013C06
0x140013c92  movzx   r9d, word ptr [rbp+4A0h+SystemInformation+2]
0x140013c97  lea     r8, aU; "%u"
0x140013c9e  mov     r15d, 200h
0x140013ca4  lea     rcx, [rbp+4A0h+pszDest]; pszDest
0x140013ca8  mov     edx, r15d; cbDest
0x140013cab  call    RtlStringCbPrintfW
0x140013cb0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140013cb4  lea     rcx, [rbp+4A0h+pszDest]
0x140013cb8  mov     rax, rdi
0x140013cbb  inc     rax
0x140013cbe  cmp     [rcx+rax*2], r14w
0x140013cc3  jnz     short loc_140013CBB
0x140013cc5  lea     eax, ds:2[rax*2]
0x140013ccc  mov     r9d, r12d; Type
0x140013ccf  mov     [rsp+5A0h+DataSize], eax; DataSize
0x140013cd3  lea     rdx, [rsp+5A0h+var_540]; ValueName
0x140013cd8  lea     rax, [rbp+4A0h+pszDest]
0x140013cdc  xor     r8d, r8d; TitleIndex
0x140013cdf  mov     rcx, rsi; KeyHandle
0x140013ce2  mov     [rsp+5A0h+Data], rax; Data
0x140013ce7  call    cs:__imp_NtSetValueKey
0x140013ced  mov     ebx, eax
0x140013cef  test    eax, eax
0x140013cf1  jns     short loc_140013D02
0x140013cf3  mov     r8, [rsp+5A0h+var_540.Buffer]
0x140013cf8  mov     edx, 0CDBh
0x140013cfd  jmp     loc_140013C06
0x140013d02  lea     rax, [rsp+5A0h+var_530]
0x140013d07  mov     [rbp+4A0h+ObjectAttributes.Length], 30h ; '0'
0x140013d0e  xorps   xmm0, xmm0
0x140013d11  mov     [rbp+4A0h+ObjectAttributes.ObjectName], rax
0x140013d15  lea     r8, [rbp+4A0h+ObjectAttributes]; ObjectAttributes
0x140013d19  mov     [rbp+4A0h+ObjectAttributes.RootDirectory], r14
0x140013d1d  mov     edx, 20019h; DesiredAccess
0x140013d22  mov     [rbp+4A0h+ObjectAttributes.Attributes], 40h ; '@'
0x140013d29  lea     rcx, [rsp+5A0h+KeyHandle]; KeyHandle
0x140013d2e  movdqu  xmmword ptr [rbp+4A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140013d33  call    cs:__imp_NtOpenKey
0x140013d39  mov     ebx, eax
0x140013d3b  test    eax, eax
0x140013d3d  jns     short loc_140013D4E
0x140013d3f  mov     r8, [rsp+5A0h+var_528]
0x140013d44  mov     edx, 0CEFh
0x140013d49  jmp     loc_140013C06
0x140013d4e  mov     rcx, [rsp+5A0h+KeyHandle]; KeyHandle
0x140013d53  lea     rax, [rsp+5A0h+ResultLength]
0x140013d58  mov     qword ptr [rsp+5A0h+DataSize], rax; ResultLength
0x140013d5d  lea     r9, [rbp+4A0h+pszDest]; KeyValueInformation
0x140013d61  mov     r8d, 2; KeyValueInformationClass
0x140013d67  mov     dword ptr [rsp+5A0h+Data], r15d; Length
0x140013d6c  lea     rdx, [rbp+4A0h+var_520]; ValueName
0x140013d70  call    cs:__imp_NtQueryValueKey
0x140013d76  mov     rcx, [rsp+5A0h+KeyHandle]; KeyHandle
0x140013d7b  mov     ebx, eax
0x140013d7d  test    eax, eax
0x140013d7f  jns     short loc_140013D98
0x140013d81  call    cs:__imp_NtClose
0x140013d87  mov     r8, [rbp+4A0h+var_520.Buffer]
0x140013d8b  mov     r9d, ebx
0x140013d8e  mov     edx, 0D02h
0x140013d93  jmp     loc_140013C09
0x140013d98  lea     rax, [rsp+5A0h+ResultLength]
0x140013d9d  mov     r8d, 2; KeyValueInformationClass
0x140013da3  mov     qword ptr [rsp+5A0h+DataSize], rax; ResultLength
0x140013da8  lea     r9, [rbp+4A0h+KeyValueInformation]; KeyValueInformation
0x140013daf  lea     rdx, [rbp+4A0h+var_4F0]; ValueName
0x140013db3  mov     dword ptr [rsp+5A0h+Data], r15d; Length
0x140013db8  call    cs:__imp_NtQueryValueKey
0x140013dbe  mov     rcx, [rsp+5A0h+KeyHandle]; Handle
0x140013dc3  mov     ebx, eax
0x140013dc5  call    cs:__imp_NtClose
0x140013dcb  test    ebx, ebx
0x140013dcd  js      short loc_140013E24
0x140013dcf  lea     rcx, [rbp+4A0h+var_424]
0x140013dd3  mov     rax, rdi
0x140013dd6  inc     rax
0x140013dd9  cmp     [rcx+rax*2], r14w
0x140013dde  jnz     short loc_140013DD6
0x140013de0  add     rax, rax
0x140013de3  lea     rcx, [rbp+4A0h+var_424]
0x140013de7  mov     edx, 1F4h
0x140013dec  lea     r9, [rbp+4A0h+var_224]
0x140013df3  sub     rdx, rax; cbDest
0x140013df6  lea     r8, aWs; ", %ws"
0x140013dfd  add     rcx, rax; pszDest
0x140013e00  call    RtlStringCbPrintfW
0x140013e05  mov     ebx, eax
0x140013e07  test    eax, eax
0x140013e09  jns     short loc_140013E24
0x140013e0b  mov     r8d, eax
0x140013e0e  mov     edx, 0D2Dh
0x140013e13  lea     rcx, aSmpcreatedynam; "SmpCreateDynamicEnvironmentVariables"
0x140013e1a  call    SmpLogFailure
0x140013e1f  jmp     loc_140013FA5
0x140013e24  lea     rcx, [rbp+4A0h+var_424]
0x140013e28  mov     rax, rdi
0x140013e2b  inc     rax
0x140013e2e  cmp     [rcx+rax*2], r14w
0x140013e33  jnz     short loc_140013E2B
0x140013e35  lea     eax, ds:2[rax*2]
0x140013e3c  mov     r9d, r12d; Type
0x140013e3f  mov     [rsp+5A0h+DataSize], eax; DataSize
0x140013e43  lea     rdx, [rbp+4A0h+var_510]; ValueName
0x140013e47  lea     rax, [rbp+4A0h+var_424]
0x140013e4b  xor     r8d, r8d; TitleIndex
0x140013e4e  mov     rcx, rsi; KeyHandle
0x140013e51  mov     [rsp+5A0h+Data], rax; Data
0x140013e56  call    cs:__imp_NtSetValueKey
0x140013e5c  mov     ebx, eax
0x140013e5e  test    eax, eax
0x140013e60  jns     short loc_140013E70
0x140013e62  mov     r8, [rbp+4A0h+var_510.Buffer]
0x140013e66  mov     edx, 0D3Dh
0x140013e6b  jmp     loc_140013C06
0x140013e70  movzx   eax, word ptr [rbp+4A0h+SystemInformation]
0x140013e74  movzx   ecx, word ptr [rbp+4A0h+SystemInformation+4]
0x140013e78  test    eax, eax
0x140013e7a  jz      short loc_140013E94
0x140013e7c  cmp     eax, 5
0x140013e7f  jz      short loc_140013ECD
0x140013e81  cmp     eax, 9
0x140013e84  jz      short loc_140013ECD
0x140013e86  cmp     eax, 0Ch
0x140013e89  jz      short loc_140013ECD
0x140013e8b  lea     r8, aU; "%u"
0x140013e92  jmp     short loc_140013ED4
0x140013e94  mov     edx, 0FF00h
0x140013e99  movzx   eax, cx
0x140013e9c  and     ax, dx
0x140013e9f  cmp     ax, dx
0x140013ea2  jnz     short loc_140013ECD
0x140013ea4  movzx   r9d, byte ptr [rbp+4A0h+SystemInformation+4]
0x140013ea9  lea     r8, a02x; "%02x"
0x140013eb0  mov     rdx, r15; cbDest
0x140013eb3  lea     rcx, [rbp+4A0h+pszDest]; pszDest
0x140013eb7  call    RtlStringCbPrintfW
0x140013ebc  mov     edx, 100h; Size
0x140013ec1  lea     rcx, [rbp+4A0h+pszDest]; Str
0x140013ec5  call    cs:__imp__wcsupr_s
0x140013ecb  jmp     short loc_140013EE3
0x140013ecd  lea     r8, a04x; "%04x"
0x140013ed4  mov     r9d, ecx
0x140013ed7  mov     rdx, r15; cbDest
0x140013eda  lea     rcx, [rbp+4A0h+pszDest]; pszDest
0x140013ede  call    RtlStringCbPrintfW
0x140013ee3  lea     rax, [rbp+4A0h+pszDest]
0x140013ee7  inc     rdi
0x140013eea  cmp     [rax+rdi*2], r14w
0x140013eef  jnz     short loc_140013EE7
0x140013ef1  lea     eax, ds:2[rdi*2]
0x140013ef8  mov     r9d, r12d; Type
0x140013efb  mov     [rsp+5A0h+DataSize], eax; DataSize
0x140013eff  lea     rdx, [rbp+4A0h+var_500]; ValueName
0x140013f03  lea     rax, [rbp+4A0h+pszDest]
0x140013f07  xor     r8d, r8d; TitleIndex
0x140013f0a  mov     rcx, rsi; KeyHandle
0x140013f0d  mov     [rsp+5A0h+Data], rax; Data
0x140013f12  call    cs:__imp_NtSetValueKey
0x140013f18  mov     ebx, eax
0x140013f1a  test    eax, eax
0x140013f1c  jns     short loc_140013F2C
0x140013f1e  mov     r8, [rbp+4A0h+var_500.Buffer]
0x140013f22  mov     edx, 0D89h
0x140013f27  jmp     loc_140013C06
0x140013f2c  mov     eax, cs:SmpSafeBootOption
0x140013f32  cmp     eax, 0FFFFFFFFh
0x140013f35  jz      short loc_140013FA2
0x140013f37  mov     edx, 12h
0x140013f3c  sub     eax, r12d
0x140013f3f  jz      short loc_140013F5D
  ... truncated ...
```
