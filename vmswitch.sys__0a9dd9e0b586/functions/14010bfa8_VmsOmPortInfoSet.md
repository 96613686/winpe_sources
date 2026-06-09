# VmsOmPortInfoSet

- ea: `0x14010bfa8`
- end: `0x14010c5d8`
- name: `VmsOmPortInfoSet`
- size: `1584`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400d05d4`
- `0x140107ae4`

## callees

- `0x1400370b4`
- `0x14003a450`
- `0x140046e5c`
- `0x140046f1c`
- `0x14005ddc4`
- `0x14006b084`
- `0x1400f0e18`
- `0x140102eec`
- `0x140106fa8`
- `0x1401080c0`
- `0x14010b9e0`
- `0x14010bfa8`
- `0x14010e740`
- `0x140131bec`
- `0x1401bbbd4`
- `0x1401bbcb0`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14010c3c3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14010c3e8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14010c40d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14010c432`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14010c50c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14010c3c3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14010c3e8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14010c40d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14010c432`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14010c50c`
- `ntoskrnl!KeReleaseMutex` at `0x14010c133`
- `ntoskrnl!KeReleaseMutex` at `0x14010c239`
- `ntoskrnl!KeReleaseMutex` at `0x14010c133`
- `ntoskrnl!KeReleaseMutex` at `0x14010c239`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010c20a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010c267`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010c20a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010c267`
- `NDIS!NdisReleaseRWLock` at `0x14010c56e`
- `NDIS!NdisReleaseRWLock` at `0x1401bcf71`
- `NDIS!NdisReleaseRWLock` at `0x14010c56e`
- `NDIS!NdisReleaseRWLock` at `0x1401bcf71`

## pseudocode

