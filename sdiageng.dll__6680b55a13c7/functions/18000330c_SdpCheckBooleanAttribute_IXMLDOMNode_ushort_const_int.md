# SdpCheckBooleanAttribute(IXMLDOMNode *,ushort const *,int *)

- ea: `0x18000330c`
- end: `0x180003409`
- name: `?SdpCheckBooleanAttribute@@YAJPEAUIXMLDOMNode@@PEBGPEAH@Z`
- size: `253`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, OLECHAR *psz, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180015730`
- `0x180016630`

## callees

- `0x18000330c`
- `0x180026fa0`
- `0x18002848c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800033cf`
- `msvcrt!_wcsicmp` at `0x1800033cf`
- `OLEAUT32!__imp_SysAllocString` at `0x180003371`
- `OLEAUT32!__imp_SysAllocString` at `0x180003371`
- `OLEAUT32!__imp_SysFreeString` at `0x1800033e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800033f1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800033e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800033f1`

## pseudocode

```c
__int64 __fastcall SdpCheckBooleanAttribute(struct IXMLDOMNode *a1, OLECHAR *psz, int *a3)
{
  int v5; // r8d
  int v6; // r9d
  unsigned int v7; // ebx
  const unsigned __int16 *v8; // rax
  OLECHAR *v9; // rdi
  int Attribute; // eax
  wchar_t *String1; // [rsp+30h] [rbp+8h] BYREF

  String1 = 0;
  if ( !a1 )
  {
    v5 = 790;
LABEL_3:
    v6 = -2147024809;
    v7 = -2147024809;
    goto LABEL_4;
  }
  if ( !psz )
  {
    v5 = 791;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v5 = 792;
    goto LABEL_3;
  }
  v8 = SysAllocString(psz);
  v9 = (OLECHAR *)v8;
  if ( v8 )
  {
    Attribute = SdpXmlGetAttribute(0, a1, v8, &String1);
    v7 = Attribute;
    if ( Attribute >= 0 )
      *a3 = _wcsicmp(String1, L"true") == 0;
    else
      SdpDebugTrace(1u, L"SdpCheckBooleanAttribute", 798, Attribute);
    SysFreeString(v9);
    goto LABEL_15;
  }
  v7 = -2147024882;
  v5 = 795;
  v6 = -2147024882;
LABEL_4:
  SdpDebugTrace(1u, L"SdpCheckBooleanAttribute", v5, v6);
LABEL_15:
  if ( String1 )
    SysFreeString(String1);
  return v7;
}

```

## disassembly

```asm
0x18000330c  mov     [rsp+arg_8], rbx
0x180003311  mov     [rsp+arg_10], rsi
0x180003316  push    rdi
0x180003317  sub     rsp, 20h
0x18000331b  mov     [rsp+28h+String1], 0
0x180003324  mov     rsi, r8
0x180003327  mov     rbx, rcx
0x18000332a  test    rcx, rcx
0x18000332d  jnz     short loc_180003354
0x18000332f  mov     r8d, 316h; int
0x180003335  mov     r9d, 80070057h; int
0x18000333b  mov     ebx, r9d
0x18000333e  lea     rdx, aSdpcheckboolea; "SdpCheckBooleanAttribute"
0x180003345  mov     ecx, 1; Level
0x18000334a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000334f  jmp     loc_1800033E7
0x180003354  test    rdx, rdx
0x180003357  jnz     short loc_180003361
0x180003359  mov     r8d, 317h
0x18000335f  jmp     short loc_180003335
0x180003361  test    rsi, rsi
0x180003364  jnz     short loc_18000336E
0x180003366  mov     r8d, 318h
0x18000336c  jmp     short loc_180003335
0x18000336e  mov     rcx, rdx; psz
0x180003371  call    cs:__imp_SysAllocString
0x180003377  mov     rdi, rax
0x18000337a  test    rax, rax
0x18000337d  jnz     short loc_18000338F
0x18000337f  mov     ebx, 8007000Eh
0x180003384  mov     r8d, 31Bh
0x18000338a  mov     r9d, ebx
0x18000338d  jmp     short loc_18000333E
0x18000338f  lea     r9, [rsp+28h+String1]; unsigned __int16 **
0x180003394  mov     r8, rdi; unsigned __int16 *
0x180003397  mov     rdx, rbx; struct IXMLDOMNode *
0x18000339a  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18000339c  call    ?SdpXmlGetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBGPEAPEAG@Z; SdpXmlGetAttribute(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort * *)
0x1800033a1  mov     ebx, eax
0x1800033a3  test    eax, eax
0x1800033a5  jns     short loc_1800033C3
0x1800033a7  mov     r9d, eax; int
0x1800033aa  lea     rdx, aSdpcheckboolea; "SdpCheckBooleanAttribute"
0x1800033b1  mov     r8d, 31Eh; int
0x1800033b7  mov     ecx, 1; Level
0x1800033bc  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800033c1  jmp     short loc_1800033DE
0x1800033c3  mov     rcx, [rsp+28h+String1]; String1
0x1800033c8  lea     rdx, aTrue; "true"
0x1800033cf  call    cs:__imp__wcsicmp
0x1800033d5  xor     ecx, ecx
0x1800033d7  test    eax, eax
0x1800033d9  setz    cl
0x1800033dc  mov     [rsi], ecx
0x1800033de  mov     rcx, rdi; bstrString
0x1800033e1  call    cs:__imp_SysFreeString
0x1800033e7  mov     rcx, [rsp+28h+String1]; bstrString
0x1800033ec  test    rcx, rcx
0x1800033ef  jz      short loc_1800033F7
0x1800033f1  call    cs:__imp_SysFreeString
0x1800033f7  mov     rsi, [rsp+28h+arg_10]
0x1800033fc  mov     eax, ebx
0x1800033fe  mov     rbx, [rsp+28h+arg_8]
0x180003403  add     rsp, 20h
0x180003407  pop     rdi
0x180003408  retn
```
