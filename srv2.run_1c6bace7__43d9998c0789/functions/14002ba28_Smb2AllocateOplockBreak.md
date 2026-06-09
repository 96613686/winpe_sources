# Smb2AllocateOplockBreak

- ea: `0x14002ba28`
- end: `0x14002bd15`
- name: `Smb2AllocateOplockBreak`
- size: `749`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140021cc0`

## callees

- `0x140012ca0`
- `0x140013920`
- `0x140016d30`
- `0x14002ba28`
- `0x14007ca90`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002ba79`
- `ntoskrnl!ExAllocatePool2` at `0x14002ba79`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002bcbd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002bcbd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002bd01`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002bd01`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14002bb69`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14002bb69`
- `ntoskrnl!MmSizeOfMdl` at `0x14002ba50`
- `ntoskrnl!MmSizeOfMdl` at `0x14002ba50`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bad7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bad7`
- `ntoskrnl!IoAllocateIrp` at `0x14002babd`
- `ntoskrnl!IoAllocateIrp` at `0x14002babd`

## pseudocode

```c
__int64 __fastcall Smb2AllocateOplockBreak(__int64 a1)
{
  unsigned int v2; // eax
  unsigned int v3; // edi
  __int64 Pool2; // rax
  __int64 v5; // rbx
  __int64 v6; // rcx
  PIRP Irp; // rax
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rdx
  __int64 v11; // r14
  __int128 v12; // xmm0
  __int64 v13; // rcx
  _BYTE *v14; // rdi
  KIRQL v15; // al
  _QWORD *v16; // rcx
  PVOID P; // [rsp+58h] [rbp+10h] BYREF
  __int64 v18; // [rsp+60h] [rbp+18h] BYREF

  v18 = 0;
  P = 0;
  v2 = MmSizeOfMdl((PVOID)0xFFFFFFFFFFFFFFFFLL, 0x1E0u);
  v3 = v2 + 544;
  if ( v2 >= 0xFFFFFDE0 )
    return 0;
  Pool2 = ExAllocatePool2(64, v3, 1865569100);
  v5 = Pool2;
  if ( !Pool2 )
    return 0;
  v6 = *(_QWORD *)(a1 + 64);
  *(_QWORD *)Pool2 = 1;
  *(_DWORD *)(Pool2 + 8) = 13;
  *(_DWORD *)(Pool2 + 12) = 220;
  *(_WORD *)(Pool2 + 16) = v3;
  *(_QWORD *)(Pool2 + 48) = 0;
  *(_QWORD *)(Pool2 + 56) = Pool2;
  *(_QWORD *)(Pool2 + 64) = v6;
  *(_DWORD *)(Pool2 + 72) = 0;
  Irp = IoAllocateIrp(7, 0);
  *(_QWORD *)(v5 + 120) = Irp;
  if ( !Irp )
  {
    ExFreePoolWithTag((PVOID)v5, 0);
    return 0;
  }
  v9 = (v5 + 343) & 0xFFFFFFFFFFFFFFF8uLL;
  *(_QWORD *)(v5 + 136) = v9;
  v10 = v9 + 192;
  *(_QWORD *)(v5 + 128) = v9 + 192;
  *(_QWORD *)(v9 + 192) = 0;
  *(_WORD *)(v9 + 202) = 0;
  *(_DWORD *)(v9 + 232) = 112;
  *(_WORD *)(v9 + 200) = 8 * (((unsigned __int16)(((v9 + 80) & 0xFFF) + 4207) >> 12) + 6);
  v9 += 80LL;
  *(_QWORD *)(v10 + 32) = v9 & 0xFFFFFFFFFFFFF000uLL;
  *(_DWORD *)(v10 + 44) = v9 & 0xFFF;
  MmBuildMdlForNonPagedPool(*(PMDL *)(v5 + 128));
  *(_WORD *)(*(_QWORD *)(v5 + 128) + 10LL) |= 0x1000u;
  *(_QWORD *)(v5 + 136) += 80LL;
  *(_QWORD *)(v5 + 88) = v5 + 80;
  *(_QWORD *)(v5 + 80) = v5 + 80;
  *(_QWORD *)(v5 + 312) = v5 + 304;
  *(_QWORD *)(v5 + 304) = v5 + 304;
  *(_QWORD *)(v5 + 144) = a1;
  Smb2ReferenceFile(a1);
  v11 = *(_QWORD *)(v5 + 136);
  *(_WORD *)(v11 + 12) = 18;
  *(_QWORD *)(v11 + 24) = -1;
  *(_DWORD *)v11 = 1112364030;
  *(_WORD *)(v11 + 4) = 64;
  *(_DWORD *)(v11 + 16) = 1;
  v12 = *(_OWORD *)(a1 + 80);
  *(_BYTE *)(v11 + 67) = 0;
  *(_DWORD *)(v11 + 68) = 0;
  *(_OWORD *)(v11 + 72) = v12;
  *(_BYTE *)(v11 + 66) = *(_BYTE *)(a1 + 285);
  *(_WORD *)(v11 + 64) = 24;
  *(_QWORD *)(v5 + 168) = Smb2OplockSendComplete;
  *(_QWORD *)(v5 + 192) = *(_QWORD *)(v5 + 120);
  *(_QWORD *)(v5 + 160) = *(_QWORD *)(v5 + 128);
  *(_QWORD *)(v5 + 176) = v5;
  *(_DWORD *)(v5 + 152) = 112;
  *(_QWORD *)(v5 + 184) = 0;
  *(_DWORD *)(v5 + 240) = 0;
  if ( (int)Smb2ReferenceSessionAndTreeConnectFromFile(a1, &v18, &P) >= 0 )
  {
    v13 = v18;
    v14 = P;
    *(_QWORD *)(v5 + 232) = 0;
    if ( (*(_BYTE *)(v13 + 59) || v14 && v14[90]) && !*(_BYTE *)(v13 + 63) )
      *(_QWORD *)(v5 + 232) = *(_QWORD *)(v13 + 40);
    *(_DWORD *)(v5 + 240) = *(_DWORD *)(v13 + 300);
    *(_QWORD *)(v11 + 40) = *(_QWORD *)v13;
    *(_QWORD *)(v5 + 224) = *(_QWORD *)v13;
    Smb2DereferenceSession(v13);
    Smb2DereferenceTreeConnect(v14);
  }
  v15 = KeAcquireSpinLockRaiseToDpc(&qword_14004B500);
  v16 = (_QWORD *)qword_14004B528;
  if ( *(__int64 **)qword_14004B528 != &qword_14004B520 )
    __fastfail(3u);
  *(_QWORD *)(v5 + 104) = qword_14004B528;
  *(_QWORD *)(v5 + 96) = &qword_14004B520;
  *v16 = v5 + 96;
  qword_14004B528 = v5 + 96;
  KeReleaseSpinLock(&qword_14004B500, v15);
  return v5;
}

