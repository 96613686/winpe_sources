# SdbMakeIndexKeyFromStringEx

- ea: `0x140018b4c`
- end: `0x140018cad`
- name: `SdbMakeIndexKeyFromStringEx`
- size: `353`
- prototype: `__int64 __fastcall(PCWSTR SourceString, char)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140018d48`
- `0x140019410`

## callees

- `0x14001008c`
- `0x140018b4c`
- `0x14002e420`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140018bab`
- `ntdll!RtlInitUnicodeString` at `0x140018bab`
- `ntdll!RtlUpcaseUnicodeString` at `0x140018be7`
- `ntdll!RtlUpcaseUnicodeString` at `0x140018be7`
- `ntdll!RtlCopyUnicodeString` at `0x140018bca`
- `ntdll!RtlCopyUnicodeString` at `0x140018bca`

## pseudocode

```c
__int64 __fastcall SdbMakeIndexKeyFromStringEx(PCWSTR SourceString, char a2)
{
  unsigned __int64 v2; // rax
  const WCHAR *v4; // rdx
  __int64 result; // rax
  unsigned __int64 v6; // r8
  unsigned __int64 v7; // rdx
  bool v8; // cc
  unsigned __int64 v9; // rax
  char *v10; // r8
  unsigned __int16 *v11; // r9
  unsigned __int64 v12; // rcx
  unsigned __int16 v13; // ax
  __int16 v14; // ax
  UNICODE_STRING SourceStringa; // [rsp+30h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING v17; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v18[16]; // [rsp+60h] [rbp+7h] BYREF
  char v19; // [rsp+70h] [rbp+17h] BYREF

  v2 = -1;
  do
    ++v2;
  while ( SourceString[v2] );
  DestinationString = 0;
  SourceStringa = 0;
  v17 = 0;
  if ( v2 > 8 && (a2 & 2) != 0 )
    v4 = &SourceString[v2 - 8];
  else
    v4 = SourceString;
  RtlInitUnicodeString(&DestinationString, v4);
  SourceStringa.Buffer = (PWSTR)&v19;
  SourceStringa.MaximumLength = 16;
  RtlCopyUnicodeString(&SourceStringa, &DestinationString);
  v17.MaximumLength = 16;
  v17.Buffer = (PWSTR)v18;
  if ( RtlUpcaseUnicodeString(&v17, &SourceStringa, 0) < 0 )
  {
    AslLogCallPrintf(1, "SdbMakeIndexKeyFromStringEx", 1633, "Failed to upcase unicode string \"%ws\"", SourceString);
    return 0;
  }
  v6 = 0;
  v7 = (unsigned __int64)v17.Length >> 1;
  if ( v7 )
  {
    while ( 1 )
    {
      v8 = v7 <= 8;
      if ( v7 >= 8 )
        break;
      v9 = v7 + 1;
      if ( !HIBYTE(v17.Buffer[v6]) )
        v9 = v7;
      ++v6;
      v7 = v9;
      if ( v6 >= (unsigned __int64)v17.Length >> 1 )
        goto LABEL_15;
    }
  }
  else
  {
LABEL_15:
    v8 = v7 <= 8;
  }
  if ( !v8 )
    return 0;
  v10 = (char *)&v17.MaximumLength + 5;
  result = 0;
  *(_QWORD *)&v17.Length = 0;
  v11 = (unsigned __int16 *)v18;
  v12 = 0;
  if ( v7 )
  {
    do
    {
      v13 = *v11++;
      *v10-- = v13;
      v14 = HIBYTE(v13);
      if ( (_BYTE)v14 )
      {
        if ( v12 < 7 )
        {
          *v10-- = v14;
          ++v12;
        }
      }
      ++v12;
    }
    while ( v12 < v7 );
    return *(_QWORD *)&v17.Length;
  }
  return result;
}

