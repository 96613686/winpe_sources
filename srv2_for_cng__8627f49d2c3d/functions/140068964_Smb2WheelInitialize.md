# Smb2WheelInitialize

- ea: `0x140068964`
- end: `0x140068baf`
- name: `Smb2WheelInitialize`
- size: `587`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140062b04`

## callees

- `0x140022690`
- `0x140038490`
- `0x1400688d8`
- `0x140068964`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400689d7`
- `ntoskrnl!ExAllocatePool2` at `0x1400689d7`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x140068989`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x140068989`
- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x140068a24`
- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x140068a24`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140068a40`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140068a40`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140068b0f`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140068b7b`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140068b0f`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140068b7b`
- `ntoskrnl!ExAllocatePool3` at `0x140068a7c`
- `ntoskrnl!ExAllocatePool3` at `0x140068a7c`
- `ntoskrnl!KeQueryNodeMaximumProcessorCount` at `0x1400689ff`
- `ntoskrnl!KeQueryNodeMaximumProcessorCount` at `0x1400689ff`
- `ntoskrnl!InitializeSListHead` at `0x140068aee`
- `ntoskrnl!InitializeSListHead` at `0x140068aee`
- `ntoskrnl!KeInitializeDpc` at `0x140068ad0`
- `ntoskrnl!KeInitializeDpc` at `0x140068ad0`
- `ntoskrnl!KeInitializeTimerEx` at `0x140068aae`
- `ntoskrnl!KeInitializeTimerEx` at `0x140068aae`

## pseudocode

```c
char __fastcall Smb2WheelInitialize(__int64 a1)
{
  USHORT HighestNodeNumber; // ax
  __int64 v3; // rbx
  _QWORD *v4; // rbx
  USHORT v5; // r12
  char v6; // r14
  __int64 Pool2; // rax
  USHORT i; // di
  __int64 v9; // rcx
  __int64 j; // rsi
  USHORT Count; // [rsp+30h] [rbp-48h] BYREF
  __int64 v13; // [rsp+38h] [rbp-40h] BYREF
  unsigned int v14; // [rsp+40h] [rbp-38h]
  int v15; // [rsp+44h] [rbp-34h]
  struct _GROUP_AFFINITY PreviousAffinity; // [rsp+48h] [rbp-30h] BYREF
  struct _GROUP_AFFINITY Affinity; // [rsp+58h] [rbp-20h] BYREF

  HighestNodeNumber = KeQueryHighestNodeNumber();
  v3 = *(_QWORD *)(a1 + 160);
  PreviousAffinity = 0;
  v4 = (_QWORD *)(v3 + 2192);
  v5 = HighestNodeNumber + 1;
  v6 = 0;
  Affinity = 0;
  Count = 0;
  *v4 = a1;
  Pool2 = ExAllocatePool2(64, 8LL * (unsigned __int16)(HighestNodeNumber + 1), 1751733068);
  v4[2] = Pool2;
  if ( Pool2 )
  {
    for ( i = 0; i < v5; ++i )
    {
      if ( KeQueryNodeMaximumProcessorCount(i) )
      {
        KeQueryNodeActiveAffinity(i, &Affinity, &Count);
        if ( Count )
        {
          KeSetSystemGroupAffinityThread(&Affinity, &PreviousAffinity);
          v6 = 1;
        }
        v13 = 3;
        v14 = i | 0x80000000;
        v15 = 0;
        *(_QWORD *)(v4[2] + 8LL * i) = ExAllocatePool3(64, 1744, 1751733068, &v13, 1);
        v9 = *(_QWORD *)(v4[2] + 8LL * i);
        if ( !v9 )
          goto LABEL_14;
        KeInitializeTimerEx((PKTIMER)(v9 + 8), NotificationTimer);
        KeInitializeDpc((PRKDPC)(*(_QWORD *)(v4[2] + 8LL * i) + 72LL), Smb2WheelWorkerDpc, v4);
        for ( j = 0; j != 100; ++j )
          InitializeSListHead((PSLIST_HEADER)(*(_QWORD *)(v4[2] + 8LL * i) + 16 * (j + 9)));
        if ( Count )
        {
          KeRevertToUserGroupAffinityThread(&PreviousAffinity);
          v6 = 0;
        }
      }
    }
    *((_BYTE *)v4 + 12) = 1;
    return 1;
  }
  else
  {
LABEL_14:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_eb44a7786d4334828a64499dcbd177e5_Traceguids, a1, v4);
    }
    if ( v6 )
      KeRevertToUserGroupAffinityThread(&PreviousAffinity);
    Smb2WheelFreeNodes(v4);
    return 0;
  }
}

```

