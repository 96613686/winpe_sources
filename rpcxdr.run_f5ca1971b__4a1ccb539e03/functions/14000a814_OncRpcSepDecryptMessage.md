# OncRpcSepDecryptMessage

- ea: `0x14000a814`
- end: `0x14000aa34`
- name: `OncRpcSepDecryptMessage`
- size: `544`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140009dc4`
- `0x14000b624`

## callees

- `0x140001100`
- `0x140001bf0`
- `0x140001ef0`
- `0x1400020c0`
- `0x140008968`
- `0x14000a1ec`
- `0x14000a814`
- `0x140012838`
- `0x140015840`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000aa26`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000aa26`
- `ksecdd!UnsealMessage` at `0x14000a8f9`
- `ksecdd!UnsealMessage` at `0x14000a8f9`
- `ksecdd!MapSecurityError` at `0x14000a912`
- `ksecdd!MapSecurityError` at `0x14000a912`

## pseudocode

```c
__int64 __fastcall OncRpcSepDecryptMessage(__int64 a1, _DWORD *a2, __int64 a3, void *a4, unsigned int a5)
{
  unsigned int v5; // r12d
  void *v6; // rsi
  PVOID v8; // r15
  void *v9; // rdx
  NTSTATUS v10; // edi
  PVOID v11; // rbx
  PVOID v12; // r13
  unsigned int v13; // eax
  SECURITY_STATUS v14; // ecx
  char *v15; // rbx
  __int64 v16; // rsi
  __int64 v17; // rax
  char *v18; // rbx
  char v20; // [rsp+20h] [rbp-50h]
  PVOID P; // [rsp+30h] [rbp-40h] BYREF
  __int128 v22; // [rsp+38h] [rbp-38h] BYREF
  _DWORD v23[2]; // [rsp+48h] [rbp-28h] BYREF
  PVOID v24; // [rsp+50h] [rbp-20h]
  size_t Size; // [rsp+58h] [rbp-18h]
  void *Src; // [rsp+60h] [rbp-10h]
  int v29; // [rsp+C8h] [rbp+58h] BYREF

  v5 = a5;
  v6 = a4;
  v8 = 0;
  P = 0;
  v9 = a4;
  v29 = 0;
  LOBYTE(a4) = 1;
  v22 = 0;
  if ( (unsigned int)OncRpcBufMgrpContextNumDescriptorsSpannedFromPtr(a3, v9, a5, a4) <= 1 )
  {
    v12 = 0;
    v11 = v6;
  }
  else
  {
    v10 = NfsMemMgrBufferAllocate(512, 1650739026, v5, &P);
    if ( v10 < 0 )
      goto LABEL_15;
    v8 = P;
    v20 = 1;
    v11 = P;
    OncRpcBufMgrpContextCoalesceToSingleBuffer(a3, v6, v5, P, v20);
    v12 = v8;
  }
  *((_QWORD *)&v22 + 1) = v23;
  *(_QWORD *)&v22 = 0x200000000LL;
  v23[1] = 10;
  v24 = v11;
  v23[0] = v5;
  Src = 0;
  Size = 0x100000000LL;
  v13 = UnsealMessage(a1, &v22, 0, &v29);
  *a2 = OncRpcSeSecStatusToGssMajor(v13);
  v10 = MapSecurityError(v14);
  if ( v10 >= 0 )
  {
    v15 = (char *)Src;
    v16 = (unsigned __int8)Src & 3;
    if ( ((unsigned __int8)Src & 3) != 0 )
      memmove((char *)Src - v16, Src, (unsigned int)Size);
    if ( v12 )
    {
      v10 = OncRpcBufMgrChainUserSuppliedBuffer(
              a3,
              (_DWORD)v8,
              v5,
              0,
              (__int64)&OncRpcSepFreeCoalescedDecryptBufferCallbackRoutine,
              0);
      if ( v10 < 0 )
      {
        ExFreePoolWithTag(v8, 0x62644752u);
        goto LABEL_15;
      }
      *(_QWORD *)(a3 + 40) = OncRpcBufMgrGetLastBufferDescriptor(a3);
    }
    v17 = *(_QWORD *)(a3 + 40);
    v18 = &v15[-v16];
    *(_QWORD *)(v17 + 64) = v18;
    *(_DWORD *)(v17 + 76) = Size + (_DWORD)v18 - *(_DWORD *)(v17 + 56);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids, (unsigned int)v10);
  }
