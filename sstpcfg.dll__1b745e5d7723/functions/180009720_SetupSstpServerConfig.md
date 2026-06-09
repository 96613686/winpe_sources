# SetupSstpServerConfig

- ea: `0x180009720`
- end: `0x180009b2e`
- name: `SetupSstpServerConfig`
- size: `1038`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180002518`
- `0x180006794`
- `0x180009720`
- `0x18000a014`
- `0x18000a044`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800097a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009846`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800097a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009846`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800099c2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800099c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009aee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009b09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009aee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009b09`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800098c9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800098c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009afe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009afe`
- `rtutils!RouterLogEventStringW` at `0x1800098fe`
- `rtutils!RouterLogEventStringW` at `0x1800099f1`
- `rtutils!RouterLogEventStringW` at `0x1800098fe`
- `rtutils!RouterLogEventStringW` at `0x1800099f1`

## string_xrefs

- `0x18000979c`: `System\CurrentControlSet\Services\SstpSvc\Parameters`
- `0x1800097f6`: `Unable to open the SSTPSVC Params Key: %d`
- `0x18000983c`: `System\CurrentControlSet\Services\SstpSvc\Parameters\ConfigStore`
- `0x180009979`: `System\CurrentControlSet\Services\SstpSvc\Parameters\ConfigStore`
- `0x1800098a3`: `ConfigStore key not present. Possible leak of URLACL/CertInfo as the current config is assumed to be default`
- `0x18000993a`: `Unable to create config store Security Desc: %d`
- `0x180009a34`: `Unable to create the config store key. Bailing out - %d`
- `0x180009aa4`: `Failure to open the config store: %d`

## pseudocode

```c
__int64 SetupSstpServerConfig()
{
  unsigned int v0; // eax
  __int64 v1; // r8
  DWORD dwErrorCode; // ebx
  unsigned int v3; // eax
  __int64 v4; // r8
  __int64 v5; // r8
  const wchar_t *v6; // rdx
  LSTATUS v7; // eax
  __int64 v8; // r8
  __int16 v10; // [rsp+50h] [rbp-B0h] BYREF
  char v11; // [rsp+52h] [rbp-AEh]
  __int16 v12; // [rsp+54h] [rbp-ACh] BYREF
  char v13; // [rsp+56h] [rbp-AAh]
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp-98h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+70h] [rbp-90h] BYREF
  int v18; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v19[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  v13 = 0;
  v11 = 0;
  v12 = 0;
  v10 = 0;
  phkResult = 0;
  hKey = 0;
  SecurityDescriptor = 0;
  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\SstpSvc\\Parameters",
         0,
         0x2001Fu,
         &phkResult);
  dwErrorCode = v0;
  if ( !v0 )
  {
    v3 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\SstpSvc\\Parameters\\ConfigStore",
           0,
           0x2001Fu,
           &hKey);
    dwErrorCode = v3;
    if ( v3 == 2 )
    {
      memset(&SecurityAttributes, 0, 20);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= (unsigned __int8)v3 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 167);
      }
      if ( (_QWORD)xmmword_1800146E0 )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSstpCfgTemplateFunc)(
          gSstpCfgEtwContext,
          xmmword_1800146E0,
          L"ConfigStore key not present. Possible leak of URLACL/CertInfo as the current config is assumed to be default");
      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
              L"D:P(A;OICI;GR;;;LS)(A;OICI;GR;;;NO)(A;OICI;GR;;;NS)(A;OICI;GA;;;SY)(A;OICI;GR;;;BU)(A;OICI;GA;;;BA)",
              1u,
              &SecurityDescriptor,
              0) )
      {
        dwErrorCode = GetLastError();
        RouterLogEventStringW(EventSource, 2u, 7u, 0, 0, dwErrorCode, 0);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 168, v5, dwErrorCode);
        }
        if ( !(_QWORD)xmmword_1800146E0 )
          goto LABEL_40;
        v6 = L"Unable to create config store Security Desc: %d";
