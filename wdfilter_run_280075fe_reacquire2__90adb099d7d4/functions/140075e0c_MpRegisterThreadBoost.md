# MpRegisterThreadBoost

- ea: `0x140075e0c`
- end: `0x1400762c7`
- name: `MpRegisterThreadBoost`
- size: `1211`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14005be60`

## callees

- `0x140003460`
- `0x1400034e0`
- `0x140003d20`
- `0x140003ed0`
- `0x1400051bc`
- `0x1400118d0`
- `0x14005961c`
- `0x140075e0c`
- `0x140078d50`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x14007601c`
- `ntoskrnl!ObfReferenceObject` at `0x14007601c`
- `ntoskrnl!ExAcquireFastMutex` at `0x140076040`
- `ntoskrnl!ExAcquireFastMutex` at `0x140076247`
- `ntoskrnl!ExAcquireFastMutex` at `0x140076040`
- `ntoskrnl!ExAcquireFastMutex` at `0x140076247`
- `ntoskrnl!PsThreadType` at `0x140075ebf`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14007614f`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400761a0`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140076207`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14007614f`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400761a0`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140076207`
- `ntoskrnl!KeBugCheck` at `0x1400762ba`
- `ntoskrnl!KeBugCheck` at `0x1400762ba`
- `ntoskrnl!ObfDereferenceObject` at `0x140076121`
- `ntoskrnl!ObfDereferenceObject` at `0x140076172`
- `ntoskrnl!ObfDereferenceObject` at `0x1400761d9`
- `ntoskrnl!ObfDereferenceObject` at `0x140076121`
- `ntoskrnl!ObfDereferenceObject` at `0x140076172`
- `ntoskrnl!ObfDereferenceObject` at `0x1400761d9`
- `ntoskrnl!ExReleaseFastMutex` at `0x140076108`
- `ntoskrnl!ExReleaseFastMutex` at `0x140076108`
- `FLTMGR!FltRetrieveIoPriorityInfo` at `0x140075f69`
- `FLTMGR!FltRetrieveIoPriorityInfo` at `0x140075f69`

## pseudocode

