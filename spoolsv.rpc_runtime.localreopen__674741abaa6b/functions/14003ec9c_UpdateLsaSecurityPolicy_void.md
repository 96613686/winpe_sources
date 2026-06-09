# UpdateLsaSecurityPolicy(void *)

- ea: `0x14003ec9c`
- end: `0x14003edaf`
- name: `?UpdateLsaSecurityPolicy@@YAJPEAX@Z`
- size: `275`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14003e46c`

## callees

- `0x14001748c`
- `0x14003ec9c`

## import_xrefs

- `ADVAPI32!LsaClose` at `0x14003ed93`
- `ADVAPI32!LsaClose` at `0x14003ed93`
- `ADVAPI32!LsaAddAccountRights` at `0x14003ed59`
- `ADVAPI32!LsaAddAccountRights` at `0x14003ed59`
- `ADVAPI32!LsaOpenPolicy` at `0x14003ecdd`
- `ADVAPI32!LsaOpenPolicy` at `0x14003ecdd`

## string_xrefs

- `0x14003ecf2`: `Failed to open LSA security policy for local machine %d`
- `0x14003ecf9`: `UpdateLsaSecurityPolicy`
- `0x14003ed7e`: `UpdateLsaSecurityPolicy`
- `0x14003ed74`: `Failed to add %ws to spooler worker service account %d`

## pseudocode

```c
__int64 __fastcall UpdateLsaSecurityPolicy(void *a1)
{
  NTSTATUS v1; // eax
  unsigned int v2; // ebx
  unsigned int i; // edi
  __int64 v4; // rax
  NTSTATUS v5; // eax
  struct _LSA_UNICODE_STRING UserRights; // [rsp+20h] [rbp-48h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-38h] BYREF
  PVOID PolicyHandle; // [rsp+A0h] [rbp+38h] BYREF

  PolicyHandle = 0;
  UserRights = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v1 = LsaOpenPolicy(0, &ObjectAttributes, 0x800u, &PolicyHandle);
  v2 = v1;
  if ( v1 >= 0 )
  {
    for ( i = 0; i < 3; ++i )
    {
      v4 = -1;
      do
        ++v4;
      while ( *((_WORD *)*(&g_aRequiredPrivileges + 2 * i + 1) + v4) );
      UserRights.Buffer = (PWSTR)*(&g_aRequiredPrivileges + 2 * i + 1);
      UserRights.Length = 2 * v4;
      UserRights.MaximumLength = 2 * v4 + 2;
      v5 = LsaAddAccountRights(PolicyHandle, &g_abSpoolerServiceSidBuffer, &UserRights, 1u);
      v2 = v5;
      if ( v5 < 0 )
      {
        SpoolerServiceTelemetry::WriteDbgTraceError(
          "UpdateLsaSecurityPolicy",
          L"Failed to add %ws to spooler worker service account %d",
          *(&g_aRequiredPrivileges + 2 * i + 1),
          (unsigned int)v5);
        break;
      }
    }
  }
  else
  {
    SpoolerServiceTelemetry::WriteDbgTraceError(
      "UpdateLsaSecurityPolicy",
      L"Failed to open LSA security policy for local machine %d",
      (unsigned int)v1);
  }
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return v2;
}

```

## disassembly

```asm
0x14003ec9c  mov     [rsp-30h+PolicyHandle], rcx
0x14003eca1  push    rbp
0x14003eca2  push    rbx
0x14003eca3  push    rsi
0x14003eca4  push    rdi
0x14003eca5  push    r14
0x14003eca7  push    r15
0x14003eca9  mov     rbp, rsp
0x14003ecac  sub     rsp, 68h
0x14003ecb0  xorps   xmm1, xmm1
0x14003ecb3  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x14003ecb7  xorps   xmm0, xmm0
0x14003ecba  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x14003ecbe  xor     r14d, r14d
0x14003ecc1  mov     r8d, 800h; DesiredAccess
0x14003ecc7  xor     ecx, ecx; SystemName
0x14003ecc9  mov     [rbp+PolicyHandle], r14
0x14003eccd  movups  xmmword ptr [rbp+UserRights.Length], xmm0
0x14003ecd1  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x14003ecd5  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x14003ecd9  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x14003ecdd  call    cs:__imp_LsaOpenPolicy
0x14003ece4  nop     dword ptr [rax+rax+00h]
0x14003ece9  mov     ebx, eax
0x14003eceb  test    eax, eax
0x14003eced  jns     short loc_14003ED0A
0x14003ecef  mov     r8d, eax
0x14003ecf2  lea     rdx, aFailedToOpenLs; "Failed to open LSA security policy for "...
0x14003ecf9  lea     rcx, aUpdatelsasecur; "UpdateLsaSecurityPolicy"
0x14003ed00  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003ed05  jmp     loc_14003ED8A
0x14003ed0a  mov     edi, r14d
0x14003ed0d  lea     r15, ?g_aRequiredPrivileges@@3PAUSE_PRIVILEGE_INFO@@A; SE_PRIVILEGE_INFO near * g_aRequiredPrivileges
0x14003ed14  cmp     edi, 3
0x14003ed17  jnb     short loc_14003ED8A
0x14003ed19  mov     esi, edi
0x14003ed1b  add     rsi, rsi
0x14003ed1e  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003ed22  mov     rcx, [r15+rsi*8+8]
0x14003ed27  inc     rax
0x14003ed2a  cmp     [rcx+rax*2], r14w
0x14003ed2f  jnz     short loc_14003ED27
0x14003ed31  add     ax, ax
0x14003ed34  mov     [rbp+UserRights.Buffer], rcx
0x14003ed38  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x14003ed3c  lea     r8, [rbp+UserRights]; UserRights
0x14003ed40  mov     [rbp+UserRights.Length], ax
0x14003ed44  lea     rdx, ?g_abSpoolerServiceSidBuffer@@3PAEA; AccountSid
0x14003ed4b  add     ax, 2
0x14003ed4f  mov     r9d, 1; CountOfRights
0x14003ed55  mov     [rbp+UserRights.MaximumLength], ax
0x14003ed59  call    cs:__imp_LsaAddAccountRights
0x14003ed60  nop     dword ptr [rax+rax+00h]
0x14003ed65  mov     ebx, eax
0x14003ed67  test    eax, eax
0x14003ed69  js      short loc_14003ED6F
0x14003ed6b  inc     edi
0x14003ed6d  jmp     short loc_14003ED14
0x14003ed6f  mov     r8, [r15+rsi*8+8]
0x14003ed74  lea     rdx, aFailedToAddWsT; "Failed to add %ws to spooler worker ser"...
0x14003ed7b  mov     r9d, eax
0x14003ed7e  lea     rcx, aUpdatelsasecur; "UpdateLsaSecurityPolicy"
0x14003ed85  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003ed8a  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x14003ed8e  test    rcx, rcx
0x14003ed91  jz      short loc_14003ED9F
0x14003ed93  call    cs:__imp_LsaClose
0x14003ed9a  nop     dword ptr [rax+rax+00h]
0x14003ed9f  mov     eax, ebx
0x14003eda1  add     rsp, 68h
0x14003eda5  pop     r15
0x14003eda7  pop     r14
0x14003eda9  pop     rdi
0x14003edaa  pop     rsi
0x14003edab  pop     rbx
0x14003edac  pop     rbp
0x14003edad  retn
```
