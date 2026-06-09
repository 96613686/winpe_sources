# ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)

- ea: `0x180005150`
- end: `0x1800051a5`
- name: `??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAPEAXI@Z`
- size: `85`
- prototype: `_DWORD *__fastcall(_DWORD *Block, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005150`
- `0x18003002c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000517e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000517e`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(_DWORD *Block, char a2)
{
  struct _RTL_CRITICAL_SECTION *v3; // rcx

  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComClassFactory::`vftable';
  v3 = (struct _RTL_CRITICAL_SECTION *)(Block + 4);
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
0x180005150  mov     [rsp+arg_0], rbx
0x180005155  push    rdi
0x180005156  sub     rsp, 20h
0x18000515a  mov     dword ptr [rcx+8], 0C0000001h
0x180005161  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180005168  mov     [rcx], rax
0x18000516b  mov     rbx, rcx
0x18000516e  add     rcx, 10h; lpCriticalSection
0x180005172  mov     edi, edx
0x180005174  cmp     byte ptr [rcx+28h], 0
0x180005178  jz      short loc_180005184
0x18000517a  mov     byte ptr [rcx+28h], 0
0x18000517e  call    cs:__imp_DeleteCriticalSection
0x180005184  test    dil, 1
0x180005188  jz      short loc_180005197
0x18000518a  mov     edx, 48h ; 'H'
0x18000518f  mov     rcx, rbx; Block
0x180005192  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005197  mov     rax, rbx
0x18000519a  mov     rbx, [rsp+28h+arg_0]
0x18000519f  add     rsp, 20h
0x1800051a3  pop     rdi
0x1800051a4  retn
```
