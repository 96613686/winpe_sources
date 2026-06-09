# TbLogProvider::FindAllSecondaryAccountsAsync::Stop(Windows::Security::Credentials::IWebAccount *,long)

- ea: `0x1800c4680`
- end: `0x1800c4b53`
- name: `?Stop@FindAllSecondaryAccountsAsync@TbLogProvider@@QEAAXPEAUIWebAccount@Credentials@Security@Windows@@J@Z`
- size: `1235`
- prototype: `void __fastcall(TbLogProvider::FindAllSecondaryAccountsAsync *__hidden this, struct Windows::Security::Credentials::IWebAccount *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800899a0`
- `0x1800b552c`

## callees

- `0x1800031e4`
- `0x180003868`
- `0x18000fcf8`
- `0x180024118`
- `0x1800455a4`
- `0x18005e830`
- `0x180063fc4`
- `0x18007f7ec`
- `0x1800c4680`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c4a80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c4a80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4807`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c481f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4a52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4a6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4807`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c481f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4a52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4a6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c46fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c475f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4b1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4b38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c46fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c475f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4b1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4b38`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall TbLogProvider::FindAllSecondaryAccountsAsync::Stop(
        TbLogProvider::FindAllSecondaryAccountsAsync *this,
        struct Windows::Security::Credentials::IWebAccount *a2,
        __int64 a3)
{
  int v3; // r14d
  struct Windows::Security::Credentials::IWebAccount *v4; // r9
  __int64 v6; // rax
  __int64 v7; // rbx
  void (__fastcall *v8)(__int64, HSTRING *); // rdi
  __int64 v9; // rdi
  void (__fastcall *v10)(__int64, HSTRING *); // rbx
  __int64 v11; // rbx
  int v12; // eax
  int *v13; // rbx
  const struct _tlgProvider_t *v14; // rax
  int v15; // edi
  int v16; // r9d
  const struct _tlgProvider_t *v17; // rax
  int v18; // ebx
  __int64 v19; // r8
  int v20; // r9d
  int v21; // [rsp+C0h] [rbp-A8h] BYREF
  HSTRING v22; // [rsp+C8h] [rbp-A0h] BYREF
  HSTRING string; // [rsp+D0h] [rbp-98h] BYREF
  int v24; // [rsp+D8h] [rbp-90h] BYREF
  int v25; // [rsp+DCh] [rbp-8Ch] BYREF
  int v26; // [rsp+E0h] [rbp-88h] BYREF
  int v27; // [rsp+E4h] [rbp-84h] BYREF
  __int64 v28; // [rsp+E8h] [rbp-80h] BYREF
  __int64 v29; // [rsp+F0h] [rbp-78h] BYREF
  __int64 v30; // [rsp+F8h] [rbp-70h] BYREF
  PCWSTR StringRawBuffer; // [rsp+100h] [rbp-68h] BYREF
  PCWSTR v32; // [rsp+108h] [rbp-60h] BYREF
  __int64 v33; // [rsp+110h] [rbp-58h] BYREF
  __int64 v34; // [rsp+118h] [rbp-50h] BYREF
  __int64 v35; // [rsp+120h] [rbp-48h] BYREF
  __int64 v36; // [rsp+128h] [rbp-40h] BYREF
  __int64 v37; // [rsp+130h] [rbp-38h] BYREF
  __int64 v38; // [rsp+138h] [rbp-30h] BYREF
  _QWORD v39[5]; // [rsp+140h] [rbp-28h] BYREF
  __int64 v40; // [rsp+178h] [rbp+10h] BYREF
  __int64 v41; // [rsp+188h] [rbp+20h] BYREF

  try
  {
    v3 = a3;
    v4 = a2;
    string = 0;
    v22 = 0;
    if ( a2 )
    {
      v6 = *(_QWORD *)a2;
      v40 = 0;
      if ( (*(int (__fastcall **)(struct Windows::Security::Credentials::IWebAccount *, __int64 *, __int64, struct Windows::Security::Credentials::IWebAccount *))(v6 + 48))(
             a2,
             &v40,
             a3,
             a2) >= 0 )
      {
        v7 = v40;
        if ( v40 )
        {
          v8 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v40 + 48LL);
          WindowsDeleteString(string);
          string = 0;
          v8(v7, &string);
          v41 = 0;
          if ( (int)wil::com_query_to_nothrow<Windows::Security::Credentials::IWebAccountProvider2,wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider,wil::err_returncode_policy> &>(
                      &v40,
                      &v41) >= 0 )
          {
            v9 = v41;
            v10 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v41 + 56LL);
            WindowsDeleteString(v22);
            v22 = 0;
            v10(v9, &v22);
          }
          wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v41);
        }
      }
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v40);
    }
    v11 = *((_QWORD *)this + 34);
    v12 = *(_DWORD *)(v11 + 72);
    if ( v12 < 0 && (v13 = (int *)(v11 + 80), v12 == v13[2]) && v13 )
    {
      wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(
        this,
        a2,
        a3,
        v4);
      v14 = TbLogProvider::Provider();
      v15 = (int)v14;
      if ( *(_DWORD *)v14 > 5u && (unsigned __int8)tlgKeywordOn(v14, 0x400000000000LL) )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(v22, 0);
        v32 = WindowsGetStringRawBuffer(string, 0);
        LODWORD(v40) = v3;
        v33 = *((_QWORD *)v13 + 15);
        v34 = *((_QWORD *)v13 + 14);
        LODWORD(v41) = v13[26];
        v35 = *((_QWORD *)v13 + 12);
        v36 = *((_QWORD *)v13 + 11);
        v24 = v13[20];
        v37 = *((_QWORD *)v13 + 9);
        v25 = v13[8];
        v38 = *((_QWORD *)v13 + 3);
        v26 = *v13;
        v39[0] = *((_QWORD *)v13 + 16);
        v27 = v13[16];
        v28 = *((_QWORD *)v13 + 7);
        v21 = v13[2];
        v29 = 0x1000000;
        v30 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v15,
          (unsigned int)&dword_18014D704,
          *((_QWORD *)this + 34) + 8,
          v16,
          (__int64)&v30,
          (__int64)&v29,
          (__int64)&v21,
          (__int64)&v28,
          (__int64)&v27,
          (__int64)v39,
          (__int64)&v26,
          (__int64)&v38,
          (__int64)&v25,
          (__int64)&v37,
          (__int64)&v24,
          (__int64)&v36,
          (__int64)&v35,
          (__int64)&v41,
          (__int64)&v34,
          (__int64)&v33,
          (__int64)&v40,
          (__int64)&v32,
          (__int64)&StringRawBuffer);
      }
    }
    else
    {
      wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(
        this,
        a2,
        a3,
        v4);
      v17 = TbLogProvider::Provider();
      v18 = (int)v17;
      if ( *(_DWORD *)v17 > 5u && (unsigned __int8)tlgKeywordOn(v17, 0x400000000000LL) )
      {
        v30 = (__int64)WindowsGetStringRawBuffer(v22, 0);
        v29 = (__int64)WindowsGetStringRawBuffer(string, 0);
        LODWORD(v40) = v3;
        LODWORD(v41) = GetCurrentThreadId();
        v19 = *((_QWORD *)this + 34);
        v21 = *(_DWORD *)(v19 + 72);
        v28 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v18,
          (unsigned int)&dword_18014D874,
          v19 + 8,
          v20,
          (__int64)&v28,
          (__int64)&v21,
          (__int64)&v41,
          (__int64)&v40,
          (__int64)&v29,
          (__int64)&v30);
      }
    }
    wil::ActivityBase<WamClientLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
    WindowsDeleteString(v22);
    v22 = 0;
    WindowsDeleteString(string);
  }
  catch ( ... )
  {
  }
}

```

