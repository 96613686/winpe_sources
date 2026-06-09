# Smb2ExecuteQueryDirectory

- ea: `0x14006e180`
- end: `0x14006e52f`
- name: `Smb2ExecuteQueryDirectory`
- size: `943`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140074860`

## callees

- `0x140005070`
- `0x140007400`
- `0x1400125d0`
- `0x140013810`
- `0x140016df0`
- `0x1400222ec`
- `0x140022958`
- `0x14006e180`
- `0x140075bb8`
- `0x140080708`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006e2fe`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006e2fe`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14006e2a6`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14006e2a6`
- `ntoskrnl!IofCallDriver` at `0x14006e513`
- `ntoskrnl!IofCallDriver` at `0x14006e513`
- `ntoskrnl!IoReuseIrp` at `0x14006e2d4`
- `ntoskrnl!IoReuseIrp` at `0x14006e2d4`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x14006e284`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x14006e284`

## string_xrefs

- `0x14006e4f8`: `Smb2ExecuteQueryDirectory`

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
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_afea1950ba7935c3d0422396ce336f53_Traceguids, a1, v7);
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
          WPP_afea1950ba7935c3d0422396ce336f53_Traceguids,
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
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_afea1950ba7935c3d0422396ce336f53_Traceguids, a1);
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
0x14006e180  push    rbx
0x14006e182  push    rsi
0x14006e183  push    rdi
0x14006e184  push    r14
0x14006e186  sub     rsp, 38h
0x14006e18a  mov     rsi, [rcx+230h]
0x14006e191  mov     rdi, rcx
0x14006e194  mov     eax, [rsi+0E8h]
0x14006e19a  lea     rbx, [rsi+48h]
0x14006e19e  test    eax, eax
0x14006e1a0  jz      loc_14006E268
0x14006e1a6  cmp     eax, 2
0x14006e1a9  jnz     short loc_14006E1B7
0x14006e1ab  or      byte ptr [rsi+0D4h], 1
0x14006e1b2  jmp     loc_14006E254
0x14006e1b7  mov     rcx, rsi
0x14006e1ba  mov     [rsp+58h+arg_0], 0
0x14006e1c3  call    Smb2GetWorkItemSecurityContext
0x14006e1c8  mov     rdx, [rsi+50h]
0x14006e1cc  lea     r9, [rsp+58h+arg_0]
0x14006e1d1  mov     rcx, [rbx]
0x14006e1d4  mov     r8, rax
0x14006e1d7  call    Smb2ReopenFile
0x14006e1dc  mov     r14d, eax
0x14006e1df  test    eax, eax
0x14006e1e1  jns     short loc_14006E242
0x14006e1e3  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006e1ea  lea     rcx, WPP_GLOBAL_Control
0x14006e1f1  cmp     r10, rcx
0x14006e1f4  jz      short loc_14006E223
0x14006e1f6  test    dword ptr [r10+2Ch], 2000000h
0x14006e1fe  jz      short loc_14006E223
0x14006e200  cmp     byte ptr [r10+29h], 1
0x14006e205  jb      short loc_14006E223
0x14006e207  mov     rcx, [r10+18h]
0x14006e20b  lea     r8, WPP_afea1950ba7935c3d0422396ce336f53_Traceguids
0x14006e212  mov     edx, 17h
0x14006e217  mov     [rsp+58h+var_38], eax
0x14006e21b  mov     r9, rdi
0x14006e21e  call    WPP_SF_qD
0x14006e223  mov     r9d, 40Dh
0x14006e229  mov     edx, r14d
0x14006e22c  lea     r8, aOnecoreBaseFsR_12; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14006e233  mov     rcx, rdi
0x14006e236  call    _Smb2SetError
0x14006e23b  xor     eax, eax
0x14006e23d  jmp     loc_14006E524
0x14006e242  mov     rcx, [rsi+50h]; P
0x14006e246  call    Smb2DereferenceHandle
0x14006e24b  mov     rax, [rsp+58h+arg_0]
0x14006e250  mov     [rsi+50h], rax
0x14006e254  mov     rax, [rbx]
0x14006e257  mov     byte ptr [rax+0E9h], 0
0x14006e25e  mov     rax, [rbx]
0x14006e261  mov     byte ptr [rax+0E7h], 0
0x14006e268  mov     rax, [rbx]
0x14006e26b  cmp     byte ptr [rax+0E7h], 0
0x14006e272  jz      short loc_14006E27D
0x14006e274  test    byte ptr [rsi+0D4h], 1
0x14006e27b  jz      short loc_14006E29E
0x14006e27d  lea     rcx, [rsi+0C0h]; Name
0x14006e284  call    cs:__imp_FsRtlDoesNameContainWildCards
0x14006e28b  nop     dword ptr [rax+rax+00h]
0x14006e290  test    al, al
0x14006e292  jz      short loc_14006E29E
0x14006e294  mov     rax, [rbx]
0x14006e297  mov     byte ptr [rax+0E9h], 1
0x14006e29e  mov     rcx, [rsi+50h]
0x14006e2a2  mov     rcx, [rcx+60h]; FileObject
0x14006e2a6  call    cs:__imp_IoGetRelatedDeviceObject
0x14006e2ad  nop     dword ptr [rax+rax+00h]
0x14006e2b2  mov     rcx, [rdi+78h]; Irp
0x14006e2b6  mov     r14, rax
0x14006e2b9  mov     al, [rax+4Ch]
0x14006e2bc  cmp     [rcx+42h], al
0x14006e2bf  jl      loc_14006E411
0x14006e2c5  test    cs:Microsoft_Windows_SMBServerEnableBits, 10h
0x14006e2cc  jnz     loc_14006E411
0x14006e2d2  xor     edx, edx; Iostatus
0x14006e2d4  call    cs:__imp_IoReuseIrp
0x14006e2db  nop     dword ptr [rax+rax+00h]
0x14006e2e0  mov     rax, [rsi+50h]
0x14006e2e4  mov     rcx, [rdi+78h]
0x14006e2e8  mov     rax, [rax+60h]
0x14006e2ec  mov     [rcx+0C0h], rax
0x14006e2f3  mov     rax, [rdi+40h]
0x14006e2f7  mov     rbx, [rax+88h]
0x14006e2fe  call    cs:__imp_KeGetCurrentNodeNumber
0x14006e305  nop     dword ptr [rax+rax+00h]
0x14006e30a  movzx   eax, ax
0x14006e30d  mov     rcx, [rbx+rax*8+8]
0x14006e312  mov     rax, [rdi+78h]
0x14006e316  mov     rdx, [rcx+0E0h]
0x14006e31d  lea     rcx, Smb2ContinueQueryDirectory
0x14006e324  mov     [rax+98h], rdx
0x14006e32b  mov     rax, [rdi+78h]
0x14006e32f  mov     byte ptr [rax+40h], 0
0x14006e333  mov     rax, [rdi+78h]
0x14006e337  mov     dword ptr [rax+30h], 0
0x14006e33e  mov     rax, [rdi+78h]
0x14006e342  mov     qword ptr [rax+38h], 0
0x14006e34a  mov     rax, [rdi+78h]
0x14006e34e  mov     rdx, [rax+0B8h]
0x14006e355  mov     [rdi+30h], rcx
0x14006e359  lea     rcx, Srv2PostOnCompletionAndClearCancel
0x14006e360  mov     rax, [rax+0B8h]
0x14006e367  mov     [rax-10h], rcx
0x14006e36b  mov     [rax-8], rdi
0x14006e36f  mov     byte ptr [rax-45h], 0E0h
0x14006e373  mov     word ptr [rdx-48h], 10Ch
0x14006e379  mov     rax, [rsi+50h]
0x14006e37d  mov     rcx, [rax+60h]
0x14006e381  lea     rax, [rsi+0C0h]
0x14006e388  mov     byte ptr [rdx-46h], 0
0x14006e38c  mov     [rdx-38h], rax
0x14006e390  mov     [rdx-18h], rcx
0x14006e394  mov     [rdx-20h], r14
0x14006e398  mov     eax, [rsi+0D0h]
0x14006e39e  mov     [rdx-28h], eax
0x14006e3a1  mov     eax, [rsi+0E4h]
0x14006e3a7  mov     [rdx-40h], eax
0x14006e3aa  mov     eax, [rsi+0D8h]
0x14006e3b0  mov     [rdx-30h], eax
0x14006e3b3  mov     al, [rsi+0D4h]
0x14006e3b9  mov     [rdx-46h], al
0x14006e3bc  mov     rax, [rdi+78h]
0x14006e3c0  mov     qword ptr [rax+18h], 0
0x14006e3c8  mov     rax, [rdi+78h]
0x14006e3cc  mov     qword ptr [rax+8], 0
0x14006e3d4  mov     rax, [rdi+78h]
0x14006e3d8  mov     qword ptr [rax+70h], 0
0x14006e3e0  mov     rax, [rdi+78h]
0x14006e3e4  or      dword ptr [rax+10h], 4
0x14006e3e8  mov     edx, [r14+30h]
0x14006e3ec  mov     rax, [rsi+0A0h]
0x14006e3f3  mov     rcx, [rdi+78h]
0x14006e3f7  test    dl, 4
0x14006e3fa  jz      short loc_14006E472
0x14006e3fc  mov     rax, [rax+18h]
0x14006e400  mov     [rcx+18h], rax
0x14006e404  mov     rax, [rdi+78h]
0x14006e408  or      dword ptr [rax+10h], 10h
0x14006e40c  jmp     loc_14006E492
0x14006e411  mov     dl, al
0x14006e413  mov     rcx, rdi
0x14006e416  call    Srv2AllocateLargerIrp
0x14006e41b  mov     ebx, eax
0x14006e41d  test    eax, eax
0x14006e41f  jns     loc_14006E2E0
0x14006e425  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006e42c  lea     rcx, WPP_GLOBAL_Control
0x14006e433  cmp     r10, rcx
0x14006e436  jz      short loc_14006E465
0x14006e438  test    dword ptr [r10+2Ch], 2000000h
0x14006e440  jz      short loc_14006E465
0x14006e442  cmp     byte ptr [r10+29h], 1
0x14006e447  jb      short loc_14006E465
0x14006e449  mov     rcx, [r10+18h]
0x14006e44d  lea     r8, WPP_afea1950ba7935c3d0422396ce336f53_Traceguids
0x14006e454  mov     edx, 19h
0x14006e459  mov     [rsp+58h+var_38], eax
0x14006e45d  mov     r9, rdi
0x14006e460  call    WPP_SF_qD
0x14006e465  mov     r9d, 451h
0x14006e46b  mov     edx, ebx
0x14006e46d  jmp     loc_14006E22C
0x14006e472  test    dl, 10h
0x14006e475  jnz     short loc_14006E48A
0x14006e477  mov     rax, [rax+18h]
0x14006e47b  mov     [rcx+70h], rax
0x14006e47f  mov     rax, [rsi+0A0h]
0x14006e486  mov     rcx, [rdi+78h]
0x14006e48a  mov     rax, [rax+38h]
0x14006e48e  mov     [rcx+8], rax
0x14006e492  xor     edx, edx
0x14006e494  mov     rcx, rdi
0x14006e497  call    Srv2MarkWorkItemCancellable
0x14006e49c  test    eax, eax
0x14006e49e  jns     short loc_14006E4EC
0x14006e4a0  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006e4a7  lea     rcx, WPP_GLOBAL_Control
0x14006e4ae  cmp     r10, rcx
0x14006e4b1  jz      short loc_14006E4DC
0x14006e4b3  test    dword ptr [r10+2Ch], 2000000h
0x14006e4bb  jz      short loc_14006E4DC
0x14006e4bd  cmp     byte ptr [r10+29h], 1
0x14006e4c2  jb      short loc_14006E4DC
0x14006e4c4  mov     rcx, [r10+18h]
0x14006e4c8  lea     r8, WPP_afea1950ba7935c3d0422396ce336f53_Traceguids
0x14006e4cf  mov     edx, 1Ah
0x14006e4d4  mov     r9, rdi
0x14006e4d7  call    WPP_SF_q
0x14006e4dc  mov     r9d, 4A7h
0x14006e4e2  mov     edx, 0C0000120h
0x14006e4e7  jmp     loc_14006E22C
0x14006e4ec  lea     rcx, [rdi+248h]
0x14006e4f3  mov     byte ptr [rsp+58h+var_38], 1
0x14006e4f8  lea     r9, aSmb2executeque; "Smb2ExecuteQueryDirectory"
0x14006e4ff  mov     r8d, 4ABh
0x14006e505  mov     dl, 3
0x14006e507  call    SRV2_PERF_ENTER_EX
0x14006e50c  mov     rdx, [rdi+78h]; Irp
0x14006e510  mov     rcx, r14; DeviceObject
0x14006e513  call    cs:__imp_IofCallDriver
0x14006e51a  nop     dword ptr [rax+rax+00h]
0x14006e51f  mov     eax, 103h
0x14006e524  add     rsp, 38h
0x14006e528  pop     r14
0x14006e52a  pop     rdi
0x14006e52b  pop     rsi
0x14006e52c  pop     rbx
0x14006e52d  retn
```
