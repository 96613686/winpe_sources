# WsAddCertMappingToRegistry

- ea: `0x180025164`
- end: `0x180025b2f`
- name: `WsAddCertMappingToRegistry`
- size: `2507`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022510`
- `0x180023930`
- `0x180026c7c`

## callees

- `0x180009010`
- `0x180009090`
- `0x18001dcac`
- `0x18001fbd0`
- `0x180024550`
- `0x1800245ec`
- `0x180025164`
- `0x180035eb0`

## import_xrefs

- `ntdll!RtlDestroyEnvironment` at `0x180025af1`
- `ntdll!RtlDestroyEnvironment` at `0x180025af1`
- `ntdll!RtlIntegerToUnicodeString` at `0x18002578c`
- `ntdll!RtlIntegerToUnicodeString` at `0x18002585f`
- `ntdll!RtlIntegerToUnicodeString` at `0x18002578c`
- `ntdll!RtlIntegerToUnicodeString` at `0x18002585f`
- `ntdll!RtlCreateEnvironment` at `0x180025208`
- `ntdll!RtlCreateEnvironment` at `0x180025208`
- `ntdll!RtlNtStatusToDosError` at `0x180025aff`
- `ntdll!RtlNtStatusToDosError` at `0x180025aff`
- `ntdll!RtlSetEnvironmentVariable` at `0x18002529b`
- `ntdll!RtlSetEnvironmentVariable` at `0x18002537a`
- `ntdll!RtlSetEnvironmentVariable` at `0x1800253fd`
- `ntdll!RtlSetEnvironmentVariable` at `0x180025480`
- `ntdll!RtlSetEnvironmentVariable` at `0x180025503`
- `ntdll!RtlSetEnvironmentVariable` at `0x180025586`
- `ntdll!RtlSetEnvironmentVariable` at `0x180025609`
- `ntdll!RtlSetEnvironmentVariable` at `0x18002568c`
- `ntdll!RtlSetEnvironmentVariable` at `0x18002570f`
- `ntdll!RtlSetEnvironmentVariable` at `0x1800257e2`
- `ntdll!RtlSetEnvironmentVariable` at `0x1800258b5`
- `ntdll!RtlSetEnvironmentVariable` at `0x18002529b`
- `ntdll!RtlSetEnvironmentVariable` at `0x18002537a`
- `ntdll!RtlSetEnvironmentVariable` at `0x1800253fd`
- `ntdll!RtlSetEnvironmentVariable` at `0x180025480`
- `ntdll!RtlSetEnvironmentVariable` at `0x180025503`
- `ntdll!RtlSetEnvironmentVariable` at `0x180025586`
- `ntdll!RtlSetEnvironmentVariable` at `0x180025609`
- `ntdll!RtlSetEnvironmentVariable` at `0x18002568c`
- `ntdll!RtlSetEnvironmentVariable` at `0x18002570f`
- `ntdll!RtlSetEnvironmentVariable` at `0x1800257e2`
- `ntdll!RtlSetEnvironmentVariable` at `0x1800258b5`
- `ntdll!RtlInitUnicodeString` at `0x18002526c`
- `ntdll!RtlInitUnicodeString` at `0x180025280`
- `ntdll!RtlInitUnicodeString` at `0x18002534a`
- `ntdll!RtlInitUnicodeString` at `0x18002535f`
- `ntdll!RtlInitUnicodeString` at `0x1800253cd`
- `ntdll!RtlInitUnicodeString` at `0x1800253e2`
- `ntdll!RtlInitUnicodeString` at `0x180025450`
- `ntdll!RtlInitUnicodeString` at `0x180025465`
- `ntdll!RtlInitUnicodeString` at `0x1800254d3`
- `ntdll!RtlInitUnicodeString` at `0x1800254e8`
- `ntdll!RtlInitUnicodeString` at `0x180025556`
- `ntdll!RtlInitUnicodeString` at `0x18002556b`
- `ntdll!RtlInitUnicodeString` at `0x1800255d9`
- `ntdll!RtlInitUnicodeString` at `0x1800255ee`
- `ntdll!RtlInitUnicodeString` at `0x18002565c`
- `ntdll!RtlInitUnicodeString` at `0x180025671`
- `ntdll!RtlInitUnicodeString` at `0x1800256df`
- `ntdll!RtlInitUnicodeString` at `0x1800256f4`
- `ntdll!RtlInitUnicodeString` at `0x180025762`
- `ntdll!RtlInitUnicodeString` at `0x180025835`
- `ntdll!RtlInitUnicodeString` at `0x18002526c`
- `ntdll!RtlInitUnicodeString` at `0x180025280`
- `ntdll!RtlInitUnicodeString` at `0x18002534a`
- `ntdll!RtlInitUnicodeString` at `0x18002535f`
- `ntdll!RtlInitUnicodeString` at `0x1800253cd`
- `ntdll!RtlInitUnicodeString` at `0x1800253e2`
- `ntdll!RtlInitUnicodeString` at `0x180025450`
- `ntdll!RtlInitUnicodeString` at `0x180025465`
- `ntdll!RtlInitUnicodeString` at `0x1800254d3`
- `ntdll!RtlInitUnicodeString` at `0x1800254e8`
- `ntdll!RtlInitUnicodeString` at `0x180025556`
- `ntdll!RtlInitUnicodeString` at `0x18002556b`
- `ntdll!RtlInitUnicodeString` at `0x1800255d9`
- `ntdll!RtlInitUnicodeString` at `0x1800255ee`
- `ntdll!RtlInitUnicodeString` at `0x18002565c`
- `ntdll!RtlInitUnicodeString` at `0x180025671`
- `ntdll!RtlInitUnicodeString` at `0x1800256df`
- `ntdll!RtlInitUnicodeString` at `0x1800256f4`
- `ntdll!RtlInitUnicodeString` at `0x180025762`
- `ntdll!RtlInitUnicodeString` at `0x180025835`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180025998`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180025998`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180025a25`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180025a25`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025a88`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025a88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025adb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025adb`

## string_xrefs

- `0x1800256d3`: `StoreName`
- `0x180025925`: `WsAddCertMappingToRegistry`
- `0x1800259ed`: `WsAddCertMappingToRegistry`

## pseudocode

```c
ULONG __fastcall WsAddCertMappingToRegistry(__int64 a1, const WCHAR *a2, unsigned int a3)
{
  NTSTATUS v6; // edi
  NTSTATUS v7; // eax
  int v8; // r8d
  _QWORD *v9; // rcx
  int v10; // edx
  ULONG v11; // ecx
  ULONG v12; // ecx
  PWSTR v13; // rbx
  int v14; // ebx
  unsigned int v15; // eax
  __int64 v16; // rcx
  unsigned int v17; // eax
  unsigned int v18; // edi
  unsigned int v19; // eax
  LSTATUS v20; // eax
  int v21; // r8d
  unsigned int v22; // edi
  PWSTR Environment; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING Value; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwDisposition; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+88h] [rbp-78h] BYREF
  char v30; // [rsp+A0h] [rbp-60h] BYREF
  char v31; // [rsp+F0h] [rbp-10h] BYREF

  hKey = 0;
  Environment = 0;
  dwDisposition = 0;
  DestinationString = 0;
  Value = 0;
  memset(&SecurityAttributes, 0, 20);
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids, 0);
    }
    v6 = -1073741811;
    goto LABEL_111;
  }
  v7 = RtlCreateEnvironment(0, &Environment);
  v6 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_111;
    }
    v10 = 23;
    goto LABEL_12;
  }
  RtlInitUnicodeString(&DestinationString, L"ServerName");
  RtlInitUnicodeString(&Value, a2);
  v7 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
  v6 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_111;
    }
    v10 = 24;
    goto LABEL_12;
  }
  if ( a3 )
  {
    v6 = -1073741637;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids, a3);
    }
    goto LABEL_111;
  }
  if ( *(_QWORD *)(a1 + 8) )
  {
    RtlInitUnicodeString(&DestinationString, L"Subject");
    RtlInitUnicodeString(&Value, *(PCWSTR *)(a1 + 8));
    v7 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
    v6 = v7;
    if ( v7 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_111;
      }
      v10 = 26;
      goto LABEL_12;
    }
  }
  RtlInitUnicodeString(&DestinationString, L"Issuer");
  RtlInitUnicodeString(&Value, *(PCWSTR *)(a1 + 16));
  v7 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
  v6 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_111;
    }
    v10 = 27;
    goto LABEL_12;
  }
  RtlInitUnicodeString(&DestinationString, L"ThumbPrint");
  RtlInitUnicodeString(&Value, *(PCWSTR *)(a1 + 24));
  v7 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
  v6 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_111;
    }
    v10 = 28;
    goto LABEL_12;
  }
  RtlInitUnicodeString(&DestinationString, L"FriendlyName");
  RtlInitUnicodeString(&Value, *(PCWSTR *)(a1 + 32));
  v7 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
  v6 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_111;
    }
    v10 = 29;
    goto LABEL_12;
  }
  RtlInitUnicodeString(&DestinationString, L"NotBefore");
  RtlInitUnicodeString(&Value, *(PCWSTR *)(a1 + 40));
  v7 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
  v6 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_111;
    }
    v10 = 30;
    goto LABEL_12;
  }
  RtlInitUnicodeString(&DestinationString, L"NotAfter");
  RtlInitUnicodeString(&Value, *(PCWSTR *)(a1 + 48));
  v7 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
  v6 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_111;
    }
    v10 = 31;
    goto LABEL_12;
  }
  RtlInitUnicodeString(&DestinationString, L"StoreLocation");
  RtlInitUnicodeString(&Value, *(PCWSTR *)(a1 + 56));
  v7 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
  v6 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_111;
    }
    v10 = 32;
    goto LABEL_12;
  }
  RtlInitUnicodeString(&DestinationString, L"StoreName");
  RtlInitUnicodeString(&Value, *(PCWSTR *)(a1 + 64));
  v7 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
  v6 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_111;
    }
    v10 = 33;
    goto LABEL_12;
  }
  RtlInitUnicodeString(&DestinationString, L"Type");
  v11 = *(_DWORD *)(a1 + 80);
  Value.Buffer = (PWSTR)&v30;
  *(_DWORD *)&Value.Length = 4325442;
  v7 = RtlIntegerToUnicodeString(v11, 0xAu, &Value);
  v6 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_111;
    }
    v10 = 34;
    goto LABEL_12;
  }
  v7 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
  v6 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_111;
    }
    v10 = 35;
    goto LABEL_12;
  }
  RtlInitUnicodeString(&DestinationString, L"Flags");
  v12 = *(_DWORD *)(a1 + 84);
  Value.Buffer = (PWSTR)&v31;
  *(_DWORD *)&Value.Length = 4325442;
  v7 = RtlIntegerToUnicodeString(v12, 0xAu, &Value);
  v6 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_111;
    }
    v10 = 36;
    goto LABEL_12;
  }
  v7 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
  v6 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_111;
    }
    v10 = 37;
