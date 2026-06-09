# ScCacheDeleteItem

- ea: `0x180037120`
- end: `0x180037250`
- name: `ScCacheDeleteItem`
- size: `304`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1800308f4`
- `0x180030950`
- `0x180030c84`

## callees

- `0x18000a408`
- `0x18000a590`
- `0x180013734`
- `0x180036f7c`
- `0x180037120`
- `0x180038484`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800371f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800371f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800371b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800371b2`

## pseudocode

```c
__int64 __fastcall ScCacheDeleteItem(LPCRITICAL_SECTION lpCriticalSection, __int64 a2, __int64 a3)
{
  PVOID v6; // rcx
  __int64 v7; // rax
  __int64 v8; // r8
  unsigned int Item; // eax
  unsigned int v10; // ebx
  __int128 v12; // [rsp+30h] [rbp-58h] BYREF
  int v13; // [rsp+40h] [rbp-48h] BYREF
  __int64 v14; // [rsp+48h] [rbp-40h]
  int v15; // [rsp+50h] [rbp-38h]
  __int64 v16; // [rsp+58h] [rbp-30h]

  WppTraceIndent((__int64)lpCriticalSection, 0);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
  }
  v12 = 0;
  if ( a3 && a2 )
  {
    v13 = 16;
    v7 = -1;
    v14 = a2;
    do
      ++v7;
    while ( *(_WORD *)(a3 + 2 * v7) );
    v16 = a3;
    v15 = 2 * v7;
    EnterCriticalSection(lpCriticalSection);
    Item = CacheGetItem(lpCriticalSection[1].DebugInfo, &v13, v8, &v12);
    v10 = Item;
    if ( Item )
    {
      if ( Item == 1168 )
        v10 = -2146434960;
    }
    else
    {
      I_ServerCacheRemoveItem(lpCriticalSection, *((_QWORD *)&v12 + 1), &v13);
    }
    LeaveCriticalSection(lpCriticalSection);
  }
  else
  {
    v10 = -2146435068;
  }
  WppTraceIndent((__int64)v6, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      42,
      (unsigned int)WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
      WPP_pszIndent,
      v10);
  }
  return v10;
}

```

## disassembly

```asm
0x180037120  push    rbx
0x180037122  push    rbp
0x180037123  push    rsi
0x180037124  push    rdi
0x180037125  push    r14
0x180037127  sub     rsp, 60h
0x18003712b  mov     rbx, rdx
0x18003712e  mov     rsi, r8
0x180037131  xor     edx, edx
0x180037133  mov     rdi, rcx
0x180037136  call    WppTraceIndent
0x18003713b  mov     rcx, cs:WPP_GLOBAL_Control
0x180037142  lea     r14, WPP_GLOBAL_Control
0x180037149  cmp     rcx, r14
0x18003714c  jz      short loc_180037176
0x18003714e  test    byte ptr [rcx+1Ch], 2
0x180037152  jz      short loc_180037176
0x180037154  cmp     byte ptr [rcx+19h], 5
0x180037158  jb      short loc_180037176
0x18003715a  mov     r9, cs:WPP_pszIndent
0x180037161  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180037168  mov     rcx, [rcx+10h]
0x18003716c  mov     edx, 28h ; '('
0x180037171  call    WPP_SF_s
0x180037176  xor     ebp, ebp
0x180037178  xorps   xmm0, xmm0
0x18003717b  movups  [rsp+88h+var_58], xmm0
0x180037180  test    rsi, rsi
0x180037183  jz      short loc_1800371FC
0x180037185  test    rbx, rbx
0x180037188  jz      short loc_1800371FC
0x18003718a  mov     [rsp+88h+var_48], 10h
0x180037192  or      rax, 0FFFFFFFFFFFFFFFFh
0x180037196  mov     [rsp+88h+var_40], rbx
0x18003719b  inc     rax
0x18003719e  cmp     [rsi+rax*2], bp
0x1800371a2  jnz     short loc_18003719B
0x1800371a4  add     eax, eax
0x1800371a6  mov     [rsp+88h+var_30], rsi
0x1800371ab  mov     rcx, rdi; lpCriticalSection
0x1800371ae  mov     [rsp+88h+var_38], eax
0x1800371b2  call    cs:__imp_EnterCriticalSection
0x1800371b8  mov     rcx, [rdi+28h]
0x1800371bc  lea     r9, [rsp+88h+var_58]
0x1800371c1  lea     rdx, [rsp+88h+var_48]
0x1800371c6  call    CacheGetItem
0x1800371cb  mov     ebx, eax
0x1800371cd  test    eax, eax
0x1800371cf  jz      short loc_1800371DF
0x1800371d1  cmp     eax, 490h
0x1800371d6  jnz     short loc_1800371F1
0x1800371d8  mov     ebx, 80100070h
0x1800371dd  jmp     short loc_1800371F1
0x1800371df  mov     rdx, qword ptr [rsp+88h+var_58+8]
0x1800371e4  lea     r8, [rsp+88h+var_48]
0x1800371e9  mov     rcx, rdi
0x1800371ec  call    I_ServerCacheRemoveItem
0x1800371f1  mov     rcx, rdi; lpCriticalSection
0x1800371f4  call    cs:__imp_LeaveCriticalSection
0x1800371fa  jmp     short loc_180037201
0x1800371fc  mov     ebx, 80100004h
0x180037201  mov     edx, 1
0x180037206  call    WppTraceIndent
0x18003720b  mov     rcx, cs:WPP_GLOBAL_Control
0x180037212  cmp     rcx, r14
0x180037215  jz      short loc_180037243
0x180037217  test    byte ptr [rcx+1Ch], 2
0x18003721b  jz      short loc_180037243
0x18003721d  cmp     byte ptr [rcx+19h], 5
0x180037221  jb      short loc_180037243
0x180037223  mov     r9, cs:WPP_pszIndent
0x18003722a  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180037231  mov     rcx, [rcx+10h]
0x180037235  mov     edx, 2Ah ; '*'
0x18003723a  mov     [rsp+88h+var_68], ebx
0x18003723e  call    WPP_SF_sd
0x180037243  mov     eax, ebx
0x180037245  add     rsp, 60h
0x180037249  pop     r14
0x18003724b  pop     rdi
0x18003724c  pop     rsi
0x18003724d  pop     rbp
0x18003724e  pop     rbx
0x18003724f  retn
```
