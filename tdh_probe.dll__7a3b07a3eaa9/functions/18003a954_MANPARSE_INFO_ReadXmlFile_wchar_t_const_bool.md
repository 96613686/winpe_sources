# MANPARSE_INFO::ReadXmlFile(wchar_t const *,bool)

- ea: `0x18003a954`
- end: `0x18003ab54`
- name: `?ReadXmlFile@MANPARSE_INFO@@QEAAJPEB_W_N@Z`
- size: `512`
- prototype: `__int64 __fastcall(void (**this)(const char *, int, const wchar_t *, unsigned int, unsigned int), const wchar_t *, bool)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180025800`
- `0x180025d2c`

## callees

- `0x180001084`
- `0x180018eb8`
- `0x18002cbec`
- `0x1800325cc`
- `0x180033924`
- `0x18003a680`
- `0x18003a954`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MANPARSE_INFO::ReadXmlFile(
        void (**this)(const char *, int, const wchar_t *, unsigned int, unsigned int),
        const wchar_t *a2,
        bool a3)
{
  const ManparseException *v6; // rbx
  _QWORD *v7; // rcx
  const ManparseException *v8; // [rsp+30h] [rbp-128h] BYREF
  char *v9; // [rsp+40h] [rbp-118h] BYREF
  MESSAGE_ENTRY *v10; // [rsp+48h] [rbp-110h]
  __int128 v11; // [rsp+50h] [rbp-108h]
  _QWORD v12[2]; // [rsp+60h] [rbp-F8h] BYREF
  char v13; // [rsp+70h] [rbp-E8h]
  char *v14; // [rsp+78h] [rbp-E0h]
  char *v15; // [rsp+80h] [rbp-D8h]
  char *v16; // [rsp+88h] [rbp-D0h]
  _QWORD *v17; // [rsp+90h] [rbp-C8h]
  _QWORD *v18; // [rsp+98h] [rbp-C0h]
  _QWORD *v19; // [rsp+A0h] [rbp-B8h]
  _QWORD *v20; // [rsp+A8h] [rbp-B0h]
  _QWORD *v21; // [rsp+B0h] [rbp-A8h]
  _QWORD *v22; // [rsp+B8h] [rbp-A0h]
  void (*v23)(const char *, int, const wchar_t *, unsigned int, unsigned int); // [rsp+E8h] [rbp-70h]
  _QWORD *v24; // [rsp+F0h] [rbp-68h]
  _QWORD *v25; // [rsp+F8h] [rbp-60h]
  _BYTE v26[88]; // [rsp+100h] [rbp-58h] BYREF
  int Manifest; // [rsp+170h] [rbp+18h]

  try
  {
    EventManParser::EventManParser((EventManParser *)v26, *this, a3);
    v9 = (char *)(this + 7);
    v10 = 0;
    v11 = 0;
    v12[0] = *this;
    v12[1] = a2;
    v13 = *((_BYTE *)this + 16);
    v14 = (char *)(this + 5);
    v15 = (char *)(this + 7);
    v16 = (char *)(this + 3);
    v17 = v12;
    v18 = v12;
    v19 = v12;
    v20 = v12;
    v21 = v12;
    v22 = v12;
    v23 = this[1];
    v24 = v12;
    v25 = v12;
    Manifest = EventManParser::ReadManifest((EventManParser *)v26, (struct ETW_PROVIDER_LIST *)&v9, a2);
    if ( Manifest >= 0 )
    {
      ETW_PROVIDER_LIST::Process((ETW_PROVIDER_LIST *)&v9, (const struct WinMetaData *)&off_18004E0C0);
      if ( v10 )
      {
        std::_Destroy_range<std::allocator<MESSAGE_ENTRY>>(v10);
        std::_Deallocate<16>(v10, 8 * ((__int64)(*((_QWORD *)&v11 + 1) - (_QWORD)v10) >> 3));
        v10 = 0;
        v11 = 0;
      }
    }
    else if ( v10 )
    {
      std::_Destroy_range<std::allocator<MESSAGE_ENTRY>>(v10);
      std::_Deallocate<16>(v10, 8 * ((__int64)(*((_QWORD *)&v11 + 1) - (_QWORD)v10) >> 3));
      v10 = 0;
      v11 = 0;
    }
    XmlReader::~XmlReader((XmlReader *)v26);
  }
  catch ( const ManparseException *v8 )
  {
    v6 = v8;
    if ( *this )
    {
      v7 = (_QWORD *)((char *)v8 + 24);
      if ( *((_QWORD *)v8 + 6) > 0xFu )
        v7 = (_QWORD *)*v7;
      ((void (__fastcall *)(_QWORD *, _QWORD, const wchar_t *, _QWORD, _DWORD))*this)(
        v7,
        *((unsigned int *)v8 + 14),
        a2,
        *((unsigned int *)v8 + 15),
        *((_DWORD *)v8 + 16));
    }
    return (unsigned int)*((_DWORD *)v6 + 14);
  }
  catch ( std::bad_alloc )
  {
    return (unsigned int)-2147024882;
  }
  catch ( ... )
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)Manifest;
}

