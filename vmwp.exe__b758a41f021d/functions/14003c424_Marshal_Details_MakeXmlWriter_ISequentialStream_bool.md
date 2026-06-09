# Marshal::Details::MakeXmlWriter(ISequentialStream *,bool)

- ea: `0x14003c424`
- end: `0x14003c5d4`
- name: `?MakeXmlWriter@Details@Marshal@@YA?AV?$com_ptr_t@UIXmlWriter@@Uerr_exception_policy@wil@@@wil@@PEAUISequentialStream@@_N@Z`
- size: `432`
- prototype: `__int64 __fastcall(void **ppvObject, IUnknown *pOutputStream)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003c1e4`
- `0x14007076c`

## callees

- `0x14003c424`
- `0x140078628`
- `0x14011ea40`
- `0x1402cb010`

## import_xrefs

- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x14003c466`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x14003c466`
- `XmlLite!CreateXmlWriter` at `0x14003c4ac`
- `XmlLite!CreateXmlWriter` at `0x14003c4ac`

## string_xrefs

- `0x14003c47e`: `onecore\vm\common\marshal\inc\MarshalXml.h`
- `0x14003c4c4`: `onecore\vm\common\marshal\inc\MarshalXml.h`
- `0x14003c4f6`: `onecore\vm\common\marshal\inc\MarshalXml.h`
- `0x14003c52a`: `onecore\vm\common\marshal\inc\MarshalXml.h`
- `0x14003c560`: `onecore\vm\common\marshal\inc\MarshalXml.h`
- `0x14003c594`: `onecore\vm\common\marshal\inc\MarshalXml.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void **__fastcall Marshal::Details::MakeXmlWriter(void **ppvObject, IUnknown *pOutputStream)
{
  HRESULT v3; // eax
  HRESULT XmlWriter; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  IXmlWriterOutput *ppOutput; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  ppOutput = 0;
  v3 = CreateXmlWriterOutputWithEncodingName(pOutputStream, 0, L"UTF-16", &ppOutput);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x42B,
      (unsigned int)"onecore\\vm\\common\\marshal\\inc\\MarshalXml.h",
      (const char *)(unsigned int)v3,
      0);
  *ppvObject = 0;
  XmlWriter = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, ppvObject, 0);
  if ( XmlWriter < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x42E,
      (unsigned int)"onecore\\vm\\common\\marshal\\inc\\MarshalXml.h",
      (const char *)(unsigned int)XmlWriter,
      1);
  v5 = (*(__int64 (__fastcall **)(_QWORD, IXmlWriterOutput *))(*(_QWORD *)*ppvObject + 24LL))(*ppvObject, ppOutput);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x42F,
      (unsigned int)"onecore\\vm\\common\\marshal\\inc\\MarshalXml.h",
      (const char *)(unsigned int)v5,
      1);
  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*ppvObject + 40LL))(*ppvObject, 2);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x431,
      (unsigned int)"onecore\\vm\\common\\marshal\\inc\\MarshalXml.h",
      (const char *)(unsigned int)v6,
      1);
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*ppvObject + 40LL))(*ppvObject, 4, 1);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x433,
      (unsigned int)"onecore\\vm\\common\\marshal\\inc\\MarshalXml.h",
      (const char *)(unsigned int)v7,
      1);
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*ppvObject + 40LL))(*ppvObject, 1);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x434,
      (unsigned int)"onecore\\vm\\common\\marshal\\inc\\MarshalXml.h",
      (const char *)(unsigned int)v8,
      1);
  if ( ppOutput )
    ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
  return ppvObject;
}

```

## disassembly

