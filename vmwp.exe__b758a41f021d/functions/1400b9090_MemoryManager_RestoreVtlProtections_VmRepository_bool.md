# MemoryManager::RestoreVtlProtections(VmRepository *,bool)

- ea: `0x1400b9090`
- end: `0x1400b9938`
- name: `?RestoreVtlProtections@MemoryManager@@UEAAXPEAVVmRepository@@_N@Z`
- size: `2216`
- prototype: `void(MemoryManager *__hidden this, struct VmRepository *, bool)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400c2b6c`

## callees

- `0x140024330`
- `0x140024504`
- `0x140032620`
- `0x140035238`
- `0x140035a08`
- `0x140053de8`
- `0x140053f10`
- `0x140078628`
- `0x140083990`
- `0x1400a4b04`
- `0x1400b0b0c`
- `0x1400b8574`
- `0x1400b9090`
- `0x1400b9940`
- `0x1400ba144`
- `0x14011ea40`
- `0x14011edec`
- `0x14011f6fc`
- `0x140161200`
- `0x1401eedbc`
- `0x1401f0050`
- `0x1401f1cec`
- `0x1401f2588`
- `0x1401f2cb4`
- `0x1401f3234`
- `0x1401f4550`
- `0x1401ffd00`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1400b9627`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1400b9627`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1400b95c1`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1400b95c1`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1400b9837`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1400b9837`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1400b97ad`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1400b97ad`
- `api-ms-win-core-processthreads-l1-1-0!CreateRemoteThreadEx` at `0x1400b972d`
- `api-ms-win-core-processthreads-l1-1-0!CreateRemoteThreadEx` at `0x1400b972d`
- `ntdll!NtQuerySystemInformation` at `0x1400b92f3`
- `ntdll!NtQuerySystemInformation` at `0x1400b92f3`
- `ntdll!RtlNumberOfSetBitsUlongPtr` at `0x1400b9673`
- `ntdll!RtlNumberOfSetBitsUlongPtr` at `0x1400b9673`

## string_xrefs