```c
__int64 __fastcall VmsOmPortInfoSet(char *Src, __int64 a2)
{
  _BYTE *v4; // r15
  int v5; // edx
  int v6; // r8d
  unsigned int v7; // ebx
  int v9; // ebx
  char v10; // r12
  char v11; // r13
  int v12; // edx
  int v13; // ecx
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rbx
  __int64 v18; // r15
  __int64 v19; // [rsp+0h] [rbp-1F8h] BYREF
  int inited; // [rsp+40h] [rbp-1B8h]
  char v21; // [rsp+44h] [rbp-1B4h]
  char v22; // [rsp+45h] [rbp-1B3h]
  char v23; // [rsp+46h] [rbp-1B2h]
  struct _LOCK_STATE_EX LockState; // [rsp+48h] [rbp-1B0h] BYREF
  char *v25; // [rsp+50h] [rbp-1A8h]
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-1A0h] BYREF
  __int64 *v27; // [rsp+68h] [rbp-190h]
  char *v28; // [rsp+70h] [rbp-188h]
  UNICODE_STRING SourceString; // [rsp+78h] [rbp-180h] BYREF
  UNICODE_STRING v30; // [rsp+88h] [rbp-170h] BYREF
  UNICODE_STRING v31; // [rsp+98h] [rbp-160h] BYREF
  UNICODE_STRING v32; // [rsp+A8h] [rbp-150h] BYREF
  _BYTE v33[256]; // [rsp+C0h] [rbp-138h] BYREF

  v27 = &v19;
  v25 = Src;
  inited = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v22 = 0;
  v4 = Src + 6364;
  v28 = Src + 6364;
  v23 = Src[6364];
  v21 = 0;
  SourceString = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  memset(v33, 0, 0xFEu);
  *(_QWORD *)&DestinationString.Length = 16646144;
  DestinationString.Buffer = (wchar_t *)v33;
  if ( (*(_DWORD *)(a2 + 8720) & 2) != 0 )
  {
    inited = VmsUtilInitUnicodeStringSafe(&v30, a2 + 1024, 2048);
    if ( inited )
      goto LABEL_3;
  }
  if ( (*(_DWORD *)(a2 + 8720) & 4) != 0 )
  {
    inited = VmsUtilInitUnicodeStringSafe(&v31, a2 + 3072, 256);
    if ( inited )
      goto LABEL_3;
  }
  if ( (*(_DWORD *)(a2 + 8720) & 8) != 0 )
  {
    inited = VmsUtilInitUnicodeStringSafe(&v32, a2 + 3328, 256);
    if ( inited )
      goto LABEL_3;
  }
  if ( (*(_DWORD *)(a2 + 8720) & 0x40) != 0 && *(_BYTE *)(a2 + 3592) && (*(_WORD *)(a2 + 3594) || *(_WORD *)(a2 + 3596)) )
  {
    KeWaitForSingleObject(&VmsOmIoctlMutex, Executive, 0, 0, 0);
    v9 = VmsIovRevokeVFIfAssigned(Src, 10);
    inited = v9;
    Src[12003] = 1;
    KeReleaseMutex(&VmsOmIoctlMutex, 0);
    if ( v9 < 0 )
      goto LABEL_4;
  }
  v10 = 0;
  v11 = 0;
  KeWaitForSingleObject(&VmsOmIoctlMutex, Executive, 0, 0, 0);
  v22 = 1;
  if ( (*(_DWORD *)(a2 + 8720) & 1) != 0 )
  {
    inited = VmsUtilInitUnicodeStringSafe(&SourceString, a2 + 512, 512);
    if ( !inited )
    {
      v11 = 1;
      goto LABEL_24;
    }
LABEL_3:
    inited = -1073741811;
    goto LABEL_4;
  }
LABEL_24:
  VmsOmObjectLockExclusive(Src, &LockState, 0);
  if ( *((_DWORD *)Src + 17) == 2 )
  {
    inited = -1073741738;
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_(VmsIfrPortLog, v12, 20, 75, (__int64)WPP_2ef67749ba943892c5000d964b576d2d_Traceguids);
    local_unwind_0(v27, &loc_14010C09E);
  }
  v13 = *((_DWORD *)Src + 544);
  if ( v13 != 1 && (*(_DWORD *)(a2 + 8720) & 0x10) != 0 && *(_DWORD *)(a2 + 3584) )
  {
    inited = -1073741811;
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_d(VmsIfrPortLog, v12, 20, 76, (__int64)WPP_2ef67749ba943892c5000d964b576d2d_Traceguids, v13);
    local_unwind_0(v27, &loc_14010C09E);
  }
  v14 = *(_DWORD *)(a2 + 8720);
  if ( (v14 & 0x80u) != 0 && !*(_DWORD *)(a2 + 8724) && *((_DWORD *)Src + 1593) )
  {
    inited = -1073741811;
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_(VmsIfrPortLog, v12, 20, 77, (__int64)WPP_2ef67749ba943892c5000d964b576d2d_Traceguids);
    LOBYTE(v14) = local_unwind_0(v27, &loc_14010C09E);
  }
  if ( (v14 & 1) != 0 )
    RtlCopyUnicodeString((PUNICODE_STRING)(Src + 616), &SourceString);
  if ( (*(_DWORD *)(a2 + 8720) & 2) != 0 )
    RtlCopyUnicodeString((PUNICODE_STRING)(Src + 3240), &v30);
  if ( (*(_DWORD *)(a2 + 8720) & 4) != 0 )
    RtlCopyUnicodeString((PUNICODE_STRING)(Src + 5304), &v31);
  if ( (*(_DWORD *)(a2 + 8720) & 8) != 0 )
    RtlCopyUnicodeString((PUNICODE_STRING)(Src + 5576), &v32);
  if ( (*(_DWORD *)(a2 + 8720) & 0x10) != 0 )
    *((_DWORD *)Src + 1578) = *(_DWORD *)(a2 + 3584);
  if ( (*(_DWORD *)(a2 + 8720) & 0x20) != 0 )
    *((_DWORD *)Src + 1462) = *(_DWORD *)(a2 + 3588);
  if ( (*(_DWORD *)(a2 + 8720) & 0x80u) != 0 )
    *((_DWORD *)Src + 1579) = *(_DWORD *)(a2 + 8724);
  if ( (*(_DWORD *)(a2 + 8720) & 0x40) != 0 )
    VmsOmpPortIPSpoofingInfoSet(Src, a2);
  if ( (*(_DWORD *)(a2 + 8720) & 0x100) != 0 )
    Src[6340] = *(_BYTE *)(a2 + 8728);
  if ( (*(_DWORD *)(a2 + 8720) & 0x200) != 0 )
    Src[6341] = *(_BYTE *)(a2 + 8729);
  if ( (*(_DWORD *)(a2 + 8720) & 0x400) != 0 )
    *((_DWORD *)Src + 1586) = *(_DWORD *)(a2 + 8732);
  if ( (*(_DWORD *)(a2 + 8720) & 0x1000000) != 0 )
  {
    *v4 = *(_BYTE *)(a2 + 8736);
    v21 = 1;
  }
  v15 = *((_QWORD *)Src + 157);
  if ( v15 )
    RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)(v15 + 72));
  memset(*((void **)Src + 1318), 0, 0x420u);
  VmsOmPortCopyDataUnsafe(Src, *((_QWORD *)Src + 1318));
  v17 = *((_QWORD *)Src + 155);
  v18 = *(_QWORD *)(v17 + 4264);
  if ( Src[1228] )
  {
    LOBYTE(v16) = 4;
    v10 = VmsOmObjectPrepareForConfigStore(Src, v16, 1);
  }
  NdisReleaseRWLock(*((PNDIS_RW_LOCK_EX *)Src + 7), &LockState);
  if ( v11 )
    VmsEptProcessPublicOid(v17, v18, v6, 66197, *((_QWORD *)Src + 1318), 1056);
  if ( DestinationString.Length )
    VmsOmNicSetPortInfo(&DestinationString, Src, a2);
  if ( v10 == 1 )
    VmsOmpPortStoreConfig(Src);
LABEL_4:
  if ( v21 && (Microsoft_Windows_Hyper_V_VmSwitchEnableBits & 2) != 0 )
    McTemplateK0zzqqq_EtwWriteTransfer(
      (unsigned __int8)*v28,
      v5,
      v6,
      *((_QWORD *)v25 + 10),
      *((_QWORD *)v25 + 78),
      v23,
      *v28,
      1);
  v7 = inited;
  if ( inited < 0 )
  {
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_id(
      VmsIfrPortLog,
      v5,
      20,
      78,
      (__int64)WPP_2ef67749ba943892c5000d964b576d2d_Traceguids,
      (char)v25,
      inited);
  }
  if ( v22 )
    KeReleaseMutex(&VmsOmIoctlMutex, 0);
  return v7;
}

```

