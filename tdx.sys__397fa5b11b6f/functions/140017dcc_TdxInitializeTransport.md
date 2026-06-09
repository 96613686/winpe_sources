# TdxInitializeTransport

- ea: `0x140017dcc`
- end: `0x14001805c`
- name: `TdxInitializeTransport`
- size: `656`
- prototype: `__int64 __usercall@<rax>(PVOID ClientBindingContext@<rcx>, PCUNICODE_STRING SourceString, PCUNICODE_STRING, HANDLE NmrBindingHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1400112e0`

## callees

- `0x14000c9cc`
- `0x14000ccfc`
- `0x140017dcc`
- `0x140018900`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140017ef5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140017f08`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140017ef5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140017f08`
- `ntoskrnl!KeInitializeSpinLock` at `0x140017df8`
- `ntoskrnl!KeInitializeSpinLock` at `0x140017f7c`
- `ntoskrnl!KeInitializeSpinLock` at `0x140017df8`
- `ntoskrnl!KeInitializeSpinLock` at `0x140017f7c`
- `ntoskrnl!ExAllocatePool2` at `0x140017e82`
- `ntoskrnl!ExAllocatePool2` at `0x140017ec2`
- `ntoskrnl!ExAllocatePool2` at `0x140017e82`
- `ntoskrnl!ExAllocatePool2` at `0x140017ec2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017ee0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017ee0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017ff7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017ff7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001803e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001803e`
- `NETIO!NmrClientAttachProvider` at `0x140017fba`
- `NETIO!NmrClientAttachProvider` at `0x140017fba`

## pseudocode