LABEL_15:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids, (unsigned int)v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000a814  mov     [rsp-38h+arg_10], rbx
0x14000a819  mov     [rsp-38h+arg_8], rdx
0x14000a81e  mov     [rsp-38h+arg_0], rcx
0x14000a823  push    rbp
0x14000a824  push    rsi
0x14000a825  push    rdi
0x14000a826  push    r12
0x14000a828  push    r13
0x14000a82a  push    r14
0x14000a82c  push    r15
0x14000a82e  mov     rbp, rsp
0x14000a831  sub     rsp, 70h
0x14000a835  mov     r12d, [rbp+arg_20]
0x14000a839  mov     rsi, r9
0x14000a83c  mov     r14, r8
0x14000a83f  xor     r15d, r15d
0x14000a842  xorps   xmm0, xmm0
0x14000a845  mov     [rbp+P], r15
0x14000a849  mov     rdx, rsi
0x14000a84c  mov     [rbp+arg_18], r15d
0x14000a850  mov     rcx, r14
0x14000a853  mov     r9b, 1
0x14000a856  mov     r8d, r12d
0x14000a859  movups  [rbp+var_38], xmm0
0x14000a85d  call    OncRpcBufMgrpContextNumDescriptorsSpannedFromPtr
0x14000a862  cmp     eax, 1
0x14000a865  jbe     short loc_14000A8A9
0x14000a867  lea     r9, [rbp+P]
0x14000a86b  mov     r8d, r12d
0x14000a86e  mov     edx, 62644752h
0x14000a873  mov     ecx, 200h
0x14000a878  call    NfsMemMgrBufferAllocate
0x14000a87d  mov     edi, eax
0x14000a87f  test    eax, eax
0x14000a881  js      loc_14000A9D1
0x14000a887  mov     r15, [rbp+P]
0x14000a88b  mov     r8d, r12d
0x14000a88e  mov     r9, r15
0x14000a891  mov     byte ptr [rsp+70h+var_50], 1
0x14000a896  mov     rdx, rsi
0x14000a899  mov     rcx, r14
0x14000a89c  mov     rbx, r15
0x14000a89f  call    OncRpcBufMgrpContextCoalesceToSingleBuffer
0x14000a8a4  mov     r13, r15
0x14000a8a7  jmp     short loc_14000A8AF
0x14000a8a9  xor     r13d, r13d
0x14000a8ac  mov     rbx, rsi
0x14000a8af  mov     rcx, [rbp+arg_0]
0x14000a8b3  lea     rax, [rbp+var_28]
0x14000a8b7  lea     r9, [rbp+arg_18]
0x14000a8bb  mov     qword ptr [rbp+var_38+8], rax
0x14000a8bf  xor     r8d, r8d
0x14000a8c2  mov     dword ptr [rbp+var_38], 0
0x14000a8c9  lea     rdx, [rbp+var_38]
0x14000a8cd  mov     dword ptr [rbp+var_38+4], 2
0x14000a8d4  mov     [rbp+var_24], 0Ah
0x14000a8db  mov     [rbp+var_20], rbx
0x14000a8df  mov     [rbp+var_28], r12d
0x14000a8e3  mov     dword ptr [rbp+Size+4], 1
0x14000a8ea  mov     [rbp+Src], 0
0x14000a8f2  mov     dword ptr [rbp+Size], 0
0x14000a8f9  call    cs:__imp_UnsealMessage
0x14000a900  nop     dword ptr [rax+rax+00h]
0x14000a905  mov     ecx, eax
0x14000a907  call    OncRpcSeSecStatusToGssMajor
0x14000a90c  mov     rdx, [rbp+arg_8]
0x14000a910  mov     [rdx], eax
0x14000a912  call    cs:__imp_MapSecurityError
0x14000a919  nop     dword ptr [rax+rax+00h]
0x14000a91e  mov     edi, eax
0x14000a920  test    eax, eax
0x14000a922  jns     short loc_14000A960
0x14000a924  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a92b  lea     rbx, WPP_GLOBAL_Control
0x14000a932  cmp     rcx, rbx
0x14000a935  jz      loc_14000A9D8
0x14000a93b  mov     eax, [rcx+2Ch]
0x14000a93e  test    al, 40h
0x14000a940  jz      loc_14000A9D8
0x14000a946  mov     rcx, [rcx+18h]
0x14000a94a  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x14000a951  mov     edx, 1Ah
0x14000a956  mov     r9d, edi
0x14000a959  call    WPP_SF_d
0x14000a95e  jmp     short loc_14000A9D8
0x14000a960  mov     rbx, [rbp+Src]
0x14000a964  mov     esi, ebx
0x14000a966  and     esi, 3
0x14000a969  test    bl, 3
0x14000a96c  jz      short loc_14000A980
0x14000a96e  mov     r8d, dword ptr [rbp+Size]; Size
0x14000a972  mov     rcx, rbx
0x14000a975  sub     rcx, rsi; void *
0x14000a978  mov     rdx, rbx; Src
0x14000a97b  call    memmove
0x14000a980  test    r13, r13
0x14000a983  jz      short loc_14000A9BD
0x14000a985  lea     rax, OncRpcSepFreeCoalescedDecryptBufferCallbackRoutine
0x14000a98c  mov     [rsp+70h+var_48], 0
0x14000a995  xor     r9d, r9d
0x14000a998  mov     [rsp+70h+var_50], rax
0x14000a99d  mov     r8d, r12d
0x14000a9a0  mov     rdx, r15
0x14000a9a3  mov     rcx, r14
0x14000a9a6  call    OncRpcBufMgrChainUserSuppliedBuffer
0x14000a9ab  mov     edi, eax
0x14000a9ad  test    eax, eax
0x14000a9af  js      short loc_14000AA1E
0x14000a9b1  mov     rcx, r14
0x14000a9b4  call    OncRpcBufMgrGetLastBufferDescriptor
0x14000a9b9  mov     [r14+28h], rax
0x14000a9bd  mov     rax, [r14+28h]
0x14000a9c1  sub     rbx, rsi
0x14000a9c4  mov     [rax+40h], rbx
0x14000a9c8  sub     ebx, [rax+38h]
0x14000a9cb  add     ebx, dword ptr [rbp+Size]
0x14000a9ce  mov     [rax+4Ch], ebx
0x14000a9d1  lea     rbx, WPP_GLOBAL_Control
0x14000a9d8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a9df  cmp     rcx, rbx
0x14000a9e2  jz      short loc_14000AA03
0x14000a9e4  mov     eax, [rcx+2Ch]
0x14000a9e7  test    al, 1
0x14000a9e9  jz      short loc_14000AA03
0x14000a9eb  mov     rcx, [rcx+18h]
0x14000a9ef  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x14000a9f6  mov     edx, 1Bh
0x14000a9fb  mov     r9d, edi
0x14000a9fe  call    WPP_SF_d
0x14000aa03  mov     rbx, [rsp+70h+arg_10]
0x14000aa0b  mov     eax, edi
0x14000aa0d  add     rsp, 70h
0x14000aa11  pop     r15
0x14000aa13  pop     r14
0x14000aa15  pop     r13
0x14000aa17  pop     r12
0x14000aa19  pop     rdi
0x14000aa1a  pop     rsi
0x14000aa1b  pop     rbp
0x14000aa1c  retn
0x14000aa1e  mov     edx, 62644752h; Tag
0x14000aa23  mov     rcx, r15; P
0x14000aa26  call    cs:__imp_ExFreePoolWithTag
0x14000aa2d  nop     dword ptr [rax+rax+00h]
0x14000aa32  jmp     short loc_14000A9D1
```
