# IASPolicy::get_ProfileAttributesCollection(IIASAttributesCollection * *)

- ea: `0x180035c70`
- end: `0x180035d00`
- name: `?get_ProfileAttributesCollection@IASPolicy@@UEAAJPEAPEAUIIASAttributesCollection@@@Z`
- size: `144`
- prototype: `__int64 __fastcall(IASPolicy *__hidden this, struct IIASAttributesCollection **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18002cd00`
- `0x180032304`
- `0x180035c70`
- `0x180042a80`

## string_xrefs

- `0x180035cc5`: `m_pAttributes.CopyTo failed with 0x%x`

## pseudocode

```c
__int64 __fastcall IASPolicy::get_ProfileAttributesCollection(IASPolicy *this, struct IIASAttributesCollection **a2)
{
  _QWORD *v3; // rcx
  int v4; // ebx

  if ( !a2 )
    return 2147500035LL;
  v3 = (_QWORD *)((char *)this + 144);
  if ( *v3 )
  {
    v4 = ATL::CComPtrBase<IIASItemsCollection>::CopyTo(v3, a2);
    if ( v4 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("m_pAttributes.CopyTo failed with 0x%x");
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        (unsigned int)WPP_dd21b8743a813b1e52cbedc9bc221252_Traceguids,
        (unsigned int)"NPSSDO",
        v4);
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180035c70  push    rbx
0x180035c72  sub     rsp, 30h
0x180035c76  test    rdx, rdx
0x180035c79  jnz     short loc_180035C82
0x180035c7b  mov     eax, 80004003h
0x180035c80  jmp     short loc_180035CFA
0x180035c82  add     rcx, 90h
0x180035c89  cmp     qword ptr [rcx], 0
0x180035c8d  jnz     short loc_180035C96
0x180035c8f  mov     ebx, 80004005h
0x180035c94  jmp     short loc_180035CF8
0x180035c96  call    ?CopyTo@?$CComPtrBase@UIIASItemsCollection@@@ATL@@QEAAJPEAPEAUIIASItemsCollection@@@Z; ATL::CComPtrBase<IIASItemsCollection>::CopyTo(IIASItemsCollection * *)
0x180035c9b  mov     ebx, eax
0x180035c9d  test    eax, eax
0x180035c9f  jns     short loc_180035CF8
0x180035ca1  mov     rax, cs:WPP_GLOBAL_Control
0x180035ca8  lea     rcx, WPP_GLOBAL_Control
0x180035caf  cmp     rax, rcx
0x180035cb2  jz      short loc_180035CF8
0x180035cb4  cmp     byte ptr [rax+19h], 2
0x180035cb8  jb      short loc_180035CF8
0x180035cba  test    dword ptr [rax+1Ch], 400h
0x180035cc1  jz      short loc_180035CF8
0x180035cc3  mov     edx, ebx
0x180035cc5  lea     rcx, aMPattributesCo; "m_pAttributes.CopyTo failed with 0x%x"
0x180035ccc  call    WppDbgPrint
0x180035cd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180035cd8  lea     r9, aNpssdo; "NPSSDO"
0x180035cdf  mov     edx, 29h ; ')'
0x180035ce4  mov     [rsp+38h+var_18], ebx
0x180035ce8  lea     r8, WPP_dd21b8743a813b1e52cbedc9bc221252_Traceguids
0x180035cef  mov     rcx, [rcx+10h]
0x180035cf3  call    WPP_SF_sd
0x180035cf8  mov     eax, ebx
0x180035cfa  add     rsp, 30h
0x180035cfe  pop     rbx
0x180035cff  retn
```
