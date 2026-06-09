# ScCacheWrite

- ea: `0x180037a4c`
- end: `0x18003808e`
- name: `ScCacheWrite`
- size: `1602`
- prototype: `__int64 __usercall@<rax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, int, int, void *Src, int)`
- caller_count: `3`
- callee_count: `13`
- tags: ``

## callers

- `0x18002f830`
- `0x180030c84`
- `0x180032318`

## callees

- `0x180009e76`
- `0x18000a408`
- `0x18000a590`
- `0x180013734`
- `0x180036ef4`
- `0x180036f7c`
- `0x180037008`
- `0x180037a4c`
- `0x180038094`
- `0x180038284`
- `0x180038484`
- `0x18003c1f6`
- `0x18003d010`

## import_xrefs

- `msvcrt!time` at `0x180037ddb`
- `msvcrt!time` at `0x180037ddb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003801b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003801b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037bee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037bee`

## string_xrefs

- `0x180037b9b`: `ScCacheWrite`

## pseudocode

```c
__int64 __fastcall ScCacheWrite(
        LPCRITICAL_SECTION lpCriticalSection,
        char *a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        int a6,
        void *Src,
        unsigned int a8)
{
  _WORD *v9; // r14
  PVOID v11; // rcx
  unsigned int v12; // ebx
  __int64 v13; // rsi
  __int64 v14; // rax
  __int64 v15; // r8
  unsigned int Item; // eax
  _QWORD *LockSemaphore; // rdx
  _WORD *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  _DWORD *v21; // rdi
  __int64 v22; // rcx
  void *v23; // rax
  __int64 v24; // rcx
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // r8
  void *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // r8
  __int128 v31; // xmm0
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  ULONG_PTR SpinCount; // rax
  bool v34; // zf
  __int64 v35; // rdi
  _QWORD *v36; // rdx
  _WORD *v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rcx
  _WORD *v41; // rcx
  unsigned int i; // esi
  __int128 v44; // [rsp+A8h] [rbp-29h] BYREF
  int v45; // [rsp+B8h] [rbp-19h] BYREF
  char *v46; // [rsp+C0h] [rbp-11h]
  int v47; // [rsp+C8h] [rbp-9h]
  _WORD *v48; // [rsp+D0h] [rbp-1h]

  v9 = (_WORD *)a4;
  WppTraceIndent((__int64)lpCriticalSection, 0);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
  }
  v44 = 0;
  if ( !v9 || !a2 )
  {
    v12 = -2146435068;
    goto LABEL_73;
  }
  WppTraceIndent((__int64)v11, 2u);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_ssDDDDDDDDDDDSDS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      (unsigned __int8)a2[14],
      (unsigned __int8)a2[13],
      (__int64)"ScCacheWrite",
      *(_DWORD *)a2,
      *((_WORD *)a2 + 2),
      *((_WORD *)a2 + 3),
      a2[8],
      a2[9],
      a2[10],
      a2[11],
      a2[12],
      a2[13],
      a2[14],
      a2[15],
      a4,
      a3);
    v9 = (_WORD *)a4;
  }
  if ( lpCriticalSection[2].RecursionCount >= a8 )
  {
    v13 = -1;
    v45 = 16;
    v14 = -1;
    v46 = a2;
    do
      ++v14;
    while ( v9[v14] );
    v48 = v9;
    v47 = 2 * v14;
    EnterCriticalSection(lpCriticalSection);
    Item = CacheGetItem(lpCriticalSection[1].DebugInfo, &v45, v15, &v44);
    v12 = Item;
    if ( Item )
    {
      if ( Item == 1168 )
      {
        while ( lpCriticalSection[2].LockCount < a8 + LODWORD(lpCriticalSection[2].DebugInfo) )
        {
          LockSemaphore = lpCriticalSection[1].LockSemaphore;
          v45 = 16;
          v18 = (_WORD *)LockSemaphore[5];
          v46 = (char *)(LockSemaphore + 3);
          v19 = -1;
          do
            ++v19;
          while ( v18[v19] );
          v48 = v18;
          v47 = 2 * v19;
          I_ServerCacheRemoveItem(lpCriticalSection, LockSemaphore, &v45);
        }
        v21 = (_DWORD *)(*(__int64 (__fastcall **)(__int64))&lpCriticalSection[1].LockCount)(80);
        if ( !v21 )
        {
          WppTraceIndent(v20, 2u);
          v12 = 8;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              29,
              WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
              WPP_pszIndent);
          }
          goto LABEL_71;
        }
        v22 = -1;
        do
          ++v22;
        while ( v9[v22] );
        v23 = (void *)(*(__int64 (__fastcall **)(__int64))&lpCriticalSection[1].LockCount)(2 * v22 + 2);
        *((_QWORD *)v21 + 5) = v23;
        if ( v23 )
        {
          v27 = -1;
          do
            ++v27;
          while ( v9[v27] );
          memcpy_0(v23, v9, 2 * v27 + 2);
          v21[2] = a8;
          v28 = (void *)(*(__int64 (__fastcall **)(_QWORD))&lpCriticalSection[1].LockCount)(a8);
          *(_QWORD *)v21 = v28;
          if ( v28 )
          {
            memcpy_0(v28, Src, (unsigned int)v21[2]);
            v21[3] = a3;
            time((time_t *const)v21 + 2);
            v31 = *(_OWORD *)a2;
            *((_QWORD *)&v44 + 1) = v21;
            LODWORD(v44) = 80;
            *(_OWORD *)(v21 + 6) = v31;
            v45 = 16;
            v46 = a2;
            do
              ++v13;
            while ( v9[v13] );
            DebugInfo = lpCriticalSection[1].DebugInfo;
            v47 = 2 * v13;
            v48 = v9;
            v12 = CacheAddItem(DebugInfo, &v45, v30, &v44);
            if ( !v12 )
            {
              SpinCount = lpCriticalSection[1].SpinCount;
              *((_QWORD *)v21 + 6) = SpinCount;
              if ( SpinCount )
                *(_QWORD *)(SpinCount + 56) = v21;
              v34 = lpCriticalSection[1].LockSemaphore == 0;
              lpCriticalSection[1].SpinCount = (ULONG_PTR)v21;
              if ( v34 )
                lpCriticalSection[1].LockSemaphore = v21;
              LODWORD(lpCriticalSection[2].DebugInfo) += v21[2];
              ++HIDWORD(lpCriticalSection[2].DebugInfo);
              goto LABEL_71;
            }
            goto LABEL_50;
          }
          WppTraceIndent(v29, 2u);
          v12 = 8;
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
LABEL_50:
            I_ServerCacheFreeItem(lpCriticalSection);
            goto LABEL_71;
          }
          v26 = 31;
        }
        else
        {
          WppTraceIndent(v24, 2u);
          v12 = 8;
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_50;
          }
          v26 = 30;
        }
        WPP_SF_s(v25[2], v26, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
        goto LABEL_50;
      }
    }
    else
    {
      v35 = *((_QWORD *)&v44 + 1);
      if ( *(_QWORD *)(*((_QWORD *)&v44 + 1) + 8LL) != __PAIR64__(a3, a8)
        || memcmp_0(**((const void ***)&v44 + 1), Src, *(unsigned int *)(*((_QWORD *)&v44 + 1) + 8LL)) )
      {
        *(_DWORD *)(v35 + 12) = a3;
        I_ServerCacheSetMRU(lpCriticalSection, v35);
        while ( lpCriticalSection[2].LockCount < LODWORD(lpCriticalSection[2].DebugInfo) + a8 - *(_DWORD *)(v35 + 8) )
        {
          v36 = lpCriticalSection[1].LockSemaphore;
          v45 = 16;
          v37 = (_WORD *)v36[5];
          v46 = (char *)(v36 + 3);
          v38 = -1;
          do
            ++v38;
          while ( v37[v38] );
          v48 = v37;
          v47 = 2 * v38;
          I_ServerCacheRemoveItem(lpCriticalSection, v36, &v45);
        }
        ((void (__fastcall *)(_QWORD))lpCriticalSection[1].OwningThread)(*(_QWORD *)v35);
        *(_QWORD *)v35 = 0;
        v39 = (*(__int64 (__fastcall **)(_QWORD))&lpCriticalSection[1].LockCount)(a8);
        *(_QWORD *)v35 = v39;
        if ( !v39 )
        {
          WppTraceIndent(v40, 2u);
          v12 = 8;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              36,
              WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
              WPP_pszIndent);
          }
          if ( v35 )
          {
            v41 = *(_WORD **)(v35 + 40);
            v46 = (char *)(v35 + 24);
            v45 = 16;
            do
              ++v13;
            while ( v41[v13] );
            v48 = v41;
            v47 = 2 * v13;
            I_ServerCacheRemoveItem(lpCriticalSection, v35, &v45);
          }
          goto LABEL_71;
        }
        LODWORD(lpCriticalSection[2].DebugInfo) -= *(_DWORD *)(v35 + 8);
        *(_DWORD *)(v35 + 8) = a8;
        LODWORD(lpCriticalSection[2].DebugInfo) += a8;
        memcpy_0(*(void **)v35, Src, *(unsigned int *)(v35 + 8));
        for ( i = 0; i < *(_DWORD *)(v35 + 72); ++i )
          ((void (__fastcall *)(_QWORD))lpCriticalSection[1].OwningThread)(*(_QWORD *)(*(_QWORD *)(v35 + 64) + 8LL * i));
        ((void (__fastcall *)(_QWORD))lpCriticalSection[1].OwningThread)(*(_QWORD *)(v35 + 64));
        *(_QWORD *)(v35 + 64) = 0;
        *(_DWORD *)(v35 + 72) = 0;
      }
      I_ServerCacheSetMRU(lpCriticalSection, v35);
    }
LABEL_71:
    LeaveCriticalSection(lpCriticalSection);
    goto LABEL_73;
  }
  v12 = -2146434958;
LABEL_73:
  WppTraceIndent((__int64)v11, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      (unsigned int)WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
      WPP_pszIndent,
      v12);
  }
  return v12;
}

```

