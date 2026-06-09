# SrvNetWskReceiveEvent

- ea: `0x140018de0`
- end: `0x140019591`
- name: `SrvNetWskReceiveEvent`
- size: `1969`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002060`
- `0x140002650`
- `0x140002a10`
- `0x14000380c`
- `0x140003a90`
- `0x140012b50`
- `0x14001389c`
- `0x140016384`
- `0x140016c84`
- `0x140016cc8`
- `0x140018de0`
- `0x140019868`
- `0x14002a3e0`
- `0x14002a4c0`
- `0x14002a540`

## import_xrefs

- `ntoskrnl!IoAllocateIrp` at `0x140019370`
- `ntoskrnl!IoAllocateIrp` at `0x140019370`
- `ntoskrnl!IoClearActivityIdThread` at `0x140019025`
- `ntoskrnl!IoClearActivityIdThread` at `0x140019025`
- `ntoskrnl!IoSetActivityIdThread` at `0x140018fca`
- `ntoskrnl!IoSetActivityIdThread` at `0x140018fca`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400190e7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400191a0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400191c4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400192a3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400192cb`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400194a4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400190e7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400191a0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400191c4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400192a3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400192cb`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400194a4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018e80`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001915f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018e80`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001915f`
- `TDI!TdiCopyBufferToMdl` at `0x14001909b`
- `TDI!TdiCopyBufferToMdl` at `0x14001909b`

## pseudocode

