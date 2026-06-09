# TdiSendDatagram

- ea: `0x14001c0e8`
- end: `0x14001c3f1`
- name: `TdiSendDatagram`
- size: `777`
- prototype: `__int64 __fastcall(struct _FILE_OBJECT *, struct _DEVICE_OBJECT *, void *, ULONG, void (__fastcall *)(__int64, __int64, __int64), __int64, __int64, unsigned int, unsigned __int16, char)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140011c7c`
- `0x140018268`
- `0x1400185a4`
- `0x140018d80`
- `0x140019f70`

## callees

- `0x140005068`
- `0x14001c0e8`
- `0x14001c7c8`
- `0x14001ce30`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001c10b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001c10b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001c1de`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001c353`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001c1de`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001c353`
- `ntoskrnl!IofCallDriver` at `0x14001c2d6`
- `ntoskrnl!IofCallDriver` at `0x14001c2d6`
- `ntoskrnl!IoFreeMdl` at `0x14001c1b5`
- `ntoskrnl!IoFreeMdl` at `0x14001c1b5`
- `ntoskrnl!IoFreeIrp` at `0x14001c1c6`
- `ntoskrnl!IoFreeIrp` at `0x14001c367`
- `ntoskrnl!IoFreeIrp` at `0x14001c1c6`
- `ntoskrnl!IoFreeIrp` at `0x14001c367`
- `ntoskrnl!IoAllocateIrp` at `0x14001c132`
- `ntoskrnl!IoAllocateIrp` at `0x14001c132`
- `ntoskrnl!IoAllocateMdl` at `0x14001c164`
- `ntoskrnl!IoAllocateMdl` at `0x14001c164`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001c226`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001c226`
- `ntoskrnl!MmProbeAndLockPages` at `0x14001c19c`
- `ntoskrnl!MmProbeAndLockPages` at `0x14001c19c`

## pseudocode

