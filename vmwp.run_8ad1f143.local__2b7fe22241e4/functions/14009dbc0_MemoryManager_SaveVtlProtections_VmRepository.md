# MemoryManager::SaveVtlProtections(VmRepository *)

- ea: `0x14009dbc0`
- end: `0x14009e48e`
- name: `?SaveVtlProtections@MemoryManager@@UEAAXPEAVVmRepository@@@Z`
- size: `2254`
- prototype: `void __fastcall(MemoryManager *__hidden this, struct VmRepository *)`
- caller_count: `3`
- callee_count: `28`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14009ac00`
- `0x14009c024`
- `0x1400cfaa8`

## callees

- `0x140023dc0`
- `0x140023f94`
- `0x14003366c`
- `0x140040ff8`
- `0x1400417c8`
- `0x1400544a8`
- `0x1400545d0`
- `0x14005b648`
- `0x14005ece4`
- `0x14006af58`
- `0x14009cff0`
- `0x14009d7cc`
- `0x14009d7ec`
- `0x14009dbc0`
- `0x1400e5aac`
- `0x140132960`
- `0x140132d0c`
- `0x14013361c`
- `0x140172bf0`
- `0x1401feb18`
- `0x140201564`
- `0x14020192c`
- `0x1402022e8`
- `0x140202f24`
- `0x140203384`
- `0x140204598`
- `0x14020e4a0`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x14009e07d`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x14009e07d`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x14009e27c`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x14009e27c`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x14009e017`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x14009e017`
- `api-ms-win-core-processthreads-l1-1-0!CreateRemoteThreadEx` at `0x14009e167`
- `api-ms-win-core-processthreads-l1-1-0!CreateRemoteThreadEx` at `0x14009e167`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x14009e1ef`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x14009e1ef`
- `ntdll!NtQuerySystemInformation` at `0x14009dd22`
- `ntdll!NtQuerySystemInformation` at `0x14009dd22`
- `ntdll!RtlNumberOfSetBitsUlongPtr` at `0x14009e0cc`
- `ntdll!RtlNumberOfSetBitsUlongPtr` at `0x14009e0cc`
- `vid!VidVsmQueryProtectionsDirty` at `0x14009dcab`
- `vid!VidVsmQueryProtectionsDirty` at `0x14009dcab`

## string_xrefs

- `0x14009de63`: `onecore\vm\common\vml\VmReaderWriterLock.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall MemoryManager::SaveVtlProtections(MemoryManager *this, struct VmRepository *a2)
{
  int v4; // r13d
  __int64 v5; // r8
  int v6; // eax
  const char *v7; // r9
  NTSTATUS v8; // eax
  __int64 v9; // r15
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rsi
  __int64 First; // rax
  __int64 v15; // r9
  _BYTE *v16; // rdi
  _BYTE *v17; // rcx
  _BYTE **v18; // rbx
  ULONG_PTR v19; // r12
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rcx
  _QWORD *v23; // rdx
  const char *v24; // r9
  const char *v25; // r9
  unsigned __int64 v26; // r12
  __int64 i; // rcx
  unsigned __int64 v28; // r12
  unsigned __int64 v29; // r15
  unsigned __int64 j; // r12
  _QWORD *v31; // rax
  const char *v32; // r9
  __int64 **v33; // rcx
  __int64 *k; // rax
  __int64 *v35; // rbx
  __int64 *m; // rcx
  __int64 v37; // r9
  HANDLE *v38; // rbx
  HANDLE *v39; // rdi
  const char *v40; // r9
  __int64 *v41; // rbx
  __int64 v42; // rcx
  __int64 v43; // r8
  __int64 v44; // rdx
  _OWORD *v45; // rax
  __int64 **v46; // rcx
  __int64 *n; // rax
  __int64 *ii; // rcx
  int v49; // eax
  int cbSize; // [rsp+20h] [rbp-568h]
  _OWORD *v52; // [rsp+48h] [rbp-540h] BYREF
  __int64 v53; // [rsp+50h] [rbp-538h]
  __int64 v54; // [rsp+58h] [rbp-530h]
  __int64 v55; // [rsp+60h] [rbp-528h] BYREF
  char *v56[2]; // [rsp+68h] [rbp-520h] BYREF
  __int64 v57; // [rsp+78h] [rbp-510h]
  _BYTE v58[8]; // [rsp+80h] [rbp-508h] BYREF
  _QWORD *v59; // [rsp+88h] [rbp-500h] BYREF
  DWORD ExitCode[2]; // [rsp+90h] [rbp-4F8h] BYREF
  int v61; // [rsp+98h] [rbp-4F0h] BYREF
  ULONG ReturnLength; // [rsp+9Ch] [rbp-4ECh] BYREF
  __int128 v63; // [rsp+A0h] [rbp-4E8h] BYREF
  __int64 v64; // [rsp+B0h] [rbp-4D8h]
  ULONG_PTR Size[2]; // [rsp+C0h] [rbp-4C8h] BYREF
  __int64 v66; // [rsp+D0h] [rbp-4B8h] BYREF
  char v67; // [rsp+D8h] [rbp-4B0h]
  _QWORD v68[2]; // [rsp+E0h] [rbp-4A8h] BYREF
  __int64 **v69; // [rsp+F0h] [rbp-498h]
  __int64 v70; // [rsp+F8h] [rbp-490h]
  __int128 Value; // [rsp+100h] [rbp-488h] BYREF
  _OWORD v72[3]; // [rsp+110h] [rbp-478h] BYREF
  _BYTE SystemInformation[1040]; // [rsp+140h] [rbp-448h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+588h] [rbp+0h]

  v4 = 0;
  ReturnLength = 0;
  if ( *((_DWORD *)this + 36) >= 0x700u )
  {
    v61 = 0;
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 448LL))(*((_QWORD *)this + 4));
    v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v5 + 88LL))(v5, &v61);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x17F0,
        (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
        (const char *)(unsigned int)v6,
        cbSize);
    if ( ((1 << v61) & 0x1C) == 0 && (*((_DWORD *)this + 96) || MemoryManager::AreAnySecureVtlsEnabled(this)) )
    {
      v58[0] = 0;
      if ( !(unsigned int)VidVsmQueryProtectionsDirty(*((_QWORD *)this + 2), v58) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x1809,
          (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
          v7);
      if ( !*((_DWORD *)this + 96) || v58[0] )
      {
        memset_0(SystemInformation, 0, 0x408u);
        ReturnLength = 0;
        v8 = NtQuerySystemInformation(SystemNumaProcessorMap, SystemInformation, 0x408u, &ReturnLength);
        if ( v8 < 0 )
          wil::details::in1diag3::_Throw_NtStatus(
            retaddr,
            (void *)0x1827,
            (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
            (const char *)(unsigned int)v8,
            cbSize);
        v9 = Vml::VmSingletonObject<NumaPhysicalTopologyInfo,INumaPhysicalTopologyInfo>::OpenShared(retaddr);
        v55 = v9;
        v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 8LL))(*((_QWORD *)this + 5));
        Size[0] = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 88LL))(v10);
        *(_OWORD *)v56 = 0;
        VmRepositoryAutoLock::VmRepositoryAutoLock(v56, a2, 1);
        if ( SLODWORD(v56[1]) < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1830,
            (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
            (const char *)LODWORD(v56[1]),
            cbSize);
        v66 = 0;
        v67 = 0;
        v68[0] = 0;
        v68[1] = 0;
        v11 = std::_Allocate<16,std::_Default_allocate_traits>(64);
        *(_QWORD *)v11 = v11;
        *(_QWORD *)(v11 + 8) = v11;
        *(_QWORD *)(v11 + 16) = v11;
        *(_WORD *)(v11 + 24) = 257;
        v68[0] = v11;
        v69 = 0;
        v70 = 0;
        v12 = std::_Allocate<16,std::_Default_allocate_traits>(64);
        *(_QWORD *)v12 = v12;
        *(_QWORD *)(v12 + 8) = v12;
        *(_QWORD *)(v12 + 16) = v12;
        *(_WORD *)(v12 + 24) = 257;
        v69 = (__int64 **)v12;
        v13 = *((_QWORD *)this + 20) + 24LL;
        if ( !(unsigned int)RrwLockAcquireShared(v13, 0xFFFFFFFFLL) )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x249,
            (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
            (const char *)0x102,
            cbSize);
        v57 = v13;
        *(_QWORD *)ExitCode = 0;
        First = MemoryBlockContainer::IteratorGetFirst(*((_QWORD *)this + 20), ExitCode);
        v16 = (_BYTE *)First;
        v59 = (_QWORD *)First;
        if ( First )
        {
          v17 = (_BYTE *)First;
          v18 = *(_BYTE ***)ExitCode;
          v19 = Size[0];
          do
          {
            if ( *v16 )
            {
              Size[0] = 0;
              Size[1] = 0;
              LOBYTE(v15) = 1;
              LOBYTE(v20) = (*(__int64 (__fastcall **)(__int64, _QWORD, ULONG_PTR *, __int64))(*(_QWORD *)v9 + 16LL))(
                              v9,
                              *(unsigned __int8 *)((unsigned __int8)v17[184] + v19 + 280),
                              Size,
                              v15);
              LOWORD(ExitCode[0]) = (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 48LL))(
                                      v9,
                                      v20);
              v21 = std::map<unsigned short,std::vector<MemoryManager::MemoryBlockSaveVtlProtectionContext>>::_Try_emplace<unsigned short const &,>(
                      v68,
                      &v52,
                      ExitCode);
              v22 = *(_QWORD *)v21 + 40LL;
              v23 = *(_QWORD **)(*(_QWORD *)v21 + 48LL);
              if ( v23 == *(_QWORD **)(*(_QWORD *)v21 + 56LL) )
              {
                std::vector<MemoryManager::MemoryBlockSaveVtlProtectionContext>::_Emplace_reallocate<MemoryBlock * &>(
                  v22,
                  v23,
                  &v59);
              }
              else
              {
                *v23 = v16;
                v23[1] = 0;
                *(_QWORD *)(v22 + 8) += 16LL;
              }
            }
            if ( v18 == *(_BYTE ***)(*((_QWORD *)this + 20) + 8LL) )
              break;
            v16 = *v18++;
            v59 = v16;
            v17 = v16;
          }
          while ( v16 );
        }
        v63 = 0;
        v64 = 0;
        try
        {
          v35 = *(__int64 **)v68[0];
          while ( !*((_BYTE *)v35 + 25) )
          {
            Value = *(_OWORD *)&SystemInformation[16 * *((unsigned __int16 *)v35 + 16) + 8];
            memset(v72, 0, sizeof(v72));
            Size[0] = 48;
            if ( !InitializeProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)v72, 1u, 0, Size) )
              wil::details::in1diag3::Throw_GetLastError(
                retaddr,
                (void *)0x1877,
                (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
                v24);
            v52 = v72;
            LOBYTE(v53) = 1;
            if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)v72, 0, 0x30003u, &Value, 0x10u, 0, 0) )
              wil::details::in1diag3::Throw_GetLastError(
                retaddr,
                (void *)0x1885,
                (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
                v25);
            v26 = 0;
            for ( i = v35[5]; i != v35[6]; i += 16 )
              v26 += *(_QWORD *)(*(_QWORD *)i + 120LL);
            v28 = v26 >> 22;
            v29 = (unsigned __int64)(unsigned int)RtlNumberOfSetBitsUlongPtr(Value) >> 1;
            if ( v29 >= v28 )
              v29 = v28;
            if ( v29 <= 8 )
            {
              if ( !v29 )
                v29 = 1;
            }
            else
            {
              v29 = 8;
            }
            for ( j = 0; j < v29; ++j )
            {
              v31 = operator new(0x18u);
              *(_WORD *)v31 = *((_WORD *)v35 + 16);
              v31[1] = this;
              v31[2] = &v66;
              v59 = v31;
              *(_QWORD *)ExitCode = CreateRemoteThreadEx(
                                      (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                                      0,
                                      0,
                                      MemoryManager::SaveVtlProtectionThread,
                                      v31,
                                      0,
                                      (LPPROC_THREAD_ATTRIBUTE_LIST)v72,
                                      0);
              std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::emplace_back<void *>(
                &v63,
                ExitCode);
              if ( (unsigned __int64)(*(_QWORD *)(*((_QWORD *)&v63 + 1) - 8LL) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
                wil::details::in1diag3::Throw_GetLastError(
                  retaddr,
                  (void *)0x18C1,
                  (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
                  v32);
              v4 |= 1u;
              v59 = 0;
              std::unique_ptr<MemoryManager::SaveVtlProtectionThreadContext>::~unique_ptr<MemoryManager::SaveVtlProtectionThreadContext>(&v59);
            }
            LOBYTE(v53) = 0;
            DeleteProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)v72);
            v33 = (__int64 **)v35[2];
            if ( *((_BYTE *)v33 + 25) )
            {
              for ( k = (__int64 *)v35[1]; !*((_BYTE *)k + 25) && v35 == (__int64 *)k[2]; k = (__int64 *)k[1] )
                v35 = k;
              v35 = k;
            }
            else
            {
              v35 = (__int64 *)v35[2];
              for ( m = *v33; !*((_BYTE *)m + 25); m = (__int64 *)*m )
                v35 = m;
            }
          }
          MemoryManager::WaitForAllThreadsToExit(&v63);
          v39 = (HANDLE *)*((_QWORD *)&v63 + 1);
          v38 = (HANDLE *)v63;
        }
        catch ( ... )
        {
          v59 = 0;
          wil::AcquireSRWLockExclusive(&v59, &v66);
          v67 = 1;
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v59);
          MemoryManager::WaitForAllThreadsToExit(&v63);
          throw;
        }
        while ( v38 != v39 )
        {
          ExitCode[0] = 0;
          if ( !GetExitCodeThread(*v38, ExitCode) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0x18E3,
              (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
              v40);
          v37 = ExitCode[0];
          if ( (ExitCode[0] & 0x80000000) != 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x18E4,
              (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
              (const char *)ExitCode[0],
              cbSize);
          ++v38;
        }
        v41 = *v69;
        while ( !*((_BYTE *)v41 + 25) )
        {
          LOBYTE(v37) = v58[0];
          std::_Sort_unchecked_MemoryBlockVtlProtectionChunk____lambda_aed391eee51fbb281f32e46a7fb4a9b9___(
            v41[5],
            v41[6],
            0xAAAAAAAAAAAAAAABuLL * ((v41[6] - v41[5]) >> 4),
            v37);
          v42 = v41[4];
          v43 = v41[7];
          v41[7] = 0;
          v44 = v41[6];
          v41[6] = 0;
          v45 = (_OWORD *)v41[5];
          v41[5] = 0;
          v52 = v45;
          v53 = v44;
          v54 = v43;
          MemoryBlock::SaveVtlProtections(v42, *((unsigned int *)this + 96), a2, &v52);
          v46 = (__int64 **)v41[2];
          if ( *((_BYTE *)v46 + 25) )
          {
            for ( n = (__int64 *)v41[1]; !*((_BYTE *)n + 25) && v41 == (__int64 *)n[2]; n = (__int64 *)n[1] )
              v41 = n;
            v41 = n;
          }
          else
          {
            v41 = (__int64 *)v41[2];
            for ( ii = *v46; !*((_BYTE *)ii + 25); ii = (__int64 *)*ii )
              v41 = ii;
          }
        }
        if ( (_QWORD)v63 )
        {
          std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>(
            v63,
            *((_QWORD *)&v63 + 1));
          std::_Deallocate<16>(v63, (v64 - v63) & 0xFFFFFFFFFFFFFFF8uLL);
          v63 = 0;
          v64 = 0;
        }
        RrwLockRelease(v13);
        MemoryManager::SaveVtlProtectionContext::~SaveVtlProtectionContext((MemoryManager::SaveVtlProtectionContext *)&v66);
        v49 = (*(__int64 (__fastcall **)(struct VmRepository *))(*(_QWORD *)a2 + 56LL))(a2);
        if ( v49 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1911,
            (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
            (const char *)(unsigned int)v49,
            cbSize);
        ++*((_DWORD *)this + 96);
        VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v56);
        Vml::VmReferencePtr<IMemoryContentsFileSizeChangeCallback,Vml::VmUserReferenceTraits>::~VmReferencePtr<IMemoryContentsFileSizeChangeCallback,Vml::VmUserReferenceTraits>(&v55);
      }
    }
  }
}

