# CXmlContentFilter::Load(wchar_t const *,ulong)

- ea: `0x180009070`
- end: `0x180009236`
- name: `?Load@CXmlContentFilter@@UEAAJPEB_WK@Z`
- size: `454`
- prototype: `__int64 __fastcall(CXmlContentFilter *this, WCHAR *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callees

- `0x180002538`
- `0x18000596c`
- `0x180005f70`
- `0x180008a10`
- `0x180009070`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009098`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000908d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000908d`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1800090f6`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1800090f6`

## string_xrefs

- `0x1800090ad`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\xmlcontentfilter.cpp"`
- `0x1800091f6`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\xmlcontentfilter.cpp"`
- `0x1800090a1`: `[XmlFilter XML Content Filter] CXmlContentFilter::Load(file): File may not exist. GetLastError(): %d`
- `0x1800091ea`: `[XmlFilter XML Content Filter] IPersistFile::Load(file): Deferred loading %s`

## pseudocode

```c
__int64 __fastcall CXmlContentFilter::Load(CXmlContentFilter *this, WCHAR *a2)
{
  HRESULT v4; // edi
  DWORD FileAttributesW; // eax
  DWORD LastError; // eax
  IStream *v7; // rcx
  _QWORD *v8; // rbx
  IStream *v9; // r15
  unsigned __int64 v10; // rdx
  _QWORD *v11; // rcx
  __int64 result; // rax
  void *retaddr; // [rsp+78h] [rbp+0h]
  IStream *ppstm; // [rsp+98h] [rbp+20h] BYREF

  v4 = 0;
  FileAttributesW = GetFileAttributesW(a2);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\xmlcontentfilter.cpp\"",
      (const wchar_t *)0xD6,
      (unsigned int)L"[XmlFilter XML Content Filter] CXmlContentFilter::Load(file): File may not exist. GetLastError(): %d",
      (const wchar_t *)LastError);
    v4 = -2147215613;
  }
  try
  {
    v7 = 0;
    ppstm = 0;
    if ( v4 >= 0 )
    {
      ppstm = 0;
      v4 = SHCreateStreamOnFileEx(a2, 0, 0, 0, 0, &ppstm);
      if ( v4 >= 0 )
      {
        v8 = operator new(0x50u, (const struct std::nothrow_t *)std::nothrow);
        if ( v8 )
        {
          v9 = ppstm;
          *v8 = &AXmlDocument::`vftable';
          v8[1] = 16;
          v8[2] = 0;
          v8[8] = v8 + 3;
          *((_WORD *)v8 + 12) = 0;
          v10 = -1;
          do
            ++v10;
          while ( a2[v10] );
          TVarString<16>::Cpy(v8 + 1, v10, a2);
          *v8 = &CXmlStreamDocument::`vftable';
          v8[9] = v9;
          if ( v9 )
            ((void (__fastcall *)(IStream *))v9->lpVtbl->AddRef)(v9);
        }
        else
        {
          v8 = 0;
        }
        v11 = (_QWORD *)*((_QWORD *)this + 65);
        if ( v11 != v8 )
        {
          if ( *((_BYTE *)this + 528) && v11 )
            (*(void (__fastcall **)(_QWORD *, __int64))(*v11 + 24LL))(v11, 1);
          *((_QWORD *)this + 65) = v8;
        }
        *((_BYTE *)this + 528) = v8 != 0;
        if ( *((_QWORD *)this + 65) )
        {
          *((_BYTE *)this + 512) = 0;
          SearchIndexerTrace::Information(
            (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\xmlcontentfilter.cpp\"",
            (const wchar_t *)0xEF,
            (unsigned int)L"[XmlFilter XML Content Filter] IPersistFile::Load(file): Deferred loading %s",
            a2);
        }
        else
        {
          v4 = -2147024882;
        }
      }
      v7 = ppstm;
    }
    if ( v7 )
      ((void (__fastcall *)(IStream *))v7->lpVtbl->Release)(v7);
    result = (unsigned int)v4;
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      246,
      "onecoreuap\\base\\appmodel\\search\\filters\\xml\\xmlcontentfilter.cpp");
  }
  return result;
}

```

## disassembly

