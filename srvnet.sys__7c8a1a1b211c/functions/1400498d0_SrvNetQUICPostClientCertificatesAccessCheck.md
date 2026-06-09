# SrvNetQUICPostClientCertificatesAccessCheck

- ea: `0x1400498d0`
- end: `0x140049a60`
- name: `SrvNetQUICPostClientCertificatesAccessCheck`
- size: `400`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x14001ce20`

## callees

- `0x140007c60`
- `0x140007ec0`
- `0x140013acc`
- `0x140016c84`
- `0x14001bc5c`
- `0x140049458`
- `0x1400498d0`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x1400498e6`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400498e6`
- `ntoskrnl!IoQueueWorkItem` at `0x140049a15`
- `ntoskrnl!IoQueueWorkItem` at `0x140049a15`
- `ntoskrnl!IoFreeWorkItem` at `0x1400499b1`
- `ntoskrnl!IoFreeWorkItem` at `0x1400499b1`

## pseudocode

```c
__int64 __fastcall SrvNetQUICPostClientCertificatesAccessCheck(__int64 a1, __int64 a2)
{
  struct _IO_WORKITEM *WorkItem; // rsi
  unsigned int v5; // ebx
  __int64 PoolWithTag; // rax
  _QWORD *v7; // rdi
  __int64 v8; // rcx

  WorkItem = IoAllocateWorkItem((PDEVICE_OBJECT)SrvNetDeviceObject);
  if ( !WorkItem )
  {
    v5 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_dq(
        WPP_GLOBAL_Control->AttachedDevice,
        43,
        WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids,
        3221225626LL,
        a1);
    }
    return v5;
  }
  PoolWithTag = SrvNetAllocatePoolWithTag(256, 128, 1986220876);
  v7 = (_QWORD *)PoolWithTag;
  if ( !PoolWithTag )
  {
    v5 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_dq(
        WPP_GLOBAL_Control->AttachedDevice,
        44,
        WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids,
        3221225626LL,
        a1);
    }
    goto LABEL_11;
  }
  v5 = SrvNetQUICDuplicateCertificateChain(a2, PoolWithTag + 8);
  if ( (v5 & 0x80000000) != 0 )
  {
LABEL_11:
    IoFreeWorkItem(WorkItem);
    if ( v7 )
    {
      v8 = v7[2];
      if ( v8 )
        SrvNetWskNotifyCleanupProviderContext(v8);
      SrvNetWskNotifyCleanupProviderContext(v7);
    }
    return v5;
  }
  *v7 = a1;
  v7[15] = WorkItem;
  SrvNetReferenceConnection(a1);
  IoQueueWorkItem(WorkItem, SrvNetQUICClientCertificatesAccessCheckWorker, CriticalWorkQueue, v7);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids, a1);
  }
  return v5;
}