```

## disassembly

```asm
0x14009dbc0  mov     [rsp+arg_10], rbx
0x14009dbc5  mov     [rsp+arg_18], rsi
0x14009dbca  push    rdi
0x14009dbcb  push    r12
0x14009dbcd  push    r13
0x14009dbcf  push    r14
0x14009dbd1  push    r15
0x14009dbd3  sub     rsp, 560h
0x14009dbda  mov     rax, cs:__security_cookie
0x14009dbe1  xor     rax, rsp
0x14009dbe4  mov     [rsp+588h+var_38], rax
0x14009dbec  mov     r12, rdx
0x14009dbef  mov     [rsp+588h+var_548], rdx
0x14009dbf4  mov     r14, rcx
0x14009dbf7  xor     edi, edi
0x14009dbf9  mov     r13d, edi
0x14009dbfc  mov     [rsp+588h+ReturnLength], edi
0x14009dc03  cmp     dword ptr [rcx+90h], 700h
0x14009dc0d  jb      loc_14009E460
0x14009dc13  mov     [rsp+588h+var_4F0], edi
0x14009dc1a  mov     rcx, [rcx+20h]
0x14009dc1e  mov     rax, [rcx]
0x14009dc21  mov     rax, [rax+1C0h]
0x14009dc28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009dc2d  mov     r8, rax
0x14009dc30  mov     rcx, [rax]
0x14009dc33  mov     rax, [rcx+58h]
0x14009dc37  lea     rdx, [rsp+588h+var_4F0]
0x14009dc3f  mov     rcx, r8
0x14009dc42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009dc47  mov     rcx, [rsp+588h]; this
0x14009dc4f  test    eax, eax
0x14009dc51  jns     short loc_14009DC68
0x14009dc53  mov     r9d, eax; char *
0x14009dc56  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x14009dc5d  mov     edx, 17F0h; void *
0x14009dc62  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009dc68  mov     ecx, [rsp+588h+var_4F0]
0x14009dc6f  mov     eax, 1
0x14009dc74  shl     eax, cl
0x14009dc76  test    al, 1Ch
0x14009dc78  jnz     loc_14009E460
0x14009dc7e  cmp     [r14+180h], edi
0x14009dc85  jnz     short loc_14009DC97
0x14009dc87  mov     rcx, r14; this
0x14009dc8a  call    ?AreAnySecureVtlsEnabled@MemoryManager@@AEBA_NXZ; MemoryManager::AreAnySecureVtlsEnabled(void)
0x14009dc8f  test    al, al
0x14009dc91  jz      loc_14009E460
0x14009dc97  mov     [rsp+588h+var_508], dil
0x14009dc9f  lea     rdx, [rsp+588h+var_508]
0x14009dca7  mov     rcx, [r14+10h]
0x14009dcab  call    cs:__imp_VidVsmQueryProtectionsDirty
0x14009dcb2  nop     dword ptr [rax+rax+00h]
0x14009dcb7  mov     rcx, [rsp+588h]; this
0x14009dcbf  test    eax, eax
0x14009dcc1  jnz     short loc_14009DCD5
0x14009dcc3  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x14009dcca  mov     edx, 1809h; void *
0x14009dccf  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14009dcd5  cmp     [r14+180h], edi
0x14009dcdc  jz      short loc_14009DCEC
0x14009dcde  cmp     [rsp+588h+var_508], dil
0x14009dce6  jz      loc_14009E460
0x14009dcec  mov     ebx, 408h
0x14009dcf1  mov     r8d, ebx; Size
0x14009dcf4  xor     edx, edx; Val
0x14009dcf6  lea     rcx, [rsp+588h+SystemInformation]; void *
0x14009dcfe  call    memset_0
0x14009dd03  mov     [rsp+588h+ReturnLength], edi
0x14009dd0a  lea     r9, [rsp+588h+ReturnLength]; ReturnLength
0x14009dd12  mov     r8d, ebx; SystemInformationLength
0x14009dd15  lea     rdx, [rsp+588h+SystemInformation]; SystemInformation
0x14009dd1d  mov     ecx, 37h ; '7'; SystemInformationClass
0x14009dd22  call    cs:__imp_NtQuerySystemInformation
0x14009dd29  nop     dword ptr [rax+rax+00h]
0x14009dd2e  mov     rcx, [rsp+588h]; this
0x14009dd36  test    eax, eax
0x14009dd38  jns     short loc_14009DD4F
0x14009dd3a  mov     r9d, eax; char *
0x14009dd3d  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x14009dd44  mov     edx, 1827h; void *
0x14009dd49  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x14009dd4f  call    ?OpenShared@?$VmSingletonObject@VNumaPhysicalTopologyInfo@@UINumaPhysicalTopologyInfo@@@Vml@@SAPEAUINumaPhysicalTopologyInfo@@XZ; Vml::VmSingletonObject<NumaPhysicalTopologyInfo,INumaPhysicalTopologyInfo>::OpenShared(void)
0x14009dd54  mov     r15, rax
0x14009dd57  mov     [rsp+588h+var_528], rax
0x14009dd5c  mov     rcx, [r14+28h]
0x14009dd60  mov     rdx, [rcx]
0x14009dd63  mov     rax, [rdx+8]
0x14009dd67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009dd6c  mov     rdx, rax
0x14009dd6f  mov     rcx, [rax]
0x14009dd72  mov     rax, [rcx+58h]
0x14009dd76  mov     rcx, rdx
0x14009dd79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009dd7e  mov     [rsp+588h+Size], rax
0x14009dd86  xorps   xmm0, xmm0
0x14009dd89  movups  xmmword ptr [rsp+588h+var_520], xmm0
0x14009dd8e  mov     r8d, 1
0x14009dd94  mov     rdx, r12
0x14009dd97  lea     rcx, [rsp+588h+var_520]
0x14009dd9c  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x14009dda1  nop
0x14009dda2  mov     r9d, dword ptr [rsp+588h+var_520+8]; char *
0x14009dda7  mov     rcx, [rsp+588h]; this
0x14009ddaf  test    r9d, r9d
0x14009ddb2  jns     short loc_14009DDC6
0x14009ddb4  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x14009ddbb  mov     edx, 1830h; void *
0x14009ddc0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009ddc6  xor     eax, eax
0x14009ddc8  mov     [rsp+588h+var_4B8], rax
0x14009ddd0  mov     [rsp+588h+var_4B0], dil
0x14009ddd8  mov     [rsp+588h+var_4A8], rdi
0x14009dde0  mov     [rsp+588h+var_4A0], rdi
0x14009dde8  lea     ebx, [rax+40h]
0x14009ddeb  mov     ecx, ebx
0x14009dded  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x14009ddf2  mov     [rax], rax
0x14009ddf5  mov     [rax+8], rax
0x14009ddf9  mov     [rax+10h], rax
0x14009ddfd  mov     word ptr [rax+18h], 101h
0x14009de03  mov     [rsp+588h+var_4A8], rax
0x14009de0b  mov     [rsp+588h+var_498], rdi
0x14009de13  mov     [rsp+588h+var_490], rdi
0x14009de1b  mov     ecx, ebx
0x14009de1d  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x14009de22  mov     [rax], rax
0x14009de25  mov     [rax+8], rax
0x14009de29  mov     [rax+10h], rax
0x14009de2d  mov     word ptr [rax+18h], 101h
0x14009de33  mov     [rsp+588h+var_498], rax
0x14009de3b  mov     rsi, [r14+0A0h]
0x14009de42  add     rsi, 18h
0x14009de46  or      edx, 0FFFFFFFFh
0x14009de49  mov     rcx, rsi
0x14009de4c  call    RrwLockAcquireShared
0x14009de51  test    eax, eax
0x14009de53  jnz     short loc_14009DE75
0x14009de55  mov     rcx, [rsp+588h]; this
0x14009de5d  mov     r9d, 102h; char *
0x14009de63  lea     r8, aOnecoreVmCommo_24; "onecore\\vm\\common\\vml\\VmReaderWrite"...
0x14009de6a  mov     edx, 249h; void *
0x14009de6f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14009de75  mov     [rsp+588h+var_510], rsi
0x14009de7a  mov     qword ptr [rsp+588h+ExitCode], rdi
0x14009de82  lea     rdx, [rsp+588h+ExitCode]
0x14009de8a  mov     rcx, [r14+0A0h]
0x14009de91  call    ?IteratorGetFirst@MemoryBlockContainer@@QEAAPEAVMemoryBlock@@AEAV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVMemoryBlock@@@std@@@std@@@std@@@Z; MemoryBlockContainer::IteratorGetFirst(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MemoryBlock *>>> &)
0x14009de96  mov     rdi, rax
0x14009de99  mov     [rsp+588h+var_500], rax
0x14009dea1  test    rax, rax
0x14009dea4  jz      loc_14009DF95
0x14009deaa  mov     rcx, rax
0x14009dead  mov     rbx, qword ptr [rsp+588h+ExitCode]
0x14009deb5  mov     r12, [rsp+588h+Size]
0x14009debd  cmp     byte ptr [rdi], 0
0x14009dec0  jz      loc_14009DF6D
0x14009dec6  mov     [rsp+588h+Size], 0
0x14009ded2  mov     [rsp+588h+var_4C0], 0
0x14009dede  mov     rax, [r15]
0x14009dee1  movzx   edx, byte ptr [rcx+0B8h]
0x14009dee8  mov     r9b, 1
0x14009deeb  lea     r8, [rsp+588h+Size]
0x14009def3  mov     dl, [rdx+r12+118h]
0x14009defb  mov     rcx, r15
0x14009defe  mov     rax, [rax+10h]
0x14009df02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009df07  mov     rcx, [r15]
0x14009df0a  mov     dl, al
0x14009df0c  mov     rax, [rcx+30h]
0x14009df10  mov     rcx, r15
0x14009df13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009df18  movzx   eax, al
0x14009df1b  mov     word ptr [rsp+588h+ExitCode], ax
0x14009df23  lea     r8, [rsp+588h+ExitCode]
0x14009df2b  lea     rdx, [rsp+588h+var_540]
0x14009df30  lea     rcx, [rsp+588h+var_4A8]
0x14009df38  call    ??$_Try_emplace@AEBG$$V@?$map@GV?$vector@UMemoryBlockSaveVtlProtectionContext@MemoryManager@@V?$allocator@UMemoryBlockSaveVtlProtectionContext@MemoryManager@@@std@@@std@@U?$less@G@2@V?$allocator@U?$pair@$$CBGV?$vector@UMemoryBlockSaveVtlProtectionContext@MemoryManager@@V?$allocator@UMemoryBlockSaveVtlProtectionContext@MemoryManager@@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBGV?$vector@UMemoryBlockSaveVtlProtectionContext@MemoryManager@@V?$allocator@UMemoryBlockSaveVtlProtectionContext@MemoryManager@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBG@Z; std::map<ushort,std::vector<MemoryManager::MemoryBlockSaveVtlProtectionContext>>::_Try_emplace<ushort const &,>(ushort const &)
0x14009df3d  mov     rcx, [rax]
0x14009df40  add     rcx, 28h ; '('
0x14009df44  mov     rdx, [rcx+8]
0x14009df48  cmp     rdx, [rcx+10h]
0x14009df4c  jz      short loc_14009DF60
0x14009df4e  mov     [rdx], rdi
0x14009df51  mov     qword ptr [rdx+8], 0
0x14009df59  add     qword ptr [rcx+8], 10h
0x14009df5e  jmp     short loc_14009DF6D
0x14009df60  lea     r8, [rsp+588h+var_500]
0x14009df68  call    ??$_Emplace_reallocate@AEAPEAVMemoryBlock@@@?$vector@UMemoryBlockSaveVtlProtectionContext@MemoryManager@@V?$allocator@UMemoryBlockSaveVtlProtectionContext@MemoryManager@@@std@@@std@@AEAAPEAUMemoryBlockSaveVtlProtectionContext@MemoryManager@@QEAU23@AEAPEAVMemoryBlock@@@Z; std::vector<MemoryManager::MemoryBlockSaveVtlProtectionContext>::_Emplace_reallocate<MemoryBlock * &>(MemoryManager::MemoryBlockSaveVtlProtectionContext * const,MemoryBlock * &)
0x14009df6d  mov     rax, [r14+0A0h]
0x14009df74  cmp     rbx, [rax+8]
0x14009df78  jz      short loc_14009DF95
0x14009df7a  mov     rdi, [rbx]
0x14009df7d  add     rbx, 8
0x14009df81  mov     [rsp+588h+var_500], rdi
0x14009df89  mov     rcx, rdi
0x14009df8c  test    rdi, rdi
0x14009df8f  jnz     loc_14009DEBD
0x14009df95  xorps   xmm1, xmm1
0x14009df98  movdqu  [rsp+588h+var_4E8], xmm1
0x14009dfa1  xor     r15d, r15d
0x14009dfa4  mov     [rsp+588h+var_4D8], r15
0x14009dfac  mov     rbx, [rsp+588h+var_4A8]
0x14009dfb4  mov     rbx, [rbx]
0x14009dfb7  cmp     [rbx+19h], r15b
0x14009dfbb  jnz     loc_14009E24A
0x14009dfc1  movzx   eax, word ptr [rbx+20h]
0x14009dfc5  add     rax, rax
0x14009dfc8  movups  xmm0, [rsp+rax*8+588h+var_440]
0x14009dfd0  movdqu  [rsp+588h+Value], xmm0
0x14009dfd9  xorps   xmm1, xmm1
0x14009dfdc  movups  [rsp+588h+var_478], xmm1
0x14009dfe4  movups  [rsp+588h+var_468], xmm1
0x14009dfec  movups  [rsp+588h+var_458], xmm1
0x14009dff4  mov     [rsp+588h+Size], 30h ; '0'
0x14009e000  lea     r9, [rsp+588h+Size]; lpSize
0x14009e008  xor     r8d, r8d; dwFlags
0x14009e00b  lea     edx, [r8+1]; dwAttributeCount
0x14009e00f  lea     rcx, [rsp+588h+var_478]; lpAttributeList
0x14009e017  call    cs:__imp_InitializeProcThreadAttributeList
0x14009e01e  nop     dword ptr [rax+rax+00h]
0x14009e023  mov     rcx, [rsp+588h]; this
0x14009e02b  test    eax, eax
0x14009e02d  jnz     short loc_14009E040
0x14009e02f  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x14009e036  mov     edx, 1877h; void *
0x14009e03b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14009e040  lea     rdi, [rsp+588h+var_478]
0x14009e048  mov     [rsp+588h+var_540], rdi
0x14009e04d  mov     byte ptr [rsp+588h+var_538], 1
0x14009e052  mov     [rsp+588h+lpReturnSize], r15; lpReturnSize
0x14009e057  mov     [rsp+588h+lpPreviousValue], r15; lpPreviousValue
0x14009e05c  mov     [rsp+588h+cbSize], 10h; cbSize
0x14009e065  lea     r9, [rsp+588h+Value]; lpValue
0x14009e06d  xor     edx, edx; dwFlags
0x14009e06f  mov     r8d, 30003h; Attribute
0x14009e075  lea     rcx, [rsp+588h+var_478]; lpAttributeList
0x14009e07d  call    cs:__imp_UpdateProcThreadAttribute
0x14009e084  nop     dword ptr [rax+rax+00h]
0x14009e089  mov     rcx, [rsp+588h]; this
0x14009e091  test    eax, eax
0x14009e093  jnz     short loc_14009E0A6
0x14009e095  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x14009e09c  mov     edx, 1885h; void *
0x14009e0a1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14009e0a6  mov     r12, r15
0x14009e0a9  mov     rcx, [rbx+28h]
0x14009e0ad  jmp     short loc_14009E0BA
0x14009e0af  mov     rax, [rcx]
0x14009e0b2  add     r12, [rax+78h]
0x14009e0b6  add     rcx, 10h
0x14009e0ba  cmp     rcx, [rbx+30h]
0x14009e0be  jnz     short loc_14009E0AF
0x14009e0c0  shr     r12, 16h
0x14009e0c4  mov     rcx, qword ptr [rsp+588h+Value]
0x14009e0cc  call    cs:__imp_RtlNumberOfSetBitsUlongPtr
0x14009e0d3  nop     dword ptr [rax+rax+00h]
0x14009e0d8  mov     r15d, eax
0x14009e0db  shr     r15, 1
0x14009e0de  cmp     r15, r12
0x14009e0e1  cmovnb  r15, r12
0x14009e0e5  cmp     r15, 8
0x14009e0e9  jbe     short loc_14009E0F3
0x14009e0eb  mov     r15d, 8
0x14009e0f1  jmp     short loc_14009E0FF
0x14009e0f3  cmp     r15, 1
0x14009e0f7  jnb     short loc_14009E0FF
0x14009e0f9  mov     r15d, 1
0x14009e0ff  xor     r12d, r12d
0x14009e102  cmp     r12, r15
0x14009e105  jnb     loc_14009E1E4
0x14009e10b  mov     ecx, 18h; Size
0x14009e110  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14009e115  movzx   ecx, word ptr [rbx+20h]
0x14009e119  mov     [rax], cx
0x14009e11c  mov     [rax+8], r14
0x14009e120  lea     rcx, [rsp+588h+var_4B8]
0x14009e128  mov     [rax+10h], rcx
0x14009e12c  mov     [rsp+588h+var_500], rax
0x14009e134  mov     [rsp+588h+lpThreadId], 0; lpThreadId
0x14009e13d  lea     rcx, [rsp+588h+var_478]
0x14009e145  mov     [rsp+588h+lpReturnSize], rcx; lpAttributeList
0x14009e14a  mov     dword ptr [rsp+588h+lpPreviousValue], 0; dwCreationFlags
0x14009e152  mov     [rsp+588h+cbSize], rax; lpParameter
0x14009e157  lea     r9, ?SaveVtlProtectionThread@MemoryManager@@CAKPEAX@Z; lpStartAddress
0x14009e15e  xor     r8d, r8d; dwStackSize
0x14009e161  xor     edx, edx; lpThreadAttributes
0x14009e163  or      rcx, 0FFFFFFFFFFFFFFFFh; hProcess
0x14009e167  call    cs:__imp_CreateRemoteThreadEx
0x14009e16e  nop     dword ptr [rax+rax+00h]
0x14009e173  mov     qword ptr [rsp+588h+ExitCode], rax
0x14009e17b  lea     rdx, [rsp+588h+ExitCode]
0x14009e183  lea     rcx, [rsp+588h+var_4E8]
0x14009e18b  call    ??$emplace_back@PEAX@?$vector@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@$$QEAPEAX@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::emplace_back<void *>(void * &&)
0x14009e190  mov     rax, qword ptr [rsp+588h+var_4E8+8]
0x14009e198  mov     rcx, [rax-8]
0x14009e19c  dec     rcx
0x14009e19f  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14009e1a3  ja      short loc_14009E1CA
0x14009e1a5  or      r13d, 1
  ... truncated ...
```
