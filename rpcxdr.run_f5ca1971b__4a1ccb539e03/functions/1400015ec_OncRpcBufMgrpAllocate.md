# OncRpcBufMgrpAllocate

- ea: `0x1400015ec`
- end: `0x1400017fb`
- name: `OncRpcBufMgrpAllocate`
- size: `527`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x140001020`
- `0x140006880`

## callees

- `0x1400015ec`
- `0x140001a2c`
- `0x140001adc`
- `0x140001f78`
- `0x1400020c0`
- `0x140015680`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140001773`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140001773`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001630`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001630`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400017db`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400017db`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000179b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000179b`

## pseudocode

```c
__int64 __fastcall OncRpcBufMgrpAllocate(_QWORD *a1, _QWORD *a2, int a3, unsigned int a4, int a5, __int64 a6)
{
  int v6; // ebx
  void *v7; // rbp
  _QWORD *v11; // r14
  _QWORD *v12; // rax
  _QWORD *v13; // rdi
  __int64 v14; // r8
  _QWORD *DescriptorFromLLLargePoolAllocation; // rax
  KIRQL v16; // al
  __int64 v17; // rdi
  KIRQL v18; // si

  v6 = 0;
  v7 = 0;
  v11 = a1;
  if ( a1 )
  {
    a1 = (_QWORD *)*a1;
    if ( !a1 )
    {
      v12 = ExAllocateFromNPagedLookasideList(&Lookaside);
      v13 = v12;
      if ( v12 )
      {
        ++qword_14001A680;
        ++dword_14001A6E8;
        v12[2] = 0;
        *(_DWORD *)v12 = 1128677970;
        *((_DWORD *)v12 + 1) = 0;
        *((_WORD *)v12 + 4) = 0;
        v12[4] = v12 + 3;
        v12[3] = v12 + 3;
        v12[5] = 0;
        v12[6] = 0;
        *((_DWORD *)v12 + 14) = 1;
      }
      else
      {
        ++qword_14001A688;
        v6 = -1073741670;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            13,
            WPP_bc787cf5db083b51efc6e85b805038bb_Traceguids,
            3221225626LL);
      }
      a1 = v13;
      v7 = v13;
    }
  }
  v14 = 16;
  if ( a4 )
    v14 = a4;
  if ( v6 >= 0 && a3 )
  {
    if ( (unsigned int)(v14 + a3 - 1) > 0x800 )
      DescriptorFromLLLargePoolAllocation = OncRpcBufMgrpAllocateDescriptorFromLLLargePoolAllocation(
                                              (__int64)a1,
                                              a3,
                                              v14,
                                              a6);
    else
      DescriptorFromLLLargePoolAllocation = (_QWORD *)OncRpcBufMgrpAllocateDescriptorFromLLInlineBuffer(a1, a2, v14, a6);
    if ( DescriptorFromLLLargePoolAllocation )
    {
      *a2 = DescriptorFromLLLargePoolAllocation;
LABEL_21:
      if ( v7 )
        *v11 = v7;
      goto LABEL_27;
    }
    v6 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_bc787cf5db083b51efc6e85b805038bb_Traceguids, 3221225626LL);
  }
  *a2 = 0;
  if ( v6 >= 0 )
    goto LABEL_21;
  if ( v7 )
    ExFreeToNPagedLookasideList(&Lookaside, v7);
LABEL_27:
  if ( v6 == -1073741670 )
  {
    v16 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
    v17 = OncRpcGlobals;
    v18 = v16;
    while ( (__int64 *)v17 != &OncRpcGlobals )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD))(v17 + 16))(*(_QWORD *)(v17 + 24), 0);
      v17 = *(_QWORD *)v17;
    }
    KeReleaseSpinLock(&SpinLock, v18);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400015ec  push    rbx
0x1400015ee  push    rbp
0x1400015ef  push    rsi
0x1400015f0  push    rdi
0x1400015f1  push    r12
0x1400015f3  push    r13
0x1400015f5  push    r14
0x1400015f7  push    r15
0x1400015f9  sub     rsp, 28h
0x1400015fd  xor     ebx, ebx
0x1400015ff  lea     rdi, WPP_GLOBAL_Control
0x140001606  xor     ebp, ebp
0x140001608  mov     r12d, r9d
0x14000160b  mov     r15d, r8d
0x14000160e  mov     r13, rdx
0x140001611  mov     r14, rcx
0x140001614  test    rcx, rcx
0x140001617  jz      loc_1400016CD
0x14000161d  mov     rcx, [rcx]
0x140001620  test    rcx, rcx
0x140001623  jnz     loc_1400016CD
0x140001629  lea     rcx, Lookaside; Lookaside
0x140001630  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140001637  nop     dword ptr [rax+rax+00h]
0x14000163c  mov     rdi, rax
0x14000163f  test    rax, rax
0x140001642  jz      short loc_14000168D
0x140001644  inc     cs:qword_14001A680
0x14000164b  inc     cs:dword_14001A6E8
0x140001651  mov     [rax+10h], rbx
0x140001655  mov     dword ptr [rax], 43464252h
0x14000165b  mov     [rax+4], ebx
0x14000165e  xor     eax, eax
0x140001660  mov     [rdi+8], ax
0x140001664  lea     rax, [rdi+18h]
0x140001668  mov     [rax+8], rax
0x14000166c  mov     [rax], rax
0x14000166f  mov     [rdi+28h], rbx
0x140001673  mov     [rdi+30h], rbx
0x140001677  mov     dword ptr [rdi+38h], 1
0x14000167e  mov     rcx, rdi
0x140001681  mov     rbp, rdi
0x140001684  lea     rdi, WPP_GLOBAL_Control
0x14000168b  jmp     short loc_1400016CD
0x14000168d  inc     cs:qword_14001A688
0x140001694  mov     ebx, 0C000009Ah
0x140001699  mov     rcx, cs:WPP_GLOBAL_Control
0x1400016a0  lea     rax, WPP_GLOBAL_Control
0x1400016a7  cmp     rcx, rax
0x1400016aa  jz      short loc_14000167E
0x1400016ac  mov     eax, [rcx+2Ch]
0x1400016af  test    al, 2
0x1400016b1  jz      short loc_14000167E
0x1400016b3  mov     rcx, [rcx+18h]
0x1400016b7  lea     r8, WPP_bc787cf5db083b51efc6e85b805038bb_Traceguids
0x1400016be  mov     edx, 0Dh
0x1400016c3  mov     r9d, ebx
0x1400016c6  call    WPP_SF_d
0x1400016cb  jmp     short loc_14000167E
0x1400016cd  xor     esi, esi
0x1400016cf  test    r12d, r12d
0x1400016d2  lea     r8d, [rsi+10h]
0x1400016d6  cmovnz  r8d, r12d
0x1400016da  test    ebx, ebx
0x1400016dc  js      short loc_14000173E
0x1400016de  test    r15d, r15d
0x1400016e1  jz      short loc_140001757
0x1400016e3  mov     r9, [rsp+68h+arg_28]
0x1400016eb  lea     eax, [r15-1]
0x1400016ef  add     eax, r8d
0x1400016f2  cmp     eax, 800h
0x1400016f7  ja      short loc_140001700
0x1400016f9  call    OncRpcBufMgrpAllocateDescriptorFromLLInlineBuffer
0x1400016fe  jmp     short loc_140001708
0x140001700  mov     edx, r15d
0x140001703  call    OncRpcBufMgrpAllocateDescriptorFromLLLargePoolAllocation
0x140001708  mov     rsi, rax
0x14000170b  test    rax, rax
0x14000170e  jnz     short loc_14000175C
0x140001710  mov     ebx, 0C000009Ah
0x140001715  mov     rcx, cs:WPP_GLOBAL_Control
0x14000171c  cmp     rcx, rdi
0x14000171f  jz      short loc_14000173E
0x140001721  mov     eax, [rcx+2Ch]
0x140001724  test    al, 2
0x140001726  jz      short loc_14000173E
0x140001728  mov     rcx, [rcx+18h]
0x14000172c  lea     edx, [rsi+0Eh]
0x14000172f  mov     r9d, ebx
0x140001732  lea     r8, WPP_bc787cf5db083b51efc6e85b805038bb_Traceguids
0x140001739  call    WPP_SF_d
0x14000173e  mov     qword ptr [r13+0], 0
0x140001746  mov     rdi, rsi
0x140001749  test    ebx, ebx
0x14000174b  js      short loc_140001764
0x14000174d  test    rbp, rbp
0x140001750  jz      short loc_14000177F
0x140001752  mov     [r14], rbp
0x140001755  jmp     short loc_14000177F
0x140001757  test    rsi, rsi
0x14000175a  jz      short loc_14000173E
0x14000175c  xor     edi, edi
0x14000175e  mov     [r13+0], rsi
0x140001762  jmp     short loc_14000174D
0x140001764  test    rbp, rbp
0x140001767  jz      short loc_14000177F
0x140001769  mov     rdx, rbp; Entry
0x14000176c  lea     rcx, Lookaside; Lookaside
0x140001773  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000177a  nop     dword ptr [rax+rax+00h]
0x14000177f  test    rdi, rdi
0x140001782  jz      short loc_14000178C
0x140001784  mov     rcx, rdi; Entry
0x140001787  call    OncRpcBufMgrpDestroyBufferDescriptor
0x14000178c  cmp     ebx, 0C000009Ah
0x140001792  jnz     short loc_1400017E7
0x140001794  lea     rcx, SpinLock; SpinLock
0x14000179b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400017a2  nop     dword ptr [rax+rax+00h]
0x1400017a7  mov     rdi, cs:OncRpcGlobals
0x1400017ae  lea     rbp, OncRpcGlobals
0x1400017b5  mov     sil, al
0x1400017b8  jmp     short loc_1400017CC
0x1400017ba  mov     rax, [rdi+10h]
0x1400017be  xor     edx, edx
0x1400017c0  mov     rcx, [rdi+18h]
0x1400017c4  call    _guard_dispatch_icall
0x1400017c9  mov     rdi, [rdi]
0x1400017cc  cmp     rdi, rbp
0x1400017cf  jnz     short loc_1400017BA
0x1400017d1  mov     dl, sil; NewIrql
0x1400017d4  lea     rcx, SpinLock; SpinLock
0x1400017db  call    cs:__imp_KeReleaseSpinLock
0x1400017e2  nop     dword ptr [rax+rax+00h]
0x1400017e7  mov     eax, ebx
0x1400017e9  add     rsp, 28h
0x1400017ed  pop     r15
0x1400017ef  pop     r14
0x1400017f1  pop     r13
0x1400017f3  pop     r12
0x1400017f5  pop     rdi
0x1400017f6  pop     rsi
0x1400017f7  pop     rbp
0x1400017f8  pop     rbx
0x1400017f9  retn
```
