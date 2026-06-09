# VmExdiServer::~VmExdiServer(void)

- ea: `0x140188130`
- end: `0x140188223`
- name: `??1VmExdiServer@@UEAA@XZ`
- size: `243`
- prototype: `void __fastcall(VmExdiServer *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140188280`

## callees

- `0x140031f60`
- `0x1400325c0`
- `0x140188090`
- `0x1401880c4`
- `0x14018822c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1401881d1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1401881e4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1401881f4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140188204`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1401881d1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1401881e4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1401881f4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140188204`

## pseudocode

```c
void __fastcall VmExdiServer::~VmExdiServer(VmExdiServer *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &VmExdiServer::`vftable'{for `Vml::VmComObject'};
  *((_QWORD *)this + 3) = &VmExdiServer::`vftable'{for `IeXdiServer'};
  *((_QWORD *)this + 4) = &VmExdiServer::`vftable'{for `IeXdiX86ExContext'};
  *((_QWORD *)this + 5) = &VmExdiServer::`vftable'{for `IeXdiX86_64Context'};
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8) = &VmExdiServer::`vftable'{for `Vml::VmSharableObject'};
  v2 = *(int *)(*((_QWORD *)this + 1) + 4LL);
  *(_DWORD *)((char *)this + v2 + 4) = v2 - 30192;
  Vml::VmReferencePtr<IVirtualMachineGuestState,Vml::VmWeakReferenceTraits>::~VmReferencePtr<IVirtualMachineGuestState,Vml::VmWeakReferenceTraits>((char *)this + 30176);
  VmExdiDebugHelper::`vbase destructor'((VmExdiServer *)((char *)this + 288));
  std::_Tree<std::_Tmap_traits<__int64,wil::com_ptr_t<IeXdiCodeBreakpoint,wil::err_exception_policy>,std::less<__int64>,std::allocator<std::pair<__int64 const,wil::com_ptr_t<IeXdiCodeBreakpoint,wil::err_exception_policy>>>,0>>::~_Tree<std::_Tmap_traits<__int64,wil::com_ptr_t<IeXdiCodeBreakpoint,wil::err_exception_policy>,std::less<__int64>,std::allocator<std::pair<__int64 const,wil::com_ptr_t<IeXdiCodeBreakpoint,wil::err_exception_policy>>>,0>>((char *)this + 264);
  CCookiedLinkList<IeXdiClientNotifyMemChg,unsigned long>::~CCookiedLinkList<IeXdiClientNotifyMemChg,unsigned long>((char *)this + 248);
  CCookiedLinkList<IeXdiClientNotifyMemChg,unsigned long>::~CCookiedLinkList<IeXdiClientNotifyMemChg,unsigned long>((char *)this + 232);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  WorkerModule::CleanUpFromRunSelf((VmExdiServer *)((char *)this + 24));
}

```

## disassembly

