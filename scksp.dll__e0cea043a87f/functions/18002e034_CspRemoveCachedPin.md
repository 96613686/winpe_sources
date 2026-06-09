# CspRemoveCachedPin

- ea: `0x18002e034`
- end: `0x18002e177`
- name: `CspRemoveCachedPin`
- size: `323`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x1800146c4`
- `0x18001b6f8`
- `0x180031a94`
- `0x180035d6c`

## callees

- `0x180009e82`
- `0x180011fd8`
- `0x180013734`
- `0x18002cda8`
- `0x18002e034`
- `0x1800308f4`
- `0x1800395f4`
- `0x18003c240`

## string_xrefs

- `0x18002e0c4`: `Cached_Pin`

## pseudocode

```c
char *__fastcall CspRemoveCachedPin(__int64 a1, unsigned int a2, unsigned int a3)
{
  __int64 v6; // rcx
  __int64 v7; // rcx
  char *result; // rax
  int v9; // [rsp+20h] [rbp-278h]
  __int64 v10; // [rsp+30h] [rbp-268h] BYREF
  int v11; // [rsp+38h] [rbp-260h]
  int v12; // [rsp+3Ch] [rbp-25Ch]
  unsigned __int16 v13[278]; // [rsp+44h] [rbp-254h] BYREF

  memset_0(&v10, 0, 0x238u);
  WppTraceIndent(v6, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids, WPP_pszIndent);
  }
  memset_0(&v10, 0, 0x238u);
  v9 = a2;
  StringCbPrintfW(v13, 0x104u, L"%s\\%d", L"Cached_Pin", v9);
  v11 = 1;
  v12 = 1;
  v10 = a1;
  MyCacheDeleteItem(&v10);
  PinCacheFlush(a1 + 584, a2, a3);
  result = WppTraceIndent(v7, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    return (char *)WPP_SF_s(
                     *((_QWORD *)WPP_GLOBAL_Control + 2),
                     19,
                     WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
                     WPP_pszIndent);
  }
  return result;
}

```

## disassembly

```asm
0x18002e034  mov     [rsp+arg_10], rbx
0x18002e039  push    rsi
0x18002e03a  push    rdi
0x18002e03b  push    r14
0x18002e03d  sub     rsp, 280h
0x18002e044  mov     rax, cs:__security_cookie
0x18002e04b  xor     rax, rsp
0x18002e04e  mov     [rsp+298h+var_28], rax
0x18002e056  mov     esi, r8d
0x18002e059  mov     edi, edx
0x18002e05b  mov     rbx, rcx
0x18002e05e  xor     edx, edx; Val
0x18002e060  mov     r8d, 238h; Size
0x18002e066  lea     rcx, [rsp+298h+var_268]; void *
0x18002e06b  call    memset_0
0x18002e070  xor     edx, edx
0x18002e072  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002e077  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e07e  lea     r14, WPP_GLOBAL_Control
0x18002e085  cmp     rcx, r14
0x18002e088  jz      short loc_18002E0B2
0x18002e08a  test    byte ptr [rcx+1Ch], 2
0x18002e08e  jz      short loc_18002E0B2
0x18002e090  cmp     byte ptr [rcx+19h], 5
0x18002e094  jb      short loc_18002E0B2
0x18002e096  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002e09d  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18002e0a4  mov     rcx, [rcx+10h]
0x18002e0a8  mov     edx, 12h
0x18002e0ad  call    WPP_SF_s
0x18002e0b2  xor     edx, edx; Val
0x18002e0b4  lea     rcx, [rsp+298h+var_268]; void *
0x18002e0b9  mov     r8d, 238h; Size
0x18002e0bf  call    memset_0
0x18002e0c4  lea     r9, aCachedPin; "Cached_Pin"
0x18002e0cb  mov     [rsp+298h+var_278], edi
0x18002e0cf  lea     r8, aSD; "%s\\%d"
0x18002e0d6  mov     edx, 104h; unsigned __int64
0x18002e0db  lea     rcx, [rsp+298h+var_254]; unsigned __int16 *
0x18002e0e0  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e0e5  lea     rcx, [rsp+298h+var_268]
0x18002e0ea  mov     [rsp+298h+var_260], 1
0x18002e0f2  mov     [rsp+298h+var_25C], 1
0x18002e0fa  mov     [rsp+298h+var_268], rbx
0x18002e0ff  call    MyCacheDeleteItem
0x18002e104  lea     rcx, [rbx+248h]
0x18002e10b  mov     r8d, esi
0x18002e10e  mov     edx, edi
0x18002e110  call    PinCacheFlush
0x18002e115  mov     edx, 1
0x18002e11a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002e11f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e126  cmp     rcx, r14
0x18002e129  jz      short loc_18002E153
0x18002e12b  test    byte ptr [rcx+1Ch], 2
0x18002e12f  jz      short loc_18002E153
0x18002e131  cmp     byte ptr [rcx+19h], 5
0x18002e135  jb      short loc_18002E153
0x18002e137  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002e13e  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18002e145  mov     rcx, [rcx+10h]
0x18002e149  mov     edx, 13h
0x18002e14e  call    WPP_SF_s
0x18002e153  mov     rcx, [rsp+298h+var_28]
0x18002e15b  xor     rcx, rsp; StackCookie
0x18002e15e  call    __security_check_cookie
0x18002e163  mov     rbx, [rsp+298h+arg_10]
0x18002e16b  add     rsp, 280h
0x18002e172  pop     r14
0x18002e174  pop     rdi
0x18002e175  pop     rsi
0x18002e176  retn
```
