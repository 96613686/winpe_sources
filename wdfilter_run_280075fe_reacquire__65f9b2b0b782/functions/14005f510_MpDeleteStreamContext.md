# MpDeleteStreamContext

- ea: `0x14005f510`
- end: `0x14005f9fd`
- name: `MpDeleteStreamContext`
- size: `1261`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140003460`
- `0x14000583c`
- `0x1400058e8`
- `0x14000a7d8`
- `0x140030060`
- `0x1400346f0`
- `0x14005f510`
- `0x14005fa00`
- `0x14005fa84`
- `0x14005fb08`
- `0x140060234`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14005f982`
- `ntoskrnl!KeBugCheckEx` at `0x14005f982`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14005f7bf`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14005f7bf`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x14005f69e`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x14005f69e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f61d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f61d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f611`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f611`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005f5d2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005f5d2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005f5bd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005f5bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f66e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f743`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f75b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f934`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f94c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f9d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f9ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f66e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f743`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f75b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f934`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f94c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f9d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f9ec`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14005f7fa`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14005f7fa`
- `ntoskrnl!KeBugCheck` at `0x14005f994`
- `ntoskrnl!KeBugCheck` at `0x14005f994`
- `FLTMGR!FltReleaseContext` at `0x14005f651`
- `FLTMGR!FltReleaseContext` at `0x14005f651`
- `FLTMGR!FltReleasePushLock` at `0x14005f8bf`
- `FLTMGR!FltReleasePushLock` at `0x14005f8e3`
- `FLTMGR!FltReleasePushLock` at `0x14005f8bf`
- `FLTMGR!FltReleasePushLock` at `0x14005f8e3`
- `FLTMGR!FltDeletePushLock` at `0x14005f57e`
- `FLTMGR!FltDeletePushLock` at `0x14005f591`
- `FLTMGR!FltDeletePushLock` at `0x14005f5a4`
- `FLTMGR!FltDeletePushLock` at `0x14005f57e`
- `FLTMGR!FltDeletePushLock` at `0x14005f591`
- `FLTMGR!FltDeletePushLock` at `0x14005f5a4`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x14005f85f`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x14005f85f`

## pseudocode

