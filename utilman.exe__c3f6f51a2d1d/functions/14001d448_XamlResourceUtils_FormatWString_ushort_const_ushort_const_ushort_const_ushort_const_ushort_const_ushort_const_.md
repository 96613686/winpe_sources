# XamlResourceUtils::FormatWString<ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *>(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x14001d448`
- end: `0x14001d727`
- name: `??$FormatWString@PEBGPEBGPEBGPEBGPEBGPEBGPEBGPEBGPEBGPEBGPEBGPEBGPEBGPEBGPEBGPEBGPEBGPEBGPEBGPEBGPEBG@XamlResourceUtils@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG000000000000000000000@Z`
- size: `735`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14001d7bc`

## callees

- `0x140002fa0`
- `0x14000305c`
- `0x14000347c`
- `0x1400088cc`
- `0x14001d448`
- `0x14001efd0`
- `0x14001f3cc`
- `0x140022de8`

## string_xrefs

- `0x14001d6da`: `enduser\ezap\XamlCommon\XamlResourceUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall XamlResourceUtils::FormatWString<unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *>(
        __int64 a1,
        const wchar_t *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        __int64 a21,
        __int64 a22,
        __int64 a23)
{
  unsigned __int64 v23; // rdi
  unsigned __int64 v24; // rbx
  unsigned __int16 *v25; // rax
  size_t v26; // r8
  unsigned __int16 *v27; // rbx
  int v28; // eax
  unsigned __int16 *v30; // [rsp+C8h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]
  int v35; // [rsp+138h] [rbp+20h]

  v35 = a4;
  v23 = scwprintf(a2, a3, a4, a5, a6, a7, a8, a9, a10, a11, a12, a13, a14, a15, a16, a17, a18, a19, a20, a21, a22, a23)
      + 1;
  v24 = saturated_mul(v23, 2u);
  v25 = (unsigned __int16 *)operator new[](v24);
  v26 = v24;
  v27 = v25;
  memset_0(v25, 0, v26);
  v30 = v27;
  v28 = StringCchPrintfW(v27, v23, a2, a3);
  if ( v28 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"enduser\\ezap\\XamlCommon\\XamlResourceUtils.h",
      (const char *)(unsigned int)v28,
      v35);
  std::wstring::wstring(a1, v27);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v30);
  return a1;
}

