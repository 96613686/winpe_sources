# CDisplayAnimatedVisual::InitializeTelemetry(void)

- ea: `0x1800701dc`
- end: `0x18007021b`
- name: `?InitializeTelemetry@CDisplayAnimatedVisual@@AEAAXXZ`
- size: `63`
- prototype: `void __fastcall(CDisplayAnimatedVisual *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008c760`

## callees

- `0x180050dfc`
- `0x1800701dc`
- `0x1800ea010`

## import_xrefs

- `dcomp!__imp_DCompositionCreateAnimationStats` at `0x1800701fa`
- `dcomp!__imp_DCompositionCreateAnimationStats` at `0x1800701fa`

## pseudocode

```c
void __fastcall CDisplayAnimatedVisual::InitializeTelemetry(CDisplayAnimatedVisual *this)
{
  _QWORD *v1; // rbx

  v1 = (_QWORD *)((char *)this + 336);
  if ( !*((_QWORD *)this + 42) )
  {
    wil::com_ptr_t<Windows::UI::Composition::ICompositionSurface,wil::err_returncode_policy>::reset((char *)this + 336);
    if ( (int)DCompositionCreateAnimationStats(v1) >= 0 )
      (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v1 + 24LL))(*v1, 0);
  }
}

```

## disassembly

```asm
0x1800701dc  push    rbx
0x1800701de  sub     rsp, 20h
0x1800701e2  lea     rbx, [rcx+150h]
0x1800701e9  cmp     qword ptr [rbx], 0
0x1800701ed  jnz     short loc_180070215
0x1800701ef  mov     rcx, rbx
0x1800701f2  call    ?reset@?$com_ptr_t@UICompositionSurface@Composition@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::UI::Composition::ICompositionSurface,wil::err_returncode_policy>::reset(void)
0x1800701f7  mov     rcx, rbx
0x1800701fa  call    cs:__imp_DCompositionCreateAnimationStats
0x180070200  test    eax, eax
0x180070202  js      short loc_180070215
0x180070204  mov     rcx, [rbx]
0x180070207  xor     edx, edx
0x180070209  mov     rax, [rcx]
0x18007020c  mov     rax, [rax+18h]
0x180070210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070215  add     rsp, 20h
0x180070219  pop     rbx
0x18007021a  retn
```
