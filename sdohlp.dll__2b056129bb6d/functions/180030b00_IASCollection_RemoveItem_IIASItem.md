# IASCollection::RemoveItem(IIASItem *)

- ea: `0x180030b00`
- end: `0x180030ce4`
- name: `?RemoveItem@IASCollection@@UEAAJPEAUIIASItem@@@Z`
- size: `484`
- prototype: `__int64 __fastcall(IASCollection *__hidden this, struct IIASItem *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18002fc70`

## callees

- `0x180024cac`
- `0x18002cd00`
- `0x1800308e8`
- `0x180030b00`
- `0x180042a80`
- `0x180058010`

## string_xrefs

- `0x180030b71`: `InternalRemoveItem failed with 0x%x`
- `0x180030c8b`: `m_pColl->Remove failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IASCollection::RemoveItem(IASCollection *this, struct IIASItem *a2)
{
  int v5; // ebx
  int v6; // edx
  __int64 v7; // [rsp+48h] [rbp+10h] BYREF
  __int64 (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp+18h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v8 = 0;
  v7 = 0;
  v5 = IASCollection::InternalRemoveItem(this, a2);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(struct IIASItem *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)a2 + 88LL))(
           a2,
           &v8);
    if ( v5 >= 0 )
    {
      v5 = (**v8)(v8, &IID_IDispatch, &v7);
      if ( v5 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 2) + 72LL))(*((_QWORD *)this + 2), v7);
        if ( v5 >= 0
          || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        {
          goto LABEL_24;
        }
        WppDbgPrint("m_pColl->Remove failed with 0x%x");
        v6 = 19;
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        {
          goto LABEL_24;
        }
        WppDbgPrint("pSdo->QueryInterface failed with 0x%x");
        v6 = 18;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      {
        goto LABEL_24;
      }
      WppDbgPrint("pItem->get_GetSdoObject failed with 0x%x");
      v6 = 17;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    {
      goto LABEL_24;
    }
    WppDbgPrint("InternalRemoveItem failed with 0x%x");
    v6 = 16;
  }
  WPP_SF_sd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v6,
    (unsigned int)WPP_c2f236718121324f7e73e45b18920f9d_Traceguids,
    (unsigned int)"NPSSDO",
    v5);
LABEL_24:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v7);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v8);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180030b00  mov     [rsp+arg_0], rbx
0x180030b05  mov     [rsp+arg_18], rsi
0x180030b0a  push    rdi
0x180030b0b  sub     rsp, 30h
0x180030b0f  mov     rdi, rdx
0x180030b12  mov     rsi, rcx
0x180030b15  test    rdx, rdx
0x180030b18  jnz     short loc_180030B24
0x180030b1a  mov     eax, 80004003h
0x180030b1f  jmp     loc_180030CD4
0x180030b24  mov     [rsp+38h+arg_10], 0
0x180030b2d  mov     [rsp+38h+arg_8], 0
0x180030b36  call    ?InternalRemoveItem@IASCollection@@QEAAJPEAUIIASItem@@@Z; IASCollection::InternalRemoveItem(IIASItem *)
0x180030b3b  mov     ebx, eax
0x180030b3d  test    eax, eax
0x180030b3f  jns     short loc_180030B87
0x180030b41  lea     rax, WPP_GLOBAL_Control
0x180030b48  mov     rcx, cs:WPP_GLOBAL_Control
0x180030b4f  cmp     rcx, rax
0x180030b52  jz      loc_180030CBE
0x180030b58  cmp     byte ptr [rcx+19h], 2
0x180030b5c  jb      loc_180030CBE
0x180030b62  test    dword ptr [rcx+1Ch], 400h
0x180030b69  jz      loc_180030CBE
0x180030b6f  mov     edx, ebx
0x180030b71  lea     rcx, aInternalremove; "InternalRemoveItem failed with 0x%x"
0x180030b78  call    WppDbgPrint
0x180030b7d  mov     edx, 10h
0x180030b82  jmp     loc_180030C9C
0x180030b87  mov     rax, [rdi]
0x180030b8a  lea     rdx, [rsp+38h+arg_10]
0x180030b8f  mov     rcx, rdi
0x180030b92  mov     rax, [rax+58h]
0x180030b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b9b  mov     ebx, eax
0x180030b9d  test    eax, eax
0x180030b9f  jns     short loc_180030BE7
0x180030ba1  lea     rax, WPP_GLOBAL_Control
0x180030ba8  mov     rcx, cs:WPP_GLOBAL_Control
0x180030baf  cmp     rcx, rax
0x180030bb2  jz      loc_180030CBE
0x180030bb8  cmp     byte ptr [rcx+19h], 2
0x180030bbc  jb      loc_180030CBE
0x180030bc2  test    dword ptr [rcx+1Ch], 400h
0x180030bc9  jz      loc_180030CBE
0x180030bcf  mov     edx, ebx
0x180030bd1  lea     rcx, aPitemGetGetsdo; "pItem->get_GetSdoObject failed with 0x%"...
0x180030bd8  call    WppDbgPrint
0x180030bdd  mov     edx, 11h
0x180030be2  jmp     loc_180030C9C
0x180030be7  mov     rcx, [rsp+38h+arg_10]
0x180030bec  mov     rax, [rcx]
0x180030bef  lea     r8, [rsp+38h+arg_8]
0x180030bf4  lea     rdx, IID_IDispatch
0x180030bfb  mov     rax, [rax]
0x180030bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c03  mov     ebx, eax
0x180030c05  test    eax, eax
0x180030c07  jns     short loc_180030C4C
0x180030c09  lea     rax, WPP_GLOBAL_Control
0x180030c10  mov     rcx, cs:WPP_GLOBAL_Control
0x180030c17  cmp     rcx, rax
0x180030c1a  jz      loc_180030CBE
0x180030c20  cmp     byte ptr [rcx+19h], 2
0x180030c24  jb      loc_180030CBE
0x180030c2a  test    dword ptr [rcx+1Ch], 400h
0x180030c31  jz      loc_180030CBE
0x180030c37  mov     edx, ebx
0x180030c39  lea     rcx, aPsdoQueryinter; "pSdo->QueryInterface failed with 0x%x"
0x180030c40  call    WppDbgPrint
0x180030c45  mov     edx, 12h
0x180030c4a  jmp     short loc_180030C9C
0x180030c4c  mov     rcx, [rsi+10h]
0x180030c50  mov     rax, [rcx]
0x180030c53  mov     rdx, [rsp+38h+arg_8]
0x180030c58  mov     rax, [rax+48h]
0x180030c5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c61  mov     ebx, eax
0x180030c63  test    eax, eax
0x180030c65  jns     short loc_180030CBE
0x180030c67  lea     rax, WPP_GLOBAL_Control
0x180030c6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180030c75  cmp     rcx, rax
0x180030c78  jz      short loc_180030CBE
0x180030c7a  cmp     byte ptr [rcx+19h], 2
0x180030c7e  jb      short loc_180030CBE
0x180030c80  test    dword ptr [rcx+1Ch], 400h
0x180030c87  jz      short loc_180030CBE
0x180030c89  mov     edx, ebx
0x180030c8b  lea     rcx, aMPcollRemoveFa; "m_pColl->Remove failed with 0x%x"
0x180030c92  call    WppDbgPrint
0x180030c97  mov     edx, 13h
0x180030c9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180030ca3  mov     [rsp+38h+var_18], ebx
0x180030ca7  lea     r9, aNpssdo; "NPSSDO"
0x180030cae  lea     r8, WPP_c2f236718121324f7e73e45b18920f9d_Traceguids
0x180030cb5  mov     rcx, [rcx+10h]
0x180030cb9  call    WPP_SF_sd
0x180030cbe  lea     rcx, [rsp+38h+arg_8]
0x180030cc3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180030cc8  lea     rcx, [rsp+38h+arg_10]
0x180030ccd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180030cd2  mov     eax, ebx
0x180030cd4  mov     rbx, [rsp+38h+arg_0]
0x180030cd9  mov     rsi, [rsp+38h+arg_18]
0x180030cde  add     rsp, 30h
0x180030ce2  pop     rdi
0x180030ce3  retn
```
