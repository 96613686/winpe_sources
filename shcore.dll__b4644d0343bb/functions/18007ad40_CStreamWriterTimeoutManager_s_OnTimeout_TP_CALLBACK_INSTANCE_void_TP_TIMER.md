# CStreamWriterTimeoutManager::s_OnTimeout(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x18007ad40`
- end: `0x18007ae64`
- name: `?s_OnTimeout@CStreamWriterTimeoutManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `292`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ddd4`
- `0x18001f74c`
- `0x1800720cc`
- `0x18007216c`
- `0x1800772bc`
- `0x18007ad40`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ae19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ae19`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007adf5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007adf5`
- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x18007ae22`
- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x18007ae22`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CStreamWriterTimeoutManager::s_OnTimeout(
        PTP_CALLBACK_INSTANCE Instance,
        _DWORD *Context,
        PTP_TIMER Timer)
{
  __int64 v5; // rax
  int v6; // ebx
  __int64 *v7; // rbx
  __int64 (__fastcall *v8)(__int64 *, GUID *, _QWORD *); // rdi
  unsigned int i; // ebx
  __int64 v10; // rcx
  _QWORD v11[2]; // [rsp+20h] [rbp-10h] BYREF
  __int64 v12; // [rsp+58h] [rbp+28h] BYREF
  __int64 *v13; // [rsp+68h] [rbp+38h] BYREF

  v12 = 0;
  v11[0] = 0;
  v13 = &v12;
  v5 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(
         &v13,
         Context,
         Timer);
  if ( (int)Microsoft::WRL::AsWeak<CStreamWriterTimeoutManager::CTimerIdAndWriters>(Context, v5) >= 0 )
  {
    v13 = 0;
    v6 = Microsoft::WRL::WeakRef::As<IInspectable>(&v12, &v13);
    if ( v6 >= 0 )
    {
      v7 = v13;
      if ( v13 )
      {
        v8 = *(__int64 (__fastcall **)(__int64 *, GUID *, _QWORD *))*v13;
        Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(v11);
        v6 = v8(v7, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, v11);
      }
      else
      {
        v6 = -2147467259;
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v13);
    if ( v6 >= 0 )
    {
      EnterCriticalSection(&g_StreamWriterManager);
      for ( i = Context[22];
            (--i & 0x80000000) == 0;
            CSyncedStreamWriterInfo::OnTimeout(*(CSyncedStreamWriterInfo **)(*((_QWORD *)Context + 10) + 8LL * i)) )
      {
        ;
      }
      LeaveCriticalSection(&g_StreamWriterManager);
      DisassociateCurrentThreadFromCallback(Instance);
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(v11);
  v10 = v12;
  if ( v12 )
  {
    v12 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
}

```

## disassembly

```asm
0x18007ad40  mov     [rsp-18h+arg_0], rbx
0x18007ad45  mov     [rsp-18h+arg_10], rsi
0x18007ad4a  push    rbp
0x18007ad4b  push    rdi
0x18007ad4c  push    r14
0x18007ad4e  mov     rbp, rsp
0x18007ad51  sub     rsp, 30h
0x18007ad55  mov     rsi, rdx
0x18007ad58  mov     r14, rcx
0x18007ad5b  mov     [rbp+arg_8], 0
0x18007ad63  mov     [rbp+var_10], 0
0x18007ad6b  lea     rax, [rbp+arg_8]
0x18007ad6f  mov     [rbp+arg_18], rax
0x18007ad73  lea     rcx, [rbp+arg_18]
0x18007ad77  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18007ad7c  mov     rdx, rax
0x18007ad7f  mov     rcx, rsi
0x18007ad82  call    ??$AsWeak@VCTimerIdAndWriters@CStreamWriterTimeoutManager@@@WRL@Microsoft@@YAJPEAVCTimerIdAndWriters@CStreamWriterTimeoutManager@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<CStreamWriterTimeoutManager::CTimerIdAndWriters>(CStreamWriterTimeoutManager::CTimerIdAndWriters *,Microsoft::WRL::WeakRef *)
0x18007ad87  test    eax, eax
0x18007ad89  js      loc_18007AE29
0x18007ad8f  mov     [rbp+arg_18], 0
0x18007ad97  lea     rdx, [rbp+arg_18]
0x18007ad9b  lea     rcx, [rbp+arg_8]
0x18007ad9f  call    ??$As@UIInspectable@@@WeakRef@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIInspectable@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::WeakRef::As<IInspectable>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IInspectable>>)
0x18007ada4  mov     ebx, eax
0x18007ada6  test    eax, eax
0x18007ada8  js      short loc_18007ADE1
0x18007adaa  mov     rbx, [rbp+arg_18]
0x18007adae  test    rbx, rbx
0x18007adb1  jz      short loc_18007ADDC
0x18007adb3  mov     rax, [rbx]
0x18007adb6  mov     rdi, [rax]
0x18007adb9  lea     rcx, [rbp+var_10]
0x18007adbd  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18007adc2  lea     r8, [rbp+var_10]
0x18007adc6  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18007adcd  mov     rcx, rbx
0x18007add0  mov     rax, rdi
0x18007add3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007add8  mov     ebx, eax
0x18007adda  jmp     short loc_18007ADE1
0x18007addc  mov     ebx, 80004005h
0x18007ade1  lea     rcx, [rbp+arg_18]
0x18007ade5  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18007adea  test    ebx, ebx
0x18007adec  js      short loc_18007AE29
0x18007adee  lea     rcx, ?g_StreamWriterManager@@3VCStreamWriterTimeoutManager@@A; lpCriticalSection
0x18007adf5  call    cs:__imp_EnterCriticalSection
0x18007adfb  mov     ebx, [rsi+58h]
0x18007adfe  jmp     short loc_18007AE0D
0x18007ae00  mov     rcx, [rsi+50h]
0x18007ae04  mov     rcx, [rcx+rbx*8]; this
0x18007ae08  call    ?OnTimeout@CSyncedStreamWriterInfo@@QEAAXXZ; CSyncedStreamWriterInfo::OnTimeout(void)
0x18007ae0d  sub     ebx, 1
0x18007ae10  jns     short loc_18007AE00
0x18007ae12  lea     rcx, ?g_StreamWriterManager@@3VCStreamWriterTimeoutManager@@A; lpCriticalSection
0x18007ae19  call    cs:__imp_LeaveCriticalSection
0x18007ae1f  mov     rcx, r14; pci
0x18007ae22  call    cs:__imp_DisassociateCurrentThreadFromCallback
0x18007ae28  nop
0x18007ae29  lea     rcx, [rbp+var_10]
0x18007ae2d  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18007ae32  nop
0x18007ae33  mov     rcx, [rbp+arg_8]
0x18007ae37  test    rcx, rcx
0x18007ae3a  jz      short loc_18007AE51
0x18007ae3c  mov     [rbp+arg_8], 0
0x18007ae44  mov     rax, [rcx]
0x18007ae47  mov     rax, [rax+10h]
0x18007ae4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ae50  nop
0x18007ae51  mov     rbx, [rsp+30h+arg_0]
0x18007ae56  mov     rsi, [rsp+30h+arg_10]
0x18007ae5b  add     rsp, 30h
0x18007ae5f  pop     r14
0x18007ae61  pop     rdi
0x18007ae62  pop     rbp
0x18007ae63  retn
```
