# CheckAndFixBitsServiceSettings(int,ulong)

- ea: `0x1800fbedc`
- end: `0x1800fc149`
- name: `?CheckAndFixBitsServiceSettings@@YAJHK@Z`
- size: `621`
- prototype: `__int64 __fastcall()`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x1800fc324`

## callees

- `0x18000def4`
- `0x18000df20`
- `0x1800d9a70`
- `0x1800fbedc`
- `0x180238960`
- `0x180238984`
- `0x180239584`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fbf8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fbf8e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800fbf51`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800fbf51`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800fc101`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800fc10f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800fc101`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800fc10f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800fbf2b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800fbf2b`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1800fc0c9`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1800fc0c9`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800fc08e`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800fc08e`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800fbf78`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800fc01a`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800fbf78`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800fc01a`

## string_xrefs

- `0x1800fbf14`: `ServicesActive`
- `0x1800fbff6`: `C:\__w\1\s\src\Client\Engine\Agent\bitsfixup.cpp`
- `0x1800fc0a3`: `C:\__w\1\s\src\Client\Engine\Agent\bitsfixup.cpp`
- `0x1800fc0db`: `C:\__w\1\s\src\Client\Engine\Agent\bitsfixup.cpp`

## pseudocode

```c
__int64 __fastcall CheckAndFixBitsServiceSettings()
{
  SC_HANDLE v0; // rdi
  struct _QUERY_SERVICE_CONFIGW *v1; // rbx
  DWORD v2; // r12d
  int v3; // r14d
  int v4; // r15d
  SC_HANDLE v5; // rax
  const char *v6; // r9
  SC_HANDLE v7; // rbp
  __int64 v8; // rdx
  SC_HANDLE v9; // rax
  unsigned int LastError; // esi
  __int64 v11; // rdx
  DWORD v12; // r8d
  DWORD v13; // esi
  struct _QUERY_SERVICE_CONFIGW *v14; // rax
  const struct std::nothrow_t *v15; // rdx
  const char *v16; // r9
  int lpBinaryPathName; // [rsp+20h] [rbp-88h]
  DWORD pcbBytesNeeded; // [rsp+78h] [rbp-30h] BYREF
  int Info; // [rsp+7Ch] [rbp-2Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v0 = 0;
  v1 = 0;
  v2 = -1;
  v3 = 0;
  v4 = 0;
  v5 = OpenSCManagerW(0, L"ServicesActive", 0x40000000u);
  v7 = v5;
  if ( !v5 )
  {
    v8 = 35;
LABEL_23:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v8,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\bitsfixup.cpp",
                  v6);
    goto LABEL_28;
  }
  v9 = OpenServiceW(v5, L"BITS", 0xC0000000);
  v0 = v9;
  if ( !v9 )
  {
    v8 = 41;
    goto LABEL_23;
  }
  pcbBytesNeeded = 0;
  if ( QueryServiceConfigW(v9, 0, 0, &pcbBytesNeeded) )
  {
    LastError = -2145120257;
    v11 = 49;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\bitsfixup.cpp",
      (const char *)LastError,
      lpBinaryPathName);
    goto LABEL_28;
  }
  if ( GetLastError() != 122 )
  {
    LastError = -2147019873;
    v11 = 51;
    goto LABEL_14;
  }
  v12 = pcbBytesNeeded;
  v13 = pcbBytesNeeded;
  if ( pcbBytesNeeded )
  {
    v14 = (struct _QUERY_SERVICE_CONFIGW *)operator new[](pcbBytesNeeded, (const struct std::nothrow_t *)&std::nothrow);
    v1 = v14;
    if ( v14 )
      memset(v14, 0, v13);
    LastError = v1 == 0 ? 0x8007000E : 0;
    if ( !v1 )
    {
      v11 = 52;
      goto LABEL_14;
    }
    v12 = pcbBytesNeeded;
  }
  if ( !QueryServiceConfigW(v0, v1, v12, &pcbBytesNeeded) )
  {
    v8 = 57;
    goto LABEL_23;
  }
  if ( v1->dwStartType == 4 )
  {
    v2 = 2;
    v3 = 1;
    v4 = 1;
  }
  if ( v3 && !ChangeServiceConfigW(v0, 0xFFFFFFFF, v2, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
  {
    v8 = 105;
    goto LABEL_23;
  }
  if ( v4 )
  {
    Info = 1;
    if ( !ChangeServiceConfig2W(v0, 3u, &Info) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x76,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\bitsfixup.cpp",
        v16);
  }
  LastError = 0;
LABEL_28:
  if ( v1 )
    operator delete(v1, v15);
  if ( v0 )
    CloseServiceHandle(v0);
  if ( v7 )
    CloseServiceHandle(v7);
  return LastError;
}

```

