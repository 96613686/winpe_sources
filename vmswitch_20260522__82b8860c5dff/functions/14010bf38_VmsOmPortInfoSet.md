# VmsOmPortInfoSet

- ea: `0x14010bf38`
- end: `0x14010c568`
- name: `VmsOmPortInfoSet`
- size: `1584`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400d0564`
- `0x140107a74`

## callees

- `0x1400370b4`
- `0x14003a450`
- `0x140046e5c`
- `0x140046f1c`
- `0x14005ddc4`
- `0x14006b084`
- `0x1400f0da8`
- `0x140102e7c`
- `0x140106f38`
- `0x140108050`
- `0x14010b970`
- `0x14010bf38`
- `0x14010e6d0`
- `0x140131b7c`
- `0x1401bbb64`
- `0x1401bbc40`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14010c353`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14010c378`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14010c39d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14010c3c2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14010c49c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14010c353`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14010c378`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14010c39d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14010c3c2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14010c49c`
- `ntoskrnl!KeReleaseMutex` at `0x14010c0c3`
- `ntoskrnl!KeReleaseMutex` at `0x14010c1c9`
- `ntoskrnl!KeReleaseMutex` at `0x14010c0c3`
- `ntoskrnl!KeReleaseMutex` at `0x14010c1c9`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010c19a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010c1f7`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010c19a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010c1f7`
- `NDIS!NdisReleaseRWLock` at `0x14010c4fe`
- `NDIS!NdisReleaseRWLock` at `0x1401bcef1`
- `NDIS!NdisReleaseRWLock` at `0x14010c4fe`
- `NDIS!NdisReleaseRWLock` at `0x1401bcef1`

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
    local_unwind_0(v27, &loc_14010C02E);
  }
  v13 = *((_DWORD *)Src + 544);
  if ( v13 != 1 && (*(_DWORD *)(a2 + 8720) & 0x10) != 0 && *(_DWORD *)(a2 + 3584) )
  {
    inited = -1073741811;
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_d(VmsIfrPortLog, v12, 20, 76, (__int64)WPP_2ef67749ba943892c5000d964b576d2d_Traceguids, v13);
    local_unwind_0(v27, &loc_14010C02E);
  }
  v14 = *(_DWORD *)(a2 + 8720);
  if ( (v14 & 0x80u) != 0 && !*(_DWORD *)(a2 + 8724) && *((_DWORD *)Src + 1593) )
  {
    inited = -1073741811;
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_(VmsIfrPortLog, v12, 20, 77, (__int64)WPP_2ef67749ba943892c5000d964b576d2d_Traceguids);
    LOBYTE(v14) = local_unwind_0(v27, &loc_14010C02E);
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
0x14010bf38  mov     [rsp+arg_10], rbx
0x14010bf3d  mov     [rsp+arg_18], rsi
0x14010bf42  push    rdi
0x14010bf43  push    r12
0x14010bf45  push    r13
0x14010bf47  push    r14
0x14010bf49  push    r15
0x14010bf4b  sub     rsp, 1D0h
0x14010bf52  mov     rax, cs:__security_cookie
0x14010bf59  xor     rax, rsp
0x14010bf5c  mov     [rsp+1F8h+var_38], rax
0x14010bf64  mov     [rsp+1F8h+var_190], rsp
0x14010bf69  mov     rdi, rdx
0x14010bf6c  mov     rsi, rcx
0x14010bf6f  mov     [rsp+1F8h+var_1A8], rcx
0x14010bf74  xor     r14d, r14d
0x14010bf77  mov     [rsp+1F8h+var_1B8], r14d
0x14010bf7c  xor     eax, eax
0x14010bf7e  mov     word ptr [rsp+1F8h+LockState.OldIrql], ax
0x14010bf83  mov     [rsp+1F8h+LockState.Flags], al
0x14010bf87  mov     [rsp+1F8h+var_1B3], r14b
0x14010bf8c  lea     r15, [rcx+18DCh]
0x14010bf93  mov     [rsp+1F8h+var_188], r15
0x14010bf98  mov     al, [r15]
0x14010bf9b  mov     [rsp+1F8h+var_1B2], al
0x14010bf9f  mov     [rsp+1F8h+var_1B4], r14b
0x14010bfa4  xorps   xmm0, xmm0
0x14010bfa7  movups  xmmword ptr [rsp+1F8h+SourceString.Length], xmm0
0x14010bfac  xorps   xmm1, xmm1
0x14010bfaf  movups  xmmword ptr [rsp+1F8h+var_170.Length], xmm1
0x14010bfb7  movups  xmmword ptr [rsp+1F8h+var_160.Length], xmm0
0x14010bfbf  movups  xmmword ptr [rsp+1F8h+var_150.Length], xmm1
0x14010bfc7  xor     edx, edx; Val
0x14010bfc9  mov     r8d, 0FEh; Size
0x14010bfcf  lea     rcx, [rsp+1F8h+var_138]; void *
0x14010bfd7  call    memset
0x14010bfdc  mov     qword ptr [rsp+1F8h+DestinationString.Length], 0FE0000h
0x14010bfe5  lea     rax, [rsp+1F8h+var_138]
0x14010bfed  mov     [rsp+1F8h+DestinationString.Buffer], rax
0x14010bff2  mov     eax, [rdi+2210h]
0x14010bff8  test    al, 2
0x14010bffa  jz      loc_14010C0FF
0x14010c000  mov     r8d, 800h
0x14010c006  lea     rdx, [rdi+400h]
0x14010c00d  lea     rcx, [rsp+1F8h+var_170]
0x14010c015  call    VmsUtilInitUnicodeStringSafe
0x14010c01a  mov     [rsp+1F8h+var_1B8], eax
0x14010c01e  test    eax, eax
0x14010c020  jz      loc_14010C0FF
0x14010c026  mov     [rsp+1F8h+var_1B8], 0C000000Dh
0x14010c02e  xor     r14d, r14d
0x14010c031  cmp     [rsp+1F8h+var_1B4], r14b
0x14010c036  jz      short loc_14010C079
0x14010c038  mov     eax, cs:Microsoft_Windows_Hyper_V_VmSwitchEnableBits
0x14010c03e  test    al, 2
0x14010c040  jz      short loc_14010C079
0x14010c042  mov     rax, [rsp+1F8h+var_188]
0x14010c047  movzx   ecx, byte ptr [rax]
0x14010c04a  movzx   eax, [rsp+1F8h+var_1B2]
0x14010c04f  mov     [rsp+1F8h+var_1C0], 1
0x14010c057  mov     [rsp+1F8h+var_1C8], ecx
0x14010c05b  mov     dword ptr [rsp+1F8h+var_1D0], eax
0x14010c05f  mov     r9, [rsp+1F8h+var_1A8]
0x14010c064  mov     rax, [r9+270h]
0x14010c06b  mov     [rsp+1F8h+Timeout], rax
0x14010c070  mov     r9, [r9+50h]
0x14010c074  call    McTemplateK0zzqqq_EtwWriteTransfer
0x14010c079  mov     ebx, [rsp+1F8h+var_1B8]
0x14010c07d  test    ebx, ebx
0x14010c07f  jns     short loc_14010C0B3
0x14010c081  mov     r9d, 4Eh ; 'N'
0x14010c087  mov     [rsp+1F8h+var_1C8], ebx
0x14010c08b  mov     rax, [rsp+1F8h+var_1A8]
0x14010c090  mov     [rsp+1F8h+var_1D0], rax
0x14010c095  lea     rax, WPP_2ef67749ba943892c5000d964b576d2d_Traceguids
0x14010c09c  mov     [rsp+1F8h+Timeout], rax
0x14010c0a1  lea     r8d, [r9-3Ah]
0x14010c0a5  mov     dl, 2
0x14010c0a7  mov     rcx, cs:VmsIfrPortLog
0x14010c0ae  call    WPP_RECORDER_SF_id
0x14010c0b3  cmp     [rsp+1F8h+var_1B3], r14b
0x14010c0b8  jz      short loc_14010C0CF
0x14010c0ba  xor     edx, edx; Wait
0x14010c0bc  lea     rcx, VmsOmIoctlMutex; Mutex
0x14010c0c3  call    cs:__imp_KeReleaseMutex
0x14010c0ca  nop     dword ptr [rax+rax+00h]
0x14010c0cf  mov     eax, ebx
0x14010c0d1  mov     rcx, [rsp+1F8h+var_38]
0x14010c0d9  xor     rcx, rsp; StackCookie
0x14010c0dc  call    __security_check_cookie
0x14010c0e1  lea     r11, [rsp+1F8h+var_28]
0x14010c0e9  mov     rbx, [r11+40h]
0x14010c0ed  mov     rsi, [r11+48h]
0x14010c0f1  mov     rsp, r11
0x14010c0f4  pop     r15
0x14010c0f6  pop     r14
0x14010c0f8  pop     r13
0x14010c0fa  pop     r12
0x14010c0fc  pop     rdi
0x14010c0fd  retn
0x14010c0ff  mov     eax, [rdi+2210h]
0x14010c105  test    al, 4
0x14010c107  jz      short loc_14010C12F
0x14010c109  mov     r8d, 100h
0x14010c10f  lea     rdx, [rdi+0C00h]
0x14010c116  lea     rcx, [rsp+1F8h+var_160]
0x14010c11e  call    VmsUtilInitUnicodeStringSafe
0x14010c123  mov     [rsp+1F8h+var_1B8], eax
0x14010c127  test    eax, eax
0x14010c129  jnz     loc_14010C026
0x14010c12f  mov     eax, [rdi+2210h]
0x14010c135  test    al, 8
0x14010c137  jz      short loc_14010C15F
0x14010c139  mov     r8d, 100h
0x14010c13f  lea     rdx, [rdi+0D00h]
0x14010c146  lea     rcx, [rsp+1F8h+var_150]
0x14010c14e  call    VmsUtilInitUnicodeStringSafe
0x14010c153  mov     [rsp+1F8h+var_1B8], eax
0x14010c157  test    eax, eax
0x14010c159  jnz     loc_14010C026
0x14010c15f  mov     eax, [rdi+2210h]
0x14010c165  test    al, 40h
0x14010c167  jz      short loc_14010C1DD
0x14010c169  cmp     [rdi+0E08h], r14b
0x14010c170  jz      short loc_14010C1DD
0x14010c172  cmp     [rdi+0E0Ah], r14w
0x14010c17a  ja      short loc_14010C186
0x14010c17c  cmp     [rdi+0E0Ch], r14w
0x14010c184  jbe     short loc_14010C1DD
0x14010c186  mov     [rsp+1F8h+Timeout], r14; Timeout
0x14010c18b  xor     r9d, r9d; Alertable
0x14010c18e  xor     r8d, r8d; WaitMode
0x14010c191  xor     edx, edx; WaitReason
0x14010c193  lea     rcx, VmsOmIoctlMutex; Object
0x14010c19a  call    cs:__imp_KeWaitForSingleObject
0x14010c1a1  nop     dword ptr [rax+rax+00h]
0x14010c1a6  mov     edx, 0Ah
0x14010c1ab  mov     rcx, rsi
0x14010c1ae  call    VmsIovRevokeVFIfAssigned
0x14010c1b3  mov     ebx, eax
0x14010c1b5  mov     [rsp+1F8h+var_1B8], eax
0x14010c1b9  mov     byte ptr [rsi+2EE3h], 1
0x14010c1c0  xor     edx, edx; Wait
0x14010c1c2  lea     rcx, VmsOmIoctlMutex; Mutex
0x14010c1c9  call    cs:__imp_KeReleaseMutex
0x14010c1d0  nop     dword ptr [rax+rax+00h]
0x14010c1d5  test    ebx, ebx
0x14010c1d7  js      loc_14010C02E
0x14010c1dd  mov     r12b, r14b
0x14010c1e0  mov     r13b, r14b
0x14010c1e3  mov     [rsp+1F8h+Timeout], r14; Timeout
0x14010c1e8  xor     r9d, r9d; Alertable
0x14010c1eb  xor     r8d, r8d; WaitMode
0x14010c1ee  xor     edx, edx; WaitReason
0x14010c1f0  lea     rcx, VmsOmIoctlMutex; Object
0x14010c1f7  call    cs:__imp_KeWaitForSingleObject
0x14010c1fe  nop     dword ptr [rax+rax+00h]
0x14010c203  mov     [rsp+1F8h+var_1B3], 1
0x14010c208  mov     eax, [rdi+2210h]
0x14010c20e  test    al, 1
0x14010c210  jz      short loc_14010C238
0x14010c212  mov     r8d, 200h
0x14010c218  lea     rdx, [rdi+200h]
0x14010c21f  lea     rcx, [rsp+1F8h+SourceString]
0x14010c224  call    VmsUtilInitUnicodeStringSafe
0x14010c229  mov     [rsp+1F8h+var_1B8], eax
0x14010c22d  test    eax, eax
0x14010c22f  jnz     loc_14010C026
0x14010c235  mov     r13b, 1
0x14010c238  xor     r8d, r8d
0x14010c23b  lea     rdx, [rsp+1F8h+LockState]
0x14010c240  mov     rcx, rsi
0x14010c243  call    VmsOmObjectLockExclusive
0x14010c248  cmp     dword ptr [rsi+44h], 2
0x14010c24c  jnz     short loc_14010C28B
0x14010c24e  mov     [rsp+1F8h+var_1B8], 0C0000056h
0x14010c256  mov     r9d, 4Bh ; 'K'
0x14010c25c  lea     rax, WPP_2ef67749ba943892c5000d964b576d2d_Traceguids
0x14010c263  mov     [rsp+1F8h+Timeout], rax
0x14010c268  lea     r8d, [r9-37h]
0x14010c26c  mov     dl, 2
0x14010c26e  mov     rcx, cs:VmsIfrPortLog
0x14010c275  call    WPP_RECORDER_SF_
0x14010c27a  lea     rdx, loc_14010C02E
0x14010c281  mov     rcx, [rsp+1F8h+var_190]
0x14010c286  call    _local_unwind_0
0x14010c28b  mov     ecx, [rsi+880h]
0x14010c291  cmp     ecx, 1
0x14010c294  jz      short loc_14010C2EA
0x14010c296  mov     eax, [rdi+2210h]
0x14010c29c  test    al, 10h
0x14010c29e  jz      short loc_14010C2EA
0x14010c2a0  cmp     [rdi+0E00h], r14d
0x14010c2a7  jz      short loc_14010C2EA
0x14010c2a9  mov     [rsp+1F8h+var_1B8], 0C000000Dh
0x14010c2b1  mov     r9d, 4Ch ; 'L'
0x14010c2b7  mov     dword ptr [rsp+1F8h+var_1D0], ecx
0x14010c2bb  lea     rax, WPP_2ef67749ba943892c5000d964b576d2d_Traceguids
0x14010c2c2  mov     [rsp+1F8h+Timeout], rax
0x14010c2c7  lea     r8d, [r9-38h]
0x14010c2cb  mov     dl, 2
0x14010c2cd  mov     rcx, cs:VmsIfrPortLog
0x14010c2d4  call    WPP_RECORDER_SF_d
0x14010c2d9  lea     rdx, loc_14010C02E
0x14010c2e0  mov     rcx, [rsp+1F8h+var_190]
0x14010c2e5  call    _local_unwind_0
0x14010c2ea  mov     eax, [rdi+2210h]
0x14010c2f0  test    al, al
0x14010c2f2  jns     short loc_14010C343
0x14010c2f4  cmp     [rdi+2214h], r14d
0x14010c2fb  jnz     short loc_14010C343
0x14010c2fd  cmp     [rsi+18E4h], r14d
0x14010c304  jz      short loc_14010C343
0x14010c306  mov     [rsp+1F8h+var_1B8], 0C000000Dh
0x14010c30e  mov     r9d, 4Dh ; 'M'
0x14010c314  lea     rax, WPP_2ef67749ba943892c5000d964b576d2d_Traceguids
0x14010c31b  mov     [rsp+1F8h+Timeout], rax
0x14010c320  lea     r8d, [r9-39h]
0x14010c324  mov     dl, 2
0x14010c326  mov     rcx, cs:VmsIfrPortLog
0x14010c32d  call    WPP_RECORDER_SF_
0x14010c332  lea     rdx, loc_14010C02E
0x14010c339  mov     rcx, [rsp+1F8h+var_190]
0x14010c33e  call    _local_unwind_0
0x14010c343  test    al, 1
0x14010c345  jz      short loc_14010C35F
0x14010c347  lea     rcx, [rsi+268h]; DestinationString
0x14010c34e  lea     rdx, [rsp+1F8h+SourceString]; SourceString
0x14010c353  call    cs:__imp_RtlCopyUnicodeString
0x14010c35a  nop     dword ptr [rax+rax+00h]
0x14010c35f  mov     eax, [rdi+2210h]
0x14010c365  test    al, 2
0x14010c367  jz      short loc_14010C384
0x14010c369  lea     rcx, [rsi+0CA8h]; DestinationString
0x14010c370  lea     rdx, [rsp+1F8h+var_170]; SourceString
0x14010c378  call    cs:__imp_RtlCopyUnicodeString
0x14010c37f  nop     dword ptr [rax+rax+00h]
0x14010c384  mov     eax, [rdi+2210h]
0x14010c38a  test    al, 4
0x14010c38c  jz      short loc_14010C3A9
0x14010c38e  lea     rcx, [rsi+14B8h]; DestinationString
0x14010c395  lea     rdx, [rsp+1F8h+var_160]; SourceString
0x14010c39d  call    cs:__imp_RtlCopyUnicodeString
0x14010c3a4  nop     dword ptr [rax+rax+00h]
0x14010c3a9  mov     eax, [rdi+2210h]
0x14010c3af  test    al, 8
0x14010c3b1  jz      short loc_14010C3CE
0x14010c3b3  lea     rcx, [rsi+15C8h]; DestinationString
0x14010c3ba  lea     rdx, [rsp+1F8h+var_150]; SourceString
0x14010c3c2  call    cs:__imp_RtlCopyUnicodeString
0x14010c3c9  nop     dword ptr [rax+rax+00h]
0x14010c3ce  mov     eax, [rdi+2210h]
0x14010c3d4  test    al, 10h
0x14010c3d6  jz      short loc_14010C3E4
0x14010c3d8  mov     eax, [rdi+0E00h]
0x14010c3de  mov     [rsi+18A8h], eax
0x14010c3e4  mov     eax, [rdi+2210h]
0x14010c3ea  test    al, 20h
0x14010c3ec  jz      short loc_14010C3FA
0x14010c3ee  mov     eax, [rdi+0E04h]
0x14010c3f4  mov     [rsi+16D8h], eax
0x14010c3fa  mov     eax, [rdi+2210h]
0x14010c400  test    al, al
0x14010c402  jns     short loc_14010C410
0x14010c404  mov     eax, [rdi+2214h]
0x14010c40a  mov     [rsi+18ACh], eax
0x14010c410  mov     eax, [rdi+2210h]
0x14010c416  test    al, 40h
0x14010c418  jz      short loc_14010C425
0x14010c41a  mov     rdx, rdi
0x14010c41d  mov     rcx, rsi
0x14010c420  call    VmsOmpPortIPSpoofingInfoSet
0x14010c425  test    dword ptr [rdi+2210h], 100h
0x14010c42f  jz      short loc_14010C43D
0x14010c431  mov     al, [rdi+2218h]
0x14010c437  mov     [rsi+18C4h], al
0x14010c43d  test    dword ptr [rdi+2210h], 200h
0x14010c447  jz      short loc_14010C455
0x14010c449  mov     al, [rdi+2219h]
0x14010c44f  mov     [rsi+18C5h], al
0x14010c455  test    dword ptr [rdi+2210h], 400h
0x14010c45f  jz      short loc_14010C46D
0x14010c461  mov     eax, [rdi+221Ch]
0x14010c467  mov     [rsi+18C8h], eax
0x14010c46d  mov     eax, [rdi+2210h]
0x14010c473  bt      eax, 18h
0x14010c477  jnb     short loc_14010C487
0x14010c479  mov     al, [rdi+2220h]
0x14010c47f  mov     [r15], al
0x14010c482  mov     [rsp+1F8h+var_1B4], 1
0x14010c487  mov     rdx, [rsi+4E8h]
0x14010c48e  test    rdx, rdx
0x14010c491  jz      short loc_14010C4A8
0x14010c493  add     rdx, 48h ; 'H'; SourceString
0x14010c497  lea     rcx, [rsp+1F8h+DestinationString]; DestinationString
0x14010c49c  call    cs:__imp_RtlCopyUnicodeString
0x14010c4a3  nop     dword ptr [rax+rax+00h]
0x14010c4a8  xor     edx, edx; Val
0x14010c4aa  mov     r8d, 420h; Size
0x14010c4b0  mov     rcx, [rsi+2930h]; void *
  ... truncated ...
```
