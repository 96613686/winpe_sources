# MpDlpInitialize

- ea: `0x140094508`
- end: `0x14009481e`
- name: `MpDlpInitialize`
- size: `790`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x14008f314`

## callees

- `0x1400018a4`
- `0x1400026c0`
- `0x1400051bc`
- `0x14000ff04`
- `0x1400861e0`
- `0x140088a2c`
- `0x14008be3c`
- `0x14008c158`
- `0x140094508`

## import_xrefs

- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400946a3`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140094717`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400946a3`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140094717`
- `FLTMGR!FltInitializePushLock` at `0x1400945d7`
- `FLTMGR!FltInitializePushLock` at `0x140094603`
- `FLTMGR!FltInitializePushLock` at `0x1400945d7`
- `FLTMGR!FltInitializePushLock` at `0x140094603`

## pseudocode

```c
__int64 MpDlpInitialize()
{
  unsigned __int64 *PoolWithTag; // rax
  NTSTATUS Callback; // ebx
  __int64 v2; // rdx
  unsigned __int64 *v3; // rcx
  _QWORD *v4; // rax
  int v5; // eax
  NTSTATUS v6; // eax
  ULONG Flags; // [rsp+20h] [rbp-28h]

  PoolWithTag = (unsigned __int64 *)MpAllocatePoolWithTag((unsigned int)ExDefaultNonPagedPoolType, 320, 1147424845);
  MpDlpData = PoolWithTag;
  if ( !PoolWithTag )
  {
    Callback = -1073741670;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_26;
    v2 = 10;
    Flags = -1073741670;
    goto LABEL_5;
  }
  *(_DWORD *)PoolWithTag = 21027357;
  *((_BYTE *)PoolWithTag + 32) = 0;
  *((_BYTE *)PoolWithTag + 240) = 0;
  *((_BYTE *)PoolWithTag + 241) = 0;
  *((_BYTE *)PoolWithTag + 265) = 0;
  *((_BYTE *)PoolWithTag + 269) = 0;
  *((_BYTE *)PoolWithTag + 266) = 0;
  *((_BYTE *)PoolWithTag + 267) = 0;
  *((_BYTE *)PoolWithTag + 268) = 0;
  FltInitializePushLock(PoolWithTag + 31);
  v3 = (unsigned __int64 *)MpDlpData;
  *((_QWORD *)MpDlpData + 32) = 0;
  v3[35] = 0;
  v3[36] = 0;
  FltInitializePushLock(v3 + 1);
  v4 = (char *)MpDlpData + 16;
  *((_QWORD *)MpDlpData + 3) = (char *)MpDlpData + 16;
  *v4 = v4;
  v5 = MpDlpInitializeEnlightenment();
  if ( v5 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    _mm_lfence();
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      11,
      WPP_4c1363a434f0368aee73563b7bc19017_Traceguids,
      KeGetCurrentThread(),
      v5);
  }
  v6 = ExInitializeLookasideListEx(
         (PLOOKASIDE_LIST_EX)((char *)MpDlpData + 48),
         0,
         0,
         PagedPool,
         0,
         0x400u,
         0x6C6D504Du,
         0);
  Callback = v6;
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_26;
    _mm_lfence();
    v2 = 12;
    Flags = v6;
    goto LABEL_5;
  }
  Callback = ExInitializeLookasideListEx(
               (PLOOKASIDE_LIST_EX)((char *)MpDlpData + 144),
               0,
               0,
               PagedPool,
               0,
               0x118u,
               0x736D504Du,
               0);
  if ( Callback < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_26;
    _mm_lfence();
    v2 = 13;
    Flags = Callback;
LABEL_5:
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      v2,
      WPP_4c1363a434f0368aee73563b7bc19017_Traceguids,
      KeGetCurrentThread(),
      Flags);
    goto LABEL_26;
  }
  Callback = MpCreateCallback((PCALLBACK_OBJECT *)MpDlpData + 38);
  if ( Callback >= 0 )
  {
    Callback = MpRegisterCallback(*((_QWORD *)MpDlpData + 38), MpDlpDeviceCallback, MpDlpData, (char *)MpDlpData + 312);
    if ( Callback >= 0 )
      return 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        WPP_4c1363a434f0368aee73563b7bc19017_Traceguids,
        (unsigned int)Callback);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    _mm_lfence();
    WPP_SF_SD(WPP_GLOBAL_Control->AttachedDevice);
  }
LABEL_26:
  MpDlpShutdown();
  return (unsigned int)Callback;
}

