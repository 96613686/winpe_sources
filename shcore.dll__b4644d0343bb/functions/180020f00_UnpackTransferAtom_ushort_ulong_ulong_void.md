# UnpackTransferAtom(ushort,ulong,ulong,void * *)

- ea: `0x180020f00`
- end: `0x180021403`
- name: `?UnpackTransferAtom@@YAJGKKPEAPEAX@Z`
- size: `1283`
- prototype: `__int64 __fastcall(unsigned __int16, unsigned int, unsigned int, void **)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001fdd0`
- `0x180020310`

## callees

- `0x18000ddd4`
- `0x18001c82c`
- `0x18002009c`
- `0x180020f00`
- `0x18002140c`
- `0x1800214b8`
- `0x18004d37c`
- `0x180066910`
- `0x180066cfc`
- `0x1800672e8`
- `0x180068d9c`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800210cc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800210cc`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180021017`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180021060`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180021017`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180021060`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800212c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800212e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800212c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800212e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800212f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002130a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800212f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002130a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021355`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021377`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021355`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021377`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002133f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002133f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800210af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800210af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800213d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800213d8`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x180020f3f`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x180020f3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800210b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800210b9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UnpackTransferAtom(ATOM a1, __int64 a2, int a3, void **a4)
{
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  struct _RTL_CRITICAL_SECTION *v6; // rax
  struct _RTL_CRITICAL_SECTION *v7; // rsi
  __int64 v8; // rcx
  char *v9; // rax
  char *v10; // rdi
  _BYTE *v11; // rax
  __int64 v12; // r12
  WCHAR *v13; // rdi
  int Error; // esi
  int v15; // ebx
  unsigned int v16; // r10d
  WCHAR v17; // ax
  unsigned __int8 v18; // al
  unsigned __int8 v19; // r8
  DWORD CurrentProcessId; // r14d
  HANDLE v22; // r15
  unsigned int v23; // ebp
  int v24; // edx
  unsigned int v25; // ecx
  DWORD v26; // ebx
  HANDLE v27; // rax
  int v28; // edx
  unsigned int v29; // ecx
  void *v30; // rdi
  HANDLE CurrentProcess; // rax
  void *v32; // rsi
  HANDLE v33; // rax
  __int64 v34; // rcx
  HANDLE TargetHandle; // [rsp+40h] [rbp-468h] BYREF
  __int64 v36; // [rsp+48h] [rbp-460h] BYREF
  void **v37; // [rsp+50h] [rbp-458h]
  HANDLE hSourceHandle[2]; // [rsp+58h] [rbp-450h] BYREF
  unsigned int v39[2]; // [rsp+68h] [rbp-440h]
  _BYTE v40[480]; // [rsp+70h] [rbp-438h] BYREF
  WCHAR Buffer[264]; // [rsp+250h] [rbp-258h] BYREF

  v37 = a4;
  if ( !GlobalGetAtomNameW(a1, Buffer, 260) )
    return ResultFromKnownLastError();
  *(_OWORD *)hSourceHandle = 0;
  *(_QWORD *)v39 = 0;
  v36 = 0;
  v5 = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>(v6);
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v8 + 24));
    HIDWORD(v7[1].OwningThread) = 1;
    v7->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
    *(_QWORD *)&v7->LockCount = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>'};
    v7->OwningThread = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `IStreamCapabilities'};
    v7->LockSemaphore = &CMemStream::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v7->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CMemStream::`vftable'{for `Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
    *(_QWORD *)&v7->LockCount = &CMemStream::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>'};
    v7->OwningThread = &CMemStream::`vftable'{for `IStreamCapabilities'};
    v7->LockSemaphore = &CMemStream::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    v7[1].LockSemaphore = 0;
    LODWORD(v7[1].SpinCount) = 0;
    InitializeCriticalSection(v7 + 2);
    v5 = v7;
    v7[1].LockSemaphore = 0;
    v9 = (char *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
    v10 = v9;
    if ( v9 )
    {
      *(_DWORD *)v9 = 1;
      *((_QWORD *)v9 + 1) = 0;
      *((_QWORD *)v9 + 2) = 0;
      *((_DWORD *)v9 + 7) = 0;
      *((_QWORD *)v9 + 4) = 0;
      *((_QWORD *)v9 + 5) = 0;
      InitializeCriticalSection((LPCRITICAL_SECTION)(v9 + 48));
      *((_QWORD *)v10 + 11) = 0;
      *((_DWORD *)v10 + 6) = 2;
      _InterlockedIncrement((volatile signed __int32 *)v10);
      v7[1].LockSemaphore = v10;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10, 0xFFFFFFFF) == 1 )
      {
        if ( *((_QWORD *)v10 + 4) )
        {
          CMemStreamBuffer::WriteToReg((CMemStreamBuffer *)v10);
          RegCloseKey(*((HKEY *)v10 + 4));
        }
        v11 = (_BYTE *)*((_QWORD *)v10 + 1);
        if ( v11 && !*((_QWORD *)v10 + 11) )
        {
          if ( (v10[28] & 1) != 0 )
          {
            v34 = *((unsigned int *)v10 + 4);
            if ( *((_DWORD *)v10 + 4) )
            {
              do
              {
                *v11++ = 0;
                --v34;
              }
              while ( v34 );
            }
          }
          LocalFree(*((HLOCAL *)v10 + 1));
        }
        CoTaskMemFree(*((LPVOID *)v10 + 5));
        Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(v10 + 88);
        DeleteCriticalSection((LPCRITICAL_SECTION)(v10 + 48));
        operator delete(v10, (const struct std::nothrow_t *)0x60);
      }
      ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *, GUID *, __int64 *))v7->DebugInfo->Type)(
        v7,
        &GUID_0000000c_0000_0000_c000_000000000046,
        &v36);
    }
  }
  if ( v5 )
    ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v5->DebugInfo->ProcessLocksList.Flink)(v5);
  v12 = v36;
  if ( !v36 )
    return 2147500037LL;
  v13 = Buffer;
  Error = 0;
  memset_0(v40, 0, sizeof(v40));
  v15 = 0;
  v16 = 0;
  while ( 1 )
  {
    v17 = *v13;
    if ( !*v13 )
      break;
    if ( v17 == 96 )
      v18 = 0;
    else
      v18 = (v17 - 32) & 0x3F;
    v19 = v18 << v15;
    if ( !v15 )
      v19 = v18;
    v40[v16] |= v19;
    v15 += 6;
    if ( v15 >= 8 )
    {
      ++v16;
      v15 -= 8;
      if ( v15 )
      {
        v40[v16] = v18 >> (6 - v15);
      }
      else if ( v16 == 480 )
      {
        Error = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64, _QWORD))(*(_QWORD *)v12 + 32LL))(v12, v40, 480, 0);
        if ( Error >= 0 )
          memset_0(v40, 0, sizeof(v40));
        v16 = 0;
      }
    }
    ++v13;
    if ( Error < 0 )
      goto LABEL_35;
  }
  Error = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, _QWORD))(*(_QWORD *)v12 + 32LL))(v12, v40, v16, 0);
  (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v12 + 40LL))(v12, 0, 0, 0);
  if ( Error >= 0 )
  {
    Error = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v12 + 40LL))(v12, 0, 0, 0);
    if ( Error >= 0 )
    {
      LODWORD(TargetHandle) = 0;
      Error = (*(__int64 (__fastcall **)(__int64, HANDLE *, __int64, HANDLE *))(*(_QWORD *)v12 + 24LL))(
                v12,
                hSourceHandle,
                24,
                &TargetHandle);
      if ( Error >= 0 )
      {
        if ( (_DWORD)TargetHandle == 24 )
        {
          CurrentProcessId = GetCurrentProcessId();
          v22 = hSourceHandle[1];
          TargetHandle = 0;
          if ( hSourceHandle[1] )
          {
            v23 = v39[0];
            v26 = GetCurrentProcessId();
            v27 = v23 == v26 ? GetCurrentProcess() : OpenProcessLocal(v25, v24, v23);
            v30 = v27;
            if ( v27 )
            {
              if ( CurrentProcessId == v26 )
                CurrentProcess = GetCurrentProcess();
              else
                CurrentProcess = OpenProcessLocal(v29, v28, CurrentProcessId);
              v32 = CurrentProcess;
              if ( CurrentProcess )
              {
                if ( !DuplicateHandle(v30, v22, CurrentProcess, &TargetHandle, 0xF001Fu, 0, a3 | 2) )
                  TargetHandle = 0;
                if ( CurrentProcessId != v26 )
                  CloseHandle(v32);
              }
              if ( v23 != v26 )
                CloseHandle(v30);
            }
          }
          v33 = TargetHandle;
          *v37 = TargetHandle;
          if ( v33 )
            Error = 0;
          else
            Error = ResultFromKnownLastError();
        }
        else
        {
          Error = -2147467259;
        }
      }
    }
  }
