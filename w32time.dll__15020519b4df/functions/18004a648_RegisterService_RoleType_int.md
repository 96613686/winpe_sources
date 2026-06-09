# RegisterService(RoleType,int)

- ea: `0x18004a648`
- end: `0x18004aadd`
- name: `?RegisterService@@YAJW4RoleType@@H@Z`
- size: `1173`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004ade0`
- `0x18004af40`

## callees

- `0x18003d270`
- `0x18004a648`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004aaae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004aaae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a709`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a74d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a7e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a828`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a9ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aa6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a709`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a74d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a7e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a828`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a9ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aa6a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18004a739`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18004a739`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004aa19`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004aa89`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004aa9d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004aa19`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004aa89`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004aa9d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004a814`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004aa35`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004a814`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004aa35`
- `api-ms-win-service-management-l1-1-0!CreateServiceW` at `0x18004a7c8`
- `api-ms-win-service-management-l1-1-0!CreateServiceW` at `0x18004a7c8`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18004a861`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18004a8a4`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18004a8c5`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18004a8e5`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18004a95b`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18004a9df`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18004a861`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18004a8a4`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18004a8c5`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18004a8e5`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18004a95b`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18004a9df`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18004a93a`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18004a93a`
- `api-ms-win-service-management-l2-1-0!SetServiceObjectSecurity` at `0x18004aa5a`
- `api-ms-win-service-management-l2-1-0!SetServiceObjectSecurity` at `0x18004aa5a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004a6f9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004a6f9`

## string_xrefs

- `0x18004a6a0`: `SeAuditPrivilege`
- `0x18004a776`: `NT AUTHORITY\LocalService`
- `0x18004a78e`: `%SystemRoot%\system32\svchost.exe -k LocalService`
- `0x18004a782`: `@%SystemRoot%\system32\w32time.dll,-200`
- `0x18004a84d`: `@%SystemRoot%\system32\w32time.dll,-201`

## pseudocode

```c
__int64 __fastcall RegisterService(int a1, int a2)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  SC_HANDLE v6; // r14
  SC_HANDLE ServiceW; // rsi
  signed int v8; // eax
  signed int v9; // eax
  signed int v10; // eax
  signed int v11; // eax
  SC_HANDLE v12; // rax
  signed int v13; // eax
  int v15; // [rsp+70h] [rbp-90h] BYREF
  int v16; // [rsp+74h] [rbp-8Ch] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+78h] [rbp-88h] BYREF
  SC_HANDLE hSCObject; // [rsp+80h] [rbp-80h] BYREF
  __int128 v19; // [rsp+88h] [rbp-78h] BYREF
  const wchar_t *Info; // [rsp+98h] [rbp-68h] BYREF
  __int128 v21; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v22; // [rsp+B0h] [rbp-50h]
  _OWORD v23[2]; // [rsp+B8h] [rbp-48h] BYREF
  _DWORD *v24; // [rsp+D8h] [rbp-28h]
  int v25; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v26; // [rsp+E4h] [rbp-1Ch]
  __int128 v27; // [rsp+F4h] [rbp-Ch]
  _BYTE v28[28]; // [rsp+104h] [rbp+4h] BYREF
  __int64 v29; // [rsp+120h] [rbp+20h] BYREF
  _DWORD v30[3]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v31; // [rsp+134h] [rbp+34h]
  int v32; // [rsp+13Ch] [rbp+3Ch]

  v30[1] = 60000;
  v31 = 120000;
  v24 = 0;
  v22 = 0;
  memset((char *)&v19 + 4, 0, 12);
  Info = 0;
  hSCObject = (SC_HANDLE)L"SeAuditPrivilege";
  memset(v28, 0, sizeof(v28));
  v25 = 0;
  SecurityDescriptor = 0;
  LODWORD(v19) = 0;
  memset(v23, 0, sizeof(v23));
  v29 = 0;
  v30[0] = 1;
  v26 = 0;
  v30[2] = 1;
  v27 = 0;
  v32 = 0;
  v15 = 1;
  v21 = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;CCLCSWRPWPDTLOCRRC;;;SY)(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;BA)(A;;CCLCSWLOCRRC;;;IU)(A;;CCLCSWLOCRRC;;;SU)"
           "(A;;CCLCSWLOCRRCRP;;;LS)(A;;FRFX;;;LS)(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;S-1-5-80-3169285310-278349998-14523336"
           "86-3865143136-4212226833)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v6 = hSCObject;
    ServiceW = hSCObject;
    goto LABEL_26;
  }
  v6 = OpenSCManagerW(0, 0, 2u);
  if ( !v6 )
  {
    v8 = GetLastError();
    v5 = v8;
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
    goto LABEL_38;
  }
  ServiceW = CreateServiceW(
               v6,
               L"w32time",
               L"@%SystemRoot%\\system32\\w32time.dll,-200",
               0x12u,
               0x20u,
               3u,
               1u,
               L"%SystemRoot%\\system32\\svchost.exe -k LocalService",
               0,
               0,
               0,
               L"NT AUTHORITY\\LocalService",
               0);
  if ( !ServiceW )
  {
    v9 = GetLastError();
    v5 = v9;
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
    if ( v5 != -2147023823 )
      goto LABEL_37;
    ServiceW = OpenServiceW(v6, L"w32time", 0x12u);
    if ( !ServiceW )
      goto LABEL_13;
  }
  Info = L"@%SystemRoot%\\system32\\w32time.dll,-201";
  if ( !ChangeServiceConfig2W(ServiceW, 1u, &Info) )
    goto LABEL_24;
  *((_QWORD *)&v23[1] + 1) = 3;
  v24 = v30;
  LODWORD(v23[0]) = 86400;
  memset((char *)v23 + 4, 0, 20);
  if ( !ChangeServiceConfig2W(ServiceW, 2u, v23)
    || !ChangeServiceConfig2W(ServiceW, 5u, &v15)
    || !ChangeServiceConfig2W(ServiceW, 6u, &hSCObject) )
  {
    goto LABEL_24;
  }
  if ( a1 != 3 || a2 )
  {
    v16 = 1;
    if ( !ChangeServiceConfigW(ServiceW, 0xFFFFFFFF, 2u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0)
      || !ChangeServiceConfig2W(ServiceW, 3u, &v16) )
    {
      goto LABEL_24;
    }
  }
  v25 = 3;
  *(_QWORD *)((char *)&v26 + 4) = &DOMAIN_JOIN_GUID;
  LODWORD(v26) = 1;
  *((_QWORD *)&v19 + 1) = &v29;
  v29 = 0x48B0739A3BC1075LL;
  *(_QWORD *)&v28[4] = &CUSTOM_SYSTEM_STATE_CHANGE_EVENT_GUID;
  *(_QWORD *)&v28[20] = &v19;
  *((_QWORD *)&v21 + 1) = &v25;
  *(_QWORD *)&v19 = 0x800000001LL;
  HIDWORD(v27) = 7;
  *(_DWORD *)v28 = 1;
  *(_DWORD *)&v28[12] = 1;
  LODWORD(v21) = 2;
  v22 = 0;
  if ( !ChangeServiceConfig2W(ServiceW, 8u, &v21) )
  {
LABEL_24:
    v11 = GetLastError();
    v5 = v11;
    if ( v11 > 0 )
      v5 = (unsigned __int16)v11 | 0x80070000;
LABEL_26:
    if ( !ServiceW )
      goto LABEL_36;
    goto LABEL_35;
  }
  if ( ServiceW )
    CloseServiceHandle(ServiceW);
  v12 = OpenServiceW(v6, L"w32time", 0x40000u);
  ServiceW = v12;
  if ( !v12 )
  {
LABEL_13:
    v10 = GetLastError();
    v5 = v10;
    if ( v10 > 0 )
      v5 = (unsigned __int16)v10 | 0x80070000;
    goto LABEL_37;
  }
  if ( SetServiceObjectSecurity(v12, 4u, SecurityDescriptor) )
  {
    v5 = 0;
  }
  else
  {
    v13 = GetLastError();
    v5 = v13;
    if ( v13 > 0 )
      v5 = (unsigned __int16)v13 | 0x80070000;
  }
