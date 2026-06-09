# CUtils::PropVariantToSemiColonDelimtedString(tagPROPVARIANT const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x1800391bc`
- end: `0x1800392a7`
- name: `?PropVariantToSemiColonDelimtedString@CUtils@@YAJAEBUtagPROPVARIANT@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(PROPVARIANT *propvar)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800243c0`
- `0x180024630`
- `0x180026e50`

## callees

- `0x180003220`
- `0x180004dd4`
- `0x18001966c`
- `0x1800391bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039266`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039285`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039266`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039285`
- `PROPSYS!PropVariantGetElementCount` at `0x1800391f5`
- `PROPSYS!PropVariantGetElementCount` at `0x1800391f5`
- `PROPSYS!PropVariantGetStringElem` at `0x180039238`
- `PROPSYS!PropVariantGetStringElem` at `0x180039238`

## pseudocode

```c
__int64 __fastcall CUtils::PropVariantToSemiColonDelimtedString(PROPVARIANT *propvar, __int64 a2)
{
  __int16 v3; // ax
  ULONG ElementCount; // edi
  ULONG v6; // ebx
  HRESULT StringElem; // esi
  unsigned int v8; // eax
  __int64 v9; // rcx
  PWSTR v10; // rcx
  PWSTR ppszVal; // [rsp+40h] [rbp+8h] BYREF

  v3 = *(_WORD *)propvar - 31;
  ppszVal = 0;
  if ( (v3 & 0xEFFF) != 0 )
    return 2147942487LL;
  ElementCount = PropVariantGetElementCount(propvar);
  if ( !ElementCount )
    return 2147942487LL;
  ATL::CSimpleStringT<unsigned short,0>::Empty(a2);
  v6 = 0;
  while ( 1 )
  {
    if ( v6 )
      ATL::CSimpleStringT<unsigned short,0>::Append(a2, L";", 1);
    StringElem = PropVariantGetStringElem(propvar, v6, &ppszVal);
    if ( StringElem < 0 )
      break;
    v8 = ocslen(ppszVal);
    ATL::CSimpleStringT<unsigned short,0>::Append(a2, v9, v8);
    v10 = ppszVal;
    if ( ppszVal )
    {
      CoTaskMemFree(ppszVal);
      v10 = 0;
      ppszVal = 0;
    }
    if ( ++v6 >= ElementCount )
      goto LABEL_12;
  }
  v10 = ppszVal;
LABEL_12:
  if ( v10 )
    CoTaskMemFree(v10);
  return (unsigned int)StringElem;
}

```

## disassembly

```asm
0x1800391bc  mov     [rsp+arg_8], rbx
0x1800391c1  mov     [rsp+arg_10], rbp
0x1800391c6  push    rsi
0x1800391c7  push    rdi
0x1800391c8  push    r14
0x1800391ca  sub     rsp, 20h
0x1800391ce  movzx   eax, word ptr [rcx]
0x1800391d1  mov     r14, rcx
0x1800391d4  sub     ax, 1Fh
0x1800391d8  mov     [rsp+38h+ppszVal], 0
0x1800391e1  mov     ecx, 0EFFFh
0x1800391e6  mov     rbp, rdx
0x1800391e9  test    cx, ax
0x1800391ec  jnz     loc_18003928F
0x1800391f2  mov     rcx, r14; propvar
0x1800391f5  call    cs:__imp_PropVariantGetElementCount
0x1800391fb  mov     edi, eax
0x1800391fd  test    eax, eax
0x1800391ff  jz      loc_18003928F
0x180039205  mov     rcx, rbp
0x180039208  xor     esi, esi
0x18003920a  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18003920f  xor     ebx, ebx
0x180039211  test    edi, edi
0x180039213  jz      short loc_18003927B
0x180039215  test    ebx, ebx
0x180039217  jz      short loc_18003922E
0x180039219  mov     r8d, 1
0x18003921f  lea     rdx, asc_18006CCC8; ";"
0x180039226  mov     rcx, rbp
0x180039229  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18003922e  lea     r8, [rsp+38h+ppszVal]; ppszVal
0x180039233  mov     edx, ebx; iElem
0x180039235  mov     rcx, r14; propvar
0x180039238  call    cs:__imp_PropVariantGetStringElem
0x18003923e  mov     esi, eax
0x180039240  test    eax, eax
0x180039242  js      short loc_18003927B
0x180039244  mov     rcx, [rsp+38h+ppszVal]; unsigned __int16 *
0x180039249  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x18003924e  mov     rdx, rcx
0x180039251  mov     r8d, eax
0x180039254  mov     rcx, rbp
0x180039257  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18003925c  mov     rcx, [rsp+38h+ppszVal]; pv
0x180039261  test    rcx, rcx
0x180039264  jz      short loc_180039273
0x180039266  call    cs:__imp_CoTaskMemFree
0x18003926c  xor     ecx, ecx
0x18003926e  mov     [rsp+38h+ppszVal], rcx
0x180039273  inc     ebx
0x180039275  cmp     ebx, edi
0x180039277  jb      short loc_180039215
0x180039279  jmp     short loc_180039280
0x18003927b  mov     rcx, [rsp+38h+ppszVal]; pv
0x180039280  test    rcx, rcx
0x180039283  jz      short loc_18003928B
0x180039285  call    cs:__imp_CoTaskMemFree
0x18003928b  mov     eax, esi
0x18003928d  jmp     short loc_180039294
0x18003928f  mov     eax, 80070057h
0x180039294  mov     rbx, [rsp+38h+arg_8]
0x180039299  mov     rbp, [rsp+38h+arg_10]
0x18003929e  add     rsp, 20h
0x1800392a2  pop     r14
0x1800392a4  pop     rdi
0x1800392a5  pop     rsi
0x1800392a6  retn
```
