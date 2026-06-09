# XmlReader::OpenInputFile(wchar_t const *,long *)

- ea: `0x180039000`
- end: `0x1800390c2`
- name: `?OpenInputFile@XmlReader@@QEAAXPEB_WPEAJ@Z`
- size: `194`
- prototype: `void __fastcall(XmlReader *__hidden this, const wchar_t *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18003a680`

## callees

- `0x18001ee78`
- `0x180035288`
- `0x180039000`
- `0x1800390c8`
- `0x18003a6d8`
- `0x18004c010`

## string_xrefs

- `0x1800390a7`: `OpenInputFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall XmlReader::OpenInputFile(xp::XmlReader **this, const wchar_t *a2, int *a3)
{
  xp::XmlReader *v6; // r15
  int v7; // edi
  __int64 v8; // r8
  __int64 v9; // r9
  struct IStream *v10; // rbx
  IXmlReaderInput *v11; // [rsp+20h] [rbp-48h]
  struct IStream *v12; // [rsp+70h] [rbp+8h] BYREF

  v6 = *this;
  v12 = 0;
  v7 = xp::XmlReader::CreateFileStream(a2, &v12);
  if ( v7 >= 0 )
  {
    v10 = v12;
    v7 = (*(__int64 (__fastcall **)(xp::XmlReader *, struct IStream *))(*(_QWORD *)v6 + 24LL))(v6, v12);
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v10 + 16LL))(v10);
  }
  if ( v7 >= 0 )
    v7 = ReadToElement(*this);
  *a3 = 0;
  if ( v7 == -1072897938 || (unsigned int)(v7 + 1072894462) <= 2 )
  {
    *a3 = v7;
    v7 = xp::XmlReader::OpenInputFileWithEncodingCodePage(*this, a2, v8, v9, v11);
    if ( v7 >= 0 )
      v7 = ReadToElement(*this);
  }
  XmlReader::ThrowIfFailed((XmlReader *)this, "OpenInputFile", v7);
}

```

## disassembly

```asm
0x180039000  push    rbx
0x180039002  push    rbp
0x180039003  push    rsi
0x180039004  push    rdi
0x180039005  push    r14
0x180039007  push    r15
0x180039009  sub     rsp, 38h
0x18003900d  mov     r14, r8
0x180039010  mov     rbp, rdx
0x180039013  mov     rsi, rcx
0x180039016  mov     r15, [rcx]
0x180039019  mov     [rsp+68h+arg_0], 0
0x180039022  lea     rdx, [rsp+68h+arg_0]; struct IStream **
0x180039027  mov     rcx, rbp; wchar_t *
0x18003902a  call    ?CreateFileStream@XmlReader@xp@@SAJPEB_WPEAPEAUIStream@@@Z; xp::XmlReader::CreateFileStream(wchar_t const *,IStream * *)
0x18003902f  mov     edi, eax
0x180039031  test    eax, eax
0x180039033  js      short loc_18003905E
0x180039035  mov     rax, [r15]
0x180039038  mov     rbx, [rsp+68h+arg_0]
0x18003903d  mov     rdx, rbx
0x180039040  mov     rcx, r15
0x180039043  mov     rax, [rax+18h]
0x180039047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003904c  mov     edi, eax
0x18003904e  mov     rax, [rbx]
0x180039051  mov     rcx, rbx
0x180039054  mov     rax, [rax+10h]
0x180039058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003905d  nop
0x18003905e  test    edi, edi
0x180039060  js      short loc_18003906C
0x180039062  mov     rcx, [rsi]; this
0x180039065  call    ReadToElement
0x18003906a  mov     edi, eax
0x18003906c  mov     dword ptr [r14], 0
0x180039073  cmp     edi, 0C00CE06Eh
0x180039079  jz      short loc_180039086
0x18003907b  lea     eax, [rdi+3FF311FEh]
0x180039081  cmp     eax, 2
0x180039084  ja      short loc_1800390A4
0x180039086  mov     [r14], edi
0x180039089  mov     rdx, rbp; wchar_t *
0x18003908c  mov     rcx, [rsi]; this
0x18003908f  call    ?OpenInputFileWithEncodingCodePage@XmlReader@xp@@QEAAJPEB_WI_N0@Z; xp::XmlReader::OpenInputFileWithEncodingCodePage(wchar_t const *,uint,bool,wchar_t const *)
0x180039094  mov     edi, eax
0x180039096  test    eax, eax
0x180039098  js      short loc_1800390A4
0x18003909a  mov     rcx, [rsi]; this
0x18003909d  call    ReadToElement
0x1800390a2  mov     edi, eax
0x1800390a4  mov     r8d, edi; int
0x1800390a7  lea     rdx, aOpeninputfile; "OpenInputFile"
0x1800390ae  mov     rcx, rsi; this
0x1800390b1  add     rsp, 38h
0x1800390b5  pop     r15
0x1800390b7  pop     r14
0x1800390b9  pop     rdi
0x1800390ba  pop     rsi
0x1800390bb  pop     rbp
0x1800390bc  pop     rbx
0x1800390bd  jmp     ?ThrowIfFailed@XmlReader@@AEBAXPEBDJ@Z; XmlReader::ThrowIfFailed(char const *,long)
```
