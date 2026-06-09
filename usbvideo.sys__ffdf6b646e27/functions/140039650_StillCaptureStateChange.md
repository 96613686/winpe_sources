# StillCaptureStateChange

- ea: `0x140039650`
- end: `0x140039ce8`
- name: `StillCaptureStateChange`
- size: `1688`
- prototype: `__int64 __fastcall(PKSPIN Pin)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x140024e30`

## callees

- `0x140001160`
- `0x140001544`
- `0x140004bac`
- `0x140009dc8`
- `0x14000b1fc`
- `0x14000b34c`
- `0x14000b7fc`
- `0x140015234`
- `0x1400166ac`
- `0x1400188bc`
- `0x14001d0cc`
- `0x140039120`
- `0x1400394cc`
- `0x140039650`
- `0x14003a3c4`
- `0x140040a70`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400397a6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140039bba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400397a6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140039bba`
- `ntoskrnl!KeWaitForSingleObject` at `0x140039805`
- `ntoskrnl!KeWaitForSingleObject` at `0x140039805`
- `ntoskrnl!KeReleaseSemaphore` at `0x140039a9e`
- `ntoskrnl!KeReleaseSemaphore` at `0x140039baa`
- `ntoskrnl!KeReleaseSemaphore` at `0x140039a9e`
- `ntoskrnl!KeReleaseSemaphore` at `0x140039baa`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400397c2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140039bd6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400397c2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140039bd6`
- `ntoskrnl!KeReadStateSemaphore` at `0x140039a77`
- `ntoskrnl!KeReadStateSemaphore` at `0x140039b83`
- `ntoskrnl!KeReadStateSemaphore` at `0x140039a77`
- `ntoskrnl!KeReadStateSemaphore` at `0x140039b83`
- `ks!KsPinGetReferenceClockInterface` at `0x140039854`
- `ks!KsPinGetReferenceClockInterface` at `0x140039854`
- `ks!KsPinGetParentFilter` at `0x1400396ab`
- `ks!KsPinGetParentFilter` at `0x1400396ab`

## pseudocode

