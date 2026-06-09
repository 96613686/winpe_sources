# CExcludedExtsPolicy::CExcludedExtsPolicy(void)

- ea: `0x1800122d4`
- end: `0x1800123f8`
- name: `??0CExcludedExtsPolicy@@QEAA@XZ`
- size: `292`
- prototype: `CExcludedExtsPolicy *__fastcall(CExcludedExtsPolicy *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800134b0`

## callees

- `0x1800122d4`
- `0x18001a7fc`

## string_xrefs

- `0x1800122e8`: `ExcludedExtensions`
- `0x180012334`: `ExcludedExtensionsMultiline0`
- `0x180012365`: `ExcludedExtensionsMultiline1`
- `0x180012396`: `ExcludedExtensionsMultiline2`
- `0x1800123c7`: `ExcludedExtensionsMultiline3`

## pseudocode

```c
CExcludedExtsPolicy *__fastcall CExcludedExtsPolicy::CExcludedExtsPolicy(CExcludedExtsPolicy *this)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rax
  _QWORD *v4; // rax
  _QWORD *v5; // rax

  *((_QWORD *)this + 1) = L"ExcludedExtensions";
  *(_QWORD *)this = &CExcludedExtsPolicy::`vftable';
  *((_QWORD *)this + 7) = L"ExcludedExtensions";
  *((_QWORD *)this + 8) = L"SOFTWARE\\Microsoft\\Windows Search\\CurrentPolicies";
  *((_DWORD *)this + 12) = 0;
  *((_DWORD *)this + 18) = 1;
  *((_QWORD *)this + 10) = 0;
  v2 = operator new(0x28u);
  if ( v2 )
  {
    *(_DWORD *)v2 = 0;
    v2[1] = L"ExcludedExtensionsMultiline0";
    v2[2] = L"SOFTWARE\\Policies\\Microsoft\\Windows\\Windows Search";
    *((_DWORD *)v2 + 6) = 1;
    v2[4] = 0;
  }
  *((_QWORD *)this + 2) = v2;
  v3 = operator new(0x28u);
  if ( v3 )
  {
    *(_DWORD *)v3 = 0;
    v3[1] = L"ExcludedExtensionsMultiline1";
    v3[2] = L"SOFTWARE\\Policies\\Microsoft\\Windows\\Windows Search";
    *((_DWORD *)v3 + 6) = 1;
    v3[4] = 0;
  }
  *((_QWORD *)this + 3) = v3;
  v4 = operator new(0x28u);
  if ( v4 )
  {
    *(_DWORD *)v4 = 0;
    v4[1] = L"ExcludedExtensionsMultiline2";
    v4[2] = L"SOFTWARE\\Policies\\Microsoft\\Windows\\Windows Search";
    *((_DWORD *)v4 + 6) = 1;
    v4[4] = 0;
  }
  *((_QWORD *)this + 4) = v4;
  v5 = operator new(0x28u);
  if ( v5 )
  {
    *(_DWORD *)v5 = 0;
    v5[1] = L"ExcludedExtensionsMultiline3";
    v5[2] = L"SOFTWARE\\Policies\\Microsoft\\Windows\\Windows Search";
    *((_DWORD *)v5 + 6) = 1;
    v5[4] = 0;
  }
  *((_QWORD *)this + 5) = v5;
  return this;
}

```

## disassembly

```asm
0x1800122d4  push    rbx
0x1800122d6  push    rbp
0x1800122d7  push    rsi
0x1800122d8  push    r14
0x1800122da  sub     rsp, 28h
0x1800122de  mov     rbx, rcx
0x1800122e1  lea     rax, ??_7CExcludedExtsPolicy@@6B@; const CExcludedExtsPolicy::`vftable'
0x1800122e8  lea     rcx, aExcludedextens_2; "ExcludedExtensions"
0x1800122ef  mov     esi, 1
0x1800122f4  mov     [rbx+8], rcx
0x1800122f8  mov     [rbx], rax
0x1800122fb  lea     r14d, [rsi+27h]
0x1800122ff  mov     [rbx+38h], rcx
0x180012303  lea     rax, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows Search\\Cu"...
0x18001230a  mov     ecx, r14d; unsigned __int64
0x18001230d  mov     [rbx+40h], rax
0x180012311  mov     dword ptr [rbx+30h], 0
0x180012318  mov     [rbx+48h], esi
0x18001231b  mov     qword ptr [rbx+50h], 0
0x180012323  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012328  lea     rbp, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18001232f  test    rax, rax
0x180012332  jz      short loc_180012354
0x180012334  lea     rcx, aExcludedextens_3; "ExcludedExtensionsMultiline0"
0x18001233b  mov     dword ptr [rax], 0
0x180012341  mov     [rax+8], rcx
0x180012345  mov     [rax+10h], rbp
0x180012349  mov     [rax+18h], esi
0x18001234c  mov     qword ptr [rax+20h], 0
0x180012354  mov     rcx, r14; unsigned __int64
0x180012357  mov     [rbx+10h], rax
0x18001235b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012360  test    rax, rax
0x180012363  jz      short loc_180012385
0x180012365  lea     rcx, aExcludedextens; "ExcludedExtensionsMultiline1"
0x18001236c  mov     dword ptr [rax], 0
0x180012372  mov     [rax+8], rcx
0x180012376  mov     [rax+10h], rbp
0x18001237a  mov     [rax+18h], esi
0x18001237d  mov     qword ptr [rax+20h], 0
0x180012385  mov     rcx, r14; unsigned __int64
0x180012388  mov     [rbx+18h], rax
0x18001238c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012391  test    rax, rax
0x180012394  jz      short loc_1800123B6
0x180012396  lea     rcx, aExcludedextens_1; "ExcludedExtensionsMultiline2"
0x18001239d  mov     dword ptr [rax], 0
0x1800123a3  mov     [rax+8], rcx
0x1800123a7  mov     [rax+10h], rbp
0x1800123ab  mov     [rax+18h], esi
0x1800123ae  mov     qword ptr [rax+20h], 0
0x1800123b6  mov     rcx, r14; unsigned __int64
0x1800123b9  mov     [rbx+20h], rax
0x1800123bd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800123c2  test    rax, rax
0x1800123c5  jz      short loc_1800123E7
0x1800123c7  lea     rcx, aExcludedextens_0; "ExcludedExtensionsMultiline3"
0x1800123ce  mov     dword ptr [rax], 0
0x1800123d4  mov     [rax+8], rcx
0x1800123d8  mov     [rax+10h], rbp
0x1800123dc  mov     [rax+18h], esi
0x1800123df  mov     qword ptr [rax+20h], 0
0x1800123e7  mov     [rbx+28h], rax
0x1800123eb  mov     rax, rbx
0x1800123ee  add     rsp, 28h
0x1800123f2  pop     r14
0x1800123f4  pop     rsi
0x1800123f5  pop     rbp
0x1800123f6  pop     rbx
0x1800123f7  retn
```