```

## disassembly

```asm
0x1400498d0  push    rbx
0x1400498d2  push    rbp
0x1400498d3  push    rsi
0x1400498d4  push    rdi
0x1400498d5  sub     rsp, 38h
0x1400498d9  mov     rbp, rcx
0x1400498dc  mov     rbx, rdx
0x1400498df  mov     rcx, cs:SrvNetDeviceObject; DeviceObject
0x1400498e6  call    cs:__imp_IoAllocateWorkItem
0x1400498ed  nop     dword ptr [rax+rax+00h]
0x1400498f2  mov     rsi, rax
0x1400498f5  test    rax, rax
0x1400498f8  jnz     short loc_14004994E
0x1400498fa  mov     r9d, 0C000009Ah
0x140049900  mov     ebx, r9d
0x140049903  mov     rcx, cs:WPP_GLOBAL_Control
0x14004990a  lea     rax, WPP_GLOBAL_Control
0x140049911  cmp     rcx, rax
0x140049914  jz      loc_1400499D8
0x14004991a  test    dword ptr [rcx+2Ch], 200000h
0x140049921  jz      loc_1400499D8
0x140049927  cmp     byte ptr [rcx+29h], 1
0x14004992b  jb      loc_1400499D8
0x140049931  mov     rcx, [rcx+18h]
0x140049935  lea     edx, [rsi+2Bh]
0x140049938  lea     r8, WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids
0x14004993f  mov     [rsp+58h+var_38], rbp
0x140049944  call    WPP_SF_dq
0x140049949  jmp     loc_1400499D8
0x14004994e  mov     edx, 80h
0x140049953  mov     ecx, 100h
0x140049958  mov     r8d, 7663534Ch
0x14004995e  call    SrvNetAllocatePoolWithTag
0x140049963  mov     rdi, rax
0x140049966  test    rax, rax
0x140049969  jnz     short loc_1400499E4
0x14004996b  mov     r9d, 0C000009Ah
0x140049971  mov     ebx, r9d
0x140049974  mov     rcx, cs:WPP_GLOBAL_Control
0x14004997b  lea     rax, WPP_GLOBAL_Control
0x140049982  cmp     rcx, rax
0x140049985  jz      short loc_1400499AE
0x140049987  test    dword ptr [rcx+2Ch], 200000h
0x14004998e  jz      short loc_1400499AE
0x140049990  cmp     byte ptr [rcx+29h], 1
0x140049994  jb      short loc_1400499AE
0x140049996  mov     rcx, [rcx+18h]
0x14004999a  lea     edx, [rdi+2Ch]
0x14004999d  lea     r8, WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids
0x1400499a4  mov     [rsp+58h+var_38], rbp
0x1400499a9  call    WPP_SF_dq
0x1400499ae  mov     rcx, rsi; IoWorkItem
0x1400499b1  call    cs:__imp_IoFreeWorkItem
0x1400499b8  nop     dword ptr [rax+rax+00h]
0x1400499bd  test    rdi, rdi
0x1400499c0  jz      short loc_1400499D8
0x1400499c2  mov     rcx, [rdi+10h]
0x1400499c6  test    rcx, rcx
0x1400499c9  jz      short loc_1400499D0
0x1400499cb  call    SrvNetWskNotifyCleanupProviderContext
0x1400499d0  mov     rcx, rdi
0x1400499d3  call    SrvNetWskNotifyCleanupProviderContext
0x1400499d8  mov     eax, ebx
0x1400499da  add     rsp, 38h
0x1400499de  pop     rdi
0x1400499df  pop     rsi
0x1400499e0  pop     rbp
0x1400499e1  pop     rbx
0x1400499e2  retn
0x1400499e4  lea     rdx, [rax+8]
0x1400499e8  mov     rcx, rbx
0x1400499eb  call    SrvNetQUICDuplicateCertificateChain
0x1400499f0  mov     ebx, eax
0x1400499f2  test    eax, eax
0x1400499f4  js      short loc_1400499AE
0x1400499f6  mov     rcx, rbp
0x1400499f9  mov     [rdi], rbp
0x1400499fc  mov     [rdi+78h], rsi
0x140049a00  call    SrvNetReferenceConnection
0x140049a05  mov     r9, rdi; Context
0x140049a08  lea     rdx, SrvNetQUICClientCertificatesAccessCheckWorker; WorkerRoutine
0x140049a0f  xor     r8d, r8d; QueueType
0x140049a12  mov     rcx, rsi; IoWorkItem
0x140049a15  call    cs:__imp_IoQueueWorkItem
0x140049a1c  nop     dword ptr [rax+rax+00h]
0x140049a21  mov     rcx, cs:WPP_GLOBAL_Control
0x140049a28  lea     rax, WPP_GLOBAL_Control
0x140049a2f  cmp     rcx, rax
0x140049a32  jz      short loc_1400499D8
0x140049a34  test    dword ptr [rcx+2Ch], 200000h
0x140049a3b  jz      short loc_1400499D8
0x140049a3d  cmp     byte ptr [rcx+29h], 2
0x140049a41  jb      short loc_1400499D8
0x140049a43  mov     rcx, [rcx+18h]
0x140049a47  lea     r8, WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids
0x140049a4e  mov     edx, 2Dh ; '-'
0x140049a53  mov     r9, rbp
0x140049a56  call    WPP_SF_q
0x140049a5b  jmp     loc_1400499D8
```
