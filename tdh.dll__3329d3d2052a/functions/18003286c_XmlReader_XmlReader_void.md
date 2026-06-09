# XmlReader::XmlReader(void)

- ea: `0x18003286c`
- end: `0x1800328ed`
- name: `??0XmlReader@@QEAA@XZ`
- size: `129`
- prototype: `XmlReader *__fastcall(XmlReader *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800325cc`

## callees

- `0x18003286c`
- `0x18003be8c`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x180032891`
- `XmlLite!CreateXmlReader` at `0x180032891`

## string_xrefs

- `0x18003289b`: `CreateXmlReader failed`

## pseudocode

```c
XmlReader *__fastcall XmlReader::XmlReader(XmlReader *this)
{
  HRESULT v2; // eax
  XmlReader *result; // rax
  void *ppvObject; // [rsp+30h] [rbp+8h] BYREF

  ppvObject = 0;
  v2 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( v2 < 0 )
    ThrowWithPrintf(v2, "CreateXmlReader failed");
  *(_QWORD *)this = ppvObject;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 1) = &XmlReader::AppendStream::`vftable';
  result = this;
  *((_DWORD *)this + 10) = 0;
  *((_QWORD *)this + 6) = 0;
  return result;
}

```

## disassembly

```asm
0x18003286c  mov     [rsp+ppvObject], rcx
0x180032871  push    rbx
0x180032872  sub     rsp, 20h
0x180032876  mov     rbx, rcx
0x180032879  mov     [rsp+28h+ppvObject], 0
0x180032882  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x180032889  xor     r8d, r8d; pMalloc
0x18003288c  lea     rdx, [rsp+28h+ppvObject]; ppvObject
0x180032891  call    cs:__imp_CreateXmlReader
0x180032897  test    eax, eax
0x180032899  jns     short loc_1800328AA
0x18003289b  lea     rdx, aCreatexmlreade_1; "CreateXmlReader failed"
0x1800328a2  mov     ecx, eax; int
0x1800328a4  call    ?ThrowWithPrintf@@YAXJPEBDZZ; ThrowWithPrintf(long,char const *,...)
0x1800328aa  mov     rax, [rsp+28h+ppvObject]
0x1800328af  mov     [rbx], rax
0x1800328b2  lea     rax, ??_7AppendStream@XmlReader@@6B@; const XmlReader::AppendStream::`vftable'
0x1800328b9  mov     qword ptr [rbx+10h], 0
0x1800328c1  mov     qword ptr [rbx+18h], 0
0x1800328c9  mov     qword ptr [rbx+20h], 0
0x1800328d1  mov     [rbx+8], rax
0x1800328d5  mov     rax, rbx
0x1800328d8  mov     dword ptr [rbx+28h], 0
0x1800328df  mov     qword ptr [rbx+30h], 0
0x1800328e7  add     rsp, 20h
0x1800328eb  pop     rbx
0x1800328ec  retn
```
