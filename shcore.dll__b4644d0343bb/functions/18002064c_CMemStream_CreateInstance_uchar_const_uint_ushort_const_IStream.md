# CMemStream::CreateInstance(uchar const *,uint,ushort const *,IStream * *)

- ea: `0x18002064c`
- end: `0x180020989`
- name: `?CreateInstance@CMemStream@@SAJPEBEIPEBGPEAPEAUIStream@@@Z`
- size: `829`
- prototype: `__int64 __fastcall(const unsigned __int8 *, unsigned int, const unsigned __int16 *, struct IStream **)`
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800081c8`
- `0x180010adc`
- `0x18001fe5c`
- `0x18004b74c`

## callees

- `0x18000ddd4`
- `0x18002064c`
- `0x18002140c`
- `0x1800214b8`
- `0x180036c3c`
- `0x18004d37c`
- `0x180066cfc`
- `0x180068d9c`
- `0x18009341c`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800207ef`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800207ef`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002072b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180020771`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002072b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180020771`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020899`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020923`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020971`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020899`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020923`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020971`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002085e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002085e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800207d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800207d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002093f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002093f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800207de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800207de`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMemStream::CreateInstance(
        const unsigned __int8 *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        struct IStream **a4)
{
  size_t v4; // r14
  struct _RTL_CRITICAL_SECTION *v6; // rax
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  __int64 v8; // rcx
  _QWORD *v9; // rdi
  char *v10; // rax
  char *v11; // rdi
  int v12; // esi
  char *v13; // rbp
  struct _RTL_CRITICAL_SECTION *v14; // r15
  _BYTE *v15; // rax
  __int64 v17; // rcx
  int v18; // eax
  unsigned int v19; // r12d
  int v20; // edx
  unsigned int v21; // eax
  unsigned int v22; // ecx
  unsigned int v24; // [rsp+70h] [rbp+18h]

  v4 = a2;
  *a4 = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( !v6 )
  {
    v7 = 0;
LABEL_46:
    v12 = -2147024882;
    goto LABEL_17;
  }
  Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>(v6);
  v9 = (_QWORD *)(v8 + 24);
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v8 + 24));
  HIDWORD(v7[1].OwningThread) = 1;
  v7->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
  *(_QWORD *)&v7->LockCount = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>'};
  v7->OwningThread = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `IStreamCapabilities'};
  *v9 = &CMemStream::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  v7->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CMemStream::`vftable'{for `Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
  *(_QWORD *)&v7->LockCount = &CMemStream::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>'};
  v7->OwningThread = &CMemStream::`vftable'{for `IStreamCapabilities'};
  *v9 = &CMemStream::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v7[1].LockSemaphore = 0;
  LODWORD(v7[1].SpinCount) = 0;
  InitializeCriticalSection(v7 + 2);
  v7[1].LockSemaphore = 0;
  v10 = (char *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( !v10 )
    goto LABEL_46;
  *(_DWORD *)v10 = 1;
  *((_QWORD *)v10 + 1) = 0;
  *((_QWORD *)v10 + 2) = 0;
  *((_DWORD *)v10 + 7) = 0;
  *((_QWORD *)v10 + 4) = 0;
  *((_QWORD *)v10 + 5) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)(v10 + 48));
  *((_QWORD *)v11 + 11) = 0;
  v12 = 0;
  if ( a1 && (_DWORD)v4 )
  {
    v14 = (struct _RTL_CRITICAL_SECTION *)(v11 + 48);
    EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 48));
    v13 = v11 + 88;
    if ( *((_QWORD *)v11 + 11) )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)(v11 + 48));
      v12 = -2147287035;
      goto LABEL_7;
    }
    if ( (unsigned int)v4 > *((_DWORD *)v11 + 4) )
    {
      v18 = -1;
      if ( (int)v4 + 4096 >= (unsigned int)v4 )
        v18 = v4 + 4096;
      v19 = v4;
      if ( (int)v4 + 4096 >= (unsigned int)v4 )
        v19 = v18;
      v20 = 2 * v4;
      if ( 2 * v4 > 0xFFFFFFFF )
        v20 = -1;
      v21 = v4;
      if ( 2 * v4 <= 0xFFFFFFFF )
        v21 = v20;
      v22 = v19;
      if ( v21 > v19 )
        v22 = v21;
      v24 = v22;
      v12 = CMemStreamBuffer::GrowBuffer((CMemStreamBuffer *)v11, v22);
      if ( v12 < 0 )
      {
        if ( v24 <= v19 || (v12 = CMemStreamBuffer::GrowBuffer((CMemStreamBuffer *)v11, v19), v12 < 0) )
        {
          LeaveCriticalSection((LPCRITICAL_SECTION)(v11 + 48));
          goto LABEL_7;
        }
      }
    }
    memcpy_0(*((void **)v11 + 1), a1, v4);
    if ( (unsigned int)v4 > *((_DWORD *)v11 + 5) )
      *((_DWORD *)v11 + 5) = v4;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v11 + 48));
    v12 = 0;
  }
  *((_DWORD *)v11 + 6) = 2;
  _InterlockedIncrement((volatile signed __int32 *)v11);
  v7[1].LockSemaphore = v11;
  v13 = v11 + 88;
  v14 = (struct _RTL_CRITICAL_SECTION *)(v11 + 48);