LABEL_35:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180020f00  mov     [rsp+arg_8], rbx
0x180020f05  push    rbp
0x180020f06  push    rsi
0x180020f07  push    rdi
0x180020f08  push    r12
0x180020f0a  push    r13
0x180020f0c  push    r14
0x180020f0e  push    r15
0x180020f10  sub     rsp, 470h
0x180020f17  mov     rax, cs:__security_cookie
0x180020f1e  xor     rax, rsp
0x180020f21  mov     [rsp+4A8h+var_48], rax
0x180020f29  mov     [rsp+4A8h+var_458], r9
0x180020f2e  mov     r13d, r8d
0x180020f31  mov     r8d, 104h; nSize
0x180020f37  lea     rdx, [rsp+4A8h+Buffer]; lpBuffer
0x180020f3f  call    cs:__imp_GlobalGetAtomNameW
0x180020f45  test    eax, eax
0x180020f47  jz      loc_1800213EF
0x180020f4d  xorps   xmm0, xmm0
0x180020f50  xor     eax, eax
0x180020f52  movups  xmmword ptr [rsp+4A8h+hSourceHandle], xmm0
0x180020f57  mov     qword ptr [rsp+4A8h+var_440], rax
0x180020f5c  xor     r15d, r15d
0x180020f5f  mov     [rsp+4A8h+var_460], r15
0x180020f64  mov     ebx, r15d
0x180020f67  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020f6e  mov     ecx, 78h ; 'x'; unsigned __int64
0x180020f73  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180020f78  mov     rsi, rax
0x180020f7b  test    rax, rax
0x180020f7e  jz      loc_1800210FB
0x180020f84  mov     rcx, rax
0x180020f87  call    ??0?$ChainInterfaces@UIStream@@UISequentialStream@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>(void)
0x180020f8c  lea     rcx, [rcx+18h]; this
0x180020f90  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180020f95  mov     dword ptr [rsi+3Ch], 1
0x180020f9c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ChainInterfaces@UIStream@@UISequentialStream@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIAccessPrivateBuffer@@UIStreamCapabilities@@VFtmBase@23@@WRL@Microsoft@@6B?$ChainInterfaces@UIStream@@UISequentialStream@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x180020fa3  mov     [rsi], rax
0x180020fa6  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ChainInterfaces@UIStream@@UISequentialStream@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIAccessPrivateBuffer@@UIStreamCapabilities@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIAccessPrivateBuffer@@UIStreamCapabilities@@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>'}
0x180020fad  mov     [rsi+8], rax
0x180020fb1  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ChainInterfaces@UIStream@@UISequentialStream@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIAccessPrivateBuffer@@UIStreamCapabilities@@VFtmBase@23@@WRL@Microsoft@@6BIStreamCapabilities@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `IStreamCapabilities'}
0x180020fb8  mov     [rsi+10h], rax
0x180020fbc  lea     rax, ??_7CMemStream@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CMemStream::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180020fc3  mov     [rsi+18h], rax
0x180020fc7  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180020fce  test    rcx, rcx
0x180020fd1  jz      short loc_180020FE0
0x180020fd3  mov     rax, [rcx]
0x180020fd6  mov     rax, [rax+8]
0x180020fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020fdf  nop
0x180020fe0  lea     rax, ??_7CMemStream@@6B?$ChainInterfaces@UIStream@@UISequentialStream@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@WRL@Microsoft@@@; const CMemStream::`vftable'{for `Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x180020fe7  mov     [rsi], rax
0x180020fea  lea     rax, ??_7CMemStream@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIAccessPrivateBuffer@@UIStreamCapabilities@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CMemStream::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>'}
0x180020ff1  mov     [rsi+8], rax
0x180020ff5  lea     rax, ??_7CMemStream@@6BIStreamCapabilities@@@; const CMemStream::`vftable'{for `IStreamCapabilities'}
0x180020ffc  mov     [rsi+10h], rax
0x180021000  lea     rax, ??_7CMemStream@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CMemStream::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180021007  mov     [rsi+18h], rax
0x18002100b  mov     [rsi+40h], r15
0x18002100f  mov     [rsi+48h], r15d
0x180021013  lea     rcx, [rsi+50h]; lpCriticalSection
0x180021017  call    cs:__imp_InitializeCriticalSection
0x18002101d  nop
0x18002101e  mov     rbx, rsi
0x180021021  mov     [rsi+40h], r15
0x180021025  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002102c  mov     ecx, 60h ; '`'; unsigned __int64
0x180021031  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180021036  mov     rdi, rax
0x180021039  test    rax, rax
0x18002103c  jz      loc_1800210FB
0x180021042  mov     dword ptr [rax], 1
0x180021048  mov     [rax+8], r15
0x18002104c  mov     [rax+10h], r15
0x180021050  mov     [rax+1Ch], r15d
0x180021054  mov     [rax+20h], r15
0x180021058  mov     [rax+28h], r15
0x18002105c  lea     rcx, [rax+30h]; lpCriticalSection
0x180021060  call    cs:__imp_InitializeCriticalSection
0x180021066  mov     [rdi+58h], r15
0x18002106a  mov     dword ptr [rdi+18h], 2
0x180021071  lock inc dword ptr [rdi]
0x180021074  mov     [rsi+40h], rdi
0x180021078  mov     eax, 0FFFFFFFFh
0x18002107d  lock xadd [rdi], eax
0x180021081  cmp     eax, 1
0x180021084  jnz     short loc_1800210E0
0x180021086  cmp     qword ptr [rdi+20h], 0
0x18002108b  jnz     loc_1800213CC
0x180021091  mov     rax, [rdi+8]
0x180021095  test    rax, rax
0x180021098  jz      short loc_1800210B5
0x18002109a  cmp     qword ptr [rdi+58h], 0
0x18002109f  jnz     short loc_1800210B5
0x1800210a1  test    byte ptr [rdi+1Ch], 1
0x1800210a5  jnz     loc_18002138C
0x1800210ab  mov     rcx, [rdi+8]; hMem
0x1800210af  call    cs:__imp_LocalFree
0x1800210b5  mov     rcx, [rdi+28h]; pv
0x1800210b9  call    cs:__imp_CoTaskMemFree
0x1800210bf  lea     rcx, [rdi+58h]
0x1800210c3  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x1800210c8  lea     rcx, [rdi+30h]; lpCriticalSection
0x1800210cc  call    cs:__imp_DeleteCriticalSection
0x1800210d2  mov     edx, 60h ; '`'; struct std::nothrow_t *
0x1800210d7  mov     rcx, rdi; void *
0x1800210da  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800210df  nop
0x1800210e0  mov     rax, [rsi]
0x1800210e3  lea     r8, [rsp+4A8h+var_460]
0x1800210e8  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x1800210ef  mov     rcx, rbx
0x1800210f2  mov     rax, [rax]
0x1800210f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210fa  nop
0x1800210fb  test    rbx, rbx
0x1800210fe  jz      short loc_180021110
0x180021100  mov     rax, [rbx]
0x180021103  mov     rcx, rbx
0x180021106  mov     rax, [rax+10h]
0x18002110a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002110f  nop
0x180021110  mov     r12, [rsp+4A8h+var_460]
0x180021115  test    r12, r12
0x180021118  jz      loc_1800213F9
0x18002111e  lea     rdi, [rsp+4A8h+Buffer]
0x180021126  mov     esi, r15d
0x180021129  xor     edx, edx; Val
0x18002112b  mov     r8d, 1E0h; Size
0x180021131  lea     rcx, [rsp+4A8h+var_438]; void *
0x180021136  call    memset_0
0x18002113b  mov     ebx, r15d
0x18002113e  mov     r10d, r15d
0x180021141  movzx   eax, word ptr [rdi]
0x180021144  test    ax, ax
0x180021147  jz      loc_1800211EB
0x18002114d  cmp     ax, 60h ; '`'
0x180021151  jnz     short loc_1800211A4
0x180021153  xor     al, al
0x180021155  movsxd  rcx, r10d
0x180021158  lea     r9, [rsp+4A8h+var_438]
0x18002115d  add     r9, rcx
0x180021160  mov     ecx, ebx
0x180021162  movzx   edx, al
0x180021165  shl     dl, cl
0x180021167  movzx   r8d, dl
0x18002116b  movzx   ecx, al
0x18002116e  test    ebx, ebx
0x180021170  cmovz   r8d, ecx
0x180021174  or      [r9], r8b
0x180021177  add     ebx, 6
0x18002117a  cmp     ebx, 8
0x18002117d  jl      short loc_180021197
0x18002117f  inc     r10d
0x180021182  add     ebx, 0FFFFFFF8h
0x180021185  jz      short loc_1800211AA
0x180021187  mov     ecx, 6
0x18002118c  sub     cl, bl
0x18002118e  shr     al, cl
0x180021190  movsxd  rcx, r10d
0x180021193  mov     [rsp+rcx+4A8h+var_438], al
0x180021197  add     rdi, 2
0x18002119b  test    esi, esi
0x18002119d  jns     short loc_180021141
0x18002119f  jmp     loc_180021229
0x1800211a4  sub     al, 20h ; ' '
0x1800211a6  and     al, 3Fh
0x1800211a8  jmp     short loc_180021155
0x1800211aa  cmp     r10d, 1E0h
0x1800211b1  jnz     short loc_180021197
0x1800211b3  mov     rax, [r12]
0x1800211b7  xor     r9d, r9d
0x1800211ba  mov     r8d, r10d
0x1800211bd  lea     rdx, [rsp+4A8h+var_438]
0x1800211c2  mov     rcx, r12
0x1800211c5  mov     rax, [rax+20h]
0x1800211c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211ce  mov     esi, eax
0x1800211d0  test    eax, eax
0x1800211d2  js      short loc_1800211E6
0x1800211d4  xor     edx, edx; Val
0x1800211d6  mov     r8d, 1E0h; Size
0x1800211dc  lea     rcx, [rsp+4A8h+var_438]; void *
0x1800211e1  call    memset_0
0x1800211e6  mov     r10d, r15d
0x1800211e9  jmp     short loc_180021197
0x1800211eb  mov     rax, [r12]
0x1800211ef  xor     r9d, r9d
0x1800211f2  mov     r8d, r10d
0x1800211f5  lea     rdx, [rsp+4A8h+var_438]
0x1800211fa  mov     rcx, r12
0x1800211fd  mov     rax, [rax+20h]
0x180021201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021206  mov     esi, eax
0x180021208  mov     rax, [r12]
0x18002120c  xor     r9d, r9d
0x18002120f  xor     r8d, r8d
0x180021212  mov     rdx, cs:qword_1800ABF60
0x180021219  mov     rcx, r12
0x18002121c  mov     rax, [rax+28h]
0x180021220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021225  test    esi, esi
0x180021227  jns     short loc_180021266
0x180021229  mov     rax, [r12]
0x18002122d  mov     rcx, r12
0x180021230  mov     rax, [rax+10h]
0x180021234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021239  mov     eax, esi
0x18002123b  mov     rcx, [rsp+4A8h+var_48]
0x180021243  xor     rcx, rsp; StackCookie
0x180021246  call    __security_check_cookie
0x18002124b  mov     rbx, [rsp+4A8h+arg_8]
0x180021253  add     rsp, 470h
0x18002125a  pop     r15
0x18002125c  pop     r14
0x18002125e  pop     r13
0x180021260  pop     r12
0x180021262  pop     rdi
0x180021263  pop     rsi
0x180021264  pop     rbp
0x180021265  retn
0x180021266  mov     rax, [r12]
0x18002126a  xor     r9d, r9d
0x18002126d  xor     r8d, r8d
0x180021270  mov     rdx, cs:qword_1800ABF60
0x180021277  mov     rcx, r12
0x18002127a  mov     rax, [rax+28h]
0x18002127e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021283  mov     esi, eax
0x180021285  test    eax, eax
0x180021287  js      short loc_180021229
0x180021289  mov     dword ptr [rsp+4A8h+TargetHandle], r15d
0x18002128e  mov     rax, [r12]
0x180021292  lea     r9, [rsp+4A8h+TargetHandle]
0x180021297  mov     r8d, 18h
0x18002129d  lea     rdx, [rsp+4A8h+hSourceHandle]
0x1800212a2  mov     rcx, r12
0x1800212a5  mov     rax, [rax+18h]
0x1800212a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212ae  mov     esi, eax
0x1800212b0  test    eax, eax
0x1800212b2  js      loc_180021229
0x1800212b8  cmp     dword ptr [rsp+4A8h+TargetHandle], 18h
0x1800212bd  jnz     loc_1800213C2
0x1800212c3  call    cs:__imp_GetCurrentProcessId
0x1800212c9  mov     r14d, eax
0x1800212cc  mov     r15, [rsp+4A8h+hSourceHandle+8]
0x1800212d1  mov     [rsp+4A8h+TargetHandle], 0
0x1800212da  test    r15, r15
0x1800212dd  jz      short loc_18002135B
0x1800212df  mov     ebp, [rsp+4A8h+var_440]
0x1800212e3  call    cs:__imp_GetCurrentProcessId
0x1800212e9  mov     ebx, eax
0x1800212eb  cmp     ebp, eax
0x1800212ed  jnz     loc_18002137F
0x1800212f3  call    cs:__imp_GetCurrentProcess
0x1800212f9  mov     rdi, rax
0x1800212fc  test    rax, rax
0x1800212ff  jz      short loc_18002135B
0x180021301  cmp     r14d, ebx
0x180021304  jnz     loc_1800213AA
0x18002130a  call    cs:__imp_GetCurrentProcess
0x180021310  mov     rsi, rax
0x180021313  test    rax, rax
0x180021316  jz      short loc_18002134E
0x180021318  or      r13d, 2
0x18002131c  mov     [rsp+4A8h+dwOptions], r13d; dwOptions
0x180021321  mov     [rsp+4A8h+bInheritHandle], 0; bInheritHandle
0x180021329  mov     [rsp+4A8h+dwDesiredAccess], 0F001Fh; dwDesiredAccess
0x180021331  lea     r9, [rsp+4A8h+TargetHandle]; lpTargetHandle
0x180021336  mov     r8, rax; hTargetProcessHandle
0x180021339  mov     rdx, r15; hSourceHandle
0x18002133c  mov     rcx, rdi; hSourceProcessHandle
0x18002133f  call    cs:__imp_DuplicateHandle
0x180021345  test    eax, eax
0x180021347  jz      short loc_1800213B7
0x180021349  cmp     r14d, ebx
0x18002134c  jnz     short loc_180021374
0x18002134e  cmp     ebp, ebx
0x180021350  jz      short loc_18002135B
0x180021352  mov     rcx, rdi; hObject
0x180021355  call    cs:__imp_CloseHandle
0x18002135b  mov     rax, [rsp+4A8h+TargetHandle]
0x180021360  mov     rcx, [rsp+4A8h+var_458]
0x180021365  mov     [rcx], rax
0x180021368  test    rax, rax
0x18002136b  jz      short loc_1800213E3
0x18002136d  xor     esi, esi
0x18002136f  jmp     loc_180021229
0x180021374  mov     rcx, rsi; hObject
0x180021377  call    cs:__imp_CloseHandle
0x18002137d  jmp     short loc_18002134E
0x18002137f  mov     r8d, ebp; unsigned int
0x180021382  call    ?OpenProcessLocal@@YAPEAXKHK@Z; OpenProcessLocal(ulong,int,ulong)
0x180021387  jmp     loc_1800212F9
0x18002138c  mov     ecx, [rdi+10h]
0x18002138f  test    rcx, rcx
0x180021392  jz      loc_1800210AB
  ... truncated ...
```
