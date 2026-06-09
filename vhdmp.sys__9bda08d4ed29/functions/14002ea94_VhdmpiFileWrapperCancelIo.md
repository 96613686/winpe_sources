# VhdmpiFileWrapperCancelIo

- ea: `0x14002ea94`
- end: `0x14002eebd`
- name: `VhdmpiFileWrapperCancelIo`
- size: `1065`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400d0684`

## callees

- `0x140014420`
- `0x1400169d0`
- `0x14001bc1c`
- `0x14001c088`
- `0x140023980`
- `0x14002e8b0`
- `0x14002ea94`
- `0x140036284`
- `0x1400ab2a0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14002ec0c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14002ec0c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14002eb73`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14002eb73`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14002eb1f`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14002eb1f`
- `ntoskrnl!KfRaiseIrql` at `0x14002eb47`
- `ntoskrnl!KfRaiseIrql` at `0x14002eb47`
- `ntoskrnl!KeLowerIrql` at `0x14002ec35`
- `ntoskrnl!KeLowerIrql` at `0x14002ec35`
- `ntoskrnl!IoCancelIrp` at `0x14002ed60`
- `ntoskrnl!IoCancelIrp` at `0x14002eda3`
- `ntoskrnl!IoCancelIrp` at `0x14002ed60`
- `ntoskrnl!IoCancelIrp` at `0x14002eda3`
- `ntoskrnl!IofCompleteRequest` at `0x14002ee7c`
- `ntoskrnl!IofCompleteRequest` at `0x14002ee7c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002ede5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002ede5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ee51`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ee51`

## pseudocode

```c
__int64 __fastcall VhdmpiFileWrapperCancelIo(__int64 a1)
{
  __int64 result; // rax
  __int64 v3; // r12
  int v4; // ecx
  int v5; // r8d
  ULONG MaximumProcessorCount; // r15d
  KIRQL v7; // al
  __int64 v8; // rsi
  KSPIN_LOCK *v9; // r13
  struct _VHD_IRP_TRACKING_CONTEXT *v10; // rbx
  struct _VHD_IRP_TRACKING_CONTEXT *v11; // r10
  struct _VHD_IRP_TRACKING_CONTEXT *v12; // r14
  _QWORD *v13; // r12
  struct _VHD_IRP_TRACKING_CONTEXT *v14; // r9
  struct _VHD_IRP_TRACKING_CONTEXT *v15; // r11
  struct _VHD_IRP_TRACKING_CONTEXT **v16; // rcx
  struct _VHD_IRP_TRACKING_CONTEXT *v17; // rcx
  int v18; // r8d
  int v19; // r8d
  int v20; // r10d
  struct _VHD_IRP_TRACKING_CONTEXT *i; // rbx
  __int64 v22; // rsi
  __int64 v23; // rbx
  __int64 v24; // rdi
  struct _VHD_IRP_TRACKING_CONTEXT *v25; // rsi
  struct _VHD_IRP_TRACKING_CONTEXT *v26; // rbx
  int *v27; // r15
  unsigned __int64 v28; // rdi
  KIRQL v29; // al
  KSPIN_LOCK *v30; // r9
  char *v31; // rdx
  char **v32; // r8
  struct _VHD_IRP_TRACKING_CONTEXT *v33; // rcx
  struct _VHD_IRP_TRACKING_CONTEXT *v34; // r14
  KIRQL v35; // dl
  int v36; // ebx
  int v37; // eax
  struct _VHD_IRP_TRACKING_CONTEXT *v38[2]; // [rsp+30h] [rbp-10h] BYREF
  KIRQL v39; // [rsp+80h] [rbp+40h]
  struct _VHD_FILE_WRAPPER *v40; // [rsp+88h] [rbp+48h] BYREF
  struct _VHD_SAFE_FILE_REFERENCE *v41; // [rsp+90h] [rbp+50h] BYREF

  result = *(unsigned int *)(a1 + 672);
  v40 = 0;
  v41 = 0;
  *(_OWORD *)v38 = 0;
  if ( !(_DWORD)result )
  {
    v3 = a1 + 568;
    VhdmpiAcquirePassiveLock(a1 + 568);
    _InterlockedExchange((volatile __int32 *)(a1 + 672), 1);
    if ( (Microsoft_Windows_VHDMPEnableBits & 1) != 0 )
      McTemplateK0zjq_EtwWriteTransfer(
        v4,
        (unsigned int)VhdIoCancellationStarted,
        v5,
        *(_QWORD *)(a1 + 48),
        a1 + 548,
        0,
        v38[0],
        v38[1]);
    MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
    v38[1] = (struct _VHD_IRP_TRACKING_CONTEXT *)v38;
    v38[0] = (struct _VHD_IRP_TRACKING_CONTEXT *)v38;
    v7 = KfRaiseIrql(2u);
    v8 = 0;
    v39 = v7;
    if ( MaximumProcessorCount )
    {
      do
      {
        KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)VhdPerProcData + 24 * v8);
        v9 = (KSPIN_LOCK *)((char *)VhdPerProcData + 192 * v8);
        v10 = (struct _VHD_IRP_TRACKING_CONTEXT *)(v9 + 1);
        v11 = (struct _VHD_IRP_TRACKING_CONTEXT *)v9[1];
        if ( *(struct _VHD_IRP_TRACKING_CONTEXT **)v10 != v10 )
        {
          do
          {
            v12 = v11;
            v13 = v11;
            VhdmpiIrpTrackingContextGetRelatedFile(v11, &v40, &v41);
            if ( v40 == (struct _VHD_FILE_WRAPPER *)a1 )
            {
              *((_DWORD *)v12 + 4) |= 0x80000000;
              if ( *((struct _VHD_IRP_TRACKING_CONTEXT **)v15 + 1) != v12
                || (v16 = (struct _VHD_IRP_TRACKING_CONTEXT **)*((_QWORD *)v12 + 1), *v16 != v12) )
              {
                __fastfail(3u);
              }
              *v16 = v15;
              *((_QWORD *)v15 + 1) = v16;
              v17 = v38[1];
              if ( *(struct _VHD_IRP_TRACKING_CONTEXT ***)v38[1] != v38 )
                __fastfail(3u);
              *((struct _VHD_IRP_TRACKING_CONTEXT **)v12 + 1) = v38[1];
              *v13 = v38;
              *(_QWORD *)v17 = v14;
              v38[1] = v14;
            }
          }
          while ( v15 != v10 );
        }
        KeReleaseSpinLockFromDpcLevel(v9);
        v8 = (unsigned int)(v8 + 1);
      }
      while ( (unsigned int)v8 < MaximumProcessorCount );
      v7 = v39;
      v3 = a1 + 568;
    }
    KeLowerIrql(v7);
    if ( (int)VhdmpiFileReferenceSetVirtualStorageBehavior(
                (struct _VHD_SAFE_FILE_REFERENCE *)(a1 + 176),
                VirtualStorageBehaviorCacheWriteBack|VirtualStorageBehaviorCacheWriteThrough) < 0
      && (unsigned int)dword_1400876D0 > 2
      && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x80000) )
    {
      TraceEvents("VhdmpiFileWrapperCancelIo", 0x21A8u, 2u, 0x80000u, "Log status 0x%08X", v18);
    }
    if ( (int)VhdmpiFileReferenceSetVirtualStorageBehavior(
                (struct _VHD_SAFE_FILE_REFERENCE *)(a1 + 280),
                VirtualStorageBehaviorCacheWriteBack|VirtualStorageBehaviorCacheWriteThrough) < 0
      && (unsigned int)dword_1400876D0 > 2
      && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x80000) )
    {
      TraceEvents("VhdmpiFileWrapperCancelIo", 0x21A9u, 2u, 0x80000u, "Log status 0x%08X", v19);
    }
    if ( (int)VhdmpiFileReferenceSetVirtualStorageBehavior(
                (struct _VHD_SAFE_FILE_REFERENCE *)(a1 + 384),
                VirtualStorageBehaviorCacheWriteBack|VirtualStorageBehaviorCacheWriteThrough) < 0
      && (unsigned int)dword_1400876D0 > 2
      && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x80000) )
    {
      TraceEvents("VhdmpiFileWrapperCancelIo", 0x21AAu, 2u, 0x80000u, "Log status 0x%08X", v20);
    }
    for ( i = v38[1];
          i != (struct _VHD_IRP_TRACKING_CONTEXT *)v38;
          i = (struct _VHD_IRP_TRACKING_CONTEXT *)*((_QWORD *)i + 1) )
    {
      IoCancelIrp((PIRP)((char *)i - (*((_WORD *)i + 9) & 0x7FFF)));
    }
    v22 = a1 + 680;
    VhdmpiAcquirePassiveLock(a1 + 680);
    v23 = *(_QWORD *)(a1 + 704);
    *(_BYTE *)(a1 + 712) = 0;
    v24 = a1 + 696;
    while ( v23 != v24 )
    {
      IoCancelIrp(*(PIRP *)(v23 + 16));
      v23 = *(_QWORD *)(v23 + 8);
    }
    VhdmpiReleasePassiveLock(v22);
    v25 = v38[0];
    while ( v25 != (struct _VHD_IRP_TRACKING_CONTEXT *)v38 )
    {
      v26 = *(struct _VHD_IRP_TRACKING_CONTEXT **)v25;
      v27 = (int *)((char *)v25 + 16);
      v28 = *((unsigned int *)v25 + 4);
      v29 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)VhdPerProcData + 24 * (unsigned __int16)v28);
      v30 = (KSPIN_LOCK *)VhdPerProcData;
      v31 = (char *)VhdPerProcData + 192 * (unsigned __int16)*((_DWORD *)v25 + 4) + 8;
      v32 = (char **)*((_QWORD *)v31 + 1);
      if ( *v32 != v31 )
        __fastfail(3u);
      v33 = v25;
      v34 = v25;
      v25 = v26;
      *(_QWORD *)v33 = v31;
      *((_QWORD *)v33 + 1) = v32;
      *v32 = (char *)v33;
      *((_QWORD *)v31 + 1) = v33;
      v35 = v29;
      v36 = *v27;
      v37 = *v27 & 0x7FFFFFFF;
      *v27 = v37;
      KeReleaseSpinLock(&v30[24 * (unsigned __int16)v37], v35);
      if ( v36 >= 0 )
      {
        VhdmpiCompleteTrackedIrp(v34);
        IofCompleteRequest((PIRP)((char *)v34 - ((v28 >> 16) & 0x7FFF)), 0);
      }
    }
    return VhdmpiReleasePassiveLock(v3);
  }
  return result;
}

