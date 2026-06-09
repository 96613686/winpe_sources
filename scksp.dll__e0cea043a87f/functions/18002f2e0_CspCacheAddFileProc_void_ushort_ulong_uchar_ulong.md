# CspCacheAddFileProc(void *,ushort *,ulong,uchar *,ulong)

- ea: `0x18002f2e0`
- end: `0x18002f42e`
- name: `?CspCacheAddFileProc@@YAKPEAXPEAGKPEAEK@Z`
- size: `334`
- prototype: `unsigned int(void *, unsigned __int16 *, unsigned int, unsigned __int8 *, unsigned int)`
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
- `0x18002f2e0`
- `0x18002fc8c`
- `0x18003c240`

## string_xrefs

- `0x18002f3ac`: `Cached_CardmodFile`

## pseudocode

```c
__int64 __fastcall CspCacheAddFileProc(
        void *a1,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int8 *a4,
        unsigned int Size)
{
  unsigned int v8; // ebx
  _DWORD *v9; // rax
  __int64 v10; // rcx
  _DWORD *v11; // rdi
  void *v13; // [rsp+30h] [rbp-278h] BYREF
  int v14; // [rsp+38h] [rbp-270h]
  int v15; // [rsp+3Ch] [rbp-26Ch]
  int v16; // [rsp+40h] [rbp-268h]
  unsigned __int16 v17[278]; // [rsp+44h] [rbp-264h] BYREF

  v8 = 0;
  memset_0(&v13, 0, 0x238u);
  if ( Size && a4 )
  {
    v9 = MIDL_user_allocate(Size + 16LL);
    v11 = v9;
    if ( v9 )
    {
      memcpy_0(v9 + 4, a4, Size);
      v11[3] = Size;
      StringCbPrintfW(v17, 0x104u, L"%s\\%s", L"Cached_CardmodFile", a2);
      v14 = 7;
      v16 = 1;
      v15 = 1;
      v13 = a1;
      v8 = CspAddCardCacheItem((struct _CARD_CACHE_QUERY_INFO *)&v13, v11);
      CspFreeH(v11);
    }
    else
    {
      WppTraceIndent(v10, 2u);
      v8 = 8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
          WPP_pszIndent);
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18002f2e0  mov     [rsp+arg_0], rbx
0x18002f2e5  push    rbp
0x18002f2e6  push    rsi
0x18002f2e7  push    rdi
0x18002f2e8  push    r14
0x18002f2ea  push    r15
0x18002f2ec  sub     rsp, 280h
0x18002f2f3  mov     rax, cs:__security_cookie
0x18002f2fa  xor     rax, rsp
0x18002f2fd  mov     [rsp+2A8h+var_38], rax
0x18002f305  mov     esi, dword ptr [rsp+2A8h+Size]
0x18002f30c  mov     r15, rdx
0x18002f30f  mov     r14, rcx
0x18002f312  xor     edx, edx; Val
0x18002f314  lea     rcx, [rsp+2A8h+var_278]; void *
0x18002f319  mov     r8d, 238h; Size
0x18002f31f  mov     rbp, r9
0x18002f322  xor     ebx, ebx
0x18002f324  call    memset_0
0x18002f329  test    esi, esi
0x18002f32b  jz      loc_18002F405
0x18002f331  test    rbp, rbp
0x18002f334  jz      loc_18002F405
0x18002f33a  lea     rcx, [rsi+10h]; size
0x18002f33e  call    MIDL_user_allocate
0x18002f343  mov     rdi, rax
0x18002f346  test    rax, rax
0x18002f349  jnz     short loc_18002F39D
0x18002f34b  lea     edx, [rbx+2]
0x18002f34e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002f353  lea     ebx, [rdi+8]
0x18002f356  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f35d  lea     rax, WPP_GLOBAL_Control
0x18002f364  cmp     rcx, rax
0x18002f367  jz      loc_18002F405
0x18002f36d  test    byte ptr [rcx+1Ch], 1
0x18002f371  jz      loc_18002F405
0x18002f377  cmp     byte ptr [rcx+19h], 2
0x18002f37b  jb      loc_18002F405
0x18002f381  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002f388  lea     edx, [rdi+13h]
0x18002f38b  mov     rcx, [rcx+10h]
0x18002f38f  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x18002f396  call    WPP_SF_s
0x18002f39b  jmp     short loc_18002F405
0x18002f39d  lea     rcx, [rax+10h]; void *
0x18002f3a1  mov     r8, rsi; Size
0x18002f3a4  mov     rdx, rbp; Src
0x18002f3a7  call    memcpy_0
0x18002f3ac  lea     r9, aCachedCardmodf; "Cached_CardmodFile"
0x18002f3b3  mov     [rdi+0Ch], esi
0x18002f3b6  lea     r8, aSS; "%s\\%s"
0x18002f3bd  mov     [rsp+2A8h+var_288], r15
0x18002f3c2  mov     edx, 104h; unsigned __int64
0x18002f3c7  lea     rcx, [rsp+2A8h+var_264]; unsigned __int16 *
0x18002f3cc  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002f3d1  mov     rdx, rdi; Destination
0x18002f3d4  mov     [rsp+2A8h+var_270], 7
0x18002f3dc  lea     rcx, [rsp+2A8h+var_278]; struct _CARD_CACHE_QUERY_INFO *
0x18002f3e1  mov     [rsp+2A8h+var_268], 1
0x18002f3e9  mov     [rsp+2A8h+var_26C], 1
0x18002f3f1  mov     [rsp+2A8h+var_278], r14
0x18002f3f6  call    CspAddCardCacheItem
0x18002f3fb  mov     ebx, eax
0x18002f3fd  mov     rcx, rdi
0x18002f400  call    CspFreeH
0x18002f405  mov     eax, ebx
0x18002f407  mov     rcx, [rsp+2A8h+var_38]
0x18002f40f  xor     rcx, rsp; StackCookie
0x18002f412  call    __security_check_cookie
0x18002f417  mov     rbx, [rsp+2A8h+arg_0]
0x18002f41f  add     rsp, 280h
0x18002f426  pop     r15
0x18002f428  pop     r14
0x18002f42a  pop     rdi
0x18002f42b  pop     rsi
0x18002f42c  pop     rbp
0x18002f42d  retn
```
