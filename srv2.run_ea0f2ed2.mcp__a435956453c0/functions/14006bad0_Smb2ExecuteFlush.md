# Smb2ExecuteFlush

- ea: `0x14006bad0`
- end: `0x14006bd76`
- name: `Smb2ExecuteFlush`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1400748b0`

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
- `0x14006b9c0`
- `0x14006bad0`
- `0x140080758`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14006bd22`
- `ntoskrnl!KeDelayExecutionThread` at `0x14006bd22`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006bb6e`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006bb6e`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14006bb18`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14006bb18`
- `ntoskrnl!IofCallDriver` at `0x14006bd04`
- `ntoskrnl!IofCallDriver` at `0x14006bd04`
- `ntoskrnl!IoReuseIrp` at `0x14006bb48`
- `ntoskrnl!IoReuseIrp` at `0x14006bb48`

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
          &WPP_b1ca86c01a7e3e2db33505aacd354a42_Traceguids,
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
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 16, &WPP_b1ca86c01a7e3e2db33505aacd354a42_Traceguids, a1);
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
0x14006bad0  push    rbx
0x14006bad2  push    rbp
0x14006bad3  push    rsi
0x14006bad4  push    rdi
0x14006bad5  sub     rsp, 38h
0x14006bad9  mov     rsi, [rcx+230h]
0x14006bae0  mov     rdi, rcx
0x14006bae3  mov     qword ptr [rsp+58h+Interval], 0
0x14006baec  mov     rax, [rsi+48h]
0x14006baf0  cmp     byte ptr [rax+0F2h], 0
0x14006baf7  jnz     loc_14006BD4B
0x14006bafd  cmp     cs:Smb2TreatHostAsStableStorage, 0
0x14006bb04  jz      short loc_14006BB14
0x14006bb06  mov     rax, [rsi+38h]
0x14006bb0a  cmp     dword ptr [rax+4Ch], 1
0x14006bb0e  jnz     loc_14006BD4B
0x14006bb14  mov     rcx, [rsi+58h]; FileObject
0x14006bb18  call    cs:__imp_IoGetRelatedDeviceObject
0x14006bb1f  nop     dword ptr [rax+rax+00h]
0x14006bb24  mov     rcx, [rdi+78h]; Irp
0x14006bb28  mov     rbp, rax
0x14006bb2b  mov     r8b, [rax+4Ch]
0x14006bb2f  cmp     [rcx+42h], r8b
0x14006bb33  jl      loc_14006BC5C
0x14006bb39  test    cs:Microsoft_Windows_SMBServerEnableBits, 10h
0x14006bb40  jnz     loc_14006BC5C
0x14006bb46  xor     edx, edx; Iostatus
0x14006bb48  call    cs:__imp_IoReuseIrp
0x14006bb4f  nop     dword ptr [rax+rax+00h]
0x14006bb54  mov     rax, [rsi+58h]
0x14006bb58  mov     rcx, [rdi+78h]
0x14006bb5c  mov     [rcx+0C0h], rax
0x14006bb63  mov     rax, [rdi+40h]
0x14006bb67  mov     rbx, [rax+88h]
0x14006bb6e  call    cs:__imp_KeGetCurrentNodeNumber
0x14006bb75  nop     dword ptr [rax+rax+00h]
0x14006bb7a  movzx   eax, ax
0x14006bb7d  mov     rcx, [rbx+rax*8+8]
0x14006bb82  mov     rax, [rdi+78h]
0x14006bb86  mov     rdx, [rcx+0E0h]
0x14006bb8d  mov     [rax+98h], rdx
0x14006bb94  lea     rdx, Smb2ContinueFlush
0x14006bb9b  mov     rax, [rdi+78h]
0x14006bb9f  mov     byte ptr [rax+40h], 0
0x14006bba3  mov     rax, [rdi+78h]
0x14006bba7  mov     qword ptr [rax+8], 0
0x14006bbaf  mov     rax, [rdi+78h]
0x14006bbb3  mov     dword ptr [rax+30h], 0
0x14006bbba  mov     rax, [rdi+78h]
0x14006bbbe  mov     qword ptr [rax+38h], 0
0x14006bbc6  mov     rax, [rdi+78h]
0x14006bbca  mov     rcx, [rax+0B8h]
0x14006bbd1  mov     [rdi+30h], rdx
0x14006bbd5  lea     rdx, Srv2PostOnCompletionAndClearCancel
0x14006bbdc  mov     rax, [rax+0B8h]
0x14006bbe3  mov     [rax-10h], rdx
0x14006bbe7  mov     dl, 1
0x14006bbe9  mov     [rax-8], rdi
0x14006bbed  mov     byte ptr [rax-45h], 0E0h
0x14006bbf1  mov     byte ptr [rcx-48h], 9
0x14006bbf5  mov     rax, [rsi+58h]
0x14006bbf9  mov     [rcx-18h], rax
0x14006bbfd  mov     [rcx-20h], rbp
0x14006bc01  mov     byte ptr [rcx-46h], 0
0x14006bc05  mov     rcx, rdi
0x14006bc08  call    Srv2MarkWorkItemCancellable
0x14006bc0d  test    eax, eax
0x14006bc0f  jns     loc_14006BCD5
0x14006bc15  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006bc1c  lea     rdx, WPP_GLOBAL_Control
0x14006bc23  cmp     rcx, rdx
0x14006bc26  jz      short loc_14006BC4F
0x14006bc28  test    dword ptr [rcx+2Ch], 800000h
0x14006bc2f  jz      short loc_14006BC4F
0x14006bc31  cmp     byte ptr [rcx+29h], 1
0x14006bc35  jb      short loc_14006BC4F
0x14006bc37  mov     rcx, [rcx+18h]
0x14006bc3b  lea     r8, WPP_b1ca86c01a7e3e2db33505aacd354a42_Traceguids
0x14006bc42  mov     edx, 10h
0x14006bc47  mov     r9, rdi
0x14006bc4a  call    WPP_SF_q
0x14006bc4f  mov     r9d, 12Fh
0x14006bc55  mov     edx, 0C0000120h
0x14006bc5a  jmp     short loc_14006BCB7
0x14006bc5c  mov     dl, r8b
0x14006bc5f  mov     rcx, rdi
0x14006bc62  call    Srv2AllocateLargerIrp
0x14006bc67  mov     ebx, eax
0x14006bc69  test    eax, eax
0x14006bc6b  jns     loc_14006BB54
0x14006bc71  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006bc78  lea     rdx, WPP_GLOBAL_Control
0x14006bc7f  cmp     rcx, rdx
0x14006bc82  jz      short loc_14006BCAF
0x14006bc84  test    dword ptr [rcx+2Ch], 800000h
0x14006bc8b  jz      short loc_14006BCAF
0x14006bc8d  cmp     byte ptr [rcx+29h], 1
0x14006bc91  jb      short loc_14006BCAF
0x14006bc93  mov     rcx, [rcx+18h]
0x14006bc97  lea     r8, WPP_b1ca86c01a7e3e2db33505aacd354a42_Traceguids
0x14006bc9e  mov     edx, 0Fh
0x14006bca3  mov     dword ptr [rsp+58h+var_38], eax
0x14006bca7  mov     r9, rdi
0x14006bcaa  call    WPP_SF_qD
0x14006bcaf  mov     r9d, 101h
0x14006bcb5  mov     edx, ebx
0x14006bcb7  lea     r8, aOnecoreBaseFsR_13; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14006bcbe  mov     rcx, rdi
0x14006bcc1  call    _Smb2SetError
0x14006bcc6  xor     edx, edx
0x14006bcc8  mov     rcx, rdi
0x14006bccb  call    Srv2CompleteWorkItem
0x14006bcd0  jmp     loc_14006BD67
0x14006bcd5  mov     rcx, rdi
0x14006bcd8  call    Srv2ReferenceConnection
0x14006bcdd  lea     rcx, [rdi+248h]
0x14006bce4  mov     [rsp+58h+var_38], 1
0x14006bce9  lea     r9, aSmb2executeflu; "Smb2ExecuteFlush"
0x14006bcf0  mov     r8d, 13Ah
0x14006bcf6  mov     dl, 3
0x14006bcf8  call    SRV2_PERF_ENTER_EX
0x14006bcfd  mov     rdx, [rdi+78h]; Irp
0x14006bd01  mov     rcx, rbp; DeviceObject
0x14006bd04  call    cs:__imp_IofCallDriver
0x14006bd0b  nop     dword ptr [rax+rax+00h]
0x14006bd10  lea     r8, [rsp+58h+Interval]; Interval
0x14006bd15  mov     qword ptr [rsp+58h+Interval], 0FFFFFFFFFFFFD8F0h
0x14006bd1e  xor     edx, edx; Alertable
0x14006bd20  xor     ecx, ecx; WaitMode
0x14006bd22  call    cs:__imp_KeDelayExecutionThread
0x14006bd29  nop     dword ptr [rax+rax+00h]
0x14006bd2e  mov     rcx, rdi
0x14006bd31  call    Srv2MarkWorkItemPending
0x14006bd36  mov     rcx, rdi
0x14006bd39  test    eax, eax
0x14006bd3b  jnz     short loc_14006BD44
0x14006bd3d  call    Smb2GoAsync2
0x14006bd42  jmp     short loc_14006BD67
0x14006bd44  call    Srv2DereferenceWorkItem
0x14006bd49  jmp     short loc_14006BD67
0x14006bd4b  mov     rax, [rcx+78h]
0x14006bd4f  mov     dword ptr [rax+30h], 0
0x14006bd56  mov     rax, [rcx+78h]
0x14006bd5a  mov     qword ptr [rax+8], 0
0x14006bd62  call    Smb2ContinueFlush
0x14006bd67  mov     eax, 103h
0x14006bd6c  add     rsp, 38h
0x14006bd70  pop     rdi
0x14006bd71  pop     rsi
0x14006bd72  pop     rbp
0x14006bd73  pop     rbx
0x14006bd74  retn
```
