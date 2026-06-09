# ATL::CComObject<CDiscoveryResult>::CreateInstance(ATL::CComObject<CDiscoveryResult> * *)

- ea: `0x18000acf8`
- end: `0x18000af4e`
- name: `?CreateInstance@?$CComObject@VCDiscoveryResult@@@ATL@@SAJPEAPEAV12@@Z`
- size: `598`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000a8a0`

## callees

- `0x180006ac4`
- `0x18000725c`
- `0x18000acf8`
- `0x18008d284`
- `0x18009ae75`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000ae5c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000ae5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000aeb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000aeb7`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000aeee`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000aeee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae66`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ad4b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ad4b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ad38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ad38`

## string_xrefs

- `0x18000ae9c`: `C:\__w\1\s\src\Client\comapi\DiscoveryResult.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObject<CDiscoveryResult>::CreateInstance(_QWORD *a1)
{
  unsigned int v3; // r14d
  HANDLE ProcessHeap; // rax
  char *v5; // rax
  char *v6; // rdi
  char *v7; // r12
  __int64 v8; // rdx
  void *v9; // r8
  signed int LastError; // eax
  signed int v11; // ebx
  int FreeThreadedMarshaler; // eax
  __int64 v13; // rdx
  IUnknown *v14; // rax
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = -2147024882;
  ProcessHeap = GetProcessHeap();
  v5 = (char *)HeapAlloc(ProcessHeap, 0, 0x140u);
  v6 = v5;
  if ( v5 )
  {
    memset_0(v5, 0, 0x140u);
    *(_QWORD *)v6 = &CSusBaseAllocTag<1752326505>::`vftable';
    *((_DWORD *)v6 + 56) = 0;
    *(_OWORD *)(v6 + 232) = 0;
    *(_OWORD *)(v6 + 248) = 0;
    *((_QWORD *)v6 + 33) = 0;
    v6[272] = 0;
    *((_QWORD *)v6 + 3) = 0;
    *((_DWORD *)v6 + 8) = 0;
    CSusInternalWrapper::CSusInternalWrapper((CSusInternalWrapper *)(v6 + 40));
    *((_QWORD *)v6 + 35) = 0;
    *((_DWORD *)v6 + 72) = 0;
    *((_QWORD *)v6 + 37) = 0;
    *((_QWORD *)v6 + 38) = 0;
    *((_QWORD *)v6 + 39) = 0;
    *(_QWORD *)v6 = &ATL::CComObject<CDiscoveryResult>::`vftable'{for `CSusBaseAllocTag<1919185763>'};
    *((_QWORD *)v6 + 1) = &ATL::CComObject<CDiscoveryResult>::`vftable'{for `ATL::IDispatchImpl<ISLSDiscoveryResult,&_GUID const IID_ISLSDiscoveryResult,&_GUID const LIBID_WUApiLib,1,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v6 + 2) = &ATL::CComObject<CDiscoveryResult>::`vftable'{for `CXxxResultImpl'};
    *((_QWORD *)v6 + 5) = &ATL::CComObject<CDiscoveryResult>::`vftable'{for `CSusInternalWrapper'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  else
  {
    v6 = 0;
  }
  v7 = v6;
  if ( v6 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v6 + 56);
    if ( !InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v6 + 232), 0, 0) )
    {
      LastError = GetLastError();
      v11 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v11 = LastError;
      if ( v11 < 0 )
        goto LABEL_17;
    }
    v6[272] = 1;
    FreeThreadedMarshaler = SecurityCheck(1, v8, v9);
    v11 = FreeThreadedMarshaler;
    if ( FreeThreadedMarshaler >= 0 )
    {
      v14 = (IUnknown *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
      FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler(v14, (LPUNKNOWN *)v6 + 35);
      v11 = FreeThreadedMarshaler;
      if ( FreeThreadedMarshaler >= 0 )
      {
        v11 = 0;
        goto LABEL_17;
      }
      v13 = 110;
    }
    else
    {
      v13 = 109;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\DiscoveryResult.cpp",
      (const char *)(unsigned int)FreeThreadedMarshaler,
      -2147024882);
    CoTaskMemFree(*((LPVOID *)v6 + 37));
    *((_DWORD *)v6 + 72) = 0;
    *((_QWORD *)v6 + 37) = 0;
    *((_QWORD *)v6 + 38) = 0;
LABEL_17:
    v3 = 0;
    if ( v11 < 0 )
      v3 = v11;
    _InterlockedDecrement((volatile signed __int32 *)v6 + 56);
    if ( v3 )
    {
      (**(void (__fastcall ***)(void *, __int64))v6)(v6, 1);
      v7 = 0;
    }
  }
  *a1 = v7;
  return v3;
}

