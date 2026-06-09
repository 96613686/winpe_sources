# Windows::UI::Composition::EffectInstance::SetAnimatableProperty(uint,DCOMPOSITION_EXPRESSION_TYPE,void const *,bool *,uint *)

- ea: `0x180013c10`
- end: `0x180013c76`
- name: `?SetAnimatableProperty@EffectInstance@Composition@UI@Windows@@UEAAJIW4DCOMPOSITION_EXPRESSION_TYPE@@PEBXPEA_NPEAI@Z`
- size: `102`
- prototype: `__int64 __fastcall(__int64, int, int, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180013c10`
- `0x180013c7c`
- `0x18001dc90`

## string_xrefs

- `0x180013c5e`: `onecoreuap\windows\dwm\effects\compiler\effectinstance.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::EffectInstance::SetAnimatableProperty(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int64 result; // rax
  unsigned int v7; // ebx
  int v8[2]; // [rsp+20h] [rbp-38h] BYREF
  int v9; // [rsp+28h] [rbp-30h]
  int v10; // [rsp+2Ch] [rbp-2Ch]
  __int64 v11; // [rsp+30h] [rbp-28h]
  __int64 v12; // [rsp+38h] [rbp-20h]
  __int64 v13; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v12 = a5;
  *(_QWORD *)v8 = a1;
  v13 = a6;
  v9 = a2;
  v10 = a3;
  v11 = a4;
  result = wil::ResultFromException__Windows::UI::Composition::EffectInstance::SetAnimatableProperty_::_4_::_lambda_1___(v8);
  v7 = result;
  if ( (int)result < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\effectinstance.cpp",
      (const char *)(unsigned int)result,
      v8[0]);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180013c10  push    rbx
0x180013c12  sub     rsp, 50h
0x180013c16  mov     rax, [rsp+58h+arg_20]
0x180013c1e  mov     [rsp+58h+var_20], rax
0x180013c23  mov     rax, [rsp+58h+arg_28]
0x180013c2b  mov     qword ptr [rsp+58h+var_38], rcx; int
0x180013c30  lea     rcx, [rsp+58h+var_38]
0x180013c35  mov     [rsp+58h+var_18], rax
0x180013c3a  mov     [rsp+58h+var_30], edx
0x180013c3e  mov     [rsp+58h+var_2C], r8d
0x180013c43  mov     [rsp+58h+var_28], r9
0x180013c48  call    wil__ResultFromException__Windows__UI__Composition__EffectInstance__SetAnimatableProperty____4____lambda_1___
0x180013c4d  mov     ebx, eax
0x180013c4f  test    eax, eax
0x180013c51  js      short loc_180013C59
0x180013c53  add     rsp, 50h
0x180013c57  pop     rbx
0x180013c58  retn
0x180013c59  mov     rcx, [rsp+58h]; this
0x180013c5e  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x180013c65  mov     r9d, ebx; char *
0x180013c68  mov     edx, 0C5h; void *
0x180013c6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013c72  mov     eax, ebx
0x180013c74  jmp     short loc_180013C53
```
