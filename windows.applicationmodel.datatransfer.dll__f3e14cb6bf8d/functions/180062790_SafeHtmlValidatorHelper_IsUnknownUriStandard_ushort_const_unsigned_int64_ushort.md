# SafeHtmlValidatorHelper::IsUnknownUriStandard(ushort const *,unsigned __int64,ushort * *)

- ea: `0x180062790`
- end: `0x1800628f7`
- name: `?IsUnknownUriStandard@SafeHtmlValidatorHelper@@YA_NPEBG_KPEAPEAG@Z`
- size: `359`
- prototype: `bool __fastcall(SafeHtmlValidatorHelper *__hidden this, const unsigned __int16 *, unsigned __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180062900`

## callees

- `0x180062790`
- `0x180081010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180062856`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180062856`
- `OLEAUT32!__imp_SysFreeString` at `0x1800628a3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800628c5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800628a3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800628c5`
- `OLEAUT32!__imp_SysStringLen` at `0x180062803`
- `OLEAUT32!__imp_SysStringLen` at `0x180062896`
- `OLEAUT32!__imp_SysStringLen` at `0x180062803`
- `OLEAUT32!__imp_SysStringLen` at `0x180062896`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x1800627c7`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x1800627c7`

## pseudocode

```c
bool __fastcall SafeHtmlValidatorHelper::IsUnknownUriStandard(
        const WCHAR *this,
        const unsigned __int16 *a2,
        BSTR *a3,
        unsigned __int16 **a4)
{
  bool v4; // di
  int v6; // eax
  UINT v7; // eax
  unsigned __int64 v8; // rsi
  OLECHAR *v9; // rcx
  unsigned __int64 v10; // rbx
  wchar_t v11; // dx
  wchar_t *v12; // rax
  UINT v13; // ebx
  BSTR bstrString[2]; // [rsp+20h] [rbp-10h] BYREF
  BSTR pbstr; // [rsp+68h] [rbp+38h] BYREF
  IUri *ppURI; // [rsp+78h] [rbp+48h] BYREF

  v4 = 0;
  if ( (unsigned __int64)a2 < 0x824 )
  {
    ppURI = 0;
    if ( CreateUri(this, 0, 0, &ppURI) >= 0 )
    {
      pbstr = 0;
      v6 = ((__int64 (__fastcall *)(IUri *, BSTR *))ppURI->lpVtbl->GetAbsoluteUri)(ppURI, &pbstr);
      if ( v6 < 0 )
      {
LABEL_19:
        ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
        return v4;
      }
      if ( v6 )
        goto LABEL_17;
      v7 = SysStringLen(pbstr);
      v8 = v7;
      if ( v7 <= 2uLL )
        goto LABEL_17;
      v9 = pbstr;
      if ( pbstr[v7 - 1] == 37 || pbstr[v7 - 2] == 37 )
        goto LABEL_18;
      v10 = 0;
      v4 = 1;
      while ( v10 < v8 )
      {
        v11 = v9[v10];
        if ( v11 < 0x80u )
        {
          v12 = wcschr(L"abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789-._~:/?#[]@!$&'()*+,;=% {}", v11);
          v9 = pbstr;
          if ( !v12 )
          {
            v4 = 0;
            goto LABEL_18;
          }
        }
        ++v10;
      }
      bstrString[0] = 0;
      if ( ((int (__fastcall *)(IUri *, BSTR *))ppURI->lpVtbl->GetSchemeName)(ppURI, bstrString) >= 0
        && (v13 = SysStringLen(bstrString[0]) - 2, SysFreeString(bstrString[0]), v4 = v13 <= 0x25, v13 > 0x25) )
      {
LABEL_17:
        v9 = pbstr;
      }
      else
      {
        v9 = 0;
        *a3 = pbstr;
        pbstr = 0;
      }
LABEL_18:
      SysFreeString(v9);
      pbstr = 0;
      goto LABEL_19;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180062790  mov     [rsp-28h+arg_0], rbx
0x180062795  push    rbp
0x180062796  push    rsi
0x180062797  push    rdi
0x180062798  push    r12
0x18006279a  push    r14
0x18006279c  mov     rbp, rsp
0x18006279f  sub     rsp, 30h
0x1800627a3  xor     dil, dil
0x1800627a6  mov     r14, r8
0x1800627a9  cmp     rdx, 824h
0x1800627b0  jnb     loc_1800628E3
0x1800627b6  lea     r9, [rbp+ppURI]; ppURI
0x1800627ba  mov     [rbp+ppURI], 0
0x1800627c2  xor     r8d, r8d; dwReserved
0x1800627c5  xor     edx, edx; dwFlags
0x1800627c7  call    cs:__imp_CreateUri
0x1800627cd  test    eax, eax
0x1800627cf  js      loc_1800628E3
0x1800627d5  mov     rcx, [rbp+ppURI]
0x1800627d9  lea     rdx, [rbp+pbstr]
0x1800627dd  mov     [rbp+pbstr], 0
0x1800627e5  mov     rax, [rcx]
0x1800627e8  mov     rax, [rax+38h]
0x1800627ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800627f1  test    eax, eax
0x1800627f3  js      loc_1800628D3
0x1800627f9  jnz     loc_1800628C1
0x1800627ff  mov     rcx, [rbp+pbstr]; pbstr
0x180062803  call    cs:__imp_SysStringLen
0x180062809  mov     esi, eax
0x18006280b  cmp     rsi, 2
0x18006280f  jbe     loc_1800628C1
0x180062815  mov     rcx, [rbp+pbstr]
0x180062819  mov     r12d, 25h ; '%'
0x18006281f  cmp     [rcx+rsi*2-2], r12w
0x180062825  jz      loc_1800628C5
0x18006282b  cmp     [rcx+rsi*2-4], r12w
0x180062831  jz      loc_1800628C5
0x180062837  xor     ebx, ebx
0x180062839  lea     edi, [rbx+1]
0x18006283c  cmp     rbx, rsi
0x18006283f  jnb     short loc_18006286F
0x180062841  movzx   edx, word ptr [rcx+rbx*2]; Ch
0x180062845  mov     eax, 80h
0x18006284a  cmp     dx, ax
0x18006284d  jnb     short loc_180062865
0x18006284f  lea     rcx, ?szAllowedUriCharacters@?BB@??IsUnknownUriStandard@SafeHtmlValidatorHelper@@YA_NPEBG_KPEAPEAG@Z@4QBGB; "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLM"...
0x180062856  call    cs:__imp_wcschr
0x18006285c  mov     rcx, [rbp+pbstr]
0x180062860  test    rax, rax
0x180062863  jz      short loc_18006286A
0x180062865  add     rbx, rdi
0x180062868  jmp     short loc_18006283C
0x18006286a  xor     dil, dil
0x18006286d  jmp     short loc_1800628C5
0x18006286f  mov     rcx, [rbp+ppURI]
0x180062873  lea     rdx, [rbp+bstrString]
0x180062877  mov     [rbp+bstrString], 0
0x18006287f  mov     rax, [rcx]
0x180062882  mov     rax, [rax+98h]
0x180062889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006288e  test    eax, eax
0x180062890  js      short loc_1800628B2
0x180062892  mov     rcx, [rbp+bstrString]; pbstr
0x180062896  call    cs:__imp_SysStringLen
0x18006289c  mov     rcx, [rbp+bstrString]; bstrString
0x1800628a0  lea     ebx, [rax-2]
0x1800628a3  call    cs:__imp_SysFreeString
0x1800628a9  cmp     ebx, r12d
0x1800628ac  setbe   dil
0x1800628b0  ja      short loc_1800628C1
0x1800628b2  mov     rax, [rbp+pbstr]
0x1800628b6  xor     ecx, ecx
0x1800628b8  mov     [r14], rax
0x1800628bb  mov     [rbp+pbstr], rcx
0x1800628bf  jmp     short loc_1800628C5
0x1800628c1  mov     rcx, [rbp+pbstr]; bstrString
0x1800628c5  call    cs:__imp_SysFreeString
0x1800628cb  mov     [rbp+pbstr], 0
0x1800628d3  mov     rcx, [rbp+ppURI]
0x1800628d7  mov     rdx, [rcx]
0x1800628da  mov     rax, [rdx+10h]
0x1800628de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800628e3  mov     rbx, [rsp+30h+arg_0]
0x1800628e8  mov     al, dil
0x1800628eb  add     rsp, 30h
0x1800628ef  pop     r14
0x1800628f1  pop     r12
0x1800628f3  pop     rdi
0x1800628f4  pop     rsi
0x1800628f5  pop     rbp
0x1800628f6  retn
```
