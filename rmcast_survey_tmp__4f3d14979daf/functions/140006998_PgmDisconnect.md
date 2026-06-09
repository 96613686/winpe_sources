# PgmDisconnect

- ea: `0x140006998`
- end: `0x140006cbe`
- name: `PgmDisconnect`
- size: `806`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140007d90`

## callees

- `0x1400054d0`
- `0x140006998`
- `0x140006f5c`
- `0x1400074c8`
- `0x140007524`
- `0x14000dd10`
- `0x140014240`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140006bd1`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140006bd1`
- `ntoskrnl!IofCompleteRequest` at `0x140006c3a`
- `ntoskrnl!IofCompleteRequest` at `0x140006c3a`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140006a39`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140006a39`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006bbe`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006be7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006c94`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006bbe`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006be7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006c94`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400069d4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006a4f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400069d4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006a4f`

## pseudocode

```c
__int64 __fastcall PgmDisconnect(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rsi
  __int64 v6; // rdi
  KIRQL v7; // r12
  signed __int64 v8; // rbx
  unsigned int v9; // ebp
  __int64 v10; // r8
  int v11; // ecx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  const char *v15; // rax
  __int64 v16; // rbx
  __int64 v17; // rdx
  _QWORD *v18; // rcx
  _OWORD v20[4]; // [rsp+40h] [rbp-48h] BYREF
  __int64 Irql; // [rsp+90h] [rbp+8h] BYREF
  KIRQL NewIrql; // [rsp+A0h] [rbp+18h]

  Irql = a1;
  LOBYTE(Irql) = 0;
  v20[0] = 0;
  v5 = 0;
  v6 = *(_QWORD *)(*(_QWORD *)(a3 + 48) + 24LL);
  v7 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  if ( v6 )
  {
    if ( ((*(_DWORD *)(v6 + 16) - 1381188947) & 0xFEFFFFFF) == 0 )
    {
      v5 = *(_QWORD *)(v6 + 24);
      if ( v5 )
      {
        if ( *(_DWORD *)(v5 + 16) == 1380205633 )
        {
          LOBYTE(v8) = 0;
          *((_QWORD *)&v20[0] + 1) = v20;
          *(_QWORD *)&v20[0] = v20;
          IoAcquireCancelSpinLock((PKIRQL)&Irql);
          v9 = 0;
          NewIrql = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v6 + 360));
          if ( *(_QWORD *)(v6 + 48) )
          {
            RemovePendingIrps(v6, v20);
            v11 = *(_DWORD *)(v6 + 32);
            if ( (v11 & 0x2000) == 0 )
            {
              *(_DWORD *)(v6 + 32) = v11 | 0x100;
              CleanupPendingNaks(v6, 0, 1);
            }
          }
          else
          {
            v12 = *(_QWORD *)(v6 + 40);
            if ( v12 )
            {
              if ( (*(_BYTE *)(a3 + 8) & 2) != 0 || (*(_DWORD *)(v6 + 32) & 8) != 0 )
              {
                *(_QWORD *)(v12 + 312) = *(_QWORD *)(v12 + 296);
              }
              else
              {
                LOBYTE(v10) = 1;
                if ( (int)PgmCheckSetCancelRoutine(a2, PgmCancelDisconnectIrp, v10) < 0 )
                {
                  v9 = -1073741536;
                  goto LABEL_24;
                }
                v13 = *(_QWORD *)(a3 + 32);
                if ( v13 && (*(_DWORD *)v13 != -1 || *(_DWORD *)(v13 + 4) != -1) )
                {
                  v14 = *(_QWORD *)v13;
                  v10 = -v14;
                  if ( v14 <= 0 )
                    v14 = -v14;
                  v8 = v14 / 0x2710uLL;
                  if ( v10 < 0 )
                    v8 = -v8;
                  *(_QWORD *)(*(_QWORD *)(v6 + 40) + 312LL) = *(_QWORD *)(*(_QWORD *)(v6 + 40) + 296LL) + v8 / 20;
                }
                *(_QWORD *)(v6 + 96) = a2;
                v9 = 259;
              }
            }
          }
          *(_DWORD *)(v6 + 32) |= 0x2000u;
LABEL_24:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            v15 = "ABORTive";
            if ( (*(_BYTE *)(a3 + 8) & 2) == 0 )
              v15 = "GRACEful";
            WPP_SF_qqqis(
              WPP_GLOBAL_Control->AttachedDevice,
              (unsigned int)"GRACEful",
              v10,
              a2,
              v6,
              v5,
              v8,
              (__int64)v15);
          }
          KeReleaseSpinLock((PKSPIN_LOCK)(v6 + 360), NewIrql);
          IoReleaseCancelSpinLock(Irql);
          KeReleaseSpinLock(&SpinLock, v7);
          while ( 1 )
          {
            v16 = *(_QWORD *)&v20[0];
            if ( *(_OWORD **)&v20[0] == v20 )
              break;
            v17 = **(_QWORD **)&v20[0];
            if ( *(_QWORD *)(**(_QWORD **)&v20[0] + 8LL) != *(_QWORD *)&v20[0]
              || (v18 = *(_QWORD **)(*(_QWORD *)&v20[0] + 8LL), *v18 != *(_QWORD *)&v20[0]) )
            {
              __fastfail(3u);
            }
            *v18 = v17;
            *(_QWORD *)(v17 + 8) = v18;
            PgmCancelCancelRoutine(v16 - 168);
            *(_DWORD *)(v16 - 120) = -1073741536;
            IofCompleteRequest((PIRP)(v16 - 168), 2);
          }
          return v9;
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids, v6, v5);
  KeReleaseSpinLock(&SpinLock, v7);
  return 3221225480LL;
}

```

