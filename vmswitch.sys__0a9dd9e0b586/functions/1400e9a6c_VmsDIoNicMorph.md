# VmsDIoNicMorph

- ea: `0x1400e9a6c`
- end: `0x1400ea166`
- name: `VmsDIoNicMorph`
- size: `1786`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400bf0e4`

## callees

- `0x14003a450`
- `0x14003c378`
- `0x14006b084`
- `0x140070a98`
- `0x140087fbc`
- `0x14008a258`
- `0x1400c65e0`
- `0x1400e9a6c`
- `0x1400ead08`
- `0x1400eaf3c`
- `0x1401bbbd4`
- `0x1401bbcb0`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e9f1b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e9f31`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e9f4c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e9f67`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e9faa`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e9f1b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e9f31`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e9f4c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e9f67`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e9faa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e9cac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e9cac`
- `ntoskrnl!ExAllocatePool2` at `0x1400e9bef`
- `ntoskrnl!ExAllocatePool2` at `0x1400e9bef`
- `NDIS!NdisFreeNetBufferListPool` at `0x1400e9c7e`
- `NDIS!NdisFreeNetBufferListPool` at `0x1400e9c7e`
- `NDIS!NdisAllocateNetBufferListPool` at `0x1400e9ebd`
- `NDIS!NdisAllocateNetBufferListPool` at `0x1400e9ebd`
- `NDIS!NdisReleaseRWLock` at `0x1400e9bb6`
- `NDIS!NdisReleaseRWLock` at `0x1400e9cf7`
- `NDIS!NdisReleaseRWLock` at `0x1401bcb4f`
- `NDIS!NdisReleaseRWLock` at `0x1400e9bb6`
- `NDIS!NdisReleaseRWLock` at `0x1400e9cf7`
- `NDIS!NdisReleaseRWLock` at `0x1401bcb4f`
- `NDIS!NdisFreeRWLock` at `0x1400e9c97`
- `NDIS!NdisFreeRWLock` at `0x1400e9c97`
- `NDIS!NdisAllocateRWLock` at `0x1400e9e1c`
- `NDIS!NdisAllocateRWLock` at `0x1400e9e1c`

## pseudocode

```c
__int64 __fastcall VmsDIoNicMorph(
        __int64 a1,
        const UNICODE_STRING *a2,
        const UNICODE_STRING *a3,
        const UNICODE_STRING *a4,
        const UNICODE_STRING *a5,
        __int64 a6,
        __int64 a7,
        char a8,
        int a9)
{
  char v11; // bl
  int v12; // edx
  int v13; // eax
  int v14; // edx
  int v15; // r8d
  char *Pool2; // rax
  int v17; // edx
  char *v18; // r15
  int v19; // edx
  int v20; // esi
  _QWORD *v21; // rdi
  __int64 v22; // r14
  void *v23; // rcx
  struct _NDIS_RW_LOCK_EX *v24; // rcx
  __int64 v25; // r14
  PNDIS_RW_LOCK_EX RWLock; // rax
  int v28; // edx
  NDIS_HANDLE NetBufferListPool; // rax
  int v30; // edx
  bool v31; // zf
  char v32; // al
  int *v33; // r14
  int v34; // r8d
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  int v38; // ecx
  _DWORD v39[10]; // [rsp+0h] [rbp-148h] BYREF
  char v40; // [rsp+80h] [rbp-C8h] BYREF
  char v41; // [rsp+81h] [rbp-C7h]
  struct _LOCK_STATE_EX LockState; // [rsp+84h] [rbp-C4h] BYREF
  int v43; // [rsp+88h] [rbp-C0h]
  __int64 v44; // [rsp+90h] [rbp-B8h]
  PVOID P; // [rsp+98h] [rbp-B0h]
  PCUNICODE_STRING SourceString; // [rsp+A0h] [rbp-A8h]
  PCUNICODE_STRING v47; // [rsp+A8h] [rbp-A0h]
  PCUNICODE_STRING v48; // [rsp+B0h] [rbp-98h]
  __int64 v49; // [rsp+B8h] [rbp-90h]
  __int64 v50; // [rsp+C0h] [rbp-88h]
  const UNICODE_STRING *v51; // [rsp+C8h] [rbp-80h]
  const UNICODE_STRING *v52; // [rsp+D0h] [rbp-78h]
  const UNICODE_STRING *v53; // [rsp+D8h] [rbp-70h]
  const UNICODE_STRING *v54; // [rsp+E0h] [rbp-68h]
  _DWORD *v55; // [rsp+E8h] [rbp-60h]
  _BYTE Parameters[20]; // [rsp+F0h] [rbp-58h] BYREF

  v55 = v39;
  v47 = a4;
  SourceString = a3;
  v49 = a1;
  v44 = a1;
  v54 = a2;
  v53 = a3;
  v52 = a4;
  v48 = a5;
  v51 = a5;
  v50 = a7;
  v11 = 0;
  v43 = 0;
  v41 = 0;
  P = 0;
  memset(Parameters, 0, sizeof(Parameters));
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v40 = 0;
  VmsOmObjectLockExclusive(a1, &LockState, 0);
  v13 = *(_DWORD *)(a1 + 1872);
  if ( v13 )
  {
    v43 = -1073741808;
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_d(VmsIfrNicLog, v12, 20, 10, (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids, v13);
    local_unwind_0(v39, &loc_1400E9C41);
  }
  *(_DWORD *)(a1 + 1872) = 4;
  v41 = 1;
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &LockState);
  if ( (*(_BYTE *)a7 & 1) == 0 && (*(_DWORD *)a7 || *(_WORD *)(a7 + 4)) )
  {
    Pool2 = (char *)ExAllocatePool2(64, 696, 1229222742);
    v18 = Pool2;
    P = Pool2;
    if ( !Pool2 )
    {
      LOBYTE(v17) = 2;
      WPP_RECORDER_SF_d(VmsIfrNicLog, v17, 20, 12, (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids, 184);
LABEL_8:
      v43 = -1073741670;
      goto LABEL_9;
    }
    memset(Pool2, 0, 0x2B8u);
    *(_QWORD *)v18 = a1;
    *((_DWORD *)v18 + 162) = a9;
    *((_QWORD *)v18 + 2) = v18 + 8;
    *((_QWORD *)v18 + 1) = v18 + 8;
    *((_QWORD *)v18 + 4) = v18 + 24;
    *((_QWORD *)v18 + 3) = v18 + 24;
    *((_QWORD *)v18 + 80) = v18 + 632;
    *((_QWORD *)v18 + 79) = v18 + 632;
    RWLock = NdisAllocateRWLock(VmsProtocolHandle);
    *((_QWORD *)v18 + 6) = RWLock;
    if ( !RWLock )
    {
      LOBYTE(v28) = 2;
      WPP_RECORDER_SF_I(
        VmsIfrNicLog,
        v28,
        20,
        13,
        (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids,
        (char)VmsProtocolHandle);
      goto LABEL_8;
    }
    *((_DWORD *)v18 + 10) = 0;
    *((_OWORD *)v18 + 4) = 0;
    *((_WORD *)v18 + 33) = 512;
    *((_QWORD *)v18 + 9) = v18 + 80;
    Parameters[13] = 0;
    *(_WORD *)&Parameters[14] = 0;
    *(_DWORD *)&Parameters[16] = 0;
    *(_DWORD *)Parameters = 1311104;
    *(_DWORD *)&Parameters[4] = 15204608;
    strcpy(&Parameters[8], "VsDI");
    NetBufferListPool = NdisAllocateNetBufferListPool(VmsProtocolHandle, (PNET_BUFFER_LIST_POOL_PARAMETERS)Parameters);
    *((_QWORD *)v18 + 7) = NetBufferListPool;
    if ( !NetBufferListPool )
    {
      LOBYTE(v30) = 2;
      WPP_RECORDER_SF_qq(
        VmsIfrNicLog,
        v30,
        20,
        14,
        (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids,
        (char)VmsProtocolHandle,
        (char)Parameters);
      goto LABEL_8;
    }
    RtlCopyUnicodeString((PUNICODE_STRING)(a1 + 616), a2);
    RtlCopyUnicodeString((PUNICODE_STRING)(a1 + 1288), a2);
    RtlCopyUnicodeString((PUNICODE_STRING)(a1 + 2112), SourceString);
    RtlCopyUnicodeString((PUNICODE_STRING)(a1 + 2640), v47);
    *(_QWORD *)(a1 + 3280) = a6;
    if ( !VmsIsHypercopyEnabled || (v31 = (unsigned __int8)HviIsKernelApertureAvailable() == 0, v32 = 0, v31) )
      v32 = 1;
    *(_BYTE *)(a1 + 1877) = v32;
    RtlCopyUnicodeString((PUNICODE_STRING)v18 + 4, v48);
    *(_QWORD *)(a1 + 3312) = v18;
    *(_QWORD *)(a1 + 3320) = &VmsDIoNicPvtContextCleanup;
    *(_DWORD *)(a1 + 3342) = *(_DWORD *)a7;
    *(_WORD *)(a1 + 3346) = *(_WORD *)(a7 + 4);
    v33 = (int *)(a1 + 3336);
    LOBYTE(v34) = a8;
    VmsOmNicAssignMacAddress(a1, a7, v34, a1 + 3336, (__int64)&v40);
    if ( !v40 || a8 )
    {
      v38 = *v33;
      *v33 = *v33;
      *(_WORD *)(a1 + 3340) = *(_WORD *)(a1 + 3340);
      *(_DWORD *)(a1 + 1838) = v38;
      *(_WORD *)(a1 + 1842) = *(_WORD *)(a1 + 3340);
      *(_DWORD *)(a1 + 2104) = *(_DWORD *)a7;
      *(_WORD *)(a1 + 2108) = *(_WORD *)(a7 + 4);
      *(_DWORD *)(a1 + 1832) = *(_DWORD *)a7;
      *(_WORD *)(a1 + 1836) = *(_WORD *)(a7 + 4);
      *(_QWORD *)(a1 + 3208) = 0;
      *(_QWORD *)(a1 + 3224) = 0;
      *(_QWORD *)(a1 + 3232) = 0;
      *(_QWORD *)(a1 + 3248) = 0;
      *(_QWORD *)(a1 + 3256) = 0;
      *(_QWORD *)(a1 + 3184) = VmsDIoNicPvtRead;
      *(_QWORD *)(a1 + 3192) = VmsDIoNicPvtWrite;
      *(_QWORD *)(a1 + 3176) = VmsDIoNicPvtPacketForward;
      *(_QWORD *)(a1 + 3168) = &VmsDIoNicPvtPacketRouted;
      *(_QWORD *)(a1 + 3200) = VmsDIoNicPvtLinkStateChanged;
      *(_QWORD *)(a1 + 3216) = VmsDIoNicPvtSendRelearnPacket;
      *(_QWORD *)(a1 + 3264) = VmsDIoNicPvtDeliverPDBuffers;
      *(_DWORD *)(a1 + 68) = 1;
    }
    else
    {
      WPP_RECORDER_SF_q_MAC_l(v35, v19, v36, v37, v39[8], a1, a7, 0);
      v43 = -1073741800;
    }
  }
  else
  {
    if ( !*(_DWORD *)a7 && !*(_WORD *)(a7 + 4) )
      v11 = 1;
    WPP_RECORDER_SF_ll_MAC_(
      VmsIfrNicLog,
      v14,
      v15,
      11,
      (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids,
      *(_BYTE *)a7 & 1,
      v11,
      a7);
    v43 = -1073741811;
  }
LABEL_9:
  v20 = v43;
  if ( v43 )
  {
    v21 = P;
    if ( P )
    {
      v22 = v44;
      *(_QWORD *)(v44 + 3312) = 0;
      *(_QWORD *)(v22 + 3320) = 0;
      v23 = (void *)v21[7];
      if ( v23 )
      {
        NdisFreeNetBufferListPool(v23);
        v21[7] = 0;
      }
      v24 = (struct _NDIS_RW_LOCK_EX *)v21[6];
      if ( v24 )
      {
        NdisFreeRWLock(v24);
        v21[6] = 0;
      }
      ExFreePoolWithTag(v21, 0);
    }
    if ( v41 )
    {
      v25 = v44;
      VmsOmObjectLockExclusive(v44, &LockState, 0);
      *(_DWORD *)(v25 + 1872) = 0;
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v49 + 56), &LockState);
    }
  }
  if ( v40 )
    v20 = -1073741800;
  if ( v20 < 0 )
  {
    LOBYTE(v19) = 2;
    WPP_RECORDER_SF_qZZZZi_MAC_lDd(
      v44,
      v19,
      20,
      16,
      (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids,
      v44,
      (__int64)v54,
      (__int64)v53,
      (__int64)v52,
      (__int64)v51,
      a6,
      v50,
      a8,
      a9,
      v20);
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x1400e9a6c  mov     r11, rsp
0x1400e9a6f  push    rbx
0x1400e9a70  push    rsi
0x1400e9a71  push    rdi
0x1400e9a72  push    r12
0x1400e9a74  push    r13
0x1400e9a76  push    r14
0x1400e9a78  push    r15
0x1400e9a7a  sub     rsp, 110h
0x1400e9a81  mov     rax, cs:__security_cookie
0x1400e9a88  xor     rax, rsp
0x1400e9a8b  mov     [rsp+148h+var_40], rax
0x1400e9a93  mov     [rsp+148h+var_60], rsp
0x1400e9a9b  mov     [rsp+148h+var_A0], r9
0x1400e9aa3  mov     rax, r8
0x1400e9aa6  mov     [rsp+148h+SourceString], rax
0x1400e9aae  mov     r12, rdx
0x1400e9ab1  mov     rdi, rcx
0x1400e9ab4  mov     [rsp+148h+var_90], rcx
0x1400e9abc  mov     [r11-0B8h], rcx
0x1400e9ac3  mov     [rsp+148h+var_68], rdx
0x1400e9acb  mov     [rsp+148h+var_70], rax
0x1400e9ad3  mov     [rsp+148h+var_78], r9
0x1400e9adb  mov     rax, [rsp+148h+arg_20]
0x1400e9ae3  mov     [rsp+148h+var_98], rax
0x1400e9aeb  mov     [rsp+148h+var_80], rax
0x1400e9af3  mov     rsi, [rsp+148h+arg_30]
0x1400e9afb  mov     [rsp+148h+var_88], rsi
0x1400e9b03  xor     ebx, ebx
0x1400e9b05  mov     [rsp+148h+var_C0], ebx
0x1400e9b0c  mov     [rsp+148h+var_C7], bl
0x1400e9b13  mov     [rsp+148h+P], rbx
0x1400e9b1b  xorps   xmm0, xmm0
0x1400e9b1e  xor     eax, eax
0x1400e9b20  movups  xmmword ptr [r11-58h], xmm0
0x1400e9b25  mov     [r11-48h], eax
0x1400e9b29  mov     word ptr [rsp+148h+LockState.OldIrql], ax
0x1400e9b31  mov     [rsp+148h+LockState.Flags], al
0x1400e9b38  mov     [rsp+148h+var_C8], bl
0x1400e9b3f  xor     r8d, r8d
0x1400e9b42  lea     rdx, [r11-0C4h]
0x1400e9b49  call    VmsOmObjectLockExclusive
0x1400e9b4e  mov     eax, [rdi+750h]
0x1400e9b54  test    eax, eax
0x1400e9b56  jz      short loc_1400E9B98
0x1400e9b58  mov     [rsp+148h+var_C0], 0C0000010h
0x1400e9b63  lea     r9d, [rbx+0Ah]
0x1400e9b67  mov     dword ptr [rsp+148h+var_120], eax
0x1400e9b6b  lea     rax, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x1400e9b72  mov     [rsp+148h+var_128], rax
0x1400e9b77  lea     r8d, [rbx+14h]
0x1400e9b7b  mov     dl, 2
0x1400e9b7d  mov     rcx, cs:VmsIfrNicLog
0x1400e9b84  call    WPP_RECORDER_SF_d
0x1400e9b89  lea     rdx, loc_1400E9C41
0x1400e9b90  mov     rcx, rsp
0x1400e9b93  call    _local_unwind_0
0x1400e9b98  mov     dword ptr [rdi+750h], 4
0x1400e9ba2  mov     [rsp+148h+var_C7], 1
0x1400e9baa  lea     rdx, [rsp+148h+LockState]; LockState
0x1400e9bb2  mov     rcx, [rdi+38h]; Lock
0x1400e9bb6  call    cs:__imp_NdisReleaseRWLock
0x1400e9bbd  nop     dword ptr [rax+rax+00h]
0x1400e9bc2  movzx   eax, byte ptr [rsi]
0x1400e9bc5  test    al, 1
0x1400e9bc7  jnz     loc_1400EA119
0x1400e9bcd  cmp     [rsi], ebx
0x1400e9bcf  jnz     short loc_1400E9BDB
0x1400e9bd1  cmp     [rsi+4], bx
0x1400e9bd5  jz      loc_1400EA119
0x1400e9bdb  mov     r8d, 49447356h
0x1400e9be1  mov     r14d, 2B8h
0x1400e9be7  mov     edx, r14d
0x1400e9bea  mov     ecx, 40h ; '@'
0x1400e9bef  call    cs:__imp_ExAllocatePool2
0x1400e9bf6  nop     dword ptr [rax+rax+00h]
0x1400e9bfb  mov     r15, rax
0x1400e9bfe  mov     [rsp+148h+P], rax
0x1400e9c06  test    rax, rax
0x1400e9c09  jnz     loc_1400E9DD3
0x1400e9c0f  lea     r9d, [rax+0Ch]
0x1400e9c13  mov     dword ptr [rsp+148h+var_120], r14d
0x1400e9c18  lea     rax, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x1400e9c1f  mov     [rsp+148h+var_128], rax
0x1400e9c24  lea     r8d, [r15+14h]
0x1400e9c28  mov     dl, 2
0x1400e9c2a  mov     rcx, cs:VmsIfrNicLog
0x1400e9c31  call    WPP_RECORDER_SF_d
0x1400e9c36  mov     [rsp+148h+var_C0], 0C000009Ah
0x1400e9c41  mov     esi, [rsp+148h+var_C0]
0x1400e9c48  xor     ebx, ebx
0x1400e9c4a  test    esi, esi
0x1400e9c4c  jz      loc_1400E9D03
0x1400e9c52  mov     rdi, [rsp+148h+P]
0x1400e9c5a  test    rdi, rdi
0x1400e9c5d  jz      short loc_1400E9CB8
0x1400e9c5f  mov     r14, [rsp+148h+var_B8]
0x1400e9c67  mov     [r14+0CF0h], rbx
0x1400e9c6e  mov     [r14+0CF8h], rbx
0x1400e9c75  mov     rcx, [rdi+38h]; PoolHandle
0x1400e9c79  test    rcx, rcx
0x1400e9c7c  jz      short loc_1400E9C8E
0x1400e9c7e  call    cs:__imp_NdisFreeNetBufferListPool
0x1400e9c85  nop     dword ptr [rax+rax+00h]
0x1400e9c8a  mov     [rdi+38h], rbx
0x1400e9c8e  mov     rcx, [rdi+30h]; Lock
0x1400e9c92  test    rcx, rcx
0x1400e9c95  jz      short loc_1400E9CA7
0x1400e9c97  call    cs:__imp_NdisFreeRWLock
0x1400e9c9e  nop     dword ptr [rax+rax+00h]
0x1400e9ca3  mov     [rdi+30h], rbx
0x1400e9ca7  xor     edx, edx; Tag
0x1400e9ca9  mov     rcx, rdi; P
0x1400e9cac  call    cs:__imp_ExFreePoolWithTag
0x1400e9cb3  nop     dword ptr [rax+rax+00h]
0x1400e9cb8  cmp     [rsp+148h+var_C7], bl
0x1400e9cbf  jz      short loc_1400E9D03
0x1400e9cc1  xor     r8d, r8d
0x1400e9cc4  lea     rdx, [rsp+148h+LockState]
0x1400e9ccc  mov     r14, [rsp+148h+var_B8]
0x1400e9cd4  mov     rcx, r14
0x1400e9cd7  call    VmsOmObjectLockExclusive
0x1400e9cdc  mov     [r14+750h], ebx
0x1400e9ce3  lea     rdx, [rsp+148h+LockState]; LockState
0x1400e9ceb  mov     rcx, [rsp+148h+var_90]
0x1400e9cf3  mov     rcx, [rcx+38h]; Lock
0x1400e9cf7  call    cs:__imp_NdisReleaseRWLock
0x1400e9cfe  nop     dword ptr [rax+rax+00h]
0x1400e9d03  mov     eax, 0C0000018h
0x1400e9d08  cmp     [rsp+148h+var_C8], bl
0x1400e9d0f  cmovnz  esi, eax
0x1400e9d12  test    esi, esi
0x1400e9d14  jns     loc_1400E9DAD
0x1400e9d1a  movzx   ecx, [rsp+148h+arg_38]
0x1400e9d22  mov     r9d, 10h
0x1400e9d28  mov     [rsp+148h+var_D8], esi
0x1400e9d2c  mov     eax, [rsp+148h+arg_40]
0x1400e9d33  mov     [rsp+148h+var_E0], eax
0x1400e9d37  mov     [rsp+148h+var_E8], ecx
0x1400e9d3b  mov     rax, [rsp+148h+var_88]
0x1400e9d43  mov     [rsp+148h+var_F0], rax
0x1400e9d48  mov     rax, [rsp+148h+arg_28]
0x1400e9d50  mov     [rsp+148h+var_F8], rax
0x1400e9d55  mov     rax, [rsp+148h+var_80]
0x1400e9d5d  mov     [rsp+148h+var_100], rax
0x1400e9d62  mov     rax, [rsp+148h+var_78]
0x1400e9d6a  mov     [rsp+148h+var_108], rax
0x1400e9d6f  mov     rax, [rsp+148h+var_70]
0x1400e9d77  mov     [rsp+148h+var_110], rax
0x1400e9d7c  mov     rcx, [rsp+148h+var_68]
0x1400e9d84  mov     [rsp+148h+var_118], rcx
0x1400e9d89  mov     rcx, [rsp+148h+var_B8]
0x1400e9d91  mov     [rsp+148h+var_120], rcx
0x1400e9d96  lea     rax, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x1400e9d9d  mov     [rsp+148h+var_128], rax
0x1400e9da2  lea     r8d, [r9+4]
0x1400e9da6  mov     dl, 2
0x1400e9da8  call    WPP_RECORDER_SF_qZZZZi_MAC_lDd
0x1400e9dad  mov     eax, esi
0x1400e9daf  mov     rcx, [rsp+148h+var_40]
0x1400e9db7  xor     rcx, rsp; StackCookie
0x1400e9dba  call    __security_check_cookie
0x1400e9dbf  add     rsp, 110h
0x1400e9dc6  pop     r15
0x1400e9dc8  pop     r14
0x1400e9dca  pop     r13
0x1400e9dcc  pop     r12
0x1400e9dce  pop     rdi
0x1400e9dcf  pop     rsi
0x1400e9dd0  pop     rbx
0x1400e9dd1  retn
0x1400e9dd3  mov     r8, r14; Size
0x1400e9dd6  xor     edx, edx; Val
0x1400e9dd8  mov     rcx, r15; void *
0x1400e9ddb  call    memset
0x1400e9de0  mov     [r15], rdi
0x1400e9de3  mov     eax, [rsp+148h+arg_40]
0x1400e9dea  mov     [r15+288h], eax
0x1400e9df1  lea     rax, [r15+8]
0x1400e9df5  mov     [rax+8], rax
0x1400e9df9  mov     [rax], rax
0x1400e9dfc  lea     rax, [r15+18h]
0x1400e9e00  mov     [rax+8], rax
0x1400e9e04  mov     [rax], rax
0x1400e9e07  lea     rax, [r15+278h]
0x1400e9e0e  mov     [rax+8], rax
0x1400e9e12  mov     [rax], rax
0x1400e9e15  mov     rcx, cs:VmsProtocolHandle; NdisHandle
0x1400e9e1c  call    cs:__imp_NdisAllocateRWLock
0x1400e9e23  nop     dword ptr [rax+rax+00h]
0x1400e9e28  mov     [r15+30h], rax
0x1400e9e2c  test    rax, rax
0x1400e9e2f  jnz     short loc_1400E9E64
0x1400e9e31  lea     r9d, [rax+0Dh]
0x1400e9e35  mov     rax, cs:VmsProtocolHandle
0x1400e9e3c  mov     [rsp+148h+var_120], rax
0x1400e9e41  lea     rax, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x1400e9e48  mov     [rsp+148h+var_128], rax
0x1400e9e4d  lea     r8d, [r9+7]
0x1400e9e51  mov     dl, 2
0x1400e9e53  mov     rcx, cs:VmsIfrNicLog
0x1400e9e5a  call    WPP_RECORDER_SF_I
0x1400e9e5f  jmp     loc_1400E9C36
0x1400e9e64  mov     [r15+28h], ebx
0x1400e9e68  xorps   xmm0, xmm0
0x1400e9e6b  movups  xmmword ptr [r15+40h], xmm0
0x1400e9e70  mov     word ptr [r15+42h], 200h
0x1400e9e77  lea     rax, [r15+50h]
0x1400e9e7b  mov     [r15+48h], rax
0x1400e9e7f  mov     qword ptr [rsp+148h+Parameters+0Ch], rbx
0x1400e9e87  mov     dword ptr [rsp+148h+Parameters], 140180h
0x1400e9e92  mov     r14d, 14h
0x1400e9e98  mov     dword ptr [rsp+148h+Parameters+4], 0E80100h
0x1400e9ea3  mov     dword ptr [rsp+148h+Parameters+8], 49447356h
0x1400e9eae  lea     rdx, [rsp+148h+Parameters]; Parameters
0x1400e9eb6  mov     rcx, cs:VmsProtocolHandle; NdisHandle
0x1400e9ebd  call    cs:__imp_NdisAllocateNetBufferListPool
0x1400e9ec4  nop     dword ptr [rax+rax+00h]
0x1400e9ec9  mov     [r15+38h], rax
0x1400e9ecd  test    rax, rax
0x1400e9ed0  jnz     short loc_1400E9F11
0x1400e9ed2  lea     r9d, [r14-6]
0x1400e9ed6  lea     rax, [rsp+148h+Parameters]
0x1400e9ede  mov     [rsp+148h+var_118], rax
0x1400e9ee3  mov     rax, cs:VmsProtocolHandle
0x1400e9eea  mov     [rsp+148h+var_120], rax
0x1400e9eef  lea     rax, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x1400e9ef6  mov     [rsp+148h+var_128], rax
0x1400e9efb  mov     r8d, r14d
0x1400e9efe  mov     dl, 2
0x1400e9f00  mov     rcx, cs:VmsIfrNicLog
0x1400e9f07  call    WPP_RECORDER_SF_qq
0x1400e9f0c  jmp     loc_1400E9C36
0x1400e9f11  lea     rcx, [rdi+268h]; DestinationString
0x1400e9f18  mov     rdx, r12; SourceString
0x1400e9f1b  call    cs:__imp_RtlCopyUnicodeString
0x1400e9f22  nop     dword ptr [rax+rax+00h]
0x1400e9f27  lea     rcx, [rdi+508h]; DestinationString
0x1400e9f2e  mov     rdx, r12; SourceString
0x1400e9f31  call    cs:__imp_RtlCopyUnicodeString
0x1400e9f38  nop     dword ptr [rax+rax+00h]
0x1400e9f3d  lea     rcx, [rdi+840h]; DestinationString
0x1400e9f44  mov     rdx, [rsp+148h+SourceString]; SourceString
0x1400e9f4c  call    cs:__imp_RtlCopyUnicodeString
0x1400e9f53  nop     dword ptr [rax+rax+00h]
0x1400e9f58  lea     rcx, [rdi+0A50h]; DestinationString
0x1400e9f5f  mov     rdx, [rsp+148h+var_A0]; SourceString
0x1400e9f67  call    cs:__imp_RtlCopyUnicodeString
0x1400e9f6e  nop     dword ptr [rax+rax+00h]
0x1400e9f73  mov     rax, [rsp+148h+arg_28]
0x1400e9f7b  mov     [rdi+0CD0h], rax
0x1400e9f82  cmp     cs:VmsIsHypercopyEnabled, 0
0x1400e9f89  jz      short loc_1400E9F96
0x1400e9f8b  call    HviIsKernelApertureAvailable
0x1400e9f90  test    al, al
0x1400e9f92  mov     al, bl
0x1400e9f94  jnz     short loc_1400E9F98
0x1400e9f96  mov     al, 1
0x1400e9f98  mov     [rdi+755h], al
0x1400e9f9e  mov     rdx, [rsp+148h+var_98]; SourceString
0x1400e9fa6  lea     rcx, [r15+40h]; DestinationString
0x1400e9faa  call    cs:__imp_RtlCopyUnicodeString
0x1400e9fb1  nop     dword ptr [rax+rax+00h]
0x1400e9fb6  mov     [rdi+0CF0h], r15
0x1400e9fbd  lea     rax, VmsDIoNicPvtContextCleanup
0x1400e9fc4  mov     [rdi+0CF8h], rax
0x1400e9fcb  mov     eax, [rsi]
0x1400e9fcd  mov     [rdi+0D0Eh], eax
0x1400e9fd3  movzx   eax, word ptr [rsi+4]
0x1400e9fd7  mov     [rdi+0D12h], ax
0x1400e9fde  lea     r14, [rdi+0D08h]
0x1400e9fe5  lea     rax, [rsp+148h+var_C8]
0x1400e9fed  mov     [rsp+148h+var_128], rax
0x1400e9ff2  mov     r9, r14
0x1400e9ff5  mov     r8b, [rsp+148h+arg_38]
0x1400e9ffd  mov     rdx, rsi
0x1400ea000  mov     rcx, rdi
0x1400ea003  call    VmsOmNicAssignMacAddress
0x1400ea008  cmp     [rsp+148h+var_C8], bl
0x1400ea00f  jz      short loc_1400EA03E
0x1400ea011  cmp     [rsp+148h+arg_38], bl
0x1400ea018  jnz     short loc_1400EA03E
0x1400ea01a  mov     dword ptr [rsp+148h+var_110], ebx
0x1400ea01e  mov     [rsp+148h+var_118], rsi
0x1400ea023  mov     [rsp+148h+var_120], rdi
0x1400ea028  call    WPP_RECORDER_SF_q_MAC_l
0x1400ea02d  mov     eax, 0C0000018h
0x1400ea032  mov     [rsp+148h+var_C0], eax
0x1400ea039  jmp     loc_1400E9C41
0x1400ea03e  mov     ecx, [r14]
0x1400ea041  mov     [r14], ecx
0x1400ea044  movzx   eax, word ptr [r14+4]
0x1400ea049  mov     [rdi+0D0Ch], ax
0x1400ea050  mov     [rdi+72Eh], ecx
0x1400ea056  movzx   eax, word ptr [r14+4]
0x1400ea05b  mov     [rdi+732h], ax
0x1400ea062  mov     eax, [rsi]
0x1400ea064  mov     [rdi+838h], eax
0x1400ea06a  movzx   eax, word ptr [rsi+4]
0x1400ea06e  mov     [rdi+83Ch], ax
  ... truncated ...
```
