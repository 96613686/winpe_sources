# UmpoRpcServerInit

- ea: `0x180014f78`
- end: `0x1800150e3`
- name: `UmpoRpcServerInit`
- size: `363`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ed10`

## callees

- `0x180010070`
- `0x180014f78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015048`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180015068`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180015068`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800150b0`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800150b0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001503e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001503e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800150c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800150c2`

## pseudocode

```c
__int64 UmpoRpcServerInit()
{
  __int64 v0; // rdx
  WCHAR *v1; // rax
  const wchar_t *v2; // rcx
  __int128 v3; // xmm1
  __int128 v4; // xmm0
  __int128 v5; // xmm1
  __int128 v6; // xmm0
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  DWORD LastError; // eax
  RPC_STATUS v18; // eax
  DWORD v19; // ebx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-198h] BYREF
  WCHAR StringSecurityDescriptor[184]; // [rsp+50h] [rbp-188h] BYREF

  v0 = 2;
  v1 = StringSecurityDescriptor;
  v2 = L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;AC)(A;;GR;;;S-1-15-3-1024-1502825166-196370834"
        "5-2616377461-2562897074-4192028372-3968301570-1997628692-1435953622)";
  do
  {
    v3 = *((_OWORD *)v2 + 1);
    *(_OWORD *)v1 = *(_OWORD *)v2;
    v4 = *((_OWORD *)v2 + 2);
    *((_OWORD *)v1 + 1) = v3;
    v5 = *((_OWORD *)v2 + 3);
    *((_OWORD *)v1 + 2) = v4;
    v6 = *((_OWORD *)v2 + 4);
    *((_OWORD *)v1 + 3) = v5;
    v7 = *((_OWORD *)v2 + 5);
    *((_OWORD *)v1 + 4) = v6;
    v8 = *((_OWORD *)v2 + 6);
    *((_OWORD *)v1 + 5) = v7;
    v9 = *((_OWORD *)v2 + 7);
    v2 += 64;
    *((_OWORD *)v1 + 6) = v8;
    *((_OWORD *)v1 + 7) = v9;
    v1 += 64;
    --v0;
  }
  while ( v0 );
  v10 = *(_OWORD *)v2;
  SecurityDescriptor = 0;
  v11 = *((_OWORD *)v2 + 1);
  *(_OWORD *)v1 = v10;
  v12 = *((_OWORD *)v2 + 2);
  *((_OWORD *)v1 + 1) = v11;
  v13 = *((_OWORD *)v2 + 3);
  *((_OWORD *)v1 + 2) = v12;
  v14 = *((_OWORD *)v2 + 4);
  *((_OWORD *)v1 + 3) = v13;
  v15 = *((_OWORD *)v2 + 5);
  *((_OWORD *)v1 + 4) = v14;
  v16 = *(_OWORD *)(v2 + 46);
  *((_OWORD *)v1 + 5) = v15;
  *(_OWORD *)(v1 + 46) = v16;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    LastError = GetLastError();
LABEL_8:
    v19 = LastError;
    goto LABEL_9;
  }
  v18 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0xAu, (RPC_WSTR)L"umpo", SecurityDescriptor);
  v19 = v18;
  if ( !v18 || v18 == 1740 )
  {
    LastError = RpcServerRegisterIf3(qword_18001B230, 0, 0, 49, 1234, 0, 0, SecurityDescriptor);
    goto LABEL_8;
  }
LABEL_9:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return v19;
}

