# ATL::CComAggObject<CWdsSimpleDeviceController>::`vector deleting destructor'(uint)

- ea: `0x1800027e0`
- end: `0x180002851`
- name: `??_E?$CComAggObject@VCWdsSimpleDeviceController@@@ATL@@UEAAPEAXI@Z`
- size: `113`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800015d4`
- `0x1800027e0`
- `0x180005570`
- `0x180005c20`
- `0x18000d010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComAggObject<CWdsSimpleDeviceController>::`vector deleting destructor'(_DWORD *Block, char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComAggObject<CWdsSimpleDeviceController>::`vftable';
  CWdsSimpleDeviceController::FinalRelease((CWdsSimpleDeviceController *)(Block + 6));
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CWdsSimpleDeviceController::~CWdsSimpleDeviceController((CWdsSimpleDeviceController *)(Block + 6));
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800027e0  mov     [rsp+arg_0], rbx
0x1800027e5  mov     [rsp+arg_8], rsi
0x1800027ea  push    rdi
0x1800027eb  sub     rsp, 20h
0x1800027ef  lea     rax, ??_7?$CComAggObject@VCWdsSimpleDeviceController@@@ATL@@6B@; const ATL::CComAggObject<CWdsSimpleDeviceController>::`vftable'
0x1800027f6  mov     dword ptr [rcx+8], 0C0000001h
0x1800027fd  mov     [rcx], rax
0x180002800  mov     rsi, rcx
0x180002803  add     rcx, 18h; this
0x180002807  mov     edi, edx
0x180002809  call    ?FinalRelease@CWdsSimpleDeviceController@@QEAAXXZ; CWdsSimpleDeviceController::FinalRelease(void)
0x18000280e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002815  mov     rax, [rcx]
0x180002818  mov     rax, [rax+10h]
0x18000281c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002821  lea     rcx, [rsi+18h]; this
0x180002825  call    ??1CWdsSimpleDeviceController@@QEAA@XZ; CWdsSimpleDeviceController::~CWdsSimpleDeviceController(void)
0x18000282a  test    dil, 1
0x18000282e  jz      short loc_18000283D
0x180002830  mov     edx, 90h
0x180002835  mov     rcx, rsi; Block
0x180002838  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000283d  mov     rbx, [rsp+28h+arg_0]
0x180002842  mov     rax, rsi
0x180002845  mov     rsi, [rsp+28h+arg_8]
0x18000284a  add     rsp, 20h
0x18000284e  pop     rdi
0x18000284f  retn
```
