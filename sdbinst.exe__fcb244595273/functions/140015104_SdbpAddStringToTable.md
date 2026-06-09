# SdbpAddStringToTable

- ea: `0x140015104`
- end: `0x1400152d0`
- name: `SdbpAddStringToTable`
- size: `460`
- prototype: `__int64 __fastcall(__int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140014fe0`

## callees

- `0x140001f94`
- `0x14000fd88`
- `0x14000fea0`
- `0x14001008c`
- `0x140013898`
- `0x140014380`
- `0x14001443c`
- `0x140015060`
- `0x140015104`
- `0x1400152d8`

## string_xrefs

- `0x14001516c`: `Failed to read a previously written string`
- `0x14001528d`: `Failed to write stringtableitem into the string table`

## pseudocode

```c
__int64 __fastcall SdbpAddStringToTable(__int64 a1, const wchar_t *a2)
{
  __int64 DatabaseInMemory; // rax
  unsigned int v5; // ebx
  unsigned int i; // eax
  __int64 StringTagPtr; // rcx
  const wchar_t *v8; // rax
  __int64 v9; // rcx
  int v10; // edx
  int v11; // r8d
  unsigned int v12; // ebx
  int v13; // eax
  wchar_t v14; // ax
  wchar_t *v15; // rdx
  unsigned int v16; // ecx
  __int64 j; // rsi
  int v18; // eax
  __int64 v19; // rcx

  DatabaseInMemory = *(_QWORD *)(a1 + 2640);
  v5 = 0;
  if ( !DatabaseInMemory )
  {
    DatabaseInMemory = SdbpCreateDatabaseInMemory();
    *(_QWORD *)(a1 + 2640) = DatabaseInMemory;
    if ( !DatabaseInMemory )
      return v5;
  }
  if ( (*(_BYTE *)(a1 + 24) & 0x10) != 0 )
  {
    for ( i = SdbFindFirstTag(DatabaseInMemory, 0, 34817); ; i = SdbFindNextTag(*(_QWORD *)(a1 + 2640), 0, v12) )
    {
      v12 = i;
      if ( !i )
        break;
      StringTagPtr = SdbGetStringTagPtr(*(_QWORD *)(a1 + 2640), i);
      if ( StringTagPtr )
      {
        v8 = a2;
        v9 = StringTagPtr - (_QWORD)a2;
        do
        {
          v10 = *(const wchar_t *)((char *)v8 + v9);
          v11 = *v8 - v10;
          if ( v11 )
            break;
          ++v8;
        }
        while ( v10 );
        if ( !v11 )
        {
          v5 = v12 - 6;
          goto LABEL_30;
        }
      }
      else
      {
        AslLogCallPrintf(1, "SdbpAddStringToTable", 2163, "Failed to read a previously written string");
      }
    }
LABEL_31:
    v19 = *(_QWORD *)(a1 + 2640);
    v5 = *(_DWORD *)(v19 + 20) - 6;
    if ( !(unsigned int)SdbWriteStringTagDirect(v19, 34817, a2) )
    {
      AslLogCallPrintf(1, "SdbpAddStringToTable", 2202, "Failed to write stringtableitem into the string table");
      v5 = 0;
    }
    if ( (*(_BYTE *)(a1 + 24) & 0x10) == 0 )
      AslHashAddString(*(_QWORD *)(a1 + 2648), a2, v5);
    return v5;
  }
  if ( !*(_QWORD *)(a1 + 2648) )
  {
    v13 = AslHashCreate((_QWORD *)(a1 + 2648));
    if ( v13 < 0 )
    {
      AslLogCallPrintf(1, "SdbpAddStringToTable", 2181, "Error creating hash table [%x]", v13);
      return v5;
    }
  }
  v14 = *a2;
  if ( !*a2 )
    goto LABEL_22;
  v15 = (wchar_t *)a2;
  v16 = 0;
  do
  {
    ++v15;
    v16 = v14 + 34 * v16;
    v14 = *v15;
  }
  while ( *v15 );
  if ( !v16 )
LABEL_22:
    v16 = 1;
  for ( j = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 2648) + 8LL) + 8LL * (v16 % **(_DWORD **)(a1 + 2648)));
        j;
        j = *(_QWORD *)(j + 16) )
  {
    v18 = wcsicmp_0(a2, *(const wchar_t **)j);
    if ( v18 <= 0 )
    {
      if ( !v18 )
        v5 = *(_DWORD *)(j + 8);
      break;
    }
  }
LABEL_30:
  if ( !v5 )
    goto LABEL_31;
  return v5;
}

```

## disassembly

