# VmsOmSwitchInfoSet

- ea: `0x1400fcf64`
- end: `0x1400fd1b7`
- name: `VmsOmSwitchInfoSet`
- size: `595`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1400b4828`

## callees

- `0x14002e45c`
- `0x1400370b4`
- `0x14006b084`
- `0x1400a839c`
- `0x1400fcf64`
- `0x140106fa8`
- `0x140107054`
- `0x14018d308`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400fd060`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400fd078`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400fd090`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400fd0a8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400fd060`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400fd078`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400fd090`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400fd0a8`
- `NDIS!NdisReleaseRWLock` at `0x1400fd0d3`
- `NDIS!NdisReleaseRWLock` at `0x1401bcbde`
- `NDIS!NdisReleaseRWLock` at `0x1400fd0d3`
- `NDIS!NdisReleaseRWLock` at `0x1401bcbde`

## pseudocode

```c
__int64 __fastcall VmsOmSwitchInfoSet(char *Src, __int64 a2)
{
  int v4; // r8d
  __int64 v5; // rdx
  char v6; // di
  int v7; // edx
  UNICODE_STRING SourceString; // [rsp+40h] [rbp-48h] BYREF
  UNICODE_STRING v10; // [rsp+50h] [rbp-38h] BYREF
  UNICODE_STRING v11; // [rsp+60h] [rbp-28h] BYREF
  UNICODE_STRING v12; // [rsp+70h] [rbp-18h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+98h] [rbp+10h] BYREF
  unsigned int inited; // [rsp+A0h] [rbp+18h]

  inited = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  SourceString = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  inited = VmsUtilInitUnicodeStringSafe(&SourceString, a2 + 256, 512);
  if ( inited
    || (inited = VmsUtilInitUnicodeStringSafe(&v10, a2 + 768, 2048)) != 0
    || (inited = VmsUtilInitUnicodeStringSafe(&v11, a2 + 2816, 256)) != 0
    || (inited = VmsUtilInitUnicodeStringSafe(&v12, a2 + 3072, 256)) != 0 )
  {
    inited = -1073741811;
  }
  else
  {
    VmsOmObjectLockExclusive(Src, &LockState, 0);
    RtlCopyUnicodeString((PUNICODE_STRING)(Src + 616), &SourceString);
    RtlCopyUnicodeString((PUNICODE_STRING)(Src + 1656), &v10);
    RtlCopyUnicodeString((PUNICODE_STRING)(Src + 3720), &v11);
    RtlCopyUnicodeString((PUNICODE_STRING)(Src + 3992), &v12);
    LOBYTE(v5) = 3;
    v6 = VmsOmObjectPrepareForConfigStore(Src, v5, 1);
    NdisReleaseRWLock(*((PNDIS_RW_LOCK_EX *)Src + 7), &LockState);
    if ( v6 == 1 )
      VmsOmSwitchStoreConfig(Src);
  }
  if ( inited )
  {
    VmsEtwTraceSwitchFailure(&VM_SWITCH_INFO_SET_FAILED, 0, (__int64)(Src + 72), (__int64)(Src + 616));
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_qZd(
      *((_QWORD *)Src + 1137),
      v7,
      20,
      34,
      (__int64)WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids,
      (char)Src,
      (__int64)(Src + 616),
      inited);
  }
  else
  {
    VmsEtwTraceSwitchSuccess(
      (unsigned int)VM_SWITCH_INFO_SET,
      (_DWORD)Src + 72,
      v4,
      (_DWORD)Src + 72,
      (__int64)(Src + 616),
      Src[1232],
      *((_DWORD *)Src + 2286));
  }
  return inited;
}

```

## disassembly

