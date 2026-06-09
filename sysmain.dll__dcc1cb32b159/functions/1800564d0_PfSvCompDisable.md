# PfSvCompDisable

- ea: `0x1800564d0`
- end: `0x180056780`
- name: `PfSvCompDisable`
- size: `688`
- prototype: `__int64 __fastcall(char *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003d1c0`
- `0x18006a020`

## callees

- `0x180039f94`
- `0x1800564d0`
- `0x180056788`
- `0x1800568d8`
- `0x1800569cc`
- `0x180056b04`
- `0x180073440`
- `0x18009eb40`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180056516`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180056595`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180056516`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180056595`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800566ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056715`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800566ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056715`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005674e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005675c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005674e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005675c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180056681`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180056681`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18005669f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18005669f`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18005670b`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18005670b`

## string_xrefs

- `0x1800565ce`: `ReadyBoot`

## pseudocode

```c
__int64 __fastcall PfSvCompDisable(char *a1, int a2)
{
  SC_HANDLE v4; // rsi
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rdi
  DWORD LastError; // ebx
  wchar_t pszDest[264]; // [rsp+60h] [rbp-248h] BYREF

  v4 = 0;
  PfSvFileInfoRegistrationUpdate(*(unsigned int *)a1);
  if ( (*a1 & 8) == 0 )
  {
    RegDeleteValueW(*(HKEY *)(*(_QWORD *)&PfSvcGlobals + 1448LL), L"EnableSuperfetch");
    PfsDeleteFilesInDirectory(*(_QWORD *)&PfSvcGlobals + 888LL, (__int64)L"*.db");
    PfsDeleteFilesInDirectory(*(_QWORD *)&PfSvcGlobals + 888LL, (__int64)L"*.trx");
    PfsDeleteFilesInDirectory(*(_QWORD *)&PfSvcGlobals + 888LL, (__int64)L"*.bin");
    *(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 1600LL) |= 0x120u;
  }
  if ( (*a1 & 3) == 0 )
  {
    RegDeleteValueW(*(HKEY *)(*(_QWORD *)&PfSvcGlobals + 1448LL), L"EnablePrefetcher");
    PfsDeleteFilesInDirectory(*(_QWORD *)&PfSvcGlobals + 888LL, (__int64)L"*.pf");
  }
  if ( (*a1 & 0x20) == 0 )
  {
    RdBtEnable(0, 0);
    if ( StringCbPrintfW(pszDest, 0x208u, L"%s\\%s", *(_QWORD *)&PfSvcGlobals + 888LL, L"ReadyBoot") >= 0 )
    {
      PfsDeleteFilesInDirectory((__int64)pszDest, (__int64)L"*.fx");
      PfsDeleteFilesInDirectory((__int64)pszDest, (__int64)L"*.xin");
      PfsDeleteFilesInDirectory((__int64)pszDest, (__int64)L"*.etl");
    }
    PfsDeleteFilesInDirectory(*(_QWORD *)&PfSvcGlobals + 888LL, (__int64)L"*.ini");
  }
  if ( (*a1 & 0x30) == 0 )
    RdbDeleteAllAttachState();
  if ( *a1 >= 0 )
  {
    HbDrvDeleteAllAttachState();
    HbDrvDeleteState(*(HKEY *)(*(_QWORD *)&PfSvcGlobals + 1432LL));
  }
  if ( *(_DWORD *)a1 )
  {
    v6 = 0;
    if ( a2 )
      *(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 1600LL) |= 0x40u;
LABEL_22:
    LastError = 0;
    goto LABEL_23;
  }
  v5 = OpenSCManagerW(0, 0, 0xF003Fu);
  v6 = v5;
  if ( v5 && (v4 = OpenServiceW(v5, L"Sysmain", 0xF01FFu)) != 0 || (LastError = GetLastError()) == 0 )
  {
    if ( !ChangeServiceConfigW(v4, 0xFFFFFFFF, 3u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
    {
      LastError = GetLastError();
      goto LABEL_23;
    }
    *(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 1600LL) |= 0x80u;
    goto LABEL_22;
  }
LABEL_23:
  if ( v6 )
    CloseServiceHandle(v6);
  if ( v4 )
    CloseServiceHandle(v4);
  return LastError;
}

```

## disassembly

```asm
0x1800564d0  push    rbx
0x1800564d2  push    rbp
0x1800564d3  push    rsi
0x1800564d4  push    rdi
0x1800564d5  sub     rsp, 288h
0x1800564dc  mov     rax, cs:__security_cookie
0x1800564e3  xor     rax, rsp
0x1800564e6  mov     [rsp+2A8h+var_38], rax
0x1800564ee  mov     rbx, rcx
0x1800564f1  mov     ebp, edx
0x1800564f3  mov     ecx, [rcx]
0x1800564f5  xor     esi, esi
0x1800564f7  call    PfSvFileInfoRegistrationUpdate
0x1800564fc  test    byte ptr [rbx], 8
0x1800564ff  jnz     short loc_18005657B
0x180056501  mov     rcx, cs:PfSvcGlobals
0x180056508  lea     rdx, aEnablesuperfet; "EnableSuperfetch"
0x18005650f  mov     rcx, [rcx+5A8h]; hKey
0x180056516  call    cs:__imp_RegDeleteValueW
0x18005651c  mov     rcx, cs:PfSvcGlobals
0x180056523  lea     rdx, aDb; "*.db"
0x18005652a  add     rcx, 378h
0x180056531  call    PfsDeleteFilesInDirectory
0x180056536  mov     rcx, cs:PfSvcGlobals
0x18005653d  lea     rdx, aTrx; "*.trx"
0x180056544  add     rcx, 378h
0x18005654b  call    PfsDeleteFilesInDirectory
0x180056550  mov     rcx, cs:PfSvcGlobals
0x180056557  lea     rdx, aBin; "*.bin"
0x18005655e  add     rcx, 378h
0x180056565  call    PfsDeleteFilesInDirectory
0x18005656a  mov     rax, cs:PfSvcGlobals
0x180056571  or      dword ptr [rax+640h], 120h
0x18005657b  test    byte ptr [rbx], 3
0x18005657e  jnz     short loc_1800565B5
0x180056580  mov     rcx, cs:PfSvcGlobals
0x180056587  lea     rdx, aEnableprefetch; "EnablePrefetcher"
0x18005658e  mov     rcx, [rcx+5A8h]; hKey
0x180056595  call    cs:__imp_RegDeleteValueW
0x18005659b  mov     rcx, cs:PfSvcGlobals
0x1800565a2  lea     rdx, aPf; "*.pf"
0x1800565a9  add     rcx, 378h
0x1800565b0  call    PfsDeleteFilesInDirectory
0x1800565b5  test    byte ptr [rbx], 20h
0x1800565b8  jnz     loc_180056648
0x1800565be  xor     edx, edx
0x1800565c0  xor     ecx, ecx
0x1800565c2  call    RdBtEnable
0x1800565c7  mov     r9, cs:PfSvcGlobals
0x1800565ce  lea     rax, aReadyboot; "ReadyBoot"
0x1800565d5  add     r9, 378h
0x1800565dc  mov     [rsp+2A8h+lpBinaryPathName], rax
0x1800565e1  lea     r8, aSS; "%s\\%s"
0x1800565e8  mov     edx, 208h; cbDest
0x1800565ed  lea     rcx, [rsp+2A8h+pszDest]; pszDest
0x1800565f2  call    StringCbPrintfW
0x1800565f7  test    eax, eax
0x1800565f9  js      short loc_18005662E
0x1800565fb  lea     rdx, aFx; "*.fx"
0x180056602  lea     rcx, [rsp+2A8h+pszDest]
0x180056607  call    PfsDeleteFilesInDirectory
0x18005660c  lea     rdx, aXin; "*.xin"
0x180056613  lea     rcx, [rsp+2A8h+pszDest]
0x180056618  call    PfsDeleteFilesInDirectory
0x18005661d  lea     rdx, aEtl; "*.etl"
0x180056624  lea     rcx, [rsp+2A8h+pszDest]
0x180056629  call    PfsDeleteFilesInDirectory
0x18005662e  mov     rcx, cs:PfSvcGlobals
0x180056635  lea     rdx, aIni; "*.ini"
0x18005663c  add     rcx, 378h
0x180056643  call    PfsDeleteFilesInDirectory
0x180056648  test    byte ptr [rbx], 30h
0x18005664b  jnz     short loc_180056652
0x18005664d  call    RdbDeleteAllAttachState
0x180056652  test    byte ptr [rbx], 80h
0x180056655  jnz     short loc_18005666F
0x180056657  call    HbDrvDeleteAllAttachState
0x18005665c  mov     rcx, cs:PfSvcGlobals
0x180056663  mov     rcx, [rcx+598h]; hKey
0x18005666a  call    HbDrvDeleteState
0x18005666f  cmp     [rbx], esi
0x180056671  jnz     loc_180056730
0x180056677  xor     edx, edx; lpDatabaseName
0x180056679  xor     ecx, ecx; lpMachineName
0x18005667b  mov     r8d, 0F003Fh; dwDesiredAccess
0x180056681  call    cs:__imp_OpenSCManagerW
0x180056687  mov     rdi, rax
0x18005668a  test    rax, rax
0x18005668d  jz      short loc_1800566AD
0x18005668f  mov     r8d, 0F01FFh; dwDesiredAccess
0x180056695  lea     rdx, ServiceName; "Sysmain"
0x18005669c  mov     rcx, rax; hSCManager
0x18005669f  call    cs:__imp_OpenServiceW
0x1800566a5  mov     rsi, rax
0x1800566a8  test    rax, rax
0x1800566ab  jnz     short loc_1800566BD
0x1800566ad  call    cs:__imp_GetLastError
0x1800566b3  mov     ebx, eax
0x1800566b5  test    eax, eax
0x1800566b7  jnz     loc_180056746
0x1800566bd  mov     [rsp+2A8h+lpDisplayName], 0; lpDisplayName
0x1800566c6  or      edx, 0FFFFFFFFh; dwServiceType
0x1800566c9  mov     [rsp+2A8h+lpPassword], 0; lpPassword
0x1800566d2  mov     r9d, edx; dwErrorControl
0x1800566d5  mov     [rsp+2A8h+lpServiceStartName], 0; lpServiceStartName
0x1800566de  mov     r8d, 3; dwStartType
0x1800566e4  mov     [rsp+2A8h+lpDependencies], 0; lpDependencies
0x1800566ed  mov     rcx, rsi; hService
0x1800566f0  mov     [rsp+2A8h+lpdwTagId], 0; lpdwTagId
0x1800566f9  mov     [rsp+2A8h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x180056702  mov     [rsp+2A8h+lpBinaryPathName], 0; lpBinaryPathName
0x18005670b  call    cs:__imp_ChangeServiceConfigW
0x180056711  test    eax, eax
0x180056713  jnz     short loc_18005671F
0x180056715  call    cs:__imp_GetLastError
0x18005671b  mov     ebx, eax
0x18005671d  jmp     short loc_180056746
0x18005671f  mov     rax, cs:PfSvcGlobals
0x180056726  bts     dword ptr [rax+640h], 7
0x18005672e  jmp     short loc_180056744
0x180056730  xor     edi, edi
0x180056732  test    ebp, ebp
0x180056734  jz      short loc_180056744
0x180056736  mov     rax, cs:PfSvcGlobals
0x18005673d  or      dword ptr [rax+640h], 40h
0x180056744  xor     ebx, ebx
0x180056746  test    rdi, rdi
0x180056749  jz      short loc_180056754
0x18005674b  mov     rcx, rdi; hSCObject
0x18005674e  call    cs:__imp_CloseServiceHandle
0x180056754  test    rsi, rsi
0x180056757  jz      short loc_180056762
0x180056759  mov     rcx, rsi; hSCObject
0x18005675c  call    cs:__imp_CloseServiceHandle
0x180056762  mov     eax, ebx
0x180056764  mov     rcx, [rsp+2A8h+var_38]
0x18005676c  xor     rcx, rsp; StackCookie
0x18005676f  call    __security_check_cookie
0x180056774  add     rsp, 288h
0x18005677b  pop     rdi
0x18005677c  pop     rsi
0x18005677d  pop     rbp
0x18005677e  pop     rbx
0x18005677f  retn
```
