# SHCreateMemStream

- ea: `0x180020990`
- end: `0x180020cb4`
- name: `SHCreateMemStream`
- size: `804`
- prototype: `IStream *__stdcall(const BYTE *pInit, UINT cbInit)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000ddd4`
- `0x180020990`
- `0x18002140c`
- `0x1800214b8`
- `0x180036c3c`
- `0x18004d37c`
- `0x180066cfc`
- `0x180068d9c`
- `0x18009341c`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020b7e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020b7e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180020a6a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180020ab3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180020a6a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180020ab3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020b0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020c59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020ca9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020b0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020c59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020ca9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020ad1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020ad1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020b63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020b63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020c76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020c76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020b6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020b6d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
IStream *__stdcall SHCreateMemStream(const BYTE *pInit, UINT cbInit)
{
  size_t v2; // r14
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rax
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  __int64 v7; // rcx
  _QWORD *v8; // rbx
  char *v9; // rax
  char *v10; // rdi
  int v11; // r12d
  struct _RTL_CRITICAL_SECTION *v12; // r15
  char *v13; // rbp
  _BYTE *v14; // rax
  int v16; // eax
  unsigned int v17; // r13d
  int v18; // edx
  unsigned int v19; // eax
  unsigned int v20; // ecx
  __int64 v21; // rcx
  unsigned int v23; // [rsp+70h] [rbp+18h]
  IStream *v24; // [rsp+78h] [rbp+20h] BYREF

  v2 = cbInit;
  v24 = 0;
  v4 = 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( v5 )
  {
    Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>(v5);
    v8 = (_QWORD *)(v7 + 24);
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v7 + 24));
    HIDWORD(v6[1].OwningThread) = 1;
    v6->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
    *(_QWORD *)&v6->LockCount = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>'};
    v6->OwningThread = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `IStreamCapabilities'};
    *v8 = &CMemStream::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v6->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CMemStream::`vftable'{for `Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
    *(_QWORD *)&v6->LockCount = &CMemStream::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>'};
    v6->OwningThread = &CMemStream::`vftable'{for `IStreamCapabilities'};
    *v8 = &CMemStream::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    v6[1].LockSemaphore = 0;
    LODWORD(v6[1].SpinCount) = 0;
    InitializeCriticalSection(v6 + 2);
    v4 = v6;
    v6[1].LockSemaphore = 0;
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
      v11 = 0;
      if ( pInit && (_DWORD)v2 )
      {
        v12 = (struct _RTL_CRITICAL_SECTION *)(v10 + 48);
        EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 48));
        v13 = v10 + 88;
        if ( *((_QWORD *)v10 + 11) )
        {
          LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 48));
          v11 = -2147287035;
          goto LABEL_13;
        }
        if ( (unsigned int)v2 > *((_DWORD *)v10 + 4) )
        {
          v16 = -1;
          if ( (int)v2 + 4096 >= (unsigned int)v2 )
            v16 = v2 + 4096;
          v17 = v2;
          if ( (int)v2 + 4096 >= (unsigned int)v2 )
            v17 = v16;
          v18 = 2 * v2;
          if ( 2 * v2 > 0xFFFFFFFF )
            v18 = -1;
          v19 = v2;
          if ( 2 * v2 <= 0xFFFFFFFF )
            v19 = v18;
          v20 = v17;
          if ( v19 > v17 )
            v20 = v19;
          v23 = v20;
          v11 = CMemStreamBuffer::GrowBuffer((CMemStreamBuffer *)v10, v20);
          if ( v11 < 0 )
          {
            if ( v23 <= v17 || (v11 = CMemStreamBuffer::GrowBuffer((CMemStreamBuffer *)v10, v17), v11 < 0) )
            {
              LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 48));
              goto LABEL_13;
            }
          }
        }
        memcpy_0(*((void **)v10 + 1), pInit, v2);
        if ( (unsigned int)v2 > *((_DWORD *)v10 + 5) )
          *((_DWORD *)v10 + 5) = v2;
        LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 48));
        v11 = 0;
      }
      *((_DWORD *)v10 + 6) = 2;
      _InterlockedIncrement((volatile signed __int32 *)v10);
      v6[1].LockSemaphore = v10;
      v13 = v10 + 88;
      v12 = (struct _RTL_CRITICAL_SECTION *)(v10 + 48);
