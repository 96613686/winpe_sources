# RefreshContext::_GetQueryParams(Windows::Internal::Flighting::ICommonTargetingAttributesFactory *,HSTRING__ *,HSTRING__ *,Microsoft::WRL::Wrappers::HString &,Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *)

- ea: `0x18002e110`
- end: `0x18002e292`
- name: `?_GetQueryParams@RefreshContext@@AEAA?AVHString@Wrappers@WRL@Microsoft@@PEAUICommonTargetingAttributesFactory@Flighting@Internal@Windows@@PEAUHSTRING__@@1AEAV2345@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@9@@Z`
- size: `386`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, Microsoft::WRL::Wrappers::HString *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b3a0`

## callees

- `0x180005f50`
- `0x1800101fc`
- `0x180019e18`
- `0x18002ade8`
- `0x18002dca8`
- `0x18002e110`
- `0x18002e3bc`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e1b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e201`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e1b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e201`

## string_xrefs

- `0x18002e22c`: `onecore\base\flighting\onesettings\libs\configurationsmanager\refreshcontext.cpp`
- `0x18002e26b`: `onecore\base\flighting\onesettings\libs\configurationsmanager\refreshcontext.cpp`
- `0x18002e280`: `onecore\base\flighting\onesettings\libs\configurationsmanager\refreshcontext.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall RefreshContext::_GetQueryParams(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        HSTRING *a6,
        __int64 (__fastcall ***a7)(_QWORD, GUID *, __int64 *))
{
  __int64 (__fastcall *v11)(__int64, __int64, __int64, __int64); // rbx
  int v12; // eax
  __int64 (__fastcall ***v13)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v14)(_QWORD, GUID *, __int64); // rbx
  int v15; // eax
  int v16; // eax
  wil::details::in1diag3 *v17; // rcx
  Microsoft::WRL::Wrappers::HString *v18; // rsi
  __int64 v19; // rdx
  __int64 (__fastcall ***v20)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v21)(_QWORD, GUID *, __int64); // rbx
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  __int64 (__fastcall ***v24)(_QWORD, GUID *, __int64); // [rsp+80h] [rbp+40h] BYREF

  v24 = 0;
  v11 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)a3 + 64LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  v12 = v11(a3, a4, a5, 1);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAF,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\refreshcontext.cpp",
      (const char *)(unsigned int)v12,
      (int)&v24);
  if ( a7 )
    RefreshContext::_ApplyCtacOverridesOnQuery(a1, &v24, a7);
  *a2 = 0;
  v13 = v24;
  v14 = (*v24)[7];
  WindowsDeleteString(0);
  *a2 = 0;
  v15 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), _QWORD *))v14)(v13, a2);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB9,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\refreshcontext.cpp",
      (const char *)(unsigned int)v15,
      (int)&v24);
  v16 = RefreshContext::_RemoveQueryTags(&v24);
  v17 = retaddr;
  v18 = (Microsoft::WRL::Wrappers::HString *)a6;
  if ( v16 < 0 )
  {
    v19 = 187;
LABEL_9:
    wil::details::in1diag3::_Log_Hr(
      v17,
      (void *)v19,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\refreshcontext.cpp",
      (const char *)(unsigned int)v16,
      (int)&v24);
    Microsoft::WRL::Wrappers::HString::Set(v18, &String1, 0);
    goto LABEL_10;
  }
  v20 = v24;
  v21 = (*v24)[7];
  WindowsDeleteString(*a6);
  *(_QWORD *)v18 = 0;
  v16 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), Microsoft::WRL::Wrappers::HString *))v21)(
          v20,
          v18);
  v17 = retaddr;
  if ( v16 < 0 )
  {
    v19 = 190;
    goto LABEL_9;
  }
LABEL_10:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  return a2;
}

