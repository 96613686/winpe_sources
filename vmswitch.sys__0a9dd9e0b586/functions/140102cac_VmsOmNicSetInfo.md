# VmsOmNicSetInfo

- ea: `0x140102cac`
- end: `0x140102ee5`
- name: `VmsOmNicSetInfo`
- size: `569`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x1400c1bd4`

## callees

- `0x14001484c`
- `0x1400313cc`
- `0x1400370b4`
- `0x140066bec`
- `0x14006b084`
- `0x14007a254`
- `0x14008c82c`
- `0x1400fe760`
- `0x140102cac`
- `0x1401068b8`
- `0x140106fa8`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140102d79`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140102d91`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140102d79`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140102d91`
- `ntoskrnl!KeReleaseMutex` at `0x140102e64`
- `ntoskrnl!KeReleaseMutex` at `0x140102e64`
- `ntoskrnl!KeWaitForSingleObject` at `0x140102d45`
- `ntoskrnl!KeWaitForSingleObject` at `0x140102d45`
- `NDIS!NdisReleaseRWLock` at `0x140102deb`
- `NDIS!NdisReleaseRWLock` at `0x140102e1f`
- `NDIS!NdisReleaseRWLock` at `0x1401bce3c`
- `NDIS!NdisReleaseRWLock` at `0x140102deb`
- `NDIS!NdisReleaseRWLock` at `0x140102e1f`
- `NDIS!NdisReleaseRWLock` at `0x1401bce3c`

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
0x140102cac  mov     r11, rsp
0x140102caf  push    rbx
0x140102cb0  push    rsi
0x140102cb1  push    rdi
0x140102cb2  push    r12
0x140102cb4  push    r13
0x140102cb6  push    r14
0x140102cb8  push    r15
0x140102cba  sub     rsp, 50h
0x140102cbe  mov     r15, rcx
0x140102cc1  xor     ebx, ebx
0x140102cc3  mov     [r11+20h], rbx
0x140102cc7  xor     eax, eax
0x140102cc9  mov     [r11+10h], ax
0x140102cce  mov     [r11+12h], al
0x140102cd2  mov     [r11+18h], ax
0x140102cd7  mov     [r11+1Ah], al
0x140102cdb  xorps   xmm0, xmm0
0x140102cde  movups  xmmword ptr [rsp+88h+SourceString.Length], xmm0
0x140102ce3  mov     r8d, 200h
0x140102ce9  add     rdx, 100h
0x140102cf0  lea     rcx, [r11-48h]
0x140102cf4  call    VmsUtilInitUnicodeStringSafe
0x140102cf9  test    eax, eax
0x140102cfb  jns     short loc_140102D07
0x140102cfd  mov     edi, 0C000000Dh
0x140102d02  jmp     loc_140102E96
0x140102d07  lea     r8, [rsp+88h+arg_18]
0x140102d0f  mov     edx, 9
0x140102d14  mov     rcx, r15
0x140102d17  call    VmsOmFindNicInitialized
0x140102d1c  mov     edi, eax
0x140102d1e  test    eax, eax
0x140102d20  jnz     loc_140102E8A
0x140102d26  xor     r14b, r14b
0x140102d29  xor     r13d, r13d
0x140102d2c  xor     esi, esi
0x140102d2e  xor     r12d, r12d
0x140102d31  mov     [rsp+88h+Timeout], rbx; Timeout
0x140102d36  xor     r9d, r9d; Alertable
0x140102d39  xor     r8d, r8d; WaitMode
0x140102d3c  xor     edx, edx; WaitReason
0x140102d3e  lea     rcx, VmsOmIoctlMutex; Object
0x140102d45  call    cs:__imp_KeWaitForSingleObject
0x140102d4c  nop     dword ptr [rax+rax+00h]
0x140102d51  nop
0x140102d52  xor     r8d, r8d
0x140102d55  lea     rdx, [rsp+88h+arg_8]
0x140102d5d  mov     rbx, [rsp+88h+arg_18]
0x140102d65  mov     rcx, rbx
0x140102d68  call    VmsOmObjectLockExclusive
0x140102d6d  lea     rcx, [rbx+268h]; DestinationString
0x140102d74  lea     rdx, [rsp+88h+SourceString]; SourceString
0x140102d79  call    cs:__imp_RtlCopyUnicodeString
0x140102d80  nop     dword ptr [rax+rax+00h]
0x140102d85  lea     rcx, [rbx+508h]; DestinationString
0x140102d8c  lea     rdx, [rsp+88h+SourceString]; SourceString
0x140102d91  call    cs:__imp_RtlCopyUnicodeString
0x140102d98  nop     dword ptr [rax+rax+00h]
0x140102d9d  mov     eax, [rbx+4E0h]
0x140102da3  dec     eax
0x140102da5  cmp     eax, 2
0x140102da8  ja      short loc_140102DF7
0x140102daa  mov     r12, [rbx+0FC8h]
0x140102db1  mov     r8, r12
0x140102db4  xor     edx, edx
0x140102db6  mov     rcx, rbx
0x140102db9  call    VmsOmNicCopyDataUnsafe
0x140102dbe  mov     rsi, [rbx+760h]
0x140102dc5  mov     r8b, 1
0x140102dc8  lea     rdx, [rsp+88h+LockState]
0x140102dd0  mov     rcx, rsi
0x140102dd3  call    VmsOmObjectLockShared
0x140102dd8  mov     r13, [rsi+10A8h]
0x140102ddf  lea     rdx, [rsp+88h+LockState]; LockState
0x140102de7  mov     rcx, [rsi+38h]; Lock
0x140102deb  call    cs:__imp_NdisReleaseRWLock
0x140102df2  nop     dword ptr [rax+rax+00h]
0x140102df7  cmp     byte ptr [rbx+754h], 1
0x140102dfe  jnz     short loc_140102E13
0x140102e00  mov     r8d, 1
0x140102e06  mov     dl, 0Ah
0x140102e08  mov     rcx, rbx
0x140102e0b  call    VmsOmObjectPrepareForConfigStore
0x140102e10  mov     r14b, al
0x140102e13  lea     rdx, [rsp+88h+arg_8]; LockState
0x140102e1b  mov     rcx, [rbx+38h]; Lock
0x140102e1f  call    cs:__imp_NdisReleaseRWLock
0x140102e26  nop     dword ptr [rax+rax+00h]
0x140102e2b  test    rsi, rsi
0x140102e2e  jz      short loc_140102E5B
0x140102e30  mov     [rsp+88h+var_58], 0; __int64
0x140102e39  mov     [rsp+88h+var_60], 1; __int64
0x140102e42  mov     [rsp+88h+Timeout], r12; Src
0x140102e47  mov     r9d, 10294h; int
0x140102e4d  mov     r8, r13; int
0x140102e50  mov     rdx, rsi; int
0x140102e53  mov     rcx, rbx; int
0x140102e56  call    VmsOmNicSendMultipleOids
0x140102e5b  xor     edx, edx; Wait
0x140102e5d  lea     rcx, VmsOmIoctlMutex; Mutex
0x140102e64  call    cs:__imp_KeReleaseMutex
0x140102e6b  nop     dword ptr [rax+rax+00h]
0x140102e70  cmp     r14b, 1
0x140102e74  jnz     short loc_140102E92
0x140102e76  lea     rdx, [rbx+48h]
0x140102e7a  mov     r8d, 0Ah
0x140102e80  mov     rcx, rbx
0x140102e83  call    VmsOmNicStoreConfig
0x140102e88  jmp     short loc_140102E92
0x140102e8a  mov     rbx, [rsp+88h+arg_18]
0x140102e92  test    edi, edi
0x140102e94  jns     short loc_140102EC3
0x140102e96  mov     r9d, 20h ; ' '
0x140102e9c  mov     dword ptr [rsp+88h+var_58], edi
0x140102ea0  mov     [rsp+88h+var_60], r15
0x140102ea5  lea     rax, WPP_bda91bcb57e433144f485e69e8239e42_Traceguids
0x140102eac  mov     [rsp+88h+Timeout], rax
0x140102eb1  lea     r8d, [r9-0Ch]
0x140102eb5  mov     dl, 2
0x140102eb7  mov     rcx, cs:VmsIfrNicLog
0x140102ebe  call    WPP_RECORDER_SF_Zd
0x140102ec3  test    rbx, rbx
0x140102ec6  jz      short loc_140102ED2
0x140102ec8  mov     dl, 9
0x140102eca  mov     rcx, rbx
0x140102ecd  call    VmsOmpObjectDereference
0x140102ed2  mov     eax, edi
0x140102ed4  add     rsp, 50h
0x140102ed8  pop     r15
0x140102eda  pop     r14
0x140102edc  pop     r13
0x140102ede  pop     r12
0x140102ee0  pop     rdi
0x140102ee1  pop     rsi
0x140102ee2  pop     rbx
0x140102ee3  retn
0x1401bce21  push    rbp
0x1401bce23  sub     rsp, 40h
0x1401bce27  mov     rbp, rdx
0x1401bce2a  lea     rdx, [rbp+98h]; LockState
0x1401bce31  mov     rcx, [rbp+0A8h]
0x1401bce38  mov     rcx, [rcx+38h]; Lock
0x1401bce3c  call    cs:__imp_NdisReleaseRWLock
0x1401bce43  nop     dword ptr [rax+rax+00h]
0x1401bce48  nop
0x1401bce49  add     rsp, 40h
0x1401bce4d  pop     rbp
0x1401bce4e  retn
```
