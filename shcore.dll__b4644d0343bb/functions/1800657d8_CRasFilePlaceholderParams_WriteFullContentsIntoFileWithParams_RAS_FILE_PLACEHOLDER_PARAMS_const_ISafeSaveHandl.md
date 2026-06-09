# CRasFilePlaceholderParams::_WriteFullContentsIntoFileWithParams(RAS_FILE_PLACEHOLDER_PARAMS const &,ISafeSaveHandleManager *,unsigned __int64,_OVERLAPPED *,bool const volatile &,TransactionType)

- ea: `0x1800657d8`
- end: `0x180065be8`
- name: `?_WriteFullContentsIntoFileWithParams@CRasFilePlaceholderParams@@AEAAJAEBURAS_FILE_PLACEHOLDER_PARAMS@@PEAUISafeSaveHandleManager@@_KPEAU_OVERLAPPED@@AED_NW4TransactionType@@@Z`
- size: `1040`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180065680`
- `0x180079f98`

## callees

- `0x1800083d0`
- `0x18000ddd4`
- `0x180022c90`
- `0x18002314c`
- `0x1800233b4`
- `0x180023730`
- `0x18002ffd0`
- `0x180031cb0`
- `0x18003a89c`
- `0x18003aaa8`
- `0x18003b35c`
- `0x180064f08`
- `0x1800657d8`
- `0x18006d8cc`
- `0x180079690`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180065a8d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180065a8d`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180065ad9`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180065ad9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065b9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065b9a`

## string_xrefs

