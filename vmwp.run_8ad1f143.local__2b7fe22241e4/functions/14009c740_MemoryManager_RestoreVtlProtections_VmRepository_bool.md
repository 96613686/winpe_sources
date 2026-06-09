# MemoryManager::RestoreVtlProtections(VmRepository *,bool)

- ea: `0x14009c740`
- end: `0x14009cfe8`
- name: `?RestoreVtlProtections@MemoryManager@@UEAAXPEAVVmRepository@@_N@Z`
- size: `2216`
- prototype: `void(MemoryManager *__hidden this, struct VmRepository *, bool)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14017e600`

## callees

- `0x140023dc0`
- `0x140023f94`
- `0x14003366c`
- `0x140040ff8`
- `0x1400417c8`
- `0x1400544a8`
- `0x1400545d0`
- `0x14005b648`
- `0x14005f65c`
- `0x14006af58`
- `0x14009c740`
- `0x14009cff0`
- `0x14009d7cc`
- `0x14009d7ec`
- `0x1400bfe8c`
- `0x140132960`
- `0x140132d0c`
- `0x14013361c`
- `0x140172bf0`
- `0x1401feb18`
- `0x1401ffdac`
- `0x140201a4c`
- `0x1402022e8`
- `0x140202984`
- `0x140202f24`
- `0x140204598`
- `0x14020e4a0`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x14009ccd7`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x14009ccd7`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x14009cee7`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x14009cee7`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x14009cc71`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x14009cc71`
- `api-ms-win-core-processthreads-l1-1-0!CreateRemoteThreadEx` at `0x14009cddd`
- `api-ms-win-core-processthreads-l1-1-0!CreateRemoteThreadEx` at `0x14009cddd`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x14009ce5d`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x14009ce5d`
- `ntdll!NtQuerySystemInformation` at `0x14009c9a3`
- `ntdll!NtQuerySystemInformation` at `0x14009c9a3`
- `ntdll!RtlNumberOfSetBitsUlongPtr` at `0x14009cd23`
- `ntdll!RtlNumberOfSetBitsUlongPtr` at `0x14009cd23`

## string_xrefs

