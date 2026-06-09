# VerifyRpcAccess(void)

- ea: `0x180002f14`
- end: `0x180003229`
- name: `?VerifyRpcAccess@@YAXXZ`
- size: `789`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180002990`

## callees

- `0x18000195c`
- `0x1800024f0`
- `0x180002510`
- `0x180002f14`
- `0x1800032dc`
- `0x18001fe50`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x1800030b3`
- `RPCRT4!RpcImpersonateClient` at `0x18000302a`
- `RPCRT4!RpcImpersonateClient` at `0x18000302a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800030cf`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800030cf`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180003015`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180002f76`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180002f76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030dd`

## string_xrefs

- `0x180002fd1`: `admin\wmi\events\forwarding\collector\service\srvmain.cpp`
- `0x180003073`: `admin\wmi\events\forwarding\collector\service\srvmain.cpp`
- `0x18000312c`: `admin\wmi\events\forwarding\collector\service\srvmain.cpp`
- `0x1800031b1`: `admin\wmi\events\forwarding\collector\service\srvmain.cpp`

## pseudocode

```c
void VerifyRpcAccess(void)
{
  DWORD LastError; // ebx
  unsigned int v1; // eax
  unsigned int v2; // ebx
  DWORD v3; // ebx
  WINBOOL IsMember; // [rsp+60h] [rbp-29h] BYREF
  void **pExceptionObject; // [rsp+68h] [rbp-21h] BYREF
  char v6; // [rsp+70h] [rbp-19h]
  const char *v7; // [rsp+78h] [rbp-11h]
  __int64 v8; // [rsp+80h] [rbp-9h]
  __int64 v9; // [rsp+88h] [rbp-1h]
  int v10; // [rsp+90h] [rbp+7h]
  int v11; // [rsp+94h] [rbp+Bh]
  int v12; // [rsp+98h] [rbp+Fh]
  PSID SidToCheck; // [rsp+A0h] [rbp+17h] BYREF
  _BYTE v14[8]; // [rsp+A8h] [rbp+1Fh] BYREF
  RPC_STATUS (__stdcall *v15)(); // [rsp+B0h] [rbp+27h]
  _BYTE v16[8]; // [rsp+B8h] [rbp+2Fh] BYREF
  PVOID (__stdcall *v17)(PSID); // [rsp+C0h] [rbp+37h]
  PSID v18; // [rsp+C8h] [rbp+3Fh]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+D0h] [rbp+47h] BYREF

  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  SidToCheck = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0xBu, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_ca6bc7c05c2a3d506e8ee1e48e049877_Traceguids, LastError);
    }
    v6 = 0;
    v7 = "admin\\wmi\\events\\forwarding\\collector\\service\\srvmain.cpp";
    v8 = 0;
    v9 = 0;
    v10 = LastError;
    v11 = -1;
    v12 = 98;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v16[0] = 0;
  v17 = FreeSid;
  v18 = SidToCheck;
  v1 = RpcImpersonateClient(0);
  v2 = v1;
  if ( v1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_ca6bc7c05c2a3d506e8ee1e48e049877_Traceguids, v1);
    }
    v6 = 0;
    v7 = "admin\\wmi\\events\\forwarding\\collector\\service\\srvmain.cpp";
    v8 = 0;
    v9 = 0;
    v10 = v2;
    v11 = -1;
    v12 = 107;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v14[0] = 0;
  v15 = RpcRevertToSelf;
  IsMember = 0;
  if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
  {
    v3 = GetLastError();
    if ( !v3 )
      v3 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_ca6bc7c05c2a3d506e8ee1e48e049877_Traceguids, v3);
    }
    v6 = 0;
    v7 = "admin\\wmi\\events\\forwarding\\collector\\service\\srvmain.cpp";
    v8 = 0;
    v9 = 0;
    v10 = v3;
    v11 = -1;
    v12 = 115;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  if ( !IsMember )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_ca6bc7c05c2a3d506e8ee1e48e049877_Traceguids, 5);
    }
    v6 = 0;
    v7 = "admin\\wmi\\events\\forwarding\\collector\\service\\srvmain.cpp";
    v8 = 0;
    v9 = 0;
    v10 = 5;
    v11 = -1;
    v12 = 120;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(v14);
  wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(v16);
}

```

## disassembly

