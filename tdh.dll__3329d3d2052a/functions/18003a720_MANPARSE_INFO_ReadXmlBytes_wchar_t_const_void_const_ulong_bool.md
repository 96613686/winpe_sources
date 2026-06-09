# MANPARSE_INFO::ReadXmlBytes(wchar_t const *,void const *,ulong,bool)

- ea: `0x18003a720`
- end: `0x18003a94e`
- name: `?ReadXmlBytes@MANPARSE_INFO@@QEAAJPEB_WPEBXK_N@Z`
- size: `558`
- prototype: `__int64 __fastcall(void (**this)(const char *, int, const wchar_t *, unsigned int, unsigned int), const wchar_t *, const void *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180025800`
- `0x180025d2c`

## callees

- `0x180001084`
- `0x180018eb8`
- `0x18002c2fc`
- `0x18002cbec`
- `0x1800325cc`
- `0x180033924`
- `0x180039184`
- `0x18003a720`

## pseudocode

```c
__int64 __fastcall MANPARSE_INFO::ReadXmlBytes(
        void (**this)(const char *, int, const wchar_t *, unsigned int, unsigned int),
        const wchar_t *a2,
        const void *a3,
        unsigned int a4,
        unsigned int a5)
{
  unsigned int v8; // ebx
  const ManparseException *v10; // rbx
  _QWORD *v11; // rcx
  const ManparseException *v12; // [rsp+30h] [rbp-148h] BYREF
  __int64 **v13; // [rsp+40h] [rbp-138h] BYREF
  MESSAGE_ENTRY *v14; // [rsp+48h] [rbp-130h]
  __int128 v15; // [rsp+50h] [rbp-128h]
  _QWORD v16[2]; // [rsp+60h] [rbp-118h] BYREF
  char v17; // [rsp+70h] [rbp-108h]
  char *v18; // [rsp+78h] [rbp-100h]
  char *v19; // [rsp+80h] [rbp-F8h]
  char *v20; // [rsp+88h] [rbp-F0h]
  _QWORD *v21; // [rsp+90h] [rbp-E8h]
  _QWORD *v22; // [rsp+98h] [rbp-E0h]
  _QWORD *v23; // [rsp+A0h] [rbp-D8h]
  _QWORD *v24; // [rsp+A8h] [rbp-D0h]
  _QWORD *v25; // [rsp+B0h] [rbp-C8h]
  _QWORD *v26; // [rsp+B8h] [rbp-C0h]
  void (*v27)(const char *, int, const wchar_t *, unsigned int, unsigned int); // [rsp+E8h] [rbp-90h]
  _QWORD *v28; // [rsp+F0h] [rbp-88h]
  _QWORD *v29; // [rsp+F8h] [rbp-80h]
  _BYTE v30[68]; // [rsp+100h] [rbp-78h] BYREF
  int v31; // [rsp+144h] [rbp-34h]

  try
  {
    EventManParser::EventManParser((EventManParser *)v30, *this, (bool)a3);
    v13 = (__int64 **)(this + 7);
    v14 = 0;
    v15 = 0;
    v16[0] = *this;
    v16[1] = L"MEMORY";
    v17 = *((_BYTE *)this + 16);
    v18 = (char *)(this + 5);
    v19 = (char *)(this + 7);
    v20 = (char *)(this + 3);
    v21 = v16;
    v22 = v16;
    v23 = v16;
    v24 = v16;
    v25 = v16;
    v26 = v16;
    v27 = this[1];
    v28 = v16;
    v29 = v16;
    a5 = 0;
    XmlReader::OpenInputMemory((XmlReader *)v30, a3, a4, (int *)&a5);
    EventManParser::DocumentRoot<0,ETW_PROVIDER_LIST>((XmlReader *)v30);
    v8 = v31;
    if ( v31 >= 0 )
    {
      ETW_PROVIDER_LIST::Process(&v13, (const struct WinMetaData *)&off_18004E0C0);
      if ( v14 )
      {
        std::_Destroy_range<std::allocator<MESSAGE_ENTRY>>(v14);
        std::_Deallocate<16>(v14, 8 * ((__int64)(*((_QWORD *)&v15 + 1) - (_QWORD)v14) >> 3));
        v14 = 0;
        v15 = 0;
      }
      XmlReader::~XmlReader((XmlReader *)v30);
    }
    else
    {
      XmlReader::~XmlReader((XmlReader *)v30);
    }
  }
  catch ( const ManparseException *v12 )
  {
    v10 = v12;
    if ( *this )
    {
      v11 = (_QWORD *)((char *)v12 + 24);
      if ( *((_QWORD *)v12 + 6) > 0xFu )
        v11 = (_QWORD *)*v11;
      ((void (__fastcall *)(_QWORD *, _QWORD, const wchar_t *, _QWORD, _DWORD))*this)(
        v11,
        *((unsigned int *)v12 + 14),
        L"MEMORY",
        *((unsigned int *)v12 + 15),
        *((_DWORD *)v12 + 16));
    }
    return *((unsigned int *)v10 + 14);
  }
  catch ( std::bad_alloc )
  {
    return (unsigned int)-2147024882;
  }
  catch ( ... )
  {
    return (unsigned int)-2147467259;
  }
  return v8;
}

```