- `0x14009c868`: `onecore\vm\common\vml\VmReaderWriterLock.h`
- `0x14009ca7a`: `onecore\vm\common\vml\VmReaderWriterLock.h`

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
    v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 448LL))(*((_QWORD *)this + 4));
    v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v6 + 88LL))(v6, &v52);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A38,
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
          (void *)0x1A5D,
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
            (void *)0x1A96,
            (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
            (const char *)0x570,
            cbSize);
        memset_0(SystemInformation, 0, 0x408u);
        ReturnLength = 0;
        v13 = NtQuerySystemInformation(SystemNumaProcessorMap, SystemInformation, 0x408u, &ReturnLength);
        if ( v13 < 0 )
          wil::details::in1diag3::_Throw_NtStatus(
            retaddr,
            (void *)0x1AAD,
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
                (void *)0x1AFE,
                (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
                v30);
            v48 = v64;
            v49 = 1;
            if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)v64, 0, 0x30003u, &Value, 0x10u, 0, 0) )
              wil::details::in1diag3::Throw_GetLastError(
                retaddr,
                (void *)0x1B0C,
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
                  (void *)0x1B49,
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
                (void *)0x1B6B,
                (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
                v44);
            if ( (ExitCode[0] & 0x80000000) != 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1B6C,
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
0x14009c740  mov     [rsp+arg_10], rbx
0x14009c745  mov     [rsp+arg_18], rsi
0x14009c74a  push    rdi
0x14009c74b  push    r12
0x14009c74d  push    r13
0x14009c74f  push    r14
0x14009c751  push    r15
0x14009c753  sub     rsp, 550h
0x14009c75a  mov     rax, cs:__security_cookie
0x14009c761  xor     rax, rsp
0x14009c764  mov     [rsp+578h+var_38], rax
0x14009c76c  mov     bl, r8b
0x14009c76f  mov     byte ptr [rsp+578h+ExitCode], bl
0x14009c773  mov     r13, rdx
0x14009c776  mov     r15, rcx
0x14009c779  xor     edi, edi
0x14009c77b  mov     [rsp+578h+var_530], edi
0x14009c77f  cmp     dword ptr [rcx+90h], 700h
0x14009c789  jb      loc_14009CF96
0x14009c78f  mov     [rsp+578h+var_4F8], edi
0x14009c796  mov     rcx, [rcx+20h]
0x14009c79a  mov     rax, [rcx]
0x14009c79d  mov     rax, [rax+1C0h]
0x14009c7a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009c7a9  mov     r8, rax
0x14009c7ac  mov     rcx, [rax]
0x14009c7af  mov     rax, [rcx+58h]
0x14009c7b3  lea     rdx, [rsp+578h+var_4F8]
0x14009c7bb  mov     rcx, r8
0x14009c7be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009c7c3  mov     rcx, [rsp+578h]; this
0x14009c7cb  test    eax, eax
0x14009c7cd  jns     short loc_14009C7E4
0x14009c7cf  mov     r9d, eax; char *
0x14009c7d2  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x14009c7d9  mov     edx, 1A38h; void *
0x14009c7de  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009c7e4  mov     ecx, [rsp+578h+var_4F8]
0x14009c7eb  mov     eax, 1
0x14009c7f0  shl     eax, cl
0x14009c7f2  test    al, 1Ch
0x14009c7f4  jnz     loc_14009CF96
0x14009c7fa  xorps   xmm0, xmm0
0x14009c7fd  movups  xmmword ptr [rsp+578h+var_488], xmm0
0x14009c805  xor     r8d, r8d
0x14009c808  mov     rdx, r13
0x14009c80b  lea     rcx, [rsp+578h+var_488]
0x14009c813  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x14009c818  nop
0x14009c819  mov     r9d, dword ptr [rsp+578h+var_488+8]; char *
0x14009c821  mov     rcx, [rsp+578h]; this
0x14009c829  test    r9d, r9d
0x14009c82c  jns     short loc_14009C840
0x14009c82e  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x14009c835  mov     edx, 1A5Dh; void *
0x14009c83a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009c840  mov     r14, [r15+0A0h]
0x14009c847  add     r14, 18h
0x14009c84b  or      edx, 0FFFFFFFFh
0x14009c84e  mov     rcx, r14
0x14009c851  call    RrwLockAcquireShared
0x14009c856  test    eax, eax
0x14009c858  jnz     short loc_14009C87A
0x14009c85a  mov     rcx, [rsp+578h]; this
0x14009c862  mov     r9d, 102h; char *
0x14009c868  lea     r8, aOnecoreVmCommo_24; "onecore\\vm\\common\\vml\\VmReaderWrite"...
0x14009c86f  mov     edx, 249h; void *
0x14009c874  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14009c87a  mov     sil, dil
0x14009c87d  mov     r12b, dil
0x14009c880  mov     [rsp+578h+Size], r14
0x14009c888  mov     [rsp+578h+var_508], rdi
0x14009c88d  lea     rdx, [rsp+578h+var_508]
0x14009c892  mov     rcx, [r15+0A0h]
0x14009c899  call    ?IteratorGetFirst@MemoryBlockContainer@@QEAAPEAVMemoryBlock@@AEAV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVMemoryBlock@@@std@@@std@@@std@@@Z; MemoryBlockContainer::IteratorGetFirst(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MemoryBlock *>>> &)
0x14009c89e  mov     rdi, rax
0x14009c8a1  test    rax, rax
0x14009c8a4  jz      short loc_14009C90A
0x14009c8a6  mov     rbx, [rsp+578h+var_508]
0x14009c8ab  cmp     byte ptr [rdi], 0
0x14009c8ae  jz      short loc_14009C8ED
0x14009c8b0  mov     r8, r13; struct VmRepository *
0x14009c8b3  mov     edx, [r15+180h]; unsigned int
0x14009c8ba  mov     rcx, rdi; this
0x14009c8bd  call    ?LoadVtlProtections@MemoryBlock@@IEAA_NIPEAVVmRepository@@@Z; MemoryBlock::LoadVtlProtections(uint,VmRepository *)
0x14009c8c2  test    al, al
0x14009c8c4  jz      short loc_14009C8D3
0x14009c8c6  mov     eax, 1
0x14009c8cb  mov     sil, al
0x14009c8ce  mov     r12b, al
0x14009c8d1  jmp     short loc_14009C8ED
0x14009c8d3  movzx   esi, sil
0x14009c8d7  mov     rax, [rdi+0E0h]
0x14009c8de  cmp     [rdi+0D8h], rax
0x14009c8e5  mov     eax, 1
0x14009c8ea  cmovnz  esi, eax
0x14009c8ed  mov     rax, [r15+0A0h]
0x14009c8f4  cmp     rbx, [rax+8]
0x14009c8f8  jz      short loc_14009C906
0x14009c8fa  mov     rdi, [rbx]
0x14009c8fd  add     rbx, 8
0x14009c901  test    rdi, rdi
0x14009c904  jnz     short loc_14009C8AB
0x14009c906  mov     bl, byte ptr [rsp+578h+ExitCode]
0x14009c90a  mov     rcx, r14
0x14009c90d  call    RrwLockRelease
0x14009c912  nop
0x14009c913  lea     rcx, [rsp+578h+var_488]; this
0x14009c91b  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x14009c920  xor     r14d, r14d
0x14009c923  test    r12b, r12b
0x14009c926  jz      short loc_14009C92F
0x14009c928  inc     dword ptr [r15+180h]
0x14009c92f  test    bl, bl
0x14009c931  jnz     loc_14009CF96
0x14009c937  test    sil, sil
0x14009c93a  jz      loc_14009CF96
0x14009c940  mov     rcx, r15; this
0x14009c943  call    ?AreAnySecureVtlsEnabled@MemoryManager@@AEBA_NXZ; MemoryManager::AreAnySecureVtlsEnabled(void)
0x14009c948  test    al, al
0x14009c94a  jnz     short loc_14009C96C
0x14009c94c  mov     rcx, [rsp+578h]; this
0x14009c954  mov     r9d, 570h; char *
0x14009c95a  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x14009c961  mov     edx, 1A96h; void *
0x14009c966  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14009c96c  mov     ebx, 408h
0x14009c971  mov     r8d, ebx; Size
0x14009c974  xor     edx, edx; Val
0x14009c976  lea     rcx, [rsp+578h+SystemInformation]; void *
0x14009c97e  call    memset_0
0x14009c983  mov     [rsp+578h+ReturnLength], r14d
0x14009c98b  lea     r9, [rsp+578h+ReturnLength]; ReturnLength
0x14009c993  mov     r8d, ebx; SystemInformationLength
0x14009c996  lea     rdx, [rsp+578h+SystemInformation]; SystemInformation
0x14009c99e  mov     ecx, 37h ; '7'; SystemInformationClass
0x14009c9a3  call    cs:__imp_NtQuerySystemInformation
0x14009c9aa  nop     dword ptr [rax+rax+00h]
0x14009c9af  mov     rcx, [rsp+578h]; this
0x14009c9b7  test    eax, eax
0x14009c9b9  jns     short loc_14009C9D0
0x14009c9bb  mov     r9d, eax; char *
0x14009c9be  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x14009c9c5  mov     edx, 1AADh; void *
0x14009c9ca  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x14009c9d0  call    ?OpenShared@?$VmSingletonObject@VNumaPhysicalTopologyInfo@@UINumaPhysicalTopologyInfo@@@Vml@@SAPEAUINumaPhysicalTopologyInfo@@XZ; Vml::VmSingletonObject<NumaPhysicalTopologyInfo,INumaPhysicalTopologyInfo>::OpenShared(void)
0x14009c9d5  mov     [rsp+578h+var_4C8], rax
0x14009c9dd  mov     rcx, [r15+28h]
0x14009c9e1  mov     rdx, [rcx]
0x14009c9e4  mov     rax, [rdx+8]
0x14009c9e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009c9ed  mov     rdx, rax
0x14009c9f0  mov     rcx, [rax]
0x14009c9f3  mov     rax, [rcx+58h]
0x14009c9f7  mov     rcx, rdx
0x14009c9fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009c9ff  mov     rdi, rax
0x14009ca02  mov     [rsp+578h+var_538], rax
0x14009ca07  xor     eax, eax
0x14009ca09  mov     [rsp+578h+var_4A8], rax
0x14009ca11  mov     [rsp+578h+var_4A0], r14b
0x14009ca19  mov     [rsp+578h+var_498], r14
0x14009ca21  mov     [rsp+578h+var_490], r14
0x14009ca29  lea     ecx, [rax+40h]
0x14009ca2c  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x14009ca31  mov     [rax], rax
0x14009ca34  mov     [rax+8], rax
0x14009ca38  mov     [rax+10h], rax
0x14009ca3c  mov     word ptr [rax+18h], 101h
0x14009ca42  mov     [rsp+578h+var_498], rax
0x14009ca4a  mov     rsi, [r15+0A0h]
0x14009ca51  add     rsi, 18h
0x14009ca55  mov     [rsp+578h+Size], rsi
0x14009ca5d  or      edx, 0FFFFFFFFh
0x14009ca60  mov     rcx, rsi
0x14009ca63  call    RrwLockAcquireShared
0x14009ca68  test    eax, eax
0x14009ca6a  jnz     short loc_14009CA8C
0x14009ca6c  mov     rcx, [rsp+578h]; this
0x14009ca74  mov     r9d, 102h; char *
0x14009ca7a  lea     r8, aOnecoreVmCommo_24; "onecore\\vm\\common\\vml\\VmReaderWrite"...
0x14009ca81  mov     edx, 249h; void *
0x14009ca86  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14009ca8c  mov     [rsp+578h+var_488], rsi
0x14009ca94  mov     [rsp+578h+var_508], r14
0x14009ca99  lea     rdx, [rsp+578h+var_508]
0x14009ca9e  mov     rcx, [r15+0A0h]
0x14009caa5  call    ?IteratorGetFirst@MemoryBlockContainer@@QEAAPEAVMemoryBlock@@AEAV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVMemoryBlock@@@std@@@std@@@std@@@Z; MemoryBlockContainer::IteratorGetFirst(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MemoryBlock *>>> &)
0x14009caaa  mov     r13, rax
0x14009caad  test    rax, rax
0x14009cab0  jz      loc_14009CBED
0x14009cab6  mov     r12, 0AAAAAAAAAAAAAAABh
0x14009cac0  mov     rbx, [rsp+578h+var_508]
0x14009cac5  mov     rsi, [rsp+578h+var_4C8]
0x14009cacd  cmp     [r13+0], r14b
0x14009cad1  jz      loc_14009CBC3
0x14009cad7  mov     [rsp+578h+var_508], r14
0x14009cadc  mov     [rsp+578h+var_500], r14
0x14009cae1  mov     rax, [rsi]
0x14009cae4  movzx   edx, byte ptr [r13+0B8h]
0x14009caec  mov     r9b, 1
0x14009caef  lea     r8, [rsp+578h+var_508]
0x14009caf4  mov     dl, [rdx+rdi+118h]
0x14009cafb  mov     rcx, rsi
0x14009cafe  mov     rax, [rax+10h]
0x14009cb02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009cb07  mov     rcx, [rsi]
0x14009cb0a  mov     dl, al
0x14009cb0c  mov     rax, [rcx+30h]
0x14009cb10  mov     rcx, rsi
0x14009cb13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009cb18  movzx   eax, al
0x14009cb1b  mov     word ptr [rsp+578h+ExitCode], ax
0x14009cb20  xorps   xmm0, xmm0
0x14009cb23  movups  [rsp+578h+Value], xmm0
0x14009cb2b  mov     rax, [r13+0E8h]
0x14009cb32  mov     [r13+0E8h], r14
0x14009cb39  mov     r14, [r13+0E0h]
0x14009cb40  mov     qword ptr [r13+0E0h], 0
0x14009cb4b  mov     rdi, [r13+0D8h]
0x14009cb52  mov     qword ptr [r13+0D8h], 0
0x14009cb5d  mov     qword ptr [rsp+578h+Value], rdi
0x14009cb65  mov     qword ptr [rsp+578h+Value+8], r14
0x14009cb6d  mov     [rsp+578h+var_4B0], rax
0x14009cb75  lea     r8, [rsp+578h+ExitCode]
0x14009cb7a  lea     rdx, [rsp+578h+var_528]
0x14009cb7f  lea     rcx, [rsp+578h+var_498]
0x14009cb87  call    ??$_Try_emplace@AEBG$$V@?$map@GV?$vector@UMemoryBlockVtlProtectionChunk@@V?$allocator@UMemoryBlockVtlProtectionChunk@@@std@@@std@@U?$less@G@2@V?$allocator@U?$pair@$$CBGV?$vector@UMemoryBlockVtlProtectionChunk@@V?$allocator@UMemoryBlockVtlProtectionChunk@@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBGV?$vector@UMemoryBlockVtlProtectionChunk@@V?$allocator@UMemoryBlockVtlProtectionChunk@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBG@Z; std::map<ushort,std::vector<MemoryBlockVtlProtectionChunk>>::_Try_emplace<ushort const &,>(ushort const &)
0x14009cb8c  mov     rcx, [rax]
0x14009cb8f  add     rcx, 28h ; '('
0x14009cb93  sub     r14, rdi
0x14009cb96  sar     r14, 4
0x14009cb9a  imul    r14, r12
0x14009cb9e  mov     r9, r14
0x14009cba1  mov     r8, rdi
0x14009cba4  mov     rdx, [rcx+8]
0x14009cba8  call    ??$_Insert_counted_range@V?$move_iterator@PEAUMemoryBlockVtlProtectionChunk@@@std@@@?$vector@UMemoryBlockVtlProtectionChunk@@V?$allocator@UMemoryBlockVtlProtectionChunk@@@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UMemoryBlockVtlProtectionChunk@@@std@@@std@@@1@V?$move_iterator@PEAUMemoryBlockVtlProtectionChunk@@@1@_K@Z; std::vector<MemoryBlockVtlProtectionChunk>::_Insert_counted_range<std::move_iterator<MemoryBlockVtlProtectionChunk *>>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<MemoryBlockVtlProtectionChunk>>>,std::move_iterator<MemoryBlockVtlProtectionChunk *>,unsigned __int64)
0x14009cbad  nop
0x14009cbae  lea     rcx, [rsp+578h+Value]
0x14009cbb6  call    ?_Tidy@?$vector@UMemoryBlockVtlProtectionChunk@@V?$allocator@UMemoryBlockVtlProtectionChunk@@@std@@@std@@AEAAXXZ; std::vector<MemoryBlockVtlProtectionChunk>::_Tidy(void)
0x14009cbbb  mov     rdi, [rsp+578h+var_538]
0x14009cbc0  xor     r14d, r14d
0x14009cbc3  mov     rax, [r15+0A0h]
0x14009cbca  cmp     rbx, [rax+8]
0x14009cbce  jnz     short loc_14009CBD5
0x14009cbd0  mov     r13, r14
0x14009cbd3  jmp     short loc_14009CBDC
0x14009cbd5  mov     r13, [rbx]
0x14009cbd8  add     rbx, 8
0x14009cbdc  test    r13, r13
0x14009cbdf  jnz     loc_14009CACD
0x14009cbe5  mov     rsi, [rsp+578h+Size]
0x14009cbed  xorps   xmm1, xmm1
0x14009cbf0  movdqu  [rsp+578h+var_4E8], xmm1
0x14009cbf9  mov     [rsp+578h+var_4D8], r14
0x14009cc01  mov     rbx, [rsp+578h+var_498]
0x14009cc09  mov     rbx, [rbx]
0x14009cc0c  mov     r13d, [rsp+578h+var_530]
0x14009cc11  cmp     [rbx+19h], r14b
0x14009cc15  jnz     loc_14009CEB8
0x14009cc1b  movzx   eax, word ptr [rbx+20h]
0x14009cc1f  add     rax, rax
0x14009cc22  movups  xmm0, [rsp+rax*8+578h+var_440]
0x14009cc2a  movdqu  [rsp+578h+Value], xmm0
0x14009cc33  xorps   xmm1, xmm1
0x14009cc36  movups  [rsp+578h+var_478], xmm1
0x14009cc3e  movups  [rsp+578h+var_468], xmm1
0x14009cc46  movups  [rsp+578h+var_458], xmm1
0x14009cc4e  mov     [rsp+578h+Size], 30h ; '0'
0x14009cc5a  lea     r9, [rsp+578h+Size]; lpSize
0x14009cc62  xor     r8d, r8d; dwFlags
0x14009cc65  lea     edx, [r8+1]; dwAttributeCount
0x14009cc69  lea     rcx, [rsp+578h+var_478]; lpAttributeList
0x14009cc71  call    cs:__imp_InitializeProcThreadAttributeList
0x14009cc78  nop     dword ptr [rax+rax+00h]
0x14009cc7d  mov     rcx, [rsp+578h]; this
0x14009cc85  test    eax, eax
0x14009cc87  jnz     short loc_14009CC9A
0x14009cc89  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x14009cc90  mov     edx, 1AFEh; void *
0x14009cc95  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14009cc9a  lea     rdi, [rsp+578h+var_478]
0x14009cca2  mov     [rsp+578h+var_528], rdi
0x14009cca7  mov     [rsp+578h+var_520], 1
0x14009ccac  mov     [rsp+578h+lpReturnSize], r14; lpReturnSize
0x14009ccb1  mov     [rsp+578h+lpPreviousValue], r14; lpPreviousValue
0x14009ccb6  mov     [rsp+578h+cbSize], 10h; cbSize
0x14009ccbf  lea     r9, [rsp+578h+Value]; lpValue
0x14009ccc7  xor     edx, edx; dwFlags
0x14009ccc9  mov     r8d, 30003h; Attribute
0x14009cccf  lea     rcx, [rsp+578h+var_478]; lpAttributeList
0x14009ccd7  call    cs:__imp_UpdateProcThreadAttribute
0x14009ccde  nop     dword ptr [rax+rax+00h]
0x14009cce3  mov     rcx, [rsp+578h]; this
0x14009cceb  test    eax, eax
0x14009cced  jnz     short loc_14009CD00
0x14009ccef  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x14009ccf6  mov     edx, 1B0Ch; void *
0x14009ccfb  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14009cd00  mov     r12, r14
  ... truncated ...
```
