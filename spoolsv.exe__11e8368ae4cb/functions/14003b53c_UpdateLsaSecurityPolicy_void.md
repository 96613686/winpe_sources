# UpdateLsaSecurityPolicy(void *)

- ea: `0x14003b53c`
- end: `0x14003b639`
- name: `?UpdateLsaSecurityPolicy@@YAJPEAX@Z`
- size: `253`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14003ae08`

## callees

- `0x1400160a0`
- `0x14003b53c`

## import_xrefs

- `ADVAPI32!LsaClose` at `0x14003b624`
- `ADVAPI32!LsaClose` at `0x14003b624`
- `ADVAPI32!LsaAddAccountRights` at `0x14003b5f0`
- `ADVAPI32!LsaAddAccountRights` at `0x14003b5f0`
- `ADVAPI32!LsaOpenPolicy` at `0x14003b57d`
- `ADVAPI32!LsaOpenPolicy` at `0x14003b57d`

## string_xrefs

- `0x14003b58c`: `Failed to open LSA security policy for local machine %d`
- `0x14003b593`: `UpdateLsaSecurityPolicy`
- `0x14003b60f`: `UpdateLsaSecurityPolicy`
- `0x14003b605`: `Failed to add %ws to spooler worker service account %d`

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
0x14003b53c  mov     [rsp-30h+PolicyHandle], rcx
0x14003b541  push    rbp
0x14003b542  push    rbx
0x14003b543  push    rsi
0x14003b544  push    rdi
0x14003b545  push    r14
0x14003b547  push    r15
0x14003b549  mov     rbp, rsp
0x14003b54c  sub     rsp, 68h
0x14003b550  xorps   xmm1, xmm1
0x14003b553  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x14003b557  xorps   xmm0, xmm0
0x14003b55a  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x14003b55e  xor     r14d, r14d
0x14003b561  mov     r8d, 800h; DesiredAccess
0x14003b567  xor     ecx, ecx; SystemName
0x14003b569  mov     [rbp+PolicyHandle], r14
0x14003b56d  movups  xmmword ptr [rbp+UserRights.Length], xmm0
0x14003b571  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x14003b575  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x14003b579  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x14003b57d  call    cs:__imp_LsaOpenPolicy
0x14003b583  mov     ebx, eax
0x14003b585  test    eax, eax
0x14003b587  jns     short loc_14003B5A1
0x14003b589  mov     r8d, eax
0x14003b58c  lea     rdx, aFailedToOpenLs; "Failed to open LSA security policy for "...
0x14003b593  lea     rcx, aUpdatelsasecur; "UpdateLsaSecurityPolicy"
0x14003b59a  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003b59f  jmp     short loc_14003B61B
0x14003b5a1  mov     edi, r14d
0x14003b5a4  lea     r15, ?g_aRequiredPrivileges@@3PAUSE_PRIVILEGE_INFO@@A; SE_PRIVILEGE_INFO near * g_aRequiredPrivileges
0x14003b5ab  cmp     edi, 3
0x14003b5ae  jnb     short loc_14003B61B
0x14003b5b0  mov     esi, edi
0x14003b5b2  add     rsi, rsi
0x14003b5b5  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003b5b9  mov     rcx, [r15+rsi*8+8]
0x14003b5be  inc     rax
0x14003b5c1  cmp     [rcx+rax*2], r14w
0x14003b5c6  jnz     short loc_14003B5BE
0x14003b5c8  add     ax, ax
0x14003b5cb  mov     [rbp+UserRights.Buffer], rcx
0x14003b5cf  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x14003b5d3  lea     r8, [rbp+UserRights]; UserRights
0x14003b5d7  mov     [rbp+UserRights.Length], ax
0x14003b5db  lea     rdx, ?g_abSpoolerServiceSidBuffer@@3PAEA; AccountSid
0x14003b5e2  add     ax, 2
0x14003b5e6  mov     r9d, 1; CountOfRights
0x14003b5ec  mov     [rbp+UserRights.MaximumLength], ax
0x14003b5f0  call    cs:__imp_LsaAddAccountRights
0x14003b5f6  mov     ebx, eax
0x14003b5f8  test    eax, eax
0x14003b5fa  js      short loc_14003B600
0x14003b5fc  inc     edi
0x14003b5fe  jmp     short loc_14003B5AB
0x14003b600  mov     r8, [r15+rsi*8+8]
0x14003b605  lea     rdx, aFailedToAddWsT; "Failed to add %ws to spooler worker ser"...
0x14003b60c  mov     r9d, eax
0x14003b60f  lea     rcx, aUpdatelsasecur; "UpdateLsaSecurityPolicy"
0x14003b616  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003b61b  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x14003b61f  test    rcx, rcx
0x14003b622  jz      short loc_14003B62A
0x14003b624  call    cs:__imp_LsaClose
0x14003b62a  mov     eax, ebx
0x14003b62c  add     rsp, 68h
0x14003b630  pop     r15
0x14003b632  pop     r14
0x14003b634  pop     rdi
0x14003b635  pop     rsi
0x14003b636  pop     rbx
0x14003b637  pop     rbp
0x14003b638  retn
```
