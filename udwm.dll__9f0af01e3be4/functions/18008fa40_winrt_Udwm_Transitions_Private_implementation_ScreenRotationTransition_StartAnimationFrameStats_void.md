# winrt::Udwm::Transitions::Private::implementation::ScreenRotationTransition::StartAnimationFrameStats(void)

- ea: `0x18008fa40`
- end: `0x18008fa8f`
- name: `?StartAnimationFrameStats@ScreenRotationTransition@implementation@Private@Transitions@Udwm@winrt@@AEAAXXZ`
- size: `79`
- prototype: `void __fastcall(winrt::Udwm::Transitions::Private::implementation::ScreenRotationTransition *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008ef20`

## callees

- `0x180050dfc`
- `0x18008fa40`
- `0x1800ea010`

## import_xrefs

- `dcomp!__imp_DCompositionCreateAnimationStats` at `0x18008fa62`
- `dcomp!__imp_DCompositionCreateAnimationStats` at `0x18008fa62`

## pseudocode

```c
void __fastcall winrt::Udwm::Transitions::Private::implementation::ScreenRotationTransition::StartAnimationFrameStats(
        winrt::Udwm::Transitions::Private::implementation::ScreenRotationTransition *this)
{
  __int64 *v1; // rbx
  __int64 v3; // rcx

  v1 = (__int64 *)((char *)this + 96);
  if ( !*((_QWORD *)this + 12) )
  {
    wil::com_ptr_t<Windows::UI::Composition::ICompositionSurface,wil::err_returncode_policy>::reset((char *)this + 96);
    if ( (int)DCompositionCreateAnimationStats(v1) >= 0 )
    {
      v3 = *v1;
      *((_DWORD *)this + 28) = 0;
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 24LL))(v3, 0);
    }
  }
}

```

## disassembly

```asm
0x18008fa40  mov     [rsp+arg_0], rbx
0x18008fa45  push    rdi
0x18008fa46  sub     rsp, 20h
0x18008fa4a  lea     rbx, [rcx+60h]
0x18008fa4e  mov     rdi, rcx
0x18008fa51  cmp     qword ptr [rbx], 0
0x18008fa55  jnz     short loc_18008FA84
0x18008fa57  mov     rcx, rbx
0x18008fa5a  call    ?reset@?$com_ptr_t@UICompositionSurface@Composition@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::UI::Composition::ICompositionSurface,wil::err_returncode_policy>::reset(void)
0x18008fa5f  mov     rcx, rbx
0x18008fa62  call    cs:__imp_DCompositionCreateAnimationStats
0x18008fa68  test    eax, eax
0x18008fa6a  js      short loc_18008FA84
0x18008fa6c  mov     rcx, [rbx]
0x18008fa6f  xor     edx, edx
0x18008fa71  mov     dword ptr [rdi+70h], 0
0x18008fa78  mov     rax, [rcx]
0x18008fa7b  mov     rax, [rax+18h]
0x18008fa7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fa84  mov     rbx, [rsp+28h+arg_0]
0x18008fa89  add     rsp, 20h
0x18008fa8d  pop     rdi
0x18008fa8e  retn
```
