# SDiagPrviSetDOMProperties(IXMLDOMDocument *,ushort const *)

- ea: `0x1800031d8`
- end: `0x1800032e3`
- name: `?SDiagPrviSetDOMProperties@@YAJPEAUIXMLDOMDocument@@PEBG@Z`
- size: `267`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008f00`
- `0x18000d748`

## callees

- `0x1800031d8`
- `0x1800032ec`
- `0x18000331c`
- `0x180019010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000324a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000326f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000324a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000326f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800032bd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800032bd`

## string_xrefs

- `0x180003264`: `xmlns:cfg='http://www.microsoft.com/schemas/dcm/configuration/2008' xmlns:dcp='http://diagnostics.microsoft.com/2007/08/DiagnosticPackageCatalog' xmlns:ms='urn:schemas-microsoft-com:xslt' `

## pseudocode

```c
__int64 __fastcall SDiagPrviSetDOMProperties(struct IXMLDOMDocument *a1, const unsigned __int16 *a2)
{
  OLECHAR *v3; // rdi
  int v4; // ebx
  __int64 v5; // rax
  struct tagVARIANT v7; // [rsp+20h] [rbp-48h] BYREF
  struct tagVARIANT v8; // [rsp+40h] [rbp-28h] BYREF
  __int64 *v9; // [rsp+98h] [rbp+30h] BYREF

  v9 = 0;
  v3 = 0;
  memset(&v7, 0, sizeof(v7));
  v4 = SDiagPrviVariantInit(&v7);
  if ( v4 >= 0 )
  {
    if ( a1 )
    {
      v4 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, GUID *, __int64 **))a1->lpVtbl->QueryInterface)(
             a1,
             &IID_IXMLDOMDocument2,
             &v9);
      if ( v4 >= 0 )
      {
        v3 = SysAllocString(L"SelectionNamespaces");
        if ( v3
          && (v7.vt = 8,
              (v7.llVal = (LONGLONG)SysAllocString(
                                      L"xmlns:cfg='http://www.microsoft.com/schemas/dcm/configuration/2008' xmlns:dcp='htt"
                                       "p://diagnostics.microsoft.com/2007/08/DiagnosticPackageCatalog' xmlns:ms='urn:sch"
                                       "emas-microsoft-com:xslt' ")) != 0) )
        {
          v5 = *v9;
          v8 = v7;
          v4 = (*(__int64 (__fastcall **)(__int64 *, OLECHAR *, struct tagVARIANT *))(v5 + 640))(v9, v3, &v8);
        }
        else
        {
          v4 = -2147024882;
        }
      }
    }
    else
    {
      v4 = -2147024809;
    }
  }
  SDiagPrviVariantClear(&v7);
  if ( v3 )
    SysFreeString(v3);
  if ( v9 )
    (*(void (__fastcall **)(__int64 *))(*v9 + 16))(v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800031d8  mov     [rsp-20h+arg_8], rdx
0x1800031dd  push    rbp
0x1800031de  push    rbx
0x1800031df  push    rsi
0x1800031e0  push    rdi
0x1800031e1  mov     rbp, rsp
0x1800031e4  sub     rsp, 68h
0x1800031e8  mov     rsi, rcx
0x1800031eb  mov     [rbp+arg_8], 0
0x1800031f3  xorps   xmm0, xmm0
0x1800031f6  lea     rcx, [rbp+var_48]; struct tagVARIANT *
0x1800031fa  xor     eax, eax
0x1800031fc  xor     edi, edi
0x1800031fe  movups  xmmword ptr [rbp+var_48], xmm0
0x180003202  mov     qword ptr [rbp+var_48+10h], rax
0x180003206  call    ?SDiagPrviVariantInit@@YAJPEAUtagVARIANT@@@Z; SDiagPrviVariantInit(tagVARIANT *)
0x18000320b  mov     ebx, eax
0x18000320d  test    eax, eax
0x18000320f  js      loc_1800032AC
0x180003215  test    rsi, rsi
0x180003218  jnz     short loc_180003224
0x18000321a  mov     ebx, 80070057h
0x18000321f  jmp     loc_1800032AC
0x180003224  mov     rax, [rsi]
0x180003227  lea     r8, [rbp+arg_8]
0x18000322b  lea     rdx, IID_IXMLDOMDocument2
0x180003232  mov     rcx, rsi
0x180003235  mov     rax, [rax]
0x180003238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000323d  mov     ebx, eax
0x18000323f  test    eax, eax
0x180003241  js      short loc_1800032AC
0x180003243  lea     rcx, psz; "SelectionNamespaces"
0x18000324a  call    cs:__imp_SysAllocString
0x180003250  mov     rdi, rax
0x180003253  test    rax, rax
0x180003256  jnz     short loc_18000325F
0x180003258  mov     ebx, 8007000Eh
0x18000325d  jmp     short loc_1800032AC
0x18000325f  mov     eax, 8
0x180003264  lea     rcx, aXmlnsCfgHttpWw; "xmlns:cfg='http://www.microsoft.com/sch"...
0x18000326b  mov     word ptr [rbp+var_48], ax
0x18000326f  call    cs:__imp_SysAllocString
0x180003275  mov     qword ptr [rbp+var_48+8], rax
0x180003279  test    rax, rax
0x18000327c  jz      short loc_180003258
0x18000327e  mov     rcx, [rbp+arg_8]
0x180003282  lea     r8, [rbp+var_28]
0x180003286  movups  xmm0, xmmword ptr [rbp+var_48]
0x18000328a  mov     rdx, rdi
0x18000328d  movsd   xmm1, qword ptr [rbp+var_48+10h]
0x180003292  mov     rax, [rcx]
0x180003295  movaps  [rbp+var_28], xmm0
0x180003299  movsd   [rbp+var_18], xmm1
0x18000329e  mov     rax, [rax+280h]
0x1800032a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032aa  mov     ebx, eax
0x1800032ac  lea     rcx, [rbp+var_48]; struct tagVARIANT *
0x1800032b0  call    ?SDiagPrviVariantClear@@YAJPEAUtagVARIANT@@@Z; SDiagPrviVariantClear(tagVARIANT *)
0x1800032b5  test    rdi, rdi
0x1800032b8  jz      short loc_1800032C3
0x1800032ba  mov     rcx, rdi; bstrString
0x1800032bd  call    cs:__imp_SysFreeString
0x1800032c3  mov     rcx, [rbp+arg_8]
0x1800032c7  test    rcx, rcx
0x1800032ca  jz      short loc_1800032D8
0x1800032cc  mov     rax, [rcx]
0x1800032cf  mov     rax, [rax+10h]
0x1800032d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032d8  mov     eax, ebx
0x1800032da  add     rsp, 68h
0x1800032de  pop     rdi
0x1800032df  pop     rsi
0x1800032e0  pop     rbx
0x1800032e1  pop     rbp
0x1800032e2  retn
```
