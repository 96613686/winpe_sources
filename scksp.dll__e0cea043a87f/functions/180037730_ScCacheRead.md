# ScCacheRead

- ea: `0x180037730`
- end: `0x180037a43`
- name: `ScCacheRead`
- size: `787`
- prototype: `__int64 __usercall@<rax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, int, int, __int64, __int64)`
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18002f964`
- `0x180030950`
- `0x180030c84`
- `0x180032318`

## callees

- `0x180009e76`
- `0x18000a408`
- `0x18000a590`
- `0x180013734`
- `0x180036f7c`
- `0x180037008`
- `0x180037730`
- `0x180038094`
- `0x180038484`
- `0x18003d010`

## import_xrefs

- `msvcrt!time` at `0x180037915`
- `msvcrt!time` at `0x180037915`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800379de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800379de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800378db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800378db`

## string_xrefs

- `0x180037894`: `ScCacheRead`

## pseudocode

```c
__int64 __fastcall ScCacheRead(
        LPCRITICAL_SECTION lpCriticalSection,
        __int64 a2,
        int a3,
        __int64 a4,
        int a5,
        int a6,
        _QWORD *a7,
        _DWORD *a8)
{
  __int64 v9; // rbx
  int v10; // esi
  PVOID v12; // rcx
  unsigned int v13; // ebx
  __int64 v14; // rax
  __int64 v15; // r8
  unsigned int Item; // eax
  __int64 v17; // rdi
  __int64 v18; // rdx
  LPCRITICAL_SECTION v19; // rcx
  void *v20; // rax
  __int64 v21; // rcx
  __int128 v23; // [rsp+A8h] [rbp-29h] BYREF
  int v24; // [rsp+B8h] [rbp-19h] BYREF
  __int64 v25; // [rsp+C0h] [rbp-11h]
  int v26; // [rsp+C8h] [rbp-9h]
  __int64 v27; // [rsp+D0h] [rbp-1h]
  time_t Time; // [rsp+118h] [rbp+47h] BYREF
  int v29; // [rsp+128h] [rbp+57h]
  __int64 v30; // [rsp+130h] [rbp+5Fh]

  v30 = a4;
  v29 = a3;
  Time = 0;
  v9 = a4;
  v10 = a3;
  WppTraceIndent((__int64)lpCriticalSection, 0);
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
  }
  v23 = 0;
  if ( v9 )
  {
    if ( !a2 )
    {
      v13 = -2146434960;
      goto LABEL_31;
    }
    WppTraceIndent((__int64)v12, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_ssDDDDDDDDDDDSDS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        *(unsigned __int8 *)(a2 + 14),
        *(unsigned __int8 *)(a2 + 13),
        (__int64)"ScCacheRead",
        *(_DWORD *)a2,
        *(_WORD *)(a2 + 4),
        *(_WORD *)(a2 + 6),
        *(_BYTE *)(a2 + 8),
        *(_BYTE *)(a2 + 9),
        *(_BYTE *)(a2 + 10),
        *(_BYTE *)(a2 + 11),
        *(_BYTE *)(a2 + 12),
        *(_BYTE *)(a2 + 13),
        *(_BYTE *)(a2 + 14),
        *(_BYTE *)(a2 + 15),
        v30,
        v29);
      v9 = v30;
      v10 = v29;
    }
    v24 = 16;
    v14 = -1;
    v25 = a2;
    do
      ++v14;
    while ( *(_WORD *)(v9 + 2 * v14) );
    v27 = v9;
    v26 = 2 * v14;
    EnterCriticalSection(lpCriticalSection);
    Item = CacheGetItem(lpCriticalSection[1].DebugInfo, &v24, v15, &v23);
    v13 = Item;
    if ( Item )
    {
      if ( Item == 1168 )
        v13 = -2146434960;
    }
    else
    {
      v17 = *((_QWORD *)&v23 + 1);
      time(&Time);
      if ( Time - *(_QWORD *)(v17 + 16) < 0
        || *(__int64 *)(v17 + 16) < 0
        || Time - *(_QWORD *)(v17 + 16) > (unsigned int)(86400 * LODWORD(lpCriticalSection[2].OwningThread)) )
      {
        v18 = v17;
        v19 = lpCriticalSection;
      }
      else
      {
        v18 = v17;
        v19 = lpCriticalSection;
        if ( v10 == *(_DWORD *)(v17 + 12) )
        {
          I_ServerCacheSetMRU(lpCriticalSection, v17);
          v20 = (void *)(*(__int64 (__fastcall **)(_QWORD))&lpCriticalSection[1].LockCount)(*(unsigned int *)(v17 + 8));
          v21 = (__int64)a7;
          *a7 = v20;
          if ( v20 )
          {
            memcpy_0(v20, *(const void **)v17, *(unsigned int *)(v17 + 8));
            *a8 = *(_DWORD *)(v17 + 8);
          }
          else
          {
            WppTraceIndent(v21, 2u);
            v13 = 8;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                25,
                WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
                WPP_pszIndent);
            }
          }
          goto LABEL_30;
        }
      }
      I_ServerCacheRemoveItem(v19, v18, &v24);
      v13 = -2146434959;
    }
LABEL_30:
    LeaveCriticalSection(lpCriticalSection);
    goto LABEL_31;
  }
  v13 = -2146435068;
LABEL_31:
  WppTraceIndent((__int64)v12, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      (unsigned int)WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
      WPP_pszIndent,
      v13);
  }
  return v13;
}

```

