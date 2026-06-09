# VmsCdpEnumNics

- ea: `0x14005407c`
- end: `0x14005463d`
- name: `VmsCdpEnumNics`
- size: `1473`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x14007b6a0`

## callees

- `0x14000accc`
- `0x140037714`
- `0x14003833c`
- `0x140038404`
- `0x140038574`
- `0x14003a450`
- `0x14003ae48`
- `0x140040c40`
- `0x14004f5d8`
- `0x14005407c`
- `0x140054644`
- `0x140054a20`
- `0x140054da0`
- `0x14008aa0c`
- `0x1400b6354`
- `0x1400c0a78`
- `0x1401bc040`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400541d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400541d3`
- `ntoskrnl!ExAllocatePool2` at `0x14005424f`
- `ntoskrnl!ExAllocatePool2` at `0x14005424f`
- `NDIS!NdisAcquireRWLockRead` at `0x14005414c`
- `NDIS!NdisAcquireRWLockRead` at `0x14005433c`
- `NDIS!NdisAcquireRWLockRead` at `0x14005414c`
- `NDIS!NdisAcquireRWLockRead` at `0x14005433c`
- `NDIS!NdisReleaseRWLock` at `0x1400541bd`
- `NDIS!NdisReleaseRWLock` at `0x14005439e`
- `NDIS!NdisReleaseRWLock` at `0x14005458c`
- `NDIS!NdisReleaseRWLock` at `0x1400541bd`
- `NDIS!NdisReleaseRWLock` at `0x14005439e`
- `NDIS!NdisReleaseRWLock` at `0x14005458c`

## pseudocode

