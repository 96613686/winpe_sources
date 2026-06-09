# CArguments::Create(long,ushort const * *,CArguments * *)

- ea: `0x140012d54`
- end: `0x140012f18`
- name: `?Create@CArguments@@SAJJPEAPEBGPEAPEAV1@@Z`
- size: `452`
- prototype: `__int64 __fastcall(int, const unsigned __int16 **, struct CArguments **)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x14000eedc`

## callees

- `0x140001008`
- `0x140012d54`
- `0x140012f20`
- `0x140013218`
- `0x140018010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140012e8f`
- `OLEAUT32!__imp_SysAllocString` at `0x140012e8f`
- `OLEAUT32!__imp_VariantClear` at `0x140012eb6`
- `OLEAUT32!__imp_VariantClear` at `0x140012eb6`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140012e4c`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140012e4c`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x140012eaa`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x140012eaa`

## pseudocode

```c
__int64 __fastcall CArguments::Create(int a1, const unsigned __int16 **a2, struct CArguments **a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rdi
  SAFEARRAY *v8; // rax
  int v9; // ebx
  LONG v10; // eax
  SAFEARRAYBOUND rgsabound; // [rsp+20h] [rbp-28h] BYREF
  VARIANTARG pv; // [rsp+28h] [rbp-20h] BYREF
  LONG rgIndices; // [rsp+A8h] [rbp+60h] BYREF

  rgsabound = 0;
  rgIndices = 0;
  memset(&pv, 0, sizeof(pv));
  v6 = operator new(0x98u);
  v7 = v6;
  if ( !v6 )
    return (unsigned int)-2147024882;
  v6[1] = &IWshRuntime::`vftable';
  v6[3] = &CUnknown::`vftable';
  v6[6] = &CUnknown::InnerUnknown::`vftable';
  *((_DWORD *)v6 + 14) = 1;
  v6[4] = v6 + 6;
  v6[5] = v6;
  _InterlockedAdd(&Global::g_cObjects, 1u);
  *((_BYTE *)v6 + 72) = 0;
  v6[8] = &TaUser_DescCArguments;
  v6[10] = 0;
  *v6 = &CArguments::`vftable'{for `IArguments2'};
  v6[11] = 0;
  v6[1] = &CArguments::`vftable'{for `IWshRuntime'};
  v6[2] = &CArguments::`vftable'{for `IProvideClassInfo'};
  v6[3] = &CArguments::`vftable'{for `CDispatch'};
  v6[12] = 0;
  v6[14] = 0;
  v6[13] = 0;
  v6[16] = 0;
  v6[17] = 0;
  v6[15] = 0;
  *((_DWORD *)v6 + 36) = 1;
  rgsabound.lLbound = 0;
  rgsabound.cElements = a1;
  v8 = SafeArrayCreate(0xCu, 1u, &rgsabound);
  v7[10] = v8;
  if ( !v8 )
    goto LABEL_3;
  rgIndices = 0;
  if ( a1 > 0 )
  {
    v10 = 0;
    while ( 1 )
    {
      pv.vt = 8;
      pv.llVal = (LONGLONG)SysAllocString(a2[v10]);
      if ( !pv.llVal )
        break;
      v9 = SafeArrayPutElement((SAFEARRAY *)v7[10], &rgIndices, &pv);
      VariantClear(&pv);
      if ( v9 < 0 )
        goto LABEL_4;
      v10 = rgIndices + 1;
      rgIndices = v10;
      if ( v10 >= a1 )
        goto LABEL_10;
    }
LABEL_3:
    v9 = -2147024882;
    goto LABEL_4;
  }
LABEL_10:
  v9 = CNamedArguments::Create(a1, a2, (SAFEARRAY ***)v7 + 11);
  if ( v9 >= 0 )
  {
    v9 = CUnnamedArguments::Create(a1, a2, (struct CUnnamedArguments **)v7 + 12);
    if ( v9 >= 0 )
    {
      *a3 = (struct CArguments *)v7;
      return 0;
    }
  }
