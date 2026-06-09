# WwanRpcServerStart(void)

- ea: `0x1800ab7d0`
- end: `0x1800abb1e`
- name: `?WwanRpcServerStart@@YAKXZ`
- size: `846`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180015ac8`

## callees

- `0x1800085d0`
- `0x180012300`
- `0x1800ab7d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab87c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab87c`
- `RPCRT4!RpcServerInqBindings` at `0x1800ab8db`
- `RPCRT4!RpcServerInqBindings` at `0x1800ab8db`
- `RPCRT4!RpcEpRegisterW` at `0x1800ab905`
- `RPCRT4!RpcEpRegisterW` at `0x1800ab943`
- `RPCRT4!RpcEpRegisterW` at `0x1800ab905`
- `RPCRT4!RpcEpRegisterW` at `0x1800ab943`
- `RPCRT4!RpcEpUnregister` at `0x1800abaaf`
- `RPCRT4!RpcEpUnregister` at `0x1800abac3`
- `RPCRT4!RpcEpUnregister` at `0x1800abaaf`
- `RPCRT4!RpcEpUnregister` at `0x1800abac3`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x1800aba2b`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x1800aba2b`
- `RPCRT4!RpcServerListen` at `0x1800aba4e`
- `RPCRT4!RpcServerListen` at `0x1800aba4e`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800ab99e`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800ab9f9`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800ab99e`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800ab9f9`
- `RPCRT4!RpcBindingVectorFree` at `0x1800abacd`
- `RPCRT4!RpcBindingVectorFree` at `0x1800abae5`
- `RPCRT4!RpcBindingVectorFree` at `0x1800abacd`
- `RPCRT4!RpcBindingVectorFree` at `0x1800abae5`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1800aba89`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1800aba9b`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1800aba89`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1800aba9b`
- `RPCRT4!RpcServerUseProtseqW` at `0x1800ab8ae`
- `RPCRT4!RpcServerUseProtseqW` at `0x1800ab8ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800abad7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800abaef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800abad7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800abaef`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800ab872`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800ab872`

## string_xrefs

- `0x1800ab882`: `ConvertStringSecurityDescriptorToSecurityDescriptor failed. Error = %d`
- `0x1800ab8f4`: `Wwan Service`
- `0x1800ab932`: `Wwan Service Second`

## pseudocode

```c
__int64 WwanRpcServerStart(void)
{
  __int64 LastError; // rbx
  unsigned int v1; // eax
  unsigned int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  __int64 result; // rax
  RPC_BINDING_VECTOR *BindingVector; // [rsp+40h] [rbp-59h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-51h] BYREF
  WCHAR StringSecurityDescriptor[72]; // [rsp+50h] [rbp-49h] BYREF

  wcscpy(StringSecurityDescriptor, L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;R;;;AC)");
  BindingVector = 0;
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    LastError = GetLastError();
    WwanLog::Error(
      "WwanRpcServerStart",
      0,
      L"ConvertStringSecurityDescriptorToSecurityDescriptor failed. Error = %d",
      LastError);
    return (unsigned int)LastError;
  }
  v1 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0, SecurityDescriptor);
  LODWORD(LastError) = v1;
  if ( v1 )
  {
    WwanLog::Error("WwanRpcServerStart", 0, L"RpcServerUseProtseq failed. Error = %d", v1);
    goto LABEL_26;
  }
  v2 = RpcServerInqBindings(&BindingVector);
  LODWORD(LastError) = v2;
  if ( v2 )
  {
    WwanLog::Error("WwanRpcServerStart", 0, L"RpcServerInqBindings failed. Error = %d", v2);
LABEL_26:
    LocalFree(SecurityDescriptor);
    return (unsigned int)LastError;
  }
  v3 = RpcEpRegisterW(qword_1800D1BE0, BindingVector, 0, (RPC_WSTR)L"Wwan Service");
  LODWORD(LastError) = v3;
  if ( v3 )
  {
    WwanLog::Error("WwanRpcServerStart", 0, L"RpcEpRegister failed for normal interface. Error = %d", v3);
LABEL_25:
    RpcBindingVectorFree(&BindingVector);
    goto LABEL_26;
  }
  v4 = RpcEpRegisterW(qword_1800CF9B0, BindingVector, 0, (RPC_WSTR)L"Wwan Service Second");
  LODWORD(LastError) = v4;
  if ( v4 )
  {
    WwanLog::Error("WwanRpcServerStart", 0, L"RpcEpRegister failed for appcontainer interface. Error = %d", v4);
LABEL_24:
    RpcEpUnregister(qword_1800CF9B0, BindingVector, 0);
    goto LABEL_25;
  }
  v5 = RpcServerRegisterIf3(qword_1800D1BE0, 0, 0, 40, 0, 0, 0, SecurityDescriptor);
  LODWORD(LastError) = v5;
  if ( v5 )
  {
    WwanLog::Error("WwanRpcServerStart", 0, L"RpcServerRegisterIfEx failed for normal interface. Error = %d", v5);
LABEL_23:
    RpcEpUnregister(qword_1800D1BE0, BindingVector, 0);
    goto LABEL_24;
  }
  v6 = RpcServerRegisterIf3(qword_1800CF9B0, 0, 0, 40, 0, 0, 0, SecurityDescriptor);
  LODWORD(LastError) = v6;
  if ( v6 )
  {
    WwanLog::Error("WwanRpcServerStart", 0, L"RpcServerRegisterIf3 failed for appcontainer interface. Error = %d", v6);
LABEL_22:
    RpcServerUnregisterIfEx(qword_1800CF9B0, 0, 0);
    goto LABEL_23;
  }
  LODWORD(LastError) = RpcServerRegisterAuthInfoW(0, 9u, 0, 0);
  if ( (_DWORD)LastError )
  {
    WwanLog::Error("WwanRpcServerStart", 0, L"RpcServerRegisterAuthInfo failed. Error = %d", (unsigned int)LastError);
LABEL_21:
    RpcServerUnregisterIfEx(qword_1800D1BE0, 0, 0);
    goto LABEL_22;
  }
  v7 = RpcServerListen(3u, 0x4D2u, 1u);
  LODWORD(LastError) = v7;
  if ( v7 && v7 != 1713 )
  {
    WwanLog::Error("WwanRpcServerStart", 0, L"RpcServerListen failed. Error = %d", v7);
    goto LABEL_21;
  }
  RpcBindingVectorFree(&BindingVector);
  LocalFree(SecurityDescriptor);
  result = 0;
  dword_1801528A8 = 1;
  return result;
}

