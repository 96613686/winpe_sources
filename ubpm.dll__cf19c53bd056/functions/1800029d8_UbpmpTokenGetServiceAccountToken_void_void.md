# UbpmpTokenGetServiceAccountToken(void *,void * *)

- ea: `0x1800029d8`
- end: `0x180002ab4`
- name: `?UbpmpTokenGetServiceAccountToken@@YAKPEAXPEAPEAX@Z`
- size: `220`
- prototype: `__int64 __fastcall(void *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x180001fb0`

## callees

- `0x1800029d8`
- `0x180004240`
- `0x180019d90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a2d`
- `api-ms-win-service-private-l1-2-0!GetServiceProcessToken` at `0x180002a62`
- `api-ms-win-service-private-l1-2-0!GetServiceProcessToken` at `0x180002a62`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180002a1f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180002a1f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180002a90`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180002a9e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180002a90`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180002a9e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180002a45`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180002a45`

## pseudocode

```c
__int64 __fastcall UbpmpTokenGetServiceAccountToken(void *a1, void **a2)
{
  SC_HANDLE v2; // rsi
  SC_HANDLE v4; // rdi
  DWORD AccountNamesFromSid; // ebx
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rax
  LPCWSTR lpServiceName; // [rsp+60h] [rbp+18h] BYREF
  void *v10; // [rsp+68h] [rbp+20h] BYREF

  v2 = 0;
  v10 = 0;
  lpServiceName = 0;
  v4 = 0;
  AccountNamesFromSid = UbpmUtilsGetAccountNamesFromSid((_DWORD)a1, 5, 0, (unsigned int)&lpServiceName, 0);
  if ( !AccountNamesFromSid )
  {
    v6 = OpenSCManagerW(0, 0, 1u);
    v2 = v6;
    if ( v6 && (v7 = OpenServiceW(v6, lpServiceName, 0xF01FFu), (v4 = v7) != 0) )
    {
      AccountNamesFromSid = GetServiceProcessToken(g_ScheduleServiceHandle, v7, &v10);
      if ( !AccountNamesFromSid )
        *a2 = v10;
    }
    else
    {
      AccountNamesFromSid = GetLastError();
    }
  }
  if ( lpServiceName )
    UBPM_MIDL_user_free(lpServiceName);
  if ( v2 )
    CloseServiceHandle(v2);
  if ( v4 )
    CloseServiceHandle(v4);
  return AccountNamesFromSid;
}

```

## disassembly

```asm
0x1800029d8  mov     rax, rsp
0x1800029db  mov     [rax+8], rbx
0x1800029df  push    rsi
0x1800029e0  push    rdi
0x1800029e1  push    r14
0x1800029e3  sub     rsp, 30h
0x1800029e7  xor     esi, esi
0x1800029e9  mov     qword ptr [rax+20h], 0
0x1800029f1  mov     r14, rdx
0x1800029f4  mov     qword ptr [rax+18h], 0
0x1800029fc  lea     r9, [rax+18h]
0x180002a00  mov     [rax-28h], rsi
0x180002a04  xor     r8d, r8d
0x180002a07  xor     edi, edi
0x180002a09  lea     edx, [rsi+5]
0x180002a0c  call    UbpmUtilsGetAccountNamesFromSid
0x180002a11  mov     ebx, eax
0x180002a13  test    eax, eax
0x180002a15  jnz     short loc_180002A76
0x180002a17  xor     edx, edx; lpDatabaseName
0x180002a19  lea     r8d, [rsi+1]; dwDesiredAccess
0x180002a1d  xor     ecx, ecx; lpMachineName
0x180002a1f  call    cs:__imp_OpenSCManagerW
0x180002a25  mov     rsi, rax
0x180002a28  test    rax, rax
0x180002a2b  jnz     short loc_180002A37
0x180002a2d  call    cs:__imp_GetLastError
0x180002a33  mov     ebx, eax
0x180002a35  jmp     short loc_180002A76
0x180002a37  mov     rdx, [rsp+48h+lpServiceName]; lpServiceName
0x180002a3c  mov     r8d, 0F01FFh; dwDesiredAccess
0x180002a42  mov     rcx, rax; hSCManager
0x180002a45  call    cs:__imp_OpenServiceW
0x180002a4b  mov     rdi, rax
0x180002a4e  test    rax, rax
0x180002a51  jz      short loc_180002A2D
0x180002a53  mov     rcx, cs:g_ScheduleServiceHandle
0x180002a5a  lea     r8, [rsp+48h+arg_18]
0x180002a5f  mov     rdx, rax
0x180002a62  call    cs:__imp_GetServiceProcessToken
0x180002a68  mov     ebx, eax
0x180002a6a  test    eax, eax
0x180002a6c  jnz     short loc_180002A76
0x180002a6e  mov     rax, [rsp+48h+arg_18]
0x180002a73  mov     [r14], rax
0x180002a76  cmp     [rsp+48h+lpServiceName], 0
0x180002a7c  jz      short loc_180002A88
0x180002a7e  mov     rcx, [rsp+48h+lpServiceName]
0x180002a83  call    UBPM_MIDL_user_free
0x180002a88  test    rsi, rsi
0x180002a8b  jz      short loc_180002A96
0x180002a8d  mov     rcx, rsi; hSCObject
0x180002a90  call    cs:__imp_CloseServiceHandle
0x180002a96  test    rdi, rdi
0x180002a99  jz      short loc_180002AA4
0x180002a9b  mov     rcx, rdi; hSCObject
0x180002a9e  call    cs:__imp_CloseServiceHandle
0x180002aa4  mov     eax, ebx
0x180002aa6  mov     rbx, [rsp+48h+arg_0]
0x180002aab  add     rsp, 30h
0x180002aaf  pop     r14
0x180002ab1  pop     rdi
0x180002ab2  pop     rsi
0x180002ab3  retn
```
