# ATL::CComObject<CWdsSimpleDeviceQueryResult>::`scalar deleting destructor'(uint)

- ea: `0x180006f00`
- end: `0x180006f7c`
- name: `??_G?$CComObject@VCWdsSimpleDeviceQueryResult@@@ATL@@UEAAPEAXI@Z`
- size: `124`
- prototype: `__int64 __fastcall(CWdsSimpleDeviceQueryResult *this)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800015d4`
- `0x1800058c0`
- `0x180006ea8`
- `0x180006f00`
- `0x18000d010`

## pseudocode

```c
CWdsSimpleDeviceQueryResult *__fastcall ATL::CComObject<CWdsSimpleDeviceQueryResult>::`scalar deleting destructor'(
        CWdsSimpleDeviceQueryResult *this,
        char a2)
{
  void *v3; // rcx

  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CWdsSimpleDeviceQueryResult>::`vftable';
  v3 = (void *)*((_QWORD *)this + 11);
  if ( v3 )
  {
    operator delete(v3);
    *((_QWORD *)this + 11) = 0;
  }
  CDynArray<unsigned short *,CDeallocateString>::Clear((char *)this + 64);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CWdsSimpleDeviceQueryResult::~CWdsSimpleDeviceQueryResult(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180006f00  mov     [rsp+arg_0], rbx
0x180006f05  push    rdi
0x180006f06  sub     rsp, 20h
0x180006f0a  lea     rax, ??_7?$CComObject@VCWdsSimpleDeviceQueryResult@@@ATL@@6B@; const ATL::CComObject<CWdsSimpleDeviceQueryResult>::`vftable'
0x180006f11  mov     dword ptr [rcx+8], 0C0000001h
0x180006f18  mov     [rcx], rax
0x180006f1b  mov     rbx, rcx
0x180006f1e  mov     rcx, [rcx+58h]; Block
0x180006f22  mov     edi, edx
0x180006f24  test    rcx, rcx
0x180006f27  jz      short loc_180006F36
0x180006f29  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006f2e  mov     qword ptr [rbx+58h], 0
0x180006f36  lea     rcx, [rbx+40h]
0x180006f3a  call    ?Clear@?$CDynArray@PEAGVCDeallocateString@@@@QEAAXXZ; CDynArray<ushort *,CDeallocateString>::Clear(void)
0x180006f3f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006f46  mov     rax, [rcx]
0x180006f49  mov     rax, [rax+10h]
0x180006f4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f52  mov     rcx, rbx; this
0x180006f55  call    ??1CWdsSimpleDeviceQueryResult@@QEAA@XZ; CWdsSimpleDeviceQueryResult::~CWdsSimpleDeviceQueryResult(void)
0x180006f5a  test    dil, 1
0x180006f5e  jz      short loc_180006F6D
0x180006f60  mov     edx, 90h
0x180006f65  mov     rcx, rbx; Block
0x180006f68  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006f6d  mov     rax, rbx
0x180006f70  mov     rbx, [rsp+28h+arg_0]
0x180006f75  add     rsp, 20h
0x180006f79  pop     rdi
0x180006f7a  retn
```
