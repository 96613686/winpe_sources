# SsAddShareToRegistry

- ea: `0x180024f2c`
- end: `0x1800258e7`
- name: `SsAddShareToRegistry`
- size: `2491`
- prototype: `int __fastcall(__int64, unsigned __int16 *, void *, ULONG)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003f60`
- `0x180029884`

## callees

- `0x180012ef0`
- `0x18001deb0`
- `0x180024f2c`
- `0x1800268d8`
- `0x1800435f8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024fba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024fba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800258c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800258c1`
- `ntdll!RtlWriteRegistryValue` at `0x1800257f4`
- `ntdll!RtlWriteRegistryValue` at `0x180025876`
- `ntdll!RtlWriteRegistryValue` at `0x1800257f4`
- `ntdll!RtlWriteRegistryValue` at `0x180025876`
- `ntdll!RtlValidSecurityDescriptor` at `0x180025841`
- `ntdll!RtlValidSecurityDescriptor` at `0x180025841`
- `ntdll!RtlSetEnvironmentVariable` at `0x1800250dd`
- `ntdll!RtlSetEnvironmentVariable` at `0x180025151`
- `ntdll!RtlSetEnvironmentVariable` at `0x18002520f`
- `ntdll!RtlSetEnvironmentVariable` at `0x1800252cd`
- `ntdll!RtlSetEnvironmentVariable` at `0x18002538b`
- `ntdll!RtlSetEnvironmentVariable` at `0x180025452`
- `ntdll!RtlSetEnvironmentVariable` at `0x180025514`
- `ntdll!RtlSetEnvironmentVariable` at `0x180025586`
- `ntdll!RtlSetEnvironmentVariable` at `0x1800255f3`
- `ntdll!RtlSetEnvironmentVariable` at `0x1800256d0`
- `ntdll!RtlSetEnvironmentVariable` at `0x180025792`
- `ntdll!RtlSetEnvironmentVariable` at `0x1800250dd`
- `ntdll!RtlSetEnvironmentVariable` at `0x180025151`
- `ntdll!RtlSetEnvironmentVariable` at `0x18002520f`
- `ntdll!RtlSetEnvironmentVariable` at `0x1800252cd`
- `ntdll!RtlSetEnvironmentVariable` at `0x18002538b`
- `ntdll!RtlSetEnvironmentVariable` at `0x180025452`
- `ntdll!RtlSetEnvironmentVariable` at `0x180025514`
- `ntdll!RtlSetEnvironmentVariable` at `0x180025586`
- `ntdll!RtlSetEnvironmentVariable` at `0x1800255f3`
- `ntdll!RtlSetEnvironmentVariable` at `0x1800256d0`
- `ntdll!RtlSetEnvironmentVariable` at `0x180025792`
- `ntdll!RtlStringFromGUIDEx` at `0x180025748`
- `ntdll!RtlStringFromGUIDEx` at `0x180025748`
- `ntdll!RtlCreateEnvironment` at `0x180025057`
- `ntdll!RtlCreateEnvironment` at `0x180025057`
- `ntdll!RtlIntegerToUnicodeString` at `0x1800251c0`
- `ntdll!RtlIntegerToUnicodeString` at `0x18002527e`
- `ntdll!RtlIntegerToUnicodeString` at `0x18002533c`
- `ntdll!RtlIntegerToUnicodeString` at `0x180025403`
- `ntdll!RtlIntegerToUnicodeString` at `0x1800254c5`
- `ntdll!RtlIntegerToUnicodeString` at `0x18002566e`
- `ntdll!RtlIntegerToUnicodeString` at `0x1800251c0`
- `ntdll!RtlIntegerToUnicodeString` at `0x18002527e`
- `ntdll!RtlIntegerToUnicodeString` at `0x18002533c`
- `ntdll!RtlIntegerToUnicodeString` at `0x180025403`
- `ntdll!RtlIntegerToUnicodeString` at `0x1800254c5`
- `ntdll!RtlIntegerToUnicodeString` at `0x18002566e`
- `ntdll!RtlDestroyEnvironment` at `0x1800258b8`
- `ntdll!RtlDestroyEnvironment` at `0x1800258b8`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180025855`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180025855`
- `ntdll!RtlInitUnicodeString` at `0x1800250bd`
- `ntdll!RtlInitUnicodeString` at `0x1800250cb`
- `ntdll!RtlInitUnicodeString` at `0x180025131`
- `ntdll!RtlInitUnicodeString` at `0x18002513f`
- `ntdll!RtlInitUnicodeString` at `0x18002519f`
- `ntdll!RtlInitUnicodeString` at `0x18002525d`
- `ntdll!RtlInitUnicodeString` at `0x18002531b`
- `ntdll!RtlInitUnicodeString` at `0x1800253e2`
- `ntdll!RtlInitUnicodeString` at `0x1800254a0`
- `ntdll!RtlInitUnicodeString` at `0x180025567`
- `ntdll!RtlInitUnicodeString` at `0x180025574`
- `ntdll!RtlInitUnicodeString` at `0x1800255d4`
- `ntdll!RtlInitUnicodeString` at `0x1800255e1`
- `ntdll!RtlInitUnicodeString` at `0x18002564f`
- `ntdll!RtlInitUnicodeString` at `0x180025726`
- `ntdll!RtlInitUnicodeString` at `0x180025737`
- `ntdll!RtlInitUnicodeString` at `0x1800250bd`
- `ntdll!RtlInitUnicodeString` at `0x1800250cb`
- `ntdll!RtlInitUnicodeString` at `0x180025131`
- `ntdll!RtlInitUnicodeString` at `0x18002513f`
- `ntdll!RtlInitUnicodeString` at `0x18002519f`
- `ntdll!RtlInitUnicodeString` at `0x18002525d`
- `ntdll!RtlInitUnicodeString` at `0x18002531b`
- `ntdll!RtlInitUnicodeString` at `0x1800253e2`
- `ntdll!RtlInitUnicodeString` at `0x1800254a0`
- `ntdll!RtlInitUnicodeString` at `0x180025567`
- `ntdll!RtlInitUnicodeString` at `0x180025574`
- `ntdll!RtlInitUnicodeString` at `0x1800255d4`
- `ntdll!RtlInitUnicodeString` at `0x1800255e1`
- `ntdll!RtlInitUnicodeString` at `0x18002564f`
- `ntdll!RtlInitUnicodeString` at `0x180025726`
- `ntdll!RtlInitUnicodeString` at `0x180025737`

