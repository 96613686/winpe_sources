# Windows::UI::Composition::EffectGenerator::BuildCompiledEffectSubgraph(uint)

- ea: `0x18000cdd4`
- end: `0x18000cf5e`
- name: `?BuildCompiledEffectSubgraph@EffectGenerator@Composition@UI@Windows@@AEAAXI@Z`
- size: `394`
- prototype: `void __fastcall(Windows::UI::Composition::EffectGenerator *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000c410`

## callees

- `0x180008a30`
- `0x18000cdd4`
- `0x18000cf64`
- `0x18001eaa0`
- `0x180021cec`
- `0x18002b8a4`
- `0x18002e010`

## string_xrefs

- `0x18000ce0c`: `onecoreuap\windows\dwm\effects\compiler\effectgenerator.cpp`
- `0x18000ce7d`: `onecoreuap\windows\dwm\effects\compiler\effectgenerator.cpp`
- `0x18000ceb5`: `onecoreuap\windows\dwm\effects\compiler\effectgenerator.cpp`

## pseudocode

```c
void __fastcall Windows::UI::Composition::EffectGenerator::BuildCompiledEffectSubgraph(
        Windows::UI::Composition::EffectGenerator *this)
{
  int v2; // eax
  __int64 (__fastcall *v3)(__int64, __int64, GUID *, __int64 *); // rdi
  __int64 v4; // rbx
  __int64 v5; // rax
  int v6; // eax
  int v7; // eax
  __int64 v8; // rdi
  unsigned int v9; // esi
  void (__fastcall ***v10)(_QWORD, _BYTE *); // rbx
  int v11; // [rsp+20h] [rbp-79h]
  __int128 v12; // [rsp+30h] [rbp-69h] BYREF
  _BYTE v13[128]; // [rsp+40h] [rbp-59h] BYREF
  char *Str1; // [rsp+C0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  __int64 v16; // [rsp+110h] [rbp+77h] BYREF
  struct D3DCompilerHelper *v17; // [rsp+118h] [rbp+7Fh] BYREF

  Windows::UI::Composition::EffectGenerator::CompilePixelShader(this);
  v17 = 0;
  v2 = D3DCompilerHelper::Get(&v17);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x39D,
      (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\effectgenerator.cpp",
      (const char *)(unsigned int)v2,
      v11);
  v16 = 0;
  v3 = (__int64 (__fastcall *)(__int64, __int64, GUID *, __int64 *))*((_QWORD *)v17 + 1);
  v4 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 1) + 32LL) + 32LL))(*(_QWORD *)(*((_QWORD *)this + 1) + 32LL));
  v5 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 1) + 32LL) + 24LL))(*(_QWORD *)(*((_QWORD *)this + 1) + 32LL));
  v6 = v3(v5, v4, &GUID_54384f1b_5b3e_4bb7_ae01_60ba3097cbb6, &v16);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3A7,
      (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\effectgenerator.cpp",
      (const char *)(unsigned int)v6,
      v11);
  v12 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v16 + 24LL))(v16, &v12);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3AA,
      (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\effectgenerator.cpp",
      (const char *)(unsigned int)v7,
      v11);
  v8 = v16;
  v9 = 0;
  if ( HIDWORD(v12) )
  {
    do
    {
      v10 = (void (__fastcall ***)(_QWORD, _BYTE *))(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 32LL))(
                                                      v8,
                                                      v9);
      memset_0(v13, 0, 0x98u);
      (**v10)(v10, v13);
      if ( !strcmp_0(Str1, "PSBody") )
        break;
      ++v9;
    }
    while ( v9 < HIDWORD(v12) );
    v8 = v16;
  }
  if ( v8 )
  {
    v16 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
}

```

## disassembly

