# IASService::get_CRPolicies(IIASItemsCollection * *)

- ea: `0x180032bc0`
- end: `0x180032ccf`
- name: `?get_CRPolicies@IASService@@UEAAJPEAPEAUIIASItemsCollection@@@Z`
- size: `271`
- prototype: `__int64 __fastcall(IASService *__hidden this, struct IIASItemsCollection **)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x18002cd00`
- `0x18002ee50`
- `0x18002f434`
- `0x180032304`
- `0x180032bc0`
- `0x180042a80`

## string_xrefs

- `0x180032c8a`: `Could not copy CRPolicies to output pointer: 0x%x`

## pseudocode

```c
__int64 __fastcall IASService::get_CRPolicies(IASService *this, struct IIASItemsCollection **a2)
{
  char *v5; // rdi
  int ItemsCollection; // ebx
  int v7; // edx

  if ( !a2 )
    return 2147500035LL;
  v5 = (char *)this + 128;
  if ( *((_QWORD *)this + 16) )
    ATL::CComPtrBase<IIASItem>::Release((char *)this + 128);
  ItemsCollection = IASItem::GetItemsCollection((char *)this + 16, 1030, 10, v5);
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
    WppDbgPrint("Could not copy CRPolicies to output pointer: 0x%x");
    v7 = 55;
  }
  else
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    {
      return (unsigned int)ItemsCollection;
    }
    WppDbgPrint("GetItemsCollection(PROPERTY_IAS_PROXYPOLICIES_COLLECTION, IASCRPOLICY) failed with 0x%x");
    v7 = 54;
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
0x180032bc0  mov     [rsp+arg_0], rbx
0x180032bc5  mov     [rsp+arg_8], rsi
0x180032bca  push    rdi
0x180032bcb  sub     rsp, 30h
0x180032bcf  mov     rsi, rdx
0x180032bd2  mov     rbx, rcx
0x180032bd5  test    rdx, rdx
0x180032bd8  jnz     short loc_180032BE4
0x180032bda  mov     eax, 80004003h
0x180032bdf  jmp     loc_180032CBF
0x180032be4  lea     rdi, [rcx+80h]
0x180032beb  cmp     qword ptr [rdi], 0
0x180032bef  jz      short loc_180032BF9
0x180032bf1  mov     rcx, rdi
0x180032bf4  call    ?Release@?$CComPtrBase@UIIASItem@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IIASItem>::Release(void)
0x180032bf9  lea     rcx, [rbx+10h]
0x180032bfd  mov     r9, rdi
0x180032c00  mov     edx, 406h
0x180032c05  mov     r8d, 0Ah
0x180032c0b  call    ?GetItemsCollection@IASItem@@IEAAJKW4_ITEMTYPE@@PEAPEAUIIASItemsCollection@@@Z; IASItem::GetItemsCollection(ulong,_ITEMTYPE,IIASItemsCollection * *)
0x180032c10  mov     ebx, eax
0x180032c12  test    eax, eax
0x180032c14  jns     short loc_180032C55
0x180032c16  mov     rax, cs:WPP_GLOBAL_Control
0x180032c1d  lea     rcx, WPP_GLOBAL_Control
0x180032c24  cmp     rax, rcx
0x180032c27  jz      loc_180032CBD
0x180032c2d  cmp     byte ptr [rax+19h], 2
0x180032c31  jb      loc_180032CBD
0x180032c37  test    dword ptr [rax+1Ch], 400h
0x180032c3e  jz      short loc_180032CBD
0x180032c40  mov     edx, ebx
0x180032c42  lea     rcx, aGetitemscollec_1; "GetItemsCollection(PROPERTY_IAS_PROXYPO"...
0x180032c49  call    WppDbgPrint
0x180032c4e  mov     edx, 36h ; '6'
0x180032c53  jmp     short loc_180032C9B
0x180032c55  mov     rdx, rsi
0x180032c58  mov     rcx, rdi
0x180032c5b  call    ?CopyTo@?$CComPtrBase@UIIASItemsCollection@@@ATL@@QEAAJPEAPEAUIIASItemsCollection@@@Z; ATL::CComPtrBase<IIASItemsCollection>::CopyTo(IIASItemsCollection * *)
0x180032c60  mov     ebx, eax
0x180032c62  test    eax, eax
0x180032c64  jns     short loc_180032CBD
0x180032c66  mov     rax, cs:WPP_GLOBAL_Control
0x180032c6d  lea     rcx, WPP_GLOBAL_Control
0x180032c74  cmp     rax, rcx
0x180032c77  jz      short loc_180032CBD
0x180032c79  cmp     byte ptr [rax+19h], 2
0x180032c7d  jb      short loc_180032CBD
0x180032c7f  test    dword ptr [rax+1Ch], 400h
0x180032c86  jz      short loc_180032CBD
0x180032c88  mov     edx, ebx
0x180032c8a  lea     rcx, aCouldNotCopyCr; "Could not copy CRPolicies to output poi"...
0x180032c91  call    WppDbgPrint
0x180032c96  mov     edx, 37h ; '7'
0x180032c9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180032ca2  lea     r9, aNpssdo; "NPSSDO"
0x180032ca9  lea     r8, WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids
0x180032cb0  mov     [rsp+38h+var_18], ebx
0x180032cb4  mov     rcx, [rcx+10h]
0x180032cb8  call    WPP_SF_sd
0x180032cbd  mov     eax, ebx
0x180032cbf  mov     rbx, [rsp+38h+arg_0]
0x180032cc4  mov     rsi, [rsp+38h+arg_8]
0x180032cc9  add     rsp, 30h
0x180032ccd  pop     rdi
0x180032cce  retn
```
