# Smb2ExecuteFlush

- ea: `0x14006ba80`
- end: `0x14006bd26`
- name: `Smb2ExecuteFlush`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140074860`

## callees

- `0x140005070`
- `0x140006ad0`
- `0x140007090`
- `0x140007400`
- `0x140008190`
- `0x1400125d0`
- `0x140015000`
- `0x1400186f0`
- `0x1400222ec`
- `0x140022958`
- `0x14006b970`
- `0x14006ba80`
- `0x140080708`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14006bcd2`
- `ntoskrnl!KeDelayExecutionThread` at `0x14006bcd2`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006bb1e`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006bb1e`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14006bac8`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14006bac8`
- `ntoskrnl!IofCallDriver` at `0x14006bcb4`
- `ntoskrnl!IofCallDriver` at `0x14006bcb4`
- `ntoskrnl!IoReuseIrp` at `0x14006baf8`
- `ntoskrnl!IoReuseIrp` at `0x14006baf8`

## pseudocode

```c
__int64 __fastcall Smb2ExecuteFlush(__int64 a1)
{
  __int64 v1; // rsi
  PDEVICE_OBJECT RelatedDeviceObject; // rax
  __int64 v4; // rdx
  IRP *v5; // rcx
  struct _DEVICE_OBJECT *v6; // rbp
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 (__fastcall *v10)(__int64, __int64, __int64); // rdx
  __int64 v11; // rax
  __int64 v12; // r9
  __int64 v13; // rdx
  int LargerIrp; // eax
  unsigned int v15; // ebx
  __int64 v16; // rdx
  char v18; // [rsp+20h] [rbp-38h]
  union _LARGE_INTEGER Interval; // [rsp+60h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 560);
  Interval.QuadPart = 0;
  if ( *(_BYTE *)(*(_QWORD *)(v1 + 72) + 242LL)
    || Smb2TreatHostAsStableStorage && *(_DWORD *)(*(_QWORD *)(v1 + 56) + 76LL) != 1 )
  {
    *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 120) + 8LL) = 0;
    Smb2ContinueFlush();
    return 259;
  }
  RelatedDeviceObject = IoGetRelatedDeviceObject(*(PFILE_OBJECT *)(v1 + 88));
  v5 = *(IRP **)(a1 + 120);
  v6 = RelatedDeviceObject;
  if ( v5->StackCount < RelatedDeviceObject->StackSize || (Microsoft_Windows_SMBServerEnableBits & 0x10) != 0 )
  {
    LOBYTE(v4) = RelatedDeviceObject->StackSize;
    LargerIrp = Srv2AllocateLargerIrp(a1, v4);
    v15 = LargerIrp;
    if ( LargerIrp < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          WPP_b1ca86c01a7e3e2db33505aacd354a42_Traceguids,
          a1,
          LargerIrp);
      }
      v12 = 257;
      v13 = v15;
      goto LABEL_19;
    }
  }
  else
  {
    IoReuseIrp(v5, 0);
  }
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 192LL) = *(_QWORD *)(v1 + 88);
  v7 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 136LL);
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 152LL) = *(_QWORD *)(*(_QWORD *)(v7 + 8LL * KeGetCurrentNodeNumber() + 8) + 224LL);
  *(_BYTE *)(*(_QWORD *)(a1 + 120) + 64LL) = 0;
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 8LL) = 0;
  *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL) = 0;
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 56LL) = 0;
  v8 = *(_QWORD *)(a1 + 120);
  v9 = *(_QWORD *)(v8 + 184);
  *(_QWORD *)(a1 + 48) = Smb2ContinueFlush;
  v10 = Srv2PostOnCompletionAndClearCancel;
  v11 = *(_QWORD *)(v8 + 184);
  *(_QWORD *)(v11 - 16) = Srv2PostOnCompletionAndClearCancel;
  LOBYTE(v10) = 1;
  *(_QWORD *)(v11 - 8) = a1;
  *(_BYTE *)(v11 - 69) = -32;
  *(_BYTE *)(v9 - 72) = 9;
  *(_QWORD *)(v9 - 24) = *(_QWORD *)(v1 + 88);
  *(_QWORD *)(v9 - 32) = v6;
  *(_BYTE *)(v9 - 70) = 0;
  if ( (int)Srv2MarkWorkItemCancellable(a1, v10) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_b1ca86c01a7e3e2db33505aacd354a42_Traceguids, a1);
    }
    v12 = 303;
    v13 = 3221225760LL;
LABEL_19:
    Smb2SetError(a1, v13, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\flush.c", v12);
    Srv2CompleteWorkItem(a1, 0);
    return 259;
  }
  Srv2ReferenceConnection(a1);
  v18 = 1;
  LOBYTE(v16) = 3;
  SRV2_PERF_ENTER_EX(a1 + 584, v16, 314, "Smb2ExecuteFlush", v18);
  IofCallDriver(v6, *(PIRP *)(a1 + 120));
  Interval.QuadPart = -10000;
  KeDelayExecutionThread(0, 0, &Interval);
  if ( (unsigned int)Srv2MarkWorkItemPending(a1) )
    Srv2DereferenceWorkItem(a1);
  else
    Smb2GoAsync2(a1);
  return 259;
}

```

