# xp::XmlReader::OpenInputFileWithEncodingCodePage(wchar_t const *,uint,bool,wchar_t const *)

- ea: `0x1800390c8`
- end: `0x18003917b`
- name: `?OpenInputFileWithEncodingCodePage@XmlReader@xp@@QEAAJPEB_WI_N0@Z`
- size: `179`
- prototype: `int(xp::XmlReader *__hidden this, const wchar_t *, unsigned int, bool, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180039000`

## callees

- `0x180035288`
- `0x1800390c8`
- `0x18004c010`

## import_xrefs

- `XmlLite!CreateXmlReaderInputWithEncodingCodePage` at `0x180039127`
- `XmlLite!CreateXmlReaderInputWithEncodingCodePage` at `0x180039127`

## pseudocode

```c
__int64 __fastcall xp::XmlReader::OpenInputFileWithEncodingCodePage(
        xp::XmlReader *this,
        const wchar_t *a2,
        __int64 a3,
        __int64 a4,
        IXmlReaderInput *ppInput)
{
  signed int FileStream; // edi
  IUnknown *v7; // rbx
  IUnknown *pInputStream; // [rsp+30h] [rbp-18h] BYREF

  pInputStream = 0;
  FileStream = xp::XmlReader::CreateFileStream(a2, (struct IStream **)&pInputStream);
  if ( FileStream >= 0 )
  {
    ppInput = 0;
    v7 = pInputStream;
    FileStream = CreateXmlReaderInputWithEncodingCodePage(pInputStream, 0, 0x4E4u, 0, 0, &ppInput);
    ((void (__fastcall *)(IUnknown *))v7->lpVtbl->Release)(v7);
    if ( FileStream >= 0 )
    {
      FileStream = (*(__int64 (__fastcall **)(xp::XmlReader *, IXmlReaderInput *))(*(_QWORD *)this + 24LL))(
                     this,
                     ppInput);
      ((void (__fastcall *)(IXmlReaderInput *))ppInput->lpVtbl->Release)(ppInput);
    }
  }
  return (unsigned int)FileStream;
}

```

## disassembly

```asm
0x1800390c8  mov     r11, rsp
0x1800390cb  mov     [r11+8], rbx
0x1800390cf  mov     [r11+10h], rsi
0x1800390d3  push    rdi
0x1800390d4  sub     rsp, 40h
0x1800390d8  mov     rax, rdx
0x1800390db  mov     rsi, rcx
0x1800390de  mov     qword ptr [r11-18h], 0
0x1800390e6  lea     rdx, [r11-18h]; struct IStream **
0x1800390ea  mov     rcx, rax; wchar_t *
0x1800390ed  call    ?CreateFileStream@XmlReader@xp@@SAJPEB_WPEAPEAUIStream@@@Z; xp::XmlReader::CreateFileStream(wchar_t const *,IStream * *)
0x1800390f2  mov     edi, eax
0x1800390f4  test    eax, eax
0x1800390f6  js      short loc_180039169
0x1800390f8  mov     [rsp+48h+arg_20], 0
0x180039101  lea     rax, [rsp+48h+arg_20]
0x180039106  mov     [rsp+48h+ppInput], rax; ppInput
0x18003910b  mov     [rsp+48h+pwszBaseUri], 0; pwszBaseUri
0x180039114  xor     r9d, r9d; fEncodingHint
0x180039117  xor     edx, edx; pMalloc
0x180039119  mov     r8d, 4E4h; nEncodingCodePage
0x18003911f  mov     rbx, [rsp+48h+pInputStream]
0x180039124  mov     rcx, rbx; pInputStream
0x180039127  call    cs:__imp_CreateXmlReaderInputWithEncodingCodePage
0x18003912d  mov     edi, eax
0x18003912f  mov     rax, [rbx]
0x180039132  mov     rcx, rbx
0x180039135  mov     rax, [rax+10h]
0x180039139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003913e  test    edi, edi
0x180039140  js      short loc_180039169
0x180039142  mov     rax, [rsi]
0x180039145  mov     rdx, [rsp+48h+arg_20]
0x18003914a  mov     rcx, rsi
0x18003914d  mov     rax, [rax+18h]
0x180039151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039156  mov     edi, eax
0x180039158  mov     rcx, [rsp+48h+arg_20]
0x18003915d  mov     rax, [rcx]
0x180039160  mov     rax, [rax+10h]
0x180039164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039169  mov     eax, edi
0x18003916b  mov     rbx, [rsp+48h+arg_0]
0x180039170  mov     rsi, [rsp+48h+arg_8]
0x180039175  add     rsp, 40h
0x180039179  pop     rdi
0x18003917a  retn
```
