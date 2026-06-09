# WorkThreadManager::s_ClearOrGetNextTask(WorkThreadManager::CThread *)

- ea: `0x18002688c`
- end: `0x180026bd0`
- name: `?s_ClearOrGetNextTask@WorkThreadManager@@CAXPEAVCThread@1@@Z`
- size: `836`
- prototype: `void __fastcall(struct WorkThreadManager::CThread *)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002b504`

## callees

- `0x18002688c`
- `0x180026bd8`
- `0x180026c64`
- `0x18002ae44`
- `0x18002b384`
- `0x18002b9e4`
- `0x18002ba48`
- `0x18002beb8`
- `0x18002bf88`
- `0x18002bfbc`
- `0x18002c064`
- `0x18002c098`
- `0x18002e1a0`
- `0x18002ecb8`
- `0x1800362c8`
- `0x18003631c`
- `0x180036340`
- `0x1800376cc`
- `0x1800378b4`
- `0x180057c64`
- `0x180073cb0`
- `0x18007416c`
- `0x1800743cc`
- `0x180074c64`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800269bf`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800269bf`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800268f0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002696e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180026ab3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800268f0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002696e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180026ab3`
- `KERNEL32!GetCurrentThread` at `0x180026a8e`
- `KERNEL32!GetCurrentThread` at `0x180026a8e`
- `KERNEL32!SetThreadPriority` at `0x180026a9a`
- `KERNEL32!SetThreadPriority` at `0x180026a9a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WorkThreadManager::s_ClearOrGetNextTask(struct WorkThreadManager::CThread *a1)
{
  WorkThreadManager::TaskList *v2; // rcx
  WorkThreadManager::TaskData *v3; // rbx
  WorkThreadManager::TaskData *v4; // rsi
  __int64 v5; // rax
  char v6; // r15
  DWORD TickCount_0; // ebx
  __int64 v8; // r10
  int v9; // ebx
  void *v10; // rdx
  unsigned int v11; // edx
  __int64 v12; // rcx
  unsigned int v13; // edx
  HANDLE CurrentThread; // rax
  WorkThreadManager::TaskData *v15; // r14
  __int64 v16; // rax
  unsigned int v17; // edx
  WorkThreadManager::TaskData *v18; // rcx
  WorkThreadManager::TaskData *v19; // rsi
  DWORD v20; // eax
  unsigned int v21; // edx
  __int64 v22; // rax
  __int64 v23; // [rsp+20h] [rbp-89h] BYREF
  int v24; // [rsp+28h] [rbp-81h]
  __int64 v25; // [rsp+30h] [rbp-79h]
  char v26; // [rsp+38h] [rbp-71h]
  __int16 v27; // [rsp+39h] [rbp-70h]
  char v28; // [rsp+3Bh] [rbp-6Eh]
  __int64 v29; // [rsp+3Ch] [rbp-6Dh]
  __int128 v30; // [rsp+48h] [rbp-61h] BYREF
  _QWORD v31[2]; // [rsp+58h] [rbp-51h] BYREF
  _DWORD v32[2]; // [rsp+68h] [rbp-41h] BYREF
  char v33; // [rsp+70h] [rbp-39h]
  __int64 v34; // [rsp+80h] [rbp-29h] BYREF
  int v35; // [rsp+88h] [rbp-21h]
  __int64 v36; // [rsp+90h] [rbp-19h]
  char v37; // [rsp+98h] [rbp-11h]
  __int16 v38; // [rsp+99h] [rbp-10h]
  char v39; // [rsp+9Bh] [rbp-Eh]
  __int64 v40; // [rsp+9Ch] [rbp-Dh]
  __int64 v41; // [rsp+A8h] [rbp-1h] BYREF
  __int64 v42; // [rsp+B0h] [rbp+7h] BYREF
  _QWORD v43[9]; // [rsp+B8h] [rbp+Fh] BYREF
  WorkThreadManager::TaskData *v44; // [rsp+110h] [rbp+67h] BYREF
  WorkThreadManager::TaskData *v45; // [rsp+118h] [rbp+6Fh] BYREF
  WorkThreadManager::TaskData *v46; // [rsp+120h] [rbp+77h] BYREF
  RTL_SRWLOCK *v47; // [rsp+128h] [rbp+7Fh] BYREF

  v34 = 1;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43[1] = v43;
  v43[0] = v43;
  AcquireSRWLockExclusive(&WorkThreadManager::s_rwLock);
  WorkThreadManager::s_anyThreadMadeProgress = 1;
  v2 = (struct WorkThreadManager::CThread *)((char *)a1 + 24);
  if ( *(WorkThreadManager::TaskList **)v2 == v2 )
  {
    v3 = 0;
    v44 = 0;
LABEL_4:
    v5 = WorkThreadManager::CThread::ClearThreadTask(a1, &v23);
    WorkThreadManager::TaskData::operator=(&v34, v5);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)&v30 + 8);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v30);
    *((_BYTE *)a1 + 41) = 1;
    v6 = 1;
    goto LABEL_11;
  }
  v4 = WorkThreadManager::TaskList::RawRemoveHead(v2);
  v3 = v4;
  v44 = v4;
  if ( !v4 )
    goto LABEL_4;
  v6 = 0;
  TickCount_0 = GetTickCount_0();
  AcquireSRWLockExclusive((PSRWLOCK)a1 + 28);
  WorkThreadManager::TaskData::TaskData(&v23, (char *)a1 + 144);
  WorkThreadManager::TaskData::operator=(v8, v4);
  *((_DWORD *)a1 + 54) = TickCount_0;
  *((_BYTE *)a1 + 89) = 0;
  v9 = *((_DWORD *)a1 + 20);
  if ( GetCurrentThreadId_0() != v9 && v9 )
    wil::details::SetEvent(*((wil::details **)a1 + 13), v10);
  if ( a1 != (struct WorkThreadManager::CThread *)-224LL )
    ReleaseSRWLockExclusive((PSRWLOCK)a1 + 28);
  WorkThreadManager::TaskData::operator=(&v34, &v23);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)&v30 + 8);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v30);
  v3 = 0;
  v44 = 0;
  WorkThreadManager::TaskData::`scalar deleting destructor'(v4, v11);
LABEL_11:
  wil::last_error_context::last_error_context((wil::last_error_context *)&v45);
  ReleaseSRWLockExclusive_0(&WorkThreadManager::s_rwLock);
  wil::last_error_context::~last_error_context((wil::last_error_context *)&v45);
  WorkThreadManager::CThread::AdjustThreadPriority(v12, v32, HIDWORD(v34));
  v23 = 1;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31[1] = v31;
  v31[0] = v31;
  WorkThreadManager::TaskData::operator=(&v34, &v23);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)&v30 + 8);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v30);
  if ( v33 && v32[0] )
  {
    CurrentThread = GetCurrentThread();
    SetThreadPriority(CurrentThread, v32[1]);
  }
  if ( v6 )
  {
    v15 = 0;
    v45 = 0;
    AcquireSRWLockExclusive(&WorkThreadManager::s_rwLock);
    v47 = &WorkThreadManager::s_rwLock;
    *((_BYTE *)a1 + 41) = 0;
    v16 = WorkThreadManager::TaskList::PopFront(&WorkThreadManager::s_taskFloodingList, &v46);
    wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>::operator=(
      &v44,
      v16);
    v18 = v46;
    v46 = 0;
    if ( v18 )
      WorkThreadManager::TaskData::`scalar deleting destructor'(v18, v17);
    v19 = v44;
    if ( v44
      && *((_DWORD *)v44 + 2) == *((_DWORD *)a1 + 38)
      && (unsigned __int8)WorkThreadManager::CThread::Eligible(a1, *(unsigned int *)v44, *((unsigned int *)v44 + 1)) )
    {
      v20 = GetTickCount_0();
      WorkThreadManager::CThread::SetThreadTask(a1, &v23, v19, v20);
      WorkThreadManager::TaskData::~TaskData((WorkThreadManager::TaskData *)&v23);
      v3 = 0;
      if ( v19 )
        WorkThreadManager::TaskData::`scalar deleting destructor'(v19, v21);
    }
    else
    {
      wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>::operator=(
        &v45,
        &v44);
      v3 = v44;
      v15 = v45;
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
      &v47,
      0);
    if ( v15 )
    {
      v22 = wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>(
              &v44,
              &v45);
      WorkThreadManager::s_AttachAndRecoverTask(v22);
      v15 = v45;
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v47);
    if ( v15 )
      WorkThreadManager::TaskData::`scalar deleting destructor'(v15, v13);
  }
  if ( v3 )
    WorkThreadManager::TaskData::`scalar deleting destructor'(v3, v13);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v41);
}

```

