# IASIPFilter::get_IPFilterAttributesCollection(IIASAttributesCollection * *)

- ea: `0x180040d70`
- end: `0x180040ea2`
- name: `?get_IPFilterAttributesCollection@IASIPFilter@@UEAAJPEAPEAUIIASAttributesCollection@@@Z`
- size: `306`
- prototype: `__int64 __fastcall(IASIPFilter *__hidden this, struct IIASAttributesCollection **)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18002cca4`
- `0x18002cd00`
- `0x180032304`
- `0x180040d70`
- `0x180042a80`

## string_xrefs

- `0x180040e67`: `m_pAttributes.CopyTo failed with 0x%x, when trying to copy IP filter attributes`

## pseudocode

```c
__int64 __fastcall IASIPFilter::get_IPFilterAttributesCollection(
        IASIPFilter *this,
        struct IIASAttributesCollection **a2)
{
  int v2; // ebx
  _QWORD *v3; // rcx

  if ( a2 )
  {
    v3 = (_QWORD *)((char *)this + 120);
    if ( *v3 )
    {
      v2 = ATL::CComPtrBase<IIASItemsCollection>::CopyTo(v3, a2);
      if ( v2 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("m_pAttributes.CopyTo failed with 0x%x, when trying to copy IP filter attributes");
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)WPP_2df12cdf81bf360e3d7ad639b5f29067_Traceguids,
          (unsigned int)"NPSSDO",
          v2);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("Collection is empty, when trying to get IP Filter attributes collection");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_2df12cdf81bf360e3d7ad639b5f29067_Traceguids, "NPSSDO");
      }
      return (unsigned int)-2147418113;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("Invalid pointer, when trying to get IP Filter attributes collection");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_2df12cdf81bf360e3d7ad639b5f29067_Traceguids, "NPSSDO");
    }
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180040d70  push    rbx
0x180040d72  sub     rsp, 30h
0x180040d76  test    rdx, rdx
0x180040d79  jnz     short loc_180040DD6
0x180040d7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180040d82  lea     rax, WPP_GLOBAL_Control
0x180040d89  cmp     rcx, rax
0x180040d8c  jz      short loc_180040DCC
0x180040d8e  cmp     byte ptr [rcx+19h], 2
0x180040d92  jb      short loc_180040DCC
0x180040d94  test    dword ptr [rcx+1Ch], 400h
0x180040d9b  jz      short loc_180040DCC
0x180040d9d  lea     rcx, aInvalidPointer; "Invalid pointer, when trying to get IP "...
0x180040da4  call    WppDbgPrint
0x180040da9  mov     rcx, cs:WPP_GLOBAL_Control
0x180040db0  lea     r9, aNpssdo; "NPSSDO"
0x180040db7  mov     edx, 0Fh
0x180040dbc  lea     r8, WPP_2df12cdf81bf360e3d7ad639b5f29067_Traceguids
0x180040dc3  mov     rcx, [rcx+10h]
0x180040dc7  call    WPP_SF_s
0x180040dcc  mov     ebx, 80004003h
0x180040dd1  jmp     loc_180040E9A
0x180040dd6  add     rcx, 78h ; 'x'
0x180040dda  cmp     qword ptr [rcx], 0
0x180040dde  jnz     short loc_180040E38
0x180040de0  mov     rcx, cs:WPP_GLOBAL_Control
0x180040de7  lea     rax, WPP_GLOBAL_Control
0x180040dee  cmp     rcx, rax
0x180040df1  jz      short loc_180040E31
0x180040df3  cmp     byte ptr [rcx+19h], 2
0x180040df7  jb      short loc_180040E31
0x180040df9  test    dword ptr [rcx+1Ch], 400h
0x180040e00  jz      short loc_180040E31
0x180040e02  lea     rcx, aCollectionIsEm; "Collection is empty, when trying to get"...
0x180040e09  call    WppDbgPrint
0x180040e0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180040e15  lea     r9, aNpssdo; "NPSSDO"
0x180040e1c  mov     edx, 10h
0x180040e21  lea     r8, WPP_2df12cdf81bf360e3d7ad639b5f29067_Traceguids
0x180040e28  mov     rcx, [rcx+10h]
0x180040e2c  call    WPP_SF_s
0x180040e31  mov     ebx, 8000FFFFh
0x180040e36  jmp     short loc_180040E9A
0x180040e38  call    ?CopyTo@?$CComPtrBase@UIIASItemsCollection@@@ATL@@QEAAJPEAPEAUIIASItemsCollection@@@Z; ATL::CComPtrBase<IIASItemsCollection>::CopyTo(IIASItemsCollection * *)
0x180040e3d  mov     ebx, eax
0x180040e3f  test    eax, eax
0x180040e41  jns     short loc_180040E9A
0x180040e43  mov     rcx, cs:WPP_GLOBAL_Control
0x180040e4a  lea     rax, WPP_GLOBAL_Control
0x180040e51  cmp     rcx, rax
0x180040e54  jz      short loc_180040E9A
0x180040e56  cmp     byte ptr [rcx+19h], 2
0x180040e5a  jb      short loc_180040E9A
0x180040e5c  test    dword ptr [rcx+1Ch], 400h
0x180040e63  jz      short loc_180040E9A
0x180040e65  mov     edx, ebx
0x180040e67  lea     rcx, aMPattributesCo_0; "m_pAttributes.CopyTo failed with 0x%x, "...
0x180040e6e  call    WppDbgPrint
0x180040e73  mov     rcx, cs:WPP_GLOBAL_Control
0x180040e7a  lea     r9, aNpssdo; "NPSSDO"
0x180040e81  mov     edx, 11h
0x180040e86  mov     [rsp+38h+var_18], ebx
0x180040e8a  lea     r8, WPP_2df12cdf81bf360e3d7ad639b5f29067_Traceguids
0x180040e91  mov     rcx, [rcx+10h]
0x180040e95  call    WPP_SF_sd
0x180040e9a  mov     eax, ebx
0x180040e9c  add     rsp, 30h
0x180040ea0  pop     rbx
0x180040ea1  retn
```
