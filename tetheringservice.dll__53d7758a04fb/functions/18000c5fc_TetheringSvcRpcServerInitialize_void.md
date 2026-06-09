# TetheringSvcRpcServerInitialize(void)

- ea: `0x18000c5fc`
- end: `0x18000c850`
- name: `?TetheringSvcRpcServerInitialize@@YAKXZ`
- size: `596`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000b888`

## callees

- `0x180002590`
- `0x18000bf74`
- `0x18000c5fc`
- `0x1800315f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c674`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c674`
- `RPCRT4!RpcBindingVectorFree` at `0x18000c806`
- `RPCRT4!RpcBindingVectorFree` at `0x18000c806`
- `RPCRT4!RpcServerInqBindings` at `0x18000c718`
- `RPCRT4!RpcServerInqBindings` at `0x18000c718`
- `RPCRT4!RpcEpRegisterW` at `0x18000c7b4`
- `RPCRT4!RpcEpRegisterW` at `0x18000c7b4`
- `RPCRT4!RpcServerRegisterIf3` at `0x18000c77d`
- `RPCRT4!RpcServerRegisterIf3` at `0x18000c77d`
- `RPCRT4!RpcServerUseProtseqW` at `0x18000c6e3`
- `RPCRT4!RpcServerUseProtseqW` at `0x18000c6e3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000c65c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000c65c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c7eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c7f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c7eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c7f3`

## pseudocode

