# DiskMonitor::StopMonitoringDisks(void)

- ea: `0x18006db68`
- end: `0x18006dc38`
- name: `?StopMonitoringDisks@DiskMonitor@@QEAAXXZ`
- size: `208`
- prototype: `void __fastcall(DiskMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800206d4`

## callees

- `0x18006c37c`
- `0x18006c3c8`
- `0x18006db68`
- `0x18006e064`
- `0x18006e0dc`
- `0x18006e11c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18006dc27`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18006dc27`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006dbc9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006dbc9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006dba4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006dba4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006db9a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006db9a`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18006db7e`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18006db7e`

## pseudocode

```c
void __fastcall DiskMonitor::StopMonitoringDisks(DiskMonitor *this)
{
  struct _TP_TIMER *v2; // rcx
  unsigned int v3; // edx
  __int64 v4; // rax
  DiskInfo *v5; // rcx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 7) )
  {
    CM_Unregister_Notification();
    *((_QWORD *)this + 7) = 0;
  }
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 9);
  if ( v2 )
  {
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 9));
    *((_QWORD *)this + 9) = 0;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1>::GetImpl'::`2'::impl) )
    WaitForSingleObject(*((HANDLE *)this + 5), 0xFFFFFFFF);
  std::_Tree<std::_Tmap_traits<int,DiskInfo *,std::less<int>,std::allocator<std::pair<int const,DiskInfo *>>,0>>::clear((char *)this + 8);
  v4 = **((_QWORD **)this + 3);
  v6 = v4;
  while ( v4 != *((_QWORD *)this + 3) )
  {
    v5 = *(DiskInfo **)(v4 + 64);
    if ( v5 )
      DiskInfo::`scalar deleting destructor'(v5, v3);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,VolumeInfo *>>>,std::_Iterator_base0>::operator++(&v6);
    v4 = v6;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1>::GetImpl'::`2'::impl) )
  {
    std::_Tree<std::_Tmap_traits<std::wstring,DiskInfo *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,DiskInfo *>>,0>>::clear((char *)this + 24);
    ReleaseMutex(*((HANDLE *)this + 5));
  }
}

```

## disassembly

```asm
0x18006db68  mov     [rsp+arg_8], rbx
0x18006db6d  push    rdi
0x18006db6e  sub     rsp, 20h
0x18006db72  mov     rbx, rcx
0x18006db75  mov     rcx, [rcx+38h]
0x18006db79  test    rcx, rcx
0x18006db7c  jz      short loc_18006DB8C
0x18006db7e  call    cs:__imp_CM_Unregister_Notification
0x18006db84  mov     qword ptr [rbx+38h], 0
0x18006db8c  mov     rcx, [rbx+48h]; pti
0x18006db90  test    rcx, rcx
0x18006db93  jz      short loc_18006DBB2
0x18006db95  mov     edx, 1; fCancelPendingCallbacks
0x18006db9a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18006dba0  mov     rcx, [rbx+48h]; pti
0x18006dba4  call    cs:__imp_CloseThreadpoolTimer
0x18006dbaa  mov     qword ptr [rbx+48h], 0
0x18006dbb2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1> `wil::Feature<__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1>::GetImpl(void)'::`2'::impl
0x18006dbb9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1>::__private_IsEnabled(void)
0x18006dbbe  test    al, al
0x18006dbc0  jz      short loc_18006DBCF
0x18006dbc2  mov     rcx, [rbx+28h]; hHandle
0x18006dbc6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18006dbc9  call    cs:__imp_WaitForSingleObject
0x18006dbcf  lea     rcx, [rbx+8]
0x18006dbd3  call    ?clear@?$_Tree@V?$_Tmap_traits@HPEAVDiskInfo@@U?$less@H@std@@V?$allocator@U?$pair@$$CBHPEAVDiskInfo@@@std@@@3@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<int,DiskInfo *,std::less<int>,std::allocator<std::pair<int const,DiskInfo *>>,0>>::clear(void)
0x18006dbd8  lea     rdi, [rbx+18h]
0x18006dbdc  mov     rax, [rdi]
0x18006dbdf  mov     rax, [rax]
0x18006dbe2  mov     [rsp+28h+arg_0], rax
0x18006dbe7  cmp     rax, [rdi]
0x18006dbea  jz      short loc_18006DC0B
0x18006dbec  mov     rcx, [rax+40h]; this
0x18006dbf0  test    rcx, rcx
0x18006dbf3  jz      short loc_18006DBFA
0x18006dbf5  call    ??_GDiskInfo@@QEAAPEAXI@Z; DiskInfo::`scalar deleting destructor'(uint)
0x18006dbfa  lea     rcx, [rsp+28h+arg_0]
0x18006dbff  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVVolumeInfo@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,VolumeInfo *>>>,std::_Iterator_base0>::operator++(void)
0x18006dc04  mov     rax, [rsp+28h+arg_0]
0x18006dc09  jmp     short loc_18006DBE7
0x18006dc0b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1> `wil::Feature<__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1>::GetImpl(void)'::`2'::impl
0x18006dc12  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1>::__private_IsEnabled(void)
0x18006dc17  test    al, al
0x18006dc19  jz      short loc_18006DC2D
0x18006dc1b  mov     rcx, rdi
0x18006dc1e  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVDiskInfo@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVDiskInfo@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,DiskInfo *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,DiskInfo *>>,0>>::clear(void)
0x18006dc23  mov     rcx, [rbx+28h]; hMutex
0x18006dc27  call    cs:__imp_ReleaseMutex
0x18006dc2d  mov     rbx, [rsp+28h+arg_8]
0x18006dc32  add     rsp, 20h
0x18006dc36  pop     rdi
0x18006dc37  retn
```