```c
__int64 __fastcall SrvNetWskReceiveEvent(__int64 a1, __int64 a2, unsigned __int64 a3, unsigned __int64 a4, _QWORD *a5)
{
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // r13
  __int64 *v7; // rax
  unsigned int v9; // r12d
  KIRQL v10; // al
  int v11; // r8d
  KIRQL v12; // r15
  __int64 v13; // rax
  int v14; // ebx
  unsigned __int32 v15; // esi
  _QWORD *v16; // r13
  int v17; // eax
  int v18; // ebx
  ULONG v19; // ecx
  ULONG v20; // ebx
  __int64 v21; // rax
  __int64 v22; // rbx
  void *v23; // rcx
  size_t v24; // r8
  unsigned __int64 v25; // rax
  KIRQL v26; // al
  __int64 *v27; // rcx
  _QWORD *v28; // rax
  __int64 result; // rax
  PDEVICE_OBJECT v30; // rcx
  __int64 v31; // rdx
  PDEVICE_OBJECT v32; // rcx
  __int64 v33; // rdx
  __int64 Buffer; // rax
  __int64 v35; // rbx
  PIRP Irp; // r9
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  unsigned __int64 v38; // rax
  int v39; // eax
  char v40; // [rsp+40h] [rbp-C0h]
  ULONG SourceOffset; // [rsp+44h] [rbp-BCh] BYREF
  ULONG BytesCopied; // [rsp+48h] [rbp-B8h] BYREF
  PVOID SourceBuffer; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v44; // [rsp+58h] [rbp-A8h]
  __int64 v45; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v46; // [rsp+68h] [rbp-98h]
  unsigned __int64 v47; // [rsp+70h] [rbp-90h]
  __int64 v48; // [rsp+78h] [rbp-88h]
  _QWORD *v49; // [rsp+80h] [rbp-80h]
  __int128 v50; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v51[256]; // [rsp+A0h] [rbp-60h] BYREF

  v5 = a3;
  ++indications;
  v49 = a5;
  v6 = a4;
  v7 = *(__int64 **)(a1 + 392);
  v47 = a4;
  v44 = a3;
  v48 = *v7;
  v50 = 0;
  if ( a3 )
  {
    v40 = 0;
    v9 = 0;
    v46 = 0;
    while ( 1 )
    {
      if ( v9 >= v6 )
        goto LABEL_46;
      SourceBuffer = v51;
      v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 80));
      v11 = *(_DWORD *)(a1 + 484);
      v12 = v10;
      if ( v11 >= 4 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qLd(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_0bd25dad6c3a3d1c3ca87626e1622cba_Traceguids, a1, v11);
        }
        goto LABEL_64;
      }
      v13 = *(unsigned int *)(a1 + 104);
      if ( (_DWORD)v13 != 4 )
      {
        if ( !(_DWORD)v13 )
          *(_DWORD *)(a1 + 108) = 0;
        v14 = 4 - v13;
        if ( 4 - v13 >= v6 - v9 )
          v14 = v6 - v9;
        if ( (int)SrvNetCopyIndicationToBufferEx(v44, (int)v13 + (int)a1 + 108, v9, v14, 0) < 0 )
          goto LABEL_63;
        *(_DWORD *)(a1 + 104) += v14;
        v9 += v14;
        if ( *(_DWORD *)(a1 + 104) != 4 )
        {
          KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 80), v12);
          goto LABEL_46;
        }
        v5 = v44;
      }
      v15 = _byteswap_ulong(*(_DWORD *)(a1 + 108));
      if ( v15 > *(_DWORD *)(a1 + 488) || v15 < 0x20 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_0bd25dad6c3a3d1c3ca87626e1622cba_Traceguids, a1, v15);
        }
LABEL_63:
        SrvNetDisconnectConnectionInternalEx(a1, 1);
LABEL_64:
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 80), v12);
        return 3221226011LL;
      }
      v16 = (_QWORD *)(a1 + 88);
      if ( (_QWORD *)*v16 != v16 )
      {
        if ( *(_BYTE *)(a1 + 493) )
        {
          *(_DWORD *)(a1 + 104) = 0;
LABEL_67:
          KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 80), v12);
          Buffer = SrvNetAllocateBuffer(v15, 0);
          v35 = Buffer;
          if ( !Buffer )
          {
            v32 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              v33 = 22;
              goto LABEL_72;
            }
            break;
          }
          *(_QWORD *)(Buffer + 72) = v15;
          *(_QWORD *)(Buffer + 88) = a1;
          Irp = IoAllocateIrp(1, 0);
          if ( !Irp )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_0bd25dad6c3a3d1c3ca87626e1622cba_Traceguids, v15);
            }
            SrvNetFreeBuffer((PVOID)v35);
            break;
          }
          Irp->UserBuffer = 0;
          Irp->Flags = 0;
          Irp->Tail.Overlay.OriginalFileObject = 0;
          CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
          CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&SrvNetWskReceiveComplete;
          CurrentStackLocation[-1].Context = (PVOID)v35;
          CurrentStackLocation[-1].Control = -32;
          if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x10) != 0
            || (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x4000000) != 0 )
          {
            v38 = v44;
            *(_WORD *)(v35 + 22) = 2;
            *(_QWORD *)(v35 + 100) = v38;
            *(_QWORD *)(v35 + 108) = 0;
            *(_QWORD *)(v35 + 116) = Irp;
            *(_QWORD *)(v35 + 124) = 0;
          }
          v39 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(v48 + 56))(*(_QWORD *)(a1 + 392), v35 + 56, 2);
          if ( v39 < 0
            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_Dd(
              WPP_GLOBAL_Control->AttachedDevice,
              24,
              WPP_0bd25dad6c3a3d1c3ca87626e1622cba_Traceguids,
              (unsigned int)v39,
              v15);
          }
        }
        else
        {
          *(_BYTE *)(a1 + 112) = 1;
          KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 80), v12);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_0bd25dad6c3a3d1c3ca87626e1622cba_Traceguids, a1);
          }
        }
LABEL_46:
        *v49 = v9;
        result = 0;
        if ( !v9 )
          return 3221226011LL;
        return result;
      }
      *(_DWORD *)(a1 + 104) = 0;
      if ( v15 > 0x100 )
        goto LABEL_67;
      if ( v15 + v9 > v47 )
        goto LABEL_67;
      v17 = SrvNetCopyIndicationToBufferEx(v5, (unsigned int)v51, v9, v15, (__int64)&SourceBuffer);
      if ( (int)(v17 + 0x80000000) >= 0 && v17 != -1073741807 )
        goto LABEL_67;
      v45 = 0;
      SourceOffset = 0;
      if ( SourceBuffer != v51 )
        ++ultraFastIndications;
      ++fastIndications;
      if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x10) != 0
        || (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x4000000) != 0 )
      {
        v50 = v5;
        v46 = IoSetActivityIdThread(&v50);
        v40 = 1;
      }
      v18 = SrvNetCommonReceiveHandler(
              a1,
              v15,
              (__int64)&SourceOffset,
              0x80000420,
              (__int64)SourceBuffer,
              0,
              (__int64)&v45);
      if ( v40 )
      {
        v40 = 0;
        IoClearActivityIdThread(v46);
      }
      if ( (int)(v18 + 0x80000000) >= 0 && v18 != -1073741802 )
      {
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          goto LABEL_63;
        }
        v31 = 19;
LABEL_62:
        WPP_SF_q(v30->AttachedDevice, v31, WPP_0bd25dad6c3a3d1c3ca87626e1622cba_Traceguids, a1);
        goto LABEL_63;
      }
      v19 = SourceOffset;
      if ( SourceOffset != v15 )
      {
        if ( v18 == -1073741802 && v45 )
        {
          v20 = *(_DWORD *)v45;
          BytesCopied = 0;
          if ( v20 >= v15 - SourceOffset )
            v20 = v15 - SourceOffset;
          TdiCopyBufferToMdl(SourceBuffer, SourceOffset, v20, *(PMDL *)(v45 + 8), 0, &BytesCopied);
          SourceOffset += BytesCopied;
          (*(void (__fastcall **)(_QWORD, _QWORD))(v45 + 16))(v15 != SourceOffset ? 0x80000005 : 0, v20);
          v19 = SourceOffset;
        }
        if ( v19 > v15 )
        {
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
            || !BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            goto LABEL_63;
          }
          v31 = 20;
          goto LABEL_62;
        }
        if ( v19 < v15 )
        {
          KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 80), v12);
          v21 = SrvNetAllocateBuffer(v15 - SourceOffset, 0);
          v22 = v21;
          if ( !v21 )
          {
            v32 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              v33 = 21;
LABEL_72:
              WPP_SF_qD(v32->AttachedDevice, v33, WPP_0bd25dad6c3a3d1c3ca87626e1622cba_Traceguids, a1, v15);
              break;
            }
            break;
          }
          v23 = *(void **)(v21 + 24);
          v24 = v15 - SourceOffset;
          *(_DWORD *)(v21 + 36) = v24;
          *(_QWORD *)(v21 + 72) = v24;
          *(_DWORD *)(v21 + 96) = 0;
          memmove(v23, (char *)SourceBuffer + SourceOffset, v24);
          if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x10) != 0
            || (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x4000000) != 0 )
          {
            v25 = v44;
            *(_WORD *)(v22 + 22) = 1;
            *(_QWORD *)(v22 + 100) = v25;
            *(_QWORD *)(v22 + 108) = 0;
          }
          v26 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 80));
          v27 = *(__int64 **)(a1 + 96);
          v12 = v26;
          if ( (_QWORD *)*v27 != v16 )
            __fastfail(3u);
          v28 = (_QWORD *)*v16;
          *(_QWORD *)v22 = v16;
          *(_QWORD *)(v22 + 8) = v27;
          *v27 = v22;
          *(_QWORD *)(a1 + 96) = v22;
          if ( v28 == v16 )
            SrvNetIndicateData(a1);
        }
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 80), v12);
      v5 = v44;
      v9 += v15;
      v6 = v47;
    }
  }
  SrvNetDisconnectConnectionInternalEx(a1, 0);
  return 3221226011LL;
}

```

