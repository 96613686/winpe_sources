# PncCreatePartition

- ea: `0x140013a24`
- end: `0x140013bc3`
- name: `PncCreatePartition`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x14002eec0`

## callees

- `0x14000389c`
- `0x1400038cc`
- `0x1400134c4`
- `0x140013a24`
- `0x14002e0bc`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140013ba5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013ba5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013b5e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013b5e`

## pseudocode

```c
__int64 __fastcall PncCreatePartition(const void **a1, _OWORD *a2, __int64 *a3)
{
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned int v9; // ebx
  __int64 v10; // rbx
  KIRQL v11; // al
  _QWORD *v12; // rcx
  __int64 v14; // [rsp+68h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_08e7a226baef3f074c5713b17b66cc56_Traceguids);
  }
  v14 = 0;
  v6 = XPartCreatePartition(a1, a2, &v14);
  v9 = v6;
  if ( v6 >= 0 )
  {
    v10 = v14;
    *(_QWORD *)(v14 + 1008) = PncSendMessage;
    *(_QWORD *)(v10 + 1016) = &PncPullMessage;
    *(_QWORD *)(v10 + 1048) = guard_check_icall_nop;
    *(_QWORD *)(v10 + 1056) = ChildResumeMessages;
    *(_QWORD *)(v10 + 1096) = ChildEnableInterrupt;
    *(_QWORD *)(v10 + 1104) = PncDisableInterrupt;
    *(_DWORD *)(v10 + 176) = -1;
    *(_QWORD *)(v10 + 1112) = PncUpdateInterruptTargetVp;
    *(_QWORD *)(v10 + 1128) = PncProcessorIndexToVpIndex;
    v11 = KeAcquireSpinLockRaiseToDpc(&XPartLibContextStatic);
    v12 = (_QWORD *)qword_1400207F0;
    if ( *(__int64 **)qword_1400207F0 != &qword_1400207E8 )
      __fastfail(3u);
    *(_QWORD *)(v10 + 816) = qword_1400207F0;
    *(_QWORD *)(v10 + 808) = &qword_1400207E8;
    *v12 = v10 + 808;
    qword_1400207F0 = v10 + 808;
    KeReleaseSpinLock(&XPartLibContextStatic, v11);
    *a3 = v10;
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        WPP_08e7a226baef3f074c5713b17b66cc56_Traceguids,
        (unsigned int)v6);
    }
    if ( v14 )
      XPartRemovePartition(v14, v7, v8);
  }
  return v9;
}

```

## disassembly

```asm
0x140013a24  push    rbx
0x140013a26  push    rsi
0x140013a27  push    rdi
0x140013a28  push    r14
0x140013a2a  sub     rsp, 28h
0x140013a2e  mov     rsi, r8
0x140013a31  mov     rbx, rdx
0x140013a34  mov     rdi, rcx
0x140013a37  mov     rcx, cs:WPP_GLOBAL_Control
0x140013a3e  lea     r14, WPP_GLOBAL_Control
0x140013a45  cmp     rcx, r14
0x140013a48  jz      short loc_140013A6E
0x140013a4a  test    dword ptr [rcx+2Ch], 1000000h
0x140013a51  jz      short loc_140013A6E
0x140013a53  cmp     byte ptr [rcx+29h], 4
0x140013a57  jb      short loc_140013A6E
0x140013a59  mov     rcx, [rcx+18h]
0x140013a5d  lea     r8, WPP_08e7a226baef3f074c5713b17b66cc56_Traceguids
0x140013a64  mov     edx, 0Ch
0x140013a69  call    WPP_SF_
0x140013a6e  lea     r8, [rsp+48h+arg_18]
0x140013a73  mov     [rsp+48h+arg_18], 0
0x140013a7c  mov     rdx, rbx
0x140013a7f  mov     rcx, rdi
0x140013a82  call    XPartCreatePartition
0x140013a87  mov     ebx, eax
0x140013a89  test    eax, eax
0x140013a8b  jns     short loc_140013AD8
0x140013a8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140013a94  cmp     rcx, r14
0x140013a97  jz      short loc_140013AC0
0x140013a99  test    dword ptr [rcx+2Ch], 1000000h
0x140013aa0  jz      short loc_140013AC0
0x140013aa2  cmp     byte ptr [rcx+29h], 2
0x140013aa6  jb      short loc_140013AC0
0x140013aa8  mov     rcx, [rcx+18h]
0x140013aac  lea     r8, WPP_08e7a226baef3f074c5713b17b66cc56_Traceguids
0x140013ab3  mov     edx, 0Dh
0x140013ab8  mov     r9d, eax
0x140013abb  call    WPP_SF_d
0x140013ac0  mov     rcx, [rsp+48h+arg_18]
0x140013ac5  test    rcx, rcx
0x140013ac8  jz      loc_140013BB6
0x140013ace  call    XPartRemovePartition
0x140013ad3  jmp     loc_140013BB6
0x140013ad8  mov     rbx, [rsp+48h+arg_18]
0x140013add  lea     rax, PncSendMessage
0x140013ae4  lea     rcx, XPartLibContextStatic; SpinLock
0x140013aeb  mov     [rbx+3F0h], rax
0x140013af2  lea     rax, PncPullMessage
0x140013af9  mov     [rbx+3F8h], rax
0x140013b00  lea     rax, _guard_check_icall_nop
0x140013b07  mov     [rbx+418h], rax
0x140013b0e  lea     rax, ChildResumeMessages
0x140013b15  mov     [rbx+420h], rax
0x140013b1c  lea     rax, ChildEnableInterrupt
0x140013b23  mov     [rbx+448h], rax
0x140013b2a  lea     rax, PncDisableInterrupt
0x140013b31  mov     [rbx+450h], rax
0x140013b38  lea     rax, PncUpdateInterruptTargetVp
0x140013b3f  mov     dword ptr [rbx+0B0h], 0FFFFFFFFh
0x140013b49  mov     [rbx+458h], rax
0x140013b50  lea     rax, PncProcessorIndexToVpIndex
0x140013b57  mov     [rbx+468h], rax
0x140013b5e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013b65  nop     dword ptr [rax+rax+00h]
0x140013b6a  mov     rcx, cs:qword_1400207F0
0x140013b71  lea     r8, qword_1400207E8
0x140013b78  mov     dl, al; NewIrql
0x140013b7a  cmp     [rcx], r8
0x140013b7d  jz      short loc_140013B86
0x140013b7f  mov     ecx, 3
0x140013b84  int     29h; Win8: RtlFailFast(ecx)
0x140013b86  lea     rax, [rbx+328h]
0x140013b8d  mov     [rax+8], rcx
0x140013b91  mov     [rax], r8
0x140013b94  mov     [rcx], rax
0x140013b97  lea     rcx, XPartLibContextStatic; SpinLock
0x140013b9e  mov     cs:qword_1400207F0, rax
0x140013ba5  call    cs:__imp_KeReleaseSpinLock
0x140013bac  nop     dword ptr [rax+rax+00h]
0x140013bb1  mov     [rsi], rbx
0x140013bb4  xor     ebx, ebx
0x140013bb6  mov     eax, ebx
0x140013bb8  add     rsp, 28h
0x140013bbc  pop     r14
0x140013bbe  pop     rdi
0x140013bbf  pop     rsi
0x140013bc0  pop     rbx
0x140013bc1  retn
```