- `0x180065857`: `onecore\shell\shcore\libs\stream\randomaccessstream.cpp`
- `0x180065932`: `onecore\shell\shcore\libs\stream\randomaccessstream.cpp`
- `0x180065a57`: `onecore\shell\shcore\libs\stream\randomaccessstream.cpp`
- `0x180065aaa`: `onecore\shell\shcore\libs\stream\randomaccessstream.cpp`
- `0x180065af8`: `onecore\shell\shcore\libs\stream\randomaccessstream.cpp`
- `0x180065b55`: `onecore\shell\shcore\libs\stream\randomaccessstream.cpp`
- `0x180065809`: `WriteFullContentsIntoFileWithParams`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CRasFilePlaceholderParams::_WriteFullContentsIntoFileWithParams(
        struct CRasFilePlaceholderParams *a1,
        __int64 a2,
        __int64 a3,
        unsigned __int64 a4,
        LPOVERLAPPED a5,
        bool *a6,
        unsigned int a7)
{
  unsigned __int64 v7; // r14
  __int64 v8; // r15
  int v11; // ebx
  int v12; // eax
  wil::details::in1diag3 *v13; // rcx
  unsigned __int64 v14; // r9
  __int64 v15; // rdx
  unsigned __int64 v16; // rax
  HANDLE v17; // rsi
  void *v18; // rcx
  unsigned int v19; // r10d
  __int64 (__fastcall *v20)(__int64, _QWORD, struct IFileHandle **); // rbx
  int v21; // eax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // rdx
  wil::details::in1diag3 *v24; // rcx
  unsigned __int64 v25; // r9
  __int64 v26; // rdx
  int ShouldContinue; // eax
  int lpOverlapped; // [rsp+28h] [rbp-C1h]
  HANDLE hFile; // [rsp+50h] [rbp-99h] BYREF
  unsigned __int64 v31; // [rsp+58h] [rbp-91h] BYREF
  __int64 v32; // [rsp+60h] [rbp-89h] BYREF
  struct IFileHandle *v33; // [rsp+68h] [rbp-81h] BYREF
  _BYTE v34[8]; // [rsp+78h] [rbp-71h] BYREF
  _BYTE v35[128]; // [rsp+A8h] [rbp-41h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+47h]
  unsigned __int64 v37; // [rsp+140h] [rbp+57h] BYREF
  __int64 v38; // [rsp+148h] [rbp+5Fh]
  unsigned __int64 v39; // [rsp+150h] [rbp+67h]

  v39 = a4;
  v38 = a3;
  v7 = a4;
  v8 = a3;
  StreamLibTelemetry::WatchCurrentThread(v35, "WriteFullContentsIntoFileWithParams");
  v11 = 0;
  if ( !*(_QWORD *)a2 )
    goto LABEL_24;
  v31 = 0;
  v12 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64 *))(**(_QWORD **)(a2 + 8) + 24LL))(
          *(_QWORD *)(a2 + 8),
          &v31);
  v11 = v12;
  v13 = retaddr;
  if ( v12 >= 0 )
  {
    v16 = v31;
    if ( v7 < v31 )
    {
      v16 = v7;
      v31 = v7;
    }
    if ( !v16 )
      goto LABEL_24;
    v17 = 0;
    hFile = 0;
    v37 = 0;
    v11 = ULongLongMult(0x100000u, 1u, &v37);
    if ( v11 >= 0 )
    {
      v11 = CTCoAllocPolicy::Alloc(v18, v19, v37, &hFile);
      v17 = hFile;
    }
    v13 = retaddr;
    if ( v11 < 0 )
    {
      v14 = (unsigned int)v11;
      v15 = 825;
      goto LABEL_4;
    }
    v33 = 0;
    v20 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IFileHandle **))(*(_QWORD *)v8 + 32LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v33);
    v21 = v20(v8, 0, &v33);
    v11 = v21;
    v22 = retaddr;
    if ( v21 < 0 )
    {
      v23 = 829;
LABEL_16:
      wil::details::in1diag3::_Log_Hr(
        v22,
        (void *)v23,
        (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\randomaccessstream.cpp",
        (const char *)(unsigned int)v21,
        lpOverlapped);
      goto LABEL_23;
    }
    hFile = 0;
    v21 = LockHandle(v33, &hFile);
    v11 = v21;
    v22 = retaddr;
    if ( v21 < 0 )
    {
      v23 = 833;
      goto LABEL_16;
    }
    v32 = 0;
    Microsoft::WRL::Wrappers::SRWLock::LockShared(v34, (char *)a1 + 104);
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64, __int64))(**(_QWORD **)(a2 + 8) + 48LL))(
            *(_QWORD *)(a2 + 8),
            0,
            v31,
            1);
    v24 = retaddr;
    if ( v11 >= 0 )
    {
      ShouldContinue = CRasFilePlaceholderParams::s_ShouldContinue(*a6, a1);
      v11 = ShouldContinue;
      v24 = retaddr;
      if ( ShouldContinue >= 0 )
      {
LABEL_22:
        Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)v34);
        (*(void (__fastcall **)(struct IFileHandle *))(*(_QWORD *)v33 + 32LL))(v33);
        v7 = v39;
        v8 = v38;
LABEL_23:
        CoTaskMemFree(v17);
        Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v33);
        if ( v11 < 0 )
          goto LABEL_25;
LABEL_24:
        CRasFilePlaceholderParams::SetLocallyCompleteIfAppropriate(a1, v8, v7, a7);
        goto LABEL_25;
      }
      v25 = (unsigned int)ShouldContinue;
      v26 = 876;
    }
    else
    {
      v25 = (unsigned int)v11;
      v26 = 873;
    }
    wil::details::in1diag3::_Log_Hr(
      v24,
      (void *)v26,
      (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\randomaccessstream.cpp",
      (const char *)v25,
      (int)&v32);
    goto LABEL_22;
  }
  v14 = (unsigned int)v12;
  v15 = 818;