LABEL_12:
    WPP_SF_LS(v9[2], v10, v8, v7, (__int64)a2);
    goto LABEL_111;
  }
  v13 = Environment;
  if ( *Environment )
  {
    while ( *v13 || *++v13 )
      ++v13;
  }
  v14 = (_DWORD)v13 - (_DWORD)Environment;
  v15 = WsImpersonateClient2("WsAddCertMappingToRegistry", 1131);
  if ( v15 )
  {
    v16 = v15;
    goto LABEL_91;
  }
  SecurityAttributes.lpSecurityDescriptor = pSecurityDescriptor;
  SecurityAttributes.nLength = 24;
  SecurityAttributes.bInheritHandle = 0;
  v17 = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          &word_1800519AC,
          0,
          0,
          0,
          0xE0002u,
          &SecurityAttributes,
          &hKey,
          &dwDisposition);
  v18 = v17;
  if ( !v17 )
  {
    if ( dwDisposition == 2 )
    {
      v19 = RegSetKeySecurity(hKey, 7u, pSecurityDescriptor);
      if ( v19 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids, v19);
        }
      }
    }
    WsRevertToSelf2(0, 0);
    v20 = RegSetValueExW(hKey, a2, 0, 7u, (const BYTE *)Environment, v14 + 2);
    v22 = v20;
    if ( !v20 )
    {
      v6 = 0;
      goto LABEL_111;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, v21, v20, (__int64)a2);
    }
    v16 = v22;
