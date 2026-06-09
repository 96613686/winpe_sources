# UdfVerifyVolume

- ea: `0x140003148`
- end: `0x1400039f5`
- name: `UdfVerifyVolume`
- size: `2221`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140049f20`

## callees

- `0x1400030e0`
- `0x140003148`
- `0x140004340`
- `0x140008790`
- `0x14000b200`
- `0x14000b808`
- `0x14000ca10`
- `0x14000ca54`
- `0x14000cad4`
- `0x140018bc8`
- `0x14001bc30`
- `0x14001c5a0`
- `0x14002c164`
- `0x14002c250`
- `0x14002c774`
- `0x14002ce08`
- `0x14002cf5c`
- `0x14002eb9c`
- `0x14002f26c`
- `0x14002f818`
- `0x14002fbd8`
- `0x14002fd68`
- `0x140030f44`
- `0x140031b04`
- `0x140035f44`
- `0x1400483a8`
- `0x1400491d0`
- `0x14004ce50`
- `0x140052864`
- `0x140054560`
- `0x140059004`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140003907`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003922`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003946`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000396a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003985`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003907`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003922`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003946`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000396a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003985`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400038b4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400038d6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400038e9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001cb28`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001cb49`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001cb5d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400038b4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400038d6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400038e9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001cb28`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001cb49`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001cb5d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000325c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000325c`
- `ntoskrnl!RtlCompareMemory` at `0x1400036e4`
- `ntoskrnl!RtlCompareMemory` at `0x1400036e4`

## pseudocode