```

## disassembly

```asm
0x14001d448  mov     rax, rsp
0x14001d44b  mov     [rax+20h], r9
0x14001d44f  mov     [rax+18h], r8
0x14001d453  mov     [rax+10h], rdx
0x14001d457  mov     [rax+8], rcx
0x14001d45b  push    rbx
0x14001d45c  push    rbp
0x14001d45d  push    rsi
0x14001d45e  push    rdi
0x14001d45f  push    r12
0x14001d461  push    r13
0x14001d463  push    r14
0x14001d465  push    r15
0x14001d467  sub     rsp, 0D8h
0x14001d46e  mov     r10, r9
0x14001d471  mov     r11, r8
0x14001d474  mov     rcx, rdx; Format
0x14001d477  mov     rax, [rsp+118h+arg_B0]
0x14001d47f  mov     [rsp+118h+var_70], rax
0x14001d487  mov     rax, [rsp+118h+arg_A8]
0x14001d48f  mov     [rsp+118h+var_78], rax
0x14001d497  mov     rax, [rsp+118h+arg_A0]
0x14001d49f  mov     [rsp+118h+var_80], rax
0x14001d4a7  mov     rax, [rsp+118h+arg_98]
0x14001d4af  mov     [rsp+118h+var_88], rax
0x14001d4b7  mov     rax, [rsp+118h+arg_90]
0x14001d4bf  mov     [rsp+118h+var_90], rax
0x14001d4c7  mov     rax, [rsp+118h+arg_88]
0x14001d4cf  mov     [rsp+118h+var_98], rax
0x14001d4d7  mov     rax, [rsp+118h+arg_80]
0x14001d4df  mov     [rsp+118h+var_A0], rax
0x14001d4e4  mov     rax, [rsp+118h+arg_78]
0x14001d4ec  mov     [rsp+118h+var_A8], rax
0x14001d4f1  mov     rax, [rsp+118h+arg_70]
0x14001d4f9  mov     [rsp+118h+var_B0], rax
0x14001d4fe  mov     rax, [rsp+118h+arg_68]
0x14001d506  mov     [rsp+118h+var_B8], rax
0x14001d50b  mov     rax, [rsp+118h+arg_60]
0x14001d513  mov     [rsp+118h+var_C0], rax
0x14001d518  mov     rax, [rsp+118h+arg_58]
0x14001d520  mov     [rsp+118h+var_C8], rax
0x14001d525  mov     rax, [rsp+118h+arg_50]
0x14001d52d  mov     [rsp+118h+var_D0], rax
0x14001d532  mov     r13, [rsp+118h+arg_48]
0x14001d53a  mov     [rsp+118h+var_D8], r13
0x14001d53f  mov     r12, [rsp+118h+arg_40]
0x14001d547  mov     [rsp+118h+var_E0], r12
0x14001d54c  mov     r15, [rsp+118h+arg_38]
0x14001d554  mov     [rsp+118h+var_E8], r15
0x14001d559  mov     r14, [rsp+118h+arg_30]
0x14001d561  mov     [rsp+118h+var_F0], r14
0x14001d566  mov     rbp, [rsp+118h+arg_28]
0x14001d56e  mov     qword ptr [rsp+118h+var_F8], rbp
0x14001d573  mov     rsi, [rsp+118h+arg_20]
0x14001d57b  mov     r9, rsi
0x14001d57e  mov     r8, r10
0x14001d581  mov     rdx, r11
0x14001d584  call    _scwprintf
0x14001d589  inc     eax
0x14001d58b  movsxd  rdi, eax
0x14001d58e  mov     eax, 2
0x14001d593  mul     rdi
0x14001d596  mov     rbx, rax
0x14001d599  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14001d5a0  cmovb   rbx, rax
0x14001d5a4  mov     rcx, rbx; unsigned __int64
0x14001d5a7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14001d5ac  mov     r8, rbx; Size
0x14001d5af  xor     edx, edx; Val
0x14001d5b1  mov     rbx, rax
0x14001d5b4  mov     rcx, rax; void *
0x14001d5b7  call    memset_0
0x14001d5bc  mov     [rsp+118h+var_50], rbx
0x14001d5c4  mov     rax, [rsp+118h+arg_B0]
0x14001d5cc  mov     [rsp+118h+var_60], rax
0x14001d5d4  mov     rax, [rsp+118h+arg_A8]
0x14001d5dc  mov     [rsp+118h+var_68], rax
0x14001d5e4  mov     rax, [rsp+118h+arg_A0]
0x14001d5ec  mov     [rsp+118h+var_70], rax
0x14001d5f4  mov     rax, [rsp+118h+arg_98]
0x14001d5fc  mov     [rsp+118h+var_78], rax
0x14001d604  mov     rax, [rsp+118h+arg_90]
0x14001d60c  mov     [rsp+118h+var_80], rax
0x14001d614  mov     rax, [rsp+118h+arg_88]
0x14001d61c  mov     [rsp+118h+var_88], rax
0x14001d624  mov     rax, [rsp+118h+arg_80]
0x14001d62c  mov     [rsp+118h+var_90], rax
0x14001d634  mov     rax, [rsp+118h+arg_78]
0x14001d63c  mov     [rsp+118h+var_98], rax
0x14001d644  mov     rax, [rsp+118h+arg_70]
0x14001d64c  mov     [rsp+118h+var_A0], rax
0x14001d651  mov     rax, [rsp+118h+arg_68]
0x14001d659  mov     [rsp+118h+var_A8], rax
0x14001d65e  mov     rax, [rsp+118h+arg_60]
0x14001d666  mov     [rsp+118h+var_B0], rax
0x14001d66b  mov     rax, [rsp+118h+arg_58]
0x14001d673  mov     [rsp+118h+var_B8], rax
0x14001d678  mov     rax, [rsp+118h+arg_50]
0x14001d680  mov     [rsp+118h+var_C0], rax
0x14001d685  mov     [rsp+118h+var_C8], r13
0x14001d68a  mov     [rsp+118h+var_D0], r12
0x14001d68f  mov     [rsp+118h+var_D8], r15
0x14001d694  mov     [rsp+118h+var_E0], r14
0x14001d699  mov     [rsp+118h+var_E8], rbp
0x14001d69e  mov     [rsp+118h+var_F0], rsi
0x14001d6a3  mov     rax, qword ptr [rsp+118h+arg_18]
0x14001d6ab  mov     qword ptr [rsp+118h+var_F8], rax; int
0x14001d6b0  mov     r9, [rsp+118h+arg_10]
0x14001d6b8  mov     r8, [rsp+118h+arg_8]; unsigned __int16 *
0x14001d6c0  mov     rdx, rdi; unsigned __int64
0x14001d6c3  mov     rcx, rbx; unsigned __int16 *
0x14001d6c6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001d6cb  mov     rcx, [rsp+118h]; this
0x14001d6d3  test    eax, eax
0x14001d6d5  jns     short loc_14001D6EC
0x14001d6d7  mov     r9d, eax; char *
0x14001d6da  lea     r8, aEnduserEzapXam_0; "enduser\\ezap\\XamlCommon\\XamlResource"...
0x14001d6e1  mov     edx, 22h ; '"'; void *
0x14001d6e6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14001d6ec  mov     rdx, rbx
0x14001d6ef  mov     rcx, [rsp+118h+arg_0]
0x14001d6f7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14001d6fc  nop
0x14001d6fd  lea     rcx, [rsp+118h+var_50]
0x14001d705  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x14001d70a  mov     rax, [rsp+118h+arg_0]
0x14001d712  add     rsp, 0D8h
0x14001d719  pop     r15
0x14001d71b  pop     r14
0x14001d71d  pop     r13
0x14001d71f  pop     r12
0x14001d721  pop     rdi
0x14001d722  pop     rsi
0x14001d723  pop     rbp
0x14001d724  pop     rbx
0x14001d725  retn
```
