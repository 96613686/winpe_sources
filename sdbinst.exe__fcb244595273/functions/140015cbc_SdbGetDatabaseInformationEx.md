# SdbGetDatabaseInformationEx

- ea: `0x140015cbc`
- end: `0x140015e0e`
- name: `SdbGetDatabaseInformationEx`
- size: `338`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1400046f4`
- `0x140015b08`

## callees

- `0x14001008c`
- `0x140013898`
- `0x140014380`
- `0x140015a18`
- `0x140015cbc`
- `0x14001651c`
- `0x1400178a0`
- `0x14002e420`

## string_xrefs

- `0x140015d0e`: `Can't read database header`

## pseudocode

```c
__int64 __fastcall SdbGetDatabaseInformationEx(__int64 a1, __int64 a2)
{
  __int64 StringTagPtr; // rsi
  unsigned int FirstTag; // eax
  unsigned int v6; // eax
  __int64 v8; // [rsp+30h] [rbp-28h] BYREF
  int v9; // [rsp+38h] [rbp-20h]

  v8 = 0;
  *(_OWORD *)a2 = 0;
  *(_OWORD *)(a2 + 16) = 0;
  v9 = 0;
  *(_OWORD *)(a2 + 32) = 0;
  StringTagPtr = 0;
  if ( (unsigned int)SdbpReadMappedData(a1, 0, &v8, 12) )
  {
    if ( v9 == 1717724275 )
    {
      *(_QWORD *)(a2 + 4) = v8;
      if ( (unsigned int)SdbGetDatabaseID(a1, (void *)(a2 + 24)) )
        *(_DWORD *)a2 |= 1u;
      FirstTag = SdbFindFirstTag(a1, 0, 28673);
      if ( FirstTag )
      {
        v6 = SdbFindFirstTag(a1, FirstTag, 24577);
        if ( v6 )
          StringTagPtr = SdbGetStringTagPtr(a1, v6);
      }
      else
      {
        AslLogCallPrintf(1, "SdbpGetDatabaseDescriptionPtr", 777, "Failed to get database tag, db is corrupt");
      }
      *(_QWORD *)(a2 + 16) = StringTagPtr;
      *(_DWORD *)(a2 + 40) = SdbpGetDatabaseRuntimePlatform(a1);
      LODWORD(StringTagPtr) = 1;
    }
    else
    {
      AslLogCallPrintf(
        1,
        "SdbGetDatabaseInformationEx",
        450,
        "Magic doesn't match. Magic: 0x%08X, Expected: 0x%08X",
        v9,
        1717724275);
    }
  }
  else
  {
    AslLogCallPrintf(1, "SdbGetDatabaseInformationEx", 445, "Can't read database header");
  }
  return (unsigned int)StringTagPtr;
}

```

## disassembly

```asm
0x140015cbc  mov     r11, rsp
0x140015cbf  mov     [r11+18h], rbx
0x140015cc3  mov     [r11+20h], rsi
0x140015cc7  push    rdi
0x140015cc8  sub     rsp, 50h
0x140015ccc  mov     rax, cs:__security_cookie
0x140015cd3  xor     rax, rsp
0x140015cd6  mov     [rsp+58h+var_18], rax
0x140015cdb  xor     eax, eax
0x140015cdd  lea     r8, [r11-28h]
0x140015ce1  xorps   xmm0, xmm0
0x140015ce4  mov     [r11-28h], rax
0x140015ce8  movups  xmmword ptr [rdx], xmm0
0x140015ceb  mov     rbx, rdx
0x140015cee  mov     rdi, rcx
0x140015cf1  movups  xmmword ptr [rdx+10h], xmm0
0x140015cf5  lea     r9d, [rax+0Ch]
0x140015cf9  mov     [rsp+58h+var_20], eax
0x140015cfd  movups  xmmword ptr [rdx+20h], xmm0
0x140015d01  xor     edx, edx
0x140015d03  xor     esi, esi
0x140015d05  call    SdbpReadMappedData
0x140015d0a  test    eax, eax
0x140015d0c  jnz     short loc_140015D2F
0x140015d0e  lea     r9, aCanTReadDataba; "Can't read database header"
0x140015d15  mov     r8d, 1BDh
0x140015d1b  lea     rdx, aSdbgetdatabase_0; "SdbGetDatabaseInformationEx"
0x140015d22  lea     ecx, [rsi+1]
0x140015d25  call    AslLogCallPrintf
0x140015d2a  jmp     loc_140015DEF
0x140015d2f  mov     eax, [rsp+58h+var_20]
0x140015d33  mov     ecx, 66626473h
0x140015d38  cmp     eax, ecx
0x140015d3a  jz      short loc_140015D67
0x140015d3c  mov     [rsp+58h+var_30], ecx
0x140015d40  lea     r9, aMagicDoesnTMat; "Magic doesn't match. Magic: 0x%08X, Exp"...
0x140015d47  mov     ecx, 1
0x140015d4c  mov     [rsp+58h+var_38], eax
0x140015d50  mov     r8d, 1C2h
0x140015d56  lea     rdx, aSdbgetdatabase_0; "SdbGetDatabaseInformationEx"
0x140015d5d  call    AslLogCallPrintf
0x140015d62  jmp     loc_140015DEF
0x140015d67  mov     eax, [rsp+58h+var_28]
0x140015d6b  lea     rdx, [rbx+18h]
0x140015d6f  mov     [rbx+4], eax
0x140015d72  mov     rcx, rdi
0x140015d75  mov     eax, [rsp+58h+var_24]
0x140015d79  mov     [rbx+8], eax
0x140015d7c  call    SdbGetDatabaseID
0x140015d81  test    eax, eax
0x140015d83  jz      short loc_140015D88
0x140015d85  or      dword ptr [rbx], 1
0x140015d88  xor     edx, edx
0x140015d8a  mov     r8d, 7001h
0x140015d90  mov     rcx, rdi
0x140015d93  call    SdbFindFirstTag
0x140015d98  test    eax, eax
0x140015d9a  jnz     short loc_140015DBA
0x140015d9c  lea     r9, aFailedToGetDat; "Failed to get database tag, db is corru"...
0x140015da3  mov     r8d, 309h
0x140015da9  lea     rdx, aSdbpgetdatabas_0; "SdbpGetDatabaseDescriptionPtr"
0x140015db0  lea     ecx, [rax+1]
0x140015db3  call    AslLogCallPrintf
0x140015db8  jmp     short loc_140015DDB
0x140015dba  mov     r8d, 6001h
0x140015dc0  mov     edx, eax
0x140015dc2  mov     rcx, rdi
0x140015dc5  call    SdbFindFirstTag
0x140015dca  test    eax, eax
0x140015dcc  jz      short loc_140015DDB
0x140015dce  mov     edx, eax
0x140015dd0  mov     rcx, rdi
0x140015dd3  call    SdbGetStringTagPtr
0x140015dd8  mov     rsi, rax
0x140015ddb  mov     rcx, rdi
0x140015dde  mov     [rbx+10h], rsi
0x140015de2  call    SdbpGetDatabaseRuntimePlatform
0x140015de7  mov     [rbx+28h], eax
0x140015dea  mov     esi, 1
0x140015def  mov     eax, esi
0x140015df1  mov     rcx, [rsp+58h+var_18]
0x140015df6  xor     rcx, rsp; StackCookie
0x140015df9  call    __security_check_cookie
0x140015dfe  mov     rbx, [rsp+58h+arg_10]
0x140015e03  mov     rsi, [rsp+58h+arg_18]
0x140015e08  add     rsp, 50h
0x140015e0c  pop     rdi
0x140015e0d  retn
```
