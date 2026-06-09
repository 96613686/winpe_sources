# VmxpRaid5RecoverUpdateParityPhase4(VMX_TRANSFER_PACKET *)

- ea: `0x140016400`
- end: `0x14001666d`
- name: `?VmxpRaid5RecoverUpdateParityPhase4@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `621`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140007828`
- `0x14000d0dc`
- `0x140012560`
- `0x140016400`
- `0x140018fcc`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400164a1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400165fe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400164a1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400165fe`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400164e9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016644`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400164e9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016644`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140016446`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140016446`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140016544`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140016580`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140016544`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140016580`

## pseudocode

```c
void __fastcall VmxpRaid5RecoverUpdateParityPhase4(struct VMX_TRANSFER_PACKET *a1)
{
  __int64 v1; // rbx
  NTSTATUS v3; // esi
  __int64 v4; // r15
  __int64 v5; // rbp
  __int64 v6; // r8
  KIRQL v7; // al
  __int64 v8; // rdx
  KIRQL v9; // r11
  __int64 v10; // rcx
  int v11; // r14d
  PVOID v12; // rsi
  __int64 v13; // r10
  PVOID v14; // rax
  unsigned int v15; // eax
  __int64 v16; // rcx
  KIRQL v17; // al
  _QWORD *v18; // rcx
  KIRQL v19; // dl
  _QWORD *v20; // rbx
  _QWORD *v21; // rbx
  __int64 v22; // rax

  v1 = *((_QWORD *)a1 + 17);
  v3 = *((_DWORD *)a1 + 24);
  v4 = *(_QWORD *)(v1 + 224);
  v5 = *(_QWORD *)(v4 - 336);
  if ( v3 < 0 )
  {
    if ( FsRtlIsTotalDeviceFailure(v3) && v3 != -2147483626 )
    {
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
      {
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 3), 33, v6, v5, v3);
      }
      v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 24));
      v8 = *((unsigned int *)a1 + 36);
      v9 = v7;
      if ( *(_DWORD *)(*(_QWORD *)(v5 + 112) + 24 * v8 + 16) != 4
        && VMX_IO_RAID5::DetachFaultTolerantMember((VMX_IO_RAID5 *)v5, v8, 1) )
      {
        ++*(_DWORD *)(*(_QWORD *)(v4 - 312) + 168LL);
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 24), v9);
    }
    if ( VmxpIsWorseStatus(v3, *(_DWORD *)(v1 + 96)) )
    {
      *(_DWORD *)(v1 + 96) = v3;
      *(_QWORD *)(v1 + 104) = 0;
    }
  }
  else if ( *(int *)(v1 + 96) >= 0 )
  {
    *(_OWORD *)(v1 + 96) = *((_OWORD *)a1 + 6);
  }
  --*(_DWORD *)(v1 + 128);
  v10 = *(_QWORD *)(v1 + 24);
  v11 = *(_DWORD *)(v1 + 128);
  if ( (*(_BYTE *)(v10 + 10) & 5) != 0 )
    v12 = *(PVOID *)(v10 + 24);
  else
    v12 = MmMapLockedPagesSpecifyCache((PMDL)v10, 0, MmCached, 0, 0, 0x40000010u);
  v13 = *((_QWORD *)a1 + 3);
  if ( (*(_BYTE *)(v13 + 10) & 5) != 0 )
    v14 = *(PVOID *)(v13 + 24);
  else
    v14 = MmMapLockedPagesSpecifyCache((PMDL)v13, 0, MmCached, 0, 0, 0x40000010u);
  VmxpComputeParity(v12, v14, *(_DWORD *)(v1 + 8));
  if ( v11 )
  {
    v15 = *((_DWORD *)a1 + 36);
    do
    {
      do
        *((_DWORD *)a1 + 36) = ++v15;
      while ( v15 == *(_DWORD *)(v4 - 32) );
    }
    while ( v15 == *(_DWORD *)(v1 + 240) );
    v16 = *(_QWORD *)(*(_QWORD *)(v5 + 48) + 8LL * v15);
    *((_QWORD *)a1 + 6) = v16;
    *((_DWORD *)a1 + 3) = 33685512;
    (*(void (__fastcall **)(__int64, struct VMX_TRANSFER_PACKET *))(*(_QWORD *)v16 + 8LL))(v16, a1);
  }
  else
  {
    (*(void (__fastcall **)(__int64))(v1 + 40))(v1);
    v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 24));
    v18 = (_QWORD *)(v5 + 304);
    v19 = v17;
    v20 = *(_QWORD **)(v5 + 304);
    if ( v20 == (_QWORD *)(v5 + 304) )
    {
      *(_BYTE *)(v5 + 266) = 0;
      v21 = 0;
    }
    else
    {
      if ( (_QWORD *)v20[1] != v18 || (v22 = *v20, *(_QWORD **)(*v20 + 8LL) != v20) )
        __fastfail(3u);
      *v18 = v22;
      v21 = v20 - 14;
      *(_QWORD *)(v22 + 8) = v18;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 24), v19);
    if ( v21 )
      ((void (__fastcall *)(_QWORD *))v21[5])(v21);
  }
}