```c
__int64 __fastcall UdfVerifyVolume(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  __int64 v4; // rsi
  NTSTATUS FileSetDescriptor; // edi
  __int64 v6; // r9
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  bool v11; // al
  _WORD *v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // r10
  __int64 v16; // r9
  int v17; // eax
  __int64 v18; // rcx
  int v19; // edx
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // r9
  __int64 v23; // rcx
  unsigned __int16 v25[2]; // [rsp+58h] [rbp-F0h] BYREF
  int v26; // [rsp+5Ch] [rbp-ECh] BYREF
  PVOID v27; // [rsp+60h] [rbp-E8h] BYREF
  int v28; // [rsp+68h] [rbp-E0h] BYREF
  PVOID v29; // [rsp+70h] [rbp-D8h] BYREF
  PVOID v30; // [rsp+78h] [rbp-D0h] BYREF
  PVOID P; // [rsp+80h] [rbp-C8h] BYREF
  PVOID v32; // [rsp+88h] [rbp-C0h] BYREF
  void *Buf2; // [rsp+90h] [rbp-B8h] BYREF
  PIO_SECURITY_CONTEXT SecurityContext; // [rsp+98h] [rbp-B0h]
  __int64 v35; // [rsp+A0h] [rbp-A8h]
  PERESOURCE Resource; // [rsp+A8h] [rbp-A0h]
  IRP *v37; // [rsp+B0h] [rbp-98h]
  __int64 v38; // [rsp+B8h] [rbp-90h]
  __int128 v39; // [rsp+C0h] [rbp-88h]
  char Source2[48]; // [rsp+D0h] [rbp-78h] BYREF

  v37 = a2;
  v38 = a1;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
  v35 = (__int64)&CurrentStackLocation->Parameters.QueryDirectory.FileName[23];
  v4 = v35;
  v29 = 0;
  P = 0;
  v32 = 0;
  v27 = 0;
  Buf2 = 0;
  v30 = 0;
  v26 = *(_DWORD *)(v35 + 64);
  v39 = 0;
  v25[0] = 0;
  v28 = 0;
  FileSetDescriptor = 0;
  *(_QWORD *)(a1 + 32) = *(_QWORD *)&SecurityContext->DesiredAccess;
  *(_DWORD *)(a1 + 28) |= 0x2000u;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200000) != 0 )
  {
    WPP_SF_q(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      42,
      WPP_808b98bda8443bb0d475e79494837b3d_Traceguids,
      v4);
  }
  ExAcquireResourceExclusiveLite(&::Resource, 1u);
  Resource = (PERESOURCE)(v4 + 1480);
  UdfAcquireResource(a1, v4 + 1480, 0, 0);
  if ( UdfNoRemounts || (unsigned int)(*(_DWORD *)(v4 + 52) - 3) <= 1 )
    goto LABEL_80;
  if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 8) + 16LL) + 48LL) & 2) == 0 )
  {
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200000) != 0 )
    {
      WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 43, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
    }
    goto LABEL_81;
  }
  v7 = *(_QWORD *)&SecurityContext->DesiredAccess;
  if ( (*(_DWORD *)(v7 + 52) & 1) == 0 )
    goto LABEL_23;
  v8 = 149504;
  if ( *(_DWORD *)(v7 + 72) != 2 )
    v8 = 477184;
  FileSetDescriptor = UdfPerformDevIoCtrl(v7, v8, *(_QWORD *)(v4 + 24), 0, 0, &v26, 4);
  if ( FileSetDescriptor >= 0 )
  {
LABEL_23:
    if ( *((_QWORD *)&v39 + 1) != 4 )
      v26 = 0;
    if ( (*(_DWORD *)(v4 + 48) & 0x204000) == 0x200000 )
    {
      v7 = *(_DWORD *)(*(_QWORD *)(v4 + 104) + 4LL) & 2;
      if ( (*(_DWORD *)(v4 + 48) & 0x20000000) == 0 )
      {
        v11 = (_DWORD)v7 != 0;
LABEL_30:
        if ( !v11 )
        {
          FileSetDescriptor = UdfSeqCacheSyncCache(v4);
          if ( FileSetDescriptor < 0 )
            goto LABEL_80;
        }
        goto LABEL_32;
      }
      if ( !(_DWORD)v7 )
      {
        v11 = 0;
        goto LABEL_30;
      }
    }
LABEL_32:
    if ( v26 && *(_DWORD *)(v4 + 64) == v26 && (*(_DWORD *)(v4 + 48) & 2) != 0 )
    {
LABEL_67:
      if ( *(_DWORD *)(v4 + 52) != 2 )
        goto LABEL_81;
      if ( (*(_DWORD *)(v4 + 48) & 0x4000) == 0 )
      {
        LOBYTE(v6) = 1;
        if ( !(unsigned __int8)UdfPrepareDeviceForWrite(v7, *(_QWORD *)(a1 + 32), *(unsigned int *)(v4 + 84), v6) )
        {
          v9 = *(_QWORD *)&WPP_GLOBAL_Control;
          if ( *(int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200000) == 0 )
          {
            goto LABEL_22;
          }
          v10 = 51;
          goto LABEL_21;
        }
      }
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200000) != 0 )
      {
        WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 52, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
      }
      *(_DWORD *)(v4 + 52) = 2;
      *(_DWORD *)(*(_QWORD *)&SecurityContext->DesiredAccess + 48LL) &= ~2u;
      FileSetDescriptor = 0;
      goto LABEL_81;
    }
    if ( (*(_DWORD *)(v4 + 2128) & 2) != 0 || *(_DWORD *)(v4 + 2016) )
    {
      if ( (int)UdfFindAnchorVolumeDescriptor(a1, v4, &P) < 0 )
      {
        v9 = *(_QWORD *)&WPP_GLOBAL_Control;
        if ( *(int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200000) == 0 )
        {
          goto LABEL_22;
        }
        v10 = 46;
        goto LABEL_21;
      }
      v12 = P;
      if ( (int)UdfFindVolumeDescriptors(
                  a1,
                  v4,
                  (unsigned int *)P + 4,
                  (__int64 *)&v29,
                  (__int64 *)&v32,
                  (__int64 *)&v27) < 0 )
      {
        v9 = *(_QWORD *)&WPP_GLOBAL_Control;
        if ( *(int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200000) == 0 )
        {
          goto LABEL_22;
        }
        v10 = 47;
        goto LABEL_21;
      }
      if ( (int)UdfCompletePcb(a1, (_DWORD *)v4, (__int64)v29) < 0 )
      {
        v9 = *(_QWORD *)&WPP_GLOBAL_Control;
        if ( *(int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200000) == 0 )
        {
          goto LABEL_22;
        }
        v10 = 48;
        goto LABEL_21;
      }
      if ( !(unsigned __int8)UdfEquivalentPcb(v13, v29, *(_QWORD *)(v4 + 16)) )
      {
        v9 = *(_QWORD *)&WPP_GLOBAL_Control;
        if ( *(int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200000) == 0 )
        {
          goto LABEL_22;
        }
        v10 = 49;
        goto LABEL_21;
      }
      if ( ((*(_DWORD *)(v4 + 84) - 7) & 0xFFFFFFF7) != 0
        || !(unsigned __int8)UdfIsMediaWriteProtected(a1, *(_QWORD *)(v4 + 24)) )
      {
        UdfDeletePcb(v29);
        v29 = 0;
        if ( (*(_BYTE *)(*(_QWORD *)(v4 + 16) + 6LL) & 2) == 0 )
          UdfFindLogicalVolumeIntegrityDescriptor(a1, v4, (char *)v27 + 432, &Buf2);
        FileSetDescriptor = UdfFindFileSetDescriptor(a1, v4, (__int64)v27 + 248, (__int64 *)&v30);
        if ( FileSetDescriptor >= 0 )
        {
          UdfUpdateVolumeLabel(a1, Source2, v25, (char *)v30 + 112);
          UdfUpdateVolumeSerialNumber(v14, &v28, v30);
          if ( *(_DWORD *)(*(_QWORD *)(v4 + 288) + 184LL) != *(_DWORD *)(v15 + 404)
            || (v16 = *(_QWORD *)(v4 + 1424), (v16 == 0) != (Buf2 == 0))
            || Buf2
            && ((v17 = *((_DWORD *)Buf2 + 18), *(_DWORD *)(v16 + 72) != v17)
             || memcmp(
                  *(const void **)(v4 + 1424),
                  Buf2,
                  *((unsigned int *)Buf2 + 19) + 80LL + 4LL * (unsigned int)(2 * v17)))
            || (v18 = *(_QWORD *)(v4 + 8), *(_DWORD *)(v18 + 24) != v28)
            || (v19 = v25[0], *(_WORD *)(v18 + 6) != v25[0])
            || *(_WORD *)(v4 + 2140) != v12[3]
            || v19 != RtlCompareMemory((const void *)(v18 + 32), Source2, v25[0]) )
          {
            v9 = *(_QWORD *)&WPP_GLOBAL_Control;
            if ( *(int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200000) == 0 )
            {
              goto LABEL_22;
            }
            v10 = 50;
            goto LABEL_21;
          }
          goto LABEL_67;
        }
      }
    }
LABEL_80:
    FileSetDescriptor = -1073741806;
    goto LABEL_81;
  }
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 44, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
  }
  if ( (CurrentStackLocation->Flags & 1) != 0 )
  {
    v9 = *(_QWORD *)&WPP_GLOBAL_Control;
    if ( *(int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200000) == 0 )
    {
      goto LABEL_22;
    }
    v10 = 45;
LABEL_21:
    WPP_SF_(*(_QWORD *)(v9 + 24), v10, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
LABEL_22:
    FileSetDescriptor = -1073741806;
  }
LABEL_81:
  *(_DWORD *)(v4 + 64) = v26;
  v20 = *(_DWORD *)(v4 + 52);
  if ( v20 )
  {
    if ( v20 == 2 && FileSetDescriptor == -1073741806 )
    {
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200000) != 0 )
      {
        WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 53, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
      }
      UdfFlushVolume(a1, v4, 0, 0, 1, 0);
      UdfFspClose(v4);
      if ( (*(_DWORD *)(v4 + 48) & 0x400) != 0 )
        UdfResetVmcb(v4 + 984);
      UdfTearDownAllocationSupport(a1, v4);
      UdfTearDownRmwSupport(v21, v4);
      UdfSeqCacheTearDown(a1, v4);
      UdfMarkAllScbsForVerify(a1);
      if ( (*(_DWORD *)(v4 + 48) & 0x4000) == 0 )
      {
        UdfAcquireResource(a1, v4 + 2024, 0, 0);
        UdfKillCleanVolumeTimer(v4);
        LOBYTE(v22) = 1;
        UdfToggleMediaEjectDisable(v23, v4, 0, v22);
        ExReleaseResourceLite((PERESOURCE)(v4 + 2024));
      }
      *(_DWORD *)(v4 + 52) = 0;
    }
  }
  else
  {
    FileSetDescriptor = -1073741806;
  }
  ExReleaseResourceLite(Resource);
  ExReleaseResourceLite(&::Resource);
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( v32 )
  {
    ExFreePoolWithTag(v32, 0);
    v32 = 0;
  }
  if ( v27 )
  {
    ExFreePoolWithTag(v27, 0);
    v27 = 0;
  }
  if ( Buf2 )
    ExFreePoolWithTag(Buf2, 0);
  if ( v30 )
    ExFreePoolWithTag(v30, 0);
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200000) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 54, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
  }
  UdfCompleteRequest((void *)a1, v37, FileSetDescriptor);
  return (unsigned int)FileSetDescriptor;
}

```

