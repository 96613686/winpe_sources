# IASService::get_ClientVendorCollection(IIASItemsCollection * *)

- ea: `0x180032ce0`
- end: `0x180032e97`
- name: `?get_ClientVendorCollection@IASService@@UEAAJPEAPEAUIIASItemsCollection@@@Z`
- size: `439`
- prototype: `__int64 __fastcall(IASService *__hidden this, struct IIASItemsCollection **)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x18002cd00`
- `0x18002f458`
- `0x180032304`
- `0x18003277c`
- `0x180032ce0`
- `0x180042a80`

## string_xrefs

- `0x180032da8`: `GetRADIUSProtocol failed with 0x%x`
- `0x180032d4d`: `Could not copy client vendors collection to output pointer: 0x%x`
- `0x180032e59`: `Could not copy client vendors collection to output pointer: 0x%x`

## pseudocode

```c
__int64 __fastcall IASService::get_ClientVendorCollection(IASService *this, struct IIASItemsCollection **a2)
{
  __int64 result; // rax
  char *v5; // rsi
  int ItemsCollection; // ebx
  int v7; // edx

  if ( !a2 )
    return 2147500035LL;
  v5 = (char *)this + 184;
  if ( !*((_QWORD *)this + 23) )
  {
    if ( *((_QWORD *)this + 18)
      || (ItemsCollection = IASService::GetRADIUSProtocol((struct ISdo **)this), ItemsCollection >= 0) )
    {
      ItemsCollection = IASItem::GetItemsCollection((char *)this + 16, *((_QWORD *)this + 18), 1030, 14, v5);
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
        WppDbgPrint("Could not copy client vendors collection to output pointer: 0x%x");
        v7 = 59;
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        {
          return (unsigned int)ItemsCollection;
        }
        WppDbgPrint("GetItemsCollection(PROPERTY_RADIUS_VENDORS_COLLECTION, IASCLIENTVENDOR) failed with 0x%x");
        v7 = 58;
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
      v7 = 57;
    }
    goto LABEL_25;
  }
  result = ATL::CComPtrBase<IIASItemsCollection>::CopyTo((char *)this + 184, a2);
  ItemsCollection = result;
  if ( (int)result >= 0 )
    return result;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("Could not copy client vendors collection to output pointer: 0x%x");
    v7 = 56;
LABEL_25:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      (unsigned int)WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids,
      (unsigned int)"NPSSDO",
      ItemsCollection);
  }
  return (unsigned int)ItemsCollection;
}

```

## disassembly

