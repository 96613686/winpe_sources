# wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock(void)

- ea: `0x180018484`
- end: `0x180018502`
- name: `?EnsureSubscribedToStateChangesUnderLock@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `126`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180018414`

## callees

- `0x180018484`
- `0x180018960`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800184c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800184c0`

## string_xrefs

- `0x1800184b9`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
bool __fastcall wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock(
        wil::details::FeatureStateManager *this)
{
  _QWORD *v2; // rbx
  FARPROC ProcAddress; // rax
  HMODULE NtDllModuleHandle; // rax
  int v5; // eax

  v2 = (_QWORD *)((char *)this + 144);
  if ( *((_QWORD *)this + 18) )
  {
    v5 = 0;
  }
  else
  {
    *v2 = 0;
    ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
    if ( g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
      || (NtDllModuleHandle = wil_details_GetNtDllModuleHandle(),
          ProcAddress = GetProcAddress(NtDllModuleHandle, "RtlRegisterFeatureConfigurationChangeNotification"),
          (g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)ProcAddress) != 0) )
    {
      v5 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(), wil::details::FeatureStateManager *, _QWORD, _QWORD *))ProcAddress)(
             `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
             this,
             0,
             v2);
    }
    else
    {
      v5 = -1073741511;
    }
  }
  return v5 == 0;
}

```

## disassembly

```asm
0x180018484  mov     [rsp+arg_0], rbx
0x180018489  push    rdi
0x18001848a  sub     rsp, 30h
0x18001848e  mov     rdi, rcx
0x180018491  lea     rbx, [rcx+90h]
0x180018498  cmp     qword ptr [rbx], 0
0x18001849c  jnz     short loc_1800184FE
0x18001849e  mov     qword ptr [rbx], 0
0x1800184a5  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1800184ac  test    rax, rax
0x1800184af  jnz     short loc_1800184D2
0x1800184b1  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1800184b6  mov     rcx, rax; hModule
0x1800184b9  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800184c0  call    cs:__imp_GetProcAddress
0x1800184c6  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800184cd  test    rax, rax
0x1800184d0  jz      short loc_1800184F7
0x1800184d2  mov     r9, rbx
0x1800184d5  xor     r8d, r8d
0x1800184d8  mov     rdx, rdi
0x1800184db  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToStateChangesUnderLock@FeatureStateManager@details@wil@@CAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@5@PEAX@Z@SA@1@Z; `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,void *)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x1800184e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184e7  test    eax, eax
0x1800184e9  setz    al
0x1800184ec  mov     rbx, [rsp+38h+arg_0]
0x1800184f1  add     rsp, 30h
0x1800184f5  pop     rdi
0x1800184f6  retn
0x1800184f7  mov     eax, 0C0000139h
0x1800184fc  jmp     short loc_1800184E7
0x1800184fe  xor     eax, eax
0x180018500  jmp     short loc_1800184E7
```
