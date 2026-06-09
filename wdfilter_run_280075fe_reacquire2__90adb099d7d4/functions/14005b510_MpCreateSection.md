# MpCreateSection

- ea: `0x14005b510`
- end: `0x14005be5d`
- name: `MpCreateSection`
- size: `2381`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14005be60`

## callees

- `0x1400018a4`
- `0x140003d20`
- `0x1400051bc`
- `0x140009bf0`
- `0x14000aa0c`
- `0x14000aa80`
- `0x14000ae58`
- `0x140011890`
- `0x1400118d0`
- `0x14005b0b8`
- `0x14005b510`

## import_xrefs

- `ntoskrnl!NtClose` at `0x14005bcdb`
- `ntoskrnl!NtClose` at `0x14005bcdb`
- `ntoskrnl!FsRtlCreateSectionForDataScan` at `0x14005b9d6`
- `ntoskrnl!FsRtlCreateSectionForDataScan` at `0x14005b9d6`
- `ntoskrnl!ObfReferenceObject` at `0x14005b635`
- `ntoskrnl!ObfReferenceObject` at `0x14005b635`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005b5dc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005b67a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005b881`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005b8a0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005be10`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005b5dc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005b67a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005b881`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005b8a0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005be10`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b5d0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b66e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b875`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005be04`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b5d0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b66e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b875`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005be04`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005b567`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005b7ff`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005b567`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005b7ff`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005b552`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005b693`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005b7ea`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005b552`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005b693`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005b7ea`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005b847`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005b847`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14005ba68`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14005bc21`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14005bd1a`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14005ba68`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14005bc21`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14005bd1a`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14005b857`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14005b857`
- `ntoskrnl!KeBugCheck` at `0x14005bb29`
- `ntoskrnl!KeBugCheck` at `0x14005bb29`
- `ntoskrnl!ObfDereferenceObject` at `0x14005b8cb`
- `ntoskrnl!ObfDereferenceObject` at `0x14005bbee`
- `ntoskrnl!ObfDereferenceObject` at `0x14005bceb`
- `ntoskrnl!ObfDereferenceObject` at `0x14005b8cb`
- `ntoskrnl!ObfDereferenceObject` at `0x14005bbee`
- `ntoskrnl!ObfDereferenceObject` at `0x14005bceb`
- `FLTMGR!FltReleaseContext` at `0x14005b8bc`
- `FLTMGR!FltReleaseContext` at `0x14005ba8e`
- `FLTMGR!FltReleaseContext` at `0x14005bbdf`
- `FLTMGR!FltReleaseContext` at `0x14005b8bc`
- `FLTMGR!FltReleaseContext` at `0x14005ba8e`
- `FLTMGR!FltReleaseContext` at `0x14005bbdf`
- `FLTMGR!FltReferenceContext` at `0x14005b654`
- `FLTMGR!FltReferenceContext` at `0x14005b654`
- `FLTMGR!FltAllocateContext` at `0x14005b6db`
- `FLTMGR!FltAllocateContext` at `0x14005b6db`

## pseudocode

```c
__int64 __fastcall MpCreateSection(__int64 a1, union _LARGE_INTEGER *a2)
{
  ULONG_PTR v2; // rbx
  _QWORD *i; // rax
  __int64 v6; // rbx
  __int64 v8; // rsi
  struct _FILE_OBJECT *v9; // r13
  NTSTATUS v10; // eax
  unsigned int v11; // ebx
  ULONG_PTR v12; // rbx
  DWORD v13; // edi
  PFLT_CONTEXT v14; // rcx
  NTSTATUS v15; // eax
  NTSTATUS v16; // ebx
  int v17; // eax
  int v18; // [rsp+70h] [rbp-9h]
  PFLT_CONTEXT Context; // [rsp+78h] [rbp-1h] BYREF
  PVOID SectionObject; // [rsp+80h] [rbp+7h] BYREF
  void *SectionHandle; // [rsp+88h] [rbp+Fh] BYREF

  v2 = MpData;
  SectionObject = 0;
  SectionHandle = 0;
  Context = 0;
  KeEnterCriticalRegion();
  ExAcquireResourceSharedLite((PERESOURCE)(v2 + 752), 1u);
  for ( i = *(_QWORD **)(MpData + 568); ; i = (_QWORD *)*i )
  {
    if ( i == (_QWORD *)(MpData + 568) )
      goto LABEL_7;
    v6 = *(_QWORD *)(a1 + 16);
    if ( (_QWORD *)v6 == i - 7 )
      break;
  }
  if ( *(_DWORD *)(v6 + 88) != *(_DWORD *)(a1 + 24) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_qqDD(
        WPP_GLOBAL_Control->AttachedDevice,
        66,
        (unsigned int)WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
        (unsigned int)KeGetCurrentThread(),
        v6);
    goto LABEL_7;
  }
  if ( !_InterlockedCompareExchange64((volatile signed __int64 *)(v6 + 96), (signed __int64)KeGetCurrentThread(), 0) )
  {
    ObfReferenceObject(*(PVOID *)(v6 + 72));
    _InterlockedIncrement64(&ObTotalReferences);
    v8 = *(_QWORD *)(a1 + 16);
    v9 = *(struct _FILE_OBJECT **)(v6 + 72);
    FltReferenceContext((PFLT_CONTEXT)v8);
    ExReleaseResourceLite((PERESOURCE)(MpData + 752));
    KeLeaveCriticalRegion();
    if ( *(_QWORD *)(v8 + 120) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_qq(
          WPP_GLOBAL_Control->AttachedDevice,
          73,
          (unsigned int)WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
          (unsigned int)KeGetCurrentThread(),
          *(_QWORD *)(v8 + 120));
      FltReleaseContext((PFLT_CONTEXT)v8);
      ObfDereferenceObject(v9);
      if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
      {
        if ( KdRefreshDebuggerNotPresent() )
          goto LABEL_51;
        __debugbreak();
      }
      return 3221225539LL;
    }
    KeEnterCriticalRegion();
    if ( (*(_DWORD *)(*(_QWORD *)(v8 + 8) + 80LL) & 4) != 0 )
    {
      v10 = FltAllocateContext(*(PFLT_FILTER *)(MpData + 16), 0x40u, 8u, PagedPool, &Context);
      v11 = v10;
      if ( v10 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            74,
            WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
            (unsigned int)v10);
        }
        v13 = 0;
        goto LABEL_26;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 75, WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids, Context);
      *(_WORD *)Context = -9706;
      *((_WORD *)Context + 1) = 8;
      *((_DWORD *)Context + 1) = 0;
      if ( (*(_DWORD *)(MpData + 868) & 0x80u) != 0 )
      {
        if ( (*(_DWORD *)(v8 + 48) & 0x20000) != 0 )
        {
          MpSuppressFileAccessTimeUpdateIfNeeded(v8, v9, Context);
          *(_DWORD *)(v8 + 48) &= ~0x20000u;
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          WPP_SF_Z(
            WPP_GLOBAL_Control->AttachedDevice,
            76,
            WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
            &v9->FileName);
        }
      }
      v18 = (*(__int64 (__fastcall **)(_QWORD, struct _FILE_OBJECT *, PFLT_CONTEXT, __int64, _QWORD, _QWORD, int, int, _DWORD, void **, PVOID *, union _LARGE_INTEGER *))(MpData + 72))(
              *(_QWORD *)(*(_QWORD *)(v8 + 8) + 104LL),
              v9,
              Context,
              5,
              0,
              0,
              2,
              0x8000000,
              0,
              &SectionHandle,
              &SectionObject,
              a2 + 3);
      if ( v18 >= 0 )
      {
        _InterlockedIncrement64(&ObTotalReferences);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          _mm_lfence();
          WPP_SF_qZ(
            WPP_GLOBAL_Control->AttachedDevice,
            78,
            (unsigned int)WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
            (_DWORD)SectionObject,
            (__int64)&v9->FileName);
        }
LABEL_21:
        v12 = MpData;
        KeEnterCriticalRegion();
        ExAcquireResourceSharedLite((PERESOURCE)(v12 + 752), 1u);
        if ( *(struct _FILE_OBJECT **)(v8 + 72) == v9 && *(_DWORD *)(v8 + 88) == *(_DWORD *)(a1 + 24) )
        {
          *(_QWORD *)(v8 + 120) = SectionHandle;
          *(_QWORD *)(v8 + 128) = SectionObject;
          *(_QWORD *)(v8 + 136) = Context;
          Context = 0;
          *(_QWORD *)(v8 + 104) = IoGetCurrentProcess();
          *(_QWORD *)(v8 + 112) = PsGetCurrentProcessId();
        }
        else
        {
          v18 = -1073741643;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              81,
              WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
              SectionObject);
          }
          NtClose(SectionHandle);
          ObfDereferenceObject(SectionObject);
          if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
          {
            if ( KdRefreshDebuggerNotPresent() )
              goto LABEL_51;
            __debugbreak();
          }
          if ( Context )
          {
            v17 = (*(__int64 (**)(void))(MpData + 80))();
            if ( v17 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                WPP_SF_qD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  82,
                  WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
                  Context,
                  v17);
              }
            }
            else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 83, WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids, Context);
            }
          }
          SectionHandle = 0;
          SectionObject = 0;
        }
        ExReleaseResourceLite((PERESOURCE)(MpData + 752));
        KeLeaveCriticalRegion();
        v13 = v18;
        goto LABEL_25;
      }
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
      {
        v13 = v18;
LABEL_25:
        v11 = 0;
        a2[2].QuadPart = (LONGLONG)SectionHandle;
        a2[1].LowPart = v13;
LABEL_26:
        KeLeaveCriticalRegion();
        v14 = Context;
        if ( Context )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              84,
              WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
              Context,
              v13);
            v14 = Context;
          }
          FltReleaseContext(v14);
        }
        FltReleaseContext((PFLT_CONTEXT)v8);
        ObfDereferenceObject(v9);
        if ( _InterlockedDecrement64(&ObTotalReferences) >= 0 || *(int *)(MpData + 868) >= 0 )
          return v11;
        if ( !KdRefreshDebuggerNotPresent() )
        {
          __debugbreak();
          return v11;
        }
