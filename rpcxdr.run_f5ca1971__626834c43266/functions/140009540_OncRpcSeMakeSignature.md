# OncRpcSeMakeSignature

- ea: `0x140009540`
- end: `0x1400096f7`
- name: `OncRpcSeMakeSignature`
- size: `439`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140004958`
- `0x140009700`
- `0x14000993c`
- `0x14000b624`
- `0x14000bb64`

## callees

- `0x140001cac`
- `0x140001ef0`
- `0x1400020c0`
- `0x140009540`
- `0x14000a1ec`
- `0x140012838`
- `0x140015640`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400096c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400096c8`
- `ksecdd!MakeSignature` at `0x14000964f`
- `ksecdd!MakeSignature` at `0x14000964f`
- `ksecdd!MapSecurityError` at `0x14000965f`
- `ksecdd!MapSecurityError` at `0x14000965f`

## pseudocode

```c
__int64 __fastcall OncRpcSeMakeSignature(
        struct _SecHandle *a1,
        _DWORD *a2,
        __int64 a3,
        void *a4,
        unsigned int a5,
        void *a6,
        unsigned int a7,
        unsigned int *a8)
{
  PSecBuffer v8; // rbx
  unsigned int v12; // esi
  NTSTATUS v13; // ebx
  PSecBuffer pBuffers; // rcx
  struct _SecHandle *v15; // rcx
  __int64 v16; // rdi
  unsigned int Signature; // esi
  int v18; // eax
  _SecBufferDesc pMessage; // [rsp+30h] [rbp-71h] BYREF
  PCtxtHandle phContext; // [rsp+40h] [rbp-61h]
  _BYTE v22[64]; // [rsp+50h] [rbp-51h] BYREF

  v8 = (PSecBuffer)v22;
  pMessage.pBuffers = (PSecBuffer)v22;
  phContext = a1;
  *(_QWORD *)&pMessage.ulVersion = 0;
  if ( a3 )
    v12 = OncRpcBufMgrpContextNumDescriptorsSpannedFromPtr(a3, a4, a5, 0);
  else
    v12 = 1;
  pMessage.cBuffers = v12 + 1;
  if ( v12 + 1 > 4 )
  {
    v13 = NfsMemMgrBufferAllocate(1, 1347241300, 16 * (v12 + 1), &pMessage.pBuffers);
    if ( v13 < 0 )
    {
      pBuffers = pMessage.pBuffers;
      goto LABEL_16;
    }
    v8 = pMessage.pBuffers;
  }
  if ( a3 )
  {
    OncRpcBufMgrpContextConfigureSecBufsFromPtr(a3, (_DWORD)a4, a5, (_DWORD)v8);
  }
  else
  {
    v8->BufferType = 1;
    pMessage.pBuffers->pvBuffer = a4;
    pMessage.pBuffers->cbBuffer = a5;
  }
  v15 = phContext;
  v16 = v12;
  pMessage.pBuffers[v16].BufferType = 2;
  pMessage.pBuffers[v16].pvBuffer = a6;
  pMessage.pBuffers[v16].cbBuffer = a7;
  Signature = MakeSignature(v15, 0, &pMessage, 0);
  v13 = MapSecurityError(Signature);
  if ( v13 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids, (unsigned int)v13);
  }
  v18 = OncRpcSeSecStatusToGssMajor(Signature);
  pBuffers = pMessage.pBuffers;
  *a2 = v18;
  *a8 = pBuffers[v16].cbBuffer;
LABEL_16:
  if ( pBuffers != (PSecBuffer)v22 )
    ExFreePoolWithTag(pBuffers, 0x504D4554u);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140009540  push    rbp
0x140009542  push    rbx
0x140009543  push    rsi
0x140009544  push    rdi
0x140009545  push    r12
0x140009547  push    r13
0x140009549  push    r14
0x14000954b  push    r15
0x14000954d  lea     rbp, [rsp-7]
0x140009552  sub     rsp, 0A8h
0x140009559  mov     rax, cs:__security_cookie
0x140009560  xor     rax, rsp
0x140009563  mov     [rbp+3Fh+var_50], rax
0x140009567  mov     r13, [rbp+3Fh+arg_38]
0x14000956e  lea     rbx, [rbp+3Fh+var_90]
0x140009572  mov     r15d, [rbp+3Fh+arg_20]
0x140009576  mov     r14, r9
0x140009579  mov     [rbp+3Fh+pMessage.pBuffers], rbx
0x14000957d  mov     rdi, r8
0x140009580  mov     [rbp+3Fh+phContext], rcx
0x140009584  mov     r12, rdx
0x140009587  mov     qword ptr [rbp+3Fh+pMessage.ulVersion], 0
0x14000958f  test    r8, r8
0x140009592  jz      short loc_1400095A9
0x140009594  xor     r9d, r9d
0x140009597  mov     r8d, r15d
0x14000959a  mov     rdx, r14
0x14000959d  mov     rcx, rdi
0x1400095a0  call    OncRpcBufMgrpContextNumDescriptorsSpannedFromPtr
0x1400095a5  mov     esi, eax
0x1400095a7  jmp     short loc_1400095AE
0x1400095a9  mov     esi, 1
0x1400095ae  lea     eax, [rsi+1]
0x1400095b1  mov     [rbp+3Fh+pMessage.cBuffers], eax
0x1400095b4  cmp     eax, 4
0x1400095b7  jbe     short loc_1400095DE
0x1400095b9  lea     r8d, [rsi+1]
0x1400095bd  mov     edx, 504D4554h
0x1400095c2  shl     r8d, 4
0x1400095c6  lea     r9, [rbp+3Fh+pMessage.pBuffers]
0x1400095ca  mov     ecx, 1
0x1400095cf  call    NfsMemMgrBufferAllocate
0x1400095d4  mov     ebx, eax
0x1400095d6  test    eax, eax
0x1400095d8  js      short loc_1400095FB
0x1400095da  mov     rbx, [rbp+3Fh+pMessage.pBuffers]
0x1400095de  test    rdi, rdi
0x1400095e1  jz      short loc_140009604
0x1400095e3  mov     r9, rbx
0x1400095e6  mov     [rsp+0E0h+var_B8], 0
0x1400095eb  mov     r8d, r15d
0x1400095ee  mov     rdx, r14
0x1400095f1  mov     rcx, rdi
0x1400095f4  call    OncRpcBufMgrpContextConfigureSecBufsFromPtr
0x1400095f9  jmp     short loc_14000961A
0x1400095fb  mov     rcx, [rbp+3Fh+pMessage.pBuffers]
0x1400095ff  jmp     loc_1400096BA
0x140009604  mov     dword ptr [rbx+4], 1
0x14000960b  mov     rax, [rbp+3Fh+pMessage.pBuffers]
0x14000960f  mov     [rax+8], r14
0x140009613  mov     rax, [rbp+3Fh+pMessage.pBuffers]
0x140009617  mov     [rax], r15d
0x14000961a  mov     rax, [rbp+3Fh+pMessage.pBuffers]
0x14000961e  lea     r8, [rbp+3Fh+pMessage]; pMessage
0x140009622  mov     rdx, [rbp+3Fh+arg_28]
0x140009626  xor     r9d, r9d; MessageSeqNo
0x140009629  mov     rcx, [rbp+3Fh+phContext]; phContext
0x14000962d  mov     edi, esi
0x14000962f  add     rdi, rdi
0x140009632  mov     dword ptr [rax+rdi*8+4], 2
0x14000963a  mov     rax, [rbp+3Fh+pMessage.pBuffers]
0x14000963e  mov     [rax+rdi*8+8], rdx
0x140009643  mov     edx, [rbp+3Fh+arg_30]
0x140009646  mov     rax, [rbp+3Fh+pMessage.pBuffers]
0x14000964a  mov     [rax+rdi*8], edx
0x14000964d  xor     edx, edx; fQOP
0x14000964f  call    cs:__imp_MakeSignature
0x140009656  nop     dword ptr [rax+rax+00h]
0x14000965b  mov     ecx, eax; SecStatus
0x14000965d  mov     esi, eax
0x14000965f  call    cs:__imp_MapSecurityError
0x140009666  nop     dword ptr [rax+rax+00h]
0x14000966b  mov     ebx, eax
0x14000966d  test    eax, eax
0x14000966f  jns     short loc_1400096A4
0x140009671  mov     rcx, cs:WPP_GLOBAL_Control
0x140009678  lea     rax, WPP_GLOBAL_Control
0x14000967f  cmp     rcx, rax
0x140009682  jz      short loc_1400096A4
0x140009684  mov     edx, [rcx+2Ch]
0x140009687  test    dl, 40h
0x14000968a  jz      short loc_1400096A4
0x14000968c  mov     rcx, [rcx+18h]
0x140009690  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x140009697  mov     edx, 17h
0x14000969c  mov     r9d, ebx
0x14000969f  call    WPP_SF_d
0x1400096a4  mov     ecx, esi
0x1400096a6  call    OncRpcSeSecStatusToGssMajor
0x1400096ab  mov     rcx, [rbp+3Fh+pMessage.pBuffers]; P
0x1400096af  mov     [r12], eax
0x1400096b3  mov     eax, [rcx+rdi*8]
0x1400096b6  mov     [r13+0], eax
0x1400096ba  lea     rax, [rbp+3Fh+var_90]
0x1400096be  cmp     rcx, rax
0x1400096c1  jz      short loc_1400096D4
0x1400096c3  mov     edx, 504D4554h; Tag
0x1400096c8  call    cs:__imp_ExFreePoolWithTag
0x1400096cf  nop     dword ptr [rax+rax+00h]
0x1400096d4  mov     eax, ebx
0x1400096d6  mov     rcx, [rbp+3Fh+var_50]
0x1400096da  xor     rcx, rsp; StackCookie
0x1400096dd  call    __security_check_cookie
0x1400096e2  add     rsp, 0A8h
0x1400096e9  pop     r15
0x1400096eb  pop     r14
0x1400096ed  pop     r13
0x1400096ef  pop     r12
0x1400096f1  pop     rdi
0x1400096f2  pop     rsi
0x1400096f3  pop     rbx
0x1400096f4  pop     rbp
0x1400096f5  retn
```
