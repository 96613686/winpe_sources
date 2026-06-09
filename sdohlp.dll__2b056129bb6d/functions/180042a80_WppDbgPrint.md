# WppDbgPrint

- ea: `0x180042a80`
- end: `0x180042c11`
- name: `WppDbgPrint`
- size: `401`
- prototype: `__int64 __fastcall(char *String1)`
- caller_count: `135`
- callee_count: `5`
- tags: ``

## callers

- `0x1800255e0`
- `0x1800279f8`
- `0x18002844c`
- `0x18002b1c0`
- `0x18002d420`
- `0x18002d770`
- `0x18002da80`
- `0x18002dd40`
- `0x18002e6a0`
- `0x18002e770`
- `0x18002e970`
- `0x18002eac0`
- `0x18002ee80`
- `0x18002f458`
- `0x18002fcf0`
- `0x18002fed0`
- `0x180030134`
- `0x1800303c0`
- `0x180030644`
- `0x180030814`
- `0x1800308e8`
- `0x180030b00`
- `0x180030d20`
- `0x180030e10`
- `0x180030f40`
- `0x180031140`
- `0x180031200`
- `0x180031570`
- `0x18003172c`
- `0x1800317ec`
- `0x180031a60`
- `0x180031ea8`
- `0x180031f38`
- `0x1800321a0`
- `0x18003233c`
- `0x1800325c0`
- `0x18003277c`
- `0x180032960`
- `0x180032a90`
- `0x180032bc0`
- `0x180032ce0`
- `0x180032ea0`
- `0x180033010`
- `0x180033230`
- `0x180033360`
- `0x180033490`
- `0x1800335b0`
- `0x1800336d0`
- `0x1800338f0`
- `0x180033a30`

## callees

- `0x1800241bb`
- `0x1800414c0`
- `0x1800429a4`
- `0x180042a80`
- `0x180055030`

## import_xrefs

- `msvcrt!_strnicmp` at `0x180042b6e`
- `msvcrt!_strnicmp` at `0x180042b6e`
- `msvcrt!vsprintf_s` at `0x180042bdc`
- `msvcrt!vsprintf_s` at `0x180042bdc`

## pseudocode

```c
char WppDbgPrint(char *String1, ...)
{
  __int64 v2; // rax
  char *v3; // rdi
  __int64 i; // rsi
  unsigned __int64 j; // r14
  char **v6; // r15
  const char *v7; // rdx
  size_t v8; // r8
  char *v9; // rcx
  __int64 v11; // [rsp+28h] [rbp-E0h] BYREF
  char *v12; // [rsp+30h] [rbp-D8h] BYREF
  char *v13; // [rsp+38h] [rbp-D0h] BYREF
  char Format[256]; // [rsp+48h] [rbp-C0h] BYREF
  char Buffer[512]; // [rsp+148h] [rbp+40h] BYREF
  va_list ArgList; // [rsp+3A0h] [rbp+298h] BYREF

  va_start(ArgList, String1);
  v11 = 0;
  memset_0(Format, 0, sizeof(Format));
  LOBYTE(v2) = (unsigned __int8)memset_0(Buffer, 0, sizeof(Buffer));
  v3 = Format;
  for ( i = 255; ; --i )
  {
    v11 = i;
    v12 = v3;
    v13 = String1;
LABEL_3:
    if ( !*String1 )
      break;
    for ( j = 0; j < 4; ++j )
    {
      v6 = &(&g_WppFormatReplacements)[4 * j];
      v7 = *v6;
      if ( *v6 )
      {
        v8 = -1;
        do
          ++v8;
        while ( v7[v8] );
      }
      else
      {
        v8 = 0;
      }
      v9 = v6[2];
      v6[1] = (char *)v8;
      if ( v9 )
      {
        v2 = -1;
        do
          ++v2;
        while ( v9[v2] );
      }
      else
      {
        v2 = 0;
      }
      v6[3] = (char *)v2;
      if ( String1 )
      {
        LODWORD(v2) = _strnicmp(String1, v7, v8);
        if ( !(_DWORD)v2 )
        {
          LODWORD(v2) = FormatReplacement_Replace(&(&g_WppFormatReplacements)[4 * j], &v13, &v12, &v11);
          if ( !(_DWORD)v2 )
            return v2;
          String1 = v13;
          v3 = v12;
          i = v11;
          goto LABEL_3;
        }
      }
    }
    if ( !i )
      return v2;
    LOBYTE(v2) = *String1++;
    *v3++ = v2;
  }
  *v3 = 0;
  vsprintf_s(Buffer, 0x200u, Format, ArgList);
  LOBYTE(v2) = IASTracePrintf("%s");
  return v2;
}

```

## disassembly

