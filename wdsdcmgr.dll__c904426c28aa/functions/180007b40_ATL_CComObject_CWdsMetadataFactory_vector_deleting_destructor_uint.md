# ATL::CComObject<CWdsMetadataFactory>::`vector deleting destructor'(uint)

- ea: `0x180007b40`
- end: `0x180007b9b`
- name: `??_E?$CComObject@VCWdsMetadataFactory@@@ATL@@UEAAPEAXI@Z`
- size: `91`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180007b40`
- `0x1800150b8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180007b79`
- `KERNEL32!DeleteCriticalSection` at `0x180007b79`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<CWdsMetadataFactory>::`vector deleting destructor'(_DWORD *Block, char a2)
{
  struct _RTL_CRITICAL_SECTION *v3; // rcx

  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CWdsMetadataFactory>::`vftable';
  v3 = (struct _RTL_CRITICAL_SECTION *)(Block + 4);
  _InterlockedDecrement((volatile signed __int32 *)ATL::_pAtlModule + 3);
  if ( LOBYTE(v3[1].DebugInfo) )
  {
    LOBYTE(v3[1].DebugInfo) = 0;
    DeleteCriticalSection(v3);
  }
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180007b40  mov     [rsp+arg_0], rbx
0x180007b45  push    rdi
0x180007b46  sub     rsp, 20h
0x180007b4a  mov     dword ptr [rcx+8], 0C0000001h
0x180007b51  lea     rax, ??_7?$CComObject@VCWdsMetadataFactory@@@ATL@@6B@; const ATL::CComObject<CWdsMetadataFactory>::`vftable'
0x180007b58  mov     [rcx], rax
0x180007b5b  mov     rbx, rcx
0x180007b5e  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007b65  add     rcx, 10h; lpCriticalSection
0x180007b69  mov     edi, edx
0x180007b6b  lock dec dword ptr [rax+0Ch]
0x180007b6f  cmp     byte ptr [rcx+28h], 0
0x180007b73  jz      short loc_180007B7F
0x180007b75  mov     byte ptr [rcx+28h], 0
0x180007b79  call    cs:__imp_DeleteCriticalSection
0x180007b7f  test    dil, 1
0x180007b83  jz      short loc_180007B8D
0x180007b85  mov     rcx, rbx; Block
0x180007b88  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007b8d  mov     rax, rbx
0x180007b90  mov     rbx, [rsp+28h+arg_0]
0x180007b95  add     rsp, 20h
0x180007b99  pop     rdi
0x180007b9a  retn
```
