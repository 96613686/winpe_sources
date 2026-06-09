# VhdmpiDiskVolumesAreReady(_DEVICE_OBJECT *,_IRP *)

- ea: `0x1400ca844`
- end: `0x1400cab59`
- name: `?VhdmpiDiskVolumesAreReady@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `789`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x140018f9c`

## callees

- `0x14001bc1c`
- `0x14001c088`
- `0x14001e350`
- `0x14001e958`
- `0x14001fb48`
- `0x140022750`
- `0x140023980`
- `0x140026dec`
- `0x140034514`
- `0x140035d9c`
- `0x140036284`
- `0x1400a9dcc`
- `0x1400bbfb8`
- `0x1400ca844`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x1400caa62`
- `ntoskrnl!KeCancelTimer` at `0x1400caa62`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ca9f4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ca9f4`
- `ntoskrnl!IofCompleteRequest` at `0x1400caaf7`
- `ntoskrnl!IofCompleteRequest` at `0x1400caaf7`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400caae2`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400caae2`

## string_xrefs

- `0x1400ca982`: `VhdmpiDiskVolumesAreReady: DiskNumber - 0x%d`
- `0x1400ca8a0`: `VhdmpiDiskVolumesAreReady: Surface - 0x%p`
- `0x1400ca8b9`: `VhdmpiDiskVolumesAreReady`
- `0x1400ca972`: `VhdmpiDiskVolumesAreReady`

## pseudocode

