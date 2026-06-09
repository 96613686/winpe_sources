# WepHostInitRPCServer(void)

- ea: `0x18000248c`
- end: `0x180002619`
- name: `?WepHostInitRPCServer@@YAJXZ`
- size: `397`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800030b8`

## callees

- `0x18000248c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800024c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800024c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800025a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800025a5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800024b8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800024b8`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x1800024f7`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x1800024f7`
- `RPCRT4!RpcServerRegisterIf3` at `0x180002542`
- `RPCRT4!RpcServerRegisterIf3` at `0x180002542`
- `RPCRT4!RpcServerInqBindings` at `0x18000255c`
- `RPCRT4!RpcServerInqBindings` at `0x18000255c`
- `RPCRT4!RpcEpRegisterW` at `0x18000257b`
- `RPCRT4!RpcEpRegisterW` at `0x18000257b`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1800025c0`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1800025c0`
- `RPCRT4!RpcEpUnregister` at `0x1800025db`
- `RPCRT4!RpcEpUnregister` at `0x1800025db`
- `RPCRT4!RpcBindingVectorFree` at `0x1800025e8`
- `RPCRT4!RpcBindingVectorFree` at `0x180002604`
- `RPCRT4!RpcBindingVectorFree` at `0x1800025e8`
- `RPCRT4!RpcBindingVectorFree` at `0x180002604`

## pseudocode

```c
__int64 WepHostInitRPCServer(void)
{
  int v0; // esi
  int v1; // edi
  signed int LastError; // eax
  signed int v3; // ebx
  RPC_STATUS v4; // eax
  RPC_BINDING_VECTOR *v5; // rax
  RPC_BINDING_VECTOR *BindingVector; // [rsp+60h] [rbp+20h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp+28h] BYREF

  v0 = 0;
  BindingVector = 0;
  SecurityDescriptor = 0;
  v1 = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)S:(ML;;NWNXNR;;;ME)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    v4 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0xAu, (RPC_WSTR)L"WEPHOST", SecurityDescriptor);
    if ( v4
      || (v4 = RpcServerRegisterIf3(qword_180005410, 0, 0, 41, 1234, 0, &WepHostCallback, SecurityDescriptor)) != 0
      && v4 != 1713
      || (v0 = 1, (v4 = RpcServerInqBindings(&BindingVector)) != 0)
      || (v4 = RpcEpRegisterW(qword_180005410, BindingVector, 0, (RPC_WSTR)L"WEPHOST")) != 0 )
    {
      v3 = (unsigned __int16)v4 | 0x80010000;
    }
    else
    {
      v5 = BindingVector;
      v3 = 0;
      BindingVector = 0;
      v1 = 1;
      g_pBindingVector = v5;
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( v3 < 0 )
  {
    if ( v0 )
      RpcServerUnregisterIfEx(qword_180005410, 0, 1);
    if ( v1 )
    {
      RpcEpUnregister(qword_180005410, g_pBindingVector, 0);
      RpcBindingVectorFree(&g_pBindingVector);
      g_pBindingVector = 0;
    }
    if ( BindingVector )
      RpcBindingVectorFree(&BindingVector);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000248c  mov     [rsp-18h+arg_10], rbx
0x180002491  push    rbp
0x180002492  push    rsi
0x180002493  push    rdi
0x180002494  mov     rbp, rsp
0x180002497  sub     rsp, 40h
0x18000249b  xor     esi, esi
0x18000249d  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800024a1  xor     r9d, r9d; SecurityDescriptorSize
0x1800024a4  mov     [rbp+BindingVector], rsi
0x1800024a8  lea     rcx, aDAGrgwgxWdAGrg; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x1800024af  mov     [rbp+SecurityDescriptor], rsi
0x1800024b3  xor     edi, edi
0x1800024b5  lea     edx, [rsi+1]; StringSDRevision
0x1800024b8  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800024be  test    eax, eax
0x1800024c0  jnz     short loc_1800024E0
0x1800024c2  call    cs:__imp_GetLastError
0x1800024c8  mov     ebx, eax
0x1800024ca  test    eax, eax
0x1800024cc  jle     loc_18000259C
0x1800024d2  movzx   ebx, ax
0x1800024d5  or      ebx, 80070000h
0x1800024db  jmp     loc_18000259C
0x1800024e0  mov     r9, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800024e4  lea     r8, Annotation; "WEPHOST"
0x1800024eb  mov     edx, 0Ah; MaxCalls
0x1800024f0  lea     rcx, Protseq; "ncalrpc"
0x1800024f7  call    cs:__imp_RpcServerUseProtseqEpW
0x1800024fd  test    eax, eax
0x1800024ff  jz      short loc_18000250F
0x180002501  movzx   ebx, ax
0x180002504  or      ebx, 80010000h
0x18000250a  jmp     loc_18000259C
0x18000250f  mov     rax, [rbp+SecurityDescriptor]
0x180002513  lea     rcx, qword_180005410
0x18000251a  mov     [rsp+40h+var_8], rax
0x18000251f  mov     r9d, 29h ; ')'
0x180002525  lea     rax, WepHostCallback
0x18000252c  xor     r8d, r8d
0x18000252f  mov     [rsp+40h+var_10], rax
0x180002534  xor     edx, edx
0x180002536  mov     [rsp+40h+var_18], esi
0x18000253a  mov     [rsp+40h+var_20], 4D2h
0x180002542  call    cs:__imp_RpcServerRegisterIf3
0x180002548  test    eax, eax
0x18000254a  jz      short loc_180002553
0x18000254c  cmp     eax, 6B1h
0x180002551  jnz     short loc_180002501
0x180002553  lea     rcx, [rbp+BindingVector]; BindingVector
0x180002557  mov     esi, 1
0x18000255c  call    cs:__imp_RpcServerInqBindings
0x180002562  test    eax, eax
0x180002564  jnz     short loc_180002501
0x180002566  mov     rdx, [rbp+BindingVector]; BindingVector
0x18000256a  lea     r9, Annotation; "WEPHOST"
0x180002571  xor     r8d, r8d; UuidVector
0x180002574  lea     rcx, qword_180005410; IfSpec
0x18000257b  call    cs:__imp_RpcEpRegisterW
0x180002581  test    eax, eax
0x180002583  jnz     loc_180002501
0x180002589  mov     rax, [rbp+BindingVector]
0x18000258d  xor     ebx, ebx
0x18000258f  mov     [rbp+BindingVector], rdi
0x180002593  mov     edi, esi
0x180002595  mov     cs:?g_pBindingVector@@3PEAU_RPC_BINDING_VECTOR@@EA, rax; _RPC_BINDING_VECTOR * g_pBindingVector
0x18000259c  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x1800025a0  test    rcx, rcx
0x1800025a3  jz      short loc_1800025AB
0x1800025a5  call    cs:__imp_LocalFree
0x1800025ab  test    ebx, ebx
0x1800025ad  jns     short loc_18000260A
0x1800025af  test    esi, esi
0x1800025b1  jz      short loc_1800025C6
0x1800025b3  xor     edx, edx; MgrTypeUuid
0x1800025b5  lea     rcx, qword_180005410; IfSpec
0x1800025bc  lea     r8d, [rdx+1]; RundownContextHandles
0x1800025c0  call    cs:__imp_RpcServerUnregisterIfEx
0x1800025c6  test    edi, edi
0x1800025c8  jz      short loc_1800025F9
0x1800025ca  mov     rdx, cs:?g_pBindingVector@@3PEAU_RPC_BINDING_VECTOR@@EA; BindingVector
0x1800025d1  lea     rcx, qword_180005410; IfSpec
0x1800025d8  xor     r8d, r8d; UuidVector
0x1800025db  call    cs:__imp_RpcEpUnregister
0x1800025e1  lea     rcx, ?g_pBindingVector@@3PEAU_RPC_BINDING_VECTOR@@EA; BindingVector
0x1800025e8  call    cs:__imp_RpcBindingVectorFree
0x1800025ee  mov     cs:?g_pBindingVector@@3PEAU_RPC_BINDING_VECTOR@@EA, 0; _RPC_BINDING_VECTOR * g_pBindingVector
0x1800025f9  cmp     [rbp+BindingVector], 0
0x1800025fe  jz      short loc_18000260A
0x180002600  lea     rcx, [rbp+BindingVector]; BindingVector
0x180002604  call    cs:__imp_RpcBindingVectorFree
0x18000260a  mov     eax, ebx
0x18000260c  mov     rbx, [rsp+40h+arg_10]
0x180002611  add     rsp, 40h
0x180002615  pop     rdi
0x180002616  pop     rsi
0x180002617  pop     rbp
0x180002618  retn
```
