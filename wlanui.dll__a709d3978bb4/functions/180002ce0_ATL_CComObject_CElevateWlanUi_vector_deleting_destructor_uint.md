# ATL::CComObject<CElevateWlanUi>::`vector deleting destructor'(uint)

- ea: `0x180002ce0`
- end: `0x180002d44`
- name: `??_E?$CComObject@VCElevateWlanUi@@@ATL@@UEAAPEAXI@Z`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002ce0`
- `0x18001d010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002d30`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002d30`
- `KERNEL32!DeleteCriticalSection` at `0x180002d21`
- `KERNEL32!DeleteCriticalSection` at `0x180002d21`

## pseudocode

```c
char *__fastcall ATL::CComObject<CElevateWlanUi>::`vector deleting destructor'(char *a1, char a2)
{
  *((_DWORD *)a1 + 2) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CElevateWlanUi>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( a1[56] )
  {
    a1[56] = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  }
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180002ce0  mov     [rsp+arg_0], rbx
0x180002ce5  push    rdi
0x180002ce6  sub     rsp, 20h
0x180002cea  mov     dword ptr [rcx+8], 0C0000001h
0x180002cf1  lea     rax, ??_7?$CComObject@VCElevateWlanUi@@@ATL@@6B@; const ATL::CComObject<CElevateWlanUi>::`vftable'
0x180002cf8  mov     [rcx], rax
0x180002cfb  mov     rbx, rcx
0x180002cfe  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002d05  mov     edi, edx
0x180002d07  mov     rax, [rcx]
0x180002d0a  mov     rax, [rax+10h]
0x180002d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d13  lea     rcx, [rbx+10h]; lpCriticalSection
0x180002d17  cmp     byte ptr [rcx+28h], 0
0x180002d1b  jz      short loc_180002D27
0x180002d1d  mov     byte ptr [rcx+28h], 0
0x180002d21  call    cs:__imp_DeleteCriticalSection
0x180002d27  test    dil, 1
0x180002d2b  jz      short loc_180002D36
0x180002d2d  mov     rcx, rbx
0x180002d30  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002d36  mov     rax, rbx
0x180002d39  mov     rbx, [rsp+28h+arg_0]
0x180002d3e  add     rsp, 20h
0x180002d42  pop     rdi
0x180002d43  retn
```