```c
__int64 __fastcall StillCaptureStateChange(PKSPIN Pin, unsigned int a2, __int64 a3)
{
  char *Context; // rsi
  int v4; // ebx
  __int64 v7; // r15
  PKSFILTER ParentFilter; // rax
  __int64 *v9; // r12
  __int64 v10; // r14
  unsigned int ReferenceClockInterface; // ebp
  __int64 Id; // r10
  __int64 v13; // rax
  __int64 v14; // rcx
  int v15; // ebx
  int v16; // ebx
  KIRQL v17; // bl
  void *v18; // rcx
  int v19; // edx
  int v20; // r8d
  int v21; // r9d
  __int64 v23; // r13
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // rax
  __int64 v27; // rbx
  __int64 v28; // rax
  int v29; // eax
  __int64 v30; // rcx
  signed __int32 v31; // eax
  __int64 v32; // rcx
  KIRQL v33; // bl
  int v34; // eax
  PDEVICE_OBJECT v35; // rcx
  __int64 v36; // rdx
  SIZE_T NumberOfBytes; // [rsp+28h] [rbp-40h]
  __int64 v38; // [rsp+70h] [rbp+8h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+88h] [rbp+20h] BYREF

  Context = (char *)Pin->Context;
  v4 = a3;
  v7 = *((_QWORD *)Context + 12);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_ddq(WPP_GLOBAL_Control->AttachedDevice, 75, a3, a2, a3, Pin);
  ParentFilter = KsPinGetParentFilter(Pin);
  if ( ParentFilter )
  {
    v9 = (__int64 *)ParentFilter->Context;
    if ( v9 )
    {
      v10 = *v9;
      if ( *v9 )
      {
        ReferenceClockInterface = 0;
        if ( a2 == v4 )
          return ReferenceClockInterface;
        Id = Pin->Id;
        v13 = *(_QWORD *)(v10 + 744);
        v14 = *(unsigned int *)(136 * Id + v13 + 8);
        LODWORD(v38) = *(_DWORD *)(136 * Id + v13 + 8);
        if ( v4 )
        {
          v15 = v4 - 1;
          if ( v15 )
          {
            v16 = v15 - 1;
            if ( !v16 )
            {
              if ( Context[377] == 3 && *(_DWORD *)v7 )
              {
                *(_DWORD *)v7 = 0;
                v38 = -20000000;
                USBVideoPinWaitForStarvation(Pin, &v38);
                AbortUSBPipe(Context, 1);
                USBVideoPinWaitForStarvation(Pin, 0);
              }
              v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 15);
              CaptureInitializePinContext(Context);
              KeReleaseSpinLock((PKSPIN_LOCK)Context + 15, v17);
              return ReferenceClockInterface;
            }
            if ( v16 == 1 )
            {
              if ( Context[377] == 2 )
              {
                if ( !*(_QWORD *)(v9[8] + 8 * v14) )
                  return (unsigned int)-1073741811;
                **((_DWORD **)Context + 12) = 1;
              }
              if ( Context[377] == 3 )
                return (unsigned int)CaptureStartTransfer(Context);
            }
            return ReferenceClockInterface;
          }
          if ( a2 )
            return ReferenceClockInterface;
          v18 = (void *)(*(_QWORD *)(v10 + 752) + 32 * Id);
          Timeout.QuadPart = 0;
          ReferenceClockInterface = KeWaitForSingleObject(v18, Executive, 0, 0, &Timeout);
          if ( ReferenceClockInterface )
            return 3221225626LL;
          v23 = (unsigned int)v38;
          v24 = 136LL * (unsigned int)v38;
          *(_QWORD *)(v7 + 112) = 0;
          *(_QWORD *)(v24 + *(_QWORD *)(v10 + 744) + 24) = Pin;
          if ( !*(_QWORD *)(v7 + 368) )
          {
            ReferenceClockInterface = KsPinGetReferenceClockInterface(Pin, (PIKSREFERENCECLOCK *)(v7 + 368));
            if ( (ReferenceClockInterface & 0x80000000) != 0 )
            {
              *(_QWORD *)(v7 + 368) = 0;
              ReferenceClockInterface = 0;
            }
          }
          if ( Context[440] )
          {
            v25 = SetSecureCommonPinContext(Context);
            ReferenceClockInterface = v25;
            if ( v25 < 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                WPP_SF_qqD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  80,
                  WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
                  v10,
                  Context,
                  v25);
              return ReferenceClockInterface;
            }
          }
          if ( Context[377] == 3 )
          {
            v26 = v9[8];
            v27 = *(_QWORD *)(v26 + 8 * v23);
            if ( *((_DWORD *)Context + 95) )
            {
              LOBYTE(v21) = Context[177];
              LOBYTE(v20) = 4;
              LODWORD(NumberOfBytes) = 11;
              LOBYTE(v19) = 1;
              ReferenceClockInterface = GetSetInterfaceControl(
                                          *((_QWORD *)Context + 53),
                                          v19,
                                          v20,
                                          v21,
                                          Context + 184,
                                          NumberOfBytes);
              if ( (ReferenceClockInterface & 0x80000000) != 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
                  WPP_SF_qq(
                    WPP_GLOBAL_Control->AttachedDevice,
                    81,
                    WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
                    v10,
                    Context);
                goto LABEL_51;
              }
              if ( v27 && (v28 = *(_QWORD *)(v27 + 80)) != 0 )
              {
                *((_QWORD *)Context + 10) = v28;
                *((_QWORD *)Context + 9) = *(_QWORD *)(v27 + 72);
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
                  WPP_SF_qq(
                    WPP_GLOBAL_Control->AttachedDevice,
                    83,
                    WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
                    v10,
                    Context);
              }
              else
              {
                v29 = SelectInterface(**((PVOID **)Context + 2));
                ReferenceClockInterface = v29;
                if ( v29 < 0 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
                  {
                    WPP_SF_qqD(
                      WPP_GLOBAL_Control->AttachedDevice,
                      82,
                      WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
                      v10,
                      Context,
                      v29);
                  }
                  goto LABEL_51;
                }
              }
            }
            else
            {
              ReferenceClockInterface = SelectStillInterfaceIsoch(Context, *(_QWORD *)(v26 + 8 * v23), 0);
              if ( (ReferenceClockInterface & 0x80000000) != 0 )
              {
LABEL_51:
                if ( Context[377] == 3 && !*((_DWORD *)Context + 95) )
                  SelectZeroBandwidthInterface(*(_QWORD *)Context, Pin->Id);
                if ( !KeReadStateSemaphore((PRKSEMAPHORE)(*(_QWORD *)(v10 + 752) + 32LL * Pin->Id)) )
                  KeReleaseSemaphore((PRKSEMAPHORE)(*(_QWORD *)(v10 + 752) + 32LL * Pin->Id), 0, 1, 0);
                v30 = *(_QWORD *)(v7 + 368);
                if ( v30 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
                  *(_QWORD *)(v7 + 368) = 0;
                }
                *(_QWORD *)(136 * v23 + *(_QWORD *)(v10 + 744) + 24) = 0;
                goto LABEL_59;
              }
            }
            Context[384] = 1;
          }
LABEL_59:
          v31 = _InterlockedIncrement((volatile signed __int32 *)(v10 + 848));
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
            WPP_SF_qqD(
              WPP_GLOBAL_Control->AttachedDevice,
              84,
              WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
              v10,
              Context,
              v31);
          return ReferenceClockInterface;
        }
        Context[384] = 0;
        *(_QWORD *)(136 * v14 + *(_QWORD *)(v10 + 744) + 24) = 0;
        v32 = *(_QWORD *)(v7 + 368);
        if ( v32 )
        {
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v32 + 16LL))(v32, 0);
          *(_QWORD *)(v7 + 368) = 0;
        }
        if ( !KeReadStateSemaphore((PRKSEMAPHORE)(*(_QWORD *)(v10 + 752) + 32LL * Pin->Id)) )
          KeReleaseSemaphore((PRKSEMAPHORE)(*(_QWORD *)(v10 + 752) + 32LL * Pin->Id), 0, 1, 0);
        v33 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 15);
        CaptureInitializePinContext(Context);
        KeReleaseSpinLock((PKSPIN_LOCK)Context + 15, v33);
        v34 = _InterlockedDecrement((volatile signed __int32 *)(v10 + 848));
        if ( v34 >= 0 )
        {
          v35 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          {
            v36 = 78;
            goto LABEL_73;
          }
        }
        else
        {
          v35 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          {
            v36 = 77;
LABEL_73:
            WPP_SF_qqD(v35->AttachedDevice, v36, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids, v10, Context, v34);
          }
        }
        if ( Context[440]
          && (int)ClearSecureCommonPinContext(Context) < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qq(
            WPP_GLOBAL_Control->AttachedDevice,
            79,
            WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
            v10,
            Context);
        }
        return ReferenceClockInterface;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 76, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids);
  return 3221225485LL;
}

```

