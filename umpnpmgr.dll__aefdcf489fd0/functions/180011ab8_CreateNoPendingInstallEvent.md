# CreateNoPendingInstallEvent

- ea: `0x180011ab8`
- end: `0x180011c83`
- name: `CreateNoPendingInstallEvent`
- size: `459`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180012dac`

## callees

- `0x1800010e0`
- `0x180011ab8`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180011c5c`
- `ntdll!RtlFreeHeap` at `0x180011c5c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011c38`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011c38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011c64`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011c64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b51`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180011af4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180011b07`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180011b1a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180011af4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180011b07`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180011b1a`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180011b47`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180011b47`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180011b7e`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180011baa`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180011bd1`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180011b7e`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180011baa`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180011bd1`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180011bea`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180011bea`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180011c04`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180011c04`

## string_xrefs

- `0x180011c1d`: `Global\PnP_No_Pending_Install_Events`

## pseudocode

```c
_BOOL8 CreateNoPendingInstallEvent()
{
  void *v0; // rcx
  DWORD LengthSid; // ebx
  DWORD v2; // ebx
  DWORD v3; // ebx
  struct _ACL *v4; // rax
  struct _ACL *v5; // rdi
  DWORD LastError; // ebx
  HANDLE v7; // rax
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+30h] [rbp-40h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v11; // [rsp+68h] [rbp-8h]

  PnpNoPendingInstallEvents = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v11 = 0;
  v0 = *(void **)(PnpSvchostGlobalData + 32);
  memset(&EventAttributes, 0, 20);
  LengthSid = GetLengthSid(v0);
  v2 = GetLengthSid(*(PSID *)(PnpSvchostGlobalData + 80)) + LengthSid;
  v3 = GetLengthSid(*(PSID *)(PnpSvchostGlobalData + 88)) + 32 + v2;
  v4 = (struct _ACL *)PnpHeapAlloc(v3);
  v5 = v4;
  if ( v4 )
  {
    if ( InitializeAcl(v4, v3, 2u)
      && AddAccessAllowedAceEx(v5, 2u, 0, 0x1F0003u, *(PSID *)(PnpSvchostGlobalData + 32))
      && AddAccessAllowedAceEx(v5, 2u, 0, 0x100001u, *(PSID *)(PnpSvchostGlobalData + 80))
      && AddAccessAllowedAceEx(v5, 2u, 0, 0x100001u, *(PSID *)(PnpSvchostGlobalData + 88))
      && InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
      && SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v5, 0)
      && (EventAttributes.nLength = 24,
          EventAttributes.lpSecurityDescriptor = pSecurityDescriptor,
          EventAttributes.bInheritHandle = 0,
          (v7 = CreateEventW(&EventAttributes, 1, 0, L"Global\\PnP_No_Pending_Install_Events")) != 0) )
    {
      LastError = 0;
      PnpNoPendingInstallEvents = v7;
    }
    else
    {
      LastError = GetLastError();
    }
    RtlFreeHeap(PnpHeapHandle, 0, v5);
  }
  else
  {
    LastError = 8;
  }
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x180011ab8  mov     [rsp-8+arg_0], rbx
0x180011abd  mov     [rsp-8+arg_8], rdi
0x180011ac2  push    rbp
0x180011ac3  mov     rbp, rsp
0x180011ac6  sub     rsp, 70h
0x180011aca  mov     rcx, cs:PnpSvchostGlobalData
0x180011ad1  xor     eax, eax
0x180011ad3  xorps   xmm0, xmm0
0x180011ad6  mov     cs:PnpNoPendingInstallEvents, rax
0x180011add  movups  [rbp+pSecurityDescriptor], xmm0
0x180011ae1  mov     [rbp+var_8], rax
0x180011ae5  mov     rcx, [rcx+20h]; pSid
0x180011ae9  movups  [rbp+var_18], xmm0
0x180011aed  mov     [rbp+EventAttributes.bInheritHandle], eax
0x180011af0  movups  xmmword ptr [rbp+EventAttributes.nLength], xmm0
0x180011af4  call    cs:__imp_GetLengthSid
0x180011afa  mov     rcx, cs:PnpSvchostGlobalData
0x180011b01  mov     ebx, eax
0x180011b03  mov     rcx, [rcx+50h]; pSid
0x180011b07  call    cs:__imp_GetLengthSid
0x180011b0d  mov     rcx, cs:PnpSvchostGlobalData
0x180011b14  add     ebx, eax
0x180011b16  mov     rcx, [rcx+58h]; pSid
0x180011b1a  call    cs:__imp_GetLengthSid
0x180011b20  add     eax, 20h ; ' '
0x180011b23  add     ebx, eax
0x180011b25  mov     ecx, ebx
0x180011b27  call    PnpHeapAlloc
0x180011b2c  mov     rdi, rax
0x180011b2f  test    rax, rax
0x180011b32  jnz     short loc_180011B3C
0x180011b34  lea     ebx, [rax+8]
0x180011b37  jmp     loc_180011C62
0x180011b3c  mov     r8d, 2; dwAclRevision
0x180011b42  mov     edx, ebx; nAclLength
0x180011b44  mov     rcx, rdi; pAcl
0x180011b47  call    cs:__imp_InitializeAcl
0x180011b4d  test    eax, eax
0x180011b4f  jnz     short loc_180011B5E
0x180011b51  call    cs:__imp_GetLastError
0x180011b57  mov     ebx, eax
0x180011b59  jmp     loc_180011C50
0x180011b5e  mov     rax, cs:PnpSvchostGlobalData
0x180011b65  xor     r8d, r8d; AceFlags
0x180011b68  mov     r9d, 1F0003h; AccessMask
0x180011b6e  mov     rcx, [rax+20h]
0x180011b72  lea     edx, [r8+2]; dwAceRevision
0x180011b76  mov     [rsp+70h+pSid], rcx; pSid
0x180011b7b  mov     rcx, rdi; pAcl
0x180011b7e  call    cs:__imp_AddAccessAllowedAceEx
0x180011b84  test    eax, eax
0x180011b86  jz      short loc_180011B51
0x180011b88  mov     rax, cs:PnpSvchostGlobalData
0x180011b8f  xor     r8d, r8d; AceFlags
0x180011b92  mov     ebx, 100001h
0x180011b97  mov     r9d, ebx; AccessMask
0x180011b9a  mov     rcx, [rax+50h]
0x180011b9e  lea     edx, [r8+2]; dwAceRevision
0x180011ba2  mov     [rsp+70h+pSid], rcx; pSid
0x180011ba7  mov     rcx, rdi; pAcl
0x180011baa  call    cs:__imp_AddAccessAllowedAceEx
0x180011bb0  test    eax, eax
0x180011bb2  jz      short loc_180011B51
0x180011bb4  mov     rax, cs:PnpSvchostGlobalData
0x180011bbb  xor     r8d, r8d; AceFlags
0x180011bbe  mov     r9d, ebx; AccessMask
0x180011bc1  mov     rcx, [rax+58h]
0x180011bc5  lea     edx, [r8+2]; dwAceRevision
0x180011bc9  mov     [rsp+70h+pSid], rcx; pSid
0x180011bce  mov     rcx, rdi; pAcl
0x180011bd1  call    cs:__imp_AddAccessAllowedAceEx
0x180011bd7  test    eax, eax
0x180011bd9  jz      loc_180011B51
0x180011bdf  mov     ebx, 1
0x180011be4  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180011be8  mov     edx, ebx; dwRevision
0x180011bea  call    cs:__imp_InitializeSecurityDescriptor
0x180011bf0  test    eax, eax
0x180011bf2  jz      loc_180011B51
0x180011bf8  xor     r9d, r9d; bDaclDefaulted
0x180011bfb  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180011bff  mov     r8, rdi; pDacl
0x180011c02  mov     edx, ebx; bDaclPresent
0x180011c04  call    cs:__imp_SetSecurityDescriptorDacl
0x180011c0a  test    eax, eax
0x180011c0c  jz      loc_180011B51
0x180011c12  lea     rax, [rbp+pSecurityDescriptor]
0x180011c16  mov     [rbp+EventAttributes.nLength], 18h
0x180011c1d  lea     r9, Name; "Global\\PnP_No_Pending_Install_Events"
0x180011c24  mov     [rbp+EventAttributes.lpSecurityDescriptor], rax
0x180011c28  xor     r8d, r8d; bInitialState
0x180011c2b  mov     [rbp+EventAttributes.bInheritHandle], 0
0x180011c32  mov     edx, ebx; bManualReset
0x180011c34  lea     rcx, [rbp+EventAttributes]; lpEventAttributes
0x180011c38  call    cs:__imp_CreateEventW
0x180011c3e  test    rax, rax
0x180011c41  jz      loc_180011B51
0x180011c47  xor     ebx, ebx
0x180011c49  mov     cs:PnpNoPendingInstallEvents, rax
0x180011c50  mov     rcx, cs:PnpHeapHandle; HeapHandle
0x180011c57  mov     r8, rdi; P
0x180011c5a  xor     edx, edx; Flags
0x180011c5c  call    cs:__imp_RtlFreeHeap
0x180011c62  mov     ecx, ebx; dwErrCode
0x180011c64  call    cs:__imp_SetLastError
0x180011c6a  xor     eax, eax
0x180011c6c  lea     r11, [rsp+70h+var_s0]
0x180011c71  mov     rdi, [r11+18h]
0x180011c75  test    ebx, ebx
0x180011c77  mov     rbx, [r11+10h]
0x180011c7b  setz    al
0x180011c7e  mov     rsp, r11
0x180011c81  pop     rbp
0x180011c82  retn
```
