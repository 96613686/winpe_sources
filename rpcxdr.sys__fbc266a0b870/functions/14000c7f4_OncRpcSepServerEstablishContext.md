# OncRpcSepServerEstablishContext

- ea: `0x14000c7f4`
- end: `0x14000ca4d`
- name: `OncRpcSepServerEstablishContext`
- size: `601`
- prototype: `__int64 __usercall@<rax>(PCredHandle phCredential@<rcx>, int, PCtxtHandle, __int64, __int64, PTimeStamp)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000bb64`

## callees

- `0x1400020c0`
- `0x14000a1ec`
- `0x14000c7f4`
- `0x140012838`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000c916`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c9b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c916`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c9b5`
- `ksecdd!AcceptSecurityContext` at `0x14000c8dd`
- `ksecdd!AcceptSecurityContext` at `0x14000c98a`
- `ksecdd!AcceptSecurityContext` at `0x14000c8dd`
- `ksecdd!AcceptSecurityContext` at `0x14000c98a`
- `ksecdd!MapSecurityError` at `0x14000c9e9`
- `ksecdd!MapSecurityError` at `0x14000c9e9`

## pseudocode

```c
__int64 __fastcall OncRpcSepServerEstablishContext(
        PCredHandle phCredential,
        _DWORD *a2,
        struct _SecHandle *a3,
        __int64 a4,
        int a5,
        PCtxtHandle phNewContext,
        _QWORD *a7,
        _DWORD *a8,
        PTimeStamp ptsExpiry)
{
  unsigned int v12; // ebx
  SECURITY_INTEGER *v13; // rdi
  struct _SecHandle *v14; // rsi
  SECURITY_STATUS v15; // eax
  PVOID v16; // r8
  SECURITY_STATUS v17; // ecx
  NTSTATUS v18; // ebx
  _DWORD v20[2]; // [rsp+50h] [rbp-31h] BYREF
  PVOID P; // [rsp+58h] [rbp-29h] BYREF
  struct _SecBufferDesc pOutput; // [rsp+60h] [rbp-21h] BYREF
  struct _SecBufferDesc pInput; // [rsp+70h] [rbp-11h] BYREF
  _DWORD v24[2]; // [rsp+80h] [rbp-1h] BYREF
  __int64 v25; // [rsp+88h] [rbp+7h]
  unsigned int pfContextAttr; // [rsp+C8h] [rbp+47h] BYREF

  v25 = a4;
  pInput.pBuffers = (PSecBuffer)v24;
  v24[0] = a5;
  pInput.cBuffers = 1;
  pOutput.pBuffers = (PSecBuffer)v20;
  pOutput.cBuffers = 1;
  pfContextAttr = 0;
  pInput.ulVersion = 0;
  v24[1] = 2;
  pOutput.ulVersion = 0;
  v20[1] = 2;
  v20[0] = 4096;
  P = 0;
  if ( (int)NfsMemMgrBufferAllocate(512, 1232291666, 4096, &P) < 0 )
    goto LABEL_2;
  v13 = ptsExpiry;
  v14 = phNewContext;
  v15 = AcceptSecurityContext(
          phCredential,
          a3,
          &pInput,
          byte_14001AA22 != 0 ? 1026 : 2,
          0x10u,
          phNewContext,
          &pOutput,
          &pfContextAttr,
          ptsExpiry);
  v12 = v15;
  if ( !v15 )
    goto LABEL_11;
  if ( v15 != 590610 )
  {
    if ( v20[0] <= 0x1000u )
      goto LABEL_9;
    ExFreePoolWithTag(P, 0x49734752u);
    P = 0;
    if ( (int)NfsMemMgrBufferAllocate(512, 1232291666, v20[0], &P) < 0 )
    {
LABEL_2:
      v12 = -2146893056;
      goto LABEL_9;
    }
    v12 = AcceptSecurityContext(
            phCredential,
            a3,
            &pInput,
            byte_14001AA22 != 0 ? 1026 : 2,
            0x10u,
            v14,
            &pOutput,
            &pfContextAttr,
            v13);
    if ( !v12 )
      goto LABEL_11;
  }
  if ( v12 == 590610 )
  {
LABEL_11:
    v16 = P;
    goto LABEL_12;
  }
LABEL_9:
  v16 = P;
  if ( P )
  {
    ExFreePoolWithTag(P, 0x49734752u);
    v16 = 0;
    P = 0;
  }
LABEL_12:
  *a8 = v20[0];
  *a7 = v16;
  *a2 = OncRpcSeSecStatusToGssMajor(v12);
  v18 = MapSecurityError(v17);
  if ( v18 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids, (unsigned int)v18);
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x14000c7f4  mov     [rsp-8+arg_0], rbx
0x14000c7f9  mov     [rsp-8+arg_10], rsi
0x14000c7fe  push    rbp
0x14000c7ff  push    rdi
0x14000c800  push    r12
0x14000c802  push    r14
0x14000c804  push    r15
0x14000c806  lea     rbp, [rsp-0Fh]
0x14000c80b  sub     rsp, 90h
0x14000c812  lea     rax, [rbp+2Fh+var_30]
0x14000c816  mov     [rbp+2Fh+var_28], r9
0x14000c81a  mov     [rbp+2Fh+pInput.pBuffers], rax
0x14000c81e  lea     r9, [rbp+2Fh+P]
0x14000c822  mov     eax, [rbp+2Fh+arg_20]
0x14000c825  mov     r15, rcx
0x14000c828  mov     ecx, 1
0x14000c82d  mov     [rbp+2Fh+var_30], eax
0x14000c830  lea     rax, [rbp+2Fh+var_60]
0x14000c834  mov     [rbp+2Fh+pInput.cBuffers], ecx
0x14000c837  mov     [rbp+2Fh+var_50.pBuffers], rax
0x14000c83b  mov     r14, r8
0x14000c83e  mov     eax, 1000h
0x14000c843  mov     [rbp+2Fh+var_50.cBuffers], ecx
0x14000c846  lea     ebx, [rcx+1]
0x14000c849  mov     [rbp+2Fh+arg_8], 0
0x14000c850  mov     r12, rdx
0x14000c853  mov     [rbp+2Fh+pInput.ulVersion], 0
0x14000c85a  mov     r8d, eax
0x14000c85d  mov     [rbp+2Fh+var_2C], ebx
0x14000c860  mov     edx, 49734752h
0x14000c865  mov     [rbp+2Fh+var_50.ulVersion], 0
0x14000c86c  mov     ecx, 200h
0x14000c871  mov     [rbp+2Fh+var_5C], ebx
0x14000c874  mov     [rbp+2Fh+var_60], eax
0x14000c877  mov     [rbp+2Fh+P], 0
0x14000c87f  call    NfsMemMgrBufferAllocate
0x14000c884  test    eax, eax
0x14000c886  jns     short loc_14000C892
0x14000c888  mov     ebx, 80090300h
0x14000c88d  jmp     loc_14000C9A4
0x14000c892  mov     al, cs:byte_14001AA22
0x14000c898  lea     r8, [rbp+2Fh+pInput]; pInput
0x14000c89c  mov     rdi, [rbp+2Fh+arg_40]
0x14000c8a0  neg     al
0x14000c8a2  mov     rsi, [rbp+2Fh+arg_28]
0x14000c8a6  lea     rax, [rbp+2Fh+arg_8]
0x14000c8aa  mov     [rsp+0B0h+ptsExpiry], rdi; ptsExpiry
0x14000c8af  sbb     r9d, r9d
0x14000c8b2  mov     [rsp+0B0h+pfContextAttr], rax; pfContextAttr
0x14000c8b7  and     r9d, 400h
0x14000c8be  lea     rax, [rbp+2Fh+var_50]
0x14000c8c2  add     r9d, ebx; fContextReq
0x14000c8c5  mov     [rsp+0B0h+pOutput], rax; pOutput
0x14000c8ca  mov     rdx, r14; phContext
0x14000c8cd  mov     [rsp+0B0h+phNewContext], rsi; phNewContext
0x14000c8d2  mov     rcx, r15; phCredential
0x14000c8d5  mov     [rsp+0B0h+TargetDataRep], 10h; TargetDataRep
0x14000c8dd  call    cs:__imp_AcceptSecurityContext
0x14000c8e4  nop     dword ptr [rax+rax+00h]
0x14000c8e9  mov     ebx, eax
0x14000c8eb  test    eax, eax
0x14000c8ed  jz      loc_14000C9CA
0x14000c8f3  cmp     eax, 90312h
0x14000c8f8  jz      loc_14000C99C
0x14000c8fe  cmp     [rbp+2Fh+var_60], 1000h
0x14000c905  jbe     loc_14000C9A4
0x14000c90b  mov     rcx, [rbp+2Fh+P]; P
0x14000c90f  mov     ebx, 49734752h
0x14000c914  mov     edx, ebx; Tag
0x14000c916  call    cs:__imp_ExFreePoolWithTag
0x14000c91d  nop     dword ptr [rax+rax+00h]
0x14000c922  mov     r8d, [rbp+2Fh+var_60]
0x14000c926  lea     r9, [rbp+2Fh+P]
0x14000c92a  mov     edx, ebx
0x14000c92c  mov     [rbp+2Fh+P], 0
0x14000c934  mov     ecx, 200h
0x14000c939  call    NfsMemMgrBufferAllocate
0x14000c93e  test    eax, eax
0x14000c940  js      loc_14000C888
0x14000c946  mov     al, cs:byte_14001AA22
0x14000c94c  lea     r8, [rbp+2Fh+pInput]; pInput
0x14000c950  neg     al
0x14000c952  mov     [rsp+0B0h+ptsExpiry], rdi; ptsExpiry
0x14000c957  lea     rax, [rbp+2Fh+arg_8]
0x14000c95b  mov     rdx, r14; phContext
0x14000c95e  mov     [rsp+0B0h+pfContextAttr], rax; pfContextAttr
0x14000c963  sbb     r9d, r9d
0x14000c966  lea     rax, [rbp+2Fh+var_50]
0x14000c96a  and     r9d, 400h
0x14000c971  mov     [rsp+0B0h+pOutput], rax; pOutput
0x14000c976  add     r9d, 2; fContextReq
0x14000c97a  mov     [rsp+0B0h+phNewContext], rsi; phNewContext
0x14000c97f  mov     rcx, r15; phCredential
0x14000c982  mov     [rsp+0B0h+TargetDataRep], 10h; TargetDataRep
0x14000c98a  call    cs:__imp_AcceptSecurityContext
0x14000c991  nop     dword ptr [rax+rax+00h]
0x14000c996  mov     ebx, eax
0x14000c998  test    eax, eax
0x14000c99a  jz      short loc_14000C9CA
0x14000c99c  cmp     ebx, 90312h
0x14000c9a2  jz      short loc_14000C9CA
0x14000c9a4  mov     r8, [rbp+2Fh+P]
0x14000c9a8  test    r8, r8
0x14000c9ab  jz      short loc_14000C9CE
0x14000c9ad  mov     edx, 49734752h; Tag
0x14000c9b2  mov     rcx, r8; P
0x14000c9b5  call    cs:__imp_ExFreePoolWithTag
0x14000c9bc  nop     dword ptr [rax+rax+00h]
0x14000c9c1  xor     r8d, r8d
0x14000c9c4  mov     [rbp+2Fh+P], r8
0x14000c9c8  jmp     short loc_14000C9CE
0x14000c9ca  mov     r8, [rbp+2Fh+P]
0x14000c9ce  mov     rcx, [rbp+2Fh+arg_38]
0x14000c9d2  mov     eax, [rbp+2Fh+var_60]
0x14000c9d5  mov     [rcx], eax
0x14000c9d7  mov     ecx, ebx
0x14000c9d9  mov     rax, [rbp+2Fh+arg_30]
0x14000c9dd  mov     [rax], r8
0x14000c9e0  call    OncRpcSeSecStatusToGssMajor
0x14000c9e5  mov     [r12], eax
0x14000c9e9  call    cs:__imp_MapSecurityError
0x14000c9f0  nop     dword ptr [rax+rax+00h]
0x14000c9f5  mov     ebx, eax
0x14000c9f7  test    eax, eax
0x14000c9f9  jns     short loc_14000CA2E
0x14000c9fb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ca02  lea     rax, WPP_GLOBAL_Control
0x14000ca09  cmp     rcx, rax
0x14000ca0c  jz      short loc_14000CA2E
0x14000ca0e  mov     edx, [rcx+2Ch]
0x14000ca11  test    dl, 40h
0x14000ca14  jz      short loc_14000CA2E
0x14000ca16  mov     rcx, [rcx+18h]
0x14000ca1a  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x14000ca21  mov     edx, 16h
0x14000ca26  mov     r9d, ebx
0x14000ca29  call    WPP_SF_d
0x14000ca2e  lea     r11, [rsp+0B0h+var_20]
0x14000ca36  mov     eax, ebx
0x14000ca38  mov     rbx, [r11+30h]
0x14000ca3c  mov     rsi, [r11+40h]
0x14000ca40  mov     rsp, r11
0x14000ca43  pop     r15
0x14000ca45  pop     r14
0x14000ca47  pop     r12
0x14000ca49  pop     rdi
0x14000ca4a  pop     rbp
0x14000ca4b  retn
```
