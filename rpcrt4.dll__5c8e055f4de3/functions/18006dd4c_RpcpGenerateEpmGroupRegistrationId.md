# RpcpGenerateEpmGroupRegistrationId

- ea: `0x18006dd4c`
- end: `0x18006df0d`
- name: `RpcpGenerateEpmGroupRegistrationId`
- size: `449`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006cddc`

## callees

- `0x180022870`
- `0x18006dd4c`
- `0x18006df14`
- `0x1800ca140`

## import_xrefs

- `ntdll!NtDeleteWnfStateName` at `0x18006df05`
- `ntdll!NtDeleteWnfStateName` at `0x18006df05`
- `ntdll!RtlPublishWnfStateData` at `0x18006de8d`
- `ntdll!RtlPublishWnfStateData` at `0x18006de8d`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18006de35`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18006de35`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18006de21`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18006de21`
- `ntdll!RtlAddAccessAllowedAce` at `0x18006dde6`
- `ntdll!RtlAddAccessAllowedAce` at `0x18006de0f`
- `ntdll!RtlAddAccessAllowedAce` at `0x18006dde6`
- `ntdll!RtlAddAccessAllowedAce` at `0x18006de0f`
- `ntdll!RtlCreateAcl` at `0x18006ddcf`
- `ntdll!RtlCreateAcl` at `0x18006ddcf`
- `ntdll!NtCreateWnfStateName` at `0x18006de63`
- `ntdll!NtCreateWnfStateName` at `0x18006de63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006dee8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006dee8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006debc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006debc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18006ddb0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18006ddb0`

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
  _ACL Acl; // [rsp+90h] [rbp-70h] BYREF

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
0x18006dd4c  mov     [rsp-8+arg_8], rbx
0x18006dd51  mov     [rsp-8+arg_10], rsi
0x18006dd56  push    rbp
0x18006dd57  lea     rbp, [rsp-0A0h]
0x18006dd5f  sub     rsp, 1A0h
0x18006dd66  mov     rax, cs:__security_cookie
0x18006dd6d  xor     rax, rsp
0x18006dd70  mov     [rbp+0A0h+var_10], rax
0x18006dd77  xor     eax, eax
0x18006dd79  mov     [rbp+0A0h+var_120], 0
0x18006dd81  xorps   xmm0, xmm0
0x18006dd84  mov     [rsp+1A0h+var_128], rax
0x18006dd89  mov     rsi, rcx
0x18006dd8c  mov     [rsp+1A0h+Sid], rax
0x18006dd91  lea     rcx, StringSid; "S-1-5-80-521322694-906040134-3864710659"...
0x18006dd98  mov     [rsp+1A0h+lpMem], rax
0x18006dd9d  lea     rdx, [rsp+1A0h+Sid]; Sid
0x18006dda2  mov     [rsp+1A0h+var_160], eax
0x18006dda6  movups  [rsp+1A0h+SecurityDescriptor], xmm0
0x18006ddab  movups  [rsp+1A0h+var_138], xmm0
0x18006ddb0  call    cs:__imp_ConvertStringSidToSidW
0x18006ddb6  test    eax, eax
0x18006ddb8  jz      loc_18006DEE8
0x18006ddbe  mov     ebx, 2
0x18006ddc3  lea     rcx, [rbp+0A0h+Acl]; Acl
0x18006ddc7  mov     r8d, ebx; AclRevision
0x18006ddca  mov     edx, 100h; AclSize
0x18006ddcf  call    cs:__imp_RtlCreateAcl
0x18006ddd5  mov     r9, [rsp+1A0h+Sid]; Sid
0x18006ddda  lea     rcx, [rbp+0A0h+Acl]; Acl
0x18006ddde  mov     r8d, 80000000h; AccessMask
0x18006dde4  mov     edx, ebx; Revision
0x18006dde6  call    cs:__imp_RtlAddAccessAllowedAce
0x18006ddec  lea     rcx, [rsp+1A0h+lpMem]; void **
0x18006ddf1  call    ?GetCurrentUserSid@@YAJPEAPEAX@Z; GetCurrentUserSid(void * *)
0x18006ddf6  test    eax, eax
0x18006ddf8  jnz     loc_18006DEF5
0x18006ddfe  mov     r9, [rsp+1A0h+lpMem]; Sid
0x18006de03  lea     rcx, [rbp+0A0h+Acl]; Acl
0x18006de07  mov     r8d, 0C0010000h; AccessMask
0x18006de0d  mov     edx, ebx; Revision
0x18006de0f  call    cs:__imp_RtlAddAccessAllowedAce
0x18006de15  mov     ebx, 1
0x18006de1a  lea     rcx, [rsp+1A0h+SecurityDescriptor]; SecurityDescriptor
0x18006de1f  mov     edx, ebx; Revision
0x18006de21  call    cs:__imp_RtlCreateSecurityDescriptor
0x18006de27  xor     r9d, r9d; DaclDefaulted
0x18006de2a  lea     r8, [rbp+0A0h+Acl]; Dacl
0x18006de2e  mov     dl, bl; DaclPresent
0x18006de30  lea     rcx, [rsp+1A0h+SecurityDescriptor]; SecurityDescriptor
0x18006de35  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18006de3b  lea     rax, [rsp+1A0h+SecurityDescriptor]
0x18006de40  xor     r9d, r9d
0x18006de43  mov     [rsp+1A0h+var_170], rax
0x18006de48  lea     edx, [rbx+2]
0x18006de4b  mov     [rsp+1A0h+var_178], 4
0x18006de53  lea     rcx, [rbp+0A0h+var_120]
0x18006de57  xor     r8d, r8d
0x18006de5a  mov     [rsp+1A0h+var_180], 0
0x18006de63  call    cs:__imp_NtCreateWnfStateName
0x18006de69  test    eax, eax
0x18006de6b  js      loc_18006DEF5
0x18006de71  mov     rcx, [rbp+0A0h+var_120]
0x18006de75  lea     r9d, [rbx+3]
0x18006de79  lea     r8, [rsp+1A0h+var_160]
0x18006de7e  mov     [rsp+1A0h+var_160], ebx
0x18006de82  xor     edx, edx
0x18006de84  mov     [rsp+1A0h+var_180], 0
0x18006de8d  call    cs:__imp_RtlPublishWnfStateData
0x18006de93  test    eax, eax
0x18006de95  js      short loc_18006DEFC
0x18006de97  mov     rax, [rbp+0A0h+var_120]
0x18006de9b  xor     ebx, ebx
0x18006de9d  mov     [rsi], rax
0x18006dea0  cmp     [rsp+1A0h+lpMem], 0
0x18006dea6  jz      short loc_18006DEB2
0x18006dea8  mov     rcx, [rsp+1A0h+lpMem]; lpMem
0x18006dead  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18006deb2  mov     rcx, [rsp+1A0h+Sid]; hMem
0x18006deb7  test    rcx, rcx
0x18006deba  jz      short loc_18006DEC2
0x18006debc  call    cs:__imp_LocalFree
0x18006dec2  mov     eax, ebx
0x18006dec4  mov     rcx, [rbp+0A0h+var_10]
0x18006decb  xor     rcx, rsp; StackCookie
0x18006dece  call    __security_check_cookie
0x18006ded3  lea     r11, [rsp+1A0h+var_s0]
0x18006dedb  mov     rbx, [r11+18h]
0x18006dedf  mov     rsi, [r11+20h]
0x18006dee3  mov     rsp, r11
0x18006dee6  pop     rbp
0x18006dee7  retn
0x18006dee8  call    cs:__imp_GetLastError
0x18006deee  mov     ebx, 0Eh
0x18006def3  jmp     short loc_18006DEB2
0x18006def5  mov     ebx, 0Eh
0x18006defa  jmp     short loc_18006DEA0
0x18006defc  lea     rcx, [rbp+0A0h+var_120]
0x18006df00  mov     ebx, 0Eh
0x18006df05  call    cs:__imp_NtDeleteWnfStateName
0x18006df0b  jmp     short loc_18006DEA0
```
