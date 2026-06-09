# OncRpcSepQueryUserNameFromContext

- ea: `0x14000c56c`
- end: `0x14000c739`
- name: `OncRpcSepQueryUserNameFromContext`
- size: `461`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000bb64`

## callees

- `0x1400020c0`
- `0x14000a1ec`
- `0x14000c56c`
- `0x14000ca54`
- `0x140012838`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14000c6c7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000c6c7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c594`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c674`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c594`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c674`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c62a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c62a`
- `ksecdd!FreeContextBuffer` at `0x14000c651`
- `ksecdd!FreeContextBuffer` at `0x14000c651`
- `ksecdd!QueryContextAttributesW` at `0x14000c5b7`
- `ksecdd!QueryContextAttributesW` at `0x14000c5b7`
- `ksecdd!MapSecurityError` at `0x14000c5cd`
- `ksecdd!MapSecurityError` at `0x14000c5cd`

## pseudocode

```c
__int64 __fastcall OncRpcSepQueryUserNameFromContext(__int64 a1, _DWORD *a2)
{
  unsigned int v4; // eax
  SECURITY_STATUS v5; // ecx
  NTSTATUS v6; // ebx
  PVOID *v7; // rdi
  unsigned __int16 Length; // ax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-38h] BYREF
  WCHAR *pBuffer; // [rsp+60h] [rbp+8h] BYREF

  pBuffer = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  pBuffer = 0;
  v4 = QueryContextAttributesW((PCtxtHandle)(a1 + 88), 1u, &pBuffer);
  *a2 = OncRpcSeSecStatusToGssMajor(v4);
  v6 = MapSecurityError(v5);
  if ( v6 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, pBuffer);
    v7 = (PVOID *)(a1 + 168);
    v6 = NfsMemMgrBufferAllocate(512, 1316177746, DestinationString.Length, a1 + 168);
    if ( v6 >= 0 )
    {
      Length = DestinationString.Length;
      *(_WORD *)(a1 + 162) = DestinationString.Length;
      *(_WORD *)(a1 + 160) = Length;
      RtlCopyUnicodeString((PUNICODE_STRING)(a1 + 160), &DestinationString);
      v6 = OncRpcSepSplitUserNameIntoParts(a1 + 160, a1 + 176, a1 + 192);
      if ( v6 >= 0 )
      {
        *a2 = 0;
        goto LABEL_8;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          32,
          WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids,
          (unsigned int)v6);
      *a2 = 655360;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        31,
        WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids,
        (unsigned int)v6);
    v7 = (PVOID *)(a1 + 168);
  }
  if ( *v7 )
  {
    ExFreePoolWithTag(*v7, 0x4E734752u);
    *v7 = 0;
    *(_OWORD *)(a1 + 160) = 0;
  }
LABEL_8:
  if ( pBuffer )
    FreeContextBuffer(pBuffer);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000c56c  push    rbx
0x14000c56e  push    rsi
0x14000c56f  push    rdi
0x14000c570  push    r14
0x14000c572  sub     rsp, 38h
0x14000c576  mov     r14, rdx
0x14000c579  mov     [rsp+58h+pBuffer], 0
0x14000c582  mov     rsi, rcx
0x14000c585  xorps   xmm0, xmm0
0x14000c588  xor     edx, edx; SourceString
0x14000c58a  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x14000c58f  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x14000c594  call    cs:__imp_RtlInitUnicodeString
0x14000c59b  nop     dword ptr [rax+rax+00h]
0x14000c5a0  lea     rcx, [rsi+58h]; phContext
0x14000c5a4  mov     [rsp+58h+pBuffer], 0
0x14000c5ad  lea     r8, [rsp+58h+pBuffer]; pBuffer
0x14000c5b2  mov     edx, 1; ulAttribute
0x14000c5b7  call    cs:__imp_QueryContextAttributesW
0x14000c5be  nop     dword ptr [rax+rax+00h]
0x14000c5c3  mov     ecx, eax
0x14000c5c5  call    OncRpcSeSecStatusToGssMajor
0x14000c5ca  mov     [r14], eax
0x14000c5cd  call    cs:__imp_MapSecurityError
0x14000c5d4  nop     dword ptr [rax+rax+00h]
0x14000c5d9  mov     ebx, eax
0x14000c5db  test    eax, eax
0x14000c5dd  jns     loc_14000C66A
0x14000c5e3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c5ea  lea     rax, WPP_GLOBAL_Control
0x14000c5f1  cmp     rcx, rax
0x14000c5f4  jz      short loc_14000C616
0x14000c5f6  mov     edx, [rcx+2Ch]
0x14000c5f9  test    dl, 40h
0x14000c5fc  jz      short loc_14000C616
0x14000c5fe  mov     rcx, [rcx+18h]
0x14000c602  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x14000c609  mov     edx, 1Fh
0x14000c60e  mov     r9d, ebx
0x14000c611  call    WPP_SF_d
0x14000c616  lea     rdi, [rsi+0A8h]
0x14000c61d  mov     rcx, [rdi]; P
0x14000c620  test    rcx, rcx
0x14000c623  jz      short loc_14000C647
0x14000c625  mov     edx, 4E734752h; Tag
0x14000c62a  call    cs:__imp_ExFreePoolWithTag
0x14000c631  nop     dword ptr [rax+rax+00h]
0x14000c636  xorps   xmm0, xmm0
0x14000c639  mov     qword ptr [rdi], 0
0x14000c640  movups  xmmword ptr [rsi+0A0h], xmm0
0x14000c647  mov     rcx, [rsp+58h+pBuffer]; pvContextBuffer
0x14000c64c  test    rcx, rcx
0x14000c64f  jz      short loc_14000C65D
0x14000c651  call    cs:__imp_FreeContextBuffer
0x14000c658  nop     dword ptr [rax+rax+00h]
0x14000c65d  mov     eax, ebx
0x14000c65f  add     rsp, 38h
0x14000c663  pop     r14
0x14000c665  pop     rdi
0x14000c666  pop     rsi
0x14000c667  pop     rbx
0x14000c668  retn
0x14000c66a  mov     rdx, [rsp+58h+pBuffer]; SourceString
0x14000c66f  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x14000c674  call    cs:__imp_RtlInitUnicodeString
0x14000c67b  nop     dword ptr [rax+rax+00h]
0x14000c680  movzx   r8d, [rsp+58h+DestinationString.Length]
0x14000c686  lea     rdi, [rsi+0A8h]
0x14000c68d  mov     r9, rdi
0x14000c690  mov     edx, 4E734752h
0x14000c695  mov     ecx, 200h
0x14000c69a  call    NfsMemMgrBufferAllocate
0x14000c69f  mov     ebx, eax
0x14000c6a1  test    eax, eax
0x14000c6a3  js      loc_14000C61D
0x14000c6a9  movzx   eax, [rsp+58h+DestinationString.Length]
0x14000c6ae  lea     rbx, [rsi+0A0h]
0x14000c6b5  mov     rcx, rbx; DestinationString
0x14000c6b8  mov     [rsi+0A2h], ax
0x14000c6bf  lea     rdx, [rsp+58h+DestinationString]; SourceString
0x14000c6c4  mov     [rbx], ax
0x14000c6c7  call    cs:__imp_RtlCopyUnicodeString
0x14000c6ce  nop     dword ptr [rax+rax+00h]
0x14000c6d3  lea     r8, [rsi+0C0h]
0x14000c6da  mov     rcx, rbx
0x14000c6dd  lea     rdx, [rsi+0B0h]
0x14000c6e4  call    OncRpcSepSplitUserNameIntoParts
0x14000c6e9  mov     ebx, eax
0x14000c6eb  test    eax, eax
0x14000c6ed  jns     short loc_14000C72D
0x14000c6ef  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c6f6  lea     rax, WPP_GLOBAL_Control
0x14000c6fd  cmp     rcx, rax
0x14000c700  jz      short loc_14000C721
0x14000c702  mov     eax, [rcx+2Ch]
0x14000c705  test    al, 40h
0x14000c707  jz      short loc_14000C721
0x14000c709  mov     rcx, [rcx+18h]
0x14000c70d  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x14000c714  mov     edx, 20h ; ' '
0x14000c719  mov     r9d, ebx
0x14000c71c  call    WPP_SF_d
0x14000c721  mov     dword ptr [r14], 0A0000h
0x14000c728  jmp     loc_14000C61D
0x14000c72d  mov     dword ptr [r14], 0
0x14000c734  jmp     loc_14000C647
```
