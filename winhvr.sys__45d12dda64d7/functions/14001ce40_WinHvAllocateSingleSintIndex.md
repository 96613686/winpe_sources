# WinHvAllocateSingleSintIndex

- ea: `0x14001ce40`
- end: `0x14001d078`
- name: `WinHvAllocateSingleSintIndex`
- size: `568`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1400010e8`
- `0x140006c5c`
- `0x140009c50`
- `0x14001ce40`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14001d015`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001d015`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001cf00`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001cf00`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14001ced0`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14001ced0`
- `ntoskrnl!RtlInitializeBitMap` at `0x14001ceed`
- `ntoskrnl!RtlInitializeBitMap` at `0x14001ceed`
- `ntoskrnl!RtlTestBit` at `0x14001cf1d`
- `ntoskrnl!RtlTestBit` at `0x14001cf1d`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14001cf6f`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14001cf6f`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14001d02a`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14001d02a`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14001cf45`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14001cf45`

## pseudocode

```c
__int64 __fastcall WinHvAllocateSingleSintIndex(int a1, char a2, unsigned int *a3, ULONG *a4)
{
  struct _GROUP_AFFINITY *p_PreviousAffinity; // rsi
  char v7; // r14
  unsigned int j; // ebx
  char v9; // r12
  ULONG ActiveProcessorCount; // r13d
  ULONG i; // edi
  unsigned __int64 v12; // rdx
  struct _PROCESSOR_NUMBER ProcNumber[2]; // [rsp+28h] [rbp-58h] BYREF
  __int64 v15; // [rsp+30h] [rbp-50h] BYREF
  struct _RTL_BITMAP BitMapHeader; // [rsp+38h] [rbp-48h] BYREF
  unsigned int *v17; // [rsp+48h] [rbp-38h]
  ULONG *v18; // [rsp+50h] [rbp-30h]
  struct _GROUP_AFFINITY Affinity; // [rsp+58h] [rbp-28h] BYREF
  struct _GROUP_AFFINITY PreviousAffinity; // [rsp+68h] [rbp-18h] BYREF

  v18 = a4;
  LODWORD(BitMapHeader.Buffer) = 0;
  *(_QWORD *)&BitMapHeader.SizeOfBitMap = 0;
  v17 = a3;
  v15 = 0;
  Affinity = 0;
  PreviousAffinity = 0;
  if ( !a2 && (unsigned __int8)a1 < 0x10u )
    return 3221225485LL;
  if ( !WinHvpConnected )
    return 3224698882LL;
  p_PreviousAffinity = &PreviousAffinity;
  v7 = 0;
  j = 16;
  v9 = 0;
  ActiveProcessorCount = KeQueryActiveProcessorCountEx(0xFFFFu);
  RtlInitializeBitMap(&BitMapHeader, WinHvpSynicProcessorsBitmap, ActiveProcessorCount);
  ExAcquireFastMutex(&WinHvpSynicChangeLock);
  for ( i = 0; i < ActiveProcessorCount; ++i )
  {
    if ( RtlTestBit(&BitMapHeader, i) )
    {
      ProcNumber[0] = 0;
      Affinity = 0;
      KeGetProcessorNumberFromIndex(i, ProcNumber);
      Affinity.Group = ProcNumber[0].Group;
      Affinity.Mask = 1LL << ProcNumber[0].Number;
      KeSetSystemGroupAffinityThread(&Affinity, p_PreviousAffinity);
      v9 = 1;
      *(_QWORD *)&ProcNumber[0].Group = 0;
      for ( j = 5; ; ++j )
      {
        if ( j >= 0x10 )
          goto LABEL_19;
        if ( !*(_DWORD *)(WinHvpGlobalSintVectors + 4LL * j) )
        {
          if ( (int)WinHvpGetVpRegister64Self(j + 655360, &v15) < 0 )
            goto LABEL_19;
          if ( (v15 & 0x10000) != 0 && !(_BYTE)v15 )
            break;
        }
      }
      v12 = v15 & 0xFFFFFFFFFFFEFF00uLL | (unsigned __int8)a1 | ((unsigned __int64)(a2 & 1) << 16);
      v15 = v12;
      if ( a1 == 48 )
        v15 = v12 | 0x80000;
      if ( (int)WinHvpSetVpRegister64Self(j + 655360) < 0 )
      {
LABEL_19:
        p_PreviousAffinity = *(struct _GROUP_AFFINITY **)&ProcNumber[0].Group;
        continue;
      }
      v7 = 1;
      break;
    }
  }
  ExReleaseFastMutex(&WinHvpSynicChangeLock);
  if ( v9 )
    KeRevertToUserGroupAffinityThread(&PreviousAffinity);
  if ( !v7 )
    return 3221225626LL;
  *v17 = j;
  *v18 = i;
  return 0;
}

