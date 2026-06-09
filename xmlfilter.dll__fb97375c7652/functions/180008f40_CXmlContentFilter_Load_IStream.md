# CXmlContentFilter::Load(IStream *)

- ea: `0x180008f40`
- end: `0x18000905d`
- name: `?Load@CXmlContentFilter@@UEAAJPEAUIStream@@@Z`
- size: `285`
- prototype: `__int64 __fastcall(CXmlContentFilter *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180002538`
- `0x18000596c`
- `0x180008a10`
- `0x180008f40`
- `0x180017010`

## string_xrefs

- `0x180009038`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\xmlcontentfilter.cpp"`
- `0x18000902c`: `[XmlFilter XML Content Filter] IPersistFile::Load(stream): Deferred loading stream`

## pseudocode

```c
__int64 __fastcall CXmlContentFilter::Load(CXmlContentFilter *this, struct IStream *a2)
{
  _QWORD *v4; // rax
  const wchar_t *v5; // r9
  _QWORD *v6; // rbx
  _QWORD *v7; // rcx
  unsigned int v8; // ebx
  __int64 result; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  v4 = operator new(0x50u, (const struct std::nothrow_t *)std::nothrow);
  try
  {
    v6 = v4;
    if ( v4 )
    {
      *v4 = &AXmlDocument::`vftable';
      v4[1] = 16;
      v4[2] = 0;
      v4[8] = v4 + 3;
      *((_WORD *)v4 + 12) = 0;
      TVarString<16>::Cpy(v4 + 1, 15, L"nameless stream");
      *v6 = &CXmlStreamDocument::`vftable';
      v6[9] = a2;
      if ( a2 )
        ((void (__fastcall *)(struct IStream *))a2->lpVtbl->AddRef)(a2);
    }
    else
    {
      v6 = 0;
    }
    v7 = (_QWORD *)*((_QWORD *)this + 64);
    if ( v7 != v6 )
    {
      if ( *((_BYTE *)this + 520) && v7 )
        (*(void (__fastcall **)(_QWORD *, __int64))(*v7 + 24LL))(v7, 1);
      *((_QWORD *)this + 64) = v6;
    }
    *((_BYTE *)this + 520) = v6 != 0;
    if ( *((_QWORD *)this + 64) )
    {
      v8 = 0;
      *((_BYTE *)this + 504) = 0;
      SearchIndexerTrace::Information(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\xmlcontentfilter.cpp\"",
        (const wchar_t *)0x11D,
        (unsigned int)L"[XmlFilter XML Content Filter] IPersistFile::Load(stream): Deferred loading stream",
        v5);
    }
    else
    {
      v8 = -2147024882;
    }
    result = v8;
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      292,
      "onecoreuap\\base\\appmodel\\search\\filters\\xml\\xmlcontentfilter.cpp");
  }
  return result;
}

```

## disassembly

```asm
0x180008f40  mov     [rsp+arg_0], rbx
0x180008f45  mov     [rsp+arg_8], rsi
0x180008f4a  push    rdi
0x180008f4b  sub     rsp, 20h
0x180008f4f  mov     rsi, rdx
0x180008f52  mov     rdi, rcx
0x180008f55  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008f5c  mov     ecx, 50h ; 'P'; unsigned __int64
0x180008f61  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008f66  mov     rbx, rax
0x180008f69  mov     [rsp+28h+arg_10], rax
0x180008f6e  test    rax, rax
0x180008f71  jz      short loc_180008FD1
0x180008f73  lea     rax, ??_7AXmlDocument@@6B@; const AXmlDocument::`vftable'
0x180008f7a  mov     [rbx], rax
0x180008f7d  lea     rcx, [rbx+8]
0x180008f81  mov     qword ptr [rcx], 10h
0x180008f88  mov     qword ptr [rcx+8], 0
0x180008f90  lea     rdx, [rcx+10h]
0x180008f94  mov     [rcx+38h], rdx
0x180008f98  xor     eax, eax
0x180008f9a  mov     [rdx], ax
0x180008f9d  lea     r8, aNamelessStream; "nameless stream"
0x180008fa4  lea     edx, [rax+0Fh]
0x180008fa7  call    ?Cpy@?$TVarString@$0BA@@@QEAAAEAV1@_KPEB_W@Z; TVarString<16>::Cpy(unsigned __int64,wchar_t const *)
0x180008fac  lea     rax, ??_7CXmlStreamDocument@@6B@; const CXmlStreamDocument::`vftable'
0x180008fb3  mov     [rbx], rax
0x180008fb6  mov     [rbx+48h], rsi
0x180008fba  test    rsi, rsi
0x180008fbd  jz      short loc_180008FCF
0x180008fbf  mov     rax, [rsi]
0x180008fc2  mov     rcx, rsi
0x180008fc5  mov     rax, [rax+8]
0x180008fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fce  nop
0x180008fcf  jmp     short loc_180008FD3
0x180008fd1  xor     ebx, ebx
0x180008fd3  test    rbx, rbx
0x180008fd6  setnz   sil
0x180008fda  mov     rcx, [rdi+200h]
0x180008fe1  cmp     rcx, rbx
0x180008fe4  jz      short loc_18000900C
0x180008fe6  cmp     byte ptr [rdi+208h], 0
0x180008fed  jz      short loc_180009005
0x180008fef  test    rcx, rcx
0x180008ff2  jz      short loc_180009005
0x180008ff4  mov     rax, [rcx]
0x180008ff7  mov     edx, 1
0x180008ffc  mov     rax, [rax+18h]
0x180009000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009005  mov     [rdi+200h], rbx
0x18000900c  mov     [rdi+208h], sil
0x180009013  cmp     qword ptr [rdi+200h], 0
0x18000901b  jnz     short loc_180009024
0x18000901d  mov     ebx, 8007000Eh
0x180009022  jmp     short loc_180009044
0x180009024  xor     ebx, ebx
0x180009026  mov     [rdi+1F8h], bl
0x18000902c  lea     r8, aXmlfilterXmlCo; "[XmlFilter XML Content Filter] IPersist"...
0x180009033  mov     edx, 11Dh; wchar_t *
0x180009038  lea     rcx, aOnecoreuapBase_0; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000903f  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x180009044  mov     eax, ebx
0x180009046  jmp     short loc_18000904C
0x180009048  mov     eax, dword ptr [rsp+28h+arg_10]
0x18000904c  mov     rbx, [rsp+28h+arg_0]
0x180009051  mov     rsi, [rsp+28h+arg_8]
0x180009056  add     rsp, 20h
0x18000905a  pop     rdi
0x18000905b  retn
```
