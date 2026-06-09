# SampRetrieveAccountCountsRegistry(ulong *,ulong *,ulong *)

- ea: `0x1800ad740`
- end: `0x1800ad9d8`
- name: `?SampRetrieveAccountCountsRegistry@@YAJPEAK00@Z`
- size: `664`
- prototype: `__int64 __fastcall(PULONG Type, PULONG, PULONG)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ad698`

## callees

- `0x1800213d0`
- `0x180027e24`
- `0x1800aa424`
- `0x1800ad740`

## import_xrefs

- `ntdll!NtClose` at `0x1800ad815`
- `ntdll!NtClose` at `0x1800ad8cd`
- `ntdll!NtClose` at `0x1800ad983`
- `ntdll!NtClose` at `0x1800ad815`
- `ntdll!NtClose` at `0x1800ad8cd`
- `ntdll!NtClose` at `0x1800ad983`
- `ntdll!RtlpNtQueryValueKey` at `0x1800ad809`
- `ntdll!RtlpNtQueryValueKey` at `0x1800ad8c1`
- `ntdll!RtlpNtQueryValueKey` at `0x1800ad977`
- `ntdll!RtlpNtQueryValueKey` at `0x1800ad809`
- `ntdll!RtlpNtQueryValueKey` at `0x1800ad8c1`
- `ntdll!RtlpNtQueryValueKey` at `0x1800ad977`
- `ntdll!RtlpNtOpenKey` at `0x1800ad7df`
- `ntdll!RtlpNtOpenKey` at `0x1800ad897`
- `ntdll!RtlpNtOpenKey` at `0x1800ad94d`
- `ntdll!RtlpNtOpenKey` at `0x1800ad7df`
- `ntdll!RtlpNtOpenKey` at `0x1800ad897`
- `ntdll!RtlpNtOpenKey` at `0x1800ad94d`

## pseudocode

