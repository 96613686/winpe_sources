# CWshEnvRegistry::_NewEnum(IUnknown * *)

- ea: `0x18000bc60`
- end: `0x18000bdb1`
- name: `?_NewEnum@CWshEnvRegistry@@UEAAJPEAPEAUIUnknown@@@Z`
- size: `337`
- prototype: `__int64 __fastcall(CWshEnvRegistry *__hidden this, struct IUnknown **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18000b2f8`
- `0x18000b50c`
- `0x18000bc60`
- `0x18000df6c`
- `0x180011010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000bd3c`
- `OLEAUT32!__imp_VariantClear` at `0x18000bd3c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000bd9e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000bd9e`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000bd30`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000bd30`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18000bcca`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18000bcca`

## pseudocode

```c
__int64 __fastcall CWshEnvRegistry::_NewEnum(HKEY *this, struct IUnknown **a2)
{
  HRESULT v5; // ebx
  SAFEARRAY *Vector; // rsi
  signed int i; // eax
  HKEY v8; // rcx
  int v9; // eax
  int v10; // eax
  struct CEnumVARIANT *v11; // rdi
  VARIANTARG pv; // [rsp+20h] [rbp-20h] BYREF
  LONG rgIndices; // [rsp+78h] [rbp+38h] BYREF
  ULONG cElements; // [rsp+80h] [rbp+40h] BYREF
  struct CEnumVARIANT *v15; // [rsp+88h] [rbp+48h] BYREF

  cElements = 0;
  rgIndices = 0;
  v15 = 0;
  memset(&pv, 0, sizeof(pv));
  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v5 = (*((__int64 (__fastcall **)(HKEY *, ULONG *))*this + 9))(this, &cElements);
  if ( v5 >= 0 )
  {
    Vector = SafeArrayCreateVector(0xCu, 0, cElements);
    if ( Vector )
    {
      rgIndices = 0;
      for ( i = 0; i < (int)cElements; i = ++rgIndices )
      {
        pv.vt = 8;
        v8 = this[9];
        v9 = Global::g_fWindowsNT
           ? CWshEnvRegistry::GetEnvStringFromRegW(v8, i, &pv.bstrVal)
           : CWshEnvRegistry::GetEnvStringFromRegA(v8, i, &pv.bstrVal);
        v5 = v9;
        if ( v9 == -2147024637 )
          break;
        if ( v9 < 0 )
          goto LABEL_20;
        v5 = SafeArrayPutElement(Vector, &rgIndices, &pv);
        VariantClear(&pv);
        if ( v5 < 0 )
          goto LABEL_20;
      }
      v10 = CEnumVARIANT::Create(Vector, &v15);
      v11 = v15;
      v5 = v10;
      if ( v10 >= 0 )
      {
        v5 = (**(__int64 (__fastcall ***)(struct CEnumVARIANT *, GUID *, struct IUnknown **))v15)(
               v15,
               &IID_IUnknown,
               a2);
        if ( v5 >= 0 )
          v5 = 0;
      }
      if ( v11 )
        (*(void (__fastcall **)(struct CEnumVARIANT *))(*(_QWORD *)v11 + 16LL))(v11);
LABEL_20:
      SafeArrayDestroy(Vector);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000bc60  push    rbp
0x18000bc62  push    rbx
0x18000bc63  push    rsi
0x18000bc64  push    rdi
0x18000bc65  push    r14
0x18000bc67  mov     rbp, rsp
0x18000bc6a  sub     rsp, 40h
0x18000bc6e  xor     eax, eax
0x18000bc70  mov     [rbp+cElements], 0
0x18000bc77  mov     [rbp+rgIndices], 0
0x18000bc7e  xorps   xmm0, xmm0
0x18000bc81  mov     [rbp+var_10], rax
0x18000bc85  mov     r14, rdx
0x18000bc88  mov     [rbp+arg_18], rax
0x18000bc8c  mov     rdi, rcx
0x18000bc8f  movups  [rbp+pv], xmm0
0x18000bc93  test    rdx, rdx
0x18000bc96  jnz     short loc_18000BCA2
0x18000bc98  mov     eax, 80004003h
0x18000bc9d  jmp     loc_18000BDA6
0x18000bca2  mov     [rdx], rax
0x18000bca5  lea     rdx, [rbp+cElements]
0x18000bca9  mov     rax, [rcx]
0x18000bcac  mov     rax, [rax+48h]
0x18000bcb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcb5  mov     ebx, eax
0x18000bcb7  test    eax, eax
0x18000bcb9  js      loc_18000BDA4
0x18000bcbf  mov     r8d, [rbp+cElements]; cElements
0x18000bcc3  mov     ecx, 0Ch; vt
0x18000bcc8  xor     edx, edx; lLbound
0x18000bcca  call    cs:__imp_SafeArrayCreateVector
0x18000bcd0  mov     rsi, rax
0x18000bcd3  test    rax, rax
0x18000bcd6  jnz     short loc_18000BCE2
0x18000bcd8  mov     ebx, 8007000Eh
0x18000bcdd  jmp     loc_18000BDA4
0x18000bce2  mov     [rbp+rgIndices], 0
0x18000bce9  xor     eax, eax
0x18000bceb  cmp     eax, [rbp+cElements]
0x18000bcee  jge     short loc_18000BD50
0x18000bcf0  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x18000bcf7  lea     r8, [rbp+pv+8]; unsigned __int16 **
0x18000bcfb  mov     ecx, 8
0x18000bd00  mov     edx, eax; dwIndex
0x18000bd02  mov     word ptr [rbp+pv], cx
0x18000bd06  mov     rcx, [rdi+48h]; hKey
0x18000bd0a  jz      short loc_18000BD13
0x18000bd0c  call    ?GetEnvStringFromRegW@CWshEnvRegistry@@CAJPEAUHKEY__@@JPEAPEAG@Z; CWshEnvRegistry::GetEnvStringFromRegW(HKEY__ *,long,ushort * *)
0x18000bd11  jmp     short loc_18000BD18
0x18000bd13  call    ?GetEnvStringFromRegA@CWshEnvRegistry@@CAJPEAUHKEY__@@JPEAPEAG@Z; CWshEnvRegistry::GetEnvStringFromRegA(HKEY__ *,long,ushort * *)
0x18000bd18  mov     ebx, eax
0x18000bd1a  cmp     eax, 80070103h
0x18000bd1f  jz      short loc_18000BD50
0x18000bd21  test    eax, eax
0x18000bd23  js      short loc_18000BD9B
0x18000bd25  lea     r8, [rbp+pv]; pv
0x18000bd29  mov     rcx, rsi; psa
0x18000bd2c  lea     rdx, [rbp+rgIndices]; rgIndices
0x18000bd30  call    cs:__imp_SafeArrayPutElement
0x18000bd36  lea     rcx, [rbp+pv]; pvarg
0x18000bd3a  mov     ebx, eax
0x18000bd3c  call    cs:__imp_VariantClear
0x18000bd42  test    ebx, ebx
0x18000bd44  js      short loc_18000BD9B
0x18000bd46  mov     eax, [rbp+rgIndices]
0x18000bd49  inc     eax
0x18000bd4b  mov     [rbp+rgIndices], eax
0x18000bd4e  jmp     short loc_18000BCEB
0x18000bd50  lea     rdx, [rbp+arg_18]; struct CEnumVARIANT **
0x18000bd54  mov     rcx, rsi; psa
0x18000bd57  call    ?Create@CEnumVARIANT@@SAJPEAUtagSAFEARRAY@@PEAPEAV1@@Z; CEnumVARIANT::Create(tagSAFEARRAY *,CEnumVARIANT * *)
0x18000bd5c  mov     rdi, [rbp+arg_18]
0x18000bd60  mov     ebx, eax
0x18000bd62  test    eax, eax
0x18000bd64  js      short loc_18000BD87
0x18000bd66  mov     rax, [rdi]
0x18000bd69  lea     rdx, IID_IUnknown
0x18000bd70  mov     r8, r14
0x18000bd73  mov     rcx, rdi
0x18000bd76  mov     rax, [rax]
0x18000bd79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd7e  mov     ebx, eax
0x18000bd80  xor     eax, eax
0x18000bd82  test    ebx, ebx
0x18000bd84  cmovns  ebx, eax
0x18000bd87  test    rdi, rdi
0x18000bd8a  jz      short loc_18000BD9B
0x18000bd8c  mov     rax, [rdi]
0x18000bd8f  mov     rcx, rdi
0x18000bd92  mov     rax, [rax+10h]
0x18000bd96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd9b  mov     rcx, rsi; psa
0x18000bd9e  call    cs:__imp_SafeArrayDestroy
0x18000bda4  mov     eax, ebx
0x18000bda6  add     rsp, 40h
0x18000bdaa  pop     r14
0x18000bdac  pop     rdi
0x18000bdad  pop     rsi
0x18000bdae  pop     rbx
0x18000bdaf  pop     rbp
0x18000bdb0  retn
```
