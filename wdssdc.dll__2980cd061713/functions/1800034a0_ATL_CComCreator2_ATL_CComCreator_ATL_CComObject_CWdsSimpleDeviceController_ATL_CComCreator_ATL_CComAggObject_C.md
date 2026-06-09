# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CWdsSimpleDeviceController>>,ATL::CComCreator<ATL::CComAggObject<CWdsSimpleDeviceController>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800034a0`
- end: `0x180003583`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCWdsSimpleDeviceController@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCWdsSimpleDeviceController@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `227`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800018e4`
- `0x1800034a0`
- `0x18000358c`
- `0x1800038ec`
- `0x1800054bc`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CWdsSimpleDeviceController>>,ATL::CComCreator<ATL::CComAggObject<CWdsSimpleDeviceController>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int v5; // ebx
  char *v6; // rdi
  struct ATL::CAtlModule *v7; // rcx

  if ( a1 )
  {
    return (unsigned int)ATL::CComCreator<ATL::CComAggObject<CWdsSimpleDeviceController>>::CreateInstance();
  }
  else if ( a3 )
  {
    *a3 = 0;
    v6 = (char *)operator new(0x78u);
    CWdsSimpleDeviceController::CWdsSimpleDeviceController((CWdsSimpleDeviceController *)v6);
    v7 = ATL::_pAtlModule;
    *(_QWORD *)v6 = &ATL::CComObject<CWdsSimpleDeviceController>::`vftable'{for `IWdsDeviceQueryController'};
    *((_QWORD *)v6 + 1) = &ATL::CComObject<CWdsSimpleDeviceController>::`vftable'{for `IWdsDeviceManagementController'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v7 + 8LL))(v7);
    v5 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v6 + 24));
    if ( v5 < 0 || (v6[64] = 1, (v5 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v6)(v6, a2, a3)) != 0) )
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 1);
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800034a0  mov     rax, rsp
0x1800034a3  mov     [rax+8], rbx
0x1800034a7  mov     [rax+10h], rbp
0x1800034ab  mov     [rax+18h], rsi
0x1800034af  mov     [rax+20h], rdi
0x1800034b3  push    r14
0x1800034b5  sub     rsp, 20h
0x1800034b9  mov     rsi, r8
0x1800034bc  mov     rbp, rdx
0x1800034bf  test    rcx, rcx
0x1800034c2  jnz     loc_18000355E
0x1800034c8  test    r8, r8
0x1800034cb  jnz     short loc_1800034D7
0x1800034cd  mov     ebx, 80004003h
0x1800034d2  jmp     loc_180003565
0x1800034d7  mov     ecx, 78h ; 'x'; Size
0x1800034dc  mov     qword ptr [r8], 0
0x1800034e3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800034e8  mov     rcx, rax; this
0x1800034eb  mov     rdi, rax
0x1800034ee  call    ??0CWdsSimpleDeviceController@@QEAA@XZ; CWdsSimpleDeviceController::CWdsSimpleDeviceController(void)
0x1800034f3  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800034fa  lea     rax, ??_7?$CComObject@VCWdsSimpleDeviceController@@@ATL@@6BIWdsDeviceQueryController@@@; const ATL::CComObject<CWdsSimpleDeviceController>::`vftable'{for `IWdsDeviceQueryController'}
0x180003501  mov     [rdi], rax
0x180003504  lea     rax, ??_7?$CComObject@VCWdsSimpleDeviceController@@@ATL@@6BIWdsDeviceManagementController@@@; const ATL::CComObject<CWdsSimpleDeviceController>::`vftable'{for `IWdsDeviceManagementController'}
0x18000350b  mov     [rdi+8], rax
0x18000350f  mov     rax, [rcx]
0x180003512  mov     rax, [rax+8]
0x180003516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000351b  lea     rcx, [rdi+18h]; this
0x18000351f  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180003524  mov     ebx, eax
0x180003526  test    eax, eax
0x180003528  js      short loc_180003548
0x18000352a  mov     byte ptr [rdi+40h], 1
0x18000352e  mov     r8, rsi
0x180003531  mov     rax, [rdi]
0x180003534  mov     rdx, rbp
0x180003537  mov     rcx, rdi
0x18000353a  mov     rax, [rax]
0x18000353d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003542  mov     ebx, eax
0x180003544  test    eax, eax
0x180003546  jz      short loc_180003565
0x180003548  mov     rax, [rdi]
0x18000354b  mov     edx, 1
0x180003550  mov     rcx, rdi
0x180003553  mov     rax, [rax+30h]
0x180003557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000355c  jmp     short loc_180003565
0x18000355e  call    ?CreateInstance@?$CComCreator@V?$CComAggObject@VCWdsSimpleDeviceController@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CWdsSimpleDeviceController>>::CreateInstance(void *,_GUID const &,void * *)
0x180003563  mov     ebx, eax
0x180003565  mov     rbp, [rsp+28h+arg_8]
0x18000356a  mov     eax, ebx
0x18000356c  mov     rbx, [rsp+28h+arg_0]
0x180003571  mov     rsi, [rsp+28h+arg_10]
0x180003576  mov     rdi, [rsp+28h+arg_18]
0x18000357b  add     rsp, 20h
0x18000357f  pop     r14
0x180003581  retn
```
