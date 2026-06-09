# Marshal::ToXmlString<Schema::Containers::Definition::Container const &,>(Schema::Containers::Definition::Container const &,ushort const *,bool,Marshal::MarshalFlags)

- ea: `0x1400cd404`
- end: `0x1400cd766`
- name: `??$ToXmlString@AEBUContainer@Definition@Containers@Schema@@$$V@Marshal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUContainer@Definition@Containers@Schema@@PEBG_NW4MarshalFlags@0@@Z`
- size: `866`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400dbe7c`

## callees

- `0x140005360`
- `0x14000ea60`
- `0x1400ccb84`
- `0x1400cd31c`
- `0x1400cd404`
- `0x1400fe010`

## import_xrefs

- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x1400cd462`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x1400cd462`
- `XmlLite!CreateXmlWriter` at `0x1400cd492`
- `XmlLite!CreateXmlWriter` at `0x1400cd492`

## string_xrefs

- `0x1400cd6ac`: `onecore\vm\common\marshal\inc\MarshalXml.h`
- `0x1400cd6c1`: `onecore\vm\common\marshal\inc\MarshalXml.h`
- `0x1400cd6d6`: `onecore\vm\common\marshal\inc\MarshalXml.h`
- `0x1400cd6eb`: `onecore\vm\common\marshal\inc\MarshalXml.h`
- `0x1400cd700`: `onecore\vm\common\marshal\inc\MarshalXml.h`
- `0x1400cd715`: `onecore\vm\common\marshal\inc\MarshalXml.h`
- `0x1400cd72a`: `onecore\vm\common\marshal\inc\MarshalXml.h`
- `0x1400cd73f`: `onecore\vm\common\marshal\inc\MarshalXml.h`
- `0x1400cd754`: `onecore\vm\common\marshal\inc\MarshalXml.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall Marshal::ToXmlString<Schema::Containers::Definition::Container const &,>(_QWORD *a1, int a2)
{
  HRESULT v4; // eax
  HRESULT v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  void *v10; // rdi
  int v11; // eax
  int v12; // eax
  int v13; // eax
  IUnknown *v14; // rcx
  IUnknown *v15; // rcx
  int v17; // [rsp+20h] [rbp-41h]
  int v18; // [rsp+20h] [rbp-41h]
  void *ppvObject; // [rsp+30h] [rbp-31h] BYREF
  IUnknown *pOutputStream; // [rsp+38h] [rbp-29h] BYREF
  int v21; // [rsp+40h] [rbp-21h]
  _QWORD v22[2]; // [rsp+50h] [rbp-11h] BYREF
  int v23[2]; // [rsp+60h] [rbp-1h] BYREF
  _UNKNOWN ***v24; // [rsp+68h] [rbp+7h]
  _QWORD v25[2]; // [rsp+70h] [rbp+Fh] BYREF
  void *v26; // [rsp+80h] [rbp+1Fh] BYREF
  int v27; // [rsp+88h] [rbp+27h] BYREF
  IXmlWriterOutput *ppOutput; // [rsp+90h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+57h]

  v26 = a1;
  v21 = 0;
  pOutputStream = 0;
  wil::MakeOrThrow<Marshal::Details::UTF16StringWriter,>(&pOutputStream);
  ppOutput = 0;
  v4 = CreateXmlWriterOutputWithEncodingName(pOutputStream, 0, L"UTF-16", &ppOutput);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x42B,
      (unsigned int)"onecore\\vm\\common\\marshal\\inc\\MarshalXml.h",
      (const char *)(unsigned int)v4,
      v17);
  v21 = 4;
  ppvObject = 0;
  v5 = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x42E,
      (unsigned int)"onecore\\vm\\common\\marshal\\inc\\MarshalXml.h",
      (const char *)(unsigned int)v5,
      v17);
  v6 = (*(__int64 (__fastcall **)(void *, IXmlWriterOutput *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppOutput);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x42F,
      (unsigned int)"onecore\\vm\\common\\marshal\\inc\\MarshalXml.h",
      (const char *)(unsigned int)v6,
      v17);
  v7 = (*(__int64 (__fastcall **)(void *, __int64, _QWORD))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 2, 0);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x431,
      (unsigned int)"onecore\\vm\\common\\marshal\\inc\\MarshalXml.h",
      (const char *)(unsigned int)v7,
      v17);
  v8 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4, 1);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x433,
      (unsigned int)"onecore\\vm\\common\\marshal\\inc\\MarshalXml.h",
      (const char *)(unsigned int)v8,
      v17);
  v9 = (*(__int64 (__fastcall **)(void *, __int64, _QWORD))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 1, 0);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x434,
      (unsigned int)"onecore\\vm\\common\\marshal\\inc\\MarshalXml.h",
      (const char *)(unsigned int)v9,
      v17);
  if ( ppOutput )
    ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
  v10 = ppvObject;
  v26 = ppvObject;
  v27 = 0;
  v11 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 216LL))(
          ppvObject,
          0,
          L"container",
          0);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E3,
      (unsigned int)"onecore\\vm\\common\\marshal\\inc\\MarshalXml.h",
      (const char *)(unsigned int)v11,
      v17);
  v22[0] = &Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Schema::Containers::Definition::Namespace>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v22[1] = &Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Schema::Containers::Definition::Namespace>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  *(_QWORD *)v23 = &Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Schema::Containers::Definition::Namespace>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v24 = &Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<std::vector<enum CCGSchema::CmsKind>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<CCGSchema::DomainJoinConfigType>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<CCGSchema::ActiveDirectoryConfigType>,Marshal::ModifierList<>>>,Marshal::Details::JsonTypeData,Marshal::Details::JsonTypeInfo>::Value;
  v25[0] = Schema::Containers::Definition::Container_ClassData;
  v25[1] = Schema::Containers::Definition::Container_ClassData + 32;
  Marshal::Details::WriteObjectXml(
    (unsigned int)&v26,
    a2,
    (unsigned int)&v27,
    (unsigned int)v25,
    (__int64)v23,
    (__int64)v22);
  v12 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v26 + 120LL))(v26);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1EF,
      (unsigned int)"onecore\\vm\\common\\marshal\\inc\\MarshalXml.h",
      (const char *)(unsigned int)v12,
      v18);
  v13 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v10 + 248LL))(v10);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x502,
      (unsigned int)"onecore\\vm\\common\\marshal\\inc\\MarshalXml.h",
      (const char *)(unsigned int)v13,
      v18);
  if ( ppvObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
  v14 = pOutputStream;
  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 0;
  *(_OWORD *)a1 = *(_OWORD *)&v14[2].lpVtbl;
  *((_OWORD *)a1 + 1) = *(_OWORD *)&v14[4].lpVtbl;
  v14[4].lpVtbl = 0;
  v14[5].lpVtbl = (struct IUnknownVtbl *)7;
  LOWORD(v14[2].lpVtbl) = 0;
  v15 = pOutputStream;
  if ( pOutputStream )
  {
    pOutputStream = 0;
    ((void (__fastcall *)(IUnknown *))v15->lpVtbl->Release)(v15);
  }
  return a1;
}

