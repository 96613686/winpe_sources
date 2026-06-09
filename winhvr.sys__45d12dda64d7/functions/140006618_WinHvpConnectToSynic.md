# WinHvpConnectToSynic

- ea: `0x140006618`
- end: `0x1400067a5`
- name: `WinHvpConnectToSynic`
- size: `397`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14002a678`

## callees

- `0x140006254`
- `0x140006618`
- `0x1400068c0`
- `0x140006c74`
- `0x140009c50`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x140006781`
- `ntoskrnl!ExReleaseFastMutex` at `0x140006781`
- `ntoskrnl!ExAcquireFastMutex` at `0x140006695`
- `ntoskrnl!ExAcquireFastMutex` at `0x140006695`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x140006655`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x140006655`
- `ntoskrnl!RtlInitializeBitMap` at `0x140006672`
- `ntoskrnl!RtlInitializeBitMap` at `0x140006672`
- `ntoskrnl!RtlTestBit` at `0x1400066db`
- `ntoskrnl!RtlTestBit` at `0x1400066db`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140006729`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140006729`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14000676e`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14000676e`
- `ntoskrnl!RtlSetBit` at `0x14000674e`
- `ntoskrnl!RtlSetBit` at `0x14000674e`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x1400066ff`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x1400066ff`

## pseudocode

```c
void WinHvpConnectToSynic()
{
  ULONG ActiveProcessorCount; // r14d
  int v1; // ebx
  char v2; // di
  struct _GROUP_AFFINITY *p_PreviousAffinity; // rsi
  ULONG v4; // ebx
  _PROCESSOR_NUMBER ProcNumber[2]; // [rsp+20h] [rbp-40h] BYREF
  struct _RTL_BITMAP BitMapHeader; // [rsp+28h] [rbp-38h] BYREF
  struct _GROUP_AFFINITY Affinity; // [rsp+38h] [rbp-28h] BYREF
  struct _GROUP_AFFINITY PreviousAffinity; // [rsp+48h] [rbp-18h] BYREF

  LODWORD(BitMapHeader.Buffer) = 0;
  *(_QWORD *)&BitMapHeader.SizeOfBitMap = 0;
  Affinity = 0;
  *(_QWORD *)&ProcNumber[0].Group = 0;
  PreviousAffinity = 0;
  ActiveProcessorCount = KeQueryActiveProcessorCountEx(0xFFFFu);
  RtlInitializeBitMap(&BitMapHeader, WinHvpSynicProcessorsBitmap, ActiveProcessorCount);
  v1 = WinHvpNested != 0 ? 0x1000 : 0;
  ExAcquireFastMutex(&WinHvpSynicChangeLock);
  if ( (int)WinHvpGetVpRegister64Self2((unsigned int)(v1 + 655377), ProcNumber) >= 0
    && *(_QWORD *)&ProcNumber[0].Group == 1 )
  {
    v2 = 0;
    p_PreviousAffinity = &PreviousAffinity;
    v4 = 0;
    if ( ActiveProcessorCount )
    {
      do
      {
        if ( !RtlTestBit(&BitMapHeader, v4) )
        {
          ProcNumber[0] = 0;
          Affinity = 0;
          KeGetProcessorNumberFromIndex(v4, ProcNumber);
          Affinity.Group = ProcNumber[0].Group;
          Affinity.Mask = 1LL << ProcNumber[0].Number;
          KeSetSystemGroupAffinityThread(&Affinity, p_PreviousAffinity);
          if ( (int)WinHvpEnableSynic() < 0 )
            goto LABEL_9;
          v2 = 1;
          p_PreviousAffinity = 0;
          WinHvpSetProcessorPartitionSints();
          RtlSetBit(&BitMapHeader, v4);
        }
        ++v4;
      }
      while ( v4 < ActiveProcessorCount );
      if ( !v2 )
        goto LABEL_10;
LABEL_9:
      KeRevertToUserGroupAffinityThread(&PreviousAffinity);
    }
  }
LABEL_10:
  ExReleaseFastMutex(&WinHvpSynicChangeLock);
}

```

## disassembly

