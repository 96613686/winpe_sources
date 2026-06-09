# StiRpcSecurityCallBack(void *,void *)

- ea: `0x18004f0a0`
- end: `0x18004f3c7`
- name: `?StiRpcSecurityCallBack@@YAJPEAX0@Z`
- size: `807`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180009474`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18000f4fc`
- `0x180011a94`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x180033cc0`
- `0x18004f0a0`

## import_xrefs

- `RPCRT4!RpcBindingInqAuthClientW` at `0x18004f10e`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x18004f10e`
- `RPCRT4!RpcStringBindingParseW` at `0x18004f1e4`
- `RPCRT4!RpcStringBindingParseW` at `0x18004f1e4`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18004f1b3`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18004f1b3`
- `RPCRT4!RpcStringFreeW` at `0x18004f387`
- `RPCRT4!RpcStringFreeW` at `0x18004f3a3`
- `RPCRT4!RpcStringFreeW` at `0x18004f387`
- `RPCRT4!RpcStringFreeW` at `0x18004f3a3`

## string_xrefs

- `0x18004f11a`: `STI Security:  Error calling RpcBindingInqAuthClient`
- `0x18004f140`: `STI Security:  Error calling RpcBindingInqAuthClient`
- `0x18004f158`: `STI Security: Error, client attempting to use weak authentication.`
- `0x18004f17e`: `STI Security: Error, client attempting to use weak authentication.`
- `0x18004f129`: `StiRpcSecurityCallBack`
- `0x18004f167`: `StiRpcSecurityCallBack`
- `0x18004f195`: `StiRpcSecurityCallBack`
- `0x18004f259`: `StiRpcSecurityCallBack`
- `0x18004f289`: `StiRpcSecurityCallBack`
- `0x18004f2a8`: `StiRpcSecurityCallBack`
- `0x18004f2d6`: `StiRpcSecurityCallBack`
- `0x18004f30d`: `StiRpcSecurityCallBack`
- `0x18004f33e`: `StiRpcSecurityCallBack`
- `0x18004f36e`: `StiRpcSecurityCallBack`
- `0x18004f24a`: `STI Security: We have a local client`
- `0x18004f270`: `STI Security: We have a local client`
- `0x18004f2fe`: `STI Security: Error 0x%08X calling RpcStringBindingParse`
- `0x18004f324`: `STI Security: Error 0x%08X calling RpcStringBindingParse`
- `0x18004f299`: `STI Security: Error, remote client attempting to connect to STI RPC server`
- `0x18004f2bf`: `STI Security: Error, remote client attempting to connect to STI RPC server`
- `0x18004f32f`: `STI Security: Error 0x%08X calling RpcBindingToStringBinding`
- `0x18004f355`: `STI Security: Error 0x%08X calling RpcBindingToStringBinding`

## pseudocode

