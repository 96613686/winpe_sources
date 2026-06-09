# ATL::CComObject<CWdsComMetadataBuilder>::`vector deleting destructor'(uint)

- ea: `0x180011450`
- end: `0x18001149b`
- name: `??_E?$CComObject@VCWdsComMetadataBuilder@@@ATL@@UEAAPEAXI@Z`
- size: `75`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000e4c4`
- `0x180011450`
- `0x1800150b8`

## pseudocode

```c
CWdsComMetadataBuilder *__fastcall ATL::CComObject<CWdsComMetadataBuilder>::`vector deleting destructor'(
        CWdsComMetadataBuilder *Block,
        char a2)
{
  *((_DWORD *)Block + 2) = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CWdsComMetadataBuilder>::`vftable';
  _InterlockedDecrement((volatile signed __int32 *)ATL::_pAtlModule + 3);
  CWdsComMetadataBuilder::~CWdsComMetadataBuilder(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180011450  mov     [rsp+arg_0], rbx
0x180011455  push    rdi
0x180011456  sub     rsp, 20h
0x18001145a  lea     rax, ??_7?$CComObject@VCWdsComMetadataBuilder@@@ATL@@6B@; const ATL::CComObject<CWdsComMetadataBuilder>::`vftable'
0x180011461  mov     dword ptr [rcx+8], 0C0000001h
0x180011468  mov     [rcx], rax
0x18001146b  mov     ebx, edx
0x18001146d  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011474  mov     rdi, rcx
0x180011477  lock dec dword ptr [rax+0Ch]
0x18001147b  call    ??1CWdsComMetadataBuilder@@QEAA@XZ; CWdsComMetadataBuilder::~CWdsComMetadataBuilder(void)
0x180011480  test    bl, 1
0x180011483  jz      short loc_18001148D
0x180011485  mov     rcx, rdi; Block
0x180011488  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001148d  mov     rax, rdi
0x180011490  mov     rbx, [rsp+28h+arg_0]
0x180011495  add     rsp, 20h
0x180011499  pop     rdi
0x18001149a  retn
```
