# GatherSystemConfiguration(_SYSTEM_CONFIGURATION * *)

- ea: `0x180015ae8`
- end: `0x180015ddf`
- name: `?GatherSystemConfiguration@@YAJPEAPEAU_SYSTEM_CONFIGURATION@@@Z`
- size: `759`
- prototype: `__int64 __fastcall(struct _SYSTEM_CONFIGURATION **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ab30`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x18001555c`
- `0x1800156c4`
- `0x180015834`
- `0x180015ae8`
- `0x180015de8`
- `0x180015fa8`
- `0x1800180be`
- `0x1800180f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015b8c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015b8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015b76`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015b76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c38`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x180015d4d`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x180015d4d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180015cd7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180015cd7`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180015c2e`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180015c2e`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x180015ca5`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x180015ca5`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180015ccf`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180015ccf`
- `POWRPROF!PowerDeterminePlatformRole` at `0x180015d1e`
- `POWRPROF!PowerDeterminePlatformRole` at `0x180015d1e`

## string_xrefs

- `0x180015b4f`: `SystemConfiguration`
- `0x180015d0c`: `SystemProductName`
- `0x180015b5c`: `GatherSystemConfiguration`
- `0x180015ba8`: `GatherSystemConfiguration`
- `0x180015d85`: `GatherSystemConfiguration`
- `0x180015da3`: `GatherSystemConfiguration`
- `0x180015dce`: `GatherSystemConfiguration`

## pseudocode