```c
__int64 __fastcall StiRpcSecurityCallBack(void *a1, void *a2)
{
  unsigned int v3; // edi
  char *v4; // rbx
  void *v5; // rdx
  void *v6; // rax
  int v7; // edx
  int v8; // ecx
  char *v9; // rbx
  void *v10; // rdx
  void *v11; // rax
  int v12; // edx
  int v13; // ecx
  int v14; // ebx
  char *v15; // rbx
  void *v16; // rdx
  void *v17; // rax
  int v18; // edx
  int v19; // ecx
  char *v20; // rbx
  void *v21; // rdx
  void *v22; // rax
  int v23; // edx
  int v24; // ecx
  char *v25; // rbx
  void *v26; // rdx
  char *v27; // rbx
  void *v28; // rdx
  unsigned int AuthnLevel; // [rsp+30h] [rbp-D0h] BYREF
  RPC_WSTR StringBinding; // [rsp+38h] [rbp-C8h] BYREF
  RPC_WSTR Protseq; // [rsp+40h] [rbp-C0h] BYREF
  RPC_AUTHZ_HANDLE Privs; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v34[38]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v35[38]; // [rsp+180h] [rbp+80h] BYREF

  StringBinding = 0;
  Protseq = 0;
  Privs = 0;
  AuthnLevel = 0;
  v3 = RpcBindingInqAuthClientW(a2, &Privs, 0, &AuthnLevel, 0, 0);
  if ( v3 )
  {
    v4 = (char *)WiaTrace_TraceLog("STI Security:  Error calling RpcBindingInqAuthClient");
    WriteDbgTraceErrorWI("StiRpcSecurityCallBack", v4);
    WiaTrcLib::Free((WiaTrcLib *)v4, v5);
    v6 = (void *)WiaTrace_Trace("STI Security:  Error calling RpcBindingInqAuthClient");
LABEL_13:
    WiaTrace_ProcessTrace_Ex(v8, v7, (int)"StiRpcSecurityCallBack", 1, v6);
    goto LABEL_14;
  }
  if ( AuthnLevel < 5 )
  {
    v9 = (char *)WiaTrace_TraceLog("STI Security: Error, client attempting to use weak authentication.");
    WriteDbgTraceErrorWI("StiRpcSecurityCallBack", v9);
    WiaTrcLib::Free((WiaTrcLib *)v9, v10);
    v11 = (void *)WiaTrace_Trace("STI Security: Error, client attempting to use weak authentication.");
    WiaTrace_ProcessTrace_Ex(v13, v12, (int)"StiRpcSecurityCallBack", 1, v11);
    v3 = 5;
    goto LABEL_14;
  }
  v3 = RpcBindingToStringBindingW(a2, &StringBinding);
  if ( v3 )
  {
    v27 = (char *)WiaTrace_TraceLog("STI Security: Error 0x%08X calling RpcBindingToStringBinding");
    WriteDbgTraceErrorWI("StiRpcSecurityCallBack", v27);
    WiaTrcLib::Free((WiaTrcLib *)v27, v28);
    v6 = (void *)WiaTrace_Trace("STI Security: Error 0x%08X calling RpcBindingToStringBinding", v3);
    goto LABEL_13;
  }
  v3 = RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0);
  if ( v3 )
  {
    v25 = (char *)WiaTrace_TraceLog("STI Security: Error 0x%08X calling RpcStringBindingParse");
    WriteDbgTraceErrorWI("StiRpcSecurityCallBack", v25);
    WiaTrcLib::Free((WiaTrcLib *)v25, v26);
    v6 = (void *)WiaTrace_Trace("STI Security: Error 0x%08X calling RpcStringBindingParse", v3);
    goto LABEL_13;
  }
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v35, L"ncalrpc");
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v34, Protseq);
  v14 = CSimpleStringBase<unsigned short>::CompareNoCase(v35, v34);
  v34[0] = &CSimpleStringBase<unsigned short>::`vftable';
  CSimpleStringBase<unsigned short>::DeleteStorage(v34);
  if ( v14 )
  {
    v20 = (char *)WiaTrace_TraceLog("STI Security: Error, remote client attempting to connect to STI RPC server");
    WriteDbgTraceErrorWI("StiRpcSecurityCallBack", v20);
    WiaTrcLib::Free((WiaTrcLib *)v20, v21);
    v22 = (void *)WiaTrace_Trace("STI Security: Error, remote client attempting to connect to STI RPC server");
    WiaTrace_ProcessTrace_Ex(v24, v23, (int)"StiRpcSecurityCallBack", 1, v22);
    v3 = 5;
  }
  else
  {
    v15 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(32, 0, "STI Security: We have a local client");
    WriteDbgTraceInfoWI("StiRpcSecurityCallBack", v15);
    WiaTrcLib::Free((WiaTrcLib *)v15, v16);
    v17 = (void *)WiaTrace_TraceWithSubCompTraceLevel(32, 0, "STI Security: We have a local client");
    WiaTrace_ProcessTrace_Ex(v19, v18, (int)"StiRpcSecurityCallBack", 4, v17);
    v3 = 0;
  }
  v35[0] = &CSimpleStringBase<unsigned short>::`vftable';
  CSimpleStringBase<unsigned short>::DeleteStorage(v35);
LABEL_14:
  if ( StringBinding )
  {
    RpcStringFreeW(&StringBinding);
    StringBinding = 0;
  }
  if ( Protseq )
    RpcStringFreeW(&Protseq);
  return v3;
}

```

## disassembly

