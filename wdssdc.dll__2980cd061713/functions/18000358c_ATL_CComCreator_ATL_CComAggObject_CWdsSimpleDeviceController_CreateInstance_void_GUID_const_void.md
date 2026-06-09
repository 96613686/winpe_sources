# ATL::CComCreator<ATL::CComAggObject<CWdsSimpleDeviceController>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000358c`
- end: `0x180003677`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCWdsSimpleDeviceController@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800034a0`

## callees

- `0x1800018e4`
- `0x18000358c`
- `0x1800038ec`
- `0x1800054bc`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CWdsSimpleDeviceController>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  char *v7; // rdi
  struct ATL::CAtlModule *v8; // rcx
  int v9; // ebx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = (char *)operator new(0x90u);
  *((_DWORD *)v7 + 2) = 0;
  *(_QWORD *)v7 = &ATL::CComAggObject<CWdsSimpleDeviceController>::`vftable';
  CWdsSimpleDeviceController::CWdsSimpleDeviceController((CWdsSimpleDeviceController *)(v7 + 24));
  v8 = ATL::_pAtlModule;
  *((_QWORD *)v7 + 3) = &ATL::CComContainedObject<CWdsSimpleDeviceController>::`vftable'{for `IWdsDeviceQueryController'};
  *((_QWORD *)v7 + 4) = &ATL::CComContainedObject<CWdsSimpleDeviceController>::`vftable'{for `IWdsDeviceManagementController'};
  *((_QWORD *)v7 + 5) = a1;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v8 + 8LL))(v8);
  v9 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v7 + 48));
  if ( v9 < 0 || (v7[88] = 1, (v9 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v7)(v7, a2, a3)) != 0) )
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v7 + 24LL))(v7, 1);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000358c  mov     rax, rsp
0x18000358f  mov     [rax+8], rbx
0x180003593  mov     [rax+10h], rbp
0x180003597  mov     [rax+18h], rsi
0x18000359b  mov     [rax+20h], rdi
0x18000359f  push    r14
0x1800035a1  sub     rsp, 20h
0x1800035a5  mov     rsi, r8
0x1800035a8  mov     rbp, rdx
0x1800035ab  mov     r14, rcx
0x1800035ae  test    r8, r8
0x1800035b1  jnz     short loc_1800035BD
0x1800035b3  mov     eax, 80004003h
0x1800035b8  jmp     loc_18000365B
0x1800035bd  mov     ecx, 90h; Size
0x1800035c2  mov     qword ptr [r8], 0
0x1800035c9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800035ce  mov     rdi, rax
0x1800035d1  mov     dword ptr [rax+8], 0
0x1800035d8  lea     rax, ??_7?$CComAggObject@VCWdsSimpleDeviceController@@@ATL@@6B@; const ATL::CComAggObject<CWdsSimpleDeviceController>::`vftable'
0x1800035df  lea     rcx, [rdi+18h]; this
0x1800035e3  mov     [rdi], rax
0x1800035e6  call    ??0CWdsSimpleDeviceController@@QEAA@XZ; CWdsSimpleDeviceController::CWdsSimpleDeviceController(void)
0x1800035eb  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800035f2  lea     rax, ??_7?$CComContainedObject@VCWdsSimpleDeviceController@@@ATL@@6BIWdsDeviceQueryController@@@; const ATL::CComContainedObject<CWdsSimpleDeviceController>::`vftable'{for `IWdsDeviceQueryController'}
0x1800035f9  mov     [rdi+18h], rax
0x1800035fd  lea     rax, ??_7?$CComContainedObject@VCWdsSimpleDeviceController@@@ATL@@6BIWdsDeviceManagementController@@@; const ATL::CComContainedObject<CWdsSimpleDeviceController>::`vftable'{for `IWdsDeviceManagementController'}
0x180003604  mov     [rdi+20h], rax
0x180003608  mov     [rdi+28h], r14
0x18000360c  mov     rdx, [rcx]
0x18000360f  mov     rax, [rdx+8]
0x180003613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003618  lea     rcx, [rdi+30h]; this
0x18000361c  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180003621  mov     ebx, eax
0x180003623  test    eax, eax
0x180003625  js      short loc_180003645
0x180003627  mov     byte ptr [rdi+58h], 1
0x18000362b  mov     r8, rsi
0x18000362e  mov     rax, [rdi]
0x180003631  mov     rdx, rbp
0x180003634  mov     rcx, rdi
0x180003637  mov     rax, [rax]
0x18000363a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000363f  mov     ebx, eax
0x180003641  test    eax, eax
0x180003643  jz      short loc_180003659
0x180003645  mov     rax, [rdi]
0x180003648  mov     edx, 1
0x18000364d  mov     rcx, rdi
0x180003650  mov     rax, [rax+18h]
0x180003654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003659  mov     eax, ebx
0x18000365b  mov     rbx, [rsp+28h+arg_0]
0x180003660  mov     rbp, [rsp+28h+arg_8]
0x180003665  mov     rsi, [rsp+28h+arg_10]
0x18000366a  mov     rdi, [rsp+28h+arg_18]
0x18000366f  add     rsp, 20h
0x180003673  pop     r14
0x180003675  retn
```
