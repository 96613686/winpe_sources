# SdbpFinalizeMiniDbInMemory

- ea: `0x1400153a4`
- end: `0x14001552f`
- name: `SdbpFinalizeMiniDbInMemory`
- size: `395`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14001d808`

## callees

- `0x14000ffe0`
- `0x14001008c`
- `0x140013898`
- `0x140014380`
- `0x14001443c`
- `0x140014500`
- `0x140014574`
- `0x140014b64`
- `0x140015060`
- `0x1400153a4`
- `0x140015538`

## string_xrefs

- `0x140015466`: `Failed to read a string`
- `0x140015457`: `Failed to write stringtable item`
- `0x140015448`: `Failed to write end list tag for the string table`

## pseudocode

```c
__int64 __fastcall SdbpFinalizeMiniDbInMemory(__int64 a1)
{
  __int64 v3; // rcx
  unsigned int NextTag; // edi
  unsigned int v5; // esi
  __int64 StringTagPtr; // rax
  unsigned int v7; // edi
  __int64 v8; // rdi
  _BYTE **v9; // rcx
  void *v10; // rcx

  if ( !*(_DWORD *)(a1 + 16) )
    return 3221225659LL;
  v3 = *(_QWORD *)(a1 + 2640);
  if ( v3 && (NextTag = SdbFindFirstTag(v3, 0, 34817)) != 0 )
  {
    v5 = SdbBeginWriteListTag(a1, 30721);
    do
    {
      StringTagPtr = SdbGetStringTagPtr(*(_QWORD *)(a1 + 2640), NextTag);
      if ( !StringTagPtr )
      {
        AslLogCallPrintf(1, "SdbpFinalizeMiniDbInMemory", 866, "Failed to read a string");
        goto LABEL_13;
      }
      if ( !(unsigned int)SdbWriteStringTagDirect(a1, 34817, StringTagPtr) )
      {
        AslLogCallPrintf(1, "SdbpFinalizeMiniDbInMemory", 872, "Failed to write stringtable item");
        goto LABEL_13;
      }
      NextTag = SdbFindNextTag(*(_QWORD *)(a1 + 2640), 0, NextTag);
    }
    while ( NextTag );
    if ( (unsigned int)SdbEndWriteListTag(a1, v5) )
      goto LABEL_14;
    AslLogCallPrintf(1, "SdbpFinalizeMiniDbInMemory", 881, "Failed to write end list tag for the string table");
LABEL_13:
    v7 = -1073741595;
  }
  else
  {
LABEL_14:
    v8 = 0;
    if ( *(_DWORD *)(a1 + 2636) )
    {
      while ( (unsigned int)SdbpSortIndex(a1, *(unsigned int *)(a1 + 40 * v8 + 48)) )
      {
        v8 = (unsigned int)(v8 + 1);
        if ( (unsigned int)v8 >= *(_DWORD *)(a1 + 2636) )
          goto LABEL_17;
      }
      AslLogCallPrintf(1, "SdbpFinalizeMiniDbInMemory", 893, "Failed to sort index");
      v7 = -1073739509;
    }
    else
    {
LABEL_17:
      *(_DWORD *)(a1 + 24) |= 9u;
      v7 = 0;
      *(_DWORD *)(a1 + 16) = 0;
    }
  }
  v9 = *(_BYTE ***)(a1 + 2640);
  if ( v9 )
  {
    SdbCloseDatabase(v9);
    *(_QWORD *)(a1 + 2640) = 0;
  }
  v10 = *(void **)(a1 + 2648);
  if ( v10 )
  {
    AslHashFree(v10);
    *(_QWORD *)(a1 + 2648) = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x1400153a4  mov     [rsp+arg_0], rbx
0x1400153a9  mov     [rsp+arg_8], rsi
0x1400153ae  push    rdi
0x1400153af  sub     rsp, 20h
0x1400153b3  cmp     dword ptr [rcx+10h], 0
0x1400153b7  mov     rbx, rcx
0x1400153ba  jnz     short loc_1400153C6
0x1400153bc  mov     eax, 0C00000BBh
0x1400153c1  jmp     loc_1400154FA
0x1400153c6  mov     rcx, [rcx+0A50h]
0x1400153cd  test    rcx, rcx
0x1400153d0  jz      loc_14001548B
0x1400153d6  xor     edx, edx
0x1400153d8  mov     r8d, 8801h
0x1400153de  call    SdbFindFirstTag
0x1400153e3  mov     edi, eax
0x1400153e5  test    eax, eax
0x1400153e7  jz      loc_14001548B
0x1400153ed  mov     edx, 7801h
0x1400153f2  mov     rcx, rbx
0x1400153f5  call    SdbBeginWriteListTag
0x1400153fa  mov     esi, eax
0x1400153fc  mov     rcx, [rbx+0A50h]
0x140015403  mov     edx, edi
0x140015405  call    SdbGetStringTagPtr
0x14001540a  test    rax, rax
0x14001540d  jz      short loc_140015466
0x14001540f  mov     edx, 8801h
0x140015414  mov     r8, rax
0x140015417  mov     rcx, rbx
0x14001541a  call    SdbWriteStringTagDirect
0x14001541f  test    eax, eax
0x140015421  jz      short loc_140015457
0x140015423  mov     rcx, [rbx+0A50h]
0x14001542a  mov     r8d, edi
0x14001542d  xor     edx, edx
0x14001542f  call    SdbFindNextTag
0x140015434  mov     edi, eax
0x140015436  test    eax, eax
0x140015438  jnz     short loc_1400153FC
0x14001543a  mov     edx, esi
0x14001543c  mov     rcx, rbx
0x14001543f  call    SdbEndWriteListTag
0x140015444  test    eax, eax
0x140015446  jnz     short loc_14001548B
0x140015448  lea     r9, aFailedToWriteE_2; "Failed to write end list tag for the st"...
0x14001544f  mov     r8d, 371h
0x140015455  jmp     short loc_140015473
0x140015457  lea     r9, aFailedToWriteS_1; "Failed to write stringtable item"
0x14001545e  mov     r8d, 368h
0x140015464  jmp     short loc_140015473
0x140015466  lea     r9, aFailedToReadAS; "Failed to read a string"
0x14001546d  mov     r8d, 362h
0x140015473  lea     rdx, aSdbpfinalizemi_0; "SdbpFinalizeMiniDbInMemory"
0x14001547a  mov     ecx, 1
0x14001547f  call    AslLogCallPrintf
0x140015484  mov     edi, 0C00000E5h
0x140015489  jmp     short loc_1400154C0
0x14001548b  xor     edi, edi
0x14001548d  cmp     [rbx+0A4Ch], edi
0x140015493  jbe     short loc_1400154B3
0x140015495  lea     rdx, [rdi+rdi*4]
0x140015499  mov     rcx, rbx
0x14001549c  mov     edx, [rbx+rdx*8+30h]
0x1400154a0  call    SdbpSortIndex
0x1400154a5  test    eax, eax
0x1400154a7  jz      short loc_14001550A
0x1400154a9  inc     edi
0x1400154ab  cmp     edi, [rbx+0A4Ch]
0x1400154b1  jb      short loc_140015495
0x1400154b3  or      dword ptr [rbx+18h], 9
0x1400154b7  xor     edi, edi
0x1400154b9  mov     dword ptr [rbx+10h], 0
0x1400154c0  mov     rcx, [rbx+0A50h]
0x1400154c7  test    rcx, rcx
0x1400154ca  jz      short loc_1400154DC
0x1400154cc  call    SdbCloseDatabase
0x1400154d1  mov     qword ptr [rbx+0A50h], 0
0x1400154dc  mov     rcx, [rbx+0A58h]; P
0x1400154e3  test    rcx, rcx
0x1400154e6  jz      short loc_1400154F8
0x1400154e8  call    AslHashFree
0x1400154ed  mov     qword ptr [rbx+0A58h], 0
0x1400154f8  mov     eax, edi
0x1400154fa  mov     rbx, [rsp+28h+arg_0]
0x1400154ff  mov     rsi, [rsp+28h+arg_8]
0x140015504  add     rsp, 20h
0x140015508  pop     rdi
0x140015509  retn
0x14001550a  lea     r9, aFailedToSortIn; "Failed to sort index"
0x140015511  mov     r8d, 37Dh
0x140015517  lea     rdx, aSdbpfinalizemi_0; "SdbpFinalizeMiniDbInMemory"
0x14001551e  mov     ecx, 1
0x140015523  call    AslLogCallPrintf
0x140015528  mov     edi, 0C000090Bh
0x14001552d  jmp     short loc_1400154C0
```
