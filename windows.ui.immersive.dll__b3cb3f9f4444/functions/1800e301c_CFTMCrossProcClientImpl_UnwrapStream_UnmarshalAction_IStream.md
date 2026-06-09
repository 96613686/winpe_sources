# CFTMCrossProcClientImpl::_UnwrapStream(UnmarshalAction,IStream *)

- ea: `0x1800e301c`
- end: `0x1800e3212`
- name: `?_UnwrapStream@CFTMCrossProcClientImpl@@AEAAJW4UnmarshalAction@@PEAUIStream@@@Z`
- size: `502`
- prototype: `int __high(enum UnmarshalAction, struct IStream *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800e2e40`
- `0x1800e2e60`

## callees

- `0x180006800`
- `0x180013f14`
- `0x180014350`
- `0x18002ae9c`
- `0x18002e93c`
- `0x180049a84`
- `0x1800729ec`
- `0x1800e301c`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e31e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e31e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e318d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e318d`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800e310f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800e3174`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800e310f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800e3174`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800e319f`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800e319f`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x1800e3065`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x1800e3065`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1800e30e9`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1800e30e9`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800e30ab`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800e30ab`

## pseudocode

```c
__int64 __fastcall CFTMCrossProcClientImpl::_UnwrapStream(__int64 a1, unsigned int a2, IStream *a3)
{
  LPVOID v6; // rdi
  unsigned __int64 *v7; // rax
  unsigned __int64 *v8; // rbx
  UINT *v9; // r14
  unsigned __int64 v10; // rcx
  BYTE *v11; // rbx
  void *v12; // rcx
  unsigned int v13; // r10d
  int v14; // eax
  IStream *v15; // rax
  unsigned __int64 v17; // [rsp+20h] [rbp-10h] BYREF
  __int64 v18; // [rsp+28h] [rbp-8h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp+48h] BYREF

  if ( a2 )
  {
    LODWORD(v6) = CoReleaseMarshalData(a3);
  }
  else
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    LODWORD(v6) = CoUnmarshalInterface(a3, &GUID_00000000_0000_0000_c000_000000000046, &ppv);
    if ( (int)v6 >= 0 )
    {
      v6 = ppv;
      v17 = a1 + 72;
      v7 = (unsigned __int64 *)Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(&v17);
      v8 = v7;
      if ( v6 )
      {
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(v7);
        LODWORD(v6) = RoGetAgileReference(0, &GUID_00000000_0000_0000_c000_000000000046, v6, v8);
      }
      else
      {
        v17 = *v7;
        v18 = 0;
        *v7 = 0;
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v17);
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v18);
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  }
  if ( (int)v6 >= 0 )
  {
    v9 = (UINT *)(a1 + 32);
    LODWORD(v6) = IStream_Read(a3, (void *)(a1 + 32), 4u);
    if ( (int)v6 >= 0 )
    {
      v10 = *v9;
      v11 = 0;
      ppv = 0;
      v17 = 0;
      LODWORD(v6) = ULongLongMult(v10, 1u, &v17);
      if ( (int)v6 >= 0 )
      {
        v14 = CTCoAllocPolicy::Alloc(v12, v13, v17, &ppv);
        v11 = (BYTE *)ppv;
        LODWORD(v6) = v14;
      }
      if ( (int)v6 >= 0 )
      {
        if ( !*v9 || (LODWORD(v6) = IStream_Read(a3, v11, *v9), (int)v6 >= 0) )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
          v15 = SHCreateMemStream(v11, *v9);
          Microsoft::WRL::ComPtr<Windows::Internal::PopupWindowXAMLContentImpl>::Attach(a1 + 80, v15);
          if ( *(_QWORD *)(a1 + 80) )
            LODWORD(v6) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 96LL))(a1, a2);
          else
            LODWORD(v6) = -2147024882;
          if ( a1 != -88 )
            LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
        }
      }
      CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&ppv);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800e301c  mov     [rsp-28h+arg_0], rbx
