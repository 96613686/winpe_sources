# ATL::CComAggObject<CElevateWlanUi>::`vector deleting destructor'(uint)

- ea: `0x180002c70`
- end: `0x180002cd4`
- name: `??_E?$CComAggObject@VCElevateWlanUi@@@ATL@@UEAAPEAXI@Z`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002c70`
- `0x18001d010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002cc0`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002cc0`
- `KERNEL32!DeleteCriticalSection` at `0x180002cb1`
- `KERNEL32!DeleteCriticalSection` at `0x180002cb1`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall ATL::CComAggObject<CElevateWlanUi>::`vector deleting destructor'(
        struct _RTL_CRITICAL_SECTION *a1,
        char a2)
{
  a1->LockCount = -1073741823;
  a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComAggObject<CElevateWlanUi>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( LOBYTE(a1[2].DebugInfo) )
  {
    LOBYTE(a1[2].DebugInfo) = 0;
    DeleteCriticalSection(a1 + 1);
  }
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180002c70  mov     [rsp+arg_0], rbx
0x180002c75  push    rdi
0x180002c76  sub     rsp, 20h
0x180002c7a  mov     dword ptr [rcx+8], 0C0000001h
0x180002c81  lea     rax, ??_7?$CComAggObject@VCElevateWlanUi@@@ATL@@6B@; const ATL::CComAggObject<CElevateWlanUi>::`vftable'
0x180002c88  mov     [rcx], rax
0x180002c8b  mov     rbx, rcx
0x180002c8e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002c95  mov     edi, edx
0x180002c97  mov     rax, [rcx]
0x180002c9a  mov     rax, [rax+10h]
0x180002c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ca3  lea     rcx, [rbx+28h]; lpCriticalSection
0x180002ca7  cmp     byte ptr [rcx+28h], 0
0x180002cab  jz      short loc_180002CB7
0x180002cad  mov     byte ptr [rcx+28h], 0
0x180002cb1  call    cs:__imp_DeleteCriticalSection
0x180002cb7  test    dil, 1
0x180002cbb  jz      short loc_180002CC6
0x180002cbd  mov     rcx, rbx
0x180002cc0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002cc6  mov     rax, rbx
0x180002cc9  mov     rbx, [rsp+28h+arg_0]
0x180002cce  add     rsp, 20h
0x180002cd2  pop     rdi
0x180002cd3  retn
```
