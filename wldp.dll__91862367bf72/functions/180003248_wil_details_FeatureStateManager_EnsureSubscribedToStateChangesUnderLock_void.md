# wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock(void)

- ea: `0x180003248`
- end: `0x1800032bd`
- name: `?EnsureSubscribedToStateChangesUnderLock@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `117`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180002d80`

## callees

- `0x180003248`
- `0x18000363c`
- `0x180042010`

## string_xrefs

- `0x18000329a`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
bool __fastcall wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock(
        wil::details::FeatureStateManager *this)
{
  _QWORD *v2; // rbx
  __int64 (*NtDllProcedureAddress)(void); // rax
  int v4; // eax

  v2 = (_QWORD *)((char *)this + 144);
  if ( *((_QWORD *)this + 18) )
  {
    v4 = 0;
  }
  else
  {
    *v2 = 0;
    NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
    if ( g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
      || (NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlRegisterFeatureConfigurationChangeNotification"),
          (g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)NtDllProcedureAddress) != 0) )
    {
      v4 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), wil::details::FeatureStateManager *, _QWORD, _QWORD *))NtDllProcedureAddress)(
             _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
             this,
             0,
             v2);
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
0x180003248  mov     [rsp+arg_0], rbx
0x18000324d  push    rdi
0x18000324e  sub     rsp, 30h
0x180003252  mov     rdi, rcx
0x180003255  lea     rbx, [rcx+90h]
0x18000325c  cmp     qword ptr [rbx], 0
0x180003260  jnz     short loc_1800032B9
0x180003262  mov     qword ptr [rbx], 0
0x180003269  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180003270  test    rax, rax
0x180003273  jz      short loc_18000329A
0x180003275  mov     r9, rbx
0x180003278  xor     r8d, r8d
0x18000327b  mov     rdx, rdi
0x18000327e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180003285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000328a  test    eax, eax
0x18000328c  setz    al
0x18000328f  mov     rbx, [rsp+38h+arg_0]
0x180003294  add     rsp, 30h
0x180003298  pop     rdi
0x180003299  retn
0x18000329a  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800032a1  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800032a6  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800032ad  test    rax, rax
0x1800032b0  jnz     short loc_180003275
0x1800032b2  mov     eax, 0C0000139h
0x1800032b7  jmp     short loc_18000328A
0x1800032b9  xor     eax, eax
0x1800032bb  jmp     short loc_18000328A
```
