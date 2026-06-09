# MergeSdbp_VerifyPredictedMergeChecksumMatches(ushort const *,ushort const *,ushort const *)

- ea: `0x1400242ac`
- end: `0x1400244c6`
- name: `?MergeSdbp_VerifyPredictedMergeChecksumMatches@@YAKPEBG00@Z`
- size: `538`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140024958`

## callees

- `0x14000d8ac`
- `0x14001008c`
- `0x140013cb8`
- `0x140014380`
- `0x1400143d8`
- `0x140014574`
- `0x140016198`
- `0x1400242ac`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400242d2`
- `KERNEL32!GetLastError` at `0x14002431e`
- `KERNEL32!GetLastError` at `0x14002436a`
- `KERNEL32!GetLastError` at `0x1400242d2`
- `KERNEL32!GetLastError` at `0x14002431e`
- `KERNEL32!GetLastError` at `0x14002436a`

## string_xrefs

- `0x1400242e4`: `Failed to open baseline SDB (%d)`
- `0x140024370`: `Failed to open result SDB (%d)`
- `0x140024324`: `Failed to open merge SDB (%d)`

## pseudocode

```c
__int64 __fastcall MergeSdbp_VerifyPredictedMergeChecksumMatches(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v5; // rdx
  __int64 v6; // r14
  DWORD LastError; // ebx
  __int64 v8; // rdx
  __int64 v9; // rdi
  __int64 v10; // rsi
  DWORD v11; // eax
  const char *v12; // r9
  __int64 v13; // r8
  unsigned int FirstTag; // eax
  unsigned int v15; // ebx
  unsigned int FirstTagBefore; // eax
  int DWORDTag; // ebp
  unsigned int v18; // eax
  int v19; // ebx
  __int64 v20; // rdx
  unsigned int v21; // r11d
  __int64 v22; // r8
  unsigned int v23; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  unsigned int v27; // eax

  v6 = SdbOpenDatabaseEx(a1, a2, 16);
  if ( !v6 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1;
    AslLogCallPrintf(
      1,
      "MergeSdbp_VerifyPredictedMergeChecksumMatches",
      803,
      "Failed to open baseline SDB (%d)",
      LastError);
    return LastError;
  }
  v9 = SdbOpenDatabaseEx(a2, v5, 16);
  if ( !v9 )
  {
    v10 = 0;
    v11 = GetLastError();
    v12 = "Failed to open merge SDB (%d)";
    v13 = 808;
    goto LABEL_7;
  }
  v10 = SdbOpenDatabaseEx(a3, v8, 16);
  if ( !v10 )
  {
    v11 = GetLastError();
    v12 = "Failed to open result SDB (%d)";
    v13 = 813;
LABEL_7:
    LastError = v11;
    if ( !v11 )
      LastError = 1;
    goto LABEL_9;
  }
  FirstTag = SdbFindFirstTag(v9, 0, 28673);
  v15 = FirstTag;
  if ( !FirstTag )
  {
    LastError = 1359;
    v12 = "Failed to find TAG_DATABASE (%d)";
    v13 = 829;
LABEL_9:
    AslLogCallPrintf(1, "MergeSdbp_VerifyPredictedMergeChecksumMatches", v13, v12, LastError);
    goto LABEL_25;
  }
  FirstTagBefore = SdbFindFirstTagBefore(v9, FirstTag, 16479);
  if ( FirstTagBefore )
  {
    DWORDTag = SdbReadDWORDTag(v9, FirstTagBefore, 0);
    if ( DWORDTag )
    {
      v18 = SdbFindFirstTagBefore(v9, v15, 16478);
      if ( v18 )
      {
        v19 = SdbReadDWORDTag(v9, v18, 0);
        if ( v19 )
        {
          v20 = *(_QWORD *)(v6 + 8);
          v21 = 1;
          if ( !v20 || (v22 = *(unsigned int *)(v6 + 20), !(_DWORD)v22) || (v23 = AslComputeCrc32(0, v20, v22)) == 0 )
            v23 = v21;
          if ( DWORDTag == v23 )
          {
            v25 = *(_QWORD *)(v10 + 8);
            if ( !v25 || (v26 = *(unsigned int *)(v10 + 20), !(_DWORD)v26) || (v27 = AslComputeCrc32(0, v25, v26)) == 0 )
              v27 = v21;
            if ( v19 != v27 )
            {
              AslLogCallPrintf(
                v21,
                "MergeSdbp_VerifyPredictedMergeChecksumMatches",
                877,
                "Merge result has mismatched checksum (0x%x vs 0x%x)",
                v19,
                v27);
              LastError = 1358;
              goto LABEL_25;
            }
          }
          else
          {
            AslLogCallPrintf(
              3,
              "MergeSdbp_VerifyPredictedMergeChecksumMatches",
              862,
              "Merge sdb provided checksum tags, but baseline did not match, so verification was not applied.");
          }
        }
      }
    }
  }
  LastError = 0;
LABEL_25:
  SdbCloseDatabase(v6);
  if ( v9 )
    SdbCloseDatabase(v9);
  if ( v10 )
    SdbCloseDatabase(v10);
  return LastError;
}

```

