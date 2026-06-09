# CSWbemObject::Delete_(long,IDispatch *)

- ea: `0x18002b310`
- end: `0x18002b399`
- name: `?Delete_@CSWbemObject@@UEAAJJPEAUIDispatch@@@Z`
- size: `137`
- prototype: `__int64 __fastcall(CSWbemObject *__hidden this, int, struct IDispatch *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180006300`
- `0x180019980`
- `0x180024774`
- `0x18002b310`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002b374`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b374`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSWbemObject::Delete_(CSWbemObject *this, unsigned int a2, struct IDispatch *a3)
{
  int v6; // ebx
  struct IWbemClassObject *v7; // rcx
  CWbemDispatchMgr *v8; // rcx
  BSTR bstrString; // [rsp+60h] [rbp+8h] BYREF

  v6 = -2147217407;
  ResetLastErrors();
  if ( !*((_QWORD *)this + 7) )
    goto LABEL_6;
  v7 = (struct IWbemClassObject *)*((_QWORD *)this + 8);
  if ( !v7 )
    goto LABEL_6;
  bstrString = 0;
  if ( CSWbemObjectPath::GetObjectPath(v7, (struct ATL::CComBSTR *)&bstrString) )
    v6 = (*(__int64 (__fastcall **)(_QWORD, BSTR, _QWORD, struct IDispatch *))(**((_QWORD **)this + 7) + 72LL))(
           *((_QWORD *)this + 7),
           bstrString,
           a2,
           a3);
  SysFreeString(bstrString);
  if ( v6 < 0 )
  {
LABEL_6:
    v8 = (CWbemDispatchMgr *)*((_QWORD *)this + 9);
    if ( v8 )
      CWbemDispatchMgr::RaiseException(v8, v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002b310  push    rbx
0x18002b312  push    rbp
0x18002b313  push    rsi
0x18002b314  push    rdi
0x18002b315  sub     rsp, 38h
0x18002b319  mov     rsi, r8
0x18002b31c  mov     ebp, edx
0x18002b31e  mov     rdi, rcx
0x18002b321  mov     ebx, 80041001h
0x18002b326  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x18002b32b  cmp     qword ptr [rdi+38h], 0
0x18002b330  jz      short loc_18002B37E
0x18002b332  mov     rcx, [rdi+40h]; struct IWbemClassObject *
0x18002b336  test    rcx, rcx
0x18002b339  jz      short loc_18002B37E
0x18002b33b  mov     [rsp+58h+bstrString], 0
0x18002b344  lea     rdx, [rsp+58h+bstrString]; struct ATL::CComBSTR *
0x18002b349  call    ?GetObjectPath@CSWbemObjectPath@@SA_NPEAUIWbemClassObject@@AEAVCComBSTR@ATL@@@Z; CSWbemObjectPath::GetObjectPath(IWbemClassObject *,ATL::CComBSTR &)
0x18002b34e  test    al, al
0x18002b350  jz      short loc_18002B36F
0x18002b352  mov     rcx, [rdi+38h]
0x18002b356  mov     rax, [rcx]
0x18002b359  mov     r9, rsi
0x18002b35c  mov     r8d, ebp
0x18002b35f  mov     rdx, [rsp+58h+bstrString]
0x18002b364  mov     rax, [rax+48h]
0x18002b368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b36d  mov     ebx, eax
0x18002b36f  mov     rcx, [rsp+58h+bstrString]; bstrString
0x18002b374  call    cs:__imp_SysFreeString
0x18002b37a  test    ebx, ebx
0x18002b37c  jns     short loc_18002B38E
0x18002b37e  mov     rcx, [rdi+48h]; this
0x18002b382  test    rcx, rcx
0x18002b385  jz      short loc_18002B38E
0x18002b387  mov     edx, ebx; int
0x18002b389  call    ?RaiseException@CWbemDispatchMgr@@QEAAXJ@Z; CWbemDispatchMgr::RaiseException(long)
0x18002b38e  mov     eax, ebx
0x18002b390  add     rsp, 38h
0x18002b394  pop     rdi
0x18002b395  pop     rsi
0x18002b396  pop     rbp
0x18002b397  pop     rbx
0x18002b398  retn
```
