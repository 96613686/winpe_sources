# MemoryManager::SaveVtlProtections(VmRepository *)

- ea: `0x1400b7900`
- end: `0x1400b81ce`
- name: `?SaveVtlProtections@MemoryManager@@UEAAXPEAVVmRepository@@@Z`
- size: `2254`
- prototype: `void __fastcall(MemoryManager *__hidden this, struct VmRepository *)`
- caller_count: `3`
- callee_count: `28`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14005d988`
- `0x1400b8974`
- `0x1400ba91c`

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
- `0x1400a50e8`
- `0x1400b7888`
- `0x1400b7900`
- `0x1400b8574`
- `0x1400b9940`
- `0x1400ba144`
- `0x1400d6d8c`
- `0x14011ea40`
- `0x14011edec`
- `0x14011f6fc`
- `0x140161200`
- `0x1401eedbc`
- `0x1401f1804`
- `0x1401f1bcc`
- `0x1401f2588`
- `0x1401f3234`
- `0x1401f4550`
- `0x1401ffd00`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1400b7dbd`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1400b7dbd`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1400b7d57`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1400b7d57`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1400b7fbc`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1400b7fbc`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1400b7f2f`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1400b7f2f`
- `api-ms-win-core-processthreads-l1-1-0!CreateRemoteThreadEx` at `0x1400b7ea7`
- `api-ms-win-core-processthreads-l1-1-0!CreateRemoteThreadEx` at `0x1400b7ea7`
- `ntdll!NtQuerySystemInformation` at `0x1400b7a62`
- `ntdll!NtQuerySystemInformation` at `0x1400b7a62`
- `ntdll!RtlNumberOfSetBitsUlongPtr` at `0x1400b7e0c`
- `ntdll!RtlNumberOfSetBitsUlongPtr` at `0x1400b7e0c`
- `vid!VidVsmQueryProtectionsDirty` at `0x1400b79eb`
- `vid!VidVsmQueryProtectionsDirty` at `0x1400b79eb`

## string_xrefs

- `0x1400b7ba3`: `onecore\vm\common\vml\VmReaderWriterLock.h`

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
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 464LL))(*((_QWORD *)this + 4));
    v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v5 + 88LL))(v5, &v61);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x17DD,
        (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
        (const char *)(unsigned int)v6,
        cbSize);
    if ( ((1 << v61) & 0x1C) == 0 && (*((_DWORD *)this + 96) || MemoryManager::AreAnySecureVtlsEnabled(this)) )
    {
      v58[0] = 0;
      if ( !(unsigned int)VidVsmQueryProtectionsDirty(*((_QWORD *)this + 2), v58) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x17F6,
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
            (void *)0x1814,
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
            (void *)0x181D,
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
                (void *)0x1864,
                (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
                v24);
            v52 = v72;
            LOBYTE(v53) = 1;
            if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)v72, 0, 0x30003u, &Value, 0x10u, 0, 0) )
              wil::details::in1diag3::Throw_GetLastError(
                retaddr,
                (void *)0x1872,
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
                  (void *)0x18AE,
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
              (void *)0x18D0,
              (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
              v40);
          v37 = ExitCode[0];
          if ( (ExitCode[0] & 0x80000000) != 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x18D1,
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
            (void *)0x18FE,
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
0x1400b7900  mov     [rsp+arg_10], rbx
0x1400b7905  mov     [rsp+arg_18], rsi
0x1400b790a  push    rdi
0x1400b790b  push    r12
0x1400b790d  push    r13
0x1400b790f  push    r14
0x1400b7911  push    r15
0x1400b7913  sub     rsp, 560h
0x1400b791a  mov     rax, cs:__security_cookie
0x1400b7921  xor     rax, rsp
0x1400b7924  mov     [rsp+588h+var_38], rax
0x1400b792c  mov     r12, rdx
0x1400b792f  mov     [rsp+588h+var_548], rdx
0x1400b7934  mov     r14, rcx
0x1400b7937  xor     edi, edi
0x1400b7939  mov     r13d, edi
0x1400b793c  mov     [rsp+588h+ReturnLength], edi
0x1400b7943  cmp     dword ptr [rcx+90h], 700h
0x1400b794d  jb      loc_1400B81A0
0x1400b7953  mov     [rsp+588h+var_4F0], edi
0x1400b795a  mov     rcx, [rcx+20h]
0x1400b795e  mov     rax, [rcx]
0x1400b7961  mov     rax, [rax+1D0h]
0x1400b7968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b796d  mov     r8, rax
0x1400b7970  mov     rcx, [rax]
0x1400b7973  mov     rax, [rcx+58h]
0x1400b7977  lea     rdx, [rsp+588h+var_4F0]
0x1400b797f  mov     rcx, r8
0x1400b7982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b7987  mov     rcx, [rsp+588h]; this
0x1400b798f  test    eax, eax
0x1400b7991  jns     short loc_1400B79A8
0x1400b7993  mov     r9d, eax; char *
0x1400b7996  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x1400b799d  mov     edx, 17DDh; void *
0x1400b79a2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400b79a8  mov     ecx, [rsp+588h+var_4F0]
0x1400b79af  mov     eax, 1
0x1400b79b4  shl     eax, cl
0x1400b79b6  test    al, 1Ch
0x1400b79b8  jnz     loc_1400B81A0
0x1400b79be  cmp     [r14+180h], edi
0x1400b79c5  jnz     short loc_1400B79D7
0x1400b79c7  mov     rcx, r14; this
0x1400b79ca  call    ?AreAnySecureVtlsEnabled@MemoryManager@@AEBA_NXZ; MemoryManager::AreAnySecureVtlsEnabled(void)
0x1400b79cf  test    al, al
0x1400b79d1  jz      loc_1400B81A0
0x1400b79d7  mov     [rsp+588h+var_508], dil
0x1400b79df  lea     rdx, [rsp+588h+var_508]
0x1400b79e7  mov     rcx, [r14+10h]
0x1400b79eb  call    cs:__imp_VidVsmQueryProtectionsDirty
0x1400b79f2  nop     dword ptr [rax+rax+00h]
0x1400b79f7  mov     rcx, [rsp+588h]; this
0x1400b79ff  test    eax, eax
0x1400b7a01  jnz     short loc_1400B7A15
0x1400b7a03  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x1400b7a0a  mov     edx, 17F6h; void *
0x1400b7a0f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400b7a15  cmp     [r14+180h], edi
0x1400b7a1c  jz      short loc_1400B7A2C
0x1400b7a1e  cmp     [rsp+588h+var_508], dil
0x1400b7a26  jz      loc_1400B81A0
0x1400b7a2c  mov     ebx, 408h
0x1400b7a31  mov     r8d, ebx; Size
0x1400b7a34  xor     edx, edx; Val
0x1400b7a36  lea     rcx, [rsp+588h+SystemInformation]; void *
0x1400b7a3e  call    memset_0
0x1400b7a43  mov     [rsp+588h+ReturnLength], edi
0x1400b7a4a  lea     r9, [rsp+588h+ReturnLength]; ReturnLength
0x1400b7a52  mov     r8d, ebx; SystemInformationLength
0x1400b7a55  lea     rdx, [rsp+588h+SystemInformation]; SystemInformation
0x1400b7a5d  mov     ecx, 37h ; '7'; SystemInformationClass
0x1400b7a62  call    cs:__imp_NtQuerySystemInformation
0x1400b7a69  nop     dword ptr [rax+rax+00h]
0x1400b7a6e  mov     rcx, [rsp+588h]; this
0x1400b7a76  test    eax, eax
0x1400b7a78  jns     short loc_1400B7A8F
0x1400b7a7a  mov     r9d, eax; char *
0x1400b7a7d  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x1400b7a84  mov     edx, 1814h; void *
0x1400b7a89  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1400b7a8f  call    ?OpenShared@?$VmSingletonObject@VNumaPhysicalTopologyInfo@@UINumaPhysicalTopologyInfo@@@Vml@@SAPEAUINumaPhysicalTopologyInfo@@XZ; Vml::VmSingletonObject<NumaPhysicalTopologyInfo,INumaPhysicalTopologyInfo>::OpenShared(void)
0x1400b7a94  mov     r15, rax
0x1400b7a97  mov     [rsp+588h+var_528], rax
0x1400b7a9c  mov     rcx, [r14+28h]
0x1400b7aa0  mov     rdx, [rcx]
0x1400b7aa3  mov     rax, [rdx+8]
0x1400b7aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b7aac  mov     rdx, rax
0x1400b7aaf  mov     rcx, [rax]
0x1400b7ab2  mov     rax, [rcx+58h]
0x1400b7ab6  mov     rcx, rdx
0x1400b7ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b7abe  mov     [rsp+588h+Size], rax
0x1400b7ac6  xorps   xmm0, xmm0
0x1400b7ac9  movups  xmmword ptr [rsp+588h+var_520], xmm0
0x1400b7ace  mov     r8d, 1
0x1400b7ad4  mov     rdx, r12
0x1400b7ad7  lea     rcx, [rsp+588h+var_520]
0x1400b7adc  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x1400b7ae1  nop
0x1400b7ae2  mov     r9d, dword ptr [rsp+588h+var_520+8]; char *
0x1400b7ae7  mov     rcx, [rsp+588h]; this
0x1400b7aef  test    r9d, r9d
0x1400b7af2  jns     short loc_1400B7B06
0x1400b7af4  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x1400b7afb  mov     edx, 181Dh; void *
0x1400b7b00  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400b7b06  xor     eax, eax
0x1400b7b08  mov     [rsp+588h+var_4B8], rax
0x1400b7b10  mov     [rsp+588h+var_4B0], dil
0x1400b7b18  mov     [rsp+588h+var_4A8], rdi
0x1400b7b20  mov     [rsp+588h+var_4A0], rdi
0x1400b7b28  lea     ebx, [rax+40h]
0x1400b7b2b  mov     ecx, ebx
0x1400b7b2d  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1400b7b32  mov     [rax], rax
0x1400b7b35  mov     [rax+8], rax
0x1400b7b39  mov     [rax+10h], rax
0x1400b7b3d  mov     word ptr [rax+18h], 101h
0x1400b7b43  mov     [rsp+588h+var_4A8], rax
0x1400b7b4b  mov     [rsp+588h+var_498], rdi
0x1400b7b53  mov     [rsp+588h+var_490], rdi
0x1400b7b5b  mov     ecx, ebx
0x1400b7b5d  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1400b7b62  mov     [rax], rax
0x1400b7b65  mov     [rax+8], rax
0x1400b7b69  mov     [rax+10h], rax
0x1400b7b6d  mov     word ptr [rax+18h], 101h
0x1400b7b73  mov     [rsp+588h+var_498], rax
0x1400b7b7b  mov     rsi, [r14+0A0h]
0x1400b7b82  add     rsi, 18h
0x1400b7b86  or      edx, 0FFFFFFFFh
0x1400b7b89  mov     rcx, rsi
0x1400b7b8c  call    RrwLockAcquireShared
0x1400b7b91  test    eax, eax
0x1400b7b93  jnz     short loc_1400B7BB5
0x1400b7b95  mov     rcx, [rsp+588h]; this
0x1400b7b9d  mov     r9d, 102h; char *
0x1400b7ba3  lea     r8, aOnecoreVmCommo_23; "onecore\\vm\\common\\vml\\VmReaderWrite"...
0x1400b7baa  mov     edx, 249h; void *
0x1400b7baf  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400b7bb5  mov     [rsp+588h+var_510], rsi
0x1400b7bba  mov     qword ptr [rsp+588h+ExitCode], rdi
0x1400b7bc2  lea     rdx, [rsp+588h+ExitCode]
0x1400b7bca  mov     rcx, [r14+0A0h]
0x1400b7bd1  call    ?IteratorGetFirst@MemoryBlockContainer@@QEAAPEAVMemoryBlock@@AEAV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVMemoryBlock@@@std@@@std@@@std@@@Z; MemoryBlockContainer::IteratorGetFirst(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MemoryBlock *>>> &)
0x1400b7bd6  mov     rdi, rax
0x1400b7bd9  mov     [rsp+588h+var_500], rax
0x1400b7be1  test    rax, rax
0x1400b7be4  jz      loc_1400B7CD5
0x1400b7bea  mov     rcx, rax
0x1400b7bed  mov     rbx, qword ptr [rsp+588h+ExitCode]
0x1400b7bf5  mov     r12, [rsp+588h+Size]
0x1400b7bfd  cmp     byte ptr [rdi], 0
0x1400b7c00  jz      loc_1400B7CAD
0x1400b7c06  mov     [rsp+588h+Size], 0
0x1400b7c12  mov     [rsp+588h+var_4C0], 0
0x1400b7c1e  mov     rax, [r15]
0x1400b7c21  movzx   edx, byte ptr [rcx+0B8h]
0x1400b7c28  mov     r9b, 1
0x1400b7c2b  lea     r8, [rsp+588h+Size]
0x1400b7c33  mov     dl, [rdx+r12+118h]
0x1400b7c3b  mov     rcx, r15
0x1400b7c3e  mov     rax, [rax+10h]
0x1400b7c42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b7c47  mov     rcx, [r15]
0x1400b7c4a  mov     dl, al
0x1400b7c4c  mov     rax, [rcx+30h]
0x1400b7c50  mov     rcx, r15
0x1400b7c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b7c58  movzx   eax, al
0x1400b7c5b  mov     word ptr [rsp+588h+ExitCode], ax
0x1400b7c63  lea     r8, [rsp+588h+ExitCode]
0x1400b7c6b  lea     rdx, [rsp+588h+var_540]
0x1400b7c70  lea     rcx, [rsp+588h+var_4A8]
0x1400b7c78  call    ??$_Try_emplace@AEBG$$V@?$map@GV?$vector@UMemoryBlockSaveVtlProtectionContext@MemoryManager@@V?$allocator@UMemoryBlockSaveVtlProtectionContext@MemoryManager@@@std@@@std@@U?$less@G@2@V?$allocator@U?$pair@$$CBGV?$vector@UMemoryBlockSaveVtlProtectionContext@MemoryManager@@V?$allocator@UMemoryBlockSaveVtlProtectionContext@MemoryManager@@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBGV?$vector@UMemoryBlockSaveVtlProtectionContext@MemoryManager@@V?$allocator@UMemoryBlockSaveVtlProtectionContext@MemoryManager@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBG@Z; std::map<ushort,std::vector<MemoryManager::MemoryBlockSaveVtlProtectionContext>>::_Try_emplace<ushort const &,>(ushort const &)
0x1400b7c7d  mov     rcx, [rax]
0x1400b7c80  add     rcx, 28h ; '('
0x1400b7c84  mov     rdx, [rcx+8]
0x1400b7c88  cmp     rdx, [rcx+10h]
0x1400b7c8c  jz      short loc_1400B7CA0
0x1400b7c8e  mov     [rdx], rdi
0x1400b7c91  mov     qword ptr [rdx+8], 0
0x1400b7c99  add     qword ptr [rcx+8], 10h
0x1400b7c9e  jmp     short loc_1400B7CAD
0x1400b7ca0  lea     r8, [rsp+588h+var_500]
0x1400b7ca8  call    ??$_Emplace_reallocate@AEAPEAVMemoryBlock@@@?$vector@UMemoryBlockSaveVtlProtectionContext@MemoryManager@@V?$allocator@UMemoryBlockSaveVtlProtectionContext@MemoryManager@@@std@@@std@@AEAAPEAUMemoryBlockSaveVtlProtectionContext@MemoryManager@@QEAU23@AEAPEAVMemoryBlock@@@Z; std::vector<MemoryManager::MemoryBlockSaveVtlProtectionContext>::_Emplace_reallocate<MemoryBlock * &>(MemoryManager::MemoryBlockSaveVtlProtectionContext * const,MemoryBlock * &)
0x1400b7cad  mov     rax, [r14+0A0h]
0x1400b7cb4  cmp     rbx, [rax+8]
0x1400b7cb8  jz      short loc_1400B7CD5
0x1400b7cba  mov     rdi, [rbx]
0x1400b7cbd  add     rbx, 8
0x1400b7cc1  mov     [rsp+588h+var_500], rdi
0x1400b7cc9  mov     rcx, rdi
0x1400b7ccc  test    rdi, rdi
0x1400b7ccf  jnz     loc_1400B7BFD
0x1400b7cd5  xorps   xmm1, xmm1
0x1400b7cd8  movdqu  [rsp+588h+var_4E8], xmm1
0x1400b7ce1  xor     r15d, r15d
0x1400b7ce4  mov     [rsp+588h+var_4D8], r15
0x1400b7cec  mov     rbx, [rsp+588h+var_4A8]
0x1400b7cf4  mov     rbx, [rbx]
0x1400b7cf7  cmp     [rbx+19h], r15b
0x1400b7cfb  jnz     loc_1400B7F8A
0x1400b7d01  movzx   eax, word ptr [rbx+20h]
0x1400b7d05  add     rax, rax
0x1400b7d08  movups  xmm0, [rsp+rax*8+588h+var_440]
0x1400b7d10  movdqu  [rsp+588h+Value], xmm0
0x1400b7d19  xorps   xmm1, xmm1
0x1400b7d1c  movups  [rsp+588h+var_478], xmm1
0x1400b7d24  movups  [rsp+588h+var_468], xmm1
0x1400b7d2c  movups  [rsp+588h+var_458], xmm1
0x1400b7d34  mov     [rsp+588h+Size], 30h ; '0'
0x1400b7d40  lea     r9, [rsp+588h+Size]; lpSize
0x1400b7d48  xor     r8d, r8d; dwFlags
0x1400b7d4b  lea     edx, [r8+1]; dwAttributeCount
0x1400b7d4f  lea     rcx, [rsp+588h+var_478]; lpAttributeList
0x1400b7d57  call    cs:__imp_InitializeProcThreadAttributeList
0x1400b7d5e  nop     dword ptr [rax+rax+00h]
0x1400b7d63  mov     rcx, [rsp+588h]; this
0x1400b7d6b  test    eax, eax
0x1400b7d6d  jnz     short loc_1400B7D80
0x1400b7d6f  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x1400b7d76  mov     edx, 1864h; void *
0x1400b7d7b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400b7d80  lea     rdi, [rsp+588h+var_478]
0x1400b7d88  mov     [rsp+588h+var_540], rdi
0x1400b7d8d  mov     byte ptr [rsp+588h+var_538], 1
0x1400b7d92  mov     [rsp+588h+lpReturnSize], r15; lpReturnSize
0x1400b7d97  mov     [rsp+588h+lpPreviousValue], r15; lpPreviousValue
0x1400b7d9c  mov     [rsp+588h+cbSize], 10h; cbSize
0x1400b7da5  lea     r9, [rsp+588h+Value]; lpValue
0x1400b7dad  xor     edx, edx; dwFlags
0x1400b7daf  mov     r8d, 30003h; Attribute
0x1400b7db5  lea     rcx, [rsp+588h+var_478]; lpAttributeList
0x1400b7dbd  call    cs:__imp_UpdateProcThreadAttribute
0x1400b7dc4  nop     dword ptr [rax+rax+00h]
0x1400b7dc9  mov     rcx, [rsp+588h]; this
0x1400b7dd1  test    eax, eax
0x1400b7dd3  jnz     short loc_1400B7DE6
0x1400b7dd5  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x1400b7ddc  mov     edx, 1872h; void *
0x1400b7de1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400b7de6  mov     r12, r15
0x1400b7de9  mov     rcx, [rbx+28h]
0x1400b7ded  jmp     short loc_1400B7DFA
0x1400b7def  mov     rax, [rcx]
0x1400b7df2  add     r12, [rax+78h]
0x1400b7df6  add     rcx, 10h
0x1400b7dfa  cmp     rcx, [rbx+30h]
0x1400b7dfe  jnz     short loc_1400B7DEF
0x1400b7e00  shr     r12, 16h
0x1400b7e04  mov     rcx, qword ptr [rsp+588h+Value]
0x1400b7e0c  call    cs:__imp_RtlNumberOfSetBitsUlongPtr
0x1400b7e13  nop     dword ptr [rax+rax+00h]
0x1400b7e18  mov     r15d, eax
0x1400b7e1b  shr     r15, 1
0x1400b7e1e  cmp     r15, r12
0x1400b7e21  cmovnb  r15, r12
0x1400b7e25  cmp     r15, 8
0x1400b7e29  jbe     short loc_1400B7E33
0x1400b7e2b  mov     r15d, 8
0x1400b7e31  jmp     short loc_1400B7E3F
0x1400b7e33  cmp     r15, 1
0x1400b7e37  jnb     short loc_1400B7E3F
0x1400b7e39  mov     r15d, 1
0x1400b7e3f  xor     r12d, r12d
0x1400b7e42  cmp     r12, r15
0x1400b7e45  jnb     loc_1400B7F24
0x1400b7e4b  mov     ecx, 18h; Size
0x1400b7e50  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400b7e55  movzx   ecx, word ptr [rbx+20h]
0x1400b7e59  mov     [rax], cx
0x1400b7e5c  mov     [rax+8], r14
0x1400b7e60  lea     rcx, [rsp+588h+var_4B8]
0x1400b7e68  mov     [rax+10h], rcx
0x1400b7e6c  mov     [rsp+588h+var_500], rax
0x1400b7e74  mov     [rsp+588h+lpThreadId], 0; lpThreadId
0x1400b7e7d  lea     rcx, [rsp+588h+var_478]
0x1400b7e85  mov     [rsp+588h+lpReturnSize], rcx; lpAttributeList
0x1400b7e8a  mov     dword ptr [rsp+588h+lpPreviousValue], 0; dwCreationFlags
0x1400b7e92  mov     [rsp+588h+cbSize], rax; lpParameter
0x1400b7e97  lea     r9, ?SaveVtlProtectionThread@MemoryManager@@CAKPEAX@Z; lpStartAddress
0x1400b7e9e  xor     r8d, r8d; dwStackSize
0x1400b7ea1  xor     edx, edx; lpThreadAttributes
0x1400b7ea3  or      rcx, 0FFFFFFFFFFFFFFFFh; hProcess
0x1400b7ea7  call    cs:__imp_CreateRemoteThreadEx
0x1400b7eae  nop     dword ptr [rax+rax+00h]
0x1400b7eb3  mov     qword ptr [rsp+588h+ExitCode], rax
0x1400b7ebb  lea     rdx, [rsp+588h+ExitCode]
0x1400b7ec3  lea     rcx, [rsp+588h+var_4E8]
0x1400b7ecb  call    ??$emplace_back@PEAX@?$vector@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@$$QEAPEAX@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::emplace_back<void *>(void * &&)
0x1400b7ed0  mov     rax, qword ptr [rsp+588h+var_4E8+8]
0x1400b7ed8  mov     rcx, [rax-8]
0x1400b7edc  dec     rcx
0x1400b7edf  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1400b7ee3  ja      short loc_1400B7F0A
0x1400b7ee5  or      r13d, 1
  ... truncated ...
```