## disassembly

```asm
0x1800c4680  mov     r11, rsp
0x1800c4683  mov     [r11+8], rbx
0x1800c4687  push    rsi
0x1800c4688  push    rdi
0x1800c4689  push    r14
0x1800c468b  sub     rsp, 150h
0x1800c4692  mov     r14d, r8d
0x1800c4695  mov     r9, rdx
0x1800c4698  mov     rsi, rcx
0x1800c469b  mov     qword ptr [r11-98h], 0
0x1800c46a6  mov     qword ptr [r11-0A0h], 0
0x1800c46b1  test    rdx, rdx
0x1800c46b4  jz      loc_1800C47A0
0x1800c46ba  mov     rax, [rdx]
0x1800c46bd  mov     qword ptr [r11+10h], 0
0x1800c46c5  lea     rdx, [r11+10h]
0x1800c46c9  mov     rcx, r9
0x1800c46cc  mov     rax, [rax+30h]
0x1800c46d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c46d5  test    eax, eax
0x1800c46d7  js      loc_1800C4793
0x1800c46dd  mov     rbx, [rsp+168h+arg_8]
0x1800c46e5  test    rbx, rbx
0x1800c46e8  jz      loc_1800C4793
0x1800c46ee  mov     rax, [rbx]
0x1800c46f1  mov     rdi, [rax+30h]
0x1800c46f5  mov     rcx, [rsp+168h+string]; string
0x1800c46fd  call    cs:__imp_WindowsDeleteString
0x1800c4703  mov     [rsp+168h+string], 0
0x1800c470f  lea     rdx, [rsp+168h+string]
0x1800c4717  mov     rcx, rbx
0x1800c471a  mov     rax, rdi
0x1800c471d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4722  nop
0x1800c4723  mov     [rsp+168h+arg_18], 0
0x1800c472f  lea     rdx, [rsp+168h+arg_18]
0x1800c4737  lea     rcx, [rsp+168h+arg_8]
0x1800c473f  call    ??$com_query_to_nothrow@UIWebAccountProvider2@Credentials@Security@Windows@@AEAV?$com_ptr_t@UIWebAccountProvider@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@@wil@@YAJAEAV?$com_ptr_t@UIWebAccountProvider@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@0@PEAPEAUIWebAccountProvider2@Credentials@Security@Windows@@@Z; wil::com_query_to_nothrow<Windows::Security::Credentials::IWebAccountProvider2,wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider,wil::err_returncode_policy> &>(wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider,wil::err_returncode_policy> &,Windows::Security::Credentials::IWebAccountProvider2 * *)
0x1800c4744  test    eax, eax
0x1800c4746  js      short loc_1800C4785
0x1800c4748  mov     rdi, [rsp+168h+arg_18]
0x1800c4750  mov     rax, [rdi]
0x1800c4753  mov     rbx, [rax+38h]
0x1800c4757  mov     rcx, [rsp+168h+var_A0]; string
0x1800c475f  call    cs:__imp_WindowsDeleteString
0x1800c4765  mov     [rsp+168h+var_A0], 0
0x1800c4771  lea     rdx, [rsp+168h+var_A0]
0x1800c4779  mov     rcx, rdi
0x1800c477c  mov     rax, rbx
0x1800c477f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4784  nop
0x1800c4785  lea     rcx, [rsp+168h+arg_18]
0x1800c478d  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x1800c4792  nop
0x1800c4793  lea     rcx, [rsp+168h+arg_8]
0x1800c479b  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x1800c47a0  mov     rbx, [rsi+110h]
0x1800c47a7  mov     eax, [rbx+48h]
0x1800c47aa  test    eax, eax
0x1800c47ac  jns     loc_1800C4A13
0x1800c47b2  add     rbx, 50h ; 'P'
0x1800c47b6  cmp     eax, [rbx+8]
0x1800c47b9  jnz     loc_1800C4A13
0x1800c47bf  test    rbx, rbx
0x1800c47c2  jz      loc_1800C4A13
0x1800c47c8  mov     rcx, rsi
0x1800c47cb  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800c47d0  call    ?Provider@TbLogProvider@@SAPEBU_tlgProvider_t@@XZ; TbLogProvider::Provider(void)
0x1800c47d5  mov     rdi, rax
0x1800c47d8  mov     ecx, [rax]
0x1800c47da  cmp     ecx, 5
0x1800c47dd  jbe     loc_1800C4B0D
0x1800c47e3  mov     rdx, 400000000000h
0x1800c47ed  mov     rcx, rax
0x1800c47f0  call    _tlgKeywordOn
0x1800c47f5  test    al, al
0x1800c47f7  jz      loc_1800C4B0D
0x1800c47fd  xor     edx, edx; length
0x1800c47ff  mov     rcx, [rsp+168h+var_A0]; string
0x1800c4807  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c480d  mov     [rsp+168h+var_68], rax
0x1800c4815  xor     edx, edx; length
0x1800c4817  mov     rcx, [rsp+168h+string]; string
0x1800c481f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c4825  mov     [rsp+168h+var_60], rax
0x1800c482d  mov     dword ptr [rsp+168h+arg_8], r14d
0x1800c4835  mov     rax, [rbx+78h]
0x1800c4839  mov     [rsp+168h+var_58], rax
0x1800c4841  mov     rax, [rbx+70h]
0x1800c4845  mov     [rsp+168h+var_50], rax
0x1800c484d  mov     eax, [rbx+68h]
0x1800c4850  mov     dword ptr [rsp+168h+arg_18], eax
0x1800c4857  mov     rax, [rbx+60h]
0x1800c485b  mov     [rsp+168h+var_48], rax
0x1800c4863  mov     rax, [rbx+58h]
0x1800c4867  mov     [rsp+168h+var_40], rax
0x1800c486f  mov     eax, [rbx+50h]
0x1800c4872  mov     [rsp+168h+var_90], eax
0x1800c4879  mov     rax, [rbx+48h]
0x1800c487d  mov     [rsp+168h+var_38], rax
0x1800c4885  mov     eax, [rbx+20h]
0x1800c4888  mov     [rsp+168h+var_8C], eax
0x1800c488f  mov     rax, [rbx+18h]
0x1800c4893  mov     [rsp+168h+var_30], rax
0x1800c489b  mov     eax, [rbx]
0x1800c489d  mov     [rsp+168h+var_88], eax
0x1800c48a4  mov     rax, [rbx+80h]
0x1800c48ab  mov     [rsp+168h+var_28], rax
0x1800c48b3  mov     eax, [rbx+40h]
0x1800c48b6  mov     [rsp+168h+var_84], eax
0x1800c48bd  mov     rax, [rbx+38h]
0x1800c48c1  mov     [rsp+168h+var_80], rax
0x1800c48c9  mov     eax, [rbx+8]
0x1800c48cc  mov     [rsp+168h+var_A8], eax
0x1800c48d3  mov     eax, 1000000h
0x1800c48d8  mov     [rsp+168h+var_78], rax
0x1800c48e0  mov     [rsp+168h+var_70], rax
0x1800c48e8  mov     r8, [rsi+110h]
0x1800c48ef  add     r8, 8
0x1800c48f3  lea     rax, [rsp+168h+var_68]
0x1800c48fb  mov     [rsp+168h+var_B8], rax
0x1800c4903  lea     rax, [rsp+168h+var_60]
0x1800c490b  mov     [rsp+168h+var_C0], rax
0x1800c4913  lea     rax, [rsp+168h+arg_8]
0x1800c491b  mov     [rsp+168h+var_C8], rax
0x1800c4923  lea     rax, [rsp+168h+var_58]
0x1800c492b  mov     [rsp+168h+var_D0], rax
0x1800c4933  lea     rax, [rsp+168h+var_50]
0x1800c493b  mov     [rsp+168h+var_D8], rax
0x1800c4943  lea     rax, [rsp+168h+arg_18]
0x1800c494b  mov     [rsp+168h+var_E0], rax
0x1800c4953  lea     rax, [rsp+168h+var_48]
0x1800c495b  mov     [rsp+168h+var_E8], rax
0x1800c4963  lea     rax, [rsp+168h+var_40]
0x1800c496b  mov     [rsp+168h+var_F0], rax
0x1800c4970  lea     rax, [rsp+168h+var_90]
0x1800c4978  mov     [rsp+168h+var_F8], rax
0x1800c497d  lea     rax, [rsp+168h+var_38]
0x1800c4985  mov     [rsp+168h+var_100], rax
0x1800c498a  lea     rax, [rsp+168h+var_8C]
0x1800c4992  mov     [rsp+168h+var_108], rax
0x1800c4997  lea     rax, [rsp+168h+var_30]
0x1800c499f  mov     [rsp+168h+var_110], rax
0x1800c49a4  lea     rax, [rsp+168h+var_88]
0x1800c49ac  mov     [rsp+168h+var_118], rax
0x1800c49b1  lea     rax, [rsp+168h+var_28]
0x1800c49b9  mov     [rsp+168h+var_120], rax
0x1800c49be  lea     rax, [rsp+168h+var_84]
0x1800c49c6  mov     [rsp+168h+var_128], rax
0x1800c49cb  lea     rax, [rsp+168h+var_80]
0x1800c49d3  mov     [rsp+168h+var_130], rax
0x1800c49d8  lea     rax, [rsp+168h+var_A8]
0x1800c49e0  mov     [rsp+168h+var_138], rax
0x1800c49e5  lea     rax, [rsp+168h+var_78]
0x1800c49ed  mov     [rsp+168h+var_140], rax
0x1800c49f2  lea     rax, [rsp+168h+var_70]
0x1800c49fa  mov     [rsp+168h+var_148], rax
0x1800c49ff  lea     rdx, dword_18014D704
0x1800c4a06  mov     rcx, rdi
0x1800c4a09  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456466@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800c4a0e  jmp     loc_1800C4B0D
0x1800c4a13  mov     rcx, rsi
0x1800c4a16  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800c4a1b  call    ?Provider@TbLogProvider@@SAPEBU_tlgProvider_t@@XZ; TbLogProvider::Provider(void)
0x1800c4a20  mov     rbx, rax
0x1800c4a23  mov     ecx, [rax]
0x1800c4a25  cmp     ecx, 5
0x1800c4a28  jbe     loc_1800C4B0D
0x1800c4a2e  mov     rdx, 400000000000h
0x1800c4a38  mov     rcx, rax
0x1800c4a3b  call    _tlgKeywordOn
0x1800c4a40  test    al, al
0x1800c4a42  jz      loc_1800C4B0D
0x1800c4a48  xor     edx, edx; length
0x1800c4a4a  mov     rcx, [rsp+168h+var_A0]; string
0x1800c4a52  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c4a58  mov     [rsp+168h+var_70], rax
0x1800c4a60  xor     edx, edx; length
0x1800c4a62  mov     rcx, [rsp+168h+string]; string
0x1800c4a6a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c4a70  mov     [rsp+168h+var_78], rax
0x1800c4a78  mov     dword ptr [rsp+168h+arg_8], r14d
0x1800c4a80  call    cs:__imp_GetCurrentThreadId
0x1800c4a86  mov     dword ptr [rsp+168h+arg_18], eax
0x1800c4a8d  mov     r8, [rsi+110h]
0x1800c4a94  mov     eax, [r8+48h]
0x1800c4a98  mov     [rsp+168h+var_A8], eax
0x1800c4a9f  mov     eax, 1000000h
0x1800c4aa4  mov     [rsp+168h+var_80], rax
0x1800c4aac  add     r8, 8
0x1800c4ab0  lea     rax, [rsp+168h+var_70]
0x1800c4ab8  mov     [rsp+168h+var_120], rax
0x1800c4abd  lea     rax, [rsp+168h+var_78]
0x1800c4ac5  mov     [rsp+168h+var_128], rax
0x1800c4aca  lea     rax, [rsp+168h+arg_8]
0x1800c4ad2  mov     [rsp+168h+var_130], rax
0x1800c4ad7  lea     rax, [rsp+168h+arg_18]
0x1800c4adf  mov     [rsp+168h+var_138], rax
0x1800c4ae4  lea     rax, [rsp+168h+var_A8]
0x1800c4aec  mov     [rsp+168h+var_140], rax
0x1800c4af1  lea     rax, [rsp+168h+var_80]
0x1800c4af9  mov     [rsp+168h+var_148], rax
0x1800c4afe  lea     rdx, dword_18014D874
0x1800c4b05  mov     rcx, rbx
0x1800c4b08  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800c4b0d  mov     rcx, rsi
0x1800c4b10  call    ?IgnoreCurrentThread@?$ActivityBase@VWamClientLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WamClientLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x1800c4b15  nop
0x1800c4b16  mov     rcx, [rsp+168h+var_A0]; string
0x1800c4b1e  call    cs:__imp_WindowsDeleteString
0x1800c4b24  mov     [rsp+168h+var_A0], 0
0x1800c4b30  mov     rcx, [rsp+168h+string]; string
0x1800c4b38  call    cs:__imp_WindowsDeleteString
0x1800c4b3e  nop
0x1800c4b3f  mov     rbx, [rsp+168h+arg_0]
0x1800c4b47  add     rsp, 150h
0x1800c4b4e  pop     r14
0x1800c4b50  pop     rdi
0x1800c4b51  pop     rsi
0x1800c4b52  retn
```