```asm
0x180009070  push    rbx
0x180009072  push    rsi
0x180009073  push    rdi
0x180009074  push    r12
0x180009076  push    r14
0x180009078  push    r15
0x18000907a  sub     rsp, 48h
0x18000907e  mov     r14, rdx
0x180009081  mov     rsi, rcx
0x180009084  xor     r12d, r12d
0x180009087  mov     edi, r12d
0x18000908a  mov     rcx, rdx; lpFileName
0x18000908d  call    cs:__imp_GetFileAttributesW
0x180009093  cmp     eax, 0FFFFFFFFh
0x180009096  jnz     short loc_1800090BE
0x180009098  call    cs:__imp_GetLastError
0x18000909e  mov     r9d, eax; wchar_t *
0x1800090a1  lea     r8, aXmlfilterXmlCo_5; "[XmlFilter XML Content Filter] CXmlCont"...
0x1800090a8  mov     edx, 0D6h; wchar_t *
0x1800090ad  lea     rcx, aOnecoreuapBase_0; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800090b4  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800090b9  mov     edi, 80041703h
0x1800090be  mov     rcx, r12
0x1800090c1  mov     [rsp+78h+arg_18], rcx
0x1800090c9  test    edi, edi
0x1800090cb  js      loc_18000920A
0x1800090d1  mov     [rsp+78h+arg_18], r12
0x1800090d9  lea     rax, [rsp+78h+arg_18]
0x1800090e1  mov     [rsp+78h+ppstm], rax; ppstm
0x1800090e6  mov     [rsp+78h+pstmTemplate], r12; pstmTemplate
0x1800090eb  xor     r9d, r9d; fCreate
0x1800090ee  xor     r8d, r8d; dwAttributes
0x1800090f1  xor     edx, edx; grfMode
0x1800090f3  mov     rcx, r14; pszFile
0x1800090f6  call    cs:__imp_SHCreateStreamOnFileEx
0x1800090fc  mov     edi, eax
0x1800090fe  test    eax, eax
0x180009100  js      loc_180009202
0x180009106  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000910d  mov     ecx, 50h ; 'P'; unsigned __int64
0x180009112  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009117  mov     rbx, rax
0x18000911a  mov     [rsp+78h+var_48], rax
0x18000911f  test    rax, rax
0x180009122  jz      short loc_18000918D
0x180009124  mov     r15, [rsp+78h+arg_18]
0x18000912c  lea     rax, ??_7AXmlDocument@@6B@; const AXmlDocument::`vftable'
0x180009133  mov     [rbx], rax
0x180009136  mov     qword ptr [rbx+8], 10h
0x18000913e  mov     [rbx+10h], r12
0x180009142  lea     rcx, [rbx+18h]
0x180009146  mov     [rbx+40h], rcx
0x18000914a  mov     [rcx], r12w
0x18000914e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180009152  inc     rdx
0x180009155  cmp     [r14+rdx*2], r12w
0x18000915a  jnz     short loc_180009152
0x18000915c  mov     r8, r14
0x18000915f  lea     rcx, [rbx+8]
0x180009163  call    ?Cpy@?$TVarString@$0BA@@@QEAAAEAV1@_KPEB_W@Z; TVarString<16>::Cpy(unsigned __int64,wchar_t const *)
0x180009168  lea     rax, ??_7CXmlStreamDocument@@6B@; const CXmlStreamDocument::`vftable'
0x18000916f  mov     [rbx], rax
0x180009172  mov     [rbx+48h], r15
0x180009176  test    r15, r15
0x180009179  jz      short loc_18000918B
0x18000917b  mov     rax, [r15]
0x18000917e  mov     rcx, r15
0x180009181  mov     rax, [rax+8]
0x180009185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000918a  nop
0x18000918b  jmp     short loc_180009190
0x18000918d  mov     rbx, r12
0x180009190  test    rbx, rbx
0x180009193  setnz   r15b
0x180009197  mov     rcx, [rsi+208h]
0x18000919e  cmp     rcx, rbx
0x1800091a1  jz      short loc_1800091C9
0x1800091a3  cmp     [rsi+210h], r12b
0x1800091aa  jz      short loc_1800091C2
0x1800091ac  test    rcx, rcx
0x1800091af  jz      short loc_1800091C2
0x1800091b1  mov     rax, [rcx]
0x1800091b4  mov     edx, 1
0x1800091b9  mov     rax, [rax+18h]
0x1800091bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091c2  mov     [rsi+208h], rbx
0x1800091c9  mov     [rsi+210h], r15b
0x1800091d0  cmp     [rsi+208h], r12
0x1800091d7  jnz     short loc_1800091E0
0x1800091d9  mov     edi, 8007000Eh
0x1800091de  jmp     short loc_180009202
0x1800091e0  mov     [rsi+200h], r12b
0x1800091e7  mov     r9, r14; wchar_t *
0x1800091ea  lea     r8, aXmlfilterXmlCo_4; "[XmlFilter XML Content Filter] IPersist"...
0x1800091f1  mov     edx, 0EFh; wchar_t *
0x1800091f6  lea     rcx, aOnecoreuapBase_0; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800091fd  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x180009202  mov     rcx, [rsp+78h+arg_18]
0x18000920a  test    rcx, rcx
0x18000920d  jz      short loc_18000921C
0x18000920f  mov     rax, [rcx]
0x180009212  mov     rax, [rax+10h]
0x180009216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000921b  nop
0x18000921c  mov     eax, edi
0x18000921e  jmp     short loc_180009227
0x180009220  mov     eax, dword ptr [rsp+78h+arg_18]
0x180009227  add     rsp, 48h
0x18000922b  pop     r15
0x18000922d  pop     r14
0x18000922f  pop     r12
0x180009231  pop     rdi
0x180009232  pop     rsi
0x180009233  pop     rbx
0x180009234  retn
```
