# CWshShell::get_SpecialFolders(IWshCollection * *)

- ea: `0x18000ca00`
- end: `0x18000cc6d`
- name: `?get_SpecialFolders@CWshShell@@UEAAJPEAPEAUIWshCollection@@@Z`
- size: `621`
- prototype: `__int64 __fastcall(CWshShell *__hidden this, struct IWshCollection **)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004cc0`
- `0x1800060e4`
- `0x1800070f4`
- `0x180007300`
- `0x18000ca00`
- `0x180011010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000cb1f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000cbbe`
- `OLEAUT32!__imp_SysAllocString` at `0x18000cb1f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000cbbe`
- `OLEAUT32!__imp_VariantClear` at `0x18000cad4`
- `OLEAUT32!__imp_VariantClear` at `0x18000cb0d`
- `OLEAUT32!__imp_VariantClear` at `0x18000cc3f`
- `OLEAUT32!__imp_VariantClear` at `0x18000cc49`
- `OLEAUT32!__imp_VariantClear` at `0x18000cc53`
- `OLEAUT32!__imp_VariantClear` at `0x18000cad4`
- `OLEAUT32!__imp_VariantClear` at `0x18000cb0d`
- `OLEAUT32!__imp_VariantClear` at `0x18000cc3f`
- `OLEAUT32!__imp_VariantClear` at `0x18000cc49`
- `OLEAUT32!__imp_VariantClear` at `0x18000cc53`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000cbfb`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000cc04`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000cbfb`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000cc04`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000caf9`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000cb3d`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000caf9`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000cb3d`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18000cb70`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18000cb83`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18000cb70`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18000cb83`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18000ca70`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18000ca8f`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18000ca70`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18000ca8f`
- `SHELL32!SHGetMalloc` at `0x18000caab`
- `SHELL32!SHGetMalloc` at `0x18000caab`

## pseudocode

