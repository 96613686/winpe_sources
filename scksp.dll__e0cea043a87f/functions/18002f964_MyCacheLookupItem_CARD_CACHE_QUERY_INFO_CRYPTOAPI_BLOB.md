# MyCacheLookupItem(_CARD_CACHE_QUERY_INFO *,_CRYPTOAPI_BLOB *)

- ea: `0x18002f964`
- end: `0x18002fb5f`
- name: `?MyCacheLookupItem@@YAKPEAU_CARD_CACHE_QUERY_INFO@@PEAU_CRYPTOAPI_BLOB@@@Z`
- size: `507`
- prototype: `unsigned int __fastcall(struct _CARD_CACHE_QUERY_INFO *, struct _CRYPTOAPI_BLOB *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002fe08`

## callees

- `0x180009e76`
- `0x18000d9d0`
- `0x180011fd8`
- `0x180013734`
- `0x18002b140`
- `0x18002eb6c`
- `0x18002f964`
- `0x180037730`

## import_xrefs

- `WinSCard!SCardReadCacheW` at `0x18002fa51`
- `WinSCard!SCardReadCacheW` at `0x18002fa51`
- `WinSCard!SCardFreeMemory` at `0x18002fb42`
- `WinSCard!SCardFreeMemory` at `0x18002fb42`

## pseudocode

```c
__int64 __fastcall MyCacheLookupItem(struct _CARD_CACHE_QUERY_INFO *a1, struct _CRYPTOAPI_BLOB *a2)
{
  __int64 v3; // rdx
  _DWORD *v5; // rcx
  unsigned int v6; // ebx
  int v7; // r9d
  DWORD v8; // r8d
  int v9; // eax
  int v10; // ebp
  LONG CacheW; // eax
  struct _RTL_CRITICAL_SECTION *v12; // rcx
  size_t v13; // rcx
  BYTE *v14; // rax
  __int64 v15; // rcx
  int Data; // [rsp+20h] [rbp-58h]
  int DataLen; // [rsp+28h] [rbp-50h]
  BYTE v19[16]; // [rsp+40h] [rbp-38h] BYREF

  v3 = *(_QWORD *)a1;
  *(_OWORD *)v19 = 0;
  v5 = *(_DWORD **)(v3 + 8);
  if ( !v5 )
  {
    v6 = 87;
    WppTraceIndent(0, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
        v7,
        (__int64)"pInfo->pCardState->pCardData");
    }
    return v6;
  }
  v8 = 0;
  if ( (*((_BYTE *)a1 + 8) & 2) != 0 )
    v8 = *((unsigned __int16 *)a1 + 271);
  if ( (*((_BYTE *)a1 + 8) & 4) != 0 )
    v8 += *((unsigned __int16 *)a1 + 272);
  v9 = *((_DWORD *)a1 + 4);
  if ( v9 )
  {
    if ( v9 != 1 )
      return 1359;
    v12 = *(struct _RTL_CRITICAL_SECTION **)(v3 + 680);
  }
  else
  {
    if ( *((_DWORD *)a1 + 2) != 1 && (*v5 < 6u || *(_DWORD *)(v3 + 696) != 2) )
    {
      *(_DWORD *)v19 = -1;
      v10 = 1;
      CacheW = SCardReadCacheW(
                 *(_QWORD *)(*(_QWORD *)(v3 + 8) + 96LL),
                 *(UUID **)(v3 + 552),
                 v8,
                 (LPWSTR)a1 + 10,
                 &v19[8],
                 (DWORD *)v19);
      goto LABEL_20;
    }
    v12 = *(struct _RTL_CRITICAL_SECTION **)(v3 + 672);
  }
  v10 = 0;
  CacheW = ScCacheRead(v12, Data, DataLen, (__int64)&v19[8], (__int64)v19);
LABEL_20:
  v6 = CacheW;
  if ( CacheW )
  {
    if ( CacheW == -2146434960 || CacheW == -2146434959 )
      return 1168;
  }
  else
  {
    v13 = *(unsigned int *)v19;
    a2->cbData = *(_DWORD *)v19;
    v14 = (BYTE *)MIDL_user_allocate(v13);
    a2->pbData = v14;
    if ( v14 )
    {
      memcpy_0(v14, *(const void **)&v19[8], a2->cbData);
    }
    else
    {
      WppTraceIndent(v15, 2);
      v6 = 8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
          WPP_pszIndent);
      }
    }
    if ( v10 )
      SCardFreeMemory(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 8LL) + 96LL), *(LPCVOID *)&v19[8]);
    else
      CspFreeH(*(_QWORD *)&v19[8]);
  }
  return v6;
}

```

