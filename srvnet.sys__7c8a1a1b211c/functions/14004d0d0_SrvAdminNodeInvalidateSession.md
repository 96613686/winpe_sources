# SrvAdminNodeInvalidateSession

- ea: `0x14004d0d0`
- end: `0x14004d4e1`
- name: `SrvAdminNodeInvalidateSession`
- size: `1041`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task`

## callees

- `0x140007c60`
- `0x140007ec0`
- `0x1400143d0`
- `0x1400146a4`
- `0x140024358`
- `0x1400243c0`
- `0x140029724`
- `0x14002a3e0`
- `0x14004d0d0`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x14004d3c8`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14004d3c8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14004d3dd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14004d453`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14004d493`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14004d3dd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14004d453`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14004d493`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14004d155`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14004d155`
- `ntoskrnl!IoAllocateWorkItem` at `0x14004d38b`
- `ntoskrnl!IoAllocateWorkItem` at `0x14004d38b`
- `ntoskrnl!RtlLengthSid` at `0x14004d271`
- `ntoskrnl!RtlLengthSid` at `0x14004d271`
- `ntoskrnl!RtlCopySid` at `0x14004d292`
- `ntoskrnl!RtlCopySid` at `0x14004d292`
- `ntoskrnl!IoQueueWorkItem` at `0x14004d43c`
- `ntoskrnl!IoQueueWorkItem` at `0x14004d43c`

## pseudocode

