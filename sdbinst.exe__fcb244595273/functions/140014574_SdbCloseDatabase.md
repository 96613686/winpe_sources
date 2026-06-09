# SdbCloseDatabase

- ea: `0x140014574`
- end: `0x1400147c7`
- name: `SdbCloseDatabase`
- size: `595`
- prototype: `BOOLEAN __fastcall(_BYTE **)`
- caller_count: `10`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x1400045e0`
- `0x140004df8`
- `0x140008500`
- `0x140014574`
- `0x1400153a4`
- `0x14001a678`
- `0x14001d808`
- `0x1400242ac`
- `0x1400286f4`
- `0x14002b138`

## callees

- `0x14000f980`
- `0x14000ffe0`
- `0x14001008c`
- `0x140013898`
- `0x140014380`
- `0x14001443c`
- `0x140014500`
- `0x140014574`
- `0x140014b64`
- `0x140015060`
- `0x140015538`
- `0x14001576c`

## import_xrefs

- `ntdll!NtClose` at `0x140014727`
- `ntdll!NtClose` at `0x140014727`
- `ntdll!RtlFreeHeap` at `0x140014765`
- `ntdll!RtlFreeHeap` at `0x140014786`
- `ntdll!RtlFreeHeap` at `0x140014765`
- `ntdll!RtlFreeHeap` at `0x140014786`
- `ntdll!RtlFreeHeap` at `0x1400147c0`

## string_xrefs

- `0x14001461f`: `Failed to read a string`
- `0x140014610`: `Failed to write stringtable item`
- `0x140014645`: `Failed to write end list tag for the string table`
- `0x1400146fe`: `SdbpWriteDatabase failed`

## pseudocode

```c
BOOLEAN __fastcall SdbCloseDatabase(_BYTE **a1)
{
  _BYTE *v2; // rcx
  unsigned int FirstTag; // edi
  unsigned int v4; // esi
  __int64 StringTagPtr; // rax
  __int64 v6; // rdi
  _BYTE *v7; // rcx
  _BYTE *v8; // rcx
  _BYTE *v9; // r8
  void *v10; // rcx
  NTSTATUS v11; // eax
  _BYTE *v12; // r8

  if ( !*((_DWORD *)a1 + 4) )
    goto LABEL_41;
  v2 = a1[330];
  if ( !v2 )
    goto LABEL_41;
  FirstTag = SdbFindFirstTag(v2, 0, 34817);
  if ( !FirstTag )
    goto LABEL_41;
  v4 = SdbBeginWriteListTag((__int64)a1, 30721);
  while ( 1 )
  {
    StringTagPtr = SdbGetStringTagPtr(a1[330], FirstTag);
    if ( !StringTagPtr )
      break;
    if ( !(unsigned int)SdbWriteStringTagDirect(a1, 34817, StringTagPtr) )
    {
      AslLogCallPrintf(1, "SdbCloseDatabase", 1594, "Failed to write stringtable item");
      goto LABEL_11;
    }
    FirstTag = SdbFindNextTag(a1[330], 0, FirstTag);
    if ( !FirstTag )
      goto LABEL_11;
  }
  AslLogCallPrintf(1, "SdbCloseDatabase", 1589, "Failed to read a string");
LABEL_11:
  if ( !(unsigned int)SdbEndWriteListTag(a1, v4) )
  {
    AslLogCallPrintf(1, "SdbCloseDatabase", 1602, "Failed to write end list tag for the string table");
  }
  else
  {
LABEL_41:
    if ( *((_DWORD *)a1 + 4) )
    {
      v6 = 0;
      if ( *((_DWORD *)a1 + 659) )
      {
        while ( (unsigned int)SdbpSortIndex(a1, LODWORD(a1[5 * v6 + 6])) )
        {
          v6 = (unsigned int)(v6 + 1);
          if ( (unsigned int)v6 >= *((_DWORD *)a1 + 659) )
            goto LABEL_19;
        }
        AslLogCallPrintf(1, "SdbCloseDatabase", 1616, "Failed to sort index");
      }
    }
  }
LABEL_19:
  v7 = a1[330];
  if ( v7 )
  {
    SdbCloseDatabase(v7);
    a1[330] = 0;
  }
  v8 = a1[331];
  if ( v8 )
  {
    AslHashFree(v8);
    a1[331] = 0;
  }
  v9 = a1[1];
  if ( v9 )
  {
    if ( *((_DWORD *)a1 + 4) && *a1 )
    {
      if ( !(unsigned int)SdbpWriteDatabase(a1) )
        AslLogCallPrintf(1, "SdbCloseDatabase", 1642, "SdbpWriteDatabase failed");
      if ( *((_DWORD *)*a1 + 18) )
        v10 = 0;
      else
        v10 = (void *)*((_QWORD *)*a1 + 1);
      v11 = NtClose(v10);
      if ( v11 < 0 )
        AslLogCallPrintf(1, "SdbCloseDatabase", 1650, "Failed to close sdb file handle [%x]", v11);
      v12 = a1[1];
      if ( v12 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
      goto LABEL_37;
    }
    if ( ((_BYTE)a1[3] & 9) == 9 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
      *((_DWORD *)a1 + 5) = 0;
LABEL_37:
      a1[1] = 0;
    }
  }
  AslFileMappingDelete(*a1);
  return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x140014574  push    rbx
0x140014576  push    rsi
0x140014577  push    rdi
0x140014578  push    r14
0x14001457a  push    r15
0x14001457c  sub     rsp, 30h
0x140014580  cmp     dword ptr [rcx+10h], 0
0x140014584  lea     r15, aSdbclosedataba; "SdbCloseDatabase"
0x14001458b  mov     rbx, rcx
0x14001458e  mov     r14d, 1
0x140014594  jz      loc_140014654
0x14001459a  mov     rcx, [rcx+0A50h]
0x1400145a1  test    rcx, rcx
0x1400145a4  jz      loc_140014654
0x1400145aa  xor     edx, edx
0x1400145ac  mov     r8d, 8801h
0x1400145b2  call    SdbFindFirstTag
0x1400145b7  mov     edi, eax
0x1400145b9  test    eax, eax
0x1400145bb  jz      loc_140014654
0x1400145c1  mov     edx, 7801h
0x1400145c6  mov     rcx, rbx
0x1400145c9  call    SdbBeginWriteListTag
0x1400145ce  mov     esi, eax
0x1400145d0  mov     rcx, [rbx+0A50h]
0x1400145d7  mov     edx, edi
0x1400145d9  call    SdbGetStringTagPtr
0x1400145de  test    rax, rax
0x1400145e1  jz      short loc_14001461F
0x1400145e3  mov     edx, 8801h
0x1400145e8  mov     r8, rax
0x1400145eb  mov     rcx, rbx
0x1400145ee  call    SdbWriteStringTagDirect
0x1400145f3  test    eax, eax
0x1400145f5  jz      short loc_140014610
0x1400145f7  mov     rcx, [rbx+0A50h]
0x1400145fe  mov     r8d, edi
0x140014601  xor     edx, edx
0x140014603  call    SdbFindNextTag
0x140014608  mov     edi, eax
0x14001460a  test    eax, eax
0x14001460c  jnz     short loc_1400145D0
0x14001460e  jmp     short loc_140014637
0x140014610  lea     r9, aFailedToWriteS_1; "Failed to write stringtable item"
0x140014617  mov     r8d, 63Ah
0x14001461d  jmp     short loc_14001462C
0x14001461f  lea     r9, aFailedToReadAS; "Failed to read a string"
0x140014626  mov     r8d, 635h
0x14001462c  mov     rdx, r15
0x14001462f  mov     ecx, r14d
0x140014632  call    AslLogCallPrintf
0x140014637  mov     edx, esi
0x140014639  mov     rcx, rbx
0x14001463c  call    SdbEndWriteListTag
0x140014641  test    eax, eax
0x140014643  jnz     short loc_140014654
0x140014645  lea     r9, aFailedToWriteE_2; "Failed to write end list tag for the st"...
0x14001464c  mov     r8d, 642h
0x140014652  jmp     short loc_140014692
0x140014654  cmp     dword ptr [rbx+10h], 0
0x140014658  jz      short loc_14001469D
0x14001465a  xor     edi, edi
0x14001465c  cmp     [rbx+0A4Ch], edi
0x140014662  jbe     short loc_14001469D
0x140014664  lea     rdx, [rdi+rdi*4]
0x140014668  mov     rcx, rbx
0x14001466b  mov     edx, [rbx+rdx*8+30h]
0x14001466f  call    SdbpSortIndex
0x140014674  test    eax, eax
0x140014676  jz      short loc_140014685
0x140014678  add     edi, r14d
0x14001467b  cmp     edi, [rbx+0A4Ch]
0x140014681  jb      short loc_140014664
0x140014683  jmp     short loc_14001469D
0x140014685  lea     r9, aFailedToSortIn; "Failed to sort index"
0x14001468c  mov     r8d, 650h
0x140014692  mov     rdx, r15
0x140014695  mov     ecx, r14d
0x140014698  call    AslLogCallPrintf
0x14001469d  mov     rcx, [rbx+0A50h]
0x1400146a4  test    rcx, rcx
0x1400146a7  jz      short loc_1400146B9
0x1400146a9  call    SdbCloseDatabase
0x1400146ae  mov     qword ptr [rbx+0A50h], 0
0x1400146b9  mov     rcx, [rbx+0A58h]; P
0x1400146c0  test    rcx, rcx
0x1400146c3  jz      short loc_1400146D5
0x1400146c5  call    AslHashFree
0x1400146ca  mov     qword ptr [rbx+0A58h], 0
0x1400146d5  mov     r8, [rbx+8]; P
0x1400146d9  test    r8, r8
0x1400146dc  jz      loc_14001479B
0x1400146e2  cmp     dword ptr [rbx+10h], 0
0x1400146e6  jz      loc_14001476D
0x1400146ec  cmp     qword ptr [rbx], 0
0x1400146f0  jz      short loc_14001476D
0x1400146f2  mov     rcx, rbx
0x1400146f5  call    SdbpWriteDatabase
0x1400146fa  test    eax, eax
0x1400146fc  jnz     short loc_140014716
0x1400146fe  lea     r9, aSdbpwritedatab_0; "SdbpWriteDatabase failed"
0x140014705  mov     r8d, 66Ah
0x14001470b  mov     rdx, r15
0x14001470e  mov     ecx, r14d
0x140014711  call    AslLogCallPrintf
0x140014716  mov     rax, [rbx]
0x140014719  cmp     dword ptr [rax+48h], 0
0x14001471d  jz      short loc_140014723
0x14001471f  xor     ecx, ecx
0x140014721  jmp     short loc_140014727
0x140014723  mov     rcx, [rax+8]; Handle
0x140014727  call    cs:__imp_NtClose
0x14001472d  test    eax, eax
0x14001472f  jns     short loc_14001474D
0x140014731  lea     r9, aFailedToCloseS; "Failed to close sdb file handle [%x]"
0x140014738  mov     [rsp+58h+var_38], eax
0x14001473c  mov     r8d, 672h
0x140014742  mov     rdx, r15
0x140014745  mov     ecx, r14d
0x140014748  call    AslLogCallPrintf
0x14001474d  mov     r8, [rbx+8]; P
0x140014751  test    r8, r8
0x140014754  jz      short loc_140014793
0x140014756  mov     rcx, gs:60h
0x14001475f  xor     edx, edx; Flags
0x140014761  mov     rcx, [rcx+30h]; HeapHandle
0x140014765  call    cs:__imp_RtlFreeHeap
0x14001476b  jmp     short loc_140014793
0x14001476d  mov     eax, [rbx+18h]
0x140014770  and     eax, 9
0x140014773  cmp     al, 9
0x140014775  jnz     short loc_14001479B
0x140014777  mov     rcx, gs:60h
0x140014780  xor     edx, edx; Flags
0x140014782  mov     rcx, [rcx+30h]; HeapHandle
0x140014786  call    cs:__imp_RtlFreeHeap
0x14001478c  mov     dword ptr [rbx+14h], 0
0x140014793  mov     qword ptr [rbx+8], 0
0x14001479b  mov     rcx, [rbx]; P
0x14001479e  call    AslFileMappingDelete
0x1400147a3  mov     rcx, gs:60h
0x1400147ac  mov     r8, rbx
0x1400147af  xor     edx, edx
0x1400147b1  mov     rcx, [rcx+30h]
0x1400147b5  add     rsp, 30h
0x1400147b9  pop     r15
0x1400147bb  pop     r14
0x1400147bd  pop     rdi
0x1400147be  pop     rsi
0x1400147bf  pop     rbx
0x1400147c0  jmp     cs:__imp_RtlFreeHeap
```
