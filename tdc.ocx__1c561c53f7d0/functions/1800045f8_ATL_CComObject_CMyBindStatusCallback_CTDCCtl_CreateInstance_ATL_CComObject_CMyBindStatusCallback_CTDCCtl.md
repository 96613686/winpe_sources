# ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::CreateInstance(ATL::CComObject<CMyBindStatusCallback<CTDCCtl>> * *)

- ea: `0x1800045f8`
- end: `0x1800046c9`
- name: `?CreateInstance@?$CComObject@V?$CMyBindStatusCallback@VCTDCCtl@@@@@ATL@@SAJPEAPEAV12@@Z`
- size: `209`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006c40`

## callees

- `0x1800011b8`
- `0x1800045f8`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::CreateInstance(_QWORD *a1)
{
  __int64 result; // rax
  _DWORD *v3; // rax
  _DWORD *v4; // rbx
  struct ATL::CAtlModule *v5; // rcx
  int v6; // [rsp+2Ch] [rbp-Ch]

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = operator new(0x10C8u);
  v4 = v3;
  if ( v3 )
  {
    v5 = ATL::_pAtlModule;
    v3[8] = 0;
    *((_QWORD *)v3 + 5) = 0;
    *((_QWORD *)v3 + 6) = 0;
    *((_QWORD *)v3 + 7) = 0;
    *((_QWORD *)v3 + 8) = 0;
    *((_QWORD *)v3 + 9) = 0;
    *((_QWORD *)v3 + 10) = 0;
    *((_QWORD *)v3 + 534) = 0;
    v3[1070] = 0;
    *((_QWORD *)v3 + 533) = 0;
    v3[1071] = v6;
    *(_QWORD *)v3 = &ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::`vftable'{for `IBindStatusCallbackImpl<CTDCCtl>'};
    *((_QWORD *)v3 + 1) = &ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::`vftable'{for `IHttpNegotiateImpl<CTDCCtl>'};
    *((_QWORD *)v3 + 2) = &ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::`vftable'{for `IServiceProviderImpl<CTDCCtl>'};
    *((_QWORD *)v3 + 3) = &ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::`vftable'{for `IAmTheTDCImpl<CTDCCtl>'};
    v3[22] = 0;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v5 + 8LL))(v5);
    result = 0;
  }
  else
  {
    result = 2147942414LL;
    v4 = 0;
  }
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x1800045f8  mov     [rsp+arg_0], rbx
0x1800045fd  mov     [rsp+arg_8], rsi
0x180004602  push    rdi
0x180004603  sub     rsp, 30h
0x180004607  xor     esi, esi
0x180004609  mov     rdi, rcx
0x18000460c  test    rcx, rcx
0x18000460f  jnz     short loc_18000461B
0x180004611  mov     eax, 80004003h
0x180004616  jmp     loc_1800046B9
0x18000461b  mov     [rcx], rsi
0x18000461e  mov     ecx, 10C8h; Size
0x180004623  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004628  mov     rbx, rax
0x18000462b  test    rax, rax
0x18000462e  jz      short loc_1800046AE
0x180004630  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004637  mov     [rax+20h], esi
0x18000463a  mov     [rax+28h], rsi
0x18000463e  mov     [rax+30h], rsi
0x180004642  mov     [rax+38h], rsi
0x180004646  mov     [rax+40h], rsi
0x18000464a  mov     [rax+48h], rsi
0x18000464e  mov     [rax+50h], rsi
0x180004652  mov     [rax+10B0h], rsi
0x180004659  mov     [rax+10B8h], esi
0x18000465f  mov     [rax+10A8h], rsi
0x180004666  mov     eax, [rsp+38h+var_C]
0x18000466a  mov     [rbx+10BCh], eax
0x180004670  lea     rax, ??_7?$CComObject@V?$CMyBindStatusCallback@VCTDCCtl@@@@@ATL@@6B?$IBindStatusCallbackImpl@VCTDCCtl@@@@@; const ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::`vftable'{for `IBindStatusCallbackImpl<CTDCCtl>'}
0x180004677  mov     [rbx], rax
0x18000467a  lea     rax, ??_7?$CComObject@V?$CMyBindStatusCallback@VCTDCCtl@@@@@ATL@@6B?$IHttpNegotiateImpl@VCTDCCtl@@@@@; const ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::`vftable'{for `IHttpNegotiateImpl<CTDCCtl>'}
0x180004681  mov     [rbx+8], rax
0x180004685  lea     rax, ??_7?$CComObject@V?$CMyBindStatusCallback@VCTDCCtl@@@@@ATL@@6B?$IServiceProviderImpl@VCTDCCtl@@@@@; const ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::`vftable'{for `IServiceProviderImpl<CTDCCtl>'}
0x18000468c  mov     [rbx+10h], rax
0x180004690  lea     rax, ??_7?$CComObject@V?$CMyBindStatusCallback@VCTDCCtl@@@@@ATL@@6B?$IAmTheTDCImpl@VCTDCCtl@@@@@; const ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::`vftable'{for `IAmTheTDCImpl<CTDCCtl>'}
0x180004697  mov     [rbx+18h], rax
0x18000469b  mov     [rbx+58h], esi
0x18000469e  mov     rax, [rcx]
0x1800046a1  mov     rax, [rax+8]
0x1800046a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046aa  mov     eax, esi
0x1800046ac  jmp     short loc_1800046B6
0x1800046ae  mov     eax, 8007000Eh
0x1800046b3  mov     rbx, rsi
0x1800046b6  mov     [rdi], rbx
0x1800046b9  mov     rbx, [rsp+38h+arg_0]
0x1800046be  mov     rsi, [rsp+38h+arg_8]
0x1800046c3  add     rsp, 30h
0x1800046c7  pop     rdi
0x1800046c8  retn
```
