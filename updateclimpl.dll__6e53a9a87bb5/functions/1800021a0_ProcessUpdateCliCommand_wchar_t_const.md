# ProcessUpdateCliCommand(wchar_t const *)

- ea: `0x1800021a0`
- end: `0x1800021d1`
- name: `?ProcessUpdateCliCommand@@YAJPEB_W@Z`
- size: `49`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800021a0`
- `0x1800021d8`
- `0x180008e40`

## pseudocode

```c
__int64 __fastcall ProcessUpdateCliCommand(const wchar_t *a1)
{
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_UpdateCli>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Calliope_UpdateCli>::GetImpl'::`2'::impl) )
    return CliMain::ProcessCliCommand(a1);
  else
    return 2147500033LL;
}

```

## disassembly

```asm
0x1800021a0  push    rbx
0x1800021a2  sub     rsp, 20h
0x1800021a6  mov     rbx, rcx
0x1800021a9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Calliope_UpdateCli@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_UpdateCli@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_UpdateCli> `wil::Feature<__WilFeatureTraits_Feature_Calliope_UpdateCli>::GetImpl(void)'::`2'::impl
0x1800021b0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_UpdateCli@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_UpdateCli>::__private_IsEnabled(void)
0x1800021b5  test    al, al
0x1800021b7  jnz     short loc_1800021C4
0x1800021b9  mov     eax, 80004001h
0x1800021be  add     rsp, 20h
0x1800021c2  pop     rbx
0x1800021c3  retn
0x1800021c4  mov     rcx, rbx; wchar_t *
0x1800021c7  add     rsp, 20h
0x1800021cb  pop     rbx
0x1800021cc  jmp     ?ProcessCliCommand@CliMain@@SAJPEB_W@Z; CliMain::ProcessCliCommand(wchar_t const *)
```
