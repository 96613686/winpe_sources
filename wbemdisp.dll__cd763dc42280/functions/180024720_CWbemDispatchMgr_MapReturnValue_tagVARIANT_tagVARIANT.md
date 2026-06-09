# CWbemDispatchMgr::MapReturnValue(tagVARIANT *,tagVARIANT *)

- ea: `0x180024720`
- end: `0x18002476e`
- name: `?MapReturnValue@CWbemDispatchMgr@@AEAAJPEAUtagVARIANT@@0@Z`
- size: `78`
- prototype: `int(CWbemDispatchMgr *__hidden this, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x180003a10`

## callees

- `0x1800019a0`
- `0x180005bf0`
- `0x180024720`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x18002475d`
- `OLEAUT32!__imp_VariantCopy` at `0x18002475d`

## pseudocode

```c
int __fastcall CWbemDispatchMgr::MapReturnValue(
        struct CSWbemServices **this,
        struct tagVARIANT *a2,
        struct tagVARIANT *a3)
{
  int result; // eax
  int v6; // [rsp+20h] [rbp-18h]

  result = MapFromCIMOMObject(this[4], a3, 0, 0, v6);
  if ( result >= 0 )
  {
    if ( (a3->vt & 0x2000) != 0 )
      return ConvertArrayRev(a2, a3);
    else
      return VariantCopy(a2, a3);
  }
  return result;
}

```

## disassembly

```asm
0x180024720  mov     [rsp+arg_0], rbx
0x180024725  push    rdi
0x180024726  sub     rsp, 30h
0x18002472a  mov     rcx, [rcx+20h]; struct CSWbemServices *
0x18002472e  mov     rbx, r8
0x180024731  mov     rdi, rdx
0x180024734  xor     r9d, r9d; unsigned __int16 *
0x180024737  mov     rdx, rbx; struct tagVARIANT *
0x18002473a  xor     r8d, r8d; struct ISWbemInternalObject *
0x18002473d  call    ?MapFromCIMOMObject@@YAJPEAVCSWbemServices@@PEAUtagVARIANT@@PEAUISWbemInternalObject@@PEAGJ@Z; MapFromCIMOMObject(CSWbemServices *,tagVARIANT *,ISWbemInternalObject *,ushort *,long)
0x180024742  test    eax, eax
0x180024744  js      short loc_180024763
0x180024746  mov     eax, 2000h
0x18002474b  mov     rdx, rbx; struct tagVARIANT *
0x18002474e  mov     rcx, rdi; struct tagVARIANT *
0x180024751  test    [rbx], ax
0x180024754  jz      short loc_18002475D
0x180024756  call    ?ConvertArrayRev@@YAJPEAUtagVARIANT@@0@Z; ConvertArrayRev(tagVARIANT *,tagVARIANT *)
0x18002475b  jmp     short loc_180024763
0x18002475d  call    cs:__imp_VariantCopy
0x180024763  mov     rbx, [rsp+38h+arg_0]
0x180024768  add     rsp, 30h
0x18002476c  pop     rdi
0x18002476d  retn
```
