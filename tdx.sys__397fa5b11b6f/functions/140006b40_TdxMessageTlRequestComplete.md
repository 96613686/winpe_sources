# TdxMessageTlRequestComplete

- ea: `0x140006b40`
- end: `0x140006da5`
- name: `TdxMessageTlRequestComplete`
- size: `613`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140004920`
- `0x140006608`

## callees

- `0x140006b40`
- `0x140008c50`
- `0x140012b8c`
- `0x14001798c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140006b78`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006b78`
- `ntoskrnl!IofCompleteRequest` at `0x140006c56`
- `ntoskrnl!IofCompleteRequest` at `0x140006c56`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006b8b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006c69`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006b8b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006c69`
- `ntoskrnl!RtlGetCallersAddress` at `0x140006bd8`
- `ntoskrnl!RtlGetCallersAddress` at `0x140006cbd`
- `ntoskrnl!RtlGetCallersAddress` at `0x140006bd8`
- `ntoskrnl!RtlGetCallersAddress` at `0x140006cbd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006c11`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006ce5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006c11`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006ce5`

## pseudocode

```c
void __fastcall TdxMessageTlRequestComplete(__int64 *a1, int a2, ULONG_PTR a3)
{
  IRP *v3; // r15
  __int64 v5; // r13
  PFILE_OBJECT FileObject; // rbx
  unsigned int *FsContext; // rbx
  KIRQL v9; // al
  int v10; // ecx
  KIRQL v11; // di
  __int64 v12; // rdx
  __int64 v13; // rdx
  ULONG_PTR v14; // rax
  KIRQL v15; // al
  unsigned int v16; // ecx
  KIRQL v17; // di
  unsigned int *v18; // rdx
  PVOID CallersAddress; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v20; // [rsp+68h] [rbp+10h]

  v3 = (IRP *)a1[1];
  v5 = *a1;
  FileObject = v3->Tail.Overlay.CurrentStackLocation->FileObject;
  v20 = *((_DWORD *)a1 + 10);
  FsContext = (unsigned int *)FileObject->FsContext;
  ExFreePoolWithTag(a1, 0);
  v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 216));
  v10 = *(_DWORD *)(v5 + 24);
  v11 = v9;
  v12 = *(unsigned int *)(v5 + 1184) + 7LL;
  CallersAddress = 0;
  v13 = v5 + 32 * v12;
  *(_DWORD *)(v13 + 24) = v10 - 1;
  *(_QWORD *)v13 = "minio\\netio\\session\\tdi\\request.c";
  *(_DWORD *)(v13 + 8) = 266;
  RtlGetCallersAddress(&CallersAddress, (PVOID *)(v13 + 16));
  *(_DWORD *)(v5 + 1184) = (*(_DWORD *)(v5 + 1184) + 1) % 0x1Eu;
  KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 216), v11);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 24), 0xFFFFFFFF) == 1 )
    TdxCleanupTransport(v5);
  if ( a2 != -1073741811 )
  {
    if ( a2 == -1073741823 )
    {
      a2 = -1073741248;
    }
    else if ( a2 != -1073741306 && a2 != -1073741305 && a2 )
    {
      a3 = v20;
      a2 = 0;
    }
  }
  v14 = 0;
  v3->IoStatus.Status = a2;
  if ( a2 >= 0 )
    v14 = a3;
  v3->IoStatus.Information = v14;
  IofCompleteRequest(v3, 2);
  v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)FsContext + 69);
  v16 = FsContext[4];
  v17 = v15;
  v18 = &FsContext[8 * FsContext[204]];
  CallersAddress = 0;
  v18[146] = v16 - 1;
  *((_QWORD *)v18 + 70) = "minio\\netio\\session\\tdi\\request.c";
  v18[142] = 306;
  RtlGetCallersAddress(&CallersAddress, (PVOID *)v18 + 72);
  FsContext[204] = ((unsigned __int8)FsContext[204] + 1) & 7;
  KeReleaseSpinLock((PKSPIN_LOCK)FsContext + 69, v17);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)FsContext + 4, 0xFFFFFFFF) == 1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_63c55c6b4ff2326ef703f60977e9aaef_Traceguids, FsContext);
    }
    TdxCleanupObjectHeader(FsContext);
  }
}

```

