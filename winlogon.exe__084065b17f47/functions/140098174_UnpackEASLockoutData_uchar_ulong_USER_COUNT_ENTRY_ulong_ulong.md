# UnpackEASLockoutData(uchar *,ulong,_USER_COUNT_ENTRY * *,ulong *,ulong *)

- ea: `0x140098174`
- end: `0x1400983db`
- name: `?UnpackEASLockoutData@@YAKPEAEKPEAPEAU_USER_COUNT_ENTRY@@PEAK2@Z`
- size: `615`
- prototype: `unsigned int __fastcall(unsigned __int8 *, unsigned int, struct _USER_COUNT_ENTRY **, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140037e2c`

## callees

- `0x140038250`
- `0x14005f18c`
- `0x140098174`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140098319`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140098319`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14009839e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14009839e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140098303`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140098390`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140098303`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140098390`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400981f4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140098371`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400981f4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140098371`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x140098204`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x140098204`

## string_xrefs

- `0x1400982a2`: `onecore\ds\security\eas\policyengine\extnlib\fvewrappers.cpp`
- `0x140098225`: `Lockout Metadata Invalid - Invalid SID Entry`
- `0x140098269`: `Lockout Metadata Invalid - Total Size < sizeof(SID)`
- `0x140098247`: `Lockout Metadata Invalid - Total Size < SIDLength`

## pseudocode

```c
__int64 __fastcall UnpackEASLockoutData(
        unsigned __int8 *a1,
        int a2,
        struct _USER_COUNT_ENTRY **a3,
        unsigned int *a4,
        unsigned int *a5)
{
  unsigned int *v5; // r13
  unsigned int v6; // esi
  struct _USER_COUNT_ENTRY **v8; // r12
  int v9; // ebp
  unsigned __int8 *v10; // r14
  int i; // ebx
  unsigned int v12; // ebx
  unsigned __int8 *v13; // r15
  DWORD LengthSid; // eax
  __int64 v15; // r12
  unsigned int v16; // eax
  HANDLE ProcessHeap; // rax
  void *v18; // rsi
  unsigned int v19; // ebx
  unsigned int v20; // r15d
  DWORD v21; // eax
  HANDLE v22; // rax
  int v24; // [rsp+20h] [rbp-68h]
  const wchar_t *v25; // [rsp+28h] [rbp-60h]
  __int128 v26; // [rsp+40h] [rbp-48h]
  SIZE_T dwBytes; // [rsp+90h] [rbp+8h] BYREF
  struct _USER_COUNT_ENTRY **v28; // [rsp+A0h] [rbp+18h]

  v28 = a3;
  v5 = a5;
  v6 = 0;
  *a3 = 0;
  *a4 = 0;
  LODWORD(dwBytes) = 0;
  v8 = a3;
  *v5 = 0;
  v9 = a2;
  v10 = a1;
  DWORD1(v26) = 0;
  if ( a1 && a2 )
  {
    for ( i = a2; i > 0; i = v12 - v15 )
    {
      if ( (unsigned int)i < 4 )
      {
        v25 = L"Lockout Metadata Invalid - Total Size < sizeof(DWORD)";
        v24 = 240;
        goto LABEL_14;
      }
      v12 = i - 4;
      if ( v12 < 0xC )
      {
        v25 = L"Lockout Metadata Invalid - Total Size < sizeof(SID)";
        v24 = 253;
        goto LABEL_14;
      }
      v13 = a1 + 4;
      LengthSid = GetLengthSid(a1 + 4);
      v15 = LengthSid;
      if ( v12 < LengthSid )
      {
        v25 = L"Lockout Metadata Invalid - Total Size < SIDLength";
        v24 = 264;
        goto LABEL_14;
      }
      if ( !IsValidSid(v13) )
      {
        v25 = L"Lockout Metadata Invalid - Invalid SID Entry";
        v24 = 274;
LABEL_14:
        DbgPrintfW(
          1u,
          L"(0x%08x) %ws:%u : %ws:%ws\n",
          0,
          L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
          v24,
          v25,
          &pPassword);
        v8 = v28;
        v16 = 1;
        *a4 = 0;
        goto LABEL_17;
      }
      ++v6;
      a1 = &v13[v15];
    }
    v8 = v28;
  }
  v16 = v6 + 1;
  *a4 = v6;
  if ( v6 + 1 < v6 )
    goto LABEL_30;
LABEL_17:
  *v5 = v16;
  if ( (unsigned int)ULongLongToULong(16LL * v16, (unsigned int *)&dwBytes) )
  {
LABEL_30:
    v19 = 534;
    goto LABEL_31;
  }
  ProcessHeap = GetProcessHeap();
  v18 = HeapAlloc(ProcessHeap, 8u, (unsigned int)dwBytes);
  if ( !v18 )
  {
    v19 = 14;
LABEL_31:
    *a4 = 0;
    *v5 = 0;
    return v19;
  }
  if ( v10 && v9 && *a4 )
  {
    v20 = 0;
    while ( v9 > 0 )
    {
      if ( (unsigned int)v9 < 4 || v20 >= *a4 )
      {
        v19 = 1359;
        v22 = GetProcessHeap();
        HeapFree(v22, 0, v18);
        goto LABEL_31;
      }
      LODWORD(v26) = *(_DWORD *)v10;
      *((_QWORD *)&v26 + 1) = v10 + 4;
      *((_OWORD *)v18 + v20) = v26;
      v21 = GetLengthSid(v10 + 4);
      v10 += v21 + 4;
      v9 += -4 - v21;
      ++v20;
    }
  }
  *v8 = (struct _USER_COUNT_ENTRY *)v18;
  return 0;
}

```