```

## disassembly

```asm
0x180014f78  push    rbx
0x180014f7a  sub     rsp, 1D0h
0x180014f81  mov     rax, cs:__security_cookie
0x180014f88  xor     rax, rsp
0x180014f8b  mov     [rsp+1D8h+var_18], rax
0x180014f93  mov     edx, 2
0x180014f98  lea     rax, [rsp+1D8h+StringSecurityDescriptor]
0x180014f9d  lea     rcx, aDAGrgwgxWdAGrg; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x180014fa4  lea     r8d, [rdx+7Eh]
0x180014fa8  movups  xmm0, xmmword ptr [rcx]
0x180014fab  movups  xmm1, xmmword ptr [rcx+10h]
0x180014faf  movups  xmmword ptr [rax], xmm0
0x180014fb2  movups  xmm0, xmmword ptr [rcx+20h]
0x180014fb6  movups  xmmword ptr [rax+10h], xmm1
0x180014fba  movups  xmm1, xmmword ptr [rcx+30h]
0x180014fbe  movups  xmmword ptr [rax+20h], xmm0
0x180014fc2  movups  xmm0, xmmword ptr [rcx+40h]
0x180014fc6  movups  xmmword ptr [rax+30h], xmm1
0x180014fca  movups  xmm1, xmmword ptr [rcx+50h]
0x180014fce  movups  xmmword ptr [rax+40h], xmm0
0x180014fd2  movups  xmm0, xmmword ptr [rcx+60h]
0x180014fd6  movups  xmmword ptr [rax+50h], xmm1
0x180014fda  movups  xmm1, xmmword ptr [rcx+70h]
0x180014fde  add     rcx, r8
0x180014fe1  movups  xmmword ptr [rax+60h], xmm0
0x180014fe5  movups  xmmword ptr [rax+70h], xmm1
0x180014fe9  add     rax, r8
0x180014fec  sub     rdx, 1
0x180014ff0  jnz     short loc_180014FA8
0x180014ff2  movups  xmm0, xmmword ptr [rcx]
0x180014ff5  xor     r9d, r9d; SecurityDescriptorSize
0x180014ff8  mov     [rsp+1D8h+SecurityDescriptor], rdx
0x180014ffd  movups  xmm1, xmmword ptr [rcx+10h]
0x180015001  lea     r8, [rsp+1D8h+SecurityDescriptor]; SecurityDescriptor
0x180015006  movups  xmmword ptr [rax], xmm0
0x180015009  lea     edx, [r9+1]; StringSDRevision
0x18001500d  movups  xmm0, xmmword ptr [rcx+20h]
0x180015011  movups  xmmword ptr [rax+10h], xmm1
0x180015015  movups  xmm1, xmmword ptr [rcx+30h]
0x180015019  movups  xmmword ptr [rax+20h], xmm0
0x18001501d  movups  xmm0, xmmword ptr [rcx+40h]
0x180015021  movups  xmmword ptr [rax+30h], xmm1
0x180015025  movups  xmm1, xmmword ptr [rcx+50h]
0x180015029  movups  xmmword ptr [rax+40h], xmm0
0x18001502d  movups  xmm0, xmmword ptr [rcx+5Ch]
0x180015031  lea     rcx, [rsp+1D8h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180015036  movups  xmmword ptr [rax+50h], xmm1
0x18001503a  movups  xmmword ptr [rax+5Ch], xmm0
0x18001503e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180015044  test    eax, eax
0x180015046  jnz     short loc_180015050
0x180015048  call    cs:__imp_GetLastError
0x18001504e  jmp     short loc_1800150B6
0x180015050  mov     r9, [rsp+1D8h+SecurityDescriptor]; SecurityDescriptor
0x180015055  lea     r8, aUmpo; "umpo"
0x18001505c  mov     edx, 0Ah; MaxCalls
0x180015061  lea     rcx, Protseq; "ncalrpc"
0x180015068  call    cs:__imp_RpcServerUseProtseqEpW
0x18001506e  mov     ebx, eax
0x180015070  test    eax, eax
0x180015072  jz      short loc_18001507B
0x180015074  cmp     eax, 6CCh
0x180015079  jnz     short loc_1800150B8
0x18001507b  mov     rax, [rsp+1D8h+SecurityDescriptor]
0x180015080  lea     rcx, qword_18001B230
0x180015087  mov     [rsp+1D8h+var_1A0], rax
0x18001508c  mov     r9d, 31h ; '1'
0x180015092  mov     [rsp+1D8h+var_1A8], 0
0x18001509b  xor     r8d, r8d
0x18001509e  mov     [rsp+1D8h+var_1B0], 0
0x1800150a6  xor     edx, edx
0x1800150a8  mov     [rsp+1D8h+var_1B8], 4D2h
0x1800150b0  call    cs:__imp_RpcServerRegisterIf3
0x1800150b6  mov     ebx, eax
0x1800150b8  mov     rcx, [rsp+1D8h+SecurityDescriptor]; hMem
0x1800150bd  test    rcx, rcx
0x1800150c0  jz      short loc_1800150C8
0x1800150c2  call    cs:__imp_LocalFree
0x1800150c8  mov     eax, ebx
0x1800150ca  mov     rcx, [rsp+1D8h+var_18]
0x1800150d2  xor     rcx, rsp; StackCookie
0x1800150d5  call    __security_check_cookie
0x1800150da  add     rsp, 1D0h
0x1800150e1  pop     rbx
0x1800150e2  retn
```