- `0x1400b91b8`: `onecore\vm\common\vml\VmReaderWriterLock.h`
- `0x1400b93ca`: `onecore\vm\common\vml\VmReaderWriterLock.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall MemoryManager::RestoreVtlProtections(MemoryManager *this, struct VmRepository *a2, char a3)
{
  char v3; // bl
  __int64 v6; // r8
  int v7; // eax
  ULONG_PTR v8; // r14
  char v9; // si
  char v10; // r12
  MemoryBlock *First; // rdi
  MemoryBlock **v12; // rbx
  NTSTATUS v13; // eax
  __int64 v14; // rax
  __int64 v15; // rdi
  __int64 v16; // rax
  char *v17; // rsi
  __int64 v18; // r9
  __int64 v19; // r13
  __int64 *v20; // rbx
  __int64 v21; // rsi
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // r14
  __int64 v25; // rdi
  __int64 v26; // rax
  __int64 *v27; // rbx
  int v28; // r13d
  BOOL v29; // eax
  const char *v30; // r9
  const char *v31; // r9
  unsigned __int64 v32; // r12
  __int64 i; // rax
  unsigned __int64 v34; // r12
  unsigned __int64 v35; // r14
  unsigned __int64 j; // r12
  _QWORD *v37; // rax
  const char *v38; // r9
  __int64 **v39; // rcx
  __int64 *k; // rax
  __int64 *m; // rcx
  HANDLE *v42; // rbx
  HANDLE *v43; // rdi
  const char *v44; // r9
  unsigned int cbSize; // [rsp+20h] [rbp-558h]
  __int64 RemoteThread; // [rsp+40h] [rbp-538h] BYREF
  int v47; // [rsp+48h] [rbp-530h]
  _OWORD *v48; // [rsp+50h] [rbp-528h] BYREF
  char v49; // [rsp+58h] [rbp-520h]
  DWORD ExitCode[4]; // [rsp+60h] [rbp-518h] BYREF
  _QWORD v51[2]; // [rsp+70h] [rbp-508h] BYREF
  int v52; // [rsp+80h] [rbp-4F8h] BYREF
  ULONG_PTR Size; // [rsp+88h] [rbp-4F0h] BYREF
  __int128 v54; // [rsp+90h] [rbp-4E8h] BYREF
  __int64 v55; // [rsp+A0h] [rbp-4D8h]
  ULONG ReturnLength; // [rsp+A8h] [rbp-4D0h] BYREF
  __int64 v57; // [rsp+B0h] [rbp-4C8h] BYREF
  __int128 Value; // [rsp+B8h] [rbp-4C0h] BYREF
  __int64 v59; // [rsp+C8h] [rbp-4B0h]
  __int64 v60; // [rsp+D0h] [rbp-4A8h] BYREF
  char v61; // [rsp+D8h] [rbp-4A0h]
  _QWORD v62[2]; // [rsp+E0h] [rbp-498h] BYREF
  char *v63[2]; // [rsp+F0h] [rbp-488h] BYREF
  _OWORD v64[3]; // [rsp+100h] [rbp-478h] BYREF
  _BYTE SystemInformation[1040]; // [rsp+130h] [rbp-448h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+578h] [rbp+0h]

  v3 = a3;
  LOBYTE(ExitCode[0]) = a3;
  v47 = 0;
  if ( *((_DWORD *)this + 36) >= 0x700u )
  {
    v52 = 0;
    v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 464LL))(*((_QWORD *)this + 4));
    v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v6 + 88LL))(v6, &v52);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A25,
        (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
        (const char *)(unsigned int)v7,
        cbSize);
    if ( ((1 << v52) & 0x1C) == 0 )
    {
      *(_OWORD *)v63 = 0;
      VmRepositoryAutoLock::VmRepositoryAutoLock(v63, a2, 0);
      if ( SLODWORD(v63[1]) < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1A4A,
          (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
          (const char *)LODWORD(v63[1]),
          cbSize);
      v8 = *((_QWORD *)this + 20) + 24LL;
      if ( !(unsigned int)RrwLockAcquireShared(v8, 0xFFFFFFFFLL) )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x249,
          (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
          (const char *)0x102,
          cbSize);
      v9 = 0;
      v10 = 0;
      Size = v8;
      v51[0] = 0;
      First = (MemoryBlock *)MemoryBlockContainer::IteratorGetFirst(*((_QWORD *)this + 20), v51);
      if ( First )
      {
        v12 = (MemoryBlock **)v51[0];
        do
        {
          if ( *(_BYTE *)First )
          {
            if ( MemoryBlock::LoadVtlProtections(First, *((_DWORD *)this + 96), a2) )
            {
              v9 = 1;
              v10 = 1;
            }
            else if ( *((_QWORD *)First + 27) != *((_QWORD *)First + 28) )
            {
              v9 = 1;
            }
          }
          if ( v12 == *(MemoryBlock ***)(*((_QWORD *)this + 20) + 8LL) )
            break;
          First = *v12++;
        }
        while ( First );
        v3 = ExitCode[0];
      }
      RrwLockRelease(v8);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v63);
      if ( v10 )
        ++*((_DWORD *)this + 96);
      if ( !v3 && v9 )
      {
        if ( !MemoryManager::AreAnySecureVtlsEnabled(this) )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x1A83,
            (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
            (const char *)0x570,
            cbSize);
        memset_0(SystemInformation, 0, 0x408u);
        ReturnLength = 0;
        v13 = NtQuerySystemInformation(SystemNumaProcessorMap, SystemInformation, 0x408u, &ReturnLength);
        if ( v13 < 0 )
          wil::details::in1diag3::_Throw_NtStatus(
            retaddr,
            (void *)0x1A9A,
            (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
            (const char *)(unsigned int)v13,
            cbSize);
        v57 = Vml::VmSingletonObject<NumaPhysicalTopologyInfo,INumaPhysicalTopologyInfo>::OpenShared(retaddr);
        v14 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 8LL))(*((_QWORD *)this + 5));
        v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 88LL))(v14);
        RemoteThread = v15;
        v60 = 0;
        v61 = 0;
        v62[0] = 0;
        v62[1] = 0;
        v16 = std::_Allocate<16,std::_Default_allocate_traits>(64);
        *(_QWORD *)v16 = v16;
        *(_QWORD *)(v16 + 8) = v16;
        *(_QWORD *)(v16 + 16) = v16;
        *(_WORD *)(v16 + 24) = 257;
        v62[0] = v16;
        v17 = (char *)(*((_QWORD *)this + 20) + 24LL);
        Size = (ULONG_PTR)v17;
        if ( !(unsigned int)RrwLockAcquireShared(v17, 0xFFFFFFFFLL) )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x249,
            (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
            (const char *)0x102,
            cbSize);
        v63[0] = v17;
        v51[0] = 0;
        v19 = MemoryBlockContainer::IteratorGetFirst(*((_QWORD *)this + 20), v51);
        if ( v19 )
        {
          v20 = (__int64 *)v51[0];
          v21 = v57;
          do
          {
            if ( *(_BYTE *)v19 )
            {
              v51[0] = 0;
              v51[1] = 0;
              LOBYTE(v18) = 1;
              LOBYTE(v22) = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *, __int64))(*(_QWORD *)v21 + 16LL))(
                              v21,
                              *(unsigned __int8 *)(*(unsigned __int8 *)(v19 + 184) + v15 + 280),
                              v51,
                              v18);
              LOWORD(ExitCode[0]) = (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 48LL))(
                                      v21,
                                      v22);
              Value = 0;
              v23 = *(_QWORD *)(v19 + 232);
              *(_QWORD *)(v19 + 232) = 0;
              v24 = *(_QWORD *)(v19 + 224);
              *(_QWORD *)(v19 + 224) = 0;
              v25 = *(_QWORD *)(v19 + 216);
              *(_QWORD *)(v19 + 216) = 0;
              *(_QWORD *)&Value = v25;
              *((_QWORD *)&Value + 1) = v24;
              v59 = v23;
              v26 = std::map<unsigned short,std::vector<MemoryBlockVtlProtectionChunk>>::_Try_emplace<unsigned short const &,>(
                      v62,
                      &v48,
                      ExitCode);
              std::vector<MemoryBlockVtlProtectionChunk>::_Insert_counted_range<std::move_iterator<MemoryBlockVtlProtectionChunk *>>(
                *(_QWORD *)v26 + 40LL,
                *(_QWORD *)(*(_QWORD *)v26 + 48LL),
                v25,
                0xAAAAAAAAAAAAAAABuLL * ((v24 - v25) >> 4));
              std::vector<MemoryBlockVtlProtectionChunk>::_Tidy(&Value);
              v15 = RemoteThread;
            }
            if ( v20 == *(__int64 **)(*((_QWORD *)this + 20) + 8LL) )
              v19 = 0;
            else
              v19 = *v20++;
          }
          while ( v19 );
          v17 = (char *)Size;
        }
        v54 = 0;
        v55 = 0;
        v27 = *(__int64 **)v62[0];
        v28 = v47;
        while ( !*((_BYTE *)v27 + 25) )
        {
          Value = *(_OWORD *)&SystemInformation[16 * *((unsigned __int16 *)v27 + 16) + 8];
          memset(v64, 0, sizeof(v64));
          Size = 48;
          v29 = InitializeProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)v64, 1u, 0, &Size);
          try
          {
            if ( !v29 )
              wil::details::in1diag3::Throw_GetLastError(
                retaddr,
                (void *)0x1AEB,
                (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
                v30);
            v48 = v64;
            v49 = 1;
            if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)v64, 0, 0x30003u, &Value, 0x10u, 0, 0) )
              wil::details::in1diag3::Throw_GetLastError(
                retaddr,
                (void *)0x1AF9,
                (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
                v31);
            v32 = 0;
            for ( i = v27[5]; i != v27[6]; i += 48 )
              v32 += *(_QWORD *)(i + 16);
            v34 = v32 >> 20;
            v35 = (unsigned __int64)(unsigned int)RtlNumberOfSetBitsUlongPtr(Value) >> 1;
            if ( v35 >= v34 )
              v35 = v34;
            if ( 0xAAAAAAAAAAAAAAABuLL * ((v27[6] - v27[5]) >> 4) < v35 )
              v35 = 0xAAAAAAAAAAAAAAABuLL * ((v27[6] - v27[5]) >> 4);
            if ( v35 <= 8 )
            {
              if ( !v35 )
                v35 = 1;
            }
            else
            {
              v35 = 8;
            }
            for ( j = 0; j < v35; ++j )
            {
              v37 = operator new(0x18u);
              *(_WORD *)v37 = *((_WORD *)v27 + 16);
              v37[1] = this;
              v37[2] = &v60;
              v51[0] = v37;
              RemoteThread = (__int64)CreateRemoteThreadEx(
                                        (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                                        0,
                                        0,
                                        MemoryManager::RestoreVtlProtectionThread,
                                        v37,
                                        0,
                                        (LPPROC_THREAD_ATTRIBUTE_LIST)v64,
                                        0);
              std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::emplace_back<void *>(
                &v54,
                &RemoteThread);
              if ( (unsigned __int64)(*(_QWORD *)(*((_QWORD *)&v54 + 1) - 8LL) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
                wil::details::in1diag3::Throw_GetLastError(
                  retaddr,
                  (void *)0x1B36,
                  (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
                  v38);
              v28 |= 1u;
              v51[0] = 0;
              std::unique_ptr<MemoryManager::SaveVtlProtectionThreadContext>::~unique_ptr<MemoryManager::SaveVtlProtectionThreadContext>(v51);
            }
            v49 = 0;
            DeleteProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)v64);
            v39 = (__int64 **)v27[2];
            if ( *((_BYTE *)v39 + 25) )
            {
              for ( k = (__int64 *)v27[1]; !*((_BYTE *)k + 25) && v27 == (__int64 *)k[2]; k = (__int64 *)k[1] )
                v27 = k;
              v27 = k;
            }
            else
            {
              v27 = (__int64 *)v27[2];
              for ( m = *v39; !*((_BYTE *)m + 25); m = (__int64 *)*m )
                v27 = m;
            }
          }
          catch ( ... )
          {
            v51[0] = 0;
            wil::AcquireSRWLockExclusive(v51, &v60);
            v61 = 1;
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v51);
            MemoryManager::WaitForAllThreadsToExit(&v54);
            throw;
          }
        }
        MemoryManager::WaitForAllThreadsToExit(&v54);
        v43 = (HANDLE *)*((_QWORD *)&v54 + 1);
        v42 = (HANDLE *)v54;
        if ( (_QWORD)v54 != *((_QWORD *)&v54 + 1) )
        {
          do
          {
            ExitCode[0] = 0;
            if ( !GetExitCodeThread(*v42, ExitCode) )
              wil::details::in1diag3::Throw_GetLastError(
                retaddr,
                (void *)0x1B58,
                (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
                v44);
            if ( (ExitCode[0] & 0x80000000) != 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1B59,
                (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
                (const char *)ExitCode[0],
                cbSize);
            ++v42;
          }
          while ( v42 != v43 );
          v43 = (HANDLE *)*((_QWORD *)&v54 + 1);
          v42 = (HANDLE *)v54;
        }
        if ( v42 )
        {
          std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>(
            v42,
            v43);
          std::_Deallocate<16>(v54, (v55 - v54) & 0xFFFFFFFFFFFFFFF8uLL);
          v54 = 0;
          v55 = 0;
        }
        RrwLockRelease(v17);
        std::_Tree<std::_Tmap_traits<unsigned short,std::vector<MemoryBlockVtlProtectionChunk>,std::less<unsigned short>,std::allocator<std::pair<unsigned short const,std::vector<MemoryBlockVtlProtectionChunk>>>,0>>::~_Tree<std::_Tmap_traits<unsigned short,std::vector<MemoryBlockVtlProtectionChunk>,std::less<unsigned short>,std::allocator<std::pair<unsigned short const,std::vector<MemoryBlockVtlProtectionChunk>>>,0>>(v62);
        Vml::VmReferencePtr<IMemoryContentsFileSizeChangeCallback,Vml::VmUserReferenceTraits>::~VmReferencePtr<IMemoryContentsFileSizeChangeCallback,Vml::VmUserReferenceTraits>(&v57);
      }
    }
  }
}

```