## disassembly

```asm
0x180037730  mov     rax, rsp
0x180037733  mov     [rax+10h], rbx
0x180037737  mov     [rax+20h], r9
0x18003773b  mov     [rax+18h], r8d
0x18003773f  push    rbp
0x180037740  push    rsi
0x180037741  push    rdi
0x180037742  push    r12
0x180037744  push    r13
0x180037746  push    r14
0x180037748  push    r15
0x18003774a  lea     rbp, [rax-3Fh]
0x18003774e  sub     rsp, 0D0h
0x180037755  mov     r12, rdx
0x180037758  xor     r14d, r14d
0x18003775b  xor     edx, edx
0x18003775d  mov     [rbp+37h+Time], r14
0x180037761  mov     rbx, r9
0x180037764  mov     esi, r8d
0x180037767  mov     r13, rcx
0x18003776a  call    WppTraceIndent
0x18003776f  mov     rcx, cs:WPP_GLOBAL_Control
0x180037776  lea     r15, WPP_GLOBAL_Control
0x18003777d  cmp     rcx, r15
0x180037780  jz      short loc_1800377A9
0x180037782  test    byte ptr [rcx+1Ch], 2
0x180037786  jz      short loc_1800377A9
0x180037788  cmp     byte ptr [rcx+19h], 5
0x18003778c  jb      short loc_1800377A9
0x18003778e  mov     r9, cs:WPP_pszIndent
0x180037795  lea     edx, [r14+17h]
0x180037799  mov     rcx, [rcx+10h]
0x18003779d  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x1800377a4  call    WPP_SF_s
0x1800377a9  xorps   xmm0, xmm0
0x1800377ac  movups  [rbp+37h+var_60], xmm0
0x1800377b0  test    rbx, rbx
0x1800377b3  jnz     short loc_1800377BF
0x1800377b5  mov     ebx, 80100004h
0x1800377ba  jmp     loc_1800379E4
0x1800377bf  test    r12, r12
0x1800377c2  jnz     short loc_1800377CE
0x1800377c4  mov     ebx, 80100070h
0x1800377c9  jmp     loc_1800379E4
0x1800377ce  mov     edx, 2
0x1800377d3  call    WppTraceIndent
0x1800377d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800377df  cmp     rcx, r15
0x1800377e2  jz      loc_1800378B6
0x1800377e8  test    byte ptr [rcx+1Ch], 4
0x1800377ec  jz      loc_1800378B6
0x1800377f2  cmp     byte ptr [rcx+19h], 4
0x1800377f6  jb      loc_1800378B6
0x1800377fc  movzx   eax, byte ptr [r12+0Fh]
0x180037802  mov     edx, 18h
0x180037807  mov     ecx, [rbp+37h+arg_10]
0x18003780a  movzx   r8d, byte ptr [r12+0Eh]
0x180037810  movzx   r9d, byte ptr [r12+0Dh]
0x180037816  movzx   r10d, byte ptr [r12+0Ch]
0x18003781c  movzx   r11d, byte ptr [r12+0Bh]
0x180037822  movzx   ebx, byte ptr [r12+0Ah]
0x180037828  movzx   edi, byte ptr [r12+9]
0x18003782e  movzx   esi, byte ptr [r12+8]
0x180037834  movzx   r14d, word ptr [r12+6]
0x18003783a  movzx   r15d, word ptr [r12+4]
0x180037840  mov     [rsp+88h], ecx
0x180037847  mov     rcx, [rbp+37h+arg_18]
0x18003784b  mov     qword ptr [rsp+100h+var_80], rcx
0x180037853  mov     rcx, cs:WPP_GLOBAL_Control
0x18003785a  mov     dword ptr [rsp+100h+var_88], eax
0x18003785e  mov     eax, [r12]
0x180037862  mov     [rsp+100h+var_90], r8d
0x180037867  mov     rcx, [rcx+10h]
0x18003786b  mov     [rsp+100h+var_98], r9d
0x180037870  mov     [rsp+100h+var_A0], r10d
0x180037875  mov     [rsp+100h+var_A8], r11d
0x18003787a  mov     [rsp+100h+var_B0], ebx
0x18003787e  mov     [rsp+100h+var_B8], edi
0x180037882  mov     [rsp+100h+var_C0], esi
0x180037886  mov     [rsp+100h+var_C8], r14d
0x18003788b  mov     [rsp+100h+var_D0], r15d
0x180037890  mov     [rsp+100h+var_D8], eax
0x180037894  lea     rax, aSccacheread; "ScCacheRead"
0x18003789b  mov     qword ptr [rsp+100h+var_E0], rax
0x1800378a0  call    WPP_SF_ssDDDDDDDDDDDSDS
0x1800378a5  mov     rbx, [rbp+37h+arg_18]
0x1800378a9  lea     r15, WPP_GLOBAL_Control
0x1800378b0  mov     esi, [rbp+37h+arg_10]
0x1800378b3  xor     r14d, r14d
0x1800378b6  mov     [rbp+37h+var_50], 10h
0x1800378bd  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800378c1  mov     [rbp+37h+var_48], r12
0x1800378c5  inc     rax
0x1800378c8  cmp     [rbx+rax*2], r14w
0x1800378cd  jnz     short loc_1800378C5
0x1800378cf  add     eax, eax
0x1800378d1  mov     [rbp+37h+var_38], rbx
0x1800378d5  mov     rcx, r13; lpCriticalSection
0x1800378d8  mov     [rbp+37h+var_40], eax
0x1800378db  call    cs:__imp_EnterCriticalSection
0x1800378e1  mov     rcx, [r13+28h]
0x1800378e5  lea     r9, [rbp+37h+var_60]
0x1800378e9  lea     rdx, [rbp+37h+var_50]
0x1800378ed  call    CacheGetItem
0x1800378f2  mov     ebx, eax
0x1800378f4  test    eax, eax
0x1800378f6  jz      short loc_18003790D
0x1800378f8  cmp     eax, 490h
0x1800378fd  jnz     loc_1800379DB
0x180037903  mov     ebx, 80100070h
0x180037908  jmp     loc_1800379DB
0x18003790d  mov     rdi, qword ptr [rbp+37h+var_60+8]
0x180037911  lea     rcx, [rbp+37h+Time]; Time
0x180037915  call    cs:__imp_time
0x18003791b  mov     rdx, [rbp+37h+Time]
0x18003791f  sub     rdx, [rdi+10h]
0x180037923  js      loc_1800379C7
0x180037929  cmp     [rdi+10h], r14
0x18003792d  jl      loc_1800379C7
0x180037933  imul    ecx, [r13+60h], 15180h
0x18003793b  cmp     rdx, rcx
0x18003793e  jg      loc_1800379C7
0x180037944  mov     rdx, rdi
0x180037947  mov     rcx, r13
0x18003794a  cmp     esi, [rdi+0Ch]
0x18003794d  jnz     short loc_1800379CD
0x18003794f  call    I_ServerCacheSetMRU
0x180037954  mov     rax, [r13+30h]
0x180037958  mov     ecx, [rdi+8]
0x18003795b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037960  mov     rcx, [rbp+37h+arg_30]
0x180037964  mov     [rcx], rax
0x180037967  test    rax, rax
0x18003796a  jnz     short loc_1800379AD
0x18003796c  lea     edx, [rax+2]
0x18003796f  call    WppTraceIndent
0x180037974  mov     ebx, 8
0x180037979  mov     rcx, cs:WPP_GLOBAL_Control
0x180037980  cmp     rcx, r15
0x180037983  jz      short loc_1800379DB
0x180037985  test    byte ptr [rcx+1Ch], 1
0x180037989  jz      short loc_1800379DB
0x18003798b  cmp     byte ptr [rcx+19h], 2
0x18003798f  jb      short loc_1800379DB
0x180037991  mov     r9, cs:WPP_pszIndent
0x180037998  lea     edx, [rbx+11h]
0x18003799b  mov     rcx, [rcx+10h]
0x18003799f  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x1800379a6  call    WPP_SF_s
0x1800379ab  jmp     short loc_1800379DB
0x1800379ad  mov     r8d, [rdi+8]; Size
0x1800379b1  mov     rcx, rax; void *
0x1800379b4  mov     rdx, [rdi]; Src
0x1800379b7  call    memcpy_0
0x1800379bc  mov     rax, [rbp+37h+arg_38]
0x1800379c0  mov     ecx, [rdi+8]
0x1800379c3  mov     [rax], ecx
0x1800379c5  jmp     short loc_1800379DB
0x1800379c7  mov     rdx, rdi
0x1800379ca  mov     rcx, r13
0x1800379cd  lea     r8, [rbp+37h+var_50]
0x1800379d1  call    I_ServerCacheRemoveItem
0x1800379d6  mov     ebx, 80100071h
0x1800379db  mov     rcx, r13; lpCriticalSection
0x1800379de  call    cs:__imp_LeaveCriticalSection
0x1800379e4  mov     edx, 1
0x1800379e9  call    WppTraceIndent
0x1800379ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800379f5  cmp     rcx, r15
0x1800379f8  jz      short loc_180037A26
0x1800379fa  test    byte ptr [rcx+1Ch], 2
0x1800379fe  jz      short loc_180037A26
0x180037a00  cmp     byte ptr [rcx+19h], 5
0x180037a04  jb      short loc_180037A26
0x180037a06  mov     r9, cs:WPP_pszIndent
0x180037a0d  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180037a14  mov     rcx, [rcx+10h]
0x180037a18  mov     edx, 1Ah
0x180037a1d  mov     [rsp+100h+var_E0], ebx
0x180037a21  call    WPP_SF_sd
0x180037a26  mov     eax, ebx
0x180037a28  mov     rbx, [rsp+100h+arg_8]
0x180037a30  add     rsp, 0D0h
0x180037a37  pop     r15
0x180037a39  pop     r14
0x180037a3b  pop     r13
0x180037a3d  pop     r12
0x180037a3f  pop     rdi
0x180037a40  pop     rsi
0x180037a41  pop     rbp
0x180037a42  retn
```