```asm
0x14003c424  push    rbx
0x14003c426  sub     rsp, 40h
0x14003c42a  mov     rax, cs:__security_cookie
0x14003c431  xor     rax, rsp
0x14003c434  mov     [rsp+48h+var_10], rax
0x14003c439  mov     rax, rdx
0x14003c43c  mov     rbx, rcx
0x14003c43f  mov     [rsp+48h+var_20], rcx
0x14003c444  mov     [rsp+48h+var_28], 0; int
0x14003c44c  mov     [rsp+48h+ppOutput], 0
0x14003c455  lea     r9, [rsp+48h+ppOutput]; ppOutput
0x14003c45a  lea     r8, pwszEncodingName; "UTF-16"
0x14003c461  xor     edx, edx; pMalloc
0x14003c463  mov     rcx, rax; pOutputStream
0x14003c466  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x14003c46d  nop     dword ptr [rax+rax+00h]
0x14003c472  mov     rcx, [rsp+48h]; this
0x14003c477  test    eax, eax
0x14003c479  jns     short loc_14003C490
0x14003c47b  mov     r9d, eax; char *
0x14003c47e  lea     r8, aOnecoreVmCommo_71; "onecore\\vm\\common\\marshal\\inc\\Mars"...
0x14003c485  mov     edx, 42Bh; void *
0x14003c48a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14003c490  mov     [rsp+48h+var_28], 1; int
0x14003c498  mov     qword ptr [rbx], 0
0x14003c49f  xor     r8d, r8d; pMalloc
0x14003c4a2  mov     rdx, rbx; ppvObject
0x14003c4a5  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x14003c4ac  call    cs:__imp_CreateXmlWriter
0x14003c4b3  nop     dword ptr [rax+rax+00h]
0x14003c4b8  mov     rcx, [rsp+48h]; this
0x14003c4bd  test    eax, eax
0x14003c4bf  jns     short loc_14003C4D6
0x14003c4c1  mov     r9d, eax; char *
0x14003c4c4  lea     r8, aOnecoreVmCommo_71; "onecore\\vm\\common\\marshal\\inc\\Mars"...
0x14003c4cb  mov     edx, 42Eh; void *
0x14003c4d0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14003c4d6  mov     rcx, [rbx]
0x14003c4d9  mov     rax, [rcx]
0x14003c4dc  mov     rdx, [rsp+48h+ppOutput]
0x14003c4e1  mov     rax, [rax+18h]
0x14003c4e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c4ea  mov     rcx, [rsp+48h]; this
0x14003c4ef  test    eax, eax
0x14003c4f1  jns     short loc_14003C508
0x14003c4f3  mov     r9d, eax; char *
0x14003c4f6  lea     r8, aOnecoreVmCommo_71; "onecore\\vm\\common\\marshal\\inc\\Mars"...
0x14003c4fd  mov     edx, 42Fh; void *
0x14003c502  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14003c508  mov     rcx, [rbx]
0x14003c50b  mov     rax, [rcx]
0x14003c50e  xor     r8d, r8d
0x14003c511  lea     edx, [r8+2]
0x14003c515  mov     rax, [rax+28h]
0x14003c519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c51e  mov     rcx, [rsp+48h]; this
0x14003c523  test    eax, eax
0x14003c525  jns     short loc_14003C53C
0x14003c527  mov     r9d, eax; char *
0x14003c52a  lea     r8, aOnecoreVmCommo_71; "onecore\\vm\\common\\marshal\\inc\\Mars"...
0x14003c531  mov     edx, 431h; void *
0x14003c536  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14003c53c  mov     rcx, [rbx]
0x14003c53f  mov     rax, [rcx]
0x14003c542  mov     edx, 4
0x14003c547  lea     r8d, [rdx-3]
0x14003c54b  mov     rax, [rax+28h]
0x14003c54f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c554  mov     rcx, [rsp+48h]; this
0x14003c559  test    eax, eax
0x14003c55b  jns     short loc_14003C572
0x14003c55d  mov     r9d, eax; char *
0x14003c560  lea     r8, aOnecoreVmCommo_71; "onecore\\vm\\common\\marshal\\inc\\Mars"...
0x14003c567  mov     edx, 433h; void *
0x14003c56c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14003c572  mov     rcx, [rbx]
0x14003c575  mov     rax, [rcx]
0x14003c578  xor     r8d, r8d
0x14003c57b  lea     edx, [r8+1]
0x14003c57f  mov     rax, [rax+28h]
0x14003c583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c588  mov     rcx, [rsp+48h]; this
0x14003c58d  test    eax, eax
0x14003c58f  jns     short loc_14003C5A6
0x14003c591  mov     r9d, eax; char *
0x14003c594  lea     r8, aOnecoreVmCommo_71; "onecore\\vm\\common\\marshal\\inc\\Mars"...
0x14003c59b  mov     edx, 434h; void *
0x14003c5a0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14003c5a6  mov     rcx, [rsp+48h+ppOutput]
0x14003c5ab  test    rcx, rcx
0x14003c5ae  jz      short loc_14003C5BD
0x14003c5b0  mov     rdx, [rcx]
0x14003c5b3  mov     rax, [rdx+10h]
0x14003c5b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c5bc  nop
0x14003c5bd  mov     rax, rbx
0x14003c5c0  mov     rcx, [rsp+48h+var_10]
0x14003c5c5  xor     rcx, rsp; StackCookie
0x14003c5c8  call    __security_check_cookie
0x14003c5cd  add     rsp, 40h
0x14003c5d1  pop     rbx
0x14003c5d2  retn
```