```

## disassembly

```asm
0x1800ab7d0  mov     [rsp-8+arg_0], rbx
0x1800ab7d5  push    rbp
0x1800ab7d6  lea     rbp, [rsp-57h]
0x1800ab7db  sub     rsp, 0F0h
0x1800ab7e2  mov     rax, cs:__security_cookie
0x1800ab7e9  xor     rax, rsp
0x1800ab7ec  mov     [rbp+57h+var_10], rax
0x1800ab7f0  movaps  xmm0, xmmword ptr cs:aDAGrgwgxWdAGrg; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x1800ab7f7  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800ab7fb  movaps  xmm1, xmmword ptr cs:aDAGrgwgxWdAGrg+10h; "GWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)("...
0x1800ab802  lea     rcx, [rbp+57h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800ab806  movups  xmmword ptr [rbp+57h+StringSecurityDescriptor], xmm0
0x1800ab80a  xor     r9d, r9d; SecurityDescriptorSize
0x1800ab80d  mov     [rbp+57h+BindingVector], 0
0x1800ab815  movaps  xmm0, xmmword ptr cs:aDAGrgwgxWdAGrg+20h; "D)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;"...
0x1800ab81c  movups  [rbp+57h+var_80], xmm0
0x1800ab820  mov     [rbp+57h+SecurityDescriptor], 0
0x1800ab828  movaps  xmm0, xmmword ptr cs:aDAGrgwgxWdAGrg+40h; "C)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;AC)"
0x1800ab82f  lea     edx, [r9+1]; StringSDRevision
0x1800ab833  movups  [rbp+57h+var_90], xmm1
0x1800ab837  movaps  xmm1, xmmword ptr cs:aDAGrgwgxWdAGrg+30h; "GWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;G"...
0x1800ab83e  movups  [rbp+57h+var_60], xmm0
0x1800ab842  movaps  xmm0, xmmword ptr cs:aDAGrgwgxWdAGrg+60h; ";;GA;;;OW)(A;;GR;;;AC)"
0x1800ab849  movups  [rbp+57h+var_70], xmm1
0x1800ab84d  movaps  xmm1, xmmword ptr cs:aDAGrgwgxWdAGrg+50h; ";;;BA)(A;;GA;;;OW)(A;;GR;;;AC)"
0x1800ab854  movups  [rbp+57h+var_40], xmm0
0x1800ab858  movups  xmm0, xmmword ptr cs:aDAGrgwgxWdAGrg+7Eh; "R;;;AC)"
0x1800ab85f  movups  [rbp+57h+var_50], xmm1
0x1800ab863  movaps  xmm1, xmmword ptr cs:aDAGrgwgxWdAGrg+70h; "W)(A;;GR;;;AC)"
0x1800ab86a  movups  [rbp+57h+var_30], xmm1
0x1800ab86e  movups  [rbp+57h+var_30+0Eh], xmm0
0x1800ab872  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800ab878  test    eax, eax
0x1800ab87a  jnz     short loc_1800AB8A1
0x1800ab87c  call    cs:__imp_GetLastError
0x1800ab882  lea     r8, aConvertstrings; "ConvertStringSecurityDescriptorToSecuri"...
0x1800ab889  xor     edx, edx; struct _GUID *
0x1800ab88b  mov     r9d, eax
0x1800ab88e  lea     rcx, aWwanrpcservers; "WwanRpcServerStart"
0x1800ab895  mov     ebx, eax
0x1800ab897  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800ab89c  jmp     loc_1800ABADD
0x1800ab8a1  mov     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800ab8a5  lea     rcx, ProtSeq; "ncalrpc"
0x1800ab8ac  xor     edx, edx; MaxCalls
0x1800ab8ae  call    cs:__imp_RpcServerUseProtseqW
0x1800ab8b4  mov     ebx, eax
0x1800ab8b6  test    eax, eax
0x1800ab8b8  jz      short loc_1800AB8D7
0x1800ab8ba  lea     r8, aRpcserverusepr; "RpcServerUseProtseq failed. Error = %d"
0x1800ab8c1  mov     r9d, eax
0x1800ab8c4  lea     rcx, aWwanrpcservers; "WwanRpcServerStart"
0x1800ab8cb  xor     edx, edx; struct _GUID *
0x1800ab8cd  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800ab8d2  jmp     loc_1800ABAD3
0x1800ab8d7  lea     rcx, [rbp+57h+BindingVector]; BindingVector
0x1800ab8db  call    cs:__imp_RpcServerInqBindings
0x1800ab8e1  mov     ebx, eax
0x1800ab8e3  test    eax, eax
0x1800ab8e5  jz      short loc_1800AB8F0
0x1800ab8e7  lea     r8, aRpcserverinqbi; "RpcServerInqBindings failed. Error = %d"
0x1800ab8ee  jmp     short loc_1800AB8C1
0x1800ab8f0  mov     rdx, [rbp+57h+BindingVector]; BindingVector
0x1800ab8f4  lea     r9, Annotation; "Wwan Service"
0x1800ab8fb  xor     r8d, r8d; UuidVector
0x1800ab8fe  lea     rcx, qword_1800D1BE0; IfSpec
0x1800ab905  call    cs:__imp_RpcEpRegisterW
0x1800ab90b  mov     ebx, eax
0x1800ab90d  test    eax, eax
0x1800ab90f  jz      short loc_1800AB92E
0x1800ab911  mov     r9d, eax
0x1800ab914  lea     r8, aRpcepregisterF; "RpcEpRegister failed for normal interfa"...
0x1800ab91b  xor     edx, edx; struct _GUID *
0x1800ab91d  lea     rcx, aWwanrpcservers; "WwanRpcServerStart"
0x1800ab924  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800ab929  jmp     loc_1800ABAC9
0x1800ab92e  mov     rdx, [rbp+57h+BindingVector]; BindingVector
0x1800ab932  lea     r9, aWwanServiceSec; "Wwan Service Second"
0x1800ab939  xor     r8d, r8d; UuidVector
0x1800ab93c  lea     rcx, qword_1800CF9B0; IfSpec
0x1800ab943  call    cs:__imp_RpcEpRegisterW
0x1800ab949  xor     edx, edx; struct _GUID *
0x1800ab94b  mov     ebx, eax
0x1800ab94d  test    eax, eax
0x1800ab94f  jz      short loc_1800AB96C
0x1800ab951  mov     r9d, eax
0x1800ab954  lea     r8, aRpcepregisterF_0; "RpcEpRegister failed for appcontainer i"...
0x1800ab95b  lea     rcx, aWwanrpcservers; "WwanRpcServerStart"
0x1800ab962  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800ab967  jmp     loc_1800ABAB5
0x1800ab96c  mov     rax, [rbp+57h+SecurityDescriptor]
0x1800ab970  lea     rcx, qword_1800D1BE0
0x1800ab977  mov     [rsp+0F0h+var_B8], rax
0x1800ab97c  mov     r9d, 28h ; '('
0x1800ab982  mov     [rsp+0F0h+var_C0], 0
0x1800ab98b  xor     r8d, r8d
0x1800ab98e  mov     [rsp+0F0h+var_C8], 0
0x1800ab996  mov     [rsp+0F0h+var_D0], 0
0x1800ab99e  call    cs:__imp_RpcServerRegisterIf3
0x1800ab9a4  xor     edx, edx; struct _GUID *
0x1800ab9a6  mov     ebx, eax
0x1800ab9a8  test    eax, eax
0x1800ab9aa  jz      short loc_1800AB9C7
0x1800ab9ac  mov     r9d, eax
0x1800ab9af  lea     r8, aRpcserverregis_0; "RpcServerRegisterIfEx failed for normal"...
0x1800ab9b6  lea     rcx, aWwanrpcservers; "WwanRpcServerStart"
0x1800ab9bd  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800ab9c2  jmp     loc_1800ABAA1
0x1800ab9c7  mov     rax, [rbp+57h+SecurityDescriptor]
0x1800ab9cb  lea     rcx, qword_1800CF9B0
0x1800ab9d2  mov     [rsp+0F0h+var_B8], rax
0x1800ab9d7  mov     r9d, 28h ; '('
0x1800ab9dd  mov     [rsp+0F0h+var_C0], 0
0x1800ab9e6  xor     r8d, r8d
0x1800ab9e9  mov     [rsp+0F0h+var_C8], 0
0x1800ab9f1  mov     [rsp+0F0h+var_D0], 0
0x1800ab9f9  call    cs:__imp_RpcServerRegisterIf3
0x1800ab9ff  mov     ebx, eax
0x1800aba01  test    eax, eax
0x1800aba03  jz      short loc_1800ABA1F
0x1800aba05  mov     r9d, eax
0x1800aba08  lea     r8, aRpcserverregis; "RpcServerRegisterIf3 failed for appcont"...
0x1800aba0f  xor     edx, edx; struct _GUID *
0x1800aba11  lea     rcx, aWwanrpcservers; "WwanRpcServerStart"
0x1800aba18  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800aba1d  jmp     short loc_1800ABA8F
0x1800aba1f  xor     r9d, r9d; Arg
0x1800aba22  xor     r8d, r8d; GetKeyFn
0x1800aba25  xor     ecx, ecx; ServerPrincName
0x1800aba27  lea     edx, [r9+9]; AuthnSvc
0x1800aba2b  call    cs:__imp_RpcServerRegisterAuthInfoW
0x1800aba31  mov     ebx, eax
0x1800aba33  test    eax, eax
0x1800aba35  jz      short loc_1800ABA40
0x1800aba37  lea     r8, aRpcserverregis_1; "RpcServerRegisterAuthInfo failed. Error"...
0x1800aba3e  jmp     short loc_1800ABA6C
0x1800aba40  mov     ecx, 3; MinimumCallThreads
0x1800aba45  mov     edx, 4D2h; MaxCalls
0x1800aba4a  lea     r8d, [rcx-2]; DontWait
0x1800aba4e  call    cs:__imp_RpcServerListen
0x1800aba54  mov     ebx, eax
0x1800aba56  test    eax, eax
0x1800aba58  jz      loc_1800ABAE1
0x1800aba5e  cmp     eax, 6B1h
0x1800aba63  jz      short loc_1800ABAE1
0x1800aba65  lea     r8, aRpcserverliste; "RpcServerListen failed. Error = %d"
0x1800aba6c  mov     r9d, ebx
0x1800aba6f  lea     rcx, aWwanrpcservers; "WwanRpcServerStart"
0x1800aba76  xor     edx, edx; struct _GUID *
0x1800aba78  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800aba7d  xor     r8d, r8d; RundownContextHandles
0x1800aba80  lea     rcx, qword_1800D1BE0; IfSpec
0x1800aba87  xor     edx, edx; MgrTypeUuid
0x1800aba89  call    cs:__imp_RpcServerUnregisterIfEx
0x1800aba8f  xor     r8d, r8d; RundownContextHandles
0x1800aba92  lea     rcx, qword_1800CF9B0; IfSpec
0x1800aba99  xor     edx, edx; MgrTypeUuid
0x1800aba9b  call    cs:__imp_RpcServerUnregisterIfEx
0x1800abaa1  mov     rdx, [rbp+57h+BindingVector]; BindingVector
0x1800abaa5  lea     rcx, qword_1800D1BE0; IfSpec
0x1800abaac  xor     r8d, r8d; UuidVector
0x1800abaaf  call    cs:__imp_RpcEpUnregister
0x1800abab5  mov     rdx, [rbp+57h+BindingVector]; BindingVector
0x1800abab9  lea     rcx, qword_1800CF9B0; IfSpec
0x1800abac0  xor     r8d, r8d; UuidVector
0x1800abac3  call    cs:__imp_RpcEpUnregister
0x1800abac9  lea     rcx, [rbp+57h+BindingVector]; BindingVector
0x1800abacd  call    cs:__imp_RpcBindingVectorFree
0x1800abad3  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x1800abad7  call    cs:__imp_LocalFree
0x1800abadd  mov     eax, ebx
0x1800abadf  jmp     short loc_1800ABB01
0x1800abae1  lea     rcx, [rbp+57h+BindingVector]; BindingVector
0x1800abae5  call    cs:__imp_RpcBindingVectorFree
0x1800abaeb  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x1800abaef  call    cs:__imp_LocalFree
0x1800abaf5  xor     eax, eax
0x1800abaf7  mov     cs:dword_1801528A8, 1
0x1800abb01  mov     rcx, [rbp+57h+var_10]
0x1800abb05  xor     rcx, rsp; StackCookie
0x1800abb08  call    __security_check_cookie
0x1800abb0d  mov     rbx, [rsp+0F0h+arg_0]
0x1800abb15  add     rsp, 0F0h
0x1800abb1c  pop     rbp
0x1800abb1d  retn
```