LABEL_7:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11, 0xFFFFFFFF) == 1 )
  {
    if ( *((_QWORD *)v11 + 4) )
    {
      CMemStreamBuffer::WriteToReg((CMemStreamBuffer *)v11);
      RegCloseKey(*((HKEY *)v11 + 4));
    }
    v15 = (_BYTE *)*((_QWORD *)v11 + 1);
    if ( v15 )
    {
      v13 = v11 + 88;
      if ( !*((_QWORD *)v11 + 11) )
      {
        if ( (v11[28] & 1) != 0 )
        {
          v17 = *((unsigned int *)v11 + 4);
          if ( *((_DWORD *)v11 + 4) )
          {
            do
            {
              *v15++ = 0;
              --v17;
            }
            while ( v17 );
          }
        }
        LocalFree(*((HLOCAL *)v11 + 1));
      }
    }
    CoTaskMemFree(*((LPVOID *)v11 + 5));
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(v13);
    DeleteCriticalSection(v14);
    operator delete(v11, (const struct std::nothrow_t *)0x60);
  }
  if ( v12 >= 0 )
    v12 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *, GUID *, struct IStream **))v7->DebugInfo->Type)(
            v7,
            &GUID_0000000c_0000_0000_c000_000000000046,
            a4);
LABEL_17:
  if ( v7 )
    ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v7->DebugInfo->ProcessLocksList.Flink)(v7);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18002064c  mov     rax, rsp
