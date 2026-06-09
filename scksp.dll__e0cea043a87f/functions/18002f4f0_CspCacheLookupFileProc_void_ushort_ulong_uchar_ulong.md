# CspCacheLookupFileProc(void *,ushort *,ulong,uchar * *,ulong *)

- ea: `0x18002f4f0`
- end: `0x18002f644`
- name: `?CspCacheLookupFileProc@@YAKPEAXPEAGKPEAPEAEPEAK@Z`
- size: `340`
- prototype: `unsigned int __fastcall(void *, unsigned __int16 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180009e76`
- `0x180009e82`
- `0x18000d9d0`
- `0x180011fd8`
- `0x180013734`
- `0x18002b140`
- `0x18002cda8`
- `0x18002f4f0`
- `0x18002fe08`
- `0x18003c240`

## string_xrefs

- `0x18002f53c`: `Cached_CardmodFile`

## pseudocode

```c
__int64 __fastcall CspCacheLookupFileProc(
        void *a1,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  unsigned int CardCacheForItem; // ebx
  unsigned int v9; // edx
  unsigned __int8 *v10; // rax
  __int64 v11; // rcx
  void *v13; // [rsp+30h] [rbp-268h] BYREF
  int v14; // [rsp+38h] [rbp-260h]
  int v15; // [rsp+3Ch] [rbp-25Ch]
  int v16; // [rsp+40h] [rbp-258h]
  unsigned __int16 v17[266]; // [rsp+44h] [rbp-254h] BYREF
  __int64 v18; // [rsp+258h] [rbp-40h]

  memset_0(&v13, 0, 0x238u);
  *a4 = 0;
  *a5 = 0;
  StringCbPrintfW(v17, 0x104u, L"%s\\%s", L"Cached_CardmodFile", a2);
  v14 = 7;
  v16 = 1;
  v15 = 1;
  v13 = a1;
  CardCacheForItem = CspQueryCardCacheForItem((struct _CARD_CACHE_QUERY_INFO *)&v13);
  if ( !CardCacheForItem )
  {
    v9 = *(_DWORD *)(v18 + 12);
    *a5 = v9;
    v10 = (unsigned __int8 *)MIDL_user_allocate(v9);
    *a4 = v10;
    if ( v10 )
    {
      memcpy_0(v10, (const void *)(v18 + 16), *a5);
    }
    else
    {
      WppTraceIndent(v11, 2u);
      CardCacheForItem = 8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
          WPP_pszIndent);
      }
    }
  }
  if ( v18 )
    CspFreeH(v18);
  return CardCacheForItem;
}

```

## disassembly

```asm
0x18002f4f0  mov     [rsp+arg_0], rbx
0x18002f4f5  push    rsi
0x18002f4f6  push    rdi
0x18002f4f7  push    r14
0x18002f4f9  sub     rsp, 280h
0x18002f500  mov     rax, cs:__security_cookie
0x18002f507  xor     rax, rsp
0x18002f50a  mov     [rsp+298h+var_28], rax
0x18002f512  mov     rsi, [rsp+298h+arg_20]
0x18002f51a  mov     rbx, rdx
0x18002f51d  mov     rdi, rcx
0x18002f520  xor     edx, edx; Val
0x18002f522  lea     rcx, [rsp+298h+var_268]; void *
0x18002f527  mov     r8d, 238h; Size
0x18002f52d  mov     r14, r9
0x18002f530  call    memset_0
0x18002f535  mov     qword ptr [r14], 0
0x18002f53c  lea     r9, aCachedCardmodf; "Cached_CardmodFile"
0x18002f543  lea     r8, aSS; "%s\\%s"
0x18002f54a  mov     dword ptr [rsi], 0
0x18002f550  mov     edx, 104h; unsigned __int64
0x18002f555  mov     [rsp+298h+var_278], rbx
0x18002f55a  lea     rcx, [rsp+298h+var_254]; unsigned __int16 *
0x18002f55f  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002f564  lea     rcx, [rsp+298h+var_268]; struct _CARD_CACHE_QUERY_INFO *
0x18002f569  mov     [rsp+298h+var_260], 7
0x18002f571  mov     [rsp+298h+var_258], 1
0x18002f579  mov     [rsp+298h+var_25C], 1
0x18002f581  mov     [rsp+298h+var_268], rdi
0x18002f586  call    CspQueryCardCacheForItem
0x18002f58b  mov     ebx, eax
0x18002f58d  test    eax, eax
0x18002f58f  jnz     short loc_18002F60C
0x18002f591  mov     rcx, [rsp+298h+var_40]
0x18002f599  mov     edx, [rcx+0Ch]
0x18002f59c  mov     ecx, edx; size
0x18002f59e  mov     [rsi], edx
0x18002f5a0  call    MIDL_user_allocate
0x18002f5a5  mov     [r14], rax
0x18002f5a8  test    rax, rax
0x18002f5ab  jnz     short loc_18002F5F5
0x18002f5ad  lea     edx, [rbx+2]
0x18002f5b0  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002f5b5  mov     ebx, 8
0x18002f5ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f5c1  lea     rax, WPP_GLOBAL_Control
0x18002f5c8  cmp     rcx, rax
0x18002f5cb  jz      short loc_18002F60C
0x18002f5cd  test    byte ptr [rcx+1Ch], 1
0x18002f5d1  jz      short loc_18002F60C
0x18002f5d3  cmp     byte ptr [rcx+19h], 2
0x18002f5d7  jb      short loc_18002F60C
0x18002f5d9  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002f5e0  lea     edx, [rbx+0Ch]
0x18002f5e3  mov     rcx, [rcx+10h]
0x18002f5e7  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x18002f5ee  call    WPP_SF_s
0x18002f5f3  jmp     short loc_18002F60C
0x18002f5f5  mov     rdx, [rsp+298h+var_40]
0x18002f5fd  mov     rcx, rax; void *
0x18002f600  mov     r8d, [rsi]; Size
0x18002f603  add     rdx, 10h; Src
0x18002f607  call    memcpy_0
0x18002f60c  mov     rcx, [rsp+298h+var_40]
0x18002f614  test    rcx, rcx
0x18002f617  jz      short loc_18002F61E
0x18002f619  call    CspFreeH
0x18002f61e  mov     eax, ebx
0x18002f620  mov     rcx, [rsp+298h+var_28]
0x18002f628  xor     rcx, rsp; StackCookie
0x18002f62b  call    __security_check_cookie
0x18002f630  mov     rbx, [rsp+298h+arg_0]
0x18002f638  add     rsp, 280h
0x18002f63f  pop     r14
0x18002f641  pop     rdi
0x18002f642  pop     rsi
0x18002f643  retn
```
