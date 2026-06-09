# _myVariantCopy(tagPROPVARIANT *,tagPROPVARIANT *)

- ea: `0x18001a7d0`
- end: `0x18001a87a`
- name: `?_myVariantCopy@@YAJPEAUtagPROPVARIANT@@0@Z`
- size: `170`
- prototype: `__int64 __fastcall(struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a01c`

## callees

- `0x18001a154`
- `0x18001a7d0`

## string_xrefs

- `0x18001a800`: `onecore\ds\security\eas\policyengine\common.cpp`

## pseudocode

```c
__int64 __fastcall _myVariantCopy(struct tagPROPVARIANT *a1, struct tagPROPVARIANT *a2)
{
  unsigned int v2; // ebx
  int v4; // [rsp+20h] [rbp-28h]
  int v5; // [rsp+20h] [rbp-28h]

  if ( !a1 )
  {
    v2 = -1073741811;
    v4 = 362;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      3221225485LL,
      L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
      v4,
      L"Null Arg",
      &pszPassword);
    return v2;
  }
  a1->vt = 0;
  if ( !a2 )
    return 0;
  if ( a2->vt == 11 )
  {
    a1->iVal = a2->iVal;
    goto LABEL_10;
  }
  if ( a2->vt == 19 )
  {
    a1->lVal = a2->lVal;
LABEL_10:
    a1->vt = a2->vt;
    return 0;
  }
  v2 = -1073741637;
  v5 = 382;
  DbgPrintfW(
    1u,
    L"(0x%08x) %ws:%u : %ws:%ws\n",
    3221225659LL,
    L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
    v5,
    L"unsupported type",
    &pszPassword);
  return v2;
}

```

## disassembly

```asm
0x18001a7d0  push    rbx
0x18001a7d2  sub     rsp, 40h
0x18001a7d6  test    rcx, rcx
0x18001a7d9  jnz     short loc_18001A81D
0x18001a7db  lea     rax, pszPassword
0x18001a7e2  mov     ebx, 0C000000Dh
0x18001a7e7  mov     [rsp+48h+var_18], rax
0x18001a7ec  lea     rax, aNullArg; "Null Arg"
0x18001a7f3  mov     [rsp+48h+var_20], rax
0x18001a7f8  mov     [rsp+48h+var_28], 16Ah
0x18001a800  lea     r9, aOnecoreDsSecur; "onecore\\ds\\security\\eas\\policyengin"...
0x18001a807  mov     r8d, ebx
0x18001a80a  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18001a811  mov     ecx, 1; unsigned int
0x18001a816  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18001a81b  jmp     short loc_18001A872
0x18001a81d  xor     eax, eax
0x18001a81f  mov     [rcx], ax
0x18001a822  test    rdx, rdx
0x18001a825  jz      short loc_18001A870
0x18001a827  cmp     word ptr [rdx], 0Bh
0x18001a82b  jz      short loc_18001A862
0x18001a82d  cmp     word ptr [rdx], 13h
0x18001a831  jz      short loc_18001A85A
0x18001a833  lea     rax, pszPassword
0x18001a83a  mov     ebx, 0C00000BBh
0x18001a83f  mov     [rsp+48h+var_18], rax
0x18001a844  lea     rax, aUnsupportedTyp; "unsupported type"
0x18001a84b  mov     [rsp+48h+var_20], rax
0x18001a850  mov     [rsp+48h+var_28], 17Eh
0x18001a858  jmp     short loc_18001A800
0x18001a85a  mov     eax, [rdx+8]
0x18001a85d  mov     [rcx+8], eax
0x18001a860  jmp     short loc_18001A86A
0x18001a862  movzx   eax, word ptr [rdx+8]
0x18001a866  mov     [rcx+8], ax
0x18001a86a  movzx   eax, word ptr [rdx]
0x18001a86d  mov     [rcx], ax
0x18001a870  xor     ebx, ebx
0x18001a872  mov     eax, ebx
0x18001a874  add     rsp, 40h
0x18001a878  pop     rbx
0x18001a879  retn
```
