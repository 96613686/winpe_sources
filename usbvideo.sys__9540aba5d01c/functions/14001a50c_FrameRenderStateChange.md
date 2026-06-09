# FrameRenderStateChange

- ea: `0x14001a50c`
- end: `0x14001a931`
- name: `FrameRenderStateChange`
- size: `1061`
- prototype: `__int64 __fastcall(PKSPIN Pin)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14000a880`

## callees

- `0x140001544`
- `0x140004bac`
- `0x140009dc8`
- `0x140015234`
- `0x1400166ac`
- `0x1400188bc`
- `0x14001a50c`
- `0x14001c6b0`
- `0x14001cfdc`
- `0x14001d0cc`
- `0x140040a70`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a8bc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a8bc`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a660`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a660`
- `ntoskrnl!KeReleaseSemaphore` at `0x14001a75b`
- `ntoskrnl!KeReleaseSemaphore` at `0x14001a8ac`
- `ntoskrnl!KeReleaseSemaphore` at `0x14001a75b`
- `ntoskrnl!KeReleaseSemaphore` at `0x14001a8ac`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a8da`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a8da`
- `ntoskrnl!KeReadStateSemaphore` at `0x14001a734`
- `ntoskrnl!KeReadStateSemaphore` at `0x14001a885`
- `ntoskrnl!KeReadStateSemaphore` at `0x14001a734`
- `ntoskrnl!KeReadStateSemaphore` at `0x14001a885`
- `ks!KsPinAcquireProcessingMutex` at `0x14001a827`
- `ks!KsPinAcquireProcessingMutex` at `0x14001a827`
- `ks!KsPinGetReferenceClockInterface` at `0x14001a68e`
- `ks!KsPinGetReferenceClockInterface` at `0x14001a68e`
- `ks!KsPinGetParentFilter` at `0x14001a567`
- `ks!KsPinGetParentFilter` at `0x14001a567`
- `ks!KsStreamPointerDelete` at `0x14001a7fb`
- `ks!KsStreamPointerDelete` at `0x14001a7fb`
- `ks!KsPinReleaseProcessingMutex` at `0x14001a848`
- `ks!KsPinReleaseProcessingMutex` at `0x14001a848`

## pseudocode

```c
__int64 __fastcall FrameRenderStateChange(PKSPIN Pin, __int64 a2, __int64 a3)
{
  _QWORD *Context; // rsi
  unsigned int v4; // edi
  unsigned int v5; // r12d
  __int64 v7; // r14
  PKSFILTER ParentFilter; // rax
  __int64 v9; // rdx
  __int64 *v10; // rbp
  __int64 v11; // rbp
  unsigned int SetInterfaceControl; // r15d
  __int64 result; // rax
  unsigned int v14; // edi
  void *v15; // rcx
  int v16; // edx
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // rcx
  struct _KSSTREAM_POINTER *v20; // rcx
  __int64 v21; // rcx
  KIRQL v22; // bl
  SIZE_T NumberOfBytes; // [rsp+28h] [rbp-40h]
  union _LARGE_INTEGER Timeout; // [rsp+70h] [rbp+8h] BYREF

  Context = Pin->Context;
  v4 = a3;
  v5 = a2;
  v7 = Context[12];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qddq(WPP_GLOBAL_Control->AttachedDevice, a2, a3, Context, a2, a3, Pin);
  ParentFilter = KsPinGetParentFilter(Pin);
  if ( ParentFilter )
  {
    v10 = (__int64 *)ParentFilter->Context;
    if ( v10 )
    {
      v11 = *v10;
      if ( v11 )
      {
        SetInterfaceControl = 0;
        if ( v5 != v4 )
        {
          LOBYTE(v9) = *((_BYTE *)Context + 177);
          result = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(*(_QWORD *)Context[49] + 120LL))(
                     Context[49],
                     v9,
                     v5,
                     v4);
          SetInterfaceControl = result;
          if ( (int)result < 0 )
            return result;
          if ( !v4 )
          {
            KsPinAcquireProcessingMutex(Pin);
            SelectZeroBandwidthInterface(*Context, Pin->Id);
            *((_BYTE *)Context + 384) = 0;
            KsPinReleaseProcessingMutex(Pin);
            v21 = *(_QWORD *)(v7 + 160);
            if ( v21 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
              *(_QWORD *)(v7 + 160) = 0;
            }
            if ( !KeReadStateSemaphore((PRKSEMAPHORE)(*(_QWORD *)(v11 + 752) + 32LL * Pin->Id)) )
              KeReleaseSemaphore((PRKSEMAPHORE)(*(_QWORD *)(v11 + 752) + 32LL * Pin->Id), 0, 1, 0);
            v22 = KeAcquireSpinLockRaiseToDpc(Context + 15);
            FrameRenderInitializePinContext(Context, 0);
            KeReleaseSpinLock(Context + 15, v22);
            return SetInterfaceControl;
          }
          v14 = v4 - 1;
          if ( v14 )
          {
            if ( v14 - 1 >= 2
              && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_qq(
                WPP_GLOBAL_Control->AttachedDevice,
                31,
                WPP_9e091edf6a993739dccdf8ddcdcaa537_Traceguids,
                v11,
                Context);
            }
            return SetInterfaceControl;
          }
          if ( v5 )
          {
            if ( *(_DWORD *)(v7 + 8) )
            {
              Timeout.QuadPart = -20000000;
              *(_DWORD *)(v7 + 12) = 1;
              USBVideoPinWaitForStarvation(Pin, &Timeout);
              USBVideoPinWaitForStarvation(Pin, 0);
              v20 = *(struct _KSSTREAM_POINTER **)(v7 + 176);
              if ( v20 )
              {
                KsStreamPointerDelete(v20);
                *(_QWORD *)(v7 + 176) = 0;
              }
              FrameRenderInitializePinContext(Context, 1);
            }
            return SetInterfaceControl;
          }
          v15 = (void *)(*(_QWORD *)(v11 + 752) + 32LL * Pin->Id);
          Timeout.QuadPart = 0;
          if ( KeWaitForSingleObject(v15, Executive, 0, 0, &Timeout) )
            return 3221225626LL;
          if ( !*(_QWORD *)(v7 + 160) && KsPinGetReferenceClockInterface(Pin, (PIKSREFERENCECLOCK *)(v7 + 160)) < 0 )
            *(_QWORD *)(v7 + 160) = 0;
          LOBYTE(v18) = *((_BYTE *)Context + 177);
          LOBYTE(v17) = 2;
          LODWORD(NumberOfBytes) = 26;
          LOBYTE(v16) = 1;
          SetInterfaceControl = GetSetInterfaceControl(Context[53], v16, v17, v18, Context + 23, NumberOfBytes);
          if ( (SetInterfaceControl & 0x80000000) != 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
              WPP_SF_qqD(
                WPP_GLOBAL_Control->AttachedDevice,
                30,
                WPP_9e091edf6a993739dccdf8ddcdcaa537_Traceguids,
                v11,
                Context,
                SetInterfaceControl);
            goto LABEL_25;
          }
          SetInterfaceControl = SelectInterface(*(PVOID *)Context[2]);
          if ( (SetInterfaceControl & 0x80000000) != 0 )
          {
LABEL_25:
            SelectZeroBandwidthInterface(*Context, Pin->Id);
            if ( !KeReadStateSemaphore((PRKSEMAPHORE)(*(_QWORD *)(v11 + 752) + 32LL * Pin->Id)) )
              KeReleaseSemaphore((PRKSEMAPHORE)(*(_QWORD *)(v11 + 752) + 32LL * Pin->Id), 0, 1, 0);
            v19 = *(_QWORD *)(v7 + 160);
            if ( v19 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
              *(_QWORD *)(v7 + 160) = 0;
            }
            return SetInterfaceControl;
          }
          *((_BYTE *)Context + 384) = 1;
        }
        return SetInterfaceControl;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_9e091edf6a993739dccdf8ddcdcaa537_Traceguids);
  return 3221225485LL;
}

```

## disassembly

```asm
0x14001a50c  mov     rax, rsp
0x14001a50f  mov     [rax+10h], rbx
0x14001a513  mov     [rax+18h], rbp
0x14001a517  push    rsi
0x14001a518  push    rdi
0x14001a519  push    r12
0x14001a51b  push    r14
0x14001a51d  push    r15
0x14001a51f  sub     rsp, 40h
0x14001a523  mov     rsi, [rcx+10h]
0x14001a527  mov     edi, r8d
0x14001a52a  mov     r12d, edx
0x14001a52d  mov     rbx, rcx
0x14001a530  mov     r14, [rsi+60h]
0x14001a534  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a53b  lea     r15, WPP_GLOBAL_Control
0x14001a542  cmp     rcx, r15
0x14001a545  jz      short loc_14001A564
0x14001a547  cmp     byte ptr [rcx+29h], 5
0x14001a54b  jb      short loc_14001A564
0x14001a54d  mov     rcx, [rcx+18h]
0x14001a551  mov     r9, rsi
0x14001a554  mov     [rax-38h], rbx
0x14001a558  mov     [rax-40h], r8d
0x14001a55c  mov     [rax-48h], edx
0x14001a55f  call    WPP_SF_qddq
0x14001a564  mov     rcx, rbx; Pin
0x14001a567  call    cs:__imp_KsPinGetParentFilter
0x14001a56e  nop     dword ptr [rax+rax+00h]
0x14001a573  test    rax, rax
0x14001a576  jz      loc_14001A8EB
0x14001a57c  mov     rbp, [rax+10h]
0x14001a580  test    rbp, rbp
0x14001a583  jz      loc_14001A8EB
0x14001a589  mov     rbp, [rbp+0]
0x14001a58d  test    rbp, rbp
0x14001a590  jz      loc_14001A8EB
0x14001a596  xor     r15d, r15d
0x14001a599  cmp     r12d, edi
0x14001a59c  jz      loc_14001A8E6
0x14001a5a2  mov     rcx, [rsi+188h]
0x14001a5a9  mov     r9d, edi
0x14001a5ac  mov     dl, [rsi+0B1h]
0x14001a5b2  mov     r8d, r12d
0x14001a5b5  mov     rax, [rcx]
0x14001a5b8  mov     rax, [rax+78h]
0x14001a5bc  call    _guard_dispatch_icall
0x14001a5c1  mov     r15d, eax
0x14001a5c4  test    eax, eax
0x14001a5c6  js      loc_14001A917
0x14001a5cc  test    edi, edi
0x14001a5ce  jz      loc_14001A824
0x14001a5d4  sub     edi, 1
0x14001a5d7  jz      short loc_14001A62E
0x14001a5d9  sub     edi, 1
0x14001a5dc  jz      loc_14001A8E6
0x14001a5e2  cmp     edi, 1
0x14001a5e5  jz      loc_14001A8E6
0x14001a5eb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a5f2  lea     rax, WPP_GLOBAL_Control
0x14001a5f9  cmp     rcx, rax
0x14001a5fc  jz      loc_14001A8E6
0x14001a602  cmp     byte ptr [rcx+29h], 2
0x14001a606  jb      loc_14001A8E6
0x14001a60c  mov     rcx, [rcx+18h]
0x14001a610  lea     r8, WPP_9e091edf6a993739dccdf8ddcdcaa537_Traceguids
0x14001a617  mov     edx, 1Fh
0x14001a61c  mov     [rsp+68h+Timeout], rsi
0x14001a621  mov     r9, rbp
0x14001a624  call    WPP_SF_qq
0x14001a629  jmp     loc_14001A8E6
0x14001a62e  test    r12d, r12d
0x14001a631  jnz     loc_14001A7BC
0x14001a637  mov     ecx, [rbx+18h]
0x14001a63a  lea     rax, [rsp+68h+arg_0]
0x14001a63f  shl     rcx, 5
0x14001a643  xor     r9d, r9d; Alertable
0x14001a646  add     rcx, [rbp+2F0h]; Object
0x14001a64d  xor     r8d, r8d; WaitMode
0x14001a650  xor     edx, edx; WaitReason
0x14001a652  mov     qword ptr [rsp+68h+arg_0], 0
0x14001a65b  mov     [rsp+68h+Timeout], rax; Timeout
0x14001a660  call    cs:__imp_KeWaitForSingleObject
0x14001a667  nop     dword ptr [rax+rax+00h]
0x14001a66c  test    eax, eax
0x14001a66e  jz      short loc_14001A67A
0x14001a670  mov     eax, 0C000009Ah
0x14001a675  jmp     loc_14001A917
0x14001a67a  cmp     qword ptr [r14+0A0h], 0
0x14001a682  jnz     short loc_14001A6A9
0x14001a684  lea     rdx, [r14+0A0h]; Interface
0x14001a68b  mov     rcx, rbx; Pin
0x14001a68e  call    cs:__imp_KsPinGetReferenceClockInterface
0x14001a695  nop     dword ptr [rax+rax+00h]
0x14001a69a  test    eax, eax
0x14001a69c  jns     short loc_14001A6A9
0x14001a69e  mov     qword ptr [r14+0A0h], 0
0x14001a6a9  mov     r9b, [rsi+0B1h]; int
0x14001a6b0  lea     rax, [rsi+0B8h]
0x14001a6b7  mov     rcx, [rsi+1A8h]; int
0x14001a6be  mov     r8b, 2; int
0x14001a6c1  mov     dword ptr [rsp+68h+NumberOfBytes], 1Ah; NumberOfBytes
0x14001a6c9  mov     dl, 1; int
0x14001a6cb  mov     [rsp+68h+Timeout], rax; Src
0x14001a6d0  call    GetSetInterfaceControl
0x14001a6d5  mov     r15d, eax
0x14001a6d8  test    eax, eax
0x14001a6da  jns     loc_14001A793
0x14001a6e0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a6e7  lea     rax, WPP_GLOBAL_Control
0x14001a6ee  cmp     rcx, rax
0x14001a6f1  jz      short loc_14001A71B
0x14001a6f3  cmp     byte ptr [rcx+29h], 3
0x14001a6f7  jb      short loc_14001A71B
0x14001a6f9  mov     rcx, [rcx+18h]
0x14001a6fd  lea     r8, WPP_9e091edf6a993739dccdf8ddcdcaa537_Traceguids
0x14001a704  mov     edx, 1Eh
0x14001a709  mov     dword ptr [rsp+68h+NumberOfBytes], r15d
0x14001a70e  mov     r9, rbp
0x14001a711  mov     [rsp+68h+Timeout], rsi
0x14001a716  call    WPP_SF_qqD
0x14001a71b  mov     edx, [rbx+18h]
0x14001a71e  mov     rcx, [rsi]
0x14001a721  call    SelectZeroBandwidthInterface
0x14001a726  mov     ecx, [rbx+18h]
0x14001a729  shl     rcx, 5
0x14001a72d  add     rcx, [rbp+2F0h]; Semaphore
0x14001a734  call    cs:__imp_KeReadStateSemaphore
0x14001a73b  nop     dword ptr [rax+rax+00h]
0x14001a740  test    eax, eax
0x14001a742  jnz     short loc_14001A767
0x14001a744  mov     ecx, [rbx+18h]
0x14001a747  lea     r8d, [rax+1]; Adjustment
0x14001a74b  shl     rcx, 5
0x14001a74f  xor     r9d, r9d; Wait
0x14001a752  add     rcx, [rbp+2F0h]; Semaphore
0x14001a759  xor     edx, edx; Increment
0x14001a75b  call    cs:__imp_KeReleaseSemaphore
0x14001a762  nop     dword ptr [rax+rax+00h]
0x14001a767  mov     rcx, [r14+0A0h]
0x14001a76e  test    rcx, rcx
0x14001a771  jz      loc_14001A8E6
0x14001a777  mov     rax, [rcx]
0x14001a77a  mov     rax, [rax+10h]
0x14001a77e  call    _guard_dispatch_icall
0x14001a783  mov     qword ptr [r14+0A0h], 0
0x14001a78e  jmp     loc_14001A8E6
0x14001a793  mov     rcx, [rsi+10h]
0x14001a797  mov     r8, rbx
0x14001a79a  mov     rdx, rbp
0x14001a79d  mov     rcx, [rcx]; StartPosition
0x14001a7a0  call    SelectInterface
0x14001a7a5  mov     r15d, eax
0x14001a7a8  test    eax, eax
0x14001a7aa  js      loc_14001A71B
0x14001a7b0  mov     byte ptr [rsi+180h], 1
0x14001a7b7  jmp     loc_14001A8E6
0x14001a7bc  cmp     dword ptr [r14+8], 0
0x14001a7c1  jz      loc_14001A8E6
0x14001a7c7  lea     rdx, [rsp+68h+arg_0]
0x14001a7cc  mov     qword ptr [rsp+68h+arg_0], 0FFFFFFFFFECED300h
0x14001a7d5  mov     rcx, rbx
0x14001a7d8  mov     dword ptr [r14+0Ch], 1
0x14001a7e0  call    USBVideoPinWaitForStarvation
0x14001a7e5  xor     edx, edx
0x14001a7e7  mov     rcx, rbx
0x14001a7ea  call    USBVideoPinWaitForStarvation
0x14001a7ef  mov     rcx, [r14+0B0h]; StreamPointer
0x14001a7f6  test    rcx, rcx
0x14001a7f9  jz      short loc_14001A812
0x14001a7fb  call    cs:__imp_KsStreamPointerDelete
0x14001a802  nop     dword ptr [rax+rax+00h]
0x14001a807  mov     qword ptr [r14+0B0h], 0
0x14001a812  mov     edx, 1
0x14001a817  mov     rcx, rsi
0x14001a81a  call    FrameRenderInitializePinContext
0x14001a81f  jmp     loc_14001A8E6
0x14001a824  mov     rcx, rbx; Pin
0x14001a827  call    cs:__imp_KsPinAcquireProcessingMutex
0x14001a82e  nop     dword ptr [rax+rax+00h]
0x14001a833  mov     edx, [rbx+18h]
0x14001a836  mov     rcx, [rsi]
0x14001a839  call    SelectZeroBandwidthInterface
0x14001a83e  mov     rcx, rbx; Pin
0x14001a841  mov     byte ptr [rsi+180h], 0
0x14001a848  call    cs:__imp_KsPinReleaseProcessingMutex
0x14001a84f  nop     dword ptr [rax+rax+00h]
0x14001a854  mov     rcx, [r14+0A0h]
0x14001a85b  test    rcx, rcx
0x14001a85e  jz      short loc_14001A877
0x14001a860  mov     rax, [rcx]
0x14001a863  mov     rax, [rax+10h]
0x14001a867  call    _guard_dispatch_icall
0x14001a86c  mov     qword ptr [r14+0A0h], 0
0x14001a877  mov     ecx, [rbx+18h]
0x14001a87a  shl     rcx, 5
0x14001a87e  add     rcx, [rbp+2F0h]; Semaphore
0x14001a885  call    cs:__imp_KeReadStateSemaphore
0x14001a88c  nop     dword ptr [rax+rax+00h]
0x14001a891  test    eax, eax
0x14001a893  jnz     short loc_14001A8B8
0x14001a895  mov     ecx, [rbx+18h]
0x14001a898  lea     r8d, [rax+1]; Adjustment
0x14001a89c  shl     rcx, 5
0x14001a8a0  xor     r9d, r9d; Wait
0x14001a8a3  add     rcx, [rbp+2F0h]; Semaphore
0x14001a8aa  xor     edx, edx; Increment
0x14001a8ac  call    cs:__imp_KeReleaseSemaphore
0x14001a8b3  nop     dword ptr [rax+rax+00h]
0x14001a8b8  lea     rcx, [rsi+78h]; SpinLock
0x14001a8bc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001a8c3  nop     dword ptr [rax+rax+00h]
0x14001a8c8  xor     edx, edx
0x14001a8ca  mov     rcx, rsi
0x14001a8cd  mov     bl, al
0x14001a8cf  call    FrameRenderInitializePinContext
0x14001a8d4  mov     dl, bl; NewIrql
0x14001a8d6  lea     rcx, [rsi+78h]; SpinLock
0x14001a8da  call    cs:__imp_KeReleaseSpinLock
0x14001a8e1  nop     dword ptr [rax+rax+00h]
0x14001a8e6  mov     eax, r15d
0x14001a8e9  jmp     short loc_14001A917
0x14001a8eb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a8f2  cmp     rcx, r15
0x14001a8f5  jz      short loc_14001A912
0x14001a8f7  cmp     byte ptr [rcx+29h], 3
0x14001a8fb  jb      short loc_14001A912
0x14001a8fd  mov     rcx, [rcx+18h]
0x14001a901  lea     r8, WPP_9e091edf6a993739dccdf8ddcdcaa537_Traceguids
0x14001a908  mov     edx, 1Dh
0x14001a90d  call    WPP_SF_
0x14001a912  mov     eax, 0C000000Dh
0x14001a917  lea     r11, [rsp+68h+var_28]
0x14001a91c  mov     rbx, [r11+38h]
0x14001a920  mov     rbp, [r11+40h]
0x14001a924  mov     rsp, r11
0x14001a927  pop     r15
0x14001a929  pop     r14
0x14001a92b  pop     r12
0x14001a92d  pop     rdi
0x14001a92e  pop     rsi
0x14001a92f  retn
```
