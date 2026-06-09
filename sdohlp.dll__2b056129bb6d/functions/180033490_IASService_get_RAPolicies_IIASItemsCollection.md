# IASService::get_RAPolicies(IIASItemsCollection * *)

- ea: `0x180033490`
- end: `0x18003359c`
- name: `?get_RAPolicies@IASService@@UEAAJPEAPEAUIIASItemsCollection@@@Z`
- size: `268`
- prototype: `__int64 __fastcall(IASService *__hidden this, struct IIASItemsCollection **)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x18002cd00`
- `0x18002ee50`
- `0x18002f434`
- `0x180032304`
- `0x180033490`
- `0x180042a80`

## string_xrefs

- `0x180033557`: `Could not copy RAPolicies to output pointer: 0x%x`

## pseudocode

```c
__int64 __fastcall IASService::get_RAPolicies(IASService *this, struct IIASItemsCollection **a2)
{
  char *v5; // rdi
  int ItemsCollection; // ebx
  int v7; // edx

  if ( !a2 )
    return 2147500035LL;
  v5 = (char *)this + 120;
  if ( *((_QWORD *)this + 15) )
    ATL::CComPtrBase<IIASItem>::Release((char *)this + 120);
  ItemsCollection = IASItem::GetItemsCollection((char *)this + 16, 1025, 9, v5);
  if ( ItemsCollection >= 0 )
  {
    ItemsCollection = ATL::CComPtrBase<IIASItemsCollection>::CopyTo(v5, a2);
    if ( ItemsCollection >= 0
      || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    {
      return (unsigned int)ItemsCollection;
    }
    WppDbgPrint("Could not copy RAPolicies to output pointer: 0x%x");
    v7 = 53;
  }
  else
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    {
      return (unsigned int)ItemsCollection;
    }
    WppDbgPrint("GetItemsCollection(PROPERTY_IAS_POLICIES_COLLECTION, IASRAPOLICY) failed with 0x%x");
    v7 = 52;
  }
  WPP_SF_sd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v7,
    (unsigned int)WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids,
    (unsigned int)"NPSSDO",
    ItemsCollection);
  return (unsigned int)ItemsCollection;
}

```

## disassembly

```asm
0x180033490  mov     [rsp+arg_0], rbx
0x180033495  mov     [rsp+arg_8], rsi
0x18003349a  push    rdi
0x18003349b  sub     rsp, 30h
0x18003349f  mov     rsi, rdx
0x1800334a2  mov     rbx, rcx
0x1800334a5  test    rdx, rdx
0x1800334a8  jnz     short loc_1800334B4
0x1800334aa  mov     eax, 80004003h
0x1800334af  jmp     loc_18003358C
0x1800334b4  lea     rdi, [rcx+78h]
0x1800334b8  cmp     qword ptr [rdi], 0
0x1800334bc  jz      short loc_1800334C6
0x1800334be  mov     rcx, rdi
0x1800334c1  call    ?Release@?$CComPtrBase@UIIASItem@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IIASItem>::Release(void)
0x1800334c6  lea     rcx, [rbx+10h]
0x1800334ca  mov     r9, rdi
0x1800334cd  mov     edx, 401h
0x1800334d2  mov     r8d, 9
0x1800334d8  call    ?GetItemsCollection@IASItem@@IEAAJKW4_ITEMTYPE@@PEAPEAUIIASItemsCollection@@@Z; IASItem::GetItemsCollection(ulong,_ITEMTYPE,IIASItemsCollection * *)
0x1800334dd  mov     ebx, eax
0x1800334df  test    eax, eax
0x1800334e1  jns     short loc_180033522
0x1800334e3  mov     rax, cs:WPP_GLOBAL_Control
0x1800334ea  lea     rcx, WPP_GLOBAL_Control
0x1800334f1  cmp     rax, rcx
0x1800334f4  jz      loc_18003358A
0x1800334fa  cmp     byte ptr [rax+19h], 2
0x1800334fe  jb      loc_18003358A
0x180033504  test    dword ptr [rax+1Ch], 400h
0x18003350b  jz      short loc_18003358A
0x18003350d  mov     edx, ebx
0x18003350f  lea     rcx, aGetitemscollec_2; "GetItemsCollection(PROPERTY_IAS_POLICIE"...
0x180033516  call    WppDbgPrint
0x18003351b  mov     edx, 34h ; '4'
0x180033520  jmp     short loc_180033568
0x180033522  mov     rdx, rsi
0x180033525  mov     rcx, rdi
0x180033528  call    ?CopyTo@?$CComPtrBase@UIIASItemsCollection@@@ATL@@QEAAJPEAPEAUIIASItemsCollection@@@Z; ATL::CComPtrBase<IIASItemsCollection>::CopyTo(IIASItemsCollection * *)
0x18003352d  mov     ebx, eax
0x18003352f  test    eax, eax
0x180033531  jns     short loc_18003358A
0x180033533  mov     rax, cs:WPP_GLOBAL_Control
0x18003353a  lea     rcx, WPP_GLOBAL_Control
0x180033541  cmp     rax, rcx
0x180033544  jz      short loc_18003358A
0x180033546  cmp     byte ptr [rax+19h], 2
0x18003354a  jb      short loc_18003358A
0x18003354c  test    dword ptr [rax+1Ch], 400h
0x180033553  jz      short loc_18003358A
0x180033555  mov     edx, ebx
0x180033557  lea     rcx, aCouldNotCopyRa; "Could not copy RAPolicies to output poi"...
0x18003355e  call    WppDbgPrint
0x180033563  mov     edx, 35h ; '5'
0x180033568  mov     rcx, cs:WPP_GLOBAL_Control
0x18003356f  lea     r9, aNpssdo; "NPSSDO"
0x180033576  lea     r8, WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids
0x18003357d  mov     [rsp+38h+var_18], ebx
0x180033581  mov     rcx, [rcx+10h]
0x180033585  call    WPP_SF_sd
0x18003358a  mov     eax, ebx
0x18003358c  mov     rbx, [rsp+38h+arg_0]
0x180033591  mov     rsi, [rsp+38h+arg_8]
0x180033596  add     rsp, 30h
0x18003359a  pop     rdi
0x18003359b  retn
```
