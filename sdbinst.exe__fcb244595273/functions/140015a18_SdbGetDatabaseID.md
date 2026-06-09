# SdbGetDatabaseID

- ea: `0x140015a18`
- end: `0x140015b00`
- name: `SdbGetDatabaseID`
- size: `232`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140015cbc`
- `0x140017be4`

## callees

- `0x140002212`
- `0x14001008c`
- `0x140013c14`
- `0x140014380`
- `0x140015a18`

## string_xrefs

- `0x140015aaa`: `Failed to read database id 0x%lx`

## pseudocode

```c
__int64 __fastcall SdbGetDatabaseID(__int64 a1, void *a2)
{
  int v2; // eax
  unsigned int v3; // ebp
  unsigned int FirstTag; // eax
  unsigned int v7; // eax
  int v8; // esi
  const void *v9; // rdi

  v2 = *(_DWORD *)(a1 + 24);
  v3 = 0;
  if ( (v2 & 2) != 0 )
  {
    v9 = (const void *)(a1 + 28);
  }
  else
  {
    FirstTag = SdbFindFirstTag(a1, 0, 28673);
    if ( !FirstTag )
    {
      AslLogCallPrintf(1, "SdbGetDatabaseID", 582, "Failed to get root tag");
      return v3;
    }
    v7 = SdbFindFirstTag(a1, FirstTag, 36871);
    v8 = v7;
    if ( !v7 )
    {
      AslLogCallPrintf(1, "SdbGetDatabaseID", 588, "Failed to get the database id");
      return v3;
    }
    v9 = (const void *)(a1 + 28);
    if ( !(unsigned int)SdbReadBinaryTag(a1, v7, a1 + 28, 16) )
    {
      AslLogCallPrintf(1, "SdbGetDatabaseID", 593, "Failed to read database id 0x%lx", v8);
      return v3;
    }
    *(_DWORD *)(a1 + 24) |= 2u;
    v2 = *(_DWORD *)(a1 + 24);
  }
  if ( (v2 & 2) != 0 )
  {
    memmove_0(a2, v9, 0x10u);
    return 1;
  }
  return v3;
}

```

## disassembly

```asm
0x140015a18  push    rbx
0x140015a1a  push    rbp
0x140015a1b  push    rsi
0x140015a1c  push    rdi
0x140015a1d  push    r14
0x140015a1f  sub     rsp, 30h
0x140015a23  mov     eax, [rcx+18h]
0x140015a26  xor     ebp, ebp
0x140015a28  mov     r14, rdx
0x140015a2b  mov     rbx, rcx
0x140015a2e  test    al, 2
0x140015a30  jnz     loc_140015AD5
0x140015a36  xor     edx, edx
0x140015a38  mov     r8d, 7001h
0x140015a3e  call    SdbFindFirstTag
0x140015a43  test    eax, eax
0x140015a45  jnz     short loc_140015A6A
0x140015a47  lea     r9, aFailedToGetRoo; "Failed to get root tag"
0x140015a4e  mov     r8d, 246h
0x140015a54  lea     rdx, aSdbgetdatabase_1; "SdbGetDatabaseID"
0x140015a5b  mov     ecx, 1
0x140015a60  call    AslLogCallPrintf
0x140015a65  jmp     loc_140015AF3
0x140015a6a  mov     r8d, 9007h
0x140015a70  mov     edx, eax
0x140015a72  mov     rcx, rbx
0x140015a75  call    SdbFindFirstTag
0x140015a7a  mov     esi, eax
0x140015a7c  test    eax, eax
0x140015a7e  jnz     short loc_140015A8F
0x140015a80  lea     r9, aFailedToGetThe_6; "Failed to get the database id"
0x140015a87  mov     r8d, 24Ch
0x140015a8d  jmp     short loc_140015A54
0x140015a8f  lea     rdi, [rbx+1Ch]
0x140015a93  mov     r9d, 10h
0x140015a99  mov     r8, rdi
0x140015a9c  mov     edx, esi
0x140015a9e  mov     rcx, rbx
0x140015aa1  call    SdbReadBinaryTag
0x140015aa6  test    eax, eax
0x140015aa8  jnz     short loc_140015ACC
0x140015aaa  lea     r9, aFailedToReadDa_0; "Failed to read database id 0x%lx"
0x140015ab1  mov     [rsp+58h+var_38], esi
0x140015ab5  mov     r8d, 251h
0x140015abb  lea     rdx, aSdbgetdatabase_1; "SdbGetDatabaseID"
0x140015ac2  lea     ecx, [rax+1]
0x140015ac5  call    AslLogCallPrintf
0x140015aca  jmp     short loc_140015AF3
0x140015acc  or      dword ptr [rbx+18h], 2
0x140015ad0  mov     eax, [rbx+18h]
0x140015ad3  jmp     short loc_140015AD9
0x140015ad5  lea     rdi, [rcx+1Ch]
0x140015ad9  test    al, 2
0x140015adb  jz      short loc_140015AF3
0x140015add  mov     r8d, 10h; Size
0x140015ae3  mov     rdx, rdi; Src
0x140015ae6  mov     rcx, r14; void *
0x140015ae9  call    memmove_0
0x140015aee  mov     ebp, 1
0x140015af3  mov     eax, ebp
0x140015af5  add     rsp, 30h
0x140015af9  pop     r14
0x140015afb  pop     rdi
0x140015afc  pop     rsi
0x140015afd  pop     rbp
0x140015afe  pop     rbx
0x140015aff  retn
```
