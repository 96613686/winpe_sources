# ATL::CComObject<CFsrmPropertiesPropSheet>::`vector deleting destructor'(uint)

- ea: `0x1800121b0`
- end: `0x1800121ff`
- name: `??_E?$CComObject@VCFsrmPropertiesPropSheet@@@ATL@@UEAAPEAXI@Z`
- size: `79`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800121b0`
- `0x180020010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800121eb`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800121eb`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<CFsrmPropertiesPropSheet>::`vector deleting destructor'(_DWORD *a1, char a2)
{
  a1[2] = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CFsrmPropertiesPropSheet>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800121b0  mov     [rsp+arg_0], rbx
0x1800121b5  push    rdi
0x1800121b6  sub     rsp, 20h
0x1800121ba  mov     dword ptr [rcx+8], 0C0000001h
0x1800121c1  lea     rax, ??_7?$CComObject@VCFsrmPropertiesPropSheet@@@ATL@@6B@; const ATL::CComObject<CFsrmPropertiesPropSheet>::`vftable'
0x1800121c8  mov     [rcx], rax
0x1800121cb  mov     rdi, rcx
0x1800121ce  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800121d5  mov     ebx, edx
0x1800121d7  mov     rax, [rcx]
0x1800121da  mov     rax, [rax+10h]
0x1800121de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121e3  test    bl, 1
0x1800121e6  jz      short loc_1800121F1
0x1800121e8  mov     rcx, rdi
0x1800121eb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800121f1  mov     rbx, [rsp+28h+arg_0]
0x1800121f6  mov     rax, rdi
0x1800121f9  add     rsp, 20h
0x1800121fd  pop     rdi
0x1800121fe  retn
```
