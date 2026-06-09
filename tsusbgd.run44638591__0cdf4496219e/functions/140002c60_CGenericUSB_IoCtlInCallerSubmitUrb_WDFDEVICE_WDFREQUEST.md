# CGenericUSB::IoCtlInCallerSubmitUrb(WDFDEVICE__ *,WDFREQUEST__ *)

- ea: `0x140002c60`
- end: `0x140003111`
- name: `?IoCtlInCallerSubmitUrb@CGenericUSB@@AEAAXPEAUWDFDEVICE__@@PEAUWDFREQUEST__@@@Z`
- size: `1201`
- prototype: `void __fastcall(CGenericUSB *__hidden this, struct WDFDEVICE__ *, struct WDFREQUEST__ *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140003e20`

## callees

- `0x140001ac0`
- `0x140002c60`
- `0x140003934`
- `0x140003a10`
- `0x1400049ac`
- `0x1400062f8`
- `0x140006370`
- `0x140006a80`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x140002df7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140002df7`
- `ntoskrnl!IoAllocateMdl` at `0x140002f05`
- `ntoskrnl!IoAllocateMdl` at `0x140002f05`
- `ntoskrnl!MmUnlockPages` at `0x14000305c`
- `ntoskrnl!MmUnlockPages` at `0x14000305c`
- `ntoskrnl!IoFreeMdl` at `0x14000306b`
- `ntoskrnl!IoFreeMdl` at `0x14000306b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003043`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003043`

## pseudocode

```c
void __fastcall CGenericUSB::IoCtlInCallerSubmitUrb(
        struct CSimpleHash **this,
        struct WDFDEVICE__ *a2,
        struct WDFREQUEST__ *a3)
{
  __int64 v4; // rdi
  int v5; // eax
  int Instance; // ebx
  _QWORD *v7; // rdi
  int v8; // eax
  __int64 v9; // r8
  unsigned __int16 v10; // r14
  unsigned __int8 *PoolWithTag; // r15
  struct _MDL *v12; // rsi
  char v13; // r12
  __int64 *v14; // rax
  __int64 v15; // rcx
  struct _MDL *Mdl; // rax
  int v17; // eax
  ULONG Length[2]; // [rsp+50h] [rbp-30h] BYREF
  PVOID VirtualAddress; // [rsp+58h] [rbp-28h] BYREF
  __int64 v20; // [rsp+60h] [rbp-20h] BYREF
  __int64 v21; // [rsp+68h] [rbp-18h] BYREF
  __int64 v22; // [rsp+70h] [rbp-10h]
  struct CTsUrbResult *v23; // [rsp+78h] [rbp-8h] BYREF
  unsigned __int64 v26; // [rsp+D8h] [rbp+58h] BYREF

  v26 = 0;
  *(_QWORD *)Length = 0;
  v20 = 0;
  VirtualAddress = 0;
  v23 = 0;
  v21 = 0;
  v4 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a3,
         off_140009018);
  v22 = v4;
  *(_BYTE *)(v4 + 32) = 1;
  v5 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, __int64 *, unsigned __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[136].Blink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a3,
         8,
         &v20,
         &v26);
  Instance = v5;
  if ( v5 < 0 || !v20 || !v26 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids,
        (unsigned int)v5);
LABEL_45:
    if ( Instance >= 0 )
      return;
    goto LABEL_46;
  }
  v7 = (_QWORD *)(v4 + 1768);
  v8 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *))WPP_MAIN_CB.Queue.ListEntry.Flink[139].Blink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a3);
  Instance = v8;
  if ( v8 >= 0 )
  {
    v10 = v26;
    if ( v26 > 0xFFFF )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 12, v9, v26);
      Instance = -1073741811;
      goto LABEL_46;
    }
    PoolWithTag = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)512, (unsigned __int16)v26, 0x47555354u);
    if ( !PoolWithTag )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids, v10);
      Instance = -1073741801;
      goto LABEL_46;
    }
    v12 = 0;
    v13 = 0;
    v14 = (__int64 *)((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[97].Flink)(
                       WPP_MAIN_CB.Queue.ListEntry.Blink,
                       *v7,
                       &v21);
    v15 = *v14;
    *(_QWORD *)PoolWithTag = *v14;
    if ( (unsigned __int16)v15 < 8u || (unsigned __int16)v15 > v10 )
      goto LABEL_19;
    memmove(PoolWithTag + 8, v14 + 1, (unsigned __int16)v15 - 8LL);
    if ( ((int (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD, PVOID *, ULONG *))WPP_MAIN_CB.Queue.ListEntry.Flink[137].Flink)(
           WPP_MAIN_CB.Queue.ListEntry.Blink,
           a3,
           0,
           &VirtualAddress,
           Length) < 0 )
    {
      VirtualAddress = 0;
      *(_QWORD *)Length = 0;
      goto LABEL_32;
    }
    if ( *(_QWORD *)Length > 0xFFFFFFFF )
    {
LABEL_19:
      Instance = -1073741811;
    }
    else
    {
      if ( !VirtualAddress )
        goto LABEL_32;
      Mdl = IoAllocateMdl(VirtualAddress, Length[0], 0, 1u, 0);
      v12 = Mdl;
      if ( !Mdl )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids);
        Instance = -1073741670;
        goto LABEL_38;
      }
      Instance = FxProbeAndLockForWrite(Mdl);
      if ( Instance >= 0 )
      {
        v13 = 1;
LABEL_32:
        ((void (__fastcall *)(struct _LIST_ENTRY *, struct CSimpleHash *))WPP_MAIN_CB.Queue.ListEntry.Flink[155].Flink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          *this);
        Instance = CTsUrbResult::CreateInstance(
                     (void ***)(v22 + 40),
                     PoolWithTag,
                     *(unsigned __int16 *)PoolWithTag,
                     v10,
                     this[7],
                     this[5],
                     this[6],
                     v12,
                     (void ****)&v23);
        ((void (__fastcall *)(struct _LIST_ENTRY *, struct CSimpleHash *))WPP_MAIN_CB.Queue.ListEntry.Flink[155].Blink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          *this);
        if ( Instance >= 0 )
        {
          v12 = 0;
          v13 = 0;
          v17 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFDEVICE__ *, struct WDFREQUEST__ *))WPP_MAIN_CB.Queue.ListEntry.Flink[45].Blink)(
                  WPP_MAIN_CB.Queue.ListEntry.Blink,
                  a2,
                  a3);
          Instance = v17;
          if ( v17 >= 0 )
          {
            Instance = 0;
          }
          else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              15,
              WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids,
              (unsigned int)v17);
          }
        }
      }
    }
LABEL_38:
    ExFreePoolWithTag(PoolWithTag, 0);
    if ( v12 )
    {
      if ( v13 )
        MmUnlockPages(v12);
      IoFreeMdl(v12);
    }
    goto LABEL_45;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids, (unsigned int)v8);
LABEL_46:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids);
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[131].Blink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a3,
    (unsigned int)Instance);
}

```

