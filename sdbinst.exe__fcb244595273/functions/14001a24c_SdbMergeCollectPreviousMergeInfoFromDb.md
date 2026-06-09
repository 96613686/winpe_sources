# SdbMergeCollectPreviousMergeInfoFromDb

- ea: `0x14001a24c`
- end: `0x14001a670`
- name: `SdbMergeCollectPreviousMergeInfoFromDb`
- size: `1060`
- prototype: `__int64 __fastcall(__int64, unsigned int, _OWORD *)`
- caller_count: `2`
- callee_count: `13`
- tags: ``

## callers

- `0x14001b7e8`
- `0x14002b138`

## callees

- `0x140002206`
- `0x14000fb1c`
- `0x14001008c`
- `0x140010d44`
- `0x140013898`
- `0x140013cb8`
- `0x140013dc0`
- `0x140014380`
- `0x14001443c`
- `0x140016148`
- `0x14001a24c`
- `0x14002e3e2`
- `0x14002e420`

## string_xrefs

- `0x14001a3e4`: `Failed to read TAG_NAME string from pdb`
- `0x14001a57f`: `Failed to read string from pdb`

## pseudocode

```c
__int64 __fastcall SdbMergeCollectPreviousMergeInfoFromDb(__int64 a1, unsigned int a2, _OWORD *a3)
{
  _OWORD *v3; // r15
  __int64 result; // rax
  __int16 TagFromTagID; // ax
  unsigned int FirstTag; // r14d
  unsigned int v9; // r15d
  unsigned int v10; // edi
  unsigned int v11; // r13d
  const char *v12; // r9
  __int64 v13; // r8
  const wchar_t *StringTagPtr; // r12
  unsigned __int64 i; // rcx
  __int64 *v16; // rdi
  char *v17; // rax
  signed __int64 v18; // r9
  int v19; // edx
  int v20; // r8d
  int DWORDTag; // eax
  int v22; // ecx
  int v23; // eax
  int v24; // eax
  unsigned int v25; // eax
  __int64 *p_Src; // rdx
  __int64 v27; // rax
  GUID *v28; // r9
  int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int64 v36; // [rsp+20h] [rbp-79h]
  int v37; // [rsp+40h] [rbp-59h] BYREF
  unsigned int v38; // [rsp+44h] [rbp-55h]
  __int64 Src; // [rsp+48h] [rbp-51h] BYREF
  _OWORD *v40; // [rsp+50h] [rbp-49h]
  _OWORD v41[4]; // [rsp+60h] [rbp-39h] BYREF
  __int128 v42; // [rsp+A0h] [rbp+7h]

  v40 = a3;
  v38 = a2;
  v3 = a3;
  v37 = 0;
  Src = 0;
  if ( !a1 )
  {
    AslLogCallPrintf(1, "SdbMergeCollectPreviousMergeInfoFromDb", 2627, "pdb null");
    return 3221225711LL;
  }
  if ( !a3 )
  {
    AslLogCallPrintf(1, "SdbMergeCollectPreviousMergeInfoFromDb", 2632, "pdbMergeHistoryItemInfo null");
    return 3221225713LL;
  }
  memset_0(a3, 0, 0x50u);
  memset_0(v41, 0, 0x50u);
  TagFromTagID = SdbGetTagFromTagID(a1, a2);
  if ( TagFromTagID == 28749 )
  {
    HIDWORD(v42) = 0;
  }
  else
  {
    if ( TagFromTagID != 28750 )
    {
      AslLogCallPrintf(
        1,
        "SdbMergeCollectPreviousMergeInfoFromDb",
        2643,
        "tiSourceMergeDb not either TAG_SOURCE_DB or TAG_MERGE_DB");
      return 3221225712LL;
    }
    HIDWORD(v42) = 1;
  }
  FirstTag = SdbFindFirstTag(a1, a2, 28687);
  if ( !FirstTag )
    goto LABEL_56;
  v9 = v38;
  do
  {
    v10 = SdbFindFirstTag(a1, FirstTag, 24577);
    v11 = SdbFindFirstTag(a1, FirstTag, 16408);
    if ( !v10 )
    {
      v12 = "Failed to find TAG_NAME for TAG_DATA entry (ti: 0x%08x)";
      v13 = 2659;
LABEL_53:
      LODWORD(v36) = FirstTag;
      AslLogCallPrintf(3, "SdbMergeCollectPreviousMergeInfoFromDb", v13, v12, v36);
      goto LABEL_54;
    }
    if ( !v11 )
    {
      v12 = "Failed to find TAG_DATA_VALUETYPE for TAG_DATA entry (ti: 0x%08x)";
      v13 = 2664;
      goto LABEL_53;
    }
    StringTagPtr = (const wchar_t *)SdbGetStringTagPtr(a1, v10);
    if ( StringTagPtr )
    {
      for ( i = 1; i < 9; ++i )
      {
        v16 = &qword_140031000[4 * i];
        v17 = (char *)v16[1];
        if ( v17 )
        {
          v18 = (char *)StringTagPtr - v17;
          do
          {
            v19 = *(unsigned __int16 *)&v17[v18];
            v20 = *(unsigned __int16 *)v17 - v19;
            if ( v20 )
              break;
            v17 += 2;
          }
          while ( v19 );
          if ( !v20 )
            break;
        }
        v16 = 0;
      }
      DWORDTag = SdbReadDWORDTag(a1, v11, 0);
      if ( !v16 )
      {
        AslLogCallPrintf(
          3,
          "SdbMergeCollectPreviousMergeInfoFromDb",
          2690,
          "Unexpected TAG_DATA entry '%S' of type %d",
          StringTagPtr,
          DWORDTag);
        goto LABEL_54;
      }
      v22 = *((_DWORD *)v16 + 6);
      if ( v22 != DWORDTag )
      {
        AslLogCallPrintf(
          3,
          "SdbMergeCollectPreviousMergeInfoFromDb",
          2698,
          "Expected field '%S' did not have the expected data type %d, actual %d",
          StringTagPtr,
          v22,
          DWORDTag);
        goto LABEL_54;
      }
      v23 = DWORDTag - 1;
      if ( v23 )
      {
        v24 = v23 - 3;
        if ( v24 )
        {
          if ( v24 == 7 )
          {
            v25 = SdbFindFirstTag(a1, FirstTag, 20487);
            if ( v25 )
            {
              Src = SdbReadQWORDTag(a1, v25, 0);
              p_Src = &Src;
              goto LABEL_35;
            }
          }
          goto LABEL_52;
        }
        v30 = SdbFindFirstTag(a1, FirstTag, 16409);
        if ( v30 )
        {
          v37 = SdbReadDWORDTag(a1, v30, 0);
          p_Src = (__int64 *)&v37;
          goto LABEL_35;
        }
      }
      else
      {
        v31 = SdbFindFirstTag(a1, FirstTag, 24606);
        if ( v31 )
        {
          p_Src = (__int64 *)SdbGetStringTagPtr(a1, v31);
          if ( !p_Src )
          {
            AslLogCallPrintf(3, "SdbMergeCollectPreviousMergeInfoFromDb", 2732, "Failed to read string from pdb");
            goto LABEL_54;
          }
LABEL_35:
          v27 = *((unsigned int *)v16 + 4);
          v28 = (GUID *)((char *)v41 + v27);
          if ( *((_DWORD *)v16 + 6) != 1 )
          {
            if ( *((_DWORD *)v16 + 6) == 4 || *((_DWORD *)v16 + 6) == 11 )
            {
              memcpy_0((char *)v41 + v27, p_Src, *((unsigned int *)v16 + 5));
              goto LABEL_54;
            }
            v29 = -1073741822;
            goto LABEL_51;
          }
          if ( (unsigned int)(*(_DWORD *)v16 - 4) <= 1 )
          {
            if ( *((_DWORD *)v16 + 5) != 16 )
            {
              v29 = -1073741789;
LABEL_51:
              LODWORD(v36) = v29;
              AslLogCallPrintf(
                3,
                "SdbMergeCollectPreviousMergeInfoFromDb",
                2738,
                "SdbpMergeTagDataToStruct failed [%x]",
                v36);
              goto LABEL_54;
            }
            v29 = AslGuidFromString(v28);
          }
          else
          {
            v29 = AslStringDuplicate(v28, p_Src);
          }
          if ( v29 >= 0 )
            goto LABEL_54;
          goto LABEL_51;
        }
      }
LABEL_52:
      v12 = "Failed to find VALUE tag for TAG_DATA entry (ti: 0x%08x)";
      v13 = 2729;
      goto LABEL_53;
    }
    AslLogCallPrintf(3, "SdbMergeCollectPreviousMergeInfoFromDb", 2670, "Failed to read TAG_NAME string from pdb");
LABEL_54:
    FirstTag = SdbFindNextTag(a1, v9, FirstTag);
  }
  while ( FirstTag );
  v3 = v40;
LABEL_56:
  result = 0;
  v32 = v41[1];
  *v3 = v41[0];
  v33 = v41[2];
  v3[1] = v32;
  v34 = v41[3];
  v3[2] = v33;
  v35 = v42;
  v3[3] = v34;
  v3[4] = v35;
  return result;
}

```

