# Smb2LeaseProcessBreakAndReleaseSpinLock

- ea: `0x140015af8`
- end: `0x140015ff0`
- name: `Smb2LeaseProcessBreakAndReleaseSpinLock`
- size: `1272`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x140015a10`

## callees

- `0x14000ae60`
- `0x14000e140`
- `0x140012790`
- `0x140012ca0`
- `0x140015af8`
- `0x140015ff8`
- `0x140016180`
- `0x1400161fc`
- `0x140016368`
- `0x14001ffc4`
- `0x1400222ec`
- `0x1400229ac`
- `0x14002e90c`
- `0x14002edbc`
- `0x140038980`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140015ebe`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140015ebe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015b7a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015cb1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015ce8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003ca11`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015b7a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015cb1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015ce8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003ca11`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015b5b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015bc7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015cd9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015da5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c9e3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015b5b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015bc7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015cd9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015da5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c9e3`
- `srvnet!SrvNetSendData` at `0x140015dc7`
- `srvnet!SrvNetSendData` at `0x140015dc7`

## pseudocode

```c
__int64 __fastcall Smb2LeaseProcessBreakAndReleaseSpinLock(__int64 a1, __int64 a2, KIRQL a3)
{
  int v4; // ebp
  __int64 result; // rax
  KIRQL v7; // al
  __int16 *v8; // rsi
  __int64 v9; // rcx
  _DWORD *v10; // rdi
  int v11; // edx
  int v12; // r8d
  __int16 v13; // ax
  int v14; // ecx
  KIRQL v15; // bp
  _QWORD *i; // rcx
  __int64 (__fastcall *v17)(); // rdx
  KIRQL v18; // bp
  void *v19; // rdi
  __int64 v20; // rsi
  _QWORD *v21; // rsi
  int v22; // edx

  v4 = a2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x1Eu)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids, a1);
  }
  if ( *(_BYTE *)(a1 + 128) && v4 == 2 )
  {
    *(_DWORD *)(a1 + 140) &= ~2u;
    LOBYTE(a2) = a3;
    return Smb2LeaseProcessPendingLeaseOperationsAndReleaseSpinLock(a1, a2);
  }
  if ( *(_QWORD *)(a1 + 256) )
  {
LABEL_6:
    v8 = (__int16 *)(a1 + 168);
    *(_DWORD *)(a1 + 140) &= ~v4 & 0xFFFFFFE7;
    if ( v4 == 2 )
    {
      *(_DWORD *)(a1 + 104) = 32;
    }
    else
    {
      *(_DWORD *)(a1 + 140) &= ~2u;
      ++*v8;
      *(_BYTE *)(a1 + 137) = 1;
    }
    *(_DWORD *)(a1 + 144) |= 4u;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), a3);
    v9 = *(_QWORD *)(*(_QWORD *)(a1 + 256) + 8LL);
    if ( (*(_BYTE *)(v9 + 10) & 5) != 0 )
      v10 = *(_DWORD **)(v9 + 24);
    else
      v10 = MmMapLockedPagesSpecifyCache((PMDL)v9, 0, MmCached, 0, 0, 0x40000010u);
    memset(v10, 0, 0x80u);
    *((_WORD *)v10 + 6) = 18;
    *((_QWORD *)v10 + 3) = -1;
    v10[4] = 1;
    *((_WORD *)v10 + 32) = 44;
    *v10 = 1112364030;
    *((_WORD *)v10 + 2) = 64;
    if ( *(_BYTE *)(a1 + 135) )
      v13 = *v8;
    else
      v13 = 0;
    *((_WORD *)v10 + 33) = v13;
    v10[17] = 0;
    *(_OWORD *)(v10 + 18) = *(_OWORD *)(a1 + 80);
    v10[22] = *(_DWORD *)(a1 + 120);
    if ( v4 == 2 )
    {
      v12 = *(_DWORD *)(*(_QWORD *)(a1 + 280) + 8LL);
      *(_DWORD *)(a1 + 124) = v12;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qDD(
          WPP_GLOBAL_Control->AttachedDevice,
          25,
          WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids,
          a1,
          *(_DWORD *)(a1 + 120),
          v12);
      }
      v10[23] = *(_DWORD *)(a1 + 124);
      v14 = *(_DWORD *)(*(_QWORD *)(a1 + 280) + 12LL);
      if ( (v14 & 1) != 0 )
        v10[17] |= 1u;
      *(_QWORD *)(a1 + 280) = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids, a1);
      }
      v14 = 768;
      if ( *(_WORD *)(*(_QWORD *)(a1 + 368) + 152LL) >= 0x300u )
        v10[2] = -1073741528;
      v10[23] = 0;
    }
    *((_QWORD *)v10 + 12) = 0;
    v10[26] = 0;
    if ( (Microsoft_Windows_SMBServerEnableBits & 1) != 0 )
      McTemplateK0xqqxxhhqqqqqqqjjjjj_EtwWriteTransfer(
        v14,
        v11,
        v12,
        *((_QWORD *)v10 + 5),
        v10[8],
        v10[9],
        *((_QWORD *)v10 + 3));
    v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
    for ( i = *(_QWORD **)(a1 + 152); i != (_QWORD *)(a1 + 152); i = (_QWORD *)*i )
    {
      v21 = i - 52;
      v22 = *((_DWORD *)i - 101);
      if ( v22 != 221 && v22 != 227 && !v21[18] && *((_BYTE *)v21 + 237) && !*((_BYTE *)v21 + 242) )
      {
        Smb2ReferenceFile(i - 52);
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), v15);
        Smb2CloseFile(v21);
        Smb2DereferenceFile(v21);
        _InterlockedAdd((volatile signed __int32 *)(Srv2Statistics + 140), 1u);
        v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
        i = (_QWORD *)(a1 + 152);
      }
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), v15);
    v18 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
    *(_BYTE *)(a1 + 131) = v10[17] & 1;
    *(_QWORD *)(*(_QWORD *)(a1 + 256) + 24LL) = a1;
    **(_DWORD **)(a1 + 256) = 108;
    if ( *(_BYTE *)(a1 + 137) )
    {
      v17 = Smb2LeaseSendComplete;
      *(_QWORD *)(*(_QWORD *)(a1 + 256) + 16LL) = Smb2LeaseSendComplete;
    }
    else if ( *(_DWORD *)(a1 + 120) == 1 )
    {
      *(_QWORD *)(*(_QWORD *)(a1 + 256) + 16LL) = Smb2LeaseSendCompleteAndResetLeaseState;
    }
    else
    {
      Smb2QueueLeaseBreak(a1);
      v17 = Smb2LeaseSendComplete;
      *(_QWORD *)(*(_QWORD *)(a1 + 256) + 16LL) = Smb2LeaseSendComplete;
    }
    v19 = *(void **)(a1 + 360);
    *(_QWORD *)(a1 + 360) = 0;
    if ( !*(_BYTE *)(a1 + 137) )
    {
      v20 = 0;
      if ( (unsigned int)(*(_DWORD *)(a1 + 12) - 224) <= 1 )
      {
        if ( !*(_DWORD *)(a1 + 176) )
          goto LABEL_27;
      }
      else if ( *(_BYTE *)(a1 + 128) )
      {
LABEL_27:
        *(_DWORD *)(a1 + 144) &= ~4u;
        LOBYTE(v17) = v18;
        if ( v20 )
        {
          *(_DWORD *)(a1 + 144) |= 0x10u;
          KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), v18);
          Smb2ReferenceLease(a1);
          result = SrvNetSendData(*(_QWORD *)(v20 + 480), *(_QWORD *)(a1 + 256));
        }
        else
        {
          result = Smb2LeaseProcessBreakNoConnectionsAndReleaseSpinLock(a1, v17);
        }
        if ( v19 )
          return Srv2DereferenceConnection(v19);
        return result;
      }
    }
    v20 = Smb2LeaseSelectConnection(a1, v19);
    goto LABEL_27;
  }
  *(_DWORD *)(a1 + 144) |= 8u;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), a3);
  result = Smb2LeaseAllocateBufferForLeaseBreakProcessing(a1);
  if ( !(_DWORD)result )
  {
    v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
    *(_DWORD *)(a1 + 144) &= ~8u;
    a3 = v7;
    goto LABEL_6;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x1Eu)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    return WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids, a1);
  }
  return result;
}

