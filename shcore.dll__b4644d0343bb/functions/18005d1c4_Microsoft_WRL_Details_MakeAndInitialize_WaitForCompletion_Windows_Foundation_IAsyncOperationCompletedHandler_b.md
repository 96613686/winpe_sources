# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x18005d1c4`
- end: `0x18005d283`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@U?$IAsyncOperation@_N@23@@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@U?$IAsyncOperation@_N@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@U?$IAsyncOperation@_N@23@@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180042068`

## callees

- `0x18000ddd4`
- `0x18002a544`
- `0x18005d1c4`
- `0x180068d9c`
- `0x180081598`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18005d220`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18005d220`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d22f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d22f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler__N_Foundation_Windows__U__IAsyncOperation__N_23___YAJPEAU__IAsyncOperation__N_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler__N_Foundation_Windows__U__IAsyncOperation__N_23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler__N_Foundation_Windows__U__IAsyncOperation__N_23___YAJPEAU__IAsyncOperation__N_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        _QWORD *a1)
{
  void *v2; // rax
  _QWORD *v4; // rdi
  HANDLE Event; // rax
  signed int LastError; // eax
  signed int v7; // ebx
  _QWORD *v8; // [rsp+30h] [rbp+8h] BYREF
  __int64 v9; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v2 )
    return 2147942414LL;
  v4 = (_QWORD *)`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>'::`2'::FTMEventDelegate::FTMEventDelegate(v2);
  v8 = v4;
  v9 = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  v4[7] = Event;
  if ( Event )
    goto LABEL_7;
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 >= 0 )
  {
LABEL_7:
    (*(void (__fastcall **)(_QWORD *))(*v4 + 8LL))(v4);
    *a1 = v4;
    v7 = 0;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v8);
  Microsoft::WRL::Details::MakeAllocator<CRasFilePlaceholderParams>::~MakeAllocator<CRasFilePlaceholderParams>(&v9);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18005d1c4  mov     [rsp+arg_10], rbx
0x18005d1c9  mov     [rsp+arg_18], rsi
0x18005d1ce  push    rdi
0x18005d1cf  sub     rsp, 20h
0x18005d1d3  mov     rsi, rcx
0x18005d1d6  mov     qword ptr [rcx], 0
0x18005d1dd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005d1e4  mov     ecx, 40h ; '@'; unsigned __int64
0x18005d1e9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005d1ee  test    rax, rax
0x18005d1f1  jnz     short loc_18005D1FA
0x18005d1f3  mov     eax, 8007000Eh
0x18005d1f8  jmp     short loc_18005D273
0x18005d1fa  mov     rcx, rax
0x18005d1fd  call    ??0FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@U?$IAsyncOperation@_N@23@@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@QEAA@XZ; `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::FTMEventDelegate(void)
0x18005d202  mov     rdi, rax
0x18005d205  mov     [rsp+28h+arg_0], rax
0x18005d20a  mov     [rsp+28h+arg_8], 0
0x18005d213  mov     r9d, 1F0003h; dwDesiredAccess
0x18005d219  xor     r8d, r8d; dwFlags
0x18005d21c  xor     edx, edx; lpName
0x18005d21e  xor     ecx, ecx; lpEventAttributes
0x18005d220  call    cs:__imp_CreateEventExW
0x18005d226  mov     [rdi+38h], rax
0x18005d22a  test    rax, rax
0x18005d22d  jnz     short loc_18005D248
0x18005d22f  call    cs:__imp_GetLastError
0x18005d235  mov     ebx, eax
0x18005d237  test    eax, eax
0x18005d239  jle     short loc_18005D244
0x18005d23b  movzx   ebx, ax
0x18005d23e  or      ebx, 80070000h
0x18005d244  test    ebx, ebx
0x18005d246  js      short loc_18005D25D
0x18005d248  mov     rax, [rdi]
0x18005d24b  mov     rcx, rdi
0x18005d24e  mov     rax, [rax+8]
0x18005d252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d257  nop
0x18005d258  mov     [rsi], rdi
0x18005d25b  xor     ebx, ebx
0x18005d25d  lea     rcx, [rsp+28h+arg_0]
0x18005d262  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18005d267  lea     rcx, [rsp+28h+arg_8]
0x18005d26c  call    ??1?$MakeAllocator@VCRasFilePlaceholderParams@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CRasFilePlaceholderParams>::~MakeAllocator<CRasFilePlaceholderParams>(void)
0x18005d271  mov     eax, ebx
0x18005d273  mov     rbx, [rsp+28h+arg_10]
0x18005d278  mov     rsi, [rsp+28h+arg_18]
0x18005d27d  add     rsp, 20h
0x18005d281  pop     rdi
0x18005d282  retn
```
