# ATL::CComObject<CUpdatePolicyReader>::`vector deleting destructor'(uint)

- ea: `0x180005380`
- end: `0x1800053f3`
- name: `??_E?$CComObject@VCUpdatePolicyReader@@@ATL@@UEAAPEAXI@Z`
- size: `115`
- prototype: `char *__fastcall(char *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180005380`
- `0x18003002c`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800053cc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800053cc`

## pseudocode

```c
char *__fastcall ATL::CComObject<CUpdatePolicyReader>::`vector deleting destructor'(char *Block, char a2)
{
  *((_DWORD *)Block + 4) = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CUpdatePolicyReader>::`vftable'{for `IUpdatePolicyReader'};
  *((_QWORD *)Block + 1) = &ATL::CComObject<CUpdatePolicyReader>::`vftable'{for `ITaskHandler'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( Block[64] )
  {
    Block[64] = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 24));
  }
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180005380  mov     [rsp+arg_0], rbx
0x180005385  push    rdi
0x180005386  sub     rsp, 20h
0x18000538a  mov     dword ptr [rcx+10h], 0C0000001h
0x180005391  lea     rax, ??_7?$CComObject@VCUpdatePolicyReader@@@ATL@@6BIUpdatePolicyReader@@@; const ATL::CComObject<CUpdatePolicyReader>::`vftable'{for `IUpdatePolicyReader'}
0x180005398  mov     [rcx], rax
0x18000539b  mov     rbx, rcx
0x18000539e  lea     rax, ??_7?$CComObject@VCUpdatePolicyReader@@@ATL@@6BITaskHandler@@@; const ATL::CComObject<CUpdatePolicyReader>::`vftable'{for `ITaskHandler'}
0x1800053a5  mov     edi, edx
0x1800053a7  mov     [rcx+8], rax
0x1800053ab  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800053b2  mov     rax, [rcx]
0x1800053b5  mov     rax, [rax+10h]
0x1800053b9  call    _guard_dispatch_icall
0x1800053be  lea     rcx, [rbx+18h]; lpCriticalSection
0x1800053c2  cmp     byte ptr [rcx+28h], 0
0x1800053c6  jz      short loc_1800053D2
0x1800053c8  mov     byte ptr [rcx+28h], 0
0x1800053cc  call    cs:__imp_DeleteCriticalSection
0x1800053d2  test    dil, 1
0x1800053d6  jz      short loc_1800053E5
0x1800053d8  mov     edx, 48h ; 'H'
0x1800053dd  mov     rcx, rbx; Block
0x1800053e0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800053e5  mov     rax, rbx
0x1800053e8  mov     rbx, [rsp+28h+arg_0]
0x1800053ed  add     rsp, 20h
0x1800053f1  pop     rdi
0x1800053f2  retn
```