## disassembly

```asm
0x140039650  mov     [rsp+arg_8], rbx
0x140039655  push    rbp
0x140039656  push    rsi
0x140039657  push    rdi
0x140039658  push    r12
0x14003965a  push    r13
0x14003965c  push    r14
0x14003965e  push    r15
0x140039660  sub     rsp, 30h
0x140039664  mov     rsi, [rcx+10h]
0x140039668  mov     ebx, r8d
0x14003966b  mov     r13d, edx
0x14003966e  mov     rdi, rcx
0x140039671  mov     r15, [rsi+60h]
0x140039675  mov     rcx, cs:WPP_GLOBAL_Control
0x14003967c  lea     rbp, WPP_GLOBAL_Control
0x140039683  cmp     rcx, rbp
0x140039686  jz      short loc_1400396A8
0x140039688  cmp     byte ptr [rcx+29h], 4
0x14003968c  jb      short loc_1400396A8
0x14003968e  mov     rcx, [rcx+18h]
0x140039692  mov     edx, 4Bh ; 'K'
0x140039697  mov     [rsp+68h+NumberOfBytes], rdi
0x14003969c  mov     r9d, r13d
0x14003969f  mov     dword ptr [rsp+68h+Timeout], ebx
0x1400396a3  call    WPP_SF_ddq
0x1400396a8  mov     rcx, rdi; Pin
0x1400396ab  call    cs:__imp_KsPinGetParentFilter
0x1400396b2  nop     dword ptr [rax+rax+00h]
0x1400396b7  xor     edx, edx; WaitReason
0x1400396b9  test    rax, rax
0x1400396bc  jz      loc_140039CA6
0x1400396c2  mov     r12, [rax+10h]
0x1400396c6  test    r12, r12
0x1400396c9  jz      loc_140039CA6
0x1400396cf  mov     r14, [r12]
0x1400396d3  test    r14, r14
0x1400396d6  jz      loc_140039CA6
0x1400396dc  mov     ebp, edx
0x1400396de  cmp     r13d, ebx
0x1400396e1  jz      loc_1400398C0
0x1400396e7  mov     r10d, [rdi+18h]
0x1400396eb  mov     rax, [r14+2E8h]
0x1400396f2  imul    rcx, r10, 88h
0x1400396f9  mov     ecx, [rcx+rax+8]
0x1400396fd  mov     dword ptr [rsp+68h+arg_0], ecx
0x140039701  test    ebx, ebx
0x140039703  jz      loc_140039B3D
0x140039709  sub     ebx, 1
0x14003970c  jz      loc_1400397D3
0x140039712  sub     ebx, 1
0x140039715  jz      short loc_140039764
0x140039717  cmp     ebx, 1
0x14003971a  jnz     loc_1400398C0
0x140039720  cmp     byte ptr [rsi+179h], 2
0x140039727  jnz     short loc_140039748
0x140039729  mov     rax, [r12+40h]
0x14003972e  cmp     [rax+rcx*8], rdx
0x140039732  jnz     short loc_14003973E
0x140039734  mov     ebp, 0C000000Dh
0x140039739  jmp     loc_1400398C0
0x14003973e  mov     rax, [rsi+60h]
0x140039742  mov     dword ptr [rax], 1
0x140039748  cmp     byte ptr [rsi+179h], 3
0x14003974f  jnz     loc_1400398C0
0x140039755  mov     rcx, rsi
0x140039758  call    CaptureStartTransfer
0x14003975d  mov     ebp, eax
0x14003975f  jmp     loc_1400398C0
0x140039764  cmp     byte ptr [rsi+179h], 3
0x14003976b  jnz     short loc_1400397A2
0x14003976d  cmp     [r15], edx
0x140039770  jz      short loc_1400397A2
0x140039772  mov     [r15], edx
0x140039775  mov     rcx, rdi
0x140039778  lea     rdx, [rsp+68h+arg_0]
0x14003977d  mov     [rsp+68h+arg_0], 0FFFFFFFFFECED300h
0x140039786  call    USBVideoPinWaitForStarvation
0x14003978b  mov     edx, 1
0x140039790  mov     rcx, rsi
0x140039793  call    AbortUSBPipe
0x140039798  xor     edx, edx
0x14003979a  mov     rcx, rdi
0x14003979d  call    USBVideoPinWaitForStarvation
0x1400397a2  lea     rcx, [rsi+78h]; SpinLock
0x1400397a6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400397ad  nop     dword ptr [rax+rax+00h]
0x1400397b2  mov     rcx, rsi
0x1400397b5  mov     bl, al
0x1400397b7  call    CaptureInitializePinContext
0x1400397bc  mov     dl, bl; NewIrql
0x1400397be  lea     rcx, [rsi+78h]; SpinLock
0x1400397c2  call    cs:__imp_KeReleaseSpinLock
0x1400397c9  nop     dword ptr [rax+rax+00h]
0x1400397ce  jmp     loc_1400398C0
0x1400397d3  test    r13d, r13d
0x1400397d6  jnz     loc_1400398C0
0x1400397dc  shl     r10, 5
0x1400397e0  lea     rax, [rsp+68h+arg_18]
0x1400397e8  add     r10, [r14+2F0h]
0x1400397ef  xor     r9d, r9d; Alertable
0x1400397f2  mov     rcx, r10; Object
0x1400397f5  mov     qword ptr [rsp+68h+arg_18], rdx
0x1400397fd  xor     r8d, r8d; WaitMode
0x140039800  mov     [rsp+68h+Timeout], rax; Timeout
0x140039805  call    cs:__imp_KeWaitForSingleObject
0x14003980c  nop     dword ptr [rax+rax+00h]
0x140039811  mov     ebp, eax
0x140039813  test    eax, eax
0x140039815  jz      short loc_140039821
0x140039817  mov     eax, 0C000009Ah
0x14003981c  jmp     loc_140039CD2
0x140039821  mov     r13d, dword ptr [rsp+68h+arg_0]
0x140039826  lea     rbx, [r15+170h]
0x14003982d  imul    rcx, r13, 88h
0x140039834  mov     qword ptr [r15+70h], 0
0x14003983c  mov     rax, [r14+2E8h]
0x140039843  mov     [rcx+rax+18h], rdi
0x140039848  cmp     qword ptr [rbx], 0
0x14003984c  jnz     short loc_14003986F
0x14003984e  mov     rdx, rbx; Interface
0x140039851  mov     rcx, rdi; Pin
0x140039854  call    cs:__imp_KsPinGetReferenceClockInterface
0x14003985b  nop     dword ptr [rax+rax+00h]
0x140039860  mov     ebp, eax
0x140039862  test    eax, eax
0x140039864  jns     short loc_14003986F
0x140039866  mov     qword ptr [rbx], 0
0x14003986d  xor     ebp, ebp
0x14003986f  cmp     byte ptr [rsi+1B8h], 0
0x140039876  jz      short loc_1400398C7
0x140039878  mov     rcx, rsi
0x14003987b  call    SetSecureCommonPinContext
0x140039880  mov     ebp, eax
0x140039882  test    eax, eax
0x140039884  jns     short loc_1400398CF
0x140039886  mov     rcx, cs:WPP_GLOBAL_Control
0x14003988d  lea     rbx, WPP_GLOBAL_Control
0x140039894  cmp     rcx, rbx
0x140039897  jz      short loc_1400398C0
0x140039899  cmp     byte ptr [rcx+29h], 4
0x14003989d  jb      short loc_1400398C0
0x14003989f  mov     rcx, [rcx+18h]
0x1400398a3  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x1400398aa  mov     dword ptr [rsp+68h+NumberOfBytes], eax
0x1400398ae  mov     edx, 50h ; 'P'
0x1400398b3  mov     r9, r14
0x1400398b6  mov     [rsp+68h+Timeout], rsi
0x1400398bb  call    WPP_SF_qqD
0x1400398c0  mov     eax, ebp
0x1400398c2  jmp     loc_140039CD2
0x1400398c7  test    ebp, ebp
0x1400398c9  js      loc_140039A45
0x1400398cf  cmp     byte ptr [rsi+179h], 3
0x1400398d6  jnz     loc_140039AE6
0x1400398dc  cmp     dword ptr [rsi+17Ch], 0
0x1400398e3  mov     rax, [r12+40h]
0x1400398e8  mov     rbx, [rax+r13*8]
0x1400398ec  jz      loc_140039A15
0x1400398f2  mov     r9b, [rsi+0B1h]; int
0x1400398f9  lea     rax, [rsi+0B8h]
0x140039900  mov     rcx, [rsi+1A8h]; int
0x140039907  mov     r8b, 4; int
0x14003990a  mov     dword ptr [rsp+68h+NumberOfBytes], 0Bh; NumberOfBytes
0x140039912  mov     dl, 1; int
0x140039914  mov     [rsp+68h+Timeout], rax; Src
0x140039919  call    GetSetInterfaceControl
0x14003991e  mov     ebp, eax
0x140039920  test    eax, eax
0x140039922  jns     short loc_140039967
0x140039924  mov     rcx, cs:WPP_GLOBAL_Control
0x14003992b  lea     rbx, WPP_GLOBAL_Control
0x140039932  cmp     rcx, rbx
0x140039935  jz      loc_140039A4C
0x14003993b  cmp     byte ptr [rcx+29h], 3
0x14003993f  jb      loc_140039A4C
0x140039945  mov     rcx, [rcx+18h]
0x140039949  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x140039950  mov     edx, 51h ; 'Q'
0x140039955  mov     [rsp+68h+Timeout], rsi
0x14003995a  mov     r9, r14
0x14003995d  call    WPP_SF_qq
0x140039962  jmp     loc_140039A4C
0x140039967  test    rbx, rbx
0x14003996a  jz      short loc_1400399C1
0x14003996c  mov     rax, [rbx+50h]
0x140039970  test    rax, rax
0x140039973  jz      short loc_1400399C1
0x140039975  mov     [rsi+50h], rax
0x140039979  mov     rax, [rbx+48h]
0x14003997d  mov     [rsi+48h], rax
0x140039981  mov     rcx, cs:WPP_GLOBAL_Control
0x140039988  lea     rbx, WPP_GLOBAL_Control
0x14003998f  cmp     rcx, rbx
0x140039992  jz      loc_140039A39
0x140039998  cmp     byte ptr [rcx+29h], 3
0x14003999c  jb      loc_140039A39
0x1400399a2  mov     rcx, [rcx+18h]
0x1400399a6  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x1400399ad  mov     edx, 53h ; 'S'
0x1400399b2  mov     [rsp+68h+Timeout], rsi
0x1400399b7  mov     r9, r14
0x1400399ba  call    WPP_SF_qq
0x1400399bf  jmp     short loc_140039A39
0x1400399c1  mov     rcx, [rsi+10h]
0x1400399c5  mov     r8, rdi
0x1400399c8  mov     rdx, r14
0x1400399cb  mov     rcx, [rcx]; StartPosition
0x1400399ce  call    SelectInterface
0x1400399d3  mov     ebp, eax
0x1400399d5  test    eax, eax
0x1400399d7  jns     short loc_140039A32
0x1400399d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400399e0  lea     rbx, WPP_GLOBAL_Control
0x1400399e7  cmp     rcx, rbx
0x1400399ea  jz      short loc_140039A4C
0x1400399ec  cmp     byte ptr [rcx+29h], 3
0x1400399f0  jb      short loc_140039A4C
0x1400399f2  mov     rcx, [rcx+18h]
0x1400399f6  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x1400399fd  mov     dword ptr [rsp+68h+NumberOfBytes], eax
0x140039a01  mov     edx, 52h ; 'R'
0x140039a06  mov     r9, r14
0x140039a09  mov     [rsp+68h+Timeout], rsi
0x140039a0e  call    WPP_SF_qqD
0x140039a13  jmp     short loc_140039A4C
0x140039a15  xor     r8d, r8d
0x140039a18  mov     rdx, rbx
0x140039a1b  mov     rcx, rsi
0x140039a1e  call    SelectStillInterfaceIsoch
0x140039a23  lea     rbx, WPP_GLOBAL_Control
0x140039a2a  mov     ebp, eax
0x140039a2c  test    eax, eax
0x140039a2e  js      short loc_140039A4C
0x140039a30  jmp     short loc_140039A39
0x140039a32  lea     rbx, WPP_GLOBAL_Control
0x140039a39  mov     byte ptr [rsi+180h], 1
0x140039a40  jmp     loc_140039AED
0x140039a45  lea     rbx, WPP_GLOBAL_Control
0x140039a4c  cmp     byte ptr [rsi+179h], 3
0x140039a53  jnz     short loc_140039A69
0x140039a55  cmp     dword ptr [rsi+17Ch], 0
0x140039a5c  jnz     short loc_140039A69
0x140039a5e  mov     edx, [rdi+18h]
0x140039a61  mov     rcx, [rsi]
0x140039a64  call    SelectZeroBandwidthInterface
0x140039a69  mov     ecx, [rdi+18h]
0x140039a6c  shl     rcx, 5
0x140039a70  add     rcx, [r14+2F0h]; Semaphore
0x140039a77  call    cs:__imp_KeReadStateSemaphore
0x140039a7e  nop     dword ptr [rax+rax+00h]
0x140039a83  test    eax, eax
0x140039a85  jnz     short loc_140039AAA
0x140039a87  mov     ecx, [rdi+18h]
0x140039a8a  lea     r8d, [rax+1]; Adjustment
0x140039a8e  shl     rcx, 5
0x140039a92  xor     r9d, r9d; Wait
0x140039a95  add     rcx, [r14+2F0h]; Semaphore
0x140039a9c  xor     edx, edx; Increment
0x140039a9e  call    cs:__imp_KeReleaseSemaphore
0x140039aa5  nop     dword ptr [rax+rax+00h]
0x140039aaa  mov     rcx, [r15+170h]
0x140039ab1  test    rcx, rcx
0x140039ab4  jz      short loc_140039ACD
0x140039ab6  mov     rax, [rcx]
0x140039ab9  mov     rax, [rax+10h]
0x140039abd  call    _guard_dispatch_icall
0x140039ac2  mov     qword ptr [r15+170h], 0
0x140039acd  mov     rax, [r14+2E8h]
0x140039ad4  imul    rcx, r13, 88h
0x140039adb  mov     qword ptr [rcx+rax+18h], 0
0x140039ae4  jmp     short loc_140039AED
0x140039ae6  lea     rbx, WPP_GLOBAL_Control
0x140039aed  mov     eax, 1
0x140039af2  lock xadd [r14+350h], eax
0x140039afb  inc     eax
0x140039afd  mov     rcx, cs:WPP_GLOBAL_Control
0x140039b04  cmp     rcx, rbx
0x140039b07  jz      loc_1400398C0
0x140039b0d  cmp     byte ptr [rcx+29h], 3
0x140039b11  jb      loc_1400398C0
0x140039b17  mov     rcx, [rcx+18h]
0x140039b1b  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x140039b22  mov     dword ptr [rsp+68h+NumberOfBytes], eax
0x140039b26  mov     edx, 54h ; 'T'
0x140039b2b  mov     r9, r14
0x140039b2e  mov     [rsp+68h+Timeout], rsi
0x140039b33  call    WPP_SF_qqD
0x140039b38  jmp     loc_1400398C0
0x140039b3d  imul    rcx, 88h
0x140039b44  mov     [rsi+180h], dl
0x140039b4a  mov     rax, [r14+2E8h]
0x140039b51  mov     [rcx+rax+18h], rdx
0x140039b56  mov     rcx, [r15+170h]
0x140039b5d  test    rcx, rcx
0x140039b60  jz      short loc_140039B75
0x140039b62  mov     rax, [rcx]
0x140039b65  mov     rax, [rax+10h]
0x140039b69  call    _guard_dispatch_icall
0x140039b6e  mov     [r15+170h], rbp
  ... truncated ...
```