## disassembly

```asm
0x1400242ac  push    rbx
0x1400242ae  push    rbp
0x1400242af  push    rsi
0x1400242b0  push    rdi
0x1400242b1  push    r14
0x1400242b3  sub     rsp, 30h
0x1400242b7  mov     rsi, r8
0x1400242ba  mov     ebp, 10h
0x1400242bf  mov     r8d, ebp
0x1400242c2  mov     rbx, rdx
0x1400242c5  call    SdbOpenDatabaseEx
0x1400242ca  mov     r14, rax
0x1400242cd  test    rax, rax
0x1400242d0  jnz     short loc_140024309
0x1400242d2  call    cs:__imp_GetLastError
0x1400242d8  lea     r11d, [rbp-0Fh]
0x1400242dc  mov     r8d, 323h
0x1400242e2  test    eax, eax
0x1400242e4  lea     r9, aFailedToOpenBa; "Failed to open baseline SDB (%d)"
0x1400242eb  mov     ebx, eax
0x1400242ed  lea     rdx, aMergesdbpVerif; "MergeSdbp_VerifyPredictedMergeChecksumM"...
0x1400242f4  cmovz   ebx, r11d
0x1400242f8  mov     ecx, r11d
0x1400242fb  mov     [rsp+58h+var_38], ebx
0x1400242ff  call    AslLogCallPrintf
0x140024304  jmp     loc_14002446A
0x140024309  mov     r8d, ebp
0x14002430c  mov     rcx, rbx
0x14002430f  call    SdbOpenDatabaseEx
0x140024314  mov     rdi, rax
0x140024317  test    rax, rax
0x14002431a  jnz     short loc_140024357
0x14002431c  xor     esi, esi
0x14002431e  call    cs:__imp_GetLastError
0x140024324  lea     r9, aFailedToOpenMe; "Failed to open merge SDB (%d)"
0x14002432b  mov     r8d, 328h
0x140024331  mov     r11d, 1
0x140024337  test    eax, eax
0x140024339  mov     ebx, eax
0x14002433b  mov     ecx, r11d
0x14002433e  cmovz   ebx, r11d
0x140024342  lea     rdx, aMergesdbpVerif; "MergeSdbp_VerifyPredictedMergeChecksumM"...
0x140024349  mov     [rsp+58h+var_38], ebx
0x14002434d  call    AslLogCallPrintf
0x140024352  jmp     loc_140024448
0x140024357  mov     r8d, ebp
0x14002435a  mov     rcx, rsi
0x14002435d  call    SdbOpenDatabaseEx
0x140024362  mov     rsi, rax
0x140024365  test    rax, rax
0x140024368  jnz     short loc_14002437F
0x14002436a  call    cs:__imp_GetLastError
0x140024370  lea     r9, aFailedToOpenRe; "Failed to open result SDB (%d)"
0x140024377  mov     r8d, 32Dh
0x14002437d  jmp     short loc_140024331
0x14002437f  xor     edx, edx
0x140024381  mov     r8d, 7001h
0x140024387  mov     rcx, rdi
0x14002438a  call    SdbFindFirstTag
0x14002438f  mov     ebx, eax
0x140024391  test    eax, eax
0x140024393  jnz     short loc_1400243AC
0x140024395  mov     ebx, 54Fh
0x14002439a  lea     r9, aFailedToFindTa_1; "Failed to find TAG_DATABASE (%d)"
0x1400243a1  mov     r8d, 33Dh
0x1400243a7  lea     ecx, [rax+1]
0x1400243aa  jmp     short loc_140024342
0x1400243ac  mov     r8d, 405Fh
0x1400243b2  mov     edx, ebx
0x1400243b4  mov     rcx, rdi
0x1400243b7  call    SdbFindFirstTagBefore
0x1400243bc  test    eax, eax
0x1400243be  jz      loc_140024446
0x1400243c4  xor     r8d, r8d
0x1400243c7  mov     edx, eax
0x1400243c9  mov     rcx, rdi
0x1400243cc  call    SdbReadDWORDTag
0x1400243d1  mov     ebp, eax
0x1400243d3  test    eax, eax
0x1400243d5  jz      short loc_140024446
0x1400243d7  mov     r8d, 405Eh
0x1400243dd  mov     edx, ebx
0x1400243df  mov     rcx, rdi
0x1400243e2  call    SdbFindFirstTagBefore
0x1400243e7  test    eax, eax
0x1400243e9  jz      short loc_140024446
0x1400243eb  xor     r8d, r8d
0x1400243ee  mov     edx, eax
0x1400243f0  mov     rcx, rdi
0x1400243f3  call    SdbReadDWORDTag
0x1400243f8  mov     ebx, eax
0x1400243fa  test    eax, eax
0x1400243fc  jz      short loc_140024446
0x1400243fe  mov     rdx, [r14+8]
0x140024402  mov     r11d, 1
0x140024408  test    rdx, rdx
0x14002440b  jz      short loc_140024421
0x14002440d  mov     r8d, [r14+14h]
0x140024411  test    r8d, r8d
0x140024414  jz      short loc_140024421
0x140024416  xor     ecx, ecx
0x140024418  call    AslComputeCrc32
0x14002441d  test    eax, eax
0x14002441f  jnz     short loc_140024424
0x140024421  mov     eax, r11d
0x140024424  cmp     ebp, eax
0x140024426  jz      short loc_140024477
0x140024428  lea     r9, aMergeSdbProvid; "Merge sdb provided checksum tags, but b"...
0x14002442f  mov     r8d, 35Eh
0x140024435  lea     rdx, aMergesdbpVerif; "MergeSdbp_VerifyPredictedMergeChecksumM"...
0x14002443c  mov     ecx, 3
0x140024441  call    AslLogCallPrintf
0x140024446  xor     ebx, ebx
0x140024448  mov     rcx, r14
0x14002444b  call    SdbCloseDatabase
0x140024450  test    rdi, rdi
0x140024453  jz      short loc_14002445D
0x140024455  mov     rcx, rdi
0x140024458  call    SdbCloseDatabase
0x14002445d  test    rsi, rsi
0x140024460  jz      short loc_14002446A
0x140024462  mov     rcx, rsi
0x140024465  call    SdbCloseDatabase
0x14002446a  mov     eax, ebx
0x14002446c  add     rsp, 30h
0x140024470  pop     r14
0x140024472  pop     rdi
0x140024473  pop     rsi
0x140024474  pop     rbp
0x140024475  pop     rbx
0x140024476  retn
0x140024477  mov     rdx, [rsi+8]
0x14002447b  test    rdx, rdx
0x14002447e  jz      short loc_140024494
0x140024480  mov     r8d, [rsi+14h]
0x140024484  test    r8d, r8d
0x140024487  jz      short loc_140024494
0x140024489  xor     ecx, ecx
0x14002448b  call    AslComputeCrc32
0x140024490  test    eax, eax
0x140024492  jnz     short loc_140024497
0x140024494  mov     eax, r11d
0x140024497  cmp     ebx, eax
0x140024499  jz      short loc_140024446
0x14002449b  mov     [rsp+58h+var_30], eax
0x14002449f  lea     r9, aMergeResultHas; "Merge result has mismatched checksum (0"...
0x1400244a6  mov     r8d, 36Dh
0x1400244ac  mov     [rsp+58h+var_38], ebx
0x1400244b0  lea     rdx, aMergesdbpVerif; "MergeSdbp_VerifyPredictedMergeChecksumM"...
0x1400244b7  mov     ecx, r11d
0x1400244ba  call    AslLogCallPrintf
0x1400244bf  mov     ebx, 54Eh
0x1400244c4  jmp     short loc_140024448
```
