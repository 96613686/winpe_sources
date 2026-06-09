# VhdmpiDiskVolumesAreReady(_DEVICE_OBJECT *,_IRP *)

- ea: `0x1400ca854`
- end: `0x1400cab69`
- name: `?VhdmpiDiskVolumesAreReady@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `789`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x140018afc`

## callees

- `0x14001b7fc`
- `0x14001bc68`
- `0x14001df30`
- `0x14001e538`
- `0x14001f728`
- `0x140022330`
- `0x140023560`
- `0x1400269cc`
- `0x140034054`
- `0x1400359ac`
- `0x140035e94`
- `0x1400a9dcc`
- `0x1400bbfc8`
- `0x1400ca854`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x1400caa72`
- `ntoskrnl!KeCancelTimer` at `0x1400caa72`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400caa04`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400caa04`
- `ntoskrnl!IofCompleteRequest` at `0x1400cab07`
- `ntoskrnl!IofCompleteRequest` at `0x1400cab07`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400caaf2`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400caaf2`

## string_xrefs

- `0x1400ca8b0`: `VhdmpiDiskVolumesAreReady: Surface - 0x%p`
- `0x1400ca8c9`: `VhdmpiDiskVolumesAreReady`
- `0x1400ca982`: `VhdmpiDiskVolumesAreReady`
- `0x1400ca992`: `VhdmpiDiskVolumesAreReady: DiskNumber - 0x%d`

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
  __int64 v9; // r8
  int *CurrentStackLocation; // rcx
  IRP *v11; // r15
  int v12; // ecx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // r8
  struct _EX_RUNDOWN_REF *HandleContextFromIrp; // rax

  v4 = VhdmpiAddRundownRefSurfaceByPdo(a1);
  if ( !v4 )
    return 0;
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
    TraceEvents((int)"VhdmpiDiskVolumesAreReady", 9476, 4, 16, "VhdmpiDiskVolumesAreReady: Surface - 0x%p", v4);
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
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
    TraceEvents(
      (int)"VhdmpiDiskVolumesAreReady",
      9525,
      4,
      16,
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
    || (VhdmpiAcquirePassiveLock(v4 + 280, v8, v9),
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
    VhdmpiAcquirePassiveLock(v6 + 184, v15, v16);
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
0x1400ca854  mov     [rsp+arg_0], rbx
0x1400ca859  mov     [rsp+arg_8], rbp
0x1400ca85e  push    rsi
0x1400ca85f  push    rdi
0x1400ca860  push    r12
0x1400ca862  push    r14
0x1400ca864  push    r15
0x1400ca866  sub     rsp, 30h
0x1400ca86a  mov     rbx, rdx
0x1400ca86d  mov     r12d, 1
0x1400ca873  mov     dl, r12b
0x1400ca876  call    VhdmpiAddRundownRefSurfaceByPdo
0x1400ca87b  mov     rdi, rax
0x1400ca87e  test    rax, rax
0x1400ca881  jnz     short loc_1400CA88A
0x1400ca883  xor     esi, esi
0x1400ca885  jmp     loc_1400CAB4F
0x1400ca88a  mov     eax, cs:dword_140087708
0x1400ca890  mov     esi, 4
0x1400ca895  lea     r14d, [rsi+0Ch]
0x1400ca899  cmp     eax, esi
0x1400ca89b  jbe     short loc_1400CA8D8
0x1400ca89d  mov     edx, r14d
0x1400ca8a0  lea     rcx, dword_140087708
0x1400ca8a7  call    _tlgKeywordOn
0x1400ca8ac  test    al, al
0x1400ca8ae  jz      short loc_1400CA8D8
0x1400ca8b0  lea     rax, aVhdmpidiskvolu; "VhdmpiDiskVolumesAreReady: Surface - 0x"...
0x1400ca8b7  mov     qword ptr [rsp+58h+var_30], rdi; char
0x1400ca8bc  mov     edx, 2504h; int
0x1400ca8c1  mov     [rsp+58h+var_38], rax; char *
0x1400ca8c6  mov     r9d, r14d; int
0x1400ca8c9  lea     rcx, aVhdmpidiskvolu_0; "VhdmpiDiskVolumesAreReady"
0x1400ca8d0  mov     r8d, esi; int
0x1400ca8d3  call    TraceEvents
0x1400ca8d8  xor     eax, eax
0x1400ca8da  lock cmpxchg [rdi+5Ch], r12d
0x1400ca8e0  jz      short loc_1400CA8EF
0x1400ca8e2  mov     dl, r12b
0x1400ca8e5  mov     rcx, rdi
0x1400ca8e8  call    VhdmpiReleaseRundownRefVirtualDiskSurface
0x1400ca8ed  jmp     short loc_1400CA883
0x1400ca8ef  mov     rbp, [rdi+10h]
0x1400ca8f3  mov     edx, 2D191Ch
0x1400ca8f8  mov     rcx, rbp
0x1400ca8fb  call    VhdmpiDequeueControlDeviceIoctl
0x1400ca900  mov     rcx, [rbx+0B8h]
0x1400ca907  mov     r15, rax
0x1400ca90a  cmp     [rcx+10h], esi
0x1400ca90d  jnz     loc_1400CAA28
0x1400ca913  mov     rcx, [rbx+18h]
0x1400ca917  test    rcx, rcx
0x1400ca91a  jz      loc_1400CAA28
0x1400ca920  mov     ecx, [rcx]
0x1400ca922  mov     [rdi+28h], ecx
0x1400ca925  mov     dword ptr [rbp+158h], 0
0x1400ca92f  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, r12b
0x1400ca936  jz      short loc_1400CA962
0x1400ca938  mov     rax, [rbp+0B00h]
0x1400ca93f  lea     rdx, VhdSurface
0x1400ca946  mov     r9, [rbp+90h]
0x1400ca94d  mov     qword ptr [rsp+58h+var_30], rax
0x1400ca952  mov     eax, [rdi+28h]
0x1400ca955  mov     dword ptr [rsp+58h+var_38], eax
0x1400ca959  mov     r9, [r9+78h]
0x1400ca95d  call    McTemplateK0zqp_EtwWriteTransfer
0x1400ca962  mov     eax, cs:dword_140087708
0x1400ca968  cmp     eax, esi
0x1400ca96a  jbe     short loc_1400CA9A9
0x1400ca96c  mov     rdx, r14
0x1400ca96f  lea     rcx, dword_140087708
0x1400ca976  call    _tlgKeywordOn
0x1400ca97b  test    al, al
0x1400ca97d  jz      short loc_1400CA9A9
0x1400ca97f  mov     eax, [rdi+28h]
0x1400ca982  lea     rcx, aVhdmpidiskvolu_0; "VhdmpiDiskVolumesAreReady"
0x1400ca989  mov     dword ptr [rsp+58h+var_30], eax; char
0x1400ca98d  mov     edx, 2535h; int
0x1400ca992  lea     rax, aVhdmpidiskvolu_1; "VhdmpiDiskVolumesAreReady: DiskNumber -"...
0x1400ca999  mov     r9d, r14d; int
0x1400ca99c  mov     r8d, esi; int
0x1400ca99f  mov     [rsp+58h+var_38], rax; char *
0x1400ca9a4  call    TraceEvents
0x1400ca9a9  mov     rax, [rdi+128h]
0x1400ca9b0  lea     r14, [rdi+0A8h]
0x1400ca9b7  mov     ecx, [rax+48h]
0x1400ca9ba  cmp     ecx, 7
0x1400ca9bd  jnz     short loc_1400CA9C8
0x1400ca9bf  lea     r8, aPhysicaldriveD; "\\??\\PhysicalDrive%d"
0x1400ca9c6  jmp     short loc_1400CA9D4
0x1400ca9c8  cmp     ecx, 2
0x1400ca9cb  jnz     short loc_1400CAA28
0x1400ca9cd  lea     r8, aCdromD; "\\??\\CDROM%d"
0x1400ca9d4  mov     r9d, [rdi+28h]
0x1400ca9d8  mov     edx, 36h ; '6'; unsigned __int64
0x1400ca9dd  mov     rcx, r14; unsigned __int16 *
0x1400ca9e0  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400ca9e5  mov     esi, eax
0x1400ca9e7  test    eax, eax
0x1400ca9e9  js      short loc_1400CAA2D
0x1400ca9eb  lea     rbx, [rdi+118h]
0x1400ca9f2  mov     rcx, rbx
0x1400ca9f5  call    VhdmpiAcquirePassiveLock
0x1400ca9fa  lea     rcx, [rdi+98h]; DestinationString
0x1400caa01  mov     rdx, r14; SourceString
0x1400caa04  call    cs:__imp_RtlInitUnicodeString
0x1400caa0b  nop     dword ptr [rax+rax+00h]
0x1400caa10  mov     rcx, rbx
0x1400caa13  call    VhdmpiReleasePassiveLock
0x1400caa18  mov     rcx, rdi
0x1400caa1b  call    VhdmpiRegisterDependentDiskName
0x1400caa20  mov     esi, eax
0x1400caa22  test    eax, eax
0x1400caa24  jns     short loc_1400CAA62
0x1400caa26  jmp     short loc_1400CAA2D
0x1400caa28  mov     esi, 0C00000E5h
0x1400caa2d  test    rbp, rbp
0x1400caa30  jz      short loc_1400CAA62
0x1400caa32  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 2
0x1400caa39  jz      short loc_1400CAA62
0x1400caa3b  mov     r9, [rbp+90h]
0x1400caa42  lea     rdx, VhdSurfaceError
0x1400caa49  mov     rax, [rbp+0B00h]
0x1400caa50  mov     qword ptr [rsp+58h+var_30], rax
0x1400caa55  mov     dword ptr [rsp+58h+var_38], esi
0x1400caa59  mov     r9, [r9+78h]
0x1400caa5d  call    McTemplateK0zqp_EtwWriteTransfer
0x1400caa62  test    r15, r15
0x1400caa65  jz      loc_1400CAB15
0x1400caa6b  lea     rcx, [rdi+160h]; PKTIMER
0x1400caa72  call    cs:__imp_KeCancelTimer
0x1400caa79  nop     dword ptr [rax+rax+00h]
0x1400caa7e  test    al, al
0x1400caa80  jz      short loc_1400CAA8C
0x1400caa82  xor     edx, edx
0x1400caa84  mov     rcx, rdi
0x1400caa87  call    VhdmpiReleaseRundownRefVirtualDiskSurface
0x1400caa8c  mov     rax, r12
0x1400caa8f  lock xadd [rdi+48h], rax
0x1400caa95  add     rax, r12
0x1400caa98  cmp     rax, r12
0x1400caa9b  jg      short loc_1400CAAA4
0x1400caa9d  mov     ecx, 0Eh
0x1400caaa2  int     29h; Win8: RtlFailFast(ecx)
0x1400caaa4  mov     dl, r12b
0x1400caaa7  mov     rcx, rdi
0x1400caaaa  call    VhdmpiReleaseRundownRefVirtualDiskSurface
0x1400caaaf  test    esi, esi
0x1400caab1  jns     short loc_1400CAABE
0x1400caab3  mov     dl, r12b
0x1400caab6  mov     rcx, rdi; struct _VHD_SURFACE *
0x1400caab9  call    VhdmpiHaltSurfaceOrWait
0x1400caabe  lea     rbx, [rbp+0B8h]
0x1400caac5  mov     rcx, rbx
0x1400caac8  call    VhdmpiAcquirePassiveLock
0x1400caacd  dec     dword ptr [rbp+0D0h]
0x1400caad3  mov     rcx, rbx
0x1400caad6  call    VhdmpiReleasePassiveLock
0x1400caadb  mov     rcx, rdi
0x1400caade  call    VhdmpiReleaseSurface
0x1400caae3  mov     rcx, r15
0x1400caae6  call    VhdmpiGetHandleContextFromIrp
0x1400caaeb  lea     rcx, [rax+108h]; RunRef
0x1400caaf2  call    cs:__imp_ExReleaseRundownProtection
0x1400caaf9  nop     dword ptr [rax+rax+00h]
0x1400caafe  xor     edx, edx; PriorityBoost
0x1400cab00  mov     [r15+30h], esi
0x1400cab04  mov     rcx, r15; Irp
0x1400cab07  call    cs:__imp_IofCompleteRequest
0x1400cab0e  nop     dword ptr [rax+rax+00h]
0x1400cab13  jmp     short loc_1400CAB4F
0x1400cab15  mov     rax, r12
0x1400cab18  lock xadd [rdi+48h], rax
0x1400cab1e  add     rax, r12
0x1400cab21  cmp     rax, r12
0x1400cab24  jg      short loc_1400CAB2D
0x1400cab26  mov     ecx, 0Eh
0x1400cab2b  int     29h; Win8: RtlFailFast(ecx)
0x1400cab2d  mov     dl, r12b
0x1400cab30  mov     rcx, rdi
0x1400cab33  call    VhdmpiReleaseRundownRefVirtualDiskSurface
0x1400cab38  test    esi, esi
0x1400cab3a  jns     short loc_1400CAB47
0x1400cab3c  mov     dl, r12b
0x1400cab3f  mov     rcx, rdi; struct _VHD_SURFACE *
0x1400cab42  call    VhdmpiHaltSurfaceOrWait
0x1400cab47  mov     rcx, rdi
0x1400cab4a  call    VhdmpiReleaseSurface
0x1400cab4f  mov     rbx, [rsp+58h+arg_0]
0x1400cab54  mov     eax, esi
0x1400cab56  mov     rbp, [rsp+58h+arg_8]
0x1400cab5b  add     rsp, 30h
0x1400cab5f  pop     r15
0x1400cab61  pop     r14
0x1400cab63  pop     r12
0x1400cab65  pop     rdi
0x1400cab66  pop     rsi
0x1400cab67  retn
```
