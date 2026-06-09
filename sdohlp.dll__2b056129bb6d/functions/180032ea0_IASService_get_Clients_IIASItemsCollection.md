# IASService::get_Clients(IIASItemsCollection * *)

- ea: `0x180032ea0`
- end: `0x18003300a`
- name: `?get_Clients@IASService@@UEAAJPEAPEAUIIASItemsCollection@@@Z`
- size: `362`
- prototype: `__int64 __fastcall(IASService *__hidden this, struct IIASItemsCollection **)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x18002cd00`
- `0x18002ee50`
- `0x18002f458`
- `0x180032304`
- `0x18003277c`
- `0x180032ea0`
- `0x180042a80`

## string_xrefs

- `0x180032f1b`: `GetRADIUSProtocol failed with 0x%x`
- `0x180032fcc`: `Could not copy the clients collection to output pointer hr=0x%X`

## pseudocode

```c
__int64 __fastcall IASService::get_Clients(IASService *this, struct IIASItemsCollection **a2)
{
  char *v5; // rsi
  int ItemsCollection; // ebx
  int v7; // edx

  if ( !a2 )
    return 2147500035LL;
  v5 = (char *)this + 152;
  if ( *((_QWORD *)this + 19) )
    ATL::CComPtrBase<IIASItem>::Release((char *)this + 152);
  if ( *((_QWORD *)this + 18)
    || (ItemsCollection = IASService::GetRADIUSProtocol((struct ISdo **)this), ItemsCollection >= 0) )
  {
    ItemsCollection = IASItem::GetItemsCollection((char *)this + 16, *((_QWORD *)this + 18), 1029, 2, v5);
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
      WppDbgPrint("Could not copy the clients collection to output pointer hr=0x%X");
      v7 = 49;
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      {
        return (unsigned int)ItemsCollection;
      }
      WppDbgPrint("GetSdoCollection(PROPERTY_RADIUS_CLIENTS_COLLECTION) failed with 0x%x");
      v7 = 48;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    {
      return (unsigned int)ItemsCollection;
    }
    WppDbgPrint("GetRADIUSProtocol failed with 0x%x");
    v7 = 47;
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
0x180032ea0  push    rbx
0x180032ea2  push    rbp
0x180032ea3  push    rsi
0x180032ea4  push    rdi
0x180032ea5  sub     rsp, 38h
0x180032ea9  mov     rbp, rdx
0x180032eac  mov     rdi, rcx
0x180032eaf  test    rdx, rdx
0x180032eb2  jnz     short loc_180032EBE
0x180032eb4  mov     eax, 80004003h
0x180032eb9  jmp     loc_180033001
0x180032ebe  lea     rsi, [rcx+98h]
0x180032ec5  cmp     qword ptr [rsi], 0
0x180032ec9  jz      short loc_180032ED3
0x180032ecb  mov     rcx, rsi
0x180032ece  call    ?Release@?$CComPtrBase@UIIASItem@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IIASItem>::Release(void)
0x180032ed3  cmp     qword ptr [rdi+90h], 0
0x180032edb  jnz     short loc_180032F31
0x180032edd  mov     rcx, rdi; this
0x180032ee0  call    ?GetRADIUSProtocol@IASService@@QEAAJXZ; IASService::GetRADIUSProtocol(void)
0x180032ee5  mov     ebx, eax
0x180032ee7  test    eax, eax
0x180032ee9  jns     short loc_180032F31
0x180032eeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180032ef2  lea     rax, WPP_GLOBAL_Control
0x180032ef9  cmp     rcx, rax
0x180032efc  jz      loc_180032FFF
0x180032f02  cmp     byte ptr [rcx+19h], 2
0x180032f06  jb      loc_180032FFF
0x180032f0c  test    dword ptr [rcx+1Ch], 400h
0x180032f13  jz      loc_180032FFF
0x180032f19  mov     edx, ebx
0x180032f1b  lea     rcx, aGetradiusproto; "GetRADIUSProtocol failed with 0x%x"
0x180032f22  call    WppDbgPrint
0x180032f27  mov     edx, 2Fh ; '/'
0x180032f2c  jmp     loc_180032FDD
0x180032f31  mov     rdx, [rdi+90h]
0x180032f38  lea     rcx, [rdi+10h]
0x180032f3c  mov     r9d, 2
0x180032f42  mov     [rsp+58h+var_38], rsi
0x180032f47  mov     r8d, 405h
0x180032f4d  call    ?GetItemsCollection@IASItem@@IEAAJPEAUISdo@@KW4_ITEMTYPE@@PEAPEAUIIASItemsCollection@@@Z; IASItem::GetItemsCollection(ISdo *,ulong,_ITEMTYPE,IIASItemsCollection * *)
0x180032f52  mov     ebx, eax
0x180032f54  test    eax, eax
0x180032f56  jns     short loc_180032F97
0x180032f58  mov     rcx, cs:WPP_GLOBAL_Control
0x180032f5f  lea     rax, WPP_GLOBAL_Control
0x180032f66  cmp     rcx, rax
0x180032f69  jz      loc_180032FFF
0x180032f6f  cmp     byte ptr [rcx+19h], 2
0x180032f73  jb      loc_180032FFF
0x180032f79  test    dword ptr [rcx+1Ch], 400h
0x180032f80  jz      short loc_180032FFF
0x180032f82  mov     edx, ebx
0x180032f84  lea     rcx, aGetsdocollecti_3; "GetSdoCollection(PROPERTY_RADIUS_CLIENT"...
0x180032f8b  call    WppDbgPrint
0x180032f90  mov     edx, 30h ; '0'
0x180032f95  jmp     short loc_180032FDD
0x180032f97  mov     rdx, rbp
0x180032f9a  mov     rcx, rsi
0x180032f9d  call    ?CopyTo@?$CComPtrBase@UIIASItemsCollection@@@ATL@@QEAAJPEAPEAUIIASItemsCollection@@@Z; ATL::CComPtrBase<IIASItemsCollection>::CopyTo(IIASItemsCollection * *)
0x180032fa2  mov     ebx, eax
0x180032fa4  test    eax, eax
0x180032fa6  jns     short loc_180032FFF
0x180032fa8  mov     rcx, cs:WPP_GLOBAL_Control
0x180032faf  lea     rax, WPP_GLOBAL_Control
0x180032fb6  cmp     rcx, rax
0x180032fb9  jz      short loc_180032FFF
0x180032fbb  cmp     byte ptr [rcx+19h], 2
0x180032fbf  jb      short loc_180032FFF
0x180032fc1  test    dword ptr [rcx+1Ch], 400h
0x180032fc8  jz      short loc_180032FFF
0x180032fca  mov     edx, ebx
0x180032fcc  lea     rcx, aCouldNotCopyTh; "Could not copy the clients collection t"...
0x180032fd3  call    WppDbgPrint
0x180032fd8  mov     edx, 31h ; '1'
0x180032fdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180032fe4  lea     r9, aNpssdo; "NPSSDO"
0x180032feb  lea     r8, WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids
0x180032ff2  mov     dword ptr [rsp+58h+var_38], ebx
0x180032ff6  mov     rcx, [rcx+10h]
0x180032ffa  call    WPP_SF_sd
0x180032fff  mov     eax, ebx
0x180033001  add     rsp, 38h
0x180033005  pop     rdi
0x180033006  pop     rsi
0x180033007  pop     rbp
0x180033008  pop     rbx
0x180033009  retn
```