```

## disassembly

```asm
0x140016400  push    rbx
0x140016402  push    rbp
0x140016403  push    rsi
0x140016404  push    rdi
0x140016405  push    r14
0x140016407  push    r15
0x140016409  sub     rsp, 38h
0x14001640d  mov     rbx, [rcx+88h]
0x140016414  mov     rdi, rcx
0x140016417  mov     esi, [rcx+60h]
0x14001641a  mov     r15, [rbx+0E0h]
0x140016421  mov     rbp, [r15-150h]
0x140016428  test    esi, esi
0x14001642a  js      short loc_140016444
0x14001642c  cmp     dword ptr [rbx+60h], 0
0x140016430  jl      loc_14001650E
0x140016436  movups  xmm0, xmmword ptr [rcx+60h]
0x14001643a  movdqu  xmmword ptr [rbx+60h], xmm0
0x14001643f  jmp     loc_14001650E
0x140016444  mov     ecx, esi; Status
0x140016446  call    cs:__imp_FsRtlIsTotalDeviceFailure
0x14001644d  nop     dword ptr [rax+rax+00h]
0x140016452  test    al, al
0x140016454  jz      loc_1400164F5
0x14001645a  cmp     esi, 80000016h
0x140016460  jz      loc_1400164F5
0x140016466  mov     rcx, cs:WPP_GLOBAL_Control
0x14001646d  lea     rax, WPP_GLOBAL_Control
0x140016474  cmp     rcx, rax
0x140016477  jz      short loc_14001649D
0x140016479  test    dword ptr [rcx+2Ch], 1000h
0x140016480  jz      short loc_14001649D
0x140016482  cmp     byte ptr [rcx+29h], 3
0x140016486  jb      short loc_14001649D
0x140016488  mov     rcx, [rcx+18h]
0x14001648c  mov     edx, 21h ; '!'
0x140016491  mov     r9, rbp
0x140016494  mov     [rsp+68h+BugCheckOnFailure], esi
0x140016498  call    WPP_SF_qd
0x14001649d  lea     rcx, [rbp+18h]; SpinLock
0x1400164a1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400164a8  nop     dword ptr [rax+rax+00h]
0x1400164ad  mov     edx, [rdi+90h]; unsigned int
0x1400164b3  mov     r11b, al
0x1400164b6  mov     rcx, [rbp+70h]
0x1400164ba  lea     r8, [rdx+rdx*2]
0x1400164be  cmp     dword ptr [rcx+r8*8+10h], 4
0x1400164c4  jz      short loc_1400164E2
0x1400164c6  mov     r8b, 1; unsigned __int8
0x1400164c9  mov     rcx, rbp; this
0x1400164cc  call    ?DetachFaultTolerantMember@VMX_IO_RAID5@@QEAAEKE@Z; VMX_IO_RAID5::DetachFaultTolerantMember(ulong,uchar)
0x1400164d1  test    al, al
0x1400164d3  jz      short loc_1400164E2
0x1400164d5  mov     rax, [r15-138h]
0x1400164dc  inc     dword ptr [rax+0A8h]
0x1400164e2  mov     dl, r11b; NewIrql
0x1400164e5  lea     rcx, [rbp+18h]; SpinLock
0x1400164e9  call    cs:__imp_KeReleaseSpinLock
0x1400164f0  nop     dword ptr [rax+rax+00h]
0x1400164f5  mov     edx, [rbx+60h]; NTSTATUS
0x1400164f8  mov     ecx, esi; Status
0x1400164fa  call    ?VmxpIsWorseStatus@@YAEJJ@Z; VmxpIsWorseStatus(long,long)
0x1400164ff  test    al, al
0x140016501  jz      short loc_14001650E
0x140016503  mov     [rbx+60h], esi
0x140016506  mov     qword ptr [rbx+68h], 0
0x14001650e  dec     dword ptr [rbx+80h]
0x140016514  mov     rcx, [rbx+18h]; MemoryDescriptorList
0x140016518  mov     r14d, [rbx+80h]
0x14001651f  test    byte ptr [rcx+0Ah], 5
0x140016523  jz      short loc_14001652B
0x140016525  mov     rsi, [rcx+18h]
0x140016529  jmp     short loc_140016553
0x14001652b  xor     r9d, r9d; RequestedAddress
0x14001652e  mov     [rsp+68h+Priority], 40000010h; Priority
0x140016536  xor     edx, edx; AccessMode
0x140016538  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140016540  lea     r8d, [r9+1]; CacheType
0x140016544  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001654b  nop     dword ptr [rax+rax+00h]
0x140016550  mov     rsi, rax
0x140016553  mov     r10, [rdi+18h]
0x140016557  test    byte ptr [r10+0Ah], 5
0x14001655c  jz      short loc_140016564
0x14001655e  mov     rax, [r10+18h]
0x140016562  jmp     short loc_14001658C
0x140016564  xor     r9d, r9d; RequestedAddress
0x140016567  mov     [rsp+68h+Priority], 40000010h; Priority
0x14001656f  xor     edx, edx; AccessMode
0x140016571  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140016579  mov     rcx, r10; MemoryDescriptorList
0x14001657c  lea     r8d, [r9+1]; CacheType
0x140016580  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140016587  nop     dword ptr [rax+rax+00h]
0x14001658c  mov     r8d, [rbx+8]; unsigned int
0x140016590  mov     rdx, rax; void *
0x140016593  mov     rcx, rsi; void *
0x140016596  call    ?VmxpComputeParity@@YAXPEAX0K@Z; VmxpComputeParity(void *,void *,ulong)
0x14001659b  test    r14d, r14d
0x14001659e  jz      short loc_1400165EE
0x1400165a0  mov     eax, [rdi+90h]
0x1400165a6  inc     eax
0x1400165a8  mov     [rdi+90h], eax
0x1400165ae  cmp     eax, [r15-20h]
0x1400165b2  jz      short loc_1400165A6
0x1400165b4  cmp     eax, [rbx+0F0h]
0x1400165ba  jz      short loc_1400165A6
0x1400165bc  mov     ecx, eax
0x1400165be  mov     rdx, rdi
0x1400165c1  mov     rax, [rbp+30h]
0x1400165c5  mov     rcx, [rax+rcx*8]
0x1400165c9  mov     [rdi+30h], rcx
0x1400165cd  mov     dword ptr [rdi+0Ch], 2020008h
0x1400165d4  mov     rax, [rcx]
0x1400165d7  mov     rax, [rax+8]
0x1400165db  call    _guard_dispatch_icall
0x1400165e0  add     rsp, 38h
0x1400165e4  pop     r15
0x1400165e6  pop     r14
0x1400165e8  pop     rdi
0x1400165e9  pop     rsi
0x1400165ea  pop     rbp
0x1400165eb  pop     rbx
0x1400165ec  retn
0x1400165ee  mov     rax, [rbx+28h]
0x1400165f2  mov     rcx, rbx
0x1400165f5  call    _guard_dispatch_icall
0x1400165fa  lea     rcx, [rbp+18h]; SpinLock
0x1400165fe  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140016605  nop     dword ptr [rax+rax+00h]
0x14001660a  lea     rcx, [rbp+130h]
0x140016611  mov     dl, al; NewIrql
0x140016613  mov     rbx, [rcx]
0x140016616  cmp     rbx, rcx
0x140016619  jnz     short loc_140016626
0x14001661b  mov     byte ptr [rbp+10Ah], 0
0x140016622  xor     ebx, ebx
0x140016624  jmp     short loc_140016640
0x140016626  cmp     [rbx+8], rcx
0x14001662a  jnz     short loc_140016666
0x14001662c  mov     rax, [rbx]
0x14001662f  cmp     [rax+8], rbx
0x140016633  jnz     short loc_140016666
0x140016635  mov     [rcx], rax
0x140016638  add     rbx, 0FFFFFFFFFFFFFF90h
0x14001663c  mov     [rax+8], rcx
0x140016640  lea     rcx, [rbp+18h]; SpinLock
0x140016644  call    cs:__imp_KeReleaseSpinLock
0x14001664b  nop     dword ptr [rax+rax+00h]
0x140016650  test    rbx, rbx
0x140016653  jz      short loc_1400165E0
0x140016655  mov     rax, [rbx+28h]
0x140016659  mov     rcx, rbx
0x14001665c  call    _guard_dispatch_icall
0x140016661  jmp     loc_1400165E0
0x140016666  mov     ecx, 3
0x14001666b  int     29h; Win8: RtlFailFast(ecx)
```
