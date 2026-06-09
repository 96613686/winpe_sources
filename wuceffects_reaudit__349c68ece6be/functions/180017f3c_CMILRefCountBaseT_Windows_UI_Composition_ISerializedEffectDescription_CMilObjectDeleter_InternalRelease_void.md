# CMILRefCountBaseT<Windows::UI::Composition::ISerializedEffectDescription,CMilObjectDeleter>::InternalRelease(void)

- ea: `0x180017f3c`
- end: `0x180018041`
- name: `?InternalRelease@?$CMILRefCountBaseT@UISerializedEffectDescription@Composition@UI@Windows@@VCMilObjectDeleter@@@@IEAAKXZ`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017f30`

## callees

- `0x180017f3c`
- `0x18002b594`
- `0x18002e010`

## string_xrefs

- `0x180017fc5`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`
- `0x180017fe3`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`
- `0x180018004`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`
- `0x180018025`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`

## pseudocode

```c
__int64 __fastcall CMILRefCountBaseT<Windows::UI::Composition::ISerializedEffectDescription,CMilObjectDeleter>::InternalRelease(
        volatile signed __int32 *a1)
{
  int v2; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = _InterlockedDecrement(a1 + 2);
  if ( v2 < -1 )
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
      (const char *)0x8007029CLL,
      v4);
  if ( !v2 )
  {
    if ( _InterlockedAdd(a1 + 2, 1u) <= 0 )
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x18,
        (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
        (const char *)0x8007029CLL,
        v4);
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)a1 + 40LL))(a1);
    v2 = _InterlockedDecrement(a1 + 2);
    if ( v2 < -1 )
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x26,
        (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
        (const char *)0x8007029CLL,
        v4);
    if ( !v2 )
    {
      if ( _InterlockedDecrement(a1 + 2) < -1 )
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x26,
          (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
          (const char *)0x8007029CLL,
          v4);
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)a1 + 32LL))(a1, 1);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180017f3c  mov     [rsp+arg_0], rbx
0x180017f41  mov     [rsp+arg_8], rsi
0x180017f46  push    rdi; int
0x180017f47  sub     rsp, 20h
0x180017f4b  or      esi, 0FFFFFFFFh
0x180017f4e  mov     rdi, rcx
0x180017f51  mov     ebx, esi
0x180017f53  lock xadd [rcx+8], ebx
0x180017f58  add     ebx, esi
0x180017f5a  cmp     ebx, esi
0x180017f5c  jl      short loc_180017FC0
0x180017f5e  test    ebx, ebx
0x180017f60  jnz     short loc_180017FAE
0x180017f62  lock add dword ptr [rdi+8], 1
0x180017f67  jle     short loc_180017FDE
0x180017f69  mov     rax, [rdi]
0x180017f6c  mov     rcx, rdi
0x180017f6f  mov     rax, [rax+28h]
0x180017f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f78  mov     ebx, esi
0x180017f7a  lock xadd [rdi+8], ebx
0x180017f7f  add     ebx, esi
0x180017f81  cmp     ebx, esi
0x180017f83  jl      short loc_180017FFF
0x180017f85  test    ebx, ebx
0x180017f87  jnz     short loc_180017FAE
0x180017f89  mov     eax, esi
0x180017f8b  lock xadd [rdi+8], eax
0x180017f90  add     eax, esi
0x180017f92  cmp     eax, esi
0x180017f94  jl      loc_180018020
0x180017f9a  mov     rax, [rdi]
0x180017f9d  mov     edx, 1
0x180017fa2  mov     rcx, rdi
0x180017fa5  mov     rax, [rax+20h]
0x180017fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fae  mov     rsi, [rsp+28h+arg_8]
0x180017fb3  mov     eax, ebx
0x180017fb5  mov     rbx, [rsp+28h+arg_0]
0x180017fba  add     rsp, 20h
0x180017fbe  pop     rdi
0x180017fbf  retn
0x180017fc0  mov     rcx, [rsp+28h]; this
0x180017fc5  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\common\\share"...
0x180017fcc  mov     r9d, 8007029Ch; char *
0x180017fd2  mov     edx, 26h ; '&'; void *
0x180017fd7  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180017fdc  jmp     short loc_180017F5E
0x180017fde  mov     rcx, [rsp+28h]; this
0x180017fe3  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\common\\share"...
0x180017fea  mov     r9d, 8007029Ch; char *
0x180017ff0  mov     edx, 18h; void *
0x180017ff5  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180017ffa  jmp     loc_180017F69
0x180017fff  mov     rcx, [rsp+28h]; this
0x180018004  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\common\\share"...
0x18001800b  mov     r9d, 8007029Ch; char *
0x180018011  mov     edx, 26h ; '&'; void *
0x180018016  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001801b  jmp     loc_180017F85
0x180018020  mov     rcx, [rsp+28h]; this
0x180018025  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\common\\share"...
0x18001802c  mov     r9d, 8007029Ch; char *
0x180018032  mov     edx, 26h ; '&'; void *
0x180018037  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001803c  jmp     loc_180017F9A
```
