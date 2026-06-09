# EvaluateContentApplicabilityForUUP(IUpdateCollection *,wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64> &)

- ea: `0x140006a44`
- end: `0x140006b20`
- name: `?EvaluateContentApplicabilityForUUP@@YAJPEAUIUpdateCollection@@AEAV?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(struct IUpdateCollection *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1400075b0`

## callees

- `0x140005c70`
- `0x140006a44`
- `0x14000f294`
- `0x140013490`
- `0x140015010`

## string_xrefs

- `0x140006a62`: `Invalid argument: updates is NULL`
- `0x140006ae5`: `Failed to evaluate content applicability for UUP update`

## pseudocode

```c
__int64 __fastcall EvaluateContentApplicabilityForUUP(struct IUpdateCollection *a1, __int64 *a2)
{
  int v4; // ebx
  struct IUpdate *v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = 0;
  if ( a1 )
  {
    ((void (__fastcall *)(struct IUpdateCollection *, _QWORD, struct IUpdate **))a1->lpVtbl->get_Item)(a1, 0, &v6);
    if ( (int)WusaSetSessionDataIfEligibleForContentApplicabilityCheck(v6, a2) >= 0 )
    {
      WusaLogDebugEventA(L"EvaluateContentApplicabilityForUUP", 549, "Starting UUP Content Applicability Check");
      v4 = CopyToCache(a1, 1);
      if ( v4 < 0 )
        WusaLogDebugEventA(
          L"EvaluateContentApplicabilityForUUP",
          552,
          "Failed to evaluate content applicability for UUP update");
    }
    else
    {
      WusaLogDebugEventA(
        L"EvaluateContentApplicabilityForUUP",
        543,
        "Failed to set session data. Skip Evaluate Content Applicability");
      v4 = 0;
    }
  }
  else
  {
    WusaLogDebugEventA(L"EvaluateContentApplicabilityForUUP", 537, "Invalid argument: updates is NULL");
    v4 = -2147024809;
  }
  if ( v6 )
    ((void (__fastcall *)(struct IUpdate *))v6->lpVtbl->Release)(v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140006a44  mov     [rsp+arg_8], rbx
0x140006a49  push    rdi
0x140006a4a  sub     rsp, 20h
0x140006a4e  mov     [rsp+28h+arg_0], 0
0x140006a57  mov     rdi, rdx
0x140006a5a  mov     rbx, rcx
0x140006a5d  test    rcx, rcx
0x140006a60  jnz     short loc_140006A81
0x140006a62  lea     r8, aInvalidArgumen_2; "Invalid argument: updates is NULL"
0x140006a69  mov     edx, 219h
0x140006a6e  lea     rcx, aEvaluateconten; "EvaluateContentApplicabilityForUUP"
0x140006a75  call    WusaLogDebugEventA
0x140006a7a  mov     ebx, 80070057h
0x140006a7f  jmp     short loc_140006AFD
0x140006a81  mov     rax, [rcx]
0x140006a84  lea     r8, [rsp+28h+arg_0]
0x140006a89  xor     edx, edx
0x140006a8b  mov     rax, [rax+38h]
0x140006a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006a94  mov     rcx, [rsp+28h+arg_0]; struct IUpdate *
0x140006a99  mov     rdx, rdi
0x140006a9c  call    ?WusaSetSessionDataIfEligibleForContentApplicabilityCheck@@YAJPEAUIUpdate@@AEAV?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@@Z; WusaSetSessionDataIfEligibleForContentApplicabilityCheck(IUpdate *,wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64> &)
0x140006aa1  lea     rcx, aEvaluateconten; "EvaluateContentApplicabilityForUUP"
0x140006aa8  test    eax, eax
0x140006aaa  jns     short loc_140006AC1
0x140006aac  lea     r8, aFailedToSetSes; "Failed to set session data. Skip Evalua"...
0x140006ab3  mov     edx, 21Fh
0x140006ab8  call    WusaLogDebugEventA
0x140006abd  xor     ebx, ebx
0x140006abf  jmp     short loc_140006AFD
0x140006ac1  lea     r8, aStartingUupCon; "Starting UUP Content Applicability Chec"...
0x140006ac8  mov     edx, 225h
0x140006acd  call    WusaLogDebugEventA
0x140006ad2  mov     edx, 1; int
0x140006ad7  mov     rcx, rbx; struct IUpdateCollection *
0x140006ada  call    ?CopyToCache@@YAJPEAUIUpdateCollection@@H@Z; CopyToCache(IUpdateCollection *,int)
0x140006adf  mov     ebx, eax
0x140006ae1  test    eax, eax
0x140006ae3  jns     short loc_140006AFD
0x140006ae5  lea     r8, aFailedToEvalua_0; "Failed to evaluate content applicabilit"...
0x140006aec  mov     edx, 228h
0x140006af1  lea     rcx, aEvaluateconten; "EvaluateContentApplicabilityForUUP"
0x140006af8  call    WusaLogDebugEventA
0x140006afd  mov     rcx, [rsp+28h+arg_0]
0x140006b02  test    rcx, rcx
0x140006b05  jz      short loc_140006B13
0x140006b07  mov     rdx, [rcx]
0x140006b0a  mov     rax, [rdx+10h]
0x140006b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b13  mov     eax, ebx
0x140006b15  mov     rbx, [rsp+28h+arg_8]
0x140006b1a  add     rsp, 20h
0x140006b1e  pop     rdi
0x140006b1f  retn
```
