# WinHvpCleanupSynicSupport

- ea: `0x14001d4e4`
- end: `0x14001d654`
- name: `WinHvpCleanupSynicSupport`
- size: `368`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14001e5ec`
- `0x14002a804`

## callees

- `0x1400067ac`
- `0x140009c50`
- `0x14000b040`
- `0x14001d4e4`

## import_xrefs

- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14001d531`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14001d531`
- `ntoskrnl!RtlInitializeBitMap` at `0x14001d54d`
- `ntoskrnl!RtlInitializeBitMap` at `0x14001d54d`
- `ntoskrnl!RtlTestBit` at `0x14001d569`
- `ntoskrnl!RtlTestBit` at `0x14001d569`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14001d5b7`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14001d5b7`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14001d5dd`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14001d5dd`
- `ntoskrnl!RtlClearAllBits` at `0x14001d5ed`
- `ntoskrnl!RtlClearAllBits` at `0x14001d5ed`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14001d58d`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14001d58d`

## pseudocode

```c
__int64 WinHvpCleanupSynicSupport()
{
  __int64 result; // rax
  struct _GROUP_AFFINITY *p_PreviousAffinity; // r14
  char v2; // si
  ULONG ActiveProcessorCount; // edi
  ULONG v4; // ebx
  struct _PROCESSOR_NUMBER ProcNumber; // [rsp+20h] [rbp-40h] BYREF
  struct _RTL_BITMAP BitMapHeader; // [rsp+28h] [rbp-38h] BYREF
  struct _GROUP_AFFINITY Affinity; // [rsp+38h] [rbp-28h] BYREF
  struct _GROUP_AFFINITY PreviousAffinity; // [rsp+48h] [rbp-18h] BYREF

  result = 0;
  LODWORD(BitMapHeader.Buffer) = 0;
  *(_QWORD *)&BitMapHeader.SizeOfBitMap = 0;
  Affinity = 0;
  PreviousAffinity = 0;
  if ( WinHvpSynicProcessorsBitmap )
  {
    p_PreviousAffinity = &PreviousAffinity;
    v2 = 0;
    ActiveProcessorCount = KeQueryActiveProcessorCountEx(0xFFFFu);
    RtlInitializeBitMap(&BitMapHeader, WinHvpSynicProcessorsBitmap, ActiveProcessorCount);
    v4 = 0;
    if ( ActiveProcessorCount )
    {
      do
      {
        if ( RtlTestBit(&BitMapHeader, v4) )
        {
          ProcNumber = 0;
          Affinity = 0;
          KeGetProcessorNumberFromIndex(v4, &ProcNumber);
          Affinity.Group = ProcNumber.Group;
          Affinity.Mask = 1LL << ProcNumber.Number;
          KeSetSystemGroupAffinityThread(&Affinity, p_PreviousAffinity);
          p_PreviousAffinity = 0;
          v2 = 1;
          WinHvpDisableSynic();
        }
        ++v4;
      }
      while ( v4 < ActiveProcessorCount );
      if ( v2 )
        KeRevertToUserGroupAffinityThread(&PreviousAffinity);
    }
    RtlClearAllBits(&BitMapHeader);
    if ( WinHvpEventRingControl )
    {
      WinHvpFreePoolWithTag(WinHvpEventRingControl, 1433815127);
      WinHvpEventRingControl = 0;
    }
    result = WinHvpFreePoolWithTag(WinHvpSynicProcessorsBitmap, 1433815127);
    WinHvpSynicProcessorsBitmap = 0;
    WinHvpSynicSupportInitialized = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14001d4e4  push    rbp
0x14001d4e6  push    rbx
0x14001d4e7  push    rsi
0x14001d4e8  push    rdi
0x14001d4e9  push    r14
0x14001d4eb  mov     rbp, rsp
0x14001d4ee  sub     rsp, 60h
0x14001d4f2  mov     rax, cs:__security_cookie
0x14001d4f9  xor     rax, rsp
0x14001d4fc  mov     [rbp+var_8], rax
0x14001d500  xor     eax, eax
0x14001d502  xorps   xmm0, xmm0
0x14001d505  cmp     cs:WinHvpSynicProcessorsBitmap, rax
0x14001d50c  xorps   xmm1, xmm1
0x14001d50f  mov     qword ptr [rbp+BitMapHeader+4], rax
0x14001d513  mov     [rbp-38h], rax
0x14001d517  movups  xmmword ptr [rbp+Affinity.Mask], xmm0
0x14001d51b  movups  xmmword ptr [rbp+PreviousAffinity.Mask], xmm1
0x14001d51f  jz      loc_14001D63C
0x14001d525  mov     ecx, 0FFFFh; GroupNumber
0x14001d52a  lea     r14, [rbp+PreviousAffinity]
0x14001d52e  xor     sil, sil
0x14001d531  call    cs:__imp_KeQueryActiveProcessorCountEx
0x14001d538  nop     dword ptr [rax+rax+00h]
0x14001d53d  mov     rdx, cs:WinHvpSynicProcessorsBitmap; BitMapBuffer
0x14001d544  lea     rcx, [rbp+BitMapHeader]; BitMapHeader
0x14001d548  mov     r8d, eax; SizeOfBitMap
0x14001d54b  mov     edi, eax
0x14001d54d  call    cs:__imp_RtlInitializeBitMap
0x14001d554  nop     dword ptr [rax+rax+00h]
0x14001d559  xor     ebx, ebx
0x14001d55b  test    edi, edi
0x14001d55d  jz      loc_14001D5E9
0x14001d563  mov     edx, ebx; BitNumber
0x14001d565  lea     rcx, [rbp+BitMapHeader]; BitMapHeader
0x14001d569  call    cs:__imp_RtlTestBit
0x14001d570  nop     dword ptr [rax+rax+00h]
0x14001d575  test    al, al
0x14001d577  jz      short loc_14001D5CE
0x14001d579  xorps   xmm0, xmm0
0x14001d57c  mov     dword ptr [rbp+ProcNumber.Group], 0
0x14001d583  lea     rdx, [rbp+ProcNumber]; ProcNumber
0x14001d587  mov     ecx, ebx; ProcIndex
0x14001d589  movups  xmmword ptr [rbp+Affinity.Mask], xmm0
0x14001d58d  call    cs:__imp_KeGetProcessorNumberFromIndex
0x14001d594  nop     dword ptr [rax+rax+00h]
0x14001d599  movzx   eax, [rbp+ProcNumber.Group]
0x14001d59d  mov     rdx, r14; PreviousAffinity
0x14001d5a0  mov     cl, [rbp+ProcNumber.Number]
0x14001d5a3  mov     [rbp+Affinity.Group], ax
0x14001d5a7  mov     eax, 1
0x14001d5ac  shl     rax, cl
0x14001d5af  lea     rcx, [rbp+Affinity]; Affinity
0x14001d5b3  mov     [rbp+Affinity.Mask], rax
0x14001d5b7  call    cs:__imp_KeSetSystemGroupAffinityThread
0x14001d5be  nop     dword ptr [rax+rax+00h]
0x14001d5c3  xor     r14d, r14d
0x14001d5c6  mov     sil, 1
0x14001d5c9  call    WinHvpDisableSynic
0x14001d5ce  inc     ebx
0x14001d5d0  cmp     ebx, edi
0x14001d5d2  jb      short loc_14001D563
0x14001d5d4  test    sil, sil
0x14001d5d7  jz      short loc_14001D5E9
0x14001d5d9  lea     rcx, [rbp+PreviousAffinity]; PreviousAffinity
0x14001d5dd  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x14001d5e4  nop     dword ptr [rax+rax+00h]
0x14001d5e9  lea     rcx, [rbp+BitMapHeader]; BitMapHeader
0x14001d5ed  call    cs:__imp_RtlClearAllBits
0x14001d5f4  nop     dword ptr [rax+rax+00h]
0x14001d5f9  mov     rcx, cs:WinHvpEventRingControl
0x14001d600  mov     ebx, 55764857h
0x14001d605  test    rcx, rcx
0x14001d608  jz      short loc_14001D61C
0x14001d60a  mov     edx, ebx
0x14001d60c  call    WinHvpFreePoolWithTag
0x14001d611  mov     cs:WinHvpEventRingControl, 0
0x14001d61c  mov     rcx, cs:WinHvpSynicProcessorsBitmap
0x14001d623  mov     edx, ebx
0x14001d625  call    WinHvpFreePoolWithTag
0x14001d62a  mov     cs:WinHvpSynicProcessorsBitmap, 0
0x14001d635  mov     cs:WinHvpSynicSupportInitialized, 0
0x14001d63c  mov     rcx, [rbp+var_8]
0x14001d640  xor     rcx, rsp; StackCookie
0x14001d643  call    __security_check_cookie
0x14001d648  add     rsp, 60h
0x14001d64c  pop     r14
0x14001d64e  pop     rdi
0x14001d64f  pop     rsi
0x14001d650  pop     rbx
0x14001d651  pop     rbp
0x14001d652  retn
```
