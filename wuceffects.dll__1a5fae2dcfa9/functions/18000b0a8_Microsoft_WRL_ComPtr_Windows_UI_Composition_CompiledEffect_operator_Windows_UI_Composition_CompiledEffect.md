# Microsoft::WRL::ComPtr<Windows::UI::Composition::CompiledEffect>::operator=(Windows::UI::Composition::CompiledEffect *)

- ea: `0x18000b0a8`
- end: `0x18000b106`
- name: `??4?$ComPtr@VCompiledEffect@Composition@UI@Windows@@@WRL@Microsoft@@QEAAAEAV012@PEAVCompiledEffect@Composition@UI@Windows@@@Z`
- size: `94`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180013bcc`

## callees

- `0x18000adec`
- `0x18000b0a8`
- `0x18002b594`

## string_xrefs

- `0x18000b0f3`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall Microsoft::WRL::ComPtr<Windows::UI::Composition::CompiledEffect>::operator=(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v5; // rcx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *a1 != a2 )
  {
    if ( a2 && _InterlockedAdd((volatile signed __int32 *)(a2 + 8), 1u) <= 0 )
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x18,
        (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
        (const char *)0x8007029CLL,
        v7);
    v5 = *a1;
    *a1 = a2;
    if ( v5 )
      CMILRefCountBaseT<Windows::UI::Composition::ICompiledEffect,CMilObjectDeleter>::InternalRelease(v5, a2, a3);
  }
  return a1;
}

```

## disassembly

```asm
0x18000b0a8  mov     [rsp+arg_0], rbx
0x18000b0ad  push    rdi; int
0x18000b0ae  sub     rsp, 20h
0x18000b0b2  mov     rbx, rdx
0x18000b0b5  mov     rdi, rcx
0x18000b0b8  cmp     [rcx], rdx
0x18000b0bb  jz      short loc_18000B0DA
0x18000b0bd  test    rdx, rdx
0x18000b0c0  jz      short loc_18000B0C9
0x18000b0c2  lock add dword ptr [rdx+8], 1
0x18000b0c7  jle     short loc_18000B0E8
0x18000b0c9  mov     rcx, [rdi]
0x18000b0cc  mov     [rdi], rbx
0x18000b0cf  test    rcx, rcx
0x18000b0d2  jz      short loc_18000B0DA
0x18000b0d4  call    ?InternalRelease@?$CMILRefCountBaseT@UICompiledEffect@Composition@UI@Windows@@VCMilObjectDeleter@@@@IEAAKXZ; CMILRefCountBaseT<Windows::UI::Composition::ICompiledEffect,CMilObjectDeleter>::InternalRelease(void)
0x18000b0d9  nop
0x18000b0da  mov     rax, rdi
0x18000b0dd  mov     rbx, [rsp+28h+arg_0]
0x18000b0e2  add     rsp, 20h
0x18000b0e6  pop     rdi
0x18000b0e7  retn
0x18000b0e8  mov     rcx, [rsp+28h]; this
0x18000b0ed  mov     r9d, 8007029Ch; char *
0x18000b0f3  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\common\\share"...
0x18000b0fa  mov     edx, 18h; void *
0x18000b0ff  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000b104  jmp     short loc_18000B0C9
```