```asm
0x18000cdd4  mov     [rsp-8+arg_0], rbx
0x18000cdd9  push    rbp
0x18000cdda  push    rsi
0x18000cddb  push    rdi
0x18000cddc  lea     rbp, [rsp-47h]
0x18000cde1  sub     rsp, 0E0h
0x18000cde8  mov     rsi, rcx
0x18000cdeb  call    ?CompilePixelShader@EffectGenerator@Composition@UI@Windows@@AEAAXXZ; Windows::UI::Composition::EffectGenerator::CompilePixelShader(void)
0x18000cdf0  mov     [rbp+57h+arg_18], 0
0x18000cdf8  lea     rcx, [rbp+57h+arg_18]; struct D3DCompilerHelper **
0x18000cdfc  call    ?Get@D3DCompilerHelper@@SAJPEAPEAU1@@Z; D3DCompilerHelper::Get(D3DCompilerHelper * *)
0x18000ce01  mov     rcx, [rbp+5Fh]; this
0x18000ce05  test    eax, eax
0x18000ce07  jns     short loc_18000CE1E
0x18000ce09  mov     r9d, eax; char *
0x18000ce0c  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x18000ce13  mov     edx, 39Dh; void *
0x18000ce18  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000ce1e  mov     [rbp+57h+arg_10], 0
0x18000ce26  mov     rax, [rbp+57h+arg_18]
0x18000ce2a  mov     rdi, [rax+8]
0x18000ce2e  mov     rax, [rsi+8]
0x18000ce32  mov     rcx, [rax+20h]
0x18000ce36  mov     rax, [rcx]
0x18000ce39  mov     rax, [rax+20h]
0x18000ce3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce42  mov     rbx, rax
0x18000ce45  mov     rcx, [rsi+8]
0x18000ce49  mov     rcx, [rcx+20h]
0x18000ce4d  mov     rdx, [rcx]
0x18000ce50  mov     rax, [rdx+18h]
0x18000ce54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce59  lea     r9, [rbp+57h+arg_10]
0x18000ce5d  lea     r8, _GUID_54384f1b_5b3e_4bb7_ae01_60ba3097cbb6
0x18000ce64  mov     rdx, rbx
0x18000ce67  mov     rcx, rax
0x18000ce6a  mov     rax, rdi
0x18000ce6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce72  mov     rcx, [rbp+5Fh]; this
0x18000ce76  test    eax, eax
0x18000ce78  jns     short loc_18000CE8F
0x18000ce7a  mov     r9d, eax; char *
0x18000ce7d  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x18000ce84  mov     edx, 3A7h; void *
0x18000ce89  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000ce8f  xorps   xmm0, xmm0
0x18000ce92  movups  [rbp+57h+var_C0], xmm0
0x18000ce96  mov     rcx, [rbp+57h+arg_10]
0x18000ce9a  mov     rax, [rcx]
0x18000ce9d  lea     rdx, [rbp+57h+var_C0]
0x18000cea1  mov     rax, [rax+18h]
0x18000cea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ceaa  mov     rcx, [rbp+5Fh]; this
0x18000ceae  test    eax, eax
0x18000ceb0  jns     short loc_18000CEC7
0x18000ceb2  mov     r9d, eax; char *
0x18000ceb5  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x18000cebc  mov     edx, 3AAh; void *
0x18000cec1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000cec7  mov     rdi, [rbp+57h+arg_10]
0x18000cecb  xor     esi, esi
0x18000cecd  cmp     dword ptr [rbp+57h+var_C0+0Ch], esi
0x18000ced0  jbe     short loc_18000CF21
0x18000ced2  mov     rax, [rdi]
0x18000ced5  mov     edx, esi
0x18000ced7  mov     rcx, rdi
0x18000ceda  mov     rax, [rax+20h]
0x18000cede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cee3  mov     rbx, rax
0x18000cee6  xor     edx, edx; Val
0x18000cee8  mov     r8d, 98h; Size
0x18000ceee  lea     rcx, [rbp+57h+var_B0]; void *
0x18000cef2  call    memset_0
0x18000cef7  mov     rcx, [rbx]
0x18000cefa  mov     rax, [rcx]
0x18000cefd  lea     rdx, [rbp+57h+var_B0]
0x18000cf01  mov     rcx, rbx
0x18000cf04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf09  lea     rdx, Str2; "PSBody"
0x18000cf10  mov     rcx, [rbp+57h+Str1]; Str1
0x18000cf14  call    strcmp_0
0x18000cf19  test    eax, eax
0x18000cf1b  jnz     short loc_18000CF51
0x18000cf1d  mov     rdi, [rbp+57h+arg_10]
0x18000cf21  test    rdi, rdi
0x18000cf24  jz      short loc_18000CF3E
0x18000cf26  mov     [rbp+57h+arg_10], 0
0x18000cf2e  mov     rax, [rdi]
0x18000cf31  mov     rcx, rdi
0x18000cf34  mov     rax, [rax+10h]
0x18000cf38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf3d  nop
0x18000cf3e  mov     rbx, [rsp+0F0h+arg_0]
0x18000cf46  add     rsp, 0E0h
0x18000cf4d  pop     rdi
0x18000cf4e  pop     rsi
0x18000cf4f  pop     rbp
0x18000cf50  retn
0x18000cf51  inc     esi
0x18000cf53  cmp     esi, dword ptr [rbp+57h+var_C0+0Ch]
0x18000cf56  jnb     short loc_18000CF1D
0x18000cf58  jmp     loc_18000CED2
```
