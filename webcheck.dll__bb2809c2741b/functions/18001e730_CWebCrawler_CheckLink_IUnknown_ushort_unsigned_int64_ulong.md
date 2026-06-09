# CWebCrawler::CheckLink(IUnknown *,ushort * *,unsigned __int64,ulong *)

- ea: `0x18001e730`
- end: `0x18001e916`
- name: `?CheckLink@CWebCrawler@@KAJPEAUIUnknown@@PEAPEAG_KPEAK@Z`
- size: `486`
- prototype: `static int(struct IUnknown *, unsigned __int16 **, unsigned __int64, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180007630`
- `0x180007754`
- `0x18001d794`
- `0x18001e730`
- `0x180020150`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001e7c8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e8ab`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e8c6`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e7c8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e8ab`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e8c6`

## pseudocode

```c
__int64 __fastcall CWebCrawler::CheckLink(struct IUnknown *a1, LPCWSTR *a2, __int64 a3, unsigned int *a4)
{
  int IsValidURL; // eax
  OLECHAR *v9; // rcx
  __int64 result; // rax
  unsigned int v11; // r14d
  struct IUnknownVtbl *lpVtbl; // rax
  __int64 v13; // rcx
  OLECHAR *v14; // r10
  const unsigned __int16 *v15; // rdx
  __int64 v16; // [rsp+20h] [rbp-10h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+38h] BYREF
  __int64 v18; // [rsp+70h] [rbp+40h] BYREF

  if ( !a2 || !*a2 || !a1 || !a3 )
    return 2147500037LL;
  IsValidURL = CUrlDownload::IsValidURL(*a2);
  v9 = (OLECHAR *)*a2;
  if ( !IsValidURL )
  {
LABEL_15:
    SysFreeString(v9);
    result = 1;
    *a2 = 0;
    return result;
  }
  if ( v9 )
  {
    while ( *v9 && *v9 != 63 )
    {
      if ( *v9 == 35 )
      {
        *v9 = 0;
        break;
      }
      ++v9;
    }
  }
  if ( (*(_DWORD *)(a3 + 136) & 0x100) != 0 && (unsigned int)CUrlDownload::IsNonHtmlUrl(*a2) )
  {
    v9 = (OLECHAR *)*a2;
    goto LABEL_15;
  }
  v11 = 0;
  if ( (*(_BYTE *)(a3 + 136) & 0x20) != 0 )
    goto LABEL_30;
  lpVtbl = a1->lpVtbl;
  bstrString = 0;
  v18 = 0;
  v16 = 0;
  ((void (__fastcall *)(struct IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(a1, &IID_IHTMLAnchorElement, &v18);
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v18 + 192LL))(v18, &bstrString);
    v13 = v18;
    goto LABEL_21;
  }
  ((void (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
    a1,
    &IID_IHTMLAreaElement,
    &v16);
  if ( !v16 )
    return 2147500037LL;
  (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v16 + 176LL))(v16, &bstrString);
  v13 = v16;
LABEL_21:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  v14 = bstrString;
  if ( bstrString )
  {
    if ( *bstrString )
    {
      v15 = *(const unsigned __int16 **)(a3 + 320);
      if ( v15 )
      {
        if ( (unsigned int)MyAsciiCmpW(bstrString, v15) )
        {
          if ( *a2 )
          {
            SysFreeString((BSTR)*a2);
            v14 = bstrString;
            *a2 = 0;
          }
          v11 = 1;
        }
      }
    }
    if ( v14 )
      SysFreeString(v14);
  }
LABEL_30:
  if ( a4 )
  {
    if ( *a2 )
    {
      CWebCrawler::GetRobotsTxtIndex((CWebCrawler *)a3, *a2, 1, a4);
      *a4 &= 0xFFFu;
    }
    else
    {
      *a4 = 0;
    }
  }
  return v11;
}

```

## disassembly

