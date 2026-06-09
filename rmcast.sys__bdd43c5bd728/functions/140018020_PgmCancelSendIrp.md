# PgmCancelSendIrp

- ea: `0x140018020`
- end: `0x140018262`
- name: `PgmCancelSendIrp`
- size: `578`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400051c8`
- `0x1400052e4`
- `0x140005524`
- `0x1400067f4`
- `0x140007f1c`
- `0x140017c80`
- `0x140018020`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400180e5`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400181c0`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140018203`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400180e5`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400181c0`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140018203`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140018152`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140018152`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400180d6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400181b1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400180d6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400181b1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018063`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018063`

## pseudocode

```c
__int64 __fastcall PgmCancelSendIrp(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  KIRQL v4; // al
  __int64 v5; // r8
  KIRQL v6; // bp
  _QWORD *v7; // rcx
  _QWORD *v8; // rax
  unsigned int v9; // ebp
  _QWORD *v10; // rsi
  __int64 v11; // rax
  IRP *v12; // rcx
  __int64 result; // rax
  __int64 v14; // rax
  PVOID Entry[7]; // [rsp+30h] [rbp-38h] BYREF

  v3 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 184) + 48LL) + 24LL);
  *(_OWORD *)Entry = 0;
  if ( v3 && *(_DWORD *)(v3 + 16) == 1397966163 )
  {
    v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 360));
    v5 = *(_QWORD *)(v3 + 40);
    v6 = v4;
    v7 = (_QWORD *)(v5 + 248);
    while ( 1 )
    {
      v7 = (_QWORD *)*v7;
      if ( v7 == (_QWORD *)(v5 + 248) )
        break;
      if ( v7[3] == a2 )
      {
LABEL_10:
        Entry[1] = Entry;
        Entry[0] = Entry;
        PgmCancelAllSends(v3, Entry, a2);
        KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 360), v6);
        IoReleaseCancelSpinLock(*(_BYTE *)(a2 + 69));
        v9 = 0;
        while ( 1 )
        {
          v10 = Entry[0];
          if ( Entry[0] == Entry )
            break;
          if ( *((PVOID **)Entry[0] + 1) != Entry
            || (v11 = *(_QWORD *)Entry[0], *(PVOID *)(*(_QWORD *)Entry[0] + 8LL) != Entry[0]) )
          {
            __fastfail(3u);
          }
          Entry[0] = *(PVOID *)Entry[0];
          *(_QWORD *)(v11 + 8) = Entry;
          v12 = (IRP *)v10[4];
          if ( v12 )
          {
            ++v9;
            PgmIoComplete(v12, -1073741536, 0);
          }
          PgmDereferenceSessionCommon(v3);
          ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(v3 + 40) + 576LL), v10);
        }
        result = (__int64)&WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          result = HIDWORD(WPP_GLOBAL_Control->Timer);
          if ( (result & 0x20) != 0 )
            return WPP_SF_dq(
                     WPP_GLOBAL_Control->AttachedDevice,
                     100,
                     WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids,
                     v9,
                     a2);
        }
        return result;
      }
    }
    v8 = (_QWORD *)(v5 + 232);
    while ( 1 )
    {
      v8 = (_QWORD *)*v8;
      if ( v8 == (_QWORD *)(v5 + 232) )
        break;
      if ( v8[3] == a2 )
        goto LABEL_10;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 360), v6);
    IoReleaseCancelSpinLock(*(_BYTE *)(a2 + 69));
    result = (__int64)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      result = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (result & 0x20) != 0 )
        return WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 99, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids, a2);
    }
  }
  else
  {
    IoReleaseCancelSpinLock(*(_BYTE *)(a2 + 69));
    result = (__int64)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      result = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (result & 2) != 0 )
      {
        if ( v3 )
          v14 = *(_QWORD *)(v3 + 24);
        else
          v14 = 0;
        return WPP_SF_qqq(
                 WPP_GLOBAL_Control->AttachedDevice,
                 98,
                 WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids,
                 a2,
                 v3,
                 v14);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140018020  push    rbx
0x140018022  push    rbp
0x140018023  push    rsi
0x140018024  push    rdi
0x140018025  sub     rsp, 48h
0x140018029  mov     rax, [rdx+0B8h]
0x140018030  xorps   xmm0, xmm0
0x140018033  mov     rdi, rdx
0x140018036  mov     rcx, [rax+30h]
0x14001803a  mov     rbx, [rcx+18h]
0x14001803e  movups  xmmword ptr [rsp+68h+Entry], xmm0
0x140018043  test    rbx, rbx
0x140018046  jz      loc_140018200
0x14001804c  cmp     dword ptr [rbx+10h], 53534553h
0x140018053  jnz     loc_140018200
0x140018059  lea     rsi, [rbx+168h]
0x140018060  mov     rcx, rsi; SpinLock
0x140018063  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001806a  nop     dword ptr [rax+rax+00h]
0x14001806f  mov     r8, [rbx+28h]
0x140018073  mov     bpl, al
0x140018076  lea     rdx, [r8+0F8h]
0x14001807d  mov     rcx, rdx
0x140018080  mov     rcx, [rcx]
0x140018083  cmp     rcx, rdx
0x140018086  jz      short loc_140018090
0x140018088  cmp     [rcx+18h], rdi
0x14001808c  jnz     short loc_140018080
0x14001808e  jmp     short loc_1400180AC
0x140018090  lea     rdx, [r8+0E8h]
0x140018097  mov     rax, rdx
0x14001809a  mov     rax, [rax]
0x14001809d  cmp     rax, rdx
0x1400180a0  jz      loc_1400181AB
0x1400180a6  cmp     [rax+18h], rdi
0x1400180aa  jnz     short loc_14001809A
0x1400180ac  lea     rax, [rsp+68h+Entry]
0x1400180b1  mov     r8, rdi
0x1400180b4  mov     [rsp+68h+Entry+8], rax
0x1400180b9  lea     rdx, [rsp+68h+Entry]
0x1400180be  lea     rax, [rsp+68h+Entry]
0x1400180c3  mov     rcx, rbx
0x1400180c6  mov     [rsp+68h+Entry], rax
0x1400180cb  call    PgmCancelAllSends
0x1400180d0  mov     dl, bpl; NewIrql
0x1400180d3  mov     rcx, rsi; SpinLock
0x1400180d6  call    cs:__imp_KeReleaseSpinLock
0x1400180dd  nop     dword ptr [rax+rax+00h]
0x1400180e2  mov     cl, [rdi+45h]; Irql
0x1400180e5  call    cs:__imp_IoReleaseCancelSpinLock
0x1400180ec  nop     dword ptr [rax+rax+00h]
0x1400180f1  xor     ebp, ebp
0x1400180f3  mov     rsi, [rsp+68h+Entry]
0x1400180f8  lea     rax, [rsp+68h+Entry]
0x1400180fd  cmp     rsi, rax
0x140018100  jz      short loc_140018167
0x140018102  lea     rax, [rsp+68h+Entry]
0x140018107  cmp     [rsi+8], rax
0x14001810b  jnz     short loc_140018160
0x14001810d  mov     rax, [rsi]
0x140018110  cmp     [rax+8], rsi
0x140018114  jnz     short loc_140018160
0x140018116  lea     rcx, [rsp+68h+Entry]
0x14001811b  mov     [rsp+68h+Entry], rax
0x140018120  mov     [rax+8], rcx
0x140018124  mov     rcx, [rsi+20h]; Irp
0x140018128  test    rcx, rcx
0x14001812b  jz      short loc_14001813C
0x14001812d  inc     ebp
0x14001812f  xor     r8d, r8d
0x140018132  mov     edx, 0C0000120h
0x140018137  call    PgmIoComplete
0x14001813c  mov     rcx, rbx
0x14001813f  call    PgmDereferenceSessionCommon
0x140018144  mov     rcx, [rbx+28h]
0x140018148  mov     rdx, rsi; Entry
0x14001814b  add     rcx, 240h; Lookaside
0x140018152  call    cs:__imp_ExFreeToNPagedLookasideList
0x140018159  nop     dword ptr [rax+rax+00h]
0x14001815e  jmp     short loc_1400180F3
0x140018160  mov     ecx, 3
0x140018165  int     29h; Win8: RtlFailFast(ecx)
0x140018167  mov     rcx, cs:WPP_GLOBAL_Control
0x14001816e  lea     rax, WPP_GLOBAL_Control
0x140018175  cmp     rcx, rax
0x140018178  jz      loc_140018258
0x14001817e  mov     eax, [rcx+2Ch]
0x140018181  test    al, 20h
0x140018183  jz      loc_140018258
0x140018189  mov     rcx, [rcx+18h]
0x14001818d  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x140018194  mov     edx, 64h ; 'd'
0x140018199  mov     [rsp+68h+var_48], rdi
0x14001819e  mov     r9d, ebp
0x1400181a1  call    WPP_SF_dq
0x1400181a6  jmp     loc_140018258
0x1400181ab  mov     dl, bpl; NewIrql
0x1400181ae  mov     rcx, rsi; SpinLock
0x1400181b1  call    cs:__imp_KeReleaseSpinLock
0x1400181b8  nop     dword ptr [rax+rax+00h]
0x1400181bd  mov     cl, [rdi+45h]; Irql
0x1400181c0  call    cs:__imp_IoReleaseCancelSpinLock
0x1400181c7  nop     dword ptr [rax+rax+00h]
0x1400181cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400181d3  lea     rax, WPP_GLOBAL_Control
0x1400181da  cmp     rcx, rax
0x1400181dd  jz      short loc_140018258
0x1400181df  mov     eax, [rcx+2Ch]
0x1400181e2  test    al, 20h
0x1400181e4  jz      short loc_140018258
0x1400181e6  mov     rcx, [rcx+18h]
0x1400181ea  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x1400181f1  mov     edx, 63h ; 'c'
0x1400181f6  mov     r9, rdi
0x1400181f9  call    WPP_SF_q
0x1400181fe  jmp     short loc_140018258
0x140018200  mov     cl, [rdx+45h]; Irql
0x140018203  call    cs:__imp_IoReleaseCancelSpinLock
0x14001820a  nop     dword ptr [rax+rax+00h]
0x14001820f  mov     rcx, cs:WPP_GLOBAL_Control
0x140018216  lea     rax, WPP_GLOBAL_Control
0x14001821d  cmp     rcx, rax
0x140018220  jz      short loc_140018258
0x140018222  mov     eax, [rcx+2Ch]
0x140018225  test    al, 2
0x140018227  jz      short loc_140018258
0x140018229  test    rbx, rbx
0x14001822c  jz      short loc_140018234
0x14001822e  mov     rax, [rbx+18h]
0x140018232  jmp     short loc_140018236
0x140018234  xor     eax, eax
0x140018236  mov     rcx, [rcx+18h]
0x14001823a  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x140018241  mov     [rsp+68h+var_40], rax
0x140018246  mov     edx, 62h ; 'b'
0x14001824b  mov     r9, rdi
0x14001824e  mov     [rsp+68h+var_48], rbx
0x140018253  call    WPP_SF_qqq
0x140018258  add     rsp, 48h
0x14001825c  pop     rdi
0x14001825d  pop     rsi
0x14001825e  pop     rbp
0x14001825f  pop     rbx
0x140018260  retn
```