## disassembly

```asm
0x140006998  mov     rax, rsp
0x14000699b  mov     [rax+10h], rbx
0x14000699f  mov     [rax+8], rcx
0x1400069a3  push    rbp
0x1400069a4  push    rsi
0x1400069a5  push    rdi
0x1400069a6  push    r12
0x1400069a8  push    r13
0x1400069aa  push    r14
0x1400069ac  push    r15
0x1400069ae  sub     rsp, 50h
0x1400069b2  mov     byte ptr [rax+8], 0
0x1400069b6  lea     rcx, SpinLock; SpinLock
0x1400069bd  xorps   xmm0, xmm0
0x1400069c0  mov     r14, r8
0x1400069c3  movups  xmmword ptr [rax-48h], xmm0
0x1400069c7  mov     rax, [r8+30h]
0x1400069cb  mov     r15, rdx
0x1400069ce  xor     esi, esi
0x1400069d0  mov     rdi, [rax+18h]
0x1400069d4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400069db  nop     dword ptr [rax+rax+00h]
0x1400069e0  mov     r12b, al
0x1400069e3  test    rdi, rdi
0x1400069e6  jz      loc_140006C53
0x1400069ec  mov     ecx, [rdi+10h]
0x1400069ef  sub     ecx, 52534553h
0x1400069f5  test    ecx, 0FEFFFFFFh
0x1400069fb  jnz     loc_140006C53
0x140006a01  mov     rsi, [rdi+18h]
0x140006a05  test    rsi, rsi
0x140006a08  jz      loc_140006C53
0x140006a0e  cmp     dword ptr [rsi+10h], 52444441h
0x140006a15  jnz     loc_140006C53
0x140006a1b  lea     rax, [rsp+88h+var_48]
0x140006a20  xor     ebx, ebx
0x140006a22  mov     [rsp+88h+var_40], rax
0x140006a27  lea     rcx, [rsp+88h+Irql]; Irql
0x140006a2f  lea     rax, [rsp+88h+var_48]
0x140006a34  mov     [rsp+88h+var_48], rax
0x140006a39  call    cs:__imp_IoAcquireCancelSpinLock
0x140006a40  nop     dword ptr [rax+rax+00h]
0x140006a45  lea     r13, [rdi+168h]
0x140006a4c  mov     rcx, r13; SpinLock
0x140006a4f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006a56  nop     dword ptr [rax+rax+00h]
0x140006a5b  xor     ebp, ebp
0x140006a5d  mov     [rsp+88h+NewIrql], al
0x140006a64  cmp     [rdi+30h], rbx
0x140006a68  jz      short loc_140006A9E
0x140006a6a  lea     rdx, [rsp+88h+var_48]
0x140006a6f  mov     rcx, rdi
0x140006a72  call    RemovePendingIrps
0x140006a77  mov     ecx, [rdi+20h]
0x140006a7a  bt      ecx, 0Dh
0x140006a7e  jb      loc_140006B5E
0x140006a84  bts     ecx, 8
0x140006a88  lea     r8d, [rbx+1]
0x140006a8c  mov     [rdi+20h], ecx
0x140006a8f  xor     edx, edx
0x140006a91  mov     rcx, rdi
0x140006a94  call    CleanupPendingNaks
0x140006a99  jmp     loc_140006B5E
0x140006a9e  mov     rcx, [rdi+28h]
0x140006aa2  test    rcx, rcx
0x140006aa5  jz      loc_140006B5E
0x140006aab  test    byte ptr [r14+8], 2
0x140006ab0  jnz     loc_140006B50
0x140006ab6  mov     eax, [rdi+20h]
0x140006ab9  test    al, 8
0x140006abb  jnz     loc_140006B50
0x140006ac1  mov     r8b, 1
0x140006ac4  lea     rdx, PgmCancelDisconnectIrp
0x140006acb  mov     rcx, r15
0x140006ace  call    PgmCheckSetCancelRoutine
0x140006ad3  test    eax, eax
0x140006ad5  js      short loc_140006B49
0x140006ad7  mov     rcx, [r14+20h]
0x140006adb  test    rcx, rcx
0x140006ade  jz      short loc_140006B3E
0x140006ae0  cmp     dword ptr [rcx], 0FFFFFFFFh
0x140006ae3  jnz     short loc_140006AEB
0x140006ae5  cmp     dword ptr [rcx+4], 0FFFFFFFFh
0x140006ae9  jz      short loc_140006B3E
0x140006aeb  mov     rcx, [rcx]
0x140006aee  mov     rax, cs:qword_14001F2A0
0x140006af5  mov     r8, rcx
0x140006af8  neg     r8
0x140006afb  cmovns  rcx, r8
0x140006aff  mul     rcx
0x140006b02  mov     rbx, rdx
0x140006b05  shr     rbx, 0Dh
0x140006b09  test    r8, r8
0x140006b0c  jns     short loc_140006B11
0x140006b0e  neg     rbx
0x140006b11  mov     rcx, [rdi+28h]
0x140006b15  mov     rax, 6666666666666667h
0x140006b1f  imul    rbx
0x140006b22  sar     rdx, 3
0x140006b26  mov     rax, rdx
0x140006b29  shr     rax, 3Fh
0x140006b2d  add     rdx, rax
0x140006b30  add     rdx, [rcx+128h]
0x140006b37  mov     [rcx+138h], rdx
0x140006b3e  mov     [rdi+60h], r15
0x140006b42  mov     ebp, 103h
0x140006b47  jmp     short loc_140006B5E
0x140006b49  mov     ebp, 0C0000120h
0x140006b4e  jmp     short loc_140006B63
0x140006b50  mov     rax, [rcx+128h]
0x140006b57  mov     [rcx+138h], rax
0x140006b5e  bts     dword ptr [rdi+20h], 0Dh
0x140006b63  mov     rcx, cs:WPP_GLOBAL_Control
0x140006b6a  lea     rax, WPP_GLOBAL_Control
0x140006b71  cmp     rcx, rax
0x140006b74  jz      short loc_140006BB4
0x140006b76  mov     eax, [rcx+2Ch]
0x140006b79  test    al, 4
0x140006b7b  jz      short loc_140006BB4
0x140006b7d  test    byte ptr [r14+8], 2
0x140006b82  lea     rdx, aGraceful; "GRACEful"
0x140006b89  mov     rcx, [rcx+18h]
0x140006b8d  lea     rax, aAbortive; "ABORTive"
0x140006b94  cmovz   rax, rdx
0x140006b98  mov     r9, r15
0x140006b9b  mov     [rsp+88h+var_50], rax
0x140006ba0  mov     [rsp+88h+var_58], rbx
0x140006ba5  mov     [rsp+88h+var_60], rsi
0x140006baa  mov     [rsp+88h+var_68], rdi
0x140006baf  call    WPP_SF_qqqis
0x140006bb4  mov     dl, [rsp+88h+NewIrql]; NewIrql
0x140006bbb  mov     rcx, r13; SpinLock
0x140006bbe  call    cs:__imp_KeReleaseSpinLock
0x140006bc5  nop     dword ptr [rax+rax+00h]
0x140006bca  mov     cl, byte ptr [rsp+88h+Irql]; Irql
0x140006bd1  call    cs:__imp_IoReleaseCancelSpinLock
0x140006bd8  nop     dword ptr [rax+rax+00h]
0x140006bdd  mov     dl, r12b; NewIrql
0x140006be0  lea     rcx, SpinLock; SpinLock
0x140006be7  call    cs:__imp_KeReleaseSpinLock
0x140006bee  nop     dword ptr [rax+rax+00h]
0x140006bf3  mov     rbx, [rsp+88h+var_48]
0x140006bf8  lea     rax, [rsp+88h+var_48]
0x140006bfd  cmp     rbx, rax
0x140006c00  jz      short loc_140006C4F
0x140006c02  mov     rdx, [rbx]
0x140006c05  mov     rax, rbx
0x140006c08  cmp     [rdx+8], rbx
0x140006c0c  jnz     short loc_140006C48
0x140006c0e  mov     rcx, [rbx+8]
0x140006c12  cmp     [rcx], rax
0x140006c15  jnz     short loc_140006C48
0x140006c17  mov     [rcx], rdx
0x140006c1a  mov     [rdx+8], rcx
0x140006c1e  lea     rcx, [rbx-0A8h]
0x140006c25  call    PgmCancelCancelRoutine
0x140006c2a  mov     dl, 2; PriorityBoost
0x140006c2c  mov     dword ptr [rbx-78h], 0C0000120h
0x140006c33  lea     rcx, [rbx-0A8h]; Irp
0x140006c3a  call    cs:__imp_IofCompleteRequest
0x140006c41  nop     dword ptr [rax+rax+00h]
0x140006c46  jmp     short loc_140006BF3
0x140006c48  mov     ecx, 3
0x140006c4d  int     29h; Win8: RtlFailFast(ecx)
0x140006c4f  mov     eax, ebp
0x140006c51  jmp     short loc_140006CA5
0x140006c53  mov     rcx, cs:WPP_GLOBAL_Control
0x140006c5a  lea     rax, WPP_GLOBAL_Control
0x140006c61  cmp     rcx, rax
0x140006c64  jz      short loc_140006C8A
0x140006c66  mov     eax, [rcx+2Ch]
0x140006c69  test    al, 2
0x140006c6b  jz      short loc_140006C8A
0x140006c6d  mov     rcx, [rcx+18h]
0x140006c71  lea     r8, WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids
0x140006c78  mov     edx, 1Eh
0x140006c7d  mov     [rsp+88h+var_68], rsi
0x140006c82  mov     r9, rdi
0x140006c85  call    WPP_SF_qq
0x140006c8a  mov     dl, r12b; NewIrql
0x140006c8d  lea     rcx, SpinLock; SpinLock
0x140006c94  call    cs:__imp_KeReleaseSpinLock
0x140006c9b  nop     dword ptr [rax+rax+00h]
0x140006ca0  mov     eax, 0C0000008h
0x140006ca5  mov     rbx, [rsp+88h+arg_8]
0x140006cad  add     rsp, 50h
0x140006cb1  pop     r15
0x140006cb3  pop     r14
0x140006cb5  pop     r13
0x140006cb7  pop     r12
0x140006cb9  pop     rdi
0x140006cba  pop     rsi
0x140006cbb  pop     rbp
0x140006cbc  retn
```