LABEL_4:
  wil::details::in1diag3::_Log_Hr(
    v13,
    (void *)v15,
    (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\randomaccessstream.cpp",
    (const char *)v14,
    lpOverlapped);
LABEL_25:
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v35);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800657d8  mov     rax, rsp
0x1800657db  mov     [rax+8], rbx
0x1800657df  mov     [rax+20h], r9
0x1800657e3  mov     [rax+18h], r8
0x1800657e7  push    rbp
0x1800657e8  push    rsi
0x1800657e9  push    rdi
0x1800657ea  push    r12
0x1800657ec  push    r13
0x1800657ee  push    r14
0x1800657f0  push    r15
0x1800657f2  lea     rbp, [rax-47h]
0x1800657f6  sub     rsp, 0F0h
0x1800657fd  mov     r14, r9
0x180065800  mov     r15, r8
0x180065803  mov     r12, rdx
0x180065806  mov     rdi, rcx
0x180065809  lea     rdx, aWritefullconte_0; "WriteFullContentsIntoFileWithParams"
0x180065810  lea     rcx, [rbp+3Fh+var_80]
0x180065814  call    ?WatchCurrentThread@StreamLibTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; StreamLibTelemetry::WatchCurrentThread(char const *)
0x180065819  nop
0x18006581a  xor     r13d, r13d
0x18006581d  mov     ebx, r13d
0x180065820  cmp     [r12], r13
0x180065824  jz      loc_180065BAF
0x18006582a  mov     [rsp+120h+var_D0], r13
0x18006582f  mov     rcx, [r12+8]
0x180065834  mov     rax, [rcx]
0x180065837  lea     rdx, [rsp+120h+var_D0]
0x18006583c  mov     rax, [rax+18h]
0x180065840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065845  mov     ebx, eax
0x180065847  mov     rcx, [rbp+47h]; this
0x18006584b  test    eax, eax
0x18006584d  jns     short loc_180065868
0x18006584f  mov     r9d, eax; char *
0x180065852  mov     edx, 332h; void *
0x180065857  lea     r8, aOnecoreShellSh_3; "onecore\\shell\\shcore\\libs\\stream\\r"...
0x18006585e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180065863  jmp     loc_180065BC2
0x180065868  mov     rax, [rsp+120h+var_D0]
0x18006586d  cmp     r14, rax
0x180065870  jnb     short loc_18006587A
0x180065872  mov     rax, r14
0x180065875  mov     [rsp+120h+var_D0], rax
0x18006587a  test    rax, rax
0x18006587d  jz      loc_180065BAF
0x180065883  mov     rsi, r13
0x180065886  mov     [rsp+120h+hFile], r13
0x18006588b  mov     [rbp+3Fh+arg_8], r13
0x18006588f  lea     r8, [rbp+3Fh+arg_8]; unsigned __int64 *
0x180065893  mov     r10d, 1
0x180065899  mov     edx, r10d; unsigned __int64
0x18006589c  mov     ecx, 100000h; unsigned __int64
0x1800658a1  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800658a6  mov     ebx, eax
0x1800658a8  test    eax, eax
0x1800658aa  js      short loc_1800658C4
0x1800658ac  lea     r9, [rsp+120h+hFile]; void **
0x1800658b1  mov     r8, [rbp+3Fh+arg_8]; unsigned __int64
0x1800658b5  mov     edx, r10d; unsigned int
0x1800658b8  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800658bd  mov     ebx, eax
0x1800658bf  mov     rsi, [rsp+120h+hFile]
0x1800658c4  mov     rcx, [rbp+47h]
0x1800658c8  test    ebx, ebx
0x1800658ca  jns     short loc_1800658D6
0x1800658cc  mov     r9d, ebx
0x1800658cf  mov     edx, 339h
0x1800658d4  jmp     short loc_180065857
0x1800658d6  mov     [rsp+120h+var_C0], r13
0x1800658db  mov     rax, [r15]
0x1800658de  mov     rbx, [rax+20h]
0x1800658e2  lea     rcx, [rsp+120h+var_C0]
0x1800658e7  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x1800658ec  lea     r8, [rsp+120h+var_C0]
0x1800658f1  xor     edx, edx
0x1800658f3  mov     rcx, r15
0x1800658f6  mov     rax, rbx
0x1800658f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800658fe  mov     ebx, eax
0x180065900  mov     rcx, [rbp+47h]
0x180065904  test    eax, eax
0x180065906  jns     short loc_18006590F
0x180065908  mov     edx, 33Dh
0x18006590d  jmp     short loc_180065932
0x18006590f  mov     [rsp+120h+hFile], r13
0x180065914  lea     rdx, [rsp+120h+hFile]; void **
0x180065919  mov     rcx, [rsp+120h+var_C0]; struct IFileHandle *
0x18006591e  call    ?LockHandle@@YAJPEAUIFileHandle@@PEAPEAX@Z; LockHandle(IFileHandle *,void * *)
0x180065923  mov     ebx, eax
0x180065925  mov     rcx, [rbp+47h]; this
0x180065929  test    eax, eax
0x18006592b  jns     short loc_180065946
0x18006592d  mov     edx, 341h; void *
0x180065932  lea     r8, aOnecoreShellSh_3; "onecore\\shell\\shcore\\libs\\stream\\r"...
0x180065939  mov     r9d, eax; char *
0x18006593c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180065941  jmp     loc_180065B97
0x180065946  mov     [rsp+120h+var_C8], r13
0x18006594b  mov     qword ptr [rsp+120h+nNumberOfBytesToWrite], r13
0x180065950  lea     rax, [rdi+68h]
0x180065954  mov     r14, [rbp+3Fh+arg_20]
0x180065958  mov     rdx, rax
0x18006595b  lea     rcx, [rbp+3Fh+var_B0]
0x18006595f  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x180065964  nop
0x180065965  mov     rcx, [r12+8]
0x18006596a  mov     rax, [rcx]
0x18006596d  lea     rdx, [rsp+120h+nNumberOfBytesToWrite]
0x180065972  mov     qword ptr [rsp+120h+lpOverlapped+8], rdx
0x180065977  lea     rdx, [rsp+120h+var_C8]
0x18006597c  mov     qword ptr [rsp+120h+lpOverlapped], rdx
0x180065981  mov     r9d, 1
0x180065987  mov     r8, [rsp+120h+var_D0]
0x18006598c  xor     edx, edx
0x18006598e  mov     rax, [rax+30h]
0x180065992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065997  mov     ebx, eax
0x180065999  cmp     qword ptr [rsp+120h+nNumberOfBytesToWrite], r13
0x18006599e  jz      loc_180065B23
0x1800659a4  mov     rbx, [rsp+120h+var_D0]
0x1800659a9  mov     r15, [rsp+120h+var_C8]
0x1800659ae  xor     r9d, r9d
0x1800659b1  xor     r8d, r8d
0x1800659b4  lea     rdx, [rbp+3Fh+var_A8]
0x1800659b8  mov     rcx, rdi
0x1800659bb  call    ?_GetParamsUnderLock@CRasFilePlaceholderParams@@AEAA?AURAS_FILE_PLACEHOLDER_PARAMS@@PEA_K0@Z; CRasFilePlaceholderParams::_GetParamsUnderLock(unsigned __int64 *,unsigned __int64 *)
0x1800659c0  nop
0x1800659c1  mov     rcx, [rbp+3Fh+var_90]
0x1800659c5  test    rcx, rcx
0x1800659c8  jz      short loc_1800659E0
0x1800659ca  mov     rax, [rcx]
0x1800659cd  mov     r8, rbx
0x1800659d0  mov     rdx, r15
0x1800659d3  mov     rax, [rax+20h]
0x1800659d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800659dc  mov     ebx, eax
0x1800659de  jmp     short loc_1800659E3
0x1800659e0  mov     ebx, r13d
0x1800659e3  lea     rcx, [rbp+3Fh+var_A8]; this
0x1800659e7  call    ??1RAS_FILE_PLACEHOLDER_PARAMS@@QEAA@XZ; RAS_FILE_PLACEHOLDER_PARAMS::~RAS_FILE_PLACEHOLDER_PARAMS(void)
0x1800659ec  mov     rcx, [rbp+47h]
0x1800659f0  test    ebx, ebx
0x1800659f2  jns     short loc_180065A01
0x1800659f4  mov     r9d, ebx
0x1800659f7  mov     edx, 34Eh
0x1800659fc  jmp     loc_180065AF8
0x180065a01  mov     r15, [rsp+120h+var_C8]
0x180065a06  mov     r13d, dword ptr [rsp+120h+var_C8+4]
0x180065a0b  mov     dword ptr [rbp+3Fh+arg_8], 0
0x180065a12  mov     rcx, [r12]
0x180065a16  mov     rax, [rcx]
0x180065a19  lea     rdx, [rbp+3Fh+arg_8]
0x180065a1d  mov     qword ptr [rsp+120h+lpOverlapped], rdx; int
0x180065a22  mov     r9d, [rsp+120h+nNumberOfBytesToWrite]
0x180065a27  mov     r8, rsi
0x180065a2a  mov     rdx, r15
0x180065a2d  mov     rax, [rax+18h]
0x180065a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065a36  mov     ebx, eax
0x180065a38  test    eax, eax
0x180065a3a  js      short loc_180065A4C
0x180065a3c  mov     rdx, rdi; struct CRasFilePlaceholderParams *
0x180065a3f  mov     rax, [rbp+3Fh+arg_28]
0x180065a43  mov     cl, [rax]; bool
0x180065a45  call    ?s_ShouldContinue@CRasFilePlaceholderParams@@SAJ_NPEAV1@@Z; CRasFilePlaceholderParams::s_ShouldContinue(bool,CRasFilePlaceholderParams *)
0x180065a4a  mov     ebx, eax
0x180065a4c  mov     rcx, [rbp+47h]; this
0x180065a50  test    ebx, ebx
0x180065a52  jns     short loc_180065A70
0x180065a54  mov     r9d, ebx; char *
0x180065a57  lea     r8, aOnecoreShellSh_3; "onecore\\shell\\shcore\\libs\\stream\\r"...
0x180065a5e  mov     edx, 356h; void *
0x180065a63  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180065a68  xor     r13d, r13d
0x180065a6b  jmp     loc_180065B23
0x180065a70  mov     [r14+10h], r15d
0x180065a74  mov     [r14+14h], r13d
0x180065a78  mov     qword ptr [rsp+120h+lpOverlapped], r14; int
0x180065a7d  xor     r9d, r9d; lpNumberOfBytesWritten
0x180065a80  mov     r8d, [rsp+120h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x180065a85  mov     rdx, rsi; lpBuffer
0x180065a88  mov     rcx, [rsp+120h+hFile]; hFile
0x180065a8d  call    cs:__imp_WriteFile
0x180065a93  mov     ecx, eax; int
0x180065a95  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180065a9a  mov     ebx, eax
0x180065a9c  mov     rcx, [rbp+47h]; this
0x180065aa0  xor     r13d, r13d
0x180065aa3  test    eax, eax
0x180065aa5  jns     short loc_180065AC3
0x180065aa7  mov     r9d, eax; char *
0x180065aaa  lea     r8, aOnecoreShellSh_3; "onecore\\shell\\shcore\\libs\\stream\\r"...
0x180065ab1  mov     edx, 35Bh; void *
0x180065ab6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180065abb  cmp     ebx, 800703E5h
0x180065ac1  jnz     short loc_180065B23
0x180065ac3  mov     [rbp+3Fh+NumberOfBytesTransferred], r13d
0x180065ac7  mov     r9d, 1; bWait
0x180065acd  lea     r8, [rbp+3Fh+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180065ad1  mov     rdx, r14; lpOverlapped
0x180065ad4  mov     rcx, [rsp+120h+hFile]; hFile
0x180065ad9  call    cs:__imp_GetOverlappedResult
0x180065adf  mov     ecx, eax; int
0x180065ae1  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180065ae6  mov     ebx, eax
0x180065ae8  mov     rcx, [rbp+47h]; this
0x180065aec  test    eax, eax
0x180065aee  jns     short loc_180065B06
0x180065af0  mov     r9d, eax; char *
0x180065af3  mov     edx, 35Fh; void *
0x180065af8  lea     r8, aOnecoreShellSh_3; "onecore\\shell\\shcore\\libs\\stream\\r"...
0x180065aff  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180065b04  jmp     short loc_180065B23
0x180065b06  mov     rcx, [r12+8]
0x180065b0b  mov     rax, [rcx]
0x180065b0e  mov     r8, qword ptr [rsp+120h+nNumberOfBytesToWrite]
0x180065b13  mov     rdx, [rsp+120h+var_C8]
0x180065b18  mov     rax, [rax+38h]
0x180065b1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065b21  mov     ebx, eax
0x180065b23  mov     rcx, [rbp+47h]
0x180065b27  test    ebx, ebx
0x180065b29  jns     short loc_180065B35
0x180065b2b  mov     r9d, ebx
0x180065b2e  mov     edx, 369h
0x180065b33  jmp     short loc_180065B55
0x180065b35  mov     rdx, rdi; struct CRasFilePlaceholderParams *
0x180065b38  mov     rax, [rbp+3Fh+arg_28]
0x180065b3c  mov     cl, [rax]; bool
0x180065b3e  call    ?s_ShouldContinue@CRasFilePlaceholderParams@@SAJ_NPEAV1@@Z; CRasFilePlaceholderParams::s_ShouldContinue(bool,CRasFilePlaceholderParams *)
0x180065b43  mov     ebx, eax
0x180065b45  mov     rcx, [rbp+47h]; this
0x180065b49  test    eax, eax
0x180065b4b  jns     short loc_180065B62
0x180065b4d  mov     r9d, eax; char *
0x180065b50  mov     edx, 36Ch; void *
0x180065b55  lea     r8, aOnecoreShellSh_3; "onecore\\shell\\shcore\\libs\\stream\\r"...
0x180065b5c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180065b61  nop
0x180065b62  lea     rcx, [rbp+3Fh+var_B0]; this
0x180065b66  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x180065b6b  test    ebx, ebx
0x180065b6d  js      short loc_180065B7E
0x180065b6f  cmp     qword ptr [rsp+120h+nNumberOfBytesToWrite], r13
0x180065b74  lea     rax, [rdi+68h]
0x180065b78  jnz     loc_180065958
0x180065b7e  mov     rcx, [rsp+120h+var_C0]
0x180065b83  mov     rax, [rcx]
0x180065b86  mov     rax, [rax+20h]
0x180065b8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065b8f  mov     r14, [rbp+3Fh+arg_18]
0x180065b93  mov     r15, [rbp+3Fh+arg_10]
0x180065b97  mov     rcx, rsi; pv
0x180065b9a  call    cs:__imp_CoTaskMemFree
0x180065ba0  nop
0x180065ba1  lea     rcx, [rsp+120h+var_C0]
0x180065ba6  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180065bab  test    ebx, ebx
0x180065bad  js      short loc_180065BC2
0x180065baf  mov     r9d, [rbp+3Fh+arg_30]
0x180065bb3  mov     r8, r14
0x180065bb6  mov     rdx, r15
0x180065bb9  mov     rcx, rdi
0x180065bbc  call    ?SetLocallyCompleteIfAppropriate@CRasFilePlaceholderParams@@QEAAJPEAUISafeSaveHandleManager@@_KW4TransactionType@@@Z; CRasFilePlaceholderParams::SetLocallyCompleteIfAppropriate(ISafeSaveHandleManager *,unsigned __int64,TransactionType)
0x180065bc1  nop
0x180065bc2  lea     rcx, [rbp+3Fh+var_80]; this
0x180065bc6  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x180065bcb  mov     eax, ebx
0x180065bcd  mov     rbx, [rsp+120h+arg_0]
0x180065bd5  add     rsp, 0F0h
0x180065bdc  pop     r15
0x180065bde  pop     r14
0x180065be0  pop     r13
0x180065be2  pop     r12
0x180065be4  pop     rdi
0x180065be5  pop     rsi
0x180065be6  pop     rbp
0x180065be7  retn
```
