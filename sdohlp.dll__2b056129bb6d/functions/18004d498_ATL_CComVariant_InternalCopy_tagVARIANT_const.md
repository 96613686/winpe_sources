# ATL::CComVariant::InternalCopy(tagVARIANT const *)

- ea: `0x18004d498`
- end: `0x18004d4c1`
- name: `?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z`
- size: `41`
- prototype: `void __fastcall(ATL::CComVariant *__hidden this, const struct tagVARIANT *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18004bdbc`
- `0x18004cef4`
- `0x18004cf60`
- `0x18004d11c`

## callees

- `0x1800268c8`
- `0x18004d498`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x18004d4a1`
- `OLEAUT32!__imp_VariantCopy` at `0x18004d4a1`

## pseudocode

```c
void __fastcall ATL::CComVariant::InternalCopy(VARIANTARG *this, const struct tagVARIANT *a2)
{
  HRESULT v3; // eax

  v3 = VariantCopy(this, a2);
  if ( v3 < 0 )
  {
    this->vt = 10;
    this->lVal = v3;
    ATL::AtlThrowImpl(v3);
  }
}

```

## disassembly

```asm
0x18004d498  push    rbx
0x18004d49a  sub     rsp, 20h
0x18004d49e  mov     rbx, rcx
0x18004d4a1  call    cs:__imp_VariantCopy
0x18004d4a7  test    eax, eax
0x18004d4a9  js      short loc_18004D4B1
0x18004d4ab  add     rsp, 20h
0x18004d4af  pop     rbx
0x18004d4b0  retn
0x18004d4b1  mov     ecx, eax; int
0x18004d4b3  mov     word ptr [rbx], 0Ah
0x18004d4b8  mov     [rbx+8], eax
0x18004d4bb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