## disassembly

```asm
0x14010bfa8  mov     [rsp+arg_10], rbx
0x14010bfad  mov     [rsp+arg_18], rsi
0x14010bfb2  push    rdi
0x14010bfb3  push    r12
0x14010bfb5  push    r13
0x14010bfb7  push    r14
0x14010bfb9  push    r15
0x14010bfbb  sub     rsp, 1D0h
0x14010bfc2  mov     rax, cs:__security_cookie
0x14010bfc9  xor     rax, rsp
0x14010bfcc  mov     [rsp+1F8h+var_38], rax
0x14010bfd4  mov     [rsp+1F8h+var_190], rsp
0x14010bfd9  mov     rdi, rdx
0x14010bfdc  mov     rsi, rcx
0x14010bfdf  mov     [rsp+1F8h+var_1A8], rcx
0x14010bfe4  xor     r14d, r14d
0x14010bfe7  mov     [rsp+1F8h+var_1B8], r14d
0x14010bfec  xor     eax, eax
0x14010bfee  mov     word ptr [rsp+1F8h+LockState.OldIrql], ax
0x14010bff3  mov     [rsp+1F8h+LockState.Flags], al
0x14010bff7  mov     [rsp+1F8h+var_1B3], r14b
0x14010bffc  lea     r15, [rcx+18DCh]
0x14010c003  mov     [rsp+1F8h+var_188], r15
0x14010c008  mov     al, [r15]
0x14010c00b  mov     [rsp+1F8h+var_1B2], al
0x14010c00f  mov     [rsp+1F8h+var_1B4], r14b
0x14010c014  xorps   xmm0, xmm0
0x14010c017  movups  xmmword ptr [rsp+1F8h+SourceString.Length], xmm0
0x14010c01c  xorps   xmm1, xmm1
0x14010c01f  movups  xmmword ptr [rsp+1F8h+var_170.Length], xmm1
0x14010c027  movups  xmmword ptr [rsp+1F8h+var_160.Length], xmm0
0x14010c02f  movups  xmmword ptr [rsp+1F8h+var_150.Length], xmm1
0x14010c037  xor     edx, edx; Val
0x14010c039  mov     r8d, 0FEh; Size
0x14010c03f  lea     rcx, [rsp+1F8h+var_138]; void *
0x14010c047  call    memset
0x14010c04c  mov     qword ptr [rsp+1F8h+DestinationString.Length], 0FE0000h
0x14010c055  lea     rax, [rsp+1F8h+var_138]
0x14010c05d  mov     [rsp+1F8h+DestinationString.Buffer], rax
0x14010c062  mov     eax, [rdi+2210h]
0x14010c068  test    al, 2
0x14010c06a  jz      loc_14010C16F
0x14010c070  mov     r8d, 800h
0x14010c076  lea     rdx, [rdi+400h]
0x14010c07d  lea     rcx, [rsp+1F8h+var_170]
0x14010c085  call    VmsUtilInitUnicodeStringSafe
0x14010c08a  mov     [rsp+1F8h+var_1B8], eax
0x14010c08e  test    eax, eax
0x14010c090  jz      loc_14010C16F
0x14010c096  mov     [rsp+1F8h+var_1B8], 0C000000Dh
0x14010c09e  xor     r14d, r14d
0x14010c0a1  cmp     [rsp+1F8h+var_1B4], r14b
0x14010c0a6  jz      short loc_14010C0E9
0x14010c0a8  mov     eax, cs:Microsoft_Windows_Hyper_V_VmSwitchEnableBits
0x14010c0ae  test    al, 2
0x14010c0b0  jz      short loc_14010C0E9
0x14010c0b2  mov     rax, [rsp+1F8h+var_188]
0x14010c0b7  movzx   ecx, byte ptr [rax]
0x14010c0ba  movzx   eax, [rsp+1F8h+var_1B2]
0x14010c0bf  mov     [rsp+1F8h+var_1C0], 1
0x14010c0c7  mov     [rsp+1F8h+var_1C8], ecx
0x14010c0cb  mov     dword ptr [rsp+1F8h+var_1D0], eax
0x14010c0cf  mov     r9, [rsp+1F8h+var_1A8]
0x14010c0d4  mov     rax, [r9+270h]
0x14010c0db  mov     [rsp+1F8h+Timeout], rax
0x14010c0e0  mov     r9, [r9+50h]
0x14010c0e4  call    McTemplateK0zzqqq_EtwWriteTransfer
0x14010c0e9  mov     ebx, [rsp+1F8h+var_1B8]
0x14010c0ed  test    ebx, ebx
0x14010c0ef  jns     short loc_14010C123
0x14010c0f1  mov     r9d, 4Eh ; 'N'
0x14010c0f7  mov     [rsp+1F8h+var_1C8], ebx
0x14010c0fb  mov     rax, [rsp+1F8h+var_1A8]
0x14010c100  mov     [rsp+1F8h+var_1D0], rax
0x14010c105  lea     rax, WPP_2ef67749ba943892c5000d964b576d2d_Traceguids
0x14010c10c  mov     [rsp+1F8h+Timeout], rax
0x14010c111  lea     r8d, [r9-3Ah]
0x14010c115  mov     dl, 2
0x14010c117  mov     rcx, cs:VmsIfrPortLog
0x14010c11e  call    WPP_RECORDER_SF_id
0x14010c123  cmp     [rsp+1F8h+var_1B3], r14b
0x14010c128  jz      short loc_14010C13F
0x14010c12a  xor     edx, edx; Wait
0x14010c12c  lea     rcx, VmsOmIoctlMutex; Mutex
0x14010c133  call    cs:__imp_KeReleaseMutex
0x14010c13a  nop     dword ptr [rax+rax+00h]
0x14010c13f  mov     eax, ebx
0x14010c141  mov     rcx, [rsp+1F8h+var_38]
0x14010c149  xor     rcx, rsp; StackCookie
0x14010c14c  call    __security_check_cookie
0x14010c151  lea     r11, [rsp+1F8h+var_28]
0x14010c159  mov     rbx, [r11+40h]
0x14010c15d  mov     rsi, [r11+48h]
0x14010c161  mov     rsp, r11
0x14010c164  pop     r15
0x14010c166  pop     r14
0x14010c168  pop     r13
0x14010c16a  pop     r12
0x14010c16c  pop     rdi
0x14010c16d  retn
0x14010c16f  mov     eax, [rdi+2210h]
0x14010c175  test    al, 4
0x14010c177  jz      short loc_14010C19F
0x14010c179  mov     r8d, 100h
0x14010c17f  lea     rdx, [rdi+0C00h]
0x14010c186  lea     rcx, [rsp+1F8h+var_160]
0x14010c18e  call    VmsUtilInitUnicodeStringSafe
0x14010c193  mov     [rsp+1F8h+var_1B8], eax
0x14010c197  test    eax, eax
0x14010c199  jnz     loc_14010C096
0x14010c19f  mov     eax, [rdi+2210h]
0x14010c1a5  test    al, 8
0x14010c1a7  jz      short loc_14010C1CF
0x14010c1a9  mov     r8d, 100h
0x14010c1af  lea     rdx, [rdi+0D00h]
0x14010c1b6  lea     rcx, [rsp+1F8h+var_150]
0x14010c1be  call    VmsUtilInitUnicodeStringSafe
0x14010c1c3  mov     [rsp+1F8h+var_1B8], eax
0x14010c1c7  test    eax, eax
0x14010c1c9  jnz     loc_14010C096
0x14010c1cf  mov     eax, [rdi+2210h]
0x14010c1d5  test    al, 40h
0x14010c1d7  jz      short loc_14010C24D
0x14010c1d9  cmp     [rdi+0E08h], r14b
0x14010c1e0  jz      short loc_14010C24D
0x14010c1e2  cmp     [rdi+0E0Ah], r14w
0x14010c1ea  ja      short loc_14010C1F6
0x14010c1ec  cmp     [rdi+0E0Ch], r14w
0x14010c1f4  jbe     short loc_14010C24D
0x14010c1f6  mov     [rsp+1F8h+Timeout], r14; Timeout
0x14010c1fb  xor     r9d, r9d; Alertable
0x14010c1fe  xor     r8d, r8d; WaitMode
0x14010c201  xor     edx, edx; WaitReason
0x14010c203  lea     rcx, VmsOmIoctlMutex; Object
0x14010c20a  call    cs:__imp_KeWaitForSingleObject
0x14010c211  nop     dword ptr [rax+rax+00h]
0x14010c216  mov     edx, 0Ah
0x14010c21b  mov     rcx, rsi
0x14010c21e  call    VmsIovRevokeVFIfAssigned
0x14010c223  mov     ebx, eax
0x14010c225  mov     [rsp+1F8h+var_1B8], eax
0x14010c229  mov     byte ptr [rsi+2EE3h], 1
0x14010c230  xor     edx, edx; Wait
0x14010c232  lea     rcx, VmsOmIoctlMutex; Mutex
0x14010c239  call    cs:__imp_KeReleaseMutex
0x14010c240  nop     dword ptr [rax+rax+00h]
0x14010c245  test    ebx, ebx
0x14010c247  js      loc_14010C09E
0x14010c24d  mov     r12b, r14b
0x14010c250  mov     r13b, r14b
0x14010c253  mov     [rsp+1F8h+Timeout], r14; Timeout
0x14010c258  xor     r9d, r9d; Alertable
0x14010c25b  xor     r8d, r8d; WaitMode
0x14010c25e  xor     edx, edx; WaitReason
0x14010c260  lea     rcx, VmsOmIoctlMutex; Object
0x14010c267  call    cs:__imp_KeWaitForSingleObject
0x14010c26e  nop     dword ptr [rax+rax+00h]
0x14010c273  mov     [rsp+1F8h+var_1B3], 1
0x14010c278  mov     eax, [rdi+2210h]
0x14010c27e  test    al, 1
0x14010c280  jz      short loc_14010C2A8
0x14010c282  mov     r8d, 200h
0x14010c288  lea     rdx, [rdi+200h]
0x14010c28f  lea     rcx, [rsp+1F8h+SourceString]
0x14010c294  call    VmsUtilInitUnicodeStringSafe
0x14010c299  mov     [rsp+1F8h+var_1B8], eax
0x14010c29d  test    eax, eax
0x14010c29f  jnz     loc_14010C096
0x14010c2a5  mov     r13b, 1
0x14010c2a8  xor     r8d, r8d
0x14010c2ab  lea     rdx, [rsp+1F8h+LockState]
0x14010c2b0  mov     rcx, rsi
0x14010c2b3  call    VmsOmObjectLockExclusive
0x14010c2b8  cmp     dword ptr [rsi+44h], 2
0x14010c2bc  jnz     short loc_14010C2FB
0x14010c2be  mov     [rsp+1F8h+var_1B8], 0C0000056h
0x14010c2c6  mov     r9d, 4Bh ; 'K'
0x14010c2cc  lea     rax, WPP_2ef67749ba943892c5000d964b576d2d_Traceguids
0x14010c2d3  mov     [rsp+1F8h+Timeout], rax
0x14010c2d8  lea     r8d, [r9-37h]
0x14010c2dc  mov     dl, 2
0x14010c2de  mov     rcx, cs:VmsIfrPortLog
0x14010c2e5  call    WPP_RECORDER_SF_
0x14010c2ea  lea     rdx, loc_14010C09E
0x14010c2f1  mov     rcx, [rsp+1F8h+var_190]
0x14010c2f6  call    _local_unwind_0
0x14010c2fb  mov     ecx, [rsi+880h]
0x14010c301  cmp     ecx, 1
0x14010c304  jz      short loc_14010C35A
0x14010c306  mov     eax, [rdi+2210h]
0x14010c30c  test    al, 10h
0x14010c30e  jz      short loc_14010C35A
0x14010c310  cmp     [rdi+0E00h], r14d
0x14010c317  jz      short loc_14010C35A
0x14010c319  mov     [rsp+1F8h+var_1B8], 0C000000Dh
0x14010c321  mov     r9d, 4Ch ; 'L'
0x14010c327  mov     dword ptr [rsp+1F8h+var_1D0], ecx
0x14010c32b  lea     rax, WPP_2ef67749ba943892c5000d964b576d2d_Traceguids
0x14010c332  mov     [rsp+1F8h+Timeout], rax
0x14010c337  lea     r8d, [r9-38h]
0x14010c33b  mov     dl, 2
0x14010c33d  mov     rcx, cs:VmsIfrPortLog
0x14010c344  call    WPP_RECORDER_SF_d
0x14010c349  lea     rdx, loc_14010C09E
0x14010c350  mov     rcx, [rsp+1F8h+var_190]
0x14010c355  call    _local_unwind_0
0x14010c35a  mov     eax, [rdi+2210h]
0x14010c360  test    al, al
0x14010c362  jns     short loc_14010C3B3
0x14010c364  cmp     [rdi+2214h], r14d
0x14010c36b  jnz     short loc_14010C3B3
0x14010c36d  cmp     [rsi+18E4h], r14d
0x14010c374  jz      short loc_14010C3B3
0x14010c376  mov     [rsp+1F8h+var_1B8], 0C000000Dh
0x14010c37e  mov     r9d, 4Dh ; 'M'
0x14010c384  lea     rax, WPP_2ef67749ba943892c5000d964b576d2d_Traceguids
0x14010c38b  mov     [rsp+1F8h+Timeout], rax
0x14010c390  lea     r8d, [r9-39h]
0x14010c394  mov     dl, 2
0x14010c396  mov     rcx, cs:VmsIfrPortLog
0x14010c39d  call    WPP_RECORDER_SF_
0x14010c3a2  lea     rdx, loc_14010C09E
0x14010c3a9  mov     rcx, [rsp+1F8h+var_190]
0x14010c3ae  call    _local_unwind_0
0x14010c3b3  test    al, 1
0x14010c3b5  jz      short loc_14010C3CF
0x14010c3b7  lea     rcx, [rsi+268h]; DestinationString
0x14010c3be  lea     rdx, [rsp+1F8h+SourceString]; SourceString
0x14010c3c3  call    cs:__imp_RtlCopyUnicodeString
0x14010c3ca  nop     dword ptr [rax+rax+00h]
0x14010c3cf  mov     eax, [rdi+2210h]
0x14010c3d5  test    al, 2
0x14010c3d7  jz      short loc_14010C3F4
0x14010c3d9  lea     rcx, [rsi+0CA8h]; DestinationString
0x14010c3e0  lea     rdx, [rsp+1F8h+var_170]; SourceString
0x14010c3e8  call    cs:__imp_RtlCopyUnicodeString
0x14010c3ef  nop     dword ptr [rax+rax+00h]
0x14010c3f4  mov     eax, [rdi+2210h]
0x14010c3fa  test    al, 4
0x14010c3fc  jz      short loc_14010C419
0x14010c3fe  lea     rcx, [rsi+14B8h]; DestinationString
0x14010c405  lea     rdx, [rsp+1F8h+var_160]; SourceString
0x14010c40d  call    cs:__imp_RtlCopyUnicodeString
0x14010c414  nop     dword ptr [rax+rax+00h]
0x14010c419  mov     eax, [rdi+2210h]
0x14010c41f  test    al, 8
0x14010c421  jz      short loc_14010C43E
0x14010c423  lea     rcx, [rsi+15C8h]; DestinationString
0x14010c42a  lea     rdx, [rsp+1F8h+var_150]; SourceString
0x14010c432  call    cs:__imp_RtlCopyUnicodeString
0x14010c439  nop     dword ptr [rax+rax+00h]
0x14010c43e  mov     eax, [rdi+2210h]
0x14010c444  test    al, 10h
0x14010c446  jz      short loc_14010C454
0x14010c448  mov     eax, [rdi+0E00h]
0x14010c44e  mov     [rsi+18A8h], eax
0x14010c454  mov     eax, [rdi+2210h]
0x14010c45a  test    al, 20h
0x14010c45c  jz      short loc_14010C46A
0x14010c45e  mov     eax, [rdi+0E04h]
0x14010c464  mov     [rsi+16D8h], eax
0x14010c46a  mov     eax, [rdi+2210h]
0x14010c470  test    al, al
0x14010c472  jns     short loc_14010C480
0x14010c474  mov     eax, [rdi+2214h]
0x14010c47a  mov     [rsi+18ACh], eax
0x14010c480  mov     eax, [rdi+2210h]
0x14010c486  test    al, 40h
0x14010c488  jz      short loc_14010C495
0x14010c48a  mov     rdx, rdi
0x14010c48d  mov     rcx, rsi
0x14010c490  call    VmsOmpPortIPSpoofingInfoSet
0x14010c495  test    dword ptr [rdi+2210h], 100h
0x14010c49f  jz      short loc_14010C4AD
0x14010c4a1  mov     al, [rdi+2218h]
0x14010c4a7  mov     [rsi+18C4h], al
0x14010c4ad  test    dword ptr [rdi+2210h], 200h
0x14010c4b7  jz      short loc_14010C4C5
0x14010c4b9  mov     al, [rdi+2219h]
0x14010c4bf  mov     [rsi+18C5h], al
0x14010c4c5  test    dword ptr [rdi+2210h], 400h
0x14010c4cf  jz      short loc_14010C4DD
0x14010c4d1  mov     eax, [rdi+221Ch]
0x14010c4d7  mov     [rsi+18C8h], eax
0x14010c4dd  mov     eax, [rdi+2210h]
0x14010c4e3  bt      eax, 18h
0x14010c4e7  jnb     short loc_14010C4F7
0x14010c4e9  mov     al, [rdi+2220h]
0x14010c4ef  mov     [r15], al
0x14010c4f2  mov     [rsp+1F8h+var_1B4], 1
0x14010c4f7  mov     rdx, [rsi+4E8h]
0x14010c4fe  test    rdx, rdx
0x14010c501  jz      short loc_14010C518
0x14010c503  add     rdx, 48h ; 'H'; SourceString
0x14010c507  lea     rcx, [rsp+1F8h+DestinationString]; DestinationString
0x14010c50c  call    cs:__imp_RtlCopyUnicodeString
0x14010c513  nop     dword ptr [rax+rax+00h]
0x14010c518  xor     edx, edx; Val
0x14010c51a  mov     r8d, 420h; Size
0x14010c520  mov     rcx, [rsi+2930h]; void *
  ... truncated ...
```