## disassembly

```asm
0x14001a24c  mov     [rsp-8+arg_18], rbx
0x14001a251  push    rbp
0x14001a252  push    rsi
0x14001a253  push    rdi
0x14001a254  push    r12
0x14001a256  push    r13
0x14001a258  push    r14
0x14001a25a  push    r15
0x14001a25c  lea     rbp, [rsp-27h]
0x14001a261  sub     rsp, 0C0h
0x14001a268  mov     rax, cs:__security_cookie
0x14001a26f  xor     rax, rsp
0x14001a272  mov     [rbp+57h+var_40], rax
0x14001a276  xor     r13d, r13d
0x14001a279  mov     [rbp+57h+var_A0], r8
0x14001a27d  mov     [rbp+57h+var_AC], edx
0x14001a280  mov     r15, r8
0x14001a283  mov     [rbp+57h+var_B0], r13d
0x14001a287  mov     ebx, edx
0x14001a289  mov     [rbp+57h+Src], r13
0x14001a28d  mov     rsi, rcx
0x14001a290  test    rcx, rcx
0x14001a293  jnz     short loc_14001A2BB
0x14001a295  lea     r9, aPdbNull; "pdb null"
0x14001a29c  mov     r8d, 0A43h
0x14001a2a2  lea     rdx, aSdbmergecollec_0; "SdbMergeCollectPreviousMergeInfoFromDb"
0x14001a2a9  lea     ecx, [rsi+1]
0x14001a2ac  call    AslLogCallPrintf
0x14001a2b1  mov     eax, 0C00000EFh
0x14001a2b6  jmp     loc_14001A649
0x14001a2bb  test    r15, r15
0x14001a2be  jnz     short loc_14001A2E7
0x14001a2c0  lea     r9, aPdbmergehistor; "pdbMergeHistoryItemInfo null"
0x14001a2c7  mov     r8d, 0A48h
0x14001a2cd  lea     rdx, aSdbmergecollec_0; "SdbMergeCollectPreviousMergeInfoFromDb"
0x14001a2d4  lea     ecx, [r15+1]
0x14001a2d8  call    AslLogCallPrintf
0x14001a2dd  mov     eax, 0C00000F1h
0x14001a2e2  jmp     loc_14001A649
0x14001a2e7  mov     edi, 50h ; 'P'
0x14001a2ec  xor     edx, edx; Val
0x14001a2ee  mov     r8d, edi; Size
0x14001a2f1  mov     rcx, r15; void *
0x14001a2f4  call    memset_0
0x14001a2f9  mov     r8d, edi; Size
0x14001a2fc  lea     rcx, [rbp+57h+var_90]; void *
0x14001a300  xor     edx, edx; Val
0x14001a302  call    memset_0
0x14001a307  mov     edx, ebx
0x14001a309  mov     rcx, rsi
0x14001a30c  call    SdbGetTagFromTagID
0x14001a311  mov     ecx, 704Dh
0x14001a316  cmp     ax, cx
0x14001a319  jz      short loc_14001A354
0x14001a31b  mov     ecx, 704Eh
0x14001a320  cmp     ax, cx
0x14001a323  jz      short loc_14001A34B
0x14001a325  lea     r9, aTisourcemerged; "tiSourceMergeDb not either TAG_SOURCE_D"...
0x14001a32c  mov     r8d, 0A53h
0x14001a332  lea     rdx, aSdbmergecollec_0; "SdbMergeCollectPreviousMergeInfoFromDb"
0x14001a339  lea     ecx, [rdi-4Fh]
0x14001a33c  call    AslLogCallPrintf
0x14001a341  mov     eax, 0C00000F0h
0x14001a346  jmp     loc_14001A649
0x14001a34b  mov     [rbp+57h+var_44], 1
0x14001a352  jmp     short loc_14001A358
0x14001a354  mov     [rbp+57h+var_44], r13d
0x14001a358  mov     r8d, 700Fh
0x14001a35e  mov     edx, ebx
0x14001a360  mov     rcx, rsi
0x14001a363  call    SdbFindFirstTag
0x14001a368  mov     r14d, eax
0x14001a36b  test    eax, eax
0x14001a36d  jz      loc_14001A61B
0x14001a373  mov     r15d, [rbp+57h+var_AC]
0x14001a377  lea     rbx, aSdbmergecollec_0; "SdbMergeCollectPreviousMergeInfoFromDb"
0x14001a37e  mov     r8d, 6001h
0x14001a384  mov     edx, r14d
0x14001a387  mov     rcx, rsi
0x14001a38a  call    SdbFindFirstTag
0x14001a38f  mov     r8d, 4018h
0x14001a395  mov     edx, r14d
0x14001a398  mov     rcx, rsi
0x14001a39b  mov     edi, eax
0x14001a39d  call    SdbFindFirstTag
0x14001a3a2  mov     r13d, eax
0x14001a3a5  test    edi, edi
0x14001a3a7  jnz     short loc_14001A3BB
0x14001a3a9  lea     r9, aFailedToFindTa_9; "Failed to find TAG_NAME for TAG_DATA en"...
0x14001a3b0  mov     r8d, 0A63h
0x14001a3b6  jmp     loc_14001A5EC
0x14001a3bb  test    r13d, r13d
0x14001a3be  jnz     short loc_14001A3D2
0x14001a3c0  lea     r9, aFailedToFindTa_5; "Failed to find TAG_DATA_VALUETYPE for T"...
0x14001a3c7  mov     r8d, 0A68h
0x14001a3cd  jmp     loc_14001A5EC
0x14001a3d2  mov     edx, edi
0x14001a3d4  mov     rcx, rsi
0x14001a3d7  call    SdbGetStringTagPtr
0x14001a3dc  mov     r12, rax
0x14001a3df  test    rax, rax
0x14001a3e2  jnz     short loc_14001A403
0x14001a3e4  lea     r9, aFailedToReadTa; "Failed to read TAG_NAME string from pdb"
0x14001a3eb  mov     r8d, 0A6Eh
0x14001a3f1  mov     rdx, rbx
0x14001a3f4  mov     ecx, 3
0x14001a3f9  call    AslLogCallPrintf
0x14001a3fe  jmp     loc_14001A5FE
0x14001a403  mov     ecx, 1
0x14001a408  mov     rdi, rcx
0x14001a40b  lea     rdx, qword_140031000
0x14001a412  shl     rdi, 5
0x14001a416  add     rdi, rdx
0x14001a419  mov     rax, [rdi+8]
0x14001a41d  test    rax, rax
0x14001a420  jz      short loc_14001A443
0x14001a422  mov     r9, r12
0x14001a425  sub     r9, rax
0x14001a428  movzx   r8d, word ptr [rax]
0x14001a42c  movzx   edx, word ptr [rax+r9]
0x14001a431  sub     r8d, edx
0x14001a434  jnz     short loc_14001A43E
0x14001a436  add     rax, 2
0x14001a43a  test    edx, edx
0x14001a43c  jnz     short loc_14001A428
0x14001a43e  test    r8d, r8d
0x14001a441  jz      short loc_14001A44E
0x14001a443  xor     edi, edi
0x14001a445  inc     rcx
0x14001a448  cmp     rcx, 9
0x14001a44c  jb      short loc_14001A408
0x14001a44e  xor     r8d, r8d
0x14001a451  mov     edx, r13d
0x14001a454  mov     rcx, rsi
0x14001a457  call    SdbReadDWORDTag
0x14001a45c  test    rdi, rdi
0x14001a45f  jnz     short loc_14001A487
0x14001a461  mov     [rsp+0F0h+var_C8], eax
0x14001a465  lea     r9, aUnexpectedTagD; "Unexpected TAG_DATA entry '%S' of type "...
0x14001a46c  mov     r8d, 0A82h
0x14001a472  mov     [rsp+0F0h+var_D0], r12
0x14001a477  mov     rdx, rbx
0x14001a47a  lea     ecx, [rdi+3]
0x14001a47d  call    AslLogCallPrintf
0x14001a482  jmp     loc_14001A5FE
0x14001a487  mov     ecx, [rdi+18h]
0x14001a48a  cmp     ecx, eax
0x14001a48c  jz      short loc_14001A4BA
0x14001a48e  mov     [rsp+0F0h+var_C0], eax
0x14001a492  lea     r9, aExpectedFieldS; "Expected field '%S' did not have the ex"...
0x14001a499  mov     [rsp+0F0h+var_C8], ecx
0x14001a49d  mov     r8d, 0A8Ah
0x14001a4a3  mov     ecx, 3
0x14001a4a8  mov     [rsp+0F0h+var_D0], r12
0x14001a4ad  mov     rdx, rbx
0x14001a4b0  call    AslLogCallPrintf
0x14001a4b5  jmp     loc_14001A5FE
0x14001a4ba  sub     eax, 1
0x14001a4bd  jz      loc_14001A558
0x14001a4c3  sub     eax, 3
0x14001a4c6  jz      short loc_14001A529
0x14001a4c8  cmp     eax, 7
0x14001a4cb  jnz     loc_14001A5DF
0x14001a4d1  mov     r8d, 5007h
0x14001a4d7  mov     edx, r14d
0x14001a4da  mov     rcx, rsi
0x14001a4dd  call    SdbFindFirstTag
0x14001a4e2  test    eax, eax
0x14001a4e4  jz      loc_14001A5DF
0x14001a4ea  xor     r8d, r8d
0x14001a4ed  mov     edx, eax
0x14001a4ef  mov     rcx, rsi
0x14001a4f2  call    SdbReadQWORDTag
0x14001a4f7  mov     [rbp+57h+Src], rax
0x14001a4fb  lea     rdx, [rbp+57h+Src]; Src
0x14001a4ff  mov     eax, [rdi+10h]
0x14001a502  lea     r9, [rbp+57h+var_90]
0x14001a506  mov     ecx, [rdi+18h]
0x14001a509  add     r9, rax
0x14001a50c  sub     ecx, 1
0x14001a50f  jz      loc_14001A59F
0x14001a515  sub     ecx, 3
0x14001a518  jz      short loc_14001A591
0x14001a51a  cmp     ecx, 7
0x14001a51d  jz      short loc_14001A591
0x14001a51f  mov     eax, 0C0000002h
0x14001a524  jmp     loc_14001A5CC
0x14001a529  mov     r8d, 4019h
0x14001a52f  mov     edx, r14d
0x14001a532  mov     rcx, rsi
0x14001a535  call    SdbFindFirstTag
0x14001a53a  test    eax, eax
0x14001a53c  jz      loc_14001A5DF
0x14001a542  xor     r8d, r8d
0x14001a545  mov     edx, eax
0x14001a547  mov     rcx, rsi
0x14001a54a  call    SdbReadDWORDTag
0x14001a54f  mov     [rbp+57h+var_B0], eax
0x14001a552  lea     rdx, [rbp+57h+var_B0]
0x14001a556  jmp     short loc_14001A4FF
0x14001a558  mov     r8d, 601Eh
0x14001a55e  mov     edx, r14d
0x14001a561  mov     rcx, rsi
0x14001a564  call    SdbFindFirstTag
0x14001a569  test    eax, eax
0x14001a56b  jz      short loc_14001A5DF
0x14001a56d  mov     edx, eax
0x14001a56f  mov     rcx, rsi
0x14001a572  call    SdbGetStringTagPtr
0x14001a577  mov     rdx, rax
0x14001a57a  test    rax, rax
0x14001a57d  jnz     short loc_14001A4FF
0x14001a57f  lea     r9, aFailedToReadSt; "Failed to read string from pdb"
0x14001a586  mov     r8d, 0AACh
0x14001a58c  jmp     loc_14001A3F1
0x14001a591  mov     r8d, [rdi+14h]; Size
0x14001a595  mov     rcx, r9; void *
0x14001a598  call    memcpy_0
0x14001a59d  jmp     short loc_14001A5FE
0x14001a59f  mov     eax, [rdi]
0x14001a5a1  sub     eax, 4
0x14001a5a4  cmp     eax, 1
0x14001a5a7  jbe     short loc_14001A5B3
0x14001a5a9  mov     rcx, r9
0x14001a5ac  call    AslStringDuplicate
0x14001a5b1  jmp     short loc_14001A5C8
0x14001a5b3  cmp     dword ptr [rdi+14h], 10h
0x14001a5b7  jz      short loc_14001A5C0
0x14001a5b9  mov     eax, 0C0000023h
0x14001a5be  jmp     short loc_14001A5CC
0x14001a5c0  mov     rcx, r9; Guid
0x14001a5c3  call    AslGuidFromString
0x14001a5c8  test    eax, eax
0x14001a5ca  jns     short loc_14001A5FE
0x14001a5cc  mov     dword ptr [rsp+0F0h+var_D0], eax
0x14001a5d0  lea     r9, aSdbpmergetagda; "SdbpMergeTagDataToStruct failed [%x]"
0x14001a5d7  mov     r8d, 0AB2h
0x14001a5dd  jmp     short loc_14001A5F1
0x14001a5df  lea     r9, aFailedToFindVa; "Failed to find VALUE tag for TAG_DATA e"...
0x14001a5e6  mov     r8d, 0AA9h
0x14001a5ec  mov     dword ptr [rsp+0F0h+var_D0], r14d
0x14001a5f1  mov     rdx, rbx
0x14001a5f4  mov     ecx, 3
0x14001a5f9  call    AslLogCallPrintf
0x14001a5fe  mov     r8d, r14d
0x14001a601  mov     edx, r15d
0x14001a604  mov     rcx, rsi
0x14001a607  call    SdbFindNextTag
0x14001a60c  mov     r14d, eax
0x14001a60f  test    eax, eax
0x14001a611  jnz     loc_14001A37E
0x14001a617  mov     r15, [rbp+57h+var_A0]
0x14001a61b  movaps  xmm0, [rbp+57h+var_90]
0x14001a61f  xor     eax, eax
0x14001a621  movaps  xmm1, [rbp+57h+var_80]
0x14001a625  movaps  xmmword ptr [r15], xmm0
0x14001a629  movaps  xmm0, [rbp+57h+var_70]
0x14001a62d  movaps  xmmword ptr [r15+10h], xmm1
0x14001a632  movaps  xmm1, [rbp+57h+var_60]
0x14001a636  movaps  xmmword ptr [r15+20h], xmm0
0x14001a63b  movaps  xmm0, xmmword ptr [rbp+7]
0x14001a63f  movaps  xmmword ptr [r15+30h], xmm1
0x14001a644  movaps  xmmword ptr [r15+40h], xmm0
0x14001a649  mov     rcx, [rbp+57h+var_40]
0x14001a64d  xor     rcx, rsp; StackCookie
0x14001a650  call    __security_check_cookie
0x14001a655  mov     rbx, [rsp+0F0h+arg_18]
0x14001a65d  add     rsp, 0C0h
0x14001a664  pop     r15
0x14001a666  pop     r14
0x14001a668  pop     r13
0x14001a66a  pop     r12
0x14001a66c  pop     rdi
0x14001a66d  pop     rsi
0x14001a66e  pop     rbp
0x14001a66f  retn
```
