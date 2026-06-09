# Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Storage::Streams::IBuffer *,uint>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(uint)

- ea: `0x1800753a0`
- end: `0x180075574`
- name: `?FireProgress@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@U?$IAsyncOperationProgressHandler@PEAUIBuffer@Streams@Storage@Windows@@I@23@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@QEAAJI@Z`
- size: `468`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180079800`

## callees

- `0x18000ddd4`
- `0x18001415c`
- `0x18001db74`
- `0x180046028`
- `0x18004ba14`
- `0x180074808`
- `0x1800753a0`
- `0x180079aa8`
- `0x180079c84`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18007549f`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18007549f`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800754cb`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800754cb`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180075501`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180075501`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(
        __int64 a1,
        unsigned int a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  bool v6; // dl
  IUnknown *v7; // rbx
  int v8; // eax
  __int64 v10; // [rsp+40h] [rbp-30h] BYREF
  LPSTREAM ppstm; // [rsp+48h] [rbp-28h] BYREF
  HRESULT v12; // [rsp+50h] [rbp-20h]
  GUID v13; // [rsp+60h] [rbp-10h] BYREF
  struct IUnknown *v14; // [rsp+A0h] [rbp+30h] BYREF
  struct IRpcOptions *v15; // [rsp+B0h] [rbp+40h] BYREF
  LPUNKNOWN pUnk; // [rsp+B8h] [rbp+48h] BYREF

  v4 = 0;
  v10 = a1;
  Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(&v10);
  pUnk = 0;
  if ( (unsigned __int8)Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(a1)
    && (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,unsigned int>>(
              &v10,
              &pUnk) >= 0 )
  {
    v14 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v14);
    if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationProgressHandler<Windows::Storage::Streams::IBuffer *,unsigned int>>::CopyLocal(
                a1 + 144,
                v5,
                &v14) >= 0 )
    {
      if ( Microsoft::WRL::gCausality )
      {
        v13 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
        (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, int))(*(_QWORD *)Microsoft::WRL::gCausality + 72LL))(
          Microsoft::WRL::gCausality,
          1,
          2,
          &v13,
          a1,
          1);
      }
      v15 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v15);
      RpcOptionsHelper::GetRpcOptions(v14, v6, &v15);
      ppstm = 0;
      v12 = 0;
      if ( v15 && v14 )
      {
        v7 = pUnk;
        Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&ppstm);
        v12 = CreateStreamOnHGlobal(0, 1, &ppstm);
        if ( v12 >= 0 )
          v12 = CoMarshalInterface(ppstm, &GUID_00000000_0000_0000_c000_000000000046, v7, 0, 0, 1u);
      }
      else
      {
        v12 = -2147467262;
      }
      v8 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, _QWORD))v14->lpVtbl[1].QueryInterface)(v14, pUnk, a2);
      v4 = v8;
      if ( v8 < 0 )
      {
        RoTransformError((unsigned int)v8, 0, 0);
        v4 = 0;
      }
      if ( Microsoft::WRL::gCausality )
        (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, __int64))(*(_QWORD *)Microsoft::WRL::gCausality + 80LL))(
          Microsoft::WRL::gCausality,
          1,
          2,
          1);
      AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>(&ppstm);
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v15);
    }
    Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(a1);
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v14);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&pUnk);
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v10);
  return v4;
}

```

## disassembly

