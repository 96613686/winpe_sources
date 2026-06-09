# PgmSendODataCompletion

- ea: `0x140018b00`
- end: `0x140018d7a`
- name: `PgmSendODataCompletion`
- size: `634`
- prototype: `void __fastcall(__int64, void *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140005038`
- `0x140005068`
- `0x1400067f4`
- `0x140007f1c`
- `0x140018b00`
- `0x14001b310`
- `0x14001b7a4`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140018d36`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140018d36`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018d17`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018d17`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018b30`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018b30`

## pseudocode

```c
void __fastcall PgmSendODataCompletion(__int64 a1, void *a2, int a3)
{
  _QWORD *v3; // r15
  __int64 v7; // r14
  IRP *v8; // rdi
  __int64 v9; // r8
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // r9d
  __int64 v14; // rdx
  KIRQL NewIrql; // [rsp+90h] [rbp+18h]

  v3 = *(_QWORD **)(a1 + 40);
  v7 = 0;
  v8 = 0;
  NewIrql = KeAcquireSpinLockRaiseToDpc(v3 + 45);
  if ( a3 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        53,
        WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids,
        (unsigned int)a3);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids);
    if ( !a2 )
      ++*(_DWORD *)(a1 + 132);
  }
  if ( (*(_DWORD *)(a1 + 136))-- == 1 && !*(_DWORD *)(a1 + 140) && !*(_DWORD *)(a1 + 104) )
  {
    v11 = *(unsigned int *)(a1 + 108);
    if ( *(_DWORD *)(a1 + 128) == (_DWORD)v11 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        WPP_SF_dqddd(
          WPP_GLOBAL_Control->AttachedDevice,
          v11,
          v9,
          *(unsigned int *)(a1 + 16),
          *(_QWORD *)(a1 + 24),
          v11,
          *(_DWORD *)(a1 + 88),
          *(_DWORD *)(a1 + 92));
      v3[23] += *(unsigned int *)(a1 + 100);
      v7 = *(_QWORD *)(a1 + 24);
      if ( v7 )
      {
        v12 = *(unsigned int *)(a1 + 128);
        v13 = *(_DWORD *)(a1 + 132);
        if ( v13 == (_DWORD)v12 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
          {
            WPP_SF_qqqdd(
              WPP_GLOBAL_Control->AttachedDevice,
              55,
              v12,
              v7,
              *(_QWORD *)(a1 + 32),
              a1,
              v13,
              *(_DWORD *)(a1 + 128));
          }
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        {
          WPP_SF_qqqdd(
            WPP_GLOBAL_Control->AttachedDevice,
            56,
            v12,
            v7,
            *(_QWORD *)(a1 + 32),
            a1,
            v13,
            *(_DWORD *)(a1 + 128));
        }
        *(_QWORD *)(a1 + 24) = 0;
        v8 = *(IRP **)(a1 + 32);
      }
      v14 = *(_QWORD *)(a1 + 80);
      if ( v14 )
      {
        if ( v8 )
        {
          v8 = 0;
          *(_QWORD *)(v14 + 32) = *(_QWORD *)(a1 + 32);
          *(_QWORD *)(a1 + 32) = 0;
        }
        *(_QWORD *)(*(_QWORD *)(a1 + 80) + 80LL) = 0;
        *(_QWORD *)(a1 + 80) = 0;
      }
    }
  }
  KeReleaseSpinLock(v3 + 45, NewIrql);
  if ( a2 )
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v3[5] + 448LL), a2);
  if ( v7 )
  {
    if ( v8 )
      PgmIoComplete(v8);
    PgmDereferenceSessionCommon(v3);
  }
}

```

## disassembly

