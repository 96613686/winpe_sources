# Windows::UI::Composition::FlattenedEffectGraph::GetGraphStringForTelemetry(Windows::UI::Composition::IWrappedString * *)

- ea: `0x18000da20`
- end: `0x18000da67`
- name: `?GetGraphStringForTelemetry@FlattenedEffectGraph@Composition@UI@Windows@@UEBAJPEAPEAUIWrappedString@234@@Z`
- size: `71`
- prototype: `__int64 __fastcall(Windows::UI::Composition::FlattenedEffectGraph *__hidden this, struct Windows::UI::Composition::IWrappedString **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000da20`
- `0x18000da70`
- `0x18001dc90`

## string_xrefs

- `0x18000da51`: `onecoreuap\windows\dwm\effects\compiler\flattenedeffectgraph.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::FlattenedEffectGraph::GetGraphStringForTelemetry(
        Windows::UI::Composition::FlattenedEffectGraph *this,
        struct Windows::UI::Composition::IWrappedString **a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5[2]; // [rsp+20h] [rbp-18h] BYREF
  struct Windows::UI::Composition::IWrappedString **v6; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v6 = a2;
  *(_QWORD *)v5 = (char *)this - 16;
  v2 = wil::ResultFromException__Windows::UI::Composition::FlattenedEffectGraph::GetGraphStringForTelemetry_::_4_::_lambda_1___(v5);
  v3 = v2;
  if ( v2 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x514,
      (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\flattenedeffectgraph.cpp",
      (const char *)(unsigned int)v2,
      v5[0]);
  return v3;
}

```

## disassembly

```asm
0x18000da20  push    rbx
0x18000da22  sub     rsp, 30h
0x18000da26  lea     rax, [rcx-10h]
0x18000da2a  mov     [rsp+38h+var_10], rdx
0x18000da2f  lea     rcx, [rsp+38h+var_18]
0x18000da34  mov     qword ptr [rsp+38h+var_18], rax; int
0x18000da39  call    wil__ResultFromException__Windows__UI__Composition__FlattenedEffectGraph__GetGraphStringForTelemetry____4____lambda_1___
0x18000da3e  mov     ebx, eax
0x18000da40  test    eax, eax
0x18000da42  js      short loc_18000DA4C
0x18000da44  mov     eax, ebx
0x18000da46  add     rsp, 30h
0x18000da4a  pop     rbx
0x18000da4b  retn
0x18000da4c  mov     rcx, [rsp+38h]; this
0x18000da51  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x18000da58  mov     r9d, ebx; char *
0x18000da5b  mov     edx, 514h; void *
0x18000da60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000da65  jmp     short loc_18000DA44
```
