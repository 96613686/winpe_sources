# WusaSetSessionDataIfEligibleForContentApplicabilityCheck(IUpdate *,wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64> &)

- ea: `0x14000f294`
- end: `0x14000f453`
- name: `?WusaSetSessionDataIfEligibleForContentApplicabilityCheck@@YAJPEAUIUpdate@@AEAV?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@@Z`
- size: `447`
- prototype: `__int64 __fastcall(struct IUpdate *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x140006a44`

## callees

- `0x14000db50`
- `0x14000e5f4`
- `0x14000e78c`
- `0x14000f294`
- `0x140013490`
- `0x140015010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000f43b`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f43b`
- `OLEAUT32!__imp_VariantInit` at `0x14000f2b7`
- `OLEAUT32!__imp_VariantInit` at `0x14000f2b7`
- `OLEAUT32!__imp_VariantClear` at `0x14000f418`
- `OLEAUT32!__imp_VariantClear` at `0x14000f418`

## string_xrefs

- `0x14000f2c2`: `update cannot be null`
- `0x14000f3f7`: `Update is not eligible for content applicability check`
- `0x14000f38e`: `Failed to get IUpdateInternalProperty interface`

## pseudocode

```c
__int64 __fastcall WusaSetSessionDataIfEligibleForContentApplicabilityCheck(struct IUpdate *a1, __int64 *a2)
{
  OLECHAR *v3; // rbx
  int v5; // edi
  const unsigned __int16 *v6; // rdx
  __int64 *v7; // rcx
  struct IUpdateVtbl *lpVtbl; // rax
  HRESULT (__stdcall *QueryInterface)(IUpdate *, const IID *const, void **); // rdi
  __int64 v10; // rax
  __int64 (__fastcall *v11)(__int64 *, __int64, __int128 *); // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-40h] BYREF
  __int128 v14; // [rsp+40h] [rbp-20h] BYREF
  IRecordInfo *pRecInfo; // [rsp+50h] [rbp-10h]
  __int64 *v16; // [rsp+80h] [rbp+20h] BYREF
  BSTR v17; // [rsp+90h] [rbp+30h] BYREF

  v3 = 0;
  v17 = 0;
  v16 = 0;
  VariantInit(&pvarg);
  if ( a1 )
  {
    if ( WusaIsUUPHandler(a1) && WusaIsUUPProductNameMatch(a1, v6) )
    {
      v5 = WusaGenerateSessionData(a2, &v17);
      if ( v5 >= 0 )
      {
        v3 = v17;
        WusaLogDebugEventA(L"WusaSetSessionDataIfEligibleForContentApplicabilityCheck", 899, "Session Data: %ls", v17);
        v7 = v16;
        lpVtbl = a1->lpVtbl;
        v16 = 0;
        QueryInterface = lpVtbl->QueryInterface;
        if ( v7 )
          (*(void (__fastcall **)(__int64 *))(*v7 + 16))(v7);
        v5 = ((__int64 (__fastcall *)(struct IUpdate *, GUID *, __int64 **))QueryInterface)(
               a1,
               &GUID_f7a9d4c1_ea19_4c5a_bf5d_c4173d2734c2,
               &v16);
        if ( v5 >= 0 )
        {
          pvarg.vt = 8;
          pvarg.llVal = (LONGLONG)v3;
          v3 = 0;
          v10 = *v16;
          pRecInfo = pvarg.pRecInfo;
          v11 = *(__int64 (__fastcall **)(__int64 *, __int64, __int128 *))(v10 + 32);
          v14 = *(_OWORD *)&pvarg.vt;
          v5 = v11(v16, 4, &v14);
          if ( v5 < 0 )
            WusaLogDebugEventA(
              L"WusaSetSessionDataIfEligibleForContentApplicabilityCheck",
              909,
              "Failed to set session data");
        }
        else
        {
          WusaLogDebugEventA(
            L"WusaSetSessionDataIfEligibleForContentApplicabilityCheck",
            903,
            "Failed to get IUpdateInternalProperty interface");
        }
      }
      else
      {
        WusaLogDebugEventA(
          L"WusaSetSessionDataIfEligibleForContentApplicabilityCheck",
          897,
          "Failed to generate session data");
        v3 = v17;
      }
    }
    else
    {
      WusaLogDebugEventA(
        L"WusaSetSessionDataIfEligibleForContentApplicabilityCheck",
        893,
        "Update is not eligible for content applicability check");
      v5 = -2147024846;
    }
  }
  else
  {
    WusaLogDebugEventA(L"WusaSetSessionDataIfEligibleForContentApplicabilityCheck", 890, "update cannot be null");
    v5 = -2147024809;
  }
  VariantClear(&pvarg);
  if ( v16 )
    (*(void (__fastcall **)(__int64 *))(*v16 + 16))(v16);
  if ( v3 )
    SysFreeString(v3);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000f294  mov     [rsp-18h+arg_8], rbx
0x14000f299  push    rbp
0x14000f29a  push    rsi
0x14000f29b  push    rdi
0x14000f29c  mov     rbp, rsp
0x14000f29f  sub     rsp, 60h
0x14000f2a3  mov     rsi, rcx
0x14000f2a6  xor     ebx, ebx
0x14000f2a8  lea     rcx, [rbp+pvarg]; pvarg
0x14000f2ac  mov     [rbp+arg_10], rbx
0x14000f2b0  mov     [rbp+arg_0], rbx
0x14000f2b4  mov     rdi, rdx
0x14000f2b7  call    cs:__imp_VariantInit
0x14000f2bd  test    rsi, rsi
0x14000f2c0  jnz     short loc_14000F2E4
0x14000f2c2  lea     r8, aUpdateCannotBe; "update cannot be null"
0x14000f2c9  mov     edx, 37Ah
0x14000f2ce  lea     rcx, aWusasetsession; "WusaSetSessionDataIfEligibleForContentA"...
0x14000f2d5  call    WusaLogDebugEventA
0x14000f2da  mov     edi, 80070057h
0x14000f2df  jmp     loc_14000F414
0x14000f2e4  mov     rcx, rsi; struct IUpdate *
0x14000f2e7  call    ?WusaIsUUPHandler@@YA_NPEAUIUpdate@@@Z; WusaIsUUPHandler(IUpdate *)
0x14000f2ec  test    al, al
0x14000f2ee  jz      loc_14000F3F7
0x14000f2f4  mov     rcx, rsi; struct IUpdate *
0x14000f2f7  call    ?WusaIsUUPProductNameMatch@@YA_NPEAUIUpdate@@PEBG@Z; WusaIsUUPProductNameMatch(IUpdate *,ushort const *)
0x14000f2fc  test    al, al
0x14000f2fe  jz      loc_14000F3F7
0x14000f304  lea     rdx, [rbp+arg_10]
0x14000f308  mov     rcx, rdi
0x14000f30b  call    ?WusaGenerateSessionData@@YAJAEAV?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@PEAPEAG@Z; WusaGenerateSessionData(wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64> &,ushort * *)
0x14000f310  lea     rcx, aWusasetsession; "WusaSetSessionDataIfEligibleForContentA"...
0x14000f317  mov     edi, eax
0x14000f319  test    eax, eax
0x14000f31b  jns     short loc_14000F337
0x14000f31d  lea     r8, aFailedToGenera; "Failed to generate session data"
0x14000f324  mov     edx, 381h
0x14000f329  call    WusaLogDebugEventA
0x14000f32e  mov     rbx, [rbp+arg_10]
0x14000f332  jmp     loc_14000F414
0x14000f337  mov     rbx, [rbp+arg_10]
0x14000f33b  lea     r8, aSessionDataLs; "Session Data: %ls"
0x14000f342  mov     r9, rbx
0x14000f345  mov     edx, 383h
0x14000f34a  call    WusaLogDebugEventA
0x14000f34f  mov     rcx, [rbp+arg_0]
0x14000f353  mov     rax, [rsi]
0x14000f356  mov     [rbp+arg_0], 0
0x14000f35e  mov     rdi, [rax]
0x14000f361  test    rcx, rcx
0x14000f364  jz      short loc_14000F372
0x14000f366  mov     rdx, [rcx]
0x14000f369  mov     rax, [rdx+10h]
0x14000f36d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f372  lea     r8, [rbp+arg_0]
0x14000f376  mov     rcx, rsi
0x14000f379  lea     rdx, _GUID_f7a9d4c1_ea19_4c5a_bf5d_c4173d2734c2
0x14000f380  mov     rax, rdi
0x14000f383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f388  mov     edi, eax
0x14000f38a  test    eax, eax
0x14000f38c  jns     short loc_14000F3A8
0x14000f38e  lea     r8, aFailedToGetIup_1; "Failed to get IUpdateInternalProperty i"...
0x14000f395  mov     edx, 387h
0x14000f39a  lea     rcx, aWusasetsession; "WusaSetSessionDataIfEligibleForContentA"...
0x14000f3a1  call    WusaLogDebugEventA
0x14000f3a6  jmp     short loc_14000F414
0x14000f3a8  mov     rcx, [rbp+arg_0]
0x14000f3ac  lea     r8, [rbp+var_20]
0x14000f3b0  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x14000f3b5  mov     eax, 8
0x14000f3ba  mov     word ptr [rbp+pvarg], ax
0x14000f3be  mov     rax, rbx
0x14000f3c1  mov     qword ptr [rbp+pvarg+8], rax
0x14000f3c5  xor     ebx, ebx
0x14000f3c7  mov     rax, [rcx]
0x14000f3ca  movups  xmm0, xmmword ptr [rbp+pvarg]
0x14000f3ce  lea     edx, [rbx+4]
0x14000f3d1  movsd   [rbp+var_10], xmm1
0x14000f3d6  mov     rax, [rax+20h]
0x14000f3da  movaps  [rbp+var_20], xmm0
0x14000f3de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f3e3  mov     edi, eax
0x14000f3e5  test    eax, eax
0x14000f3e7  jns     short loc_14000F414
0x14000f3e9  lea     r8, aFailedToSetSes_0; "Failed to set session data"
0x14000f3f0  mov     edx, 38Dh
0x14000f3f5  jmp     short loc_14000F39A
0x14000f3f7  lea     r8, aUpdateIsNotEli; "Update is not eligible for content appl"...
0x14000f3fe  mov     edx, 37Dh
0x14000f403  lea     rcx, aWusasetsession; "WusaSetSessionDataIfEligibleForContentA"...
0x14000f40a  call    WusaLogDebugEventA
0x14000f40f  mov     edi, 80070032h
0x14000f414  lea     rcx, [rbp+pvarg]; pvarg
0x14000f418  call    cs:__imp_VariantClear
0x14000f41e  mov     rcx, [rbp+arg_0]
0x14000f422  test    rcx, rcx
0x14000f425  jz      short loc_14000F433
0x14000f427  mov     rax, [rcx]
0x14000f42a  mov     rax, [rax+10h]
0x14000f42e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f433  test    rbx, rbx
0x14000f436  jz      short loc_14000F441
0x14000f438  mov     rcx, rbx; bstrString
0x14000f43b  call    cs:__imp_SysFreeString
0x14000f441  mov     rbx, [rsp+60h+arg_8]
0x14000f449  mov     eax, edi
0x14000f44b  add     rsp, 60h
0x14000f44f  pop     rdi
0x14000f450  pop     rsi
0x14000f451  pop     rbp
0x14000f452  retn
```