```asm
0x140018b00  mov     [rsp+arg_8], rbx
0x140018b05  push    rbp
0x140018b06  push    rsi
0x140018b07  push    rdi
0x140018b08  push    r12
0x140018b0a  push    r13
0x140018b0c  push    r14
0x140018b0e  push    r15
0x140018b10  sub     rsp, 40h
0x140018b14  mov     r15, [rcx+28h]
0x140018b18  mov     rbx, rcx
0x140018b1b  mov     ebp, r8d
0x140018b1e  mov     r13, rdx
0x140018b21  xor     r12d, r12d
0x140018b24  xor     r14d, r14d
0x140018b27  xor     edi, edi
0x140018b29  lea     rcx, [r15+168h]; SpinLock
0x140018b30  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018b37  nop     dword ptr [rax+rax+00h]
0x140018b3c  mov     [rsp+78h+NewIrql], al
0x140018b43  test    ebp, ebp
0x140018b45  js      short loc_140018B82
0x140018b47  mov     rcx, cs:WPP_GLOBAL_Control
0x140018b4e  lea     rsi, WPP_GLOBAL_Control
0x140018b55  cmp     rcx, rsi
0x140018b58  jz      short loc_140018B75
0x140018b5a  mov     edx, [rcx+2Ch]
0x140018b5d  test    dl, 10h
0x140018b60  jz      short loc_140018B75
0x140018b62  mov     rcx, [rcx+18h]
0x140018b66  lea     edx, [rdi+34h]
0x140018b69  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x140018b70  call    WPP_SF_
0x140018b75  test    r13, r13
0x140018b78  jnz     short loc_140018BB4
0x140018b7a  inc     dword ptr [rbx+84h]
0x140018b80  jmp     short loc_140018BB4
0x140018b82  mov     rcx, cs:WPP_GLOBAL_Control
0x140018b89  lea     rsi, WPP_GLOBAL_Control
0x140018b90  cmp     rcx, rsi
0x140018b93  jz      short loc_140018BB4
0x140018b95  mov     eax, [rcx+2Ch]
0x140018b98  test    al, 2
0x140018b9a  jz      short loc_140018BB4
0x140018b9c  mov     rcx, [rcx+18h]
0x140018ba0  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x140018ba7  mov     edx, 35h ; '5'
0x140018bac  mov     r9d, ebp
0x140018baf  call    WPP_SF_d
0x140018bb4  add     dword ptr [rbx+88h], 0FFFFFFFFh
0x140018bbb  jnz     loc_140018D09
0x140018bc1  cmp     [rbx+8Ch], edi
0x140018bc7  jnz     loc_140018D09
0x140018bcd  cmp     [rbx+68h], edi
0x140018bd0  jnz     loc_140018D09
0x140018bd6  mov     edx, [rbx+6Ch]
0x140018bd9  cmp     [rbx+80h], edx
0x140018bdf  jnz     loc_140018D09
0x140018be5  mov     rcx, cs:WPP_GLOBAL_Control
0x140018bec  cmp     rcx, rsi
0x140018bef  jz      short loc_140018C20
0x140018bf1  mov     eax, [rcx+2Ch]
0x140018bf4  test    al, 10h
0x140018bf6  jz      short loc_140018C20
0x140018bf8  mov     eax, [rbx+5Ch]
0x140018bfb  mov     r9d, [rbx+10h]
0x140018bff  mov     rcx, [rcx+18h]
0x140018c03  mov     [rsp+78h+var_40], eax
0x140018c07  mov     eax, [rbx+58h]
0x140018c0a  mov     [rsp+78h+var_48], eax
0x140018c0e  mov     rax, [rbx+18h]
0x140018c12  mov     dword ptr [rsp+78h+var_50], edx
0x140018c16  mov     [rsp+78h+var_58], rax
0x140018c1b  call    WPP_SF_dqddd
0x140018c20  mov     eax, [rbx+64h]
0x140018c23  add     [r15+0B8h], rax
0x140018c2a  mov     r14, [rbx+18h]
0x140018c2e  test    r14, r14
0x140018c31  jz      loc_140018CD5
0x140018c37  mov     r8d, [rbx+80h]
0x140018c3e  mov     r9d, [rbx+84h]
0x140018c45  cmp     r9d, r8d
0x140018c48  jnz     short loc_140018C8C
0x140018c4a  mov     r12d, [rbx+64h]
0x140018c4e  xor     ebp, ebp
0x140018c50  mov     rcx, cs:WPP_GLOBAL_Control
0x140018c57  cmp     rcx, rsi
0x140018c5a  jz      short loc_140018CCD
0x140018c5c  mov     eax, [rcx+2Ch]
0x140018c5f  test    al, 20h
0x140018c61  jz      short loc_140018CCD
0x140018c63  mov     rax, [rbx+20h]
0x140018c67  lea     edx, [rbp+37h]
0x140018c6a  mov     rcx, [rcx+18h]
0x140018c6e  mov     [rsp+78h+var_40], r8d
0x140018c73  mov     [rsp+78h+var_48], r9d
0x140018c78  mov     r9, r14
0x140018c7b  mov     [rsp+78h+var_50], rbx
0x140018c80  mov     [rsp+78h+var_58], rax
0x140018c85  call    WPP_SF_qqqdd
0x140018c8a  jmp     short loc_140018CCD
0x140018c8c  mov     rcx, cs:WPP_GLOBAL_Control
0x140018c93  cmp     rcx, rsi
0x140018c96  jz      short loc_140018CC8
0x140018c98  mov     eax, [rcx+2Ch]
0x140018c9b  test    al, 2
0x140018c9d  jz      short loc_140018CC8
0x140018c9f  mov     rax, [rbx+20h]
0x140018ca3  mov     edx, 38h ; '8'
0x140018ca8  mov     rcx, [rcx+18h]
0x140018cac  mov     [rsp+78h+var_40], r8d
0x140018cb1  mov     [rsp+78h+var_48], r9d
0x140018cb6  mov     r9, r14
0x140018cb9  mov     [rsp+78h+var_50], rbx
0x140018cbe  mov     [rsp+78h+var_58], rax
0x140018cc3  call    WPP_SF_qqqdd
0x140018cc8  mov     ebp, 0C0000001h
0x140018ccd  mov     [rbx+18h], rdi
0x140018cd1  mov     rdi, [rbx+20h]
0x140018cd5  mov     rdx, [rbx+50h]
0x140018cd9  test    rdx, rdx
0x140018cdc  jz      short loc_140018D09
0x140018cde  test    rdi, rdi
0x140018ce1  jz      short loc_140018CF5
0x140018ce3  mov     rax, [rbx+20h]
0x140018ce7  xor     edi, edi
0x140018ce9  mov     [rdx+20h], rax
0x140018ced  mov     qword ptr [rbx+20h], 0
0x140018cf5  mov     rax, [rbx+50h]
0x140018cf9  mov     qword ptr [rax+50h], 0
0x140018d01  mov     qword ptr [rbx+50h], 0
0x140018d09  mov     dl, [rsp+78h+NewIrql]; NewIrql
0x140018d10  lea     rcx, [r15+168h]; SpinLock
0x140018d17  call    cs:__imp_KeReleaseSpinLock
0x140018d1e  nop     dword ptr [rax+rax+00h]
0x140018d23  test    r13, r13
0x140018d26  jz      short loc_140018D42
0x140018d28  mov     rcx, [r15+28h]
0x140018d2c  mov     rdx, r13; Entry
0x140018d2f  add     rcx, 1C0h; Lookaside
0x140018d36  call    cs:__imp_ExFreeToNPagedLookasideList
0x140018d3d  nop     dword ptr [rax+rax+00h]
0x140018d42  test    r14, r14
0x140018d45  jz      short loc_140018D61
0x140018d47  test    rdi, rdi
0x140018d4a  jz      short loc_140018D59
0x140018d4c  mov     r8d, r12d
0x140018d4f  mov     edx, ebp
0x140018d51  mov     rcx, rdi; Irp
0x140018d54  call    PgmIoComplete
0x140018d59  mov     rcx, r15
0x140018d5c  call    PgmDereferenceSessionCommon
0x140018d61  mov     rbx, [rsp+78h+arg_8]
0x140018d69  add     rsp, 40h
0x140018d6d  pop     r15
0x140018d6f  pop     r14
0x140018d71  pop     r13
0x140018d73  pop     r12
0x140018d75  pop     rdi
0x140018d76  pop     rsi
0x140018d77  pop     rbp
0x140018d78  retn
```