## disassembly

```asm
0x140098174  mov     rax, rsp
0x140098177  mov     [rax+10h], rbx
0x14009817b  mov     [rax+18h], r8
0x14009817f  push    rbp
0x140098180  push    rsi
0x140098181  push    rdi
0x140098182  push    r12
0x140098184  push    r13
0x140098186  push    r14
0x140098188  push    r15
0x14009818a  sub     rsp, 50h
0x14009818e  mov     r13, [rsp+88h+arg_20]
0x140098196  xor     esi, esi
0x140098198  mov     [r8], rsi
0x14009819b  xorps   xmm0, xmm0
0x14009819e  mov     [r9], esi
0x1400981a1  mov     rdi, r9
0x1400981a4  mov     dword ptr [rax+8], 0
0x1400981ab  mov     r12, r8
0x1400981ae  mov     [r13+0], esi
0x1400981b2  mov     ebp, edx
0x1400981b4  mov     r14, rcx
0x1400981b7  movups  xmmword ptr [rax-48h], xmm0
0x1400981bb  test    rcx, rcx
0x1400981be  jz      loc_1400982D7
0x1400981c4  test    edx, edx
0x1400981c6  jz      loc_1400982D7
0x1400981cc  mov     ebx, edx
0x1400981ce  test    ebx, ebx
0x1400981d0  jle     loc_1400982CF
0x1400981d6  cmp     ebx, 4
0x1400981d9  jb      loc_14009827F
0x1400981df  mov     eax, [rcx]
0x1400981e1  add     ebx, 0FFFFFFFCh
0x1400981e4  mov     dword ptr [rsp+88h+var_48], eax
0x1400981e8  cmp     ebx, 0Ch
0x1400981eb  jb      short loc_14009825D
0x1400981ed  lea     r15, [rcx+4]
0x1400981f1  mov     rcx, r15; pSid
0x1400981f4  call    cs:__imp_GetLengthSid
0x1400981fa  mov     r12d, eax
0x1400981fd  cmp     ebx, eax
0x1400981ff  jb      short loc_14009823B
0x140098201  mov     rcx, r15; pSid
0x140098204  call    cs:__imp_IsValidSid
0x14009820a  test    eax, eax
0x14009820c  jz      short loc_140098219
0x14009820e  inc     esi
0x140098210  lea     rcx, [r15+r12]
0x140098214  sub     ebx, r12d
0x140098217  jmp     short loc_1400981CE
0x140098219  lea     rax, pPassword
0x140098220  mov     [rsp+88h+var_58], rax
0x140098225  lea     rax, aLockoutMetadat_1; "Lockout Metadata Invalid - Invalid SID "...
0x14009822c  mov     [rsp+88h+var_60], rax
0x140098231  mov     [rsp+88h+var_68], 112h
0x140098239  jmp     short loc_14009829F
0x14009823b  lea     rax, pPassword
0x140098242  mov     [rsp+88h+var_58], rax
0x140098247  lea     rax, aLockoutMetadat; "Lockout Metadata Invalid - Total Size <"...
0x14009824e  mov     [rsp+88h+var_60], rax
0x140098253  mov     [rsp+88h+var_68], 108h
0x14009825b  jmp     short loc_14009829F
0x14009825d  lea     rax, pPassword
0x140098264  mov     [rsp+88h+var_58], rax
0x140098269  lea     rax, aLockoutMetadat_0; "Lockout Metadata Invalid - Total Size <"...
0x140098270  mov     [rsp+88h+var_60], rax
0x140098275  mov     [rsp+88h+var_68], 0FDh
0x14009827d  jmp     short loc_14009829F
0x14009827f  lea     rax, pPassword
0x140098286  mov     [rsp+88h+var_58], rax
0x14009828b  lea     rax, aLockoutMetadat_2; "Lockout Metadata Invalid - Total Size <"...
0x140098292  mov     [rsp+88h+var_60], rax
0x140098297  mov     [rsp+88h+var_68], 0F0h
0x14009829f  xor     r8d, r8d
0x1400982a2  lea     r9, aOnecoreDsSecur_2; "onecore\\ds\\security\\eas\\policyengin"...
0x1400982a9  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x1400982b0  lea     r15d, [r8+1]
0x1400982b4  mov     ecx, r15d; unsigned int
0x1400982b7  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x1400982bc  mov     r12, [rsp+88h+arg_10]
0x1400982c4  mov     eax, r15d
0x1400982c7  mov     dword ptr [rdi], 0
0x1400982cd  jmp     short loc_1400982E4
0x1400982cf  mov     r12, [rsp+88h+arg_10]
0x1400982d7  lea     eax, [rsi+1]
0x1400982da  mov     [rdi], esi
0x1400982dc  cmp     eax, esi
0x1400982de  jb      loc_1400983AE
0x1400982e4  mov     ecx, eax
0x1400982e6  lea     rdx, [rsp+88h+dwBytes]; unsigned int *
0x1400982ee  shl     rcx, 4; unsigned __int64
0x1400982f2  mov     [r13+0], eax
0x1400982f6  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1400982fb  test    eax, eax
0x1400982fd  jnz     loc_1400983AE
0x140098303  call    cs:__imp_GetProcessHeap
0x140098309  mov     r8d, dword ptr [rsp+88h+dwBytes]; dwBytes
0x140098311  mov     edx, 8; dwFlags
0x140098316  mov     rcx, rax; hHeap
0x140098319  call    cs:__imp_HeapAlloc
0x14009831f  mov     rsi, rax
0x140098322  test    rax, rax
0x140098325  jnz     short loc_14009832F
0x140098327  lea     ebx, [rax+0Eh]
0x14009832a  jmp     loc_1400983B3
0x14009832f  test    r14, r14
0x140098332  jz      short loc_1400983A6
0x140098334  test    ebp, ebp
0x140098336  jz      short loc_1400983A6
0x140098338  cmp     dword ptr [rdi], 0
0x14009833b  jz      short loc_1400983A6
0x14009833d  xor     r15d, r15d
0x140098340  test    ebp, ebp
0x140098342  jle     short loc_1400983A6
0x140098344  cmp     ebp, 4
0x140098347  jb      short loc_14009838B
0x140098349  lea     rbx, [r14+4]
0x14009834d  mov     eax, [r14]
0x140098350  mov     qword ptr [rsp+88h+var_48+8], rbx
0x140098355  mov     dword ptr [rsp+88h+var_48], eax
0x140098359  cmp     r15d, [rdi]
0x14009835c  jnb     short loc_14009838B
0x14009835e  movups  xmm0, [rsp+88h+var_48]
0x140098363  mov     eax, r15d
0x140098366  mov     rcx, rbx; pSid
0x140098369  add     rax, rax
0x14009836c  movdqu  xmmword ptr [rsi+rax*8], xmm0
0x140098371  call    cs:__imp_GetLengthSid
0x140098377  mov     ecx, 0FFFFFFFCh
0x14009837c  mov     r14d, eax
0x14009837f  sub     ecx, eax
0x140098381  add     r14, rbx
0x140098384  add     ebp, ecx
0x140098386  inc     r15d
0x140098389  jmp     short loc_140098340
0x14009838b  mov     ebx, 54Fh
0x140098390  call    cs:__imp_GetProcessHeap
0x140098396  mov     r8, rsi; lpMem
0x140098399  xor     edx, edx; dwFlags
0x14009839b  mov     rcx, rax; hHeap
0x14009839e  call    cs:__imp_HeapFree
0x1400983a4  jmp     short loc_1400983B3
0x1400983a6  mov     [r12], rsi
0x1400983aa  xor     ebx, ebx
0x1400983ac  jmp     short loc_1400983C1
0x1400983ae  mov     ebx, 216h
0x1400983b3  mov     dword ptr [rdi], 0
0x1400983b9  mov     dword ptr [r13+0], 0
0x1400983c1  mov     eax, ebx
0x1400983c3  mov     rbx, [rsp+88h+arg_8]
0x1400983cb  add     rsp, 50h
0x1400983cf  pop     r15
0x1400983d1  pop     r14
0x1400983d3  pop     r13
0x1400983d5  pop     r12
0x1400983d7  pop     rdi
0x1400983d8  pop     rsi
0x1400983d9  pop     rbp
0x1400983da  retn
```
