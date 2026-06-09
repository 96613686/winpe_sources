# TraceXMLFailure(IXMLDOMDocument2 *)

- ea: `0x18003d9b0`
- end: `0x18003dbcb`
- name: `?TraceXMLFailure@@YAXPEAUIXMLDOMDocument2@@@Z`
- size: `539`
- prototype: `void __fastcall(struct IXMLDOMDocument2 *)`
- caller_count: `8`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180039cc0`
- `0x18003a560`
- `0x18003a880`
- `0x18003b31c`
- `0x18003b8ac`
- `0x18003bc7c`
- `0x18003c96c`
- `0x18003d140`

## callees

- `0x18002cca4`
- `0x18003d9b0`
- `0x1800406ec`
- `0x180042a80`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18003dbb5`
- `OLEAUT32!__imp_SysFreeString` at `0x18003dbbf`
- `OLEAUT32!__imp_SysFreeString` at `0x18003dbb5`
- `OLEAUT32!__imp_SysFreeString` at `0x18003dbbf`

## string_xrefs

- `0x18003da06`: `Can not parse XML error`
- `0x18003db65`: `Can not parse XML error`
- `0x18003daf5`: `\nXML Parsing Error:\n=================\nReason: %S\nSource: %S\nLine:%d\nPos:%d\n`

## pseudocode

```c
void __fastcall TraceXMLFailure(struct IXMLDOMDocument2 *a1)
{
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rax
  BSTR v2[2]; // [rsp+40h] [rbp-10h] BYREF
  int v3; // [rsp+60h] [rbp+10h] BYREF
  int v4; // [rsp+68h] [rbp+18h] BYREF
  __int64 v5; // [rsp+70h] [rbp+20h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp+28h] BYREF

  lpVtbl = a1->lpVtbl;
  v5 = 0;
  if ( ((int (__fastcall *)(struct IXMLDOMDocument2 *, __int64 *))lpVtbl->get_parseError)(a1, &v5) >= 0 )
  {
    bstrString = 0;
    v2[0] = 0;
    v4 = 0;
    v3 = 0;
    if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v5 + 72LL))(v5, &bstrString) < 0
      || (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v5 + 80LL))(v5, v2) < 0
      || (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v5 + 88LL))(v5, &v4) < 0
      || (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v5 + 96LL))(v5, &v3) < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("Can not parse XML error");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids, "NPSSDO");
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("\nXML Parsing Error:\n=================\nReason: %S\nSource: %S\nLine:%d\nPos:%d\n");
      WPP_SF_sSSdd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)bstrString, (__int64)v2[0], v4, v3);
    }
    if ( v5 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      v5 = 0;
    }
    SysFreeString(bstrString);
    SysFreeString(v2[0]);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("Can not parse XML error");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids, "NPSSDO");
  }
}

```

## disassembly

