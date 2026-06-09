# RaidCreateUnit

- ea: `0x140011638`
- end: `0x14001196e`
- name: `RaidCreateUnit`
- size: `822`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140027450`

## callees

- `0x140003df0`
- `0x140004cb4`
- `0x140010190`
- `0x140011638`
- `0x140011974`
- `0x140011e8c`
- `0x140011f40`
- `0x140012174`
- `0x1400bb9e0`
- `0x14014b400`
- `0x14014b800`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x1400117d0`
- `ntoskrnl!IoDeleteDevice` at `0x1400117d0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400118d0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400118d0`
- `ntoskrnl!IoCreateDevice` at `0x1400116dd`
- `ntoskrnl!IoCreateDevice` at `0x1400116dd`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140011684`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140011684`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x140011671`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x140011671`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011837`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011837`

## pseudocode

```c
NTSTATUS __fastcall RaidCreateUnit(__int64 a1, _QWORD *a2)
{
  __int64 RecommendedSharedDataAlignment; // rdi
  ULONG MaximumProcessorCount; // eax
  __int64 v5; // r14
  int v6; // r12d
  NTSTATUS result; // eax
  char *DeviceExtension; // rbx
  size_t v9; // r14
  __int64 v10; // rsi
  void *v11; // rcx
  __int64 v12; // r15
  char *v13; // rdi
  void *v14; // rcx
  char v15; // cl
  int Resources; // esi
  KIRQL v17; // r14
  __int64 v18; // rax
  __int16 v19; // cx
  _DWORD *v20; // rax
  _DWORD *v21; // rcx
  __int64 v22; // rax
  _QWORD *v23; // rax
  PDEVICE_OBJECT DeviceObject; // [rsp+40h] [rbp-29h] BYREF
  _QWORD *v25; // [rsp+48h] [rbp-21h]
  _OWORD v26[2]; // [rsp+50h] [rbp-19h] BYREF
  __int128 v27; // [rsp+70h] [rbp+7h]
  __int64 v28; // [rsp+80h] [rbp+17h]

  v25 = a2;
  DeviceObject = 0;
  RecommendedSharedDataAlignment = KeGetRecommendedSharedDataAlignment();
  MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
  v5 = MaximumProcessorCount;
  v6 = (*(_BYTE *)(a1 + 112) & 2) != 0 ? RecommendedSharedDataAlignment + 216 : 0;
  result = IoCreateDevice(
             *(PDRIVER_OBJECT *)(*(_QWORD *)(a1 + 8) + 8LL),
             RecommendedSharedDataAlignment + v6 + ((MaximumProcessorCount + 57) << 6),
             0,
             0x2Du,
             0x180u,
             0,
             &DeviceObject);
  if ( result >= 0 )
  {
    DeviceExtension = (char *)DeviceObject->DeviceExtension;
    RaidZeroUnit(DeviceExtension);
    v9 = v5 << 6;
    v10 = ~(RecommendedSharedDataAlignment - 1);
    v11 = (void *)(v10 & (unsigned __int64)&DeviceExtension[RecommendedSharedDataAlignment + 3647]);
    *((_QWORD *)DeviceExtension + 5) = v11;
    v12 = (unsigned int)RecommendedSharedDataAlignment;
    memset_0(v11, 0, v9);
    v13 = DeviceExtension + 32;
    if ( v6 )
    {
      v14 = (void *)(v10 & (v12 + v9 + *((_QWORD *)DeviceExtension + 5) - 1LL));
      *(_QWORD *)v13 = v14;
      memset_0(v14, 0, 0xD8u);
    }
    *((_QWORD *)DeviceExtension + 3) = a1;
    *((_QWORD *)DeviceExtension + 1) = DeviceObject;
    *(_WORD *)(DeviceExtension + 1861) = 256;
    DeviceExtension[1863] = 1;
    DeviceObject->Flags |= 0x10u;
    DeviceObject->Flags |= 0x1000u;
    *(_DWORD *)(*((_QWORD *)DeviceExtension + 1) + 152LL) = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 152LL);
    v15 = -1;
    *((_DWORD *)DeviceExtension + 14) = 0;
    if ( ((*(unsigned __int8 *)(a1 + 4956) + 3) & 0xFFFFFFFC) <= 0xFF )
      v15 = (*(_BYTE *)(a1 + 4956) + 3) & 0xFC;
    DeviceExtension[1860] = v15;
    Resources = RaidUnitAllocateResources((__int64)DeviceExtension);
    if ( Resources >= 0 )
    {
      RaidUnitSetInitialQueueDepth(DeviceExtension);
      DeviceExtension[757] = 1;
      RiDisableDeviceQueueFastPath(DeviceExtension + 720, 0);
      memset(v26, 0, sizeof(v26));
      v28 = 0;
      v27 = 0;
      if ( *(_QWORD *)v13 && (unsigned __int8)RaidIsUnitControlSupported(DeviceExtension, 31) )
      {
        v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*(_QWORD *)v13 + 24LL));
        *(_DWORD *)(*(_QWORD *)v13 + 80LL) |= 0x20u;
        *(_QWORD *)&v26[0] = 0x3800000038LL;
        DWORD2(v26[0]) = 2;
        if ( (unsigned int)Feature_Servicing_perLunLockingEnable__private_IsEnabledDeviceUsageNoInline() )
        {
          v18 = *((_QWORD *)DeviceExtension + 3);
          WORD4(v27) = 1;
          HIDWORD(v27) = 4;
          v19 = *(_WORD *)(v18 + 56);
          LOWORD(v28) = *((_WORD *)DeviceExtension + 52);
          BYTE2(v28) = DeviceExtension[106];
          WORD5(v27) = v19;
        }
        v20 = (_DWORD *)*((_QWORD *)DeviceExtension + 3);
        if ( *v20 == 1094997074 )
        {
          v21 = v20 + 90;
        }
        else
        {
          v21 = v20 + 44;
          if ( *v20 != 1314275652 )
            v21 = 0;
        }
        RaCallMiniportUnitControl(v21, 31, v26);
        KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)v13 + 24LL), v17);
      }
      v22 = *((_QWORD *)DeviceExtension + 3);
      DeviceExtension[505] &= ~0x80u;
      DeviceExtension[504] &= ~0x80u;
      *((_QWORD *)DeviceExtension + 234) = 0;
      if ( *(_QWORD *)(v22 + 5024)
        && (*(_BYTE *)(v22 + 108) & 8) == 0
        && !_InterlockedCompareExchange((volatile signed __int32 *)DeviceExtension + 904, 1, 0) )
      {
        RaidAdapterPoFxActivateComponent(*((_QWORD *)DeviceExtension + 3), 0, 0);
      }
      v23 = v25;
      *((_DWORD *)DeviceExtension + 482) = 10;
      *((_DWORD *)DeviceExtension + 483) = 25;
      *((_DWORD *)DeviceExtension + 484) = 125;
      *v23 = DeviceExtension;
    }
    else
    {
      IoDeleteDevice(DeviceObject);
    }
    return Resources;
  }
  return result;
}

```

