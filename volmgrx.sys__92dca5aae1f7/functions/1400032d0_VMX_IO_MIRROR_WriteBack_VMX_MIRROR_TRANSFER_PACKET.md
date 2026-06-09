# VMX_IO_MIRROR::WriteBack(VMX_MIRROR_TRANSFER_PACKET *)

- ea: `0x1400032d0`
- end: `0x14000376e`
- name: `?WriteBack@VMX_IO_MIRROR@@QEAAXPEAVVMX_MIRROR_TRANSFER_PACKET@@@Z`
- size: `1182`
- prototype: `void __fastcall(VMX_IO_MIRROR *__hidden this, struct VMX_MIRROR_TRANSFER_PACKET *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002be0`

## callees

- `0x1400032d0`
- `0x140003774`
- `0x140003bd8`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400033e0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400033e0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000340c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000340c`
- `ntoskrnl!ExAllocatePool2` at `0x14000332b`
- `ntoskrnl!ExAllocatePool2` at `0x140003619`
- `ntoskrnl!ExAllocatePool2` at `0x14000332b`
- `ntoskrnl!ExAllocatePool2` at `0x140003619`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400036ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000374d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400036ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000374d`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400033c7`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400033c7`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140003657`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140003657`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000335f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000335f`

## pseudocode

```c
void __fastcall VMX_IO_MIRROR::WriteBack(VMX_IO_MIRROR *this, struct VMX_MIRROR_TRANSFER_PACKET *a2)
{
  __int64 v3; // rsi
  unsigned int v5; // edi
  int v6; // r12d
  int v7; // r13d
  _QWORD *Pool2; // rax
  _QWORD *v9; // r14
  unsigned int v10; // ebp
  struct _LIST_ENTRY *Flink; // rcx
  _BYTE *v12; // rax
  _BYTE *v13; // rcx
  __int64 v14; // rax
  KIRQL v15; // al
  unsigned int v16; // edx
  __int64 v17; // r8
  __int64 v18; // rbp
  __int64 v19; // rcx
  void (__fastcall *v20)(struct VMX_TRANSFER_PACKET *); // r8
  struct VMX_MIRROR_TRANSFER_PACKET *v21; // rdx
  __int64 v22; // rcx
  void (__fastcall ***v23)(_QWORD, __int64, void (__fastcall *)(struct VMX_TRANSFER_PACKET *)); // rcx
  unsigned int v24; // edi
  __int64 i; // rbx
  __int64 v26; // rcx
  struct _LIST_ENTRY *v27; // rax
  unsigned int v28; // r13d
  void (__fastcall ***v29)(_QWORD, __int64); // rcx
  bool v30; // zf
  __int64 j; // rbx
  void (__fastcall ***v32)(_QWORD, __int64); // rcx
  int v33; // [rsp+70h] [rbp+8h]

  v3 = *((_QWORD *)a2 + 28);
  v5 = *((_DWORD *)this + 14);
  v6 = *((_DWORD *)a2 + 60);
  v7 = *((_DWORD *)a2 + 24);
  v33 = v7;
  if ( a2 == *((struct VMX_MIRROR_TRANSFER_PACKET **)this + 21) )
  {
LABEL_8:
    v9 = 0;
  }
  else
  {
    Pool2 = (_QWORD *)ExAllocatePool2(66, 8LL * v5, 1934650710);
    v9 = Pool2;
    if ( Pool2 )
    {
      *Pool2 = a2;
      v10 = 1;
      while ( v10 < v5 )
      {
        Flink = WPP_MAIN_CB.Queue.ListEntry.Flink;
        if ( !WPP_MAIN_CB.Queue.ListEntry.Flink )
        {
          v27 = (struct _LIST_ENTRY *)ExAllocatePool2(66, 128, 538996054);
          WPP_MAIN_CB.Queue.ListEntry.Flink = v27;
          if ( !v27 )
          {
LABEL_37:
            v28 = 1;
            for ( v9[v10] = 0; v28 < v10; ++v28 )
            {
              v29 = (void (__fastcall ***)(_QWORD, __int64))v9[v28];
              if ( v29 )
                (**v29)(v29, 1);
            }
            ExFreePoolWithTag(v9, 0);
            v7 = v33;
            goto LABEL_8;
          }
          ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v27, 0, 0, 0x200u, 0x128u, 0x32506D56u, 0x20u);
          Flink = WPP_MAIN_CB.Queue.ListEntry.Flink;
        }
        v12 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)Flink);
        v13 = v12;
        if ( !v12 )
          goto LABEL_37;
        v12[80] = 2;
        *((_QWORD *)v12 + 4) = 0;
        *((_QWORD *)v12 + 3) = 0;
        v12[83] = 0;
        *((_WORD *)v12 + 66) = 0;
        *((_QWORD *)v12 + 27) = 0;
        v12[177] = 0;
        *(_QWORD *)v12 = &VMX_RAID5_TRANSFER_PACKET::`vftable';
        v14 = v10++;
        *((_WORD *)v13 + 136) = 0;
        v13[274] = 0;
        v9[v14] = v13;
      }
    }
  }
  KeInitializeSpinLock((PKSPIN_LOCK)(v3 + 88));
  *(_DWORD *)(v3 + 96) = 0;
  *(_QWORD *)(v3 + 104) = 0;
  v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 3);
  *(_DWORD *)(v3 + 128) = 0;
  v16 = 0;
  v17 = *((_QWORD *)this + 12);
  while ( v16 < v5 )
  {
    if ( (*(_DWORD *)(v17 + 16) & 0xFFFFFFFD) == 0 && (v16 != v6 || v7 == 1073741834) )
    {
      if ( !v9 )
      {
        *((_DWORD *)a2 + 60) = v16;
        ++*(_DWORD *)(v3 + 128);
        break;
      }
      *(_DWORD *)(v9[(*(_DWORD *)(v3 + 128))++] + 240LL) = v16;
    }
    ++v16;
    v17 += 40;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)this + 3, v15);
  if ( *(_DWORD *)(v3 + 128) )
  {
    v18 = 0;
    v20 = VmxpMirrorTransferCompletionRoutine;
    do
    {
      if ( v9 )
      {
        v21 = (struct VMX_MIRROR_TRANSFER_PACKET *)v9[v18];
        *((_QWORD *)v21 + 31) = v9;
        *((_DWORD *)v21 + 64) = *(_DWORD *)(v3 + 128);
        *((_DWORD *)v21 + 65) = v18;
      }
      else
      {
        v21 = a2;
        *((_QWORD *)a2 + 31) = 0;
        *((_QWORD *)a2 + 32) = 0;
      }
      v18 = (unsigned int)(v18 + 1);
      v22 = *((unsigned int *)v21 + 60);
      *((_QWORD *)v21 + 3) = *((_QWORD *)a2 + 3);
      *((_QWORD *)v21 + 4) = 0;
      *((_DWORD *)v21 + 2) = *((_DWORD *)a2 + 2);
      *((_QWORD *)v21 + 2) = *((_QWORD *)a2 + 2);
      *((_QWORD *)v21 + 5) = VmxpMirrorTransferCompletionRoutine;
      *((_QWORD *)v21 + 6) = *(_QWORD *)(*((_QWORD *)this + 6) + 8 * v22);
      *((_QWORD *)v21 + 7) = *((_QWORD *)a2 + 7);
      *((_DWORD *)v21 + 16) = *((_DWORD *)a2 + 16);
      *((_QWORD *)v21 + 9) = *((_QWORD *)a2 + 9);
      *((_BYTE *)v21 + 81) = *((_BYTE *)a2 + 81);
      *((_BYTE *)v21 + 82) = 0;
      *((_QWORD *)v21 + 28) = *((_QWORD *)a2 + 28);
      *((_QWORD *)v21 + 29) = *((_QWORD *)a2 + 29);
      *((_BYTE *)v21 + 272) = 0;
      *((_BYTE *)v21 + 274) = 1;
      *(_OWORD *)((char *)v21 + 280) = *((_OWORD *)a2 + 6);
    }
    while ( (unsigned int)v18 < *(_DWORD *)(v3 + 128) );
    if ( v9 )
    {
      for ( ; (unsigned int)v18 < v5; v18 = (unsigned int)(v18 + 1) )
      {
        v23 = (void (__fastcall ***)(_QWORD, __int64, void (__fastcall *)(struct VMX_TRANSFER_PACKET *)))v9[v18];
        if ( v23 )
          (**v23)(v23, 1, v20);
      }
      v24 = *(_DWORD *)(v3 + 128);
      for ( i = 0; (unsigned int)i < v24; i = (unsigned int)(i + 1) )
      {
        *(_DWORD *)(v9[i] + 12LL) = 16842755;
        v26 = *(_QWORD *)(v9[i] + 48LL);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26);
      }
    }
    else
    {
      v19 = *((_QWORD *)a2 + 6);
      *((_DWORD *)a2 + 3) = 16842755;
      (*(void (__fastcall **)(__int64, struct VMX_MIRROR_TRANSFER_PACKET *))(*(_QWORD *)v19 + 8LL))(v19, a2);
    }
  }
  else
  {
    v30 = *(_DWORD *)(v3 + 168) == 0;
    *(_OWORD *)(v3 + 96) = *((_OWORD *)a2 + 6);
    if ( v30 )
    {
      (*(void (__fastcall **)(__int64))(v3 + 40))(v3);
    }
    else
    {
      *(_QWORD *)(v3 + 152) = VmxpMirrorLogDetachOperation;
      *(_QWORD *)(v3 + 160) = VmxpMirrorLogDetachCompletion;
      VMX_LOG::QueueLogPacket(*((VMX_LOG **)this + 16), (struct VMX_LOG_TRANSFER_PACKET *)v3);
    }
    if ( v9 )
    {
      for ( j = 0; (unsigned int)j < v5; j = (unsigned int)(j + 1) )
      {
        v32 = (void (__fastcall ***)(_QWORD, __int64))v9[j];
        if ( v32 )
          (**v32)(v32, 1);
      }
      ExFreePoolWithTag(v9, 0);
    }
    else
    {
      VMX_IO_MIRROR::RecyclePacket(this, a2);
    }
  }
}

```

## disassembly

```asm
0x1400032d0  mov     [rsp+arg_18], rbx
0x1400032d5  push    rbp
0x1400032d6  push    rsi
0x1400032d7  push    rdi
0x1400032d8  push    r14
0x1400032da  push    r15
0x1400032dc  sub     rsp, 40h
0x1400032e0  mov     rbx, rdx
0x1400032e3  mov     rsi, [rdx+0E0h]
0x1400032ea  mov     r15, rcx
0x1400032ed  mov     edi, [rcx+38h]
0x1400032f0  mov     [rsp+68h+arg_8], r12
0x1400032f5  mov     r12d, [rdx+0F0h]
0x1400032fc  mov     [rsp+68h+arg_10], r13
0x140003304  mov     r13d, [rdx+60h]
0x140003308  mov     [rsp+68h+arg_0], r13d
0x14000330d  cmp     rdx, [rcx+0A8h]
0x140003314  jz      loc_1400033C0
0x14000331a  mov     edx, edi
0x14000331c  mov     ecx, 42h ; 'B'
0x140003321  shl     rdx, 3
0x140003325  mov     r8d, 73506D56h
0x14000332b  call    cs:__imp_ExAllocatePool2
0x140003332  nop     dword ptr [rax+rax+00h]
0x140003337  mov     r14, rax
0x14000333a  test    rax, rax
0x14000333d  jz      loc_1400033C3
0x140003343  mov     [rax], rbx
0x140003346  mov     ebp, 1
0x14000334b  cmp     ebp, edi
0x14000334d  jnb     short loc_1400033C3
0x14000334f  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue; Lookaside
0x140003356  test    rcx, rcx
0x140003359  jz      loc_140003609
0x14000335f  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140003366  nop     dword ptr [rax+rax+00h]
0x14000336b  mov     rcx, rax
0x14000336e  test    rax, rax
0x140003371  jz      loc_14000366F
0x140003377  mov     byte ptr [rax+50h], 2
0x14000337b  xor     eax, eax
0x14000337d  mov     [rcx+20h], rax
0x140003381  mov     [rcx+18h], rax
0x140003385  mov     [rcx+53h], al
0x140003388  mov     [rcx+84h], ax
0x14000338f  mov     [rcx+0D8h], rax
0x140003396  mov     [rcx+0B1h], al
0x14000339c  lea     rax, ??_7VMX_RAID5_TRANSFER_PACKET@@6B@; const VMX_RAID5_TRANSFER_PACKET::`vftable'
0x1400033a3  mov     [rcx], rax
0x1400033a6  mov     eax, ebp
0x1400033a8  inc     ebp
0x1400033aa  mov     word ptr [rcx+110h], 0
0x1400033b3  mov     byte ptr [rcx+112h], 0
0x1400033ba  mov     [r14+rax*8], rcx
0x1400033be  jmp     short loc_14000334B
0x1400033c0  xor     r14d, r14d
0x1400033c3  lea     rcx, [rsi+58h]; SpinLock
0x1400033c7  call    cs:__imp_KeInitializeSpinLock
0x1400033ce  nop     dword ptr [rax+rax+00h]
0x1400033d3  xor     eax, eax
0x1400033d5  lea     rcx, [r15+18h]; SpinLock
0x1400033d9  mov     [rsi+60h], eax
0x1400033dc  mov     [rsi+68h], rax
0x1400033e0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400033e7  nop     dword ptr [rax+rax+00h]
0x1400033ec  mov     dword ptr [rsi+80h], 0
0x1400033f6  xor     edx, edx
0x1400033f8  mov     r8, [r15+60h]
0x1400033fc  movzx   r9d, al
0x140003400  cmp     edx, edi
0x140003402  jb      short loc_140003471
0x140003404  movzx   edx, r9b; NewIrql
0x140003408  lea     rcx, [r15+18h]; SpinLock
0x14000340c  call    cs:__imp_KeReleaseSpinLock
0x140003413  nop     dword ptr [rax+rax+00h]
0x140003418  mov     eax, [rsi+80h]
0x14000341e  mov     r13, [rsp+68h+arg_10]
0x140003426  mov     r12, [rsp+68h+arg_8]
0x14000342b  test    eax, eax
0x14000342d  jz      loc_1400036D4
0x140003433  xor     ebp, ebp
0x140003435  test    eax, eax
0x140003437  jnz     short loc_1400034AF
0x140003439  test    r14, r14
0x14000343c  jnz     loc_14000358B
0x140003442  mov     rcx, [rbx+30h]
0x140003446  mov     rdx, rbx
0x140003449  mov     dword ptr [rbx+0Ch], 1010003h
0x140003450  mov     rax, [rcx]
0x140003453  mov     rax, [rax+8]
0x140003457  call    _guard_dispatch_icall
0x14000345c  mov     rbx, [rsp+68h+arg_18]
0x140003464  add     rsp, 40h
0x140003468  pop     r15
0x14000346a  pop     r14
0x14000346c  pop     rdi
0x14000346d  pop     rsi
0x14000346e  pop     rbp
0x14000346f  retn
0x140003471  test    dword ptr [r8+10h], 0FFFFFFFDh
0x140003479  jnz     short loc_1400034A4
0x14000347b  cmp     edx, r12d
0x14000347e  jz      loc_140003579
0x140003484  test    r14, r14
0x140003487  jz      loc_1400036C3
0x14000348d  movsxd  rax, dword ptr [rsi+80h]
0x140003494  mov     rcx, [r14+rax*8]
0x140003498  mov     [rcx+0F0h], edx
0x14000349e  inc     dword ptr [rsi+80h]
0x1400034a4  inc     edx
0x1400034a6  add     r8, 28h ; '('
0x1400034aa  jmp     loc_140003400
0x1400034af  lea     r8, ?VmxpMirrorTransferCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpMirrorTransferCompletionRoutine(VMX_TRANSFER_PACKET *)
0x1400034b6  test    r14, r14
0x1400034b9  jz      loc_1400035EB
0x1400034bf  mov     rdx, [r14+rbp*8]
0x1400034c3  mov     [rdx+0F8h], r14
0x1400034ca  mov     eax, [rsi+80h]
0x1400034d0  mov     [rdx+100h], eax
0x1400034d6  mov     [rdx+104h], ebp
0x1400034dc  mov     rax, [rbx+18h]
0x1400034e0  inc     ebp
0x1400034e2  mov     ecx, [rdx+0F0h]
0x1400034e8  mov     [rdx+18h], rax
0x1400034ec  mov     qword ptr [rdx+20h], 0
0x1400034f4  mov     eax, [rbx+8]
0x1400034f7  mov     [rdx+8], eax
0x1400034fa  mov     rax, [rbx+10h]
0x1400034fe  mov     [rdx+10h], rax
0x140003502  mov     [rdx+28h], r8
0x140003506  mov     rax, [r15+30h]
0x14000350a  mov     rcx, [rax+rcx*8]
0x14000350e  mov     [rdx+30h], rcx
0x140003512  mov     rax, [rbx+38h]
0x140003516  mov     [rdx+38h], rax
0x14000351a  mov     eax, [rbx+40h]
0x14000351d  mov     [rdx+40h], eax
0x140003520  mov     rax, [rbx+48h]
0x140003524  mov     [rdx+48h], rax
0x140003528  movzx   eax, byte ptr [rbx+51h]
0x14000352c  mov     [rdx+51h], al
0x14000352f  mov     byte ptr [rdx+52h], 0
0x140003533  mov     rax, [rbx+0E0h]
0x14000353a  mov     [rdx+0E0h], rax
0x140003541  mov     rax, [rbx+0E8h]
0x140003548  mov     [rdx+0E8h], rax
0x14000354f  mov     byte ptr [rdx+110h], 0
0x140003556  mov     byte ptr [rdx+112h], 1
0x14000355d  movups  xmm0, xmmword ptr [rbx+60h]
0x140003561  movups  xmmword ptr [rdx+118h], xmm0
0x140003568  cmp     ebp, [rsi+80h]
0x14000356e  jnb     loc_140003439
0x140003574  jmp     loc_1400034B6
0x140003579  cmp     r13d, 4000000Ah
0x140003580  jnz     loc_1400034A4
0x140003586  jmp     loc_140003484
0x14000358b  cmp     ebp, edi
0x14000358d  jnb     short loc_1400035AE
0x14000358f  mov     rcx, [r14+rbp*8]
0x140003593  test    rcx, rcx
0x140003596  jz      short loc_1400035A8
0x140003598  mov     rax, [rcx]
0x14000359b  mov     edx, 1
0x1400035a0  mov     rax, [rax]
0x1400035a3  call    _guard_dispatch_icall
0x1400035a8  inc     ebp
0x1400035aa  cmp     ebp, edi
0x1400035ac  jb      short loc_14000358F
0x1400035ae  mov     edi, [rsi+80h]
0x1400035b4  xor     ebx, ebx
0x1400035b6  test    edi, edi
0x1400035b8  jz      loc_14000345C
0x1400035be  mov     rax, [r14+rbx*8]
0x1400035c2  lea     rcx, [r14+rbx*8]
0x1400035c6  mov     dword ptr [rax+0Ch], 1010003h
0x1400035cd  mov     rdx, [rcx]
0x1400035d0  mov     rcx, [rdx+30h]
0x1400035d4  mov     rax, [rcx]
0x1400035d7  mov     rax, [rax+8]
0x1400035db  call    _guard_dispatch_icall
0x1400035e0  inc     ebx
0x1400035e2  cmp     ebx, edi
0x1400035e4  jb      short loc_1400035BE
0x1400035e6  jmp     loc_14000345C
0x1400035eb  mov     rdx, rbx
0x1400035ee  mov     qword ptr [rbx+0F8h], 0
0x1400035f9  mov     qword ptr [rbx+100h], 0
0x140003604  jmp     loc_1400034DC
0x140003609  mov     edx, 80h
0x14000360e  mov     ecx, 42h ; 'B'
0x140003613  mov     r8d, 20206D56h
0x140003619  call    cs:__imp_ExAllocatePool2
0x140003620  nop     dword ptr [rax+rax+00h]
0x140003625  mov     qword ptr cs:WPP_MAIN_CB.Queue, rax
0x14000362c  test    rax, rax
0x14000362f  jz      short loc_14000366F
0x140003631  mov     [rsp+68h+Depth], 20h ; ' '; Depth
0x140003638  mov     r9d, 200h; Flags
0x14000363e  mov     [rsp+68h+Tag], 32506D56h; Tag
0x140003646  xor     r8d, r8d; Free
0x140003649  xor     edx, edx; Allocate
0x14000364b  mov     [rsp+68h+Size], 128h; Size
0x140003654  mov     rcx, rax; Lookaside
0x140003657  call    cs:__imp_ExInitializeNPagedLookasideList
0x14000365e  nop     dword ptr [rax+rax+00h]
0x140003663  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x14000366a  jmp     loc_14000335F
0x14000366f  mov     eax, ebp
0x140003671  mov     r13d, 1
0x140003677  mov     qword ptr [r14+rax*8], 0
0x14000367f  cmp     ebp, r13d
0x140003682  jbe     short loc_1400036A8
0x140003684  mov     eax, r13d
0x140003687  mov     rcx, [r14+rax*8]
0x14000368b  test    rcx, rcx
0x14000368e  jz      short loc_1400036A0
0x140003690  mov     rax, [rcx]
0x140003693  mov     edx, 1
0x140003698  mov     rax, [rax]
0x14000369b  call    _guard_dispatch_icall
0x1400036a0  inc     r13d
0x1400036a3  cmp     r13d, ebp
0x1400036a6  jb      short loc_140003684
0x1400036a8  xor     edx, edx; Tag
0x1400036aa  mov     rcx, r14; P
0x1400036ad  call    cs:__imp_ExFreePoolWithTag
0x1400036b4  nop     dword ptr [rax+rax+00h]
0x1400036b9  mov     r13d, [rsp+68h+arg_0]
0x1400036be  jmp     loc_1400033C0
0x1400036c3  mov     [rbx+0F0h], edx
0x1400036c9  inc     dword ptr [rsi+80h]
0x1400036cf  jmp     loc_140003404
0x1400036d4  cmp     dword ptr [rsi+0A8h], 0
0x1400036db  movups  xmm0, xmmword ptr [rbx+60h]
0x1400036df  movups  xmmword ptr [rsi+60h], xmm0
0x1400036e3  jbe     short loc_140003712
0x1400036e5  lea     rax, ?VmxpMirrorLogDetachOperation@@YAJPEAVVMX_LOG_TRANSFER_PACKET@@@Z; VmxpMirrorLogDetachOperation(VMX_LOG_TRANSFER_PACKET *)
0x1400036ec  mov     rdx, rsi; struct VMX_LOG_TRANSFER_PACKET *
0x1400036ef  mov     [rsi+98h], rax
0x1400036f6  lea     rax, ?VmxpMirrorLogDetachCompletion@@YAXPEAVVMX_LOG_TRANSFER_PACKET@@J@Z; VmxpMirrorLogDetachCompletion(VMX_LOG_TRANSFER_PACKET *,long)
0x1400036fd  mov     [rsi+0A0h], rax
0x140003704  mov     rcx, [r15+80h]; this
0x14000370b  call    ?QueueLogPacket@VMX_LOG@@QEAAXPEAVVMX_LOG_TRANSFER_PACKET@@@Z; VMX_LOG::QueueLogPacket(VMX_LOG_TRANSFER_PACKET *)
0x140003710  jmp     short loc_14000371E
0x140003712  mov     rax, [rsi+28h]
0x140003716  mov     rcx, rsi
0x140003719  call    _guard_dispatch_icall
0x14000371e  test    r14, r14
0x140003721  jz      short loc_14000375E
0x140003723  xor     ebx, ebx
0x140003725  test    edi, edi
0x140003727  jz      short loc_140003748
0x140003729  mov     rcx, [r14+rbx*8]
0x14000372d  test    rcx, rcx
0x140003730  jz      short loc_140003742
0x140003732  mov     rax, [rcx]
0x140003735  mov     edx, 1
0x14000373a  mov     rax, [rax]
0x14000373d  call    _guard_dispatch_icall
0x140003742  inc     ebx
0x140003744  cmp     ebx, edi
0x140003746  jb      short loc_140003729
0x140003748  xor     edx, edx; Tag
0x14000374a  mov     rcx, r14; P
0x14000374d  call    cs:__imp_ExFreePoolWithTag
0x140003754  nop     dword ptr [rax+rax+00h]
0x140003759  jmp     loc_14000345C
0x14000375e  mov     rdx, rbx; struct VMX_MIRROR_TRANSFER_PACKET *
0x140003761  mov     rcx, r15; this
0x140003764  call    ?RecyclePacket@VMX_IO_MIRROR@@QEAAXPEAVVMX_MIRROR_TRANSFER_PACKET@@@Z; VMX_IO_MIRROR::RecyclePacket(VMX_MIRROR_TRANSFER_PACKET *)
0x140003769  jmp     loc_14000345C
```