## disassembly

```asm
0x18003a720  mov     rax, rsp
0x18003a723  mov     [rax+8], rcx
0x18003a727  push    rbx
0x18003a728  push    rsi
0x18003a729  push    rdi
0x18003a72a  push    r15
0x18003a72c  sub     rsp, 158h
0x18003a733  mov     edi, r9d
0x18003a736  mov     rsi, r8
0x18003a739  mov     rbx, rcx
0x18003a73c  mov     rdx, [rcx]; void (*)(const char *, int, const wchar_t *, unsigned int, unsigned int)
0x18003a73f  lea     rcx, [rax-78h]; this
0x18003a743  call    ??0EventManParser@@QEAA@P6AXPEBDJPEB_WII@Z_N@Z; EventManParser::EventManParser(void (*)(char const *,long,wchar_t const *,uint,uint),bool)
0x18003a748  nop
0x18003a749  lea     rcx, [rbx+38h]
0x18003a74d  mov     [rsp+178h+var_138], rcx
0x18003a752  mov     [rsp+178h+var_130], 0
0x18003a75b  xorps   xmm0, xmm0
0x18003a75e  movdqa  [rsp+178h+var_128], xmm0
0x18003a764  mov     rax, [rbx]
0x18003a767  mov     [rsp+178h+var_118], rax
0x18003a76c  lea     r15, aMemory; "MEMORY"
0x18003a773  mov     [rsp+178h+var_110], r15
0x18003a778  mov     al, [rbx+10h]
0x18003a77b  mov     [rsp+178h+var_108], al
0x18003a77f  lea     rax, [rbx+28h]
0x18003a783  mov     [rsp+178h+var_100], rax
0x18003a788  mov     [rsp+178h+var_F8], rcx
0x18003a790  lea     rax, [rbx+18h]
0x18003a794  mov     [rsp+178h+var_F0], rax
0x18003a79c  lea     rax, [rsp+178h+var_118]
0x18003a7a1  mov     [rsp+178h+var_E8], rax
0x18003a7a9  lea     rax, [rsp+178h+var_118]
0x18003a7ae  mov     [rsp+178h+var_E0], rax
0x18003a7b6  lea     rax, [rsp+178h+var_118]
0x18003a7bb  mov     [rsp+178h+var_D8], rax
0x18003a7c3  lea     rax, [rsp+178h+var_118]
0x18003a7c8  mov     [rsp+178h+var_D0], rax
0x18003a7d0  lea     rax, [rsp+178h+var_118]
0x18003a7d5  mov     [rsp+178h+var_C8], rax
0x18003a7dd  lea     rax, [rsp+178h+var_118]
0x18003a7e2  mov     [rsp+178h+var_C0], rax
0x18003a7ea  mov     rax, [rbx+8]
0x18003a7ee  mov     [rsp+178h+var_90], rax
0x18003a7f6  lea     rax, [rsp+178h+var_118]
0x18003a7fb  mov     [rsp+178h+var_88], rax
0x18003a803  lea     rax, [rsp+178h+var_118]
0x18003a808  mov     [rsp+178h+var_80], rax
0x18003a810  mov     [rsp+178h+arg_20], 0
0x18003a81b  mov     r8d, edi; unsigned __int64
0x18003a81e  lea     r9, [rsp+178h+arg_20]; int *
0x18003a826  mov     rdx, rsi; void *
0x18003a829  lea     rcx, [rsp+178h+var_78]; this
0x18003a831  call    ?OpenInputMemory@XmlReader@@QEAAXPEBX_KPEAJ@Z; XmlReader::OpenInputMemory(void const *,unsigned __int64,long *)
0x18003a836  mov     r9d, [rsp+178h+arg_20]
0x18003a83e  mov     r8, r15
0x18003a841  lea     rdx, [rsp+178h+var_138]
0x18003a846  lea     rcx, [rsp+178h+var_78]; this
0x18003a84e  call    ??$DocumentRoot@$0A@VETW_PROVIDER_LIST@@@EventManParser@@AEAAXAEAVETW_PROVIDER_LIST@@PEB_WJ@Z; EventManParser::DocumentRoot<0,ETW_PROVIDER_LIST>(ETW_PROVIDER_LIST &,wchar_t const *,long)
0x18003a853  mov     ebx, [rsp+178h+var_34]
0x18003a85a  test    ebx, ebx
0x18003a85c  jns     short loc_18003A8C0
0x18003a85e  mov     rcx, [rsp+178h+var_130]; this
0x18003a863  test    rcx, rcx
0x18003a866  jz      short loc_18003A8B0
0x18003a868  mov     rdx, qword ptr [rsp+178h+var_128]
0x18003a86d  call    ??$_Destroy_range@V?$allocator@UMESSAGE_ENTRY@@@std@@@std@@YAXPEAUMESSAGE_ENTRY@@QEAU1@AEAV?$allocator@UMESSAGE_ENTRY@@@0@@Z; std::_Destroy_range<std::allocator<MESSAGE_ENTRY>>(MESSAGE_ENTRY *,MESSAGE_ENTRY * const,std::allocator<MESSAGE_ENTRY> &)
0x18003a872  mov     rcx, [rsp+178h+var_130]
0x18003a877  mov     rax, qword ptr [rsp+178h+var_128+8]
0x18003a87c  sub     rax, rcx
0x18003a87f  sar     rax, 3
0x18003a883  mov     rdx, 8E38E38E38E38E39h
0x18003a88d  imul    rax, rdx
0x18003a891  lea     rdx, [rax+rax*8]
0x18003a895  shl     rdx, 3
0x18003a899  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003a89e  mov     [rsp+178h+var_130], 0
0x18003a8a7  xorps   xmm0, xmm0
0x18003a8aa  movdqa  [rsp+178h+var_128], xmm0
0x18003a8b0  lea     rcx, [rsp+178h+var_78]; this
0x18003a8b8  call    ??1XmlReader@@QEAA@XZ; XmlReader::~XmlReader(void)
0x18003a8bd  nop
0x18003a8be  jmp     short loc_18003A93F
0x18003a8c0  lea     rdx, off_18004E0C0; struct WinMetaData *
0x18003a8c7  lea     rcx, [rsp+178h+var_138]; this
0x18003a8cc  call    ?Process@ETW_PROVIDER_LIST@@QEAAXAEBVWinMetaData@@@Z; ETW_PROVIDER_LIST::Process(WinMetaData const &)
0x18003a8d1  nop
0x18003a8d2  mov     rcx, [rsp+178h+var_130]; this
0x18003a8d7  test    rcx, rcx
0x18003a8da  jz      short loc_18003A924
0x18003a8dc  mov     rdx, qword ptr [rsp+178h+var_128]
0x18003a8e1  call    ??$_Destroy_range@V?$allocator@UMESSAGE_ENTRY@@@std@@@std@@YAXPEAUMESSAGE_ENTRY@@QEAU1@AEAV?$allocator@UMESSAGE_ENTRY@@@0@@Z; std::_Destroy_range<std::allocator<MESSAGE_ENTRY>>(MESSAGE_ENTRY *,MESSAGE_ENTRY * const,std::allocator<MESSAGE_ENTRY> &)
0x18003a8e6  mov     rcx, [rsp+178h+var_130]
0x18003a8eb  mov     rax, qword ptr [rsp+178h+var_128+8]
0x18003a8f0  sub     rax, rcx
0x18003a8f3  sar     rax, 3
0x18003a8f7  mov     rdx, 8E38E38E38E38E39h
0x18003a901  imul    rax, rdx
0x18003a905  lea     rdx, [rax+rax*8]
0x18003a909  shl     rdx, 3
0x18003a90d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003a912  mov     [rsp+178h+var_130], 0
0x18003a91b  xorps   xmm0, xmm0
0x18003a91e  movdqa  [rsp+178h+var_128], xmm0
0x18003a924  lea     rcx, [rsp+178h+var_78]; this
0x18003a92c  call    ??1XmlReader@@QEAA@XZ; XmlReader::~XmlReader(void)
0x18003a931  nop
0x18003a932  jmp     short loc_18003A93F
0x18003a934  jmp     short loc_18003A938
0x18003a936  jmp     short $+2
0x18003a938  mov     ebx, [rsp+178h+arg_20]
0x18003a93f  mov     eax, ebx
0x18003a941  add     rsp, 158h
0x18003a948  pop     r15
0x18003a94a  pop     rdi
0x18003a94b  pop     rsi
0x18003a94c  pop     rbx
0x18003a94d  retn
```
