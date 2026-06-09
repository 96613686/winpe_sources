# Smb2ExecuteQueryDirectory

- ea: `0x14006e1d0`
- end: `0x14006e57f`
- name: `Smb2ExecuteQueryDirectory`
- size: `943`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400748b0`

## callees

- `0x140005070`
- `0x140007400`
- `0x1400125d0`
- `0x140013810`
- `0x140016df0`
- `0x1400222ec`
- `0x140022958`
- `0x14006e1d0`
- `0x140075c08`
- `0x140080758`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006e34e`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006e34e`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14006e2f6`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14006e2f6`
- `ntoskrnl!IofCallDriver` at `0x14006e563`
- `ntoskrnl!IofCallDriver` at `0x14006e563`
- `ntoskrnl!IoReuseIrp` at `0x14006e324`
- `ntoskrnl!IoReuseIrp` at `0x14006e324`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x14006e2d4`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x14006e2d4`

## string_xrefs

- `0x14006e548`: `Smb2ExecuteQueryDirectory`

## pseudocode

```c
__int64 __fastcall Smb2ExecuteQueryDirectory(__int64 a1)
{
  __int64 v1; // rsi
  int v3; // eax
  __int64 *v4; // rbx
  __int64 v5; // rcx
  volatile signed __int64 *WorkItemSecurityContext; // rax
  SECURITY_STATUS v7; // eax
  unsigned int v8; // r14d
  __int64 v9; // r9
  __int64 v10; // rdx
  PDEVICE_OBJECT RelatedDeviceObject; // rax
  __int64 v13; // rdx
  IRP *v14; // rcx
  struct _DEVICE_OBJECT *v15; // r14
  CCHAR StackSize; // al
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rcx
  ULONG Flags; // edx
  __int64 v23; // rax
  _QWORD *v24; // rcx
  int LargerIrp; // eax
  unsigned int v26; // ebx
  __int64 v27; // rdx
  __int64 v28; // [rsp+60h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 560);
  v3 = *(_DWORD *)(v1 + 232);
  v4 = (__int64 *)(v1 + 72);
  if ( v3 )
  {
    if ( v3 == 2 )
    {
      *(_BYTE *)(v1 + 212) |= 1u;
    }
    else
    {
      v5 = *(_QWORD *)(a1 + 560);
      v28 = 0;
      WorkItemSecurityContext = (volatile signed __int64 *)Smb2GetWorkItemSecurityContext(v5);
      v7 = Smb2ReopenFile(*v4, *(_QWORD *)(v1 + 80), WorkItemSecurityContext, &v28);
      v8 = v7;
      if ( v7 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 23, &WPP_afea1950ba7935c3d0422396ce336f53_Traceguids, a1, v7);
        }
        v9 = 1037;
        v10 = v8;
        goto LABEL_10;
      }
      Smb2DereferenceHandle(*(PVOID *)(v1 + 80));
      *(_QWORD *)(v1 + 80) = v28;
    }
    *(_BYTE *)(*v4 + 233) = 0;
    *(_BYTE *)(*v4 + 231) = 0;
  }
  if ( (!*(_BYTE *)(*v4 + 231) || (*(_BYTE *)(v1 + 212) & 1) != 0)
    && FsRtlDoesNameContainWildCards((PUNICODE_STRING)(v1 + 192)) )
  {
    *(_BYTE *)(*v4 + 233) = 1;
  }
  RelatedDeviceObject = IoGetRelatedDeviceObject(*(PFILE_OBJECT *)(*(_QWORD *)(v1 + 80) + 96LL));
  v14 = *(IRP **)(a1 + 120);
  v15 = RelatedDeviceObject;
  StackSize = RelatedDeviceObject->StackSize;
  if ( v14->StackCount < StackSize || (Microsoft_Windows_SMBServerEnableBits & 0x10) != 0 )
  {
    LOBYTE(v13) = StackSize;
    LargerIrp = Srv2AllocateLargerIrp(a1, v13);
    v26 = LargerIrp;
    if ( LargerIrp < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          25,
          &WPP_afea1950ba7935c3d0422396ce336f53_Traceguids,
          a1,
          LargerIrp);
      }
      v9 = 1105;
      v10 = v26;
      goto LABEL_10;
    }
  }
  else
  {
    IoReuseIrp(v14, 0);
  }
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 192LL) = *(_QWORD *)(*(_QWORD *)(v1 + 80) + 96LL);
  v17 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 136LL);
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 152LL) = *(_QWORD *)(*(_QWORD *)(v17 + 8LL * KeGetCurrentNodeNumber() + 8) + 224LL);
  *(_BYTE *)(*(_QWORD *)(a1 + 120) + 64LL) = 0;
  *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL) = 0;
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 56LL) = 0;
  v18 = *(_QWORD *)(a1 + 120);
  v19 = *(_QWORD *)(v18 + 184);
  *(_QWORD *)(a1 + 48) = Smb2ContinueQueryDirectory;
  v20 = *(_QWORD *)(v18 + 184);
  *(_QWORD *)(v20 - 16) = Srv2PostOnCompletionAndClearCancel;
  *(_QWORD *)(v20 - 8) = a1;
  *(_BYTE *)(v20 - 69) = -32;
  *(_WORD *)(v19 - 72) = 268;
  v21 = *(_QWORD *)(*(_QWORD *)(v1 + 80) + 96LL);
  *(_BYTE *)(v19 - 70) = 0;
  *(_QWORD *)(v19 - 56) = v1 + 192;
  *(_QWORD *)(v19 - 24) = v21;
  *(_QWORD *)(v19 - 32) = v15;
  *(_DWORD *)(v19 - 40) = *(_DWORD *)(v1 + 208);
  *(_DWORD *)(v19 - 64) = *(_DWORD *)(v1 + 228);
  *(_DWORD *)(v19 - 48) = *(_DWORD *)(v1 + 216);
  *(_BYTE *)(v19 - 70) = *(_BYTE *)(v1 + 212);
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 24LL) = 0;
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 8LL) = 0;
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 112LL) = 0;
  *(_DWORD *)(*(_QWORD *)(a1 + 120) + 16LL) |= 4u;
  Flags = v15->Flags;
  v23 = *(_QWORD *)(v1 + 160);
  v24 = *(_QWORD **)(a1 + 120);
  if ( (Flags & 4) != 0 )
  {
    v24[3] = *(_QWORD *)(v23 + 24);
    *(_DWORD *)(*(_QWORD *)(a1 + 120) + 16LL) |= 0x10u;
  }
  else
  {
    if ( (Flags & 0x10) == 0 )
    {
      v24[14] = *(_QWORD *)(v23 + 24);
      v23 = *(_QWORD *)(v1 + 160);
      v24 = *(_QWORD **)(a1 + 120);
    }
    v24[1] = *(_QWORD *)(v23 + 56);
  }
  if ( (int)Srv2MarkWorkItemCancellable(a1, 0) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 26, &WPP_afea1950ba7935c3d0422396ce336f53_Traceguids, a1);
    }
    v9 = 1191;
    v10 = 3221225760LL;
