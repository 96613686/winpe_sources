# VidResourcePartitionpSetMemoryPartitionComponent

- ea: `0x140095c48`
- end: `0x140095dd8`
- name: `VidResourcePartitionpSetMemoryPartitionComponent`
- size: `400`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400925c0`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x140095c48`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointerWithTag` at `0x140095cd3`
- `ntoskrnl!ObOpenObjectByPointerWithTag` at `0x140095cd3`
- `ntoskrnl!PsPartitionType` at `0x140095caf`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140095d9f`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140095d9f`

## string_xrefs

- `0x140095d11`: `VidResourcePartitionpSetMemoryPartitionComponent`

## pseudocode

```c
__int64 __fastcall VidResourcePartitionpSetMemoryPartitionComponent(__int64 a1, void *a2, int a3)
{
  int v5; // r8d
  NTSTATUS v6; // ebx
  __int64 v7; // rdi
  __int64 v8; // rax
  int v10; // [rsp+40h] [rbp-49h] BYREF
  NTSTATUS v11; // [rsp+44h] [rbp-45h] BYREF
  char v12[32]; // [rsp+50h] [rbp-39h] BYREF
  char v13[16]; // [rsp+70h] [rbp-19h] BYREF
  char v14[16]; // [rsp+80h] [rbp-9h] BYREF
  int *v15; // [rsp+90h] [rbp+7h]
  __int64 v16; // [rsp+98h] [rbp+Fh]
  NTSTATUS *v17; // [rsp+A0h] [rbp+17h]
  __int64 v18; // [rsp+A8h] [rbp+1Fh]
  __int64 v19; // [rsp+B0h] [rbp+27h]
  __int64 v20; // [rsp+B8h] [rbp+2Fh]

  v5 = a3 - 3;
  if ( v5 )
  {
    if ( v5 != 1 )
      return (unsigned int)-1073741811;
    v7 = 112;
    v8 = 120;
  }
  else
  {
    v7 = 96;
    v8 = 104;
  }
  v6 = ObOpenObjectByPointerWithTag(a2, 0x200u, 0, 0x1F0003u, PsPartitionType, 0, 0x72446456u, (PHANDLE)(a1 + v8));
  if ( v6 >= 0 )
  {
    ObfReferenceObjectWithTag(a2, 0x72446456u);
    v6 = 0;
    *(_QWORD *)(v7 + a1) = a2;
  }
  else if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v13, "VidResourcePartitionpSetMemoryPartitionComponent");
    tlgCreate1Sz_char(v14, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
    v10 = 2763;
    v15 = &v10;
    v16 = 4;
    v17 = &v11;
    v11 = v6;
    v19 = a1 + 8;
    v18 = 4;
    v20 = 16;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, byte_14004811B, 0, 0, 7, v12);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140095c48  mov     [rsp-8+arg_10], rbx
