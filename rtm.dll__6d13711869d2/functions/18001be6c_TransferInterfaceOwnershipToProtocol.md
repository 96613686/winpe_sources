# TransferInterfaceOwnershipToProtocol

- ea: `0x18001be6c`
- end: `0x18001bfcc`
- name: `TransferInterfaceOwnershipToProtocol`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180014970`

## callees

- `0x18001b548`
- `0x18001b9ac`
- `0x18001ba30`
- `0x18001be6c`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## string_xrefs

- `0x18001bed0`: `TransferInterfaceOwnershipToProtocol : Could not find IGMP protocol entry`

## pseudocode

```c
__int64 __fastcall TransferInterfaceOwnershipToProtocol(__int64 a1, __int64 a2)
{
  __int64 ProtocolEntry; // rsi
  __int64 v5; // r9
  __int64 v6; // r8
  unsigned int v7; // edi
  __int64 v8; // rdx
  int v10; // [rsp+20h] [rbp-838h] BYREF
  _BYTE v11[2044]; // [rsp+24h] [rbp-834h] BYREF

  v10 = 0;
  memset_0(v11, 0, sizeof(v11));
  ProtocolEntry = GetProtocolEntry(&qword_18002B9A8, *(unsigned int *)(a2 + 24), *(unsigned int *)(a2 + 28));
  if ( ProtocolEntry )
  {
    v7 = 0;
    if ( qword_18002B8A8 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(
        gMgmEtwContext,
        qword_18002B8A8,
        L"Invoked Disable IGMP Alert ");
    (*(void (__fastcall **)(_QWORD, _QWORD))(ProtocolEntry + 96))(
      *(unsigned int *)(a2 + 16),
      *(unsigned int *)(a2 + 20));
    DeleteInInterfaceRefs(a2 + 56);
    DeleteOutInterfaceRefs(ProtocolEntry, a2, 1);
    v8 = qword_18002B8A8;
    *(_WORD *)(a2 + 32) |= 0x4000u;
    *(_DWORD *)(a2 + 24) = *(_DWORD *)(a1 + 16);
    *(_DWORD *)(a2 + 28) = *(_DWORD *)(a1 + 20);
    if ( v8 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(
        gMgmEtwContext,
        v8,
        L"Invoked Enable IGMP Alert ");
    (*(void (__fastcall **)(_QWORD, _QWORD))(ProtocolEntry + 104))(
      *(unsigned int *)(a2 + 16),
      *(unsigned int *)(a2 + 20));
  }
  else
  {
    if ( qword_18002B8A8 )
    {
      v5 = *(unsigned int *)(a2 + 20);
      v6 = *(unsigned int *)(a2 + 16);
      LOWORD(v10) = 0;
      FormatRRASErrorString(&v10, L"TransferInterfaceOwnershipToProtocol : Could not find IGMP protocol entry", v6, v5);
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v10);
    }
    return 635;
  }
  return v7;
}

```

## disassembly

```asm
0x18001be6c  push    rbx
0x18001be6e  push    rbp
0x18001be6f  push    rsi
0x18001be70  push    rdi
0x18001be71  sub     rsp, 838h
0x18001be78  mov     rax, cs:__security_cookie
0x18001be7f  xor     rax, rsp
0x18001be82  mov     [rsp+858h+var_38], rax
0x18001be8a  mov     rbx, rdx
0x18001be8d  mov     rbp, rcx
0x18001be90  xor     eax, eax
0x18001be92  lea     rcx, [rsp+858h+var_834]; void *
0x18001be97  xor     edx, edx; Val
0x18001be99  mov     [rsp+858h+var_838], eax
0x18001be9d  mov     r8d, 7FCh; Size
0x18001bea3  call    memset_0
0x18001bea8  mov     r8d, [rbx+1Ch]
0x18001beac  lea     rcx, qword_18002B9A8
0x18001beb3  mov     edx, [rbx+18h]
0x18001beb6  call    GetProtocolEntry
0x18001bebb  mov     rsi, rax
0x18001bebe  test    rax, rax
0x18001bec1  jnz     short loc_18001BF13
0x18001bec3  cmp     cs:qword_18002B8A8, rax
0x18001beca  jz      short loc_18001BF09
0x18001becc  mov     r9d, [rbx+14h]
0x18001bed0  lea     rdx, aTransferinterf; "TransferInterfaceOwnershipToProtocol : "...
0x18001bed7  mov     r8d, [rbx+10h]
0x18001bedb  lea     rcx, [rsp+858h+var_838]
0x18001bee0  mov     word ptr [rsp+858h+var_838], ax
0x18001bee5  call    FormatRRASErrorString
0x18001beea  mov     rdx, cs:qword_18002B8A8
0x18001bef1  lea     r8, [rsp+858h+var_838]
0x18001bef6  mov     rcx, cs:gMgmEtwContext
0x18001befd  mov     rax, cs:gMgmTemplateFunc
0x18001bf04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf09  mov     edi, 27Bh
0x18001bf0e  jmp     loc_18001BFAE
0x18001bf13  mov     rdx, cs:qword_18002B8A8
0x18001bf1a  xor     edi, edi
0x18001bf1c  test    rdx, rdx
0x18001bf1f  jz      short loc_18001BF3B
0x18001bf21  mov     rcx, cs:gMgmEtwContext
0x18001bf28  lea     r8, aInvokedDisable; "Invoked Disable IGMP Alert "
0x18001bf2f  mov     rax, cs:gMgmTemplateFunc
0x18001bf36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf3b  mov     edx, [rbx+14h]
0x18001bf3e  mov     ecx, [rbx+10h]
0x18001bf41  mov     rax, [rsi+60h]
0x18001bf45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf4a  lea     rcx, [rbx+38h]
0x18001bf4e  call    DeleteInInterfaceRefs
0x18001bf53  mov     r8d, 1
0x18001bf59  mov     rdx, rbx
0x18001bf5c  mov     rcx, rsi
0x18001bf5f  call    DeleteOutInterfaceRefs
0x18001bf64  mov     rdx, cs:qword_18002B8A8
0x18001bf6b  mov     eax, 4000h
0x18001bf70  or      [rbx+20h], ax
0x18001bf74  mov     eax, [rbp+10h]
0x18001bf77  mov     [rbx+18h], eax
0x18001bf7a  mov     eax, [rbp+14h]
0x18001bf7d  mov     [rbx+1Ch], eax
0x18001bf80  test    rdx, rdx
0x18001bf83  jz      short loc_18001BF9F
0x18001bf85  mov     rcx, cs:gMgmEtwContext
0x18001bf8c  lea     r8, aInvokedEnableI; "Invoked Enable IGMP Alert "
0x18001bf93  mov     rax, cs:gMgmTemplateFunc
0x18001bf9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf9f  mov     edx, [rbx+14h]
0x18001bfa2  mov     ecx, [rbx+10h]
0x18001bfa5  mov     rax, [rsi+68h]
0x18001bfa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfae  mov     eax, edi
0x18001bfb0  mov     rcx, [rsp+858h+var_38]
0x18001bfb8  xor     rcx, rsp; StackCookie
0x18001bfbb  call    __security_check_cookie
0x18001bfc0  add     rsp, 838h
0x18001bfc7  pop     rdi
0x18001bfc8  pop     rsi
0x18001bfc9  pop     rbp
0x18001bfca  pop     rbx
0x18001bfcb  retn
```
