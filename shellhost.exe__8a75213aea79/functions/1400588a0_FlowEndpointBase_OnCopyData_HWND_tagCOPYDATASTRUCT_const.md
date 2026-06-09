# FlowEndpointBase::OnCopyData(HWND__ *,tagCOPYDATASTRUCT const &)

- ea: `0x1400588a0`
- end: `0x140058a06`
- name: `?OnCopyData@FlowEndpointBase@@IEAAXPEAUHWND__@@AEBUtagCOPYDATASTRUCT@@@Z`
- size: `358`
- prototype: `void __fastcall(FlowEndpointBase *__hidden this, HWND, const struct tagCOPYDATASTRUCT *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005fd30`

## callees

- `0x14000b420`
- `0x14004eaa4`
- `0x140052594`
- `0x140052bf8`
- `0x1400538ac`
- `0x140054cc0`
- `0x140055088`
- `0x140055274`
- `0x1400588a0`
- `0x14005d1a8`
- `0x14005fcdc`
- `0x140067010`

## import_xrefs

- `USER32!ReplyMessage` at `0x1400589b4`
- `USER32!ReplyMessage` at `0x1400589b4`

## string_xrefs

- `0x1400589f4`: `shellcommon\internal\shell\inc\ValueSetChannel.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall FlowEndpointBase::OnCopyData(FlowEndpointBase *this, HWND a2, const struct tagCOPYDATASTRUCT *a3)
{
  unsigned int dwData; // r14d
  Windows::Storage::Streams *cbData; // rcx
  int OverCallerManagedBuffer; // eax
  __int64 v9; // rax
  struct Windows::Storage::Streams::IBuffer **v10; // [rsp+20h] [rbp-20h]
  int v11; // [rsp+20h] [rbp-20h]
  _BYTE v12[8]; // [rsp+30h] [rbp-10h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  __int64 v15; // [rsp+60h] [rbp+20h] BYREF
  __int64 v16; // [rsp+78h] [rbp+38h] BYREF

  if ( *((_DWORD *)this + 28) != 3 )
  {
    if ( (dwData = a3->dwData,
          !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl))
      || !a2
      || *((_DWORD *)this + 28) == 1 && dwData == 3
      || FlowEndpointBase::DoesWindowBelongToCallingProcess(this, a2) )
    {
      if ( *((_DWORD *)this + 28) == 4 || *((_DWORD *)this + 28) == 1 && dwData == 3 || a2 == *((HWND *)this + 5) )
      {
        v16 = 0;
        if ( !*((_BYTE *)this + 129) )
        {
          cbData = (Windows::Storage::Streams *)a3->cbData;
          if ( (_DWORD)cbData )
          {
            v15 = 0;
            OverCallerManagedBuffer = Windows::Storage::Streams::CBuffer_CreateOverCallerManagedBuffer(
                                        cbData,
                                        (unsigned int)cbData,
                                        (unsigned int)a3->lpData,
                                        (unsigned __int8 *)&v15,
                                        v10);
            if ( OverCallerManagedBuffer < 0 )
              wil::details::in1diag3::_Throw_Hr(
                retaddr,
                (void *)0x226,
                (unsigned int)"shellcommon\\internal\\shell\\inc\\ValueSetChannel.h",
                (const char *)(unsigned int)OverCallerManagedBuffer,
                v11);
            winrt::com_ptr<Windows::Storage::Streams::IBuffer>::as<winrt::Windows::Storage::Streams::IBuffer>(&v15, v12);
            v9 = winrt::Windows::Foundation::Collections::ValueSet::ValueSet((winrt::Windows::Foundation::Collections::ValueSet *)v13);
            winrt::com_ptr<winrt::impl::IRestrictedErrorInfo>::operator=(&v16, v9);
            winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)v13);
            winrt::impl::consume_Windows_Storage_Streams_IPropertySetSerializer<winrt::Windows::Storage::Streams::IPropertySetSerializer>::Deserialize(
              (char *)this + 72,
              &v16,
              v12);
            winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)v12);
            if ( v15 )
              winrt::com_ptr<IUnknown>::unconditional_release_ref(&v15);
          }
        }
        ReplyMessage(0);
        (*(void (__fastcall **)(_QWORD, HWND, _QWORD, __int64 *))(**((_QWORD **)this + 10) + 8LL))(
          *((_QWORD *)this + 10),
          a2,
          dwData,
          &v16);
        winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v16);
      }
    }
  }
}

```

## disassembly