0x140095c4d  mov     [rsp-8+arg_18], rsi
0x140095c52  push    rbp
0x140095c53  push    rdi
0x140095c54  push    r14
0x140095c56  lea     rbp, [rsp-47h]
0x140095c5b  sub     rsp, 0D0h
0x140095c62  mov     rax, cs:__security_cookie
0x140095c69  xor     rax, rsp
0x140095c6c  mov     [rbp+57h+var_20], rax
0x140095c70  mov     rsi, rdx
0x140095c73  mov     r14, rcx
0x140095c76  sub     r8d, 3
0x140095c7a  jz      short loc_140095C96
0x140095c7c  cmp     r8d, 1
0x140095c80  jz      short loc_140095C8C
0x140095c82  mov     ebx, 0C000000Dh
0x140095c87  jmp     loc_140095DB1
0x140095c8c  mov     edi, 70h ; 'p'
0x140095c91  lea     eax, [rdi+8]
0x140095c94  jmp     short loc_140095C9E
0x140095c96  mov     edi, 60h ; '`'
0x140095c9b  lea     eax, [rdi+8]
0x140095c9e  add     rax, r14
0x140095ca1  mov     r9d, 1F0003h; DesiredAccess
0x140095ca7  mov     [rsp+0E0h+Handle], rax; Handle
0x140095cac  xor     r8d, r8d; PassedAccessState
0x140095caf  mov     rax, cs:__imp_PsPartitionType
0x140095cb6  mov     edx, 200h; HandleAttributes
0x140095cbb  mov     [rsp+0E0h+Tag], 72446456h; Tag
0x140095cc3  mov     [rsp+0E0h+AccessMode], 0; AccessMode
0x140095cc8  mov     rcx, [rax]
0x140095ccb  mov     [rsp+0E0h+ObjectType], rcx; ObjectType
0x140095cd0  mov     rcx, rsi; Object
0x140095cd3  call    cs:__imp_ObOpenObjectByPointerWithTag
0x140095cda  nop     dword ptr [rax+rax+00h]
0x140095cdf  mov     ebx, eax
0x140095ce1  test    eax, eax
0x140095ce3  jns     loc_140095D97
0x140095ce9  mov     ecx, cs:dword_140065110
0x140095cef  cmp     ecx, 2
0x140095cf2  jbe     loc_140095DB1
0x140095cf8  mov     edx, 100h
0x140095cfd  lea     rcx, dword_140065110
0x140095d04  call    _tlgKeywordOn
0x140095d09  test    al, al
0x140095d0b  jz      loc_140095DB1
0x140095d11  lea     rdx, aVidresourcepar_10; "VidResourcePartitionpSetMemoryPartition"...
0x140095d18  lea     rcx, [rbp+57h+var_70]
0x140095d1c  call    _tlgCreate1Sz_char
0x140095d21  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140095d28  lea     rcx, [rbp+57h+var_60]
0x140095d2c  call    _tlgCreate1Sz_char
0x140095d31  lea     rax, [rbp+57h+var_A0]
0x140095d35  mov     [rbp+57h+var_A0], 0ACBh
0x140095d3c  mov     [rbp+57h+var_50], rax
0x140095d40  lea     rdx, byte_14004811B
0x140095d47  lea     rax, [rbp+57h+var_9C]
0x140095d4b  mov     [rbp+57h+var_48], 4
0x140095d53  mov     [rbp+57h+var_40], rax
0x140095d57  lea     rcx, dword_140065110
0x140095d5e  lea     rax, [r14+8]
0x140095d62  mov     [rbp+57h+var_9C], ebx
0x140095d65  mov     [rbp+57h+var_30], rax
0x140095d69  xor     r9d, r9d
0x140095d6c  lea     rax, [rbp+57h+var_90]
0x140095d70  mov     [rbp+57h+var_38], 4
0x140095d78  mov     qword ptr [rsp+0E0h+AccessMode], rax
0x140095d7d  xor     r8d, r8d
0x140095d80  mov     dword ptr [rsp+0E0h+ObjectType], 7
0x140095d88  mov     [rbp+57h+var_28], 10h
0x140095d90  call    _tlgWriteTransfer_EtwWriteTransfer
0x140095d95  jmp     short loc_140095DB1
0x140095d97  mov     edx, 72446456h; Tag
0x140095d9c  mov     rcx, rsi; Object
0x140095d9f  call    cs:__imp_ObfReferenceObjectWithTag
0x140095da6  nop     dword ptr [rax+rax+00h]
0x140095dab  xor     ebx, ebx
0x140095dad  mov     [rdi+r14], rsi
0x140095db1  mov     eax, ebx
0x140095db3  mov     rcx, [rbp+57h+var_20]
0x140095db7  xor     rcx, rsp; StackCookie
0x140095dba  call    __security_check_cookie
0x140095dbf  lea     r11, [rsp+0E0h+var_10]
0x140095dc7  mov     rbx, [r11+30h]
0x140095dcb  mov     rsi, [r11+38h]
0x140095dcf  mov     rsp, r11
0x140095dd2  pop     r14
0x140095dd4  pop     rdi
0x140095dd5  pop     rbp
0x140095dd6  retn
```
