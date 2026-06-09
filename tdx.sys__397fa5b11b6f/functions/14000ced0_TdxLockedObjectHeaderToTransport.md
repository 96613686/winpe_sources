# TdxLockedObjectHeaderToTransport

- ea: `0x14000ced0`
- end: `0x14000cfad`
- name: `TdxLockedObjectHeaderToTransport`
- size: `221`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140004df4`
- `0x14000aad0`
- `0x14000cde0`
- `0x1400157cc`

## callees

- `0x14000ced0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000cefb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000cefb`
- `ntoskrnl!RtlGetCallersAddress` at `0x14000cf46`
- `ntoskrnl!RtlGetCallersAddress` at `0x14000cf46`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cf7f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cf7f`

## pseudocode

```c
__int64 __fastcall TdxLockedObjectHeaderToTransport(__int64 a1)
{
  __int64 v1; // rbx
  KIRQL v3; // al
  int v4; // ecx
  KIRQL v5; // di
  __int64 v6; // rdx
  __int64 v7; // rdx
  PVOID CallersAddress; // [rsp+30h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 40);
  if ( !v1 )
    return 0;
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 216));
  v4 = *(_DWORD *)(v1 + 24);
  v5 = v3;
  v6 = *(unsigned int *)(v1 + 1184) + 7LL;
  CallersAddress = 0;
  v7 = v1 + 32 * v6;
  *(_DWORD *)(v7 + 24) = v4 + 1;
  *(_QWORD *)v7 = "minio\\netio\\session\\tdi\\transport.h";
  *(_DWORD *)(v7 + 8) = 359;
  RtlGetCallersAddress(&CallersAddress, (PVOID *)(v7 + 16));
  *(_DWORD *)(v1 + 1184) = (*(_DWORD *)(v1 + 1184) + 1) % 0x1Eu;
  KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 216), v5);
  _InterlockedIncrement((volatile signed __int32 *)(v1 + 24));
  return *(_QWORD *)(a1 + 40);
}

```

## disassembly

```asm
0x14000ced0  mov     [rsp+arg_18], rbx
0x14000ced5  push    rbp
0x14000ced6  sub     rsp, 20h
0x14000ceda  mov     rbx, [rcx+28h]
0x14000cede  mov     rbp, rcx
0x14000cee1  test    rbx, rbx
0x14000cee4  jz      loc_14000CFA9
0x14000ceea  mov     [rsp+28h+arg_8], rsi
0x14000ceef  lea     rcx, [rbx+0D8h]; SpinLock
0x14000cef6  mov     [rsp+28h+arg_10], rdi
0x14000cefb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000cf02  nop     dword ptr [rax+rax+00h]
0x14000cf07  mov     ecx, [rbx+18h]
0x14000cf0a  movzx   edi, al
0x14000cf0d  mov     edx, [rbx+4A0h]
0x14000cf13  lea     rax, aMinioNetioSess_7; "minio\\netio\\session\\tdi\\transport.h"
0x14000cf1a  add     rdx, 7
0x14000cf1e  mov     [rsp+28h+CallersAddress], 0
0x14000cf27  shl     rdx, 5
0x14000cf2b  add     rdx, rbx
0x14000cf2e  inc     ecx
0x14000cf30  mov     [rdx+18h], ecx
0x14000cf33  lea     rcx, [rsp+28h+CallersAddress]; CallersAddress
0x14000cf38  mov     [rdx], rax
0x14000cf3b  mov     dword ptr [rdx+8], 167h
0x14000cf42  add     rdx, 10h; CallersCaller
0x14000cf46  call    cs:__imp_RtlGetCallersAddress
0x14000cf4d  nop     dword ptr [rax+rax+00h]
0x14000cf52  mov     r8d, [rbx+4A0h]
0x14000cf59  lea     rcx, [rbx+0D8h]; SpinLock
0x14000cf60  inc     r8d
0x14000cf63  mov     eax, 88888889h
0x14000cf68  mul     r8d
0x14000cf6b  shr     edx, 4
0x14000cf6e  imul    eax, edx, 1Eh
0x14000cf71  movzx   edx, dil; NewIrql
0x14000cf75  sub     r8d, eax
0x14000cf78  mov     [rbx+4A0h], r8d
0x14000cf7f  call    cs:__imp_KeReleaseSpinLock
0x14000cf86  nop     dword ptr [rax+rax+00h]
0x14000cf8b  lock inc dword ptr [rbx+18h]
0x14000cf8f  mov     rax, [rbp+28h]
0x14000cf93  mov     rdi, [rsp+28h+arg_10]
0x14000cf98  mov     rsi, [rsp+28h+arg_8]
0x14000cf9d  mov     rbx, [rsp+28h+arg_18]
0x14000cfa2  add     rsp, 20h
0x14000cfa6  pop     rbp
0x14000cfa7  retn
0x14000cfa9  xor     eax, eax
0x14000cfab  jmp     short loc_14000CF9D
```