```

## disassembly

```asm
0x1400cd404  mov     [rsp-8+arg_10], rbx
0x1400cd409  push    rbp
0x1400cd40a  push    rsi
0x1400cd40b  push    rdi
0x1400cd40c  lea     rbp, [rsp-3Fh]
0x1400cd411  sub     rsp, 0A0h
0x1400cd418  mov     rax, cs:__security_cookie
0x1400cd41f  xor     rax, rsp
0x1400cd422  mov     [rbp+4Fh+var_18], rax
0x1400cd426  mov     rsi, rdx
0x1400cd429  mov     rbx, rcx
0x1400cd42c  mov     [rbp+4Fh+var_30], rcx
0x1400cd430  mov     [rbp+4Fh+var_70], 0
0x1400cd437  mov     [rbp+4Fh+pOutputStream], 0
0x1400cd43f  lea     rcx, [rbp+4Fh+pOutputStream]
0x1400cd443  call    ??$MakeOrThrow@VUTF16StringWriter@Details@Marshal@@$$V@wil@@YA?AV?$ComPtr@VUTF16StringWriter@Details@Marshal@@@WRL@Microsoft@@XZ; wil::MakeOrThrow<Marshal::Details::UTF16StringWriter,>(void)
0x1400cd448  nop
0x1400cd449  mov     [rbp+4Fh+ppOutput], 0
0x1400cd451  lea     r9, [rbp+4Fh+ppOutput]; ppOutput
0x1400cd455  lea     r8, pwszEncodingName; "UTF-16"
0x1400cd45c  xor     edx, edx; pMalloc
0x1400cd45e  mov     rcx, [rbp+4Fh+pOutputStream]; pOutputStream
0x1400cd462  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x1400cd468  mov     rcx, [rbp+57h]; this
0x1400cd46c  test    eax, eax
0x1400cd46e  js      loc_1400CD6BE
0x1400cd474  mov     edi, 4
0x1400cd479  mov     [rbp+4Fh+var_70], edi
0x1400cd47c  mov     [rbp+4Fh+ppvObject], 0
0x1400cd484  xor     r8d, r8d; pMalloc
0x1400cd487  lea     rdx, [rbp+4Fh+ppvObject]; ppvObject
0x1400cd48b  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x1400cd492  call    cs:__imp_CreateXmlWriter
0x1400cd498  mov     rcx, [rbp+57h]; this
0x1400cd49c  test    eax, eax
0x1400cd49e  js      loc_1400CD6D3
0x1400cd4a4  mov     rcx, [rbp+4Fh+ppvObject]
0x1400cd4a8  mov     rax, [rcx]
0x1400cd4ab  mov     rdx, [rbp+4Fh+ppOutput]
0x1400cd4af  mov     rax, [rax+18h]
0x1400cd4b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cd4b8  mov     rcx, [rbp+57h]; this
0x1400cd4bc  test    eax, eax
0x1400cd4be  js      loc_1400CD6E8
0x1400cd4c4  mov     rcx, [rbp+4Fh+ppvObject]
0x1400cd4c8  mov     rax, [rcx]
0x1400cd4cb  xor     r8d, r8d
0x1400cd4ce  lea     edx, [rdi-2]
0x1400cd4d1  mov     rax, [rax+28h]
0x1400cd4d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cd4da  mov     rcx, [rbp+57h]; this
0x1400cd4de  test    eax, eax
0x1400cd4e0  js      loc_1400CD6FD
0x1400cd4e6  mov     rcx, [rbp+4Fh+ppvObject]
0x1400cd4ea  mov     rax, [rcx]
0x1400cd4ed  lea     r8d, [rdi-3]
0x1400cd4f1  mov     edx, edi
0x1400cd4f3  mov     rax, [rax+28h]
0x1400cd4f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cd4fc  mov     rcx, [rbp+57h]; this
0x1400cd500  test    eax, eax
0x1400cd502  js      loc_1400CD712
0x1400cd508  mov     rcx, [rbp+4Fh+ppvObject]
0x1400cd50c  mov     rax, [rcx]
0x1400cd50f  xor     r8d, r8d
0x1400cd512  lea     edx, [rdi-3]
0x1400cd515  mov     rax, [rax+28h]
0x1400cd519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cd51e  mov     rcx, [rbp+57h]; this
0x1400cd522  test    eax, eax
0x1400cd524  js      loc_1400CD727
0x1400cd52a  mov     rcx, [rbp+4Fh+ppOutput]
0x1400cd52e  test    rcx, rcx
0x1400cd531  jz      short loc_1400CD540
0x1400cd533  mov     rax, [rcx]
0x1400cd536  mov     rax, [rax+10h]
0x1400cd53a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cd53f  nop
0x1400cd540  mov     rdi, [rbp+4Fh+ppvObject]
0x1400cd544  mov     [rbp+4Fh+var_30], rdi
0x1400cd548  mov     [rbp+4Fh+var_28], 0
0x1400cd54f  mov     rax, [rdi]
0x1400cd552  xor     r9d, r9d
0x1400cd555  lea     r8, aContainer_1; "container"
0x1400cd55c  xor     edx, edx
0x1400cd55e  mov     rcx, rdi
0x1400cd561  mov     rax, [rax+0D8h]
0x1400cd568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cd56d  mov     rcx, [rbp+57h]; this
0x1400cd571  test    eax, eax
0x1400cd573  js      loc_1400CD73C
0x1400cd579  mov     rax, cs:?Container_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::Container_ClassData
0x1400cd580  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@UNamespace@Definition@Containers@Schema@@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$00@std@@A; std::array<Marshal::Details::XmlTypeData const *,1> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Schema::Containers::Definition::Namespace>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x1400cd587  mov     [rbp+4Fh+var_60], rcx
0x1400cd58b  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@UNamespace@Definition@Containers@Schema@@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$00@std@@A; std::array<Marshal::Details::BaseTypeData const *,1> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Schema::Containers::Definition::Namespace>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x1400cd592  mov     [rbp+4Fh+var_58], rcx
0x1400cd596  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@UNamespace@Definition@Containers@Schema@@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$00@std@@A; std::array<Marshal::Details::BaseTypeData const *,1> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Schema::Containers::Definition::Namespace>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x1400cd59d  mov     qword ptr [rbp+4Fh+var_50], rcx
0x1400cd5a1  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@U?$ModifiedType@V?$vector@W4CmsKind@CCGSchema@@V?$allocator@W4CmsKind@CCGSchema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@U?$optional@UDomainJoinConfigType@CCGSchema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@U?$optional@UActiveDirectoryConfigType@CCGSchema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@@Marshal@@UJsonTypeData@Details@2@UJsonTypeInfo@42@@Details@Marshal@@2V?$array@PEBUJsonTypeData@Details@Marshal@@$02@std@@A; std::array<Marshal::Details::JsonTypeData const *,3> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<std::vector<CCGSchema::CmsKind>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<CCGSchema::DomainJoinConfigType>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<CCGSchema::ActiveDirectoryConfigType>,Marshal::ModifierList<>>>,Marshal::Details::JsonTypeData,Marshal::Details::JsonTypeInfo>::Value
0x1400cd5a8  mov     [rbp+4Fh+var_48], rcx
0x1400cd5ac  mov     [rbp+4Fh+var_40], rax
0x1400cd5b0  add     rax, 20h ; ' '
0x1400cd5b4  mov     [rbp+4Fh+var_38], rax
0x1400cd5b8  lea     rax, [rbp+4Fh+var_60]
0x1400cd5bc  mov     [rsp+0B0h+var_88], rax
0x1400cd5c1  lea     rax, [rbp+4Fh+var_50]
0x1400cd5c5  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x1400cd5ca  lea     r9, [rbp+4Fh+var_40]
0x1400cd5ce  lea     r8, [rbp+4Fh+var_28]
0x1400cd5d2  mov     rdx, rsi
0x1400cd5d5  lea     rcx, [rbp+4Fh+var_30]
0x1400cd5d9  call    ?WriteObjectXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::WriteObjectXml(Marshal::XmlWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x1400cd5de  mov     rcx, [rbp+4Fh+var_30]
0x1400cd5e2  mov     rax, [rcx]
0x1400cd5e5  mov     rax, [rax+78h]
0x1400cd5e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cd5ee  mov     rcx, [rbp+57h]; this
0x1400cd5f2  test    eax, eax
0x1400cd5f4  js      loc_1400CD751
0x1400cd5fa  mov     rax, [rdi]
0x1400cd5fd  mov     rcx, rdi
0x1400cd600  mov     rax, [rax+0F8h]
0x1400cd607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cd60c  mov     rcx, [rbp+57h]; this
0x1400cd610  test    eax, eax
0x1400cd612  js      loc_1400CD6A9
0x1400cd618  mov     rcx, [rbp+4Fh+ppvObject]
0x1400cd61c  test    rcx, rcx
0x1400cd61f  jz      short loc_1400CD62E
0x1400cd621  mov     rax, [rcx]
0x1400cd624  mov     rax, [rax+10h]
0x1400cd628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cd62d  nop
0x1400cd62e  mov     rcx, [rbp+4Fh+pOutputStream]
0x1400cd632  xorps   xmm0, xmm0
0x1400cd635  movups  xmmword ptr [rbx], xmm0
0x1400cd638  mov     qword ptr [rbx+10h], 0
0x1400cd640  mov     qword ptr [rbx+18h], 0
0x1400cd648  movups  xmm0, xmmword ptr [rcx+10h]
0x1400cd64c  movups  xmmword ptr [rbx], xmm0
0x1400cd64f  movups  xmm1, xmmword ptr [rcx+20h]
0x1400cd653  movups  xmmword ptr [rbx+10h], xmm1
0x1400cd657  mov     qword ptr [rcx+20h], 0
0x1400cd65f  mov     qword ptr [rcx+28h], 7
0x1400cd667  xor     eax, eax
0x1400cd669  mov     [rcx+10h], ax
0x1400cd66d  mov     rcx, [rbp+4Fh+pOutputStream]
0x1400cd671  test    rcx, rcx
0x1400cd674  jz      short loc_1400CD687
0x1400cd676  mov     [rbp+4Fh+pOutputStream], rax
0x1400cd67a  mov     rdx, [rcx]
0x1400cd67d  mov     rax, [rdx+10h]
0x1400cd681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cd686  nop
0x1400cd687  mov     rax, rbx
0x1400cd68a  mov     rcx, [rbp+4Fh+var_18]
0x1400cd68e  xor     rcx, rsp; StackCookie
0x1400cd691  call    __security_check_cookie
0x1400cd696  mov     rbx, [rsp+0B0h+arg_10]
0x1400cd69e  add     rsp, 0A0h
0x1400cd6a5  pop     rdi
0x1400cd6a6  pop     rsi
0x1400cd6a7  pop     rbp
0x1400cd6a8  retn
0x1400cd6a9  mov     r9d, eax; char *
0x1400cd6ac  lea     r8, aOnecoreVmCommo_9; "onecore\\vm\\common\\marshal\\inc\\Mars"...
0x1400cd6b3  mov     edx, 502h; void *
0x1400cd6b8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cd6be  mov     r9d, eax; char *
0x1400cd6c1  lea     r8, aOnecoreVmCommo_9; "onecore\\vm\\common\\marshal\\inc\\Mars"...
0x1400cd6c8  mov     edx, 42Bh; void *
0x1400cd6cd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cd6d3  mov     r9d, eax; char *
0x1400cd6d6  lea     r8, aOnecoreVmCommo_9; "onecore\\vm\\common\\marshal\\inc\\Mars"...
0x1400cd6dd  mov     edx, 42Eh; void *
0x1400cd6e2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cd6e8  mov     r9d, eax; char *
0x1400cd6eb  lea     r8, aOnecoreVmCommo_9; "onecore\\vm\\common\\marshal\\inc\\Mars"...
0x1400cd6f2  mov     edx, 42Fh; void *
0x1400cd6f7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cd6fd  mov     r9d, eax; char *
0x1400cd700  lea     r8, aOnecoreVmCommo_9; "onecore\\vm\\common\\marshal\\inc\\Mars"...
0x1400cd707  mov     edx, 431h; void *
0x1400cd70c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cd712  mov     r9d, eax; char *
0x1400cd715  lea     r8, aOnecoreVmCommo_9; "onecore\\vm\\common\\marshal\\inc\\Mars"...
0x1400cd71c  mov     edx, 433h; void *
0x1400cd721  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cd727  mov     r9d, eax; char *
0x1400cd72a  lea     r8, aOnecoreVmCommo_9; "onecore\\vm\\common\\marshal\\inc\\Mars"...
0x1400cd731  mov     edx, 434h; void *
0x1400cd736  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cd73c  mov     r9d, eax; char *
0x1400cd73f  lea     r8, aOnecoreVmCommo_9; "onecore\\vm\\common\\marshal\\inc\\Mars"...
0x1400cd746  mov     edx, 1E3h; void *
0x1400cd74b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cd751  mov     r9d, eax; char *
0x1400cd754  lea     r8, aOnecoreVmCommo_9; "onecore\\vm\\common\\marshal\\inc\\Mars"...
0x1400cd75b  mov     edx, 1EFh; void *
0x1400cd760  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