## disassembly

```asm
0x18002688c  push    rbp
0x18002688e  push    rbx
0x18002688f  push    rsi
0x180026890  push    rdi
0x180026891  push    r12
0x180026893  push    r14
0x180026895  push    r15
0x180026897  lea     rbp, [rsp-27h]
0x18002689c  sub     rsp, 0D0h
0x1800268a3  mov     rdi, rcx
0x1800268a6  mov     [rbp+57h+var_80], 1
0x1800268ae  xor     r12d, r12d
0x1800268b1  mov     [rbp+57h+var_78], r12d
0x1800268b5  mov     [rbp+57h+var_70], r12
0x1800268b9  mov     [rbp+57h+var_68], r12b
0x1800268bd  xor     eax, eax
0x1800268bf  mov     [rbp+57h+var_67], ax
0x1800268c3  mov     [rbp+57h+var_65], al
0x1800268c6  mov     [rbp+57h+var_64], rax
0x1800268ca  mov     [rbp+57h+var_58], r12
0x1800268ce  mov     [rbp+57h+var_50], r12
0x1800268d2  xorps   xmm0, xmm0
0x1800268d5  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x1800268d9  lea     rax, [rbp+57h+var_48]
0x1800268dd  mov     [rbp+57h+var_48+8], rax
0x1800268e1  lea     rax, [rbp+57h+var_48]
0x1800268e5  mov     [rbp+57h+var_48], rax
0x1800268e9  lea     rcx, ?s_rwLock@WorkThreadManager@@0Vsrwlock@wil@@A; SRWLock
0x1800268f0  call    cs:__imp_AcquireSRWLockExclusive
0x1800268f6  mov     cs:?s_anyThreadMadeProgress@WorkThreadManager@@0_NA, 1; bool WorkThreadManager::s_anyThreadMadeProgress
0x1800268fd  lea     rcx, [rdi+18h]; this
0x180026901  cmp     [rcx], rcx
0x180026904  jnz     short loc_18002690F
0x180026906  mov     ebx, r12d
0x180026909  mov     [rbp+57h+arg_0], rbx
0x18002690d  jmp     short loc_180026923
0x18002690f  call    ?RawRemoveHead@TaskList@WorkThreadManager@@AEAAPEAUTaskData@2@XZ; WorkThreadManager::TaskList::RawRemoveHead(void)
0x180026914  mov     rsi, rax
0x180026917  mov     rbx, rax
0x18002691a  mov     [rbp+57h+arg_0], rax
0x18002691e  test    rax, rax
0x180026921  jnz     short loc_18002695A
0x180026923  lea     rdx, [rsp+100h+var_E0]
0x180026928  mov     rcx, rdi
0x18002692b  call    ?ClearThreadTask@CThread@WorkThreadManager@@QEAA?AUTaskData@2@XZ; WorkThreadManager::CThread::ClearThreadTask(void)
0x180026930  mov     rdx, rax
0x180026933  lea     rcx, [rbp+57h+var_80]
0x180026937  call    ??4TaskData@WorkThreadManager@@QEAAAEAU01@$$QEAU01@@Z; WorkThreadManager::TaskData::operator=(WorkThreadManager::TaskData &&)
0x18002693c  lea     rcx, [rbp+57h+var_B8+8]
0x180026940  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026945  lea     rcx, [rbp+57h+var_B8]
0x180026949  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002694e  mov     byte ptr [rdi+29h], 1
0x180026952  mov     r15b, 1
0x180026955  jmp     loc_1800269F5
0x18002695a  mov     r15b, r12b
0x18002695d  call    GetTickCount_0
0x180026962  mov     ebx, eax
0x180026964  lea     r14, [rdi+0E0h]
0x18002696b  mov     rcx, r14; SRWLock
0x18002696e  call    cs:__imp_AcquireSRWLockExclusive
0x180026974  lea     r10, [rdi+90h]
0x18002697b  mov     rdx, r10
0x18002697e  lea     rcx, [rsp+100h+var_E0]
0x180026983  call    ??0TaskData@WorkThreadManager@@QEAA@$$QEAU01@@Z; WorkThreadManager::TaskData::TaskData(WorkThreadManager::TaskData &&)
0x180026988  mov     rdx, rsi
0x18002698b  mov     rcx, r10
0x18002698e  call    ??4TaskData@WorkThreadManager@@QEAAAEAU01@$$QEAU01@@Z; WorkThreadManager::TaskData::operator=(WorkThreadManager::TaskData &&)
0x180026993  mov     [rdi+0D8h], ebx
0x180026999  mov     [rdi+59h], r12b
0x18002699d  mov     ebx, [rdi+50h]
0x1800269a0  call    GetCurrentThreadId_0
0x1800269a5  cmp     eax, ebx
0x1800269a7  jz      short loc_1800269B7
0x1800269a9  test    ebx, ebx
0x1800269ab  jz      short loc_1800269B7
0x1800269ad  mov     rcx, [rdi+68h]; this
0x1800269b1  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x1800269b6  nop
0x1800269b7  test    r14, r14
0x1800269ba  jz      short loc_1800269C6
0x1800269bc  mov     rcx, r14; SRWLock
0x1800269bf  call    cs:__imp_ReleaseSRWLockExclusive
0x1800269c5  nop
0x1800269c6  lea     rdx, [rsp+100h+var_E0]
0x1800269cb  lea     rcx, [rbp+57h+var_80]
0x1800269cf  call    ??4TaskData@WorkThreadManager@@QEAAAEAU01@$$QEAU01@@Z; WorkThreadManager::TaskData::operator=(WorkThreadManager::TaskData &&)
0x1800269d4  lea     rcx, [rbp+57h+var_B8+8]
0x1800269d8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800269dd  lea     rcx, [rbp+57h+var_B8]
0x1800269e1  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800269e6  mov     rbx, r12
0x1800269e9  mov     [rbp+57h+arg_0], rbx
0x1800269ed  mov     rcx, rsi; this
0x1800269f0  call    ??_GTaskData@WorkThreadManager@@QEAAPEAXI@Z; WorkThreadManager::TaskData::`scalar deleting destructor'(uint)
0x1800269f5  lea     rcx, [rbp+57h+arg_8]; this
0x1800269f9  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800269fe  lea     rsi, ?s_rwLock@WorkThreadManager@@0Vsrwlock@wil@@A; wil::srwlock WorkThreadManager::s_rwLock
0x180026a05  mov     rcx, rsi; SRWLock
0x180026a08  call    ReleaseSRWLockExclusive_0
0x180026a0d  lea     rcx, [rbp+57h+arg_8]; this
0x180026a11  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180026a16  mov     r8d, dword ptr [rbp+57h+var_80+4]
0x180026a1a  lea     rdx, [rbp+57h+var_98]
0x180026a1e  call    ?AdjustThreadPriority@CThread@WorkThreadManager@@QEAA@W4TaskOptions@Internal@Windows@@@Z; WorkThreadManager::CThread::AdjustThreadPriority(Windows::Internal::TaskOptions)
0x180026a23  mov     [rsp+100h+var_E0], 1
0x180026a2c  mov     [rsp+100h+var_D8], r12d
0x180026a31  mov     [rbp+57h+var_D0], r12
0x180026a35  mov     [rbp+57h+var_C8], r12b
0x180026a39  xor     eax, eax
0x180026a3b  mov     [rbp+57h+var_C7], ax
0x180026a3f  mov     [rbp+57h+var_C5], al
0x180026a42  mov     [rbp+57h+var_C4], rax
0x180026a46  xorps   xmm0, xmm0
0x180026a49  movdqu  [rbp+57h+var_B8], xmm0
0x180026a4e  movups  [rbp+57h+var_A8], xmm0
0x180026a52  lea     rax, [rbp+57h+var_A8]
0x180026a56  mov     qword ptr [rbp+57h+var_A8+8], rax
0x180026a5a  lea     rax, [rbp+57h+var_A8]
0x180026a5e  mov     qword ptr [rbp+57h+var_A8], rax
0x180026a62  lea     rdx, [rsp+100h+var_E0]
0x180026a67  lea     rcx, [rbp+57h+var_80]
0x180026a6b  call    ??4TaskData@WorkThreadManager@@QEAAAEAU01@$$QEAU01@@Z; WorkThreadManager::TaskData::operator=(WorkThreadManager::TaskData &&)
0x180026a70  lea     rcx, [rbp+57h+var_B8+8]
0x180026a74  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026a79  lea     rcx, [rbp+57h+var_B8]
0x180026a7d  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180026a82  cmp     [rbp+57h+var_90], r12b
0x180026a86  jz      short loc_180026AA0
0x180026a88  cmp     [rbp+57h+var_98], r12d
0x180026a8c  jz      short loc_180026AA0
0x180026a8e  call    cs:__imp_GetCurrentThread
0x180026a94  mov     edx, [rbp+57h+nPriority]; nPriority
0x180026a97  mov     rcx, rax; hThread
0x180026a9a  call    cs:__imp_SetThreadPriority
0x180026aa0  test    r15b, r15b
0x180026aa3  jz      loc_180026B9E
0x180026aa9  mov     r14, r12
0x180026aac  mov     [rbp+57h+arg_8], r12
0x180026ab0  mov     rcx, rsi; SRWLock
0x180026ab3  call    cs:__imp_AcquireSRWLockExclusive
0x180026ab9  mov     [rbp+57h+arg_18], rsi
0x180026abd  mov     [rdi+29h], r12b
0x180026ac1  lea     rdx, [rbp+57h+arg_10]
0x180026ac5  lea     rcx, ?s_taskFloodingList@WorkThreadManager@@0VTaskList@1@A; WorkThreadManager::TaskList WorkThreadManager::s_taskFloodingList
0x180026acc  call    ?PopFront@TaskList@WorkThreadManager@@QEAA?AV?$unique_ptr@UTaskData@WorkThreadManager@@U?$default_delete@UTaskData@WorkThreadManager@@@wistd@@@wistd@@XZ; WorkThreadManager::TaskList::PopFront(void)
0x180026ad1  mov     rdx, rax
0x180026ad4  lea     rcx, [rbp+57h+arg_0]
0x180026ad8  call    ??4?$unique_ptr@UTaskData@WorkThreadManager@@U?$default_delete@UTaskData@WorkThreadManager@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>::operator=(wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>> &&)
0x180026add  mov     rcx, [rbp+57h+arg_10]; this
0x180026ae1  mov     [rbp+57h+arg_10], r12
0x180026ae5  test    rcx, rcx
0x180026ae8  jz      short loc_180026AEF
0x180026aea  call    ??_GTaskData@WorkThreadManager@@QEAAPEAXI@Z; WorkThreadManager::TaskData::`scalar deleting destructor'(uint)
0x180026aef  mov     rsi, [rbp+57h+arg_0]
0x180026af3  test    rsi, rsi
0x180026af6  jz      short loc_180026B49
0x180026af8  mov     eax, [rdi+98h]
0x180026afe  cmp     [rsi+8], eax
0x180026b01  jnz     short loc_180026B49
0x180026b03  mov     r8d, [rsi+4]
0x180026b07  mov     edx, [rsi]
0x180026b09  mov     rcx, rdi
0x180026b0c  call    ?Eligible@CThread@WorkThreadManager@@QEBA_NW4TaskApartment@Internal@Windows@@W4TaskOptions@45@@Z; WorkThreadManager::CThread::Eligible(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions)
0x180026b11  test    al, al
0x180026b13  jz      short loc_180026B49
0x180026b15  call    GetTickCount_0
0x180026b1a  mov     r9d, eax
0x180026b1d  mov     r8, rsi
0x180026b20  lea     rdx, [rsp+100h+var_E0]
0x180026b25  mov     rcx, rdi
0x180026b28  call    ?SetThreadTask@CThread@WorkThreadManager@@QEAA?AUTaskData@2@$$QEAU32@K@Z; WorkThreadManager::CThread::SetThreadTask(WorkThreadManager::TaskData &&,ulong)
0x180026b2d  lea     rcx, [rsp+100h+var_E0]; this
0x180026b32  call    ??1TaskData@WorkThreadManager@@QEAA@XZ; WorkThreadManager::TaskData::~TaskData(void)
0x180026b37  mov     rbx, r12
0x180026b3a  test    rsi, rsi
0x180026b3d  jz      short loc_180026B5E
0x180026b3f  mov     rcx, rsi; this
0x180026b42  call    ??_GTaskData@WorkThreadManager@@QEAAPEAXI@Z; WorkThreadManager::TaskData::`scalar deleting destructor'(uint)
0x180026b47  jmp     short loc_180026B5E
0x180026b49  lea     rdx, [rbp+57h+arg_0]
0x180026b4d  lea     rcx, [rbp+57h+arg_8]
0x180026b51  call    ??4?$unique_ptr@UTaskData@WorkThreadManager@@U?$default_delete@UTaskData@WorkThreadManager@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>::operator=(wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>> &&)
0x180026b56  mov     rbx, [rbp+57h+arg_0]
0x180026b5a  mov     r14, [rbp+57h+arg_8]
0x180026b5e  xor     edx, edx
0x180026b60  lea     rcx, [rbp+57h+arg_18]
0x180026b64  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x180026b69  test    r14, r14
0x180026b6c  jz      short loc_180026B87
0x180026b6e  lea     rdx, [rbp+57h+arg_8]
0x180026b72  lea     rcx, [rbp+57h+arg_0]
0x180026b76  call    ??0?$unique_ptr@UTaskData@WorkThreadManager@@U?$default_delete@UTaskData@WorkThreadManager@@@wistd@@@wistd@@QEAA@$$QEAV01@@Z; wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>(wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>> &&)
0x180026b7b  mov     rcx, rax
0x180026b7e  call    ?s_AttachAndRecoverTask@WorkThreadManager@@CAXV?$unique_ptr@UTaskData@WorkThreadManager@@U?$default_delete@UTaskData@WorkThreadManager@@@wistd@@@wistd@@@Z; WorkThreadManager::s_AttachAndRecoverTask(wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>)
0x180026b83  mov     r14, [rbp+57h+arg_8]
0x180026b87  lea     rcx, [rbp+57h+arg_18]
0x180026b8b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180026b90  nop
0x180026b91  test    r14, r14
0x180026b94  jz      short loc_180026B9E
0x180026b96  mov     rcx, r14; this
0x180026b99  call    ??_GTaskData@WorkThreadManager@@QEAAPEAXI@Z; WorkThreadManager::TaskData::`scalar deleting destructor'(uint)
0x180026b9e  test    rbx, rbx
0x180026ba1  jz      short loc_180026BAC
0x180026ba3  mov     rcx, rbx; this
0x180026ba6  call    ??_GTaskData@WorkThreadManager@@QEAAPEAXI@Z; WorkThreadManager::TaskData::`scalar deleting destructor'(uint)
0x180026bab  nop
0x180026bac  lea     rcx, [rbp+57h+var_50]
0x180026bb0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026bb5  lea     rcx, [rbp+57h+var_58]
0x180026bb9  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180026bbe  add     rsp, 0D0h
0x180026bc5  pop     r15
0x180026bc7  pop     r14
0x180026bc9  pop     r12
0x180026bcb  pop     rdi
0x180026bcc  pop     rsi
0x180026bcd  pop     rbx
0x180026bce  pop     rbp
0x180026bcf  retn
```