```asm
0x1800753a0  push    rbp
0x1800753a2  push    rbx
0x1800753a3  push    rsi
0x1800753a4  push    rdi
0x1800753a5  push    r15
0x1800753a7  mov     rbp, rsp
0x1800753aa  sub     rsp, 70h
0x1800753ae  mov     esi, edx
0x1800753b0  mov     rdi, rcx
0x1800753b3  xor     ebx, ebx
0x1800753b5  mov     [rbp+var_30], rcx
0x1800753b9  lea     rcx, [rbp+var_30]
0x1800753bd  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x1800753c2  nop
0x1800753c3  mov     [rbp+pUnk], rbx
0x1800753c7  mov     rcx, rdi
0x1800753ca  call    ?TryLockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@U?$IAsyncOperationProgressHandler@PEAUIBuffer@Streams@Storage@Windows@@I@23@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAA_NXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Storage::Streams::IBuffer *,uint>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(void)
0x1800753cf  test    al, al
0x1800753d1  jz      loc_180075554
0x1800753d7  lea     rdx, [rbp+pUnk]
0x1800753db  lea     rcx, [rbp+var_30]
0x1800753df  call    ??$As@U?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint>>>)
0x1800753e4  test    eax, eax
0x1800753e6  js      loc_180075554
0x1800753ec  mov     [rbp+arg_0], rbx
0x1800753f0  lea     rcx, [rbp+arg_0]
0x1800753f4  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x1800753f9  lea     rcx, [rdi+90h]
0x180075400  lea     r8, [rbp+arg_0]
0x180075404  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationProgressHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationProgressHandler<Windows::Storage::Streams::IBuffer *,uint>>::CopyLocal(_GUID const &,void * *)
0x180075409  test    eax, eax
0x18007540b  js      loc_180075541
0x180075411  lea     r15d, [rbx+1]
0x180075415  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18007541c  test    rcx, rcx
0x18007541f  jz      short loc_18007544E
0x180075421  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180075428  movdqu  [rbp+var_10], xmm0
0x18007542d  mov     rax, [rcx]
0x180075430  mov     [rsp+70h+mshlflags], r15d
0x180075435  mov     [rsp+70h+pvDestContext], rdi
0x18007543a  lea     r9, [rbp+var_10]
0x18007543e  lea     r8d, [rbx+2]
0x180075442  mov     edx, r15d
0x180075445  mov     rax, [rax+48h]
0x180075449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007544e  mov     [rbp+arg_10], 0
0x180075456  lea     rcx, [rbp+arg_10]
0x18007545a  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18007545f  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x180075463  mov     rcx, [rbp+arg_0]; struct IUnknown *
0x180075467  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18007546c  mov     [rbp+ppstm], 0
0x180075474  mov     [rbp+var_20], 0
0x18007547b  cmp     [rbp+arg_10], 0
0x180075480  jz      short loc_1800754D6
0x180075482  cmp     [rbp+arg_0], 0
0x180075487  jz      short loc_1800754D6
0x180075489  mov     rbx, [rbp+pUnk]
0x18007548d  lea     rcx, [rbp+ppstm]
0x180075491  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180075496  lea     r8, [rbp+ppstm]; ppstm
0x18007549a  mov     edx, r15d; fDeleteOnRelease
0x18007549d  xor     ecx, ecx; hGlobal
0x18007549f  call    cs:__imp_CreateStreamOnHGlobal
0x1800754a5  mov     [rbp+var_20], eax
0x1800754a8  test    eax, eax
0x1800754aa  js      short loc_1800754DD
0x1800754ac  mov     [rsp+70h+mshlflags], r15d; mshlflags
0x1800754b1  mov     [rsp+70h+pvDestContext], 0; pvDestContext
0x1800754ba  xor     r9d, r9d; dwDestContext
0x1800754bd  mov     r8, rbx; pUnk
0x1800754c0  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800754c7  mov     rcx, [rbp+ppstm]; pStm
0x1800754cb  call    cs:__imp_CoMarshalInterface
0x1800754d1  mov     [rbp+var_20], eax
0x1800754d4  jmp     short loc_1800754DD
0x1800754d6  mov     [rbp+var_20], 80004002h
0x1800754dd  mov     rcx, [rbp+arg_0]
0x1800754e1  mov     rax, [rcx]
0x1800754e4  mov     r8d, esi
0x1800754e7  mov     rdx, [rbp+pUnk]
0x1800754eb  mov     rax, [rax+18h]
0x1800754ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800754f4  mov     ebx, eax
0x1800754f6  test    eax, eax
0x1800754f8  jns     short loc_180075509
0x1800754fa  xor     r8d, r8d
0x1800754fd  xor     edx, edx
0x1800754ff  mov     ecx, eax
0x180075501  call    cs:__imp_RoTransformError
0x180075507  xor     ebx, ebx
0x180075509  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180075510  test    rcx, rcx
0x180075513  jz      short loc_18007552E
0x180075515  mov     rax, [rcx]
0x180075518  mov     r9d, r15d
0x18007551b  mov     r8d, 2
0x180075521  mov     edx, r15d
0x180075524  mov     rax, [rax+50h]
0x180075528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007552d  nop
0x18007552e  lea     rcx, [rbp+ppstm]
0x180075532  call    ??1?$AutoStubBias@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>(void)
0x180075537  nop
0x180075538  lea     rcx, [rbp+arg_10]
0x18007553c  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180075541  mov     rcx, rdi
0x180075544  call    ?UnlockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@U?$IAsyncOperationProgressHandler@PEAUIBuffer@Streams@Storage@Windows@@I@23@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Storage::Streams::IBuffer *,uint>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(void)
0x180075549  nop
0x18007554a  lea     rcx, [rbp+arg_0]
0x18007554e  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180075553  nop
0x180075554  lea     rcx, [rbp+pUnk]
0x180075558  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18007555d  nop
0x18007555e  lea     rcx, [rbp+var_30]
0x180075562  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180075567  mov     eax, ebx
0x180075569  add     rsp, 70h
0x18007556d  pop     r15
0x18007556f  pop     rdi
0x180075570  pop     rsi
0x180075571  pop     rbx
0x180075572  pop     rbp
0x180075573  retn
```
