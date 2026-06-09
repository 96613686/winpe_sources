# ATL::CComObject<CWdsDeviceManagementHelper>::`scalar deleting destructor'(uint)

- ea: `0x180008510`
- end: `0x18000856b`
- name: `??_G?$CComObject@VCWdsDeviceManagementHelper@@@ATL@@UEAAPEAXI@Z`
- size: `91`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180008510`
- `0x1800150b8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180008549`
- `KERNEL32!DeleteCriticalSection` at `0x180008549`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<CWdsDeviceManagementHelper>::`scalar deleting destructor'(_DWORD *Block, char a2)
{
  struct _RTL_CRITICAL_SECTION *v3; // rcx

  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CWdsDeviceManagementHelper>::`vftable';
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
0x180008510  mov     [rsp+arg_0], rbx
0x180008515  push    rdi
0x180008516  sub     rsp, 20h
0x18000851a  mov     dword ptr [rcx+8], 0C0000001h
0x180008521  lea     rax, ??_7?$CComObject@VCWdsDeviceManagementHelper@@@ATL@@6B@; const ATL::CComObject<CWdsDeviceManagementHelper>::`vftable'
0x180008528  mov     [rcx], rax
0x18000852b  mov     rbx, rcx
0x18000852e  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008535  add     rcx, 10h; lpCriticalSection
0x180008539  mov     edi, edx
0x18000853b  lock dec dword ptr [rax+0Ch]
0x18000853f  cmp     byte ptr [rcx+28h], 0
0x180008543  jz      short loc_18000854F
0x180008545  mov     byte ptr [rcx+28h], 0
0x180008549  call    cs:__imp_DeleteCriticalSection
0x18000854f  test    dil, 1
0x180008553  jz      short loc_18000855D
0x180008555  mov     rcx, rbx; Block
0x180008558  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000855d  mov     rax, rbx
0x180008560  mov     rbx, [rsp+28h+arg_0]
0x180008565  add     rsp, 20h
0x180008569  pop     rdi
0x18000856a  retn
```
