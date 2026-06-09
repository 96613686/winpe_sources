# ATL::CComObject<CWdsSimpleDeviceController>::`vector deleting destructor'(uint)

- ea: `0x180002860`
- end: `0x1800028cc`
- name: `??_E?$CComObject@VCWdsSimpleDeviceController@@@ATL@@UEAAPEAXI@Z`
- size: `108`
- prototype: `__int64 __fastcall(CWdsSimpleDeviceController *this)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800015d4`
- `0x180002860`
- `0x180005570`
- `0x180005c20`
- `0x18000d010`

## pseudocode

```c
CWdsSimpleDeviceController *__fastcall ATL::CComObject<CWdsSimpleDeviceController>::`vector deleting destructor'(
        CWdsSimpleDeviceController *this,
        char a2)
{
  *((_DWORD *)this + 4) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CWdsSimpleDeviceController>::`vftable'{for `IWdsDeviceQueryController'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CWdsSimpleDeviceController>::`vftable'{for `IWdsDeviceManagementController'};
  CWdsSimpleDeviceController::FinalRelease(this);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CWdsSimpleDeviceController::~CWdsSimpleDeviceController(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002860  mov     [rsp+arg_0], rbx
0x180002865  push    rdi
0x180002866  sub     rsp, 20h
0x18000286a  lea     rax, ??_7?$CComObject@VCWdsSimpleDeviceController@@@ATL@@6BIWdsDeviceQueryController@@@; const ATL::CComObject<CWdsSimpleDeviceController>::`vftable'{for `IWdsDeviceQueryController'}
0x180002871  mov     dword ptr [rcx+10h], 0C0000001h
0x180002878  mov     [rcx], rax
0x18000287b  mov     ebx, edx
0x18000287d  lea     rax, ??_7?$CComObject@VCWdsSimpleDeviceController@@@ATL@@6BIWdsDeviceManagementController@@@; const ATL::CComObject<CWdsSimpleDeviceController>::`vftable'{for `IWdsDeviceManagementController'}
0x180002884  mov     rdi, rcx
0x180002887  mov     [rcx+8], rax
0x18000288b  call    ?FinalRelease@CWdsSimpleDeviceController@@QEAAXXZ; CWdsSimpleDeviceController::FinalRelease(void)
0x180002890  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002897  mov     rax, [rcx]
0x18000289a  mov     rax, [rax+10h]
0x18000289e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028a3  mov     rcx, rdi; this
0x1800028a6  call    ??1CWdsSimpleDeviceController@@QEAA@XZ; CWdsSimpleDeviceController::~CWdsSimpleDeviceController(void)
0x1800028ab  test    bl, 1
0x1800028ae  jz      short loc_1800028BD
0x1800028b0  mov     edx, 78h ; 'x'
0x1800028b5  mov     rcx, rdi; Block
0x1800028b8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800028bd  mov     rbx, [rsp+28h+arg_0]
0x1800028c2  mov     rax, rdi
0x1800028c5  add     rsp, 20h
0x1800028c9  pop     rdi
0x1800028ca  retn
```