```c
__int64 __fastcall SampRetrieveAccountCountsRegistry(PULONG Type, PULONG a2, PULONG a3)
{
  NTSTATUS v6; // ebx
  PUNICODE_STRING v7; // rcx
  __int64 v8; // rdx
  HANDLE KeyHandle; // [rsp+30h] [rbp-50h] BYREF
  ULONG v11[2]; // [rsp+38h] [rbp-48h] BYREF
  struct _UNICODE_STRING v12; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  ULONG DataLength; // [rsp+B8h] [rbp+38h] BYREF

  KeyHandle = 0;
  DataLength = 0;
  *(_QWORD *)v11 = 0;
  v12 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( (int)SampBuildDomainSubKeyName(&v12, &SampNameDomainUsers) < 0 )
    goto LABEL_23;
  ObjectAttributes.RootDirectory = SampKey;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &v12;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = RtlpNtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes, 0);
  if ( v6 >= 0 )
  {
    DataLength = 0;
    v6 = RtlpNtQueryValueKey(KeyHandle, Type, 0, &DataLength, (ULONG)v11);
    NtClose(KeyHandle);
  }
  SampFreeUnicodeString(&v12);
  if ( v6 >= 0 )
  {
LABEL_23:
    if ( (int)SampBuildDomainSubKeyName(&v12, &SampNameDomainGroups) < 0 )
      goto LABEL_13;
    ObjectAttributes.RootDirectory = SampKey;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &v12;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v6 = RtlpNtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes, 0);
    if ( v6 >= 0 )
    {
      DataLength = 0;
      v6 = RtlpNtQueryValueKey(KeyHandle, a2, 0, &DataLength, (ULONG)v11);
      NtClose(KeyHandle);
    }
    SampFreeUnicodeString(&v12);
    if ( v6 >= 0 )
    {
LABEL_13:
      v6 = SampBuildDomainSubKeyName(&v12, &SampNameDomainAliases);
      if ( v6 >= 0 )
      {
        ObjectAttributes.RootDirectory = SampKey;
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &v12;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v6 = RtlpNtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes, 0);
        if ( v6 >= 0 )
        {
          DataLength = 0;
          v6 = RtlpNtQueryValueKey(KeyHandle, a3, 0, &DataLength, (ULONG)v11);
          NtClose(KeyHandle);
        }
        SampFreeUnicodeString(&v12);
      }
      v7 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        v8 = 95;
        goto LABEL_19;
      }
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        v8 = 94;
        goto LABEL_19;
      }
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v8 = 93;
LABEL_19:
      WPP_SF_Dd(v7[3].Buffer, v8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, (unsigned int)v6, v6);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800ad740  mov     [rsp-18h+arg_0], rbx
0x1800ad745  mov     [rsp-18h+arg_8], rsi
0x1800ad74a  push    rbp
0x1800ad74b  push    rdi
0x1800ad74c  push    r14
0x1800ad74e  mov     rbp, rsp
0x1800ad751  sub     rsp, 80h
0x1800ad758  xorps   xmm1, xmm1
0x1800ad75b  mov     [rbp+KeyHandle], 0
0x1800ad763  mov     rsi, rdx
0x1800ad766  mov     [rbp+DataLength], 0
0x1800ad76d  mov     rdi, rcx
0x1800ad770  mov     qword ptr [rbp+var_48], 0
0x1800ad778  xorps   xmm0, xmm0
0x1800ad77b  lea     rdx, ?SampNameDomainUsers@@3U_UNICODE_STRING@@A; struct _UNICODE_STRING *
0x1800ad782  lea     rcx, [rbp+var_40]; struct _UNICODE_STRING *
0x1800ad786  mov     r14, r8
0x1800ad789  movups  xmmword ptr [rbp+var_40.Length], xmm0
0x1800ad78d  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x1800ad791  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x1800ad795  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x1800ad799  call    ?SampBuildDomainSubKeyName@@YAJPEAU_UNICODE_STRING@@0@Z; SampBuildDomainSubKeyName(_UNICODE_STRING *,_UNICODE_STRING *)
0x1800ad79e  test    eax, eax
0x1800ad7a0  js      loc_1800AD846
0x1800ad7a6  mov     rax, cs:SampKey
0x1800ad7ad  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800ad7b1  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x1800ad7b5  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1800ad7b9  lea     rax, [rbp+var_40]
0x1800ad7bd  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800ad7c4  xorps   xmm0, xmm0
0x1800ad7c7  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800ad7cb  xor     r9d, r9d; Unused
0x1800ad7ce  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800ad7d5  mov     edx, 20019h; DesiredAccess
0x1800ad7da  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800ad7df  call    cs:__imp_RtlpNtOpenKey
0x1800ad7e5  mov     ebx, eax
0x1800ad7e7  test    eax, eax
0x1800ad7e9  js      short loc_1800AD81B
0x1800ad7eb  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1800ad7ef  lea     rax, [rbp+var_48]
0x1800ad7f3  lea     r9, [rbp+DataLength]; DataLength
0x1800ad7f7  mov     qword ptr [rsp+80h+Unused], rax; Unused
0x1800ad7fc  xor     r8d, r8d; Data
0x1800ad7ff  mov     [rbp+DataLength], 0
0x1800ad806  mov     rdx, rdi; Type
0x1800ad809  call    cs:__imp_RtlpNtQueryValueKey
0x1800ad80f  mov     rcx, [rbp+KeyHandle]; Handle
0x1800ad813  mov     ebx, eax
0x1800ad815  call    cs:__imp_NtClose
0x1800ad81b  lea     rcx, [rbp+var_40]
0x1800ad81f  call    SampFreeUnicodeString
0x1800ad824  test    ebx, ebx
0x1800ad826  jns     short loc_1800AD846
0x1800ad828  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad82f  test    dword ptr [rcx+44h], 20000h
0x1800ad836  jz      loc_1800AD9BE
0x1800ad83c  mov     edx, 5Dh ; ']'
0x1800ad841  jmp     loc_1800AD9A7
0x1800ad846  lea     rdx, ?SampNameDomainGroups@@3U_UNICODE_STRING@@A; struct _UNICODE_STRING *
0x1800ad84d  lea     rcx, [rbp+var_40]; struct _UNICODE_STRING *
0x1800ad851  call    ?SampBuildDomainSubKeyName@@YAJPEAU_UNICODE_STRING@@0@Z; SampBuildDomainSubKeyName(_UNICODE_STRING *,_UNICODE_STRING *)
0x1800ad856  test    eax, eax
0x1800ad858  js      loc_1800AD8FE
0x1800ad85e  mov     rax, cs:SampKey
0x1800ad865  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800ad869  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x1800ad86d  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1800ad871  lea     rax, [rbp+var_40]
0x1800ad875  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800ad87c  xorps   xmm0, xmm0
0x1800ad87f  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800ad883  xor     r9d, r9d; Unused
0x1800ad886  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800ad88d  mov     edx, 20019h; DesiredAccess
0x1800ad892  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800ad897  call    cs:__imp_RtlpNtOpenKey
0x1800ad89d  mov     ebx, eax
0x1800ad89f  test    eax, eax
0x1800ad8a1  js      short loc_1800AD8D3
0x1800ad8a3  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1800ad8a7  lea     rax, [rbp+var_48]
0x1800ad8ab  lea     r9, [rbp+DataLength]; DataLength
0x1800ad8af  mov     qword ptr [rsp+80h+Unused], rax; Unused
0x1800ad8b4  xor     r8d, r8d; Data
0x1800ad8b7  mov     [rbp+DataLength], 0
0x1800ad8be  mov     rdx, rsi; Type
0x1800ad8c1  call    cs:__imp_RtlpNtQueryValueKey
0x1800ad8c7  mov     rcx, [rbp+KeyHandle]; Handle
0x1800ad8cb  mov     ebx, eax
0x1800ad8cd  call    cs:__imp_NtClose
0x1800ad8d3  lea     rcx, [rbp+var_40]
0x1800ad8d7  call    SampFreeUnicodeString
0x1800ad8dc  test    ebx, ebx
0x1800ad8de  jns     short loc_1800AD8FE
0x1800ad8e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad8e7  test    dword ptr [rcx+44h], 20000h
0x1800ad8ee  jz      loc_1800AD9BE
0x1800ad8f4  mov     edx, 5Eh ; '^'
0x1800ad8f9  jmp     loc_1800AD9A7
0x1800ad8fe  lea     rdx, ?SampNameDomainAliases@@3U_UNICODE_STRING@@A; struct _UNICODE_STRING *
0x1800ad905  lea     rcx, [rbp+var_40]; struct _UNICODE_STRING *
0x1800ad909  call    ?SampBuildDomainSubKeyName@@YAJPEAU_UNICODE_STRING@@0@Z; SampBuildDomainSubKeyName(_UNICODE_STRING *,_UNICODE_STRING *)
0x1800ad90e  mov     ebx, eax
0x1800ad910  test    eax, eax
0x1800ad912  js      short loc_1800AD992
0x1800ad914  mov     rax, cs:SampKey
0x1800ad91b  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800ad91f  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x1800ad923  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1800ad927  lea     rax, [rbp+var_40]
0x1800ad92b  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800ad932  xorps   xmm0, xmm0
0x1800ad935  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800ad939  xor     r9d, r9d; Unused
0x1800ad93c  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800ad943  mov     edx, 20019h; DesiredAccess
0x1800ad948  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800ad94d  call    cs:__imp_RtlpNtOpenKey
0x1800ad953  mov     ebx, eax
0x1800ad955  test    eax, eax
0x1800ad957  js      short loc_1800AD989
0x1800ad959  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1800ad95d  lea     rax, [rbp+var_48]
0x1800ad961  lea     r9, [rbp+DataLength]; DataLength
0x1800ad965  mov     qword ptr [rsp+80h+Unused], rax; Unused
0x1800ad96a  xor     r8d, r8d; Data
0x1800ad96d  mov     [rbp+DataLength], 0
0x1800ad974  mov     rdx, r14; Type
0x1800ad977  call    cs:__imp_RtlpNtQueryValueKey
0x1800ad97d  mov     rcx, [rbp+KeyHandle]; Handle
0x1800ad981  mov     ebx, eax
0x1800ad983  call    cs:__imp_NtClose
0x1800ad989  lea     rcx, [rbp+var_40]
0x1800ad98d  call    SampFreeUnicodeString
0x1800ad992  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad999  test    dword ptr [rcx+44h], 20000h
0x1800ad9a0  jz      short loc_1800AD9BE
0x1800ad9a2  mov     edx, 5Fh ; '_'
0x1800ad9a7  mov     rcx, [rcx+38h]
0x1800ad9ab  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x1800ad9b2  mov     r9d, ebx
0x1800ad9b5  mov     [rsp+80h+Unused], ebx
0x1800ad9b9  call    WPP_SF_Dd
0x1800ad9be  lea     r11, [rsp+80h+var_s0]
0x1800ad9c6  mov     eax, ebx
0x1800ad9c8  mov     rbx, [r11+20h]
0x1800ad9cc  mov     rsi, [r11+28h]
0x1800ad9d0  mov     rsp, r11
0x1800ad9d3  pop     r14
0x1800ad9d5  pop     rdi
0x1800ad9d6  pop     rbp
0x1800ad9d7  retn
```