```

## disassembly

```asm
0x14002ba28  mov     [rsp+arg_0], rbx
0x14002ba2d  push    rbp
0x14002ba2e  push    rsi
0x14002ba2f  push    rdi
0x14002ba30  push    r12
0x14002ba32  push    r14
0x14002ba34  sub     rsp, 20h
0x14002ba38  mov     rsi, rcx
0x14002ba3b  xor     ebp, ebp
0x14002ba3d  or      rcx, 0FFFFFFFFFFFFFFFFh; Base
0x14002ba41  mov     [rsp+48h+arg_10], rbp
0x14002ba46  mov     edx, 1E0h; Length
0x14002ba4b  mov     [rsp+48h+P], rbp
0x14002ba50  call    cs:__imp_MmSizeOfMdl
0x14002ba57  nop     dword ptr [rax+rax+00h]
0x14002ba5c  lea     edi, [rax+220h]
0x14002ba62  cmp     edi, 220h
0x14002ba68  jb      short loc_14002BAE3
0x14002ba6a  lea     r12d, [rbp+40h]
0x14002ba6e  mov     edx, edi
0x14002ba70  mov     ecx, r12d
0x14002ba73  mov     r8d, 6F32534Ch
0x14002ba79  call    cs:__imp_ExAllocatePool2
0x14002ba80  nop     dword ptr [rax+rax+00h]
0x14002ba85  mov     rbx, rax
0x14002ba88  test    rax, rax
0x14002ba8b  jz      short loc_14002BAE3
0x14002ba8d  mov     rcx, [rsi+40h]
0x14002ba91  xor     edx, edx; ChargeQuota
0x14002ba93  mov     qword ptr [rax], 1
0x14002ba9a  mov     dword ptr [rax+8], 0Dh
0x14002baa1  mov     dword ptr [rax+0Ch], 0DCh
0x14002baa8  mov     [rax+10h], di
0x14002baac  mov     [rax+30h], rbp
0x14002bab0  mov     [rax+38h], rax
0x14002bab4  mov     [rax+40h], rcx
0x14002bab8  mov     cl, 7; StackSize
0x14002baba  mov     [rax+48h], ebp
0x14002babd  call    cs:__imp_IoAllocateIrp
0x14002bac4  nop     dword ptr [rax+rax+00h]
0x14002bac9  mov     [rbx+78h], rax
0x14002bacd  test    rax, rax
0x14002bad0  jnz     short loc_14002BAF7
0x14002bad2  xor     edx, edx; Tag
0x14002bad4  mov     rcx, rbx; P
0x14002bad7  call    cs:__imp_ExFreePoolWithTag
0x14002bade  nop     dword ptr [rax+rax+00h]
0x14002bae3  xor     eax, eax
0x14002bae5  mov     rbx, [rsp+48h+arg_0]
0x14002baea  add     rsp, 20h
0x14002baee  pop     r14
0x14002baf0  pop     r12
0x14002baf2  pop     rdi
0x14002baf3  pop     rsi
0x14002baf4  pop     rbp
0x14002baf5  retn
0x14002baf7  mov     r9d, 0FFFh
0x14002bafd  lea     rax, [rbx+157h]
0x14002bb04  and     rax, 0FFFFFFFFFFFFFFF8h
0x14002bb08  mov     edi, 70h ; 'p'
0x14002bb0d  mov     [rbx+88h], rax
0x14002bb14  lea     r8d, [r9+70h]
0x14002bb18  lea     rdx, [rax+0C0h]
0x14002bb1f  lea     rcx, [rax+50h]
0x14002bb23  mov     [rbx+80h], rdx
0x14002bb2a  movzx   eax, cx
0x14002bb2d  mov     [rdx], rbp
0x14002bb30  and     ax, r9w
0x14002bb34  mov     [rdx+0Ah], bp
0x14002bb38  add     ax, r8w
0x14002bb3c  mov     [rdx+28h], edi
0x14002bb3f  shr     ax, 0Ch
0x14002bb43  add     ax, 6
0x14002bb47  shl     ax, 3
0x14002bb4b  mov     [rdx+8], ax
0x14002bb4f  mov     rax, rcx
0x14002bb52  and     ecx, r9d
0x14002bb55  and     rax, 0FFFFFFFFFFFFF000h
0x14002bb5b  mov     [rdx+20h], rax
0x14002bb5f  mov     [rdx+2Ch], ecx
0x14002bb62  mov     rcx, [rbx+80h]; MemoryDescriptorList
0x14002bb69  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14002bb70  nop     dword ptr [rax+rax+00h]
0x14002bb75  mov     rax, [rbx+80h]
0x14002bb7c  mov     ecx, 1000h
0x14002bb81  or      [rax+0Ah], cx
0x14002bb85  lea     rax, [rbx+50h]
0x14002bb89  add     qword ptr [rbx+88h], 50h ; 'P'
0x14002bb91  mov     rcx, rsi
0x14002bb94  mov     [rax+8], rax
0x14002bb98  mov     [rax], rax
0x14002bb9b  lea     rax, [rbx+130h]
0x14002bba2  mov     [rax+8], rax
0x14002bba6  mov     [rax], rax
0x14002bba9  mov     [rbx+90h], rsi
0x14002bbb0  call    Smb2ReferenceFile
0x14002bbb5  mov     r14, [rbx+88h]
0x14002bbbc  lea     r8, [rsp+48h+P]
0x14002bbc1  lea     rdx, [rsp+48h+arg_10]
0x14002bbc6  mov     rcx, rsi
0x14002bbc9  mov     word ptr [r14+0Ch], 12h
0x14002bbd0  mov     qword ptr [r14+18h], 0FFFFFFFFFFFFFFFFh
0x14002bbd8  mov     dword ptr [r14], 424D53FEh
0x14002bbdf  mov     [r14+4], r12w
0x14002bbe4  mov     dword ptr [r14+10h], 1
0x14002bbec  movups  xmm0, xmmword ptr [rsi+50h]
0x14002bbf0  mov     [r14+43h], bpl
0x14002bbf4  mov     [r14+44h], ebp
0x14002bbf8  movdqu  xmmword ptr [r14+48h], xmm0
0x14002bbfe  mov     al, [rsi+11Dh]
0x14002bc04  mov     [r14+42h], al
0x14002bc08  lea     rax, Smb2OplockSendComplete
0x14002bc0f  mov     word ptr [r14+40h], 18h
0x14002bc16  mov     [rbx+0A8h], rax
0x14002bc1d  mov     rax, [rbx+78h]
0x14002bc21  mov     [rbx+0C0h], rax
0x14002bc28  mov     rax, [rbx+80h]
0x14002bc2f  mov     [rbx+0A0h], rax
0x14002bc36  mov     [rbx+0B0h], rbx
0x14002bc3d  mov     [rbx+98h], edi
0x14002bc43  mov     [rbx+0B8h], rbp
0x14002bc4a  mov     [rbx+0F0h], ebp
0x14002bc50  call    Smb2ReferenceSessionAndTreeConnectFromFile
0x14002bc55  test    eax, eax
0x14002bc57  js      short loc_14002BCB6
0x14002bc59  mov     rcx, [rsp+48h+arg_10]
0x14002bc5e  mov     rdi, [rsp+48h+P]
0x14002bc63  mov     [rbx+0E8h], rbp
0x14002bc6a  cmp     [rcx+3Bh], bpl
0x14002bc6e  jnz     short loc_14002BC7B
0x14002bc70  test    rdi, rdi
0x14002bc73  jz      short loc_14002BC8C
0x14002bc75  cmp     [rdi+5Ah], bpl
0x14002bc79  jz      short loc_14002BC8C
0x14002bc7b  cmp     [rcx+3Fh], bpl
0x14002bc7f  jnz     short loc_14002BC8C
0x14002bc81  mov     rax, [rcx+28h]
0x14002bc85  mov     [rbx+0E8h], rax
0x14002bc8c  mov     eax, [rcx+12Ch]
0x14002bc92  mov     [rbx+0F0h], eax
0x14002bc98  mov     rax, [rcx]
0x14002bc9b  mov     [r14+28h], rax
0x14002bc9f  mov     rax, [rcx]
0x14002bca2  mov     [rbx+0E0h], rax
0x14002bca9  call    Smb2DereferenceSession
0x14002bcae  mov     rcx, rdi; P
0x14002bcb1  call    Smb2DereferenceTreeConnect
0x14002bcb6  lea     rcx, qword_14004B500; SpinLock
0x14002bcbd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002bcc4  nop     dword ptr [rax+rax+00h]
0x14002bcc9  mov     rcx, cs:qword_14004B528
0x14002bcd0  lea     r8, qword_14004B520
0x14002bcd7  mov     dl, al; NewIrql
0x14002bcd9  cmp     [rcx], r8
0x14002bcdc  jz      short loc_14002BCE5
0x14002bcde  mov     ecx, 3
0x14002bce3  int     29h; Win8: RtlFailFast(ecx)
0x14002bce5  lea     rax, [rbx+60h]
0x14002bce9  mov     [rax+8], rcx
0x14002bced  mov     [rax], r8
0x14002bcf0  mov     [rcx], rax
0x14002bcf3  lea     rcx, qword_14004B500; SpinLock
0x14002bcfa  mov     cs:qword_14004B528, rax
0x14002bd01  call    cs:__imp_KeReleaseSpinLock
0x14002bd08  nop     dword ptr [rax+rax+00h]
0x14002bd0d  mov     rax, rbx
0x14002bd10  jmp     loc_14002BAE5
```