## string_xrefs

- `0x1800255c9`: `ShareName`

## pseudocode

```c
int __fastcall SsAddShareToRegistry(__int64 a1, unsigned __int16 *a2, void *a3, ULONG a4)
{
  __int64 v4; // r14
  unsigned __int16 *v7; // rdi
  int v9; // edx
  __int64 v10; // rcx
  __int64 v11; // rax
  WCHAR *v12; // rax
  WCHAR *v13; // rsi
  _WORD *v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // rax
  NTSTATUS v19; // eax
  _QWORD *v20; // rcx
  int v21; // edx
  ULONG v22; // ecx
  ULONG v23; // ecx
  ULONG v24; // ecx
  ULONG v25; // ecx
  ULONG v26; // ecx
  ULONG ValueLength; // eax
  PVOID ValueData; // rcx
  NTSTATUS v29; // eax
  ULONG v30; // eax
  struct _UNICODE_STRING Value; // [rsp+30h] [rbp-79h] BYREF
  PWSTR Environment; // [rsp+40h] [rbp-69h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-61h] BYREF
  _BYTE v35[80]; // [rsp+60h] [rbp-49h] BYREF

  v4 = -1;
  Environment = 0;
  v7 = a2;
  DestinationString = 0;
  Value = 0;
  if ( !a2 )
    goto LABEL_6;
  v9 = *a2 - 42;
  if ( !v9 )
    v9 = v7[1];
  if ( !v9 )
  {
    v7 = 0;
LABEL_6:
    v10 = 0;
    goto LABEL_7;
  }
  v18 = -1;
  do
    ++v18;
  while ( v7[v18] );
  v10 = 2 * v18;
LABEL_7:
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(*(_QWORD *)a1 + 2 * v11) );
  v12 = (WCHAR *)LocalAlloc(0x40u, v10 + 2 * (v11 + 2));
  v13 = v12;
  if ( !v12 )
    return (int)v12;
  v14 = *(_WORD **)a1;
  v15 = -1;
  do
    ++v15;
  while ( v14[v15] );
  memcpy_0(v12, v14, 2 * v15);
  v16 = -1;
  do
    ++v16;
  while ( *(_WORD *)(*(_QWORD *)a1 + 2 * v16) );
  if ( v7 )
  {
    v13[v16] = 45;
    v17 = -1;
    do
      ++v17;
    while ( v7[v17] );
    do
      ++v4;
    while ( *(_WORD *)(*(_QWORD *)a1 + 2 * v4) );
    memcpy_0(&v13[v4 + 1], v7, 2 * v17 + 2);
  }
  else
  {
    v13[v16] = 0;
  }
  LODWORD(v12) = RtlCreateEnvironment(0, &Environment);
  if ( (int)v12 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"Path");
    RtlInitUnicodeString(&Value, *(PCWSTR *)(a1 + 40));
    v19 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
    if ( v19 < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_138;
      }
      v21 = 14;
      goto LABEL_137;
    }
    if ( *(_QWORD *)(a1 + 16) )
    {
      RtlInitUnicodeString(&DestinationString, L"Remark");
      RtlInitUnicodeString(&Value, *(PCWSTR *)(a1 + 16));
      v19 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
      if ( v19 < 0 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_138;
        }
        v21 = 15;
        goto LABEL_137;
      }
    }
    RtlInitUnicodeString(&DestinationString, L"Type");
    v22 = *(_DWORD *)(a1 + 8);
    Value.Buffer = (PWSTR)v35;
    *(_DWORD *)&Value.Length = 4325442;
    v19 = RtlIntegerToUnicodeString(v22, 0xAu, &Value);
    if ( v19 < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_138;
      }
      v21 = 16;
      goto LABEL_137;
    }
    v19 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
    if ( v19 < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_138;
      }
      v21 = 17;
      goto LABEL_137;
    }
    RtlInitUnicodeString(&DestinationString, L"Permissions");
    v23 = *(_DWORD *)(a1 + 24);
    Value.Buffer = (PWSTR)v35;
    *(_DWORD *)&Value.Length = 4325442;
    v19 = RtlIntegerToUnicodeString(v23, 0xAu, &Value);
    if ( v19 < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_138;
      }
      v21 = 18;
      goto LABEL_137;
    }
    v19 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
    if ( v19 < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_138;
      }
      v21 = 19;
      goto LABEL_137;
    }
    RtlInitUnicodeString(&DestinationString, L"MaxUses");
    v24 = *(_DWORD *)(a1 + 28);
    Value.Buffer = (PWSTR)v35;
    *(_DWORD *)&Value.Length = 4325442;
    v19 = RtlIntegerToUnicodeString(v24, 0xAu, &Value);
    if ( v19 < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_138;
      }
      v21 = 20;
      goto LABEL_137;
    }
    v19 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
    if ( v19 < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_138;
      }
      v21 = 21;
      goto LABEL_137;
    }
    if ( *(_DWORD *)(a1 + 84) )
      a4 = *(_DWORD *)(a1 + 84);
    RtlInitUnicodeString(&DestinationString, L"CSCFlags");
    *(_DWORD *)&Value.Length = 4325442;
    Value.Buffer = (PWSTR)v35;
    v19 = RtlIntegerToUnicodeString(a4, 0xAu, &Value);
    if ( v19 < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_138;
      }
      v21 = 22;
      goto LABEL_137;
    }
    v19 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
    if ( v19 < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_138;
      }
      v21 = 23;
      goto LABEL_137;
    }
    RtlInitUnicodeString(&DestinationString, L"CATimeout");
    v25 = *(_DWORD *)(a1 + 92);
    Value.Buffer = (PWSTR)v35;
    *(_DWORD *)&Value.Length = 4325442;
    v19 = RtlIntegerToUnicodeString(v25, 0xAu, &Value);
    if ( v19 < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_138;
      }
      v21 = 24;
      goto LABEL_137;
    }
    v19 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
    if ( v19 < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_138;
      }
      v21 = 25;
      goto LABEL_137;
    }
    if ( v7 )
    {
      RtlInitUnicodeString(&DestinationString, L"ServerName");
      RtlInitUnicodeString(&Value, v7);
      v19 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
      if ( v19 < 0 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_138;
        }
        v21 = 26;
        goto LABEL_137;
      }
    }
    RtlInitUnicodeString(&DestinationString, L"ShareName");
    RtlInitUnicodeString(&Value, *(PCWSTR *)a1);
    v19 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
    if ( v19 < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_138;
      }
      v21 = 27;
      goto LABEL_137;
    }
    if ( (*(_DWORD *)(a1 + 80) & 0x100) != 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"StorQoSFlowScope");
      v26 = *(_DWORD *)(a1 + 96);
      Value.Buffer = (PWSTR)v35;
      *(_DWORD *)&Value.Length = 4325442;
      v19 = RtlIntegerToUnicodeString(v26, 0xAu, &Value);
      if ( v19 < 0 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_138;
        }
        v21 = 28;
        goto LABEL_137;
      }
      v19 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
      if ( v19 < 0 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_138;
        }
        v21 = 29;
        goto LABEL_137;
      }
    }
    if ( (*(_DWORD *)(a1 + 80) & 0x200) == 0 )
      goto LABEL_124;
    RtlInitUnicodeString(&DestinationString, L"StorQoSPolicyId");
    RtlInitUnicodeString(&Value, L"{00000000-0000-0000-0000-000000000000}");
    v19 = RtlStringFromGUIDEx(a1 + 100, &Value, 0);
    if ( v19 < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_138;
      }
      v21 = 30;
      goto LABEL_137;
    }
    v19 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
    if ( v19 < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_138;
      }
      v21 = 31;
    }
    else
    {
LABEL_124:
      ValueLength = SsRtlQueryEnvironmentLength(Environment);
      v29 = RtlWriteRegistryValue(0, &word_18005DDBC, v13, 7u, ValueData, ValueLength);
      if ( v29 < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_dS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          (unsigned int)WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids,
          v29,
          (__int64)v13);
      }
      if ( !a3 )
        goto LABEL_138;
      if ( RtlValidSecurityDescriptor(a3) )
      {
        v30 = RtlLengthSecurityDescriptor(a3);
        v19 = RtlWriteRegistryValue(0, &word_18005DFC4, v13, 3u, a3, v30);
        if ( v19 >= 0 )
        {
LABEL_138:
          RtlDestroyEnvironment(Environment);
          LODWORD(v12) = (unsigned int)LocalFree(v13);
          return (int)v12;
        }
      }
      else
      {
        v19 = -1073741703;
      }
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_138;
      }
      v21 = 33;
    }
LABEL_137:
    WPP_SF_dS(v20[2], v21, (unsigned int)WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids, v19, (__int64)v13);
    goto LABEL_138;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    LODWORD(v12) = WPP_SF_dS(
                     *((_QWORD *)WPP_GLOBAL_Control + 2),
                     13,
                     (unsigned int)WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids,
                     (_DWORD)v12,
                     (__int64)v13);
  }
  return (int)v12;
}

```

