# TdiPnPPowerRequest

- ea: `0x140002c40`
- end: `0x140002f27`
- name: `TdiPnPPowerRequest`
- size: `743`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING DeviceName, PNET_PNP_EVENT PowerEvent, PTDI_PNP_CONTEXT Context1, PTDI_PNP_CONTEXT Context2, ProviderPnPPowerComplete ProtocolCompletionHandler)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002c40`
- `0x140002f50`
- `0x140005600`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140002c69`
- `ntoskrnl!ExAllocatePool2` at `0x140002ca0`
- `ntoskrnl!ExAllocatePool2` at `0x140002d7c`
- `ntoskrnl!ExAllocatePool2` at `0x140002ddd`
- `ntoskrnl!ExAllocatePool2` at `0x140002c69`
- `ntoskrnl!ExAllocatePool2` at `0x140002ca0`
- `ntoskrnl!ExAllocatePool2` at `0x140002d7c`
- `ntoskrnl!ExAllocatePool2` at `0x140002ddd`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140002d1d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140002d1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002e42`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002e59`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002e7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002e92`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002eb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002ec9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002f00`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002f13`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002e42`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002e59`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002e7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002e92`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002eb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002ec9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002f00`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002f13`

## pseudocode

```c
NTSTATUS __stdcall TdiPnPPowerRequest(
        PUNICODE_STRING DeviceName,
        PNET_PNP_EVENT PowerEvent,
        PTDI_PNP_CONTEXT Context1,
        PTDI_PNP_CONTEXT Context2,
        ProviderPnPPowerComplete ProtocolCompletionHandler)
{
  __int64 Pool2; // rbx
  __int64 v10; // rax
  void *v11; // rsi
  ULONG_PTR v12; // rbp
  NTSTATUS v13; // edi
  USHORT *v15; // rax
  USHORT *v16; // rax
  void *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  void *v20; // rcx

  Pool2 = ExAllocatePool2(64, 136, 1749632084);
  if ( !Pool2 )
    return -1073741670;
  v10 = ExAllocatePool2(64, DeviceName->MaximumLength, 1766409300);
  v11 = (void *)v10;
  if ( !v10 )
  {
LABEL_29:
    v20 = (void *)Pool2;
LABEL_30:
    ExFreePoolWithTag(v20, 0);
    return -1073741670;
  }
  *(_BYTE *)(Pool2 + 16) = 2;
  *(_WORD *)(Pool2 + 122) = DeviceName->MaximumLength;
  *(_QWORD *)(Pool2 + 48) = ProtocolCompletionHandler;
  *(_QWORD *)(Pool2 + 128) = v10;
  v12 = PowerEvent->TdiReserved[0];
  if ( v12 )
  {
    for ( ; *(_QWORD *)(v12 + 104); v12 = *(_QWORD *)(v12 + 104) )
      ;
    *(_QWORD *)(v12 + 104) = Pool2;
  }
  else
  {
    PowerEvent->TdiReserved[0] = Pool2;
  }
  *(_QWORD *)(Pool2 + 40) = PowerEvent;
  *(_QWORD *)(Pool2 + 104) = 0;
  *(_DWORD *)(Pool2 + 56) = 0;
  if ( Context1 )
  {
    v16 = (USHORT *)ExAllocatePool2(64, Context1->ContextSize + 8LL, 2018067540);
    *(_QWORD *)(Pool2 + 80) = v16;
    if ( !v16 )
    {
      if ( v12 )
        *(_QWORD *)(v12 + 104) = 0;
      ExFreePoolWithTag((PVOID)Pool2, 0);
      v20 = v11;
      goto LABEL_30;
    }
    *v16 = Context1->ContextSize;
    *(_WORD *)(*(_QWORD *)(Pool2 + 80) + 2LL) = Context1->ContextType;
    memmove((void *)(*(_QWORD *)(Pool2 + 80) + 8LL), Context1->ContextData, Context1->ContextSize);
  }
  else
  {
    *(_QWORD *)(Pool2 + 80) = 0;
  }
  if ( Context2 )
  {
    v15 = (USHORT *)ExAllocatePool2(64, Context2->ContextSize + 8LL, 2034844756);
    *(_QWORD *)(Pool2 + 88) = v15;
    if ( v15 )
    {
      *v15 = Context2->ContextSize;
      *(_WORD *)(*(_QWORD *)(Pool2 + 88) + 2LL) = Context2->ContextType;
      memmove((void *)(*(_QWORD *)(Pool2 + 88) + 8LL), Context2->ContextData, Context2->ContextSize);
      goto LABEL_10;
    }
    ExFreePoolWithTag(v11, 0);
    v19 = *(void **)(Pool2 + 80);
    if ( v19 )
      ExFreePoolWithTag(v19, 0);
    if ( v12 )
      *(_QWORD *)(v12 + 104) = 0;
    goto LABEL_29;
  }
  *(_QWORD *)(Pool2 + 88) = 0;
LABEL_10:
  RtlCopyUnicodeString((PUNICODE_STRING)(Pool2 + 120), DeviceName);
  v13 = TdiHandleSerializedRequest(Pool2, 10);
  if ( v13 != 259 )
  {
    v13 = *(_DWORD *)(Pool2 + 56);
    ExFreePoolWithTag(v11, 0);
    v17 = *(void **)(Pool2 + 80);
    if ( v17 )
    {
      ExFreePoolWithTag(v17, 0);
      *(_QWORD *)(Pool2 + 80) = 0;
    }
    v18 = *(void **)(Pool2 + 88);
    if ( v18 )
    {
      ExFreePoolWithTag(v18, 0);
      *(_QWORD *)(Pool2 + 88) = 0;
    }
    if ( v12 )
      *(_QWORD *)(v12 + 104) = 0;
    ExFreePoolWithTag((PVOID)Pool2, 0);
  }
  return v13;
}

```