LABEL_4:
  (*(void (__fastcall **)(_QWORD *))(*v7 + 16LL))(v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140012d54  push    rbp
0x140012d56  push    rbx
0x140012d57  push    rsi
0x140012d58  push    rdi
0x140012d59  push    r12
0x140012d5b  push    r13
0x140012d5d  push    r14
0x140012d5f  push    r15
0x140012d61  mov     rbp, rsp
0x140012d64  sub     rsp, 48h
0x140012d68  mov     esi, ecx
0x140012d6a  xor     r13d, r13d
0x140012d6d  xorps   xmm0, xmm0
0x140012d70  mov     qword ptr [rbp+rgsabound.cElements], r13
0x140012d74  xor     eax, eax
0x140012d76  mov     [rbp+rgIndices], r13d
0x140012d7a  mov     ecx, 98h; Size
0x140012d7f  mov     [rbp+var_10], rax
0x140012d83  movups  [rbp+pv], xmm0
0x140012d87  mov     r15, r8
0x140012d8a  mov     r14, rdx
0x140012d8d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140012d92  mov     rdi, rax
0x140012d95  test    rax, rax
0x140012d98  jz      loc_140012F00
0x140012d9e  lea     rax, ??_7IWshRuntime@@6B@; const IWshRuntime::`vftable'
0x140012da5  mov     [rdi+8], rax
0x140012da9  lea     rcx, ??_7InnerUnknown@CUnknown@@6B@; const CUnknown::InnerUnknown::`vftable'
0x140012db0  lea     rax, ??_7CUnknown@@6B@; const CUnknown::`vftable'
0x140012db7  mov     [rdi+18h], rax
0x140012dbb  lea     edx, [r13+1]; cDims
0x140012dbf  lea     rax, [rdi+30h]
0x140012dc3  mov     [rax], rcx
0x140012dc6  mov     [rax+8], edx
0x140012dc9  mov     [rdi+20h], rax
0x140012dcd  mov     [rdi+28h], rdi
0x140012dd1  lock add cs:?g_cObjects@Global@@2JA, edx; long Global::g_cObjects
0x140012dd8  mov     [rdi+48h], r13b
0x140012ddc  lea     rax, ?TaUser_DescCArguments@@3UTaDescDispatch@@A; TaDescDispatch TaUser_DescCArguments
0x140012de3  mov     [rdi+40h], rax
0x140012de7  lea     ecx, [rdx+0Bh]; vt
0x140012dea  mov     [rdi+50h], r13
0x140012dee  lea     rax, ??_7CArguments@@6BIArguments2@@@; const CArguments::`vftable'{for `IArguments2'}
0x140012df5  mov     [rdi], rax
0x140012df8  lea     r8, [rbp+rgsabound]; rgsabound
0x140012dfc  mov     [rdi+58h], r13
0x140012e00  lea     rax, ??_7CArguments@@6BIWshRuntime@@@; const CArguments::`vftable'{for `IWshRuntime'}
0x140012e07  mov     [rdi+8], rax
0x140012e0b  lea     rax, ??_7CArguments@@6BIProvideClassInfo@@@; const CArguments::`vftable'{for `IProvideClassInfo'}
0x140012e12  mov     [rdi+10h], rax
0x140012e16  lea     rax, ??_7CArguments@@6BCDispatch@@@; const CArguments::`vftable'{for `CDispatch'}
0x140012e1d  mov     [rdi+18h], rax
0x140012e21  mov     [rdi+60h], r13
0x140012e25  mov     [rdi+70h], r13
0x140012e29  mov     [rdi+68h], r13
0x140012e2d  mov     [rdi+80h], r13
0x140012e34  mov     [rdi+88h], r13
0x140012e3b  mov     [rdi+78h], r13
0x140012e3f  mov     [rdi+90h], edx
0x140012e45  mov     [rbp+rgsabound.lLbound], r13d
0x140012e49  mov     [rbp+rgsabound.cElements], esi
0x140012e4c  call    cs:__imp_SafeArrayCreate
0x140012e52  mov     [rdi+50h], rax
0x140012e56  test    rax, rax
0x140012e59  jnz     short loc_140012E74
0x140012e5b  mov     ebx, 8007000Eh
0x140012e60  mov     rax, [rdi]
0x140012e63  mov     rcx, rdi
0x140012e66  mov     rax, [rax+10h]
0x140012e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012e6f  jmp     loc_140012F05
0x140012e74  mov     [rbp+rgIndices], r13d
0x140012e78  test    esi, esi
0x140012e7a  jle     short loc_140012ECC
0x140012e7c  mov     eax, r13d
0x140012e7f  mov     ecx, 8
0x140012e84  mov     word ptr [rbp+pv], cx
0x140012e88  movsxd  rcx, eax
0x140012e8b  mov     rcx, [r14+rcx*8]; psz
0x140012e8f  call    cs:__imp_SysAllocString
0x140012e95  mov     qword ptr [rbp+pv+8], rax
0x140012e99  test    rax, rax
0x140012e9c  jz      short loc_140012E5B
0x140012e9e  mov     rcx, [rdi+50h]; psa
0x140012ea2  lea     r8, [rbp+pv]; pv
0x140012ea6  lea     rdx, [rbp+rgIndices]; rgIndices
0x140012eaa  call    cs:__imp_SafeArrayPutElement
0x140012eb0  lea     rcx, [rbp+pv]; pvarg
0x140012eb4  mov     ebx, eax
0x140012eb6  call    cs:__imp_VariantClear
0x140012ebc  test    ebx, ebx
0x140012ebe  js      short loc_140012E60
0x140012ec0  mov     eax, [rbp+rgIndices]
0x140012ec3  inc     eax
0x140012ec5  mov     [rbp+rgIndices], eax
0x140012ec8  cmp     eax, esi
0x140012eca  jl      short loc_140012E7F
0x140012ecc  lea     r8, [rdi+58h]; struct CNamedArguments **
0x140012ed0  mov     rdx, r14; unsigned __int16 **
0x140012ed3  mov     ecx, esi; int
0x140012ed5  call    ?Create@CNamedArguments@@SAJJPEAPEBGPEAPEAV1@@Z; CNamedArguments::Create(long,ushort const * *,CNamedArguments * *)
0x140012eda  mov     ebx, eax
0x140012edc  test    eax, eax
0x140012ede  js      short loc_140012E60
0x140012ee0  lea     r8, [rdi+60h]; struct CUnnamedArguments **
0x140012ee4  mov     rdx, r14; unsigned __int16 **
0x140012ee7  mov     ecx, esi; int
0x140012ee9  call    ?Create@CUnnamedArguments@@SAJJPEAPEBGPEAPEAV1@@Z; CUnnamedArguments::Create(long,ushort const * *,CUnnamedArguments * *)
0x140012eee  mov     ebx, eax
0x140012ef0  test    eax, eax
0x140012ef2  js      loc_140012E60
0x140012ef8  mov     [r15], rdi
0x140012efb  mov     ebx, r13d
0x140012efe  jmp     short loc_140012F05
0x140012f00  mov     ebx, 8007000Eh
0x140012f05  mov     eax, ebx
0x140012f07  add     rsp, 48h
0x140012f0b  pop     r15
0x140012f0d  pop     r14
0x140012f0f  pop     r13
0x140012f11  pop     r12
0x140012f13  pop     rdi
0x140012f14  pop     rsi
0x140012f15  pop     rbx
0x140012f16  pop     rbp
0x140012f17  retn
```