```asm
0x140015104  push    rbx
0x140015106  push    rbp
0x140015107  push    rsi
0x140015108  push    rdi
0x140015109  push    r14
0x14001510b  sub     rsp, 30h
0x14001510f  mov     rax, [rcx+0A50h]
0x140015116  xor     ebp, ebp
0x140015118  mov     r14, rdx
0x14001511b  mov     rdi, rcx
0x14001511e  mov     ebx, ebp
0x140015120  test    rax, rax
0x140015123  jnz     short loc_14001513A
0x140015125  call    SdbpCreateDatabaseInMemory
0x14001512a  mov     [rdi+0A50h], rax
0x140015131  test    rax, rax
0x140015134  jz      loc_1400152C3
0x14001513a  test    byte ptr [rdi+18h], 10h
0x14001513e  jz      loc_1400151CE
0x140015144  xor     edx, edx
0x140015146  mov     r8d, 8801h
0x14001514c  mov     rcx, rax
0x14001514f  call    SdbFindFirstTag
0x140015154  jmp     short loc_1400151BB
0x140015156  mov     rcx, [rdi+0A50h]
0x14001515d  mov     edx, ebx
0x14001515f  call    SdbGetStringTagPtr
0x140015164  mov     rcx, rax
0x140015167  test    rax, rax
0x14001516a  jnz     short loc_14001518A
0x14001516c  lea     r9, aFailedToReadAP; "Failed to read a previously written str"...
0x140015173  mov     r8d, 873h
0x140015179  lea     rdx, aSdbpaddstringt; "SdbpAddStringToTable"
0x140015180  lea     ecx, [rax+1]
0x140015183  call    AslLogCallPrintf
0x140015188  jmp     short loc_1400151AA
0x14001518a  mov     rax, r14
0x14001518d  sub     rcx, r14
0x140015190  movzx   r8d, word ptr [rax]
0x140015194  movzx   edx, word ptr [rax+rcx]
0x140015198  sub     r8d, edx
0x14001519b  jnz     short loc_1400151A5
0x14001519d  add     rax, 2
0x1400151a1  test    edx, edx
0x1400151a3  jnz     short loc_140015190
0x1400151a5  test    r8d, r8d
0x1400151a8  jz      short loc_1400151C6
0x1400151aa  mov     rcx, [rdi+0A50h]
0x1400151b1  mov     r8d, ebx
0x1400151b4  xor     edx, edx
0x1400151b6  call    SdbFindNextTag
0x1400151bb  mov     ebx, eax
0x1400151bd  test    eax, eax
0x1400151bf  jnz     short loc_140015156
0x1400151c1  jmp     loc_14001526F
0x1400151c6  add     ebx, 0FFFFFFFAh
0x1400151c9  jmp     loc_14001526B
0x1400151ce  lea     rsi, [rdi+0A58h]
0x1400151d5  cmp     [rsi], rbp
0x1400151d8  jnz     short loc_14001520D
0x1400151da  mov     rcx, rsi
0x1400151dd  call    AslHashCreate
0x1400151e2  test    eax, eax
0x1400151e4  jns     short loc_14001520D
0x1400151e6  lea     r9, aErrorCreatingH; "Error creating hash table [%x]"
0x1400151ed  mov     [rsp+58h+var_38], eax
0x1400151f1  mov     r8d, 885h
0x1400151f7  lea     rdx, aSdbpaddstringt; "SdbpAddStringToTable"
0x1400151fe  mov     ecx, 1
0x140015203  call    AslLogCallPrintf
0x140015208  jmp     loc_1400152C3
0x14001520d  movzx   eax, word ptr [r14]
0x140015211  mov     r8, [rsi]
0x140015214  test    ax, ax
0x140015217  jz      short loc_140015236
0x140015219  mov     rdx, r14
0x14001521c  mov     ecx, ebp
0x14001521e  imul    ecx, 22h ; '"'
0x140015221  lea     rdx, [rdx+2]
0x140015225  movzx   eax, ax
0x140015228  add     ecx, eax
0x14001522a  movzx   eax, word ptr [rdx]
0x14001522d  test    ax, ax
0x140015230  jnz     short loc_14001521E
0x140015232  test    ecx, ecx
0x140015234  jnz     short loc_14001523B
0x140015236  mov     ecx, 1
0x14001523b  xor     edx, edx
0x14001523d  mov     eax, ecx
0x14001523f  div     dword ptr [r8]
0x140015242  mov     rax, [r8+8]
0x140015246  mov     rsi, [rax+rdx*8]
0x14001524a  jmp     short loc_14001525F
0x14001524c  mov     rdx, [rsi]; String2
0x14001524f  mov     rcx, r14; String1
0x140015252  call    _wcsicmp_0
0x140015257  test    eax, eax
0x140015259  jle     short loc_140015266
0x14001525b  mov     rsi, [rsi+10h]
0x14001525f  test    rsi, rsi
0x140015262  jnz     short loc_14001524C
0x140015264  jmp     short loc_14001526B
0x140015266  jnz     short loc_14001526B
0x140015268  mov     ebx, [rsi+8]
0x14001526b  test    ebx, ebx
0x14001526d  jnz     short loc_1400152C3
0x14001526f  mov     rcx, [rdi+0A50h]
0x140015276  mov     edx, 8801h
0x14001527b  mov     r8, r14
0x14001527e  mov     ebx, [rcx+14h]
0x140015281  sub     ebx, 6
0x140015284  call    SdbWriteStringTagDirect
0x140015289  test    eax, eax
0x14001528b  jnz     short loc_1400152AB
0x14001528d  lea     r9, aFailedToWriteS; "Failed to write stringtableitem into th"...
0x140015294  mov     r8d, 89Ah
0x14001529a  lea     rdx, aSdbpaddstringt; "SdbpAddStringToTable"
0x1400152a1  lea     ecx, [rax+1]
0x1400152a4  call    AslLogCallPrintf
0x1400152a9  mov     ebx, ebp
0x1400152ab  test    byte ptr [rdi+18h], 10h
0x1400152af  jnz     short loc_1400152C3
0x1400152b1  mov     rcx, [rdi+0A58h]
0x1400152b8  mov     r8d, ebx
0x1400152bb  mov     rdx, r14
0x1400152be  call    AslHashAddString
0x1400152c3  mov     eax, ebx
0x1400152c5  add     rsp, 30h
0x1400152c9  pop     r14
0x1400152cb  pop     rdi
0x1400152cc  pop     rsi
0x1400152cd  pop     rbp
0x1400152ce  pop     rbx
0x1400152cf  retn
```