## disassembly

```asm
0x14006ba80  push    rbx
0x14006ba82  push    rbp
0x14006ba83  push    rsi
0x14006ba84  push    rdi
0x14006ba85  sub     rsp, 38h
0x14006ba89  mov     rsi, [rcx+230h]
0x14006ba90  mov     rdi, rcx
0x14006ba93  mov     qword ptr [rsp+58h+Interval], 0
0x14006ba9c  mov     rax, [rsi+48h]
0x14006baa0  cmp     byte ptr [rax+0F2h], 0
0x14006baa7  jnz     loc_14006BCFB
0x14006baad  cmp     cs:Smb2TreatHostAsStableStorage, 0
0x14006bab4  jz      short loc_14006BAC4
0x14006bab6  mov     rax, [rsi+38h]
0x14006baba  cmp     dword ptr [rax+4Ch], 1
0x14006babe  jnz     loc_14006BCFB
0x14006bac4  mov     rcx, [rsi+58h]; FileObject
0x14006bac8  call    cs:__imp_IoGetRelatedDeviceObject
0x14006bacf  nop     dword ptr [rax+rax+00h]
0x14006bad4  mov     rcx, [rdi+78h]; Irp
0x14006bad8  mov     rbp, rax
0x14006badb  mov     r8b, [rax+4Ch]
0x14006badf  cmp     [rcx+42h], r8b
0x14006bae3  jl      loc_14006BC0C
0x14006bae9  test    cs:Microsoft_Windows_SMBServerEnableBits, 10h
0x14006baf0  jnz     loc_14006BC0C
0x14006baf6  xor     edx, edx; Iostatus
0x14006baf8  call    cs:__imp_IoReuseIrp
0x14006baff  nop     dword ptr [rax+rax+00h]
0x14006bb04  mov     rax, [rsi+58h]
0x14006bb08  mov     rcx, [rdi+78h]
0x14006bb0c  mov     [rcx+0C0h], rax
0x14006bb13  mov     rax, [rdi+40h]
0x14006bb17  mov     rbx, [rax+88h]
0x14006bb1e  call    cs:__imp_KeGetCurrentNodeNumber
0x14006bb25  nop     dword ptr [rax+rax+00h]
0x14006bb2a  movzx   eax, ax
0x14006bb2d  mov     rcx, [rbx+rax*8+8]
0x14006bb32  mov     rax, [rdi+78h]
0x14006bb36  mov     rdx, [rcx+0E0h]
0x14006bb3d  mov     [rax+98h], rdx
0x14006bb44  lea     rdx, Smb2ContinueFlush
0x14006bb4b  mov     rax, [rdi+78h]
0x14006bb4f  mov     byte ptr [rax+40h], 0
0x14006bb53  mov     rax, [rdi+78h]
0x14006bb57  mov     qword ptr [rax+8], 0
0x14006bb5f  mov     rax, [rdi+78h]
0x14006bb63  mov     dword ptr [rax+30h], 0
0x14006bb6a  mov     rax, [rdi+78h]
0x14006bb6e  mov     qword ptr [rax+38h], 0
0x14006bb76  mov     rax, [rdi+78h]
0x14006bb7a  mov     rcx, [rax+0B8h]
0x14006bb81  mov     [rdi+30h], rdx
0x14006bb85  lea     rdx, Srv2PostOnCompletionAndClearCancel
0x14006bb8c  mov     rax, [rax+0B8h]
0x14006bb93  mov     [rax-10h], rdx
0x14006bb97  mov     dl, 1
0x14006bb99  mov     [rax-8], rdi
0x14006bb9d  mov     byte ptr [rax-45h], 0E0h
0x14006bba1  mov     byte ptr [rcx-48h], 9
0x14006bba5  mov     rax, [rsi+58h]
0x14006bba9  mov     [rcx-18h], rax
0x14006bbad  mov     [rcx-20h], rbp
0x14006bbb1  mov     byte ptr [rcx-46h], 0
0x14006bbb5  mov     rcx, rdi
0x14006bbb8  call    Srv2MarkWorkItemCancellable
0x14006bbbd  test    eax, eax
0x14006bbbf  jns     loc_14006BC85
0x14006bbc5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006bbcc  lea     rdx, WPP_GLOBAL_Control
0x14006bbd3  cmp     rcx, rdx
0x14006bbd6  jz      short loc_14006BBFF
0x14006bbd8  test    dword ptr [rcx+2Ch], 800000h
0x14006bbdf  jz      short loc_14006BBFF
0x14006bbe1  cmp     byte ptr [rcx+29h], 1
0x14006bbe5  jb      short loc_14006BBFF
0x14006bbe7  mov     rcx, [rcx+18h]
0x14006bbeb  lea     r8, WPP_b1ca86c01a7e3e2db33505aacd354a42_Traceguids
0x14006bbf2  mov     edx, 10h
0x14006bbf7  mov     r9, rdi
0x14006bbfa  call    WPP_SF_q
0x14006bbff  mov     r9d, 12Fh
0x14006bc05  mov     edx, 0C0000120h
0x14006bc0a  jmp     short loc_14006BC67
0x14006bc0c  mov     dl, r8b
0x14006bc0f  mov     rcx, rdi
0x14006bc12  call    Srv2AllocateLargerIrp
0x14006bc17  mov     ebx, eax
0x14006bc19  test    eax, eax
0x14006bc1b  jns     loc_14006BB04
0x14006bc21  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006bc28  lea     rdx, WPP_GLOBAL_Control
0x14006bc2f  cmp     rcx, rdx
0x14006bc32  jz      short loc_14006BC5F
0x14006bc34  test    dword ptr [rcx+2Ch], 800000h
0x14006bc3b  jz      short loc_14006BC5F
0x14006bc3d  cmp     byte ptr [rcx+29h], 1
0x14006bc41  jb      short loc_14006BC5F
0x14006bc43  mov     rcx, [rcx+18h]
0x14006bc47  lea     r8, WPP_b1ca86c01a7e3e2db33505aacd354a42_Traceguids
0x14006bc4e  mov     edx, 0Fh
0x14006bc53  mov     dword ptr [rsp+58h+var_38], eax
0x14006bc57  mov     r9, rdi
0x14006bc5a  call    WPP_SF_qD
0x14006bc5f  mov     r9d, 101h
0x14006bc65  mov     edx, ebx
0x14006bc67  lea     r8, aOnecoreBaseFsR_13; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14006bc6e  mov     rcx, rdi
0x14006bc71  call    _Smb2SetError
0x14006bc76  xor     edx, edx
0x14006bc78  mov     rcx, rdi
0x14006bc7b  call    Srv2CompleteWorkItem
0x14006bc80  jmp     loc_14006BD17
0x14006bc85  mov     rcx, rdi
0x14006bc88  call    Srv2ReferenceConnection
0x14006bc8d  lea     rcx, [rdi+248h]
0x14006bc94  mov     [rsp+58h+var_38], 1
0x14006bc99  lea     r9, aSmb2executeflu; "Smb2ExecuteFlush"
0x14006bca0  mov     r8d, 13Ah
0x14006bca6  mov     dl, 3
0x14006bca8  call    SRV2_PERF_ENTER_EX
0x14006bcad  mov     rdx, [rdi+78h]; Irp
0x14006bcb1  mov     rcx, rbp; DeviceObject
0x14006bcb4  call    cs:__imp_IofCallDriver
0x14006bcbb  nop     dword ptr [rax+rax+00h]
0x14006bcc0  lea     r8, [rsp+58h+Interval]; Interval
0x14006bcc5  mov     qword ptr [rsp+58h+Interval], 0FFFFFFFFFFFFD8F0h
0x14006bcce  xor     edx, edx; Alertable
0x14006bcd0  xor     ecx, ecx; WaitMode
0x14006bcd2  call    cs:__imp_KeDelayExecutionThread
0x14006bcd9  nop     dword ptr [rax+rax+00h]
0x14006bcde  mov     rcx, rdi
0x14006bce1  call    Srv2MarkWorkItemPending
0x14006bce6  mov     rcx, rdi
0x14006bce9  test    eax, eax
0x14006bceb  jnz     short loc_14006BCF4
0x14006bced  call    Smb2GoAsync2
0x14006bcf2  jmp     short loc_14006BD17
0x14006bcf4  call    Srv2DereferenceWorkItem
0x14006bcf9  jmp     short loc_14006BD17
0x14006bcfb  mov     rax, [rcx+78h]
0x14006bcff  mov     dword ptr [rax+30h], 0
0x14006bd06  mov     rax, [rcx+78h]
0x14006bd0a  mov     qword ptr [rax+8], 0
0x14006bd12  call    Smb2ContinueFlush
0x14006bd17  mov     eax, 103h
0x14006bd1c  add     rsp, 38h
0x14006bd20  pop     rdi
0x14006bd21  pop     rsi
0x14006bd22  pop     rbp
0x14006bd23  pop     rbx
0x14006bd24  retn
```
