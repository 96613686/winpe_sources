# PtInternalDeviceControl

- ea: `0x140001ce0`
- end: `0x1400023be`
- name: `PtInternalDeviceControl`
- size: `1758`
- prototype: `__int64 __fastcall(__int64, IRP *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000173c`
- `0x1400017e8`
- `0x140001a80`
- `0x140001ce0`
- `0x140003200`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140001d79`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140001d79`
- `ntoskrnl!IofCompleteRequest` at `0x140001d93`
- `ntoskrnl!IofCompleteRequest` at `0x1400020a5`
- `ntoskrnl!IofCompleteRequest` at `0x140002355`
- `ntoskrnl!IofCompleteRequest` at `0x140001d93`
- `ntoskrnl!IofCompleteRequest` at `0x1400020a5`
- `ntoskrnl!IofCompleteRequest` at `0x140002355`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140002371`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140002371`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002026`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002026`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002086`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002086`

## pseudocode

```c
__int64 __fastcall PtInternalDeviceControl(__int64 a1, IRP *a2, int a3)
{
  unsigned int v5; // ebx
  int v6; // r9d
  __int64 v7; // rbx
  struct _IO_REMOVE_LOCK *v8; // r15
  NTSTATUS v9; // eax
  int v10; // edx
  int v11; // r8d
  unsigned int v12; // esi
  int v13; // edx
  int v14; // r8d
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  unsigned int LowPart; // ecx
  int v18; // r9d
  int v19; // r9d
  struct _IRP *v20; // rcx
  struct _IRP *v21; // rcx
  KIRQL v22; // al
  __int64 v23; // rsi
  _WORD *v24; // rcx
  int v25; // r9d
  struct _IRP *MasterIrp; // rcx
  int v27; // r9d
  struct _IRP *v28; // rax
  int v29; // r9d

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      a3,
      22,
      (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
  if ( *(_DWORD *)(a1 + 72) == 56 )
  {
    v5 = -1073741808;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v6 = 23;
LABEL_104:
      WPP_RECORDER_SF_sqd(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        a3,
        v6,
        (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
      return v5;
    }
    return v5;
  }
  a2->IoStatus.Information = 0;
  v7 = *(_QWORD *)(a1 + 64);
  v8 = (struct _IO_REMOVE_LOCK *)(v7 + 24);
  v9 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v7 + 24), &PtInternalDeviceControl, File, 1u, 0x20u);
  v12 = v9;
  if ( v9 >= 0 )
  {
    CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
    LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
    if ( LowPart <= 0xB0403 )
    {
      if ( LowPart != 721923 )
      {
        switch ( LowPart )
        {
          case 0xB0000u:
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_s(
                WPP_GLOBAL_Control->DeviceExtension,
                v10,
                v11,
                33,
                (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
            if ( CurrentStackLocation->Parameters.Read.Length >= 0x1C )
            {
              MasterIrp = a2->AssociatedIrp.MasterIrp;
              *(_DWORD *)&MasterIrp->Type = 65617;
              *(_DWORD *)(&MasterIrp->Size + 1) = 196620;
              LOWORD(MasterIrp->MdlAddress) = 101;
              HIDWORD(MasterIrp->MdlAddress) = 100;
              MasterIrp->Flags = 0x20000;
              *(&MasterIrp->Flags + 1) = 250;
              MasterIrp->AssociatedIrp.IrpCount = 65536030;
              a2->IoStatus.Information = 28;
              goto LABEL_33;
            }
            goto LABEL_37;
          case 0xB0004u:
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_33;
            v25 = 38;
            break;
          case 0xB0008u:
            if ( CurrentStackLocation->Parameters.Create.Options < 4 )
              goto LABEL_37;
            v21 = a2->AssociatedIrp.MasterIrp;
            if ( *(_WORD *)(v7 + 220) != (v21->Size & 0xF) )
            {
              *(_WORD *)(v7 + 218) = v21->Type;
              *(_WORD *)(v7 + 220) = a2->AssociatedIrp.MasterIrp->Size & 0xF;
              if ( (a2->AssociatedIrp.MasterIrp->Size & 0x8000u) != 0 )
              {
                v22 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v7 + 232));
                v23 = *(_QWORD *)(v7 + 224);
                *(_BYTE *)(v7 + 222) = 1;
                if ( v23 )
                {
                  if ( _InterlockedExchange64((volatile __int64 *)(v23 + 104), 0) )
                  {
                    v24 = *(_WORD **)(v23 + 24);
                    *v24 = *(_WORD *)(v7 + 218);
                    v24[2] = *(_WORD *)(v7 + 220);
                    *(_DWORD *)(v23 + 48) = 0;
                    *(_QWORD *)(v7 + 224) = 0;
                    *(_BYTE *)(v7 + 222) = 0;
                  }
                  else
                  {
                    v23 = 0;
                  }
                }
                KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 232), v22);
                if ( v23 )
                {
                  *(_QWORD *)(v23 + 56) = 12;
                  IofCompleteRequest((PIRP)v23, 0);
                }
              }
            }
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_33;
            v25 = 36;
            break;
          default:
            switch ( LowPart )
            {
              case 0xB0020u:
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  WPP_RECORDER_SF_s(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v10,
                    v11,
                    37,
                    (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
                if ( CurrentStackLocation->Parameters.Read.Length >= 6 )
                {
                  *(_DWORD *)&a2->AssociatedIrp.MasterIrp->Size = 16384030;
                  a2->IoStatus.Information = 6;
                  goto LABEL_33;
                }
                break;
              case 0xB0040u:
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  WPP_RECORDER_SF_s(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v10,
                    v11,
                    35,
                    (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
                if ( CurrentStackLocation->Parameters.Read.Length >= 4 )
                {
                  a2->AssociatedIrp.MasterIrp->Size = 0;
                  a2->AssociatedIrp.MasterIrp->Type = 0;
                  a2->IoStatus.Information = 4;
                  goto LABEL_33;
                }
                break;
              case 0xB0080u:
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  WPP_RECORDER_SF_s(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v10,
                    v11,
                    34,
                    (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
                if ( CurrentStackLocation->Parameters.Read.Length >= 0xE )
                {
                  v20 = a2->AssociatedIrp.MasterIrp;
                  v20->Type = 3;
                  memmove(&v20->Size, qword_1400051A0, 0xCu);
                  a2->IoStatus.Information = 14;
                  goto LABEL_33;
                }
                break;
              case 0xB0203u:
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  WPP_RECORDER_SF_s(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v10,
                    v11,
                    25,
                    (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
                if ( *(_QWORD *)(v7 + 80) )
                {
                  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  {
LABEL_25:
                    v5 = -1073741757;
                    goto LABEL_102;
                  }
                  v18 = 26;
LABEL_24:
                  WPP_RECORDER_SF_s(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v10,
                    v11,
                    v18,
                    (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
                  goto LABEL_25;
                }
                if ( CurrentStackLocation->Parameters.Create.Options < 0x10 )
                {
                  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  {
LABEL_30:
                    v5 = -1073741811;
                    goto LABEL_102;
                  }
                  v19 = 27;
LABEL_29:
                  WPP_RECORDER_SF_s(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v10,
                    v11,
                    v19,
                    (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
                  goto LABEL_30;
                }
                _InterlockedAdd((volatile signed __int32 *)&WPP_MAIN_CB.Queue.Wcb.DeviceContext, 1u);
                *(_BYTE *)(v7 + 88) = 1;
LABEL_32:
                *(_OWORD *)(v7 + 72) = *(_OWORD *)&CurrentStackLocation->Parameters.CreatePipe.Parameters->NamedPipeType;
LABEL_33:
                v5 = 0;
                goto LABEL_102;
              default:
                goto LABEL_76;
            }
LABEL_37:
            v5 = -1073741789;
            goto LABEL_102;
        }
        WPP_RECORDER_SF_s(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          v11,
          v25,
          (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
        goto LABEL_33;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
LABEL_68:
        v5 = -1073741822;
        goto LABEL_102;
      }
      v27 = 28;
LABEL_67:
      WPP_RECORDER_SF_s(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        v11,
        v27,
        (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
      goto LABEL_68;
    }
    if ( LowPart == 724996 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v29 = 39;
        goto LABEL_100;
      }
    }
    else
    {
      if ( LowPart != 737223 )
      {
        switch ( LowPart )
        {
          case 0xB3FCBu:
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_s(
                WPP_GLOBAL_Control->DeviceExtension,
                v10,
                v11,
                42,
                (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
            v5 = -1073741637;
LABEL_102:
            a2->IoStatus.Status = v5;
            IofCompleteRequest(a2, 0);
            IoReleaseRemoveLockEx(v8, &PtInternalDeviceControl, 0x20u);
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v6 = 44;
              goto LABEL_104;
            }
            return v5;
          case 0xF0000u:
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_s(
                WPP_GLOBAL_Control->DeviceExtension,
                v10,
                v11,
                40,
                (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
            if ( CurrentStackLocation->Parameters.Read.Length >= 0xC )
            {
              v28 = a2->AssociatedIrp.MasterIrp;
              *(_DWORD *)&v28->Type = 131074;
              *(&v28->Size + 1) = 60;
              LODWORD(v28->MdlAddress) = 0;
              a2->IoStatus.Information = 12;
              goto LABEL_33;
            }
            goto LABEL_37;
          case 0xF0203u:
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_s(
                WPP_GLOBAL_Control->DeviceExtension,
                v10,
                v11,
                29,
                (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
            if ( *(_QWORD *)(v7 + 80) )
            {
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                goto LABEL_25;
              v18 = 30;
              goto LABEL_24;
            }
            if ( CurrentStackLocation->Parameters.Create.Options < 0x10 )
            {
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                goto LABEL_30;
              v19 = 31;
              goto LABEL_29;
            }
            _InterlockedAdd((_DWORD *)&WPP_MAIN_CB.Queue.Wcb.DeviceContext + 1, 1u);
            *(_BYTE *)(v7 + 88) = 0;
            goto LABEL_32;
          case 0xF0403u:
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_68;
            v27 = 32;
            goto LABEL_67;
        }
        if ( LowPart != 999367 )
        {
LABEL_76:
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_sD(
              WPP_GLOBAL_Control->DeviceExtension,
              v10,
              v11,
              43,
              (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
          goto LABEL_101;
        }
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v29 = 41;
LABEL_100:
        WPP_RECORDER_SF_s(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          v11,
          v29,
          (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
      }
    }
LABEL_101:
    v5 = -1073741808;
    goto LABEL_102;
  }
  a2->IoStatus.Status = v9;
  IofCompleteRequest(a2, 0);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sqd(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      v14,
      24,
      (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
  return v12;
}

```

