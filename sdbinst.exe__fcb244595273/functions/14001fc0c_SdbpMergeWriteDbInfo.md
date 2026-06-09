# SdbpMergeWriteDbInfo

- ea: `0x14001fc0c`
- end: `0x140020696`
- name: `SdbpMergeWriteDbInfo`
- size: `2698`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400207cc`

## callees

- `0x14000fb80`
- `0x14001008c`
- `0x140014500`
- `0x140014b64`
- `0x140014d4c`
- `0x140014f94`
- `0x140014fe0`
- `0x14001fc0c`
- `0x14002e420`

## string_xrefs

- `0x14001fcc7`: `Failed to write open DATA tag`
- `0x14001fde9`: `Failed to write open DATA tag`
- `0x14001ff07`: `Failed to write open DATA tag`
- `0x140020007`: `Failed to write open DATA tag`
- `0x140020141`: `Failed to write open DATA tag`
- `0x140020268`: `Failed to write open DATA tag`
- `0x140020377`: `Failed to write open DATA tag`
- `0x140020479`: `Failed to write open DATA tag`
- `0x14002056a`: `Failed to write open DATA tag`
- `0x14001fd09`: `SdbpMergeWriteDataHelper`
- `0x14001fd95`: `SdbpMergeWriteDataHelper`
- `0x14001fe2b`: `SdbpMergeWriteDataHelper`
- `0x14001febe`: `SdbpMergeWriteDataHelper`
- `0x14001ff3d`: `SdbpMergeWriteDataHelper`
- `0x14001ffc6`: `SdbpMergeWriteDataHelper`
- `0x14002003d`: `SdbpMergeWriteDataHelper`
- `0x1400200c4`: `SdbpMergeWriteDataHelper`
- `0x140020179`: `SdbpMergeWriteDataHelper`
- `0x1400201fa`: `SdbpMergeWriteDataHelper`
- `0x1400202a0`: `SdbpMergeWriteDataHelper`
- `0x140020328`: `SdbpMergeWriteDataHelper`
- `0x1400203af`: `SdbpMergeWriteDataHelper`
- `0x140020430`: `SdbpMergeWriteDataHelper`
- `0x1400204b1`: `SdbpMergeWriteDataHelper`
- `0x14002052f`: `SdbpMergeWriteDataHelper`
- `0x1400205a2`: `SdbpMergeWriteDataHelper`
- `0x140020623`: `SdbpMergeWriteDataHelper`
- `0x14001fd3d`: `Failed to write DATA VALUETYPE value 0x%08X`
- `0x14001fe5f`: `Failed to write DATA VALUETYPE value 0x%08X`
- `0x14001ff6f`: `Failed to write DATA VALUETYPE value 0x%08X`
- `0x14002006d`: `Failed to write DATA VALUETYPE value 0x%08X`
- `0x1400201a1`: `Failed to write DATA VALUETYPE value 0x%08X`
- `0x1400202cf`: `Failed to write DATA VALUETYPE value 0x%08X`
- `0x1400203da`: `Failed to write DATA VALUETYPE value 0x%08X`
- `0x1400204d9`: `Failed to write DATA VALUETYPE value 0x%08X`
- `0x1400205cd`: `Failed to write DATA VALUETYPE value 0x%08X`
- `0x14001fcf9`: `Failed to write DATA NAME value "%S"`
- `0x14001fe1b`: `Failed to write DATA NAME value "%S"`
- `0x14001ff30`: `Failed to write DATA NAME value "%S"`
- `0x140020030`: `Failed to write DATA NAME value "%S"`
- `0x14002016c`: `Failed to write DATA NAME value "%S"`
- `0x140020293`: `Failed to write DATA NAME value "%S"`
- `0x1400203a2`: `Failed to write DATA NAME value "%S"`
- `0x1400204a4`: `Failed to write DATA NAME value "%S"`
- `0x140020595`: `Failed to write DATA NAME value "%S"`
- `0x140020402`: `Failed to write DATA DWORD value 0x%08X`
- `0x1400205f5`: `Failed to write DATA DWORD value 0x%08X`
- `0x14001fd65`: `Failed to write DATA STRING value "%S"`
- `0x14001fe98`: `Failed to write DATA STRING value "%S"`
- `0x1400201d6`: `Failed to write DATA STRING value "%S"`
- `0x140020304`: `Failed to write DATA STRING value "%S"`
- `0x140020501`: `Failed to write DATA STRING value "%S"`
- `0x14001ff97`: `Failed to write DATA QWORD value 0x%016llX`
- `0x140020095`: `Failed to write DATA QWORD value 0x%016llX`
- `0x140020643`: `PDB null or not writeable`
- `0x14001fd88`: `Failed to write end of DATA tag`
- `0x14001feb1`: `Failed to write end of DATA tag`
- `0x14001ffb9`: `Failed to write end of DATA tag`
- `0x1400200b7`: `Failed to write end of DATA tag`
- `0x1400201ed`: `Failed to write end of DATA tag`
- `0x14002031b`: `Failed to write end of DATA tag`
- `0x140020423`: `Failed to write end of DATA tag`
- `0x140020522`: `Failed to write end of DATA tag`
- `0x140020616`: `Failed to write end of DATA tag`
- `0x14001fc74`: `SdbpMergeWriteDbInfo`
- `0x14001fdb7`: `SdbpMergeWriteDbInfo`
- `0x140020650`: `SdbpMergeWriteDbInfo`
- `0x14001fdae`: `SdbpMergeWriteDataHelper failed to add DATA [%x]`

## pseudocode

```c
__int64 __fastcall SdbpMergeWriteDbInfo(__int64 a1, __int64 a2, int a3)
{
  _WORD *v7; // rsi
  unsigned int v8; // ebp
  __int64 v9; // r8
  int v10; // eax
  const char *v11; // r9
  unsigned int v12; // esi
  unsigned int v13; // esi
  unsigned int v14; // ebp
  unsigned int v15; // ebp
  unsigned __int64 v16; // xmm0_8
  unsigned int v17; // ebp
  unsigned int v18; // ebp
  unsigned int v19; // ebp
  _WORD *v20; // rsi
  unsigned int v21; // r15d
  unsigned int v22; // ebp
  __int64 v23; // [rsp+20h] [rbp-C8h]
  _BYTE v25[80]; // [rsp+40h] [rbp-A8h] BYREF

  if ( a1 && *(_DWORD *)(a1 + 16) )
  {
    if ( !a2 )
    {
      AslLogCallPrintf(1, "SdbpMergeWriteDbInfo", 2474, "SDB info was null");
      return 3221225712LL;
    }
    if ( !a3 )
    {
      v7 = *(_WORD **)a2;
      if ( *(_QWORD *)a2 )
      {
        if ( *v7 )
        {
          v8 = SdbBeginWriteListTag(a1, 28687);
          if ( !v8 )
          {
            AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2405, "Failed to write open DATA tag");
LABEL_18:
            v9 = 2481;
LABEL_19:
            v10 = -1073741595;
            v11 = "SdbpMergeWriteDataHelper failed to add DATA [%x]";
            v12 = -1073741595;
LABEL_20:
            LODWORD(v23) = v10;
            AslLogCallPrintf(1, "SdbpMergeWriteDbInfo", v9, v11, v23);
            return v12;
          }
          if ( !(unsigned int)SdbWriteStringTag(a1, 24577, L"FilePath") )
          {
            AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2410, "Failed to write DATA NAME value \"%S\"", L"FilePath");
            goto LABEL_18;
          }
          if ( !(unsigned int)SdbWriteDWORDTag(a1, 16408, 1) )
          {
            AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2415, "Failed to write DATA VALUETYPE value 0x%08X", 1);
            goto LABEL_18;
          }
          if ( !(unsigned int)SdbWriteStringTag(a1, 24606, v7) )
          {
            AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2422, "Failed to write DATA STRING value \"%S\"", v7);
            goto LABEL_18;
          }
          if ( !(unsigned int)SdbEndWriteListTag(a1, v8) )
          {
            AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2448, "Failed to write end of DATA tag");
            goto LABEL_18;
          }