```

## disassembly

```asm
0x140015af8  push    rbx
0x140015afa  push    rbp
0x140015afb  push    rsi
0x140015afc  push    rdi
0x140015afd  push    r12
0x140015aff  push    r13
0x140015b01  push    r14
0x140015b03  push    r15
0x140015b05  sub     rsp, 0B8h
0x140015b0c  mov     dil, r8b
0x140015b0f  mov     ebp, edx
0x140015b11  mov     rbx, rcx
0x140015b14  mov     rcx, cs:WPP_GLOBAL_Control
0x140015b1b  lea     r13, WPP_GLOBAL_Control
0x140015b22  mov     r14d, 2
0x140015b28  cmp     rcx, r13
0x140015b2b  jnz     loc_140015E20
0x140015b31  xor     r12d, r12d
0x140015b34  cmp     [rbx+80h], r12b
0x140015b3b  jnz     loc_140015ED2
0x140015b41  lea     r15, [rbx+60h]
0x140015b45  cmp     [rbx+100h], r12
0x140015b4c  jnz     short loc_140015B90
0x140015b4e  or      dword ptr [rbx+90h], 8
0x140015b55  mov     dl, dil; NewIrql
0x140015b58  mov     rcx, r15; SpinLock
0x140015b5b  call    cs:__imp_KeReleaseSpinLock
0x140015b62  nop     dword ptr [rax+rax+00h]
0x140015b67  mov     rcx, rbx
0x140015b6a  call    Smb2LeaseAllocateBufferForLeaseBreakProcessing
0x140015b6f  test    eax, eax
0x140015b71  jnz     loc_140015EF2
0x140015b77  mov     rcx, r15; SpinLock
0x140015b7a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015b81  nop     dword ptr [rax+rax+00h]
0x140015b86  and     dword ptr [rbx+90h], 0FFFFFFF7h
0x140015b8d  mov     dil, al
0x140015b90  mov     eax, ebp
0x140015b92  lea     rsi, [rbx+0A8h]
0x140015b99  not     eax
0x140015b9b  mov     r13d, 1
0x140015ba1  and     eax, 0FFFFFFE7h
0x140015ba4  and     [rbx+8Ch], eax
0x140015baa  cmp     ebp, r14d
0x140015bad  jnz     loc_140015F34
0x140015bb3  mov     dword ptr [rbx+68h], 20h ; ' '
0x140015bba  or      dword ptr [rbx+90h], 4
0x140015bc1  mov     dl, dil; NewIrql
0x140015bc4  mov     rcx, r15; SpinLock
0x140015bc7  call    cs:__imp_KeReleaseSpinLock
0x140015bce  nop     dword ptr [rax+rax+00h]
0x140015bd3  mov     rax, [rbx+100h]
0x140015bda  mov     rcx, [rax+8]; MemoryDescriptorList
0x140015bde  test    byte ptr [rcx+0Ah], 5
0x140015be2  jz      loc_140015EA9
0x140015be8  mov     rdi, [rcx+18h]
0x140015bec  xor     edx, edx; Val
0x140015bee  mov     r8d, 80h; Size
0x140015bf4  mov     rcx, rdi; void *
0x140015bf7  call    memset
0x140015bfc  mov     word ptr [rdi+0Ch], 12h
0x140015c02  mov     qword ptr [rdi+18h], 0FFFFFFFFFFFFFFFFh
0x140015c0a  mov     [rdi+10h], r13d
0x140015c0e  mov     word ptr [rdi+40h], 2Ch ; ','
0x140015c14  mov     dword ptr [rdi], 424D53FEh
0x140015c1a  mov     word ptr [rdi+4], 40h ; '@'
0x140015c20  cmp     [rbx+87h], r12b
0x140015c27  jz      loc_140015F4B
0x140015c2d  movzx   eax, word ptr [rsi]
0x140015c30  mov     [rdi+42h], ax
0x140015c34  lea     rsi, [rdi+48h]
0x140015c38  mov     [rdi+44h], r12d
0x140015c3c  movups  xmm0, xmmword ptr [rbx+50h]
0x140015c40  movdqu  xmmword ptr [rsi], xmm0
0x140015c44  mov     eax, [rbx+78h]
0x140015c47  mov     [rdi+58h], eax
0x140015c4a  cmp     ebp, r14d
0x140015c4d  jnz     loc_140015F53
0x140015c53  mov     rax, [rbx+118h]
0x140015c5a  mov     r8d, [rax+8]
0x140015c5e  mov     [rbx+7Ch], r8d
0x140015c62  mov     rcx, cs:WPP_GLOBAL_Control
0x140015c69  lea     rax, WPP_GLOBAL_Control
0x140015c70  cmp     rcx, rax
0x140015c73  jnz     loc_140015E52
0x140015c79  mov     eax, [rbx+7Ch]
0x140015c7c  mov     [rdi+5Ch], eax
0x140015c7f  mov     rax, [rbx+118h]
0x140015c86  mov     ecx, [rax+0Ch]
0x140015c89  test    r13b, cl
0x140015c8c  jz      short loc_140015C92
0x140015c8e  or      [rdi+44h], r13d
0x140015c92  mov     [rbx+118h], r12
0x140015c99  mov     [rdi+60h], r12
0x140015c9d  mov     [rdi+68h], r12d
0x140015ca1  test    cs:Microsoft_Windows_SMBServerEnableBits, r13b
0x140015ca8  jnz     loc_14003C94D
0x140015cae  mov     rcx, r15; SpinLock
0x140015cb1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015cb8  nop     dword ptr [rax+rax+00h]
0x140015cbd  lea     r14, [rbx+98h]
0x140015cc4  mov     bpl, al
0x140015cc7  mov     rcx, [r14]
0x140015cca  cmp     rcx, r14
0x140015ccd  jnz     loc_140015DF1
0x140015cd3  mov     dl, bpl; NewIrql
0x140015cd6  mov     rcx, r15; SpinLock
0x140015cd9  call    cs:__imp_KeReleaseSpinLock
0x140015ce0  nop     dword ptr [rax+rax+00h]
0x140015ce5  mov     rcx, r15; SpinLock
0x140015ce8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015cef  nop     dword ptr [rax+rax+00h]
0x140015cf4  mov     cl, [rdi+44h]
0x140015cf7  mov     bpl, al
0x140015cfa  and     cl, r13b
0x140015cfd  mov     [rbx+83h], cl
0x140015d03  mov     rcx, [rbx+100h]
0x140015d0a  mov     [rcx+18h], rbx
0x140015d0e  mov     rcx, [rbx+100h]
0x140015d15  mov     dword ptr [rcx], 6Ch ; 'l'
0x140015d1b  cmp     [rbx+89h], r12b
0x140015d22  jnz     loc_140015E92
0x140015d28  cmp     [rbx+78h], r13d
0x140015d2c  jz      loc_140015F9F
0x140015d32  mov     rcx, rbx
0x140015d35  call    Smb2QueueLeaseBreak
0x140015d3a  mov     rax, [rbx+100h]
0x140015d41  lea     rdx, Smb2LeaseSendComplete
0x140015d48  mov     [rax+10h], rdx
0x140015d4c  mov     rdi, [rbx+168h]
0x140015d53  mov     [rbx+168h], r12
0x140015d5a  cmp     [rbx+89h], r12b
0x140015d61  jnz     loc_140015FC3
0x140015d67  mov     eax, [rbx+0Ch]
0x140015d6a  mov     rsi, r12
0x140015d6d  sub     eax, 0E0h
0x140015d72  cmp     eax, r13d
0x140015d75  jbe     loc_140015FB6
0x140015d7b  cmp     [rbx+80h], r12b
0x140015d82  jz      loc_140015FC3
0x140015d88  and     dword ptr [rbx+90h], 0FFFFFFFBh
0x140015d8f  mov     dl, bpl; NewIrql
0x140015d92  test    rsi, rsi
0x140015d95  jz      loc_140015FD6
0x140015d9b  or      dword ptr [rbx+90h], 10h
0x140015da2  mov     rcx, r15; SpinLock
0x140015da5  call    cs:__imp_KeReleaseSpinLock
0x140015dac  nop     dword ptr [rax+rax+00h]
0x140015db1  mov     rcx, rbx
0x140015db4  call    Smb2ReferenceLease
0x140015db9  mov     rdx, [rbx+100h]
0x140015dc0  mov     rcx, [rsi+1E0h]
0x140015dc7  call    cs:__imp_SrvNetSendData
0x140015dce  nop     dword ptr [rax+rax+00h]
0x140015dd3  test    rdi, rdi
0x140015dd6  jnz     loc_140015FE3
0x140015ddc  add     rsp, 0B8h
0x140015de3  pop     r15
0x140015de5  pop     r14
0x140015de7  pop     r13
0x140015de9  pop     r12
0x140015deb  pop     rdi
0x140015dec  pop     rsi
0x140015ded  pop     rbp
0x140015dee  pop     rbx
0x140015def  retn
0x140015df1  lea     rsi, [rcx-1A0h]
0x140015df8  mov     edx, [rsi+0Ch]
0x140015dfb  cmp     edx, 0DDh
0x140015e01  jz      short loc_140015E18
0x140015e03  cmp     edx, 0E3h
0x140015e09  jz      short loc_140015E18
0x140015e0b  cmp     [rsi+90h], r12
0x140015e12  jz      loc_14003C9BB
0x140015e18  mov     rcx, [rcx]
0x140015e1b  jmp     loc_140015CCA
0x140015e20  bt      dword ptr [rcx+2Ch], 1Eh
0x140015e25  jnb     loc_140015B31
0x140015e2b  cmp     [rcx+29h], r14b
0x140015e2f  jb      loc_140015B31
0x140015e35  mov     rcx, [rcx+18h]
0x140015e39  lea     r8, WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids
0x140015e40  mov     edx, 17h
0x140015e45  mov     r9, rbx
0x140015e48  call    WPP_SF_q
0x140015e4d  jmp     loc_140015B31
0x140015e52  test    dword ptr [rcx+2Ch], 40000000h
0x140015e59  jz      loc_140015C79
0x140015e5f  cmp     [rcx+29h], r13b
0x140015e63  jb      loc_140015C79
0x140015e69  mov     eax, [rbx+78h]
0x140015e6c  mov     edx, 19h
0x140015e71  mov     rcx, [rcx+18h]
0x140015e75  mov     r9, rbx
0x140015e78  mov     [rsp+0F8h+Priority], r8d
0x140015e7d  lea     r8, WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids
0x140015e84  mov     [rsp+0F8h+BugCheckOnFailure], eax
0x140015e88  call    WPP_SF_qDD
0x140015e8d  jmp     loc_140015C79
0x140015e92  mov     rcx, [rbx+100h]
0x140015e99  lea     rdx, Smb2LeaseSendComplete
0x140015ea0  mov     [rcx+10h], rdx
0x140015ea4  jmp     loc_140015D4C
0x140015ea9  mov     [rsp+0F8h+Priority], 40000010h; Priority
0x140015eb1  xor     r9d, r9d; RequestedAddress
0x140015eb4  mov     r8d, r13d; CacheType
0x140015eb7  mov     [rsp+0F8h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x140015ebc  xor     edx, edx; AccessMode
0x140015ebe  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140015ec5  nop     dword ptr [rax+rax+00h]
0x140015eca  mov     rdi, rax
0x140015ecd  jmp     loc_140015BEC
0x140015ed2  cmp     ebp, r14d
0x140015ed5  jnz     loc_140015B41
0x140015edb  and     dword ptr [rbx+8Ch], 0FFFFFFFDh
0x140015ee2  mov     dl, dil
0x140015ee5  mov     rcx, rbx
0x140015ee8  call    Smb2LeaseProcessPendingLeaseOperationsAndReleaseSpinLock
0x140015eed  jmp     loc_140015DDC
0x140015ef2  mov     rcx, cs:WPP_GLOBAL_Control
0x140015ef9  cmp     rcx, r13
0x140015efc  jz      loc_140015DDC
0x140015f02  bt      dword ptr [rcx+2Ch], 1Eh
0x140015f07  jnb     loc_140015DDC
0x140015f0d  cmp     [rcx+29h], r14b
0x140015f11  jb      loc_140015DDC
0x140015f17  mov     rcx, [rcx+18h]
0x140015f1b  lea     r8, WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids
0x140015f22  mov     edx, 18h
0x140015f27  mov     r9, rbx
0x140015f2a  call    WPP_SF_q
0x140015f2f  jmp     loc_140015DDC
0x140015f34  and     dword ptr [rbx+8Ch], 0FFFFFFFDh
0x140015f3b  add     [rsi], r13w
0x140015f3f  mov     [rbx+89h], r13b
0x140015f46  jmp     loc_140015BBA
0x140015f4b  mov     eax, r12d
0x140015f4e  jmp     loc_140015C30
0x140015f53  mov     rcx, cs:WPP_GLOBAL_Control
0x140015f5a  lea     rax, WPP_GLOBAL_Control
0x140015f61  cmp     rcx, rax
0x140015f64  jz      loc_14003C928
0x140015f6a  test    dword ptr [rcx+2Ch], 40000000h
0x140015f71  jz      loc_14003C928
0x140015f77  cmp     [rcx+29h], r14b
0x140015f7b  jb      loc_14003C928
0x140015f81  mov     rcx, [rcx+18h]
0x140015f85  lea     r8, WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids
0x140015f8c  mov     edx, 1Ah
0x140015f91  mov     r9, rbx
0x140015f94  call    WPP_SF_q
0x140015f99  nop
0x140015f9a  jmp     loc_14003C928
0x140015f9f  mov     rax, [rbx+100h]
0x140015fa6  lea     rcx, Smb2LeaseSendCompleteAndResetLeaseState
0x140015fad  mov     [rax+10h], rcx
0x140015fb1  jmp     loc_140015D4C
0x140015fb6  cmp     [rbx+0B0h], r12d
0x140015fbd  jbe     loc_140015D88
0x140015fc3  mov     rdx, rdi
0x140015fc6  mov     rcx, rbx
0x140015fc9  call    Smb2LeaseSelectConnection
0x140015fce  mov     rsi, rax
0x140015fd1  jmp     loc_140015D88
0x140015fd6  mov     rcx, rbx
0x140015fd9  call    Smb2LeaseProcessBreakNoConnectionsAndReleaseSpinLock
0x140015fde  jmp     loc_140015DD3
0x140015fe3  mov     rcx, rdi; P
0x140015fe6  call    Srv2DereferenceConnection
0x140015feb  jmp     loc_140015DDC
0x14003c928  mov     rax, [rbx+170h]
0x14003c92f  mov     ecx, 300h
0x14003c934  cmp     [rax+98h], cx
0x14003c93b  jb      short loc_14003C944
0x14003c93d  mov     dword ptr [rdi+8], 0C0000128h
0x14003c944  mov     [rdi+5Ch], r12d
0x14003c948  jmp     loc_140015C99
0x14003c94d  mov     eax, [rdi+5Ch]
0x14003c950  mov     r9, [rdi+28h]
0x14003c954  mov     [rsp+0F8h+var_70], rsi
0x14003c95c  mov     [rsp+0F8h+var_78], r12d
0x14003c964  mov     [rsp+0F8h+var_80], r12d
0x14003c969  mov     [rsp+0F8h+var_88], r12d
0x14003c96e  mov     [rsp+0F8h+var_90], eax
0x14003c972  mov     eax, [rdi+58h]
0x14003c975  mov     [rsp+0F8h+var_98], eax
0x14003c979  mov     eax, [rdi+44h]
0x14003c97c  mov     [rsp+0F8h+var_A0], eax
0x14003c980  mov     eax, [rdi+10h]
0x14003c983  mov     [rsp+0F8h+var_A8], eax
0x14003c987  movzx   eax, word ptr [rdi+0Eh]
0x14003c98b  mov     [rsp+0F8h+var_B0], ax
0x14003c990  movzx   eax, word ptr [rdi+0Ch]
0x14003c994  mov     [rsp+0F8h+var_B8], ax
0x14003c999  mov     rax, [rdi+18h]
0x14003c99d  mov     [rsp+0F8h+var_C8], rax
0x14003c9a2  mov     eax, [rdi+24h]
0x14003c9a5  mov     [rsp+0F8h+Priority], eax
0x14003c9a9  mov     eax, [rdi+20h]
0x14003c9ac  mov     [rsp+0F8h+BugCheckOnFailure], eax
  ... truncated ...
```