## disassembly

```asm
0x180024f2c  push    rbp
0x180024f2e  push    rbx
0x180024f2f  push    rsi
0x180024f30  push    rdi
0x180024f31  push    r12
0x180024f33  push    r13
0x180024f35  push    r14
0x180024f37  push    r15
0x180024f39  lea     rbp, [rsp-1Fh]
0x180024f3e  sub     rsp, 0C8h
0x180024f45  mov     rax, cs:__security_cookie
0x180024f4c  xor     rax, rsp
0x180024f4f  mov     [rbp+57h+var_50], rax
0x180024f53  xor     r13d, r13d
0x180024f56  or      r14, 0FFFFFFFFFFFFFFFFh
0x180024f5a  mov     [rbp+57h+Environment], r13
0x180024f5e  xorps   xmm0, xmm0
0x180024f61  xorps   xmm1, xmm1
0x180024f64  mov     r12d, r9d
0x180024f67  mov     r15, r8
0x180024f6a  mov     rdi, rdx
0x180024f6d  mov     rbx, rcx
0x180024f70  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180024f74  movups  xmmword ptr [rbp+57h+Value.Length], xmm1
0x180024f78  test    rdx, rdx
0x180024f7b  jz      short loc_180024F9A
0x180024f7d  movzx   edx, word ptr [rdx]
0x180024f80  sub     edx, 2Ah ; '*'
0x180024f83  jnz     short loc_180024F8F
0x180024f85  movzx   edx, word ptr [rdi+2]
0x180024f89  movzx   ecx, r13w
0x180024f8d  sub     edx, ecx
0x180024f8f  test    edx, edx
0x180024f91  jnz     loc_180025036
0x180024f97  mov     rdi, r13
0x180024f9a  mov     rcx, r13
0x180024f9d  mov     rdx, [rbx]
0x180024fa0  mov     rax, r14
0x180024fa3  inc     rax
0x180024fa6  cmp     [rdx+rax*2], r13w
0x180024fab  jnz     short loc_180024FA3
0x180024fad  add     rax, 2
0x180024fb1  lea     rdx, [rcx+rax*2]; uBytes
0x180024fb5  mov     ecx, 40h ; '@'; uFlags
0x180024fba  call    cs:__imp_LocalAlloc
0x180024fc0  mov     rsi, rax
0x180024fc3  test    rax, rax
0x180024fc6  jz      loc_1800258C7
0x180024fcc  mov     rdx, [rbx]; Src
0x180024fcf  mov     r8, r14
0x180024fd2  inc     r8
0x180024fd5  cmp     [rdx+r8*2], r13w
0x180024fda  jnz     short loc_180024FD2
0x180024fdc  add     r8, r8; Size
0x180024fdf  mov     rcx, rsi; void *
0x180024fe2  call    memcpy_0
0x180024fe7  mov     rax, [rbx]
0x180024fea  mov     rcx, r14
0x180024fed  inc     rcx
0x180024ff0  cmp     [rax+rcx*2], r13w
0x180024ff5  jnz     short loc_180024FED
0x180024ff7  test    rdi, rdi
0x180024ffa  jz      short loc_18002504C
0x180024ffc  mov     word ptr [rsi+rcx*2], 2Dh ; '-'
0x180025002  mov     r8, r14
0x180025005  inc     r8
0x180025008  cmp     [rdi+r8*2], r13w
0x18002500d  jnz     short loc_180025005
0x18002500f  mov     rax, [rbx]
0x180025012  inc     r14
0x180025015  cmp     [rax+r14*2], r13w
0x18002501a  jnz     short loc_180025012
0x18002501c  lea     rcx, [r14+1]
0x180025020  mov     rdx, rdi; Src
0x180025023  lea     rcx, [rsi+rcx*2]; void *
0x180025027  lea     r8, ds:2[r8*2]; Size
0x18002502f  call    memcpy_0
0x180025034  jmp     short loc_180025051
0x180025036  mov     rax, r14
0x180025039  inc     rax
0x18002503c  cmp     [rdi+rax*2], r13w
0x180025041  jnz     short loc_180025039
0x180025043  lea     rcx, [rax+rax]
0x180025047  jmp     loc_180024F9D
0x18002504c  mov     [rsi+rcx*2], r13w
0x180025051  lea     rdx, [rbp+57h+Environment]; Environment
0x180025055  xor     ecx, ecx; Inherit
0x180025057  call    cs:__imp_RtlCreateEnvironment
0x18002505d  test    eax, eax
0x18002505f  jns     short loc_1800250B2
0x180025061  mov     rcx, cs:WPP_GLOBAL_Control
0x180025068  lea     rbx, WPP_GLOBAL_Control
0x18002506f  cmp     rcx, rbx
0x180025072  jz      loc_1800258C7
0x180025078  mov     edi, 100h
0x18002507d  test    [rcx+1Ch], edi
0x180025080  jz      loc_1800258C7
0x180025086  cmp     byte ptr [rcx+19h], 1
0x18002508a  jb      loc_1800258C7
0x180025090  mov     rcx, [rcx+10h]
0x180025094  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x18002509b  mov     edx, 0Dh
0x1800250a0  mov     [rsp+100h+ValueData], rsi
0x1800250a5  mov     r9d, eax
0x1800250a8  call    WPP_SF_dS
0x1800250ad  jmp     loc_1800258C7
0x1800250b2  lea     rdx, SourceString; "Path"
0x1800250b9  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800250bd  call    cs:__imp_RtlInitUnicodeString
0x1800250c3  mov     rdx, [rbx+28h]; SourceString
0x1800250c7  lea     rcx, [rbp+57h+Value]; DestinationString
0x1800250cb  call    cs:__imp_RtlInitUnicodeString
0x1800250d1  lea     r8, [rbp+57h+Value]; Value
0x1800250d5  lea     rdx, [rbp+57h+DestinationString]; Name
0x1800250d9  lea     rcx, [rbp+57h+Environment]; Environment
0x1800250dd  call    cs:__imp_RtlSetEnvironmentVariable
0x1800250e3  test    eax, eax
0x1800250e5  jns     short loc_180025120
0x1800250e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800250ee  lea     rbx, WPP_GLOBAL_Control
0x1800250f5  cmp     rcx, rbx
0x1800250f8  jz      loc_1800258B4
0x1800250fe  mov     edi, 100h
0x180025103  test    [rcx+1Ch], edi
0x180025106  jz      loc_1800258B4
0x18002510c  cmp     byte ptr [rcx+19h], 1
0x180025110  jb      loc_1800258B4
0x180025116  mov     edx, 0Eh
0x18002511b  jmp     loc_18002589C
0x180025120  cmp     [rbx+10h], r13
0x180025124  jz      short loc_180025194
0x180025126  lea     rdx, aRemark; "Remark"
0x18002512d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180025131  call    cs:__imp_RtlInitUnicodeString
0x180025137  mov     rdx, [rbx+10h]; SourceString
0x18002513b  lea     rcx, [rbp+57h+Value]; DestinationString
0x18002513f  call    cs:__imp_RtlInitUnicodeString
0x180025145  lea     r8, [rbp+57h+Value]; Value
0x180025149  lea     rdx, [rbp+57h+DestinationString]; Name
0x18002514d  lea     rcx, [rbp+57h+Environment]; Environment
0x180025151  call    cs:__imp_RtlSetEnvironmentVariable
0x180025157  test    eax, eax
0x180025159  jns     short loc_180025194
0x18002515b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025162  lea     rbx, WPP_GLOBAL_Control
0x180025169  cmp     rcx, rbx
0x18002516c  jz      loc_1800258B4
0x180025172  mov     edi, 100h
0x180025177  test    [rcx+1Ch], edi
0x18002517a  jz      loc_1800258B4
0x180025180  cmp     byte ptr [rcx+19h], 1
0x180025184  jb      loc_1800258B4
0x18002518a  mov     edx, 0Fh
0x18002518f  jmp     loc_18002589C
0x180025194  lea     rdx, aType_0; "Type"
0x18002519b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18002519f  call    cs:__imp_RtlInitUnicodeString
0x1800251a5  mov     ecx, [rbx+8]; Value
0x1800251a8  lea     rax, [rbp+57h+var_A0]
0x1800251ac  lea     r8, [rbp+57h+Value]; String
0x1800251b0  mov     [rbp+57h+Value.Buffer], rax
0x1800251b4  mov     edx, 0Ah; Base
0x1800251b9  mov     dword ptr [rbp+57h+Value.Length], 420042h
0x1800251c0  call    cs:__imp_RtlIntegerToUnicodeString
0x1800251c6  test    eax, eax
0x1800251c8  jns     short loc_180025203
0x1800251ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800251d1  lea     rbx, WPP_GLOBAL_Control
0x1800251d8  cmp     rcx, rbx
0x1800251db  jz      loc_1800258B4
0x1800251e1  mov     edi, 100h
0x1800251e6  test    [rcx+1Ch], edi
0x1800251e9  jz      loc_1800258B4
0x1800251ef  cmp     byte ptr [rcx+19h], 1
0x1800251f3  jb      loc_1800258B4
0x1800251f9  mov     edx, 10h
0x1800251fe  jmp     loc_18002589C
0x180025203  lea     r8, [rbp+57h+Value]; Value
0x180025207  lea     rdx, [rbp+57h+DestinationString]; Name
0x18002520b  lea     rcx, [rbp+57h+Environment]; Environment
0x18002520f  call    cs:__imp_RtlSetEnvironmentVariable
0x180025215  test    eax, eax
0x180025217  jns     short loc_180025252
0x180025219  mov     rcx, cs:WPP_GLOBAL_Control
0x180025220  lea     rbx, WPP_GLOBAL_Control
0x180025227  cmp     rcx, rbx
0x18002522a  jz      loc_1800258B4
0x180025230  mov     edi, 100h
0x180025235  test    [rcx+1Ch], edi
0x180025238  jz      loc_1800258B4
0x18002523e  cmp     byte ptr [rcx+19h], 1
0x180025242  jb      loc_1800258B4
0x180025248  mov     edx, 11h
0x18002524d  jmp     loc_18002589C
0x180025252  lea     rdx, aPermissions; "Permissions"
0x180025259  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18002525d  call    cs:__imp_RtlInitUnicodeString
0x180025263  mov     ecx, [rbx+18h]; Value
0x180025266  lea     rax, [rbp+57h+var_A0]
0x18002526a  lea     r8, [rbp+57h+Value]; String
0x18002526e  mov     [rbp+57h+Value.Buffer], rax
0x180025272  mov     edx, 0Ah; Base
0x180025277  mov     dword ptr [rbp+57h+Value.Length], 420042h
0x18002527e  call    cs:__imp_RtlIntegerToUnicodeString
0x180025284  test    eax, eax
0x180025286  jns     short loc_1800252C1
0x180025288  mov     rcx, cs:WPP_GLOBAL_Control
0x18002528f  lea     rbx, WPP_GLOBAL_Control
0x180025296  cmp     rcx, rbx
0x180025299  jz      loc_1800258B4
0x18002529f  mov     edi, 100h
0x1800252a4  test    [rcx+1Ch], edi
0x1800252a7  jz      loc_1800258B4
0x1800252ad  cmp     byte ptr [rcx+19h], 1
0x1800252b1  jb      loc_1800258B4
0x1800252b7  mov     edx, 12h
0x1800252bc  jmp     loc_18002589C
0x1800252c1  lea     r8, [rbp+57h+Value]; Value
0x1800252c5  lea     rdx, [rbp+57h+DestinationString]; Name
0x1800252c9  lea     rcx, [rbp+57h+Environment]; Environment
0x1800252cd  call    cs:__imp_RtlSetEnvironmentVariable
0x1800252d3  test    eax, eax
0x1800252d5  jns     short loc_180025310
0x1800252d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800252de  lea     rbx, WPP_GLOBAL_Control
0x1800252e5  cmp     rcx, rbx
0x1800252e8  jz      loc_1800258B4
0x1800252ee  mov     edi, 100h
0x1800252f3  test    [rcx+1Ch], edi
0x1800252f6  jz      loc_1800258B4
0x1800252fc  cmp     byte ptr [rcx+19h], 1
0x180025300  jb      loc_1800258B4
0x180025306  mov     edx, 13h
0x18002530b  jmp     loc_18002589C
0x180025310  lea     rdx, aMaxuses; "MaxUses"
0x180025317  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18002531b  call    cs:__imp_RtlInitUnicodeString
0x180025321  mov     ecx, [rbx+1Ch]; Value
0x180025324  lea     rax, [rbp+57h+var_A0]
0x180025328  lea     r8, [rbp+57h+Value]; String
0x18002532c  mov     [rbp+57h+Value.Buffer], rax
0x180025330  mov     edx, 0Ah; Base
0x180025335  mov     dword ptr [rbp+57h+Value.Length], 420042h
0x18002533c  call    cs:__imp_RtlIntegerToUnicodeString
0x180025342  test    eax, eax
0x180025344  jns     short loc_18002537F
0x180025346  mov     rcx, cs:WPP_GLOBAL_Control
0x18002534d  lea     rbx, WPP_GLOBAL_Control
0x180025354  cmp     rcx, rbx
0x180025357  jz      loc_1800258B4
0x18002535d  mov     edi, 100h
0x180025362  test    [rcx+1Ch], edi
0x180025365  jz      loc_1800258B4
0x18002536b  cmp     byte ptr [rcx+19h], 1
0x18002536f  jb      loc_1800258B4
0x180025375  mov     edx, 14h
0x18002537a  jmp     loc_18002589C
0x18002537f  lea     r8, [rbp+57h+Value]; Value
0x180025383  lea     rdx, [rbp+57h+DestinationString]; Name
0x180025387  lea     rcx, [rbp+57h+Environment]; Environment
0x18002538b  call    cs:__imp_RtlSetEnvironmentVariable
0x180025391  test    eax, eax
0x180025393  jns     short loc_1800253CE
0x180025395  mov     rcx, cs:WPP_GLOBAL_Control
0x18002539c  lea     rbx, WPP_GLOBAL_Control
0x1800253a3  cmp     rcx, rbx
0x1800253a6  jz      loc_1800258B4
0x1800253ac  mov     edi, 100h
0x1800253b1  test    [rcx+1Ch], edi
0x1800253b4  jz      loc_1800258B4
0x1800253ba  cmp     byte ptr [rcx+19h], 1
0x1800253be  jb      loc_1800258B4
0x1800253c4  mov     edx, 15h
0x1800253c9  jmp     loc_18002589C
0x1800253ce  cmp     [rbx+54h], r13d
0x1800253d2  lea     rdx, aCscflags; "CSCFlags"
0x1800253d9  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800253dd  cmovnz  r12d, [rbx+54h]
0x1800253e2  call    cs:__imp_RtlInitUnicodeString
0x1800253e8  lea     rax, [rbp+57h+var_A0]
0x1800253ec  mov     dword ptr [rbp+57h+Value.Length], 420042h
0x1800253f3  lea     r8, [rbp+57h+Value]; String
0x1800253f7  mov     [rbp+57h+Value.Buffer], rax
0x1800253fb  mov     edx, 0Ah; Base
0x180025400  mov     ecx, r12d; Value
0x180025403  call    cs:__imp_RtlIntegerToUnicodeString
0x180025409  test    eax, eax
0x18002540b  jns     short loc_180025446
0x18002540d  mov     rcx, cs:WPP_GLOBAL_Control
0x180025414  lea     rbx, WPP_GLOBAL_Control
0x18002541b  cmp     rcx, rbx
0x18002541e  jz      loc_1800258B4
0x180025424  mov     edi, 100h
0x180025429  test    [rcx+1Ch], edi
0x18002542c  jz      loc_1800258B4
0x180025432  cmp     byte ptr [rcx+19h], 1
0x180025436  jb      loc_1800258B4
0x18002543c  mov     edx, 16h
0x180025441  jmp     loc_18002589C
0x180025446  lea     r8, [rbp+57h+Value]; Value
  ... truncated ...
```