```asm
0x18001e730  mov     [rsp-28h+arg_0], rbx
0x18001e735  mov     [rsp-28h+arg_18], rsi
0x18001e73a  push    rbp
0x18001e73b  push    rdi
0x18001e73c  push    r13
0x18001e73e  push    r14
0x18001e740  push    r15
0x18001e742  mov     rbp, rsp
0x18001e745  sub     rsp, 30h
0x18001e749  xor     r13d, r13d
0x18001e74c  mov     rdi, r9
0x18001e74f  mov     r15, r8
0x18001e752  mov     rbx, rdx
0x18001e755  mov     rsi, rcx
0x18001e758  test    rdx, rdx
0x18001e75b  jz      loc_18001E8FA
0x18001e761  mov     rcx, [rdx]; szURL
0x18001e764  test    rcx, rcx
0x18001e767  jz      loc_18001E8FA
0x18001e76d  test    rsi, rsi
0x18001e770  jz      loc_18001E8FA
0x18001e776  test    r8, r8
0x18001e779  jz      loc_18001E8FA
0x18001e77f  call    ?IsValidURL@CUrlDownload@@SAHPEBG@Z; CUrlDownload::IsValidURL(ushort const *)
0x18001e784  mov     rcx, [rbx]
0x18001e787  test    eax, eax
0x18001e789  jz      short loc_18001E7C8
0x18001e78b  test    rcx, rcx
0x18001e78e  jz      short loc_18001E7AC
0x18001e790  cmp     [rcx], r13w
0x18001e794  jz      short loc_18001E7AC
0x18001e796  cmp     word ptr [rcx], 3Fh ; '?'
0x18001e79a  jz      short loc_18001E7AC
0x18001e79c  cmp     word ptr [rcx], 23h ; '#'
0x18001e7a0  jz      short loc_18001E7A8
0x18001e7a2  add     rcx, 2
0x18001e7a6  jmp     short loc_18001E790
0x18001e7a8  mov     [rcx], r13w
0x18001e7ac  test    dword ptr [r15+88h], 100h
0x18001e7b7  jz      short loc_18001E7DB
0x18001e7b9  mov     rcx, [rbx]; unsigned __int16 *
0x18001e7bc  call    ?IsNonHtmlUrl@CUrlDownload@@SAHPEBG@Z; CUrlDownload::IsNonHtmlUrl(ushort const *)
0x18001e7c1  test    eax, eax
0x18001e7c3  jz      short loc_18001E7DB
0x18001e7c5  mov     rcx, [rbx]; bstrString
0x18001e7c8  call    cs:__imp_SysFreeString
0x18001e7ce  mov     eax, 1
0x18001e7d3  mov     [rbx], r13
0x18001e7d6  jmp     loc_18001E8FF
0x18001e7db  test    byte ptr [r15+88h], 20h
0x18001e7e3  mov     r14d, r13d
0x18001e7e6  jnz     loc_18001E8CC
0x18001e7ec  mov     rax, [rsi]
0x18001e7ef  lea     r8, [rbp+arg_10]
0x18001e7f3  lea     rdx, IID_IHTMLAnchorElement
0x18001e7fa  mov     [rbp+bstrString], r13
0x18001e7fe  mov     rcx, rsi
0x18001e801  mov     [rbp+arg_10], r13
0x18001e805  mov     [rbp+var_10], r13
0x18001e809  mov     rax, [rax]
0x18001e80c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e811  mov     rcx, [rbp+arg_10]
0x18001e815  test    rcx, rcx
0x18001e818  jz      short loc_18001E833
0x18001e81a  mov     rax, [rcx]
0x18001e81d  lea     rdx, [rbp+bstrString]
0x18001e821  mov     rax, [rax+0C0h]
0x18001e828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e82d  mov     rcx, [rbp+arg_10]
0x18001e831  jmp     short loc_18001E870
0x18001e833  mov     rax, [rsi]
0x18001e836  lea     r8, [rbp+var_10]
0x18001e83a  lea     rdx, IID_IHTMLAreaElement
0x18001e841  mov     rcx, rsi
0x18001e844  mov     rax, [rax]
0x18001e847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e84c  mov     rcx, [rbp+var_10]
0x18001e850  test    rcx, rcx
0x18001e853  jz      loc_18001E8FA
0x18001e859  mov     rax, [rcx]
0x18001e85c  lea     rdx, [rbp+bstrString]
0x18001e860  mov     rax, [rax+0B0h]
0x18001e867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e86c  mov     rcx, [rbp+var_10]
0x18001e870  mov     rax, [rcx]
0x18001e873  mov     rax, [rax+10h]
0x18001e877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e87c  mov     r10, [rbp+bstrString]
0x18001e880  test    r10, r10
0x18001e883  jz      short loc_18001E8CC
0x18001e885  cmp     [r10], r13w
0x18001e889  jz      short loc_18001E8BE
0x18001e88b  mov     rdx, [r15+140h]; unsigned __int16 *
0x18001e892  test    rdx, rdx
0x18001e895  jz      short loc_18001E8BE
0x18001e897  mov     rcx, r10; unsigned __int16 *
0x18001e89a  call    ?MyAsciiCmpW@@YAHPEBG0@Z; MyAsciiCmpW(ushort const *,ushort const *)
0x18001e89f  test    eax, eax
0x18001e8a1  jz      short loc_18001E8BE
0x18001e8a3  mov     rcx, [rbx]; bstrString
0x18001e8a6  test    rcx, rcx
0x18001e8a9  jz      short loc_18001E8B8
0x18001e8ab  call    cs:__imp_SysFreeString
0x18001e8b1  mov     r10, [rbp+bstrString]
0x18001e8b5  mov     [rbx], r13
0x18001e8b8  mov     r14d, 1
0x18001e8be  test    r10, r10
0x18001e8c1  jz      short loc_18001E8CC
0x18001e8c3  mov     rcx, r10; bstrString
0x18001e8c6  call    cs:__imp_SysFreeString
0x18001e8cc  test    rdi, rdi
0x18001e8cf  jz      short loc_18001E8F5
0x18001e8d1  mov     rdx, [rbx]; unsigned __int16 *
0x18001e8d4  test    rdx, rdx
0x18001e8d7  jz      short loc_18001E8F2
0x18001e8d9  mov     r9, rdi; unsigned int *
0x18001e8dc  mov     r8d, 1; int
0x18001e8e2  mov     rcx, r15; this
0x18001e8e5  call    ?GetRobotsTxtIndex@CWebCrawler@@IEAAJPEBGHPEAK@Z; CWebCrawler::GetRobotsTxtIndex(ushort const *,int,ulong *)
0x18001e8ea  and     dword ptr [rdi], 0FFFh
0x18001e8f0  jmp     short loc_18001E8F5
0x18001e8f2  mov     [rdi], r13d
0x18001e8f5  mov     eax, r14d
0x18001e8f8  jmp     short loc_18001E8FF
0x18001e8fa  mov     eax, 80004005h
0x18001e8ff  mov     rbx, [rsp+30h+arg_0]
0x18001e904  mov     rsi, [rsp+30h+arg_18]
0x18001e909  add     rsp, 30h
0x18001e90d  pop     r15
0x18001e90f  pop     r14
0x18001e911  pop     r13
0x18001e913  pop     rdi
0x18001e914  pop     rbp
0x18001e915  retn
```
