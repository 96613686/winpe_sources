# MyCacheAddItem(_CARD_CACHE_QUERY_INFO *,_CRYPTOAPI_BLOB *)

- ea: `0x18002f830`
- end: `0x18002f95e`
- name: `?MyCacheAddItem@@YAKPEAU_CARD_CACHE_QUERY_INFO@@PEAU_CRYPTOAPI_BLOB@@@Z`
- size: `302`
- prototype: `unsigned int __fastcall(struct _CARD_CACHE_QUERY_INFO *, struct _CRYPTOAPI_BLOB *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002fc8c`

## callees

- `0x180011fd8`
- `0x18002eb6c`
- `0x18002f830`
- `0x180037a4c`

## import_xrefs

- `WinSCard!SCardWriteCacheW` at `0x18002f8fc`
- `WinSCard!SCardWriteCacheW` at `0x18002f8fc`

## pseudocode

```c
__int64 __fastcall MyCacheAddItem(struct _CARD_CACHE_QUERY_INFO *a1, struct _CRYPTOAPI_BLOB *a2)
{
  __int64 v3; // rdx
  __int64 v4; // r10
  unsigned int v5; // ebx
  int v6; // r9d
  DWORD v7; // r8d
  int v8; // eax
  struct _RTL_CRITICAL_SECTION *v10; // r10

  v3 = *(_QWORD *)a1;
  v4 = *(_QWORD *)(*(_QWORD *)a1 + 8LL);
  if ( v4 )
  {
    v7 = 0;
    if ( (*((_BYTE *)a1 + 8) & 2) != 0 )
      v7 = *((unsigned __int16 *)a1 + 271);
    if ( (*((_BYTE *)a1 + 8) & 4) != 0 )
      v7 += *((unsigned __int16 *)a1 + 272);
    v8 = *((_DWORD *)a1 + 4);
    if ( v8 )
    {
      if ( v8 != 1 )
        return 1359;
      v10 = *(struct _RTL_CRITICAL_SECTION **)(v3 + 680);
    }
    else
    {
      if ( *((_DWORD *)a1 + 2) != 1 && (*(_DWORD *)v4 < 6u || *(_DWORD *)(v3 + 696) != 2) )
        return (unsigned int)SCardWriteCacheW(
                               *(_QWORD *)(v4 + 96),
                               *(UUID **)(v3 + 552),
                               v7,
                               (LPWSTR)a1 + 10,
                               a2->pbData,
                               a2->cbData);
      v10 = *(struct _RTL_CRITICAL_SECTION **)(v3 + 672);
    }
    return (unsigned int)ScCacheWrite(v10, 0, 0, a2->pbData, a2->cbData);
  }
  v5 = 87;
  WppTraceIndent(a1, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_ss(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
      v6,
      (__int64)"pInfo->pCardState->pCardData");
  }
  return v5;
}

```

## disassembly

```asm
0x18002f830  push    rbx
0x18002f832  sub     rsp, 40h
0x18002f836  mov     r11, rdx
0x18002f839  mov     rdx, [rcx]
0x18002f83c  mov     r10, [rdx+8]
0x18002f840  test    r10, r10
0x18002f843  jnz     short loc_18002F8A0
0x18002f845  lea     ebx, [r10+57h]
0x18002f849  lea     edx, [rbx-55h]
0x18002f84c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002f851  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f858  lea     rax, WPP_GLOBAL_Control
0x18002f85f  cmp     rcx, rax
0x18002f862  jz      loc_18002F956
0x18002f868  test    byte ptr [rcx+1Ch], 1
0x18002f86c  jz      loc_18002F956
0x18002f872  cmp     byte ptr [rcx+19h], 2
0x18002f876  jb      loc_18002F956
0x18002f87c  mov     rcx, [rcx+10h]
0x18002f880  lea     rax, aPinfoPcardstat; "pInfo->pCardState->pCardData"
0x18002f887  lea     edx, [rbx-4Dh]
0x18002f88a  mov     [rsp+48h+Data], rax
0x18002f88f  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x18002f896  call    WPP_SF_ss
0x18002f89b  jmp     loc_18002F956
0x18002f8a0  xor     r8d, r8d
0x18002f8a3  test    byte ptr [rcx+8], 2
0x18002f8a7  jz      short loc_18002F8B1
0x18002f8a9  movzx   r8d, word ptr [rcx+21Eh]
0x18002f8b1  test    byte ptr [rcx+8], 4
0x18002f8b5  jz      short loc_18002F8C1
0x18002f8b7  movzx   eax, word ptr [rcx+220h]
0x18002f8be  add     r8d, eax; FreshnessCounter
0x18002f8c1  mov     eax, [rcx+10h]
0x18002f8c4  test    eax, eax
0x18002f8c6  jnz     short loc_18002F904
0x18002f8c8  cmp     dword ptr [rcx+8], 1
0x18002f8cc  jz      short loc_18002F919
0x18002f8ce  cmp     dword ptr [r10], 6
0x18002f8d2  jb      short loc_18002F8DD
0x18002f8d4  cmp     dword ptr [rdx+2B8h], 2
0x18002f8db  jz      short loc_18002F919
0x18002f8dd  mov     eax, [r11]
0x18002f8e0  lea     r9, [rcx+14h]; LookupName
0x18002f8e4  mov     rdx, [rdx+228h]; CardIdentifier
0x18002f8eb  mov     rcx, [r10+60h]; hContext
0x18002f8ef  mov     [rsp+48h+DataLen], eax; DataLen
0x18002f8f3  mov     rax, [r11+8]
0x18002f8f7  mov     [rsp+48h+Data], rax; Data
0x18002f8fc  call    cs:__imp_SCardWriteCacheW
0x18002f902  jmp     short loc_18002F954
0x18002f904  cmp     eax, 1
0x18002f907  jz      short loc_18002F910
0x18002f909  mov     ebx, 54Fh
0x18002f90e  jmp     short loc_18002F956
0x18002f910  mov     r10, [rdx+2A8h]
0x18002f917  jmp     short loc_18002F920
0x18002f919  mov     r10, [rdx+2A0h]
0x18002f920  mov     eax, [r11]
0x18002f923  lea     r9, [rcx+14h]
0x18002f927  mov     rdx, [rdx+228h]
0x18002f92e  mov     rcx, r10; lpCriticalSection
0x18002f931  mov     [rsp+48h+var_10], eax; int
0x18002f935  mov     rax, [r11+8]
0x18002f939  mov     [rsp+48h+Src], rax; Src
0x18002f93e  mov     qword ptr [rsp+48h+DataLen], 0; int
0x18002f947  mov     dword ptr [rsp+48h+Data], 0; int
0x18002f94f  call    ScCacheWrite
0x18002f954  mov     ebx, eax
0x18002f956  mov     eax, ebx
0x18002f958  add     rsp, 40h
0x18002f95c  pop     rbx
0x18002f95d  retn
```