```asm
0x180032ce0  push    rbx
0x180032ce2  push    rbp
0x180032ce3  push    rsi
0x180032ce4  push    rdi
0x180032ce5  sub     rsp, 38h
0x180032ce9  mov     rbp, rdx
0x180032cec  mov     rdi, rcx
0x180032cef  test    rdx, rdx
0x180032cf2  jnz     short loc_180032CFE
0x180032cf4  mov     eax, 80004003h
0x180032cf9  jmp     loc_180032E8E
0x180032cfe  lea     rsi, [rcx+0B8h]
0x180032d05  cmp     qword ptr [rsi], 0
0x180032d09  jz      short loc_180032D63
0x180032d0b  mov     rcx, rsi
0x180032d0e  call    ?CopyTo@?$CComPtrBase@UIIASItemsCollection@@@ATL@@QEAAJPEAPEAUIIASItemsCollection@@@Z; ATL::CComPtrBase<IIASItemsCollection>::CopyTo(IIASItemsCollection * *)
0x180032d13  mov     ebx, eax
0x180032d15  test    eax, eax
0x180032d17  jns     loc_180032E8E
0x180032d1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180032d24  lea     rax, WPP_GLOBAL_Control
0x180032d2b  cmp     rcx, rax
0x180032d2e  jz      loc_180032E8C
0x180032d34  cmp     byte ptr [rcx+19h], 2
0x180032d38  jb      loc_180032E8C
0x180032d3e  test    dword ptr [rcx+1Ch], 400h
0x180032d45  jz      loc_180032E8C
0x180032d4b  mov     edx, ebx
0x180032d4d  lea     rcx, aCouldNotCopyCl; "Could not copy client vendors collectio"...
0x180032d54  call    WppDbgPrint
0x180032d59  mov     edx, 38h ; '8'
0x180032d5e  jmp     loc_180032E6A
0x180032d63  cmp     qword ptr [rcx+90h], 0
0x180032d6b  jnz     short loc_180032DBE
0x180032d6d  call    ?GetRADIUSProtocol@IASService@@QEAAJXZ; IASService::GetRADIUSProtocol(void)
0x180032d72  mov     ebx, eax
0x180032d74  test    eax, eax
0x180032d76  jns     short loc_180032DBE
0x180032d78  mov     rcx, cs:WPP_GLOBAL_Control
0x180032d7f  lea     rax, WPP_GLOBAL_Control
0x180032d86  cmp     rcx, rax
0x180032d89  jz      loc_180032E8C
0x180032d8f  cmp     byte ptr [rcx+19h], 2
0x180032d93  jb      loc_180032E8C
0x180032d99  test    dword ptr [rcx+1Ch], 400h
0x180032da0  jz      loc_180032E8C
0x180032da6  mov     edx, ebx
0x180032da8  lea     rcx, aGetradiusproto; "GetRADIUSProtocol failed with 0x%x"
0x180032daf  call    WppDbgPrint
0x180032db4  mov     edx, 39h ; '9'
0x180032db9  jmp     loc_180032E6A
0x180032dbe  mov     rdx, [rdi+90h]
0x180032dc5  lea     rcx, [rdi+10h]
0x180032dc9  mov     r9d, 0Eh
0x180032dcf  mov     [rsp+58h+var_38], rsi
0x180032dd4  mov     r8d, 406h
0x180032dda  call    ?GetItemsCollection@IASItem@@IEAAJPEAUISdo@@KW4_ITEMTYPE@@PEAPEAUIIASItemsCollection@@@Z; IASItem::GetItemsCollection(ISdo *,ulong,_ITEMTYPE,IIASItemsCollection * *)
0x180032ddf  mov     ebx, eax
0x180032de1  test    eax, eax
0x180032de3  jns     short loc_180032E24
0x180032de5  mov     rcx, cs:WPP_GLOBAL_Control
0x180032dec  lea     rax, WPP_GLOBAL_Control
0x180032df3  cmp     rcx, rax
0x180032df6  jz      loc_180032E8C
0x180032dfc  cmp     byte ptr [rcx+19h], 2
0x180032e00  jb      loc_180032E8C
0x180032e06  test    dword ptr [rcx+1Ch], 400h
0x180032e0d  jz      short loc_180032E8C
0x180032e0f  mov     edx, ebx
0x180032e11  lea     rcx, aGetitemscollec_3; "GetItemsCollection(PROPERTY_RADIUS_VEND"...
0x180032e18  call    WppDbgPrint
0x180032e1d  mov     edx, 3Ah ; ':'
0x180032e22  jmp     short loc_180032E6A
0x180032e24  mov     rdx, rbp
0x180032e27  mov     rcx, rsi
0x180032e2a  call    ?CopyTo@?$CComPtrBase@UIIASItemsCollection@@@ATL@@QEAAJPEAPEAUIIASItemsCollection@@@Z; ATL::CComPtrBase<IIASItemsCollection>::CopyTo(IIASItemsCollection * *)
0x180032e2f  mov     ebx, eax
0x180032e31  test    eax, eax
0x180032e33  jns     short loc_180032E8C
0x180032e35  mov     rcx, cs:WPP_GLOBAL_Control
0x180032e3c  lea     rax, WPP_GLOBAL_Control
0x180032e43  cmp     rcx, rax
0x180032e46  jz      short loc_180032E8C
0x180032e48  cmp     byte ptr [rcx+19h], 2
0x180032e4c  jb      short loc_180032E8C
0x180032e4e  test    dword ptr [rcx+1Ch], 400h
0x180032e55  jz      short loc_180032E8C
0x180032e57  mov     edx, ebx
0x180032e59  lea     rcx, aCouldNotCopyCl; "Could not copy client vendors collectio"...
0x180032e60  call    WppDbgPrint
0x180032e65  mov     edx, 3Bh ; ';'
0x180032e6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180032e71  lea     r9, aNpssdo; "NPSSDO"
0x180032e78  lea     r8, WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids
0x180032e7f  mov     dword ptr [rsp+58h+var_38], ebx
0x180032e83  mov     rcx, [rcx+10h]
0x180032e87  call    WPP_SF_sd
0x180032e8c  mov     eax, ebx
0x180032e8e  add     rsp, 38h
0x180032e92  pop     rdi
0x180032e93  pop     rsi
0x180032e94  pop     rbp
0x180032e95  pop     rbx
0x180032e96  retn
```
