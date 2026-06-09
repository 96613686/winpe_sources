# InitializeSecurityContextW

- ea: `0x1800035f0`
- end: `0x180003665`
- name: `InitializeSecurityContextW`
- size: `117`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle phCredential, PCtxtHandle phContext, SEC_WCHAR *pszTargetName, unsigned int fContextReq, unsigned int Reserved1, unsigned int TargetDataRep, PSecBufferDesc pInput, unsigned int Reserved2, PCtxtHandle phNewContext, PSecBufferDesc pOutput, unsigned int *pfContextAttr, PTimeStamp ptsExpiry)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003670`

## pseudocode

```c
SECURITY_STATUS __stdcall InitializeSecurityContextW(
        PCredHandle phCredential,
        PCtxtHandle phContext,
        SEC_WCHAR *pszTargetName,
        unsigned int fContextReq,
        unsigned int Reserved1,
        unsigned int TargetDataRep,
        PSecBufferDesc pInput,
        unsigned int Reserved2,
        PCtxtHandle phNewContext,
        PSecBufferDesc pOutput,
        unsigned int *pfContextAttr,
        PTimeStamp ptsExpiry)
{
  return InitializeSecurityContextCommon(
           phCredential,
           phContext,
           pszTargetName,
           fContextReq,
           Reserved1,
           TargetDataRep,
           pInput,
           Reserved2,
           phNewContext,
           pOutput,
           pfContextAttr,
           ptsExpiry,
           1u);
}

```

## disassembly

```asm
0x1800035f0  sub     rsp, 78h
0x1800035f4  mov     rax, [rsp+78h+ptsExpiry]
0x1800035fc  mov     [rsp+78h+var_18], 1; unsigned __int8
0x180003601  mov     [rsp+78h+var_20], rax; union _LARGE_INTEGER *
0x180003606  mov     rax, [rsp+78h+pfContextAttr]
0x18000360e  mov     [rsp+78h+var_28], rax; unsigned int *
0x180003613  mov     rax, [rsp+78h+pOutput]
0x18000361b  mov     [rsp+78h+var_30], rax; struct _SecBufferDesc *
0x180003620  mov     rax, [rsp+78h+phNewContext]
0x180003628  mov     [rsp+78h+var_38], rax; struct _SecHandle *
0x18000362d  mov     eax, [rsp+78h+Reserved2]
0x180003634  mov     [rsp+78h+var_40], eax; unsigned int
0x180003638  mov     rax, [rsp+78h+pInput]
0x180003640  mov     [rsp+78h+var_48], rax; struct _SecBufferDesc *
0x180003645  mov     eax, [rsp+78h+TargetDataRep]
0x18000364c  mov     [rsp+78h+var_50], eax; unsigned int
0x180003650  mov     eax, [rsp+78h+Reserved1]
0x180003657  mov     [rsp+78h+var_58], eax; unsigned int
0x18000365b  call    ?InitializeSecurityContextCommon@@YAJPEAU_SecHandle@@0PEAXKKKPEAU_SecBufferDesc@@K02PEAKPEAT_LARGE_INTEGER@@E@Z; InitializeSecurityContextCommon(_SecHandle *,_SecHandle *,void *,ulong,ulong,ulong,_SecBufferDesc *,ulong,_SecHandle *,_SecBufferDesc *,ulong *,_LARGE_INTEGER *,uchar)
0x180003660  add     rsp, 78h
0x180003664  retn
```
