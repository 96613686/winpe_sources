# ATL::CComObject<CUpdatePolicyPublisher>::`vector deleting destructor'(uint)

- ea: `0x180005310`
- end: `0x180005378`
- name: `??_E?$CComObject@VCUpdatePolicyPublisher@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `char *__fastcall(char *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x180005310`
- `0x18003002c`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005351`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005351`

## pseudocode

```c
char *__fastcall ATL::CComObject<CUpdatePolicyPublisher>::`vector deleting destructor'(char *Block, char a2)
{
  *((_DWORD *)Block + 2) = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CUpdatePolicyPublisher>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
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
0x180005310  mov     [rsp+arg_0], rbx
0x180005315  push    rdi
0x180005316  sub     rsp, 20h
0x18000531a  mov     dword ptr [rcx+8], 0C0000001h
0x180005321  lea     rax, ??_7?$CComObject@VCUpdatePolicyPublisher@@@ATL@@6B@; const ATL::CComObject<CUpdatePolicyPublisher>::`vftable'
0x180005328  mov     [rcx], rax
0x18000532b  mov     rbx, rcx
0x18000532e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005335  mov     edi, edx
0x180005337  mov     rax, [rcx]
0x18000533a  mov     rax, [rax+10h]
0x18000533e  call    _guard_dispatch_icall
0x180005343  lea     rcx, [rbx+10h]; lpCriticalSection
0x180005347  cmp     byte ptr [rcx+28h], 0
0x18000534b  jz      short loc_180005357
0x18000534d  mov     byte ptr [rcx+28h], 0
0x180005351  call    cs:__imp_DeleteCriticalSection
0x180005357  test    dil, 1
0x18000535b  jz      short loc_18000536A
0x18000535d  mov     edx, 40h ; '@'
0x180005362  mov     rcx, rbx; Block
0x180005365  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000536a  mov     rax, rbx
0x18000536d  mov     rbx, [rsp+28h+arg_0]
0x180005372  add     rsp, 20h
0x180005376  pop     rdi
0x180005377  retn
```