```c
__int64 __fastcall TdiSendDatagram(
        struct _FILE_OBJECT *a1,
        struct _DEVICE_OBJECT *a2,
        void *a3,
        ULONG a4,
        void (__fastcall *a5)(__int64, __int64, __int64),
        __int64 a6,
        __int64 a7,
        unsigned int a8,
        unsigned __int16 a9,
        char a10)
{
  PIRP Irp; // rdi
  char *v15; // rbx
  struct _MDL *Mdl; // rax
  struct _MDL *v17; // rsi
  char v18; // al
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v20; // rax
  char v21; // al
  int Timer_high; // edx
  const char *v23; // r9

  Irp = 0;
  v15 = (char *)ExAllocateFromNPagedLookasideList(&Lookaside);
  if ( v15 )
  {
    Irp = IoAllocateIrp(*(_BYTE *)(*(_QWORD *)pgPgmDevice + 76LL), 0);
    if ( Irp )
    {
      Mdl = IoAllocateMdl(a3, a4, 0, 0, 0);
      v17 = Mdl;
      if ( Mdl )
      {
        if ( a10 )
        {
          MmProbeAndLockPages(Mdl, 0, IoReadAccess);
          v18 = 1;
        }
        else
        {
          MmBuildMdlForNonPagedPool(Mdl);
          v18 = 0;
        }
        v15[96] = v18;
        Irp->MdlAddress = v17;
        *((_DWORD *)v15 + 12) = 1;
        *((_DWORD *)v15 + 13) = 131086;
        *(_DWORD *)(v15 + 58) = _byteswap_ulong(a8);
        *((_WORD *)v15 + 28) = __ROR2__(a9, 8);
        *((_DWORD *)v15 + 8) = 22;
        *((_QWORD *)v15 + 5) = v15 + 48;
        *((_QWORD *)v15 + 9) = a5;
        *((_QWORD *)v15 + 10) = a6;
        *((_QWORD *)v15 + 11) = a7;
        CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
        CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&TdiSendDatagramCompletion;
        CurrentStackLocation[-1].Context = v15;
        CurrentStackLocation[-1].Control = -32;
        v20 = Irp->Tail.Overlay.CurrentStackLocation;
        *(_WORD *)&v20[-1].MajorFunction = 2319;
        v20[-1].DeviceObject = a2;
        v20[-1].FileObject = a1;
        v20[-1].Parameters.Read.Length = a4;
        v20[-1].Parameters.QueryDirectory.FileName = (PUNICODE_STRING)v15;
        v21 = IofCallDriver(a2, Irp);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
          if ( (Timer_high & 0x10) != 0 )
          {
            v23 = "MCast";
            if ( (a8 & 0xF0) != 0xE0 )
              v23 = "Unicast";
            LOBYTE(Timer_high) = a8 & 0xF0;
            WPP_SF_sDDD(WPP_GLOBAL_Control->AttachedDevice, Timer_high, a9, (_DWORD)v23, a8, a9, v21);
          }
        }
        return 259;
      }
    }
  }
  if ( v15 )
    ExFreeToNPagedLookasideList(&Lookaside, v15);
  if ( Irp )
    IoFreeIrp(Irp);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids, 104);
  if ( a5 )
  {
    a5(a6, a7, 3221225626LL);
    return 259;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x14001c0e8  push    rbx
0x14001c0ea  push    rsi
0x14001c0eb  push    rdi
0x14001c0ec  push    r12
0x14001c0ee  push    r14
0x14001c0f0  push    r15
0x14001c0f2  sub     rsp, 68h
0x14001c0f6  mov     r14d, r9d
0x14001c0f9  mov     rsi, r8
0x14001c0fc  mov     r15, rdx
0x14001c0ff  mov     r12, rcx
0x14001c102  xor     edi, edi
0x14001c104  lea     rcx, Lookaside; Lookaside
0x14001c10b  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14001c112  nop     dword ptr [rax+rax+00h]
0x14001c117  mov     rbx, rax
0x14001c11a  test    rax, rax
0x14001c11d  jz      loc_14001C344
0x14001c123  mov     rax, cs:pgPgmDevice
0x14001c12a  mov     rcx, [rax]
0x14001c12d  xor     edx, edx; ChargeQuota
0x14001c12f  mov     cl, [rcx+4Ch]; StackSize
0x14001c132  call    cs:__imp_IoAllocateIrp
0x14001c139  nop     dword ptr [rax+rax+00h]
0x14001c13e  mov     rdi, rax
0x14001c141  mov     [rsp+98h+var_50], rax
0x14001c146  test    rax, rax
0x14001c149  jz      loc_14001C344
0x14001c14f  mov     [rsp+98h+Irp], 0; Irp
0x14001c158  xor     r9d, r9d; ChargeQuota
0x14001c15b  xor     r8d, r8d; SecondaryBuffer
0x14001c15e  mov     edx, r14d; Length
0x14001c161  mov     rcx, rsi; VirtualAddress
0x14001c164  call    cs:__imp_IoAllocateMdl
0x14001c16b  nop     dword ptr [rax+rax+00h]
0x14001c170  mov     rsi, rax
0x14001c173  mov     [rsp+98h+Mdl], rax
0x14001c178  test    rax, rax
0x14001c17b  jz      loc_14001C344
0x14001c181  mov     [rsp+98h+Entry], rbx
0x14001c186  cmp     [rsp+98h+arg_48], 0
0x14001c18e  jz      loc_14001C223
0x14001c194  xor     r8d, r8d; Operation
0x14001c197  xor     edx, edx; AccessMode
0x14001c199  mov     rcx, rax; MemoryDescriptorList
0x14001c19c  call    cs:__imp_MmProbeAndLockPages
0x14001c1a3  nop     dword ptr [rax+rax+00h]
0x14001c1a8  nop
0x14001c1a9  mov     al, 1
0x14001c1ab  jmp     loc_14001C234
0x14001c1b0  mov     rcx, [rsp+98h+Mdl]; Mdl
0x14001c1b5  call    cs:__imp_IoFreeMdl
0x14001c1bc  nop     dword ptr [rax+rax+00h]
0x14001c1c1  mov     rcx, [rsp+98h+var_50]; Irp
0x14001c1c6  call    cs:__imp_IoFreeIrp
0x14001c1cd  nop     dword ptr [rax+rax+00h]
0x14001c1d2  mov     rdx, [rsp+98h+Entry]; Entry
0x14001c1d7  lea     rcx, Lookaside; Lookaside
0x14001c1de  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001c1e5  nop     dword ptr [rax+rax+00h]
0x14001c1ea  mov     rax, [rsp+98h+arg_20]
0x14001c1f2  test    rax, rax
0x14001c1f5  jz      short loc_14001C219
0x14001c1f7  mov     r8d, 0C000009Ah
0x14001c1fd  mov     rdx, [rsp+98h+arg_30]
0x14001c205  mov     rcx, [rsp+98h+arg_28]
0x14001c20d  call    _guard_dispatch_icall
0x14001c212  mov     eax, 103h
0x14001c217  jmp     short loc_14001C21E
0x14001c219  mov     eax, 0C000009Ah
0x14001c21e  jmp     loc_14001C3E2
0x14001c223  mov     rcx, rsi; MemoryDescriptorList
0x14001c226  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14001c22d  nop     dword ptr [rax+rax+00h]
0x14001c232  xor     al, al
0x14001c234  mov     [rbx+60h], al
0x14001c237  mov     [rdi+8], rsi
0x14001c23b  lea     rcx, [rbx+30h]
0x14001c23f  mov     dword ptr [rcx], 1
0x14001c245  mov     dword ptr [rbx+34h], 2000Eh
0x14001c24c  mov     esi, [rsp+98h+arg_38]
0x14001c253  mov     eax, esi
0x14001c255  bswap   eax
0x14001c257  mov     [rbx+3Ah], eax
0x14001c25a  movzx   eax, [rsp+98h+arg_40]
0x14001c262  ror     ax, 8
0x14001c266  mov     [rbx+38h], ax
0x14001c26a  mov     dword ptr [rbx+20h], 16h
0x14001c271  mov     [rbx+28h], rcx
0x14001c275  mov     rax, [rsp+98h+arg_20]
0x14001c27d  mov     [rbx+48h], rax
0x14001c281  mov     rax, [rsp+98h+arg_28]
0x14001c289  mov     [rbx+50h], rax
0x14001c28d  mov     rax, [rsp+98h+arg_30]
0x14001c295  mov     [rbx+58h], rax
0x14001c299  mov     rax, [rdi+0B8h]
0x14001c2a0  lea     rcx, TdiSendDatagramCompletion
0x14001c2a7  mov     [rax-10h], rcx
0x14001c2ab  mov     [rax-8], rbx
0x14001c2af  mov     byte ptr [rax-45h], 0E0h
0x14001c2b3  mov     rax, [rdi+0B8h]
0x14001c2ba  mov     word ptr [rax-48h], 90Fh
0x14001c2c0  mov     [rax-20h], r15
0x14001c2c4  mov     [rax-18h], r12
0x14001c2c8  mov     [rax-40h], r14d
0x14001c2cc  mov     [rax-38h], rbx
0x14001c2d0  mov     rdx, rdi; Irp
0x14001c2d3  mov     rcx, r15; DeviceObject
0x14001c2d6  call    cs:__imp_IofCallDriver
0x14001c2dd  nop     dword ptr [rax+rax+00h]
0x14001c2e2  lea     rdx, WPP_GLOBAL_Control
0x14001c2e9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c2f0  cmp     rcx, rdx
0x14001c2f3  jz      loc_14001C3D6
0x14001c2f9  mov     edx, [rcx+2Ch]
0x14001c2fc  test    dl, 10h
0x14001c2ff  jz      loc_14001C3D6
0x14001c305  movzx   r8d, [rsp+98h+arg_40]
0x14001c30e  mov     dl, sil
0x14001c311  and     dl, 0F0h
0x14001c314  lea     r10, aUnicast; "Unicast"
0x14001c31b  lea     r9, aMcast; "MCast"
0x14001c322  cmp     dl, 0E0h
0x14001c325  cmovnz  r9, r10
0x14001c329  mov     [rsp+98h+var_68], eax
0x14001c32d  mov     [rsp+98h+var_70], r8d
0x14001c332  mov     dword ptr [rsp+98h+Irp], esi
0x14001c336  mov     rcx, [rcx+18h]
0x14001c33a  call    WPP_SF_sDDD
0x14001c33f  jmp     loc_14001C3D6
0x14001c344  test    rbx, rbx
0x14001c347  jz      short loc_14001C35F
0x14001c349  mov     rdx, rbx; Entry
0x14001c34c  lea     rcx, Lookaside; Lookaside
0x14001c353  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001c35a  nop     dword ptr [rax+rax+00h]
0x14001c35f  test    rdi, rdi
0x14001c362  jz      short loc_14001C373
0x14001c364  mov     rcx, rdi; Irp
0x14001c367  call    cs:__imp_IoFreeIrp
0x14001c36e  nop     dword ptr [rax+rax+00h]
0x14001c373  lea     rdx, WPP_GLOBAL_Control
0x14001c37a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c381  cmp     rcx, rdx
0x14001c384  jz      short loc_14001C3AB
0x14001c386  mov     eax, [rcx+2Ch]
0x14001c389  mov     edx, 2
0x14001c38e  test    dl, al
0x14001c390  jz      short loc_14001C3AB
0x14001c392  mov     edx, 1Ch
0x14001c397  lea     r9d, [rdx+4Ch]
0x14001c39b  lea     r8, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids
0x14001c3a2  mov     rcx, [rcx+18h]
0x14001c3a6  call    WPP_SF_d
0x14001c3ab  mov     r9, [rsp+98h+arg_20]
0x14001c3b3  test    r9, r9
0x14001c3b6  jz      short loc_14001C3DD
0x14001c3b8  mov     r8d, 0C000009Ah
0x14001c3be  mov     rdx, [rsp+98h+arg_30]
0x14001c3c6  mov     rcx, [rsp+98h+arg_28]
0x14001c3ce  mov     rax, r9
0x14001c3d1  call    _guard_dispatch_icall
0x14001c3d6  mov     eax, 103h
0x14001c3db  jmp     short loc_14001C3E2
0x14001c3dd  mov     eax, 0C000009Ah
0x14001c3e2  add     rsp, 68h
0x14001c3e6  pop     r15
0x14001c3e8  pop     r14
0x14001c3ea  pop     r12
0x14001c3ec  pop     rdi
0x14001c3ed  pop     rsi
0x14001c3ee  pop     rbx
0x14001c3ef  retn
```