## disassembly

```asm
0x140006b40  mov     [rsp+arg_10], rbx
0x140006b45  push    rbp
0x140006b46  push    rsi
0x140006b47  push    rdi
0x140006b48  push    r12
0x140006b4a  push    r13
0x140006b4c  push    r14
0x140006b4e  push    r15
0x140006b50  sub     rsp, 20h
0x140006b54  mov     r15, [rcx+8]
0x140006b58  mov     ebp, edx
0x140006b5a  mov     r13, [rcx]
0x140006b5d  xor     edx, edx; Tag
0x140006b5f  mov     r12, r8
0x140006b62  mov     rax, [r15+0B8h]
0x140006b69  mov     rbx, [rax+30h]
0x140006b6d  mov     eax, [rcx+28h]
0x140006b70  mov     [rsp+58h+arg_8], eax
0x140006b74  mov     rbx, [rbx+18h]
0x140006b78  call    cs:__imp_ExFreePoolWithTag
0x140006b7f  nop     dword ptr [rax+rax+00h]
0x140006b84  lea     rcx, [r13+0D8h]; SpinLock
0x140006b8b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006b92  nop     dword ptr [rax+rax+00h]
0x140006b97  mov     ecx, [r13+18h]
0x140006b9b  movzx   edi, al
0x140006b9e  mov     edx, [r13+4A0h]
0x140006ba5  lea     rax, aMinioNetioSess_0; "minio\\netio\\session\\tdi\\request.c"
0x140006bac  add     rdx, 7
0x140006bb0  mov     [rsp+58h+CallersAddress], 0
0x140006bb9  shl     rdx, 5
0x140006bbd  add     rdx, r13
0x140006bc0  dec     ecx
0x140006bc2  mov     [rdx+18h], ecx
0x140006bc5  lea     rcx, [rsp+58h+CallersAddress]; CallersAddress
0x140006bca  mov     [rdx], rax
0x140006bcd  mov     dword ptr [rdx+8], 10Ah
0x140006bd4  add     rdx, 10h; CallersCaller
0x140006bd8  call    cs:__imp_RtlGetCallersAddress
0x140006bdf  nop     dword ptr [rax+rax+00h]
0x140006be4  mov     r8d, [r13+4A0h]
0x140006beb  lea     rcx, [r13+0D8h]; SpinLock
0x140006bf2  inc     r8d
0x140006bf5  mov     eax, 88888889h
0x140006bfa  mul     r8d
0x140006bfd  shr     edx, 4
0x140006c00  imul    eax, edx, 1Eh
0x140006c03  movzx   edx, dil; NewIrql
0x140006c07  sub     r8d, eax
0x140006c0a  mov     [r13+4A0h], r8d
0x140006c11  call    cs:__imp_KeReleaseSpinLock
0x140006c18  nop     dword ptr [rax+rax+00h]
0x140006c1d  mov     r14d, 0FFFFFFFFh
0x140006c23  mov     eax, r14d
0x140006c26  lock xadd [r13+18h], eax
0x140006c2c  cmp     eax, 1
0x140006c2f  jz      loc_140006D68
0x140006c35  cmp     ebp, 0C000000Dh
0x140006c3b  jnz     loc_140006D34
0x140006c41  xor     eax, eax
0x140006c43  mov     [r15+30h], ebp
0x140006c47  test    ebp, ebp
0x140006c49  mov     dl, 2; PriorityBoost
0x140006c4b  mov     rcx, r15; Irp
0x140006c4e  cmovns  rax, r12
0x140006c52  mov     [r15+38h], rax
0x140006c56  call    cs:__imp_IofCompleteRequest
0x140006c5d  nop     dword ptr [rax+rax+00h]
0x140006c62  lea     rcx, [rbx+228h]; SpinLock
0x140006c69  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006c70  nop     dword ptr [rax+rax+00h]
0x140006c75  mov     ecx, [rbx+10h]
0x140006c78  movzx   edi, al
0x140006c7b  mov     edx, [rbx+330h]
0x140006c81  lea     rax, aMinioNetioSess_0; "minio\\netio\\session\\tdi\\request.c"
0x140006c88  shl     rdx, 5
0x140006c8c  add     rdx, rbx
0x140006c8f  mov     [rsp+58h+CallersAddress], 0
0x140006c98  dec     ecx
0x140006c9a  mov     [rdx+248h], ecx
0x140006ca0  lea     rcx, [rsp+58h+CallersAddress]; CallersAddress
0x140006ca5  mov     [rdx+230h], rax
0x140006cac  mov     dword ptr [rdx+238h], 132h
0x140006cb6  add     rdx, 240h; CallersCaller
0x140006cbd  call    cs:__imp_RtlGetCallersAddress
0x140006cc4  nop     dword ptr [rax+rax+00h]
0x140006cc9  mov     eax, [rbx+330h]
0x140006ccf  lea     rcx, [rbx+228h]; SpinLock
0x140006cd6  inc     eax
0x140006cd8  movzx   edx, dil; NewIrql
0x140006cdc  and     eax, 7
0x140006cdf  mov     [rbx+330h], eax
0x140006ce5  call    cs:__imp_KeReleaseSpinLock
0x140006cec  nop     dword ptr [rax+rax+00h]
0x140006cf1  lock xadd [rbx+10h], r14d
0x140006cf7  cmp     r14d, 1
0x140006cfb  jnz     short loc_140006D1E
0x140006cfd  mov     rcx, cs:WPP_GLOBAL_Control
0x140006d04  lea     rax, WPP_GLOBAL_Control
0x140006d0b  cmp     rcx, rax
0x140006d0e  jz      short loc_140006D16
0x140006d10  cmp     byte ptr [rcx+29h], 5
0x140006d14  jnb     short loc_140006D7F
0x140006d16  mov     rcx, rbx
0x140006d19  call    TdxCleanupObjectHeader
0x140006d1e  mov     rbx, [rsp+58h+arg_10]
0x140006d23  add     rsp, 20h
0x140006d27  pop     r15
0x140006d29  pop     r14
0x140006d2b  pop     r13
0x140006d2d  pop     r12
0x140006d2f  pop     rdi
0x140006d30  pop     rsi
0x140006d31  pop     rbp
0x140006d32  retn
0x140006d34  cmp     ebp, 0C0000001h
0x140006d3a  jz      short loc_140006D75
0x140006d3c  cmp     ebp, 0C0000206h
0x140006d42  jz      loc_140006C41
0x140006d48  cmp     ebp, 0C0000207h
0x140006d4e  jz      loc_140006C41
0x140006d54  test    ebp, ebp
0x140006d56  jz      loc_140006C41
0x140006d5c  mov     r12d, [rsp+58h+arg_8]
0x140006d61  xor     ebp, ebp
0x140006d63  jmp     loc_140006C41
0x140006d68  mov     rcx, r13
0x140006d6b  call    TdxCleanupTransport
0x140006d70  jmp     loc_140006C35
0x140006d75  mov     ebp, 0C0000240h
0x140006d7a  jmp     loc_140006C41
0x140006d7f  test    dword ptr [rcx+2Ch], 200h
0x140006d86  jz      short loc_140006D16
0x140006d88  mov     rcx, [rcx+18h]
0x140006d8c  lea     r8, WPP_63c55c6b4ff2326ef703f60977e9aaef_Traceguids
0x140006d93  mov     edx, 11h
0x140006d98  mov     r9, rbx
0x140006d9b  call    WPP_SF_q
0x140006da0  jmp     loc_140006D16
```
