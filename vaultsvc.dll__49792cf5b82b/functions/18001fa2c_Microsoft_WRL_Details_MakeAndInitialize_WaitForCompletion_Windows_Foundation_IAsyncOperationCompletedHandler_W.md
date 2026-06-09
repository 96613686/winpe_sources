# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x18001fa2c`
- end: `0x18001fb03`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f818`

## callees

- `0x18001fa00`
- `0x18001fa2c`
- `0x18001fb0c`
- `0x180038ce0`
- `0x18003b500`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001fa85`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001fa85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa94`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___23___YAJPEAU__IAsyncOperation_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___23___YAJPEAU__IAsyncOperation_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        _QWORD *a1)
{
  void *v2; // rax
  _QWORD *v3; // rdi
  HANDLE Event; // rax
  signed int LastError; // eax
  signed int v6; // ebx
  _QWORD *v8; // [rsp+30h] [rbp+8h] BYREF
  __int64 v9; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v2 )
    return 2147942414LL;
  v3 = (_QWORD *)`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>'::`2'::FTMEventDelegate::FTMEventDelegate(v2);
  v8 = v3;
  v9 = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  v3[7] = Event;
  if ( Event )
    goto LABEL_6;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 >= 0 )
  {
LABEL_6:
    (*(void (__fastcall **)(_QWORD *))(*v3 + 8LL))(v3);
    *a1 = v3;
    (*(void (__fastcall **)(_QWORD *))(*v3 + 16LL))(v3);
    return 0;
  }
  else
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
    __1__MakeAllocator_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___23___YAJPEAU__IAsyncOperation_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Details_WRL_Microsoft__QEAA_XZ(&v9);
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x18001fa2c  mov     [rsp+arg_10], rbx
0x18001fa31  mov     [rsp+arg_18], rsi
0x18001fa36  push    rdi
0x18001fa37  sub     rsp, 20h
0x18001fa3b  mov     rsi, rcx
0x18001fa3e  mov     qword ptr [rcx], 0
0x18001fa45  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fa4c  mov     ecx, 40h ; '@'; unsigned __int64
0x18001fa51  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001fa56  test    rax, rax
0x18001fa59  jz      loc_18001FAE4
0x18001fa5f  mov     rcx, rax
0x18001fa62  call    ??0FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@QEAA@XZ; `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::FTMEventDelegate(void)
0x18001fa67  mov     rdi, rax
0x18001fa6a  mov     [rsp+28h+arg_0], rax
0x18001fa6f  mov     [rsp+28h+arg_8], 0
0x18001fa78  mov     r9d, 1F0003h; dwDesiredAccess
0x18001fa7e  xor     r8d, r8d; dwFlags
0x18001fa81  xor     edx, edx; lpName
0x18001fa83  xor     ecx, ecx; lpEventAttributes
0x18001fa85  call    cs:__imp_CreateEventExW
0x18001fa8b  mov     [rdi+38h], rax
0x18001fa8f  test    rax, rax
0x18001fa92  jnz     short loc_18001FAA4
0x18001fa94  call    cs:__imp_GetLastError
0x18001fa9a  mov     ebx, eax
0x18001fa9c  test    eax, eax
0x18001fa9e  jg      short loc_18001FAD9
0x18001faa0  test    ebx, ebx
0x18001faa2  js      short loc_18001FAEB
0x18001faa4  mov     rax, [rdi]
0x18001faa7  mov     rcx, rdi
0x18001faaa  mov     rax, [rax+8]
0x18001faae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fab3  nop
0x18001fab4  mov     [rsi], rdi
0x18001fab7  mov     rax, [rdi]
0x18001faba  mov     rcx, rdi
0x18001fabd  mov     rax, [rax+10h]
0x18001fac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fac6  nop
0x18001fac7  xor     eax, eax
0x18001fac9  mov     rbx, [rsp+28h+arg_10]
0x18001face  mov     rsi, [rsp+28h+arg_18]
0x18001fad3  add     rsp, 20h
0x18001fad7  pop     rdi
0x18001fad8  retn
0x18001fad9  movzx   ebx, ax
0x18001fadc  or      ebx, 80070000h
0x18001fae2  jmp     short loc_18001FAA0
0x18001fae4  mov     eax, 8007000Eh
0x18001fae9  jmp     short loc_18001FAC9
0x18001faeb  lea     rcx, [rsp+28h+arg_0]
0x18001faf0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001faf5  lea     rcx, [rsp+28h+arg_8]
0x18001fafa  call    ??1?$MakeAllocator@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::~MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>(void)
0x18001faff  mov     eax, ebx
0x18001fb01  jmp     short loc_18001FAC9
```