LABEL_10:
    Smb2SetError(a1, v10, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\querydir.c", v9);
    return 0;
  }
  LOBYTE(v27) = 3;
  SRV2_PERF_ENTER_EX(a1 + 584, v27, 1195, "Smb2ExecuteQueryDirectory", 1);
  IofCallDriver(v15, *(PIRP *)(a1 + 120));
  return 259;
}

```

## disassembly

```asm
0x14006e1d0  push    rbx
0x14006e1d2  push    rsi
0x14006e1d3  push    rdi
0x14006e1d4  push    r14
0x14006e1d6  sub     rsp, 38h
0x14006e1da  mov     rsi, [rcx+230h]
0x14006e1e1  mov     rdi, rcx
0x14006e1e4  mov     eax, [rsi+0E8h]
0x14006e1ea  lea     rbx, [rsi+48h]
0x14006e1ee  test    eax, eax
0x14006e1f0  jz      loc_14006E2B8
0x14006e1f6  cmp     eax, 2
0x14006e1f9  jnz     short loc_14006E207
0x14006e1fb  or      byte ptr [rsi+0D4h], 1
0x14006e202  jmp     loc_14006E2A4
0x14006e207  mov     rcx, rsi
0x14006e20a  mov     [rsp+58h+arg_0], 0
0x14006e213  call    Smb2GetWorkItemSecurityContext
0x14006e218  mov     rdx, [rsi+50h]
0x14006e21c  lea     r9, [rsp+58h+arg_0]
0x14006e221  mov     rcx, [rbx]
0x14006e224  mov     r8, rax
0x14006e227  call    Smb2ReopenFile
0x14006e22c  mov     r14d, eax
0x14006e22f  test    eax, eax
0x14006e231  jns     short loc_14006E292
0x14006e233  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006e23a  lea     rcx, WPP_GLOBAL_Control
0x14006e241  cmp     r10, rcx
0x14006e244  jz      short loc_14006E273
0x14006e246  test    dword ptr [r10+2Ch], 2000000h
0x14006e24e  jz      short loc_14006E273
0x14006e250  cmp     byte ptr [r10+29h], 1
0x14006e255  jb      short loc_14006E273
0x14006e257  mov     rcx, [r10+18h]
0x14006e25b  lea     r8, WPP_afea1950ba7935c3d0422396ce336f53_Traceguids
0x14006e262  mov     edx, 17h
0x14006e267  mov     [rsp+58h+var_38], eax
0x14006e26b  mov     r9, rdi
0x14006e26e  call    WPP_SF_qD
0x14006e273  mov     r9d, 40Dh
0x14006e279  mov     edx, r14d
0x14006e27c  lea     r8, aOnecoreBaseFsR_12; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14006e283  mov     rcx, rdi
0x14006e286  call    _Smb2SetError
0x14006e28b  xor     eax, eax
0x14006e28d  jmp     loc_14006E574
0x14006e292  mov     rcx, [rsi+50h]; P
0x14006e296  call    Smb2DereferenceHandle
0x14006e29b  mov     rax, [rsp+58h+arg_0]
0x14006e2a0  mov     [rsi+50h], rax
0x14006e2a4  mov     rax, [rbx]
0x14006e2a7  mov     byte ptr [rax+0E9h], 0
0x14006e2ae  mov     rax, [rbx]
0x14006e2b1  mov     byte ptr [rax+0E7h], 0
0x14006e2b8  mov     rax, [rbx]
0x14006e2bb  cmp     byte ptr [rax+0E7h], 0
0x14006e2c2  jz      short loc_14006E2CD
0x14006e2c4  test    byte ptr [rsi+0D4h], 1
0x14006e2cb  jz      short loc_14006E2EE
0x14006e2cd  lea     rcx, [rsi+0C0h]; Name
0x14006e2d4  call    cs:__imp_FsRtlDoesNameContainWildCards
0x14006e2db  nop     dword ptr [rax+rax+00h]
0x14006e2e0  test    al, al
0x14006e2e2  jz      short loc_14006E2EE
0x14006e2e4  mov     rax, [rbx]
0x14006e2e7  mov     byte ptr [rax+0E9h], 1
0x14006e2ee  mov     rcx, [rsi+50h]
0x14006e2f2  mov     rcx, [rcx+60h]; FileObject
0x14006e2f6  call    cs:__imp_IoGetRelatedDeviceObject
0x14006e2fd  nop     dword ptr [rax+rax+00h]
0x14006e302  mov     rcx, [rdi+78h]; Irp
0x14006e306  mov     r14, rax
0x14006e309  mov     al, [rax+4Ch]
0x14006e30c  cmp     [rcx+42h], al
0x14006e30f  jl      loc_14006E461
0x14006e315  test    cs:Microsoft_Windows_SMBServerEnableBits, 10h
0x14006e31c  jnz     loc_14006E461
0x14006e322  xor     edx, edx; Iostatus
0x14006e324  call    cs:__imp_IoReuseIrp
0x14006e32b  nop     dword ptr [rax+rax+00h]
0x14006e330  mov     rax, [rsi+50h]
0x14006e334  mov     rcx, [rdi+78h]
0x14006e338  mov     rax, [rax+60h]
0x14006e33c  mov     [rcx+0C0h], rax
0x14006e343  mov     rax, [rdi+40h]
0x14006e347  mov     rbx, [rax+88h]
0x14006e34e  call    cs:__imp_KeGetCurrentNodeNumber
0x14006e355  nop     dword ptr [rax+rax+00h]
0x14006e35a  movzx   eax, ax
0x14006e35d  mov     rcx, [rbx+rax*8+8]
0x14006e362  mov     rax, [rdi+78h]
0x14006e366  mov     rdx, [rcx+0E0h]
0x14006e36d  lea     rcx, Smb2ContinueQueryDirectory
0x14006e374  mov     [rax+98h], rdx
0x14006e37b  mov     rax, [rdi+78h]
0x14006e37f  mov     byte ptr [rax+40h], 0
0x14006e383  mov     rax, [rdi+78h]
0x14006e387  mov     dword ptr [rax+30h], 0
0x14006e38e  mov     rax, [rdi+78h]
0x14006e392  mov     qword ptr [rax+38h], 0
0x14006e39a  mov     rax, [rdi+78h]
0x14006e39e  mov     rdx, [rax+0B8h]
0x14006e3a5  mov     [rdi+30h], rcx
0x14006e3a9  lea     rcx, Srv2PostOnCompletionAndClearCancel
0x14006e3b0  mov     rax, [rax+0B8h]
0x14006e3b7  mov     [rax-10h], rcx
0x14006e3bb  mov     [rax-8], rdi
0x14006e3bf  mov     byte ptr [rax-45h], 0E0h
0x14006e3c3  mov     word ptr [rdx-48h], 10Ch
0x14006e3c9  mov     rax, [rsi+50h]
0x14006e3cd  mov     rcx, [rax+60h]
0x14006e3d1  lea     rax, [rsi+0C0h]
0x14006e3d8  mov     byte ptr [rdx-46h], 0
0x14006e3dc  mov     [rdx-38h], rax
0x14006e3e0  mov     [rdx-18h], rcx
0x14006e3e4  mov     [rdx-20h], r14
0x14006e3e8  mov     eax, [rsi+0D0h]
0x14006e3ee  mov     [rdx-28h], eax
0x14006e3f1  mov     eax, [rsi+0E4h]
0x14006e3f7  mov     [rdx-40h], eax
0x14006e3fa  mov     eax, [rsi+0D8h]
0x14006e400  mov     [rdx-30h], eax
0x14006e403  mov     al, [rsi+0D4h]
0x14006e409  mov     [rdx-46h], al
0x14006e40c  mov     rax, [rdi+78h]
0x14006e410  mov     qword ptr [rax+18h], 0
0x14006e418  mov     rax, [rdi+78h]
0x14006e41c  mov     qword ptr [rax+8], 0
0x14006e424  mov     rax, [rdi+78h]
0x14006e428  mov     qword ptr [rax+70h], 0
0x14006e430  mov     rax, [rdi+78h]
0x14006e434  or      dword ptr [rax+10h], 4
0x14006e438  mov     edx, [r14+30h]
0x14006e43c  mov     rax, [rsi+0A0h]
0x14006e443  mov     rcx, [rdi+78h]
0x14006e447  test    dl, 4
0x14006e44a  jz      short loc_14006E4C2
0x14006e44c  mov     rax, [rax+18h]
0x14006e450  mov     [rcx+18h], rax
0x14006e454  mov     rax, [rdi+78h]
0x14006e458  or      dword ptr [rax+10h], 10h
0x14006e45c  jmp     loc_14006E4E2
0x14006e461  mov     dl, al
0x14006e463  mov     rcx, rdi
0x14006e466  call    Srv2AllocateLargerIrp
0x14006e46b  mov     ebx, eax
0x14006e46d  test    eax, eax
0x14006e46f  jns     loc_14006E330
0x14006e475  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006e47c  lea     rcx, WPP_GLOBAL_Control
0x14006e483  cmp     r10, rcx
0x14006e486  jz      short loc_14006E4B5
0x14006e488  test    dword ptr [r10+2Ch], 2000000h
0x14006e490  jz      short loc_14006E4B5
0x14006e492  cmp     byte ptr [r10+29h], 1
0x14006e497  jb      short loc_14006E4B5
0x14006e499  mov     rcx, [r10+18h]
0x14006e49d  lea     r8, WPP_afea1950ba7935c3d0422396ce336f53_Traceguids
0x14006e4a4  mov     edx, 19h
0x14006e4a9  mov     [rsp+58h+var_38], eax
0x14006e4ad  mov     r9, rdi
0x14006e4b0  call    WPP_SF_qD
0x14006e4b5  mov     r9d, 451h
0x14006e4bb  mov     edx, ebx
0x14006e4bd  jmp     loc_14006E27C
0x14006e4c2  test    dl, 10h
0x14006e4c5  jnz     short loc_14006E4DA
0x14006e4c7  mov     rax, [rax+18h]
0x14006e4cb  mov     [rcx+70h], rax
0x14006e4cf  mov     rax, [rsi+0A0h]
0x14006e4d6  mov     rcx, [rdi+78h]
0x14006e4da  mov     rax, [rax+38h]
0x14006e4de  mov     [rcx+8], rax
0x14006e4e2  xor     edx, edx
0x14006e4e4  mov     rcx, rdi
0x14006e4e7  call    Srv2MarkWorkItemCancellable
0x14006e4ec  test    eax, eax
0x14006e4ee  jns     short loc_14006E53C
0x14006e4f0  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006e4f7  lea     rcx, WPP_GLOBAL_Control
0x14006e4fe  cmp     r10, rcx
0x14006e501  jz      short loc_14006E52C
0x14006e503  test    dword ptr [r10+2Ch], 2000000h
0x14006e50b  jz      short loc_14006E52C
0x14006e50d  cmp     byte ptr [r10+29h], 1
0x14006e512  jb      short loc_14006E52C
0x14006e514  mov     rcx, [r10+18h]
0x14006e518  lea     r8, WPP_afea1950ba7935c3d0422396ce336f53_Traceguids
0x14006e51f  mov     edx, 1Ah
0x14006e524  mov     r9, rdi
0x14006e527  call    WPP_SF_q
0x14006e52c  mov     r9d, 4A7h
0x14006e532  mov     edx, 0C0000120h
0x14006e537  jmp     loc_14006E27C
0x14006e53c  lea     rcx, [rdi+248h]
0x14006e543  mov     byte ptr [rsp+58h+var_38], 1
0x14006e548  lea     r9, aSmb2executeque; "Smb2ExecuteQueryDirectory"
0x14006e54f  mov     r8d, 4ABh
0x14006e555  mov     dl, 3
0x14006e557  call    SRV2_PERF_ENTER_EX
0x14006e55c  mov     rdx, [rdi+78h]; Irp
0x14006e560  mov     rcx, r14; DeviceObject
0x14006e563  call    cs:__imp_IofCallDriver
0x14006e56a  nop     dword ptr [rax+rax+00h]
0x14006e56f  mov     eax, 103h
0x14006e574  add     rsp, 38h
0x14006e578  pop     r14
0x14006e57a  pop     rdi
0x14006e57b  pop     rsi
0x14006e57c  pop     rbx
0x14006e57d  retn
```
