# CrossFadeToNewBrush$catch$235

- ea: `0x18002caaf`
- end: `0x18002caeb`
- name: `CrossFadeToNewBrush$catch$235`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800266dc`

## string_xrefs

- `0x18002cac3`: `onecoreuap\windows\dwm\effects\compiler\global\materialbrushfactory.cpp`

## pseudocode

```c
__int64 __fastcall CrossFadeToNewBrush_catch_235(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 240) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 232),
                            (void *)0x124,
                            (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\global\\materialbrushfactory.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x18002caaf  mov     [rsp+arg_8], rdx
0x18002cab4  push    rbp
0x18002cab5  sub     rsp, 30h
0x18002cab9  mov     rbp, rdx
0x18002cabc  mov     rcx, [rbp+0E8h]; this
0x18002cac3  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x18002caca  mov     edx, 124h; void *
0x18002cacf  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002cad4  mov     [rbp+0F0h], eax
0x18002cada  mov     rax, 0
0x18002cae4  add     rsp, 30h
0x18002cae8  pop     rbp
0x18002cae9  retn
```