```asm
0x140006618  push    rbp
0x14000661a  push    rbx
0x14000661b  push    rsi
0x14000661c  push    rdi
0x14000661d  push    r14
0x14000661f  mov     rbp, rsp
0x140006622  sub     rsp, 60h
0x140006626  mov     rax, cs:__security_cookie
0x14000662d  xor     rax, rsp
0x140006630  mov     [rbp+var_8], rax
0x140006634  xor     eax, eax
0x140006636  xorps   xmm0, xmm0
0x140006639  xorps   xmm1, xmm1
0x14000663c  mov     qword ptr [rbp+BitMapHeader+4], rax
0x140006640  mov     ecx, 0FFFFh; GroupNumber
0x140006645  mov     [rbp-38h], rax
0x140006649  movups  xmmword ptr [rbp+Affinity.Mask], xmm0
0x14000664d  mov     qword ptr [rbp+ProcNumber.Group], rax
0x140006651  movups  xmmword ptr [rbp+PreviousAffinity.Mask], xmm1
0x140006655  call    cs:__imp_KeQueryActiveProcessorCountEx
0x14000665c  nop     dword ptr [rax+rax+00h]
0x140006661  mov     rdx, cs:WinHvpSynicProcessorsBitmap; BitMapBuffer
0x140006668  lea     rcx, [rbp+BitMapHeader]; BitMapHeader
0x14000666c  mov     r8d, eax; SizeOfBitMap
0x14000666f  mov     r14d, eax
0x140006672  call    cs:__imp_RtlInitializeBitMap
0x140006679  nop     dword ptr [rax+rax+00h]
0x14000667e  mov     cl, cs:WinHvpNested
0x140006684  neg     cl
0x140006686  lea     rcx, WinHvpSynicChangeLock; FastMutex
0x14000668d  sbb     ebx, ebx
0x14000668f  and     ebx, 1000h
0x140006695  call    cs:__imp_ExAcquireFastMutex
0x14000669c  nop     dword ptr [rax+rax+00h]
0x1400066a1  lea     rdx, [rbp+ProcNumber]
0x1400066a5  lea     ecx, [rbx+0A0011h]
0x1400066ab  call    WinHvpGetVpRegister64Self2
0x1400066b0  test    eax, eax
0x1400066b2  js      loc_14000677A
0x1400066b8  cmp     qword ptr [rbp+ProcNumber.Group], 1
0x1400066bd  jnz     loc_14000677A
0x1400066c3  xor     dil, dil
0x1400066c6  lea     rsi, [rbp+PreviousAffinity]
0x1400066ca  xor     ebx, ebx
0x1400066cc  test    r14d, r14d
0x1400066cf  jz      loc_14000677A
0x1400066d5  mov     edx, ebx; BitNumber
0x1400066d7  lea     rcx, [rbp+BitMapHeader]; BitMapHeader
0x1400066db  call    cs:__imp_RtlTestBit
0x1400066e2  nop     dword ptr [rax+rax+00h]
0x1400066e7  test    al, al
0x1400066e9  jnz     short loc_14000675A
0x1400066eb  xorps   xmm0, xmm0
0x1400066ee  mov     dword ptr [rbp+ProcNumber.Group], 0
0x1400066f5  lea     rdx, [rbp+ProcNumber]; ProcNumber
0x1400066f9  mov     ecx, ebx; ProcIndex
0x1400066fb  movups  xmmword ptr [rbp+Affinity.Mask], xmm0
0x1400066ff  call    cs:__imp_KeGetProcessorNumberFromIndex
0x140006706  nop     dword ptr [rax+rax+00h]
0x14000670b  movzx   eax, [rbp+ProcNumber.Group]
0x14000670f  mov     rdx, rsi; PreviousAffinity
0x140006712  mov     cl, [rbp+ProcNumber.Number]
0x140006715  mov     [rbp+Affinity.Group], ax
0x140006719  mov     eax, 1
0x14000671e  shl     rax, cl
0x140006721  lea     rcx, [rbp+Affinity]; Affinity
0x140006725  mov     [rbp+Affinity.Mask], rax
0x140006729  call    cs:__imp_KeSetSystemGroupAffinityThread
0x140006730  nop     dword ptr [rax+rax+00h]
0x140006735  call    WinHvpEnableSynic
0x14000673a  test    eax, eax
0x14000673c  js      short loc_14000676A
0x14000673e  mov     dil, 1
0x140006741  xor     esi, esi
0x140006743  call    WinHvpSetProcessorPartitionSints
0x140006748  mov     edx, ebx; BitNumber
0x14000674a  lea     rcx, [rbp+BitMapHeader]; BitMapHeader
0x14000674e  call    cs:__imp_RtlSetBit
0x140006755  nop     dword ptr [rax+rax+00h]
0x14000675a  inc     ebx
0x14000675c  cmp     ebx, r14d
0x14000675f  jb      loc_1400066D5
0x140006765  test    dil, dil
0x140006768  jz      short loc_14000677A
0x14000676a  lea     rcx, [rbp+PreviousAffinity]; PreviousAffinity
0x14000676e  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x140006775  nop     dword ptr [rax+rax+00h]
0x14000677a  lea     rcx, WinHvpSynicChangeLock; FastMutex
0x140006781  call    cs:__imp_ExReleaseFastMutex
0x140006788  nop     dword ptr [rax+rax+00h]
0x14000678d  mov     rcx, [rbp+var_8]
0x140006791  xor     rcx, rsp; StackCookie
0x140006794  call    __security_check_cookie
0x140006799  add     rsp, 60h
0x14000679d  pop     r14
0x14000679f  pop     rdi
0x1400067a0  pop     rsi
0x1400067a1  pop     rbx
0x1400067a2  pop     rbp
0x1400067a3  retn
```