```

## disassembly

```asm
0x18000acf8  mov     [rsp+arg_8], rbx
0x18000acfd  mov     [rsp+arg_10], rsi
0x18000ad02  mov     [rsp+arg_18], rdi
0x18000ad07  push    r12
0x18000ad09  push    r14
0x18000ad0b  push    r15
0x18000ad0d  sub     rsp, 40h
0x18000ad11  mov     r15, rcx
0x18000ad14  mov     [rsp+58h+var_20], rcx
0x18000ad19  xor     esi, esi
0x18000ad1b  test    rcx, rcx
0x18000ad1e  jnz     short loc_18000AD2A
0x18000ad20  mov     eax, 80004003h
0x18000ad25  jmp     loc_18000AF34
0x18000ad2a  mov     [rcx], rsi
0x18000ad2d  mov     r14d, 8007000Eh
0x18000ad33  mov     [rsp+58h+var_38], r14d
0x18000ad38  call    cs:__imp_GetProcessHeap
0x18000ad3e  mov     ebx, 140h
0x18000ad43  mov     r8d, ebx; dwBytes
0x18000ad46  xor     edx, edx; dwFlags
0x18000ad48  mov     rcx, rax; hHeap
0x18000ad4b  call    cs:__imp_HeapAlloc
0x18000ad51  mov     rdi, rax
0x18000ad54  mov     [rsp+58h+var_28], rax
0x18000ad59  test    rax, rax
0x18000ad5c  jz      loc_18000AE15
0x18000ad62  mov     r8d, ebx; Size
0x18000ad65  xor     edx, edx; Val
0x18000ad67  mov     rcx, rax; void *
0x18000ad6a  call    memset_0
0x18000ad6f  lea     rax, ??_7?$CSusBaseAllocTag@$0GIHCGBGJ@@@6B@; const CSusBaseAllocTag<1752326505>::`vftable'
0x18000ad76  mov     [rdi], rax
0x18000ad79  mov     [rdi+0E0h], esi
0x18000ad7f  xorps   xmm0, xmm0
0x18000ad82  xor     eax, eax
0x18000ad84  movups  xmmword ptr [rdi+0E8h], xmm0
0x18000ad8b  movups  xmmword ptr [rdi+0F8h], xmm0
0x18000ad92  mov     [rdi+108h], rax
0x18000ad99  mov     [rdi+110h], sil
0x18000ada0  mov     [rdi+18h], rsi
0x18000ada4  mov     [rdi+20h], esi
0x18000ada7  lea     rcx, [rdi+28h]; this
0x18000adab  call    ??0CSusInternalWrapper@@QEAA@XZ; CSusInternalWrapper::CSusInternalWrapper(void)
0x18000adb0  nop
0x18000adb1  mov     [rdi+118h], rsi
0x18000adb8  mov     [rdi+120h], esi
0x18000adbe  mov     [rdi+128h], rsi
0x18000adc5  xor     eax, eax
0x18000adc7  mov     [rdi+130h], rax
0x18000adce  mov     [rdi+138h], rsi
0x18000add5  lea     rax, ??_7?$CComObject@VCDiscoveryResult@@@ATL@@6B?$CSusBaseAllocTag@$0HCGEHDGD@@@@; const ATL::CComObject<CDiscoveryResult>::`vftable'{for `CSusBaseAllocTag<1919185763>'}
0x18000addc  mov     [rdi], rax
0x18000addf  lea     rax, ??_7?$CComObject@VCDiscoveryResult@@@ATL@@6B?$IDispatchImpl@UISLSDiscoveryResult@@$1?IID_ISLSDiscoveryResult@@3U_GUID@@B$1?LIBID_WUApiLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CDiscoveryResult>::`vftable'{for `ATL::IDispatchImpl<ISLSDiscoveryResult,&_GUID const IID_ISLSDiscoveryResult,&_GUID const LIBID_WUApiLib,1,0,ATL::CComTypeInfoHolder>'}
0x18000ade6  mov     [rdi+8], rax
0x18000adea  lea     rax, ??_7?$CComObject@VCDiscoveryResult@@@ATL@@6BCXxxResultImpl@@@; const ATL::CComObject<CDiscoveryResult>::`vftable'{for `CXxxResultImpl'}
0x18000adf1  mov     [rdi+10h], rax
0x18000adf5  lea     rax, ??_7?$CComObject@VCDiscoveryResult@@@ATL@@6BCSusInternalWrapper@@@; const ATL::CComObject<CDiscoveryResult>::`vftable'{for `CSusInternalWrapper'}
0x18000adfc  mov     [rdi+28h], rax
0x18000ae00  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000ae07  mov     rax, [rcx]
0x18000ae0a  mov     rax, [rax+8]
0x18000ae0e  call    _guard_dispatch_icall
0x18000ae13  jmp     short loc_18000AE18
0x18000ae15  mov     rdi, rsi
0x18000ae18  mov     [rsp+58h+var_30], rdi
0x18000ae1d  mov     r12, rdi
0x18000ae20  mov     [rsp+58h+var_28], rdi
0x18000ae25  jmp     short loc_18000AE3D
0x18000ae27  xor     esi, esi
0x18000ae29  mov     r14d, [rsp+58h+var_38]
0x18000ae2e  mov     r12, [rsp+58h+var_28]
0x18000ae33  mov     rdi, [rsp+58h+var_30]
0x18000ae38  mov     r15, [rsp+58h+var_20]
0x18000ae3d  test    rdi, rdi
0x18000ae40  jz      loc_18000AF2E
0x18000ae46  lock inc dword ptr [rdi+0E0h]
0x18000ae4d  lea     r14, [rdi+0E8h]
0x18000ae54  xor     r8d, r8d; Flags
0x18000ae57  xor     edx, edx; dwSpinCount
0x18000ae59  mov     rcx, r14; lpCriticalSection
0x18000ae5c  call    cs:__imp_InitializeCriticalSectionEx
0x18000ae62  test    eax, eax
0x18000ae64  jnz     short loc_18000AE82
0x18000ae66  call    cs:__imp_GetLastError
0x18000ae6c  movzx   ebx, ax
0x18000ae6f  or      ebx, 80070000h
0x18000ae75  test    eax, eax
0x18000ae77  cmovle  ebx, eax
0x18000ae7a  test    ebx, ebx
0x18000ae7c  js      loc_18000AF03
0x18000ae82  mov     byte ptr [r14+28h], 1
0x18000ae87  mov     ecx, 1; unsigned int
0x18000ae8c  call    ?SecurityCheck@@YAJK@Z; SecurityCheck(ulong)
0x18000ae91  mov     ebx, eax
0x18000ae93  test    eax, eax
0x18000ae95  jns     short loc_18000AED5
0x18000ae97  mov     edx, 6Dh ; 'm'; void *
0x18000ae9c  lea     r8, aCW1SSrcClientC_28; "C:\\__w\\1\\s\\src\\Client\\comapi\\Dis"...
0x18000aea3  mov     r9d, eax; char *
0x18000aea6  mov     rcx, [rsp+58h]; this
0x18000aeab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aeb0  mov     rcx, [rdi+128h]; pv
0x18000aeb7  call    cs:__imp_CoTaskMemFree
0x18000aebd  mov     [rdi+120h], esi
0x18000aec3  mov     [rdi+128h], rsi
0x18000aeca  xor     eax, eax
0x18000aecc  mov     [rdi+130h], rax
0x18000aed3  jmp     short loc_18000AF03
0x18000aed5  mov     rax, [rdi]
0x18000aed8  mov     rcx, rdi
0x18000aedb  mov     rax, [rax+8]
0x18000aedf  call    _guard_dispatch_icall
0x18000aee4  mov     rcx, rax; punkOuter
0x18000aee7  lea     rdx, [rdi+118h]; ppunkMarshal
0x18000aeee  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000aef4  mov     ebx, eax
0x18000aef6  test    eax, eax
0x18000aef8  jns     short loc_18000AF01
0x18000aefa  mov     edx, 6Eh ; 'n'
0x18000aeff  jmp     short loc_18000AE9C
0x18000af01  mov     ebx, esi
0x18000af03  mov     r14d, esi
0x18000af06  test    ebx, ebx
0x18000af08  cmovs   r14d, ebx
0x18000af0c  lock dec dword ptr [rdi+0E0h]
0x18000af13  test    r14d, r14d
0x18000af16  jz      short loc_18000AF2E
0x18000af18  mov     r8, [rdi]
0x18000af1b  mov     edx, 1
0x18000af20  mov     rcx, rdi
0x18000af23  mov     rax, [r8]
0x18000af26  call    _guard_dispatch_icall
0x18000af2b  mov     r12, rsi
0x18000af2e  mov     [r15], r12
0x18000af31  mov     eax, r14d
0x18000af34  mov     rbx, [rsp+58h+arg_8]
0x18000af39  mov     rsi, [rsp+58h+arg_10]
0x18000af3e  mov     rdi, [rsp+58h+arg_18]
0x18000af43  add     rsp, 40h
0x18000af47  pop     r15
0x18000af49  pop     r14
0x18000af4b  pop     r12
0x18000af4d  retn
```
