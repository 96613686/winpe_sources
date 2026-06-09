# DavImpersonateAndGetLogonId

- ea: `0x180005568`
- end: `0x1800056ed`
- name: `DavImpersonateAndGetLogonId`
- size: `389`
- prototype: `__int64 __fastcall(PLUID DestinationLuid)`
- caller_count: `12`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180002ca0`
- `0x18000370c`
- `0x180005a38`
- `0x180006670`
- `0x180006a90`
- `0x180006d20`
- `0x180007b50`
- `0x180008c50`
- `0x180009480`
- `0x180009740`
- `0x18000a370`
- `0x18000b060`

## callees

- `0x180005568`
- `0x18000591c`
- `0x180006618`
- `0x18000b7dc`
- `0x18000b8e8`
- `0x180028a00`
- `0x18002cfa0`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180005614`
- `ntdll!NtQueryInformationToken` at `0x180005614`
- `ntdll!RtlCopyLuid` at `0x18000565e`
- `ntdll!RtlCopyLuid` at `0x18000565e`

## pseudocode

```c
__int64 __fastcall DavImpersonateAndGetLogonId(PLUID DestinationLuid)
{
  unsigned int v2; // eax
  __int64 v3; // r8
  unsigned int v4; // ebx
  unsigned int v5; // edi
  _QWORD *v6; // rcx
  unsigned int v7; // eax
  unsigned int v8; // eax
  ULONG ReturnLength; // [rsp+30h] [rbp-58h] BYREF
  _OWORD TokenInformation[3]; // [rsp+38h] [rbp-50h] BYREF
  __int64 v12; // [rsp+68h] [rbp-20h]

  memset(TokenInformation, 0, sizeof(TokenInformation));
  v12 = 0;
  ReturnLength = 0;
  v2 = DavImpersonateClient();
  v4 = v2;
  if ( !v2 )
  {
    v7 = NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFBLL, TokenStatistics, TokenInformation, 0x38u, &ReturnLength);
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 212, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v7);
    }
    else if ( DestinationLuid )
    {
      RtlCopyLuid(DestinationLuid, (PLUID)TokenInformation + 1);
    }
    v8 = DavRevertToSelf();
    v5 = v8;
    if ( v8 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 213, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v8);
    v4 = NetpNtStatusToApiStatus(v5);
    goto LABEL_16;
  }
  v5 = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v4;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 211, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v2);
LABEL_16:
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
    WPP_SF_LL(v6[2], 214, v3, v5, v4);
  return v4;
}

```

## disassembly

```asm
0x180005568  mov     [rsp+arg_8], rbx
0x18000556d  mov     [rsp+arg_10], rsi
0x180005572  push    rdi
0x180005573  sub     rsp, 80h
0x18000557a  mov     rax, cs:__security_cookie
0x180005581  xor     rax, rsp
0x180005584  mov     [rsp+88h+var_18], rax
0x180005589  xorps   xmm0, xmm0
0x18000558c  xor     eax, eax
0x18000558e  movups  [rsp+88h+TokenInformation], xmm0
0x180005593  mov     [rsp+88h+var_20], rax
0x180005598  mov     rdi, rcx
0x18000559b  movups  [rsp+88h+var_40], xmm0
0x1800055a0  mov     [rsp+88h+var_58], eax
0x1800055a4  movups  [rsp+88h+var_30], xmm0
0x1800055a9  call    DavImpersonateClient
0x1800055ae  mov     ebx, eax
0x1800055b0  test    eax, eax
0x1800055b2  jz      short loc_1800055F4
0x1800055b4  xor     edi, edi
0x1800055b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055bd  lea     rsi, WPP_GLOBAL_Control
0x1800055c4  cmp     rcx, rsi
0x1800055c7  jz      loc_1800056C9
0x1800055cd  test    byte ptr [rcx+1Ch], 1
0x1800055d1  jz      loc_1800056A9
0x1800055d7  mov     rcx, [rcx+10h]
0x1800055db  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x1800055e2  mov     edx, 0D3h
0x1800055e7  mov     r9d, eax
0x1800055ea  call    WPP_SF_d
0x1800055ef  jmp     loc_1800056A2
0x1800055f4  mov     r9d, 38h ; '8'; TokenInformationLength
0x1800055fa  lea     rax, [rsp+88h+var_58]
0x1800055ff  lea     r8, [rsp+88h+TokenInformation]; TokenInformation
0x180005604  mov     [rsp+88h+ReturnLength], rax; ReturnLength
0x180005609  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x180005610  lea     edx, [r9-2Eh]; TokenInformationClass
0x180005614  call    cs:__imp_NtQueryInformationToken
0x18000561a  lea     rsi, WPP_GLOBAL_Control
0x180005621  test    eax, eax
0x180005623  jz      short loc_180005651
0x180005625  mov     rcx, cs:WPP_GLOBAL_Control
0x18000562c  cmp     rcx, rsi
0x18000562f  jz      short loc_180005664
0x180005631  test    byte ptr [rcx+1Ch], 1
0x180005635  jz      short loc_180005664
0x180005637  mov     rcx, [rcx+10h]
0x18000563b  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180005642  mov     edx, 0D4h
0x180005647  mov     r9d, eax
0x18000564a  call    WPP_SF_d
0x18000564f  jmp     short loc_180005664
0x180005651  test    rdi, rdi
0x180005654  jz      short loc_180005664
0x180005656  lea     rdx, [rsp+88h+TokenInformation+8]; SourceLuid
0x18000565b  mov     rcx, rdi; DestinationLuid
0x18000565e  call    cs:__imp_RtlCopyLuid
0x180005664  call    DavRevertToSelf
0x180005669  mov     edi, eax
0x18000566b  test    eax, eax
0x18000566d  jz      short loc_180005699
0x18000566f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005676  cmp     rcx, rsi
0x180005679  jz      short loc_180005699
0x18000567b  test    byte ptr [rcx+1Ch], 1
0x18000567f  jz      short loc_180005699
0x180005681  mov     rcx, [rcx+10h]
0x180005685  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000568c  mov     edx, 0D5h
0x180005691  mov     r9d, eax
0x180005694  call    WPP_SF_d
0x180005699  mov     ecx, edi
0x18000569b  call    NetpNtStatusToApiStatus
0x1800056a0  mov     ebx, eax
0x1800056a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056a9  cmp     rcx, rsi
0x1800056ac  jz      short loc_1800056C9
0x1800056ae  test    byte ptr [rcx+1Ch], 1
0x1800056b2  jz      short loc_1800056C9
0x1800056b4  mov     rcx, [rcx+10h]
0x1800056b8  mov     edx, 0D6h
0x1800056bd  mov     r9d, edi
0x1800056c0  mov     dword ptr [rsp+88h+ReturnLength], ebx
0x1800056c4  call    WPP_SF_LL
0x1800056c9  mov     eax, ebx
0x1800056cb  mov     rcx, [rsp+88h+var_18]
0x1800056d0  xor     rcx, rsp; StackCookie
0x1800056d3  call    __security_check_cookie
0x1800056d8  lea     r11, [rsp+88h+var_8]
0x1800056e0  mov     rbx, [r11+18h]
0x1800056e4  mov     rsi, [r11+20h]
0x1800056e8  mov     rsp, r11
0x1800056eb  pop     rdi
0x1800056ec  retn
```
