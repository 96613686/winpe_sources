# CUmRdpDr::Initialize(void)

- ea: `0x180011850`
- end: `0x180011c38`
- name: `?Initialize@CUmRdpDr@@QEAAHXZ`
- size: `1000`
- prototype: `__int64 __fastcall(CUmRdpDr *__hidden this)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a5cc`
- `0x18000e5c0`

## callees

- `0x180008f20`
- `0x1800090b0`
- `0x180009108`
- `0x18000ae30`
- `0x18000e784`
- `0x18001036c`
- `0x180011580`
- `0x180011850`
- `0x180011c40`
- `0x180012be8`
- `0x1800130e8`
- `0x1800139d8`
- `0x180015428`
- `0x180018580`
- `0x1800197e8`
- `0x180047ebe`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ba6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011bae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ba6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011bae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800118ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011c21`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800118ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011c21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011bbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011c12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011bbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011c12`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011a11`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011a78`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011a98`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011a11`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011a78`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011a98`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180011afb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180011afb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011be2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011be2`
- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x180011b40`
- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x180011b40`
- `KERNEL32!VerifyVersionInfoW` at `0x180011b56`
- `KERNEL32!VerifyVersionInfoW` at `0x180011b79`
- `KERNEL32!VerifyVersionInfoW` at `0x180011b56`
- `KERNEL32!VerifyVersionInfoW` at `0x180011b79`

## pseudocode

```c
__int64 __fastcall CUmRdpDr::Initialize(CUmRdpDr *this)
{
  int IsProtocolRDP; // eax
  void *v4; // r8
  unsigned int LastError; // ebx
  char *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  char *v10; // rsi
  unsigned int v11; // esi
  CUmRdpDr *v12; // rcx
  HANDLE EventW; // rax
  unsigned int v14; // eax
  unsigned int v15; // ecx
  HANDLE v16; // rax
  HANDLE v17; // rax
  SIZE_T v18; // rdx
  unsigned int v19; // eax
  HANDLE Thread; // rax
  ULONGLONG v21; // rbx
  BOOL v22; // r14d
  DWORD v23; // eax
  void *v24; // r8
  void *v25; // rcx
  struct _OSVERSIONINFOEXW VersionInformation; // [rsp+30h] [rbp-168h] BYREF

  if ( *((_DWORD *)this + 505) )
  {
    CUmRdpPrn::ReadPrinterDriverPolicy((CUmRdpDr *)((char *)this + 24));
    return 1;
  }
  IsProtocolRDP = TSNUTL_IsProtocolRDP(*(_DWORD *)this);
  v4 = (void *)*((_QWORD *)this + 1);
  *((_DWORD *)this + 506) = IsProtocolRDP;
  CUmRdpDrv::Initialize((CUmRdpDr *)((char *)this + 880), this, v4);
  if ( !*((_DWORD *)this + 506) || *((_DWORD *)this + 505) )
    return 1;
  if ( *((_QWORD *)this + 248) )
  {
    SetLastError(0x4DFu);
    return 0;
  }
  *((_DWORD *)this + 542) = 0;
  LastError = 0;
  CUmRdpDr::GetUserSettings(this);
  *((_QWORD *)this + 254) = 0;
  *((_QWORD *)this + 255) = 0;
  v6 = (char *)ALLOCMEM(0x608u);
  v10 = v6;
  if ( v6 )
  {
    *((_DWORD *)v6 + 384) = 0;
    memset_0(v6 + 512, 0, 0x200u);
    memset_0(v10, 0, 0x200u);
    memset_0(v10 + 1024, 0, 0x200u);
  }
  *((_QWORD *)this + 250) = v10;
  if ( !v10 )
  {
    v11 = 0;
LABEL_14:
    TsLogError(&EVENT_NOTIFY_INSUFFICIENTRESOURCES, 0, 0, v9);
    goto LABEL_23;
  }
  v11 = 1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl'::`2'::impl,
                          v7,
                          v8,
                          v9) )
  {
    v11 = CUmRdpDr::InitializeDedicatedThreads(this);
    if ( !v11 )
      goto LABEL_14;
  }
  CUmRdpPrn::Initialize(
    (CUmRdpDr *)((char *)this + 24),
    this,
    (CUmRdpDr *)((char *)this + 2032),
    *((void **)this + 250),
    *((HANDLE *)this + 1));
  if ( !(unsigned int)CUmRdpDr::ResizeBuffer(v12, (void **)this + 269, 0xCu, (unsigned int *)this + 540) )
  {
    GetLastError();
LABEL_22:
    v11 = 0;
    goto LABEL_23;
  }
  *(_OWORD *)((char *)this + 2088) = 0;
  *(_OWORD *)((char *)this + 2104) = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 264) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    goto LABEL_22;
  }
  v14 = WTBLOBJ_AddWaitableObject(
          *((void **)this + 250),
          this,
          EventW,
          (void (*)(void *, void *))CUmRdpDr::staticGetNextEvtOverlappedSignaled);
  v15 = 0;
  LastError = v14;
  if ( !v14 )
    v15 = v11;
  v11 = v15;
