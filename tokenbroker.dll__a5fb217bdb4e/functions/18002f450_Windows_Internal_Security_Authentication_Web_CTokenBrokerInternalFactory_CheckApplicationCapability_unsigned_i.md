# Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::CheckApplicationCapability(unsigned __int64,Windows::Foundation::IUriRuntimeClass *,HSTRING__ *,uchar *)

- ea: `0x18002f450`
- end: `0x18002f926`
- name: `?CheckApplicationCapability@CTokenBrokerInternalFactory@Web@Authentication@Security@Internal@Windows@@UEAAJ_KPEAUIUriRuntimeClass@Foundation@6@PEAUHSTRING__@@PEAE@Z`
- size: `1238`
- prototype: `int(Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory *__hidden this, unsigned __int64, struct Windows::Foundation::IUriRuntimeClass *, HSTRING, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000bd40`
- `0x18000bd70`
- `0x18001e700`
- `0x180020620`
- `0x18002071c`
- `0x180020c60`
- `0x180021750`
- `0x1800228a8`
- `0x180023090`
- `0x1800231c0`
- `0x180023a80`
- `0x180024000`
- `0x18002eb54`
- `0x18002f450`
- `0x18002f92c`
- `0x18002fbf0`
- `0x180030960`
- `0x1800332f8`
- `0x1800372d0`
- `0x18007f4cc`
- `0x18008e690`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002f6c4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002f730`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002f6c4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002f730`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f7f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f7f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f7a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f84c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f8bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f7a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f84c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f8bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18002f4d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18002f4d9`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18002f80c`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18002f80c`

## string_xrefs

- `0x18002f4c1`: `Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::CheckApplicationCapability`
- `0x18002f487`: `TokenBrokerInternalCheckApplicationCapability`
- `0x18002f4f3`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`
- `0x18002f536`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`
- `0x18002f579`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`
- `0x18002f5d1`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`
- `0x18002f633`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`
- `0x18002f6a4`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`
- `0x18002f77b`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`
- `0x18002f821`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::CheckApplicationCapability(
        unsigned __int64 this,
        __int64 a2,
        struct Windows::Foundation::IUriRuntimeClass *a3,
        HSTRING a4,
        bool *a5)
{
  struct IUnknown *v9; // rdi
  __int64 v10; // rcx
  __int64 *v12; // rbx
  int v13; // eax
  unsigned int v14; // edi
  int v15; // eax
  HSTRING *v16; // r8
  unsigned int v17; // edi
  __int64 v18; // r8
  HSTRING v19; // rbx
  int TokenBindingEntryInTable; // eax
  unsigned int v21; // edi
  PCWSTR StringRawBuffer; // rax
  int v23; // eax
  unsigned int v24; // edi
  int v25; // [rsp+20h] [rbp-1E8h]
  _BYTE v26[8]; // [rsp+30h] [rbp-1D8h] BYREF
  Windows::Internal::Security::Authentication::Web::CallerContext *v27[2]; // [rsp+38h] [rbp-1D0h] BYREF
  HANDLE Token[2]; // [rsp+48h] [rbp-1C0h] BYREF
  _BYTE v29[8]; // [rsp+58h] [rbp-1B0h] BYREF
  _BYTE v30[8]; // [rsp+60h] [rbp-1A8h] BYREF
  HSTRING string; // [rsp+68h] [rbp-1A0h] BYREF
  _QWORD v32[42]; // [rsp+70h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v32,
    "TokenBrokerInternalCheckApplicationCapability");
  v32[0] = &TbLogProvider::TokenBrokerInternalCheckApplicationCapability::`vftable';
  TbLogProvider::TokenBrokerInternalCheckApplicationCapability::StartActivity((TbLogProvider::TokenBrokerInternalCheckApplicationCapability *)v32);
  v9 = (struct IUnknown *)(this & -(__int64)(this != 88));
  Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(
    v10,
    (__int64)v29,
    v9,
    "Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::CheckApplicationCapability",
    0);
  if ( WindowsIsStringEmpty(a4) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A4,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
      (const char *)0x80070057LL,
      v25);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v29);
    TbLogProvider::TokenBrokerInternalCheckApplicationCapability::~TokenBrokerInternalCheckApplicationCapability((TbLogProvider::TokenBrokerInternalCheckApplicationCapability *)v32);
    return 2147942487LL;
  }
  else if ( a3 )
  {
    if ( a5 )
    {
      wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(v27, v30);
      v12 = (__int64 *)v27[0];
      if ( v27[0] )
      {
        if ( *(_BYTE *)v27[0]
          || (v13 = Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(v27[0], v9, 0, 0),
              v14 = v13,
              v13 >= 0) )
        {
          string = 0;
          Token[0] = 0;
          LOBYTE(Token[1]) = 0;
          v15 = Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(Token, v12[1]);
          v17 = v15;
          if ( v15 >= 0 )
          {
            Windows::Internal::Security::Authentication::TokenBroker::GetApplicationPfnForLookup(
              a3,
              (struct Windows::Foundation::IUriRuntimeClass *)&string,
              v16);
            if ( LOBYTE(Token[1]) )
              SetThreadToken(0, Token[0]);
            Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)Token);
            *(_OWORD *)Token = 0;
            Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer((Windows::Internal::Security::Authentication::Web::CallerContext *)v12);
            v18 = v12[9];
            v19 = string;
            TokenBindingEntryInTable = FindTokenBindingEntryInTable(a2, string, v18, Token);
            v21 = TokenBindingEntryInTable;
            if ( TokenBindingEntryInTable >= 0 )
            {
              v26[0] = 0;
              StringRawBuffer = WindowsGetStringRawBuffer(a4, 0);
              v23 = CapabilityCheck(*((_QWORD *)Token[0] + 1), StringRawBuffer, v26);
              if ( v23 >= 0 )
              {
                *a5 = v26[0] != 0;
                wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v32);
                if ( Token[1] )
                  std::_Ref_count_base::_Decref((std::_Ref_count_base *)Token[1]);
                if ( v19 )
                  WindowsDeleteString(v19);
                wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
                  v27,
                  0);
                Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v29);
                v32[0] = &TbLogProvider::TokenBrokerInternalCheckApplicationCapability::`vftable';
                wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v32);
                wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v32);
                return 0;
              }
              else
              {
                v24 = wil::details::in1diag3::Return_NtStatus(
                        retaddr,
                        (void *)0x3C9,
                        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
                        (const char *)(unsigned int)v23,
                        v25);
                if ( Token[1] )
                  std::_Ref_count_base::_Decref((std::_Ref_count_base *)Token[1]);
                if ( v19 )
                  WindowsDeleteString(v19);
                wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
                  v27,
                  0);
                Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v29);
                v32[0] = &TbLogProvider::TokenBrokerInternalCheckApplicationCapability::`vftable';
                wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v32);
                wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v32);
                return v24;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x3C0,
                (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
                (const char *)(unsigned int)TokenBindingEntryInTable,
                v25);
              if ( Token[1] )
                std::_Ref_count_base::_Decref((std::_Ref_count_base *)Token[1]);
              if ( v19 )
                WindowsDeleteString(v19);
              wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
                v27,
                0);
              Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v29);
              v32[0] = &TbLogProvider::TokenBrokerInternalCheckApplicationCapability::`vftable';
              wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v32);
              wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v32);
              return v21;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3B4,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
              (const char *)(unsigned int)v15,
              v25);
            if ( LOBYTE(Token[1]) )
              SetThreadToken(0, Token[0]);
            Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)Token);
            wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
              v27,
              0);
            Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v29);
            v32[0] = &TbLogProvider::TokenBrokerInternalCheckApplicationCapability::`vftable';
            wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v32);
            wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v32);
            return v17;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3AC,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
            (const char *)(unsigned int)v13,
            v25);
          wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
            v27,
            0);
          Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v29);
          TbLogProvider::TokenBrokerInternalCheckApplicationCapability::~TokenBrokerInternalCheckApplicationCapability((TbLogProvider::TokenBrokerInternalCheckApplicationCapability *)v32);
          return v14;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3A9,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
          (const char *)0x8007000ELL,
          v25);
        wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
          v27,
          0);
        Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v29);
        TbLogProvider::TokenBrokerInternalCheckApplicationCapability::~TokenBrokerInternalCheckApplicationCapability((TbLogProvider::TokenBrokerInternalCheckApplicationCapability *)v32);
        return 2147942414LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3A6,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
        (const char *)0x80070057LL,
        v25);
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v29);
      TbLogProvider::TokenBrokerInternalCheckApplicationCapability::~TokenBrokerInternalCheckApplicationCapability((TbLogProvider::TokenBrokerInternalCheckApplicationCapability *)v32);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A5,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
      (const char *)0x80070057LL,
      v25);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v29);
    TbLogProvider::TokenBrokerInternalCheckApplicationCapability::~TokenBrokerInternalCheckApplicationCapability((TbLogProvider::TokenBrokerInternalCheckApplicationCapability *)v32);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18002f450  push    rbx
0x18002f452  push    rsi
0x18002f453  push    rdi
0x18002f454  push    r12
0x18002f456  push    r14
0x18002f458  push    r15
0x18002f45a  sub     rsp, 1D8h
0x18002f461  mov     rax, cs:__security_cookie
0x18002f468  xor     rax, rsp
0x18002f46b  mov     [rsp+208h+var_48], rax
0x18002f473  mov     r15, r9
0x18002f476  mov     rsi, r8
0x18002f479  mov     r12, rdx
0x18002f47c  mov     rbx, rcx
0x18002f47f  mov     r14, [rsp+208h+arg_20]
0x18002f487  lea     rdx, aTokenbrokerint_39; "TokenBrokerInternalCheckApplicationCapa"...
0x18002f48e  lea     rcx, [rsp+208h+var_198]
0x18002f493  call    ??0?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002f498  lea     rax, ??_7TokenBrokerInternalCheckApplicationCapability@TbLogProvider@@6B@; const TbLogProvider::TokenBrokerInternalCheckApplicationCapability::`vftable'
0x18002f49f  mov     [rsp+208h+var_198], rax
0x18002f4a4  lea     rcx, [rsp+208h+var_198]; this
0x18002f4a9  call    ?StartActivity@TokenBrokerInternalCheckApplicationCapability@TbLogProvider@@QEAAXXZ; TbLogProvider::TokenBrokerInternalCheckApplicationCapability::StartActivity(void)
0x18002f4ae  nop
0x18002f4af  lea     rax, [rbx-58h]
0x18002f4b3  neg     rax
0x18002f4b6  sbb     rdi, rdi
0x18002f4b9  and     rdi, rbx
0x18002f4bc  mov     byte ptr [rsp+208h+var_1E8], 0; int
0x18002f4c1  lea     r9, aWindowsInterna_88; "Windows::Internal::Security::Authentica"...
0x18002f4c8  mov     r8, rdi
0x18002f4cb  lea     rdx, [rsp+208h+var_1B0]
0x18002f4d0  call    ?ProfileCaller@CWamCallerProfiler@Web@Authentication@Security@Internal@Windows@@QEAA?AVCWamProfilerThreadScope@23456@PEAUIUnknown@@PEBD_N@Z; Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(IUnknown *,char const *,bool)
0x18002f4d5  nop
0x18002f4d6  mov     rcx, r15; string
0x18002f4d9  call    cs:__imp_WindowsIsStringEmpty
0x18002f4df  test    eax, eax
0x18002f4e1  jz      short loc_18002F521
0x18002f4e3  mov     rcx, [rsp+208h]; this
0x18002f4eb  mov     ebx, 80070057h
0x18002f4f0  mov     r9d, ebx; char *
0x18002f4f3  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18002f4fa  mov     edx, 3A4h; void *
0x18002f4ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f504  nop
0x18002f505  lea     rcx, [rsp+208h+var_1B0]; this
0x18002f50a  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18002f50f  nop
0x18002f510  lea     rcx, [rsp+208h+var_198]; this
0x18002f515  call    ??1TokenBrokerInternalCheckApplicationCapability@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalCheckApplicationCapability::~TokenBrokerInternalCheckApplicationCapability(void)
0x18002f51a  mov     eax, ebx
0x18002f51c  jmp     loc_18002F904
0x18002f521  test    rsi, rsi
0x18002f524  jnz     short loc_18002F564
0x18002f526  mov     rcx, [rsp+208h]; this
0x18002f52e  mov     ebx, 80070057h
0x18002f533  mov     r9d, ebx; char *
0x18002f536  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18002f53d  mov     edx, 3A5h; void *
0x18002f542  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f547  nop
0x18002f548  lea     rcx, [rsp+208h+var_1B0]; this
0x18002f54d  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18002f552  nop
0x18002f553  lea     rcx, [rsp+208h+var_198]; this
0x18002f558  call    ??1TokenBrokerInternalCheckApplicationCapability@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalCheckApplicationCapability::~TokenBrokerInternalCheckApplicationCapability(void)
0x18002f55d  mov     eax, ebx
0x18002f55f  jmp     loc_18002F904
0x18002f564  test    r14, r14
0x18002f567  jnz     short loc_18002F5A7
0x18002f569  mov     rcx, [rsp+208h]; this
0x18002f571  mov     ebx, 80070057h
0x18002f576  mov     r9d, ebx; char *
0x18002f579  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18002f580  mov     edx, 3A6h; void *
0x18002f585  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f58a  nop
0x18002f58b  lea     rcx, [rsp+208h+var_1B0]; this
0x18002f590  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18002f595  nop
0x18002f596  lea     rcx, [rsp+208h+var_198]; this
0x18002f59b  call    ??1TokenBrokerInternalCheckApplicationCapability@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalCheckApplicationCapability::~TokenBrokerInternalCheckApplicationCapability(void)
0x18002f5a0  mov     eax, ebx
0x18002f5a2  jmp     loc_18002F904
0x18002f5a7  lea     rdx, [rsp+208h+var_1A8]
0x18002f5ac  lea     rcx, [rsp+208h+var_1D0]
0x18002f5b1  call    ??0?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x18002f5b6  nop
0x18002f5b7  mov     rbx, [rsp+208h+var_1D0]
0x18002f5bc  test    rbx, rbx
0x18002f5bf  jnz     short loc_18002F60C
0x18002f5c1  mov     rcx, [rsp+208h]; this
0x18002f5c9  mov     ebx, 8007000Eh
0x18002f5ce  mov     r9d, ebx; char *
0x18002f5d1  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18002f5d8  mov     edx, 3A9h; void *
0x18002f5dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f5e2  nop
0x18002f5e3  xor     edx, edx
0x18002f5e5  lea     rcx, [rsp+208h+var_1D0]
0x18002f5ea  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18002f5ef  nop
0x18002f5f0  lea     rcx, [rsp+208h+var_1B0]; this
0x18002f5f5  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18002f5fa  nop
0x18002f5fb  lea     rcx, [rsp+208h+var_198]; this
0x18002f600  call    ??1TokenBrokerInternalCheckApplicationCapability@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalCheckApplicationCapability::~TokenBrokerInternalCheckApplicationCapability(void)
0x18002f605  mov     eax, ebx
0x18002f607  jmp     loc_18002F904
0x18002f60c  cmp     byte ptr [rbx], 0
0x18002f60f  jnz     short loc_18002F66E
0x18002f611  xor     r9d, r9d; bool
0x18002f614  xor     r8d, r8d; unsigned __int64
0x18002f617  mov     rdx, rdi; struct IUnknown *
0x18002f61a  mov     rcx, rbx; this
0x18002f61d  call    ?Initialize@CallerContext@Web@Authentication@Security@Internal@Windows@@QEAAJPEAUIUnknown@@_K_N@Z; Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(IUnknown *,unsigned __int64,bool)
0x18002f622  mov     edi, eax
0x18002f624  test    eax, eax
0x18002f626  jns     short loc_18002F66E
0x18002f628  mov     rcx, [rsp+208h]; this
0x18002f630  mov     r9d, eax; char *
0x18002f633  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18002f63a  mov     edx, 3ACh; void *
0x18002f63f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f644  nop
0x18002f645  xor     edx, edx
0x18002f647  lea     rcx, [rsp+208h+var_1D0]
0x18002f64c  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18002f651  nop
0x18002f652  lea     rcx, [rsp+208h+var_1B0]; this
0x18002f657  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18002f65c  nop
0x18002f65d  lea     rcx, [rsp+208h+var_198]; this
0x18002f662  call    ??1TokenBrokerInternalCheckApplicationCapability@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalCheckApplicationCapability::~TokenBrokerInternalCheckApplicationCapability(void)
0x18002f667  mov     eax, edi
0x18002f669  jmp     loc_18002F904
0x18002f66e  mov     [rsp+208h+string], 0
0x18002f677  mov     [rsp+208h+Token], 0
0x18002f680  mov     byte ptr [rsp+208h+Token+8], 0
0x18002f685  mov     rdx, [rbx+8]; unsigned __int64
0x18002f689  lea     rcx, [rsp+208h+Token]; TokenHandle
0x18002f68e  call    ?Impersonate@ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAAJ_K@Z; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(unsigned __int64)
0x18002f693  mov     edi, eax
0x18002f695  test    eax, eax
0x18002f697  jns     short loc_18002F714
0x18002f699  mov     rcx, [rsp+208h]; this
0x18002f6a1  mov     r9d, eax; char *
0x18002f6a4  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18002f6ab  mov     edx, 3B4h; void *
0x18002f6b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f6b5  nop
0x18002f6b6  cmp     byte ptr [rsp+208h+Token+8], 0
0x18002f6bb  jz      short loc_18002F6CA
0x18002f6bd  mov     rdx, [rsp+208h+Token]; Token
0x18002f6c2  xor     ecx, ecx; Thread
0x18002f6c4  call    cs:__imp_SetThreadToken
0x18002f6ca  lea     rcx, [rsp+208h+Token]; this
0x18002f6cf  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x18002f6d4  nop
0x18002f6d5  xor     edx, edx
0x18002f6d7  lea     rcx, [rsp+208h+var_1D0]
0x18002f6dc  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18002f6e1  nop
0x18002f6e2  lea     rcx, [rsp+208h+var_1B0]; this
0x18002f6e7  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18002f6ec  nop
0x18002f6ed  lea     rax, ??_7TokenBrokerInternalCheckApplicationCapability@TbLogProvider@@6B@; const TbLogProvider::TokenBrokerInternalCheckApplicationCapability::`vftable'
0x18002f6f4  mov     [rsp+208h+var_198], rax
0x18002f6f9  lea     rcx, [rsp+208h+var_198]
0x18002f6fe  call    ?Destroy@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18002f703  lea     rcx, [rsp+208h+var_198]
0x18002f708  call    ??1?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18002f70d  mov     eax, edi
0x18002f70f  jmp     loc_18002F904
0x18002f714  lea     rdx, [rsp+208h+string]; struct Windows::Foundation::IUriRuntimeClass *
0x18002f719  mov     rcx, rsi; this
0x18002f71c  call    ?GetApplicationPfnForLookup@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUriRuntimeClass@Foundation@5@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetApplicationPfnForLookup(Windows::Foundation::IUriRuntimeClass *,HSTRING__ * *)
0x18002f721  nop
0x18002f722  cmp     byte ptr [rsp+208h+Token+8], 0
0x18002f727  jz      short loc_18002F736
0x18002f729  mov     rdx, [rsp+208h+Token]; Token
0x18002f72e  xor     ecx, ecx; Thread
0x18002f730  call    cs:__imp_SetThreadToken
0x18002f736  lea     rcx, [rsp+208h+Token]; this
0x18002f73b  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x18002f740  xorps   xmm0, xmm0
0x18002f743  movdqu  xmmword ptr [rsp+208h+Token], xmm0
0x18002f749  mov     rcx, rbx; this
0x18002f74c  call    ?IsCallerAppContainer@CallerContext@Web@Authentication@Security@Internal@Windows@@QEBA_NXZ; Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer(void)
0x18002f751  lea     r9, [rsp+208h+Token]
0x18002f756  mov     r8, [rbx+48h]
0x18002f75a  mov     rbx, [rsp+208h+string]
0x18002f75f  mov     rdx, rbx
0x18002f762  mov     rcx, r12
0x18002f765  call    ?FindTokenBindingEntryInTable@@YAJ_KPEAUHSTRING__@@1AEAV?$shared_ptr@VTBTokenBinding@@@std@@@Z; FindTokenBindingEntryInTable(unsigned __int64,HSTRING__ *,HSTRING__ *,std::shared_ptr<TBTokenBinding> &)
0x18002f76a  mov     edi, eax
0x18002f76c  test    eax, eax
0x18002f76e  jns     short loc_18002F7EB
0x18002f770  mov     rcx, [rsp+208h]; this
0x18002f778  mov     r9d, eax; char *
0x18002f77b  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18002f782  mov     edx, 3C0h; void *
0x18002f787  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f78c  nop
0x18002f78d  mov     rcx, [rsp+208h+Token+8]; this
0x18002f792  test    rcx, rcx
0x18002f795  jz      short loc_18002F79D
0x18002f797  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002f79c  nop
0x18002f79d  test    rbx, rbx
0x18002f7a0  jz      short loc_18002F7AC
0x18002f7a2  mov     rcx, rbx; string
0x18002f7a5  call    cs:__imp_WindowsDeleteString
0x18002f7ab  nop
0x18002f7ac  xor     edx, edx
0x18002f7ae  lea     rcx, [rsp+208h+var_1D0]
0x18002f7b3  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18002f7b8  nop
0x18002f7b9  lea     rcx, [rsp+208h+var_1B0]; this
0x18002f7be  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18002f7c3  nop
0x18002f7c4  lea     rax, ??_7TokenBrokerInternalCheckApplicationCapability@TbLogProvider@@6B@; const TbLogProvider::TokenBrokerInternalCheckApplicationCapability::`vftable'
0x18002f7cb  mov     [rsp+208h+var_198], rax
0x18002f7d0  lea     rcx, [rsp+208h+var_198]
0x18002f7d5  call    ?Destroy@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18002f7da  lea     rcx, [rsp+208h+var_198]
0x18002f7df  call    ??1?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18002f7e4  mov     eax, edi
0x18002f7e6  jmp     loc_18002F904
0x18002f7eb  mov     [rsp+208h+var_1D8], 0
0x18002f7f0  xor     edx, edx; length
0x18002f7f2  mov     rcx, r15; string
0x18002f7f5  call    cs:__imp_WindowsGetStringRawBuffer
0x18002f7fb  lea     r8, [rsp+208h+var_1D8]
0x18002f800  mov     rdx, rax
0x18002f803  mov     rcx, [rsp+208h+Token]
0x18002f808  mov     rcx, [rcx+8]
0x18002f80c  call    cs:__imp_CapabilityCheck
0x18002f812  test    eax, eax
0x18002f814  jns     short loc_18002F88F
0x18002f816  mov     rcx, [rsp+208h]; this
0x18002f81e  mov     r9d, eax; char *
0x18002f821  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18002f828  mov     edx, 3C9h; void *
0x18002f82d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002f832  mov     edi, eax
0x18002f834  mov     rcx, [rsp+208h+Token+8]; this
0x18002f839  test    rcx, rcx
0x18002f83c  jz      short loc_18002F844
0x18002f83e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002f843  nop
0x18002f844  test    rbx, rbx
0x18002f847  jz      short loc_18002F853
0x18002f849  mov     rcx, rbx; string
0x18002f84c  call    cs:__imp_WindowsDeleteString
0x18002f852  nop
0x18002f853  xor     edx, edx
0x18002f855  lea     rcx, [rsp+208h+var_1D0]
0x18002f85a  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18002f85f  nop
0x18002f860  lea     rcx, [rsp+208h+var_1B0]; this
0x18002f865  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18002f86a  nop
0x18002f86b  lea     rax, ??_7TokenBrokerInternalCheckApplicationCapability@TbLogProvider@@6B@; const TbLogProvider::TokenBrokerInternalCheckApplicationCapability::`vftable'
0x18002f872  mov     [rsp+208h+var_198], rax
0x18002f877  lea     rcx, [rsp+208h+var_198]
0x18002f87c  call    ?Destroy@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18002f881  lea     rcx, [rsp+208h+var_198]
0x18002f886  call    ??1?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18002f88b  mov     eax, edi
0x18002f88d  jmp     short loc_18002F904
0x18002f88f  cmp     [rsp+208h+var_1D8], 0
0x18002f894  setnz   al
0x18002f897  mov     [r14], al
0x18002f89a  lea     rcx, [rsp+208h+var_198]
0x18002f89f  call    ?Stop@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002f8a4  nop
0x18002f8a5  mov     rcx, [rsp+208h+Token+8]; this
0x18002f8aa  test    rcx, rcx
0x18002f8ad  jz      short loc_18002F8B5
0x18002f8af  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002f8b4  nop
0x18002f8b5  test    rbx, rbx
0x18002f8b8  jz      short loc_18002F8C4
0x18002f8ba  mov     rcx, rbx; string
0x18002f8bd  call    cs:__imp_WindowsDeleteString
0x18002f8c3  nop
0x18002f8c4  xor     edx, edx
0x18002f8c6  lea     rcx, [rsp+208h+var_1D0]
0x18002f8cb  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18002f8d0  nop
0x18002f8d1  lea     rcx, [rsp+208h+var_1B0]; this
0x18002f8d6  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18002f8db  nop
0x18002f8dc  lea     rax, ??_7TokenBrokerInternalCheckApplicationCapability@TbLogProvider@@6B@; const TbLogProvider::TokenBrokerInternalCheckApplicationCapability::`vftable'
0x18002f8e3  mov     [rsp+208h+var_198], rax
0x18002f8e8  lea     rcx, [rsp+208h+var_198]
0x18002f8ed  call    ?Destroy@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18002f8f2  lea     rcx, [rsp+208h+var_198]
0x18002f8f7  call    ??1?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18002f8fc  xor     eax, eax
  ... truncated ...
```
