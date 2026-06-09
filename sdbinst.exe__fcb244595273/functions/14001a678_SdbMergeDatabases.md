# SdbMergeDatabases

- ea: `0x14001a678`
- end: `0x14001a82c`
- name: `SdbMergeDatabases`
- size: `436`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140024958`

## callees

- `0x14001008c`
- `0x140014574`
- `0x140014d98`
- `0x140016198`
- `0x140018e34`
- `0x14001a678`
- `0x14001d808`

## string_xrefs

- `0x14001a6aa`: `Failed to open original SDB`
- `0x14001a6e3`: `Failed to open merge SDB`
- `0x14001a78b`: `Compressing result database as original was.`
- `0x14001a76c`: `SdbWriteDatabaseToFile failed to write the database to disk [%x]`
- `0x14001a7e7`: `SdbWriteDatabaseToFile failed to write the database to disk [%x]`
- `0x14001a7b8`: `SdbpCompressExistingDatabase failed to compress the resulting database. Writing out uncompressed.`

## pseudocode

```c
__int64 __fastcall SdbMergeDatabases(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v7; // rdx
  __int64 v8; // rsi
  unsigned int v9; // ebx
  _BYTE **v10; // rdi
  int v11; // eax
  const char *v12; // r9
  __int64 v13; // r8
  __int64 v15; // [rsp+20h] [rbp-48h]
  _BYTE **v16; // [rsp+30h] [rbp-38h] BYREF

  v16 = 0;
  v8 = SdbOpenDatabaseEx(a1, a2, 16);
  if ( !v8 )
  {
    v9 = -1073741514;
    AslLogCallPrintf(1, "SdbMergeDatabases", 5691, "Failed to open original SDB");
    goto LABEL_18;
  }
  v10 = (_BYTE **)SdbOpenDatabaseEx(a2, v7, 16);
  if ( !v10 )
  {
    v9 = -1073741514;
    AslLogCallPrintf(1, "SdbMergeDatabases", 5698, "Failed to open merge SDB");
    goto LABEL_16;
  }
  v11 = SdbpMergeOrDiffDatabasesInMemoryImpl(v8, (_DWORD)v10, 0, a4, 0, (__int64)&v16);
  v9 = v11;
  if ( v11 < 0 )
  {
    v12 = "SdbpMergeOrDiffDatabasesInMemoryImpl failed to merge SDB files [%x]";
    v13 = 5709;
LABEL_7:
    LODWORD(v15) = v11;
    AslLogCallPrintf(1, "SdbMergeDatabases", v13, v12, v15);
    goto LABEL_16;
  }
  v11 = SdbWriteDatabaseToFile(v16, a3);
  v9 = v11;
  if ( v11 < 0 )
  {
    v12 = "SdbWriteDatabaseToFile failed to write the database to disk [%x]";
    v13 = 5715;
    goto LABEL_7;
  }
  if ( (*(_BYTE *)(v8 + 24) & 4) != 0 )
  {
    if ( g_CompressCallback )
    {
      AslLogCallPrintf(3, "SdbMergeDatabases", 5724, "Compressing result database as original was.");
      if ( !(unsigned int)SdbpCompressExistingDatabase(a3, a3) )
      {
        AslLogCallPrintf(
          1,
          "SdbMergeDatabases",
          5727,
          "SdbpCompressExistingDatabase failed to compress the resulting database. Writing out uncompressed.");
        v11 = SdbWriteDatabaseToFile(v16, a3);
        v9 = v11;
        if ( v11 < 0 )
        {
          v12 = "SdbWriteDatabaseToFile failed to write the database to disk [%x]";
          v13 = 5731;
          goto LABEL_7;
        }
      }
    }
  }
  v9 = 0;
LABEL_16:
  SdbCloseDatabase((_BYTE **)v8);
  if ( v10 )
    SdbCloseDatabase(v10);
LABEL_18:
  if ( v16 )
    SdbCloseDatabase(v16);
  return v9;
}