```c
__int64 __fastcall SrvAdminNodeInvalidateSession(__int64 a1, __int64 a2, void *a3, __int64 a4, int a5)
{
  __int64 v5; // rsi
  int v6; // edi
  __int64 v9; // r8
  _DWORD *matched; // rbx
  __int64 PoolWithTag; // rax
  bool v12; // r14
  __int64 v13; // r8
  __int64 v14; // r13
  __int64 v15; // r15
  ULONG v16; // eax
  PSID v17; // r8
  __int64 v18; // r8
  __int64 v19; // rcx
  __int64 v20; // rax
  PIO_WORKITEM WorkItem; // rax
  __int64 v22; // r8
  bool v23; // cf
  bool v24; // zf
  int v26; // [rsp+40h] [rbp-31h] BYREF
  int v27; // [rsp+48h] [rbp-29h] BYREF
  PSID Sid; // [rsp+50h] [rbp-21h]
  __int128 v29; // [rsp+58h] [rbp-19h] BYREF
  int v30; // [rsp+68h] [rbp-9h]

  Sid = a3;
  v30 = 0;
  v5 = 0;
  v27 = 0;
  v29 = 0;
  v6 = 0;
  v26 = a2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_idq(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a1, a2, a4);
  }
  ExAcquirePushLockExclusiveEx(&NodeInfo, 0);
  v27 = 17;
  matched = (_DWORD *)RfsHashTableBucketLookupMatchEntry(SrvNodeTasksTable, &v26, v9, &v27);
  if ( !matched )
  {
    PoolWithTag = SrvNetAllocatePoolWithTag(64, 3656, 1684095315);
    matched = (_DWORD *)PoolWithTag;
    if ( !PoolWithTag )
    {
      v6 = -1073741670;
      v12 = 0;
LABEL_33:
      ExReleasePushLockExclusiveEx(&NodeInfo, 0);
      if ( v5 )
        SrvNetWskNotifyCleanupProviderContext(v5);
      if ( matched && v12 )
        SrvNetWskNotifyCleanupProviderContext(matched);
      return (unsigned int)v6;
    }
    v6 = RfsHashTableInsertEx((_DWORD)SrvNodeTasksTable, PoolWithTag, (unsigned int)&v26, 1, 0);
    if ( v6 < 0 )
      goto LABEL_31;
    matched[4] = 1;
    matched[8] = v26;
    matched[6] = 1;
    matched[9] = 2840;
    matched[718] = v26;
    matched[716] = 1;
    matched[719] = 2840;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qidq(WPP_GLOBAL_Control->AttachedDevice, 23, v13, matched, a1, v26, a4);
    }
  }
  v14 = (unsigned int)matched[7];
  v15 = 22 * v14;
  matched[7] = v14 + 1;
  *(_QWORD *)&matched[v15 + 12] = a1;
  matched[v15 + 15] = 0;
  if ( SrvAdminBackChannelSessionRequests == matched[7] )
    matched[4] = 2;
  v16 = RtlLengthSid(Sid);
  v17 = Sid;
  matched[v15 + 14] = v16;
  RtlCopySid(0x44u, &matched[v15 + 16], v17);
  if ( (unsigned int)v14 >= 0x20 )
  {
    v6 = -1073741595;
    goto LABEL_29;
  }
  matched[717] = matched[7];
  v19 = 3 * v14;
  matched[2 * v19 + 724] = a5;
  *(_QWORD *)&matched[2 * v19 + 722] = a1;
  *(_QWORD *)&matched[6 * v14 + 726] = a4;
  DWORD2(v29) = v26;
  LODWORD(v29) = 1;
  if ( RfsHashTableBucketLookupMatchEntry(SrvNodeActiveTasksTable, &v26, v18, &v29) )
  {
    ExReleasePushLockExclusiveEx(&NodeInfo, 0);
    return (unsigned int)v6;
  }
  v20 = SrvNetAllocatePoolWithTag(64, 144, 1684095315);
  v5 = v20;
  if ( !v20 )
  {
    v6 = -1073741670;
LABEL_29:
    v23 = matched[7] == 0;
    v24 = matched[7] == 1;
    if ( matched[7] != 1 )
    {
LABEL_32:
      v12 = v23 || v24;
      goto LABEL_33;
    }
    RfsHashTableRemove(SrvNodeTasksTable, matched, &v26, 1);
LABEL_31:
    v23 = matched[7] == 0;
    v24 = matched[7] == 1;
    goto LABEL_32;
  }
  v6 = RfsHashTableInsertEx((_DWORD)SrvNodeActiveTasksTable, v20, (unsigned int)&v26, 1, 0);
  if ( v6 < 0 )
    goto LABEL_29;
  *(_QWORD *)(v5 + 128) = 0;
  *(_BYTE *)(v5 + 140) = v26;
  *(_DWORD *)(v5 + 136) = 16;
  WorkItem = IoAllocateWorkItem((PDEVICE_OBJECT)SrvNetDeviceObject);
  *(_QWORD *)(v5 + 120) = WorkItem;
  if ( !WorkItem )
  {
    v6 = -1073741670;
    RfsHashTableRemove(SrvNodeActiveTasksTable, v5 + 96, &v26, 1);
    goto LABEL_29;
  }
  ExAcquireRundownProtection(&SrvAdminNodeRundown);
  ExReleasePushLockExclusiveEx(&NodeInfo, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qidq(WPP_GLOBAL_Control->AttachedDevice, 24, v22, matched, a1, v26, a4);
  }
  IoQueueWorkItem(*(PIO_WORKITEM *)(v5 + 120), InvalidationThread, CriticalWorkQueue, (PVOID)v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14004d0d0  push    rbp
0x14004d0d2  push    rbx
0x14004d0d3  push    rsi
0x14004d0d4  push    rdi
0x14004d0d5  push    r12
0x14004d0d7  push    r13
0x14004d0d9  push    r14
0x14004d0db  push    r15
0x14004d0dd  lea     rbp, [rsp-17h]
0x14004d0e2  sub     rsp, 88h
0x14004d0e9  mov     rax, cs:__security_cookie
0x14004d0f0  xor     rax, rsp
0x14004d0f3  mov     [rbp+4Fh+var_50], rax
0x14004d0f7  xor     eax, eax
0x14004d0f9  mov     [rbp+4Fh+Sid], r8
0x14004d0fd  xorps   xmm0, xmm0
0x14004d100  mov     [rbp+4Fh+var_58], eax
0x14004d103  xor     esi, esi
0x14004d105  mov     [rbp+4Fh+var_78], eax
0x14004d108  movups  [rbp+4Fh+var_68], xmm0
0x14004d10c  xor     edi, edi
0x14004d10e  mov     [rbp+4Fh+var_80], edx
0x14004d111  mov     r12, r9
0x14004d114  mov     r14, rcx
0x14004d117  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004d11e  lea     r13, WPP_GLOBAL_Control
0x14004d125  cmp     rcx, r13
0x14004d128  jz      short loc_14004D14C
0x14004d12a  mov     eax, [rcx+2Ch]
0x14004d12d  test    al, 20h
0x14004d12f  jz      short loc_14004D14C
0x14004d131  cmp     byte ptr [rcx+29h], 4
0x14004d135  jb      short loc_14004D14C
0x14004d137  mov     rcx, [rcx+18h]
0x14004d13b  mov     [rsp+0C0h+var_98], r9
0x14004d140  mov     r9, r14
0x14004d143  mov     dword ptr [rsp+0C0h+var_A0], edx
0x14004d147  call    WPP_SF_idq
0x14004d14c  xor     edx, edx
0x14004d14e  lea     rcx, NodeInfo
0x14004d155  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14004d15c  nop     dword ptr [rax+rax+00h]
0x14004d161  mov     rcx, cs:SrvNodeTasksTable
0x14004d168  lea     r9, [rbp+4Fh+var_78]
0x14004d16c  lea     rdx, [rbp+4Fh+var_80]
0x14004d170  mov     [rbp+4Fh+var_78], 11h
0x14004d177  call    RfsHashTableBucketLookupMatchEntry
0x14004d17c  mov     rbx, rax
0x14004d17f  mov     r15d, 1
0x14004d185  test    rax, rax
0x14004d188  jnz     loc_14004D242
0x14004d18e  mov     edx, 0E48h
0x14004d193  lea     ecx, [rax+40h]
0x14004d196  mov     r8d, 64614153h
0x14004d19c  call    SrvNetAllocatePoolWithTag
0x14004d1a1  mov     rbx, rax
0x14004d1a4  test    rax, rax
0x14004d1a7  jnz     short loc_14004D1B6
0x14004d1a9  mov     edi, 0C000009Ah
0x14004d1ae  xor     r14b, r14b
0x14004d1b1  jmp     loc_14004D48A
0x14004d1b6  mov     rcx, cs:SrvNodeTasksTable
0x14004d1bd  lea     r8, [rbp+4Fh+var_80]
0x14004d1c1  mov     r9d, r15d
0x14004d1c4  mov     byte ptr [rsp+0C0h+var_A0], sil
0x14004d1c9  mov     rdx, rbx
0x14004d1cc  call    RfsHashTableInsertEx
0x14004d1d1  mov     edi, eax
0x14004d1d3  test    eax, eax
0x14004d1d5  js      loc_14004D482
0x14004d1db  mov     [rbx+10h], r15d
0x14004d1df  mov     ecx, 0B18h
0x14004d1e4  mov     eax, [rbp+4Fh+var_80]
0x14004d1e7  mov     [rbx+20h], eax
0x14004d1ea  mov     [rbx+18h], r15d
0x14004d1ee  mov     [rbx+24h], ecx
0x14004d1f1  mov     eax, [rbp+4Fh+var_80]
0x14004d1f4  mov     [rbx+0B38h], eax
0x14004d1fa  mov     [rbx+0B30h], r15d
0x14004d201  mov     [rbx+0B3Ch], ecx
0x14004d207  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004d20e  cmp     rcx, r13
0x14004d211  jz      short loc_14004D242
0x14004d213  mov     eax, [rcx+2Ch]
0x14004d216  test    al, 20h
0x14004d218  jz      short loc_14004D242
0x14004d21a  cmp     byte ptr [rcx+29h], 4
0x14004d21e  jb      short loc_14004D242
0x14004d220  mov     eax, [rbp+4Fh+var_80]
0x14004d223  mov     edx, 17h
0x14004d228  mov     rcx, [rcx+18h]
0x14004d22c  mov     r9, rbx
0x14004d22f  mov     [rsp+0C0h+var_90], r12
0x14004d234  mov     dword ptr [rsp+0C0h+var_98], eax
0x14004d238  mov     [rsp+0C0h+var_A0], r14
0x14004d23d  call    WPP_SF_qidq
0x14004d242  mov     r13d, [rbx+1Ch]
0x14004d246  imul    r15, r13, 58h ; 'X'
0x14004d24a  lea     eax, [r13+1]
0x14004d24e  mov     [rbx+1Ch], eax
0x14004d251  mov     [r15+rbx+30h], r14
0x14004d256  mov     [r15+rbx+3Ch], esi
0x14004d25b  mov     eax, [rbx+1Ch]
0x14004d25e  cmp     cs:SrvAdminBackChannelSessionRequests, eax
0x14004d264  jnz     short loc_14004D26D
0x14004d266  mov     dword ptr [rbx+10h], 2
0x14004d26d  mov     rcx, [rbp+4Fh+Sid]; Sid
0x14004d271  call    cs:__imp_RtlLengthSid
0x14004d278  nop     dword ptr [rax+rax+00h]
0x14004d27d  mov     r8, [rbp+4Fh+Sid]; SourceSid
0x14004d281  lea     rdx, [rbx+40h]
0x14004d285  add     rdx, r15; DestinationSid
0x14004d288  mov     [r15+rbx+38h], eax
0x14004d28d  mov     ecx, 44h ; 'D'; DestinationSidLength
0x14004d292  call    cs:__imp_RtlCopySid
0x14004d299  nop     dword ptr [rax+rax+00h]
0x14004d29e  mov     r15d, 1
0x14004d2a4  cmp     r13d, 20h ; ' '
0x14004d2a8  jnb     loc_14004D461
0x14004d2ae  mov     eax, [rbx+1Ch]
0x14004d2b1  lea     rcx, ds:0[r13*2]
0x14004d2b9  mov     [rbx+0B34h], eax
0x14004d2bf  lea     r9, [rbp+4Fh+var_68]
0x14004d2c3  mov     eax, [rbp+4Fh+arg_20]
0x14004d2c6  lea     rdx, [rbp+4Fh+var_80]
0x14004d2ca  add     rcx, r13
0x14004d2cd  mov     [rbx+rcx*8+0B50h], eax
0x14004d2d4  lea     rax, ds:0[r13*2]
0x14004d2dc  mov     [rbx+rcx*8+0B48h], r14
0x14004d2e4  add     rax, r13
0x14004d2e7  mov     [rbx+rax*8+0B58h], r12
0x14004d2ef  mov     al, byte ptr [rbp+4Fh+var_80]
0x14004d2f2  mov     rcx, cs:SrvNodeActiveTasksTable
0x14004d2f9  mov     byte ptr [rbp+4Fh+var_68+8], al
0x14004d2fc  movzx   eax, word ptr [rbp+4Fh+var_80+1]
0x14004d300  mov     word ptr [rbp+4Fh+var_68+9], ax
0x14004d304  mov     al, byte ptr [rbp+4Fh+var_80+3]
0x14004d307  mov     byte ptr [rbp+4Fh+var_68+0Bh], al
0x14004d30a  mov     dword ptr [rbp+4Fh+var_68], r15d
0x14004d30e  call    RfsHashTableBucketLookupMatchEntry
0x14004d313  test    rax, rax
0x14004d316  jnz     loc_14004D44A
0x14004d31c  mov     edx, 90h
0x14004d321  lea     ecx, [rax+40h]
0x14004d324  mov     r8d, 64614153h
0x14004d32a  call    SrvNetAllocatePoolWithTag
0x14004d32f  mov     rsi, rax
0x14004d332  test    rax, rax
0x14004d335  jnz     short loc_14004D341
0x14004d337  mov     edi, 0C000009Ah
0x14004d33c  jmp     loc_14004D466
0x14004d341  mov     rcx, cs:SrvNodeActiveTasksTable
0x14004d348  lea     r8, [rbp+4Fh+var_80]
0x14004d34c  mov     r9d, r15d
0x14004d34f  mov     byte ptr [rsp+0C0h+var_A0], 0
0x14004d354  mov     rdx, rsi
0x14004d357  call    RfsHashTableInsertEx
0x14004d35c  mov     edi, eax
0x14004d35e  test    eax, eax
0x14004d360  js      loc_14004D466
0x14004d366  mov     qword ptr [rsi+80h], 0
0x14004d371  mov     al, byte ptr [rbp+4Fh+var_80]
0x14004d374  mov     [rsi+8Ch], al
0x14004d37a  mov     dword ptr [rsi+88h], 10h
0x14004d384  mov     rcx, cs:SrvNetDeviceObject; DeviceObject
0x14004d38b  call    cs:__imp_IoAllocateWorkItem
0x14004d392  nop     dword ptr [rax+rax+00h]
0x14004d397  mov     [rsi+78h], rax
0x14004d39b  test    rax, rax
0x14004d39e  jnz     short loc_14004D3C1
0x14004d3a0  mov     edi, 0C000009Ah
0x14004d3a5  mov     rcx, cs:SrvNodeActiveTasksTable
0x14004d3ac  lea     rdx, [rsi+60h]
0x14004d3b0  mov     r9d, r15d
0x14004d3b3  lea     r8, [rbp+4Fh+var_80]
0x14004d3b7  call    RfsHashTableRemove
0x14004d3bc  jmp     loc_14004D466
0x14004d3c1  lea     rcx, SrvAdminNodeRundown; RunRef
0x14004d3c8  call    cs:__imp_ExAcquireRundownProtection
0x14004d3cf  nop     dword ptr [rax+rax+00h]
0x14004d3d4  xor     edx, edx
0x14004d3d6  lea     rcx, NodeInfo
0x14004d3dd  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14004d3e4  nop     dword ptr [rax+rax+00h]
0x14004d3e9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004d3f0  lea     rax, WPP_GLOBAL_Control
0x14004d3f7  cmp     rcx, rax
0x14004d3fa  jz      short loc_14004D42B
0x14004d3fc  mov     eax, [rcx+2Ch]
0x14004d3ff  test    al, 20h
0x14004d401  jz      short loc_14004D42B
0x14004d403  cmp     byte ptr [rcx+29h], 4
0x14004d407  jb      short loc_14004D42B
0x14004d409  mov     eax, [rbp+4Fh+var_80]
0x14004d40c  mov     edx, 18h
0x14004d411  mov     rcx, [rcx+18h]
0x14004d415  mov     r9, rbx
0x14004d418  mov     [rsp+0C0h+var_90], r12
0x14004d41d  mov     dword ptr [rsp+0C0h+var_98], eax
0x14004d421  mov     [rsp+0C0h+var_A0], r14
0x14004d426  call    WPP_SF_qidq
0x14004d42b  mov     rcx, [rsi+78h]; IoWorkItem
0x14004d42f  lea     rdx, InvalidationThread; WorkerRoutine
0x14004d436  mov     r9, rsi; Context
0x14004d439  xor     r8d, r8d; QueueType
0x14004d43c  call    cs:__imp_IoQueueWorkItem
0x14004d443  nop     dword ptr [rax+rax+00h]
0x14004d448  jmp     short loc_14004D4BE
0x14004d44a  xor     edx, edx
0x14004d44c  lea     rcx, NodeInfo
0x14004d453  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14004d45a  nop     dword ptr [rax+rax+00h]
0x14004d45f  jmp     short loc_14004D4BE
0x14004d461  mov     edi, 0C00000E5h
0x14004d466  cmp     [rbx+1Ch], r15d
0x14004d46a  jnz     short loc_14004D486
0x14004d46c  mov     rcx, cs:SrvNodeTasksTable
0x14004d473  lea     r8, [rbp+4Fh+var_80]
0x14004d477  mov     r9d, r15d
0x14004d47a  mov     rdx, rbx
0x14004d47d  call    RfsHashTableRemove
0x14004d482  cmp     [rbx+1Ch], r15d
0x14004d486  setbe   r14b
0x14004d48a  xor     edx, edx
0x14004d48c  lea     rcx, NodeInfo
0x14004d493  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14004d49a  nop     dword ptr [rax+rax+00h]
0x14004d49f  test    rsi, rsi
0x14004d4a2  jz      short loc_14004D4AC
0x14004d4a4  mov     rcx, rsi
0x14004d4a7  call    SrvNetWskNotifyCleanupProviderContext
0x14004d4ac  test    rbx, rbx
0x14004d4af  jz      short loc_14004D4BE
0x14004d4b1  test    r14b, r14b
0x14004d4b4  jz      short loc_14004D4BE
0x14004d4b6  mov     rcx, rbx
0x14004d4b9  call    SrvNetWskNotifyCleanupProviderContext
0x14004d4be  mov     eax, edi
0x14004d4c0  mov     rcx, [rbp+4Fh+var_50]
0x14004d4c4  xor     rcx, rsp; StackCookie
0x14004d4c7  call    __security_check_cookie
0x14004d4cc  add     rsp, 88h
0x14004d4d3  pop     r15
0x14004d4d5  pop     r14
0x14004d4d7  pop     r13
0x14004d4d9  pop     r12
0x14004d4db  pop     rdi
0x14004d4dc  pop     rsi
0x14004d4dd  pop     rbx
0x14004d4de  pop     rbp
0x14004d4df  retn
```