```c
void __fastcall MpDeleteStreamContext(__int64 a1, unsigned __int16 a2)
{
  void *v3; // rcx
  __int64 v4; // r8
  __int64 *v5; // rsi
  __int64 v6; // rbx
  __int64 *v7; // rcx
  __int64 **v8; // rax
  PDEVICE_OBJECT v9; // rcx
  void *v10; // rcx
  void *v11; // rdx
  PSLIST_ENTRY v12; // rbx
  int v13; // r8d
  _QWORD **v14; // rbx
  _QWORD *v15; // rsi
  _QWORD **v16; // rbx
  _QWORD *v17; // rsi
  void *v18; // rcx
  _QWORD *v19; // rax
  __int64 v20; // rcx
  void *v21; // rcx
  _QWORD *v22; // rax
  void *v23; // rcx
  _QWORD *v24; // rax
  _QWORD *v25; // rcx
  _QWORD *v26; // rdx
  _QWORD *p_Next; // rsi
  __int64 v28; // rcx
  void *v29; // rcx

  if ( a2 != 8 )
    KeBugCheckEx(0x108u, a2, 8u, 0, 0);
  v3 = *(void **)(a1 + 200);
  if ( v3 )
  {
    ObDereferenceObjectDeferDelete(v3);
    if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
    {
      if ( KdRefreshDebuggerNotPresent() )
        KeBugCheck(1u);
      __debugbreak();
    }
  }
  if ( (*(_DWORD *)(a1 + 48) & 6) == 0 )
  {
    if ( dword_140026A00 == 1 )
      MpSaveStreamStateToCsvCache(a1);
    if ( dword_140026A04 == 1 )
      MpSaveStreamStateToRefsCache(a1);
    if ( dword_140026A08 == 1 )
      MpSaveStreamStateToNtfsCache(a1);
  }
  FltDeletePushLock((PULONG_PTR)(a1 + 192));
  FltDeletePushLock((PULONG_PTR)(a1 + 288));
  FltDeletePushLock((PULONG_PTR)(a1 + 624));
  v5 = (__int64 *)(a1 + 16);
  if ( (__int64 *)*v5 != v5 )
  {
    v6 = *(_QWORD *)(a1 + 8);
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite((PERESOURCE)(v6 + 288), 1u);
    v7 = (__int64 *)*v5;
    if ( *(__int64 **)(*v5 + 8) != v5 )
      goto LABEL_62;
    v8 = *(__int64 ***)(a1 + 24);
    if ( *v8 != v5 )
      goto LABEL_62;
    *v8 = v7;
    v7[1] = (__int64)v8;
    --*(_DWORD *)(*(_QWORD *)(a1 + 8) + 4LL);
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(a1 + 8) + 288LL));
    KeLeaveCriticalRegion();
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_qLZ(
      WPP_GLOBAL_Control->AttachedDevice,
      50,
      (unsigned int)WPP_49dcc05efb723005c5388b24d04d6cac_Traceguids,
      a1,
      *(_DWORD *)(*(_QWORD *)(a1 + 8) + 4LL),
      a1 + 240);
  if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 0x40) != 0 )
    McTemplateK0x_EtwWriteTransfer(v9, AMFilter_DeleteStreamContextEvent, v4, *(unsigned int *)(a1 + 168));
  FltReleaseContext(*(PFLT_CONTEXT *)(a1 + 8));
  v10 = *(void **)(a1 + 144);
  if ( v10 )
    ExFreePoolWithTag(v10, 0x6573504Du);
  v11 = *(void **)(a1 + 152);
  if ( v11 )
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(MpData + 1408), v11);
  if ( (*(_DWORD *)(a1 + 48) & 0x10000) == 0 )
    goto LABEL_22;
  FltAcquirePushLockExclusive((PULONG_PTR)MpDlpData + 1);
  v24 = (_QWORD *)*((_QWORD *)MpDlpData + 2);
  do
  {
    if ( v24 == (_QWORD *)((char *)MpDlpData + 16) )
    {
      FltReleasePushLock((PULONG_PTR)MpDlpData + 1);
      goto LABEL_22;
    }
    v25 = v24;
    v24 = (_QWORD *)*v24;
  }
  while ( v25[3] != a1 );
  if ( (_QWORD *)v24[1] != v25 || (v26 = (_QWORD *)v25[1], (_QWORD *)*v26 != v25) )
LABEL_62:
    __fastfail(3u);
  *v26 = v24;
  v24[1] = v26;
  MpDeleteDlpSectionFileNameEntry(v25);
  FltReleasePushLock((PULONG_PTR)MpDlpData + 1);
  MpDlpProcessRemoveSensitiveSectionFromRunningProcesses(a1);
LABEL_22:
  v12 = ExpInterlockedFlushSList((PSLIST_HEADER)(a1 + 272));
  while ( v12 )
  {
    p_Next = &v12->Next;
    v12 = v12->Next;
    MpDlpOnFileObjectClose(0, (_DWORD)p_Next + 24, v13, 3, 0, 0);
    v28 = p_Next[2];
    if ( v28 )
    {
      MpReleaseProcessContext(v28);
      p_Next[2] = 0;
    }
    v29 = (void *)p_Next[4];
    if ( v29 )
    {
      ExFreePoolWithTag(v29, 0x6E66504Du);
      p_Next[4] = 0;
    }
    ExFreePoolWithTag(p_Next, 0x6670504Du);
  }
  v14 = (_QWORD **)(a1 + 296);
  while ( 1 )
  {
    v15 = *v14;
    if ( *v14 == v14 )
      break;
    if ( (_QWORD **)v15[1] != v14 )
      goto LABEL_62;
    v19 = (_QWORD *)*v15;
    if ( *(_QWORD **)(*v15 + 8LL) != v15 )
      goto LABEL_62;
    *v14 = v19;
    v19[1] = v14;
    if ( v15 )
    {
      v20 = v15[2];
      if ( v20 )
      {
        MpReleaseProcessContext(v20);
        v15[2] = 0;
      }
      v21 = (void *)v15[4];
      if ( v21 )
      {
        ExFreePoolWithTag(v21, 0x6E66504Du);
        v15[4] = 0;
      }
      ExFreePoolWithTag(v15, 0x6670504Du);
    }
  }
  v16 = (_QWORD **)(a1 + 312);
  while ( 1 )
  {
    v17 = *v16;
    if ( *v16 == v16 )
      break;
    if ( (_QWORD **)v17[1] != v16 )
      goto LABEL_62;
    v22 = (_QWORD *)*v17;
    if ( *(_QWORD **)(*v17 + 8LL) != v17 )
      goto LABEL_62;
    *v16 = v22;
    v22[1] = v16;
    v23 = (void *)v17[3];
    if ( v23 )
      ExFreePoolWithTag(v23, 0x6165504Du);
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(MpData + 1280), v17);
  }
  v18 = *(void **)(a1 + 248);
  if ( v18 )
    ExFreePoolWithTag(v18, 0x6E66504Du);
}

```

