# VmExdiServer::~VmExdiServer(void)

- ea: `0x14019918c`
- end: `0x14019927f`
- name: `??1VmExdiServer@@UEAA@XZ`
- size: `243`
- prototype: `void __fastcall(VmExdiServer *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1401992d0`

## callees

- `0x1400328a0`
- `0x140032f00`
- `0x1401990ec`
- `0x140199120`
- `0x140199288`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14019922d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140199240`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140199250`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140199260`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14019922d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140199240`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140199250`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140199260`

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
0x14019918c  mov     [rsp+arg_0], rbx
0x140199191  push    rdi
0x140199192  sub     rsp, 20h
0x140199196  mov     rdi, rcx
0x140199199  lea     rax, ??_7VmExdiServer@@6BVmComObject@Vml@@@; const VmExdiServer::`vftable'{for `Vml::VmComObject'}
0x1401991a0  mov     [rcx], rax
0x1401991a3  lea     rax, ??_7VmExdiServer@@6BIeXdiServer@@@; const VmExdiServer::`vftable'{for `IeXdiServer'}
0x1401991aa  mov     [rcx+18h], rax
0x1401991ae  lea     rax, ??_7VmExdiServer@@6BIeXdiX86ExContext@@@; const VmExdiServer::`vftable'{for `IeXdiX86ExContext'}
0x1401991b5  mov     [rcx+20h], rax
0x1401991b9  lea     rax, ??_7VmExdiServer@@6BIeXdiX86_64Context@@@; const VmExdiServer::`vftable'{for `IeXdiX86_64Context'}
0x1401991c0  mov     [rcx+28h], rax
0x1401991c4  mov     rax, [rcx+8]
0x1401991c8  movsxd  rdx, dword ptr [rax+4]
0x1401991cc  lea     rax, ??_7VmExdiServer@@6BVmSharableObject@Vml@@@; const VmExdiServer::`vftable'{for `Vml::VmSharableObject'}
0x1401991d3  mov     [rdx+rcx+8], rax
0x1401991d8  mov     rax, [rcx+8]
0x1401991dc  movsxd  rcx, dword ptr [rax+4]
0x1401991e0  lea     edx, [rcx-75F0h]
0x1401991e6  mov     [rcx+rdi+4], edx
0x1401991ea  lea     rcx, [rdi+75E0h]
0x1401991f1  call    ??1?$VmReferencePtr@UIVirtualMachineGuestState@@VVmWeakReferenceTraits@Vml@@@Vml@@QEAA@XZ; Vml::VmReferencePtr<IVirtualMachineGuestState,Vml::VmWeakReferenceTraits>::~VmReferencePtr<IVirtualMachineGuestState,Vml::VmWeakReferenceTraits>(void)
0x1401991f6  lea     rcx, [rdi+120h]; this
0x1401991fd  call    ??_DVmExdiDebugHelper@@QEAAXXZ; VmExdiDebugHelper::`vbase destructor'(void)
0x140199202  lea     rcx, [rdi+108h]
0x140199209  call    ??1?$_Tree@V?$_Tmap_traits@_JV?$com_ptr_t@UIeXdiCodeBreakpoint@@Uerr_exception_policy@wil@@@wil@@U?$less@_J@std@@V?$allocator@U?$pair@$$CB_JV?$com_ptr_t@UIeXdiCodeBreakpoint@@Uerr_exception_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<__int64,wil::com_ptr_t<IeXdiCodeBreakpoint,wil::err_exception_policy>,std::less<__int64>,std::allocator<std::pair<__int64 const,wil::com_ptr_t<IeXdiCodeBreakpoint,wil::err_exception_policy>>>,0>>::~_Tree<std::_Tmap_traits<__int64,wil::com_ptr_t<IeXdiCodeBreakpoint,wil::err_exception_policy>,std::less<__int64>,std::allocator<std::pair<__int64 const,wil::com_ptr_t<IeXdiCodeBreakpoint,wil::err_exception_policy>>>,0>>(void)
0x14019920e  lea     rcx, [rdi+0F8h]
0x140199215  call    ??1?$CCookiedLinkList@UIeXdiClientNotifyMemChg@@K@@QEAA@XZ; CCookiedLinkList<IeXdiClientNotifyMemChg,ulong>::~CCookiedLinkList<IeXdiClientNotifyMemChg,ulong>(void)
0x14019921a  lea     rcx, [rdi+0E8h]
0x140199221  call    ??1?$CCookiedLinkList@UIeXdiClientNotifyMemChg@@K@@QEAA@XZ; CCookiedLinkList<IeXdiClientNotifyMemChg,ulong>::~CCookiedLinkList<IeXdiClientNotifyMemChg,ulong>(void)
0x140199226  lea     rcx, [rdi+0C0h]; lpCriticalSection
0x14019922d  call    cs:__imp_DeleteCriticalSection
0x140199234  nop     dword ptr [rax+rax+00h]
0x140199239  lea     rcx, [rdi+98h]; lpCriticalSection
0x140199240  call    cs:__imp_DeleteCriticalSection
0x140199247  nop     dword ptr [rax+rax+00h]
0x14019924c  lea     rcx, [rdi+70h]; lpCriticalSection
0x140199250  call    cs:__imp_DeleteCriticalSection
0x140199257  nop     dword ptr [rax+rax+00h]
0x14019925c  lea     rcx, [rdi+48h]; lpCriticalSection
0x140199260  call    cs:__imp_DeleteCriticalSection
0x140199267  nop     dword ptr [rax+rax+00h]
0x14019926c  lea     rcx, [rdi+18h]; this
0x140199270  mov     rbx, [rsp+28h+arg_0]
0x140199275  add     rsp, 20h
0x140199279  pop     rdi
0x14019927a  jmp     ?CleanUpFromRunSelf@WorkerModule@@QEAAXXZ; WorkerModule::CleanUpFromRunSelf(void)
```