LABEL_23:
  *(_OWORD *)((char *)this + 2120) = 0;
  *(_OWORD *)((char *)this + 2136) = 0;
  if ( !v11 )
    goto LABEL_36;
  v16 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 268) = v16;
  if ( !v16 || (v17 = CreateEventW(0, 1, 0, 0), (*((_QWORD *)this + 251) = v17) == 0) )
  {
    v23 = GetLastError();
    v11 = 0;
    goto LABEL_35;
  }
  LastError = WTBLOBJ_AddWaitableObject(*((void **)this + 250), 0, v17, guard_check_icall_nop);
  v19 = 0;
  if ( !LastError )
    v19 = v11;
  v11 = v19;
  if ( !v19 )
  {
LABEL_36:
    CloseHandle(*((HANDLE *)this + 1));
    v24 = (void *)*((_QWORD *)this + 269);
    *((_QWORD *)this + 1) = 0;
    if ( v24 )
    {
      HeapFree(NtCurrentPeb()->ProcessHeap, 0, v24);
      *((_QWORD *)this + 269) = 0;
      *((_DWORD *)this + 540) = 0;
    }
    CUmRdpDr::Shutdown(this);
    CUmRdpDr::CloseWaitableObjects(this);
    v25 = (void *)*((_QWORD *)this + 248);
    if ( v25 )
    {
      CloseHandle(v25);
      *((_QWORD *)this + 248) = 0;
    }
    SetLastError(LastError);
    if ( !v11 )
      return v11;
    goto LABEL_41;
  }
  _InterlockedAdd((volatile signed __int32 *)this + 4, 1u);
  Thread = CreateThread(0, v18, CUmRdpDr::staticBackgroundThread, this, 0, (LPDWORD)this + 498);
  *((_QWORD *)this + 248) = Thread;
  if ( !Thread )
  {
    v11 = 0;
    CUmRdpDr::Release(this);
    v23 = GetLastError();
LABEL_35:
    LastError = v23;
    goto LABEL_36;
  }
  v11 = 1;
  memset_0(&VersionInformation, 0, sizeof(VersionInformation));
  VersionInformation.dwOSVersionInfoSize = 284;
  VersionInformation.wSuiteMask = 16;
  v21 = VerSetConditionMask(0, 0x40u, 6u);
  v22 = VerifyVersionInfoW(&VersionInformation, 0x40u, v21);
  VersionInformation.wSuiteMask = 256;
  if ( VerifyVersionInfoW(&VersionInformation, 0x40u, v21) && !v22 )
    fRunningOnPTS = 1;
LABEL_41:
  *((_DWORD *)this + 505) = 1;
  return v11;
}

