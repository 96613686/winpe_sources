# GetCachedCardData

- ea: `0x180030378`
- end: `0x1800304f9`
- name: `GetCachedCardData`
- size: `385`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, unsigned int, unsigned int, _QWORD *, _DWORD *, _DWORD *)`
- caller_count: `5`
- callee_count: `10`
- tags: ``

## callers

- `0x18002c67c`
- `0x18002c80c`
- `0x18002c99c`
- `0x18002d7f0`
- `0x18002de34`

## callees

- `0x180009e76`
- `0x180009e82`
- `0x18000d9d0`
- `0x180011fd8`
- `0x180013734`
- `0x180013c94`
- `0x18002b140`
- `0x18002fe08`
- `0x180030378`
- `0x18003c240`

## pseudocode

```c
__int64 __fastcall GetCachedCardData(
        __int64 a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        _QWORD *a5,
        _DWORD *a6,
        _DWORD *a7)
{
  unsigned int CardCacheForItem; // esi
  size_t v12; // rbx
  void *v13; // rax
  __int64 v14; // rcx
  void *v15; // rdi
  __int64 v17; // [rsp+20h] [rbp-288h] BYREF
  unsigned __int64 v18; // [rsp+28h] [rbp-280h]
  _BYTE v19[4]; // [rsp+30h] [rbp-278h] BYREF
  unsigned __int16 v20[266]; // [rsp+34h] [rbp-274h] BYREF
  _DWORD *v21; // [rsp+248h] [rbp-60h]

  memset_0(v19, 0, 0x228u);
  if ( !a5 || !a6 )
    return 2148532228LL;
  *a5 = 0;
  *a6 = 0;
  v18 = __PAIR64__(a4, a3);
  v17 = a1;
  StringCbCopyW(v20, 0x208u, a2);
  CardCacheForItem = CspQueryCardCacheForItem((struct _CARD_CACHE_QUERY_INFO *)&v17);
  if ( CardCacheForItem )
  {
    v15 = 0;
    LODWORD(v12) = 0;
  }
  else
  {
    v12 = (unsigned int)v21[3];
    v13 = MIDL_user_allocate(v12);
    v15 = v13;
    if ( !v13 )
    {
      WppTraceIndent(v14, 2);
      CardCacheForItem = 8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
          WPP_pszIndent,
          v17,
          v18);
      }
      goto LABEL_13;
    }
    memcpy_0(v13, v21 + 4, v12);
    if ( a7 )
      *a7 = v21[2];
  }
  *a5 = v15;
  *a6 = v12;
LABEL_13:
  if ( v21 )
    CspFreeH(v21);
  return CardCacheForItem;
}

```

## disassembly

```asm
0x180030378  push    rbx
0x18003037a  push    rbp
0x18003037b  push    rsi
0x18003037c  push    rdi
0x18003037d  push    r12
0x18003037f  push    r14
0x180030381  push    r15
0x180030383  sub     rsp, 270h
0x18003038a  mov     rax, cs:__security_cookie
0x180030391  xor     rax, rsp
0x180030394  mov     [rsp+2A8h+var_48], rax
0x18003039c  mov     r15, [rsp+2A8h+arg_20]
0x1800303a4  mov     esi, r8d
0x1800303a7  mov     r14, [rsp+2A8h+arg_28]
0x1800303af  mov     rdi, rdx
0x1800303b2  mov     rbp, [rsp+2A8h+arg_30]
0x1800303ba  mov     rbx, rcx
0x1800303bd  xor     edx, edx; Val
0x1800303bf  lea     rcx, [rsp+2A8h+var_278]; void *
0x1800303c4  mov     r8d, 228h; Size
0x1800303ca  mov     r12d, r9d
0x1800303cd  call    memset_0
0x1800303d2  test    r15, r15
0x1800303d5  jz      loc_1800304D2
0x1800303db  test    r14, r14
0x1800303de  jz      loc_1800304D2
0x1800303e4  mov     qword ptr [r15], 0
0x1800303eb  lea     rcx, [rsp+2A8h+var_274]; unsigned __int16 *
0x1800303f0  mov     r8, rdi; unsigned __int16 *
0x1800303f3  mov     dword ptr [r14], 0
0x1800303fa  mov     edx, 208h; unsigned __int64
0x1800303ff  mov     [rsp+2A8h+var_280], esi
0x180030403  mov     [rsp+2A8h+var_27C], r12d
0x180030408  mov     [rsp+2A8h+var_288], rbx
0x18003040d  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180030412  lea     rcx, [rsp+2A8h+var_288]; struct _CARD_CACHE_QUERY_INFO *
0x180030417  call    CspQueryCardCacheForItem
0x18003041c  mov     esi, eax
0x18003041e  test    eax, eax
0x180030420  jnz     loc_1800304B2
0x180030426  mov     rcx, [rsp+2A8h+var_60]
0x18003042e  mov     ebx, [rcx+0Ch]
0x180030431  mov     ecx, ebx; size
0x180030433  call    MIDL_user_allocate
0x180030438  mov     rdi, rax
0x18003043b  test    rax, rax
0x18003043e  jnz     short loc_180030486
0x180030440  lea     edx, [rsi+2]
0x180030443  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180030448  lea     esi, [rdi+8]
0x18003044b  mov     rcx, cs:WPP_GLOBAL_Control
0x180030452  lea     rax, WPP_GLOBAL_Control
0x180030459  cmp     rcx, rax
0x18003045c  jz      short loc_1800304BC
0x18003045e  test    byte ptr [rcx+1Ch], 1
0x180030462  jz      short loc_1800304BC
0x180030464  cmp     byte ptr [rcx+19h], 2
0x180030468  jb      short loc_1800304BC
0x18003046a  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180030471  lea     edx, [rdi+16h]
0x180030474  mov     rcx, [rcx+10h]
0x180030478  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x18003047f  call    WPP_SF_s
0x180030484  jmp     short loc_1800304BC
0x180030486  mov     rdx, [rsp+2A8h+var_60]
0x18003048e  mov     r8, rbx; Size
0x180030491  add     rdx, 10h; Src
0x180030495  mov     rcx, rax; void *
0x180030498  call    memcpy_0
0x18003049d  test    rbp, rbp
0x1800304a0  jz      short loc_1800304B6
0x1800304a2  mov     rax, [rsp+2A8h+var_60]
0x1800304aa  mov     ecx, [rax+8]
0x1800304ad  mov     [rbp+0], ecx
0x1800304b0  jmp     short loc_1800304B6
0x1800304b2  xor     edi, edi
0x1800304b4  xor     ebx, ebx
0x1800304b6  mov     [r15], rdi
0x1800304b9  mov     [r14], ebx
0x1800304bc  mov     rcx, [rsp+2A8h+var_60]
0x1800304c4  test    rcx, rcx
0x1800304c7  jz      short loc_1800304CE
0x1800304c9  call    CspFreeH
0x1800304ce  mov     eax, esi
0x1800304d0  jmp     short loc_1800304D7
0x1800304d2  mov     eax, 80100004h
0x1800304d7  mov     rcx, [rsp+2A8h+var_48]
0x1800304df  xor     rcx, rsp; StackCookie
0x1800304e2  call    __security_check_cookie
0x1800304e7  add     rsp, 270h
0x1800304ee  pop     r15
0x1800304f0  pop     r14
0x1800304f2  pop     r12
0x1800304f4  pop     rdi
0x1800304f5  pop     rsi
0x1800304f6  pop     rbp
0x1800304f7  pop     rbx
0x1800304f8  retn
```
