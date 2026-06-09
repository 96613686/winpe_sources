# TaskNamedValueCollectionImpl::Create(ushort *,ushort *,ITaskNamedValuePair * *)

- ea: `0x180039a00`
- end: `0x180039b77`
- name: `?Create@TaskNamedValueCollectionImpl@@UEAAJPEAG0PEAPEAUITaskNamedValuePair@@@Z`
- size: `375`
- prototype: `__int64 __fastcall(TaskNamedValueCollectionImpl *__hidden this, unsigned __int16 *, unsigned __int16 *, struct ITaskNamedValuePair **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001880`
- `0x180037cf0`
- `0x180039a00`
- `0x18003b360`
- `0x18004c3c0`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039a97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039a97`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039a41`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039a41`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall TaskNamedValueCollectionImpl::Create(
        TaskNamedValueCollectionImpl *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct ITaskNamedValuePair **a4)
{
  unsigned __int64 v8; // rdi
  int v9; // ebx
  int v10; // ebx
  struct ITaskNamedValuePair *v12; // rax
  struct ITaskNamedValuePair *v13; // [rsp+30h] [rbp-58h] BYREF
  struct ITaskNamedValuePair *v14; // [rsp+38h] [rbp-50h] BYREF
  unsigned __int64 v15[9]; // [rsp+40h] [rbp-48h] BYREF

  v13 = 0;
  v8 = ((unsigned __int64)this + 32) & -(__int64)(this != 0);
  if ( v8 )
    EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
  v15[0] = v8;
  v9 = CreateComInstance<TaskNamedValuePairImpl,ATL::CComPtr<ITaskNamedValuePair>>(&v13);
  if ( v9 < 0 )
    goto LABEL_15;
  v10 = ((__int64 (__fastcall *)(struct ITaskNamedValuePair *, unsigned __int16 *))v13->lpVtbl->put_Name)(v13, a2);
  if ( v10 >= 0 )
  {
    v9 = ((__int64 (__fastcall *)(struct ITaskNamedValuePair *, unsigned __int16 *))v13->lpVtbl->put_Value)(v13, a3);
    if ( v9 >= 0 )
    {
      v14 = v13;
      if ( v13 )
        ((void (__fastcall *)(struct ITaskNamedValuePair *))v13->lpVtbl->AddRef)(v13);
      std::vector<ATL::CAdapt<ATL::CComPtr<ITaskNamedValuePair>>>::push_back((char *)this + 8, &v14);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v14);
      if ( a4 )
      {
        v12 = v13;
        v13 = 0;
        *a4 = v12;
      }
    }
LABEL_15:
    ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>((__int64 *)v15);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v13);
    return (unsigned int)v9;
  }
  if ( v8 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
  if ( v13 )
    ((void (__fastcall *)(struct ITaskNamedValuePair *))v13->lpVtbl->Release)(v13);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180039a00  mov     rax, rsp
0x180039a03  push    rbx
0x180039a04  push    rsi
0x180039a05  push    rdi
0x180039a06  push    r12
0x180039a08  push    r14
0x180039a0a  push    r15
0x180039a0c  sub     rsp, 58h
0x180039a10  mov     r14, r9
0x180039a13  mov     r12, r8
0x180039a16  mov     r15, rdx
0x180039a19  mov     rsi, rcx
0x180039a1c  mov     dword ptr [rax+8], 0
0x180039a23  mov     qword ptr [rax-58h], 0
0x180039a2b  mov     rax, rcx
0x180039a2e  lea     r10, [rcx+20h]
0x180039a32  neg     rax
0x180039a35  sbb     rdi, rdi
0x180039a38  and     rdi, r10
0x180039a3b  jz      short loc_180039A4D
0x180039a3d  lea     rcx, [rdi+8]; lpCriticalSection
0x180039a41  call    cs:__imp_EnterCriticalSection
0x180039a48  nop     dword ptr [rax+rax+00h]
0x180039a4d  mov     [rsp+88h+var_48], rdi
0x180039a52  lea     rcx, [rsp+88h+var_58]
0x180039a57  call    ??$CreateComInstance@VTaskNamedValuePairImpl@@V?$CComPtr@UITaskNamedValuePair@@@ATL@@@@YAJAEAV?$CComPtr@UITaskNamedValuePair@@@ATL@@@Z; CreateComInstance<TaskNamedValuePairImpl,ATL::CComPtr<ITaskNamedValuePair>>(ATL::CComPtr<ITaskNamedValuePair> &)
0x180039a5c  mov     ebx, eax
0x180039a5e  mov     [rsp+88h+arg_0], eax
0x180039a65  test    eax, eax
0x180039a67  js      loc_180039B47
0x180039a6d  mov     rcx, [rsp+88h+var_58]
0x180039a72  mov     rax, [rcx]
0x180039a75  mov     rdx, r15
0x180039a78  mov     rax, [rax+40h]
0x180039a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039a81  mov     ebx, eax
0x180039a83  mov     [rsp+88h+arg_0], eax
0x180039a8a  test    eax, eax
0x180039a8c  jns     short loc_180039AC2
0x180039a8e  test    rdi, rdi
0x180039a91  jz      short loc_180039AA4
0x180039a93  lea     rcx, [rdi+8]; lpCriticalSection
0x180039a97  call    cs:__imp_LeaveCriticalSection
0x180039a9e  nop     dword ptr [rax+rax+00h]
0x180039aa3  nop
0x180039aa4  mov     rcx, [rsp+88h+var_58]
0x180039aa9  test    rcx, rcx
0x180039aac  jz      short loc_180039ABB
0x180039aae  mov     rax, [rcx]
0x180039ab1  mov     rax, [rax+10h]
0x180039ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039aba  nop
0x180039abb  mov     eax, ebx
0x180039abd  jmp     loc_180039B68
0x180039ac2  mov     rcx, [rsp+88h+var_58]
0x180039ac7  mov     rax, [rcx]
0x180039aca  mov     rdx, r12
0x180039acd  mov     rax, [rax+50h]
0x180039ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039ad6  mov     ebx, eax
0x180039ad8  mov     [rsp+88h+arg_0], eax
0x180039adf  test    eax, eax
0x180039ae1  jns     short loc_180039AFC
0x180039ae3  lea     rcx, [rsp+88h+var_48]
0x180039ae8  call    ??1?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(void)
0x180039aed  nop
0x180039aee  lea     rcx, [rsp+88h+var_58]
0x180039af3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180039af8  mov     eax, ebx
0x180039afa  jmp     short loc_180039B68
0x180039afc  mov     rcx, [rsp+88h+var_58]
0x180039b01  mov     [rsp+88h+var_50], rcx
0x180039b06  test    rcx, rcx
0x180039b09  jz      short loc_180039B18
0x180039b0b  mov     rax, [rcx]
0x180039b0e  mov     rax, [rax+8]
0x180039b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039b17  nop
0x180039b18  lea     rcx, [rsi+8]
0x180039b1c  lea     rdx, [rsp+88h+var_50]
0x180039b21  call    ?push_back@?$vector@V?$CAdapt@V?$CComPtr@UITaskNamedValuePair@@@ATL@@@ATL@@V?$allocator@V?$CAdapt@V?$CComPtr@UITaskNamedValuePair@@@ATL@@@ATL@@@std@@@std@@QEAAX$$QEAV?$CAdapt@V?$CComPtr@UITaskNamedValuePair@@@ATL@@@ATL@@@Z; std::vector<ATL::CAdapt<ATL::CComPtr<ITaskNamedValuePair>>>::push_back(ATL::CAdapt<ATL::CComPtr<ITaskNamedValuePair>> &&)
0x180039b26  nop
0x180039b27  lea     rcx, [rsp+88h+var_50]
0x180039b2c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180039b31  test    r14, r14
0x180039b34  jz      short loc_180039B47
0x180039b36  mov     rax, [rsp+88h+var_58]
0x180039b3b  mov     [rsp+88h+var_58], 0
0x180039b44  mov     [r14], rax
0x180039b47  lea     rcx, [rsp+88h+var_48]
0x180039b4c  call    ??1?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(void)
0x180039b51  nop
0x180039b52  lea     rcx, [rsp+88h+var_58]
0x180039b57  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180039b5c  nop
0x180039b5d  jmp     short loc_180039B66
0x180039b5f  mov     ebx, [rsp+88h+arg_0]
0x180039b66  mov     eax, ebx
0x180039b68  add     rsp, 58h
0x180039b6c  pop     r15
0x180039b6e  pop     r14
0x180039b70  pop     r12
0x180039b72  pop     rdi
0x180039b73  pop     rsi
0x180039b74  pop     rbx
0x180039b75  retn
```