```

## disassembly

```asm
0x140018b4c  push    rbp
0x140018b4e  push    rbx
0x140018b4f  push    rsi
0x140018b50  push    rdi
0x140018b51  lea     rbp, [rsp-3Fh]
0x140018b56  sub     rsp, 98h
0x140018b5d  mov     rax, cs:__security_cookie
0x140018b64  xor     rax, rsp
0x140018b67  mov     [rbp+57h+var_30], rax
0x140018b6b  or      rax, 0FFFFFFFFFFFFFFFFh
0x140018b6f  mov     rbx, rcx
0x140018b72  xor     esi, esi
0x140018b74  inc     rax
0x140018b77  cmp     [rcx+rax*2], si
0x140018b7b  jnz     short loc_140018B74
0x140018b7d  xorps   xmm0, xmm0
0x140018b80  xorps   xmm1, xmm1
0x140018b83  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140018b87  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm1
0x140018b8b  movups  xmmword ptr [rbp+57h+var_60.Length], xmm0
0x140018b8f  cmp     rax, 8
0x140018b93  jbe     short loc_140018BA4
0x140018b95  test    dl, 2
0x140018b98  jz      short loc_140018BA4
0x140018b9a  add     rcx, 0FFFFFFFFFFFFFFF0h
0x140018b9e  lea     rdx, [rcx+rax*2]
0x140018ba2  jmp     short loc_140018BA7
0x140018ba4  mov     rdx, rbx; SourceString
0x140018ba7  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140018bab  call    cs:__imp_RtlInitUnicodeString
0x140018bb1  lea     rax, [rbp+57h+var_40]
0x140018bb5  mov     edi, 10h
0x140018bba  lea     rdx, [rbp+57h+DestinationString]; SourceString
0x140018bbe  mov     [rbp+57h+SourceString.Buffer], rax
0x140018bc2  lea     rcx, [rbp+57h+SourceString]; DestinationString
0x140018bc6  mov     [rbp+57h+SourceString.MaximumLength], di
0x140018bca  call    cs:__imp_RtlCopyUnicodeString
0x140018bd0  lea     rax, [rbp+57h+var_50]
0x140018bd4  mov     [rbp+57h+var_60.MaximumLength], di
0x140018bd8  xor     r8d, r8d; AllocateDestinationString
0x140018bdb  mov     [rbp+57h+var_60.Buffer], rax
0x140018bdf  lea     rdx, [rbp+57h+SourceString]; SourceString
0x140018be3  lea     rcx, [rbp+57h+var_60]; DestinationString
0x140018be7  call    cs:__imp_RtlUpcaseUnicodeString
0x140018bed  test    eax, eax
0x140018bef  jns     short loc_140018C16
0x140018bf1  lea     r9, aFailedToUpcase; "Failed to upcase unicode string \"%ws\""
0x140018bf8  mov     [rsp+0B0h+var_90], rbx
0x140018bfd  mov     r8d, 661h
0x140018c03  lea     rdx, aSdbmakeindexke; "SdbMakeIndexKeyFromStringEx"
0x140018c0a  lea     ecx, [rdi-0Fh]
0x140018c0d  call    AslLogCallPrintf
0x140018c12  xor     eax, eax
0x140018c14  jmp     short loc_140018C95
0x140018c16  movzx   ecx, [rbp+57h+var_60.Length]
0x140018c1a  mov     r8, rsi
0x140018c1d  shr     rcx, 1
0x140018c20  mov     rdx, rcx
0x140018c23  jz      short loc_140018C47
0x140018c25  mov     r9, [rbp+57h+var_60.Buffer]
0x140018c29  cmp     rdx, 8
0x140018c2d  jnb     short loc_140018C4B
0x140018c2f  cmp     [r9+r8*2+1], sil
0x140018c34  lea     rax, [rdx+1]
0x140018c38  cmovz   rax, rdx
0x140018c3c  inc     r8
0x140018c3f  mov     rdx, rax
0x140018c42  cmp     r8, rcx
0x140018c45  jb      short loc_140018C29
0x140018c47  cmp     rdx, 8
0x140018c4b  ja      short loc_140018C12
0x140018c4d  lea     r8, [rbp+57h+var_60+7]
0x140018c51  mov     rax, rsi
0x140018c54  mov     qword ptr [rbp+57h+var_60.Length], rax
0x140018c58  lea     r9, [rbp+57h+var_50]
0x140018c5c  mov     rcx, rsi
0x140018c5f  test    rdx, rdx
0x140018c62  jz      short loc_140018C95
0x140018c64  movzx   eax, word ptr [r9]
0x140018c68  lea     r9, [r9+2]
0x140018c6c  mov     [r8], al
0x140018c6f  dec     r8
0x140018c72  shr     ax, 8
0x140018c76  test    al, al
0x140018c78  jz      short loc_140018C89
0x140018c7a  cmp     rcx, 7
0x140018c7e  jnb     short loc_140018C89
0x140018c80  mov     [r8], al
0x140018c83  dec     r8
0x140018c86  inc     rcx
0x140018c89  inc     rcx
0x140018c8c  cmp     rcx, rdx
0x140018c8f  jb      short loc_140018C64
0x140018c91  mov     rax, qword ptr [rbp+57h+var_60.Length]
0x140018c95  mov     rcx, [rbp+57h+var_30]
0x140018c99  xor     rcx, rsp; StackCookie
0x140018c9c  call    __security_check_cookie
0x140018ca1  add     rsp, 98h
0x140018ca8  pop     rdi
0x140018ca9  pop     rsi
0x140018caa  pop     rbx
0x140018cab  pop     rbp
0x140018cac  retn
```
