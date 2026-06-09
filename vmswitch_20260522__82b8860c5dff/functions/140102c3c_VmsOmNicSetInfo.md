# VmsOmNicSetInfo

- ea: `0x140102c3c`
- end: `0x140102e75`
- name: `VmsOmNicSetInfo`
- size: `569`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x1400c1b64`

## callees

- `0x14001484c`
- `0x1400313cc`
- `0x1400370b4`
- `0x140066bec`
- `0x14006b084`
- `0x14007a254`
- `0x14008c82c`
- `0x1400fe6f0`
- `0x140102c3c`
- `0x140106848`
- `0x140106f38`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140102d09`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140102d21`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140102d09`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140102d21`
- `ntoskrnl!KeReleaseMutex` at `0x140102df4`
- `ntoskrnl!KeReleaseMutex` at `0x140102df4`
- `ntoskrnl!KeWaitForSingleObject` at `0x140102cd5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140102cd5`
- `NDIS!NdisReleaseRWLock` at `0x140102d7b`
- `NDIS!NdisReleaseRWLock` at `0x140102daf`
- `NDIS!NdisReleaseRWLock` at `0x1401bcdbc`
- `NDIS!NdisReleaseRWLock` at `0x140102d7b`
- `NDIS!NdisReleaseRWLock` at `0x140102daf`
- `NDIS!NdisReleaseRWLock` at `0x1401bcdbc`

## pseudocode

```c
__int64 __fastcall VmsOmNicSetInfo(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  __int64 v4; // rdx
  int NicInitialized; // edi
  char v6; // r14
  __int64 v7; // r13
  __int64 v8; // rsi
  void *v9; // r12
  __int64 v10; // rdx
  __int64 v11; // r8
  UNICODE_STRING SourceString; // [rsp+40h] [rbp-48h] BYREF
  struct _LOCK_STATE_EX v14; // [rsp+98h] [rbp+10h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v16; // [rsp+A8h] [rbp+20h] BYREF

  v3 = 0;
  v16 = 0;
  *(_WORD *)&v14.OldIrql = 0;
  v14.Flags = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  SourceString = 0;
  if ( (int)VmsUtilInitUnicodeStringSafe(&SourceString, a2 + 256, 512) < 0 )
  {
    NicInitialized = -1073741811;
LABEL_14:
    LOBYTE(v4) = 2;
    WPP_RECORDER_SF_Zd(
      VmsIfrNicLog,
      v4,
      20,
      32,
      (__int64)WPP_bda91bcb57e433144f485e69e8239e42_Traceguids,
      a1,
      NicInitialized);
    goto LABEL_15;
  }
  NicInitialized = VmsOmFindNicInitialized(a1, 9, &v16);
  if ( NicInitialized )
  {
    v3 = v16;
  }
  else
  {
    v6 = 0;
    LODWORD(v7) = 0;
    v8 = 0;
    v9 = 0;
    KeWaitForSingleObject(&VmsOmIoctlMutex, Executive, 0, 0, 0);
    v3 = v16;
    VmsOmObjectLockExclusive(v16, &v14, 0);
    RtlCopyUnicodeString((PUNICODE_STRING)(v3 + 616), &SourceString);
    RtlCopyUnicodeString((PUNICODE_STRING)(v3 + 1288), &SourceString);
    if ( (unsigned int)(*(_DWORD *)(v3 + 1248) - 1) <= 2 )
    {
      v9 = *(void **)(v3 + 4040);
      VmsOmNicCopyDataUnsafe(v3, 0, v9);
      v8 = *(_QWORD *)(v3 + 1888);
      LOBYTE(v11) = 1;
      VmsOmObjectLockShared(v8, &LockState, v11);
      v7 = *(_QWORD *)(v8 + 4264);
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v8 + 56), &LockState);
    }
    if ( *(_BYTE *)(v3 + 1876) == 1 )
    {
      LOBYTE(v10) = 10;
      v6 = VmsOmObjectPrepareForConfigStore(v3, v10, 1);
    }
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v3 + 56), &v14);
    if ( v8 )
      VmsOmNicSendMultipleOids(v3, v8, v7, 66196, v9, 1, 0);
    KeReleaseMutex(&VmsOmIoctlMutex, 0);
    if ( v6 == 1 )
      VmsOmNicStoreConfig(v3, (const UNICODE_STRING *)(v3 + 72), 10);
  }
  if ( NicInitialized < 0 )
    goto LABEL_14;