LABEL_33:
          if ( *(_DWORD *)(a2 + 12) || *(_DWORD *)(a2 + 8) )
          {
            v14 = SdbBeginWriteListTag(a1, 28687);
            if ( !v14 )
            {
              AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2405, "Failed to write open DATA tag");
LABEL_45:
              v9 = 2498;
              goto LABEL_19;
            }
            if ( !(unsigned int)SdbWriteStringTag(a1, 24577, L"FileTime") )
            {
              AslLogCallPrintf(
                1,
                "SdbpMergeWriteDataHelper",
                2410,
                "Failed to write DATA NAME value \"%S\"",
                L"FileTime");
              goto LABEL_45;
            }
            if ( !(unsigned int)SdbWriteDWORDTag(a1, 16408, 11) )
            {
              AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2415, "Failed to write DATA VALUETYPE value 0x%08X", 11);
              goto LABEL_45;
            }
            if ( !(unsigned int)SdbWriteQWORDTag(a1, 20487, *(_QWORD *)(a2 + 8)) )
            {
              AslLogCallPrintf(
                1,
                "SdbpMergeWriteDataHelper",
                2436,
                "Failed to write DATA QWORD value 0x%016llX",
                *(_QWORD *)(a2 + 8));
              goto LABEL_45;
            }
            if ( !(unsigned int)SdbEndWriteListTag(a1, v14) )
            {
              AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2448, "Failed to write end of DATA tag");
              goto LABEL_45;
            }
          }
