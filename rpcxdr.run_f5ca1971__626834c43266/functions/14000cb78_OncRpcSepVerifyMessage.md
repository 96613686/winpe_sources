# OncRpcSepVerifyMessage

- ea: `0x14000cb78`
- end: `0x14000cdef`
- name: `OncRpcSepVerifyMessage`
- size: `631`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140009dc4`
- `0x14000b624`
- `0x14000bf88`

## callees

- `0x140001bf0`
- `0x140001cac`
- `0x140001ef0`
- `0x1400020c0`
- `0x14000a1ec`
- `0x14000cb78`
- `0x140012838`
- `0x140015640`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000cd79`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cd96`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cd79`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cd96`
- `ksecdd!VerifySignature` at `0x14000cd06`
- `ksecdd!VerifySignature` at `0x14000cd06`
- `ksecdd!MapSecurityError` at `0x14000cd1f`
- `ksecdd!MapSecurityError` at `0x14000cd1f`

## pseudocode

```c
__int64 __fastcall OncRpcSepVerifyMessage(
        struct _SecHandle *a1,
        _DWORD *a2,
        __int64 a3,
        void *a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        unsigned int a8)
{
  struct _SecBuffer *v8; // rbx
  void *v9; // r14
  __int64 v10; // rcx
  void *v11; // rax
  unsigned int v13; // eax
  unsigned int v14; // r13d
  int v15; // eax
  unsigned int v16; // esi
  int v17; // eax
  void *v18; // rax
  void *v19; // rdx
  struct _SecHandle *v20; // rcx
  __int64 v21; // rax
  unsigned int v22; // eax
  SECURITY_STATUS v23; // ecx
  void *v25; // [rsp+30h] [rbp-99h] BYREF
  struct _SecBuffer *v26; // [rsp+38h] [rbp-91h] BYREF
  __int64 v27; // [rsp+40h] [rbp-89h]
  void *v28; // [rsp+48h] [rbp-81h]
  __int64 v29; // [rsp+50h] [rbp-79h]
  struct _SecBufferDesc pMessage; // [rsp+58h] [rbp-71h] BYREF
  PCtxtHandle phContext; // [rsp+68h] [rbp-61h]
  _DWORD *v32; // [rsp+70h] [rbp-59h]
  _BYTE P[64]; // [rsp+80h] [rbp-49h] BYREF

  v8 = (struct _SecBuffer *)P;
  v9 = 0;
  phContext = a1;
  v10 = a7;
  v11 = a4;
  v27 = a7;
  v29 = a7;
  v28 = a4;
  v32 = a2;
  v25 = 0;
  v26 = (struct _SecBuffer *)P;
  pMessage = 0;
  if ( a3 )
  {
    LOBYTE(a4) = 1;
    v13 = OncRpcBufMgrpContextNumDescriptorsSpannedFromPtr(a3, v11, a5, a4);
    v10 = v27;
    v14 = v13;
  }
  else
  {
    v14 = 1;
  }
  if ( a6 )
  {
    LOBYTE(a4) = 1;
    if ( (unsigned int)OncRpcBufMgrpContextNumDescriptorsSpannedFromPtr(a6, v10, a8, a4) > 1 )
    {
      v15 = NfsMemMgrBufferAllocate(1, 1347241300, a8, &v25);
      v9 = v25;
      v16 = v15;
      if ( v15 < 0 )
        goto LABEL_17;
      v29 = (__int64)v25;
      OncRpcBufMgrpContextCoalesceToSingleBuffer(a6, v27, a8, v25, 1);
    }
  }
  if ( v14 + 1 <= 4
    || (v17 = NfsMemMgrBufferAllocate(1, 1347241300, 16 * (v14 + 1), &v26), v8 = v26, v16 = v17, v17 >= 0) )
  {
    pMessage.ulVersion = 0;
    pMessage.cBuffers = v14 + 1;
    pMessage.pBuffers = v8;
    if ( a3 )
    {
      OncRpcBufMgrpContextConfigureSecBufsFromPtr(a3, (_DWORD)v28, a5, (_DWORD)v8);
    }
    else
    {
      v18 = v28;
      v8->BufferType = 1;
      v8->pvBuffer = v18;
      v8->cbBuffer = a5;
    }
    v19 = (void *)v29;
    v20 = phContext;
    v21 = v14;
    v8[v21].BufferType = 2;
    v8[v21].pvBuffer = v19;
    v8[v21].cbBuffer = a8;
    v22 = VerifySignature(v20, &pMessage, 0, 0);
    *v32 = OncRpcSeSecStatusToGssMajor(v22);
    v16 = MapSecurityError(v23);
    if ( (v16 & 0x80000000) != 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids, v16);
    }
  }
