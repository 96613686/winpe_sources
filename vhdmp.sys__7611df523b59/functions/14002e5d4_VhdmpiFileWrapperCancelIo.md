# VhdmpiFileWrapperCancelIo

- ea: `0x14002e5d4`
- end: `0x14002e9fd`
- name: `VhdmpiFileWrapperCancelIo`
- size: `1065`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400d06f4`

## callees

- `0x140013f80`
- `0x140016530`
- `0x14001b7fc`
- `0x14001bc68`
- `0x140023560`
- `0x14002e3f0`
- `0x14002e5d4`
- `0x140035e94`
- `0x1400ab2a0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14002e74c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14002e74c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14002e6b3`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14002e6b3`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14002e65f`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14002e65f`
- `ntoskrnl!KfRaiseIrql` at `0x14002e687`
- `ntoskrnl!KfRaiseIrql` at `0x14002e687`
- `ntoskrnl!KeLowerIrql` at `0x14002e775`
- `ntoskrnl!KeLowerIrql` at `0x14002e775`
- `ntoskrnl!IoCancelIrp` at `0x14002e8a0`
- `ntoskrnl!IoCancelIrp` at `0x14002e8e3`
- `ntoskrnl!IoCancelIrp` at `0x14002e8a0`
- `ntoskrnl!IoCancelIrp` at `0x14002e8e3`
- `ntoskrnl!IofCompleteRequest` at `0x14002e9bc`
- `ntoskrnl!IofCompleteRequest` at `0x14002e9bc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002e925`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002e925`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002e991`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002e991`

## pseudocode

```c
__int64 __fastcall VhdmpiFileWrapperCancelIo(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  __int64 v5; // r12
  int v6; // ecx
  int v7; // r8d
  ULONG MaximumProcessorCount; // r15d
  KIRQL v9; // al
  __int64 v10; // rsi
  KSPIN_LOCK *v11; // r13
  struct _VHD_IRP_TRACKING_CONTEXT *v12; // rbx
  struct _VHD_IRP_TRACKING_CONTEXT *v13; // r10
  struct _VHD_IRP_TRACKING_CONTEXT *v14; // r14
  _QWORD *v15; // r12
  struct _VHD_IRP_TRACKING_CONTEXT *v16; // r9
  struct _VHD_IRP_TRACKING_CONTEXT *v17; // r11
  struct _VHD_IRP_TRACKING_CONTEXT **v18; // rcx
  struct _VHD_IRP_TRACKING_CONTEXT *v19; // rcx
  int v20; // r8d
  int v21; // r8d
  __int64 v22; // rdx
  __int64 v23; // r8
  int v24; // r10d
  struct _VHD_IRP_TRACKING_CONTEXT *i; // rbx
  __int64 v26; // rsi
  __int64 v27; // rbx
  __int64 v28; // rdi
  struct _VHD_IRP_TRACKING_CONTEXT *v29; // rsi
  struct _VHD_IRP_TRACKING_CONTEXT *v30; // rbx
  int *v31; // r15
  unsigned __int64 v32; // rdi
  KIRQL v33; // al
  KSPIN_LOCK *v34; // r9
  char *v35; // rdx
  char **v36; // r8
  struct _VHD_IRP_TRACKING_CONTEXT *v37; // rcx
  struct _VHD_IRP_TRACKING_CONTEXT *v38; // r14
  KIRQL v39; // dl
  int v40; // ebx
  int v41; // eax
  struct _VHD_IRP_TRACKING_CONTEXT *v42[2]; // [rsp+30h] [rbp-10h] BYREF
  KIRQL v43; // [rsp+80h] [rbp+40h]
  struct _VHD_FILE_WRAPPER *v44; // [rsp+88h] [rbp+48h] BYREF
  struct _VHD_SAFE_FILE_REFERENCE *v45; // [rsp+90h] [rbp+50h] BYREF

  result = *(unsigned int *)(a1 + 672);
  v44 = 0;
  v45 = 0;
  *(_OWORD *)v42 = 0;
  if ( !(_DWORD)result )
  {
    v5 = a1 + 568;
    VhdmpiAcquirePassiveLock(a1 + 568, a2, a3);
    _InterlockedExchange((volatile __int32 *)(a1 + 672), 1);
    if ( (Microsoft_Windows_VHDMPEnableBits & 1) != 0 )
      McTemplateK0zjq_EtwWriteTransfer(
        v6,
        (unsigned int)VhdIoCancellationStarted,
        v7,
        *(_QWORD *)(a1 + 48),
        a1 + 548,
        0,
        v42[0],
        v42[1]);
    MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
    v42[1] = (struct _VHD_IRP_TRACKING_CONTEXT *)v42;
    v42[0] = (struct _VHD_IRP_TRACKING_CONTEXT *)v42;
    v9 = KfRaiseIrql(2u);
    v10 = 0;
    v43 = v9;
    if ( MaximumProcessorCount )
    {
      do
      {
        KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)VhdPerProcData + 24 * v10);
        v11 = (KSPIN_LOCK *)((char *)VhdPerProcData + 192 * v10);
        v12 = (struct _VHD_IRP_TRACKING_CONTEXT *)(v11 + 1);
        v13 = (struct _VHD_IRP_TRACKING_CONTEXT *)v11[1];
        if ( *(struct _VHD_IRP_TRACKING_CONTEXT **)v12 != v12 )
        {
          do
          {
            v14 = v13;
            v15 = v13;
            VhdmpiIrpTrackingContextGetRelatedFile(v13, &v44, &v45);
            if ( v44 == (struct _VHD_FILE_WRAPPER *)a1 )
            {
              *((_DWORD *)v14 + 4) |= 0x80000000;
              if ( *((struct _VHD_IRP_TRACKING_CONTEXT **)v17 + 1) != v14
                || (v18 = (struct _VHD_IRP_TRACKING_CONTEXT **)*((_QWORD *)v14 + 1), *v18 != v14) )
              {
                __fastfail(3u);
              }
              *v18 = v17;
              *((_QWORD *)v17 + 1) = v18;
              v19 = v42[1];
              if ( *(struct _VHD_IRP_TRACKING_CONTEXT ***)v42[1] != v42 )
                __fastfail(3u);
              *((struct _VHD_IRP_TRACKING_CONTEXT **)v14 + 1) = v42[1];
              *v15 = v42;
              *(_QWORD *)v19 = v16;
              v42[1] = v16;
            }
          }
          while ( v17 != v12 );
        }
        KeReleaseSpinLockFromDpcLevel(v11);
        v10 = (unsigned int)(v10 + 1);
      }
      while ( (unsigned int)v10 < MaximumProcessorCount );
      v9 = v43;
      v5 = a1 + 568;
    }
    KeLowerIrql(v9);
    if ( (int)VhdmpiFileReferenceSetVirtualStorageBehavior(
                (struct _VHD_SAFE_FILE_REFERENCE *)(a1 + 176),
                VirtualStorageBehaviorCacheWriteBack|VirtualStorageBehaviorCacheWriteThrough) < 0
      && (unsigned int)dword_140087708 > 2
      && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
    {
      TraceEvents("VhdmpiFileWrapperCancelIo", 0x21A8u, 2u, 0x80000u, "Log status 0x%08X", v20);
    }
    if ( (int)VhdmpiFileReferenceSetVirtualStorageBehavior(
                (struct _VHD_SAFE_FILE_REFERENCE *)(a1 + 280),
                VirtualStorageBehaviorCacheWriteBack|VirtualStorageBehaviorCacheWriteThrough) < 0
      && (unsigned int)dword_140087708 > 2
      && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
    {
      TraceEvents("VhdmpiFileWrapperCancelIo", 0x21A9u, 2u, 0x80000u, "Log status 0x%08X", v21);
    }
    if ( (int)VhdmpiFileReferenceSetVirtualStorageBehavior(
                (struct _VHD_SAFE_FILE_REFERENCE *)(a1 + 384),
                VirtualStorageBehaviorCacheWriteBack|VirtualStorageBehaviorCacheWriteThrough) < 0 )
    {
      v22 = (unsigned int)dword_140087708;
      if ( (unsigned int)dword_140087708 > 2 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
          TraceEvents("VhdmpiFileWrapperCancelIo", 0x21AAu, 2u, 0x80000u, "Log status 0x%08X", v24);
      }
    }
    for ( i = v42[1];
          i != (struct _VHD_IRP_TRACKING_CONTEXT *)v42;
          i = (struct _VHD_IRP_TRACKING_CONTEXT *)*((_QWORD *)i + 1) )
    {
      IoCancelIrp((PIRP)((char *)i - (*((_WORD *)i + 9) & 0x7FFF)));
    }
    v26 = a1 + 680;
    VhdmpiAcquirePassiveLock(a1 + 680, v22, v23);
    v27 = *(_QWORD *)(a1 + 704);
    *(_BYTE *)(a1 + 712) = 0;
    v28 = a1 + 696;
    while ( v27 != v28 )
    {
      IoCancelIrp(*(PIRP *)(v27 + 16));
      v27 = *(_QWORD *)(v27 + 8);
    }
    VhdmpiReleasePassiveLock(v26);
    v29 = v42[0];
    while ( v29 != (struct _VHD_IRP_TRACKING_CONTEXT *)v42 )
    {
      v30 = *(struct _VHD_IRP_TRACKING_CONTEXT **)v29;
      v31 = (int *)((char *)v29 + 16);
      v32 = *((unsigned int *)v29 + 4);
      v33 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)VhdPerProcData + 24 * (unsigned __int16)v32);
      v34 = (KSPIN_LOCK *)VhdPerProcData;
      v35 = (char *)VhdPerProcData + 192 * (unsigned __int16)*((_DWORD *)v29 + 4) + 8;
      v36 = (char **)*((_QWORD *)v35 + 1);
      if ( *v36 != v35 )
        __fastfail(3u);
      v37 = v29;
      v38 = v29;
      v29 = v30;
      *(_QWORD *)v37 = v35;
      *((_QWORD *)v37 + 1) = v36;
      *v36 = (char *)v37;
      *((_QWORD *)v35 + 1) = v37;
      v39 = v33;
      v40 = *v31;
      v41 = *v31 & 0x7FFFFFFF;
      *v31 = v41;
      KeReleaseSpinLock(&v34[24 * (unsigned __int16)v41], v39);
      if ( v40 >= 0 )
      {
        VhdmpiCompleteTrackedIrp(v38);
        IofCompleteRequest((PIRP)((char *)v38 - ((v32 >> 16) & 0x7FFF)), 0);
      }
    }
    return VhdmpiReleasePassiveLock(v5);
  }
  return result;
}

