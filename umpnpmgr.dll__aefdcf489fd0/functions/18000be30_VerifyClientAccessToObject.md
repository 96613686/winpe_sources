# VerifyClientAccessToObject

- ea: `0x18000be30`
- end: `0x18000bf56`
- name: `VerifyClientAccessToObject`
- size: `294`
- prototype: `__int64 __fastcall(DWORD, __int64, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000bc30`
- `0x18000fd90`
- `0x1800121f0`
- `0x1800144b0`
- `0x1800146d0`
- `0x180015550`

## callees

- `0x18000be30`
- `0x180011964`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf20`
- `RPCRT4!RpcImpersonateClient` at `0x18000be59`
- `RPCRT4!RpcImpersonateClient` at `0x18000be59`
- `RPCRT4!RpcRevertToSelf` at `0x18000bf44`
- `RPCRT4!RpcRevertToSelf` at `0x180018e19`
- `RPCRT4!RpcRevertToSelf` at `0x18000bf44`
- `RPCRT4!RpcRevertToSelf` at `0x180018e19`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18000be9c`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18000be9c`
- `api-ms-win-security-base-l1-1-0!AccessCheckAndAuditAlarmW` at `0x18000bef9`
- `api-ms-win-security-base-l1-1-0!AccessCheckAndAuditAlarmW` at `0x18000bef9`

## string_xrefs

- `0x18000bee2`: `PlugPlaySecurityObject`
- `0x18000bee9`: `Security`

## pseudocode

```c
__int64 __fastcall VerifyClientAccessToObject(DWORD a1, __int64 a2, __int64 a3)
{
  PSECURITY_DESCRIPTOR SecurityDescriptor; // rbx
  RPC_STATUS v4; // eax
  __int64 v6; // rbx
  DWORD LastError; // eax
  DWORD AccessMask; // [rsp+80h] [rbp+8h] BYREF
  WINBOOL pfGenerateOnClose; // [rsp+88h] [rbp+10h] BYREF
  int v10; // [rsp+8Ch] [rbp+14h]
  WINBOOL AccessStatus; // [rsp+90h] [rbp+18h] BYREF
  int v12; // [rsp+94h] [rbp+1Ch]
  DWORD GrantedAccess; // [rsp+98h] [rbp+20h] BYREF

  v12 = HIDWORD(a3);
  v10 = HIDWORD(a2);
  AccessMask = a1;
  SecurityDescriptor = PlugPlaySecurityObject;
  AccessStatus = 0;
  pfGenerateOnClose = 0;
  GrantedAccess = 0;
  v4 = RpcImpersonateClient(0);
  if ( v4 == 1725 )
    return 1;
  if ( v4 )
    return 0;
  if ( !SecurityDescriptor )
    goto LABEL_10;
  MapGenericMask(&AccessMask, &PlugPlaySecurityObjectMapping);
  if ( !AccessCheckAndAuditAlarmW(
          L"PlugPlayManager",
          0,
          (LPWSTR)L"Security",
          (LPWSTR)L"PlugPlaySecurityObject",
          SecurityDescriptor,
          AccessMask,
          &PlugPlaySecurityObjectMapping,
          0,
          &GrantedAccess,
          &AccessStatus,
          &pfGenerateOnClose) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      LastError = GetLastError();
      WPP_SF_d(v6, 10, WPP_ff742bcf67f033c920602db626fdd8de_Traceguids, LastError);
    }
LABEL_10:
    AccessStatus = 0;
  }
  RpcRevertToSelf();
  return (unsigned int)AccessStatus;
}