```

## disassembly

```asm
0x18003a954  mov     rax, rsp
0x18003a957  mov     [rax+20h], rbx
0x18003a95b  mov     [rax+18h], r8b
0x18003a95f  mov     [rax+10h], rdx
0x18003a963  mov     [rax+8], rcx
0x18003a967  push    rdi
0x18003a968  sub     rsp, 150h
0x18003a96f  mov     rdi, rdx
0x18003a972  mov     rbx, rcx
0x18003a975  mov     rdx, [rcx]; void (*)(const char *, int, const wchar_t *, unsigned int, unsigned int)
0x18003a978  lea     rcx, [rax-58h]; this
0x18003a97c  call    ??0EventManParser@@QEAA@P6AXPEBDJPEB_WII@Z_N@Z; EventManParser::EventManParser(void (*)(char const *,long,wchar_t const *,uint,uint),bool)
0x18003a981  nop
0x18003a982  lea     rcx, [rbx+38h]
0x18003a986  mov     [rsp+158h+var_118], rcx
0x18003a98b  mov     [rsp+158h+var_110], 0
0x18003a994  xorps   xmm0, xmm0
0x18003a997  movdqa  [rsp+158h+var_108], xmm0
0x18003a99d  mov     rax, [rbx]
0x18003a9a0  mov     [rsp+158h+var_F8], rax
0x18003a9a5  mov     [rsp+158h+var_F0], rdi
0x18003a9aa  mov     al, [rbx+10h]
0x18003a9ad  mov     [rsp+158h+var_E8], al
0x18003a9b1  lea     rax, [rbx+28h]
0x18003a9b5  mov     [rsp+158h+var_E0], rax
0x18003a9ba  mov     [rsp+158h+var_D8], rcx
0x18003a9c2  lea     rax, [rbx+18h]
0x18003a9c6  mov     [rsp+158h+var_D0], rax
0x18003a9ce  lea     rax, [rsp+158h+var_F8]
0x18003a9d3  mov     [rsp+158h+var_C8], rax
0x18003a9db  lea     rax, [rsp+158h+var_F8]
0x18003a9e0  mov     [rsp+158h+var_C0], rax
0x18003a9e8  lea     rax, [rsp+158h+var_F8]
0x18003a9ed  mov     [rsp+158h+var_B8], rax
0x18003a9f5  lea     rax, [rsp+158h+var_F8]
0x18003a9fa  mov     [rsp+158h+var_B0], rax
0x18003aa02  lea     rax, [rsp+158h+var_F8]
0x18003aa07  mov     [rsp+158h+var_A8], rax
0x18003aa0f  lea     rax, [rsp+158h+var_F8]
0x18003aa14  mov     [rsp+158h+var_A0], rax
0x18003aa1c  mov     rax, [rbx+8]
0x18003aa20  mov     [rsp+158h+var_70], rax
0x18003aa28  lea     rax, [rsp+158h+var_F8]
0x18003aa2d  mov     [rsp+158h+var_68], rax
0x18003aa35  lea     rax, [rsp+158h+var_F8]
0x18003aa3a  mov     [rsp+158h+var_60], rax
0x18003aa42  mov     r8, rdi; wchar_t *
0x18003aa45  lea     rdx, [rsp+158h+var_118]; struct ETW_PROVIDER_LIST *
0x18003aa4a  lea     rcx, [rsp+158h+var_58]; this
0x18003aa52  call    ?ReadManifest@EventManParser@@QEAAJAEAVETW_PROVIDER_LIST@@PEB_W@Z; EventManParser::ReadManifest(ETW_PROVIDER_LIST &,wchar_t const *)
0x18003aa57  mov     [rsp+158h+arg_10], eax
0x18003aa5e  test    eax, eax
0x18003aa60  jns     short loc_18003AAC4
0x18003aa62  mov     rcx, [rsp+158h+var_110]; this
0x18003aa67  test    rcx, rcx
0x18003aa6a  jz      short loc_18003AAB4
0x18003aa6c  mov     rdx, qword ptr [rsp+158h+var_108]
0x18003aa71  call    ??$_Destroy_range@V?$allocator@UMESSAGE_ENTRY@@@std@@@std@@YAXPEAUMESSAGE_ENTRY@@QEAU1@AEAV?$allocator@UMESSAGE_ENTRY@@@0@@Z; std::_Destroy_range<std::allocator<MESSAGE_ENTRY>>(MESSAGE_ENTRY *,MESSAGE_ENTRY * const,std::allocator<MESSAGE_ENTRY> &)
0x18003aa76  mov     rcx, [rsp+158h+var_110]
0x18003aa7b  mov     rax, qword ptr [rsp+158h+var_108+8]
0x18003aa80  sub     rax, rcx
0x18003aa83  sar     rax, 3
0x18003aa87  mov     rdx, 8E38E38E38E38E39h
0x18003aa91  imul    rax, rdx
0x18003aa95  lea     rdx, [rax+rax*8]
0x18003aa99  shl     rdx, 3
0x18003aa9d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003aaa2  mov     [rsp+158h+var_110], 0
0x18003aaab  xorps   xmm0, xmm0
0x18003aaae  movdqa  [rsp+158h+var_108], xmm0
0x18003aab4  lea     rcx, [rsp+158h+var_58]; this
0x18003aabc  call    ??1XmlReader@@QEAA@XZ; XmlReader::~XmlReader(void)
0x18003aac1  nop
0x18003aac2  jmp     short loc_18003AB3C
0x18003aac4  lea     rdx, off_18004E0C0; struct WinMetaData *
0x18003aacb  lea     rcx, [rsp+158h+var_118]; this
0x18003aad0  call    ?Process@ETW_PROVIDER_LIST@@QEAAXAEBVWinMetaData@@@Z; ETW_PROVIDER_LIST::Process(WinMetaData const &)
0x18003aad5  nop
0x18003aad6  mov     rcx, [rsp+158h+var_110]; this
0x18003aadb  test    rcx, rcx
0x18003aade  jz      short loc_18003AB28
0x18003aae0  mov     rdx, qword ptr [rsp+158h+var_108]
0x18003aae5  call    ??$_Destroy_range@V?$allocator@UMESSAGE_ENTRY@@@std@@@std@@YAXPEAUMESSAGE_ENTRY@@QEAU1@AEAV?$allocator@UMESSAGE_ENTRY@@@0@@Z; std::_Destroy_range<std::allocator<MESSAGE_ENTRY>>(MESSAGE_ENTRY *,MESSAGE_ENTRY * const,std::allocator<MESSAGE_ENTRY> &)
0x18003aaea  mov     rcx, [rsp+158h+var_110]
0x18003aaef  mov     rax, qword ptr [rsp+158h+var_108+8]
0x18003aaf4  sub     rax, rcx
0x18003aaf7  sar     rax, 3
0x18003aafb  mov     rdx, 8E38E38E38E38E39h
0x18003ab05  imul    rax, rdx
0x18003ab09  lea     rdx, [rax+rax*8]
0x18003ab0d  shl     rdx, 3
0x18003ab11  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003ab16  mov     [rsp+158h+var_110], 0
0x18003ab1f  xorps   xmm0, xmm0
0x18003ab22  movdqa  [rsp+158h+var_108], xmm0
0x18003ab28  lea     rcx, [rsp+158h+var_58]; this
0x18003ab30  call    ??1XmlReader@@QEAA@XZ; XmlReader::~XmlReader(void)
0x18003ab35  nop
0x18003ab36  jmp     short loc_18003AB3C
0x18003ab38  jmp     short loc_18003AB3C
0x18003ab3a  jmp     short $+2
0x18003ab3c  mov     eax, [rsp+158h+arg_10]
0x18003ab43  mov     rbx, [rsp+158h+arg_18]
0x18003ab4b  add     rsp, 150h
0x18003ab52  pop     rdi
0x18003ab53  retn
```