```

## disassembly

```asm
0x14001a678  push    rbx
0x14001a67a  push    rbp
0x14001a67b  push    rsi
0x14001a67c  push    rdi
0x14001a67d  push    r14
0x14001a67f  sub     rsp, 40h
0x14001a683  mov     rbp, r8
0x14001a686  mov     [rsp+68h+var_38], 0
0x14001a68f  mov     edi, 10h
0x14001a694  mov     r14d, r9d
0x14001a697  mov     r8d, edi
0x14001a69a  mov     rbx, rdx
0x14001a69d  call    SdbOpenDatabaseEx
0x14001a6a2  mov     rsi, rax
0x14001a6a5  test    rax, rax
0x14001a6a8  jnz     short loc_14001A6D0
0x14001a6aa  lea     r9, aFailedToOpenOr_0; "Failed to open original SDB"
0x14001a6b1  mov     r8d, 163Bh
0x14001a6b7  lea     rdx, aSdbmergedataba; "SdbMergeDatabases"
0x14001a6be  mov     ebx, 0C0000136h
0x14001a6c3  lea     ecx, [rdi-0Fh]
0x14001a6c6  call    AslLogCallPrintf
0x14001a6cb  jmp     loc_14001A810
0x14001a6d0  mov     r8d, edi
0x14001a6d3  mov     rcx, rbx
0x14001a6d6  call    SdbOpenDatabaseEx
0x14001a6db  mov     rdi, rax
0x14001a6de  test    rax, rax
0x14001a6e1  jnz     short loc_14001A709
0x14001a6e3  lea     r9, aFailedToOpenMe_0; "Failed to open merge SDB"
0x14001a6ea  mov     r8d, 1642h
0x14001a6f0  lea     rdx, aSdbmergedataba; "SdbMergeDatabases"
0x14001a6f7  mov     ebx, 0C0000136h
0x14001a6fc  lea     ecx, [rax+1]
0x14001a6ff  call    AslLogCallPrintf
0x14001a704  jmp     loc_14001A7FB
0x14001a709  lea     rax, [rsp+68h+var_38]
0x14001a70e  mov     r9d, r14d
0x14001a711  mov     [rsp+68h+var_40], rax
0x14001a716  xor     r8d, r8d
0x14001a719  mov     rdx, rdi
0x14001a71c  mov     dword ptr [rsp+68h+var_48], 0
0x14001a724  mov     rcx, rsi
0x14001a727  call    SdbpMergeOrDiffDatabasesInMemoryImpl
0x14001a72c  mov     ebx, eax
0x14001a72e  test    eax, eax
0x14001a730  jns     short loc_14001A759
0x14001a732  lea     r9, aSdbpmergeordif_0; "SdbpMergeOrDiffDatabasesInMemoryImpl fa"...
0x14001a739  mov     r8d, 164Dh
0x14001a73f  lea     rdx, aSdbmergedataba; "SdbMergeDatabases"
0x14001a746  mov     dword ptr [rsp+68h+var_48], eax
0x14001a74a  mov     ecx, 1
0x14001a74f  call    AslLogCallPrintf
0x14001a754  jmp     loc_14001A7FB
0x14001a759  mov     rcx, [rsp+68h+var_38]
0x14001a75e  mov     rdx, rbp
0x14001a761  call    SdbWriteDatabaseToFile
0x14001a766  mov     ebx, eax
0x14001a768  test    eax, eax
0x14001a76a  jns     short loc_14001A77B
0x14001a76c  lea     r9, aSdbwritedataba; "SdbWriteDatabaseToFile failed to write "...
0x14001a773  mov     r8d, 1653h
0x14001a779  jmp     short loc_14001A73F
0x14001a77b  test    byte ptr [rsi+18h], 4
0x14001a77f  jz      short loc_14001A7F9
0x14001a781  cmp     cs:g_CompressCallback, 0
0x14001a789  jz      short loc_14001A7F9
0x14001a78b  lea     r9, aCompressingRes; "Compressing result database as original"...
0x14001a792  mov     r8d, 165Ch
0x14001a798  lea     rdx, aSdbmergedataba; "SdbMergeDatabases"
0x14001a79f  mov     ecx, 3
0x14001a7a4  call    AslLogCallPrintf
0x14001a7a9  mov     rdx, rbp
0x14001a7ac  mov     rcx, rbp
0x14001a7af  call    SdbpCompressExistingDatabase
0x14001a7b4  test    eax, eax
0x14001a7b6  jnz     short loc_14001A7F9
0x14001a7b8  lea     r9, aSdbpcompressex_0; "SdbpCompressExistingDatabase failed to "...
0x14001a7bf  mov     r8d, 165Fh
0x14001a7c5  lea     rdx, aSdbmergedataba; "SdbMergeDatabases"
0x14001a7cc  lea     ecx, [rax+1]
0x14001a7cf  call    AslLogCallPrintf
0x14001a7d4  mov     rcx, [rsp+68h+var_38]
0x14001a7d9  mov     rdx, rbp
0x14001a7dc  call    SdbWriteDatabaseToFile
0x14001a7e1  mov     ebx, eax
0x14001a7e3  test    eax, eax
0x14001a7e5  jns     short loc_14001A7F9
0x14001a7e7  lea     r9, aSdbwritedataba; "SdbWriteDatabaseToFile failed to write "...
0x14001a7ee  mov     r8d, 1663h
0x14001a7f4  jmp     loc_14001A73F
0x14001a7f9  xor     ebx, ebx
0x14001a7fb  mov     rcx, rsi
0x14001a7fe  call    SdbCloseDatabase
0x14001a803  test    rdi, rdi
0x14001a806  jz      short loc_14001A810
0x14001a808  mov     rcx, rdi
0x14001a80b  call    SdbCloseDatabase
0x14001a810  mov     rcx, [rsp+68h+var_38]
0x14001a815  test    rcx, rcx
0x14001a818  jz      short loc_14001A81F
0x14001a81a  call    SdbCloseDatabase
0x14001a81f  mov     eax, ebx
0x14001a821  add     rsp, 40h
0x14001a825  pop     r14
0x14001a827  pop     rdi
0x14001a828  pop     rsi
0x14001a829  pop     rbp
0x14001a82a  pop     rbx
0x14001a82b  retn
```