## disassembly

```asm
0x140002c60  mov     [rsp-38h+arg_10], rbx
0x140002c65  mov     [rsp-38h+arg_8], rdx
0x140002c6a  mov     [rsp-38h+arg_0], rcx
0x140002c6f  push    rbp
0x140002c70  push    rsi
0x140002c71  push    rdi
0x140002c72  push    r12
0x140002c74  push    r13
0x140002c76  push    r14
0x140002c78  push    r15
0x140002c7a  mov     rbp, rsp
0x140002c7d  sub     rsp, 80h
0x140002c84  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002c8b  mov     r13, r8
0x140002c8e  mov     r8, cs:off_140009018
0x140002c95  mov     rdx, r13
0x140002c98  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002c9f  mov     [rbp+arg_18], 0
0x140002ca7  mov     qword ptr [rbp+Length], 0
0x140002caf  mov     [rbp+var_20], 0
0x140002cb7  mov     [rbp+VirtualAddress], 0
0x140002cbf  mov     [rbp+var_8], 0
0x140002cc7  mov     [rbp+var_18], 0
0x140002ccf  mov     rax, [rax+650h]
0x140002cd6  call    _guard_dispatch_icall
0x140002cdb  mov     rdi, rax
0x140002cde  mov     [rbp+var_10], rax
0x140002ce2  lea     r9, [rbp+var_20]
0x140002ce6  mov     r8d, 8
0x140002cec  mov     rdx, r13
0x140002cef  mov     byte ptr [rax+20h], 1
0x140002cf3  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x140002cfa  mov     rax, [rcx+888h]
0x140002d01  lea     rcx, [rbp+arg_18]
0x140002d05  mov     [rsp+80h+Irp], rcx
0x140002d0a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002d11  call    _guard_dispatch_icall
0x140002d16  mov     ebx, eax
0x140002d18  test    eax, eax
0x140002d1a  js      loc_140003079
0x140002d20  mov     r8, [rbp+var_20]
0x140002d24  test    r8, r8
0x140002d27  jz      loc_140003079
0x140002d2d  mov     r9, [rbp+arg_18]
0x140002d31  test    r9, r9
0x140002d34  jz      loc_140003079
0x140002d3a  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002d41  add     rdi, 6E8h
0x140002d48  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002d4f  mov     rdx, r13
0x140002d52  mov     [rsp+80h+Irp], rdi
0x140002d57  mov     rax, [rax+8B8h]
0x140002d5e  call    _guard_dispatch_icall
0x140002d63  mov     ebx, eax
0x140002d65  test    eax, eax
0x140002d67  jns     short loc_140002DA7
0x140002d69  mov     rcx, cs:WPP_GLOBAL_Control
0x140002d70  lea     rdi, WPP_GLOBAL_Control
0x140002d77  cmp     rcx, rdi
0x140002d7a  jz      loc_1400030AE
0x140002d80  cmp     byte ptr [rcx+29h], 2
0x140002d84  jb      loc_1400030AE
0x140002d8a  mov     rcx, [rcx+18h]
0x140002d8e  lea     r8, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids
0x140002d95  mov     edx, 0Bh
0x140002d9a  mov     r9d, eax
0x140002d9d  call    WPP_SF_d
0x140002da2  jmp     loc_1400030AE
0x140002da7  mov     r14, [rbp+arg_18]
0x140002dab  cmp     r14, 0FFFFh
0x140002db2  jbe     short loc_140002DE8
0x140002db4  mov     rcx, cs:WPP_GLOBAL_Control
0x140002dbb  lea     rdi, WPP_GLOBAL_Control
0x140002dc2  cmp     rcx, rdi
0x140002dc5  jz      short loc_140002DDE
0x140002dc7  cmp     byte ptr [rcx+29h], 2
0x140002dcb  jb      short loc_140002DDE
0x140002dcd  mov     rcx, [rcx+18h]
0x140002dd1  mov     edx, 0Ch
0x140002dd6  mov     r9, r14
0x140002dd9  call    WPP_SF_i
0x140002dde  mov     ebx, 0C000000Dh
0x140002de3  jmp     loc_1400030AE
0x140002de8  movzx   edx, r14w; NumberOfBytes
0x140002dec  mov     ecx, 200h; PoolType
0x140002df1  mov     r8d, 47555354h; Tag
0x140002df7  call    cs:__imp_ExAllocatePoolWithTag
0x140002dfe  nop     dword ptr [rax+rax+00h]
0x140002e03  mov     r15, rax
0x140002e06  test    rax, rax
0x140002e09  jnz     short loc_140002E45
0x140002e0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140002e12  lea     rdi, WPP_GLOBAL_Control
0x140002e19  cmp     rcx, rdi
0x140002e1c  jz      short loc_140002E3B
0x140002e1e  cmp     byte ptr [rcx+29h], 2
0x140002e22  jb      short loc_140002E3B
0x140002e24  mov     rcx, [rcx+18h]
0x140002e28  lea     edx, [rax+0Dh]
0x140002e2b  movzx   r9d, r14w
0x140002e2f  lea     r8, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids
0x140002e36  call    WPP_SF_d
0x140002e3b  mov     ebx, 0C0000017h
0x140002e40  jmp     loc_1400030AE
0x140002e45  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002e4c  lea     r8, [rbp+var_18]
0x140002e50  mov     rdx, [rdi]
0x140002e53  xor     esi, esi
0x140002e55  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002e5c  xor     r12b, r12b
0x140002e5f  mov     rax, [rax+610h]
0x140002e66  call    _guard_dispatch_icall
0x140002e6b  lea     edx, [rsi+8]
0x140002e6e  lea     rdi, WPP_GLOBAL_Control
0x140002e75  mov     rcx, [rax]
0x140002e78  mov     [r15], rcx
0x140002e7b  movzx   ecx, cx
0x140002e7e  cmp     cx, dx
0x140002e81  jnb     short loc_140002E8D
0x140002e83  mov     ebx, 0C000000Dh
0x140002e88  jmp     loc_14000303E
0x140002e8d  cmp     cx, r14w
0x140002e91  ja      short loc_140002E83
0x140002e93  mov     r8, rcx
0x140002e96  lea     rcx, [r15+8]; void *
0x140002e9a  sub     r8, rdx; Size
0x140002e9d  lea     rdx, [rax+8]; Src
0x140002ea1  call    memmove
0x140002ea6  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002ead  lea     rcx, [rbp+Length]
0x140002eb1  mov     [rsp+80h+Irp], rcx
0x140002eb6  lea     r9, [rbp+VirtualAddress]
0x140002eba  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002ec1  xor     r8d, r8d
0x140002ec4  mov     rdx, r13
0x140002ec7  mov     rax, [rax+890h]
0x140002ece  call    _guard_dispatch_icall
0x140002ed3  xor     ebx, ebx
0x140002ed5  test    eax, eax
0x140002ed7  jns     short loc_140002EE3
0x140002ed9  mov     [rbp+VirtualAddress], rbx
0x140002edd  mov     qword ptr [rbp+Length], rbx
0x140002ee1  jmp     short loc_140002F5D
0x140002ee3  mov     rdx, qword ptr [rbp+Length]; Length
0x140002ee7  mov     eax, 0FFFFFFFFh
0x140002eec  cmp     rdx, rax
0x140002eef  ja      short loc_140002E83
0x140002ef1  mov     rcx, [rbp+VirtualAddress]; VirtualAddress
0x140002ef5  test    rcx, rcx
0x140002ef8  jz      short loc_140002F5D
0x140002efa  mov     r9b, 1; ChargeQuota
0x140002efd  mov     [rsp+80h+Irp], rbx; Irp
0x140002f02  xor     r8d, r8d; SecondaryBuffer
0x140002f05  call    cs:__imp_IoAllocateMdl
0x140002f0c  nop     dword ptr [rax+rax+00h]
0x140002f11  mov     rsi, rax
0x140002f14  test    rax, rax
0x140002f17  jnz     short loc_140002F48
0x140002f19  mov     rcx, cs:WPP_GLOBAL_Control
0x140002f20  cmp     rcx, rdi
0x140002f23  jz      short loc_140002F3E
0x140002f25  cmp     byte ptr [rcx+29h], 2
0x140002f29  jb      short loc_140002F3E
0x140002f2b  mov     rcx, [rcx+18h]
0x140002f2f  lea     edx, [rax+0Eh]
0x140002f32  lea     r8, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids
0x140002f39  call    WPP_SF_
0x140002f3e  mov     ebx, 0C000009Ah
0x140002f43  jmp     loc_14000303E
0x140002f48  mov     rcx, rax
0x140002f4b  call    FxProbeAndLockForWrite
0x140002f50  mov     ebx, eax
0x140002f52  test    eax, eax
0x140002f54  js      loc_14000303E
0x140002f5a  mov     r12b, 1
0x140002f5d  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002f64  mov     rbx, [rbp+arg_0]
0x140002f68  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002f6f  mov     rax, [rax+9B0h]
0x140002f76  mov     rdx, [rbx]
0x140002f79  call    _guard_dispatch_icall
0x140002f7e  mov     rcx, [rbp+var_10]
0x140002f82  lea     rax, [rbp+var_8]
0x140002f86  movzx   r8d, word ptr [r15]; unsigned int
0x140002f8a  add     rcx, 28h ; '('; void *
0x140002f8e  mov     [rsp+80h+var_40], rax; struct CTsUrbResult **
0x140002f93  mov     rdx, r15; unsigned __int8 *
0x140002f96  mov     rax, [rbx+30h]
0x140002f9a  mov     [rsp+80h+var_48], rsi; struct _MDL *
0x140002f9f  mov     [rsp+80h+var_50], rax; struct CSimpleHash *
0x140002fa4  mov     rax, [rbx+28h]
0x140002fa8  mov     [rsp+80h+var_58], rax; struct CSimpleHash *
0x140002fad  mov     rax, [rbx+38h]
0x140002fb1  movzx   r9d, r14w; unsigned int
0x140002fb5  mov     [rsp+80h+Irp], rax; struct CSimpleHash *
0x140002fba  call    ?CreateInstance@CTsUrbResult@@SAJPEAXPEAEKKPEAVCSimpleHash@@22PEAU_MDL@@PEAPEAV1@@Z; CTsUrbResult::CreateInstance(void *,uchar *,ulong,ulong,CSimpleHash *,CSimpleHash *,CSimpleHash *,_MDL *,CTsUrbResult * *)
0x140002fbf  mov     rcx, [rbp+arg_0]
0x140002fc3  mov     ebx, eax
0x140002fc5  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002fcc  mov     rdx, [rcx]
0x140002fcf  mov     rax, [rax+9B8h]
0x140002fd6  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002fdd  call    _guard_dispatch_icall
0x140002fe2  test    ebx, ebx
0x140002fe4  js      short loc_14000303E
0x140002fe6  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002fed  mov     r8, r13
0x140002ff0  mov     rdx, [rbp+arg_8]
0x140002ff4  xor     esi, esi
0x140002ff6  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002ffd  xor     r12b, r12b
0x140003000  mov     rax, [rax+2D8h]
0x140003007  call    _guard_dispatch_icall
0x14000300c  mov     ebx, eax
0x14000300e  test    eax, eax
0x140003010  jns     short loc_14000303C
0x140003012  mov     rcx, cs:WPP_GLOBAL_Control
0x140003019  cmp     rcx, rdi
0x14000301c  jz      short loc_14000303E
0x14000301e  cmp     byte ptr [rcx+29h], 2
0x140003022  jb      short loc_14000303E
0x140003024  mov     rcx, [rcx+18h]
0x140003028  lea     edx, [rsi+0Fh]
0x14000302b  mov     r9d, eax
0x14000302e  lea     r8, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids
0x140003035  call    WPP_SF_d
0x14000303a  jmp     short loc_14000303E
0x14000303c  xor     ebx, ebx
0x14000303e  xor     edx, edx; Tag
0x140003040  mov     rcx, r15; P
0x140003043  call    cs:__imp_ExFreePoolWithTag
0x14000304a  nop     dword ptr [rax+rax+00h]
0x14000304f  test    rsi, rsi
0x140003052  jz      short loc_1400030AA
0x140003054  test    r12b, r12b
0x140003057  jz      short loc_140003068
0x140003059  mov     rcx, rsi; MemoryDescriptorList
0x14000305c  call    cs:__imp_MmUnlockPages
0x140003063  nop     dword ptr [rax+rax+00h]
0x140003068  mov     rcx, rsi; Mdl
0x14000306b  call    cs:__imp_IoFreeMdl
0x140003072  nop     dword ptr [rax+rax+00h]
0x140003077  jmp     short loc_1400030AA
0x140003079  mov     rcx, cs:WPP_GLOBAL_Control
0x140003080  lea     rdi, WPP_GLOBAL_Control
0x140003087  cmp     rcx, rdi
0x14000308a  jz      short loc_1400030AA
0x14000308c  cmp     byte ptr [rcx+29h], 2
0x140003090  jb      short loc_1400030AA
0x140003092  mov     rcx, [rcx+18h]
0x140003096  lea     r8, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids
0x14000309d  mov     edx, 0Ah
0x1400030a2  mov     r9d, eax
0x1400030a5  call    WPP_SF_d
0x1400030aa  test    ebx, ebx
0x1400030ac  jns     short loc_1400030F5
0x1400030ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400030b5  cmp     rcx, rdi
0x1400030b8  jz      short loc_1400030D5
0x1400030ba  cmp     byte ptr [rcx+29h], 2
0x1400030be  jb      short loc_1400030D5
0x1400030c0  mov     rcx, [rcx+18h]
0x1400030c4  lea     r8, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids
0x1400030cb  mov     edx, 10h
0x1400030d0  call    WPP_SF_
0x1400030d5  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400030dc  mov     r8d, ebx
0x1400030df  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400030e6  mov     rdx, r13
0x1400030e9  mov     rax, [rax+838h]
0x1400030f0  call    _guard_dispatch_icall
0x1400030f5  mov     rbx, [rsp+80h+arg_10]
0x1400030fd  add     rsp, 80h
0x140003104  pop     r15
0x140003106  pop     r14
0x140003108  pop     r13
0x14000310a  pop     r12
0x14000310c  pop     rdi
0x14000310d  pop     rsi
0x14000310e  pop     rbp
0x14000310f  retn
```
