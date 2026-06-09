# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x180033fc8`
- end: `0x18003409d`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180033d24`

## callees

- `0x18000ddd4`
- `0x18002a544`
- `0x180033fc8`
- `0x1800340a4`
- `0x180068d9c`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180034021`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180034021`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034030`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034030`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAUIBuffer_Streams_Storage_Windows__I_Foundation_Windows__U__IAsyncOperationWithProgress_PEAUIBuffer_Streams_Storage_Windows__I_23___YAJPEAU__IAsyncOperationWithProgress_PEAUIBuffer_Streams_Storage_Windows__I_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAUIBuffer_Streams_Storage_Windows__I_Foundation_Windows__U__IAsyncOperationWithProgress_PEAUIBuffer_Streams_Storage_Windows__I_23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAUIBuffer_Streams_Storage_Windows__I_Foundation_Windows__U__IAsyncOperationWithProgress_PEAUIBuffer_Streams_Storage_Windows__I_23___YAJPEAU__IAsyncOperationWithProgress_PEAUIBuffer_Streams_Storage_Windows__I_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
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
  v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v2 )
    return 2147942414LL;
  v3 = (_QWORD *)`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,unsigned int>>'::`2'::FTMEventDelegate::FTMEventDelegate(v2);
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
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v8);
    Microsoft::WRL::Details::MakeAllocator<CRasFilePlaceholderParams>::~MakeAllocator<CRasFilePlaceholderParams>(&v9);
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x180033fc8  mov     [rsp+arg_10], rbx
0x180033fcd  mov     [rsp+arg_18], rsi
0x180033fd2  push    rdi
0x180033fd3  sub     rsp, 20h
0x180033fd7  mov     rsi, rcx
0x180033fda  mov     qword ptr [rcx], 0
0x180033fe1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180033fe8  mov     ecx, 40h ; '@'; unsigned __int64
0x180033fed  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180033ff2  test    rax, rax
0x180033ff5  jz      loc_18003407E
0x180033ffb  mov     rcx, rax
0x180033ffe  call    ??0FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@QEAA@XZ; `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::FTMEventDelegate(void)
0x180034003  mov     rdi, rax
0x180034006  mov     [rsp+28h+arg_0], rax
0x18003400b  mov     [rsp+28h+arg_8], 0
0x180034014  mov     r9d, 1F0003h; dwDesiredAccess
0x18003401a  xor     r8d, r8d; dwFlags
0x18003401d  xor     edx, edx; lpName
0x18003401f  xor     ecx, ecx; lpEventAttributes
0x180034021  call    cs:__imp_CreateEventExW
0x180034027  mov     [rdi+38h], rax
0x18003402b  test    rax, rax
0x18003402e  jnz     short loc_180034049
0x180034030  call    cs:__imp_GetLastError
0x180034036  mov     ebx, eax
0x180034038  test    eax, eax
0x18003403a  jle     short loc_180034045
0x18003403c  movzx   ebx, ax
0x18003403f  or      ebx, 80070000h
0x180034045  test    ebx, ebx
0x180034047  js      short loc_180034085
0x180034049  mov     rax, [rdi]
0x18003404c  mov     rcx, rdi
0x18003404f  mov     rax, [rax+8]
0x180034053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034058  nop
0x180034059  mov     [rsi], rdi
0x18003405c  mov     rax, [rdi]
0x18003405f  mov     rcx, rdi
0x180034062  mov     rax, [rax+10h]
0x180034066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003406b  nop
0x18003406c  xor     eax, eax
0x18003406e  mov     rbx, [rsp+28h+arg_10]
0x180034073  mov     rsi, [rsp+28h+arg_18]
0x180034078  add     rsp, 20h
0x18003407c  pop     rdi
0x18003407d  retn
0x18003407e  mov     eax, 8007000Eh
0x180034083  jmp     short loc_18003406E
0x180034085  lea     rcx, [rsp+28h+arg_0]
0x18003408a  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18003408f  lea     rcx, [rsp+28h+arg_8]
0x180034094  call    ??1?$MakeAllocator@VCRasFilePlaceholderParams@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CRasFilePlaceholderParams>::~MakeAllocator<CRasFilePlaceholderParams>(void)
0x180034099  mov     eax, ebx
0x18003409b  jmp     short loc_18003406E
```
