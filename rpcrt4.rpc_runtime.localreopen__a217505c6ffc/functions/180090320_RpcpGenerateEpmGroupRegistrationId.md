# RpcpGenerateEpmGroupRegistrationId

- ea: `0x180090320`
- end: `0x180090524`
- name: `RpcpGenerateEpmGroupRegistrationId`
- size: `516`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18008f2fc`

## callees

- `0x180023a40`
- `0x180090320`
- `0x18009052c`
- `0x1800ceda0`

## import_xrefs

- `ntdll!NtDeleteWnfStateName` at `0x180090516`
- `ntdll!NtDeleteWnfStateName` at `0x180090516`
- `ntdll!RtlPublishWnfStateData` at `0x18009048b`
- `ntdll!RtlPublishWnfStateData` at `0x18009048b`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180090427`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180090427`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18009040d`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18009040d`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800903c6`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800903f5`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800903c6`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800903f5`
- `ntdll!RtlCreateAcl` at `0x1800903a9`
- `ntdll!RtlCreateAcl` at `0x1800903a9`
- `ntdll!NtCreateWnfStateName` at `0x18009045b`
- `ntdll!NtCreateWnfStateName` at `0x18009045b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800904f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800904f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800904c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800904c0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180090384`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180090384`

## pseudocode

```c
__int64 __fastcall RpcpGenerateEpmGroupRegistrationId(_QWORD *a1)
{
  unsigned int v2; // ebx
  int v4; // [rsp+40h] [rbp-C0h] BYREF
  PSID lpMem; // [rsp+48h] [rbp-B8h] BYREF
  PSID Sid; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v8; // [rsp+78h] [rbp-88h]
  _QWORD v9[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _ACL Acl; // [rsp+90h] [rbp-70h] BYREF

  v9[0] = 0;
  v8 = 0;
  Sid = 0;
  lpMem = 0;
  v4 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  if ( ConvertStringSidToSidW(L"S-1-5-80-521322694-906040134-3864710659-1525148216-3451224162", &Sid) )
  {
    RtlCreateAcl(&Acl, 0x100u, 2u);
    RtlAddAccessAllowedAce(&Acl, 2u, 0x80000000, Sid);
    if ( (unsigned int)GetCurrentUserSid(&lpMem)
      || (RtlAddAccessAllowedAce(&Acl, 2u, 0xC0010000, lpMem),
          RtlCreateSecurityDescriptor(SecurityDescriptor, 1u),
          RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, &Acl, 0),
          (int)NtCreateWnfStateName(v9, 3, 0, 0, 0, 4, SecurityDescriptor) < 0) )
    {
      v2 = 14;
    }
    else
    {
      v4 = 1;
      if ( (int)RtlPublishWnfStateData(v9[0], 0, &v4, 4, 0) < 0 )
      {
        v2 = 14;
        NtDeleteWnfStateName(v9);
      }
      else
      {
        v2 = 0;
        *a1 = v9[0];
      }
    }
    if ( lpMem )
      FreeWrapper(lpMem);
  }
  else
  {
    GetLastError();
    v2 = 14;
  }
  if ( Sid )
    LocalFree(Sid);
  return v2;
}

```

## disassembly