## disassembly

```asm
0x140001ce0  push    rbx
0x140001ce2  push    rbp
0x140001ce3  push    rsi
0x140001ce4  push    rdi
0x140001ce5  push    r12
0x140001ce7  push    r13
0x140001ce9  push    r14
0x140001ceb  push    r15
0x140001ced  sub     rsp, 48h
0x140001cf1  mov     rdi, rdx
0x140001cf4  mov     r14, rcx
0x140001cf7  lea     r12, WPP_RECORDER_INITIALIZED
0x140001cfe  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140001d05  lea     rbp, WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids
0x140001d0c  jz      short loc_140001D29
0x140001d0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140001d15  mov     r9d, 16h
0x140001d1b  mov     qword ptr [rsp+88h+RemlockSize], rbp
0x140001d20  mov     rcx, [rcx+40h]
0x140001d24  call    WPP_RECORDER_SF_s
0x140001d29  cmp     dword ptr [r14+48h], 38h ; '8'
0x140001d2e  jnz     short loc_140001D4D
0x140001d30  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140001d37  mov     ebx, 0C0000010h
0x140001d3c  jz      loc_1400023AA
0x140001d42  mov     r9d, 17h
0x140001d48  jmp     loc_14000238C
0x140001d4d  xor     r13d, r13d
0x140001d50  mov     [rsp+88h+RemlockSize], 20h ; ' '; RemlockSize
0x140001d58  mov     [rdi+38h], r13
0x140001d5c  lea     r8, File; File
0x140001d63  mov     rbx, [r14+40h]
0x140001d67  lea     rdx, PtInternalDeviceControl; Tag
0x140001d6e  lea     r9d, [r13+1]; Line
0x140001d72  lea     r15, [rbx+18h]
0x140001d76  mov     rcx, r15; RemoveLock
0x140001d79  call    cs:__imp_IoAcquireRemoveLockEx
0x140001d80  nop     dword ptr [rax+rax+00h]
0x140001d85  mov     esi, eax
0x140001d87  test    eax, eax
0x140001d89  jns     short loc_140001DD1
0x140001d8b  xor     edx, edx; PriorityBoost
0x140001d8d  mov     [rdi+30h], eax
0x140001d90  mov     rcx, rdi; Irp
0x140001d93  call    cs:__imp_IofCompleteRequest
0x140001d9a  nop     dword ptr [rax+rax+00h]
0x140001d9f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140001da6  jz      short loc_140001DCA
0x140001da8  mov     rcx, cs:WPP_GLOBAL_Control
0x140001daf  lea     r9d, [r13+18h]
0x140001db3  mov     [rsp+88h+var_50], esi
0x140001db7  mov     [rsp+88h+var_58], r14
0x140001dbc  mov     qword ptr [rsp+88h+RemlockSize], rbp
0x140001dc1  mov     rcx, [rcx+40h]
0x140001dc5  call    WPP_RECORDER_SF_sqd
0x140001dca  mov     eax, esi
0x140001dcc  jmp     loc_1400023AC
0x140001dd1  mov     rsi, [rdi+0B8h]
0x140001dd8  mov     eax, 0B0403h
0x140001ddd  mov     ecx, [rsi+18h]
0x140001de0  cmp     ecx, eax
0x140001de2  ja      loc_140002196
0x140001de8  jz      loc_140002168
0x140001dee  mov     eax, ecx
0x140001df0  sub     eax, 0B0000h
0x140001df5  jz      loc_1400020FA
0x140001dfb  sub     eax, 4
0x140001dfe  jz      loc_1400020E5
0x140001e04  sub     eax, 4
0x140001e07  jz      loc_140001FCD
0x140001e0d  sub     eax, 18h
0x140001e10  jz      loc_140001F87
0x140001e16  sub     eax, 20h ; ' '
0x140001e19  jz      loc_140001F3F
0x140001e1f  sub     eax, 40h ; '@'
0x140001e22  jz      loc_140001EE2
0x140001e28  cmp     eax, 183h
0x140001e2d  jnz     loc_1400021DB
0x140001e33  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140001e3a  jz      short loc_140001E57
0x140001e3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140001e43  mov     r9d, 19h
0x140001e49  mov     qword ptr [rsp+88h+RemlockSize], rbp
0x140001e4e  mov     rcx, [rcx+40h]
0x140001e52  call    WPP_RECORDER_SF_s
0x140001e57  cmp     [rbx+50h], r13
0x140001e5b  jz      short loc_140001E8B
0x140001e5d  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140001e64  jz      short loc_140001E81
0x140001e66  mov     r9d, 1Ah
0x140001e6c  mov     rcx, cs:WPP_GLOBAL_Control
0x140001e73  mov     qword ptr [rsp+88h+RemlockSize], rbp
0x140001e78  mov     rcx, [rcx+40h]
0x140001e7c  call    WPP_RECORDER_SF_s
0x140001e81  mov     ebx, 0C0000043h
0x140001e86  jmp     loc_14000234D
0x140001e8b  cmp     dword ptr [rsi+10h], 10h
0x140001e8f  jnb     short loc_140001EBF
0x140001e91  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140001e98  jz      short loc_140001EB5
0x140001e9a  mov     r9d, 1Bh
0x140001ea0  mov     rcx, cs:WPP_GLOBAL_Control
0x140001ea7  mov     qword ptr [rsp+88h+RemlockSize], rbp
0x140001eac  mov     rcx, [rcx+40h]
0x140001eb0  call    WPP_RECORDER_SF_s
0x140001eb5  mov     ebx, 0C000000Dh
0x140001eba  jmp     loc_14000234D
0x140001ebf  mov     eax, 1
0x140001ec4  lock add dword ptr cs:WPP_MAIN_CB.Queue+20h, eax
0x140001ecb  mov     [rbx+58h], al
0x140001ece  mov     rax, [rsi+20h]
0x140001ed2  movups  xmm0, xmmword ptr [rax]
0x140001ed5  movdqu  xmmword ptr [rbx+48h], xmm0
0x140001eda  mov     ebx, r13d
0x140001edd  jmp     loc_14000234D
0x140001ee2  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140001ee9  jz      short loc_140001F06
0x140001eeb  mov     rcx, cs:WPP_GLOBAL_Control
0x140001ef2  mov     r9d, 22h ; '"'
0x140001ef8  mov     qword ptr [rsp+88h+RemlockSize], rbp
0x140001efd  mov     rcx, [rcx+40h]
0x140001f01  call    WPP_RECORDER_SF_s
0x140001f06  cmp     dword ptr [rsi+8], 0Eh
0x140001f0a  jnb     short loc_140001F16
0x140001f0c  mov     ebx, 0C0000023h
0x140001f11  jmp     loc_14000234D
0x140001f16  mov     rcx, [rdi+18h]
0x140001f1a  lea     rdx, qword_1400051A0; Src
0x140001f21  mov     r8d, 0Ch; Size
0x140001f27  mov     word ptr [rcx], 3
0x140001f2c  add     rcx, 2; void *
0x140001f30  call    memmove
0x140001f35  mov     qword ptr [rdi+38h], 0Eh
0x140001f3d  jmp     short loc_140001EDA
0x140001f3f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140001f46  jz      short loc_140001F63
0x140001f48  mov     rcx, cs:WPP_GLOBAL_Control
0x140001f4f  mov     r9d, 23h ; '#'
0x140001f55  mov     qword ptr [rsp+88h+RemlockSize], rbp
0x140001f5a  mov     rcx, [rcx+40h]
0x140001f5e  call    WPP_RECORDER_SF_s
0x140001f63  cmp     dword ptr [rsi+8], 4
0x140001f67  jb      short loc_140001F0C
0x140001f69  mov     rcx, [rdi+18h]
0x140001f6d  mov     [rcx+2], r13w
0x140001f72  mov     rcx, [rdi+18h]
0x140001f76  mov     [rcx], r13w
0x140001f7a  mov     qword ptr [rdi+38h], 4
0x140001f82  jmp     loc_140001EDA
0x140001f87  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140001f8e  jz      short loc_140001FAB
0x140001f90  mov     rcx, cs:WPP_GLOBAL_Control
0x140001f97  mov     r9d, 25h ; '%'
0x140001f9d  mov     qword ptr [rsp+88h+RemlockSize], rbp
0x140001fa2  mov     rcx, [rcx+40h]
0x140001fa6  call    WPP_RECORDER_SF_s
0x140001fab  cmp     dword ptr [rsi+8], 6
0x140001faf  jb      loc_140001F0C
0x140001fb5  mov     rax, [rdi+18h]
0x140001fb9  mov     dword ptr [rax+2], 0FA001Eh
0x140001fc0  mov     qword ptr [rdi+38h], 6
0x140001fc8  jmp     loc_140001EDA
0x140001fcd  cmp     dword ptr [rsi+10h], 4
0x140001fd1  jb      loc_140001F0C
0x140001fd7  mov     rcx, [rdi+18h]
0x140001fdb  movzx   eax, word ptr [rcx+2]
0x140001fdf  and     ax, 0Fh
0x140001fe3  cmp     [rbx+0DCh], ax
0x140001fea  jz      loc_1400020B8
0x140001ff0  movzx   eax, word ptr [rcx]
0x140001ff3  mov     [rbx+0DAh], ax
0x140001ffa  mov     rax, [rdi+18h]
0x140001ffe  movzx   ecx, word ptr [rax+2]
0x140002002  and     cx, 0Fh
0x140002006  mov     [rbx+0DCh], cx
0x14000200d  mov     rax, [rdi+18h]
0x140002011  cmp     [rax+2], r13w
0x140002016  jge     loc_1400020B8
0x14000201c  lea     rbp, [rbx+0E8h]
0x140002023  mov     rcx, rbp; SpinLock
0x140002026  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000202d  nop     dword ptr [rax+rax+00h]
0x140002032  mov     rsi, [rbx+0E0h]
0x140002039  mov     dl, al; NewIrql
0x14000203b  mov     byte ptr [rbx+0DEh], 1
0x140002042  test    rsi, rsi
0x140002045  jz      short loc_140002083
0x140002047  mov     rcx, r13
0x14000204a  xchg    rcx, [rsi+68h]
0x14000204e  test    rcx, rcx
0x140002051  jz      short loc_140002080
0x140002053  mov     rcx, [rsi+18h]
0x140002057  movzx   eax, word ptr [rbx+0DAh]
0x14000205e  mov     [rcx], ax
0x140002061  movzx   eax, word ptr [rbx+0DCh]
0x140002068  mov     [rcx+4], ax
0x14000206c  mov     [rsi+30h], r13d
0x140002070  mov     [rbx+0E0h], r13
0x140002077  mov     [rbx+0DEh], r13b
0x14000207e  jmp     short loc_140002083
0x140002080  mov     rsi, r13
0x140002083  mov     rcx, rbp; SpinLock
0x140002086  call    cs:__imp_KeReleaseSpinLock
0x14000208d  nop     dword ptr [rax+rax+00h]
0x140002092  test    rsi, rsi
0x140002095  jz      short loc_1400020B1
0x140002097  mov     edx, 0Ch
0x14000209c  mov     rcx, rsi; Irp
0x14000209f  mov     [rsi+38h], rdx
0x1400020a3  xor     edx, edx; PriorityBoost
0x1400020a5  call    cs:__imp_IofCompleteRequest
0x1400020ac  nop     dword ptr [rax+rax+00h]
0x1400020b1  lea     rbp, WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids
0x1400020b8  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400020bf  jz      loc_140001EDA
0x1400020c5  mov     r9d, 24h ; '$'
0x1400020cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400020d2  mov     qword ptr [rsp+88h+RemlockSize], rbp
0x1400020d7  mov     rcx, [rcx+40h]
0x1400020db  call    WPP_RECORDER_SF_s
0x1400020e0  jmp     loc_140001EDA
0x1400020e5  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400020ec  jz      loc_140001EDA
0x1400020f2  mov     r9d, 26h ; '&'
0x1400020f8  jmp     short loc_1400020CB
0x1400020fa  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140002101  jz      short loc_14000211E
0x140002103  mov     rcx, cs:WPP_GLOBAL_Control
0x14000210a  mov     r9d, 21h ; '!'
0x140002110  mov     qword ptr [rsp+88h+RemlockSize], rbp
0x140002115  mov     rcx, [rcx+40h]
0x140002119  call    WPP_RECORDER_SF_s
0x14000211e  cmp     dword ptr [rsi+8], 1Ch
0x140002122  jb      loc_140001F0C
0x140002128  mov     rcx, [rdi+18h]
0x14000212c  mov     dword ptr [rcx], 10051h
0x140002132  mov     dword ptr [rcx+4], 3000Ch
0x140002139  mov     word ptr [rcx+8], 65h ; 'e'
0x14000213f  mov     dword ptr [rcx+0Ch], 64h ; 'd'
0x140002146  mov     dword ptr [rcx+10h], 20000h
0x14000214d  mov     dword ptr [rcx+14h], 0FAh
0x140002154  mov     dword ptr [rcx+18h], 3E8001Eh
0x14000215b  mov     qword ptr [rdi+38h], 1Ch
0x140002163  jmp     loc_140001EDA
0x140002168  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000216f  jz      short loc_14000218C
0x140002171  mov     r9d, 1Ch
0x140002177  mov     rcx, cs:WPP_GLOBAL_Control
0x14000217e  mov     qword ptr [rsp+88h+RemlockSize], rbp
0x140002183  mov     rcx, [rcx+40h]
0x140002187  call    WPP_RECORDER_SF_s
0x14000218c  mov     ebx, 0C0000002h
0x140002191  jmp     loc_14000234D
0x140002196  mov     eax, ecx
0x140002198  sub     eax, 0B1004h
0x14000219d  jz      loc_140002324
0x1400021a3  sub     eax, 2FC3h
0x1400021a8  jz      loc_140002313
0x1400021ae  sub     eax, 4
0x1400021b1  jz      loc_1400022E8
0x1400021b7  sub     eax, 3C035h
0x1400021bc  jz      loc_140002299
0x1400021c2  sub     eax, 203h
0x1400021c7  jz      short loc_140002224
0x1400021c9  sub     eax, 200h
0x1400021ce  jz      short loc_14000220C
0x1400021d0  cmp     eax, 3BC4h
0x1400021d5  jz      loc_140002313
0x1400021db  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400021e2  jz      loc_140002348
0x1400021e8  mov     dword ptr [rsp+88h+var_58], ecx
0x1400021ec  mov     r9d, 2Bh ; '+'
0x1400021f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400021f9  mov     qword ptr [rsp+88h+RemlockSize], rbp
0x1400021fe  mov     rcx, [rcx+40h]
0x140002202  call    WPP_RECORDER_SF_sD
0x140002207  jmp     loc_140002348
0x14000220c  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140002213  jz      loc_14000218C
0x140002219  mov     r9d, 20h ; ' '
0x14000221f  jmp     loc_140002177
0x140002224  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000222b  jz      short loc_140002248
0x14000222d  mov     rcx, cs:WPP_GLOBAL_Control
0x140002234  mov     r9d, 1Dh
0x14000223a  mov     qword ptr [rsp+88h+RemlockSize], rbp
0x14000223f  mov     rcx, [rcx+40h]
0x140002243  call    WPP_RECORDER_SF_s
0x140002248  cmp     [rbx+50h], r13
0x14000224c  jz      short loc_140002266
0x14000224e  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140002255  jz      loc_140001E81
0x14000225b  mov     r9d, 1Eh
0x140002261  jmp     loc_140001E6C
0x140002266  cmp     dword ptr [rsi+10h], 10h
0x14000226a  jnb     short loc_140002284
0x14000226c  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140002273  jz      loc_140001EB5
0x140002279  mov     r9d, 1Fh
0x14000227f  jmp     loc_140001EA0
  ... truncated ...
```