```

## disassembly

```asm
0x14002e5d4  mov     [rsp-38h+arg_18], rbx
0x14002e5d9  push    rbp
0x14002e5da  push    rsi
0x14002e5db  push    rdi
0x14002e5dc  push    r12
0x14002e5de  push    r13
0x14002e5e0  push    r14
0x14002e5e2  push    r15
0x14002e5e4  mov     rbp, rsp
0x14002e5e7  sub     rsp, 40h
0x14002e5eb  mov     eax, [rcx+2A0h]
0x14002e5f1  xorps   xmm0, xmm0
0x14002e5f4  mov     [rbp+arg_8], 0
0x14002e5fc  mov     rdi, rcx
0x14002e5ff  mov     [rbp+arg_10], 0
0x14002e607  movups  xmmword ptr [rbp+var_10], xmm0
0x14002e60b  test    eax, eax
0x14002e60d  jnz     loc_14002E9DD
0x14002e613  lea     r12, [rcx+238h]
0x14002e61a  mov     rcx, r12
0x14002e61d  call    VhdmpiAcquirePassiveLock
0x14002e622  mov     eax, 1
0x14002e627  xchg    eax, [rdi+2A0h]
0x14002e62d  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 1
0x14002e634  jz      short loc_14002E65A
0x14002e636  mov     r9, [rdi+30h]
0x14002e63a  lea     rax, [rdi+224h]
0x14002e641  mov     dword ptr [rsp+40h+var_18], 0
0x14002e649  lea     rdx, VhdIoCancellationStarted
0x14002e650  mov     [rsp+40h+var_20], rax
0x14002e655  call    McTemplateK0zjq_EtwWriteTransfer
0x14002e65a  mov     ecx, 0FFFFh; GroupNumber
0x14002e65f  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x14002e666  nop     dword ptr [rax+rax+00h]
0x14002e66b  mov     r15d, eax
0x14002e66e  mov     r14d, 2
0x14002e674  lea     rax, [rbp+var_10]
0x14002e678  mov     cl, r14b; NewIrql
0x14002e67b  mov     [rbp+var_10+8], rax
0x14002e67f  lea     rax, [rbp+var_10]
0x14002e683  mov     [rbp+var_10], rax
0x14002e687  call    cs:__imp_KfRaiseIrql
0x14002e68e  nop     dword ptr [rax+rax+00h]
0x14002e693  xor     esi, esi
0x14002e695  mov     [rbp+arg_0], al
0x14002e698  test    r15d, r15d
0x14002e69b  jz      loc_14002E773
0x14002e6a1  mov     rcx, cs:VhdPerProcData
0x14002e6a8  lea     rbx, [rsi+rsi*2]
0x14002e6ac  shl     rbx, 6
0x14002e6b0  add     rcx, rbx; SpinLock
0x14002e6b3  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14002e6ba  nop     dword ptr [rax+rax+00h]
0x14002e6bf  mov     r13, cs:VhdPerProcData
0x14002e6c6  add     r13, rbx
0x14002e6c9  lea     rbx, [r13+8]
0x14002e6cd  mov     r10, [rbx]
0x14002e6d0  cmp     r10, rbx
0x14002e6d3  jz      short loc_14002E749
0x14002e6d5  mov     r11, [r10]
0x14002e6d8  lea     r8, [rbp+arg_10]; struct _VHD_SAFE_FILE_REFERENCE **
0x14002e6dc  mov     r14, r10
0x14002e6df  lea     rdx, [rbp+arg_8]; struct _VHD_FILE_WRAPPER **
0x14002e6e3  mov     rcx, r14; struct _VHD_IRP_TRACKING_CONTEXT *
0x14002e6e6  mov     r12, r10
0x14002e6e9  mov     r9, r10
0x14002e6ec  mov     r10, r11
0x14002e6ef  call    ?VhdmpiIrpTrackingContextGetRelatedFile@@YAXPEAU_VHD_IRP_TRACKING_CONTEXT@@PEAPEAU_VHD_FILE_WRAPPER@@PEAPEAU_VHD_SAFE_FILE_REFERENCE@@@Z; VhdmpiIrpTrackingContextGetRelatedFile(_VHD_IRP_TRACKING_CONTEXT *,_VHD_FILE_WRAPPER * *,_VHD_SAFE_FILE_REFERENCE * *)
0x14002e6f4  cmp     [rbp+arg_8], rdi
0x14002e6f8  jnz     short loc_14002E744
0x14002e6fa  bts     dword ptr [r14+10h], 1Fh
0x14002e700  cmp     [r11+8], r14
0x14002e704  jnz     short loc_14002E72A
0x14002e706  mov     rcx, [r14+8]
0x14002e70a  cmp     [rcx], r14
0x14002e70d  jnz     short loc_14002E72A
0x14002e70f  mov     [rcx], r11
0x14002e712  lea     rdx, [rbp+var_10]
0x14002e716  mov     [r11+8], rcx
0x14002e71a  mov     rcx, [rbp+var_10+8]
0x14002e71e  cmp     [rcx], rdx
0x14002e721  jz      short loc_14002E731
0x14002e723  mov     ecx, 3
0x14002e728  int     29h; Win8: RtlFailFast(ecx)
0x14002e72a  mov     ecx, 3
0x14002e72f  int     29h; Win8: RtlFailFast(ecx)
0x14002e731  mov     [r14+8], rcx
0x14002e735  lea     rdx, [rbp+var_10]
0x14002e739  mov     [r12], rdx
0x14002e73d  mov     [rcx], r9
0x14002e740  mov     [rbp+var_10+8], r9
0x14002e744  cmp     r11, rbx
0x14002e747  jnz     short loc_14002E6D5
0x14002e749  mov     rcx, r13; SpinLock
0x14002e74c  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14002e753  nop     dword ptr [rax+rax+00h]
0x14002e758  inc     esi
0x14002e75a  cmp     esi, r15d
0x14002e75d  jb      loc_14002E6A1
0x14002e763  mov     al, [rbp+arg_0]
0x14002e766  lea     r12, [rdi+238h]
0x14002e76d  mov     r14d, 2
0x14002e773  mov     cl, al; NewIrql
0x14002e775  call    cs:__imp_KeLowerIrql
0x14002e77c  nop     dword ptr [rax+rax+00h]
0x14002e781  lea     rcx, [rdi+0B0h]; struct _VHD_SAFE_FILE_REFERENCE *
0x14002e788  mov     edx, 3; enum _VIRTUAL_STORAGE_BEHAVIOR_CODE
0x14002e78d  call    ?VhdmpiFileReferenceSetVirtualStorageBehavior@@YAJAEAU_VHD_SAFE_FILE_REFERENCE@@W4_VIRTUAL_STORAGE_BEHAVIOR_CODE@@@Z; VhdmpiFileReferenceSetVirtualStorageBehavior(_VHD_SAFE_FILE_REFERENCE &,_VIRTUAL_STORAGE_BEHAVIOR_CODE)
0x14002e792  lea     rsi, dword_140087708
0x14002e799  mov     r8d, eax
0x14002e79c  lea     r13, aLogStatus0x08x_3; "Log status 0x%08X"
0x14002e7a3  mov     ebx, 80000h
0x14002e7a8  lea     r15, aVhdmpifilewrap_1; "VhdmpiFileWrapperCancelIo"
0x14002e7af  test    eax, eax
0x14002e7b1  jns     short loc_14002E7E9
0x14002e7b3  mov     ecx, cs:dword_140087708
0x14002e7b9  cmp     ecx, r14d
0x14002e7bc  jbe     short loc_14002E7E9
0x14002e7be  mov     edx, ebx
0x14002e7c0  mov     rcx, rsi
0x14002e7c3  call    _tlgKeywordOn
0x14002e7c8  test    al, al
0x14002e7ca  jz      short loc_14002E7E9
0x14002e7cc  mov     dword ptr [rsp+40h+var_18], r8d; char
0x14002e7d1  mov     edx, 21A8h; int
0x14002e7d6  mov     r8d, r14d; int
0x14002e7d9  mov     [rsp+40h+var_20], r13; char *
0x14002e7de  mov     r9d, ebx; int
0x14002e7e1  mov     rcx, r15; int
0x14002e7e4  call    TraceEvents
0x14002e7e9  lea     rcx, [rdi+118h]; struct _VHD_SAFE_FILE_REFERENCE *
0x14002e7f0  mov     edx, 3; enum _VIRTUAL_STORAGE_BEHAVIOR_CODE
0x14002e7f5  call    ?VhdmpiFileReferenceSetVirtualStorageBehavior@@YAJAEAU_VHD_SAFE_FILE_REFERENCE@@W4_VIRTUAL_STORAGE_BEHAVIOR_CODE@@@Z; VhdmpiFileReferenceSetVirtualStorageBehavior(_VHD_SAFE_FILE_REFERENCE &,_VIRTUAL_STORAGE_BEHAVIOR_CODE)
0x14002e7fa  mov     r8d, eax
0x14002e7fd  test    eax, eax
0x14002e7ff  jns     short loc_14002E838
0x14002e801  mov     ecx, cs:dword_140087708
0x14002e807  cmp     ecx, r14d
0x14002e80a  jbe     short loc_14002E838
0x14002e80c  mov     rdx, rbx
0x14002e80f  mov     rcx, rsi
0x14002e812  call    _tlgKeywordOn
0x14002e817  test    al, al
0x14002e819  jz      short loc_14002E838
0x14002e81b  mov     dword ptr [rsp+40h+var_18], r8d; char
0x14002e820  mov     edx, 21A9h; int
0x14002e825  mov     r8d, r14d; int
0x14002e828  mov     [rsp+40h+var_20], r13; char *
0x14002e82d  mov     r9d, ebx; int
0x14002e830  mov     rcx, r15; int
0x14002e833  call    TraceEvents
0x14002e838  lea     rcx, [rdi+180h]; struct _VHD_SAFE_FILE_REFERENCE *
0x14002e83f  mov     edx, 3; enum _VIRTUAL_STORAGE_BEHAVIOR_CODE
0x14002e844  call    ?VhdmpiFileReferenceSetVirtualStorageBehavior@@YAJAEAU_VHD_SAFE_FILE_REFERENCE@@W4_VIRTUAL_STORAGE_BEHAVIOR_CODE@@@Z; VhdmpiFileReferenceSetVirtualStorageBehavior(_VHD_SAFE_FILE_REFERENCE &,_VIRTUAL_STORAGE_BEHAVIOR_CODE)
0x14002e849  mov     r10d, eax
0x14002e84c  test    eax, eax
0x14002e84e  jns     short loc_14002E887
0x14002e850  mov     edx, cs:dword_140087708
0x14002e856  cmp     edx, r14d
0x14002e859  jbe     short loc_14002E887
0x14002e85b  mov     rdx, rbx
0x14002e85e  mov     rcx, rsi
0x14002e861  call    _tlgKeywordOn
0x14002e866  test    al, al
0x14002e868  jz      short loc_14002E887
0x14002e86a  mov     dword ptr [rsp+40h+var_18], r10d; char
0x14002e86f  mov     edx, 21AAh; int
0x14002e874  mov     r9d, ebx; int
0x14002e877  mov     [rsp+40h+var_20], r13; char *
0x14002e87c  mov     r8d, r14d; int
0x14002e87f  mov     rcx, r15; int
0x14002e882  call    TraceEvents
0x14002e887  mov     rbx, [rbp+var_10+8]
0x14002e88b  mov     r13d, 7FFFh
0x14002e891  jmp     short loc_14002E8B0
0x14002e893  movzx   eax, word ptr [rbx+12h]
0x14002e897  mov     rcx, rbx
0x14002e89a  and     rax, r13
0x14002e89d  sub     rcx, rax; Irp
0x14002e8a0  call    cs:__imp_IoCancelIrp
0x14002e8a7  nop     dword ptr [rax+rax+00h]
0x14002e8ac  mov     rbx, [rbx+8]
0x14002e8b0  lea     rax, [rbp+var_10]
0x14002e8b4  cmp     rbx, rax
0x14002e8b7  jnz     short loc_14002E893
0x14002e8b9  lea     rsi, [rdi+2A8h]
0x14002e8c0  mov     rcx, rsi
0x14002e8c3  call    VhdmpiAcquirePassiveLock
0x14002e8c8  mov     rbx, [rdi+2C0h]
0x14002e8cf  mov     byte ptr [rdi+2C8h], 0
0x14002e8d6  add     rdi, 2B8h
0x14002e8dd  jmp     short loc_14002E8F3
0x14002e8df  mov     rcx, [rbx+10h]; Irp
0x14002e8e3  call    cs:__imp_IoCancelIrp
0x14002e8ea  nop     dword ptr [rax+rax+00h]
0x14002e8ef  mov     rbx, [rbx+8]
0x14002e8f3  cmp     rbx, rdi
0x14002e8f6  jnz     short loc_14002E8DF
0x14002e8f8  mov     rcx, rsi
0x14002e8fb  call    VhdmpiReleasePassiveLock
0x14002e900  mov     rsi, [rbp+var_10]
0x14002e904  jmp     loc_14002E9C8
0x14002e909  mov     rbx, [rsi]
0x14002e90c  lea     r15, [rsi+10h]
0x14002e910  mov     edi, [r15]
0x14002e913  movzx   eax, di
0x14002e916  lea     rcx, [rax+rax*2]
0x14002e91a  shl     rcx, 6
0x14002e91e  add     rcx, cs:VhdPerProcData; SpinLock
0x14002e925  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002e92c  nop     dword ptr [rax+rax+00h]
0x14002e931  mov     ecx, [r15]
0x14002e934  mov     r10b, al
0x14002e937  mov     r9, cs:VhdPerProcData
0x14002e93e  movzx   edx, cx
0x14002e941  lea     rcx, [rdx+rdx*2]
0x14002e945  shl     rcx, 6
0x14002e949  lea     rdx, [r9+8]
0x14002e94d  add     rdx, rcx
0x14002e950  mov     r8, [rdx+8]
0x14002e954  cmp     [r8], rdx
0x14002e957  jnz     loc_14002E9F6
0x14002e95d  mov     rcx, rsi
0x14002e960  mov     r14, rsi
0x14002e963  mov     rsi, rbx
0x14002e966  mov     [rcx], rdx
0x14002e969  mov     [rcx+8], r8
0x14002e96d  mov     [r8], rcx
0x14002e970  mov     [rdx+8], rcx
0x14002e974  mov     dl, r10b; NewIrql
0x14002e977  mov     ebx, [r15]
0x14002e97a  mov     eax, ebx
0x14002e97c  btr     eax, 1Fh
0x14002e980  mov     [r15], eax
0x14002e983  movzx   eax, ax
0x14002e986  lea     rcx, [rax+rax*2]
0x14002e98a  shl     rcx, 6
0x14002e98e  add     rcx, r9; SpinLock
0x14002e991  call    cs:__imp_KeReleaseSpinLock
0x14002e998  nop     dword ptr [rax+rax+00h]
0x14002e99d  shr     ebx, 1Fh
0x14002e9a0  xor     bl, 1
0x14002e9a3  jz      short loc_14002E9C8
0x14002e9a5  mov     rcx, r14; struct _VHD_IRP_TRACKING_CONTEXT *
0x14002e9a8  call    ?VhdmpiCompleteTrackedIrp@@YA_NPEAU_VHD_IRP_TRACKING_CONTEXT@@@Z; VhdmpiCompleteTrackedIrp(_VHD_IRP_TRACKING_CONTEXT *)
0x14002e9ad  shr     rdi, 10h
0x14002e9b1  xor     edx, edx; PriorityBoost
0x14002e9b3  and     rdi, r13
0x14002e9b6  sub     r14, rdi
0x14002e9b9  mov     rcx, r14; Irp
0x14002e9bc  call    cs:__imp_IofCompleteRequest
0x14002e9c3  nop     dword ptr [rax+rax+00h]
0x14002e9c8  lea     rax, [rbp+var_10]
0x14002e9cc  cmp     rsi, rax
0x14002e9cf  jnz     loc_14002E909
0x14002e9d5  mov     rcx, r12
0x14002e9d8  call    VhdmpiReleasePassiveLock
0x14002e9dd  mov     rbx, [rsp+40h+arg_18]
0x14002e9e5  add     rsp, 40h
0x14002e9e9  pop     r15
0x14002e9eb  pop     r14
0x14002e9ed  pop     r13
0x14002e9ef  pop     r12
0x14002e9f1  pop     rdi
0x14002e9f2  pop     rsi
0x14002e9f3  pop     rbp
0x14002e9f4  retn
0x14002e9f6  mov     ecx, 3
0x14002e9fb  int     29h; Win8: RtlFailFast(ecx)
```