```c
__int64 __fastcall MpRegisterThreadBoost(__int64 a1)
{
  _QWORD *v1; // rbx
  _QWORD *v2; // rsi
  NTSTATUS v5; // edi
  __int64 v6; // rdx
  _QWORD *v7; // rax
  PETHREAD v8; // rcx
  _QWORD *v9; // rax
  __int64 v10; // r9
  __int64 v11; // rcx
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  __int64 v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  _QWORD *BoostControlUnsafe; // rax
  __int64 v18; // r9
  _QWORD *v19; // rcx
  void **v20; // rax
  int v21; // [rsp+20h] [rbp-30h]
  PETHREAD Thread; // [rsp+30h] [rbp-20h] BYREF
  struct _IO_PRIORITY_INFO PriorityInfo; // [rsp+38h] [rbp-18h] BYREF

  v1 = 0;
  Thread = 0;
  PriorityInfo = 0;
  v2 = 0;
  if ( (*(_DWORD *)(MpData + 864) & 4) == 0 )
    return 3221225659LL;
  if ( byte_1400269FC )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        WPP_27a2cd78501a34f8ef1761f750746219_Traceguids,
        KeGetCurrentThread());
    return 3221225659LL;
  }
  v5 = MpReferenceObjectByHandle(*(_QWORD *)(a1 + 16), 3168, (int)PsThreadType, 1, (PVOID *)&Thread);
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v6 = 13;
LABEL_11:
      _mm_lfence();
      v21 = v5;
LABEL_12:
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        v6,
        WPP_27a2cd78501a34f8ef1761f750746219_Traceguids,
        KeGetCurrentThread(),
        v21);
      goto LABEL_32;
    }
    goto LABEL_32;
  }
  if ( !*(_BYTE *)(a1 + 24) )
  {
    ExAcquireFastMutex((PFAST_MUTEX)(MpData + 2576));
    BoostControlUnsafe = (_QWORD *)MppFindBoostControlUnsafe(Thread);
    v1 = BoostControlUnsafe;
    if ( !BoostControlUnsafe )
    {
LABEL_31:
      ExReleaseFastMutex((PFAST_MUTEX)(MpData + 2576));
      goto LABEL_32;
    }
    v19 = (_QWORD *)*BoostControlUnsafe;
    if ( *(_QWORD **)(*BoostControlUnsafe + 8LL) == BoostControlUnsafe )
    {
      v20 = (void **)BoostControlUnsafe[1];
      if ( *v20 == v1 )
      {
        *v20 = v19;
        v19[1] = v20;
        if ( *(_DWORD *)(MpData + 2816) )
        {
          LOBYTE(v18) = 1;
          MppBoostThread(v1[2], *((unsigned int *)v1 + 7), *((unsigned int *)v1 + 6), v18);
        }
        goto LABEL_31;
      }
    }
    goto LABEL_57;
  }
  PriorityInfo.Size = 16;
  *(_QWORD *)&PriorityInfo.ThreadPriority = 0xFFFF;
  PriorityInfo.IoPriority = IoPriorityNormal;
  v5 = FltRetrieveIoPriorityInfo(0, 0, Thread, &PriorityInfo);
  if ( v5 >= 0 )
  {
    v7 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)(MpData + 2688));
    v1 = v7;
    if ( !v7 )
    {
      v5 = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v6 = 15;
        v21 = -1073741670;
        goto LABEL_12;
      }
      goto LABEL_32;
    }
    v7[2] = 0;
    v7[3] = 0;
    v7[1] = v7;
    *v7 = v7;
    *((_DWORD *)v7 + 7) = PriorityInfo.ThreadPriority;
    *((_DWORD *)v7 + 6) = PriorityInfo.IoPriority;
    v8 = Thread;
    v7[2] = Thread;
    ObfReferenceObject(v8);
    _InterlockedIncrement64(&ObTotalReferences);
    v5 = 0;
    ExAcquireFastMutex((PFAST_MUTEX)(MpData + 2576));
    v9 = (_QWORD *)MppFindBoostControlUnsafe(Thread);
    v2 = v9;
    if ( v9 )
    {
      v11 = *v9;
      if ( *(_QWORD **)(*v9 + 8LL) != v9 )
        goto LABEL_57;
      v12 = (_QWORD *)v9[1];
      if ( (_QWORD *)*v12 != v2 )
        goto LABEL_57;
      *v12 = v11;
      *(_QWORD *)(v11 + 8) = v12;
      if ( *(_DWORD *)(MpData + 2816) )
      {
        LOBYTE(v10) = 1;
        MppBoostThread(v1[2], *((unsigned int *)v1 + 7), *((unsigned int *)v1 + 6), v10);
      }
    }
    v13 = (_QWORD *)(MpData + 2560);
    v14 = *(_QWORD *)(MpData + 2560);
    if ( *(_QWORD *)(v14 + 8) == MpData + 2560 )
    {
      *v1 = v14;
      v1[1] = v13;
      *(_QWORD *)(v14 + 8) = v1;
      *v13 = v1;
      if ( *(_DWORD *)(MpData + 2816) )
        MppBoostThread(v1[2], *(unsigned int *)(MpData + 2820), 2, 0);
      v1 = 0;
      goto LABEL_31;
    }
LABEL_57:
    __fastfail(3u);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v6 = 14;
    goto LABEL_11;
  }
LABEL_32:
  if ( Thread )
  {
    ObfDereferenceObject(Thread);
    if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
    {
      if ( KdRefreshDebuggerNotPresent() )
        goto LABEL_58;
      __debugbreak();
    }
  }
  if ( v1 )
  {
    v15 = (void *)v1[2];
    if ( v15 )
    {
      ObfDereferenceObject(v15);
      if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
      {
        if ( KdRefreshDebuggerNotPresent() )
          goto LABEL_58;
        __debugbreak();
      }
    }
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(MpData + 2688), v1);
  }
  if ( v2 )
  {
    v16 = (void *)v2[2];
    if ( !v16 )
      goto LABEL_50;
    ObfDereferenceObject(v16);
    if ( _InterlockedDecrement64(&ObTotalReferences) >= 0 || *(int *)(MpData + 868) >= 0 )
      goto LABEL_50;
    if ( !KdRefreshDebuggerNotPresent() )
    {
      __debugbreak();
LABEL_50:
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(MpData + 2688), v2);
      return (unsigned int)v5;
    }
LABEL_58:
    KeBugCheck(1u);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140075e0c  mov     [rsp-18h+arg_8], rbx
0x140075e11  mov     [rsp-18h+arg_10], rsi
0x140075e16  push    rbp
0x140075e17  push    rdi
0x140075e18  push    r14
0x140075e1a  mov     rbp, rsp
0x140075e1d  sub     rsp, 50h
0x140075e21  mov     rax, cs:__security_cookie
0x140075e28  xor     rax, rsp
0x140075e2b  mov     [rbp+var_8], rax
0x140075e2f  mov     rax, cs:MpData
0x140075e36  xor     ebx, ebx
0x140075e38  xorps   xmm0, xmm0
0x140075e3b  mov     [rbp+Thread], rbx
0x140075e3f  movups  xmmword ptr [rbp+PriorityInfo.Size], xmm0
0x140075e43  xor     esi, esi
0x140075e45  mov     r14, rcx
0x140075e48  mov     edx, [rax+360h]
0x140075e4e  test    dl, 4
0x140075e51  jz      short loc_140075E98
0x140075e53  cmp     cs:byte_1400269FC, bl
0x140075e59  jz      short loc_140075EBF
0x140075e5b  mov     rcx, cs:WPP_GLOBAL_Control
0x140075e62  lea     rax, WPP_GLOBAL_Control
0x140075e69  cmp     rcx, rax
0x140075e6c  jz      short loc_140075E98
0x140075e6e  mov     eax, [rcx+2Ch]
0x140075e71  test    al, 2
0x140075e73  jz      short loc_140075E98
0x140075e75  mov     r9, gs:188h
0x140075e7e  lea     edx, [rbx+0Ch]
0x140075e81  mov     rcx, cs:WPP_GLOBAL_Control
0x140075e88  lea     r8, WPP_27a2cd78501a34f8ef1761f750746219_Traceguids
0x140075e8f  mov     rcx, [rcx+18h]
0x140075e93  call    WPP_SF_q
0x140075e98  mov     eax, 0C00000BBh
0x140075e9d  mov     rcx, [rbp+var_8]
0x140075ea1  xor     rcx, rsp; StackCookie
0x140075ea4  call    __security_check_cookie
0x140075ea9  lea     r11, [rsp+50h+var_s0]
0x140075eae  mov     rbx, [r11+28h]
0x140075eb2  mov     rsi, [r11+30h]
0x140075eb6  mov     rsp, r11
0x140075eb9  pop     r14
0x140075ebb  pop     rdi
0x140075ebc  pop     rbp
0x140075ebd  retn
0x140075ebf  mov     r8, cs:__imp_PsThreadType
0x140075ec6  lea     rax, [rbp+Thread]
0x140075eca  mov     rcx, [rcx+10h]; int
0x140075ece  mov     r9b, 1; int
0x140075ed1  mov     edx, 0C60h; int
0x140075ed6  mov     qword ptr [rsp+50h+var_30], rax; PVOID *
0x140075edb  mov     r8, [r8]; int
0x140075ede  call    MpReferenceObjectByHandle
0x140075ee3  mov     edi, eax
0x140075ee5  test    eax, eax
0x140075ee7  jns     short loc_140075F3D
0x140075ee9  mov     rcx, cs:WPP_GLOBAL_Control
0x140075ef0  lea     rax, WPP_GLOBAL_Control
0x140075ef7  cmp     rcx, rax
0x140075efa  jz      loc_140076114
0x140075f00  mov     ecx, [rcx+2Ch]
0x140075f03  test    cl, 1
0x140075f06  jz      loc_140076114
0x140075f0c  mov     edx, 0Dh
0x140075f11  lfence
0x140075f14  mov     [rsp+50h+var_30], edi
0x140075f18  mov     r9, gs:188h
0x140075f21  lea     r8, WPP_27a2cd78501a34f8ef1761f750746219_Traceguids
0x140075f28  mov     rcx, cs:WPP_GLOBAL_Control
0x140075f2f  mov     rcx, [rcx+18h]
0x140075f33  call    WPP_SF_qD
0x140075f38  jmp     loc_140076114
0x140075f3d  cmp     [r14+18h], bl
0x140075f41  jz      loc_140076239
0x140075f47  mov     r8, [rbp+Thread]; Thread
0x140075f4b  lea     r9, [rbp+PriorityInfo]; PriorityInfo
0x140075f4f  xor     edx, edx; FileObject
0x140075f51  mov     [rbp+PriorityInfo.Size], 10h
0x140075f58  xor     ecx, ecx; Data
0x140075f5a  mov     qword ptr [rbp+PriorityInfo.ThreadPriority], 0FFFFh
0x140075f62  mov     [rbp+PriorityInfo.IoPriority], 2
0x140075f69  call    cs:__imp_FltRetrieveIoPriorityInfo
0x140075f70  nop     dword ptr [rax+rax+00h]
0x140075f75  mov     edi, eax
0x140075f77  test    eax, eax
0x140075f79  jns     short loc_140075FA7
0x140075f7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140075f82  lea     rax, WPP_GLOBAL_Control
0x140075f89  cmp     rcx, rax
0x140075f8c  jz      loc_140076114
0x140075f92  mov     eax, [rcx+2Ch]
0x140075f95  test    al, 1
0x140075f97  jz      loc_140076114
0x140075f9d  mov     edx, 0Eh
0x140075fa2  jmp     loc_140075F11
0x140075fa7  mov     rcx, cs:MpData
0x140075fae  add     rcx, 0A80h; Lookaside
0x140075fb5  call    ExAllocateFromPagedLookasideList
0x140075fba  mov     rbx, rax
0x140075fbd  test    rax, rax
0x140075fc0  jnz     short loc_140075FF9
0x140075fc2  mov     edi, 0C000009Ah
0x140075fc7  mov     rcx, cs:WPP_GLOBAL_Control
0x140075fce  lea     rax, WPP_GLOBAL_Control
0x140075fd5  cmp     rcx, rax
0x140075fd8  jz      loc_140076114
0x140075fde  mov     eax, [rcx+2Ch]
0x140075fe1  test    al, 1
0x140075fe3  jz      loc_140076114
0x140075fe9  lea     edx, [rbx+0Fh]
0x140075fec  mov     [rsp+50h+var_30], 0C000009Ah
0x140075ff4  jmp     loc_140075F18
0x140075ff9  mov     [rax+10h], rsi
0x140075ffd  mov     [rax+18h], rsi
0x140076001  mov     [rax+8], rbx
0x140076005  mov     [rax], rbx
0x140076008  mov     eax, [rbp+PriorityInfo.ThreadPriority]
0x14007600b  mov     [rbx+1Ch], eax
0x14007600e  mov     eax, [rbp+PriorityInfo.IoPriority]
0x140076011  mov     [rbx+18h], eax
0x140076014  mov     rcx, [rbp+Thread]; Object
0x140076018  mov     [rbx+10h], rcx
0x14007601c  call    cs:__imp_ObfReferenceObject
0x140076023  nop     dword ptr [rax+rax+00h]
0x140076028  lock inc cs:ObTotalReferences
0x140076030  mov     rcx, cs:MpData
0x140076037  xor     edi, edi
0x140076039  add     rcx, 0A10h; FastMutex
0x140076040  call    cs:__imp_ExAcquireFastMutex
0x140076047  nop     dword ptr [rax+rax+00h]
0x14007604c  mov     rcx, [rbp+Thread]
0x140076050  call    MppFindBoostControlUnsafe
0x140076055  mov     rsi, rax
0x140076058  test    rax, rax
0x14007605b  jz      short loc_1400760A2
0x14007605d  mov     rcx, [rax]
0x140076060  cmp     [rcx+8], rax
0x140076064  jnz     loc_1400762AE
0x14007606a  mov     rax, [rax+8]
0x14007606e  cmp     [rax], rsi
0x140076071  jnz     loc_1400762AE
0x140076077  mov     [rax], rcx
0x14007607a  mov     [rcx+8], rax
0x14007607e  mov     rax, cs:MpData
0x140076085  mov     ecx, [rax+0B00h]
0x14007608b  test    ecx, ecx
0x14007608d  jz      short loc_1400760A2
0x14007608f  mov     r8d, [rbx+18h]
0x140076093  mov     r9b, 1
0x140076096  mov     edx, [rbx+1Ch]
0x140076099  mov     rcx, [rbx+10h]
0x14007609d  call    MppBoostThread
0x1400760a2  mov     rax, cs:MpData
0x1400760a9  add     rax, 0A00h
0x1400760af  mov     rcx, [rax]
0x1400760b2  cmp     [rcx+8], rax
0x1400760b6  jnz     loc_1400762AE
0x1400760bc  mov     [rbx], rcx
0x1400760bf  mov     [rbx+8], rax
0x1400760c3  mov     [rcx+8], rbx
0x1400760c7  mov     [rax], rbx
0x1400760ca  mov     rax, cs:MpData
0x1400760d1  mov     ecx, [rax+0B00h]
0x1400760d7  test    ecx, ecx
0x1400760d9  jz      short loc_1400760F8
0x1400760db  mov     rdx, cs:MpData
0x1400760e2  xor     r9d, r9d
0x1400760e5  mov     rcx, [rbx+10h]
0x1400760e9  mov     edx, [rdx+0B04h]
0x1400760ef  lea     r8d, [r9+2]
0x1400760f3  call    MppBoostThread
0x1400760f8  xor     ebx, ebx
0x1400760fa  mov     rcx, cs:MpData
0x140076101  add     rcx, 0A10h; FastMutex
0x140076108  call    cs:__imp_ExReleaseFastMutex
0x14007610f  nop     dword ptr [rax+rax+00h]
0x140076114  mov     rcx, [rbp+Thread]; Object
0x140076118  or      r14, 0FFFFFFFFFFFFFFFFh
0x14007611c  test    rcx, rcx
0x14007611f  jz      short loc_140076164
0x140076121  call    cs:__imp_ObfDereferenceObject
0x140076128  nop     dword ptr [rax+rax+00h]
0x14007612d  mov     rax, r14
0x140076130  lock xadd cs:ObTotalReferences, rax
0x140076139  add     rax, r14
0x14007613c  jns     short loc_140076164
0x14007613e  mov     rax, cs:MpData
0x140076145  mov     ecx, [rax+364h]
0x14007614b  test    ecx, ecx
0x14007614d  jns     short loc_140076164
0x14007614f  call    cs:__imp_KdRefreshDebuggerNotPresent
0x140076156  nop     dword ptr [rax+rax+00h]
0x14007615b  test    al, al
0x14007615d  jnz     loc_1400762B5
0x140076163  int     3; Trap to Debugger
0x140076164  test    rbx, rbx
0x140076167  jz      short loc_1400761CB
0x140076169  mov     rcx, [rbx+10h]; Object
0x14007616d  test    rcx, rcx
0x140076170  jz      short loc_1400761B5
0x140076172  call    cs:__imp_ObfDereferenceObject
0x140076179  nop     dword ptr [rax+rax+00h]
0x14007617e  mov     rax, r14
0x140076181  lock xadd cs:ObTotalReferences, rax
0x14007618a  add     rax, r14
0x14007618d  jns     short loc_1400761B5
0x14007618f  mov     rax, cs:MpData
0x140076196  mov     ecx, [rax+364h]
0x14007619c  test    ecx, ecx
0x14007619e  jns     short loc_1400761B5
0x1400761a0  call    cs:__imp_KdRefreshDebuggerNotPresent
0x1400761a7  nop     dword ptr [rax+rax+00h]
0x1400761ac  test    al, al
0x1400761ae  jnz     loc_1400762B5
0x1400761b4  int     3; Trap to Debugger
0x1400761b5  mov     rcx, cs:MpData
0x1400761bc  mov     rdx, rbx; Entry
0x1400761bf  add     rcx, 0A80h; Lookaside
0x1400761c6  call    ExFreeToNPagedLookasideList
0x1400761cb  test    rsi, rsi
0x1400761ce  jz      short loc_140076232
0x1400761d0  mov     rcx, [rsi+10h]; Object
0x1400761d4  test    rcx, rcx
0x1400761d7  jz      short loc_14007621C
0x1400761d9  call    cs:__imp_ObfDereferenceObject
0x1400761e0  nop     dword ptr [rax+rax+00h]
0x1400761e5  mov     rax, r14
0x1400761e8  lock xadd cs:ObTotalReferences, rax
0x1400761f1  add     rax, r14
0x1400761f4  jns     short loc_14007621C
0x1400761f6  mov     rax, cs:MpData
0x1400761fd  mov     ecx, [rax+364h]
0x140076203  test    ecx, ecx
0x140076205  jns     short loc_14007621C
0x140076207  call    cs:__imp_KdRefreshDebuggerNotPresent
0x14007620e  nop     dword ptr [rax+rax+00h]
0x140076213  test    al, al
0x140076215  jnz     loc_1400762B5
0x14007621b  int     3; Trap to Debugger
0x14007621c  mov     rcx, cs:MpData
0x140076223  mov     rdx, rsi; Entry
0x140076226  add     rcx, 0A80h; Lookaside
0x14007622d  call    ExFreeToNPagedLookasideList
0x140076232  mov     eax, edi
0x140076234  jmp     loc_140075E9D
0x140076239  mov     rcx, cs:MpData
0x140076240  add     rcx, 0A10h; FastMutex
0x140076247  call    cs:__imp_ExAcquireFastMutex
0x14007624e  nop     dword ptr [rax+rax+00h]
0x140076253  mov     rcx, [rbp+Thread]
0x140076257  call    MppFindBoostControlUnsafe
0x14007625c  mov     rbx, rax
0x14007625f  test    rax, rax
0x140076262  jz      loc_1400760FA
0x140076268  mov     rcx, [rax]
0x14007626b  cmp     [rcx+8], rax
0x14007626f  jnz     short loc_1400762AE
0x140076271  mov     rax, [rax+8]
0x140076275  cmp     [rax], rbx
0x140076278  jnz     short loc_1400762AE
0x14007627a  mov     [rax], rcx
0x14007627d  mov     [rcx+8], rax
0x140076281  mov     rax, cs:MpData
0x140076288  mov     ecx, [rax+0B00h]
0x14007628e  test    ecx, ecx
0x140076290  jz      loc_1400760FA
0x140076296  mov     r8d, [rbx+18h]
0x14007629a  mov     r9b, 1
0x14007629d  mov     edx, [rbx+1Ch]
0x1400762a0  mov     rcx, [rbx+10h]
0x1400762a4  call    MppBoostThread
0x1400762a9  jmp     loc_1400760FA
0x1400762ae  mov     ecx, 3
0x1400762b3  int     29h; Win8: RtlFailFast(ecx)
0x1400762b5  mov     ecx, 1; BugCheckCode
0x1400762ba  call    cs:__imp_KeBugCheck
```
