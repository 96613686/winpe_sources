# ATL::CComCreator<ATL::CComObject<CIdleBackgroundCopyCallback>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800782bc`
- end: `0x1800784d1`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCIdleBackgroundCopyCallback@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `533`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800775f0`

## callees

- `0x180006ac4`
- `0x18000725c`
- `0x1800782bc`
- `0x18009ae75`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18007840a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18007840a`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18007844a`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18007844a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078414`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078414`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078311`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078311`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800782fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800782fe`

## string_xrefs

- `0x18007845e`: `C:\__w\1\s\src\Client\comapi\IdleBackgroundCopyCallback.cpp`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CIdleBackgroundCopyCallback>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // r14d
  HANDLE ProcessHeap; // rax
  char *v8; // rax
  char *v9; // rdi
  signed int LastError; // eax
  signed int v11; // ebx
  IUnknown *v12; // rax
  HRESULT FreeThreadedMarshaler; // eax
  int v14; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  ProcessHeap = GetProcessHeap();
  v8 = (char *)HeapAlloc(ProcessHeap, 0, 0x120u);
  v9 = v8;
  if ( v8 )
  {
    memset_0(v8, 0, 0x120u);
    *(_QWORD *)v9 = &CSusBaseAllocTag<1752326505>::`vftable';
    *((_DWORD *)v9 + 54) = 0;
    *((_OWORD *)v9 + 14) = 0;
    *((_OWORD *)v9 + 15) = 0;
    *((_QWORD *)v9 + 32) = 0;
    v9[264] = 0;
    *((_DWORD *)v9 + 4) = -1;
    CSusInternalWrapper::CSusInternalWrapper((CSusInternalWrapper *)(v9 + 32));
    *((_DWORD *)v9 + 68) = 0;
    *((_QWORD *)v9 + 35) = 0;
    *(_QWORD *)v9 = &ATL::CComObject<CIdleBackgroundCopyCallback>::`vftable'{for `CSusBaseAllocTag<1768055651>'};
    *((_QWORD *)v9 + 1) = &ATL::CComObject<CIdleBackgroundCopyCallback>::`vftable'{for `CUpdateLockdown'};
    *((_QWORD *)v9 + 3) = &ATL::CComObject<CIdleBackgroundCopyCallback>::`vftable'{for `IBackgroundCopyCallback'};
    *((_QWORD *)v9 + 4) = &ATL::CComObject<CIdleBackgroundCopyCallback>::`vftable'{for `CSusInternalWrapper'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  else
  {
    v9 = 0;
  }
  if ( v9 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v9 + 54);
    if ( InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v9 + 224), 0, 0) )
      goto LABEL_11;
    LastError = GetLastError();
    v11 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v11 = LastError;
    if ( v11 >= 0 )
    {
LABEL_11:
      v9[264] = 1;
      v12 = (IUnknown *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v9 + 8LL))(v9);
      FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler(v12, (LPUNKNOWN *)v9 + 35);
      v11 = FreeThreadedMarshaler;
      if ( FreeThreadedMarshaler >= 0 )
      {
        *((_DWORD *)v9 + 68) = 1;
        v11 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6E,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\IdleBackgroundCopyCallback.cpp",
          (const char *)(unsigned int)FreeThreadedMarshaler,
          v14);
      }
    }
    v6 = 0;
    if ( v11 < 0 )
      v6 = v11;
    _InterlockedDecrement((volatile signed __int32 *)v9 + 54);
    if ( v6 || (v6 = (**((__int64 (__fastcall ***)(__int64, __int64, _QWORD *))v9 + 1))((__int64)(v9 + 8), a2, a3)) != 0 )
      (**(void (__fastcall ***)(void *, __int64))v9)(v9, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x1800782bc  mov     [rsp+arg_10], r8
0x1800782c1  mov     [rsp+arg_8], rdx
0x1800782c6  mov     [rsp+arg_0], rcx
0x1800782cb  push    rbx
0x1800782cc  push    rdi
0x1800782cd  push    r12
0x1800782cf  push    r14
0x1800782d1  push    r15
0x1800782d3  sub     rsp, 20h
0x1800782d7  mov     r15, r8
0x1800782da  mov     r12, rdx
0x1800782dd  test    r8, r8
0x1800782e0  jnz     short loc_1800782EC
0x1800782e2  mov     eax, 80004003h
0x1800782e7  jmp     loc_1800784C4
0x1800782ec  mov     qword ptr [r8], 0
0x1800782f3  mov     r14d, 8007000Eh
0x1800782f9  mov     dword ptr [rsp+48h+arg_0], r14d
0x1800782fe  call    cs:__imp_GetProcessHeap
0x180078304  mov     ebx, 120h
0x180078309  mov     r8d, ebx; dwBytes
0x18007830c  xor     edx, edx; dwFlags
0x18007830e  mov     rcx, rax; hHeap
0x180078311  call    cs:__imp_HeapAlloc
0x180078317  mov     rdi, rax
0x18007831a  mov     [rsp+48h+arg_18], rax
0x18007831f  test    rax, rax
0x180078322  jz      loc_1800783CE
0x180078328  mov     r8d, ebx; Size
0x18007832b  xor     edx, edx; Val
0x18007832d  mov     rcx, rax; void *
0x180078330  call    memset_0
0x180078335  lea     rax, ??_7?$CSusBaseAllocTag@$0GIHCGBGJ@@@6B@; const CSusBaseAllocTag<1752326505>::`vftable'
0x18007833c  mov     [rdi], rax
0x18007833f  mov     dword ptr [rdi+0D8h], 0
0x180078349  xorps   xmm0, xmm0
0x18007834c  xor     eax, eax
0x18007834e  movups  xmmword ptr [rdi+0E0h], xmm0
0x180078355  movups  xmmword ptr [rdi+0F0h], xmm0
0x18007835c  mov     [rdi+100h], rax
0x180078363  mov     [rdi+108h], al
0x180078369  mov     dword ptr [rdi+10h], 0FFFFFFFFh
0x180078370  lea     rcx, [rdi+20h]; this
0x180078374  call    ??0CSusInternalWrapper@@QEAA@XZ; CSusInternalWrapper::CSusInternalWrapper(void)
0x180078379  mov     dword ptr [rdi+110h], 0
0x180078383  mov     qword ptr [rdi+118h], 0
0x18007838e  lea     rax, ??_7?$CComObject@VCIdleBackgroundCopyCallback@@@ATL@@6B?$CSusBaseAllocTag@$0GJGCGDGD@@@@; const ATL::CComObject<CIdleBackgroundCopyCallback>::`vftable'{for `CSusBaseAllocTag<1768055651>'}
0x180078395  mov     [rdi], rax
0x180078398  lea     rax, ??_7?$CComObject@VCIdleBackgroundCopyCallback@@@ATL@@6BCUpdateLockdown@@@; const ATL::CComObject<CIdleBackgroundCopyCallback>::`vftable'{for `CUpdateLockdown'}
0x18007839f  mov     [rdi+8], rax
0x1800783a3  lea     rax, ??_7?$CComObject@VCIdleBackgroundCopyCallback@@@ATL@@6BIBackgroundCopyCallback@@@; const ATL::CComObject<CIdleBackgroundCopyCallback>::`vftable'{for `IBackgroundCopyCallback'}
0x1800783aa  mov     [rdi+18h], rax
0x1800783ae  lea     rax, ??_7?$CComObject@VCIdleBackgroundCopyCallback@@@ATL@@6BCSusInternalWrapper@@@; const ATL::CComObject<CIdleBackgroundCopyCallback>::`vftable'{for `CSusInternalWrapper'}
0x1800783b5  mov     [rdi+20h], rax
0x1800783b9  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800783c0  mov     rax, [rcx]
0x1800783c3  mov     rax, [rax+8]
0x1800783c7  call    _guard_dispatch_icall
0x1800783cc  jmp     short loc_1800783D0
0x1800783ce  xor     edi, edi
0x1800783d0  mov     [rsp+48h+arg_18], rdi
0x1800783d5  jmp     short loc_1800783EB
0x1800783d7  mov     r15, [rsp+48h+arg_10]
0x1800783dc  mov     r12, [rsp+48h+arg_8]
0x1800783e1  mov     r14d, dword ptr [rsp+48h+arg_0]
0x1800783e6  mov     rdi, [rsp+48h+arg_18]
0x1800783eb  test    rdi, rdi
0x1800783ee  jz      loc_1800784C1
0x1800783f4  lock inc dword ptr [rdi+0D8h]
0x1800783fb  lea     r14, [rdi+0E0h]
0x180078402  xor     r8d, r8d; Flags
0x180078405  xor     edx, edx; dwSpinCount
0x180078407  mov     rcx, r14; lpCriticalSection
0x18007840a  call    cs:__imp_InitializeCriticalSectionEx
0x180078410  test    eax, eax
0x180078412  jnz     short loc_18007842C
0x180078414  call    cs:__imp_GetLastError
0x18007841a  movzx   ebx, ax
0x18007841d  or      ebx, 80070000h
0x180078423  test    eax, eax
0x180078425  cmovle  ebx, eax
0x180078428  test    ebx, ebx
0x18007842a  js      short loc_18007847D
0x18007842c  mov     byte ptr [r14+28h], 1
0x180078431  mov     rax, [rdi]
0x180078434  mov     rcx, rdi
0x180078437  mov     rax, [rax+8]
0x18007843b  call    _guard_dispatch_icall
0x180078440  lea     rdx, [rdi+118h]; ppunkMarshal
0x180078447  mov     rcx, rax; punkOuter
0x18007844a  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180078450  mov     ebx, eax
0x180078452  test    eax, eax
0x180078454  jns     short loc_180078471
0x180078456  mov     rcx, [rsp+48h]; this
0x18007845b  mov     r9d, eax; char *
0x18007845e  lea     r8, aCW1SSrcClientC_24; "C:\\__w\\1\\s\\src\\Client\\comapi\\Idl"...
0x180078465  mov     edx, 6Eh ; 'n'; void *
0x18007846a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007846f  jmp     short loc_18007847D
0x180078471  mov     dword ptr [rdi+110h], 1
0x18007847b  xor     ebx, ebx
0x18007847d  xor     r14d, r14d
0x180078480  test    ebx, ebx
0x180078482  cmovs   r14d, ebx
0x180078486  lock dec dword ptr [rdi+0D8h]
0x18007848d  test    r14d, r14d
0x180078490  jnz     short loc_1800784AE
0x180078492  lea     rcx, [rdi+8]
0x180078496  mov     rax, [rcx]
0x180078499  mov     r8, r15
0x18007849c  mov     rdx, r12
0x18007849f  mov     rax, [rax]
0x1800784a2  call    _guard_dispatch_icall
0x1800784a7  mov     r14d, eax
0x1800784aa  test    eax, eax
0x1800784ac  jz      short loc_1800784C1
0x1800784ae  mov     r8, [rdi]
0x1800784b1  mov     edx, 1
0x1800784b6  mov     rcx, rdi
0x1800784b9  mov     rax, [r8]
0x1800784bc  call    _guard_dispatch_icall
0x1800784c1  mov     eax, r14d
0x1800784c4  add     rsp, 20h
0x1800784c8  pop     r15
0x1800784ca  pop     r14
0x1800784cc  pop     r12
0x1800784ce  pop     rdi
0x1800784cf  pop     rbx
0x1800784d0  retn
```
