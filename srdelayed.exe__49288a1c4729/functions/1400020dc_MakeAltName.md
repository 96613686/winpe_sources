# MakeAltName

- ea: `0x1400020dc`
- end: `0x1400021c8`
- name: `MakeAltName`
- size: `236`
- prototype: `NTSTATUS __fastcall(PCUNICODE_STRING StringIn, PUNICODE_STRING Destination)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400028a4`

## callees

- `0x1400019d4`
- `0x1400020dc`
- `0x1400023a0`
- `0x140002458`
- `0x140003770`

## import_xrefs

- `ntdll!RtlAppendUnicodeToString` at `0x14000217c`
- `ntdll!RtlAppendUnicodeToString` at `0x14000217c`
- `ntdll!RtlFreeUnicodeString` at `0x140002148`
- `ntdll!RtlFreeUnicodeString` at `0x140002148`
- `ntdll!RtlDuplicateUnicodeString` at `0x140002159`
- `ntdll!RtlDuplicateUnicodeString` at `0x140002159`

## pseudocode

```c
NTSTATUS __fastcall MakeAltName(PCUNICODE_STRING StringIn, PUNICODE_STRING Destination)
{
  int v4; // edi
  NTSTATUS result; // eax
  __int64 v6; // [rsp+30h] [rbp-38h]
  wchar_t pszDest[12]; // [rsp+40h] [rbp-28h] BYREF

  v4 = 0;
LABEL_2:
  LODWORD(v6) = ulAltCounter++;
  result = RtlStringCbPrintfExW(pszDest, 0x16u, 0, 0, 0, L".%ld", v6);
  if ( result >= 0 )
  {
    RtlFreeUnicodeString(Destination);
    for ( result = RtlDuplicateUnicodeString(3u, StringIn, Destination); result >= 0; result = Realloc(Destination) )
    {
      result = RtlAppendUnicodeToString(Destination, pszDest);
      if ( result >= 0 )
      {
        if ( !(unsigned __int8)FileExists(Destination) )
          return 0;
        if ( (unsigned int)++v4 < 0x3E8 )
          goto LABEL_2;
        return -2147483642;
      }
      if ( result != -1073741789 )
        return result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400020dc  mov     [rsp+arg_10], rbx
0x1400020e1  mov     [rsp+arg_18], rsi
0x1400020e6  push    rdi
0x1400020e7  sub     rsp, 60h
0x1400020eb  mov     rax, cs:__security_cookie
0x1400020f2  xor     rax, rsp
0x1400020f5  mov     [rsp+68h+var_10], rax
0x1400020fa  mov     rbx, rdx
0x1400020fd  mov     rsi, rcx
0x140002100  xor     edi, edi
0x140002102  mov     r8d, cs:ulAltCounter
0x140002109  lea     rcx, [rsp+68h+pszDest]; pszDest
0x14000210e  mov     [rsp+68h+var_38], r8d
0x140002113  xor     r9d, r9d; pcbRemaining
0x140002116  lea     eax, [r8+1]
0x14000211a  xor     r8d, r8d; ppszDestEnd
0x14000211d  mov     cs:ulAltCounter, eax
0x140002123  lea     edx, [r9+16h]; cbDest
0x140002127  lea     rax, aLd; ".%ld"
0x14000212e  mov     [rsp+68h+pszFormat], rax; pszFormat
0x140002133  mov     qword ptr [rsp+68h+dwFlags], 0; dwFlags
0x14000213c  call    RtlStringCbPrintfExW
0x140002141  test    eax, eax
0x140002143  js      short loc_1400021A9
0x140002145  mov     rcx, rbx; UnicodeString
0x140002148  call    cs:__imp_RtlFreeUnicodeString
0x14000214e  mov     r8, rbx; StringOut
0x140002151  mov     rdx, rsi; StringIn
0x140002154  mov     ecx, 3; Flags
0x140002159  call    cs:__imp_RtlDuplicateUnicodeString
0x14000215f  jmp     short loc_140002170
0x140002161  cmp     eax, 0C0000023h
0x140002166  jnz     short loc_1400021A9
0x140002168  mov     rcx, rbx
0x14000216b  call    Realloc
0x140002170  test    eax, eax
0x140002172  js      short loc_1400021A9
0x140002174  lea     rdx, [rsp+68h+pszDest]; Source
0x140002179  mov     rcx, rbx; Destination
0x14000217c  call    cs:__imp_RtlAppendUnicodeToString
0x140002182  test    eax, eax
0x140002184  js      short loc_140002161
0x140002186  mov     rcx, rbx
0x140002189  call    FileExists
0x14000218e  test    al, al
0x140002190  jz      short loc_1400021A7
0x140002192  inc     edi
0x140002194  cmp     edi, 3E8h
0x14000219a  jb      loc_140002102
0x1400021a0  mov     eax, 80000006h
0x1400021a5  jmp     short loc_1400021A9
0x1400021a7  xor     eax, eax
0x1400021a9  mov     rcx, [rsp+68h+var_10]
0x1400021ae  xor     rcx, rsp; StackCookie
0x1400021b1  call    __security_check_cookie
0x1400021b6  lea     r11, [rsp+68h+var_8]
0x1400021bb  mov     rbx, [r11+20h]
0x1400021bf  mov     rsi, [r11+28h]
0x1400021c3  mov     rsp, r11
0x1400021c6  pop     rdi
0x1400021c7  retn
```