```c
__int64 __fastcall VhdmpiDiskVolumesAreReady(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  __int64 v3; // rdx
  __int64 v4; // rdi
  int v5; // esi
  __int64 v6; // rbp
  __int64 v7; // rax
  __int64 v8; // rdx
  int v9; // r8d
  int *CurrentStackLocation; // rcx
  IRP *v11; // r15
  int v12; // ecx
  int v13; // eax
  __int64 v14; // rdx
  struct _EX_RUNDOWN_REF *HandleContextFromIrp; // rax

  v4 = VhdmpiAddRundownRefSurfaceByPdo(a1);
  if ( !v4 )
    return 0;
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
    TraceEvents(
      "VhdmpiDiskVolumesAreReady",
      0x2504u,
      4u,
      0x10u,
      "VhdmpiDiskVolumesAreReady: Surface - 0x%p",
      (const void *)v4);
  if ( _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 92), 1, 0) )
  {
    LOBYTE(v3) = 1;
    VhdmpiReleaseRundownRefVirtualDiskSurface(v4, v3);
    return 0;
  }
  v6 = *(_QWORD *)(v4 + 16);
  v7 = VhdmpiDequeueControlDeviceIoctl(v6, 2955548);
  CurrentStackLocation = (int *)a2->Tail.Overlay.CurrentStackLocation;
  v11 = (IRP *)v7;
  if ( CurrentStackLocation[4] != 4 )
    goto LABEL_22;
  CurrentStackLocation = (int *)&a2->AssociatedIrp.MasterIrp->Type;
  if ( !CurrentStackLocation )
    goto LABEL_22;
  v12 = *CurrentStackLocation;
  *(_DWORD *)(v4 + 40) = v12;
  *(_DWORD *)(v6 + 344) = 0;
  if ( (Microsoft_Windows_VHDMPEnableBits & 1) != 0 )
    McTemplateK0zqp_EtwWriteTransfer(
      v12,
      (unsigned int)VhdSurface,
      v9,
      *(_QWORD *)(*(_QWORD *)(v6 + 144) + 120LL),
      *(_DWORD *)(v4 + 40),
      *(_QWORD *)(v6 + 2816));
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
    TraceEvents(
      "VhdmpiDiskVolumesAreReady",
      0x2535u,
      4u,
      0x10u,
      "VhdmpiDiskVolumesAreReady: DiskNumber - 0x%d",
      *(_DWORD *)(v4 + 40));
  LODWORD(CurrentStackLocation) = *(_DWORD *)(*(_QWORD *)(v4 + 296) + 72LL);
  if ( (_DWORD)CurrentStackLocation != 7 )
  {
    if ( (_DWORD)CurrentStackLocation == 2 )
    {
      v13 = RtlStringCchPrintfW((unsigned __int16 *)(v4 + 168), 0x36u, L"\\??\\CDROM%d", *(unsigned int *)(v4 + 40));
      goto LABEL_19;
    }
LABEL_22:
    v5 = -1073741595;
    goto LABEL_23;
  }
  v13 = RtlStringCchPrintfW((unsigned __int16 *)(v4 + 168), 0x36u, L"\\??\\PhysicalDrive%d", *(unsigned int *)(v4 + 40));
LABEL_19:
  v5 = v13;
  if ( v13 < 0
    || (VhdmpiAcquirePassiveLock(v4 + 280),
        RtlInitUnicodeString((PUNICODE_STRING)(v4 + 152), (PCWSTR)(v4 + 168)),
        VhdmpiReleasePassiveLock(v4 + 280),
        v5 = VhdmpiRegisterDependentDiskName(v4),
        v5 < 0) )
  {
LABEL_23:
    if ( v6 && (Microsoft_Windows_VHDMPEnableBits & 2) != 0 )
      McTemplateK0zqp_EtwWriteTransfer(
        (_DWORD)CurrentStackLocation,
        (unsigned int)VhdSurfaceError,
        v9,
        *(_QWORD *)(*(_QWORD *)(v6 + 144) + 120LL),
        v5,
        *(_QWORD *)(v6 + 2816));
  }
  if ( v11 )
  {
    if ( KeCancelTimer((PKTIMER)(v4 + 352)) )
      VhdmpiReleaseRundownRefVirtualDiskSurface(v4, 0);
    if ( _InterlockedIncrement64((volatile signed __int64 *)(v4 + 72)) <= 1 )
      __fastfail(0xEu);
    LOBYTE(v14) = 1;
    VhdmpiReleaseRundownRefVirtualDiskSurface(v4, v14);
    if ( v5 < 0 )
      VhdmpiHaltSurfaceOrWait((struct _VHD_SURFACE *)v4);
    VhdmpiAcquirePassiveLock(v6 + 184);
    --*(_DWORD *)(v6 + 208);
    VhdmpiReleasePassiveLock(v6 + 184);
    VhdmpiReleaseSurface(v4);
    HandleContextFromIrp = (struct _EX_RUNDOWN_REF *)VhdmpiGetHandleContextFromIrp(v11);
    ExReleaseRundownProtection(HandleContextFromIrp + 33);
    v11->IoStatus.Status = v5;
    IofCompleteRequest(v11, 0);
  }
  else
  {
    if ( _InterlockedIncrement64((volatile signed __int64 *)(v4 + 72)) <= 1 )
      __fastfail(0xEu);
    LOBYTE(v8) = 1;
    VhdmpiReleaseRundownRefVirtualDiskSurface(v4, v8);
    if ( v5 < 0 )
      VhdmpiHaltSurfaceOrWait((struct _VHD_SURFACE *)v4);
    VhdmpiReleaseSurface(v4);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400ca844  mov     [rsp+arg_0], rbx
0x1400ca849  mov     [rsp+arg_8], rbp
0x1400ca84e  push    rsi
0x1400ca84f  push    rdi
0x1400ca850  push    r12
0x1400ca852  push    r14
0x1400ca854  push    r15
0x1400ca856  sub     rsp, 30h
0x1400ca85a  mov     rbx, rdx
0x1400ca85d  mov     r12d, 1
0x1400ca863  mov     dl, r12b
0x1400ca866  call    VhdmpiAddRundownRefSurfaceByPdo
0x1400ca86b  mov     rdi, rax
0x1400ca86e  test    rax, rax
0x1400ca871  jnz     short loc_1400CA87A
0x1400ca873  xor     esi, esi
0x1400ca875  jmp     loc_1400CAB3F
0x1400ca87a  mov     eax, cs:dword_1400876D0
0x1400ca880  mov     esi, 4
0x1400ca885  lea     r14d, [rsi+0Ch]
0x1400ca889  cmp     eax, esi
0x1400ca88b  jbe     short loc_1400CA8C8
0x1400ca88d  mov     edx, r14d
0x1400ca890  lea     rcx, dword_1400876D0
0x1400ca897  call    _tlgKeywordOn
0x1400ca89c  test    al, al
0x1400ca89e  jz      short loc_1400CA8C8
0x1400ca8a0  lea     rax, aVhdmpidiskvolu; "VhdmpiDiskVolumesAreReady: Surface - 0x"...
0x1400ca8a7  mov     qword ptr [rsp+58h+var_30], rdi; char
0x1400ca8ac  mov     edx, 2504h; int
0x1400ca8b1  mov     [rsp+58h+var_38], rax; char *
0x1400ca8b6  mov     r9d, r14d; int
0x1400ca8b9  lea     rcx, aVhdmpidiskvolu_0; "VhdmpiDiskVolumesAreReady"
0x1400ca8c0  mov     r8d, esi; int
0x1400ca8c3  call    TraceEvents
0x1400ca8c8  xor     eax, eax
0x1400ca8ca  lock cmpxchg [rdi+5Ch], r12d
0x1400ca8d0  jz      short loc_1400CA8DF
0x1400ca8d2  mov     dl, r12b
0x1400ca8d5  mov     rcx, rdi
0x1400ca8d8  call    VhdmpiReleaseRundownRefVirtualDiskSurface
0x1400ca8dd  jmp     short loc_1400CA873
0x1400ca8df  mov     rbp, [rdi+10h]
0x1400ca8e3  mov     edx, 2D191Ch
0x1400ca8e8  mov     rcx, rbp
0x1400ca8eb  call    VhdmpiDequeueControlDeviceIoctl
0x1400ca8f0  mov     rcx, [rbx+0B8h]
0x1400ca8f7  mov     r15, rax
0x1400ca8fa  cmp     [rcx+10h], esi
0x1400ca8fd  jnz     loc_1400CAA18
0x1400ca903  mov     rcx, [rbx+18h]
0x1400ca907  test    rcx, rcx
0x1400ca90a  jz      loc_1400CAA18
0x1400ca910  mov     ecx, [rcx]
0x1400ca912  mov     [rdi+28h], ecx
0x1400ca915  mov     dword ptr [rbp+158h], 0
0x1400ca91f  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, r12b
0x1400ca926  jz      short loc_1400CA952
0x1400ca928  mov     rax, [rbp+0B00h]
0x1400ca92f  lea     rdx, VhdSurface
0x1400ca936  mov     r9, [rbp+90h]
0x1400ca93d  mov     qword ptr [rsp+58h+var_30], rax
0x1400ca942  mov     eax, [rdi+28h]
0x1400ca945  mov     dword ptr [rsp+58h+var_38], eax
0x1400ca949  mov     r9, [r9+78h]
0x1400ca94d  call    McTemplateK0zqp_EtwWriteTransfer
0x1400ca952  mov     eax, cs:dword_1400876D0
0x1400ca958  cmp     eax, esi
0x1400ca95a  jbe     short loc_1400CA999
0x1400ca95c  mov     rdx, r14
0x1400ca95f  lea     rcx, dword_1400876D0
0x1400ca966  call    _tlgKeywordOn
0x1400ca96b  test    al, al
0x1400ca96d  jz      short loc_1400CA999
0x1400ca96f  mov     eax, [rdi+28h]
0x1400ca972  lea     rcx, aVhdmpidiskvolu_0; "VhdmpiDiskVolumesAreReady"
0x1400ca979  mov     dword ptr [rsp+58h+var_30], eax; char
0x1400ca97d  mov     edx, 2535h; int
0x1400ca982  lea     rax, aVhdmpidiskvolu_1; "VhdmpiDiskVolumesAreReady: DiskNumber -"...
0x1400ca989  mov     r9d, r14d; int
0x1400ca98c  mov     r8d, esi; int
0x1400ca98f  mov     [rsp+58h+var_38], rax; char *
0x1400ca994  call    TraceEvents
0x1400ca999  mov     rax, [rdi+128h]
0x1400ca9a0  lea     r14, [rdi+0A8h]
0x1400ca9a7  mov     ecx, [rax+48h]
0x1400ca9aa  cmp     ecx, 7
0x1400ca9ad  jnz     short loc_1400CA9B8
0x1400ca9af  lea     r8, aPhysicaldriveD; "\\??\\PhysicalDrive%d"
0x1400ca9b6  jmp     short loc_1400CA9C4
0x1400ca9b8  cmp     ecx, 2
0x1400ca9bb  jnz     short loc_1400CAA18
0x1400ca9bd  lea     r8, aCdromD; "\\??\\CDROM%d"
0x1400ca9c4  mov     r9d, [rdi+28h]
0x1400ca9c8  mov     edx, 36h ; '6'; unsigned __int64
0x1400ca9cd  mov     rcx, r14; unsigned __int16 *
0x1400ca9d0  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400ca9d5  mov     esi, eax
0x1400ca9d7  test    eax, eax
0x1400ca9d9  js      short loc_1400CAA1D
0x1400ca9db  lea     rbx, [rdi+118h]
0x1400ca9e2  mov     rcx, rbx
0x1400ca9e5  call    VhdmpiAcquirePassiveLock
0x1400ca9ea  lea     rcx, [rdi+98h]; DestinationString
0x1400ca9f1  mov     rdx, r14; SourceString
0x1400ca9f4  call    cs:__imp_RtlInitUnicodeString
0x1400ca9fb  nop     dword ptr [rax+rax+00h]
0x1400caa00  mov     rcx, rbx
0x1400caa03  call    VhdmpiReleasePassiveLock
0x1400caa08  mov     rcx, rdi
0x1400caa0b  call    VhdmpiRegisterDependentDiskName
0x1400caa10  mov     esi, eax
0x1400caa12  test    eax, eax
0x1400caa14  jns     short loc_1400CAA52
0x1400caa16  jmp     short loc_1400CAA1D
0x1400caa18  mov     esi, 0C00000E5h
0x1400caa1d  test    rbp, rbp
0x1400caa20  jz      short loc_1400CAA52
0x1400caa22  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 2
0x1400caa29  jz      short loc_1400CAA52
0x1400caa2b  mov     r9, [rbp+90h]
0x1400caa32  lea     rdx, VhdSurfaceError
0x1400caa39  mov     rax, [rbp+0B00h]
0x1400caa40  mov     qword ptr [rsp+58h+var_30], rax
0x1400caa45  mov     dword ptr [rsp+58h+var_38], esi
0x1400caa49  mov     r9, [r9+78h]
0x1400caa4d  call    McTemplateK0zqp_EtwWriteTransfer
0x1400caa52  test    r15, r15
0x1400caa55  jz      loc_1400CAB05
0x1400caa5b  lea     rcx, [rdi+160h]; PKTIMER
0x1400caa62  call    cs:__imp_KeCancelTimer
0x1400caa69  nop     dword ptr [rax+rax+00h]
0x1400caa6e  test    al, al
0x1400caa70  jz      short loc_1400CAA7C
0x1400caa72  xor     edx, edx
0x1400caa74  mov     rcx, rdi
0x1400caa77  call    VhdmpiReleaseRundownRefVirtualDiskSurface
0x1400caa7c  mov     rax, r12
0x1400caa7f  lock xadd [rdi+48h], rax
0x1400caa85  add     rax, r12
0x1400caa88  cmp     rax, r12
0x1400caa8b  jg      short loc_1400CAA94
0x1400caa8d  mov     ecx, 0Eh
0x1400caa92  int     29h; Win8: RtlFailFast(ecx)
0x1400caa94  mov     dl, r12b
0x1400caa97  mov     rcx, rdi
0x1400caa9a  call    VhdmpiReleaseRundownRefVirtualDiskSurface
0x1400caa9f  test    esi, esi
0x1400caaa1  jns     short loc_1400CAAAE
0x1400caaa3  mov     dl, r12b
0x1400caaa6  mov     rcx, rdi; struct _VHD_SURFACE *
0x1400caaa9  call    VhdmpiHaltSurfaceOrWait
0x1400caaae  lea     rbx, [rbp+0B8h]
0x1400caab5  mov     rcx, rbx
0x1400caab8  call    VhdmpiAcquirePassiveLock
0x1400caabd  dec     dword ptr [rbp+0D0h]
0x1400caac3  mov     rcx, rbx
0x1400caac6  call    VhdmpiReleasePassiveLock
0x1400caacb  mov     rcx, rdi
0x1400caace  call    VhdmpiReleaseSurface
0x1400caad3  mov     rcx, r15
0x1400caad6  call    VhdmpiGetHandleContextFromIrp
0x1400caadb  lea     rcx, [rax+108h]; RunRef
0x1400caae2  call    cs:__imp_ExReleaseRundownProtection
0x1400caae9  nop     dword ptr [rax+rax+00h]
0x1400caaee  xor     edx, edx; PriorityBoost
0x1400caaf0  mov     [r15+30h], esi
0x1400caaf4  mov     rcx, r15; Irp
0x1400caaf7  call    cs:__imp_IofCompleteRequest
0x1400caafe  nop     dword ptr [rax+rax+00h]
0x1400cab03  jmp     short loc_1400CAB3F
0x1400cab05  mov     rax, r12
0x1400cab08  lock xadd [rdi+48h], rax
0x1400cab0e  add     rax, r12
0x1400cab11  cmp     rax, r12
0x1400cab14  jg      short loc_1400CAB1D
0x1400cab16  mov     ecx, 0Eh
0x1400cab1b  int     29h; Win8: RtlFailFast(ecx)
0x1400cab1d  mov     dl, r12b
0x1400cab20  mov     rcx, rdi
0x1400cab23  call    VhdmpiReleaseRundownRefVirtualDiskSurface
0x1400cab28  test    esi, esi
0x1400cab2a  jns     short loc_1400CAB37
0x1400cab2c  mov     dl, r12b
0x1400cab2f  mov     rcx, rdi; struct _VHD_SURFACE *
0x1400cab32  call    VhdmpiHaltSurfaceOrWait
0x1400cab37  mov     rcx, rdi
0x1400cab3a  call    VhdmpiReleaseSurface
0x1400cab3f  mov     rbx, [rsp+58h+arg_0]
0x1400cab44  mov     eax, esi
0x1400cab46  mov     rbp, [rsp+58h+arg_8]
0x1400cab4b  add     rsp, 30h
0x1400cab4f  pop     r15
0x1400cab51  pop     r14
0x1400cab53  pop     r12
0x1400cab55  pop     rdi
0x1400cab56  pop     rsi
0x1400cab57  retn
```
