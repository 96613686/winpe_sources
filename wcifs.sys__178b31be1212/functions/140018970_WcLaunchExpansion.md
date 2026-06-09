# WcLaunchExpansion

- ea: `0x140018970`
- end: `0x140018b93`
- name: `WcLaunchExpansion`
- size: `547`
- prototype: `__int64 __fastcall(struct _FLT_INSTANCE *FltObject, struct _FILE_OBJECT *Object, __int64, struct _FLT_CALLBACK_DATA *, int, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140014008`
- `0x140017ef8`

## callees

- `0x1400016f0`
- `0x140004198`
- `0x140017d98`
- `0x140018970`
- `0x140019550`
- `0x14001b524`
- `0x14002eea4`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140018aab`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140018aab`
- `ntoskrnl!ExAcquireFastMutex` at `0x140018afc`
- `ntoskrnl!ExAcquireFastMutex` at `0x140018afc`
- `ntoskrnl!ExReleaseFastMutex` at `0x140018b27`
- `ntoskrnl!ExReleaseFastMutex` at `0x140018b27`
- `FLTMGR!FltCbdqInsertIo` at `0x140018ade`
- `FLTMGR!FltCbdqInsertIo` at `0x140018ade`

## pseudocode

```c
__int64 __fastcall WcLaunchExpansion(
        struct _FLT_INSTANCE *FltObject,
        struct _FILE_OBJECT *Object,
        __int64 a3,
        struct _FLT_CALLBACK_DATA *a4,
        int a5,
        int a6)
{
  __int64 v6; // rbp
  signed __int32 v7; // edi
  char v8; // r13
  __int64 UnionContext; // rax
  int v14; // edx
  int inserted; // ebx
  PVOID v16; // rdx
  __int64 v17; // rcx
  PVOID Entry; // [rsp+A0h] [rbp+18h] BYREF

  v6 = 0;
  v7 = 0;
  v8 = 0;
  if ( *(_QWORD *)(a3 + 80) )
    goto LABEL_11;
  Entry = 0;
  UnionContext = WcGetUnionContext(a4, FltObject, Object);
  v6 = UnionContext;
  if ( UnionContext )
  {
    if ( *(_DWORD *)(UnionContext + 24) == 2 )
    {
      inserted = -1073741823;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v14) = 2;
        WPP_RECORDER_SF_sD(
          wil_details_featureDescriptors_a->DeviceExtension,
          v14,
          10,
          21,
          (__int64)WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\expansion.c",
          196);
      }
      goto LABEL_19;
    }
    inserted = WcCreateExpansionContext(FltObject, UnionContext, a3, &Entry);
    if ( inserted < 0 )
    {
LABEL_19:
      WcReleaseUnionContext(v6);
      goto LABEL_20;
    }
    v16 = Entry;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)(a3 + 80), (signed __int64)Entry, 0) )
      ExFreeToNPagedLookasideList(&stru_14000E580, v16);
LABEL_11:
    if ( a6 == 19 )
      **(_DWORD **)(a3 + 80) |= 2u;
    v17 = *(_QWORD *)(a3 + 80);
    if ( a4 )
    {
      inserted = FltCbdqInsertIo((PFLT_CALLBACK_DATA_QUEUE)(v17 + 40), a4, 0, Object);
      if ( inserted < 0 )
        goto LABEL_18;
      v8 = 1;
    }
    else
    {
      ExAcquireFastMutex((PFAST_MUTEX)(v17 + 184));
      inserted = WcScheduleExpansionWorkItem(FltObject, Object);
      ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a3 + 80) + 184LL));
      if ( inserted < 0 )
        goto LABEL_18;
    }
    v7 = _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a3 + 80) + 248LL));
LABEL_18:
    if ( !v6 )
      goto LABEL_20;
    goto LABEL_19;
  }
  inserted = -1073741823;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v14) = 2;
    WPP_RECORDER_SF_sD(
      wil_details_featureDescriptors_a->DeviceExtension,
      v14,
      10,
      20,
      (__int64)WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\expansion.c",
      183);
  }
LABEL_20:
  WcTelemetryPostExpansionTrigger((_DWORD)Object, a5, a6, *(_QWORD *)(a3 + 80), v7, inserted, v8);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x140018970  mov     rax, rsp
0x140018973  push    rbx
0x140018974  push    rbp
0x140018975  push    rsi
0x140018976  push    rdi
0x140018977  push    r12
0x140018979  push    r13
0x14001897b  push    r14
0x14001897d  push    r15
0x14001897f  sub     rsp, 48h
0x140018983  xor     ebp, ebp
0x140018985  xor     edi, edi
0x140018987  xor     r13b, r13b
0x14001898a  mov     r14, r9
0x14001898d  mov     rsi, r8
0x140018990  mov     r12, rdx
0x140018993  mov     r15, rcx
0x140018996  cmp     [r8+50h], rdi
0x14001899a  jnz     loc_140018AB7
0x1400189a0  mov     r8, rdx
0x1400189a3  mov     [rax+18h], rdi
0x1400189a7  mov     rdx, rcx
0x1400189aa  mov     rcx, r9
0x1400189ad  call    WcGetUnionContext
0x1400189b2  mov     rbp, rax
0x1400189b5  test    rax, rax
0x1400189b8  jnz     short loc_140018A12
0x1400189ba  mov     ebx, 0C0000001h
0x1400189bf  lea     rax, WPP_RECORDER_INITIALIZED
0x1400189c6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400189cd  jz      loc_140018B57
0x1400189d3  mov     rcx, cs:wil_details_featureDescriptors_a
0x1400189da  lea     rax, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\wcifs\\expansio"...
0x1400189e1  mov     [rsp+88h+var_58], 5B7h
0x1400189e9  lea     r9d, [rdi+14h]
0x1400189ed  mov     [rsp+88h+var_60], rax
0x1400189f2  lea     r8d, [rdi+0Ah]
0x1400189f6  lea     rax, WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids
0x1400189fd  mov     dl, 2
0x1400189ff  mov     rcx, [rcx+40h]
0x140018a03  mov     [rsp+88h+var_68], rax
0x140018a08  call    WPP_RECORDER_SF_sD
0x140018a0d  jmp     loc_140018B57
0x140018a12  cmp     dword ptr [rax+18h], 2
0x140018a16  jnz     short loc_140018A72
0x140018a18  mov     ebx, 0C0000001h
0x140018a1d  lea     rax, WPP_RECORDER_INITIALIZED
0x140018a24  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140018a2b  jz      loc_140018B4F
0x140018a31  mov     rcx, cs:wil_details_featureDescriptors_a
0x140018a38  lea     rax, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\wcifs\\expansio"...
0x140018a3f  mov     r9d, 15h
0x140018a45  mov     [rsp+88h+var_58], 5C4h
0x140018a4d  mov     [rsp+88h+var_60], rax
0x140018a52  mov     dl, 2
0x140018a54  lea     rax, WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids
0x140018a5b  mov     rcx, [rcx+40h]
0x140018a5f  lea     r8d, [r9-0Bh]
0x140018a63  mov     [rsp+88h+var_68], rax
0x140018a68  call    WPP_RECORDER_SF_sD
0x140018a6d  jmp     loc_140018B4F
0x140018a72  lea     r9, [rsp+88h+Entry]
0x140018a7a  mov     r8, rsi
0x140018a7d  mov     rdx, rax
0x140018a80  mov     rcx, r15; Instance
0x140018a83  call    WcCreateExpansionContext
0x140018a88  mov     ebx, eax
0x140018a8a  test    eax, eax
0x140018a8c  js      loc_140018B4F
0x140018a92  mov     rdx, [rsp+88h+Entry]; Entry
0x140018a9a  xor     eax, eax
0x140018a9c  lock cmpxchg [rsi+50h], rdx
0x140018aa2  jz      short loc_140018AB7
0x140018aa4  lea     rcx, stru_14000E580; Lookaside
0x140018aab  call    cs:__imp_ExFreeToNPagedLookasideList
0x140018ab2  nop     dword ptr [rax+rax+00h]
0x140018ab7  cmp     [rsp+88h+arg_28], 13h
0x140018abf  jnz     short loc_140018AC8
0x140018ac1  mov     rax, [rsi+50h]
0x140018ac5  or      dword ptr [rax], 2
0x140018ac8  mov     rcx, [rsi+50h]
0x140018acc  test    r14, r14
0x140018acf  jz      short loc_140018AF5
0x140018ad1  add     rcx, 28h ; '('; Cbdq
0x140018ad5  mov     r9, r12; InsertContext
0x140018ad8  xor     r8d, r8d; Context
0x140018adb  mov     rdx, r14; Cbd
0x140018ade  call    cs:__imp_FltCbdqInsertIo
0x140018ae5  nop     dword ptr [rax+rax+00h]
0x140018aea  mov     ebx, eax
0x140018aec  test    eax, eax
0x140018aee  js      short loc_140018B4A
0x140018af0  mov     r13b, 1
0x140018af3  jmp     short loc_140018B37
0x140018af5  add     rcx, 0B8h; FastMutex
0x140018afc  call    cs:__imp_ExAcquireFastMutex
0x140018b03  nop     dword ptr [rax+rax+00h]
0x140018b08  mov     r8, [rsi+50h]
0x140018b0c  xor     r9d, r9d
0x140018b0f  mov     rdx, r12; Object
0x140018b12  mov     rcx, r15; FltObject
0x140018b15  call    WcScheduleExpansionWorkItem
0x140018b1a  mov     rcx, [rsi+50h]
0x140018b1e  mov     ebx, eax
0x140018b20  add     rcx, 0B8h; FastMutex
0x140018b27  call    cs:__imp_ExReleaseFastMutex
0x140018b2e  nop     dword ptr [rax+rax+00h]
0x140018b33  test    ebx, ebx
0x140018b35  js      short loc_140018B4A
0x140018b37  mov     rax, [rsi+50h]
0x140018b3b  mov     edi, 1
0x140018b40  lock xadd [rax+0F8h], edi
0x140018b48  inc     edi
0x140018b4a  test    rbp, rbp
0x140018b4d  jz      short loc_140018B57
0x140018b4f  mov     rcx, rbp
0x140018b52  call    WcReleaseUnionContext
0x140018b57  mov     r9, [rsi+50h]
0x140018b5b  mov     rcx, r12
0x140018b5e  mov     r8d, [rsp+88h+arg_28]
0x140018b66  mov     edx, [rsp+88h+arg_20]
0x140018b6d  mov     byte ptr [rsp+88h+var_58], r13b
0x140018b72  mov     dword ptr [rsp+88h+var_60], ebx
0x140018b76  mov     dword ptr [rsp+88h+var_68], edi
0x140018b7a  call    WcTelemetryPostExpansionTrigger
0x140018b7f  mov     eax, ebx
0x140018b81  add     rsp, 48h
0x140018b85  pop     r15
0x140018b87  pop     r14
0x140018b89  pop     r13
0x140018b8b  pop     r12
0x140018b8d  pop     rdi
0x140018b8e  pop     rsi
0x140018b8f  pop     rbp
0x140018b90  pop     rbx
0x140018b91  retn
```