## disassembly

```asm
0x140068964  push    rbp
0x140068966  push    rbx
0x140068967  push    rsi
0x140068968  push    rdi
0x140068969  push    r12
0x14006896b  push    r13
0x14006896d  push    r14
0x14006896f  push    r15
0x140068971  mov     rbp, rsp
0x140068974  sub     rsp, 78h
0x140068978  mov     rax, cs:__security_cookie
0x14006897f  xor     rax, rsp
0x140068982  mov     [rbp+var_10], rax
0x140068986  mov     r13, rcx
0x140068989  call    cs:__imp_KeQueryHighestNodeNumber
0x140068990  nop     dword ptr [rax+rax+00h]
0x140068995  mov     rbx, [r13+0A0h]
0x14006899c  mov     esi, 1
0x1400689a1  xorps   xmm0, xmm0
0x1400689a4  xorps   xmm1, xmm1
0x1400689a7  movups  xmmword ptr [rbp+PreviousAffinity.Mask], xmm0
0x1400689ab  add     rbx, 890h
0x1400689b2  mov     r8d, 6869534Ch
0x1400689b8  lea     r12d, [rsi+rax]
0x1400689bc  xor     r14b, r14b
0x1400689bf  xor     eax, eax
0x1400689c1  movzx   edx, r12w
0x1400689c5  movups  xmmword ptr [rbp+Affinity.Mask], xmm1
0x1400689c9  mov     [rbp+Count], ax
0x1400689cd  lea     ecx, [rsi+3Fh]
0x1400689d0  shl     rdx, 3
0x1400689d4  mov     [rbx], r13
0x1400689d7  call    cs:__imp_ExAllocatePool2
0x1400689de  nop     dword ptr [rax+rax+00h]
0x1400689e3  mov     [rbx+10h], rax
0x1400689e7  test    rax, rax
0x1400689ea  jz      loc_140068B34
0x1400689f0  xor     edi, edi
0x1400689f2  cmp     di, r12w
0x1400689f6  jnb     loc_140068B2B
0x1400689fc  movzx   ecx, di; NodeNumber
0x1400689ff  call    cs:__imp_KeQueryNodeMaximumProcessorCount
0x140068a06  nop     dword ptr [rax+rax+00h]
0x140068a0b  movzx   ecx, ax
0x140068a0e  xor     eax, eax
0x140068a10  cmp     ax, cx
0x140068a13  jz      loc_140068B23
0x140068a19  lea     r8, [rbp+Count]; Count
0x140068a1d  movzx   ecx, di; NodeNumber
0x140068a20  lea     rdx, [rbp+Affinity]; Affinity
0x140068a24  call    cs:__imp_KeQueryNodeActiveAffinity
0x140068a2b  nop     dword ptr [rax+rax+00h]
0x140068a30  xor     eax, eax
0x140068a32  cmp     ax, [rbp+Count]
0x140068a36  jz      short loc_140068A4F
0x140068a38  lea     rdx, [rbp+PreviousAffinity]; PreviousAffinity
0x140068a3c  lea     rcx, [rbp+Affinity]; Affinity
0x140068a40  call    cs:__imp_KeSetSystemGroupAffinityThread
0x140068a47  nop     dword ptr [rax+rax+00h]
0x140068a4c  mov     r14b, sil
0x140068a4f  movzx   eax, di
0x140068a52  lea     r9, [rbp+var_40]
0x140068a56  bts     eax, 1Fh
0x140068a5a  mov     [rbp+var_40], 3
0x140068a62  mov     [rbp+var_38], eax
0x140068a65  mov     edx, 6D0h
0x140068a6a  xor     eax, eax
0x140068a6c  mov     dword ptr [rsp+78h+var_58], esi
0x140068a70  mov     r8d, 6869534Ch
0x140068a76  mov     [rbp+var_34], eax
0x140068a79  lea     ecx, [rax+40h]
0x140068a7c  call    cs:__imp_ExAllocatePool3
0x140068a83  nop     dword ptr [rax+rax+00h]
0x140068a88  mov     rcx, rax
0x140068a8b  movzx   r15d, di
0x140068a8f  mov     rax, [rbx+10h]
0x140068a93  mov     [rax+r15*8], rcx
0x140068a97  mov     rax, [rbx+10h]
0x140068a9b  mov     rcx, [rax+r15*8]
0x140068a9f  test    rcx, rcx
0x140068aa2  jz      loc_140068B34
0x140068aa8  add     rcx, 8; Timer
0x140068aac  xor     edx, edx; Type
0x140068aae  call    cs:__imp_KeInitializeTimerEx
0x140068ab5  nop     dword ptr [rax+rax+00h]
0x140068aba  mov     rax, [rbx+10h]
0x140068abe  lea     rdx, Smb2WheelWorkerDpc; DeferredRoutine
0x140068ac5  mov     r8, rbx; DeferredContext
0x140068ac8  mov     rcx, [rax+r15*8]
0x140068acc  add     rcx, 48h ; 'H'; Dpc
0x140068ad0  call    cs:__imp_KeInitializeDpc
0x140068ad7  nop     dword ptr [rax+rax+00h]
0x140068adc  xor     esi, esi
0x140068ade  mov     rax, [rbx+10h]
0x140068ae2  lea     rcx, [rsi+9]
0x140068ae6  shl     rcx, 4
0x140068aea  add     rcx, [rax+r15*8]; SListHead
0x140068aee  call    cs:__imp_InitializeSListHead
0x140068af5  nop     dword ptr [rax+rax+00h]
0x140068afa  inc     rsi
0x140068afd  cmp     rsi, 64h ; 'd'
0x140068b01  jnz     short loc_140068ADE
0x140068b03  xor     eax, eax
0x140068b05  cmp     ax, [rbp+Count]
0x140068b09  jz      short loc_140068B1E
0x140068b0b  lea     rcx, [rbp+PreviousAffinity]; PreviousAffinity
0x140068b0f  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x140068b16  nop     dword ptr [rax+rax+00h]
0x140068b1b  xor     r14b, r14b
0x140068b1e  mov     esi, 1
0x140068b23  add     di, si
0x140068b26  jmp     loc_1400689F2
0x140068b2b  mov     [rbx+0Ch], sil
0x140068b2f  mov     al, sil
0x140068b32  jmp     short loc_140068B91
0x140068b34  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140068b3b  lea     rax, WPP_GLOBAL_Control
0x140068b42  cmp     rcx, rax
0x140068b45  jz      short loc_140068B72
0x140068b47  mov     eax, [rcx+2Ch]
0x140068b4a  test    sil, al
0x140068b4d  jz      short loc_140068B72
0x140068b4f  cmp     [rcx+29h], sil
0x140068b53  jb      short loc_140068B72
0x140068b55  mov     rcx, [rcx+18h]
0x140068b59  lea     r8, WPP_eb44a7786d4334828a64499dcbd177e5_Traceguids
0x140068b60  mov     edx, 10h
0x140068b65  mov     [rsp+78h+var_58], rbx
0x140068b6a  mov     r9, r13
0x140068b6d  call    WPP_SF_qq
0x140068b72  test    r14b, r14b
0x140068b75  jz      short loc_140068B87
0x140068b77  lea     rcx, [rbp+PreviousAffinity]; PreviousAffinity
0x140068b7b  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x140068b82  nop     dword ptr [rax+rax+00h]
0x140068b87  mov     rcx, rbx
0x140068b8a  call    Smb2WheelFreeNodes
0x140068b8f  xor     al, al
0x140068b91  mov     rcx, [rbp+var_10]
0x140068b95  xor     rcx, rsp; StackCookie
0x140068b98  call    __security_check_cookie
0x140068b9d  add     rsp, 78h
0x140068ba1  pop     r15
0x140068ba3  pop     r14
0x140068ba5  pop     r13
0x140068ba7  pop     r12
0x140068ba9  pop     rdi
0x140068baa  pop     rsi
0x140068bab  pop     rbx
0x140068bac  pop     rbp
0x140068bad  retn
```
