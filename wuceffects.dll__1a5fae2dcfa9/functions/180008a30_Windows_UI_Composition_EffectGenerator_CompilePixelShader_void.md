# Windows::UI::Composition::EffectGenerator::CompilePixelShader(void)

- ea: `0x180008a30`
- end: `0x180008b6f`
- name: `?CompilePixelShader@EffectGenerator@Composition@UI@Windows@@AEAAXXZ`
- size: `319`
- prototype: `void __fastcall(Windows::UI::Composition::EffectGenerator *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000cdd4`

## callees

- `0x180007394`
- `0x180008a30`
- `0x1800090a0`
- `0x18000cf64`
- `0x18001eaa0`
- `0x180021060`
- `0x18002e010`

## string_xrefs

- `0x180008a90`: `onecoreuap\windows\dwm\effects\compiler\effectgenerator.cpp`
- `0x180008b5d`: `onecoreuap\windows\dwm\effects\compiler\effectgenerator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall Windows::UI::Composition::EffectGenerator::CompilePixelShader(
        Windows::UI::Composition::EffectGenerator *this)
{
  int v1; // eax
  _QWORD *v2; // rcx
  int v3; // eax
  int v4; // [rsp+20h] [rbp-29h]
  struct D3DCompilerHelper *v5; // [rsp+68h] [rbp+1Fh] BYREF
  int v6[2]; // [rsp+70h] [rbp+27h] BYREF
  _QWORD v7[4]; // [rsp+78h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  Windows::UI::Composition::PixelShaderSourceBuilder::ToString((char *)this + 88, v7);
  *(_QWORD *)v6 = &Windows::UI::Composition::ShaderIncludeResolver::`vftable';
  v5 = 0;
  v1 = D3DCompilerHelper::Get(&v5);
  if ( v1 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3CD,
      (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\effectgenerator.cpp",
      (const char *)(unsigned int)v1,
      v4);
  v2 = v7;
  if ( v7[3] > 0xFu )
    v2 = (_QWORD *)v7[0];
  v3 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, const char *, _QWORD))v5)(v2, v7[2], "PixelShader.hlsl", 0);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3E4,
      (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\effectgenerator.cpp",
      (const char *)(unsigned int)v3,
      (int)v6);
  std::string::~string(v7);
}

```

## disassembly

```asm
0x180008a30  mov     [rsp-8+arg_8], rbx
0x180008a35  push    rbp
0x180008a36  lea     rbp, [rsp-57h]
0x180008a3b  sub     rsp, 0A0h
0x180008a42  mov     rax, cs:__security_cookie
0x180008a49  xor     rax, rsp
0x180008a4c  mov     [rbp+57h+var_8], rax
0x180008a50  mov     rbx, rcx
0x180008a53  add     rcx, 58h ; 'X'
0x180008a57  lea     rdx, [rbp+57h+var_28]
0x180008a5b  call    ?ToString@PixelShaderSourceBuilder@Composition@UI@Windows@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; Windows::UI::Composition::PixelShaderSourceBuilder::ToString(void)
0x180008a60  nop
0x180008a61  lea     rax, ??_7ShaderIncludeResolver@Composition@UI@Windows@@6B@; const Windows::UI::Composition::ShaderIncludeResolver::`vftable'
0x180008a68  mov     qword ptr [rbp+57h+var_30], rax
0x180008a6c  mov     [rbp+57h+var_40], 0
0x180008a74  mov     [rbp+57h+var_38], 0
0x180008a7c  lea     rcx, [rbp+57h+var_38]; struct D3DCompilerHelper **
0x180008a80  call    ?Get@D3DCompilerHelper@@SAJPEAPEAU1@@Z; D3DCompilerHelper::Get(D3DCompilerHelper * *)
0x180008a85  mov     rcx, [rbp+5Fh]; this
0x180008a89  test    eax, eax
0x180008a8b  jns     short loc_180008AA2
0x180008a8d  mov     r9d, eax; char *
0x180008a90  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x180008a97  mov     edx, 3CDh; void *
0x180008a9c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180008aa2  mov     r8, [rbx+8]
0x180008aa6  add     r8, 20h ; ' '
0x180008aaa  mov     rax, [rbp+57h+var_38]
0x180008aae  lea     rcx, [rbp+57h+var_28]
0x180008ab2  cmp     [rbp+57h+var_10], 0Fh
0x180008ab7  cmova   rcx, [rbp+57h+var_28]
0x180008abc  lea     rdx, [rbp+57h+var_40]
0x180008ac0  mov     [rsp+0A0h+var_50], rdx
0x180008ac5  mov     [rsp+0A0h+var_58], r8
0x180008aca  mov     [rsp+0A0h+var_60], 0
0x180008ad2  mov     [rsp+0A0h+var_68], 8800h
0x180008ada  lea     rdx, aLib40Level93Ps; "lib_4_0_level_9_3_ps_only"
0x180008ae1  mov     [rsp+0A0h+var_70], rdx
0x180008ae6  mov     [rsp+0A0h+var_78], 0
0x180008aef  lea     rdx, [rbp+57h+var_30]
0x180008af3  mov     qword ptr [rsp+0A0h+var_80], rdx; int
0x180008af8  xor     r9d, r9d
0x180008afb  lea     r8, aPixelshaderHls; "PixelShader.hlsl"
0x180008b02  mov     rdx, [rbp+57h+var_18]
0x180008b06  mov     rax, [rax]
0x180008b09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b0e  test    eax, eax
0x180008b10  js      short loc_180008B56
0x180008b12  mov     rcx, [rbp+57h+var_40]
0x180008b16  test    rcx, rcx
0x180008b19  jz      short loc_180008B30
0x180008b1b  mov     [rbp+57h+var_40], 0
0x180008b23  mov     rax, [rcx]
0x180008b26  mov     rax, [rax+10h]
0x180008b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b2f  nop
0x180008b30  lea     rcx, [rbp+57h+var_28]; void *
0x180008b34  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180008b39  mov     rcx, [rbp+57h+var_8]
0x180008b3d  xor     rcx, rsp; StackCookie
0x180008b40  call    __security_check_cookie
0x180008b45  mov     rbx, [rsp+0A0h+arg_8]
0x180008b4d  add     rsp, 0A0h
0x180008b54  pop     rbp
0x180008b55  retn
0x180008b56  mov     rcx, [rbp+5Fh]; this
0x180008b5a  mov     r9d, eax; char *
0x180008b5d  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x180008b64  mov     edx, 3E4h; void *
0x180008b69  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
