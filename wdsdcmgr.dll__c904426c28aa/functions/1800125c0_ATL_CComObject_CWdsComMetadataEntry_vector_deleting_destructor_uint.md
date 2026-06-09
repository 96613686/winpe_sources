# ATL::CComObject<CWdsComMetadataEntry>::`vector deleting destructor'(uint)

- ea: `0x1800125c0`
- end: `0x180012637`
- name: `??_E?$CComObject@VCWdsComMetadataEntry@@@ATL@@UEAAPEAXI@Z`
- size: `119`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180009838`
- `0x18000a380`
- `0x1800125c0`
- `0x1800150b8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180012610`
- `KERNEL32!DeleteCriticalSection` at `0x180012610`

## pseudocode

```c
char *__fastcall ATL::CComObject<CWdsComMetadataEntry>::`vector deleting destructor'(char *Block, char a2)
{
  *((_DWORD *)Block + 2) = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CWdsComMetadataEntry>::`vftable';
  _InterlockedDecrement((volatile signed __int32 *)ATL::_pAtlModule + 3);
  CWdsMetadataEntry::Shutdown((CWdsMetadataEntry *)(Block + 64));
  CWdsMetadataValue::Shutdown((CWdsMetadataValue *)(Block + 104));
  if ( Block[56] )
  {
    Block[56] = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 16));
  }
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800125c0  mov     [rsp+arg_0], rbx
0x1800125c5  mov     [rsp+arg_8], rsi
0x1800125ca  push    rdi
0x1800125cb  sub     rsp, 20h
0x1800125cf  mov     dword ptr [rcx+8], 0C0000001h
0x1800125d6  lea     rax, ??_7?$CComObject@VCWdsComMetadataEntry@@@ATL@@6B@; const ATL::CComObject<CWdsComMetadataEntry>::`vftable'
0x1800125dd  mov     [rcx], rax
0x1800125e0  mov     rdi, rcx
0x1800125e3  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800125ea  add     rcx, 40h ; '@'; this
0x1800125ee  mov     esi, edx
0x1800125f0  lock dec dword ptr [rax+0Ch]
0x1800125f4  call    ?Shutdown@CWdsMetadataEntry@@QEAAXXZ; CWdsMetadataEntry::Shutdown(void)
0x1800125f9  lea     rcx, [rdi+68h]; this
0x1800125fd  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x180012602  lea     rcx, [rdi+10h]; lpCriticalSection
0x180012606  cmp     byte ptr [rcx+28h], 0
0x18001260a  jz      short loc_180012616
0x18001260c  mov     byte ptr [rcx+28h], 0
0x180012610  call    cs:__imp_DeleteCriticalSection
0x180012616  test    sil, 1
0x18001261a  jz      short loc_180012624
0x18001261c  mov     rcx, rdi; Block
0x18001261f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012624  mov     rbx, [rsp+28h+arg_0]
0x180012629  mov     rax, rdi
0x18001262c  mov     rsi, [rsp+28h+arg_8]
0x180012631  add     rsp, 20h
0x180012635  pop     rdi
0x180012636  retn
```
