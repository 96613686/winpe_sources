# CMicrodomBuilder::StartElement(CXmlCursor *)

- ea: `0x1800556ac`
- end: `0x180055a86`
- name: `?StartElement@CMicrodomBuilder@@AEAAJPEAVCXmlCursor@@@Z`
- size: `986`
- prototype: `__int64 __fastcall(CMicrodomBuilder *__hidden this, struct CXmlCursor *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180057e54`

## callees

- `0x1800370f4`
- `0x1800547f8`
- `0x180055520`
- `0x18005557c`
- `0x1800556ac`
- `0x180055a8c`
- `0x18005f1e0`
- `0x180060014`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x1800556db`
- `ntdll!RtlRaiseStatus` at `0x1800559d7`
- `ntdll!RtlRaiseStatus` at `0x1800556db`
- `ntdll!RtlRaiseStatus` at `0x1800559d7`

## string_xrefs

- `0x1800556ff`: `onecore\base\xml\udom_builder.cpp`
- `0x1800559ac`: `onecore\base\xml\udom_builder.cpp`
- `0x180055a06`: `onecore\base\xml\udom_builder.cpp`

## pseudocode

```c
__int64 __fastcall CMicrodomBuilder::StartElement(CMicrodomBuilder *this, struct CXmlCursor *a2)
{
  char *v4; // r15
  struct CMicrodomBuilder::CXmlStreamObject *StreamObject; // rax
  __int64 v6; // rdx
  struct _XML_EXTENT *v7; // r13
  struct CMicrodomBuilder::CXmlStreamObject *v8; // rsi
  const char *v9; // rax
  __int64 result; // rax
  unsigned int v11; // ecx
  unsigned int v12; // edx
  char *v13; // rbx
  __int64 v14; // rdx
  _QWORD *v15; // r8
  _QWORD *v16; // rax
  unsigned int v17; // r12d
  bool i; // zf
  NTSTATUS v19; // eax
  struct CMicrodomBuilder::CXmlStreamObject *v20; // rax
  struct CMicrodomBuilder::CXmlStreamObject *v21; // rsi
  unsigned int v22; // edx
  unsigned int v23; // r8d
  __int64 v24; // rdx
  _QWORD *v25; // rcx
  _QWORD *v26; // r8
  struct CMicrodomBuilder::CXmlStreamObject *v27; // rax
  int v28; // [rsp+30h] [rbp-40h] BYREF
  int v29; // [rsp+34h] [rbp-3Ch]
  int v30; // [rsp+38h] [rbp-38h]
  const char *v31; // [rsp+40h] [rbp-30h] BYREF
  const char *v32; // [rsp+48h] [rbp-28h]
  int v33; // [rsp+50h] [rbp-20h]
  const char *v34; // [rsp+58h] [rbp-18h]
  struct _XML_EXTENT *v35; // [rsp+60h] [rbp-10h] BYREF

  if ( *((_DWORD *)a2 + 2282) != 3 )
    RtlRaiseStatus(-1073741595);
  v4 = (char *)a2 + 9184;
  StreamObject = CMicrodomBuilder::AllocateStreamObject(this);
  v7 = 0;
  v8 = StreamObject;
  if ( !StreamObject )
  {
    v33 = 1290;
    v31 = "onecore\\base\\xml\\udom_builder.cpp";
    v32 = "CMicrodomBuilder::StartElement";
    v9 = "NewElement = this->AllocateStreamObject()";
LABEL_5:
    v34 = v9;
    RtlReportErrorOrigination(&v31, v6, 3221225495LL);
    return 3221225495LL;
  }
  *((_DWORD *)StreamObject + 18) = (*((_DWORD *)this + 324))++;
  v11 = *((_DWORD *)v4 + 18);
  *((_DWORD *)StreamObject + 20) = v11;
  v12 = *((_DWORD *)v4 + 19);
  *((_DWORD *)StreamObject + 21) = v12;
  if ( v11 > v12 )
    v12 = v11;
  if ( *((_DWORD *)this + 325) > v12 )
    v12 = *((_DWORD *)this + 325);
  *((_DWORD *)this + 325) = v12;
  *((_DWORD *)StreamObject + 28) = 16;
  result = CMicrodomBuilder::AddStringsForElement(
             this,
             a2,
             (const struct _XML_EXTENT *)(v4 + 24),
             (const struct _XML_EXTENT *)(v4 + 48),
             (const struct _XML_EXTENT *)v4,
             (struct CMicrodomBuilder::ThreeStringIdPair *)&v28);
  if ( (int)result >= 0 )
  {
    v13 = (char *)this + 1264;
    *((_DWORD *)v8 + 30) = v28;
    *((_DWORD *)v8 + 29) = v29;
    *((_DWORD *)v8 + 31) = v30;
    *((_QWORD *)v8 + 8) = *((_QWORD *)this + 157);
    *((_QWORD *)v8 + 1) = *((_QWORD *)this + 159);
    *(_QWORD *)v8 = (char *)this + 1264;
    **((_QWORD **)this + 159) = v8;
    *((_QWORD *)this + 159) = v8;
    *((_QWORD *)v8 + 2) = (char *)this + 1264;
    ++*((_QWORD *)this + 161);
    v14 = *((_QWORD *)this + 157);
    if ( v14 )
    {
      v15 = *(_QWORD **)(v14 + 96);
      v16 = (_QWORD *)((char *)v8 + 48);
      if ( *v15 != v14 + 88 )
LABEL_32:
        __fastfail(3u);
      *v16 = v14 + 88;
      *((_QWORD *)v8 + 7) = v15;
      *v15 = v16;
      *(_QWORD *)(v14 + 96) = v16;
      ++*(_QWORD *)(v14 + 104);
    }
    *((_QWORD *)this + 157) = v8;
    v17 = 0;
    for ( i = *((_DWORD *)v4 + 20) == 0; !i; i = v17 == *((_DWORD *)v4 + 20) )
    {
      v35 = 0;
      if ( a2 == (struct CXmlCursor *)-3456LL )
      {
        v19 = RtlXmlReportErrorFunction(3221225485LL);
      }
      else
      {
        v19 = RtlIndexIntoGrowingList((char *)a2 + 3456, v17, &v35);
        v7 = v35;
      }
      if ( v19 < 0 )
        RtlRaiseStatus(v19);
      v20 = CMicrodomBuilder::AllocateStreamObject(this);
      v21 = v20;
      if ( !v20 )
      {
        v33 = 1339;
        v31 = "onecore\\base\\xml\\udom_builder.cpp";
        v32 = "CMicrodomBuilder::StartElement";
        v9 = "NewAttribute = this->AllocateStreamObject()";
        goto LABEL_5;
      }
      *((_DWORD *)v20 + 18) = (*((_DWORD *)this + 324))++;
      v22 = *((_DWORD *)v7 + 24);
      *((_DWORD *)v20 + 20) = v22;
      v23 = *((_DWORD *)v7 + 25);
      *((_DWORD *)v20 + 21) = v23;
      if ( v22 > v23 )
        v23 = v22;
      if ( *((_DWORD *)this + 325) > v23 )
        v23 = *((_DWORD *)this + 325);
      *((_DWORD *)this + 325) = v23;
      ++*(_DWORD *)(*((_QWORD *)this + 157) + 76LL);
      *((_BYTE *)v20 + 132) = 1;
      *((_DWORD *)v20 + 28) = 65560;
      result = CMicrodomBuilder::AddStringsForElement(
                 this,
                 a2,
                 (struct _XML_EXTENT *)((char *)v7 + 24),
                 (struct _XML_EXTENT *)((char *)v7 + 72),
                 v7,
                 (struct CMicrodomBuilder::ThreeStringIdPair *)&v28);
      if ( (int)result < 0 )
        return result;
      *((_DWORD *)v21 + 30) = v28;
      *((_DWORD *)v21 + 29) = v29;
      *((_DWORD *)v21 + 31) = v30;
      if ( *((_DWORD *)v7 + 17) )
      {
        result = CMicrodomBuilder::DecodeAndAddString(
                   this,
                   a2,
                   (struct _XML_EXTENT *)((char *)v7 + 48),
                   (unsigned int *)v21 + 32);
        v7 = 0;
        if ( (int)result < 0 )
          return result;
      }
      else
      {
        *((_DWORD *)v21 + 32) = -1;
        v7 = 0;
      }
      v24 = *((_QWORD *)this + 157);
      v25 = (_QWORD *)((char *)v21 + 48);
      v26 = *(_QWORD **)(v24 + 96);
      if ( *v26 != v24 + 88 )
        goto LABEL_32;
      *v25 = v24 + 88;
      *((_QWORD *)v21 + 7) = v26;
      ++v17;
      *v26 = v25;
      *(_QWORD *)(v24 + 96) = v25;
      ++*(_QWORD *)(v24 + 104);
      *((_QWORD *)v21 + 1) = *((_QWORD *)this + 159);
      *(_QWORD *)v21 = v13;
      **((_QWORD **)this + 159) = v21;
      *((_QWORD *)this + 159) = v21;
      *((_QWORD *)v21 + 2) = v13;
      ++*((_QWORD *)this + 161);
    }
    result = CMicrodomBuilder::InsertDefaultAttributes(this);
    if ( (int)result >= 0 )
    {
      if ( v4[84] )
      {
        v27 = CMicrodomBuilder::AllocateStreamObject(this);
        if ( !v27 )
        {
          v33 = 1401;
          v31 = "onecore\\base\\xml\\udom_builder.cpp";
          v32 = "CMicrodomBuilder::StartElement";
          v9 = "CloserElement = this->AllocateStreamObject()";
          goto LABEL_5;
        }
        *((_DWORD *)v27 + 28) = 196612;
        *((_QWORD *)v27 + 1) = *((_QWORD *)this + 159);
        *(_QWORD *)v27 = v13;
        **((_QWORD **)this + 159) = v27;
        *((_QWORD *)this + 159) = v27;
        *((_QWORD *)v27 + 2) = v13;
        ++*((_QWORD *)this + 161);
        *((_QWORD *)this + 157) = *(_QWORD *)(*((_QWORD *)this + 157) + 64LL);
      }
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800556ac  mov     [rsp-38h+arg_10], rbx
0x1800556b1  push    rbp
0x1800556b2  push    rsi
0x1800556b3  push    rdi
0x1800556b4  push    r12
0x1800556b6  push    r13
0x1800556b8  push    r14
0x1800556ba  push    r15
0x1800556bc  mov     rbp, rsp
0x1800556bf  sub     rsp, 70h
0x1800556c3  mov     eax, 3
0x1800556c8  mov     r14, rdx
0x1800556cb  mov     rdi, rcx
0x1800556ce  cmp     [rdx+23A8h], eax
0x1800556d4  jz      short loc_1800556E8
0x1800556d6  mov     ecx, 0C00000E5h; Status
0x1800556db  call    cs:__imp_RtlRaiseStatus
0x1800556e2  nop     dword ptr [rax+rax+00h]
0x1800556e7  int     3; Trap to Debugger
0x1800556e8  lea     r15, [rdx+23E0h]
0x1800556ef  call    ?AllocateStreamObject@CMicrodomBuilder@@AEAAPEAVCXmlStreamObject@1@XZ; CMicrodomBuilder::AllocateStreamObject(void)
0x1800556f4  xor     r13d, r13d
0x1800556f7  mov     rsi, rax
0x1800556fa  test    rax, rax
0x1800556fd  jnz     short loc_180055740
0x1800556ff  lea     rax, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_builder.cpp"
0x180055706  mov     [rbp+var_20], 50Ah
0x18005570d  mov     [rbp+var_30], rax
0x180055711  lea     rax, aCmicrodombuild_17; "CMicrodomBuilder::StartElement"
0x180055718  mov     [rbp+var_28], rax
0x18005571c  lea     rax, aNewelementThis; "NewElement = this->AllocateStreamObject"...
0x180055723  mov     r8d, 0C0000017h
0x180055729  mov     [rbp+var_18], rax
0x18005572d  lea     rcx, [rbp+var_30]
0x180055731  call    RtlReportErrorOrigination
0x180055736  mov     eax, 0C0000017h
0x18005573b  jmp     loc_180055A6E
0x180055740  mov     eax, [rdi+510h]
0x180055746  lea     r8, [r15+18h]; struct _XML_EXTENT *
0x18005574a  mov     [rsi+48h], eax
0x18005574d  mov     r9d, 1
0x180055753  add     [rdi+510h], r9d
0x18005575a  lea     r9, [r15+30h]; struct _XML_EXTENT *
0x18005575e  mov     ecx, [r15+48h]
0x180055762  mov     [rsi+50h], ecx
0x180055765  mov     edx, [r15+4Ch]
0x180055769  cmp     ecx, edx
0x18005576b  mov     [rsi+54h], edx
0x18005576e  mov     eax, [rdi+514h]
0x180055774  cmova   edx, ecx
0x180055777  cmp     eax, edx
0x180055779  mov     rcx, rdi; this
0x18005577c  cmova   edx, eax
0x18005577f  lea     rax, [rbp+var_40]
0x180055783  mov     [rdi+514h], edx
0x180055789  mov     rdx, r14; struct CXmlCursor *
0x18005578c  mov     [rsp+70h+var_48], rax; struct CMicrodomBuilder::ThreeStringIdPair *
0x180055791  mov     [rsp+70h+var_50], r15; struct _XML_EXTENT *
0x180055796  mov     dword ptr [rsi+70h], 10h
0x18005579d  call    ?AddStringsForElement@CMicrodomBuilder@@AEAAJPEAVCXmlCursor@@AEBU_XML_EXTENT@@11PEAUThreeStringIdPair@1@@Z; CMicrodomBuilder::AddStringsForElement(CXmlCursor *,_XML_EXTENT const &,_XML_EXTENT const &,_XML_EXTENT const &,CMicrodomBuilder::ThreeStringIdPair *)
0x1800557a2  test    eax, eax
0x1800557a4  js      loc_180055A6E
0x1800557aa  mov     eax, [rbp+var_40]
0x1800557ad  lea     rbx, [rdi+4F0h]
0x1800557b4  mov     [rsi+78h], eax
0x1800557b7  mov     r9d, 1
0x1800557bd  mov     eax, [rbp+var_3C]
0x1800557c0  mov     [rsi+74h], eax
0x1800557c3  mov     eax, [rbp+var_38]
0x1800557c6  mov     [rsi+7Ch], eax
0x1800557c9  mov     rax, [rdi+4E8h]
0x1800557d0  mov     [rsi+40h], rax
0x1800557d4  mov     rax, [rbx+8]
0x1800557d8  mov     [rsi+8], rax
0x1800557dc  mov     [rsi], rbx
0x1800557df  mov     rax, [rbx+8]
0x1800557e3  mov     [rax], rsi
0x1800557e6  mov     [rbx+8], rsi
0x1800557ea  mov     [rsi+10h], rbx
0x1800557ee  add     [rbx+18h], r9
0x1800557f2  mov     rdx, [rdi+4E8h]
0x1800557f9  test    rdx, rdx
0x1800557fc  jz      short loc_180055825
0x1800557fe  lea     rcx, [rdx+58h]
0x180055802  mov     r8, [rcx+8]
0x180055806  lea     rax, [rsi+30h]
0x18005580a  cmp     [r8], rcx
0x18005580d  jnz     loc_1800559A5
0x180055813  mov     [rax], rcx
0x180055816  mov     [rax+8], r8
0x18005581a  mov     [r8], rax
0x18005581d  mov     [rcx+8], rax
0x180055821  add     [rdx+68h], r9
0x180055825  mov     [rdi+4E8h], rsi
0x18005582c  mov     r12d, r13d
0x18005582f  cmp     [r15+50h], r13d
0x180055833  jz      loc_1800559E4
0x180055839  lea     rax, [r14+0D80h]
0x180055840  mov     [rbp+var_10], r13
0x180055844  test    rax, rax
0x180055847  jz      short loc_18005585E
0x180055849  lea     r8, [rbp+var_10]
0x18005584d  mov     edx, r12d
0x180055850  mov     rcx, rax
0x180055853  call    RtlIndexIntoGrowingList
0x180055858  mov     r13, [rbp+var_10]
0x18005585c  jmp     short loc_180055868
0x18005585e  mov     ecx, 0C000000Dh
0x180055863  call    RtlXmlReportErrorFunction
0x180055868  test    eax, eax
0x18005586a  js      loc_1800559D5
0x180055870  mov     rcx, rdi; this
0x180055873  call    ?AllocateStreamObject@CMicrodomBuilder@@AEAAPEAVCXmlStreamObject@1@XZ; CMicrodomBuilder::AllocateStreamObject(void)
0x180055878  mov     rsi, rax
0x18005587b  test    rax, rax
0x18005587e  jz      loc_1800559AC
0x180055884  mov     ecx, [rdi+510h]
0x18005588a  mov     r9d, 1
0x180055890  mov     [rax+48h], ecx
0x180055893  add     [rdi+510h], r9d
0x18005589a  mov     edx, [r13+60h]
0x18005589e  mov     [rax+50h], edx
0x1800558a1  mov     r8d, [r13+64h]
0x1800558a5  cmp     edx, r8d
0x1800558a8  mov     [rax+54h], r8d
0x1800558ac  mov     ecx, [rdi+514h]
0x1800558b2  cmova   r8d, edx
0x1800558b6  cmp     ecx, r8d
0x1800558b9  mov     rdx, r14; struct CXmlCursor *
0x1800558bc  cmova   r8d, ecx
0x1800558c0  mov     rcx, rdi; this
0x1800558c3  mov     [rdi+514h], r8d
0x1800558ca  lea     r8, [r13+18h]; struct _XML_EXTENT *
0x1800558ce  mov     rax, [rdi+4E8h]
0x1800558d5  add     [rax+4Ch], r9d
0x1800558d9  lea     rax, [rbp+var_40]
0x1800558dd  mov     [rsi+84h], r9b
0x1800558e4  lea     r9, [r13+48h]; struct _XML_EXTENT *
0x1800558e8  mov     [rsp+70h+var_48], rax; struct CMicrodomBuilder::ThreeStringIdPair *
0x1800558ed  mov     [rsp+70h+var_50], r13; struct _XML_EXTENT *
0x1800558f2  mov     dword ptr [rsi+70h], 10018h
0x1800558f9  call    ?AddStringsForElement@CMicrodomBuilder@@AEAAJPEAVCXmlCursor@@AEBU_XML_EXTENT@@11PEAUThreeStringIdPair@1@@Z; CMicrodomBuilder::AddStringsForElement(CXmlCursor *,_XML_EXTENT const &,_XML_EXTENT const &,_XML_EXTENT const &,CMicrodomBuilder::ThreeStringIdPair *)
0x1800558fe  test    eax, eax
0x180055900  js      loc_180055A6E
0x180055906  mov     eax, [rbp+var_40]
0x180055909  mov     [rsi+78h], eax
0x18005590c  mov     eax, [rbp+var_3C]
0x18005590f  mov     [rsi+74h], eax
0x180055912  mov     eax, [rbp+var_38]
0x180055915  mov     [rsi+7Ch], eax
0x180055918  lea     rax, [rsi+80h]
0x18005591f  cmp     dword ptr [r13+44h], 0
0x180055924  jz      short loc_180055945
0x180055926  lea     r8, [r13+30h]; struct _XML_EXTENT *
0x18005592a  mov     r9, rax; unsigned int *
0x18005592d  mov     rdx, r14; struct CXmlCursor *
0x180055930  mov     rcx, rdi; this
0x180055933  call    ?DecodeAndAddString@CMicrodomBuilder@@AEAAJPEAVCXmlCursor@@AEBU_XML_EXTENT@@PEAK@Z; CMicrodomBuilder::DecodeAndAddString(CXmlCursor *,_XML_EXTENT const &,ulong *)
0x180055938  xor     r13d, r13d
0x18005593b  test    eax, eax
0x18005593d  js      loc_180055A6E
0x180055943  jmp     short loc_18005594B
0x180055945  or      dword ptr [rax], 0FFFFFFFFh
0x180055948  xor     r13d, r13d
0x18005594b  mov     rdx, [rdi+4E8h]
0x180055952  lea     rcx, [rsi+30h]
0x180055956  lea     rax, [rdx+58h]
0x18005595a  mov     r8, [rax+8]
0x18005595e  cmp     [r8], rax
0x180055961  jnz     short loc_1800559A5
0x180055963  mov     [rcx], rax
0x180055966  mov     r9d, 1
0x18005596c  mov     [rcx+8], r8
0x180055970  add     r12d, r9d
0x180055973  mov     [r8], rcx
0x180055976  mov     [rax+8], rcx
0x18005597a  add     [rdx+68h], r9
0x18005597e  mov     rax, [rbx+8]
0x180055982  mov     [rsi+8], rax
0x180055986  mov     [rsi], rbx
0x180055989  mov     rax, [rbx+8]
0x18005598d  mov     [rax], rsi
0x180055990  mov     [rbx+8], rsi
0x180055994  mov     [rsi+10h], rbx
0x180055998  add     [rbx+18h], r9
0x18005599c  cmp     r12d, [r15+50h]
0x1800559a0  jmp     loc_180055833
0x1800559a5  mov     ecx, 3
0x1800559aa  int     29h; Win8: RtlFailFast(ecx)
0x1800559ac  lea     rax, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_builder.cpp"
0x1800559b3  mov     [rbp+var_20], 53Bh
0x1800559ba  mov     [rbp+var_30], rax
0x1800559be  lea     rax, aCmicrodombuild_17; "CMicrodomBuilder::StartElement"
0x1800559c5  mov     [rbp+var_28], rax
0x1800559c9  lea     rax, aNewattributeTh; "NewAttribute = this->AllocateStreamObje"...
0x1800559d0  jmp     loc_180055723
0x1800559d5  mov     ecx, eax; Status
0x1800559d7  call    cs:__imp_RtlRaiseStatus
0x1800559de  nop     dword ptr [rax+rax+00h]
0x1800559e3  int     3; Trap to Debugger
0x1800559e4  mov     rcx, rdi; this
0x1800559e7  call    ?InsertDefaultAttributes@CMicrodomBuilder@@AEAAJXZ; CMicrodomBuilder::InsertDefaultAttributes(void)
0x1800559ec  test    eax, eax
0x1800559ee  js      short loc_180055A6E
0x1800559f0  cmp     [r15+54h], r13b
0x1800559f4  jz      short loc_180055A6C
0x1800559f6  mov     rcx, rdi; this
0x1800559f9  call    ?AllocateStreamObject@CMicrodomBuilder@@AEAAPEAVCXmlStreamObject@1@XZ; CMicrodomBuilder::AllocateStreamObject(void)
0x1800559fe  mov     rcx, rax
0x180055a01  test    rax, rax
0x180055a04  jnz     short loc_180055A2F
0x180055a06  lea     rax, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_builder.cpp"
0x180055a0d  mov     [rbp+var_20], 579h
0x180055a14  mov     [rbp+var_30], rax
0x180055a18  lea     rax, aCmicrodombuild_17; "CMicrodomBuilder::StartElement"
0x180055a1f  mov     [rbp+var_28], rax
0x180055a23  lea     rax, aCloserelementT; "CloserElement = this->AllocateStreamObj"...
0x180055a2a  jmp     loc_180055723
0x180055a2f  mov     dword ptr [rax+70h], 30004h
0x180055a36  mov     r9d, 1
0x180055a3c  mov     rax, [rbx+8]
0x180055a40  mov     [rcx+8], rax
0x180055a44  mov     [rcx], rbx
0x180055a47  mov     rax, [rbx+8]
0x180055a4b  mov     [rax], rcx
0x180055a4e  mov     [rbx+8], rcx
0x180055a52  mov     [rcx+10h], rbx
0x180055a56  add     [rbx+18h], r9
0x180055a5a  mov     rax, [rdi+4E8h]
0x180055a61  mov     rcx, [rax+40h]
0x180055a65  mov     [rdi+4E8h], rcx
0x180055a6c  xor     eax, eax
0x180055a6e  mov     rbx, [rsp+70h+arg_10]
0x180055a76  add     rsp, 70h
0x180055a7a  pop     r15
0x180055a7c  pop     r14
0x180055a7e  pop     r13
0x180055a80  pop     r12
0x180055a82  pop     rdi
0x180055a83  pop     rsi
0x180055a84  pop     rbp
0x180055a85  retn
```