```

## disassembly

```asm
0x180011850  push    rbx
0x180011852  push    rbp
0x180011853  push    rsi
0x180011854  push    rdi
0x180011855  push    r12
0x180011857  push    r14
0x180011859  sub     rsp, 168h
0x180011860  mov     rax, cs:__security_cookie
0x180011867  xor     rax, rsp
0x18001186a  mov     [rsp+198h+var_48], rax
0x180011872  xor     r12d, r12d
0x180011875  mov     rdi, rcx
0x180011878  cmp     [rcx+7E4h], r12d
0x18001187f  jz      short loc_1800118AF
0x180011881  add     rcx, 18h; this
0x180011885  call    ?ReadPrinterDriverPolicy@CUmRdpPrn@@QEAAXXZ; CUmRdpPrn::ReadPrinterDriverPolicy(void)
0x18001188a  mov     eax, 1
0x18001188f  mov     rcx, [rsp+198h+var_48]
0x180011897  xor     rcx, rsp; StackCookie
0x18001189a  call    __security_check_cookie
0x18001189f  add     rsp, 168h
0x1800118a6  pop     r14
0x1800118a8  pop     r12
0x1800118aa  pop     rdi
0x1800118ab  pop     rsi
0x1800118ac  pop     rbp
0x1800118ad  pop     rbx
0x1800118ae  retn
0x1800118af  mov     ecx, [rcx]; unsigned int
0x1800118b1  call    ?TSNUTL_IsProtocolRDP@@YAHK@Z; TSNUTL_IsProtocolRDP(ulong)
0x1800118b6  mov     r8, [rdi+8]; void *
0x1800118ba  lea     rcx, [rdi+370h]; this
0x1800118c1  mov     rdx, rdi; struct CUmRdpDr *
0x1800118c4  mov     [rdi+7E8h], eax
0x1800118ca  call    ?Initialize@CUmRdpDrv@@QEAAHPEAVCUmRdpDr@@PEAX@Z; CUmRdpDrv::Initialize(CUmRdpDr *,void *)
0x1800118cf  cmp     [rdi+7E8h], r12d
0x1800118d6  jz      short loc_18001188A
0x1800118d8  cmp     [rdi+7E4h], r12d
0x1800118df  jnz     short loc_18001188A
0x1800118e1  cmp     [rdi+7C0h], r12
0x1800118e8  jz      short loc_1800118F9
0x1800118ea  mov     ecx, 4DFh; dwErrCode
0x1800118ef  call    cs:__imp_SetLastError
0x1800118f5  xor     eax, eax
0x1800118f7  jmp     short loc_18001188F
0x1800118f9  mov     rcx, rdi; this
0x1800118fc  mov     [rdi+878h], r12d
0x180011903  mov     ebx, r12d
0x180011906  call    ?GetUserSettings@CUmRdpDr@@AEAAXXZ; CUmRdpDr::GetUserSettings(void)
0x18001190b  lea     r14, [rdi+7F0h]
0x180011912  mov     ecx, 608h; dwBytes
0x180011917  mov     [r14], r12
0x18001191a  mov     [r14+8], r12
0x18001191e  call    ?ALLOCMEM@@YAPEAX_K@Z; ALLOCMEM(unsigned __int64)
0x180011923  mov     rsi, rax
0x180011926  test    rax, rax
0x180011929  jz      short loc_180011966
0x18001192b  mov     ebp, 200h
0x180011930  mov     [rax+600h], r12d
0x180011937  mov     r8d, ebp; Size
0x18001193a  lea     rcx, [rax+200h]; void *
0x180011941  xor     edx, edx; Val
0x180011943  call    memset_0
0x180011948  mov     r8d, ebp; Size
0x18001194b  xor     edx, edx; Val
0x18001194d  mov     rcx, rsi; void *
0x180011950  call    memset_0
0x180011955  lea     rcx, [rsi+400h]; void *
0x18001195c  mov     r8d, ebp; Size
0x18001195f  xor     edx, edx; Val
0x180011961  call    memset_0
0x180011966  mov     [rdi+7D0h], rsi
0x18001196d  mov     ebp, 1
0x180011972  test    rsi, rsi
0x180011975  jnz     short loc_18001197C
0x180011977  mov     esi, r12d
0x18001197a  jmp     short loc_18001199C
0x18001197c  mov     esi, ebp
0x18001197e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock> `wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl(void)'::`2'::impl
0x180011985  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(void)
0x18001198a  test    al, al
0x18001198c  jz      short loc_1800119B2
0x18001198e  mov     rcx, rdi; this
0x180011991  call    ?InitializeDedicatedThreads@CUmRdpDr@@AEAAHXZ; CUmRdpDr::InitializeDedicatedThreads(void)
0x180011996  mov     esi, eax
0x180011998  test    eax, eax
0x18001199a  jnz     short loc_1800119B2
0x18001199c  xor     r8d, r8d; unsigned __int16 **
0x18001199f  lea     rcx, EVENT_NOTIFY_INSUFFICIENTRESOURCES; struct _EVENT_DESCRIPTOR *
0x1800119a6  xor     edx, edx; int
0x1800119a8  call    ?TsLogError@@YAXAEBU_EVENT_DESCRIPTOR@@HQEAPEAGK@Z; TsLogError(_EVENT_DESCRIPTOR const &,int,ushort * * const,ulong)
0x1800119ad  jmp     loc_180011A55
0x1800119b2  mov     rax, [rdi+8]
0x1800119b6  lea     rcx, [rdi+18h]; this
0x1800119ba  mov     r9, [rdi+7D0h]; void *
0x1800119c1  mov     r8, r14; struct tagDRDEVLST *
0x1800119c4  mov     rdx, rdi; struct CUmRdpDr *
0x1800119c7  mov     qword ptr [rsp+198h+dwCreationFlags], rax; void *
0x1800119cc  call    ?Initialize@CUmRdpPrn@@QEAAHPEAVCUmRdpDr@@PEAUtagDRDEVLST@@PEAX2@Z; CUmRdpPrn::Initialize(CUmRdpDr *,tagDRDEVLST *,void *,void *)
0x1800119d1  lea     r9, [rdi+870h]; unsigned int *
0x1800119d8  mov     r8d, 0Ch; unsigned int
0x1800119de  lea     rdx, [rdi+868h]; void **
0x1800119e5  call    ?ResizeBuffer@CUmRdpDr@@QEAAHPEAPEAXKPEAK@Z; CUmRdpDr::ResizeBuffer(void * *,ulong,ulong *)
0x1800119ea  test    eax, eax
0x1800119ec  jnz     short loc_1800119F6
0x1800119ee  call    cs:__imp_GetLastError
0x1800119f4  jmp     short loc_180011A52
0x1800119f6  xorps   xmm0, xmm0
0x1800119f9  xor     r9d, r9d; lpName
0x1800119fc  movups  xmmword ptr [rdi+828h], xmm0
0x180011a03  xor     r8d, r8d; bInitialState
0x180011a06  mov     edx, ebp; bManualReset
0x180011a08  xor     ecx, ecx; lpEventAttributes
0x180011a0a  movups  xmmword ptr [rdi+838h], xmm0
0x180011a11  call    cs:__imp_CreateEventW
0x180011a17  mov     [rdi+840h], rax
0x180011a1e  test    rax, rax
0x180011a21  jz      short loc_180011A4A
0x180011a23  mov     rcx, [rdi+7D0h]; void *
0x180011a2a  lea     r9, ?staticGetNextEvtOverlappedSignaled@CUmRdpDr@@CAXPEAX0@Z; void (*)(void *, void *)
0x180011a31  mov     r8, rax; void *
0x180011a34  mov     rdx, rdi; void *
0x180011a37  call    ?WTBLOBJ_AddWaitableObject@@YAKPEAX00P6AX00@Z@Z; WTBLOBJ_AddWaitableObject(void *,void *,void *,void (*)(void *,void *))
0x180011a3c  test    eax, eax
0x180011a3e  mov     ecx, r12d
0x180011a41  mov     ebx, eax
0x180011a43  cmovz   ecx, esi
0x180011a46  mov     esi, ecx
0x180011a48  jmp     short loc_180011A55
0x180011a4a  call    cs:__imp_GetLastError
0x180011a50  mov     ebx, eax
0x180011a52  mov     esi, r12d
0x180011a55  xorps   xmm0, xmm0
0x180011a58  movups  xmmword ptr [rdi+848h], xmm0
0x180011a5f  movups  xmmword ptr [rdi+858h], xmm0
0x180011a66  test    esi, esi
0x180011a68  jz      loc_180011BB9
0x180011a6e  xor     r9d, r9d; lpName
0x180011a71  xor     r8d, r8d; bInitialState
0x180011a74  xor     edx, edx; bManualReset
0x180011a76  xor     ecx, ecx; lpEventAttributes
0x180011a78  call    cs:__imp_CreateEventW
0x180011a7e  mov     [rdi+860h], rax
0x180011a85  test    rax, rax
0x180011a88  jz      loc_180011BAE
0x180011a8e  xor     r9d, r9d; lpName
0x180011a91  xor     r8d, r8d; bInitialState
0x180011a94  mov     edx, ebp; bManualReset
0x180011a96  xor     ecx, ecx; lpEventAttributes
0x180011a98  call    cs:__imp_CreateEventW
0x180011a9e  mov     [rdi+7D8h], rax
0x180011aa5  test    rax, rax
0x180011aa8  jz      loc_180011BAE
0x180011aae  mov     rcx, [rdi+7D0h]; void *
0x180011ab5  lea     r9, _guard_check_icall_nop; void (*)(void *, void *)
0x180011abc  mov     r8, rax; void *
0x180011abf  xor     edx, edx; void *
0x180011ac1  call    ?WTBLOBJ_AddWaitableObject@@YAKPEAX00P6AX00@Z@Z; WTBLOBJ_AddWaitableObject(void *,void *,void *,void (*)(void *,void *))
0x180011ac6  mov     ebx, eax
0x180011ac8  mov     eax, r12d
0x180011acb  test    ebx, ebx
0x180011acd  cmovz   eax, esi
0x180011ad0  mov     esi, eax
0x180011ad2  test    eax, eax
0x180011ad4  jz      loc_180011BB9
0x180011ada  lock add [rdi+10h], ebp
0x180011ade  lea     rax, [rdi+7C8h]
0x180011ae5  mov     r9, rdi; lpParameter
0x180011ae8  mov     [rsp+198h+lpThreadId], rax; lpThreadId
0x180011aed  lea     r8, ?staticBackgroundThread@CUmRdpDr@@CAKPEAX@Z; lpStartAddress
0x180011af4  xor     ecx, ecx; lpThreadAttributes
0x180011af6  mov     [rsp+198h+dwCreationFlags], r12d; dwCreationFlags
0x180011afb  call    cs:__imp_CreateThread
0x180011b01  mov     [rdi+7C0h], rax
0x180011b08  test    rax, rax
0x180011b0b  jz      loc_180011B9B
0x180011b11  mov     ebx, 11Ch
0x180011b16  lea     rcx, [rsp+198h+VersionInformation]; void *
0x180011b1b  mov     r8d, ebx; Size
0x180011b1e  xor     edx, edx; Val
0x180011b20  mov     esi, ebp
0x180011b22  call    memset_0
0x180011b27  mov     eax, 10h
0x180011b2c  mov     [rsp+198h+VersionInformation.dwOSVersionInfoSize], ebx
0x180011b30  mov     r8b, 6; Condition
0x180011b33  mov     [rsp+198h+VersionInformation.wSuiteMask], ax
0x180011b3b  xor     ecx, ecx; ConditionMask
0x180011b3d  lea     edx, [rax+30h]; TypeMask
0x180011b40  call    cs:__imp_VerSetConditionMask
0x180011b46  mov     edx, 40h ; '@'; dwTypeMask
0x180011b4b  lea     rcx, [rsp+198h+VersionInformation]; lpVersionInformation
0x180011b50  mov     r8, rax; dwlConditionMask
0x180011b53  mov     rbx, rax
0x180011b56  call    cs:__imp_VerifyVersionInfoW
0x180011b5c  mov     r8, rbx; dwlConditionMask
0x180011b5f  lea     rcx, [rsp+198h+VersionInformation]; lpVersionInformation
0x180011b64  mov     r14d, eax
0x180011b67  mov     edx, 40h ; '@'; dwTypeMask
0x180011b6c  mov     eax, 100h
0x180011b71  mov     [rsp+198h+VersionInformation.wSuiteMask], ax
0x180011b79  call    cs:__imp_VerifyVersionInfoW
0x180011b7f  cmp     eax, ebp
0x180011b81  jnz     loc_180011C2B
0x180011b87  test    r14d, r14d
0x180011b8a  jnz     loc_180011C2B
0x180011b90  mov     cs:?fRunningOnPTS@@3HA, ebp; int fRunningOnPTS
0x180011b96  jmp     loc_180011C2B
0x180011b9b  mov     rcx, rdi; this
0x180011b9e  mov     esi, r12d
0x180011ba1  call    ?Release@CUmRdpDr@@QEAAJXZ; CUmRdpDr::Release(void)
0x180011ba6  call    cs:__imp_GetLastError
0x180011bac  jmp     short loc_180011BB7
0x180011bae  call    cs:__imp_GetLastError
0x180011bb4  mov     esi, r12d
0x180011bb7  mov     ebx, eax
0x180011bb9  mov     rcx, [rdi+8]; hObject
0x180011bbd  call    cs:__imp_CloseHandle
0x180011bc3  mov     r8, [rdi+868h]; lpMem
0x180011bca  mov     [rdi+8], r12
0x180011bce  test    r8, r8
0x180011bd1  jz      short loc_180011BF6
0x180011bd3  mov     rcx, gs:60h
0x180011bdc  xor     edx, edx; dwFlags
0x180011bde  mov     rcx, [rcx+30h]; hHeap
0x180011be2  call    cs:__imp_HeapFree
0x180011be8  mov     [rdi+868h], r12
0x180011bef  mov     [rdi+870h], r12d
0x180011bf6  mov     rcx, rdi; this
0x180011bf9  call    ?Shutdown@CUmRdpDr@@QEAAHXZ; CUmRdpDr::Shutdown(void)
0x180011bfe  mov     rcx, rdi; this
0x180011c01  call    ?CloseWaitableObjects@CUmRdpDr@@AEAAXXZ; CUmRdpDr::CloseWaitableObjects(void)
0x180011c06  mov     rcx, [rdi+7C0h]; hObject
0x180011c0d  test    rcx, rcx
0x180011c10  jz      short loc_180011C1F
0x180011c12  call    cs:__imp_CloseHandle
0x180011c18  mov     [rdi+7C0h], r12
0x180011c1f  mov     ecx, ebx; dwErrCode
0x180011c21  call    cs:__imp_SetLastError
0x180011c27  test    esi, esi
0x180011c29  jz      short loc_180011C31
0x180011c2b  mov     [rdi+7E4h], ebp
0x180011c31  mov     eax, esi
0x180011c33  jmp     loc_18001188F
```