```

## disassembly

```asm
0x14001ce40  mov     [rsp-38h+arg_0], rbx
0x14001ce45  push    rbp
0x14001ce46  push    rsi
0x14001ce47  push    rdi
0x14001ce48  push    r12
0x14001ce4a  push    r13
0x14001ce4c  push    r14
0x14001ce4e  push    r15
0x14001ce50  mov     rbp, rsp
0x14001ce53  sub     rsp, 80h
0x14001ce5a  mov     rax, cs:__security_cookie
0x14001ce61  xor     rax, rsp
0x14001ce64  mov     [rbp+var_8], rax
0x14001ce68  mov     r15d, ecx
0x14001ce6b  xorps   xmm0, xmm0
0x14001ce6e  xor     ecx, ecx
0x14001ce70  mov     [rbp+var_30], r9
0x14001ce74  mov     qword ptr [rbp+BitMapHeader+4], rcx
0x14001ce78  xorps   xmm1, xmm1
0x14001ce7b  mov     [rbp-48h], rcx
0x14001ce7f  mov     [rbp+var_38], r8
0x14001ce83  mov     [rbp+var_60], dl
0x14001ce86  mov     [rbp+var_50], 0
0x14001ce8e  movups  xmmword ptr [rbp+Affinity.Mask], xmm0
0x14001ce92  movups  xmmword ptr [rbp+PreviousAffinity.Mask], xmm1
0x14001ce96  test    dl, dl
0x14001ce98  jnz     short loc_14001CEAA
0x14001ce9a  cmp     r15b, 10h
0x14001ce9e  jnb     short loc_14001CEAA
0x14001cea0  mov     eax, 0C000000Dh
0x14001cea5  jmp     loc_14001D050
0x14001ceaa  cmp     cs:WinHvpConnected, cl
0x14001ceb0  jnz     short loc_14001CEBC
0x14001ceb2  mov     eax, 0C0350002h
0x14001ceb7  jmp     loc_14001D050
0x14001cebc  mov     ecx, 0FFFFh; GroupNumber
0x14001cec1  lea     rsi, [rbp+PreviousAffinity]
0x14001cec5  xor     r14b, r14b
0x14001cec8  mov     ebx, 10h
0x14001cecd  xor     r12b, r12b
0x14001ced0  call    cs:__imp_KeQueryActiveProcessorCountEx
0x14001ced7  nop     dword ptr [rax+rax+00h]
0x14001cedc  mov     rdx, cs:WinHvpSynicProcessorsBitmap; BitMapBuffer
0x14001cee3  lea     rcx, [rbp+BitMapHeader]; BitMapHeader
0x14001cee7  mov     r8d, eax; SizeOfBitMap
0x14001ceea  mov     r13d, eax
0x14001ceed  call    cs:__imp_RtlInitializeBitMap
0x14001cef4  nop     dword ptr [rax+rax+00h]
0x14001cef9  lea     rcx, WinHvpSynicChangeLock; FastMutex
0x14001cf00  call    cs:__imp_ExAcquireFastMutex
0x14001cf07  nop     dword ptr [rax+rax+00h]
0x14001cf0c  xor     edi, edi
0x14001cf0e  cmp     edi, r13d
0x14001cf11  jnb     loc_14001D00E
0x14001cf17  mov     edx, edi; BitNumber
0x14001cf19  lea     rcx, [rbp+BitMapHeader]; BitMapHeader
0x14001cf1d  call    cs:__imp_RtlTestBit
0x14001cf24  nop     dword ptr [rax+rax+00h]
0x14001cf29  test    al, al
0x14001cf2b  jz      loc_14001D004
0x14001cf31  xorps   xmm0, xmm0
0x14001cf34  mov     dword ptr [rbp+ProcNumber.Group], 0
0x14001cf3b  lea     rdx, [rbp+ProcNumber]; ProcNumber
0x14001cf3f  mov     ecx, edi; ProcIndex
0x14001cf41  movups  xmmword ptr [rbp+Affinity.Mask], xmm0
0x14001cf45  call    cs:__imp_KeGetProcessorNumberFromIndex
0x14001cf4c  nop     dword ptr [rax+rax+00h]
0x14001cf51  movzx   eax, [rbp+ProcNumber.Group]
0x14001cf55  mov     rdx, rsi; PreviousAffinity
0x14001cf58  mov     cl, [rbp+ProcNumber.Number]
0x14001cf5b  mov     [rbp+Affinity.Group], ax
0x14001cf5f  mov     eax, 1
0x14001cf64  shl     rax, cl
0x14001cf67  lea     rcx, [rbp+Affinity]; Affinity
0x14001cf6b  mov     [rbp+Affinity.Mask], rax
0x14001cf6f  call    cs:__imp_KeSetSystemGroupAffinityThread
0x14001cf76  nop     dword ptr [rax+rax+00h]
0x14001cf7b  mov     r12b, 1
0x14001cf7e  mov     qword ptr [rbp+ProcNumber.Group], 0
0x14001cf86  mov     ebx, 5
0x14001cf8b  cmp     ebx, 10h
0x14001cf8e  jnb     short loc_14001D000
0x14001cf90  mov     rax, cs:WinHvpGlobalSintVectors
0x14001cf97  mov     ecx, ebx
0x14001cf99  cmp     dword ptr [rax+rcx*4], 0
0x14001cf9d  jnz     short loc_14001CFC3
0x14001cf9f  lea     esi, [rbx+0A0000h]
0x14001cfa5  mov     ecx, esi
0x14001cfa7  lea     rdx, [rbp+var_50]
0x14001cfab  call    WinHvpGetVpRegister64Self
0x14001cfb0  test    eax, eax
0x14001cfb2  js      short loc_14001D000
0x14001cfb4  mov     rax, [rbp+var_50]
0x14001cfb8  bt      rax, 10h
0x14001cfbd  jnb     short loc_14001CFC3
0x14001cfbf  test    al, al
0x14001cfc1  jz      short loc_14001CFC7
0x14001cfc3  inc     ebx
0x14001cfc5  jmp     short loc_14001CF8B
0x14001cfc7  movzx   edx, [rbp+var_60]
0x14001cfcb  and     rax, 0FFFFFFFFFFFEFF00h
0x14001cfd1  and     edx, 1
0x14001cfd4  movzx   r8d, r15b
0x14001cfd8  shl     rdx, 10h
0x14001cfdc  or      rdx, r8
0x14001cfdf  or      rdx, rax
0x14001cfe2  mov     [rbp+var_50], rdx
0x14001cfe6  cmp     r15d, 30h ; '0'
0x14001cfea  jnz     short loc_14001CFF5
0x14001cfec  bts     rdx, 13h
0x14001cff1  mov     [rbp+var_50], rdx
0x14001cff5  mov     ecx, esi
0x14001cff7  call    WinHvpSetVpRegister64Self
0x14001cffc  test    eax, eax
0x14001cffe  jns     short loc_14001D00B
0x14001d000  mov     rsi, qword ptr [rbp+ProcNumber.Group]
0x14001d004  inc     edi
0x14001d006  jmp     loc_14001CF0E
0x14001d00b  mov     r14b, r12b
0x14001d00e  lea     rcx, WinHvpSynicChangeLock; FastMutex
0x14001d015  call    cs:__imp_ExReleaseFastMutex
0x14001d01c  nop     dword ptr [rax+rax+00h]
0x14001d021  test    r12b, r12b
0x14001d024  jz      short loc_14001D036
0x14001d026  lea     rcx, [rbp+PreviousAffinity]; PreviousAffinity
0x14001d02a  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x14001d031  nop     dword ptr [rax+rax+00h]
0x14001d036  test    r14b, r14b
0x14001d039  jnz     short loc_14001D042
0x14001d03b  mov     eax, 0C000009Ah
0x14001d040  jmp     short loc_14001D050
0x14001d042  mov     rax, [rbp+var_38]
0x14001d046  mov     [rax], ebx
0x14001d048  mov     rax, [rbp+var_30]
0x14001d04c  mov     [rax], edi
0x14001d04e  xor     eax, eax
0x14001d050  mov     rcx, [rbp+var_8]
0x14001d054  xor     rcx, rsp; StackCookie
0x14001d057  call    __security_check_cookie
0x14001d05c  mov     rbx, [rsp+80h+arg_0]
0x14001d064  add     rsp, 80h
0x14001d06b  pop     r15
0x14001d06d  pop     r14
0x14001d06f  pop     r13
0x14001d071  pop     r12
0x14001d073  pop     rdi
0x14001d074  pop     rsi
0x14001d075  pop     rbp
0x14001d076  retn
```
