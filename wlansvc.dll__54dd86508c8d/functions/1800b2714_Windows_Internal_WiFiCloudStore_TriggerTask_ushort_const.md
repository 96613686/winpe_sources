# Windows::Internal::WiFiCloudStore::TriggerTask(ushort const *)

- ea: `0x1800b2714`
- end: `0x1800b2a7f`
- name: `?TriggerTask@WiFiCloudStore@Internal@Windows@@YAJPEBG@Z`
- size: `875`
- prototype: `__int64 __fastcall(OLECHAR *psz, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180206d04`

## callees

- `0x1800727d4`
- `0x1800b2714`
- `0x1800b2a88`
- `0x1800f225c`
- `0x18022c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b275a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b275a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b2833`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b28c3`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b2958`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b2833`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b28c3`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b2958`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b29fb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b2a2b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b29fb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b2a2b`
- `OLEAUT32!__imp_VariantInit` at `0x1800b2785`
- `OLEAUT32!__imp_VariantInit` at `0x1800b2785`
- `OLEAUT32!__imp_VariantClear` at `0x1800b2a37`
- `OLEAUT32!__imp_VariantClear` at `0x1800b2a37`

## string_xrefs

- `0x1800b276f`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`
- `0x1800b281a`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`
- `0x1800b284e`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`
- `0x1800b28aa`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`
- `0x1800b28de`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`
- `0x1800b293a`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`
- `0x1800b2970`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`
- `0x1800b29c0`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Windows::Internal::WiFiCloudStore::TriggerTask(OLECHAR *psz, const unsigned __int16 *a2)
{
  HRESULT v3; // eax
  int v4; // eax
  const char *v5; // r9
  OLECHAR *v6; // r14
  LPVOID v7; // rdi
  __int64 (__fastcall *v8)(LPVOID, OLECHAR *, __int64 *); // rbx
  int v9; // eax
  OLECHAR *v10; // rsi
  const char *v11; // r9
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, OLECHAR *, __int64 *); // rbx
  int v14; // eax
  const char *v15; // r9
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  const char *v19; // r9
  LPVOID v20; // rcx
  __int64 result; // rax
  int ppv; // [rsp+20h] [rbp-E8h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-D8h] BYREF
  VARIANTARG v24; // [rsp+50h] [rbp-B8h] BYREF
  OLECHAR *v25; // [rsp+70h] [rbp-98h]
  OLECHAR *v26; // [rsp+78h] [rbp-90h]
  VARIANTARG v27; // [rsp+80h] [rbp-88h] BYREF
  VARIANTARG v28; // [rsp+A0h] [rbp-68h] BYREF
  VARIANTARG v29; // [rsp+C0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]
  LPVOID v31; // [rsp+118h] [rbp+10h] BYREF
  __int64 v32; // [rsp+120h] [rbp+18h] BYREF
  __int64 v33; // [rsp+128h] [rbp+20h] BYREF

  v31 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  v3 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &v31);
  try
  {
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x30,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
        (const char *)(unsigned int)v3,
        ppv);
    VariantInit(&pvarg);
    v27 = pvarg;
    v28 = pvarg;
    v29 = pvarg;
    v24 = pvarg;
    v4 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*(_QWORD *)v31 + 80LL))(
           v31,
           &v24,
           &v29,
           &v28);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
        (const char *)(unsigned int)v4,
        (int)&v27);
    v6 = SysAllocString(L"\\Microsoft\\Windows\\WlanSvc");
    v25 = v6;
    if ( !v6 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x36,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
        v5);
    v33 = 0;
    v7 = v31;
    v8 = *(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int64 *))(*(_QWORD *)v31 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
    v9 = v8(v7, v6, &v33);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x39,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
        (const char *)(unsigned int)v9,
        (int)&v27);
    v10 = SysAllocString(L"CDSSync");
    v26 = v10;
    if ( !v10 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x3C,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
        v11);
    v32 = 0;
    v12 = v33;
    v13 = *(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v33 + 104LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
    v14 = v13(v12, v10, &v32);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
        (const char *)(unsigned int)v14,
        (int)&v27);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(psz);
    if ( !pvarg.llVal )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x43,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
        v15);
    v24 = pvarg;
    v16 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, _QWORD))(*(_QWORD *)v32 + 96LL))(v32, &v24, 0);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x45,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
        (const char *)(unsigned int)v16,
        (int)&v27);
    v17 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    SysFreeString(v10);
    v18 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    SysFreeString(v6);
    VariantClear(&pvarg);
    v20 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
    }
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v31) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x48,
                     (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
                     v19);
    return (unsigned int)v31;
  }
  return result;
}

```

## disassembly

