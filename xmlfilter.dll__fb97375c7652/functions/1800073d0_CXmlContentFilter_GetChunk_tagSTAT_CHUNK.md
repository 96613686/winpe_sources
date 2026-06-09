# CXmlContentFilter::GetChunk(tagSTAT_CHUNK *)

- ea: `0x1800073d0`
- end: `0x180007463`
- name: `?GetChunk@CXmlContentFilter@@UEAAJPEAUtagSTAT_CHUNK@@@Z`
- size: `147`
- prototype: `__int64 __fastcall(CXmlContentFilter *__hidden this, struct tagSTAT_CHUNK *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180005f70`
- `0x1800073d0`
- `0x18000ef7c`
- `0x180017010`

## string_xrefs

- `0x18000743f`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\xmlcontentfilter.cpp"`
- `0x180007433`: `[XmlFilter XML Content Filter] CXmlContentFilter::GetChunk(): m_chFilterImpParserSink.GetChunk returned error %#x on document %s`

## pseudocode

```c
__int64 __fastcall CXmlContentFilter::GetChunk(CXmlContentFilter *this, struct tagSTAT_CHUNK *a2)
{
  __int64 result; // rax
  CFilterImpContentHandler *v4; // rcx
  unsigned int Chunk; // ebx
  __int64 v6; // rax
  void *retaddr; // [rsp+38h] [rbp+0h]

  if ( !*((_BYTE *)this + 520) )
    return 2147751696LL;
  if ( !a2 )
    return 2147942487LL;
  v4 = (CXmlContentFilter *)((char *)this + 88);
  try
  {
    Chunk = CFilterImpContentHandler::GetChunk(v4, a2);
    if ( (int)(Chunk + 0x80000000) < 0 || Chunk == -2147215616 )
    {
      result = Chunk;
    }
    else
    {
      v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 66) + 16LL))(*((_QWORD *)this + 66));
      SearchIndexerTrace::Error(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\xmlcontentfilter.cpp\"",
        (const wchar_t *)0x1BB,
        (unsigned int)L"[XmlFilter XML Content Filter] CXmlContentFilter::GetChunk(): m_chFilterImpParserSink.GetChunk ret"
                       "urned error %#x on document %s",
        (const wchar_t *)Chunk,
        v6);
      result = Chunk;
    }
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      452,
      "onecoreuap\\base\\appmodel\\search\\filters\\xml\\xmlcontentfilter.cpp");
  }
  return result;
}

```

## disassembly

```asm
0x1800073d0  mov     [rsp+arg_8], rbx
0x1800073d5  push    rdi
0x1800073d6  sub     rsp, 30h
0x1800073da  mov     rdi, rcx
0x1800073dd  cmp     byte ptr [rcx+208h], 0
0x1800073e4  jnz     short loc_1800073ED
0x1800073e6  mov     eax, 80041710h
0x1800073eb  jmp     short loc_180007457
0x1800073ed  test    rdx, rdx
0x1800073f0  jnz     short loc_1800073F9
0x1800073f2  mov     eax, 80070057h
0x1800073f7  jmp     short loc_180007457
0x1800073f9  add     rcx, 58h ; 'X'; this
0x1800073fd  call    ?GetChunk@CFilterImpContentHandler@@QEAAJPEAUtagSTAT_CHUNK@@@Z; CFilterImpContentHandler::GetChunk(tagSTAT_CHUNK *)
0x180007402  mov     ebx, eax
0x180007404  mov     eax, 80000000h
0x180007409  lea     ecx, [rbx+rax]
0x18000740c  test    eax, ecx
0x18000740e  jnz     short loc_18000744F
0x180007410  cmp     ebx, 80041700h
0x180007416  jz      short loc_18000744F
0x180007418  mov     rcx, [rdi+210h]
0x18000741f  mov     rdx, [rcx]
0x180007422  mov     rax, [rdx+10h]
0x180007426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000742b  mov     [rsp+38h+var_18], rax
0x180007430  mov     r9d, ebx; wchar_t *
0x180007433  lea     r8, aXmlfilterXmlCo_3; "[XmlFilter XML Content Filter] CXmlCont"...
0x18000743a  mov     edx, 1BBh; wchar_t *
0x18000743f  lea     rcx, aOnecoreuapBase_0; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180007446  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18000744b  mov     eax, ebx
0x18000744d  jmp     short loc_180007457
0x18000744f  mov     eax, ebx
0x180007451  jmp     short loc_180007457
0x180007453  mov     eax, [rsp+38h+arg_0]
0x180007457  mov     rbx, [rsp+38h+arg_8]
0x18000745c  add     rsp, 30h
0x180007460  pop     rdi
0x180007461  retn
```
