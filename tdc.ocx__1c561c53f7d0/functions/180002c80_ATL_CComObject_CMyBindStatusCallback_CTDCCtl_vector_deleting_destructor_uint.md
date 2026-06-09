# ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::`vector deleting destructor'(uint)

- ea: `0x180002c80`
- end: `0x180002cf7`
- name: `??_E?$CComObject@V?$CMyBindStatusCallback@VCTDCCtl@@@@@ATL@@UEAAPEAXI@Z`
- size: `119`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001194`
- `0x18000279c`
- `0x180002c80`
- `0x180015010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::`vector deleting destructor'(
        _DWORD *Block,
        char a2)
{
  Block[8] = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::`vftable'{for `IBindStatusCallbackImpl<CTDCCtl>'};
  *((_QWORD *)Block + 1) = &ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::`vftable'{for `IHttpNegotiateImpl<CTDCCtl>'};
  *((_QWORD *)Block + 2) = &ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::`vftable'{for `IServiceProviderImpl<CTDCCtl>'};
  *((_QWORD *)Block + 3) = &ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::`vftable'{for `IAmTheTDCImpl<CTDCCtl>'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CMyBindStatusCallback<CTDCCtl>::~CMyBindStatusCallback<CTDCCtl>(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180002c80  mov     [rsp+arg_0], rbx
0x180002c85  push    rdi
0x180002c86  sub     rsp, 20h
0x180002c8a  mov     dword ptr [rcx+20h], 0C0000001h
0x180002c91  lea     rax, ??_7?$CComObject@V?$CMyBindStatusCallback@VCTDCCtl@@@@@ATL@@6B?$IBindStatusCallbackImpl@VCTDCCtl@@@@@; const ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::`vftable'{for `IBindStatusCallbackImpl<CTDCCtl>'}
0x180002c98  mov     [rcx], rax
0x180002c9b  mov     rdi, rcx
0x180002c9e  lea     rax, ??_7?$CComObject@V?$CMyBindStatusCallback@VCTDCCtl@@@@@ATL@@6B?$IHttpNegotiateImpl@VCTDCCtl@@@@@; const ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::`vftable'{for `IHttpNegotiateImpl<CTDCCtl>'}
0x180002ca5  mov     ebx, edx
0x180002ca7  mov     [rcx+8], rax
0x180002cab  lea     rax, ??_7?$CComObject@V?$CMyBindStatusCallback@VCTDCCtl@@@@@ATL@@6B?$IServiceProviderImpl@VCTDCCtl@@@@@; const ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::`vftable'{for `IServiceProviderImpl<CTDCCtl>'}
0x180002cb2  mov     [rcx+10h], rax
0x180002cb6  lea     rax, ??_7?$CComObject@V?$CMyBindStatusCallback@VCTDCCtl@@@@@ATL@@6B?$IAmTheTDCImpl@VCTDCCtl@@@@@; const ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::`vftable'{for `IAmTheTDCImpl<CTDCCtl>'}
0x180002cbd  mov     [rcx+18h], rax
0x180002cc1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002cc8  mov     rax, [rcx]
0x180002ccb  mov     rax, [rax+10h]
0x180002ccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cd4  mov     rcx, rdi
0x180002cd7  call    ??1?$CMyBindStatusCallback@VCTDCCtl@@@@QEAA@XZ; CMyBindStatusCallback<CTDCCtl>::~CMyBindStatusCallback<CTDCCtl>(void)
0x180002cdc  test    bl, 1
0x180002cdf  jz      short loc_180002CE9
0x180002ce1  mov     rcx, rdi; Block
0x180002ce4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002ce9  mov     rbx, [rsp+28h+arg_0]
0x180002cee  mov     rax, rdi
0x180002cf1  add     rsp, 20h
0x180002cf5  pop     rdi
0x180002cf6  retn
```
