# TdxSelectTlRequestTransportAddress

- ea: `0x14000fcf0`
- end: `0x14000fe2a`
- name: `TdxSelectTlRequestTransportAddress`
- size: `314`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140004df4`
- `0x140006608`
- `0x14000aad0`
- `0x140010100`
- `0x140013174`

## callees

- `0x1400054ec`
- `0x14000fcf0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000fe1c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000fe1c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000fddd`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000fddd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fd40`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fd40`
- `ntoskrnl!RtlGetCallersAddress` at `0x14000fd94`
- `ntoskrnl!RtlGetCallersAddress` at `0x14000fd94`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fdbe`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fdbe`

## pseudocode

```c
__int64 __fastcall TdxSelectTlRequestTransportAddress(__int64 a1, char a2)
{
  __int64 v5; // r14
  KIRQL v6; // di
  int v7; // edx
  __int64 v8; // rcx
  PVOID CallersAddress; // [rsp+40h] [rbp+8h] BYREF

  if ( (*(_DWORD *)a1 & 0x40) == 0 )
    return a1;
  v5 = *(_QWORD *)(a1 + 512);
  if ( v5 )
  {
    v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 552));
    v7 = *(_DWORD *)(v5 + 16) + 1;
    v8 = 32LL * *(unsigned int *)(v5 + 816);
    CallersAddress = 0;
    *(_DWORD *)(v8 + v5 + 584) = v7;
    *(_QWORD *)(v8 + v5 + 560) = "minio\\netio\\session\\tdi\\address.h";
    *(_DWORD *)(v8 + v5 + 568) = 392;
    RtlGetCallersAddress(&CallersAddress, (PVOID *)(v8 + v5 + 576));
    *(_DWORD *)(v5 + 816) = ((unsigned __int8)*(_DWORD *)(v5 + 816) + 1) & 7;
    KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 552), v6);
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 16));
  }
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 8));
  if ( a2 )
    DbgTdxDereferenceTransportAddress(a1, (__int64)"minio\\netio\\session\\tdi\\address.h", 396);
  if ( v5 )
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v5 + 8));
  return v5;
}

```

## disassembly

```asm
0x14000fcf0  push    rbx
0x14000fcf2  push    rbp
0x14000fcf3  sub     rsp, 28h
0x14000fcf7  mov     eax, [rcx]
0x14000fcf9  movzx   ebp, dl
0x14000fcfc  mov     rbx, rcx
0x14000fcff  test    al, 40h
0x14000fd01  jnz     short loc_14000FD0E
0x14000fd03  mov     rax, rcx
0x14000fd06  add     rsp, 28h
0x14000fd0a  pop     rbp
0x14000fd0b  pop     rbx
0x14000fd0c  retn
0x14000fd0e  mov     [rsp+38h+arg_18], r14
0x14000fd13  mov     r14, [rcx+200h]
0x14000fd1a  mov     [rsp+38h+var_18], r15
0x14000fd1f  lea     r15, aMinioNetioSess; "minio\\netio\\session\\tdi\\address.h"
0x14000fd26  test    r14, r14
0x14000fd29  jz      loc_14000FDD9
0x14000fd2f  mov     [rsp+38h+arg_8], rsi
0x14000fd34  lea     rcx, [r14+228h]; SpinLock
0x14000fd3b  mov     [rsp+38h+arg_10], rdi
0x14000fd40  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000fd47  nop     dword ptr [rax+rax+00h]
0x14000fd4c  mov     edx, [r14+10h]
0x14000fd50  movzx   edi, al
0x14000fd53  mov     ecx, [r14+330h]
0x14000fd5a  inc     edx
0x14000fd5c  shl     rcx, 5
0x14000fd60  mov     [rsp+38h+CallersAddress], 0
0x14000fd69  mov     [rcx+r14+248h], edx
0x14000fd71  lea     rdx, [r14+240h]
0x14000fd78  add     rdx, rcx; CallersCaller
0x14000fd7b  mov     [rcx+r14+230h], r15
0x14000fd83  mov     dword ptr [rcx+r14+238h], 188h
0x14000fd8f  lea     rcx, [rsp+38h+CallersAddress]; CallersAddress
0x14000fd94  call    cs:__imp_RtlGetCallersAddress
0x14000fd9b  nop     dword ptr [rax+rax+00h]
0x14000fda0  mov     eax, [r14+330h]
0x14000fda7  lea     rcx, [r14+228h]; SpinLock
0x14000fdae  inc     eax
0x14000fdb0  movzx   edx, dil; NewIrql
0x14000fdb4  and     eax, 7
0x14000fdb7  mov     [r14+330h], eax
0x14000fdbe  call    cs:__imp_KeReleaseSpinLock
0x14000fdc5  nop     dword ptr [rax+rax+00h]
0x14000fdca  lock inc dword ptr [r14+10h]
0x14000fdcf  mov     rdi, [rsp+38h+arg_10]
0x14000fdd4  mov     rsi, [rsp+38h+arg_8]
0x14000fdd9  lea     rcx, [rbx+8]; SpinLock
0x14000fddd  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000fde4  nop     dword ptr [rax+rax+00h]
0x14000fde9  test    bpl, bpl
0x14000fdec  jnz     short loc_14000FE05
0x14000fdee  mov     r15, [rsp+38h+var_18]
0x14000fdf3  test    r14, r14
0x14000fdf6  jnz     short loc_14000FE18
0x14000fdf8  mov     rax, r14
0x14000fdfb  mov     r14, [rsp+38h+arg_18]
0x14000fe00  jmp     loc_14000FD06
0x14000fe05  mov     r8d, 18Ch
0x14000fe0b  mov     rdx, r15
0x14000fe0e  mov     rcx, rbx
0x14000fe11  call    DbgTdxDereferenceTransportAddress
0x14000fe16  jmp     short loc_14000FDEE
0x14000fe18  lea     rcx, [r14+8]; SpinLock
0x14000fe1c  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000fe23  nop     dword ptr [rax+rax+00h]
0x14000fe28  jmp     short loc_14000FDF8
```