## disassembly

```asm
0x140002c40  push    rbx
0x140002c42  push    rdi
0x140002c43  push    r12
0x140002c45  push    r14
0x140002c47  push    r15
0x140002c49  sub     rsp, 20h
0x140002c4d  mov     r15, r8
0x140002c50  mov     rdi, rdx
0x140002c53  mov     r14, rcx
0x140002c56  mov     edx, 88h
0x140002c5b  mov     ecx, 40h ; '@'
0x140002c60  mov     r8d, 68494454h
0x140002c66  mov     r12, r9
0x140002c69  call    cs:__imp_ExAllocatePool2
0x140002c70  nop     dword ptr [rax+rax+00h]
0x140002c75  mov     rbx, rax
0x140002c78  test    rax, rax
0x140002c7b  jz      loc_140002E27
0x140002c81  movzx   edx, word ptr [r14+2]
0x140002c86  mov     ecx, 40h ; '@'
0x140002c8b  mov     [rsp+48h+arg_0], rbp
0x140002c90  mov     r8d, 69494454h
0x140002c96  mov     [rsp+48h+arg_8], rsi
0x140002c9b  mov     [rsp+48h+arg_10], r13
0x140002ca0  call    cs:__imp_ExAllocatePool2
0x140002ca7  nop     dword ptr [rax+rax+00h]
0x140002cac  mov     rsi, rax
0x140002caf  test    rax, rax
0x140002cb2  jz      loc_140002EAC
0x140002cb8  mov     byte ptr [rbx+10h], 2
0x140002cbc  movzx   ecx, word ptr [r14+2]
0x140002cc1  mov     [rbx+7Ah], cx
0x140002cc5  mov     rcx, [rsp+48h+ProtocolCompletionHandler]
0x140002cca  mov     [rbx+30h], rcx
0x140002cce  mov     [rbx+80h], rax
0x140002cd5  mov     rbp, [rdi+58h]
0x140002cd9  test    rbp, rbp
0x140002cdc  jz      loc_140002D62
0x140002ce2  cmp     qword ptr [rbp+68h], 0
0x140002ce7  jnz     loc_140002EE1
0x140002ced  mov     [rbp+68h], rbx
0x140002cf1  xor     r13d, r13d
0x140002cf4  mov     [rbx+28h], rdi
0x140002cf8  mov     [rbx+68h], r13
0x140002cfc  mov     [rbx+38h], r13d
0x140002d00  test    r15, r15
0x140002d03  jnz     loc_140002DCA
0x140002d09  mov     [rbx+50h], r13
0x140002d0d  test    r12, r12
0x140002d10  jnz     short loc_140002D68
0x140002d12  mov     [rbx+58h], r13
0x140002d16  lea     rcx, [rbx+78h]; DestinationString
0x140002d1a  mov     rdx, r14; SourceString
0x140002d1d  call    cs:__imp_RtlCopyUnicodeString
0x140002d24  nop     dword ptr [rax+rax+00h]
0x140002d29  mov     edx, 0Ah
0x140002d2e  mov     rcx, rbx
0x140002d31  call    TdiHandleSerializedRequest
0x140002d36  mov     edi, eax
0x140002d38  cmp     eax, 103h
0x140002d3d  jnz     loc_140002E3A
0x140002d43  mov     eax, edi
0x140002d45  mov     rsi, [rsp+48h+arg_8]
0x140002d4a  mov     rbp, [rsp+48h+arg_0]
0x140002d4f  mov     r13, [rsp+48h+arg_10]
0x140002d54  add     rsp, 20h
0x140002d58  pop     r15
0x140002d5a  pop     r14
0x140002d5c  pop     r12
0x140002d5e  pop     rdi
0x140002d5f  pop     rbx
0x140002d60  retn
0x140002d62  mov     [rdi+58h], rbx
0x140002d66  jmp     short loc_140002CF1
0x140002d68  movzx   edx, word ptr [r12]
0x140002d6d  mov     ecx, 40h ; '@'
0x140002d72  add     rdx, 8
0x140002d76  mov     r8d, 79494454h
0x140002d7c  call    cs:__imp_ExAllocatePool2
0x140002d83  nop     dword ptr [rax+rax+00h]
0x140002d88  mov     [rbx+58h], rax
0x140002d8c  mov     rcx, rax
0x140002d8f  test    rax, rax
0x140002d92  jz      loc_140002E8D
0x140002d98  movzx   eax, word ptr [r12]
0x140002d9d  lea     rdx, [r12+8]; Src
0x140002da2  mov     [rcx], ax
0x140002da5  mov     rcx, [rbx+58h]
0x140002da9  movzx   eax, word ptr [r12+2]
0x140002daf  mov     [rcx+2], ax
0x140002db3  mov     rcx, [rbx+58h]
0x140002db7  movzx   r8d, word ptr [r12]; Size
0x140002dbc  add     rcx, 8; void *
0x140002dc0  call    memmove
0x140002dc5  jmp     loc_140002D16
0x140002dca  movzx   edx, word ptr [r15]
0x140002dce  mov     ecx, 40h ; '@'
0x140002dd3  add     rdx, 8
0x140002dd7  mov     r8d, 78494454h
0x140002ddd  call    cs:__imp_ExAllocatePool2
0x140002de4  nop     dword ptr [rax+rax+00h]
0x140002de9  mov     [rbx+50h], rax
0x140002ded  mov     rcx, rax
0x140002df0  test    rax, rax
0x140002df3  jz      loc_140002EF2
0x140002df9  movzx   eax, word ptr [r15]
0x140002dfd  lea     rdx, [r15+8]; Src
0x140002e01  mov     [rcx], ax
0x140002e04  mov     rcx, [rbx+50h]
0x140002e08  movzx   eax, word ptr [r15+2]
0x140002e0d  mov     [rcx+2], ax
0x140002e11  mov     rcx, [rbx+50h]
0x140002e15  movzx   r8d, word ptr [r15]; Size
0x140002e19  add     rcx, 8; void *
0x140002e1d  call    memmove
0x140002e22  jmp     loc_140002D0D
0x140002e27  mov     eax, 0C000009Ah
0x140002e2c  add     rsp, 20h
0x140002e30  pop     r15
0x140002e32  pop     r14
0x140002e34  pop     r12
0x140002e36  pop     rdi
0x140002e37  pop     rbx
0x140002e38  retn
0x140002e3a  mov     edi, [rbx+38h]
0x140002e3d  xor     edx, edx; Tag
0x140002e3f  mov     rcx, rsi; P
0x140002e42  call    cs:__imp_ExFreePoolWithTag
0x140002e49  nop     dword ptr [rax+rax+00h]
0x140002e4e  mov     rcx, [rbx+50h]; P
0x140002e52  test    rcx, rcx
0x140002e55  jz      short loc_140002E69
0x140002e57  xor     edx, edx; Tag
0x140002e59  call    cs:__imp_ExFreePoolWithTag
0x140002e60  nop     dword ptr [rax+rax+00h]
0x140002e65  mov     [rbx+50h], r13
0x140002e69  mov     rcx, [rbx+58h]; P
0x140002e6d  test    rcx, rcx
0x140002e70  jnz     short loc_140002EC7
0x140002e72  test    rbp, rbp
0x140002e75  jnz     short loc_140002EDB
0x140002e77  xor     edx, edx; Tag
0x140002e79  mov     rcx, rbx; P
0x140002e7c  call    cs:__imp_ExFreePoolWithTag
0x140002e83  nop     dword ptr [rax+rax+00h]
0x140002e88  jmp     loc_140002D43
0x140002e8d  xor     edx, edx; Tag
0x140002e8f  mov     rcx, rsi; P
0x140002e92  call    cs:__imp_ExFreePoolWithTag
0x140002e99  nop     dword ptr [rax+rax+00h]
0x140002e9e  mov     rcx, [rbx+50h]; P
0x140002ea2  test    rcx, rcx
0x140002ea5  jnz     short loc_140002F11
0x140002ea7  test    rbp, rbp
0x140002eaa  jnz     short loc_140002F21
0x140002eac  mov     rcx, rbx; P
0x140002eaf  xor     edx, edx; Tag
0x140002eb1  call    cs:__imp_ExFreePoolWithTag
0x140002eb8  nop     dword ptr [rax+rax+00h]
0x140002ebd  mov     eax, 0C000009Ah
0x140002ec2  jmp     loc_140002D45
0x140002ec7  xor     edx, edx; Tag
0x140002ec9  call    cs:__imp_ExFreePoolWithTag
0x140002ed0  nop     dword ptr [rax+rax+00h]
0x140002ed5  mov     [rbx+58h], r13
0x140002ed9  jmp     short loc_140002E72
0x140002edb  mov     [rbp+68h], r13
0x140002edf  jmp     short loc_140002E77
0x140002ee1  mov     rbp, [rbp+68h]
0x140002ee5  cmp     qword ptr [rbp+68h], 0
0x140002eea  jz      loc_140002CED
0x140002ef0  jmp     short loc_140002EE1
0x140002ef2  test    rbp, rbp
0x140002ef5  jz      short loc_140002EFB
0x140002ef7  mov     [rbp+68h], r13
0x140002efb  xor     edx, edx; Tag
0x140002efd  mov     rcx, rbx; P
0x140002f00  call    cs:__imp_ExFreePoolWithTag
0x140002f07  nop     dword ptr [rax+rax+00h]
0x140002f0c  mov     rcx, rsi
0x140002f0f  jmp     short loc_140002EAF
0x140002f11  xor     edx, edx; Tag
0x140002f13  call    cs:__imp_ExFreePoolWithTag
0x140002f1a  nop     dword ptr [rax+rax+00h]
0x140002f1f  jmp     short loc_140002EA7
0x140002f21  mov     [rbp+68h], r13
0x140002f25  jmp     short loc_140002EAC
```