LABEL_22:
        LOWORD(v18) = 0;
        FormatRRASErrorString(&v18, v6, dwErrorCode);
        ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v18);
LABEL_40:
        RegCloseKey(phkResult);
        return dwErrorCode;
      }
      SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
      SecurityAttributes.nLength = 24;
      SecurityAttributes.bInheritHandle = 1;
      v7 = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\SstpSvc\\Parameters\\ConfigStore",
             0,
             0,
             0,
             0x2001Fu,
             &SecurityAttributes,
             &hKey,
             0);
      dwErrorCode = v7;
      if ( v7 )
      {
        RouterLogEventStringW(EventSource, 2u, 7u, 0, 0, v7, 0);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 169, v8, dwErrorCode);
        }
        if ( (_QWORD)xmmword_1800146E0 )
        {
          LOWORD(v18) = 0;
          FormatRRASErrorString(&v18, L"Unable to create the config store key. Bailing out - %d", dwErrorCode);
          ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
            gSstpCfgEtwContext,
            xmmword_1800146E0,
            &v18);
        }
        goto LABEL_38;
      }
    }
    else if ( v3 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 170, v4, v3);
      }
      if ( !(_QWORD)xmmword_1800146E0 )
        goto LABEL_40;
      v6 = L"Failure to open the config store: %d";
      goto LABEL_22;
    }
    GetSstpServerConfigp(phkResult);
    GetSstpServerConfigp(hKey);
    dwErrorCode = ConfigureSstpServer(&v12, &v10, hKey, phkResult);
    RegCloseKey(hKey);
LABEL_38:
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    goto LABEL_40;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 166, v1, v0);
  }
  if ( (_QWORD)xmmword_1800146E0 )
  {
    LOWORD(v18) = 0;
    FormatRRASErrorString(&v18, L"Unable to open the SSTPSVC Params Key: %d", dwErrorCode);
    ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v18);
  }
  return dwErrorCode;
}

