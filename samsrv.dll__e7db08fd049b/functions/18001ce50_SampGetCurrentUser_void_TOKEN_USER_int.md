# SampGetCurrentUser(void *,_TOKEN_USER * *,int *)

- ea: `0x18001ce50`
- end: `0x18001cf8d`
- name: `?SampGetCurrentUser@@YAJPEAXPEAPEAU_TOKEN_USER@@PEAH@Z`
- size: `317`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, struct _TOKEN_USER **, int *)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001e1b0`
- `0x18001e900`
- `0x18001f7e0`

## callees

- `0x180012a28`
- `0x18001ce50`
- `0x18001cfa0`
- `0x180027e24`
- `0x18008ecd0`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18001cedb`
- `ntdll!NtQueryInformationToken` at `0x18001cedb`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001cef4`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001cef4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ceac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ceac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cf0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cf0b`
- `RPCRT4!RpcRevertToSelf` at `0x18001cf53`
- `RPCRT4!RpcRevertToSelf` at `0x18001cf53`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtUnImpersonateAnyClient` at `0x18001cf44`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtUnImpersonateAnyClient` at `0x18001cf44`

## pseudocode

```c
__int64 __fastcall SampGetCurrentUser(__int64 TokenHandle, HLOCAL *a2, int *a3)
{
  __int64 v3; // rbx
  NTSTATUS v6; // edi
  struct _TOKEN_USER *v7; // rax
  ULONG TokenInformationLength; // [rsp+50h] [rbp+8h] BYREF
  int v10; // [rsp+58h] [rbp+10h] BYREF

  v3 = TokenHandle;
  TokenInformationLength = 0;
  v10 = 0;
  *a2 = 0;
  if ( !TokenHandle )
  {
    v6 = SampImpersonateClient(&v10);
    if ( v6 < 0 )
      goto LABEL_9;
    v3 = -5;
  }
  TokenInformationLength = 84;
  v7 = (struct _TOKEN_USER *)LocalAlloc(0x40u, 0x54u);
  *a2 = v7;
  if ( v7 )
  {
    v6 = NtQueryInformationToken((HANDLE)v3, TokenUser, v7, TokenInformationLength, &TokenInformationLength);
    if ( v6 >= 0 )
    {
      if ( CheckTokenMembership((HANDLE)v3, SampAdministratorsAliasSid, a3) )
        goto LABEL_11;
      v6 = -1073741823;
    }
  }
  else
  {
    v6 = -1073741670;
  }
LABEL_9:
  if ( *a2 )
  {
    LocalFree(*a2);
    *a2 = 0;
  }
LABEL_11:
  if ( v10 == 2 )
  {
    RpcRevertToSelf();
  }
  else if ( v10 == 1 )
  {
    SamIRevertNullSession();
  }
  else if ( v10 == 3 && (int)SampShouldCallNtdsaApiSet() >= 0 )
  {
    NtdsaExtUnImpersonateAnyClient();
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 76, WPP_5505de3e48bd33375e96ca021b170945_Traceguids, (unsigned int)v6, v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001ce50  mov     rax, rsp
0x18001ce53  push    rdi
0x18001ce54  sub     rsp, 40h
0x18001ce58  mov     [rax+18h], rbx
0x18001ce5c  mov     rbx, rcx
0x18001ce5f  mov     [rax+20h], rbp
0x18001ce63  mov     rbp, r8
0x18001ce66  mov     [rax-10h], rsi
0x18001ce6a  mov     rsi, rdx
0x18001ce6d  mov     [rax-18h], r14
0x18001ce71  xor     r14d, r14d
0x18001ce74  mov     [rax+8], r14d
0x18001ce78  mov     [rax+10h], r14d
0x18001ce7c  mov     [rdx], r14
0x18001ce7f  test    rcx, rcx
0x18001ce82  jnz     short loc_18001CE9A
0x18001ce84  lea     rcx, [rax+10h]
0x18001ce88  call    SampImpersonateClient
0x18001ce8d  mov     edi, eax
0x18001ce8f  test    eax, eax
0x18001ce91  js      short loc_18001CF03
0x18001ce93  mov     rbx, 0FFFFFFFFFFFFFFFBh
0x18001ce9a  mov     edx, 54h ; 'T'; uBytes
0x18001ce9f  mov     [rsp+48h+TokenInformationLength], 54h ; 'T'
0x18001cea7  mov     ecx, 40h ; '@'; uFlags
0x18001ceac  call    cs:__imp_LocalAlloc
0x18001ceb2  mov     [rsi], rax
0x18001ceb5  test    rax, rax
0x18001ceb8  jnz     short loc_18001CEC1
0x18001ceba  mov     edi, 0C000009Ah
0x18001cebf  jmp     short loc_18001CF03
0x18001cec1  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18001cec6  lea     rcx, [rsp+48h+TokenInformationLength]
0x18001cecb  mov     [rsp+48h+ReturnLength], rcx; ReturnLength
0x18001ced0  mov     r8, rax; TokenInformation
0x18001ced3  mov     rcx, rbx; TokenHandle
0x18001ced6  mov     edx, 1; TokenInformationClass
0x18001cedb  call    cs:__imp_NtQueryInformationToken
0x18001cee1  mov     edi, eax
0x18001cee3  test    eax, eax
0x18001cee5  js      short loc_18001CF03
0x18001cee7  mov     rdx, cs:SampAdministratorsAliasSid; SidToCheck
0x18001ceee  mov     r8, rbp; IsMember
0x18001cef1  mov     rcx, rbx; TokenHandle
0x18001cef4  call    cs:__imp_CheckTokenMembership
0x18001cefa  test    eax, eax
0x18001cefc  jnz     short loc_18001CF14
0x18001cefe  mov     edi, 0C0000001h
0x18001cf03  mov     rcx, [rsi]; hMem
0x18001cf06  test    rcx, rcx
0x18001cf09  jz      short loc_18001CF14
0x18001cf0b  call    cs:__imp_LocalFree
0x18001cf11  mov     [rsi], r14
0x18001cf14  mov     eax, [rsp+48h+arg_8]
0x18001cf18  mov     r14, [rsp+48h+var_18]
0x18001cf1d  mov     rsi, [rsp+48h+var_10]
0x18001cf22  mov     rbp, [rsp+48h+arg_18]
0x18001cf27  mov     rbx, [rsp+48h+arg_10]
0x18001cf2c  cmp     eax, 2
0x18001cf2f  jz      short loc_18001CF53
0x18001cf31  sub     eax, 1
0x18001cf34  jz      short loc_18001CF4C
0x18001cf36  cmp     eax, 2
0x18001cf39  jnz     short loc_18001CF59
0x18001cf3b  call    ?SampShouldCallNtdsaApiSet@@YAJXZ; SampShouldCallNtdsaApiSet(void)
0x18001cf40  test    eax, eax
0x18001cf42  js      short loc_18001CF59
0x18001cf44  call    cs:__imp_NtdsaExtUnImpersonateAnyClient
0x18001cf4a  jmp     short loc_18001CF59
0x18001cf4c  call    SamIRevertNullSession
0x18001cf51  jmp     short loc_18001CF59
0x18001cf53  call    cs:__imp_RpcRevertToSelf
0x18001cf59  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf60  test    dword ptr [rcx+44h], 20000h
0x18001cf67  jz      short loc_18001CF85
0x18001cf69  mov     rcx, [rcx+38h]
0x18001cf6d  lea     r8, WPP_5505de3e48bd33375e96ca021b170945_Traceguids
0x18001cf74  mov     edx, 4Ch ; 'L'
0x18001cf79  mov     dword ptr [rsp+48h+ReturnLength], edi
0x18001cf7d  mov     r9d, edi
0x18001cf80  call    WPP_SF_Dd
0x18001cf85  mov     eax, edi
0x18001cf87  add     rsp, 40h
0x18001cf8b  pop     rdi
0x18001cf8c  retn
```
