# SdpCheckDocumentVersion(IXMLDOMDocument2 *,ushort const *,ushort const *)

- ea: `0x180003410`
- end: `0x1800034bc`
- name: `?SdpCheckDocumentVersion@@YAJPEAUIXMLDOMDocument2@@PEBG1@Z`
- size: `172`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800176dc`
- `0x180020648`

## callees

- `0x180003410`
- `0x180026fa0`
- `0x18002848c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000347b`
- `msvcrt!_wcsicmp` at `0x18000347b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800034ae`
- `OLEAUT32!__imp_SysFreeString` at `0x1800034ae`

## pseudocode

```c
__int64 __fastcall SdpCheckDocumentVersion(
        struct IXMLDOMDocument2 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v3; // r9d
  int v4; // r8d
  unsigned int v5; // ebx
  int Attribute; // eax
  wchar_t *String1; // [rsp+40h] [rbp+18h] BYREF

  String1 = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      Attribute = SdpXmlGetAttribute(a1, 0, a2, &String1);
      v5 = Attribute;
      if ( Attribute >= 0 )
      {
        if ( !_wcsicmp(String1, L"1.0") )
          goto LABEL_10;
        v5 = -2143551223;
        v4 = 855;
        v3 = -2143551223;
      }
      else
      {
        v3 = Attribute;
        v4 = 851;
      }
    }
    else
    {
      v3 = -2147024809;
      v4 = 847;
      v5 = -2147024809;
    }
  }
  else
  {
    v3 = -2147024809;
    v4 = 846;
    v5 = -2147024809;
  }
  SdpDebugTrace(1u, L"SdpCheckDocumentVersion", v4, v3);
LABEL_10:
  if ( String1 )
    SysFreeString(String1);
  return v5;
}

```

## disassembly

```asm
0x180003410  mov     [rsp+String1], r8
0x180003415  push    rbx
0x180003416  sub     rsp, 20h
0x18000341a  mov     [rsp+28h+String1], 0
0x180003423  test    rcx, rcx
0x180003426  jnz     short loc_180003439
0x180003428  mov     r9d, 80070057h
0x18000342e  mov     r8d, 34Eh
0x180003434  mov     ebx, r9d
0x180003437  jmp     short loc_180003493
0x180003439  test    rdx, rdx
0x18000343c  jnz     short loc_18000344F
0x18000343e  mov     r9d, 80070057h
0x180003444  mov     r8d, 34Fh
0x18000344a  mov     ebx, r9d
0x18000344d  jmp     short loc_180003493
0x18000344f  mov     r8, rdx; unsigned __int16 *
0x180003452  lea     r9, [rsp+28h+String1]; unsigned __int16 **
0x180003457  xor     edx, edx; struct IXMLDOMNode *
0x180003459  call    ?SdpXmlGetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBGPEAPEAG@Z; SdpXmlGetAttribute(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort * *)
0x18000345e  mov     ebx, eax
0x180003460  test    eax, eax
0x180003462  jns     short loc_18000346F
0x180003464  mov     r9d, eax
0x180003467  mov     r8d, 353h
0x18000346d  jmp     short loc_180003493
0x18000346f  mov     rcx, [rsp+28h+String1]; String1
0x180003474  lea     rdx, a10; "1.0"
0x18000347b  call    cs:__imp__wcsicmp
0x180003481  test    eax, eax
0x180003483  jz      short loc_1800034A4
0x180003485  mov     ebx, 803C0109h
0x18000348a  mov     r8d, 357h; int
0x180003490  mov     r9d, ebx; int
0x180003493  lea     rdx, aSdpcheckdocume; "SdpCheckDocumentVersion"
0x18000349a  mov     ecx, 1; Level
0x18000349f  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800034a4  mov     rcx, [rsp+28h+String1]; bstrString
0x1800034a9  test    rcx, rcx
0x1800034ac  jz      short loc_1800034B4
0x1800034ae  call    cs:__imp_SysFreeString
0x1800034b4  mov     eax, ebx
0x1800034b6  add     rsp, 20h
0x1800034ba  pop     rbx
0x1800034bb  retn
```
