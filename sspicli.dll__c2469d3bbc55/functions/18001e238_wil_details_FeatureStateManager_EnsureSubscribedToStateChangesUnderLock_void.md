# wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock(void)

- ea: `0x18001e238`
- end: `0x18001e2ad`
- name: `?EnsureSubscribedToStateChangesUnderLock@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `117`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180010a94`

## callees

- `0x180012f7c`
- `0x18001e238`
- `0x180023010`

## string_xrefs

- `0x18001e265`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
bool __fastcall wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock(
        wil::details::FeatureStateManager *this)
{
  _QWORD *v1; // rbx
  __int64 (*NtDllProcedureAddress)(void); // rax
  int v4; // eax

  v1 = (_QWORD *)((char *)this + 144);
  if ( *((_QWORD *)this + 18) )
  {
    v4 = 0;
  }
  else
  {
    NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
    *v1 = 0;
    if ( NtDllProcedureAddress
      || (NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlRegisterFeatureConfigurationChangeNotification"),
          (g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)NtDllProcedureAddress) != 0) )
    {
      v4 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), wil::details::FeatureStateManager *, _QWORD, _QWORD *))NtDllProcedureAddress)(
             _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
             this,
             0,
             v1);
    }
    else
    {
      v4 = -1073741511;
    }
  }
  return v4 == 0;
}

```

## disassembly

```asm
0x18001e238  mov     [rsp+arg_0], rbx
0x18001e23d  push    rdi
0x18001e23e  sub     rsp, 30h
0x18001e242  lea     rbx, [rcx+90h]
0x18001e249  mov     rdi, rcx
0x18001e24c  cmp     qword ptr [rbx], 0
0x18001e250  jnz     short loc_18001E29B
0x18001e252  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18001e259  mov     qword ptr [rbx], 0
0x18001e260  test    rax, rax
0x18001e263  jnz     short loc_18001E284
0x18001e265  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18001e26c  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001e271  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001e278  test    rax, rax
0x18001e27b  jnz     short loc_18001E284
0x18001e27d  mov     eax, 0C0000139h
0x18001e282  jmp     short loc_18001E29D
0x18001e284  mov     r9, rbx
0x18001e287  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18001e28e  xor     r8d, r8d
0x18001e291  mov     rdx, rdi
0x18001e294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e299  jmp     short loc_18001E29D
0x18001e29b  xor     eax, eax
0x18001e29d  mov     rbx, [rsp+38h+arg_0]
0x18001e2a2  test    eax, eax
0x18001e2a4  setz    al
0x18001e2a7  add     rsp, 30h
0x18001e2ab  pop     rdi
0x18001e2ac  retn
```
