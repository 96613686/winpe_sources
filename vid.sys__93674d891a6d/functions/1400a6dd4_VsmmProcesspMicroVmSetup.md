# VsmmProcesspMicroVmSetup

- ea: `0x1400a6dd4`
- end: `0x1400a6eda`
- name: `VsmmProcesspMicroVmSetup`
- size: `262`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400757a8`
- `0x1400a6c28`

## callees

- `0x1400248f4`
- `0x14002f724`
- `0x1400a6d0c`
- `0x1400a6dd4`
- `0x1400fd58c`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x1400a6eb1`
- `ntoskrnl!PsGetProcessId` at `0x1400a6eb1`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400a6e2d`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400a6e2d`

## pseudocode

```c
__int64 __fastcall VsmmProcesspMicroVmSetup(__int64 a1)
{
  struct _KPROCESS **v1; // r15
  __int64 v2; // rbx
  __int64 v3; // rbp
  void *v4; // rsi
  int v6; // r8d
  int v7; // edi
  int CurrentProcess; // eax
  int v9; // eax
  _OWORD *v10; // r14
  unsigned int v11; // ebx
  struct _KPROCESS *v12; // rcx
  HANDLE ProcessId; // rax
  _OWORD v15[4]; // [rsp+40h] [rbp-48h] BYREF

  v1 = (struct _KPROCESS **)(a1 + 10296);
  v2 = a1 + 10288;
  v3 = *(_QWORD *)(a1 + 10280);
  v4 = (void *)(a1 + 10336);
  v6 = (*(_DWORD *)(a1 + 24) >> 4) & 4 | 8;
  if ( (*(_DWORD *)(a1 + 16) & 0x4000) == 0 )
    v6 = (*(_DWORD *)(a1 + 24) >> 4) & 4;
  v7 = v6 | 0x10;
  if ( !v3 )
    v7 = v6;
  CurrentProcess = PsGetCurrentProcess();
  v9 = VsmmNtSlatMemoryProcessCreate(CurrentProcess, 0, v3, v7, v4, (__int64)v1, v2);
  v10 = (_OWORD *)(a1 + 656);
  v11 = v9;
  if ( v9 >= 0 )
  {
    v12 = *v1;
    v15[0] = *v10;
    ProcessId = PsGetProcessId(v12);
    VsmmProcesspLogVmMemInfo(v15, ProcessId);
  }
  else
  {
    VidTraceErrorStatusInternal0(
      "VsmmProcesspMicroVmSetup",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmprocess.c",
      785,
      (unsigned int)v9);
    VidTraceErrorStatusPartitionInternal0(
      (unsigned int)"VsmmProcesspMicroVmSetup",
      (unsigned int)"onecore\\vm\\vid\\sys\\vsmm\\vsmmprocess.c",
      826,
      v11,
      (__int64)v10);
  }
  return v11;
}

```

## disassembly

```asm
0x1400a6dd4  push    rbx
0x1400a6dd6  push    rbp
0x1400a6dd7  push    rsi
0x1400a6dd8  push    rdi
0x1400a6dd9  push    r14
0x1400a6ddb  push    r15
0x1400a6ddd  sub     rsp, 58h
0x1400a6de1  mov     eax, [rcx+10h]
0x1400a6de4  lea     r15, [rcx+2838h]
0x1400a6deb  mov     edx, [rcx+18h]
0x1400a6dee  lea     rbx, [rcx+2830h]
0x1400a6df5  mov     rbp, [rcx+2828h]
0x1400a6dfc  lea     rsi, [rcx+2860h]
0x1400a6e03  shr     rdx, 4
0x1400a6e07  and     eax, 4000h
0x1400a6e0c  and     edx, 4
0x1400a6e0f  mov     r14, rcx
0x1400a6e12  mov     r8d, edx
0x1400a6e15  or      r8d, 8
0x1400a6e19  test    rax, rax
0x1400a6e1c  cmovz   r8d, edx
0x1400a6e20  mov     edi, r8d
0x1400a6e23  or      edi, 10h
0x1400a6e26  test    rbp, rbp
0x1400a6e29  cmovz   edi, r8d
0x1400a6e2d  call    cs:__imp_PsGetCurrentProcess
0x1400a6e34  nop     dword ptr [rax+rax+00h]
0x1400a6e39  mov     [rsp+88h+var_58], rbx; __int64
0x1400a6e3e  mov     r9d, edi; int
0x1400a6e41  mov     rcx, rax; int
0x1400a6e44  mov     [rsp+88h+var_60], r15; __int64
0x1400a6e49  mov     r8, rbp; int
0x1400a6e4c  mov     [rsp+88h+var_68], rsi; PVOID
0x1400a6e51  xor     edx, edx; int
0x1400a6e53  call    VsmmNtSlatMemoryProcessCreate
0x1400a6e58  add     r14, 290h
0x1400a6e5f  mov     ebx, eax
0x1400a6e61  test    eax, eax
0x1400a6e63  jns     short loc_1400A6EA4
0x1400a6e65  mov     r9d, eax
0x1400a6e68  lea     rdx, aOnecoreVmVidSy; "onecore\\vm\\vid\\sys\\vsmm\\vsmmproces"...
0x1400a6e6f  mov     r8d, 311h
0x1400a6e75  lea     rcx, aVsmmprocesspmi; "VsmmProcesspMicroVmSetup"
0x1400a6e7c  call    VidTraceErrorStatusInternal0
0x1400a6e81  mov     r9d, ebx
0x1400a6e84  mov     [rsp+88h+var_68], r14
0x1400a6e89  mov     r8d, 33Ah
0x1400a6e8f  lea     rdx, aOnecoreVmVidSy; "onecore\\vm\\vid\\sys\\vsmm\\vsmmproces"...
0x1400a6e96  lea     rcx, aVsmmprocesspmi; "VsmmProcesspMicroVmSetup"
0x1400a6e9d  call    VidTraceErrorStatusPartitionInternal0
0x1400a6ea2  jmp     short loc_1400A6ECA
0x1400a6ea4  movups  xmm0, xmmword ptr [r14]
0x1400a6ea8  mov     rcx, [r15]; Process
0x1400a6eab  movdqu  [rsp+88h+var_48], xmm0
0x1400a6eb1  call    cs:__imp_PsGetProcessId
0x1400a6eb8  nop     dword ptr [rax+rax+00h]
0x1400a6ebd  mov     rdx, rax
0x1400a6ec0  lea     rcx, [rsp+88h+var_48]
0x1400a6ec5  call    VsmmProcesspLogVmMemInfo
0x1400a6eca  mov     eax, ebx
0x1400a6ecc  add     rsp, 58h
0x1400a6ed0  pop     r15
0x1400a6ed2  pop     r14
0x1400a6ed4  pop     rdi
0x1400a6ed5  pop     rsi
0x1400a6ed6  pop     rbp
0x1400a6ed7  pop     rbx
0x1400a6ed8  retn
```
