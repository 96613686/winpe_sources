# CInputHapticsManagerStatics::OnCreated(CInputHapticsManager *)

- ea: `0x1800c3b98`
- end: `0x1800c3c56`
- name: `?OnCreated@CInputHapticsManagerStatics@@SAXPEAVCInputHapticsManager@@@Z`
- size: `190`
- prototype: `void __fastcall(struct CInputHapticsManager *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c4540`

## callees

- `0x180036998`
- `0x1800c10f8`
- `0x1800c156c`
- `0x1800c3964`
- `0x1800c3b98`
- `0x1800c5bdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800c3bd3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800c3bd3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c3baf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c3baf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800c3c16`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800c3c16`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CInputHapticsManagerStatics::OnCreated(struct CInputHapticsManager *a1)
{
  __int64 i; // rbx
  DWORD v3; // ebx
  __int64 v4; // rcx
  _QWORD v5[2]; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v6[24]; // [rsp+30h] [rbp-18h] BYREF
  DWORD v7; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v8; // [rsp+58h] [rbp+10h] BYREF

  AcquireSRWLockExclusive(&CInputHapticsManagerStatics::s_managerMapLock);
  v8 = &CInputHapticsManagerStatics::s_managerMapLock;
  i = CInputHapticsManagerStatics::s_managerMap;
LABEL_2:
  for ( i = *(_QWORD *)i;
        i != CInputHapticsManagerStatics::s_managerMap;
        i = *(_QWORD *)std::_Hash<std::_Umap_traits<unsigned int,CInputHapticsManagerStatics::InputHapticsManagerEntry,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,CInputHapticsManagerStatics::InputHapticsManagerEntry>>,0>>::erase(
                         &CInputHapticsManagerStatics::s_managerMap,
                         &v7,
                         i) )
  {
    if ( WaitForSingleObject(*(HANDLE *)(i + 32), 0) )
      goto LABEL_2;
  }
  v7 = *((_DWORD *)a1 + 16);
  v3 = v7;
  v5[0] = a1;
  Microsoft::WRL::ComPtr<Windows::Devices::Haptics::IInputHapticsManager>::InternalAddRef(v5);
  v5[1] = OpenThread(0x100000u, 0, v3);
  std::_Hash<std::_Umap_traits<unsigned int,CInputHapticsManagerStatics::InputHapticsManagerEntry,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,CInputHapticsManagerStatics::InputHapticsManagerEntry>>,0>>::emplace<unsigned int &,CInputHapticsManagerStatics::InputHapticsManagerEntry>(
    v4,
    v6,
    &v7,
    v5);
  CInputHapticsManagerStatics::InputHapticsManagerEntry::~InputHapticsManagerEntry((CInputHapticsManagerStatics::InputHapticsManagerEntry *)v5);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v8);
}

```

## disassembly