LABEL_13:
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10, 0xFFFFFFFF) == 1 )
      {
        if ( *((_QWORD *)v10 + 4) )
        {
          CMemStreamBuffer::WriteToReg((CMemStreamBuffer *)v10);
          RegCloseKey(*((HKEY *)v10 + 4));
        }
        v14 = (_BYTE *)*((_QWORD *)v10 + 1);
        if ( v14 )
        {
          v13 = v10 + 88;
          if ( !*((_QWORD *)v10 + 11) )
          {
            if ( (v10[28] & 1) != 0 )
            {
              v21 = *((unsigned int *)v10 + 4);
              if ( *((_DWORD *)v10 + 4) )
              {
                do
                {
                  *v14++ = 0;
                  --v21;
                }
                while ( v21 );
              }
            }
            LocalFree(*((HLOCAL *)v10 + 1));
          }
        }
        CoTaskMemFree(*((LPVOID *)v10 + 5));
        Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(v13);
        DeleteCriticalSection(v12);
        operator delete(v10, (const struct std::nothrow_t *)0x60);
      }
      if ( v11 >= 0 )
        ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *, GUID *, IStream **))v6->DebugInfo->Type)(
          v6,
          &GUID_0000000c_0000_0000_c000_000000000046,
          &v24);
    }
  }
  if ( v4 )
    ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v4->DebugInfo->ProcessLocksList.Flink)(v4);
  return v24;
}

