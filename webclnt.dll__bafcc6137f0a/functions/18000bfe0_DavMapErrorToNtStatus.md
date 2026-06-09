# DavMapErrorToNtStatus

- ea: `0x18000bfe0`
- end: `0x18000c11f`
- name: `DavMapErrorToNtStatus`
- size: `319`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `14`
- callee_count: `3`
- tags: ``

## callers

- `0x1800056f4`
- `0x180007e10`
- `0x1800196d0`
- `0x18001ca70`
- `0x18001db70`
- `0x18001dfc0`
- `0x18001ead0`
- `0x18001f190`
- `0x180021f00`
- `0x180022870`
- `0x180023360`
- `0x180023960`
- `0x180024000`
- `0x180024190`

## callees

- `0x18000bd30`
- `0x18000bfe0`
- `0x18000c2fc`

## pseudocode

```c
__int64 __fastcall DavMapErrorToNtStatus(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // edi
  __int64 v4; // rbx
  __int64 v6; // rbx
  unsigned int v7; // ebx
  __int64 v8; // r8

  v3 = a1;
  if ( (unsigned int)(a1 - 12001) > 0xC0 )
    goto LABEL_22;
  if ( (unsigned int)a1 >= rgHttpToNtstatus1[0] && (unsigned int)a1 <= dword_180036170 )
  {
    v4 = 0;
    while ( rgHttpToNtstatus1[2 * v4] != (_DWORD)a1 )
    {
      v4 = (unsigned int)(v4 + 1);
      if ( (int)v4 > 20 )
        return 3221225473LL;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_Ld(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, a3, (unsigned int)dword_1800360D4[2 * v4], a1);
    return (unsigned int)dword_1800360D4[2 * v4];
  }
  if ( (unsigned int)a1 < rgHttpToNtstatus2[0] || (unsigned int)a1 > dword_180036380 )
  {
LABEL_22:
    v7 = DavDosErrorToNtStatus(a1);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_Ld(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, v8, v7, v3);
    return v7;
  }
  v6 = 0;
  while ( rgHttpToNtstatus2[2 * v6] != (_DWORD)a1 )
  {
    v6 = (unsigned int)(v6 + 1);
    if ( (int)v6 > 24 )
      return 3221225473LL;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_Ld(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, a3, (unsigned int)dword_1800362C4[2 * v6], a1);
  return (unsigned int)dword_1800362C4[2 * v6];
}

```

## disassembly

```asm
0x18000bfe0  mov     [rsp+arg_0], rbx
0x18000bfe5  mov     [rsp+arg_8], rsi
0x18000bfea  push    rdi
0x18000bfeb  sub     rsp, 30h
0x18000bfef  lea     eax, [rcx-2EE1h]
0x18000bff5  mov     edi, ecx
0x18000bff7  cmp     eax, 0C0h
0x18000bffc  ja      loc_18000C0D8
0x18000c002  cmp     ecx, cs:rgHttpToNtstatus1
0x18000c008  jb      short loc_18000C06C
0x18000c00a  cmp     ecx, cs:dword_180036170
0x18000c010  ja      short loc_18000C06C
0x18000c012  xor     ebx, ebx
0x18000c014  lea     rsi, __ImageBase
0x18000c01b  cmp     rva rgHttpToNtstatus1[rsi+rbx*8], edi
0x18000c022  jz      short loc_18000C02D
0x18000c024  inc     ebx
0x18000c026  cmp     ebx, 14h
0x18000c029  jle     short loc_18000C01B
0x18000c02b  jmp     short loc_18000C095
0x18000c02d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c034  lea     rax, WPP_GLOBAL_Control
0x18000c03b  cmp     rcx, rax
0x18000c03e  jz      short loc_18000C060
0x18000c040  test    byte ptr [rcx+1Ch], 2
0x18000c044  jz      short loc_18000C060
0x18000c046  mov     r9d, rva dword_1800360D4[rsi+rbx*8]
0x18000c04e  mov     edx, 10h
0x18000c053  mov     rcx, [rcx+10h]
0x18000c057  mov     [rsp+38h+var_18], edi
0x18000c05b  call    WPP_SF_Ld
0x18000c060  mov     eax, rva dword_1800360D4[rsi+rbx*8]
0x18000c067  jmp     loc_18000C10F
0x18000c06c  cmp     edi, cs:rgHttpToNtstatus2
0x18000c072  jb      short loc_18000C0D8
0x18000c074  cmp     edi, cs:dword_180036380
0x18000c07a  ja      short loc_18000C0D8
0x18000c07c  xor     ebx, ebx
0x18000c07e  lea     rsi, __ImageBase
0x18000c085  cmp     rva rgHttpToNtstatus2[rsi+rbx*8], edi
0x18000c08c  jz      short loc_18000C09C
0x18000c08e  inc     ebx
0x18000c090  cmp     ebx, 18h
0x18000c093  jle     short loc_18000C085
0x18000c095  mov     eax, 0C0000001h
0x18000c09a  jmp     short loc_18000C10F
0x18000c09c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c0a3  lea     rax, WPP_GLOBAL_Control
0x18000c0aa  cmp     rcx, rax
0x18000c0ad  jz      short loc_18000C0CF
0x18000c0af  test    byte ptr [rcx+1Ch], 2
0x18000c0b3  jz      short loc_18000C0CF
0x18000c0b5  mov     r9d, rva dword_1800362C4[rsi+rbx*8]
0x18000c0bd  mov     edx, 11h
0x18000c0c2  mov     rcx, [rcx+10h]
0x18000c0c6  mov     [rsp+38h+var_18], edi
0x18000c0ca  call    WPP_SF_Ld
0x18000c0cf  mov     eax, rva dword_1800362C4[rsi+rbx*8]
0x18000c0d6  jmp     short loc_18000C10F
0x18000c0d8  call    DavDosErrorToNtStatus
0x18000c0dd  mov     ebx, eax
0x18000c0df  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c0e6  lea     rax, WPP_GLOBAL_Control
0x18000c0ed  cmp     rcx, rax
0x18000c0f0  jz      short loc_18000C10D
0x18000c0f2  test    byte ptr [rcx+1Ch], 2
0x18000c0f6  jz      short loc_18000C10D
0x18000c0f8  mov     rcx, [rcx+10h]
0x18000c0fc  mov     edx, 12h
0x18000c101  mov     r9d, ebx
0x18000c104  mov     [rsp+38h+var_18], edi
0x18000c108  call    WPP_SF_Ld
0x18000c10d  mov     eax, ebx
0x18000c10f  mov     rbx, [rsp+38h+arg_0]
0x18000c114  mov     rsi, [rsp+38h+arg_8]
0x18000c119  add     rsp, 30h
0x18000c11d  pop     rdi
0x18000c11e  retn
```