## disassembly

```asm
0x140003148  mov     r11, rsp
0x14000314b  mov     [r11+18h], rbx
0x14000314f  push    rsi
0x140003150  push    rdi
0x140003151  push    r13
0x140003153  push    r14
0x140003155  push    r15
0x140003157  sub     rsp, 120h
0x14000315e  mov     rax, cs:__security_cookie
0x140003165  xor     rax, rsp
0x140003168  mov     [rsp+148h+var_38], rax
0x140003170  mov     [rsp+148h+var_98], rdx
0x140003178  mov     r13, rcx
0x14000317b  mov     [rsp+148h+var_90], rcx
0x140003183  mov     rbx, [rdx+0B8h]
0x14000318a  mov     rcx, [rbx+8]
0x14000318e  mov     [rsp+148h+var_B0], rcx
0x140003196  mov     rsi, [rbx+10h]
0x14000319a  add     rsi, 170h
0x1400031a1  mov     [rsp+148h+var_A8], rsi
0x1400031a9  mov     [rsp+148h+var_D8], 0
0x1400031b2  mov     qword ptr [r11-0C8h], 0
0x1400031bd  mov     qword ptr [r11-0C0h], 0
0x1400031c8  mov     [rsp+148h+var_E8], 0
0x1400031d1  mov     qword ptr [r11-0B8h], 0
0x1400031dc  mov     [rsp+148h+var_D0], 0
0x1400031e5  mov     eax, [rsi+40h]
0x1400031e8  mov     [rsp+148h+var_EC], eax
0x1400031ec  mov     [rsp+148h+var_F4], 0
0x1400031f1  xorps   xmm0, xmm0
0x1400031f4  movups  [rsp+148h+var_88], xmm0
0x1400031fc  xor     eax, eax
0x1400031fe  mov     [rsp+148h+var_F0], ax
0x140003203  mov     [rsp+148h+var_E0], eax
0x140003207  xor     edi, edi
0x140003209  mov     [rsp+148h+var_F8], edi
0x14000320d  mov     rax, [rcx+10h]
0x140003211  mov     [r13+20h], rax
0x140003215  bts     dword ptr [r13+1Ch], 0Dh
0x14000321b  lea     rax, WPP_GLOBAL_Control
0x140003222  mov     rcx, cs:WPP_GLOBAL_Control
0x140003229  mov     r14d, 200000h
0x14000322f  lea     r15, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x140003236  cmp     rcx, rax
0x140003239  jz      short loc_140003253
0x14000323b  test    [rcx+2Ch], r14d
0x14000323f  jz      short loc_140003253
0x140003241  lea     edx, [rdi+2Ah]
0x140003244  mov     r9, rsi
0x140003247  mov     r8, r15
0x14000324a  mov     rcx, [rcx+18h]
0x14000324e  call    WPP_SF_q
0x140003253  mov     dl, 1; Wait
0x140003255  lea     rcx, Resource; Resource
0x14000325c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140003263  nop     dword ptr [rax+rax+00h]
0x140003268  nop
0x140003269  lea     rax, [rsi+5C8h]
0x140003270  mov     [rsp+148h+Resource], rax
0x140003278  xor     r9d, r9d
0x14000327b  xor     r8d, r8d
0x14000327e  mov     rdx, rax
0x140003281  mov     rcx, r13
0x140003284  call    UdfAcquireResource
0x140003289  mov     [rsp+148h+var_F4], 1
0x14000328e  cmp     cs:UdfNoRemounts, 0
0x140003295  jnz     loc_1400037BE
0x14000329b  mov     eax, [rsi+34h]
0x14000329e  sub     eax, 3
0x1400032a1  cmp     eax, 1
0x1400032a4  jbe     loc_1400037BE
0x1400032aa  mov     rax, [rsi+8]
0x1400032ae  mov     rcx, [rax+10h]
0x1400032b2  mov     eax, [rcx+30h]
0x1400032b5  test    al, 2
0x1400032b7  jnz     short loc_1400032F0
0x1400032b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400032c0  lea     rdx, WPP_GLOBAL_Control
0x1400032c7  cmp     rcx, rdx
0x1400032ca  jz      loc_1400037C7
0x1400032d0  test    [rcx+2Ch], r14d
0x1400032d4  jz      loc_1400037C7
0x1400032da  mov     edx, 2Bh ; '+'
0x1400032df  mov     r8, r15
0x1400032e2  mov     rcx, [rcx+18h]
0x1400032e6  call    WPP_SF_
0x1400032eb  jmp     loc_1400037C7
0x1400032f0  mov     rcx, [rsp+148h+var_B0]
0x1400032f8  mov     rcx, [rcx+10h]
0x1400032fc  mov     eax, [rcx+34h]
0x1400032ff  test    al, 1
0x140003301  jz      loc_1400033C6
0x140003307  mov     edx, 24800h
0x14000330c  mov     eax, 74800h
0x140003311  cmp     dword ptr [rcx+48h], 2
0x140003315  cmovnz  edx, eax
0x140003318  lea     rax, [rsp+148h+var_88]
0x140003320  mov     [rsp+148h+var_100], rax
0x140003325  mov     [rsp+148h+var_108], 1
0x14000332a  mov     [rsp+148h+var_118], 4
0x140003332  lea     rax, [rsp+148h+var_EC]
0x140003337  mov     qword ptr [rsp+148h+var_120], rax
0x14000333c  mov     dword ptr [rsp+148h+var_128], 0
0x140003344  xor     r9d, r9d
0x140003347  mov     r8, [rsi+18h]
0x14000334b  call    UdfPerformDevIoCtrl
0x140003350  mov     edi, eax
0x140003352  mov     [rsp+148h+var_F8], eax
0x140003356  test    eax, eax
0x140003358  jns     short loc_1400033C6
0x14000335a  mov     rax, cs:WPP_GLOBAL_Control
0x140003361  lea     rdx, WPP_GLOBAL_Control
0x140003368  cmp     rax, rdx
0x14000336b  jz      short loc_140003384
0x14000336d  test    [rax+2Ch], r14d
0x140003371  jz      short loc_140003384
0x140003373  mov     edx, 2Ch ; ','
0x140003378  mov     r8, r15
0x14000337b  mov     rcx, [rax+18h]
0x14000337f  call    WPP_SF_
0x140003384  test    byte ptr [rbx+2], 1
0x140003388  jz      loc_1400037C7
0x14000338e  mov     rcx, cs:WPP_GLOBAL_Control
0x140003395  lea     rbx, WPP_GLOBAL_Control
0x14000339c  cmp     rcx, rbx
0x14000339f  jz      short loc_1400033B8
0x1400033a1  test    [rcx+2Ch], r14d
0x1400033a5  jz      short loc_1400033B8
0x1400033a7  mov     edx, 2Dh ; '-'
0x1400033ac  mov     r8, r15
0x1400033af  mov     rcx, [rcx+18h]
0x1400033b3  call    WPP_SF_
0x1400033b8  mov     edi, 0C0000012h
0x1400033bd  mov     [rsp+148h+var_F8], edi
0x1400033c1  jmp     loc_1400037CE
0x1400033c6  cmp     qword ptr [rsp+148h+var_88+8], 4
0x1400033cf  jz      short loc_1400033D9
0x1400033d1  mov     [rsp+148h+var_EC], 0
0x1400033d9  mov     edx, [rsi+30h]
0x1400033dc  mov     eax, edx
0x1400033de  and     eax, 204000h
0x1400033e3  cmp     eax, r14d
0x1400033e6  jnz     short loc_14000341F
0x1400033e8  mov     rax, [rsi+68h]
0x1400033ec  mov     ecx, [rax+4]
0x1400033ef  and     ecx, 2
0x1400033f2  bt      edx, 1Dh
0x1400033f6  jb      short loc_1400033FF
0x1400033f8  test    ecx, ecx
0x1400033fa  setnz   al
0x1400033fd  jmp     short loc_140003405
0x1400033ff  test    ecx, ecx
0x140003401  jnz     short loc_14000341F
0x140003403  xor     al, al
0x140003405  test    al, al
0x140003407  jnz     short loc_14000341F
0x140003409  mov     rcx, rsi
0x14000340c  call    UdfSeqCacheSyncCache
0x140003411  mov     edi, eax
0x140003413  mov     [rsp+148h+var_F8], eax
0x140003417  test    eax, eax
0x140003419  js      loc_1400037BE
0x14000341f  mov     eax, [rsp+148h+var_EC]
0x140003423  test    eax, eax
0x140003425  jz      short loc_140003437
0x140003427  cmp     [rsi+40h], eax
0x14000342a  jnz     short loc_140003437
0x14000342c  mov     eax, [rsi+30h]
0x14000342f  test    al, 2
0x140003431  jnz     loc_1400036F9
0x140003437  mov     eax, [rsi+850h]
0x14000343d  test    al, 2
0x14000343f  jnz     short loc_14000344E
0x140003441  cmp     dword ptr [rsi+7E0h], 0
0x140003448  jz      loc_1400037BE
0x14000344e  lea     r8, [rsp+148h+P]
0x140003456  mov     rdx, rsi
0x140003459  mov     rcx, r13
0x14000345c  call    UdfFindAnchorVolumeDescriptor
0x140003461  mov     [rsp+148h+var_F8], eax
0x140003465  test    eax, eax
0x140003467  jns     short loc_140003494
0x140003469  mov     rcx, cs:WPP_GLOBAL_Control
0x140003470  lea     rbx, WPP_GLOBAL_Control
0x140003477  cmp     rcx, rbx
0x14000347a  jz      loc_1400033B8
0x140003480  test    [rcx+2Ch], r14d
0x140003484  jz      loc_1400033B8
0x14000348a  mov     edx, 2Eh ; '.'
0x14000348f  jmp     loc_1400033AC
0x140003494  mov     rbx, [rsp+148h+P]
0x14000349c  lea     r8, [rbx+10h]
0x1400034a0  lea     rax, [rsp+148h+var_E8]
0x1400034a5  mov     qword ptr [rsp+148h+var_120], rax
0x1400034aa  lea     rax, [rsp+148h+var_C0]
0x1400034b2  mov     qword ptr [rsp+148h+var_128], rax
0x1400034b7  lea     r9, [rsp+148h+var_D8]
0x1400034bc  mov     rdx, rsi
0x1400034bf  mov     rcx, r13
0x1400034c2  call    UdfFindVolumeDescriptors
0x1400034c7  mov     [rsp+148h+var_F8], eax
0x1400034cb  test    eax, eax
0x1400034cd  jns     short loc_1400034FA
0x1400034cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400034d6  lea     rbx, WPP_GLOBAL_Control
0x1400034dd  cmp     rcx, rbx
0x1400034e0  jz      loc_1400033B8
0x1400034e6  test    [rcx+2Ch], r14d
0x1400034ea  jz      loc_1400033B8
0x1400034f0  mov     edx, 2Fh ; '/'
0x1400034f5  jmp     loc_1400033AC
0x1400034fa  mov     r8, [rsp+148h+var_D8]
0x1400034ff  mov     rdx, rsi
0x140003502  mov     rcx, r13
0x140003505  call    UdfCompletePcb
0x14000350a  mov     [rsp+148h+var_F8], eax
0x14000350e  test    eax, eax
0x140003510  jns     short loc_14000353D
0x140003512  mov     rcx, cs:WPP_GLOBAL_Control
0x140003519  lea     rbx, WPP_GLOBAL_Control
0x140003520  cmp     rcx, rbx
0x140003523  jz      loc_1400033B8
0x140003529  test    [rcx+2Ch], r14d
0x14000352d  jz      loc_1400033B8
0x140003533  mov     edx, 30h ; '0'
0x140003538  jmp     loc_1400033AC
0x14000353d  mov     r8, [rsi+10h]
0x140003541  mov     rdx, [rsp+148h+var_D8]
0x140003546  call    UdfEquivalentPcb
0x14000354b  test    al, al
0x14000354d  jnz     short loc_14000357A
0x14000354f  mov     rcx, cs:WPP_GLOBAL_Control
0x140003556  lea     rbx, WPP_GLOBAL_Control
0x14000355d  cmp     rcx, rbx
0x140003560  jz      loc_1400033B8
0x140003566  test    [rcx+2Ch], r14d
0x14000356a  jz      loc_1400033B8
0x140003570  mov     edx, 31h ; '1'
0x140003575  jmp     loc_1400033AC
0x14000357a  mov     eax, [rsi+54h]
0x14000357d  sub     eax, 7
0x140003580  test    eax, 0FFFFFFF7h
0x140003585  jnz     short loc_14000359B
0x140003587  mov     rdx, [rsi+18h]
0x14000358b  mov     rcx, r13
0x14000358e  call    UdfIsMediaWriteProtected
0x140003593  test    al, al
0x140003595  jnz     loc_1400037BE
0x14000359b  mov     rcx, [rsp+148h+var_D8]; P
0x1400035a0  call    UdfDeletePcb
0x1400035a5  mov     [rsp+148h+var_D8], 0
0x1400035ae  mov     rax, [rsi+10h]
0x1400035b2  test    byte ptr [rax+6], 2
0x1400035b6  jnz     short loc_1400035D7
0x1400035b8  mov     r8, [rsp+148h+var_E8]
0x1400035bd  add     r8, 1B0h
0x1400035c4  lea     r9, [rsp+148h+Buf2]
0x1400035cc  mov     rdx, rsi
0x1400035cf  mov     rcx, r13
0x1400035d2  call    UdfFindLogicalVolumeIntegrityDescriptor
0x1400035d7  mov     r8, [rsp+148h+var_E8]
0x1400035dc  add     r8, 0F8h
0x1400035e3  lea     r9, [rsp+148h+var_D0]
0x1400035e8  mov     rdx, rsi
0x1400035eb  mov     rcx, r13
0x1400035ee  call    UdfFindFileSetDescriptor
0x1400035f3  mov     edi, eax
0x1400035f5  mov     [rsp+148h+var_F8], eax
0x1400035f9  test    eax, eax
0x1400035fb  js      loc_1400037BE
0x140003601  mov     r9, [rsp+148h+var_D0]
0x140003606  add     r9, 70h ; 'p'
0x14000360a  lea     r8, [rsp+148h+var_F0]
0x14000360f  lea     rdx, [rsp+148h+Source2]
0x140003617  mov     rcx, r13
0x14000361a  call    UdfUpdateVolumeLabel
0x14000361f  mov     r10, [rsp+148h+var_D0]
0x140003624  mov     r8, r10
0x140003627  lea     rdx, [rsp+148h+var_E0]
0x14000362c  call    UdfUpdateVolumeSerialNumber
0x140003631  mov     rdx, [rsi+120h]
0x140003638  mov     eax, [r10+194h]
0x14000363f  cmp     [rdx+0B8h], eax
0x140003645  jnz     loc_140003793
0x14000364b  mov     r9, [rsi+590h]
0x140003652  xor     ecx, ecx
0x140003654  test    r9, r9
0x140003657  setz    cl
0x14000365a  xor     eax, eax
0x14000365c  mov     rdx, [rsp+148h+Buf2]; Buf2
0x140003664  test    rdx, rdx
0x140003667  setz    al
0x14000366a  cmp     ecx, eax
0x14000366c  jnz     loc_140003793
0x140003672  test    rdx, rdx
0x140003675  jz      short loc_1400036A2
0x140003677  mov     eax, [rdx+48h]
0x14000367a  cmp     [r9+48h], eax
0x14000367e  jnz     loc_140003793
0x140003684  lea     ecx, [rax+rax]
  ... truncated ...
```