```

## disassembly

```asm
0x180020990  mov     [rsp+arg_8], rbx
0x180020995  mov     [rsp+Src], rcx
0x18002099a  push    rbp
0x18002099b  push    rsi
0x18002099c  push    rdi
0x18002099d  push    r12
0x18002099f  push    r13
0x1800209a1  push    r14
0x1800209a3  push    r15
0x1800209a5  sub     rsp, 20h
0x1800209a9  mov     r14d, edx
0x1800209ac  mov     rbp, rcx
0x1800209af  xor     r13d, r13d
0x1800209b2  mov     [rsp+58h+arg_18], r13
0x1800209b7  mov     ebx, r13d
0x1800209ba  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800209c1  lea     ecx, [r13+78h]; unsigned __int64
0x1800209c5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800209ca  mov     rsi, rax
0x1800209cd  test    rax, rax
0x1800209d0  jz      loc_180020BB1
0x1800209d6  mov     rcx, rax
0x1800209d9  call    ??0?$ChainInterfaces@UIStream@@UISequentialStream@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>(void)
0x1800209de  lea     rbx, [rcx+18h]
0x1800209e2  mov     rcx, rbx; this
0x1800209e5  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800209ea  mov     dword ptr [rsi+3Ch], 1
0x1800209f1  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ChainInterfaces@UIStream@@UISequentialStream@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIAccessPrivateBuffer@@UIStreamCapabilities@@VFtmBase@23@@WRL@Microsoft@@6B?$ChainInterfaces@UIStream@@UISequentialStream@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x1800209f8  mov     [rsi], rax
0x1800209fb  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ChainInterfaces@UIStream@@UISequentialStream@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIAccessPrivateBuffer@@UIStreamCapabilities@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIAccessPrivateBuffer@@UIStreamCapabilities@@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>'}
0x180020a02  mov     [rsi+8], rax
0x180020a06  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ChainInterfaces@UIStream@@UISequentialStream@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIAccessPrivateBuffer@@UIStreamCapabilities@@VFtmBase@23@@WRL@Microsoft@@6BIStreamCapabilities@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `IStreamCapabilities'}
0x180020a0d  mov     [rsi+10h], rax
0x180020a11  lea     rax, ??_7CMemStream@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CMemStream::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180020a18  mov     [rbx], rax
0x180020a1b  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180020a22  test    rcx, rcx
0x180020a25  jz      short loc_180020A34
0x180020a27  mov     rax, [rcx]
0x180020a2a  mov     rax, [rax+8]
0x180020a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a33  nop
0x180020a34  lea     rax, ??_7CMemStream@@6B?$ChainInterfaces@UIStream@@UISequentialStream@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@WRL@Microsoft@@@; const CMemStream::`vftable'{for `Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x180020a3b  mov     [rsi], rax
0x180020a3e  lea     rax, ??_7CMemStream@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIAccessPrivateBuffer@@UIStreamCapabilities@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CMemStream::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>'}
0x180020a45  mov     [rsi+8], rax
0x180020a49  lea     rax, ??_7CMemStream@@6BIStreamCapabilities@@@; const CMemStream::`vftable'{for `IStreamCapabilities'}
0x180020a50  mov     [rsi+10h], rax
0x180020a54  lea     rax, ??_7CMemStream@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CMemStream::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180020a5b  mov     [rbx], rax
0x180020a5e  mov     [rsi+40h], r13
0x180020a62  mov     [rsi+48h], r13d
0x180020a66  lea     rcx, [rsi+50h]; lpCriticalSection
0x180020a6a  call    cs:__imp_InitializeCriticalSection
0x180020a70  nop
0x180020a71  mov     rbx, rsi
0x180020a74  mov     [rsi+40h], r13
0x180020a78  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020a7f  mov     ecx, 60h ; '`'; unsigned __int64
0x180020a84  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180020a89  mov     rdi, rax
0x180020a8c  test    rax, rax
0x180020a8f  jz      loc_180020BB1
0x180020a95  mov     dword ptr [rax], 1
0x180020a9b  mov     [rax+8], r13
0x180020a9f  mov     [rax+10h], r13
0x180020aa3  mov     [rax+1Ch], r13d
0x180020aa7  mov     [rax+20h], r13
0x180020aab  mov     [rax+28h], r13
0x180020aaf  lea     rcx, [rax+30h]; lpCriticalSection
0x180020ab3  call    cs:__imp_InitializeCriticalSection
0x180020ab9  mov     [rdi+58h], r13
0x180020abd  mov     r12d, r13d
0x180020ac0  test    rbp, rbp
0x180020ac3  jz      short loc_180020B16
0x180020ac5  test    r14d, r14d
0x180020ac8  jz      short loc_180020B16
0x180020aca  lea     r15, [rdi+30h]
0x180020ace  mov     rcx, r15; lpCriticalSection
0x180020ad1  call    cs:__imp_EnterCriticalSection
0x180020ad7  lea     rbp, [rdi+58h]
0x180020adb  cmp     [rbp+0], r13
0x180020adf  jnz     loc_180020C56
0x180020ae5  cmp     r14d, [rdi+10h]
0x180020ae9  ja      loc_180020BE0
0x180020aef  mov     r8, r14; Size
0x180020af2  mov     rdx, [rsp+58h+Src]; Src
0x180020af7  mov     rcx, [rdi+8]; void *
0x180020afb  call    memcpy_0
0x180020b00  cmp     r14d, [rdi+14h]
0x180020b04  jbe     short loc_180020B0A
0x180020b06  mov     [rdi+14h], r14d
0x180020b0a  mov     rcx, r15; lpCriticalSection
0x180020b0d  call    cs:__imp_LeaveCriticalSection
0x180020b13  mov     r12d, r13d
0x180020b16  mov     dword ptr [rdi+18h], 2
0x180020b1d  lock inc dword ptr [rdi]
0x180020b20  mov     [rsi+40h], rdi
0x180020b24  lea     rbp, [rdi+58h]
0x180020b28  lea     r15, [rdi+30h]
0x180020b2c  or      eax, 0FFFFFFFFh
0x180020b2f  lock xadd [rdi], eax
0x180020b33  cmp     eax, 1
0x180020b36  jnz     short loc_180020B91
0x180020b38  cmp     [rdi+20h], r13
0x180020b3c  jnz     loc_180020C6A
0x180020b42  mov     rax, [rdi+8]
0x180020b46  test    rax, rax
0x180020b49  jz      short loc_180020B69
0x180020b4b  lea     rbp, [rdi+58h]
0x180020b4f  cmp     [rbp+0], r13
0x180020b53  jnz     short loc_180020B69
0x180020b55  test    byte ptr [rdi+1Ch], 1
0x180020b59  jnz     loc_180020C34
0x180020b5f  mov     rcx, [rdi+8]; hMem
0x180020b63  call    cs:__imp_LocalFree
0x180020b69  mov     rcx, [rdi+28h]; pv
0x180020b6d  call    cs:__imp_CoTaskMemFree
0x180020b73  mov     rcx, rbp
0x180020b76  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180020b7b  mov     rcx, r15; lpCriticalSection
0x180020b7e  call    cs:__imp_DeleteCriticalSection
0x180020b84  mov     edx, 60h ; '`'; struct std::nothrow_t *
0x180020b89  mov     rcx, rdi; void *
0x180020b8c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180020b91  test    r12d, r12d
0x180020b94  js      short loc_180020BB1
0x180020b96  mov     rax, [rsi]
0x180020b99  lea     r8, [rsp+58h+arg_18]
0x180020b9e  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x180020ba5  mov     rcx, rbx
0x180020ba8  mov     rax, [rax]
0x180020bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bb0  nop
0x180020bb1  test    rbx, rbx
0x180020bb4  jz      short loc_180020BC6
0x180020bb6  mov     rax, [rbx]
0x180020bb9  mov     rcx, rbx
0x180020bbc  mov     rax, [rax+10h]
0x180020bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bc5  nop
0x180020bc6  mov     rax, [rsp+58h+arg_18]
0x180020bcb  mov     rbx, [rsp+58h+arg_8]
0x180020bd0  add     rsp, 20h
0x180020bd4  pop     r15
0x180020bd6  pop     r14
0x180020bd8  pop     r13
0x180020bda  pop     r12
0x180020bdc  pop     rdi
0x180020bdd  pop     rsi
0x180020bde  pop     rbp
0x180020bdf  retn
0x180020be0  lea     ecx, [r14+1000h]
0x180020be7  mov     r8d, 0FFFFFFFFh
0x180020bed  mov     eax, r8d
0x180020bf0  cmp     ecx, r14d
0x180020bf3  cmovnb  eax, ecx
0x180020bf6  mov     r13d, r14d
0x180020bf9  cmovnb  r13d, eax
0x180020bfd  lea     rcx, [r14+r14]
0x180020c01  cmp     rcx, r8
0x180020c04  mov     edx, ecx
0x180020c06  ja      short loc_180020C51
0x180020c08  mov     eax, r14d
0x180020c0b  cmovbe  eax, edx
0x180020c0e  mov     ecx, r13d
0x180020c11  cmp     eax, r13d
0x180020c14  cmova   ecx, eax
0x180020c17  mov     [rsp+58h+arg_10], ecx
0x180020c1b  mov     edx, ecx; unsigned int
0x180020c1d  mov     rcx, rdi; this
0x180020c20  call    ?GrowBuffer@CMemStreamBuffer@@QEAAJK@Z; CMemStreamBuffer::GrowBuffer(ulong)
0x180020c25  mov     r12d, eax
0x180020c28  test    eax, eax
0x180020c2a  js      short loc_180020C81
0x180020c2c  xor     r13d, r13d
0x180020c2f  jmp     loc_180020AEF
0x180020c34  mov     ecx, [rdi+10h]
0x180020c37  test    rcx, rcx
0x180020c3a  jz      loc_180020B5F
0x180020c40  mov     [rax], r13b
0x180020c43  inc     rax
0x180020c46  sub     rcx, 1
0x180020c4a  jnz     short loc_180020C40
0x180020c4c  jmp     loc_180020B5F
0x180020c51  mov     edx, r8d
0x180020c54  jmp     short loc_180020C08
0x180020c56  mov     rcx, r15; lpCriticalSection
0x180020c59  call    cs:__imp_LeaveCriticalSection
0x180020c5f  mov     r12d, 80030005h
0x180020c65  jmp     loc_180020B2C
0x180020c6a  mov     rcx, rdi; this
0x180020c6d  call    ?WriteToReg@CMemStreamBuffer@@AEAAHXZ; CMemStreamBuffer::WriteToReg(void)
0x180020c72  mov     rcx, [rdi+20h]; hKey
0x180020c76  call    cs:__imp_RegCloseKey
0x180020c7c  jmp     loc_180020B42
0x180020c81  cmp     [rsp+58h+arg_10], r13d
0x180020c86  jbe     short loc_180020CA3
0x180020c88  mov     edx, r13d; unsigned int
0x180020c8b  mov     rcx, rdi; this
0x180020c8e  call    ?GrowBuffer@CMemStreamBuffer@@QEAAJK@Z; CMemStreamBuffer::GrowBuffer(ulong)
0x180020c93  mov     r12d, eax
0x180020c96  xor     r13d, r13d
0x180020c99  test    eax, eax
0x180020c9b  jns     loc_180020AEF
0x180020ca1  jmp     short loc_180020CA6
0x180020ca3  xor     r13d, r13d
0x180020ca6  mov     rcx, r15; lpCriticalSection
0x180020ca9  call    cs:__imp_LeaveCriticalSection
0x180020caf  jmp     loc_180020B2C
```
