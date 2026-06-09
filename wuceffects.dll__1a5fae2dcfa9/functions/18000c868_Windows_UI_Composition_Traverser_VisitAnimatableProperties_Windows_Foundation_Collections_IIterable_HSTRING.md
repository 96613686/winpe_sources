# Windows::UI::Composition::Traverser::VisitAnimatableProperties(Windows::Foundation::Collections::IIterable<HSTRING__ *> *)

- ea: `0x18000c868`
- end: `0x18000c9af`
- name: `?VisitAnimatableProperties@Traverser@Composition@UI@Windows@@AEAAXPEAU?$IIterable@PEAUHSTRING__@@@Collections@Foundation@4@@Z`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b520`

## callees

- `0x18000c868`
- `0x18000c9b8`
- `0x18001eaa0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c9a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c9a3`

## string_xrefs

- `0x18000c8aa`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`
- `0x18000c8df`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`
- `0x18000c947`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`
- `0x18000c984`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Windows::UI::Composition::Traverser::VisitAnimatableProperties(
        Windows::UI::Composition::FlattenedEffectGraph **this,
        __int64 a2)
{
  int v3; // eax
  int v4; // eax
  __int64 v5; // rcx
  int v6; // eax
  int v7; // eax
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+8h]
  char v10; // [rsp+38h] [rbp+18h] BYREF
  __int64 v11; // [rsp+40h] [rbp+20h] BYREF
  HSTRING string; // [rsp+48h] [rbp+28h] BYREF

  if ( a2 )
  {
    v11 = 0;
    v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 48LL))(a2, &v11);
    if ( v3 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x2FB,
        (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
        (const char *)(unsigned int)v3,
        savedregs);
    v10 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v11 + 56LL))(v11, &v10);
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x2FE,
        (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
        (const char *)(unsigned int)v4,
        savedregs);
    while ( v10 )
    {
      string = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v11 + 48LL))(v11, &string);
      if ( v6 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x303,
          (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
          (const char *)(unsigned int)v6,
          savedregs);
      Windows::UI::Composition::Traverser::VisitAnimatableProperty(this, string);
      v7 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v11 + 64LL))(v11, &v10);
      if ( v7 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x307,
          (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
          (const char *)(unsigned int)v7,
          savedregs);
      if ( string )
        WindowsDeleteString(string);
    }
    v5 = v11;
    if ( v11 )
    {
      v11 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
  }
}

```

## disassembly

```asm
0x18000c868  test    rdx, rdx
0x18000c86b  jz      locret_18000C91F
0x18000c871  mov     [rsp-8+arg_0], rbx
0x18000c876  push    rbp; int
0x18000c877  mov     rbp, rsp
0x18000c87a  sub     rsp, 20h
0x18000c87e  mov     r8, rdx
0x18000c881  mov     rbx, rcx
0x18000c884  mov     [rbp+arg_10], 0
0x18000c88c  mov     rax, [rdx]
0x18000c88f  lea     rdx, [rbp+arg_10]
0x18000c893  mov     rcx, r8
0x18000c896  mov     rax, [rax+30h]
0x18000c89a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c89f  mov     rcx, [rbp+8]; this
0x18000c8a3  test    eax, eax
0x18000c8a5  jns     short loc_18000C8BC
0x18000c8a7  mov     r9d, eax; char *
0x18000c8aa  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x18000c8b1  mov     edx, 2FBh; void *
0x18000c8b6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000c8bc  mov     [rbp+arg_8], 0
0x18000c8c0  mov     rcx, [rbp+arg_10]
0x18000c8c4  mov     rax, [rcx]
0x18000c8c7  lea     rdx, [rbp+arg_8]
0x18000c8cb  mov     rax, [rax+38h]
0x18000c8cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8d4  mov     rcx, [rbp+8]; this
0x18000c8d8  test    eax, eax
0x18000c8da  jns     short loc_18000C8F1
0x18000c8dc  mov     r9d, eax; char *
0x18000c8df  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x18000c8e6  mov     edx, 2FEh; void *
0x18000c8eb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000c8f1  cmp     [rbp+arg_8], 0
0x18000c8f5  jnz     short loc_18000C920
0x18000c8f7  mov     rcx, [rbp+arg_10]
0x18000c8fb  test    rcx, rcx
0x18000c8fe  jz      short loc_18000C915
0x18000c900  mov     [rbp+arg_10], 0
0x18000c908  mov     rax, [rcx]
0x18000c90b  mov     rax, [rax+10h]
0x18000c90f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c914  nop
0x18000c915  mov     rbx, [rsp+20h+arg_0]
0x18000c91a  add     rsp, 20h
0x18000c91e  pop     rbp
0x18000c91f  retn
0x18000c920  mov     [rbp+string], 0
0x18000c928  mov     rcx, [rbp+arg_10]
0x18000c92c  mov     rax, [rcx]
0x18000c92f  lea     rdx, [rbp+string]
0x18000c933  mov     rax, [rax+30h]
0x18000c937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c93c  mov     rcx, [rbp+8]; this
0x18000c940  test    eax, eax
0x18000c942  jns     short loc_18000C959
0x18000c944  mov     r9d, eax; char *
0x18000c947  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x18000c94e  mov     edx, 303h; void *
0x18000c953  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000c959  mov     rdx, [rbp+string]; string
0x18000c95d  mov     rcx, rbx; this
0x18000c960  call    ?VisitAnimatableProperty@Traverser@Composition@UI@Windows@@AEAAXPEAUHSTRING__@@@Z; Windows::UI::Composition::Traverser::VisitAnimatableProperty(HSTRING__ *)
0x18000c965  mov     rcx, [rbp+arg_10]
0x18000c969  mov     rax, [rcx]
0x18000c96c  lea     rdx, [rbp+arg_8]
0x18000c970  mov     rax, [rax+40h]
0x18000c974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c979  mov     rcx, [rbp+8]; this
0x18000c97d  test    eax, eax
0x18000c97f  jns     short loc_18000C996
0x18000c981  mov     r9d, eax; char *
0x18000c984  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x18000c98b  mov     edx, 307h; void *
0x18000c990  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000c996  mov     rcx, [rbp+string]; string
0x18000c99a  test    rcx, rcx
0x18000c99d  jz      loc_18000C8F1
0x18000c9a3  call    cs:__imp_WindowsDeleteString
0x18000c9a9  jmp     loc_18000C8F1
```