```asm
0x140188130  mov     [rsp+arg_0], rbx
0x140188135  push    rdi
0x140188136  sub     rsp, 20h
0x14018813a  mov     rdi, rcx
0x14018813d  lea     rax, ??_7VmExdiServer@@6BVmComObject@Vml@@@; const VmExdiServer::`vftable'{for `Vml::VmComObject'}
0x140188144  mov     [rcx], rax
0x140188147  lea     rax, ??_7VmExdiServer@@6BIeXdiServer@@@; const VmExdiServer::`vftable'{for `IeXdiServer'}
0x14018814e  mov     [rcx+18h], rax
0x140188152  lea     rax, ??_7VmExdiServer@@6BIeXdiX86ExContext@@@; const VmExdiServer::`vftable'{for `IeXdiX86ExContext'}
0x140188159  mov     [rcx+20h], rax
0x14018815d  lea     rax, ??_7VmExdiServer@@6BIeXdiX86_64Context@@@; const VmExdiServer::`vftable'{for `IeXdiX86_64Context'}
0x140188164  mov     [rcx+28h], rax
0x140188168  mov     rax, [rcx+8]
0x14018816c  movsxd  rdx, dword ptr [rax+4]
0x140188170  lea     rax, ??_7VmExdiServer@@6BVmSharableObject@Vml@@@; const VmExdiServer::`vftable'{for `Vml::VmSharableObject'}
0x140188177  mov     [rdx+rcx+8], rax
0x14018817c  mov     rax, [rcx+8]
0x140188180  movsxd  rcx, dword ptr [rax+4]
0x140188184  lea     edx, [rcx-75F0h]
0x14018818a  mov     [rcx+rdi+4], edx
0x14018818e  lea     rcx, [rdi+75E0h]
0x140188195  call    ??1?$VmReferencePtr@UIVirtualMachineGuestState@@VVmWeakReferenceTraits@Vml@@@Vml@@QEAA@XZ; Vml::VmReferencePtr<IVirtualMachineGuestState,Vml::VmWeakReferenceTraits>::~VmReferencePtr<IVirtualMachineGuestState,Vml::VmWeakReferenceTraits>(void)
0x14018819a  lea     rcx, [rdi+120h]; this
0x1401881a1  call    ??_DVmExdiDebugHelper@@QEAAXXZ; VmExdiDebugHelper::`vbase destructor'(void)
0x1401881a6  lea     rcx, [rdi+108h]
0x1401881ad  call    ??1?$_Tree@V?$_Tmap_traits@_JV?$com_ptr_t@UIeXdiCodeBreakpoint@@Uerr_exception_policy@wil@@@wil@@U?$less@_J@std@@V?$allocator@U?$pair@$$CB_JV?$com_ptr_t@UIeXdiCodeBreakpoint@@Uerr_exception_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<__int64,wil::com_ptr_t<IeXdiCodeBreakpoint,wil::err_exception_policy>,std::less<__int64>,std::allocator<std::pair<__int64 const,wil::com_ptr_t<IeXdiCodeBreakpoint,wil::err_exception_policy>>>,0>>::~_Tree<std::_Tmap_traits<__int64,wil::com_ptr_t<IeXdiCodeBreakpoint,wil::err_exception_policy>,std::less<__int64>,std::allocator<std::pair<__int64 const,wil::com_ptr_t<IeXdiCodeBreakpoint,wil::err_exception_policy>>>,0>>(void)
0x1401881b2  lea     rcx, [rdi+0F8h]
0x1401881b9  call    ??1?$CCookiedLinkList@UIeXdiClientNotifyMemChg@@K@@QEAA@XZ; CCookiedLinkList<IeXdiClientNotifyMemChg,ulong>::~CCookiedLinkList<IeXdiClientNotifyMemChg,ulong>(void)
0x1401881be  lea     rcx, [rdi+0E8h]
0x1401881c5  call    ??1?$CCookiedLinkList@UIeXdiClientNotifyMemChg@@K@@QEAA@XZ; CCookiedLinkList<IeXdiClientNotifyMemChg,ulong>::~CCookiedLinkList<IeXdiClientNotifyMemChg,ulong>(void)
0x1401881ca  lea     rcx, [rdi+0C0h]; lpCriticalSection
0x1401881d1  call    cs:__imp_DeleteCriticalSection
0x1401881d8  nop     dword ptr [rax+rax+00h]
0x1401881dd  lea     rcx, [rdi+98h]; lpCriticalSection
0x1401881e4  call    cs:__imp_DeleteCriticalSection
0x1401881eb  nop     dword ptr [rax+rax+00h]
0x1401881f0  lea     rcx, [rdi+70h]; lpCriticalSection
0x1401881f4  call    cs:__imp_DeleteCriticalSection
0x1401881fb  nop     dword ptr [rax+rax+00h]
0x140188200  lea     rcx, [rdi+48h]; lpCriticalSection
0x140188204  call    cs:__imp_DeleteCriticalSection
0x14018820b  nop     dword ptr [rax+rax+00h]
0x140188210  lea     rcx, [rdi+18h]; this
0x140188214  mov     rbx, [rsp+28h+arg_0]
0x140188219  add     rsp, 20h
0x14018821d  pop     rdi
0x14018821e  jmp     ?CleanUpFromRunSelf@WorkerModule@@QEAAXXZ; WorkerModule::CleanUpFromRunSelf(void)
```