```c
__int64 TetheringSvcRpcServerInitialize(void)
{
  DWORD LastError; // eax
  DWORD v1; // ebx
  TetheringServiceTelemetry *v2; // rcx
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // r9
  unsigned int v6; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-C0h] BYREF
  RPC_BINDING_VECTOR *BindingVector; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR StringSecurityDescriptor[728]; // [rsp+50h] [rbp-B0h] BYREF

  BindingVector = 0;
  memcpy_0(
    StringSecurityDescriptor,
    L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;CO)(A;;GR;;;S-1-15-3-1)(A;;GR;;;S-1-15-3-2)(A;;GR;;;S-1-15-3-"
     "3)(A;;GR;;;S-1-15-3-1024-3370394368-3817654550-1919658829-3274896815-2391583585-3783478911-1164931198-2338837334)(A"
     ";;GRGW;;;S-1-15-3-1024-2376854566-714973910-1571250757-2327293875-1093179939-177522618-3998750142-2013394283)(A;;GR"
     "GW;;;S-1-15-2-155514346-2573954481-755741238-1654018636-1233331829-3075935687-2861478708)(A;;GRGW;;;S-1-15-2-112136"
     "6727-2517420131-1100342901-1044639592-4216533239-371662368-2140263060)(A;;GRGW;;;S-1-15-2-2543942650-389403887-2808"
     "249486-612059083-208952635-835677591-2189227231)(A;;GRGW;;;S-1-15-2-3801529221-2855318152-1555692692-2306892612-233"
     "8533892-3542301781-2904385964)",
    0x5A4u);
  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
    goto LABEL_9;
  LastError = GetLastError();
  v1 = LastError;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_18a7ed7453dd33af20c1feb47c4ff862_Traceguids, LastError);
    v2 = WPP_GLOBAL_Control;
  }
  if ( !v1 )
  {
LABEL_9:
    v6 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, SecurityDescriptor);
    v3 = v6;
    if ( v6 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_27;
      }
      v4 = 18;
    }
    else
    {
      v6 = RpcServerInqBindings(&BindingVector);
      v3 = v6;
      if ( v6 )
      {
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_27;
        }
        v4 = 19;
      }
      else
      {
        v6 = RpcServerRegisterIf3(qword_180034D10, 0, 0, 33, 1234, 0, 0, SecurityDescriptor);
        v3 = v6;
        if ( v6 )
        {
          v2 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_27;
          }
          v4 = 20;
        }
        else
        {
          v6 = RpcEpRegisterW(qword_180034D10, BindingVector, 0, 0);
          v3 = v6;
          if ( !v6 )
            goto LABEL_27;
          v2 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_27;
          }
          v4 = 21;
        }
      }
    }
    v5 = v6;
    goto LABEL_26;
  }
  v3 = 1338;
  if ( v2 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 )
  {
    v4 = 17;
    v5 = 1338;
LABEL_26:
    WPP_SF_d(*((_QWORD *)v2 + 2), v4, WPP_18a7ed7453dd33af20c1feb47c4ff862_Traceguids, v5);
  }
LABEL_27:
  LocalFree(SecurityDescriptor);
  LocalFree(0);
  if ( BindingVector )
    RpcBindingVectorFree(&BindingVector);
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_18a7ed7453dd33af20c1feb47c4ff862_Traceguids, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x18000c5fc  push    rbp
0x18000c5fe  push    rbx
0x18000c5ff  push    rsi
0x18000c600  push    r15
0x18000c602  lea     rbp, [rsp-518h]
0x18000c60a  sub     rsp, 618h
0x18000c611  mov     rax, cs:__security_cookie
0x18000c618  xor     rax, rsp
0x18000c61b  mov     [rbp+530h+var_30], rax
0x18000c622  lea     rcx, [rsp+630h+StringSecurityDescriptor]; void *
0x18000c627  mov     [rsp+630h+BindingVector], 0
0x18000c630  lea     rdx, aDAGrgwgxWdAGrg; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x18000c637  mov     r8d, 5A4h; Size
0x18000c63d  call    memcpy_0
0x18000c642  xor     r9d, r9d; SecurityDescriptorSize
0x18000c645  mov     [rsp+630h+SecurityDescriptor], 0
0x18000c64e  lea     r8, [rsp+630h+SecurityDescriptor]; SecurityDescriptor
0x18000c653  lea     rcx, [rsp+630h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18000c658  lea     edx, [r9+1]; StringSDRevision
0x18000c65c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000c662  lea     rsi, WPP_GLOBAL_Control
0x18000c669  lea     r15, WPP_18a7ed7453dd33af20c1feb47c4ff862_Traceguids
0x18000c670  test    eax, eax
0x18000c672  jnz     short loc_18000C6D2
0x18000c674  call    cs:__imp_GetLastError
0x18000c67a  mov     ebx, eax
0x18000c67c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c683  cmp     rcx, rsi
0x18000c686  jz      short loc_18000C6A9
0x18000c688  test    byte ptr [rcx+1Ch], 1
0x18000c68c  jz      short loc_18000C6A9
0x18000c68e  mov     rcx, [rcx+10h]
0x18000c692  mov     edx, 10h
0x18000c697  mov     r9d, eax
0x18000c69a  mov     r8, r15
0x18000c69d  call    WPP_SF_d
0x18000c6a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6a9  test    ebx, ebx
0x18000c6ab  jz      short loc_18000C6D2
0x18000c6ad  mov     ebx, 53Ah
0x18000c6b2  cmp     rcx, rsi
0x18000c6b5  jz      loc_18000C7E6
0x18000c6bb  test    byte ptr [rcx+1Ch], 1
0x18000c6bf  jz      loc_18000C7E6
0x18000c6c5  mov     edx, 11h
0x18000c6ca  mov     r9d, ebx
0x18000c6cd  jmp     loc_18000C7DA
0x18000c6d2  mov     r8, [rsp+630h+SecurityDescriptor]; SecurityDescriptor
0x18000c6d7  lea     rcx, Protseq; "ncalrpc"
0x18000c6de  mov     edx, 0Ah; MaxCalls
0x18000c6e3  call    cs:__imp_RpcServerUseProtseqW
0x18000c6e9  mov     ebx, eax
0x18000c6eb  test    eax, eax
0x18000c6ed  jz      short loc_18000C713
0x18000c6ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6f6  cmp     rcx, rsi
0x18000c6f9  jz      loc_18000C7E6
0x18000c6ff  test    byte ptr [rcx+1Ch], 1
0x18000c703  jz      loc_18000C7E6
0x18000c709  mov     edx, 12h
0x18000c70e  jmp     loc_18000C7D7
0x18000c713  lea     rcx, [rsp+630h+BindingVector]; BindingVector
0x18000c718  call    cs:__imp_RpcServerInqBindings
0x18000c71e  mov     ebx, eax
0x18000c720  test    eax, eax
0x18000c722  jz      short loc_18000C748
0x18000c724  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c72b  cmp     rcx, rsi
0x18000c72e  jz      loc_18000C7E6
0x18000c734  test    byte ptr [rcx+1Ch], 1
0x18000c738  jz      loc_18000C7E6
0x18000c73e  mov     edx, 13h
0x18000c743  jmp     loc_18000C7D7
0x18000c748  mov     rax, [rsp+630h+SecurityDescriptor]
0x18000c74d  lea     rcx, qword_180034D10
0x18000c754  mov     [rsp+630h+var_5F8], rax
0x18000c759  mov     r9d, 21h ; '!'
0x18000c75f  mov     [rsp+630h+var_600], 0
0x18000c768  xor     r8d, r8d
0x18000c76b  mov     [rsp+630h+var_608], 0
0x18000c773  xor     edx, edx
0x18000c775  mov     [rsp+630h+var_610], 4D2h
0x18000c77d  call    cs:__imp_RpcServerRegisterIf3
0x18000c783  mov     ebx, eax
0x18000c785  test    eax, eax
0x18000c787  jz      short loc_18000C7A2
0x18000c789  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c790  cmp     rcx, rsi
0x18000c793  jz      short loc_18000C7E6
0x18000c795  test    byte ptr [rcx+1Ch], 1
0x18000c799  jz      short loc_18000C7E6
0x18000c79b  mov     edx, 14h
0x18000c7a0  jmp     short loc_18000C7D7
0x18000c7a2  mov     rdx, [rsp+630h+BindingVector]; BindingVector
0x18000c7a7  lea     rcx, qword_180034D10; IfSpec
0x18000c7ae  xor     r9d, r9d; Annotation
0x18000c7b1  xor     r8d, r8d; UuidVector
0x18000c7b4  call    cs:__imp_RpcEpRegisterW
0x18000c7ba  mov     ebx, eax
0x18000c7bc  test    eax, eax
0x18000c7be  jz      short loc_18000C7E6
0x18000c7c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7c7  cmp     rcx, rsi
0x18000c7ca  jz      short loc_18000C7E6
0x18000c7cc  test    byte ptr [rcx+1Ch], 1
0x18000c7d0  jz      short loc_18000C7E6
0x18000c7d2  mov     edx, 15h
0x18000c7d7  mov     r9d, eax
0x18000c7da  mov     rcx, [rcx+10h]
0x18000c7de  mov     r8, r15
0x18000c7e1  call    WPP_SF_d
0x18000c7e6  mov     rcx, [rsp+630h+SecurityDescriptor]; hMem
0x18000c7eb  call    cs:__imp_LocalFree
0x18000c7f1  xor     ecx, ecx; hMem
0x18000c7f3  call    cs:__imp_LocalFree
0x18000c7f9  cmp     [rsp+630h+BindingVector], 0
0x18000c7ff  jz      short loc_18000C80C
0x18000c801  lea     rcx, [rsp+630h+BindingVector]; BindingVector
0x18000c806  call    cs:__imp_RpcBindingVectorFree
0x18000c80c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c813  cmp     rcx, rsi
0x18000c816  jz      short loc_18000C832
0x18000c818  test    byte ptr [rcx+1Ch], 4
0x18000c81c  jz      short loc_18000C832
0x18000c81e  mov     rcx, [rcx+10h]
0x18000c822  mov     edx, 16h
0x18000c827  mov     r9d, ebx
0x18000c82a  mov     r8, r15
0x18000c82d  call    WPP_SF_d
0x18000c832  mov     eax, ebx
0x18000c834  mov     rcx, [rbp+530h+var_30]
0x18000c83b  xor     rcx, rsp; StackCookie
0x18000c83e  call    __security_check_cookie
0x18000c843  add     rsp, 618h
0x18000c84a  pop     r15
0x18000c84c  pop     rsi
0x18000c84d  pop     rbx
0x18000c84e  pop     rbp
0x18000c84f  retn
```