```c
__int64 __fastcall GatherSystemConfiguration(struct _SYSTEM_CONFIGURATION **a1)
{
  int v2; // edx
  int v3; // ecx
  signed int v4; // ebx
  HANDLE ProcessHeap; // rax
  void *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  void *v9; // rdi
  int v11; // edx
  signed int LastError; // eax
  DWORD dwMajorVersion; // ecx
  DWORD dwMinorVersion; // edx
  DWORD v15; // r10d
  DWORD v16; // r8d
  bool v17; // zf
  int v18; // [rsp+30h] [rbp-D0h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+38h] [rbp-C8h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v21; // [rsp+184h] [rbp+84h]
  unsigned __int16 v22; // [rsp+186h] [rbp+86h]
  char v23; // [rsp+18Ah] [rbp+8Ah]

  memset_0(&VersionInformation, 0, 0x11Cu);
  v18 = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  if ( !a1 )
  {
    v4 = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sqs_EventWriteTransfer(
        v3,
        v2,
        (unsigned int)"GatherSystemConfiguration",
        -2147024809,
        (__int64)"SystemConfiguration");
    return (unsigned int)v4;
  }
  *a1 = 0;
  ProcessHeap = GetProcessHeap();
  v6 = HeapAlloc(ProcessHeap, 8u, 0x90u);
  v9 = v6;
  if ( !v6 )
  {
    v4 = -2147024882;
LABEL_6:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
    {
LABEL_9:
      if ( !v9 )
        return (unsigned int)v4;
LABEL_10:
      DestroySystemConfiguration((struct _SYSTEM_CONFIGURATION *)v9, v7);
      return (unsigned int)v4;
    }
    McTemplateU0s_EventWriteTransfer(v8, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY, "GatherSystemConfiguration");
LABEL_8:
    if ( v4 >= 0 )
      return (unsigned int)v4;
    goto LABEL_9;
  }
  memset_0(v6, 0, 0x90u);
  if ( (int)GatherSMBIOS((struct _SYSTEM_CONFIGURATION *)v9, v11) < 0 )
    memset_0(v9, 0, 0x90u);
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( !GetVersionExW(&VersionInformation) )
    goto LABEL_15;
  dwMajorVersion = VersionInformation.dwMajorVersion;
  *(_DWORD *)v9 = VersionInformation.dwMajorVersion;
  dwMinorVersion = VersionInformation.dwMinorVersion;
  *((_DWORD *)v9 + 1) = VersionInformation.dwMinorVersion;
  v15 = v21;
  *((_WORD *)v9 + 4) = v21;
  v16 = v22;
  *((_WORD *)v9 + 5) = v22;
  *((_DWORD *)v9 + 3) = VersionInformation.dwBuildNumber;
  *((_BYTE *)v9 + 22) = v23;
  if ( GetProductInfo(dwMajorVersion, dwMinorVersion, v15, v16, (PDWORD)v9 + 4) )
  {
    v4 = IsWow64(&v18);
    if ( v4 >= 0 )
    {
      if ( v18 )
        GetNativeSystemInfo(&SystemInfo);
      else
        GetSystemInfo(&SystemInfo);
      v17 = *((_QWORD *)v9 + 5) == 0;
      *((_WORD *)v9 + 10) = SystemInfo.wProcessorArchitecture;
      if ( !v17 || (v4 = GatherProductValue(L"SystemManufacturer", (unsigned __int16 **)v9 + 5), v4 >= 0) )
      {
        if ( *((_QWORD *)v9 + 6)
          || (v4 = GatherProductValue(L"SystemProductName", (unsigned __int16 **)v9 + 6), v4 >= 0) )
        {
          *((_DWORD *)v9 + 33) = PowerDeterminePlatformRole() == PlatformRoleMobile;
          v4 = IsMSFTInternal(v18, (int *)v9 + 34);
          if ( v4 >= 0 )
          {
            *((_DWORD *)v9 + 9) = GetUserGeoID(0x10u);
            *a1 = (struct _SYSTEM_CONFIGURATION *)v9;
            v9 = 0;
            goto LABEL_32;
          }
        }
      }
    }
  }
  else
  {
LABEL_15:
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
    {
      v4 = -2147467259;
      goto LABEL_33;
    }
  }
  if ( v4 == -2147024882 )
    goto LABEL_6;
  if ( v4 == -2147024809 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sq_EventWriteTransfer(v8, v7, "GatherSystemConfiguration", 2147942487LL);
    goto LABEL_10;
  }
LABEL_32:
  if ( v4 )
  {
LABEL_33:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sq_EventWriteTransfer(v8, v7, "GatherSystemConfiguration", (unsigned int)v4);
    goto LABEL_8;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    McTemplateU0s_EventWriteTransfer(v8, SDIAGPRV_EVENT_DEBUG_SUCCESS, "GatherSystemConfiguration");
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180015ae8  push    rbp
0x180015aea  push    rbx
0x180015aeb  push    rsi
0x180015aec  push    rdi
0x180015aed  lea     rbp, [rsp-0A8h]
0x180015af5  sub     rsp, 1A8h
0x180015afc  mov     rax, cs:__security_cookie
0x180015b03  xor     rax, rsp
0x180015b06  mov     [rbp+0C0h+var_30], rax
0x180015b0d  mov     rsi, rcx
0x180015b10  xor     edx, edx; Val
0x180015b12  lea     rcx, [rsp+1C0h+VersionInformation]; void *
0x180015b17  mov     r8d, 11Ch; Size
0x180015b1d  call    memset_0
0x180015b22  mov     [rsp+1C0h+var_190], 0
0x180015b2a  xorps   xmm0, xmm0
0x180015b2d  movups  xmmword ptr [rsp+1C0h+SystemInfo], xmm0
0x180015b32  movups  xmmword ptr [rsp+1C0h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180015b37  movups  xmmword ptr [rsp+1C0h+SystemInfo.dwNumberOfProcessors], xmm0
0x180015b3c  test    rsi, rsi
0x180015b3f  jnz     short loc_180015B6F
0x180015b41  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180015b48  mov     ebx, 80070057h
0x180015b4d  jz      short loc_180015BCC
0x180015b4f  lea     rax, aSystemconfigur; "SystemConfiguration"
0x180015b56  mov     r9d, 80070057h
0x180015b5c  lea     r8, aGathersystemco; "GatherSystemConfiguration"
0x180015b63  mov     [rsp+1C0h+pdwReturnedProductType], rax
0x180015b68  call    McTemplateU0sqs_EventWriteTransfer
0x180015b6d  jmp     short loc_180015BCC
0x180015b6f  mov     qword ptr [rsi], 0
0x180015b76  call    cs:__imp_GetProcessHeap
0x180015b7c  mov     ebx, 90h
0x180015b81  mov     edx, 8; dwFlags
0x180015b86  mov     rcx, rax; hHeap
0x180015b89  mov     r8d, ebx; dwBytes
0x180015b8c  call    cs:__imp_HeapAlloc
0x180015b92  mov     rdi, rax
0x180015b95  test    rax, rax
0x180015b98  jnz     short loc_180015BE9
0x180015b9a  mov     ebx, 8007000Eh
0x180015b9f  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180015ba6  jz      short loc_180015BBF
0x180015ba8  lea     r8, aGathersystemco; "GatherSystemConfiguration"
0x180015baf  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x180015bb6  call    McTemplateU0s_EventWriteTransfer
0x180015bbb  test    ebx, ebx
0x180015bbd  jns     short loc_180015BCC
0x180015bbf  test    rdi, rdi
0x180015bc2  jz      short loc_180015BCC
0x180015bc4  mov     rcx, rdi; struct _SYSTEM_CONFIGURATION *
0x180015bc7  call    ?DestroySystemConfiguration@@YAJPEAU_SYSTEM_CONFIGURATION@@@Z; DestroySystemConfiguration(_SYSTEM_CONFIGURATION *)
0x180015bcc  mov     eax, ebx
0x180015bce  mov     rcx, [rbp+0C0h+var_30]
0x180015bd5  xor     rcx, rsp; StackCookie
0x180015bd8  call    __security_check_cookie
0x180015bdd  add     rsp, 1A8h
0x180015be4  pop     rdi
0x180015be5  pop     rsi
0x180015be6  pop     rbx
0x180015be7  pop     rbp
0x180015be8  retn
0x180015be9  mov     r8, rbx; Size
0x180015bec  xor     edx, edx; Val
0x180015bee  mov     rcx, rdi; void *
0x180015bf1  call    memset_0
0x180015bf6  mov     rcx, rdi; struct _SYSTEM_CONFIGURATION *
0x180015bf9  call    ?GatherSMBIOS@@YAJPEAU_SYSTEM_CONFIGURATION@@@Z; GatherSMBIOS(_SYSTEM_CONFIGURATION *)
0x180015bfe  test    eax, eax
0x180015c00  jns     short loc_180015C0F
0x180015c02  mov     r8, rbx; Size
0x180015c05  xor     edx, edx; Val
0x180015c07  mov     rcx, rdi; void *
0x180015c0a  call    memset_0
0x180015c0f  xor     edx, edx; Val
0x180015c11  lea     rcx, [rsp+1C0h+VersionInformation.dwMajorVersion]; void *
0x180015c16  mov     r8d, 118h; Size
0x180015c1c  call    memset_0
0x180015c21  lea     rcx, [rsp+1C0h+VersionInformation]; lpVersionInformation
0x180015c26  mov     [rsp+1C0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180015c2e  call    cs:__imp_GetVersionExW
0x180015c34  test    eax, eax
0x180015c36  jnz     short loc_180015C5F
0x180015c38  call    cs:__imp_GetLastError
0x180015c3e  mov     ebx, eax
0x180015c40  test    eax, eax
0x180015c42  jle     short loc_180015C4D
0x180015c44  movzx   ebx, ax
0x180015c47  or      ebx, 80070000h
0x180015c4d  test    ebx, ebx
0x180015c4f  js      loc_180015D5D
0x180015c55  mov     ebx, 80004005h
0x180015c5a  jmp     loc_180015D75
0x180015c5f  mov     ecx, [rsp+1C0h+VersionInformation.dwMajorVersion]; dwOSMajorVersion
0x180015c63  mov     [rdi], ecx
0x180015c65  mov     edx, [rsp+1C0h+VersionInformation.dwMinorVersion]; dwOSMinorVersion
0x180015c69  mov     [rdi+4], edx
0x180015c6c  movzx   r10d, [rbp+0C0h+var_3C]
0x180015c74  mov     [rdi+8], r10w
0x180015c79  movzx   r8d, [rbp+0C0h+var_3A]
0x180015c81  mov     [rdi+0Ah], r8w
0x180015c86  mov     r9d, r8d; dwSpMinorVersion
0x180015c89  mov     eax, [rsp+1C0h+VersionInformation.dwBuildNumber]
0x180015c8d  mov     r8d, r10d; dwSpMajorVersion
0x180015c90  mov     [rdi+0Ch], eax
0x180015c93  mov     al, [rbp+0C0h+var_36]
0x180015c99  mov     [rdi+16h], al
0x180015c9c  lea     rax, [rdi+10h]
0x180015ca0  mov     [rsp+1C0h+pdwReturnedProductType], rax; pdwReturnedProductType
0x180015ca5  call    cs:__imp_GetProductInfo
0x180015cab  test    eax, eax
0x180015cad  jz      short loc_180015C38
0x180015caf  lea     rcx, [rsp+1C0h+var_190]; int *
0x180015cb4  call    ?IsWow64@@YAJPEAH@Z; IsWow64(int *)
0x180015cb9  mov     ebx, eax
0x180015cbb  test    eax, eax
0x180015cbd  js      loc_180015D5D
0x180015cc3  cmp     [rsp+1C0h+var_190], 0
0x180015cc8  lea     rcx, [rsp+1C0h+SystemInfo]; lpSystemInfo
0x180015ccd  jz      short loc_180015CD7
0x180015ccf  call    cs:__imp_GetNativeSystemInfo
0x180015cd5  jmp     short loc_180015CDD
0x180015cd7  call    cs:__imp_GetSystemInfo
0x180015cdd  movzx   eax, word ptr [rsp+1C0h+SystemInfo]
0x180015ce2  lea     rdx, [rdi+28h]; unsigned __int16 **
0x180015ce6  cmp     qword ptr [rdx], 0
0x180015cea  mov     [rdi+14h], ax
0x180015cee  jnz     short loc_180015D02
0x180015cf0  lea     rcx, Value; "SystemManufacturer"
0x180015cf7  call    ?GatherProductValue@@YAJPEBGPEAPEAG@Z; GatherProductValue(ushort const *,ushort * *)
0x180015cfc  mov     ebx, eax
0x180015cfe  test    eax, eax
0x180015d00  js      short loc_180015D5D
0x180015d02  lea     rdx, [rdi+30h]; unsigned __int16 **
0x180015d06  cmp     qword ptr [rdx], 0
0x180015d0a  jnz     short loc_180015D1E
0x180015d0c  lea     rcx, aSystemproductn; "SystemProductName"
0x180015d13  call    ?GatherProductValue@@YAJPEBGPEAPEAG@Z; GatherProductValue(ushort const *,ushort * *)
0x180015d18  mov     ebx, eax
0x180015d1a  test    eax, eax
0x180015d1c  js      short loc_180015D5D
0x180015d1e  call    cs:__imp_PowerDeterminePlatformRole
0x180015d24  xor     ecx, ecx
0x180015d26  lea     rdx, [rdi+88h]; int *
0x180015d2d  cmp     eax, 2
0x180015d30  setz    cl
0x180015d33  mov     [rdi+84h], ecx
0x180015d39  mov     ecx, [rsp+1C0h+var_190]; int
0x180015d3d  call    ?IsMSFTInternal@@YAJHPEAH@Z; IsMSFTInternal(int,int *)
0x180015d42  mov     ebx, eax
0x180015d44  test    eax, eax
0x180015d46  js      short loc_180015D5D
0x180015d48  mov     ecx, 10h; GeoClass
0x180015d4d  call    cs:__imp_GetUserGeoID
0x180015d53  mov     [rdi+24h], eax
0x180015d56  mov     [rsi], rdi
0x180015d59  xor     edi, edi
0x180015d5b  jmp     short loc_180015D71
0x180015d5d  cmp     ebx, 8007000Eh
0x180015d63  jz      loc_180015B9F
0x180015d69  cmp     ebx, 80070057h
0x180015d6f  jz      short loc_180015DBB
0x180015d71  test    ebx, ebx
0x180015d73  jz      short loc_180015D96
0x180015d75  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180015d7c  jz      loc_180015BBB
0x180015d82  mov     r9d, ebx
0x180015d85  lea     r8, aGathersystemco; "GatherSystemConfiguration"
0x180015d8c  call    McTemplateU0sq_EventWriteTransfer
0x180015d91  jmp     loc_180015BBB
0x180015d96  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180015d9d  jz      loc_180015BCC
0x180015da3  lea     r8, aGathersystemco; "GatherSystemConfiguration"
0x180015daa  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180015db1  call    McTemplateU0s_EventWriteTransfer
0x180015db6  jmp     loc_180015BCC
0x180015dbb  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180015dc2  jz      loc_180015BC4
0x180015dc8  mov     r9d, 80070057h
0x180015dce  lea     r8, aGathersystemco; "GatherSystemConfiguration"
0x180015dd5  call    McTemplateU0sq_EventWriteTransfer
0x180015dda  jmp     loc_180015BC4
```