```asm
0x1400588a0  mov     [rsp-18h+arg_8], rbx
0x1400588a5  mov     [rsp-18h+arg_10], rsi
0x1400588aa  push    rbp
0x1400588ab  push    rdi
0x1400588ac  push    r14
0x1400588ae  mov     rbp, rsp
0x1400588b1  sub     rsp, 40h
0x1400588b5  mov     rsi, r8
0x1400588b8  mov     rdi, rdx
0x1400588bb  mov     rbx, rcx
0x1400588be  cmp     dword ptr [rcx+70h], 3
0x1400588c2  jz      loc_1400589DE
0x1400588c8  mov     r14d, [r8]
0x1400588cb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x1400588d2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x1400588d7  test    al, al
0x1400588d9  jz      short loc_1400588FF
0x1400588db  test    rdi, rdi
0x1400588de  jz      short loc_1400588FF
0x1400588e0  cmp     dword ptr [rbx+70h], 1
0x1400588e4  jnz     short loc_1400588EC
0x1400588e6  cmp     r14d, 3
0x1400588ea  jz      short loc_1400588FF
0x1400588ec  mov     rdx, rdi; HWND
0x1400588ef  mov     rcx, rbx; this
0x1400588f2  call    ?DoesWindowBelongToCallingProcess@FlowEndpointBase@@IEAA_NPEAUHWND__@@@Z; FlowEndpointBase::DoesWindowBelongToCallingProcess(HWND__ *)
0x1400588f7  test    al, al
0x1400588f9  jz      loc_1400589DE
0x1400588ff  cmp     dword ptr [rbx+70h], 4
0x140058903  jz      short loc_14005891B
0x140058905  cmp     dword ptr [rbx+70h], 1
0x140058909  jnz     short loc_140058911
0x14005890b  cmp     r14d, 3
0x14005890f  jz      short loc_14005891B
0x140058911  cmp     rdi, [rbx+28h]
0x140058915  jnz     loc_1400589DE
0x14005891b  mov     [rbp+arg_18], 0
0x140058923  cmp     byte ptr [rbx+81h], 0
0x14005892a  jnz     loc_1400589B2
0x140058930  mov     ecx, [rsi+8]; this
0x140058933  test    ecx, ecx
0x140058935  jz      short loc_1400589B2
0x140058937  mov     [rbp+arg_0], 0
0x14005893f  lea     r9, [rbp+arg_0]; unsigned __int8 *
0x140058943  mov     r8, [rsi+10h]; unsigned int
0x140058947  mov     edx, ecx; unsigned int
0x140058949  call    ?CBuffer_CreateOverCallerManagedBuffer@Streams@Storage@Windows@@YAJIIPEAEPEAPEAUIBuffer@123@@Z; Windows::Storage::Streams::CBuffer_CreateOverCallerManagedBuffer(uint,uint,uchar *,Windows::Storage::Streams::IBuffer * *)
0x14005894e  mov     rcx, [rbp+18h]; this
0x140058952  test    eax, eax
0x140058954  js      loc_1400589F1
0x14005895a  lea     rdx, [rbp+var_10]
0x14005895e  lea     rcx, [rbp+arg_0]
0x140058962  call    ??$as@UIBuffer@Streams@Storage@Windows@winrt@@@?$com_ptr@UIBuffer@Streams@Storage@Windows@@@winrt@@QEBA?A_PXZ
0x140058967  nop
0x140058968  lea     rcx, [rbp+var_8]; this
0x14005896c  call    ??0ValueSet@Collections@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Collections::ValueSet::ValueSet(void)
0x140058971  mov     rdx, rax
0x140058974  lea     rcx, [rbp+arg_18]
0x140058978  call    ??4?$com_ptr@UIRestrictedErrorInfo@impl@winrt@@@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::com_ptr<winrt::impl::IRestrictedErrorInfo>::operator=(winrt::com_ptr<winrt::impl::IRestrictedErrorInfo> &&)
0x14005897d  lea     rcx, [rbp+var_8]; this
0x140058981  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x140058986  lea     rcx, [rbx+48h]
0x14005898a  lea     r8, [rbp+var_10]
0x14005898e  lea     rdx, [rbp+arg_18]
0x140058992  call    ?Deserialize@?$consume_Windows_Storage_Streams_IPropertySetSerializer@UIPropertySetSerializer@Streams@Storage@Windows@winrt@@@impl@winrt@@QEBA@AEBUIPropertySet@Collections@Foundation@Windows@3@AEBUIBuffer@Streams@Storage@73@@Z; winrt::impl::consume_Windows_Storage_Streams_IPropertySetSerializer<winrt::Windows::Storage::Streams::IPropertySetSerializer>::Deserialize(winrt::Windows::Foundation::Collections::IPropertySet const &,winrt::Windows::Storage::Streams::IBuffer const &)
0x140058997  nop
0x140058998  lea     rcx, [rbp+var_10]; this
0x14005899c  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x1400589a1  nop
0x1400589a2  cmp     [rbp+arg_0], 0
0x1400589a7  jz      short loc_1400589B2
0x1400589a9  lea     rcx, [rbp+arg_0]
0x1400589ad  call    ?unconditional_release_ref@?$com_ptr@UIUnknown@@@winrt@@AEAAXXZ; winrt::com_ptr<IUnknown>::unconditional_release_ref(void)
0x1400589b2  xor     ecx, ecx; lResult
0x1400589b4  call    cs:__imp_ReplyMessage
0x1400589ba  mov     rcx, [rbx+50h]
0x1400589be  mov     rax, [rcx]
0x1400589c1  lea     r9, [rbp+arg_18]
0x1400589c5  mov     r8d, r14d
0x1400589c8  mov     rdx, rdi
0x1400589cb  mov     rax, [rax+8]
0x1400589cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400589d4  nop
0x1400589d5  lea     rcx, [rbp+arg_18]; this
0x1400589d9  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x1400589de  mov     rbx, [rsp+40h+arg_8]
0x1400589e3  mov     rsi, [rsp+40h+arg_10]
0x1400589e8  add     rsp, 40h
0x1400589ec  pop     r14
0x1400589ee  pop     rdi
0x1400589ef  pop     rbp
0x1400589f0  retn
0x1400589f1  mov     r9d, eax; char *
0x1400589f4  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\Valu"...
0x1400589fb  mov     edx, 226h; void *
0x140058a00  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