```asm
0x180042a80  mov     rax, rsp
0x180042a83  mov     [rax+8], rcx
0x180042a87  mov     [rax+10h], rdx
0x180042a8b  mov     [rax+18h], r8
0x180042a8f  mov     [rax+20h], r9
0x180042a93  push    rbp
0x180042a94  push    rbx
0x180042a95  push    rsi
0x180042a96  push    rdi
0x180042a97  push    r14
0x180042a99  push    r15
0x180042a9b  lea     rbp, [rax-288h]
0x180042aa2  sub     rsp, 358h
0x180042aa9  mov     rax, cs:__security_cookie
0x180042ab0  xor     rax, rsp
0x180042ab3  mov     [rbp+280h+var_40], rax
0x180042aba  mov     rbx, rcx
0x180042abd  mov     [rsp+380h+var_360], 0
0x180042ac6  lea     rcx, [rsp+380h+Format]; void *
0x180042acb  xor     edx, edx; Val
0x180042acd  mov     r8d, 100h; Size
0x180042ad3  call    memset_0
0x180042ad8  xor     edx, edx; Val
0x180042ada  lea     rcx, [rbp+280h+Buffer]; void *
0x180042ade  mov     r8d, 200h; Size
0x180042ae4  call    memset_0
0x180042ae9  lea     rdi, [rsp+380h+Format]
0x180042aee  mov     esi, 0FFh
0x180042af3  mov     [rsp+380h+var_360], rsi
0x180042af8  mov     [rsp+380h+var_358], rdi
0x180042afd  mov     [rsp+380h+var_350], rbx
0x180042b02  cmp     byte ptr [rbx], 0
0x180042b05  jz      loc_180042BC4
0x180042b0b  xor     r14d, r14d
0x180042b0e  cmp     r14, 4
0x180042b12  jnb     loc_180042BAC
0x180042b18  mov     r15, r14
0x180042b1b  lea     rcx, g_WppFormatReplacements
0x180042b22  shl     r15, 5
0x180042b26  add     r15, rcx
0x180042b29  mov     rdx, [r15]; String2
0x180042b2c  test    rdx, rdx
0x180042b2f  jz      short loc_180042B41
0x180042b31  or      r8, 0FFFFFFFFFFFFFFFFh
0x180042b35  inc     r8
0x180042b38  cmp     byte ptr [rdx+r8], 0
0x180042b3d  jnz     short loc_180042B35
0x180042b3f  jmp     short loc_180042B44
0x180042b41  xor     r8d, r8d; MaxCount
0x180042b44  mov     rcx, [r15+10h]
0x180042b48  mov     [r15+8], r8
0x180042b4c  test    rcx, rcx
0x180042b4f  jz      short loc_180042B60
0x180042b51  or      rax, 0FFFFFFFFFFFFFFFFh
0x180042b55  inc     rax
0x180042b58  cmp     byte ptr [rcx+rax], 0
0x180042b5c  jnz     short loc_180042B55
0x180042b5e  jmp     short loc_180042B62
0x180042b60  xor     eax, eax
0x180042b62  mov     [r15+18h], rax
0x180042b66  test    rbx, rbx
0x180042b69  jz      short loc_180042B78
0x180042b6b  mov     rcx, rbx; String1
0x180042b6e  call    cs:__imp__strnicmp
0x180042b74  test    eax, eax
0x180042b76  jz      short loc_180042B7D
0x180042b78  inc     r14
0x180042b7b  jmp     short loc_180042B0E
0x180042b7d  lea     r9, [rsp+380h+var_360]
0x180042b82  mov     rcx, r15
0x180042b85  lea     r8, [rsp+380h+var_358]
0x180042b8a  lea     rdx, [rsp+380h+var_350]
0x180042b8f  call    FormatReplacement_Replace
0x180042b94  test    eax, eax
0x180042b96  jz      short loc_180042BF2
0x180042b98  mov     rbx, [rsp+380h+var_350]
0x180042b9d  mov     rdi, [rsp+380h+var_358]
0x180042ba2  mov     rsi, [rsp+380h+var_360]
0x180042ba7  jmp     loc_180042B02
0x180042bac  cmp     rsi, 1
0x180042bb0  jb      short loc_180042BF2
0x180042bb2  mov     al, [rbx]
0x180042bb4  inc     rbx
0x180042bb7  mov     [rdi], al
0x180042bb9  inc     rdi
0x180042bbc  dec     rsi
0x180042bbf  jmp     loc_180042AF3
0x180042bc4  lea     r9, [rbp+280h+ArgList]; ArgList
0x180042bcb  mov     byte ptr [rdi], 0
0x180042bce  lea     r8, [rsp+380h+Format]; Format
0x180042bd3  mov     edx, 200h; BufferCount
0x180042bd8  lea     rcx, [rbp+280h+Buffer]; Buffer
0x180042bdc  call    cs:__imp_vsprintf_s
0x180042be2  lea     rdx, [rbp+280h+Buffer]
0x180042be6  lea     rcx, aS_1; "%s"
0x180042bed  call    IASTracePrintf
0x180042bf2  mov     rcx, [rbp+280h+var_40]
0x180042bf9  xor     rcx, rsp; StackCookie
0x180042bfc  call    __security_check_cookie
0x180042c01  add     rsp, 358h
0x180042c08  pop     r15
0x180042c0a  pop     r14
0x180042c0c  pop     rdi
0x180042c0d  pop     rsi
0x180042c0e  pop     rbx
0x180042c0f  pop     rbp
0x180042c10  retn
```