```

## disassembly

```asm
0x140094508  mov     [rsp+arg_0], rbx
0x14009450d  mov     [rsp+arg_8], rsi
0x140094512  push    r14
0x140094514  sub     rsp, 40h
0x140094518  mov     ecx, cs:ExDefaultNonPagedPoolType
0x14009451e  mov     edx, 140h
0x140094523  mov     r8d, 4464504Dh
0x140094529  call    MpAllocatePoolWithTag
0x14009452e  xor     r14d, r14d
0x140094531  mov     cs:MpDlpData, rax
0x140094538  test    rax, rax
0x14009453b  jnz     short loc_140094595
0x14009453d  mov     ebx, 0C000009Ah
0x140094542  mov     rax, cs:WPP_GLOBAL_Control
0x140094549  lea     rsi, WPP_GLOBAL_Control
0x140094550  cmp     rax, rsi
0x140094553  jz      loc_140094800
0x140094559  mov     eax, [rax+2Ch]
0x14009455c  test    al, 1
0x14009455e  jz      loc_140094800
0x140094564  lea     edx, [r14+0Ah]
0x140094568  mov     [rsp+48h+Flags], 0C000009Ah
0x140094570  mov     r9, gs:188h
0x140094579  lea     r8, WPP_4c1363a434f0368aee73563b7bc19017_Traceguids
0x140094580  mov     rcx, cs:WPP_GLOBAL_Control
0x140094587  mov     rcx, [rcx+18h]
0x14009458b  call    WPP_SF_qD
0x140094590  jmp     loc_140094800
0x140094595  mov     dword ptr [rax], 140DA1Dh
0x14009459b  lea     rcx, [rax+0F8h]; PushLock
0x1400945a2  mov     [rax+20h], r14b
0x1400945a6  mov     [rax+0F0h], r14b
0x1400945ad  mov     [rax+0F1h], r14b
0x1400945b4  mov     [rax+109h], r14b
0x1400945bb  mov     [rax+10Dh], r14b
0x1400945c2  mov     [rax+10Ah], r14b
0x1400945c9  mov     [rax+10Bh], r14b
0x1400945d0  mov     [rax+10Ch], r14b
0x1400945d7  call    cs:__imp_FltInitializePushLock
0x1400945de  nop     dword ptr [rax+rax+00h]
0x1400945e3  mov     rcx, cs:MpDlpData
0x1400945ea  mov     [rcx+100h], r14
0x1400945f1  mov     [rcx+118h], r14
0x1400945f8  mov     [rcx+120h], r14
0x1400945ff  add     rcx, 8; PushLock
0x140094603  call    cs:__imp_FltInitializePushLock
0x14009460a  nop     dword ptr [rax+rax+00h]
0x14009460f  mov     rax, cs:MpDlpData
0x140094616  add     rax, 10h
0x14009461a  mov     [rax+8], rax
0x14009461e  mov     [rax], rax
0x140094621  call    MpDlpInitializeEnlightenment
0x140094626  lea     rsi, WPP_GLOBAL_Control
0x14009462d  test    eax, eax
0x14009462f  jns     short loc_140094671
0x140094631  mov     rcx, cs:WPP_GLOBAL_Control
0x140094638  cmp     rcx, rsi
0x14009463b  jz      short loc_140094671
0x14009463d  mov     ecx, [rcx+2Ch]
0x140094640  test    cl, 1
0x140094643  jz      short loc_140094671
0x140094645  lfence
0x140094648  mov     r9, gs:188h
0x140094651  lea     r8, WPP_4c1363a434f0368aee73563b7bc19017_Traceguids
0x140094658  mov     rcx, cs:WPP_GLOBAL_Control
0x14009465f  mov     edx, 0Bh
0x140094664  mov     [rsp+48h+Flags], eax
0x140094668  mov     rcx, [rcx+18h]
0x14009466c  call    WPP_SF_qD
0x140094671  mov     rcx, cs:MpDlpData
0x140094678  mov     r9d, 1; PoolType
0x14009467e  mov     [rsp+48h+Depth], r14w; Depth
0x140094684  add     rcx, 30h ; '0'; Lookaside
0x140094688  mov     [rsp+48h+Tag], 6C6D504Dh; Tag
0x140094690  xor     r8d, r8d; Free
0x140094693  mov     [rsp+48h+Size], 400h; Size
0x14009469c  xor     edx, edx; Allocate
0x14009469e  mov     [rsp+48h+Flags], r14d; Flags
0x1400946a3  call    cs:__imp_ExInitializeLookasideListEx
0x1400946aa  nop     dword ptr [rax+rax+00h]
0x1400946af  mov     ebx, eax
0x1400946b1  test    eax, eax
0x1400946b3  jns     short loc_1400946E2
0x1400946b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400946bc  cmp     rcx, rsi
0x1400946bf  jz      loc_140094800
0x1400946c5  mov     ecx, [rcx+2Ch]
0x1400946c8  test    cl, 1
0x1400946cb  jz      loc_140094800
0x1400946d1  lfence
0x1400946d4  mov     edx, 0Ch
0x1400946d9  mov     [rsp+48h+Flags], eax
0x1400946dd  jmp     loc_140094570
0x1400946e2  mov     rcx, cs:MpDlpData
0x1400946e9  mov     r9d, 1; PoolType
0x1400946ef  mov     [rsp+48h+Depth], r14w; Depth
0x1400946f5  add     rcx, 90h; Lookaside
0x1400946fc  mov     [rsp+48h+Tag], 736D504Dh; Tag
0x140094704  xor     r8d, r8d; Free
0x140094707  mov     [rsp+48h+Size], 118h; Size
0x140094710  xor     edx, edx; Allocate
0x140094712  mov     [rsp+48h+Flags], r14d; Flags
0x140094717  call    cs:__imp_ExInitializeLookasideListEx
0x14009471e  nop     dword ptr [rax+rax+00h]
0x140094723  mov     ebx, eax
0x140094725  test    eax, eax
0x140094727  jns     short loc_140094755
0x140094729  mov     rax, cs:WPP_GLOBAL_Control
0x140094730  cmp     rax, rsi
0x140094733  jz      loc_140094800
0x140094739  mov     eax, [rax+2Ch]
0x14009473c  test    al, 1
0x14009473e  jz      loc_140094800
0x140094744  lfence
0x140094747  mov     edx, 0Dh
0x14009474c  mov     [rsp+48h+Flags], ebx
0x140094750  jmp     loc_140094570
0x140094755  mov     rcx, cs:MpDlpData
0x14009475c  lea     rdx, aCallbackWdddev; "\\Callback\\WddDeviceNotifcationsCallba"...
0x140094763  add     rcx, 130h; CallbackObject
0x14009476a  call    MpCreateCallback
0x14009476f  mov     ebx, eax
0x140094771  test    eax, eax
0x140094773  jns     short loc_1400947A1
0x140094775  mov     rax, cs:WPP_GLOBAL_Control
0x14009477c  cmp     rax, rsi
0x14009477f  jz      short loc_140094800
0x140094781  mov     eax, [rax+2Ch]
0x140094784  test    al, 1
0x140094786  jz      short loc_140094800
0x140094788  lfence
0x14009478b  mov     rcx, cs:WPP_GLOBAL_Control
0x140094792  mov     [rsp+48h+Flags], ebx
0x140094796  mov     rcx, [rcx+18h]
0x14009479a  call    WPP_SF_SD
0x14009479f  jmp     short loc_140094800
0x1400947a1  mov     rcx, cs:MpDlpData
0x1400947a8  lea     rdx, MpDlpDeviceCallback
0x1400947af  mov     r8, rcx
0x1400947b2  lea     r9, [rcx+138h]
0x1400947b9  mov     rcx, [rcx+130h]
0x1400947c0  call    MpRegisterCallback
0x1400947c5  mov     ebx, eax
0x1400947c7  test    eax, eax
0x1400947c9  jns     short loc_140094807
0x1400947cb  mov     rax, cs:WPP_GLOBAL_Control
0x1400947d2  cmp     rax, rsi
0x1400947d5  jz      short loc_140094800
0x1400947d7  mov     eax, [rax+2Ch]
0x1400947da  test    al, 1
0x1400947dc  jz      short loc_140094800
0x1400947de  lfence
0x1400947e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400947e8  lea     r8, WPP_4c1363a434f0368aee73563b7bc19017_Traceguids
0x1400947ef  mov     edx, 0Fh
0x1400947f4  mov     r9d, ebx
0x1400947f7  mov     rcx, [rcx+18h]
0x1400947fb  call    WPP_SF_d
0x140094800  call    MpDlpShutdown
0x140094805  jmp     short loc_14009480A
0x140094807  mov     ebx, r14d
0x14009480a  mov     rsi, [rsp+48h+arg_8]
0x14009480f  mov     eax, ebx
0x140094811  mov     rbx, [rsp+48h+arg_0]
0x140094816  add     rsp, 40h
0x14009481a  pop     r14
0x14009481c  retn
```
