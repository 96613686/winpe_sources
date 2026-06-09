# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<uint,uint>,Windows::Foundation::IAsyncOperationWithProgress<uint,uint>>(Windows::Foundation::IAsyncOperationWithProgress<uint,uint> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<uint,uint>,Windows::Foundation::IAsyncOperationWithProgress<uint,uint>>(Windows::Foundation::IAsyncOperationWithProgress<uint,uint> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<uint,uint>,Windows::Foundation::IAsyncOperationWithProgress<uint,uint>>(Windows::Foundation::IAsyncOperationWithProgress<uint,uint> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x180034f50`
- end: `0x180035025`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@II@Foundation@Windows@@U?$IAsyncOperationWithProgress@II@23@@@YAJPEAU?$IAsyncOperationWithProgress@II@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@II@Foundation@Windows@@U?$IAsyncOperationWithProgress@II@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@II@Foundation@Windows@@U?$IAsyncOperationWithProgress@II@23@@@YAJPEAU?$IAsyncOperationWithProgress@II@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180034cac`

## callees

- `0x18000ddd4`
- `0x18002a544`
- `0x180034f50`
- `0x18003502c`
- `0x180068d9c`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180034fa9`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180034fa9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fb8`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_II_Foundation_Windows__U__IAsyncOperationWithProgress_II_23___YAJPEAU__IAsyncOperationWithProgress_II_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_II_Foundation_Windows__U__IAsyncOperationWithProgress_II_23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_II_Foundation_Windows__U__IAsyncOperationWithProgress_II_23___YAJPEAU__IAsyncOperationWithProgress_II_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
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
  v3 = (_QWORD *)`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned int,unsigned int>,Windows::Foundation::IAsyncOperationWithProgress<unsigned int,unsigned int>>'::`2'::FTMEventDelegate::FTMEventDelegate(v2);
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
0x180034f50  mov     [rsp+arg_10], rbx
0x180034f55  mov     [rsp+arg_18], rsi
0x180034f5a  push    rdi
0x180034f5b  sub     rsp, 20h
0x180034f5f  mov     rsi, rcx
0x180034f62  mov     qword ptr [rcx], 0
0x180034f69  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180034f70  mov     ecx, 40h ; '@'; unsigned __int64
0x180034f75  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180034f7a  test    rax, rax
0x180034f7d  jz      loc_180035006
0x180034f83  mov     rcx, rax
0x180034f86  call    ??0FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@II@Foundation@Windows@@U?$IAsyncOperationWithProgress@II@23@@@YAJPEAU?$IAsyncOperationWithProgress@II@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@QEAA@XZ; `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<uint,uint>,Windows::Foundation::IAsyncOperationWithProgress<uint,uint>>(Windows::Foundation::IAsyncOperationWithProgress<uint,uint> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::FTMEventDelegate(void)
0x180034f8b  mov     rdi, rax
0x180034f8e  mov     [rsp+28h+arg_0], rax
0x180034f93  mov     [rsp+28h+arg_8], 0
0x180034f9c  mov     r9d, 1F0003h; dwDesiredAccess
0x180034fa2  xor     r8d, r8d; dwFlags
0x180034fa5  xor     edx, edx; lpName
0x180034fa7  xor     ecx, ecx; lpEventAttributes
0x180034fa9  call    cs:__imp_CreateEventExW
0x180034faf  mov     [rdi+38h], rax
0x180034fb3  test    rax, rax
0x180034fb6  jnz     short loc_180034FD1
0x180034fb8  call    cs:__imp_GetLastError
0x180034fbe  mov     ebx, eax
0x180034fc0  test    eax, eax
0x180034fc2  jle     short loc_180034FCD
0x180034fc4  movzx   ebx, ax
0x180034fc7  or      ebx, 80070000h
0x180034fcd  test    ebx, ebx
0x180034fcf  js      short loc_18003500D
0x180034fd1  mov     rax, [rdi]
0x180034fd4  mov     rcx, rdi
0x180034fd7  mov     rax, [rax+8]
0x180034fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034fe0  nop
0x180034fe1  mov     [rsi], rdi
0x180034fe4  mov     rax, [rdi]
0x180034fe7  mov     rcx, rdi
0x180034fea  mov     rax, [rax+10h]
0x180034fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034ff3  nop
0x180034ff4  xor     eax, eax
0x180034ff6  mov     rbx, [rsp+28h+arg_10]
0x180034ffb  mov     rsi, [rsp+28h+arg_18]
0x180035000  add     rsp, 20h
0x180035004  pop     rdi
0x180035005  retn
0x180035006  mov     eax, 8007000Eh
0x18003500b  jmp     short loc_180034FF6
0x18003500d  lea     rcx, [rsp+28h+arg_0]
0x180035012  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180035017  lea     rcx, [rsp+28h+arg_8]
0x18003501c  call    ??1?$MakeAllocator@VCRasFilePlaceholderParams@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CRasFilePlaceholderParams>::~MakeAllocator<CRasFilePlaceholderParams>(void)
0x180035021  mov     eax, ebx
0x180035023  jmp     short loc_180034FF6
```