## disassembly

```asm
0x140011638  mov     [rsp-8+arg_10], rbx
0x14001163d  push    rbp
0x14001163e  push    rsi
0x14001163f  push    rdi
0x140011640  push    r12
0x140011642  push    r13
0x140011644  push    r14
0x140011646  push    r15
0x140011648  lea     rbp, [rsp-27h]
0x14001164d  sub     rsp, 90h
0x140011654  mov     rax, cs:__security_cookie
0x14001165b  xor     rax, rsp
0x14001165e  mov     [rbp+57h+var_38], rax
0x140011662  mov     [rbp+57h+var_78], rdx
0x140011666  mov     r13, rcx
0x140011669  mov     [rbp+57h+var_80], 0
0x140011671  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x140011678  nop     dword ptr [rax+rax+00h]
0x14001167d  mov     ecx, 0FFFFh; GroupNumber
0x140011682  mov     edi, eax
0x140011684  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x14001168b  nop     dword ptr [rax+rax+00h]
0x140011690  mov     r8b, [r13+70h]
0x140011694  lea     ecx, [rdi+0D8h]
0x14001169a  and     r8b, 2
0x14001169e  mov     r14d, eax
0x1400116a1  neg     r8b
0x1400116a4  lea     rax, [rbp+57h+var_80]
0x1400116a8  mov     [rsp+0C0h+DeviceObject], rax; DeviceObject
0x1400116ad  mov     r9d, 2Dh ; '-'; DeviceType
0x1400116b3  sbb     r12d, r12d
0x1400116b6  mov     [rsp+0C0h+Exclusive], 0; Exclusive
0x1400116bb  and     r12d, ecx
0x1400116be  mov     [rsp+0C0h+DeviceCharacteristics], 180h; DeviceCharacteristics
0x1400116c6  mov     rcx, [r13+8]
0x1400116ca  lea     edx, [r14+39h]
0x1400116ce  shl     edx, 6
0x1400116d1  xor     r8d, r8d; DeviceName
0x1400116d4  add     edx, r12d
0x1400116d7  add     edx, edi; DeviceExtensionSize
0x1400116d9  mov     rcx, [rcx+8]; DriverObject
0x1400116dd  call    cs:__imp_IoCreateDevice
0x1400116e4  nop     dword ptr [rax+rax+00h]
0x1400116e9  test    eax, eax
0x1400116eb  js      loc_140011946
0x1400116f1  mov     rax, [rbp+57h+var_80]
0x1400116f5  mov     rbx, [rax+40h]
0x1400116f9  mov     rcx, rbx
0x1400116fc  call    RaidZeroUnit
0x140011701  lea     rcx, [rbx+0E3Fh]
0x140011708  shl     r14, 6
0x14001170c  add     rcx, rdi
0x14001170f  lea     rsi, [rdi-1]
0x140011713  not     rsi
0x140011716  mov     r8, r14; Size
0x140011719  and     rcx, rsi; void *
0x14001171c  xor     edx, edx; Val
0x14001171e  mov     [rbx+28h], rcx
0x140011722  mov     r15d, edi
0x140011725  call    memset_0
0x14001172a  lea     rdi, [rbx+20h]
0x14001172e  test    r12d, r12d
0x140011731  jz      short loc_140011753
0x140011733  mov     rcx, [rbx+28h]
0x140011737  xor     edx, edx; Val
0x140011739  dec     rcx
0x14001173c  mov     r8d, 0D8h; Size
0x140011742  add     rcx, r14
0x140011745  add     rcx, r15
0x140011748  and     rcx, rsi; void *
0x14001174b  mov     [rdi], rcx
0x14001174e  call    memset_0
0x140011753  mov     [rbx+18h], r13
0x140011757  xor     r15d, r15d
0x14001175a  mov     rax, [rbp+57h+var_80]
0x14001175e  mov     [rbx+8], rax
0x140011762  mov     word ptr [rbx+745h], 100h
0x14001176b  lea     r12d, [r15+1]
0x14001176f  mov     [rbx+747h], r12b
0x140011776  mov     rax, [rbp+57h+var_80]
0x14001177a  or      dword ptr [rax+30h], 10h
0x14001177e  mov     rax, [rbp+57h+var_80]
0x140011782  bts     dword ptr [rax+30h], 0Ch
0x140011787  mov     rax, [r13+8]
0x14001178b  mov     rcx, [rbx+8]
0x14001178f  mov     eax, [rax+98h]
0x140011795  mov     [rcx+98h], eax
0x14001179b  mov     ecx, 0FFh
0x1400117a0  mov     [rbx+38h], r15d
0x1400117a4  movzx   eax, byte ptr [r13+135Ch]
0x1400117ac  add     eax, 3
0x1400117af  and     eax, 0FFFFFFFCh
0x1400117b2  cmp     eax, ecx
0x1400117b4  ja      short loc_1400117B8
0x1400117b6  mov     cl, al
0x1400117b8  mov     [rbx+744h], cl
0x1400117be  mov     rcx, rbx
0x1400117c1  call    RaidUnitAllocateResources
0x1400117c6  mov     esi, eax
0x1400117c8  test    eax, eax
0x1400117ca  jns     short loc_1400117E1
0x1400117cc  mov     rcx, [rbp+57h+var_80]; DeviceObject
0x1400117d0  call    cs:__imp_IoDeleteDevice
0x1400117d7  nop     dword ptr [rax+rax+00h]
0x1400117dc  jmp     loc_140011944
0x1400117e1  mov     rcx, rbx
0x1400117e4  call    RaidUnitSetInitialQueueDepth
0x1400117e9  lea     rcx, [rbx+2D0h]
0x1400117f0  xor     edx, edx
0x1400117f2  mov     [rcx+25h], r12b
0x1400117f6  call    RiDisableDeviceQueueFastPath
0x1400117fb  xorps   xmm0, xmm0
0x1400117fe  xor     eax, eax
0x140011800  movups  [rbp+57h+var_70], xmm0
0x140011804  mov     [rbp+57h+var_40], rax
0x140011808  movups  [rbp+57h+var_60], xmm0
0x14001180c  movups  [rbp+57h+var_50], xmm0
0x140011810  cmp     [rdi], r15
0x140011813  jz      loc_1400118DC
0x140011819  lea     r13d, [rax+1Fh]
0x14001181d  mov     rcx, rbx
0x140011820  mov     edx, r13d
0x140011823  call    RaidIsUnitControlSupported
0x140011828  test    al, al
0x14001182a  jz      loc_1400118DC
0x140011830  mov     rcx, [rdi]
0x140011833  add     rcx, 18h; SpinLock
0x140011837  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001183e  nop     dword ptr [rax+rax+00h]
0x140011843  mov     rcx, [rdi]
0x140011846  mov     r14b, al
0x140011849  lea     eax, [r13+19h]
0x14001184d  or      dword ptr [rcx+50h], 20h
0x140011851  mov     dword ptr [rbp+57h+var_70], eax
0x140011854  mov     dword ptr [rbp+57h+var_70+4], eax
0x140011857  mov     dword ptr [rbp+57h+var_70+8], 2
0x14001185e  call    Feature_Servicing_perLunLockingEnable__private_IsEnabledDeviceUsageNoInline
0x140011863  test    eax, eax
0x140011865  jz      short loc_140011891
0x140011867  mov     rax, [rbx+18h]
0x14001186b  mov     word ptr [rbp+57h+var_50+8], r12w
0x140011870  mov     dword ptr [rbp+57h+var_50+0Ch], 4
0x140011877  movzx   ecx, word ptr [rax+38h]
0x14001187b  mov     al, [rbx+68h]
0x14001187e  mov     byte ptr [rbp+57h+var_40], al
0x140011881  mov     al, [rbx+69h]
0x140011884  mov     byte ptr [rbp+57h+var_40+1], al
0x140011887  mov     al, [rbx+6Ah]
0x14001188a  mov     byte ptr [rbp+57h+var_40+2], al
0x14001188d  mov     word ptr [rbp+57h+var_50+0Ah], cx
0x140011891  mov     rax, [rbx+18h]
0x140011895  mov     ecx, [rax]
0x140011897  cmp     ecx, 41445452h
0x14001189d  jnz     short loc_1400118A8
0x14001189f  lea     rcx, [rax+168h]
0x1400118a6  jmp     short loc_1400118BA
0x1400118a8  cmp     ecx, 4E564144h
0x1400118ae  lea     rcx, [rax+0B0h]
0x1400118b5  jz      short loc_1400118BA
0x1400118b7  mov     rcx, r15
0x1400118ba  lea     r8, [rbp+57h+var_70]
0x1400118be  mov     edx, r13d
0x1400118c1  call    RaCallMiniportUnitControl
0x1400118c6  mov     rcx, [rdi]
0x1400118c9  mov     dl, r14b; NewIrql
0x1400118cc  add     rcx, 18h; SpinLock
0x1400118d0  call    cs:__imp_KeReleaseSpinLock
0x1400118d7  nop     dword ptr [rax+rax+00h]
0x1400118dc  mov     rax, [rbx+18h]
0x1400118e0  and     byte ptr [rbx+1F9h], 7Fh
0x1400118e7  and     byte ptr [rbx+1F8h], 7Fh
0x1400118ee  mov     [rbx+750h], r15
0x1400118f5  cmp     [rax+13A0h], r15
0x1400118fc  jz      short loc_14001191F
0x1400118fe  test    byte ptr [rax+6Ch], 8
0x140011902  jnz     short loc_14001191F
0x140011904  xor     eax, eax
0x140011906  lock cmpxchg [rbx+0E20h], r12d
0x14001190f  jnz     short loc_14001191F
0x140011911  mov     rcx, [rbx+18h]
0x140011915  xor     r8d, r8d
0x140011918  xor     edx, edx
0x14001191a  call    RaidAdapterPoFxActivateComponent
0x14001191f  mov     rax, [rbp+57h+var_78]
0x140011923  mov     dword ptr [rbx+788h], 0Ah
0x14001192d  mov     dword ptr [rbx+78Ch], 19h
0x140011937  mov     dword ptr [rbx+790h], 7Dh ; '}'
0x140011941  mov     [rax], rbx
0x140011944  mov     eax, esi
0x140011946  mov     rcx, [rbp+57h+var_38]
0x14001194a  xor     rcx, rsp; StackCookie
0x14001194d  call    __security_check_cookie
0x140011952  mov     rbx, [rsp+0C0h+arg_10]
0x14001195a  add     rsp, 90h
0x140011961  pop     r15
0x140011963  pop     r14
0x140011965  pop     r13
0x140011967  pop     r12
0x140011969  pop     rdi
0x14001196a  pop     rsi
0x14001196b  pop     rbp
0x14001196c  retn
```
