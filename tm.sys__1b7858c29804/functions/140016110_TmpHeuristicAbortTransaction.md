# TmpHeuristicAbortTransaction

- ea: `0x140016110`
- end: `0x1400161b3`
- name: `TmpHeuristicAbortTransaction`
- size: `163`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140001e84`
- `0x14000f82c`
- `0x140015fc8`
- `0x140016110`
- `0x14001b338`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14001619e`
- `ntoskrnl!KeReleaseMutex` at `0x14001619e`

## pseudocode

```c
__int64 __fastcall TmpHeuristicAbortTransaction(__int64 Object)
{
  TmpAcquireTransactionMutex(Object);
  if ( (unsigned int)(*(_DWORD *)(Object + 192) - 3) <= 1 )
  {
    TmpTraceTransactionHeuristicCorruption(Object);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
      WPP_SF_qq_guid_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        13,
        (unsigned int)WPP_f4159a977dea3a818e35a78ee98eeba7_Traceguids,
        *(_QWORD *)(Object + 512),
        Object,
        Object + 176);
    _InterlockedOr((volatile signed __int32 *)(Object + 196), 0x8000000u);
    TmpForgetTransaction((PVOID)Object);
  }
  KeReleaseMutex((PRKMUTEX)(*(_QWORD *)(Object + 88) + 32LL), 0);
  return 0;
}

```

## disassembly

```asm
0x140016110  push    rbx
0x140016112  sub     rsp, 30h
0x140016116  mov     rbx, rcx
0x140016119  call    TmpAcquireTransactionMutex
0x14001611e  mov     eax, [rbx+0C0h]
0x140016124  sub     eax, 3
0x140016127  cmp     eax, 1
0x14001612a  ja      short loc_140016194
0x14001612c  mov     rcx, rbx
0x14001612f  call    TmpTraceTransactionHeuristicCorruption
0x140016134  mov     rcx, cs:WPP_GLOBAL_Control
0x14001613b  lea     rax, WPP_GLOBAL_Control
0x140016142  cmp     rcx, rax
0x140016145  jz      short loc_14001617B
0x140016147  mov     eax, [rcx+2Ch]
0x14001614a  test    al, 8
0x14001614c  jz      short loc_14001617B
0x14001614e  mov     r9, [rbx+200h]
0x140016155  lea     rax, [rbx+0B0h]
0x14001615c  mov     rcx, [rcx+18h]
0x140016160  lea     r8, WPP_f4159a977dea3a818e35a78ee98eeba7_Traceguids
0x140016167  mov     [rsp+38h+var_10], rax
0x14001616c  mov     edx, 0Dh
0x140016171  mov     [rsp+38h+var_18], rbx
0x140016176  call    WPP_SF_qq_guid_
0x14001617b  lock or dword ptr [rbx+0C4h], 8000000h
0x140016186  mov     r8b, 1
0x140016189  mov     rcx, rbx; Object
0x14001618c  mov     dl, r8b
0x14001618f  call    TmpForgetTransaction
0x140016194  mov     rcx, [rbx+58h]
0x140016198  xor     edx, edx; Wait
0x14001619a  add     rcx, 20h ; ' '; Mutex
0x14001619e  call    cs:__imp_KeReleaseMutex
0x1400161a5  nop     dword ptr [rax+rax+00h]
0x1400161aa  xor     eax, eax
0x1400161ac  add     rsp, 30h
0x1400161b0  pop     rbx
0x1400161b1  retn
```
