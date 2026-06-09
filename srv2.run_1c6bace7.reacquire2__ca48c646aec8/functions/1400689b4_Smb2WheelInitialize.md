# Smb2WheelInitialize

- ea: `0x1400689b4`
- end: `0x140068bff`
- name: `Smb2WheelInitialize`
- size: `587`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140062b54`

## callees

- `0x140022690`
- `0x140038490`
- `0x140068928`
- `0x1400689b4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140068a27`
- `ntoskrnl!ExAllocatePool2` at `0x140068a27`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x1400689d9`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x1400689d9`
- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x140068a74`
- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x140068a74`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140068a90`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140068a90`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140068b5f`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140068bcb`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140068b5f`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140068bcb`
- `ntoskrnl!ExAllocatePool3` at `0x140068acc`
- `ntoskrnl!ExAllocatePool3` at `0x140068acc`
- `ntoskrnl!KeQueryNodeMaximumProcessorCount` at `0x140068a4f`
- `ntoskrnl!KeQueryNodeMaximumProcessorCount` at `0x140068a4f`
- `ntoskrnl!InitializeSListHead` at `0x140068b3e`
- `ntoskrnl!InitializeSListHead` at `0x140068b3e`
- `ntoskrnl!KeInitializeDpc` at `0x140068b20`
- `ntoskrnl!KeInitializeDpc` at `0x140068b20`
- `ntoskrnl!KeInitializeTimerEx` at `0x140068afe`
- `ntoskrnl!KeInitializeTimerEx` at `0x140068afe`

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
0x1400689b4  push    rbp
0x1400689b6  push    rbx
0x1400689b7  push    rsi
0x1400689b8  push    rdi
0x1400689b9  push    r12
0x1400689bb  push    r13
0x1400689bd  push    r14
0x1400689bf  push    r15
0x1400689c1  mov     rbp, rsp
0x1400689c4  sub     rsp, 78h
0x1400689c8  mov     rax, cs:__security_cookie
0x1400689cf  xor     rax, rsp
0x1400689d2  mov     [rbp+var_10], rax
0x1400689d6  mov     r13, rcx
0x1400689d9  call    cs:__imp_KeQueryHighestNodeNumber
0x1400689e0  nop     dword ptr [rax+rax+00h]
0x1400689e5  mov     rbx, [r13+0A0h]
0x1400689ec  mov     esi, 1
0x1400689f1  xorps   xmm0, xmm0
0x1400689f4  xorps   xmm1, xmm1
0x1400689f7  movups  xmmword ptr [rbp+PreviousAffinity.Mask], xmm0
0x1400689fb  add     rbx, 890h
0x140068a02  mov     r8d, 6869534Ch
0x140068a08  lea     r12d, [rsi+rax]
0x140068a0c  xor     r14b, r14b
0x140068a0f  xor     eax, eax
0x140068a11  movzx   edx, r12w
0x140068a15  movups  xmmword ptr [rbp+Affinity.Mask], xmm1
0x140068a19  mov     [rbp+Count], ax
0x140068a1d  lea     ecx, [rsi+3Fh]
0x140068a20  shl     rdx, 3
0x140068a24  mov     [rbx], r13
0x140068a27  call    cs:__imp_ExAllocatePool2
0x140068a2e  nop     dword ptr [rax+rax+00h]
0x140068a33  mov     [rbx+10h], rax
0x140068a37  test    rax, rax
0x140068a3a  jz      loc_140068B84
0x140068a40  xor     edi, edi
0x140068a42  cmp     di, r12w
0x140068a46  jnb     loc_140068B7B
0x140068a4c  movzx   ecx, di; NodeNumber
0x140068a4f  call    cs:__imp_KeQueryNodeMaximumProcessorCount
0x140068a56  nop     dword ptr [rax+rax+00h]
0x140068a5b  movzx   ecx, ax
0x140068a5e  xor     eax, eax
0x140068a60  cmp     ax, cx
0x140068a63  jz      loc_140068B73
0x140068a69  lea     r8, [rbp+Count]; Count
0x140068a6d  movzx   ecx, di; NodeNumber
0x140068a70  lea     rdx, [rbp+Affinity]; Affinity
0x140068a74  call    cs:__imp_KeQueryNodeActiveAffinity
0x140068a7b  nop     dword ptr [rax+rax+00h]
0x140068a80  xor     eax, eax
0x140068a82  cmp     ax, [rbp+Count]
0x140068a86  jz      short loc_140068A9F
0x140068a88  lea     rdx, [rbp+PreviousAffinity]; PreviousAffinity
0x140068a8c  lea     rcx, [rbp+Affinity]; Affinity
0x140068a90  call    cs:__imp_KeSetSystemGroupAffinityThread
0x140068a97  nop     dword ptr [rax+rax+00h]
0x140068a9c  mov     r14b, sil
0x140068a9f  movzx   eax, di
0x140068aa2  lea     r9, [rbp+var_40]
0x140068aa6  bts     eax, 1Fh
0x140068aaa  mov     [rbp+var_40], 3
0x140068ab2  mov     [rbp+var_38], eax
0x140068ab5  mov     edx, 6D0h
0x140068aba  xor     eax, eax
0x140068abc  mov     dword ptr [rsp+78h+var_58], esi
0x140068ac0  mov     r8d, 6869534Ch
0x140068ac6  mov     [rbp+var_34], eax
0x140068ac9  lea     ecx, [rax+40h]
0x140068acc  call    cs:__imp_ExAllocatePool3
0x140068ad3  nop     dword ptr [rax+rax+00h]
0x140068ad8  mov     rcx, rax
0x140068adb  movzx   r15d, di
0x140068adf  mov     rax, [rbx+10h]
0x140068ae3  mov     [rax+r15*8], rcx
0x140068ae7  mov     rax, [rbx+10h]
0x140068aeb  mov     rcx, [rax+r15*8]
0x140068aef  test    rcx, rcx
0x140068af2  jz      loc_140068B84
0x140068af8  add     rcx, 8; Timer
0x140068afc  xor     edx, edx; Type
0x140068afe  call    cs:__imp_KeInitializeTimerEx
0x140068b05  nop     dword ptr [rax+rax+00h]
0x140068b0a  mov     rax, [rbx+10h]
0x140068b0e  lea     rdx, Smb2WheelWorkerDpc; DeferredRoutine
0x140068b15  mov     r8, rbx; DeferredContext
0x140068b18  mov     rcx, [rax+r15*8]
0x140068b1c  add     rcx, 48h ; 'H'; Dpc
0x140068b20  call    cs:__imp_KeInitializeDpc
0x140068b27  nop     dword ptr [rax+rax+00h]
0x140068b2c  xor     esi, esi
0x140068b2e  mov     rax, [rbx+10h]
0x140068b32  lea     rcx, [rsi+9]
0x140068b36  shl     rcx, 4
0x140068b3a  add     rcx, [rax+r15*8]; SListHead
0x140068b3e  call    cs:__imp_InitializeSListHead
0x140068b45  nop     dword ptr [rax+rax+00h]
0x140068b4a  inc     rsi
0x140068b4d  cmp     rsi, 64h ; 'd'
0x140068b51  jnz     short loc_140068B2E
0x140068b53  xor     eax, eax
0x140068b55  cmp     ax, [rbp+Count]
0x140068b59  jz      short loc_140068B6E
0x140068b5b  lea     rcx, [rbp+PreviousAffinity]; PreviousAffinity
0x140068b5f  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x140068b66  nop     dword ptr [rax+rax+00h]
0x140068b6b  xor     r14b, r14b
0x140068b6e  mov     esi, 1
0x140068b73  add     di, si
0x140068b76  jmp     loc_140068A42
0x140068b7b  mov     [rbx+0Ch], sil
0x140068b7f  mov     al, sil
0x140068b82  jmp     short loc_140068BE1
0x140068b84  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140068b8b  lea     rax, WPP_GLOBAL_Control
0x140068b92  cmp     rcx, rax
0x140068b95  jz      short loc_140068BC2
0x140068b97  mov     eax, [rcx+2Ch]
0x140068b9a  test    sil, al
0x140068b9d  jz      short loc_140068BC2
0x140068b9f  cmp     [rcx+29h], sil
0x140068ba3  jb      short loc_140068BC2
0x140068ba5  mov     rcx, [rcx+18h]
0x140068ba9  lea     r8, WPP_eb44a7786d4334828a64499dcbd177e5_Traceguids
0x140068bb0  mov     edx, 10h
0x140068bb5  mov     [rsp+78h+var_58], rbx
0x140068bba  mov     r9, r13
0x140068bbd  call    WPP_SF_qq
0x140068bc2  test    r14b, r14b
0x140068bc5  jz      short loc_140068BD7
0x140068bc7  lea     rcx, [rbp+PreviousAffinity]; PreviousAffinity
0x140068bcb  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x140068bd2  nop     dword ptr [rax+rax+00h]
0x140068bd7  mov     rcx, rbx
0x140068bda  call    Smb2WheelFreeNodes
0x140068bdf  xor     al, al
0x140068be1  mov     rcx, [rbp+var_10]
0x140068be5  xor     rcx, rsp; StackCookie
0x140068be8  call    __security_check_cookie
0x140068bed  add     rsp, 78h
0x140068bf1  pop     r15
0x140068bf3  pop     r14
0x140068bf5  pop     r13
0x140068bf7  pop     r12
0x140068bf9  pop     rdi
0x140068bfa  pop     rsi
0x140068bfb  pop     rbx
0x140068bfc  pop     rbp
0x140068bfd  retn
```