## disassembly

```asm
0x14005f510  mov     [rsp+arg_10], rbp
0x14005f515  push    rdi
0x14005f516  sub     rsp, 30h
0x14005f51a  mov     rdi, rcx
0x14005f51d  cmp     dx, 8
0x14005f521  jnz     loc_14005F96A
0x14005f527  mov     rcx, [rcx+0C8h]; Object
0x14005f52e  test    rcx, rcx
0x14005f531  jnz     loc_14005F7BF
0x14005f537  mov     eax, [rdi+30h]
0x14005f53a  mov     [rsp+38h+arg_8], rsi
0x14005f53f  test    al, 6
0x14005f541  jnz     short loc_14005F572
0x14005f543  cmp     cs:dword_140026A00, 1
0x14005f54a  jz      loc_14005F7B2
0x14005f550  cmp     cs:dword_140026A04, 1
0x14005f557  jnz     short loc_14005F561
0x14005f559  mov     rcx, rdi
0x14005f55c  call    MpSaveStreamStateToRefsCache
0x14005f561  cmp     cs:dword_140026A08, 1
0x14005f568  jnz     short loc_14005F572
0x14005f56a  mov     rcx, rdi
0x14005f56d  call    MpSaveStreamStateToNtfsCache
0x14005f572  lea     rcx, [rdi+0C0h]; PushLock
0x14005f579  mov     [rsp+38h+arg_0], rbx
0x14005f57e  call    cs:__imp_FltDeletePushLock
0x14005f585  nop     dword ptr [rax+rax+00h]
0x14005f58a  lea     rcx, [rdi+120h]; PushLock
0x14005f591  call    cs:__imp_FltDeletePushLock
0x14005f598  nop     dword ptr [rax+rax+00h]
0x14005f59d  lea     rcx, [rdi+270h]; PushLock
0x14005f5a4  call    cs:__imp_FltDeletePushLock
0x14005f5ab  nop     dword ptr [rax+rax+00h]
0x14005f5b0  lea     rsi, [rdi+10h]
0x14005f5b4  cmp     [rsi], rsi
0x14005f5b7  jz      short loc_14005F629
0x14005f5b9  mov     rbx, [rdi+8]
0x14005f5bd  call    cs:__imp_KeEnterCriticalRegion
0x14005f5c4  nop     dword ptr [rax+rax+00h]
0x14005f5c9  mov     dl, 1; Wait
0x14005f5cb  lea     rcx, [rbx+120h]; Resource
0x14005f5d2  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14005f5d9  nop     dword ptr [rax+rax+00h]
0x14005f5de  mov     rcx, [rsi]
0x14005f5e1  cmp     [rcx+8], rsi
0x14005f5e5  jnz     loc_14005F963
0x14005f5eb  mov     rax, [rsi+8]
0x14005f5ef  cmp     [rax], rsi
0x14005f5f2  jnz     loc_14005F963
0x14005f5f8  mov     [rax], rcx
0x14005f5fb  mov     [rcx+8], rax
0x14005f5ff  mov     rax, [rdi+8]
0x14005f603  dec     dword ptr [rax+4]
0x14005f606  mov     rcx, [rdi+8]
0x14005f60a  add     rcx, 120h; Resource
0x14005f611  call    cs:__imp_ExReleaseResourceLite
0x14005f618  nop     dword ptr [rax+rax+00h]
0x14005f61d  call    cs:__imp_KeLeaveCriticalRegion
0x14005f624  nop     dword ptr [rax+rax+00h]
0x14005f629  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f630  lea     rax, WPP_GLOBAL_Control
0x14005f637  cmp     rcx, rax
0x14005f63a  jnz     loc_14005F814
0x14005f640  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, 40h
0x14005f647  jnz     loc_14005F9A1
0x14005f64d  mov     rcx, [rdi+8]; Context
0x14005f651  call    cs:__imp_FltReleaseContext
0x14005f658  nop     dword ptr [rax+rax+00h]
0x14005f65d  mov     rcx, [rdi+90h]; P
0x14005f664  test    rcx, rcx
0x14005f667  jz      short loc_14005F67A
0x14005f669  mov     edx, 6573504Dh; Tag
0x14005f66e  call    cs:__imp_ExFreePoolWithTag
0x14005f675  nop     dword ptr [rax+rax+00h]
0x14005f67a  mov     rdx, [rdi+98h]; Entry
0x14005f681  test    rdx, rdx
0x14005f684  jnz     loc_14005F9B9
0x14005f68a  test    dword ptr [rdi+30h], 10000h
0x14005f691  jnz     loc_14005F854
0x14005f697  lea     rcx, [rdi+110h]; ListHead
0x14005f69e  call    cs:__imp_ExpInterlockedFlushSList
0x14005f6a5  nop     dword ptr [rax+rax+00h]
0x14005f6aa  xor     ebp, ebp
0x14005f6ac  mov     rbx, rax
0x14005f6af  test    rax, rax
0x14005f6b2  jnz     loc_14005F8F4
0x14005f6b8  lea     rbx, [rdi+128h]
0x14005f6bf  mov     rsi, [rbx]
0x14005f6c2  cmp     rsi, rbx
0x14005f6c5  jnz     short loc_14005F700
0x14005f6c7  lea     rbx, [rdi+138h]
0x14005f6ce  mov     rsi, [rbx]
0x14005f6d1  cmp     rsi, rbx
0x14005f6d4  jnz     loc_14005F76C
0x14005f6da  mov     rcx, [rdi+0F8h]; P
0x14005f6e1  test    rcx, rcx
0x14005f6e4  jnz     loc_14005F9E7
0x14005f6ea  mov     rbx, [rsp+38h+arg_0]
0x14005f6ef  mov     rsi, [rsp+38h+arg_8]
0x14005f6f4  mov     rbp, [rsp+38h+arg_10]
0x14005f6f9  add     rsp, 30h
0x14005f6fd  pop     rdi
0x14005f6fe  retn
0x14005f700  cmp     [rsi+8], rbx
0x14005f704  jnz     loc_14005F963
0x14005f70a  mov     rax, [rsi]
0x14005f70d  cmp     [rax+8], rsi
0x14005f711  jnz     loc_14005F963
0x14005f717  mov     [rbx], rax
0x14005f71a  mov     [rax+8], rbx
0x14005f71e  test    rsi, rsi
0x14005f721  jz      short loc_14005F6BF
0x14005f723  mov     rcx, [rsi+10h]
0x14005f727  test    rcx, rcx
0x14005f72a  jz      short loc_14005F735
0x14005f72c  call    MpReleaseProcessContext
0x14005f731  mov     [rsi+10h], rbp
0x14005f735  mov     rcx, [rsi+20h]; P
0x14005f739  test    rcx, rcx
0x14005f73c  jz      short loc_14005F753
0x14005f73e  mov     edx, 6E66504Dh; Tag
0x14005f743  call    cs:__imp_ExFreePoolWithTag
0x14005f74a  nop     dword ptr [rax+rax+00h]
0x14005f74f  mov     [rsi+20h], rbp
0x14005f753  mov     edx, 6670504Dh; Tag
0x14005f758  mov     rcx, rsi; P
0x14005f75b  call    cs:__imp_ExFreePoolWithTag
0x14005f762  nop     dword ptr [rax+rax+00h]
0x14005f767  jmp     loc_14005F6BF
0x14005f76c  cmp     [rsi+8], rbx
0x14005f770  jnz     loc_14005F963
0x14005f776  mov     rax, [rsi]
0x14005f779  cmp     [rax+8], rsi
0x14005f77d  jnz     loc_14005F963
0x14005f783  mov     [rbx], rax
0x14005f786  mov     [rax+8], rbx
0x14005f78a  mov     rcx, [rsi+18h]; P
0x14005f78e  test    rcx, rcx
0x14005f791  jnz     loc_14005F9D1
0x14005f797  mov     rcx, cs:MpData
0x14005f79e  mov     rdx, rsi; Entry
0x14005f7a1  add     rcx, 500h; Lookaside
0x14005f7a8  call    ExFreeToNPagedLookasideList
0x14005f7ad  jmp     loc_14005F6CE
0x14005f7b2  mov     rcx, rdi; int
0x14005f7b5  call    MpSaveStreamStateToCsvCache
0x14005f7ba  jmp     loc_14005F550
0x14005f7bf  call    cs:__imp_ObDereferenceObjectDeferDelete
0x14005f7c6  nop     dword ptr [rax+rax+00h]
0x14005f7cb  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14005f7d2  lock xadd cs:ObTotalReferences, rax
0x14005f7db  cmp     rax, 1
0x14005f7df  jns     loc_14005F537
0x14005f7e5  mov     rax, cs:MpData
0x14005f7ec  mov     ecx, [rax+364h]
0x14005f7f2  test    ecx, ecx
0x14005f7f4  jns     loc_14005F537
0x14005f7fa  call    cs:__imp_KdRefreshDebuggerNotPresent
0x14005f801  nop     dword ptr [rax+rax+00h]
0x14005f806  test    al, al
0x14005f808  jnz     loc_14005F98F
0x14005f80e  int     3; Trap to Debugger
0x14005f80f  jmp     loc_14005F537
0x14005f814  mov     eax, [rcx+2Ch]
0x14005f817  test    al, 4
0x14005f819  jz      loc_14005F640
0x14005f81f  mov     r8, [rdi+8]
0x14005f823  lea     rax, [rdi+0F0h]
0x14005f82a  mov     rcx, [rcx+18h]
0x14005f82e  mov     edx, 32h ; '2'
0x14005f833  mov     [rsp+38h+var_10], rax
0x14005f838  mov     r9, rdi
0x14005f83b  mov     eax, [r8+4]
0x14005f83f  lea     r8, WPP_49dcc05efb723005c5388b24d04d6cac_Traceguids
0x14005f846  mov     dword ptr [rsp+38h+BugCheckParameter4], eax
0x14005f84a  call    WPP_SF_qLZ
0x14005f84f  jmp     loc_14005F640
0x14005f854  mov     rcx, cs:MpDlpData
0x14005f85b  add     rcx, 8; PushLock
0x14005f85f  call    cs:__imp_FltAcquirePushLockExclusive
0x14005f866  nop     dword ptr [rax+rax+00h]
0x14005f86b  mov     rdx, cs:MpDlpData
0x14005f872  add     rdx, 10h
0x14005f876  mov     rax, [rdx]
0x14005f879  nop     dword ptr [rax+00000000h]
0x14005f880  cmp     rax, rdx
0x14005f883  jz      short loc_14005F8D8
0x14005f885  mov     rcx, rax; P
0x14005f888  mov     rax, [rax]
0x14005f88b  cmp     [rcx+18h], rdi
0x14005f88f  jnz     short loc_14005F880
0x14005f891  cmp     [rax+8], rcx
0x14005f895  jnz     loc_14005F963
0x14005f89b  mov     rdx, [rcx+8]
0x14005f89f  cmp     [rdx], rcx
0x14005f8a2  jnz     loc_14005F963
0x14005f8a8  mov     [rdx], rax
0x14005f8ab  mov     [rax+8], rdx
0x14005f8af  call    MpDeleteDlpSectionFileNameEntry
0x14005f8b4  mov     rcx, cs:MpDlpData
0x14005f8bb  add     rcx, 8; PushLock
0x14005f8bf  call    cs:__imp_FltReleasePushLock
0x14005f8c6  nop     dword ptr [rax+rax+00h]
0x14005f8cb  mov     rcx, rdi
0x14005f8ce  call    MpDlpProcessRemoveSensitiveSectionFromRunningProcesses
0x14005f8d3  jmp     loc_14005F697
0x14005f8d8  mov     rcx, cs:MpDlpData
0x14005f8df  add     rcx, 8; PushLock
0x14005f8e3  call    cs:__imp_FltReleasePushLock
0x14005f8ea  nop     dword ptr [rax+rax+00h]
0x14005f8ef  jmp     loc_14005F697
0x14005f8f4  mov     rsi, rbx
0x14005f8f7  mov     dword ptr [rsp+38h+var_10], ebp
0x14005f8fb  mov     rbx, [rbx]
0x14005f8fe  xor     ecx, ecx
0x14005f900  mov     r9d, 3
0x14005f906  mov     byte ptr [rsp+38h+BugCheckParameter4], bpl
0x14005f90b  lea     rdx, [rsi+18h]
0x14005f90f  call    MpDlpOnFileObjectClose
0x14005f914  mov     rcx, [rsi+10h]
0x14005f918  test    rcx, rcx
0x14005f91b  jz      short loc_14005F926
0x14005f91d  call    MpReleaseProcessContext
0x14005f922  mov     [rsi+10h], rbp
0x14005f926  mov     rcx, [rsi+20h]; P
0x14005f92a  test    rcx, rcx
0x14005f92d  jz      short loc_14005F944
0x14005f92f  mov     edx, 6E66504Dh; Tag
0x14005f934  call    cs:__imp_ExFreePoolWithTag
0x14005f93b  nop     dword ptr [rax+rax+00h]
0x14005f940  mov     [rsi+20h], rbp
0x14005f944  mov     edx, 6670504Dh; Tag
0x14005f949  mov     rcx, rsi; P
0x14005f94c  call    cs:__imp_ExFreePoolWithTag
0x14005f953  nop     dword ptr [rax+rax+00h]
0x14005f958  test    rbx, rbx
0x14005f95b  jz      loc_14005F6B8
0x14005f961  jmp     short loc_14005F8F4
0x14005f963  mov     ecx, 3
0x14005f968  int     29h; Win8: RtlFailFast(ecx)
0x14005f96a  xor     ebp, ebp
0x14005f96c  movzx   edx, dx; BugCheckParameter1
0x14005f96f  xor     r9d, r9d; BugCheckParameter3
0x14005f972  mov     [rsp+38h+BugCheckParameter4], rbp; BugCheckParameter4
0x14005f977  mov     ecx, 108h; BugCheckCode
0x14005f97c  mov     r8d, 8; BugCheckParameter2
0x14005f982  call    cs:__imp_KeBugCheckEx
0x14005f98f  mov     ecx, 1; BugCheckCode
0x14005f994  call    cs:__imp_KeBugCheck
0x14005f9a1  mov     r9d, [rdi+0A8h]
0x14005f9a8  lea     rdx, AMFilter_DeleteStreamContextEvent
0x14005f9af  call    McTemplateK0x_EtwWriteTransfer
0x14005f9b4  jmp     loc_14005F64D
0x14005f9b9  mov     rcx, cs:MpData
0x14005f9c0  add     rcx, 580h; Lookaside
0x14005f9c7  call    ExFreeToNPagedLookasideList
0x14005f9cc  jmp     loc_14005F68A
0x14005f9d1  mov     edx, 6165504Dh; Tag
0x14005f9d6  call    cs:__imp_ExFreePoolWithTag
0x14005f9dd  nop     dword ptr [rax+rax+00h]
0x14005f9e2  jmp     loc_14005F797
0x14005f9e7  mov     edx, 6E66504Dh; Tag
0x14005f9ec  call    cs:__imp_ExFreePoolWithTag
0x14005f9f3  nop     dword ptr [rax+rax+00h]
0x14005f9f8  jmp     loc_14005F6EA
```