LABEL_17:
  if ( v9 )
    ExFreePoolWithTag(v9, 0x504D4554u);
  if ( v8 != (struct _SecBuffer *)P )
    ExFreePoolWithTag(v8, 0x504D4554u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids, v16);
  return v16;
}

```

## disassembly

```asm
0x14000cb78  push    rbp
0x14000cb7a  push    rbx
0x14000cb7b  push    rsi
0x14000cb7c  push    r12
0x14000cb7e  push    r13
0x14000cb80  push    r14
0x14000cb82  push    r15
0x14000cb84  lea     rbp, [rsp-7]
0x14000cb89  sub     rsp, 0D0h
0x14000cb90  mov     rax, cs:__security_cookie
0x14000cb97  xor     rax, rsp
0x14000cb9a  mov     [rbp+37h+var_40], rax
0x14000cb9e  mov     r12, [rbp+37h+arg_28]
0x14000cba2  lea     rbx, [rbp+37h+P]
0x14000cba6  xor     r14d, r14d
0x14000cba9  mov     [rbp+37h+phContext], rcx
0x14000cbad  mov     rcx, [rbp+37h+arg_30]
0x14000cbb1  mov     rax, r9
0x14000cbb4  mov     [rsp+100h+var_C0], rcx
0x14000cbb9  xorps   xmm0, xmm0
0x14000cbbc  mov     [rbp+37h+var_B0], rcx
0x14000cbc0  mov     r15, r8
0x14000cbc3  mov     [rsp+100h+var_B8], rax
0x14000cbc8  mov     [rbp+37h+var_90], rdx
0x14000cbcc  mov     [rsp+100h+var_D0], r14
0x14000cbd1  mov     [rsp+100h+var_C8], rbx
0x14000cbd6  movups  xmmword ptr [rbp+37h+pMessage.ulVersion], xmm0
0x14000cbda  test    r8, r8
0x14000cbdd  jz      short loc_14000CBFB
0x14000cbdf  mov     r8d, [rbp+37h+arg_20]
0x14000cbe3  mov     r9b, 1
0x14000cbe6  mov     rdx, rax
0x14000cbe9  mov     rcx, r15
0x14000cbec  call    OncRpcBufMgrpContextNumDescriptorsSpannedFromPtr
0x14000cbf1  mov     rcx, [rsp+100h+var_C0]
0x14000cbf6  mov     r13d, eax
0x14000cbf9  jmp     short loc_14000CC01
0x14000cbfb  mov     r13d, 1
0x14000cc01  test    r12, r12
0x14000cc04  jz      short loc_14000CC62
0x14000cc06  mov     esi, [rbp+37h+arg_38]
0x14000cc09  mov     rdx, rcx
0x14000cc0c  mov     r8d, esi
0x14000cc0f  mov     rcx, r12
0x14000cc12  mov     r9b, 1
0x14000cc15  call    OncRpcBufMgrpContextNumDescriptorsSpannedFromPtr
0x14000cc1a  cmp     eax, 1
0x14000cc1d  jbe     short loc_14000CC62
0x14000cc1f  lea     r9, [rsp+100h+var_D0]
0x14000cc24  mov     r8d, esi
0x14000cc27  mov     edx, 504D4554h
0x14000cc2c  mov     ecx, 1
0x14000cc31  call    NfsMemMgrBufferAllocate
0x14000cc36  mov     r14, [rsp+100h+var_D0]
0x14000cc3b  mov     esi, eax
0x14000cc3d  test    eax, eax
0x14000cc3f  js      loc_14000CD65
0x14000cc45  mov     r8d, [rbp+37h+arg_38]
0x14000cc49  mov     r9, r14
0x14000cc4c  mov     rdx, [rsp+100h+var_C0]
0x14000cc51  mov     rcx, r12
0x14000cc54  mov     [rbp+37h+var_B0], r14
0x14000cc58  mov     [rsp+100h+var_E0], 1
0x14000cc5d  call    OncRpcBufMgrpContextCoalesceToSingleBuffer
0x14000cc62  lea     r12d, [r13+1]
0x14000cc66  cmp     r12d, 4
0x14000cc6a  jbe     short loc_14000CC97
0x14000cc6c  lea     r8d, [r13+1]
0x14000cc70  mov     edx, 504D4554h
0x14000cc75  shl     r8d, 4
0x14000cc79  lea     r9, [rsp+100h+var_C8]
0x14000cc7e  mov     ecx, 1
0x14000cc83  call    NfsMemMgrBufferAllocate
0x14000cc88  mov     rbx, [rsp+100h+var_C8]
0x14000cc8d  mov     esi, eax
0x14000cc8f  test    eax, eax
0x14000cc91  js      loc_14000CD65
0x14000cc97  mov     [rbp+37h+pMessage.ulVersion], 0
0x14000cc9e  mov     [rbp+37h+pMessage.cBuffers], r12d
0x14000cca2  mov     [rbp+37h+pMessage.pBuffers], rbx
0x14000cca6  test    r15, r15
0x14000cca9  jz      short loc_14000CCC6
0x14000ccab  mov     r8d, [rbp+37h+arg_20]
0x14000ccaf  mov     r9, rbx
0x14000ccb2  mov     rdx, [rsp+100h+var_B8]
0x14000ccb7  mov     rcx, r15
0x14000ccba  mov     [rsp+100h+var_D8], 1
0x14000ccbf  call    OncRpcBufMgrpContextConfigureSecBufsFromPtr
0x14000ccc4  jmp     short loc_14000CCDB
0x14000ccc6  mov     rax, [rsp+100h+var_B8]
0x14000cccb  mov     dword ptr [rbx+4], 1
0x14000ccd2  mov     [rbx+8], rax
0x14000ccd6  mov     eax, [rbp+37h+arg_20]
0x14000ccd9  mov     [rbx], eax
0x14000ccdb  mov     rdx, [rbp+37h+var_B0]
0x14000ccdf  xor     r9d, r9d; pfQOP
0x14000cce2  mov     rcx, [rbp+37h+phContext]; phContext
0x14000cce6  xor     r8d, r8d; MessageSeqNo
0x14000cce9  mov     eax, r13d
0x14000ccec  add     rax, rax
0x14000ccef  mov     dword ptr [rbx+rax*8+4], 2
0x14000ccf7  mov     [rbx+rax*8+8], rdx
0x14000ccfc  mov     edx, [rbp+37h+arg_38]
0x14000ccff  mov     [rbx+rax*8], edx
0x14000cd02  lea     rdx, [rbp+37h+pMessage]; pMessage
0x14000cd06  call    cs:__imp_VerifySignature
0x14000cd0d  nop     dword ptr [rax+rax+00h]
0x14000cd12  mov     ecx, eax
0x14000cd14  call    OncRpcSeSecStatusToGssMajor
0x14000cd19  mov     rdx, [rbp+37h+var_90]
0x14000cd1d  mov     [rdx], eax
0x14000cd1f  call    cs:__imp_MapSecurityError
0x14000cd26  nop     dword ptr [rax+rax+00h]
0x14000cd2b  mov     esi, eax
0x14000cd2d  test    eax, eax
0x14000cd2f  jns     short loc_14000CD65
0x14000cd31  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cd38  lea     r15, WPP_GLOBAL_Control
0x14000cd3f  cmp     rcx, r15
0x14000cd42  jz      short loc_14000CD6C
0x14000cd44  mov     eax, [rcx+2Ch]
0x14000cd47  test    al, 40h
0x14000cd49  jz      short loc_14000CD6C
0x14000cd4b  mov     rcx, [rcx+18h]
0x14000cd4f  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x14000cd56  mov     edx, 1Ch
0x14000cd5b  mov     r9d, esi
0x14000cd5e  call    WPP_SF_d
0x14000cd63  jmp     short loc_14000CD6C
0x14000cd65  lea     r15, WPP_GLOBAL_Control
0x14000cd6c  test    r14, r14
0x14000cd6f  jz      short loc_14000CD85
0x14000cd71  mov     edx, 504D4554h; Tag
0x14000cd76  mov     rcx, r14; P
0x14000cd79  call    cs:__imp_ExFreePoolWithTag
0x14000cd80  nop     dword ptr [rax+rax+00h]
0x14000cd85  lea     rax, [rbp+37h+P]
0x14000cd89  cmp     rbx, rax
0x14000cd8c  jz      short loc_14000CDA2
0x14000cd8e  mov     edx, 504D4554h; Tag
0x14000cd93  mov     rcx, rbx; P
0x14000cd96  call    cs:__imp_ExFreePoolWithTag
0x14000cd9d  nop     dword ptr [rax+rax+00h]
0x14000cda2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cda9  cmp     rcx, r15
0x14000cdac  jz      short loc_14000CDCD
0x14000cdae  mov     eax, [rcx+2Ch]
0x14000cdb1  test    al, 1
0x14000cdb3  jz      short loc_14000CDCD
0x14000cdb5  mov     rcx, [rcx+18h]
0x14000cdb9  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x14000cdc0  mov     edx, 1Dh
0x14000cdc5  mov     r9d, esi
0x14000cdc8  call    WPP_SF_d
0x14000cdcd  mov     eax, esi
0x14000cdcf  mov     rcx, [rbp+37h+var_40]
0x14000cdd3  xor     rcx, rsp; StackCookie
0x14000cdd6  call    __security_check_cookie
0x14000cddb  add     rsp, 0D0h
0x14000cde2  pop     r15
0x14000cde4  pop     r14
0x14000cde6  pop     r13
0x14000cde8  pop     r12
0x14000cdea  pop     rsi
0x14000cdeb  pop     rbx
0x14000cdec  pop     rbp
0x14000cded  retn
```
