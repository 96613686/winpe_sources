# TaskNamedValueCollectionImpl::Create(ushort *,ushort *,ITaskNamedValuePair * *)

- ea: `0x180036a30`
- end: `0x180036b9b`
- name: `?Create@TaskNamedValueCollectionImpl@@UEAAJPEAG0PEAPEAUITaskNamedValuePair@@@Z`
- size: `363`
- prototype: `__int64 __fastcall(TaskNamedValueCollectionImpl *__hidden this, unsigned __int16 *, unsigned __int16 *, struct ITaskNamedValuePair **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800017f0`
- `0x1800351ec`
- `0x180036a30`
- `0x180038988`
- `0x1800488b0`
- `0x180054010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036ac1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036ac1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036a71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036a71`

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
0x180036a30  mov     rax, rsp
0x180036a33  push    rbx
0x180036a34  push    rsi
0x180036a35  push    rdi
0x180036a36  push    r12
0x180036a38  push    r14
0x180036a3a  push    r15
0x180036a3c  sub     rsp, 58h
0x180036a40  mov     r14, r9
0x180036a43  mov     r12, r8
0x180036a46  mov     r15, rdx
0x180036a49  mov     rsi, rcx
0x180036a4c  mov     dword ptr [rax+8], 0
0x180036a53  mov     qword ptr [rax-58h], 0
0x180036a5b  mov     rax, rcx
0x180036a5e  lea     r10, [rcx+20h]
0x180036a62  neg     rax
0x180036a65  sbb     rdi, rdi
0x180036a68  and     rdi, r10
0x180036a6b  jz      short loc_180036A77
0x180036a6d  lea     rcx, [rdi+8]; lpCriticalSection
0x180036a71  call    cs:__imp_EnterCriticalSection
0x180036a77  mov     [rsp+88h+var_48], rdi
0x180036a7c  lea     rcx, [rsp+88h+var_58]
0x180036a81  call    ??$CreateComInstance@VTaskNamedValuePairImpl@@V?$CComPtr@UITaskNamedValuePair@@@ATL@@@@YAJAEAV?$CComPtr@UITaskNamedValuePair@@@ATL@@@Z; CreateComInstance<TaskNamedValuePairImpl,ATL::CComPtr<ITaskNamedValuePair>>(ATL::CComPtr<ITaskNamedValuePair> &)
0x180036a86  mov     ebx, eax
0x180036a88  mov     [rsp+88h+arg_0], eax
0x180036a8f  test    eax, eax
0x180036a91  js      loc_180036B6B
0x180036a97  mov     rcx, [rsp+88h+var_58]
0x180036a9c  mov     rax, [rcx]
0x180036a9f  mov     rdx, r15
0x180036aa2  mov     rax, [rax+40h]
0x180036aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036aab  mov     ebx, eax
0x180036aad  mov     [rsp+88h+arg_0], eax
0x180036ab4  test    eax, eax
0x180036ab6  jns     short loc_180036AE6
0x180036ab8  test    rdi, rdi
0x180036abb  jz      short loc_180036AC8
0x180036abd  lea     rcx, [rdi+8]; lpCriticalSection
0x180036ac1  call    cs:__imp_LeaveCriticalSection
0x180036ac7  nop
0x180036ac8  mov     rcx, [rsp+88h+var_58]
0x180036acd  test    rcx, rcx
0x180036ad0  jz      short loc_180036ADF
0x180036ad2  mov     rax, [rcx]
0x180036ad5  mov     rax, [rax+10h]
0x180036ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ade  nop
0x180036adf  mov     eax, ebx
0x180036ae1  jmp     loc_180036B8C
0x180036ae6  mov     rcx, [rsp+88h+var_58]
0x180036aeb  mov     rax, [rcx]
0x180036aee  mov     rdx, r12
0x180036af1  mov     rax, [rax+50h]
0x180036af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036afa  mov     ebx, eax
0x180036afc  mov     [rsp+88h+arg_0], eax
0x180036b03  test    eax, eax
0x180036b05  jns     short loc_180036B20
0x180036b07  lea     rcx, [rsp+88h+var_48]
0x180036b0c  call    ??1?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(void)
0x180036b11  nop
0x180036b12  lea     rcx, [rsp+88h+var_58]
0x180036b17  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180036b1c  mov     eax, ebx
0x180036b1e  jmp     short loc_180036B8C
0x180036b20  mov     rcx, [rsp+88h+var_58]
0x180036b25  mov     [rsp+88h+var_50], rcx
0x180036b2a  test    rcx, rcx
0x180036b2d  jz      short loc_180036B3C
0x180036b2f  mov     rax, [rcx]
0x180036b32  mov     rax, [rax+8]
0x180036b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b3b  nop
0x180036b3c  lea     rcx, [rsi+8]
0x180036b40  lea     rdx, [rsp+88h+var_50]
0x180036b45  call    ?push_back@?$vector@V?$CAdapt@V?$CComPtr@UITaskNamedValuePair@@@ATL@@@ATL@@V?$allocator@V?$CAdapt@V?$CComPtr@UITaskNamedValuePair@@@ATL@@@ATL@@@std@@@std@@QEAAX$$QEAV?$CAdapt@V?$CComPtr@UITaskNamedValuePair@@@ATL@@@ATL@@@Z; std::vector<ATL::CAdapt<ATL::CComPtr<ITaskNamedValuePair>>>::push_back(ATL::CAdapt<ATL::CComPtr<ITaskNamedValuePair>> &&)
0x180036b4a  nop
0x180036b4b  lea     rcx, [rsp+88h+var_50]
0x180036b50  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180036b55  test    r14, r14
0x180036b58  jz      short loc_180036B6B
0x180036b5a  mov     rax, [rsp+88h+var_58]
0x180036b5f  mov     [rsp+88h+var_58], 0
0x180036b68  mov     [r14], rax
0x180036b6b  lea     rcx, [rsp+88h+var_48]
0x180036b70  call    ??1?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(void)
0x180036b75  nop
0x180036b76  lea     rcx, [rsp+88h+var_58]
0x180036b7b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180036b80  nop
0x180036b81  jmp     short loc_180036B8A
0x180036b83  mov     ebx, [rsp+88h+arg_0]
0x180036b8a  mov     eax, ebx
0x180036b8c  add     rsp, 58h
0x180036b90  pop     r15
0x180036b92  pop     r14
0x180036b94  pop     r12
0x180036b96  pop     rdi
0x180036b97  pop     rsi
0x180036b98  pop     rbx
0x180036b99  retn
```