0x18002064f  mov     [rax+10h], rbx
0x180020653  mov     [rax+20h], r9
0x180020657  mov     [rax+18h], r8
0x18002065b  mov     [rax+8], rcx
0x18002065f  push    rbp
0x180020660  push    rsi
0x180020661  push    rdi
0x180020662  push    r12
0x180020664  push    r13
0x180020666  push    r14
0x180020668  push    r15
0x18002066a  sub     rsp, 20h
0x18002066e  mov     r14d, edx
0x180020671  mov     rbp, rcx
0x180020674  xor     r12d, r12d
0x180020677  mov     [r9], r12
0x18002067a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020681  lea     ecx, [r12+78h]; unsigned __int64
0x180020686  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002068b  mov     rbx, rax
0x18002068e  test    rax, rax
0x180020691  jz      loc_18002097C
0x180020697  mov     rcx, rax
0x18002069a  call    ??0?$ChainInterfaces@UIStream@@UISequentialStream@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>(void)
0x18002069f  lea     rdi, [rcx+18h]
0x1800206a3  mov     rcx, rdi; this
0x1800206a6  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800206ab  mov     dword ptr [rbx+3Ch], 1
0x1800206b2  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ChainInterfaces@UIStream@@UISequentialStream@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIAccessPrivateBuffer@@UIStreamCapabilities@@VFtmBase@23@@WRL@Microsoft@@6B?$ChainInterfaces@UIStream@@UISequentialStream@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x1800206b9  mov     [rbx], rax
0x1800206bc  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ChainInterfaces@UIStream@@UISequentialStream@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIAccessPrivateBuffer@@UIStreamCapabilities@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIAccessPrivateBuffer@@UIStreamCapabilities@@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>'}
0x1800206c3  mov     [rbx+8], rax
0x1800206c7  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ChainInterfaces@UIStream@@UISequentialStream@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIAccessPrivateBuffer@@UIStreamCapabilities@@VFtmBase@23@@WRL@Microsoft@@6BIStreamCapabilities@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `IStreamCapabilities'}
0x1800206ce  mov     [rbx+10h], rax
0x1800206d2  lea     rax, ??_7CMemStream@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CMemStream::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800206d9  mov     [rdi], rax
0x1800206dc  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800206e3  test    rcx, rcx
0x1800206e6  jz      short loc_1800206F5
0x1800206e8  mov     rax, [rcx]
0x1800206eb  mov     rax, [rax+8]
0x1800206ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800206f4  nop
0x1800206f5  lea     rax, ??_7CMemStream@@6B?$ChainInterfaces@UIStream@@UISequentialStream@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@WRL@Microsoft@@@; const CMemStream::`vftable'{for `Microsoft::WRL::ChainInterfaces<IStream,ISequentialStream,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x1800206fc  mov     [rbx], rax
0x1800206ff  lea     rax, ??_7CMemStream@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIAccessPrivateBuffer@@UIStreamCapabilities@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CMemStream::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAccessPrivateBuffer,IStreamCapabilities,Microsoft::WRL::FtmBase>'}
0x180020706  mov     [rbx+8], rax
0x18002070a  lea     rax, ??_7CMemStream@@6BIStreamCapabilities@@@; const CMemStream::`vftable'{for `IStreamCapabilities'}
0x180020711  mov     [rbx+10h], rax
0x180020715  lea     rax, ??_7CMemStream@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CMemStream::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18002071c  mov     [rdi], rax
0x18002071f  mov     [rbx+40h], r12
0x180020723  mov     [rbx+48h], r12d
0x180020727  lea     rcx, [rbx+50h]; lpCriticalSection
0x18002072b  call    cs:__imp_InitializeCriticalSection
0x180020731  nop
0x180020732  mov     [rbx+40h], r12
0x180020736  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002073d  mov     ecx, 60h ; '`'; unsigned __int64
0x180020742  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180020747  mov     rdi, rax
0x18002074a  test    rax, rax
0x18002074d  jz      loc_18002097F
0x180020753  mov     dword ptr [rax], 1
0x180020759  mov     [rax+8], r12
0x18002075d  mov     [rax+10h], r12
0x180020761  mov     [rax+1Ch], r12d
0x180020765  mov     [rax+20h], r12
0x180020769  mov     [rax+28h], r12
0x18002076d  lea     rcx, [rax+30h]; lpCriticalSection
0x180020771  call    cs:__imp_InitializeCriticalSection
0x180020777  mov     [rdi+58h], r12
0x18002077b  mov     esi, r12d
0x18002077e  test    rbp, rbp
0x180020781  jnz     loc_18002084E
0x180020787  mov     dword ptr [rdi+18h], 2
0x18002078e  lock inc dword ptr [rdi]
0x180020791  mov     [rbx+40h], rdi
0x180020795  lea     rbp, [rdi+58h]
0x180020799  lea     r15, [rdi+30h]
0x18002079d  or      eax, 0FFFFFFFFh
0x1800207a0  lock xadd [rdi], eax
0x1800207a4  cmp     eax, 1
0x1800207a7  jnz     short loc_180020802
0x1800207a9  cmp     [rdi+20h], r12
0x1800207ad  jnz     loc_180020933
0x1800207b3  mov     rax, [rdi+8]
0x1800207b7  test    rax, rax
0x1800207ba  jz      short loc_1800207DA
0x1800207bc  lea     rbp, [rdi+58h]
0x1800207c0  cmp     [rbp+0], r12
0x1800207c4  jnz     short loc_1800207DA
0x1800207c6  test    byte ptr [rdi+1Ch], 1
0x1800207ca  jnz     loc_1800208A7
0x1800207d0  mov     rcx, [rdi+8]; hMem
0x1800207d4  call    cs:__imp_LocalFree
0x1800207da  mov     rcx, [rdi+28h]; pv
0x1800207de  call    cs:__imp_CoTaskMemFree
0x1800207e4  mov     rcx, rbp
0x1800207e7  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x1800207ec  mov     rcx, r15; lpCriticalSection
0x1800207ef  call    cs:__imp_DeleteCriticalSection
0x1800207f5  mov     edx, 60h ; '`'; struct std::nothrow_t *
0x1800207fa  mov     rcx, rdi; void *
0x1800207fd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180020802  test    esi, esi
0x180020804  js      short loc_180020822
0x180020806  mov     rax, [rbx]
0x180020809  mov     r8, [rsp+58h+arg_18]
0x18002080e  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x180020815  mov     rcx, rbx
0x180020818  mov     rax, [rax]
0x18002081b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020820  mov     esi, eax
0x180020822  test    rbx, rbx
0x180020825  jz      short loc_180020837
0x180020827  mov     rcx, [rbx]
0x18002082a  mov     rax, [rcx+10h]
0x18002082e  mov     rcx, rbx
0x180020831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020836  nop
0x180020837  mov     eax, esi
0x180020839  mov     rbx, [rsp+58h+arg_8]
0x18002083e  add     rsp, 20h
0x180020842  pop     r15
0x180020844  pop     r14
0x180020846  pop     r13
0x180020848  pop     r12
0x18002084a  pop     rdi
0x18002084b  pop     rsi
0x18002084c  pop     rbp
0x18002084d  retn
0x18002084e  test    r14d, r14d
0x180020851  jz      loc_180020787
0x180020857  lea     r15, [rdi+30h]
0x18002085b  mov     rcx, r15; lpCriticalSection
0x18002085e  call    cs:__imp_EnterCriticalSection
0x180020864  lea     rbp, [rdi+58h]
0x180020868  cmp     [rbp+0], r12
0x18002086c  jnz     loc_180020920
0x180020872  mov     r13, r14
0x180020875  cmp     r14d, [rdi+10h]
0x180020879  ja      short loc_1800208C4
0x18002087b  mov     r8, r13; Size
0x18002087e  mov     rdx, [rsp+58h+Src]; Src
0x180020883  mov     rcx, [rdi+8]; void *
0x180020887  call    memcpy_0
0x18002088c  cmp     r14d, [rdi+14h]
0x180020890  jbe     short loc_180020896
0x180020892  mov     [rdi+14h], r14d
0x180020896  mov     rcx, r15; lpCriticalSection
0x180020899  call    cs:__imp_LeaveCriticalSection
0x18002089f  mov     esi, r12d
0x1800208a2  jmp     loc_180020787
0x1800208a7  mov     ecx, [rdi+10h]
0x1800208aa  test    rcx, rcx
0x1800208ad  jz      loc_1800207D0
0x1800208b3  mov     [rax], r12b
0x1800208b6  inc     rax
0x1800208b9  sub     rcx, 1
0x1800208bd  jnz     short loc_1800208B3
0x1800208bf  jmp     loc_1800207D0
0x1800208c4  lea     ecx, [r14+1000h]
0x1800208cb  mov     r8d, 0FFFFFFFFh
0x1800208d1  mov     eax, r8d
0x1800208d4  cmp     ecx, r14d
0x1800208d7  cmovnb  eax, ecx
0x1800208da  mov     r12d, r14d
0x1800208dd  cmovnb  r12d, eax
0x1800208e1  lea     rcx, ds:0[r14*2]
0x1800208e9  cmp     rcx, r8
0x1800208ec  mov     edx, ecx
0x1800208ee  ja      short loc_18002091B
0x1800208f0  mov     eax, r14d
0x1800208f3  cmovbe  eax, edx
0x1800208f6  mov     ecx, r12d
0x1800208f9  cmp     eax, r12d
0x1800208fc  cmova   ecx, eax
0x1800208ff  mov     [rsp+58h+arg_10], ecx
0x180020903  mov     edx, ecx; unsigned int
0x180020905  mov     rcx, rdi; this
0x180020908  call    ?GrowBuffer@CMemStreamBuffer@@QEAAJK@Z; CMemStreamBuffer::GrowBuffer(ulong)
0x18002090d  mov     esi, eax
0x18002090f  test    eax, eax
0x180020911  js      short loc_18002094A
0x180020913  xor     r12d, r12d
0x180020916  jmp     loc_18002087B
0x18002091b  mov     edx, r8d
0x18002091e  jmp     short loc_1800208F0
0x180020920  mov     rcx, r15; lpCriticalSection
0x180020923  call    cs:__imp_LeaveCriticalSection
0x180020929  mov     esi, 80030005h
0x18002092e  jmp     loc_18002079D
0x180020933  mov     rcx, rdi; this
0x180020936  call    ?WriteToReg@CMemStreamBuffer@@AEAAHXZ; CMemStreamBuffer::WriteToReg(void)
0x18002093b  mov     rcx, [rdi+20h]; hKey
0x18002093f  call    cs:__imp_RegCloseKey
0x180020945  jmp     loc_1800207B3
0x18002094a  cmp     [rsp+58h+arg_10], r12d
0x18002094f  jbe     short loc_18002096B
0x180020951  mov     edx, r12d; unsigned int
0x180020954  mov     rcx, rdi; this
0x180020957  call    ?GrowBuffer@CMemStreamBuffer@@QEAAJK@Z; CMemStreamBuffer::GrowBuffer(ulong)
0x18002095c  mov     esi, eax
0x18002095e  xor     r12d, r12d
0x180020961  test    eax, eax
0x180020963  jns     loc_18002087B
0x180020969  jmp     short loc_18002096E
0x18002096b  xor     r12d, r12d
0x18002096e  mov     rcx, r15; lpCriticalSection
0x180020971  call    cs:__imp_LeaveCriticalSection
0x180020977  jmp     loc_18002079D
0x18002097c  mov     rbx, r12
0x18002097f  mov     esi, 8007000Eh
0x180020984  jmp     loc_180020822
```