```c
__int64 __fastcall VmsCdpEnumNics(__int64 a1, __int64 a2, _QWORD *a3)
{
  char *v4; // r13
  int v5; // eax
  int v6; // edx
  __int64 v7; // r14
  int v8; // r15d
  unsigned int NicCountUnsafe; // eax
  __int64 v10; // rsi
  int v11; // eax
  int v12; // edx
  int v13; // edx
  unsigned int v14; // ebx
  int v15; // edx
  __int64 v16; // r12
  int v17; // eax
  int v18; // eax
  int v19; // edx
  __int64 v20; // rdx
  char v21; // al
  unsigned int v22; // eax
  int v23; // eax
  unsigned int v25; // [rsp+B8h] [rbp+7h] BYREF
  unsigned int v26; // [rsp+BCh] [rbp+Bh] BYREF
  __int64 Pool2; // [rsp+C0h] [rbp+Fh] BYREF
  __int64 v28; // [rsp+C8h] [rbp+17h] BYREF
  __int64 v29[7]; // [rsp+D0h] [rbp+1Fh] BYREF
  __int64 v30; // [rsp+118h] [rbp+67h] BYREF
  __int64 LockState; // [rsp+120h] [rbp+6Fh] BYREF
  struct _LOCK_STATE_EX v32; // [rsp+130h] [rbp+7Fh] BYREF

  LockState = a2;
  v30 = a1;
  v28 = 0;
  LOWORD(LockState) = 0;
  BYTE2(LockState) = 0;
  *(_WORD *)&v32.OldIrql = 0;
  v32.Flags = 0;
  VmsWppTraceApi(
    (unsigned int)&v30,
    (unsigned int)"VmsCdpEnumNics",
    (unsigned int)"onecore\\vm\\dv\\net\\nvsp\\driver\\ctl\\vmsctlnic.c",
    1116,
    4,
    0,
    0,
    1,
    1);
  v29[0] = 0;
  v4 = 0;
  v5 = LibIoctlInitializeOperation(a3, v29);
  v7 = v29[0];
  v8 = v5;
  if ( v5 < 0 )
  {
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v6, 20, 44, (__int64)WPP_7a8fadac4d893e575a01306db05fafbf_Traceguids, v5);
    goto LABEL_9;
  }
  NdisAcquireRWLockRead(VmsOmObjectListLock, (PLOCK_STATE_EX)&LockState, 0);
  NicCountUnsafe = VmsOmGetNicCountUnsafe();
  v10 = NicCountUnsafe;
  v25 = NicCountUnsafe;
  if ( !NicCountUnsafe )
  {
LABEL_6:
    NdisReleaseRWLock(VmsOmObjectListLock, (PLOCK_STATE_EX)&LockState);
    goto LABEL_7;
  }
  v11 = LibIoctlAddArrayRecordEx(v7, 23, 2, 2612);
  v8 = v11;
  if ( v11 < 0 )
  {
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v12, 20, 45, (__int64)WPP_7a8fadac4d893e575a01306db05fafbf_Traceguids, v11);
    goto LABEL_6;
  }
  v14 = 0;
  v26 = 0;
  Pool2 = ExAllocatePool2(64, v10 << 8, 1950577494);
  v4 = (char *)Pool2;
  if ( !Pool2 )
  {
    v8 = -1073741670;
    LOBYTE(v15) = 2;
    WPP_RECORDER_SF_ddd(VmsIfrLog, v15, 20, 46, (__int64)WPP_7a8fadac4d893e575a01306db05fafbf_Traceguids, v25, 0, 154);
    goto LABEL_6;
  }
  v16 = VmsOmNicList;
  while ( (__int64 *)v16 != &VmsOmNicList )
  {
    v17 = *(_DWORD *)(v16 + 1872);
    if ( v17 == 5 )
      goto LABEL_25;
    if ( v17 == 2 && (unsigned __int8)VmsPtCheckIsEmbeddedTeamingEnabled(v16, 0) )
    {
      v18 = VmsCdpCopyMemberNicsToIoctlBuffer(v30, v7, v16, (unsigned int)&v26, (__int64)&Pool2, (__int64)&v25);
      v4 = (char *)Pool2;
      if ( v18 < 0 )
        v8 = v18;
      if ( v8 >= 0 )
        goto LABEL_25;
    }
    else
    {
      NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v16 + 56), &v32, 0);
      if ( v14 < v25 || (v21 = VmsCdpNicResizeArray(&Pool2, v20, &v25, v14 + 2), v4 = (char *)Pool2, v21) )
      {
        memmove(&v4[256 * (unsigned __int64)v14], *(const void **)(v16 + 352), *(unsigned __int16 *)(v16 + 344));
        v8 = 0;
        v26 = v14 + 1;
      }
      else
      {
        v8 = -1073741801;
      }
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v16 + 56), &v32);
      if ( v8 < 0 )
        goto LABEL_6;
      v8 = LibIoctlAddArrayRecordElement(v7, 0, &v28);
      if ( v8 >= 0 )
      {
        VmsCdpCopyNicInfo(v16, v28);
        v22 = v30;
        if ( (v30 & 1) != 0 )
        {
          WPP_RECORDER_SF_sddsSSdLLddSSdSS(
            *(_DWORD *)(v28 + 772),
            v28 + 1300,
            v28 + 1038,
            47,
            (__int64)WPP_7a8fadac4d893e575a01306db05fafbf_Traceguids,
            (__int64)"onecore\\vm\\dv\\net\\nvsp\\driver\\ctl\\vmsctlnic.c",
            241,
            ((unsigned int)v30 >> 2) & 0x7F,
            (__int64)"VmsCdpEnumNics",
            v28,
            v28 + 256,
            *(_WORD *)(v28 + 768),
            *(_DWORD *)(v28 + 772),
            *(_DWORD *)(v28 + 776),
            *(_BYTE *)(v28 + 780),
            *(_BYTE *)(v28 + 781),
            v28 + 782,
            v28 + 1038,
            *(_DWORD *)(v28 + 1296),
            v28 + 1300,
            v28 + 1812);
          v22 = v30;
          v7 = v29[0];
        }
        if ( (v22 & 1) != 0 )
          WPP_RECORDER_SF_sdds_MAC__MAC__MAC_DdS(
            *(_DWORD *)(v28 + 2344),
            v28,
            v28 + 2336,
            48,
            (__int64)WPP_7a8fadac4d893e575a01306db05fafbf_Traceguids,
            (__int64)"onecore\\vm\\dv\\net\\nvsp\\driver\\ctl\\vmsctlnic.c",
            242,
            (v22 >> 2) & 0x7F,
            (__int64)"VmsCdpEnumNics",
            v28 + 2324,
            v28 + 2330,
            v28 + 2336,
            *(_DWORD *)(v28 + 2344),
            *(_DWORD *)(v28 + 2348),
            v28 + 2352);
        goto LABEL_25;
      }
    }
    if ( v8 != -2147483643 && v8 != -1073741789 )
    {
      LOBYTE(v19) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v19, 20, 49, (__int64)WPP_7a8fadac4d893e575a01306db05fafbf_Traceguids, v8);
      goto LABEL_6;
    }
LABEL_25:
    v16 = *(_QWORD *)v16;
    v14 = v26;
  }
  NdisReleaseRWLock(VmsOmObjectListLock, (PLOCK_STATE_EX)&LockState);
  v23 = VmsPtNicAddConfiguredNicsToIoctlBuffer(v30, v7, (__int64)v4, v14);
  if ( v23 < 0 )
    v8 = v23;
LABEL_7:
  if ( v4 )
    ExFreePoolWithTag(v4, 0);
LABEL_9:
  LibIoctlFinalizeAndDeinitializeOperationEx(v7, 0);
  if ( v8 < 0 )
  {
    if ( v8 == -2147483643 || v8 == -1073741789 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) > 4u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          0,
          4,
          50,
          (__int64)WPP_7a8fadac4d893e575a01306db05fafbf_Traceguids,
          v8);
    }
    else
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v13, 20, 51, (__int64)WPP_7a8fadac4d893e575a01306db05fafbf_Traceguids, v8);
    }
  }
  VmsWppTraceApi(
    (unsigned int)&v30,
    (unsigned int)"VmsCdpEnumNics",
    (unsigned int)"onecore\\vm\\dv\\net\\nvsp\\driver\\ctl\\vmsctlnic.c",
    1360,
    4,
    v8,
    1,
    0,
    0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14005407c  mov     rax, rsp
0x14005407f  mov     [rax+18h], rbx
0x140054083  mov     [rax+10h], rdx
0x140054087  mov     [rax+8], rcx
0x14005408b  push    rbp
0x14005408c  push    rsi
0x14005408d  push    rdi
0x14005408e  push    r12
0x140054090  push    r13
0x140054092  push    r14
0x140054094  push    r15
0x140054096  lea     rbp, [rax-5Fh]
0x14005409a  sub     rsp, 0D0h
0x1400540a1  xor     eax, eax
0x1400540a3  mov     byte ptr [rsp+100h+var_C0], 1
0x1400540a8  xor     esi, esi
0x1400540aa  mov     byte ptr [rsp+100h+var_C8], 1
0x1400540af  mov     byte ptr [rsp+100h+var_D0], sil
0x1400540b4  lea     r12, aVmscdpenumnics_0; "VmsCdpEnumNics"
0x1400540bb  mov     rbx, r8
0x1400540be  mov     [rsp+100h+var_D8], esi
0x1400540c2  mov     r9d, 45Ch
0x1400540c8  mov     byte ptr [rsp+100h+var_E0], 4
0x1400540cd  lea     r8, aOnecoreVmDvNet_9; "onecore\\vm\\dv\\net\\nvsp\\driver\\ctl"...
0x1400540d4  mov     [rbp+57h+var_40], rsi
0x1400540d8  mov     rdx, r12
0x1400540db  mov     word ptr [rbp+57h+LockState], ax
0x1400540df  lea     rcx, [rbp+57h+arg_0]
0x1400540e3  mov     byte ptr [rbp+57h+LockState+2], al
0x1400540e6  mov     word ptr [rbp+57h+arg_18.OldIrql], ax
0x1400540ea  mov     [rbp+57h+arg_18.Flags], al
0x1400540f0  call    VmsWppTraceApi
0x1400540f5  lea     rdx, [rbp+57h+var_38]
0x1400540f9  mov     [rbp+57h+var_38], rsi
0x1400540fd  mov     rcx, rbx
0x140054100  mov     r13d, esi
0x140054103  call    LibIoctlInitializeOperation
0x140054108  mov     r14, [rbp+57h+var_38]
0x14005410c  mov     r15d, eax
0x14005410f  test    eax, eax
0x140054111  jns     short loc_14005413E
0x140054113  mov     rcx, cs:VmsIfrLog
0x14005411a  lea     rdi, WPP_7a8fadac4d893e575a01306db05fafbf_Traceguids
0x140054121  mov     [rsp+100h+var_D8], eax
0x140054125  lea     r9d, [rsi+2Ch]
0x140054129  lea     r8d, [rsi+14h]
0x14005412d  mov     [rsp+100h+var_E0], rdi
0x140054132  mov     dl, 2
0x140054134  call    WPP_RECORDER_SF_d
0x140054139  jmp     loc_1400541E6
0x14005413e  mov     rcx, cs:VmsOmObjectListLock; Lock
0x140054145  lea     rdx, [rbp+57h+LockState]; LockState
0x140054149  xor     r8d, r8d; Flags
0x14005414c  call    cs:__imp_NdisAcquireRWLockRead
0x140054153  nop     dword ptr [rax+rax+00h]
0x140054158  call    VmsOmGetNicCountUnsafe
0x14005415d  mov     esi, eax
0x14005415f  lea     rdi, WPP_7a8fadac4d893e575a01306db05fafbf_Traceguids
0x140054166  mov     [rbp+57h+var_50], esi
0x140054169  test    eax, eax
0x14005416b  jz      short loc_1400541B0
0x14005416d  mov     edx, 17h
0x140054172  mov     r9d, 0A34h
0x140054178  mov     rcx, r14
0x14005417b  lea     r8d, [rdx-15h]
0x14005417f  call    LibIoctlAddArrayRecordEx
0x140054184  mov     r15d, eax
0x140054187  test    eax, eax
0x140054189  jns     loc_14005423A
0x14005418f  mov     rcx, cs:VmsIfrLog
0x140054196  mov     r9d, 2Dh ; '-'
0x14005419c  mov     [rsp+100h+var_D8], eax
0x1400541a0  mov     dl, 2
0x1400541a2  mov     [rsp+100h+var_E0], rdi
0x1400541a7  lea     r8d, [r9-19h]
0x1400541ab  call    WPP_RECORDER_SF_d
0x1400541b0  xor     esi, esi
0x1400541b2  mov     rcx, cs:VmsOmObjectListLock; Lock
0x1400541b9  lea     rdx, [rbp+57h+LockState]; LockState
0x1400541bd  call    cs:__imp_NdisReleaseRWLock
0x1400541c4  nop     dword ptr [rax+rax+00h]
0x1400541c9  test    r13, r13
0x1400541cc  jz      short loc_1400541DF
0x1400541ce  xor     edx, edx; Tag
0x1400541d0  mov     rcx, r13; P
0x1400541d3  call    cs:__imp_ExFreePoolWithTag
0x1400541da  nop     dword ptr [rax+rax+00h]
0x1400541df  lea     r12, aVmscdpenumnics_0; "VmsCdpEnumNics"
0x1400541e6  xor     edx, edx
0x1400541e8  mov     rcx, r14
0x1400541eb  call    LibIoctlFinalizeAndDeinitializeOperationEx
0x1400541f0  test    r15d, r15d
0x1400541f3  jns     loc_1400545EC
0x1400541f9  cmp     r15d, 80000005h
0x140054200  jz      loc_1400545BA
0x140054206  cmp     r15d, 0C0000023h
0x14005420d  jz      loc_1400545BA
0x140054213  mov     rcx, cs:VmsIfrLog
0x14005421a  mov     r9d, 33h ; '3'
0x140054220  mov     [rsp+100h+var_D8], r15d
0x140054225  mov     dl, 2
0x140054227  mov     [rsp+100h+var_E0], rdi
0x14005422c  lea     r8d, [r9-1Fh]
0x140054230  call    WPP_RECORDER_SF_d
0x140054235  jmp     loc_1400545EC
0x14005423a  xor     ebx, ebx
0x14005423c  mov     rdx, rsi
0x14005423f  shl     rdx, 8
0x140054243  mov     r8d, 74437356h
0x140054249  mov     [rbp+57h+var_4C], ebx
0x14005424c  lea     ecx, [rbx+40h]
0x14005424f  call    cs:__imp_ExAllocatePool2
0x140054256  nop     dword ptr [rax+rax+00h]
0x14005425b  xor     esi, esi
0x14005425d  mov     [rbp+57h+var_48], rax
0x140054261  mov     r13, rax
0x140054264  test    rax, rax
0x140054267  jnz     short loc_1400542A3
0x140054269  mov     r15d, 0C000009Ah
0x14005426f  mov     eax, [rbp+57h+var_50]
0x140054272  lea     r9d, [rbx+2Eh]
0x140054276  mov     rcx, cs:VmsIfrLog
0x14005427d  lea     r8d, [rbx+14h]
0x140054281  mov     dword ptr [rsp+100h+var_C8], r15d
0x140054286  mov     dl, 2
0x140054288  mov     [rsp+100h+var_D0], 100h
0x140054290  mov     [rsp+100h+var_D8], eax
0x140054294  mov     [rsp+100h+var_E0], rdi
0x140054299  call    WPP_RECORDER_SF_ddd
0x14005429e  jmp     loc_1400541B2
0x1400542a3  mov     r12, cs:VmsOmNicList
0x1400542aa  lea     rax, VmsOmNicList
0x1400542b1  cmp     r12, rax
0x1400542b4  jz      loc_140054581
0x1400542ba  mov     eax, [r12+750h]
0x1400542c2  cmp     eax, 5
0x1400542c5  jz      short loc_140054324
0x1400542c7  cmp     eax, 2
0x1400542ca  jnz     short loc_140054330
0x1400542cc  xor     edx, edx
0x1400542ce  mov     rcx, r12
0x1400542d1  call    VmsPtCheckIsEmbeddedTeamingEnabled
0x1400542d6  test    al, al
0x1400542d8  jz      short loc_140054330
0x1400542da  mov     rcx, [rbp+57h+arg_0]
0x1400542de  lea     rax, [rbp+57h+var_50]
0x1400542e2  mov     qword ptr [rsp+100h+var_D8], rax
0x1400542e7  lea     r9, [rbp+57h+var_4C]
0x1400542eb  lea     rax, [rbp+57h+var_48]
0x1400542ef  mov     r8, r12
0x1400542f2  mov     rdx, r14
0x1400542f5  mov     [rsp+100h+var_E0], rax
0x1400542fa  call    VmsCdpCopyMemberNicsToIoctlBuffer
0x1400542ff  mov     r13, [rbp+57h+var_48]
0x140054303  test    eax, eax
0x140054305  cmovs   r15d, eax
0x140054309  test    r15d, r15d
0x14005430c  jns     short loc_140054324
0x14005430e  cmp     r15d, 80000005h
0x140054315  jz      short loc_140054324
0x140054317  cmp     r15d, 0C0000023h
0x14005431e  jnz     loc_14005455A
0x140054324  mov     r12, [r12]
0x140054328  mov     ebx, [rbp+57h+var_4C]
0x14005432b  jmp     loc_1400542AA
0x140054330  mov     rcx, [r12+38h]; Lock
0x140054335  lea     rdx, [rbp+57h+arg_18]; LockState
0x140054339  xor     r8d, r8d; Flags
0x14005433c  call    cs:__imp_NdisAcquireRWLockRead
0x140054343  nop     dword ptr [rax+rax+00h]
0x140054348  cmp     ebx, [rbp+57h+var_50]
0x14005434b  jb      short loc_14005436E
0x14005434d  lea     r9d, [rbx+2]
0x140054351  lea     r8, [rbp+57h+var_50]
0x140054355  lea     rcx, [rbp+57h+var_48]
0x140054359  call    VmsCdpNicResizeArray
0x14005435e  mov     r13, [rbp+57h+var_48]
0x140054362  test    al, al
0x140054364  jnz     short loc_14005436E
0x140054366  mov     r15d, 0C0000017h
0x14005436c  jmp     short loc_140054395
0x14005436e  movzx   r8d, word ptr [r12+158h]; Size
0x140054377  mov     rdx, [r12+160h]; Src
0x14005437f  mov     ecx, ebx
0x140054381  shl     rcx, 8
0x140054385  add     rcx, r13; void *
0x140054388  call    memmove
0x14005438d  inc     ebx
0x14005438f  mov     r15d, esi
0x140054392  mov     [rbp+57h+var_4C], ebx
0x140054395  mov     rcx, [r12+38h]; Lock
0x14005439a  lea     rdx, [rbp+57h+arg_18]; LockState
0x14005439e  call    cs:__imp_NdisReleaseRWLock
0x1400543a5  nop     dword ptr [rax+rax+00h]
0x1400543aa  test    r15d, r15d
0x1400543ad  js      loc_1400541B2
0x1400543b3  lea     r8, [rbp+57h+var_40]
0x1400543b7  xor     edx, edx
0x1400543b9  mov     rcx, r14
0x1400543bc  call    LibIoctlAddArrayRecordElement
0x1400543c1  mov     r15d, eax
0x1400543c4  test    eax, eax
0x1400543c6  js      loc_14005430E
0x1400543cc  mov     rdx, [rbp+57h+var_40]
0x1400543d0  mov     rcx, r12
0x1400543d3  call    VmsCdpCopyNicInfo
0x1400543d8  mov     rax, [rbp+57h+arg_0]
0x1400543dc  test    al, 1
0x1400543de  jz      loc_1400544CB
0x1400543e4  mov     r14, [rbp+57h+var_40]
0x1400543e8  mov     r9d, 2Fh ; '/'
0x1400543ee  shr     eax, 2
0x1400543f1  and     eax, 7Fh
0x1400543f4  movzx   ebx, byte ptr [r14+30Ch]
0x1400543fc  lea     rcx, [r14+714h]
0x140054403  movzx   edi, word ptr [r14+300h]
0x14005440b  lea     rdx, [r14+514h]
0x140054412  movzx   r11d, byte ptr [r14+30Dh]
0x14005441a  lea     r8, [r14+40Eh]
0x140054421  mov     [rsp+0A0h], rcx
0x140054429  lea     r10, [r14+30Eh]
0x140054430  mov     ecx, [r14+510h]
0x140054437  lea     rsi, [r14+100h]
0x14005443e  mov     [rsp+100h+var_68], rdx
0x140054446  mov     dword ptr [rsp+100h+var_70], ecx
0x14005444d  mov     ecx, [r14+308h]
0x140054454  mov     qword ptr [rsp+100h+var_78], r8
0x14005445c  mov     [rsp+100h+var_80], r10
0x140054464  mov     dword ptr [rsp+100h+var_88], r11d
0x140054469  mov     [rsp+100h+var_90], ebx
0x14005446d  lea     rbx, aVmscdpenumnics_0; "VmsCdpEnumNics"
0x140054474  mov     dword ptr [rsp+100h+var_98], ecx
0x140054478  mov     ecx, [r14+304h]
0x14005447f  mov     [rsp+100h+var_A0], ecx
0x140054483  mov     [rsp+100h+var_A8], edi
0x140054487  lea     rdi, WPP_7a8fadac4d893e575a01306db05fafbf_Traceguids
0x14005448e  mov     [rsp+100h+var_B0], rsi
0x140054493  mov     [rsp+100h+var_B8], r14
0x140054498  mov     [rsp+100h+var_C0], rbx
0x14005449d  mov     dword ptr [rsp+100h+var_C8], eax
0x1400544a1  lea     rax, aOnecoreVmDvNet_9; "onecore\\vm\\dv\\net\\nvsp\\driver\\ctl"...
0x1400544a8  mov     [rsp+100h+var_D0], 4F1h
0x1400544b0  mov     qword ptr [rsp+100h+var_D8], rax
0x1400544b5  mov     [rsp+100h+var_E0], rdi
0x1400544ba  call    WPP_RECORDER_SF_sddsSSdLLddSSdSS
0x1400544bf  mov     rax, [rbp+57h+arg_0]
0x1400544c3  xor     esi, esi
0x1400544c5  mov     r14, [rbp+57h+var_38]
0x1400544c9  jmp     short loc_1400544D2
0x1400544cb  lea     rbx, aVmscdpenumnics_0; "VmsCdpEnumNics"
0x1400544d2  test    al, 1
0x1400544d4  jz      loc_140054324
0x1400544da  mov     rdx, [rbp+57h+var_40]
0x1400544de  mov     r9d, 30h ; '0'
0x1400544e4  shr     eax, 2
0x1400544e7  and     eax, 7Fh
0x1400544ea  lea     rcx, [rdx+930h]
0x1400544f1  mov     qword ptr [rsp+100h+var_90], rcx
0x1400544f6  lea     r8, [rdx+920h]
0x1400544fd  mov     ecx, [rdx+92Ch]
0x140054503  lea     r10, [rdx+91Ah]
0x14005450a  mov     dword ptr [rsp+100h+var_98], ecx
0x14005450e  lea     r11, [rdx+914h]
0x140054515  mov     ecx, [rdx+928h]
0x14005451b  mov     [rsp+100h+var_A0], ecx
0x14005451f  mov     qword ptr [rsp+100h+var_A8], r8
0x140054524  mov     [rsp+100h+var_B0], r10
0x140054529  mov     [rsp+100h+var_B8], r11
0x14005452e  mov     [rsp+100h+var_C0], rbx
0x140054533  mov     dword ptr [rsp+100h+var_C8], eax
0x140054537  lea     rax, aOnecoreVmDvNet_9; "onecore\\vm\\dv\\net\\nvsp\\driver\\ctl"...
0x14005453e  mov     [rsp+100h+var_D0], 4F2h
0x140054546  mov     qword ptr [rsp+100h+var_D8], rax
0x14005454b  mov     [rsp+100h+var_E0], rdi
0x140054550  call    WPP_RECORDER_SF_sdds_MAC__MAC__MAC_DdS
0x140054555  jmp     loc_140054324
0x14005455a  mov     rcx, cs:VmsIfrLog
0x140054561  mov     r9d, 31h ; '1'
0x140054567  mov     [rsp+100h+var_D8], r15d
0x14005456c  mov     dl, 2
0x14005456e  mov     [rsp+100h+var_E0], rdi
0x140054573  lea     r8d, [r9-1Dh]
0x140054577  call    WPP_RECORDER_SF_d
0x14005457c  jmp     loc_1400541B2
0x140054581  mov     rcx, cs:VmsOmObjectListLock; Lock
0x140054588  lea     rdx, [rbp+57h+LockState]; LockState
0x14005458c  call    cs:__imp_NdisReleaseRWLock
0x140054593  nop     dword ptr [rax+rax+00h]
0x140054598  mov     rcx, [rbp+57h+arg_0]
0x14005459c  mov     r9d, ebx
0x14005459f  mov     r8, r13
0x1400545a2  mov     rdx, r14
0x1400545a5  call    VmsPtNicAddConfiguredNicsToIoctlBuffer
0x1400545aa  test    eax, eax
0x1400545ac  jns     loc_1400541C9
0x1400545b2  mov     r15d, eax
0x1400545b5  jmp     loc_1400541C9
0x1400545ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400545c1  cmp     byte ptr [rcx+29h], 4
0x1400545c5  ja      short loc_1400545CD
  ... truncated ...
```
