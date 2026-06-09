# COplockFileHandleProxy::OpenUnbufferedFileHandle(IUnbufferedFileHandleOplockCallback *,unsigned __int64 *)

- ea: `0x180087610`
- end: `0x18008772e`
- name: `?OpenUnbufferedFileHandle@COplockFileHandleProxy@@UEAAJPEAUIUnbufferedFileHandleOplockCallback@@PEA_K@Z`
- size: `286`
- prototype: `__int64 __fastcall(COplockFileHandleProxy *__hidden this, struct IUnbufferedFileHandleOplockCallback *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000ddd4`
- `0x18003cf28`
- `0x180087610`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180087668`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180087668`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800876f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800876f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall COplockFileHandleProxy::OpenUnbufferedFileHandle(
        COplockFileHandleProxy *this,
        struct IUnbufferedFileHandleOplockCallback *a2,
        unsigned __int64 *a3)
{
  int RemoteIdentity; // ebx
  void *v7; // rdi
  __int64 (__fastcall *v8)(void *, _QWORD, unsigned __int64 *); // rbx
  DWORD CurrentProcessId; // eax
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v13; // [rsp+40h] [rbp+8h] BYREF
  void *v14; // [rsp+58h] [rbp+20h] BYREF

  v14 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v14);
  RemoteIdentity = CFTMCrossProcClientImpl::_GetRemoteIdentity(
                     (COplockFileHandleProxy *)((char *)this + 32),
                     &GUID_cb15a49f_a5f0_41bf_ba39_361cee68ee91,
                     &v14);
  if ( RemoteIdentity >= 0 )
  {
    v7 = v14;
    v8 = *(__int64 (__fastcall **)(void *, _QWORD, unsigned __int64 *))(*(_QWORD *)v14 + 24LL);
    CurrentProcessId = GetCurrentProcessId();
    RemoteIdentity = v8(v7, CurrentProcessId, a3);
    if ( RemoteIdentity >= 0 )
    {
      v13 = 0;
      v10 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this - 1);
      v11 = **v10;
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v13);
      RemoteIdentity = v11(v10, &GUID_cb15a49f_a5f0_41bf_ba39_361cee68ee91, &v13);
      if ( RemoteIdentity < 0
        || (RemoteIdentity = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v13 + 32LL))(v13, *a3),
            RemoteIdentity < 0) )
      {
        CloseHandle((HANDLE)*a3);
        *a3 = 0;
      }
      else
      {
        RemoteIdentity = (*(__int64 (__fastcall **)(__int64, struct IUnbufferedFileHandleOplockCallback *))(*(_QWORD *)v13 + 40LL))(
                           v13,
                           a2);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v13);
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v14);
  return (unsigned int)RemoteIdentity;
}

```

## disassembly

```asm
0x180087610  mov     rax, rsp
0x180087613  mov     [rax+10h], rbx
0x180087617  mov     [rax+18h], rbp
0x18008761b  push    rsi
0x18008761c  push    rdi
0x18008761d  push    r14
0x18008761f  sub     rsp, 20h
0x180087623  mov     rsi, r8
0x180087626  mov     r14, rdx
0x180087629  mov     rbp, rcx
0x18008762c  mov     qword ptr [rax+20h], 0
0x180087634  lea     rcx, [rax+20h]
0x180087638  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18008763d  lea     rcx, [rbp+20h]; this
0x180087641  lea     r8, [rsp+38h+arg_18]; void **
0x180087646  lea     rdx, _GUID_cb15a49f_a5f0_41bf_ba39_361cee68ee91; struct _GUID *
0x18008764d  call    ?_GetRemoteIdentity@CFTMCrossProcClientImpl@@IEAAJAEBU_GUID@@PEAPEAX@Z; CFTMCrossProcClientImpl::_GetRemoteIdentity(_GUID const &,void * *)
0x180087652  mov     ebx, eax
0x180087654  test    eax, eax
0x180087656  js      loc_18008770F
0x18008765c  mov     rdi, [rsp+38h+arg_18]
0x180087661  mov     rax, [rdi]
0x180087664  mov     rbx, [rax+18h]
0x180087668  call    cs:__imp_GetCurrentProcessId
0x18008766e  mov     r8, rsi
0x180087671  mov     edx, eax
0x180087673  mov     rcx, rdi
0x180087676  mov     rax, rbx
0x180087679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008767e  mov     ebx, eax
0x180087680  test    eax, eax
0x180087682  js      loc_18008770F
0x180087688  mov     [rsp+38h+arg_0], 0
0x180087691  mov     rdi, [rbp-8]
0x180087695  mov     rax, [rdi]
0x180087698  mov     rbx, [rax]
0x18008769b  lea     rcx, [rsp+38h+arg_0]
0x1800876a0  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x1800876a5  lea     r8, [rsp+38h+arg_0]
0x1800876aa  lea     rdx, _GUID_cb15a49f_a5f0_41bf_ba39_361cee68ee91
0x1800876b1  mov     rcx, rdi
0x1800876b4  mov     rax, rbx
0x1800876b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800876bc  mov     ebx, eax
0x1800876be  test    eax, eax
0x1800876c0  js      short loc_1800876F4
0x1800876c2  mov     rcx, [rsp+38h+arg_0]
0x1800876c7  mov     rax, [rcx]
0x1800876ca  mov     rdx, [rsi]
0x1800876cd  mov     rax, [rax+20h]
0x1800876d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800876d6  mov     ebx, eax
0x1800876d8  test    eax, eax
0x1800876da  js      short loc_1800876F4
0x1800876dc  mov     rcx, [rsp+38h+arg_0]
0x1800876e1  mov     rax, [rcx]
0x1800876e4  mov     rdx, r14
0x1800876e7  mov     rax, [rax+28h]
0x1800876eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800876f0  mov     ebx, eax
0x1800876f2  jmp     short loc_180087704
0x1800876f4  mov     rcx, [rsi]; hObject
0x1800876f7  call    cs:__imp_CloseHandle
0x1800876fd  mov     qword ptr [rsi], 0
0x180087704  lea     rcx, [rsp+38h+arg_0]
0x180087709  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18008770e  nop
0x18008770f  lea     rcx, [rsp+38h+arg_18]
0x180087714  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180087719  mov     eax, ebx
0x18008771b  mov     rbx, [rsp+38h+arg_8]
0x180087720  mov     rbp, [rsp+38h+arg_10]
0x180087725  add     rsp, 20h
0x180087729  pop     r14
0x18008772b  pop     rdi
0x18008772c  pop     rsi
0x18008772d  retn
```