## disassembly

```asm
0x18002f964  push    rbx
0x18002f966  push    rbp
0x18002f967  push    rsi
0x18002f968  push    rdi
0x18002f969  sub     rsp, 58h
0x18002f96d  mov     rsi, rdx
0x18002f970  xorps   xmm0, xmm0
0x18002f973  mov     rdx, [rcx]
0x18002f976  mov     rdi, rcx
0x18002f979  movups  xmmword ptr [rsp+78h+var_38], xmm0
0x18002f97e  mov     rcx, [rdx+8]
0x18002f982  test    rcx, rcx
0x18002f985  jnz     short loc_18002F9E1
0x18002f987  lea     edx, [rcx+2]
0x18002f98a  lea     ebx, [rcx+57h]
0x18002f98d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002f992  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f999  lea     rax, WPP_GLOBAL_Control
0x18002f9a0  cmp     rcx, rax
0x18002f9a3  jz      loc_18002FB54
0x18002f9a9  test    byte ptr [rcx+1Ch], 1
0x18002f9ad  jz      loc_18002FB54
0x18002f9b3  cmp     byte ptr [rcx+19h], 2
0x18002f9b7  jb      loc_18002FB54
0x18002f9bd  mov     rcx, [rcx+10h]
0x18002f9c1  lea     rax, aPinfoPcardstat; "pInfo->pCardState->pCardData"
0x18002f9c8  lea     edx, [rbx-4Ch]
0x18002f9cb  mov     [rsp+78h+Data], rax
0x18002f9d0  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x18002f9d7  call    WPP_SF_ss
0x18002f9dc  jmp     loc_18002FB54
0x18002f9e1  xor     r8d, r8d
0x18002f9e4  test    byte ptr [rdi+8], 2
0x18002f9e8  jz      short loc_18002F9F2
0x18002f9ea  movzx   r8d, word ptr [rdi+21Eh]
0x18002f9f2  test    byte ptr [rdi+8], 4
0x18002f9f6  jz      short loc_18002FA02
0x18002f9f8  movzx   eax, word ptr [rdi+220h]
0x18002f9ff  add     r8d, eax; FreshnessCounter
0x18002fa02  mov     eax, [rdi+10h]
0x18002fa05  test    eax, eax
0x18002fa07  jnz     short loc_18002FA59
0x18002fa09  cmp     dword ptr [rdi+8], 1
0x18002fa0d  jz      short loc_18002FA71
0x18002fa0f  cmp     dword ptr [rcx], 6
0x18002fa12  jb      short loc_18002FA1D
0x18002fa14  cmp     dword ptr [rdx+2B8h], 2
0x18002fa1b  jz      short loc_18002FA71
0x18002fa1d  mov     dword ptr [rsp+78h+var_38], 0FFFFFFFFh
0x18002fa25  lea     rax, [rsp+78h+var_38]
0x18002fa2a  mov     rcx, [rdx+8]
0x18002fa2e  lea     r9, [rdi+14h]; LookupName
0x18002fa32  mov     rdx, [rdx+228h]; CardIdentifier
0x18002fa39  mov     ebp, 1
0x18002fa3e  mov     [rsp+78h+DataLen], rax; DataLen
0x18002fa43  lea     rax, [rsp+78h+var_38+8]
0x18002fa48  mov     [rsp+78h+Data], rax; Data
0x18002fa4d  mov     rcx, [rcx+60h]; hContext
0x18002fa51  call    cs:__imp_SCardReadCacheW
0x18002fa57  jmp     short loc_18002FA9E
0x18002fa59  cmp     eax, 1
0x18002fa5c  jz      short loc_18002FA68
0x18002fa5e  mov     ebx, 54Fh
0x18002fa63  jmp     loc_18002FB54
0x18002fa68  mov     rcx, [rdx+2A8h]
0x18002fa6f  jmp     short loc_18002FA78
0x18002fa71  mov     rcx, [rdx+2A0h]; lpCriticalSection
0x18002fa78  mov     rdx, [rdx+228h]
0x18002fa7f  lea     rax, [rsp+78h+var_38]
0x18002fa84  mov     [rsp+78h+var_40], rax; __int64
0x18002fa89  lea     r9, [rdi+14h]
0x18002fa8d  lea     rax, [rsp+78h+var_38+8]
0x18002fa92  xor     ebp, ebp
0x18002fa94  mov     [rsp+78h+var_48], rax; __int64
0x18002fa99  call    ScCacheRead
0x18002fa9e  mov     ebx, eax
0x18002faa0  test    eax, eax
0x18002faa2  jz      short loc_18002FAC0
0x18002faa4  cmp     eax, 80100070h
0x18002faa9  jz      short loc_18002FAB6
0x18002faab  cmp     eax, 80100071h
0x18002fab0  jnz     loc_18002FB54
0x18002fab6  mov     ebx, 490h
0x18002fabb  jmp     loc_18002FB54
0x18002fac0  mov     eax, dword ptr [rsp+78h+var_38]
0x18002fac4  mov     ecx, eax; size
0x18002fac6  mov     [rsi], eax
0x18002fac8  call    MIDL_user_allocate
0x18002facd  mov     [rsi+8], rax
0x18002fad1  test    rax, rax
0x18002fad4  jnz     short loc_18002FB1E
0x18002fad6  lea     edx, [rax+2]
0x18002fad9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002fade  mov     ebx, 8
0x18002fae3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002faea  lea     rax, WPP_GLOBAL_Control
0x18002faf1  cmp     rcx, rax
0x18002faf4  jz      short loc_18002FB2E
0x18002faf6  test    byte ptr [rcx+1Ch], 1
0x18002fafa  jz      short loc_18002FB2E
0x18002fafc  cmp     byte ptr [rcx+19h], 2
0x18002fb00  jb      short loc_18002FB2E
0x18002fb02  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002fb09  lea     edx, [rbx+4]
0x18002fb0c  mov     rcx, [rcx+10h]
0x18002fb10  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x18002fb17  call    WPP_SF_s
0x18002fb1c  jmp     short loc_18002FB2E
0x18002fb1e  mov     r8d, [rsi]; Size
0x18002fb21  mov     rcx, rax; void *
0x18002fb24  mov     rdx, qword ptr [rsp+78h+var_38+8]; Src
0x18002fb29  call    memcpy_0
0x18002fb2e  test    ebp, ebp
0x18002fb30  jz      short loc_18002FB4A
0x18002fb32  mov     rax, [rdi]
0x18002fb35  mov     rdx, qword ptr [rsp+78h+var_38+8]; pvMem
0x18002fb3a  mov     rcx, [rax+8]
0x18002fb3e  mov     rcx, [rcx+60h]; hContext
0x18002fb42  call    cs:__imp_SCardFreeMemory
0x18002fb48  jmp     short loc_18002FB54
0x18002fb4a  mov     rcx, qword ptr [rsp+78h+var_38+8]
0x18002fb4f  call    CspFreeH
0x18002fb54  mov     eax, ebx
0x18002fb56  add     rsp, 58h
0x18002fb5a  pop     rdi
0x18002fb5b  pop     rsi
0x18002fb5c  pop     rbp
0x18002fb5d  pop     rbx
0x18002fb5e  retn
```