```asm
0x180002f14  mov     [rsp-8+arg_0], rbx
0x180002f19  mov     [rsp-8+arg_8], rdi
0x180002f1e  push    rbp
0x180002f1f  lea     rbp, [rsp-57h]
0x180002f24  sub     rsp, 0E0h
0x180002f2b  mov     rax, cs:__security_cookie
0x180002f32  xor     rax, rsp
0x180002f35  mov     [rbp+57h+var_8], rax
0x180002f39  xor     edi, edi
0x180002f3b  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x180002f3e  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180002f44  mov     [rbp+57h+SidToCheck], rdi
0x180002f48  lea     rax, [rbp+57h+SidToCheck]
0x180002f4c  mov     [rsp+0E0h+pSid], rax; pSid
0x180002f51  mov     [rsp+0E0h+nSubAuthority7], edi; nSubAuthority7
0x180002f55  mov     [rsp+0E0h+nSubAuthority6], edi; nSubAuthority6
0x180002f59  mov     [rsp+0E0h+nSubAuthority5], edi; nSubAuthority5
0x180002f5d  mov     [rsp+0E0h+nSubAuthority4], edi; nSubAuthority4
0x180002f61  mov     [rsp+0E0h+nSubAuthority3], edi; nSubAuthority3
0x180002f65  mov     [rsp+0E0h+nSubAuthority2], edi; nSubAuthority2
0x180002f69  xor     r9d, r9d; nSubAuthority1
0x180002f6c  lea     r8d, [rdi+0Bh]; nSubAuthority0
0x180002f70  mov     dl, 1; nSubAuthorityCount
0x180002f72  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180002f76  call    cs:__imp_AllocateAndInitializeSid
0x180002f7c  test    eax, eax
0x180002f7e  jnz     loc_180003011
0x180002f84  call    cs:__imp_GetLastError
0x180002f8a  mov     ebx, eax
0x180002f8c  mov     eax, 507h
0x180002f91  test    ebx, ebx
0x180002f93  cmovz   ebx, eax
0x180002f96  lea     rcx, WPP_GLOBAL_Control
0x180002f9d  mov     r10, cs:WPP_GLOBAL_Control
0x180002fa4  cmp     r10, rcx
0x180002fa7  jz      short loc_180002FCD
0x180002fa9  test    byte ptr [r10+1Ch], 10h
0x180002fae  jz      short loc_180002FCD
0x180002fb0  cmp     byte ptr [r10+19h], 2
0x180002fb5  jb      short loc_180002FCD
0x180002fb7  lea     edx, [rdi+0Dh]
0x180002fba  mov     r9d, ebx
0x180002fbd  lea     r8, WPP_ca6bc7c05c2a3d506e8ee1e48e049877_Traceguids
0x180002fc4  mov     rcx, [r10+10h]
0x180002fc8  call    WPP_SF_D
0x180002fcd  mov     [rbp+57h+var_70], dil
0x180002fd1  lea     rax, aAdminWmiEvents; "admin\\wmi\\events\\forwarding\\collect"...
0x180002fd8  mov     [rbp+57h+var_68], rax
0x180002fdc  mov     [rbp+57h+var_60], rdi
0x180002fe0  mov     [rbp+57h+var_58], rdi
0x180002fe4  mov     [rbp+57h+var_50], ebx
0x180002fe7  mov     [rbp+57h+var_4C], 0FFFFFFFFh
0x180002fee  mov     [rbp+57h+var_48], 62h ; 'b'
0x180002ff5  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180002ffc  mov     [rbp+57h+pExceptionObject], rax
0x180003000  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180003007  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000300b  call    _CxxThrowException_0
0x180003011  mov     rcx, [rbp+57h+SidToCheck]
0x180003015  mov     rax, cs:__imp_FreeSid
0x18000301c  mov     [rbp+57h+var_28], dil
0x180003020  mov     [rbp+57h+var_20], rax
0x180003024  mov     [rbp+57h+var_18], rcx
0x180003028  xor     ecx, ecx; BindingHandle
0x18000302a  call    cs:__imp_RpcImpersonateClient
0x180003030  mov     ebx, eax
0x180003032  test    eax, eax
0x180003034  jz      short loc_1800030B3
0x180003036  lea     rcx, WPP_GLOBAL_Control
0x18000303d  mov     r10, cs:WPP_GLOBAL_Control
0x180003044  cmp     r10, rcx
0x180003047  jz      short loc_18000306F
0x180003049  test    byte ptr [r10+1Ch], 10h
0x18000304e  jz      short loc_18000306F
0x180003050  cmp     byte ptr [r10+19h], 2
0x180003055  jb      short loc_18000306F
0x180003057  mov     edx, 0Eh
0x18000305c  mov     r9d, eax
0x18000305f  lea     r8, WPP_ca6bc7c05c2a3d506e8ee1e48e049877_Traceguids
0x180003066  mov     rcx, [r10+10h]
0x18000306a  call    WPP_SF_D
0x18000306f  mov     [rbp+57h+var_70], dil
0x180003073  lea     rax, aAdminWmiEvents; "admin\\wmi\\events\\forwarding\\collect"...
0x18000307a  mov     [rbp+57h+var_68], rax
0x18000307e  mov     [rbp+57h+var_60], rdi
0x180003082  mov     [rbp+57h+var_58], rdi
0x180003086  mov     [rbp+57h+var_50], ebx
0x180003089  mov     [rbp+57h+var_4C], 0FFFFFFFFh
0x180003090  mov     [rbp+57h+var_48], 6Bh ; 'k'
0x180003097  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000309e  mov     [rbp+57h+pExceptionObject], rax
0x1800030a2  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800030a9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800030ad  call    _CxxThrowException_0
0x1800030b3  mov     rax, cs:__imp_RpcRevertToSelf
0x1800030ba  mov     [rbp+57h+var_38], dil
0x1800030be  mov     [rbp+57h+var_30], rax
0x1800030c2  mov     [rbp+57h+IsMember], edi
0x1800030c5  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800030c9  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x1800030cd  xor     ecx, ecx; TokenHandle
0x1800030cf  call    cs:__imp_CheckTokenMembership
0x1800030d5  test    eax, eax
0x1800030d7  jnz     loc_18000316C
0x1800030dd  call    cs:__imp_GetLastError
0x1800030e3  mov     ebx, eax
0x1800030e5  mov     eax, 507h
0x1800030ea  test    ebx, ebx
0x1800030ec  cmovz   ebx, eax
0x1800030ef  lea     rcx, WPP_GLOBAL_Control
0x1800030f6  mov     r10, cs:WPP_GLOBAL_Control
0x1800030fd  cmp     r10, rcx
0x180003100  jz      short loc_180003128
0x180003102  test    byte ptr [r10+1Ch], 10h
0x180003107  jz      short loc_180003128
0x180003109  cmp     byte ptr [r10+19h], 2
0x18000310e  jb      short loc_180003128
0x180003110  mov     edx, 0Fh
0x180003115  mov     r9d, ebx
0x180003118  lea     r8, WPP_ca6bc7c05c2a3d506e8ee1e48e049877_Traceguids
0x18000311f  mov     rcx, [r10+10h]
0x180003123  call    WPP_SF_D
0x180003128  mov     [rbp+57h+var_70], dil
0x18000312c  lea     rax, aAdminWmiEvents; "admin\\wmi\\events\\forwarding\\collect"...
0x180003133  mov     [rbp+57h+var_68], rax
0x180003137  mov     [rbp+57h+var_60], rdi
0x18000313b  mov     [rbp+57h+var_58], rdi
0x18000313f  mov     [rbp+57h+var_50], ebx
0x180003142  mov     [rbp+57h+var_4C], 0FFFFFFFFh
0x180003149  mov     [rbp+57h+var_48], 73h ; 's'
0x180003150  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180003157  mov     [rbp+57h+pExceptionObject], rax
0x18000315b  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180003162  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180003166  call    _CxxThrowException_0
0x18000316c  cmp     [rbp+57h+IsMember], edi
0x18000316f  jnz     loc_1800031F5
0x180003175  lea     rcx, WPP_GLOBAL_Control
0x18000317c  mov     rax, cs:WPP_GLOBAL_Control
0x180003183  cmp     rax, rcx
0x180003186  jz      short loc_1800031AD
0x180003188  test    byte ptr [rax+1Ch], 10h
0x18000318c  jz      short loc_1800031AD
0x18000318e  cmp     byte ptr [rax+19h], 2
0x180003192  jb      short loc_1800031AD
0x180003194  mov     edx, 10h
0x180003199  lea     r9d, [rdx-0Bh]
0x18000319d  lea     r8, WPP_ca6bc7c05c2a3d506e8ee1e48e049877_Traceguids
0x1800031a4  mov     rcx, [rax+10h]
0x1800031a8  call    WPP_SF_D
0x1800031ad  mov     [rbp+57h+var_70], dil
0x1800031b1  lea     rax, aAdminWmiEvents; "admin\\wmi\\events\\forwarding\\collect"...
0x1800031b8  mov     [rbp+57h+var_68], rax
0x1800031bc  mov     [rbp+57h+var_60], rdi
0x1800031c0  mov     [rbp+57h+var_58], rdi
0x1800031c4  mov     [rbp+57h+var_50], 5
0x1800031cb  mov     [rbp+57h+var_4C], 0FFFFFFFFh
0x1800031d2  mov     [rbp+57h+var_48], 78h ; 'x'
0x1800031d9  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800031e0  mov     [rbp+57h+pExceptionObject], rax
0x1800031e4  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800031eb  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800031ef  call    _CxxThrowException_0
0x1800031f5  lea     rcx, [rbp+57h+var_38]
0x1800031f9  call    ??1?$ScopeGuardImpl0@P6AJXZ@wmi@@QEAA@XZ; wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(void)
0x1800031fe  nop
0x1800031ff  lea     rcx, [rbp+57h+var_28]
0x180003203  call    ??1?$ScopeGuardImpl1@P6AXPEAV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@ZPEAV12@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>(void)
0x180003208  mov     rcx, [rbp+57h+var_8]
0x18000320c  xor     rcx, rsp; StackCookie
0x18000320f  call    __security_check_cookie
0x180003214  lea     r11, [rsp+0E0h+var_s0]
0x18000321c  mov     rbx, [r11+10h]
0x180003220  mov     rdi, [r11+18h]
0x180003224  mov     rsp, r11
0x180003227  pop     rbp
0x180003228  retn
```
