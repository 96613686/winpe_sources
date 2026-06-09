# ATL::CComAggObject<CFsrmPropertiesPropSheet>::`scalar deleting destructor'(uint)

- ea: `0x180012150`
- end: `0x18001219f`
- name: `??_G?$CComAggObject@VCFsrmPropertiesPropSheet@@@ATL@@UEAAPEAXI@Z`
- size: `79`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180012150`
- `0x180020010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001218b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001218b`

## pseudocode

```c
_DWORD *__fastcall ATL::CComAggObject<CFsrmPropertiesPropSheet>::`scalar deleting destructor'(_DWORD *a1, char a2)
{
  a1[2] = -1073741823;
  *(_QWORD *)a1 = &ATL::CComAggObject<CFsrmPropertiesPropSheet>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180012150  mov     [rsp+arg_0], rbx
0x180012155  push    rdi
0x180012156  sub     rsp, 20h
0x18001215a  mov     dword ptr [rcx+8], 0C0000001h
0x180012161  lea     rax, ??_7?$CComAggObject@VCFsrmPropertiesPropSheet@@@ATL@@6B@; const ATL::CComAggObject<CFsrmPropertiesPropSheet>::`vftable'
0x180012168  mov     [rcx], rax
0x18001216b  mov     rdi, rcx
0x18001216e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180012175  mov     ebx, edx
0x180012177  mov     rax, [rcx]
0x18001217a  mov     rax, [rax+10h]
0x18001217e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012183  test    bl, 1
0x180012186  jz      short loc_180012191
0x180012188  mov     rcx, rdi
0x18001218b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180012191  mov     rbx, [rsp+28h+arg_0]
0x180012196  mov     rax, rdi
0x180012199  add     rsp, 20h
0x18001219d  pop     rdi
0x18001219e  retn
```
