# Smb2GetNegotiateSecurityInfo

- ea: `0x14008ef9c`
- end: `0x14008f158`
- name: `Smb2GetNegotiateSecurityInfo`
- size: `444`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140090290`

## callees

- `0x140024260`
- `0x140038490`
- `0x14008ef9c`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14008f03e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14008f03e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008f0b3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008f0b3`
- `srvnet!SrvLibQueryCredentialHandle` at `0x14008f054`
- `srvnet!SrvLibQueryCredentialHandle` at `0x14008f054`
- `ksecdd!MapSecurityError` at `0x14008f137`
- `ksecdd!MapSecurityError` at `0x14008f137`
- `ksecdd!DeleteSecurityContext` at `0x14008f0e0`
- `ksecdd!DeleteSecurityContext` at `0x14008f0e0`
- `ksecdd!AcceptSecurityContext` at `0x14008f09a`
- `ksecdd!AcceptSecurityContext` at `0x14008f09a`

## pseudocode

```c
NTSTATUS __fastcall Smb2GetNegotiateSecurityInfo(_QWORD *a1, _DWORD *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rsi
  struct _SecHandle *CredentialHandle; // rax
  SECURITY_STATUS v7; // eax
  __int64 v8; // rdi
  SECURITY_STATUS v9; // r14d
  int v10; // ecx
  __int64 v11; // rsi
  __int64 v12; // rdi
  NTSTATUS result; // eax
  unsigned int pfContextAttr; // [rsp+50h] [rbp-19h] BYREF
  __int128 v15; // [rsp+58h] [rbp-11h] BYREF
  struct _SecBufferDesc pOutput; // [rsp+68h] [rbp-1h] BYREF
  SECURITY_INTEGER ptsExpiry; // [rsp+78h] [rbp+Fh] BYREF
  struct _SecHandle phContext; // [rsp+80h] [rbp+17h] BYREF

  pfContextAttr = 0;
  ptsExpiry.QuadPart = 0;
  phContext = 0;
  v4 = MEMORY[0xFFFFF78000000014];
  *a1 = 0;
  *a2 = 0;
  pOutput.cBuffers = 1;
  pOutput.pBuffers = (PSecBuffer)&v15;
  pOutput.ulVersion = 0;
  v15 = 0x200000000uLL;
  ExAcquireResourceSharedLite(&Smb2ExtensibleCredHandleLock, 1u);
  v5 = MEMORY[0xFFFFF78000000014];
  CredentialHandle = (struct _SecHandle *)SrvLibQueryCredentialHandle(Smb2ExtensibleCredentialHandle);
  v7 = AcceptSecurityContext(CredentialHandle, 0, 0, 0x120111u, 0x10u, &phContext, &pOutput, &pfContextAttr, &ptsExpiry);
  v8 = MEMORY[0xFFFFF78000000014];
  v9 = v7;
  ExReleaseResourceLite(&Smb2ExtensibleCredHandleLock);
  if ( v9 < 0 )
  {
    result = MapSecurityError(v9);
    if ( result == -1073741816 || result == -1073741570 )
      return -1073741623;
  }
  else
  {
    v10 = v15;
    v11 = v5 - v4;
    v12 = v8 - v4;
    if ( (_DWORD)v15 )
    {
      *a1 = *((_QWORD *)&v15 + 1);
      *a2 = v10;
    }
    DeleteSecurityContext(&phContext);
    if ( MEMORY[0xFFFFF78000000014] - v4 > 50000000 && (byte_14004C339 & 0x10) != 0 )
      McTemplateK0hxxxx_EtwWriteTransfer(
        (unsigned __int64)(v12 + ((unsigned __int128)(v12 * (__int128)(__int64)0xD6BF94D5E57A42BDuLL) >> 64)) >> 63,
        v11 / 10000000,
        v12 / 10000000,
        0,
        v11 / 10000000,
        v12 / 10000000,
        (MEMORY[0xFFFFF78000000014] - v4) / 10000000);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14008ef9c  mov     [rsp-8+arg_10], rbx
0x14008efa1  mov     [rsp-8+arg_18], rsi
0x14008efa6  push    rbp
0x14008efa7  push    rdi
0x14008efa8  push    r12
0x14008efaa  push    r14
0x14008efac  push    r15
0x14008efae  lea     rbp, [rsp-37h]
0x14008efb3  sub     rsp, 0A0h
0x14008efba  mov     rax, cs:__security_cookie
0x14008efc1  xor     rax, rsp
0x14008efc4  mov     [rbp+57h+var_30], rax
0x14008efc8  xorps   xmm0, xmm0
0x14008efcb  mov     [rbp+57h+var_70], 0
0x14008efd2  movups  xmmword ptr [rbp+57h+var_58.ulVersion], xmm0
0x14008efd6  mov     qword ptr [rbp+57h+var_48], 0
0x14008efde  mov     r12, rdx
0x14008efe1  xorps   xmm1, xmm1
0x14008efe4  lea     rax, [rbp+57h+var_68]
0x14008efe8  movups  [rbp+57h+var_68], xmm1
0x14008efec  mov     r15, rcx
0x14008efef  mov     rdi, 0FFFFF78000000014h
0x14008eff9  movups  xmmword ptr [rbp+57h+phContext.dwLower], xmm0
0x14008effd  mov     rbx, [rdi]
0x14008f000  mov     qword ptr [rcx], 0
0x14008f007  lea     rcx, Smb2ExtensibleCredHandleLock; Resource
0x14008f00e  mov     dword ptr [rdx], 0
0x14008f014  mov     dl, 1; Wait
0x14008f016  mov     [rbp+57h+var_58.cBuffers], 1
0x14008f01d  mov     [rbp+57h+var_58.pBuffers], rax
0x14008f021  mov     [rbp+57h+var_58.ulVersion], 0
0x14008f028  mov     qword ptr [rbp+57h+var_68+8], 0
0x14008f030  mov     dword ptr [rbp+57h+var_68], 0
0x14008f037  mov     dword ptr [rbp+57h+var_68+4], 2
0x14008f03e  call    cs:__imp_ExAcquireResourceSharedLite
0x14008f045  nop     dword ptr [rax+rax+00h]
0x14008f04a  mov     rsi, [rdi]
0x14008f04d  mov     rcx, cs:Smb2ExtensibleCredentialHandle
0x14008f054  call    cs:__imp_SrvLibQueryCredentialHandle
0x14008f05b  nop     dword ptr [rax+rax+00h]
0x14008f060  mov     r9d, 120111h; fContextReq
0x14008f066  xor     r8d, r8d; pInput
0x14008f069  mov     rcx, rax; phCredential
0x14008f06c  xor     edx, edx; phContext
0x14008f06e  lea     rax, [rbp+57h+var_48]
0x14008f072  mov     [rsp+0C0h+ptsExpiry], rax; ptsExpiry
0x14008f077  lea     rax, [rbp+57h+var_70]
0x14008f07b  mov     [rsp+0C0h+pfContextAttr], rax; pfContextAttr
0x14008f080  lea     rax, [rbp+57h+var_58]
0x14008f084  mov     [rsp+0C0h+pOutput], rax; pOutput
0x14008f089  lea     rax, [rbp+57h+phContext]
0x14008f08d  mov     [rsp+0C0h+phNewContext], rax; phNewContext
0x14008f092  mov     [rsp+0C0h+TargetDataRep], 10h; TargetDataRep
0x14008f09a  call    cs:__imp_AcceptSecurityContext
0x14008f0a1  nop     dword ptr [rax+rax+00h]
0x14008f0a6  mov     rdi, [rdi]
0x14008f0a9  lea     rcx, Smb2ExtensibleCredHandleLock; Resource
0x14008f0b0  mov     r14d, eax
0x14008f0b3  call    cs:__imp_ExReleaseResourceLite
0x14008f0ba  nop     dword ptr [rax+rax+00h]
0x14008f0bf  test    r14d, r14d
0x14008f0c2  js      short loc_14008F134
0x14008f0c4  mov     ecx, dword ptr [rbp+57h+var_68]
0x14008f0c7  sub     rsi, rbx
0x14008f0ca  sub     rdi, rbx
0x14008f0cd  test    ecx, ecx
0x14008f0cf  jz      short loc_14008F0DC
0x14008f0d1  mov     rax, qword ptr [rbp+57h+var_68+8]
0x14008f0d5  mov     [r15], rax
0x14008f0d8  mov     [r12], ecx
0x14008f0dc  lea     rcx, [rbp+57h+phContext]; phContext
0x14008f0e0  call    cs:__imp_DeleteSecurityContext
0x14008f0e7  nop     dword ptr [rax+rax+00h]
0x14008f0ec  mov     rcx, 0FFFFF78000000014h
0x14008f0f6  mov     rcx, [rcx]
0x14008f0f9  sub     rcx, rbx
0x14008f0fc  cmp     rcx, 2FAF080h
0x14008f103  jg      loc_14009BB54
0x14008f109  xor     eax, eax
0x14008f10b  mov     rcx, [rbp+57h+var_30]
0x14008f10f  xor     rcx, rsp; StackCookie
0x14008f112  call    __security_check_cookie
0x14008f117  lea     r11, [rsp+0C0h+var_20]
0x14008f11f  mov     rbx, [r11+40h]
0x14008f123  mov     rsi, [r11+48h]
0x14008f127  mov     rsp, r11
0x14008f12a  pop     r15
0x14008f12c  pop     r14
0x14008f12e  pop     r12
0x14008f130  pop     rdi
0x14008f131  pop     rbp
0x14008f132  retn
0x14008f134  mov     ecx, r14d; SecStatus
0x14008f137  call    cs:__imp_MapSecurityError
0x14008f13e  nop     dword ptr [rax+rax+00h]
0x14008f143  cmp     eax, 0C0000008h
0x14008f148  jz      short loc_14008F151
0x14008f14a  cmp     eax, 0C00000FEh
0x14008f14f  jnz     short loc_14008F10B
0x14008f151  mov     eax, 0C00000C9h
0x14008f156  jmp     short loc_14008F10B
0x14009bb54  test    cs:byte_14004C339, 10h
0x14009bb5b  jz      loc_14008F109
0x14009bb61  mov     r9, 0D6BF94D5E57A42BDh
0x14009bb6b  mov     rax, r9
0x14009bb6e  imul    rcx
0x14009bb71  mov     rax, r9
0x14009bb74  lea     r10, [rcx+rdx]
0x14009bb78  imul    rdi
0x14009bb7b  mov     rax, r9
0x14009bb7e  sar     r10, 17h
0x14009bb82  mov     rcx, r10
0x14009bb85  xor     r9d, r9d
0x14009bb88  shr     rcx, 3Fh
0x14009bb8c  add     r10, rcx
0x14009bb8f  lea     r8, [rdi+rdx]
0x14009bb93  mov     [rsp+0C0h+pOutput], r10
0x14009bb98  imul    rsi
0x14009bb9b  sar     r8, 17h
0x14009bb9f  add     rdx, rsi
0x14009bba2  mov     rcx, r8
0x14009bba5  sar     rdx, 17h
0x14009bba9  mov     rax, rdx
0x14009bbac  shr     rcx, 3Fh
0x14009bbb0  shr     rax, 3Fh
0x14009bbb4  add     r8, rcx
0x14009bbb7  add     rdx, rax
0x14009bbba  mov     [rsp+0C0h+phNewContext], r8
0x14009bbbf  mov     qword ptr [rsp+0C0h+TargetDataRep], rdx
0x14009bbc4  call    McTemplateK0hxxxx_EtwWriteTransfer
0x14009bbc9  nop
0x14009bbca  jmp     loc_14008F109
```
