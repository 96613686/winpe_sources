# CMultipleValues::GetValue(tagPROPVARIANT *)

- ea: `0x18007a410`
- end: `0x18007a473`
- name: `?GetValue@CMultipleValues@@UEAAJPEAUtagPROPVARIANT@@@Z`
- size: `99`
- prototype: `int(CMultipleValues *__hidden this, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18007a410`
- `0x18007aac0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007a44d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007a44d`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18007a430`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18007a45a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18007a430`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18007a45a`

## pseudocode

```c
__int64 __fastcall CMultipleValues::GetValue(CMultipleValues *this, PROPVARIANT *a2)
{
  int inited; // ebp

  *(_WORD *)a2 = 0;
  if ( *((_BYTE *)this + 64) )
  {
    inited = InitPropVariantFromPropVariantDSA((HDSA *)this + 7, (__int64)a2);
    if ( inited >= 0 )
    {
      PropVariantClear((PROPVARIANT *)this + 4);
      if ( PropVariantCopy((PROPVARIANT *)this + 4, a2) >= 0 )
        *((_BYTE *)this + 64) = 0;
    }
  }
  else
  {
    return (unsigned int)PropVariantCopy(a2, (const PROPVARIANT *)this + 4);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18007a410  push    rbx
0x18007a412  push    rbp
0x18007a413  push    rsi
0x18007a414  push    rdi
0x18007a415  sub     rsp, 28h
0x18007a419  xor     eax, eax
0x18007a41b  mov     rsi, rdx
0x18007a41e  mov     [rdx], ax
0x18007a421  mov     rdi, rcx
0x18007a424  cmp     [rcx+40h], al
0x18007a427  jnz     short loc_18007A43A
0x18007a429  lea     rdx, [rcx+20h]; pvarSrc
0x18007a42d  mov     rcx, rsi; pvarDest
0x18007a430  call    cs:__imp_PropVariantCopy
0x18007a436  mov     ebp, eax
0x18007a438  jmp     short loc_18007A468
0x18007a43a  add     rcx, 38h ; '8'
0x18007a43e  call    ?InitPropVariantFromPropVariantDSA@@YAJPEAV?$CDSA@UtagPROPVARIANT@@@@PEAUtagPROPVARIANT@@@Z; InitPropVariantFromPropVariantDSA(CDSA<tagPROPVARIANT> *,tagPROPVARIANT *)
0x18007a443  mov     ebp, eax
0x18007a445  test    eax, eax
0x18007a447  js      short loc_18007A468
0x18007a449  lea     rcx, [rdi+20h]; pvar
0x18007a44d  call    cs:__imp_PropVariantClear
0x18007a453  mov     rdx, rsi; pvarSrc
0x18007a456  lea     rcx, [rdi+20h]; pvarDest
0x18007a45a  call    cs:__imp_PropVariantCopy
0x18007a460  test    eax, eax
0x18007a462  js      short loc_18007A468
0x18007a464  mov     byte ptr [rdi+40h], 0
0x18007a468  mov     eax, ebp
0x18007a46a  add     rsp, 28h
0x18007a46e  pop     rdi
0x18007a46f  pop     rsi
0x18007a470  pop     rbp
0x18007a471  pop     rbx
0x18007a472  retn
```