## disassembly

```asm
0x180037a4c  mov     rax, rsp
0x180037a4f  mov     [rax+8], rbx
0x180037a53  mov     [rax+20h], r9
0x180037a57  mov     [rax+18h], r8d
0x180037a5b  push    rbp
0x180037a5c  push    rsi
0x180037a5d  push    rdi
0x180037a5e  push    r12
0x180037a60  push    r13
0x180037a62  push    r14
0x180037a64  push    r15
0x180037a66  lea     rbp, [rax-3Fh]
0x180037a6a  sub     rsp, 0D0h
0x180037a71  mov     r12, rdx
0x180037a74  mov     r14, r9
0x180037a77  xor     edx, edx
0x180037a79  mov     r13, rcx
0x180037a7c  call    WppTraceIndent
0x180037a81  mov     rcx, cs:WPP_GLOBAL_Control
0x180037a88  lea     rbx, WPP_GLOBAL_Control
0x180037a8f  cmp     rcx, rbx
0x180037a92  jz      short loc_180037ABC
0x180037a94  test    byte ptr [rcx+1Ch], 2
0x180037a98  jz      short loc_180037ABC
0x180037a9a  cmp     byte ptr [rcx+19h], 5
0x180037a9e  jb      short loc_180037ABC
0x180037aa0  mov     r9, cs:WPP_pszIndent
0x180037aa7  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180037aae  mov     rcx, [rcx+10h]
0x180037ab2  mov     edx, 1Bh
0x180037ab7  call    WPP_SF_s
0x180037abc  xor     edi, edi
0x180037abe  xorps   xmm0, xmm0
0x180037ac1  movups  [rbp+37h+var_60], xmm0
0x180037ac5  test    r14, r14
0x180037ac8  jz      loc_180038023
0x180037ace  test    r12, r12
0x180037ad1  jz      loc_180038023
0x180037ad7  lea     edx, [rdi+2]
0x180037ada  call    WppTraceIndent
0x180037adf  mov     rcx, cs:WPP_GLOBAL_Control
0x180037ae6  cmp     rcx, rbx
0x180037ae9  jz      loc_180037BB2
0x180037aef  test    byte ptr [rcx+1Ch], 4
0x180037af3  jz      loc_180037BB2
0x180037af9  cmp     byte ptr [rcx+19h], 4
0x180037afd  jb      loc_180037BB2
0x180037b03  movzx   eax, byte ptr [r12+0Fh]
0x180037b09  mov     edx, 1Ch
0x180037b0e  mov     ecx, [rbp+37h+arg_10]
0x180037b11  movzx   r8d, byte ptr [r12+0Eh]
0x180037b17  movzx   r9d, byte ptr [r12+0Dh]
0x180037b1d  movzx   r10d, byte ptr [r12+0Ch]
0x180037b23  movzx   r11d, byte ptr [r12+0Bh]
0x180037b29  movzx   ebx, byte ptr [r12+0Ah]
0x180037b2f  movzx   edi, byte ptr [r12+9]
0x180037b35  movzx   esi, byte ptr [r12+8]
0x180037b3b  movzx   r14d, word ptr [r12+6]
0x180037b41  movzx   r15d, word ptr [r12+4]
0x180037b47  mov     [rsp+88h], ecx
0x180037b4e  mov     rcx, [rbp+37h+arg_18]
0x180037b52  mov     qword ptr [rsp+100h+var_80], rcx
0x180037b5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180037b61  mov     dword ptr [rsp+100h+var_88], eax
0x180037b65  mov     eax, [r12]
0x180037b69  mov     [rsp+100h+var_90], r8d
0x180037b6e  mov     rcx, [rcx+10h]
0x180037b72  mov     [rsp+100h+var_98], r9d
0x180037b77  mov     [rsp+100h+var_A0], r10d
0x180037b7c  mov     [rsp+100h+var_A8], r11d
0x180037b81  mov     [rsp+100h+var_B0], ebx
0x180037b85  mov     [rsp+100h+var_B8], edi
0x180037b89  mov     [rsp+100h+var_C0], esi
0x180037b8d  mov     [rsp+100h+var_C8], r14d
0x180037b92  mov     [rsp+100h+var_D0], r15d
0x180037b97  mov     [rsp+100h+var_D8], eax
0x180037b9b  lea     rax, aSccachewrite; "ScCacheWrite"
0x180037ba2  mov     qword ptr [rsp+100h+var_E0], rax
0x180037ba7  call    WPP_SF_ssDDDDDDDDDDDSDS
0x180037bac  mov     r14, [rbp+37h+arg_18]
0x180037bb0  xor     edi, edi
0x180037bb2  mov     r15d, [rbp+37h+arg_38]
0x180037bb6  cmp     [r13+5Ch], r15d
0x180037bba  jnb     short loc_180037BC6
0x180037bbc  mov     ebx, 80100072h
0x180037bc1  jmp     loc_180038028
0x180037bc6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180037bca  mov     [rbp+37h+var_50], 10h
0x180037bd1  mov     rax, rsi
0x180037bd4  mov     [rbp+37h+var_48], r12
0x180037bd8  inc     rax
0x180037bdb  cmp     [r14+rax*2], di
0x180037be0  jnz     short loc_180037BD8
0x180037be2  add     eax, eax
0x180037be4  mov     [rbp+37h+var_38], r14
0x180037be8  mov     rcx, r13; lpCriticalSection
0x180037beb  mov     [rbp+37h+var_40], eax
0x180037bee  call    cs:__imp_EnterCriticalSection
0x180037bf4  mov     rcx, [r13+28h]
0x180037bf8  lea     r9, [rbp+37h+var_60]
0x180037bfc  lea     rdx, [rbp+37h+var_50]
0x180037c00  call    CacheGetItem
0x180037c05  mov     ebx, eax
0x180037c07  test    eax, eax
0x180037c09  jz      loc_180037E73
0x180037c0f  cmp     eax, 490h
0x180037c14  jnz     loc_180038011
0x180037c1a  jmp     short loc_180037C54
0x180037c1c  mov     rdx, [r13+40h]
0x180037c20  mov     [rbp+37h+var_50], 10h
0x180037c27  mov     rcx, [rdx+28h]
0x180037c2b  lea     rax, [rdx+18h]
0x180037c2f  mov     [rbp+37h+var_48], rax
0x180037c33  mov     rax, rsi
0x180037c36  inc     rax
0x180037c39  cmp     [rcx+rax*2], di
0x180037c3d  jnz     short loc_180037C36
0x180037c3f  add     eax, eax
0x180037c41  mov     [rbp+37h+var_38], rcx
0x180037c45  mov     rcx, r13
0x180037c48  mov     [rbp+37h+var_40], eax
0x180037c4b  lea     r8, [rbp+37h+var_50]
0x180037c4f  call    I_ServerCacheRemoveItem
0x180037c54  mov     ecx, [r13+50h]
0x180037c58  add     ecx, r15d
0x180037c5b  cmp     [r13+58h], ecx
0x180037c5f  jb      short loc_180037C1C
0x180037c61  mov     rax, [r13+30h]
0x180037c65  mov     ecx, 50h ; 'P'
0x180037c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037c6f  xor     ebx, ebx
0x180037c71  mov     rdi, rax
0x180037c74  test    rax, rax
0x180037c77  jnz     short loc_180037CCE
0x180037c79  lea     edx, [rax+2]
0x180037c7c  call    WppTraceIndent
0x180037c81  lea     ebx, [rdi+8]
0x180037c84  mov     rcx, cs:WPP_GLOBAL_Control
0x180037c8b  lea     r14, WPP_GLOBAL_Control
0x180037c92  cmp     rcx, r14
0x180037c95  jz      loc_180038018
0x180037c9b  test    byte ptr [rcx+1Ch], 1
0x180037c9f  jz      loc_180038018
0x180037ca5  cmp     byte ptr [rcx+19h], 2
0x180037ca9  jb      loc_180038018
0x180037caf  mov     r9, cs:WPP_pszIndent
0x180037cb6  lea     edx, [rdi+1Dh]
0x180037cb9  mov     rcx, [rcx+10h]
0x180037cbd  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180037cc4  call    WPP_SF_s
0x180037cc9  jmp     loc_180038018
0x180037cce  mov     rcx, rsi
0x180037cd1  inc     rcx
0x180037cd4  cmp     [r14+rcx*2], bx
0x180037cd9  jnz     short loc_180037CD1
0x180037cdb  mov     rax, [r13+30h]
0x180037cdf  lea     rcx, ds:2[rcx*2]
0x180037ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037cec  mov     [rdi+28h], rax
0x180037cf0  test    rax, rax
0x180037cf3  jnz     short loc_180037D32
0x180037cf5  lea     edx, [rax+2]
0x180037cf8  call    WppTraceIndent
0x180037cfd  mov     ebx, 8
0x180037d02  mov     rcx, cs:WPP_GLOBAL_Control
0x180037d09  lea     r14, WPP_GLOBAL_Control
0x180037d10  cmp     rcx, r14
0x180037d13  jz      loc_180037E63
0x180037d19  test    byte ptr [rcx+1Ch], 1
0x180037d1d  jz      loc_180037E63
0x180037d23  cmp     byte ptr [rcx+19h], 2
0x180037d27  jb      loc_180037E63
0x180037d2d  lea     edx, [rbx+16h]
0x180037d30  jmp     short loc_180037DA5
0x180037d32  mov     r8, rsi
0x180037d35  inc     r8
0x180037d38  cmp     [r14+r8*2], bx
0x180037d3d  jnz     short loc_180037D35
0x180037d3f  lea     r8, ds:2[r8*2]; Size
0x180037d47  mov     rdx, r14; Src
0x180037d4a  mov     rcx, rax; void *
0x180037d4d  call    memcpy_0
0x180037d52  mov     [rdi+8], r15d
0x180037d56  mov     rcx, r15
0x180037d59  mov     rax, [r13+30h]
0x180037d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037d62  mov     [rdi], rax
0x180037d65  test    rax, rax
0x180037d68  jnz     short loc_180037DC1
0x180037d6a  lea     edx, [rax+2]
0x180037d6d  call    WppTraceIndent
0x180037d72  mov     ebx, 8
0x180037d77  mov     rcx, cs:WPP_GLOBAL_Control
0x180037d7e  lea     r14, WPP_GLOBAL_Control
0x180037d85  cmp     rcx, r14
0x180037d88  jz      loc_180037E63
0x180037d8e  test    byte ptr [rcx+1Ch], 1
0x180037d92  jz      loc_180037E63
0x180037d98  cmp     byte ptr [rcx+19h], 2
0x180037d9c  jb      loc_180037E63
0x180037da2  lea     edx, [rbx+17h]
0x180037da5  mov     r9, cs:WPP_pszIndent
0x180037dac  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180037db3  mov     rcx, [rcx+10h]
0x180037db7  call    WPP_SF_s
0x180037dbc  jmp     loc_180037E63
0x180037dc1  mov     r8d, [rdi+8]; Size
0x180037dc5  mov     rcx, rax; void *
0x180037dc8  mov     rdx, [rbp+37h+Src]; Src
0x180037dcc  call    memcpy_0
0x180037dd1  mov     eax, [rbp+37h+arg_10]
0x180037dd4  lea     rcx, [rdi+10h]; Time
0x180037dd8  mov     [rdi+0Ch], eax
0x180037ddb  call    cs:__imp_time
0x180037de1  movups  xmm0, xmmword ptr [r12]
0x180037de6  mov     qword ptr [rbp+37h+var_60+8], rdi
0x180037dea  mov     dword ptr [rbp+37h+var_60], 50h ; 'P'
0x180037df1  movdqu  xmmword ptr [rdi+18h], xmm0
0x180037df6  mov     [rbp+37h+var_50], 10h
0x180037dfd  mov     [rbp+37h+var_48], r12
0x180037e01  inc     rsi
0x180037e04  cmp     [r14+rsi*2], bx
0x180037e09  jnz     short loc_180037E01
0x180037e0b  mov     rcx, [r13+28h]
0x180037e0f  lea     eax, [rsi+rsi]
0x180037e12  lea     r9, [rbp+37h+var_60]
0x180037e16  mov     [rbp+37h+var_40], eax
0x180037e19  lea     rdx, [rbp+37h+var_50]
0x180037e1d  mov     [rbp+37h+var_38], r14
0x180037e21  call    CacheAddItem
0x180037e26  mov     ebx, eax
0x180037e28  test    eax, eax
0x180037e2a  jnz     short loc_180037E5C
0x180037e2c  mov     rax, [r13+48h]
0x180037e30  mov     [rdi+30h], rax
0x180037e34  test    rax, rax
0x180037e37  jz      short loc_180037E3D
0x180037e39  mov     [rax+38h], rdi
0x180037e3d  cmp     qword ptr [r13+40h], 0
0x180037e42  mov     [r13+48h], rdi
0x180037e46  jnz     short loc_180037E4C
0x180037e48  mov     [r13+40h], rdi
0x180037e4c  mov     eax, [rdi+8]
0x180037e4f  add     [r13+50h], eax
0x180037e53  inc     dword ptr [r13+54h]
0x180037e57  jmp     loc_180038011
0x180037e5c  lea     r14, WPP_GLOBAL_Control
0x180037e63  mov     rdx, rdi
0x180037e66  mov     rcx, r13
0x180037e69  call    I_ServerCacheFreeItem
0x180037e6e  jmp     loc_180038018
0x180037e73  mov     rdi, qword ptr [rbp+37h+var_60+8]
0x180037e77  mov     r14d, [rbp+37h+arg_10]
0x180037e7b  cmp     [rdi+0Ch], r14d
0x180037e7f  jnz     short loc_180037EA4
0x180037e81  cmp     [rdi+8], r15d
0x180037e85  jnz     short loc_180037EA4
0x180037e87  mov     r8d, [rdi+8]; Size
0x180037e8b  mov     rdx, [rbp+37h+Src]; Buf2
0x180037e8f  mov     rcx, [rdi]; Buf1
0x180037e92  call    memcmp_0
0x180037e97  xor     r12d, r12d
0x180037e9a  test    eax, eax
0x180037e9c  jz      loc_180038006
0x180037ea2  jmp     short loc_180037EA7
0x180037ea4  xor     r12d, r12d
0x180037ea7  mov     rdx, rdi
0x180037eaa  mov     [rdi+0Ch], r14d
0x180037eae  mov     rcx, r13
0x180037eb1  call    I_ServerCacheSetMRU
0x180037eb6  jmp     short loc_180037EF1
0x180037eb8  mov     rdx, [r13+40h]
0x180037ebc  mov     [rbp+37h+var_50], 10h
0x180037ec3  mov     rcx, [rdx+28h]
0x180037ec7  lea     rax, [rdx+18h]
0x180037ecb  mov     [rbp+37h+var_48], rax
0x180037ecf  mov     rax, rsi
0x180037ed2  inc     rax
0x180037ed5  cmp     [rcx+rax*2], r12w
0x180037eda  jnz     short loc_180037ED2
0x180037edc  add     eax, eax
0x180037ede  mov     [rbp+37h+var_38], rcx
0x180037ee2  mov     rcx, r13
0x180037ee5  mov     [rbp+37h+var_40], eax
0x180037ee8  lea     r8, [rbp+37h+var_50]
0x180037eec  call    I_ServerCacheRemoveItem
0x180037ef1  mov     eax, r15d
0x180037ef4  sub     eax, [rdi+8]
0x180037ef7  add     eax, [r13+50h]
0x180037efb  cmp     [r13+58h], eax
0x180037eff  jb      short loc_180037EB8
0x180037f01  mov     rcx, [rdi]
0x180037f04  mov     rax, [r13+38h]
0x180037f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f0d  mov     [rdi], r12
0x180037f10  mov     rcx, r15
0x180037f13  mov     rax, [r13+30h]
0x180037f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f1c  mov     [rdi], rax
0x180037f1f  test    rax, rax
  ... truncated ...
```