LABEL_51:
        KeBugCheck(1u);
      }
      _mm_lfence();
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        77,
        WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
        (unsigned int)v18);
    }
    else
    {
      v15 = FsRtlCreateSectionForDataScan(&SectionHandle, &SectionObject, a2 + 3, v9, 5u, 0, 0, 2u, 0x8000000u, 0);
      v18 = v15;
      if ( v15 >= 0 )
      {
        _InterlockedIncrement64(&ObTotalReferences);
        v16 = v15;
        v18 = v15;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          v18 = v15;
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            _mm_lfence();
            WPP_SF_qZ(
              WPP_GLOBAL_Control->AttachedDevice,
              80,
              (unsigned int)WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
              (_DWORD)SectionObject,
              (__int64)&v9->FileName);
            v18 = v16;
          }
        }
        goto LABEL_21;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v13 = v15;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          _mm_lfence();
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            79,
            WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
            (unsigned int)v15);
        }
        goto LABEL_25;
      }
    }
    v13 = v18;
    goto LABEL_25;
  }
LABEL_7:
  ExReleaseResourceLite((PERESOURCE)(MpData + 752));
  KeLeaveCriticalRegion();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      72,
      WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
      KeGetCurrentThread());
  return 3221225654LL;
}

```

## disassembly

```asm
0x14005b510  push    rbp
0x14005b512  push    rbx
0x14005b513  push    rdi
0x14005b514  push    r12
0x14005b516  push    r15
0x14005b518  lea     rbp, [rsp-37h]
0x14005b51d  sub     rsp, 0B0h
0x14005b524  mov     rax, cs:__security_cookie
0x14005b52b  xor     rax, rsp
0x14005b52e  mov     [rbp+57h+var_40], rax
0x14005b532  mov     rbx, cs:MpData
0x14005b539  xor     r15d, r15d
0x14005b53c  mov     [rbp+57h+var_60], r15d
0x14005b540  mov     r12, rdx
0x14005b543  mov     [rbp+57h+SectionObject], r15
0x14005b547  mov     rdi, rcx
0x14005b54a  mov     [rbp+57h+SectionHandle], r15
0x14005b54e  mov     [rbp+57h+Context], r15
0x14005b552  call    cs:__imp_KeEnterCriticalRegion
0x14005b559  nop     dword ptr [rax+rax+00h]
0x14005b55e  mov     dl, 1; Wait
0x14005b560  lea     rcx, [rbx+2F0h]; Resource
0x14005b567  call    cs:__imp_ExAcquireResourceSharedLite
0x14005b56e  nop     dword ptr [rax+rax+00h]
0x14005b573  mov     rdx, cs:MpData
0x14005b57a  add     rdx, 238h
0x14005b581  mov     rax, [rdx]
0x14005b584  cmp     rax, rdx
0x14005b587  jz      loc_14005BDF6
0x14005b58d  mov     rbx, [rdi+10h]
0x14005b591  lea     rcx, [rax-38h]
0x14005b595  cmp     rbx, rcx
0x14005b598  jz      short loc_14005B59F
0x14005b59a  mov     rax, [rax]
0x14005b59d  jmp     short loc_14005B584
0x14005b59f  mov     ecx, [rdi+18h]
0x14005b5a2  mov     r8d, [rbx+58h]
0x14005b5a6  cmp     r8d, ecx
0x14005b5a9  jz      short loc_14005B602
0x14005b5ab  mov     rax, cs:WPP_GLOBAL_Control
0x14005b5b2  lea     r15, WPP_GLOBAL_Control
0x14005b5b9  cmp     rax, r15
0x14005b5bc  jnz     loc_14005BB36
0x14005b5c2  mov     rcx, cs:MpData
0x14005b5c9  add     rcx, 2F0h; Resource
0x14005b5d0  call    cs:__imp_ExReleaseResourceLite
0x14005b5d7  nop     dword ptr [rax+rax+00h]
0x14005b5dc  call    cs:__imp_KeLeaveCriticalRegion
0x14005b5e3  nop     dword ptr [rax+rax+00h]
0x14005b5e8  mov     rax, cs:WPP_GLOBAL_Control
0x14005b5ef  cmp     rax, r15
0x14005b5f2  jnz     loc_14005BE28
0x14005b5f8  mov     eax, 0C00000B6h
0x14005b5fd  jmp     loc_14005B904
0x14005b602  mov     rcx, gs:188h
0x14005b60b  xor     eax, eax
0x14005b60d  lock cmpxchg [rbx+60h], rcx
0x14005b613  jnz     loc_14005BDF6
0x14005b619  mov     rcx, [rbx+48h]; Object
0x14005b61d  mov     [rsp+0D0h+arg_10], rsi
0x14005b625  mov     [rsp+0D0h+var_28], r13
0x14005b62d  mov     [rsp+0D0h+var_30], r14
0x14005b635  call    cs:__imp_ObfReferenceObject
0x14005b63c  nop     dword ptr [rax+rax+00h]
0x14005b641  lock inc cs:ObTotalReferences
0x14005b649  mov     rsi, [rdi+10h]
0x14005b64d  mov     r13, [rbx+48h]
0x14005b651  mov     rcx, rsi; Context
0x14005b654  call    cs:__imp_FltReferenceContext
0x14005b65b  nop     dword ptr [rax+rax+00h]
0x14005b660  mov     rcx, cs:MpData
0x14005b667  add     rcx, 2F0h; Resource
0x14005b66e  call    cs:__imp_ExReleaseResourceLite
0x14005b675  nop     dword ptr [rax+rax+00h]
0x14005b67a  call    cs:__imp_KeLeaveCriticalRegion
0x14005b681  nop     dword ptr [rax+rax+00h]
0x14005b686  mov     rcx, [rsi+78h]
0x14005b68a  test    rcx, rcx
0x14005b68d  jnz     loc_14005BB98
0x14005b693  call    cs:__imp_KeEnterCriticalRegion
0x14005b69a  nop     dword ptr [rax+rax+00h]
0x14005b69f  mov     rax, [rsi+8]
0x14005b6a3  mov     r14, 0FFFFFFFFFFFFFFFFh
0x14005b6aa  mov     ecx, [rax+50h]
0x14005b6ad  test    cl, 4
0x14005b6b0  jz      loc_14005B99F
0x14005b6b6  mov     rcx, cs:MpData
0x14005b6bd  lea     rax, [rbp+57h+Context]
0x14005b6c1  mov     edx, 40h ; '@'; ContextType
0x14005b6c6  mov     [rsp+0D0h+ReturnedContext], rax; ReturnedContext
0x14005b6cb  mov     r9d, 1; PoolType
0x14005b6d1  mov     r8d, 8; ContextSize
0x14005b6d7  mov     rcx, [rcx+10h]; Filter
0x14005b6db  call    cs:__imp_FltAllocateContext
0x14005b6e2  nop     dword ptr [rax+rax+00h]
0x14005b6e7  mov     ebx, eax
0x14005b6e9  test    eax, eax
0x14005b6eb  js      loc_14005B949
0x14005b6f1  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b6f8  lea     r15, WPP_GLOBAL_Control
0x14005b6ff  cmp     rcx, r15
0x14005b702  jnz     loc_14005B920
0x14005b708  mov     rax, [rbp+57h+Context]
0x14005b70c  mov     word ptr [rax], 0DA16h
0x14005b711  mov     rax, [rbp+57h+Context]
0x14005b715  mov     word ptr [rax+2], 8
0x14005b71b  mov     rax, [rbp+57h+Context]
0x14005b71f  mov     dword ptr [rax+4], 0
0x14005b726  mov     rax, cs:MpData
0x14005b72d  mov     ecx, [rax+364h]
0x14005b733  test    cl, cl
0x14005b735  jns     short loc_14005B754
0x14005b737  test    dword ptr [rsi+30h], 20000h
0x14005b73e  jnz     loc_14005B968
0x14005b744  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b74b  cmp     rcx, r15
0x14005b74e  jnz     loc_14005BA9F
0x14005b754  mov     r10, [rsi+8]
0x14005b758  lea     rcx, [r12+18h]
0x14005b75d  mov     rax, cs:MpData
0x14005b764  mov     r9d, 5
0x14005b76a  mov     r8, [rbp+57h+Context]
0x14005b76e  mov     rdx, r13
0x14005b771  mov     [rsp+0D0h+var_78], rcx
0x14005b776  lea     rcx, [rbp+57h+SectionObject]
0x14005b77a  mov     [rsp+0D0h+var_80], rcx
0x14005b77f  lea     rcx, [rbp+57h+SectionHandle]
0x14005b783  mov     rax, [rax+48h]
0x14005b787  mov     qword ptr [rsp+0D0h+Flags], rcx
0x14005b78c  xor     ecx, ecx
0x14005b78e  mov     [rsp+0D0h+AllocationAttributes], ecx
0x14005b792  mov     [rsp+0D0h+SectionPageProtection], 8000000h
0x14005b79a  mov     dword ptr [rsp+0D0h+MaximumSize], 2
0x14005b7a2  mov     [rsp+0D0h+ObjectAttributes], rcx
0x14005b7a7  mov     [rsp+0D0h+ReturnedContext], rcx
0x14005b7ac  mov     rcx, [r10+68h]
0x14005b7b0  call    cs:__guard_dispatch_icall_fptr
0x14005b7b6  mov     [rbp+57h+var_60], eax
0x14005b7b9  mov     r9d, eax
0x14005b7bc  test    eax, eax
0x14005b7be  js      loc_14005B983
0x14005b7c4  lock inc cs:ObTotalReferences
0x14005b7cc  mov     rax, cs:WPP_GLOBAL_Control
0x14005b7d3  cmp     rax, r15
0x14005b7d6  jz      short loc_14005B7E3
0x14005b7d8  mov     eax, [rax+2Ch]
0x14005b7db  test    al, 4
0x14005b7dd  jnz     loc_14005BC73
0x14005b7e3  mov     rbx, cs:MpData
0x14005b7ea  call    cs:__imp_KeEnterCriticalRegion
0x14005b7f1  nop     dword ptr [rax+rax+00h]
0x14005b7f6  mov     dl, 1; Wait
0x14005b7f8  lea     rcx, [rbx+2F0h]; Resource
0x14005b7ff  call    cs:__imp_ExAcquireResourceSharedLite
0x14005b806  nop     dword ptr [rax+rax+00h]
0x14005b80b  cmp     [rsi+48h], r13
0x14005b80f  jnz     loc_14005BCA4
0x14005b815  mov     eax, [rdi+18h]
0x14005b818  cmp     [rsi+58h], eax
0x14005b81b  jnz     loc_14005BCA4
0x14005b821  mov     rax, [rbp+57h+SectionHandle]
0x14005b825  mov     [rsi+78h], rax
0x14005b829  mov     rax, [rbp+57h+SectionObject]
0x14005b82d  mov     [rsi+80h], rax
0x14005b834  mov     rax, [rbp+57h+Context]
0x14005b838  mov     [rsi+88h], rax
0x14005b83f  mov     [rbp+57h+Context], 0
0x14005b847  call    cs:__imp_IoGetCurrentProcess
0x14005b84e  nop     dword ptr [rax+rax+00h]
0x14005b853  mov     [rsi+68h], rax
0x14005b857  call    cs:__imp_PsGetCurrentProcessId
0x14005b85e  nop     dword ptr [rax+rax+00h]
0x14005b863  mov     [rsi+70h], rax
0x14005b867  mov     rcx, cs:MpData
0x14005b86e  add     rcx, 2F0h; Resource
0x14005b875  call    cs:__imp_ExReleaseResourceLite
0x14005b87c  nop     dword ptr [rax+rax+00h]
0x14005b881  call    cs:__imp_KeLeaveCriticalRegion
0x14005b888  nop     dword ptr [rax+rax+00h]
0x14005b88d  mov     edi, [rbp+57h+var_60]
0x14005b890  mov     rax, [rbp+57h+SectionHandle]
0x14005b894  xor     ebx, ebx
0x14005b896  mov     [r12+10h], rax
0x14005b89b  mov     [r12+8], edi
0x14005b8a0  call    cs:__imp_KeLeaveCriticalRegion
0x14005b8a7  nop     dword ptr [rax+rax+00h]
0x14005b8ac  mov     rcx, [rbp+57h+Context]; Context
0x14005b8b0  test    rcx, rcx
0x14005b8b3  jnz     loc_14005BA82
0x14005b8b9  mov     rcx, rsi; Context
0x14005b8bc  call    cs:__imp_FltReleaseContext
0x14005b8c3  nop     dword ptr [rax+rax+00h]
0x14005b8c8  mov     rcx, r13; Object
0x14005b8cb  call    cs:__imp_ObfDereferenceObject
0x14005b8d2  nop     dword ptr [rax+rax+00h]
0x14005b8d7  lock xadd cs:ObTotalReferences, r14
0x14005b8e0  cmp     r14, 1
0x14005b8e4  js      loc_14005BA53
0x14005b8ea  mov     eax, ebx
0x14005b8ec  mov     r13, [rsp+0D0h+var_28]
0x14005b8f4  mov     rsi, [rsp+0D0h+arg_10]
0x14005b8fc  mov     r14, [rsp+0D0h+var_30]
0x14005b904  mov     rcx, [rbp+57h+var_40]
0x14005b908  xor     rcx, rsp; StackCookie
0x14005b90b  call    __security_check_cookie
0x14005b910  add     rsp, 0B0h
0x14005b917  pop     r15
0x14005b919  pop     r12
0x14005b91b  pop     rdi
0x14005b91c  pop     rbx
0x14005b91d  pop     rbp
0x14005b91e  retn
0x14005b920  mov     eax, [rcx+2Ch]
0x14005b923  test    al, 4
0x14005b925  jz      loc_14005B708
0x14005b92b  mov     r9, [rbp+57h+Context]
0x14005b92f  lea     r8, WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids
0x14005b936  mov     rcx, [rcx+18h]
0x14005b93a  mov     edx, 4Bh ; 'K'
0x14005b93f  call    WPP_SF_q
0x14005b944  jmp     loc_14005B708
0x14005b949  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b950  lea     r15, WPP_GLOBAL_Control
0x14005b957  cmp     rcx, r15
0x14005b95a  jnz     loc_14005BC40
0x14005b960  mov     edi, [rbp+57h+var_60]
0x14005b963  jmp     loc_14005B8A0
0x14005b968  mov     r8, [rbp+57h+Context]
0x14005b96c  mov     rdx, r13
0x14005b96f  mov     rcx, rsi
0x14005b972  call    MpSuppressFileAccessTimeUpdateIfNeeded
0x14005b977  and     dword ptr [rsi+30h], 0FFFDFFFFh
0x14005b97e  jmp     loc_14005B754
0x14005b983  mov     [rbp+57h+var_60], r9d
0x14005b987  mov     rax, cs:WPP_GLOBAL_Control
0x14005b98e  cmp     rax, r15
0x14005b991  jnz     loc_14005BAC8
0x14005b997  mov     edi, r9d
0x14005b99a  jmp     loc_14005B890
0x14005b99f  mov     [rsp+0D0h+Flags], r15d; Flags
0x14005b9a4  lea     r8, [r12+18h]; SectionFileSize
0x14005b9a9  mov     [rsp+0D0h+AllocationAttributes], 8000000h; AllocationAttributes
0x14005b9b1  lea     rdx, [rbp+57h+SectionObject]; SectionObject
0x14005b9b5  mov     [rsp+0D0h+SectionPageProtection], 2; SectionPageProtection
0x14005b9bd  lea     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x14005b9c1  mov     [rsp+0D0h+MaximumSize], r15; MaximumSize
0x14005b9c6  mov     r9, r13; FileObject
0x14005b9c9  mov     [rsp+0D0h+ObjectAttributes], r15; ObjectAttributes
0x14005b9ce  mov     dword ptr [rsp+0D0h+ReturnedContext], 5; DesiredAccess
0x14005b9d6  call    cs:__imp_FsRtlCreateSectionForDataScan
0x14005b9dd  nop     dword ptr [rax+rax+00h]
0x14005b9e2  mov     [rbp+57h+var_60], eax
0x14005b9e5  test    eax, eax
0x14005b9e7  js      loc_14005BB79
0x14005b9ed  lock inc cs:ObTotalReferences
0x14005b9f5  mov     ebx, eax
0x14005b9f7  mov     [rbp+57h+var_60], eax
0x14005b9fa  lea     r15, WPP_GLOBAL_Control
0x14005ba01  mov     rax, cs:WPP_GLOBAL_Control
0x14005ba08  cmp     rax, r15
0x14005ba0b  jz      loc_14005B7E3
0x14005ba11  mov     eax, [rax+2Ch]
0x14005ba14  mov     [rbp+57h+var_60], ebx
0x14005ba17  test    al, 4
0x14005ba19  jz      loc_14005B7E3
0x14005ba1f  lfence
0x14005ba22  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ba29  lea     rax, [r13+58h]
0x14005ba2d  mov     r9, [rbp+57h+SectionObject]
0x14005ba31  lea     r8, WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids
0x14005ba38  mov     edx, 50h ; 'P'
0x14005ba3d  mov     [rsp+0D0h+ReturnedContext], rax
0x14005ba42  mov     rcx, [rcx+18h]
0x14005ba46  call    WPP_SF_qZ
0x14005ba4b  mov     [rbp+57h+var_60], ebx
0x14005ba4e  jmp     loc_14005B7E3
0x14005ba53  mov     rax, cs:MpData
0x14005ba5a  mov     ecx, [rax+364h]
0x14005ba60  test    ecx, ecx
0x14005ba62  jns     loc_14005B8EA
0x14005ba68  call    cs:__imp_KdRefreshDebuggerNotPresent
0x14005ba6f  nop     dword ptr [rax+rax+00h]
0x14005ba74  test    al, al
0x14005ba76  jnz     loc_14005BB24
0x14005ba7c  int     3; Trap to Debugger
0x14005ba7d  jmp     loc_14005B8EA
0x14005ba82  mov     r10, cs:WPP_GLOBAL_Control
0x14005ba89  cmp     r10, r15
0x14005ba8c  jnz     short loc_14005BAF7
0x14005ba8e  call    cs:__imp_FltReleaseContext
0x14005ba95  nop     dword ptr [rax+rax+00h]
0x14005ba9a  jmp     loc_14005B8B9
0x14005ba9f  mov     eax, [rcx+2Ch]
0x14005baa2  test    al, 4
0x14005baa4  jz      loc_14005B754
0x14005baaa  mov     rcx, [rcx+18h]
0x14005baae  lea     r9, [r13+58h]
0x14005bab2  mov     edx, 4Ch ; 'L'
0x14005bab7  lea     r8, WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids
0x14005babe  call    WPP_SF_Z
  ... truncated ...
```