## disassembly

```asm
0x140018de0  mov     [rsp-8+arg_8], rbx
0x140018de5  push    rbp
0x140018de6  push    rsi
0x140018de7  push    rdi
0x140018de8  push    r12
0x140018dea  push    r13
0x140018dec  push    r14
0x140018dee  push    r15
0x140018df0  lea     rbp, [rsp-0B0h]
0x140018df8  sub     rsp, 1B0h
0x140018dff  mov     rax, cs:__security_cookie
0x140018e06  xor     rax, rsp
0x140018e09  mov     [rbp+0E0h+var_40], rax
0x140018e10  mov     rax, [rbp+0E0h+arg_20]
0x140018e17  mov     rbx, r8
0x140018e1a  inc     cs:indications
0x140018e20  xorps   xmm0, xmm0
0x140018e23  mov     [rbp+0E0h+var_160], rax
0x140018e27  mov     r13, r9
0x140018e2a  mov     rax, [rcx+188h]
0x140018e31  mov     rdi, rcx
0x140018e34  mov     [rsp+1E0h+var_170], r9
0x140018e39  mov     [rsp+1E0h+var_188], rbx
0x140018e3e  mov     rax, [rax]
0x140018e41  mov     [rsp+1E0h+var_168], rax
0x140018e46  movups  [rbp+0E0h+var_158], xmm0
0x140018e4a  test    r8, r8
0x140018e4d  jz      loc_140019325
0x140018e53  mov     [rsp+1E0h+var_1A0], 0
0x140018e58  xor     r12d, r12d
0x140018e5b  mov     [rsp+1E0h+var_178], 0
0x140018e64  mov     esi, r12d
0x140018e67  cmp     rsi, r13
0x140018e6a  jnb     loc_1400191D0
0x140018e70  lea     rax, [rbp+0E0h+var_140]
0x140018e74  lea     r14, [rdi+50h]
0x140018e78  mov     [rsp+1E0h+SourceBuffer], rax
0x140018e7d  mov     rcx, r14; SpinLock
0x140018e80  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018e87  nop     dword ptr [rax+rax+00h]
0x140018e8c  mov     r8d, [rdi+1E4h]
0x140018e93  mov     r15b, al
0x140018e96  cmp     r8d, 4
0x140018e9a  jge     loc_140019543
0x140018ea0  mov     eax, [rdi+68h]
0x140018ea3  cmp     eax, 4
0x140018ea6  jz      short loc_140018F03
0x140018ea8  test    eax, eax
0x140018eaa  jnz     short loc_140018EAF
0x140018eac  mov     [rdi+6Ch], eax
0x140018eaf  mov     rcx, rax
0x140018eb2  mov     qword ptr [rsp+1E0h+DestinationOffset], 0
0x140018ebb  mov     ebx, 4
0x140018ec0  lea     rdx, [rdi+6Ch]
0x140018ec4  sub     rbx, rax
0x140018ec7  mov     r8d, r12d
0x140018eca  mov     rax, r13
0x140018ecd  sub     rax, rsi
0x140018ed0  cmp     rbx, rax
0x140018ed3  cmovnb  ebx, eax
0x140018ed6  add     rdx, rcx
0x140018ed9  mov     rcx, [rsp+1E0h+var_188]
0x140018ede  mov     r9d, ebx
0x140018ee1  call    SrvNetCopyIndicationToBufferEx
0x140018ee6  test    eax, eax
0x140018ee8  js      loc_140019290
0x140018eee  add     [rdi+68h], ebx
0x140018ef1  add     r12d, ebx
0x140018ef4  cmp     dword ptr [rdi+68h], 4
0x140018ef8  jnz     loc_1400191BE
0x140018efe  mov     rbx, [rsp+1E0h+var_188]
0x140018f03  mov     esi, [rdi+6Ch]
0x140018f06  bswap   esi
0x140018f08  cmp     esi, [rdi+1E8h]
0x140018f0e  ja      loc_1400194F6
0x140018f14  cmp     esi, 20h ; ' '
0x140018f17  jb      loc_1400194F6
0x140018f1d  lea     r13, [rdi+58h]
0x140018f21  cmp     [r13+0], r13
0x140018f25  jnz     loc_1400192B1
0x140018f2b  mov     dword ptr [rdi+68h], 0
0x140018f32  cmp     esi, 100h
0x140018f38  ja      loc_1400192C5
0x140018f3e  lea     ecx, [rsi+r12]
0x140018f42  cmp     rcx, [rsp+1E0h+var_170]
0x140018f47  ja      loc_1400192C5
0x140018f4d  lea     rax, [rsp+1E0h+SourceBuffer]
0x140018f52  mov     r9d, esi
0x140018f55  mov     r8d, r12d
0x140018f58  mov     qword ptr [rsp+1E0h+DestinationOffset], rax
0x140018f5d  lea     rdx, [rbp+0E0h+var_140]
0x140018f61  mov     rcx, rbx
0x140018f64  call    SrvNetCopyIndicationToBufferEx
0x140018f69  mov     edx, 80000000h
0x140018f6e  mov     ecx, eax
0x140018f70  add     eax, edx
0x140018f72  test    edx, eax
0x140018f74  jnz     short loc_140018F82
0x140018f76  cmp     ecx, 0C0000011h
0x140018f7c  jnz     loc_1400192C5
0x140018f82  lea     rax, [rbp+0E0h+var_140]
0x140018f86  mov     [rsp+1E0h+var_180], 0
0x140018f8f  mov     [rsp+1E0h+SourceOffset], 0
0x140018f97  cmp     [rsp+1E0h+SourceBuffer], rax
0x140018f9c  jz      short loc_140018FA4
0x140018f9e  inc     cs:ultraFastIndications
0x140018fa4  inc     cs:fastIndications
0x140018faa  test    byte ptr cs:WPP_MAIN_CB.Queue+10h, 10h
0x140018fb1  jnz     short loc_140018FBC
0x140018fb3  test    byte ptr cs:WPP_MAIN_CB.Queue+13h, 4
0x140018fba  jz      short loc_140018FE0
0x140018fbc  xor     eax, eax
0x140018fbe  mov     qword ptr [rbp+0E0h+var_158], rbx
0x140018fc2  lea     rcx, [rbp+0E0h+var_158]
0x140018fc6  mov     qword ptr [rbp+0E0h+var_158+8], rax
0x140018fca  call    cs:__imp_IoSetActivityIdThread
0x140018fd1  nop     dword ptr [rax+rax+00h]
0x140018fd6  mov     [rsp+1E0h+var_178], rax
0x140018fdb  mov     [rsp+1E0h+var_1A0], 1
0x140018fe0  lea     rax, [rsp+1E0h+var_180]
0x140018fe5  mov     r9d, 80000420h
0x140018feb  mov     [rsp+1E0h+var_1B0], rax
0x140018ff0  lea     r8, [rsp+1E0h+SourceOffset]
0x140018ff5  mov     rax, [rsp+1E0h+SourceBuffer]
0x140018ffa  mov     edx, esi
0x140018ffc  mov     [rsp+1E0h+BytesCopied], 0
0x140019005  mov     rcx, rdi
0x140019008  mov     qword ptr [rsp+1E0h+DestinationOffset], rax
0x14001900d  call    SrvNetCommonReceiveHandler
0x140019012  cmp     [rsp+1E0h+var_1A0], 0
0x140019017  mov     ebx, eax
0x140019019  jz      short loc_140019031
0x14001901b  mov     rcx, [rsp+1E0h+var_178]
0x140019020  mov     [rsp+1E0h+var_1A0], 0
0x140019025  call    cs:__imp_IoClearActivityIdThread
0x14001902c  nop     dword ptr [rax+rax+00h]
0x140019031  mov     eax, 80000000h
0x140019036  lea     ecx, [rbx+rax]
0x140019039  test    eax, ecx
0x14001903b  jnz     short loc_140019049
0x14001903d  cmp     ebx, 0C0000016h
0x140019043  jnz     loc_1400191EC
0x140019049  mov     ecx, [rsp+1E0h+SourceOffset]
0x14001904d  cmp     ecx, esi
0x14001904f  jz      loc_14001919A
0x140019055  cmp     ebx, 0C0000016h
0x14001905b  jnz     short loc_1400190D3
0x14001905d  mov     r9, [rsp+1E0h+var_180]
0x140019062  test    r9, r9
0x140019065  jz      short loc_1400190D3
0x140019067  mov     ebx, [r9]
0x14001906a  mov     eax, esi
0x14001906c  sub     eax, ecx
0x14001906e  mov     [rsp+1E0h+var_198], 0
0x140019076  mov     r9, [r9+8]; DestinationMdlChain
0x14001907a  cmp     ebx, eax
0x14001907c  mov     edx, ecx; SourceOffset
0x14001907e  mov     rcx, [rsp+1E0h+SourceBuffer]; SourceBuffer
0x140019083  cmovnb  ebx, eax
0x140019086  lea     rax, [rsp+1E0h+var_198]
0x14001908b  mov     [rsp+1E0h+BytesCopied], rax; BytesCopied
0x140019090  mov     r8d, ebx; SourceBytesToCopy
0x140019093  mov     [rsp+1E0h+DestinationOffset], 0; DestinationOffset
0x14001909b  call    cs:__imp_TdiCopyBufferToMdl
0x1400190a2  nop     dword ptr [rax+rax+00h]
0x1400190a7  mov     eax, [rsp+1E0h+SourceOffset]
0x1400190ab  mov     edx, ebx
0x1400190ad  add     eax, [rsp+1E0h+var_198]
0x1400190b1  mov     r8, [rsp+1E0h+var_180]
0x1400190b6  mov     [rsp+1E0h+SourceOffset], eax
0x1400190ba  sub     eax, esi
0x1400190bc  neg     eax
0x1400190be  mov     rax, [r8+10h]
0x1400190c2  sbb     ecx, ecx
0x1400190c4  and     ecx, 80000005h
0x1400190ca  call    _guard_dispatch_icall
0x1400190cf  mov     ecx, [rsp+1E0h+SourceOffset]
0x1400190d3  cmp     ecx, esi
0x1400190d5  ja      loc_140019258
0x1400190db  jnb     loc_14001919A
0x1400190e1  mov     dl, r15b; NewIrql
0x1400190e4  mov     rcx, r14; SpinLock
0x1400190e7  call    cs:__imp_KeReleaseSpinLock
0x1400190ee  nop     dword ptr [rax+rax+00h]
0x1400190f3  mov     ecx, esi
0x1400190f5  xor     edx, edx
0x1400190f7  sub     ecx, [rsp+1E0h+SourceOffset]
0x1400190fb  call    SrvNetAllocateBuffer
0x140019100  mov     rbx, rax
0x140019103  test    rax, rax
0x140019106  jz      loc_140019222
0x14001910c  mov     rcx, [rax+18h]; void *
0x140019110  mov     r8d, esi
0x140019113  sub     r8d, [rsp+1E0h+SourceOffset]; Size
0x140019118  mov     [rax+24h], r8d
0x14001911c  mov     [rax+48h], r8
0x140019120  mov     dword ptr [rax+60h], 0
0x140019127  mov     edx, [rsp+1E0h+SourceOffset]
0x14001912b  add     rdx, [rsp+1E0h+SourceBuffer]; Src
0x140019130  call    memmove
0x140019135  test    byte ptr cs:WPP_MAIN_CB.Queue+10h, 10h
0x14001913c  jnz     short loc_140019147
0x14001913e  test    byte ptr cs:WPP_MAIN_CB.Queue+13h, 4
0x140019145  jz      short loc_14001915C
0x140019147  mov     rax, [rsp+1E0h+var_188]
0x14001914c  mov     word ptr [rbx+16h], 1
0x140019152  mov     [rbx+64h], rax
0x140019156  xor     eax, eax
0x140019158  mov     [rbx+6Ch], rax
0x14001915c  mov     rcx, r14; SpinLock
0x14001915f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140019166  nop     dword ptr [rax+rax+00h]
0x14001916b  mov     rcx, [r13+8]
0x14001916f  mov     r15b, al
0x140019172  cmp     [rcx], r13
0x140019175  jnz     loc_14001921B
0x14001917b  mov     rax, [r13+0]
0x14001917f  mov     [rbx], r13
0x140019182  mov     [rbx+8], rcx
0x140019186  mov     [rcx], rbx
0x140019189  mov     [r13+8], rbx
0x14001918d  cmp     rax, r13
0x140019190  jnz     short loc_14001919A
0x140019192  mov     rcx, rdi
0x140019195  call    SrvNetIndicateData
0x14001919a  mov     dl, r15b; NewIrql
0x14001919d  mov     rcx, r14; SpinLock
0x1400191a0  call    cs:__imp_KeReleaseSpinLock
0x1400191a7  nop     dword ptr [rax+rax+00h]
0x1400191ac  mov     rbx, [rsp+1E0h+var_188]
0x1400191b1  add     r12d, esi
0x1400191b4  mov     r13, [rsp+1E0h+var_170]
0x1400191b9  jmp     loc_140018E64
0x1400191be  mov     dl, r15b; NewIrql
0x1400191c1  mov     rcx, r14; SpinLock
0x1400191c4  call    cs:__imp_KeReleaseSpinLock
0x1400191cb  nop     dword ptr [rax+rax+00h]
0x1400191d0  mov     rcx, [rbp+0E0h+var_160]
0x1400191d4  mov     eax, r12d
0x1400191d7  mov     [rcx], rax
0x1400191da  xor     eax, eax
0x1400191dc  test    r12d, r12d
0x1400191df  mov     ecx, 0C000021Bh
0x1400191e4  cmovz   eax, ecx
0x1400191e7  jmp     loc_140019334
0x1400191ec  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400191f3  lea     rax, WPP_GLOBAL_Control
0x1400191fa  cmp     rcx, rax
0x1400191fd  jz      loc_140019290
0x140019203  mov     eax, [rcx+2Ch]
0x140019206  test    al, 10h
0x140019208  jz      loc_140019290
0x14001920e  cmp     byte ptr [rcx+29h], 1
0x140019212  jb      short loc_140019290
0x140019214  mov     edx, 13h
0x140019219  jmp     short loc_14001927D
0x14001921b  mov     ecx, 3
0x140019220  int     29h; Win8: RtlFailFast(ecx)
0x140019222  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140019229  lea     rax, WPP_GLOBAL_Control
0x140019230  cmp     rcx, rax
0x140019233  jz      loc_140019325
0x140019239  mov     eax, [rcx+2Ch]
0x14001923c  test    al, 10h
0x14001923e  jz      loc_140019325
0x140019244  cmp     byte ptr [rcx+29h], 1
0x140019248  jb      loc_140019325
0x14001924e  mov     edx, 15h
0x140019253  jmp     loc_14001930E
0x140019258  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001925f  lea     rax, WPP_GLOBAL_Control
0x140019266  cmp     rcx, rax
0x140019269  jz      short loc_140019290
0x14001926b  mov     eax, [rcx+2Ch]
0x14001926e  test    al, 10h
0x140019270  jz      short loc_140019290
0x140019272  cmp     byte ptr [rcx+29h], 1
0x140019276  jb      short loc_140019290
0x140019278  mov     edx, 14h
0x14001927d  mov     rcx, [rcx+18h]
0x140019281  lea     r8, WPP_0bd25dad6c3a3d1c3ca87626e1622cba_Traceguids
0x140019288  mov     r9, rdi
0x14001928b  call    WPP_SF_q
0x140019290  mov     edx, 1
0x140019295  mov     rcx, rdi
0x140019298  call    SrvNetDisconnectConnectionInternalEx
0x14001929d  mov     dl, r15b; NewIrql
0x1400192a0  mov     rcx, r14; SpinLock
0x1400192a3  call    cs:__imp_KeReleaseSpinLock
0x1400192aa  nop     dword ptr [rax+rax+00h]
0x1400192af  jmp     short loc_14001932F
0x1400192b1  cmp     byte ptr [rdi+1EDh], 0
0x1400192b8  jz      loc_140019496
0x1400192be  mov     dword ptr [rdi+68h], 0
0x1400192c5  mov     dl, r15b; NewIrql
0x1400192c8  mov     rcx, r14; SpinLock
0x1400192cb  call    cs:__imp_KeReleaseSpinLock
0x1400192d2  nop     dword ptr [rax+rax+00h]
0x1400192d7  xor     edx, edx
0x1400192d9  mov     ecx, esi
  ... truncated ...
```