LABEL_46:
          if ( *(_DWORD *)(a2 + 20) || *(_DWORD *)(a2 + 16) )
          {
            v15 = SdbBeginWriteListTag(a1, 28687);
            if ( !v15 )
            {
              AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2405, "Failed to write open DATA tag");
LABEL_58:
              v9 = 2506;
              goto LABEL_19;
            }
            if ( !(unsigned int)SdbWriteStringTag(a1, 24577, L"SdbTime") )
            {
              AslLogCallPrintf(
                1,
                "SdbpMergeWriteDataHelper",
                2410,
                "Failed to write DATA NAME value \"%S\"",
                L"SdbTime");
              goto LABEL_58;
            }
            if ( !(unsigned int)SdbWriteDWORDTag(a1, 16408, 11) )
            {
              AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2415, "Failed to write DATA VALUETYPE value 0x%08X", 11);
              goto LABEL_58;
            }
            if ( !(unsigned int)SdbWriteQWORDTag(a1, 20487, *(_QWORD *)(a2 + 16)) )
            {
              AslLogCallPrintf(
                1,
                "SdbpMergeWriteDataHelper",
                2436,
                "Failed to write DATA QWORD value 0x%016llX",
                *(_QWORD *)(a2 + 16));
              goto LABEL_58;
            }
            if ( !(unsigned int)SdbEndWriteListTag(a1, v15) )
            {
              AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2448, "Failed to write end of DATA tag");
              goto LABEL_58;
            }
          }
          v16 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
          if ( *(_QWORD *)(a2 + 24) || *(_QWORD *)(a2 + 32) != v16 )
          {
            v10 = AslGuidToString(v25, 39, a2 + 24);
            v12 = v10;
            if ( v10 < 0 )
            {
              v11 = "AslGuidToString failed to convert guid to string [%x]";
              v9 = 2515;
              goto LABEL_20;
            }
            v17 = SdbBeginWriteListTag(a1, 28687);
            if ( !v17 )
            {
              AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2405, "Failed to write open DATA tag");
LABEL_73:
              v9 = 2521;
              goto LABEL_19;
            }
            if ( !(unsigned int)SdbWriteStringTag(a1, 24577, L"DatabaseId") )
            {
              AslLogCallPrintf(
                1,
                "SdbpMergeWriteDataHelper",
                2410,
                "Failed to write DATA NAME value \"%S\"",
                L"DatabaseId");
              goto LABEL_73;
            }
            if ( !(unsigned int)SdbWriteDWORDTag(a1, 16408, 1) )
            {
              AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2415, "Failed to write DATA VALUETYPE value 0x%08X", 1);
              goto LABEL_73;
            }
            if ( !(unsigned int)SdbWriteStringTag(a1, 24606, v25) )
            {
              AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2422, "Failed to write DATA STRING value \"%S\"", v25);
              goto LABEL_73;
            }
            if ( !(unsigned int)SdbEndWriteListTag(a1, v17) )
            {
              AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2448, "Failed to write end of DATA tag");
              goto LABEL_73;
            }
          }
          if ( *(_QWORD *)(a2 + 40) || *(_QWORD *)(a2 + 48) != v16 )
          {
            v10 = AslGuidToString(v25, 39, a2 + 40);
            v12 = v10;
            if ( v10 < 0 )
            {
              v11 = "AslGuidToString failed to convert guid to string [%x]";
              v9 = 2530;
              goto LABEL_20;
            }
            v18 = SdbBeginWriteListTag(a1, 28687);
            if ( !v18 )
            {
              AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2405, "Failed to write open DATA tag");
LABEL_88:
              v9 = 2536;
              goto LABEL_19;
            }
            if ( !(unsigned int)SdbWriteStringTag(a1, 24577, L"TargetDatabaseId") )
            {
              AslLogCallPrintf(
                1,
                "SdbpMergeWriteDataHelper",
                2410,
                "Failed to write DATA NAME value \"%S\"",
                L"TargetDatabaseId");
              goto LABEL_88;
            }
            if ( !(unsigned int)SdbWriteDWORDTag(a1, 16408, 1) )
            {
              AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2415, "Failed to write DATA VALUETYPE value 0x%08X", 1);
              goto LABEL_88;
            }
            if ( !(unsigned int)SdbWriteStringTag(a1, 24606, v25) )
            {
              AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2422, "Failed to write DATA STRING value \"%S\"", v25);
              goto LABEL_88;
            }
            if ( !(unsigned int)SdbEndWriteListTag(a1, v18) )
            {
              AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2448, "Failed to write end of DATA tag");
              goto LABEL_88;
            }
          }
          if ( !a3 && *(_DWORD *)(a2 + 56) )
          {
            v19 = SdbBeginWriteListTag(a1, 28687);
            if ( !v19 )
            {
              AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2405, "Failed to write open DATA tag");
LABEL_101:
              v9 = 2544;
              goto LABEL_19;
            }
            if ( !(unsigned int)SdbWriteStringTag(a1, 24577, L"CrcChecksum") )
            {
              AslLogCallPrintf(
                1,
                "SdbpMergeWriteDataHelper",
                2410,
                "Failed to write DATA NAME value \"%S\"",
                L"CrcChecksum");
              goto LABEL_101;
            }
            if ( !(unsigned int)SdbWriteDWORDTag(a1, 16408, 4) )
            {
              AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2415, "Failed to write DATA VALUETYPE value 0x%08X", 4);
              goto LABEL_101;
            }
            if ( !(unsigned int)SdbWriteDWORDTag(a1, 16409, *(unsigned int *)(a2 + 56)) )
            {
              AslLogCallPrintf(
                1,
                "SdbpMergeWriteDataHelper",
                2429,
                "Failed to write DATA DWORD value 0x%08X",
                *(_DWORD *)(a2 + 56));
              goto LABEL_101;
            }
            if ( !(unsigned int)SdbEndWriteListTag(a1, v19) )
            {
              AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2448, "Failed to write end of DATA tag");
              goto LABEL_101;
            }
          }
          v20 = *(_WORD **)(a2 + 64);
          if ( v20 && *v20 )
          {
            v21 = SdbBeginWriteListTag(a1, 28687);
            if ( !v21 )
            {
              AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2405, "Failed to write open DATA tag");
LABEL_114:
              v9 = 2552;
              goto LABEL_19;
            }
            if ( !(unsigned int)SdbWriteStringTag(a1, 24577, L"CompilerVersion") )
            {
              AslLogCallPrintf(
                1,
                "SdbpMergeWriteDataHelper",
                2410,
                "Failed to write DATA NAME value \"%S\"",
                L"CompilerVersion");
              goto LABEL_114;
            }
            if ( !(unsigned int)SdbWriteDWORDTag(a1, 16408, 1) )
            {
              AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2415, "Failed to write DATA VALUETYPE value 0x%08X", 1);
              goto LABEL_114;
            }
            if ( !(unsigned int)SdbWriteStringTag(a1, 24606, v20) )
            {
              AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2422, "Failed to write DATA STRING value \"%S\"", v20);
              goto LABEL_114;
            }
            if ( !(unsigned int)SdbEndWriteListTag(a1, v21) )
            {
              AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2448, "Failed to write end of DATA tag");
              goto LABEL_114;
            }
          }
          if ( *(_DWORD *)(a2 + 72) )
          {
            v22 = SdbBeginWriteListTag(a1, 28687);
            if ( !v22 )
            {
              AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2405, "Failed to write open DATA tag");
LABEL_126:
              v9 = 2560;
              goto LABEL_19;
            }
            if ( !(unsigned int)SdbWriteStringTag(a1, 24577, L"RuntimePlatform") )
            {
              AslLogCallPrintf(
                1,
                "SdbpMergeWriteDataHelper",
                2410,
                "Failed to write DATA NAME value \"%S\"",
                L"RuntimePlatform");
              goto LABEL_126;
            }
            if ( !(unsigned int)SdbWriteDWORDTag(a1, 16408, 4) )
            {
              AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2415, "Failed to write DATA VALUETYPE value 0x%08X", 4);
              goto LABEL_126;
            }
            if ( !(unsigned int)SdbWriteDWORDTag(a1, 16409, *(unsigned int *)(a2 + 72)) )
            {
              AslLogCallPrintf(
                1,
                "SdbpMergeWriteDataHelper",
                2429,
                "Failed to write DATA DWORD value 0x%08X",
                *(_DWORD *)(a2 + 72));
              goto LABEL_126;
            }
            if ( !(unsigned int)SdbEndWriteListTag(a1, v22) )
            {
              AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2448, "Failed to write end of DATA tag");
              goto LABEL_126;
            }
          }
          return 0;
        }
      }
    }
    v13 = SdbBeginWriteListTag(a1, 28687);
    if ( v13 )
    {
      if ( (unsigned int)SdbWriteStringTag(a1, 24577, L"FilePath") )
      {
        if ( (unsigned int)SdbWriteDWORDTag(a1, 16408, 1) )
        {
          if ( (unsigned int)SdbWriteStringTag(a1, 24606, &Format) )
          {
            if ( (unsigned int)SdbEndWriteListTag(a1, v13) )
            {
              if ( a3 )
                goto LABEL_46;
              goto LABEL_33;
            }
            AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2448, "Failed to write end of DATA tag");
          }
          else
          {
            AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2422, "Failed to write DATA STRING value \"%S\"", &Format);
          }
        }
        else
        {
          AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2415, "Failed to write DATA VALUETYPE value 0x%08X", 1);
        }
      }
      else
      {
        AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2410, "Failed to write DATA NAME value \"%S\"", L"FilePath");
      }
    }
    else
    {
      AslLogCallPrintf(1, "SdbpMergeWriteDataHelper", 2405, "Failed to write open DATA tag");
    }
    v9 = 2490;
    goto LABEL_19;
  }
  AslLogCallPrintf(1, "SdbpMergeWriteDbInfo", 2470, "PDB null or not writeable");
  return 3221225711LL;
}