```

## disassembly

```asm
0x14002ea94  mov     [rsp-38h+arg_18], rbx
0x14002ea99  push    rbp
0x14002ea9a  push    rsi
0x14002ea9b  push    rdi
0x14002ea9c  push    r12
0x14002ea9e  push    r13
0x14002eaa0  push    r14
0x14002eaa2  push    r15
0x14002eaa4  mov     rbp, rsp
0x14002eaa7  sub     rsp, 40h
0x14002eaab  mov     eax, [rcx+2A0h]
0x14002eab1  xorps   xmm0, xmm0
0x14002eab4  mov     [rbp+arg_8], 0
0x14002eabc  mov     rdi, rcx
0x14002eabf  mov     [rbp+arg_10], 0
0x14002eac7  movups  xmmword ptr [rbp+var_10], xmm0
0x14002eacb  test    eax, eax
0x14002eacd  jnz     loc_14002EE9D
0x14002ead3  lea     r12, [rcx+238h]
0x14002eada  mov     rcx, r12
0x14002eadd  call    VhdmpiAcquirePassiveLock
0x14002eae2  mov     eax, 1
0x14002eae7  xchg    eax, [rdi+2A0h]
0x14002eaed  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 1
0x14002eaf4  jz      short loc_14002EB1A
0x14002eaf6  mov     r9, [rdi+30h]
0x14002eafa  lea     rax, [rdi+224h]
0x14002eb01  mov     dword ptr [rsp+40h+var_18], 0
0x14002eb09  lea     rdx, VhdIoCancellationStarted
0x14002eb10  mov     [rsp+40h+var_20], rax
0x14002eb15  call    McTemplateK0zjq_EtwWriteTransfer
0x14002eb1a  mov     ecx, 0FFFFh; GroupNumber
0x14002eb1f  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x14002eb26  nop     dword ptr [rax+rax+00h]
0x14002eb2b  mov     r15d, eax
0x14002eb2e  mov     r14d, 2
0x14002eb34  lea     rax, [rbp+var_10]
0x14002eb38  mov     cl, r14b; NewIrql
0x14002eb3b  mov     [rbp+var_10+8], rax
0x14002eb3f  lea     rax, [rbp+var_10]
0x14002eb43  mov     [rbp+var_10], rax
0x14002eb47  call    cs:__imp_KfRaiseIrql
0x14002eb4e  nop     dword ptr [rax+rax+00h]
0x14002eb53  xor     esi, esi
0x14002eb55  mov     [rbp+arg_0], al
0x14002eb58  test    r15d, r15d
0x14002eb5b  jz      loc_14002EC33
0x14002eb61  mov     rcx, cs:VhdPerProcData
0x14002eb68  lea     rbx, [rsi+rsi*2]
0x14002eb6c  shl     rbx, 6
0x14002eb70  add     rcx, rbx; SpinLock
0x14002eb73  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14002eb7a  nop     dword ptr [rax+rax+00h]
0x14002eb7f  mov     r13, cs:VhdPerProcData
0x14002eb86  add     r13, rbx
0x14002eb89  lea     rbx, [r13+8]
0x14002eb8d  mov     r10, [rbx]
0x14002eb90  cmp     r10, rbx
0x14002eb93  jz      short loc_14002EC09
0x14002eb95  mov     r11, [r10]
0x14002eb98  lea     r8, [rbp+arg_10]; struct _VHD_SAFE_FILE_REFERENCE **
0x14002eb9c  mov     r14, r10
0x14002eb9f  lea     rdx, [rbp+arg_8]; struct _VHD_FILE_WRAPPER **
0x14002eba3  mov     rcx, r14; struct _VHD_IRP_TRACKING_CONTEXT *
0x14002eba6  mov     r12, r10
0x14002eba9  mov     r9, r10
0x14002ebac  mov     r10, r11
0x14002ebaf  call    ?VhdmpiIrpTrackingContextGetRelatedFile@@YAXPEAU_VHD_IRP_TRACKING_CONTEXT@@PEAPEAU_VHD_FILE_WRAPPER@@PEAPEAU_VHD_SAFE_FILE_REFERENCE@@@Z; VhdmpiIrpTrackingContextGetRelatedFile(_VHD_IRP_TRACKING_CONTEXT *,_VHD_FILE_WRAPPER * *,_VHD_SAFE_FILE_REFERENCE * *)
0x14002ebb4  cmp     [rbp+arg_8], rdi
0x14002ebb8  jnz     short loc_14002EC04
0x14002ebba  bts     dword ptr [r14+10h], 1Fh
0x14002ebc0  cmp     [r11+8], r14
0x14002ebc4  jnz     short loc_14002EBEA
0x14002ebc6  mov     rcx, [r14+8]
0x14002ebca  cmp     [rcx], r14
0x14002ebcd  jnz     short loc_14002EBEA
0x14002ebcf  mov     [rcx], r11
0x14002ebd2  lea     rdx, [rbp+var_10]
0x14002ebd6  mov     [r11+8], rcx
0x14002ebda  mov     rcx, [rbp+var_10+8]
0x14002ebde  cmp     [rcx], rdx
0x14002ebe1  jz      short loc_14002EBF1
0x14002ebe3  mov     ecx, 3
0x14002ebe8  int     29h; Win8: RtlFailFast(ecx)
0x14002ebea  mov     ecx, 3
0x14002ebef  int     29h; Win8: RtlFailFast(ecx)
0x14002ebf1  mov     [r14+8], rcx
0x14002ebf5  lea     rdx, [rbp+var_10]
0x14002ebf9  mov     [r12], rdx
0x14002ebfd  mov     [rcx], r9
0x14002ec00  mov     [rbp+var_10+8], r9
0x14002ec04  cmp     r11, rbx
0x14002ec07  jnz     short loc_14002EB95
0x14002ec09  mov     rcx, r13; SpinLock
0x14002ec0c  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14002ec13  nop     dword ptr [rax+rax+00h]
0x14002ec18  inc     esi
0x14002ec1a  cmp     esi, r15d
0x14002ec1d  jb      loc_14002EB61
0x14002ec23  mov     al, [rbp+arg_0]
0x14002ec26  lea     r12, [rdi+238h]
0x14002ec2d  mov     r14d, 2
0x14002ec33  mov     cl, al; NewIrql
0x14002ec35  call    cs:__imp_KeLowerIrql
0x14002ec3c  nop     dword ptr [rax+rax+00h]
0x14002ec41  lea     rcx, [rdi+0B0h]; struct _VHD_SAFE_FILE_REFERENCE *
0x14002ec48  mov     edx, 3; enum _VIRTUAL_STORAGE_BEHAVIOR_CODE
0x14002ec4d  call    ?VhdmpiFileReferenceSetVirtualStorageBehavior@@YAJAEAU_VHD_SAFE_FILE_REFERENCE@@W4_VIRTUAL_STORAGE_BEHAVIOR_CODE@@@Z; VhdmpiFileReferenceSetVirtualStorageBehavior(_VHD_SAFE_FILE_REFERENCE &,_VIRTUAL_STORAGE_BEHAVIOR_CODE)
0x14002ec52  lea     rsi, dword_1400876D0
0x14002ec59  mov     r8d, eax
0x14002ec5c  lea     r13, aLogStatus0x08x_3; "Log status 0x%08X"
0x14002ec63  mov     ebx, 80000h
0x14002ec68  lea     r15, aVhdmpifilewrap_1; "VhdmpiFileWrapperCancelIo"
0x14002ec6f  test    eax, eax
0x14002ec71  jns     short loc_14002ECA9
0x14002ec73  mov     ecx, cs:dword_1400876D0
0x14002ec79  cmp     ecx, r14d
0x14002ec7c  jbe     short loc_14002ECA9
0x14002ec7e  mov     edx, ebx
0x14002ec80  mov     rcx, rsi
0x14002ec83  call    _tlgKeywordOn
0x14002ec88  test    al, al
0x14002ec8a  jz      short loc_14002ECA9
0x14002ec8c  mov     dword ptr [rsp+40h+var_18], r8d; char
0x14002ec91  mov     edx, 21A8h; int
0x14002ec96  mov     r8d, r14d; int
0x14002ec99  mov     [rsp+40h+var_20], r13; char *
0x14002ec9e  mov     r9d, ebx; int
0x14002eca1  mov     rcx, r15; int
0x14002eca4  call    TraceEvents
0x14002eca9  lea     rcx, [rdi+118h]; struct _VHD_SAFE_FILE_REFERENCE *
0x14002ecb0  mov     edx, 3; enum _VIRTUAL_STORAGE_BEHAVIOR_CODE
0x14002ecb5  call    ?VhdmpiFileReferenceSetVirtualStorageBehavior@@YAJAEAU_VHD_SAFE_FILE_REFERENCE@@W4_VIRTUAL_STORAGE_BEHAVIOR_CODE@@@Z; VhdmpiFileReferenceSetVirtualStorageBehavior(_VHD_SAFE_FILE_REFERENCE &,_VIRTUAL_STORAGE_BEHAVIOR_CODE)
0x14002ecba  mov     r8d, eax
0x14002ecbd  test    eax, eax
0x14002ecbf  jns     short loc_14002ECF8
0x14002ecc1  mov     ecx, cs:dword_1400876D0
0x14002ecc7  cmp     ecx, r14d
0x14002ecca  jbe     short loc_14002ECF8
0x14002eccc  mov     rdx, rbx
0x14002eccf  mov     rcx, rsi
0x14002ecd2  call    _tlgKeywordOn
0x14002ecd7  test    al, al
0x14002ecd9  jz      short loc_14002ECF8
0x14002ecdb  mov     dword ptr [rsp+40h+var_18], r8d; char
0x14002ece0  mov     edx, 21A9h; int
0x14002ece5  mov     r8d, r14d; int
0x14002ece8  mov     [rsp+40h+var_20], r13; char *
0x14002eced  mov     r9d, ebx; int
0x14002ecf0  mov     rcx, r15; int
0x14002ecf3  call    TraceEvents
0x14002ecf8  lea     rcx, [rdi+180h]; struct _VHD_SAFE_FILE_REFERENCE *
0x14002ecff  mov     edx, 3; enum _VIRTUAL_STORAGE_BEHAVIOR_CODE
0x14002ed04  call    ?VhdmpiFileReferenceSetVirtualStorageBehavior@@YAJAEAU_VHD_SAFE_FILE_REFERENCE@@W4_VIRTUAL_STORAGE_BEHAVIOR_CODE@@@Z; VhdmpiFileReferenceSetVirtualStorageBehavior(_VHD_SAFE_FILE_REFERENCE &,_VIRTUAL_STORAGE_BEHAVIOR_CODE)
0x14002ed09  mov     r10d, eax
0x14002ed0c  test    eax, eax
0x14002ed0e  jns     short loc_14002ED47
0x14002ed10  mov     edx, cs:dword_1400876D0
0x14002ed16  cmp     edx, r14d
0x14002ed19  jbe     short loc_14002ED47
0x14002ed1b  mov     rdx, rbx
0x14002ed1e  mov     rcx, rsi
0x14002ed21  call    _tlgKeywordOn
0x14002ed26  test    al, al
0x14002ed28  jz      short loc_14002ED47
0x14002ed2a  mov     dword ptr [rsp+40h+var_18], r10d; char
0x14002ed2f  mov     edx, 21AAh; int
0x14002ed34  mov     r9d, ebx; int
0x14002ed37  mov     [rsp+40h+var_20], r13; char *
0x14002ed3c  mov     r8d, r14d; int
0x14002ed3f  mov     rcx, r15; int
0x14002ed42  call    TraceEvents
0x14002ed47  mov     rbx, [rbp+var_10+8]
0x14002ed4b  mov     r13d, 7FFFh
0x14002ed51  jmp     short loc_14002ED70
0x14002ed53  movzx   eax, word ptr [rbx+12h]
0x14002ed57  mov     rcx, rbx
0x14002ed5a  and     rax, r13
0x14002ed5d  sub     rcx, rax; Irp
0x14002ed60  call    cs:__imp_IoCancelIrp
0x14002ed67  nop     dword ptr [rax+rax+00h]
0x14002ed6c  mov     rbx, [rbx+8]
0x14002ed70  lea     rax, [rbp+var_10]
0x14002ed74  cmp     rbx, rax
0x14002ed77  jnz     short loc_14002ED53
0x14002ed79  lea     rsi, [rdi+2A8h]
0x14002ed80  mov     rcx, rsi
0x14002ed83  call    VhdmpiAcquirePassiveLock
0x14002ed88  mov     rbx, [rdi+2C0h]
0x14002ed8f  mov     byte ptr [rdi+2C8h], 0
0x14002ed96  add     rdi, 2B8h
0x14002ed9d  jmp     short loc_14002EDB3
0x14002ed9f  mov     rcx, [rbx+10h]; Irp
0x14002eda3  call    cs:__imp_IoCancelIrp
0x14002edaa  nop     dword ptr [rax+rax+00h]
0x14002edaf  mov     rbx, [rbx+8]
0x14002edb3  cmp     rbx, rdi
0x14002edb6  jnz     short loc_14002ED9F
0x14002edb8  mov     rcx, rsi
0x14002edbb  call    VhdmpiReleasePassiveLock
0x14002edc0  mov     rsi, [rbp+var_10]
0x14002edc4  jmp     loc_14002EE88
0x14002edc9  mov     rbx, [rsi]
0x14002edcc  lea     r15, [rsi+10h]
0x14002edd0  mov     edi, [r15]
0x14002edd3  movzx   eax, di
0x14002edd6  lea     rcx, [rax+rax*2]
0x14002edda  shl     rcx, 6
0x14002edde  add     rcx, cs:VhdPerProcData; SpinLock
0x14002ede5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002edec  nop     dword ptr [rax+rax+00h]
0x14002edf1  mov     ecx, [r15]
0x14002edf4  mov     r10b, al
0x14002edf7  mov     r9, cs:VhdPerProcData
0x14002edfe  movzx   edx, cx
0x14002ee01  lea     rcx, [rdx+rdx*2]
0x14002ee05  shl     rcx, 6
0x14002ee09  lea     rdx, [r9+8]
0x14002ee0d  add     rdx, rcx
0x14002ee10  mov     r8, [rdx+8]
0x14002ee14  cmp     [r8], rdx
0x14002ee17  jnz     loc_14002EEB6
0x14002ee1d  mov     rcx, rsi
0x14002ee20  mov     r14, rsi
0x14002ee23  mov     rsi, rbx
0x14002ee26  mov     [rcx], rdx
0x14002ee29  mov     [rcx+8], r8
0x14002ee2d  mov     [r8], rcx
0x14002ee30  mov     [rdx+8], rcx
0x14002ee34  mov     dl, r10b; NewIrql
0x14002ee37  mov     ebx, [r15]
0x14002ee3a  mov     eax, ebx
0x14002ee3c  btr     eax, 1Fh
0x14002ee40  mov     [r15], eax
0x14002ee43  movzx   eax, ax
0x14002ee46  lea     rcx, [rax+rax*2]
0x14002ee4a  shl     rcx, 6
0x14002ee4e  add     rcx, r9; SpinLock
0x14002ee51  call    cs:__imp_KeReleaseSpinLock
0x14002ee58  nop     dword ptr [rax+rax+00h]
0x14002ee5d  shr     ebx, 1Fh
0x14002ee60  xor     bl, 1
0x14002ee63  jz      short loc_14002EE88
0x14002ee65  mov     rcx, r14; struct _VHD_IRP_TRACKING_CONTEXT *
0x14002ee68  call    ?VhdmpiCompleteTrackedIrp@@YA_NPEAU_VHD_IRP_TRACKING_CONTEXT@@@Z; VhdmpiCompleteTrackedIrp(_VHD_IRP_TRACKING_CONTEXT *)
0x14002ee6d  shr     rdi, 10h
0x14002ee71  xor     edx, edx; PriorityBoost
0x14002ee73  and     rdi, r13
0x14002ee76  sub     r14, rdi
0x14002ee79  mov     rcx, r14; Irp
0x14002ee7c  call    cs:__imp_IofCompleteRequest
0x14002ee83  nop     dword ptr [rax+rax+00h]
0x14002ee88  lea     rax, [rbp+var_10]
0x14002ee8c  cmp     rsi, rax
0x14002ee8f  jnz     loc_14002EDC9
0x14002ee95  mov     rcx, r12
0x14002ee98  call    VhdmpiReleasePassiveLock
0x14002ee9d  mov     rbx, [rsp+40h+arg_18]
0x14002eea5  add     rsp, 40h
0x14002eea9  pop     r15
0x14002eeab  pop     r14
0x14002eead  pop     r13
0x14002eeaf  pop     r12
0x14002eeb1  pop     rdi
0x14002eeb2  pop     rsi
0x14002eeb3  pop     rbp
0x14002eeb4  retn
0x14002eeb6  mov     ecx, 3
0x14002eebb  int     29h; Win8: RtlFailFast(ecx)
```