```asm
0x180090320  mov     [rsp-8+arg_8], rbx
0x180090325  mov     [rsp-8+arg_10], rsi
0x18009032a  push    rbp
0x18009032b  lea     rbp, [rsp-0A0h]
0x180090333  sub     rsp, 1A0h
0x18009033a  mov     rax, cs:__security_cookie
0x180090341  xor     rax, rsp
0x180090344  mov     [rbp+0A0h+var_10], rax
0x18009034b  xor     eax, eax
0x18009034d  mov     [rbp+0A0h+var_120], 0
0x180090355  xorps   xmm0, xmm0
0x180090358  mov     [rsp+1A0h+var_128], rax
0x18009035d  mov     rsi, rcx
0x180090360  mov     [rsp+1A0h+Sid], rax
0x180090365  lea     rcx, StringSid; "S-1-5-80-521322694-906040134-3864710659"...
0x18009036c  mov     [rsp+1A0h+lpMem], rax
0x180090371  lea     rdx, [rsp+1A0h+Sid]; Sid
0x180090376  mov     [rsp+1A0h+var_160], eax
0x18009037a  movups  [rsp+1A0h+SecurityDescriptor], xmm0
0x18009037f  movups  [rsp+1A0h+var_138], xmm0
0x180090384  call    cs:__imp_ConvertStringSidToSidW
0x18009038b  nop     dword ptr [rax+rax+00h]
0x180090390  test    eax, eax
0x180090392  jz      loc_1800904F3
0x180090398  mov     ebx, 2
0x18009039d  lea     rcx, [rbp+0A0h+Acl]; Acl
0x1800903a1  mov     r8d, ebx; AclRevision
0x1800903a4  mov     edx, 100h; AclSize
0x1800903a9  call    cs:__imp_RtlCreateAcl
0x1800903b0  nop     dword ptr [rax+rax+00h]
0x1800903b5  mov     r9, [rsp+1A0h+Sid]; Sid
0x1800903ba  lea     rcx, [rbp+0A0h+Acl]; Acl
0x1800903be  mov     r8d, 80000000h; AccessMask
0x1800903c4  mov     edx, ebx; Revision
0x1800903c6  call    cs:__imp_RtlAddAccessAllowedAce
0x1800903cd  nop     dword ptr [rax+rax+00h]
0x1800903d2  lea     rcx, [rsp+1A0h+lpMem]; void **
0x1800903d7  call    ?GetCurrentUserSid@@YAJPEAPEAX@Z; GetCurrentUserSid(void * *)
0x1800903dc  test    eax, eax
0x1800903de  jnz     loc_180090506
0x1800903e4  mov     r9, [rsp+1A0h+lpMem]; Sid
0x1800903e9  lea     rcx, [rbp+0A0h+Acl]; Acl
0x1800903ed  mov     r8d, 0C0010000h; AccessMask
0x1800903f3  mov     edx, ebx; Revision
0x1800903f5  call    cs:__imp_RtlAddAccessAllowedAce
0x1800903fc  nop     dword ptr [rax+rax+00h]
0x180090401  mov     ebx, 1
0x180090406  lea     rcx, [rsp+1A0h+SecurityDescriptor]; SecurityDescriptor
0x18009040b  mov     edx, ebx; Revision
0x18009040d  call    cs:__imp_RtlCreateSecurityDescriptor
0x180090414  nop     dword ptr [rax+rax+00h]
0x180090419  xor     r9d, r9d; DaclDefaulted
0x18009041c  lea     r8, [rbp+0A0h+Acl]; Dacl
0x180090420  mov     dl, bl; DaclPresent
0x180090422  lea     rcx, [rsp+1A0h+SecurityDescriptor]; SecurityDescriptor
0x180090427  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18009042e  nop     dword ptr [rax+rax+00h]
0x180090433  lea     rax, [rsp+1A0h+SecurityDescriptor]
0x180090438  xor     r9d, r9d
0x18009043b  mov     [rsp+1A0h+var_170], rax
0x180090440  lea     edx, [rbx+2]
0x180090443  mov     [rsp+1A0h+var_178], 4
0x18009044b  lea     rcx, [rbp+0A0h+var_120]
0x18009044f  xor     r8d, r8d
0x180090452  mov     [rsp+1A0h+var_180], 0
0x18009045b  call    cs:__imp_NtCreateWnfStateName
0x180090462  nop     dword ptr [rax+rax+00h]
0x180090467  test    eax, eax
0x180090469  js      loc_180090506
0x18009046f  mov     rcx, [rbp+0A0h+var_120]
0x180090473  lea     r9d, [rbx+3]
0x180090477  lea     r8, [rsp+1A0h+var_160]
0x18009047c  mov     [rsp+1A0h+var_160], ebx
0x180090480  xor     edx, edx
0x180090482  mov     [rsp+1A0h+var_180], 0
0x18009048b  call    cs:__imp_RtlPublishWnfStateData
0x180090492  nop     dword ptr [rax+rax+00h]
0x180090497  test    eax, eax
0x180090499  js      short loc_18009050D
0x18009049b  mov     rax, [rbp+0A0h+var_120]
0x18009049f  xor     ebx, ebx
0x1800904a1  mov     [rsi], rax
0x1800904a4  cmp     [rsp+1A0h+lpMem], 0
0x1800904aa  jz      short loc_1800904B6
0x1800904ac  mov     rcx, [rsp+1A0h+lpMem]; lpMem
0x1800904b1  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800904b6  mov     rcx, [rsp+1A0h+Sid]; hMem
0x1800904bb  test    rcx, rcx
0x1800904be  jz      short loc_1800904CC
0x1800904c0  call    cs:__imp_LocalFree
0x1800904c7  nop     dword ptr [rax+rax+00h]
0x1800904cc  mov     eax, ebx
0x1800904ce  mov     rcx, [rbp+0A0h+var_10]
0x1800904d5  xor     rcx, rsp; StackCookie
0x1800904d8  call    __security_check_cookie
0x1800904dd  lea     r11, [rsp+1A0h+var_s0]
0x1800904e5  mov     rbx, [r11+18h]
0x1800904e9  mov     rsi, [r11+20h]
0x1800904ed  mov     rsp, r11
0x1800904f0  pop     rbp
0x1800904f1  retn
0x1800904f3  call    cs:__imp_GetLastError
0x1800904fa  nop     dword ptr [rax+rax+00h]
0x1800904ff  mov     ebx, 0Eh
0x180090504  jmp     short loc_1800904B6
0x180090506  mov     ebx, 0Eh
0x18009050b  jmp     short loc_1800904A4
0x18009050d  lea     rcx, [rbp+0A0h+var_120]
0x180090511  mov     ebx, 0Eh
0x180090516  call    cs:__imp_NtDeleteWnfStateName
0x18009051d  nop     dword ptr [rax+rax+00h]
0x180090522  jmp     short loc_1800904A4
```
