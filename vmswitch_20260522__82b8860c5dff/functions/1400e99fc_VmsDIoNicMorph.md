# VmsDIoNicMorph

- ea: `0x1400e99fc`
- end: `0x1400ea0f6`
- name: `VmsDIoNicMorph`
- size: `1786`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400bf074`

## callees

- `0x14003a450`
- `0x14003c378`
- `0x14006b084`
- `0x140070a98`
- `0x140087fbc`
- `0x14008a258`
- `0x1400c6570`
- `0x1400e99fc`
- `0x1400eac98`
- `0x1400eaecc`
- `0x1401bbb64`
- `0x1401bbc40`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e9eab`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e9ec1`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e9edc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e9ef7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e9f3a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e9eab`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e9ec1`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e9edc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e9ef7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e9f3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e9c3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e9c3c`
- `ntoskrnl!ExAllocatePool2` at `0x1400e9b7f`
- `ntoskrnl!ExAllocatePool2` at `0x1400e9b7f`
- `NDIS!NdisFreeNetBufferListPool` at `0x1400e9c0e`
- `NDIS!NdisFreeNetBufferListPool` at `0x1400e9c0e`
- `NDIS!NdisAllocateNetBufferListPool` at `0x1400e9e4d`
- `NDIS!NdisAllocateNetBufferListPool` at `0x1400e9e4d`
- `NDIS!NdisReleaseRWLock` at `0x1400e9b46`
- `NDIS!NdisReleaseRWLock` at `0x1400e9c87`
- `NDIS!NdisReleaseRWLock` at `0x1401bcacf`
- `NDIS!NdisReleaseRWLock` at `0x1400e9b46`
- `NDIS!NdisReleaseRWLock` at `0x1400e9c87`
- `NDIS!NdisReleaseRWLock` at `0x1401bcacf`
- `NDIS!NdisFreeRWLock` at `0x1400e9c27`
- `NDIS!NdisFreeRWLock` at `0x1400e9c27`
- `NDIS!NdisAllocateRWLock` at `0x1400e9dac`
- `NDIS!NdisAllocateRWLock` at `0x1400e9dac`

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
    local_unwind_0(v39, &loc_1400E9BD1);
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
0x1400e99fc  mov     r11, rsp
0x1400e99ff  push    rbx
0x1400e9a00  push    rsi
0x1400e9a01  push    rdi
0x1400e9a02  push    r12
0x1400e9a04  push    r13
0x1400e9a06  push    r14
0x1400e9a08  push    r15
0x1400e9a0a  sub     rsp, 110h
0x1400e9a11  mov     rax, cs:__security_cookie
0x1400e9a18  xor     rax, rsp
0x1400e9a1b  mov     [rsp+148h+var_40], rax
0x1400e9a23  mov     [rsp+148h+var_60], rsp
0x1400e9a2b  mov     [rsp+148h+var_A0], r9
0x1400e9a33  mov     rax, r8
0x1400e9a36  mov     [rsp+148h+SourceString], rax
0x1400e9a3e  mov     r12, rdx
0x1400e9a41  mov     rdi, rcx
0x1400e9a44  mov     [rsp+148h+var_90], rcx
0x1400e9a4c  mov     [r11-0B8h], rcx
0x1400e9a53  mov     [rsp+148h+var_68], rdx
0x1400e9a5b  mov     [rsp+148h+var_70], rax
0x1400e9a63  mov     [rsp+148h+var_78], r9
0x1400e9a6b  mov     rax, [rsp+148h+arg_20]
0x1400e9a73  mov     [rsp+148h+var_98], rax
0x1400e9a7b  mov     [rsp+148h+var_80], rax
0x1400e9a83  mov     rsi, [rsp+148h+arg_30]
0x1400e9a8b  mov     [rsp+148h+var_88], rsi
0x1400e9a93  xor     ebx, ebx
0x1400e9a95  mov     [rsp+148h+var_C0], ebx
0x1400e9a9c  mov     [rsp+148h+var_C7], bl
0x1400e9aa3  mov     [rsp+148h+P], rbx
0x1400e9aab  xorps   xmm0, xmm0
0x1400e9aae  xor     eax, eax
0x1400e9ab0  movups  xmmword ptr [r11-58h], xmm0
0x1400e9ab5  mov     [r11-48h], eax
0x1400e9ab9  mov     word ptr [rsp+148h+LockState.OldIrql], ax
0x1400e9ac1  mov     [rsp+148h+LockState.Flags], al
0x1400e9ac8  mov     [rsp+148h+var_C8], bl
0x1400e9acf  xor     r8d, r8d
0x1400e9ad2  lea     rdx, [r11-0C4h]
0x1400e9ad9  call    VmsOmObjectLockExclusive
0x1400e9ade  mov     eax, [rdi+750h]
0x1400e9ae4  test    eax, eax
0x1400e9ae6  jz      short loc_1400E9B28
0x1400e9ae8  mov     [rsp+148h+var_C0], 0C0000010h
0x1400e9af3  lea     r9d, [rbx+0Ah]
0x1400e9af7  mov     dword ptr [rsp+148h+var_120], eax
0x1400e9afb  lea     rax, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x1400e9b02  mov     [rsp+148h+var_128], rax
0x1400e9b07  lea     r8d, [rbx+14h]
0x1400e9b0b  mov     dl, 2
0x1400e9b0d  mov     rcx, cs:VmsIfrNicLog
0x1400e9b14  call    WPP_RECORDER_SF_d
0x1400e9b19  lea     rdx, loc_1400E9BD1
0x1400e9b20  mov     rcx, rsp
0x1400e9b23  call    _local_unwind_0
0x1400e9b28  mov     dword ptr [rdi+750h], 4
0x1400e9b32  mov     [rsp+148h+var_C7], 1
0x1400e9b3a  lea     rdx, [rsp+148h+LockState]; LockState
0x1400e9b42  mov     rcx, [rdi+38h]; Lock
0x1400e9b46  call    cs:__imp_NdisReleaseRWLock
0x1400e9b4d  nop     dword ptr [rax+rax+00h]
0x1400e9b52  movzx   eax, byte ptr [rsi]
0x1400e9b55  test    al, 1
0x1400e9b57  jnz     loc_1400EA0A9
0x1400e9b5d  cmp     [rsi], ebx
0x1400e9b5f  jnz     short loc_1400E9B6B
0x1400e9b61  cmp     [rsi+4], bx
0x1400e9b65  jz      loc_1400EA0A9
0x1400e9b6b  mov     r8d, 49447356h
0x1400e9b71  mov     r14d, 2B8h
0x1400e9b77  mov     edx, r14d
0x1400e9b7a  mov     ecx, 40h ; '@'
0x1400e9b7f  call    cs:__imp_ExAllocatePool2
0x1400e9b86  nop     dword ptr [rax+rax+00h]
0x1400e9b8b  mov     r15, rax
0x1400e9b8e  mov     [rsp+148h+P], rax
0x1400e9b96  test    rax, rax
0x1400e9b99  jnz     loc_1400E9D63
0x1400e9b9f  lea     r9d, [rax+0Ch]
0x1400e9ba3  mov     dword ptr [rsp+148h+var_120], r14d
0x1400e9ba8  lea     rax, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x1400e9baf  mov     [rsp+148h+var_128], rax
0x1400e9bb4  lea     r8d, [r15+14h]
0x1400e9bb8  mov     dl, 2
0x1400e9bba  mov     rcx, cs:VmsIfrNicLog
0x1400e9bc1  call    WPP_RECORDER_SF_d
0x1400e9bc6  mov     [rsp+148h+var_C0], 0C000009Ah
0x1400e9bd1  mov     esi, [rsp+148h+var_C0]
0x1400e9bd8  xor     ebx, ebx
0x1400e9bda  test    esi, esi
0x1400e9bdc  jz      loc_1400E9C93
0x1400e9be2  mov     rdi, [rsp+148h+P]
0x1400e9bea  test    rdi, rdi
0x1400e9bed  jz      short loc_1400E9C48
0x1400e9bef  mov     r14, [rsp+148h+var_B8]
0x1400e9bf7  mov     [r14+0CF0h], rbx
0x1400e9bfe  mov     [r14+0CF8h], rbx
0x1400e9c05  mov     rcx, [rdi+38h]; PoolHandle
0x1400e9c09  test    rcx, rcx
0x1400e9c0c  jz      short loc_1400E9C1E
0x1400e9c0e  call    cs:__imp_NdisFreeNetBufferListPool
0x1400e9c15  nop     dword ptr [rax+rax+00h]
0x1400e9c1a  mov     [rdi+38h], rbx
0x1400e9c1e  mov     rcx, [rdi+30h]; Lock
0x1400e9c22  test    rcx, rcx
0x1400e9c25  jz      short loc_1400E9C37
0x1400e9c27  call    cs:__imp_NdisFreeRWLock
0x1400e9c2e  nop     dword ptr [rax+rax+00h]
0x1400e9c33  mov     [rdi+30h], rbx
0x1400e9c37  xor     edx, edx; Tag
0x1400e9c39  mov     rcx, rdi; P
0x1400e9c3c  call    cs:__imp_ExFreePoolWithTag
0x1400e9c43  nop     dword ptr [rax+rax+00h]
0x1400e9c48  cmp     [rsp+148h+var_C7], bl
0x1400e9c4f  jz      short loc_1400E9C93
0x1400e9c51  xor     r8d, r8d
0x1400e9c54  lea     rdx, [rsp+148h+LockState]
0x1400e9c5c  mov     r14, [rsp+148h+var_B8]
0x1400e9c64  mov     rcx, r14
0x1400e9c67  call    VmsOmObjectLockExclusive
0x1400e9c6c  mov     [r14+750h], ebx
0x1400e9c73  lea     rdx, [rsp+148h+LockState]; LockState
0x1400e9c7b  mov     rcx, [rsp+148h+var_90]
0x1400e9c83  mov     rcx, [rcx+38h]; Lock
0x1400e9c87  call    cs:__imp_NdisReleaseRWLock
0x1400e9c8e  nop     dword ptr [rax+rax+00h]
0x1400e9c93  mov     eax, 0C0000018h
0x1400e9c98  cmp     [rsp+148h+var_C8], bl
0x1400e9c9f  cmovnz  esi, eax
0x1400e9ca2  test    esi, esi
0x1400e9ca4  jns     loc_1400E9D3D
0x1400e9caa  movzx   ecx, [rsp+148h+arg_38]
0x1400e9cb2  mov     r9d, 10h
0x1400e9cb8  mov     [rsp+148h+var_D8], esi
0x1400e9cbc  mov     eax, [rsp+148h+arg_40]
0x1400e9cc3  mov     [rsp+148h+var_E0], eax
0x1400e9cc7  mov     [rsp+148h+var_E8], ecx
0x1400e9ccb  mov     rax, [rsp+148h+var_88]
0x1400e9cd3  mov     [rsp+148h+var_F0], rax
0x1400e9cd8  mov     rax, [rsp+148h+arg_28]
0x1400e9ce0  mov     [rsp+148h+var_F8], rax
0x1400e9ce5  mov     rax, [rsp+148h+var_80]
0x1400e9ced  mov     [rsp+148h+var_100], rax
0x1400e9cf2  mov     rax, [rsp+148h+var_78]
0x1400e9cfa  mov     [rsp+148h+var_108], rax
0x1400e9cff  mov     rax, [rsp+148h+var_70]
0x1400e9d07  mov     [rsp+148h+var_110], rax
0x1400e9d0c  mov     rcx, [rsp+148h+var_68]
0x1400e9d14  mov     [rsp+148h+var_118], rcx
0x1400e9d19  mov     rcx, [rsp+148h+var_B8]
0x1400e9d21  mov     [rsp+148h+var_120], rcx
0x1400e9d26  lea     rax, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x1400e9d2d  mov     [rsp+148h+var_128], rax
0x1400e9d32  lea     r8d, [r9+4]
0x1400e9d36  mov     dl, 2
0x1400e9d38  call    WPP_RECORDER_SF_qZZZZi_MAC_lDd
0x1400e9d3d  mov     eax, esi
0x1400e9d3f  mov     rcx, [rsp+148h+var_40]
0x1400e9d47  xor     rcx, rsp; StackCookie
0x1400e9d4a  call    __security_check_cookie
0x1400e9d4f  add     rsp, 110h
0x1400e9d56  pop     r15
0x1400e9d58  pop     r14
0x1400e9d5a  pop     r13
0x1400e9d5c  pop     r12
0x1400e9d5e  pop     rdi
0x1400e9d5f  pop     rsi
0x1400e9d60  pop     rbx
0x1400e9d61  retn
0x1400e9d63  mov     r8, r14; Size
0x1400e9d66  xor     edx, edx; Val
0x1400e9d68  mov     rcx, r15; void *
0x1400e9d6b  call    memset
0x1400e9d70  mov     [r15], rdi
0x1400e9d73  mov     eax, [rsp+148h+arg_40]
0x1400e9d7a  mov     [r15+288h], eax
0x1400e9d81  lea     rax, [r15+8]
0x1400e9d85  mov     [rax+8], rax
0x1400e9d89  mov     [rax], rax
0x1400e9d8c  lea     rax, [r15+18h]
0x1400e9d90  mov     [rax+8], rax
0x1400e9d94  mov     [rax], rax
0x1400e9d97  lea     rax, [r15+278h]
0x1400e9d9e  mov     [rax+8], rax
0x1400e9da2  mov     [rax], rax
0x1400e9da5  mov     rcx, cs:VmsProtocolHandle; NdisHandle
0x1400e9dac  call    cs:__imp_NdisAllocateRWLock
0x1400e9db3  nop     dword ptr [rax+rax+00h]
0x1400e9db8  mov     [r15+30h], rax
0x1400e9dbc  test    rax, rax
0x1400e9dbf  jnz     short loc_1400E9DF4
0x1400e9dc1  lea     r9d, [rax+0Dh]
0x1400e9dc5  mov     rax, cs:VmsProtocolHandle
0x1400e9dcc  mov     [rsp+148h+var_120], rax
0x1400e9dd1  lea     rax, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x1400e9dd8  mov     [rsp+148h+var_128], rax
0x1400e9ddd  lea     r8d, [r9+7]
0x1400e9de1  mov     dl, 2
0x1400e9de3  mov     rcx, cs:VmsIfrNicLog
0x1400e9dea  call    WPP_RECORDER_SF_I
0x1400e9def  jmp     loc_1400E9BC6
0x1400e9df4  mov     [r15+28h], ebx
0x1400e9df8  xorps   xmm0, xmm0
0x1400e9dfb  movups  xmmword ptr [r15+40h], xmm0
0x1400e9e00  mov     word ptr [r15+42h], 200h
0x1400e9e07  lea     rax, [r15+50h]
0x1400e9e0b  mov     [r15+48h], rax
0x1400e9e0f  mov     qword ptr [rsp+148h+Parameters+0Ch], rbx
0x1400e9e17  mov     dword ptr [rsp+148h+Parameters], 140180h
0x1400e9e22  mov     r14d, 14h
0x1400e9e28  mov     dword ptr [rsp+148h+Parameters+4], 0E80100h
0x1400e9e33  mov     dword ptr [rsp+148h+Parameters+8], 49447356h
0x1400e9e3e  lea     rdx, [rsp+148h+Parameters]; Parameters
0x1400e9e46  mov     rcx, cs:VmsProtocolHandle; NdisHandle
0x1400e9e4d  call    cs:__imp_NdisAllocateNetBufferListPool
0x1400e9e54  nop     dword ptr [rax+rax+00h]
0x1400e9e59  mov     [r15+38h], rax
0x1400e9e5d  test    rax, rax
0x1400e9e60  jnz     short loc_1400E9EA1
0x1400e9e62  lea     r9d, [r14-6]
0x1400e9e66  lea     rax, [rsp+148h+Parameters]
0x1400e9e6e  mov     [rsp+148h+var_118], rax
0x1400e9e73  mov     rax, cs:VmsProtocolHandle
0x1400e9e7a  mov     [rsp+148h+var_120], rax
0x1400e9e7f  lea     rax, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x1400e9e86  mov     [rsp+148h+var_128], rax
0x1400e9e8b  mov     r8d, r14d
0x1400e9e8e  mov     dl, 2
0x1400e9e90  mov     rcx, cs:VmsIfrNicLog
0x1400e9e97  call    WPP_RECORDER_SF_qq
0x1400e9e9c  jmp     loc_1400E9BC6
0x1400e9ea1  lea     rcx, [rdi+268h]; DestinationString
0x1400e9ea8  mov     rdx, r12; SourceString
0x1400e9eab  call    cs:__imp_RtlCopyUnicodeString
0x1400e9eb2  nop     dword ptr [rax+rax+00h]
0x1400e9eb7  lea     rcx, [rdi+508h]; DestinationString
0x1400e9ebe  mov     rdx, r12; SourceString
0x1400e9ec1  call    cs:__imp_RtlCopyUnicodeString
0x1400e9ec8  nop     dword ptr [rax+rax+00h]
0x1400e9ecd  lea     rcx, [rdi+840h]; DestinationString
0x1400e9ed4  mov     rdx, [rsp+148h+SourceString]; SourceString
0x1400e9edc  call    cs:__imp_RtlCopyUnicodeString
0x1400e9ee3  nop     dword ptr [rax+rax+00h]
0x1400e9ee8  lea     rcx, [rdi+0A50h]; DestinationString
0x1400e9eef  mov     rdx, [rsp+148h+var_A0]; SourceString
0x1400e9ef7  call    cs:__imp_RtlCopyUnicodeString
0x1400e9efe  nop     dword ptr [rax+rax+00h]
0x1400e9f03  mov     rax, [rsp+148h+arg_28]
0x1400e9f0b  mov     [rdi+0CD0h], rax
0x1400e9f12  cmp     cs:VmsIsHypercopyEnabled, 0
0x1400e9f19  jz      short loc_1400E9F26
0x1400e9f1b  call    HviIsKernelApertureAvailable
0x1400e9f20  test    al, al
0x1400e9f22  mov     al, bl
0x1400e9f24  jnz     short loc_1400E9F28
0x1400e9f26  mov     al, 1
0x1400e9f28  mov     [rdi+755h], al
0x1400e9f2e  mov     rdx, [rsp+148h+var_98]; SourceString
0x1400e9f36  lea     rcx, [r15+40h]; DestinationString
0x1400e9f3a  call    cs:__imp_RtlCopyUnicodeString
0x1400e9f41  nop     dword ptr [rax+rax+00h]
0x1400e9f46  mov     [rdi+0CF0h], r15
0x1400e9f4d  lea     rax, VmsDIoNicPvtContextCleanup
0x1400e9f54  mov     [rdi+0CF8h], rax
0x1400e9f5b  mov     eax, [rsi]
0x1400e9f5d  mov     [rdi+0D0Eh], eax
0x1400e9f63  movzx   eax, word ptr [rsi+4]
0x1400e9f67  mov     [rdi+0D12h], ax
0x1400e9f6e  lea     r14, [rdi+0D08h]
0x1400e9f75  lea     rax, [rsp+148h+var_C8]
0x1400e9f7d  mov     [rsp+148h+var_128], rax
0x1400e9f82  mov     r9, r14
0x1400e9f85  mov     r8b, [rsp+148h+arg_38]
0x1400e9f8d  mov     rdx, rsi
0x1400e9f90  mov     rcx, rdi
0x1400e9f93  call    VmsOmNicAssignMacAddress
0x1400e9f98  cmp     [rsp+148h+var_C8], bl
0x1400e9f9f  jz      short loc_1400E9FCE
0x1400e9fa1  cmp     [rsp+148h+arg_38], bl
0x1400e9fa8  jnz     short loc_1400E9FCE
0x1400e9faa  mov     dword ptr [rsp+148h+var_110], ebx
0x1400e9fae  mov     [rsp+148h+var_118], rsi
0x1400e9fb3  mov     [rsp+148h+var_120], rdi
0x1400e9fb8  call    WPP_RECORDER_SF_q_MAC_l
0x1400e9fbd  mov     eax, 0C0000018h
0x1400e9fc2  mov     [rsp+148h+var_C0], eax
0x1400e9fc9  jmp     loc_1400E9BD1
0x1400e9fce  mov     ecx, [r14]
0x1400e9fd1  mov     [r14], ecx
0x1400e9fd4  movzx   eax, word ptr [r14+4]
0x1400e9fd9  mov     [rdi+0D0Ch], ax
0x1400e9fe0  mov     [rdi+72Eh], ecx
0x1400e9fe6  movzx   eax, word ptr [r14+4]
0x1400e9feb  mov     [rdi+732h], ax
0x1400e9ff2  mov     eax, [rsi]
0x1400e9ff4  mov     [rdi+838h], eax
0x1400e9ffa  movzx   eax, word ptr [rsi+4]
0x1400e9ffe  mov     [rdi+83Ch], ax
  ... truncated ...
```
