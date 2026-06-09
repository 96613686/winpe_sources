# RefreshContext::_GetQueryParamsOld(Windows::Internal::Flighting::ICommonTargetingAttributesFactory *,HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *)

- ea: `0x18002e298`
- end: `0x18002e3b3`
- name: `?_GetQueryParamsOld@RefreshContext@@AEAA?AVHString@Wrappers@WRL@Microsoft@@PEAUICommonTargetingAttributesFactory@Flighting@Internal@Windows@@PEAUHSTRING__@@1PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@9@@Z`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b3a0`

## callees

- `0x180005f50`
- `0x1800101fc`
- `0x18002dca8`
- `0x18002e298`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e345`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e345`

## string_xrefs

- `0x18002e38c`: `onecore\base\flighting\onesettings\libs\configurationsmanager\refreshcontext.cpp`
- `0x18002e3a1`: `onecore\base\flighting\onesettings\libs\configurationsmanager\refreshcontext.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall RefreshContext::_GetQueryParamsOld(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 (__fastcall ***a6)(_QWORD, GUID *, __int64 *))
{
  __int64 (__fastcall *v10)(__int64, __int64, __int64, __int64); // rbx
  int v11; // eax
  __int64 (__fastcall ***v12)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v13)(_QWORD, GUID *, __int64); // rbx
  int v14; // eax
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 (__fastcall ***v17)(_QWORD, GUID *, __int64); // [rsp+70h] [rbp+18h] BYREF

  v17 = 0;
  v10 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)a3 + 64LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  v11 = v10(a3, a4, a5, 1);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x97,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\refreshcontext.cpp",
      (const char *)(unsigned int)v11,
      (int)&v17);
  if ( a6 )
    RefreshContext::_ApplyCtacOverridesOnQuery(a1, &v17, a6);
  *a2 = 0;
  v12 = v17;
  v13 = (*v17)[7];
  WindowsDeleteString(0);
  *a2 = 0;
  v14 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), _QWORD *))v13)(v12, a2);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA1,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\refreshcontext.cpp",
      (const char *)(unsigned int)v14,
      (int)&v17);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  return a2;
}

```

## disassembly

```asm
0x18002e298  mov     rax, rsp
0x18002e29b  mov     [rax+8], rbx
0x18002e29f  mov     [rax+20h], rbp
0x18002e2a3  mov     [rax+10h], rdx
0x18002e2a7  push    rsi
0x18002e2a8  push    rdi
0x18002e2a9  push    r14
0x18002e2ab  sub     rsp, 40h
0x18002e2af  mov     rdi, r9
0x18002e2b2  mov     rsi, r8
0x18002e2b5  mov     r14, rdx
0x18002e2b8  mov     rbp, rcx
0x18002e2bb  mov     dword ptr [rax-28h], 0
0x18002e2c2  mov     qword ptr [rax+18h], 0
0x18002e2ca  mov     rax, [r8]
0x18002e2cd  mov     rbx, [rax+40h]
0x18002e2d1  lea     rcx, [rsp+58h+arg_10]
0x18002e2d6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e2db  lea     rax, [rsp+58h+arg_10]
0x18002e2e0  mov     qword ptr [rsp+58h+var_38], rax; int
0x18002e2e5  mov     r9d, 1
0x18002e2eb  mov     r8, [rsp+58h+arg_20]
0x18002e2f3  mov     rdx, rdi
0x18002e2f6  mov     rcx, rsi
0x18002e2f9  mov     rax, rbx
0x18002e2fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e301  mov     rcx, [rsp+58h]; this
0x18002e306  test    eax, eax
0x18002e308  js      loc_18002E39E
0x18002e30e  mov     r8, [rsp+58h+arg_28]
0x18002e316  test    r8, r8
0x18002e319  jz      short loc_18002E328
0x18002e31b  lea     rdx, [rsp+58h+arg_10]
0x18002e320  mov     rcx, rbp
0x18002e323  call    ?_ApplyCtacOverridesOnQuery@RefreshContext@@AEAAXAEAV?$ComPtr@UIClientAttributes@Flighting@Internal@Windows@@@WRL@Microsoft@@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Z; RefreshContext::_ApplyCtacOverridesOnQuery(Microsoft::WRL::ComPtr<Windows::Internal::Flighting::IClientAttributes> &,Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *)
0x18002e328  mov     qword ptr [r14], 0
0x18002e32f  mov     [rsp+58h+var_28], 1
0x18002e337  mov     rdi, [rsp+58h+arg_10]
0x18002e33c  mov     rax, [rdi]
0x18002e33f  mov     rbx, [rax+38h]
0x18002e343  xor     ecx, ecx; string
0x18002e345  call    cs:__imp_WindowsDeleteString
0x18002e34b  mov     qword ptr [r14], 0
0x18002e352  mov     rdx, r14
0x18002e355  mov     rcx, rdi
0x18002e358  mov     rax, rbx
0x18002e35b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e360  mov     rcx, [rsp+58h]; this
0x18002e365  test    eax, eax
0x18002e367  js      short loc_18002E389
0x18002e369  lea     rcx, [rsp+58h+arg_10]
0x18002e36e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e373  mov     rax, r14
0x18002e376  mov     rbx, [rsp+58h+arg_0]
0x18002e37b  mov     rbp, [rsp+58h+arg_18]
0x18002e380  add     rsp, 40h
0x18002e384  pop     r14
0x18002e386  pop     rdi
0x18002e387  pop     rsi
0x18002e388  retn
0x18002e389  mov     r9d, eax; char *
0x18002e38c  lea     r8, aOnecoreBaseFli_20; "onecore\\base\\flighting\\onesettings\\"...
0x18002e393  mov     edx, 0A1h; void *
0x18002e398  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002e39e  mov     r9d, eax; char *
0x18002e3a1  lea     r8, aOnecoreBaseFli_20; "onecore\\base\\flighting\\onesettings\\"...
0x18002e3a8  mov     edx, 97h; void *
0x18002e3ad  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