```asm
0x18004f0a0  push    rbp
0x18004f0a2  push    rbx
0x18004f0a3  push    rdi
0x18004f0a4  push    r15
0x18004f0a6  lea     rbp, [rsp-1C8h]
0x18004f0ae  sub     rsp, 2C8h
0x18004f0b5  mov     rax, cs:__security_cookie
0x18004f0bc  xor     rax, rsp
0x18004f0bf  mov     [rbp+1E0h+var_30], rax
0x18004f0c6  mov     rbx, rdx
0x18004f0c9  mov     [rsp+2E0h+AuthzSvc], 0; AuthzSvc
0x18004f0d2  mov     rcx, rbx; ClientBinding
0x18004f0d5  mov     [rsp+2E0h+StringBinding], 0
0x18004f0de  lea     r9, [rsp+2E0h+AuthnLevel]; AuthnLevel
0x18004f0e3  mov     [rsp+2E0h+Protseq], 0
0x18004f0ec  xor     r8d, r8d; ServerPrincName
0x18004f0ef  mov     [rsp+2E0h+Privs], 0
0x18004f0f8  lea     rdx, [rsp+2E0h+Privs]; Privs
0x18004f0fd  mov     [rsp+2E0h+AuthnLevel], 0
0x18004f105  mov     [rsp+2E0h+AuthnSvc], 0; AuthnSvc
0x18004f10e  call    cs:__imp_RpcBindingInqAuthClientW
0x18004f114  mov     edi, eax
0x18004f116  test    eax, eax
0x18004f118  jz      short loc_18004F151
0x18004f11a  lea     rcx, aStiSecurityErr_0; "STI Security:  Error calling RpcBinding"...
0x18004f121  call    WiaTrace_TraceLog
0x18004f126  mov     rdx, rax; char *
0x18004f129  lea     rcx, aStirpcsecurity; "StiRpcSecurityCallBack"
0x18004f130  mov     rbx, rax
0x18004f133  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004f138  mov     rcx, rbx; this
0x18004f13b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004f140  lea     rcx, aStiSecurityErr_0; "STI Security:  Error calling RpcBinding"...
0x18004f147  call    WiaTrace_Trace
0x18004f14c  jmp     loc_18004F363
0x18004f151  cmp     [rsp+2E0h+AuthnLevel], 5
0x18004f156  jnb     short loc_18004F1AB
0x18004f158  lea     rcx, aStiSecurityErr; "STI Security: Error, client attempting "...
0x18004f15f  call    WiaTrace_TraceLog
0x18004f164  mov     rdx, rax; char *
0x18004f167  lea     rcx, aStirpcsecurity; "StiRpcSecurityCallBack"
0x18004f16e  mov     rbx, rax
0x18004f171  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004f176  mov     rcx, rbx; this
0x18004f179  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004f17e  lea     rcx, aStiSecurityErr; "STI Security: Error, client attempting "...
0x18004f185  call    WiaTrace_Trace
0x18004f18a  mov     r9d, 1; int
0x18004f190  mov     [rsp+2E0h+AuthnSvc], rax; lpMem
0x18004f195  lea     r8, aStirpcsecurity; "StiRpcSecurityCallBack"
0x18004f19c  call    WiaTrace_ProcessTrace_Ex
0x18004f1a1  mov     edi, 5
0x18004f1a6  jmp     loc_18004F37A
0x18004f1ab  lea     rdx, [rsp+2E0h+StringBinding]; StringBinding
0x18004f1b0  mov     rcx, rbx; Binding
0x18004f1b3  call    cs:__imp_RpcBindingToStringBindingW
0x18004f1b9  mov     edi, eax
0x18004f1bb  test    eax, eax
0x18004f1bd  jnz     loc_18004F32D
0x18004f1c3  mov     rcx, [rsp+2E0h+StringBinding]; StringBinding
0x18004f1c8  lea     r8, [rsp+2E0h+Protseq]; Protseq
0x18004f1cd  mov     [rsp+2E0h+AuthzSvc], 0; NetworkOptions
0x18004f1d6  xor     r9d, r9d; NetworkAddr
0x18004f1d9  xor     edx, edx; ObjUuid
0x18004f1db  mov     [rsp+2E0h+AuthnSvc], 0; Endpoint
0x18004f1e4  call    cs:__imp_RpcStringBindingParseW
0x18004f1ea  mov     edi, eax
0x18004f1ec  test    eax, eax
0x18004f1ee  jnz     loc_18004F2FC
0x18004f1f4  lea     rdx, Protseq; "ncalrpc"
0x18004f1fb  lea     rcx, [rbp+1E0h+var_160]
0x18004f202  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18004f207  mov     rdx, [rsp+2E0h+Protseq]
0x18004f20c  lea     rcx, [rsp+2E0h+var_290]
0x18004f211  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18004f216  lea     rdx, [rsp+2E0h+var_290]
0x18004f21b  lea     rcx, [rbp+1E0h+var_160]
0x18004f222  call    ?CompareNoCase@?$CSimpleStringBase@G@@QEBAHAEBV1@H@Z; CSimpleStringBase<ushort>::CompareNoCase(CSimpleStringBase<ushort> const &,int)
0x18004f227  lea     r15, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18004f22e  mov     ebx, eax
0x18004f230  lea     rcx, [rsp+2E0h+var_290]
0x18004f235  mov     [rsp+2E0h+var_290], r15
0x18004f23a  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x18004f23f  test    ebx, ebx
0x18004f241  jnz     short loc_18004F299
0x18004f243  lea     edi, [rbx+20h]
0x18004f246  xor     edx, edx
0x18004f248  mov     ecx, edi
0x18004f24a  lea     r8, aStiSecurityWeH; "STI Security: We have a local client"
0x18004f251  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18004f256  mov     rdx, rax; char *
0x18004f259  lea     rcx, aStirpcsecurity; "StiRpcSecurityCallBack"
0x18004f260  mov     rbx, rax
0x18004f263  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18004f268  mov     rcx, rbx; this
0x18004f26b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004f270  lea     r8, aStiSecurityWeH; "STI Security: We have a local client"
0x18004f277  xor     edx, edx
0x18004f279  mov     ecx, edi
0x18004f27b  call    WiaTrace_TraceWithSubCompTraceLevel
0x18004f280  lea     r9d, [rdi-1Ch]; int
0x18004f284  mov     [rsp+2E0h+AuthnSvc], rax; lpMem
0x18004f289  lea     r8, aStirpcsecurity; "StiRpcSecurityCallBack"
0x18004f290  call    WiaTrace_ProcessTrace_Ex
0x18004f295  xor     edi, edi
0x18004f297  jmp     short loc_18004F2E7
0x18004f299  lea     rcx, aStiSecurityErr_2; "STI Security: Error, remote client atte"...
0x18004f2a0  call    WiaTrace_TraceLog
0x18004f2a5  mov     rdx, rax; char *
0x18004f2a8  lea     rcx, aStirpcsecurity; "StiRpcSecurityCallBack"
0x18004f2af  mov     rbx, rax
0x18004f2b2  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004f2b7  mov     rcx, rbx; this
0x18004f2ba  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004f2bf  lea     rcx, aStiSecurityErr_2; "STI Security: Error, remote client atte"...
0x18004f2c6  call    WiaTrace_Trace
0x18004f2cb  mov     r9d, 1; int
0x18004f2d1  mov     [rsp+2E0h+AuthnSvc], rax; lpMem
0x18004f2d6  lea     r8, aStirpcsecurity; "StiRpcSecurityCallBack"
0x18004f2dd  call    WiaTrace_ProcessTrace_Ex
0x18004f2e2  mov     edi, 5
0x18004f2e7  lea     rcx, [rbp+1E0h+var_160]
0x18004f2ee  mov     [rbp+1E0h+var_160], r15
0x18004f2f5  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x18004f2fa  jmp     short loc_18004F37A
0x18004f2fc  mov     edx, edi
0x18004f2fe  lea     rcx, aStiSecurityErr_1; "STI Security: Error 0x%08X calling RpcS"...
0x18004f305  call    WiaTrace_TraceLog
0x18004f30a  mov     rdx, rax; char *
0x18004f30d  lea     rcx, aStirpcsecurity; "StiRpcSecurityCallBack"
0x18004f314  mov     rbx, rax
0x18004f317  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004f31c  mov     rcx, rbx; this
0x18004f31f  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004f324  lea     rcx, aStiSecurityErr_1; "STI Security: Error 0x%08X calling RpcS"...
0x18004f32b  jmp     short loc_18004F35C
0x18004f32d  mov     edx, edi
0x18004f32f  lea     rcx, aStiSecurityErr_3; "STI Security: Error 0x%08X calling RpcB"...
0x18004f336  call    WiaTrace_TraceLog
0x18004f33b  mov     rdx, rax; char *
0x18004f33e  lea     rcx, aStirpcsecurity; "StiRpcSecurityCallBack"
0x18004f345  mov     rbx, rax
0x18004f348  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004f34d  mov     rcx, rbx; this
0x18004f350  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004f355  lea     rcx, aStiSecurityErr_3; "STI Security: Error 0x%08X calling RpcB"...
0x18004f35c  mov     edx, edi
0x18004f35e  call    WiaTrace_Trace
0x18004f363  mov     r9d, 1; int
0x18004f369  mov     [rsp+2E0h+AuthnSvc], rax; lpMem
0x18004f36e  lea     r8, aStirpcsecurity; "StiRpcSecurityCallBack"
0x18004f375  call    WiaTrace_ProcessTrace_Ex
0x18004f37a  cmp     [rsp+2E0h+StringBinding], 0
0x18004f380  jz      short loc_18004F396
0x18004f382  lea     rcx, [rsp+2E0h+StringBinding]; String
0x18004f387  call    cs:__imp_RpcStringFreeW
0x18004f38d  mov     [rsp+2E0h+StringBinding], 0
0x18004f396  cmp     [rsp+2E0h+Protseq], 0
0x18004f39c  jz      short loc_18004F3A9
0x18004f39e  lea     rcx, [rsp+2E0h+Protseq]; String
0x18004f3a3  call    cs:__imp_RpcStringFreeW
0x18004f3a9  mov     eax, edi
0x18004f3ab  mov     rcx, [rbp+1E0h+var_30]
0x18004f3b2  xor     rcx, rsp; StackCookie
0x18004f3b5  call    __security_check_cookie
0x18004f3ba  add     rsp, 2C8h
0x18004f3c1  pop     r15
0x18004f3c3  pop     rdi
0x18004f3c4  pop     rbx
0x18004f3c5  pop     rbp
0x18004f3c6  retn
```