```c
__int64 __fastcall TdxInitializeTransport(
        char *ClientBindingContext,
        int a2,
        int a3,
        __int16 a4,
        PCUNICODE_STRING SourceString,
        PCUNICODE_STRING a6,
        HANDLE NmrBindingHandle)
{
  unsigned __int16 v11; // ax
  __int64 Pool2; // rax
  unsigned __int16 v14; // ax
  __int64 v15; // rax
  int v16; // eax
  NTSTATUS v17; // ebx
  KIRQL v18; // al
  _QWORD *v19; // rcx

  memset(ClientBindingContext, 0, 0x4A8u);
  KeInitializeSpinLock((PKSPIN_LOCK)ClientBindingContext + 2);
  *((_DWORD *)ClientBindingContext + 7) = a2;
  *((_DWORD *)ClientBindingContext + 6) = 1;
  *((_DWORD *)ClientBindingContext + 8) = a3;
  *((_WORD *)ClientBindingContext + 18) = a4;
  if ( a4 == 1 && a3 == 6 )
    *((_DWORD *)ClientBindingContext + 42) |= 8u;
  *((_QWORD *)ClientBindingContext + 20) = NmrBindingHandle;
  *((_QWORD *)ClientBindingContext + 1) = ClientBindingContext;
  *(_QWORD *)ClientBindingContext = ClientBindingContext;
  *((_QWORD *)ClientBindingContext + 23) = ClientBindingContext + 176;
  *((_QWORD *)ClientBindingContext + 22) = ClientBindingContext + 176;
  *((_QWORD *)ClientBindingContext + 25) = ClientBindingContext + 192;
  *((_QWORD *)ClientBindingContext + 24) = ClientBindingContext + 192;
  v11 = SourceString->Length + 2;
  *((_WORD *)ClientBindingContext + 21) = v11;
  Pool2 = ExAllocatePool2(64, v11, 1417176148);
  *((_QWORD *)ClientBindingContext + 6) = Pool2;
  if ( !Pool2 )
    return 3221225495LL;
  v14 = a6->Length + 2;
  *((_WORD *)ClientBindingContext + 29) = v14;
  v15 = ExAllocatePool2(64, v14, 1417176148);
  *((_QWORD *)ClientBindingContext + 8) = v15;
  if ( !v15 )
  {
    ExFreePoolWithTag(*((PVOID *)ClientBindingContext + 6), 0x54786454u);
    return 3221225495LL;
  }
  RtlCopyUnicodeString((PUNICODE_STRING)(ClientBindingContext + 40), SourceString);
  RtlCopyUnicodeString((PUNICODE_STRING)(ClientBindingContext + 56), a6);
  v16 = 65507;
  *((_DWORD *)ClientBindingContext + 28) = 2;
  *(_QWORD *)(ClientBindingContext + 116) = 0x3FFFFFFF;
  if ( a3 != 17 )
    v16 = 65515;
  *((_DWORD *)ClientBindingContext + 31) = v16;
  *((_DWORD *)ClientBindingContext + 32) = 1411503;
  if ( *((_WORD *)ClientBindingContext + 18) == 1 && *((_DWORD *)ClientBindingContext + 8) == 6 )
    *((_DWORD *)ClientBindingContext + 32) = 5605807;
  *((_DWORD *)ClientBindingContext + 33) = 1;
  *((_QWORD *)ClientBindingContext + 17) = 0xFFFF;
  *((_QWORD *)ClientBindingContext + 18) = MEMORY[0xFFFFF78000000014];
  KeInitializeSpinLock((PKSPIN_LOCK)ClientBindingContext + 27);
  DbgTdxReferenceTransport(ClientBindingContext, "minio\\netio\\session\\tdi\\transport.c", 701);
  v17 = NmrClientAttachProvider(
          NmrBindingHandle,
          ClientBindingContext,
          &TdxTlClientDispatch,
          (PVOID *)ClientBindingContext + 9,
          (const void **)ClientBindingContext + 10);
  if ( v17 >= 0 )
  {
    v18 = KeAcquireSpinLockRaiseToDpc(&TdxTransportSpinLock);
    v19 = (_QWORD *)qword_14001E298;
    if ( *(__int64 **)qword_14001E298 != &TdxTransportListHead )
      __fastfail(3u);
    *(_QWORD *)ClientBindingContext = &TdxTransportListHead;
    *((_QWORD *)ClientBindingContext + 1) = v19;
    *v19 = ClientBindingContext;
    qword_14001E298 = (__int64)ClientBindingContext;
    *((_DWORD *)ClientBindingContext + 42) |= 4u;
    KeReleaseSpinLock(&TdxTransportSpinLock, v18);
  }
  else
  {
    DbgTdxDereferenceTransport(ClientBindingContext, "minio\\netio\\session\\tdi\\transport.c", 710);
    DbgTdxDereferenceTransport(ClientBindingContext, "minio\\netio\\session\\tdi\\transport.c", 711);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x140017dcc  push    rbx
0x140017dce  push    rbp
0x140017dcf  push    rsi
0x140017dd0  push    rdi
0x140017dd1  push    r13
0x140017dd3  push    r14
0x140017dd5  push    r15
0x140017dd7  sub     rsp, 30h
0x140017ddb  mov     ebp, r8d
0x140017dde  mov     ebx, edx
0x140017de0  xor     edx, edx; Val
0x140017de2  mov     r8d, 4A8h; Size
0x140017de8  movzx   edi, r9w
0x140017dec  mov     rsi, rcx
0x140017def  call    memset
0x140017df4  lea     rcx, [rsi+10h]; SpinLock
0x140017df8  call    cs:__imp_KeInitializeSpinLock
0x140017dff  nop     dword ptr [rax+rax+00h]
0x140017e04  mov     r15d, 1
0x140017e0a  mov     [rsi+1Ch], ebx
0x140017e0d  mov     [rsi+18h], r15d
0x140017e11  mov     [rsi+20h], ebp
0x140017e14  mov     [rsi+24h], di
0x140017e18  cmp     di, r15w
0x140017e1c  jnz     short loc_140017E2A
0x140017e1e  cmp     ebp, 6
0x140017e21  jnz     short loc_140017E2A
0x140017e23  or      dword ptr [rsi+0A8h], 8
0x140017e2a  mov     r14, [rsp+68h+NmrBindingHandle]
0x140017e32  lea     rax, [rsi+0B0h]
0x140017e39  mov     rdi, [rsp+68h+SourceString]
0x140017e41  mov     r13d, 2
0x140017e47  mov     [rsi+0A0h], r14
0x140017e4e  mov     r8d, 54786454h
0x140017e54  mov     [rsi+8], rsi
0x140017e58  mov     [rsi], rsi
0x140017e5b  mov     [rax+8], rax
0x140017e5f  lea     ecx, [r13+3Eh]
0x140017e63  mov     [rax], rax
0x140017e66  lea     rax, [rsi+0C0h]
0x140017e6d  mov     [rax+8], rax
0x140017e71  mov     [rax], rax
0x140017e74  movzx   eax, word ptr [rdi]
0x140017e77  add     ax, r13w
0x140017e7b  movzx   edx, ax
0x140017e7e  mov     [rsi+2Ah], dx
0x140017e82  call    cs:__imp_ExAllocatePool2
0x140017e89  nop     dword ptr [rax+rax+00h]
0x140017e8e  mov     [rsi+30h], rax
0x140017e92  test    rax, rax
0x140017e95  jnz     short loc_140017EA1
0x140017e97  mov     eax, 0C0000017h
0x140017e9c  jmp     loc_14001804C
0x140017ea1  mov     rbx, [rsp+68h+arg_28]
0x140017ea9  mov     ecx, 40h ; '@'
0x140017eae  mov     r8d, 54786454h
0x140017eb4  movzx   eax, word ptr [rbx]
0x140017eb7  add     ax, r13w
0x140017ebb  movzx   edx, ax
0x140017ebe  mov     [rsi+3Ah], dx
0x140017ec2  call    cs:__imp_ExAllocatePool2
0x140017ec9  nop     dword ptr [rax+rax+00h]
0x140017ece  mov     [rsi+40h], rax
0x140017ed2  test    rax, rax
0x140017ed5  jnz     short loc_140017EEE
0x140017ed7  mov     rcx, [rsi+30h]; P
0x140017edb  mov     edx, 54786454h; Tag
0x140017ee0  call    cs:__imp_ExFreePoolWithTag
0x140017ee7  nop     dword ptr [rax+rax+00h]
0x140017eec  jmp     short loc_140017E97
0x140017eee  lea     rcx, [rsi+28h]; DestinationString
0x140017ef2  mov     rdx, rdi; SourceString
0x140017ef5  call    cs:__imp_RtlCopyUnicodeString
0x140017efc  nop     dword ptr [rax+rax+00h]
0x140017f01  lea     rcx, [rsi+38h]; DestinationString
0x140017f05  mov     rdx, rbx; SourceString
0x140017f08  call    cs:__imp_RtlCopyUnicodeString
0x140017f0f  nop     dword ptr [rax+rax+00h]
0x140017f14  mov     eax, 0FFE3h
0x140017f19  mov     [rsi+70h], r13d
0x140017f1d  cmp     ebp, 11h
0x140017f20  mov     qword ptr [rsi+74h], 3FFFFFFFh
0x140017f28  lea     ecx, [rax+8]
0x140017f2b  cmovnz  eax, ecx
0x140017f2e  mov     [rsi+7Ch], eax
0x140017f31  mov     dword ptr [rsi+80h], 1589AFh
0x140017f3b  cmp     [rsi+24h], r15w
0x140017f40  jnz     short loc_140017F52
0x140017f42  cmp     dword ptr [rsi+20h], 6
0x140017f46  jnz     short loc_140017F52
0x140017f48  mov     dword ptr [rsi+80h], 5589AFh
0x140017f52  mov     [rsi+84h], r15d
0x140017f59  lea     rcx, [rsi+0D8h]; SpinLock
0x140017f60  mov     qword ptr [rsi+88h], 0FFFFh
0x140017f6b  mov     rax, ds:0FFFFF78000000014h
0x140017f75  mov     [rsi+90h], rax
0x140017f7c  call    cs:__imp_KeInitializeSpinLock
0x140017f83  nop     dword ptr [rax+rax+00h]
0x140017f88  lea     rdi, aMinioNetioSess_4; "minio\\netio\\session\\tdi\\transport.c"
0x140017f8f  mov     r8d, 2BDh
0x140017f95  mov     rdx, rdi
0x140017f98  mov     rcx, rsi
0x140017f9b  call    DbgTdxReferenceTransport
0x140017fa0  lea     rax, [rsi+50h]
0x140017fa4  mov     rdx, rsi; ClientBindingContext
0x140017fa7  lea     r9, [rsi+48h]; ProviderBindingContext
0x140017fab  mov     [rsp+68h+ProviderDispatch], rax; ProviderDispatch
0x140017fb0  lea     r8, TdxTlClientDispatch; ClientDispatch
0x140017fb7  mov     rcx, r14; NmrBindingHandle
0x140017fba  call    cs:__imp_NmrClientAttachProvider
0x140017fc1  nop     dword ptr [rax+rax+00h]
0x140017fc6  mov     ebx, eax
0x140017fc8  test    eax, eax
0x140017fca  jns     short loc_140017FF0
0x140017fcc  mov     r8d, 2C6h
0x140017fd2  mov     rdx, rdi
0x140017fd5  mov     rcx, rsi
0x140017fd8  call    DbgTdxDereferenceTransport
0x140017fdd  mov     r8d, 2C7h
0x140017fe3  mov     rdx, rdi
0x140017fe6  mov     rcx, rsi
0x140017fe9  call    DbgTdxDereferenceTransport
0x140017fee  jmp     short loc_14001804A
0x140017ff0  lea     rcx, TdxTransportSpinLock; SpinLock
0x140017ff7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017ffe  nop     dword ptr [rax+rax+00h]
0x140018003  mov     rcx, cs:qword_14001E298
0x14001800a  lea     rdx, TdxTransportListHead
0x140018011  cmp     [rcx], rdx
0x140018014  jz      short loc_14001801D
0x140018016  mov     ecx, 3
0x14001801b  int     29h; Win8: RtlFailFast(ecx)
0x14001801d  mov     [rsi], rdx
0x140018020  mov     dl, al; NewIrql
0x140018022  mov     [rsi+8], rcx
0x140018026  mov     [rcx], rsi
0x140018029  lea     rcx, TdxTransportSpinLock; SpinLock
0x140018030  mov     cs:qword_14001E298, rsi
0x140018037  or      dword ptr [rsi+0A8h], 4
0x14001803e  call    cs:__imp_KeReleaseSpinLock
0x140018045  nop     dword ptr [rax+rax+00h]
0x14001804a  mov     eax, ebx
0x14001804c  add     rsp, 30h
0x140018050  pop     r15
0x140018052  pop     r14
0x140018054  pop     r13
0x140018056  pop     rdi
0x140018057  pop     rsi
0x140018058  pop     rbp
0x140018059  pop     rbx
0x14001805a  retn
```