```

## disassembly

```asm
0x18000be30  mov     rax, rsp
0x18000be33  mov     [rax+18h], r8
0x18000be37  mov     [rax+10h], rdx
0x18000be3b  mov     [rax+8], ecx
0x18000be3e  push    rbx
0x18000be3f  push    rsi
0x18000be40  push    rdi
0x18000be41  sub     rsp, 60h
0x18000be45  mov     rbx, cs:PlugPlaySecurityObject
0x18000be4c  xor     esi, esi
0x18000be4e  mov     [rax+18h], esi
0x18000be51  mov     [rax+10h], esi
0x18000be54  mov     [rax+20h], esi
0x18000be57  xor     ecx, ecx; BindingHandle
0x18000be59  call    cs:__imp_RpcImpersonateClient
0x18000be5f  cmp     eax, 6BDh
0x18000be64  jnz     short loc_18000BE73
0x18000be66  mov     eax, 1
0x18000be6b  add     rsp, 60h
0x18000be6f  pop     rdi
0x18000be70  pop     rsi
0x18000be71  pop     rbx
0x18000be72  retn
0x18000be73  test    eax, eax
0x18000be75  jz      short loc_18000BE81
0x18000be77  xor     eax, eax
0x18000be79  add     rsp, 60h
0x18000be7d  pop     rdi
0x18000be7e  pop     rsi
0x18000be7f  pop     rbx
0x18000be80  retn
0x18000be81  test    rbx, rbx
0x18000be84  jz      loc_18000BF3D
0x18000be8a  lea     rdi, PlugPlaySecurityObjectMapping
0x18000be91  mov     rdx, rdi; GenericMapping
0x18000be94  lea     rcx, [rsp+78h+AccessMask]; AccessMask
0x18000be9c  call    cs:__imp_MapGenericMask
0x18000bea2  lea     rax, [rsp+78h+arg_8]
0x18000beaa  mov     [rsp+78h+pfGenerateOnClose], rax; pfGenerateOnClose
0x18000beaf  lea     rax, [rsp+78h+arg_10]
0x18000beb7  mov     [rsp+78h+AccessStatus], rax; AccessStatus
0x18000bebc  lea     rax, [rsp+78h+arg_18]
0x18000bec4  mov     [rsp+78h+GrantedAccess], rax; GrantedAccess
0x18000bec9  mov     [rsp+78h+ObjectCreation], esi; ObjectCreation
0x18000becd  mov     [rsp+78h+GenericMapping], rdi; GenericMapping
0x18000bed2  mov     eax, [rsp+78h+AccessMask]
0x18000bed9  mov     [rsp+78h+DesiredAccess], eax; DesiredAccess
0x18000bedd  mov     [rsp+78h+SecurityDescriptor], rbx; SecurityDescriptor
0x18000bee2  lea     r9, ObjectName; "PlugPlaySecurityObject"
0x18000bee9  lea     r8, ObjectTypeName; "Security"
0x18000bef0  xor     edx, edx; HandleId
0x18000bef2  lea     rcx, SubsystemName; "PlugPlayManager"
0x18000bef9  call    cs:__imp_AccessCheckAndAuditAlarmW
0x18000beff  test    eax, eax
0x18000bf01  jnz     short loc_18000BF44
0x18000bf03  lea     rax, WPP_GLOBAL_Control
0x18000bf0a  mov     rbx, cs:WPP_GLOBAL_Control
0x18000bf11  cmp     rbx, rax
0x18000bf14  jz      short loc_18000BF3D
0x18000bf16  test    byte ptr [rbx+1Ch], 1
0x18000bf1a  jz      short loc_18000BF3D
0x18000bf1c  mov     rbx, [rbx+10h]
0x18000bf20  call    cs:__imp_GetLastError
0x18000bf26  mov     r9d, eax
0x18000bf29  mov     edx, 0Ah
0x18000bf2e  lea     r8, WPP_ff742bcf67f033c920602db626fdd8de_Traceguids
0x18000bf35  mov     rcx, rbx
0x18000bf38  call    WPP_SF_d
0x18000bf3d  mov     [rsp+78h+arg_10], esi
0x18000bf44  call    cs:__imp_RpcRevertToSelf
0x18000bf4a  mov     eax, [rsp+78h+arg_10]
0x18000bf51  jmp     loc_18000BE79
0x180018e10  push    rbp
0x180018e12  sub     rsp, 60h
0x180018e16  mov     rbp, rdx
0x180018e19  call    cs:__imp_RpcRevertToSelf
0x180018e1f  nop
0x180018e20  add     rsp, 60h
0x180018e24  pop     rbp
0x180018e25  retn
```