```

## disassembly

```asm
0x180009720  push    rbp
0x180009722  push    rbx
0x180009723  push    rsi
0x180009724  push    rdi
0x180009725  push    r12
0x180009727  lea     rbp, [rsp-7A0h]
0x18000972f  sub     rsp, 8A0h
0x180009736  mov     rax, cs:__security_cookie
0x18000973d  xor     rax, rsp
0x180009740  mov     [rbp+7C0h+var_30], rax
0x180009747  xor     eax, eax
0x180009749  lea     rcx, [rbp+7C0h+var_82C]; void *
0x18000974d  xor     esi, esi
0x18000974f  mov     [rsp+8C0h+var_86B], ax
0x180009754  mov     [rsp+8C0h+var_86F], ax
0x180009759  xor     edx, edx; Val
0x18000975b  mov     r8d, 7FCh; Size
0x180009761  mov     [rsp+54h], ax
0x180009766  mov     [rsp+50h], ax
0x18000976b  mov     [rsp+8C0h+var_860], rsi
0x180009770  mov     [rsp+8C0h+hKey], rsi
0x180009775  mov     [rsp+8C0h+SecurityDescriptor], rsi
0x18000977a  mov     [rbp+7C0h+var_830], esi
0x18000977d  call    memset_0
0x180009782  lea     rax, [rsp+8C0h+var_860]
0x180009787  mov     r12, 0FFFFFFFF80000002h
0x18000978e  mov     rcx, r12; hKey
0x180009791  mov     [rsp+8C0h+phkResult], rax; phkResult
0x180009796  mov     r9d, 2001Fh; samDesired
0x18000979c  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Ss"...
0x1800097a3  xor     r8d, r8d; ulOptions
0x1800097a6  call    cs:__imp_RegOpenKeyExW
0x1800097ac  mov     ebx, eax
0x1800097ae  test    eax, eax
0x1800097b0  jz      short loc_180009829
0x1800097b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097b9  lea     rdi, WPP_GLOBAL_Control
0x1800097c0  cmp     rcx, rdi
0x1800097c3  jz      short loc_1800097E2
0x1800097c5  test    byte ptr [rcx+1Ch], 40h
0x1800097c9  jz      short loc_1800097E2
0x1800097cb  cmp     byte ptr [rcx+19h], 1
0x1800097cf  jb      short loc_1800097E2
0x1800097d1  mov     rcx, [rcx+10h]
0x1800097d5  mov     edx, 0A6h
0x1800097da  mov     r9d, eax
0x1800097dd  call    WPP_SF_d
0x1800097e2  cmp     qword ptr cs:xmmword_1800146E0, rsi
0x1800097e9  jz      loc_180009B0F
0x1800097ef  mov     r8d, ebx
0x1800097f2  mov     word ptr [rbp+7C0h+var_830], si
0x1800097f6  lea     rdx, aUnableToOpenTh; "Unable to open the SSTPSVC Params Key: "...
0x1800097fd  lea     rcx, [rbp+7C0h+var_830]
0x180009801  call    FormatRRASErrorString
0x180009806  mov     rdx, qword ptr cs:xmmword_1800146E0
0x18000980d  lea     r8, [rbp+7C0h+var_830]
0x180009811  mov     rcx, cs:gSstpCfgEtwContext
0x180009818  mov     rax, cs:gSstpCfgTemplateFunc
0x18000981f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009824  jmp     loc_180009B0F
0x180009829  lea     rax, [rsp+8C0h+hKey]
0x18000982e  mov     r9d, 2001Fh; samDesired
0x180009834  xor     r8d, r8d; ulOptions
0x180009837  mov     [rsp+8C0h+phkResult], rax; phkResult
0x18000983c  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Ss"...
0x180009843  mov     rcx, r12; hKey
0x180009846  call    cs:__imp_RegOpenKeyExW
0x18000984c  mov     ebx, eax
0x18000984e  cmp     eax, 2
0x180009851  jnz     loc_180009A67
0x180009857  xor     eax, eax
0x180009859  xorps   xmm0, xmm0
0x18000985c  movups  xmmword ptr [rsp+8C0h+SecurityAttributes.nLength], xmm0
0x180009861  mov     [rbp+7C0h+SecurityAttributes.bInheritHandle], eax
0x180009864  mov     rcx, cs:WPP_GLOBAL_Control
0x18000986b  lea     rdi, WPP_GLOBAL_Control
0x180009872  cmp     rcx, rdi
0x180009875  jz      short loc_180009890
0x180009877  test    byte ptr [rcx+1Ch], 40h
0x18000987b  jz      short loc_180009890
0x18000987d  cmp     [rcx+19h], bl
0x180009880  jb      short loc_180009890
0x180009882  mov     rcx, [rcx+10h]
0x180009886  mov     edx, 0A7h
0x18000988b  call    WPP_SF_
0x180009890  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180009897  test    rdx, rdx
0x18000989a  jz      short loc_1800098B6
0x18000989c  mov     rcx, cs:gSstpCfgEtwContext
0x1800098a3  lea     r8, aConfigstoreKey; "ConfigStore key not present. Possible l"...
0x1800098aa  mov     rax, cs:gSstpCfgTemplateFunc
0x1800098b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098b6  xor     r9d, r9d; SecurityDescriptorSize
0x1800098b9  lea     r8, [rsp+8C0h+SecurityDescriptor]; SecurityDescriptor
0x1800098be  lea     rcx, StringSecurityDescriptor; "D:P(A;OICI;GR;;;LS)(A;OICI;GR;;;NO)(A;O"...
0x1800098c5  lea     edx, [r9+1]; StringSDRevision
0x1800098c9  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800098cf  test    eax, eax
0x1800098d1  jnz     loc_180009974
0x1800098d7  call    cs:__imp_GetLastError
0x1800098dd  mov     rcx, cs:EventSource; hLogHandle
0x1800098e4  xor     r9d, r9d; dwSubStringCount
0x1800098e7  mov     [rsp+8C0h+dwErrorIndex], esi; dwErrorIndex
0x1800098eb  mov     ebx, eax
0x1800098ed  mov     [rsp+8C0h+dwErrorCode], eax; dwErrorCode
0x1800098f1  mov     [rsp+8C0h+phkResult], rsi; plpszSubStringArray
0x1800098f6  lea     edx, [r9+2]; dwEventType
0x1800098fa  lea     r8d, [r9+7]; dwMessageId
0x1800098fe  call    cs:__imp_RouterLogEventStringW
0x180009904  mov     rcx, cs:WPP_GLOBAL_Control
0x18000990b  cmp     rcx, rdi
0x18000990e  jz      short loc_18000992D
0x180009910  test    byte ptr [rcx+1Ch], 40h
0x180009914  jz      short loc_18000992D
0x180009916  cmp     byte ptr [rcx+19h], 1
0x18000991a  jb      short loc_18000992D
0x18000991c  mov     rcx, [rcx+10h]
0x180009920  mov     edx, 0A8h
0x180009925  mov     r9d, ebx
0x180009928  call    WPP_SF_d
0x18000992d  cmp     qword ptr cs:xmmword_1800146E0, rsi
0x180009934  jz      loc_180009B04
0x18000993a  lea     rdx, aUnableToCreate_0; "Unable to create config store Security "...
0x180009941  mov     r8d, ebx
0x180009944  mov     word ptr [rbp+7C0h+var_830], si
0x180009948  lea     rcx, [rbp+7C0h+var_830]
0x18000994c  call    FormatRRASErrorString
0x180009951  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180009958  lea     r8, [rbp+7C0h+var_830]
0x18000995c  mov     rcx, cs:gSstpCfgEtwContext
0x180009963  mov     rax, cs:gSstpCfgTemplateFunc
0x18000996a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000996f  jmp     loc_180009B04
0x180009974  mov     rax, [rsp+8C0h+SecurityDescriptor]
0x180009979  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Ss"...
0x180009980  mov     [rsp+8C0h+lpdwDisposition], rsi; lpdwDisposition
0x180009985  xor     r9d, r9d; lpClass
0x180009988  mov     [rsp+8C0h+SecurityAttributes.lpSecurityDescriptor], rax
0x18000998d  xor     r8d, r8d; Reserved
0x180009990  lea     rax, [rsp+8C0h+hKey]
0x180009995  mov     [rsp+8C0h+SecurityAttributes.nLength], 18h
0x18000999d  mov     [rsp+8C0h+var_888], rax; phkResult
0x1800099a2  mov     rcx, r12; hKey
0x1800099a5  lea     rax, [rsp+8C0h+SecurityAttributes]
0x1800099aa  mov     [rbp+7C0h+SecurityAttributes.bInheritHandle], 1
0x1800099b1  mov     qword ptr [rsp+8C0h+dwErrorIndex], rax; lpSecurityAttributes
0x1800099b6  mov     [rsp+8C0h+dwErrorCode], 2001Fh; samDesired
0x1800099be  mov     dword ptr [rsp+8C0h+phkResult], esi; dwOptions
0x1800099c2  call    cs:__imp_RegCreateKeyExW
0x1800099c8  mov     ebx, eax
0x1800099ca  test    eax, eax
0x1800099cc  jz      loc_180009AB0
0x1800099d2  mov     rcx, cs:EventSource; hLogHandle
0x1800099d9  xor     r9d, r9d; dwSubStringCount
0x1800099dc  mov     [rsp+8C0h+dwErrorIndex], esi; dwErrorIndex
0x1800099e0  mov     [rsp+8C0h+dwErrorCode], eax; dwErrorCode
0x1800099e4  mov     [rsp+8C0h+phkResult], rsi; plpszSubStringArray
0x1800099e9  lea     edx, [r9+2]; dwEventType
0x1800099ed  lea     r8d, [r9+7]; dwMessageId
0x1800099f1  call    cs:__imp_RouterLogEventStringW
0x1800099f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099fe  cmp     rcx, rdi
0x180009a01  jz      short loc_180009A20
0x180009a03  test    byte ptr [rcx+1Ch], 40h
0x180009a07  jz      short loc_180009A20
0x180009a09  cmp     byte ptr [rcx+19h], 1
0x180009a0d  jb      short loc_180009A20
0x180009a0f  mov     rcx, [rcx+10h]
0x180009a13  mov     edx, 0A9h
0x180009a18  mov     r9d, ebx
0x180009a1b  call    WPP_SF_d
0x180009a20  cmp     qword ptr cs:xmmword_1800146E0, rsi
0x180009a27  jz      loc_180009AF4
0x180009a2d  mov     r8d, ebx
0x180009a30  mov     word ptr [rbp+7C0h+var_830], si
0x180009a34  lea     rdx, aUnableToCreate; "Unable to create the config store key. "...
0x180009a3b  lea     rcx, [rbp+7C0h+var_830]
0x180009a3f  call    FormatRRASErrorString
0x180009a44  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180009a4b  lea     r8, [rbp+7C0h+var_830]
0x180009a4f  mov     rcx, cs:gSstpCfgEtwContext
0x180009a56  mov     rax, cs:gSstpCfgTemplateFunc
0x180009a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a62  jmp     loc_180009AF4
0x180009a67  test    ebx, ebx
0x180009a69  jz      short loc_180009AB0
0x180009a6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a72  lea     rdi, WPP_GLOBAL_Control
0x180009a79  cmp     rcx, rdi
0x180009a7c  jz      short loc_180009A9B
0x180009a7e  test    byte ptr [rcx+1Ch], 40h
0x180009a82  jz      short loc_180009A9B
0x180009a84  cmp     byte ptr [rcx+19h], 1
0x180009a88  jb      short loc_180009A9B
0x180009a8a  mov     rcx, [rcx+10h]
0x180009a8e  mov     edx, 0AAh
0x180009a93  mov     r9d, ebx
0x180009a96  call    WPP_SF_d
0x180009a9b  cmp     qword ptr cs:xmmword_1800146E0, rsi
0x180009aa2  jz      short loc_180009B04
0x180009aa4  lea     rdx, aFailureToOpenT; "Failure to open the config store: %d"
0x180009aab  jmp     loc_180009941
0x180009ab0  mov     rcx, [rsp+8C0h+var_860]; hKey
0x180009ab5  lea     rdx, [rsp+8C0h+var_86C]
0x180009aba  call    GetSstpServerConfigp
0x180009abf  mov     rcx, [rsp+8C0h+hKey]; hKey
0x180009ac4  lea     rdx, [rsp+8C0h+var_870]
0x180009ac9  call    GetSstpServerConfigp
0x180009ace  mov     r9, [rsp+8C0h+var_860]
0x180009ad3  lea     rdx, [rsp+8C0h+var_870]
0x180009ad8  mov     r8, [rsp+8C0h+hKey]
0x180009add  lea     rcx, [rsp+8C0h+var_86C]
0x180009ae2  call    ConfigureSstpServer
0x180009ae7  mov     rcx, [rsp+8C0h+hKey]; hKey
0x180009aec  mov     ebx, eax
0x180009aee  call    cs:__imp_RegCloseKey
0x180009af4  mov     rcx, [rsp+8C0h+SecurityDescriptor]; hMem
0x180009af9  test    rcx, rcx
0x180009afc  jz      short loc_180009B04
0x180009afe  call    cs:__imp_LocalFree
0x180009b04  mov     rcx, [rsp+8C0h+var_860]; hKey
0x180009b09  call    cs:__imp_RegCloseKey
0x180009b0f  mov     eax, ebx
0x180009b11  mov     rcx, [rbp+7C0h+var_30]
0x180009b18  xor     rcx, rsp; StackCookie
0x180009b1b  call    __security_check_cookie
0x180009b20  add     rsp, 8A0h
0x180009b27  pop     r12
0x180009b29  pop     rdi
0x180009b2a  pop     rsi
0x180009b2b  pop     rbx
0x180009b2c  pop     rbp
0x180009b2d  retn
```