## disassembly

```asm
0x1400b9090  mov     [rsp+arg_10], rbx
0x1400b9095  mov     [rsp+arg_18], rsi
0x1400b909a  push    rdi
0x1400b909b  push    r12
0x1400b909d  push    r13
0x1400b909f  push    r14
0x1400b90a1  push    r15
0x1400b90a3  sub     rsp, 550h
0x1400b90aa  mov     rax, cs:__security_cookie
0x1400b90b1  xor     rax, rsp
0x1400b90b4  mov     [rsp+578h+var_38], rax
0x1400b90bc  mov     bl, r8b
0x1400b90bf  mov     byte ptr [rsp+578h+ExitCode], bl
0x1400b90c3  mov     r13, rdx
0x1400b90c6  mov     r15, rcx
0x1400b90c9  xor     edi, edi
0x1400b90cb  mov     [rsp+578h+var_530], edi
0x1400b90cf  cmp     dword ptr [rcx+90h], 700h
0x1400b90d9  jb      loc_1400B98E6
0x1400b90df  mov     [rsp+578h+var_4F8], edi
0x1400b90e6  mov     rcx, [rcx+20h]
0x1400b90ea  mov     rax, [rcx]
0x1400b90ed  mov     rax, [rax+1D0h]
0x1400b90f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b90f9  mov     r8, rax
0x1400b90fc  mov     rcx, [rax]
0x1400b90ff  mov     rax, [rcx+58h]
0x1400b9103  lea     rdx, [rsp+578h+var_4F8]
0x1400b910b  mov     rcx, r8
0x1400b910e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b9113  mov     rcx, [rsp+578h]; this
0x1400b911b  test    eax, eax
0x1400b911d  jns     short loc_1400B9134
0x1400b911f  mov     r9d, eax; char *
0x1400b9122  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x1400b9129  mov     edx, 1A25h; void *
0x1400b912e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400b9134  mov     ecx, [rsp+578h+var_4F8]
0x1400b913b  mov     eax, 1
0x1400b9140  shl     eax, cl
0x1400b9142  test    al, 1Ch
0x1400b9144  jnz     loc_1400B98E6
0x1400b914a  xorps   xmm0, xmm0
0x1400b914d  movups  xmmword ptr [rsp+578h+var_488], xmm0
0x1400b9155  xor     r8d, r8d
0x1400b9158  mov     rdx, r13
0x1400b915b  lea     rcx, [rsp+578h+var_488]
0x1400b9163  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x1400b9168  nop
0x1400b9169  mov     r9d, dword ptr [rsp+578h+var_488+8]; char *
0x1400b9171  mov     rcx, [rsp+578h]; this
0x1400b9179  test    r9d, r9d
0x1400b917c  jns     short loc_1400B9190
0x1400b917e  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x1400b9185  mov     edx, 1A4Ah; void *
0x1400b918a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400b9190  mov     r14, [r15+0A0h]
0x1400b9197  add     r14, 18h
0x1400b919b  or      edx, 0FFFFFFFFh
0x1400b919e  mov     rcx, r14
0x1400b91a1  call    RrwLockAcquireShared
0x1400b91a6  test    eax, eax
0x1400b91a8  jnz     short loc_1400B91CA
0x1400b91aa  mov     rcx, [rsp+578h]; this
0x1400b91b2  mov     r9d, 102h; char *
0x1400b91b8  lea     r8, aOnecoreVmCommo_23; "onecore\\vm\\common\\vml\\VmReaderWrite"...
0x1400b91bf  mov     edx, 249h; void *
0x1400b91c4  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400b91ca  mov     sil, dil
0x1400b91cd  mov     r12b, dil
0x1400b91d0  mov     [rsp+578h+Size], r14
0x1400b91d8  mov     [rsp+578h+var_508], rdi
0x1400b91dd  lea     rdx, [rsp+578h+var_508]
0x1400b91e2  mov     rcx, [r15+0A0h]
0x1400b91e9  call    ?IteratorGetFirst@MemoryBlockContainer@@QEAAPEAVMemoryBlock@@AEAV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVMemoryBlock@@@std@@@std@@@std@@@Z; MemoryBlockContainer::IteratorGetFirst(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MemoryBlock *>>> &)
0x1400b91ee  mov     rdi, rax
0x1400b91f1  test    rax, rax
0x1400b91f4  jz      short loc_1400B925A
0x1400b91f6  mov     rbx, [rsp+578h+var_508]
0x1400b91fb  cmp     byte ptr [rdi], 0
0x1400b91fe  jz      short loc_1400B923D
0x1400b9200  mov     r8, r13; struct VmRepository *
0x1400b9203  mov     edx, [r15+180h]; unsigned int
0x1400b920a  mov     rcx, rdi; this
0x1400b920d  call    ?LoadVtlProtections@MemoryBlock@@IEAA_NIPEAVVmRepository@@@Z; MemoryBlock::LoadVtlProtections(uint,VmRepository *)
0x1400b9212  test    al, al
0x1400b9214  jz      short loc_1400B9223
0x1400b9216  mov     eax, 1
0x1400b921b  mov     sil, al
0x1400b921e  mov     r12b, al
0x1400b9221  jmp     short loc_1400B923D
0x1400b9223  movzx   esi, sil
0x1400b9227  mov     rax, [rdi+0E0h]
0x1400b922e  cmp     [rdi+0D8h], rax
0x1400b9235  mov     eax, 1
0x1400b923a  cmovnz  esi, eax
0x1400b923d  mov     rax, [r15+0A0h]
0x1400b9244  cmp     rbx, [rax+8]
0x1400b9248  jz      short loc_1400B9256
0x1400b924a  mov     rdi, [rbx]
0x1400b924d  add     rbx, 8
0x1400b9251  test    rdi, rdi
0x1400b9254  jnz     short loc_1400B91FB
0x1400b9256  mov     bl, byte ptr [rsp+578h+ExitCode]
0x1400b925a  mov     rcx, r14
0x1400b925d  call    RrwLockRelease
0x1400b9262  nop
0x1400b9263  lea     rcx, [rsp+578h+var_488]; this
0x1400b926b  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400b9270  xor     r14d, r14d
0x1400b9273  test    r12b, r12b
0x1400b9276  jz      short loc_1400B927F
0x1400b9278  inc     dword ptr [r15+180h]
0x1400b927f  test    bl, bl
0x1400b9281  jnz     loc_1400B98E6
0x1400b9287  test    sil, sil
0x1400b928a  jz      loc_1400B98E6
0x1400b9290  mov     rcx, r15; this
0x1400b9293  call    ?AreAnySecureVtlsEnabled@MemoryManager@@AEBA_NXZ; MemoryManager::AreAnySecureVtlsEnabled(void)
0x1400b9298  test    al, al
0x1400b929a  jnz     short loc_1400B92BC
0x1400b929c  mov     rcx, [rsp+578h]; this
0x1400b92a4  mov     r9d, 570h; char *
0x1400b92aa  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x1400b92b1  mov     edx, 1A83h; void *
0x1400b92b6  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400b92bc  mov     ebx, 408h
0x1400b92c1  mov     r8d, ebx; Size
0x1400b92c4  xor     edx, edx; Val
0x1400b92c6  lea     rcx, [rsp+578h+SystemInformation]; void *
0x1400b92ce  call    memset_0
0x1400b92d3  mov     [rsp+578h+ReturnLength], r14d
0x1400b92db  lea     r9, [rsp+578h+ReturnLength]; ReturnLength
0x1400b92e3  mov     r8d, ebx; SystemInformationLength
0x1400b92e6  lea     rdx, [rsp+578h+SystemInformation]; SystemInformation
0x1400b92ee  mov     ecx, 37h ; '7'; SystemInformationClass
0x1400b92f3  call    cs:__imp_NtQuerySystemInformation
0x1400b92fa  nop     dword ptr [rax+rax+00h]
0x1400b92ff  mov     rcx, [rsp+578h]; this
0x1400b9307  test    eax, eax
0x1400b9309  jns     short loc_1400B9320
0x1400b930b  mov     r9d, eax; char *
0x1400b930e  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x1400b9315  mov     edx, 1A9Ah; void *
0x1400b931a  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1400b9320  call    ?OpenShared@?$VmSingletonObject@VNumaPhysicalTopologyInfo@@UINumaPhysicalTopologyInfo@@@Vml@@SAPEAUINumaPhysicalTopologyInfo@@XZ; Vml::VmSingletonObject<NumaPhysicalTopologyInfo,INumaPhysicalTopologyInfo>::OpenShared(void)
0x1400b9325  mov     [rsp+578h+var_4C8], rax
0x1400b932d  mov     rcx, [r15+28h]
0x1400b9331  mov     rdx, [rcx]
0x1400b9334  mov     rax, [rdx+8]
0x1400b9338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b933d  mov     rdx, rax
0x1400b9340  mov     rcx, [rax]
0x1400b9343  mov     rax, [rcx+58h]
0x1400b9347  mov     rcx, rdx
0x1400b934a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b934f  mov     rdi, rax
0x1400b9352  mov     [rsp+578h+var_538], rax
0x1400b9357  xor     eax, eax
0x1400b9359  mov     [rsp+578h+var_4A8], rax
0x1400b9361  mov     [rsp+578h+var_4A0], r14b
0x1400b9369  mov     [rsp+578h+var_498], r14
0x1400b9371  mov     [rsp+578h+var_490], r14
0x1400b9379  lea     ecx, [rax+40h]
0x1400b937c  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1400b9381  mov     [rax], rax
0x1400b9384  mov     [rax+8], rax
0x1400b9388  mov     [rax+10h], rax
0x1400b938c  mov     word ptr [rax+18h], 101h
0x1400b9392  mov     [rsp+578h+var_498], rax
0x1400b939a  mov     rsi, [r15+0A0h]
0x1400b93a1  add     rsi, 18h
0x1400b93a5  mov     [rsp+578h+Size], rsi
0x1400b93ad  or      edx, 0FFFFFFFFh
0x1400b93b0  mov     rcx, rsi
0x1400b93b3  call    RrwLockAcquireShared
0x1400b93b8  test    eax, eax
0x1400b93ba  jnz     short loc_1400B93DC
0x1400b93bc  mov     rcx, [rsp+578h]; this
0x1400b93c4  mov     r9d, 102h; char *
0x1400b93ca  lea     r8, aOnecoreVmCommo_23; "onecore\\vm\\common\\vml\\VmReaderWrite"...
0x1400b93d1  mov     edx, 249h; void *
0x1400b93d6  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400b93dc  mov     [rsp+578h+var_488], rsi
0x1400b93e4  mov     [rsp+578h+var_508], r14
0x1400b93e9  lea     rdx, [rsp+578h+var_508]
0x1400b93ee  mov     rcx, [r15+0A0h]
0x1400b93f5  call    ?IteratorGetFirst@MemoryBlockContainer@@QEAAPEAVMemoryBlock@@AEAV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVMemoryBlock@@@std@@@std@@@std@@@Z; MemoryBlockContainer::IteratorGetFirst(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MemoryBlock *>>> &)
0x1400b93fa  mov     r13, rax
0x1400b93fd  test    rax, rax
0x1400b9400  jz      loc_1400B953D
0x1400b9406  mov     r12, 0AAAAAAAAAAAAAAABh
0x1400b9410  mov     rbx, [rsp+578h+var_508]
0x1400b9415  mov     rsi, [rsp+578h+var_4C8]
0x1400b941d  cmp     [r13+0], r14b
0x1400b9421  jz      loc_1400B9513
0x1400b9427  mov     [rsp+578h+var_508], r14
0x1400b942c  mov     [rsp+578h+var_500], r14
0x1400b9431  mov     rax, [rsi]
0x1400b9434  movzx   edx, byte ptr [r13+0B8h]
0x1400b943c  mov     r9b, 1
0x1400b943f  lea     r8, [rsp+578h+var_508]
0x1400b9444  mov     dl, [rdx+rdi+118h]
0x1400b944b  mov     rcx, rsi
0x1400b944e  mov     rax, [rax+10h]
0x1400b9452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b9457  mov     rcx, [rsi]
0x1400b945a  mov     dl, al
0x1400b945c  mov     rax, [rcx+30h]
0x1400b9460  mov     rcx, rsi
0x1400b9463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b9468  movzx   eax, al
0x1400b946b  mov     word ptr [rsp+578h+ExitCode], ax
0x1400b9470  xorps   xmm0, xmm0
0x1400b9473  movups  [rsp+578h+Value], xmm0
0x1400b947b  mov     rax, [r13+0E8h]
0x1400b9482  mov     [r13+0E8h], r14
0x1400b9489  mov     r14, [r13+0E0h]
0x1400b9490  mov     qword ptr [r13+0E0h], 0
0x1400b949b  mov     rdi, [r13+0D8h]
0x1400b94a2  mov     qword ptr [r13+0D8h], 0
0x1400b94ad  mov     qword ptr [rsp+578h+Value], rdi
0x1400b94b5  mov     qword ptr [rsp+578h+Value+8], r14
0x1400b94bd  mov     [rsp+578h+var_4B0], rax
0x1400b94c5  lea     r8, [rsp+578h+ExitCode]
0x1400b94ca  lea     rdx, [rsp+578h+var_528]
0x1400b94cf  lea     rcx, [rsp+578h+var_498]
0x1400b94d7  call    ??$_Try_emplace@AEBG$$V@?$map@GV?$vector@UMemoryBlockVtlProtectionChunk@@V?$allocator@UMemoryBlockVtlProtectionChunk@@@std@@@std@@U?$less@G@2@V?$allocator@U?$pair@$$CBGV?$vector@UMemoryBlockVtlProtectionChunk@@V?$allocator@UMemoryBlockVtlProtectionChunk@@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBGV?$vector@UMemoryBlockVtlProtectionChunk@@V?$allocator@UMemoryBlockVtlProtectionChunk@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBG@Z; std::map<ushort,std::vector<MemoryBlockVtlProtectionChunk>>::_Try_emplace<ushort const &,>(ushort const &)
0x1400b94dc  mov     rcx, [rax]
0x1400b94df  add     rcx, 28h ; '('
0x1400b94e3  sub     r14, rdi
0x1400b94e6  sar     r14, 4
0x1400b94ea  imul    r14, r12
0x1400b94ee  mov     r9, r14
0x1400b94f1  mov     r8, rdi
0x1400b94f4  mov     rdx, [rcx+8]
0x1400b94f8  call    ??$_Insert_counted_range@V?$move_iterator@PEAUMemoryBlockVtlProtectionChunk@@@std@@@?$vector@UMemoryBlockVtlProtectionChunk@@V?$allocator@UMemoryBlockVtlProtectionChunk@@@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UMemoryBlockVtlProtectionChunk@@@std@@@std@@@1@V?$move_iterator@PEAUMemoryBlockVtlProtectionChunk@@@1@_K@Z; std::vector<MemoryBlockVtlProtectionChunk>::_Insert_counted_range<std::move_iterator<MemoryBlockVtlProtectionChunk *>>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<MemoryBlockVtlProtectionChunk>>>,std::move_iterator<MemoryBlockVtlProtectionChunk *>,unsigned __int64)
0x1400b94fd  nop
0x1400b94fe  lea     rcx, [rsp+578h+Value]
0x1400b9506  call    ?_Tidy@?$vector@UMemoryBlockVtlProtectionChunk@@V?$allocator@UMemoryBlockVtlProtectionChunk@@@std@@@std@@AEAAXXZ; std::vector<MemoryBlockVtlProtectionChunk>::_Tidy(void)
0x1400b950b  mov     rdi, [rsp+578h+var_538]
0x1400b9510  xor     r14d, r14d
0x1400b9513  mov     rax, [r15+0A0h]
0x1400b951a  cmp     rbx, [rax+8]
0x1400b951e  jnz     short loc_1400B9525
0x1400b9520  mov     r13, r14
0x1400b9523  jmp     short loc_1400B952C
0x1400b9525  mov     r13, [rbx]
0x1400b9528  add     rbx, 8
0x1400b952c  test    r13, r13
0x1400b952f  jnz     loc_1400B941D
0x1400b9535  mov     rsi, [rsp+578h+Size]
0x1400b953d  xorps   xmm1, xmm1
0x1400b9540  movdqu  [rsp+578h+var_4E8], xmm1
0x1400b9549  mov     [rsp+578h+var_4D8], r14
0x1400b9551  mov     rbx, [rsp+578h+var_498]
0x1400b9559  mov     rbx, [rbx]
0x1400b955c  mov     r13d, [rsp+578h+var_530]
0x1400b9561  cmp     [rbx+19h], r14b
0x1400b9565  jnz     loc_1400B9808
0x1400b956b  movzx   eax, word ptr [rbx+20h]
0x1400b956f  add     rax, rax
0x1400b9572  movups  xmm0, [rsp+rax*8+578h+var_440]
0x1400b957a  movdqu  [rsp+578h+Value], xmm0
0x1400b9583  xorps   xmm1, xmm1
0x1400b9586  movups  [rsp+578h+var_478], xmm1
0x1400b958e  movups  [rsp+578h+var_468], xmm1
0x1400b9596  movups  [rsp+578h+var_458], xmm1
0x1400b959e  mov     [rsp+578h+Size], 30h ; '0'
0x1400b95aa  lea     r9, [rsp+578h+Size]; lpSize
0x1400b95b2  xor     r8d, r8d; dwFlags
0x1400b95b5  lea     edx, [r8+1]; dwAttributeCount
0x1400b95b9  lea     rcx, [rsp+578h+var_478]; lpAttributeList
0x1400b95c1  call    cs:__imp_InitializeProcThreadAttributeList
0x1400b95c8  nop     dword ptr [rax+rax+00h]
0x1400b95cd  mov     rcx, [rsp+578h]; this
0x1400b95d5  test    eax, eax
0x1400b95d7  jnz     short loc_1400B95EA
0x1400b95d9  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x1400b95e0  mov     edx, 1AEBh; void *
0x1400b95e5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400b95ea  lea     rdi, [rsp+578h+var_478]
0x1400b95f2  mov     [rsp+578h+var_528], rdi
0x1400b95f7  mov     [rsp+578h+var_520], 1
0x1400b95fc  mov     [rsp+578h+lpReturnSize], r14; lpReturnSize
0x1400b9601  mov     [rsp+578h+lpPreviousValue], r14; lpPreviousValue
0x1400b9606  mov     [rsp+578h+cbSize], 10h; cbSize
0x1400b960f  lea     r9, [rsp+578h+Value]; lpValue
0x1400b9617  xor     edx, edx; dwFlags
0x1400b9619  mov     r8d, 30003h; Attribute
0x1400b961f  lea     rcx, [rsp+578h+var_478]; lpAttributeList
0x1400b9627  call    cs:__imp_UpdateProcThreadAttribute
0x1400b962e  nop     dword ptr [rax+rax+00h]
0x1400b9633  mov     rcx, [rsp+578h]; this
0x1400b963b  test    eax, eax
0x1400b963d  jnz     short loc_1400B9650
0x1400b963f  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x1400b9646  mov     edx, 1AF9h; void *
0x1400b964b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400b9650  mov     r12, r14
  ... truncated ...
```