0x1800e3021  mov     [rsp-28h+arg_8], rsi
0x1800e3026  push    rbp
0x1800e3027  push    rdi
0x1800e3028  push    r12
0x1800e302a  push    r14
0x1800e302c  push    r15
0x1800e302e  mov     rbp, rsp
0x1800e3031  sub     rsp, 30h
0x1800e3035  mov     rsi, r8
0x1800e3038  mov     r12d, edx
0x1800e303b  mov     r15, rcx
0x1800e303e  test    edx, edx
0x1800e3040  jnz     loc_1800E30E6
0x1800e3046  lea     rcx, [rbp+ppv]
0x1800e304a  mov     [rbp+ppv], 0
0x1800e3052  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e3057  lea     r8, [rbp+ppv]; ppv
0x1800e305b  mov     rcx, rsi; pStm
0x1800e305e  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800e3065  call    cs:__imp_CoUnmarshalInterface
0x1800e306c  nop     dword ptr [rax+rax+00h]
0x1800e3071  mov     edi, eax
0x1800e3073  test    eax, eax
0x1800e3075  js      short loc_1800E30DB
0x1800e3077  mov     rdi, [rbp+ppv]
0x1800e307b  lea     rax, [r15+48h]
0x1800e307f  lea     rcx, [rbp+var_10]
0x1800e3083  mov     [rbp+var_10], rax
0x1800e3087  call    ??B?$ComPtrRef@VAgileRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVAgileRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(void)
0x1800e308c  mov     rbx, rax
0x1800e308f  test    rdi, rdi
0x1800e3092  jz      short loc_1800E30BB
0x1800e3094  mov     rcx, rax
0x1800e3097  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800e309c  mov     r9, rbx
0x1800e309f  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800e30a6  mov     r8, rdi
0x1800e30a9  xor     ecx, ecx
0x1800e30ab  call    cs:__imp_RoGetAgileReference
0x1800e30b2  nop     dword ptr [rax+rax+00h]
0x1800e30b7  mov     edi, eax
0x1800e30b9  jmp     short loc_1800E30DB
0x1800e30bb  mov     rax, [rax]
0x1800e30be  lea     rcx, [rbp+var_10]
0x1800e30c2  mov     [rbp+var_10], rax
0x1800e30c6  mov     [rbp+var_8], rdi
0x1800e30ca  mov     [rbx], rdi
0x1800e30cd  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800e30d2  lea     rcx, [rbp+var_8]
0x1800e30d6  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800e30db  lea     rcx, [rbp+ppv]
0x1800e30df  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e30e4  jmp     short loc_1800E30F7
0x1800e30e6  mov     rcx, rsi; pStm
0x1800e30e9  call    cs:__imp_CoReleaseMarshalData
0x1800e30f0  nop     dword ptr [rax+rax+00h]
0x1800e30f5  mov     edi, eax
0x1800e30f7  test    edi, edi
0x1800e30f9  js      loc_1800E31F8
0x1800e30ff  lea     r14, [r15+20h]
0x1800e3103  mov     r8d, 4; cb
0x1800e3109  mov     rdx, r14; pv
0x1800e310c  mov     rcx, rsi; pstm
0x1800e310f  call    cs:__imp_IStream_Read
0x1800e3116  nop     dword ptr [rax+rax+00h]
0x1800e311b  mov     edi, eax
0x1800e311d  test    eax, eax
0x1800e311f  js      loc_1800E31F8
0x1800e3125  mov     ecx, [r14]; unsigned __int64
0x1800e3128  lea     r8, [rbp+var_10]; unsigned __int64 *
0x1800e312c  xor     ebx, ebx
0x1800e312e  mov     [rbp+ppv], rbx
0x1800e3132  mov     [rbp+var_10], rbx
0x1800e3136  lea     r10d, [rbx+1]
0x1800e313a  mov     edx, r10d; unsigned __int64
0x1800e313d  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800e3142  mov     edi, eax
0x1800e3144  test    eax, eax
0x1800e3146  js      short loc_1800E315E
0x1800e3148  mov     r8, [rbp+var_10]; unsigned __int64
0x1800e314c  lea     r9, [rbp+ppv]; void **
0x1800e3150  mov     edx, r10d; unsigned int
0x1800e3153  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800e3158  mov     rbx, [rbp+ppv]
0x1800e315c  mov     edi, eax
0x1800e315e  test    edi, edi
0x1800e3160  js      loc_1800E31EF
0x1800e3166  mov     r8d, [r14]; cb
0x1800e3169  test    r8d, r8d
0x1800e316c  jz      short loc_1800E3186
0x1800e316e  mov     rdx, rbx; pv
0x1800e3171  mov     rcx, rsi; pstm
0x1800e3174  call    cs:__imp_IStream_Read
0x1800e317b  nop     dword ptr [rax+rax+00h]
0x1800e3180  mov     edi, eax
0x1800e3182  test    eax, eax
0x1800e3184  js      short loc_1800E31EF
0x1800e3186  lea     rsi, [r15+58h]
0x1800e318a  mov     rcx, rsi; lpCriticalSection
0x1800e318d  call    cs:__imp_EnterCriticalSection
0x1800e3194  nop     dword ptr [rax+rax+00h]
0x1800e3199  mov     edx, [r14]; cbInit
0x1800e319c  mov     rcx, rbx; pInit
0x1800e319f  call    cs:__imp_SHCreateMemStream
0x1800e31a6  nop     dword ptr [rax+rax+00h]
0x1800e31ab  mov     rdx, rax
0x1800e31ae  lea     rcx, [r15+50h]
0x1800e31b2  call    ?Attach@?$ComPtr@VPopupWindowXAMLContentImpl@Internal@Windows@@@WRL@Microsoft@@QEAAXPEAVPopupWindowXAMLContentImpl@Internal@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::Internal::PopupWindowXAMLContentImpl>::Attach(Windows::Internal::PopupWindowXAMLContentImpl *)
0x1800e31b7  mov     r8, [r15+50h]
0x1800e31bb  test    r8, r8
0x1800e31be  jnz     short loc_1800E31C7
0x1800e31c0  mov     edi, 8007000Eh
0x1800e31c5  jmp     short loc_1800E31DB
0x1800e31c7  mov     rax, [r15]
0x1800e31ca  mov     edx, r12d
0x1800e31cd  mov     rcx, r15
0x1800e31d0  mov     rax, [rax+60h]
0x1800e31d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e31d9  mov     edi, eax
0x1800e31db  test    rsi, rsi
0x1800e31de  jz      short loc_1800E31EF
0x1800e31e0  mov     rcx, rsi; lpCriticalSection
0x1800e31e3  call    cs:__imp_LeaveCriticalSection
0x1800e31ea  nop     dword ptr [rax+rax+00h]
0x1800e31ef  lea     rcx, [rbp+ppv]
0x1800e31f3  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800e31f8  mov     rbx, [rsp+30h+arg_0]
0x1800e31fd  mov     eax, edi
0x1800e31ff  mov     rsi, [rsp+30h+arg_8]
0x1800e3204  add     rsp, 30h
0x1800e3208  pop     r15
0x1800e320a  pop     r14
0x1800e320c  pop     r12
0x1800e320e  pop     rdi
0x1800e320f  pop     rbp
0x1800e3210  retn
```
