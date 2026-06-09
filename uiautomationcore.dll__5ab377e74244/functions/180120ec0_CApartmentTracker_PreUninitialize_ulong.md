# CApartmentTracker::PreUninitialize(ulong)

- ea: `0x180120ec0`
- end: `0x180120f9a`
- name: `?PreUninitialize@CApartmentTracker@@UEAAJK@Z`
- size: `218`
- prototype: `__int64 __fastcall(CApartmentTracker *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180167b00`

## callees

- `0x1800d2f00`
- `0x180105e04`
- `0x180120ec0`
- `0x180120fa0`
- `0x18012b47c`
- `0x180130920`
- `0x180274e78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180120ef2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180120ef2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180120f39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180120f39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180120ef8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180120ef8`
- `ntdll!RtlDllShutdownInProgress` at `0x180120ecf`
- `ntdll!RtlDllShutdownInProgress` at `0x180120ecf`
- `api-ms-win-core-com-private-l1-1-0!CoRevokeInitializeSpy` at `0x180120f55`
- `api-ms-win-core-com-private-l1-1-0!CoRevokeInitializeSpy` at `0x180120f55`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CApartmentTracker::PreUninitialize(CApartmentTracker *this, int a2)
{
  __int64 v5; // rcx
  __int64 v6; // rcx
  RefcountBase *v7; // r11
  _QWORD v8[3]; // [rsp+20h] [rbp-18h] BYREF
  DWORD CurrentThreadId; // [rsp+50h] [rbp+18h] BYREF
  __int64 v10; // [rsp+58h] [rbp+20h] BYREF

  if ( !RtlDllShutdownInProgress() && a2 == 1 )
  {
    *((_DWORD *)this + 2) = 0;
    v10 = 0;
    if ( CoRevokeInitializeSpy(*(ULARGE_INTEGER *)((char *)this + 16)) >= 0 )
    {
      EnterCriticalSection(&CApartmentTracker::_classLock);
      CurrentThreadId = GetCurrentThreadId();
      std::_Hash<std::_Umap_traits<unsigned long,CApartmentTracker *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,CApartmentTracker *>>,0>>::find(
        v5,
        v8,
        &CurrentThreadId);
      if ( v8[0] != qword_18039F768 )
      {
        v10 = *(_QWORD *)(v8[0] + 24LL);
        std::_Hash<std::_Umap_traits<unsigned long,CApartmentTracker *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,CApartmentTracker *>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,CApartmentTracker *>>>>,0>(
          v6,
          &CurrentThreadId);
      }
      LeaveCriticalSection(&CApartmentTracker::_classLock);
    }
    while ( *((_QWORD *)this + 3) )
    {
      STATrackedObject::ReleaseContainedInterfaceIfValid(*((STATrackedObject **)this + 3));
      LinkBase<STATrackedObject *>::Unlink(*((_QWORD *)this + 3) + 16LL, (char *)this + 24);
      RefcountBase::Release(v7);
    }
    AutoRelease<EditTextRange *>::~AutoRelease<EditTextRange *>(&v10);
  }
  return 0;
}

```

## disassembly

```asm
0x180120ec0  mov     [rsp+arg_0], rbx
0x180120ec5  push    rdi
0x180120ec6  sub     rsp, 30h
0x180120eca  mov     edi, edx
0x180120ecc  mov     rbx, rcx
0x180120ecf  call    cs:__imp_RtlDllShutdownInProgress
0x180120ed5  test    al, al
0x180120ed7  jnz     short loc_180120EDE
0x180120ed9  cmp     edi, 1
0x180120edc  jz      short loc_180120F41
0x180120ede  xor     eax, eax
0x180120ee0  mov     rbx, [rsp+38h+arg_0]
0x180120ee5  add     rsp, 30h
0x180120ee9  pop     rdi
0x180120eea  retn
0x180120eeb  lea     rcx, ?_classLock@CApartmentTracker@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180120ef2  call    cs:__imp_EnterCriticalSection
0x180120ef8  call    cs:__imp_GetCurrentThreadId
0x180120efe  mov     [rsp+38h+arg_10], eax
0x180120f02  lea     r8, [rsp+38h+arg_10]
0x180120f07  lea     rdx, [rsp+38h+var_18]
0x180120f0c  call    ?find@?$_Hash@V?$_Umap_traits@KPEAVCApartmentTracker@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKPEAVCApartmentTracker@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAVCApartmentTracker@@@std@@@std@@@std@@@2@AEBK@Z; std::_Hash<std::_Umap_traits<ulong,CApartmentTracker *,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,CApartmentTracker *>>,0>>::find(ulong const &)
0x180120f11  mov     r8, [rsp+38h+var_18]
0x180120f16  cmp     r8, cs:qword_18039F768
0x180120f1d  jz      short loc_180120F32
0x180120f1f  mov     rax, [r8+18h]
0x180120f23  mov     [rsp+38h+arg_18], rax
0x180120f28  lea     rdx, [rsp+38h+arg_10]
0x180120f2d  call    ??$erase@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAVCApartmentTracker@@@std@@@std@@@std@@@std@@$0A@@?$_Hash@V?$_Umap_traits@KPEAVCApartmentTracker@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKPEAVCApartmentTracker@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAVCApartmentTracker@@@std@@@std@@@std@@@1@V21@@Z; std::_Hash<std::_Umap_traits<ulong,CApartmentTracker *,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,CApartmentTracker *>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,CApartmentTracker *>>>>,0>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,CApartmentTracker *>>>>)
0x180120f32  lea     rcx, ?_classLock@CApartmentTracker@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180120f39  call    cs:__imp_LeaveCriticalSection
0x180120f3f  jmp     short loc_180120F82
0x180120f41  mov     dword ptr [rbx+8], 0
0x180120f48  mov     [rsp+38h+arg_18], 0
0x180120f51  mov     rcx, [rbx+10h]; uliCookie
0x180120f55  call    cs:__imp_CoRevokeInitializeSpy
0x180120f5b  test    eax, eax
0x180120f5d  js      short loc_180120F82
0x180120f5f  jmp     short loc_180120EEB
0x180120f61  mov     rcx, rax; this
0x180120f64  call    ?ReleaseContainedInterfaceIfValid@STATrackedObject@@QEAAXXZ; STATrackedObject::ReleaseContainedInterfaceIfValid(void)
0x180120f69  mov     r11, [rbx+18h]
0x180120f6d  lea     rcx, [r11+10h]
0x180120f71  lea     rdx, [rbx+18h]
0x180120f75  call    ?Unlink@?$LinkBase@PEAVSTATrackedObject@@@@QEAAXPEAPEAVSTATrackedObject@@@Z; LinkBase<STATrackedObject *>::Unlink(STATrackedObject * *)
0x180120f7a  mov     rcx, r11; this
0x180120f7d  call    ?Release@RefcountBase@@QEAAKXZ; RefcountBase::Release(void)
0x180120f82  mov     rax, [rbx+18h]
0x180120f86  test    rax, rax
0x180120f89  jnz     short loc_180120F61
0x180120f8b  lea     rcx, [rsp+38h+arg_18]
0x180120f90  call    ??1?$AutoRelease@PEAVEditTextRange@@@@QEAA@XZ; AutoRelease<EditTextRange *>::~AutoRelease<EditTextRange *>(void)
0x180120f95  jmp     loc_180120EDE
```
