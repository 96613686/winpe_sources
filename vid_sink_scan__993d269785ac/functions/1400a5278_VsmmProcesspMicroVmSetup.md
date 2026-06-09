# VsmmProcesspMicroVmSetup

- ea: `0x1400a5278`
- end: `0x1400a537e`
- name: `VsmmProcesspMicroVmSetup`
- size: `262`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140074988`
- `0x1400a50cc`

## callees

- `0x140024754`
- `0x14002f524`
- `0x1400a51b0`
- `0x1400a5278`
- `0x1400fad1c`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x1400a5355`
- `ntoskrnl!PsGetProcessId` at `0x1400a5355`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400a52d1`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400a52d1`

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
  _OWORD *v9; // r14
  int v10; // ebx
  struct _KPROCESS *v11; // rcx
  HANDLE ProcessId; // rax
  _OWORD v14[4]; // [rsp+40h] [rbp-48h] BYREF

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
  v9 = (_OWORD *)(a1 + 656);
  v10 = VsmmNtSlatMemoryProcessCreate(CurrentProcess, 0, v3, v7, v4, (__int64)v1, v2);
  if ( v10 >= 0 )
  {
    v11 = *v1;
    v14[0] = *v9;
    ProcessId = PsGetProcessId(v11);
    VsmmProcesspLogVmMemInfo(v14, ProcessId);
  }
  else
  {
    VidTraceErrorStatusInternal0("VsmmProcesspMicroVmSetup", "onecore\\vm\\vid\\sys\\vsmm\\vsmmprocess.c", 785);
    VidTraceErrorStatusPartitionInternal0(
      (unsigned int)"VsmmProcesspMicroVmSetup",
      (unsigned int)"onecore\\vm\\vid\\sys\\vsmm\\vsmmprocess.c",
      809,
      v10,
      (__int64)v9);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400a5278  push    rbx
0x1400a527a  push    rbp
0x1400a527b  push    rsi
0x1400a527c  push    rdi
0x1400a527d  push    r14
0x1400a527f  push    r15
0x1400a5281  sub     rsp, 58h
0x1400a5285  mov     eax, [rcx+10h]
0x1400a5288  lea     r15, [rcx+2838h]
0x1400a528f  mov     edx, [rcx+18h]
0x1400a5292  lea     rbx, [rcx+2830h]
0x1400a5299  mov     rbp, [rcx+2828h]
0x1400a52a0  lea     rsi, [rcx+2860h]
0x1400a52a7  shr     rdx, 4
0x1400a52ab  and     eax, 4000h
0x1400a52b0  and     edx, 4
0x1400a52b3  mov     r14, rcx
0x1400a52b6  mov     r8d, edx
0x1400a52b9  or      r8d, 8
0x1400a52bd  test    rax, rax
0x1400a52c0  cmovz   r8d, edx
0x1400a52c4  mov     edi, r8d
0x1400a52c7  or      edi, 10h
0x1400a52ca  test    rbp, rbp
0x1400a52cd  cmovz   edi, r8d
0x1400a52d1  call    cs:__imp_PsGetCurrentProcess
0x1400a52d8  nop     dword ptr [rax+rax+00h]
0x1400a52dd  mov     [rsp+88h+var_58], rbx; __int64
0x1400a52e2  mov     r9d, edi; int
0x1400a52e5  mov     rcx, rax; int
0x1400a52e8  mov     [rsp+88h+var_60], r15; __int64
0x1400a52ed  mov     r8, rbp; int
0x1400a52f0  mov     [rsp+88h+var_68], rsi; PVOID
0x1400a52f5  xor     edx, edx; int
0x1400a52f7  call    VsmmNtSlatMemoryProcessCreate
0x1400a52fc  add     r14, 290h
0x1400a5303  mov     ebx, eax
0x1400a5305  test    eax, eax
0x1400a5307  jns     short loc_1400A5348
0x1400a5309  mov     r9d, eax
0x1400a530c  lea     rdx, aOnecoreVmVidSy; "onecore\\vm\\vid\\sys\\vsmm\\vsmmproces"...
0x1400a5313  mov     r8d, 311h
0x1400a5319  lea     rcx, aVsmmprocesspmi; "VsmmProcesspMicroVmSetup"
0x1400a5320  call    VidTraceErrorStatusInternal0
0x1400a5325  mov     r9d, ebx
0x1400a5328  mov     [rsp+88h+var_68], r14
0x1400a532d  mov     r8d, 329h
0x1400a5333  lea     rdx, aOnecoreVmVidSy; "onecore\\vm\\vid\\sys\\vsmm\\vsmmproces"...
0x1400a533a  lea     rcx, aVsmmprocesspmi; "VsmmProcesspMicroVmSetup"
0x1400a5341  call    VidTraceErrorStatusPartitionInternal0
0x1400a5346  jmp     short loc_1400A536E
0x1400a5348  movups  xmm0, xmmword ptr [r14]
0x1400a534c  mov     rcx, [r15]; Process
0x1400a534f  movdqu  [rsp+88h+var_48], xmm0
0x1400a5355  call    cs:__imp_PsGetProcessId
0x1400a535c  nop     dword ptr [rax+rax+00h]
0x1400a5361  mov     rdx, rax
0x1400a5364  lea     rcx, [rsp+88h+var_48]
0x1400a5369  call    VsmmProcesspLogVmMemInfo
0x1400a536e  mov     eax, ebx
0x1400a5370  add     rsp, 58h
0x1400a5374  pop     r15
0x1400a5376  pop     r14
0x1400a5378  pop     rdi
0x1400a5379  pop     rsi
0x1400a537a  pop     rbp
0x1400a537b  pop     rbx
0x1400a537c  retn
```
