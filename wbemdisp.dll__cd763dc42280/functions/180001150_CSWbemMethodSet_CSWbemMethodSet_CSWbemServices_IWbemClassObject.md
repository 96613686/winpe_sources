# CSWbemMethodSet::CSWbemMethodSet(CSWbemServices *,IWbemClassObject *)

- ea: `0x180001150`
- end: `0x1800012a8`
- name: `??0CSWbemMethodSet@@QEAA@PEAVCSWbemServices@@PEAUIWbemClassObject@@@Z`
- size: `344`
- prototype: `CSWbemMethodSet *__fastcall(CSWbemMethodSet *__hidden this, struct CSWbemServices *, struct IWbemClassObject *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800023b0`

## callees

- `0x180001150`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800011e2`
- `OLEAUT32!__imp_SysAllocString` at `0x1800011e2`
- `OLEAUT32!__imp_SysFreeString` at `0x180001277`
- `OLEAUT32!__imp_SysFreeString` at `0x180001277`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CSWbemMethodSet *__fastcall CSWbemMethodSet::CSWbemMethodSet(
        CSWbemMethodSet *this,
        struct CSWbemServices *a2,
        struct IWbemClassObject *a3)
{
  BSTR bstrString; // [rsp+48h] [rbp+10h] BYREF

  *(_QWORD *)this = &CSWbemMethodSet::`vftable'{for `ISWbemMethodSet'};
  *((_QWORD *)this + 1) = &CSWbemMethodSet::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 2) = &CSWbemMethodSet::`vftable'{for `IProvideClassInfo'};
  *((_QWORD *)this + 5) = &CDispatchHelp::`vftable';
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  *((_QWORD *)this + 10) = this;
  *(GUID *)((char *)this + 88) = IID_ISWbemMethodSet;
  *(GUID *)((char *)this + 104) = CLSID_SWbemMethodSet;
  *((_QWORD *)this + 6) = SysAllocString(L"SWbemMethodSet");
  *((_QWORD *)this + 4) = a3;
  ((void (__fastcall *)(struct IWbemClassObject *))a3->lpVtbl->AddRef)(a3);
  *((_QWORD *)this + 3) = a2;
  if ( a2 )
    (*(void (__fastcall **)(struct CSWbemServices *))(*(_QWORD *)a2 + 8LL))(a2);
  *((_DWORD *)this + 31) = 1;
  _InterlockedIncrement(&g_cObj);
  *((_DWORD *)this + 30) = 0;
  ((void (__fastcall *)(struct IWbemClassObject *, _QWORD))a3->lpVtbl->BeginMethodEnumeration)(a3, 0);
  bstrString = 0;
  while ( !((unsigned int (__fastcall *)(struct IWbemClassObject *, _QWORD, BSTR *, _QWORD, _QWORD))a3->lpVtbl->NextMethod)(
             a3,
             0,
             &bstrString,
             0,
             0) )
  {
    SysFreeString(bstrString);
    ++*((_DWORD *)this + 30);
  }
  ((void (__fastcall *)(struct IWbemClassObject *))a3->lpVtbl->EndMethodEnumeration)(a3);
  return this;
}

```

## disassembly

```asm
0x180001150  mov     [rsp+arg_10], rbx
0x180001155  mov     [rsp+arg_18], rsi
0x18000115a  mov     [rsp+arg_0], rcx
0x18000115f  push    rdi
0x180001160  sub     rsp, 30h
0x180001164  mov     rdi, r8
0x180001167  mov     rsi, rdx
0x18000116a  mov     rbx, rcx
0x18000116d  lea     rax, ??_7CSWbemMethodSet@@6BISWbemMethodSet@@@; const CSWbemMethodSet::`vftable'{for `ISWbemMethodSet'}
0x180001174  mov     [rcx], rax
0x180001177  lea     rax, ??_7CSWbemMethodSet@@6BISupportErrorInfo@@@; const CSWbemMethodSet::`vftable'{for `ISupportErrorInfo'}
0x18000117e  mov     [rcx+8], rax
0x180001182  lea     rax, ??_7CSWbemMethodSet@@6BIProvideClassInfo@@@; const CSWbemMethodSet::`vftable'{for `IProvideClassInfo'}
0x180001189  mov     [rcx+10h], rax
0x18000118d  lea     rax, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x180001194  mov     [rcx+28h], rax
0x180001198  mov     qword ptr [rcx+40h], 0
0x1800011a0  mov     qword ptr [rcx+48h], 0
0x1800011a8  mov     qword ptr [rcx+50h], 0
0x1800011b0  mov     qword ptr [rcx+30h], 0
0x1800011b8  mov     dword ptr [rcx+38h], 0
0x1800011bf  movups  xmm1, xmmword ptr cs:CLSID_SWbemMethodSet.Data1
0x1800011c6  movups  xmm0, xmmword ptr cs:IID_ISWbemMethodSet.Data1
0x1800011cd  mov     [rcx+50h], rcx
0x1800011d1  movdqu  xmmword ptr [rcx+58h], xmm0
0x1800011d6  movdqu  xmmword ptr [rcx+68h], xmm1
0x1800011db  lea     rcx, psz; "SWbemMethodSet"
0x1800011e2  call    cs:__imp_SysAllocString
0x1800011e8  mov     [rbx+30h], rax
0x1800011ec  mov     [rbx+20h], rdi
0x1800011f0  mov     rax, [rdi]
0x1800011f3  mov     rcx, rdi
0x1800011f6  mov     rax, [rax+8]
0x1800011fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011ff  mov     [rbx+18h], rsi
0x180001203  test    rsi, rsi
0x180001206  jz      short loc_180001217
0x180001208  mov     rax, [rsi]
0x18000120b  mov     rcx, rsi
0x18000120e  mov     rax, [rax+8]
0x180001212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001217  mov     dword ptr [rbx+7Ch], 1
0x18000121e  lock inc cs:?g_cObj@@3JA; long g_cObj
0x180001225  mov     dword ptr [rbx+78h], 0
0x18000122c  mov     rax, [rdi]
0x18000122f  xor     edx, edx
0x180001231  mov     rcx, rdi
0x180001234  mov     rax, [rax+0B0h]
0x18000123b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001240  mov     [rsp+38h+bstrString], 0
0x180001249  mov     rax, [rdi]
0x18000124c  mov     [rsp+38h+var_18], 0
0x180001255  xor     r9d, r9d
0x180001258  lea     r8, [rsp+38h+bstrString]
0x18000125d  xor     edx, edx
0x18000125f  mov     rcx, rdi
0x180001262  mov     rax, [rax+0B8h]
0x180001269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000126e  test    eax, eax
0x180001270  jnz     short loc_180001282
0x180001272  mov     rcx, [rsp+38h+bstrString]; bstrString
0x180001277  call    cs:__imp_SysFreeString
0x18000127d  inc     dword ptr [rbx+78h]
0x180001280  jmp     short loc_180001249
0x180001282  mov     rax, [rdi]
0x180001285  mov     rcx, rdi
0x180001288  mov     rax, [rax+0C0h]
0x18000128f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001294  nop
0x180001295  mov     rax, rbx
0x180001298  mov     rbx, [rsp+38h+arg_10]
0x18000129d  mov     rsi, [rsp+38h+arg_18]
0x1800012a2  add     rsp, 30h
0x1800012a6  pop     rdi
0x1800012a7  retn
```
