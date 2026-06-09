# InitializeSecurityContextA

- ea: `0x180003570`
- end: `0x1800035e5`
- name: `InitializeSecurityContextA`
- size: `117`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle phCredential, PCtxtHandle phContext, SEC_CHAR *pszTargetName, unsigned int fContextReq, unsigned int Reserved1, unsigned int TargetDataRep, PSecBufferDesc pInput, unsigned int Reserved2, PCtxtHandle phNewContext, PSecBufferDesc pOutput, unsigned int *pfContextAttr, PTimeStamp ptsExpiry)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003670`

## pseudocode

```c
SECURITY_STATUS __stdcall InitializeSecurityContextA(
        PCredHandle phCredential,
        PCtxtHandle phContext,
        SEC_CHAR *pszTargetName,
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
           0);
}

```

## disassembly

```asm
0x180003570  sub     rsp, 78h
0x180003574  mov     rax, [rsp+78h+ptsExpiry]
0x18000357c  mov     [rsp+78h+var_18], 0; unsigned __int8
0x180003581  mov     [rsp+78h+var_20], rax; union _LARGE_INTEGER *
0x180003586  mov     rax, [rsp+78h+pfContextAttr]
0x18000358e  mov     [rsp+78h+var_28], rax; unsigned int *
0x180003593  mov     rax, [rsp+78h+pOutput]
0x18000359b  mov     [rsp+78h+var_30], rax; struct _SecBufferDesc *
0x1800035a0  mov     rax, [rsp+78h+phNewContext]
0x1800035a8  mov     [rsp+78h+var_38], rax; struct _SecHandle *
0x1800035ad  mov     eax, [rsp+78h+Reserved2]
0x1800035b4  mov     [rsp+78h+var_40], eax; unsigned int
0x1800035b8  mov     rax, [rsp+78h+pInput]
0x1800035c0  mov     [rsp+78h+var_48], rax; struct _SecBufferDesc *
0x1800035c5  mov     eax, [rsp+78h+TargetDataRep]
0x1800035cc  mov     [rsp+78h+var_50], eax; unsigned int
0x1800035d0  mov     eax, [rsp+78h+Reserved1]
0x1800035d7  mov     [rsp+78h+var_58], eax; unsigned int
0x1800035db  call    ?InitializeSecurityContextCommon@@YAJPEAU_SecHandle@@0PEAXKKKPEAU_SecBufferDesc@@K02PEAKPEAT_LARGE_INTEGER@@E@Z; InitializeSecurityContextCommon(_SecHandle *,_SecHandle *,void *,ulong,ulong,ulong,_SecBufferDesc *,ulong,_SecHandle *,_SecBufferDesc *,ulong *,_LARGE_INTEGER *,uchar)
0x1800035e0  add     rsp, 78h
0x1800035e4  retn
```