LABEL_15:
  if ( v3 )
  {
    LOBYTE(v4) = 9;
    VmsOmpObjectDereference(v3, v4);
  }
  return (unsigned int)NicInitialized;
}

```

## disassembly

```asm
0x140102c3c  mov     r11, rsp
0x140102c3f  push    rbx
0x140102c40  push    rsi
0x140102c41  push    rdi
0x140102c42  push    r12
0x140102c44  push    r13
0x140102c46  push    r14
0x140102c48  push    r15
0x140102c4a  sub     rsp, 50h
0x140102c4e  mov     r15, rcx
0x140102c51  xor     ebx, ebx
0x140102c53  mov     [r11+20h], rbx
0x140102c57  xor     eax, eax
0x140102c59  mov     [r11+10h], ax
0x140102c5e  mov     [r11+12h], al
0x140102c62  mov     [r11+18h], ax
0x140102c67  mov     [r11+1Ah], al
0x140102c6b  xorps   xmm0, xmm0
0x140102c6e  movups  xmmword ptr [rsp+88h+SourceString.Length], xmm0
0x140102c73  mov     r8d, 200h
0x140102c79  add     rdx, 100h
0x140102c80  lea     rcx, [r11-48h]
0x140102c84  call    VmsUtilInitUnicodeStringSafe
0x140102c89  test    eax, eax
0x140102c8b  jns     short loc_140102C97
0x140102c8d  mov     edi, 0C000000Dh
0x140102c92  jmp     loc_140102E26
0x140102c97  lea     r8, [rsp+88h+arg_18]
0x140102c9f  mov     edx, 9
0x140102ca4  mov     rcx, r15
0x140102ca7  call    VmsOmFindNicInitialized
0x140102cac  mov     edi, eax
0x140102cae  test    eax, eax
0x140102cb0  jnz     loc_140102E1A
0x140102cb6  xor     r14b, r14b
0x140102cb9  xor     r13d, r13d
0x140102cbc  xor     esi, esi
0x140102cbe  xor     r12d, r12d
0x140102cc1  mov     [rsp+88h+Timeout], rbx; Timeout
0x140102cc6  xor     r9d, r9d; Alertable
0x140102cc9  xor     r8d, r8d; WaitMode
0x140102ccc  xor     edx, edx; WaitReason
0x140102cce  lea     rcx, VmsOmIoctlMutex; Object
0x140102cd5  call    cs:__imp_KeWaitForSingleObject
0x140102cdc  nop     dword ptr [rax+rax+00h]
0x140102ce1  nop
0x140102ce2  xor     r8d, r8d
0x140102ce5  lea     rdx, [rsp+88h+arg_8]
0x140102ced  mov     rbx, [rsp+88h+arg_18]
0x140102cf5  mov     rcx, rbx
0x140102cf8  call    VmsOmObjectLockExclusive
0x140102cfd  lea     rcx, [rbx+268h]; DestinationString
0x140102d04  lea     rdx, [rsp+88h+SourceString]; SourceString
0x140102d09  call    cs:__imp_RtlCopyUnicodeString
0x140102d10  nop     dword ptr [rax+rax+00h]
0x140102d15  lea     rcx, [rbx+508h]; DestinationString
0x140102d1c  lea     rdx, [rsp+88h+SourceString]; SourceString
0x140102d21  call    cs:__imp_RtlCopyUnicodeString
0x140102d28  nop     dword ptr [rax+rax+00h]
0x140102d2d  mov     eax, [rbx+4E0h]
0x140102d33  dec     eax
0x140102d35  cmp     eax, 2
0x140102d38  ja      short loc_140102D87
0x140102d3a  mov     r12, [rbx+0FC8h]
0x140102d41  mov     r8, r12
0x140102d44  xor     edx, edx
0x140102d46  mov     rcx, rbx
0x140102d49  call    VmsOmNicCopyDataUnsafe
0x140102d4e  mov     rsi, [rbx+760h]
0x140102d55  mov     r8b, 1
0x140102d58  lea     rdx, [rsp+88h+LockState]
0x140102d60  mov     rcx, rsi
0x140102d63  call    VmsOmObjectLockShared
0x140102d68  mov     r13, [rsi+10A8h]
0x140102d6f  lea     rdx, [rsp+88h+LockState]; LockState
0x140102d77  mov     rcx, [rsi+38h]; Lock
0x140102d7b  call    cs:__imp_NdisReleaseRWLock
0x140102d82  nop     dword ptr [rax+rax+00h]
0x140102d87  cmp     byte ptr [rbx+754h], 1
0x140102d8e  jnz     short loc_140102DA3
0x140102d90  mov     r8d, 1
0x140102d96  mov     dl, 0Ah
0x140102d98  mov     rcx, rbx
0x140102d9b  call    VmsOmObjectPrepareForConfigStore
0x140102da0  mov     r14b, al
0x140102da3  lea     rdx, [rsp+88h+arg_8]; LockState
0x140102dab  mov     rcx, [rbx+38h]; Lock
0x140102daf  call    cs:__imp_NdisReleaseRWLock
0x140102db6  nop     dword ptr [rax+rax+00h]
0x140102dbb  test    rsi, rsi
0x140102dbe  jz      short loc_140102DEB
0x140102dc0  mov     [rsp+88h+var_58], 0; __int64
0x140102dc9  mov     [rsp+88h+var_60], 1; __int64
0x140102dd2  mov     [rsp+88h+Timeout], r12; Src
0x140102dd7  mov     r9d, 10294h; int
0x140102ddd  mov     r8, r13; int
0x140102de0  mov     rdx, rsi; int
0x140102de3  mov     rcx, rbx; int
0x140102de6  call    VmsOmNicSendMultipleOids
0x140102deb  xor     edx, edx; Wait
0x140102ded  lea     rcx, VmsOmIoctlMutex; Mutex
0x140102df4  call    cs:__imp_KeReleaseMutex
0x140102dfb  nop     dword ptr [rax+rax+00h]
0x140102e00  cmp     r14b, 1
0x140102e04  jnz     short loc_140102E22
0x140102e06  lea     rdx, [rbx+48h]
0x140102e0a  mov     r8d, 0Ah
0x140102e10  mov     rcx, rbx
0x140102e13  call    VmsOmNicStoreConfig
0x140102e18  jmp     short loc_140102E22
0x140102e1a  mov     rbx, [rsp+88h+arg_18]
0x140102e22  test    edi, edi
0x140102e24  jns     short loc_140102E53
0x140102e26  mov     r9d, 20h ; ' '
0x140102e2c  mov     dword ptr [rsp+88h+var_58], edi
0x140102e30  mov     [rsp+88h+var_60], r15
0x140102e35  lea     rax, WPP_bda91bcb57e433144f485e69e8239e42_Traceguids
0x140102e3c  mov     [rsp+88h+Timeout], rax
0x140102e41  lea     r8d, [r9-0Ch]
0x140102e45  mov     dl, 2
0x140102e47  mov     rcx, cs:VmsIfrNicLog
0x140102e4e  call    WPP_RECORDER_SF_Zd
0x140102e53  test    rbx, rbx
0x140102e56  jz      short loc_140102E62
0x140102e58  mov     dl, 9
0x140102e5a  mov     rcx, rbx
0x140102e5d  call    VmsOmpObjectDereference
0x140102e62  mov     eax, edi
0x140102e64  add     rsp, 50h
0x140102e68  pop     r15
0x140102e6a  pop     r14
0x140102e6c  pop     r13
0x140102e6e  pop     r12
0x140102e70  pop     rdi
0x140102e71  pop     rsi
0x140102e72  pop     rbx
0x140102e73  retn
0x1401bcda1  push    rbp
0x1401bcda3  sub     rsp, 40h
0x1401bcda7  mov     rbp, rdx
0x1401bcdaa  lea     rdx, [rbp+98h]; LockState
0x1401bcdb1  mov     rcx, [rbp+0A8h]
0x1401bcdb8  mov     rcx, [rcx+38h]; Lock
0x1401bcdbc  call    cs:__imp_NdisReleaseRWLock
0x1401bcdc3  nop     dword ptr [rax+rax+00h]
0x1401bcdc8  nop
0x1401bcdc9  add     rsp, 40h
0x1401bcdcd  pop     rbp
0x1401bcdce  retn
```