```asm
0x1400fcf64  mov     r11, rsp
0x1400fcf67  mov     [r11+20h], rbx
0x1400fcf6b  mov     [r11+8], rcx
0x1400fcf6f  push    rdi
0x1400fcf70  sub     rsp, 80h
0x1400fcf77  mov     rdi, rdx
0x1400fcf7a  mov     rbx, rcx
0x1400fcf7d  mov     dword ptr [r11+18h], 0
0x1400fcf85  xor     eax, eax
0x1400fcf87  mov     [r11+10h], ax
0x1400fcf8c  mov     [r11+12h], al
0x1400fcf90  xorps   xmm0, xmm0
0x1400fcf93  movups  xmmword ptr [rsp+88h+SourceString.Length], xmm0
0x1400fcf98  xorps   xmm1, xmm1
0x1400fcf9b  movups  xmmword ptr [rsp+88h+var_38.Length], xmm1
0x1400fcfa0  movups  xmmword ptr [rsp+88h+var_28.Length], xmm0
0x1400fcfa5  movups  xmmword ptr [rsp+88h+var_18.Length], xmm1
0x1400fcfaa  mov     r8d, 200h
0x1400fcfb0  add     rdx, 100h
0x1400fcfb7  lea     rcx, [r11-48h]
0x1400fcfbb  call    VmsUtilInitUnicodeStringSafe
0x1400fcfc0  mov     [rsp+88h+arg_10], eax
0x1400fcfc7  test    eax, eax
0x1400fcfc9  jnz     loc_1400FD0F4
0x1400fcfcf  mov     r8d, 800h
0x1400fcfd5  lea     rdx, [rdi+300h]
0x1400fcfdc  lea     rcx, [rsp+88h+var_38]
0x1400fcfe1  call    VmsUtilInitUnicodeStringSafe
0x1400fcfe6  mov     [rsp+88h+arg_10], eax
0x1400fcfed  test    eax, eax
0x1400fcfef  jnz     loc_1400FD0F4
0x1400fcff5  mov     r8d, 100h
0x1400fcffb  lea     rdx, [rdi+0B00h]
0x1400fd002  lea     rcx, [rsp+88h+var_28]
0x1400fd007  call    VmsUtilInitUnicodeStringSafe
0x1400fd00c  mov     [rsp+88h+arg_10], eax
0x1400fd013  test    eax, eax
0x1400fd015  jnz     loc_1400FD0F4
0x1400fd01b  mov     r8d, 100h
0x1400fd021  lea     rdx, [rdi+0C00h]
0x1400fd028  lea     rcx, [rsp+88h+var_18]
0x1400fd02d  call    VmsUtilInitUnicodeStringSafe
0x1400fd032  mov     [rsp+88h+arg_10], eax
0x1400fd039  test    eax, eax
0x1400fd03b  jnz     loc_1400FD0F4
0x1400fd041  xor     r8d, r8d
0x1400fd044  lea     rdx, [rsp+88h+LockState]
0x1400fd04c  mov     rcx, rbx
0x1400fd04f  call    VmsOmObjectLockExclusive
0x1400fd054  lea     rcx, [rbx+268h]; DestinationString
0x1400fd05b  lea     rdx, [rsp+88h+SourceString]; SourceString
0x1400fd060  call    cs:__imp_RtlCopyUnicodeString
0x1400fd067  nop     dword ptr [rax+rax+00h]
0x1400fd06c  lea     rcx, [rbx+678h]; DestinationString
0x1400fd073  lea     rdx, [rsp+88h+var_38]; SourceString
0x1400fd078  call    cs:__imp_RtlCopyUnicodeString
0x1400fd07f  nop     dword ptr [rax+rax+00h]
0x1400fd084  lea     rcx, [rbx+0E88h]; DestinationString
0x1400fd08b  lea     rdx, [rsp+88h+var_28]; SourceString
0x1400fd090  call    cs:__imp_RtlCopyUnicodeString
0x1400fd097  nop     dword ptr [rax+rax+00h]
0x1400fd09c  lea     rcx, [rbx+0F98h]; DestinationString
0x1400fd0a3  lea     rdx, [rsp+88h+var_18]; SourceString
0x1400fd0a8  call    cs:__imp_RtlCopyUnicodeString
0x1400fd0af  nop     dword ptr [rax+rax+00h]
0x1400fd0b4  mov     r8d, 1
0x1400fd0ba  mov     dl, 3
0x1400fd0bc  mov     rcx, rbx
0x1400fd0bf  call    VmsOmObjectPrepareForConfigStore
0x1400fd0c4  mov     dil, al
0x1400fd0c7  lea     rdx, [rsp+88h+LockState]; LockState
0x1400fd0cf  mov     rcx, [rbx+38h]; Lock
0x1400fd0d3  call    cs:__imp_NdisReleaseRWLock
0x1400fd0da  nop     dword ptr [rax+rax+00h]
0x1400fd0df  cmp     dil, 1
0x1400fd0e3  jnz     short loc_1400FD0FF
0x1400fd0e5  mov     edx, 3
0x1400fd0ea  mov     rcx, rbx; Src
0x1400fd0ed  call    VmsOmSwitchStoreConfig
0x1400fd0f2  jmp     short loc_1400FD0FF
0x1400fd0f4  mov     [rsp+88h+arg_10], 0C000000Dh
0x1400fd0ff  lea     rdi, [rbx+268h]
0x1400fd106  lea     rdx, [rbx+48h]
0x1400fd10a  cmp     [rsp+88h+arg_10], 0
0x1400fd112  jnz     short loc_1400FD13F
0x1400fd114  movzx   ecx, byte ptr [rbx+4D0h]
0x1400fd11b  mov     eax, [rbx+23B8h]
0x1400fd121  mov     dword ptr [rsp+88h+var_58], eax
0x1400fd125  mov     dword ptr [rsp+88h+var_60], ecx
0x1400fd129  mov     qword ptr [rsp+88h+var_68], rdi
0x1400fd12e  mov     r9, rdx
0x1400fd131  lea     rcx, VM_SWITCH_INFO_SET
0x1400fd138  call    VmsEtwTraceSwitchSuccess
0x1400fd13d  jmp     short loc_1400FD19E
0x1400fd13f  mov     [rsp+88h+var_58], rdi; __int64
0x1400fd144  mov     [rsp+88h+var_60], rdx; __int64
0x1400fd149  mov     dword ptr [rsp+88h+var_68], 0; char
0x1400fd151  lea     r9, [rsp+88h+arg_10]
0x1400fd159  lea     rcx, VM_SWITCH_INFO_SET_FAILED; EventDescriptor
0x1400fd160  call    VmsEtwTraceSwitchFailure
0x1400fd165  mov     r9d, 22h ; '"'
0x1400fd16b  mov     eax, [rsp+88h+arg_10]
0x1400fd172  mov     [rsp+88h+var_50], eax
0x1400fd176  mov     [rsp+88h+var_58], rdi
0x1400fd17b  mov     [rsp+88h+var_60], rbx
0x1400fd180  lea     rax, WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids
0x1400fd187  mov     qword ptr [rsp+88h+var_68], rax
0x1400fd18c  lea     r8d, [r9-0Eh]
0x1400fd190  mov     dl, 2
0x1400fd192  mov     rcx, [rbx+2388h]
0x1400fd199  call    WPP_RECORDER_SF_qZd
0x1400fd19e  mov     eax, [rsp+88h+arg_10]
0x1400fd1a5  mov     rbx, [rsp+88h+arg_18]
0x1400fd1ad  add     rsp, 80h
0x1400fd1b4  pop     rdi
0x1400fd1b5  retn
0x1401bcbc3  push    rbp
0x1401bcbc5  sub     rsp, 40h
0x1401bcbc9  mov     rbp, rdx
0x1401bcbcc  lea     rdx, [rbp+98h]; LockState
0x1401bcbd3  mov     rcx, [rbp+90h]
0x1401bcbda  mov     rcx, [rcx+38h]; Lock
0x1401bcbde  call    cs:__imp_NdisReleaseRWLock
0x1401bcbe5  nop     dword ptr [rax+rax+00h]
0x1401bcbea  nop
0x1401bcbeb  add     rsp, 40h
0x1401bcbef  pop     rbp
0x1401bcbf0  retn
```