```

## disassembly

```asm
0x18002e110  mov     [rsp-28h+arg_0], rbx
0x18002e115  mov     [rsp-28h+arg_8], rdx
0x18002e11a  push    rbp
0x18002e11b  push    rsi
0x18002e11c  push    rdi
0x18002e11d  push    r14
0x18002e11f  push    r15
0x18002e121  mov     rbp, rsp
0x18002e124  sub     rsp, 40h
0x18002e128  mov     rdi, r9
0x18002e12b  mov     rsi, r8
0x18002e12e  mov     r14, rdx
0x18002e131  mov     r15, rcx
0x18002e134  mov     [rbp+var_10], 0
0x18002e13b  mov     [rbp+arg_10], 0
0x18002e143  mov     rax, [r8]
0x18002e146  mov     rbx, [rax+40h]
0x18002e14a  lea     rcx, [rbp+arg_10]
0x18002e14e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e153  lea     rax, [rbp+arg_10]
0x18002e157  mov     qword ptr [rsp+40h+var_20], rax; int
0x18002e15c  mov     r9d, 1
0x18002e162  mov     r8, [rbp+arg_20]
0x18002e166  mov     rdx, rdi
0x18002e169  mov     rcx, rsi
0x18002e16c  mov     rax, rbx
0x18002e16f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e174  mov     rcx, [rbp+28h]; this
0x18002e178  test    eax, eax
0x18002e17a  js      loc_18002E27D
0x18002e180  mov     r8, [rbp+arg_30]
0x18002e184  test    r8, r8
0x18002e187  jz      short loc_18002E195
0x18002e189  lea     rdx, [rbp+arg_10]
0x18002e18d  mov     rcx, r15
0x18002e190  call    ?_ApplyCtacOverridesOnQuery@RefreshContext@@AEAAXAEAV?$ComPtr@UIClientAttributes@Flighting@Internal@Windows@@@WRL@Microsoft@@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Z; RefreshContext::_ApplyCtacOverridesOnQuery(Microsoft::WRL::ComPtr<Windows::Internal::Flighting::IClientAttributes> &,Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *)
0x18002e195  mov     qword ptr [r14], 0
0x18002e19c  mov     [rbp+var_10], 1
0x18002e1a3  mov     rdi, [rbp+arg_10]
0x18002e1a7  mov     rax, [rdi]
0x18002e1aa  mov     rbx, [rax+38h]
0x18002e1ae  xor     ecx, ecx; string
0x18002e1b0  call    cs:__imp_WindowsDeleteString
0x18002e1b6  mov     qword ptr [r14], 0
0x18002e1bd  mov     rdx, r14
0x18002e1c0  mov     rcx, rdi
0x18002e1c3  mov     rax, rbx
0x18002e1c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e1cb  mov     rcx, [rbp+28h]; this
0x18002e1cf  test    eax, eax
0x18002e1d1  js      loc_18002E268
0x18002e1d7  lea     rcx, [rbp+arg_10]
0x18002e1db  call    ?_RemoveQueryTags@RefreshContext@@CAJAEAV?$ComPtr@UIClientAttributes@Flighting@Internal@Windows@@@WRL@Microsoft@@QEBQEBG_K@Z; RefreshContext::_RemoveQueryTags(Microsoft::WRL::ComPtr<Windows::Internal::Flighting::IClientAttributes> &,ushort const * const * const,unsigned __int64)
0x18002e1e0  mov     rcx, [rbp+28h]
0x18002e1e4  mov     rsi, [rbp+arg_28]
0x18002e1e8  test    eax, eax
0x18002e1ea  jns     short loc_18002E1F3
0x18002e1ec  mov     edx, 0BBh
0x18002e1f1  jmp     short loc_18002E229
0x18002e1f3  mov     rdi, [rbp+arg_10]
0x18002e1f7  mov     rax, [rdi]
0x18002e1fa  mov     rbx, [rax+38h]
0x18002e1fe  mov     rcx, [rsi]; string
0x18002e201  call    cs:__imp_WindowsDeleteString
0x18002e207  mov     qword ptr [rsi], 0
0x18002e20e  mov     rdx, rsi
0x18002e211  mov     rcx, rdi
0x18002e214  mov     rax, rbx
0x18002e217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e21c  mov     rcx, [rbp+28h]; this
0x18002e220  test    eax, eax
0x18002e222  jns     short loc_18002E24B
0x18002e224  mov     edx, 0BEh; void *
0x18002e229  mov     r9d, eax; char *
0x18002e22c  lea     r8, aOnecoreBaseFli_20; "onecore\\base\\flighting\\onesettings\\"...
0x18002e233  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002e238  xor     r8d, r8d; unsigned int
0x18002e23b  lea     rdx, String1; unsigned __int16 *
0x18002e242  mov     rcx, rsi; this
0x18002e245  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18002e24a  nop
0x18002e24b  lea     rcx, [rbp+arg_10]
0x18002e24f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e254  mov     rax, r14
0x18002e257  mov     rbx, [rsp+40h+arg_0]
0x18002e25c  add     rsp, 40h
0x18002e260  pop     r15
0x18002e262  pop     r14
0x18002e264  pop     rdi
0x18002e265  pop     rsi
0x18002e266  pop     rbp
0x18002e267  retn
0x18002e268  mov     r9d, eax; char *
0x18002e26b  lea     r8, aOnecoreBaseFli_20; "onecore\\base\\flighting\\onesettings\\"...
0x18002e272  mov     edx, 0B9h; void *
0x18002e277  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002e27d  mov     r9d, eax; char *
0x18002e280  lea     r8, aOnecoreBaseFli_20; "onecore\\base\\flighting\\onesettings\\"...
0x18002e287  mov     edx, 0AFh; void *
0x18002e28c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