LABEL_91:
    v6 = NetpApiStatusToNtStatus(v16);
    goto LABEL_111;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids, v17);
  }
  v6 = NetpApiStatusToNtStatus(v18);
  WsRevertToSelf2("WsAddCertMappingToRegistry", 1219);
LABEL_111:
  if ( hKey )
    RegCloseKey(hKey);
  if ( Environment )
    RtlDestroyEnvironment(Environment);
  return RtlNtStatusToDosError(v6);
}

```

## disassembly

```asm
0x180025164  mov     [rsp-8+arg_18], rbx
0x180025169  push    rbp
0x18002516a  push    rsi
0x18002516b  push    rdi
0x18002516c  push    r14
0x18002516e  push    r15
0x180025170  lea     rbp, [rsp-50h]
0x180025175  sub     rsp, 150h
0x18002517c  mov     rax, cs:__security_cookie
0x180025183  xor     rax, rsp
0x180025186  mov     [rbp+70h+var_30], rax
0x18002518a  xor     r15d, r15d
0x18002518d  xor     eax, eax
0x18002518f  mov     [rbp+70h+hKey], r15
0x180025193  xorps   xmm0, xmm0
0x180025196  mov     [rsp+170h+Environment], r15
0x18002519b  xorps   xmm1, xmm1
0x18002519e  mov     [rsp+170h+dwDisposition], r15d
0x1800251a3  mov     r14d, r8d
0x1800251a6  mov     [rbp+70h+SecurityAttributes.bInheritHandle], eax
0x1800251a9  mov     rsi, rdx
0x1800251ac  mov     rbx, rcx
0x1800251af  movups  xmmword ptr [rsp+170h+DestinationString.Length], xmm0
0x1800251b4  movups  xmmword ptr [rsp+170h+Value.Length], xmm1
0x1800251b9  movups  xmmword ptr [rbp+70h+SecurityAttributes.nLength], xmm0
0x1800251bd  test    rdx, rdx
0x1800251c0  jnz     short loc_180025201
0x1800251c2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800251c9  lea     rbx, WPP_GLOBAL_Control
0x1800251d0  cmp     rcx, rbx
0x1800251d3  jz      short loc_1800251F7
0x1800251d5  test    byte ptr [rcx+1Ch], 2
0x1800251d9  jz      short loc_1800251F7
0x1800251db  cmp     byte ptr [rcx+19h], 1
0x1800251df  jb      short loc_1800251F7
0x1800251e1  mov     rcx, [rcx+10h]
0x1800251e5  lea     edx, [rsi+16h]
0x1800251e8  xor     r9d, r9d
0x1800251eb  lea     r8, WPP_abf29b036dd53d344014067ca7a3b351_Traceguids
0x1800251f2  call    WPP_SF_S
0x1800251f7  mov     edi, 0C000000Dh
0x1800251fc  jmp     loc_180025AD2
0x180025201  lea     rdx, [rsp+170h+Environment]; Environment
0x180025206  xor     ecx, ecx; Inherit
0x180025208  call    cs:__imp_RtlCreateEnvironment
0x18002520f  nop     dword ptr [rax+rax+00h]
0x180025214  mov     edi, eax
0x180025216  test    eax, eax
0x180025218  jns     short loc_180025260
0x18002521a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180025221  lea     rbx, WPP_GLOBAL_Control
0x180025228  cmp     rcx, rbx
0x18002522b  jz      loc_180025AD2
0x180025231  test    byte ptr [rcx+1Ch], 2
0x180025235  jz      loc_180025AD2
0x18002523b  cmp     byte ptr [rcx+19h], 1
0x18002523f  jb      loc_180025AD2
0x180025245  mov     edx, 17h
0x18002524a  mov     rcx, [rcx+10h]
0x18002524e  mov     r9d, eax
0x180025251  mov     qword ptr [rsp+170h+dwOptions], rsi
0x180025256  call    WPP_SF_LS
0x18002525b  jmp     loc_180025AD2
0x180025260  lea     rdx, aServername; "ServerName"
0x180025267  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x18002526c  call    cs:__imp_RtlInitUnicodeString
0x180025273  nop     dword ptr [rax+rax+00h]
0x180025278  mov     rdx, rsi; SourceString
0x18002527b  lea     rcx, [rsp+170h+Value]; DestinationString
0x180025280  call    cs:__imp_RtlInitUnicodeString
0x180025287  nop     dword ptr [rax+rax+00h]
0x18002528c  lea     r8, [rsp+170h+Value]; Value
0x180025291  lea     rdx, [rsp+170h+DestinationString]; Name
0x180025296  lea     rcx, [rsp+170h+Environment]; Environment
0x18002529b  call    cs:__imp_RtlSetEnvironmentVariable
0x1800252a2  nop     dword ptr [rax+rax+00h]
0x1800252a7  mov     edi, eax
0x1800252a9  test    eax, eax
0x1800252ab  jns     short loc_1800252E2
0x1800252ad  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800252b4  lea     rbx, WPP_GLOBAL_Control
0x1800252bb  cmp     rcx, rbx
0x1800252be  jz      loc_180025AD2
0x1800252c4  test    byte ptr [rcx+1Ch], 2
0x1800252c8  jz      loc_180025AD2
0x1800252ce  cmp     byte ptr [rcx+19h], 1
0x1800252d2  jb      loc_180025AD2
0x1800252d8  mov     edx, 18h
0x1800252dd  jmp     loc_18002524A
0x1800252e2  test    r14d, r14d
0x1800252e5  jz      short loc_180025334
0x1800252e7  mov     edi, 0C00000BBh
0x1800252ec  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800252f3  lea     rbx, WPP_GLOBAL_Control
0x1800252fa  cmp     rcx, rbx
0x1800252fd  jz      loc_180025AD2
0x180025303  test    byte ptr [rcx+1Ch], 2
0x180025307  jz      loc_180025AD2
0x18002530d  cmp     byte ptr [rcx+19h], 1
0x180025311  jb      loc_180025AD2
0x180025317  mov     rcx, [rcx+10h]
0x18002531b  lea     r8, WPP_abf29b036dd53d344014067ca7a3b351_Traceguids
0x180025322  mov     edx, 19h
0x180025327  mov     r9d, r14d
0x18002532a  call    WPP_SF_d
0x18002532f  jmp     loc_180025AD2
0x180025334  cmp     [rbx+8], r15
0x180025338  jz      loc_1800253C1
0x18002533e  lea     rdx, aSubject; "Subject"
0x180025345  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x18002534a  call    cs:__imp_RtlInitUnicodeString
0x180025351  nop     dword ptr [rax+rax+00h]
0x180025356  mov     rdx, [rbx+8]; SourceString
0x18002535a  lea     rcx, [rsp+170h+Value]; DestinationString
0x18002535f  call    cs:__imp_RtlInitUnicodeString
0x180025366  nop     dword ptr [rax+rax+00h]
0x18002536b  lea     r8, [rsp+170h+Value]; Value
0x180025370  lea     rdx, [rsp+170h+DestinationString]; Name
0x180025375  lea     rcx, [rsp+170h+Environment]; Environment
0x18002537a  call    cs:__imp_RtlSetEnvironmentVariable
0x180025381  nop     dword ptr [rax+rax+00h]
0x180025386  mov     edi, eax
0x180025388  test    eax, eax
0x18002538a  jns     short loc_1800253C1
0x18002538c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180025393  lea     rbx, WPP_GLOBAL_Control
0x18002539a  cmp     rcx, rbx
0x18002539d  jz      loc_180025AD2
0x1800253a3  test    byte ptr [rcx+1Ch], 2
0x1800253a7  jz      loc_180025AD2
0x1800253ad  cmp     byte ptr [rcx+19h], 1
0x1800253b1  jb      loc_180025AD2
0x1800253b7  mov     edx, 1Ah
0x1800253bc  jmp     loc_18002524A
0x1800253c1  lea     rdx, aIssuer; "Issuer"
0x1800253c8  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x1800253cd  call    cs:__imp_RtlInitUnicodeString
0x1800253d4  nop     dword ptr [rax+rax+00h]
0x1800253d9  mov     rdx, [rbx+10h]; SourceString
0x1800253dd  lea     rcx, [rsp+170h+Value]; DestinationString
0x1800253e2  call    cs:__imp_RtlInitUnicodeString
0x1800253e9  nop     dword ptr [rax+rax+00h]
0x1800253ee  lea     r8, [rsp+170h+Value]; Value
0x1800253f3  lea     rdx, [rsp+170h+DestinationString]; Name
0x1800253f8  lea     rcx, [rsp+170h+Environment]; Environment
0x1800253fd  call    cs:__imp_RtlSetEnvironmentVariable
0x180025404  nop     dword ptr [rax+rax+00h]
0x180025409  mov     edi, eax
0x18002540b  test    eax, eax
0x18002540d  jns     short loc_180025444
0x18002540f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180025416  lea     rbx, WPP_GLOBAL_Control
0x18002541d  cmp     rcx, rbx
0x180025420  jz      loc_180025AD2
0x180025426  test    byte ptr [rcx+1Ch], 2
0x18002542a  jz      loc_180025AD2
0x180025430  cmp     byte ptr [rcx+19h], 1
0x180025434  jb      loc_180025AD2
0x18002543a  mov     edx, 1Bh
0x18002543f  jmp     loc_18002524A
0x180025444  lea     rdx, aThumbprint; "ThumbPrint"
0x18002544b  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x180025450  call    cs:__imp_RtlInitUnicodeString
0x180025457  nop     dword ptr [rax+rax+00h]
0x18002545c  mov     rdx, [rbx+18h]; SourceString
0x180025460  lea     rcx, [rsp+170h+Value]; DestinationString
0x180025465  call    cs:__imp_RtlInitUnicodeString
0x18002546c  nop     dword ptr [rax+rax+00h]
0x180025471  lea     r8, [rsp+170h+Value]; Value
0x180025476  lea     rdx, [rsp+170h+DestinationString]; Name
0x18002547b  lea     rcx, [rsp+170h+Environment]; Environment
0x180025480  call    cs:__imp_RtlSetEnvironmentVariable
0x180025487  nop     dword ptr [rax+rax+00h]
0x18002548c  mov     edi, eax
0x18002548e  test    eax, eax
0x180025490  jns     short loc_1800254C7
0x180025492  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180025499  lea     rbx, WPP_GLOBAL_Control
0x1800254a0  cmp     rcx, rbx
0x1800254a3  jz      loc_180025AD2
0x1800254a9  test    byte ptr [rcx+1Ch], 2
0x1800254ad  jz      loc_180025AD2
0x1800254b3  cmp     byte ptr [rcx+19h], 1
0x1800254b7  jb      loc_180025AD2
0x1800254bd  mov     edx, 1Ch
0x1800254c2  jmp     loc_18002524A
0x1800254c7  lea     rdx, aFriendlyname; "FriendlyName"
0x1800254ce  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x1800254d3  call    cs:__imp_RtlInitUnicodeString
0x1800254da  nop     dword ptr [rax+rax+00h]
0x1800254df  mov     rdx, [rbx+20h]; SourceString
0x1800254e3  lea     rcx, [rsp+170h+Value]; DestinationString
0x1800254e8  call    cs:__imp_RtlInitUnicodeString
0x1800254ef  nop     dword ptr [rax+rax+00h]
0x1800254f4  lea     r8, [rsp+170h+Value]; Value
0x1800254f9  lea     rdx, [rsp+170h+DestinationString]; Name
0x1800254fe  lea     rcx, [rsp+170h+Environment]; Environment
0x180025503  call    cs:__imp_RtlSetEnvironmentVariable
0x18002550a  nop     dword ptr [rax+rax+00h]
0x18002550f  mov     edi, eax
0x180025511  test    eax, eax
0x180025513  jns     short loc_18002554A
0x180025515  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002551c  lea     rbx, WPP_GLOBAL_Control
0x180025523  cmp     rcx, rbx
0x180025526  jz      loc_180025AD2
0x18002552c  test    byte ptr [rcx+1Ch], 2
0x180025530  jz      loc_180025AD2
0x180025536  cmp     byte ptr [rcx+19h], 1
0x18002553a  jb      loc_180025AD2
0x180025540  mov     edx, 1Dh
0x180025545  jmp     loc_18002524A
0x18002554a  lea     rdx, aNotbefore; "NotBefore"
0x180025551  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x180025556  call    cs:__imp_RtlInitUnicodeString
0x18002555d  nop     dword ptr [rax+rax+00h]
0x180025562  mov     rdx, [rbx+28h]; SourceString
0x180025566  lea     rcx, [rsp+170h+Value]; DestinationString
0x18002556b  call    cs:__imp_RtlInitUnicodeString
0x180025572  nop     dword ptr [rax+rax+00h]
0x180025577  lea     r8, [rsp+170h+Value]; Value
0x18002557c  lea     rdx, [rsp+170h+DestinationString]; Name
0x180025581  lea     rcx, [rsp+170h+Environment]; Environment
0x180025586  call    cs:__imp_RtlSetEnvironmentVariable
0x18002558d  nop     dword ptr [rax+rax+00h]
0x180025592  mov     edi, eax
0x180025594  test    eax, eax
0x180025596  jns     short loc_1800255CD
0x180025598  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002559f  lea     rbx, WPP_GLOBAL_Control
0x1800255a6  cmp     rcx, rbx
0x1800255a9  jz      loc_180025AD2
0x1800255af  test    byte ptr [rcx+1Ch], 2
0x1800255b3  jz      loc_180025AD2
0x1800255b9  cmp     byte ptr [rcx+19h], 1
0x1800255bd  jb      loc_180025AD2
0x1800255c3  mov     edx, 1Eh
0x1800255c8  jmp     loc_18002524A
0x1800255cd  lea     rdx, aNotafter; "NotAfter"
0x1800255d4  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x1800255d9  call    cs:__imp_RtlInitUnicodeString
0x1800255e0  nop     dword ptr [rax+rax+00h]
0x1800255e5  mov     rdx, [rbx+30h]; SourceString
0x1800255e9  lea     rcx, [rsp+170h+Value]; DestinationString
0x1800255ee  call    cs:__imp_RtlInitUnicodeString
0x1800255f5  nop     dword ptr [rax+rax+00h]
0x1800255fa  lea     r8, [rsp+170h+Value]; Value
0x1800255ff  lea     rdx, [rsp+170h+DestinationString]; Name
0x180025604  lea     rcx, [rsp+170h+Environment]; Environment
0x180025609  call    cs:__imp_RtlSetEnvironmentVariable
0x180025610  nop     dword ptr [rax+rax+00h]
0x180025615  mov     edi, eax
0x180025617  test    eax, eax
0x180025619  jns     short loc_180025650
0x18002561b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180025622  lea     rbx, WPP_GLOBAL_Control
0x180025629  cmp     rcx, rbx
0x18002562c  jz      loc_180025AD2
0x180025632  test    byte ptr [rcx+1Ch], 2
0x180025636  jz      loc_180025AD2
0x18002563c  cmp     byte ptr [rcx+19h], 1
0x180025640  jb      loc_180025AD2
0x180025646  mov     edx, 1Fh
0x18002564b  jmp     loc_18002524A
0x180025650  lea     rdx, aStorelocation; "StoreLocation"
0x180025657  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x18002565c  call    cs:__imp_RtlInitUnicodeString
0x180025663  nop     dword ptr [rax+rax+00h]
0x180025668  mov     rdx, [rbx+38h]; SourceString
0x18002566c  lea     rcx, [rsp+170h+Value]; DestinationString
0x180025671  call    cs:__imp_RtlInitUnicodeString
0x180025678  nop     dword ptr [rax+rax+00h]
0x18002567d  lea     r8, [rsp+170h+Value]; Value
0x180025682  lea     rdx, [rsp+170h+DestinationString]; Name
0x180025687  lea     rcx, [rsp+170h+Environment]; Environment
0x18002568c  call    cs:__imp_RtlSetEnvironmentVariable
0x180025693  nop     dword ptr [rax+rax+00h]
0x180025698  mov     edi, eax
0x18002569a  test    eax, eax
0x18002569c  jns     short loc_1800256D3
0x18002569e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800256a5  lea     rbx, WPP_GLOBAL_Control
0x1800256ac  cmp     rcx, rbx
0x1800256af  jz      loc_180025AD2
0x1800256b5  test    byte ptr [rcx+1Ch], 2
0x1800256b9  jz      loc_180025AD2
0x1800256bf  cmp     byte ptr [rcx+19h], 1
0x1800256c3  jb      loc_180025AD2
0x1800256c9  mov     edx, 20h ; ' '
0x1800256ce  jmp     loc_18002524A
0x1800256d3  lea     rdx, aStorename; "StoreName"
0x1800256da  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x1800256df  call    cs:__imp_RtlInitUnicodeString
0x1800256e6  nop     dword ptr [rax+rax+00h]
0x1800256eb  mov     rdx, [rbx+40h]; SourceString
0x1800256ef  lea     rcx, [rsp+170h+Value]; DestinationString
0x1800256f4  call    cs:__imp_RtlInitUnicodeString
0x1800256fb  nop     dword ptr [rax+rax+00h]
0x180025700  lea     r8, [rsp+170h+Value]; Value
0x180025705  lea     rdx, [rsp+170h+DestinationString]; Name
  ... truncated ...
```