```

## disassembly

```asm
0x14001fc0c  mov     rax, rsp
0x14001fc0f  mov     [rax+18h], rbx
0x14001fc13  push    rbp
0x14001fc14  push    rsi
0x14001fc15  push    rdi
0x14001fc16  push    r12
0x14001fc18  push    r13
0x14001fc1a  push    r14
0x14001fc1c  push    r15
0x14001fc1e  sub     rsp, 0B0h
0x14001fc25  movaps  xmmword ptr [rax-48h], xmm6
0x14001fc29  mov     rax, cs:__security_cookie
0x14001fc30  xor     rax, rsp
0x14001fc33  mov     [rsp+0E8h+var_58], rax
0x14001fc3b  xor     r15d, r15d
0x14001fc3e  mov     [rsp+0E8h+var_B8], r8d
0x14001fc43  mov     ebp, r8d
0x14001fc46  mov     r14, rdx
0x14001fc49  mov     rdi, rcx
0x14001fc4c  xorps   xmm6, xmm6
0x14001fc4f  test    rcx, rcx
0x14001fc52  jz      loc_140020643
0x14001fc58  cmp     [rcx+10h], r15d
0x14001fc5c  jz      loc_140020643
0x14001fc62  test    rdx, rdx
0x14001fc65  jnz     short loc_14001FC8E
0x14001fc67  lea     r9, aSdbInfoWasNull; "SDB info was null"
0x14001fc6e  mov     r8d, 9AAh
0x14001fc74  lea     rdx, aSdbpmergewrite_1; "SdbpMergeWriteDbInfo"
0x14001fc7b  lea     ecx, [r14+1]
0x14001fc7f  call    AslLogCallPrintf
0x14001fc84  mov     eax, 0C00000F0h
0x14001fc89  jmp     loc_140020666
0x14001fc8e  test    ebp, ebp
0x14001fc90  jnz     loc_14001FDCE
0x14001fc96  mov     rsi, [rdx]
0x14001fc99  test    rsi, rsi
0x14001fc9c  jz      loc_14001FDCE
0x14001fca2  cmp     [rsi], r15w
0x14001fca6  jz      loc_14001FDCE
0x14001fcac  mov     rbx, cs:off_140031028; "FilePath"
0x14001fcb3  mov     r13d, 700Fh
0x14001fcb9  mov     edx, r13d
0x14001fcbc  call    SdbBeginWriteListTag
0x14001fcc1  mov     ebp, eax
0x14001fcc3  test    eax, eax
0x14001fcc5  jnz     short loc_14001FCDC
0x14001fcc7  lea     r9, aFailedToWriteO_1; "Failed to write open DATA tag"
0x14001fcce  mov     r8d, 965h
0x14001fcd4  lea     ebx, [rax+1]
0x14001fcd7  jmp     loc_14001FD95
0x14001fcdc  mov     r12d, 6001h
0x14001fce2  mov     r8, rbx
0x14001fce5  mov     edx, r12d
0x14001fce8  mov     rcx, rdi
0x14001fceb  call    SdbWriteStringTag
0x14001fcf0  test    eax, eax
0x14001fcf2  jnz     short loc_14001FD1C
0x14001fcf4  mov     [rsp+0E8h+var_C8], rbx
0x14001fcf9  lea     r9, aFailedToWriteD_0; "Failed to write DATA NAME value \"%S\""
0x14001fd00  lea     ebx, [rax+1]
0x14001fd03  mov     r8d, 96Ah
0x14001fd09  lea     rdx, aSdbpmergewrite; "SdbpMergeWriteDataHelper"
0x14001fd10  mov     ecx, ebx
0x14001fd12  call    AslLogCallPrintf
0x14001fd17  jmp     loc_14001FDA3
0x14001fd1c  mov     r15d, 4018h
0x14001fd22  mov     ebx, 1
0x14001fd27  mov     edx, r15d
0x14001fd2a  mov     r8d, ebx
0x14001fd2d  mov     rcx, rdi
0x14001fd30  call    SdbWriteDWORDTag
0x14001fd35  test    eax, eax
0x14001fd37  jnz     short loc_14001FD4C
0x14001fd39  mov     dword ptr [rsp+0E8h+var_C8], ebx
0x14001fd3d  lea     r9, aFailedToWriteD; "Failed to write DATA VALUETYPE value 0x"...
0x14001fd44  mov     r8d, 96Fh
0x14001fd4a  jmp     short loc_14001FD09
0x14001fd4c  mov     edx, 601Eh
0x14001fd51  mov     r8, rsi
0x14001fd54  mov     rcx, rdi
0x14001fd57  call    SdbWriteStringTag
0x14001fd5c  test    eax, eax
0x14001fd5e  jnz     short loc_14001FD74
0x14001fd60  mov     [rsp+0E8h+var_C8], rsi
0x14001fd65  lea     r9, aFailedToWriteD_2; "Failed to write DATA STRING value \"%S"...
0x14001fd6c  mov     r8d, 976h
0x14001fd72  jmp     short loc_14001FD09
0x14001fd74  mov     edx, ebp
0x14001fd76  mov     rcx, rdi
0x14001fd79  call    SdbEndWriteListTag
0x14001fd7e  xor     esi, esi
0x14001fd80  test    eax, eax
0x14001fd82  jnz     loc_14001FEDF
0x14001fd88  lea     r9, aFailedToWriteE_1; "Failed to write end of DATA tag"
0x14001fd8f  mov     r8d, 990h
0x14001fd95  lea     rdx, aSdbpmergewrite; "SdbpMergeWriteDataHelper"
0x14001fd9c  mov     ecx, ebx
0x14001fd9e  call    AslLogCallPrintf
0x14001fda3  mov     r8d, 9B1h
0x14001fda9  mov     eax, 0C00000E5h
0x14001fdae  lea     r9, aSdbpmergewrite_5; "SdbpMergeWriteDataHelper failed to add "...
0x14001fdb5  mov     esi, eax
0x14001fdb7  lea     rdx, aSdbpmergewrite_1; "SdbpMergeWriteDbInfo"
0x14001fdbe  mov     dword ptr [rsp+0E8h+var_C8], eax
0x14001fdc2  mov     ecx, ebx
0x14001fdc4  call    AslLogCallPrintf
0x14001fdc9  jmp     loc_14002063F
0x14001fdce  mov     rbx, cs:off_140031028; "FilePath"
0x14001fdd5  mov     r13d, 700Fh
0x14001fddb  mov     edx, r13d
0x14001fdde  call    SdbBeginWriteListTag
0x14001fde3  mov     esi, eax
0x14001fde5  test    eax, eax
0x14001fde7  jnz     short loc_14001FDFE
0x14001fde9  lea     r9, aFailedToWriteO_1; "Failed to write open DATA tag"
0x14001fdf0  mov     r8d, 965h
0x14001fdf6  lea     ebx, [rax+1]
0x14001fdf9  jmp     loc_14001FEBE
0x14001fdfe  mov     r12d, 6001h
0x14001fe04  mov     r8, rbx
0x14001fe07  mov     edx, r12d
0x14001fe0a  mov     rcx, rdi
0x14001fe0d  call    SdbWriteStringTag
0x14001fe12  test    eax, eax
0x14001fe14  jnz     short loc_14001FE3E
0x14001fe16  mov     [rsp+0E8h+var_C8], rbx
0x14001fe1b  lea     r9, aFailedToWriteD_0; "Failed to write DATA NAME value \"%S\""
0x14001fe22  lea     ebx, [rax+1]
0x14001fe25  mov     r8d, 96Ah
0x14001fe2b  lea     rdx, aSdbpmergewrite; "SdbpMergeWriteDataHelper"
0x14001fe32  mov     ecx, ebx
0x14001fe34  call    AslLogCallPrintf
0x14001fe39  jmp     loc_14001FECC
0x14001fe3e  mov     r15d, 4018h
0x14001fe44  mov     ebx, 1
0x14001fe49  mov     edx, r15d
0x14001fe4c  mov     r8d, ebx
0x14001fe4f  mov     rcx, rdi
0x14001fe52  call    SdbWriteDWORDTag
0x14001fe57  test    eax, eax
0x14001fe59  jnz     short loc_14001FE6E
0x14001fe5b  mov     dword ptr [rsp+0E8h+var_C8], ebx
0x14001fe5f  lea     r9, aFailedToWriteD; "Failed to write DATA VALUETYPE value 0x"...
0x14001fe66  mov     r8d, 96Fh
0x14001fe6c  jmp     short loc_14001FE2B
0x14001fe6e  mov     edx, 601Eh
0x14001fe73  lea     r8, Format
0x14001fe7a  mov     rcx, rdi
0x14001fe7d  call    SdbWriteStringTag
0x14001fe82  test    eax, eax
0x14001fe84  jnz     short loc_14001FEA1
0x14001fe86  lea     rax, Format
0x14001fe8d  mov     r8d, 976h
0x14001fe93  mov     [rsp+0E8h+var_C8], rax
0x14001fe98  lea     r9, aFailedToWriteD_2; "Failed to write DATA STRING value \"%S"...
0x14001fe9f  jmp     short loc_14001FE2B
0x14001fea1  mov     edx, esi
0x14001fea3  mov     rcx, rdi
0x14001fea6  call    SdbEndWriteListTag
0x14001feab  xor     esi, esi
0x14001fead  test    eax, eax
0x14001feaf  jnz     short loc_14001FED7
0x14001feb1  lea     r9, aFailedToWriteE_1; "Failed to write end of DATA tag"
0x14001feb8  mov     r8d, 990h
0x14001febe  lea     rdx, aSdbpmergewrite; "SdbpMergeWriteDataHelper"
0x14001fec5  mov     ecx, ebx
0x14001fec7  call    AslLogCallPrintf
0x14001fecc  mov     r8d, 9BAh
0x14001fed2  jmp     loc_14001FDA9
0x14001fed7  test    ebp, ebp
0x14001fed9  jnz     loc_14001FFDF
0x14001fedf  cmp     [r14+0Ch], esi
0x14001fee3  jnz     short loc_14001FEEF
0x14001fee5  cmp     [r14+8], esi
0x14001fee9  jz      loc_14001FFDF
0x14001feef  mov     rsi, cs:off_140031048; "FileTime"
0x14001fef6  mov     edx, r13d
0x14001fef9  mov     rcx, rdi
0x14001fefc  call    SdbBeginWriteListTag
0x14001ff01  mov     ebp, eax
0x14001ff03  test    eax, eax
0x14001ff05  jnz     short loc_14001FF19
0x14001ff07  lea     r9, aFailedToWriteO_1; "Failed to write open DATA tag"
0x14001ff0e  mov     r8d, 965h
0x14001ff14  jmp     loc_14001FFC6
0x14001ff19  mov     edx, r12d
0x14001ff1c  mov     r8, rsi
0x14001ff1f  mov     rcx, rdi
0x14001ff22  call    SdbWriteStringTag
0x14001ff27  test    eax, eax
0x14001ff29  jnz     short loc_14001FF50
0x14001ff2b  mov     [rsp+0E8h+var_C8], rsi
0x14001ff30  lea     r9, aFailedToWriteD_0; "Failed to write DATA NAME value \"%S\""
0x14001ff37  mov     r8d, 96Ah
0x14001ff3d  lea     rdx, aSdbpmergewrite; "SdbpMergeWriteDataHelper"
0x14001ff44  mov     ecx, ebx
0x14001ff46  call    AslLogCallPrintf
0x14001ff4b  jmp     loc_14001FFD4
0x14001ff50  mov     edx, r15d
0x14001ff53  mov     r8d, 0Bh
0x14001ff59  mov     rcx, rdi
0x14001ff5c  call    SdbWriteDWORDTag
0x14001ff61  xor     esi, esi
0x14001ff63  test    eax, eax
0x14001ff65  jnz     short loc_14001FF7E
0x14001ff67  mov     dword ptr [rsp+0E8h+var_C8], 0Bh
0x14001ff6f  lea     r9, aFailedToWriteD; "Failed to write DATA VALUETYPE value 0x"...
0x14001ff76  mov     r8d, 96Fh
0x14001ff7c  jmp     short loc_14001FF3D
0x14001ff7e  mov     r8, [r14+8]
0x14001ff82  mov     edx, 5007h
0x14001ff87  mov     rcx, rdi
0x14001ff8a  call    SdbWriteQWORDTag
0x14001ff8f  test    eax, eax
0x14001ff91  jnz     short loc_14001FFAB
0x14001ff93  mov     rax, [r14+8]
0x14001ff97  lea     r9, aFailedToWriteD_4; "Failed to write DATA QWORD value 0x%016"...
0x14001ff9e  mov     [rsp+0E8h+var_C8], rax
0x14001ffa3  mov     r8d, 984h
0x14001ffa9  jmp     short loc_14001FF3D
0x14001ffab  mov     edx, ebp
0x14001ffad  mov     rcx, rdi
0x14001ffb0  call    SdbEndWriteListTag
0x14001ffb5  test    eax, eax
0x14001ffb7  jnz     short loc_14001FFDF
0x14001ffb9  lea     r9, aFailedToWriteE_1; "Failed to write end of DATA tag"
0x14001ffc0  mov     r8d, 990h
0x14001ffc6  lea     rdx, aSdbpmergewrite; "SdbpMergeWriteDataHelper"
0x14001ffcd  mov     ecx, ebx
0x14001ffcf  call    AslLogCallPrintf
0x14001ffd4  mov     r8d, 9C2h
0x14001ffda  jmp     loc_14001FDA9
0x14001ffdf  cmp     [r14+14h], esi
0x14001ffe3  jnz     short loc_14001FFEF
0x14001ffe5  cmp     [r14+10h], esi
0x14001ffe9  jz      loc_1400200DD
0x14001ffef  mov     rsi, cs:off_140031068; "SdbTime"
0x14001fff6  mov     edx, r13d
0x14001fff9  mov     rcx, rdi
0x14001fffc  call    SdbBeginWriteListTag
0x140020001  mov     ebp, eax
0x140020003  test    eax, eax
0x140020005  jnz     short loc_140020019
0x140020007  lea     r9, aFailedToWriteO_1; "Failed to write open DATA tag"
0x14002000e  mov     r8d, 965h
0x140020014  jmp     loc_1400200C4
0x140020019  mov     edx, r12d
0x14002001c  mov     r8, rsi
0x14002001f  mov     rcx, rdi
0x140020022  call    SdbWriteStringTag
0x140020027  test    eax, eax
0x140020029  jnz     short loc_140020050
0x14002002b  mov     [rsp+0E8h+var_C8], rsi
0x140020030  lea     r9, aFailedToWriteD_0; "Failed to write DATA NAME value \"%S\""
0x140020037  mov     r8d, 96Ah
0x14002003d  lea     rdx, aSdbpmergewrite; "SdbpMergeWriteDataHelper"
0x140020044  mov     ecx, ebx
0x140020046  call    AslLogCallPrintf
0x14002004b  jmp     loc_1400200D2
0x140020050  mov     edx, r15d
0x140020053  mov     rcx, rdi
0x140020056  mov     r15d, 0Bh
0x14002005c  mov     r8d, r15d
0x14002005f  call    SdbWriteDWORDTag
0x140020064  test    eax, eax
0x140020066  jnz     short loc_14002007C
0x140020068  mov     dword ptr [rsp+0E8h+var_C8], r15d
0x14002006d  lea     r9, aFailedToWriteD; "Failed to write DATA VALUETYPE value 0x"...
0x140020074  mov     r8d, 96Fh
0x14002007a  jmp     short loc_14002003D
0x14002007c  mov     r8, [r14+10h]
0x140020080  mov     edx, 5007h
0x140020085  mov     rcx, rdi
0x140020088  call    SdbWriteQWORDTag
0x14002008d  test    eax, eax
0x14002008f  jnz     short loc_1400200A9
0x140020091  mov     rax, [r14+10h]
0x140020095  lea     r9, aFailedToWriteD_4; "Failed to write DATA QWORD value 0x%016"...
0x14002009c  mov     [rsp+0E8h+var_C8], rax
0x1400200a1  mov     r8d, 984h
0x1400200a7  jmp     short loc_14002003D
0x1400200a9  mov     edx, ebp
0x1400200ab  mov     rcx, rdi
0x1400200ae  call    SdbEndWriteListTag
0x1400200b3  test    eax, eax
0x1400200b5  jnz     short loc_1400200DD
0x1400200b7  lea     r9, aFailedToWriteE_1; "Failed to write end of DATA tag"
0x1400200be  mov     r8d, 990h
0x1400200c4  lea     rdx, aSdbpmergewrite; "SdbpMergeWriteDataHelper"
0x1400200cb  mov     ecx, ebx
0x1400200cd  call    AslLogCallPrintf
0x1400200d2  mov     r8d, 9CAh
0x1400200d8  jmp     loc_14001FDA9
0x1400200dd  xorps   xmm0, xmm0
0x1400200e0  lea     r8, [r14+18h]
0x1400200e4  movq    r12, xmm6
0x1400200e9  psrldq  xmm0, 8
0x1400200ee  movq    r15, xmm0
0x1400200f3  cmp     [r8], r12
  ... truncated ...
```
