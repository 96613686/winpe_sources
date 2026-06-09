# IASService::get_RemoteServers(IIASItemsCollection * *)

- ea: `0x1800335b0`
- end: `0x1800336bf`
- name: `?get_RemoteServers@IASService@@UEAAJPEAPEAUIIASItemsCollection@@@Z`
- size: `271`
- prototype: `__int64 __fastcall(IASService *__hidden this, struct IIASItemsCollection **)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x18002cd00`
- `0x18002ee50`
- `0x18002f434`
- `0x180032304`
- `0x1800335b0`
- `0x180042a80`

## string_xrefs

- `0x18003367a`: `Could not copy RemoteServerGroups to output pointer: 0x%x`

## pseudocode

```c
__int64 __fastcall IASService::get_RemoteServers(IASService *this, struct IIASItemsCollection **a2)
{
  char *v5; // rdi
  int ItemsCollection; // ebx
  int v7; // edx

  if ( !a2 )
    return 2147500035LL;
  v5 = (char *)this + 136;
  if ( *((_QWORD *)this + 17) )
    ATL::CComPtrBase<IIASItem>::Release((char *)this + 136);
  ItemsCollection = IASItem::GetItemsCollection((char *)this + 16, 1024, 3, v5);
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
    WppDbgPrint("Could not copy RemoteServerGroups to output pointer: 0x%x");
    v7 = 51;
  }
  else
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    {
      return (unsigned int)ItemsCollection;
    }
    WppDbgPrint("GetItemsCollection (PROPERTY_IAS_RADIUSSERVERGROUPS_COLLECTION, IASREMOTESERVERGROUP) failed with 0x%x");
    v7 = 50;
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
0x1800335b0  mov     [rsp+arg_0], rbx
0x1800335b5  mov     [rsp+arg_8], rsi
0x1800335ba  push    rdi
0x1800335bb  sub     rsp, 30h
0x1800335bf  mov     rsi, rdx
0x1800335c2  mov     rbx, rcx
0x1800335c5  test    rdx, rdx
0x1800335c8  jnz     short loc_1800335D4
0x1800335ca  mov     eax, 80004003h
0x1800335cf  jmp     loc_1800336AF
0x1800335d4  lea     rdi, [rcx+88h]
0x1800335db  cmp     qword ptr [rdi], 0
0x1800335df  jz      short loc_1800335E9
0x1800335e1  mov     rcx, rdi
0x1800335e4  call    ?Release@?$CComPtrBase@UIIASItem@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IIASItem>::Release(void)
0x1800335e9  lea     rcx, [rbx+10h]
0x1800335ed  mov     r9, rdi
0x1800335f0  mov     edx, 400h
0x1800335f5  mov     r8d, 3
0x1800335fb  call    ?GetItemsCollection@IASItem@@IEAAJKW4_ITEMTYPE@@PEAPEAUIIASItemsCollection@@@Z; IASItem::GetItemsCollection(ulong,_ITEMTYPE,IIASItemsCollection * *)
0x180033600  mov     ebx, eax
0x180033602  test    eax, eax
0x180033604  jns     short loc_180033645
0x180033606  mov     rax, cs:WPP_GLOBAL_Control
0x18003360d  lea     rcx, WPP_GLOBAL_Control
0x180033614  cmp     rax, rcx
0x180033617  jz      loc_1800336AD
0x18003361d  cmp     byte ptr [rax+19h], 2
0x180033621  jb      loc_1800336AD
0x180033627  test    dword ptr [rax+1Ch], 400h
0x18003362e  jz      short loc_1800336AD
0x180033630  mov     edx, ebx
0x180033632  lea     rcx, aGetitemscollec; "GetItemsCollection (PROPERTY_IAS_RADIUS"...
0x180033639  call    WppDbgPrint
0x18003363e  mov     edx, 32h ; '2'
0x180033643  jmp     short loc_18003368B
0x180033645  mov     rdx, rsi
0x180033648  mov     rcx, rdi
0x18003364b  call    ?CopyTo@?$CComPtrBase@UIIASItemsCollection@@@ATL@@QEAAJPEAPEAUIIASItemsCollection@@@Z; ATL::CComPtrBase<IIASItemsCollection>::CopyTo(IIASItemsCollection * *)
0x180033650  mov     ebx, eax
0x180033652  test    eax, eax
0x180033654  jns     short loc_1800336AD
0x180033656  mov     rax, cs:WPP_GLOBAL_Control
0x18003365d  lea     rcx, WPP_GLOBAL_Control
0x180033664  cmp     rax, rcx
0x180033667  jz      short loc_1800336AD
0x180033669  cmp     byte ptr [rax+19h], 2
0x18003366d  jb      short loc_1800336AD
0x18003366f  test    dword ptr [rax+1Ch], 400h
0x180033676  jz      short loc_1800336AD
0x180033678  mov     edx, ebx
0x18003367a  lea     rcx, aCouldNotCopyRe; "Could not copy RemoteServerGroups to ou"...
0x180033681  call    WppDbgPrint
0x180033686  mov     edx, 33h ; '3'
0x18003368b  mov     rcx, cs:WPP_GLOBAL_Control
0x180033692  lea     r9, aNpssdo; "NPSSDO"
0x180033699  lea     r8, WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids
0x1800336a0  mov     [rsp+38h+var_18], ebx
0x1800336a4  mov     rcx, [rcx+10h]
0x1800336a8  call    WPP_SF_sd
0x1800336ad  mov     eax, ebx
0x1800336af  mov     rbx, [rsp+38h+arg_0]
0x1800336b4  mov     rsi, [rsp+38h+arg_8]
0x1800336b9  add     rsp, 30h
0x1800336bd  pop     rdi
0x1800336be  retn
```