LABEL_35:
  CloseServiceHandle(ServiceW);
LABEL_36:
  if ( v6 )
LABEL_37:
    CloseServiceHandle(v6);
LABEL_38:
  LocalFree(SecurityDescriptor);
  return v5;
}

```

## disassembly

```asm
0x18004a648  push    rbp
0x18004a64a  push    rbx
0x18004a64b  push    rsi
0x18004a64c  push    rdi
0x18004a64d  push    r12
0x18004a64f  push    r13
0x18004a651  push    r14
0x18004a653  push    r15
0x18004a655  lea     rbp, [rsp-58h]
0x18004a65a  sub     rsp, 158h
0x18004a661  mov     rax, cs:__security_cookie
0x18004a668  xor     rax, rsp
0x18004a66b  mov     [rbp+90h+var_50], rax
0x18004a66f  xorps   xmm0, xmm0
0x18004a672  mov     [rbp+90h+var_64], 0EA60h
0x18004a679  xor     eax, eax
0x18004a67b  mov     [rbp+90h+var_5C], 1D4C0h
0x18004a683  xor     r13d, r13d
0x18004a686  mov     [rbp+90h+var_B8], rax
0x18004a68a  mov     [rbp+90h+var_E0], rax
0x18004a68e  lea     r8, [rsp+190h+SecurityDescriptor]; SecurityDescriptor
0x18004a693  mov     [rbp+90h+var_104], rax
0x18004a697  mov     r12d, edx
0x18004a69a  lea     ebx, [rax+1]
0x18004a69d  mov     [rbp+90h+var_FC], eax
0x18004a6a0  lea     rax, aSeauditprivile; "SeAuditPrivilege"
0x18004a6a7  mov     [rbp+90h+Info], r13
0x18004a6ab  mov     r15d, ecx
0x18004a6ae  mov     [rbp+90h+hSCObject], rax
0x18004a6b2  movups  [rbp+90h+var_8C], xmm0
0x18004a6b6  mov     edx, ebx; StringSDRevision
0x18004a6b8  mov     [rbp+90h+var_B0], r13d
0x18004a6bc  xor     r9d, r9d; SecurityDescriptorSize
0x18004a6bf  mov     [rsp+190h+SecurityDescriptor], r13
0x18004a6c4  lea     rcx, StringSecurityDescriptor; "D:(A;;CCLCSWRPWPDTLOCRRC;;;SY)(A;;CCDCL"...
0x18004a6cb  mov     [rbp+90h+var_108], r13d
0x18004a6cf  movups  [rbp+90h+var_D8], xmm0
0x18004a6d3  mov     [rbp+90h+var_70], r13
0x18004a6d7  movups  [rbp+90h+var_C8], xmm0
0x18004a6db  mov     [rbp+90h+var_68], ebx
0x18004a6de  movups  [rbp+90h+var_AC], xmm0
0x18004a6e2  mov     [rbp+90h+var_60], ebx
0x18004a6e5  movups  [rbp+90h+var_9C], xmm0
0x18004a6e9  mov     [rbp+90h+var_54], r13d
0x18004a6ed  movups  [rbp+90h+var_8C+0Ch], xmm0
0x18004a6f1  mov     [rsp+190h+var_120], ebx
0x18004a6f5  movups  [rbp+90h+var_F0], xmm0
0x18004a6f9  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004a700  nop     dword ptr [rax+rax+00h]
0x18004a705  test    eax, eax
0x18004a707  jnz     short loc_18004A731
0x18004a709  call    cs:__imp_GetLastError
0x18004a710  nop     dword ptr [rax+rax+00h]
0x18004a715  mov     ebx, eax
0x18004a717  test    eax, eax
0x18004a719  jle     short loc_18004A724
0x18004a71b  movzx   ebx, ax
0x18004a71e  or      ebx, 80070000h
0x18004a724  mov     r14, [rbp+90h+hSCObject]
0x18004a728  mov     rsi, [rbp+90h+hSCObject]
0x18004a72c  jmp     loc_18004AA06
0x18004a731  xor     edx, edx; lpDatabaseName
0x18004a733  xor     ecx, ecx; lpMachineName
0x18004a735  lea     r8d, [rdx+2]; dwDesiredAccess
0x18004a739  call    cs:__imp_OpenSCManagerW
0x18004a740  nop     dword ptr [rax+rax+00h]
0x18004a745  mov     r14, rax
0x18004a748  test    rax, rax
0x18004a74b  jnz     short loc_18004A771
0x18004a74d  call    cs:__imp_GetLastError
0x18004a754  nop     dword ptr [rax+rax+00h]
0x18004a759  mov     ebx, eax
0x18004a75b  test    eax, eax
0x18004a75d  jle     loc_18004AAA9
0x18004a763  movzx   ebx, ax
0x18004a766  or      ebx, 80070000h
0x18004a76c  jmp     loc_18004AAA9
0x18004a771  mov     [rsp+190h+lpPassword], r13; lpPassword
0x18004a776  lea     rax, ServiceStartName; "NT AUTHORITY\\LocalService"
0x18004a77d  mov     [rsp+190h+lpServiceStartName], rax; lpServiceStartName
0x18004a782  lea     r8, DisplayName; "@%SystemRoot%\\system32\\w32time.dll,-2"...
0x18004a789  mov     [rsp+190h+lpDependencies], r13; lpDependencies
0x18004a78e  lea     rax, BinaryPathName; "%SystemRoot%\\system32\\svchost.exe -k "...
0x18004a795  mov     [rsp+190h+lpdwTagId], r13; lpdwTagId
0x18004a79a  lea     rdx, ModuleName; "w32time"
0x18004a7a1  mov     [rsp+190h+lpLoadOrderGroup], r13; lpLoadOrderGroup
0x18004a7a6  mov     r9d, 12h; dwDesiredAccess
0x18004a7ac  mov     [rsp+190h+lpBinaryPathName], rax; lpBinaryPathName
0x18004a7b1  mov     rcx, r14; hSCManager
0x18004a7b4  mov     [rsp+190h+dwErrorControl], ebx; dwErrorControl
0x18004a7b8  mov     [rsp+190h+dwStartType], 3; dwStartType
0x18004a7c0  mov     [rsp+190h+dwServiceType], 20h ; ' '; dwServiceType
0x18004a7c8  call    cs:__imp_CreateServiceW
0x18004a7cf  nop     dword ptr [rax+rax+00h]
0x18004a7d4  mov     rsi, rax
0x18004a7d7  mov     edi, 80070000h
0x18004a7dc  test    rax, rax
0x18004a7df  jnz     short loc_18004A84D
0x18004a7e1  call    cs:__imp_GetLastError
0x18004a7e8  nop     dword ptr [rax+rax+00h]
0x18004a7ed  mov     ebx, eax
0x18004a7ef  test    eax, eax
0x18004a7f1  jle     short loc_18004A7F8
0x18004a7f3  movzx   ebx, ax
0x18004a7f6  or      ebx, edi
0x18004a7f8  cmp     ebx, 80070431h
0x18004a7fe  jnz     loc_18004AA9A
0x18004a804  mov     r8d, 12h; dwDesiredAccess
0x18004a80a  lea     rdx, ModuleName; "w32time"
0x18004a811  mov     rcx, r14; hSCManager
0x18004a814  call    cs:__imp_OpenServiceW
0x18004a81b  nop     dword ptr [rax+rax+00h]
0x18004a820  mov     rsi, rax
0x18004a823  test    rax, rax
0x18004a826  jnz     short loc_18004A848
0x18004a828  call    cs:__imp_GetLastError
0x18004a82f  nop     dword ptr [rax+rax+00h]
0x18004a834  mov     ebx, eax
0x18004a836  test    eax, eax
0x18004a838  jle     loc_18004AA9A
0x18004a83e  movzx   ebx, ax
0x18004a841  or      ebx, edi
0x18004a843  jmp     loc_18004AA9A
0x18004a848  mov     ebx, 1
0x18004a84d  lea     rax, aSystemrootSyst_1; "@%SystemRoot%\\system32\\w32time.dll,-2"...
0x18004a854  mov     edx, ebx; dwInfoLevel
0x18004a856  lea     r8, [rbp+90h+Info]; lpInfo
0x18004a85a  mov     [rbp+90h+Info], rax
0x18004a85e  mov     rcx, rsi; hService
0x18004a861  call    cs:__imp_ChangeServiceConfig2W
0x18004a868  nop     dword ptr [rax+rax+00h]
0x18004a86d  test    eax, eax
0x18004a86f  jz      loc_18004A9EF
0x18004a875  xorps   xmm0, xmm0
0x18004a878  mov     dword ptr [rbp+90h+var_C8+4], r13d
0x18004a87c  lea     rax, [rbp+90h+var_68]
0x18004a880  mov     qword ptr [rbp+90h+var_C8+8], 3
0x18004a888  lea     r8, [rbp+90h+var_D8]; lpInfo
0x18004a88c  mov     [rbp+90h+var_B8], rax
0x18004a890  mov     edx, 2; dwInfoLevel
0x18004a895  mov     dword ptr [rbp+90h+var_D8], 15180h
0x18004a89c  mov     rcx, rsi; hService
0x18004a89f  movdqu  [rbp+90h+var_D8+4], xmm0
0x18004a8a4  call    cs:__imp_ChangeServiceConfig2W
0x18004a8ab  nop     dword ptr [rax+rax+00h]
0x18004a8b0  test    eax, eax
0x18004a8b2  jz      loc_18004A9EF
0x18004a8b8  lea     r8, [rsp+190h+var_120]; lpInfo
0x18004a8bd  mov     edx, 5; dwInfoLevel
0x18004a8c2  mov     rcx, rsi; hService
0x18004a8c5  call    cs:__imp_ChangeServiceConfig2W
0x18004a8cc  nop     dword ptr [rax+rax+00h]
0x18004a8d1  test    eax, eax
0x18004a8d3  jz      loc_18004A9EF
0x18004a8d9  lea     r8, [rbp+90h+hSCObject]; lpInfo
0x18004a8dd  mov     edx, 6; dwInfoLevel
0x18004a8e2  mov     rcx, rsi; hService
0x18004a8e5  call    cs:__imp_ChangeServiceConfig2W
0x18004a8ec  nop     dword ptr [rax+rax+00h]
0x18004a8f1  test    eax, eax
0x18004a8f3  jz      loc_18004A9EF
0x18004a8f9  cmp     r15d, 3
0x18004a8fd  jnz     short loc_18004A904
0x18004a8ff  test    r12d, r12d
0x18004a902  jz      short loc_18004A96F
0x18004a904  mov     [rsp+190h+lpDependencies], r13; lpDisplayName
0x18004a909  or      edx, 0FFFFFFFFh; dwServiceType
0x18004a90c  mov     [rsp+190h+lpdwTagId], r13; lpPassword
0x18004a911  mov     r9d, edx; dwErrorControl
0x18004a914  mov     [rsp+190h+lpLoadOrderGroup], r13; lpServiceStartName
0x18004a919  mov     r8d, 2; dwStartType
0x18004a91f  mov     [rsp+190h+lpBinaryPathName], r13; lpDependencies
0x18004a924  mov     rcx, rsi; hService
0x18004a927  mov     qword ptr [rsp+190h+dwErrorControl], r13; lpdwTagId
0x18004a92c  mov     qword ptr [rsp+190h+dwStartType], r13; lpLoadOrderGroup
0x18004a931  mov     qword ptr [rsp+190h+dwServiceType], r13; lpBinaryPathName
0x18004a936  mov     [rsp+190h+var_11C], ebx
0x18004a93a  call    cs:__imp_ChangeServiceConfigW
0x18004a941  nop     dword ptr [rax+rax+00h]
0x18004a946  test    eax, eax
0x18004a948  jz      loc_18004A9EF
0x18004a94e  lea     r8, [rsp+190h+var_11C]; lpInfo
0x18004a953  mov     edx, 3; dwInfoLevel
0x18004a958  mov     rcx, rsi; hService
0x18004a95b  call    cs:__imp_ChangeServiceConfig2W
0x18004a962  nop     dword ptr [rax+rax+00h]
0x18004a967  test    eax, eax
0x18004a969  jz      loc_18004A9EF
0x18004a96f  lea     rax, DOMAIN_JOIN_GUID
0x18004a976  mov     [rbp+90h+var_B0], 3
0x18004a97d  mov     qword ptr [rbp+90h+var_AC+4], rax
0x18004a981  lea     r8, [rbp+90h+var_F0]; lpInfo
0x18004a985  lea     rax, [rbp+90h+var_70]
0x18004a989  mov     dword ptr [rbp+90h+var_AC], ebx
0x18004a98c  mov     [rbp+90h+var_104+4], rax
0x18004a990  mov     edx, 8; dwInfoLevel
0x18004a995  lea     rax, CUSTOM_SYSTEM_STATE_CHANGE_EVENT_GUID
0x18004a99c  mov     dword ptr [rbp+90h+var_70], 0A3BC1075h
0x18004a9a3  mov     qword ptr [rbp+90h+var_8C+4], rax
0x18004a9a7  mov     rcx, rsi; hService
0x18004a9aa  lea     rax, [rbp+90h+var_108]
0x18004a9ae  mov     dword ptr [rbp+90h+var_70+4], 48B0739h
0x18004a9b5  mov     [rbp+90h+var_78], rax
0x18004a9b9  lea     rax, [rbp+90h+var_B0]
0x18004a9bd  mov     qword ptr [rbp+90h+var_F0+8], rax
0x18004a9c1  mov     [rbp+90h+var_108], ebx
0x18004a9c4  mov     dword ptr [rbp+90h+var_104], edx
0x18004a9c7  mov     dword ptr [rbp+90h+var_9C+0Ch], 7
0x18004a9ce  mov     dword ptr [rbp+90h+var_8C], ebx
0x18004a9d1  mov     dword ptr [rbp+90h+var_8C+0Ch], ebx
0x18004a9d4  mov     dword ptr [rbp+90h+var_F0], 2
0x18004a9db  mov     [rbp+90h+var_E0], r13
0x18004a9df  call    cs:__imp_ChangeServiceConfig2W
0x18004a9e6  nop     dword ptr [rax+rax+00h]
0x18004a9eb  test    eax, eax
0x18004a9ed  jnz     short loc_18004AA11
0x18004a9ef  call    cs:__imp_GetLastError
0x18004a9f6  nop     dword ptr [rax+rax+00h]
0x18004a9fb  mov     ebx, eax
0x18004a9fd  test    eax, eax
0x18004a9ff  jle     short loc_18004AA06
0x18004aa01  movzx   ebx, ax
0x18004aa04  or      ebx, edi
0x18004aa06  test    rsi, rsi
0x18004aa09  jz      loc_18004AA95
0x18004aa0f  jmp     short loc_18004AA86
0x18004aa11  test    rsi, rsi
0x18004aa14  jz      short loc_18004AA25
0x18004aa16  mov     rcx, rsi; hSCObject
0x18004aa19  call    cs:__imp_CloseServiceHandle
0x18004aa20  nop     dword ptr [rax+rax+00h]
0x18004aa25  mov     r8d, 40000h; dwDesiredAccess
0x18004aa2b  lea     rdx, ModuleName; "w32time"
0x18004aa32  mov     rcx, r14; hSCManager
0x18004aa35  call    cs:__imp_OpenServiceW
0x18004aa3c  nop     dword ptr [rax+rax+00h]
0x18004aa41  mov     rsi, rax
0x18004aa44  test    rax, rax
0x18004aa47  jz      loc_18004A828
0x18004aa4d  mov     r8, [rsp+190h+SecurityDescriptor]; lpSecurityDescriptor
0x18004aa52  mov     edx, 4; dwSecurityInformation
0x18004aa57  mov     rcx, rax; hService
0x18004aa5a  call    cs:__imp_SetServiceObjectSecurity
0x18004aa61  nop     dword ptr [rax+rax+00h]
0x18004aa66  test    eax, eax
0x18004aa68  jnz     short loc_18004AA83
0x18004aa6a  call    cs:__imp_GetLastError
0x18004aa71  nop     dword ptr [rax+rax+00h]
0x18004aa76  mov     ebx, eax
0x18004aa78  test    eax, eax
0x18004aa7a  jle     short loc_18004AA86
0x18004aa7c  movzx   ebx, ax
0x18004aa7f  or      ebx, edi
0x18004aa81  jmp     short loc_18004AA86
0x18004aa83  mov     ebx, r13d
0x18004aa86  mov     rcx, rsi; hSCObject
0x18004aa89  call    cs:__imp_CloseServiceHandle
0x18004aa90  nop     dword ptr [rax+rax+00h]
0x18004aa95  test    r14, r14
0x18004aa98  jz      short loc_18004AAA9
0x18004aa9a  mov     rcx, r14; hSCObject
0x18004aa9d  call    cs:__imp_CloseServiceHandle
0x18004aaa4  nop     dword ptr [rax+rax+00h]
0x18004aaa9  mov     rcx, [rsp+190h+SecurityDescriptor]; hMem
0x18004aaae  call    cs:__imp_LocalFree
0x18004aab5  nop     dword ptr [rax+rax+00h]
0x18004aaba  mov     eax, ebx
0x18004aabc  mov     rcx, [rbp+90h+var_50]
0x18004aac0  xor     rcx, rsp; StackCookie
0x18004aac3  call    __security_check_cookie
0x18004aac8  add     rsp, 158h
0x18004aacf  pop     r15
0x18004aad1  pop     r14
0x18004aad3  pop     r13
0x18004aad5  pop     r12
0x18004aad7  pop     rdi
0x18004aad8  pop     rsi
0x18004aad9  pop     rbx
0x18004aada  pop     rbp
0x18004aadb  retn
```