## disassembly

```asm
0x1800fbedc  mov     rax, rsp
0x1800fbedf  mov     [rax+8], rbx
0x1800fbee3  mov     [rax+10h], rbp
0x1800fbee7  mov     [rax+18h], rsi
0x1800fbeeb  mov     [rax+20h], rdi
0x1800fbeef  push    r12
0x1800fbef1  push    r14
0x1800fbef3  push    r15
0x1800fbef5  sub     rsp, 90h
0x1800fbefc  mov     rax, cs:__security_cookie
0x1800fbf03  xor     rax, rsp
0x1800fbf06  mov     [rsp+0A8h+var_28], rax
0x1800fbf0e  mov     r8d, 40000000h; dwDesiredAccess
0x1800fbf14  lea     rdx, DatabaseName; "ServicesActive"
0x1800fbf1b  xor     ecx, ecx; lpMachineName
0x1800fbf1d  xor     edi, edi
0x1800fbf1f  xor     ebx, ebx
0x1800fbf21  or      r12d, 0FFFFFFFFh
0x1800fbf25  xor     r14d, r14d
0x1800fbf28  xor     r15d, r15d
0x1800fbf2b  call    cs:__imp_OpenSCManagerW
0x1800fbf31  mov     rbp, rax
0x1800fbf34  test    rax, rax
0x1800fbf37  jnz     short loc_1800FBF41
0x1800fbf39  lea     edx, [rdi+23h]
0x1800fbf3c  jmp     loc_1800FC09B
0x1800fbf41  mov     r8d, 0C0000000h; dwDesiredAccess
0x1800fbf47  lea     rdx, ?c_szBitsService@@3QB_WB; "BITS"
0x1800fbf4e  mov     rcx, rbp; hSCManager
0x1800fbf51  call    cs:__imp_OpenServiceW
0x1800fbf57  mov     rdi, rax
0x1800fbf5a  test    rax, rax
0x1800fbf5d  jnz     short loc_1800FBF67
0x1800fbf5f  lea     edx, [rax+29h]
0x1800fbf62  jmp     loc_1800FC09B
0x1800fbf67  lea     r9, [rsp+0A8h+pcbBytesNeeded]; pcbBytesNeeded
0x1800fbf6c  mov     [rsp+0A8h+pcbBytesNeeded], ebx
0x1800fbf70  xor     r8d, r8d; cbBufSize
0x1800fbf73  xor     edx, edx; lpServiceConfig
0x1800fbf75  mov     rcx, rdi; hService
0x1800fbf78  call    cs:__imp_QueryServiceConfigW
0x1800fbf7e  test    eax, eax
0x1800fbf80  jz      short loc_1800FBF8E
0x1800fbf82  mov     esi, 80240FFFh
0x1800fbf87  mov     edx, 31h ; '1'
0x1800fbf8c  jmp     short loc_1800FBFEE
0x1800fbf8e  call    cs:__imp_GetLastError
0x1800fbf94  cmp     eax, 7Ah ; 'z'
0x1800fbf97  jz      short loc_1800FBFA5
0x1800fbf99  mov     esi, 8007139Fh
0x1800fbf9e  mov     edx, 33h ; '3'
0x1800fbfa3  jmp     short loc_1800FBFEE
0x1800fbfa5  mov     r8d, [rsp+0A8h+pcbBytesNeeded]
0x1800fbfaa  mov     esi, r8d
0x1800fbfad  test    r8d, r8d
0x1800fbfb0  jz      short loc_1800FC00F
0x1800fbfb2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800fbfb9  mov     ecx, r8d; unsigned __int64
0x1800fbfbc  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800fbfc1  mov     rbx, rax
0x1800fbfc4  test    rax, rax
0x1800fbfc7  jz      short loc_1800FBFD6
0x1800fbfc9  mov     r8d, esi; Size
0x1800fbfcc  xor     edx, edx; Val
0x1800fbfce  mov     rcx, rax; void *
0x1800fbfd1  call    memset
0x1800fbfd6  mov     rax, rbx
0x1800fbfd9  neg     rax
0x1800fbfdc  sbb     esi, esi
0x1800fbfde  not     esi
0x1800fbfe0  and     esi, 8007000Eh
0x1800fbfe6  test    rbx, rbx
0x1800fbfe9  jnz     short loc_1800FC00A
0x1800fbfeb  lea     edx, [rbx+34h]; void *
0x1800fbfee  mov     rcx, [rsp+0A8h]; this
0x1800fbff6  lea     r8, aCW1SSrcClientE_82; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x1800fbffd  mov     r9d, esi; char *
0x1800fc000  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fc005  jmp     loc_1800FC0EC
0x1800fc00a  mov     r8d, [rsp+0A8h+pcbBytesNeeded]; cbBufSize
0x1800fc00f  lea     r9, [rsp+0A8h+pcbBytesNeeded]; pcbBytesNeeded
0x1800fc014  mov     rdx, rbx; lpServiceConfig
0x1800fc017  mov     rcx, rdi; hService
0x1800fc01a  call    cs:__imp_QueryServiceConfigW
0x1800fc020  test    eax, eax
0x1800fc022  jnz     short loc_1800FC029
0x1800fc024  lea     edx, [rax+39h]
0x1800fc027  jmp     short loc_1800FC09B
0x1800fc029  cmp     dword ptr [rbx+4], 4
0x1800fc02d  mov     esi, 1
0x1800fc032  jnz     short loc_1800FC03E
0x1800fc034  lea     r12d, [rsi+1]
0x1800fc038  mov     r14d, esi
0x1800fc03b  mov     r15d, esi
0x1800fc03e  test    r14d, r14d
0x1800fc041  jz      short loc_1800FC0B3
0x1800fc043  mov     [rsp+0A8h+lpDisplayName], 0; lpDisplayName
0x1800fc04c  or      edx, 0FFFFFFFFh; dwServiceType
0x1800fc04f  mov     [rsp+0A8h+lpPassword], 0; lpPassword
0x1800fc058  mov     r9d, edx; dwErrorControl
0x1800fc05b  mov     [rsp+0A8h+lpServiceStartName], 0; lpServiceStartName
0x1800fc064  mov     r8d, r12d; dwStartType
0x1800fc067  mov     [rsp+0A8h+lpDependencies], 0; lpDependencies
0x1800fc070  mov     rcx, rdi; hService
0x1800fc073  mov     [rsp+0A8h+lpdwTagId], 0; lpdwTagId
0x1800fc07c  mov     [rsp+0A8h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x1800fc085  mov     [rsp+0A8h+lpBinaryPathName], 0; lpBinaryPathName
0x1800fc08e  call    cs:__imp_ChangeServiceConfigW
0x1800fc094  test    eax, eax
0x1800fc096  jnz     short loc_1800FC0B3
0x1800fc098  lea     edx, [rax+69h]; void *
0x1800fc09b  mov     rcx, [rsp+0A8h]; this
0x1800fc0a3  lea     r8, aCW1SSrcClientE_82; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x1800fc0aa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800fc0af  mov     esi, eax
0x1800fc0b1  jmp     short loc_1800FC0EC
0x1800fc0b3  test    r15d, r15d
0x1800fc0b6  jz      short loc_1800FC0EA
0x1800fc0b8  lea     r8, [rsp+0A8h+Info]; lpInfo
0x1800fc0bd  mov     [rsp+0A8h+Info], esi
0x1800fc0c1  mov     edx, 3; dwInfoLevel
0x1800fc0c6  mov     rcx, rdi; hService
0x1800fc0c9  call    cs:__imp_ChangeServiceConfig2W
0x1800fc0cf  test    eax, eax
0x1800fc0d1  jnz     short loc_1800FC0EA
0x1800fc0d3  mov     rcx, [rsp+0A8h]; this
0x1800fc0db  lea     r8, aCW1SSrcClientE_82; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x1800fc0e2  lea     edx, [rax+76h]; void *
0x1800fc0e5  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800fc0ea  xor     esi, esi
0x1800fc0ec  test    rbx, rbx
0x1800fc0ef  jz      short loc_1800FC0F9
0x1800fc0f1  mov     rcx, rbx; void *
0x1800fc0f4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fc0f9  test    rdi, rdi
0x1800fc0fc  jz      short loc_1800FC107
0x1800fc0fe  mov     rcx, rdi; hSCObject
0x1800fc101  call    cs:__imp_CloseServiceHandle
0x1800fc107  test    rbp, rbp
0x1800fc10a  jz      short loc_1800FC115
0x1800fc10c  mov     rcx, rbp; hSCObject
0x1800fc10f  call    cs:__imp_CloseServiceHandle
0x1800fc115  mov     eax, esi
0x1800fc117  mov     rcx, [rsp+0A8h+var_28]
0x1800fc11f  xor     rcx, rsp; StackCookie
0x1800fc122  call    __security_check_cookie
0x1800fc127  lea     r11, [rsp+0A8h+var_18]
0x1800fc12f  mov     rbx, [r11+20h]
0x1800fc133  mov     rbp, [r11+28h]
0x1800fc137  mov     rsi, [r11+30h]
0x1800fc13b  mov     rdi, [r11+38h]
0x1800fc13f  mov     rsp, r11
0x1800fc142  pop     r15
0x1800fc144  pop     r14
0x1800fc146  pop     r12
0x1800fc148  retn
```
