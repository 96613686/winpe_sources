# Windows::UI::Composition::FlattenedEffectGraph::CreateEffectInstance(Windows::UI::Composition::IEffectInstance * *)

- ea: `0x180016000`
- end: `0x180016057`
- name: `?CreateEffectInstance@FlattenedEffectGraph@Composition@UI@Windows@@UEBAJPEAPEAUIEffectInstance@234@@Z`
- size: `87`
- prototype: `__int64 __fastcall(Windows::UI::Composition::FlattenedEffectGraph *__hidden this, struct Windows::UI::Composition::IEffectInstance **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180016000`
- `0x180016060`
- `0x18001dc90`

## string_xrefs

- `0x18001603f`: `onecoreuap\windows\dwm\effects\compiler\flattenedeffectgraph.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::FlattenedEffectGraph::CreateEffectInstance(
        Windows::UI::Composition::FlattenedEffectGraph *this,
        struct Windows::UI::Composition::IEffectInstance **a2)
{
  __int64 result; // rax
  unsigned int v3; // ebx
  int v4[2]; // [rsp+20h] [rbp-18h] BYREF
  char *v5; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  struct Windows::UI::Composition::IEffectInstance **v7; // [rsp+48h] [rbp+10h] BYREF

  v7 = a2;
  *a2 = 0;
  *(_QWORD *)v4 = &v7;
  v5 = (char *)this - 16;
  result = wil::ResultFromException__Windows::UI::Composition::FlattenedEffectGraph::CreateEffectInstance_::_4_::_lambda_1___(v4);
  v3 = result;
  if ( (int)result < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x240,
      (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\flattenedeffectgraph.cpp",
      (const char *)(unsigned int)result,
      v4[0]);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x180016000  mov     [rsp+arg_8], rdx
0x180016005  push    rbx
0x180016006  sub     rsp, 30h
0x18001600a  lea     rax, [rsp+38h+arg_8]
0x18001600f  mov     qword ptr [rdx], 0
0x180016016  mov     qword ptr [rsp+38h+var_18], rax; int
0x18001601b  lea     rax, [rcx-10h]
0x18001601f  lea     rcx, [rsp+38h+var_18]
0x180016024  mov     [rsp+38h+var_10], rax
0x180016029  call    wil__ResultFromException__Windows__UI__Composition__FlattenedEffectGraph__CreateEffectInstance____4____lambda_1___
0x18001602e  mov     ebx, eax
0x180016030  test    eax, eax
0x180016032  js      short loc_18001603A
0x180016034  add     rsp, 30h
0x180016038  pop     rbx
0x180016039  retn
0x18001603a  mov     rcx, [rsp+38h]; this
0x18001603f  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x180016046  mov     r9d, ebx; char *
0x180016049  mov     edx, 240h; void *
0x18001604e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016053  mov     eax, ebx
0x180016055  jmp     short loc_180016034
```