```asm
0x1800b2714  mov     rax, rsp
0x1800b2717  push    rbx
0x1800b2718  push    rsi
0x1800b2719  push    rdi
0x1800b271a  push    r14
0x1800b271c  push    r15
0x1800b271e  sub     rsp, 0E0h
0x1800b2725  mov     r15, rcx
0x1800b2728  mov     qword ptr [rax+10h], 0
0x1800b2730  lea     rcx, [rax+10h]
0x1800b2734  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b2739  lea     rax, [rsp+108h+arg_8]
0x1800b2741  mov     qword ptr [rsp+108h+ppv], rax; int
0x1800b2746  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800b274d  xor     edx, edx; pUnkOuter
0x1800b274f  lea     r8d, [rdx+1]; dwClsContext
0x1800b2753  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800b275a  call    cs:__imp_CoCreateInstance
0x1800b2760  mov     rcx, [rsp+108h]; this
0x1800b2768  test    eax, eax
0x1800b276a  jns     short loc_1800B2780
0x1800b276c  mov     r9d, eax; char *
0x1800b276f  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x1800b2776  mov     edx, 30h ; '0'; void *
0x1800b277b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b2780  lea     rcx, [rsp+108h+pvarg]; pvarg
0x1800b2785  call    cs:__imp_VariantInit
0x1800b278b  nop
0x1800b278c  mov     rcx, [rsp+108h+arg_8]
0x1800b2794  movups  xmm1, xmmword ptr [rsp+108h+pvarg]
0x1800b2799  movaps  xmmword ptr [rsp+108h+var_88], xmm1
0x1800b27a1  movsd   xmm0, qword ptr [rsp+108h+pvarg+10h]
0x1800b27a7  movsd   [rsp+108h+var_78], xmm0
0x1800b27b0  movaps  [rsp+108h+var_68], xmm1
0x1800b27b8  movsd   [rsp+108h+var_58], xmm0
0x1800b27c1  movaps  [rsp+108h+var_48], xmm1
0x1800b27c9  movsd   [rsp+108h+var_38], xmm0
0x1800b27d2  movaps  [rsp+108h+var_B8], xmm1
0x1800b27d7  movsd   [rsp+108h+var_A8], xmm0
0x1800b27dd  mov     rax, [rcx]
0x1800b27e0  lea     rdx, [rsp+108h+var_88]
0x1800b27e8  mov     qword ptr [rsp+108h+ppv], rdx; int
0x1800b27ed  lea     r9, [rsp+108h+var_68]
0x1800b27f5  lea     r8, [rsp+108h+var_48]
0x1800b27fd  lea     rdx, [rsp+108h+var_B8]
0x1800b2802  mov     rax, [rax+50h]
0x1800b2806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b280b  mov     rcx, [rsp+108h]; this
0x1800b2813  test    eax, eax
0x1800b2815  jns     short loc_1800B282C
0x1800b2817  mov     r9d, eax; char *
0x1800b281a  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x1800b2821  mov     edx, 33h ; '3'; void *
0x1800b2826  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b282c  lea     rcx, aMicrosoftWindo; "\\Microsoft\\Windows\\WlanSvc"
0x1800b2833  call    cs:__imp_SysAllocString
0x1800b2839  mov     r14, rax
0x1800b283c  mov     [rsp+108h+var_98], rax
0x1800b2841  mov     rcx, [rsp+108h]; this
0x1800b2849  test    rax, rax
0x1800b284c  jnz     short loc_1800B285D
0x1800b284e  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x1800b2855  lea     edx, [rax+36h]; void *
0x1800b2858  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800b285d  mov     [rsp+108h+arg_18], 0
0x1800b2869  mov     rdi, [rsp+108h+arg_8]
0x1800b2871  mov     rax, [rdi]
0x1800b2874  mov     rbx, [rax+38h]
0x1800b2878  lea     rcx, [rsp+108h+arg_18]
0x1800b2880  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b2885  lea     r8, [rsp+108h+arg_18]
0x1800b288d  mov     rdx, r14
0x1800b2890  mov     rcx, rdi
0x1800b2893  mov     rax, rbx
0x1800b2896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b289b  mov     rcx, [rsp+108h]; this
0x1800b28a3  test    eax, eax
0x1800b28a5  jns     short loc_1800B28BC
0x1800b28a7  mov     r9d, eax; char *
0x1800b28aa  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x1800b28b1  mov     edx, 39h ; '9'; void *
0x1800b28b6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b28bc  lea     rcx, aCdssync; "CDSSync"
0x1800b28c3  call    cs:__imp_SysAllocString
0x1800b28c9  mov     rsi, rax
0x1800b28cc  mov     [rsp+108h+var_90], rax
0x1800b28d1  mov     rcx, [rsp+108h]; this
0x1800b28d9  test    rax, rax
0x1800b28dc  jnz     short loc_1800B28ED
0x1800b28de  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x1800b28e5  lea     edx, [rax+3Ch]; void *
0x1800b28e8  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800b28ed  mov     [rsp+108h+arg_10], 0
0x1800b28f9  mov     rdi, [rsp+108h+arg_18]
0x1800b2901  mov     rax, [rdi]
0x1800b2904  mov     rbx, [rax+68h]
0x1800b2908  lea     rcx, [rsp+108h+arg_10]
0x1800b2910  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b2915  lea     r8, [rsp+108h+arg_10]
0x1800b291d  mov     rdx, rsi
0x1800b2920  mov     rcx, rdi
0x1800b2923  mov     rax, rbx
0x1800b2926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b292b  mov     rcx, [rsp+108h]; this
0x1800b2933  test    eax, eax
0x1800b2935  jns     short loc_1800B294B
0x1800b2937  mov     r9d, eax; char *
0x1800b293a  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x1800b2941  mov     edx, 3Fh ; '?'; void *
0x1800b2946  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b294b  mov     eax, 8
0x1800b2950  mov     word ptr [rsp+108h+pvarg], ax
0x1800b2955  mov     rcx, r15; psz
0x1800b2958  call    cs:__imp_SysAllocString
0x1800b295e  mov     qword ptr [rsp+108h+pvarg+8], rax
0x1800b2963  mov     rcx, [rsp+108h]; this
0x1800b296b  test    rax, rax
0x1800b296e  jnz     short loc_1800B297F
0x1800b2970  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x1800b2977  lea     edx, [rax+43h]; void *
0x1800b297a  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800b297f  mov     rcx, [rsp+108h+arg_10]
0x1800b2987  movups  xmm0, xmmword ptr [rsp+108h+pvarg]
0x1800b298c  movaps  [rsp+108h+var_B8], xmm0
0x1800b2991  movsd   xmm1, qword ptr [rsp+108h+pvarg+10h]
0x1800b2997  movsd   [rsp+108h+var_A8], xmm1
0x1800b299d  mov     rax, [rcx]
0x1800b29a0  xor     r8d, r8d
0x1800b29a3  lea     rdx, [rsp+108h+var_B8]
0x1800b29a8  mov     rax, [rax+60h]
0x1800b29ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b29b1  mov     rcx, [rsp+108h]; this
0x1800b29b9  test    eax, eax
0x1800b29bb  jns     short loc_1800B29D2
0x1800b29bd  mov     r9d, eax; char *
0x1800b29c0  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x1800b29c7  mov     edx, 45h ; 'E'; void *
0x1800b29cc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b29d2  mov     rcx, [rsp+108h+arg_10]
0x1800b29da  test    rcx, rcx
0x1800b29dd  jz      short loc_1800B29F8
0x1800b29df  mov     [rsp+108h+arg_10], 0
0x1800b29eb  mov     rax, [rcx]
0x1800b29ee  mov     rax, [rax+10h]
0x1800b29f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b29f7  nop
0x1800b29f8  mov     rcx, rsi; bstrString
0x1800b29fb  call    cs:__imp_SysFreeString
0x1800b2a01  nop
0x1800b2a02  mov     rcx, [rsp+108h+arg_18]
0x1800b2a0a  test    rcx, rcx
0x1800b2a0d  jz      short loc_1800B2A28
0x1800b2a0f  mov     [rsp+108h+arg_18], 0
0x1800b2a1b  mov     rax, [rcx]
0x1800b2a1e  mov     rax, [rax+10h]
0x1800b2a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2a27  nop
0x1800b2a28  mov     rcx, r14; bstrString
0x1800b2a2b  call    cs:__imp_SysFreeString
0x1800b2a31  nop
0x1800b2a32  lea     rcx, [rsp+108h+pvarg]; pvarg
0x1800b2a37  call    cs:__imp_VariantClear
0x1800b2a3d  nop
0x1800b2a3e  mov     rcx, [rsp+108h+arg_8]
0x1800b2a46  test    rcx, rcx
0x1800b2a49  jz      short loc_1800B2A64
0x1800b2a4b  mov     [rsp+108h+arg_8], 0
0x1800b2a57  mov     rax, [rcx]
0x1800b2a5a  mov     rax, [rax+10h]
0x1800b2a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2a63  nop
0x1800b2a64  xor     eax, eax
0x1800b2a66  jmp     short loc_1800B2A6F
0x1800b2a68  mov     eax, dword ptr [rsp+108h+arg_8]
0x1800b2a6f  add     rsp, 0E0h
0x1800b2a76  pop     r15
0x1800b2a78  pop     r14
0x1800b2a7a  pop     rdi
0x1800b2a7b  pop     rsi
0x1800b2a7c  pop     rbx
0x1800b2a7d  retn
```
