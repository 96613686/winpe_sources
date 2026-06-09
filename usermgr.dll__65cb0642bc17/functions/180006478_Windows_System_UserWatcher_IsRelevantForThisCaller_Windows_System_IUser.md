# Windows::System::UserWatcher::IsRelevantForThisCaller(Windows::System::IUser *)

- ea: `0x180006478`
- end: `0x1800066ee`
- name: `?IsRelevantForThisCaller@UserWatcher@System@Windows@@AEAA_NPEAUIUser@23@@Z`
- size: `630`
- prototype: `bool __fastcall(Windows::System::UserWatcher *__hidden this, struct Windows::System::IUser *)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800061a0`
- `0x180006300`
- `0x1800bb7c0`
- `0x1800bb9d0`

## callees

- `0x180006478`
- `0x180007920`
- `0x18000acdc`
- `0x18000ce48`
- `0x180014e7c`
- `0x180014e9c`
- `0x18004e58c`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180006627`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180006627`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800065cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180006682`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800065cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180006682`
- `ntdll!RtlEqualSid` at `0x180006666`
- `ntdll!RtlEqualSid` at `0x180006666`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180006537`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180006537`

## string_xrefs

- `0x1800064f3`: `onecore\ds\security\umstartup\usermgr\lib\userwatcher.cpp`
- `0x180006526`: `onecore\ds\security\umstartup\usermgr\lib\userwatcher.cpp`
- `0x1800065f7`: `onecore\ds\security\umstartup\usermgr\lib\userwatcher.cpp`
- `0x180006649`: `onecore\ds\security\umstartup\usermgr\lib\userwatcher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
bool __fastcall Windows::System::UserWatcher::IsRelevantForThisCaller(
        Windows::System::UserWatcher *this,
        struct Windows::System::IUser *a2)
{
  __int64 (__fastcall *v4)(struct Windows::System::IUser *, GUID *, __int64 *); // rbx
  int v5; // eax
  int v6; // eax
  int CurrentServiceSessionId; // eax
  int v8; // ecx
  bool v9; // bl
  void (__fastcall *v10)(void *, int *); // rbx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  int v13; // eax
  __int64 v14; // rdi
  unsigned int (__fastcall *v15)(__int64, PCWSTR, PSID *); // rbx
  PCWSTR StringRawBuffer; // rax
  const char *v17; // r9
  __int64 v18; // rcx
  __int64 v19; // rcx
  bool result; // al
  int v21[2]; // [rsp+20h] [rbp-38h] BYREF
  PSID Sid2[6]; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v24; // [rsp+68h] [rbp+10h] BYREF
  __int64 v25; // [rsp+70h] [rbp+18h] BYREF
  HSTRING string; // [rsp+78h] [rbp+20h] BYREF

  try
  {
    Sid2[1] = a2;
    if ( a2 )
      (*(void (__fastcall **)(struct Windows::System::IUser *))(*(_QWORD *)a2 + 8LL))(a2);
    v25 = 0;
    *(_QWORD *)v21 = 0;
    v24 = 0;
    v4 = **(__int64 (__fastcall ***)(struct Windows::System::IUser *, GUID *, __int64 *))a2;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
    v5 = v4(a2, &GUID_ebe7ab25_f6a9_4472_9fa2_e979ef15ff58, &v25);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x370,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userwatcher.cpp",
        (const char *)(unsigned int)v5,
        v21[0]);
    v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v25 + 96LL))(v25, &v24);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x371,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userwatcher.cpp",
        (const char *)(unsigned int)v6,
        v21[0]);
    CurrentServiceSessionId = RtlGetCurrentServiceSessionId(retaddr);
    v8 = *((_DWORD *)this + 106);
    if ( v8 == CurrentServiceSessionId || (v9 = 0, v8 == v24) )
    {
      v9 = 1;
      if ( !*((_BYTE *)this + 428) && !*((_BYTE *)this + 833) && !*((_BYTE *)this + 834) )
      {
        string = 0;
        Sid2[0] = 0;
        v10 = *(void (__fastcall **)(void *, int *))(Windows::System::Internal::Adapters::g_AdapterCollection + 56LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v21);
        v10(&Windows::System::Internal::Adapters::g_AdapterCollection, v21);
        v11 = v25;
        v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v25 + 72LL);
        WindowsDeleteString(string);
        string = 0;
        v13 = v12(v11, &string);
        if ( v13 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x37E,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userwatcher.cpp",
            (const char *)(unsigned int)v13,
            v21[0]);
        v14 = *(_QWORD *)v21;
        v15 = *(unsigned int (__fastcall **)(__int64, PCWSTR, PSID *))(**(_QWORD **)v21 + 40LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          Sid2,
          0);
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        if ( !v15(v14, StringRawBuffer, Sid2) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x37F,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userwatcher.cpp",
            v17);
        v9 = RtlEqualSid(*((PSID *)this + 67), Sid2[0]) != 0;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(Sid2);
        WindowsDeleteString(string);
      }
    }
    v18 = *(_QWORD *)v21;
    if ( *(_QWORD *)v21 )
    {
      *(_QWORD *)v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = v25;
    if ( v25 )
    {
      v25 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    (*(void (__fastcall **)(struct Windows::System::IUser *))(*(_QWORD *)a2 + 16LL))(a2);
    result = v9;
  }
  catch ( ... )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180006478  mov     [rsp+arg_0], rbx
0x18000647d  push    rsi
0x18000647e  push    rdi
0x18000647f  push    r14
0x180006481  sub     rsp, 40h
0x180006485  mov     rsi, rdx
0x180006488  mov     r14, rcx
0x18000648b  mov     [rsp+58h+var_28], rdx
0x180006490  test    rdx, rdx
0x180006493  jz      short loc_1800064A5
0x180006495  mov     rax, [rdx]
0x180006498  mov     rcx, rdx
0x18000649b  mov     rax, [rax+8]
0x18000649f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064a4  nop
0x1800064a5  mov     [rsp+58h+arg_10], 0
0x1800064ae  mov     qword ptr [rsp+58h+var_38], 0; int
0x1800064b7  mov     [rsp+58h+arg_8], 0
0x1800064bf  mov     rax, [rsi]
0x1800064c2  mov     rbx, [rax]
0x1800064c5  lea     rcx, [rsp+58h+arg_10]
0x1800064ca  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800064cf  lea     r8, [rsp+58h+arg_10]
0x1800064d4  lea     rdx, _GUID_ebe7ab25_f6a9_4472_9fa2_e979ef15ff58
0x1800064db  mov     rcx, rsi
0x1800064de  mov     rax, rbx
0x1800064e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064e6  nop
0x1800064e7  mov     rcx, [rsp+58h]; this
0x1800064ec  test    eax, eax
0x1800064ee  jns     short loc_180006504
0x1800064f0  mov     r9d, eax; char *
0x1800064f3  lea     r8, aOnecoreDsSecur_96; "onecore\\ds\\security\\umstartup\\userm"...
0x1800064fa  mov     edx, 370h; void *
0x1800064ff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180006504  mov     rcx, [rsp+58h+arg_10]
0x180006509  mov     rax, [rcx]
0x18000650c  lea     rdx, [rsp+58h+arg_8]
0x180006511  mov     rax, [rax+60h]
0x180006515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000651a  mov     rcx, [rsp+58h]; this
0x18000651f  test    eax, eax
0x180006521  jns     short loc_180006537
0x180006523  mov     r9d, eax; char *
0x180006526  lea     r8, aOnecoreDsSecur_96; "onecore\\ds\\security\\umstartup\\userm"...
0x18000652d  mov     edx, 371h; void *
0x180006532  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180006537  call    cs:__imp_RtlGetCurrentServiceSessionId
0x18000653d  mov     ecx, [r14+1A8h]
0x180006544  cmp     ecx, eax
0x180006546  jz      short loc_180006554
0x180006548  xor     bl, bl
0x18000654a  cmp     ecx, [rsp+58h+arg_8]
0x18000654e  jnz     loc_180006689
0x180006554  mov     bl, 1
0x180006556  cmp     byte ptr [r14+1ACh], 0
0x18000655e  jnz     loc_180006689
0x180006564  cmp     byte ptr [r14+341h], 0
0x18000656c  jnz     loc_180006689
0x180006572  cmp     byte ptr [r14+342h], 0
0x18000657a  jnz     loc_180006689
0x180006580  mov     [rsp+58h+string], 0
0x180006589  mov     [rsp+58h+Sid2], 0
0x180006592  mov     rax, cs:?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x180006599  mov     rbx, [rax+38h]
0x18000659d  lea     rcx, [rsp+58h+var_38]
0x1800065a2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800065a7  lea     rdx, [rsp+58h+var_38]
0x1800065ac  lea     rcx, ?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x1800065b3  mov     rax, rbx
0x1800065b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065bb  mov     rdi, [rsp+58h+arg_10]
0x1800065c0  mov     rax, [rdi]
0x1800065c3  mov     rbx, [rax+48h]
0x1800065c7  mov     rcx, [rsp+58h+string]; string
0x1800065cc  call    cs:__imp_WindowsDeleteString
0x1800065d2  mov     [rsp+58h+string], 0
0x1800065db  lea     rdx, [rsp+58h+string]
0x1800065e0  mov     rcx, rdi
0x1800065e3  mov     rax, rbx
0x1800065e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065eb  mov     rcx, [rsp+58h]; this
0x1800065f0  test    eax, eax
0x1800065f2  jns     short loc_180006608
0x1800065f4  mov     r9d, eax; char *
0x1800065f7  lea     r8, aOnecoreDsSecur_96; "onecore\\ds\\security\\umstartup\\userm"...
0x1800065fe  mov     edx, 37Eh; void *
0x180006603  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180006608  mov     rdi, qword ptr [rsp+58h+var_38]
0x18000660d  mov     rax, [rdi]
0x180006610  mov     rbx, [rax+28h]
0x180006614  xor     edx, edx
0x180006616  lea     rcx, [rsp+58h+Sid2]
0x18000661b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180006620  xor     edx, edx; length
0x180006622  mov     rcx, [rsp+58h+string]; string
0x180006627  call    cs:__imp_WindowsGetStringRawBuffer
0x18000662d  lea     r8, [rsp+58h+Sid2]
0x180006632  mov     rdx, rax
0x180006635  mov     rcx, rdi
0x180006638  mov     rax, rbx
0x18000663b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006640  mov     rcx, [rsp+58h]; this
0x180006645  test    eax, eax
0x180006647  jnz     short loc_18000665A
0x180006649  lea     r8, aOnecoreDsSecur_96; "onecore\\ds\\security\\umstartup\\userm"...
0x180006650  mov     edx, 37Fh; void *
0x180006655  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000665a  mov     rdx, [rsp+58h+Sid2]; Sid2
0x18000665f  mov     rcx, [r14+218h]; Sid1
0x180006666  call    cs:__imp_RtlEqualSid
0x18000666c  nop
0x18000666d  test    al, al
0x18000666f  setnz   bl
0x180006672  lea     rcx, [rsp+58h+Sid2]
0x180006677  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000667c  nop
0x18000667d  mov     rcx, [rsp+58h+string]; string
0x180006682  call    cs:__imp_WindowsDeleteString
0x180006688  nop
0x180006689  mov     rcx, qword ptr [rsp+58h+var_38]
0x18000668e  test    rcx, rcx
0x180006691  jz      short loc_1800066A9
0x180006693  mov     qword ptr [rsp+58h+var_38], 0
0x18000669c  mov     rax, [rcx]
0x18000669f  mov     rax, [rax+10h]
0x1800066a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066a8  nop
0x1800066a9  mov     rcx, [rsp+58h+arg_10]
0x1800066ae  test    rcx, rcx
0x1800066b1  jz      short loc_1800066C9
0x1800066b3  mov     [rsp+58h+arg_10], 0
0x1800066bc  mov     rax, [rcx]
0x1800066bf  mov     rax, [rax+10h]
0x1800066c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066c8  nop
0x1800066c9  mov     rcx, [rsi]
0x1800066cc  mov     rax, [rcx+10h]
0x1800066d0  mov     rcx, rsi
0x1800066d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066d8  nop
0x1800066d9  mov     al, bl
0x1800066db  jmp     short loc_1800066DF
0x1800066dd  xor     al, al
0x1800066df  mov     rbx, [rsp+58h+arg_0]
0x1800066e4  add     rsp, 40h
0x1800066e8  pop     r14
0x1800066ea  pop     rdi
0x1800066eb  pop     rsi
0x1800066ec  retn
```