```asm
0x18003d9b0  push    rbp
0x18003d9b2  mov     rbp, rsp
0x18003d9b5  sub     rsp, 50h
0x18003d9b9  mov     rax, [rcx]
0x18003d9bc  lea     rdx, [rbp+arg_10]
0x18003d9c0  mov     [rbp+arg_10], 0
0x18003d9c8  mov     rax, [rax+1E0h]
0x18003d9cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d9d4  test    eax, eax
0x18003d9d6  jns     short loc_18003DA3A
0x18003d9d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d9df  lea     rax, WPP_GLOBAL_Control
0x18003d9e6  cmp     rcx, rax
0x18003d9e9  jz      loc_18003DBC5
0x18003d9ef  cmp     byte ptr [rcx+19h], 2
0x18003d9f3  jb      loc_18003DBC5
0x18003d9f9  test    dword ptr [rcx+1Ch], 400h
0x18003da00  jz      loc_18003DBC5
0x18003da06  lea     rcx, aCanNotParseXml; "Can not parse XML error"
0x18003da0d  call    WppDbgPrint
0x18003da12  mov     rcx, cs:WPP_GLOBAL_Control
0x18003da19  lea     r9, aNpssdo; "NPSSDO"
0x18003da20  mov     edx, 0Ah
0x18003da25  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003da2c  mov     rcx, [rcx+10h]
0x18003da30  call    WPP_SF_s
0x18003da35  jmp     loc_18003DBC5
0x18003da3a  mov     rcx, [rbp+arg_10]
0x18003da3e  lea     rdx, [rbp+bstrString]
0x18003da42  mov     [rbp+bstrString], 0
0x18003da4a  mov     [rbp+var_10], 0
0x18003da52  mov     [rbp+arg_8], 0
0x18003da59  mov     [rbp+arg_0], 0
0x18003da60  mov     rax, [rcx]
0x18003da63  mov     rax, [rax+48h]
0x18003da67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da6c  test    eax, eax
0x18003da6e  js      loc_18003DB43
0x18003da74  mov     rcx, [rbp+arg_10]
0x18003da78  lea     rdx, [rbp+var_10]
0x18003da7c  mov     rax, [rcx]
0x18003da7f  mov     rax, [rax+50h]
0x18003da83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da88  test    eax, eax
0x18003da8a  js      loc_18003DB43
0x18003da90  mov     rcx, [rbp+arg_10]
0x18003da94  lea     rdx, [rbp+arg_8]
0x18003da98  mov     rax, [rcx]
0x18003da9b  mov     rax, [rax+58h]
0x18003da9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003daa4  test    eax, eax
0x18003daa6  js      loc_18003DB43
0x18003daac  mov     rcx, [rbp+arg_10]
0x18003dab0  lea     rdx, [rbp+arg_0]
0x18003dab4  mov     rax, [rcx]
0x18003dab7  mov     rax, [rax+60h]
0x18003dabb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dac0  test    eax, eax
0x18003dac2  js      short loc_18003DB43
0x18003dac4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dacb  lea     rax, WPP_GLOBAL_Control
0x18003dad2  cmp     rcx, rax
0x18003dad5  jz      loc_18003DB94
0x18003dadb  cmp     byte ptr [rcx+19h], 2
0x18003dadf  jb      loc_18003DB94
0x18003dae5  test    dword ptr [rcx+1Ch], 400h
0x18003daec  jz      loc_18003DB94
0x18003daf2  mov     eax, [rbp+arg_0]
0x18003daf5  lea     rcx, aXmlParsingErro; "\nXML Parsing Error:\n================="...
0x18003dafc  mov     r9d, [rbp+arg_8]
0x18003db00  mov     r8, [rbp+var_10]
0x18003db04  mov     rdx, [rbp+bstrString]
0x18003db08  mov     dword ptr [rsp+50h+var_30], eax
0x18003db0c  call    WppDbgPrint
0x18003db11  mov     eax, [rbp+arg_0]
0x18003db14  mov     rcx, cs:WPP_GLOBAL_Control
0x18003db1b  mov     dword ptr [rsp+50h+var_18], eax; char
0x18003db1f  mov     eax, [rbp+arg_8]
0x18003db22  mov     dword ptr [rsp+50h+var_20], eax; char
0x18003db26  mov     rax, [rbp+var_10]
0x18003db2a  mov     rcx, [rcx+10h]; LoggerHandle
0x18003db2e  mov     [rsp+50h+var_28], rax; __int64
0x18003db33  mov     rax, [rbp+bstrString]
0x18003db37  mov     [rsp+50h+var_30], rax; __int64
0x18003db3c  call    WPP_SF_sSSdd
0x18003db41  jmp     short loc_18003DB94
0x18003db43  mov     rcx, cs:WPP_GLOBAL_Control
0x18003db4a  lea     rax, WPP_GLOBAL_Control
0x18003db51  cmp     rcx, rax
0x18003db54  jz      short loc_18003DB94
0x18003db56  cmp     byte ptr [rcx+19h], 2
0x18003db5a  jb      short loc_18003DB94
0x18003db5c  test    dword ptr [rcx+1Ch], 400h
0x18003db63  jz      short loc_18003DB94
0x18003db65  lea     rcx, aCanNotParseXml; "Can not parse XML error"
0x18003db6c  call    WppDbgPrint
0x18003db71  mov     rcx, cs:WPP_GLOBAL_Control
0x18003db78  lea     r9, aNpssdo; "NPSSDO"
0x18003db7f  mov     edx, 0Ch
0x18003db84  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003db8b  mov     rcx, [rcx+10h]
0x18003db8f  call    WPP_SF_s
0x18003db94  mov     rcx, [rbp+arg_10]
0x18003db98  test    rcx, rcx
0x18003db9b  jz      short loc_18003DBB1
0x18003db9d  mov     rax, [rcx]
0x18003dba0  mov     rax, [rax+10h]
0x18003dba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dba9  mov     [rbp+arg_10], 0
0x18003dbb1  mov     rcx, [rbp+bstrString]; bstrString
0x18003dbb5  call    cs:__imp_SysFreeString
0x18003dbbb  mov     rcx, [rbp+var_10]; bstrString
0x18003dbbf  call    cs:__imp_SysFreeString
0x18003dbc5  add     rsp, 50h
0x18003dbc9  pop     rbp
0x18003dbca  retn
```