```c
__int64 __fastcall CWshShell::get_SpecialFolders(CWshShell *this, struct IWshCollection **a2)
{
  CWshCollection *v4; // rdi
  SAFEARRAY *Vector; // r12
  HRESULT v6; // ebx
  SAFEARRAY *v7; // r14
  ULONG v8; // eax
  wchar_t **v9; // rsi
  const OLECHAR *v10; // rcx
  CWshCollection *v11; // rax
  struct IUnknown *v12; // rdx
  __int64 v13; // r9
  VARIANTARG pv; // [rsp+30h] [rbp-50h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-38h] BYREF
  VARIANTARG v16; // [rsp+60h] [rbp-20h] BYREF
  LONG rgIndices; // [rsp+C8h] [rbp+48h] BYREF
  SAFEARRAYBOUND psaboundNew; // [rsp+D0h] [rbp+50h] BYREF
  IMalloc *ppMalloc; // [rsp+D8h] [rbp+58h] BYREF

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v4 = 0;
  rgIndices = 0;
  ppMalloc = 0;
  psaboundNew = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&pv, 0, sizeof(pv));
  memset(&v16, 0, sizeof(v16));
  Vector = SafeArrayCreateVector(0xCu, 0, 0x13u);
  if ( Vector )
  {
    v7 = SafeArrayCreateVector(0xCu, 0, 0x13u);
    if ( v7 )
    {
      v6 = SHGetMalloc(&ppMalloc);
      if ( v6 >= 0 )
      {
        v8 = 0;
        v9 = &off_180018390;
        rgIndices = 0;
        while ( *v9 )
        {
          VariantClear(&pvarg);
          if ( (int)GetFolder((__int64)ppMalloc, *((_DWORD *)v9 + 2), (__int64)&pvarg) < 0 )
          {
            v8 = rgIndices;
          }
          else
          {
            v6 = SafeArrayPutElement(Vector, &rgIndices, &pvarg);
            if ( v6 < 0 )
              goto LABEL_25;
            VariantClear(&pv);
            v10 = *v9;
            pv.vt = 8;
            pv.llVal = (LONGLONG)SysAllocString(v10);
            if ( !pv.llVal )
              goto LABEL_24;
            v6 = SafeArrayPutElement(v7, &rgIndices, &pv);
            if ( v6 < 0 )
              goto LABEL_25;
            v8 = ++rgIndices;
          }
          v9 += 2;
        }
        psaboundNew.lLbound = 0;
        psaboundNew.cElements = v8;
        v6 = SafeArrayRedim(Vector, &psaboundNew);
        if ( v6 >= 0 )
        {
          v6 = SafeArrayRedim(v7, &psaboundNew);
          if ( v6 >= 0 )
          {
            v11 = (CWshCollection *)operator new(0x78u);
            if ( !v11
              || (v4 = CWshCollection::CWshCollection(v11, v12)) == 0
              || (v16.vt = 8, (v16.llVal = (LONGLONG)SysAllocString(&psz)) == 0) )
            {
LABEL_24:
              v6 = -2147024882;
              goto LABEL_25;
            }
            v6 = CWshCollection::Init(v4, Vector, v7, v13, &v16);
            if ( v6 >= 0 )
            {
              *a2 = v4;
              v4 = 0;
              v6 = 0;
            }
          }
        }
      }
LABEL_25:
      SafeArrayDestroy(v7);
    }
    else
    {
      v6 = -2147024882;
    }
    SafeArrayDestroy(Vector);
  }
  else
  {
    v6 = -2147024882;
  }
  if ( ppMalloc )
  {
    ((void (__fastcall *)(IMalloc *))ppMalloc->lpVtbl->Release)(ppMalloc);
    ppMalloc = 0;
  }
  if ( v4 )
    (*(void (__fastcall **)(CWshCollection *))(*(_QWORD *)v4 + 16LL))(v4);
  VariantClear(&pvarg);
  VariantClear(&pv);
  VariantClear(&v16);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000ca00  push    rbp
0x18000ca02  push    rbx
0x18000ca03  push    rsi
0x18000ca04  push    rdi
0x18000ca05  push    r12
0x18000ca07  push    r14
0x18000ca09  push    r15
0x18000ca0b  mov     rbp, rsp
0x18000ca0e  sub     rsp, 80h
0x18000ca15  mov     r15, rdx
0x18000ca18  test    rdx, rdx
0x18000ca1b  jnz     short loc_18000CA27
0x18000ca1d  mov     eax, 80004003h
0x18000ca22  jmp     loc_18000CC5B
0x18000ca27  xor     eax, eax
0x18000ca29  mov     qword ptr [rdx], 0
0x18000ca30  xor     edi, edi
0x18000ca32  mov     [rbp+rgIndices], 0
0x18000ca39  xorps   xmm0, xmm0
0x18000ca3c  mov     [rbp+ppMalloc], 0
0x18000ca44  xorps   xmm1, xmm1
0x18000ca47  mov     qword ptr [rbp+psaboundNew.cElements], rdi
0x18000ca4b  xor     edx, edx; lLbound
0x18000ca4d  mov     qword ptr [rbp+pvarg+10h], rax
0x18000ca51  lea     ebx, [rdi+0Ch]
0x18000ca54  mov     qword ptr [rbp+pv+10h], rax
0x18000ca58  lea     esi, [rdi+13h]
0x18000ca5b  mov     qword ptr [rbp+var_20+10h], rax
0x18000ca5f  mov     ecx, ebx; vt
0x18000ca61  mov     r8d, esi; cElements
0x18000ca64  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000ca68  movups  xmmword ptr [rbp+pv], xmm1
0x18000ca6c  movups  xmmword ptr [rbp+var_20], xmm0
0x18000ca70  call    cs:__imp_SafeArrayCreateVector
0x18000ca76  mov     r12, rax
0x18000ca79  test    rax, rax
0x18000ca7c  jnz     short loc_18000CA88
0x18000ca7e  mov     ebx, 8007000Eh
0x18000ca83  jmp     loc_18000CC0A
0x18000ca88  mov     ecx, ebx; vt
0x18000ca8a  mov     r8d, esi; cElements
0x18000ca8d  xor     edx, edx; lLbound
0x18000ca8f  call    cs:__imp_SafeArrayCreateVector
0x18000ca95  mov     r14, rax
0x18000ca98  test    rax, rax
0x18000ca9b  jnz     short loc_18000CAA7
0x18000ca9d  mov     ebx, 8007000Eh
0x18000caa2  jmp     loc_18000CC01
0x18000caa7  lea     rcx, [rbp+ppMalloc]; ppMalloc
0x18000caab  call    cs:__imp_SHGetMalloc
0x18000cab1  mov     ebx, eax
0x18000cab3  test    eax, eax
0x18000cab5  js      loc_18000CBF8
0x18000cabb  xor     eax, eax
0x18000cabd  lea     rsi, off_180018390; "AllUsersDesktop"
0x18000cac4  mov     [rbp+rgIndices], eax
0x18000cac7  cmp     [rsi], rdi
0x18000caca  jz      loc_18000CB63
0x18000cad0  lea     rcx, [rbp+pvarg]; pvarg
0x18000cad4  call    cs:__imp_VariantClear
0x18000cada  mov     edx, [rsi+8]
0x18000cadd  lea     r8, [rbp+pvarg]
0x18000cae1  mov     rcx, [rbp+ppMalloc]
0x18000cae5  call    GetFolder
0x18000caea  test    eax, eax
0x18000caec  js      short loc_18000CB57
0x18000caee  lea     r8, [rbp+pvarg]; pv
0x18000caf2  mov     rcx, r12; psa
0x18000caf5  lea     rdx, [rbp+rgIndices]; rgIndices
0x18000caf9  call    cs:__imp_SafeArrayPutElement
0x18000caff  mov     ebx, eax
0x18000cb01  test    eax, eax
0x18000cb03  js      loc_18000CBF8
0x18000cb09  lea     rcx, [rbp+pv]; pvarg
0x18000cb0d  call    cs:__imp_VariantClear
0x18000cb13  mov     rcx, [rsi]; psz
0x18000cb16  mov     eax, 8
0x18000cb1b  mov     word ptr [rbp+pv], ax
0x18000cb1f  call    cs:__imp_SysAllocString
0x18000cb25  mov     qword ptr [rbp+pv+8], rax
0x18000cb29  test    rax, rax
0x18000cb2c  jz      loc_18000CBF3
0x18000cb32  lea     r8, [rbp+pv]; pv
0x18000cb36  mov     rcx, r14; psa
0x18000cb39  lea     rdx, [rbp+rgIndices]; rgIndices
0x18000cb3d  call    cs:__imp_SafeArrayPutElement
0x18000cb43  mov     ebx, eax
0x18000cb45  test    eax, eax
0x18000cb47  js      loc_18000CBF8
0x18000cb4d  mov     eax, [rbp+rgIndices]
0x18000cb50  inc     eax
0x18000cb52  mov     [rbp+rgIndices], eax
0x18000cb55  jmp     short loc_18000CB5A
0x18000cb57  mov     eax, [rbp+rgIndices]
0x18000cb5a  add     rsi, 10h
0x18000cb5e  jmp     loc_18000CAC7
0x18000cb63  lea     rdx, [rbp+psaboundNew]; psaboundNew
0x18000cb67  mov     [rbp+psaboundNew.lLbound], edi
0x18000cb6a  mov     rcx, r12; psa
0x18000cb6d  mov     [rbp+psaboundNew.cElements], eax
0x18000cb70  call    cs:__imp_SafeArrayRedim
0x18000cb76  mov     ebx, eax
0x18000cb78  test    eax, eax
0x18000cb7a  js      short loc_18000CBF8
0x18000cb7c  lea     rdx, [rbp+psaboundNew]; psaboundNew
0x18000cb80  mov     rcx, r14; psa
0x18000cb83  call    cs:__imp_SafeArrayRedim
0x18000cb89  mov     ebx, eax
0x18000cb8b  test    eax, eax
0x18000cb8d  js      short loc_18000CBF8
0x18000cb8f  mov     ecx, 78h ; 'x'; Size
0x18000cb94  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cb99  test    rax, rax
0x18000cb9c  jz      short loc_18000CBF3
0x18000cb9e  mov     rcx, rax; this
0x18000cba1  call    ??0CWshCollection@@QEAA@PEAUIUnknown@@@Z; CWshCollection::CWshCollection(IUnknown *)
0x18000cba6  mov     rdi, rax
0x18000cba9  test    rax, rax
0x18000cbac  jz      short loc_18000CBF3
0x18000cbae  mov     eax, 8
0x18000cbb3  lea     rcx, psz; psz
0x18000cbba  mov     word ptr [rbp+var_20], ax
0x18000cbbe  call    cs:__imp_SysAllocString
0x18000cbc4  mov     qword ptr [rbp+var_20+8], rax
0x18000cbc8  test    rax, rax
0x18000cbcb  jz      short loc_18000CBF3
0x18000cbcd  lea     rax, [rbp+var_20]
0x18000cbd1  mov     r8, r14; struct tagSAFEARRAY *
0x18000cbd4  mov     rdx, r12; struct tagSAFEARRAY *
0x18000cbd7  mov     [rsp+80h+var_60], rax; struct tagVARIANT *
0x18000cbdc  mov     rcx, rdi; this
0x18000cbdf  call    ?Init@CWshCollection@@QEAAJPEAUtagSAFEARRAY@@0JPEAUtagVARIANT@@@Z; CWshCollection::Init(tagSAFEARRAY *,tagSAFEARRAY *,long,tagVARIANT *)
0x18000cbe4  mov     ebx, eax
0x18000cbe6  test    eax, eax
0x18000cbe8  js      short loc_18000CBF8
0x18000cbea  mov     [r15], rdi
0x18000cbed  xor     edi, edi
0x18000cbef  xor     ebx, ebx
0x18000cbf1  jmp     short loc_18000CBF8
0x18000cbf3  mov     ebx, 8007000Eh
0x18000cbf8  mov     rcx, r14; psa
0x18000cbfb  call    cs:__imp_SafeArrayDestroy
0x18000cc01  mov     rcx, r12; psa
0x18000cc04  call    cs:__imp_SafeArrayDestroy
0x18000cc0a  mov     rcx, [rbp+ppMalloc]
0x18000cc0e  test    rcx, rcx
0x18000cc11  jz      short loc_18000CC27
0x18000cc13  mov     rax, [rcx]
0x18000cc16  mov     rax, [rax+10h]
0x18000cc1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc1f  mov     [rbp+ppMalloc], 0
0x18000cc27  test    rdi, rdi
0x18000cc2a  jz      short loc_18000CC3B
0x18000cc2c  mov     rax, [rdi]
0x18000cc2f  mov     rcx, rdi
0x18000cc32  mov     rax, [rax+10h]
0x18000cc36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc3b  lea     rcx, [rbp+pvarg]; pvarg
0x18000cc3f  call    cs:__imp_VariantClear
0x18000cc45  lea     rcx, [rbp+pv]; pvarg
0x18000cc49  call    cs:__imp_VariantClear
0x18000cc4f  lea     rcx, [rbp+var_20]; pvarg
0x18000cc53  call    cs:__imp_VariantClear
0x18000cc59  mov     eax, ebx
0x18000cc5b  add     rsp, 80h
0x18000cc62  pop     r15
0x18000cc64  pop     r14
0x18000cc66  pop     r12
0x18000cc68  pop     rdi
0x18000cc69  pop     rsi
0x18000cc6a  pop     rbx
0x18000cc6b  pop     rbp
0x18000cc6c  retn
```