```asm
0x1800c3b98  mov     [rsp+arg_10], rbx
0x1800c3b9d  push    rdi
0x1800c3b9e  sub     rsp, 40h
0x1800c3ba2  mov     rdi, rcx
0x1800c3ba5  lea     rbx, ?s_managerMapLock@CInputHapticsManagerStatics@@0Vsrwlock@wil@@A; wil::srwlock CInputHapticsManagerStatics::s_managerMapLock
0x1800c3bac  mov     rcx, rbx; SRWLock
0x1800c3baf  call    cs:__imp_AcquireSRWLockExclusive
0x1800c3bb5  mov     [rsp+48h+arg_8], rbx
0x1800c3bba  mov     rbx, cs:?s_managerMap@CInputHapticsManagerStatics@@0V?$unordered_map@IUInputHapticsManagerEntry@CInputHapticsManagerStatics@@U?$hash@I@std@@U?$equal_to@I@4@V?$allocator@U?$pair@$$CBIUInputHapticsManagerEntry@CInputHapticsManagerStatics@@@std@@@4@@std@@A; std::unordered_map<uint,CInputHapticsManagerStatics::InputHapticsManagerEntry> CInputHapticsManagerStatics::s_managerMap
0x1800c3bc1  mov     rbx, [rbx]
0x1800c3bc4  cmp     rbx, cs:?s_managerMap@CInputHapticsManagerStatics@@0V?$unordered_map@IUInputHapticsManagerEntry@CInputHapticsManagerStatics@@U?$hash@I@std@@U?$equal_to@I@4@V?$allocator@U?$pair@$$CBIUInputHapticsManagerEntry@CInputHapticsManagerStatics@@@std@@@4@@std@@A; std::unordered_map<uint,CInputHapticsManagerStatics::InputHapticsManagerEntry> CInputHapticsManagerStatics::s_managerMap
0x1800c3bcb  jz      short loc_1800C3BF6
0x1800c3bcd  xor     edx, edx; dwMilliseconds
0x1800c3bcf  mov     rcx, [rbx+20h]; hHandle
0x1800c3bd3  call    cs:__imp_WaitForSingleObject
0x1800c3bd9  test    eax, eax
0x1800c3bdb  jnz     short loc_1800C3BC1
0x1800c3bdd  mov     r8, rbx
0x1800c3be0  lea     rdx, [rsp+48h+arg_0]
0x1800c3be5  lea     rcx, ?s_managerMap@CInputHapticsManagerStatics@@0V?$unordered_map@IUInputHapticsManagerEntry@CInputHapticsManagerStatics@@U?$hash@I@std@@U?$equal_to@I@4@V?$allocator@U?$pair@$$CBIUInputHapticsManagerEntry@CInputHapticsManagerStatics@@@std@@@4@@std@@A; std::unordered_map<uint,CInputHapticsManagerStatics::InputHapticsManagerEntry> CInputHapticsManagerStatics::s_managerMap
0x1800c3bec  call    ?erase@?$_Hash@V?$_Umap_traits@IUInputHapticsManagerEntry@CInputHapticsManagerStatics@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIUInputHapticsManagerEntry@CInputHapticsManagerStatics@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIUInputHapticsManagerEntry@CInputHapticsManagerStatics@@@std@@@std@@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIUInputHapticsManagerEntry@CInputHapticsManagerStatics@@@std@@@std@@@std@@@2@@Z; std::_Hash<std::_Umap_traits<uint,CInputHapticsManagerStatics::InputHapticsManagerEntry,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,CInputHapticsManagerStatics::InputHapticsManagerEntry>>,0>>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,CInputHapticsManagerStatics::InputHapticsManagerEntry>>>>)
0x1800c3bf1  mov     rbx, [rax]
0x1800c3bf4  jmp     short loc_1800C3BC4
0x1800c3bf6  mov     ebx, [rdi+40h]
0x1800c3bf9  mov     [rsp+48h+arg_0], ebx
0x1800c3bfd  mov     [rsp+48h+var_28], rdi
0x1800c3c02  lea     rcx, [rsp+48h+var_28]
0x1800c3c07  call    ?InternalAddRef@?$ComPtr@UIInputHapticsManager@Haptics@Devices@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Devices::Haptics::IInputHapticsManager>::InternalAddRef(void)
0x1800c3c0c  mov     r8d, ebx; dwThreadId
0x1800c3c0f  xor     edx, edx; bInheritHandle
0x1800c3c11  mov     ecx, 100000h; dwDesiredAccess
0x1800c3c16  call    cs:__imp_OpenThread
0x1800c3c1c  mov     [rsp+48h+var_20], rax
0x1800c3c21  lea     r9, [rsp+48h+var_28]
0x1800c3c26  lea     r8, [rsp+48h+arg_0]
0x1800c3c2b  lea     rdx, [rsp+48h+var_18]
0x1800c3c30  call    ??$emplace@AEAIUInputHapticsManagerEntry@CInputHapticsManagerStatics@@@?$_Hash@V?$_Umap_traits@IUInputHapticsManagerEntry@CInputHapticsManagerStatics@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIUInputHapticsManagerEntry@CInputHapticsManagerStatics@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIUInputHapticsManagerEntry@CInputHapticsManagerStatics@@@std@@@std@@@std@@@std@@_N@1@AEAI$$QEAUInputHapticsManagerEntry@CInputHapticsManagerStatics@@@Z; std::_Hash<std::_Umap_traits<uint,CInputHapticsManagerStatics::InputHapticsManagerEntry,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,CInputHapticsManagerStatics::InputHapticsManagerEntry>>,0>>::emplace<uint &,CInputHapticsManagerStatics::InputHapticsManagerEntry>(uint &,CInputHapticsManagerStatics::InputHapticsManagerEntry &&)
0x1800c3c35  nop
0x1800c3c36  lea     rcx, [rsp+48h+var_28]; this
0x1800c3c3b  call    ??1InputHapticsManagerEntry@CInputHapticsManagerStatics@@QEAA@XZ; CInputHapticsManagerStatics::InputHapticsManagerEntry::~InputHapticsManagerEntry(void)
0x1800c3c40  nop
0x1800c3c41  lea     rcx, [rsp+48h+arg_8]
0x1800c3c46  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800c3c4b  mov     rbx, [rsp+48h+arg_10]
0x1800c3c50  add     rsp, 40h
0x1800c3c54  pop     rdi
0x1800c3c55  retn
```
