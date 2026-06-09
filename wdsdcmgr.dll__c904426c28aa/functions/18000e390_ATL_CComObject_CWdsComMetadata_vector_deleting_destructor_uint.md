# ATL::CComObject<CWdsComMetadata>::`vector deleting destructor'(uint)

- ea: `0x18000e390`
- end: `0x18000e3db`
- name: `??_E?$CComObject@VCWdsComMetadata@@@ATL@@UEAAPEAXI@Z`
- size: `75`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000e390`
- `0x18000e4c4`
- `0x1800150b8`

## pseudocode

```c
CWdsComMetadataBuilder *__fastcall ATL::CComObject<CWdsComMetadata>::`vector deleting destructor'(
        CWdsComMetadataBuilder *Block,
        char a2)
{
  *((_DWORD *)Block + 2) = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CWdsComMetadata>::`vftable';
  _InterlockedDecrement((volatile signed __int32 *)ATL::_pAtlModule + 3);
  CWdsComMetadataBuilder::~CWdsComMetadataBuilder(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000e390  mov     [rsp+arg_0], rbx
0x18000e395  push    rdi
0x18000e396  sub     rsp, 20h
0x18000e39a  lea     rax, ??_7?$CComObject@VCWdsComMetadata@@@ATL@@6B@; const ATL::CComObject<CWdsComMetadata>::`vftable'
0x18000e3a1  mov     dword ptr [rcx+8], 0C0000001h
0x18000e3a8  mov     [rcx], rax
0x18000e3ab  mov     ebx, edx
0x18000e3ad  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000e3b4  mov     rdi, rcx
0x18000e3b7  lock dec dword ptr [rax+0Ch]
0x18000e3bb  call    ??1CWdsComMetadataBuilder@@QEAA@XZ; CWdsComMetadataBuilder::~CWdsComMetadataBuilder(void)
0x18000e3c0  test    bl, 1
0x18000e3c3  jz      short loc_18000E3CD
0x18000e3c5  mov     rcx, rdi; Block
0x18000e3c8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e3cd  mov     rax, rdi
0x18000e3d0  mov     rbx, [rsp+28h+arg_0]
0x18000e3d5  add     rsp, 20h
0x18000e3d9  pop     rdi
0x18000e3da  retn
```
